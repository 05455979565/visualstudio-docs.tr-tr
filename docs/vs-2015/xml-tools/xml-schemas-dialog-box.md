---
title: XML şemaları iletişim kutusu | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0271fa26-2205-49bd-96e0-ae1441571808
caps.latest.revision: 9
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 9d388dc928b2f15c084034831a4b05f9d6420a65
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42675219"
---
# <a name="xml-schemas-dialog-box"></a>XML Şemaları İletişim Kutusu
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [XML şemaları iletişim kutusu](https://docs.microsoft.com/visualstudio/xml-tools/xml-schemas-dialog-box).  
  
  
**XML şemaları** iletişim kutusu, bir XML belgesi ile ilişkilendirmek için hangi XML Şeması Tanım Dili (XSD) şeması/şemaları seçmek için kullanılır. Şema önbelleğinden bir şema seçin veya önbelleğinde bulunmayan bir şema belirtin. Seçili şemaları şema kümesinin bir parçası olarak kabul edilir. Şema kümesi, IntelliSense ve ayrıca XML belgesi doğrulama için kullanılır.  
  
 Erişebildiğiniz **XML şemaları** ya tıklayarak iletişim kutusunu **şemaları** düğmesini seçerek veya belge Özellikler penceresinde **şemaları** gelen**XML** menüsü.  
  
## <a name="uielement-list"></a>UIElement Listesi  
 **Kullanın**  
 XML Şeması nasıl kullanıldığının seçin.  
  
-   **Otomatik**. Bu şema geçerli belgede tarafından'kullanımda değildir, ancak otomatik ilişkilendirmesi için kullanılabilir. XML belgesi eşleşen bir ad alanı bildirirse `targetNamespace` bu şema şema otomatik olarak ilişkilendirilir ve şema kümesindeki dahil edilir.  
  
-   **Bu şemayı kullan**. Bu şemayı geçerli belgede tarafından kullanılıyor. Açıkça ya da kullanıcının sahip olduğu bu sütuna tıklayarak bu şema kullanılması istenen veya şema eşleşmesi temeline göre otomatik olarak ilişkili `targetNamespace`.  
  
-   **Seçili şemaları kullanma**. Eşleşen bir şemaya sahip olsa bile bu şemayı geçerli belgede tarafından kullanılmaz `targetNamespace`. Bu ayar şema önbelleği veya çözüm aynı şemaya yönelik birden fazla sürümü olduğunda çakışmaları çözümlemek için yararlı olabilir.  
  
 **Target Namespace**  
 XML şeması ile ilişkili hedef ad alanı görüntüler.  
  
 **Dosya adı**  
 XML Şeması dosya adını görüntüler.  
  
 **Ekle**  
 Açılır **açık XSD şeması** form veya iletişim şema kümesine eklenecek ek şemaları seçmenize olanak sağlar. Şema için bir şema eklediğinizde ayarlayın, **kullanım** sütun değeri ayarı **Bu şemayı kullan**.  
  
 **Kaldır**  
 Şu anda seçili şeması, şema kümeden kaldırır. Bu, bellek içi şema önbelleğinden ancak dosya sisteminden şemayı kaldırır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [XML Düzenleyicisi bileşenleri](../xml-tools/xml-editor-components.md)   
 [Nasıl yapılır: XML şemalarını seçme](../xml-tools/how-to-select-the-xml-schemas-to-use.md)   
 [Şema Önbelleği](../xml-tools/schema-cache.md)



