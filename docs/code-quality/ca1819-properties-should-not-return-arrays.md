---
title: 'CA1819: Özellikler diziler döndürmemelidir'
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- PropertiesShouldNotReturnArrays
- CA1819
helpviewer_keywords:
- PropertiesShouldNotReturnArrays
- CA1819
ms.assetid: 85fcf312-57f8-438a-8b10-34441fe0bdeb
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 9fd738b0c16ede4f71c001036546c335d8ca7186
ms.sourcegitcommit: 209ed0fcbb8daa1685e8d6b9a97f3857a4ce1152
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/16/2019
ms.locfileid: "69547037"
---
# <a name="ca1819-properties-should-not-return-arrays"></a>CA1819: Özellikler diziler döndürmemelidir

|||
|-|-|
|TypeName|PropertiesShouldNotReturnArrays|
|CheckId|CA1819|
|Kategori|Microsoft. Performance|
|Yeni Değişiklik|Yeni|

## <a name="cause"></a>Sebep

Bir özellik bir dizi döndürür.

Varsayılan olarak, bu kural yalnızca dışarıdan görünür özellikler ve türlere bakar, ancak bu [yapılandırılabilir](#configurability).

## <a name="rule-description"></a>Kural açıklaması

Özellik salt okunurdur olsa bile, Özellikler tarafından döndürülen diziler yazma korumalı değildir. Dizi değiştirilmeye kanıt tutulacak özellik dizisinin bir kopyasını döndürmelidir. Genellikle, kullanıcılar bu tür bir özelliği çağırmanın olumsuz performans etkilerine ilişkin etkileri anlamaz. Özellikle, özelliği dizini oluşturulmuş bir özellik olarak kullanabilir.

## <a name="how-to-fix-violations"></a>İhlalleri çözme

Bu kural ihlalini onarmak için, özelliği bir yöntem yapın veya özelliği bir koleksiyon döndürecek şekilde değiştirin.

## <a name="when-to-suppress-warnings"></a>Uyarıların ne zaman bastırılamıyor

<xref:System.Attribute> Sınıfından türetilmiş bir özniteliğin özelliği için oluşturulan bir uyarıyı gizleyebilirsiniz. Öznitelikler, diziler döndüren özellikler içerebilir, ancak koleksiyonlar döndüren Özellikler içeremez.

Özellik [veri aktarımı nesne (DTO)](/previous-versions/msp-n-p/ff649585(v=pandp.10)) sınıfının bir parçasıysa, bu uyarıyı gizleyebilirsiniz.

Aksi takdirde, bu kuraldan bir uyarıyı bastırmayın.

## <a name="configurability"></a>Yapılandırılabilirlik

Bu kuralı [FxCop çözümleyicilerinin](install-fxcop-analyzers.md) (eski analizler olmadan) çalıştırıyorsanız, kod tabanınızın hangi bölümlerinin bu kuralı çalıştırmak için erişilebilirliğini temel alarak yapılandırabilirsiniz. Örneğin, kuralın yalnızca genel olmayan API yüzeyine karşı çalışması gerektiğini belirtmek için, aşağıdaki anahtar-değer çiftini projenizdeki bir. editorconfig dosyasına ekleyin:

```ini
dotnet_code_quality.ca1819.api_surface = private, internal
```

Bu seçeneği yalnızca bu kural için, tüm kurallar için veya bu kategorideki tüm kurallar (performans) için yapılandırabilirsiniz. Daha fazla bilgi için bkz. [FxCop çözümleyicileri yapılandırma](configure-fxcop-analyzers.md).

## <a name="example-violation"></a>Örnek ihlali

Aşağıdaki örnek, bu kuralı ihlal eden bir özelliği gösterir:

[!code-csharp[FxCop.Performance.PropertyArrayViolation#1](../code-quality/codesnippet/CSharp/ca1819-properties-should-not-return-arrays_1.cs)]
[!code-vb[FxCop.Performance.PropertyArrayViolation#1](../code-quality/codesnippet/VisualBasic/ca1819-properties-should-not-return-arrays_1.vb)]

Bu kural ihlalini onarmak için, özelliği bir metodu yapın ya da özelliği bir dizi yerine bir koleksiyon döndürecek şekilde değiştirin.

### <a name="change-the-property-to-a-method"></a>Özelliği bir yöntem olarak değiştirin

Aşağıdaki örnek, özelliğini bir yöntemi ile değiştirerek ihlalin düzeltir:

[!code-vb[FxCop.Performance.PropertyArrayFixedMethod#1](../code-quality/codesnippet/VisualBasic/ca1819-properties-should-not-return-arrays_2.vb)]
[!code-csharp[FxCop.Performance.PropertyArrayFixedMethod#1](../code-quality/codesnippet/CSharp/ca1819-properties-should-not-return-arrays_2.cs)]

### <a name="change-the-property-to-return-a-collection"></a>Özelliği bir koleksiyon döndürecek şekilde değiştirin

Aşağıdaki örnek, özelliği bir <xref:System.Collections.ObjectModel.ReadOnlyCollection%601?displayProperty=fullName>döndürecek şekilde değiştirerek ihlalini düzeltir:

[!code-csharp[FxCop.Performance.PropertyArrayFixedCollection#1](../code-quality/codesnippet/CSharp/ca1819-properties-should-not-return-arrays_3.cs)]
[!code-vb[FxCop.Performance.PropertyArrayFixedCollection#1](../code-quality/codesnippet/VisualBasic/ca1819-properties-should-not-return-arrays_3.vb)]

## <a name="allow-users-to-modify-a-property"></a>Kullanıcıların bir özelliği değiştirmesine izin ver

Sınıfın tüketicisi bir özelliği değiştirmesine izin vermek isteyebilirsiniz. Aşağıdaki örnek, bu kuralı ihlal eden bir okuma/yazma özelliği gösterir:

[!code-csharp[FxCop.Performance.PropertyModifyViolation#1](../code-quality/codesnippet/CSharp/ca1819-properties-should-not-return-arrays_4.cs)]
[!code-vb[FxCop.Performance.PropertyModifyViolation#1](../code-quality/codesnippet/VisualBasic/ca1819-properties-should-not-return-arrays_4.vb)]

Aşağıdaki örnek, özelliği bir <xref:System.Collections.ObjectModel.Collection%601?displayProperty=fullName>döndürecek şekilde değiştirerek ihlalini düzeltir:

[!code-vb[FxCop.Performance.PropertyModifyFixed#1](../code-quality/codesnippet/VisualBasic/ca1819-properties-should-not-return-arrays_5.vb)]
[!code-csharp[FxCop.Performance.PropertyModifyFixed#1](../code-quality/codesnippet/CSharp/ca1819-properties-should-not-return-arrays_5.cs)]

## <a name="related-rules"></a>İlgili kurallar

- [CA1024 Uygun yerlerde özellikleri kullanın](../code-quality/ca1024-use-properties-where-appropriate.md)