---
title: Seçin ve Python yorumlayıcılarını yükleme
description: Visual Studio'da kısa yönergelerle yükleyicilerinin nerede bulacağını üzerinde desteklenen Python yorumlayıcılarını tam bir listesi.
ms.date: 03/13/2019
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: jillfra
ms.custom: seodec18
ms.workload:
- python
- data-science
ms.openlocfilehash: c8c2d96aeb24b9311998528d0360b1c3eac38e5f
ms.sourcegitcommit: 4d9c54f689416bf1dc4ace058919592482d02e36
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/19/2019
ms.locfileid: "58194184"
---
# <a name="install-python-interpreters"></a>Python yorumlayıcılarını yükleme

Varsayılan olarak, Python geliştirme iş yükünü Visual Studio 2017 ve sonraki sürümlerinde yükleme Python 3 (64-bit) yükler. İsteğe bağlı olarak Python 2 ve Miniconda (Visual Studio 2019) veya Anaconda 2/3 (Visual Studio 2017), Anaconda yanı sıra Python 3 32-bit ve 64-bit sürümleri yüklemek açıklandığı seçebileceğiniz [yükleme](installing-python-support-in-visual-studio.md).

::: moniker range=">=vs-2019"
Alternatif olarak, standart python yorumlayıcılarını'nden yükleyebilirsiniz **ortam Ekle** iletişim. Seçin **ortam Ekle** komutunu **Python ortamları** penceresi veya Python araç çubuğunu seçin **Python yükleme** sekmesinde, hangi yorumlayıcılarını belirtmek için yükleyip **yükleme**.
::: moniker-end

Ayrıca, herhangi bir Visual Studio yükleyicisi dışında aşağıdaki tabloda listelenen yorumlayıcılarını el ile de yükleyebilirsiniz. Örneğin, Visual Studio'yu yüklemeden önce Anaconda 3 yüklü değilse, Visual Studio yükleyicisi yeniden yüklemeniz gerekmez. Ayrıca yorumlayıcıyı el ile yükleyebilirsiniz, örneğin, daha yeni bir sürümü kullanılabilir, henüz Visual Studio Yükleyicisi'nde görünmez.

İçin **Visual Studio 2015 veya önceki**, yorumlayıcılarını birini el ile yüklemelisiniz.

Visual Studio (tüm sürümler) otomatik olarak algılar her yüklü Python yorumlayıcısı ve ortam kayıt defteri ayarına göre kontrol ederek [CESARETLENDİRİCİ 514 - Python kayıt Windows kayıt defterinde](https://www.python.org/dev/peps/pep-0514/). Python yüklemeleri altında bulundu genellikle **HKEY_LOCAL_MACHINE\SOFTWARE\Python** (32-bit) ve **HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Python** (64-bit) sonra düğümleri için içinde Dağıtım gibi **PythonCore** (CPython) ve **ContinuumAnalytics** (Anaconda).

Visual Studio yüklü bir ortam algılamazsa bkz [el ile bir ortamı tanımlamanız](managing-python-environments-in-visual-studio.md#manually-identify-an-existing-environment).

Visual Studio gösterir bilinen tüm ortamlarda [ **Python ortamları** ](managing-python-environments-in-visual-studio.md#the-python-environments-window) penceresinde ve mevcut yorumlayıcılarını güncelleştirmeleri otomatik olarak algılar.

| Yorumlayıcı | Açıklama |
| --- | --- |
| [CPython](https://www.python.org/) | "Yerel" ve en yaygın olarak kullanılan Yorumlayıcı, 32-bit ve 64-bit sürümleri (32-bit önerilir) kullanılabilir. En son dil özellikleri, en yüksek Python paket uyumluluğu, tam hata ayıklama desteği ve birlikte çalışma içerir [Ipython](https://ipython.org/). Ayrıca bkz: [Python 2 veya Python 3 kullanmalıyım? ](https://wiki,python.org/moin/Python2orPython3). Visual Studio 2015 veya önceki Python 3.6 + desteklemez ve hatalar gibi verebilirsiniz Not **desteklenmeyen python 3.6 sürümünü**. Python 3.5 veya daha önceki kullanmak yerine. |
| [V Ironpythonu](https://github.com/IronLanguages/ironpython2) | Python, 32-bit ve 64 bit sürümlerde kullanılabilir sağlayan bir .NET uygulaması C#/F#/Visual Basic birlikte çalışabilirliği, .NET API'leri, standart Python hata ayıklama (ancak değil C++ karışık mod hata ayıklama için) erişim ve IronPython karışık /C# hata ayıklama. Ancak, IronPython, sanal ortamları desteklemez. |
| [Anaconda](https://www.continuum.io) | Bir açık veri bilimi platformu Python tarafından desteklenen ve CPython ve zor yükleme paketlerinin en son sürümünü içerir. Aksi takdirde karar veremez, öneririz. |
| [PyPy](https://www.pypy.org/) | Yüksek performans izleme JIT uzun süre çalışan programlar ve performans tanımlamak burada durumlar için iyi bir Python uygulamasıdır verir ancak diğer çözümleri bulunamıyor. Visual Studio ile ancak sınırlı destek ile çalıştığı için Gelişmiş hata ayıklama özellikleri. |
| [Jython](http://www.jython.org/) | Java sanal makine'üzerinde (JVM) Python uygulaması. Benzer şekilde, IronPython, Jython içinde çalışan kod Java sınıfları ve kitaplıkları ile etkileşim kurabilir, ancak birçok kitaplıkları CPython için hedeflenen kullanmanız mümkün olmayabilir. Visual Studio ile ancak sınırlı destek ile çalıştığı için Gelişmiş hata ayıklama özellikleri. |

Algılama Python ortamları için yeni form sağlamak isteyen geliştiriciler [PTVS Ortam Algılama](https://github.com/Microsoft/PTVS/wiki/Extensibility-Environments) (github.com).

## <a name="move-an-interpreter"></a>Yorumlayıcıyı Taşı

Mevcut yorumlayıcıyı dosya sistemini kullanarak yeni bir konuma taşırsanız, Visual Studio değişiklik otomatik olarak algılamaz.

- Başlangıçta yorumlayıcı konumunu belirttiyseniz **Python ortamları** penceresinde sonra ortamı kullanarak düzenleyin **yapılandırma** Bu pencerede, yeni konumunu belirlemek için sekmesinde. Bkz: [el ile bir ortamı tanımlamanız](managing-python-environments-in-visual-studio.md#manually-identify-an-existing-environment).

- Ardından bir yükleyici programı'nı kullanarak yorumlayıcı yüklü değilse, yorumlayıcı yeni konumda yeniden yüklemek için aşağıdaki adımları kullanın:

  1. Python yorumlayıcısı orijinal konumuna geri yükleyin.
  2. Kayıt defteri girişlerini temizler, Yükleyicisi'ni kullanarak yorumlayıcı kaldırın.
  3. Yorumlayıcı istediğiniz konuma yeniden yükleyin.
  4. Otomatik Algıla eski konumu yerine yeni konuma Visual Studio'yu yeniden başlatın.

Bu işlem Visual Studio kullanan Yorumlayıcı'nın konumu tanımlayan kayıt defteri girdilerini düzgün şekilde güncelleştirilmesini sağlar. Bir yükleyici kullanarak, diğer yan bulunabilecek etkileri işler.

## <a name="see-also"></a>Ayrıca bkz.

- [Python ortamları yönetme](managing-python-environments-in-visual-studio.md)
- [Proje için yorumlayıcıyı seçme](selecting-a-python-environment-for-a-project.md)
- [Bağımlılıklar için Requirements.txt dosyasını kullanma](managing-required-packages-with-requirements-txt.md)
- [Arama yolları](search-paths.md)
- [Python ortamları penceresi başvurusu](python-environments-window-tab-reference.md)
