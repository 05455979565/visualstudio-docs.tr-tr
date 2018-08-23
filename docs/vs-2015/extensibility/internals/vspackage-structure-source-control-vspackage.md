---
title: VSPackage yapısı (kaynak denetimi VSPackage'ı) | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- VSPackages, structure
- source control packages, VSPackage overview
ms.assetid: 92722be7-b397-48c3-a7a7-0b931a341961
caps.latest.revision: 27
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 8c27eb3c0bc977f716d3437042e1e4105eb1692d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42633871"
---
# <a name="vspackage-structure-source-control-vspackage"></a>VSPackage Yapısı (Kaynak Denetimi VSPackage’ı)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [VSPackage yapısı (kaynak denetimi VSPackage'ı)](https://docs.microsoft.com/visualstudio/extensibility/internals/vspackage-structure-source-control-vspackage).  
  
Kaynak denetimi paket SDK izin kendi kaynak denetimi işlevlerini ile tümleştirmek bir kaynak denetimi uygulayan bir VSPackage'ı oluşturma yönergeleri sağlar [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] ortam. VSPackage genellikle tarafından isteğe bağlı olarak yüklenen bir COM bileşenidir [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] tümleşik geliştirme ortamı (IDE), kayıt defteri girdilerini pakette tarafından tanıtılan Hizmetleri temel. Her VSPackage'ı uygulamalıdır <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage>. VSPackage genellikle Hizmetleri tarafından sunulan kullanıyor [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] IDE ve bazı hizmetler kendi proffers.  
  
 VSPackage kendi menü öğeleri bildirir ve varsayılan öğe durumu .vsct dosyası aracılığıyla oluşturur. [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] IDE VSPackage yüklenene kadar bu menü öğeleri Bu durumdayken görüntüler. Sonuç olarak, VSPackage'nın uygulaması <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> etkinleştirmek ya da menü öğelerini devre dışı yöntemi çağrılır.  
  
## <a name="source-control-package-characteristics"></a>Kaynak denetimi paket özellikleri  
 Kaynak denetimi VSPackage'ı ile son derece tümleşiktir [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].  
  
 VSPackage semantiği şunlardır:  
  
-   VSPackage'ı olan da uygulanacak arabirim ( `IVsPackage` arabirimi)  
  
-   Komut kullanıcı Arabirimi uygulama (.vsct dosyası ve uygulaması <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> arabirimi)  
  
-   İle VSPackage kaydı [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].  
  
 Kaynak denetimi VSPackage'ı ile diğer iletmelidir [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] varlıkları:  
  
-   Projeler  
  
-   Düzenleyiciler  
  
-   Çözümler  
  
-   Windows  
  
-   Çalıştırılan Belge tablosu  
  
### <a name="visual-studio-environment-services-that-may-be-consumed"></a>Tüketilebilir visual Studio ortamını Hizmetleri  
 <xref:Microsoft.VisualStudio.Shell.Interop.SVsShell>  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.SVsUIShell>  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.SVsSolution>  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.SVsSolution>  
  
 SVsRegisterScciProvider hizmeti  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.SVsQueryEditQuerySave>  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.SVsTrackProjectDocuments>  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.SVsSccManager>  
  
### <a name="vsip-interfaces-implemented-and-called"></a>Uygulanan ve adlı VSIP arabirimleri  
 Kaynak denetimi VSPackage paketidir ve bu nedenle doğrudan diğer kayıtlı VSPackages ile etkileşebilirsiniz [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]. Kaynak denetimi işlevlerini teknolojilerimizden sağlamak için kaynak denetimi VSPackage'ı projeleri veya kabuk tarafından sağlanan arabirimlerle giderebilirsiniz.  
  
 Her projede [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] uygulamalıdır <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3> içinde bir proje olarak tanınması için [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] IDE. Ancak, bu arabirimi değil özel kaynak denetimi için yeterli. Altında bir kaynak olarak beklenen projelerini denetleyecek uygulama <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProject2>. Bu arabirim içeriği için bir proje sorgulamak ve karakterleri ve bağlama bilgileri (sunucu konumu ve disk konumu altında olan proje arasında bağlantı kurmak için gereken bilgileri sağlamak için kaynak denetimi VSPackage'ı tarafından kullanılır Kaynak Denetimi).  
  
 Kaynak denetimi VSPackage'ı uygulayan <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccManager2>, sırayla sağlayan kendileri için kaynak denetimi kaydedin ve bunların durumunu karakterleri almak proje.  
  
 Kaynak denetimi VSPackage'ı dikkate almanız gereken arabirimleri tam bir listesi için bkz. [ilgili hizmetler ve arabirimler](../../extensibility/internals/related-services-and-interfaces-source-control-vspackage.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Tasarım öğeleri](../../extensibility/internals/source-control-vspackage-design-elements.md)   
 [İlgili hizmetler ve arabirimler](../../extensibility/internals/related-services-and-interfaces-source-control-vspackage.md)

