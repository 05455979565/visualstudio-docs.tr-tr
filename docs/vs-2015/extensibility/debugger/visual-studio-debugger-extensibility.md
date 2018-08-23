---
title: Visual Studio hata ayıklayıcı genişletilebilirliği | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- debugging [Visual Studio], Debugging SDK
- Debugging SDK
ms.assetid: c088b6a2-c3ad-446b-830d-9c6f41b2934b
caps.latest.revision: 33
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: d4c3a9644e7150ea31cca2aba927bbdbacb8b0eb
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42687463"
---
# <a name="visual-studio-debugger-extensibility"></a>Visual Studio Hata Ayıklayıcı Genişletilebilirliği
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [Visual Studio hata ayıklayıcı genişletilebilirliği](https://docs.microsoft.com/visualstudio/extensibility/debugger/visual-studio-debugger-extensibility).  
  
Visual Studio, programınızdaki hataları aşağı izlemek için güçlü ve kullanımı kolay bir araç sağlayan bir tam etkileşimli kaynak kodu hata ayıklayıcı, içerir. Hata ayıklayıcı tam destek Visual Basic, C#, C/C++ ve JavaScript sahiptir. Bununla birlikte, [!INCLUDE[vsipsdk](../../includes/vsipsdk-md.md)], yani kullanılabilir [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkId=214453), hata ayıklayıcı aynı zengin özelliklere sahip başka bir programlama dili desteklenebilir.  
  
 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Hata ayıklayıcısı, hataları ayıklanan diline özgü buna karşılık olarak hata ayıklama bileşenlerini genel ön uç (diğer bir deyişle, kullanıcı arabirimi) etmektir. İçin gerekli olan tüm yeni diller için destek [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] hata ayıklayıcı, hata ayıklama altyapısı (DE) gibi gerekli arka uç bileşenlerine oluşturmaktır. Olduğu yer [!INCLUDE[vsipsdk](../../includes/vsipsdk-md.md)] halinde sunulur.  
  
 [!INCLUDE[vsipsdk](../../includes/vsipsdk-md.md)] Tüm eksiksiz bir başvuru içeriyor [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] yeni DE oluşturmak için gereken öğeleri. Ayrıca, örnekler ve başlamanıza yardımcı olacak öğreticiler vardır.  
  
 Hata ayıklama desteği ile dil proje sistemi bir uçtan uca örnek için bkz: [IronPython örnek](http://msdn.microsoft.com/en-us/4c41695c-12c1-4670-b43b-d8d84c9e4089).  
  
 Aşağıdaki bölümlerde kullanarak hata ayıklayıcıyı genişletmek nasıl [!INCLUDE[vsipsdk](../../includes/vsipsdk-md.md)].  
  
## <a name="in-this-section"></a>Bu Bölümde  
 [Başlarken](../../extensibility/debugger/getting-started-with-debugger-extensibility.md)  
 Neler açıklanır [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] teklifler ve SDK'yı yüklemeyi nasıl hata ayıklama.  
  
 [Özel Hata Ayıklama Altyapısı Oluşturma](../../extensibility/debugger/creating-a-custom-debug-engine.md)  
 Programınızı DE ayırmak için bir DE hazırlama özel DE işlemin, belgeler.  
  
 [Bir CLR ifade değerlendiricisi yazma](../../extensibility/debugger/writing-a-common-language-runtime-expression-evaluator.md)  
 İfade değerlendiricisi yazma olup olmadığını açıklar.  
  
 [Hata Ayıklama Altyapısı Uygulama Stratejisi Seçme](../../extensibility/debugger/choosing-a-debug-engine-implementation-strategy.md)  
 Sizin DE uygulamak nasıl ele alınmaktadır.  
  
 [Başvuru](../../extensibility/debugger/reference/reference-visual-studio-debugging-apis.md)  
 Belgeler [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] hata ayıklama API'si.  
  
 [Örnekler](../../extensibility/debugger/visual-studio-debugging-samples.md)  
 Bir ortak dil çalışma zamanı ifade değerlendiricisi örneği ve bir hata ayıklama altyapısı örneği bağlantılar içerir.

