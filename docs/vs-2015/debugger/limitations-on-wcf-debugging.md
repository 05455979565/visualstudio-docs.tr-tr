---
title: WCE hata ayıklamasında sınırlamalar | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- debugging, WCF
- WCF, debugging limitations
ms.assetid: 8e0333c4-1ddc-4abe-8f1c-d19bf6a2a07a
caps.latest.revision: 33
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 3faa57a0a2ca413898364c2d4ad1891df85f1ce8
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "68176808"
---
# <a name="limitations-on-wcf-debugging"></a>WCE Hata Ayıklamasında Sınırlamalar
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bir WCF Hizmeti hatasını ayıklamaya başlayabilmeniz için üç yol vardır:  
  
- Bir hizmeti çağıran bir istemci işlemi hata ayıklama. Hata ayıklama adımlarında hizmete. Hizmet istemci uygulamanızı aynı çözümde olması gerekmez.  
  
- Bir hizmete bir istekte bir istemci işlemi hata ayıklama. Hizmet, çözümünüzün bir parçası olmalıdır.  
  
- Kullandığınız **iliştirme** çalışmakta olan bir servise bağlamak için. Hata ayıklama, hizmet içinde başlar.  
  
  Bu konuda, bu senaryolara sınırlamaları açıklanmaktadır.  
  
## <a name="limitations-on-stepping-into-a-service"></a>Bir hizmette Adımlama sınırlamaları  
 Bir istemci uygulamalarında hata ayıklaması yaptığınız bir hizmette adımlamak için aşağıdaki koşullar karşılanmalıdır:  
  
- İstemci, bir zaman uyumlu istemci nesnesini kullanarak hizmet çağırmanız gerekir.  
  
- Sözleşme işlemi, tek yönlü olamaz.  
  
- Zaman uyumsuz sunucusuysa, hizmet içinde kod çalıştırılıyorken tam çağrı yığınını görüntüleyemezsiniz.  
  
- Hata ayıklama app.config veya Web.config dosyasında aşağıdaki kod ile etkinleştirilmesi gerekir:  
  
    ```  
    <system.web>  
      <compilation debug="true" />  
    </system.web>  
    ```  
  
     Bu kod, yalnızca bir kez eklenmesi gerekir. Bu kodu kullanarak hizmete ekleme .config dosyasını düzenleyerek veya ekleyebilirsiniz **iliştirme**. Kullanırken **iliştirme** bir hizmette hata ayıklama kodu otomatik olarak .config dosyasına eklenir. Bundan sonra hata ayıklama ve .config dosyasını düzenlemek zorunda kalmadan hizmette adım.  
  
## <a name="limitations-on-stepping-out-of-a-service"></a>Bir hizmet dışı Adımlama sınırlamaları  
 Bir hizmeti ve istemcisine Adımlama bir hizmette atlamak için açıklanan onunla aynı sınırlamalara sahiptir. Ayrıca, hata ayıklayıcı istemciye bağlı olması gerekir. Bir istemci ve hizmet adımla ayıklıyorsanız, hata ayıklayıcı hizmete iliştirilmiş olarak kalır. Olup kullanarak istemci başlatıldı böyle **hata ayıklamayı Başlat** veya istemciye kullanarak bağlı **iliştirme**. Hizmete ekleyerek hata ayıklama başladıysa, hata ayıklayıcı istemciye henüz eklenmemiş. Bu durumda, hizmet dışına adım ve istemciye varsa, ilk kullanmalısınız **iliştirme** istemciye el ile iliştirilebilir.  
  
## <a name="limitations-on-automatic-attach-to-a-service"></a>Bir hizmete otomatik sınırlamalar ekleme  
 Bir hizmete otomatik olarak ekleme, aşağıdaki sınırlamalara sahiptir:  
  
- Hizmetin bir parçası olması [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] ayıkladığınız çözüm.  
  
- Hizmetin barındırılması gerekir. Bir Web sitesi projesi (dosya sistemi ve HTTP), Web uygulama projesi (dosya sistemi ve HTTP) veya WCF hizmet kitaplığı projesi parçası olabilir. WCF hizmet kitaplığı projeleri hizmet kitaplıkları veya iş akışı hizmet kitaplığı olabilir.  
  
- Bir WCF istemciden hizmete çağrılması gerekir.  
  
- Hata ayıklama app.config veya Web.config dosyasında aşağıdaki kod ile etkinleştirilmesi gerekir:  
  
    ```  
    <system.web>  
      <compilation debug="true" />  
    <system.web>  
    ```  
  
## <a name="self-hosting"></a>Kendi kendine barındırma  
 A *kendi kendini barındıran hizmete* WCF hizmet konağı IIS içinde çalışmaz bir WCF hizmeti veya [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] geliştirme sunucusu. Şirket içinde barındırılan hizmetinde hata ayıklama hakkında daha fazla bilgi için bkz: [nasıl yapılır: Kendini barındıran WCF hizmetinde hata ayıklama](../debugger/how-to-debug-a-self-hosted-wcf-service.md).  
  
## <a name="self-hosting"></a>Kendi kendine barındırma  
 Hata ayıklamayı etkinleştirmek için [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] 3.0 veya 3.5 uygulamaları [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] önce 3.0 veya 3.5 yüklenmelidir [!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)] yüklenir. Varsa [!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)] önce yüklü [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] 3.0 veya 3.5, hata oluşursa hata ayıklamayı denediğinizde bir [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] 3.0 veya 3.5 uygulama. Hata iletisidir "için otomatik olarak sunucuda oturum adım." Bu sorunu gidermek için Windows kullanın **Denetim Masası**, **programlar ve Özellikler** onarmak için [!INCLUDE[vs_dev10_long](../includes/vs-dev10-long-md.md)] yükleme.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [WCF hizmetlerinde hata ayıklama](../debugger/debugging-wcf-services.md)   
 [Nasıl yapılır: Kendini Barındıran WCF Hizmetinde Hata Ayıklama](../debugger/how-to-debug-a-self-hosted-wcf-service.md)
