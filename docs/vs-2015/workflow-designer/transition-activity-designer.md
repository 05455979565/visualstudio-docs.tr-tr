---
title: Geçiş etkinlik Tasarımcısı | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: .net-framework-4.6
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- System.Activities.Statements.Transition.UI
ms.assetid: f6e8b5cc-7fb8-4699-9703-f3c9fc7cc316
caps.latest.revision: 7
author: steved0x
ms.author: gewarren
manager: erikre
ms.openlocfilehash: b144b47670f794ce29d01d3916c3f2f4295fff9e
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42697364"
---
# <a name="transition-activity-designer"></a>Transition Etkinlik Tasarımcısı
A <xref:System.Activities.Statements.Transition> iki durum arasında geçiş temsil eder.  
  
## <a name="using-the-transition-activity-designer"></a>Geçiş etkinlik Tasarımcısını kullanma  
 Transition etkinlik Tasarımcısı iki durum arasında geçiş yapılandırmanıza olanak sağlar.  
  
### <a name="transition-properties-in-the-workflow-designer"></a>İş akışı tasarımcısında geçiş özellikleri  
 Aşağıdaki tabloda <xref:System.Activities.Statements.Transition> iş akışı Tasarımcısı'nı kullanarak ayarlanabilir ve Tasarımcısı'nda nasıl kullanıldığını açıklar.  
  
|Özellik adı|Gerekli|Kullanım|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Statements.Transition.DisplayName%2A>|False|Kolay adı belirtir <xref:System.Activities.Statements.Transition> etkinlik Tasarımcısı. Varsayılan değer **T1**. Değer özellik kılavuzunda, genişletilmiş geçiş Tasarımcı başlığını ve genişletilmiş geçiş Tasarımcı içinde eylem bölümü başlığını düzenlenebilir. <xref:System.Activities.Activity.DisplayName%2A> İş akışı Tasarımcısı üst kısmında görüntülenen içerik haritalı gezinme kullanılır.<br /><br /> Ancak <xref:System.Activities.Activity.DisplayName%2A> kati şekilde gerekli değil kullanmak için en iyi bir uygulamadır.|  
|<xref:System.Activities.Statements.Transition.Condition%2A>|False|Varsa, değerlendirilmelidir bir ifade belirtir **True** denetimi hedef duruma geçmeden önce. Bu durum, özellik kılavuzunda ve genişletilmiş geçiş Tasarımcısı'nda düzenlenebilir. Birden çok koşulu paylaşılan bir geçiş aşamasında, geçişi Tasarımcısı'nda göründükleri sırayla değerlendirilir. **Not:** unutmayın <xref:System.Activities.Statements.Transition.Condition%2A> değerlendiren bir geçişin **False** (veya tüm koşulları bir paylaşılan tetikleyici geçişi için değerlendirmek **False**), geçiş gerçekleşmez ve tüm tetikleyiciler durumundan tüm geçişler için zamanlanacak. Bu öğreticide, bu durum koşulları yapılandırılmış yol nedeniyle meydana olamaz (tahmin doğru veya yanlış olup belirli eylemler uyguluyoruz).|  
|**Kaynak**|Doğru|Bu geçiş kaynaklandığı durumu gösterir. Kaynak durumu adına tıklayarak Tasarımcı görünümü için genişletilmiş görünümünü bu duruma geçer. Geçiş oluşturulur ve değiştirilemez bu değer ayarlanır.|  
|<xref:System.Activities.Statements.Transition.Trigger%2A>|False|Tamamlama, geçişi başlatan etkinlik belirtir. Bu etkinlik ayarlamak için bir etkinlikten sürükleyin **araç kutusu** üzerine bırakın **tetikleyici** geçişin bölümü.|  
|<xref:System.Activities.Statements.Transition.Action%2A>|False|Tetikleyici etkinlik tamamlandığında çalıştırılan etkinlik belirtir ve <xref:System.Activities.Statements.Transition.Condition%2A>, varsa, değerlendiren **true**. Bu etkinlik sonrasında hedef durumuna geçiş yaparken yürütülür <xref:System.Activities.Statements.State.Exit%2A> kaynak durumu için etkinlik varsa yürütülür. Geçiş Tasarımcı genişletildiğinde, bu değer bir etkinlikten sürükleyerek ayarlanabilir **araç kutusu** üzerine sürükleyip bırakarak **eylem** geçişin bölümü. Tek bir geçiş için birden fazla eylem olabilir. Bireysel eylemleri genişletilir ve sözleşmeleri yapılır ve yukarı veya aşağı ok olduğunda bir geçiş birden çok eylem eylemini görüntülenen sıralanabilir.|  
|**Hedef**|Doğru|Geçiş tamamlandıktan sonra Durum makinesi için geçiş durumu gösterir. Bu karşılık gelir <xref:System.Activities.Statements.Transition.To%2A> nesne modelinde geçiş özelliği. Hedef durum adına tıklayarak Tasarımcı görünümü için genişletilmiş görünümünü bu duruma geçer. Bu değer, geçiş oluşturulduğunda ve tasarımcıda hedef duruma geçiş bağlanan oku sürükleyerek değiştirilebilir ayarlanır.|  
  
### <a name="creating-transitions"></a>Geçiş oluşturma  
 Geçişler, bir çizgi bir durumdan diğerine sürükleyerek ya da bir durumda bir durum başka bir duruma sürüklediğinizde görüntülenen üçgenler üzerine bırakarak oluşturulur. Sürükleyerek bir geçiş oluşturmak için kaynak durumu edge üzerinde fareyi üzerine gelin ve bir satır kaynak durumu hedef durumuna sürükleyin. Bırakarak bir geçiş oluşturmak için hedef durumu ve kaynak durumu gelin, sürükleyip görünen dört üçgenler birini sürüklediğinizde kaynak durumu. Hedef durumu gelen sürüklediğiniz ya da yeni bir durum olabilir **araç kutusu**, ya da mevcut bir durumu, iş akışı Tasarımcısı'ndan sürüklediğiniz.  
  
> [!NOTE]
>  Kadar 76 geçiş iş akışı Tasarımcısı'nı kullanarak oluşturulan bir durum makinesindeki tek bir durumda olabilir. İş Akışı Tasarımcısı dışında oluşturulan bir durum geçişlerini sınırı yalnızca sistem kaynaklarının yetersizliği sınırlıdır.  
  
 Paylaşılan tetikleyici geçişi, aynı olayın paylaşan geçişleri kümesidir. Paylaşılan tetikleyici koşullu ilerleme ortak bir tetikleyici olaya paylaşan birden çok geçiş için yapılandırılmış bir ifade değerlendirme göre bir hedef duruma olanak tanır. Geçiş için ek eylemler eklemek ve paylaşılan bir geçiş oluşturmak için istenen geçiş başlangıcını gösteren daireye tıklayın ve istenen duruma sürükleyin. Aynı tetikleyici olarak ilk geçiş yeni geçişi paylaşır, ancak benzersiz bir koşulu ve eylem gerekir. Paylaşılan geçişleri de oluşturulabilir gelen geçiş Tasarımcısı'nda tıklayarak **paylaşılan tetikleyici geçişi Ekle** geçiş Tasarımcısı'nı seçip ardından istediğiniz hedef durumu alt kısmındaki  **Bağlanmak için kullanılabilir durumları** açılır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Durum makinesi](../workflow-designer/statemachine-activity-designer.md)   
 [Son durum](../workflow-designer/finalstate-activity-designer.md)   
 [durumu](../workflow-designer/state-activity-designer.md)