---
title: 'CA1711: Tanımlayıcılar yanlış sonek içermemelidir'
ms.date: 03/11/2019
ms.topic: reference
f1_keywords:
- CA1711
- IdentifiersShouldNotHaveIncorrectSuffix
helpviewer_keywords:
- CA1711
- IdentifiersShouldNotHaveIncorrectSuffix
ms.assetid: a63359ab-386d-44ae-b381-ee3a983aca29
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 2e04487a9bfcd8ef9a0e9a15bc76a93b221f9ce1
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/24/2019
ms.locfileid: "71234139"
---
# <a name="ca1711-identifiers-should-not-have-incorrect-suffix"></a>CA1711: Tanımlayıcılar yanlış sonek içermemelidir

|||
|-|-|
|TypeName|IdentifiersShouldNotHaveIncorrectSuffix|
|CheckId|CA1711|
|Kategori|Microsoft. Naming|
|Son değişiklik|Yeni|

## <a name="cause"></a>Sebep

Bir tanımlayıcı yanlış bir son eke sahip.

Bu kural varsayılan olarak yalnızca dışarıdan görünen tanımlayıcılara bakar, ancak bu [yapılandırılabilir](#configurability).

## <a name="rule-description"></a>Kural açıklaması

Kural gereği, yalnızca, belirli temel türleri genişleten veya bazı arabirimleri ya da bu türlerden türetilmiş türleri uygulayan tür adları, belirli ayrılmış soneklerle bitmelidir. Diğer tür adları aşağıdaki ayrılmış sonekleri kullanmamalı.

Aşağıdaki tabloda, ayrılmış sonekler ve ilişkili oldukları temel türler ve arabirimler listelenmiştir.

|Önekini|Temel tür/arabirim|
|------------|--------------------------|
|Öznitelik|<xref:System.Attribute?displayProperty=fullName>|
|Koleksiyon|<xref:System.Collections.ICollection?displayProperty=fullName><br /><br /> <xref:System.Collections.IEnumerable?displayProperty=fullName><br /><br /> <xref:System.Collections.Queue?displayProperty=fullName><br /><br /> <xref:System.Collections.Stack?displayProperty=fullName><br /><br /> <xref:System.Collections.Generic.ICollection%601?displayProperty=fullName><br /><br /> <xref:System.Data.DataSet?displayProperty=fullName><br /><br /> <xref:System.Data.DataTable?displayProperty=fullName>|
|Sözlüğünü|<xref:System.Collections.IDictionary?displayProperty=fullName><br /><br /> <xref:System.Collections.Generic.IDictionary%602?displayProperty=fullName>|
|EventArgs|<xref:System.EventArgs?displayProperty=fullName>|
|Çalışılıyor|Bir olay işletici temsilcisi|
|Özel Durum|<xref:System.Exception?displayProperty=fullName>|
|İzin|<xref:System.Security.IPermission?displayProperty=fullName>|
|Sıra|<xref:System.Collections.Queue?displayProperty=fullName>|
|Yığın|<xref:System.Collections.Stack?displayProperty=fullName>|
|Akış|<xref:System.IO.Stream?displayProperty=fullName>|

Ayrıca, aşağıdaki **sonekler kullanılmamalıdır:**

- `Delegate`

- `Enum`

- `Impl`(bunun `Core` yerine kullanın)

- `Ex`ya da benzer sonekin aynı türden önceki bir sürümden ayırt edilebilmesi için

Adlandırma kuralları, ortak dil çalışma zamanını hedefleyen kitaplıklar için ortak bir görünüm sağlar. Bu, yeni yazılım kitaplıkları için gerekli olan öğrenme eğrisini azaltır ve müşterinin, kitaplığın yönetilen kod geliştirme konusunda uzmanlığa sahip olan birisi tarafından geliştirildiğini arttırır.

## <a name="how-to-fix-violations"></a>İhlalleri çözme

Tür adından soneki kaldırın.

## <a name="when-to-suppress-warnings"></a>Uyarıların ne zaman bastırılamıyor

Sonekte uygulama etki alanında açık bir anlama sahip olmadığı sürece bu kuraldan bir uyarıyı bastırmayın.

## <a name="configurability"></a>Yapılandırılabilirlik

Bu kuralı [FxCop çözümleyicilerinin](install-fxcop-analyzers.md) (eski analizler olmadan) çalıştırıyorsanız, kod tabanınızın hangi bölümlerinin bu kuralı çalıştırmak için erişilebilirliğini temel alarak yapılandırabilirsiniz. Örneğin, kuralın yalnızca genel olmayan API yüzeyine karşı çalışması gerektiğini belirtmek için, aşağıdaki anahtar-değer çiftini projenizdeki bir. editorconfig dosyasına ekleyin:

```ini
dotnet_code_quality.ca1711.api_surface = private, internal
```

Bu seçeneği yalnızca bu kural için, tüm kurallar için veya bu kategorideki tüm kurallar (adlandırma) için yapılandırabilirsiniz. Daha fazla bilgi için bkz. [FxCop çözümleyicileri yapılandırma](configure-fxcop-analyzers.md).

## <a name="related-rules"></a>İlgili kurallar

- [CA1710 Tanımlayıcılar doğru sonekine sahip olmalıdır](../code-quality/ca1710-identifiers-should-have-correct-suffix.md)

## <a name="see-also"></a>Ayrıca bkz.

- [Öznitelikler](/dotnet/standard/design-guidelines/attributes)
- [Olayları işleme ve oluşturma](/dotnet/standard/events/index)