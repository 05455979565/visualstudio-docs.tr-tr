---
title: Geliştirme sırasında sisteminizi doğrulama | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-techdebt
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- layer diagrams
ms.assetid: c9dafb47-7b1d-4c72-9432-d43be3db1799
caps.latest.revision: 39
author: alexhomer1
ms.author: gewarren
manager: douge
ms.openlocfilehash: 8b0d65d99cf99c7f1468a0bf596eb687f931b5d3
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42692990"
---
# <a name="validate-your-system-during-development"></a>Geliştirme sırasında sisteminizi doğrulama
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [geliştirme sırasında sisteminizi doğrulama](https://docs.microsoft.com/visualstudio/modeling/validate-your-system-during-development).  
  
Visual Studio, yazılım sisteminizin mimarisi ve kullanıcı gereksinimleri ile tutarlı korunmasına yardımcı olabilirsiniz.  
  
 Bu özelliklerin her biri Visual Studio'nun hangi sürümlerinin desteklediği için bkz [mimari ve Modelleme Araçları sürüm desteği](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport).  
  
## <a name="key-tasks"></a>Anahtar görevler  
 Sisteminizi doğrulamak için aşağıdaki görevleri kullanın.  
  
|**Görevler**|**İlişkili konular**|  
|---------------|---------------------------|  
|**Modelinizi tutarlı olduğundan emin olun:**<br /><br /> Projenizin kullandığı ve modelleri yorumlar biçimine bağlı olarak, bazı öğeler birleşimleri izin vermemek yararlı olabilir. Örneğin, UML sınıfları kısıtlayabilirsiniz, böylece her zaman olduğu [!INCLUDE[TLA2#tla_net](../includes/tla2sharptla-net-md.md)]-uyumlu adları. Bu gibi kısıtlamalar tanımlayabilirsiniz [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] uzantıları.|-   [UML modelinizi doğrulama](../modeling/validate-your-uml-model.md)<br />-   [UML modelleri için doğrulama kısıtlamaları tanımlama](../modeling/define-validation-constraints-for-uml-models.md)|  
|**Yazılım kullanıcıların gereksinimleri karşıladığından emin olun**:<br /><br /> Sisteminiz ve bileşenlerinin testleri düzenlemenize yardımcı olması için gereksinimleri ve mimari modelleri kullanabilirsiniz. Bu uygulama, kullanıcıların ve diğer proje katılımcıları için önemli olan gereksinimleri test etmek ve gereklilikler değiştiğinde testleri hızlı bir şekilde güncelleştirmenize yardımcı emin olun yardımcı olur.|-   [Model aracılığıyla test geliştirme](../modeling/develop-tests-from-a-model.md)|  
|**Yazılım sisteminizin hedeflenen tasarım ile tutarlı kalmasından emin olun:**<br /><br /> Katman diyagramları, uygulamanızın bileşenleri arasında istenen bağımlılıkları açıklar. Geliştirme sırasında gerçek kod bağımlılıkları hedeflenen tasarım ile uyumlu olduğunu doğrulayabilirsiniz.|-   [Kodunuz aracılığıyla katman diyagramları oluşturma](../modeling/create-layer-diagrams-from-your-code.md)<br />-   [Katman diyagramları ile kod doğrulama](../modeling/validate-code-with-layer-diagrams.md)|  
  
## <a name="external-resources"></a>Dış Kaynaklar  
  
|**Kategori**|**Bağlantılar**|  
|------------------|---------------|  
|**Videolar**|![video bağlantısı](../data-tools/media/playvideo.gif "PlayVideo") [Channel 9: Doug yedi: kod anlama ve Visual Studio 2010 ile sistem tasarımı](http://go.microsoft.com/fwlink/?LinkId=216100)<br /><br /> ![video bağlantısı](../data-tools/media/playvideo.gif "PlayVideo") [Channel 9: bir katman diyagramı kullanarak uygulama mimarileri oluşturma](http://go.microsoft.com/fwlink/?LinkID=201117)<br /><br /> ![video bağlantısı](../data-tools/media/playvideo.gif "PlayVideo") [MSDN nasıl yaparım serisi: katman diyagramlarını kullanarak kod doğrulama](http://go.microsoft.com/fwlink/?LinkID=214405)|  
|**Forumları**|-   [Visual Studio Görselleştirme ve Modelleme Araçları](http://go.microsoft.com/fwlink/?LinkId=184720)<br />-   [Visual Studio Görselleştirme ve modelleme SDK'sını (DSL araçları)](http://go.microsoft.com/fwlink/?LinkId=184721)|  
|**Bloglar**|-   [Visual Studio ALM + Team Foundation Server blogu](http://go.microsoft.com/fwlink/?LinkID=201340)|  
|**Teknik makaleler ve belgeler**|[MSDN Mimari Merkezi](http://go.microsoft.com/fwlink/?LinkId=201343)|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Uygulamayı test etme](http://msdn.microsoft.com/library/796b7d6d-ad45-4772-9719-55eaf5490dac)   
 [UML modellerini ve diyagramları genişletme](../modeling/extend-uml-models-and-diagrams.md)   
 [Kullanıcı gereksinimlerini modelleme](../modeling/model-user-requirements.md)   
 [Çözümleme ve mimarinin modelini oluşturma](../modeling/analyze-and-model-your-architecture.md)



