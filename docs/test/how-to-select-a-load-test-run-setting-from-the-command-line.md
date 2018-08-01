---
title: Komut satırından Visual Studio Yük testi çalıştırma ayarlarını ayarlayın
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, command line
- load tests, run settings, selecting
ms.assetid: 175d1d58-f09a-4449-b132-a29a394a7c8e
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: 263f8a671897b5f9c8af835f13214139e3abef17
ms.sourcegitcommit: 495bba1d8029646653f99ad20df2f80faad8d58b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/31/2018
ms.locfileid: "39382483"
---
# <a name="how-to-select-a-load-test-run-setting-to-use-from-the-command-line"></a>Nasıl yapılır: yük testi çalıştırması komut satırından kullanmak için ayarı seçin

Bir yük testi içerebilir *çalıştırma ayarları*, yük testinin çalışma biçimini etkileyen özellikler şunlardır. Çalıştırma ayarları kategorilere göre düzenlenir **özellikleri** penceresi. Bir yük testi çalıştırdığınızda, şu anda etkin olarak ayarlanmış çalıştırma ayarını kullanır.

 Yük testiniz yalnızca bir çalışma ayarı içeriyorsa, her zaman etkin düğüm olur. Yük testi çalıştırma ayarları birden çok düğüm içeriyorsa, komut satırından bir yük testi çalıştırdığınızda kullanılacak seçebilirsiniz. Bkz: [nasıl yapılır: bir yük testine ek çalışma ayarları ekleme](../test/how-to-add-additional-run-settings-to-a-load-test.md).

## <a name="to-change-the-run-setting-from-the-command-line"></a>Komut satırından çalıştırma ayarını değiştirmek için

1.  Bağlam parametresi stratejisi yararlanmak için farklı çalıştırma ayarları komut satırından kullanmak istiyorsanız, aşağıdaki komutu kullanın:

    `Set Test.UseRunSetting= CorporateStagingWebServer`

2.  MSTest kullanarak yük testini çalıştırın:

    `mstest /testcontainer:loadtest1.loadtest`

## <a name="see-also"></a>Ayrıca bkz.

- [Yük testi çalıştırma ayarlarını yapılandırma](../test/configure-load-test-run-settings.md)
- [Sayaç kümelerini ve eşik kurallarını bilgisayarlar için bir yük testi içinde belirtin.](../test/specify-counter-sets-and-threshold-rules-for-load-testing.md)
- [Nasıl yapılır: bir yük testine ek çalışma ayarları ekleme](../test/how-to-add-additional-run-settings-to-a-load-test.md)
- [Nasıl yapılır: etkin çalışma yük testi için ayarı seçin](../test/how-to-select-the-active-run-setting-for-a-load-test.md)
