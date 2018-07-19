---
title: Visual Studio’da XAML Tasarımcısı’nı kullanarak kullanıcı arabirimi oluşturma
ms.date: 07/17/2017
ms.prod: visual-studio-dev15
ms.technology: vs-ide-designers
ms.topic: conceptual
f1_keywords:
- VS.XamlDesigner
- VS.DevicePanel
- VS.XamlEditor
- VS.DocumentOutline
ms.assetid: c54969a7-d75a-4a35-9b37-af7a596a7c24
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- uwp
ms.openlocfilehash: 3daf20ee3fcb2472e88d2387abf870862b0d5c47
ms.sourcegitcommit: 522ba712c0d625e51352506146b0556414681964
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37889973"
---
# <a name="creating-a-ui-by-using-xaml-designer-in-visual-studio"></a>Visual Studio’da XAML Tasarımcısı’nı kullanarak kullanıcı arabirimi oluşturma
Visual Studio'da XAML Tasarımcısı, tasarım XAML tabanlı Windows ve Web uygulamaları yardımcı olması için görsel bir arabirim sağlar. Denetimlerden sürükleyerek, uygulamalarınız için kullanıcı arabirimleri oluşturabilirsiniz **araç kutusu** ve ayarları **özellikleri** penceresi. Ayrıca, XAML XAML görünümünde doğrudan düzenleyebilirsiniz.

 Gelişmiş XAML tasarım görevleri için animasyon ve davranışlarla gibi bkz [Visual Studio için Blend'i kullanarak kullanıcı Arabirimi oluşturma](../designers/creating-a-ui-by-using-blend-for-visual-studio.md). Ayrıca bkz: [Visual Studio ve Visual Studio için Blend tasarım XAML](../designers/designing-xaml-in-visual-studio.md) araçlar arasında bir karşılaştırma için.

## <a name="xaml-designer-workspace"></a>XAML Tasarımcısı çalışma alanı
 XAML Tasarımcısı'nda çalışma birkaç görsel arabirim öğelerini içerir. Bunlar **çalışma yüzeyine**, **XAML Düzenleyicisi**, **cihaz** penceresinde **belge anahattı** penceresinde ve **özellikleri**  penceresi. XAML Tasarımcısı'nı açmak için bir XAML dosyasında sağ **Çözüm Gezgini** ve **Görünüm Tasarımcısı**.

## <a name="authoring-views"></a>Yazma görünümleri
 XAML Tasarımcısı, uygulamanızın biçimlendirmenin XAML eşitlenmiş bir Tasarım görünümünü ve XAML görünümü sağlar. Visual Studio'da açık bir XAML dosyası ile XAML görünümünü ve Tasarım görünümü arasında kullanarak geçebilirsiniz **tasarım** ve **XAML** sekmeler. Kullanabileceğiniz **takas bölmeleri** düğmesi hangi penceresinde geçiş yapmak için en üstte görünür: çalışma yüzeyine ya da XAML Düzenleyicisi.

 Tasarım görünümünde, pencereyi içeren *çalışma yüzeyine* etkin pencere ve birincil çalışma yüzeyi olarak kullanabilirsiniz. Görsel olarak bir sayfa veya çizim öğeleri ekleyerek ve ardından bunları değiştirerek uygulamanızı tasarlamak için kullanabilirsiniz. Daha fazla bilgi için bkz. [XAML Tasarımcısı'nda öğelerle çalışma](../designers/working-with-elements-in-xaml-designer.md). Bu örnekte, çalışma yüzeyinde Tasarım görünümünde gösterilmiştir.

 ![XAML Tasarımcısı'nın tasarım görünümü](../designers/media/xaml_editor_design_view.png)

 Bu özellikler, çalışma yüzeyine kullanılabilir:

 **Dayama çizgileri** dayama çizgileri olan *hizalama sınırları* denetimleri kenarlarına zaman hizalanır veya ne zaman metin taban çizgileri hizalanmış göstermek için kırmızı kesik çizgili satırlar halinde görünür. Hizalama sınırları yalnızca görünür **dayama çizgilerine yaslamayı** etkinleştirilir.

 **Kılavuz rayları** `Grid` rails içindeki satırları ve sütunları yönetmek için kullanılan bir [kılavuz](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.controls.grid.aspx) paneli. Oluşturma ve satırları ve sütunları Sil ve kendi göreli genişlik ve yükseklik ayarlayabilirsiniz. Çalışma yüzeyinin sol tarafında görünür, dikey kılavuz parmaklık için satırlar kullanılır ve üst kısmında görünür, yatay çizgi sütunlar için kullanılır.

 **Kılavuz donatıcıları** hakkında kılavuz parmaklık bağlı dikey veya yatay çizgi bulunan bir üçgen olarak bir kılavuz donatıcı görünür. Bir kılavuz donatıcı sürüklediğinizde, fareyi hareket ettirdiğinizde genişlikleri veya bitişik sütun veya satır yükseklikleri güncelleştirin.

 Kılavuz donatıcıları, genişlik ve yükseklik bir kılavuz satırları ve sütunları denetlemek için kullanılır. Yeni bir sütun veya satır içinde kılavuz rayları tıklayarak ekleyebilirsiniz. Yeni bir satır veya sütun satırında iki veya daha fazla sütun veya satır içeren bir kılavuz bölmesi için eklediğinizde, kısa bir araç çubuğu genişlik ve yükseklik açıkça ayarlamanıza olanak tanır parmaklık dışında görünür. Mini Araç kılavuz satırları ve sütunları boyutlandırma seçeneklerini ayarlamanızı sağlar.

 **Yeniden boyutlandırma tutamaçları** yeniden boyutlandırma tutamaçları üzerinde Seçili denetimleri görünür ve yeniden boyutlandırma sağlar. Bir denetimi yeniden boyutlandırdığınızda, genişlik ve yükseklik değerlerini, genellikle denetiminin boyutunu yardımcı olması için görünür. Denetimleri düzenleme hakkında daha fazla bilgi için **tasarım** görüntülemek için bkz: [XAML Tasarımcısı'nda öğelerle çalışma](../designers/working-with-elements-in-xaml-designer.md).

 **Kenar boşlukları** kenar boşlukları, bir denetimin kenarı ile onun kapsayıcısının arasındaki sabit boşluk miktarını temsil eder. Bir denetim kenar boşluklarını kullanarak ayarlayabilirsiniz [kenar boşluğu](http://msdn.microsoft.com/library/windows/apps/windows.ui.xaml.frameworkelement.margin.aspx) özellikleri altında **Düzen** Özellikler penceresinde.

 **Margin donatıcıları** Düzen kapsayıcısı göreli öğe kenar boşluklarını değiştirmek için kenar boşluğu donatıcıları kullanabilirsiniz. Kenar boşluğu donatıcısı açıksa, bir kenar boşluğu ayarlı değildir ve kenar boşluğu donatıcısı bozuk zincirini görüntüler. Kenar boşluğu ayarlı değil, Düzen kapsayıcısı çalışma zamanında yeniden boyutlandırıldığında öğeleri değiştirilmez. Kenar boşluğu donatıcısı kapalı olduğunda, kenar boşluğu donatıcısı sertifikalarından zinciri görüntüler ve Düzen kapsayıcısı (kenar sabit kalır), çalışma zamanında yeniden boyutlandırıldığından kenar boşlukları ile öğeleri Taşı.

 **Öğe tanıtıcıları** öğenin çevreleyen mavi kutusunun köşeleri işaretçiyi getirdiğinizde çalışma yüzeyinde görüntülenen öğe tutamaçları kullanarak bir öğeyi değiştirebilirsiniz. Bu tanıtıcıları, döndürme, yeniden boyutlandırma, çevir, taşıyın veya öğeye bir köşe yarıçapı eklemenizi sağlar. Öğesi işleyici için Sembol işlevi değişir ve işaretçiyi tam konumuna bağlı olarak değişir. Öğe tutamaçları görmüyorsanız, öğe seçili olduğundan emin olun.

 İçinde **tasarım** görünümü, ek çalışma yüzeyine komutları kullanılabilir ekranın sol alt bölümünde aşağıda gösterildiği gibi:

 ![Tasarım görünümü komutları](../designers/media/xaml_editor_design_controls.png)

 Bu komutlar, bu araç çubuğunda kullanılabilir:

 **Yakınlaştırma** yakınlaştırma tasarım yüzeyine boyut olanak sağlar. %12,5 %800 yakınlaştırma veya gibi seçeneklerini **seçimi Sığdır** ve **tümünü Sığdır**.

 **Yaslama kılavuzunu Göster/Gizle** görüntüler veya kılavuz çizgilerini gösterir kılavuza gizler. Kılavuz çizgileri, ya da etkinleştirdiğinizde kullanılır **çizgilerine yaslamayı** veya **dayama çizgilerine yaslamayı**.

 **Açma / kapatma çizgilerine yaslamayı** varsa **çizgilerine yaslamayı** etkindir, çalışma yüzeyinde bir öğeyi sürüklediğinizde en yakın yatay ve dikey kılavuz ile hizalamak için öğe eğilimi gösterir.

 **Açma / kapatma dayama çizgilerine yaslamayı** dayama çizgileri Yardım, hizalama, birbirlerine göreli denetler. Varsa **dayama çizgilerine yaslamayı** denetimini diğer denetimlere göre sınırları görünür kenarları ve bazı denetimler metnin yatay veya dikey olarak hizalandığında hizalama sürüklediğinizde, etkinleştirilir. Bir hizalama sınırı kırmızı kesik çizgili bir çizgi olarak görünür.

 İçinde **XAML** görünümü, XAML Düzenleyicisi'ni içeren pencereyi etkin pencere ve XAML Düzenleyicisi'ni, birincil geliştirme aracı. Extensible Application Markup Language (XAML), bir uygulamanın kullanıcı arabirimini belirtmek için bildirim temelli, XML tabanlı bir sözlüğünü sağlar. XAML görünümü, IntelliSense, otomatik biçimlendirme, söz dizimi vurgulama ve etiket Gezinti içerir. Bu örnekte, XAML görünümü gösterilmiştir:

 ![XAML görünümü](../designers/media/xaml_editor.png)

 **Bölünmüş Görünüm çubuğunun** XAML Düzenleyicisi'ni alt pencereye olduğunda Bölünmüş Görünüm Çubuğu XAML görünümü üst kısmında görünür. Bölünmüş Görünüm Çubuğu göreli boyutlarını denetlemenize olanak sağlayan **tasarım** görünümü ve **XAML** görünümü. Görünüm konumları da değiştirebilir (kullanarak **takas bölmeleri** düğmesi), görünümleri yatay veya dikey olarak düzenlenmiş belirtin ve ya da görünümü Daralt.

 **Biçimlendirme yakınlaştırma** biçimlendirme Yakınlaştırma sayesinde boyutuna **XAML** görünümü. %400 %20 değerinden yakınlaştırma yapabilirsiniz.

## <a name="device-window"></a>Cihaz penceresi
 **Cihaz** XAML Tasarımcısı penceresinde tasarım zamanında çeşitli görünümler, görüntüler, benzetimini gerçekleştirmek ve projeniz için seçenekleri görüntüleme olanak sağlar. **Cihaz** penceresi üzerinde kullanılabilir **tasarım** XAML Tasarımcısı'nda çalışırken menüsü. İşte bu şekilde görünür:

 ![Cihaz penceresi](../designers/media/xaml_editor_device_panel.png)

 Cihaz penceresindeki Seçenekler şunlardır:

 **Görüntüleme** farklı ekran boyutları ve uygulama çözümü belirtir.

 **Yönlendirme** uygulama için farklı yönleri belirtir: **yatay** veya **dikey**.

 **Edge** uygulamanızın farklı edge hizalamaları belirtir: **hem**, **sol**, **sağ**, veya **hiçbiri**.

 **Yüksek Karşıtlık** seçili karşıltık ayarını temel alarak uygulamayı önizleyin. Dışında bir değere ayarlanırsa, bu ayar **varsayılan**, geçersiz kılmalar `RequestedTheme` özellik kümesinde *App.xaml*.

 **Ölçeklendirme geçersiz kılma** odasının ışıklarının belge tasarım yüzeyine içinde ölçeklendirme öykünmesini etkinleştirir. Bu bir faktörüyle ölçeğe artırmanıza olanak sağlar. Öykünme üzerinde etkinleştirmek için onay kutusunu seçin. Örneğin, ölçeklendirme, yüzde %100 ise, belge tasarım yüzeyine içinde %140 ölçeklendirin. Geçerli ölçeğe 180 ise bu seçenek devre dışıdır.

 **Minimum Genişlik** minimum genişlik ayarını belirtir. Minimum genişliğini değiştirilebilir *App.xaml*.

 **Tema** uygulama temasını belirtir. Örneğin, arasında geçiş bir **koyu** ve **ışık** tema.

 **Chrome Göster** etkinleştirebilir veya sanal tablet çerçeve Tasarım görünümünde uygulamanızın etrafında'devre dışı bırakır. Çerçeve göstermek için onay kutusunu seçin.

 **Görüntülenecek küçük** görüntü modunu belirtir. Belge boyutunu görüntüleme boyutuna kırpmak için bu onay kutusunu seçin.

## <a name="document-outline-window"></a>Belge Anahattı penceresi
 Belge Anahattı penceresi XAML Tasarımcısı'nda bu görevleri gerçekleştirmenize yardımcı olur:

-   Çalışma yüzeyinde tüm öğeleri hiyerarşik yapısını görüntüleyin.

-   Öğeleri seçin, böylece bunları (hiyerarşisinde etrafında onları çalışma yüzeyinde değiştirin, özelliklerini Özellikler penceresinde ayarlayın ve benzeri taşıma) değiştirebilirsiniz. Daha fazla bilgi için [XAML Tasarımcısı'nda öğelerle çalışma](../designers/working-with-elements-in-xaml-designer.md)

-   Denetimleri olan öğeler için şablonları oluşturup yeniden açın.

-   Seçilen öğeler için bağlam menüsünü kullanın. Aynı menüyü, çalışma yüzeyinde seçilen öğeleri için de kullanılabilir.

 Görüntülemek için **belge anahattı** penceresinde, menü çubuğundan seçin **görünümü** > **diğer Windows** > **BelgeAnahattı**.

 ![Belge Anahattı penceresi](../designers/media/xaml_editor_doc_outline.png)

 Kullanılabilir seçenekleri bunlar **belge anahattı** penceresi:

 **Belge Anahattı** ana görünümünde **belge anahattı** penceresi hiyerarşisini bir belgenin bir ağaç yapısında görüntüler. Farklı düzeylerde, belge inceleme ve kilitleme ve öğeleri tek veya grup gizlemek için Belge Anahattı hiyerarşik yapısını kullanabilirsiniz.

 **Göster/Gizle** Belge Anahattı öğelere karşılık gelen gösterir veya gizler çalışma yüzeyine öğeleri. Kullanım **Göster/Gizle** gösterilen göz önünde bir simgesi görüntüleyen, düğmeler veya basın **Ctrl**+**H** öğeleri gizlenecek ve **Shift** + **Ctrl**+**H** bunları görüntülemek için.

 **Kilitle/Kilidini Aç** kilitler veya belge ana hattı öğelere karşılık gelen çalışma yüzeyine öğeleri kilidini açar. Kilitli öğeler değiştirilemez. Kullanım **Kilitle/Kilidini Aç** kilitliyken bir kilit simgesi görüntüleyen, düğmeler veya basın **Ctrl**+**L** kilit öğelere ve **Shift** + **Ctrl**+**L** kilidini açmak için.

 **Kapsamına dönmek için pageRoot** en üstündeki seçeneği **belge anahattı** yukarı ok simgesi gösterir, penceresinde Belge Anahattı önceki kapsama döndürür. Üst kapsama gitme yalnızca bir stil veya şablon kapsamı içinde olduğunuzda geçerlidir.

## <a name="properties-window"></a>Özellik penceresi
 **Özellikleri** penceresi denetimlerinde özellik değerlerini ayarlamanıza olanak sağlar. İşte bu şekilde görünür:

 ![Özellik penceresi](../designers/media/xaml_editor_prop_window.png)

 Çeşitli seçenekler en üstündeki **özellikleri** penceresi. Seçili olan öğenin adını kullanarak değiştirebileceğiniz **adı** kutusu. Sol üst köşesinde şu anda seçilen öğeyi temsil eden bir simge yoktur. Özellikleri kategoriye veya alfabetik olarak düzenlemek için tıklayın **kategori**, **adı**, veya **kaynak** içinde **ölçütü** listesi. Bir denetim için olayların listesini görmek için tıklayın **olayları** düğmesi, bir ışık Şimşek simgesi görüntüler. Bir özellik için arama yapmak için özelliğin adını yazmaya başlayın **arama özellikleri** kutusu. **Özellikleri** yazarken aramanızla eşleşen Özellikler penceresinde görüntülenir. Bazı özellikler bir aşağı ok düğmesini seçerek gelişmiş özelliklerini ayarlamanıza olanak sağlar. Özellikleri kullanma ve olayları işleme hakkında daha fazla bilgi için bkz. [hızlı başlangıç: denetimler ekleme ve olayları işleme](http://go.microsoft.com/fwlink/?LinkID=247983)

 Her bir özellik sağındaki değer bir *özelliği işaretçisi* kutusu simgesi olarak görünür. Özellik işaretçisi görünümünü veri bağlama veya özelliğine uygulanan bir kaynak olup olmadığını belirtir. Örneğin, beyaz kutu simgesi varsayılan bir değer belirtir, yerel kaynak uygulanan ve turuncu bir kutu, genellikle bir veri bağlamayı uygulanan gösterir genellikle bir siyah kutu simgesi gösterir. Özellik işaretçisi tıkladığınızda stili tanımına gidin, veri bağlama Oluşturucusu'nu açmak veya Kaynak Seçici'yi açın.

## <a name="see-also"></a>Ayrıca bkz.

- [XAML Tasarımcısı'nda öğelerle çalışma](../designers/working-with-elements-in-xaml-designer.md)
- [Kaynak oluşturma ve uygulama](../designers/how-to-create-and-apply-a-resource.md)
- [İzlenecek yol: XAML Tasarımcısı’nda verileri bağlama](../designers/walkthrough-binding-to-data-in-xaml-designer.md)