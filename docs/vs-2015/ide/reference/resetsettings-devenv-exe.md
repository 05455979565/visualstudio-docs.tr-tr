---
title: -ResetSettings (devenv.exe) | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Devenv, /ResetSettings switch
- ResetSettings switch
- /ResetSettings Devenv switch
ms.assetid: 1d41021c-6f58-4bd5-b122-d1c995812192
caps.latest.revision: 14
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 25697a792b0c48746a1d7840b8091ea718f5cdc7
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42694713"
---
# <a name="resetsettings-devenvexe"></a>/ResetSettings (devenv.exe)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [- ResetSettings (devenv.exe)](https://docs.microsoft.com/visualstudio/ide/reference/resetsettings-devenv-exe).  
  
  
Geri yükler [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] varsayılan ayarları ve otomatik olarak başlatan [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] IDE. İsteğe bağlı olarak belirtilen .vssettings dosya ayarlarını sıfırlar.  
  
 Varsayılan ayarlar, profili tarafından belirlenir seçilen [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] önce başlatıldı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
Devenv /ResetSettings SettingsFile  
```  
  
## <a name="arguments"></a>Arguments  
 `SettingsFile`  
 Uygulanacak .vssettings dosyasının adını ve tam yolunu [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].  
  
 Genel Geliştirme Ayarları profilini geri yüklemek için kullanın `General`.  
  
## <a name="remarks"></a>Açıklamalar  
 Hayır ise `SettingsFile` belirtilirse, sonraki başlatışınızda ayar varsayılan koleksiyonunu seçmek için istenir [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].  
  
## <a name="example"></a>Örnek  
 Aşağıdaki komut satırını dosyasında depolanan ayarları uygular `MySettings.vssettings`.  
  
```  
Devenv.exe /ResetSettings "C:\My Files\MySettings.vssettings"  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio'da geliştirme ayarlarını özelleştirme](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)   
 [Devenv Komut Satırı Anahtarları](../../ide/reference/devenv-command-line-switches.md)



