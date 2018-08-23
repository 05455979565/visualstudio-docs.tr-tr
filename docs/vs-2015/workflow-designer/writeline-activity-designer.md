---
title: WriteLine etkinlik Tasarımcısı | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: .net-framework-4.6
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- System.Activities.Statements.WriteLine.UI
ms.assetid: 1b5f29a8-b7fd-477e-949e-2f689cae3c96
caps.latest.revision: 5
author: gewarren
ms.author: gewarren
manager: erikre
ms.openlocfilehash: f1085c7a8989ebfdecdf0e9782afeeaf1e9b4400
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42690647"
---
# <a name="writeline-activity-designer"></a>WriteLine Etkinlik Tasarımcısı
**WriteLine** etkinlik Tasarımcısı oluşturmak ve yapılandırmak için kullanılan bir <xref:System.Activities.Statements.WriteLine> etkinlik.  
  
## <a name="the-writeline-activity"></a>WriteLine etkinlik  
 <xref:System.Activities.Statements.WriteLine> Etkinlik metni belirtilen bir yazar <xref:System.IO.TextWriter> nesne. Hayır ise <xref:System.IO.TextWriter> belirtilen <xref:System.Activities.Statements.WriteLine> metin konsola yazar.  
  
### <a name="using-the-writeline-activity-designer"></a>WriteLine etkinlik Tasarımcısı kullanma  
 **WriteLine** etkinlik Tasarımcısı bulunabilir **Temelleri** kategorisi **araç kutusu**, hangi erişilen tıklayarak **araç kutusu**sekmesinde [!INCLUDE[wfd2](../includes/wfd2-md.md)] (Alternatif olarak, seçin **araç** gelen **görünümü** menüsünü veya CTRL + ALT + X.)  
  
 **WriteLine** etkinlik Tasarımcısı, gelen sürüklenebilir **araç kutusu** ve oturum bırakılan [!INCLUDE[wfd2](../includes/wfd2-md.md)] yüzey yerde etkinlikleri genellikle yerleştirilir, örneğin olarak içinde bir <xref:System.Activities.Statements.Sequence>. Bu, oluşturur bir <xref:System.Activities.Statements.WriteLine> etkinliği ile bir varsayılan <xref:System.Activities.Activity.DisplayName%2A> WriteLine biri. <xref:System.Activities.Activity.DisplayName%2A> Üst bilgisinde düzenlenebilir **WriteLine** etkinlik Tasarımcısı veya **DisplayName** özellik kılavuzunda kutusu.  
  
### <a name="the-writeline-properties"></a>WriteLine özellikleri  
 Aşağıdaki tabloda <xref:System.Activities.Statements.WriteLine> özellikleri Tasarımcısı'nda nasıl kullanıldığı açıklanmaktadır. Bu özellikler, özellik kılavuzunda düzenlenebilir ve bunlardan bazıları üzerinde düzenlenebilir [!INCLUDE[wfd2](../includes/wfd2-md.md)]Tasarımcı yüzeyine bırakın.  
  
|Özellik adı|Gerekli|Kullanım|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|Kolay adı <xref:System.Activities.Statements.WriteLine> etkinlik. WriteLine varsayılandır. Ancak <xref:System.Activities.Activity.DisplayName%2A> kati şekilde gerekli değil bir kullanmak için en iyi bir uygulamadır.|  
|<xref:System.Activities.Statements.WriteLine.Text%2A>|False|Yazılacak metin. Özellik ayarlamak için bir Visual Basic ifadesinin türü **metin** kutusuna **WriteLine** etkinlik Tasarımcısı veya özellik kılavuzunda.|  
|<xref:System.Activities.Statements.WriteLine.TextWriter%2A>|False|<xref:System.IO.TextWriter> Hangi <xref:System.Activities.Statements.WriteLine> Yazar <xref:System.Activities.Statements.WriteLine.Text%2A>. Konsol varsayılandır.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Temel öğeler](../workflow-designer/primitives-activity-designers.md)   
 [Ata](../workflow-designer/assign-activity-designer.md)   
 [gecikme](../workflow-designer/delay-activity-designer.md)   
 [InvokeMethod](../workflow-designer/invokemethod-activity-designer.md)