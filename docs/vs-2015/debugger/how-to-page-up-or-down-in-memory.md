---
title: 'Nasıl yapılır: sayfa yukarı veya aşağı bellekte | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- FSharp
- VB
- CSharp
- C++
- JScript
- VB
- CSharp
- C++
helpviewer_keywords:
- debugger, paging up or down in memory
- memory, paging up or down
- Disassembly window, viewing memory space
- Memory window, paging up or down in memory
ms.assetid: 50b30a68-66f6-43f8-a48b-59ce12c95471
caps.latest.revision: 23
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6d443955af62f2375357828c0513bbdee289a781
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42692143"
---
# <a name="how-to-page-up-or-down-in-memory"></a>Nasıl Yapılır: Bellekte Sayfa Yukarı veya Aşağı Gitme
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [nasıl yapılır: sayfa yukarı veya aşağı bellekte](https://docs.microsoft.com/visualstudio/debugger/how-to-page-up-or-down-in-memory).  
  
Bellek içeriğini görüntülediğinizde bir **bellek** penceresi veya **ayrıştırılmış kodu** penceresinde bellek alanı yukarı veya aşağı taşımak için dikey kaydırma çubuğunu kullanabilirsiniz.  
  
### <a name="to-page-up-or-down-in-memory"></a>Yukarı veya aşağı bellekte sayfa için  
  
1.  Page DOWN (daha yüksek bir bellek adresi taşıma) için dikey bir kaydırma çubuğuna ait kaydırma kutusunun altındaki'ı tıklatın.  
  
2.  (Daha düşük bir bellek adresi taşıma) ayarlama sayfası için thumb yukarıda dikey kaydırma çubuğunu tıklayın.  
  
 Ayrıca dikey kaydırma çubuğu standart olmayan bir şekilde çalıştığını görürsünüz. Çok büyük modern bir bilgisayarın adres alanı ve kaydırma çubuğunun Kaydırma kutusu yazılımdır ve rastgele bir konuma sürükleyerek kayıp kolaydır. Bu nedenle, thumb "springloaded" olduğundan ve her zaman kaydırma çubuğunu Merkezi'nde kalır. Yerel kod uygulamalarında yukarı veya aşağı sayfa ancak hakkında ücretsiz kaydırma yapılamıyor.  
  
 Yönetilen uygulamalarda Ayrıştırılmış kod bir işleve sınırlıdır ve normalde gezinebilirsiniz.  
  
 Daha büyük adresleri penceresinin en altında göründüğünü fark edeceksiniz. Daha yüksek bir adresi görüntülemek için aşağı, en fazla değil taşımanız gerekir.  
  
#### <a name="to-move-up-or-down-one-instruction"></a>Bir yönerge aşağı veya yukarı taşımak için  
  
-   Dikey kaydırma çubuğu ortasından altına veya üstüne oka tıklayın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bellek Windows](../debugger/memory-windows.md)   
 [Nasıl yapılır: Ayrıştırılmış kod penceresini kullanma](../debugger/how-to-use-the-disassembly-window.md)   
 [Hata ayıklayıcıda verileri görüntüleme](../debugger/viewing-data-in-the-debugger.md)





