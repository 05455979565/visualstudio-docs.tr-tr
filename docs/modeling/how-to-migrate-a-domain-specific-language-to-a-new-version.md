---
title: 'Nasıl yapılır: Etki Alanına Özgü Dili Yeni Sürüme Geçirme'
ms.date: 11/04/2016
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: ab671cfffdf43d9b69ecda7f06c27a0e8df6bf70
ms.sourcegitcommit: 6944ceb7193d410a2a913ecee6f40c6e87e8a54b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43775919"
---
# <a name="how-to-migrate-a-domain-specific-language-to-a-new-version"></a>Nasıl yapılır: Etki Alanına Özgü Dili Yeni Sürüme Geçirme
Tanımlamak ve etki alanına özgü dil kullanan projeler geçirebileceğiniz [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)] sürümünden [!INCLUDE[dsl](../modeling/includes/dsl_md.md)] , ile dağıtılan [!INCLUDE[vs_orcas_long](../debugger/includes/vs_orcas_long_md.md)].

 Geçiş Aracı bir parçası olarak sağlanan [!INCLUDE[vssdk_current_long](../misc/includes/vssdk_current_long_md.md)]. Aracı dönüştürür [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] projeler ve çözümler kullanın veya DSL araçları tanımlayın.

 Geçiş Aracı açıkça çalıştırmanız gerekir: bir çözümde açtığınızda otomatik olarak başlatılmaz [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Ayrıntılı yönergeler belge ve araç bu yolda bulunabilir:

 **% Program Files%\Microsoft Visual Studio 2010 SDK\VisualStudioIntegration\Tools\DSLTools\DslProjectsMigrationTool.exe**

## <a name="before-you-migrate-your-dsl-projects"></a>DSL projelerinizin geçiş önce
 Geçiş Aracı değiştirir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] proje dosyaları (**.csproj**) ve çözüm dosyaları (**.sln**).

#### <a name="to-prepare-projects-for-migration"></a>Projeleri geçişe hazırlamak için.

-   Emin **.csproj** ve **.sln** dosyaları yazılabilir. Kaynak denetimi altında olmaları durumunda, bunlar kullanıma emin emin olun.

-   Geçirmek istediğiniz klasörleri bir kopyasını oluşturun.

## <a name="migrating-a-collection-of-projects"></a>Proje koleksiyonu geçirme

#### <a name="to-migrate-dsl-projects-and-solutions-to-visual-studio-2010"></a>DSL projeler ve çözümler, Visual Studio 2010'a geçirmeye

1.  DSL geçiş aracını başlatın.

    -   Windows Explorer (veya dosya Gezgini) araca çift tıklayın veya bir komut istemi'nden aracını başlatın. Bu konumda aracıdır:

         **%ProgramFiles%\Microsoft visual Studio 2010 SDK\VisualStudioIntegration\Tools\DSLTools\DslProjectsMigrationTool.exe**

2.  Dönüştürmek istediğiniz projeler ve çözümler içeren bir klasör seçin.

    -   Üst kısmındaki araç kutusunda yolunu girin veya **Gözat**.

     Geçiş Aracı tanımlayın veya DSL kullanan projeler ağacını görüntüler. Ağaç kullanan her bir proje içerir **Microsoft.VisualStudio.Modeling.Sdk** veya **TextTemplating** derlemeler.

3.  Proje ağacını gözden geçirin ve projeleri dönüştürmek istiyor musunuz işaretini kaldırın.

    -   Bir proje veya çözüm, araç haline getiren değişikliklerin bir listesini görmek için seçin.

        > [!NOTE]
        >  Klasör adları yanında görünen onay kutularını hiçbir etkisi yoktur. Projeler ve çözümler incelemek için klasörleri genişletmeniz gerekir.

4.  Projeleri dönüştürün.

    1.  Tıklayın **Dönüştür**.

         Her proje dosyası dönüştürülür önce bir kopyasını _proje_**.csproj** olarak kaydedilen _proje_**. vs2008.csproj**

         Her bir kopyasını _çözüm_**.sln** olarak kaydedilen _çözüm_**. vs2008.sln**

    2.  Bildirilen herhangi bir başarısız dönüştürmeler araştırın.

         Metin penceresindeki hataları raporlanır. Ayrıca, ağaç görünümünde kırmızı bayrak dönüştürmek için başarısız olan her düğümde gösterir. Bu hata hakkında daha fazla bilgi almak için düğüme tıklayabilirsiniz.

5.  **Tüm Şablonları dönüştürme** çözümlerinde başarıyla içeren projeleri dönüştürülür.

    1.  Çözümü açın.

    2.  Tıklayın **tüm Şablonları Dönüştür** Çözüm Gezgini başlığını düğmesi.

        > [!NOTE]
        >  Bu adım, gereksiz yapabilirsiniz. Daha fazla bilgi için [otomatikleştirmek tüm Şablonları Dönüştür nasıl](http://msdn.microsoft.com/b63cfe20-fe5e-47cc-9506-59b29bca768a).

6.  Özel kodunuz dönüştürülmüş projelerinde güncelleştirin.

    -   Projeleri derlemek ve tüm hataları araştırmak çalışır.

    -   Tasarımcınıza test edin.


[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]

## <a name="see-also"></a>Ayrıca Bkz.

- [İlgili blog gönderileri](https://blogs.msdn.microsoft.com/visualstudioalm/tag/code-index/)