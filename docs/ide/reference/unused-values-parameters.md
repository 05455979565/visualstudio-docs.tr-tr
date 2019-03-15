---
title: Kullanılmayan değerleri ve parametreler
ms.date: 02/15/2019
ms.topic: reference
author: kendrahavens
ms.author: kendrahavens
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- dotnet
ms.openlocfilehash: 1ea80887fff6dcb1afba80feb782b23d1e790579
ms.sourcegitcommit: 11337745c1aaef450fd33e150664656d45fe5bc5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57325347"
---
# <a name="unused-expression-values-and-parameters"></a>Kullanılmayan ifade değerleri ve parametreler

Bu yeniden düzenleme için geçerlidir:

- C#
- Visual Basic

**Ne:** Belirerek kullanılmayan parametreleri ve kullanılmayan ifade değerleri için bir uyarı oluşturur.

**ne zaman:** Parametreleri veya hiçbir zaman kullanılmaz ifade değerleri var.

**Neden:** Bazen bir değer ya da parametre artık kullanılıp kullanılmadığını ayırt etmek zor olabilir. Bu değerleri Soluklaşan veya bir uyarı verme, hangi kod silebilmeniz için görsel bir ipucu alın.

## <a name="unused-expression-values-and-parameters-diagnostic"></a>Kullanılmayan ifade değerleri ve parametre tanılama

1. Herhangi bir ifade değeri veya kullanılmayan parametresi vardır.
2. Kullanılmayan parametre soluk görünür uğradı. Kullanılmayan ifade değeri, bir uyarı alır.

  ![Kullanılmayan parametre](media/unused-parameter.png)
  ![kullanılmayan değer](media/unused-value.png)

## <a name="see-also"></a>Ayrıca bkz.

- [Yeniden Düzenleme](../refactoring-in-visual-studio.md)
- [.NET Geliştiricileri için İpuçları](../../ide/visual-studio-2017-for-dotnet-developers.md)