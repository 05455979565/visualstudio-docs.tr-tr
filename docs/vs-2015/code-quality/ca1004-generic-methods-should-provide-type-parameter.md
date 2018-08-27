---
title: 'CA1004: Genel metotlar tür parametresi sağlamalıdır | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- CA1004
- GenericMethodsShouldProvideTypeParameter
helpviewer_keywords:
- GenericMethodsShouldProvideTypeParameter
- CA1004
ms.assetid: 38755f6a-fb45-4bf2-932e-0354ad826499
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: bb32ab837ce7431f90c6a7ccdc178aa62b8145cf
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/24/2018
ms.locfileid: "42901727"
---
# <a name="ca1004-generic-methods-should-provide-type-parameter"></a>CA1004: Genel metotlar tür parametresi sağlamalıdır
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CA1004: Genel metotlar tür parametresi sağlamalıdır](https://docs.microsoft.com/visualstudio/code-quality/ca1004-generic-methods-should-provide-type-parameter).

|||
|-|-|
|TypeName|GenericMethodsShouldProvideTypeParameter|
|CheckId|CA1004|
|Kategori|Microsoft.Design|
|Yeni Değişiklik|Yeni|

## <a name="cause"></a>Sebep
 Dışarıdan görünen bir genel yöntem parametre imzası tüm tür parametreleri yöntemi için karşılık gelen tür içermiyor.

## <a name="rule-description"></a>Kural Tanımı
 Tip argümanının açıkça özelleştirilmesi yerine yöntemi geçen argüman tipiyle tanımlanan genel yöntemin nasıl tip argümanı olduğunun sonucudur. Çıkarımı etkinleştirmek için bir genel yöntem parametre imzası yöntem türü parametresi gibi aynı türde bir parametre içermelidir. Bu durumda, tip bağımsız değişkeninin belirtilmesine gerek yoktur. Tüm tip parametreleri için çıkarım kullandığınızda jenerik ve jenerik olmayan örnek yöntemleri için sözdizimi aynıdır. Bu kullanılabilirlik genel yöntemlerin kullanımını kolaylaştırır.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Bu kural ihlalini düzeltmek için parametre imzası yöntem her tür parametresi için aynı türü içeren tasarım değiştirin.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Bu kuraldan uyarıyı bastırmayın. Genel türler anlaşılması ve kullanımı kolay bir sözdizimindeki sağlama öğrenmek için gerekli olan ve yeni kitaplıkları benimseme oranını artırır süreyi azaltır.

## <a name="example"></a>Örnek
 Aşağıdaki örnek, iki genel yöntem çağırma söz dizimini gösterir. Tür bağımsız değişkeni `InferredTypeArgument` algılanır ve tür bağımsız değişkeni `NotInferredTypeArgument` açıkça belirtilmesi gerekir.

 [!code-csharp[FxCop.Design.Inference#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.Inference/cs/FxCop.Design.Inference.cs#1)]
 [!code-vb[FxCop.Design.Inference#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.Inference/vb/FxCop.Design.Inference.vb#1)]

## <a name="related-rules"></a>İlgili kuralları
 [CA1005: Genel türlerde aşırı parametrelerden kaçının](../code-quality/ca1005-avoid-excessive-parameters-on-generic-types.md)

 [CA1010: Koleksiyonlar genel arabirim uygulamalıdır](../code-quality/ca1010-collections-should-implement-generic-interface.md)

 [CA1000: Genel türlerde statik üyeleri belirtme](../code-quality/ca1000-do-not-declare-static-members-on-generic-types.md)

 [CA1002: Genel listeleri gösterme](../code-quality/ca1002-do-not-expose-generic-lists.md)

 [CA1006: Üye imzalarında genel türleri iç içe kullanmayın](../code-quality/ca1006-do-not-nest-generic-types-in-member-signatures.md)

 [CA1003: Genel olay işleyici örnekleri kullan](../code-quality/ca1003-use-generic-event-handler-instances.md)

 [CA1007: Uygun yerlerde genel türler kullanın](../code-quality/ca1007-use-generics-where-appropriate.md)