---
title: Kod stili seçenekleri ve kod Temizleme
ms.date: 04/25/2019
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: jillfra
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.CSharp.Code_Style.General
- VS.ToolsOptionsPages.Text_Editor.Basic.Code_Style.General
ms.workload:
- multiple
ms.openlocfilehash: 4c7bb8f3e94a761023a19a5ea3361073b73d9f3b
ms.sourcegitcommit: 90c3187d804ad7544367829d07ed4b47d3f8a72d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/06/2019
ms.locfileid: "68822412"
---
# <a name="code-style-preferences"></a>Kod stili tercihleri

Bir [Editorconfig dosyası](#code-styles-in-editorconfig-files)kullanarak proje başına kod stili ayarları tanımlayabilir veya metin düzenleyici [ **seçenekleri** sayfasında](#code-styles-in-the-options-dialog-box)Visual Studio 'da düzenlediğiniz tüm kodlar için. Kod C# Için, Visual Studio 'Yu **Code Cleanup** (Visual Studio 2019) ve **Format Document** (Visual Studio 2017) komutlarını kullanarak bu kod stili tercihlerini uygulamak üzere de yapılandırabilirsiniz.

> [!NOTE]
> Bu konu, Windows üzerinde Visual Studio için geçerlidir. Mac için Visual Studio için bkz: [Mac için Visual Studio'daki Düzenleyici davranışı](/visualstudio/mac/editor-behavior).

## <a name="code-styles-in-editorconfig-files"></a>EditorConfig dosyalarındaki kod stilleri

.NET için [kod stili ayarları](../ide/editorconfig-code-style-settings-reference.md) , projenize bir [editorconfig](create-portable-custom-editor-options.md) dosyası eklenerek belirtilebilir. EditorConfig dosyaları, Visual Studio kişiselleştirme hesabı yerine bir kod temeli ile ilişkilendirilir. Bir EditorConfig dosyasındaki ayarlar, **Seçenekler** iletişim kutusunda belirtilen kod stillerinden önceliklidir. Deponuzda veya projenizde tüm katkıda bulunanlar için kodlama stillerini zorlamak istediğinizde bir EditorConfig dosyası kullanın.

::: moniker range=">=vs-2019"

EditorConfig dosyanızı el ile doldurabilir veya Visual Studio **seçenekleri** iletişim kutusunda seçtiğiniz kod stili ayarlarına bağlı olarak dosyayı otomatik olarak oluşturabilirsiniz. Bu seçenekler sayfası **Araçlar** > **Seçenekler** > **metin Düzenleyicisi** > [**C#** veya **temel**] > **kod stili** > **genel**' te kullanılabilir. Bu **Seçenekler** sayfasındaki ayarlara göre otomatik olarak bir kodlama stili *. editorconfig* dosyası oluşturmak için, **ayarlardan. editorconfig dosyası oluştur** ' a tıklayın.

![Visual Studio 2019 ayarlarından editorconfig dosyası oluşturma](media/vs-2019/generate-editorconfig-file-small.png)

::: moniker-end

## <a name="code-styles-in-the-options-dialog-box"></a>Seçenekler iletişim kutusundaki kod stilleri

Kod stili tercihleri, **Araçlar** menüsünden **Seçenekler** iletişim kutusu açılarak C# tüm ve Visual Basic projeleriniz için ayarlanabilir. İçinde **seçenekleri** iletişim kutusunda **metin düzenleyici** > [**C#** veya **temel**] > **kod stili**  >  **Genel**.

Listedeki her bir öğe seçildiğinde tercih önizlemesini sunar:

::: moniker range="vs-2017"

![Kod stili seçenekleri](media/code-style-quick-actions-dialog.png)

::: moniker-end

::: moniker range=">=vs-2019"

![Kod stili seçenekleri](media/vs-2019/code-style-quick-actions-dialog.png)

::: moniker-end

Bu pencerede ayarlanan seçenekler, Visual Studio kişiselleştirme hesabınız için geçerlidir ve belirli bir proje ya da kod temeli ile ilişkili değildir. Ayrıca, sürekli tümleştirme (CI) yapıları dahil olmak üzere derleme zamanında zorlanmaz. Kod stili tercihlerini projenizle ilişkilendirmek ve derleme sırasında uygulanan stilleri sağlamak istiyorsanız, tercihleri projeyle ilişkili bir [. editorconfig dosyasında](#code-styles-in-editorconfig-files) belirtin.

### <a name="preference-and-severity"></a>Tercihi ve önem derecesi

Bu sayfadaki her kod stili ayarı için, her satırdaki açılan listeleri kullanarak **tercih** ve **önem derecesi** değerlerini ayarlayabilirsiniz. Önem derecesi **yalnızca yeniden düzenleme**, **öneri**, **Uyarı**veya **hata**olarak ayarlanabilir. Bir kod stili için [hızlı eylemleri](../ide/quick-actions.md) etkinleştirmek Istiyorsanız, **önem derecesi** ayarının **yalnızca yeniden düzenleme**dışında bir değere ayarlandığından emin olun. Tercih edilen olmayan bir stil ![kullanıldığında **hızlı eylemler** ampul ampullü ![ampul](media/light-bulb-dropdown.png)](media/error-bulb.png), hata açık ampul hatası ampul veya ![screwsürücü](media/screwdriver.png) screwdriver simgesi görüntülenir. ve otomatik olarak kodu tercih edilen stile yeniden yazmak için **hızlı eylemler** listesinden bir seçenek belirleyebilirsiniz.

## <a name="apply-code-styles"></a>Kod stillerini Uygula

::: moniker range="vs-2017"

Kod stili ayarlarınızı (bir editorconfig dosyası veya **kod stili** seçeneklerinden) ve ile birlikte uygulamak için, **Biçim belgesi** komutunu (**Gelişmiş** > **Biçim belgesini** **Düzenle** > ) yapılandırabilirsiniz. yaptığı normal biçimlendirme (girintileme gibi). Proje için bir *. editorconfig* dosyası varsa, bu ayarlar öncelik kazanır.

> [!NOTE]
> **Belgeyi Biçimlendir** komutunu kullanarak kod stillerini uygulamak yalnızca kod dosyaları için C# kullanılabilir. Bu bir deneysel özelliktir.

[Biçimlendirme seçenekleri sayfasında](reference/options-text-editor-csharp-formatting.md#format-document-settings) **Belge biçimini biçimlendirmek** istediğiniz ayarları yapılandırın.

![Visual Studio 2017 'de biçim belgesi için kod stili ayarları](media/format-document-settings-experiment.png)

> [!TIP]
> **Hiçbiri** önem derecesine sahip bir şekilde yapılandırılan kurallar kod temizlemesine katılmaz, ancak **Hızlı Eylemler ve yeniden düzenlemeler** menüsüyle tek tek uygulanabilir.

**Biçim belgesi** komutunu ilk kez tetikleyişinizde, sarı bir bilgi çubuğu kod temizleme ayarlarınızı yapılandırmanızı ister.

::: moniker-end

::: moniker range=">=vs-2019"

Kod C# dosyaları Için, Visual Studio 2019 düzenleyicinin alt kısmındaki bir **kod temizleme** düğmesine sahiptir (klavye:+Bir editorconfig dosyasından veya **kod stili** seçenekleri sayfasından kod stilleri uygulamak için CTRL**K**, **CTRL**+**E**). Proje için bir *. editorconfig* dosyası varsa, bu ayarlar öncelik kazanır.

![Visual Studio 2019 ' de kod temizlemeyi yürütme](media/execute-code-cleanup.png)

> [!TIP]
> **Hiçbiri** önem derecesine sahip bir şekilde yapılandırılan kurallar kod temizlemesine katılmaz, ancak **Hızlı Eylemler ve yeniden düzenlemeler** menüsüyle tek tek uygulanabilir.

İlk olarak, **kod temizlemeyi Yapılandır** iletişim kutusunda hangi kod stillerini uygulamak istediğinizi (iki profilden birinde) yapılandırın. Bu iletişim kutusunu açmak için, kod temizleme Brob simgesinin yanındaki genişletici okuna ve ardından **kod temizlemeyi Yapılandır**' ı seçin.

![Visual Studio 2019 ' de kod temizlemeyi yapılandırma](media/configure-code-cleanup.png)

Kod temizlemeyi yapılandırdıktan sonra, kod temizlemeyi çalıştırmak için Broom simgesine tıklayabilir veya **CTRL**+**K**, **CTRL**+**E** tuşlarına basabilirsiniz. Ayrıca, tüm proje veya çözümünüz genelinde kod temizleme işlemini de çalıştırabilirsiniz. **Çözüm Gezgini**' de proje veya çözüm adına sağ tıklayın, **Çözümle ve kod temizleme**' yi seçin ve ardından **kod temizlemeyi Çalıştır**' ı seçin.

![Kod temizlemeyi tüm proje veya çözüm genelinde Çalıştır](media/run-code-cleanup-project-solution.png)

Kod stili ayarlarınızın bir dosyayı her kaydedişinizde uygulanmasını istiyorsanız, [kayıt uzantısında kod temizlemeyi](https://marketplace.visualstudio.com/items?itemName=MadsKristensen.CodeCleanupOnSave) beğenmeyebilirsiniz.

::: moniker-end

## <a name="see-also"></a>Ayrıca bkz.

- [Hızlı Eylemler](../ide/quick-actions.md)
- [Kodlama kuralı ayarlarına EditorConfig için .NET](../ide/editorconfig-code-style-settings-reference.md)
- [Düzenleyici davranışı (Mac için Visual Studio)](/visualstudio/mac/editor-behavior)
