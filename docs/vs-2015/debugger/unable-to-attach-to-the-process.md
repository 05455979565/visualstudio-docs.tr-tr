---
title: İşleme iliştirilemiyor. | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.remote.unable2attach
dev_langs:
- FSharp
- VB
- CSharp
- C++
ms.assetid: 0468de6c-3ff1-4979-a8c6-8afb53f37547
caps.latest.revision: 13
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: c74799daf57ca031c4b3ce6bf76f72e453eeb0b3
ms.sourcegitcommit: 75807551ea14c5a37aa07dd93a170b02fc67bc8c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/12/2019
ms.locfileid: "64824213"
---
# <a name="unable-to-attach-to-the-process"></a>İşleme İliştirilemiyor
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

İşleme iliştirilemiyor. Hata ayıklayıcı bileşeni sunucuda bu makineye bağlanırken erişim aldı.  
  
 Bu hataya neden iki yaygın senaryo vardır:  
  
 **Senaryo 1:** Makine Windows XP çalışıyor. Windows Server 2003 çalıştıran makine B. Makine B üzerinde kayıt defterini, aşağıdaki DWORD değerini içerir:  
  
 `HKLM\Software\Microsoft\MachineDebugManager\AllowLaunchAsOtherUser=1`  
  
 1 kullanıcı Terminal Server oturumunu (oturumu 1) makinede B ve yönetilen bir uygulama bu oturumdan başlayan.  
  
 Her iki makinede yönetici de olan, kullanıcı 2, makine A. kaydediliyor Burada, makine b 1 oturumda çalışan bir uygulamaya eklemek izinli çalışır  
  
 **Senaryo 2:** Bir kullanıcı her iki makinelerde aynı parola kullanarak makinelere iki, A ve B aynı çalışma kaydedilir. Hata ayıklayıcı bir makine üzerinde çalışan ve makine b makine A üzerinde çalışan yönetilen bir uygulamaya iliştirmeye **ağ erişimi: Yerel hesaplar için paylaşım ve güvenlik modeli** kümesine **Konuk**.  
  
### <a name="to-solve-scenario-1"></a>Senaryo 1 çözmek için  
  
- Hata ayıklayıcı ve yönetilen uygulama aynı kullanıcı hesabı adı ve parola altında çalıştırın.  
  
### <a name="to-solve-scenario-2"></a>Senaryo 2 çözmek için  
  
1. Gelen **Başlat** menüsünde seçin **Denetim Masası**.  
  
2. Denetim Masası'ndaki çift **Yönetimsel Araçlar**.  
  
3. Yönetimsel Araçlar penceresinde, **yerel güvenlik ilkesi**.  
  
4. Yerel Güvenlik İlkesi penceresinde **yerel ilkeler**.  
  
5. İçinde **ilkeleri** sütunu, çift **ağ erişimi: Yerel hesaplar için paylaşım ve güvenlik modeli**.  
  
6. İçinde **ağ erişimi: Yerel hesaplar için paylaşım ve güvenlik modeli** iletişim kutusunda, yerel güvenlik ayarını **Klasik**, tıklatıp **Tamam**.  
  
    > [!CAUTION]
    > Güvenlik modeli Klasik olarak değiştirilmesi beklenmeyen Access'te paylaşılan dosyaları ve DCOM bileşenleri için neden olabilir. Bu değişiklik yaparsanız, uzak bir kullanıcı, yerel kullanıcı hesabı yerine ile Konuk kimlik doğrulaması yapabilir. Uzak bir kullanıcı, kullanıcı adınızı ve parolanızı eşleşiyorsa, bu kullanıcı herhangi bir klasör veya DCOM nesne dışarı paylaştığı erişebilir olacaktır. Bu güvenlik modeli kullandığınız makinedeki tüm kullanıcı hesaplarını güçlü parolalar veya hata ayıklama için bir yalıtılmış ağ Adası ayarlama ve yetkisiz erişimi önlemek için makineleri hata ayıklaması emin olun.  
  
7. Tüm pencereleri kapatın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata Ayıklayıcısı Ayarları ve Hazırlığı](../debugger/debugger-settings-and-preparation.md)
