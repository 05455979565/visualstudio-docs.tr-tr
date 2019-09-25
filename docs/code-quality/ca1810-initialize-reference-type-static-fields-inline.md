---
title: 'CA1810: Başvuru türü statik alanları satır içinden başlatın'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- InitializeReferenceTypeStaticFieldsInline
- CA1810
helpviewer_keywords:
- InitializeReferenceTypeStaticFieldsInline
- CA1810
ms.assetid: e9693118-a914-4efb-9550-ec659d8d97d2
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 5e6f65c8b8c570f8df142c36f85388b68b66d3b0
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/24/2019
ms.locfileid: "71233665"
---
# <a name="ca1810-initialize-reference-type-static-fields-inline"></a>CA1810: Başvuru türü statik alanları satır içinden başlatın

|||
|-|-|
|TypeName|InitializeReferenceTypeStaticFieldsInline|
|CheckId|CA1810|
|Kategori|Microsoft. Performance|
|Son değişiklik|Kırılmamış|

## <a name="cause"></a>Sebep
Başvuru türü açık bir statik oluşturucu bildirir.

## <a name="rule-description"></a>Kural açıklaması
Bir tür açık statik yapıcı bildirdiğinde, JIT derleyici her bir statik yöntemi kontrol ekler ve türün yapıcı örneği statik yapıcının daha önceden çağrıldığından emin olur. Statik başlatma, herhangi bir statik üyeye erişildiğinde veya türün bir örneği oluşturulduğunda tetiklenir. Ancak, türün bir değişkenini bildirirseniz ancak kullanmıyorsanız, başlatma genel durumu değiştirdiğinde önemli olabilecek bir statik başlatma tetiklenmez.

Tüm statik veriler satır içi olarak başlatıldığında ve açık bir statik Oluşturucu bildirilmemiş ise, Microsoft ara dili (MSIL) derleyicileri `beforefieldinit` bayrağı ve statik verileri Başlatan bir örtük statik oluşturucuyu MSIL türüne ekler tanımı. JIT derleyicisi `beforefieldinit` bayrağıyla karşılaştığında, çoğu zaman statik oluşturucu denetimleri eklenmez. Statik başlatma, bir statik bir yöntem veya örnek Oluşturucu çağrılmadan önce değil, herhangi bir statik alana erişilmediği, ancak bir süre önce oluşma garantisi. Statik başlatmanın, türden bir değişken bildirildiğinde herhangi bir zamanda gerçekleşebileceğini unutmayın.

Statik oluşturucu denetimleri performansı düşürebilir. Genellikle statik bir Oluşturucu yalnızca statik alanları başlatmak için kullanılır, bu durumda yalnızca statik başlatmanın statik bir alana ilk erişimden önce meydana geldiğinden emin olmanız gerekir. Bu `beforefieldinit` davranış, ve diğer birçok tür için uygundur. Yalnızca statik başlatma genel durumu etkiliyorsa ve aşağıdakilerden biri doğru olduğunda uygunsuz olur:

- Genel durum üzerindeki etkisi pahalıdır ve tür kullanılmazsa gerekli değildir.

- Genel durum efektlerine, türdeki herhangi bir statik alana erişmeden erişilebilir.

## <a name="how-to-fix-violations"></a>İhlalleri çözme
Bu kural ihlalini düzeltmek için bildirildiğinde, tüm statik veriyi başlatın ve statik oluşturucuyu kaldırın.

## <a name="when-to-suppress-warnings"></a>Uyarıların ne zaman bastırılamıyor
Performans sorunu değilse, bu kuraldan bir uyarı bastırmak güvenlidir; veya statik başlatmanın neden olduğu genel durum değişiklikleri pahalıdır veya türün statik bir yöntemi çağrılmadan veya türün bir örneği oluşturulmadan önce gerçekleşmesi gerekir.

## <a name="example"></a>Örnek

Aşağıdaki örnek, kuralı ve bir `StaticConstructor` `NoStaticConstructor`türü ihlal eden bir türü gösterir, bu, kuralı karşılamak için statik oluşturucunun satır içi başlatma ile yerini almıştır.

[!code-csharp[FxCop.Performance.RefTypeStaticCtor#1](../code-quality/codesnippet/CSharp/ca1810-initialize-reference-type-static-fields-inline_1.cs)]
[!code-vb[FxCop.Performance.RefTypeStaticCtor#1](../code-quality/codesnippet/VisualBasic/ca1810-initialize-reference-type-static-fields-inline_1.vb)]

Sınıfı için MSIL tanımına `beforefieldinit` bayrağın eklenmesini aklınızda yapın. `NoStaticConstructor`

```
.class public auto ansi StaticConstructor
extends [mscorlib]System.Object
{
} // end of class StaticConstructor

.class public auto ansi beforefieldinit NoStaticConstructor
extends [mscorlib]System.Object
{
} // end of class NoStaticConstructor
```

## <a name="related-rules"></a>İlgili kurallar

- [CA2207 Değer türü statik alanları satır içi Başlat](../code-quality/ca2207-initialize-value-type-static-fields-inline.md)