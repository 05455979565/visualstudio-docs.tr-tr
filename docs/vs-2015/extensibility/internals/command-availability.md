---
title: Komut kullanılabilirliği | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- commands, context
- menu items, visibility contexts
ms.assetid: c74e3ccf-d771-48c8-a2f9-df323b166784
caps.latest.revision: 35
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 9933975b005241e89444c47a96b80bf0e43bfbcb
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42695429"
---
# <a name="command-availability"></a>Komut Kullanılabilirliği
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [komutu kullanılabilirlik](https://docs.microsoft.com/visualstudio/extensibility/internals/command-availability).  
  
Visual Studio bağlamı, hangi komutları kullanılabilir olduğunu belirler. İçerik, geçerli proje, geçerli Düzenleyici, yüklenen VSPackage'ları ve diğer yönleri tümleşik geliştirme ortamı (IDE) bağlı olarak değiştirebilirsiniz.  
  
## <a name="command-contexts"></a>Komut bağlamları  
 Aşağıdaki komut bağlamları en yaygın olarak görülür.  
  
-   **IDE** IDE tarafından sağlanan komutlardır her zaman kullanılabilir.  
  
-   **VSPackage** VSPackages komutlar için görünür veya gizli olduğunda tanımlayabilirsiniz.  
  
-   **Proje** yalnızca şu anda seçili proje için proje komut belirir.  
  
-   **Düzenleyici** yalnızca bir düzenleyici etkin bir anda olabilir. Aktif Düzenleyici komutları kullanılabilir. Bir düzenleyici bir dil hizmeti ile yakın bir tümleştirmede çalışır. Dil hizmeti ilişkili Düzenleyicisi bağlamında komutlarının işlemesi gerekir.  
  
-   **Dosya türü** birden fazla dosya türü yükleyebilir ve bir düzenleyici. Kullanılabilir komutlar, dosya türüne bağlı olarak değiştirebilirsiniz.  
  
-   **Etkin pencereyi** son etkin belge penceresini tuş bağlamaları için kullanıcı arabirimi (UI) bağlamını ayarlar. Ancak, iç Web tarayıcısı benzer bir anahtar bağlaması tablo içeren bir araç penceresi UI bağlamı ayarlayabilirsiniz. HTML düzenleyicisi gibi birden çok sekmeli belge pencereleri için farklı komut bağlam GUID her sekmesi vardır. Araç penceresi kaydedildikten sonra her zaman kullanılabilir **görünümü** menüsü.  
  
-   **UI bağlamı** UI bağlamları değerleri tarafından tanımlanan <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT> sınıfından, örneğin, <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT.SolutionBuilding_guid> çözüm yerleşik olduğunda veya <xref:Microsoft.VisualStudio.VSConstants.UICONTEXT.Debugging_guid> hata ayıklayıcısı etkinken. Aynı anda birden fazla UI bağlamı etkin olabilir.  
  
## <a name="defining-custom-context-guids"></a>Özel bağlam GUID'leri tanımlama  
 GUID zaten tanımlı değil bir uygun komut bağlamı ise, VSPackage birinde tanımlayabilir ve etkin veya etkin değil olarak komutlarınızı görünürlüğünü denetleme için gerekli olması için program.  
  
1.  Bağlam GUID'leri çağırarak kayıt <xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection.GetCmdUIContextCookie%2A> yöntemi.  
  
2.  Bir bağlam GUID durumunu çağırarak alma <xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection.IsCmdUIContextActive%2A> yöntemi.  
  
3.  Çağırarak bağlam GUID'leri açıp kapatma <xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection.SetCmdUIContext%2A> yöntemi.  
  
    > [!CAUTION]
    >  Diğer VSPackage'ları bunlara bağımlı çünkü, VSPackage'ı tüm mevcut bir bağlamı GUID'leri etkilemez emin olun.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Seçim bağlamı nesneleri](../../extensibility/internals/selection-context-objects.md)   
 [VSPackage’ların Kullanıcı Arabirimi Öğeleri Eklemesi](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)

