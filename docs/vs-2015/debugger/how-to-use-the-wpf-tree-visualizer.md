---
title: 'Nasıl yapılır: WPF ağacı Görselleştiricisini kullanma | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- WPF, debugging
- debugging, WPF
ms.assetid: 2a1bf1cd-90f9-4d06-9fb4-1bfc925afef3
caps.latest.revision: 21
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 381dc45351ae03e615afbdd31239869e3dba8e4e
ms.sourcegitcommit: 75807551ea14c5a37aa07dd93a170b02fc67bc8c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2019
ms.locfileid: "67825429"
---
# <a name="how-to-use-the-wpf-tree-visualizer"></a>Nasıl yapılır: WPF Ağacı Görselleştiricisini kullanma
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

WPF ağacı görselleştiricisini WPF nesne görsel ağacını keşfedin ve o ağaç içinde bulunan nesneler için WPF bağımlılık özellikleri görüntülemek için kullanabilirsiniz. Görsel ağacı hakkında daha fazla bilgi için bkz: [WPF içinde ağaçlar](https://msdn.microsoft.com/library/e83f25e5-d66b-4fc7-92d2-50130c9a6649). Bağımlılık özellikleri hakkında daha fazla bilgi için bkz: [bağımlılık özelliklerine genel bakış](https://msdn.microsoft.com/library/d119d00c-3afb-48d6-87a0-c4da4f83dee5).  
  
 WPF ağacı görselleştiricisini açtığınızda, iki bölme görürsünüz: **görsel ağacı** soldaki ve **özelliklerini** _adı_ **:**  _Tür_ sağ bölmesinde. Herhangi bir nesne seçin **görsel ağacı** bölmesinde ve **özelliklerini** _adı_ **:** _türü_ bölmesi Bu nesne özelliklerini göstermek için otomatik olarak güncelleştirilir.  
  
### <a name="to-open-the-wpf-tree-visualizer"></a>WPF ağacı görselleştiricisini açmak için  
  
1. Bir DataTip içinde **Watch** penceresinde **Otolar** penceresinde veya **Yereller** penceresinde, bir WPF nesne adının yanındaki oka bitişik için büyüteç simgesini tıklayın.  
  
     Görselleştiriciler listesi görüntülenir.  
  
2. Tıklayın **WPF ağacı Görselleştiricisini**.  
  
### <a name="to-search-the-visual-tree"></a>Görsel ağacı aramak için  
  
- İçinde **görsel ağacı** bölmesinde, içinde arama yapmak istediğiniz dizeyi yazın **arama** kutusu.  
  
  WPF ağacı görselleştiricisini, yazdığınız dizesiyle eşleşen görsel ağaçta ilk nesnenin hemen bulur. Daha fazla karakter daha doğru bir eşleşme bulmak için yazın.  

  - Sonraki eşleşmeye görsel ağacı içinde gitmek için tıklayın **sonraki**.  

  - Önceki eşleşmeye geri gitmek için tıklayın **önceki**.  

  - Arama ölçütlerini temizlemek için tıklatın **Temizle**.  

### <a name="to-search-the-properties-list"></a>Özellikler listesinde aramak için  
  
- İçinde **özelliklerini** _adı_ **:** _türü_ bölmesinde, içinde arama yapmak istediğiniz dizeyi yazın **filtre**kutusu.  
  
  WPF ağacı görselleştiricisini hemen yazdığınız dizeyi eşleştir özelliklerini bulur; Artık, listede yalnızca yazdığınız dize eşleşen özellikler görüntülenir. Daha fazla karakter daha doğru bir eşleşme bulmak için yazın.  

  - Arama ölçütlerini temizlemek için tıklatın **Temizle**.  
  
### <a name="to-close-the-visualizer"></a>Görselleştirici kapatmak için  
  
- Tıklayın **Kapat** iletişim kutusunun sağ alt köşesindeki simgeyi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Nasıl yapılır: Görselleştirici kullanma](../misc/how-to-use-a-visualizer.md)   
 [Özel Görselleştiriciler oluşturma](../debugger/create-custom-visualizers-of-data.md)   
 [WPF içinde ağaçlar](https://msdn.microsoft.com/library/e83f25e5-d66b-4fc7-92d2-50130c9a6649)   
 [Bağımlılık Özelliklerine Genel Bakış](https://msdn.microsoft.com/library/d119d00c-3afb-48d6-87a0-c4da4f83dee5)
