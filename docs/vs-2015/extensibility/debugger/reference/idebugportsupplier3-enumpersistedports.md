---
title: IDebugPortSupplier3::EnumPersistedPorts | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IDebugPortSupplier3::EnumPersistedPorts
helpviewer_keywords:
- IDebugPortSupplier3::EnumPersistedPorts
ms.assetid: 1c3dead3-5d6c-4067-8418-4015f0b0dd07
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 8f821c72259a77618c6cd83fe6df84837e21a6db
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42630217"
---
# <a name="idebugportsupplier3enumpersistedports"></a>IDebugPortSupplier3::EnumPersistedPorts
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugPortSupplier3::EnumPersistedPorts](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugportsupplier3-enumpersistedports).  
  
Bu yöntem, kalıcı bağlantı noktalarının listesi numaralandırmasına izin veren bir nesneyi alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT EnumPersistedPorts(  
   BSTR_ARRAY         PortNames,  
   IEnumDebugPorts2** ppEnum  
);  
```  
  
```csharp  
int EnumPersistedPorts(  
   BSTR_ARRAY           PortNames,  
   out IEnumDebugPorts2 ppEnum  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `PortNames`  
 [in] A [BSTR_ARRAY](../../../extensibility/debugger/reference/bstr-array.md) bulun ve kalıcı bağlantı noktaları arasında döndürmek için bağlantı noktası adları listesini içeren yapısı. Yalnızca kalıcı bağlantı noktalarından şu adlara sahip döndürülür.  
  
 `ppEnum`  
 [out] Uygulayan bir nesne [IEnumDebugPorts2](../../../extensibility/debugger/reference/ienumdebugports2.md) arabirimi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Bağlantı noktası sağlayıcısı örneği ve bağlantı noktası sağlayıcısı kaldırıldığında kaydedilen kalıcı bağlantı noktaları yüklenir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugPortSupplier3](../../../extensibility/debugger/reference/idebugportsupplier3.md)   
 [IEnumDebugPorts2](../../../extensibility/debugger/reference/ienumdebugports2.md)   
 [BSTR_ARRAY](../../../extensibility/debugger/reference/bstr-array.md)

