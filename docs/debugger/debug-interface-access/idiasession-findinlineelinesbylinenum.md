---
title: 'IDiaSession:: findInlineeLinesByLinenum | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- C++
ms.assetid: cf32ae7c-a0c8-4800-bc8f-d64fdd15fb06
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: ac7f2299dcfbef53c510c9e9689f92cde2132974
ms.sourcegitcommit: 66f31cc4ce1236e638ab58d2f70d3646206386fa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/27/2020
ms.locfileid: "85465799"
---
# <a name="idiasessionfindinlineelinesbylinenum"></a>IDiaSession::findInlineeLinesByLinenum
Bir istemcinin, belirtilen kaynak dosyasında ve satır numarasında satır içine alınmış, doğrudan veya dolaylı olarak satır numarası bilgilerini yinelemesinden izin veren bir sabit listesi alır.

## <a name="syntax"></a>Söz dizimi

```C++
HRESULT findInlineeLinesByVA ( 
   IDiaSymbol*           compiland,
   IDiaSourceFile*       file,
   DWORD                 linenum,
   DWORD                 column,
   IDiaEnumLineNumbers** ppResult
);
```

#### <a name="parameters"></a>Parametreler
 `compiland`

'ndaki Satır numaralarının aranacağı compiland 'yi temsil eden bir [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md) nesnesi. Bu parametre olamaz `NULL` .

 `file`

'ndaki İçinde arama yapılacak kaynak dosyayı temsil eden bir [IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md) nesnesi. Bu parametre olamaz `NULL` .

 `linenum`

'ndaki Tek tabanlı satır numarasını belirtir.

> [!NOTE]
> Tüm satırları belirtmek için sıfır kullanamazsınız (tüm satırları bulmak için [IDiaSession:: findLines](../../debugger/debug-interface-access/idiasession-findlines.md) metodunu kullanın).

 `column`

'ndaki Sütun numarasını belirtir. Tüm sütunları belirtmek için sıfır kullanın. Sütun, bir satıra bir bayt kaymadır.

 `ppResult`

dışı Alınan satır numaralarının bir listesini içeren bir [IDiaEnumLineNumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md) nesnesi döndürür.

## <a name="return-value"></a>Dönüş Değeri
 Başarılı olursa, döndürür `S_OK` ; Aksi takdirde, bir hata kodu döndürür.

## <a name="see-also"></a>Ayrıca bkz.
- [IDiaSession](../../debugger/debug-interface-access/idiasession.md)
- [IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md)
- [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
- [SymTagEnum Numaralandırması](../../debugger/debug-interface-access/symtagenum.md)
- [IDiaEnumLineNumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md)