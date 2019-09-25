---
title: 'CA3007: Açık yeniden yönlendirme güvenlik açıkları için inceleme kodu'
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
ms.openlocfilehash: 0226c0e2e66a6543b81cd8ee674a743766b65f3e
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/24/2019
ms.locfileid: "71237270"
---
# <a name="ca3007-review-code-for-open-redirect-vulnerabilities"></a>CA3007: Açık yeniden yönlendirme güvenlik açıkları için inceleme kodu

|||
|-|-|
|TypeName|Belgekodu Koduforopenredirectgüvenlik açıkları|
|CheckId|CA3007|
|Kategori|Microsoft.Security|
|Son değişiklik|Kırılmamış|

## <a name="cause"></a>Sebep

Güvenilir olmayan HTTP isteği girişi bir HTTP yanıtı yönlendirmeye ulaşır.

## <a name="rule-description"></a>Kural açıklaması

Güvenilmeyen girişle çalışırken, açık yeniden yönlendirme güvenlik açıklarına karşı bir sorun yaşının. Saldırgan, meşru bir URL 'nin görünümüne izin vermek için Web sitesini kullanmak üzere açık bir yeniden yönlendirme güvenlik açığıyla yararlanabilir, ancak şüphelenmeyecek bir ziyaretçi kimlik avına veya başka bir kötü amaçlı Web sayfasına yönlendirebilir.

Bu kural http isteklerinden gelen ve HTTP yeniden yönlendirme URL 'sine ulaşan giriş bulmaya çalışır.

> [!NOTE]
> Bu kural derlemeler genelinde verileri izleyemez. Örneğin, bir derleme HTTP istek girişini okuduğunda ve bunu bir HTTP yeniden yönlendirme ile yanıt veren başka bir derlemeye geçirirse, bu kural bir uyarı oluşturmaz.

> [!NOTE]
> Bu kuralın, yöntem çağrılarında veri akışını ne kadar analiz edip bu kurala ilişkin yapılandırılabilir bir sınır vardır. Bir EditorConfig dosyasında sınırı yapılandırma hakkında bilgi için bkz. [çözümleyici yapılandırması](https://github.com/dotnet/roslyn-analyzers/blob/master/docs/Analyzer%20Configuration.md#dataflow-analysis) .

## <a name="how-to-fix-violations"></a>İhlalleri çözme

Açık yeniden yönlendirme güvenlik açıklarını gidermeye yönelik bazı yaklaşımlar şunlardır:

- Kullanıcıların yeniden yönlendirmeleri başlatmasına izin verme.
- Kullanıcıların bir yeniden yönlendirme senaryosunda URL 'nin herhangi bir kısmını belirtmenize izin vermez.
- Yeniden yönlendirmeleri, URL 'Lerin önceden tanımlanmış bir "izin verilenler listesi" olarak kısıtlar.
- Yeniden yönlendirme URL 'Lerini doğrulayın.
- Uygulanabiliyorsa, kullanıcılar sitenizden yeniden yönlendirildiğinde bir vazgeçme sayfası kullanın.

## <a name="when-to-suppress-warnings"></a>Uyarıların ne zaman bastırılamıyor

Girişin amaçlanan URL 'Lerle sınırlı olduğunu bildiğinizi biliyorsanız, bu uyarıyı bastırmak de normaldir.

## <a name="pseudo-code-examples"></a>Sözde kod örnekleri

### <a name="violation"></a>Edildiği

```csharp
using System;

public partial class WebForm : System.Web.UI.Page
{
    protected void Page_Load(object sender, EventArgs e)
    {
        string input = Request.Form["url"];
        this.Response.Redirect(input);
    }
}
```

```vb
Imports System

Partial Public Class WebForm
    Inherits System.Web.UI.Page

    Protected Sub Page_Load(sender As Object, eventArgs As EventArgs)
        Dim input As String = Me.Request.Form("url")
        Me.Response.Redirect(input)
    End Sub
End Class
```

### <a name="solution"></a>Çözüm

```csharp
using System;

public partial class WebForm : System.Web.UI.Page
{
    protected void Page_Load(object sender, EventArgs e)
    {
        string input = Request.Form["in"];
        if (String.IsNullOrWhiteSpace(input))
        {
            this.Response.Redirect("https://example.org/login.html");
        }
    }
}
```

```vb
Imports System

Partial Public Class WebForm
    Inherits System.Web.UI.Page

    Protected Sub Page_Load(sender As Object, eventArgs As EventArgs)
        Dim input As String = Me.Request.Form("in")
        If String.IsNullOrWhiteSpace(input) Then
            Me.Response.Redirect("https://example.org/login.html")
        End If
    End Sub
End Class
```
