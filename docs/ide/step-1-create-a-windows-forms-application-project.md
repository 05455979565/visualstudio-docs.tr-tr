---
title: '1\. Adım: Windows Forms Uygulaması projesi oluşturma'
ms.date: 08/30/2019
ms.assetid: 16ac2422-e720-4e3a-b511-bc2a54201a86
ms.topic: tutorial
ms.prod: visual-studio-windows
ms.technology: vs-ide-general
ms.devlang:
- csharp
- vb
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 65339eabcffdf0f333036442ea8473ecf8c8f06e
ms.sourcegitcommit: 4dfe098ac0df294aad63e6b384d6575980798ca3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/11/2019
ms.locfileid: "70888016"
---
# <a name="step-1-create-a-windows-forms-app-project"></a>1\. Adım: Windows Forms Uygulaması projesi oluşturma

Bir resim görüntüleyici oluşturduğunuzda, ilk adım Windows Forms bir uygulama projesi oluşturmaktır.

::: moniker range="vs-2017"

## <a name="open-visual-studio-2017"></a>Visual Studio 2017 'yi açın

1. Menü çubuğunda, **dosya** > **yeni** > **proje**. İletişim kutusu aşağıdaki ekran görüntüsüne benzer görünmelidir.

     ![Yeni proje iletişim kutusu](../ide/media/newprojectdialogcallouts.png)<br/>***Yeni proje*** *iletişim kutusu*

2. **Yeni proje** iletişim kutusunun sol tarafında, **görsel C#**  veya **Visual Basic**' yi seçin ve ardından **Windows Masaüstü**' nu seçin.

3. Proje şablonları listesinde **Windows Forms uygulama (.NET Framework)** öğesini seçin. Yeni formu *PictureViewer olarak adlandırın*olarak adlandırın ve ardından **Tamam** düğmesini seçin.

    >[!NOTE]
    >**Windows Forms App (.NET Framework)** şablonunu görmüyorsanız, **.net masaüstü geliştirme** iş yükünü yüklemek için Visual Studio yükleyicisi kullanın.<br/><br/>![Visual Studio Yükleyicisi .NET masaüstü geliştirme iş yükü](../ide/media/dot-net-desktop-dev-workload.png)<br/><br/> Daha fazla bilgi için bkz. [Visual Studio 'Yu Install](../install/install-visual-studio.md) sayfası.

::: moniker-end

::: moniker range="vs-2019"

## <a name="open-visual-studio-2019"></a>Visual Studio 2019 'yi açın

1. Başlangıç penceresinde **Yeni proje oluştur**' u seçin.

   ![' Yeni proje oluştur ' penceresini görüntüleyin](../get-started/media/vs-2019/create-new-project-dark-theme.png)

1. **Yeni proje oluştur** penceresinde, arama kutusuna *Windows Forms* girin veya yazın. Ardından, **Proje türü** listesinden **Masaüstü** ' ni seçin.

   **Proje türü** filtresini uyguladıktan sonra, C# veya Visual Basic için **Windows Forms App (.NET Framework)** şablonunu seçin ve ardından **İleri**' yi seçin.

   ![Windows Forms uygulaması C# için şablonu seçin (.NET Framework)](./media/create-new-project-search-winforms-filtered.png)

   > [!NOTE]
   > **Windows Forms App (.NET Framework)** şablonunu görmüyorsanız, **Yeni proje oluştur** penceresinden yükleyebilirsiniz. **Aradığınızı bulamıyor musunuz?** iletisi için **daha fazla araç ve özellik yüklemeyi** seçin bağlantısına tıklayın.
   >
   > ![' Yeni proje oluştur ' penceresindeki ' daha fazla araç ve özellik yüklemesi ' ' ne aradığınızı bulma ' iletisi bağlantısı](../get-started/media/vs-2019/not-finding-what-looking-for.png)
   >
   > Sonra, Visual Studio Yükleyicisi **.net masaüstü geliştirme** Iş yükünü seçin.
   >
   > ![Visual Studio Yükleyicisi'nde .NET core iş yükü](../ide/media/install-dot-net-desktop-env.png)
   >
   > Bundan sonra Visual Studio Yükleyicisi **Değiştir** düğmesini seçin. İşinizi kaydetmeniz istenebilir; Öyleyse, bunu yapın. Sonra, iş yükünü yüklemek için **devam** ' ı seçin.

1. **Yeni projeyi yapılandırın** penceresinde, **Proje adı** kutusuna *PictureViewer olarak adlandırın* yazın veya girin. Ardından **Oluştur**' u seçin.

::: moniker-end

Visual Studio, uygulamanız için bir çözüm oluşturur. Bir çözüm, uygulamanız için gereken tüm proje ve dosyalar için bir kapsayıcı görevi görür. Bu terimler, Bu öğreticinin ilerleyen kısımlarında daha ayrıntılı olarak açıklanacaktır.

## <a name="about-the-windows-forms-app-project"></a>Windows Forms uygulama projesi hakkında

1. Geliştirme ortamı üç pencere içerir: Ana pencere, **Çözüm Gezgini**ve **Özellikler** penceresi.

     Bu pencerelerin herhangi biri eksikse, varsayılan pencere yerleşimini geri yükleyebilirsiniz. Menü çubuğunda **pencere** > **sıfırlama pencere düzeni**' ni seçin.

     Ayrıca, menü komutlarını kullanarak da Windows görüntüleyebilirsiniz. Menü çubuğunda, **Görünüm** > **Özellikleri penceresi** ' ni veya **Çözüm Gezgini**' ı seçin.

     Başka herhangi bir pencere açıksa, sağ üst köşelerindeki **Kapat** (x) düğmesini seçerek onları kapatın.

    ::: moniker range="vs-2017"

    * **Ana pencere** Bu pencerede, yaptığınız gibi, formlarla çalışma ve kod düzenlemeyle ilgili birçok iş olacaktır. Pencere, **form düzenleyicisinde**bir form gösterir. Pencerenin üst kısmında, **Başlangıç sayfası** sekmesi ve **Form1.cs [Design]** sekmesi görüntülenir. (Visual Basic, sekme adı *. cs*yerine *. vb* ile biter.)

    ::: moniker-end

    ::: moniker range=">=vs-2019"

    * **Ana pencere** Bu pencerede, yaptığınız gibi, formlarla çalışma ve kod düzenlemeyle ilgili birçok iş olacaktır. Pencere, **form düzenleyicisinde**bir form gösterir.

    ::: moniker-end

    * **Çözüm Gezgini penceresi** Bu pencerede, çözümünüzdeki tüm öğeleri görüntüleyebilir ve buna gidebilirsiniz.

    Bir dosya seçerseniz, **Özellikler** penceresinin içeriği değişir. Bir kod dosyası açarsanız ( C# ve. *vb* içinde *. cs* ile biten) Visual Basic), kod dosyası veya kod dosyası Tasarımcısı görüntülenir. Tasarımcı, üzerinde düğme ve liste gibi denetimler ekleyebileceğiniz görsel bir yüzeydir. Visual Studio Forms için tasarımcı **Windows Form Tasarımcısı**olarak adlandırılır.

    * **Özellikler penceresi** Bu pencerede, diğer pencereler üzerinde seçtiğiniz öğelerin özelliklerini değiştirebilirsiniz. Örneğin, Form1 ' i seçerseniz, **Text** özelliğini ayarlayarak başlığını değiştirebilir ve **BackColor** özelliğini ayarlayarak arka plan rengini değiştirebilirsiniz.

      > [!NOTE]
      > **Çözüm Gezgini** en üstteki satır, Visual Studio 'nun sizin için bir çözüm oluşturduğu anlamına gelen **' PictureViewer olarak adlandırın ' (1 proje) çözümünü**gösterir. Bir çözüm birden fazla proje içerebilir, ancak şimdilik yalnızca bir proje içeren çözümlerle çalışırsınız.

1. Menü çubuğunda **Dosya** > **Tümünü Kaydet**' i seçin.

     Alternatif olarak, aşağıdaki görüntüde gösterildiği gibi, araç çubuğunda **Tümünü Kaydet** düğmesini seçin.

     ![Tümünü Kaydet araç çubuğu düğmesi](../ide/media/express_iconsaveall.png)<br/>
     ***Tümünü Kaydet*** *araç çubuğu düğmesi*

     Visual Studio, klasör adı ve proje adını otomatik olarak doldurur ve projeyi projeler klasörünüze kaydeder.

## <a name="next-steps"></a>Sonraki adımlar

* Sonraki öğretici adımına gitmek için bkz  **[. 2. Adım: ](../ide/step-2-run-your-program.md)Uygulamanızı**çalıştırın.

* Genel bakış konusuna dönmek için bkz [. öğretici 1: Bir resim görüntüleyici](../ide/tutorial-1-create-a-picture-viewer.md)oluşturun.

## <a name="see-also"></a>Ayrıca bkz.

* [Öğretici 2: Süreli matematik testi oluşturma](tutorial-2-create-a-timed-math-quiz.md)
* [Öğretici 3: Eşleşen bir oyun oluşturun](tutorial-3-create-a-matching-game.md)
