---
title: Artımlı derlemeleri | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: msbuild
ms.topic: conceptual
helpviewer_keywords:
- msbuild, incremental builds
ms.assetid: 325e28c7-4838-4e3f-b672-4586adc7500c
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: eb11467d8d59e7af11741d7719da2858ac1a784c
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "68192888"
---
# <a name="incremental-builds"></a>Artımlı Derlemeler
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Artımlı derlemeleri en iyi duruma getirilir ve böylece göre ilgili giriş dosyaları güncel olduğundan Çıkış dosyalarını olan hedefleri yürütülmez derlemeleri ' dir. Hedef öğe olabilir bir `Inputs` hangi hedef öğeler gösteren özniteliği, giriş olarak bekliyor ve bir `Outputs` ne üretir çıktı olarak öğelerini gösteren özniteliği. MSBuild, bu öznitelik değerleri, 1-1 eşlemesini bulmayı dener. 1-1 eşleme varsa, her giriş öğesinin zaman damgası için çıkış karşılığı zaman damgası MSBuild karşılaştırır. 1-1 eşleme sahip Çıkış dosyalarını, tüm giriş dosyaları için karşılaştırılır. Kendi çıktı dosyasını aynı yaş ise güncel veya kendi girdi dosyası veya dosya daha yeni bir öğe olarak kabul edilir.  
  
 Tüm çıkış öğeleri güncel olduğundan, MSBuild hedefini atlar. Bu *Artımlı derleme* hedefinin derleme hızını önemli ölçüde artırabilir. Yalnızca bazı dosyalar güncel olduğundan MSBuild hedef yürütür, ancak güncel öğeleri atlar ve böylece tüm öğeleri güncel getirir. Bu olarak bilinen bir *kısmi Artımlı derleme*.  
  
 1-1 eşlemeleri genellikle öğesi dönüşümlere göre oluşturulur. Daha fazla bilgi için [dönüştüren](../msbuild/msbuild-transforms.md).  
  
 Aşağıdaki hedef göz önünde bulundurun.  
  
```  
<Target Name="Backup" Inputs="@(Compile)"   
    Outputs="@(Compile->'$(BackupFolder)%(Identity).bak')">  
    <Copy SourceFiles="@(Compile)" DestinationFiles=  
        "@(Compile->'$(BackupFolder)%(Identity).bak')" />  
</Target>  
```  
  
 Tarafından temsil edilen dosya kümesini `Compile` öğesi türü, bir yedekleme dizinine kopyalanır. Yedekleme dosyalarının, .bak dosya adı uzantısına sahip. Dosyaları tarafından temsil edilen varsa `Compile` öğesi türü veya karşılık gelen yedekleme dosyalarını değil silindi veya sonraki derlemelerde yedekleme hedef atlandı sonra yedekleme hedef çalıştırdıktan sonra değiştirilmiş.  
  
## <a name="output-inference"></a>Çıkış çıkarımı  
 MSBuild karşılaştırır `Inputs` ve `Outputs` hedef yürütmek olup olmadığını belirlemek için bir hedef öznitelikleri. İdeal olarak, ilişkili hedefleri yürütülür olup olmadığını Artımlı derleme tamamlandıktan sonra var olan dosya kümesini aynı kalmalıdır. Derleme özellikleri ve oluşturulan veya görevler tarafından değiştirilen öğeleri etkileyebileceğinden, MSBuild bile bunları etkiler hedef atlandı değerlerine Infer gerekir. Bu olarak bilinir *çıkış çıkarımı*.  
  
 Üç durum vardır:  
  
- Hedef sahip bir `Condition` değerlendiren özniteliği `false`. Bu durumda, hedef değil çalıştırılan ve yapı üzerinde hiçbir etkisi olmaz.  
  
- Hedef, güncel olmayan çıkışlar vardır ve bunları güncel duruma getirmek için çalıştırın.  
  
- Hedef, güncel olmayan çıkış sahiptir ve atlanır. MSBuild hedef değerlendirir ve hedef çalışsaydı gibi öğeleri ve özellikleri için değişiklikleri yapar.  
  
  Artımlı derleme desteklemek için görevleri emin olmanız gerekir `TaskParameter` öznitelik herhangi bir değerini `Output` öğesi için bir görev giriş parametresi eşittir. Bazı örnekler şunlardır:  
  
```  
<CreateProperty Value="123">  
    <Output PropertyName="Easy" TaskParameter="Value" />  
</CreateProperty>  
```  
  
 Bu özelliği olup olmadığını hedef yürütülen atlandı veya değer "123" olan bir kolayca oluşturur.  
  
```  
<CreateItem Include="a.cs;b.cs">  
    <Output ItemName="Simple" TaskParameter="Include" />  
</CreateItem>  
```  
  
 Bu, hedef yürütülen veya atlandı olup olmadığını olan iki öğe, "a.cs" ve "b.cs" basit, öğe türü oluşturur.  
  
 MSBuild 3. 5'başlayarak, çıkış çıkarım, bir hedef öğe ve özelliği grupları otomatik olarak gerçekleştirilir. `CreateItem` Görevler, bir hedef olarak gerekli değildir ve bundan kaçınılmalıdır. Ayrıca, `CreateProperty` görevleri yalnızca bir hedef gerçekleştirilip gerçekleştirilmediğini belirlemek için bir hedef olarak kullanılmalıdır.  
  
## <a name="determining-whether-a-target-has-been-run"></a>Bir hedef çalıştırılıp çalıştırılmadığını belirleyen  
 Çıkış çıkarımı nedeniyle eklemeniz gerekir. bir `CreateProperty` hedef gerçekleştirilip gerçekleştirilmediğini belirlemek için özellikleri ve öğeleri incelemek için bir hedef için görev. Ekleme `CreateProperty` Görev hedef ve ona bir `Output` öğesi olan `TaskParameter` "ValueSetByTask" olduğu.  
  
```  
<CreateProperty Value="true">  
    <Output TaskParameter="ValueSetByTask" PropertyName="CompileRan" />  
</CreateProperty>  
```  
  
 Bu özellik CompileRan oluşturur ve değer verir `true`, ancak yalnızca hedef yürütülür. Hedef atladıysanız CompileRan oluşturulmaz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hedefler](../msbuild/msbuild-targets.md)
