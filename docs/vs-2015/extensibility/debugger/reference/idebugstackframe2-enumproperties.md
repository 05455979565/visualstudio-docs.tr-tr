---
title: IDebugStackFrame2::EnumProperties | Microsoft Docs
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
- IDebugStackFrame2::EnumProperties
helpviewer_keywords:
- IDebugStackFrame2::EnumProperties
ms.assetid: 334bb95e-c7e0-4008-9f06-8c3999e47ee8
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 5cbbdfe2585ec7fa90b2e98bbd76baa5093f296e
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42628337"
---
# <a name="idebugstackframe2enumproperties"></a>IDebugStackFrame2::EnumProperties
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugStackFrame2::EnumProperties](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugstackframe2-enumproperties).  
  
Yığın çerçevesinde yerel değişkenler gibi ilişkili özellikleri için bir numaralandırıcı oluşturur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT EnumProperties (   
   DEBUGPROP_INFO_FLAGS      dwFieldSpec,  
   UINT                      nRadix,  
   REFIID                    refiid,  
   DWORD                     dwTimeout,  
   ULONG*                    pcelt,  
   IEnumDebugPropertyInfo2** ppEnum  
);  
```  
  
```csharp  
int EnumProperties (   
   enum_DEBUGPROP_INFO_FLAGS   dwFieldSpec,  
   uint                        nRadix,  
   ref Guid                    refiid,  
   uint                        dwTimeout,  
   out uint                    pcelt,  
   out IEnumDebugPropertyInfo2 ppEnum  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `dwFieldSpec`  
 [in] Bayraklarının bir birleşimi [DEBUGPROP_INFO_FLAGS](../../../extensibility/debugger/reference/debugprop-info-flags.md) hangi alanların numaralandırılmış belirten numaralandırma [DEBUG_PROPERTY_INFO](../../../extensibility/debugger/reference/debug-property-info.md) yapılardır doldurulmalıdır.  
  
 `nRadix`  
 [in] Sayısal yedeklenmesine biçimlendirmede kullanılacak sayı tabanı.  
  
 `refiid`  
 [in] Bir GUID, seçmek için kullanılan bir filtre [DEBUG_PROPERTY_INFO](../../../extensibility/debugger/reference/debug-property-info.md) yapılardır, gibi sıralanması `guidFilterLocals`.  
  
 `dwTimeout`  
 [in] Bu yöntemden geri dönmeden önce beklenecek milisaniye cinsinden en uzun süre. Kullanım `INFINITE` süresiz bekleme.  
  
 `pcelt`  
 [out] Numaralandırılan özellikleri sayısını döndürür. Arama ile aynıdır [GetCount](../../../extensibility/debugger/reference/ienumdebugpropertyinfo2-getcount.md) yöntemi.  
  
 `ppEnum`  
 [out] Döndürür bir [IEnumDebugPropertyInfo2](../../../extensibility/debugger/reference/ienumdebugpropertyinfo2.md) istenen özellikler listesini içeren nesne.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntem, seçili tüm özellikleri ile tek bir çağrı alınacak izin verdiğinden, sıralı olarak çağrı daha hızlı [GetDebugProperty](../../../extensibility/debugger/reference/idebugstackframe2-getdebugproperty.md) ve [EnumChildren](../../../extensibility/debugger/reference/idebugproperty2-enumchildren.md) yöntemleri.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md)   
 [DEBUGPROP_INFO_FLAGS](../../../extensibility/debugger/reference/debugprop-info-flags.md)   
 [IEnumDebugPropertyInfo2](../../../extensibility/debugger/reference/ienumdebugpropertyinfo2.md)   
 [GetCount](../../../extensibility/debugger/reference/ienumdebugpropertyinfo2-getcount.md)   
 [GetDebugProperty](../../../extensibility/debugger/reference/idebugstackframe2-getdebugproperty.md)   
 [EnumChildren](../../../extensibility/debugger/reference/idebugproperty2-enumchildren.md)

