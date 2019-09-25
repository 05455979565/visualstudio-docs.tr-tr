---
title: 'CA2000: Kapsamı kaybetmeden önce nesneleri bırakın'
ms.date: 05/14/2019
ms.topic: reference
f1_keywords:
- CA2000
- Dispose objects before losing scope
- DisposeObjectsBeforeLosingScope
helpviewer_keywords:
- CA2000
- DisposeObjectsBeforeLosingScope
ms.assetid: 0c3d7d8d-b94d-46e8-aa4c-38df632c1463
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 7a498a01741b86c16a52f790489dc8ce62aad06c
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/24/2019
ms.locfileid: "71233237"
---
# <a name="ca2000-dispose-objects-before-losing-scope"></a>CA2000: Kapsamı kaybetmeden önce nesneleri bırakın

|||
|-|-|
|TypeName|DisposeObjectsBeforeLosingScope|
|CheckId|CA2000|
|Kategori|Microsoft. güvenilirliği|
|Son değişiklik|Kırılmamış|

## <a name="cause"></a>Sebep

Bir <xref:System.IDisposable> türün yerel nesnesi oluşturulur, ancak nesne tüm başvuruları kapsam dışı olmadan önce nesne atılamaz.

## <a name="rule-description"></a>Kural açıklaması

Bir atılabilir nesnesi, tüm başvuruları kapsam dışına çıkarılmadan önce açıkça atılmaz, çöp toplayıcı nesnenin sonlandırıcısını çalıştırdığında, nesne belirsiz bir zamanda silinir. Nesnenin sonlandırıcısını çalışmasını engelleyecek olağanüstü bir olay ortaya çıkabilecek için, bunun yerine nesne açıkça atılmalıdır.

### <a name="special-cases"></a>Özel durumlar

CA2000 kuralı, nesne atılmasa bile aşağıdaki türlerin yerel nesneleri için başlatılmıyor:

- <xref:System.IO.Stream?displayProperty=nameWithType>
- <xref:System.IO.TextReader?displayProperty=nameWithType>
- <xref:System.IO.TextWriter?displayProperty=nameWithType>
- <xref:System.Resources.IResourceReader?displayProperty=nameWithType>

Bu türlerden birine ait bir nesnenin bir oluşturucuya geçirilmesi ve sonra bir alana atanması, yeni oluşturulan türe bir *atma sahipliğinin aktarılmasını* gösterir. Diğer bir deyişle, yeni oluşturulan tür artık nesnenin elden atılırken sorumludur. Kodunuz bu türlerden birinin bir nesnesini bir oluşturucuya geçirirse, nesne tüm başvuruları kapsam dışı olmadan önce atılmasa bile kural CA2000 hiçbir ihlalin gerçekleşmez.

## <a name="how-to-fix-violations"></a>İhlalleri çözme

Bu kuralın ihlalini onarmak için, tüm başvuruları <xref:System.IDisposable.Dispose%2A> kapsam dışı olmadan önce nesne üzerinde çağrı yapın.

[ `using` ](/dotnet/csharp/language-reference/keywords/using-statement) [`Using`](/dotnet/visual-basic/language-reference/statements/using-statement) Uygulayan nesnelerikaydırmakiçin(VisualBasic)ifadesinikullanabilirsiniz<xref:System.IDisposable>. Bu şekilde Sarmalanan nesneler `using` bloğun sonuna otomatik olarak silinir. Ancak aşağıdaki durumlar, bir `using` ifadesiyle birlikte işlenmemelidir.

- Bir atılabilir nesnesi döndürmek için, nesnesinin bir `try/finally` `using` blok dışında bir blokta oluşturulması gerekir.

- Bir `using` deyimin oluşturucusunda bir atılabilir nesnesinin üyelerini başlatmayın.

- Yalnızca bir özel durum işleyicisi tarafından korunan oluşturucular [bir `using` deyimin alım bölümünde](/dotnet/csharp/language-reference/language-specification/statements#the-using-statement)iç içe geçmişse, dış oluşturucudaki bir hata, iç içe Oluşturucu tarafından oluşturulan nesnenin hiçbir zaman kapanmamış olması halinde oluşabilir. Aşağıdaki örnekte, <xref:System.IO.StreamReader> oluşturucudaki bir hata <xref:System.IO.FileStream> nesnenin hiçbir şekilde kapanmamış olması olabilir. CA2000 bayraklar bu durumda kural ihlaline neden oluyor.

   ```csharp
   using (StreamReader sr = new StreamReader(new FileStream("C:\myfile.txt", FileMode.Create)))
   { ... }
   ```

- Dinamik nesneler, <xref:System.IDisposable> nesnelerin Dispose modelini uygulamak için bir gölge nesnesi kullanmalıdır.

## <a name="when-to-suppress-warnings"></a>Uyarıların ne zaman bastırılamıyor

Bu kuraldan bir uyarıyı şu durumlar dışında gösterme:

- Nesneniz için Şunu çağıran `Dispose`bir yöntemi (örneğin,<xref:System.IO.Stream.Close%2A>
- Uyarıyı tetikleyen Yöntem, nesnenizin sarmaladığı bir <xref:System.IDisposable> nesne döndürüyor
- Ayırma yöntemi Dispose sahipliğini içermez; diğer bir deyişle, nesneyi atılama sorumluluğu, yönteminde oluşturulan ve çağırana döndürülen başka bir nesne veya sarmalayıcı için aktarılır

## <a name="related-rules"></a>İlgili kurallar

- [CA2213 Atılabilir alanlar atılmalıdır](../code-quality/ca2213-disposable-fields-should-be-disposed.md)
- [CA2202 Nesneleri birden çok kez atma](../code-quality/ca2202-do-not-dispose-objects-multiple-times.md)

## <a name="example"></a>Örnek

Atılabilir nesnesi döndüren bir yöntem uygularsanız, nesnenin atılmış olduğundan emin olmak için catch bloğu olmayan bir try/finally bloğu kullanın. Bir try/finally bloğu kullanarak, özel durumların hata noktasında ortaya çıkmasına ve nesnenin atıldığından emin olmanızı sağlayabilirsiniz.

OpenPort1 yönteminde, ISerializable nesne SerialPort 'u açma çağrısı veya SomeMethod çağrısı başarısız olabilir. Bu uygulamada bir CA2000 uyarısı oluşturulur.

OpenPort2 yönteminde, iki SerialPort nesnesi bildirilmiştir ve null olarak ayarlanır:

- `tempPort`, yöntem işlemlerinin başarılı olduğunu test etmek için kullanılır.

- `port`, yönteminin dönüş değeri için kullanılır.

Oluşturulur ve bir `try` blokta açılır ve diğer tüm gerekli işler aynı `try` blokta gerçekleştirilir. `tempPort` `try` Bloğun sonunda, açılan bağlantı noktası döndürülecek `port` nesneye atanır ve `tempPort` nesne olarak `null`ayarlanır.

`finally` Bloğu değerini`tempPort`denetler. Null değilse, yöntemindeki bir işlem başarısız olur ve `tempPort` tüm kaynakların serbest bırakılmış olduğundan emin olmak için kapalıdır. Döndürülen bağlantı noktası nesnesi, metodun işlemleri başarılı olursa Açık SerialPort nesnesini içerir veya bir işlem başarısız olursa null olur.

```csharp
public SerialPort OpenPort1(string portName)
{
   SerialPort port = new SerialPort(portName);
   port.Open();  //CA2000 fires because this might throw
   SomeMethod(); //Other method operations can fail
   return port;
}

public SerialPort OpenPort2(string portName)
{
   SerialPort tempPort = null;
   SerialPort port = null;
   try
   {
      tempPort = new SerialPort(portName);
      tempPort.Open();
      SomeMethod();
      //Add any other methods above this line
      port = tempPort;
      tempPort = null;

   }
   finally
   {
      if (tempPort != null)
      {
         tempPort.Close();
      }
   }
   return port;
}
```

```vb
Public Function OpenPort1(ByVal PortName As String) As SerialPort

   Dim port As New SerialPort(PortName)
   port.Open()    'CA2000 fires because this might throw
   SomeMethod()   'Other method operations can fail
   Return port

End Function

Public Function OpenPort2(ByVal PortName As String) As SerialPort

   Dim tempPort As SerialPort = Nothing
   Dim port As SerialPort = Nothing

   Try
      tempPort = New SerialPort(PortName)
      tempPort.Open()
      SomeMethod()
      'Add any other methods above this line
      port = tempPort
      tempPort = Nothing

   Finally
      If Not tempPort Is Nothing Then
         tempPort.Close()
      End If

   End Try

   Return port

End Function
```

## <a name="example"></a>Örnek

Varsayılan olarak, Visual Basic derleyicisinde tüm aritmetik işleçler taşma için denetlenir. Bu nedenle, herhangi bir <xref:System.OverflowException>Visual Basic aritmetik işlemi oluşturabilir. Bu, CA2000 gibi kurallarda beklenmeyen ihlallere neden olabilir. Örneğin, Visual Basic derleyici, StreamReader atılmasına neden olacak bir özel durum oluşturabilecek ekleme için bir taşma denetimi yönergesi yaydığı için, aşağıdaki CreateReader1 işlevi bir CA2000 ihlaline neden olur.

Bunu yapmak için, projenizdeki Visual Basic derleyicisinden taşma denetimleri yaymayı devre dışı bırakabilir veya kodunuzu aşağıdaki CreateReader2 işlevinde olarak değiştirebilirsiniz.

Taşma denetimlerinin yayışını devre dışı bırakmak için Çözüm Gezgini ' de proje adına sağ tıklayın ve ardından **Özellikler**' e tıklayın. **Derle**' ye tıklayın, **Gelişmiş derleme seçenekleri**' ne tıklayın ve ardından **tamsayı taşma denetimlerini kaldır**' ı işaretleyin.

[!code-vb[FxCop.Reliability.CA2000.DisposeObjectsBeforeLosingScope#1](../code-quality/codesnippet/VisualBasic/ca2000-dispose-objects-before-losing-scope-vboverflow_1.vb)]

## <a name="see-also"></a>Ayrıca bkz.

- <xref:System.IDisposable>
- [Dispose Deseni](/dotnet/standard/design-guidelines/dispose-pattern)