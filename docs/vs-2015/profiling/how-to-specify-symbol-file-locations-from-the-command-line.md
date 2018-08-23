---
title: 'Nasıl yapılır: komut satırından sembol dosyası konumlarını belirtme | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8aa067bb-e8bf-4081-aff0-cfbcf65934a0
caps.latest.revision: 16
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f482c839ffe98c7be8147bbed45fa9fda69b4c85
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42688562"
---
# <a name="how-to-specify-symbol-file-locations-from-the-command-line"></a>Nasıl yapılır: Simge Dosyası Konumlarını Komut Satırından Belirtme
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [nasıl yapılır: komut satırından sembol dosyası konumu belirtin](https://docs.microsoft.com/visualstudio/profiling/how-to-specify-symbol-file-locations-from-the-command-line).  
  
İşlev adları ve satır numaraları gibi sembol bilgilerini görüntülemek için profili oluşturulan bileşenlerin sembol (.pdb) dosyalarını ve Windows sistem dosyalarını erişim VSPerfReport komut satırı aracı gerektirir. Bir bileşen derlendiğinde sembol dosyaları oluşturulur. Daha fazla bilgi için [VSPerfReport](../profiling/vsperfreport.md). VSPerfReport sembol dosyaları için aşağıdaki konumlar otomatik olarak arar:  
  
-   Belirtilen yollar **/symbolpath** seçeneği veya **_NT_SYMBOL_PATH** ortam değişkeni.  
  
-   Burada bir bileşen derlenen tam yerel yolu.  
  
-   Profil oluşturma veri (.vsp veya .vsps) dosyasını içeren dizin.  
  
 Microsoft, çok ürünlerin, çevrimiçi bir sembol sunucusunda için .pdb dosyaları sağlar. Raporlama için kullanmakta olduğunuz bilgisayarın Internet'e bağlıysa, VSPerfReport otomatik olarak sembol bilgilerini arama ve dosyalarını yerel depoya kaydetmek için çevrimiçi bir sembol sunucusuna bağlanır.  
  
 Sembol dosyaları ve Microsoft sembol sunucusunun depolama konumu aşağıdaki yöntemlerle belirtebilirsiniz:  
  
-   Ayarlama **_NT_SYMBOL_PATH** ortam değişkeni.  
  
-   Ekleme **/symbolpath** VSPerfReport komut satırı seçeneği.  
  
 Bu yöntemlerin her ikisi de kullanabilirsiniz.  
  
> [!NOTE]
>  Varsa [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] Windows simge dosyaları büyük olasılıkla belirtilmedi için zaten bir konuma yerel bilgisayarda yüklü. Daha fazla bilgi için [nasıl yapılır: başvuru Windows sembol bilgilerini](../profiling/how-to-reference-windows-symbol-information.md). Hala VSPerfReport konumu ve bu konunun ilerleyen bölümlerinde açıklandığı sunucusu kullanmak için yapılandırmanız gerekir.  
  
## <a name="specifying-windows-symbol-files"></a>Windows sembol dosyalarını belirtme  
  
#### <a name="to-configure-the-use-of-the-windows-symbol-server"></a>Windows sembol sunucusu kullanımını yapılandırmak için  
  
1.  Gerekirse, sembol dosyaları yerel olarak depolamak için bir dizin oluşturun.  
  
2.  Ayarlamak için aşağıdaki sözdizimini kullanın **_NT_SYMBOL_PATH** ortam değişkeni veya VSPerfReport/symbolpath seçeneği:  
  
     **SRV\***  *LocalStore* **\*http://msdl.microsoft.com/downloads/symbols**  
  
     Burada *LocalStore* oluşturduğunuz yerel bir dizin yolu.  
  
## <a name="specifying-component-symbol-files"></a>Bileşen sembol dosyalarını belirtme  
 Profil oluşturma araçları, bileşenler veya profil oluşturma veri dosyasını içeren klasöre depolanan özgün konumlarına profilinde istediğiniz bileşenlerin the.pdb dosyaları arar. Bir veya daha fazla yol ekleyerek aramak için diğer konumlar belirtebilirsiniz **_NT_SYMBOL_PATH** veya **/symbolpath** seçeneği. Ayrı yollarının noktalı virgülle ayırın.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki komut satırı kümeleri **_NT_SYMBOL_PATH** ortam değişkenini Windows sembol sunucusu ve yerel dizine **C:\Symbols**.  
  
 **ayarlama _NT_SYMBOL_PATH srv =\*C:\symbols\*http://msdl.microsoft.com/downloads/symbols**  
  
 VSPerfReport komut satırını kullanarak C:\Projects\Symbols dizin arama yolunu ekler **/symbolpath** seçeneği.  
  
 **VSPerfReport***MyApp* **.exe /SymbolPath:C:\Projects\Symbols userrulesdirectory** 



