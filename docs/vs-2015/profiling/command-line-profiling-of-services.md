---
title: Komut satırından hizmetler profili oluşturma | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- profiling toos,services
- profiling services
ms.assetid: f0d62318-b0e8-49c6-9a30-9f7a6adef2f6
caps.latest.revision: 21
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 64cd62c29df9a7c43d690119194582b20a784c3c
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "63439007"
---
# <a name="command-line-profiling-of-services"></a>Komut Satırından Hizmetler Profili Oluşturma
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu bölümde kullanarak Windows Hizmetleri için performans verilerini toplamak için seçenekleri ve yordamları açıklanmaktadır [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] komut satırından profil oluşturma araçları.  
  
> [!NOTE]
> Windows 8 ve Windows Server 2012'deki Gelişmiş güvenlik özellikleri Visual Studio profil oluşturucu bu platformlarda veri toplayan bir şekilde önemli değişiklikler gerekmiştir. Windows Store apps ayrıca yeni toplama teknikleri gerektirir. Bkz: [Windows 8 ve Windows Server 2012 uygulamalarında performans araçları](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md).  
  
## <a name="common-tasks"></a>Ortak Görevler  
  
|Görev|İlgili içerik|  
|----------|---------------------|  
|**Uygulama istatistikleri toplamak:** Performans istatistikleri toplamak için örnekleme yöntemini kullanın. Veri örnekleme, CPU kullanımı sorunlarını analiz etmek için ve bir uygulamanın genel performans özelliklerini anlamak için kullanışlıdır.|-   [Örnekleme kullanarak uygulama istatistikleri toplama](../profiling/collecting-application-statistics-for-services-by-using-the-profiler-sampling-method.md)|  
|**Ayrıntılı zamanlama verileri toplama:** Ayrıntılı zamanlama bilgilerini toplamak için izleme metodunu kullanın. Ölçümlü izleme verileri ayrıntılı analiz uygulama senaryoları biri için g/ç sorunlarını analiz etmek için yararlı olacaktır.|-   [İzleme kullanarak ayrıntılı zamanlama verileri toplama](../profiling/collecting-detailed-timing-data-for-services-by-using-the-instrumentation-method-from-the-profiler-command-line.md)|  
|**.NET bellek verileri toplamak:** Ayrılmış nesnelerin sayısı ve boyutu gösteren .NET bellek ayırma verilerini toplamak için örnekleme veya Araçlar'ı kullanın. Her çöp toplama nesildeki kazanılır nesnelerinin sayısı ve boyutu gösteren nesne yaşam süresi verilerini de toplayabilirsiniz.|-   [.NET bellek verileri toplama](../profiling/collecting-memory-data-from-dotnet-framework-services-by-using-the-profiler-command-line.md)|  
|**Eşzamanlılık verileri toplamak:** Kaynak Çekişme verisi ve CPU kullanımı, iş parçacığı Çekişme, iş parçacığı geçişi, eşitleme gecikmeleri, alanları çakışan g/ç ve diğer sistem olaylarıdır gösteren iş parçacığı etkinlik verilerini toplamak için eşzamanlılık yöntemi kullanın.|-   [Eşzamanlılık verileri toplama](../profiling/collecting-concurrency-data-for-a-service-by-using-the-profiler-command-line.md)|  
|**Katman etkileşim verileri ekleyin:** Zaman uyumlu ADO.NET ilişkin performans verilerini çağırır, yapılan bir Microsoft hizmeti ekleyebilirsiniz [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] veritabanı.|-   [Katman etkileşim verileri toplama](../profiling/adding-tier-interaction-data-from-the-command-line.md)|  
  
## <a name="related-tasks"></a>İlişkili görevler  
  
|Görev|İlgili içerik|  
|----------|---------------------|  
|**(İstemci) tek başına uygulamaların profilini oluşturma**|-   [Bağımsız uygulamaların profilini oluşturma](../profiling/command-line-profiling-of-stand-alone-applications.md)|  
|**Profil ASP.NET uygulamaları**|-   [ASP.NET Web uygulamalarında profil oluşturma](../profiling/command-line-profiling-of-aspnet-web-applications.md)|
