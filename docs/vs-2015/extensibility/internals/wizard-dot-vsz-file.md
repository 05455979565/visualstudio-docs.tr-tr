---
title: Sihirbazı (. Vsz) dosyası | Microsoft Docs
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
- .vsz files
- vsz files
- wizards, files
ms.assetid: 72e1d0f3-eef1-455e-b803-96827f030f50
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 24296384ec66386cdcb735547a1b6ce9c64a0618
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42693911"
---
# <a name="wizard-vsz-file"></a>Sihirbaz (.Vsz) Dosyası
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [Sihirbazı (. Vsz) dosya](https://docs.microsoft.com/visualstudio/extensibility/internals/wizard-dot-vsz-file).  
  
Tümleşik geliştirme ortamı (IDE), sihirbazları başlatmak için .vsz dosyalarını kullanır. Bu .vsz dosyaları IDE çağırmak için hangi Sihirbazı belirlemek için kullandığı bilgileri ve sihirbaz için geçirmek için hangi bilgileri içerir.  
  
 .Vsz dosyası, bölüm olan bir .ini biçimli metin dosyası sürümüdür. IDE bilinen bilgileri dosyasının başında depolanır. Bu, IDE çağıran sihirbazın .vsz dosyasındaki IDE'ye geçirilecek parametreler arasında bir bağlantı sağlar. Dosyayı geri kalanını sihirbaza özeldir ve IDE tarafından toplanacak olan ve belirli sihirbazın geçirilen parametreleri sağlar.  
  
 Aşağıdaki örnek, bir .vsz dosyasının içeriğini gösterir.  
  
```  
VSWizard 8.0  
Wizard=VsWizard.CBlankSiteWizard -or- {123-1234556-123334}  
Param="WIZARDNAME = Wizard One"  
Param="WIZARDUI = FALSE"  
```  
  
 .Vsz dosyası bölümleri aşağıda verilmiştir.  
  
|Bölümü|Açıklama|  
|----------|-----------------|  
|VSWizard|Dosyadaki ilk parametre, şablon dosyası biçiminin sürüm numarasıdır. Bu sürüm numarası 6.0, 7.0, 7.1 veya 8.0 olmalıdır. Diğer sayılar başlatılamıyor ve biçimi geçersiz hataya neden.|  
|Sihirbazı|Bu alan, OLE ProgID Sihirbazı'nın veya alternatif olarak bir CLSID IDE tarafından cocreated Sihirbazı GUID dize gösterimini içerir.|  
|param|Bu bölümleri isteğe bağlıdır. Kadar gerekli ekleyebilirsiniz.|  
  
 Parametreleri sihirbaza ek özel parametreleri geçirmek üzere .vsz dosyasını olanak tanır. Her değer çeşitleri bir dizide dize öğesi olarak sihirbaza geçirilir. Daha fazla bilgi için [özel parametreler](../../extensibility/internals/custom-parameters.md). Özel sihirbazlar geliştirilmesini .vsz dosyasında kullanma hakkında daha fazla bilgi için bkz: [. Vsz dosyası (proje denetimi)](http://msdn.microsoft.com/library/b8678fee-6795-46d1-9338-48b22d5e9207)  
  
 Varsayılan yerel ayar kimliği .vsz dosyanıza eklemek için belirtin `FALLBACK_LCID`xxxx olmak üzere yerel ayar kimliği, örneğin, İngilizce için 1033 xxxx, =. Zaman `FALLBACK_LCID` parametresi tanımlı, geçerli kimlik bulunmazsa sihirbaz sağlanan geri dönüş yerel ayar Kimliğini kullanır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özel Parametreler](../../extensibility/internals/custom-parameters.md)   
 [Sihirbazlar](../../extensibility/internals/wizards.md)   
 [Şablon Dizin Açıklaması (.Vsdir) Dosyaları](../../extensibility/internals/template-directory-description-dot-vsdir-files.md)

