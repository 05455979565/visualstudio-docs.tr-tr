---
title: Visual Basic'de Durdur deyimleri | Microsoft Docs
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
- VB
helpviewer_keywords:
- End statements
- breakpoints, Stop statements
- debugging managed code, Stop statements vs breakpoints
- Stop statements, about Stop statements
- debugging [Visual Basic], Stop statements vs. breakpoints
ms.assetid: 4ad3fe5c-3dfb-4913-b2eb-a0b635751c18
caps.latest.revision: 16
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0fcb4e3018dad53ef869748a4394363dba78f71c
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42627926"
---
# <a name="stop-statements-in-visual-basic"></a>Visual Basic'de Durdur Deyimleri
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [Visual Basic'de Durdur deyimleri](https://docs.microsoft.com/visualstudio/debugger/stop-statements-in-visual-basic).  
  
Visual Basic Stop deyimi, bir kesme noktası ayarlamak için programlı bir alternatif sunar. Hata ayıklayıcı Stop deyimi karşılaştığında (kesme moduna girer) programın yürütülmesini keser. C# programcıları System.Diagnostics.Debugger.Break yapılan bir çağrı kullanılarak aynı etkiyi elde edebilirsiniz.  
  
 Ayarlar veya kaynak kodu düzenleyerek bir Stop deyimi kaldırın. Ayarlayamıyor veya bir kesme noktası gibi hata ayıklayıcı komutlarını kullanarak Stop deyimleri temizleyin.  
  
 Bir End deyimi Stop deyimi değişkenleri sıfırlamak veya desteklemez, tasarım moduna dönmek. Uygulamayı çalıştırmaya devam etmek için hata ayıklama menüsünden devam seçebilirsiniz.  
  
 Stop deyimi, bir Visual Basic uygulama hata ayıklayıcının dışında çalıştırmak, Just-ın-Time, hata ayıklayıcı başlatılır, hata ayıklama etkin. Just-ın-Time, hata ayıklama etkin değil, Stop deyimi yürütmeyi sonlandırma bir End deyimi değilmiş gibi davranır. Visual Basic uygulamasında yayın sürümünden tüm Stop deyimleri kaldırmak için hiçbir QueryUnload ya da kaldırma olayı oluşur. Daha fazla bilgi için [tam zamanında hata ayıklama](../debugger/just-in-time-debugging-in-visual-studio.md).  
  
 Stop deyimleri kaldırmanın ihtiyacını önlemek için koşullu derleme kullanabilirsiniz:  
  
```  
#If DEBUG Then  
   Stop  
#Else  
   ' Don't stop  
#End If  
```  
  
 Başka bir alternatif bir onay deyimi yerine Stop deyimi kullanmaktır. Belirtilen koşul karşılanmamıştır ve bir yayım sürümünü derlediğinizde otomatik olarak kaldırılır Debug.Assert deyimi yürütmeyi keser. Daha fazla bilgi için [yönetilen koddaki onaylar](../debugger/assertions-in-managed-code.md). Hata ayıklama sürümü her zaman yürütmeyi keser bir onay deyimi istiyorsanız, bunu yapabilirsiniz:  
  
```  
Debug.Assert(false)  
```  
  
 Henüz başka bir alternatif Debug.Fail yöntemi kullanmaktır:  
  
```  
Debug.Fail("a clever output string goes here")  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata ayıklayıcısı güvenliği](../debugger/debugger-security.md)   
 [C#, F # ve Visual Basic proje türleri](../debugger/debugging-preparation-csharp-f-hash-and-visual-basic-project-types.md)   
 [Yönetilen kodda hata ayıklama](../debugger/debugging-managed-code.md)



