---
title: Bir sürümden sonra paket yükleri değiştiğinde
description: Bir düzen oluştururken, bir yayın zaten gönderildikten sonra paket yüklerin değişip değişmediğini belirlemeyi öğrenin.
ms.date: 05/22/2019
ms.topic: how-to
author: ornellaalt
ms.author: ornella
manager: jillfra
ms.workload:
- multiple
ms.prod: visual-studio-windows
ms.technology: vs-installation
ms.openlocfilehash: 135a89534b17a509d75616b0819dae112901fef3
ms.sourcegitcommit: 9e15138a34532b222e80f6b42b1a9de7b2fe0175
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/26/2020
ms.locfileid: "85419256"
---
# <a name="package-payload-changes"></a>Paket yükü değişiklikleri

Bir yayın zaten sevk edildikten sonra bazı paket yüklerin değiştirilmesine izin verilir. Siz veya başka biri bir düzen oluşturduğunda, bu davranış, bir düzenin ne zaman oluşturulduğuna bağlı olarak farklı düzen içeriğine yol açabilir.

## <a name="verify-that-a-layout-includes-package-payload-changes"></a>Bir düzenin paket yükü değişikliklerini içerdiğini doğrulama

Daha önce oluşturulmuş olan düzenin, yayın gönderildikten sonra değiştirilen paket yüklerini elde ettiği belirlenir:

1. Kurulum günlüğünü açın. Günlük genellikle `%TEMP%\dd_setup_[date].log` `[date]` Düzen işleminin biçimde başladığı yerdir `yyyyMMddHHmmss` .

2. Günlükte aşağıdaki metin gibi yapılandırılmış bir satırı arayın:

    `Falling back to signature and signer check because hash verification returned HashMismatch for path: [path]`

3. Daha sonra, [Path] için indirme başarılı olduğunu belirten günlükte daha sonra satırları arayın. Şu metne benzer görünebilir:

    `Download of [url] succeeded using engine 'WebClient'`

    `END: Downloading [url] to [path]`

## <a name="see-also"></a>Ayrıca bkz.

* [Visual Studio 'nun ağ yüklemesi oluşturma](create-a-network-installation-of-visual-studio.md)
* [Visual Studio 'nun ağ tabanlı yüklemesini güncelleştirme](update-a-network-installation-of-visual-studio.md)
