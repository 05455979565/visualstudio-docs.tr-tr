---
title: Visual Basic'te Görselleştirici yazma | Microsoft Docs
ms.custom: seodec18
ms.date: 04/12/2019
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- visualizers, writing
- walkthroughs [Visual Studio], visualizers
ms.assetid: c93bf5a1-3e5e-422f-894e-bd72c9bc1b57
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: d30e789d0ae3fa3e717be9739b94439a7d6a31a2
ms.sourcegitcommit: 847d192013eb8225776243045c9b5a53d1ba4a59
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/15/2019
ms.locfileid: "59584551"
---
# <a name="walkthrough-writing-a-visualizer-in-visual-basic"></a>İzlenecek yol: Visual Basic'de Görselleştirici yazma
Bu kılavuz kullanılarak basit Görselleştirici yazma işlemi gösterilmektedir [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]. Bu izlenecek yolda oluşturacağınız Görselleştirici, bir Windows Forms ileti kutusunu kullanarak bir dizenin içeriklerini görüntüler. Bu basit dize Görselleştirici nasıl görselleştiriciler diğer veri türleri için daha uygun projelerinize oluşturacağınızı göstermek için basit bir örnektir.

> [!NOTE]
> İletişim kutuları ve menü komutları gördüğünüz açıklanana Yardım'da, etkin ayarlarınıza ve sürüm bağlı olarak farklı olabilir. Ayarlarınızı değiştirmek için Git **Araçları** menüsünü seçip **içeri ve dışarı aktarma** . Daha fazla bilgi için [ayarlarına](../ide/environment-settings.md#reset-settings).

Görselleştirici kod, hata ayıklayıcı tarafından okunacak DLL'de yerleştirilmelidir. İlk adım, DLL için bir sınıf kitaplığı projesi oluşturmaktır.

## <a name="create-and-prepare-a-class-library-project"></a>Oluşturma ve bir sınıf kitaplığı projesi hazırlama

### <a name="to-create-a-class-library-project"></a>Bir sınıf kitaplığı projesi oluşturmak için

1. Yeni bir sınıf kitaplığı projesi oluşturun.

    ::: moniker range=">=vs-2019"
    Tuşuna **Esc** başlangıç penceresini kapatın. Tür **Ctrl + Q** arama kutusunu açmak için şunu yazın **visual basic**, seçin **şablonları**, ardından **yeni bir sınıf kitaplığı (.NET Standard)oluşturma**. Görünen iletişim kutusunda **Oluştur**.
    ::: moniker-end
    ::: moniker range="vs-2017"
    Üstteki menü çubuğundan seçin **dosya** > **yeni** > **proje**. Sol bölmesinde **yeni proje** iletişim kutusunun **Visual Basic**, seçin **.NET Standard**seçip Ortadaki bölmeden **sınıf kitaplığı (.NET Standart)**.
    ::: moniker-end

2. Sınıf kitaplığı için uygun bir ad yazın `MyFirstVisualizer`ve ardından **Oluştur** veya **Tamam**.

   Sınıf kitaplığı oluşturduktan sonra tanımlanan sınıflara var. kullanabilmesi için Microsoft.VisualStudio.DebuggerVisualizers.DLL, bir başvuru eklemeniz gerekir. İlk olarak, ancak, projenize anlamlı bir ad verin.

### <a name="to-rename-class1vb-and-add-microsoftvisualstudiodebuggervisualizers"></a>Class1.vb yeniden adlandırıp Microsoft.VisualStudio.DebuggerVisualizers Ekle

1. İçinde **Çözüm Gezgini**, sağ **Class1.vb**ve kısayol menüsünde **Yeniden Adlandır**.

2. Ad Class1.vb DebuggerSide.vb gibi anlamlı değiştirin.

   > [!NOTE]
   >  [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] sınıf bildirimi içinde DebuggerSide.vb yeni dosya adı ile eşleşecek şekilde otomatik olarak değiştirir.

3. İçinde **Çözüm Gezgini**, sağ **My ilk Görselleştirici**ve kısayol menüsünde **Başvuru Ekle**.

4. İçinde **Başvuru Ekle** iletişim kutusundaki **Gözat** sekmesinde **Gözat** Microsoft.VisualStudio.DebuggerVisualizers.DLL bulun.

    DLL içinde bulabilirsiniz  *\<Visual Studio yükleme dizini > \Common7\IDE\PublicAssemblies* Visual Studio'nun yükleme dizininin alt.

5. **Tamam**'ı tıklatın.

6. Aşağıdaki deyime DebuggerSide.vb içinde ekleyin `Imports` ifadeleri:

   ```vb
   Imports Microsoft.VisualStudio.DebuggerVisualizers
   ```

## <a name="add-the-debugger-side-code"></a>Hata ayıklayıcı tarafı kodu ekleyin
 Artık, hata ayıklayıcı tarafından çalışan kod oluşturmaya hazırsınız. Görselleştirmek istediğiniz bilgileri görüntülemek için hata ayıklayıcısı içinde çalıştırılan kod budur. İlk olarak, bildirimini değiştirmek zorunda `DebuggerSide` taban sınıfından devralan nesnesini `DialogDebuggerVisualizer`.

### <a name="to-inherit-from-dialogdebuggervisualizer"></a>DialogDebuggerVisualizer devralacak şekilde

1. Aşağıdaki kod satırını DebuggerSide.vb içinde gidin:

   ```vb
   Public Class DebuggerSide
   ```

2. Kod şuna benzer şekilde düzenleyin:

   ```vb
   Public Class DebuggerSide
   Inherits DialogDebuggerVisualizer
   ```

   `DialogDebuggerVisualizer` soyut bir yöntemi, `Show`, geçersiz kılmanız gerekir.

### <a name="to-override-the-dialogdebuggervisualizershow-method"></a>DialogDebuggerVisualizer.Show yöntemi geçersiz kılmak için

- İçinde `public class DebuggerSide`, aşağıdaki yöntemi ekleyin:

  ```vb
  Protected Overrides Sub Show(ByVal windowService As Microsoft.VisualStudio.DebuggerVisualizers.IDialogVisualizerService, ByVal objectProvider As Microsoft.VisualStudio.DebuggerVisualizers.IVisualizerObjectProvider)

      End Sub
  ```

  `Show` Yöntemi gerçekten görselleştiricisi iletişim kutusu veya diğer kullanıcı arabirimi oluşturur ve hata ayıklayıcı'dan görselleştiriciye geçirildi bilgilerini görüntüler kodunu içerir. İletişim kutusu oluşturur ve bilgi görüntüleyen bir kod eklemeniz gerekir. Bu kılavuzda, bir Windows Forms ileti kutusunu kullanarak bunu. İlk olarak, bir başvuru ekleyin ve `Imports` bildirimi <xref:System.Windows.Forms>.

### <a name="to-add-systemwindowsforms"></a>System.Windows.Forms eklemek için

1.  İçinde **Çözüm Gezgini**, sağ **başvuruları**ve kısayol menüsünde **Başvuru Ekle**.

2. İçinde **Başvuru Ekle** iletişim kutusundaki **Gözat** sekmesinde **Gözat**, System.Windows.Forms.DLL bulun.

    DLL içinde bulabilirsiniz *C:\Windows\Microsoft.NET\Framework\v4.0.30319*.

3.  **Tamam**'ı tıklatın.

4.  Aşağıdaki deyime DebuggerSide.cs içinde ekleyin `Imports` ifadeleri:

    ```vb
    Imports System.Windows.Forms
    ```

## <a name="create-your-visualizers-user-interface"></a>Visualizer'ın kullanıcı arabirimi oluşturma
 Şimdi oluşturun ve kullanıcı arabirimi için Görselleştirici göstermek için bazı kod ekleyeceksiniz. Bu, ilk Görselleştirici olduğu için kullanıcı arabirimi basit tutmak ve bir ileti kutusunu kullanın.

### <a name="to-show-the-visualizer-output-in-a-dialog-box"></a>İletişim kutusunda görselleştiricisi çıkışının görüntülenmesi için

1.  İçinde `Show` yöntemini aşağıdaki kod satırını ekleyin:

    ```vb
    MessageBox.Show(objectProvider.GetObject().ToString())
    ```

     Bu kod örneği, hata işleme içermez. Hata işleme gerçek Görselleştirici veya herhangi bir uygulama türünü içermelidir.

2.  Üzerinde **derleme** menüsünde tıklatın **derleme MyFirstVisualizer**. Proje başarıyla oluşturması gerekir. Devam etmeden önce derleme hataları düzeltin.

## <a name="add-the-necessary-attribute"></a>Gerekli öznitelik Ekle
 Hata ayıklayıcı tarafı kodun sonuna olmasıdır. Var olan bir adım daha ancak: görselleştiriciyi hata ayıklanan yan hangi sınıfları koleksiyonu belirten özniteliği oluşur.

### <a name="to-add-the-debugee-side-code"></a>Debugee tarafı kod eklemek için

1.  DebuggerSide.vb için aşağıdaki kodu özniteliği ekleyin `Imports` deyimleri önce `namespace MyFirstVisualizer`:

    ```vb
    <Assembly: System.Diagnostics.DebuggerVisualizer(GetType(MyFirstVisualizer.DebuggerSide), GetType(VisualizerObjectSource), Target:=GetType(System.String), Description:="My First Visualizer")>
    ```

2.  Üzerinde **derleme** menüsünde tıklatın **derleme MyFirstVisualizer**. Proje başarıyla oluşturması gerekir. Devam etmeden önce derleme hataları düzeltin.

## <a name="create-a-test-harness"></a>Bir Test bandı oluşturma
 Bu noktada, ilk Görselleştirici tamamlandı. Doğru adımları izlediyseniz, görselleştiricisi oluşturun ve içine yüklemek [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Görselleştirici içine yüklemeden önce [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], ancak doğru şekilde çalıştığından emin olmak için sınamalısınız. Görselleştirici içine yüklemeden çalıştırmak için test bandı şimdi oluşturacak [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].

### <a name="to-add-a-test-method-to-show-the-visualizer"></a>Görselleştirici göstermek için bir test yöntemi eklemek için

1. Sınıfına aşağıdaki yöntemi ekleyin `public DebuggerSide`:

   ```vb
   Shared Public Sub TestShowVisualizer(ByVal objectToVisualize As Object)
       Dim visualizerHost As New VisualizerDevelopmentHost(objectToVisualize, GetType(DebuggerSide))
   visualizerHost.ShowVisualizer()
   End Sub
   ```

2. Üzerinde **derleme** menüsünde tıklatın **derleme MyFirstVisualizer**. Proje başarıyla oluşturması gerekir. Devam etmeden önce derleme hataları düzeltin.

   Ardından, DLL, Görselleştirici çağırmak için bir yürütülebilir proje oluşturmanız gerekir. Kolaylık olması için bir konsol uygulama projesi kullanın.

### <a name="to-add-a-console-application-project-to-the-solution"></a>Bir konsol uygulaması projesi çözüme eklemek için

1. Çözüm Gezgini'nde çözüme sağ tıklayın, seçin **Ekle**ve ardından **yeni proje**.

    ::: moniker range=">=vs-2019"
    Arama kutusuna **visual basic**, seçin **şablonları**, ardından **yeni bir konsol uygulaması (.NET Framework) oluşturma**. Görünen iletişim kutusunda **Oluştur**.
    ::: moniker-end
    ::: moniker range="vs-2017"
    Üstteki menü çubuğundan seçin **dosya** > **yeni** > **proje**. Sol bölmesinde **yeni proje** iletişim kutusunun **Visual Basic**, seçin **Windows Masaüstü**seçip Ortadaki bölmeden **konsol uygulaması (.NET Framework)**.
    ::: moniker-end

2. Sınıf kitaplığı için uygun bir ad yazın `MyTestConsole`ve ardından **Oluştur** veya **Tamam**.

   Artık gerekli MyTestConsole MyFirstVisualizer çağırabilmek başvuran eklemeniz gerekir.

### <a name="to-add-necessary-references-to-mytestconsole"></a>MyTestConsole gerekli başvuruları eklemek için

1.  İçinde **Çözüm Gezgini**, sağ **MyTestConsole**ve kısayol menüsünde **Başvuru Ekle**.

2.  İçinde **Başvuru Ekle** iletişim kutusundaki **Gözat** Microsoft.VisualStudio.DebuggerVisualizers sekmesine,.

3.  **Tamam**'ı tıklatın.

4.  Sağ **MyTestConsole**ve ardından **Başvuru Ekle** yeniden.

5.  İçinde **Başvuru Ekle** iletişim kutusu, tıklayın **projeleri** sekmesini ve ardından MyFirstVisualizer seçin.

6.  **Tamam**'ı tıklatın.

## <a name="finish-your-test-harness-and-test-your-visualizer"></a>Son Test Bandınız ve, Görselleştiriciyi test etme
 Şimdi, test bandı tamamlamak için kod ekleyeceksiniz.

### <a name="to-add-code-to-mytestconsole"></a>Kod için MyTestConsole eklemek için

1. İçinde **Çözüm Gezgini**, sağ **Program.vb**ve kısayol menüsünde **Yeniden Adlandır**.

2. Uygun, Module1.vb adından gibi Düzen **TestConsole.vb**.

    Dikkat [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] sınıf bildirimi içinde TestConsole.vb yeni dosya adı ile eşleşecek şekilde otomatik olarak değiştirir.

3. TestConsole içinde. vb, aşağıdaki `Imports` deyimi:

   ```vb
   Imports MyFirstVisualizer
   ```

4. Yönteminde `Main`, aşağıdaki kodu ekleyin:

   ```vb
   Dim myString As String = "Hello, World"
   DebuggerSide.TestShowVisualizer(myString)
   ```

   Şimdi, ilk görselleştiriciyi sınamak hazır olursunuz.

### <a name="to-test-the-visualizer"></a>Görselleştiriciyi sınamak için

1. İçinde **Çözüm Gezgini**, sağ **MyTestConsole**ve kısayol menüsünde **başlangıç projesi olarak ayarla**.

2. Üzerinde **hata ayıklama** menüsünde tıklatın **Başlat**.

    Konsol uygulamasını başlatır. Görselleştirici görünür ve "Hello, World." dizesini görüntüler

   Tebrikler. Yalnızca yerleşik ve test, ilk Görselleştirici.

   Görselleştiricisindeki kullanmak istiyorsanız [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] yüklemek zorunda yalnızca, test bandı çağırmak yerine,. Daha fazla bilgi için [nasıl yapılır: Görselleştiriciyi yükleme](../debugger/how-to-install-a-visualizer.md).

## <a name="see-also"></a>Ayrıca bkz.

- [Görselleştirici Mimarisi](../debugger/visualizer-architecture.md)
- [Nasıl yapılır: Görselleştiriciyi Yükleme](../debugger/how-to-install-a-visualizer.md)
- [Özel Görselleştirici Oluşturma](../debugger/create-custom-visualizers-of-data.md)