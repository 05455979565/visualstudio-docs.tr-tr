---
title: 'CA1000: Genel türlerde statik üyeleri bildirmeyin | Microsoft Docs'
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
- CA1000
- DoNotDeclareStaticMembersOnGenericTypes
helpviewer_keywords:
- DoNotDeclareStaticMembersOnGenericTypes
- CA1000
ms.assetid: 5c0da594-f8d0-4f40-953d-56bf7fbd2087
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 3b04eb787efae7b35e2be086e517fb78d5af526b
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42631038"
---
# <a name="ca1000-do-not-declare-static-members-on-generic-types"></a>CA1000: Genel türlerde statik üyeleri belirtme
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CA1000: Genel türlerde statik üyeleri bildirmeyin](https://docs.microsoft.com/visualstudio/code-quality/ca1000-do-not-declare-static-members-on-generic-types).  
  
TypeName | DoNotDeclareStaticMembersOnGenericTypes |  
| Checkıd | CA1000 |  
| Kategori | Microsoft.Design|  
| Yeni değişiklik | Bozucu |  
  
## <a name="cause"></a>Sebep  
 Dışarıdan görünen bir genel tür içeren bir `static` (`Shared` Visual Basic'te) üye.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Olduğunda bir `static` genel bir tür üyesi çağrıldığında, tür bağımsız değişkeni türü için belirtilmesi gerekir. Destek çıkarımı desteklenmeyen genel örnek üyesi çağrıldığında tür bağımsız değişkeni üye için belirlenmelidir. Aşağıdaki çağrıları göz atarak bu iki durumda tür bağımsız değişkeni belirtmek için sözdizimi farklıdır ve kolaylıkla karıştırılır aşağıdaki gibidir:  
  
```vb  
' Shared method in a generic type.  
GenericType(Of Integer).SharedMethod()  
  
' Generic instance method that does not support inference.  
someObject.GenericMethod(Of Integer)()  
```  
  
```csharp  
// Static method in a generic type.  
GenericType<int>.StaticMethod();  
  
// Generic instance method that does not support inference.  
someObject.GenericMethod<int>();  
```  
  
 Genellikle, tür bağımsız değişkeni, üye ne zaman çağrıldığını belirtilmesi gerekmez. böylece hem de önceki bildirimler kaçınılmalıdır. Bu arama üyeler söz genel olmayan türler için farklı bir genel türler için bir sözdiziminde sonuçlanır. Daha fazla bilgi için [CA1004: Genel metotlar tür parametresi sağlamalıdır](../code-quality/ca1004-generic-methods-should-provide-type-parameter.md).  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlalini düzeltmek için statik üye kaldırma veya bir örnek üyesi için değiştirin.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan uyarıyı bastırmayın. Genel türler anlaşılması ve kullanımı kolay bir sözdizimindeki sağlama öğrenmek için gerekli olan ve yeni kitaplıkları benimseme oranını artırır süreyi azaltır.  
  
## <a name="related-rules"></a>İlgili kuralları  
 [CA1005: Genel türlerde aşırı parametrelerden kaçının](../code-quality/ca1005-avoid-excessive-parameters-on-generic-types.md)  
  
 [CA1010: Koleksiyonlar genel arabirim uygulamalıdır](../code-quality/ca1010-collections-should-implement-generic-interface.md)  
  
 [CA1002: Genel listeleri gösterme](../code-quality/ca1002-do-not-expose-generic-lists.md)  
  
 [CA1006: Üye imzalarında genel türleri iç içe kullanmayın](../code-quality/ca1006-do-not-nest-generic-types-in-member-signatures.md)  
  
 [CA1004: Genel metotlar tür parametresi sağlamalıdır](../code-quality/ca1004-generic-methods-should-provide-type-parameter.md)  
  
 [CA1003: Genel olay işleyici örnekleri kullan](../code-quality/ca1003-use-generic-event-handler-instances.md)  
  
 [CA1007: Uygun yerlerde genel türler kullanın](../code-quality/ca1007-use-generics-where-appropriate.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Genel Türler](http://msdn.microsoft.com/library/75ea8509-a4ea-4e7a-a2b3-cf72482e9282)



