---
title: 'CA2204: Değişmez değerler doğru yazılmalıdır | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- Literals should be spelled correctly
- CA2204
- LiteralsShouldBeSpelledCorrectly
helpviewer_keywords:
- CA2204
ms.assetid: b0bbcbb6-c92d-4c14-8ef7-9c8b38c791a6
caps.latest.revision: 21
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 575b10770f629a9ca97030f09e48622654307ee8
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42685158"
---
# <a name="ca2204-literals-should-be-spelled-correctly"></a>CA2204: Değişmez değerler doğru yazılmalıdır
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CA2204: değişmez değerler yazıldığından](https://docs.microsoft.com/visualstudio/code-quality/ca2204-literals-should-be-spelled-correctly).  
  
TypeName | LiteralsShouldBeSpelledCorrectly |  
| Checkıd | CA2204 |  
| Kategori | Microsoft.Usage|  
| Yeni değişiklik | Olmayan yeni |  
  
## <a name="cause"></a>Sebep  
 Bir sabit dizesi, bir parametre veya bir yerelleştirilmiş dize arar ve sabit dizesini gerektiren özelliği kullanılır. bir yöntem geçişleri Microsoft Yazım kitaplığı tarafından tanınmayan bir veya birkaç sözcük içerir.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Bu kural, bir parametre veya bir özellik için bir değer olarak geçirilen bir sabit dize denetler veya aşağıdaki durumlarda daha fazla doğrudur:  
  
-   <xref:System.ComponentModel.LocalizableAttribute> Özniteliği parametre ya da özelliğin true.  
  
-   Parametresi veya özellik adı "Metin", "İleti" veya "Başlık" içeriyor.  
  
-   "Value" veya "biçim" Console.Write veya Console.WriteLine yönteme geçirilen dize parametresi adıdır.  
  
 Bu kural sabit dizesini bileşik sözcüklerin kelimelere, ayrıştırır ve her kelimenin/belirtecin yazımını denetler. Ayrıştırma algoritma hakkında daha fazla bilgi için bkz. [CA1704: tanımlayıcılar yazıldığından](../code-quality/ca1704-identifiers-should-be-spelled-correctly.md).  
  
 Varsayılan olarak, yazım denetimcisi (TR) İngilizce sürümü kullanılır.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlalini düzeltmek için sözcük yazımını düzeltin ya da sözcüğü bir özel sözlüğüne ekleyin. Özel sözlükler kullanma hakkında daha fazla bilgi için bkz: [nasıl yapılır: kod çözümleme dizinini özelleştirme](../code-quality/how-to-customize-the-code-analysis-dictionary.md).  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan uyarıyı bastırmayın. Doğru bir şekilde yazılmış kelimeler yeni yazılım kitaplıkları için gereken öğrenme eğrisini azaltır.  
  
## <a name="related-rules"></a>İlgili kuralları  
 [CA1704: Tanımlayıcılar doğru yazılmalıdır](../code-quality/ca1704-identifiers-should-be-spelled-correctly.md)  
  
 [CA1703: Kaynak dizeler doğru yazılmalıdır](../code-quality/ca1703-resource-strings-should-be-spelled-correctly.md)



