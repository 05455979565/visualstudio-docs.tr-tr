---
title: Live Unit Testing
ms.date: 03/07/2017
ms.topic: conceptual
helpviewer_keywords:
- Live Unit Testing
author: jillre
ms.author: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: b5974819e9dca064655cf04eec3dd371f09ee15c
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72652998"
---
# <a name="how-to-configure-and-use-live-unit-testing"></a>Live Unit Testing yapılandırma ve kullanma

Bir uygulama geliştirirken, Live Unit Testing etkilenen birim testlerini arka planda otomatik olarak çalıştırır ve sonuçları ve kod kapsamını gerçek zamanlı olarak gösterir. Kodunuzu değiştirirken Live Unit Testing, değişikliklerinizin mevcut testleri nasıl etkilediği ve eklediğiniz yeni kodun bir veya daha fazla var olan testlerin kapsamında olup olmadığı hakkında geri bildirim sağlar. Bu, hata düzeltmeleri yaparken veya yeni özellikler eklerken birim testlerini yazmanızı ister.

> [!NOTE]
> Live Unit Testing, Visual Studio C# Enterprise sürümünde .NET Core veya .NET Framework hedefleyen projeleri ve Visual Basic kullanılabilir.

Testleriniz için Live Unit Testing kullandığınızda, testlerin durumu hakkında verileri sürdürür. Kalıcı verilerin kullanılması, kod değişikliklerine yanıt olarak testlerinizi dinamik olarak çalıştırırken Live Unit Testing üstün performans sunmasına olanak tanır.

## <a name="supported-test-frameworks"></a>Desteklenen test çerçeveleri

Live Unit Testing, aşağıdaki tabloda listelenen üç popüler birim testi çerçevesi ile birlikte kullanılabilir. Bağdaştırıcılarının en düşük desteklenen sürümü ve çerçeveleri de gösterilir. Birim test çerçevelerinin tümü NuGet.org adresinden kullanılabilir.

|Test çerçevesi  |Visual Studio bağdaştırıcısı en düşük sürüm  |Framework minimum sürümü  |
|---------|---------|---------|
|xUnit.net |xUnit. Runner. VisualStudio sürüm 2.2.0-Beta3-build1187 |xUnit 1.9.2 |
|NUnit |NUnit3TestAdapter sürümü 3.5.1 |NUnit sürümü 3.5.0 |
|MSTest |MSTest. TestAdapter 1.1.4-Önizleme |MSTest. TestFramework 1.0.5-Önizleme |

Microsoft. VisualStudio. QualityTools. UnitTestFramework 'e başvuran daha önceden MSTest tabanlı test projelerine sahipseniz ve yeni MSTest NuGet paketlerine geçmek istemiyorsanız, Visual Studio 2019 veya Visual Studio 2017 sürümüne yükseltin.

Bazı durumlarda, Live Unit Testing çalışması için bir proje tarafından başvurulan NuGet paketlerini açıkça geri yüklemeniz gerekebilir. Bu işlemi,  >  çözümün açık bir derlemesini yaparak veya çözüm içindeki paketleri geri yükleyerek**yapabilirsiniz (çözüme** sağ tıklayıp NuGet 'ı geri yükle **' yi seçin** .  **Paketler**).

## <a name="configure"></a>Yapılandırma

Üst düzey Visual Studio menü çubuğunda **araçlar**  > **Seçenekler** ' i ve ardından **seçenekler** iletişim kutusunun sol bölmesinde **Live Unit Testing** ' yı seçerek Live Unit Testing yapılandırın.

> [!TIP]
> Live Unit Testing etkinleştirildikten sonra (bkz. bir sonraki bölüm, [başlatma, duraklatma ve durdurma Live Unit Testing](#start-pause-and-stop)), **Seçenekler** iletişim kutusunu da **Test**  > **Live Unit Testing**  > **seçeneklerini**belirleyerek açabilirsiniz.

Aşağıdaki görüntüde iletişim kutusunda kullanılabilen Live Unit Testing yapılandırma seçenekleri gösterilmektedir:

![Live Unit Testing yapılandırma seçenekleri](./media/lut-options.png)

Yapılandırılabilir seçenekler şunlardır:

- Bir çözüm oluşturulup hata ayıklandığında Live Unit Testing duraklatılır.

- Sistemin pil gücü belirtilen eşiğin altına düştüğünde Live Unit Testing duraklayacağını belirtir.

- Bir çözüm açıldığında Live Unit Testing otomatik olarak çalışıp çalışmadığını belirtir.

- Hata ayıklama sembolü ve XML belge açıklaması oluşturma 'nın etkinleştirilip etkinleştirilmeyeceğini belirtir.

- Kalıcı verilerin depolandığı dizin.

- Tüm kalıcı verileri silme özelliği. Live Unit Testing, kalıcı olmayan veya beklenmedik bir şekilde davranmışsa, kalıcı verilerin bozulmasından etkileneceği durumlarda faydalıdır.

- Bir test çalışmasının zaman aşımına uğramadan zaman aralığı. Varsayılan değer 30 saniyedir.

- Live Unit Testing oluşturduğu test işlemlerinin maksimum sayısı.

- Live Unit Testing işlemlerin tüketebileceği maksimum bellek miktarı.

- Live Unit Testing **Çıkış** penceresine yazılan bilgi düzeyi.

   Seçenekler, günlüğe kaydetme (**yok**), yalnızca hata Iletileri (**hata**), hata ve bilgilendirici iletiler (**bilgi**, varsayılan) veya tüm ayrıntılar (**verbose**) içerir.

   Ayrıca, `VS_UTE_DIAGNOSTICS` adlı bir Kullanıcı düzeyi ortam değişkenine "1" değeri atayarak ve ardından Visual Studio 'Yu yeniden başlatarak Live Unit Testing **Çıkış** penceresinde ayrıntılı çıkış görüntüleyebilirsiniz.

   Bir dosyadaki Live Unit Testing ayrıntılı MSBuild günlük iletilerini yakalamak için, `LiveUnitTesting_BuildLog` Kullanıcı düzeyi ortam değişkenini, günlüğü içeren dosyanın adı olarak ayarlayın.

## <a name="start-pause-and-stop"></a>Başlat, Duraklat ve durdur

Live Unit Testing etkinleştirmek için, en üst düzey Visual Studio menüsünden **Test**  > **Live Unit Testing**  > **Başlat** ' ı seçin. Live Unit Testing etkinleştirildiğinde, **Live Unit Testing** menüdeki seçenekler tek bir öğeden değişir, **başlatılır** **,** **duraklatılır**ve temiz bir şekilde **sıfırlanır**:

- **Duraklatma** Live Unit Testing geçici olarak askıya alır.

  Live Unit Testing duraklatıldığında, kapsam görselleştirmesi düzenleyicide görünmez, ancak toplanan tüm veriler korunur. Live Unit Testing sürdürmek için Live Unit Testing menüsünden **devam** ' ı seçin. Live Unit Testing, duraklatıldığı sırada yapılan tüm düzenlemeleri yakalamak ve glifleri uygun şekilde güncelleştirirken gerekli işi yapar.

- Live Unit Testing **tamamen durdurulur** . Live Unit Testing, topladığı tüm verileri atar.

- **Temizleme Işlemini sıfırlayın** Live Unit Testing, kalıcı verileri siler ve sonra Live Unit Testing yeniden başlatır.

> [!NOTE]
> Birim testi projesi içermeyen bir çözümde Live Unit Testing başlatırsanız, **Live Unit Testing** menüsünde **duraklatma**, **durdurma**ve **sıfırlama Temizleme** seçenekleri görüntülenir, ancak Live Unit Testing başlamaz. **Çıkış** penceresinde, "Bu çözüm tarafından desteklenmeyen test bağdaştırıcılarına başvurulmuyor..." iletisi görüntülenir.

Dilediğiniz zaman, Live Unit Testing geçici olarak duraklatabilir veya tamamen durdurabilirsiniz. Bunu yapmak isteyebilirsiniz, örneğin bir yeniden düzenleme ortasındaysa ve testlerinizin bir süre için bölüneceği hakkında bilgi sahibi olun.

## <a name="view-coverage-visualization"></a>Kapsam görselleştirmesini görüntüle

Etkinleştirildikten sonra, yazmakta olduğunuz kodun birim testlerin kapsamında olup olmadığını ve bunu kapsayan testlerin geçtiğini göstermek üzere Visual Studio Düzenleyicisi 'ndeki her kod satırını güncelleştirir Live Unit Testing. Aşağıdaki görüntüde hem geçen hem de başarısız testlerin bulunduğu kod satırları ve testlerin kapsamadığı kod satırları gösterilmektedir. Yeşil "✓" ile donatılmış satırlar yalnızca testlerin geçirilerek, kırmızı bir "x" ile donatılmış satırlar bir veya daha fazla başarısız test tarafından ele alınmıştır ve mavi "➖" ile düzenlenmiş satırlar herhangi bir test tarafından kapsanmaz.

![Visual Studio 'da kod kapsamı](./media/lut-codewindow.png)

Live Unit Testing kapsam görselleştirmesi, kod düzenleyicisinde kodu değiştirirken hemen güncelleştirilir. Düzenleme işlemleri sırasında, aşağıdaki görüntüde gösterildiği gibi, yuvarlama, başarısız ve kapsanmayan sembollerin altına bir yuvarlak Zamanlayıcı görüntüsü ekleyerek, verilerin güncel olmadığını belirtmek için görselleştirme değişiklikleri.

![Zamanlayıcı simgesiyle Visual Studio 'da kod kapsamı](./media/lut-codeupdating.png)

## <a name="get-information-about-test-status"></a>Test durumu hakkında bilgi al

Kod penceresinde başarılı veya başarısız sembolün üzerine gelindiğinde, bu satıra kaç tane testin vurmasına bakabilirsiniz. Bireysel testlerin durumunu görmek için, simgesini seçin:

![Visual Studio 'da bir sembolün test durumu](./media/lut-failedinfo.png)

Araç ipucu, testlerin adlarını ve sonuçlarını sağlamanın yanı sıra testlerin kümesini yeniden çalıştırmanıza veya hata ayıklamanıza olanak tanır. Araç ipucunda bir veya daha fazla testi seçerseniz, yalnızca bu testlerin da çalıştırılmasını veya hata ayıklamasını sağlayabilirsiniz. Bu, kod penceresi olmadan testlerinizin hatalarını ayıklamanıza olanak tanır. Hata ayıklarken, önceden ayarlamış olduğunuz kesme noktalarını gözlemlemenin yanı sıra, hata ayıklayıcı beklenmeyen bir sonuç döndüren bir <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert> yöntemi yürüttüğünde program yürütme duraklatılır.

Araç ipucunda başarısız bir testin üzerine geldiğinizde, aşağıdaki görüntüde gösterildiği gibi, hata hakkında ek bilgi sağlamak için genişler. Doğrudan başarısız teste gitmek için araç ipucunda çift tıklayın.

![Visual Studio 'da başarısız test araç ipucu bilgileri](./media/lut-failedmsg.png)

Başarısız teste gittiğinizde, Live Unit Testing Yöntem imzasında görsel olarak belirtir:

- geçti (yeşil bir "✓" ile birlikte yarı dolu bir Beaker ile gösterilir)
- başarısız oldu (kırmızı "🞩" ile birlikte yarı dolu bir Beaker)
- Live Unit Testing (mavi bir "➖" ile birlikte yarı dolu bir Beaker) dahil değildir

Test dışı yöntemler bir sembol ile birlikte tasarlanmaz. Aşağıdaki görüntüde dört tür yöntem gösterilmektedir.

![Pass veya fail simgesiyle Visual Studio 'daki test yöntemleri](media/lut-testsource.png)

## <a name="diagnose-and-correct-test-failures"></a>Test başarısızlıklarını tanılama ve düzeltme

Başarısız testten, ürün kodunda kolayca hata ayıklayın, düzenleme yapabilir ve uygulamanızı geliştirmeye devam edebilirsiniz. Live Unit Testing arka planda çalıştığından, hata ayıklama, düzenleme ve devam etme sürecinde Live Unit Testing durdurup yeniden başlatmanız gerekmez.

Örneğin, önceki görüntüde gösterilen test hatası, <xref:System.Char.IsLower%2A?displayProperty=fullName> yöntemine geçirildiğinde alfabetik olmayan karakterlerin `true` döndürdüğü test yönteminde yanlış bir varsayım nedeniyle oluştu. Test yöntemini düzelttikten sonra, tüm testlerin geçmesi gerekir. Live Unit Testing duraklatıp durdurmanız gerekmez.

## <a name="test-explorer"></a>Test Gezgini

**Test Gezgini** , testleri çalıştırmanızı ve hatalarını ayıklamanızı ve test sonuçlarını çözümlemeyi sağlayan bir arabirim sağlar. Live Unit Testing, **Test Gezgini**ile tümleşir. Live Unit Testing etkinleştirilmediği veya durdurulduğunda **Test Gezgini** , bir testin son çalıştırıldığı zaman birim testlerinin durumunu görüntüler. Kaynak kodu değişiklikleri testleri yeniden çalıştırmanız gerekir. Buna karşılık Live Unit Testing etkinleştirildiğinde, **Test Gezgini** 'ndeki birim testlerinin durumu hemen güncelleştirilir. Birim testlerini açıkça çalıştırmanız gerekmez.

> [!TIP]
> En üst düzey Visual Studio menüsünden **test  > ** **Windows**  > **Test Gezgini** ' ni seçerek **Test Gezgini** 'ni açın.

**Test Gezgini** penceresinde bazı testlerin sık kullanıma hazır olduğunu fark edebilirsiniz. Örneğin, daha önce kaydedilen bir projeyi açtıktan sonra Live Unit Testing etkinleştirdiğinizde, **Test Gezgini** penceresi, aşağıdaki görüntüde gösterildiği gibi, başarısız olan teste göre daha fazla zaman aşımına uğrar. Bu durumda, Live Unit Testing başarısız testi yeniden çalıştırmıştır, ancak başarılı testleri yeniden çalıştırmaz. Bunun nedeni Live Unit Testing kalıcı verilerinin, testlerin son kez başarıyla çalıştırılmasından bu yana hiçbir değişiklik olmadığını gösterir.

![Test Gezgininde başarısız test](media/lut-test-explorer.png)

**Test Gezgini** menüsünden **Tümünü Çalıştır** veya **Çalıştır** seçeneklerini belirleyerek, beliden görüntülenen tüm testleri yeniden çalıştırabilirsiniz. Ya da **Test Gezgini** menüsünde bir veya daha fazla test seçin, sağ tıklayın ve ardından **Seçilen Testleri Çalıştır** veya açılan menüden **Seçili testlerin hatalarını ayıkla** ' yı seçin. Testler çalıştırıldığında, en üstteki kabarcılar.

Live Unit Testing otomatik olarak çalıştırma ve güncelleştirme, **Test Gezgini**'nden testleri açıkça çalıştırma arasında bazı farklılıklar vardır. Bu farklar şunlardır:

- Test Gezgini penceresinde testleri çalıştırmak veya hata ayıklamak, düzenli ikili dosyalar çalıştırlarken Live Unit Testing, işaretlenmiş ikililer çalıştırır.
- Live Unit Testing, testleri çalıştırmak için yeni bir uygulama etki alanı oluşturmaz, bunun yerine varsayılan etki alanından testleri çalıştırır. **Test Gezgini** penceresinden çalıştırılan testler yeni bir uygulama etki alanı oluşturur.
- Live Unit Testing her bir test derlemesindeki testleri sırayla çalıştırır. **Test Gezgini** penceresinde, paralel olarak birden çok test çalıştırmayı seçebilirsiniz.

## <a name="large-solutions"></a>Büyük çözümler

Çözümünüz 10 veya daha fazla proje içeriyorsa, Visual Studio şunları yaptığınızda aşağıdaki iletişim kutusunu görüntüler:

- Live Unit Testing başlatın ve kalıcı veri yok
- **Test**  > **Live Unit Testing** seçin  > **temizlemeyi Sıfırla**

![Büyük projeler için Live Unit Testing iletişim kutusu](media/lut-large-project.png)

İletişim kutusu, büyük projelerdeki çok sayıda test için dinamik yürütmenin performansı ciddi ölçüde etkileyebileceğini uyarır. **Tamam**' ı seçerseniz, Çözümdeki tüm testleri yürütür Live Unit Testing. **İptal**' i seçerseniz, yürütülecek testleri seçebilirsiniz. Aşağıdaki bölümde bunun nasıl yapılacağı açıklanmaktadır.

## <a name="include-and-exclude-test-projects-and-test-methods"></a>Test projelerini ve test yöntemlerini dahil etme ve hariç tutma

Birçok test projesi içeren çözümler için, bir projedeki hangi projelerin ve bireysel yöntemlerin Live Unit Testing katılmasını denetleyebilirsiniz. Örneğin, yüzlerce test projesi içeren bir çözümünüz varsa, Live Unit Testing katılmak için hedeflenen bir test projesi kümesi seçebilirsiniz. Proje veya Çözümdeki tüm testleri dışlamak, çoğu testi dahil etmek veya hariç tutmak veya tek testleri dışlamak istediğinize bağlı olarak bunu yapmanız için çeşitli yollar vardır. Live Unit Testing, bir Kullanıcı ayarı olarak dahil etme/hariç tutma durumunu kaydeder ve bir çözüm kapatılıp yeniden açıldığında onu anımsar.

### <a name="exclude-all-tests-in-a-project-or-solution"></a>Bir proje veya Çözümdeki tüm testleri hariç tut

Birim testlerinde ayrı projeleri seçmek için Live Unit Testing başlatıldıktan sonra aşağıdakileri yapın:

1. **Çözüm Gezgini** çözüme sağ tıklayın ve tüm**çözümün hariç tutulması Için  > ** **canlı testler** ' i seçin.
1. Testlere eklemek istediğiniz her bir test projesine sağ tıklayın ve**dahil** >  **canlı testler** ' i seçin.

### <a name="exclude-individual-tests-from-the-code-editor-window"></a>Kod Düzenleyicisi penceresinden bireysel testleri hariç tut

Bireysel test yöntemlerini dahil etmek veya hariç tutmak için kod Düzenleyicisi penceresini kullanabilirsiniz. Kod Düzenleyicisi penceresindeki test yönteminin imzasına sağ tıklayın ve sonra aşağıdaki seçeneklerden birini seçin:

- **Canlı testler**  > **içerme \<selected yöntemi >**
- **Canlı testler**  > **hariç tutma \<selected yöntemi >**
- **Canlı testler** ,**Tüm \<selected yöntemini hariç tutmak  >  >**

### <a name="exclude-tests-programmatically"></a>Testleri programlı olarak hariç tut

Yöntemleri, sınıfları veya yapıları program aracılığıyla Live Unit Testing kapsamını raporlamadan çıkarmak için <xref:System.Diagnostics.CodeAnalysis.ExcludeFromCodeCoverageAttribute> özniteliğini uygulayabilirsiniz.

Live Unit Testing bireysel yöntemleri dışlamak için aşağıdaki öznitelikleri kullanın:

- XUnit için: `[Trait("Category", "SkipWhenLiveUnitTesting")]`
- NUnit için: `[Category("SkipWhenLiveUnitTesting")]`
- MSTest için: `[TestCategory("SkipWhenLiveUnitTesting")]`

Live Unit Testing tüm testlerin bir derlemesini dışlamak için aşağıdaki öznitelikleri kullanın:

- XUnit için: `[assembly: AssemblyTrait("Category", "SkipWhenLiveUnitTesting")]`
- NUnit için: `[assembly: Category("SkipWhenLiveUnitTesting")]`
- MSTest için: `[assembly: TestCategory("SkipWhenLiveUnitTesting")]`

## <a name="see-also"></a>Ayrıca bkz.

- [Kod testi araçları](https://visualstudio.microsoft.com/vs/testing-tools/)
- [Live Unit Testing blogu](https://go.microsoft.com/fwlink/?linkid=842514)
- [Live Unit Testing SSS](live-unit-testing-faq.md)
- [Channel 9 videosu: Visual Studio 'da Live Unit Testing](https://channel9.msdn.com/Events/Visual-Studio/Visual-Studio-2017-Launch/T105)
