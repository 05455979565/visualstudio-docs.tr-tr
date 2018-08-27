---
title: 'CA1030: uygun yerlerde olaylar kullanın | Microsoft Docs'
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
- UseEventsWhereAppropriate
- CA1030
helpviewer_keywords:
- CA1030
- UseEventsWhereAppropriate
ms.assetid: ea051367-deeb-40f9-9b65-eb818f1e133a
caps.latest.revision: 18
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 8100aff6c2215d9a5fa031d69fc0ee105e440e3a
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/24/2018
ms.locfileid: "42902916"
---
# <a name="ca1030-use-events-where-appropriate"></a>CA1030: Uygun yerlerde olaylar kullanın
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CA1030: uygun yerlerde olaylar kullanın](https://docs.microsoft.com/visualstudio/code-quality/ca1030-use-events-where-appropriate).

|||
|-|-|
|TypeName|UseEventsWhereAppropriate|
|CheckId|CA1030|
|Kategori|Microsoft.Design|
|Yeni Değişiklik|Bölünemez|

## <a name="cause"></a>Sebep
 Genel, korumalı veya özel yöntem adı aşağıdakilerden biri ile başlar:

-   Eklenti fiyatı

-   RemoveOn

-   Ateş

-   artırma

## <a name="rule-description"></a>Kural Tanımı
 Bu kural, normalde olaylar için kullanılan adlara sahip yöntemleri algılar. Olayları gözlemci ya da Yayımla-abone ol tasarım desenini izler; Bunlar, bir nesnede bir durum değişikliği diğer nesnelere iletileceği olduğunda kullanılır. Yanıt olarak açıkça tanımlanmış bir durum değişikliği bir yöntem çağrıldığında, bir olay işleyicisi tarafından yöntemin çağrılması gerekir. Yöntemi direkt olarak çağırmak yerine olayları yükselterek çağıran nesneler.

 Olayların bazı genel örnekleri burada bir düğmeye tıklanması gibi bir kullanıcı eylemi yürütmek için kod kesiminin neden olan kullanıcı arabirimi uygulamalarında bulunur. [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] Olay modeli için kullanıcı arabirimleri sınırlı değil; bunu her yerden, iletişim kurması gereken durumu değiştirir. bir veya daha fazla nesneye kullanılmalıdır.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Bir nesnenin durumu değiştiğinde yöntemi çağrılırsa, kullanılacak tasarım değiştirme düşünmelisiniz [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] olay modeli.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Yöntem ile çalışmazsa bu kuraldan bir uyarıyı bastırmak [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] olay modeli.



