---
title: 64 Bit uygulamalarda hata ayıklama | Microsoft Docs
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
helpviewer_keywords:
- debugging [Visual Studio], 64-bit
- 64-bit debugging
ms.assetid: db648e5f-6375-4e2d-aa98-eb7261958927
caps.latest.revision: 38
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 41b3327e7c659772460bfa644e2540ed15a4ff89
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42683773"
---
# <a name="debug-64-bit-applications"></a>64 Bit uygulamalarda hata ayıklama
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [hata ayıklama 64-Bit uygulamalar](https://docs.microsoft.com/visualstudio/debugger/debug-64-bit-applications) .  
  
Yerel bilgisayarda veya uzak bilgisayarda çalışan bir 64-bit uygulamada hata ayıklaması yapabilirsiniz.  
  
 Bir uzak bilgisayarda çalışan 64-bit bir uygulamada hata ayıklamak için bkz: [uzaktan hata ayıklama](../debugger/remote-debugging.md).  
  
 64 bit uygulamalarda hata ayıklama için yerel olarak Visual Studio 64 bit çalışan işlemi (msvsmon.exe) 32-bit Visual Studio işlemi içinde gerçekleştirilemez alt düzey işlemleri gerçekleştirmek için kullanır.  
  
 .NET Framework 3.5 veya daha önceki bir sürümünü kullanan 64 bit işlemleri için karışık mod hata ayıklaması desteklenmiyor.  
  
## <a name="debug-a-64-bit-application"></a>Bir 64 bit uygulamanın hatalarını ayıklama  
 Bir 64 bit uygulamanın hatalarını ayıklamaya denemek için:  
  
1.  Visual Studio çözümü, örneğin bir C# konsol uygulaması oluşturun.  
  
2.  Yapılandırma Yöneticisi'ni kullanarak 64-bit yapılandırmasını ayarlayın. Daha fazla bilgi için [nasıl yapılır: projeleri hedef platformlar yapılandırma](../ide/how-to-configure-projects-to-target-platforms.md).  
  
3.  Bu aşamada, uzaktan hata ayıklayıcı (msvsmon.exe) 64 bit sürümü başlatır. 64-bit yapılandırmayla çözümünün açık olduğu sürece çalıştırır.  
  
4.  Hata ayıklama başlatılamıyor. Aynı deneyimi, 32-bit yapılandırmasına sahip olmalıdır. Hatalarla karşılaşırsanız, aşağıdaki sorun giderme bölümüne bakın.  
  
## <a name="troubleshooting-64-bit-debugging"></a>64-bit hata ayıklama sorunlarını giderme  
 Bir hata görebilirsiniz: "bir 64 bit hata ayıklama işlemi beklenenden uzun sürüyor." Bu durumda, Visual Studio msvsmon.exe 64-bit sürümü için bir istek gönderdi ve geri dönmeniz bu isteğin sonucu için uzun sürdü.  
  
 Bu hata iki ana nedeni vardır:  
  
-   Ağ güvenlik yazılımı güvenilir olmadığı ağ yığınını neden bilgisayarınızda yüklü olması ve localhost üzerinde giden paketlerin bıraktı. Tüm ağ güvenlik yazılımı devre dışı bırakmayı deneyin ve bu da çözmediğine bakın. Bu durumda, rapor, yazılım, localhost trafiğiyle engel ağ güvenlik yazılım satıcınıza için.  
  
-   Visual Studio ile bir yanıt vermemesine veya performans sorunu içine çalışıyor. Sorun düzenli olarak ortaya Visual Studio (devenv.exe) ve çalışan işleminden (msvsmon.exe) dökümleri toplayın ve bunları Microsoft'a gönderin. 
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [64-bit uygulamalar](http://msdn.microsoft.com/library/fd4026bc-2c3d-4b27-86dc-ec5e96018181)   
 [Programları 64 Bit için yapılandırma](http://msdn.microsoft.com/library/cb99f72b-8c74-48f4-846a-8921b37b97e9)   
 [Visual Studio IDE 64 Bit desteği](../ide/visual-studio-ide-64-bit-support.md)   
 [Döküm dosyalarını kullanma](../debugger/using-dump-files.md)   
 [Uzaktan hata ayıklama](../debugger/remote-debugging.md)






