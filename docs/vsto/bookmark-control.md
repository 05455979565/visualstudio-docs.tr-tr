---
title: Yer işareti denetimi
ms.date: 02/02/2017
ms.topic: conceptual
f1_keywords:
- VST.Toolbox.Bookmark
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- bookmarks, controlling
- Bookmark control, data binding
- Bookmark control, events
- Bookmark control
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 2b8557581e93c8d2ba5a54a13c04d5de74b24f71
ms.sourcegitcommit: e98db44f3a33529b0ba188d24390efd09e548191
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/25/2019
ms.locfileid: "71255143"
---
# <a name="bookmark-control"></a>Yer işareti denetimi
  <xref:Microsoft.Office.Tools.Word.Bookmark> Denetim, benzersiz bir ada sahip, olayları ortaya çıkaran ve verilere bağlanabilen bir yer işaretidir. Yer işareti, bir Microsoft Office Word belgesindeki bir öğeyi veya konumu işaretlemek için yer tutucu olarak kullanılabilir. Denetim bir <xref:Microsoft.Office.Interop.Word.Bookmark> nesne ve<xref:Microsoft.Office.Interop.Word.Range>nesnebirleşimidir. <xref:Microsoft.Office.Tools.Word.Bookmark>

 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]

 Belge düzeyi projelerinde, tasarım zamanında veya çalışma zamanında <xref:Microsoft.Office.Tools.Word.Bookmark> belgenize denetim ekleyebilirsiniz. VSTO eklenti projelerinde, çalışma zamanında herhangi bir açık belgeye <xref:Microsoft.Office.Tools.Word.Bookmark> denetimler ekleyebilirsiniz. Daha fazla bilgi için [nasıl yapılır: Word belgelerine](../vsto/how-to-add-bookmark-controls-to-word-documents.md)Bookmark denetimleri ekleyin.

## <a name="bind-data-to-the-control"></a>Verileri denetime bağlama
 Bir <xref:Microsoft.Office.Tools.Word.Bookmark> denetim basit veri bağlamayı destekler. Yer işareti, <xref:System.Windows.Forms.IBindableComponent.DataBindings%2A> özelliği kullanılarak bir veri kaynağına bağlanmalıdır. Yer işaretinin <xref:Microsoft.Office.Tools.Word.Bookmark.Text%2A> varsayılan veri bağlama özelliği özelliğidir.

 Bağlantılı veri kümesindeki veriler güncelleştirilirse, <xref:Microsoft.Office.Tools.Word.Bookmark> denetimde değişiklikler gösterilir.

 Belge düzeyi projelerde veri **kaynakları** penceresini kullanarak verileri yer işaretlerine de bağlayabilirsiniz. Daha fazla bilgi için [nasıl yapılır: Belgeleri nesnelerdeki](../vsto/how-to-populate-documents-with-data-from-objects.md)verilerle doldurun.

## <a name="formatting"></a>Biçimlendirme
 Bir <xref:Microsoft.Office.Interop.Word.Bookmark> <xref:Microsoft.Office.Tools.Word.Bookmark> denetime uygulanabilen biçimlendirme, bir denetime uygulanabilir. Bu biçimlendirme yazı tiplerini, girintileri, aralığı, numaralandırmayı ve stilleri içerir.

## <a name="assign-text-to-the-bookmark"></a>Yer işaretine metin ata
 Bir <xref:Microsoft.Office.Interop.Word.Bookmark?displayProperty=nameWithType> nesne ve bir <xref:Microsoft.Office.Tools.Word.Bookmark?displayProperty=nameWithType> denetim arasındaki ek bir farklılık, metin yer işaretine atandığında nasıl davranacağını gösterir. Sıfır uzunlukta <xref:Microsoft.Office.Interop.Word.Bookmark?displayProperty=nameWithType>metin atarsanız, metin yer işaretinin sağına eklenir ve yer işareti sıfır uzunlukta kalır. Ancak, sıfır uzunluklu <xref:Microsoft.Office.Tools.Word.Bookmark?displayProperty=nameWithType>metin atarsanız, metin yer işaretine eklenir ve yer işaretinin uzunluğu, takılan toplam karakter sayısına genişletilir.

 <xref:Microsoft.Office.Tools.Word.Bookmark?displayProperty=nameWithType> Denetimin <xref:Microsoft.Office.Tools.Word.Bookmark.Text?displayProperty=nameWithType> özelliği de vardır. Bu <xref:Microsoft.Office.Interop.Word.Range.Text?displayProperty=nameWithType> özellik, bir<xref:Microsoft.Office.Tools.Word.Bookmark?displayProperty=nameWithType>denetimin <xref:Microsoft.Office.Tools.Word.Bookmark.Range?displayProperty=nameWithType> özelliği veya bir <xref:Microsoft.Office.Interop.Word.Bookmark?displayProperty=nameWithType> nesnenin özelliğiüzerindekullanılabilir<xref:Microsoft.Office.Interop.Word.Bookmark.Range?displayProperty=nameWithType> olan özellikten farklıdır.

|Text özelliği|Açıklama|
|-------------------|-----------------|
|<xref:Microsoft.Office.Tools.Word.Bookmark.Text?displayProperty=nameWithType>|Yer işareti içindeki metni göstermek ve yer işaretini belgede bırakmak için bu özelliği kullanın. Yer işaretine metin atama, yer işareti aralığını genişletir ve yer işaretini silmez.<br /><br /> Örneğin, metni `Bookmark1.Text = "Hello world"` yer işaretine ekler ve yer işaretini dokunulmamış olarak bırakır.|
|<xref:Microsoft.Office.Interop.Word.Range.Text?displayProperty=nameWithType>|Yer işareti konumundaki metni göstermek ve yer işaretini otomatik olarak silmek için bu özelliği kullanın. Örneğin, `Bookmark1.Range.Text = "Hello world"` metni yer işaretine ekler ve yer işaretini siler.|

## <a name="rename-the-control-at-design-time"></a>Tasarım zamanında denetimi yeniden adlandırma
 Belge düzeyi projelerde, bir <xref:Microsoft.Office.Tools.Word.Bookmark> denetimi **araç kutusundan** belgenize sürüklediğinizde, Visual Studio otomatik olarak denetim için bir ad oluşturur. Denetimin adını **Özellikler** penceresinde değiştirebilirsiniz.

## <a name="overlapping-controls"></a>Çakışan denetimler
 Yer işareti denetimleri birbirini örtüşebilir. Aynı metin birden fazla yer işareti tarafından paylaşılabilir. Çakışan yer işaretlerinin birine yeni metin atadığınızda, bu yalnızca yeni metni içerir ve yer işaretleri artık çakışmayacaktır. Diğer yer işareti artık yalnızca özgün çakışan yer işaretleri arasında paylaşılmayan metni içerir.

 Aşağıdaki tabloda, "Bunun örnek metin olan" tümcesi gösterilmektedir. iki çakışan yer işareti tarafından paylaşılır:

|Yer işareti|Metin|
|--------------|----------|
|Çakışan yer işaretleri|[Bu {Sample] metindir.}|
|Bookmark1|Bu örnek|
|Bookmark2|örnek metin.|

 Yeni metni atarsanız "Bu değişiklik." Bookmark1 için, yer işaretleri örtüşmez ve bookmark2 yalnızca özgün olarak Bookmark1 bölümü olmayan metni korur.

|Yer işareti|Metin|
|--------------|----------|
|İki ayrı yer işareti|[Bu değişiklik.] {Text.}|
|Bookmark1|Bu değişiklik|
|Bookmark2|metinleri.|

Başka bir yer işareti içeren bir yer işaretinin metnini değiştirirseniz, iç yer işareti silinmez. Ancak, iç yer işareti boş bir yer işaretine dönüşür ve dış yer işaretinin sonuna gider.

Aşağıdaki tabloda, "Bunun örnek metin olan" tümcesi gösterilmektedir. , başka bir yer işareti içinde yer alan bir yer işareti tarafından paylaşılır:

|Yer işareti|Metin|
|--------------|----------|
|Çakışan yer işaretleri|[Bu {Sample} metindir.]|
|Bookmark1|Bu örnek metindir.|
|Bookmark2|örnek|

 Yeni metni atarsanız "Bu değişiklik." Bookmark1 için, yer işaretleri artık örtüşmemelidir ve bookmark2 Bookmark1 sonunda yer alan boş bir yer işareti haline gelir.

|Yer işareti|Metin|
|--------------|----------|
|İki ayrı yer işareti|[Bu değişiklik.]{}|
|Bookmark1|Bu değişiklik.|
|Bookmark2|*\<Boş >*|

## <a name="events"></a>Olaylar

<xref:Microsoft.Office.Tools.Word.Bookmark> Denetim için aşağıdaki olaylar mevcuttur:

- <xref:Microsoft.Office.Tools.Word.Bookmark.BeforeDoubleClick>

- <xref:Microsoft.Office.Tools.Word.Bookmark.BeforeRightClick>

- <xref:Microsoft.Office.Tools.Word.Bookmark.BindingContextChanged>

- <xref:Microsoft.Office.Tools.Word.Bookmark.Deselected>

- <xref:System.ComponentModel.IComponent.Disposed>

- <xref:Microsoft.Office.Tools.Word.Bookmark.Selected>

- <xref:Microsoft.Office.Tools.Word.Bookmark.SelectionChange>

## <a name="see-also"></a>Ayrıca bkz.

- [Genişletilmiş nesneleri kullanarak Word 'Ü otomatikleştirme](../vsto/automating-word-by-using-extended-objects.md)
- [Nasıl yapılır: Word belgelerine yer Işareti denetimleri ekleme](../vsto/how-to-add-bookmark-controls-to-word-documents.md)
- [İzlenecek yol: Yer işaretleri için kısayol menüleri oluşturma](../vsto/walkthrough-creating-shortcut-menus-for-bookmarks.md)
- [Office çözümlerinde verileri denetimlere bağlama](../vsto/binding-data-to-controls-in-office-solutions.md)
- [Konak öğelerinin ve konak denetimlerinin programlama sınırlamaları](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)