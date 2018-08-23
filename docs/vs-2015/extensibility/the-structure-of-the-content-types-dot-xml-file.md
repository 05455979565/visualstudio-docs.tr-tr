---
title: Yapısı, Content_types] .xml dosyası | Microsoft Docs
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
- content_types
- content types
- opc
- vsix
ms.assetid: 9c399598-b9fa-4da7-84b5-defbf82e9335
caps.latest.revision: 9
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 89c5e1bab9f8cbe8cd6e2b980013c6bfdf4bc039
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42691504"
---
# <a name="the-structure-of-the-contenttypesxml-file"></a>Yapısı, Content_types] .xml dosyası
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [[Content_types] .xml dosyasının yapısı](https://docs.microsoft.com/visualstudio/extensibility/the-structure-of-the-content-types-dot-xml-file).  
  
Bir VSIX paketi, içerik türleri hakkındaki bilgileri içerir. Visual Studio paketi yüklemek için [Content_Types] .xml dosyasını kullanır, ancak dosyayı yüklemez.  
  
> [!NOTE]
>  Bu konuda, VSIX paketinde kullanılan [Content_Type] .xml dosyaları için geçerli olsa da, [Content_Types] .xml dosya türü parçasıdır *açık paketleme kuralları (OPC)* standart. Daha fazla bilgi için [OPC: A yeni standart için paketleme verilerinizi](http://go.microsoft.com/fwlink/?LinkID=148207) MSDN Web sitesinde.  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Kök öğe ve öznitelikler ve alt öğeler aşağıdaki bölümlerde açıklanmaktadır.  
  
### <a name="root-element"></a>Kök öğe  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|`Types`|VSIX paketini dosya türlerini listeleme alt öğeleri içerir.|  
  
### <a name="attributes"></a>Öznitelikler  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`Xmlns`|(Gerekli) Bu [Content_Types] .xml dosyası için kullanılan şema konumu.|  
  
### <a name="attribute-name-attribute"></a>{Öznitelik adı} Özniteliği  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|http://schemas.openformats.org/package/2006/content-types|İçerik türleri şema konumu.|  
  
### <a name="child-elements"></a>Alt Öğeler  
 `Types` Herhangi bir sayıda öğe içerebilir `Default` öğeleri.  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|`Default`|VSIX paketinde bir içerik türü açıklar. Paketteki her dosya türü kendi olmalıdır `Default` öğesi.|  
  
### <a name="attributes"></a>Öznitelikler  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|`Extension`|VSIX paketini bir dosyanın dosya adı uzantısı.|  
|`ContentType`|Dosya adı uzantısıyla ilişkili olan içerik türünü açıklar.|  
  
### <a name="attribute-name-attribute"></a>{Öznitelik adı} Özniteliği  
 Visual Studio aşağıdaki tanır `ContentType` ilişkili değerleri `Extension` türleri.  
  
|Uzantı|contentType|  
|---------------|-----------------|  
|txt|metin/düz|  
|pkgdef|metin/düz|  
|XML|metin/xml|  
|vsixmanifest|metin/xml|  
|htm veya html|metin/html|  
|RTF|Uygulama/rtf|  
|PDF|Uygulama/pdf|  
|GIF|Görüntü/gif|  
|JPG veya jpeg|Görüntü/jpg|  
|TIFF|Görüntü/TIFF|  
|vsix|Uygulama/zip'i|  
|Zip|Uygulama/zip'i|  
|dll|Uygulama/octet-akış|  
|diğer tüm dosya türleri|Uygulama/octet-akış|  
  
## <a name="example"></a>Örnek  
  
### <a name="description"></a>Açıklama  
 Aşağıdaki [Content_Types] .xml dosyasının tipik bir VSIX paketi açıklar.  
  
### <a name="code"></a>Kod  
  
```  
<?xml version="1.0" encoding="utf-8" ?>   
<Types xmlns="http://schemas.openxmlformats.org/package/2006/content-types">  
    <Default Extension="vsixmanifest" ContentType="text/xml" />   
    <Default Extension="dll" ContentType="application/octet-stream" />   
    <Default Extension="png" ContentType="application/octet-stream" />   
    <Default Extension="txt" ContentType="text/plain" />   
    <Default Extension="pkgdef" ContentType="text/plain" />   
</Types>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bir VSIX paketinin anatomisi](../extensibility/anatomy-of-a-vsix-package.md)   
 [VSIX Uzantı Şeması 1.0 başvurusu](http://msdn.microsoft.com/en-us/76e410ec-b1fb-4652-ac98-4a4c52e09a2b)   
 [OPC: Verilerinizi paketleme için yeni bir standart](http://go.microsoft.com/fwlink/?LinkID=148207)

