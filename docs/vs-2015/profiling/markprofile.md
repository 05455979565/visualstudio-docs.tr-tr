---
title: MarkProfile | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MarkProfile
ms.assetid: 54dac8c8-c8ee-4023-af27-b25466e3a6ec
caps.latest.revision: 15
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c4a5882ea5edd1f8432bf67197ec016c3ce5a81f
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42686108"
---
# <a name="markprofile"></a>MarkProfile
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [MarkProfile](https://docs.microsoft.com/visualstudio/profiling/markprofile).  
  
`MarkProfile` Yöntemi .vsp dosyasında profil işareti ekler. Profil oluşturma için iş parçacığı içeren `MarkProfile` işlevi eklenecek işareti için açık olması gerekir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
PROFILE_COMMAND_STATUS PROFILERAPI MarkProfile( long lMarker );  
```  
  
#### <a name="parameters"></a>Parametreler  
 `lMarker`  
  
 Eklenecek işaretçisi. İşaretin değerinden büyük veya 0 (sıfır) eşit olmalıdır.  
  
## <a name="property-valuereturn-value"></a>Özellik Değeri/Dönüş Değeri  
 İşlevi kullanarak başarısı veya başarısızlığı gösterir **PROFILE_COMMAND_STATUS** sabit listesi. Dönüş değeri aşağıdakilerden biri olabilir:  
  
|Numaralandırıcı|Açıklama|  
|----------------|-----------------|  
|MARK_ERROR_MARKER_RESERVED|Parametresi veya 0'a eşit olan küçük. Bu değerler ayrılmıştır. Açıklama ve işareti kaydedilmez.|  
|MARK_ERROR_MODE_NEVER|HİÇ işlev çağrıldığında profil oluşturma modunda ayarlandı. Açıklama ve işareti kaydedilmez.|  
|MARK_ERROR_MODE_OFF|İşlev çağrıldığında, profil oluşturma modunda OFF olarak ayarlandı. Açıklama ve işareti kaydedilmez.|  
|MARK_ERROR_NO_SUPPORT|Bu bağlamda işareti desteği yok. Açıklama ve işareti kaydedilmez.|  
|MARK_ERROR_OUTOFMEMORY|Bellek olayı kaydetmek kullanılabilir değildi. Açıklama ve işareti kaydedilmez.|  
|MARK_TEXTTOOLONG|Dize en fazla 256 karakter aşıyor. Açıklama dizesi kesilmiş ve işareti ve yorum kaydedilir.|  
|MARK_OK|MARK_OK tamamlandığını bildiren döndürülür.|  
  
## <a name="remarks"></a>Açıklamalar  
 İşareti değeri MarkProfile işlevi içeren iş parçacığı profili, kodu her çalıştığında .vsp dosyasına eklenir. Birden çok kez MarkProfile çağırabilirsiniz.  
  
 Profil işaretleri kapsam içinde geneldir. Örneğin, bir iş parçacığında eklenen bir profili işareti başlangıç veya bitiş .vsp dosyasının içinde herhangi bir iş parçacığı bir veri parçasının işaretlemek için kullanılabilir.  
  
 İşaretler ve açıklama işareti komutu veya API işlevleri (CommentMarkAtProfile, CommentMarkProfile veya MarkProfile) ile eklendiğinde işareti profili işlevi içeren iş parçacığı profil durumu olmalıdır.  
  
> [!IMPORTANT]
>  MarkProfile yöntemi yalnızca izleme profil ile kullanılmalıdır.  
  
## <a name="net-framework-equivalent"></a>.NET Framework Eşdeğeri  
 Microsoft.VisualStudio.Profiler.dll  
  
## <a name="function-information"></a>İşlev bilgisi  
 Başlık: VSPerf.h içinde bildirilen  
  
 İçeri aktarma kitaplığı: VSPerf.lib  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod MarkProfile işlevi gösterir.  
  
```  
void ExerciseMarkProfile()  
{  
    // Declare and initialize variables to pass to   
    // MarkProfile.  The values of these parameters   
    // are assigned based on the needs of the code;  
    // and for the sake of simplicity in this example,   
    // the variables are assigned arbitrary values.  
    int markId = 03;  
  
    // Declare enumeration to hold return value of   
    // call to MarkProfile.  
    PROFILE_COMMAND_STATUS markResult;  
  
    // Variables used to print output.  
    HRESULT hResult;  
    TCHAR tchBuffer[256];  
  
    markResult = MarkProfile(markId);  
  
    // Format and print result.  
    LPCTSTR pszFormat = TEXT("%s %d.\0");  
    TCHAR* pszTxt = TEXT("MarkProfile returned");  
    hResult = StringCchPrintf(tchBuffer, 256, pszFormat,   
        pszTxt, markResult);  
  
#ifdef DEBUG  
    OutputDebugString(tchBuffer);  
#endif  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio Profiler API Başvurusu (yerel)](../profiling/visual-studio-profiler-api-reference-native.md)



