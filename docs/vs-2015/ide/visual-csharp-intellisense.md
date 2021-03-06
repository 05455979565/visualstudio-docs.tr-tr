---
title: Görsel C# IntelliSense | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- IntelliSense [J#]
- Visual C#, IntelliSense
- IntelliSense [C#]
ms.assetid: 79ca304d-dc1e-4dc9-a2a6-7808df2e588e
caps.latest.revision: 26
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 36803dfbba7ea6d6d2a869fb94c05105ed4af15d
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72643341"
---
# <a name="visual-c-intellisense"></a>Visual C# IntelliSense
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Visual C# IntelliSense, düzenleyicide kodlarken ve [anında mod](../ide/reference/immediate-window.md) komut penceresinde hata ayıklarken kullanılabilir.

## <a name="completion-lists"></a>Tamamlanma listeleri
 Görselde C# IntelliSense tamamlanma listeleri, liste üyelerinden belirteçler, tüm sözcüğü ve daha fazlasını içerir. Öğesine hızlı erişim sağlar:

- Bir türün veya ad alanının üyeleri,

- Değişkenler, komutlar ve işlev adları,

- [Kod parçacıkları](#CodeSnippets),

- [Dil anahtar sözcükleri](#Keywords),

- [Genişletme Yöntemleri](#ExtensionMethods)

  ' De C# tamamlanma listesi, ilgisiz belirteçleri filtreleyecek ve bağlam temelinde bir belirteci önceden seçecek kadar akıllı bir değer sağlar. Daha fazla bilgi için, içindeki [filtrelenmiş tamamlanma listelerine C# ](../misc/filtered-completion-lists-in-csharp.md) ve [üzerinde C#önceden seçilmiş tamamlanma listesi öğelerine ](../misc/pre-selected-completion-list-items-in-csharp.md)bakın.

### <a name="CodeSnippets"></a>Tamamlanma listelerindeki kod parçacıkları
 Görsel C#olarak, tamamlama listesi, önceden tanımlanmış kod gövdelerini programınıza kolayca ekleyebileceğiniz kod parçacıkları içerir. Kod parçacıkları, [öğe parçacığının kısayol öğesi (IntelliSense kod parçacıkları)](https://msdn.microsoft.com/052cc97a-5c70-42f8-b398-4c3adf670cfa)olarak tamamlanma listesinde görünür.  Görselde C# varsayılan olarak kullanılabilen kod parçacıkları hakkında daha fazla bilgi için bkz. [ C# görsel kod parçacıkları](../ide/visual-csharp-code-snippets.md).

### <a name="Keywords"></a>Tamamlanma listelerinde dil anahtar sözcükleri
 Görselde C#, tamamlanma listesi dil anahtar sözcüklerini de içerir. Dil anahtar sözcükleri hakkında C# daha fazla bilgi için bkz [ C# . anahtar sözcükler](https://msdn.microsoft.com/library/e929b0f2-4b92-4d37-8060-23d323b098ad).

### <a name="ExtensionMethods"></a>Tamamlanma listelerindeki genişletme yöntemleri
 Görselde C#, tamamlanma listesi kapsamdaki genişletme yöntemlerini içerir.

> [!NOTE]
> Tamamlanma listesi <xref:System.String> nesneleri için tüm genişletme yöntemlerini görüntülemez.

 Uzantı yöntemleri örnek metotlardan farklı bir simge kullanır. Liste simgelerinin listesi için bkz. [sınıf görünümü ve nesne tarayıcısı simgeleri](../ide/class-view-and-object-browser-icons.md). Aynı ada sahip bir örnek yöntemi ve genişletme yöntemi her ikisi de kapsam içinde olduğunda, tamamlanma listesi uzantı yöntemi simgesini görüntüler.

### <a name="filtered-completion-lists"></a>Filtrelenmiş tamamlanma listeleri
 IntelliSense, filtre kullanarak gereksiz üyeleri tamamlama listesinden kaldırır.

 Görsel C# , bu öğeler için görüntülenen tamamlanma listelerine filtre uygular:

- **Arabirimler ve temel sınıflar.** IntelliSense, hem sınıf bildirimi tabanında hem de arabirim listelerinde ve kısıtlama listelerinde, arabirim ve temel sınıf tamamlama listelerinden öğeleri otomatik olarak kaldırır. Örneğin, numaralandırmalar taban sınıflar için kullanılamadığından numaralandırmalar, temel sınıfların tamamlanma listesinde görünmez. Temel sınıfların tamamlanma listesi yalnızca arabirimler ve ad alanları içerir. Listeden bir öğe seçer ve bir virgül yazarsanız, görsel C# birden çok devralmayı desteklemediğinden, IntelliSense, tamamlama listesinden temel sınıfları kaldırır. Aynı davranış de kısıtlama yan tümceleri için oluşur.

- **Öznitelikler**: bir türe bir öznitelik uyguladığınızda, listenin yalnızca bu türleri içeren ad alanlarından (<xref:System.Attribute> gibi) ilgili türleri içermesi için tamamlama listesi filtrelenir.

- `as` ve `is` işleçleri.

- **Catch yan tümceleri.**

- **Nesne başlatıcıları:** Yalnızca başlatılmış Üyeler tamamlama listesinde görünür.

- **Yeni anahtar sözcük**: `new` yazdığınızda ve sonra ara çubuğuna bastığınızda bir tamamlama listesi görüntülenir. Kodunuzda bağlam temelinde, listede otomatik olarak bir öğe seçilir. Örneğin, öğeler için tamamlama listesinde ve metotlarda Return deyimlerinin öğeleri otomatik olarak seçilir.

- **as ve, işleçleri:** @No__t_1 veya `is` anahtar sözcüğünü yazdıktan sonra ara çubuğuna bastığınızda filtrelenmiş bir tamamlanma listesi otomatik olarak görüntülenir.

- Olaylar: `event` anahtar sözcüğünü yazdığınızda, tamamlanma listesi yalnızca temsilci türlerini içerir.

- Parametre yardımı, parametreleri girdiğiniz parametrelerle eşleşen ilk yöntem aşırı yüklemesini otomatik olarak sıralar. Birden çok yöntem aşırı yüklemesi varsa, listede bir sonraki olası aşırı yüklemeye gitmek için yukarı ve aşağı okları kullanabilirsiniz.

## <a name="most-recently-used-members"></a>En son kullanılan Üyeler
 IntelliSense, otomatik nesne adı tamamlamada açılan [liste üyeleri](../ide/using-intellisense.md) kutusunda en son seçtiğiniz üyeleri anımsar. Üye listesini bir dahaki sefer kullandığınızda en son kullanılan Üyeler en üstte gösterilir. En son kullanılan üyelerin geçmişi, IDE içindeki her oturum arasında temizlenir.

## <a name="override"></a>override
 [Geçersiz kılma](https://msdn.microsoft.com/library/dd1907a8-acf8-46d3-80b9-c2ca4febada8) yazın ve ardından boşluk tuşuna bastığınızda IntelliSense, bir açılır liste kutusunda geçersiz kılabileceğiniz geçerli temel sınıf üyelerini görüntüler. @No__t_0 sonra yöntemin dönüş türünü yazmak, IntelliSense 'in yalnızca aynı türü döndüren yöntemleri göstermesini ister. IntelliSense herhangi bir eşleşme bulamadığınızda, tüm temel sınıf üyelerini görüntüler.

## <a name="automatic-code-generation"></a>Otomatik Kod Üretimi

### <a name="add-using"></a>using Ekle
 IntelliSense kullanarak ekleme işlemi, odağınızı kodun başka bir bölümüne kaydırabilmeniz yerine, yazmakta olduğunuz koda odaklanmanızı sağlar.

 Using using işlemini başlatmak için imleci çözümlenemeyen bir tür başvurusu üzerine konumlandırın. Örneğin, bir konsol uygulaması oluşturup `Main` yönteminin gövdesine `XmlTextReader` eklediğinizde, çözülemeyen bir tür başvurusu olarak göründüğünden `XmlTextReader` en sağdaki karakter altında akıllı bir etiket görüntülenir.

 ![Akıllı Etiket görüntüsünü kullanarak ekleme](../ide/media/addusesmart.gif "AddUseSmart")

 Daha sonra, **IntelliSense** menüsünün veya bağlam menüsünün **Çözümle** alt menüsünden seçerek Ekle ' yi çağırabilir veya akıllı etiket aracılığıyla kullanarak Ekle ' yi çağırarak çalıştırabilirsiniz. Akıllı etiket yalnızca imleç açık veya ilişkisiz tür olarak konumlandırıldığında görünür.

 ![Using, akıllı etiket genişletilmiş görüntüsünü kullanarak ekleme](../ide/media/addusesmartexp.gif "AddUseSmartExp")

### <a name="organize-usings"></a>Using deyimlerini Düzenle
 **Düzenleme** kullanımları seçenekleri, kaynak kodun davranışını değiştirmeden `using` ve `extern` bildirimlerini sıralar ve kaldırır. Zaman içinde, kaynak dosyalar gereksiz ve düzensiz `using` yönergeleri nedeniyle okunabilir ve okunabilir hale gelebilir. Kullanılmayan `using` yönergelerini kaldırarak ve bunları sıralayarak okunabilirliği geliştirerek, **using using** , kaynak kodu düzenleme özelliklerini geliştirir.

 Visual Studio IDE 'deki kullanılabilir seçenekleri görmek için, **Düzenle** menüsünde, **IntelliSense**' in üzerine gelin ve ardından kullanımları **Düzenle**' ye gelin. IDE `usings` yönergeleri düzenlemek ve kaldırmak için aşağıdaki seçenekleri sağlar:

### <a name="implement-interface"></a>Arabirimi Uygulama
 IntelliSense, kod Düzenleyicisi 'nde çalışırken bir [arabirimi](https://msdn.microsoft.com/library/7da38e81-4f99-4bc5-b07d-c986b687eeba) uygulamanıza yardımcı olacak bir seçenek sunar. Normalde, bir arabirimi düzgün bir şekilde uygulamak için sınıfınıza arabirimin her üyesi için bir yöntem bildirimi oluşturmanız gerekir. IntelliSense kullanarak bir sınıf bildiriminde bir arabirimin adını yazdıktan sonra akıllı bir etiket görüntülenir. Akıllı etiket, açık veya örtük adlandırma kullanarak arabirimi otomatik olarak uygulama seçeneği sunar. Açık adlandırma altında yöntem bildirimleri arabirimin adını taşır; örtük adlandırma altında yöntem bildirimleri ait oldukları arabirimi göstermez. Açıkça adlandırılmış bir arabirim yöntemine, bir sınıf örneği aracılığıyla değil, yalnızca bir arabirim örneği üzerinden erişilebilir. Daha fazla bilgi için bkz. [Açık arabirim uygulama](https://msdn.microsoft.com/library/181c901f-0d4c-4f29-97fc-895079617bf2).

 Arabirim Uygula, arabirimi karşılamak için gerekli olan en az Yöntem saplamaları sayısını oluşturacaktır. Bir temel sınıf arabirimin parçalarını uygularsa, bu saplamalar yeniden oluşturulmaz.

### <a name="implement-abstract-base-class"></a>Soyut temel sınıf Uygula
 IntelliSense, kod Düzenleyicisi 'nde çalışırken soyut bir temel sınıfın üyelerini otomatik olarak uygulamanıza yardımcı olacak bir seçenek sunar. Normalde, soyut bir temel sınıfın üyelerini uygulamak için, türetilmiş sınıfınızdaki soyut temel sınıfın her bir yöntemi için yeni bir yöntem tanımı oluşturulmasını gerektirir. IntelliSense kullanarak bir sınıf bildiriminde soyut bir temel sınıfın adını yazdıktan sonra akıllı bir etiket görüntülenir. Akıllı etiket, temel sınıf yöntemlerini otomatik olarak uygulama seçeneği sunar.

 Soyut temel sınıf Uygula özelliği tarafından oluşturulan Yöntem saplamaları, MethodStub. parçacığında dosyasında tanımlanan kod parçacığına göre modellenir. Kod parçacıkları değiştirilebilir. Daha fazla bilgi için bkz. [Izlenecek yol: kod parçacığı oluşturma](../ide/walkthrough-creating-a-code-snippet.md).

### <a name="generate-from-usage"></a>Kullanımdan oluştur
 **Kullanımdan oluştur** özelliği, sınıfları ve üyeleri tanımladıktan önce kullanmanıza olanak sağlar. Kullanmak istediğiniz ancak henüz tanımlamamış herhangi bir sınıf, Oluşturucu, yöntem, özellik, alan veya Enum için bir saplama oluşturabilirsiniz. Geçerli konumunuzu kodda bırakmadan yeni türler ve Üyeler oluşturabilirsiniz. Bu, iş akışınız için kesintiye en aza indirir.

 Her tanımsız tanımlayıcı altında dalgalı alt çizgi görünür. Fare işaretçisini tanımlayıcıda bıraktığınızda, araç ipucunda bir hata iletisi görüntülenir.

 Uygun seçenekleri göstermek için aşağıdaki yordamlardan birini kullanabilirsiniz:

- Tanımsız tanımlayıcıya tıklayın. En soldaki karakter altında kısa bir alt çizgi görünür. Fare işaretçisini kısa alt çizginin üzerinde bekletin ve akıllı bir etiket (simge) görünür. Akıllı etikete tıklayın.

- Tanımsız tanımlayıcıya tıklayın ve ardından CTRL + tuşlarına basın. (nokta).

- Tanımsız tanımlayıcıya sağ tıklayın ve ardından **Oluştur**' a tıklayın.

  Görüntülenen seçenekler şunları içerebilir:

- **Özellik saplaması oluştur**

- **Alan saplaması oluştur**

- **Yöntem saplaması oluştur**

- **Sınıf üret**

- **Yeni tür oluşturma** (bir sınıf, yapı, arabirim veya sabit listesi için)

## <a name="generate-event-handlers"></a>Olay işleyicileri oluştur
 IntelliSense, kod Düzenleyicisi 'nde Yöntemler (olay işleyicileri) ile olay alanlarını almanıza yardımcı olabilir.

 Bir. cs dosyasındaki bir olay alanından sonra `+=` işlecini yazdığınızda, IntelliSense, sekme tuşuna basarak bu seçeneği girmenizi ister. Bu, olayı işleme yöntemine işaret eden bir temsilcinin yeni bir örneğini ekler.

 ![Düğme otomatik kancası](../ide/media/vxautohookup.gif "Vxoto")

 Sekme tuşuna basarsanız, IntelliSense sizin için ifadeyi otomatik olarak tamamlar ve olay işleyicisi başvurusunu kod düzenleyicisinde seçili metin olarak görüntüler. Otomatik olay kancaini tamamlayabilmeniz için, IntelliSense, olay işleyicisi için boş bir saplama oluşturmak üzere TAB tuşuna tekrar basmanız istenir.

 ![Olay Işleyicisi oluştur](../ide/media/vxgenerateeventhandler.gif "vxGenerateEventHandler")

> [!NOTE]
> IntelliSense tarafından oluşturulan yeni bir temsilci var olan bir olay işleyicisine başvuruyorsa, IntelliSense bu bilgileri araç ipucunda iletişim kurar. Bu başvuruyu daha sonra değiştirebilirsiniz; metin, kod düzenleyicisinde zaten seçilidir. Aksi takdirde, bu noktada otomatik olay kancau tamamlanmıştır.

 Sekme tuşuna basarsanız, IntelliSense doğru imzaya sahip bir yöntemi dışarı yerleştirir ve imleci olay işleyicinizin gövdesine koyar.

> [!NOTE]
> Olay kancası bildirimine geri dönmek için **Görünüm** menüsündeki **geri GIT** komutunu (Ctrl +-) kullanın.

 Aşağıdaki görev, IntelliSense 'in `button1.Click` adlı bir olay alanına `button1_Click` adlı bir olay işleyicisini otomatik olarak nasıl yedeklegösterdiğini gösterir.

## <a name="see-also"></a>Ayrıca Bkz.
 [Visual Studio IDE](../ide/visual-studio-ide.md)
