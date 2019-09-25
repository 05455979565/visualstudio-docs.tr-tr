---
title: 'CA1505: Bakımı yapılamayan kodlardan kaçının'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- AvoidUnmaintainableCode
- CA1505
helpviewer_keywords:
- AvoidUnmaintainableCode
- CA1505
ms.assetid: 8292b268-5929-4221-b699-f9c414bcec5d
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: c3ba027ef2e663870d0af50bc6d2154133f7980c
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/24/2019
ms.locfileid: "71234539"
---
# <a name="ca1505-avoid-unmaintainable-code"></a>CA1505: Bakımı yapılamayan kodlardan kaçının

|||
|-|-|
|TypeName|AvoidUnmantainableCode|
|CheckId|CA1505|
|Kategori|Microsoft. Bakımolmaması|
|Son değişiklik|Kırılmamış|

## <a name="cause"></a>Sebep

Bir tür veya yöntemin düşük bakım dizin değeri vardır.

## <a name="rule-description"></a>Kural açıklaması

Bakımı dizini aşağıdaki ölçümler kullanılarak hesaplanır: kod satırları, program hacmi ve döngüsel karmaşıklığı. Program birimi, koddaki işleç ve işlenen sayısını temel alan bir tür veya yöntemin anlaşılmasından zorluk ölçüsüne ilişkin bir ölçüdür. Döngüsel karmaşıklığı, tür veya metodun yapısal karmaşıklığına yönelik bir ölçüdür. Kod ölçümleri hakkında daha fazla bilgi için [Ölçü karmaşıklığı ve yönetilen kodun bakımlığından](../code-quality/code-metrics-values.md)daha fazla bilgi edinebilirsiniz.

Düşük bakım dizini, bir tür veya yöntemin bakımını yapmak zor olabilir ve yeniden tasarımı için iyi bir aday olacaktır.

## <a name="how-to-fix-violations"></a>İhlalleri çözme

Bu ihlalin giderilmesi için tür veya yöntemi yeniden tasarlayıp daha küçük ve daha odaklanmış tür ya da yöntemlere bölmeyi deneyin.

## <a name="when-to-suppress-warnings"></a>Uyarıların ne zaman bastırılamıyor

Tür veya yöntem bölünemiyor veya büyük boyutuna karşın bakım yapılabilir olarak kabul edildiğinde, bu uyarıyı bastırın.

## <a name="see-also"></a>Ayrıca bkz.

- [Bakımsız uyarılar](../code-quality/maintainability-warnings.md)
- [Yönetilen kodun ölçüm karmaşıklığı ve bakımma](../code-quality/code-metrics-values.md)