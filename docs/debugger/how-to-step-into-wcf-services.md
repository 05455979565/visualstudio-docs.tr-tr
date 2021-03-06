---
title: WCF hizmetlerine nasıl adımla | Microsoft Docs
ms.date: 11/04/2016
ms.topic: how-to
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging, WCF
- WCF, debugging
ms.assetid: 9893ad01-54af-499f-85a6-9d1cfe6eb640
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: fa4097280ae388a9a941c017697e0a5e3daa44cd
ms.sourcegitcommit: c076fe12e459f0dbe2cd508e1294af14cb53119f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2020
ms.locfileid: "85349126"
---
# <a name="how-to-step-into-wcf-services"></a>Nasıl Yapılır: WCF Hizmetleri İçine Adımlama
İçinde [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)] , BIR WCF hizmetine adım adım ekleyebilirsiniz. WCF hizmeti [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] istemcisiyle aynı çözümde ise, WCF hizmetinin içindeki kesme noktalarına de ulaşırsınız.

 Çalışma adımlaması için app.config veya Web.config dosyasında hata ayıklamanın etkinleştirilmiş olması gerekir. Hata ayıklamayı etkinleştirme ve WCF hizmetlerine adımlamayı kısıtlama hakkında daha fazla bilgi için bkz. [WCF hata ayıklama kısıtlamaları](../debugger/limitations-on-wcf-debugging.md).

### <a name="to-step-into-a-wcf-service"></a>Bir WCF hizmetine adım adım

1. [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]WCF istemcisi ve WCF hizmeti projelerini içeren bir çözüm oluşturun.

2. Çözüm Gezgini, WCF Istemci projesine sağ tıklayın ve ardından **Başlangıç projesi olarak ayarla**' ya tıklayın.

3. app.config veya web.config dosyasında hata ayıklamayı etkinleştirin. Daha fazla bilgi için bkz. [WCF hata ayıklama kısıtlamaları](../debugger/limitations-on-wcf-debugging.md).

4. İstemci projesindeki, adımlamayı başlatmak istediğiniz konumda bir kesme noktası ayarlayın. Genellikle, bu, WCF hizmeti çağrısından hemen önce olacaktır.

5. Kesme noktasında çalıştırın ve ardından adımlamayı başlatın. Hata ayıklayıcı, hizmette otomatik olarak adım adım sunulacaktır.

## <a name="see-also"></a>Ayrıca bkz.
- [WCF Hizmetlerinde Hata Ayıklama](../debugger/debugging-wcf-services.md)
- [WCE Hata Ayıklamasında Sınırlamalar](../debugger/limitations-on-wcf-debugging.md)
- [Nasıl Yapılır: Kendini Barındıran WCF Hizmetinde Hata Ayıklama](../debugger/how-to-debug-a-self-hosted-wcf-service.md)