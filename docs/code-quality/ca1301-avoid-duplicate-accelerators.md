---
title: 'CA1301: Yinelenen hızlandırıcılardan kaçının'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA1301
- AvoidDuplicateAccelerators
helpviewer_keywords:
- CA1301
- AvoidDuplicateAccelerators
ms.assetid: 20570a00-864b-459c-a1fa-a6e9db5f1001
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 16cd44f00db13027d737b6a6b496877075ac6fa9
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68922273"
---
# <a name="ca1301-avoid-duplicate-accelerators"></a>CA1301: Yinelenen hızlandırıcılardan kaçının

|||
|-|-|
|TypeName|AvoidDuplicateAccelerators|
|CheckId|CA1301|
|Kategori|Microsoft. Globalization|
|Yeni Değişiklik|Kırılmamış|

## <a name="cause"></a>Sebep
Bir tür, <xref:System.Windows.Forms.Control?displayProperty=fullName> bir kaynak dosyasında depolanan özdeş erişim anahtarlarına sahip iki veya daha fazla üst düzey denetimi genişletir ve içerir.

## <a name="rule-description"></a>Kural açıklaması

Hızlandırıcı olarak da bilinen bir erişim anahtarı, **alt** tuşunu kullanarak bir denetime klavye erişimi sağlar. Birden çok denetim aynı erişim anahtarına sahip olduğunda, erişim anahtarının davranışı iyi tanımlanmamıştır. Kullanıcı, erişim anahtarını kullanarak amaçlanan denetime erişemeyebilir ve hedeflenen bir denetim etkinleştirilebilir. Bu, bir denetim etkin olabilir.

Bu kuralın geçerli uygulanması menü öğelerini yoksayar. Ancak, aynı alt menüdeki menü öğeleri aynı erişim anahtarlarına sahip olmamalıdır.

## <a name="how-to-fix-violations"></a>İhlalleri çözme
Bu kuralın ihlalini onarmak için, tüm denetimler için benzersiz erişim anahtarları tanımlayın.

## <a name="when-to-suppress-warnings"></a>Uyarıların ne zaman bastırılamıyor
Bu kuraldan uyarıyı bastırmayın.

## <a name="example"></a>Örnek
Aşağıdaki örnekte, aynı erişim anahtarlarına sahip iki denetim içeren en az bir form gösterilmektedir. Anahtarlar, gösterilmemiş bir kaynak dosyasında depolanır. Ancak, değerleri, açıklamalı `checkBox.Text` satırlarda görüntülenir. Yinelenen hızlandırıcıların davranışı, `checkBox.Text` satırları açıklamalı çıkış karşılıklarıyla birlikte değiş tokuşu yaparak incelenebilir. Ancak, bu durumda, örnek kuraldan bir uyarı oluşturmaz.

[!code-csharp[FxCop.Globalization.AvoidDuplicateAccels#1](../code-quality/codesnippet/CSharp/ca1301-avoid-duplicate-accelerators_1.cs)]

## <a name="see-also"></a>Ayrıca bkz.

- <xref:System.Resources.ResourceManager?displayProperty=fullName>
- [Masaüstü Uygulamalarındaki Kaynaklar](/dotnet/framework/resources/index)