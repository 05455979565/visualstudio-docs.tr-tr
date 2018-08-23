---
title: ': Ca1800 gereksiz yok | Microsoft Docs'
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
- CA1800
- DoNotCastUnnecessarily
helpviewer_keywords:
- DoNotCastUnnecessarily
- CA1800
ms.assetid: b79a010a-6627-421e-8955-6007e32fa808
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 5972d3fc6c3f2fa4d943b768c962127bdfc994fc
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42675183"
---
# <a name="ca1800-do-not-cast-unnecessarily"></a>CA1800: Gereksiz atamalar yapmayın
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CA1800: gereksiz yere yapmayın](https://docs.microsoft.com/visualstudio/code-quality/ca1800-do-not-cast-unnecessarily).  
  
TypeName | DoNotCastUnnecessarily |  
| Checkıd | CA1800 |  
| Kategori | Microsoft.Performance|  
| Yeni değişiklik | Bölünemez |  
  
## <a name="cause"></a>Sebep  
 Bir yöntem yinelenen atamalardan biri kendi bağımsız değişkenler veya yerel değişkenler üzerinde gerçekleştirir. Tam çözümleme bu kural tarafından test edilen derleme, hata ayıklama bilgileri kullanılarak oluşturulmalıdır ve ilişkili bir program veritabanı (.pdb) dosyası kullanılabilir olmalıdır.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Özellikle yayınlar sıkıştırılmış yineleme deyiminde gerçekleştirildiğinde yinelenen yayınların performansını azaltır. Yinelenen açık tür dönüştürme işlemleri için atamanın sonucu yerel bir değişkende depolayın ve yinelenen atama işlemleri yerine yerel değişkenini kullanın.  
  
 C# `is` işleci gerçek atama yapılmadan önce atama başarılı olup olmadığını sınamak için kullanılan test sonucunu göz önünde bulundurun `as` işleci bunun yerine. Bu örtük dönüştürme işlemi tarafından gerçekleştirilen olmadan aynı işlevlere `is` işleci.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlalini düzeltmek için tür dönüştürme işlemlerinin sayısını en aza indirmek için yöntem uygulaması değiştirin.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Performans önemli değilse bu kuraldan bir uyarıyı bastırmak için ya da kural tamamen yok saymak için güvenlidir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C# kullanarak kuralı ihlal eden bir yöntemi gösterir `is` işleci. İkinci yöntem değiştirerek kural karşılayan `is` işleci ile bir test sonucunu karşı `as` işleci atama işlemleri her ikisinden birine yinelemesi sayısını azaltır.  
  
 [!code-csharp[FxCop.Performance.UnnecessaryCastsAsIs#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Performance.UnnecessaryCastsAsIs/cs/FxCop.Performance.UnnecessaryCastsAsIs.cs#1)]  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek bir yöntemi gösterir `start_Click`, birden çok yinelenen açık Atamalar, kural ve bir yöntem ihlal olan `reset_Click`, hangi karşılayan kural dönüştürme bir yerel değişkende depolayarak.  
  
 [!code-csharp[FxCop.Performance.UnnecessaryCasts#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Performance.UnnecessaryCasts/cs/FxCop.Performance.UnnecessaryCasts.cs#1)]
 [!code-vb[FxCop.Performance.UnnecessaryCasts#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Performance.UnnecessaryCasts/vb/FxCop.Performance.UnnecessaryCasts.vb#1)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [olarak](http://msdn.microsoft.com/library/a9be126b-cbf4-4990-a70d-d0e1983cad0e)   
 [is](http://msdn.microsoft.com/library/bc62316a-d41f-4f90-8300-c6f4f0556e43)



