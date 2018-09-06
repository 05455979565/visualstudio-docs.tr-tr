---
title: Toplama ayrıntılı zamanlama verileri araçları kullanarak | Microsoft Docs
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
- Profiling Tools,instrumentation method
- instrumentation profiling method
ms.assetid: e9deb370-c459-45ac-84d3-14d646590d05
caps.latest.revision: 23
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ae3d2335c73f68f790e9b3def8f2a1d4ced7c969
ms.sourcegitcommit: 6944ceb7193d410a2a913ecee6f40c6e87e8a54b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43774906"
---
# <a name="collecting-detailed-timing-data-by-using-instrumentation"></a>İzleme Kullanarak Ayrıntılı Zamanlama Verileri Toplama
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [tarafından ölçümlü izleme kullanarak ayrıntılı zamanlama verileri toplama](https://docs.microsoft.com/visualstudio/profiling/collecting-detailed-timing-data-by-using-instrumentation).  
  
[!INCLUDE[vsprvs](../includes/vsprvs-md.md)] Profil oluşturma araçları araç haline getirme yöntemi, bir modülün bir kopyasını profil oluşturma kodu ekler. Kodun her giriş, çıkış ve işlevlerin işlev çağrısı modülünde bir profil oluşturma sırasında kaydeder. Araçlar yöntemini giriş ve çıkış işlemleri uygulama performansı üzerindeki etkisini anlamak için kodun bir bölümünü hakkında ayrıntılı zamanlama bilgileri toplamak için yararlı olacaktır.  
  
 Araçlar yöntemini aşağıdaki yordamlardan birini kullanarak belirtebilirsiniz:  
  
-   Profil Oluşturma Sihirbazı'nın ilk sayfasında, seçin **izleme**.  
  
-   Üzerinde **performans Gezgini** araç penceresindeki **yöntemi** listesinde **izleme**.  
  
-   Üzerinde **genel** sayfa seçin performans oturumu Özellikleri iletişim kutusunun **izleme**.  
  
## <a name="common-tasks"></a>Ortak Görevler  
 Ek seçenekler belirtebilirsiniz _performans oturumu_**özellik sayfaları** performans oturumunun iletişim kutusu. Bu iletişim kutusunu açmak için:  
  
-   İçinde **performans Gezgini**performans oturumu adına sağ tıklayın ve ardından **özellikleri**.  
  
 Aşağıdaki tabloda görevler belirleyebilirsiniz seçenekleri açıklanmıştır _performans oturumu_**özellik sayfaları** iletişim kutusuna izleme metodunu kullanarak profili.  
  
|Görev|İlgili içerik|  
|----------|---------------------|  
|Üzerinde **genel** sayfasında .NET bellek ayırma ve yaşam süresi verilerini ekleyin ve oluşturulan profil oluşturma veri (.vsp) dosyasının adlandırma ayrıntılarını belirtin.|-   [.NET bellek ayırma ve yaşam süresi verilerini toplama](../profiling/collecting-dotnet-memory-allocation-and-lifetime-data.md)<br />-   [Nasıl yapılır: performans veri dosyası adlandırma seçeneklerini ayarlama](../profiling/how-to-set-performance-data-file-name-options.md)|  
|Üzerinde **başlatma** , solution.specify içinde birden çok .exe proje başlatmak için uygulama ve bunların başlatma sırasını varsa, sayfa.|-   [Nasıl yapılır: başlatma için ikili dosya belirtme](../profiling/how-to-specify-the-binary-to-start.md)|  
|Üzerinde **ikili dosyaları** sayfasında, modüller için izleme eklenmiş kopyalar konumunu belirtin. Varsayılan olarak, orijinal ikililerin bir yedekleme klasörüne taşınır.|-   [Nasıl yapılır: işaretlenmiş ikilileri yeniden Yerleştir](../profiling/how-to-relocate-instrumented-binaries.md)|  
|Üzerinde **katman etkileşim** sayfasında, profil oluşturma çalışması için ADO.NET çağrı veri ekleyin.|-   [Katman etkileşim verileri toplama](../profiling/collecting-tier-interaction-data.md)|  
|Üzerinde **izleme** öncesinde ve sonrasında bir komut isteminde çalıştırmak için komutları belirtin sayfasında ve ek yükü, profil oluşturma profili ASP.NET Web sayfalarında JavaScript kodu azaltmak için profil küçük işlevleri Dışla izleme işlemi.|-   [Nasıl yapılır: kısa işlevleri izlemeden dahil veya hariç](../profiling/how-to-exclude-or-include-short-functions-from-instrumentation.md)<br />-   [Nasıl yapılır: Web sayfalarında JavaScript kodu profili](../profiling/how-to-profile-javascript-code-in-web-pages.md)<br />-   [Nasıl yapılır: ön ve son izleme komutları belirtme](../profiling/how-to-specify-pre-and-post-instrument-commands.md)|  
|Üzerinde **CPU sayaçları** sayfasında, profil oluşturma verileri eklemek için bir veya daha fazla işlemci performans sayaçları belirtin.|-   [Nasıl yapılır: CPU sayaç verileri toplama](../profiling/how-to-collect-cpu-counter-data.md)|  
|Üzerinde **Windows olayları** sayfasında, örnekleme verileri toplama için bir veya daha fazla olay izleme için Windows (ETW) olayları seçin.|-   [Nasıl yapılır: olay izleme için Windows (ETW) verilerini toplama](../profiling/how-to-collect-event-tracing-for-windows-etw-data.md)|  
|Üzerinde **Windows sayaçları** sayfasında işaretleri olarak profil oluşturma verilerini eklemek için bir veya daha fazla işletim sistemi performans sayaçları belirtin.|-   [Nasıl yapılır: Windows sayaç verileri toplama](../profiling/how-to-collect-windows-counter-data.md)|  
|Üzerinde **Gelişmiş** sayfasında, Vsınstr izleme programa dahil etmek veya belirli işlevleri hariç tutmak için seçenekleri gibi geçirmek istediğiniz ek seçenekleri belirtin.|-   [Nasıl yapılır: ek izleme seçeneklerini belirtme](../profiling/how-to-specify-additional-instrumentation-options.md)<br />-   [Nasıl yapılır: izlemeyi belirli araçlarla sınırlama](../profiling/how-to-limit-instrumentation-to-specific-functions.md)<br />-   [Vsınstr](../profiling/vsinstr.md)|



