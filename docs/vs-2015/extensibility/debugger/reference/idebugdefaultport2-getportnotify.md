---
title: IDebugDefaultPort2::GetPortNotify | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IDebugDefaultPort2::GetPortNotify
helpviewer_keywords:
- IDebugDefaultPort2::GetPortNotify
ms.assetid: 3ae715ee-9886-4694-a52b-59bb3b27467a
caps.latest.revision: 12
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: c0f5b1faf000ef982e38736b3cd3ea89a1dc2dc0
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "68196279"
---
# <a name="idebugdefaultport2getportnotify"></a>IDebugDefaultPort2::GetPortNotify
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu yöntem alır bir [IDebugPortNotify2](../../../extensibility/debugger/reference/idebugportnotify2.md) Bu bağlantı noktası için arabirim.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT GetPortNotify(  
   IDebugPortNotify2** ppPortNotify  
);  
```  
  
```csharp  
int GetPortNotify(  
   out IDebugPortNotify2 ppPortNotify  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `ppPortNotify`  
 [out] Bir [IDebugPortNotify2](../../../extensibility/debugger/reference/idebugportnotify2.md) nesne.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Normalde, `QueryInterface` yöntemi, uygulama nesnesi üzerinde çağrıldığında [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md) arabirimi almak için bir [IDebugPortNotify2](../../../extensibility/debugger/reference/idebugportnotify2.md) arabirimi. Ancak, istendiği arayüz farklı bir nesne üzerinde uygulanmadı koşullar vardır. Bu yöntem bu koşullarda gizler ve döndürür `IDebugPortNotify2` en uygun nesnesinden arabirimi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugDefaultPort2](../../../extensibility/debugger/reference/idebugdefaultport2.md)   
 [IDebugPortNotify2](../../../extensibility/debugger/reference/idebugportnotify2.md)
