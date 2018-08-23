---
title: '&lt;assemblyIdentity&gt; öğesi (ClickOnce uygulaması) | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-deployment
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- urn:schemas-microsoft-com:asm.v2#assemblyIdentity
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- <assemblyIdentity> element [ClickOnce application manifest]
ms.assetid: f48e9531-efac-4d11-8166-f63a5ece1ac5
caps.latest.revision: 22
author: mikejo5000
ms.author: mikejo
manager: wpickett
ms.openlocfilehash: 67ee803e18a1b098cd8e1bad2befd5a2d794766c
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42696043"
---
# <a name="ltassemblyidentitygt-element-clickonce-application"></a>&lt;assemblyIdentity&gt; öğesi (ClickOnce uygulaması)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [ &lt;assemblyIdentity&gt; öğesi (ClickOnce uygulaması)](https://docs.microsoft.com/visualstudio/deployment/assemblyidentity-element-clickonce-application).  
  
Dağıtılan uygulamayı tanımlayan bir [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] dağıtım.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      <assemblyIdentity   
   name  
   version  
   publicKeyToken  
   processorArchitecture  
   language  
/>  
```  
  
## <a name="elements-and-attributes"></a>Öğeler ve öznitelikler  
 `assemblyIdentity` Öğesi gereklidir. Alt öğe içerir ve aşağıdaki özniteliklere sahiptir.  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`Name`|Gerekli. Uygulamanın adını tanımlar.<br /><br /> Varsa `Name` özel karakterler içeriyor ve tek veya çift tırnak gibi uygulama etkinleştirmesi başarısız olabilir.|  
|`Version`|Gerekli. Uygulamanın sürüm numarası şu biçimde belirtir: `major.minor.build.revision`|  
|`publicKeyToken`|İsteğe bağlı. Son 8 baytını temsil eden 16 karakterlik bir onaltılık dize belirtir `SHA-1` altında derleme veya uygulama imzalanan ortak anahtarı değerini karma. Katalog imzalamak için kullanılan ortak anahtar, 2048 bit olmalıdır veya büyük.<br /><br /> Bu öznitelik, bir derlemeyi imzalamayı önerilir ancak isteğe bağlı olsa da gereklidir. Bir derlemeyi imzalı değilse, değeri otomatik olarak imzalanan bir derlemeden kopyalama ya da sıfır "kukla" değerini kullanın.|  
|`processorArchitecture`|Gerekli. İşlemciyi belirtir. Geçerli değerler `msil` tüm işlemciler için `x86` 32-bit Windows için `IA64` 64 bit Windows için ve `Itanium` Intel 64-bit Itanium işlemcilere için.|  
|`language`|Gerekli. İki bölümü dil kodlarını tanımlar (örneğin, `en-US`) derlemenin. Bu öğe `asmv2` ad alanı. Belirtilmemişse, varsayılan değer `neutral`.|  
  
## <a name="examples"></a>Örnekler  
  
### <a name="description"></a>Açıklama  
 Aşağıdaki kod örneğinde gösterilmiştir bir `assemblyIdentity` öğesinde bir [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] uygulama bildirimi. Bu kod örneği, sağlanan daha büyük bir örneğin parçasıdır [ClickOnce Uygulama bildirimi](../deployment/clickonce-application-manifest.md).  
  
### <a name="code"></a>Kod  
  
```  
<asmv1:assemblyIdentity   
  name="My Application Deployment.exe"   
  version="1.0.0.0"   
  publicKeyToken="43cb1e8e7a352766"   
  language="neutral"   
  processorArchitecture="x86"   
  type="win32" />  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ClickOnce Uygulama bildirimi](../deployment/clickonce-application-manifest.md)   
 [\<assemblyIdentity > öğesi](../deployment/assemblyidentity-element-clickonce-deployment.md)



