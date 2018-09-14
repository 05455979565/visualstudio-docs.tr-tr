---
title: 'CA2124: Savunmasız sonunda yan tümcelerini dış deneme içine sarmalayın'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-code-analysis
ms.topic: reference
f1_keywords:
- CA2124
- WrapVulnerableFinallyClausesInOuterTry
helpviewer_keywords:
- CA2124
- WrapVulnerableFinallyClausesInOuterTry
ms.assetid: 82efd224-9e60-4b88-a0f5-dfabcc49a254
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 738c214e845cb962bc6c28aa63806dee2858c295
ms.sourcegitcommit: 568bb0b944d16cfe1af624879fa3d3594d020187
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/13/2018
ms.locfileid: "45551246"
---
# <a name="ca2124-wrap-vulnerable-finally-clauses-in-outer-try"></a>CA2124: Savunmasız sonunda yan tümcelerini dış deneme içine sarmalayın

|||
|-|-|
|TypeName|WrapVulnerableFinallyClausesInOuterTry|
|CheckId|CA2124|
|Kategori|Microsoft.Security|
|Yeni Değişiklik|Bozucu olmayan|

## <a name="cause"></a>Sebep
 1.0 ve 1.1 sürümlerinde [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)], bir ortak veya korumalı yöntem içerir bir `try` / `catch` / `finally` blok. `finally` Blok güvenlik durumunu sıfırlamak için görünür ve sınırlanan değil bir `finally` blok.

## <a name="rule-description"></a>Kural açıklaması
 Bu kural bulur `try` / `finally` 1.0 ve 1.1 sürümlerini hedefleyen kodda engeller [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] olabilecek kötü amaçlı bir özel durum filtreleri çağrı yığınında mevcut açıktır. Kimliğe bürünme gibi hassas işlemler try bloğunda oluşur ve bir özel durum, filtre önce yürütebilir `finally` blok. Kimliğe bürünme örneği için bu filtrenin bürünülen kullanıcıyla yürütmesine anlamına gelir. Şu anda yalnızca Visual Basic'te implementable filtrelerdir.

> [!NOTE]
> 2.0 ve sonraki sürümlerinde [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)], çalışma zamanı otomatik olarak koruyan bir `try` / `catch` /  `finally` sıfırlama doğrudan yöntemi içinde ortaya çıkarsa kötü amaçlı bir özel durum filtrelerden engelleme, özel durum bloğu içerir.

## <a name="how-to-fix-violations"></a>İhlaller nasıl düzeltilir?
 Sarmalanmış halden yerleştirin `try` / `finally` bir dış try bloğu içinde. Aşağıdaki ikinci örneğe bakın. Bu zorlar `finally` filtre kodundan önce yürütülecek.

## <a name="when-to-suppress-warnings"></a>Uyarılar bastırıldığında
 Bu kuraldan uyarıyı bastırmayın.

## <a name="pseudo-code-example"></a>Sözde kod örneği

### <a name="description"></a>Açıklama

Bu kural tarafından algılanan düzeni aşağıdaki sözde kod göstermektedir.

```csharp
try {
   // Do some work.
   Impersonator imp = new Impersonator("John Doe");
   imp.AddToCreditCardBalance(100);
}
finally {
   // Reset security state.
   imp.Revert();
}
```

Aşağıdaki sözde kod kodunuzu koruyun ve bu kural karşılamak için kullanabileceğiniz desenini gösterir.

```csharp
try {
     try {
        // Do some work.
     }
     finally {
        // Reset security state.
     }
}
catch()
{
    throw;
}
```