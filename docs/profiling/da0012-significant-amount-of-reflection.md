---
title: DA0012-önemli miktarda yansıma | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vs.performance.rules.DAReflection
- vs.performance.12
- vs.performance.rules.DA0012
- vs.performance.DA0011
ms.assetid: c92a1d76-21fa-426e-8b1b-a3c08e9bcbca
author: mikejo5000
ms.author: mikejo
manager: jillfra
monikerRange: vs-2017
ms.workload:
- multiple
ms.openlocfilehash: df8b9c80b3d3b12cb556947a7ca77b3141fb853d
ms.sourcegitcommit: b885f26e015d03eafe7c885040644a52bb071fae
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/30/2020
ms.locfileid: "85520647"
---
# <a name="da0012-significant-amount-of-reflection"></a>DA0012: Önemli miktarda Yansıma

|Öğe|Değer|
|-|-|
|Kural kimliği|DA0012|
|Kategori|.NET Framework kullanımı|
|Profil oluşturma yöntemleri|Örnekleme|
|İleti|Yansımayı aşırı kullanıyor olabilirsiniz. Bu, pahalı bir işlemdir.|
|Kural türü|Uyarı|

## <a name="cause"></a>Nedeni
 InvokeMember ve GetMember gibi System. Reflection yöntemlerine veya MemberInvoke gibi Yöntem türlerine yapılan çağrılar, profil oluşturma verilerinin önemli bir orandır. Mümkün olduğunda, bu yöntemleri bağımlı derlemelerin yöntemlerine erken bağlama ile değiştirmeyi göz önünde bulundurun.

## <a name="rule-description"></a>Kural açıklaması
 Yansıma, uygulamanızın bağımlı bir çalışma zamanı derlemesine geç bağlamayı gerçekleştirmek veya çalışma zamanında yeni türler oluşturmak ve dinamik olarak yürütmek için kullanılabilecek .NET Framework esnek bir olandır. Ancak, bu teknikler sık kullanılıyorsa veya sıkı Döngülerde çağrılırsa performansı düşürebilir.

 Daha fazla bilgi için, MSDN 'deki Microsoft desenleri ve uygulamalar kitaplığı 'nın .NET uygulama performansını ve ölçeklenebilirlik birimini geliştirme bölümünde yönetilen kod performansını artırma başlıklı Bölüm 5 ' in [yansıma ve geç bağlama](/previous-versions/msp-n-p/ff647790(v=pandp.10)#reflection-and-late-binding) bölümüne bakın.

## <a name="how-to-investigate-a-warning"></a>Uyarı araştırma
 Profil oluşturma verilerinin [Işlev ayrıntıları görünümüne](../profiling/function-details-view.md) gitmek Için hatalar Listesi penceresinde iletiye çift tıklayın. .NET yansıma API 'lerinin en sık kullanımını yapan programın bölümlerini bulmak için System. Type veya System. Reflection yönteminin çağırma işlevlerini inceleyin. Meta veri döndüren yöntemlerin kullanmaktan kaçının. Uygulamanızın performansı önemli olduğunda, geç bağlamayı kullanmaktan ve türleri dinamik olarak çalışma zamanında oluşturmaktan kaçınabilirsiniz.
