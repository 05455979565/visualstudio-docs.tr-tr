---
title: Sınıf tasarımcısında Visual C++ numaralandırmaları | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Class Designer [Visual Studio], enumerations
ms.assetid: 11e90ba1-18cd-44f8-9e26-e3746a7a19d1
caps.latest.revision: 14
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 6d4bc1385c934d9858cef19f8ffe73ad6a0baaf0
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42687291"
---
# <a name="visual-c-enumerations-in-class-designer"></a>Sınıf Tasarımcısında Visual C++ Numaralandırmaları
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [sınıf tasarımcısında Visual C++ numaralandırmaları](https://docs.microsoft.com/visualstudio/ide/visual-cpp-enumerations-in-class-designer).  
  
Sınıf Tasarımcısı, C++ destekler `enum` ve kapsamlı `enum class` türleri. Bir örneği verilmiştir:  
  
```  
enum CardSuit {  
   Diamonds = 1,  
   Hearts = 2,  
   Clubs = 3,  
   Spades = 4  
};  
  
// or...  
enum class CardSuit {  
   Diamonds = 1,  
   Hearts = 2,  
   Clubs = 3,  
   Spades = 4  
};  
  
```  
  
 Sınıf diyagramında C++ numaralandırma şekli görünür ve etiketi dışında bir yapı şeklinde çalışır **Enum** veya **sabit listesi sınıfı**, mavi yerine pembe ve sol üst taraftaki renkli kenarlık vardır Kenar boşlukları. Numaralandırma şekilleri ve yapı şekilleri dörtgen köşelerine sahiptir.  
  
 Kullanma hakkında daha fazla bilgi için `enum` yazın, bkz: [numaralandırmalar](http://msdn.microsoft.com/library/081829db-5dca-411e-a53c-bffef315bcb3).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual C++ kodu (Sınıf Tasarımcısı) ile çalışma](../ide/working-with-visual-cpp-code-class-designer.md)   
 [Sabit Listeleri](http://msdn.microsoft.com/library/081829db-5dca-411e-a53c-bffef315bcb3)



