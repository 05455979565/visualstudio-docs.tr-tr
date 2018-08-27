---
title: 'CA1036: Karşılaştırılabilir türlerde yöntemleri geçersiz kılma | Microsoft Docs'
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
- CA1036
- OverrideMethodsOnComparableTypes
helpviewer_keywords:
- OverrideMethodsOnComparableTypes
- CA1036
ms.assetid: 2329f844-4cb8-426d-bee2-cd065d1346d0
caps.latest.revision: 23
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 906ee4c3e5300f04b5627c7b3aa19ba7950f3239
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/24/2018
ms.locfileid: "42900767"
---
# <a name="ca1036-override-methods-on-comparable-types"></a>CA1036: Karşılaştırılabilir türlerde geçersiz kılma yöntemleri
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CA1036: karşılaştırılabilir türlerde yöntemleri geçersiz kılmak](https://docs.microsoft.com/visualstudio/code-quality/ca1036-override-methods-on-comparable-types).

|||
|-|-|
|TypeName|OverrideMethodsOnComparableTypes|
|CheckId|CA1036|
|Kategori|Microsoft.Design|
|Yeni Değişiklik|Bölünemez|

## <a name="cause"></a>Sebep
 Ortak veya korumalı tür uygulayan <xref:System.IComparable?displayProperty=fullName> arabirim ve geçersiz <xref:System.Object.Equals%2A?displayProperty=fullName> veya eşitlik, eşitsizlik durumu olabilir, daha küçük veya büyük özel dil işleciyle aşırı yüklenebilir değil. Türü arabiriminin bir uygulamasını devralırsa kuralı ihlal raporlamaz.

## <a name="rule-description"></a>Kural Tanımı
 Özel sıralama düzenini tanımlamak türleri uygulayan <xref:System.IComparable> arabirimi. <xref:System.IComparable.CompareTo%2A> Yöntem türü iki örneği için doğru sıralama düzenini belirten bir tamsayı değeri döndürür. Bu kural, bir sıralama düzeni kümesi türlerini tanımlar; Bu, olağan anlamını eşitlik, eşitsizlik durumu olabilir, daha az daha küçük ve büyük geçerli değildir, anlamına gelir. Bir uygulamasını sağlaması zaman <xref:System.IComparable>, genellikle gerekir ayrıca geçersiz <xref:System.Object.Equals%2A> ile tutarlı olan değerler döndürür, böylece <xref:System.IComparable.CompareTo%2A>. Kılarsanız <xref:System.Object.Equals%2A> ve Kodladığınız İşleç aşırı yüklemeleri destekler bir dilde tutarlı işleçleri de sağlamalıdır <xref:System.Object.Equals%2A>.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Bu kural ihlalini düzeltmek için geçersiz kılın <xref:System.Object.Equals%2A>. İşleç aşırı yüklemesi programlama dilini destekler, aşağıdaki işleçleri sağlayın:

-   op_Equality

-   op_Inequality

-   op_LessThan

-   op_GreaterThan

 C# içinde bu işleçler temsil etmek için kullanılan belirteçleri aşağıda belirtilmiştir: ==,! =, \<, ve >.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Eksik işleçleriyle ihlaline neden olur ve Visual Basic .NET ile olduğu gibi İşleç aşırı yüklemesi, programlama diliniz desteklemiyor olduğunda bu kuraldan bir uyarıyı bastırmak güvenlidir. Op_Equality işleçleri uygulamaya karar verirseniz, uygulama bağlamında mantıklı dışında eşitlik işleçlerde tetiklendiğinde için bu kuraldan bir uyarıyı bastırmak güvenlidir. Her zaman ancak op_Equality gerekir ve Object.equals'ı geçersiz kılarsanız == işleci.

## <a name="example"></a>Örnek
 Aşağıdaki örnek, doğru uygulayan bir tür içerir <xref:System.IComparable>. Kod açıklamaları için ilgili çeşitli kuralları karşılayan yöntemleri tanımlamak <xref:System.Object.Equals%2A> ve <xref:System.IComparable> arabirimi.

 [!code-csharp[FxCop.Design.IComparable#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.IComparable/cs/FxCop.Design.IComparable.cs#1)]

## <a name="example"></a>Örnek
 Aşağıdaki uygulama davranışını testleri <xref:System.IComparable> daha önce gösterilen uygulama.

 [!code-csharp[FxCop.Design.TestIComparable#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.TestIComparable/cs/FxCop.Design.TestIComparable.cs#1)]

## <a name="see-also"></a>Ayrıca Bkz.
 <xref:System.IComparable?displayProperty=fullName><xref:System.Object.Equals%2A?displayProperty=fullName>
 [Eşitlik İşleçleri](http://msdn.microsoft.com/library/bc496a91-fefb-4ce0-ab4c-61f09964119a)



