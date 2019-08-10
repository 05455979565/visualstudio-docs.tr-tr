---
title: 'CA2123: Geçersiz kılan bağlantı talepleri taban ile özdeş olmalıdır'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2123
- OverrideLinkDemandsShouldBeIdenticalToBase
helpviewer_keywords:
- OverrideLinkDemandsShouldBeIdenticalToBase
- CA2123
ms.assetid: 4538ecd5-fc6f-4480-ab00-90b2ce4730db
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 0ecc30f3fe16b283c0eb9cc1f369458bb1d7f952
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68920807"
---
# <a name="ca2123-override-link-demands-should-be-identical-to-base"></a>CA2123: Geçersiz kılan bağlantı talepleri taban ile özdeş olmalıdır

|||
|-|-|
|TypeName|OverrideLinkDemandsShouldBeIdenticalToBase|
|CheckId|CA2123|
|Kategori|Microsoft.Security|
|Yeni Değişiklik|Yeni|

## <a name="cause"></a>Sebep
Ortak bir türdeki ortak veya korumalı yöntem bir yöntemi geçersiz kılar veya arabirimini uygular ve arabirim ya da sanal yöntemle aynı [bağlantı taleplerine](/dotnet/framework/misc/link-demands) sahip değildir.

## <a name="rule-description"></a>Kural açıklaması
Bu kural, arabirim ya da başka bir türdeki sanal yöntem olan temel yöntem ile başka bir yöntemi eşleştirir ve sonra her bir bağlantı talebini inceler. Bir ihlal, yöntemin veya temel yöntemin bir bağlantı talebi varsa ve diğeri değilse bildirilir.

Bu kural ihlal edilirse, kötü niyetli bir çağıran yalnızca güvenli olmayan yöntemi çağırarak bağlantı talebini atlayabilir.

## <a name="how-to-fix-violations"></a>İhlalleri çözme
Bu kural ihlalini onarmak için, aynı bağlantı talebini geçersiz kılma yöntemine veya uygulamasına uygulayın. Bu mümkün değilse, yöntemi bir tam talep ile işaretleyin ya da özniteliği tamamen kaldırın.

## <a name="when-to-suppress-warnings"></a>Uyarıların ne zaman bastırılamıyor
Bu kuraldan uyarıyı bastırmayın.

## <a name="example"></a>Örnek
Aşağıdaki örnekte, bu kuralın çeşitli ihlalleri gösterilmektedir.

[!code-csharp[FxCop.Security.OverridesAndSecurity#1](../code-quality/codesnippet/CSharp/ca2123-override-link-demands-should-be-identical-to-base_1.cs)]

## <a name="see-also"></a>Ayrıca bkz.

- [Güvenli Kodlama Yönergeleri](/dotnet/standard/security/secure-coding-guidelines)
- [Bağlantı talepleri](/dotnet/framework/misc/link-demands)