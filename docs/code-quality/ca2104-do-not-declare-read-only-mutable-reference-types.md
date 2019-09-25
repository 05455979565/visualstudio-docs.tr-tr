---
title: 'CA2104: Salt okunurdur kesilebilir başvuru türleri bildirmeyin'
ms.date: 11/01/2018
ms.topic: reference
f1_keywords:
- DoNotDeclareReadOnlyMutableReferenceTypes
- CA2104
helpviewer_keywords:
- CA2104
- DoNotDeclareReadOnlyMutableReferenceTypes
ms.assetid: 81b83ee5-4db5-4be0-9f8d-90b53894ec3b
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 8f4f165b4b00f46b478907c9affca672b4c7f113
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/24/2019
ms.locfileid: "71232962"
---
# <a name="ca2104-do-not-declare-read-only-mutable-reference-types"></a>CA2104: Salt okunur kesilebilir başvuru türleri bildirmeyin

|||
|-|-|
|TypeName|DoNotDeclareReadOnlyMutableReferenceTypes|
|CheckId|CA2104|
|Kategori|Microsoft.Security|
|Son değişiklik|Kırılmamış|

> [!NOTE]
> Rule CA2104 artık kullanılmıyor ve sonraki bir Visual Studio sürümünde kaldırılacak. Bir türün gerçek dengeszliği belirlenmesi için gerekli olan karmaşık analizler nedeniyle, bir [çözümleyici](roslyn-analyzers-overview.md) olarak uygulanmaz.

## <a name="cause"></a>Sebep

Dışarıdan görünen bir tür, kesilebilir başvuru türü olan dışarıdan görünen bir salt okunur alan içerir.

## <a name="rule-description"></a>Kural açıklaması

Kesilebilir tür, örnek verileri değiştirilebilen bir türdür. <xref:System.Text.StringBuilder?displayProperty=fullName> Sınıfı kesilebilir başvuru türüne bir örnektir. Bu, sınıfının bir örneğinin değerini değiştirecek üyeleri içerir. Değişmez bir başvuru türü örneği <xref:System.String?displayProperty=fullName> sınıf olur. Örneği oluşturulduktan sonra, değeri hiçbir şekilde değişiklik yapabilir.

Bir başvuru türü alanı (veya içindeki C++işaretçi C#) üzerinde salt okunur değiştirici ([ReadOnly](/dotnet/csharp/language-reference/keywords/readonly) , C++ [ReadOnly](/dotnet/visual-basic/language-reference/modifiers/readonly) Visual Basic ve [const](/cpp/cpp/const-cpp) ), alanın farklı bir başvuru türü örneğiyle değiştirilmesini engeller. Ancak, değiştirici alanın örnek verilerinin başvuru türü aracılığıyla değiştirilmesini engellemez.

Bu kural yanlışlıkla, değişmez değer olan bir tür için ihlalin bir ihlal gösterebilir. Bu durumda, uyarının bastırmasının güvenli olması gerekir.

Salt okuma dizisi alanları bu kuraldan muaf tutulur, [bunun yerine CA2105 ihlaline neden olur: Dizi alanları salt okuma](../code-quality/ca2105-array-fields-should-not-be-read-only.md) kuralı olmamalıdır.

## <a name="how-to-fix-violations"></a>İhlalleri çözme

Bu kural ihlalini onarmak için, salt okunurdur değiştiricisini kaldırın veya bir son değişiklik kabul edilebilir ise, alanı değişmez bir türle değiştirin.

## <a name="when-to-suppress-warnings"></a>Uyarıların ne zaman bastırılamıyor

Alan türü sabit ise bu kuraldan bir uyarıyı bastırmak güvenlidir.

## <a name="example"></a>Örnek

Aşağıdaki örnek, bu kuralın ihlaline neden olan bir alan bildirimini gösterir:

[!code-cpp[FxCop.Security.MutableReferenceTypes#1](../code-quality/codesnippet/CPP/ca2104-do-not-declare-read-only-mutable-reference-types_1.cpp)]
[!code-csharp[FxCop.Security.MutableReferenceTypes#1](../code-quality/codesnippet/CSharp/ca2104-do-not-declare-read-only-mutable-reference-types_1.cs)]
[!code-vb[FxCop.Security.MutableReferenceTypes#1](../code-quality/codesnippet/VisualBasic/ca2104-do-not-declare-read-only-mutable-reference-types_1.vb)]