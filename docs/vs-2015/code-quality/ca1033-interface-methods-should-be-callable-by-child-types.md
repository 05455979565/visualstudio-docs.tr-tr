---
title: 'CA1033: Arabirim yöntemleri alt türler tarafından çağırılabilir olmalıdır | Microsoft Docs'
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
- InterfaceMethodsShouldBeCallableByChildTypes
- CA1033
helpviewer_keywords:
- CA1033
- InterfaceMethodsShouldBeCallableByChildTypes
ms.assetid: 9f171497-a5e3-4769-a77b-7aed755b2662
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: a71462661c577bebbd76e7fa05aeca9d613c4c23
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/24/2018
ms.locfileid: "42902585"
---
# <a name="ca1033-interface-methods-should-be-callable-by-child-types"></a>CA1033: Arabirim yöntemleri alt türler tarafından çağırılabilir olmalıdır
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CA1033: arabirim yöntemleri alt türler tarafından çağırılabilir](https://docs.microsoft.com/visualstudio/code-quality/ca1033-interface-methods-should-be-callable-by-child-types).

|||
|-|-|
|TypeName|InterfaceMethodsShouldBeCallableByChildTypes|
|CheckId|CA1033|
|Kategori|Microsoft.Design|
|Yeni Değişiklik|Bölünemez|

## <a name="cause"></a>Sebep
 Ağzı açık dışarıdan görünen bir tür açık yöntem uygulaması ortak bir arabirim sağlar ve aynı ada sahip alternatif dışarıdan görünen bir yöntem sağlamaz.

## <a name="rule-description"></a>Kural Tanımı
 Açıkça bir ortak arabirim yöntemini uygulayan bir taban türü göz önünde bulundurun. Temel türünden türetilen bir tür devralınan arabirim yöntemi yalnızca geçerli örneğe bir başvuru erişebilirsiniz (`this` C#) arabirimine dönüştürün. Temel uygulama artık türetilmiş bir tür (açıkça) devralınan arabirim yöntemini yeniden uyguluyorsa, erişilebilir. Geçerli örnek başvuru çağrısıyla türetilen uygulamaya çağırır; Bu, özyineleme ve bir nihai yığın taşmasına neden olur.

 Bu kural açık bir uygulama için bir ihlali raporlamaz <xref:System.IDisposable.Dispose%2A?displayProperty=fullName> dışarıdan görünür olduğunda `Close()` veya `System.IDisposable.Dispose(Boolean)` yöntemi sağlanır.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Bu kural ihlalini düzeltmek için aynı işlevselliği kullanıma sunma ve türetilmiş türlere de görünür olan yeni bir yöntem uygulayın veya açıkça verilmemiş bir uygulama için değiştirin. Bir değişiklik kabul edilebilir ise, korumalı tür alternatiftir.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Dışarıdan görünen bir yöntem sağlanır, ancak açıkça uygulanan yöntem yerine farklı bir ad ile aynı işlevlere sahiptir, bu kuraldan bir uyarıyı bastırmak güvenlidir.

## <a name="example"></a>Örnek
 Aşağıdaki örnek, bir tür gösterir `ViolatingBase`, kural ve bir tür ihlal `FixedBase`, ihlalin düzeltme gösterir.

 [!code-csharp[FxCop.Design.ExplicitMethodImplementations#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.ExplicitMethodImplementations/cs/FxCop.Design.ExplicitMethodImplementations.cs#1)]

## <a name="see-also"></a>Ayrıca Bkz.
 [Arabirimler](http://msdn.microsoft.com/library/2feda177-ce11-432d-81b4-d50f5f35fd37)



