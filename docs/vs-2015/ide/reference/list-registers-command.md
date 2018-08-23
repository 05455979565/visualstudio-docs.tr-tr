---
title: Liste kayıtları komut | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- debug.listregisters
helpviewer_keywords:
- list registers command
- Debug.ListRegisters command
- ListRegisters command
ms.assetid: 19a9d789-f6c9-46b3-b1f6-4934fc33e055
caps.latest.revision: 14
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: c9ff1287bb4c92d074c0a0e123d48ddb7e61cc90
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42693248"
---
# <a name="list-registers-command"></a>Yazmaçları Listele Komutu
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [Listele komutu kaydeder](https://docs.microsoft.com/visualstudio/ide/reference/list-registers-command).  
  
  
Seçilen değeri kaydeder ve olanak tanır görüntüler liste kayıtları göstermek için değiştirin.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
Debug.ListRegisters [/Display [{register|registerGroup}...]] [/List]  
[/Watch [{register|registerGroup}...]]  
[/Unwatch [{register|registerGroup}...]]  
```  
  
## <a name="switches"></a>Anahtarlar  
 / Görüntüleme [{`register`&#124;`registerGroup`}...]  
 Belirtilen değerleri görüntüler `register` veya `registerGroup`. Hayır ise `register` veya `registerGroup` belirtilirse, kayıtları varsayılan listesi görüntülenir. Hiçbir anahtarı belirtilmişse davranışı aynıdır. Örneğin:  
  
 `Debug.ListRegisters /Display eax`  
  
 eşdeğerdir  
  
 `Debug.ListRegisters eax`  
  
 / Listeleme  
 YAZMAÇ grupları listesinde tüm görüntüler.  
  
 / İzleme [{`register`&#124;`registerGroup`}...]  
 Bir veya daha fazla ekler `register` veya `registerGroup` değerleri listesi.  
  
 / Unwatch [{`register`&#124;`registerGroup`}...]  
 Bir veya daha fazla kaldırır `register` veya `registerGroup` listedeki değerler.  
  
## <a name="remarks"></a>Açıklamalar  
 Diğer ad `r` yerine kullanılan `Debug.ListRegisters`.  
  
## <a name="example"></a>Örnek  
 Bu örnekte `Debug.ListRegisters` diğer `r` kayıt grubunun değerleri görüntülemek için `Flags`.  
  
```  
r /Display Flags  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio komutları](../../ide/reference/visual-studio-commands.md)   
 [Hata ayıklama temelleri: Yazmaçlar penceresi](../../debugger/debugging-basics-registers-window.md)   
 [Nasıl yapılır: yazmaçlar penceresini kullanma](../../debugger/how-to-use-the-registers-window.md)



