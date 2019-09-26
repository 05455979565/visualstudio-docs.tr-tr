---
title: 'CA1502: Aşırı karmaşıklıktan kaçının'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- AvoidExcessiveComplexity
- CA1502
helpviewer_keywords:
- CA1502
- AvoidExcessiveComplexity
ms.assetid: d735454b-2f8f-47ce-907d-f7a5a5391221
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 4f26faf16cc8a9a8235596aef68e5af5c3b4401e
ms.sourcegitcommit: e98db44f3a33529b0ba188d24390efd09e548191
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/25/2019
ms.locfileid: "71253297"
---
# <a name="ca1502-avoid-excessive-complexity"></a>CA1502: Aşırı karmaşıklıktan kaçının

|||
|-|-|
|TypeName|AvoidExcessiveComplexity|
|CheckId|CA1502|
|Kategori|Microsoft. Bakımolmaması|
|Son değişiklik|Kırılmamış|

## <a name="cause"></a>Sebep

Bir yöntemin aşırı döngüsel karmaşıklığı vardır.

## <a name="rule-description"></a>Kural açıklaması

*Döngüsel karmaşıklığı* , koşullu dalların sayısı ve karmaşıklığı tarafından belirlenen yöntemi aracılığıyla, doğrusal olarak bağımsız yolların sayısını ölçer. Düşük bir döngüsel karmaşıklığı genellikle anlaşılması, test etmek ve sürdürmek kolay bir yöntemi gösterir. Döngüsel karmaşıklığı, yönteminin bir denetim akışı grafiğinden hesaplanır ve aşağıdaki gibi verilmiştir:

Döngüsel karmaşıklığı = kenar sayısı-düğüm sayısı + 1

*Düğüm* , bir mantık dal noktasını temsil eder ve bir *kenar* , düğümler arasındaki çizgiyi temsil eder.

Kural, döngüsel karmaşıklığı 25 ' ten fazla olduğunda bir ihlalin bildirir.

Kod ölçümleri hakkında daha fazla bilgi edinmek için [yönetilen kodun ölçü karmaşıklığı](../code-quality/code-metrics-values.md).

## <a name="how-to-fix-violations"></a>İhlalleri çözme

Bu kural ihlalini onarmak için, döngüsel karmaşıklığını azaltmak üzere yöntemi yeniden düzenleyin.

## <a name="when-to-suppress-warnings"></a>Uyarıların ne zaman bastırılamıyor

Karmaşıklığın kolayca azaltılamamasının ve yöntemin anlaşılması, test edilmesi ve bakımının kolay olması durumunda bu kuraldan bir uyarının gösterilmesinin güvenli olması güvenlidir. Özellikle, büyük `switch` (`Select` ın [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]) ifadesini içeren bir yöntem, dışlama için bir adaydır. Kod tabanını geliştirme döngüsündeki geç hale getirme veya daha önce sevk edilen koddaki çalışma zamanı davranışında beklenmedik bir değişikliği tanıtma riski, kodu yeniden düzenlemenin bakımlık avantajlarından yararlanabilir.

## <a name="how-cyclomatic-complexity-is-calculated"></a>Döngüsel karmaşıklığı nasıl hesaplanır

Döngüsel karmaşıklığı aşağıdaki 1 eklenerek hesaplanır:

- Dal sayısı ( `if`, `while`ve `do`gibi)

- `case` İçindeki deyim sayısı`switch`

## <a name="example"></a>Örnek

Aşağıdaki örneklerde, değişen döngüsel karmaşıklıkları olan Yöntemler gösterilmektedir.

**1 döngüsel karmaşıklığı**

[!code-cpp[FxCop.Maintainability.AvoidExcessiveComplexity#1](../code-quality/codesnippet/CPP/ca1502-avoid-excessive-complexity_1.cpp)]
[!code-vb[FxCop.Maintainability.AvoidExcessiveComplexity#1](../code-quality/codesnippet/VisualBasic/ca1502-avoid-excessive-complexity_1.vb)]
[!code-csharp[FxCop.Maintainability.AvoidExcessiveComplexity#1](../code-quality/codesnippet/CSharp/ca1502-avoid-excessive-complexity_1.cs)]

## <a name="example"></a>Örnek

**2 döngüsel karmaşıklığı**

[!code-cpp[FxCop.Maintainability.AvoidExcessiveComplexity#2](../code-quality/codesnippet/CPP/ca1502-avoid-excessive-complexity_2.cpp)]
[!code-vb[FxCop.Maintainability.AvoidExcessiveComplexity#2](../code-quality/codesnippet/VisualBasic/ca1502-avoid-excessive-complexity_2.vb)]
[!code-csharp[FxCop.Maintainability.AvoidExcessiveComplexity#2](../code-quality/codesnippet/CSharp/ca1502-avoid-excessive-complexity_2.cs)]

## <a name="example"></a>Örnek

**3 döngüsel karmaşıklığı**

[!code-cpp[FxCop.Maintainability.AvoidExcessiveComplexity#3](../code-quality/codesnippet/CPP/ca1502-avoid-excessive-complexity_3.cpp)]
[!code-vb[FxCop.Maintainability.AvoidExcessiveComplexity#3](../code-quality/codesnippet/VisualBasic/ca1502-avoid-excessive-complexity_3.vb)]
[!code-csharp[FxCop.Maintainability.AvoidExcessiveComplexity#3](../code-quality/codesnippet/CSharp/ca1502-avoid-excessive-complexity_3.cs)]

## <a name="example"></a>Örnek

**8 döngüsel karmaşıklığı**

[!code-cpp[FxCop.Maintainability.AvoidExcessiveComplexity#4](../code-quality/codesnippet/CPP/ca1502-avoid-excessive-complexity_4.cpp)]
[!code-vb[FxCop.Maintainability.AvoidExcessiveComplexity#4](../code-quality/codesnippet/VisualBasic/ca1502-avoid-excessive-complexity_4.vb)]
[!code-csharp[FxCop.Maintainability.AvoidExcessiveComplexity#4](../code-quality/codesnippet/CSharp/ca1502-avoid-excessive-complexity_4.cs)]

## <a name="related-rules"></a>İlgili kurallar

[CA1501 Aşırı devralmadan kaçının](../code-quality/ca1501-avoid-excessive-inheritance.md)

## <a name="see-also"></a>Ayrıca bkz.

- [Yönetilen Kodun Ölçüm Karmaşıklığı ve Bakımı](../code-quality/code-metrics-values.md)