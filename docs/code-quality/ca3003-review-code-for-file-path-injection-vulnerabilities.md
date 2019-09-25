---
title: 'CA3003: Dosya yolu ekleme güvenlik açıkları için inceleme kodu'
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
ms.openlocfilehash: c9e43dcdf1e923cb7bc4a98b17fd0be71b7927eb
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/24/2019
ms.locfileid: "71237406"
---
# <a name="ca3003-review-code-for-file-path-injection-vulnerabilities"></a>CA3003: Dosya yolu ekleme güvenlik açıkları için inceleme kodu

|||
|-|-|
|TypeName|Belgeınlist Codeforfilepathınjectionaçıklardan|
|CheckId|CA3003|
|Kategori|Microsoft.Security|
|Son değişiklik|Kırılmamış|

## <a name="cause"></a>Sebep

Güvenilir olmayan HTTP isteği girişi bir dosya işleminin yoluna ulaşır.

## <a name="rule-description"></a>Kural açıklaması

Web isteklerinden güvenilmeyen giriş ile çalışırken, dosyalara yollar belirtirken Kullanıcı denetimli girişi kullanmanın en az olması gerekir. Saldırgan, istenmeyen bir dosyayı okuyabilir ve bu da hassas verilerin bilgi halinde açıklanmasına neden olabilir. Ya da bir saldırgan, istenmeyen bir dosyaya yazabiliyor olabilir, bu da hassas verilerin yetkisiz olarak değiştirilmesine veya sunucunun güvenliğinin tehlikeye çıkmasına yol açabilir. Ortak bir saldırgan tekniği, hedeflenen dizin dışındaki dosyalara erişmek için [yol çapraz geçiş yoludur](https://www.owasp.org/index.php/Path_Traversal) .

Bu kural, bir dosya işlemindeki yola ulaşan HTTP isteklerinden girdi bulmaya çalışır.

> [!NOTE]
> Bu kural derlemeler genelinde verileri izleyemez. Örneğin, bir derleme HTTP istek girişini okuyup onu bir dosyaya yazan başka bir derlemeye geçirirse, bu kural bir uyarı oluşturmaz.

> [!NOTE]
> Bu kuralın, yöntem çağrılarında veri akışını ne kadar analiz edip bu kurala ilişkin yapılandırılabilir bir sınır vardır. Bir EditorConfig dosyasında sınırı yapılandırma hakkında bilgi için bkz. [çözümleyici yapılandırması](https://github.com/dotnet/roslyn-analyzers/blob/master/docs/Analyzer%20Configuration.md#dataflow-analysis) .

## <a name="how-to-fix-violations"></a>İhlalleri çözme

- Mümkünse, dosya yollarını Kullanıcı girişine dayalı olarak açıkça bilinen bir güvenli listeye sınırlayın.  Örneğin, uygulamanızın yalnızca "Red. txt", "Green. txt" veya "Blue. txt" erişimine ihtiyacı varsa yalnızca bu değerlere izin verin.
- Güvenilmeyen dosya adlarını denetleyin ve adın düzgün biçimlendirildiğini doğrulayın.
- Yolları belirtirken tam yol adlarını kullanın.
- Yol ortam değişkenleri gibi potansiyel olarak tehlikeli yapılarından kaçının.
- Yalnızca uzun dosya adlarını kabul edin ve Kullanıcı kısa adlar gönderdiğinde uzun adı doğrulayın.
- Son Kullanıcı girişini geçerli karakterlerle sınırlayın.
- MAX_PATH uzunluğunun aşıldığı adları reddedin.
- Dosya adlarını, yorum yapmadan tam olarak işleme.
- Dosya adının bir dosyayı mu yoksa bir cihazı mi temsil ettiğini belirleme.

## <a name="when-to-suppress-warnings"></a>Uyarıların ne zaman bastırılamıyor

Önceki bölümde açıklandığı gibi girişi doğrulandıktan sonra bu uyarıyı bastırmak de normaldir.

## <a name="pseudo-code-examples"></a>Sözde kod örnekleri

### <a name="violation"></a>Edildiği

```csharp
using System;
using System.IO;

public partial class WebForm : System.Web.UI.Page
{
    protected void Page_Load(object sender, EventArgs e)
    {
        string userInput = Request.Params["UserInput"];
        // Assume the following directory structure:
        //   wwwroot\currentWebDirectory\user1.txt
        //   wwwroot\currentWebDirectory\user2.txt
        //   wwwroot\secret\allsecrets.txt
        // There is nothing wrong if the user inputs:
        //   user1.txt
        // However, if the user input is:
        //   ..\secret\allsecrets.txt
        // Then an attacker can now see all the secrets.

        // Avoid this:
        using (File.Open(userInput, FileMode.Open))
        {
            // Read a file with the name supplied by user
            // Input through request's query string and display
            // The content to the webpage.
        }
    }
}
```

```vb
Imports System
Imports System.IO

Partial Public Class WebForm
    Inherits System.Web.UI.Page

    Protected Sub Page_Load(sender As Object, e As EventArgs)
        Dim userInput As String = Me.Request.Params("UserInput")
        ' Assume the following directory structure:
        '   wwwroot\currentWebDirectory\user1.txt
        '   wwwroot\currentWebDirectory\user2.txt
        '   wwwroot\secret\allsecrets.txt
        ' There is nothing wrong if the user inputs:
        '   user1.txt
        ' However, if the user input is:
        '   ..\secret\allsecrets.txt
        ' Then an attacker can now see all the secrets.

        ' Avoid this:
        Using File.Open(userInput, FileMode.Open)
            ' Read a file with the name supplied by user
            ' Input through request's query string and display
            ' The content to the webpage.
        End Using
    End Sub
End Class
```
