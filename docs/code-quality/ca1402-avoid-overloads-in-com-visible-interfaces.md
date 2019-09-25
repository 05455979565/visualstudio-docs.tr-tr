---
title: 'CA1402: COM görünebilir arabirimler içinde aşırı yüklemelerden kaçının'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- AvoidOverloadsInComVisibleInterfaces
- CA1402
helpviewer_keywords:
- AvoidOverloadsInComVisibleInterfaces
- CA1402
ms.assetid: 2724c1f9-d5d3-4704-b124-21c4d398e5df
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: fdbb6012fb1252c90014ba91caf8ad7dacf901c2
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/24/2019
ms.locfileid: "71234856"
---
# <a name="ca1402-avoid-overloads-in-com-visible-interfaces"></a>CA1402: COM görünebilir arabirimler içinde aşırı yüklemelerden kaçının

|||
|-|-|
|TypeName|AvoidOverloadsInComVisibleInterfaces|
|CheckId|CA1402|
|Kategori|Microsoft. çalışabilirliği|
|Son değişiklik|Yeni|

## <a name="cause"></a>Sebep
Bileşen nesne modeli (COM) görünür arabirimi, aşırı yüklenmiş yöntemleri bildirir.

## <a name="rule-description"></a>Kural açıklaması
Aşırı yüklenmiş yöntemler COM istemcilerine maruz kaldığında, sadece ilk yöntem aşırı yüklemesi adını korur. Sonraki aşırı yüklemeler, ada bir alt çizgi karakteri olan ' _ ' ve aşırı yükleme bildiriminin sırasına karşılık gelen bir tamsayı eklenerek benzersiz olarak yeniden adlandırılır. Örneğin, aşağıdaki yöntemleri göz önünde bulundurun:

```csharp
void SomeMethod(int valueOne);
void SomeMethod(int valueOne, int valueTwo, int valueThree);
void SomeMethod(int valueOne, int valueTwo);
```

Bu yöntemler aşağıdaki gibi COM istemcilerine sunulur.

```csharp
void SomeMethod(int valueOne);
void SomeMethod_2(int valueOne, int valueTwo, int valueThree);
void SomeMethod_3(int valueOne, int valueTwo);
```

Visual Basic 6 COM istemcileri, ad içinde bir alt çizgi kullanarak arabirim yöntemleri uygulayamaz.

## <a name="how-to-fix-violations"></a>İhlalleri çözme
Bu kuralın ihlalini onarmak için, aşırı yüklenmiş yöntemleri adların benzersiz olması için yeniden adlandırın. Alternatif olarak, `internal` erişilebilirliği (`Friend` ın [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]) olarak değiştirerek veya <xref:System.Runtime.InteropServices.ComVisibleAttribute?displayProperty=fullName> özniteliğini olarak `false`ayarlayarak, arabirimi com 'a görünmez hale getirin.

## <a name="when-to-suppress-warnings"></a>Uyarıların ne zaman bastırılamıyor
Bu kuraldan uyarıyı bastırmayın.

## <a name="example"></a>Örnek
Aşağıdaki örnekte, kuralı ve kuralı karşılayan bir arabirimi ihlal eden bir arabirim gösterilmektedir.

[!code-vb[FxCop.Interoperability.OverloadsInterface#1](../code-quality/codesnippet/VisualBasic/ca1402-avoid-overloads-in-com-visible-interfaces_1.vb)]
[!code-csharp[FxCop.Interoperability.OverloadsInterface#1](../code-quality/codesnippet/CSharp/ca1402-avoid-overloads-in-com-visible-interfaces_1.cs)]

## <a name="related-rules"></a>İlgili kurallar
[CA1413 COM görünebilir değer türlerinde genel olmayan alanlardan kaçının](../code-quality/ca1413-avoid-non-public-fields-in-com-visible-value-types.md)

[CA1407 COM görünebilir türler içinde statik üyelerden kaçının](../code-quality/ca1407-avoid-static-members-in-com-visible-types.md)

[CA1017 Derlemeleri ComVisibleAttribute ile işaretleyin](../code-quality/ca1017-mark-assemblies-with-comvisibleattribute.md)

## <a name="see-also"></a>Ayrıca bkz.

- [Yönetilmeyen Kod ile Birlikte Çalışma](/dotnet/framework/interop/index)
- [Long Veri Türü](/dotnet/visual-basic/language-reference/data-types/long-data-type)