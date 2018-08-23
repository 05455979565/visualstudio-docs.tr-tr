---
title: Açık dosya komutu | Microsoft Docs
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
- file.openfile
helpviewer_keywords:
- Open File command
- File.OpenFile command
- of command
ms.assetid: a51a83fc-e3c6-4fa2-8882-8b7b6c0a6406
caps.latest.revision: 20
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 51be74b491ee9a45cfac4735332146b9c5ffb06d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42693879"
---
# <a name="open-file-command"></a>Dosya Aç Komutu
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [açık dosya komutu](https://docs.microsoft.com/visualstudio/ide/reference/open-file-command).  
  
  
Varolan bir dosyayı açar ve bir düzenleyici belirtmenize olanak tanır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
File.OpenFile filename [/e:editorname]  
```  
  
## <a name="arguments"></a>Arguments  
 `filename`  
 Gerekli. Tam veya kısmi yolu ve dosya adını dosyayı açın. Boşluk içeren yolları tırnak içine alınmalıdır.  
  
## <a name="switches"></a>Anahtarlar  
 / e:`editorname`  
 İsteğe bağlı. Dosyanın açılmasını düzenleyicinin adı. Bağımsız değişken belirtildi, ancak hiçbir Düzenleyici adı verilmesi, **birlikte Aç** iletişim kutusu görüntülenir.  
  
 / E:`editorname` bağımsız değişkeni sözdizimini açık ile iletişim kutusunda tırnak işaretleri arasına göründükleri gibi Düzenleyicisi adları kullanır.  
  
 Örneğin, bir dosya kaynak kod Düzenleyicisi'nde açmak için / e: şunları girersiniz`editorname` bağımsız değişken.  
  
```  
/e:"Source Code (text) Editor"  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bir yol girin gibi doğru yol ve dosya adı bulmak otomatik tamamlama çalışır.  
  
## <a name="example"></a>Örnek  
 Bu örnek, Kaynak Kod Düzenleyicisi'nde "Test1.css" stil dosyasını açar.  
  
```  
>File.OpenFile "C:\My Projects\project1\Test1.css" /e:"Source Code (text) Editor"  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio komutları](../../ide/reference/visual-studio-commands.md)   
 [Komut penceresi](../../ide/reference/command-window.md)   
 [Komut penceresi](../../ide/reference/immediate-window.md)   
 [Bul/komut kutusu](../../ide/find-command-box.md)   
 [Visual Studio Komut Diğer Adları](../../ide/reference/visual-studio-command-aliases.md)



