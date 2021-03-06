---
title: Kod analizini kullanarak yönetilen kod kalitesini analiz etme | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
helpviewer_keywords:
- code analysis,managed code
- managed code analyis
ms.assetid: 68510a55-da51-4381-81a5-0feba76b8b4f
caps.latest.revision: 26
author: jillre
ms.author: jillfra
manager: wpickett
ms.openlocfilehash: 0d5f0646f26226e9895414db512681e0a7a71faa
ms.sourcegitcommit: a8e8f4bd5d508da34bbe9f2d4d9fa94da0539de0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/19/2019
ms.locfileid: "72671111"
---
# <a name="analyzing-managed-code-quality-by-using-code-analysis"></a>Kod Çözümlemesi ile Yönetilen Kod Kalitesini Çözümleme
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Kodunuzda güvenli olmayan veri erişimi, kullanım ihlalleri ve tasarım sorunları gibi olası sorunları öğrenmek için Visual Studio 'daki kod çözümleme araçları ' nı kullanabilirsiniz. Kod Analizi .NET Framework, yerel (C ve C++) ve veritabanı uygulamalarında kullanılabilir. Yönetilen kod için kod analizi, belirli kodlama sorunlarını hedefleyen *kural kümelerindeki* kuralları düzenler.

## <a name="common-tasks"></a>Ortak Görevler

|Ortak Görevler|Destekleyici İçerik|
|------------------|------------------------|
|**Uygulamalı alıştırma:** Basit bir .NET Framework uygulamasındaki kusurları düzelterek kod analizinin temellerini öğrenin.|-   [Izlenecek yol: kod kusurları Için yönetilen kodu analiz etme](../code-quality/walkthrough-analyzing-managed-code-for-code-defects.md)|
|**Bir proje için kod analizini yapılandırın:** Yönetilen kod kuralları, güvenlik ve tasarım gibi belirli alanlara yönelik kural kümeleri halinde düzenlenir. Microsoft standart kural kümelerinden birini kullanabilir veya kendi kendinizinkini oluşturabilirsiniz.|[yönetilen koda genel bakış için -    kod analizi](../code-quality/code-analysis-for-managed-code-overview.md)<br />[kod analizi kurallarını gruplandırmak Için kural kümeleri kullanma](../code-quality/using-rule-sets-to-group-code-analysis-rules.md) -   <br />[SuppressMessage özniteliğini kullanarak uyarıları -    gösterme](../code-quality/suppress-warnings-by-using-the-suppressmessage-attribute.md)|
|**Kod analizini Çalıştır:** Kod analizini, proje yapılandırması her oluşturulduğunda otomatik olarak çalışacak şekilde belirtebilir ve Kod analizini bir projede el ile çalıştırabilirsiniz.|-   [nasıl yapılır: Otomatik Kod analizini etkinleştirme ve devre dışı bırakma](../code-quality/how-to-enable-and-disable-automatic-code-analysis-for-managed-code.md)<br />-   [nasıl yapılır: Kod analizini El Ile çalıştırma](../code-quality/how-to-run-code-analysis-manually-for-managed-code.md)|
|**Kod analizi sonuçlarını çözümle:** Kod Analizi uyarıları ve hataları, Kod Analizi penceresinde listelenir. Uyarı hakkındaki ek bilgileri göstermek ve kuralı tetikleyen kaynak kodu satırını göstermek ve vurgulamak için bir uyarı veya hata başlığı seçebilirsiniz. MSDN kitaplığında, sorunun nasıl çözümlenme hakkında bilgi ve örnek içeren ayrıntılı bilgileri göstermek için uyarı kimliğini seçebilirsiniz.|-   [nasıl yapılır: yönetilen kod kusurlarını görüntüleme](../code-quality/how-to-view-managed-code-defects.md)<br />[yönetilen kod uyarıları Için kod analizini](../code-quality/code-analysis-for-managed-code-warnings.md) -   <br />[CheckId 'ye göre -    uyarıları](../code-quality/code-analysis-warnings-for-managed-code-by-checkid.md)<br />-   [Anonim yöntemler ve kod analizi](../code-quality/anonymous-methods-and-code-analysis.md)|
|**Kod analizini geliştirme yaşam döngüsüyle tümleştirin:** @No__t_1 içindeki iade ilkeleri, tüm kod iadelerinin ortak bir kod analizi standartları kümesini karşıladığından emin olmak için geliştirme ekiplerini etkinleştirin. Kod çözümleme kuralı ihlali için bir iş öğesi oluşturmak, Hata Listesi penceresinde gerçekleştirebileceğiniz basit bir yordamdır.|[Takım projesi Iade Ilkeleriyle kod kalitesini -    geliştirme](../code-quality/enhancing-code-quality-with-team-project-check-in-policies.md)<br />-   [nasıl yapılır: takım projesi Iade Ilkesiyle kod proje kural kümelerini senkronize etme](../code-quality/how-to-synchronize-code-project-rule-sets-with-team-project-check-in-policy.md)<br />-   [nasıl yapılır: yönetilen bir kod hatası Için Iş öğesi oluşturma](../code-quality/how-to-create-a-work-item-for-a-managed-code-defect.md)|
