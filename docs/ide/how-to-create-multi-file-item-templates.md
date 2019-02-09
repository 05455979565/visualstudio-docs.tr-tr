---
title: Çok dosyalı öğe şablonları oluşturma
ms.date: 01/02/2018
ms.topic: conceptual
helpviewer_keywords:
- Visual Studio templates, creating multi-file item templates
- multi-file item templates
- item templates, creating multi-file item templates
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 1871b7270c462ea599450e48f0a86a4887ebc5ac
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/08/2019
ms.locfileid: "55970523"
---
# <a name="how-to-create-multi-file-item-templates"></a>Nasıl yapılır: Çok dosyalı şablonlar oluşturma

Öğe şablonları, yalnızca bir öğe belirtebilirsiniz, ancak öğe birden çok dosya bazen oluşur. Örneğin, bir Windows Forms öğe şablonu, aşağıdaki üç dosyayı gerektirir:

- Form için kod içeren bir dosya

- Form tasarımcısı bilgilerini içeren bir dosya

- Form için gömülü kaynaklar içeren bir dosya

Çok dosyalı öğe şablonları, öğe oluşturulduğunda doğru dosya uzantılarını kullanılmasını sağlamak için parametreleri gerektirir. Çok dosyalı öğe şablonu kullanarak oluşturursanız **şablonu Dışarı Aktarma Sihirbazı**, bu parametreleri otomatik olarak oluşturulur ve başka düzenleme gereklidir.

## <a name="to-create-a-multi-file-item-template-by-using-the-export-template-wizard"></a>Şablonu Dışarı Aktarma Sihirbazı'nı kullanarak bir çok dosyalı öğe şablonu oluşturmak için

Tek Dosyalı öğe şablonu olduğu gibi aynı şekilde çok dosyalı öğe şablonu oluşturabilirsiniz. Bkz: [nasıl yapılır: Öğe şablonları oluşturma](../ide/how-to-create-item-templates.md). Üzerinde **vermek öğesi seçin** Sayfası Sihirbazı'nın bağımlı dosyaları (örneğin, bir Windows Forms formu dosyası) sahip bir dosya seçin. Sihirbaz, şablonda tasarımcı ve kaynak dosyaları gibi tüm bağımlı dosyaları otomatik olarak içerir.

## <a name="to-manually-create-a-multi-file-item-template"></a>Çok dosyalı öğe şablonu el ile oluşturmak için

1. Öğe şablonu, el ile tek dosyalı öğe şablonu oluşturma, ancak dahil, çok dosyalı oluşturan her bir dosya oluşturun.

1. İçinde *.vstemplate* XML dosyasında, ekleme bir `ProjectItem` öğesi her kişi için dosya ve ekleme bir `TargetFileName` özniteliği bu öğe için. Değerini `TargetFileName` özniteliğini *$fileinputname$. FileExtension*burada *FileExtension* şablonuna dahil dosyanın dosya uzantısı. Örneğin:

    ```xml
    <ProjectItem TargetFileName="$fileinputname$.vb">
        Form1.vb
    </ProjectItem>
    <ProjectItem TargetFileName="$fileinputname$.Designer.vb">
        Form1.Designer.vb
    </ProjectItem>
    <ProjectItem TargetFileName="$fileinputname$.resx">
        Form1.resx
    </ProjectItem>
    ```

     > [!NOTE]
     > Bu şablondan türetilmiş bir öğe için bir proje eklendiğinde, dosya adları, kullanıcının girdiği adından derleyeceği **Yeni Öğe Ekle** iletişim kutusu.

1. Şablonunuzda eklenmesi, seçime sağ tıklayın ve dosyaları seçin **göndermek** > **sıkıştırılmış (daraltılmış) klasör**.

   Seçtiğiniz dosyalar sıkıştırılmadan bir *.zip* dosya.

1. Kopyalama *.zip* dosyasına kullanıcı öğe şablonu konumu. Varsayılan olarak, dizindir *%USERPROFILE%\Documents\Visual Studio \<sürüm\>\Templates\ItemTemplates*. Daha fazla bilgi için [nasıl yapılır: Şablonları bulma ve düzenleme](../ide/how-to-locate-and-organize-project-and-item-templates.md).

1. Visual Studio'yu kapatın ve yeniden açın.

1. Yeni bir proje oluşturun veya varolan bir projeyi açın ve ardından **proje** > **Yeni Öğe Ekle** veya basın **Ctrl** +  **Shift**+**A**.

   Çok dosyalı öğe şablonu görünür **Yeni Öğe Ekle** iletişim kutusu.

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir Windows Forms şablonu gösterir. Bu şablona dayalı bir öğe oluşturulduğunda oluşturulan üç dosyalarının adlarını girdiğiniz ad eşleşecektir **Yeni Öğe Ekle** iletişim kutusu.

```xml
<VSTemplate Version="2.0.0" Type="Item"
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">
    <TemplateData>
        <Name>Multi-file Item Template</Name>
        <Icon>Icon.ico</Icon>
        <Description>An example of a multi-file item template</Description>
        <ProjectType>VisualBasic</ProjectType>
    </TemplateData>
    <TemplateContent>
        <ProjectItem TargetFileName="$fileinputname$.vb" SubType="Form">
            Form1.vb
        </ProjectItem>
        <ProjectItem TargetFileName="$fileinputname$.Designer.vb">
            Form1.Designer.vb
        </ProjectItem>
        <ProjectItem TargetFileName="$fileinputname$.resx">
            Form1.resx
        </ProjectItem>
    </TemplateContent>
</VSTemplate>
```

## <a name="see-also"></a>Ayrıca bkz.

- [Proje ve öğe şablonları oluşturma](../ide/creating-project-and-item-templates.md)
- [Nasıl yapılır: Öğe şablonları oluşturma](../ide/how-to-create-item-templates.md)
- [Şablon parametreleri](../ide/template-parameters.md)
- [Nasıl yapılır: Bir şablonda parametreleri ikame](../ide/how-to-substitute-parameters-in-a-template.md)