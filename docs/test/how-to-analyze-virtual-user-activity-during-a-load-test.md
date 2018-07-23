---
title: Visual Studio'da yük testleri için sanal kullanıcı etkinliğini çözümleme
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- virtual user activity chart, viewing
ms.assetid: 8bda19b3-91c1-4daf-b6c7-09108bddadff
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 20367c2632e62d53199ee7bc1a522b81b570070e
ms.sourcegitcommit: 5b767247b3d819a99deb0dbce729a0562b9654ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/20/2018
ms.locfileid: "39178511"
---
# <a name="how-to-analyze-what-virtual-users-are-doing-during-a-load-test-using-the-virtual-user-activity-chart"></a>Nasıl yapılır: Sanal Kullanıcı Etkinlik Grafiğini Kullanarak Bir Yük Testi Sırasında Sanal Kullanıcıların Ne Yaptıklarını Çözümleme

Sanal kullanıcı aktivite Grafiği'ni kullanarak yük testi ile ilişkili sanal kullanıcı etkinliğini görüntüleyin. Grafikteki her satırın tek bir sanal kullanıcı temsil eder. Sanal kullanıcı aktivite grafiği, tam olarak neyin test sırasında her sanal kullanıcı yürütülmüş gösterir. Kullanıcı Etkinlik düzenlerini görebilir, yük düzenleri, yavaş veya başarısız testleri ilişkilendirin ve diğer sanal kullanıcı etkinliğini isteklerle bakın. Sanal kullanıcı aktivite grafiği, yalnızca yük testi çalışması bittikten sonra kullanılabilir.

Aşağıdaki yordamlar, sanal kullanıcı aktivite grafiği görüntüleme, nasıl belirli kullanıcının etkinliğini araştırın ve filtrelemenin nasıl kullanılacağını göstermektedir.

## <a name="to-view-the-virtual-user-activity-chart-in-your-load-test-results"></a>Yük testi sonuçlarınızda Sanal kullanıcı aktivite grafiği görüntülemek için

1.  Sanal kullanıcı verilerini görüntülemek için öncelikle yapılandırmalısınız **Tüm Bireysel Ayrıntılar** ayarını **Zamanlama Ayrıntıları Deposu** yük testi ile ilişkili olan özellik. Daha sonra Yük testi çalıştırın. Daha fazla bilgi için [nasıl yapılır: yapılandırma toplama sanal kullanıcı etkinlik grafiğini etkinleştirmek için Ayrıntılar](../test/how-to-configure-load-tests-to-collect-full-details.md).

2.  Sonra Yük test çalıştırmaları, test sonuçları Özet sayfasında görüntülenir. Seçin **kullanıcı ayrıntı** araç çubuğunda.

     veya

     Grafik görünümü seçerek açın **grafikleri** araç çubuğunda. Grafiği sağ tıklayın ve ardından **kullanıcı ayrıntılarına Git**.

     Bu seçeneği kullanırsanız, sanal kullanıcı aktivite grafiği otomatik sağ tıkladığınız testin bir parçası yakınlaştırma. İşaretçinizi üzerinde yaklaşık 30 ikinci işareti bulunuyorsa, örneğin, ayrıntı görünümü yaklaşık 30 ikinci işaretleme üzerinde görüntüler **zaman dönemini Yakınlaştır** sanal kullanıcı aktivite grafiği alt kısmındaki araç.

     Ardından, kullanabileceğiniz sanal kullanıcı aktivite grafiği, belirli kullanıcılar bir etkinlik ayrıntıları inceleyin.

## <a name="to-investigate-a-specific-users-activity-in-the-virtual-user-activity-chart"></a>Sanal kullanıcı aktivite grafiği belirli kullanıcılar etkinliğinde incelemek için

1.  Zaman dönemi aracına yakınlaştırma sanal kullanıcı aktivite grafiği alt kısmında, belirli bir kullanıcı ayrıntılarını araştırmak istediğiniz grafikteki bir alan seçmek için kullanın.

2.  Graftaki bir ayrıntı üzerinde gezdirin. Aşağıdaki bilgiler, araç ipucunda görüntülendiğini görürsünüz:

    -   **Kullanıcı Kimliği**

    -   **Senaryo**

    -   **Test**

    -   **URL** (bir test veya işlem göstermez)

    -   **Sonucu**

    -   **Tarayıcı** (bir test veya işlem göstermez)

    -   **Ağ**

    -   **Başlangıç saati**

    -   **Süresi**

    -   **Aracı**

    -   **Test günlüğü** (test günlüğü bağlantı)

        > [!NOTE]
        > Test günlüğü bağlantısını seçerseniz, uygulamanızın hata ayıklamaya yardımcı olmak için web testi sonucu veya birim testi sonucu günlükle ilişkilendirilmiş açılır.

     Ardından, sanal kullanıcı aktivite grafiği filtreleme ve vurgulama işlemleri kullanabilirsiniz.

## <a name="to-use-filtering-options-in-the-virtual-user-activity-chart"></a>Sanal kullanıcı aktivite grafiği filtreleme seçeneklerini kullanmak için

1.  Ayrıntıları göstergede ya da seçmek için açılan listeyi kullanın. **Test**, **sayfa**, veya **işlem**.

     **Ayrıntı göstergesi panel**

     ![Ayrıntı göstergesi panel](../test/media/ltest_detailslegend.png)

2.  Hatalar, günlükleri, test, arama ve yük testi ile ilişkili aspx sayfaları için onay kutularının işaretini kaldırın veya seçin.

     Sanal kullanıcı aktivite grafiği uygun şekilde güncelleştirir.

     Sanal kullanıcı aktivite grafiği testler, sayfalar ve işlemleri birkaç farklı ölçütlere göre filtreleme olanağı sağlar. Görünümden belirli testleri kaldırın veya tüm başarılı testleri kaldırın veya bazı hatalarla başarısız testleri Kaldır. Ayrıca, günlükleri olmayan tüm testleri de kaldırabilirsiniz.

     Örneğin, seçebileceğiniz **(hataları vurgula)** Sepeti tüm hataları görüntüler seçeneği, kırmızı renkli. Belirleyebilirsiniz **(Günlüklü sonuçları vurgula)** grafikteki yeşil renkli günlükleri olan tüm test sonuçlarını görüntüleyen seçeneği.

     **Sonuçlar paneli Filtrele**

     ![Sonuçlar paneli Filtrele](../test/media/ltest_filterresults.png)

3.  Filtre sonuçlarını seçin veya aşağıdaki filtre seçenekleri için onay kutularını temizleyin:

    -   **Yalnızca Günlüklü sonuçları göster** yalnızca test test günlüklerinin ilişkili olan sonuçları görüntüler.

    -   **Başarılı sonuçları göster** başarılı sonuçları görüntüler.

    -   **Hatalı sonuçları göster** hata ayıklamaya yardımcı olabilecek hatalı sonuçları görüntüler.

        > [!NOTE]
        > Altında listelenen hata türleri listesi **hatalı sonuçları göster** düğüm daha fazla araştırılması tablolar düğmesi seçerek **Web Performans Test Sonuçları Görüntüleyicisi** araç çubuğu. Daha fazla bilgi için [yük testi sonuçlarını çözümleme ve hataları Tablo görünümünde](../test/analyze-load-test-results-and-errors-in-the-tables-view.md).

     Sanal kullanıcı aktivite grafiği uygun şekilde güncelleştirir.

## <a name="see-also"></a>Ayrıca bkz.

- [Ayrıntılar görünümünde sanal kullanıcı etkinliğini çözümleme](../test/analyze-load-test-virtual-user-activity-in-the-details-view.md)
- [İzlenecek yol: sorunları yalıtmak için sanal kullanıcı etkinlik grafiğini kullanma](../test/walkthrough-use-the-virtual-user-activity-chart-to-isolate-issues.md)