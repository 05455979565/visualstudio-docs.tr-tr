---
title: Katkıda bulunan yeni öğe Ekle iletişim kutusu | Microsoft Docs
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
- Add New Item dialog box, contributing to
ms.assetid: b2e53175-9372-4d17-8c2b-9264c9e51e9c
caps.latest.revision: 19
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: f5fcbac8b9e26bcca5a588846c14972156761d5b
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42629549"
---
# <a name="contributing-to-the-add-new-item-dialog-box"></a>Yeni Öğe Ekleme İletişim Kutusuna Katkıda Bulunma
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [ekleme yeni öğe iletişim kutusuna katkıda bulunan](https://docs.microsoft.com/visualstudio/extensibility/internals/contributing-to-the-add-new-item-dialog-box).  
  
Proje alt öğeleri için yeni bir tam dizin sağlayabilir **Yeni Öğe Ekle** kaydederek iletişim kutusu **Öğe Ekle** şablonlar altında `Projects` kayıt defteri alt anahtarı.  
  
## <a name="registering-add-new-item-templates"></a>Kaydetme Yeni Öğe Ekle şablonları  
 Bu bölümde altında bulunan **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\8.0\Projects** kayıt defteri. Kayıt defteri girdilerini varsayar bir [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] proje kuramsal proje alt türü tarafından toplanır. Girişleri [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] proje aşağıda listelenmiştir.  
  
```  
[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\8.0\Projects\{F184B08F-C81C-45F6-A57F-5ABD9991F28F}]  
@="#2143"  
"DefaultProjectExtension"="vbproj"  
"PossibleProjectExtensions"="vbproj;vbp"  
"ProjectTemplatesDir"="visualStudioInstallPath\\Vb\\.\\VBProjects"  
  
[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\8.0\Projects\{F184B08F-C81C-45F6-A57F-5ABD9991F28F}\AddItemTemplates\TemplateDirs\{12345678-1234-1234-1122334455667788}\/1]  
@="#100"  
"TemplatesDir"="projectSubTypeTemplatesDir\\VBProjectItems"  
```  
  
 `AddItemTemplates\TemplateDirs` Alt anahtar içerir, burada öğeler yapılan bulunan dizine olan yolu ile kayıt defteri girdilerini **Yeni Öğe Ekle** iletişim kutusu yerleştirilir.  
  
 Tüm ortam otomatik olarak yükleyen `AddItemTemplates` verileri altında `Projects` kayıt defteri alt anahtarı. Bu, temel proje uygulamaları için verilerin yanı sıra belirli proje alt türleri için verileri içerebilir. Her proje alt proje türü tarafından tanımlanan `GUID`. Proje alt alternatif kümesi olduğunu belirtebilirsiniz `Add Item` şablonları kullanılmalıdır belirli flavored proje örneği için destekleyerek `VSHPROPID_ AddItemTemplatesGuid` sabit listesinden alınmış <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID2> içinde <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.GetProperty%2A> GUID döndürmek için uygulama Proje alt türü değeri. Varsa `VSHPROPID_AddItemTemplatesGuid` özelliği belirtilmedi, temel proje GUID kullanılır.  
  
 Öğeleri filtreleyebilirsiniz **Yeni Öğe Ekle** uygulayarak iletişim kutusu <xref:Microsoft.VisualStudio.Shell.Interop.IVsFilterAddProjectItemDlg> proje alt toplayıcısı nesne üzerinde arabirimi. Örneğin, bir veritabanı projesi toplayarak uygulayan bir proje alt bir [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] proje, filtreleyebilirsiniz [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] özel öğeleri gelen **Yeni Öğe Ekle** filtreleme uygulayarak ve iletişim kutusunu açın, ekleyebilirsiniz Veritabanı Proje belirli öğeleri destekleyerek `VSHPROPID_ AddItemTemplatesGuid` içinde <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.GetProperty%2A>. Filtreleme ve öğeler ekleme hakkında daha fazla bilgi için **Yeni Öğe Ekle** iletişim kutusu, bkz: [ekleme yeni öğe iletişim kutularına öğe eklemeyi](../../extensibility/internals/adding-items-to-the-add-new-item-dialog-boxes.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsFilterAddProjectItemDlg2>   
 [Genişletme Projeleri için Genellikle Kullanılan Nesnelerin CATID’leri](../../extensibility/internals/catids-for-objects-that-are-typically-used-to-extend-projects.md)

