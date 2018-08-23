---
title: 'CA1011: temel türleri parametre geçirmeyi düşünün. | Microsoft Docs'
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
- ConsiderPassingBaseTypesAsParameters
- CA1011
helpviewer_keywords:
- CA1011
- ConsiderPassingBaseTypesAsParameters
ms.assetid: ce1e1241-dcf4-419b-9363-1d5bc4989279
caps.latest.revision: 20
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: aa1cfd44b80757d0cf24dbab16b5e8f982eca551
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42631019"
---
# <a name="ca1011-consider-passing-base-types-as-parameters"></a>CA1011: Temel türleri parametre olarak geçirmeyi düşünün
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CA1011: temel türleri parametre olarak geçirmeyi düşünün](https://docs.microsoft.com/visualstudio/code-quality/ca1011-consider-passing-base-types-as-parameters).  
  
TypeName | ConsiderPassingBaseTypesAsParameters |  
| Checkıd | CA1011 |  
| Kategori | Microsoft.Design|  
| Yeni değişiklik | Bozucu |  
  
## <a name="cause"></a>Sebep  
 Yalnızca parametrenin temel türün üyeleri yöntemini çağırır ve yöntem bildiriminde türetilmiş bir tür bir biçimsel parametre içerir.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Temel tür yöntem bildiriminde parametre olarak belirtildiğinde temel türünden türetilen herhangi bir tür yöntemine karşılık gelen bağımsız değişken olarak geçirilebilir. Bağımsız değişken bir yöntem gövdesi içinde kullanıldığında, yürütülen belirli yöntem bağımsız değişkenin türüne bağlıdır. Türetilmiş tür tarafından sağlanan ek işlevler gerekmiyorsa, temel tür kullanımı yöntemi daha geniş kullanımını sağlar.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlalini düzeltmek için kendi temel türü için parametre türünü değiştirin.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan bir uyarıyı bastırmak güvenlidir  
  
-   yöntem türetilmiş türü tarafından sağlanan belirli işlevleri gerektiriyorsa  
  
     \- veya -  
  
-   yalnızca türetilmiş tür ya da daha fazla türetilmiş bir türü, yönteme geçirilen zorlamak için.  
  
 Bu durumlarda, kod derleyici ve çalışma zamanı tarafından sağlanan güçlü tür denetimi nedeniyle daha sağlam olacaktır.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek bir yöntemi gösterir `ManipulateFileStream`, yalnızca ile kullanılabilecek bir <xref:System.IO.FileStream> bu kuralı ihlal nesnesidir. İkinci bir yöntem `ManipulateAnyStream`, kural değiştirerek karşılayan <xref:System.IO.FileStream> parametresi kullanılarak bir <xref:System.IO.Stream>.  
  
 [!code-cpp[FxCop.Design.ConsiderPassingBaseTypes#1](../snippets/cpp/VS_Snippets_CodeAnalysis/FxCop.Design.ConsiderPassingBaseTypes/cpp/FxCop.Design.ConsiderPassingBaseTypes.cpp#1)]
 [!code-csharp[FxCop.Design.ConsiderPassingBaseTypes#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.ConsiderPassingBaseTypes/cs/FxCop.Design.ConsiderPassingBaseTypes.cs#1)]
 [!code-vb[FxCop.Design.ConsiderPassingBaseTypes#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.ConsiderPassingBaseTypes/vb/FxCop.Design.ConsiderPassingBaseTypes.vb#1)]  
  
## <a name="related-rules"></a>İlgili kuralları  
 [CA1059: Üyeler belli somut türleri göstermemelidir](../code-quality/ca1059-members-should-not-expose-certain-concrete-types.md)



