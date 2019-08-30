---
title: Çevrimdışı yüklemesini oluşturma
description: Visual Studio bir güvenilir bir internet bağlantısı veya düşük bant genişliğine sahip olduğunuzda çevrimdışı yüklemeyi öğrenin.
ms.date: 07/24/2019
ms.custom: seodec18
ms.topic: conceptual
f1_keywords:
- offline installation [Visual Studio]
- offline install [Visual Studio]
- layout [Visual Studio]
ms.assetid: f8625d5e-f6ea-4db0-83c0-619b77fab3cf
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.prod: visual-studio-windows
ms.technology: vs-installation
ms.openlocfilehash: 599eef257894c0619252a4c2db23b304e4439d70
ms.sourcegitcommit: 44e9b1d9230fcbbd081ee81be9d4be8a485d8502
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/30/2019
ms.locfileid: "70180038"
---
# <a name="create-an-offline-installation-of-visual-studio"></a>Visual Studio’nun çevrimdışı yüklemesini oluşturma

::: moniker range="vs-2017"

Biz, Visual Studio 2017'de ağ ve bilgisayar yapılandırmalarını çeşitli içinde çalışacak şekilde tasarlanmıştır. Denemenizi öneririz ancak [Visual Studio web yükleyicisini](https://visualstudio.microsoft.com/vs/older-downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=vs+2017+download)&mdash;küçük bir dosyadır ve en son düzeltmeler ve özellikler ile güncel kalın sağlar&mdash;için aktarmanızı değil olduğunu biliyoruz.

::: moniker-end

::: moniker range="vs-2019"

Visual Studio 2019 ' i çeşitli ağ ve bilgisayar yapılandırmalarında iyi bir şekilde çalışacak şekilde tasarlıyoruz. Denemenizi öneririz ancak [Visual Studio web yükleyicisini](https://visualstudio.microsoft.com/downloads)&mdash;küçük bir dosyadır ve en son düzeltmeler ve özellikler ile güncel kalın sağlar&mdash;için aktarmanızı değil olduğunu biliyoruz.

::: moniker-end

Örneğin, düşük bant genişliğine sahip bir ya da güvenilir bir internet bağlantısına sahip olabilir. Öyleyse, birkaç seçeneğiniz vardır: Yüklemeden önce dosyaları indirmek için yeni "tümünü Indir, sonra Yükle" özelliğini kullanabilir veya dosyaların yerel bir önbelleğini oluşturmak için komut satırını kullanabilirsiniz.

> [!NOTE]
> Internet 'ten güvenlik duvarlı bir istemci iş istasyonu ağına Visual Studio dağıtımı gerçekleştirmek isteyen bir kuruluş yöneticisiyseniz, bkz. [Visual Studio 'nun ağ yüklemesi oluşturma](../install/create-a-network-installation-of-visual-studio.md) ve [sertifika yükleme Visual Studio çevrimdışı yükleme sayfaları için gereklidir](../install/install-certificates-for-visual-studio-offline.md) .

## <a name="use-the-download-all-then-install-feature"></a>Kullanım "tümünü indir ve Yükle" özelliği

::: moniker range="vs-2017"

[**Sürüm 15,8 ' de yeni**](/visualstudio/releasenotes/vs2017-relnotes-v15.8#install): Web yükleyicisini indirdikten sonra, yeni **Tümünü İndir '** i seçin ve sonra Visual Studio yükleyicisi seçeneğini yükleyin. Ardından, yükleme işlemine devam.

   !["Tümünü indir ve Yükle" seçeneği](media/download-all-then-install.png)

::: moniker-end

::: moniker range="vs-2019"

Web yükleyicisini indirdikten sonra, yeni **Tümünü İndir '** i seçin ve sonra Visual Studio yükleyicisi seçeneğini yükleyin. Ardından, yükleme işlemine devam.

   !["Tümünü indir ve Yükle" seçeneği](media/vs-2019/download-all-then-install-from-installer.png)

::: moniker-end

Visual Studio 'Yu indirdiğiniz aynı bilgisayar için tek bir yükleme olarak indirebilmeniz için "tümünü Indir ve Yükle" özelliğini tasarladık. Bu şekilde, Visual Studio 'Yu yüklemeden önce Web ile güvenli bir şekilde bağlantıyı kesebilirsiniz.

> [!IMPORTANT]
> Başka bir bilgisayara aktarmayı planladığınız çevrimdışı bir önbellek oluşturmak için "tümünü Indir ve Yükle" özelliğini kullanmayın. Bu şekilde çalışacak şekilde tasarlanmamıştır. <br><br>Visual Studio 'Yu başka bir bilgisayara yüklemek üzere çevrimdışı bir önbellek oluşturmak istiyorsanız, yerel bir önbellek oluşturma veya görsel ağ yüklemesi oluşturma hakkında bilgi için bu sayfanın [Yerel önbellek oluşturmak için komut satırını kullanma](#use-the-command-line-to-create-a-local-cache) bölümüne bakın. [Visual Studio'nun ağ kurulumunu oluşturma](../install/create-a-network-installation-of-visual-studio.md)Bir ağ önbelleğinin nasıl oluşturulacağı hakkında bilgi için bkz.

## <a name="use-the-command-line-to-create-a-local-cache"></a>Yerel önbellek oluşturmak için komut satırını kullanın

Küçük bir önyükleyici indirdikten sonra komut satırında yerel önbellek oluşturmak için kullanın. Ardından Visual Studio'yu yüklemek için yerel önbellek kullanın. (Bu işlem, önceki sürümleri için ISO dosyalarını değiştirir.)

İşte nasıl.

### <a name="step-1---download-the-visual-studio-bootstrapper"></a>1\. adım - Visual Studio önyükleyicisini yükleyin

Bu adımı tamamlamak için bir internet bağlantısı olması gerekir.

Seçtiğiniz Visual Studio sürümünüz için Visual Studio önyükleyicisi indirerek başlayın. Kurulum dosyanızı&mdash;veya önyükleyici&mdash;ile eşleşir veya şunlardan birini benzer.

::: moniker range="vs-2017"

| Sürüm                    | Dosya                                                                    |
|----------------------------|-------------------------------------------------------------------------|
| Visual Studio Community    | [vs_community.exe](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=community&rel=15&utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=offline+install&utm_content=download+vs2017)       |
| Visual Studio Professional | [vs_professional.exe](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=professional&rel=15&utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=offline+install&utm_content=download+vs2017) |
| Visual Studio Enterprise   | [vs_enterprise.exe](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=enterprise&rel=15&utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=offline+install&utm_content=download+vs2017)     |

::: moniker-end

::: moniker range="vs-2019"

| Sürüm                    | Dosya                                                                    |
|----------------------------|-------------------------------------------------------------------------|
| Visual Studio Community    | [vs_community.exe](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=community&rel=16&utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=offline+install&utm_content=download+vs2019)       |
| Visual Studio Professional | [vs_professional.exe](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=professional&rel=16&utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=offline+install&utm_content=download+vs2019) |
| Visual Studio Enterprise   | [vs_enterprise.exe](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=enterprise&rel=16&utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=offline+install&utm_content=download+vs2019)     |

::: moniker-end

### <a name="step-2---create-a-local-install-cache"></a>2\. adım - yerel yükleme önbelleği oluşturma

Bu adımı tamamlamak için bir internet bağlantısı olması gerekir.

> [!IMPORTANT]
> Visual Studio Community yüklerseniz, yüklemeyi 30 gün içinde etkinleştirmeniz gerekir. Bu, internet bağlantısı gerektirir.

Bir komut istemi açın ve aşağıdaki örneklerde komutlardan birini kullanın. Visual Studio Community sürümünü kullanıyorsanız, burada listelenen örnekler varsayılır; komut sürümünüz için uygun şekilde ayarlayın.

> [!TIP]
> Bir hatayı engellemek için, tam yükleme yolunuz 80 karakterden az olduğundan emin olun.

- .NET web ve .NET masaüstü geliştirme için çalıştırın:

   ```cmd
    vs_community.exe --layout c:\vslayout --add Microsoft.VisualStudio.Workload.ManagedDesktop --add Microsoft.VisualStudio.Workload.NetWeb --add Component.GitHub.VisualStudio --includeOptional --lang en-US
    ```

- .NET Masaüstü ve Office geliştirme için çalıştırın:

   ```cmd
    vs_community.exe --layout c:\vslayout --add Microsoft.VisualStudio.Workload.ManagedDesktop --add Microsoft.VisualStudio.Workload.Office --includeOptional --lang en-US
    ```

- C++ Masaüstü geliştirmesi için çalıştırın:

   ```cmd
    vs_community.exe --layout c:\vslayout --add Microsoft.VisualStudio.Workload.NativeDesktop --includeRecommended --lang en-US
    ```

- Tüm özellikleri ile tam olarak yerel bir düzen oluşturmak için (Bu uzun sürer&mdash;sahibiz _çok_ özelliklerinin!) çalıştırın:

   ```cmd
    vs_community.exe --layout c:\vslayout --lang en-US
    ```

::: moniker range="vs-2017"

   > [!NOTE]
   > Tamamen Visual Studio düzeni en az 35 GB disk alanı gerektirir. Daha fazla bilgi için bkz. [sistem gereksinimleri](/visualstudio/productinfo/vs2017-system-requirements-vs/). Yalnızca yüklemek istediğiniz bileşenleri içeren bir düzen oluşturma hakkında bilgi için bkz. [Visual Studio 'yu yüklemek için komut satırı parametrelerini kullanma](use-command-line-parameters-to-install-visual-studio.md).

::: moniker-end

::: moniker range="vs-2019"

   > [!NOTE]
   > Tamamen Visual Studio düzeni en az 35 GB disk alanı gerektirir. Daha fazla bilgi için bkz. [sistem gereksinimleri](/visualstudio/releases/2019/system-requirements/). Yalnızca yüklemek istediğiniz bileşenleri içeren bir düzen oluşturma hakkında bilgi için bkz. [Visual Studio 'yu yüklemek için komut satırı parametrelerini kullanma](use-command-line-parameters-to-install-visual-studio.md).

::: moniker-end

İngilizce dışında bir dil yüklemek isterseniz değiştirme `en-US` yerel için [dil yerel ayarlar listesini](#list-of-language-locales). Ardından, [kullanılabilir iş yükleri ve bileşenlerin listesini](workload-and-component-ids.md) yükleme önbelleğiniz daha fazla özelleştirmek için.

### <a name="step-3---install-visual-studio-from-the-local-cache"></a>Adım 3 - yerel önbellekten Visual Studio yükleme

> [!TIP]
> Yerel Yükleme önbellekten çalıştırdığınızda, Kurulum bu dosyaların her biri yerel sürümünü kullanır. Ancak önbellekte olmayan bileşenleri yüklemesi sırasında seçerseniz, bunları internet'ten indirmek Kurulum çalışır.

Yalnızca daha önce indirilen dosyaları yüklediğinizden emin olmak için Düzen önbelleği oluşturmak için kullanılan aynı komut satırı seçeneklerini kullanın. Örneğin, aşağıdaki komutla bir düzen önbelleği oluşturduysanız:

```cmd
vs_community.exe --layout c:\vslayout --add Microsoft.VisualStudio.Workload.ManagedDesktop --add Microsoft.VisualStudio.Workload.NetWeb --add Component.GitHub.VisualStudio --includeOptional --lang en-US
```

Ardından yüklemesini çalıştırmak için bu komutu kullanın:

```cmd
c:\vslayout\vs_community.exe --add Microsoft.VisualStudio.Workload.ManagedDesktop --add Microsoft.VisualStudio.Workload.NetWeb --add Component.GitHub.VisualStudio --includeOptional
```

> [!NOTE]
> İmza geçersiz olduğunu belirten bir hata alırsanız, güncelleştirilmiş bir sertifika yüklemeniz gerekir. Çevrimdışı önbelleğinize sertifikaları klasörünü açın. Her sertifika dosyasını çift tıklayın ve Sertifika Yöneticisi sihirbazda'ye tıklayın. İçin bir parola istenirse, boş bırakın.

### <a name="list-of-language-locales"></a>Dil yerel ayarlar listesi

| **Dil yerel ayar** | **Dil** |
| ----------------------- | --------------- |
| cs-CZ | Çekçe |
| de-DE | Almanca |
| en-US | İngilizce |
| es-ES | İspanyolca |
| fr-FR | Fransızca |
| İt-IT | İtalyanca |
| ja-JP | Japonca |
| ko-KR | Korece |
| pl-PL | Lehçe |
| pt-BR | Portekizce - Brezilya |
| ru-RU | Rusça |
| tr-TR | Türkçe |
| zh-CN | Çince - Basitleştirilmiş |
| zh-TW | Çince - Geleneksel |

[!INCLUDE[install_get_support_md](includes/install_get_support_md.md)]

## <a name="see-also"></a>Ayrıca bkz.

- [Visual Studio'nun bir ağ oluşturun](../install/create-a-network-installation-of-visual-studio.md)
- [Visual Studio’nun ağ tabanlı yüklemesini güncelleştirme](update-a-network-installation-of-visual-studio.md)
- [Visual Studio'yu çevrimdışı yükleme için gerekli sertifikaları yükleme](../install/install-certificates-for-visual-studio-offline.md)
- [Komut satırı parametrelerini kullanarak Visual Studio'yu yükleme](use-command-line-parameters-to-install-visual-studio.md)
- [Visual Studio iş yükü ve bileşen kimlikleri](workload-and-component-ids.md)
