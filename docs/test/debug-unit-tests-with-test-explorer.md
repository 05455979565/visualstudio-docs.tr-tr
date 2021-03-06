---
title: Test Gezgini ile birim testlerinde hata ayıklama
description: Visual Studio 'da test Gezgini ile birim testlerinde hata ayıklamayı nasıl ayıklayacağınızı öğrenin.
ms.date: 07/14/2020
ms.topic: how-to
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 2def56c6a3860ce0476f448f87bdde25c7970807
ms.sourcegitcommit: a77158415da04e9bb8b33c332f6cca8f14c08f8c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/15/2020
ms.locfileid: "86393527"
---
# <a name="debug-and-analyze-unit-tests-with-test-explorer"></a>Test Gezgini ile birim testlerini hata ayıklama ve çözümleme

Testleriniz için bir hata ayıklama oturumu başlatmak üzere test Gezgini ' ni kullanabilirsiniz. Visual Studio hata ayıklayıcı ile kodunuzda adım adım geçiş, birim testleri ve test edilen proje arasında sorunsuz bir şekilde geri ve ileri doğru bir şekilde gerçekleşir. Hata ayıklamayı başlatmak için:

1. Visual Studio düzenleyicisinde, hata ayıklamak istediğiniz bir veya daha fazla test yöntemlerinde bir kesme noktası ayarlayın.

    > [!NOTE]
    > Test yöntemleri herhangi bir sırada çalıştırılabildiğinden, hata ayıklamak istediğiniz tüm test yöntemlerinde kesme noktaları ayarlayın.

::: moniker range="vs-2017"
2. Test Gezgini 'nde test yöntemleri ' ni seçin ve sağ tıklama menüsünde **Seçili testlerin hatalarını ayıkla** ' yı seçin.
::: moniker-end
::: moniker range=">=vs-2019"
2. Test Gezgini 'nde test yöntemleri ' ni seçin ve sağ tıklama menüsünde **Hata Ayıkla** ' yı seçin.

   ![Test yürütme ayrıntıları](../test/media/vs-2019/test-explorer-debug.png)
::: moniker-end

   Hata ayıklayıcı hakkında daha fazla bilgi için bkz. [Visual Studio 'Da hata ayıklama](../debugger/debugger-feature-tour.md).

## <a name="diagnose-test-method-performance-issues"></a>Test yöntemi performans sorunlarını tanılama

::: moniker range="vs-2017"
Bir test yönteminin neden çok fazla zaman aldığını tanılamak için test Gezgini 'nde yöntemi seçin ve sağ tıklama menüsünde **profil seçili test** ' i seçin. Bkz. [izleme profili oluşturma raporu](../profiling/understanding-instrumentation-data-values.md?view=vs-2017).
::: moniker-end

::: moniker range=">=vs-2019"
Test yönteminin neden çok fazla zaman aldığını tanılamak için test Gezgini 'nde yöntemi seçin ve sağ tıklama menüsünde **profil** ' i seçin. Bkz. [izleme profili oluşturma raporu](../profiling/understanding-instrumentation-data-values.md?view=vs-2017).
::: moniker-end

> [!NOTE]
> Bu özellik şu anda .NET Core için desteklenmiyor.

## <a name="see-also"></a>Ayrıca bkz.

- [Kodunuzun birim testi](../test/unit-test-your-code.md)
- [Test Gezgini ile birim testleri çalıştırma](../test/run-unit-tests-with-test-explorer.md)
- [Test Gezgini Hakkında SSS](test-explorer-faq.md)
