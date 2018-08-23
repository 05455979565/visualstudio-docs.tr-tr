---
title: IDebugEngineLaunch2 | Microsoft Docs
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
- IDebugEngineLaunch2
helpviewer_keywords:
- IDebugEngineLaunch2 interface
ms.assetid: 5eaf2ad8-3fbf-446e-b48b-5327ad3f5255
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 3b4f70dac4d8831b02e458be3b8b4e38e5703b5d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42685713"
---
# <a name="idebugenginelaunch2"></a>IDebugEngineLaunch2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [IDebugEngineLaunch2](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugenginelaunch2).  
  
Başlatma ve sonlandırma programlar için hata ayıklama altyapısı (DE) tarafından kullanılır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDebugEngineLaunch2 : IDebugEngine2  
```  
  
## <a name="notes-for-implementers"></a>Uygulayanlar için Notlar  
 Tamamen özel bir bağlantı noktası tarafından işlenen bir işlem başlatmaya özel gereksinimleriniz varsa, bu arabirim tarafından bir özel DE uygulanır. Bu genellikle DE yorumlayıcıyı parçası olduğunda ve bir betik ayıklanan işlemin durumdur: yorumlayıcı önce başlatılması gerekir ve ardından betiği yüklenen çalışmaya ve. Bir bağlantı noktası yorumlayıcı başlatabilirsiniz, ancak komut dosyası (aynı role DE sahip olduğu) bir özel işlem gerektirebilir. Yalnızca özel bir bağlantı noktası işleyemiyor bir programın tanıtımından benzersiz gereksinimleri varsa, bu arabirim uygulanır.  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 Bu arabirim SDM sağlayabilirseniz bu arabirim oturum hata ayıklama Yöneticisi (SDM) tarafından çağrılır [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md) (QueryInterface kullanarak) arabirim. Bu arabirim elde edilebilir, DE özel gereksinimleri vardır ve başlatabiliyorsanız bağlantı noktası yerine programını başlatmak için bu arabirimi çağırır SDM bilir.  
  
## <a name="methods-in-vtable-order"></a>Vtable sırayla yöntemleri  
 Aşağıdaki tabloda yöntemlerini gösterilmektedir `IDebugEngineLaunch2`.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[LaunchSuspended](../../../extensibility/debugger/reference/idebugenginelaunch2-launchsuspended.md)|Bir işlem DE yoluyla başlatır.|  
|[ResumeProcess](../../../extensibility/debugger/reference/idebugenginelaunch2-resumeprocess.md)|Sürdürür, yürütme işlemi.|  
|[CanTerminateProcess](../../../extensibility/debugger/reference/idebugenginelaunch2-canterminateprocess.md)|Bir işlemin sona erdirilecek belirler.|  
|[TerminateProcess](../../../extensibility/debugger/reference/idebugenginelaunch2-terminateprocess.md)|Bir işlemi sonlandırır.|  
  
## <a name="requirements"></a>Gereksinimler  
 Üstbilgi: Msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)

