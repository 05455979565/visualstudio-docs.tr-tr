---
title: 'Öğretici: Visual Basic kodu hatalarını ayıklama'
description: Kodu adımlayın Visual Studio hata ayıklayıcısını başlatın ve veri İnceleme hakkında bilgi edinin.
ms.custom: debug-experiment, seodec18, get-started
ms.date: 11/27/2018
ms.technology: vs-ide-debug
ms.topic: tutorial
dev_langs:
- CSharp
helpviewer_keywords:
- debugger
ms.assetid: 62734c0d-a75a-4576-8f73-0e97c19280e1
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: cb6763ef598cb700c7fb7b3d40a3890629c2a058
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/17/2019
ms.locfileid: "59667566"
---
# <a name="tutorial-learn-to-debug-visual-basic-code-using-visual-studio"></a>Öğretici: Visual Studio kullanarak Visual Basic kod hata ayıklamayı öğrenin

Bu makalede, Visual Studio hata ayıklayıcı adım adım kılavuzda özelliklerini tanıtır. Hata ayıklayıcısı özellikleri daha üst düzey bir görünümünü istiyorsanız bkz [hata ayıklayıcıya ilk bakış](../../debugger/debugger-feature-tour.md). Olduğunda, *uygulamanızda hata ayıklama*, hata ayıklayıcısı ekli, uygulamanızın çalıştığını genellikle anlamına gelir. Bunu yaptığınızda, hata ayıklayıcı, kodunuzun ne yaptığını görmek için birçok yol sağlar. çalışırken. Kodunuzda adım adım ve değişkenlerinde depolanan değerleri bakmak, gözcüler ayarlayabilirsiniz değerleri değiştiğinde görmek için değişkenlerini kodunuzun yürütme yolunu inceleyin, bir dal kod çalıştırma, vb. olup olmadığını. Bu, kodda hata ayıklamak için girişimde ilk kez ise, okumak isteyebilirsiniz [yeni başlayanlar için hata ayıklama](../../debugger/debugging-absolute-beginners.md) bu makalede geçmeden önce.

Bu öğreticide şunları yapacaksınız:

> [!div class="checklist"]
> * Hata ayıklayıcıyı başlatın ve kesme noktaları isabet.
> * Hata ayıklayıcı kodda adım adım için komutları öğrenin
> * Veri ipuçları ve hata ayıklayıcı pencereleri değişkenler inceleyin
> * Çağrı yığınını inceleyin

## <a name="prerequisites"></a>Önkoşullar

::: moniker range=">=vs-2019"

Visual Studio 2019 yüklü olması gerekir ve **.NET Masaüstü geliştirmesinden** iş yükü.

::: moniker-end
::: moniker range="vs-2017"

Visual Studio 2017 yüklü olması gerekir ve **.NET Masaüstü geliştirmesinden** iş yükü.

::: moniker-end

::: moniker range="vs-2017"

Visual Studio henüz yüklemediyseniz, Git [Visual Studio indirmeleri](https://visualstudio.microsoft.com/vs/older-downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=vs+2017+download) ücretsiz yüklemek için sayfa.

::: moniker-end

::: moniker range="vs-2019"

Visual Studio henüz yüklemediyseniz, Git [Visual Studio indirmeleri](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) ücretsiz yüklemek için sayfa.

::: moniker-end

İş yükünü yükleyin, ancak Visual Studio zaten gerekiyorsa, Git **Araçları** > **araçları ve özellikleri Al...** , Visual Studio yükleyicisi açılır. Visual Studio Yükleyicisi'ni başlatır. Seçin **.NET masaüstü geliştirme** iş yükü, ardından **Değiştir**.

## <a name="create-a-project"></a>Proje oluşturma

1. Visual Studio'yu açın.

    ::: moniker range=">=vs-2019"
    Tuşuna **Esc** başlangıç penceresini kapatın. Tür **Ctrl + Q** arama kutusunu açmak için şunu yazın **visual basic**, seçin **şablonları**, ardından **oluştur yeni konsol uygulaması (.NET Framework) projesi**. Görüntülenen iletişim kutusunda gibi bir ad yazın **get-başlatıldı-hata ayıklama**ve ardından **Oluştur**.
    ::: moniker-end
    ::: moniker range="vs-2017"
    Üstteki menü çubuğundan seçin **dosya** > **yeni** > **proje**. Sol bölmesinde **yeni proje** iletişim kutusunun **Visual Basic**, seçin **Windows Masaüstü**seçip Ortadaki bölmeden **konsol uygulaması (.NET Framework)**. Gibi bir ad yazın **get-başlatıldı-hata ayıklama** tıklatıp **Tamam**.
    ::: moniker-end

    Görmüyorsanız **konsol uygulaması (.NET Framework)** proje şablonu, Git **Araçları** > **araçları ve özellikleri Al...** , Visual Studio yükleyicisi açılır. Seçin **.NET masaüstü geliştirme** iş yükü, ardından **Değiştir**.

    Visual Studio projesi oluşturur.

1. İçinde *Module1.vb*, aşağıdaki kodu değiştirin

    ```vb
    Module Module1

        Sub Main()
        End Sub

    End Module
    ```

    Bu kod ile:

    ```vb
    Imports System
    Imports System.Collections.Generic

    Public Class Shape

      ' A few example members
        Public Property X As Integer
            Get
                Return X
            End Get
            Set
            End Set
        End Property

        Public Property Y As Integer
            Get
                Return Y
            End Get
            Set
            End Set
        End Property

        Public Property Height As Integer
            Get
                Return Height
            End Get
            Set
            End Set
        End Property

        Public Property Width As Integer
            Get
                Return Width
            End Get
            Set
            End Set
        End Property

        ' Virtual method
        Public Overridable Sub Draw()
            Console.WriteLine("Performing base class drawing tasks")
        End Sub
    End Class

    Public Class Circle
        Inherits Shape

        Public Overrides Sub Draw()
            ' Code to draw a circle...
            Console.WriteLine("Drawing a circle")
            MyBase.Draw()
        End Sub
    End Class

    Public Class Rectangle
        Inherits Shape

        Public Overrides Sub Draw()
            ' Code to draw a rectangle...
            Console.WriteLine("Drawing a rectangle")
            MyBase.Draw()
        End Sub
    End Class

    Public Class Triangle
        Inherits Shape

        Public Overrides Sub Draw()
            ' Code to draw a triangle...
            Console.WriteLine("Drawing a trangle")
            MyBase.Draw()
        End Sub
    End Class

    Module Module1

        Sub Main(ByVal args() As String)

            Dim shapes = New List(Of Shape) From
            {
                New Rectangle,
                New Triangle,
                New Circle
            }

            For Each shape In shapes
                shape.Draw()
            Next
            ' Keep the console open in debug mode.
            Console.WriteLine("Press any key to exit.")
            Console.ReadKey()

        End Sub

    End Module

    ' Output:
    '    Drawing a rectangle
    '    Performing base class drawing tasks
    '    Drawing a triangle
    '    Performing base class drawing tasks
    '    Drawing a circle
    '    Performing base class drawing tasks
    ```

## <a name="start-the-debugger"></a>Hata ayıklayıcıyı başlatın!

1. Tuşuna **F5** (**hata ayıklama > hata ayıklamayı Başlat**) veya **hata ayıklamayı Başlat** düğmesi ![hata ayıklamayı Başlat](../../debugger/media/dbg-tour-start-debugging.png "hata ayıklamayı Başlat ") hata ayıklama araç çubuğu.

     **F5** başladığında hata ayıklayıcının uygulamayla uygulamaya bağlı işlem ancak biz kodunu incelemek için özel bir şey yapmadınız hemen. Bu nedenle yalnızca uygulamayı yükler ve konsol çıktısı görürsünüz.

    ```cmd
    Drawing a rectangle
    Performing base class drawing tasks
    Drawing a triangle
    Performing base class drawing tasks
    Drawing a circle
    Performing base class drawing tasks
    ```

     Bu öğreticide, biz hata ayıklayıcıyı kullanarak bu uygulamaya daha yakından göz atın ve hata ayıklayıcı göz özelliklerini elde etmek.

2. Kırmızı Durdur tuşuna basarak hata ayıklayıcıyı ![hata ayıklamayı Durdur](../../debugger/media/dbg-tour-stop-debugging.png "hata ayıklamayı Durdur") düğmesi.

## <a name="set-a-breakpoint-and-start-the-debugger"></a>Bir kesme noktası ayarlayın ve hata ayıklayıcıyı başlatın

1. İçinde `For Each` , döngü `Main` işlev, aşağıdaki kod satırının sol kenar boşluğunu tıklayarak kesme noktası ayarlayın:

    `shape.Draw()`

    Kesme noktasının ayarlandığı kırmızı bir daire görünür.

    ![Bir kesme noktası ayarlayın](../visual-basic/media/get-started-set-breakpoint-vb.png)

    Kesme noktaları güvenilir hata ayıklama en temel hem de temel özelliğidir. Bir kesme noktası değişkenlerin değerleri veya bellek davranışını göz olabilmesi için Visual Studio çalışan kodunuzu nereye askıya almanız ya da bir dal kod getting run olup olmadığını gösterir.

2. Tuşuna **F5** veya **hata ayıklamayı Başlat** düğmesi ![hata ayıklamayı Başlat](../../debugger/media/dbg-tour-start-debugging.png "hata ayıklamayı Başlat"), uygulama başlatılır ve hata ayıklayıcı çalışan satırına kodu kesme noktası ayarladığınız yerdir.

    ![Bir kesme noktası isabet](../visual-basic/media/get-started-hit-breakpoint-vb.png)

    Sarı ok, aynı zamanda aynı noktayı (Bu bildirimi henüz çalıştırılmadı) uygulama yürütmeyi askıya alır, hata ayıklayıcı durduruldu, deyimi temsil eder.

     Uygulama henüz çalışmıyorsa **F5** hata ayıklayıcıyı başlatır ve ilk kesme noktasında durur. Aksi takdirde, **F5** uygulamayı sonraki kesme noktasına kadar çalışmaya devam eder.

    Kod satırının veya ayrıntılı olarak incelemek istediğiniz kod bölümünün bildiğiniz durumlarda kesme noktaları yararlı bir özelliktir.

## <a name="navigate-code-in-the-debugger-using-step-commands"></a>Kod adım komutları kullanarak hata ayıklayıcısında gidin

Almak için en iyi yolu olduğundan bu çoğunlukla, klavye kısayollarını Burada, kullandığımız hata ayıklayıcı (komutları parantez içinde gösterilen eşdeğer komutları menüsü gibi) uygulamanız çalıştırma sırasında hızlı.

1. İçinde duraklatıldığı sırada `shape.Draw` yöntem çağrısı `Main` işlev, basın **F11** (veya tercih **hata ayıklama > içine adımla**) için koda ilerlemek için `Rectangle` sınıfı.

     ![İçine adımla kodu F11 kullanın](../visual-basic/media/get-started-f11-vb.png "F11 adımla")

     F11 olan **içine adımla** komut ve aynı anda uygulama yürütme bir deyim ilerler. F11 çoğu ayrıntılı yürütme akışı incelemek için iyi bir yoludur. (Daha hızlı kod boyunca taşımak için başka seçenekleriniz de gösteriyoruz.) Varsayılan olarak, kullanıcı dışı kod üzerinde hata ayıklayıcı atlar (daha ayrıntılı bilgi isterseniz bkz [yalnızca kendi kodum](../../debugger/just-my-code.md)).

2. Basın **F10** (veya tercih **hata ayıklama > Step Over**) hata ayıklayıcı birkaç kez durur kadar `MyBase.Draw` yöntem çağrısının yazıp ENTER tuşuna **F10** bir kez daha.

     ![Step Over kodu F10 kullanın](../visual-basic/media/get-started-step-over-vb.png "F10 adımla")

     Hata ayıklayıcı içine girmez şu bildirim `Draw` temel sınıf yöntemini (`Shape`). **F10** işlevleri veya yöntemleri (kod hala çalışır), uygulama kodunuzda içine Adımlama olmadan, hata ayıklayıcı ilerler. Tuşuna basarak **F10** üzerinde `MyBase.Draw` yöntem çağrısının (yerine **F11**), biz uygulama kodunu üzerinden atlandı `MyBase.Draw` (biz İlgilenmiyor, şu anda hangi olabilir).

## <a name="navigate-code-using-run-to-click"></a>Tıkla Çalıştır'ı kullanarak kod gidin

1. Kod Düzenleyicisi'nde, ekranı aşağı kaydırın ve üzerine `Console.WriteLine` yönteminde `Triangle` sınıfı yeşil kadar **tıklanan satıra kadar Çalıştır** düğmesi ![tıklanan satıra kadar Çalıştır](../../debugger/media/dbg-tour-run-to-click.png "RunToClick")soldaki bölmede görünür. "Yürütmeyi buraya Çalıştır" düğmesi için araç ipucu gösterilmektedir.

     ![Tıkla Çalıştır kullanın özellik](../visual-basic/media/get-started-run-to-click-vb.png "tıklanan satıra kadar Çalıştır")

   > [!NOTE]
   > **Tıklanan satıra kadar Çalıştır** düğmesidir yeni [!include[vs_dev15](../../misc/includes/vs_dev15_md.md)]. Yeşil ok düğmesini görmüyorsanız kullanın **F11** Bu örnekte bunun yerine hata ayıklayıcı doğru yere ilerlemek için.

2. Tıklayın **tıklanan satıra kadar Çalıştır** düğmesi ![tıklanan satıra kadar Çalıştır](../../debugger/media/dbg-tour-run-to-click.png "RunToClick").

    Bu düğmeyi kullanarak geçici bir kesme noktası ayarlayarak benzer. **Tıklanan satıra kadar Çalıştır** (herhangi bir açık dosyayı tıklayabilirsiniz) uygulama kodu görünür bir bölge içinde hızla dolaşma için kullanışlıdır.

    Hata ayıklayıcı ilerler `Console.WriteLine` yöntem uygulaması için `Triangle` sınıfı.

    Duraklatıldığı sırada bir yazım yanlışı dikkat edin! "Bir trangle çizim" çıkış yanlış yazılmıştır. Biz burada Hata Ayıklayıcısı'nda uygulama çalıştırılırken düzeltebilirsiniz.

## <a name="edit-code-and-continue-debugging"></a>Kodu düzenleme ve hata ayıklamaya devam etme

1. İçine tıklayın "bir trangle çizim" ve "trangle" değiştirme "üçgene", bir düzeltme yazın.

1. Tuşuna **F11** bir kez ve bkz hata ayıklayıcıyı yeniden ilerler.

    > [!NOTE]
    > Ne tür kod hata ayıklayıcıda düzenleme bağlı olarak, bir uyarı iletisi görebilirsiniz. Bazı senaryolarda, kod devam edebilmek derlemeniz gerekir.

## <a name="step-out"></a>Dışına adımla

İşiniz olduğunu düşünelim İnceleme `Draw` yönteminde `Triangle` sınıfı ve istediğiniz get işlevi dışında ancak hata ayıklayıcıda haberdar olun. Bunu kullanarak yapabilirsiniz **Step Out** komutu.

1. Tuşuna **Shift** + **F11** (veya **hata ayıklama > dışarı adımla**).

     Bu komut, uygulama yürütmeyi devam ettirir (ve hata ayıklayıcı ilerler) geçerli işlev dönene kadar.

     Geri olmalıdır `For Each` içinde döngü `Main` yöntemi.

## <a name="restart-your-app-quickly"></a>Uygulamanızı hızlı bir şekilde yeniden başlatın

Tıklayın **yeniden** ![yeniden uygulama](../../debugger/media/dbg-tour-restart.png "RestartApp") hata ayıklama araç çubuğu düğmesini (**Ctrl** + **kaydırma**   +  **F5**).

Bastığınızda **yeniden**, uygulama durdurup hata ayıklayıcı yerine zaman kaydeder. İlk kesme noktasına isabet kodu yürüterek, hata ayıklayıcı duraklatır.

Hata ayıklayıcıyı yeniden üzerinde sizin ayarladığınız kesme noktasında durur `shape.Draw()` yöntemi.

## <a name="inspect-variables-with-data-tips"></a>Veri ipuçları değişkenlerle inceleyin

Değişkenleri incelemek özellik hata ayıklayıcının en kullanışlı özellikler biridir ve bunu yapmanın farklı yolu vardır. Genellikle, hata ayıklama bir sorun açmayı denediğinde, belirli bir zamanda sahip olmalarını beklediğiniz değerleri değişkenleri olup depoladığını kullanıma bulmak çalışıyorsunuz.

1. Üzerinde duraklatıldığı sırada `shape.Draw()` yöntemi, kutucuğun üzerine gelip `shapes` nesne ve bkz varsayılan özellik değerine `Count` özelliği.

1. Genişletin `shapes` tüm özelliklerini, dizinin ilk dizini gibi görmek için nesne `[0]`, değeri olan `Rectangle`.

     ![Bir veri ipucunda görüntülemek](../visual-basic/media/get-started-data-tip-vb.png "bir veri ipucunda görüntüleyin")

    Nesneleri gibi özelliklerini görüntülemek için daha da genişletebilirsiniz `Height` dikdörtgeninin özelliği.

    Genellikle, hata ayıklama sırasında istediğiniz nesnelerin özellik değerlerini denetlemek için hızlı bir yol ve veri ipuçları yapmak için iyi bir yoludur.

## <a name="inspect-variables-with-the-autos-and-locals-windows"></a>Otolar ve yerel öğeler pencerelerinde değişkenlerle inceleyin

1. Bakmak **Otolar** altındaki kod düzenleyicisi penceresi.

     ![Otomatik değişkenler penceresi değişkenleri İnceleme](../visual-basic/media/get-started-autos-window-vb.png "otomatik değişkenler penceresi")

    İçinde **Otolar** penceresi değişkenleri ve bunların geçerli değerini görürsünüz. **Otolar** penceresi, geçerli veya önceki satırındaki (dile özgü davranışı için belgeleri denetleyin) kullanılan tüm değişkenleri gösterir.

2. Ardından, bakmak **Yereller** penceresinde ileri bir sekmeye **Otolar** penceresi.

    **Yereller** penceresi gösterir, geçerli olan değişkenlere [kapsam](https://www.wikipedia.org/wiki/Scope_(computer_science)), diğer bir deyişle, geçerli yürütme bağlamı.

## <a name="set-a-watch"></a>Bir izleme ayarlayın

1. Ana Kod Düzenleyicisi'ni penceresinde sağ `shapes` seçin ve nesne **Gözcü Ekle**.

    **Watch** Kod Düzenleyicisi sayfanın en penceresi açılır. Kullanabileceğiniz bir **Watch** penceresinin bir değişken (veya bir ifade) takip etmek istediğinizi belirtin.

    Artık, bir izleme ayarlayın sahipsiniz `shapes` nesne ve hata ayıklayıcı geçerken değiştirme değeri görebilirsiniz. Diğer değişken pencerelerini aksine **Watch** penceresi her zaman, izlerken değişkenleri gösterir (bunlar zaman kapsam dışına renkte).

## <a name="examine-the-call-stack"></a>Çağrı yığınını inceleyin

1. İçinde duraklatıldığı sırada `For Each` döngüsünde, tıklayın **çağrı yığını** varsayılan alt sağ bölmede açık olarak penceresinde.

2. Tıklayın **F11** birkaç kez duraklatmak, hata ayıklayıcı görene kadar `MyBase.Draw` yöntemi `Rectangle` Kod düzenleyicisinde sınıfı. Bakmak **çağrı yığını** penceresi.

    ![Çağrı yığınını incelemek](../visual-basic/media/get-started-call-stack-vb.png "ExamineCallStack")

    **Çağrı yığını** penceresi, yöntemleri ve işlevleri çağrılır sırasını gösterir. Geçerli işlev en üst satırına gösterir ( `Rectangle.Draw` bu uygulamada yöntemi). İkinci satır gösteren `Rectangle.Draw` çağırıldığı `Main` işlevi ve benzeri.

   > [!NOTE]
   > **Çağrı yığını** penceresi benzer hata ayıklama perspektifi için Eclipse gibi bazı IDE içinde.

    Çağrı yığınını inceleyebilir ve bir uygulamanın yürütme akışını anlamanıza için iyi bir yoludur.

    Bir satır kod, kaynak koda bakmaktır gitmek için çift tıklayın ve hata ayıklayıcı tarafından denetlenmekte olan geçerli kapsamını da değişiklikler. Bu eylem, hata ayıklayıcı ilerleyin değil.

    Sağ tıklama menülerden kullanabilirsiniz **çağrı yığını** başka şeyler için pencere. Örneğin, belirtilen işlevlere kesme noktaları ekleme, hata ayıklayıcıyı kullanarak ilerleyin **imlece kadar Çalıştır**ve kaynak kodunu inceleyin. Daha fazla bilgi için [nasıl yapılır: Çağrı yığınını incelemek](../../debugger/how-to-use-the-call-stack-window.md).

## <a name="change-the-execution-flow"></a>Yürütme akışı değiştirme

1. İçinde hata ayıklayıcısı ile duraklatıldı `MyBase.Draw` yöntemi çağrısı `Rectangle` sınıfı, sol taraftaki sarı ok (yürütme işaretçisi) almak için fareyi kullanın ve sarı ok için bir satır yukarı taşı `Console.WriteLine` yöntem çağrısı.

1. Tuşuna **F11**.

    Hata ayıklayıcıyı yeniden çalıştırır `Console.WriteLine` yöntemi (yinelenen çıkış konsol penceresi çıktısı görürsünüz).

    Yürütme akışı değiştirerek farklı kod yürütme yolları test veya hata ayıklayıcı yeniden başlatmadan kodu yeniden gibi işlemler yapabilirsiniz.

    > [!WARNING]
    > Genelde bu özellikle dikkat etmek gerekir ve araç ipucunda bir uyarı görürsünüz. Çok diğer uyarılar görebilirsiniz. İşaretçiyi taşıma uygulamanızı daha önceki bir uygulama durumuna geri alınamaz.

1. Tuşuna **F5** uygulamayı çalıştırmaya devam etmek için.

    Bu öğreticiyi tamamlamak Tebrikler!

## <a name="next-steps"></a>Sonraki adımlar

Bu öğreticide, kodu adımlayın hata ayıklayıcıyı başlatın ve değişkenleri denetleyin öğrendiniz. Daha fazla bilgi için bağlantılar hata ayıklayıcı özelliklerine genel bir bakış almak isteyebilirsiniz.

> [!div class="nextstepaction"]
> [Hata ayıklayıcıya ilk bakış](../../debugger/debugger-feature-tour.md)
