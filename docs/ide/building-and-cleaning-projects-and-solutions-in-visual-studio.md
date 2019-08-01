---
title: Projeleri ve Çözümleri Oluşturma ve Temizleme
ms.date: 11/04/2016
ms.technology: vs-ide-compile
ms.topic: conceptual
f1_keywords:
- VS.BuildProjectPicker
- vs.batchbuild
helpviewer_keywords:
- Clean Solution command
- builds [Visual Studio], managing
- solution build configurations, starting
- Build Solution command
- project build configurations, starting
- build configurations, starting
- project build configurations, dependencies
- Rebuild Solution command
- solution build configurations, build order
- builds [Visual Studio], preparing
ms.assetid: 710891fd-379e-42c2-a84b-44a7af694ca0
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b8676ad9dc1a3b245242687e2ea56148b83b8d56
ms.sourcegitcommit: 59e5758036223ee866f3de5e3c0ab2b6dbae97b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/23/2019
ms.locfileid: "68416427"
---
# <a name="build-and-clean-projects-and-solutions-in-visual-studio"></a>Visual Studio 'da projeler ve çözümler oluşturma ve Temizleme

Bu konudaki yordamları kullanarak, derleme, yeniden veya tüm veya bazı projeler veya bir çözümde proje öğeleri temizleyin. Adım adım bir öğretici için bkz [. İzlenecek yol: Uygulama](../ide/walkthrough-building-an-application.md)oluşturma.

> [!NOTE]
> Bu konu, Windows üzerinde Visual Studio için geçerlidir. Mac için Visual Studio için bkz. [Mac için Visual Studio içindeki proje ve çözümleri oluşturma ve Temizleme](/visualstudio/mac/building-and-cleaning-projects-and-solutions).

> [!NOTE]
> Visual Studio sürümünüz kullanıcı Arabiriminde, bu konuda, etkin ayarlarınıza bağlı olarak açıklanmıştır öğesinden farklı olabilir. Ayarlarınızı, örneğin değiştirileceğini **genel** veya **Visual C++** ayarları seçebilirsiniz **Araçları** > **içeri ve dışarı aktarma ayarları**ve ardından **tüm ayarları Sıfırla**.

## <a name="to-build-rebuild-or-clean-an-entire-solution"></a>Derleme, yeniden oluşturmanız veya bütün bir çözüm Temizle

1. İçinde **Çözüm Gezgini**, seçin veya çözümü açın.

2. Menü çubuğunda, **derleme**ve ardından aşağıdaki komutlardan birini seçin:

    - Seçin **derleme** veya **Çözümü Derle** yalnızca bu dosyaları ve en son derlemeden sonra değiştirilen bileşenleri proje derlemek için.

        > [!NOTE]
        > **Derleme** komut olur **Çözümü Derle** ne zaman bir çözüm birden fazla proje içerir.

    - Seçin **çözümü yeniden derle** "çözümü Temizle" ve sonra tüm proje dosyaları ve bileşenleri oluşturun.

    - Seçin **çözümü Temizle** tüm ara ve Çıkış dosyalarını silmek için. Yalnızca proje ve bileşen dosyalarını sol yeni örneklerini Ara ve Çıkış dosyalarını sonra oluşturulabilir.

## <a name="to-build-or-rebuild-a-single-project"></a>Derleme veya tek projeyi yeniden derleyin

1. İçinde **Çözüm Gezgini**, seçin veya projeyi açın.

2. Menü çubuğunda **Oluştur**' u seçin ve sonra *ProjectName* **Derle** veya *ProjectName*öğesini **yeniden oluştur** ' u seçin.

    - Yalnızca en son derlemeden bu yana değiştirilen proje bileşenlerini derlemek için **Build** *ProjectName* öğesini seçin.

    - Projeyi "temizlemek" için *ProjectName* **yeniden derle** öğesini seçin ve proje dosyalarını ve tüm proje bileşenlerini derleyin.

## <a name="to-build-only-the-startup-project-and-its-dependencies"></a>Başlangıç projesi ve bağımlılıklarını oluşturma

1. Menü çubuğunda, **Araçları** > **seçenekleri**.

2. İçinde **seçenekleri** iletişim kutusunda **projeler ve çözümler** düğümünü seçip **derleme ve çalıştırma** sayfası.

     **Projeleri ve çözümleri** >  oluşturmaveçalıştırmaseçenekleri > iletişim kutusu açılır.

3. Seçin **çalıştırıldığında yalnızca başlangıç projelerini ve bağımlılıkları derle** onay kutusu.

     Bu onay kutusu işaretli olduğunda, aşağıdaki adımlardan birini gerçekleştirdiğinizde yalnızca geçerli başlangıç projesi ve bağımlılıklarını oluşturulur:

    - Menü çubuğunda **Hata Ayıkla** > **Başlat** (**F5**) öğesini seçin.

    - Menü çubuğunda Build**Build Solution** ( > **CTRL**+**Shift**+**B**) **öğesini seçin.**

    Bu onay kutusunun işareti kaldırıldığında, önceki komutlardan birini çalıştırdığınızda tüm projeler, bağımlılıklarını ve çözüm dosyaları oluşturulur. Varsayılan olarak, bu onay kutusu işaretli değildir.

## <a name="to-build-only-the-selected-visual-c-project"></a>Yalnızca seçilen Visual C++ projesi oluşturmak için

Bir [!INCLUDE[vcprvc](../code-quality/includes/vcprvc_md.md)] proje seçin ve ardından menü çubuğunda**yalnızca proje** **Oluştur** > ' u ve aşağıdaki komutlardan birini seçin:

- **Yalnızca derleme** *ProjectName*

- **Yalnızca yeniden** *ProjectName*

- **Temizleme yalnızca** *ProjectName*

- **Yalnızca bağlantı** *ProjectName*

Bu komutlar yalnızca uygulanacak [!INCLUDE[vcprvc](../code-quality/includes/vcprvc_md.md)] oluşturma, yeniden oluşturma, temizlenmesi veya herhangi bir proje bağımlılıkları veya çözüm dosyaları bağlama olmadan seçtiğiniz proje. Sürümünüze bağlı [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], **yalnızca proje** alt daha fazla komut içerebilir.

## <a name="to-compile-multiple-c-project-items"></a>Birden çok C++ proje öğeleri derlemek için

İçinde **Çözüm Gezgini**, sahip birden çok dosya olabilir derlenmiş eylemleri seçin bu dosyalardan biri için kısayol menüsünü açın ve ardından **derleme**.

Dosyaları bağımlılıkları varsa, bağımlılık sırasına dosyaları derlenir. Dosyalar derlerken kullanılamayan bir ön derlenmiş üstbilgi gerektiriyorsa, derleme işlemi başarısız olur. Derleme işlemi, geçerli etkin çözüm yapılandırmasını kullanır.

## <a name="to-stop-a-build"></a>Bir derlemeyi durdurmak için

Aşağıdaki adımlardan birini gerçekleştirin:

- Menü çubuğunda, **derleme** > **iptali**' ni seçin.

- **CTRL**+**Kes**'e basın.

## <a name="see-also"></a>Ayrıca bkz.

- [Nasıl yapılır: Derleme günlüğü dosyalarını görüntüleme, kaydetme ve yapılandırma](../ide/how-to-view-save-and-configure-build-log-files.md)
- [Derleme günlükleri alma](../msbuild/obtaining-build-logs-with-msbuild.md)
- [Derleme ve oluşturma](../ide/compiling-and-building-in-visual-studio.md)
- [Yapı yapılandırmalarını anlama](../ide/understanding-build-configurations.md)
- [Nasıl yapılır: Hata ayıklama ve yayın yapılandırmasını ayarla](../debugger/how-to-set-debug-and-release-configurations.md)
- [C/C++ oluşturma başvurusu](/cpp/build/reference/c-cpp-building-reference)
- [Devenv komut satırı anahtarları](../ide/reference/devenv-command-line-switches.md)
- [Projeler ve çözümler](../ide/solutions-and-projects-in-visual-studio.md)
- [Projeleri ve çözümleri oluşturma ve Temizleme (Mac için Visual Studio)](/visualstudio/mac/building-and-cleaning-projects-and-solutions)