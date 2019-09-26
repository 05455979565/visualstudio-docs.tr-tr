---
title: 'CA2134: Metotlar taban metotları geçersiz kılarken tutarlı saydamlığı tutmalıdır'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2134
ms.assetid: 3b17e487-0326-442e-90e1-dc0ba9cdd3f2
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 517588826983613c71a74296914b1dfeb3eaa2b4
ms.sourcegitcommit: e98db44f3a33529b0ba188d24390efd09e548191
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/25/2019
ms.locfileid: "71253311"
---
# <a name="ca2134-methods-must-keep-consistent-transparency-when-overriding-base-methods"></a>CA2134: Metotlar taban metotları geçersiz kılarken tutarlı saydamlığı tutmalıdır

|||
|-|-|
|TypeName|MethodsMustOverrideWithConsistentTransparency|
|CheckId|CA2134|
|Kategori|Microsoft.Security|
|Son değişiklik|Yeni|

## <a name="cause"></a>Sebep
Bu kural, <xref:System.Security.SecurityCriticalAttribute> ile işaretlenmiş bir yöntem saydam veya <xref:System.Security.SecuritySafeCriticalAttribute>ile işaretlenmiş bir yöntemi geçersiz kıldığında ateşlenir. Bu kural, saydam olan veya ile <xref:System.Security.SecuritySafeCriticalAttribute> işaretlenmiş bir yöntem <xref:System.Security.SecurityCriticalAttribute>ile işaretlenen bir yöntemi geçersiz kıldığında de ateşlenir.

Bu kural, sanal bir yöntemi geçersiz kılarken veya bir arabirim uygulanırken uygulanır.

## <a name="rule-description"></a>Kural açıklaması
Bu kural, devralma zincirinde daha fazla bir yöntemin güvenlik erişilebilirliğini değiştirme girişimleri üzerinde ateşlenir. Örneğin, bir temel sınıftaki sanal bir yöntem saydam veya kritik öneme sahip ise, türetilmiş sınıf onu saydam veya güvenli kritik bir yöntemle geçersiz kılmalıdır. Buna karşılık, sanal güvenlik açısından önemliyse, türetilen sınıfın onu bir güvenlik kritik yöntemiyle geçersiz kılması gerekir. Arabirim yöntemlerinin uygulanması için aynı kural geçerlidir.

Saydamlık kuralları, kod çalışma zamanı yerine JıT olarak derlenirse, saydamlık hesaplamasının dinamik tür bilgilerine sahip olmaması için zorlanır. Bu nedenle, saydam hesaplamanın sonucu, dinamik türden bağımsız olarak, yalnızca JıT olarak derlenen statik türlerden belirlenebilmelidir.

## <a name="how-to-fix-violations"></a>İhlalleri çözme
Bu kural ihlalini onarmak için, sanal bir yöntemi geçersiz kılan metodun saydamlığını değiştirin veya sanal ya da arabirim yönteminin saydamlığını eşleştirmek için bir arabirim uygulama.

## <a name="when-to-suppress-warnings"></a>Uyarıların ne zaman bastırılamıyor
Bu kuraldan gelen uyarıları göstermez. Bu kuralın ihlalleri, düzey 2 saydamlığı kullanan derlemeler için <xref:System.TypeLoadException> çalışma zamanına neden olacak.

## <a name="examples"></a>Örnekler

### <a name="code"></a>Kod
[!code-csharp[FxCop.Security.CA2134.MethodsMustOverrideWithConsistentTransparency#1](../code-quality/codesnippet/CSharp/ca2134-methods-must-keep-consistent-transparency-when-overriding-base-methods_1.cs)]

## <a name="see-also"></a>Ayrıca bkz.
[Güvenliği saydam kod, düzey 2](/dotnet/framework/misc/security-transparent-code-level-2)