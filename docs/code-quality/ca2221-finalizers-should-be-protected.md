---
title: 'CA2221: Sonlandırıcılar korunmalıdır'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2221
- FinalizersShouldBeProtected
helpviewer_keywords:
- FinalizersShouldBeProtected
- CA2221
ms.assetid: bda03aee-4cce-45d3-907d-17f4ee030acc
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 827a8ee01575d6d263c8f8ee423de72cfe939e39
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/24/2019
ms.locfileid: "71231176"
---
# <a name="ca2221-finalizers-should-be-protected"></a>CA2221: Sonlandırıcılar korunmalıdır

|||
|-|-|
|TypeName|FinalizersShouldBeProtected|
|CheckId|CA2221|
|Kategori|Microsoft. Usage|
|Son değişiklik|Kırılmamış|

## <a name="cause"></a>Sebep
Ortak tür, Aile (korumalı) erişimi belirtmeyen bir Sonlandırıcı uygular.

## <a name="rule-description"></a>Kural açıklaması
Sonlandırıcılar aile erişim değiştiricisi kullanmalıdır. Bu kural, Visual Basic ve Visual C# C++ derleyicileri tarafından zorlanır.

## <a name="how-to-fix-violations"></a>İhlalleri çözme
Bu kural ihlalini onarmak için sonlandırıcıyı aile erişimi olacak şekilde değiştirin.

## <a name="when-to-suppress-warnings"></a>Uyarıların ne zaman bastırılamıyor
Bu kuraldan uyarıyı bastırmayın.

## <a name="example"></a>Örnek
Bu kural, herhangi bir üst düzey .NET dilinde ihlal edilemez; Microsoft ara dili yazıyorsanız, bu çiğnenebilir.

```
// =============== CLASS MEMBERS DECLARATION ===================
//   note that class flags, 'extends' and 'implements' clauses
//          are provided here for information only

.namespace UsageLibrary
{
  .class public auto ansi beforefieldinit FinalizeMethodNotProtected
         extends [mscorlib]System.Object
  {
    .method public hidebysig instance void
            Finalize() cil managed
    {

      // Code size       1 (0x1)
      .maxstack  0
      IL_0000:  ret
    } // end of method FinalizeMethodNotProtected::Finalize

    .method public hidebysig specialname rtspecialname
            instance void  .ctor() cil managed
    {
      // Code size       7 (0x7)
      .maxstack  1
      IL_0000:  ldarg.0
      IL_0001:  call       instance void [mscorlib]System.Object::.ctor()
      IL_0006:  ret
    } // end of method FinalizeMethodNotProtected::.ctor

  } // end of class FinalizeMethodNotProtected
} // end of namespace
```

## <a name="see-also"></a>Ayrıca bkz.

- [Dispose Deseni](/dotnet/standard/design-guidelines/dispose-pattern)