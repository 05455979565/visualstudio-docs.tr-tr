---
title: 'CA2120: Serileştirme oluşturucularının güvenliğini sağlayın'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2120
- SecureSerializationConstructors
helpviewer_keywords:
- SecureSerializationConstructors
- CA2120
ms.assetid: e9989da1-55a0-43f8-9aa9-da86afae3b41
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 38de3597d3693b072fec12f64211af4469851627
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/24/2019
ms.locfileid: "71232538"
---
# <a name="ca2120-secure-serialization-constructors"></a>CA2120: Serileştirme oluşturucularının güvenliğini sağlayın

|||
|-|-|
|TypeName|SecureSerializationConstructors|
|CheckId|CA2120|
|Kategori|Microsoft.Security|
|Son değişiklik|Yeni|

## <a name="cause"></a>Sebep
Türü <xref:System.Runtime.Serialization.ISerializable?displayProperty=fullName> arabirimini uygular, bir temsilci veya arabirim değildir ve kısmen güvenilen çağıranlara izin veren bir derlemede bildirilmiştir. Türün bir <xref:System.Runtime.Serialization.SerializationInfo?displayProperty=fullName> nesne <xref:System.Runtime.Serialization.StreamingContext?displayProperty=fullName> ve nesne alan bir Oluşturucusu vardır (serileştirme oluşturucusunun imzası). Bu Oluşturucu bir güvenlik denetimi tarafından güvenli değildir, ancak türdeki bir veya daha fazla normal Oluşturucu güvenli hale getirilir.

## <a name="rule-description"></a>Kural açıklaması
Bu kural, özel serileştirme desteği olan türler için geçerlidir. Bir tür, <xref:System.Runtime.Serialization.ISerializable?displayProperty=fullName> arabirimini uyguluyorsa özel Serileştirmeyi destekler. Serileştirme Oluşturucusu gereklidir ve <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A?displayProperty=fullName> yöntemi kullanılarak serileştirilmiş nesneleri yeniden serileştirmek veya yeniden oluşturmak için kullanılır. Serileştirme Oluşturucusu nesneleri ayırdığı ve Başlatan, normal oluşturucularda bulunan güvenlik denetimlerinin de serileştirme oluşturucusunda de mevcut olması gerekir. Bu kuralı ihlal ederseniz, başka bir örnek oluşturmayan çağıranlar bunu yapmak için serileştirme oluşturucusunu kullanabilir.

## <a name="how-to-fix-violations"></a>İhlalleri çözme
Bu kural ihlalini onarmak için serileştirme oluşturucuyu, diğer oluşturucuları koruanlarla aynı olan güvenlik taleplerine karşı koruyun.

## <a name="when-to-suppress-warnings"></a>Uyarıların ne zaman bastırılamıyor
Kural ihlalini engellemez.

## <a name="example"></a>Örnek
Aşağıdaki örnek, kuralı ihlal eden bir türü gösterir.

[!code-csharp[FxCop.Security.SerialCtors#1](../code-quality/codesnippet/CSharp/ca2120-secure-serialization-constructors_1.cs)]

## <a name="related-rules"></a>İlgili kurallar
[CA2229 Serileştirme oluşturucularını Uygula](../code-quality/ca2229-implement-serialization-constructors.md)

[CA2237 ISerializable türlerini SerializableAttribute ile işaretleyin](../code-quality/ca2237-mark-iserializable-types-with-serializableattribute.md)

## <a name="see-also"></a>Ayrıca bkz.

- <xref:System.Runtime.Serialization.ISerializable?displayProperty=fullName>
- <xref:System.Runtime.Serialization.SerializationInfo?displayProperty=fullName>
- <xref:System.Runtime.Serialization.StreamingContext?displayProperty=fullName>