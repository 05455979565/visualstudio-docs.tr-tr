---
title: 'Hata: Hedef bilgisayardaki Visual Studio uzaktan hata ayıklayıcı hizmeti geriye bu bilgisayara bağlanamıyor. | Microsoft Docs'
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
- vs.debug.error.service_access_denied_oncallback
dev_langs:
- FSharp
- VB
- CSharp
- C++
ms.assetid: 89ecf99d-66bf-4da0-a840-aa95b0be1702
caps.latest.revision: 15
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 27ae98de5ac5062bd55a3818b82e1f6ba771b612
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42694431"
---
# <a name="error-the-visual-studio-remote-debugger-service-on-the-target-computer-cannot-connect-back-to-this-computer"></a>Hata: Hedef bilgisayardaki Visual Studio Uzaktan Hata Ayıklayıcı hizmeti geriye bu bilgisayara bağlanamıyor
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [hata: hedef bilgisayardaki Visual Studio uzaktan hata ayıklayıcı hizmeti geriye bu bilgisayara bağlanamıyor](https://docs.microsoft.com/visualstudio/debugger/error-the-visual-studio-remote-debugger-service-on-the-target-computer-cannot-connect-back-to-this-computer).  
  
Bu hata, Visual Studio uzaktan hata ayıklayıcı hizmeti hata ayıklaması yaptığınız bilgisayarda bağlanmayı denediğinde doğrulayamayan bir kullanıcı hesabı altında çalıştığından emin anlamına gelir.  
  
 Aşağıdaki tabloda neler hesapları erişeceği gösterilmektedir bilgisayar:  
  
|||||  
|-|-|-|-|  
||LocalSystem hesabı|Etki alanı hesabı|Her iki bilgisayarda aynı kullanıcı adı ve parola sahip yerel hesaplar|  
|Her iki bilgisayar aynı etki alanında|Evet|Evet|Evet|  
|Her iki bilgisayarda çift yönlü güven bulunan etki alanları|Hayır|Hayır|Evet|  
|Bir çalışma grubunda bir veya her iki bilgisayar|Hayır|Hayır|Evet|  
|Farklı etki alanlarında bilgisayarları|Hayır|Hayır|Evet|  
  
 Bunlara ek olarak:  
  
-   Herhangi bir işlem hata ayıklama Visual Studio uzaktan hata ayıklayıcı hizmetin altında çalışacağı hesabın uzak bilgisayarda bir yönetici olmalıdır.  
  
-   Hesabın ayrıca verilecek sahip `Log on as a service` kullanan uzak bilgisayardaki ayrıcalığını **yerel güvenlik ilkesi** yönetim aracı.  
  
-   Bir yerel hesap erişim bilgisayarı kullanıyorsanız, yerel bir hesap altında Visual Studio uzaktan hata ayıklayıcı hizmeti çalıştırmanız gerekir.  
  
### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için  
  
1.  Visual Studio uzaktan hata ayıklayıcı hizmeti uzak bilgisayarda doğru ayarlandığından emin olun. Daha fazla bilgi için [ayarlanmış yukarı uzak Araçlar cihazda](http://msdn.microsoft.com/library/90f45630-0d26-4698-8c1f-63f85a12db9c).  
  
2.  Hata ayıklayıcısı ana bilgisayar erişimi olan bir hesabı altında uzaktan hata ayıklayıcı hizmeti, önceki tabloda gösterildiği gibi çalıştırın.  
  
### <a name="to-add-log-on-as-a-service-privilege"></a>"Hizmet olarak oturum aç" ayrıcalığı eklemek için  
  
1.  Üzerinde **Başlat** menüsünde seçin **Denetim Masası**.  
  
2.  Denetim Masası'ndaki seçin **Klasik Görünüm**, gerekirse.  
  
3.  **Yönetim Araçları**'na çift tıklayın.  
  
4.  Yönetimsel Araçlar penceresinde, **yerel güvenlik ilkesi**.  
  
5.  İçinde **yerel güvenlik ayarları** penceresini genişletin **yerel ilkeler** klasör.  
  
6.  Tıklayın **kullanıcı hakları ataması**.  
  
7.  İçinde **ilke** sütunu, çift tıklayın **hizmet olarak oturum açın** geçerli yerel Grup İlkesi atamalarını görüntülemek için **hizmet oturum açma** iletişim kutusu.  
  
8.  Yeni kullanıcı eklemek için tıklatın **kullanıcı veya Grup Ekle** düğmesi.  
  
9. Kullanıcı ekleme işlemini tamamladığınızda, tıklayın **Tamam**.  
  
### <a name="to-work-around-this-error"></a>Bu hatayı çözmek için  
  
-   Hizmet yerine bir uygulama olarak uzaktan hata ayıklama İzleyicisi'ni çalıştırın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Uzaktan hata ayıklama ve sorun giderme](../debugger/remote-debugging-errors-and-troubleshooting.md)   
 [Uzaktan hata ayıklama](../debugger/remote-debugging.md)



