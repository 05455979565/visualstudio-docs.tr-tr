---
title: 'Nasıl yapılır: paralel İzleme penceresini kullanma | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug.parallelwatch
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- debugger, parallel watch window
ms.assetid: 28004d9b-420c-48f7-b80e-ab1519802558
caps.latest.revision: 19
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 88c4efe15e2afd3f4158b93cf8701109cd3902b8
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42693886"
---
# <a name="how-to-use-the-parallel-watch-window"></a>Nasıl Yapılır: Paralel İzleme Penceresini Kullanma
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [değişkenleri iş parçacıklarında paralel bir izleme ayarını](https://docs.microsoft.com/visualstudio/debugger/how-to-use-the-parallel-watch-window).  
  
Paralel İzleme penceresinde aynı anda birden çok iş parçacığında bir ifade tutan değerleri görüntüleyebilirsiniz. Her satır bir uygulama içinde çalışan bir iş parçacığını temsil eder, ancak bir iş parçacığı içinde birden çok satır gösterilebilir. Daha açık belirtmek gerekirse her satır, işlev imzası geçerli yığın çerçevesinde işlevi eşleşen bir işlev çağrısını temsil eder. Sıralama, yeniden sıralama, kaldırmak ve sütunları olan öğeleri gruplayın. Bayrak, işaretsiz dondurma, (askıya) ve (devam) iş parçacıklarını çözme. Aşağıdaki sütunlar görüntülenir **paralel izleme** penceresi:  
  
-   Özel dikkat edilmesi gereken istediğiniz bir iş parçacığını işaretle Bayrak sütunu.  
  
-   Çerçeve sütunu bir ok Seçilen çerçevenin gösterir.  
  
-   Makine, işlem, döşeme, görev ve iş parçacığı görüntüleyebilirsiniz yapılandırılabilir bir sütun.  
  
    > [!TIP]
    >  Açmalısınız **paralel görev** görev bilgileri görüntülemek için pencere **paralel izleme** penceresi.  
  
-   **\<Gözcü Ekle >** izlemek için ifadeleri, girebileceğiniz sütunu.  
  
 [!INCLUDE[note_settings_general](../includes/note-settings-general-md.md)]  
  
### <a name="to-display-the-parallel-watch-window"></a>Paralel İzleme penceresini görüntülemek için  
  
1.  Kodda bir kesme noktası ayarlayın.  
  
2.  Menü çubuğunda, **hata ayıklama**, **hata ayıklamayı Başlat**. Uygulama kesme noktasına ulaşmak bekler.  
  
3.  Menü çubuğunda, **hata ayıklama**, **Windows**, **paralel izleme**, Gözcü penceresi seçin. Dört adede kadar windows açabilirsiniz.  
  
### <a name="to-add-a-watch-expression"></a>Bir Gözcü ifadesini eklemek için  
  
-   Seçin  **\<Gözcü Ekle >** ve ardından bir Gözcü ifadesini belirtin.  
  
### <a name="to-flag-or-unflag-a-thread"></a>Bir iş parçacığını işaretleme veya işaretini kaldırma için  
  
-   Satır için bayrak sütunu seçin veya iş parçacığı için kısayol menüsünü açın ve seçin **bayrağı** veya **Unflag**.  
  
### <a name="to-display-only-flagged-threads"></a>Yalnızca bayraklı iş parçacıklarını görüntülemek için  
  
-   Sadece bayrak eklenmiş Göster düğmesini seçin sol üst köşesinde **paralel izleme** penceresi.  
  
### <a name="to-switch-frames"></a>Çerçeve geçiş yapmak için  
  
-   Çerçeve sütunu çift tıklayın. (Klavye: satırı seçin ve Enter tuşuna basın.)  
  
### <a name="to-sort-a-column"></a>Bir sütunu sıralamak için  
  
-   Sütun başlığı seçin.  
  
### <a name="to-group-threads"></a>İş parçacıklarını gruplandırma  
  
-   Paralel İzleme penceresi kısayol menüsünü açın, **Group By**ve ardından uygun alt öğeyi seçin.  
  
### <a name="to-freeze-or-thaw-threads"></a>Dondurma veya çözme iş parçacığı  
  
-   Satır için kısayol menüsünü açın ve seçin **dondurma** veya **çözme**.  
  
### <a name="to-export-the-data-in-the-parallel-watch-window"></a>Paralel İzleme penceresinde verileri dışarı aktarmak için  
  
-   Seçin **Excel'de Aç** düğmesine ve ardından **Excel'de Aç** veya **CSV'ye aktar**.  
  
### <a name="to-filter-by-a-boolean-expression"></a>Bir Boole ifadesine göre filtre uygulamak için  
  
-   Bir Boole ifadesi girin **Boole ifadesine göre filtrele** kutusu. Hata ayıklayıcı, her iş parçacığı bağlamı için ifadeyi hesaplar. Değeri satır `true` görüntülenir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çok iş parçacıklı uygulamalarda hata ayıklama](../debugger/debug-multithreaded-applications-in-visual-studio.md)   
 [Nasıl yapılır: GPU iş parçacıkları penceresini kullanma](../debugger/how-to-use-the-gpu-threads-window.md)   
 [İzlenecek yol: C++ AMP Uygulamasında Hata Ayıklama](http://msdn.microsoft.com/library/40e92ecc-f6ba-411c-960c-b3047b854fb5)



