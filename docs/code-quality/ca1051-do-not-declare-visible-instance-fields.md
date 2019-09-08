---
title: 'CA1051: Görünür örnek alanlarını bildirmeyin'
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- CA1051
- DoNotDeclareVisibleInstanceFields
helpviewer_keywords:
- CA1051
- DoNotDeclareVisibleInstanceFields
ms.assetid: 2805376c-824c-462c-81d1-c51aaf7cabe7
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 455ab619f293981c5ebd3afba6336c63f2fe7f49
ms.sourcegitcommit: 0f44ec8ba0263056ad04d2d0dc904ad4206ce8fc
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70766064"
---
# <a name="ca1051-do-not-declare-visible-instance-fields"></a>CA1051: Görünür örnek alanlarını bildirmeyin

|||
|-|-|
|TypeName|DoNotDeclareVisibleInstanceFields|
|CheckId|CA1051|
|Kategori|Microsoft.Design|
|Yeni Değişiklik|Yeni|

## <a name="cause"></a>Sebep

Türün özel olmayan bir örnek alanı vardır.

Bu kural varsayılan olarak yalnızca dışarıdan görünür türlere bakar, ancak bu [yapılandırılabilir](#configurability).

## <a name="rule-description"></a>Kural açıklaması

Bir alanın birincil kullanım alanının uygulama ayrıntısı olması gerekir. Alanlar, `internal` veya özellikleri kullanılarak sunulmalıdır. `private` Bir alana erişmek için bir özelliğe erişmek kolaydır ve bir özelliğin erişimcilerinin kodu, önemli değişikliklere bildirmeden tür özellikleri genişleyebilir.

Yalnızca bir özel veya iç alanın değerini döndüren Özellikler bir alana erişim için en iyi duruma getirilir; Özellikler yerine dışarıdan görünür alanları kullanmanın performans artışı en az düzeydedir. *Dışarıdan görünür* `public`, ,,`protected internal` ve(`Public`VisualBasic)erişilebilirlik düzeylerine başvurur. `Protected` `protected` `Protected Friend`

Ayrıca, ortak alanlar [bağlantı taleplerine](/dotnet/framework/misc/link-demands)karşı korunamaz. Daha fazla bilgi için bkz [. CA2112: Güvenli türler alanları](../code-quality/ca2112-secured-types-should-not-expose-fields.md)kullanıma sunmamalıdır. (Bağlantı talepleri .NET Core uygulamaları için geçerli değildir.)

## <a name="how-to-fix-violations"></a>İhlalleri çözme

Bu kural ihlalini onarmak için, alanı `private` oluşturun veya `internal` dışarıdan görünebilir bir özellik kullanarak sunun.

## <a name="when-to-suppress-warnings"></a>Uyarıların ne zaman bastırılamıyor

Yalnızca tüketicilerin alana doğrudan erişim ihtiyacı olduğundan eminseniz bu uyarıyı gizleyin. Birçok uygulama için, sunulan alanlar, özellikler üzerinden performans veya bakım açısından avantaj sağlamaz.

Tüketicilerin aşağıdaki durumlarda alan erişimine ihtiyacı olabilir:

- ASP.NET Web Forms içerik denetimleri
- Hedef platform, WPF ve UWP için `ref` Model-View-ViewModel (MVVM) çerçeveleri gibi alanları değiştirmek için ' ı kullanyaptığında

## <a name="configurability"></a>Yapılandırılabilirlik

Bu kuralı [FxCop çözümleyicilerinin](install-fxcop-analyzers.md) (eski analizler olmadan) çalıştırıyorsanız, kod tabanınızın hangi bölümlerinin bu kuralı çalıştırmak için erişilebilirliğini temel alarak yapılandırabilirsiniz. Örneğin, kuralın yalnızca genel olmayan API yüzeyine karşı çalışması gerektiğini belirtmek için, aşağıdaki anahtar-değer çiftini projenizdeki bir. editorconfig dosyasına ekleyin:

```ini
dotnet_code_quality.ca1051.api_surface = private, internal
```

Bu seçeneği yalnızca bu kural için, tüm kurallar için veya bu kategorideki tüm kurallar (tasarım) için yapılandırabilirsiniz. Daha fazla bilgi için bkz. [FxCop çözümleyicileri yapılandırma](configure-fxcop-analyzers.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, bu kuralı ihlal eden`BadPublicInstanceFields`bir türü () gösterir. `GoodPublicInstanceFields`düzeltilen kodu gösterir.

[!code-csharp[FxCop.Design.TypesPublicInstanceFields#1](../code-quality/codesnippet/CSharp/ca1051-do-not-declare-visible-instance-fields_1.cs)]

## <a name="related-rules"></a>İlgili kurallar

- [CA2112 Güvenli türler alanları kullanıma sunmamalıdır](../code-quality/ca2112-secured-types-should-not-expose-fields.md)

## <a name="see-also"></a>Ayrıca bkz.

- [Bağlantı talepleri](/dotnet/framework/misc/link-demands)
