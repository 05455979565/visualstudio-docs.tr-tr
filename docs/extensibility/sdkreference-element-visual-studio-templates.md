---
title: "SDKReference öğesi (Visual Studio şablonları) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 72c8b352-0b7a-42b3-ba5d-2a2d1e90c34b
caps.latest.revision: "5"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: a6ca0159d522d7890452a54986093f4062803faf
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="sdkreference-element-visual-studio-templates"></a>SDKReference Öğesi (Visual Studio Şablonları)
Öğe şablonu bir SDK başvurusu kullandığını belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```xml  
<VSTemplate>      
    <TemplateContent>          
        <References>              
            <Reference>  
                <SDKReference>SDKname</SDKReference>  
```  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
 Yok.  
  
### <a name="child-elements"></a>Alt Öğeler  
 Yok.  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[Başvuru](../extensibility/reference-element-visual-studio-templates.md)|Öğe bir projeye eklendiğinde eklemek için derleme başvurusu belirtir.|  
  
## <a name="text-value"></a>Metin Değeri  
 Bir metin değeri gereklidir.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu metin öğe şablonu örneği oluşturulduğunda bir projeye eklemek için SDK'sı başvurusu belirtir.  
  
```xml  
<VSTemplate Version="3.0.0" xmlns="http://schemas.microsoft.com/developer/vstemplate/2005" Type="Item">   
    <TemplateData> . . . </TemplateData>   
    <TemplateContent>   
        <References>   
            <Reference>   
                <SDKReference>Microsoft Visual C++ Runtime Package, Version=11.0.0.0</SDKReference>  
...  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [References öğesi (Visual Studio şablonları)](../extensibility/references-element-visual-studio-templates.md)   
 [Reference öğesi (Visual Studio şablonları)](../extensibility/reference-element-visual-studio-templates.md)   
 [Proje ve öğe şablonları oluşturma](../ide/creating-project-and-item-templates.md)   
 [Visual Studio Şablon Şeması Başvurusu](../extensibility/visual-studio-template-schema-reference.md)