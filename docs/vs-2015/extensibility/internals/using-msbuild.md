---
title: MSBuild kullanarak | Microsoft Docs
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
- VSPackages, compiling with MSBuild
- MSBuild, extensibility
- packages, compiling with MSBuild
ms.assetid: 9d38c388-1f64-430e-8f6c-e88bc99a4260
caps.latest.revision: 21
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: c8b776823c78835ad687a110c1fcc0ba1382bead
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42633101"
---
# <a name="using-msbuild"></a>MSBuild Kullanma
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [kullanarak MSBuild](https://docs.microsoft.com/visualstudio/extensibility/internals/using-msbuild).  
  
MSBuild proje öğeleri oluşturulması, derleme görevleri ve derleme yapılandırmaları için tam olarak açıklayan proje dosyaları oluşturmak için bir iyi tanımlanmış, Genişletilebilir XML biçiminde sağlar.  
  
 Bir dil proje sistemi Msbuild'i temel alan bir uçtan uca örnek için bkz: IronPython örnek ayrıntılı Bakışında[VSSDK örnekleri](../../misc/vssdk-samples.md).  
  
## <a name="general-msbuild-considerations"></a>Genel MSBuild konuları  
 MSBuild proje dosyaları, örneğin, [!INCLUDE[csprcs](../../includes/csprcs-md.md)] .csproj ve [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] .vbproj dosyalarının, oluşturma zamanında kullanılan, ancak tasarım zamanında kullanılan verileri de içerebilir veri içerir. Derleme zamanı verilerin depolanacağı MSBuild temelleri dahil olmak üzere, kullanarak [öğe unsuru (MSBuild)](../../msbuild/item-element-msbuild.md) ve [özellik öğesi (MSBuild)](../../msbuild/property-element-msbuild.md). Proje türü ve tüm ilgili proje alt türleri için belirli veri olan tasarım zamanı veri için rezerve serbest biçimli XML depolanır.  
  
 MSBuild, yapılandırma nesneleri için yerel destek yok ancak yapılandırmaya özgü verileri belirtmek için koşullu öznitelikler sağlar. Örneğin:  
  
```  
<OutputDir Condition="'$(Configuration)'=="release'">Bin\MyReleaseConfig</OutputDir>  
```  
  
 Koşullu öznitelikleri hakkında daha fazla bilgi için bkz. [koşullu yapıları](../../msbuild/msbuild-conditional-constructs.md).  
  
### <a name="extending-msbuild-for-your-project-type"></a>MSBuild proje türünüz için genişletme  
 MSBuild arabirimleri ve API'leri olan gelecek sürümlerinde değişebilir [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]. Bu nedenle, değişikliklere karşı koruma sağladığından, yönetilen paket framework (MPF) sınıflarını kullanacak şekilde akıllıca olur.  
  
 Projeleri (MPFProj) için yönetilen paket çerçevesini oluşturmak ve yeni proje sistemi yönetmek için yardımcı sınıflar sağlar. Kaynak kod ve derleme yönergelerini bulabilirsiniz [projeler - Visual Studio 2013 için MPF](http://mpfproj12.codeplex.com/).  
  
 Projeye özgü MPF sınıfları aşağıdaki gibidir:  
  
|örneği|Uygulama|  
|-----------|--------------------|  
|`Microsoft.VisualStudio.Package.ProjectNode`|<xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3><br /><br /> <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgProvider2><br /><br /> <xref:Microsoft.VisualStudio.Shell.Interop.IPersistFileFormat><br /><br /> <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents>|  
|`Microsoft.VisualStudio.Package.ProjectFactory`|<xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectFactory>|  
|`Microsoft.VisualStudio.Package.HierarchyNode`|<xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy>|  
|`Microsoft.VisualStudio.Package.ProjectConfig`|<xref:Microsoft.VisualStudio.Shell.Interop.IVsCfg><br /><br /> <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectCfg><br /><br /> <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildableProjectCfg><br /><br /> <xref:Microsoft.VisualStudio.Shell.Interop.IVsDebuggableProjectCfg>|  
|`Microsoft.VisualStudio.Package.SettingsPage`|<xref:Microsoft.VisualStudio.OLE.Interop.IPropertyPageSite>|  
  
 `Microsoft.VisualStudio.Package.ProjectElement` MSBuild öğeleri için bir sarmalayıcı sınıftır.  
  
#### <a name="single-file-generators-vs-msbuild-tasks"></a>Tek dosya oluşturucuları vs. MSBuild Görevleri  
 Tek dosya oluşturucuları-sadece tasarım zamanına kullanılabilip erişilebilir, ancak MSBuild görevleri tasarım zamanı ve derleme zamanı sırasında kullanılabilir. Maksimum esneklik için bu nedenle, dönüştürme ve kod oluşturmak için MSBuild görevleri kullanın. Daha fazla bilgi için [özel Araçlar](../../extensibility/internals/custom-tools.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MSBuild başvurusu](../../msbuild/msbuild-reference.md)   
 [MSBuild](http://msdn.microsoft.com/en-us/7c49aba1-ee6c-47d8-9de1-6f29a906e20b)   
 [Özel Araçlar](../../extensibility/internals/custom-tools.md)

