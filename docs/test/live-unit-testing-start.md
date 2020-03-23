---
title: Canlı Ünite Testi ile kodunuzu nasıl test edebilirsiniz öğrenin
ms.date: 08/31/2017
ms.topic: conceptual
helpviewer_keywords:
- Live Unit Testing
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: 748dfc592fbf7a3b9737e9f418362067b92bb8ff
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/18/2020
ms.locfileid: "75594298"
---
# <a name="get-started-with-live-unit-testing"></a>Live Unit Testing kullanmaya başlama

Visual Studio çözümünde Canlı Birim Testini etkinleştirdiğinizde, test kapsamınızı ve testlerinizin durumunu görsel olarak betimler. Canlı Birim Testi, kodunuzu her değiştirdiğinizde testleri dinamik olarak yürütür ve değişikliklerinizin testlerin başarısız olması durumunda sizi hemen haber eder.

Canlı Birim Testi, .NET Framework veya .NET Core'u hedefleyen çözümleri test etmek için kullanılabilir. Bu eğitimde, .NET Standard'ı hedefleyen basit bir sınıf kitaplığı oluşturarak Canlı Birim Testi'ni kullanmayı öğreneceksiniz ve bunu test etmek için .NET Core'u hedefleyen bir MSTest projesi oluşturacaksınız.

C# çözümlerinin tamamı GitHub'daki [MicrosoftDocs/visualstudio-docs](https://github.com/MicrosoftDocs/visualstudio-docs/tree/master/docs/test/samples/csharp/UtilityLibraries/) repo'dan indirilebilir.

## <a name="prerequisites"></a>Önkoşullar

Bu öğretici, **.NET Core çapraz platform geliştirme** iş yüküyle Visual Studio Enterprise sürümünü yüklemiş olduğunuzu gerektirir.

## <a name="create-the-solution-and-the-class-library-project"></a>Çözümü ve sınıf kitaplığı projesini oluşturun

Tek bir .NET Standart sınıf kitaplık projesi olan StringLibrary'den oluşan UtilityLibraries adlı bir Visual Studio çözümü oluşturarak başlayın.

Çözüm, bir veya daha fazla proje için sadece bir kapsayıcıdır. Boş bir çözüm oluşturmak için Visual Studio'yu açın ve aşağıdakileri yapın:

1. Üst düzey Visual Studio menüsünden > **Yeni** > **Dosya'yı** seçin. **File**

1. **Çözümü** şablon arama kutusuna yazın ve ardından **Boş Çözüm** şablonunu seçin.

   ::: moniker range="vs-2017"

   ![**Yeni Proje** iletişim kutusu](./media/lut-start/new-solution.png)

   ::: moniker-end

1. Çözümü oluşturmayı bitirin.

Çözümü oluşturduğunuza göre, dizeleri ile çalışmak için bir dizi uzantı yöntemi içeren StringLibrary adlı bir sınıf kitaplığı oluşturursunuz.

1. **Çözüm Gezgini'nde,** UtilityLibraries çözümüne sağ tıklayın ve**Yeni Proje** **Ekle'yi** > seçin.

::: moniker range="vs-2017"

2. Yeni **Proje Ekle** iletişim kutusunda C# düğümünü seçin ve **ardından .NET Standard'ı**seçin.

   > [!NOTE]
   > Kitaplığımız belirli bir .NET uygulaması yerine .NET Standard'ı hedeflediği için, .NET Standard'ın bu sürümünü destekleyen herhangi bir .NET uygulamasından çağrılabilir. Daha fazla bilgi için [.NET Standard](/dotnet/standard/net-standard)' a bakın.

3. Sağ bölmedeki **Sınıf Kitaplığı (.NET Standart)** şablonunu seçin ve aşağıdaki resimde görüldüğü gibi **Ad** metin kutusuna **StringLibrary** girin:

   ![**Yeni Proje Ekle** iletişim kutusu](./media/lut-start/add-project-cs.png)

4. Projeyi oluşturmak için **Tamam**'ı seçin.

::: moniker-end

::: moniker range=">=vs-2019"

2. **Sınıf kitaplığını** şablon arama kutusuna yazın ve **Sınıf Kitaplığı (.NET Standart)** şablonunu seçin. **İleri**'ye tıklayın.

   > [!NOTE]
   > Kitaplığımız belirli bir .NET uygulaması yerine .NET Standard'ı hedeflediği için, .NET Standard'ın bu sürümünü destekleyen herhangi bir .NET uygulamasından çağrılabilir. Daha fazla bilgi için [.NET Standard](/dotnet/standard/net-standard)' a bakın.

3. Proje **StringLibrary'yi**adlandırın.

4. Projeyi oluşturmak için **Oluştur'u** tıklatın.

::: moniker-end

5. Kod penceresindeki varolan kodun tümünün değiştirin:

   [!code-csharp[StringLibrary source code](samples/csharp/utilitylibraries/stringlibrary/class1.cs)]

   StringLibrary'nin üç statik yöntemi vardır:

   - `StartsWithUpper`bir `true` dize büyük harf libir karakterle başlarsa döndürür; aksi takdirde, `false`döner .

   - `StartsWithLower`bir `true` dize küçük bir karakterle başlarsa döndürür; aksi takdirde, `false`döner .

   - `HasEmbeddedSpaces`bir `true` dize katıştırılmış bir beyaz boşluk karakteri içeriyorsa döndürür; aksi takdirde, `false`döner .

6. Üst düzey Visual Studio menüsünden **Yapı** > **Çözümünü** seçin. Yapı başarılı olmalıdır.

## <a name="create-the-test-project"></a>Test projesini oluşturma

Bir sonraki adım, StringLibrary kitaplığını sınamak için birim test projesi oluşturmaktır. Aşağıdaki adımları gerçekleştirerek birim testleri oluşturun:

1. **Çözüm Gezgini'nde,** UtilityLibraries çözümüne sağ tıklayın ve**Yeni Proje** **Ekle'yi** > seçin.

::: moniker range="vs-2017"

2. Yeni **Proje Ekle** iletişim kutusunda C# düğümünü seçin ve **ardından .NET Core'u**seçin.

   > [!NOTE]
   > Ünite testlerinizi sınıf kitaplığınız ile aynı dilde yazmak zorunda değildir.

3. Sağ bölmedeki **Birim Test Projesi (.NET Core)** şablonunu seçin ve aşağıdaki resimde görüldüğü gibi **StringLibraryTests'i Ad** metin kutusuna girin: **StringLibraryTests**

   ![Birim test projesi için **Yeni Proje Ekle** iletişim kutusu](./media/lut-start/add-unit-test-cs.png)

4. Projeyi oluşturmak için **Tamam**'ı seçin.

::: moniker-end

::: moniker range=">=vs-2019"

2. **Birim testini** şablon arama kutusuna yazın ve Birim Test **Projesi (.NET Core)** şablonunu seçin. **İleri**'ye tıklayın.

3. Proje **StringLibraryTests**adını.

4. Projeyi oluşturmak için **Oluştur'u** tıklatın.

::: moniker-end

   > [!NOTE]
   > Bu başlangıç öğretici MSTest test çerçevesi ile Canlı Birim Testi kullanır. XUnit ve NUnit test çerçevelerini de kullanabilirsiniz.

5. Birim test projesi, test ettiği sınıf kitaplığına otomatik olarak erişemez. Sınıf kitaplığı projesine bir başvuru ekleyerek test kitaplığına erişim sağlarsınız. `StringLibraryTests` Bunu yapmak için projeye sağ tıklayın ve**Başvuru** **Ekle'yi** > seçin. Başvuru **Yöneticisi** iletişim kutusunda, **Çözüm** sekmesinin seçildiğinden emin olun ve aşağıdaki resimde gösterildiği gibi StringLibrary projesini seçin.

   ![**Başvuru Yöneticisi** iletişim kutusu](./media/lut-start/add-reference.png)

6. Şablon tarafından sağlanan ortak birim test kodunu aşağıdaki kodla değiştirin:

   [!code-csharp[StringLibraryTest source code](samples/snippets/csharp/lut-start/unittest1.cs)]

7. Araç çubuğundaki **Kaydet** simgesini seçerek projenizi kaydedin.

8. Birim test kodu bazı ASCII olmayan karakterler içerdiğinden, Visual Studio dosyayı varsayılan ASCII biçiminde kaydederseniz bazı karakterlerin kaybolacağı konusunda uyarmak için aşağıdaki iletişim kutusunu görüntüler. Diğer **Kodlama yla Kaydet** düğmesini seçin.

   ![Dosya kodlaması seçin](media/lut-start/ascii-encoding.png)

9. **Gelişmiş Kaydet Seçenekleri** iletişim kutusunun **Kodlama** açılır listesinde, Aşağıdaki resimde görüldüğü gibi **Unicode (imzasız UTF-8) - Codepage 65001'** i seçin:

   ![UTF-8 kodlamaseçimi](media/lut-start/utf8-encoding.png)

10. Üst düzey Visual Studio menüsünden **Rebuild** > **Solution'ı** seçerek birim test projesini derleyin.

Bunun için bazı birim testlerinin yanı sıra bir sınıf kitaplığı da oluşturdunuz. Canlı Birim Testini kullanmak için gereken ön hazırlıkları tamamladınız.

## <a name="enable-live-unit-testing"></a>Canlı Birim Testini Etkinleştir

Şimdiye kadar, StringLibrary sınıf kitaplığı için testleri yazmış olsanız da, bunları yürütemediniz. Canlı Birim Testi, etkinleştirdikten sonra bunları otomatik olarak yürütür. Bunu yapmak için aşağıdakileri yapın:

1. İsteğe bağlı olarak, StringLibrary kodunu içeren kod penceresini seçin. Bu, bir C# projesi için *Class1.cs* veya Visual Basic projesi için *Class1.vb'dir.* (Bu adım, Canlı Birim Testi'ni etkinleştirdikten sonra testlerinizin sonucunu ve kod kapsamınızın kapsamını görsel olarak incelemenize olanak tanır.)

1.  > En üst düzey Visual Studio menüsünden**Canlı Birim Test** > **Başlat'ı** seçin. **Test**

1. Visual Studio, tüm testlerinizi otomatik olarak çalıştıran Canlı Birim Testi'ni başlatır.

Test **Gezgini,** testlerinizi çalıştırmayı bitirdiğinde, hem genel sonuçları hem de tek tek testlerin sonuçlarını görüntüler. Buna ek olarak, kod penceresi hem test kodu kapsamınızı hem de testlerinizin sonucunu grafik olarak görüntüler. Aşağıdaki resimde de görüldüğü gibi, üç test de başarıyla yürütülmüştür. Ayrıca, testlerimizin `StartsWithUpper` yöntemdeki tüm kod yollarını kapsadığını ve bu testlerin hepsinin başarıyla yürütüldettiğini de gösterir (yeşil onay işareti "✓" ile gösterilir). Son olarak, StringLibrary'deki diğer yöntemlerin hiçbirinde kod kapsamı olmadığını gösterir (mavi bir satırla gösterilir, "➖").

![Canlı Birim testini başladıktan sonra Test Gezgini ve kod penceresi](media/lut-start/lut-results-cs.png)

Ayrıca, kod penceresinde belirli bir kod kapsamı simgesini seçerek test kapsamı ve test sonuçları hakkında daha ayrıntılı bilgi edinebilirsiniz. Bu ayrıntıyı incelemek için aşağıdakileri yapın:

1. Yöntemde okuyan `if (String.IsNullOrWhiteSpace(s))` satırdaki yeşil onay işaretini `StartsWithUpper` tıklatın. Aşağıdaki resimde de görüldüğü gibi, Canlı Birim Testi üç testin bu kod satırını kapsadığını ve hepsinin başarıyla yürütüldettiğini gösterir.

   !['if' koşullu deyimi için kod kapsamı](media/lut-start/code-coverage-cs1.png)

1. Yöntemde okuyan `return Char.IsUpper(s[0])` satırdaki yeşil onay işaretini `StartsWithUpper` tıklatın. Aşağıdaki resimde de görüldüğü gibi, Canlı Birim Testi yalnızca iki testin bu kod satırını kapsadığını ve hepsinin başarıyla yürütüldettiğini gösterir.

   ![İade deyimi için kod kapsamı](media/lut-start/code-coverage-cs2.png)

Canlı Birim Testi'nin tanımladığı en önemli sorun eksik kod kapsamıdır. Bir sonraki bölümde ele alabilirsiniz.

## <a name="expand-test-coverage"></a>Test kapsamını genişletme

Bu bölümde, birim testlerinizi `StartsWithLower` yönteme genişletirsiniz. Bunu yaparken, Canlı Birim Testi dinamik olarak kodunuzu test etmeye devam edecektir.

Kod kapsamını `StartsWithLower` yönteme genişletmek için aşağıdakileri yapın:

1. Projenizin `TestStartsWithLower` `TestDoesNotStartWithLower` test kaynak kodu dosyasına aşağıdaki leri ve yöntemleri ekleyin:

    [!code-csharp[StringLibraryTest source code](samples/snippets/csharp/lut-start/unittest2.cs#1)]

1. Çağrıdan `DirectCallWithNullOrEmpty` hemen sonra yönteme aşağıdaki kodu [`Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsFalse`](/dotnet/api/microsoft.visualstudio.testtools.unittesting.assert.isfalse) ekleyerek yöntemi değiştirin.

    [!code-csharp[StringLibraryTest source code](samples/snippets/csharp/lut-start/unittest2.cs#2)]

1. Canlı Birim Testi, kaynak kodunuzu değiştirdiğinizde yeni ve değiştirilmiş testleri otomatik olarak yürütür. **Test Gezgini'nin** aşağıdaki resminin gösterdiği gibi, eklediğiniz ve değiştirdiğiniz iki test de dahil olmak üzere tüm testler başarılı oldu.

   ![Test kapsamını genişlettikten sonra Test Gezgini](media/lut-start/test-dynamic.png)

1. StringLibrary sınıfının kaynak kodunu içeren pencereye geçin. Canlı Birim Testi artık kod kapsamımızın `StartsWithLower` yönteme genişletilmesini gösteriyor.

    ![StartsWithLower yöntemi için kod kapsamı](media/lut-start/lut-extended-cs.png)

Bazı durumlarda, Test **Gezgini'ndeki** başarılı testler gri renkte olabilir. Bu, bir testin şu anda yürütüldettiğini veya testin en son yürütülmediğinden beri testi etkileyecek kod değişikliği olmadığından yeniden çalışmadığını gösterir.

Şimdiye kadar, tüm testlerimiz başarılı oldu. Bir sonraki bölümde, test başarısızlığıyla nasıl başa çıkabileceğinizi inceleyeceğiz.

## <a name="handle-a-test-failure"></a>Test hatalarını işleme

Bu bölümde, test hatalarını tanımlamak, sorun gidermek ve adreslemek için Canlı Birim Testini nasıl kullanabileceğinizi araştıracaksınız. Bunu, test kapsamını `HasEmbeddedSpaces` yönteme genişleterek yaparsınız.

1. Test dosyanıza aşağıdaki yöntemi ekleyin:

    [!code-csharp[The TestHasEmbeddedSpaces test method](samples/snippets/csharp/lut-start/unittest2.cs#3)]

1. Test yürütüldüğünde, Canlı Birim Testi `TestHasEmbeddedSpaces` aşağıdaki resimde görüldüğü gibi yöntemin başarısız olduğunu gösterir:

   ![Test Gezgini başarısız bir testi bildiriyor](media/lut-start/test-failure.png)

1. Kitaplık kodunu görüntüleyen pencereyi seçin. Canlı Birim Testi, kod `HasEmbeddedSpaces` kapsamını yönteme genişletti. Ayrıca, başarısız testler in kapsadığı🞩satırlara kırmızı " " " ekleyerek test başarısızlığını bildirir.

1. Yöntem imzası ile çizginin `HasEmbeddedSpaces` üzerine geçin. Canlı Birim Testi, yöntemin bir test tarafından kapsandığını bildiren bir araç ipucu görüntüler:

   ![Başarısız bir testte Canlı Birim Test bilgileri](media/lut-start/test-failure-info-cs.png)

1. Başarısız **TestHasEmbeddedSpaces** testini seçin. Canlı Birim Testi, aşağıdaki resimde görüldüğü gibi, tüm testleri çalıştırma, seçili testleri hata ayıklama ve seçili testleri hata ayıklama gibi bir dizi seçenek sunar:

   ![Başarısız bir test için Canlı Birim Test seçenekleri](media/lut-start/test-failure-options.png)

1. Başarısız testi hata ayıklamak için **Seçili Hata** Ayıklama'yı seçin.

1. Visual Studio testi hata ayıklama modunda yürütür.

   Test, dizideki her dizeyi adlı `phrase` bir değişkene `HasEmbeddedSpaces` atar ve yönteme geçirir. Program yürütme duraklar ve assert ifadesi ilk kez hata `false`ayıklama çağırır. [`Microsoft.VisualStudio.TestTools.UnitTesting.Assert.IsTrue`](/dotnet/api/microsoft.visualstudio.testtools.unittesting.assert.istrue) Yöntem çağrısında beklenmeyen değerden kaynaklanan özel durum iletişim kutusu aşağıdaki resimde gösterilir.

   ![Canlı Birim Testi özel durum iletişim kutusu](media/lut-start/exception-dialog-cs.png)

   Buna ek olarak, Visual Studio'nun sağladığı hata ayıklama araçlarının tümü, aşağıdaki resimde görüldüğü gibi, başarısız testimizin sorunsuz giderilmesine yardımcı olmak için kullanılabilir:

   ![Visual Studio hata ayıklama araçları](media/lut-start/debugging-tools-cs.png)

   **Otomatik ler** `phrase` penceresinde, değişkenin değerinin dizinin ikinci öğesi olan "Name\tDescription" olduğunu unutmayın. Test yöntemi `HasEmbeddedSpaces` bu `true` dize geçtizaman dönmek için bekliyor; bunun yerine, `false`döner. Açıkçası, "\t", sekme karakteri, gömülü bir boşluk olarak tanımıyor.

1. **Hata Ayıklama** > **Devam'ı**seçin, **F5**tuşuna basın veya test programını yürütmeye devam etmek için araç çubuğundaki **Devam** düğmesini tıklatın. Işlenmemiş bir özel durum oluştuğundan, test sonlanır.
Bu, hatanın ön incelemesi için yeterli bilgi sağlar. Ya `TestHasEmbeddedSpaces` (test yordamı) yanlış bir `HasEmbeddedSpaces` varsayım yaptı veya doğru tüm katıştırılmış boşlukları tanımıyor.

1. Sorunu tanılamak ve düzeltmek için `StringLibrary.HasEmbeddedSpaces` yöntemle başlayın. Yöntemdeki karşılaştırmaya `HasEmbeddedSpaces` bak. Gömülü bir alanı U+0020 olarak kabul eder. Ancak, Unicode Standart diğer boşluk karakterleri bir dizi içerir. Bu, kitaplık kodunun bir beyaz alan karakteri için yanlış şekilde sınandığını gösterir.

1. Eşitlik karşılaştırmasını yönteme yapılan <xref:System.Char.IsWhiteSpace%2A?displayProperty=fullName> bir çağrıyla değiştirin:

    [!code-csharp[The TestHasEmbeddedSpaces test method](samples/snippets/csharp/lut-start/program2.cs#1)]

1. Canlı Birim Testi başarısız test yöntemini otomatik olarak yeniden çalıştırAr ve aşağıdaki resimde görüldüğü gibi kod penceresinde ve **Test Gezgini'nde**sonuçları güncelleştirir:

    ![Başarılı HasEmbeddedSpaces testi](media/lut-start/test-success-cs.png)

## <a name="see-also"></a>Ayrıca bkz.

- [Visual Studio Canlı Ünite Testi](live-unit-testing.md)
- [Canlı Ünite Testi Sık Sorulan Sorular](live-unit-testing-faq.md)
