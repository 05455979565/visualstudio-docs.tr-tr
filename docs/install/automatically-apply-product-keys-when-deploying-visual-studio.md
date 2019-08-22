---
title: Ürün anahtarlarını otomatik olarak uygulama
description: Visual Studio'yu dağıtırken ürün anahtarlarını program aracılığıyla uygulama hakkında bilgi edinin.
ms.date: 04/10/2019
ms.custom: seodec18
ms.topic: conceptual
ms.assetid: d79260be-6234-4fd3-89b5-a9756b4a93c1
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.prod: visual-studio-windows
ms.technology: vs-installation
ms.openlocfilehash: dabaf63e205d3e76432767743e323c90ed389846
ms.sourcegitcommit: 673b9364fc9a96b027662dcb4cf5d61cab60ef11
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/21/2019
ms.locfileid: "69891302"
---
# <a name="automatically-apply-product-keys-when-deploying-visual-studio"></a>Visual Studio’yu dağıtırken ürün anahtarlarını otomatik olarak uygulama

Ürün anahtarınızı program aracılığıyla Visual Studio'nun dağıtımı otomatik hale getirmek için kullanılan bir betiği bir parçası olarak uygulayabilirsiniz. Bir ürün anahtarı bir cihazda program aracılığıyla Visual Studio'nun veya bir yükleme tamamlandıktan sonra yükleme sırasında ya da ayarlayabilirsiniz.

## <a name="apply-the-license-after-installation"></a>Yüklemeden sonra lisans Uygula

::: moniker range="vs-2017"

Visual Studio yüklü bir sürümü ile bir ürün anahtarı kullanarak etkinleştirebilirsiniz `StorePID.exe` yardımcı programı hedef makinelerde sessiz modda. `StorePID.exe` Visual Studio 2017 aşağıdaki varsayılan konuma yükler bir hizmet programıdır: <br> `C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\IDE`

::: moniker-end

::: moniker range="vs-2019"

Visual Studio yüklü bir sürümü ile bir ürün anahtarı kullanarak etkinleştirebilirsiniz `StorePID.exe` yardımcı programı hedef makinelerde sessiz modda. `StorePID.exe`, aşağıdaki varsayılan konumda Visual Studio 2019 ile yüklenen bir yardımcı programdır: <br> `C:\Program Files (x86)\Microsoft Visual Studio\2019\Enterprise\Common7\IDE`

::: moniker-end

 Çalıştırma `StorePID.exe` yükseltilmiş ayrıcalıklarla kullanarak ya da System Center aracı ya da yükseltilmiş bir komut istemi. Bu ürün anahtarını ve Microsoft ürün kodu (MPC) ile izleyin.

>[!IMPORTANT]
> Ürün anahtarı tireler dahil ettiğinizden emin olun.

 ```cmd
 StorePID.exe [product key including the dashes] [MPC]
 ```

::: moniker range="vs-2017"

Aşağıdaki örnek, Visual Studio 2017 bir MPC 08860 biri olan bir kuruluş için lisans uygulamak için bir komut satırı gösterir. bir ürün anahtarı `AAAAA-BBBBB-CCCCC-DDDDDD-EEEEEE`, varsayılan yükleme konumu varsayar:

```cmd
"C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\StorePID.exe" AAAAA-BBBBB-CCCCC-DDDDDD-EEEEEE 08860
```

::: moniker-end

::: moniker range="vs-2019"

Aşağıdaki örnek, MPC/09260, ürün anahtarı `AAAAA-BBBBB-CCCCC-DDDDDD-EEEEEE`ve varsayılan yükleme konumunu varsayan Visual Studio 2019 Enterprise lisansını uygulamak için bir komut satırı gösterir:

```cmd
"C:\Program Files (x86)\Microsoft Visual Studio\2019\Enterprise\Common7\IDE\StorePID.exe" AAAAA-BBBBB-CCCCC-DDDDDD-EEEEEE 09260
```

::: moniker-end

::: moniker range="vs-2017"

 Aşağıdaki tablo, Visual Studio'nun her sürümü için MPC kodları listeler:

| Visual Studio sürümü                | MPC   |
|--------------------------------------|-------|
| Visual Studio Enterprise 2017        | 08860 |
| Visual Studio Professional 2017      | 08862 |
| Visual Studio Test Uzmanı 2017 | 08866 |

::: moniker-end

::: moniker range="vs-2019"

| Visual Studio sürümü                | MPC   |
|--------------------------------------|-------|
| Visual Studio Enterprise 2019        | 09260 |
| Visual Studio Professional 2019      | 09262 |

::: moniker-end

Varsa `StorePID.exe` başarıyla döndürür ürün anahtarı geçerli bir `%ERRORLEVEL%` 0. Hatalarla karşılaştığında, hata durumu bağlı olarak aşağıdaki kodlarından birini döndürür:

| Hata                     | Kod |
|---------------------------|------|
| `PID_ACTION_SUCCESS`      | 0    |
| `PID_ACTION_NOTINSTALLED` | 1\.    |
| `PID_ACTION_INVALID`      | 2    |
| `PID_ACTION_EXPIRED`      | 3    |
| `PID_ACTION_INUSE`        | 4    |
| `PID_ACTION_FAILURE`      | 5    |
| `PID_ACTION_NOUPGRADE`    | 6    |

[!INCLUDE[install_get_support_md](includes/install_get_support_md.md)]

> [!NOTE]
> Sanal örneklerde sorun giderme için, *C:\Program Files (x86) \Microsoft Visual Studio \<Version\>\Common7\IDE\DDConfigCA.exe*çalıştırın.

## <a name="see-also"></a>Ayrıca bkz.

* [Visual Studio'yu yükleyin](../install/install-visual-studio.md)
* [Visual Studio’nun çevrimdışı yüklemesini oluşturma](../install/create-an-offline-installation-of-visual-studio.md)
