---
title: DOCCONTEXT_COMPARE | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- DOCCONTEXT_COMPARE
helpviewer_keywords:
- DOCCONTEXT_COMPARE enumeration
ms.assetid: ed947c34-b07e-4b69-8381-b6e7cb842862
caps.latest.revision: 11
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 6d0fd8cff2f352c8ede674be64062a738c1f3d02
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "68198799"
---
# <a name="doccontextcompare"></a>DOCCONTEXT_COMPARE
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

İki belge bağlamları karşılaştırma ölçütü belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
enum enum_DOCCONTEXT_COMPARE {   
   DOCCONTEXT_EQUAL         = 0x0001,  
   DOCCONTEXT_LESS_THAN     = 0x0002,  
   DOCCONTEXT_GREATER_THAN  = 0x0003,  
   DOCCONTEXT_SAME_DOCUMENT = 0x0004  
};  
typedef DWORD DOCCONTEXT_COMPARE;  
```  
  
```csharp  
enum enum_DOCCONTEXT_COMPARE {   
   DOCCONTEXT_EQUAL         = 0x0001,  
   DOCCONTEXT_LESS_THAN     = 0x0002,  
   DOCCONTEXT_GREATER_THAN  = 0x0003,  
   DOCCONTEXT_SAME_DOCUMENT = 0x0004  
};  
```  
  
## <a name="members"></a>Üyeler  
 DOCCONTEXT_EQUAL  
 Hedef belge bağlamına eşit olan listesinde ilk belge bağlamı bulur.  
  
 DOCCONTEXT_LESS_THAN  
 Hedef belge bağlamı'dan küçük listedeki ilk belge bağlamı bulun.  
  
 DOCCONTEXT_GREATER_THAN  
 Hedef belge bağlamı büyük listesinde ilk belge bağlamı bulur.  
  
 DOCCONTEXT_SAME_DOCUMENT  
 Aynı belgede hedef belge bağlamı olarak listede ilk belge içeriği bulabilirsiniz.  
  
## <a name="remarks"></a>Açıklamalar  
 Bağımsız değişken olarak geçirilen [karşılaştırma](../../../extensibility/debugger/reference/idebugdocumentcontext2-compare.md) yöntemi.  
  
 Bu değerler, listedeki ilk belge içeriği bulmak için karşılaştırma ölçütleri belirtmek için kullanılır. Bir belge bağlamına belge bağlamları listesini kendisine karşı karşılaştırmak için verilen `IDebugDocumentContext2::Compare` yöntemi. Karşılaştırma işleci olan listede ilk belge bağlamı `true` sonra döndürülür.  
  
## <a name="requirements"></a>Gereksinimler  
 Üstbilgi: msdbg.h  
  
 Ad alanı: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sabit listeleri](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [Compare](../../../extensibility/debugger/reference/idebugdocumentcontext2-compare.md)
