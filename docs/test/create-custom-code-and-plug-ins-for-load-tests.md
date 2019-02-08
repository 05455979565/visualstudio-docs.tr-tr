---
title: Yük testleri için özel kod ve eklentiler oluşturma
ms.date: 10/19/2016
ms.topic: conceptual
f1_keywords:
- vs.test.dialog.recorderplugin
helpviewer_keywords:
- Web performance tests, plug-ins
- load tests, plug-ins
ms.assetid: 0c0fcc99-673b-4ea0-a268-0475f66e5cb6
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 8382d5014b88d9f1711a082e46530e1e3dfb96e4
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/08/2019
ms.locfileid: "55956018"
---
# <a name="create-custom-code-and-plug-ins-for-load-tests"></a>Yük testleri için özel kod ve eklentiler oluşturma

Özel bir eklenti yazma ve yük testi ya da bir web performans testi ekleme kodu kullanır. Yerleşik işlevselliği genişletmek testler için özel eklentiler oluşturma için yük testi API'si ve web performans testi API'ı kullanabilirsiniz. Yük testinize birden fazla eklenti ekleyebilirsiniz.

[!INCLUDE [web-load-test-deprecated](includes/web-load-test-deprecated.md)]

## <a name="tasks"></a>Görevler

|Görevler|İlişkili konular|
|-|-----------------------|
|**Özel bir yük testi eklentisi oluşturma**: Yük testi API, özel bir Yük testiniz için daha fazla işlevsellik eklemek için eklenti oluşturmak için kullanabilirsiniz.|-   [Nasıl Yapılır: Yük testi API'si kullanma](../test/how-to-use-the-load-test-api.md)<br />-   [Nasıl Yapılır: Bir yük testi eklentisi oluşturma](../test/how-to-create-a-load-test-plug-in.md)|
|**Özel bir Web performans testiniz için eklenti oluşturun:** Web performans testi API, özel bir web performans testi isteği düzeyinde de dahil olmak üzere, daha fazla test işlevselliği eklemek için eklenti oluşturmak için kullanabilirsiniz. Ayrıca, bir web hizmetini test oluşturabilirsiniz.<br /><br /> Ayrıca, bir web performans testi kaydedildikten sonra ancak Web Performans Testi Sonuç Görüntüleyicisi'nde göründüğü önce değiştirebileceğiniz bir web kaydedici eklentisi oluşturabilirsiniz.|-   [Nasıl Yapılır: Web performans testi API'si kullanma](../test/how-to-use-the-web-performance-test-api.md)<br />-   [Nasıl Yapılır: Bir web performans testi eklentisi oluşturma](../test/how-to-create-a-web-performance-test-plug-in.md)<br />-   [Nasıl Yapılır: İstek düzeyi eklentisi oluşturma](../test/how-to-create-a-request-level-plug-in.md)<br />-   [Nasıl Yapılır: Web hizmeti testi oluşturma](../test/how-to-create-a-web-service-test.md)<br />-   [Nasıl Yapılır: Kaydedici eklentisi oluşturma](../test/how-to-create-a-recorder-plug-in.md)|
|**Web Performans Test Sonuçları Görüntüleyicisi için kullanıcı Arabirimi özellikleri ekleyin:** Visual Studio eklentisini kullanarak Web Performans Test Sonuçları Görüntüleyicisi için daha fazla kullanıcı Arabirimi özelliklerini ekleyebilirsiniz.|-   [Nasıl Yapılır: Visual Studio eklentisi web performans test sonuçları Görüntüleyicisi için oluşturma](../test/how-to-create-an-add-in-for-the-web-performance-test-results-viewer.md)|
|**Özel HTTP Gövde Düzenleyicisi oluşturma:** Bir web hizmetinden http XML yanıtlarını ikili veya dizesini düzenlemek için özel bir düzenleyici oluşturabilirsiniz.|-   [Nasıl Yapılır: Özel HTTP Gövde Düzenleyicisi için web performans testi Düzenleyicisi oluşturma](../test/how-to-create-a-custom-http-body-editor-for-the-web-performance-test-editor.md)|

## <a name="reference"></a>Başvuru

<xref:Microsoft.VisualStudio.TestTools.WebTesting.WebTestPlugin>

<xref:Microsoft.VisualStudio.TestTools.WebTesting.WebTestRequestPlugin>

<xref:Microsoft.VisualStudio.TestTools.LoadTesting.ILoadTestPlugin>

<xref:Microsoft.VisualStudio.TestTools.WebTesting.WebTestRecorderPlugin>

<xref:Microsoft.VisualStudio.TestTools.LoadTesting>

## <a name="see-also"></a>Ayrıca bkz.

- [Yük testi sonuçlarını çözümleme](../test/analyze-load-test-results-using-the-load-test-analyzer.md)
- [Oluşturma ve bir kodlanmış web performans testini çalıştırma](../test/generate-and-run-a-coded-web-performance-test.md)