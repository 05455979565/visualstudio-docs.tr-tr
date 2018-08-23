---
title: İşlem görünümü - çakışma verileri | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Process view
ms.assetid: 8821d98c-0771-43b2-a38b-e9039a3abd75
caps.latest.revision: 16
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 411de842beb616cf4ed7c51d0458e8d7bce82690
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42687863"
---
# <a name="process-view---contention-data"></a>İşlem Görünümü - Çakışma Verileri
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [işlem görünümü - çakışma verileri](https://docs.microsoft.com/visualstudio/profiling/process-view-contention-data).  
  
İşlem görünümü işlemleri ve profil oluşturma çalışması sırasında yürütülen iş parçacığı için Çekişme verilerini görüntüler.  
  
 Semboller kullanılabilir olduğunda işlemler adına göre listelenmiştir. Simgeleri kullanılabilir durumda değilse, işlemleri kendi bellek adresi onaltılık biçiminde listelenir. İş parçacıkları, onları oluşturan işlemin alt öğesi olarak listelenir.  
  
 İşlem görünümü tablodaki sütun değerleri aşağıdaki tabloda açıklanmaktadır.  
  
|Sütun|Açıklama|  
|------------|-----------------|  
|**Başlangıç zamanı**|Milisaniye veya işlemci sayısını, işlem veya iş parçacığı başına profil oluşturma başlangıç geçiş yapar.|  
|**Engellenme süresi**|Bu sırada iş parçacığı ve işlem işlevlerini yürütülmesini engellenen toplam süresi.|  
|**Engellenme süresi yüzdesi**|İşlem veya iş parçacığı ve işlem işlevlerini çalıştırılması engellenen iş parçacığı ömrünün yüzdesi.|  
|**Çakışmaları**|İş parçacığı ve işlem işlevlerini çalıştırılması engellenen sayısı.|  
|**Çekişme yüzdesi**|Profil çalıştıran tüm çekişmelerin yüzdesi, işlem veya iş parçacığı Çekişme yoktu.|  
|**Bitiş zamanı**|Milisaniye veya işlemci sayısını başından sonuna kadar işlem veya iş parçacığı profil oluşturma.|  
|**ID**|Sistem tarafından oluşturulan tanımlayıcısını işlem veya iş parçacığı.|  
|**Yaşam süresi**|Milisaniye veya işlemci sayısını, işlem ya da iş parçacığı işlem veya iş parçacığı sonuna ya da profil oluşturmanın sonuna başından itibaren geçiş yapar.|  
|**Türü**|Satır türü işlem veya iş parçacığı.<br /><br /> Yalnızca **VSReport** komut satırı raporlar. Daha fazla bilgi için [VSPerfReport](../profiling/vsperfreport.md).|  
|**Ad**|İşlem veya iş parçacığı adı.|  
|**Benzersiz kimliği**|İş parçacığı ve işlem için benzersiz olan bir profil oluşturucu tarafından oluşturulan bir tanımlayıcı.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: rapor görünümü sütunlarını özelleştirme](../profiling/how-to-customize-report-view-columns.md)   
 [İşlem Görünümü](../profiling/process-view.md)



