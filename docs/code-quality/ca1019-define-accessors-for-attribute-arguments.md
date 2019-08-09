---
title: 'CA1019: Öznitelik bağımsız değişkenleri için erişimciler tanımlayın'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA1019
- DefineAccessorsForAttributeArguments
helpviewer_keywords:
- CA1019
- DefineAccessorsForAttributeArguments
ms.assetid: 197f2378-3c43-427e-80de-9ec25006c05c
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 8422427997db291aa24bc8a8bacfdc59abe35998
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68923074"
---
# <a name="ca1019-define-accessors-for-attribute-arguments"></a>CA1019: Öznitelik bağımsız değişkenleri için erişimciler tanımlayın

|||
|-|-|
|TypeName|DefineAccessorsForAttributeArguments|
|CheckId|CA1019|
|Kategori|Microsoft.Design|
|Yeni Değişiklik|Kırılmamış|

## <a name="cause"></a>Sebep
Yapıcısında bir öznitelik, karşılık gelen özellikleri olmayan bağımsız değişkenleri tanımlar.

## <a name="rule-description"></a>Kural açıklaması
Öznitelikler özniteliği işaretlediğinizde özelleştirilen zorunlu bağımsız değişkenleri tanımlayabilir. Ayrıca bunlar konum parametreleri olarak öznitelik yapıcısına verildiğinden duruma bağlı bağımsız değişkenler olarak da bilinirler. Zorunlu her bağımsız değişken için bağımsız değişkenin değeri yürütme zamanından alınması gerektiğinden öznitelik ilgili salt okunur özelliği de sağlamalıdır. Bu kural, her Oluşturucu parametresi için ilgili özelliği tanımladınız olduğunu denetler.

Öznitelikler adlandırılmış bağımsız değişkenler olarak bilinen duruma bağlı bağımsız değişkenler olarak da tanımlanabilir. Bu bağımsız öznitelik oluşturucular ad tarafından sağlanır ve karşılık gelen bir okuma/yazma özelliğine sahip olmalıdır.

Zorunlu ve isteğe bağlı bağımsız değişkenler için, karşılık gelen özellikler ve Oluşturucu parametreleri aynı adı ancak büyük küçük harfleri kullanmalıdır. Özellikler, Pascal büyük harfleri kullanır ve parametreler ortası büyük harfleri kullanır.

## <a name="how-to-fix-violations"></a>İhlalleri çözme
Bu kuralın ihlalini onarmak için, bir tane olmayan her bir oluşturucu parametresi için salt okunurdur bir özellik ekleyin.

## <a name="when-to-suppress-warnings"></a>Uyarıların ne zaman bastırılamıyor
Zorunlu bağımsız değişkenin değerinin alınabilir olmasını istemiyorsanız bu kuraldan bir uyarı gizleyin.

## <a name="custom-attributes-example"></a>Özel öznitelikler örneği

Aşağıdaki örnek, zorunlu (konumsal) bir parametre tanımlayan iki özniteliği gösterir. Özniteliğin ilk uygulanması yanlış tanımlanmış. İkinci uygulama doğru.

[!code-csharp[FxCop.Design.AttributeAccessors#1](../code-quality/codesnippet/CSharp/ca1019-define-accessors-for-attribute-arguments_1.cs)]
[!code-vb[FxCop.Design.AttributeAccessors#1](../code-quality/codesnippet/VisualBasic/ca1019-define-accessors-for-attribute-arguments_1.vb)]

## <a name="positional-and-named-arguments"></a>Konumsal ve adlandırılmış bağımsız değişkenler

Konumsal ve adlandırılmış bağımsız değişkenler, kitaplığınızın tüketicilerine açık hale getirir ve bu bağımsız değişkenler öznitelik için zorunludur ve hangi bağımsız değişkenler isteğe bağlıdır.

Aşağıdaki örnek, hem Konumsal hem de adlandırılmış bağımsız değişkenlere sahip bir özniteliğin bir uygulamasını gösterir:

[!code-csharp[FxCop.Design.AttributeAccessorsNamed#1](../code-quality/codesnippet/CSharp/ca1019-define-accessors-for-attribute-arguments_2.cs)]

Aşağıdaki örnek, özel özniteliğin iki özelliğe nasıl uygulanacağını gösterir:

[!code-csharp[FxCop.Design.AttributeAccessorsNamedApplied#1](../code-quality/codesnippet/CSharp/ca1019-define-accessors-for-attribute-arguments_3.cs)]

## <a name="related-rules"></a>İlgili kurallar
[CA1813 Korumasız özniteliklerden kaçının](../code-quality/ca1813-avoid-unsealed-attributes.md)

## <a name="see-also"></a>Ayrıca bkz.
[Öznitelikler](/dotnet/standard/design-guidelines/attributes)