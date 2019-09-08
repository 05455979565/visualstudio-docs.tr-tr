---
title: Proje ve öğe şablon parametreleri
ms.date: 01/02/2018
ms.topic: reference
helpviewer_keywords:
- Visual Studio templates, parameters
- template parameters [Visual Studio]
- project templates, parameters
- item templates, parameters
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 2fbc9d95a6e334c3dcd788c4b686a222c417b0df
ms.sourcegitcommit: 0f44ec8ba0263056ad04d2d0dc904ad4206ce8fc
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70766107"
---
# <a name="template-parameters"></a>Şablon parametreleri

Şablon örneği başlatıldığında, şablonunuzda değerleri değiştirebilirsiniz. Bu işlevini ayarlamak için kullanın *şablon parametreleri*. Şablon parametresi sınıf adları ve şablonda ad alanları gibi değerleri değiştirmek için kullanılabilir. Şablon Sihirbazı, bir kullanıcı yeni bir öğe ekler veya proje bu parametreler, arka planda çalışır.

## <a name="declare-and-enable-template-parameters"></a>Şablon parametrelerini bildir ve Etkinleştir

Şablon parametreleri biçimi $ içinde bildirilen*parametre*$. Örneğin:

- $safeprojectname$

- $guid1$

- $guid5$

### <a name="enable-parameter-substitution-in-templates"></a>Şablonlarda parametre değişimini etkinleştir

1. İçinde *.vstemplate* dosya, şablonunu bulun `ProjectItem` parametre değiştirme etkinleştirmek istediğiniz öğeye karşılık gelen öğe.

1. Ayarlama `ReplaceParameters` özniteliği `ProjectItem` öğesine `true`.

1. Proje öğesi için kod dosyasında, uygun yerlerde parametreleri içerir. Örneğin, aşağıdaki parametre güvenli proje adı ad alanında bir dosya için kullanıldığını belirtir:

    ```csharp
    namespace $safeprojectname$
    ```

## <a name="reserved-template-parameters"></a>Ayrılmış şablon parametreleri

Aşağıdaki tabloda, herhangi bir şablon tarafından kullanılabilecek ayrılmış şablon parametreleri listelenmektedir:

|Parametre|Açıklama|
|---------------|-----------------|
|clrversion|Geçerli sürümü ortak dil çalışma zamanı (CLR).|
|ext_*|Üst şablonun değişkenlerine başvurmak için herhangi bir parametreye önekiekleyin.`ext_` Örneğin: `ext_safeprojectname`.|
|1-10 GUID|' % S'projesi bir proje dosyasında GUID değiştirmek için kullanılan bir GUID. En fazla 10 benzersiz GUID'ler belirtebilirsiniz (örneğin, `guid1`).|
|ItemName|Parametrenin kullanıldığı dosyanın adı.|
|MachineName|Geçerli bilgisayar adı (örneğin, Computer01).|
|ProjectName|Proje oluşturulduğunda Kullanıcı tarafından girilen ad.|
|RegisteredOrganization|Kayıt defteri anahtar değeri HKLM\Software\Microsoft\Windows NT\CurrentVersion\RegisteredOrganization.|
|RootNamespace|Geçerli projenin kök ad alanı. Bu parametre, yalnızca öğe şablonları için geçerlidir.|
|safeitemname|`itemname` Bununla aynı ancak tüm güvenli olmayan karakterler ve boşluklar alt çizgi karakterleriyle değiştirilirler.|
|safeitemrootname|`safeitemname`Aynı.|
|safeprojectname|Proje oluşturulduğunda Kullanıcı tarafından belirtilen ad ve tüm güvenli olmayan karakterler ve boşluklar kaldırıldı.|
|zaman|GG/AA/YYYY biçiminde geçerli saati 00:00:00.|
|Belirtilmedisolutionname|Çözüm adı. "Çözüm dizini oluşturma" işaretlendiğinde `specifiedSolutionName` çözüm adına sahip. "Çözüm dizini oluşturma" işaretli olduğunda `specifiedSolutionName` boştur.|
|USERDOMAIN|Geçerli kullanıcı etki alanı.|
|Kullanıcı adı|Geçerli kullanıcı adı.|
|webnamespace|Geçerli Web sitesinin adı. Bu parametre, web formu şablonda benzersiz sınıf isimleri güvence altına almak için kullanılır. Web sitesi web sunucusunun kök dizininde ise, bu şablon parametresi web sunucusunun kök dizinine çözümler.|
|Yıl|YYYY biçiminde geçerli yıl.|

> [!NOTE]
> Şablon parametreleri büyük/küçük harfe duyarlıdır.

## <a name="custom-template-parameters"></a>Özel şablon parametreleri

Kendi şablon parametreleri ve değerleri, ek parametre değiştirme sırasında kullanılan ayrılmış varsayılan şablon parametreleri olarak belirtebilirsiniz. Daha fazla bilgi için [CustomParameters öğesi (Visual Studio şablonları)](../extensibility/customparameters-element-visual-studio-templates.md).

## <a name="example-use-the-project-name-for-a-file-name"></a>Örnek: Dosya adı için proje adını kullan

Bir parametre kullanarak proje öğeleri için değişken dosya adlarını belirtebilirsiniz `TargetFileName` özniteliği.

Aşağıdaki örnek, bir yürütülebilir dosyanın adını tarafından belirtilen proje adı kullandığını belirtir `$projectname$`.

```xml
<TemplateContent>
    <ProjectItem
        ReplaceParameters="true"
        TargetFileName="$projectname$.exe">
            File1.exe
    </ProjectItem>
      ...
</TemplateContent>
```

## <a name="example-use-the-safe-project-name-for-the-namespace-name"></a>Örnek: Ad alanı adı için güvenli proje adını kullanın

C# sınıf dosyasında ad alanı için güvenli bir proje adı kullanmak için aşağıdaki sözdizimini kullanın:

```csharp
namespace $safeprojectname$
{
    public class Class1
    {
        public Class1()
        { }
    }
}
```

İçinde *.vstemplate* dosya için proje şablonu, dahil `ReplaceParameters="true"` dosyasına başvurduğunuzda özniteliği:

```xml
<TemplateContent>
    <ProjectItem ReplaceParameters="true">
        Class1.cs
    </ProjectItem>
    ...
</TemplateContent>
```

## <a name="see-also"></a>Ayrıca bkz.

- [Nasıl yapılır: Şablondaki parametreleri değiştirme](how-to-substitute-parameters-in-a-template.md)
- [Şablonları özelleştirme](../ide/customizing-project-and-item-templates.md)
- [Nasıl yapılır: Proje şablonları oluşturma](../ide/how-to-create-project-templates.md)
- [Şablon Şeması Başvurusu](../extensibility/visual-studio-template-schema-reference.md)
