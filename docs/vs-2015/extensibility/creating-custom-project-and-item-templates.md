---
title: Özel proje ve öğe şablonları oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 586da5dc-f678-402b-afd0-0332959fd7a6
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: b8212b11a60697211f70cd608b6f08a3fade874e
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42691281"
---
# <a name="creating-custom-project-and-item-templates"></a>Özel Proje ve Öğe Şablonları Oluşturma
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [oluşturma özel Proje ve öğe şablonlarını](https://docs.microsoft.com/visualstudio/extensibility/creating-custom-project-and-item-templates).  
  
Visual Studio SDK, bir özel Proje şablonu ve özel öğe şablonu oluşturma proje şablonları içerir. Bu şablonlar, bazı ortak parametresi değişimleri dahil ve zip dosyaları olarak oluşturun. Değil bunlar otomatik olarak dağıtılır ve deneysel örneğinde kullanılabilir değildir. Zip kopyalamalısınız konumuna dosyası  
  
 Şablon oluşturma şablonları, daha büyük uzantılarında şablonları dahil sağlar. Bu kaynak dosyaları üzerinde sürüm denetimi uygulamak ve bir grup şablon projelerini bir VSIX paketi oluşturmanıza olanak sağlar.  
  
 Temel şablon oluşturma senaryoları için kullanmanız gereken **şablonu dışarı aktar** Sihirbazı'nı, ama için sıkıştırılmış bir dosya çıkarır. Temel şablon oluşturma hakkında daha fazla bilgi için bkz: [oluşturma proje ve öğe şablonları](../ide/creating-project-and-item-templates.md).  
  
 Başlangıç Visual Studio "15" Preview 4, özel Proje ve öğe şablonları için tarama artık gerçekleştirilir. Bunun yerine, uzantı yükleme konumu olarak bu şablonları tanımlamak, şablon bildirim dosyalarını sağlamanız gerekir. Preview 2 yükleme VSIX uzantılarınızı güncelleştirmek için kullanabilirsiniz. Uzantınızı bir MSI kullanarak dağıtırsanız, şablon bildirim dosyalarını el ile oluşturmanız gerekir. Daha fazla bilgi için [özel Proje ve öğe şablonlarını yükseltme Visual Studio "15" için](../extensibility/upgrading-custom-project-and-item-templates-for-visual-studio-“15”.md). Şablon bildirim şeması belgelenen [Visual Studio şablon bildirim şeması başvurusu](../extensibility/visual-studio-template-manifest-schema-reference.md).  
  
## <a name="creating-a-project-template"></a>Proje şablonu oluşturma  
  
1.  Bir proje şablonu projesi oluşturun. Proje şablonunda bulabilirsiniz **yeni proje** iletişim kutusunda, Visual Basic veya Visual C# **genişletilebilirlik** klasör.  
  
     Şablon sınıf dosyası, simge, .vstemplate dosyasının, ProjectTemplate.vbproj veya ProjectTemplate.csproj adlı düzenlenebilir proje dosyasını ve genellikle diğer proje türlerine göre bu tür bir resources.resx dosya, bir AssemblyInfo oluşturulan bazı dosyalar oluşturur. Dosya ve bir .settings dosyası. Her kod dosyası, uygun yerlerde genel parametresi değişimleri içerir.  
  
2.  Ekleme ve projeniz için gereken proje öğeleri kaldırın. Düzenlenebilir bir proje dosyası, AssemblyInfo dosyası veya .vstemplate dosyasının kaldırmayın.  
  
3.  .Vstemplate dosyası bir ekleme ve silme işlemleri yansıtacak şekilde güncelleştirin. [Proje](../extensibility/project-element-visual-studio-templates.md) öğesi içermelidir bir [ProjectItem](../extensibility/projectitem-element-visual-studio-item-templates.md) şablona dahil edilecek her bir dosya için öğesi.  
  
4.  Kod dosyalarınızı ve diğer kullanıcıya yönelik içeriği değiştirme ve uygun parametresi değişimleri ekleyin.  
  
5.  Oluşturulan içerik gerektiği gibi değiştirin.  
  
6.  Projeyi oluşturun.  
  
     Visual Studio, şablonunuzu içeren bir .zip dosyası oluşturur. Değil dağıtılan ve deneysel örneğinde kullanılabilir değil.  
  
## <a name="creating-an-item-template"></a>Öğe şablonu oluşturma  
  
1.  Bir öğe şablonu projesi oluşturun.  
  
     Şablon, bir sınıf dosyası, simge, .vstemplate dosyası ve bir AssemblyInfo dosyası oluşturur. Bazı ortak parametresi değişimleri sınıf dosyası içerir.  
  
2.  Ekleme ve projeniz için gereken proje öğeleri kaldırın.  
  
3.  .Vstemplate dosyası bir ekleme ve silme işlemleri yansıtacak şekilde güncelleştirin. [Proje](../extensibility/project-element-visual-studio-templates.md) öğesi içermelidir bir [ProjectItem](../extensibility/projectitem-element-visual-studio-item-templates.md) şablona dahil edilecek her bir dosya için öğesi.  
  
4.  Kod dosyalarınızı ve diğer kullanıcıya yönelik içeriği değiştirme ve uygun parametresi değişimleri ekleyin.  
  
5.  Oluşturulan içerik gerektiği gibi değiştirin.  
  
6.  Projeyi oluşturun.  
  
     Visual Studio, şablonunuzu içeren sıkıştırılmış bir dosya oluşturur. Değil dağıtılan ve deneysel örneğinde kullanılabilir değil.  
  
## <a name="deployment"></a>Dağıtım  
  
#### <a name="to-deploy-the-project-or-item-template"></a>Proje veya öğe şablonu dağıtmak için  
  
1.  Bir VSIX projesi oluşturun. Daha fazla bilgi için [VSIX proje şablonu](../extensibility/vsix-project-template.md).  
  
2.  VSIX projesini başlangıç projesi olarak ayarlayın. İçinde **Çözüm Gezgini**, VSIX proje düğümünü sağ tıklatın ve seçin seçin **başlangıç projesi olarak ayarla**.  
  
3.  Proje şablonu projesi VSIX projesinin bir varlık ayarlayın. .Vsixmanifest dosyasını açın. Git **varlıklar** sekmesine **yeni**.  
  
    1.  Ayarlama **türü** alanı **Microsoft.VisualStudio.ProjectTemplate** veya **Microsoft.VisualStudio.ItemTemplate**.  
  
    2.  Kaynağı için **mevcut çözümde bir proje** seçeneğini ve ardından şablonunuzu içeren projeyi seçin.  
  
4.  Çözümü derleyin ve F5 tuşuna basın. Deneysel örneği açılır.  
  
5.  Bir proje şablonu projesi için listelenen, proje şablonunu görmeniz gerekir **yeni proje** iletişim (**dosya / yeni / Project**), Visual C# veya Visual Basic düğümü. Bir öğe Şablonu proje öğesi şablonunuzu Yeni Öğe Ekle iletişim kutusunda listelenen görmeniz gerekir (içinde **Çözüm Gezgini**, proje düğümünü seçin ve tıklayın **Ekle / yeni öğe**).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio Şablon Başvurusu](../ide/visual-studio-template-reference.md)

