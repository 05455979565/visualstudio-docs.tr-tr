---
title: Kimin Yanlış Parametre Değeri Geçirdiğini Nasıl Bulabilirim? | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug.parameters
dev_langs:
- FSharp
- VB
- CSharp
- C++
- C++
helpviewer_keywords:
- debugging [C++], parameters
- parameters [debugger]
- passing parameters, troubleshooting wrong values
- functions [debugger], detecting wrong parameter values
- parameter values, troubleshooting
ms.assetid: 1f1ae455-0e25-4e9d-b33f-53908f5bd6ce
caps.latest.revision: 22
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b1d7ae67e7ba09a25277afc55ef92da47a8e770d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42673374"
---
# <a name="how-can-i-find-out-who-is-passing-a-wrong-parameter-value"></a>Kimin Yanlış Parametre Değeri Geçirdiğini Nasıl Bulabilirim?
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [nasıl bulabilirim kullanıma kimin yanlış parametre değeri geçirdiğini olabilir?](https://docs.microsoft.com/visualstudio/debugger/how-can-i-find-out-who-is-passing-a-wrong-parameter-value-q).  
  
Sorun açıklaması  
 Benim birine yanlış parametre değeri geçirilir. Bu işlev her yerden çağrılır. Nasıl öğrenebilirim kullanıma neyin yanlış değer geçiyor?  
  
## <a name="solution"></a>Çözüm  
  
#### <a name="to-resolve-this-problem"></a>Bu sorunu gidermek için  
  
1.  İşlevin başında bir konum kesme noktası ayarlayın.  
  
2.  Kesme noktasına sağ tıklayıp **koşul**.  
  
3.  İçinde **kesme noktası koşulu** iletişim kutusu, tıklayarak **koşul** onay kutusu. Bkz: [kesme noktalarının Gelişmiş](../debugger/using-breakpoints.md#BKMK_Specify_a_breakpoint_condition_using_a_code_expression).  
  
4.  Gibi bir ifade girin `Var==3`, metin kutusuna, burada `Var` hatalı değeri içeren parametrenin adıdır ve `3` ona iletilen hatalı değer.  
  
5.  Seçin **true'dur** radyo düğmesini tıklatıp tıklayın **Tamam** düğmesi.  
  
6.  Şimdi programı yeniden çalıştırın. Kesme noktası programın işlevin başında durdurulmasına neden olduğunda `Var` parametresinin değeri `3`.  
  
7.  Çağıran işlevi bulmak ve kaynak koduna gitmek için çağrı yığını penceresini kullanın. Daha fazla bilgi için [nasıl yapılır: çağrı yığını penceresinde kullanmak](../debugger/how-to-use-the-call-stack-window.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yerel kod hata ayıklaması SSS](../debugger/debugging-native-code-faqs.md)   
 [Kesme noktaları](http://msdn.microsoft.com/en-us/fe4eedc1-71aa-4928-962f-0912c334d583)   
 [Yerel kodda hata ayıklama](../debugger/debugging-native-code.md)



