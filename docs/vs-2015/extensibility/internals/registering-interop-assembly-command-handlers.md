---
title: Birlikte çalışma bütünleştirilmiş kodu komut işleyicilerini kaydetme | Microsoft Docs
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
- interop assemblies, command handlers
- command handling with interop assemblies, registering
ms.assetid: 303cd399-e29d-4ea1-8abe-5e0b59c12a0c
caps.latest.revision: 20
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 2288c1692f50e3937bbfa71502a0572a1747c976
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42684347"
---
# <a name="registering-interop-assembly-command-handlers"></a>Birlikte Çalışma Bütünleştirilmiş Kodu Komut İşleyicilerini Kaydetme
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [birlikte çalışma bütünleştirilmiş kodu komut işleyicilerini kaydetme](https://docs.microsoft.com/visualstudio/extensibility/internals/registering-interop-assembly-command-handlers).  
  
VSPackage ile kaydetmelisiniz [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] böylece tümleşik geliştirme ortamı (IDE) komutlarının düzgün bir şekilde yönlendirir.  
  
 Kayıt defterini düzenleyerek el ile veya kayıt şirketi (.rgs) dosyası kullanılarak güncelleştirilebilir. Daha fazla bilgi için [Kaydedici betikleri oluşturma](http://msdn.microsoft.com/library/cbd5024b-8061-4a71-be65-7fee90374a35).  
  
 Yönetilen paket Framework (MPF) aracılığıyla bu işlevselliği sağlar <xref:Microsoft.VisualStudio.Shell.ProvideMenuResourceAttribute> sınıfı.  
  
 [Komut tablosu biçimi başvurusu](http://msdn.microsoft.com/en-us/09e9c6ef-9863-48de-9483-d45b7b7c798f) yönetilmeyen Uydu DLL'leri UI kaynakları bulunur.  
  
## <a name="command-handler-registration-of-a-vspackage"></a>Komut işleyici VSPackage kaydı  
 Kullanıcı Arabirimi (UI) için bir işleyici olarak davranan bir VSPackage-tabanlı komutları gerektirir sonra VSPackage'ı adlı bir kayıt defteri girişi `GUID`. Bu kayıt defteri girdisi VSPackage'nın kullanıcı Arabirimi kaynak dosyası ve bu dosyaya menüsü kaynak konumunu belirtir. Kayıt defteri girdisini hkey_local_machıne\software\microsoft\visualstudio altında bulunan\\*\<sürüm >* \Menus, burada  *\<sürüm >* sürümü [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)], örneğin 9.0.  
  
> [!NOTE]
>  Kök yolu hkey_local_machıne\software\microsoft\visualstudio\\*\<sürüm >* bir alternatif ile geçersiz kılınabilir ne zaman kök [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Kabuk başlatılır. Kök yolu hakkında daha fazla bilgi için bkz: [yükleme VSPackage'ları ile Windows Installer](../../extensibility/internals/installing-vspackages-with-windows-installer.md).  
  
### <a name="the-ctmenu-resource-registry-entry"></a>CTMENU kaynak kayıt defteri girdisi  
 Kayıt defteri girdisi yapıdır:  
  
```  
HKEY_LOCAL_MACHINE\Software\VisualStudio\<Version>\  
  Menus\  
    <GUID> = <Resource Information>  
```  
  
 \<*GUID*> olan `GUID` {XXXXXX-XXXX-XXXX-XXXX-XXXXXXXXX} biçimde Vspackage'i biri.  
  
 *\<Kaynak bilgileri >* virgülle ayrılmış üç öğelerden oluşur. Sırayla bu öğeler şunlardır:  
  
 \<*Kaynak DLL yolu*>, \< *menüsü kaynak kimliği*>, \< *menü sürümü*>  
  
 Aşağıdaki tablo alanlarını açıklar \< *kaynak bilgileri*>.  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|\<*Kaynak DLL yolu*>|Bu kaynağın menü kaynağı içeren DLL tam yolunu veya bu VSPackage'nın kaynak kullanılacak DLL olduğunu belirten, boş bırakılır (VSPackage kayıtlı olduğu paketleri alt belirtildiği gibi).<br /><br /> Bu alanı boş bırakın uygulamadır.|  
|\<*Menü kaynak kimliği*>|Bu kaynak kimliği olan `CTMENU` gelen derlenmiş gibi tüm kullanıcı Arabirimi öğeleri için VSPackage'ı içeren kaynak bir [.vsct](../../extensibility/internals/visual-studio-command-table-dot-vsct-files.md) dosya.|  
|\<*Menü sürümü*>|Bir sürüm olarak kullanılan birkaç budur `CTMENU` kaynak. [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] içeriğini remerge gerekip gerekmediğini belirlemek için bu değeri kullanır `CTMENU` önbelleğinde tüm kaynakla `CTMENU` kaynakları. Bir remerge devenv Kurulum komutu yürüterek tetiklenir.<br /><br /> Bu değer başlangıçta 1 olarak verilecek ve her değişiminin artırılır `CTMENU` kaynak ve remerge gerçekleşmeden önce.|  
  
### <a name="example"></a>Örnek  
 Kaynak girdilerinin birkaç örneği aşağıda verilmiştir:  
  
```  
HKEY_LOCAL_MACHINE\Software\VisualStudio\9.0Exp\  
  Menus\  
    {019971D6-4685-11D2-B48A-0000F87572EB} = ,1, 10  
    {1b027a40-8f43-11d0-8d11-00a0c91bc942} = , 10211, 3  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [VSPackage kullanıcı arabirimi öğelerini nasıl eklenir](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)   
 [Birlikte Çalışma Bütünleştirilmiş Kodları Kullanan Komutlar ve Menüler](../../extensibility/internals/commands-and-menus-that-use-interop-assemblies.md)

