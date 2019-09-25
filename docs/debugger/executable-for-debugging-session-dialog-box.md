---
title: Hata ayıklama oturumu için yürütülebilir Iletişim kutusu | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vs.debug.exefordebug
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- executable files, specifying when debugging
- DLLs, debugging
- debugger, Executable for Debugging Session dialog box
- Executable for Debugging Session dialog box
ms.assetid: c0ddbe32-b99f-4425-acf1-f48842804f56
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 14d4ac95aae860e0750af66aec6adb2969434f11
ms.sourcegitcommit: ea182703e922c74725045afc251bcebac305068a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/24/2019
ms.locfileid: "71211057"
---
# <a name="executable-for-debugging-session-dialog-box"></a>Hata Ayıklama Oturumu İçin Yürütülebilir İletişim Kutusu

Bu iletişim kutusu, çalıştırılabilir dosya belirtilmediğinde bir DLL 'de hata ayıklamaya çalıştığınızda görüntülenir. Visual Studio doğrudan bir DLL başlatamıyor. Bunun yerine, Visual Studio belirtilen yürütülebiliri başlatır. Yürütülebilir dosya tarafından çağrıldığında DLL 'de hata ayıklaması yapabilirsiniz.

 **Yürütülebilir dosya adı** Hata ayıklaması yaptığınız DLL 'yi çağıran bir yürütülebilir dosyanın yolunu girin.

 **Projenin erişilebileceği URL (yalnızca atl sunucusu)** ATL sunucu DLL dosyasında hata ayıklaması yapıyorsanız, projenin bulunabileceği URL 'YI girin.

 Bu ayarlar girildikten sonra proje özelliği sayfalarında depolanır, bu nedenle sonraki hata ayıklama oturumları için bunları yeniden girmeniz gerekmez. Ayarları değiştirmeniz gerekiyorsa, özellik sayfalarını açıp değerleri değiştirebilirsiniz. Hata ayıklama oturumu için yürütülebilir dosya belirtme hakkında daha fazla bilgi için bkz. [hata ayıklama dll 'leri](../debugger/how-to-debug-from-a-dll-project.md).

## <a name="see-also"></a>Ayrıca Bkz.

- [Visual Studio’da hata ayıklama](../debugger/index.yml)
- [Hata ayıklayıcıya ilk bakış](../debugger/debugger-feature-tour.md)