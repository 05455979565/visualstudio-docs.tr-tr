---
title: 'Nasıl yapılır: Windows sayaç verileri toplama | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.property.syscounter
- vs.performance.property.wincounter
helpviewer_keywords:
- windows counters
- performance tools, using windows counters
- profiling tools, using windows counters
ms.assetid: db4fbac2-bea5-4558-aa8b-160fcccf4b33
caps.latest.revision: 18
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 9743fa7defbbf3321636d2ba4799454713a647db
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "63432776"
---
# <a name="how-to-collect-windows-counter-data"></a>Nasıl yapılır: Windows sayaç verileri toplama
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Windows sayaçları profil oluşturma sırasında belirlenen aralıklarla toplanabilecek sistem performans sayaçları ' dir. Profil oluşturma araçları rapor işaretler görünümünde bir satır olarak etiketlenmiş **AutoMark** her koleksiyon aralığı. Satır o aralıkta performans sayaç değerlerini tanımlayan sütun içerir. Analizi iki belirli işaret arasındaki zaman dilimiyle sınırlamak için işaretleri, sağ tıklayın ve ardından seçin **filtre tarafından** ->  **işaretleri** kısayol menüsünden.  
  
 **Gereksinimler**  
  
- [!INCLUDE[vsUltLong](../includes/vsultlong-md.md)], [!INCLUDE[vsPreLong](../includes/vsprelong-md.md)], [!INCLUDE[vsPro](../includes/vspro-md.md)]  
  
> [!NOTE]
> Windows 8 ve Windows Server 2012'deki Gelişmiş güvenlik özellikleri Visual Studio profil oluşturucu bu platformlarda veri toplayan bir şekilde önemli değişiklikler gerekmiştir. Windows Store apps ayrıca yeni toplama teknikleri gerektirir. Bkz: [Windows 8 ve Windows Server 2012 uygulamalarında performans araçları](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).  
  
### <a name="to-collect-windows-counter-data"></a>Windows sayaç verileri toplamak için  
  
1. Performans Gezgini içinde Windows sayaçları yapılandırmak ve seçmek istediğiniz oturumu sağ **özellikleri**.  
  
2. İçinde **özellik sayfaları**, tıklayın **Windows sayaçları**.  
  
3. Seçin **Windows sayaçları toplamak** onay kutusu.  
  
4. İçinde **toplama aralığı (milisaniye)** metin kutusunda, bir zaman aralığı yazın.  
  
5. Bir kategori seçin **sayaç kategorisi** aşağı açılan listesi.  
  
6. Bir örnekten seçin **örneği** aşağı açılan listesi.  
  
7. Uygulamanızın profilini, kullanmak istediğiniz sayaçları seçin.  
  
8. Tıklayın **uygulayın.**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Performans oturumlarını yapılandırma](../profiling/configuring-performance-sessions.md)   
 [Performans oturum özellikleri](../profiling/performance-session-properties.md)   
 [CPU ve Windows Sayaçları](../profiling/cpu-and-windows-counters.md)
