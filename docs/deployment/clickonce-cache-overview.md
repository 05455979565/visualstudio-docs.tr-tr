---
title: ClickOnce önbelleğine genel bakış | Microsoft Docs
ms.date: 11/04/2016
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
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 3d7abeeec4a640119e3089c795ac529a10f8dc09
ms.sourcegitcommit: d20ce855461c240ac5eee0fcfe373f166b4a04a9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/29/2020
ms.locfileid: "84182631"
---
# <a name="clickonce-cache-overview"></a>ClickOnce önbelleğine genel bakış
[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]Yerel olarak yüklenmiş veya çevrimiçi olarak barındırılan tüm uygulamalar, istemci bilgisayarda bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama *önbelleğinde*depolanır. [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]Önbellek, geçerli kullanıcının belgeler ve ayarlar klasörünün yerel ayarlar dizininde bulunan gizli dizinlerin bir ailesidir. Bu önbellek derlemeler, yapılandırma dosyaları, uygulama ve Kullanıcı ayarları ve veri dizini dahil tüm uygulama dosyalarını barındırır. Önbellek, uygulamanın veri dizinini en son sürüme geçirmeden de sorumludur. Veri taşıma hakkında daha fazla bilgi için bkz. [ClickOnce uygulamalarında yerel ve uzak verilere erişme](../deployment/accessing-local-and-remote-data-in-clickonce-applications.md).

 Uygulama depolaması için tek bir konum sağlayarak, [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] kullanıcıdan bir uygulamanın fiziksel yüklemesini yönetme görevini devralır. Önbellek Ayrıca, tüm uygulamalar için derlemeleri ve veri dosyalarını ve bunların farklı sürümlerini birbirinden ayrı tutarak uygulamaları yalıtmaya yardımcı olur. Örneğin, bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulamayı yükselttiğinizde, bu sürüm ve veri kaynakları önbellekte kendi dizinleriyle birlikte sağlanır.

## <a name="cache-storage-quota"></a>Önbellek depolama kotası
 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]çevrimiçi olarak barındırılan uygulamalar, önbelleğin boyutunu kısıtlayan bir kota ile kaplayabilecekleri alan miktarı ile sınırlıdır [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] . Önbellek boyutu kullanıcının tüm çevrimiçi uygulamalarına uygulanır; tek bir kısmen güvenilen çevrimiçi uygulama, kota alanının yarısını kaplayan bir şekilde sınırlandırılmıştır. Yüklü uygulamalar önbellek boyutuyla sınırlı değildir ve önbellek sınırına göre sayılmaz. Tüm [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulamalar için önbellek yalnızca geçerli sürümü ve daha önce yüklenen sürümü korur.

 Varsayılan olarak, istemci bilgisayarlarda çevrimiçi uygulamalar için 250 MB depolama alanı vardır [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] . Veri dosyaları bu sınıra doğru sayılmaz. Bir sistem yöneticisi, önbellek boyutunu kilobayt cinsinden ifade eden bir DWORD değeri olan **\Software\classes\software\microsoft\windows\currentversion\deployment\onlineappquocontainer kb HKEY_CURRENT_USER**kayıt defteri anahtarını değiştirerek bu kotayı belirli bir istemci bilgisayarda büyütebilir veya azaltabilir. Örneğin, önbellek boyutunu 50 MB olarak azaltmak için bu değeri 51200 olarak değiştirirsiniz.

## <a name="see-also"></a>Ayrıca bkz.
- [ClickOnce uygulamalarında yerel ve uzak veri erişimi](../deployment/accessing-local-and-remote-data-in-clickonce-applications.md)