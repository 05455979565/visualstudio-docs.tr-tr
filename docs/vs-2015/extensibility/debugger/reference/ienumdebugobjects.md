---
title: IEnumDebugObjects | Microsoft Docs
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
- IEnumDebugObjects
helpviewer_keywords:
- IEnumDebugObjects interface
ms.assetid: 0950364c-6c8a-4b6c-ba37-c6aa359fa72c
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 3fdb43790d10ffac3fe081369976fe6ee27e0786
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42694472"
---
# <a name="ienumdebugobjects"></a>IEnumDebugObjects
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IEnumDebugObjects](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/ienumdebugobjects).  
  
> [!IMPORTANT]
>  Visual Studio 2015'te, bu şekilde ifade değerlendiricisi uygulama kullanım dışı bırakılmıştır. CLR ifade değerlendiricisi uygulama hakkında daha fazla bilgi için lütfen bkz [CLR ifade Değerlendiricilerini](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) ve [yönetilen ifade değerlendiricisi örnek](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).  
  
 Bu arabirimi uygulayan nesnelerin bir koleksiyonunu temsil eder [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) arabirimi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IEnumDebugObjects : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Uygulayanlar için Notlar  
 İfade değerlendirici uygulayan nesne kümeleri sağlamak için bu arabirimi uygulayan [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) arabirimi. Bu varlığı nedeniyle standart bir COM numaralandırma olmadığını unutmayın [GetCount](../../../extensibility/debugger/reference/ienumdebugobjects-getcount.md) yöntemi.  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 [GetElements](../../../extensibility/debugger/reference/idebugarrayobject-getelements.md) bu arabirimi döndürür.  
  
## <a name="methods-in-vtable-order"></a>Vtable sırayla yöntemleri  
 Bu arabirim, aşağıdaki yöntemleri uygular.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[Next](../../../extensibility/debugger/reference/ienumdebugobjects-next.md)|Sonraki alır [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) nesnelerden sabit listesi.|  
|[Atla](../../../extensibility/debugger/reference/ienumdebugobjects-skip.md)|Belirtilen bir girdi sayısı atlar.|  
|[Sıfırlama](../../../extensibility/debugger/reference/ienumdebugobjects-reset.md)|Numaralandırma ilk girişe sıfırlar.|  
|[Kopya](../../../extensibility/debugger/reference/ienumdebugobjects-clone.md)|Geçerli sabit bir kopyasını alır.|  
|[GetCount](../../../extensibility/debugger/reference/ienumdebugobjects-getcount.md)|Sabit listesi içerisindeki giriş sayısını alır.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu arabirim, dizi bir nesne üzerinden numaralandırmak bir hata ayıklama altyapısı sağlar.  
  
## <a name="requirements"></a>Gereksinimler  
 Üstbilgi: ee.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)   
 [GetElements](../../../extensibility/debugger/reference/idebugarrayobject-getelements.md)

