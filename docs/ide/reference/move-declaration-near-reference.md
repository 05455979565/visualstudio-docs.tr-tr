---
title: Visual Studio'da değişken bildirimi başvurunun yanına taşıma
ms.date: 01/26/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: douge
dev_langs:
- csharp
ms.workload:
- dotnet
ms.openlocfilehash: fc6ee94cbebb1cb35dd524017f22bd8ab3812468
ms.sourcegitcommit: aea5cdb76fbc7eb31d1e5cc3c8d6adb0c743220f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44124963"
---
# <a name="move-declaration-near-reference-refactoring"></a>Başvuru yeniden düzenleme yakın bildirimi taşıma

Bu yeniden düzenleme için geçerlidir:

- C#

**Ne:** yakın değişken bildirimlerini kullanımları için geçiş yapmanıza izin veren.

**Ne zaman:** daha dar bir kapsamda olan değişken bildirimleri sahip.

**Neden:** olduğu, ancak okunabilirlik sorunları veya bilgi gizleme neden olabilir bırakabilir. Okunabilirliği artırmak için yeniden düzenleme için bir fırsat budur.

## <a name="how-to"></a>Nasıl Yapılır Konuları

1. İmlecinizi Değişken bildiriminde yerleştirin.

1. Ardından, aşağıdakilerden birini yapın:

   - **Klavye**
     - Tuşuna **Ctrl**+**.** Tetikleyici için **hızlı Eylemler ve yeniden düzenlemeler** menü ve select **bildirimi başvurunun yanına taşıma** gelen önizleme penceresi açılır.
   - **Fare**
     - Kod sağ tıklayın, **hızlı Eylemler ve yeniden düzenlemeler** menü ve select **bildirimi başvurunun yanına taşıma** gelen önizleme penceresi açılır.

1. Değişiklik ile tamamladığınızda basın **Enter** veya düzeltmeyi menüsünde tıklatın ve değişiklikler uygulanır.

Örnek:

```csharp
// Before
int x;
if (condition)
{
    x = 1;
    Console.WriteLine(x);
}

// Move declaration near reference

// After
if (condition)
{
    int x = 1;
    Console.WriteLine(x);
}
```

## <a name="see-also"></a>Ayrıca bkz.

- [Yeniden Düzenleme](../refactoring-in-visual-studio.md)
- [Değişiklikleri Önizleme](../../ide/preview-changes.md)