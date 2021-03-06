---
title: -Kurulum (devenv. exe) | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- setup Devenv switch
- /setup Devenv switch
- Devenv, /setup switch
ms.assetid: 87608b7f-a156-400c-80f5-fc823f843e61
caps.latest.revision: 19
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: a923d1f3532548ebc6ed651a0739e0e5792f7967
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72663529"
---
# <a name="setup-devenvexe"></a>/Setup (devenv.exe)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Tüm kullanılabilir VSPackages 'lerden menüleri, araç çubuklarını ve komut gruplarını açıklayan kaynak meta verilerini birleştirmeye [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] zorlar.

## <a name="syntax"></a>Sözdizimi

```
devenv /setup
```

## <a name="remarks"></a>Açıklamalar
 Bu anahtar bağımsız değişken almaz. @No__t_0 komutu genellikle yükleme işleminin son adımı olarak verilir. @No__t_0 anahtarın kullanımı [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] başlamaz.

 [/Setup (devenv. exe)](../../ide/reference/setup-devenv-exe.md) ve [/ınstallvstempsyonlar (devenv. exe)](../../ide/reference/installvstemplates-devenv-exe.md) anahtarlarını kullanabilmeniz için `devenv` yönetici olarak çalıştırmanız gerekir.

## <a name="example"></a>Örnek
 Bu örnekte, VSPackages içeren bir [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] sürümünün yüklenmesiyle ilgili son adım gösterilmektedir.

```
devenv /setup
```

## <a name="see-also"></a>Ayrıca Bkz.
 [Devenv Komut Satırı Anahtarları](../../ide/reference/devenv-command-line-switches.md)
