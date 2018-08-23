---
title: 'CA1414: Boolean P-Invoke bağımsız değişkenlerini MarshalAs ile işaretleyin | Microsoft Docs'
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
- CA1414
- MarkBooleanPInvokeArgumentsWithMarshalAs
helpviewer_keywords:
- CA1414
- MarkBooleanPInvokeArgumentsWithMarshalAs
ms.assetid: c0c84cf5-7701-4897-9114-66fc4b895699
caps.latest.revision: 16
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 25650e2dd30c876929b677aaf82f082dd32bd5e6
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42634119"
---
# <a name="ca1414-mark-boolean-pinvoke-arguments-with-marshalas"></a>CA1414: Boolean P/Invoke bağımsız değişkenlerini MarshalAs ile işaretleyin
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CA1414: boolean P-Invoke bağımsız değişkenlerini MarshalAs ile işaretleyin](https://docs.microsoft.com/visualstudio/code-quality/ca1414-mark-boolean-p-invoke-arguments-with-marshalas).  
  
TypeName | MarkBooleanPInvokeArgumentsWithMarshalAs |  
| Checkıd | CA1414 |  
| Kategori | Microsoft.Interoperability|  
| Yeni değişiklik | Bozucu |  
  
## <a name="cause"></a>Sebep  
 Bir platform çağırma yöntemi bildirimi içeren bir <xref:System.Boolean?displayProperty=fullName> parametre veya dönüş değerindeki ancak <xref:System.Runtime.InteropServices.MarshalAsAttribute?displayProperty=fullName> özniteliği için parametre veya dönüş değerindeki uygulanmaz.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Bir platform yöntemi erişimleri yönetilmeyen kod çağırmak ve tarafından tanımlanan `Declare` anahtar sözcüğünü [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] veya <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName>. <xref:System.Runtime.InteropServices.MarshalAsAttribute> Yönetilen ve yönetilmeyen kod arasında veri türlerine dönüştürmek için kullanılan sıralama davranışını belirtir. Gibi pek çok basit veri türleri <xref:System.Byte?displayProperty=fullName> ve <xref:System.Int32?displayProperty=fullName>, yönetimsiz kod içinde tek bir gösterimi olan ve sıralama davranışları belirtilmesine gerek yoktur; ortak dil çalışma zamanı otomatik olarak doğru davranışı sağlar.  
  
 <xref:System.Boolean> Veri türüne, yönetimsiz kod içinde birden çok temsile sahiptir. Zaman <xref:System.Runtime.InteropServices.MarshalAsAttribute> , varsayılan hazırlama davranışı için belirtilmemiş <xref:System.Boolean> veri türü <xref:System.Runtime.InteropServices.UnmanagedType?displayProperty=fullName>. Tüm durumlarda uygun olmayan bir 32 bit tamsayı budur. Yönetilmeyen yöntemi tarafından gerekli Boolean gösterimi belirlenen verilecek ve uygun eşleşen <xref:System.Runtime.InteropServices.UnmanagedType?displayProperty=fullName>. UnmanagedType.Bool her zaman 4 bayttır Win32 BOOL türüdür. C++ için UnmanagedType.U1 kullanılmalıdır `bool` ya da diğer 1 baytlık türleri. Daha fazla bilgi için [Boole türleri için varsayılan hazırlama](http://msdn.microsoft.com/en-us/d4c00537-70f7-4ca6-8197-bfc1ec037ff9).  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlalini düzeltmek için geçerli <xref:System.Runtime.InteropServices.MarshalAsAttribute> için <xref:System.Boolean> parametre veya dönüş değeri. Öznitelik değerini uygun ayarlamak <xref:System.Runtime.InteropServices.UnmanagedType>.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan uyarıyı bastırmayın. Varsayılan hazırlama davranışı uygun olsa bile, davranışı açıkça belirtildiğinde kodu daha kolay korunur.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, iki platform çağırma uygun ile işaretlenmiş yöntemler gösterir <xref:System.Runtime.InteropServices.MarshalAsAttribute> öznitelikleri.  
  
 [!code-cpp[FxCop.Interoperability.BoolMarshalAs#1](../snippets/cpp/VS_Snippets_CodeAnalysis/FxCop.Interoperability.BoolMarshalAs/cpp/FxCop.Interoperability.BoolMarshalAs.cpp#1)]
 [!code-csharp[FxCop.Interoperability.BoolMarshalAs#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Interoperability.BoolMarshalAs/cs/FxCop.Interoperability.BoolMarshalAs.cs#1)]
 [!code-vb[FxCop.Interoperability.BoolMarshalAs#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Interoperability.BoolMarshalAs/vb/FxCop.Interoperability.BoolMarshalAs.vb#1)]  
  
## <a name="related-rules"></a>İlgili kuralları  
 [CA1901: P/Invoke bildirimleri taşınabilir olmalıdır](../code-quality/ca1901-p-invoke-declarations-should-be-portable.md)  
  
 [CA2101: P/Invoke dize bağımsız değişkenleri için hazırlama belirtin](../code-quality/ca2101-specify-marshaling-for-p-invoke-string-arguments.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Runtime.InteropServices.UnmanagedType?displayProperty=fullName>   
 [Boole türleri için varsayılan sıralama](http://msdn.microsoft.com/en-us/d4c00537-70f7-4ca6-8197-bfc1ec037ff9)   
 [Yönetilmeyen Kod ile Birlikte Çalışma](http://msdn.microsoft.com/library/ccb68ce7-b0e9-4ffb-839d-03b1cd2c1258)



