---
title: Çağrı ağacı görünümü | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.view.calltree
helpviewer_keywords:
- Call Tree view
- profiling tools reports, Call Tree view
- performance reports, Call Tree view
- profiling tools, Call Tree view
ms.assetid: b2dbc033-bf95-4d10-8e51-f9462979133e
caps.latest.revision: 39
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 105f16c0d9deb8d94a102818c5335af18685c675
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "63439327"
---
# <a name="call-tree-view"></a>Çağrı Ağacı Görünümü
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Çağrı ağacı görünümü, profili oluşturulan uygulamada geçiş işlev yürütme yollarını görüntüler. Ağacının kökü, uygulama veya bileşen giriş noktasıdır. Her işlev düğümü, çağrılan işlevlerin ve bu işlev çağrıları ile ilgili performans verilerini listeler.  
  
 Çağrı ağacı görünümü ayrıca genişletin ve en çok zaman harcanan veya sık örneklenen bir işlev yürütme yolunu vurgulayın. Yolun en pahalı performans görüntülemek için işlev sağ tıklayın ve ardından **etkin yolu Genişlet**.  
  
 Profil oluşturma çalıştırmasını her işlem, bir kök düğümü olarak görüntülenir. Çağrı ağacı görünümü başlangıç düğümü başlangıç düğümü olarak ayarlamak istediğiniz düğüme sağ tıklayın ve ardından seçerek ayarlayabilirsiniz **kümesi kök**.  
  
 Kök düğümü ayarladığınızda, Seçili düğümün alt ağacı dışında görünümünden diğer tüm girişleri kaldırın. Görüntülemekte olduğunuz düğüme geri kök düğümü sıfırlayabilirsiniz. Çağrı ağacı Görünümü penceresi sağ tıklayın ve ardından **sıfırlama kök**.  
  
 Çağrı ağacı görünümü sütun ekleme veya kaldırma için özelleştirilebilir. Sağ **sütun adı başlık çubuğu**ve ardından **sütunları Ekle/Kaldır**.  
  
 Çağrı ağacı görünümü sunulan veri miktarını sınırlamak için gürültü azaltma yapılandırılabilir. Gürültü azaltma kullanarak performans sorunlarını Görünümü'nde daha belirgin. Performans sorunlarını kolayca ayırt etmek için analiz daha kolay olur. Daha fazla bilgi için [nasıl yapılır: Rapor görünümlerinde gürültü azaltmayı yapılandırma](../profiling/how-to-configure-noise-reduction-in-report-views.md).  
  
> [!NOTE]
> Gürültü azaltma etkinleştirildiğinde, bir uyarı görüntüleyecek şekilde yapılandırılması durumunda rapora bir bilgi çubuğu görüntülenir.  
  
 Çağrı ağacı görünümü içinde sütunların tanımları hakkında daha fazla bilgi için aşağıdakilere bakın:  
  
 [Çağrı Ağacı Görünümü](../profiling/call-tree-view-sampling-data.md)  
  
 [Çağrı Ağacı Görünümü](../profiling/call-tree-view-instrumentation-data.md)  
  
 [Çağrı Ağacı Görünümü - Örnekleme](../profiling/call-tree-view-dotnet-memory-sampling-data.md)  
  
 [Çağrı Ağacı Görünümü](../profiling/call-tree-view-contention-data.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Performans raporu görünümleri](../profiling/performance-report-views.md)   
 [İzleme veri değerlerini anlama](../profiling/understanding-instrumentation-data-values.md)   
 [Örnekleme Veri Değerlerini Anlama](../profiling/understanding-sampling-data-values.md)
