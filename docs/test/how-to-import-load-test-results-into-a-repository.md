---
title: "Nasıl yapılır: Visual Studio'da bir depoda yük testi sonuçları içeri aktarma"
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- results, load test
- load test results, importing
- Load Test Results Repository
- load tests, importing results
ms.assetid: a955b3d2-c8ad-40dd-8ea3-9f1a271e1eed
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 42336bcbded19343651eeff3b18a7f4a52c96fbe
ms.sourcegitcommit: 495bba1d8029646653f99ad20df2f80faad8d58b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/31/2018
ms.locfileid: "39382255"
---
# <a name="how-to-import-load-test-results-into-a-repository"></a>Nasıl yapılır: bir depoda alma yük testi sonuçları

Çalıştırma sırasında toplanan bilgileri, bir yük testi çalıştırdığınızda, yük testi sonuçları deposunda depolanır. Yük testi sonuçları deposu, performans sayacı verileri ve hatalar hakkında bilgi içerir. Daha fazla bilgi için [Yönet yük testi sonuçları yük testi sonuçları deposunda](../test/manage-load-test-results-in-the-load-test-results-repository.md).

 Kullanarak yük testi sonuçları Yük Testi Düzenleyicisi'nden yönetebilirsiniz **açık ve yük testi sonuçlarını yönetme** iletişim kutusu. Açın, içeri aktarma, dışarı aktarma ve yük testi sonuçları kaldırın.

## <a name="to-import-results-into-a-repository"></a>Sonuçları bir depoya içeri aktarmak için

1.  Bir web performansı ve yük testi projesinden, bir yük testi açın.

2.  Gömülü araç çubuğunda **sonuçları Aç ve Yönet**.

     **Yönetme yük testi sonuçlarını Aç ve** iletişim kutusu görüntülenir.

3.  İçinde **yük testi sonuçlarını bulmak için bir denetleyici adı girin**, bir denetleyici seçin. Seçin  **\<yerel >** yerel olarak depolanmış sonuçlara erişmek için.

     Yük testi sonuçları yoksa görünürler **yük testi sonuçları** listesi. Sütunların **zaman**, **süresi**, **kullanıcı**, **sonucu**, **Test**, ve  **Açıklama**. **Test** test adını içerir ve **açıklama** test çalıştırılmadan önce eklenir isteğe bağlı bir açıklama içerir.

4.  Seçin **alma**.

     **Alma yük testi sonuçları** iletişim kutusu görüntülenir.

5.  İçinde **dosya adı** kutusuna arşivlenmiş test sonuç dosyasının adını yazın ve ardından **açık**.

     \- veya -

     Dosyaya gidin ve ardından **açık**.

    > [!NOTE]
    > Bu adımda belirttiğiniz bir arşivlenen test sonuçları dosyasını dışarı aktarma işlemi gerçekleştirerek oluşturulmuş olması gerekir.

     Sonuçları içeri aktarılır ve görünür **yük testi sonuçları** listesi.

## <a name="see-also"></a>Ayrıca bkz.

- [Yük testi sonuçları deposu içindeki yük testi sonuçlarını yönetme](../test/manage-load-test-results-in-the-load-test-results-repository.md)
- [Yük testi sonuçlarını çözümleme](../test/analyze-load-test-results-using-the-load-test-analyzer.md)
- [Nasıl yapılır: bir depodan dışarı aktarma yük testi sonuçları](../test/how-to-export-load-test-results-from-a-repository.md)