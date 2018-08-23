---
title: 'CA1819: Özellikler diziler döndürmemelidir | Microsoft Docs'
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
- PropertiesShouldNotReturnArrays
- CA1819
helpviewer_keywords:
- PropertiesShouldNotReturnArrays
- CA1819
ms.assetid: 85fcf312-57f8-438a-8b10-34441fe0bdeb
caps.latest.revision: 24
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 3bdb25dc2216d71e975b8f376e1682a92dd00cd9
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42691901"
---
# <a name="ca1819-properties-should-not-return-arrays"></a>CA1819: Özellikler diziler döndürmemelidir
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CA1819: özellikler diziler döndürmemelidir](https://docs.microsoft.com/visualstudio/code-quality/ca1819-properties-should-not-return-arrays).  
  
TypeName | PropertiesShouldNotReturnArrays |  
| Checkıd | CA1819 |  
| Kategori | Microsoft.Performance|  
| Yeni değişiklik | Bozucu |  
  
## <a name="cause"></a>Sebep  
 Ortak türde ortak veya korumalı bir özellik, bir dizi döndürür.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Özellik salt okunur olsa bile özellikleri tarafından döndürülen dizi yazma korumalı değildir. Dizi değiştirilmeye kanıt tutulacak özellik dizisinin bir kopyasını döndürmelidir. Tipik olarak, kullanıcılar bu tür bir özellik aramanın performans üzerindeki olumsuz etkilerini anlamayacaktır. Özellikle, bunlar bir dizinlenmiş özellik olarak özelliğini kullanabilirsiniz.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlalini düzeltmek için özelliği bir yöntem yapın veya özelliği bir koleksiyon döndürecek şekilde değiştirin.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Öznitelikler, dizi döndüren özellikler içerebilir, ancak koleksiyon döndüren özellikler içeremez. [] System.Attribute türevi bir öznitelik bir özellik için oluşturulan bir uyarı gizleyebilirsiniz (<!-- TODO: review code entity reference <xref:assetId:///System.Attribute?qualifyHint=False&amp;autoUpgrade=True>  -->) sınıfı. Aksi takdirde, bu kuraldan bir uyarıyı bastırmayın.  
  
## <a name="example-violation"></a>Örnek ihlali  
  
### <a name="description"></a>Açıklama  
 Aşağıdaki örnek bu kuralı ihlal eden bir özellik gösterilmiştir.  
  
### <a name="code"></a>Kod  
 [!code-csharp[FxCop.Performance.PropertyArrayViolation#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Performance.PropertyArrayViolation/cs/FxCop.Performance.PropertyArrayViolation.cs#1)]
 [!code-vb[FxCop.Performance.PropertyArrayViolation#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Performance.PropertyArrayViolation/vb/FxCop.Performance.PropertyArrayViolation.vb#1)]  
  
### <a name="comments"></a>Açıklamalar  
 Bu kural ihlalini düzeltmek için özelliği bir yöntem yapın veya özelliği bir dizi yerine bir koleksiyon döndürecek şekilde değiştirin.  
  
## <a name="change-the-property-to-a-method-example"></a>Özelliğini yöntemi örneği  
  
### <a name="description"></a>Açıklama  
 Aşağıdaki örnek, bir yönteme özelliğini değiştirerek ihlali düzeltir.  
  
### <a name="code"></a>Kod  
 [!code-csharp[FxCop.Performance.PropertyArrayFixedMethod#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Performance.PropertyArrayFixedMethod/cs/FxCop.Performance.PropertyArrayFixedMethod.cs#1)]
 [!code-vb[FxCop.Performance.PropertyArrayFixedMethod#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Performance.PropertyArrayFixedMethod/vb/FxCop.Performance.PropertyArrayFixedMethod.vb#1)]  
  
## <a name="return-a-collection-example"></a>Bir koleksiyon örneği döndürür.  
  
### <a name="description"></a>Açıklama  
 Aşağıdaki örnek, döndürülecek özelliği değiştirilerek ihlali giderir bir  
  
 <xref:System.Collections.ObjectModel.ReadOnlyCollection%601?displayProperty=fullName>.  
  
### <a name="code"></a>Kod  
 [!code-csharp[FxCop.Performance.PropertyArrayFixedCollection#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Performance.PropertyArrayFixedCollection/cs/FxCop.Performance.PropertyArrayFixedCollection.cs#1)]
 [!code-vb[FxCop.Performance.PropertyArrayFixedCollection#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Performance.PropertyArrayFixedCollection/vb/FxCop.Performance.PropertyArrayFixedCollection.vb#1)]  
  
## <a name="allowing-users-to-modify-a-property"></a>Kullanıcıların bir özelliği değiştirmek için  
  
### <a name="description"></a>Açıklama  
 Bir özelliği değiştirmek tüketici sınıfı izin vermek isteyebilirsiniz. Aşağıdaki örnek bu kuralı ihlal eden bir okuma/yazma özelliği gösterir.  
  
### <a name="code"></a>Kod  
 [!code-csharp[FxCop.Performance.PropertyModifyViolation#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Performance.PropertyModifyViolation/cs/FxCop.Performance.PropertyModifyViolation.cs#1)]
 [!code-vb[FxCop.Performance.PropertyModifyViolation#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Performance.PropertyModifyViolation/vb/FxCop.Performance.PropertyModifyViolation.vb#1)]  
  
### <a name="comments"></a>Açıklamalar  
 Aşağıdaki örnek, döndürülecek özelliği değiştirilerek ihlali giderir bir <xref:System.Collections.ObjectModel.Collection%601?displayProperty=fullName>.  
  
### <a name="code"></a>Kod  
 [!code-csharp[FxCop.Performance.PropertyModifyFixed#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Performance.PropertyModifyFixed/cs/FxCop.Performance.PropertyModifyFixed.cs#1)]
 [!code-vb[FxCop.Performance.PropertyModifyFixed#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Performance.PropertyModifyFixed/vb/FxCop.Performance.PropertyModifyFixed.vb#1)]  
  
## <a name="related-rules"></a>İlgili kuralları  
 [CA1024: Uygun yerlerde özellikler kullanın](../code-quality/ca1024-use-properties-where-appropriate.md)



