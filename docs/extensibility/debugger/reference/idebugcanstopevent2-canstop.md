---
title: IDebugCanStopEvent2::CanStop | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugCanStopEvent2::CanStop
helpviewer_keywords: IDebugCanStopEvent2::CanStop
ms.assetid: 7d61adbe-6b3d-41f3-86a1-45d9cc01a7f8
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: d9008410831d3c2c7b6e93d4f35a1d08914a5336
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugcanstopevent2canstop"></a>IDebugCanStopEvent2::CanStop
Hata ayıklama altyapısı (DE) geçerli kod konumda durdurun ya da yalnızca yürütme devam gerekip gerekmediğini bildirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT CanStop (   
   BOOL fCanStop  
);  
```  
  
```csharp  
int CanStop (   
   int fCanStop  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `fCanStop`  
 [in] Sıfır olmayan (`TRUE`) DE geçerli kod konumda; durdurmanız gerekir, aksi takdirde, sıfır (`FALSE`).  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu olay alıcısı genellikle çağırır [GetReason](../../../extensibility/debugger/reference/idebugcanstopevent2-getreason.md) DE istediği durdurmak için nedenini belirlemek için yöntem ve çağrıları `IDebugCanStopEvent2::CanStop` uygun yanıtı yöntemiyle.  
  
 DE durursa, durdurma nedenini açıklayan bir olay gönderir. Tarafından temsil edilen bir kullanıcı veya sinyal sonu gönderilir iki olay vardır [IDebugBreakEvent2](../../../extensibility/debugger/reference/idebugbreakevent2.md) arabirimi ve tarafından temsil edilen bir kesme noktası olay [IDebugBreakpointEvent2](../../../extensibility/debugger/reference/idebugbreakpointevent2.md) arabirimi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugCanStopEvent2](../../../extensibility/debugger/reference/idebugcanstopevent2.md)   
 [IDebugBreakEvent2](../../../extensibility/debugger/reference/idebugbreakevent2.md)   
 [IDebugBreakpointEvent2](../../../extensibility/debugger/reference/idebugbreakpointevent2.md)   
 [GetReason](../../../extensibility/debugger/reference/idebugcanstopevent2-getreason.md)