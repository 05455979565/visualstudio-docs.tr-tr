---
title: 'CA3011: DLL ekleme güvenlik açıkları için inceleme kodu'
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
ms.openlocfilehash: a459be8c8ab028581c850f5b5770a95cb70e3510
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/24/2019
ms.locfileid: "71237198"
---
# <a name="ca3011-review-code-for-dll-injection-vulnerabilities"></a>CA3011: DLL ekleme güvenlik açıkları için inceleme kodu

|||
|-|-|
|TypeName|Belgelerkodufordllinjectionaçıklardan|
|CheckId|CA3011|
|Kategori|Microsoft.Security|
|Son değişiklik|Kırılmamış|

## <a name="cause"></a>Sebep

Güvenilir olmayan HTTP isteği girişi, bir derlemeyi yükleyen bir yönteme ulaşırsa.

## <a name="rule-description"></a>Kural açıklaması

Güvenilmeyen girişle çalışırken güvenilmeyen kodun yüklenmesi gerekir. Web uygulamanız güvenilmeyen kod yüklerse, bir saldırgan işlem için kötü amaçlı dll 'Leri ekleyebilir ve kötü amaçlı kod yürütebilir.

Bu kural, bir derlemeyi yükleyen bir yönteme ulaşan HTTP isteğinden giriş bulmaya çalışır.

> [!NOTE]
> Bu kural derlemeler genelinde verileri izleyemez. Örneğin, bir derleme HTTP istek girişini okuyup derlemeyi yükleyen başka bir derlemeye geçirirse, bu kural bir uyarı oluşturmaz.

> [!NOTE]
> Bu kuralın, yöntem çağrılarında veri akışını ne kadar analiz edip bu kurala ilişkin yapılandırılabilir bir sınır vardır. Bir EditorConfig dosyasında sınırı yapılandırma hakkında bilgi için bkz. [çözümleyici yapılandırması](https://github.com/dotnet/roslyn-analyzers/blob/master/docs/Analyzer%20Configuration.md#dataflow-analysis) .

## <a name="how-to-fix-violations"></a>İhlalleri çözme

Güvenilmeyen dll 'Leri Kullanıcı girişinden yüklemeyin.

## <a name="when-to-suppress-warnings"></a>Uyarıların ne zaman bastırılamıyor

Bu kuraldan gelen uyarıları göstermez.

## <a name="pseudo-code-examples"></a>Sözde kod örnekleri

### <a name="violation"></a>Edildiği

```csharp
using System;
using System.Reflection;

public partial class WebForm : System.Web.UI.Page
{
    protected void Page_Load(object sender, EventArgs e)
    {
        string input = Request.Form["in"];
        byte[] rawAssembly = Convert.FromBase64String(input);
        Assembly.Load(rawAssembly);
    }
}
```

```vb
Imports System
Imports System.Reflection

Public Partial Class WebForm
    Inherits System.Web.UI.Page

    Protected Sub Page_Load(sender As Object, e As EventArgs)
        Dim input As String = Request.Form("in")
        Dim rawAssembly As Byte() = Convert.FromBase64String(input)
        Assembly.Load(rawAssembly)
    End Sub
End Class
```
