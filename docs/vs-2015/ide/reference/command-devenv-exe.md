---
title: -Command (devenv.exe) | Microsoft Docs
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
- Devenv, /command switch
- /command Devenv switch
ms.assetid: 13c20cd6-f09d-400a-8b7b-ecc266a32cef
caps.latest.revision: 14
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 4e4ff0beb638e9cf5ea7a0e5f0f3330300cca6f8
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42692643"
---
# <a name="command-devenvexe"></a>/Command (devenv.exe)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [-komut (devenv.exe)](https://docs.microsoft.com/visualstudio/ide/reference/command-devenv-exe).  
  
  
Başlatıldıktan sonra belirtilen komutu yürütür [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] tümleşik geliştirme ortamı (IDE).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
devenv /command CommandName  
```  
  
## <a name="arguments"></a>Arguments  
 `CommandName`  
 Gerekli. Tam adı bir [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] komut ya da çift tırnak işareti içine alınmış, diğer ad. Komut ve diğer ad sözdizimi hakkında daha fazla bilgi için bkz: [Visual Studio komutları](../../ide/reference/visual-studio-commands.md).  
  
## <a name="remarks"></a>Açıklamalar  
 Başlangıç tamamlandıktan sonra IDE adlandırılmış komutu yürütür. Bu anahtarı kullanırsanız, IDE aşağıdaki dotnetclıtools'u görüntülemiyor [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] başlangıcında başlangıç sayfası.  
  
 Bir eklenti bir komut sunarsa, komut satırından eklentiyi başlatmak için bu anahtarı kullanabilirsiniz. Daha fazla bilgi için [nasıl yapılır: denetim eklentileri kullanarak Eklenti Yöneticisi](http://msdn.microsoft.com/library/4f60444a-cb48-4cdb-8df4-941f6419aeeb).  
  
## <a name="example"></a>Örnek  
 Bu örnek başlatır [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] ve makro açık sık kullanılan dosyaları otomatik olarak çalıştırır.  
  
```  
devenv /command "Macros.MyMacros.Module1.OpenFavoriteFiles"  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Devenv komut satırı anahtarları](../../ide/reference/devenv-command-line-switches.md)   
 [Visual Studio Komut Diğer Adları](../../ide/reference/visual-studio-command-aliases.md)



