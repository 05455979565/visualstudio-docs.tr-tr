---
title: Bu ilgili metot, aşağıdaki varsayılan ekleme, güncelleştirme ve silme metotları için yedek bir metottur
ms.date: 11/04/2016
ms.topic: error-reference
ms.assetid: 62afa6da-97cf-48b9-8de3-33e4d72a0377
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- data-storage
ms.openlocfilehash: 252303c4933501dd3a4672329d66ef4910238a08
ms.sourcegitcommit: b885f26e015d03eafe7c885040644a52bb071fae
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/30/2020
ms.locfileid: "85535258"
---
# <a name="this-related-method-is-the-backing-method-for-the-following-default-insert-update-or-delete-methods"></a>Bu ilgili metot, aşağıdaki varsayılan ekleme, güncelleştirme ve silme metotları için yedek bir metottur

Bu ilgili yöntem, aşağıdaki varsayılan `Insert` , veya yöntemleri için yedekleme yöntemidir `Update` `Delete` . Silinirse, bu yöntemler de silinir. Devam etmek istiyor musunuz?

Seçilen `DataContext` Yöntem `Insert` , `Update` o anda `Delete` **o/R tasarımcısında**varlık sınıflarından biri için, veya yöntemlerinden biri olarak kullanılmaktadır. Seçili yöntemi silmek, bu yöntemi kullanan varlık sınıfının bir güncelleştirme sırasında INSERT, Update veya Delete işlemini gerçekleştirmek için varsayılan çalışma zamanı davranışına geri dönmesi için yol açar.

## <a name="selected-method-options"></a>Seçili Yöntem seçenekleri

- Seçili yöntemi silmek için, varlık sınıfının çalışma zamanı güncelleştirmelerini kullanmasına neden olan **Evet**' e tıklayın.

   Seçilen yöntem silinir ve güncelleştirme davranışını geçersiz kılmak için bu yöntemi kullanan sınıflar varsayılan LINQ to SQL çalışma zamanı davranışı kullanılarak döndürülür.

- İleti kutusunu kapatmak için, seçili yöntemi değiştirmeden bırakarak **Hayır**' a tıklayın.

   İleti kutusu kapanır ve hiçbir değişiklik yapılmaz.

## <a name="see-also"></a>Ayrıca bkz.

- [Visual Studio 'da LINQ to SQL araçları](../data-tools/linq-to-sql-tools-in-visual-studio2.md)