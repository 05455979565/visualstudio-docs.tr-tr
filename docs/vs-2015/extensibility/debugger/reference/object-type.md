---
title: NESNE_TÜRÜ | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- OBJECT_TYPE
helpviewer_keywords:
- OBJECT_TYPE enumeration
ms.assetid: c4d246f9-8a98-44ec-b2bb-ff5c684f668e
caps.latest.revision: 10
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: fc23045fa70554133eba3a7f1326681bf31ea379
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "68205147"
---
# <a name="objecttype"></a>OBJECT_TYPE
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

İfade değerlendirici nesneden türünü belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
enum enum_OBJECT_TYPE {   
   OBJECT_TYPE_BOOLEAN = 0x0,  
   OBJECT_TYPE_CHAR    = 0x1,  
   OBJECT_TYPE_I1      = 0x2,  
   OBJECT_TYPE_U1      = 0x3,  
   OBJECT_TYPE_I2      = 0x4,  
   OBJECT_TYPE_U2      = 0x5,  
   OBJECT_TYPE_I4      = 0x6,  
   OBJECT_TYPE_U4      = 0x7,  
   OBJECT_TYPE_I8      = 0x8,  
   OBJECT_TYPE_U8      = 0x9,  
   OBJECT_TYPE_R4      = 0xa,  
   OBJECT_TYPE_R8      = 0xb,  
   OBJECT_TYPE_OBJECT  = 0xc,  
   OBJECT_TYPE_NULL    = 0xd,  
   OBJECT_TYPE_CLASS   = 0xe  
};  
typedef DWORD OBJECT_TYPE;  
```  
  
```csharp  
public enum enum_OBJECT_TYPE {   
   OBJECT_TYPE_BOOLEAN = 0x0,  
   OBJECT_TYPE_CHAR    = 0x1,  
   OBJECT_TYPE_I1      = 0x2,  
   OBJECT_TYPE_U1      = 0x3,  
   OBJECT_TYPE_I2      = 0x4,  
   OBJECT_TYPE_U2      = 0x5,  
   OBJECT_TYPE_I4      = 0x6,  
   OBJECT_TYPE_U4      = 0x7,  
   OBJECT_TYPE_I8      = 0x8,  
   OBJECT_TYPE_U8      = 0x9,  
   OBJECT_TYPE_R4      = 0xa,  
   OBJECT_TYPE_R8      = 0xb,  
   OBJECT_TYPE_OBJECT  = 0xc,  
   OBJECT_TYPE_NULL    = 0xd,  
   OBJECT_TYPE_CLASS   = 0xe  
};  
```  
  
## <a name="members"></a>Üyeler  
 OBJECT_TYPE_BOOLEAN  
 Bir Boole değeri bir nesne olduğunu gösterir.  
  
 OBJECT_TYPE_CHAR  
 Bir nesne bir karakter olduğunu gösterir.  
  
 OBJECT_TYPE_I1  
 Nesnesi bir bayt imzalı bir tamsayı olduğu anlamına gelir.  
  
 OBJECT_TYPE_U1  
 Bir nesne için bir tane bayt işaretsiz tamsayı olduğunu gösterir.  
  
 OBJECT_TYPE_I2  
 Nesne iki baytlık bir işaretli tamsayı olduğunu gösterir.  
  
 OBJECT_TYPE_U2  
 Bir nesne bir iki bayt işaretsiz tamsayı olduğunu gösterir.  
  
 OBJECT_TYPE_I4  
 Nesne dört baytlık bir işaretli tamsayı olduğunu gösterir.  
  
 OBJECT_TYPE_U4  
 Dört bayt işaretsiz tamsayı bir nesne olduğunu gösterir.  
  
 OBJECT_TYPE_I8  
 Nesne bir sekiz bayt imzalı tamsayı olduğunu gösterir.  
  
 OBJECT_TYPE_U8  
 Bir nesne bir sekiz bayt işaretsiz tamsayı olduğunu gösterir.  
  
 OBJECT_TYPE_R4  
 Nesne dört baytlık bir kayan noktalı sayı olduğunu gösterir.  
  
 OBJECT_TYPE_R8  
 Bir nesne bir sekiz bayt kayan noktalı sayı olduğunu gösterir.  
  
 OBJECT_TYPE_OBJECT  
 Bir nesne bir nesne olduğunu gösterir.  
  
 OBJECT_TYPE_NULL  
 Nesne NULL olduğunu gösterir.  
  
 OBJECT_TYPE_CLASS  
 Bir nesne bir sınıf olduğunu belirtir.  
  
## <a name="remarks"></a>Açıklamalar  
 Bağımsız değişken olarak geçirilen [CreatePrimitiveObject](../../../extensibility/debugger/reference/idebugfunctionobject-createprimitiveobject.md) ve [CreateArrayObject](../../../extensibility/debugger/reference/idebugfunctionobject-createarrayobject.md) yöntemleri.  
  
## <a name="requirements"></a>Gereksinimler  
 Üstbilgi: ee.h  
  
 Ad alanı: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sabit listeleri](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [CreatePrimitiveObject](../../../extensibility/debugger/reference/idebugfunctionobject-createprimitiveobject.md)   
 [CreateArrayObject](../../../extensibility/debugger/reference/idebugfunctionobject-createarrayobject.md)
