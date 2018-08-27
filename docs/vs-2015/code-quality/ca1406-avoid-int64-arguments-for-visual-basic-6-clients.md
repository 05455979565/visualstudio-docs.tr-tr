---
title: 'CA1406: Visual Basic 6 istemcileri için Int64 bağımsız değişkenlerinden kaçının | Microsoft Docs'
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
- AvoidInt64ArgumentsForVB6Clients
- CA1406
helpviewer_keywords:
- AvoidInt64ArgumentsForVB6Clients
- CA1406
ms.assetid: d5d0d3fc-f105-43da-be5b-923ab023309c
caps.latest.revision: 16
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 5947ce0bbcb19058cb32950e1e77cb3566b2ad2e
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/24/2018
ms.locfileid: "42902408"
---
# <a name="ca1406-avoid-int64-arguments-for-visual-basic-6-clients"></a>CA1406: Visual Basic 6 istemcileri için Int64 bağımsız değişkenlerinden kaçının
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CA1406: Visual Basic 6 istemcileri için Int64 önlemek bağımsız](https://docs.microsoft.com/visualstudio/code-quality/ca1406-avoid-int64-arguments-for-visual-basic-6-clients).

|||
|-|-|
|TypeName|AvoidInt64ArgumentsForVB6Clients|
|CheckId|CA1406|
|Kategori|Microsoft.Interoperability|
|Yeni Değişiklik|Yeni|

## <a name="cause"></a>Sebep
 Özel Bileşen Nesne Modeli (COM) görünür olarak işaretlenmiş bir tür o alır bir üye bildirir bir <xref:System.Int64?displayProperty=fullName> bağımsız değişken.

## <a name="rule-description"></a>Kural Tanımı
 Visual Basic 6 COM istemcileri, 64-bit tamsayıya erişemiyor.

 Varsayılan olarak, COM görünür şunlardır: derlemeleri, genel tür, genel türlerde ortak örnek üyeleri ve tüm ortak türlerin üyeleri. Ancak, hatalı pozitif sonuçları azaltmak için bu kural türünü açıkça belirtilen COM görünürlüğünü gerektirir; derlemeyi içeren ile işaretlenmelidir <xref:System.Runtime.InteropServices.ComVisibleAttribute?displayProperty=fullName> kümesine `false` ve türü ile işaretlenmelidir <xref:System.Runtime.InteropServices.ComVisibleAttribute> kümesine `true`.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Değeri her zaman ifade edilemez bir 32 bit tam sayı bir parametre için bu kural ihlalini düzeltmek için parametre türüne değiştirin <xref:System.Int32?displayProperty=fullName>. Parametrenin değeri bir 32 bit tamsayı ifade edilebilir daha büyük olabilir, parametre türüne değiştirme <xref:System.Decimal?displayProperty=fullName>. Unutmayın hem <xref:System.Single?displayProperty=fullName> ve <xref:System.Double?displayProperty=fullName> üst aralığı, hassasiyet kaybetmek <xref:System.Int64> veri türü. COM görünür olmasını üyesi değildir, kendisiyle işaretlemek <xref:System.Runtime.InteropServices.ComVisibleAttribute> kümesine `false`.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Visual Basic 6 COM istemcileri türü erişmeyecek belirli ise bu kuraldan bir uyarıyı bastırmak güvenlidir.

## <a name="example"></a>Örnek
 Aşağıdaki örnek kuralını ihlal eden bir tür gösterir.

 [!code-csharp[FxCop.Interoperability.LongArgument#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Interoperability.LongArgument/cs/FxCop.Interoperability.LongArgument.cs#1)]
 [!code-vb[FxCop.Interoperability.LongArgument#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Interoperability.LongArgument/vb/FxCop.Interoperability.LongArgument.vb#1)]

## <a name="related-rules"></a>İlgili kuralları
 [CA1413: COM görünebilir değer türleri içinde genel olmayan alanlardan kaçının](../code-quality/ca1413-avoid-non-public-fields-in-com-visible-value-types.md)

 [CA1407: COM görünebilir türler içinde statik üyelerden kaçının](../code-quality/ca1407-avoid-static-members-in-com-visible-types.md)

 [CA1017: Derlemeleri ComVisibleAttribute ile işaretleyin](../code-quality/ca1017-mark-assemblies-with-comvisibleattribute.md)

## <a name="see-also"></a>Ayrıca Bkz.
 [Yönetilmeyen kod ile birlikte](http://msdn.microsoft.com/library/ccb68ce7-b0e9-4ffb-839d-03b1cd2c1258) [Long veri türü](http://msdn.microsoft.com/library/b4770c34-1804-4f8c-b512-c10b0893e516)



