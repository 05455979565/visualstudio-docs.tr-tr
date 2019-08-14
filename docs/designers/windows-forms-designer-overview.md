---
title: Windows Forms uygulamaları tasarlama
ms.date: 08/09/2019
ms.topic: conceptual
helpviewer_keywords:
- Windows Forms Designer
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 8280a60f1d265336d427079bdef6612b42ed4330
ms.sourcegitcommit: 6b0503ed8d25454d6e39a8e606910b3fa58cf1d2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/13/2019
ms.locfileid: "68984195"
---
# <a name="windows-forms-designer-overview"></a>Windows Form Tasarımcısı genel bakış

Visual Studio 'daki Windows Form Tasarımcısı, Windows Forms tabanlı uygulamalar oluşturmak için hızlı bir geliştirme çözümü sağlar. Windows Form Tasarımcısı, forma kolayca denetim eklemenizi, bunları düzenlemenizi ve olayları için kod yazmanızı sağlar. Windows Forms hakkında daha fazla bilgi için bkz. [Windows Forms genel bakış](/dotnet/framework/winforms/windows-forms-overview).

## <a name="functionality"></a>İşlevi

Tasarımcı kullanarak şunları yapabilirsiniz:

- Form için bileşenleri, veri denetimlerini veya Windows tabanlı denetimleri ekleyin.

- Tasarımcıda forma çift tıklayın ve bu formun `Load` olayına kod yazın veya formdaki bir denetime çift tıklayın ve denetimin varsayılan olayı için kod yazın.

- Denetimi seçip bir ad yazarak bir denetimin metin özelliğini düzenleyin.

- Seçili denetimin yerleşimini fareyle veya ok tuşlarıyla taşıyarak ayarlayın. Benzer şekilde, CTRL ve ok tuşlarını kullanarak yerleşimi daha kesin bir şekilde ayarlayın. Son olarak, Shift ve ok tuşlarını kullanarak denetimin boyutunu ayarlayın.

- Tıklatırken **SHIFT** veya **CTRL** ' i seçerek birden çok denetim seçin. SHIFT + tıklama **tuşlarını**kullanırken, seçilen ilk denetim, boyutu hizalarken veya düzenleme yaparken baskın denetimdir. **CTRL**+ tıklama kullanılırken, seçilen son denetim baskın olduğundan, baskın denetim her yeni denetim eklenmiş şekilde değişir. Alternatif olarak, seçmek istediğiniz denetimlerin çevresine bir seçim dikdörtgeni sürükleyerek birden çok denetim seçebilirsiniz.

> [!NOTE]
> Formun kaynak ( *. resx*) dosyasında değişiklik yapmak Için kaynak düzenleyicisini değil Windows Form Tasarımcısı kullanın. Form tabanlı. resx dosyasını düzenlerseniz, kaynak düzenleyicisinde yaptığınız değişikliklerin kaybedilmesi gerektiğini belirten bir uyarı görürsünüz. Bunun nedeni Windows Form Tasarımcısı. resx dosyasını oluşturur.

## <a name="see-also"></a>Ayrıca bkz.

- [Windows Forms genel bakış](/dotnet/framework/winforms/windows-forms-overview)
- [Windows Forms denetimleri](/dotnet/framework/winforms/controls/)
- [Windows Forms denetimleri için erişilebilirlik](/dotnet/framework/winforms/controls/providing-accessibility-information-for-controls-on-a-windows-form)
- [Windows Forms Kullanıcı girişi](/dotnet/framework/winforms/user-input-in-windows-forms)
- [Windows Forms veri bağlama](/dotnet/framework/winforms/windows-forms-data-binding)
- [Windows Forms uygulamalarını geliştirin](/dotnet/framework/winforms/advanced/)