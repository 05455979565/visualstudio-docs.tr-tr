---
title: Idiadatasource | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaDataSource interface
ms.assetid: 6260ac76-4f9d-4144-ba22-32f8620b32c2
caps.latest.revision: 16
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: a02eb9048c0e9338e6300fc63666af4db535b3ac
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "68198585"
---
# <a name="idiadatasource"></a>IDiaDataSource
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Hata ayıklama sembolleri bir kaynak erişim başlatır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
IDiaDataSource : IUnknown  
```  
  
## <a name="methods-in-vtable-order"></a>Vtable sırayla yöntemleri  
 Aşağıdaki tabloda yöntemlerini gösterilmektedir `IDiaDataSource`.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|[IDiaDataSource::get_lastError](../../debugger/debug-interface-access/idiadatasource-get-lasterror.md)|Son yükleme hatası için dosya adını alır.|  
|[IDiaDataSource::loadDataFromPdb](../../debugger/debug-interface-access/idiadatasource-loaddatafrompdb.md)|Açılır ve hata ayıklama veri kaynağı olarak bir program veritabanı (.pdb) dosyası hazırlar.|  
|[IDiaDataSource::loadAndValidateDataFromPdb](../../debugger/debug-interface-access/idiadatasource-loadandvalidatedatafrompdb.md)|Açılır ve program veritabanı (.pdb) dosyası, sağlanan imza bilgileri eşleştiğini doğrular. .pdb dosyası, hata ayıklama veri kaynağı olarak hazırlar.|  
|[IDiaDataSource::loadDataForExe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)|Açılır ve.exe/.dll dosya ile ilgili hata ayıklama verileri hazırlar.|  
|[IDiaDataSource::loadDataFromIStream](../../debugger/debug-interface-access/idiadatasource-loaddatafromistream.md)|Bir bellek içi veri akışı yoluyla erişilen bir program veritabanı (.pdb) dosyası içinde depolanan hata ayıklama verileri hazırlar.|  
|[IDiaDataSource::openSession](../../debugger/debug-interface-access/idiadatasource-opensession.md)|Semboller sorgulamak için bir oturum açar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Yükleme yöntemlerinden birini çağrısı `IDiaDataSource` sembol kaynak arabirimi açılır. Başarılı bir çağrı [Idiadatasource::opensession](../../debugger/debug-interface-access/idiadatasource-opensession.md) yöntemi döndürür bir [Idiasession](../../debugger/debug-interface-access/idiasession.md) veri kaynağının desteklediği arabirimi. Load yöntemi bir dosya ile ilgili hata verirse sonra [Idiadatasource::get_lasterror](../../debugger/debug-interface-access/idiadatasource-get-lasterror.md) yöntemi dönüş değeri hata ile ilgili dosya adını içerir.  
  
## <a name="notes-for-callers"></a>Arayanlar İçin Notlar  
 Bu arabirim çağırılarak alınır `CoCreateInstance` sınıfı tanımlayıcısına sahip işlev `CLSID_DiaSource` ve arabirim kimliği `IID_IDiaDataSource`. Bu örnek, bu arabirimi nasıl aldıklarına gösterir.  
  
## <a name="example"></a>Örnek  
  
```cpp#  
  
      IDiaDataSource* pSource;  
HRESULT hr = CoCreateInstance(CLSID_DiaSource,  
                              NULL,  
                              CLSCTX_INPROC_SERVER,  
                              IID_IDiaDataSource,  
                              (void**) &pSource);  
if (FAILED(hr))  
{  
    // Report error and exit  
}  
```  
  
## <a name="requirements"></a>Gereksinimler  
 Üst bilgi: dia2.h  
  
 Kitaplık: diaguids.lib  
  
 DLL: msdia80.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Arabirimler (Arabirim Erişimi SDK'sında Hata Ayıklama)](../../debugger/debug-interface-access/interfaces-debug-interface-access-sdk.md)
