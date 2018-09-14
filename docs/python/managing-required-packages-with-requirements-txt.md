---
title: Paket gereksinimlerini yönetmek için requirements.txt dosyasını kullanma
description: Bir proje bağımlılıklarınızı yönetmek için requirements.txt dosyasını kullanabilirsiniz. Requirements.txt dosyasını içeren bir proje alırsanız, bu bağımlılıkların bir adımda kolayca yükleyebilirsiniz.
ms.date: 06/27/2018
ms.prod: visual-studio-dev15
ms.technology: vs-python
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: douge
ms.workload:
- python
- data-science
ms.openlocfilehash: 478cb56856a5177f74b92542afadb0c36ac946c2
ms.sourcegitcommit: 568bb0b944d16cfe1af624879fa3d3594d020187
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/13/2018
ms.locfileid: "45548798"
---
# <a name="manage-required-packages-with-requirementstxt"></a>Gerekli paketleri requirements.txt ile yönetme

Proje yapı sistemini kullanarak başkalarıyla paylaşmaya ya da planladığınız [Microsoft Azure'a yayımlama](python-azure-cloud-service-project-template.md), proje gerektiren dış paketleri belirtmeniz gerekir. Kullanmak için önerilen yaklaşımdır bir [requirements.txt dosyasını](https://pip.readthedocs.org/en/latest/user_guide.html#requirements-files) (readthedocs.org) yükleyen gerekli sürümlerinden birini bağımlı paketler pip komutların listesini içerir.

Teknik olarak, herhangi bir dosya adının gereksinimlerini izlemek için kullanılabilir (kullanarak `-r <full path to file>` paketi yüklerken), Visual Studio için belirli destek sağlar, ancak *requirements.txt*:

- İçeren bir proje yüklemiş olduğunuz varsa *requirements.txt* ve bu dosyada listelenen paketleri yüklemek istiyorsanız, genişletme **Python ortamları** düğümünde **ÇözümGezgini**, ardından bir ortam düğümüne sağ tıklayıp **Requirements.txt'ten Yükle**:

    ![Requirements.txt'ten yükle](media/environments-requirements-txt-install.png)

- Bir ortama yüklenen tüm gerekli paketler zaten varsa, o ortamda sağ tıklayabilirsiniz **Çözüm Gezgini** seçip **Generovat requirements.txt** gerekli oluşturmak için dosya. Dosya zaten varsa, güncelleştirmek için bir komut istemi görünür:

    ![Güncelleştirme requirements.txt seçenekleri](media/environments-requirements-txt-replace.png)

  - **Tüm dosya yerine** tüm öğeleri, yorumları ve mevcut olan seçenekler kaldırır.
  - **Girdilerinin Yenile** paket gereksinimleri algılar ve şu anda yüklü olan sürümle eşleştirmek için sürüm belirticisi güncelleştirir.
  - **Güncelleştirme ve giriş eklemek** bulunur ve diğer tüm paketleri dosyanın sonuna ekler gereksinimlere yeniler.

Çünkü *requirements.txt* dosyaları, bir ortamın gereksinimleri dondurmak için yöneliktir, tüm yüklü paketleri kesin sürümleri ile yazılır. Kesin sürümlerini kullanan başka bir bilgisayardaki ortamınızı kolayca üretebileceği sağlar. Başka bir paketin, bağımlılık olarak bir sürüm aralığı veya pip dışındaki bir yükleyici ile yüklenmiş olan bile paketleri dahil edilir.

Bir paket pip tarafından yüklenemez ve görünür bir *requirements.txt* dosyası, tüm yükleme başarısız olur. Bu durumda, bu paketi hariç tutmak için ya da kullanılacak dosyayı el ile düzenlemeniz [pip'ın seçenekleri](https://pip.readthedocs.org/en/latest/reference/pip_install.html#requirements-file-format) paket yüklenebilir bir sürümünü başvurmak için. Örneğin, kullanmayı tercih edebilirsiniz [ `pip wheel` ](https://pip.readthedocs.org/en/latest/reference/pip_wheel.html) bağımlılığı derlemek ve eklemek için `--find-links <path>` seçeneği, *requirements.txt*:

```output
C:\Project>pip wheel azure
Downloading/unpacking azure
    Running setup.py (path:C:\Project\env\build\azure\setup.py) egg_info for package azure

Building wheels for collected packages: azure
    Running setup.py bdist_wheel for azure
    Destination directory: c:\project\wheelhouse
Successfully built azure
Cleaning up...

C:\Project>type requirements.txt
--find-links wheelhouse
--no-index
azure==0.8.0

C:\Project>pip install -r requirements.txt -v
Downloading/unpacking azure==0.8.0 (from -r requirements.txt (line 3))
    Local files found: C:/Project/wheelhouse/azure-0.8.0-py3-none-any.whl
Installing collected packages: azure
Successfully installed azure
Cleaning up...
    Removing temporary dir C:\Project\env\build...
```

### <a name="see-also"></a>Ayrıca bkz.

- [Visual Studio'da Python ortamlarını yönetme](managing-python-environments-in-visual-studio.md)
- [Proje için yorumlayıcıyı seçme](selecting-a-python-environment-for-a-project.md)
- [Arama yolları](search-paths.md)
- [Python ortamları penceresi başvurusu](python-environments-window-tab-reference.md)
