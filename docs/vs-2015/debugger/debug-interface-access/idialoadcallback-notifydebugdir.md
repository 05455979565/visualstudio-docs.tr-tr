---
title: Idialoadcallback::notifydebugdir | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- IDiaLoadCallback::NotifyDebugDir method
ms.assetid: bd04e2f6-0dbf-4742-a556-96f2cd99aa19
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4496a7941de29f4ef500a135559dcd746036f6d6
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42687790"
---
# <a name="idialoadcallbacknotifydebugdir"></a>IDiaLoadCallback::NotifyDebugDir
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [Idialoadcallback::notifydebugdir](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idialoadcallback-notifydebugdir).  
  
Hata ayıklama dizini .exe dosyasında bulundu çağrılır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT NotifyDebugDir (   
   BOOL  fExecutable,  
   DWORD cbData,  
   BYTE  data[]  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `fExecutable`  
 [in] `TRUE` hata ayıklama dizini, yürütülebilir bir dosya (.dbg Dosya yerine) salt okunur ise.  
  
 `cbData`  
 [in] Hata ayıklama dizininde bulunan verileri baytlık sayısı.  
  
 `data[]`  
 [in] Oturum hata ayıklama dizini doldurulmuş bir dizi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür. Dönüş kodu genellikle göz ardı edilir.  
  
## <a name="remarks"></a>Açıklamalar  
 [Idiadatasource::loaddataforexe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md) yürütülebilir dosya işlenirken bir hata ayıklama dizini bulduğunda, bu geri çağırma yöntemini çağırır.  
  
 Bu yöntem, hata ayıklama bilgisi .pdb dosyasında bulunan dışındaki desteklemek için istemcinin ters mühendislik hata ayıklama ve/veya yürütülebilir dosya ihtiyacını ortadan kaldırır. Bu verilerle istemcide kullanılabilir hata ayıklama bilgilerinin türünü ve bu yürütülebilir dosya veya .dbg dosyasında bulunan tanıyabilirsiniz.  
  
 Çoğu istemci çünkü bu geri çağırma gerekmeyeceğinden `IDiaDataSource::loadDataForExe` yöntemi .pdb hem .dbg dosyaları sembolleri sunmak için gerekli olduğunda şeffaf bir şekilde açılır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idialoadcallback2](../../debugger/debug-interface-access/idialoadcallback2.md)   
 [IDiaDataSource::loadDataForExe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)


