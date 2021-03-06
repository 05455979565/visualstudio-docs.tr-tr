---
title: Sabitler (arabirim erişimi SDK'SINDA hata ayıklama) | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- constants, DIA SDK
- DIA SDK, constants
ms.assetid: aca4ec77-bc08-4cdd-a6ce-8d4a28ea5ea3
caps.latest.revision: 10
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 931e1ab46793a5ff7e0434949330eaf4dbc820e8
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "68164432"
---
# <a name="constants-debug-interface-access-sdk"></a>Sabitler (Arabirim Erişimi SDK'sında Hata Ayıklama)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu dize sabitleri, program hata ayıklama veritabanı (PDB) dosyası DIA SDK'sı aracılığıyla çeşitli bölümlerini belirlemek için kullanılabilir.  
  
## <a name="constants"></a>Sabitler  
 Aşağıdaki C/C++ makroları olarak bildirilir.  
  
|Makrosu|Değer|  
|-----------|-----------|  
|`DiaTable_Symbols`|L "Simge"|  
|`DiaTable_Sections`|L "Bölümler"|  
|`DiaTable_SrcFiles`|L "Kaynakdosyalar"|  
|`DiaTable_LineNums`|L "Lınenumbers"|  
|`DiaTable_SegMap`|L "SegmentMap"|  
|`DiaTable_Dbg`|L "Dbg"|  
|`DiaTable_InjSrc`|L "InjectedSource"|  
|`DiaTable_FrameData`|L "FrameData"|  
  
## <a name="example"></a>Örnek  
 Şu simgelerden birini kullanarak bir örnek aşağıda verilmiştir:  
  
```cpp#  
HRESULT GetSymbolTable(IDiaEnumTables *pEnumTables, IDiaTable **pTable)  
{  
    HRESULT hr;  
    VARIANT var;  
    var.vt      = VT_BSTR;  
    var.bstrVal = SysAllocString( DiaTable_Symbols );  
    hr = pEnumTables->Item( var, pTable );  
    return(hr);  
}  
```  
  
## <a name="requirements"></a>Gereksinimler  
 Üstbilgi: dia2.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Başvuru](../../debugger/debug-interface-access/debug-interface-access-sdk-reference.md)   
 [Sabit listeleri ve yapıları](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [Arabirimler (arabirim erişimi SDK'SINDA hata ayıklama)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)   
 [IDiaEnumTables::Item](../../debugger/debug-interface-access/idiaenumtables-item.md)
