---
title: Arama veri bağlamayı destekleyen bir Windows Forms Kullanıcı denetimi oluşturun | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-data-tools
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
- aspx
helpviewer_keywords:
- data binding, user controls
- LookupBindingPropertiesAttribute class, examples
- user controls [Visual Basic], creating
ms.assetid: c48b4d75-ccfc-4950-8b14-ff8adbfe4208
caps.latest.revision: 18
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 48891f82667270f04af49c60122c63f8d3a943f7
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72668785"
---
# <a name="create-a-windows-forms-user-control-that-supports-lookup-data-binding"></a>Arama veri bağlama modelini destekleyen bir Windows Forms kullanıcı denetimi oluşturma
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Windows Forms verileri görüntülerken, **araç kutusundan**var olan denetimleri seçebilir veya uygulamanız standart denetimlerde kullanılamayan işlevselliği gerektiriyorsa özel denetimleri yazabilirsiniz. Bu izlenecek yol, <xref:System.ComponentModel.LookupBindingPropertiesAttribute> uygulayan bir denetimin nasıl oluşturulacağını gösterir. @No__t_0 uygulayan denetimler, verilere bağlanabilen üç özellik içerebilir. Bu tür denetimler <xref:System.Windows.Forms.ComboBox> benzerdir.

 Denetim yazma hakkında daha fazla bilgi için bkz. [tasarım zamanında Windows Forms denetimleri geliştirme](https://msdn.microsoft.com/library/e5a8e088-7ec8-4fd9-bcb3-9078fd134829).

 Veri bağlama senaryolarında kullanılacak denetimleri yazma sırasında, aşağıdaki veri bağlama özniteliklerinden birini uygulamanız gerekir:

|Veri bağlama özniteliği kullanımı|
|-----------------------------------|
|Verilerin tek bir sütununu (veya özelliği) görüntüleyen <xref:System.Windows.Forms.TextBox> gibi basit denetimlerde <xref:System.ComponentModel.DefaultBindingPropertyAttribute> uygulayın. Daha fazla bilgi için bkz. [basit veri bağlamayı destekleyen Windows Forms Kullanıcı denetimi oluşturma](../data-tools/create-a-windows-forms-user-control-that-supports-simple-data-binding.md).|
|Denetimlerin listesini (veya tabloları) görüntüleyen <xref:System.Windows.Forms.DataGridView> gibi denetimlerde <xref:System.ComponentModel.ComplexBindingPropertiesAttribute> uygulayın. Daha fazla bilgi için bkz. [karmaşık veri bağlamayı destekleyen Windows Forms Kullanıcı denetimi oluşturma](../data-tools/create-a-windows-forms-user-control-that-supports-complex-data-binding.md).|
|@No__t_0, verilerin listelerini (veya tabloları) görüntüleyen, ancak tek bir sütun veya özellik sunmanız gereken <xref:System.Windows.Forms.ComboBox> gibi denetimlerde uygulayın. (Bu işlem Bu izlenecek yol sayfasında açıklanmaktadır.)|

 Bu izlenecek yol, iki tablodaki verilere bağlanan bir arama denetimi oluşturur. Bu örnekte, Northwind örnek veritabanındaki `Customers` ve `Orders` tabloları kullanılmaktadır. Arama denetimi `Orders` tablosundan `CustomerID` alanına bağlanacak. @No__t_1 tablosundan `CompanyName` aramak için bu değeri kullanır.

 Bu izlenecek yol sırasında şunları yapmayı öğreneceksiniz:

- Yeni bir **Windows uygulaması**oluşturun.

- Projenize yeni bir **Kullanıcı denetimi** ekleyin.

- Kullanıcı denetimini görsel olarak tasarlayın.

- @No__t_0 özniteliğini uygulayın.

- **Veri kaynağı yapılandırma** Sihirbazı ile bir veri kümesi oluşturun.

- Yeni denetimi kullanmak için, **veri kaynakları** penceresinde **Orders** tablosundaki **CustomerID** sütununu ayarlayın.

- Yeni denetimdeki verileri göstermek için bir form oluşturun.

## <a name="prerequisites"></a>Prerequisites
 Bu izlenecek yolu tamamlamak için şunlar gerekir:

- Northwind örnek veritabanına erişim.

## <a name="create-a-windows-application"></a>Windows uygulaması oluşturma
 İlk adım bir **Windows uygulaması**oluşturmaktır.

#### <a name="to-create-the-new-windows-project"></a>Yeni Windows projesi oluşturmak için

1. Visual Studio 'da, **Dosya** menüsünden Yeni bir **Proje**oluşturun.

2. Projeyi **LookupControlWalkthrough**olarak adlandırın.

3. **Windows Forms uygulama**' yı seçin ve **Tamam**' ı tıklatın.

     **LookupControlWalkthrough** projesi oluşturulur ve **Çözüm Gezgini**eklenir.

## <a name="add-a-user-control-to-the-project"></a>Projeye Kullanıcı denetimi Ekle
 Bu izlenecek yol, **Kullanıcı denetiminden**bir arama denetimi oluşturur, bu nedenle **LookupControlWalkthrough** projesine bir **Kullanıcı denetim** öğesi ekleyin.

#### <a name="to-add-a-user-control-to-the-project"></a>Projeye Kullanıcı denetimi eklemek için

1. **Proje** menüsünden **Kullanıcı denetimi Ekle**' yi seçin.

2. **Ad** alanına `LookupBox` yazın ve ardından **Ekle**' ye tıklayın.

     **LookupBox** denetimi **Çözüm Gezgini**eklenir ve tasarımcıda açılır.

## <a name="design-the-lookupbox-control"></a>LookupBox denetimini tasarlama

#### <a name="to-design-the-lookupbox-control"></a>LookupBox denetimini tasarlamak için

- **Araç kutusundan** bir <xref:System.Windows.Forms.ComboBox> Kullanıcı denetiminin tasarım yüzeyine sürükleyin.

## <a name="add-the-required-data-binding-attribute"></a>Gerekli veri bağlama özniteliğini ekleyin
 Veri bağlamayı destekleyen arama denetimleri için <xref:System.ComponentModel.LookupBindingPropertiesAttribute> uygulayabilirsiniz.

#### <a name="to-implement-the-lookupbindingproperties-attribute"></a>LookupBindingProperties özniteliğini uygulamak için

1. **LookupBox** denetimini kod görünümüne geçirin. ( **Görünüm** menüsünde **kod**öğesini seçin.)

2. @No__t_0 kodundaki kodu aşağıdaki kodla değiştirin:

     [!code-csharp[VbRaddataDisplaying#5](../snippets/csharp/VS_Snippets_VBCSharp/VbRaddataDisplaying/CS/LookupBox.cs#5)]
     [!code-vb[VbRaddataDisplaying#5](../snippets/visualbasic/VS_Snippets_VBCSharp/VbRaddataDisplaying/VB/LookupBox.vb#5)]

3. **Build** menüsünde **Build Solution**öğesini seçin.

## <a name="create-a-data-source-from-your-database"></a>Veritabanınızdan bir veri kaynağı oluşturun
 Bu adım, Northwind örnek veritabanındaki `Customers` ve `Orders` tablolarına göre **veri kaynağı yapılandırma** Sihirbazı 'nı kullanarak bir veri kaynağı oluşturur. Bağlantıyı oluşturmak için Northwind örnek veritabanına erişiminizin olması gerekir. Northwind örnek veritabanını ayarlama hakkında daha fazla bilgi için bkz. [ınstall SQL Server Sample Databases](../data-tools/install-sql-server-sample-databases.md).

#### <a name="to-create-the-data-source"></a>Veri kaynağı oluşturmak için

1. **Veri** menüsünde **veri kaynaklarını göster**' e tıklayın.

2. Veri **kaynakları** penceresinde, **veri kaynağı yapılandırma** Sihirbazı ' nı başlatmak Için **Yeni veri kaynağı Ekle** ' yi seçin.

3. **Veri kaynağı türü seçin** sayfasında **veritabanı** ' nı seçin ve ardından **İleri**' ye tıklayın.

4. **Veri bağlantınızı seçin** sayfasında aşağıdakilerden birini yapın:

    - Northwind örnek veritabanıyla kurulan veri bağlantısı aşağı açılan listede kullanılabilir durumdaysa bunu seçin.

    - **Yeni bağlantı** ' yı seçerek **Bağlantı Ekle/Değiştir** iletişim kutusunu başlatın.

5. Veritabanınız parola gerektiriyorsa, hassas verileri dahil etme seçeneğini belirleyin ve ardından **İleri**' ye tıklayın.

6. **Bağlantı dizesini uygulama yapılandırma dosyasına kaydet** sayfasında, **İleri**' ye tıklayın.

7. **Veritabanı nesnelerinizi seçin** sayfasında **Tablolar** düğümünü genişletin.

8. @No__t_0 ve `Orders` tablolarını seçip **son**' a tıklayın.

     **NorthwindDataSet** , projenize eklenir ve `Customers` ve `Orders` tabloları **veri kaynakları** penceresinde görünür.

## <a name="set-the-customerid-column-of-the-orders-table-to-use-the-lookupbox-control"></a>LookupBox denetimini kullanmak için Orders tablosunun CustomerID sütununu ayarlayın
 **Veri kaynakları** penceresinde, öğeleri formunuza sürüklemeden önce oluşturulacak denetimi ayarlayabilirsiniz.

#### <a name="to-set-the-customerid-column-to-bind-to-the-lookupbox-control"></a>MüşteriNo sütununu LookupBox denetimine bağlanacak şekilde ayarlamak için

1. Tasarımcıda **Form1** ' i açın.

2. **Veri kaynakları** penceresindeki **müşteriler** düğümünü genişletin.

3. **Orders** düğümünü ( **Faks** sütununun altındaki **müşteriler** düğümünde bir düğüm) genişletin.

4. **Siparişler** düğümündeki açılan oka tıklayın ve denetim listesinden **Ayrıntılar** ' ı seçin.

5. **MüşteriNo** sütunundaki açılan oka tıklayın ( **siparişler** düğümünde) ve **Özelleştir**' i seçin.

6. **Veri Kullanıcı arabirimi özelleştirme seçenekleri** Iletişim kutusunda **Ilişkili denetimler** listesinden **LookupBox** ' ı seçin.

7. **Tamam**'a tıklayın.

8. **MüşteriNo** sütunundaki açılan oka tıklayın ve **LookupBox**' ı seçin.

## <a name="addcontrols-to-the-form"></a>Form için addcontrols
 Veri **kaynakları** penceresinden **Form1**üzerine sürükleyerek veri bağlantılı denetimleri oluşturabilirsiniz.

#### <a name="to-create-data-bound-controls-on-the-windows-form"></a>Windows formunda veriye bağlı denetimler oluşturmak için

- **Veri kaynakları** penceresinden **Orders** düğümünü Windows form üzerine sürükleyin ve **arama kutusu** denetiminin `CustomerID` sütununda verileri göstermek için kullanıldığını doğrulayın.

## <a name="bind-the-control-to-look-up-companyname-from-the-customers-table"></a>Müşteriler tablosundan ara CompanyName 'e denetim bağlama

#### <a name="to-setup-the-lookup-bindings"></a>Arama bağlamalarını ayarlamak için

- **Veri kaynakları** penceresinde ana **müşteriler** düğümünü seçin ve **Form1'in**içindeki **CustomerIDLookupBox** içindeki Birleşik giriş kutusuna sürükleyin.

     Bu, `Orders` tablosundan `CustomerID` değerini koruyarak `Customers` tablosundan `CompanyName` göstermek üzere veri bağlamayı ayarlar.

## <a name="running-the-application"></a>Uygulamayı çalıştırma

#### <a name="to-run-the-application"></a>Uygulamayı çalıştırmak için

- Uygulamayı çalıştırmak için F5 tuşuna basın.

- Bazı kayıtlar arasında ilerleyin ve `CompanyName` `LookupBox` denetiminde göründüğünü doğrulayın.

## <a name="see-also"></a>Ayrıca Bkz.
 [Visual Studio'da verilere Windows Forms denetimleri bağlama](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)
