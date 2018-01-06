---
title: "Visual Studio komut diğer adları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- aliases, Visual Studio commands
- Visual Studio, commands
- predefined command aliases
- commands, aliases
- Visual Studio commands
- pre-defined command aliases
- command aliases
ms.assetid: de8bb378-8c1c-4087-a9a5-537fa8314c19
caps.latest.revision: "17"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 48e849df1cb918682176befa25c688fe7b436460
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="visual-studio-command-aliases"></a>Visual Studio Komut Diğer Adları
Diğer adlar bir komuta girmek için bir yol sağlamak **Bul/komut** kutusunu veya **komutu** komutu yürütmek için gereken metin kısaltmayı tarafından penceresi. Örneğin, girmek yerine `>File.OpenFile` görüntülemek için **açık dosya** iletişim kutusunda, önceden tanımlanmış diğer kullanabilirsiniz `>of`.  
  
 Tür `alias` içinde **komutu**geçerli diğer adlar ve tanımları listesini görüntülemek için penceresi. Tür `>cls` içeriğini temizlemek için **komutu** penceresi. Belirli bir komut için bir diğer ad görmek istiyorsanız, yazın `alias <command name>`.  
  
 Visual Studio komutları biri için kendi diğer adı (veya ile bağımsız değişkenler olmadan) kolayca oluşturabilirsiniz. Örneğin, diğer ad sözdizimi `File.NewFile MyFile.txt` olan `alias MyAlias File.NewFile MyFile.txt`. Diğer adlarıyla birini silin`alias <alias name> /delete`  
  
 Aşağıdaki tabloda önceden tanımlanmış Visual Studio komut diğer adları listesini içerir. Bazı komut adları birden fazla önceden tanımlanmış diğer adı vardır. Komut adlarının doğru sözdizimi, bağımsız değişkenleri ve bu komutları anahtarları açıklayan ayrıntılı konularını görüntülemek için aşağıdaki bağlantıları tıklatın.  
  
|Komut adı|Alias|Tam adı|  
|------------------|-----------|-------------------|  
|[Yazdır Komutu](../../ide/reference/print-command.md)|?|Debug.Print|  
|[Hızlı Bakış Komutu](../../ide/reference/quick-watch-command.md)|??|Debug.Quickwatch|  
|Yeni Proje Ekle|AddProj|File.AddNewProject|  
|[Diğer Ad Komutu](../../ide/reference/alias-command.md)|Alias|Tools.Alias|  
|Otomatik değişkenler penceresi|Otomatik değişkenler|Debug.Autos|  
|Kesme Noktaları penceresi|bl'yi denetlemeye|Debug.Breakpoints|  
|Kesme|BP|Debug.ToggleBreakPoint|  
|Çağrı Yığını penceresi|Çağrı yığını|Debug.CallStack|  
|Yer işaretleri temizleyin|ClearBook|Edit.ClearBookmarks|  
|Close|Close|File.Close|  
|Tüm belgeleri kapatma|CloseAll|Window.CloseAllDocuments|  
|Tümünü temizle|CLS|Edit.ClearAll|  
|Komut modu|Cmd|View.CommandWindow|  
|Görünümü Kodu|kod|View.ViewCode|  
|[Belleği Listele Komutu](../../ide/reference/list-memory-command.md)|d|Debug.ListMemory|  
|[Liste belleği komutu](../../ide/reference/list-memory-command.md) ANSI olarak|da|Debug.ListMemory /Ansi|  
|[Liste belleği komutu](../../ide/reference/list-memory-command.md) bir bayt biçimi|DB|Debug.ListMemory /Format:OneByte|  
|[Liste belleği komutu](../../ide/reference/list-memory-command.md) dört bayt biçiminde ANSI olarak|DC|Debug.ListMemory /Format:FourBytes /Ansi|  
|[Liste belleği komutu](../../ide/reference/list-memory-command.md) dört bayt biçimi|Ekle|Debug.ListMemory /Format:FourBytes|  
|BOL'ye Sil|DelBOL|Edit.DeleteToBOL|  
|EOL için Sil|DelEOL|Edit.DeleteToEOL|  
|Yatay boşluk Sil|DelHSp|Edit.DeleteHorizontalWhitespace|  
|Görünüm Tasarımcısı|tasarımcı|View.ViewDesigner|  
|[Liste belleği komutu](../../ide/reference/list-memory-command.md) Float biçimi|DF|Debug.ListMemory/Format:Float|  
|Ayrıştırma penceresi|dısasm|Debug.Disassembly|  
|[Liste belleği komutu](../../ide/reference/list-memory-command.md) sekiz bayt biçimi|dq|Debug.ListMemory /Format:EightBytes|  
|[Liste belleği komutu](../../ide/reference/list-memory-command.md) Unicode olarak|DU|Debug.ListMemory / Unicode|  
|[Deyimi Değerlendir Komutu](../../ide/reference/evaluate-statement-command.md)|Değerlendirme sürümü|Debug.EvaluateStatement|  
|Çık|Çık|File.Exit|  
|Biçim Seçimi|biçim|Edit.FormatSelection|  
|Tam ekran|Tam ekran|View.FullScreen|  
|[Başlat Komutu](../../ide/reference/start-command.md)|G|Debug.Start|  
|[Git Komutu](../../ide/reference/go-to-command.md)|GotoLn|Edit.GoTo|  
|Ayraca gidin|GotoBrace|Edit.GotoBrace|  
|F1Help|Yardım|Help.F1Help|  
|Anlık mod|immed|Tools.ImmediateMode|  
|Dosya metin olarak Ekle|Insertfıle|Edit.InsertFileAsText|  
|[Çağrı Yığınını Listele Komutu](../../ide/reference/list-call-stack-command.md)|KB|Debug.ListCallStack|  
|Küçük harf olun|LCase|Edit.MakeLowercase|  
|Satır kesme|LineCut|Edit.LineCut|  
|Satırı Sil|LineDel|Edit.LineDelete|  
|Üyeleri Listeleme|ListMembers|Edit.ListMembers|  
|Yerel öğeler penceresi|Yerel öğeler|Debug.Locals|  
|[Komut Penceresi Çıktısı Günlüğü Tut Komutu](../../ide/reference/log-command-window-output-command.md)|Günlük|Tools.LogCommandWindowOutput|  
|Komut penceresinde işaret modu|işareti|Tools.CommandWindowMarkMode|  
|Bellek penceresi|Bellek Memory1|Debug.Memory1|  
|Bellek penceresi 2|Memory2|Debug.Memory2|  
|Bellek penceresi 3|Memory3|Debug.Memory3|  
|Bellek penceresi 4|Belleği4|Debug.Memory4|  
|[Sayı Tabanını Ayarla Komutu](../../ide/reference/set-radix-command.md)|n|Debug.SetRadix|  
|[ShowWebBrowser Komutu](../../ide/reference/showwebbrowser-command.md)|NAV gidin|View.ShowWebBrowser|  
|Sonraki Yer İşareti|NextBook|Edit.NextBookmark|  
|[Yeni Dosya Komutu](../../ide/reference/new-file-command.md)|nf|File.NewFile|  
|Yeni Proje|NP NewProj|File.NewProject|  
|[Dosya Aç Komutu](../../ide/reference/open-file-command.md)|Açma|File.OpenFile|  
|[Proje Aç Komutu](../../ide/reference/open-project-command.md)|OP|File.OpenProject|  
|Tanımları/durdurma anahat oluşturma için Daralt|OutlineDefs StopOutlining|Edit.CollapsetoDefinitions|  
|Adımlama|P|Debug.StepOver|  
|Parametre bilgileri|Paramınfo|Edit.ParameterInfo|  
|Dışarı Adım|pr|Debug.StepOut|  
|Önceki Yer İşareti|PrevBook|Edit.PreviousBookmark|  
|Dosya Yazdır|Yazdırma|File.Print|  
|Özellikler Penceresi|özellik|View.PropertiesWindow|  
|Durdur|q|Debug.StopDebugging|  
|Yinele|Yinele|Edit.Redo|  
|Yazmaçlar penceresi|yazmaçlar|Debug.Registers|  
|İmleci çalıştırın|RTC|Debug.RunToCursor|  
|Seçili öğeleri Kaydet|Kaydet|File.SaveSelectedItems|  
|Tümünü Kaydet|SaveAll|File.SaveAll|  
|Farklı Kaydet|Farklı Kaydet|File.SaveSelectedItemsAs|  
|[Kabuk Komutu](../../ide/reference/shell-command.md)|kabuk|Tools.Shell|  
|Dosyalarda Bul Durdur|StopFind|Edit.findınfiles/stop|  
|Bağlantı değiştirme|SwapAnchor|Edit.SwapAnchor|  
|Girme|t|Debug.StepInto|  
|Seçim Sekmelere ayırma|sekmelere ayırma|Edit.TabifySelection|  
|Tasklist penceresi|TaskList|View.TaskList|  
|İş Parçacıkları penceresi|İş Parçacıkları|Debug.Threads|  
|Yatay Döşe|TileH|Window.TileHorizontally|  
|Dikey Döşe|TileV|Window.TileVertically|  
|Yer İşaretini Değiştir|ToggleBook|Edit.ToggleBookmark|  
|Araç penceresi|araç kutusu|View.Toolbox|  
|[Ayrıştırılmış Kodu Listele Komutu](../../ide/reference/list-disassembly-command.md)|u|Debug.ListDisassembly|  
|Büyük Harf Yap|UCase|Edit.MakeUppercase|  
|Geri alma|Geri alma|Edit.Undo|  
|Seçim untabify|Untabify|Edit.UntabifySelection|  
|Gözcü penceresi|İzleme|Debug.WatchN|  
|Sözcük kaydırmayı değiştirme|WordWrap|Edit.ToggleWordWrap|  
|Liste işlemleri|&#124;|Debug.ListProcesses|  
|[İş Parçacıklarını Listele Komutu](../../ide/reference/list-threads-command.md)|~ ~ * k ~\*kb|Debug.ListThreads Debug.ListTheads /AllThreads|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio komutları](../../ide/reference/visual-studio-commands.md)   
 [Komut penceresi](../../ide/reference/command-window.md)   
 [Bul/komut kutusu](../../ide/find-command-box.md)