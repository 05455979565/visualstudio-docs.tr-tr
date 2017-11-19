---
title: IDebugModule2::ReloadSymbols_Deprecated | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDebugModule2::ReloadSymbols
helpviewer_keywords: IDebugModule2::ReloadSymbols method
ms.assetid: 0f9f0133-7d58-4cd9-a6ca-1141e095749d
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 3923431ed4936cf34a077d8d5d818c96e9630221
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="idebugmodule2reloadsymbolsdeprecated"></a>IDebugModule2::ReloadSymbols_Deprecated
KULLANIMDAN KALKTI. KULLANMAYIN. Bu modül simgelerini yeniden yükler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
HRESULT ReloadSymbols(   
   LPCOLESTR pszUrlToSymbols,  
   BSTR*     pbstrDebugMessage  
);  
```  
  
```csharp  
int ReloadSymbols(   
   string     pszUrlToSymbols,  
   out string pbstrDebugMessage  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pszUrlToSymbols`  
 [in] Sembol deposu yolu.  
  
 `pbstrDebugMessage`  
 [out] Modül adı modülleri penceresinde sağındaki görüntülenen bir durum veya hata iletisi gibi bir bilgilendirme iletisi döndürür.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür. Hata ayıklama altyapısı her zaman döndürmelidir `E_FAIL`.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntem artık desteklenmiyor. Uygulama [LoadSymbols](../../../extensibility/debugger/reference/idebugmodule3-loadsymbols.md) yöntemi yerine.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDebugModule2](../../../extensibility/debugger/reference/idebugmodule2.md)   
 [LoadSymbols](../../../extensibility/debugger/reference/idebugmodule3-loadsymbols.md)