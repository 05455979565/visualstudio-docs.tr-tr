---
title: 'Nasıl yapılır: yerelleştirilmiş adları, özellikleri ve Izinleri belirtmek için kaynak dosyası kullanma | Microsoft Docs'
ms.date: 02/02/2017
ms.topic: how-to
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Business Data Connectivity service [SharePoint development in Visual Studio], localize strings
- BDC [SharePoint development in Visual Studio], localize strings
- BDC [SharePoint development in Visual Studio], resource file
- Business Data Connectivity service [SharePoint development in Visual Studio], resource strings
- BDC [SharePoint development in Visual Studio], properties
- Business Data Connectivity service [SharePoint development in Visual Studio], properties
- Business Data Connectivity service [SharePoint development in Visual Studio], resource file
- BDC [SharePoint development in Visual Studio], resource strings
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: a87cc8a3eb8f98ea19a87e93c37aae5303151ecf
ms.sourcegitcommit: f9e44f5ab6a1dfb56c945c9986730465e1adb6fc
ms.contentlocale: tr-TR
ms.lasthandoff: 07/06/2020
ms.locfileid: "86015406"
---
# <a name="how-to-use-a-resource-file-to-specify-localized-names-properties-and-permissions"></a>Nasıl yapılır: yerelleştirilmiş adları, özellikleri ve izinleri belirtmek için kaynak dosyası kullanma
  Bir kaynak dosyası kullanarak, yerelleştirilmiş Adlar verebilir, özellikleri tanımlayabilir ve bir Iş verileri bağlantısı (BDC) modelinde tanımlanan nesneleri uygulayabilirsiniz. Bu bilgileri belirtmek için, iş verileri bağlantı **modeli** öğesi içeren bir projeye bir **Iş verileri bağlantısı kaynak** öğesi eklersiniz. Ardından, kaynak dosyasının XML 'sini düzenleyerek adları, özellikleri ve izinleri belirtirsiniz.

### <a name="to-add-a-bdc-resource-file-to-a-sharepoint-project"></a>Bir SharePoint projesine bir BDC kaynak dosyası eklemek için

1. **Çözüm Gezgini**, SharePoint projesinin klasörünü genişletin ve ardından İVB modelini içeren klasörü seçin.

2. Menü çubuğunda, **Proje**  >  **Yeni öğe Ekle**' yi seçin.

3. **SharePoint** düğümünü genişletin ve ardından **2010** düğümünü seçin.

4. **Yeni öğe Ekle** iletişim kutusunda, **Iş verileri bağlantısı kaynak öğesi**' ni seçin.

5. **Ad** kutusunda, kaynak dosyasının adını belirtin ve ardından **Ekle** düğmesini seçin.

     . Bdcr uzantısına sahip bir kaynak dosyası projeye eklenir ve düzenlenmek üzere açılır.

6. IVB modelini uygulamak istediğiniz yerelleştirilmiş adları, özellikleri ve izinleri tanımlamak için XML ekleyin.

     Bu öğelerin nasıl tanımlanacağı hakkında daha fazla bilgi için bkz. [model ve kaynak dosyaları](/previous-versions/office/developer/sharepoint-2010/aa674515(v=office.14)).

## <a name="see-also"></a>Ayrıca bkz.
- [Nasıl yapılır: bir SharePoint projesine mevcut bir BDC modeli dosyası ekleme](../sharepoint/how-to-add-an-existing-bdc-model-file-to-a-sharepoint-project.md)
- [İş verileri bağlantı modeli oluşturma](../sharepoint/creating-a-business-data-connectivity-model.md)
- [Nasıl yapılır: BDC modeli oluşturma](../sharepoint/how-to-create-a-bdc-model.md)
- [Nasıl yapılır: bir BDC özelliğine özel bütünleştirilmiş kod ekleme](../sharepoint/how-to-include-a-custom-assembly-in-a-bdc-feature.md)
- [İş verilerini SharePoint ile tümleştirme](../sharepoint/integrating-business-data-into-sharepoint.md)
