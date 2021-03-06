---
title: Etki alanı Ilişkilerinin özellikleri | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: reference
helpviewer_keywords:
- Domain-Specific Language, domain relationships
ms.assetid: 9ccb3dc2-b80c-4585-932f-3c5f87bafbcd
caps.latest.revision: 22
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 95372b2bc7537e017a4eeca9b414ef054d82046d
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72671547"
---
# <a name="properties-of-domain-relationships"></a>Etki Alanı İlişkilerinin Özellikleri
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Aşağıdaki tabloda yer alan Özellikler bir etki alanı ilişkisiyle ilişkilendirilir. Etki alanı ilişkileri hakkında daha fazla bilgi için bkz. [modelleri, sınıfları ve Ilişkileri anlama](../modeling/understanding-models-classes-and-relationships.md). Bu özelliklerin nasıl kullanılacağı hakkında daha fazla bilgi için bkz. [etki alanına özgü dili özelleştirme ve genişletme](../modeling/customizing-and-extending-a-domain-specific-language.md).

|Özellik|Açıklama|Varsayılan|
|--------------|-----------------|-------------|
|Erişim değiştiricisi|Etki alanı ilişkisine erişim düzeyi (`public` veya `internal`).|`public`|
|Özel Öznitelikler|Etki alanı ilişkisinden oluşturulan kaynak kodu sınıfına öznitelikler eklemek için kullanılır.|\<none >|
|Double türevi üretir|@No__t_0, hem temel sınıf hem de kısmi bir sınıf (geçersiz kılmaları özelleştirmeyi desteklemek için) oluşturulur. Daha fazla bilgi için bkz. [oluşturulan sınıfları geçersiz kılma ve genişletme](../modeling/overriding-and-extending-the-generated-classes.md).|`False`|
|Özel Oluşturucusu vardır|@No__t_0, kaynak kodda özel bir oluşturucunun sağlandığını gösterir. Daha fazla bilgi için bkz. [oluşturulan sınıfları geçersiz kılma ve genişletme](../modeling/overriding-and-extending-the-generated-classes.md).|`False`|
|Devralma değiştiricisi|Etki alanı ilişkisinden oluşturulan kaynak kodu sınıfının devralım türünü açıklar (`none`, `abstract` veya `sealed`).|\<none >|
|Yinelemelere izin verir|@No__t_0, aynı iki öğe arasında etki alanı ilişkisinin Yinelenen bağlantıları oluşturulabilir.|`False`|
|Temel Ilişkiler|Etki alanı ilişkisi türetildiyse, etki alanı ilişkisinin temel ilişkisi.|\<none >|
|Ekleniyor|@No__t_0, etki alanı ilişkisi bir katıştırma ilişkisidir. @No__t_0, ilişki bir başvuru ilişkisidir.|\<both >|
|Name|Etki alanı ilişkisinin adı.|Geçerli ad|
|Ad Alanı|Etki alanı ilişkisiyle bağlantılı olan ad alanı.|Geçerli ad alanı|
|Notlar|Etki alanı ilişkisiyle ilişkili resmi olmayan notlar.|\<none >|
|Açıklama|Kodu belgelemek için kullanılan açıklama ve oluşturulan tasarımcının Kullanıcı arabiriminde kullanılır.|\<none >|
|Görünen ad|Etki alanı ilişkisi için oluşturulan tasarımcıda görüntülenen ad.|\<none >|
|Help anahtar sözcüğü|Etki alanı ilişkisi için F1 yardımını dizine eklemek üzere kullanılan isteğe bağlı anahtar sözcük.|\<none >|

## <a name="see-also"></a>Ayrıca Bkz.
 [Alana Özgü Dil Araçları sözlüğü](https://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)
