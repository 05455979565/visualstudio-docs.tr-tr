---
title: Visual Studio Test Professional 2017 iş yükü ve Bileşen kimlikleri
description: Tümleşik test araçları için genel test edicileri sağlamak için Visual Studio iş yükü ve Bileşen kimlikleri kullanın
keywords: ''
author: TerryGLee
ms.author: tglee
manager: douge
ms.date: 08/14/2018
ms.topic: reference
helpviewer_keywords:
- workload ID, Visual Studio
- component ID, Visual Studio
- install Visual Studio, administrator guide
ms.service: ''
ms.technology: vs-acquisition
ms.prod: visual-studio-dev15
ms.assetid: 70c03438-8434-4921-ada0-c172519af431
ms.workload:
- multiple
ms.openlocfilehash: 4dfd54aa8b476187d1f6ba0a4f7916515e87064f
ms.sourcegitcommit: 2b1f8e5288582367af2bed20848ba556f146716e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/14/2018
ms.locfileid: "42624329"
---
# <a name="visual-studio-test-professional-2017-component-directory"></a>Visual Studio Test Professional 2017 bileşen dizini

Tabloları bu sayfa listesi kimliklerinin komut satırını kullanarak Visual Studio'yu yüklemek için kullanabilirsiniz veya bağımlılık VSIX bildirimi olarak belirtebilirsiniz. Visual Studio güncelleştirmeleri yayınlayabilir gibi ek bileşenler ekleyeceğiz olduğunu unutmayın.

Ayrıca sayfa hakkında aşağıdakileri unutmayın:

* Her iş yükü, izlediği iş yükü kimliği ve iş yükü için kullanılabilir olan bileşenlerin bir tablo, kendi bölümü vardır.
* Varsayılan olarak, **gerekli** bileşenleri, iş yükünü yüklediğinizde yüklenir.
* Kullanmayı tercih ederseniz de yükleyebilirsiniz **önerilen** ve **isteğe bağlı** bileşenleri.
* Her türlü iş yükü ile bağlı olmayan ek bileşenleri listeleyen bir bölüm de ekledik.

VSIX bildiriminizi bağımlılıkları oluşturduğunuzda, Bileşen kimlikleri yalnızca belirtmeniz gerekir. Tablolar, sunduğumuz en az Bileşen bağımlılıkları belirlemek için bu sayfada kullanın. Bazı senaryolarda, bir iş yükü yalnızca bir bileşenden belirttiğiniz gelebilir. Diğer senaryolarda, tek bir iş yükünü birden fazla bileşenlerini veya birden çok iş yükü birden çok bileşenlerini belirttiğiniz gelebilir. Daha fazla bilgi için bkz [nasıl yapılır: Visual Studio 2017'ye geçirme genişletilebilirlik projeleri](../extensibility/how-to-migrate-extensibility-projects-to-visual-studio-2017.md) sayfası.

Bu kimliklerinin kullanma hakkında daha fazla bilgi için bkz. [Visual Studio 2017'yi yükleme komut satırı parametreleri kullanmak](use-command-line-parameters-to-install-visual-studio.md) sayfası. Ve iş yükü ve Bileşen kimlikleri diğer ürünlere yönelik bir listesi için bkz. [Visual Studio 2017 iş yükü ve Bileşen kimlikleri](workload-and-component-ids.md) sayfası.

## <a name="test-professional"></a>Test Professional

**ID:** Microsoft.VisualStudio.Workload.TestProfessional

**Açıklama:** Test Professional, BT'yi uzmanı edicileri hedefleyen tümleşik test araçları, tüm test yaşam test ihtiyaçlarını sürücü sağlar.

### <a name="components-included-by-this-workload"></a>Bu iş yükü tarafından bulunan bileşenler

Bileşen kimliği | Ad | Sürüm | Bağımlılık türü
--- | --- | --- | ---
Microsoft.VisualStudio.Component.TestTools.FeedbackClient | Microsoft Geri Bildirim İstemcisi | 15.6.27406.0 | Gerekli
Microsoft.VisualStudio.Component.TestTools.MicrosoftTestManager | Microsoft Test Manager | 15.6.27406.0 | Gerekli

## <a name="unaffiliated-components"></a>Kullanıcıyla bağlantılı olmayan bileşenleri

Bu, her türlü iş yükü ile dahil edilmez, ancak tek bir bileşeni olarak seçilebilir bileşenlerdir.

Bileşen kimliği | Ad | Sürüm
--- | --- | ---
yok | yok | yok

## <a name="get-support"></a>Destek alın

Bazı durumlarda sorunlar. Visual Studio yüklemenizin başarısız olursa bkz [sorun giderme, Visual Studio 2017 yükleme ve yükseltme sorunlarını](troubleshooting-installation-issues.md) sayfası. Sorun giderme adımlarını hiçbiri yardımcı (yalnızca İngilizce) yükleme Yardımı için canlı sohbet göre bize başvurabilirsiniz. Ayrıntılar için bkz [Visual Studio destek sayfasını](https://visualstudio.microsoft.com/vs/support/#talktous).

Birkaç diğer destek seçenekleri şunlardır:

* Ürün sorunları bize bildirebilirsiniz [sorun bildir](../ide/how-to-report-a-problem-with-visual-studio-2017.md) hem de Visual Studio yükleyicisi Visual Studio IDE içinde görünen bir araç.
* Üzerinde bir ürün önerisi bizimle paylaşabilirsiniz [UserVoice](https://visualstudio.uservoice.com/forums/121579).
* Ürün sorunları izlemek ve sorularınıza cevap bulun [Visual Studio Geliştirici topluluğu](https://developercommunity.visualstudio.com/).
* ABD ve diğer Visual Studio geliştiricilere ile görüşebilirsiniz [Gitter Topluluğu'nda Visual Studio konuşma](https://gitter.im/Microsoft/VisualStudio). (Bu seçenek gerektirir bir [GitHub](https://github.com/) hesabı.)

## <a name="see-also"></a>Ayrıca bkz.

* [Visual Studio iş yükü ve bileşen kimlikleri](workload-and-component-ids.md)
* [Visual Studio Yönetici Kılavuzu](visual-studio-administrator-guide.md)
* [Komut satırı parametrelerini kullanarak Visual Studio'yu yükleme](use-command-line-parameters-to-install-visual-studio.md)
  * [Komut satırı parametresi örnekleri](command-line-parameter-examples.md)
* [Visual Studio’nun çevrimdışı yüklemesini oluşturma](create-an-offline-installation-of-visual-studio.md)
