---
title: Kullanıcı ayarları desteği | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- Custom Settings Points
- user settings [Visual Studio SDK], registering persistence support
- persistence, registering settings
ms.assetid: ad9beac3-4f8d-4093-ad0e-6fb00444a709
caps.latest.revision: 27
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 80734d9859df2e06bc51d40e1fffa40c7d97c7a7
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65691807"
---
# <a name="support-for-user-settings"></a>Kullanıcı Ayarları için Destek
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

VSPackage kullanıcı seçtiğinde, kalıcı durum değişken grupları, bir veya daha fazla ayarları kategorileri tanımlayabilir **içeri/dışarı aktarma ayarları** komutunu **Araçları** menüsü. Bu kalıcılığını sağlamak için ayarları API'leri kullanın. içinde [!INCLUDE[vsipsdk](../../includes/vsipsdk-md.md)].  
  
 Bir özel ayarları noktası ve bir GUID başvurulan bir kayıt defteri girişi VSPackage'nın ayarları kategorisi tanımlar. VSPackage birden çok ayar kategorileri destekler, her bir özel ayarları noktası tarafından tanımlanan.  
  
- Birlikte çalışma derlemelerini temel ayarları uygulamaları (kullanarak <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserSettings> arabirimi) kayıt defterini düzenledikten veya Kaydedici betik (.rgs dosyası) kullanarak özel ayarları noktası oluşturmanız gerekir. Daha fazla bilgi için [Kaydedici betikleri oluşturma](https://msdn.microsoft.com/library/cbd5024b-8061-4a71-be65-7fee90374a35).  
  
- Yönetilen paket Framework (MPF) kullanan kodu oluşturmalıdır özel ayarları noktaları ekleyerek bir <xref:Microsoft.VisualStudio.Shell.ProvideProfileAttribute> her özel ayarları noktası VSPackage'ı için.  
  
     Birkaç özel ayarları noktası tek bir VSPackage'ı destekliyorsa, her özel ayarları noktası ayrı bir sınıf tarafından uygulanır ve her benzersiz bir örneği tarafından kayıtlı <xref:Microsoft.VisualStudio.Shell.ProvideProfileAttribute> sınıfı. Sonuç olarak, sınıf uygulama bir ayar birden fazla ayarları kategorisi destekleyebilir.  
  
## <a name="custom-settings-point-registry-entry-details"></a>Özel ayarlar noktası kayıt defteri girişi ayrıntıları  
 Özel ayarları noktaları bir kayıt defteri girişini şu konumda oluşturulur: HKLM\Software\Microsoft\VisualStudio\\ *\<sürüm >* \UserSettings\\`<CSPName>`burada `<CSPName>` VSPackage'ı destekleyen özel ayarları noktası adıdır ve  *\<sürüm >* sürümü [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)], örneğin 8.0.  
  
> [!NOTE]
> Kök yolu hkey_local_machıne\software\microsoft\visualstudio\\ *\<sürüm >* bir alternatif ile geçersiz kılınabilir ne zaman kök [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] tümleşik geliştirme ortamıdır (IDE) başlatılmamış. Daha fazla bilgi için [komut satırı anahtarları](../../extensibility/command-line-switches-visual-studio-sdk.md).  
  
 Kayıt defteri girdisi yapısı aşağıda gösterilmiştir:  
  
 HKLM\Software\Microsoft\VisualStudio\\ *\<sürüm >* \UserSettings\  
  
 `<CSPName`>= s '#12345'  
  
 Paket '{XXXX XXXXXX XXXX XXXX XXXXXXXXX}' =  
  
 Kategori = '{YYYYYY YYYY YYYY YYYY YYYYYYYYY}'  
  
 ResourcePackage = '{ZZZZZZ ZZZZ ZZZZ ZZZZ ZZZZZZZZZ}'  
  
 AlternateParent CategoryName =  
  
|Ad|Tür|Veri|Açıklama|  
|----------|----------|----------|-----------------|  
|(Varsayılan)|REG_SZ|Özel ayarları noktası adı|Anahtarın adı `<CSPName`>, özel ayarları noktası yerelleştirilmemiş adıdır.<br /><br /> Üzerinde MPF tabanlı uygulamalar için anahtarın adını birleştirerek elde edilen `categoryName` ve `objectName` bağımsız değişkenleri <xref:Microsoft.VisualStudio.Shell.ProvideProfileAttribute> oluşturucuya `categoryName_objectName`.<br /><br /> Anahtar boş olabilir veya bir uydu DLL yerelleştirilmiş dizeye başvuru kimliği içerebilir. Bu değer elde edilir `objectNameResourceID` bağımsız değişkeni <xref:Microsoft.VisualStudio.Shell.ProvideProfileAttribute> Oluşturucusu.|  
|Paket|REG_SZ|GUID|Özel ayarları noktası uygulayan VSPackage GUİD'si.<br /><br /> Uygulamaları tabanlı MPF kullanarak <xref:Microsoft.VisualStudio.Shell.ProvideProfileAttribute> sınıfı, oluşturucunun kullanın `objectType` VSPackage'nın içeren bağımsız değişken <xref:System.Type> ve bu değeri elde etmek için yansıma.|  
|Kategori|REG_SZ|GUID|Ayarları kategorisi tanımlayan GUID.<br /><br /> Birlikte çalışma derlemelerini tabanlı uygulamalar için bu değer bir rasgele seçilen olabilir GUID, hangi [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] IDE geçtiği <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserSettings.ExportSettings%2A> ve <xref:Microsoft.VisualStudio.Shell.Interop.IVsUserSettings.ImportSettings%2A> yöntemleri. Bu iki yöntemden birini tüm uygulamaları kendi bir GUID bağımsız değişken doğrulamanız gerekir.<br /><br /> Üzerinde MPF tabanlı uygulamalar için bu GUID ile alınan <xref:System.Type> sınıfı uygulama [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] ayarları mekanizması.|  
|ResourcePackage|REG_SZ|GUID|İsteğe bağlı.<br /><br /> Uygulama VSPackage bunları sağlamazsa, uydu DLL içeren yolu dizeleri yerelleştirilmiş.<br /><br /> MPF VSPackage, doğru kaynak almak için yansıtma kullanır böylece <xref:Microsoft.VisualStudio.Shell.ProvideProfileAttribute> sınıfı, bu bağımsız değişken ayarlı değil.|  
|AlternateParent|REG_SZ|Bu özel ayarları noktasını içeren araçları seçenekleri sayfasından altında klasör adı.|İsteğe bağlı.<br /><br /> Yalnızca bir ayarları uygulaması destekliyorsa, bu değeri ayarlamanız gerekir **Araçlar Seçenekler** Kalıcılık mekanizması olarak kullanan sayfaları [!INCLUDE[vsipsdk](../../includes/vsipsdk-md.md)] durumunu kaydetmek için Otomasyon modelindeki mekanizması yerine.<br /><br /> Bu gibi durumlarda AlternateParent anahtar değer `topic` bölümünü `topic.sub-topic` belirli tanımlamak için kullanılan dize **ToolsOptions** sayfası. Örneğin, **ToolsOptions** sayfa `"TextEditor.Basic"` AlternateParent değer `"TextEditor"`.<br /><br /> Zaman <xref:Microsoft.VisualStudio.Shell.ProvideProfileAttribute> özel ayarları noktası oluşturur, kategori adı ile aynıdır.|
