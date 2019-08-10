---
title: 'CA2112: Güvenli türler alanları açığa çıkarmamalıdır'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2112
- SecuredTypesShouldNotExposeFields
helpviewer_keywords:
- SecuredTypesShouldNotExposeFields
- CA2112
ms.assetid: 9eb13a78-3487-49f2-81d1-3c3866db132f
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 43ef4165823f59045dda8c05b5679fdd3b795114
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68921088"
---
# <a name="ca2112-secured-types-should-not-expose-fields"></a>CA2112: Güvenli türler alanları açığa çıkarmamalıdır

|||
|-|-|
|TypeName|SecuredTypesShouldNotExposeFields|
|CheckId|CA2112|
|Kategori|Microsoft.Security|
|Yeni Değişiklik|Yeni|

## <a name="cause"></a>Sebep
Ortak veya korumalı bir tür ortak alanlar içerir ve bir [bağlantı taleplerine](/dotnet/framework/misc/link-demands)göre güvenli hale getirilir.

## <a name="rule-description"></a>Kural açıklaması
Bağlantı talebi tarafından güvenli türde bir örnek kod erişimi varsa, kod türün alanlarına erişmek için bağlantı talebine sahip değildir.

## <a name="how-to-fix-violations"></a>İhlalleri çözme
Bu kural ihlalini onarmak için alanları ortak yapın ve alan verilerini döndüren ortak özellikler veya yöntemler ekleyin. Türler üzerinde LinkDemand güvenlik denetimleri, türün özelliklerine ve yöntemlerine erişimi korur. Ancak, kod erişim güvenliği alanlar için geçerlidir.

## <a name="when-to-suppress-warnings"></a>Uyarıların ne zaman bastırılamıyor
Hem güvenlik sorunları hem de iyi tasarım için genel alanları ortak hale getirerek ihlalleri çözmeniz gerekir. Alan güvenli kalması gereken bilgileri içermiyorsa ve alanın içeriğine bağlı değilseniz, bu kuraldan bir uyarıyı gizleyebilirsiniz.

## <a name="example"></a>Örnek
Aşağıdaki örnek, güvenli olmayan alanları olan bir kitaplık türünden`SecuredTypeWithFields`() oluşur, kitaplık türünün örneklerini oluşturabileceğiniz`Distributor`ve yanlış bir şekilde örnekleri türlerine geçiren bir tür (), bunları oluşturmak için izne sahip değildir ve uygulama kodu , türü güvenlik altına alan izne sahip olmasa da, bir örneğin alanlarını okuyabilir.

Aşağıdaki kitaplık kodu, kuralı ihlal ediyor.

[!code-csharp[FxCop.Security.LinkDemandOnField#1](../code-quality/codesnippet/CSharp/ca2112-secured-types-should-not-expose-fields_1.cs)]

## <a name="example-1"></a>Örnek 1
Uygulama, güvenli türü koruyan bağlantı talebi nedeniyle bir örnek oluşturamıyor. Aşağıdaki sınıf, uygulamanın güvenli türdeki bir örneği almasını sağlar.

[!code-csharp[FxCop.Security.LDOnFieldsDistributor#1](../code-quality/codesnippet/CSharp/ca2112-secured-types-should-not-expose-fields_2.cs)]

## <a name="example-2"></a>Örnek 2
Aşağıdaki uygulama, güvenli bir tür yöntemlerine erişim izni olmadan, kodun alanlarına erişip erişecebileceği gösterilmektedir.

[!code-csharp[FxCop.Security.TestLinkDemandOnFields#1](../code-quality/codesnippet/CSharp/ca2112-secured-types-should-not-expose-fields_3.cs)]

Bu örnek aşağıdaki çıktıyı üretir:

```txt
Creating an instance of SecuredTypeWithFields.
Secured type fields: 22, 33
Changing secured type's field...
Cached Object fields: 99, 33
```

## <a name="related-rules"></a>İlgili kurallar

- [CA1051 Görünür örnek alanlarını bildirme](../code-quality/ca1051-do-not-declare-visible-instance-fields.md)

## <a name="see-also"></a>Ayrıca bkz.

- [Bağlantı talepleri](/dotnet/framework/misc/link-demands)
- [Veri ve Modelleme](/dotnet/framework/data/index)