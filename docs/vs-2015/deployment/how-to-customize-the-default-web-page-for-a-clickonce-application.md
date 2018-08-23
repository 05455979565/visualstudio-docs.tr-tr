---
title: 'Nasıl yapılır: ClickOnce uygulaması için varsayılan Web sayfasını özelleştirme | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-deployment
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- Publish.htm Web page
- ClickOnce deployment default Web page
- deploying applications [ClickOnce], publishing
- publishing, ClickOnce
ms.assetid: 418de18c-bee9-4f24-9cd9-0252d175070d
caps.latest.revision: 16
author: mikejo5000
ms.author: mikejo
manager: wpickett
ms.openlocfilehash: bae699d0425f622f81ca14427934271b8d45eefb
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42687839"
---
# <a name="how-to-customize-the-default-web-page-for-a-clickonce-application"></a>Nasıl yapılır: ClickOnce Uygulaması için Varsayılan Web Sayfasını Özelleştirme
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [nasıl yapılır: ClickOnce uygulaması için varsayılan Web sayfasını özelleştirme](https://docs.microsoft.com/visualstudio/deployment/how-to-customize-the-default-web-page-for-a-clickonce-application).  
  
ClickOnce uygulaması için Web yayımlama sırasında bir Web sayfası otomatik olarak oluşturulur ve birlikte uygulamayı yayınladınız. Varsayılan sayfa adı uygulama ve uygulama yükleme, önkoşulları yükleyin veya MSDN Yardımı'na erişmek için bağlantılar içerir.  
  
> [!NOTE]
>  Sayfada gördüğünüz gerçek bağlantıları burada sayfası görüntülendiğinde bilgisayar ve hangi bağlıdır Önkoşullar dahil.  
  
 Publish.htm Web sayfası için varsayılan adıdır; adı değiştirebilirsiniz **Proje Tasarımcısı**. Daha fazla bilgi için [nasıl yapılır: ClickOnce uygulaması için bir yayımlama sayfası belirtme](../deployment/how-to-specify-a-publish-page-for-a-clickonce-application.md).  
  
 Publish.htm Web sayfası, yalnızca daha yeni bir sürümü algılanırsa yayımlanır.  
  
> [!NOTE]
>  Yaptığınız değişiklikler, **Yayımla** Publish.htm sayfası, bir özel durum ayarlarını etkilemez: başlangıçta yayımladıktan sonra önkoşulları ekleyip, Önkoşullar listesinde artık doğru olacaktır. Değişiklikleri yansıtacak şekilde önkoşul bağlantı metnini düzenlemek gerekir.  
  
### <a name="to-customize-the-publish-web-page"></a>Yayımla Web sayfasını özelleştirme  
  
1.  Bir Web konumuna ClickOnce uygulamanızı yayımlayın. Daha fazla bilgi için [nasıl yapılır: yayımlama sihirbazını kullanarak ClickOnce uygulaması yayımlama](../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md).  
  
2.  Visual Web Designer veya başka bir HTML düzenleyicisi, Web sunucusunda Publish.htm dosyasını açın.  
  
3.  İstediğiniz gibi sayfayı özelleştirmek ve kaydedin.  
  
4.  İsteğe bağlı. Visual Studio özelleştirilmiş Yayımla Web sayfanızın üzerine yazmasını engellemek için işareti kaldırın **sonra dağıtım web sayfasını otomatik olarak üretmek her yayımlama** Yayımlama Seçenekleri iletişim kutusundaki.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ClickOnce güvenliği ve dağıtımı](../deployment/clickonce-security-and-deployment.md)   
 [ClickOnce uygulamalarını yayımlama](../deployment/publishing-clickonce-applications.md)   
 [Nasıl yapılır: ClickOnce uygulamasıyla Önkoşulları Yükleme](../deployment/how-to-install-prerequisites-with-a-clickonce-application.md)   
 [Nasıl yapılır: ClickOnce Uygulaması için bir Yayımlama Sayfası Belirtme](../deployment/how-to-specify-a-publish-page-for-a-clickonce-application.md)



