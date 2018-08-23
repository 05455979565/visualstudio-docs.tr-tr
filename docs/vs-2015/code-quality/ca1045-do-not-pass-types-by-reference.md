---
title: 'CA1045: türleri başvuruya göre geçirmeyin | Microsoft Docs'
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
- CA1045
- DoNotPassTypesByReference
helpviewer_keywords:
- CA1045
- DoNotPassTypesByReference
ms.assetid: bcc3900a-e092-4bb8-896f-cb83f6289968
caps.latest.revision: 20
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 8bca9c62c173297aeddc88321a41244de89617f9
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42692750"
---
# <a name="ca1045-do-not-pass-types-by-reference"></a>CA1045: Türleri başvuruya göre geçirmeyin
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CA1045: türleri başvuruya göre geçirmeyin](https://docs.microsoft.com/visualstudio/code-quality/ca1045-do-not-pass-types-by-reference).  
  
TypeName | DoNotPassTypesByReference |  
| Checkıd | CA1045 |  
| Kategori | Microsoft.Design|  
| Yeni değişiklik | Bozucu |  
  
## <a name="cause"></a>Sebep  
 Ortak türde ortak veya korumalı bir yöntem olan bir `ref` ilkel tür, bir başvuru türü veya değer türü alan parametresi yerleşik türlerden biri değil.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Türleri başvuruya göre geçirme (kullanarak `out` veya `ref`) değer türleri ve başvuru türleri farkı anlama ve işleme birden çok değer yöntemi işaretçileri deneyimiyle gerektirir. Ayrıca, arasındaki farkı `out` ve `ref` parametreleri anlaşılmadı.  
  
 Bir başvuru türü "başvuruya göre" geçirildiğinde, parametre nesnesinin farklı bir örneğine geri dönmek için kullanılacak yöntemi amaçlamaktadır. (Bir başvuru türü başvuruya göre geçirme da çift işaretçisi, bir işaretçi veya çift yöneltme işaretçisi kullanılarak olarak bilinir.) Zaten bir başvuru türü alan bir parametre için varsayılan çağırma kuralı, "değeriyle" geçti kullanarak nesneye bir işaretçi alır. İşaretçi, işaret ettiği, nesnenin değil değere göre geçirilir. Yöntemi, işaretçi, başvuru yeni bir örneğine işaret edecek şekilde değiştiremezsiniz anlamına gelir yazın, ancak işaret ettiği nesnenin içeriğini değiştirebilirsiniz değere göre geçirme. Çoğu uygulama için bu yeterli olur ve istediğiniz davranışı üretir.  
  
 Bir yöntem başka bir örneği döndürmelidir, bunu gerçekleştirmek için yöntemin dönüş değerini kullanın. Bkz: <xref:System.String?displayProperty=fullName> sınıfı için çeşitli yöntemler dizeler üzerinde çalışan ve bir dize yeni bir örneğini döndürür. Bu modeli kullanarak, özgün nesneye korunup korunmayacağını karar arayana bırakılır.  
  
 Dönüş değerleri sıradan bir hale ve yoğun olarak kullanılan, doğru uygulama olsa da `out` ve `ref` Ara tasarım ve kodlama becerilerinde parametrelerine gereksinim duyar. Genel kitle asıl kullanıcılara beklememelidir bilgilendirmelidir tasarım Kütüphane mimarları `out` veya `ref` parametreleri.  
  
> [!NOTE]
>  Büyük yapılar olan parametreler ile çalışırken, değere göre geçirdiğinizde bu yapıları kopyalamak için gereken ek kaynakları bir performans etkisi neden olabilir. Bu gibi durumlarda kullanmayı düşünebilirsiniz `ref` veya `out` parametreleri.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bir değer türü tarafından neden bu kural ihlalini düzeltmek için yöntemin dönüş değeri olarak nesneyi döndürmek sahip. Yöntemi, birden çok değer döndürmelidir, tek bir örneği değerleri içeren nesneyi döndürmek için yeniden tasarlayın.  
  
 Bir başvuru türüne göre neden bu kural ihlalini düzeltmek için istediğiniz davranışı başvurusu yeni bir örneğini döndürülecek olduğundan emin olun. İse, bunu yapmak için yöntemin dönüş değerini kullanmanız gerekir.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan bir uyarıyı bastırmak güvenlidir; Ancak, bu tasarım, kullanılabilirlik sorunları neden olabilir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki Kitaplık kullanıcının geri bildirim yanıtlarını oluşturan bir sınıfın iki uygulamaları gösterir. İlk uygulama (`BadRefAndOut`) kitaplığı üç dönüş değerleri yönetme açmaya zorlar. İkinci uygulama (`RedesignedRefAndOut`) bir kapsayıcı sınıfının bir örneğini döndürerek kullanıcı deneyimini basitleştirir (`ReplyData`), verileri tek bir birim olarak yönetir.  
  
 [!code-csharp[FxCop.Design.NoRefOrOut#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.NoRefOrOut/cs/FxCop.Design.NoRefOrOut.cs#1)]  
  
## <a name="example"></a>Örnek  
 Aşağıdaki uygulama, kullanıcı deneyimini gösterir. Yeniden tasarlanan kitaplık çağrısı (`UseTheSimplifiedClass` yöntemi) daha basit ve yöntem tarafından döndürülen bilgileri kolayca yönetilebilir. İki yöntem çıkışı aynıdır.  
  
 [!code-csharp[FxCop.Design.TestNoRefOrOut#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.TestNoRefOrOut/cs/FxCop.Design.TestNoRefOrOut.cs#1)]  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek kitaplığı gösterir nasıl `ref` parametreleri başvuru türleri için kullanılır ve bu işlevselliği uygulamak için daha iyi bir yolunu gösterir.  
  
 [!code-csharp[FxCop.Design.RefByRefNo#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.RefByRefNo/cs/FxCop.Design.RefByRefNo.cs#1)]  
  
## <a name="example"></a>Örnek  
 Aşağıdaki uygulama davranışını göstermek için kitaplıkta her yöntemini çağırır.  
  
 [!code-csharp[FxCop.Design.TestRefByRefNo#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Design.TestRefByRefNo/cs/FxCop.Design.TestRefByRefNo.cs#1)]  
  
 Bu örnek aşağıdaki çıktıyı üretir.  
  
 **İşaretçi - değer olarak geçilemez değiştiriliyor:**  
**12345**  
**12345**  
**İşaretçi, başvuru tarafından geçirilmediğine - değiştirme:**  
**12345**  
**12345 ABCDE**  
**Döndürülen değere göre geçirme:**  
**12345 ABCDE**   
## <a name="related-rules"></a>İlgili kuralları  
 [CA1021: Out parametrelerinden kaçının](../code-quality/ca1021-avoid-out-parameters.md)



