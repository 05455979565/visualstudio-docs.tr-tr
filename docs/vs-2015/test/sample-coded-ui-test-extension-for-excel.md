---
title: Excel için kodlanmış UI testi uzantısı örneği | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- coded UI tests, extensions for Excel
ms.assetid: 451e4d14-7fac-42f9-af56-2bdc8414c6c7
caps.latest.revision: 15
ms.author: gewarren
manager: douge
ms.openlocfilehash: b4da574b77d8dd2b1b14ccb0b04e449799338620
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42688151"
---
# <a name="sample-coded-ui-test-extension-for-excel"></a>Excel için Kodlanmış UI Testi Uzantısı Örneği
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [örnek kodlanmış UI testi uzantısı için Excel](https://docs.microsoft.com/visualstudio/test/sample-coded-ui-test-extension-for-excel).  
  
Örnek uzantısı bileşeninin çalışan [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] kodlanmış UI testi işlemi ve biraz hiyerarşik `ExtensionPackage` temel sınıf. `TechnologyManager`, `ActionFilter`, Ve `PropertyProvider` sınıflardır sonraki düzeyi, en üst düzeyinde denetim öğeleri.  
  
 ![Excel Test Uzantısı Mimarisi](../test/media/excel-extarch.png "Excel_ExtArch")  
Excel uzantısı mimarisi  
  
## <a name="extension-points"></a>Uzantı noktaları  
 Bu sınıflar, kodlanmış UI testi etkinleştirmek için örneği'nde uygulanan uzantı noktaları temsil [!INCLUDE[ofprexcel](../includes/ofprexcel-md.md)].  
  
### <a name="extensionpackage"></a>ExtensionPackage  
 Devralınan <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITestExtensionPackage> sınıfı, bu, kodlanmış UI testi uzantısı için giriş noktası. Bu Özet sınıf uygulama kodlanmış UI testi özel kullanıcı Arabirimi test teknoloji Yöneticisi, kullanıcı Arabirimi test özellik sağlayıcısı ve yeni UI testi için kullanıcı Arabirimi test eylemi filtre framework iç erişim sağlar. Daha fazla bilgi için [ExtensionPackage sınıfı](../test/sample-excel-extension-extensionpackage-class.md).  
  
### <a name="technologymanager"></a>TechnologyManager  
 Devralınan <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyManager> sınıfı, bu sınıfın sağladığı bir teknoloji Yöneticisi test kaydı ve kayıttan yürütme için. Daha fazla bilgi için [TechnologyManager sınıfı](../test/sample-excel-extension-technologymanager-class.md).  
  
### <a name="actionfilter"></a>ActionFilter  
 Devralınan <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter> sınıfı, bu sınıfın sağladığı temel sınıf bir tek bir test sonucu benzer test eylem sonuçlarını toplamak için. Daha fazla bilgi için [ActionFilter sınıfı](../test/sample-excel-extension-actionfilter-class.md).  
  
### <a name="technology-elements"></a>Teknoloji öğeleri  
 Devralınan bir temel sınıf <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyElement> sınıfı kaydı ve kayıttan UI testleriniz teknoloji öğeleri için temel sağlar. Daha fazla bilgi için [öğe sınıfları](../test/sample-excel-extension-element-classes.md).  
  
### <a name="propertyprovider"></a>PropertyProvider  
 Devralınan <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestPropertyProvider> sınıfı, bu sınıfın sağladığı temel sınıf test kaydı ve kayıttan yürütme için kullanıcı Arabirimi öğeleri özelliklerini desteklemek için. Daha fazla bilgi için [PropertyProvider sınıfı](../test/sample-excel-extension-propertyprovider-class.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestPropertyProvider>   
 <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITechnologyElement>   
 <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UITestActionFilter>   
 <xref:Microsoft.VisualStudio.TestTools.UITest.Extension.UITestExtensionPackage>   
 [ExtensionPackage sınıfı](../test/sample-excel-extension-extensionpackage-class.md)   
 [TechnologyManager Sınıfı](../test/sample-excel-extension-technologymanager-class.md)   
 [ActionFilter sınıfı](../test/sample-excel-extension-actionfilter-class.md)   
 [Öğe sınıfları](../test/sample-excel-extension-element-classes.md)   
 [PropertyProvider Sınıfı](../test/sample-excel-extension-propertyprovider-class.md)



