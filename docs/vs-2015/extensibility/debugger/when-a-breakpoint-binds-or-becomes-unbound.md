---
title: Bir kesme noktası bağlandığı veya bağlanmamış hale geldiği zaman | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], breakpoint unbound events
- breakpoint bound events
ms.assetid: 61bf00b2-8293-49d3-b919-1efb0dec9151
caps.latest.revision: 8
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: f1425edc2c8fc3fe8c38c133388f90b18b516b09
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "68162171"
---
# <a name="when-a-breakpoint-binds-or-becomes-unbound"></a>Kesme Noktasının Bağlandığı veya Bağlanmamış Hale Geldiği Durumlar
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bir kesme noktası için bir çağrı yapılır zaman bağlanamaz olduğunda [IDebugPendingBreakpoint2::CanBind](../../extensibility/debugger/reference/idebugpendingbreakpoint2-canbind.md) yöntemi, bağlama süresi ve oluşturma zamanı kesme noktasının farklıdır.  
  
## <a name="methods-called"></a>Olarak adlandırılan yöntemler  
 Oturum hata ayıklama Yöneticisi (SDM) aşağıdaki yöntemleri çağırır:  
  
1. [IDebugEngine2::CreatePendingBreakpoint](../../extensibility/debugger/reference/idebugengine2-creatependingbreakpoint.md). DE döndürür bir [IDebugPendingBreakpoint2](../../extensibility/debugger/reference/idebugpendingbreakpoint2.md).  
  
2. [IDebugPendingBreakpoint2::Enable](../../extensibility/debugger/reference/idebugpendingbreakpoint2-enable.md).  
  
3. [IDebugPendingBreakpoint2::Virtualize](../../extensibility/debugger/reference/idebugpendingbreakpoint2-virtualize.md).  
  
4. [IDebugPendingBreakpoint2::Bind](../../extensibility/debugger/reference/idebugpendingbreakpoint2-bind.md) yöntemi ve başarılıysa S_OK döndürür. DE gönderen bir [IDebugBreakpointBoundEvent2](../../extensibility/debugger/reference/idebugbreakpointboundevent2.md) veya [IDebugBreakpointErrorEvent2](../../extensibility/debugger/reference/idebugbreakpointerrorevent2.md).  
  
5. [IDebugBreakpointBoundEvent2::GetPendingBreakpoint](../../extensibility/debugger/reference/idebugbreakpointboundevent2-getpendingbreakpoint.md) ve [IDebugBreakpointBoundEvent2::EnumBoundBreakpoints](../../extensibility/debugger/reference/idebugbreakpointboundevent2-enumboundbreakpoints.md) doğrulamak ve bağlı kesme noktalarını almak için yöntemleri.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata Ayıklayıcısı Olaylarını Çağırma](../../extensibility/debugger/calling-debugger-events.md)
