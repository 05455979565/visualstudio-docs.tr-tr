---
title: 'CA1034: İç içe türler görünür olmamalıdır'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- NestedTypesShouldNotBeVisible
- CA1034
helpviewer_keywords:
- NestedTypesShouldNotBeVisible
- CA1034
ms.assetid: e9789a2c-2540-42a1-8705-ae7104011194
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: a086ad80bd13fb18f866769db34d72cae3e67496
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68922871"
---
# <a name="ca1034-nested-types-should-not-be-visible"></a>CA1034: İç içe türler görünür olmamalıdır

|||
|-|-|
|TypeName|NestedTypesShouldNotBeVisible|
|CheckId|CA1034|
|Kategori|Microsoft.Design|
|Yeni Değişiklik|Yeni|

## <a name="cause"></a>Sebep

Dışarıdan görünen bir tür, dışarıdan görünen bir tür bildirimi içerir. İç içe geçmiş numaralandırmalar ve korumalı türler bu kuraldan muaf tutulur.

## <a name="rule-description"></a>Kural açıklaması
İç içe bir tür, başka bir türün kapsamı içinde belirtilen bir türdür. İç içe türler, kapsayan türün özel uygulama ayrıntılarını kapsüllemek için faydalıdır. Bu amaçla kullanılan, iç içe türün dışarıdan görünür olmaması gerekir.

Mantıksal gruplandırma için dışarıdan görünebilir iç içe türler kullanmayın veya ad çakışmalarını önleyin; Bunun yerine ad alanlarını kullanın.

İç içe türler, bazı programcılar açıkça anlaşılmayan üye erişilebilirliği kavramını içerir.

Korumalı türler, Gelişmiş özelleştirme senaryolarında alt sınıflarda ve iç içe türler için kullanılabilir.

## <a name="how-to-fix-violations"></a>İhlalleri çözme
İç içe geçmiş türün dışarıdan görünür olmasını düşünmüyorsanız, türün erişilebilirliğini değiştirin. Aksi takdirde, iç içe türü üst öğesinden kaldırın. İç içe geçme amacı iç içe türü sınıflandırıdıysanız, bunun yerine hiyerarşiyi oluşturmak için bir ad alanı kullanın.

## <a name="when-to-suppress-warnings"></a>Uyarıların ne zaman bastırılamıyor
Bu kuraldan uyarıyı bastırmayın.

## <a name="example"></a>Örnek
Aşağıdaki örnek, kuralı ihlal eden bir türü gösterir.

[!code-cpp[FxCop.Design.NestedTypes#1](../code-quality/codesnippet/CPP/ca1034-nested-types-should-not-be-visible_1.cpp)]
[!code-csharp[FxCop.Design.NestedTypes#1](../code-quality/codesnippet/CSharp/ca1034-nested-types-should-not-be-visible_1.cs)]
[!code-vb[FxCop.Design.NestedTypes#1](../code-quality/codesnippet/VisualBasic/ca1034-nested-types-should-not-be-visible_1.vb)]