---
title: Proje ve öğe şablonları oluşturma | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- templates [Visual Studio], projects
- item templates, about item templates
- templates [Visual Studio], item
- Visual Studio templates, item
- Visual Studio templates, about templates
- project templates [Visual Studio], about project templates
- Visual Studio templates, project
- templates [Visual Studio], about templates
ms.assetid: a6ce501a-699b-4e3e-ade8-c81895645c20
caps.latest.revision: 12
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 995696dafce64cdcb1fbb11d0788bbe13453c440
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72619296"
---
# <a name="creating-project-and-item-templates"></a>Proje ve Öğe Şablonları Oluşturma
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../includes/vsprvs-md.md)] proje ve öğe şablonları, kullanıcılara kendi amaçları doğrultusunda kullanabilecekleri bazı temel kodları ve yapıları veren yeniden kullanılabilir saplamalar sağlar.

## <a name="visual-studio-templates"></a>Visual Studio şablonları
 @No__t_0 yüklediğinizde, bir dizi önceden tanımlanmış proje ve öğe şablonu yüklenir. **Yeni proje** iletişim kutusunda bulunan [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] ve [!INCLUDE[csprcs](../includes/csprcs-md.md)] Windows Forms uygulama ve sınıf kitaplığı şablonları proje şablonlarının örnekleridir. Yüklenen öğe şablonları, **Yeni öğe Ekle** iletişim kutusunda kullanılabilir ve kod dosyaları, XML dosyaları, HTML sayfaları ve stil sayfaları gibi öğeleri içerir.

 Bu şablonlar, kullanıcıların proje oluşturmaya veya geçerli projeleri genişletmesinin başlaması için bir başlangıç noktası sağlar. Proje şablonları, belirli bir proje türü için gereken dosyaları sağlar, standart derleme başvurularını dahil eder ve varsayılan proje özelliklerini ve derleyici seçeneklerini ayarlar. Öğe şablonları, örneğin, saplama kodu, tasarımcı bilgi dosyaları ve katıştırılmış kaynakları içeren kaynak kodu dosyaları gibi, doğru dosya adı uzantısına sahip olan tek bir boş dosyanın karmaşıklık halinde değişebilir.

 **Yeni proje** ve **Yeni öğe Ekle** iletişim kutularında yüklü şablonlara ek olarak, kendi şablonlarınızı yazabilir veya topluluk tarafından oluşturulan şablonları indirebilir veya kullanabilirsiniz. Daha fazla bilgi için bkz. [nasıl yapılır: proje şablonları oluşturma](../ide/how-to-create-project-templates.md) ve [nasıl yapılır: öğe şablonları oluşturma](../ide/how-to-create-item-templates.md).

## <a name="contents-of-a-template"></a>Şablonun içeriği
 Tüm proje ve öğe şablonları, [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] ile birlikte yüklenip oluşturulıp aynı ilkeleri kullanarak ve benzer içeriğe sahip olacak şekilde çalışır. Tüm şablonlar aşağıdaki öğeleri içerir:

- Şablon kullanıldığında oluşturulacak dosyalar. Bu kaynak kod dosyalarını, katıştırılmış kaynakları, proje dosyalarını vb. içerir.

- Tek bir. vstemplate dosyası. Bu dosya, şablonu **Yeni proje** ve **Yeni öğe Ekle** iletişim kutularında göstermek ve şablondan bir proje ya da öğe oluşturmak için gereken bilgileri [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] sağlayan meta verileri içerir. . Vstemplate dosyaları hakkında daha fazla bilgi için bkz. [şablon parametreleri](../ide/template-parameters.md).

  Bu dosyalar bir. zip dosyasında sıkıştırıldığında ve doğru klasöre yerleştirıldığında, [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] onları otomatik olarak görüntüler. Proje şablonları **Yeni proje** Iletişim kutularının **Şablonlarım** bölümünde görünür ve öğe şablonları **Yeni öğe Ekle** iletişim kutularında görünür. Şablon klasörleri hakkında daha fazla bilgi için bkz. [nasıl yapılır: şablonları bulma ve düzenleme](../ide/how-to-locate-and-organize-project-and-item-templates.md).

## <a name="starter-kits"></a>Başlangıç Paketleri
 Başlangıç setleri, topluluğun diğer üyeleriyle paylaşılabilen gelişmiş şablonlardır. Bir Starter Kit, kullanıcıların yararlı ve gerçek dünyada uygulamalar oluştururken yeni araçlar ve programlama teknikleri öğrenmesine yardımcı olmak üzere derleme, belge ve diğer kaynakları oluşturan kod örnekleri içerir. Başlangıç setleri için temel içerik ve yordamlar şablonlarla aynıdır. Daha fazla bilgi için bkz. [nasıl yapılır: Başlangıç setleri oluşturma](../ide/how-to-create-starter-kits.md).

## <a name="see-also"></a>Ayrıca Bkz.
 [Nasıl yapılır: proje şablonları oluşturma](../ide/how-to-create-project-templates.md) [nasıl yapılır: öğe şablonları oluşturma](../ide/how-to-create-item-templates.md) [şablon parametreleri](../ide/template-parameters.md) [şablonları özelleştirme](../ide/customizing-project-and-item-templates.md) [nasıl yapılır: Başlangıç setleri oluşturma](../ide/how-to-create-starter-kits.md)
