---
title: PROGRAM_DESTROY_FLAGS | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
helpviewer_keywords:
- PROGRAM_DESTROY_FLAGS enumeration
ms.assetid: be00d4a3-d5b8-4159-b632-64577f534883
caps.latest.revision: 8
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 16933eb409f55be209d54c26d0c077ed96f53cb1
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "68205004"
---
# <a name="programdestroyflags"></a>PROGRAM_DESTROY_FLAGS
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Geçerli numaralandırır programının değerlerini bayrakları yok.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
enum enum_PPROGRAM_DESTROY_FLAGS  
{  
   PROGRAM_DESTROY_CONTINUE_DEBUGGING = 0x1  
};  
typedef DWORD PROGRAM_DESTROY_FLAGS;  
```  
  
```csharp  
public enum enum_PPROGRAM_DESTROY_FLAGS  
{  
   PROGRAM_DESTROY_CONTINUE_DEBUGGING = 0x1  
};  
```  
  
## <a name="terms"></a>Koşulları  
 PROGRAM_DESTROY_CONTINUE_DEBUGGING  
 Program yok, ancak hata ayıklamaya devam.  
  
## <a name="remarks"></a>Açıklamalar  
 Sabit listesi tarafından döndürülen [GetFlags](../../../extensibility/debugger/reference/idebugprogramdestroyeventflags2-getflags.md) yöntemi.  
  
## <a name="requirements"></a>Gereksinimler  
 Üst bilgi: Msdbg.h  
  
 Ad alanı: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sabit listeleri](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [GetFlags](../../../extensibility/debugger/reference/idebugprogramdestroyeventflags2-getflags.md)
