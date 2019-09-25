---
title: 'CA3008: XPath ekleme güvenlik açıkları için inceleme kodu'
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
ms.openlocfilehash: 1d001dc306bbb225c4ecc1c0f17bf46619e2d0a7
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/24/2019
ms.locfileid: "71237255"
---
# <a name="ca3008-review-code-for-xpath-injection-vulnerabilities"></a>CA3008: XPath ekleme güvenlik açıkları için inceleme kodu

|||
|-|-|
|TypeName|Belgeınlist Codeforxpathınjectionaçıklardan|
|CheckId|CA3008|
|Kategori|Microsoft.Security|
|Son değişiklik|Kırılmamış|

## <a name="cause"></a>Sebep

Potansiyel olarak güvenilmeyen HTTP isteği girişi bir XPath sorgusuna ulaşır.

## <a name="rule-description"></a>Kural açıklaması

Güvenilmeyen girişle çalışırken, XPath ekleme saldırılarına karşı en az bir yer vardır. Güvenilmeyen giriş kullanarak XPath sorguları oluşturmak, bir saldırganın istenmeyen bir sonuç döndürmek için sorguyu kötü amaçlı olarak işlemesini ve sorgulanan XML 'in içeriğini açığa çıkarmasına izin verebilir.

Bu kural, bir XPath ifadesine ulaşan HTTP isteklerinden girdi bulmaya çalışır.

> [!NOTE]
> Bu kural derlemeler genelinde verileri izleyemez. Örneğin, bir derleme HTTP istek girişini okuyup bir XPath sorgusu gerçekleştiren başka bir derlemeye geçerse, bu kural bir uyarı oluşturmaz.

> [!NOTE]
> Bu kuralın, yöntem çağrılarında veri akışını ne kadar analiz edip bu kurala ilişkin yapılandırılabilir bir sınır vardır. Bir EditorConfig dosyasında sınırı yapılandırma hakkında bilgi için bkz. [çözümleyici yapılandırması](https://github.com/dotnet/roslyn-analyzers/blob/master/docs/Analyzer%20Configuration.md#dataflow-analysis) .

## <a name="how-to-fix-violations"></a>İhlalleri çözme

XPath ekleme güvenlik açıklarını gidermeye yönelik bazı yaklaşımlar şunlardır:

- Kullanıcı girişinden XPath sorguları oluşturmayın.
- Girişin yalnızca güvenli bir karakter kümesi içerdiğini doğrulayın.
- Kaçış tırnak işaretleri.

## <a name="when-to-suppress-warnings"></a>Uyarıların ne zaman bastırılamıyor

Girişin güvenli olduğunu bildiğinizi biliyorsanız, bu uyarıyı bastırmak normaldir.

## <a name="pseudo-code-examples"></a>Sözde kod örnekleri

### <a name="violation"></a>Edildiği

```csharp
using System;
using System.Xml.XPath;

public partial class WebForm : System.Web.UI.Page
{
    public XPathNavigator AuthorizedOperations { get; set; }

    protected void Page_Load(object sender, EventArgs e)
    {
        string operation = Request.Form["operation"];

        // If an attacker uses this for input:
        //     ' or 'a' = 'a
        // Then the XPath query will be:
        //     authorizedOperation[@username = 'anonymous' and @operationName = '' or 'a' = 'a']
        // and it will return any authorizedOperation node.
        XPathNavigator node = AuthorizedOperations.SelectSingleNode(
            "//authorizedOperation[@username = 'anonymous' and @operationName = '" + operation + "']");
    }
}
```

```vb
Imports System
Imports System.Xml.XPath

Partial Public Class WebForm
    Inherits System.Web.UI.Page

    Public Property AuthorizedOperations As XPathNavigator

    Protected Sub Page_Load(sender As Object, e As EventArgs)
        Dim operation As String = Me.Request.Form("operation")

        ' If an attacker uses this for input:
        '     ' or 'a' = 'a
        ' Then the XPath query will be:
        '      authorizedOperation[@username = 'anonymous' and @operationName = '' or 'a' = 'a']
        ' and it will return any authorizedOperation node.
        Dim node As XPathNavigator = AuthorizedOperations.SelectSingleNode( _
            "//authorizedOperation[@username = 'anonymous' and @operationName = '" + operation + "']")
    End Sub
End Class
```
