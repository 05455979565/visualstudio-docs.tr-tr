---
title: Modelinizi profiller ve stereotipler aracılığıyla özelleştirme | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- UML model, profiles
- UML model, stereotypes
- UML model, customizing
ms.assetid: fd607157-0d3a-4583-a84e-427a4b2a5acb
caps.latest.revision: 20
author: alexhomer1
ms.author: gewarren
manager: douge
ms.openlocfilehash: 2dd494b475b5d9068597857a2f4df12e5fed8e2f
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42691908"
---
# <a name="customize-your-model-with-profiles-and-stereotypes"></a>Modelinizi profiller ve stereotipler aracılığıyla özelleştirme
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [modelinizi profiller ve stereotipler aracılığıyla özelleştirme](https://docs.microsoft.com/visualstudio/modeling/customize-your-model-with-profiles-and-stereotypes).  
  
Visual Studio'da sınıfları ve bunları belirli amaçlarla özelleştirmek için bileşenleri gibi standart UML model öğelerini uyarlayabilirsiniz. Uygulayabileceğiniz bir *stereotip* bir model öğesine öğenin özellikler listesini değiştirebilirsiniz. Stereotipler adlı koleksiyon içinde tanımlanan *profilleri*.  
  
 Bu özellik, Visual Studio'nun hangi sürümlerinin desteklediğini görmek için bkz: [mimari ve Modelleme Araçları sürüm desteği](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport).  
  
 Stereotip kullanmak için bir profil için bir paket bağlayın. Bu, paket öğe profilinde tanımlanan stereotiplerin sağlar. Bazı profiller, Visual Studio ile birlikte yüklenir. Ayrıca, kendi profilinizi tanımlayabilirsiniz.  
  
 Bir öğenin özellikler listesinde bulunan stereotipler ayarlanabilir. Şekli diyagram üzerinde temel türleri için uygulanan stereotipler da örnekte gösterildiği gibi şeklinde görünür.  
  
 ![UML sınıf ile bir stereotip. ](../modeling/media/uml-class-stereotype.png "UML_class_stereotype")  
  
> [!NOTE]
>  Bir model oluşturmak ve ardından model başkalarıyla paylaşmak için bir profil kullanıyorsanız, bunlar aynı profili kendi bilgisayarınızda yüklü olan sürece stereotipleri görme olanakları mümkün olmayacaktır.  
  
## <a name="related-topics"></a>İlgili Konular  
  
|Başlık|Açıklama|  
|-----------|-----------------|  
|[Model öğelerine stereotipler ekleme](../modeling/add-stereotypes-to-uml-model-elements.md)|Profile paket bağlama ve bir stereotip öğeye uygulayarak bir paket içindeki bir model öğesini yapılıyor.|  
|[UML modelleri için standart stereotipler](../modeling/standard-stereotypes-for-uml-models.md)|L3 ve UML Standart profilleri L2 Visual Studio ile yüklenir ve her model için varsayılan olarak bağlanır. Bunlar, modellerinize eklemek için kullanabileceğiniz stereotipler sağlar.<br /><br /> Örneğin, yalnızca kendi örnekleri dışarıdan görünen davranışını tanımlamak üzere tasarlanmış olduğunu belirtmek için bir sınıf «belirtimi» stereotipi uygulayabilirsiniz,|  
|[UML genişletmek için profil tanımlama](../modeling/define-a-profile-to-extend-uml.md)|Kendi uygulama alanına kendi stereotipleri ve uyumlu araçları tanımlayabilirsiniz.<br /><br /> Örneğin, bankacılık yazılımı geliştiriyorsanız, sınıflara uygulanabilecek bir «Hesap» stereotipi tanımlayabilirsiniz. Ardından, farklı türdeki hesabı ve ilişkilerini açıklamak için sınıf diyagramlarını kullanabilirsiniz.|  
|[Bir UML profili yükleme](../modeling/install-a-uml-profile.md)|Birisi bir UML profili verdiği, bilgisayarınıza yükleyebilirsiniz.|  
|[Özel tanımlama Modelleme araç kutusu öğesi](../modeling/define-a-custom-modeling-toolbox-item.md)|Özel araç kutusu öğesi bir stereotip yeni öğeler üzerinde sürekli olarak ayarlama özelliğinden kaydeder.|  
|[Sterotipe göre renkli UML sınıfları](http://code.msdn.microsoft.com/UML-Color-Classes-by-07de2b70)|Bu örnek kod, UML diyagramları genişletir. Otomatik olarak, bir UML şekli göre stereotip öğenin rengini ayarlar.|



