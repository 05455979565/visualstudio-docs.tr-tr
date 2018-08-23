---
title: 'Nasıl yapılır: etkinleştirme ve devre dışı Düzenle ve devam et | Microsoft Docs'
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
- /INCREMENTAL linker option
- Apply Code Changes command
- Edit and Continue, disabling
- code changes, applying in break mode
- INCREMENTAL linker option
- Edit and Continue, enabling
- break mode, applying code changes
- Edit and Continue, applying code changes
- Step command
- Go command
ms.assetid: fd961a1c-76fa-420d-ad8f-c1a6c003b0db
caps.latest.revision: 29
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 57a9ec8b8e25da6edb36e1983e45f7bb78251208
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42688228"
---
# <a name="how-to-enable-and-disable-edit-and-continue"></a>Nasıl Yapılır: Düzenle ve Devam Et'i Etkinleştirme veya Devre Dışı Bırakma
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [nasıl yapılır: etkinleştirme ve devre dışı Düzenle ve devam et](https://docs.microsoft.com/visualstudio/debugger/how-to-enable-and-disable-edit-and-continue).  
  
Düzenle ve devam et, etkinleştirmek veya devre dışı **seçenekleri** tasarım zamanında iletişim kutusu. Hata ayıklarken bu ayarı değiştiremezsiniz.  
  
 Düzenle ve works yalnızca hata ayıklama yapılarında devam edin. Yerel C++ için Düzenle ve devam et gerektirir / Incremental kullanma seçeneği.  
  
## <a name="procedures"></a>Yordamlar  
  
#### <a name="to-enabledisable-edit-and-continue"></a>Etkinleştirmek/devre dışı Düzenle ve devam et  
  
1.  Hata ayıklama seçenekleri sayfasını aç (**Araçlar / Seçenekler / hata ayıklama**).  
  
2.  Ekranı aşağı kaydırarak **Düzenle ve devam et** kategorisi.  
  
3.  Etkinleştirmek için seçin **etkinleştirme Düzenle ve devam et** onay kutusu. Devre dışı bırakmak için onay kutusunu temizleyin.  
  
    > [!NOTE]
    >  Etkin IntelliTrace ve hem IntelliTrace olayları ve çağrı bilgilerini toplamak, Düzenle ve Devam Et'i devre dışı bırakılmıştır. Daha fazla bilgi için [yapılandırma IntelliTrace](http://msdn.microsoft.com/en-us/7657ecab-e07e-4b1b-872d-f05d966be37e).  
  
4.  **Tamam**'ı tıklatın.  
  
 Bu seçenekler hakkında daha fazla bilgi için bkz. [genel, hata ayıklama, Seçenekler iletişim kutusu](../debugger/general-debugging-options-dialog-box.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Düzenle ve devam et](../debugger/edit-and-continue.md)



