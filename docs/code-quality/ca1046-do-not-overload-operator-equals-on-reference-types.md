---
title: 'CA1046: Eşittir işlecini başvuru türlerinde aşırı yüklemeyin'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- DoNotOverloadOperatorEqualsOnReferenceTypes
- CA1046
helpviewer_keywords:
- CA1046
- DoNotOverloadOperatorEqualsOnReferenceTypes
ms.assetid: c1dfbfe3-63f9-4005-a81a-890427b77e79
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: d765bfda87fe184256304b86f145f4f02adb7db6
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68922638"
---
# <a name="ca1046-do-not-overload-operator-equals-on-reference-types"></a>CA1046: Eşittir işlecini başvuru türlerinde aşırı yüklemeyin

|||
|-|-|
|TypeName|DoNotOverloadOperatorEqualsOnReferenceTypes|
|CheckId|CA1046|
|Kategori|Microsoft.Design|
|Yeni Değişiklik|Yeni|

## <a name="cause"></a>Sebep
Ortak veya iç içe ortak başvuru türü eşitlik işlecini aşırı yükler.

## <a name="rule-description"></a>Kural açıklaması
Başvuru türleri için, varsayılan eşitlik işleci neredeyse her zaman doğrudur. Varsayılan olarak, yalnızca aynı nesneye gelirseniz iki başvuru eşit olur.

## <a name="how-to-fix-violations"></a>İhlalleri çözme
Bu kural ihlalini onarmak için eşitlik işlecinin uygulamasını kaldırın.

## <a name="when-to-suppress-warnings"></a>Uyarıların ne zaman bastırılamıyor
Başvuru türü yerleşik bir değer türü gibi davrandığı zaman, bu kuraldan bir uyarının bastırması güvenlidir. Türün örneklerine ekleme veya çıkarma yapmak için anlamlı ise, eşitlik işlecinin uygulanması ve ihlalin görünmemesi için büyük olasılıkla doğrudur.

## <a name="example"></a>Örnek
Aşağıdaki örnek, iki başvuruyu karşılaştırırken varsayılan davranışı gösterir.

[!code-csharp[FxCop.Design.RefTypesNoEqualityOp#1](../code-quality/codesnippet/CSharp/ca1046-do-not-overload-operator-equals-on-reference-types_1.cs)]

## <a name="example"></a>Örnek

Aşağıdaki uygulama bazı başvuruları karşılaştırır.

[!code-csharp[FxCop.Design.TestRefTypesNoEqualityOp#1](../code-quality/codesnippet/CSharp/ca1046-do-not-overload-operator-equals-on-reference-types_2.cs)]

Bu örnek aşağıdaki çıktıyı üretir:

```txt
a = new (2,2) and b = new (2,2) are equal? No
c and a are equal? Yes
b and a are == ? No
c and a are == ? Yes
```

## <a name="related-rules"></a>İlgili kurallar

[CA1013 Ekleme ve çıkarmayı aşırı yükleme sırasında eşittir işleci](../code-quality/ca1013-overload-operator-equals-on-overloading-add-and-subtract.md)

## <a name="see-also"></a>Ayrıca bkz.

- <xref:System.Object.Equals%2A?displayProperty=fullName>
- [Eşitlik İşleçleri](/dotnet/standard/design-guidelines/equality-operators)