---
title: Yeni Proje iletişim kutusuna dizin ekleme | Microsoft Docs
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
- New Project dialog box, extending
ms.assetid: 53b328f5-20bb-49a3-bf9e-1818f4fbdf50
caps.latest.revision: 14
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: e22f0566ddde7bfd795bb01141deabbecd532a19
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42687344"
---
# <a name="adding-directories-to-the-new-project-dialog-box"></a>Yeni Proje İletişim Kutusuna Dizin Ekleme
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [yeni proje iletişim kutusuna dizin ekleme](https://docs.microsoft.com/visualstudio/extensibility/internals/adding-directories-to-the-new-project-dialog-box).  
  
Yeni proje türleri oluşturduğunuzda, yeni bir dizin de kaydedebilirsiniz **yeni proje** şablon olarak kullanmak için bunları görüntülemek için iletişim kutusu. Aşağıdaki kod örneği, bir düğüm olarak da bilinen yeni bir dizin kaydedilecek açıklanmaktadır. Örnekte, VSPackage CLSID_Package tarafından kullanıma sunulan şablonları kaydedilir. Sonuç olarak, sol tarafındaki **yeni proje** iletişim kutusu eklenen düğümü Folder_Label_ResID kaynak tarafından belirlenen bir adla sunar. Bu kaynak VSPackage uydu DLL yüklenir.  
  
 **Klasör** değeri bir GUID Folder_Label_ResID düğümü altında görüntülendiği bir klasörün temsil eder. Örnekte, GUID'i temsil **diğer projeleri** klasöründe **proje türleri** bölmesinde **yeni proje** iletişim kutusu. Varsa **diğer projeleri** değeri yok, en üst düzeyinde etiketi konumlandırıldı.  
  
 TemplatesDir değeri proje şablonları içeren dizinin tam yolunu belirtir. .Vsz dosyaları veya Normal şablon dosyaları kopyalamak için bu dosyalar olabilir.  
  
 TemplatesLocalizedSubDir belirtirseniz, kaynak Kimliğini yerelleştirilmiş şablonları tutan TemplatesDir alt adları bir dize olmalıdır. Çünkü [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] dize kaynağını yükler, yoksa bir uydu DLL farklı bir alt dizin adı her uydu DLL içerebilir. SortPriority değeri bir sıralama önceliği belirtir.  
  
```  
NoRemove NewProjectTemplates  
{  
    NoRemove TemplateDirs  
  {  
    ForceRemove %CLSID_Package%  
    {  
      ForceRemove /1 = s '#%Folder_Label_ResID%'  
      {  
        val Folder = s '{DCF2A94A-45B0-11D1-ADBF-00C04FB6BE4C}'  
        val TemplatesDir = s '%Template_Path%'  
        val TemplatesLocalizedSubDir = s '#100'  
        val SortPriority = d 1000  
      }  
    }  
  }  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Proje ve öğe şablonlarını kaydetme](../../extensibility/internals/registering-project-and-item-templates.md)   
 [Öğeler ekleme yeni öğe Ekle iletişim kutuları](../../extensibility/internals/adding-items-to-the-add-new-item-dialog-boxes.md)   
 [Yeni Öğe Ekleme İletişim Kutusuna Dizin Ekleme](../../extensibility/internals/adding-directories-to-the-add-new-item-dialog-box.md)

