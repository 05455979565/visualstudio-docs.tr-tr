---
title: Windows Workflow Foundation için hata ayıklayıcı çağrılıyor (eski) | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-workflow-designer
ms.topic: reference
helpviewer_keywords:
- stepping
- Step Over command
- stepping, commands
- debugging, using workflow debugger
- workflows, debugger
- workflow debugger, starting
- Step In command
- debugger, workflow
- Step Out command
- debugging workflows, starting the debugger
ms.assetid: d6f58e35-5cce-4ff2-9afc-b2d9d0f819cf
caps.latest.revision: 6
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: bcceca362f3c2a891d36f8f4e8071d0e35c8f164
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72658987"
---
# <a name="invoking-the-visual-studio-debugger-for-windows-workflow-foundation-legacy"></a>Windows Workflow Foundation için Visual Studio Hata Ayıklayıcısını Çağırma (Eski)
Bu konuda, eski [!INCLUDE[wfd1](../includes/wfd1-md.md)] [!INCLUDE[wf](../includes/wf-md.md)] uygulamalarda hata ayıklamada [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] hata ayıklayıcının nasıl kullanılacağı açıklanmaktadır. @No__t_1 veya [!INCLUDE[vstecwinfx](../includes/vstecwinfx-md.md)] hedeflemek gerektiğinde eski [!INCLUDE[wfd2](../includes/wfd2-md.md)] kullanın.

 Genellikle, diğer Visual Studio programlama dillerinde yazılmış programlarda hata ayıkladığınızda olduğu gibi eski iş akışlarının hatalarını ayıklayın. Aşağıdaki yollarla Windows Workflow Foundation için [!INCLUDE[vs_current_long](../includes/vs-current-long-md.md)] hata ayıklayıcıyı başlatabilirsiniz:

- Kullanılabilir işlemlerden çalışan bir iş akışı örneği seçmek için **hata ayıklama** menüsünde **İşleme İliştir** ' i seçin.

- İş akışının bir örneğini çalıştırmaya başlamak veya bir kesme noktası isabet ettikten sonra çalışmaya devam etmek için **F5** tuşuna basın.

## <a name="stepping-through-code"></a>Kod üzerinden adımla
 Hata ayıklayıcı, en yaygın hata ayıklama yordamlarından birini destekler, her seferinde tek bir satır yürüten adımlardır. Kod ile adımlamayı için üç komut vardır:

- **Adım adım**: **F11**kullanarak bir etkinliğe adım adım ekleyebilirsiniz. Hata ayıklayıcı, tanımlı herhangi bir işleyicide adımları. Hiçbir işleyici tanımlanmamışsa, etkinliğin üzerinde veya diğer etkinlikleri içeren bileşik etkinliklerle ilk yürütme etkinliğinin içine adımlayın. Tasarımcıdan kod işleyicilerine adımla şu etkinlikler için desteklenmez: **IfElseActivity**, **WhileActivity**, **ConditionedActivityGroup**veya **ReplicatorActivity**. Bu etkinliklerle ilişkili işleyicilerde hata ayıklamak için, koda açık kesme noktaları koymanız gerekir.

- **Dışarı adımla**: **Shift-F11**kullanarak bir etkinliğin dışına ileredebilirsiniz. Bir etkinliğin dışına geçmek, geçerli etkinliği ve tüm eşdüzey etkinliklerini tamamlamaya kadar çalıştırır. Hata ayıklayıcı daha sonra geçerli etkinliğin üst öğesiyle kesilir. Kod işleyiciden atlama yaparken, hata ayıklayıcı işleyicinin ilişkilendirildiği etkinliği keser.

- **Adımlama**: **F10**kullanarak bir etkinliğin üzerinde ilerliğinizi yapabilirsiniz. Bileşik bir etkinliğin üzerine adımlanıyor. hata ayıklayıcı bileşik etkinliğin ilk yürütülebilir alt öğesi üzerinde kesilir. **CodeActivity** etkinliği gibi bir Composite 'ın üzerine adımlarken, hata ayıklayıcı aktiviteyi ve ilgili işleyicileri ve bir sonraki etkinliğin üzerinde kesintiler yürütür. Yürütülen etkinlik bileşik bir etkinliğin son alt etkinliği ise, yürütmeden sonra hata ayıklayıcı üst etkinliği keser.

## <a name="attaching-to-a-process"></a>Bir Işleme iliştirme
 Bir işleme ekleyerek bir iş akışında hata ayıklamak için, **Işleme İliştir** Iletişim kutusunda **kullanılabilir işlemler** liste kutusundan kullanılabilir işlem ' i seçin. **Otomatik: Iş akışı kodu** Ekle metin kutusunda görüntülenmiyorsa, ardından **Seç**' **e** tıklayın. **Kod türünü seç** iletişim kutusunda, **Bu kod türlerinde hata ayıkla** ' ya tıklayın ve **iş akışı**' nı seçin. Ardından **Tamam** ' a tıklayın ve **Ekle**' ye tıklayın.

## <a name="debugging-with-f5"></a>F5 ile hata ayıklama
 Bir iş akışı ana bilgisayar uygulaması ve iş akışı DLL 'SI farklı Visual Studio projelerinde bulunuyorsa, örneğin, bir iş akışı etkinlik kitaplığı kullanırken, iş akışında hata ayıklamak için Visual Studio çözüm başlangıç projesi olarak iş akışı DLL projesini ayarlamanız gerekir **F5**'i kullanma. Ayrıca, iş akışı DLL projesinin **Başlat dış program** özelliğindeki ana bilgisayar uygulaması yolunu da ayarlamanız gerekir.

 Çözüm Gezgini bir başlangıç projesi ayarlamak için, proje adına sağ tıklayın ve **Başlangıç projesi olarak ayarla**' yı seçin. **Dış program Başlat** özelliğindeki ana bilgisayar yolunu ayarlamak için, Çözüm Gezgini iş akışı projesinin **Özellikler** düğümüne çift tıklayın ve **Hata Ayıkla** sekmesini seçin. **Başlat eylemi**altında **dış program Başlat** ' ı seçin ve hata ayıklamak istediğiniz iş akışını barındıran. exe dosyasının yolunu girin.

 Ana bilgisayar uygulaması başlangıç projesi olarak ayarlandıysa, yalnızca Visual Studio hata ayıklayıcısı hata ayıklama için çağrılır; Windows Workflow Foundation için [!INCLUDE[vs_current_long](../includes/vs-current-long-md.md)] hata ayıklayıcı çağrılmıyor. Visual Studio hata ayıklayıcısı kullanılırsa yalnızca C# veya Visual Basic kod kesme noktaları isabet edilir; iş akışı tasarımcısında ayarlanan kesme noktaları isabet etmez. Örneğin, tasarımcıda bir <xref:System.Workflow.Activities.ParallelActivity> etkinliğinde ayarladığınız bir kesme noktası, Windows Workflow Foundation için [!INCLUDE[vs_current_long](../includes/vs-current-long-md.md)] hata ayıklayıcı kullanılırsa, ancak Visual Studio hata ayıklayıcısını kullandığınızda kullanılmaz.

## <a name="see-also"></a>Ayrıca Bkz.
 [Nasıl yapılır: Iş akışlarında (eski)](../workflow-designer/how-to-set-breakpoints-in-workflows-legacy.md) [hata ayıklama eski Iş akışlarında](../workflow-designer/debugging-legacy-workflows.md) kesme noktaları ayarlama