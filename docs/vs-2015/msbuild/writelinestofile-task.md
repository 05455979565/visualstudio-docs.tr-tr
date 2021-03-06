---
title: WriteLinesToFile görevi | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: msbuild
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#WriteLinesToFile
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- WriteLinesToFile task [MSBuild]
- MSBuild, WriteLinesToFile task
ms.assetid: 9c8862ac-8da5-4437-9430-ecc30421f1c9
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: f530648c7dd772fb60148f4d755d4a4ffb420cbb
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62419965"
---
# <a name="writelinestofile-task"></a>WriteLinesToFile Görevi
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Belirtilen öğe yolları, belirtilen bir metin dosyasına yazar.  
  
## <a name="task-parameters"></a>Görev parametreleri  
 Parametreleri aşağıdaki tabloda açıklanmıştır `WriteLinestoFile` görev.  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`File`|Gerekli <xref:Microsoft.Build.Framework.ITaskItem> parametresi.<br /><br /> Öğeleri yazmak için dosyayı belirtir.|  
|`Lines`|İsteğe bağlı <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametresi.<br /><br /> Dosyaya yazmak için öğeleri belirtir.|  
|`Overwrite`|İsteğe bağlı `Boolean` parametresi.<br /><br /> Varsa `true`, görev dosyasındaki varolan içeriğin üzerine yazar.|  
|`Encoding`|İsteğe bağlı `String` parametresi.<br /><br /> Örneğin, "Unicode" kodlama karakter seçer.  Ayrıca bkz: <xref:System.Text.Encoding>.|  
  
## <a name="remarks"></a>Açıklamalar  
 Varsa `Overwrite` olduğu `true`, yeni bir dosya oluşturur, içeriği dosyaya yazın ve ardından dosyayı kapatır. Hedef dosya zaten varsa üzerine yazılır. Varsa `Overwrite` olduğu `false`, dosyaya içerik ekler, hedef dosya zaten yoksa, oluşturma.  
  
 Yukarıda listelenen parametrelerin yanı sıra, bu görev parametreleri devralan <xref:Microsoft.Build.Tasks.TaskExtension> kendisi sınıfının devraldığı <xref:Microsoft.Build.Utilities.Task> sınıfı. Bu ek parametrelerin ve Tanımlamaların bir listesi için bkz. [TaskExtension temel sınıfı](../msbuild/taskextension-base-class.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte `WriteLinesToFile` yazma yollarının öğeler için görev `MyItems` öğesi tarafından belirtilen dosya koleksiyonuna `MyTextFile` öğe koleksiyonu.  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  
    <ItemGroup>  
        <MyTextFile Include="Items.txt"/>  
        <MyItems Include="*.cs"/>  
    </ItemGroup>  
  
    <Target Name="WriteToFile">  
        <WriteLinesToFile  
            File="@(MyTextFile)"  
            Lines="@(MyItems)"  
            Overwrite="true"  
            Encoding="Unicode"/>  
    </Target>  
  
</Project>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görevleri](../msbuild/msbuild-tasks.md)   
 [Görev Başvurusu](../msbuild/msbuild-task-reference.md)
