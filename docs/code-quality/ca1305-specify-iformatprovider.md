---
title: 'CA1305: IFormatProvider belirt'
ms.date: 06/30/2018
ms.topic: reference
f1_keywords:
- SpecifyIFormatProvider
- CA1305
helpviewer_keywords:
- CA1305
- SpecifyIFormatProvider
ms.assetid: fb34ed9a-4eab-47cc-8eef-3068a4a1397e
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
ms.workload:
- multiple
ms.openlocfilehash: a9f6c8fd44749de43d86bf8037df0130ad682321
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/24/2019
ms.locfileid: "71235043"
---
# <a name="ca1305-specify-iformatprovider"></a>CA1305: IFormatProvider belirt

|||
|-|-|
|TypeName|SpecifyIFormatProvider|
|CheckId|CA1305|
|Kategori|Microsoft. Globalization|
|Son değişiklik|Kırılmamış|

## <a name="cause"></a>Sebep

Bir yöntem veya Oluşturucu bir <xref:System.IFormatProvider?displayProperty=fullName> parametreyi kabul eden aşırı yüklemeleri olan bir veya daha fazla üyeyi çağırır ve yöntem veya Oluşturucu <xref:System.IFormatProvider> parametreyi alan aşırı yüklemeyi çağırmaz.

Bu kural, <xref:System.IFormatProvider> parametreyi yok saymakla belgelenen .net yöntemlerine yapılan çağrıları yoksayar. Kural aşağıdaki yöntemleri de yoksayar:

- <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType>
- <xref:System.Resources.ResourceManager.GetObject%2A?displayProperty=nameWithType>
- <xref:System.Resources.ResourceManager.GetString%2A?displayProperty=nameWithType>

## <a name="rule-description"></a>Kural açıklaması

<xref:System.Globalization.CultureInfo?displayProperty=nameWithType> Veya<xref:System.IFormatProvider> nesnesi sağlanmadığında, aşırı yüklenmiş üye tarafından sağlanan varsayılan değer, tüm yerel ayarlarda istediğiniz etkiye sahip olmayabilir. Ayrıca, .NET üyeleri, kodunuz için doğru olmayan varsayımlar temelinde varsayılan kültür ve biçimlendirme seçeneklerini de tercih edebilir. Kodunuzun senaryolarınız için beklendiği gibi çalıştığından emin olmak için, aşağıdaki yönergelere göre kültüre özgü bilgiler sağlamalısınız:

- Değer kullanıcıya görüntülenecektir, geçerli kültürü kullanın. Bkz. <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType>.

- Değer, yazılım (bir dosya veya veritabanına kalıcı olarak) tarafından depolanacaksa ve erişiliyorsa, sabit kültür ' i kullanın. Bkz. <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>.

- Değerin hedefini belirtmediğinizde, veri tüketicisinin veya sağlayıcının kültürü belirtmesini sağlayabilirsiniz.

Aşırı yüklenmiş üyenin varsayılan davranışı gereksinimlerinize uygun olsa da, kodunuzun kendi kendine belgelenmesi ve daha kolay tutulması için kültüre özgü aşırı yüklemeyi açıkça çağırmak daha iyidir.

## <a name="how-to-fix-violations"></a>İhlalleri çözme

Bu kural ihlalini onarmak için bir <xref:System.IFormatProvider> bağımsız değişken alan aşırı yüklemeyi kullanın. Ya da, [ C# enterpolasyonlu bir dize](/dotnet/csharp/tutorials/string-interpolation) kullanın ve <xref:System.FormattableString.Invariant%2A?displayProperty=nameWithType> yönteme geçirin.

## <a name="when-to-suppress-warnings"></a>Uyarıların ne zaman bastırılamıyor

Varsayılan biçimin doğru seçim olması ve kodun bakımınızın önemli bir geliştirme önceliği olmaması durumunda bu kuraldan gelen bir uyarının görüntülenmesini güvenli hale gelir.

## <a name="example"></a>Örnek

Aşağıdaki kodda, `example1` dize CA1305 kuralını ihlal ediyor. Dize, ' i <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType> <xref:System.IFormatProvider>uygulayankuralınıgeçirerek CA1305 kuralını karşılar. <xref:System.String.Format(System.IFormatProvider,System.String,System.Object)?displayProperty=nameWithType> `example2` Dize `example3` , enterpolasyonlu bir dizeyi öğesine <xref:System.FormattableString.Invariant%2A?displayProperty=fullName]>geçirerek CA1305 kuralını karşılar.

```csharp
string name = "Georgette";

// Violates CA1305
string example1 = String.Format("Hello {0}", name);

// Satisfies CA1305
string example2 = String.Format(CultureInfo.CurrentCulture, "Hello {0}", name);

// Satisfies CA1305
string example3 = FormattableString.Invariant($"Hello {name}");
```

## <a name="related-rules"></a>İlgili kurallar

- [CA1304 CultureInfo belirt](../code-quality/ca1304-specify-cultureinfo.md)

## <a name="see-also"></a>Ayrıca bkz.

- [CultureInfo sınıfını kullanma](/dotnet/standard/globalization-localization/globalization#work-with-culture-specific-settings)