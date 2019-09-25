---
title: 'CA3010: XAML ekleme güvenlik açıkları için inceleme kodu'
ms.date: 04/03/2019
ms.topic: reference
author: dotpaul
ms.author: paulming
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: efd30a783f534d76f7f7f3fa18fd181dbe7e98a1
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/24/2019
ms.locfileid: "71237234"
---
# <a name="ca3010-review-code-for-xaml-injection-vulnerabilities"></a>CA3010: XAML ekleme güvenlik açıkları için inceleme kodu

|||
|-|-|
|TypeName|ReviewCodeForXamlInjectionVulnerabilities|
|CheckId|CA3010|
|Kategori|Microsoft.Security|
|Son değişiklik|Kırılmamış|

## <a name="cause"></a>Sebep

Güvenilir olmayan http isteği girişi bir <xref:System.Windows.Markup.XamlReader?displayProperty=nameWithType> Load metoduna ulaşır.

## <a name="rule-description"></a>Kural açıklaması

Güvenilmeyen girişle çalışırken, XAML ekleme saldırılarına karşı daha az olun. XAML doğrudan nesne örneğini oluşturma ve yürütmeyi temsil eden bir biçimlendirme dilidir. Bu, XAML 'de oluşturulan öğelerin sistem kaynaklarıyla etkileşime girebileceği anlamına gelir (örneğin, ağ erişimi ve dosya sistemi GÇ). Bir saldırgan bir <xref:System.Windows.Markup.XamlReader?displayProperty=nameWithType> Load yöntemi çağrısının girişini denet,, saldırgan kodu yürütebilir.

Bu kural, <xref:System.Windows.Markup.XamlReader?displayProperty=nameWithType> Load yöntemine ulaşan http isteklerinden girdi bulmaya çalışır.

> [!NOTE]
> Bu kural derlemeler genelinde verileri izleyemez. Örneğin, bir derleme HTTP istek girişini okuyup XAML yükleyen başka bir derlemeye geçerse, bu kural bir uyarı oluşturmaz.

> [!NOTE]
> Bu kuralın, yöntem çağrılarında veri akışını ne kadar analiz edip bu kurala ilişkin yapılandırılabilir bir sınır vardır. Bir EditorConfig dosyasında sınırı yapılandırma hakkında bilgi için bkz. [çözümleyici yapılandırması](https://github.com/dotnet/roslyn-analyzers/blob/master/docs/Analyzer%20Configuration.md#dataflow-analysis) .

## <a name="how-to-fix-violations"></a>İhlalleri çözme

Güvenilmeyen XAML yüklemeyin.

## <a name="when-to-suppress-warnings"></a>Uyarıların ne zaman bastırılamıyor

Bu kuraldan gelen uyarıları göstermez.

## <a name="pseudo-code-examples"></a>Sözde kod örnekleri

### <a name="violation"></a>Edildiği

```csharp
using System;
using System.IO;

public partial class WebForm : System.Web.UI.Page
{
    protected void Page_Load(object sender, EventArgs e)
    {
        string input = Request.Form["in"];
        byte[] bytes = Convert.FromBase64String(input);
        MemoryStream ms = new MemoryStream(bytes);
        System.Windows.Markup.XamlReader.Load(ms);
    }
}
```

```vb
Imports System
Imports System.IO

Public Partial Class WebForm
    Inherits System.Web.UI.Page

    Protected Sub Page_Load(sender As Object, e As EventArgs)
        Dim input As String = Request.Form("in")
        Dim bytes As Byte() = Convert.FromBase64String(input)
        Dim ms As MemoryStream = New MemoryStream(bytes)
        System.Windows.Markup.XamlReader.Load(ms)
    End Sub
End Class
```
