---
title: IPropertyProxyEESide::ResolveAssemblyRef | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- IPropertyProxyEESide::ResolveAssemblyRef
helpviewer_keywords:
- IPropertyProxyEESide::ResolveAssemblyRef
ms.assetid: 662ca0a6-dad0-4c00-a718-bb3bbc5bd9da
caps.latest.revision: 13
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 47c397746a82247a8cb1ee329d56004d013486de
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "68199495"
---
# <a name="ipropertyproxyeesideresolveassemblyref"></a>IPropertyProxyEESide::ResolveAssemblyRef
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Belirtilen yönetilen bütünleştirilmiş kod başvurusu konumunu belirler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
HRESULT ResolveAssemblyRef(  
   BSTR*                  assemName,  
   IEEDataStorage**       assemBytes,  
   IEEDataStorage**       assemPdb,  
   BSTR*                  assemLocation,  
   ASSEMBLYLOCRESOLUTION* alr  
);  
```  
  
```csharp  
int ResolveAssemblyRef(  
   ref string                     assemName,  
   out IEEDataStorage             assemBytes,  
   out IEEDataStorage             assemPdb,  
   out string                     assemLocation,  
   out enum_ASSEMBLYLOCRESOLUTION alr  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `assemName`  
 [in] Çözümlenecek derlemenin adı.  
  
 `assemBytes`  
 [out] Döndürür bir [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md) başvuru ile ilişkili derleme baytları içeren nesne.  
  
 `assemPdb`  
 [out] Döndürür bir `IEEDataStorage` sembolü içeren bir nesne, bu başvuru ile ilişkili veri depolayın.  
  
 `assemLocation`  
 [out] Bu başvuru yolu konumunu döndürür.  
  
 `alr`  
 [out] Bir değer döndürür [ASSEMBLYLOCRESOLUTION](../../../extensibility/debugger/reference/assemblylocresolution.md) bu başvurusunun derleme konumunu belirten sabit listesi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa döndürür `S_OK`; Aksi takdirde bir hata kodu döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntem, genellikle bir özel ifade değerlendiricisi tarafından uygulanmadı.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IPropertyProxyEESide](../../../extensibility/debugger/reference/ipropertyproxyeeside.md)   
 [IEEDataStorage](../../../extensibility/debugger/reference/ieedatastorage.md)   
 [ASSEMBLYLOCRESOLUTION](../../../extensibility/debugger/reference/assemblylocresolution.md)
