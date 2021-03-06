---
title: "&lt;Belge&gt; öğesi (Visual Studio'da Office Geliştirme)"
titleSuffix: ''
ms.custom: seodec18
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- document element
- application manifests [Office development in Visual Studio], <document> element
- <document> element
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 36d822d60d1a28d48f660f6d358b75bf4a913048
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "63000030"
---
# <a name="ltdocumentgt-element-office-development-in-visual-studio"></a>&lt;Belge&gt; öğesi (Visual Studio'da Office Geliştirme)
  `document` Öğesinin `vstov4` ad alanı için belge düzeyi özelleştirmeleri özelleştirme özel bilgileri depolar.

## <a name="syntax"></a>Sözdizimi

```xml
<document solutionId />
```

## <a name="elements-and-attributes"></a>Öğeler ve öznitelikler
 Yalnızca belge düzeyinde özelleştirmeler için gereklidir. `document` Öğe konusu `vstov4` ad alanı. `document` Öğesinde şu öznitelikler bulunur.

|Öznitelik|Açıklama|
|---------------|-----------------|
|`solutionId`|Gerekli. Bir belge düzeyi çözümü benzersiz olarak tanımlanabilmesi için Office çalışma zamanı için Visual Studio Araçları tarafından kullanılan GUID. Bu değer _AssemblyLocation özel belge özelliği olarak depolanır. Daha fazla bilgi için [özel belge özelliklerine genel bakış](../vsto/custom-document-properties-overview.md).|

 `document` alt öğe yok.

## <a name="document-level-customization-example"></a>Belge düzeyi özelleştirmesi örneği

### <a name="description"></a>Açıklama
 Aşağıdaki kod örneğinde gösterilmiştir `document` kullanılarak dağıtılan bir belge düzeyinde Office çözüm öğesinde [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)]. Bu kod örneği, sağlanan daha büyük bir örneğin parçasıdır [Office çözümleri için uygulama bildirimleri](../vsto/application-manifests-for-office-solutions.md).

### <a name="code"></a>Kod

```xml
<vstov4:document
  solutionId="73e" />
```

## <a name="see-also"></a>Ayrıca bkz.

- [Office çözümleri için uygulama bildirimleri](../vsto/application-manifests-for-office-solutions.md)
- [Office çözümleri için dağıtım bildirimleri](../vsto/deployment-manifests-for-office-solutions.md)
- [ClickOnce Uygulama bildirimi](../deployment/clickonce-application-manifest.md)