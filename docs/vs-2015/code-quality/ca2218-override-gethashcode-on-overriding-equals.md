---
title: "CA2218: geçersiz kılma eşittir geçersiz kılma Gethashcode'u | Microsoft Docs"
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
- CA2218
- OverrideGetHashCodeOnOverridingEquals
helpviewer_keywords:
- OverrideGetHashCodeOnOverridingEquals
- CA2218
ms.assetid: 69b020cd-29e8-45a6-952e-32cf3ce2e21d
caps.latest.revision: 22
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: cf8fb22f5cfd6b5a9752077f11c47076b504b46c
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42694926"
---
# <a name="ca2218-override-gethashcode-on-overriding-equals"></a>CA2218: GetHashCode'u Eşittir'i geçersiz kılarak geçersiz kılın
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CA2218: Gethashcode'u eşittir geçersiz kılma üzerinde geçersiz kılma](https://docs.microsoft.com/visualstudio/code-quality/ca2218-override-gethashcode-on-overriding-equals).

TypeName | OverrideGetHashCodeOnOverridingEquals | | Checkıd | CA2218 | | Kategori | Microsoft.Usage| | Yeni değişiklik | Olmayan yeni |

## <a name="cause"></a>Sebep
 Geçersiz kılma genel bir türü <xref:System.Object.Equals%2A?displayProperty=fullName> ancak geçersiz <xref:System.Object.GetHashCode%2A?displayProperty=fullName>.

## <a name="rule-description"></a>Kural Tanımı
 <xref:System.Object.GetHashCode%2A> karma algoritmalar ve karma tablo gibi veri yapıları için uygun olan geçerli örneği temel alarak bir değeri döndürür. Aynı türdeki ve eşit olan iki nesne türlerinden birini örnekleri doğru şekilde çalıştığından emin olmak için aynı karma kodu döndürmesi gerekir:

-   <xref:System.Collections.Hashtable?displayProperty=fullName>

-   <xref:System.Collections.SortedList?displayProperty=fullName>

-   <xref:System.Collections.Generic.Dictionary%602?displayProperty=fullName>

-   <xref:System.Collections.Generic.SortedDictionary%602?displayProperty=fullName>

-   <xref:System.Collections.Generic.SortedList%602?displayProperty=fullName>

-   <xref:System.Collections.Specialized.HybridDictionary?displayProperty=fullName>

-   <xref:System.Collections.Specialized.ListDictionary?displayProperty=fullName>

-   <xref:System.Collections.Specialized.OrderedDictionary?displayProperty=fullName>

-   Uygulayan türler <xref:System.Collections.Generic.IEqualityComparer%601?displayProperty=fullName>

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Bu kural ihlalini düzeltmek için bir uygulamasını sağlamak <xref:System.Object.GetHashCode%2A>. Nesnelerin aynı türden bir çift uygulama aynı değeri döndürdüğünü emin olmalısınız uygulamanıza <xref:System.Object.Equals%2A> döndürür `true` çifti için.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Bu kuraldan uyarıyı bastırmayın.

## <a name="class-example"></a>Sınıf örneği

### <a name="description"></a>Açıklama
 Aşağıdaki örnek bu kuralı ihlal eden bir sınıf (başvuru türü) gösterir.

### <a name="code"></a>Kod
 [!code-csharp[FxCop.Usage.GetHashCodeErrorClass#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.GetHashCodeErrorClass/cs/FxCop.Usage.GetHashCodeErrorClass.cs#1)]

### <a name="comments"></a>Açıklamalar
 Aşağıdaki örnek, geçersiz kılarak ihlali düzeltmeleri <xref:System.Object.GetHashCode>.

### <a name="code"></a>Kod
 [!code-csharp[FxCop.Usage.GetHashCodeFixedClass#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.GetHashCodeFixedClass/cs/FxCop.Usage.GetHashCodeFixedClass.cs#1)]

## <a name="structure-example"></a>Yapısı örneği

### <a name="description"></a>Açıklama
 Aşağıdaki örnek bu kuralı ihlal eden bir yapı (değer türü) gösterir.

### <a name="code"></a>Kod
 [!code-csharp[FxCop.Usage.GetHashCodeErrorStruct#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.GetHashCodeErrorStruct/cs/FxCop.Usage.GetHashCodeErrorStruct.cs#1)]

### <a name="comments"></a>Açıklamalar
 Aşağıdaki örnek, geçersiz kılarak ihlali düzeltmeleri <xref:System.Object.GetHashCode>.

### <a name="code"></a>Kod
 [!code-csharp[FxCop.Usage.GetHashCodeFixedStruct#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.GetHashCodeFixedStruct/cs/FxCop.Usage.GetHashCodeFixedStruct.cs#1)]

## <a name="related-rules"></a>İlgili kuralları
 [CA1046: Başvuru türlerinde eşittir işleçlerini aşırı yüklemeyin](../code-quality/ca1046-do-not-overload-operator-equals-on-reference-types.md)

 [CA2225: İşleç aşırı yüklemeleri adlandırılmış alternatiflere sahiptir](../code-quality/ca2225-operator-overloads-have-named-alternates.md)

 [CA2226: İşleçler simetrik aşırı yüklemelere sahip olmalıdır](../code-quality/ca2226-operators-should-have-symmetrical-overloads.md)

 [CA2224: Eşittir işlecini aşırı yükleyerek eşittiri geçersiz kılın](../code-quality/ca2224-override-equals-on-overloading-operator-equals.md)

 [CA2231: ValueType.Equals değerini geçersiz kılmada eşittir işlecini aşırı yükle](../code-quality/ca2231-overload-operator-equals-on-overriding-valuetype-equals.md)

## <a name="see-also"></a>Ayrıca bkz.

- <xref:System.Object.Equals%2A?displayProperty=fullName>
- <xref:System.Object.GetHashCode%2A?displayProperty=fullName>
- <xref:System.Collections.Hashtable?displayProperty=fullName>
- [Eşitlik İşleçleri](http://msdn.microsoft.com/library/bc496a91-fefb-4ce0-ab4c-61f09964119a)