---
title: Belirsizliği Çöz iletişim kutusu | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.Disambig
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- Resolve Ambiguity dialog box
- debugger, Resolve Ambiguity dialog box
- debugging [C++], resolving ambiguity
ms.assetid: d9f47455-a116-4c84-8bad-2dfbf4d77f74
caps.latest.revision: 10
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: b35d305bbd011adc02692cd7c9c687ac0bfc7d45
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "68148783"
---
# <a name="resolve-ambiguity-dialog-box"></a>Belirsizliği Çöz İletişim Kutusu
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

`Resolve Ambiguity` İletişim kutusu, hata ayıklayıcı görüntüleneceği konumun seçtiğinizde görüntülenir. Örneğin, C++ şablonları kullanıyorsanız, tek işlevi şablondan birden çok işlevler oluşturabilirsiniz. Şablonu kaynak konumda hata ayıklayıcıyı durdurur ve seçtiğiniz `Go To Disassembly`, hata ayıklayıcı birden çok seçenek vardır. Şablondan oluşturulan her işlev kendi ayrıştırılmış kodu bulunur ve hata ayıklayıcı, görüntülemek istediğiniz hangi kodun bilmez. `Resolve Ambiguity` İletişim kutusunda istediğiniz konuma karşılık gelen tüm konumlara listesinden seçmenize imkan tanır.  
  
 `Choose the specific location`  
 Komutunuz için karşılık gelen tüm konumlarda listeler.  
  
 `Address`  
 Her işlev için bellek adresleri gösterilir.  
  
 `Function`  
 Her işlevin adını gösterir.  
  
 `Module`  
 Modülü (EXE veya DLL) gösterir işlev için nesne kodu içeren.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata Ayıklayıcısındaki İfadeler](../debugger/expressions-in-the-debugger.md)
