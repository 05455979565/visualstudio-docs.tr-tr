---
title: IDebugMemoryBytes2::ReadAt | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugMemoryBytes2::ReadAt
helpviewer_keywords:
- IDebugMemoryBytes2::ReadAt method
- ReadAt method
ms.assetid: b413684d-4155-4bd4-ae30-ffa512243b5f
caps.latest.revision: 14
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: f10dc6e9e00e2b7f66722f3c89b74bb14e45fdbe
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "68180585"
---
# <a name="idebugmemorybytes2readat"></a>IDebugMemoryBytes2::ReadAt
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Belirli bir konumda itibaren bayt dizisini okur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT ReadAt(   
   IDebugMemoryContext2* pStartContext,  
   DWORD                 dwCount,  
   BYTE*                 rgbMemory,  
   DWORD*                pdwRead,  
   DWORD*                pdwUnreadable  
);  
```  
  
```csharp  
int ReadAt(  
   IDebugMemoryContext2 pStartContext,  
   uint                 dwCount,  
   byte[]               rgbMemory,  
   out uint             pdwRead,  
   ref uint             pdwUnreadable  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pStartContext`  
 [in] [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md) nesnesini bayt okumaya başlayacağı konumu belirtir.  
  
 `dwCount`  
 [in] Okunacak bayt sayısı. Ayrıca belirtir `rgbMemory` dizisi.  
  
 `rgbMemory`  
 [out içinde] Bayt ile doldurulmuş dizi gerçekten okuyun.  
  
 `pdwRead`  
 [out] Aslında okumak bitişik baytların sayısını döndürür.  
  
 `pdwUnreadable`  
 [out içinde] Okunamaz bayt sayısını döndürür. İstemci in okunamaz bayt sayısı uninterested ise null değeri olabilir.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa S_OK döndürür; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 100 bayt istenir ve ilk 50 okunabilir, sonraki 20 okunamaz ve kalan 30 okunabilir varsa, bu yöntemi döndürür:  
  
 *`pdwRead` = 50  
  
 *`pdwUnreadable` = 20  
  
 Bu durumda, çünkü `*pdwRead + *pdwUnreadable < dwCount`, arayan istenen özgün 100 kalan 30 bayt okuma için ek bir çağrı yapmanız gerekir ve [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md) geçirilen nesne `pStartContext` parametresi Gelişmiş 70.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugMemoryBytes2](../../../extensibility/debugger/reference/idebugmemorybytes2.md)   
 [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md)
