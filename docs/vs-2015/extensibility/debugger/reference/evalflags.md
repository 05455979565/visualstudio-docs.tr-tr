---
title: EVALFLAGS | Microsoft Docs
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
- EVALFLAGS
helpviewer_keywords:
- EVALFLAGS enumeration
ms.assetid: 7b2cb14a-511a-4fef-9e4f-308139719fba
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 088c63fb1683bdf277ed1c3c5aba06a3156efbbf
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42686118"
---
# <a name="evalflags"></a>EVALFLAGS
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [EVALFLAGS](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/evalflags).  
  
İfade değerlendirme denetim bayrakları belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
enum enum_EVALFLAGS {  
   EVAL_RETURNVALUE = 0x0002,  
   EVAL_NOSIDEEFFECTS = 0x0004,  
   EVAL_ALLOWBPS = 0x0008,  
   EVAL_ALLOWERRORREPORT = 0x0010,  
   EVAL_FUNCTION_AS_ADDRESS = 0x0040,  
   EVAL_NOFUNCEVAL = 0x0080,  
   EVAL_NOEVENTS = 0x1000  
};  
typedef DWORD EVALFLAGS;  
```  
  
```csharp  
public enum enum_EVALFLAGS {  
   EVAL_RETURNVALUE = 0x0002,  
   EVAL_NOSIDEEFFECTS = 0x0004,  
   EVAL_ALLOWBPS = 0x0008,  
   EVAL_ALLOWERRORREPORT = 0x0010,  
   EVAL_FUNCTION_AS_ADDRESS = 0x0040,  
   EVAL_NOFUNCEVAL = 0x0080,  
   EVAL_NOEVENTS = 0x1000  
}  
```  
  
## <a name="members"></a>Üyeler  
 EVAL_RETURNVALUE  
 Dönüş değeri varsa, değerlendirilecek belirtir.  
  
 EVAL_NOSIDEEFFECTS  
 Yan etkileri izin verilmeyeceğini belirtir.  
  
 EVAL_ALLOWBPS  
 Durdurma kesme noktalarında belirtir.  
  
 EVAL_ALLOWERRORREPORT  
 Hata izin verilmesi için konağa raporlama belirtir. Internet Explorer'da komut ifade değerlendirmesi için kullanılır.  
  
 EVAL_FUNCTION_AS_ADDRESS  
 İşlev çağırma yerine adresleri olarak değerlendirilecek işlevleri zorlar.  
  
 EVAL_NOFUNCEVAL  
 İşlevi, değerlendirilen öğesinden engeller. Örneğin, düşünün `int` ifade belirteci `myExpression(int) + 10`. Bu işlev bir adres, ancak bir değer olarak değil doğru değerlendirilebilir.  
  
 EVAL_NOEVENTS  
 İfade değerlendirme sırasında meydana gelen olayları oturum hata ayıklama Yöneticisi (SDM) veya IDE gönderilmemelidir belirten bayrak.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu bayraklar bağımsız değişken olarak geçirilen [EvaluateAsync](../../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md) ve [EvaluateSync](../../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md) yöntemleri.  
  
 Bu bayraklar bir bit düzeyinde OR ile birleştirilebilir.  
  
## <a name="requirements"></a>Gereksinimler  
 Üstbilgi: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sabit listeleri](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [EvaluateAsync](../../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md)   
 [EvaluateSync](../../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md)

