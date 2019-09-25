---
title: 'CA1702: Bileşik sözcüklerin büyük küçük harfleri doğru olmalıdır'
ms.date: 03/28/2018
ms.topic: reference
f1_keywords:
- CA1702
- CompoundWordsShouldBeCasedCorrectly
helpviewer_keywords:
- CA1702
- CompoundWordsShouldBeCasedCorrectly
ms.assetid: 05481245-7ad8-48c3-a456-3aa44b6160a6
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 5480d3dde926dfe31b018a5cd0b1ea6a5813063b
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/24/2019
ms.locfileid: "71234329"
---
# <a name="ca1702-compound-words-should-be-cased-correctly"></a>CA1702: Bileşik sözcüklerin büyük küçük harfleri doğru olmalıdır

|||
|-|-|
|TypeName|CompoundWordsShouldBeCasedCorrectly|
|CheckId|CA1702|
|Kategori|Microsoft. Naming|
|Son değişiklik|Parçalara ayırma-derlemeler üzerinde harekete geçirildi.<br /><br /> Tür parametrelerinde harekete geçirildiğinde, bozmasız değildir.|

## <a name="cause"></a>Sebep

Tanımlayıcının adı birden çok sözcük içerir ve bu sözcüklerden en az biri büyük harf kullanımı hatasına maruz kalmış birleşik kelime olarak görülür.

## <a name="rule-description"></a>Kural açıklaması

Tanımlayıcının adı, büyük/küçük harfe bağlı olan sözcüklere bölünür. Her bitişik iki sözcüklü birleşim, Microsoft yazım denetleyicisi kitaplığı tarafından denetlenir. Tanınırsa, tanımlayıcı kuralın ihlal edildiğini üretir. İhlalin oluşmasına neden olan Birleşik kelimelerin örnekleri, sırasıyla "Checksum" ve "multipart" olarak, "Checksum" ve "multipart" şeklinde olmalıdır. Önceki yaygın kullanım nedeniyle, birkaç özel durum kuralda yerleşik olarak bulunur ve "araç çubuğu" ve "dosya adı" gibi birçok tek sözcük işaretlenir, bu da iki ayrı sözcük olarak (Bu durumda "araç çubuğu" ve "dosya adı") kullanılır.

Adlandırma kuralları, ortak dil çalışma zamanını hedefleyen kitaplıklar için ortak bir görünüm sağlar. Bu, yeni yazılım kitaplıkları için gerekli olan öğrenme eğrisini azaltır ve müşterinin, kitaplığın yönetilen kod geliştirme konusunda uzmanlığa sahip olan birisi tarafından geliştirildiğini arttırır.

## <a name="how-to-fix-violations"></a>İhlalleri çözme

Adı doğru bir şekilde olacak şekilde değiştirin.

## <a name="language"></a>Dil

Yazım denetleyicisi şu anda yalnızca Ingilizce tabanlı kültür sözlüklerine karşı kontrol eder. **Kod analysisculture** öğesini ekleyerek proje dosyasındaki projenizin kültürünü değiştirebilirsiniz.

Örneğin:

```xml
<Project ...>
  <PropertyGroup>
    <CodeAnalysisCulture>en-AU</CodeAnalysisCulture>
```

> [!IMPORTANT]
> Kültürü, Ingilizce tabanlı kültür dışında bir şeye ayarlarsanız, bu kod analizi kuralı sessizce devre dışıdır.

## <a name="when-to-suppress-warnings"></a>Uyarıların ne zaman bastırılamıyor

Bileşik sözcüğün her iki bölümü de yazım sözlüğü tarafından tanınıyorsa ve amaç iki sözcükten birini kullanıyorsa, bu kuraldan bir uyarının görüntülenmesini güvenli hale gelir.

## <a name="related-rules"></a>İlgili kurallar

- [CA1701 Kaynak dizesi bileşik sözcüklerin doğru şekilde küçük harf oluşturulması gerekir](../code-quality/ca1701-resource-string-compound-words-should-be-cased-correctly.md)
- [CA1709 Tanımlayıcılar doğru şekilde yazılmalıdır](../code-quality/ca1709-identifiers-should-be-cased-correctly.md)
- [CA1708 Tanımlayıcılar, büyük/küçük harf bakımından farklı olmalıdır](../code-quality/ca1708-identifiers-should-differ-by-more-than-case.md)

## <a name="see-also"></a>Ayrıca bkz.

- [Adlandırma Kuralları](/dotnet/standard/design-guidelines/naming-guidelines)
- [Büyük/Küçük Harf Kuralları](/dotnet/standard/design-guidelines/capitalization-conventions)