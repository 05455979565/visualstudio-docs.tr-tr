---
title: Yük testi Visual Studio için bir eşik kuralı ekleme
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, monitoring
- load tests, thresholds
- load tests, analyzing
- thresholds in load tests
ms.assetid: 3d8fac8f-426f-4155-9ced-f7cd4c79792c
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: f68ab9b183119c18bed51bb7faaa86993d7f34ce
ms.sourcegitcommit: 5b767247b3d819a99deb0dbce729a0562b9654ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/20/2018
ms.locfileid: "39179885"
---
# <a name="how-to-add-a-threshold-rule-using-the-load-test-editor"></a>Nasıl yapılır: Yük Testi Düzenleyicisini kullanarak bir eşik kuralı ekleme

Yük testlerindeki eşik kuralları, bir performans sayacı değeri bir sabit değer ya da başka bir performans sayacı değeri ile karşılaştırın.

## <a name="to-add-a-threshold-rule"></a>Eşik kuralı ekleme

1.  Bir yük testi açın.

2.  Yük Testi Düzenleyicisi'nde genişletin **sayaç kümeleri** düğümü.

3.  Birini genişletin **sayaç kategorileri** sayaç kümelerinden birinde. Örneğin, seçebileceğiniz **YüklemeTesti**. Düğümünü genişletin.

4.  Örneğin, sayaçları birine sağ tıklayın **kullanıcı yükü**altında **YüklemeTesti**. Seçin **eşik kuralı ekleme**.

     **Eşik Kuralı Ekle** iletişim kutusu görüntülenir.

5.  Kurallar iki türlerinden birini seçebilirsiniz: **Sabiti Karşılaştır** ve **sayacı Karşılaştır**. Uygun türünü seçin ve şu değerleri ayarlayın.

    > [!NOTE]
    > Ayarlama **aşarsa uyar** özelliğini **True** bir Eşiği aşan bir sorun olduğunu belirtmek için veya **False** eşiğin altında kalan bir sorun olduğunu belirtmek için.

## <a name="see-also"></a>Ayrıca bkz.

- [Eşik kuralı ihlallerini çözümleme](../test/analyze-threshold-rule-violations-in-load-tests.md)
- [Sayaç kümelerini ve eşik kurallarını bilgisayarlar için bir yük testi içinde belirtin.](../test/specify-counter-sets-and-threshold-rules-for-load-testing.md)
- [Yük testi sonuçlarını çözümleme](../test/analyze-load-test-results-using-the-load-test-analyzer.md)
