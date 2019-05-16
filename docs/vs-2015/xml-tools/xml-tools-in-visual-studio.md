---
title: XML Araçları
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-xml-tools
ms.topic: conceptual
f1_keywords:
- vb.xmldesigner
helpviewer_keywords:
- XML [Visual Studio], resources
- Enterprise Templates, XML and
- discovery files, XML
- server controls, XML and
- Web server controls, XML
- XSL
- XML [Visual Studio], data sources
- XML schemas
- XML [Visual Studio], SGML relationship to
- CSS, style sheets for XML
- XML [Visual Studio], .NET Framework classes
- data [Visual Studio], XML
- classes [Visual Studio], XML
- style sheets, for XML
- Web services
- SGML, XML
- XML [Visual Studio]
- datasets [Visual Basic], XML Schemas
- XSD schemas
- XSL, style sheets
- XMLDataDocument class
ms.assetid: 1fd5de47-2d61-4180-9539-c2c4bf9ab768
caps.latest.revision: 29
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 906f08c0020eb288c1bcd318327be18dc8d08ca5
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65695326"
---
# <a name="xml-tools-in-visual-studio"></a>Visual Studio'daki XML Araçları
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Genişletilebilir Biçimlendirme Dili (XML) * veri tanımlamak için bir biçim sağlayan bir biçimlendirme dilidir. Bu, birden çok platformda daha kesin bildirimleri içerik ve daha anlamlı arama sonuçlarının kolaylaştırır. Ayrıca, XML veri sunudan ayrımı sağlar. Örneğin, HTML etiketleri tarayıcıya kalın veya italik verileri görüntülemek için kullandığınız; XML etiketleri yalnızca şehir adı, sıcaklık ve barometric baskısı gibi verileri tanımlamak için kullanın. XML verilerini bir tarayıcıda sunmak için Genişletilebilir Stil Sayfası Dili (XSL) gibi stil sayfaları ve geçişli stil sayfaları (CSS) kullanırsınız. XML verileri, sunu ve işlem ayırır. Bu, görüntülemek ve farklı bir stil sayfaları ve uygulamaları uygulayarak istediğiniz verileri işlemek sağlar.

 XML Web üzerinden teslimat için optimize edilmiştir SGML bir alt kümesidir. Bu, World Wide Web Consortium (W3C) tarafından tanımlanır. Bu Standardizasyon Tekdüzen ve uygulamaları veya satıcılar bağımsız yapılandırılmış veri olacağını garanti eder.

 XML'dir özelliklerinin çoğu özünde [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] ve [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)]. Aşağıdaki konu listesi içinde sunulan XML ilgili özellikler ve Araçlar adları [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] ve [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)].

 Daha fazla bilgi için [XML Geliştirici Merkezi](http://go.microsoft.com/fwlink/?LinkID=100176), sağlayan en son belgeler, teknik bilgileri, indirmeler, haber grupları ve diğer kaynaklar için XML geliştiriciler.

## <a name="in-this-section"></a>Bu Bölümde
 [XML verileriyle çalışma](../xml-tools/working-with-xml-data.md) şekilde veri XML rolünde işlenir Discusses [!INCLUDE[vsprvs](../includes/vsprvs-md.md)].

 [XSLT hata ayıklama](../xml-tools/debugging-xslt.md) XSLT hatalarını ayıklamak için Visual Studio hata ayıklayıcıyı kullanma hakkındaki konulara bağlantılar sağlar.

## <a name="reference"></a>Başvuru
 [Microsoft.VisualStudio.XmlEditor](http://go.microsoft.com/fwlink/?LinkID=165699) sunan [XML Düzenleyicisi](http://go.microsoft.com/fwlink/?LinkId=228249) ayrıştırma ağacı aracılığıyla [System.Xml.Linq](http://go.microsoft.com/fwlink/?LinkId=228250) XML belgeleri için.

 [XML standartları başvurusu](https://msdn.microsoft.com/79c78508-c9d0-423a-a00f-672e855de401) XML, belge türü tanımı (DTD'nin), XML Şeması Tanım Dili (XSD) ve XSLT de dahil olmak üzere, XML teknolojileri hakkında bilgi sağlar.

 <xref:System.Xml?displayProperty=fullName> Sınıfları ve oluşturan diğer öğeleri açıklayan <xref:System.Xml> ad alanı ve her bir öğede daha ayrıntılı bilgi için bağlantılar sağlar.

 <xref:System.Xml.Serialization?displayProperty=fullName> Sınıfları ve oluşturan diğer öğeleri açıklayan <xref:System.Xml.Serialization> ad alanı ve her öğeyle ilgili daha ayrıntılı bilgi için bağlantılar sağlar.

## <a name="related-sections"></a>İlgili Bölümler
 [XML belge nesne modeli (DOM)](https://msdn.microsoft.com/library/b5e52844-4820-47c0-a61d-de2da33e9f54) Describes nasıl <xref:System.Xml.XmlDocument> ve onun ilişkili sınıfları W3C belge nesne modeli (çekirdek) Düzey 1 ve 2. düzey ad alanı desteği belirtimleri ile uyumlu.

 [XmlReader okuma XML](https://msdn.microsoft.com/3029834c-a27e-4331-b7aa-711924062182) Describes nasıl <xref:System.Xml.XmlReader> Önbelleklenmemiş, iletme yalnızca, salt okunur erişim XML verilerini bir XML akışı sağlar.

 [XML XmlWriter ile yazma](https://msdn.microsoft.com/ea41f72c-e1d3-4e0a-ab0f-f0eb1c27ab86) Describes nasıl <xref:System.Xml.XmlWriter> Önbelleklenmemiş, sağlar. yalnızca XML akışlarını ve W3C standardı ile uyum XML belgeleri oluşturmanıza yardımcı olur oluşturma yolu iletin.

 [XSLT dönüşümleri](https://msdn.microsoft.com/library/202f8820-224c-494f-b61e-cd127eac6e03) Describes nasıl <xref:System.Xml.Xsl.XslCompiledTransform> sınıfı XSLT 1.0 öneri uygular.

 [XPath veri modelini kullanarak XML verilerini işleme](https://msdn.microsoft.com/library/536c6fce-1453-4654-9c72-bca54d47e081) Describes nasıl <xref:System.Xml.XPath.XPathNavigator> sınıfı içinde depolanan XML verileri işleyebilir bir <xref:System.Xml.XPath.XPathDocument> veya <xref:System.Xml.XmlDocument> nesne. <xref:System.Xml.XPath.XPathNavigator> Sınıfı XQuery 1.0 ve XPath 2.0 veri modeline dayanır ve gidin ve XML verileri düzenlemek için kullanılabilir.

 [XML şema nesne modeli (SOM)](https://msdn.microsoft.com/library/a897a599-ffd1-43f9-8807-e58c8a7194cd) oluşturmak ve XML şemaları sağlayarak işlemek için kullanılan sınıfları açıklar bir <xref:System.Xml.Schema.XmlSchema> yüklemek ve bir şema düzenlemek için sınıf.
