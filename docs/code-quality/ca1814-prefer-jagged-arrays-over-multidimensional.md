---
title: 'CA1814: Çok boyutlu diziler yerine basit dizileri tercih edin'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- PreferJaggedArraysOverMultidimensional
- CA1814
helpviewer_keywords:
- PreferJaggedArraysOverMultidimensional
- CA1814
ms.assetid: b1ccf563-2ec8-42e5-b89c-731a9de1ea1d
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: e2c7e7efe348526661b9de74b3631e6795608b99
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68921344"
---
# <a name="ca1814-prefer-jagged-arrays-over-multidimensional"></a>CA1814: Çok boyutlu diziler yerine basit dizileri tercih edin

|||
|-|-|
|TypeName|PreferJaggedArraysOverMultidimensional|
|CheckId|CA1814|
|Kategori|Microsoft. Performance|
|Yeni Değişiklik|Yeni|

## <a name="cause"></a>Sebep
Bir üye çok boyutlu bir dizi olarak bildirilmiştir.

## <a name="rule-description"></a>Kural açıklaması
Basit bir dizi, öğeleri dizi olan bir dizidir. Öğeleri olan diziler bazı veri kümeler için daha az harcanmış önde gelen farklı boyutlarda olabilir.

## <a name="how-to-fix-violations"></a>İhlalleri çözme
Bu kural ihlalini onarmak için, çok boyutlu diziyi pürüzlü bir dizi olarak değiştirin.

## <a name="when-to-suppress-warnings"></a>Uyarıların ne zaman bastırılamıyor
Çok boyutlu dizi alanı atık olarak içermiyorsa, bu kuraldan bir uyarı gizleyin.

## <a name="example"></a>Örnek
Aşağıdaki örnek, pürüzlü ve çok boyutlu diziler için bildirimleri gösterir.

[!code-vb[FxCop.Performance.JaggedArrays#1](../code-quality/codesnippet/VisualBasic/ca1814-prefer-jagged-arrays-over-multidimensional_1.vb)]
[!code-csharp[FxCop.Performance.JaggedArrays#1](../code-quality/codesnippet/CSharp/ca1814-prefer-jagged-arrays-over-multidimensional_1.cs)]