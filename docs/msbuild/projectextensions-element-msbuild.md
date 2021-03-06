---
title: ProjectExtensions Öğesi (MSBuild) | Microsoft Dokümanlar
ms.date: 03/13/2017
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#ProjectExtensions
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- <ProjectExtensions> element [MSBuild]
- ProjectExtensions element [MSBuild]
ms.assetid: f95f312f-ff92-41eb-9469-ad99e236a307
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 94f2d88aa19bf01ebe6f25c7d80772c812abcc59
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/18/2020
ms.locfileid: "77632972"
---
# <a name="projectextensions-element-msbuild"></a>ProjectExtensions öğesi (MSBuild)

MSBuild proje dosyalarının MSBuild olmayan bilgileri içermesine izin verir. Bir `ProjectExtensions` öğenin içindeki her şey MSBuild tarafından yoksayılır.

 \<Proje \<> ProjeUzantıları>

## <a name="syntax"></a>Sözdizimi

```xml
<ProjectExtensions>
    Non-MSBuild information to include in file.
</ProjectExtensions>
```

## <a name="attributes-and-elements"></a>Öznitelikler ve öğeler

 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.

### <a name="attributes"></a>Öznitelikler

 None

### <a name="child-elements"></a>Alt öğeleri

 None

### <a name="parent-elements"></a>Üst öğeler

| Öğe | Açıklama |
| - | - |
| [Proje](../msbuild/project-element-msbuild.md) | MSBuild proje dosyasının gerekli kök öğesi. |

## <a name="remarks"></a>Açıklamalar

 Bir `ProjectExtensions` MSBuild projesinde yalnızca bir öğe kullanılabilir.

## <a name="example"></a>Örnek

 Aşağıdaki kod örneği, bir `ProjectExtensions` öğede depolanan tümleşik geliştirme ortamından gelen bilgileri gösterir.

```xml
<ProjectExtensions>
    <VSIDE>
        <External>
            <!--
            Raw XML passed to the IDE by an external source
            -->
        </External>
    </VSIDE>
</ProjectExtensions>
```

## <a name="see-also"></a>Ayrıca bkz.

- [Proje dosyası şema başvurusu](../msbuild/msbuild-project-file-schema-reference.md)
- [Msbuild](../msbuild/msbuild.md)
