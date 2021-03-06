---
title: VS kabuğuna VSPackage dosya konumunu belirtme | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- managed VSPackages, file location
- VSPackages, managed package file location
ms.assetid: beb8607a-4183-4ed2-9ac8-7527f11513b1
caps.latest.revision: 21
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: c0662bfe22b4c78bb754bbac2fbfdd281a4a7bce
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "63408506"
---
# <a name="specifying-vspackage-file-location-to-the-vs-shell"></a>VS Kabuğuna VSPackage Dosya Konumunu Belirtme
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] VSPackage'ı yüklemek için DLL derlemeyi bulabilir olması gerekir. Bunun çeşitli yollarla aşağıdaki tabloda açıklandığı gibi bulabilirsiniz.  
  
|Yöntem|Açıklama|  
|------------|-----------------|  
|Kod temeli kayıt defteri anahtarı kullanın.|Kod temeli anahtar yönlendirmek için kullanılabilir [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] herhangi bir tam dosya yolundan VSPackage derlemesi yüklenemiyor. Anahtarın değeri, DLL dosyasının yolu olmalıdır. Bu sahip için en iyi yoludur [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] , paket derlemesi yüklenemiyor. Bu teknik bazen "CodeBase/özel yükleme dizini teknik." adlandırılır Kayıt sırasında kod tabanının değeri kayıt öznitelik sınıfları bir örneği üzerinden geçirilir <xref:Microsoft.VisualStudio.Shell.RegistrationAttribute.RegistrationContext> türü.|  
|DLL içine yerleştirin **PrivateAssemblies** dizin.|Derlemede yerleştirin **PrivateAssemblies** alt [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] dizin. Derlemeleri bulunan **PrivateAssemblies** otomatik olarak algılanır ancak görünmez **Add References** iletişim kutusu. Arasındaki fark **PrivateAssemblies** ve **Publicassembly'ler** derlemelere olan içinde **Publicassembly'ler** listelenen **başvuruları ekleme**  iletişim kutusu. "CodeBase/özel yükleme dizini" teknik kullanmayı seçtiğiniz sonra içine yüklemelisiniz **PrivateAssemblies** dizin.|  
|Tanımlayıcı adlı bütünleştirilmiş kod ve derleme kayıt defteri anahtarını kullanın.|Derleme anahtar açıkça yönlendirmek için kullanılabilir [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] VSPackage derleme adında güçlü yüklenemedi. Anahtarın değeri, derlemenin tanımlayıcı adı olmalıdır.|  
|DLL içine yerleştirin **Publicassembly'ler** dizin.|Son olarak, derlemeyi ayrıca içine yerleştirilebilir **Publicassembly'ler** alt. Derlemeleri bulunan **Publicassembly'ler** otomatik olarak algılanır ve ayrıca görünür **Add References** iletişim kutusunda [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].<br /><br /> VSPackage derlemeler yalnızca yerleştirilmelidir **Publicassembly'ler** bunlar içeriyorsa, dizin yönetilen bileşenlerin diğer VSPackage geliştiriciler tarafından kullanılabilmeleri için tasarlanmıştır. Çoğu derleme, bu ölçütü karşılamıyor.|  
  
> [!NOTE]
> Tanımlayıcı adlı, imzalı derlemeler tüm bağımlı bütünleştirilmiş kodlarınızı için kullanın. Bu derlemeler de dizininizin veya genel derleme önbelleği (GAC) yüklenmesi gerekir. Bu, zayıf adı bağlaması olarak bilinen aynı temel dosya adı olan derlemeler çakışıyor karşı korur.
