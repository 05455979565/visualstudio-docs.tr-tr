---
title: UsingTask öğesi (MSBuild) | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: msbuild
ms.topic: conceptual
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#UsingTask
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- UsingTask element [MSBuild]
- <UsingTask> element [MSBuild]
ms.assetid: 20247902-9446-4a1f-8253-5c7a17e4fe43
caps.latest.revision: 27
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: bf2882120f2e4c27e33b105585ba56261122055d
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "63445645"
---
# <a name="usingtask-element-msbuild"></a>UsingTask Öğesi (MSBuild)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Başvurulduğundan görev eşleyen bir [görev](../msbuild/task-element-msbuild.md) görev uygulamasını içeren derlemenin öğesi.  
  
 \<Proje >  
 \<UsingTask >  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
<UsingTask TaskName="TaskName"  
    AssemblyName = "AssemblyName"   
    TaskFactory = "ClassName"  
    Condition="'String A'=='String B'" />  
```  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`AssemblyName`|Her iki `AssemblyName` özniteliği veya `AssemblyFile` özniteliği gereklidir.<br /><br /> Yüklenecek derlemenin adı. `AssemblyName` Özniteliği güçlü adlandırma gerekli olmamasına rağmen tanımlayıcı adlı derlemeler kabul eder. Bu özniteliği kullanarak bir derlemeyi kullanarak yükleme için eşdeğer <xref:System.Reflection.Assembly.Load%2A> .NET yöntemi.<br /><br /> Bu öznitelik, kullanamazsınız `AssemblyFile` özniteliği kullanılır.|  
|`AssemblyFile`|Ya da `AssemblyName` veya `AssemblyFile` özniteliği gereklidir.<br /><br /> Derlemenin dosya yolu. Bu öznitelik, tam yol veya göreli yolları kabul eder. Göreli yolları proje dosyası veya hedefler dosyasının dizinine göreli olduğundan burada `UsingTask` öğesi bildirilir. Bu özniteliği kullanarak bir derlemeyi kullanarak yükleme için eşdeğer <xref:System.Reflection.Assembly.LoadFrom%2A> .NET yöntemi.<br /><br /> Bu öznitelik, kullanamazsınız `AssemblyName` özniteliği kullanılır.|  
|`TaskFactory`|İsteğe bağlı öznitelik.<br /><br /> Belirtilen bir örneğini oluşturmaktan sorumlu bir bütünleştirilmiş kod sınıfı belirtir `Task` adı.  Kullanıcı ayrıca belirtebilir bir `TaskBody` görev fabrikasını alır ve görev oluşturmak için kullandığı bir alt öğesi olarak. İçeriğini `TaskBody` için görev fabrikasını özgüdür.|  
|`TaskName`|Gerekli öznitelik.<br /><br /> Derlemeden başvurulacak görev adı. Belirsizlikler mümkün ise bu öznitelik her zaman tam bir ad belirtmeniz gerekir. Belirsizlikler varsa, MSBuild beklenmeyen sonuçlara neden bir rastgele eşleşme seçer.|  
|`Condition`|İsteğe bağlı öznitelik.<br /><br /> Değerlendirilecek koşul. Daha fazla bilgi için [koşullar](../msbuild/msbuild-conditions.md).|  
  
### <a name="child-elements"></a>Alt Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[ParameterGroup](../msbuild/parametergroup-element.md)|Oluşturulan bir görev üzerinde görünen parametre kümesi tarafından belirtilen `TaskFactory`.|  
|[Görev](../msbuild/task-element-msbuild.md)|Geçirilen verileri `TaskFactory` görev örneği oluşturmak için.|  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[Project](../msbuild/project-element-msbuild.md)|Gerekli kök öğesi bir [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)] proje dosyası.|  
  
## <a name="remarks"></a>Açıklamalar  
 Ortam değişkenleri, komut satırı özelliklerini ve proje düzeyi özellikleri herhangi bir yerde başvurulabilir `UsingTask` proje dosyasında açıkça ya da bir içeri aktarılan proje dosyası üzerinden görünürse öğesi. Daha fazla bilgi için [görevleri](../msbuild/msbuild-tasks.md).  
  
> [!NOTE]
> Proje düzeyi özellikleri varsa hiçbir anlamı `UsingTask` öğesi genel olarak MSBuild altyapı kayıtlı .tasks dosyaları birinden geliyor. Proje düzeyi özellikleri MSBuild'e genel değil.  
  
 MSBuild 4. 0'da, görevleri kullanarak .overridetask dosyalarından yüklenebilir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek nasıl kullanılacağını gösterir `UsingTask` öğesi ile bir `AssemblyName` özniteliği.  
  
```  
<UsingTask TaskName="MyTask" AssemblyName="My.Assembly" TaskFactory="MyTaskFactory">  
       <ParameterGroup>  
              <Parameter1 ParameterType="System.String" Required="False" Output="False"/>  
              <Parameter2 ParameterType="System.Int" Required="True" Output="False"/>  
              ...  
</ParameterGroup>  
       <TaskBody>  
      ... Task factory-specific data ...  
       </TaskBody>  
</UsingTask>  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek nasıl kullanılacağını gösterir `UsingTask` öğesi ile bir `AssemblyFile` özniteliği.  
  
```  
<UsingTask TaskName="Email"  
              AssemblyFile="c:\myTasks\myTask.dll" />  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görevleri](../msbuild/msbuild-tasks.md)   
 [Görev başvurusu](../msbuild/msbuild-task-reference.md)   
 [Proje Dosyası Şema Başvurusu](../msbuild/msbuild-project-file-schema-reference.md)
