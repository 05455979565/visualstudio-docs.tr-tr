---
title: VSCT derleyici komut satırı bayrakları | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- VSCT files, compiling
- command-table file compilation (VSCT files)
ms.assetid: 9dc6c33f-e6cf-4cf2-9b05-e8f7bfac1cfb
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 19ebf1713c2a0d42b1269befa3bea28d4dc0309b
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42690701"
---
# <a name="vsct-compiler-command-line-flags"></a>VSCT Derleyici Komut Satırı Bayrakları
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [VSCT derleyici komut satırı bayrakları](https://docs.microsoft.com/visualstudio/extensibility/internals/vsct-compiler-command-line-flags).  
  
Visual Studio komut tablosu (VSCT) derleyici .vsct dosyaları başarılı derlenmesini sağlamak için komut satırı anahtarları sağlar.  
  
## <a name="command-line-parameters"></a>Komut satırı parametreleri  
 Temel VSCT Yardım görüntülemek için bir [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] **komut** penceresinde gidin *Visual Studio SDK yükleme yolunu*\VisualStudioIntegration\Tools\Bin\ klasörü ve türü:  
  
```  
vsct /?  
```  
  
 Bu döndürür:  
  
```  
Microsoft (R) Visual Studio (R) Command Table Compiler Version 3.00.2000  
  
Syntax: vsct <infile> [<outfile>] [-S[symbols file]] [-D<preprocessor-define>]*  
[-I<include-path>]* [-L<language>] [-E[C|H|N]:<name>]  
  
  -D    Specify any additional preprocessor defines  
  -I    Indcate what additional include paths to send to the preprocessor  
  -L    Specify the langauge to use when selecting strings  
  -E    Emit C# objects in the specified namespace for command items,  
        folowed by [L|F|H|N]:<value>  
        F = Name of the file to emit (used if -EL is provided)  
        L = Name of a language providing a CodeDOM provider  
        N = namespace (required if -EL is provided)  
        H = C++ header  
  -c    Clean build skipping dependancy checks  
  -v    Verbose output  
```  
  
> [!NOTE]
>  Karakter - (dash) ve / (eğik çizgi) komut satırı parametrelerini belirten için kabul edilen iki gösterimdir.  
  
 Kabul edilebilir bayrakları ve bunların anlamı aşağıda verilmiştir.  
  
|Anahtar|Açıklama|  
|------------|-----------------|  
|-D|Ek tanımlı simgeleri belirtin.|  
|-I|Ek dosya başvuruları çözümlenirken kullanılacak yol eklemeyi gösterir.|  
|-L|Belirtin <xref:System.Globalization.CultureInfo> kültür adı, örneğin "en-US".|  
|-E|C# nesnelerini ardından komutu öğeleri için belirtilen ad alanında Yayımla [C&#124;H&#124;N]:*filename*nerede C C#, H = C++ üst bilgi, N = ad alanı =. Ad alanı, C# için gereklidir.|  
|-v|Ayrıntılı çıkış.|  
  
 -L anahtar dizeler için karşılık gelen ikili .cto dosyasını oluşturmak için bir grup seçmek için derleyiciye belirtilen <xref:System.Globalization.CultureInfo> kültür adı. Bir veya daha fazla dil özniteliğinde belirtilen kültür adı eşleşmelidir [Strings öğesi](../../extensibility/strings-element.md) .vsct dosyası içinde. Strings öğesi hiçbir dil özniteliği varsa, içeren uyarıdan devralınır [CommandTable öğesi](../../extensibility/commandtable-element.md).  
  
 .Vsct dosyası birden çok dize öğesi olabilir ve her farklı bir dil özniteliği olabilir. Genelleştirme, birden çok kez VSCT derleyici çalıştıran ve her bir kültür adı için -M anahtarı değiştirerek elde edilir.  
  
 Dizeleri herhangi bir öğenin dil özniteliği -L anahtar tarafından belirtilen kültür adı ile eşleşmiyorsa, derleyici dil ve bölge eşleşecek şekilde çalışacaktır. Örneğin, "en-US" bulunamazsa derleyici "en" Bunun yerine çalışacaktır. Bu başarısız olursa, işletim sisteminin geçerli kültürü çalışacaktır. Bu başarısız olursa, bulduğu ilk olan Strings öğesi derlenir.  
  
 -E anahtar, komut tablosu tarafından kullanılan simgeler içeren C stili bir başlık dosyası yayma ya da komut simgelerinin nesneleri içeren bir C# dosyası yaymak için kullanılabilir.  
  
 -D ve – anahtarları aynı ada sahip Cl.exe C önişlemcisi bayrakları sözdizimi vardır. – D X = Y biçimi tanımları XML tabanlı genişletilmesi için kullanılan \<tanımlanan > içinde testleri `Condition` öznitelikleri. – Yolları dahil miyim çözümlemek için kullanılan \<Ekle >, \<Extern > ve \<bit eşlem > dosya başvuruları. Daha fazla bilgi için [VSCT XML Şeması Başvurusu](../../extensibility/vsct-xml-schema-reference.md).  
  
 VSCT derleyici, ayrıca önceden oluşturulmuş bir ikili dosya uygulayamaz. Bunu yapmak için ikili dosya kaynağı \<infile >.   İkili dosya VSCT derleyici tarafından üretilmişse, simge zaten eklenmiş olacaktır ve sembolik adları ile çıktı oluşturur bir \<sembolleri > çıkış bölümü. İkili CTC derleyici tarafından üretilmişse, çıkış gerçek GUID'leri ve kimlikleri içerir. Ctc.exe geçerli sürümleri tarafından üretilen *.ctsym dosya ikili giriş dosyasıyla aynı klasörde ise sembolleri bu dosyasından yüklenen ve çıktısı için kullanılacak.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio komut tablosu (. Vsct) dosyaları](../../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)   
 [VSCT XML Şeması Başvurusu](../../extensibility/vsct-xml-schema-reference.md)   
 [VSPackage’ların Kullanıcı Arabirimi Öğeleri Eklemesi](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)

