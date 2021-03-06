---
title: IDiaEnumFrameData | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumFrameData interface
ms.assetid: 2ca7fd5a-b2fa-4b3a-9492-0263eafc435b
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a5c99d9587de85941721ae404fefdcac7586fb08
ms.sourcegitcommit: 66f31cc4ce1236e638ab58d2f70d3646206386fa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/27/2020
ms.locfileid: "85468303"
---
# <a name="idiaenumframedata"></a>IDiaEnumFrameData
Veri kaynağında bulunan çeşitli çerçeve verisi öğelerini numaralandırır.

## <a name="syntax"></a>Syntax

```
IDiaEnumFrameData : IUnknown
```

## <a name="methods-in-vtable-order"></a>Vtable sırasındaki Yöntemler
Aşağıdaki tabloda, yöntemleri gösterilmektedir `IDiaEnumFrameData` .

|Yöntem|Açıklama|
|------------|-----------------|
|[IDiaEnumFrameData::get__NewEnum](../../debugger/debug-interface-access/idiaenumframedata-get-newenum.md)|`IEnumVARIANT Interface`Bu Numaralandırıcı sürümünü alır.|
|[IDiaEnumFrameData::get_Count](../../debugger/debug-interface-access/idiaenumframedata-get-count.md)|Çerçeve verisi öğelerinin sayısını alır.|
|[IDiaEnumFrameData::Item](../../debugger/debug-interface-access/idiaenumframedata-item.md)|Bir kare veri öğesini bir dizin aracılığıyla alır.|
|[IDiaEnumFrameData::Next](../../debugger/debug-interface-access/idiaenumframedata-next.md)|Sabit Listesi dizisinde belirtilen sayıda çerçeve verisi öğesini alır.|
|[IDiaEnumFrameData::Skip](../../debugger/debug-interface-access/idiaenumframedata-skip.md)|Bir numaralandırma dizisindeki belirtilen sayıda çerçeve verisi öğesini atlar.|
|[IDiaEnumFrameData::Reset](../../debugger/debug-interface-access/idiaenumframedata-reset.md)|Bir numaralandırma dizisini başlangıca sıfırlar.|
|[IDiaEnumFrameData::Clone](../../debugger/debug-interface-access/idiaenumframedata-clone.md)|Geçerli numaralandırıcı ile aynı numaralandırma durumunu içeren bir Numaralandırıcı oluşturur.|
|[IDiaEnumFrameData::frameByRVA](../../debugger/debug-interface-access/idiaenumframedata-framebyrva.md)|Göreli sanal adres (RVA) ile bir çerçeve döndürür.|
|[IDiaEnumFrameData::frameByVA](../../debugger/debug-interface-access/idiaenumframedata-framebyva.md)|Sanal adrese (VA) göre bir çerçeve döndürür.|

## <a name="remarks"></a>Açıklamalar

## <a name="notes-for-callers"></a>Arayanlar İçin Notlar
Bu arabirimi [IDiaSession:: getEnumTables](../../debugger/debug-interface-access/idiasession-getenumtables.md) yönteminden alın. Ayrıntılar için örneğe bakın.

## <a name="example"></a>Örnek
Bu örnek, arabirimin nasıl alınacağını ( `GetEnumFrameData` işlevin) ve nasıl kullanılacağını ( `ShowFrameData` işlev) gösterir `IDiaEnumFrameData` . İşlevin bir örneği için bkz. [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md) arabirimi `PrintFrameData` .

```C++

      IDiaEnumFrameData* GetEnumFrameData(IDiaSession *pSession)
{
    IDiaEnumFrameData* pUnknown    = NULL;
    REFIID             iid         = __uuidof(IDiaEnumFrameData);
    IDiaEnumTables*    pEnumTables = NULL;
    IDiaTable*         pTable      = NULL;
    ULONG              celt        = 0;

    if (pSession->getEnumTables(&pEnumTables) != S_OK)
    {
        wprintf(L"ERROR - GetTable() getEnumTables\n");
        return NULL;
    }
    while (pEnumTables->Next(1, &pTable, &celt) == S_OK && celt == 1)
    {
        // There is only one table that matches the given iid
        HRESULT hr = pTable->QueryInterface(iid, (void**)&pUnknown);
        pTable->Release();
        if (hr == S_OK)
        {
            break;
        }
    }
    pEnumTables->Release();
    return pUnknown;
}

void ShowFrameData(IDiaSession *pSession)
{
    IDiaEnumFrameData* pEnumFrameData = GetEnumFrameData(pSession);;

    if (pEnumFrameData != NULL)
    {
        IDiaFrameData* pFrameData;
        ULONG celt = 0;

        while(pEnumFrameData->Next(1, &pFrameData, &celt) == S_OK &&
              celt == 1)
        {
            PrintFrameData(pFrameData);
            pFrameData->Release();
        }
        pEnumFrameData->Release();
    }
}
```

## <a name="requirements"></a>Gereksinimler
**Üst bilgi:** Dia2. h

**Kitaplık:** diaguid. lib

**DLL:** msdia80.dll

## <a name="see-also"></a>Ayrıca bkz.
- [Arabirimler (Arabirim Erişimi SDK'sında Hata Ayıklama)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)
- [IDiaSession::getEnumTables](../../debugger/debug-interface-access/idiasession-getenumtables.md)
- [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)
