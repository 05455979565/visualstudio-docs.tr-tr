---
title: 'CA2235: tüm serileştirilebilir olmayan alanları işaretleyin | Microsoft Docs'
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
- CA2235
- MarkAllNonSerializableFields
helpviewer_keywords:
- CA2235
- MarkAllNonSerializableFields
ms.assetid: 599ad877-3a15-426c-bf17-5de15427365f
caps.latest.revision: 15
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 641f9c4dc5deec777ed4a0f74a920fc73e6af3d8
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42691449"
---
# <a name="ca2235-mark-all-non-serializable-fields"></a>CA2235: Tüm serileştirilebilir olmayan alanları işaretleyin
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CA2235: tüm serileştirilebilir olmayan alanları işaretleyin](https://docs.microsoft.com/visualstudio/code-quality/ca2235-mark-all-non-serializable-fields).  
  
TypeName | MarkAllNonSerializableFields |  
| Checkıd | CA2235 |  
| Kategori | Microsoft.Usage|  
| Yeni değişiklik | Olmayan yeni |  
  
## <a name="cause"></a>Sebep  
 Seri hale getirilemeyen bir örnek alan türü seri hale getirilebilir bir tür içinde bildirilir.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Seri hale getirilebilir bir tür ile işaretlenmiş biridir <xref:System.SerializableAttribute?displayProperty=fullName> özniteliği. Türü seri olduğunda, bir <xref:System.Runtime.Serialization.SerializationException?displayProperty=fullName> serileştirilebilir değil bir türde bir örnek alanıyla bir tür içeriyorsa, özel durum harekete geçirilir.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlalini düzeltmek için geçerli <xref:System.NonSerializedAttribute?displayProperty=fullName> getirilemeyen alanına öznitelik.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Yalnızca, bu kuraldan bir uyarıyı bastırmak bir <xref:System.Runtime.Serialization.ISerializationSurrogate?displayProperty=fullName> türü bildirilen serileştirilmiş ve seri durumdan alanın örneklerini sağlar.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, kuralını ihlal eden bir tür ile kural karşılayan bir tür gösterir.  
  
 [!code-csharp[FxCop.Usage.MarkNonSerializable#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.MarkNonSerializable/cs/FxCop.Usage.MarkNonSerializable.cs#1)]
 [!code-vb[FxCop.Usage.MarkNonSerializable#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Usage.MarkNonSerializable/vb/FxCop.Usage.MarkNonSerializable.vb#1)]  
  
## <a name="related-rules"></a>İlgili kuralları  
 [CA2236: ISerializable türler üzerinde taban sınıf yöntemlerini çağırın](../code-quality/ca2236-call-base-class-methods-on-iserializable-types.md)  
  
 [CA2240: ISerializable'ı doğru uygulayın](../code-quality/ca2240-implement-iserializable-correctly.md)  
  
 [CA2229: Serileştirme oluşturucularını uygulayın](../code-quality/ca2229-implement-serialization-constructors.md)  
  
 [CA2238: Serileştirme yöntemlerini doğru uygulama](../code-quality/ca2238-implement-serialization-methods-correctly.md)  
  
 [CA2237: ISerializable türleri SerializableAttribute ile işaretleyin](../code-quality/ca2237-mark-iserializable-types-with-serializableattribute.md)  
  
 [CA2239: İsteğe bağlı alanlar için seri durumdan çıkarma metotları sağlayın](../code-quality/ca2239-provide-deserialization-methods-for-optional-fields.md)  
  
 [CA2120: Serileştirme oluşturucularının güvenliğini sağlayın](../code-quality/ca2120-secure-serialization-constructors.md)



