---
title: 'CA2134: Yöntemler taban yöntemleri geçersiz kılarken tutarlı saydamlığı tutmalıdır'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2134
ms.assetid: 3b17e487-0326-442e-90e1-dc0ba9cdd3f2
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0f56b81f3f3ce16f509f29791e28992402c222f9
ms.sourcegitcommit: 568bb0b944d16cfe1af624879fa3d3594d020187
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/13/2018
ms.locfileid: "45552009"
---
# <a name="ca2134-methods-must-keep-consistent-transparency-when-overriding-base-methods"></a>CA2134: Yöntemler taban yöntemleri geçersiz kılarken tutarlı saydamlığı tutmalıdır
|||
|-|-|
|TypeName|MethodsMustOverrideWithConsistentTransparency|
|CheckId|CA2134|
|Kategori|Microsoft.Security|
|Yeni Değişiklik|Yeni|

## <a name="cause"></a>Sebep
 Bu kural bir yöntem ile işaretlendiğinde tetikler <xref:System.Security.SecurityCriticalAttribute> saydam veya ile işaretlenmiş bir yöntemi geçersiz kılmalar <xref:System.Security.SecuritySafeCriticalAttribute>. Kural, saydam veya ile işaretlenmiş bir yöntemi, harekete <xref:System.Security.SecuritySafeCriticalAttribute> ile işaretlenmiş yöntemi geçersiz bir <xref:System.Security.SecurityCriticalAttribute>.

 Bu kural, sanal bir yöntemi geçersiz kılarken veya bir arabirim uygulanırken uygulanır.

## <a name="rule-description"></a>Kural açıklaması
 Bu kural bir yöntem daha devralım zincirinde yukarı doğru güvenlik erişilebilirliğini girişimleri tetikler. Taban sınıfında sanal bir yöntem, saydam veya güvenli kritik ise, örneğin, ardından türetilmiş sınıf, saydam veya güvenli kritik bir yöntemle geçersiz kılmanız gerekir. Sanal güvenlik açısından kritik ise, buna karşılık, türetilmiş sınıf, bir güvenlik kritik yöntemi geçersiz kılmanız gerekir. Aynı kural, arabirim yöntemleri uygulamak için geçerlidir.

 Saydamlık kuralları saydamlık hesaplama dinamik tür bilgisi yok. böylece kodu yerine çalışma zamanında derlenmiş JIT olduğunda uygulanır. Bu nedenle, saydamlık hesaplama sonucu olan JIT olarak derlenmiş dinamik türden bağımsız olarak, yalnızca statik türlerinden belirlenemedi olmalıdır.

## <a name="how-to-fix-violations"></a>İhlaller nasıl düzeltilir?
 Bu kural ihlalini düzeltmek için sanal yöntemini geçersiz kılma veya sanal saydamlık ya da arabirim yöntemi eşleştirmek için bir arabirimi uygulayan yöntem saydamlığını değiştirin.

## <a name="when-to-suppress-warnings"></a>Uyarılar bastırıldığında
 Bu kuraldan uyarıları bastırmayın. Bu kural ihlalleri çalışma zamanı'nda neden <xref:System.TypeLoadException> Düzey 2 Asetatını kullanın derlemeler için.

## <a name="examples"></a>Örnekler

### <a name="code"></a>Kod
 [!code-csharp[FxCop.Security.CA2134.MethodsMustOverrideWithConsistentTransparency#1](../code-quality/codesnippet/CSharp/ca2134-methods-must-keep-consistent-transparency-when-overriding-base-methods_1.cs)]

## <a name="see-also"></a>Ayrıca bkz.
 [Güvenliği saydam kod, Düzey 2](/dotnet/framework/misc/security-transparent-code-level-2)