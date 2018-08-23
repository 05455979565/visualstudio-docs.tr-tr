---
title: 'Hata ayıklama hazırlığı: Windows Forms uygulamaları | Microsoft Docs'
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
- VB
- CSharp
helpviewer_keywords:
- debugging Windows applications
- Windows applications, debugging
- debugging [Visual Studio], Windows applications
- debugging [J#], Windows applications
- debugging [C#], Windows applications
- debugging [Visual Basic], Windows applications
ms.assetid: 7092ee7f-8378-4def-aef8-1695bd97cf14
caps.latest.revision: 31
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a7f362db7c0ba56db2b5b5f2362ea7755e3076a0
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42686455"
---
# <a name="debugging-preparation-windows-forms-applications"></a>Hata Ayıklama Hazırlığı: Windows Forms Uygulamaları
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [hata ayıklama hazırlığı: Windows Forms uygulamaları](https://docs.microsoft.com/visualstudio/debugger/debugging-preparation-windows-forms-applications).  
  
Windows Forms proje şablonu, bir Windows Forms uygulaması oluşturur. Bu tür bir uygulamada hata ayıklama [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] oldukça basittir. Daha fazla bilgi için [bir Windows uygulaması projesi oluşturma](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa).  
  
 Proje şablonuyla bir Windows Forms projesi oluşturduğunuzda [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] hata ayıklama ve yayın yapılandırmaları için gereken ayarları otomatik olarak oluşturur. Gerekirse, bu ayarları değiştirebilirsiniz. Bu ayarlar değiştirilebilir  **\<proje adı > özellik sayfaları** iletişim kutusu (**Projem** Visual Basic'te).  
  
 Daha fazla bilgi için [önerilen özellik ayarları](../debugger/managed-debugging-recommended-property-settings.md).  
  
 Aşağıdaki tabloda bir ek önerilen özellik ayarı görüntüler.  
  
### <a name="configuration-properties-in-debug-tab"></a>Hata ayıklama sekmesindeki yapılandırma özellikleri  
  
|**Özellik adı**|**Ayarı**|  
|-----------------------|-----------------|  
|**Başlatma eylemi**|-Kümesine **başlangıç projesi** çoğu zaman. Kümesine **harici program Başlat** başka bir yürütülebilir başlatmak istiyorsanız başlattığınızda hata ayıklama (genellikle DLL'lerinde hata ayıklama için).|  
  
 Windows Forms uygulamaları içinde hata ayıklama [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], veya zaten çalışan bir uygulamaya ekleme. Ekleme hakkında daha fazla bilgi için bkz. [çalışan işlemlere ekleme](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md).  
  
### <a name="to-debug-a-c-f-or-visual-basic-windows-forms-application"></a>Bir C#, F # veya Visual Basic Windows Forms uygulamasında hata ayıklamak için  
  
1.  Projeyi [!INCLUDE[vsprvs](../includes/vsprvs-md.md)].  
  
2.  Kesme noktaları, gerektiği şekilde oluşturun.  
  
     Windows Forms uygulamaları, olay temelli olduğundan, kesme noktalarınız olay işleyici kodu veya olay işleyici kodu tarafından çağrılan yöntemler geçer. Kesme noktaları yerleştirmek için tipik olaylar şunlardır:  
  
    1.  ' A tıklayın, Enter vb. gibi bir denetim ile ilişkili olayları.  
  
    2.  Uygulama başlatma ve kapatma, yük, etkin, vb. gibi ilişkili olaylar.  
  
    3.  Odak ve doğrulama olayları.  
  
     Daha fazla bilgi için [Windows Forms'ta olay işleyicileri oluşturma](http://msdn.microsoft.com/library/6514e530-c6b8-489c-a8d2-eda7b7072701).  
  
3.  Üzerinde **hata ayıklama** menüsünde tıklatın **Başlat**.  
  
4.  İçinde açıklanan teknikleri kullanarak hata ayıklama [hata ayıklayıcı temel bilgileri](../debugger/debugger-basics.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yönetilen kodda hata ayıklama](../debugger/debugging-managed-code.md)   
 [C#, F # ve Visual Basic proje türleri](../debugger/debugging-preparation-csharp-f-hash-and-visual-basic-project-types.md)   
 [Nasıl yapılır: kümesi hata ayıklama ve yayın yapılandırmaları](../debugger/how-to-set-debug-and-release-configurations.md)   
 [Hata ayıklama yapılandırması proje ayarları C#](../debugger/project-settings-for-csharp-debug-configurations.md)   
 [Hata ayıklama yapılandırması proje ayarları bir Visual Basic](../debugger/project-settings-for-a-visual-basic-debug-configuration.md)   
 [Çalıştırma işlemleri iliştirme](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md)   
 [Windows Forms](http://msdn.microsoft.com/library/627df1e9-b254-41af-bbac-9a4f02810c54)



