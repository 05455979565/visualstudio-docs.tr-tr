---
title: ': Ayrılmış özel durum türleri ca2201 oluşturmayın | Microsoft Docs'
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
- DoNotRaiseReservedExceptionTypes
- CA2201
helpviewer_keywords:
- CA2201
- DoNotRaiseReservedExceptionTypes
ms.assetid: dd14ef5c-80e6-41a5-834e-eba8e2eae75e
caps.latest.revision: 18
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 1971ccb2012794467a4fbdf661d55df61c934c90
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/24/2018
ms.locfileid: "42902337"
---
# <a name="ca2201-do-not-raise-reserved-exception-types"></a>CA2201: Ayrılmış özel durum türleri oluşturmayın
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CA2201: ayrılmış özel durum türlerini harekete geçirmeyin](https://docs.microsoft.com/visualstudio/code-quality/ca2201-do-not-raise-reserved-exception-types).

|||
|-|-|
|TypeName|DoNotRaiseReservedExceptionTypes|
|CheckId|CA2201|
|Kategori|Microsoft.Usage|
|Yeni Değişiklik|Yeni|

## <a name="cause"></a>Sebep
 Bir yöntem çok genel veya çalışma zamanı tarafından ayrılmış bir özel durum türü oluşturur.

## <a name="rule-description"></a>Kural Tanımı
 Kullanıcı için yeterli bilgi sağlamak için genel aşağıdaki özel durum türleri şunlardır:

-   <xref:System.Exception?displayProperty=fullName>

-   <xref:System.ApplicationException?displayProperty=fullName>

-   <xref:System.SystemException?displayProperty=fullName>

 Aşağıdaki özel durum türleri ayrılmıştır ve yalnızca ortak dil çalışma zamanı tarafından oluşturulur:

-   <xref:System.ExecutionEngineException?displayProperty=fullName>

-   <xref:System.IndexOutOfRangeException?displayProperty=fullName>

-   <xref:System.NullReferenceException?displayProperty=fullName>

-   <xref:System.OutOfMemoryException?displayProperty=fullName>

 **Genel özel durum oluşturması beklenmiyor**

 Bir genel özel durum türü gibi throw varsa <xref:System.Exception> veya <xref:System.SystemException> kitaplığı veya çerçeveyi, tüketicilerin kaynaklananlar zorlar özel durumları işlemek nasıl bilmiyorsanız Bilinmeyen özel durumlar dahil olmak üzere,.

 Bunun yerine, framework zaten daha türetilmiş bir tür throw veya türetilen kendi türünüzü oluşturabilirsiniz <xref:System.Exception>.

 **Belirli özel durumlar**

 Aşağıdaki tablo parametreleri gösterir ve bir özellik kümesi erişimcisinde değer parametresi dahil olmak üzere bu parametreyi doğruladığınızda atmak için hangi özel durumları:

|Parametre açıklaması|Özel Durum|
|---------------------------|---------------|
|`null` Başvuru|<xref:System.ArgumentNullException?displayProperty=fullName>|
|(Örneğin, bir koleksiyon veya liste için bir dizin), izin verilen aralığın dışında|<xref:System.ArgumentOutOfRangeException?displayProperty=fullName>|
|Geçersiz `enum` değeri|<xref:System.ComponentModel.InvalidEnumArgumentException?displayProperty=fullName>|
|Bir yöntemin parametre belirtimleri karşılamıyor bir biçim içeriyor (için biçim dizesi gibi `ToString(String)`)|<xref:System.FormatException?displayProperty=fullName>|
|Aksi takdirde geçersiz|<xref:System.ArgumentException?displayProperty=fullName>|

 Bir işlem için geçerli bir nesne throw durumunu geçersiz olduğunda <xref:System.InvalidOperationException?displayProperty=fullName>

 Byla zahozena bir nesne üzerinde bir işlem gerçekleştirildiğinde throw <xref:System.ObjectDisposedException?displayProperty=fullName>

 Ne zaman bir işlemi desteklenmiyor (olduğu gibi bir geçersiz kılınan **Stream.Write** okumak için açık bir Stream içinde) throw <xref:System.NotSupportedException?displayProperty=fullName>

 Bir dönüştürme (olduğu gibi bir açık tür dönüştürme işleci aşırı yükleme gibi) bir taşma neden olacağından, throw <xref:System.OverflowException?displayProperty=fullName>

 Diğer tüm durumlarda, türetilen kendi türünüzü oluşturabilirsiniz <xref:System.Exception> ve bu durum.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Bu kural ihlalini düzeltmek için oluşturulan özel durumun türü ayrılmış türlerinden biri değil belirli bir türe değiştirin.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Bu kuraldan uyarıyı bastırmayın.

## <a name="related-rules"></a>İlgili kuralları
 [CA1031: Genel özel durum türlerini yakalamayın](../code-quality/ca1031-do-not-catch-general-exception-types.md)



