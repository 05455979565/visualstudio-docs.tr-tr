---
title: Evrensel Windows Platformu (UWP) için uygulama geliştirme
ms.date: 10/24/2017
ms.technology: vs-ide-general
ms.topic: conceptual
ms.assetid: eac59cb6-f12e-4a77-9953-6d62b164a643
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- uwp
ms.openlocfilehash: 3bfe4b1a172158740705e392c573de7911016583
ms.sourcegitcommit: 44e9b1d9230fcbbd081ee81be9d4be8a485d8502
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/30/2019
ms.locfileid: "70179860"
---
# <a name="develop-apps-for-the-universal-windows-platform-uwp"></a>Evrensel Windows Platformu (UWP) için uygulama geliştirme

Evrensel Windows Platformu ve tek bir Windows çekirdeğiyle aynı uygulamayı, telefonlardan masaüstü bilgisayarlardan herhangi bir Windows 10 cihazında çalıştırabilirsiniz. Bu Evrensel Windows uygulamalarını Visual Studio ve Evrensel Windows uygulama geliştirme araçları ile oluşturun.

![Evrensel Windows Platformu](../cross-platform/media/uwp_coreextensions.png)

Uygulamanızı Windows 10 telefonda, Windows 10 Masaüstü veya Xbox üzerinde çalıştırın. Aynı uygulama paketidir! Windows 10 tek, birleştirilmiş çekirdek sunulmasıyla birlikte, tüm platformlardaki bir uygulama paketini çalıştırabilecek. Birkaç platformda, platforma özgü davranışlardan yararlanmak üzere uygulamanıza ekleyebileceğiniz Uzantı SDK 'Ları vardır. Örneğin, mobil cihazlar için bir uzantı SDK'sı, Windows phone'da basıldığında geri düğmesini işler. Projenizde bir uzantı SDK 'sına başvurdıysanız, bu SDK 'nın o platformda kullanılabilir olup olmadığını test etmek için yalnızca çalışma zamanı denetimleri ekleyin. Her platform için aynı uygulama paketine sahip olabilirsiniz!

**Windows çekirdeği nedir?**

İlk kez Windows 10 ' un tüm Windows 10 platformlarındaki ortak bir çekirdeğe sahip olması yeniden düzenlenmiş. Tek bir ortak kaynak, bir ortak Windows çekirdeği, bir dosya g/ç yığını ve bir uygulama modeli vardır. Kullanıcı arabirimi için yalnızca bir XAML kullanıcı arabirimi çerçevesi ve bir HTML UI çerçevesi vardır. Uygulamanızın farklı Windows 10 cihazlarında çalışmasını kolaylaştıran harika bir uygulama oluşturmaya odaklanabilirsiniz.

**Evrensel Windows Platformu tam olarak nedir?**

Evrensel Windows Platformu yalnızca sözleşmelerin ve sürümlerin bir koleksiyonudur. Bu, uygulamanızın çalıştırılacağı yeri hedeflemesini sağlar. Artık bir işletim sistemini hedeflemiyor; Artık bir veya daha fazla cihaz ailelerini hedefleyebilirsiniz. [Evrensel Windows platformu girişi](/windows/uwp/get-started/universal-application-platform-guide)okuyarak daha fazla bilgi edinin.

## <a name="requirements"></a>Gereksinimler

Evrensel Windows uygulama geliştirme araçları, uygulamanızın farklı cihazlarda nasıl göründüğünü görmek için kullanabileceğiniz öykünücülerle gelir. Bu öykünücüleri kullanmak istiyorsanız, bu yazılımı bir fiziksel makineye yüklemeniz gerekir. Fiziksel makinenin Windows 8.1 (x64) Professional sürümü veya üstünü çalıştırması ve Istemci Hyper-V ve Ikinci düzey adres çevirisi 'ni (SLAT) destekleyen bir işlemcisi olması gerekir. Sanal makineye Visual Studio yüklendiğinde Öykünücüler kullanılamaz.

İhtiyacınız olan yazılımın listesi aşağıda verilmiştir:

::: moniker range="vs-2017"

- [Windows 10](http://windows.microsoft.com/windows/downloads). Visual Studio 2017, yalnızca Windows 10 ' da UWP geliştirmeyi destekler. Daha ayrıntılı bilgi için bkz. Visual Studio [Platform hedefleme](/visualstudio/productinfo/vs2017-compatibility-vs) ve [sistem gereksinimleri](/visualstudio/productinfo/vs2017-system-requirements-vs).

- [Visual Studio](https://visualstudio.microsoft.com/vs/older-downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=vs+2017+download). Ayrıca, isteğe bağlı Evrensel Windows Platformu geliştirme iş yüküne da ihtiyacınız olacaktır.

     ![UWP iş yükü](media/uwp_workload.png)

::: moniker-end

::: moniker range="vs-2019"

- [Windows 10](http://windows.microsoft.com/windows/downloads). Visual Studio 2019, yalnızca Windows 10 ' da UWP geliştirmeyi destekler. Daha ayrıntılı bilgi için bkz. Visual Studio [Platform hedefleme](/visualstudio/releases/2019/compatibility/) ve [sistem gereksinimleri](/visualstudio/releases/2019/system-requirements/).

- [Visual Studio](https://visualstudio.microsoft.com/downloads). Ayrıca, isteğe bağlı Evrensel Windows Platformu geliştirme iş yüküne da ihtiyacınız olacaktır.

     ![UWP iş yükü](media/uwp_workload.png)

::: moniker-end

Bu yazılımı yükledikten sonra, Windows 10 cihazınızı geliştirme için etkinleştirmeniz gerekir. Bkz. [cihazınızı geliştirme Için etkinleştirme](/windows/uwp/get-started/enable-your-device-for-development). Her Windows 10 cihazı için artık bir geliştirici lisansına ihtiyacınız yoktur.

## <a name="universal-windows-apps"></a>Evrensel Windows uygulamaları

Windows 10 cihazları için Evrensel Windows Platformu uygulaması C#oluşturmak üzere, C++ Visual Basic veya JavaScript 'ten tercih ettiğiniz geliştirme dilini seçin. [İlk uygulamanızı oluşturma](/windows/uwp/get-started/your-first-app) konusunu okuyun veya [Windows 10 Için Araçlar 'a genel bakış](https://channel9.msdn.com/Series/ConnectOn-Demand/229) videosunu izleyin.

Visual Studio 2015 ile oluşturulmuş Windows Mağazası 8,1 uygulamalarınız, Windows Phone 8,1 uygulamaları veya Evrensel Windows uygulamaları varsa, en son Evrensel Windows Platformu kullanmak için bu uygulamaların bağlantı noktası oluşturmanız gerekir. Bkz. [Windows çalışma zamanı 8. x ÖĞESINDEN UWP 'e taşıma](/windows/uwp/porting/w8x-to-uwp-root).

Evrensel Windows uygulamanızı oluşturduktan sonra uygulamanızı bir Windows 10 cihazına yüklemek veya Windows Mağazası 'na göndermek için paketlemeyi yapmanız gerekir. Bkz. [paketleme uygulamaları](/windows/uwp/packaging/index).

## <a name="see-also"></a>Ayrıca bkz.

- [Visual Studio 'da platformlar arası mobil geliştirme](../cross-platform/cross-platform-mobile-development-in-visual-studio.md)
