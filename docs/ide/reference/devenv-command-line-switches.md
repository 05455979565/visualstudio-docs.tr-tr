---
title: Devenv komut satırı anahtarları
ms.date: 12/10/2018
ms.topic: reference
helpviewer_keywords:
- switches, Devenv
- command-line switches, Devenv
- command line [Visual Studio], switches
- Devenv
ms.assetid: e12bc6ed-74fd-4bea-8d7c-89b99c20bad8
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: ed7a36ad561daf87ec65db0f6c51c9dd7833eb9e
ms.sourcegitcommit: ddd99f64a3f86508892a6d61e8a33c88fb911cc4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/29/2020
ms.locfileid: "82255558"
---
# <a name="devenv-command-line-switches"></a>Devenv komut satırı anahtarları

Devenv, komut satırından IDE için çeşitli seçenekler ayarlamanıza, projeler oluşturmanıza, projelerde hata ayıklamanıza ve proje dağıtmanıza imkan tanır. IDE 'yi bir komut dosyası veya. bat dosyasından (gecelik derleme betiği gibi) çalıştırmak veya IDE 'yi belirli bir yapılandırmada başlatmak için bu anahtarları kullanın.

> [!NOTE]
> Derleme ile ilgili görevler için devenv yerine MSBuild kullanmanız önerilir. Daha fazla bilgi için bkz. [MSBuild komut satırı başvurusu](../../msbuild/msbuild-command-line-reference.md).

VSPackage geliştirmeyle ilgili anahtarlar hakkında daha fazla bilgi için bkz. [VSPackage geliştirmesi Için Devenv komut satırı anahtarları](../../extensibility/devenv-command-line-switches-for-vspackage-development.md).

## <a name="devenv-switch-syntax"></a>Devenv Switch sözdizimi

İle `devenv` başlayan komutlar, `devenv.com` `stdout` ve `stderr`gibi standart sistem akışları üzerinden çıkış sunan yardımcı program tarafından işlenir. Yardımcı programı çıktıyı yakaladığında, örneğin bir. txt dosyasına uygun g/ç yeniden yönlendirmeyi belirler.

Alternatif olarak, ile `devenv.exe` başlayan komutlar aynı anahtarları kullanabilir, ancak `devenv.com` yardımcı program atlanır. Kullanımı `devenv.exe` doğrudan kullanmak çıktının konsolda görüntülenmesini önler.

Anahtarlar için `devenv` sözdizimi kuralları, diğer DOS komut satırı yardımcı programları için kurallara benzer. Aşağıdaki sözdizimi kuralları tüm `devenv` anahtarlar ve bunların bağımsız değişkenleri için geçerlidir:

- Komutları ile `devenv`başlar.

- Anahtarlar büyük/küçük harfe duyarlı değildir.

- Bir anahtarı, kısa çizgi ("-") veya eğik çizgi ("/") kullanarak belirtebilirsiniz.

- Bir çözüm veya proje belirtirken, ilk bağımsız değişken dosya yolu da dahil olmak üzere çözüm dosyasının veya proje dosyasının adıdır.

- İlk bağımsız değişken bir çözüm veya proje olmayan bir dosya ise, bu dosya, IDE 'nin yeni bir örneğinde uygun düzenleyicide açılır.

- Bir çözüm dosyası adı yerine bir proje dosya adı sağlarsanız, bir `devenv` komut aynı ada sahip bir çözüm dosyası için proje dosyasının ana klasörünü arar. Örneğin, komut `devenv myproject1.vbproj /build` üst klasörü adında `myproject1.sln`bir çözüm dosyası arar.

  > [!NOTE]
  > Bu projeye başvuran bir ve yalnızca bir çözüm dosyası, üst klasöründe bulunmalıdır. Üst klasörde bu projeye başvuruda bulunan çözüm dosyası yoksa veya üst klasör ona başvuran iki veya daha fazla çözüm dosyası içeriyorsa, geçici bir çözüm dosyası oluşturulur.

- Dosya yolları ve dosya adları boşluk içeriyorsa, bunları tırnak işaretleri ("") içine almanız gerekir. Örneğin, `"c:\project a\"`.

- Aynı satırdaki anahtarlar ve bağımsız değişkenler arasına bir boşluk karakteri ekleyin. Örneğin, komut `devenv /log output.txt` IDE 'yi açar ve bu oturuma ait tüm günlük bilgilerini çıktı. txt dosyasına verir.

- `devenv` Komutlarda desenli eşleştirme sözdizimini kullanamazsınız.

## <a name="devenv-switches"></a>Devenv anahtarları

Aşağıdaki komut satırı anahtarları IDE 'yi görüntüler ve açıklanan görevi yapar.

|Komut satırı anahtarı|Açıklama|
| - |-----------------|
|[/Command](command-devenv-exe.md)|IDE 'yi başlatır ve belirtilen komutu yürütür.<br /><br /> `devenv /command "nav https://docs.microsoft.com/"`|
|[/DebugExe](debugexe-devenv-exe.md)|Hata ayıklayıcının denetimi altına bir C++ yürütülebiliri yükler. Bu anahtar Visual Basic veya C# yürütülebilir dosyaları için kullanılamaz. Daha fazla bilgi için bkz. [hata ayıklayıcıda otomatik olarak bir işlem başlatma](../../debugger/debug-multiple-processes.md#BKMK_Automatically_start_an_process_in_the_debugger).<br /><br /> `devenv /debugexe mysln.exe`|
|[/Diff](diff.md)|İki dosyayı karşılaştırır. Dört parametre alır: *SourceFile*, *TargetFile*, *sourcedisplayname* (isteğe bağlı) ve *targetdisplayname* (isteğe bağlı).<br /><br /> `devenv /diff File1 File2 Alias1 Alias2`|
|[/DoNotLoadProjects](donotloadprojects-devenv-exe.md)|Herhangi bir proje yüklemeden belirtilen çözümü açar.<br /><br /> `devenv /donotloadprojects mysln.sln`|
|[/Edit](edit-devenv-exe.md)|Belirtilen dosyaları bu uygulamanın çalışan bir örneğinde açar. Çalışan örnek yoksa, Basitleştirilmiş pencere düzenine sahip yeni bir örneği başlatır.<br /><br /> `devenv /edit File1 File2`|
|[/LCıD veya/L](lcid-devenv-exe.md)|IDE için varsayılan dili ayarlar. Visual Studio yüklemenize belirtilen dil dahil değilse, bu ayar yok sayılır.<br /><br /> `devenv /l 1033`|
|[/Log](log-devenv-exe.md)|Visual Studio 'Yu başlatır ve tüm etkinlikleri günlük dosyasına kaydeder.<br /><br /> `devenv /log mylogfile.xml`|
|[/NoSplash](nosplash-devenv-exe.md)|Giriş ekranını göstermeden IDE 'yi açar.<br /><br /> `devenv /nosplash File1 File2`|
|[/ResetSettings](resetsettings-devenv-exe.md)|Visual Studio varsayılan ayarlarını geri yükler. Ayarları, belirtilen `.vssettings` dosya için isteğe bağlı olarak sıfırlar.<br /><br /> `devenv /resetsettings mysettings.vssettings`|
|[/Run veya/R](run-devenv-exe.md)|Belirtilen çözümü derler ve çalıştırır.<br /><br /> `devenv /run mysln.sln`|
|[/RunExit](runexit-devenv-exe.md)|Belirtilen çözümü derler ve çalıştırır, çözüm çalıştırıldığında IDE 'yi en aza indirir ve çözümün çalışmasını tamamladıktan sonra IDE 'yi kapatır.<br /><br /> `devenv /runexit mysln.sln`|
|[/SafeMode](safemode-devenv-exe.md)|Visual Studio 'Yu güvenli modda başlatır. Bu anahtar yalnızca varsayılan ortamı, varsayılan Hizmetleri ve üçüncü taraf paketlerin sevk edilen sürümlerini yükler.<br /><br /> Bu anahtar bağımsız değişken almaz.|
|[/UseEnv](useenv-devenv-exe.md)|IDE 'nin C++ derlemesi için PATH, ıNCLUDE, LıBPATH ve LIB ortam değişkenlerini kullanmasına neden olur. Bu anahtar, C++ iş yüküne **sahip masaüstü geliştirmeyle** birlikte yüklenir. Daha fazla bilgi için bkz. [komut satırı derlemeleri Için yolu ve ortam değişkenlerini ayarlama](/cpp/build/setting-the-path-and-environment-variables-for-command-line-builds).|

Aşağıdaki komut satırı anahtarları IDE 'yi görüntülemez.

|Komut satırı anahtarı|Açıklama|
| - |-----------------|
|[/?](q-devenv-exe.md)|`devenv` **Komut istemi penceresinde**anahtarlar için yardımı görüntüler.<br /><br /> Bu anahtar bağımsız değişken almaz.|
|[/Build](build-devenv-exe.md)|Belirtilen çözümü veya projeyi belirtilen çözümün yapılandırmasına göre oluşturur.<br /><br /> `devenv mysln.sln /build`|
|[/Clean](clean-devenv-exe.md)|Kaynak dosyalarını etkilemeden derleme komutu tarafından oluşturulan tüm dosyaları siler.<br /><br /> `devenv mysln.sln /clean`|
|[/Deploy](deploy-devenv-exe.md)|Çözümü, çözümün yapılandırmasına göre, dağıtım için gerekli dosyalarla birlikte oluşturur.<br /><br /> `devenv mysln.sln /deploy`|
|[/Out](out-devenv-exe.md)|Oluştururken hata alacak bir dosya belirtmenizi sağlar.<br /><br /> `devenv mysln.sln /build Debug /out log.txt`|
|[/Project](project-devenv-exe.md)|Derlenecek, temizleyen veya dağıtılacak proje. `/Build`Bu anahtarı yalnızca `/Rebuild`, `/Clean`, veya `/Deploy` anahtarını de sağladıysanız kullanabilirsiniz.<br /><br /> `devenv mysln.sln /build Debug /project proj1`|
|[/ProjectConfig](projectconfig-devenv-exe.md)|Derlemek veya dağıtmak için proje yapılandırmasını belirtir. Bu anahtarı yalnızca `/Project` anahtarı da sağladıysanız kullanabilirsiniz.<br /><br /> `devenv mysln.sln /build Release /project proj1 /projectconfig Release`|
|[/Rebuild](rebuild-devenv-exe.md)|Belirtilen çözümü veya projeyi temizler ve belirtilen çözümün yapılandırmasına göre oluşturur.<br /><br /> `devenv mysln.sln /rebuild`|
|[/Upgrade](upgrade-devenv-exe.md)|Belirtilen çözüm dosyasını ve tüm proje dosyalarını veya belirtilen proje dosyasını, bu dosyalar için geçerli Visual Studio biçimlerine yükseltir.<br /><br /> `devenv mysln.sln /upgrade`|

## <a name="see-also"></a>Ayrıca bkz.

- [Genel, Ortam, Seçenekler İletişim Kutusu](general-environment-options-dialog-box.md)
- [VSPackage geliştirmesi için Devenv komut satırı anahtarları](../../extensibility/devenv-command-line-switches-for-vspackage-development.md)
