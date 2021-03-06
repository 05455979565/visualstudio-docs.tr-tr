---
title: ClickOnce önbelleğine genel bakış | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- Windows applications, ClickOnce deployemtn
- ClickOnce applications, cache
- ClickOnce deployment, cache
ms.assetid: e379921e-9ef1-4326-bbf3-53ba67925526
caps.latest.revision: 14
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 58ea758ea10e2c58ff123a2bc991f14191db0aa1
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "68151661"
---
# <a name="clickonce-cache-overview"></a>ClickOnce Önbelleğine Genel Bakış
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Tüm [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] uygulamaları, yerel olarak yüklü veya çevrimiçi barındırılan depolanır istemci bilgisayarda bir [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)]uygulama *önbellek*. A [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] Documents and Settings klasörü geçerli kullanıcının yerel ayarlarını dizininin altında gizli dizinler ailesinin bir önbellektir. Bu önbellek, derlemeleri, yapılandırma dosyaları, uygulama ve kullanıcı ayarlarını ve veri dizini gibi uygulamanın tüm dosyaları içerir. Önbellek, uygulamanın veri dizini en son sürüme geçirmek için sorumludur. Veri geçişi hakkında daha fazla bilgi için bkz. [erişen yerel ve uzak veri ClickOnce uygulamalarında](../deployment/accessing-local-and-remote-data-in-clickonce-applications.md).  
  
 Uygulama depolaması için tek bir konum sağlayarak [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] kullanıcıdan uygulamanın fiziksel yükleme yönetme görevini kazanır. Önbelleğe derlemeler ve veri dosyaları için tüm uygulamaları otomatik olarak kilitlenmesini sağlayarak uygulamalarını yalıtmak da yardımcı olur ve farklı sürümlerine birbirinden ayırın. Örneğin, yükseltme yaptığınızda bir [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] uygulama sürümü ve veri kaynaklarıyla önbelleğinde kendi dizinlerle sağlanır.  
  
## <a name="cache-storage-quota"></a>Önbellek depolama kotası  
 [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] Çevrimiçi barındırılan uygulamalar olunabilecek boşluk boyutunu sınırlayan bir kota tarafından kısıtlı [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] önbellek. Önbellek boyutu, kullanıcının tüm çevrimiçi uygulamalar için geçerlidir; tek bir kısmen güvenilen, çevrimiçi uygulama yarısı kota alanı kaplayan sınırlıdır. Yüklü uygulamalar, önbellek boyutuyla sınırlı değildir ve önbellek sınırınızı sayılmaz. Tüm [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] uygulamalar, önbelleğe yalnızca geçerli sürümü ve daha önce yüklü olan sürümü korur.  
  
 Çevrimiçi 250 MB depolama alanı için varsayılan olarak, istemci bilgisayarlara sahip [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] uygulamalar. Veri dosyaları, bu sınır içinde sayılmaz. Bir Sistem Yöneticisi büyütebilir veya kayıt defteri anahtarı DWORD değerini olan HKEY_CURRENT_USER\Software\Classes\Software\Microsoft\Windows\CurrentVersion\Deployment\OnlineAppQuotaInKB değiştirerek belirli bir istemci bilgisayar üzerinde bu kotayı azaltmak Bu, önbellek boyutu kilobayt cinsinden ifade eder. Örneğin, 50 MB önbellek boyutunu azaltmak amacıyla, bu değer 51200 yapmanız gerekir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ClickOnce Uygulamalarında Yerel ve Uzak Veri Erişimi](../deployment/accessing-local-and-remote-data-in-clickonce-applications.md)
