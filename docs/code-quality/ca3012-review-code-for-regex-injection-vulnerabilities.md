---
title: 'CA3012: Normal ifade ekleme güvenlik açıkları için inceleme kodu'
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
ms.openlocfilehash: 42808b3961b18a23f594800f9d0782c908c9b1ba
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/24/2019
ms.locfileid: "71237187"
---
# <a name="ca3012-review-code-for-regex-injection-vulnerabilities"></a>CA3012: Normal ifade ekleme güvenlik açıkları için inceleme kodu

|||
|-|-|
|TypeName|Belgeınlist Codeforregexınjectionaçıklardan|
|CheckId|CA3012|
|Kategori|Microsoft.Security|
|Son değişiklik|Kırılmamış|

## <a name="cause"></a>Sebep

Güvenilir olmayan HTTP isteği girişi bir normal ifadeye ulaşır.

## <a name="rule-description"></a>Kural açıklaması

Güvenilmeyen girişle çalışırken, en az sayıda Regex ekleme saldırısı olması gerekir. Saldırgan, normal ifadeyi kötü amaçlı olarak değiştirmek, Regex istenmeden sonuçlarla eşleştirmek için veya Regex aşırı CPU tüketmek için bir hizmet reddi saldırısından kaynaklanan Regex ekleme işlemini kullanabilir.

Bu kural, bir normal ifadeye ulaşan HTTP isteklerinden girdi bulmaya çalışır.

> [!NOTE]
> Bu kural derlemeler genelinde verileri izleyemez. Örneğin, bir derleme HTTP istek girişini okur ve sonra onu normal ifade oluşturan başka bir derlemeye geçirirse, bu kural bir uyarı oluşturmaz.

> [!NOTE]
> Bu kuralın, yöntem çağrılarında veri akışını ne kadar analiz edip bu kurala ilişkin yapılandırılabilir bir sınır vardır. Bir EditorConfig dosyasında sınırı yapılandırma hakkında bilgi için bkz. [çözümleyici yapılandırması](https://github.com/dotnet/roslyn-analyzers/blob/master/docs/Analyzer%20Configuration.md#dataflow-analysis) .

## <a name="how-to-fix-violations"></a>İhlalleri çözme

Regex içindeki bazı azaltmalar şunları içerir:

- Normal ifadeler kullanılırken her zaman bir [eşleşme zaman aşımı](/dotnet/standard/base-types/best-practices#use-time-out-values) kullanın.
- Kullanıcı girişini temel alan normal ifadeler kullanmaktan kaçının.
- Ya da başka bir yöntem çağırarak <xref:System.Text.RegularExpressions.Regex.Escape%2A?displayProperty=fullName> Kullanıcı girişinden özel karakterleri kaçış.
- Kullanıcı girişinden yalnızca özel olmayan karakterlere izin ver.

## <a name="when-to-suppress-warnings"></a>Uyarıların ne zaman bastırılamıyor

[Eşleştirme zaman aşımı](/dotnet/standard/base-types/best-practices#use-time-out-values) kullandığınızı ve Kullanıcı girişinin özel karakterlerden muaf olduğunu biliyorsanız, bu uyarıyı bastırmak çok normaldir.

## <a name="pseudo-code-examples"></a>Sözde kod örnekleri

### <a name="violation"></a>Edildiği

```csharp
using System;
using System.Text.RegularExpressions;

public partial class WebForm : System.Web.UI.Page
{
    public string SearchableText { get; set; }

    protected void Page_Load(object sender, EventArgs e)
    {
        string findTerm = Request.Form["findTerm"];
        Match m = Regex.Match(SearchableText, "^term=" + findTerm);
    }
}
```

```vb
Imports System
Imports System.Text.RegularExpressions

Public Partial Class WebForm
    Inherits System.Web.UI.Page

    Public Property SearchableText As String

    Protected Sub Page_Load(sender As Object, e As EventArgs)
        Dim findTerm As String = Request.Form("findTerm")
        Dim m As Match = Regex.Match(SearchableText, "^term=" + findTerm)
    End Sub
End Class
```
