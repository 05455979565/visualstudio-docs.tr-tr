---
title: Test denetleyicileri ve Test aracıları için bağlantı noktalarını yapılandırma
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- firewalls, configuring for test agents
- firewalls, configuring for test controllers
- test agents, firewalls
- test controllers, firewalls
- agents, firewalls
- controllers, firewalls
ms.assetid: 211edbd7-9fe4-4251-ba85-8bec4363261b
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: bd66bcb3615477abc2fc9a8122f2ec4675f37bbb
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62965828"
---
# <a name="configure-ports-for-test-controllers-and-test-agents"></a>Test denetleyicileri için bağlantı noktalarını yapılandırın ve test aracıları

Test denetleyicisi, test aracısı ve istemci tarafından kullanılan varsayılan gelen bağlantı noktalarını değiştirebilirsiniz. Bu test denetleyicisi, test aracısı veya başka bir yazılımla istemci bağlantı noktası ayarlarıyla çakışan kullanmaya çalışıyorsanız gerekli olabilir. Bağlantı noktalarını değiştirmek için başka bir test denetleyicisi ve istemci arasındaki güvenlik duvarı kısıtlamasıdır nedenidir. Bu durumda el ile test denetleyicisi sonuçları istemciye gönderebilmesi için bir güvenlik duvarı etkinleştirmesini karşılamak için bağlantı noktası yapılandırmak isteyebilirsiniz.

[!INCLUDE [web-load-test-deprecated](includes/web-load-test-deprecated.md)]

Aşağıdaki çizim, test denetleyicisi, test aracısı ve istemci arasındaki bağlantı noktalarını gösterir. Bunu, bu bağlantı noktalarındaki güvenlik kısıtlamalarını yanı sıra gelen ve giden bağlantılar için hangi bağlantı noktalarının kullanılan açıklar.

![Test denetleyicisi ve test aracısı bağlantı noktaları ve güvenlik](../test/media/test-controller-agent-firewall.png)

## <a name="incoming-connections"></a>Gelen bağlantılar

6901 test denetleyicisi tarafından kullanılan varsayılan bağlantı noktasıdır ve 6910 test aracısın varsayılan bağlantı noktasıdır. İstemci, test denetleyicisinden test sonuçlarını almak için kullanılan varsayılan olarak rastgele bir bağlantı noktası kullanır. Tüm gelen bağlantıları için test denetleyicisi çağıran tarafın kimliğini doğrular ve belirli bir güvenlik grubuna ait olduğunu doğrular.

- **Test denetleyicisi** gelen bağlantılar, TCP port 6901 üzerindedir. Gerekirse, gelen bağlantı noktası yapılandırabilirsiniz. Daha fazla bilgi için [gelen bağlantı noktalarını yapılandırma](#configure-the-incoming-ports).

    Test denetleyicisi test aracısına giden bağlantıyı sağlayabilmelidir gerekiyor ve istemciye.

    > [!NOTE]
    > Test denetleyicisi gelen gereken **dosya ve Yazıcı Paylaşımı** bağlantı açık.

- **Test aracısı** gelen bağlantılar, TCP port 6910 üzerindedir. Gerekirse, gelen bağlantı noktası yapılandırabilirsiniz. Daha fazla bilgi için [gelen bağlantı noktalarını yapılandırma](#configure-the-incoming-ports).

   Test aracısı test denetleyicisine giden bağlantıyı sağlayabilmelidir gerekir.

- **İstemci** varsayılan olarak, rastgele bir TCP bağlantı noktası gelen bağlantılar için kullanılır. Gerekirse, gelen bağlantı noktası yapılandırabilirsiniz. Daha fazla bilgi için [gelen bağlantı noktalarını yapılandırma](#configure-the-incoming-ports).

   Test denetleyicisi istemciye ilk kez bağlanmaya çalıştığında güvenlik duvarı bildirimlerini alabilirsiniz.

   Windows Server 2008'de güvenlik duvarı bildirimleri varsayılan olarak devre dışıdır ve istemci programları için güvenlik duvarı özel durumlarını el ile eklemeniz gerekir (*devenv.exe*, *mstest.exe*, *mlm.exe*) gelen bağlantıları kabul edebilmesi için.

## <a name="outgoing-connections"></a>Giden bağlantılar

Rastgele TCP bağlantı noktaları tüm giden bağlantılar için kullanılır.

- **Test denetleyicisi** test denetleyicisi aracılara ve istemciye giden bağlantıyı sağlayabilmelidir gerekiyor.

- **Test aracısı** test aracısı denetleyiciye giden bağlantıyı sağlayabilmelidir gerekiyor.

- **İstemci** istemcinin denetleyicisine giden bağlantıyı sağlayabilmelidir gerekir.

## <a name="configure-the-incoming-ports"></a>Gelen bağlantı noktalarını yapılandırma

Bir test denetleyicisi için bağlantı noktalarını yapılandırmak ve test aracıları için aşağıdaki yönergeleri izleyin.

- **Denetleyici Hizmeti** düzenleyerek bağlantı noktasının değerini değiştirip *% ProgramFiles (x86) %\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\QTCcontroller.exe.config* dosyası:

    ```xml
    <appSettings>
      <add key="ControllerServicePort" value="6901"/>
    </appSettings>
    ```

- **Aracı hizmeti** düzenleyerek bağlantı noktasını değiştirmek *% ProgramFiles (x86) %\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\QTAgentService.exe.config* dosyası:

    ```xml
    <appSettings>
      <add key="AgentServicePort" value="6910"/>
    </appSettings>
    ```

- **İstemci** aşağıdaki kayıt defteri eklemek için kayıt defteri düzenleyicisini kullanıp (**DWORD**) değerleri. Test denetleyicisinden veri almak için istemci belirtilen aralık bağlantı noktalarından birini kullanır:

     **HKEY_LOCAL_MACHINE\SOFTWARE\MICROSOFT\VisualStudio\12.0\EnterpriseTools\QualityTools\ListenPortRange\PortRangeStart**

     **HKEY_LOCAL_MACHINE\SOFTWARE\MICROSOFT\VisualStudio\12.0\EnterpriseTools\QualityTools\ListenPortRange\PortRangeEnd**

## <a name="see-also"></a>Ayrıca bkz.

- [Test aracılarını yükleme ve yapılandırma](../test/lab-management/install-configure-test-agents.md)