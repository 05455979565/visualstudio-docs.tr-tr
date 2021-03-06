---
title: Outlook form bölgeleri oluşturma yönergeleri
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- form regions [Office development in Visual Studio], guidelines
- icons [Office development in Visual Studio]
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: a962b1ae2bff7b9a954204485a6ee73a3b63eb7b
ms.sourcegitcommit: e98db44f3a33529b0ba188d24390efd09e548191
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/25/2019
ms.locfileid: "71255946"
---
# <a name="guidelines-to-create-outlook-form-regions"></a>Outlook form bölgeleri oluşturma yönergeleri
  Aşağıdaki bilgiler, form bölgelerini iyileştirmenize ve olası sorunları önlemenize yardımcı olabilir:

- [Form bölgesi adlarını kullanın](#UsingFormRegions).

- [Form bölgesi devralmayı devre dışı bırakın](#DisablingInheritance).

- [Türleri ve ileti sınıfı adlarını anlayın](#ClassNames).

- [Okuma bölmesi için bitişik form bölgelerini tasarlayın](#ReadingPane).

- [En iyi simge boyutlarını kullanın](#UsingOptimal).

  Form bölgeleri hakkında daha fazla bilgi için bkz. [Outlook form bölgeleri oluşturma](../vsto/creating-outlook-form-regions.md).

  [!INCLUDE[appliesto_olkallapp](../vsto/includes/appliesto-olkallapp-md.md)]

## <a name="UsingFormRegions"></a>Form bölgesi adlarını kullan
 Form bölgesini anlatmak için kullanılan birkaç ad vardır. Bu adlar ve bunların form bölgesini nasıl etkilediği arasındaki farkı anlamak önemlidir. Aşağıdaki tabloda her bir ad açıklanmaktadır.

|Form bölgesi adı|Açıklama|
|----------------------|-----------------|
|Form bölgesi öğe adı|**Yeni öğe Ekle** Iletişim kutusunda **Outlook form bölgesi** öğesi için belirttiğiniz addır. Bu, **Çözüm Gezgini**görüntülenen form bölgesi kod dosyasının adıdır.|
|<xref:Microsoft.Office.Tools.Outlook.FormRegionManifest.FormRegionName%2A>özelliði|Bu adı açıklayıcı metin olarak belirtin ve **Yeni Outlook form bölgesi** Sihirbazı ' nın **görüntüleme tercihlerini seçin** . Bu ad, **Özellikler** penceresinde **FormRegionName** özelliği olarak görünür.<br /><br /> Outlook Kullanıcı arabiriminde (UI) form bölgesini tanımlayan etiketi belirtmek için özelliğinikullanın.<xref:Microsoft.Office.Tools.Outlook.FormRegionManifest.FormRegionName%2A> Ayrı form bölgelerinde, bu ad Outlook öğesi şeridinde bir düğme olarak görünür.<br /><br /> Bitişik form bölgeleri için bu ad, form bölgesinin üstünde başlık metni olarak görünür.|
|`Microsoft.Office.Tools.Outlook.FormRegionName`özniteliğe|Projeye bir **Outlook form bölgesi** öğesi eklediğinizde, Visual Studio bu özelliği form bölgesinin tam adı olarak ayarlar. Varsayılan tam adı, form bölgesinin adına bir noktayla bağlı olan VSTO eklentisinin adıdır — Örneğin, `OutlookAddIn1.FormRegion1`.<br /><br /> Bu tam ad, form bölgesi fabrikası sınıfının en üstünde bir öznitelik olarak da görünür.<br /><br /> Form bölgesini tüm Outlook VSTO eklentileri genelinde benzersiz olarak tanımlamak için özniteliğinikullanın.`Microsoft.Office.Tools.Outlook.FormRegionName` Form bölgesi öğesini yeniden adlandırarak veya `Microsoft.Office.Tools.Outlook.FormRegionName` <xref:Microsoft.Office.Tools.Outlook.FormRegionManifest.FormRegionName%2A> özelliğini değiştirerek özniteliğin değerini değiştiremezsiniz. Bu adı değiştirmek için, form bölgesi kod dosyasındaki `Microsoft.Office.Tools.Outlook.FormRegionName` özniteliğini değiştirmelisiniz.|

## <a name="DisablingInheritance"></a>Form bölgesi devralmayı devre dışı bırak
 Varsayılan olarak, özel bir ileti sınıfı, temel ileti sınıfının tüm form bölge ilişkilendirmelerini devralır. Örneğin, öğesinden `IPM.Task.Contoso` `IPM.Task`türetilir adlı bir ileti sınıfı. Bu nedenle `IPM.Task.Contoso` , öğesinin `IPM.Task`form bölgesi ilişkilendirmelerini devralır.

 Form bölgesinin herhangi bir türetilmiş ileti sınıfıyla ilişkilendirilmesini istemiyorsanız form bölgesinin <xref:Microsoft.Office.Tools.Outlook.FormRegionManifest.ExactMessageClass%2A> özelliğini **true**olarak ayarlayın. Örneğin, bitişik bir form bölgesini ile `IPM.Task` ilişkilendirir ve <xref:Microsoft.Office.Tools.Outlook.FormRegionManifest.ExactMessageClass%2A> özelliğini **true**olarak ayarlarsanız form bölgesi yalnızca standart görev formunun alt kısmına eklenir. Form bölgesi, standart görev formunun özelleştirilmiş herhangi bir sürümünün alt kısmına eklenmez.

## <a name="ClassNames"></a>Türleri ve ileti sınıfı adlarını anlayın
 Outlook öğesinin tür adı, Outlook öğesinin ileti sınıfı adından farklıdır. Örneğin, bir RSS öğesinin `Microsoft.Office.Interop.Outlook.PostItem`tür adı. Bir RSS öğesinin `IPM.Post.RSS`ileti sınıfı adı.

 Koddaki bir Outlook öğesine başvurmak için tür adını kullanın. Tür adlarının bir listesi için bkz. [form bölgesini bir Outlook ileti sınıfıyla ilişkilendirme](../vsto/associating-a-form-region-with-an-outlook-message-class.md).

 Öğeyi form bölgesiyle ilişkilendirmek için **Yeni Outlook form bölgesi** Sihirbazı ' nda Outlook öğelerinin ileti sınıfı adını kullanın. Geçerli ileti sınıfı adlarının bir listesi için bkz. [form bölgesini bir Outlook ileti sınıfıyla ilişkilendirme](../vsto/associating-a-form-region-with-an-outlook-message-class.md).

## <a name="ReadingPane"></a>Okuma bölmesi için bitişik form bölgelerini tasarlama
 Outlook okuma bölmesini kullanarak bir Outlook öğesinin öğeyi açmadan önizlemesini yapabilirsiniz. Okuma bölmesi yalnızca okuma için tasarlanmıştır. Bu nedenle, metin kutusu gibi bitişik form bölgesine eklediğiniz giriş denetimleri, öğe ve form bölgesi okuma bölmesinde açıldığında beklendiği gibi davranmayabilir.

 Örneğin, bitişik form bölgesine sahip bir öğe okuma bölmesinde açıksa, aşağıdaki durum mümkündür:

1. Form bölgesindeki bir metin kutusunda bazı metni seçin.

2. **Sil**'e basın.

3. TextBox içindeki metin yerine tüm posta öğesi silinir.

   Giriş denetimleri içeren bitişik bir form bölgesi tasarlıyorsanız, düzgün şekilde çalışmasını sağlamak için denetimleri okuma bölmesinde test edin. Beklenen şekilde davranmayan denetimleri devre dışı bırakan özel kod eklemeyi düşünün.

   Alternatif olarak, form bölgesinin <xref:Microsoft.Office.Tools.Outlook.FormRegionManifest.ShowInspectorRead%2A> özelliğini **false**olarak ayarlayabilirsiniz. Bu şekilde, form bölgesi okuma bölmesinde kullanılamaz.

## <a name="UsingOptimal"></a>En iyi simge boyutlarını kullan
 Form bölgesinin, **Özellikler** penceresinin **simgeler** özellik grubundaki simge özelliklerini ayarlayarak hangi simgeleri görüntülemesini istediğinizi belirtebilirsiniz. En iyi görsel kaliteyi elde etmek için aşağıdaki yönergeleri kullanın:

- **Sayfa** simgesi Için Taşınabilir Ağ GRAFIKLERI (png) dosyası kullanın.

- **Pencere** simgeleri 32 piksel 32 piksel olmalıdır.

- Diğer tüm simgeler 16 piksel 16 piksel olmalıdır.

  **Sayfa** simgesi, ayrı, değiştirme veya değiştirme formu bölgeleri olan öğeler Için bir Inspector şeridinde görüntülenir.

  **Pencere** simgesi, bildirim alanında ve değiştirme veya değiştirme-tüm form bölgelerini görüntüleyen açık öğeler için **alt**+**sekme** iletişim kutusunda görünür.

## <a name="see-also"></a>Ayrıca bkz.
- [Çalışma zamanında form bölgesine erişme](../vsto/accessing-a-form-region-at-run-time.md)
- [Outlook form bölgeleri oluşturma](../vsto/creating-outlook-form-regions.md)
- [İzlenecek yol: Outlook form bölgesi tasarlama](../vsto/walkthrough-designing-an-outlook-form-region.md)
- [Nasıl yapılır: Outlook eklenti projesine form bölgesi ekleme](../vsto/how-to-add-a-form-region-to-an-outlook-add-in-project.md)
- [Form bölgesini Outlook ileti sınıfıyla ilişkilendirme](../vsto/associating-a-form-region-with-an-outlook-message-class.md)
