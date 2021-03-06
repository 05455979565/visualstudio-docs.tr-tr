---
title: SccHistory işlevi | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- SccHistory
helpviewer_keywords:
- SccHistory function
ms.assetid: a636d9d3-47c1-4b48-ac6b-bcfde19d6cf9
caps.latest.revision: 17
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 8df85c03201e46768c43fb64cc41b7fa081eb91a
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "63446819"
---
# <a name="scchistory-function"></a>SccHistory İşlevi
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu işlev, belirtilen dosyaları geçmişini görüntüler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
SCCRTN SccHistory(  
   LPVOID    pvContext,  
   HWND      hWnd,  
   LONG      nFiles,  
   LPCSTR*   lpFileNames,  
   LONG      fOptions,  
   LPCMDOPTS pvOptions  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pvContext`  
 [in] Kaynak Denetimi Eklentisi bağlam yapısı.  
  
 `hWnd`  
 [in] Kaynak Denetimi Eklentisi sağladığı herhangi bir iletişim kutusu için bir üst öğe olarak kullanabileceğiniz IDE penceresi için bir tanıtıcı.  
  
 `nFiles`  
 [in] Belirtilen dosya sayısı `lpFileName` dizisi.  
  
 `lpFileName`  
 [in] Dosyaların tam adları dizisi.  
  
 `fOptions`  
 [in] Komut bayrakları (şu anda değil kullanılır).  
  
 `pvOptions`  
 [in] Kaynak denetimi fişi özel seçenekleri.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Kaynak Denetimi Eklentisi uygulanması bu işlev, aşağıdaki değerlerden birini döndürmesi beklenir:  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|SCC_OK|Sürüm Geçmişi başarıyla alındı.|  
|SCC_I_RELOADFILE|Diskteki dosyanın gerçekten değişiklik geçmişini getirilirken (örneğin, eski bir sürümünü alarak), kaynak denetim sistemi IDE bu dosyayı yeniden yüklemek için.|  
|SCC_E_FILENOTCONTROLLED|Dosya kaynak denetimi altında değil.|  
|SCC_E_OPNOTSUPPORTED|Kaynak denetim sistemi bu işlemi desteklemiyor.|  
|SCC_E_NOTAUTHORIZED|Kullanıcı bu işlemi gerçekleştirmek için izin verilmiyor.|  
|SCC_E_ACCESSFAILURE|Kaynak denetim sistemi, ağ veya çakışma sorunları nedeniyle muhtemelen erişilirken sorun oluştu. Bir yeniden deneme önerilir.|  
|SCC_E_PROJNOTOPEN|Proje değiştirilmediğinden açılır.|  
|SCC_E_NONSPECIFICERROR|Belirli olmayan hata oluştu. Dosya geçmişi alınamadı.|  
  
## <a name="remarks"></a>Açıklamalar  
 Kaynak denetimi eklentisi her dosyanın geçmişini görüntülemek için kendi iletişim kutusunu görüntüleyebilirsiniz kullanarak `hWnd` olarak üst pencere. Alternatif olarak, isteğe bağlı geri çağırma çıktıyı işlevi sağlanan için [SccOpenProject](../extensibility/sccopenproject-function.md) , destekleniyorsa, kullanılabilir.  
  
 Belirli koşullar altında bu çağrı yürütülmesi sırasında incelenmekte olan dosyayı değiştirmek olduğunu unutmayın. Örneğin, [!INCLUDE[vsvss](../includes/vsvss-md.md)] history komutu kullanıcı dosyanın eski bir sürümünü almak için bir fırsat sunar. Böyle bir durumda, kaynak denetimi eklentisi döndürür `SCC_I_RELOAD` dosyayı yeniden yüklemeniz gerekir IDE uyarır.  
  
> [!NOTE]
> Kaynak denetimi eklentisi dosyaları dizisi için bu işlevi desteklemiyorsa, yalnızca ilk dosyası için dosya geçmişi görüntülenebilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaynak Denetimi Eklentisi API işlevleri](../extensibility/source-control-plug-in-api-functions.md)   
 [SccOpenProject](../extensibility/sccopenproject-function.md)
