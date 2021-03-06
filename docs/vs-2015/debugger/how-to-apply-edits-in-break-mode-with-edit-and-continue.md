---
title: 'Nasıl yapılır: Düzen ile kesme modunda düzenlemeleri uygulayın ve devam et | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.variables.failededit
dev_langs:
- FSharp
- VB
- CSharp
- C++
- VB
helpviewer_keywords:
- Edit and Continue [Visual Basic], applying edits in break mode
- break mode, applying code changes
- Edit and Continue, applying edits in break mode
- editing, break mode
- coding, editing in break mode
- code, editing in break mode
ms.assetid: 1eef7498-6a1f-4fba-8146-510adc6375c9
caps.latest.revision: 33
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 5c04dc0ae6e5272d2544ad7436fa7ca516c9a022
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "63437353"
---
# <a name="how-to-apply-edits-in-break-mode-with-edit-and-continue"></a>Nasıl yapılır: Düzen ile kesme modunda düzenlemeleri uygulayın ve devam et
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Düzenle ve devam et, kesme modunda kodunuzu düzenleyin ve ardından durdurup yeniden başlatmadan yürütme devam etmek için kullanabilirsiniz.  
  
 Düzenle ve devam et hata ayıklama aşağıdaki senaryolarda kullanılabilir değil:  
  
- Karma mod (yerel/yönetilen) hata ayıklama.  
  
- SQL hata ayıklama.  
  
- Bir Dr hata ayıklama. Watson dökümü.  
  
- İşlenmeyen bir özel durumdan sonra kod düzenleme, **işlenmemiş özel durumlarda çağrı yığınını geriye doğru izleme** seçeneği belirlenmez.  
  
- Katıştırılmış çalışma zamanı uygulama hata ayıklama.  
  
- Bir uygulama ile hata ayıklama **ekleme** uygulamasıyla çalışan yerine **Başlat** gelen **hata ayıklama** menüsü.  
  
- En iyi duruma getirilmiş kodda hata ayıklama.  
  
- 64 bitlik bir uygulama hedeflendiğinde, yönetilen kodda hata ayıklama. İsterseniz kullanım Düzenle ve devam et, hedef x86 için ayarlamanız gerekir. (_Proje_**özellikleri**, **derleme** sekmesinde **Gelişmiş derleyici** ayarı.).  
  
- Derleme hataları nedeniyle oluşturmak yeni bir sürüm başarısız olduktan sonra kodunuzu eski bir sürümü hata ayıklama.  
  
### <a name="to-edit-code-in-break-mode"></a>Kesme modunda kod düzenlemek için  
  
1. Aşağıdakilerden birini yaparak Kesme moduna girin:  
  
    - Kodunuzda bir kesme noktası ayarlayın ve ardından **hata ayıklamayı Başlat** gelen **hata ayıklama** menü ve kesme noktasına isabet uygulamaya tamamlanmasını bekleyin.  
  
         – veya –  
  
    - Hata ayıklamayı başlatın ve ardından **tümünü Kes** gelen **hata ayıklama** menüsü.  
  
         – veya –  
  
    - Bir özel durum oluştuğunda seçin **düzenlemeyi etkinleştir** üzerinde**özel durum Yardımcısı'nı**.  
  
2. İstenen ve yasal kod değişikliklerini yapın.  
  
     Daha fazla bilgi için [desteklenmeyen düzenlemeler Visual Basic Düzenle ve devam et](../debugger/unsupported-edits-in-visual-basic-edit-and-continue.md).  
  
    > [!NOTE]
    > Bir kod bu değişikliği yapmak için Düzenle ve devam et tarafından izin verilmiyor dener düzenlemeniz tarafından mor dalgalı çizgi altı çizili olacaktır ve bir görev görev listesinde görünür. Geçersiz kod değişikliği geri sürece kod yürütülmesine devam etmek mümkün olmayacaktır.  
  
3. Üzerinde **hata ayıklama** menüsünde tıklatın **devam** yürütme devam etmek için.  
  
     Kodunuz artık projeye dahil uygulanan düzenlemeleriniz ile yürütür.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Basic'de desteklenmeyen düzenlemeler Düzenle ve devam et](../debugger/unsupported-edits-in-visual-basic-edit-and-continue.md)   
 [Düzenle ve Devam Et (Visual Basic)](../debugger/edit-and-continue-visual-basic.md)
