---
title: 'İzlenecek yol: Grafik bilgilerini yakalama | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
ms.assetid: 48f12f6e-57b4-48ec-a145-89fa71a42424
caps.latest.revision: 22
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 9ebd0453347084d1662c6bc7837fc1e96f498fbd
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "68151465"
---
# <a name="walkthrough-capturing-graphics-information"></a>İzlenecek yol: Grafik Bilgilerini Yakalama
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu izlenecek yolda nasıl kullanılacağını gösterir [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] el ile bir Direct3D uygulamadan grafik bilgilerini yakalamak için grafik tanılama.  
  
 Bu örneklerde bu görevler gösterilir:  
  
- Grafik tanılama uygulamanıza takma  
  
- Graf bilgilerini yakalama  
  
## <a name="capturing-graphics-information"></a>Graf bilgilerini yakalama  
 Grafik tanılama araçlarını kullanmak için öncelikle kullanır grafik bilgilerini yakalama olması. Yakalama özelliğini etkinleştirmek için kullanın **tanılamayı Başlat** başladığında uygulamanızı grafik tanılama yeteneklerinizi komutu.  
  
#### <a name="to-enable-the-capture-of-graphics-information-after-a-project-or-solution-is-loaded"></a>Bir proje veya çözüm sonra grafik bilgilerini yakalama etkinleştirmek için yüklenir  
  
1. İçinde [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], grafik bilgilerini yakalamak istediğiniz uygulama için bir proje veya çözüm dosya yükleyin.  
  
2. Grafik tanılama araç çubuğunda **tanılamayı Başlat**.  
  
#### <a name="to-enable-the-capture-of-graphics-information-without-loading-a-project-or-solution"></a>Bir proje veya çözüm yüklemeden grafik bilgilerini yakalamayı etkinleştirme  
  
1. Menü çubuğunda, **dosya**, **açık**, **proje/çözüm**. **Açık proje** iletişim kutusu görüntülenir.  
  
2. Yürütülebilir dosya, grafik bilgilerini yakalamak ve ardından istediğiniz uygulama için bir proje veya çözüm dosyası yerine belirtin **açık**.  
  
3. Menü çubuğunda, **hata ayıklama**, **grafik**, **tanılamayı Başlat**.  
  
   Uygulamayı başlatın ve işleme çerçeveler olduktan sonra grafik bilgilerini yakalayabilir.  
  
#### <a name="to-capture-graphics-information"></a>Grafik bilgilerini yakalamak için  
  
- Grafik tanılama araç çubuğunda **yakalama** düğmesi. ![Grafik yakalama düğmesinin simgesi](../debugger/media/debuggingdirectxgraphics.png "DebuggingDirectXGraphics")  
  
   -veya-  
  
   Odak uygulamayla basın **Print Screen**.  
  
  Her zaman bir kare hakkında bilgi yakalama grafik tanılama Direct3D olayları ve ilişkili durumu kaydeder ve bu verileri bir grafik günlüğüne ekler. Yeni bir grafik günlüğü, her bir grafik Tanılama oturumu için oluşturulur. Grafik günlükleri hakkında daha fazla bilgi için bkz: [genel bakış](../debugger/overview-of-visual-studio-graphics-diagnostics.md).  
  
## <a name="next-steps"></a>Sonraki Adımlar  
 Bu izlenecek yol, grafik bilgilerini elle yakalama gösterilmiştir. Sonraki adım olarak, bu seçenek göz önünde bulundurun:  
  
- Grafik tanılama araçlarını kullanarak yakalanan grafik bilgileri analiz etmeyi öğrenin. Bkz: [genel bakış](../debugger/overview-of-visual-studio-graphics-diagnostics.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Grafik Bilgilerini Yakalama](../debugger/capturing-graphics-information.md)
