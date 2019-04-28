---
title: 'Katman diyagramları: Referans | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: reference
f1_keywords:
- vs.teamarch.layerdiagram.layerexplorer.artifactlink
- vs.teamarch.layerdiagram.layerexplorer.artifactlink.properties
- vs.teamarch.layerdiagram.diagram
- vs.teamarch.UMLModelExplorer.layerdiagram
- vs.teamarch.layerdiagram.layerexplorer
- vs.teamarch.layerdiagram.shapes.properties
- vs.teamarch.layerdiagram.toolbox
helpviewer_keywords:
- architecture, layer diagrams
- layer diagrams
- diagrams - modeling, layer
- constraints, architectural
ms.assetid: f26c986c-1e79-420e-b29a-a283e6d8a71d
caps.latest.revision: 35
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: d281b0ddb15a2acc455acd037c088c133c74c1f1
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "63440980"
---
# <a name="layer-diagrams-reference"></a>Katman diyagramları: Başvuru
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Visual Studio'da kullanabileceğiniz bir *katman diyagramı* sisteminizin üst düzey, mantıksal mimarisini görselleştirmek için. Bir katman diyagramı fiziksel yapıları sisteminizde adı verilen mantıklı, soyut gruplar halinde düzenler *katmanları*. Bu katmanlar, yapıların gerçekleştirdiği temel görevleri veya sistemin ana bileşenlerini açıklar. Her katman aynı zamanda daha ayrıntılı görevleri açıklayan iç içe katmanlar içerebilir.  
  
 Bu özellik, Visual Studio'nun hangi sürümlerinin desteklediğini görmek için bkz: [mimari ve Modelleme Araçları sürüm desteği](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport).  
  
 Katmanlar arasındaki hedeflenen veya varolan bağımlılıkları belirtebilirsiniz. Oklar olarak temsil edilen Bu bağımlılıklar, hangi katmanların kullanın veya diğer Katmanlar tarafından temsil edilen işlevi kullanmakta gösterir. Sisteminiz farklı rolleri ve işlevleri açıklayan katmanlara düzenleyerek, bir katman diyagramı anlamak, yeniden kullanmak ve kodunuzu bakımını kolaylaştırmak yardımcı olabilir.  
  
 Bir katman diyagramı, aşağıdaki görevleri gerçekleştirmenize yardımcı olması için kullanın:  
  
- Sisteminizde varolan veya hedeflenen mantıksal mimarisi iletişim kurar.  
  
- Mevcut kodunuzu ve hedeflenen mimariyi arasında çakışmalar keşfedin.  
  
- Yeniden düzenleyin, güncelleştirin veya sisteminizin evrim Geçiren hedeflenen mimari üzerindeki değişikliklerin etkisini görselleştirin.  
  
- İadeniz doğrulama dahil ederek geliştirme ve kodunuzun bakım sırasında hedeflenen mimariyi güçlendirmek ve yapı işlemleri.  
  
  Bu konuda, bir katman diyagramı üzerinde kullanabileceğiniz öğeleri açıklar. Oluşturun ve katman diyagramları çizmek için bkz hakkında daha ayrıntılı bilgi için [katman diyagramları: Yönergeleri](../modeling/layer-diagrams-guidelines.md). Katman desenleri hakkında daha fazla bilgi için ziyaret [desenler ve uygulamalar site](http://go.microsoft.com/fwlink/?LinkId=145794).  
  
## <a name="reading-layer-diagrams"></a>Katman diyagramları okuma  
 ![Katman diyagramlarındaki öğeler](../modeling/media/uml-layerrefreading.png "UML_LayerRefReading")  
  
 Aşağıdaki tabloda, bir katman diyagramı üzerinde kullanabileceğiniz öğeleri açıklar.  
  
|**Şekil**|**Öğe**|**Açıklama**|  
|---------------|-----------------|---------------------|  
|1.|**Katman**|Sisteminizdeki fiziksel yapıları mantıksal grubudur. Bu yapılar ad alanları, projeler, sınıflar, yöntemler vb. olabilir.<br /><br /> Bir katmana bağlı yapıların listesini görmek için katmanın kısayol menüsünü açın ve ardından **bağlantıları görüntüle** açmak için **Katman Gezgini**.<br /><br /> Daha fazla bilgi için [Katman Gezgini](#Explorer).<br /><br /> -   **Namespace bağımlılıkları Yasak** -Bu katman ile ilişkili yapıların belirli ad alanlarına bağlı olamayacağını belirtir.<br />-   **Ad Yasak** -Bu katman ile ilişkili yapıların belirli ad alanlarına ait olmaması gerektiğini belirtir.<br />-   **Gerekli ad alanları** -Bu katman ile ilişkili yapıların belirli ad alanlarına birine ait olduğunu belirtir.|  
|2|**Bağımlılık**|Bir katmanın işlevselliği kullanabileceğini belirtir başka bir katmanda ancak tersi doğru değildir.<br /><br /> -   **Yön** -Bağımlılık yönünü belirtir.|  
|3|**Çift yönlü bağımlılık**|Bir katmanın işlevselliği kullanabileceğini belirtir başka bir katmanda ve bunun tersi de geçerlidir.<br /><br /> -   **Yön** -Bağımlılık yönünü belirtir.|  
|4|**Yorum**|Genel Notlar ve diyagramı diyagram üzerindeki öğeleri eklemek için bu seçeneği kullanın.|  
|5|**Açıklama bağlantısı**|Açıklamalar diyagram üzerindeki öğeleri bağlamak için bu seçeneği kullanın.|  
  
## <a name="Explorer"></a> Katman Gezgini  
 Her katman, çözümünüzdeki projeler, sınıflar, ad alanları, proje dosyaları ve diğer bölümlerini yazılım gibi yapıtları bağlayabilirsiniz. Bir katmandaki sayı katmana bağlı olan yapıların sayısını gösterir. Ancak, bir katmandaki yapı sayısını okurken aşağıdakileri unutmayın:  
  
- Bir katman diğer yapıları içeren bir yapıya bağlanırsa, ancak katman doğrudan diğer yapılara bağlanmazsa, sayı yalnızca bağlı yapıyı içerir. Bununla birlikte, diğer yapılar katman doğrulanırken analiz için alınır.  
  
   Örneğin, bir katman tek bir ad alanına bağlanırsa, ad alanı sınıflar içerse bile, bağlı yapıların sayısı 1'dir. Katmanın ad alanındaki her bir sınıfa da bağlantıları bulunuyorsa, sayı bağlantılı sınıfları da içerecektir.  
  
- Bir katman yapılarla bağlantılı diğer katmanları içeriyorsa, kapsayıcı katman da üzerindeki sayı bu yapıları içermese bile bu yapılara bağlıdır.  
  
  Katmanlar ve yapılar bağlama hakkında daha fazla bilgi için bkz:  
  
- [Katman Diyagramları: Yönergeler](../modeling/layer-diagrams-guidelines.md)  
  
- [Kodunuz aracılığıyla katman diyagramları oluşturma](../modeling/create-layer-diagrams-from-your-code.md)  
  
#### <a name="to-examine-the-linked-artifacts"></a>Bağlı yapıtlar incelemek için  
  
- Katman diyagramında bir veya daha fazla katmanı için kısayol menüsünü açın ve ardından **bağlantıları görüntüle**.  
  
     **Katman Gezgini** açılır ve Seçili katmanlara bağlanmış yapılar gösterir. **Katman Gezgini** her yapı bağlantılarını özelliklerini gösteren bir sütun vardır.  
  
    > [!NOTE]
    > Bu özelliklerin tümünü göremiyorsanız genişletin **Katman Gezgini** penceresi.  
  
    |**Katman Gezgini'nde sütun**|**Açıklama**|  
    |----------------------------------|---------------------|  
    |**Kategorileri**|Sınıfı, ad alanı, kaynak dosyasını ve benzeri gibi bir yapı türü|  
    |**Katman**|Yapıya katmanı|  
    |**Doğrulamayı destekler**|Varsa **True**, sonra da katman doğrulama işlemine proje ya da bu öğeden bağımlılıklara uygun olduğunu doğrulayabilirsiniz.<br /><br /> Varsa **False**, sonra bağlantının katman doğrulama işleminde yer almaz.<br /><br /> Daha fazla bilgi için [katman diyagramları: Yönergeleri](../modeling/layer-diagrams-guidelines.md).|  
    |**tanımlayıcı**|Bağlantılı yapıt başvurusu|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Uygulamanız için model oluşturma](../modeling/create-models-for-your-app.md)
