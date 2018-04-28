---
title: '9. adım: diğer özellikleri deneme'
ms.custom: ''
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-acquisition
ms.topic: conceptual
ms.assetid: 1b0c5c80-e5a6-4f69-a4a4-0e89a82d4de0
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: bc842af3723a8b056d1de684bd798f4fda37cff8
ms.sourcegitcommit: 04a717340b4ab4efc82945fbb25dfe58add2ee4c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/28/2018
---
# <a name="step-9-try-other-features"></a>9. adım: diğer özellikleri deneme
Daha fazla bilgi edinmek için simgeleri ve renkleri değiştirmeyi, oyun zamanlayıcısı ve sesler eklemeyi deneyin. Oyunu daha zorlu hale getirmek için tahtayı büyütmeyi ve zamanlayıcıyı ayarlamayı deneyin.  
  
 Tamamlanmış bir örnek sürümünü indirmek için bkz: [tam eşleşen oyun öğretici örnek](http://code.msdn.microsoft.com/Complete-Matching-Game-4cffddba).  
  
## <a name="to-try-other-features"></a>Diğer özellikleri denemek için  

-   Simgelerin ve renklerin yerine kendi tercih ettiklerinizi kullanın.  

    > [!TIP]
    >  Etiketin bakmayı deneyin [Forecolor](http://msdn.microsoft.com/library/system.windows.forms.control.forecolor.aspx) özelliği.  

-   Oyuncunun oyunu kazanmasının ne kadar sürdüğünü izleyen bir oyun zamanlayıcısı ekleyin.  

    > [!TIP]
    >  Bunu yapmak için geçen süre yukarıdaki formda görüntülemek için bir etiket ekleyebilirsiniz <xref:System.Windows.Forms.TableLayoutPanel>, ve başka bir zamanlayıcı süreyi izlemek amacıyla forma ekleyin. Oyuncu oyuna başladığında zamanlayıcıyı başlatmak ve son iki simgeyi eşleştirdikten sonra zamanlayıcıyı durdurmak için kod kullanın.  

-   Oyuncu bir eşleşme bulduğunda çalacak bir ses, eşleşmeyen iki simgeyi açtığında çalacak başka bir ses ve program simgeleri yeniden gizlediğinde çalacak üçüncü bir ses ekleyin.  

    > [!TIP]
    >  Ses çalınmaya kullanabileceğiniz <xref:System.Media> ad alanı. Bkz: [Windows Forms uygulamasında (C#) ses çalma](http://youtu.be/qOh4ooHg1UU) veya [Visual Basic'te ses çalınmaya nasıl](http://youtu.be/-4oPDeQrtMs) daha fazla bilgi için.  
  
-   Oyun tahtasını büyüterek oyunu zorlaştırın.  

    > [!TIP]
    >  Daha fazlasını satırları ve sütunları için TableLayoutPanel - eklemeniz gerekir, ayrıca oluşturduğunuz simgeler sayısını göz önünde bulundurun gerekir.  

-   Oyuncunun tepki verirken çok yavaş davranması ve belirli bir süre dolmadan önce ikinci simgeyi seçmemesi durumunda ilk simgeyi gizleyerek oyunu daha zorlu hale getirin.  

## <a name="to-continue-or-review"></a>Devam etmek veya gözden geçirmek için  
  
-   Bir yerde tıkanıp kalırsanız veya programlamayla ilgili sorularınız olursa, MSDN forumlarından birinde sorunuzu göndermeyi deneyin. Bkz: [Visual Basic Forumu](http://social.msdn.microsoft.com/Forums/home?forum=vbgeneral) ve [Visual C# Forumu](http://social.msdn.microsoft.com/Forums/home?forum=csharpgeneral).  
  
-   Yararlanabileceğiniz harika ve ücretsiz video öğrenme kaynakları vardır. Visual Basic'te programlama hakkında daha fazla bilgi için bkz: [Visual Basic temelleri: yeni başlayanlar için geliştirme](http://channel9.msdn.com/Series/Visual-Basic-Development-for-Absolute-Beginners). Visual C# programlama hakkında daha fazla bilgi için bkz: [C# temelleri: yeni başlayanlar için geliştirme](http://channel9.msdn.com/Series/C-Sharp-Fundamentals-Development-for-Absolute-Beginners).  
  
-   Eğitmen önceki adıma dönmek için bkz: [adım 8: oyuncunun kazandığını doğrulamak için yöntem ekleme](../ide/step-8-add-a-method-to-verify-whether-the-player-won.md).
