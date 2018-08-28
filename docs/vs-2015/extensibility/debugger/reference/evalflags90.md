---
title: EVALFLAGS90 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- EVALFLAGS90 enumeration
ms.assetid: 64fb0139-8b04-4726-b52c-db2e04d65498
caps.latest.revision: 8
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 3ab44d09b969d36699be2e5ce593d96db4d366af
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42683801"
---
# <a name="evalflags90"></a>EVALFLAGS90
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [EVALFLAGS90](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/evalflags90).  
  
İfade değerlendirme denetim bayrakları için geçerli değerleri listeler. Bu numaralandırma genişletir [EVALFLAGS](../../../extensibility/debugger/reference/evalflags.md) sabit listesi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp#  
enum enum_EVALFLAGS90  
{  
   // VS 8.0 values  
   EVAL90_RETURNVALUE                 = 0x0002,  
   EVAL90_NOSIDEEFFECTS               = 0x0004,  
   EVAL90_ALLOWBPS                    = 0x0008,  
   EVAL90_ALLOWERRORREPORT            = 0x0010,  
   EVAL90_FUNCTION_AS_ADDRESS         = 0x0040,  
   EVAL90_NOFUNCEVAL                  = 0x0080,  
   EVAL90_NOEVENTS                    = 0x1000,  
   EVAL90_DESIGN_TIME_EXPR_EVAL       = 0x2000,  
   EVAL90_ALLOW_IMPLICIT_VARS         = 0x4000,  
  
   // Values added in VS 9.0  
   EVAL90_FORCE_EVALUATION_NOW        = 0x8000  
};  
typedef DWORD EVALFLAGS90;  
```  
  
```csharp  
public enum enum_EVALFLAGS90  
{  
   // VS 8.0 values  
   EVAL90_RETURNVALUE                 = 0x0002,  
   EVAL90_NOSIDEEFFECTS               = 0x0004,  
   EVAL90_ALLOWBPS                    = 0x0008,  
   EVAL90_ALLOWERRORREPORT            = 0x0010,  
   EVAL90_FUNCTION_AS_ADDRESS         = 0x0040,  
   EVAL90_NOFUNCEVAL                  = 0x0080,  
   EVAL90_NOEVENTS                    = 0x1000,  
   EVAL90_DESIGN_TIME_EXPR_EVAL       = 0x2000,  
   EVAL90_ALLOW_IMPLICIT_VARS         = 0x4000,  
  
   // Values added in VS 9.0  
   EVAL90_FORCE_EVALUATION_NOW        = 0x8000  
};  
```  
  
#### <a name="parameters"></a>Parametreler  
 EVAL90_RETURNVALUE  
 Dönüş değeri varsa, değerlendirilecek belirtir.  
  
 EVAL90_NOSIDEEFFECTS  
 Yan etkileri izin verilmeyeceğini belirtir.  
  
 EVAL90_ALLOWBPS  
 Durdurma kesme noktalarında belirtir.  
  
 EVAL90_ALLOWERRORREPORT  
 Konağa izin verilmesi için Raporlama hata belirtir. Internet Explorer'da komut ifade değerlendirmesi için kullanılır.  
  
 EVAL90_FUNCTION_AS_ADDRESS  
 İşlev çağırma yerine adresleri olarak değerlendirilecek işlevleri zorlar.  
  
 EVAL90_NOFUNCEVAL  
 İşlevi, değerlendirilen öğesinden engeller. Örneğin, düşünün `int` ifade belirteci `myExpression(int) + 10`. Bu işlev bir adres, ancak bir değer olarak değil doğru değerlendirilebilir.  
  
 EVAL90_NOEVENTS  
 İfade değerlendirme sırasında meydana gelen olayları oturum hata ayıklama Yöneticisi (SDM) veya IDE gönderilmemelidir belirten bayrak.  
  
 EVAL90_DESIGN_TIME_EXPR_EVAL  
 Tasarım zamanı ifade değerlendirmesi sağlar.  
  
 EVAL90_ALLOW_IMPLICIT_VARS  
 Örtük değişken oluşturmaya izin verir.  
  
 EVAL90_FORCE_EVALUATION_NOW  
 Hemen oluşmasını zorlar değerlendirmesi'ni kullanın. Bu, hizmet kullanıcı isteği gibi bir istek olduğunda yararlıdır.  
  
## <a name="requirements"></a>Gereksinimler  
 Üstbilgi: Msdbg90.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Derleme: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sabit Listeleri](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)
