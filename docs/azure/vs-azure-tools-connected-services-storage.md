---
title: Azure depolama bağlı hizmetlerini kullanarak ekleyin | Microsoft Docs
description: Azure depolama, Visual Studio bağlı Hizmetleri Ekle iletişim kutusunu kullanarak uygulamanıza ekleme
author: ghogen
manager: douge
assetId: 521ec044-ad4b-4828-8864-01decde2e758
ms.prod: visual-studio-dev15
ms.custom: vs-azure
ms.workload: azure-vs
ms.topic: conceptual
ms.date: 03/26/2017
ms.author: ghogen
ms.openlocfilehash: a0eb93c2c6bd63fca72adc19882d556c33bf3f64
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/02/2019
ms.locfileid: "53868689"
---
# <a name="adding-azure-storage-by-using-visual-studio-connected-services"></a>Visual Studio bağlı Hizmetler'i kullanarak Azure depolama ekleme

Visual Studio ile aşağıdakilerden herhangi birini Azure Depolama'ya kullanarak bağlanabilirsiniz **bağlı hizmet Ekle** iletişim:

- C# bulut hizmeti
- .NET arka uç mobil hizmet
- ASP.NET Web sitesi veya hizmet
- ASP.NET Core hizmeti
- Azure Web işi hizmeti

Bağlı hizmet işlevselliğinin tüm gerekli başvuruları ve bağlantı kodunu projenize ekler ve yapılandırma dosyalarını uygun şekilde değiştirir.

Tamamlandıktan sonra **bağlı hizmet Ekle** iletişim kutusu otomatik olarak açıklayan belgeleri bulacağı kuyrukları, blob depolama ile çalışmaya başlamak için gereken adımları görüntüler ve tablolar.

> [!NOTE]
> Bu konu, Windows üzerinde Visual Studio için geçerlidir. Mac için Visual Studio için bkz: [Mac için Visual Studio'da Hizmetleri bağlı](/visualstudio/mac/connected-services).

## <a name="connect-to-azure-storage-using-the-connected-services-dialog"></a>Bağlı hizmetler iletişim kutusunu kullanarak Azure Depolama'ya Bağlan

1. Projenizi Visual Studio'da açın.

1. İçinde **Çözüm Gezgini**, sağ **bağlı hizmetler** düğümünün ve bağlam menüsünden ve Seç **bağlı hizmet Ekle**.

    ![Azure'ı ekleme bağlı hizmeti](./media/vs-azure-tools-connected-services-storage/IC796702.png)

1. İçinde **bağlı hizmetler** sayfasında **Azure depolama ile bulut depolama**.

    ![Azure depolama ekleme](./media/vs-azure-tools-connected-services-storage/add-azure-storage.png)

1. İçinde **Azure depolama** iletişim kutusu, mevcut bir depolama hesabını seçin ve Seç **Ekle**.

    Bir depolama hesabı oluşturmanız gerekiyorsa, sonraki adıma gidin. Aksi takdirde, 6. adıma atlayın.

    ![Mevcut depolama hesabını projeye Ekle](./media/vs-azure-tools-connected-services-storage/select-azure-storage-account.png)

1. Bir depolama hesabı oluşturmak için:

   1. Seçin **yeni depolama hesabı oluşturma** iletişim kutusunun alt kısmındaki.

   1. Doldurun **depolama hesabı oluştur** iletişim ve select **Oluştur**.

       ![Yeni Azure depolama hesabı](./media/vs-azure-tools-connected-services-storage/create-storage-account.png)

   1. Zaman **Azure depolama** iletişim kutusu görüntülendiğinde, yeni depolama hesabı listesinde görünür. Yeni depolama hesabı listesinde seçip **Ekle**.

1. Bağlı hizmet altında görünür depolama **hizmet başvuruları** projenizin düğümü.

## <a name="how-your-project-is-modified"></a>Projenizi nasıl değiştirilir

İletişim bitirdikten sonra Visual Studio başvuruları ekler ve belirli yapılandırma dosyalarını değiştirir. Belirli değişiklikleri proje türüne bağlıdır:

- ASP.NET projesi - [ne olduğunu – ASP.NET projeleri](http://go.microsoft.com/fwlink/p/?LinkId=513126)
- ASP.NET Core projesi - [ne olduğunu – ASP.NET 5 projeleri](http://go.microsoft.com/fwlink/p/?LinkId=513124)
- Bulut hizmeti projesi (web rolleri ve çalışan rolleri) - [ne olduğunu – bulut hizmeti projeleri](http://go.microsoft.com/fwlink/p/?LinkId=516965)
- Web işi projesi - [ne olduğunu - WebJob projeleri](/azure/visual-studio/vs-storage-webjobs-what-happened)

## <a name="see-also"></a>Ayrıca bkz.

- [MSDN forumu: Azure depolama](https://social.msdn.microsoft.com/forums/azure/home?forum=windowsazuredata)
- [Microsoft Azure depolama ekibi blogu](http://blogs.msdn.com/b/windowsazurestorage/)
- [Azure Depolama belgeleri](https://docs.microsoft.com/azure/storage/)
- [Bağlı hizmetler (Mac için Visual Studio)](/visualstudio/mac/connected-services)
