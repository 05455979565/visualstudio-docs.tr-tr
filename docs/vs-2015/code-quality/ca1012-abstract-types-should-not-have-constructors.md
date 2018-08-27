---
title: 'CA1012: Soyut türlerde oluşturucular bulunmamalıdır | Microsoft Docs'
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
- AbstractTypesShouldNotHaveConstructors
- CA1012
helpviewer_keywords:
- CA1012
ms.assetid: 09f458ac-dd88-4cd7-a47f-4106c1e80ece
caps.latest.revision: 27
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 692dfc0ad69cf4d71d82953e2cc9965733915dc6
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/24/2018
ms.locfileid: "42901796"
---
# <a name="ca1012-abstract-types-should-not-have-constructors"></a>CA1012: Soyut türlerde oluşturucular bulunmamalıdır
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CA1012: soyut türlerin oluşturucuları olmamalıdır](https://docs.microsoft.com/visualstudio/code-quality/ca1012-abstract-types-should-not-have-constructors).

|||
|-|-|
|TypeName|AbstractTypesShouldNotHaveConstructors|
|CheckId|CA1012|
|Kategori|Microsoft.Design|
|Yeni Değişiklik|Bölünemez|

## <a name="cause"></a>Sebep
 Genel bir türü soyuttur ve ortak yapıcıya sahip.

## <a name="rule-description"></a>Kural Tanımı
 Soyut türler üzerindeki kurucular yalnızca türetilen türler tarafından çağrılabilir. Ortak yapıcılar türün bir örneğini yaptığından ve siz bir soyut türün örneğini yapamayacağınızdan, soyut sınıf hatalı biçimde dizayn edilmiş ortak yapıcıya sahip olur.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Bu kural ihlalini düzeltmek için korumalı Oluşturucu olun veya türü soyut olarak bildirmeyin.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Bu kuraldan uyarıyı bastırmayın. Soyut tür, genel bir oluşturucusu vardır.

## <a name="example"></a>Örnek
 Aşağıdaki örnek bu kuralı ihlal soyut bir tür içeriyor.

 [!code-csharp[FxCop.Design.AbstractTypeBad#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.AbstractTypeBad/cs/FxCop.Design.AbstractTypeBad.cs#1)]
 [!code-vb[FxCop.Design.AbstractTypeBad#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.AbstractTypeBad/vb/FxCop.Design.AbstractTypeBad.vb#1)]

## <a name="example"></a>Örnek
 Aşağıdaki örnek önceki ihlali oluşturucudan erişilebilirliğini değiştirerek giderir `public` için `protected`.

 [!code-csharp[FxCop.Design.AbstractTypeGood#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.AbstractTypeGood/cs/FxCop.Design.AbstractTypeGood.cs#1)]
 [!code-vb[FxCop.Design.AbstractTypeGood#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Design.AbstractTypeGood/vb/FxCop.Design.AbstractTypeGood.vb#1)]



