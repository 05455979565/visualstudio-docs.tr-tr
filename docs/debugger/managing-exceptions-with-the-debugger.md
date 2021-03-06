---
title: Hata ayıklayıcı ile özel durumları yönetme | Microsoft Docs
ms.custom: seodec18
ms.date: 10/09/2018
ms.topic: how-to
f1_keywords:
- vs.debug.exceptions
- vs.debug.exceptions.find
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- run-time errors
- exception handling, during debugging
- errors [debugger]
- debugger, runtime errors
- On Error-style error handlers
- exceptions, Win32
- run-time errors, debugging
- Win32, exceptions
- run time, exceptions
- error handling
- debugging [Visual Studio], exception handling
- common language runtime, exceptions
- native run-time checks
- exceptions, debugging
ms.assetid: 43a77fa8-37d0-4c98-a334-0134dbca4ece
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: ff28944a36d338230a17cd533a4832452e42885b
ms.sourcegitcommit: c076fe12e459f0dbe2cd508e1294af14cb53119f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2020
ms.locfileid: "85348463"
---
# <a name="manage-exceptions-with-the-debugger-in-visual-studio"></a>Visual Studio 'da hata ayıklayıcı ile özel durumları yönetme

Bir özel durum, bir program yürütülürken oluşan bir hata durumu göstergesidir. Hata ayıklamaya hangi özel durumlar veya özel durum kümeleri gerektiğini ve hata ayıklayıcının hangi noktada kesilmesini istediğinizi (yani, hata ayıklayıcıda duraklatıp) söyleyebilirsiniz. Hata ayıklayıcı kesildiğinde, özel durumun oluşturulduğu yeri gösterir. Ayrıca, özel durumlar ekleyebilir veya silebilirsiniz. Visual Studio 'da bir çözüm açıkken, **özel durum ayarları** penceresini açmak için **Windows > özel durum ayarları > hata ayıkla** ' yı kullanın.

En önemli özel durumlara yanıt veren işleyiciler sağlayın. Özel durumlar için işleyiciler eklemeyi bilmeniz gerekiyorsa bkz. [daha Iyi C# kodu yazarak hataları giderme](../debugger/write-better-code-with-visual-studio.md). Ayrıca, bazı özel durumlar için yürütmeyi her zaman bölmek üzere hata ayıklayıcıyı nasıl yapılandıracağınızı öğrenin.

Bir özel durum oluştuğunda, hata ayıklayıcı **Çıkış** penceresine bir özel durum iletisi yazar. Aşağıdaki durumlarda yürütmeyi kesintiye uğratır:

- İşlenmemiş bir özel durum oluşturulur.
- Hata ayıklayıcı, herhangi bir işleyici çağrılmadan önce yürütmeyi bölmek üzere yapılandırılmıştır.
- [Yalnızca kendi kodum](../debugger/just-my-code.md)ayarlamış olursunuz ve hata ayıklayıcı kullanıcı kodunda işlenmemiş tüm özel durumları bölmek üzere yapılandırılmıştır.

> [!NOTE]
> ASP.NET, bir tarayıcıda hata sayfalarını gösteren bir üst düzey özel durum işleyicisine sahiptir. **Yalnızca kendi kodum** açık olmadığı takdirde yürütmeyi kesintiye uğramaz. Bir örnek için bkz. [hata ayıklayıcıya Kullanıcı tarafından işlenmeyen özel durumlarla devam etmesini söyleyin](#BKMK_UserUnhandled) .

<!-- Two consecutive notes are intentional here...-->

> [!NOTE]
> Visual Basic bir uygulamada hata stili Hata İşleyicilerde kullansanız bile hata ayıklayıcı tüm hataları özel durum olarak yönetir.

## <a name="tell-the-debugger-to-break-when-an-exception-is-thrown"></a>Bir özel durum oluştuğunda hata ayıklayıcıya kesilmesini söyleyin

Hata ayıklayıcı, bir özel durumun oluşturulduğu noktada yürütmeyi bölebilir, bu nedenle özel durumu bir işleyici çağrılmadan önce inceleyebilirsiniz.

**Özel durum ayarları** penceresinde (**hata ayıkla > Windows > özel durum ayarları**), **ortak dil çalışma zamanı özel durumları**gibi özel durumlar kategorisi için düğümünü genişletin. Daha sonra bu kategoride yer alan **sistem. AccessViolationException**gibi belirli bir özel durum için onay kutusunu işaretleyin. Tüm özel durumlar kategorisini de seçebilirsiniz.

![Denetlenen AccessViolationException](../debugger/media/exceptionsettingscheckaccess.png "ExceptionSettingsCheckAccess")

> [!TIP]
> Özel durumları **özel durum ayarları** araç çubuğunda **Ara** penceresini kullanarak bulabilir veya belirli ad alanlarını filtrelemek için arama kullanabilirsiniz (örneğin, **System.IO**).

**Özel durum ayarları** penceresinde bir özel durum seçerseniz, işlenmesinin ne olursa olsun, hata ayıklayıcı yürütmesi özel durumun her yerde kesilir. Şimdi özel durum ilk fırsat özel durumu olarak adlandırılır. Örneğin, birkaç senaryo aşağıda verilmiştir:

- Aşağıdaki C# konsol uygulamasında Main yöntemi bir blok içinde bir **AccessViolationException** oluşturur `try/catch` .

  ```csharp
  static void Main(string[] args)
  {
      try
      {
          throw new AccessViolationException();
          Console.WriteLine("here");
      }
      catch (Exception e)
      {
          Console.WriteLine("caught exception");
      }
      Console.WriteLine("goodbye");
  }
  ```

  **Özel durum ayarları**'nda **AccessViolationException** işaretliyse, `throw` Bu kodu hata ayıklayıcıda çalıştırdığınızda yürütme satırda kesintiye uğracaktır. Sonra yürütmeye devam edebilirsiniz. Konsolun her iki satırı da görüntülemesi gerekir:

  ```cmd
  caught exception
  goodbye
  ```

  Ancak `here` çizgiyi görüntülemez.

- C# konsol uygulaması, iki yöntemi olan bir sınıf içeren bir sınıf kitaplığına başvurur. Bir yöntem bir özel durum oluşturur ve onu işler, ancak ikinci bir yöntem aynı özel durumu oluşturur ancak işlemez.

  ```csharp
  public class Class1
  {
      public void ThrowHandledException()
      {
          try
          {
              throw new AccessViolationException();
          }
          catch (AccessViolationException ave)
          {
              Console.WriteLine("caught exception" + ave.Message);
          }
      }

      public void ThrowUnhandledException()
      {
          throw new AccessViolationException();
      }
  }
  ```

  Konsol uygulamasının Main () yöntemi aşağıda verilmiştir:

  ```csharp
  static void Main(string[] args)
  {
      Class1 class1 = new Class1();
      class1.ThrowHandledException();
      class1.ThrowUnhandledException();
  }
  ```

  **Özel durum ayarları**'nda **AccessViolationException** işaretliyse yürütme, `throw` hata ayıklayıcıda bu kodu çalıştırdığınızda hem **ThrowHandledException ()** hem de **ThrowUnhandledException ()** satırındaki satıra kadar kesilir.

Özel durum ayarlarını varsayılanlara geri yüklemek için, **listeyi varsayılan ayarlar düğmesine geri yükle** ' yi seçin:

![Özel durum ayarlarındaki Varsayılanları geri yükleme](../debugger/media/restoredefaultexceptions.png "RestoreDefaultExceptions")

## <a name="tell-the-debugger-to-continue-on-user-unhandled-exceptions"></a><a name="BKMK_UserUnhandled"></a>Hata ayıklayıcıya Kullanıcı tarafından işlenmeyen özel durumlarla devam etmesini söyleyin

[Yalnızca kendi kodum](../debugger/just-my-code.md)ile .NET veya JavaScript kodunda hata ayıklaması yapıyorsanız, hata ayıklayıcıya Kullanıcı kodunda işlenmemiş ancak başka bir yerde işlenen özel durumların kesilmesini engellemesini söyleyebilirsiniz.

1. **Özel durum ayarları** penceresinde, bir sütun etiketine sağ tıklayarak kısayol menüsünü açın ve ardından **sütunları göster > ek eylemler**' i seçin. ( **Yalnızca kendi kodum**kapalıysa, bu komutu görmezsiniz.) **Ek eylemler** adlı üçüncü bir sütun görüntülenir.

   ![Ek eylemler sütunu](../debugger/media/additionalactionscolumn.png "Adtionalactionscolumn")

   Bu sütundaki **Kullanıcı kodunda işlenmemiş olduğunda devam** eden bir özel durum için, bu özel durum Kullanıcı kodunda işlenmediğinde ancak dışarıdan işlenirse hata ayıklayıcı devam eder.

2. Belirli bir özel durum için bu ayarı değiştirmek için, özel durumu seçin, kısayol menüsünü görüntülemek için sağ tıklayın ve **Kullanıcı kodunda Işlenmemiş olduğunda devam**' ı seçin. Ayrıca, tüm ortak dil çalışma zamanı özel durumları gibi tüm özel durumlar kategorisi için ayarı da değiştirebilirsiniz.

   ![* * Kullanıcı kodunda işlenmediğinde devam et * * ayarı](../debugger/media/continuewhenunhandledinusercodesetting.png "Devam Whenunhandledınusercodesetting")

Örneğin, ASP.NET Web uygulamaları özel durumları bir HTTP 500 durum koduna dönüştürerek işler ([ASP.NET Web API 'de özel durum işleme](/aspnet/web-api/overview/error-handling/exception-handling)) ve özel durumun kaynağını belirlemenize yardımcı olabilir. Aşağıdaki örnekte, Kullanıcı kodu öğesine bir çağrısı yapar `String.Format()` <xref:System.FormatException> . Yürütme sonları aşağıdaki gibidir:

![İşlenmeyen özel durum&#45;Kullanıcı sonları](../debugger/media/exceptionunhandledbyuser.png "ExceptionUnhandledByUser")

## <a name="add-and-delete-exceptions"></a>Özel durum ekleme ve silme

Özel durumlar ekleyip silebilirsiniz. Bir kategoriden özel durum türünü silmek için, özel durumu seçin ve **özel durum ayarları** araç çubuğunda liste düğmesinden (eksi işareti) **Seçili özel durumu Sil** ' i seçin. Ya da özel duruma sağ tıklayıp kısayol menüsünden **Sil** ' i seçebilirsiniz. Bir özel durumun silinmesi, özel durumdan kaldırılmış olarak aynı etkiye sahiptir ve bu, hata ayıklayıcının oluşturulduğu zaman kesintiye uğramaması anlamına gelir.

Özel durum eklemek için:

1. **Özel durum ayarları** penceresinde, özel durum kategorisinden birini seçin (örneğin, **ortak dil çalışma zamanı**).

2. Seçili Kategori düğmesine (artı işareti) **özel durum Ekle** ' yi seçin.

   ![* * Seçili kategoriye bir özel durum ekleyin * * düğmesi](../debugger/media/addanexceptiontotheselectedcategorybutton.png "AddAnExceptionToTheSelectedCategoryButton")

3. Özel durumun adını yazın (örneğin, **System. UriTemplateMatchException**).

   ![Özel durum adını yazın](../debugger/media/typetheexceptionname.png "TypeTheExceptionName")

   Özel durum listeye eklenir (alfabetik sırada) ve otomatik olarak denetlenir.

GPU bellek erişimi özel durumları, JavaScript çalışma zamanı özel durumları veya Win32 özel durumlar kategorilerine bir özel durum eklemek için, hata kodunu ve açıklamayı ekleyin.

> [!TIP]
> Yazılışını inceleyin! **Özel durum ayarları** penceresi, eklenen bir özel durumun varlığını denetlemez. Bu nedenle, **Sydıtem. UriTemplateMatchException**yazarsanız, bu özel durum için bir giriş alırsınız ( **System. UriTemplateMatchException**için değil).

Özel durum ayarları çözümün. suo dosyasında kalıcı hale getirilir, bu nedenle belirli bir çözüme uygulanır. Belirli özel durum ayarlarını çözümler genelinde yeniden kullanamazsınız. Artık yalnızca eklenen özel durumlar kalıcıdır; Silinen özel durumlar değildir. Bir özel durum ekleyebilir, çözümü kapatıp yeniden açabilirsiniz ve özel durum hala orada olacaktır. Ancak bir özel durumu siler ve çözümü kapatabilir/yeniden açarsanız, özel durum yeniden görüntülenir.

**Özel durum ayarları** penceresi C# dilinde genel özel durum türlerini destekler, ancak Visual Basic. Gibi özel durumları kesmek için `MyNamespace.GenericException<T>` , özel durumu **MyNamespace. GenericException ' 1**olarak eklemeniz gerekir. Diğer bir deyişle, şu kod gibi bir özel durum oluşturduysanız:

```csharp
public class GenericException<T> : Exception
{
    public GenericException() : base("This is a generic exception.")
    {
    }
}
```

Özel durumu, önceki yordamı kullanarak **özel durum ayarlarına** ekleyebilirsiniz:

![Genel özel durum ekleme](../debugger/media/addgenericexception.png "AddGenericException")

## <a name="add-conditions-to-an-exception"></a>Özel duruma koşul ekleme

Özel durumların koşullarını ayarlamak için **özel durum ayarları** penceresini kullanın. Şu anda desteklenen koşullar, özel durum için dahil edilecek veya hariç tutulacak modül adlarını içerir. Modül adlarını koşul olarak ayarlayarak yalnızca belirli kod modüllerinde özel durum için kesmeyi seçebilirsiniz. Ayrıca belirli modüller üzerinde koparmaktan kaçınabilirsiniz.

> [!NOTE]
> Bir özel duruma koşul eklemek, ' den itibaren desteklenmektedir [!include[vs_dev15](../misc/includes/vs_dev15_md.md)] .

Koşullu özel durumlar eklemek için:

1. Özel durum ayarları penceresinde **Koşulları Düzenle** düğmesini seçin veya özel duruma sağ tıklayıp **Koşulları Düzenle**' yi seçin.

   ![Özel durum koşulları](../debugger/media/dbg-conditional-exception.png "DbgConditionalException")

2. Özel duruma ek gerekli koşullar eklemek için her yeni koşul için **Koşul Ekle** ' yi seçin. Ek koşul satırları görüntülenir.

   ![Özel durum için ek koşullar](../debugger/media/extraconditionsforanexception.png "ExtraConditionsForAnException")

3. Her bir koşul satırı için, modülün adını yazın ve karşılaştırma operatörü listesini **eşittir** veya **eşit**olarak değiştirin. **\\\*** Adında birden fazla modül belirtmek için joker karakterler () belirtebilirsiniz.

4. Bir koşulu silmeniz gerekiyorsa, koşul satırının sonundaki **X** seçeneğini belirleyin.

## <a name="see-also"></a>Ayrıca bkz.

- [Özel durumdan sonra yürütmeye devam etme](../debugger/continuing-execution-after-an-exception.md)<br/>
- [Nasıl yapılır: Özel durumdan sonra sistem kodunu inceleme](../debugger/how-to-examine-system-code-after-an-exception.md)<br/>
- [Nasıl yapılır: Yerel çalışma zamanı denetimlerini kullanma](../debugger/how-to-use-native-run-time-checks.md)<br/>
- [C çalışma zamanı kitaplığı olmadan çalışma zamanı denetimlerini kullanma](../debugger/using-run-time-checks-without-the-c-run-time-library.md)<br/>
- [Hata ayıklayıcıya ilk bakış](../debugger/debugger-feature-tour.md)
