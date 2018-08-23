---
title: 'CA2104: salt okunur kesilebilir başvuru türleri bildirmeyin | Microsoft Docs'
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
- DoNotDeclareReadOnlyMutableReferenceTypes
- CA2104
helpviewer_keywords:
- CA2104
- DoNotDeclareReadOnlyMutableReferenceTypes
ms.assetid: 81b83ee5-4db5-4be0-9f8d-90b53894ec3b
caps.latest.revision: 20
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 88e26ec1ba4acdfad0b4545f07dd6024d8242a2a
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42687462"
---
# <a name="ca2104-do-not-declare-read-only-mutable-reference-types"></a>CA2104: Salt okunur kesilebilir başvuru türleri bildirmeyin
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CA2104: salt okunur kesilebilir başvuru türleri bildirmeyin](https://docs.microsoft.com/visualstudio/code-quality/ca2104-do-not-declare-read-only-mutable-reference-types).  
  
TypeName | DoNotDeclareReadOnlyMutableReferenceTypes |  
| Checkıd | CA2104 |  
| Kategori | Microsoft.Security|  
| Yeni değişiklik | Bölünemez |  
  
## <a name="cause"></a>Sebep  
 Dışarıdan görünen bir tür, kesilebilir başvuru türü olan dışarıdan görünen bir salt okunur alan içerir.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Kesilebilir tür, örnek verileri değiştirilebilen bir türdür. <xref:System.Text.StringBuilder?displayProperty=fullName> Sınıfı kesilebilir başvuru türünde bir örnek verilmiştir. Sınıfının bir örneğini değerini değiştirebilir üye içeriyor. Bir değişmez başvuru türü örneğidir <xref:System.String?displayProperty=fullName> sınıfı. Değeri, örneği oluşturulduktan sonra hiçbir zaman değiştirebilirsiniz.  
  
 Salt okunur değiştiricisi ([salt okunur](http://msdn.microsoft.com/library/2f8081f6-0de2-4903-898d-99696c48d2f4) C# ' ta, [salt okunur](http://msdn.microsoft.com/library/e868185d-6142-4359-a2fd-a7965cadfce8) içinde [!INCLUDE[vbprvb](../includes/vbprvb-md.md)], ve [const](http://msdn.microsoft.com/library/b21c0271-1ad0-40a0-b21c-5e812bba0318) C++'ta) bir başvuru türü üzerinde alan (c++ işaretçisi) alanın engeller farklı bir başvuru türü örneği tarafından değiştirildi. Ancak, değiştiricisi başvuru türünü değiştirme alanının örnek verilerini engellemez.  
  
 Salt okunur dizi alanları bu kurala ancak bunun yerine ihlalini neden [CA2105: dizi alanları okunamadı yalnızca](../code-quality/ca2105-array-fields-should-not-be-read-only.md) kuralı.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlalini düzeltmek için salt okunur değiştiricisi kaldırın veya bir değişiklik kabul edilebilir ise, alan bir sabit türüyle değiştirin.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Alan türü sabit ise bu kuraldan bir uyarıyı bastırmak güvenlidir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bu kural ihlalini neden olan bir alan bildirimi gösterir.  
  
 [!code-cpp[FxCop.Security.MutableReferenceTypes#1](../snippets/cpp/VS_Snippets_CodeAnalysis/FxCop.Security.MutableReferenceTypes/cpp/FxCop.Security.MutableReferenceTypes.cpp#1)]
 [!code-csharp[FxCop.Security.MutableReferenceTypes#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Security.MutableReferenceTypes/cs/FxCop.Security.MutableReferenceTypes.cs#1)]
 [!code-vb[FxCop.Security.MutableReferenceTypes#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Security.MutableReferenceTypes/vb/FxCop.Security.MutableReferenceTypes.vb#1)]



