---
title: RequiredPlatformVersion öğesi (Visual Studio şablonları) | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6f0e4986-3157-4bba-aed3-c28413ebe976
caps.latest.revision: 7
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 5fb35bfefeb7722c3ec488a1f9caf63cd49202dd
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42697263"
---
# <a name="requiredplatformversion-element-visual-studio-templates"></a>RequiredPlatformVersion Öğesi (Visual Studio Şablonları)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [RequiredPlatformVersion öğesi (Visual Studio şablonları)](https://docs.microsoft.com/visualstudio/extensibility/requiredplatformversion-element-visual-studio-templates).  
  
Proje şablonu düzgün çalışması için gerekli işletim sistemi en düşük sürümünü belirtir. Bu öğe oluşturmak için proje şablonları kullanılan [!INCLUDE[win8_appname_long](../includes/win8-appname-long-md.md)] uygulamalar.  
  
 `RequiredPlatformVersion` Değeri doğrudan işletim sistemi sürümü ile karşılaştırılır. Varsa `RequiredPlatformVersion` işletim sistemi sürümünden daha yüksek olan şablon görünmez **yeni proje** iletişim kutusu. Bir şablon için belirttiğiniz için [!INCLUDE[win8](../includes/win8-md.md)] veya üzeri olarak ayarlayın `RequiredPlatformVersion` 6.2.0 için. Bir şablon için belirttiğiniz için [!INCLUDE[win81](../includes/win81-md.md)] veya üzeri olarak ayarlayın RequiredPlatformVersion 6.3.0 için.  
  
 Belirten şablonları `RequiredPlatformVersion`= 8 önceki müşteri ile uyumlu [!INCLUDE[win8_appname_long](../includes/win8-appname-long-md.md)] şablonları.  
  
 VSTemplate  
TemplateData  
... TargetPlatformName  
RequiredPlatformVersion  
  
## <a name="syntax"></a>Sözdizimi  
  
```xml  
<RequiredPlatformVersion> OperatingSystem </RequiredPlatformVersion>  
```  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Yok.  
  
### <a name="attributes"></a>Öznitelikler  
 Yok.  
  
### <a name="child-elements"></a>Alt Öğeler  
 Yok.  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[TemplatePlatformName](../extensibility/templatedata-element-visual-studio-templates.md)|Platformunu belirtir, proje şablonu hedefler.|  
  
## <a name="text-value"></a>Metin Değeri  
 Bir metin değeri gereklidir.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu metin şablon için gerekli en düşük işletim sistemi sürümünü belirtir.  
  
## <a name="example"></a>Örnek  
 Bu örnekte belirten proje şablonunun hedeflediği [!INCLUDE[win8](../includes/win8-md.md)] veya üzeri.  
  
```xml  
<VSTemplate Type="Project" Version="3.0.0"    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
    <TemplateData>  
        <TargetPlatformName>Windows</TargetPlatformName>  
            <RequiredPlatformVersion>6.3.0</RequiredPlatformVersion>  
  
    </TemplateData>  
    <TemplateContent>  
  
    </TemplateContent>  
</VSTemplate>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [TargetPlatformName öğesi (Visual Studio şablonları)](../extensibility/targetplatformname-element-visual-studio-templates.md)   
 [Proje ve öğe şablonları oluşturma](../ide/creating-project-and-item-templates.md)   
 [Visual Studio Şablon Şeması Başvurusu](../extensibility/visual-studio-template-schema-reference.md)
