---
title: Yayımla alarak IIS yayımlama ayarları
ms.custom: Create and import a publishing profile to deploy an application from Visual Studio to IIS
ms.date: 05/07/2018
ms.technology: vs-ide-deployment
ms.topic: tutorial
helpviewer_keywords:
- deployment, publish settings
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e6df935578955d3c72b6f4fa61efdf614229bca0
ms.sourcegitcommit: 4667e6ad223642bc4ac525f57281482c9894daf4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/20/2018
ms.locfileid: "36282167"
---
# <a name="publish-an-application-to-iis-by-importing-publish-settings-in-visual-studio"></a>İçeri aktararak IIS uygulama yayımlama Visual Studio'da yayımlama ayarları

Kullanabileceğiniz **Yayımla** aracı almak için uygulamanızı dağıtma ve yayımlama ayarları. Bu makalede, kullandığımız IIS ayarlarını yayımlamak ancak kullanabilirsiniz içe aktarmak için benzer adımları için yayımlama ayarları [Azure App Service](../deployment/tutorial-import-publish-settings-azure.md). Bir yayımlama ayarları profili el ile Visual Studio'nun her bir yükleme dağıtımı IIS yapılandırma daha hızlı olabilir, bazı senaryolarda kullanın.

Visual Studio'da ASP.NET, ASP.NET Core ve .NET Core uygulamaları için aşağıdaki adımları uygulayın. Adımları Visual Studio 2017 sürüm 15,6 karşılık gelir.

Bu öğreticide şunları yapacaksınız:

> [!div class="checklist"]
> * Yayımlama ayarları dosyası oluşturabilmesi IIS yapılandırma
> * Yayımlama ayarları dosyası oluşturma
> * Yayımlama ayarları dosyasını Visual Studio'ya içeri aktarma
> * IIS uygulama dağıtma

Yayımlama ayarları dosyası (*\*.publishsettings*) bir yayımlama profili farklı (*\*.pubxml*) Visual Studio'da oluşturuldu. Yayımlama ayarları dosyası IIS veya Azure uygulama hizmeti tarafından oluşturulan veya el ile oluşturulabilir ve ardından Visual Studio'ya aktarılabilir.

> [!NOTE]
> Yalnızca bir Visual Studio yayımlama profilini kopyalamak gerekiyorsa (\*.pubxml dosyası) bir yüklemesinden Visual Studio diğerine, yayımlama profili bulabilirsiniz  *\<profilename\>.pubxml*, içinde  *\\< projectname\>\Properties\PublishProfiles* yönetilen proje türleri için klasör. Web siteleri için kısmına bakın *\App_Data* klasör. Yayımlama profillerini MSBuild XML dosyalarıdır.

## <a name="prerequisites"></a>Önkoşullar

* Visual Studio 2017 yüklü olması gerekir ve **ASP.NET** ve **.NET Framework** geliştirme iş yükü. .NET Core uygulaması için etmeniz **.NET Core** iş yükü.

    Visual Studio henüz yüklemediyseniz, Git [Visual Studio indirmeleri](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017) ücretsiz yüklemek için sayfa.

* Yayımlama ayarları dosyası, IIS'den oluşturmak için Windows Server 2012 veya Windows Server 2016 çalıştıran bir bilgisayar olması gerekir ve doğru yapılandırılmış bir IIS Web sunucusu rolü bulunmalıdır. ASP.NET 4.5 veya ASP.NET Core ayrıca yüklenmesi gerekir. ASP.NET Core için bkz: [IIS yayımlama](/aspnet/core/publishing/iis?tabs=aspnetcore2x#iis-configuration). ASP.NET 4.5 için bkz: [IIS 8.0 kullanarak ASP.NET 3.5 ve ASP.NET 4.5](/iis/get-started/whats-new-in-iis-8/iis-80-using-aspnet-35-and-aspnet-45).

## <a name="create-a-new-aspnet-project-in-visual-studio"></a>Visual Studio'da yeni bir ASP.NET projesi oluşturma

1. Visual Studio çalıştıran bilgisayarda seçin **dosya** > **yeni proje**.

1. Altında **Visual C#** veya **Visual Basic**, seçin **Web**ve ardından Orta bölmede ya da **ASP.NET Web uygulaması (.NET Framework)** veya (C# yalnızca) **ASP.NET çekirdek Web uygulaması**ve ardından **Tamam**.

    Belirtilen proje şablonları görmüyorsanız tıklatın **açık Visual Studio yükleyicisi** sol bölmesinde bağlantı **yeni proje** iletişim kutusu. Visual Studio yükleyicisi başlatır. Yüklemelisiniz gerekli Visual Studio iş yüklerini tanımlamak için bu makaledeki önkoşullara bakın.

1. Ya da seçin **MVC** (.NET Framework) veya **Web uygulaması (Model-View-Controller)** (için .NET Core), emin olun **doğrulaması yok** seçilir ve ardından **Tamam**.

1. Gibi bir ad yazın **mywebapp şeklindedir** tıklatıp **Tamam**.

    Visual Studio projesi oluşturur.

1. Seçin **yapı** > **yapı çözümü** Projeyi derlemek için.

## <a name="install-and-configure-web-deploy-on-windows-server"></a>Yükleme ve Windows Server'da Web dağıtımı yapılandırma

[!INCLUDE [install-web-deploy-with-hosting-server](../deployment/includes/install-web-deploy-with-hosting-server.md)]

## <a name="create-the-publish-settings-file-in-iis-on-windows-server"></a>Windows Server'da IIS'de yayımlama ayarları dosyası oluşturma

[!INCLUDE [create-publish-settings-iis](../deployment/includes/create-publish-settings-iis.md)]

## <a name="import-the-publish-settings-in-visual-studio-and-deploy"></a>Visual Studio'da yayımlama ayarlarını içeri aktarın ve dağıtın

[!INCLUDE [import-publish-settings](../deployment/includes/import-publish-settings-vs.md)]

Uygulama başarıyla dağıtıldıktan sonra otomatik olarak başlamanız gerekir. Visual Studio'dan başlamazsa, IIS'de uygulamayı başlatın. ASP.NET Core için uygulama havuzu için alan emin olmanız gerekir. **DefaultAppPool** ayarlanır **yönetilen kod yok**.

## <a name="next-steps"></a>Sonraki adımlar

Bu öğreticide bir yayımlama ayarları dosyası oluşturdunuz, Visual Studio'ya içeri aktarılan ve IIS bir ASP.NET uygulaması dağıttınız. Visual Studio'da yayımlama diğer seçeneklerine genel bakış isteyebilirsiniz.

> [!div class="nextstepaction"]
> [Dağıtıma ilk bakış](../deployment/deploying-applications-services-and-components.md)
