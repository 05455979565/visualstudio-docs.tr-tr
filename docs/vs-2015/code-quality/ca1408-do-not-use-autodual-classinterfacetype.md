---
title: 'CA1408: AutoDual ClassInterfaceType kullanma | Microsoft Docs'
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
- DoNotUseAutoDualClassInterfaceType
- CA1408
helpviewer_keywords:
- CA1408
- DoNotUseAutoDualClassInterfaceType
ms.assetid: 60ca5e02-3c51-42dd-942b-4f950eecfa0f
caps.latest.revision: 18
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: d8e33b85e7f53a1f67eddfb139c6ccef66015522
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42632332"
---
# <a name="ca1408-do-not-use-autodual-classinterfacetype"></a>CA1408: AutoDual ClassInterfaceType kullanma
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CA1408: AutoDual ClassInterfaceType kullanmayın](https://docs.microsoft.com/visualstudio/code-quality/ca1408-do-not-use-autodual-classinterfacetype).  
  
TypeName | DoNotUseAutoDualClassInterfaceType |  
| Checkıd | CA1408 |  
| Kategori | Microsoft.Interoperability|  
| Yeni değişiklik | Bozucu |  
  
## <a name="cause"></a>Sebep  
 Bileşen Nesne Modeli (COM) görünen bir tür ile işaretlenmiş <xref:System.Runtime.InteropServices.ClassInterfaceAttribute> özniteliğini `AutoDual` değerini <xref:System.Runtime.InteropServices.ClassInterfaceType>.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Çift arabirim kullanan türler, belirli bir arabirim düzenine bağlanmak için istemcileri etkinleştirir. Gelecek sürümdeki değişiklikler, türün düzeni veya bazı temel türler, arayüze bağlanan COM istemcilerini kesintiye uğratır. Varsayılan olarak, <xref:System.Runtime.InteropServices.ClassInterfaceAttribute> özniteliği belirtilmezse, yalnızca gönderme arabirimi kullanılır.  
  
 Tersi durumda işaretlenmiş sürece tüm genel türlere COM görünür; Tüm özel ve genel türler COM'a görünmez  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlalini düzeltmek için değerini değiştirmek <xref:System.Runtime.InteropServices.ClassInterfaceAttribute> özniteliğini `None` değerini <xref:System.Runtime.InteropServices.ClassInterfaceType> ve arabirimini açıkça tanımlar.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu düzen türü kendi taban türleri ve gelecekte yayımlanacak bir sürümde değişmez belirli olmadığı sürece bu kuraldan bir uyarıyı bastırmayın.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, kural ve açık bir arabirim kullanmak için sınıfı yeniden bildirimi ihlal eden bir sınıfı gösterir.  
  
 [!code-csharp[FxCop.Interoperability.AutoDual#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Interoperability.AutoDual/cs/FxCop.Interoperability.AutoDual.cs#1)]
 [!code-vb[FxCop.Interoperability.AutoDual#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Interoperability.AutoDual/vb/FxCop.Interoperability.AutoDual.vb#1)]  
  
## <a name="related-rules"></a>İlgili kuralları  
 [CA1403: Otomatik yerleşim türleri COM görünebilir olmamalıdır](../code-quality/ca1403-auto-layout-types-should-not-be-com-visible.md)  
  
 [CA1412: ComSource Arabirimlerini IDispatch olarak işaretleyin](../code-quality/ca1412-mark-comsource-interfaces-as-idispatch.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıf arabirimine giriş](http://msdn.microsoft.com/en-us/733c0dd2-12e5-46e6-8de1-39d5b25df024)   
 [Birlikte çalışma için .NET türlerini niteleme](http://msdn.microsoft.com/library/4b8afb52-fb8d-4e65-b47c-fd82956a3cdd)   
 [Yönetilmeyen Kod ile Birlikte Çalışma](http://msdn.microsoft.com/library/ccb68ce7-b0e9-4ffb-839d-03b1cd2c1258)



