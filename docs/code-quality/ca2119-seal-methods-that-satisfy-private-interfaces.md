---
title: 'CA2119: Özel arabirimleri karşılayan metotları mühürleyin'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- SealMethodsThatSatisfyPrivateInterfaces
- CA2119
helpviewer_keywords:
- CA2119
- SealMethodsThatSatisfyPrivateInterfaces
ms.assetid: 483d02e1-cfaf-4754-a98f-4116df0f3509
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CPP
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 02e69a97468675cd6f7530793581c15717465d6f
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68921055"
---
# <a name="ca2119-seal-methods-that-satisfy-private-interfaces"></a>CA2119: Özel arabirimleri karşılayan metotları mühürleyin

|||
|-|-|
|TypeName|SealMethodsThatSatisfyPrivateInterfaces|
|CheckId|CA2119|
|Kategori|Microsoft.Security|
|Yeni Değişiklik|Yeni|

## <a name="cause"></a>Sebep
Devralınabilir bir ortak tür, bir `internal` (`Friend` Visual Basic) arabiriminde geçersiz kılınabilir bir yöntem uygulamasını sağlar.

## <a name="rule-description"></a>Kural açıklaması
Arabirim yöntemleri, uygulama türü tarafından değiştirilemeyen genel erişilebilirliği vardır. İç arabirim, arabirimini tanımlayan derlemenin dışında uygulanması amaçlanan bir sözleşme oluşturur. `virtual` (`Overridable` Visual Basic) değiştiricisini kullanarak bir iç arabirimin yöntemini uygulayan ortak tür, metodun, derlemenin dışında olan türetilmiş bir tür tarafından geçersiz kılınmasına izin verir. Tanımlama derlemesinde ikinci bir tür yöntemi çağırırsa ve yalnızca dahili bir sözleşme bekliyorsa, bunun yerine dış derlemede geçersiz kılınan yöntem yürütüldüğünde davranışın güvenliği tehlikeye girebilir. Bu, bir güvenlik açığı oluşturur.

## <a name="how-to-fix-violations"></a>İhlalleri çözme
Bu kuralın ihlal edildiğini onarmak için, aşağıdakilerden birini kullanarak metodun derleme dışında geçersiz kılınmasını engelleyin:

- Bildirim türünü `sealed` (`NotInheritable` Visual Basic) yapın.

- Bildirim türünün erişilebilirliğini ( `internal` `Friend` Visual Basic) olarak değiştirin.

- Tüm ortak oluşturucuları bildirim türünden kaldırın.

- `virtual` Değiştiricisini kullanmadan yöntemi uygulayın.

- Yöntemi açıkça uygulayın.

## <a name="when-to-suppress-warnings"></a>Uyarıların ne zaman bastırılamıyor
Dikkatli bir gözden geçirdikten sonra, yöntem derleme dışında geçersiz kılınırsa, açıktan yararlanabilen güvenlik sorunları yoksa, bu kuraldan bir uyarıyı gizlemek güvenlidir.

## <a name="example-1"></a>Örnek 1
Aşağıdaki örnek, bu kuralı ihlal eden `BaseImplementation`bir türü gösterir.

[!code-cpp[FxCop.Security.SealMethods1#1](../code-quality/codesnippet/CPP/ca2119-seal-methods-that-satisfy-private-interfaces_1.cpp)]
[!code-csharp[FxCop.Security.SealMethods1#1](../code-quality/codesnippet/CSharp/ca2119-seal-methods-that-satisfy-private-interfaces_1.cs)]
[!code-vb[FxCop.Security.SealMethods1#1](../code-quality/codesnippet/VisualBasic/ca2119-seal-methods-that-satisfy-private-interfaces_1.vb)]

## <a name="example-2"></a>Örnek 2
Aşağıdaki örnek, önceki örneğin sanal yöntem uygulamasından yararlanır.

[!code-cpp[FxCop.Security.SealMethods2#1](../code-quality/codesnippet/CPP/ca2119-seal-methods-that-satisfy-private-interfaces_2.cpp)]
[!code-csharp[FxCop.Security.SealMethods2#1](../code-quality/codesnippet/CSharp/ca2119-seal-methods-that-satisfy-private-interfaces_2.cs)]
[!code-vb[FxCop.Security.SealMethods2#1](../code-quality/codesnippet/VisualBasic/ca2119-seal-methods-that-satisfy-private-interfaces_2.vb)]

## <a name="see-also"></a>Ayrıca bkz.

- [Arabirimler](/dotnet/csharp/programming-guide/interfaces/index)
- [Arabirimler](/dotnet/visual-basic/programming-guide/language-features/interfaces/index)