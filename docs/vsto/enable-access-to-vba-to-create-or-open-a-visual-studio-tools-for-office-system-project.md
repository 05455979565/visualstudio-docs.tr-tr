---
title: VSTO sistem projesi oluşturmak/açmak için VBA erişimi
decsprition: You must explicitly enable access to the Office VBA project system before you can create or open a Visual Studio Tools for Office system project
titleSuffix: Visual Studio Tools for Microsoft Office
ms.custom: seodec18
ms.date: 08/14/2019
ms.topic: conceptual
f1_keywords:
- vst.project.vbawrongversion
- VST.Project.VBASecurityGenericError
- VST.Project.VBASecurityPermissions
- VST.SelectDocWizard.MissingCOM
- VST.Project.VBASecurityNotSet
dev_langs:
- VB
- CSharp
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 3199b23f7ad1bb45fd509d2a9b5cd21da1a49971
ms.sourcegitcommit: 209ed0fcbb8daa1685e8d6b9a97f3857a4ce1152
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/16/2019
ms.locfileid: "69551549"
---
# <a name="enable-access-to-vba-to-create-or-open-a-visual-studio-tools-for-the-microsoft-office-system-project"></a>Microsoft Office sistemi projesi için Visual Studio Araçları oluşturmak veya açmak üzere VBA 'a erişimi etkinleştir

Microsoft Office sistemi projesi için bir Visual Studio Araçları oluşturmadan veya açmadan önce Microsoft Office Visual Basic for Applications (VBA) proje sistemine erişimi açıkça etkinleştirmeniz gerekir.

 Microsoft Office geliştirme projeleri, Microsoft Office Word ve Microsoft Office Excel 'de Visual Basic for Applications (VBA) proje sistemine, projeler Visual Basic for Applications kullanmasa bile erişimi gerektirir. Hem Visual Basic hem de C# projelerdeki denetimlerin tasarım zamanı desteği, Visual Basic for Applications proje sistemine bağlıdır.

 Bazı Microsoft Office makro virüsleri, kendilerini yaymaya yönelik bir yol olarak Visual Basic for Applications proje sistemini otomatikleştirmeye çalışır. Visual Basic for Applications proje sistemine erişimi etkinleştirerek, makro virüslerinin yayılmasının önlenmesine yardımcı olan bir korumayı kaldırırsınız. Ancak, normal makro güvenliği yerinde kalır, bu nedenle, makro güvenlik düzeyi ve Office uygulamalarınız için tuttuğunuz güvenilen yayımcılar listesi bilgisayarınızda herhangi bir makronun çalışıp çalışmadığını tespit eder.

> [!NOTE]
> Bu yalnızca geliştirme bilgisayarı için geçerlidir. Son kullanıcı bilgisayarlarında Office çözümlerini çalıştırmak için bu seçeneğin etkinleştirilmesi gerekmez.

 Visual Basic for Applications proje sistemine erişimi devre dışı bırakmak, virüslerden korunmanıza yardımcı olmak açısından, bilgisayarınız bir makro ile bulaşmışsa bazı virüslerin diğer belgelere yayılmasını durdurmaya yardımcı olur. virüsten. Bu seçenek, bilgisayarınız için ek bir koruma katmanı olarak varsayılan olarak devre dışıdır, ancak en iyi güvenlik yöntemlerini takip ediyorsanız bilgisayarınızı virüslere açık hale getirir.

 Office makro virüslerine karşı en iyi koruma, Office 'i yüksek veya çok yüksek güvenlik düzeyinde çalıştırmak, yalnızca doğrulanmış, bilinen kaynaklardaki makrolara güvenmek ve güvenlik düzeltme ekleri ve virüs tarayıcıları ile güncel kalmak için.

 **Visual Basic projesine erişimi** el ile etkinleştirebilir veya devre dışı bırakabilirsiniz.

 VBA veya COM hataları görürseniz Office yüklemenizi onarabilirsiniz.

[!include[Add-ins note](includes/addinsnote.md)]

## <a name="to-enable-or-disable-access-to-visual-basic-projects"></a>Visual Basic projelerine erişimi etkinleştirmek veya devre dışı bırakmak için

1. **Dosya** sekmesine tıklayın.

2. **Seçenekler**' e tıklayın.

3. **Güven Merkezi**' ne ve ardından **Güven Merkezi ayarları**' na tıklayın.

4. **Güven Merkezi**'Nde **makro ayarları**' na tıklayın.

5. Visual Basic projelerine erişimi etkinleştirmek veya devre dışı bırakmak için **VBA proje nesne modeline güven erişimini** işaretleyin veya işaretini kaldırın.

6.           **Tamam**'ı tıklatın.

### <a name="to-enable-or-disable-access-to-visual-basic-projects-with-the-2007-microsoft-office-system"></a>2007 Microsoft Office sistemiyle Visual Basic projelerine erişimi etkinleştirmek veya devre dışı bırakmak için

1. Word veya Excel 'deki **Araçlar** menüsünde **makro**' nın üzerine gelin ve ardından **güvenlik**' e tıklayın.

2. **Güvenlik** iletişim kutusunda, **Güvenilen Yayımcılar** sekmesine tıklayın.

3. **Visual Basic projesine erişimi**devre dışı bırakmak veya kaldırmak için seçin.

4. **Tamam**'ı tıklatın.

## <a name="to-set-your-office-macro-security-level"></a>Office makro güvenlik düzeyinizi ayarlamak için

1. **Dosya** sekmesine tıklayın.

2. **Seçenekler**' e tıklayın.

3. **Güven Merkezi**' ne ve ardından **Güven Merkezi ayarları**' na tıklayın.

4. **Güven Merkezi**'Nde **makro ayarları**' na tıklayın.

5. **Makro ayarları** bölümünde, istenen ayarı seçin.

6.           **Tamam**'ı tıklatın.

### <a name="to-set-your-office-macro-security-level-with-the-2007-microsoft-office-system"></a>Office makro güvenlik düzeyinizi 2007 Microsoft Office sistemiyle ayarlamak için

1. Word veya Excel 'deki **Araçlar** menüsünde **makro**' nın üzerine gelin ve ardından **güvenlik**' e tıklayın.

2. **Güvenlik düzeyi** sekmesinde, istenen ayarı seçin.

    **Güvenlik düzeyi** sekmesi her bir düzey hakkındaki ayrıntıları içerir. Daha fazla bilgi için Office Yardımı 'nda "makro güvenlik düzeyleri" konusuna bakın.

### <a name="to-install-vba-with-the-2007-microsoft-office-system"></a>VBA 'Yı 2007 Microsoft Office sistemine yüklemek için

1. Denetim Masası 'nda **Program Ekle/** Kaldır veya **Programlar ve Özellikler**' i çalıştırın.

2. **Yüklü olan programlar** listesinden Office ' i seçin.

3. **Değiştir**'i tıklatın.

4. **Özellik Ekle veya Kaldır**' ı seçin ve ardından **devam**' a tıklayın.

5. **Uygulamaların gelişmiş özelleştirmesini Seç**' i seçin ve ardından **İleri**' ye tıklayın.

6. **Uygulamalar ve araçlar için güncelleştirme seçeneklerini belirleyin** listesinde **Office Paylaşılan Özellikler** ' i genişletin.

7. **Visual Basic for Applications**' nin yanındaki açılan menüyü açın ve sonra Bilgisayarımdan **Çalıştır**' a tıklayın.

8.           **Devam**'a tıklayın.

9. **Kapat**'ı tıklatın.

## <a name="to-repair-your-installation-of-office"></a>Office yüklemenizi onarmak için

1. Denetim Masası 'nda **Program Ekle/** Kaldır veya **Programlar ve Özellikler**' i çalıştırın.

2. **Yüklü olan programlar** listesinden Office sürümünüzü seçin.

3. **Değiştir**'i tıklatın.

4. **Yeniden yükle veya Onar**' ı seçin ve ardından **İleri**' ye tıklayın.

5. **Office yüklememdeki hataları Algıla ve Onar**' ı seçin ve ardından **yükleme**' ye tıklayın.

## <a name="see-also"></a>Ayrıca bkz.
- [Güvenli Office çözümleri](../vsto/securing-office-solutions.md)
