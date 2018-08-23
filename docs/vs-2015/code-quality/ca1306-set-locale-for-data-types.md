---
title: 'CA1306: Veri türleri için yerel ayarları ayarlayın | Microsoft Docs'
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
- CA1306
- SetLocaleForDataTypes
helpviewer_keywords:
- CA1306
- SetLocaleForDataTypes
ms.assetid: 104297b2-5806-4de0-a8d9-c589380a796c
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 6ece2ead5931f17b27ecdf86672df37b932ddefb
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42692620"
---
# <a name="ca1306-set-locale-for-data-types"></a>CA1306: Veri türleri için yerel ayarları ayarlayın
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CA1306: veri türleri için Yereli ayarlayın](https://docs.microsoft.com/visualstudio/code-quality/ca1306-set-locale-for-data-types).  
  
TypeName | SetLocaleForDataTypes |  
| Checkıd | CA1306 |  
| Kategori | Microsoft.Globalization|  
| Yeni değişiklik | Bölünemez |  
  
## <a name="cause"></a>Sebep  
 Yöntem veya Oluşturucu oluşturulan bir veya daha fazla <xref:System.Data.DataTable?displayProperty=fullName> veya <xref:System.Data.DataSet?displayProperty=fullName> örnekler ve yerel ayar özelliğini açıkça ayarlamamış (<xref:System.Data.DataTable.Locale%2A?displayProperty=fullName> veya <xref:System.Data.DataSet.Locale%2A?displayProperty=fullName>).  
  
## <a name="rule-description"></a>Kural Tanımı  
 Yerel ayar sayısal değerleri, para birimi simgeleri ve sıralama için kullanılan biçimlendirme gibi veriler için kültüre özgü sunu öğelerini belirler. Oluştururken bir <xref:System.Data.DataTable> veya <xref:System.Data.DataSet>, yerel ayarı açık olarak ayarlamanız gerekir. Varsayılan olarak, bu tür için bir yerel ayar geçerli kültür ' dir. Bir veritabanı veya dosya depolanır ve genel olarak paylaşılan veri yerel ayarı normalde sabit kültür için ayarlanmalıdır (<xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=fullName>). Varsayılan yerel ayarı kullanarak veri kültürler arası paylaşıldığında içeriğini açabilir <xref:System.Data.DataTable> veya <xref:System.Data.DataSet> sunulan ya da yanlış yorumlanır.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlalini düzeltmek için açık yerel olarak <xref:System.Data.DataTable> veya <xref:System.Data.DataSet>.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Kitaplık veya uygulama yerel sınırlı bir kitle için olduğunda, veriler paylaşılmayan veya varsayılan ayar tüm desteklenen senaryolar istenen davranışı verir. Bu kuraldan bir uyarıyı bastırmak güvenlidir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek iki oluşturur <xref:System.Data.DataTable> örnekleri.  
  
 [!code-csharp[FxCop.Globalization.DataTable#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Globalization.DataTable/cs/FxCop.Globalization.DataTable.cs#1)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Data.DataTable?displayProperty=fullName>   
 <xref:System.Data.DataSet?displayProperty=fullName>   
 <xref:System.Globalization.CultureInfo?displayProperty=fullName>   
 <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName>   
 <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=fullName>



