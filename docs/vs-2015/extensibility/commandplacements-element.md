---
title: CommandPlacements öğesi | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- CommandPlacements
helpviewer_keywords:
- CommandPlacements element (VSCT XML schema)
- VSCT XML schema elements, CommandPlacements
ms.assetid: 78a5724a-3b9f-4c78-9c0d-8faa3924f81c
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 449a419a84f0f367ea1c97ec56d57fcd936ae423
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42634057"
---
# <a name="commandplacements-element"></a>CommandPlacements Öğesi
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CommandPlacements öğesi](https://docs.microsoft.com/visualstudio/extensibility/commandplacements-element).  
  
CommandPlacements öğesi CommandPlacement öğeleri ve diğer CommandPlacements gruplandırmaları gruplandırır.  
  
 CommandPlacements öğesi isteğe bağlıdır. Hiçbir komut, grupları veya menüler, ikincil bir konumda eklenmelidir, bu bölümde .vsct dosyanıza dahil gerekmez.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
<CommandPlacements>  
  <CommandPlacement>... </CommandPlacement>  
  <CommandPlacement>... </CommandPlacement>  
</CommandPlacements>  
```  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|Koşul|İsteğe bağlı. Bkz: [koşullu öznitelikler](../extensibility/vsct-xml-schema-conditional-attributes.md).|  
  
### <a name="child-elements"></a>Alt Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|CommandPlacements|CommandPlacement öğeleri gruplandırır ve diğer CommandPlacements gruplandırmaları.|  
|[CommandPlacement Öğesi](../extensibility/commandplacement-element.md)|Düğmeler, grupları ve menüler birden fazla grup veya menüdeki dahil edilmesini sağlar.|  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[CommandTable Öğesi](../extensibility/commandtable-element.md)|Komutları temsil eden tüm öğeleri tanımlar.|  
  
## <a name="example"></a>Örnek  
  
```  
<CommandPlacements>  
  <CommandPlacement guid="guidWidgetPackage" id="cmdidInsertOptions"  
    priority="0x0300">  
    <Parent guid="cmdGuidWidgetCommands" id="menuIDEditWidget"/>  
  </CommandPlacement>  
</CommandPlacements>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CommandPlacement öğesi](../extensibility/commandplacement-element.md)   
 [Visual Studio Komut Tablosu (.Vsct) Dosyaları](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)

