---
title: Yayımlama sayfası, proje Tasarımcısı | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- Microsoft.VisualStudio.Publish.ClickOnceProvider.Dialog.PropertyPage
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- Project Designer, Publish page
- Publish page in Project Designer
ms.assetid: 153527c6-8b95-4003-8e8e-03a489d0a629
caps.latest.revision: 37
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 391e6c457dd09afa154c46cbc8644f028052cb32
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72665700"
---
# <a name="publish-page-project-designer"></a>Yayın Sayfası, Proje Tasarımcısı
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

**Proje Tasarımcısı** ' nın **Yayımla** sayfası ClickOnce dağıtımı için özellikleri yapılandırmak üzere kullanılır.

 **Yayımla** sayfasına erişmek için **Çözüm Gezgini**' de bir proje düğümü seçin ve ardından **Proje** menüsünde **Özellikler**' e tıklayın. **Proje Tasarımcısı** göründüğünde, **Yayımla** sekmesine tıklayın.

> [!NOTE]
> Burada açıklanan bazı ClickOnce özellikleri, **derleme** menüsünde veya bu sayfadaki **publishwizard** düğmesine tıklanarak bulunan **publishwizard**'da da ayarlanabilir.

## <a name="uielement-list"></a>UIElement Listesi
 **Yayımlama klasörü konumu** Uygulamanın yayımlandığı konumu belirtir. Bir sürücü yolu (`C:\deploy\myapplication`), bir dosya paylaşma (`\\server\myapplication`), bir FTP sunucusu (`ftp://ftp.microsoft.com/myapplication`) veya bir Web sitesi (`http://www.microsoft.com/myapplication`) olabilir. Göz at ( **...** ) düğmesinin çalışması Için **Yayımlama konumu** kutusunda metnin mevcut olması gerektiğini unutmayın.

 Varsayılan olarak, yayımlama konumu IIS yüklüyse `http://localhost/<projectname>/` veya IIS yüklü değilse `publish\` dizinidir. Bilgisayarınızda Windows Vista çalışıyorsa, IIS 'nin yüklü olup olmamasından bağımsız olarak, varsayılan olarak her zaman `publish\` dizinidir.

 **Yükleme klasörü URL 'si** Seçim. Kullanıcıların uygulamayı yüklemek için gideceği bir Web sitesini belirtir. Bu, yalnızca **yayımlama konumundan**farklı olduğunda (örneğin, uygulama bir hazırlama sunucusuna yayımlandığında) gereklidir.

 **Modu ve ayarları yükler** Uygulamanın doğrudan **yayımlama konumundan** çalıştırılıp çalıştırılmadığını ( **uygulama yalnızca çevrimiçi kullanılabilir** olduğunda) veya yüklenip buradan **Başlat** menüsüne ve **Program Ekle/Kaldır** öğesine eklendiğini belirler. **Denetim Masası** ( **uygulama çevrimdışı kullanılabilir olduğunda da** seçilidir).

 WPF Web tarayıcı uygulamaları için **uygulama çevrimdışı olarak kullanılabilir** , çünkü bu uygulamalar yalnızca çevrimiçi kullanılabilir.

 **Uygulama dosyaları** Her bir dosyanın nasıl ve nerede yükleneceğini belirlemek için kullanılan [uygulama dosyaları Iletişim kutusunu](https://msdn.microsoft.com/b06dff3a-b87a-4caf-996b-7a4acf8137a8)açar.

 **Önkoşullar** Uygulamayla birlikte yüklenecek .NET Framework gibi Önkoşul bileşenlerini belirtmek için kullanılan [Önkoşullar Iletişim kutusunu](../../ide/reference/prerequisites-dialog-box.md)açar.

 **Güncelleştirmeler** Uygulamanın güncelleştirme davranışını belirtmek için kullanılan [uygulama güncelleştirmeleri Iletişim kutusunu](https://msdn.microsoft.com/8eca8743-8e68-4d04-bfd5-4dc0a9b2934f)açar. **Uygulama yalnızca çevrimiçi kullanılabilir** olduğunda kullanılamaz.

 **Seçenekler** Diğer gelişmiş yayımlama seçeneklerini belirtmek için kullanılan [Yayımla Seçenekleri Iletişim kutusunu](https://msdn.microsoft.com/fd9baa1b-7311-4f9e-8ffb-ae50cf110592)açar.

 **Yayımlama sürümü** Uygulama için yayımlama sürüm numarasını ayarlar; sürüm numarası değiştirildiğinde, uygulama bir güncelleştirme olarak yayımlanır. Yayımla sürümünün (**ana**, **İkincil**, **derleme**, **Düzeltme**) her bölümü, <xref:System.Version> izin verilen en büyük 65355 (<xref:System.UInt16.MaxValue>) değerine sahip olabilir.

 ClickOnce kullanarak bir uygulamanın birden fazla sürümünü yüklediğinizde yükleme, uygulamanın önceki sürümlerini belirttiğiniz Yayımla konumundaki arşiv adlı bir klasöre taşır. Önceki sürümlerin bu şekilde arşivlenmesi, yükleme dizinini önceki sürümden klasörlerin temizlenmesini önler.

 **Her yayınla birlikte düzeltmeyi otomatik olarak artır** Seçim. Bu seçenek belirlendiğinde (varsayılan), yayımlama sürümü numarasının **Düzeltme** bölümü, uygulamanın her yayımlanışında bir artırılır. Bu, uygulamanın bir güncelleştirme olarak yayımlanmasına neden olur.

 **Yayımlama Sihirbazı** [Yayımla sihirbazını](https://msdn.microsoft.com/fc6abebd-13d6-48e4-a567-fbc52dad0872)açar. Yayımla sihirbazının tamamlanması, **derleme** menüsündeki **Yayımla** komutunu çalıştırmasıyla aynı etkiye sahiptir.

 **Şimdi Yayımla** Geçerli ayarları kullanarak uygulamayı yayımlar. **Publishwizard**'daki **son** düğmesine eşittir.

## <a name="see-also"></a>Ayrıca Bkz.
 [ClickOnce uygulamalarını yayımlama](../../deployment/publishing-clickonce-applications.md) [nasıl yapılır: yayımlama sihirbazını kullanarak ClickOnce uygulaması](../../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md) yayımlama [nasıl yapılır: Visual Studio 'Nun dosyaları nereye kopyaladığını belirtme](../../deployment/how-to-specify-where-visual-studio-copies-the-files.md) nasıl yapılır [: son kullanıcıların nereden yükleneceğine konum belirtme](../../deployment/how-to-specify-the-location-where-end-users-will-install-from.md) [ : teknik destek için bir bağlantı belirtin](../../deployment/how-to-specify-a-link-for-technical-support.md) [nasıl yapılır: ClickOnce Çevrimdışı veya çevrimiçi yükleme modunu belirtme](../../deployment/how-to-specify-the-clickonce-offline-or-online-install-mode.md) [nasıl yapılır: otomatik başlatmayı etkinleştirme CD yüklemeleri için autostart](../../deployment/how-to-enable-autostart-for-cd-installations.md) 'ı ayarlama nasıl yapılır: [ClickOnce yayımlama sürümü](../../deployment/how-to-set-the-clickonce-publish-version.md) [nasıl yapılır: otomatik olarak artırma ClickOnce yayımlama sürümü](../../deployment/how-to-automatically-increment-the-clickonce-publish-version.md) [nasıl yapılır: ClickOnce tarafından hangi dosyaların yayımlandığını belirtme](../../deployment/how-to-specify-which-files-are-published-by-clickonce.md) [nasıl yapılır](../../deployment/how-to-install-prerequisites-with-a-clickonce-application.md) : ClickOnce uygulamasıyla önkoşulları yüklemek nasıl yapılır: [ClickOnce uygulaması için güncelleştirmeleri yönetme](../../deployment/how-to-manage-updates-for-a-clickonce-application.md) [nasıl yapılır: ClickOnce uygulaması için dil Yayımla](../../deployment/how-to-change-the-publish-language-for-a-clickonce-application.md) [nasıl yapılır: ClickOnce uygulaması Için Başlat menüsü adı belirtme](../../deployment/how-to-specify-a-start-menu-name-for-a-clickonce-application.md) [nasıl yapılır: ClickOnce uygulaması Için bir yayımlama sayfası belirtme](../../deployment/how-to-specify-a-publish-page-for-a-clickonce-application.md) [ClickOnce güvenliği ve dağıtımı](../../deployment/clickonce-security-and-deployment.md)
