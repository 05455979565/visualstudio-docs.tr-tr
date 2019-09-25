---
title: 'CA1403: Otomatik yerleşim türleri COM görünebilir olmamalıdır'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- AutoLayoutTypesShouldNotBeComVisible
- CA1403
helpviewer_keywords:
- CA1403
- AutoLayoutTypesShouldNotBeComVisible
ms.assetid: a7007714-f9b4-4730-94e0-67d3dc68991f
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 4e590514247444d32d0d9a31b2bbc409434cf53c
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/24/2019
ms.locfileid: "71234827"
---
# <a name="ca1403-auto-layout-types-should-not-be-com-visible"></a>CA1403: Otomatik yerleşim türleri COM görünebilir olmamalıdır

|||
|-|-|
|TypeName|AutoLayoutTypesShouldNotBeComVisible|
|CheckId|CA1403|
|Kategori|Microsoft. çalışabilirliği|
|Son değişiklik|Yeni|

## <a name="cause"></a>Sebep

Bileşen nesne modeli (com) görünür değer türü, <xref:System.Runtime.InteropServices.StructLayoutAttribute?displayProperty=fullName> olarak <xref:System.Runtime.InteropServices.LayoutKind.Auto?displayProperty=fullName>ayarlanmış özniteliğiyle işaretlenir.

## <a name="rule-description"></a>Kural açıklaması

<xref:System.Runtime.InteropServices.LayoutKind>Düzen türleri ortak dil çalışma zamanı tarafından yönetilir. Bu türlerin düzeni, belirli bir düzeni bekleyen COM istemcilerini kesen .NET sürümleri arasında değişebilir. Öznitelik belirtilmemişse, C#, Visual Basic ve C++ derleyiciler değer türleri için [LayoutKind. Auto](<xref:System.Runtime.InteropServices.LayoutKind.Auto>) belirtir. <xref:System.Runtime.InteropServices.StructLayoutAttribute>

Aksi belirtilmedikçe genel, genel olmayan türler COM olarak görünür ve genel olmayan ve genel türler COM 'a görünmez. Ancak, hatalı pozitif sonuçları azaltmak için bu kural, türün COM görünürlüğünü açık bir şekilde ifade etmek için gereklidir. Kapsayan bütünleştirilmiş kod <xref:System.Runtime.InteropServices.ComVisibleAttribute?displayProperty=fullName> , olarak `false` ayarlanmış olarak işaretlenmelidir ve türü olarak <xref:System.Runtime.InteropServices.ComVisibleAttribute> `true`kümesiyle işaretlenmelidir.

## <a name="how-to-fix-violations"></a>İhlalleri çözme

Bu kural ihlalini onarmak için, <xref:System.Runtime.InteropServices.StructLayoutAttribute> özniteliğinin değerini [LayoutKind. Explicit](<xref:System.Runtime.InteropServices.LayoutKind.Explicit>) veya [LayoutKind. Sequential](<xref:System.Runtime.InteropServices.LayoutKind.Sequential>)olarak değiştirin ya da türü com olarak görünmez yapın.

## <a name="when-to-suppress-warnings"></a>Uyarıların ne zaman bastırılamıyor

Bu kuraldan uyarıyı bastırmayın.

## <a name="example"></a>Örnek

Aşağıdaki örnek, kuralı ve kuralı karşılayan bir türü ihlal eden bir türü gösterir.

[!code-csharp[FxCop.Interoperability.AutoLayout#1](../code-quality/codesnippet/CSharp/ca1403-auto-layout-types-should-not-be-com-visible_1.cs)]
[!code-vb[FxCop.Interoperability.AutoLayout#1](../code-quality/codesnippet/VisualBasic/ca1403-auto-layout-types-should-not-be-com-visible_1.vb)]

## <a name="related-rules"></a>İlgili kurallar

[CA1408 Oto Dual ClassInterfaceType kullanmayın](../code-quality/ca1408-do-not-use-autodual-classinterfacetype.md)

## <a name="see-also"></a>Ayrıca bkz.

- [Birlikte çalışma için .NET türlerini niteleyin](/dotnet/framework/interop/qualifying-net-types-for-interoperation)
- [Yönetilmeyen kod ile birlikte çalışma](/dotnet/framework/interop/index)