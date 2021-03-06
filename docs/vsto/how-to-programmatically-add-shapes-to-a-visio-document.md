---
title: 'Nasıl yapılır: Visio belgesine program aracılığıyla şekiller ekleme'
ms.date: 02/02/2017
ms.topic: how-to
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Visio [Office development in Visual Studio], adding Visio shapes
- shapes [Office development in Visual Studio], adding Visio shapes
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: adde20bff07b54a7fb5777bd9e03a995b4fbd7df
ms.sourcegitcommit: b885f26e015d03eafe7c885040644a52bb071fae
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/30/2020
ms.locfileid: "85538066"
---
# <a name="how-to-programmatically-add-shapes-to-a-visio-document"></a>Nasıl yapılır: Visio belgesine program aracılığıyla şekiller ekleme
  Kalıptan ana öğe alarak ve şekilleri etkin sayfada bırakarak bir Microsoft Office Visio belgesine şekil ekleyebilirsiniz.

 Daha fazla bilgi için,Microsoft.Office.Interop.Visio.Documtları için VBA başvuru belgelerine bakın [. Add](/office/vba/api/Visio.Documents.Add) yöntemi, [Microsoft. Office. Interop. Visio. Application. ActivePage](/office/vba/api/Visio.Application.ActivePage) özelliği ve [Microsoft. Office. Interop. Visio. Page. Drop](/office/vba/api/Visio.Page.Drop) yöntemi.

## <a name="add-shapes-to-a-visio-document"></a>Visio belgesine şekil ekleme

### <a name="to-add-shapes-to-a-visio-document"></a>Visio belgesine şekil eklemek için

- Bir belge etkinken Documents. Master koleksiyonundan ana şablonları alın ve şekilleri etkin belgeye bırakın. Bir ana şablonu dizin veya ana adı kullanarak alabilirsiniz.

     Aşağıdaki kod örneği, boş bir Visio belgesi oluşturur ve sonra **temel şekiller** kalıbı yerleştirilen ile açar. Daha sonra kod, birkaç şekli alır ve etkin sayfada bırakır.

     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#13](../vsto/codesnippet/CSharp/trin_vstcorevisioautomationaddin/ThisAddIn.cs#13)]
     [!code-vb[Trin_VstcoreVisioAutomationAddIn#13](../vsto/codesnippet/VisualBasic/trin_vstcorevisioautomationaddin/ThisAddIn.vb#13)]

## <a name="see-also"></a>Ayrıca bkz.
- [Visio çözümleri](../vsto/visio-solutions.md)
- [Visio nesne modeline genel bakış](../vsto/visio-object-model-overview.md)
- [Visio şekilleri ile çalışma](../vsto/working-with-visio-shapes.md)
- [Nasıl yapılır: Visio belgesine program aracılığıyla şekilleri kopyalama ve yapıştırma](../vsto/how-to-programmatically-copy-and-paste-shapes-in-a-visio-document.md)
