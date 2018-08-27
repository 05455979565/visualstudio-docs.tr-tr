---
title: 'CA1813: korumasız özniteliklerden kaçının | Microsoft Docs'
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
- CA1813
- AvoidUnsealedAttributes
helpviewer_keywords:
- CA1813
- AvoidUnsealedAttributes
ms.assetid: f5e31b4c-9f8b-49e1-a2a8-bb5f1140729a
caps.latest.revision: 15
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: c422e4e261374d591acd0630f428f139b29cfcca
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/24/2018
ms.locfileid: "42903011"
---
# <a name="ca1813-avoid-unsealed-attributes"></a>CA1813: Korumasız özniteliklerden kaçının
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CA1813: korumasız özniteliklerden kaçının](https://docs.microsoft.com/visualstudio/code-quality/ca1813-avoid-unsealed-attributes).

|||
|-|-|
|TypeName|AvoidUnsealedAttributes|
|CheckId|CA1813|
|Kategori|Microsoft.Performance|
|Yeni Değişiklik|Yeni|

## <a name="cause"></a>Sebep
 Bir ortak türün devraldığı <xref:System.Attribute?displayProperty=fullName>soyut ve korumalı değil (`NotInheritable` Visual Basic'te).

## <a name="rule-description"></a>Kural Tanımı
 [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] Sınıf kitaplığı özel öznitelikleri almak için yöntemler sağlar. Varsayılan olarak, bu yöntemleri öznitelik devralma hiyerarşisinde arar; Örneğin <xref:System.Attribute.GetCustomAttribute%2A?displayProperty=fullName> belirtilen öznitelik türünün veya belirtilen öznitelik türü genişleten herhangi bir öznitelik türü arar. Öznitelik mühürleme kalıtım hiyerarşisi aracılığıyla aramayı ortadan kaldırır ve performansı artırabilir.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Bu kural ihlalini düzeltmek için öznitelik türünü mühürleyin veya soyut olun.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Bu kuraldan bir uyarıyı bastırmak güvenlidir. Yalnızca, bir öznitelik hiyerarşisi tanımlama ve öznitelik mühürleme ya da soyut yapmak varsa bunu yapmanız gerekir.

## <a name="example"></a>Örnek
 Aşağıdaki örnek, bu kural karşılayan özel bir öznitelik gösterir.

 [!code-csharp[FxCop.Performance.AttributesSealed#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Performance.AttributesSealed/cs/FxCop.Performance.AttributesSealed.cs#1)]
 [!code-vb[FxCop.Performance.AttributesSealed#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Performance.AttributesSealed/vb/FxCop.Performance.AttributesSealed.vb#1)]

## <a name="related-rules"></a>İlgili kuralları
 [CA1019: Öznitelik bağımsız değişkenleri için erişimcileri tanımlayın](../code-quality/ca1019-define-accessors-for-attribute-arguments.md)

 [CA1018: Öznitelikleri AttributeUsageAttribute ile işaretleyin](../code-quality/ca1018-mark-attributes-with-attributeusageattribute.md)

## <a name="see-also"></a>Ayrıca Bkz.
 [Öznitelikler](http://msdn.microsoft.com/library/ee0038ef-b247-4747-a650-3c5c5cd58d8b)



