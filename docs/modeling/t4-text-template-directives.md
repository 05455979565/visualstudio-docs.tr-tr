---
title: "T4 Metin şablonu yönergeleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.topic: article
helpviewer_keywords:
- text templates, import directive
- text templates, include directive
- text templates, assembly directive
- text templates, output directive
- text templates, directives
- text templates, template directive
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: 785cebbb2b0280dd5025eb945d0db776018e46ad
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2018
---
# <a name="t4-text-template-directives"></a>T4 Metin Şablonu Yönergeleri
Yönergeler metin şablonu dönüştürme motoru için yönergeler sağlar.  
  
 Yönergelerin sözdizimi aşağıdaki gibidir:  
  
```  
<#@ DirectiveName [AttributeName = "AttributeValue"] ... #>  
```  
  
 Tüm öznitelik değerleri çift tırnak işaretleri arasına alınmalıdır. Değerin kendisi tırnak işaretleri içeriyorsa, bunlardan \ karakteriyle kaçılmalıdır.  
  
 Yönergeler genellikle şablon dosyasında ya da eklenen dosyadaki ilk öğelerdir. Bunları bir kod bloğunun içine yerleştirmeniz değil `<#...#>`, ya da bir sınıf özelliği bloğu sonra `<#+...#>`.  
  
 [T4 Şablon Yönergesi](../modeling/t4-template-directive.md)  
 ```  
<#@ template [language="VB"] [hostspecific="true|TrueFromBase"] [debug="true"] [inherits="templateBaseClass"] [culture="code"] [compilerOptions="options"] [visibility="internal"] [linePragmas="false"] #>  
```  
  
 [T4 Parametre Yönergesi](../modeling/t4-parameter-directive.md)  
 ```  
<#@ parameter type="Full.TypeName" name="ParameterName" #>  
```  
  
 [T4 Çıkış Yönergesi](../modeling/t4-output-directive.md)  
 ```  
<#@ output extension=".fileNameExtension" [encoding="encoding"] #>  
```  
  
 [T4 Derleme Yönergesi](../modeling/t4-assembly-directive.md)  
 ```  
<#@ assembly name="[assembly strong name|assembly file name]" #>  
```  
  
 [T4 İçe Aktarma Yönergesi](../modeling/t4-import-directive.md)  
 ```  
<#@ import namespace="namespace" #>  
```  
  
 [T4 Include Yönergesi](../modeling/t4-include-directive.md)  
 ```  
<#@ include file="filePath" #>  
```  
  
 [T4 CleanUpBehavior yönergesi](../modeling/t4-cleanupbehavior-directive.md)  
 ```  
<#@ CleanupBehavior processor="T4VSHost" CleanupAfterProcessingtemplate="true" #>  
```  
  
 Ayrıca, kendi yönergelerinizi oluşturabilirsiniz. Daha fazla bilgi için bkz: [özel T4 metin şablonu yönerge işlemciler oluşturma](../modeling/creating-custom-t4-text-template-directive-processors.md). Görselleştirme ve Modelleme SDK'sını etki alanına özgü dil (DSL) oluşturmak için kullanıyorsanız, bir yönerge işlemcisi, DSL'nin bir parçası olarak oluşturulur.