---
title: 'Nasıl yapılır: program aracılığıyla çalışma sayfalarını gizleme'
ms.date: 02/02/2017
ms.topic: how-to
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- hidden worksheets
- worksheets, hiding
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 83cf1f63a67525dca4cf9dbb5a4916da5d70b4ce
ms.sourcegitcommit: b885f26e015d03eafe7c885040644a52bb071fae
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/30/2020
ms.locfileid: "85547413"
---
# <a name="how-to-programmatically-hide-worksheets"></a>Nasıl yapılır: program aracılığıyla çalışma sayfalarını gizleme
  Çalışma kitabındaki tüm çalışma sayfalarını gösterebilir veya gizleyebilirsiniz. Çalışma sayfasını gizlemek için çalışma sayfası konak öğesini kullanın veya çalışma kitabının sayfalar koleksiyonunu kullanarak çalışma sayfasına erişin.

 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]

## <a name="use-the-worksheet-host-item"></a>Çalışma sayfası konak öğesini kullan
 Belge düzeyi özelleştirmesindeki çalışma sayfası tasarım zamanında eklendiyse, <xref:Microsoft.Office.Tools.Excel.Worksheet.Visible%2A> belirtilen çalışma sayfasını gizlemek için özelliğini kullanın.

### <a name="to-hide-a-worksheet-using-a-worksheet-host-item"></a>Çalışma sayfası konak öğesi kullanarak çalışma sayfasını gizlemek için

1. <xref:Microsoft.Office.Tools.Excel.Worksheet.Visible%2A> `Sheet1` Konak öğesinin özelliğini <xref:Microsoft.Office.Interop.Excel.XlSheetVisibility.xlSheetHidden> numaralandırma değeri olarak ayarlayın.

     [!code-csharp[Trin_VstcoreExcelAutomation#25](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#25)]
     [!code-vb[Trin_VstcoreExcelAutomation#25](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#25)]

## <a name="use-the-sheets-collection-of-the-excel-workbook"></a>Excel çalışma kitabının sayfalar koleksiyonunu kullanın
 Aşağıdaki durumlarda Microsoft Office Excel koleksiyonu aracılığıyla çalışma sayfalarına erişin <xref:Microsoft.Office.Interop.Excel.Sheets> :

- Bir VSTO eklentisinin çalışma sayfasını gizlemek istiyorsunuz.

- Gizlemek istediğiniz çalışma sayfası, çalışma zamanında belge düzeyi özelleştirmesinde oluşturulmuştur.

### <a name="to-hide-a-worksheet-using-the-sheets-collection-of-the-excel-workbook"></a>Excel çalışma kitabının sayfalar koleksiyonunu kullanarak bir çalışma sayfasını gizlemek için

1. <xref:Microsoft.Office.Interop.Excel.Worksheets.Visible%2A>Çalışma sayfasının özelliğini <xref:Microsoft.Office.Interop.Excel.XlSheetVisibility.xlSheetHidden> numaralandırma değerine ayarlayın.

     [!code-csharp[Trin_VstcoreExcelAutomation#26](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#26)]
     [!code-vb[Trin_VstcoreExcelAutomation#26](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#26)]

## <a name="see-also"></a>Ayrıca bkz.
- [Çalışma sayfalarıyla çalışma](../vsto/working-with-worksheets.md)
- [Nasıl yapılır: çalışma kitaplarındaki çalışma sayfalarını program aracılığıyla silme](../vsto/how-to-programmatically-delete-worksheets-from-workbooks.md)
- [Nasıl yapılır: çalışma kitaplarını program aracılığıyla çalışma kitapları Içinde taşıma](../vsto/how-to-programmatically-move-worksheets-within-workbooks.md)
- [Nasıl yapılır: program aracılığıyla çalışma sayfalarını koruma](../vsto/how-to-programmatically-protect-worksheets.md)
- [Konak öğeleri ve konak denetimlerine genel bakış](../vsto/host-items-and-host-controls-overview.md)
- [Office Projelerindeki Nesnelere Genel erişim](../vsto/global-access-to-objects-in-office-projects.md)
