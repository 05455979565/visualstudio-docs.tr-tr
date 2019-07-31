---
title: DebuggerDisplay kullanarak özel bilgileri görüntüle | Microsoft Docs
ms.date: 01/09/2019
ms.topic: conceptual
helpviewer_keywords:
- attributes, debugger
- DebuggerDisplay attribute
- DebuggerDisplayAttribute class
ms.assetid: f4eb7c76-af4e-493b-9ab6-9cb05949d9b3
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 1f8046ba598873329e6aa9fcea344504f15b4dbc
ms.sourcegitcommit: 5694c5236fa32ba7f5bc1236a853f725ec7557e9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/31/2019
ms.locfileid: "68680584"
---
# <a name="tell-the-debugger-what-to-show-using-the-debuggerdisplay-attribute-c-visual-basic-f-ccli"></a>Hata ayıklayıcıya DebuggerDisplay özniteliği kullanarak neyin gösterileceğini söyleyin (C#, Visual Basic, F#, C++/CLI)
Bir nesne, özellik veya alanın hata ayıklayıcı değişkeni penceresinde nasıl görüntülendiğini denetler.<xref:System.Diagnostics.DebuggerDisplayAttribute> Bu öznitelik türler, temsilciler, özellikler, alanlar ve derlemelere uygulanabilir. Bir temel türe uygulanmışsa öznitelik bir alt sınıf için de geçerli olur.

`DebuggerDisplay` Özniteliğin tek bir bağımsız değişkeni vardır ve bu, türü örneklerin değer sütununda görüntülenecek bir dizedir. Bu dize, küme ayraçları (`{` ve `}`) içerebilir. Bir küme ayraçları içindeki metin, alan, özellik veya yöntem olarak değerlendirilir.

Bir sınıfta geçersiz kılınan `ToString()` bir yöntem varsa, hata ayıklayıcı varsayılan `{<typeName>}`yerine geçersiz kılınan yöntemi kullanır. Bu nedenle, `ToString()` yöntemi geçersiz kıldıysanız, hata ayıklayıcı varsayılan`{<typeName>}`yerine geçersiz kılınan yöntemi kullanır ve kullanmak `DebuggerDisplay`zorunda değilsiniz. Her ikisini de kullanırsanız, `DebuggerDisplay` öznitelik geçersiz kılınan `ToString()` yönteme göre önceliklidir.

Hata ayıklayıcının bu örtük `ToString()` çağrıyı değerlendirip, **Araçlar/Seçenekler/hata ayıklama** iletişim kutusunda bir Kullanıcı ayarına bağlıdır. Visual Basic bu örtük `ToString()` değerlendirmeyi uygulamaz.

> [!IMPORTANT]
> **Araçlar/Seçenekler/hata ayıklama** iletişim kutusunda `DebuggerDisplay` **değişkenlerin ham yapısını göster Windows** onay kutusu işaretliyse, öznitelik yok sayılır.

> [!NOTE]
> Yerel kod için bu öznitelik yalnızca C++/CLI kodunda desteklenir.

Aşağıdaki tabloda, `DebuggerDisplay` özniteliğin bazı olası kullanımları ve örnek çıktıları gösterilmektedir.

|Öznitelik|Değer sütununda görünen çıkış|
|---------------| - |
|`[DebuggerDisplay("x = {x} y = {y}")]`<br /><br /> Alanlar `x` ve`y`içeren bir tür üzerinde kullanılır.|`x = 5 y = 18`|
|`[DebuggerDisplay("String value is {getString()}")]`Parametre sözdizimi diller arasında farklılık gösterebilir. Bu nedenle, dikkatli bir şekilde kullanın.|`String value is [5, 6, 6]`|

`DebuggerDisplay`adlandırılmış parametreleri de kabul edebilir.

|Parametreler|Amaç|
|----------------|-------------|
|`Name`, `Type`|Bu parametreler, Windows değişkeninin **ad** ve **tür** sütunlarını etkiler. (Oluşturucu ile aynı söz dizimini kullanan dizeler için de ayarlanabilir.) Bu parametrelerin aşırı kullanılması veya yanlış kullanılması, kafa karıştırıcı çıktıya neden olabilir.|
|`Target`, `TargetTypeName`|Öznitelik, derleme düzeyinde kullanıldığında hedef türünü belirtir.|

Autoexp.cs dosyası, derleme düzeyinde DebuggerDisplay özniteliğini kullanır. Autoexp.cs dosyası, Visual Studio 'Nun .NET nesneleri için kullandığı varsayılan genişleimleri belirler. DebuggerDisplay özniteliğini kullanma örnekleri için autoexp.cs dosyasını inceleyebilir veya varsayılan genişletmeleri değiştirmek için autoexp.cs dosyasını değiştirebilir ve derleyebilirsiniz. Autoexp.cs dosyasını değiştirmeden önce yedeklediğinizden emin olun.

Autoexp.cs oluşturmak için, VS2015 için bir Geliştirici Komut İstemi açın ve aşağıdaki komutları çalıştırın

```cmd
cd <directory containing autoexp.cs>
csc /t:library autoexp.cs
```

Sonraki hata ayıklama oturumunda, oto exp. dll ' ye yapılan değişiklikler alınacaktır.

## <a name="using-expressions-in-debuggerdisplay"></a>DebuggerDisplay içinde Ifadeleri kullanma
DebuggerDisplay özniteliğinde küme ayraçları arasında genel bir ifade kullanabilseniz de, bu uygulama önerilmez.

DebuggerDisplay içindeki genel bir ifade, yalnızca hedef türün geçerli `this` örneği için işaretçiye örtülü erişime sahiptir. İfadenin diğer adlar, Yereller veya işaretçiler erişimi yok. İfade özelliklere başvuruyorsa, bu özelliklerdeki öznitelikler işlenmez. Örneğin, alan C# `[DebuggerDisplay("Object {count - 2}")]` `Object 6` 8ise`count` , kod görüntülenir.

DebuggerDisplay içinde ifadelerin kullanılması aşağıdaki sorunlara yol açabilir:

- İfadeleri değerlendirmek hata ayıklayıcıda en pahalı işlemdir ve ifade her görüntülendiğinde değerlendirilir. Bu, kodun üzerinden adımlarken performans sorunlarına neden olabilir. Örneğin, öğelerin sayısı büyükse, bir koleksiyondaki veya listedeki değerleri göstermek için kullanılan karmaşık bir ifade çok yavaş olabilir.

- İfadeler, ifadenin yazıldığı dilin değerlendiricisi tarafından değil, geçerli yığın çerçevesinin dilinin ifade değerlendiricisi tarafından değerlendirilir. Bu, diller farklı olduğunda öngörülemeyen sonuçlara neden olabilir.

- Bir ifadeyi değerlendirmek uygulamanın durumunu değiştirebilir. Örneğin, bir özelliğin değerini ayarlayan bir ifade, yürütülen koddaki özellik değerini indirger.

  İfade değerlendirmesinin olası sorunlarını azaltmanın bir yolu, işlemi gerçekleştiren ve bir dize döndüren özel bir özellik oluşturmaktır. DebuggerDisplay özniteliği daha sonra bu özel özelliğin değerini gösterebilir. Aşağıdaki örnek bu kalıbı uygular:

```csharp
[DebuggerDisplay("{DebuggerDisplay,nq}")]
public sealed class MyClass
{
    public int count { get; set; }
    public bool flag { get; set; }
    private string DebuggerDisplay
    {
        get
        {
            return string.Format("Object {0}", count - 2);
        }
    }
}
```

", NQ" soneki, ifade değerlendiricisi 'nin son değeri (nq = tırnak yok) görüntülerken teklifleri kaldırmasını söyler.

## <a name="example"></a>Örnek
Aşağıdaki kod örneği, ve `DebuggerDisplay` `DebuggerTypeProxy`ile `DebuggerBrowseable` birlikte nasıl kullanılacağını göstermektedir. **İzleme** penceresi gibi bir hata ayıklayıcı değişkenleri penceresinde görüntülendiğinde şuna benzer bir genişletme oluşturur:

|**Ad**|**Değer**|**Tür**|
|--------------|---------------|--------------|
|Anahtar|ünden|nesne {String}|
|Değer|3|nesne {int}|

```csharp
[DebuggerDisplay("{value}", Name = "{key}")]
internal class KeyValuePairs
{
    private IDictionary dictionary;
    private object key;
    private object value;
    public KeyValuePairs(IDictionary dictionary, object key, object value)
    {
        this.value = value;
        this.key = key;
        this.dictionary = dictionary;
    }

    public object Key
    {
        get { return key; }
        set
        {
            object tempValue = dictionary[key];
            dictionary.Remove(key);
            key = value;
            dictionary.Add(key, tempValue);
        }
    }

    public object Value
    {
        get { return this.value; }
        set
        {
            this.value = value;
            dictionary[key] = this.value;
        }
    }
}

[DebuggerDisplay("{DebuggerDisplay,nq}")]
[DebuggerTypeProxy(typeof(HashtableDebugView))]
class MyHashtable
{
    public Hashtable hashtable;

    public MyHashtable()
    {
        hashtable = new Hashtable();
    }

    private string DebuggerDisplay { get { return "Count = " + hashtable.Count; } }

    private class HashtableDebugView
    {
        private MyHashtable myhashtable;
        public HashtableDebugView(MyHashtable myhashtable)
        {
            this.myhashtable = myhashtable;
        }

        [DebuggerBrowsable(DebuggerBrowsableState.RootHidden)]
        public KeyValuePairs[] Keys
        {
            get
            {
                KeyValuePairs[] keys = new KeyValuePairs[myhashtable.hashtable.Count];

                int i = 0;
                foreach (object key in myhashtable.hashtable.Keys)
                {
                    keys[i] = new KeyValuePairs(myhashtable.hashtable, key, myhashtable.hashtable[key]);
                    i++;
                }
                return keys;
            }
        }
    }
}
```

## <a name="see-also"></a>Ayrıca Bkz.

- [DebuggerTypeProxy Özniteliğini Kullanma](../debugger/using-debuggertypeproxy-attribute.md)
- [Yönetilen nesnelerin özel görünümlerini oluşturma](../debugger/create-custom-views-of-dot-managed-objects.md)
- [C# dilinde biçim belirticileri](../debugger/format-specifiers-in-csharp.md)
- [Hata Ayıklayıcı Görüntü Öznitelikleriyle Hata Ayıklamayı Geliştirme](/dotnet/framework/debug-trace-profile/enhancing-debugging-with-the-debugger-display-attributes)
