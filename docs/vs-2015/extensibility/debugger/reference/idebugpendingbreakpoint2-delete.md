---
title: IDebugPendingBreakpoint2::Delete | Microsoft Docs
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
- IDebugPendingBreakpoint2::Delete
helpviewer_keywords:
- IDebugPendingBreakpoint2::Delete method
- Delete method
ms.assetid: 4cb5ed81-6f0c-41ce-a770-5adb6b4bf5d9
caps.latest.revision: 10
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 4b0e9902042033029251782918d4dc2ee8bbc268
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42687586"
---
# <a name="idebugpendingbreakpoint2delete"></a>IDebugPendingBreakpoint2::Delete
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugPendingBreakpoint2::Delete](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugpendingbreakpoint2-delete).  
  
Bu bekleyen kesme noktasının ve ondan bağlı tüm kesme noktalarını siler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT Delete(   
   void   
);  
```  
  
```csharp  
int Delete();  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür. Döndürür `E_BP_DELETED` kesme noktası silinmiş olması durumunda.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bu yöntem için basit bir uygulama gösterilmektedir `CPendingBreakpoint` uygulayan nesne [IDebugPendingBreakpoint2](../../../extensibility/debugger/reference/idebugpendingbreakpoint2.md) arabirimi.  
  
```cpp#  
HRESULT CPendingBreakpoint::Delete(void)    
{    
   HRESULT hr;    
  
   // Verify that the pending breakpoint has not been deleted. If deleted,    
   // then return hr = E_BP_DELETED.    
   if (m_state.state != PBPS_DELETED)    
   {    
      // If the pending breakpoint has bound and has an associated bound   
      // breakpoint, delete and release the bound breakpoint and set the   
      // pointer to NULL.    
      if (m_pBoundBP)    
      {    
         m_pBoundBP->Delete();    
         m_pBoundBP->Release();    
         m_pBoundBP = NULL;    
      }    
      // If the pending breakpoint did not bind and has an associated   
      // error breakpoint, release the error breakpoint and set the   
      // pointer to NULL.   
      if (m_pErrorBP)    
      {    
         m_pErrorBP->Release();    
         m_pErrorBP = NULL;    
      }    
  
      // Set the PENDING_BP_STATE in the PENDING_BP_STATE_INFO structure   
      // to deleted.     
      m_state.state = PBPS_DELETED;    
   }    
   else    
   {    
      hr = E_BP_DELETED;    
   }    
  
   return hr;    
}    
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugPendingBreakpoint2](../../../extensibility/debugger/reference/idebugpendingbreakpoint2.md)

