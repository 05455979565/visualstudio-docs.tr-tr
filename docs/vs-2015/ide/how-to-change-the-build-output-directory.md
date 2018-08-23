---
title: 'Nasıl yapılır: Derleme çıktı dizinini değiştirme | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- output directory, changing
ms.assetid: a8333c89-afb2-4b1d-b2e2-9146da852402
caps.latest.revision: 16
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: a12accc247d79a68eaafc9878dc5e9d7d8c7d6dc
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42692521"
---
# <a name="how-to-change-the-build-output-directory"></a>Nasıl Yapılır: Derleme Çıktı Dizinini Değiştirme
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [nasıl yapılır: Derleme çıktı dizinini değiştirme](https://docs.microsoft.com/visualstudio/ide/how-to-change-the-build-output-directory).  
  
(Hata ayıklama, yayın veya her ikisi için) yapılandırma olarak projeniz tarafından oluşturulan çıkış konumunu belirtebilirsiniz.  
  
> [!NOTE]
>  Varsa bir **Kurulum** proje, bu makalenin sonundaki nota bakın.  
  
## <a name="changing-the-build-output-directory"></a>Derleme çıktı dizinini değiştirme  
  
#### <a name="to-change-the-build-output-directory"></a>Derleme çıkış dizinini değiştirme  
  
1.  Menü çubuğunda, **proje**, *Appname* **özellikleri**. Ayrıca'nde proje düğümüne sağ **Çözüm Gezgini** seçip **özellikleri**.  
  
2.  Visual Basic projesi varsa, seçin **derleme** sekmesi. Bir Visual C# projesi varsa, seçin **derleme** sekmesi. Bir C++ veya JavaScript projesi varsa, seçin **genel** sekmesi.  
  
3.  Yapılandırma açılan sayfanın üstünde çıktısı yapılandırmayı seçin. dosya konumu (hata ayıklama, yayın veya tümü) değiştirmek istediğiniz.  
  
     Çıkış yolu girdisini bulun (**yapı çıkış yolu** Visual Basic'te **çıkış dizinine** Visual C++ ' ta **çıkış yolu** JavaScript ve C#). Proje dizinine göre yeni bir derleme çıktı dizinini belirtin.  
  
> [!NOTE]
>  Kurulum projesinde **çıktı dosyası adını** kutusu yalnızca, proje dosyalarının konumu değil Setup.exe dosyasının konumunu değiştirir. Daha fazla bilgi için **derleme, yapılandırma özellikleri, dağıtım Proje Özellikleri iletişim kutusu**.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleme sayfası, Proje Tasarımcısı (C#)](../ide/reference/build-page-project-designer-csharp.md)   
 [Genel özellik sayfası (Proje)](http://msdn.microsoft.com/library/593b383c-cd0f-4dcd-ad65-9ec9b4b19c45)   
 [Derleme ve Oluşturma](../ide/compiling-and-building-in-visual-studio.md)



