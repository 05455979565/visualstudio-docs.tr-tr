---
title: Şerit nesne modeline genel bakış
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Ribbon [Office development in Visual Studio], object model
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 6ca22704345fefb4944bda7dd9f71942fe8dfb50
ms.sourcegitcommit: e98db44f3a33529b0ba188d24390efd09e548191
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/25/2019
ms.locfileid: "71256011"
---
# <a name="ribbon-object-model-overview"></a>Şerit nesne modeline genel bakış
  , [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] Çalışma zamanında Şerit denetimlerinin özelliklerini almak ve ayarlamak için kullanabileceğiniz, türü kesin belirlenmiş bir nesne modeli sunar. Örneğin, menü denetimlerini dinamik olarak doldurabilir veya bağlamsal olarak denetimlerini gösterebilir ve gizleyebilirsiniz. Ayrıca, şerit 'e sekmeler, gruplar ve denetimler ekleyebilirsiniz, ancak yalnızca Şerit Office uygulaması tarafından yüklenmeden önce. Bilgi için bkz. [Salt okunabilir olan özellikleri ayarlama](#SettingReadOnlyProperties).

 [!INCLUDE[appliesto_ribbon](../vsto/includes/appliesto-ribbon-md.md)]

 Bu şerit nesne modeli, genellikle [Şerit sınıfından](#RibbonClass), [Şerit olaylarından](#RibbonEvents)ve [Şerit denetim sınıflarından](#RibbonControlClasses)oluşur.

## <a name="RibbonClass"></a>Şerit sınıfı
 Projeye yeni bir **Şerit (görsel Tasarımcı)** öğesi eklediğinizde, Visual Studio projenize **Şerit** sınıfı ekler. **Şerit** sınıfı <xref:Microsoft.Office.Tools.Ribbon.RibbonBase> sınıfından devralır.

 Bu sınıf, Şerit kod dosyası ve Şerit Tasarımcı kod dosyası arasında bölünen kısmi bir sınıf olarak görünür.

## <a name="RibbonEvents"></a>Şerit olayları
 **Şerit** sınıfı aşağıdaki üç olayı içerir:

|Olay|Açıklama|
|-----------|-----------------|
|<xref:Microsoft.Office.Tools.Ribbon.RibbonBase.Load>|Office uygulaması şerit özelleştirmesini yüklediğinde tetiklenir. <xref:Microsoft.Office.Tools.Ribbon.OfficeRibbon.Load> Olay işleyicisi, Şerit kod dosyasına otomatik olarak eklenir. Şerit yüklendiğinde özel kod çalıştırmak için bu olay işleyicisini kullanın.|
|<xref:Microsoft.Office.Tools.Ribbon.RibbonBase.LoadImage>|Şerit 'in yüklediğinde, Şerit özelleştirmesindeki görüntüleri önbelleğe almanıza olanak sağlar. Bu olay işleyicisindeki Şerit görüntülerini önbelleğe almak için kod yazarsanız küçük bir performans kazancı elde edebilirsiniz. Daha fazla bilgi için bkz. <xref:Microsoft.Office.Tools.Ribbon.OfficeRibbon.LoadImage>.|
|<xref:Microsoft.Office.Tools.Ribbon.RibbonBase.Close>|Şerit örneği kapandığında tetiklenir.|

## <a name="RibbonControlClasses"></a>Şerit denetimleri
 Ad <xref:Microsoft.Office.Tools.Ribbon> alanı, **araç kutusunun** **Office Şerit denetimleri** grubunda gördüğünüz her denetim için bir tür içerir.

 Aşağıdaki tabloda her `Ribbon` bir denetimin türü gösterilmektedir. Her denetimin açıklaması için bkz. [Şerit 'e genel bakış](../vsto/ribbon-overview.md).

|Denetim adı|Sınıf adı|
|------------------|----------------|
|**Box**|<xref:Microsoft.Office.Tools.Ribbon.RibbonBox>|
|**Düğme**|<xref:Microsoft.Office.Tools.Ribbon.RibbonButton>|
|**ButtonGroup**|<xref:Microsoft.Office.Tools.Ribbon.RibbonButtonGroup>|
|**CheckBox**|<xref:Microsoft.Office.Tools.Ribbon.RibbonCheckBox>|
|**ComboBox**|<xref:Microsoft.Office.Tools.Ribbon.RibbonComboBox>|
|**Listenin**|<xref:Microsoft.Office.Tools.Ribbon.RibbonDropDown>|
|**EditBox**|<xref:Microsoft.Office.Tools.Ribbon.RibbonEditBox>|
|**Galeri**|<xref:Microsoft.Office.Tools.Ribbon.RibbonGallery>|
|**Grup**|<xref:Microsoft.Office.Tools.Ribbon.RibbonGroup>|
|**Etiket**|<xref:Microsoft.Office.Tools.Ribbon.RibbonLabel>|
|**Menü**|<xref:Microsoft.Office.Tools.Ribbon.RibbonMenu>|
|**Ayıraç**|<xref:Microsoft.Office.Tools.Ribbon.RibbonSeparator>|
|**SplitButton**|<xref:Microsoft.Office.Tools.Ribbon.RibbonSplitButton>|
|**sekmesi**|<xref:Microsoft.Office.Tools.Ribbon.RibbonTab>|
|**ToggleButton**|<xref:Microsoft.Office.Tools.Ribbon.RibbonToggleButton>|

 Ad alanı, ad <xref:System.Windows.Forms> alanındaki denetim sınıflarının adlarıyla ad çarpışmasını önlemek için bu türler için "Ribbon" önekini kullanır. <xref:Microsoft.Office.Tools.Ribbon>

 Şerit Tasarımcısına bir denetim eklediğinizde, Şerit Tasarımcısı bu denetimin sınıfını Şerit Tasarımcı kod dosyasında bir alan olarak bildirir.

### <a name="common-tasks-using-the-properties-of-ribbon-controls"></a>Şerit denetimlerinin özelliklerini kullanan ortak görevler
 Her `Ribbon` denetim, bir denetime etiket atama ya da denetimleri gizleme veya gösterme gibi çeşitli görevleri gerçekleştirmek için kullanabileceğiniz özellikleri içerir.

 Bazı durumlarda, şerit yüklendikten sonra veya bir denetim dinamik menüye eklendikten sonra Özellikler salt okunurdur. Daha fazla bilgi için bkz. [Salt okunabilir olan özellikleri ayarlama](#SettingReadOnlyProperties).

 Aşağıdaki tabloda, denetim özelliklerini kullanarak `Ribbon` gerçekleştirebileceğiniz görevlerden bazıları açıklanmaktadır.

|Bu görev için:|Bunu yapın:|
|--------------------|--------------|
|Bir denetimi gizleyin veya gösterin.|Visible özelliğini kullanın.|
|Bir denetimi etkinleştirin veya devre dışı bırakın.|Enabled özelliğini kullanın.|
|Bir denetimin boyutunu ayarlayın.|ControlSize özelliğini kullanın.|
|Denetimde görüntülenen görüntüyü alın.|Image özelliğini kullanın.|
|Bir denetimin etiketini değiştirin.|Label özelliğini kullanın.|
|Bir denetime kullanıcı tanımlı veriler ekleyin.|Tag özelliğini kullanın.|
|Öğeleri,,, veya <xref:Microsoft.Office.Tools.Ribbon.RibbonBox>içinde <xref:Microsoft.Office.Tools.Ribbon.RibbonDropDown> <xref:Microsoft.Office.Tools.Ribbon.RibbonGallery>alın<br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonSplitButton>denetimle.|Items özelliğini kullanın.|
|Bir <xref:Microsoft.Office.Tools.Ribbon.RibbonComboBox>, <xref:Microsoft.Office.Tools.Ribbon.RibbonDropDown>veya denetimineöğeekleyin.<xref:Microsoft.Office.Tools.Ribbon.RibbonGallery>|Items özelliğini kullanın.|
|Bir <xref:Microsoft.Office.Tools.Ribbon.RibbonMenu>öğesine denetimler ekleyin.|Items özelliğini kullanın.<br /><br /> Şerit Office uygulamasına <xref:Microsoft.Office.Tools.Ribbon.RibbonMenu> yüklendikten sonra öğesine denetim eklemek için, Şerit Office uygulamasına yüklenmeden önce <xref:Microsoft.Office.Tools.Ribbon.RibbonMenu.Dynamic%2A> özelliği **true** olarak ayarlamanız gerekir. Bilgi için bkz. [Salt okunabilir olan özellikleri ayarlama](#SettingReadOnlyProperties).|
|Seçili öğe <xref:Microsoft.Office.Tools.Ribbon.RibbonComboBox>,<br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonDropDown>, veya <xref:Microsoft.Office.Tools.Ribbon.RibbonGallery>.|Selectedidıtem özelliğini kullanın. Bir <xref:Microsoft.Office.Tools.Ribbon.RibbonComboBox>için <xref:Microsoft.Office.Tools.Ribbon.RibbonComboBox.Text%2A> özelliğini kullanın.|
|Grupları bir <xref:Microsoft.Office.Tools.Ribbon.RibbonTab>üzerinde alın.|<xref:Microsoft.Office.Tools.Ribbon.RibbonTab.Groups%2A> Özelliğini kullanın.|
|İçinde görünen satır ve sütun sayısını belirtin <xref:Microsoft.Office.Tools.Ribbon.RibbonGallery>.|<xref:Microsoft.Office.Tools.Ribbon.RibbonGallery.RowCount%2A> Ve<xref:Microsoft.Office.Tools.Ribbon.RibbonGallery.ColumnCount%2A> özelliklerini kullanın.|

## <a name="SettingReadOnlyProperties"></a>Salt okuma yapılacak özellikleri ayarlama
 Bazı özellikler yalnızca Şerit yüklenmeden önce ayarlanabilir. Bu özellikleri ayarlamak için üç yer vardır:

- Visual Studio **Özellikler** penceresinde.

- **Şerit** sınıfının oluşturucusunda.

- ,, Veya`ThisDocument` projenizin sınıfında. `CreateRibbonExtensibilityObject` `ThisAddin` `ThisWorkbook`

  Dinamik menüler bazı özel durumlar sağlar. Menüyü içeren şerit yüklendikten sonra bile, yeni denetimler oluşturabilir, özelliklerini ayarlayabilir ve ardından onları çalışma zamanında dinamik bir menüye ekleyebilirsiniz.

  Dinamik menüye eklediğiniz denetimlerin özellikleri herhangi bir zamanda ayarlanabilir.

  Daha fazla bilgi için, bkz. [Salt okunabilir hale gelecek özellikler](#ReadOnlyProperties).

### <a name="set-properties-in-the-constructor-of-the-ribbon"></a>Şeridin oluşturucusunda Özellikleri ayarla
 `Ribbon` **Şerit** sınıfının oluşturucusunda bir denetimin özelliklerini ayarlayabilirsiniz. Bu kod, `InitializeComponent` yönteme çağrıdan sonra görünmelidir. Aşağıdaki örnek, geçerli saat 17:00 Pasifik saati (UTC-8) veya daha sonraki bir gruba yeni bir düğme ekler.

 Aşağıdaki kodu ekleyin.

 [!code-csharp[Trin_Ribbon_ObjectModel#1](../vsto/codesnippet/CSharp/trin_Ribbon_objectmodel_dotnet4/Ribbon1.Designer.cs#1)]
 [!code-vb[Trin_Ribbon_ObjectModel#1](../vsto/codesnippet/VisualBasic/trin_Ribbon_objectmodel_dotnet4/Ribbon1.Designer.vb#1)]

 Visual Studio C# 2008 ' den yükselttiğiniz Visual projelerinde, Oluşturucu Şerit kod dosyasında görünür.

 Visual Basic projelerinde veya içinde C# [!INCLUDE[vs_dev12](../vsto/includes/vs-dev12-md.md)]oluşturduğunuz Visual projelerinde, Oluşturucu Şerit Tasarımcı kod dosyasında görünür. Bu dosya *YourRibbonItem*olarak adlandırılmıştır. Designer.cs veya *YourRibbonItem*. Designer. vb. Bu dosyayı Visual Basic projelerinde görmek için, önce Çözüm Gezgini **tüm dosyaları göster** düğmesini tıklamalısınız.

### <a name="set-properties-in-the-createribbonextensibilityobject-method"></a>CreateRibbonExtensibilityObject yönteminde özellikleri ayarlama
 Bir `Ribbon` denetimin özelliklerini,, veya `CreateRibbonExtensibilityObject` `ThisWorkbook` `ThisAddin`projeniziniçindekiyöntemini geçersizkılarsınızşekildeayarlayabilirsiniz`ThisDocument` . `CreateRibbonExtensibilityObject` Yöntemi hakkında daha fazla bilgi için bkz. [Şerit 'e genel bakış](../vsto/ribbon-overview.md).

 Aşağıdaki örnek, bir Excel çalışma kitabı projesinin `CreateRibbonExtensibilityObject` `ThisWorkbook` sınıfının yönteminde şerit özelliklerini ayarlar.

 Aşağıdaki kodu ekleyin.

 [!code-vb[Trin_Ribbon_ObjectModel#2](../vsto/codesnippet/VisualBasic/trin_Ribbon_objectmodel_dotnet4/ThisWorkbook.vb#2)]
 [!code-csharp[Trin_Ribbon_ObjectModel#2](../vsto/codesnippet/CSharp/trin_Ribbon_objectmodel_dotnet4/ThisWorkbook.cs#2)]

### <a name="ReadOnlyProperties"></a>Salt okunabilir hale gelecek özellikler
 Aşağıdaki tabloda, yalnızca Şerit yüklenmeden önce ayarlanmaları gereken özellikler gösterilmektedir.

> [!NOTE]
> Dinamik menülerde denetimlerin özelliklerini istediğiniz zaman ayarlayabilirsiniz. Bu tablo bu durumda uygulanmaz.

|Özellik|Şerit denetim sınıfı|
|--------------|--------------------------|
|**BoxStyle**|<xref:Microsoft.Office.Tools.Ribbon.RibbonBox>|
|**ButtonType**|<xref:Microsoft.Office.Tools.Ribbon.RibbonSplitButton>|
|**ColumnCount**|<xref:Microsoft.Office.Tools.Ribbon.RibbonGallery>|
|**ControlID**|<xref:Microsoft.Office.Tools.Ribbon.RibbonTab>|
|**Iletişim başlatıcısı**|<xref:Microsoft.Office.Tools.Ribbon.RibbonGroup>|
|**Dinamik**|<xref:Microsoft.Office.Tools.Ribbon.RibbonMenu>|
|**Genel**|<xref:Microsoft.Office.Tools.Ribbon.OfficeRibbon>|
|**Gruplandıran**|<xref:Microsoft.Office.Tools.Ribbon.RibbonTab>|
|**Görüntü**|<xref:Microsoft.Office.Tools.Ribbon.RibbonButton><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonComboBox><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonDialogLauncher><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonDropDown><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonEditBox><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonGallery><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonMenu><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonSplitButton><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonToggleButton>|
|**Öğe boyutu**|<xref:Microsoft.Office.Tools.Ribbon.RibbonMenu><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonSplitButton>|
|**'In**|<xref:Microsoft.Office.Tools.Ribbon.RibbonComboBox><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonEditBox>|
|**Ad**|<xref:Microsoft.Office.Tools.Ribbon.RibbonComponent>|
|**Konumu**|<xref:Microsoft.Office.Tools.Ribbon.RibbonButton><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonCheckBox><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonGallery><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonGroup><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonMenu><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonSeparator><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonSplitButton><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonTab><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonToggleButton>|
|**RibbonType**|<xref:Microsoft.Office.Tools.Ribbon.OfficeRibbon>|
|**Satır**|<xref:Microsoft.Office.Tools.Ribbon.RibbonGallery>|
|**ShowItemImage**|<xref:Microsoft.Office.Tools.Ribbon.RibbonComboBox><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonDropDown><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonGallery>|
|**ShowItemLabel**|<xref:Microsoft.Office.Tools.Ribbon.RibbonDropDown><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonGallery>|
|**ShowItemSelection**|<xref:Microsoft.Office.Tools.Ribbon.RibbonGallery>|
|**SizeString**|<xref:Microsoft.Office.Tools.Ribbon.RibbonComboBox><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonDropDown><br /><br /> <xref:Microsoft.Office.Tools.Ribbon.RibbonEditBox>|
|**Startfromkaralama**|<xref:Microsoft.Office.Tools.Ribbon.OfficeRibbon>|
|**Sekmeler**|<xref:Microsoft.Office.Tools.Ribbon.OfficeRibbon>|
|**Başlık**|<xref:Microsoft.Office.Tools.Ribbon.RibbonSeparator>|

### <a name="set-properties-for-ribbons-that-appear-in-outlook-inspectors"></a>Outlook Inspector 'da görünen şeritlerin özelliklerini ayarlama
 Bir Kullanıcı şeridin göründüğü bir Inspector açtığında şeridin yeni bir örneği oluşturulur. Ancak, yukarıdaki tabloda listelenen özellikleri yalnızca şeridin ilk örneği oluşturulmadan önce ayarlayabilirsiniz. İlk örnek oluşturulduktan sonra, ilk örnek Outlook 'un şeridi yüklemek için kullandığı XML dosyasını tanımladığından, bu özellikler salt okunurdur.

 Şerit 'in diğer örnekleri oluşturulduğunda bu özelliklerden herhangi birini farklı bir değere ayarlayan koşullu mantığa sahipseniz, bu kodun hiçbir etkisi olmayacaktır.

> [!NOTE]
> Outlook şeridine eklediğiniz her denetim için **ad** özelliğinin ayarlanmış olduğundan emin olun. Çalışma zamanında Outlook şeridine bir denetim eklerseniz kodunuzda bu özelliği ayarlamanız gerekir. Tasarım zamanında Outlook şeridine bir denetim eklerseniz, Name özelliği otomatik olarak ayarlanır.

## <a name="ribbon-control-events"></a>Şerit denetim olayları
 Her denetim sınıfı bir veya daha fazla olay içerir. Aşağıdaki tabloda bu olaylar açıklanmaktadır.

|Olay|Açıklama|
|-----------|-----------------|
|Şuna tıklayın|Bir denetime tıklandığında gerçekleşir.|
|TextChanged|Bir düzenleme kutusu veya Birleşik giriş kutusunun metni değiştirildiğinde gerçekleşir.|
|Item' yükleme|Denetimin Items koleksiyonu Office tarafından istendiğinde gerçekleşir. Office, kod denetimin özelliklerini değiştirene veya <xref:Microsoft.Office.Core.IRibbonUI.InvalidateControl%2A> yöntemi çağırana kadar öğeler koleksiyonunu önbelleğe alır.|
|Görüntüleyip|<xref:Microsoft.Office.Tools.Ribbon.RibbonGallery> Ya<xref:Microsoft.Office.Tools.Ribbon.RibbonDropDown> da ' de bir düğme tıklandığında gerçekleşir.|
|SelectionChanged|Seçim bir <xref:Microsoft.Office.Tools.Ribbon.RibbonDropDown> veya <xref:Microsoft.Office.Tools.Ribbon.RibbonGallery> değiştiğinde gerçekleşir.|
|DialogLauncherClick|Bir grubun sağ alt köşesindeki iletişim kutusu Başlatıcısı simgesine tıklandığında gerçekleşir.|

 Bu olaylara yönelik olay işleyicileri aşağıdaki iki parametreye sahiptir.

|Parametre|Açıklama|
|---------------|-----------------|
|*Gönderen*|Olayı <xref:System.Object> tetikleyen denetimi temsil eden bir.|
|*e*|<xref:Microsoft.Office.Tools.Ribbon.RibbonControlEventArgs> Bir<xref:Microsoft.Office.Core.IRibbonControl>içerir. Tarafından sağlanan şerit nesne modelinde kullanılamayan herhangi bir özelliğe erişmek için bu denetimi kullanın [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)].|

## <a name="see-also"></a>Ayrıca bkz.
- [Çalışma zamanında Şerite erişin](../vsto/accessing-the-ribbon-at-run-time.md)
- [Şerite Genel Bakış](../vsto/ribbon-overview.md)
- [Nasıl yapılır: Şeriti özelleştirmeye başlama](../vsto/how-to-get-started-customizing-the-ribbon.md)
- [Şerit Tasarımcısı](../vsto/ribbon-designer.md)
- [İzlenecek yol: Şerit Tasarımcısını kullanarak özel sekme oluşturma](../vsto/walkthrough-creating-a-custom-tab-by-using-the-ribbon-designer.md)
- [İzlenecek yol: Çalışma zamanında Şeritteki denetimleri güncelleştirme](../vsto/walkthrough-updating-the-controls-on-a-ribbon-at-run-time.md)
- [Outlook için şerit özelleştirme](../vsto/customizing-a-ribbon-for-outlook.md)
- [Nasıl yapılır: Yerleşik bir sekmeyi özelleştirme](../vsto/how-to-customize-a-built-in-tab.md)
- [Nasıl yapılır: Backstage görünümüne denetimler ekleme](../vsto/how-to-add-controls-to-the-backstage-view.md)
- [Nasıl yapılır: Şerit Tasarımcısından Şerit XML 'ine şerit aktarma](../vsto/how-to-export-a-ribbon-from-the-ribbon-designer-to-ribbon-xml.md)
- [Nasıl yapılır: Eklenti kullanıcı arabirimi hatalarını göster](../vsto/how-to-show-add-in-user-interface-errors.md)
