---
title: UNMANAGED_ADDRESS_PHYSICAL | Microsoft Dokümanlar
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- UNMANAGED_ADDRESS_PHYSICAL
helpviewer_keywords:
- UNMANAGED_ADDRESS_PHYSICAL structure
ms.assetid: fed09686-caa6-4efc-851e-a0432019e9d0
author: acangialosi
ms.author: anthc
manager: jillfra
ms.workload:
- vssdk
dev_langs:
- CPP
- CSharp
ms.openlocfilehash: 9070fcfbf79fb96ecff87a793c221f3e7a65c2ae
ms.sourcegitcommit: 16a4a5da4a4fd795b46a0869ca2152f2d36e6db2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/06/2020
ms.locfileid: "80713283"
---
# <a name="unmanaged_address_physical"></a>UNMANAGED_ADDRESS_PHYSICAL
Bu yapı fiziksel bir adresi temsil eder.

## <a name="syntax"></a>Sözdizimi

```cpp
typedef struct _tagUNMANAGED_ADDRESS_PHYSICAL {
   ULONGLONG offset;
} UNMANAGED_ADDRESS_PHYSICAL;
```

```csharp
public struct UNMANAGED_ADDRESS_PHYSICAL {
   public ulong offset;
}
```

## <a name="members"></a>Üyeler
 `offset`\
 Fiziksel bir adres alanına 64 bit lik ofset.

## <a name="remarks"></a>Açıklamalar
 Bu yapı, `DEBUG_ADDRESS_UNION` yapı alanı [(ADDRESS_KIND](../../../extensibility/debugger/reference/address-kind.md) numaralandırmadan bir değer) `ADDRESS_KIND_UNMANAGED_PHYSICAL` `dwKind` ayarlandığında, [DEBUG_ADDRESS_UNION](../../../extensibility/debugger/reference/debug-address-union.md) yapıdaki birliğin bir parçasıdır.

## <a name="requirements"></a>Gereksinimler
 Üstbilgi: sh.h

 Ad alanı: Microsoft.VisualStudio.Debugger.Interop

 Montaj: Microsoft.VisualStudio.Debugger.Interop.dll

## <a name="see-also"></a>Ayrıca bkz.
- [Yapılar ve Birleşimler](../../../extensibility/debugger/reference/structures-and-unions.md)
- [DEBUG_ADDRESS_UNION](../../../extensibility/debugger/reference/debug-address-union.md)
