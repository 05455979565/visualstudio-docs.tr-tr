---
title: FIELD_INFO | Microsoft Dokümanlar
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- FIELD_INFO
helpviewer_keywords:
- FIELD_INFO structure
ms.assetid: bfafef6d-0c83-43d7-a779-1f0d24b166a1
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 6e2089746adecc583d04176afca18ad19826ea53
ms.sourcegitcommit: 16a4a5da4a4fd795b46a0869ca2152f2d36e6db2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/06/2020
ms.locfileid: "80736886"
---
# <a name="field_info"></a>FIELD_INFO
Bu yapı yerel bir değişkeni, parametreyi veya başka bir alanı açıklar.

## <a name="syntax"></a>Sözdizimi

```cpp
typedef struct _tagFieldInfo {
    FIELD_INFO_FIELDS dwFields;
    BSTR              bstrFullName;
    BSTR              bstrName;
    BSTR              bstrType;
    FIELD_MODIFIERS   dwModifiers;
} FIELD_INFO;
```

```csharp
public struct FIELD_INFO {
    public uint   dwFields;
    public string bstrFullName;
    public string bstrName;
    public string bstrType;
    public uint   dwModifiers;
};
```

## <a name="members"></a>Üyeler
`dwFields`\
Hangi üyelerin [doldurulduğuna](../../../extensibility/debugger/reference/field-info-fields.md) FIELD_INFO_FIELDS numaralandırmadan gelen bayrakların birleşimi.

`bstrFullName`\
Alanın tam adı.

`bstrName`\
Alanın kısa adı.

`bstrType`\
Alanın türü.

`dwModifiers`\
Alanı açıklayan [FIELD_MODIFIERS](../../../extensibility/debugger/reference/field-modifiers.md) numaralandırmadan gelen bayrakların birleşimi.

## <a name="remarks"></a>Açıklamalar
Bu yapı doldurulduğu [GetInfo](../../../extensibility/debugger/reference/idebugfield-getinfo.md) yöntemine aktarılır.

## <a name="requirements"></a>Gereksinimler
Üstbilgi: sh.h

Ad alanı: Microsoft.VisualStudio.Debugger.Interop

Montaj: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Ayrıca bkz.
- [Yapılar ve Birleşimler](../../../extensibility/debugger/reference/structures-and-unions.md)
- [FIELD_INFO_FIELDS](../../../extensibility/debugger/reference/field-info-fields.md)
- [FIELD_MODIFIERS](../../../extensibility/debugger/reference/field-modifiers.md)
- [GetInfo](../../../extensibility/debugger/reference/idebugfield-getinfo.md)
