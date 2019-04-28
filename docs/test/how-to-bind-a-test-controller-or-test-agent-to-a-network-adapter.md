---
title: Bir ağ bağdaştırıcısına bir Test denetleyicisi veya Test aracısı bağlama
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- controllers, netwrok adapter
- agents, configuring
- agents, network adapter
- controllers, configuring
ms.assetid: 7eb9290a-f9f6-4e41-9caa-796fcfaf0610
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: dfcbac0bb9188826804ba13884f0f57962dddeab
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62979337"
---
# <a name="how-to-bind-a-test-controller-or-test-agent-to-a-network-adapter"></a>Nasıl yapılır: Bir ağ bağdaştırıcısına bir test denetleyicisi veya test aracısı bağlama

Test denetleyicisi veya test aracısı yazılımı yüklü olduğu bir bilgisayarda birden çok ağ bağdaştırıcısı varsa, test denetleyicisi veya test aracısının belirlemek için bilgisayar adı yerine IP adresi belirtmeniz gerekir.

> [!WARNING]
> Bir test ajanı ayarlamaya çalıştığınızda şu hatayı alabilirsiniz:
>
> **8110 hata oluştu. Değil belirtilen denetleyici bilgisayara bağlanabilir ya denetleyicisi nesneye erişim**
>
> Birden fazla ağ bağdaştırıcısı olan bir bilgisayarda test denetleyicisi yükleyerek bu hatayı neden olabilir. Aracıları başarıyla yükleyip, bu sorunla bir testi çalıştırmaya çalışana kadar karşılaşmamanız da olasıdır.

[!INCLUDE [web-load-test-deprecated](includes/web-load-test-deprecated.md)]

## <a name="bind-a-test-controller-to-a-specific-network-adapter"></a>Belirli bir ağ bağdaştırıcısına bir test denetleyicisi bağlama

### <a name="to-obtain-the-ip-addresses-of-the-network-adapters"></a>Ağ bağdaştırıcılarının IP adreslerini almak için

1. Microsoft Windows seçin **Başlat**, seçin **Aramaya Başla** kutusuna **cmd**ve ardından **Enter**.

2. Tür **ipconfig/all**.

     Ağ bağdaştırıcılarınız için IP adresleri görüntülenir. Denetleyicinizi bağlamak istediğiniz ağ bağdaştırıcısının IP adresini kaydedin.

### <a name="to-bind-a-network-adapter-to-a-test-controller"></a>Bir ağ bağdaştırıcısına bir test Denetleyicisi'ne bağlamak için

1. Microsoft Windows seçin **Başlat**, seçin **Aramaya Başla** kutusuna **services.msc**ve ardından **Enter**.

     **Hizmetleri** iletişim kutusu görüntülenir.

2. Sonuçlar bölmesinde altında **adı** sütun sağ **Visual Studio Test denetleyicisi** hizmet ve ardından **Durdur**.

     veya

     Yükseltilmiş bir komut istemi açın ve komut istemine aşağıdaki komutu çalıştırın:

     `net stop vsttcontroller`

3. Açık *QTCcontroller.exe.config* bulunan XML yapılandırma dosyasını *% ProgramFiles (x86) %\Microsoft Visual Studio\2017\\\<sürümü > \Common7\IDE*.

4. bulun `<appSettings>` etiketi.

    ```xml
    <appSettings>
      <add key="LogSizeLimitInMegs" value="20"/>
      <add key="AgentConnectionTimeoutInSeconds" value="120"/>
      <add key="AgentSyncTimeoutInSeconds" value="300"/>
      <add key="ControllerServicePort" value="6901"/>
      <add key="ControllerUsersGroup" value="TeamTestControllerUsers"/>
      <add key="ControllerAdminsGroup" value="TeamTestControllerAdmins"/>
      <add key="CreateTraceListener" value="no"/>
    </appSettings>
    ```

5. Ekleme `BindTo` hangi ağ bağdaştırıcısının kullanılacağını belirlemek için anahtar `<appSettings>` bölümü.

    ```xml
            <add key="BindTo" value="<YOUR IP ADDRESS>"/>
    </appSettings>
    ```

6. Test denetleyicisi hizmetini başlatın. Bunu yapmak için bir komut isteminde aşağıdaki komutu çalıştırın:

    `net start vsttcontroller`

    > [!WARNING]
    > Test aracısı yüklemesini yeniden test aracısı denetleyiciye bağlanmak için çalıştırmanız gerekir. Bu kez, denetleyici adı yerine denetleyicisinin IP adresini belirtin.

     Bu, denetleyici, aracı hizmeti ve aracı işlemine uygulanır. `BindTo` Özelliği, birden fazla ağ bağdaştırıcısı olan bir bilgisayarda çalışan her işlem için ayarlanmalıdır. Ayarlamaya ilişkin yordam `BindTo` özelliği olduğundan, test denetleyicisi için bu konunun önceki kısımlarında belirtildiği gibi her üç işlem için aynıdır.

### <a name="to-bind-a-network-interface-card-to-a-test-agent"></a>Bir test aracısı için bir ağ arabirimi kartı bağlamak için

1. Microsoft Windows seçin **Başlat**, seçin **Aramaya Başla** kutusuna **services.msc**ve ardından **Enter**.

    **Hizmetleri** iletişim kutusu görüntülenir.

2. Sonuçlar bölmesinde altında **adı** sütun sağ **Visual Studio Test aracısı** hizmet ve ardından **Durdur**.

     veya

     Yükseltilmiş bir komut istemi açın ve komut istemine aşağıdaki komutu çalıştırın:

     **net stop vsttagent**

3. Açık *QTAgentService.exe.config* bulunan XML yapılandırma dosyasını *% ProgramFiles (x86) %\Microsoft Visual Studio\2017\\\<sürümü > \Common7\IDE*.

4. bulun `<appSettings>` etiketi.

    ```xml
    <appSettings>
      <appSettings>
      <add key="LogSizeLimitInMegs" value="20"/>
      <add key="AgentServicePort" value="6910"/>
      <add key="ControllerConnectionPeriodInSeconds" value="30"/>
      <add key="StopTestRunCallTimeoutInSeconds" value="120"/>
      <add key="CreateTraceListener" value="no"/>
      <add key="GetCollectorDataTimeout" value="300"/>
    </appSettings>  </appSettings>
    ```

5. Ekleme `BindTo` hangi ağ bağdaştırıcısının kullanılacağını belirlemek için anahtar `<appSettings>` bölümü.

    ```xml
            <add key="BindTo" value="<YOUR IP ADDRESS>"/>
    </appSettings>
    ```

6. Test aracısı hizmetini başlatın. Bunu yapmak için bir komut isteminde aşağıdaki komutu çalıştırın:

    `net start vsttagent`

## <a name="see-also"></a>Ayrıca bkz.

- [Test aracılarını yükleme ve yapılandırma](../test/lab-management/install-configure-test-agents.md)
- [Yük testi günlüğü ayarlarını değiştirme](../test/modify-load-test-logging-settings.md)
- [Test denetleyicileri için bağlantı noktalarını yapılandırın ve test aracıları](../test/configure-ports-for-test-controllers-and-test-agents.md)
- [Nasıl yapılır: Test denetleyicileri için zaman aşımı sürelerini belirtme ve test aracıları](../test/how-to-specify-timeout-periods-for-test-controllers-and-test-agents.md)