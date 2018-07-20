---
title: Özellik sayfaları Web projeleri için ayarları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging [Visual Studio], Web applications
- project settings [Visual Studio], debug configurations
- debug builds, project settings
- projects [Visual Studio], debug configurations
- debugging Web applications, project settings
- debug configurations, Web projects
ms.assetid: 8ec5160a-6408-4f47-8d41-f0e20e79a3b9
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5584d5c5f971231712fb79f4ad40d330dd659b33
ms.sourcegitcommit: 0e5289414d90a314ca0d560c0c3fe9c88cb2217c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/19/2018
ms.locfileid: "39151639"
---
# <a name="property-pages-settings-for-web-projects"></a>Web Projeleri Özellik Sayfası Ayarları
Bir web sitesi hata ayıklama yapılandırmasında özellik ayarları değiştirebilirsiniz **özellik sayfaları** anlatıldığı gibi iletişim kutusu, [hata ayıklama ve yayın yapılandırmaları](../debugger/how-to-set-debug-and-release-configurations.md). Aşağıdaki tablolarda, hata ayıklayıcı ile ilgili ayarların nerede bulunacağı gösterilmektedir **özellik sayfaları** iletişim kutusu.  
  
### <a name="configuration-properties-folder-start-options-category"></a>Yapılandırma özellikleri klasörü (Başlat seçenekleri kategori)  
  
|**Ayarı**|**Açıklama**|  
|-----------------|---------------------|  
|**Başlatma eylemi**|Grupları seçenekleri için uygulama başlatma ilgili başlığı.|  
|**Geçerli sayfayı kullanın.**|Hata ayıklama için başlangıç noktası olarak geçerli sayfayı belirtir.|  
|**Belirli sayfa:**|Hata ayıklamayı başlatmak için istediğiniz Web sayfası belirtir.|  
|**Dış programı Başlat:**|Hata ayıklamak istediğiniz program başlatmak için komut belirtir.|  
|**Komut satırı bağımsız değişkenleri:**|Yukarıda belirtilen komut için bağımsız değişkenleri belirtir.|  
|**Çalışma dizini:**|Ayıklanan programın çalışma dizini belirtir. İçinde [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)], çalışma dizini, uygulama varsayılan olarak, \bin\debug başlatılan dizinidir.|  
|**Başlangıç URL'si**|Web uygulamasının hatalarını ayıklamak istediğiniz konumu belirtir.|  
|**Bir sayfa açma. Harici uygulamadan istek için bekle**|Harici uygulamadan istek için beklenecek diyor. Bu seçenek, Internet Explorer veya başka bir uygulama başlatılmaz. Yalnızca, bir uygulama tarafından çağrıldığında hata ayıklamaya hazırlar.|  
|**Sunucu**|Grupları seçenekleri kullanılacak sunucunun ilgili başlığı.|  
|**Varsayılan Web sunucusunu kullan**|Varsayılan Web sunucusu kullanacak şekilde söyler.|  
|**Özel sunucu kullan**|Sunucusu olarak kullanmak için temel URL'yi girmenizi sağlar.|  
|**Hata ayıklayıcılar**|Grupları seçenekleri yapılması hata ayıklama bilgisinin türüne ilgili başlığı.|  
|**ASP.NET hata ayıklaması**|Sunucu sayfalar için yazılan hata ayıklamasını etkinleştirir [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] geliştirme platformu. Bir URL belirtmelisiniz **URL'yi Başlat**.|  
|**Yerel kodda hata ayıklama**|Yerel (yönetilmeyen) Win32 koddaki çağrıları yönetilen uygulamanızın hatalarını ayıklamanızı sağlar.|  
|**SQL Server hata ayıklama**|SQL Server veritabanı nesnelerini hata ayıklamasını sağlar.|  
|**Silverlight'ta hata ayıklama**|Silverlight bileşenleri hata ayıklamasını sağlar.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata ayıklayıcı ayarları ve hazırlığı](../debugger/debugger-settings-and-preparation.md)