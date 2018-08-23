---
title: IEnumDebugReferenceInfo2 | Microsoft Docs
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
- IEnumDebugReferenceInfo2
helpviewer_keywords:
- IEnumDebugReferenceInfo2
ms.assetid: 7ed01441-686f-4032-8268-a4c750f19f85
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 891022c12d3fe463c165653b5bf0b054efa751d5
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42693831"
---
# <a name="ienumdebugreferenceinfo2"></a>IEnumDebugReferenceInfo2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IEnumDebugReferenceInfo2](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/ienumdebugreferenceinfo2).  
  
Bu arabirim numaralandırır [DEBUG_REFERENCE_INFO](../../../extensibility/debugger/reference/debug-reference-info.md) yapıları.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IEnumDebugReferenceInfo2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Uygulayanlar için Notlar  
 Hata ayıklama altyapısı (DE), bellekte nesnelere başvurular için kendi destek bir parçası olarak bu arabirimi uygular. Bu arabirim, yalnızca başvuru destekleniyorsa uygulanmalıdır.  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 Visual Studio çağrıları [EnumChildren](../../../extensibility/debugger/reference/idebugreference2-enumchildren.md) bu arabirimi elde edilir.  
  
## <a name="methods-in-vtable-order"></a>Vtable sırayla yöntemleri  
 Aşağıdaki tabloda yöntemlerini gösterilmektedir `IEnumDebugReferenceInfo2`.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[Next](../../../extensibility/debugger/reference/ienumdebugreferenceinfo2-next.md)|Belirtilen sayıda alır [DEBUG_REFERENCE_INFO](../../../extensibility/debugger/reference/debug-reference-info.md) yapıları, bir sabit listesi sırası.|  
|[Atla](../../../extensibility/debugger/reference/ienumdebugreferenceinfo2-skip.md)|Belirtilen sayıda atlar [DEBUG_REFERENCE_INFO](../../../extensibility/debugger/reference/debug-reference-info.md) yapıları, sabit listesi sırası.|  
|[Sıfırlama](../../../extensibility/debugger/reference/ienumdebugreferenceinfo2-reset.md)|Bir numaralandırma sıralı başlangıç durumuna sıfırlar.|  
|[Kopya](../../../extensibility/debugger/reference/ienumdebugreferenceinfo2-clone.md)|Geçerli Numaralandırıcı aynı numaralandırma duruma içeren bir numaralandırıcı oluşturur.|  
|[GetCount](../../../extensibility/debugger/reference/ienumdebugreferenceinfo2-getcount.md)|Sayısını alır [DEBUG_REFERENCE_INFO](../../../extensibility/debugger/reference/debug-reference-info.md) yapılarda bir numaralandırıcı.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bir özellik adı, türü ve adresi iken temel olarak bir tür ve adres başvurusudur. Bir başvuru nesnesi var. belleğinde başvurulan olduğu sürece devam ettirir. Bkz: [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md) daha fazla ayrıntı için.  
  
## <a name="requirements"></a>Gereksinimler  
 Üstbilgi: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Temel arabirimler](../../../extensibility/debugger/reference/core-interfaces.md)   
 [DEBUG_REFERENCE_INFO](../../../extensibility/debugger/reference/debug-reference-info.md)   
 [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)   
 [EnumChildren](../../../extensibility/debugger/reference/idebugreference2-enumchildren.md)

