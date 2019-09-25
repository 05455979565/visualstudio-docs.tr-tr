---
title: 'CA2003: Fiberleri iş parçacığı olarak görmeyin'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2003
- DoNotTreatFibersAsThreads
helpviewer_keywords:
- CA2003
- DoNotTreatFibersAsThreads
ms.assetid: 15398fb1-f384-4bcc-ad93-00e1c0fa9ddf
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 9f5e4e7eb28207cb37824b23acbbac02b6df380d
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/24/2019
ms.locfileid: "71233145"
---
# <a name="ca2003-do-not-treat-fibers-as-threads"></a>CA2003: Fiberleri iş parçacığı olarak görmeyin

|||
|-|-|
|TypeName|DoNotTreatFibersAsThreads|
|CheckId|CA2003|
|Kategori|Microsoft. güvenilirliği|
|Son değişiklik|Kırılmamış|

## <a name="cause"></a>Sebep

Yönetilen bir iş parçacığı Win32 iş parçacığı olarak kabul ediliyor.

## <a name="rule-description"></a>Kural açıklaması

Yönetilen bir iş parçacığının Win32 iş parçacığı olduğunu varsaymayın; Bu bir fiber. Ortak dil çalışma zamanı (CLR), yönetilen iş parçacıklarını SQL 'e ait gerçek iş parçacıkları bağlamında lifleri görmeyin olarak çalıştırır. Bu iş parçacıkları SQL Server işlemindeki AppDomain 'ler ve hatta veritabanları arasında paylaşılabilir. Yönetilen iş parçacığı yerel depolama alanı çalışır, ancak yönetilmeyen iş parçacığı yerel depolama birimini kullanamaz veya kodunuzun geçerli işletim sistemi iş parçacığında yeniden çalışacağını varsayabilirsiniz. İş parçacığının yerel ayarı gibi ayarları değiştirmeyin. P/Invoke aracılığıyla Createcriticalhandle bölümünü veya CreateMutex 'i çağırmayın, çünkü bir kilidi çağıran iş parçacığının da kiliden çıkması gerekir. Bir kilit giren iş parçacığı fibers kullandığınızda bir kilit çıkmadığından, Win32 kritik bölümleri ve zaman uyumu sağlayıcılar SQL 'de gereksizdir. Yönetilen iş parçacığı yerel depolama alanı ve iş parçacığının geçerli kullanıcı <xref:System.Threading.Thread> arabirimi (UI) kültürü dahil olmak üzere yönetilen bir nesnede durumun büyük bir bölümünü güvenle kullanabilirsiniz. Ancak, programlama modeli nedenleriyle, SQL kullandığınızda bir iş parçacığının geçerli kültürünü değiştiremeyeceksiniz. Bu sınırlama, yeni bir izin ile zorlanır.

## <a name="how-to-fix-violations"></a>İhlalleri çözme

İş parçacıklarının kullanımını inceleyin ve kodunuzu uygun şekilde değiştirin.

## <a name="when-to-suppress-warnings"></a>Uyarıların ne zaman bastırılamıyor

Bu kuralı engellemez.