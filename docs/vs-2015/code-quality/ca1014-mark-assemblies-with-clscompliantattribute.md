---
title: 'CA1014: Derlemeleri CLSCompliantAttribute ile işaretle | Microsoft Docs'
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
- CA1014
- MarkAssembliesWithClsCompliant
helpviewer_keywords:
- CA1014
- MarkAssembliesWithClsCompliant
ms.assetid: 4fe57449-cf45-4745-bcd2-6345f1ed266d
caps.latest.revision: 20
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 6b3a91e3c73582fdaaaec8560cf9212363dc2a7c
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42684404"
---
# <a name="ca1014-mark-assemblies-with-clscompliantattribute"></a>CA1014: Derlemeleri CLSCompliantAttribute ile işaretleme
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CA1014: derlemeleri CLSCompliantAttribute ile işaretle](https://docs.microsoft.com/visualstudio/code-quality/ca1014-mark-assemblies-with-clscompliantattribute).  
  
TypeName | MarkAssembliesWithClsCompliant |  
| Checkıd | CA1014 |  
| Kategori | Microsoft.Design|  
| Yeni değişiklik | Bölünemez |  
  
## <a name="cause"></a>Sebep  
 Bir derleme olmayan <xref:System.CLSCompliantAttribute?displayProperty=fullName> özniteliğinin.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Ortak Dil Tanımlaması (CLS) ad kısıtlamalarını, veri türlerini ve karşıt programlama dillerini kullanırsa derlemelerin uyması zorunlu olan kuralları tanımlar. İyi tasarım ilkeleri tüm derlemeler CLS uyumluluğu ile açıkça belirtmek <xref:System.CLSCompliantAttribute>. Öznitelik bir derlemede mevcut değilse derleme uyumlu değil.  
  
 Bu türleri içeren veya uyumlu olmayan üyeler için CLS uyumlu bir derleme mümkündür.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlalini düzeltmek için özniteliği derlemeye ekleyin. Tüm derleme uyumsuz olarak işaretleme yerine hangi tür veya tür üyeleri uyumlu olmayan ve bu nedenle bu öğeleri işaretler belirlemeniz gerekir. Mümkünse, olabilecek en büyük hedef kitlesine derlemenizin tüm işlevleri erişebilmesi için uyumlu olmayan üyeler için CLS uyumlu bir alternatif sağlamanız gerekir.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan uyarıyı bastırmayın. Derleme uyumlu olmasını istemiyorsanız özniteliğini uygulayın ve değerini ayarlamak `false`.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir derlemeye gösterir <xref:System.CLSCompliantAttribute?displayProperty=fullName> CLS uyumlu bildiren özniteliği uygulandı.  
  
 [!code-cpp[FxCop.Design.AssembliesCls#1](../snippets/cpp/VS_Snippets_CodeAnalysis/FxCop.Design.AssembliesCls/cpp/FxCop.Design.AssembliesCls.cpp#1)]
 [!code-csharp[FxCop.Design.AssembliesCls#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.AssembliesCls/cs/FxCop.Design.AssembliesCls.cs#1)]
 [!code-vb[FxCop.Design.AssembliesCls#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.AssembliesCls/vb/FxCop.Design.AssembliesCls.vb#1)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.CLSCompliantAttribute?displayProperty=fullName>   
 [Dil Bağımsızlığı ve Dilden Bağımsız Bileşenler](http://msdn.microsoft.com/library/4f0b77d0-4844-464f-af73-6e06bedeafc6)



