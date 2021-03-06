---
title: 'Nasıl yapılır: barındırma Işlemini devre dışı bırakma | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- hosting process, disabling
- vshost.exe, disabling the hosting process
ms.assetid: 9157488d-737f-454b-8d8d-36f99de38bb0
caps.latest.revision: 12
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 95dcd7da113bfe996d00e617b7c8e2f9b68864d7
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72667968"
---
# <a name="how-to-disable-the-hosting-process"></a>Nasıl Yapılır: Barındırma Sürecini Devre Dışı Bırakma
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Barındırma işlemi etkinleştirildiğinde, bazı API 'lere yapılan çağrılar etkilenebilir. Bu durumlarda, doğru sonuçları döndürmek için barındırma işlemini devre dışı bırakmak gereklidir.

### <a name="to-disable-the-hosting-process"></a>Barındırma işlemini devre dışı bırakmak için

1. @No__t_0 bir çalıştırılabilir proje açın. Yürütülebilir dosyalar üretmeyen projeler (örneğin, sınıf kitaplığı veya hizmet projeleri) bu seçeneğe sahip değildir.

2. **Proje** menüsünde **Özellikler**' e tıklayın.

3. **Hata Ayıkla** sekmesine tıklayın.

4. **Visual Studio barındırma Işlemini etkinleştir** onay kutusunu temizleyin.

   Barındırma işlemi devre dışı bırakıldığında, birkaç hata ayıklama özelliği kullanılamaz veya performans azalır. Daha fazla bilgi için bkz. [hata ayıklama ve barındırma işlemi](../debugger/debugging-and-the-hosting-process.md).

   Genel olarak, barındırma işlemi devre dışı olduğunda:

- @No__t_0 uygulamalarda hata ayıklamaya başlamak için gereken süre artar.

- Tasarım zamanı ifade değerlendirmesi kullanılamıyor.

- Kısmi güven hata ayıklaması kullanılamıyor.

## <a name="see-also"></a>Ayrıca Bkz.
 [Uygulama geliştirme sırasında](https://msdn.microsoft.com/c9497d62-3b7b-4449-88e8-cf27acc9efe6) [hata ayıklama ve barındırma işlemi](../debugger/debugging-and-the-hosting-process.md) [barındırma süreci (VSHost. exe)](../ide/hosting-process-vshost-exe.md) derlemeleri
