---
title: VB hata ayıklama yapılandırması için proje ayarları | Microsoft Docs
ms.custom: seodec18
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vbProjectPropertiesDebug
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- project settings [Visual Studio], debug configurations
- debug builds, project settings
- debugging [Visual Basic], debugger settings
- projects [Visual Studio], debug configurations
- project configurations, debug
- debug configurations, Visual Basic
ms.assetid: 72a8483a-af0b-4403-8b0d-ee9ad71ee435
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: bcac88c2faf1af7378ce25597789700df61648a9
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/22/2019
ms.locfileid: "72730613"
---
# <a name="project-settings-for-a-visual-basic-debug-configuration"></a>Visual Basic Hata Ayıklama Yapılandırması Proje Ayarları
Bir [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] hata ayıklama yapılandırması için proje ayarlarını, [hata ayıklama ve sürüm yapılandırmalarında](../debugger/how-to-set-debug-and-release-configurations.md)anlatıldığı gibi **Özellik sayfaları** penceresinde değiştirebilirsiniz. Aşağıdaki tablolarda, **Özellik sayfaları** penceresinde hata ayıklayıcı ile ilgili ayarların nerede bulunacağı gösterilmektedir.

> [!WARNING]
> Bu konu, UWP uygulamaları için geçerlidir. Bkz. [hata ayıklama oturumu başlatma (vb C#, C++ ve XAML)](../debugger/start-a-debugging-session-for-a-store-app-in-visual-studio-vb-csharp-cpp-and-xaml.md)

### <a name="debug-tab"></a>Hata ayıklama sekmesi

| Ayar | Açıklama |
|------------------------------| - |
| **Yapılandırma** | Uygulamayı derlemek için modu ayarlar. **Etkin (hata ayıklama)** , **hata ayıklama**, **yayın**, **Tüm yapılandırmaların**arasından seçim yapın. |
| **Başlatma eylemi** | Bu denetim grubu, hata ayıklama menüsünden Başlat ' ı seçtiğinizde gerçekleştirilecek eylemi belirtir.<br /><br /> -   **Başlangıç projesi** varsayılandır ve hata ayıklama için başlangıç projesini başlatır. <br />**dış programı başlat** -   , bir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] projesinin parçası olmayan bir programı başlatıp eklemenize olanak sağlar. Daha fazla bilgi için bkz. [çalışan Işlemlere iliştirme](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md).<br />**URL 'de -    başlangıç tarayıcısı** , bir Web uygulamasında hata ayıklamanızı sağlar. |
| **Komut satırı bağımsız değişkenleri** | Hata Ayıklanacak programın komut satırı bağımsız değişkenlerini belirtir. Komut adı, dış program Başlat bölümünde belirtilen program adıdır. Başlat eylemi başlangıç URL 'SI olarak ayarlandıysa komut satırı bağımsız değişkenleri yok sayılır. |
| **Çalışma dizini** | Hata ayıklanan programın çalışma dizinini belirtir. @No__t_0, çalışma dizini uygulamanın başlatıldığı dizindir. Geçerli yapılandırmaya bağlı olarak, varsayılan çalışma dizini \bin\Debug veya \bin\Release ' dir. |
| **Uzak makineyi kullan** | Onay kutusu seçildiğinde, uzaktan hata ayıklama etkinleştirilir. Metin kutusunda, uygulamanın hata ayıklama amacıyla çalışacağı uzak makinenin adını veya bir [msvsmon sunucu adını](../debugger/remote-debugging.md)yazabilirsiniz. Uzak makinedeki EXE konumu, derleme sekmesindeki çıkış yolu özelliği tarafından belirtilir. Konum, uzak makinede paylaşılabilir bir dizin olmalıdır. |
| **Yönetilmeyen kod hata ayıklaması** | Yönetilen uygulamanızdan yerel (yönetilmeyen) Win32 koduna yapılan çağrıların hatalarını ayıklamanızı sağlar. Bu, [!INCLUDE[vcprvc](../code-quality/includes/vcprvc_md.md)] projesindeki hata ayıklayıcı türü için karışık seçme ile aynı etkiye sahiptir. |
| **SQL Server hata ayıklama** | SQL Server veritabanı nesnelerinin hatalarını ayıklamasına izin verir. |

### <a name="compile-tab-press-advanced-compile-options-button"></a>Derle sekmesi: Gelişmiş derleme seçenekleri düğmesine basın

| Ayar | Açıklama |
|---------------------------| - |
| **İyileştirmeleri etkinleştir** | Bu seçenek işaretlenmemelidir. İyileştirme, aslında yürütülen kodun [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] görülen kaynak koddan farklı olmasına neden olur ve bu nedenle hata ayıklamayı zorlaştırır. Kod iyileştirildiğinden, Yalnızca kendi kodum hata ayıklaması sırasında semboller varsayılan olarak yüklenmez. |
| **Hata ayıklama bilgisi oluştur** | Hem hata ayıklama hem de yayın sürümlerinde varsayılan olarak tanımlanan bu ayar (/debug derleyici seçeneğine eşdeğerdir) derleme zamanında hata ayıklama bilgileri oluşturur. Hata ayıklayıcı, hata ayıklama sırasında yararlı bir biçimde değişken adlarını ve diğer bilgileri göstermek için bu bilgileri kullanır. Programınızı bu bilgi olmadan derlerseniz, hata ayıklayıcı işlevselliği sınırlı olacaktır. Daha fazla bilgi için bkz. [/Debug](/dotnet/visual-basic/reference/command-line-compiler/debug). |
| **Hata ayıklama sabiti tanımla** | Bu sembolün tanımlanması, çıkış işlevlerinin [hata ayıklama sınıfından](/dotnet/api/system.diagnostics.debug)koşullu derlemesini mümkün bir şekilde sunar. Bu sembol tanımlanmış olduğunda, hata ayıklama sınıfı yöntemleri [Çıkış penceresinde](../ide/reference/output-window.md)çıkış oluşturur. Bu sembol olmadan hata ayıklama sınıfı yöntemleri derlenmez ve hiçbir çıkış oluşturulmaz. Bu simge hata ayıklama sürümünde tanımlanmalıdır ve yayın sürümünde tanımlanmamıştır. Bu sembolün bir yayın sürümünde tanımlanması, programınızı yavaşlattığı gereksiz kodu oluşturur. |
| **Izleme sabitini tanımlama** | Bu sembolün tanımlanması, [Trace sınıfından](/dotnet/api/system.diagnostics.trace)çıkış işlevlerinin koşullu derlemesini mümkün bir şekilde sunar. Bu sembol tanımlanmış olarak, Trace class yöntemleri [Çıkış penceresinde](../ide/reference/output-window.md)çıktı oluşturur. Bu sembol olmadan, Izleme sınıfı yöntemleri derlenmez ve hiçbir Izleme çıkışı oluşturulmaz. Bu simge, hem hata ayıklama hem de yayın sürümleri için varsayılan olarak tanımlanmıştır. |

## <a name="see-also"></a>Ayrıca bkz.
- [Hata Ayıklayıcısı Ayarları ve Hazırlığı](../debugger/debugger-settings-and-preparation.md)