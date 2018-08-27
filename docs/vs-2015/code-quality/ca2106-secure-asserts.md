---
title: 'Ca2106: bildirimlerin Güvenliğini sağlayın | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- CA2106
- SecureAsserts
helpviewer_keywords:
- CA2106
- SecureAsserts
ms.assetid: 91feb36e-6e2c-436c-8272-5aee31f77e98
caps.latest.revision: 21
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 67d1228b7684b2ba00a7e64f3755fb107fa0e75b
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/24/2018
ms.locfileid: "42902972"
---
# <a name="ca2106-secure-asserts"></a>CA2106: Bildirimlerin güvenliğini sağlayın
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [ca2106 bildirimlerin: bildirimlerin güvenliğini sağlayın](https://docs.microsoft.com/visualstudio/code-quality/ca2106-secure-asserts).

|||
|-|-|
|TypeName|SecureAsserts|
|CheckId|CA2106|
|Kategori|Microsoft.Security|
|Yeni Değişiklik|Yeni|

## <a name="cause"></a>Sebep
 Bir yöntem izin ileri sürer ve güvenlik önlemi olmayan çağrı üzerinde gerçekleşir.

## <a name="rule-description"></a>Kural Tanımı
 Güvenlik denetimleri yapmadan herhangi bir güvenlik izni ileri sürmek, kodunuzdaki güvenlik zayıflıklarını yararlanılabilir bırakır. Bir güvenlik izni onaylanan güvenlik yığın ilerlemesi sona erer. Çağıran tüm denetimleri yapmadan bir izin onaylama işlemi ise çağıranın dolaylı olarak kod izinlerinizi kullanarak yürütebilir. Yalnızca assert zararlı bir biçimde kullanılamaz emin olduğunuzda verilebilir güvenlik denetimleri olmadan onaylar. Assert çağırmanızı kod zararsız ise zararsız olduğunda ya da kullanıcıların çağırdığınız koda rastgele bilgi geçiremezsiniz.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Bu kural ihlalini düzeltmek için yöntemi veya metodu bildirim türünün için bir güvenlik talebi ekleyin.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Bu kuraldan bir uyarıyı dikkatli bir güvenlik incelemesinden sonra yalnızca gösterme.

## <a name="see-also"></a>Ayrıca Bkz.
 <xref:System.Security.CodeAccessPermission.Assert%2A?displayProperty=fullName> [Güvenli kodlama yönergeleri](http://msdn.microsoft.com/library/4f882d94-262b-4494-b0a6-ba9ba1f5f177)



