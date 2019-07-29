---
title: Visual Studio + GitHub kurumsal demeti | Microsoft Docs
author: evanwindom
ms.author: lank
manager: lank
ms.date: 07/28/2019
ms.topic: conceptual
description: Visual Studio + GitHub kurumsal paketteki abonelikleri yönetme
ms.openlocfilehash: 0f297eac1d6b2bc5fe322be305fab7f268f3d041
ms.sourcegitcommit: ce1ab8a25c66a83e60eab80ed8e1596fe66dd85c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/29/2019
ms.locfileid: "68605392"
---
# <a name="manage-visual-studio-subscriptions-with-github-enterprise"></a>GitHub Enterprise ile Visual Studio aboneliklerini yönetme
Microsoft ile kurumsal anlaşma (EA) olan müşteriler, Visual Studio Standard abonelikleri ve GitHub Enterprise 'ı birlikte getiren yeni bir abonelik paketi satın almaya uygundur. Visual Studio abonelerinin GitHub Enterprise 'ı edinmenin kolay ve ekonomik bir yoludur. 

Kuruluşunuz GitHub Enterprise ile Visual Studio abonelikleri satın aldığında, bunlar iki bölümden sağlanır ve yönetilir.

## <a name="manage-visual-studio-subscriptions"></a>Visual Studio aboneliklerini yönetme
Kuruluşunuz GitHub Enterprise ile Visual Studio abonelikleri satın aldığında, aboneliklerin Visual Studio bölümü hemen sağlanır ve abonelikler Visual Studio ['da atama ve yönetim için kullanılabilir Abonelikler yönetim](https://manage.visualstudio.com) portalı. 

Abonelikleri yönetme hakkında daha fazla bilgi için şu konulara bakın:
- [Yönetici Portalı’nı Kullanma](using-admin-portal.md)
- [Abonelikleri Atama](assign-license.md)
- [Abonelikleri Düzenleme](edit-license.md)
- [Abonelikleri Silme](delete-license.md)
- [Fazla Yüklemeler](handle-overclaimed-license.md)

> [!Important]
> GitHub Enterprise ile Visual Studio abonelikleri, Visual Studio abonelik yöneticileri tarafından atanmışsa ve bu aboneliklerin hiç satın alınmadıysa, bu abonelikler kuruluş içindeki GitHub Enterprise Admins 'e görünür olmayacaktır. GitHub Enterprise aboneliklerinin görünebildiğinden emin olmak için GitHub Enterprise veya Visual Studio Enterprise GitHub Enterprise aboneliğiyle **en az bir** Visual Studio Professional içeren bir satın alma, abonelikler ilk kez yapılmalıdır atanır.  
>
> Bu, atanan her GitHub aboneliğine ilişkin lisans gereksinimleriyle uyumlu kalmak için yönetim portalı 'nda atanan GitHub aboneliğine sahip bir Visual Studio olduğundan emin olmak için müşterinin sorumluluğundadır. aboneliğiniz.

## <a name="manage-github-enterprise-subscriptions"></a>GitHub Enterprise aboneliklerini yönetme
GitHub Enterprise abonelikleri satın alındığında, GitHub 'a erişecek ve yöneticileri tanımlayan kuruluşları oluşturmaya ve yapılandırmaya yardımcı olmak üzere müşteriler ile GitHub iş ortakları yapılır.  Bu Yöneticiler daha sonra yöneticiler olarak ayarlandıklarından bir bildirim alır.  

Bu işlem daha karmaşık olduğundan, kuruluşlar ve yöneticilerin tam olarak ayarlanması için abonelikler satın alındıktan sonra birkaç gün sürebilir.

GitHub, bulut tabanlı GitHub.com ya da şirket içi GitHub Enterprise Server olarak kullanılabilir.  İki sürümü yönetmek için süreçler farklılık gösterir.  GitHub, GitHub Enterprise aboneliklerini yönetmenize yardımcı olmak için çeşitli yardım konuları ve yönetici kılavuzlarını sağlar.  Aşağıdaki seçili konulara bağlantılar sağladık.  

### <a name="githubcom"></a>GitHub.com 
GitHub.com yönetimi hakkında daha fazla bilgi için lütfen [GitHub yardımı](https://help.github.com/en)'nda aşağıdaki konulara göz atın.
- [Yardım konularının tam listesi](https://help.github.com/en)
- [Kuruluşunuzdaki üyelikleri yönetme](https://help.github.com/en/articles/managing-membership-in-your-organization)
> - [Kullanıcıları kuruluşunuza katmak üzere davet etme](https://help.github.com/en/articles/inviting-users-to-join-your-organization)
> - [Kullanıcıları ekiplerden/kuruluşlardan kaldırma](https://help.github.com/en/articles/removing-a-member-from-your-organization)
> - [Kuruluşunuzun eski bir üyesini yeniden belirten](https://help.github.com/en/articles/reinstating-a-former-member-of-your-organization)
- [Rolleri kullanarak erişimi yönetme](https://help.github.com/en/articles/managing-peoples-access-to-your-organization-with-roles)
- [Kullanıcıları ekiplere düzenleme](https://help.github.com/en/articles/organizing-members-into-teams)
- [Kuruluşunuzun depolarına erişimi yönetme](https://help.github.com/en/articles/managing-access-to-your-organizations-repositories)

### <a name="github-enterprise-server"></a>GitHub Enterprise Server
GitHub yardımı, soruları yanıtlamak ve kuruluşunuzun GitHub Enterprise Server uygulamasının yönetimine ilişkin ipuçları vermek için çeşitli yönetici kılavuzlarını sağlar.

- [Tüm yönetici kılavuzlarını görüntüle](https://help.github.com/en/enterprise/2.16/admin)
- [Kullanıcı Yönetimi](https://help.github.com/en/enterprise/2.16/admin/user-management)
> - [Kuruluşlar ve takımlar](https://help.github.com/en/enterprise/2.16/admin/user-management/organizations-and-teams)
> > - [Kuruluşlar oluşturma](https://help.github.com/en/enterprise/2.16/admin/user-management/creating-organizations)
> > - [Takımlar oluşturma](https://help.github.com/en/enterprise/2.16/admin/user-management/creating-teams)
> > - [Takımlara kişi ekleme](https://help.github.com/en/enterprise/2.16/admin/user-management/adding-people-to-teams)
> > - [Ekiplerden ve kuruluşlardan kişileri kaldırma](https://help.github.com/en/enterprise/2.16/admin/user-management/removing-users-from-teams-and-organizations)
> - [Kullanıcı güvenliği](https://help.github.com/en/enterprise/2.16/admin/user-management/user-security)
- [GitHub Enterprise Server 'ı yükleme ve yapılandırma](https://help.github.com/en/enterprise/2.16/admin/installation)

## <a name="support-resources"></a>Destek kaynakları
- [GitHub yardımı](https://help.github.com/en)'nda çok çeşitli GitHub konuları dizisiyle soruların yanıtlarını bulabilirsiniz.
- [GitHub topluluk forumundaki](https://github.community/)diğer GitHub kullanıcılarından yardım alın.
- Visual Studio abonelikleri için Sales, abonelikler, hesaplar ve faturalandırma konusunda yardım için Visual Studio [abonelikleri desteğiyle](https://visualstudio.microsoft.com/subscriptions/support/)görüşün.
- Visual Studio IDE, Azure DevOps Services veya diğer Visual Studio ürünleri veya hizmetleri hakkında sorularınız mı var?  [Visual Studio desteği](https://visualstudio.microsoft.com/support/)' ni ziyaret edin.
- GitHub Enterprise için [Teknik destek](https://support.microsoft.com/en-us/supportforbusiness/productselection?sapId=b77fe80f-5417-80bd-4b2a-275cf0018c24) alın.   

## <a name="next-steps"></a>Sonraki adımlar
Visual Studio aboneliklerini GitHub Enterprise ile yönetme hakkında daha fazla bilgi için Visual Studio [abonelikleri Yönetici portalı](https://visualstudio.microsoft.com/subscriptions-administration/)' na göz atın.
