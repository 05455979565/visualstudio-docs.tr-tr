---
title: "Nasıl yapılır: Visual C++ projelerini Visual Studio 2015'e yükseltme | Microsoft Docs"
titleSuffix: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- projects [C++], upgrading
ms.assetid: 9a283ebb-f6d8-49c0-a73e-323979ff56a2
caps.latest.revision: 26
author: mikeblome
ms.author: mblome
manager: jillfra
ms.openlocfilehash: 5b0153560173cf8b10ab5e20ebffd47d40baf735
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2019
ms.locfileid: "60095756"
---
# <a name="how-to-upgrade-visual-c-projects-to-visual-studio-2015"></a>Nasıl yapılır: Visual C++ projelerini Visual Studio 2015'e yükseltme
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Visual Studio 2017 için kullanılabileceği en son belgeler için bkz [Visual C++ taşıma ve yükseltme Kılavuzu](https://docs.microsoft.com/cpp/porting/visual-cpp-porting-and-upgrading-guide).

Visual Studio'nun önceki bir sürümde oluşturulmuş bir Visual C++ projesini ilk kez açtığınızda, projeyi güncelleştirmeniz istenebilir. Visual C++ derleyicisi ve kitaplıkların en son sürümüne yükseltmek isteyip istemediğinizi soran ileti. Sürümüne yükseltme seçenekleri bağlıdır [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] projeyi oluşturmak için kullanıldı.

 Kullanabileceğiniz [!INCLUDE[vs_dev12](../includes/vs-dev12-md.md)] açmak, düzenlemek ve derlemek için [!INCLUDE[win8](../includes/win8-md.md)] kullanılarak oluşturulmuş projeler [!INCLUDE[vs_dev11_long](../includes/vs-dev11-long-md.md)], ancak yeni bir [!INCLUDE[win8](../includes/win8-md.md)] projesini kullanmalısınız [!INCLUDE[vs_dev11_long](../includes/vs-dev11-long-md.md)]. (Oluşturmak için bir [!INCLUDE[win81](../includes/win81-md.md)] projesini kullanmalısınız [!INCLUDE[vs_dev12](../includes/vs-dev12-md.md)].)

 Windows 10 projesi oluşturmak için kullanmanız gerekir [!INCLUDE[vs_dev14](../includes/vs-dev14-md.md)].

 Projeyi güncelleştirmeniz istenmezse, projeyi yükseltmek için herhangi bir şey yapmanız gerekmeyebilir.

- ' % S'projesi (.vcproj) bir sürümünde oluşturulduysa [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] sürümünden eski [!INCLUDE[vs2010](../includes/vs2010-md.md)], projeyi güncelleştirmeniz gerekir.

- ' % S'proje (.vcxproj) içinde oluşturulduysa [!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)], [!INCLUDE[vs_dev11_long](../includes/vs-dev11-long-md.md)], veya [!INCLUDE[vs_dev12](../includes/vs-dev12-md.md)] iki seçeneğiniz vardır:

    - Güncellemeyi atlayabilirsiniz. [!INCLUDE[vs_dev14](../includes/vs-dev14-md.md)] Visual C++ araçlarına erişimi varsa herhangi bir değişiklik yapmadan projeyi yükler [!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)] SP1 [!INCLUDE[vs_dev11_long](../includes/vs-dev11-long-md.md)], veya [!INCLUDE[vs_dev12](../includes/vs-dev12-md.md)]. Proje ile aynı makinede sahip oluşturulduysa Visual Studio sürümünü yükleyerek bu erişimi sağlayabilirsiniz [!INCLUDE[vs_dev14](../includes/vs-dev14-md.md)]. Daha fazla bilgi için [yükleme Visual Studio sürümlerini yan yana](../install/install-visual-studio-versions-side-by-side.md).

    - İzin vererek projeyi güncelleştirebilirsiniz [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] bu konunun ilerleyen kısımlarında açıklanan değişiklikleri yapın. Çözümünüzde birden fazla Visual C++ projesi varsa tümünü güncelleştirmeniz gerekir.

        > [!NOTE]
        >  İlk istendiğinde güncelleştirmeyi reddederseniz, projeyi daha sonra seçerek güncelleştirebilirsiniz **VC ++ projesini güncelleştir** üzerinde **proje** menüsü. Komut görünmüyorsa, güncelleştirme gerekli değildir.

## <a name="upgrading-a-visual-c-project"></a>Bir Visual C++ projesini yükseltme
 İzin verirseniz [!INCLUDE[vs_dev14](../includes/vs-dev14-md.md)] otomatik olarak projeyi güncelleştirmesini sağlamak için bu değişiklikler yapılır:

- Projeyi değiştirir, böylece kullandığı [!INCLUDE[vs_dev14](../includes/vs-dev14-md.md)] derleyici ve kitaplıkları (PlatformToolset = VisualStudio v140).

- İçin [!INCLUDE[cppcli](../includes/cppcli-md.md)] projeler, .NET Framework 4.5.2 TargetFrameworkVersion değiştirir.

## <a name="continuing-to-work-with-a-custom-platformtoolset"></a>Özel PlatformToolset ile çalışmaya devam etmesini
 Özel PlatformToolset ile çalışmaya devam etmek isteyip istemediğinizi [!INCLUDE[vs_dev14](../includes/vs-dev14-md.md)], araç takımı x x86 %ProgramFiles%\MSBuild\Microsoft.Cpp\v4.0\Platforms\Win32\PlatformToolsets\ altında bulunmalıdır makine, veya % ProgramFiles (x86)%\MSBuild\ altında X x64 Microsoft.Cpp\v4.0\Platforms\Win32\PlatformToolsets\ makine. Özel PlatformToolset oluşturma hakkında daha fazla bilgi için bkz: [yerel C++ çoklu sürüm desteğinin](http://go.microsoft.com/fwlink/?LinkId=248587) Visual C++ Team blogunda.

## <a name="see-also"></a>Ayrıca Bkz.
 [Visual C++ taşıma ve yükseltme Kılavuzu](http://msdn.microsoft.com/library/f5fbcc3d-aa72-41a6-ad9a-a706af2166fb) [taşıma, geçirme ve Visual Studio projelerini yükseltme](../porting/porting-migrating-and-upgrading-visual-studio-projects.md)
