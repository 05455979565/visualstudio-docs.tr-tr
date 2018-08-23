---
title: Kod parçacıkları | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.ExpansionManagerImport
- vs.codesnippetmanager
helpviewer_keywords:
- code snippets, replacement parameters
- code snippets, surround with
- replacement parameters
- code snippets, expansion
- surround with
- code snippets
ms.assetid: 85976ad9-4c9a-4e7b-896e-66ec6f955199
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 29087da38fe7c89936e3823b43e591116396e432
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42629343"
---
# <a name="code-snippets"></a>Kod Parçacıkları
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [kod parçacıkları](https://docs.microsoft.com/visualstudio/ide/code-snippets).  
  
Küçük bir bağlam menüsü komutu veya bir birleşimini bir kısayol tuşlarını kullanarak bir kod dosyasında eklenebilen yeniden kullanılabilir kod bloklarını kod parçacıkları verilmiştir. Genellikle try-finally gibi sık kullanılan kod blokları veya if-else blokları içerir, ancak tüm sınıfları veya yöntemleri eklemek için kullanılabilir.  
  
## <a name="expansion-snippets-and-surround-with-snippets"></a>Genişletme kod parçacıkları ve Surround-With kod parçacıkları  
 Visual Studio'da kod parçacığı, iki tür vardır: Belirtilen ekleme noktasına eklenir ve bir kod parçacığı kısayol değiştirebilir, genişletme kod parçacıkları ve seçilen bir kod bloğu içine eklenen surround-with kod parçacıkları (C# ve C++ yalnızca).  
  
 Bir ekleme kod parçacığı örneği: C# dilinde kısayol tryf bir try-finally bloğu eklemek için kullanılır:  
  
```  
try  
{  
  
}  
finally  
{  
  
}  
  
```  
  
 Tıklayarak, bu kod parçacığı ekleyebilirsiniz **parçacık Ekle** kod penceresinin bağlam menüsünde **Visual C#**, yazın `tryf`, sekme veya yazabilirsiniz. sonra `tryf` sekmesini + SEKME tuşuna basın.  
  
 Surround-with kod parçacığı örneği: c++ kısayol `if` ekleme parçacığı veya bir surround-with kod parçacığı olarak kullanılabilir. Bir kod satırı seçerseniz (örneğin `return FALSE;`) ve ardından **Surround With**, ardından **varsa**, kod parçacığı çizgiyi genişletilir:  
  
```  
if (true)  
{  
    return FALSE;  
}  
  
```  
  
## <a name="snippet-replacement-parameters"></a>Kod parçacığı değiştirme parametreleri  
 Kod parçacıkları, yazmakta olduğunuz kesin kod uyacak şekilde değiştirmeniz gereken yer tutucular olan değiştirme parametreleri içerebilir. Önceki örnekte `true` uygun koşulu ile değiştirirsiniz değiştirme parametresi. Yaptığınız değişiklik, kod parçacığında aynı değiştirme parametresinin her örneği için tekrarlanır.  
  
 Örneğin, Visual Basic'te bir özellik ekleyen bir kod parçacığı yoktur. Tıklayın **parçacık Ekle** kod penceresinin bağlam menüsünde **kod desenleri**, ardından **özellikler, yordamlar, olaylar**, ardından bir özellik tanımlayın. Aşağıdaki kodu eklenir:  
  
```  
Private newPropertyValue As String  
Public Property NewProperty() As String  
    Get  
        Return newPropertyValue  
    End Get  
    Set(ByVal value As String)  
        newPropertyValue = value  
    End Set  
End Property  
  
```  
  
 Değiştirirseniz `newPropertyValue` için `m_property`, ardından her örneğini `newPropertyValue` değiştirilir. Değiştirirseniz `String` için `Int` özellik bildiriminde sonra küme yöntemini değeri de değiştirilecek `Int`.  
  
## <a name="code-snippet-manager"></a>Kod parçacığı Yöneticisi  
 Tıklayarak diskte şu anda yüklü olan tüm kod parçacıkları yanı sıra, konumlarına görebilirsiniz **Araçlar/kod parçacıkları Yöneticisi**. Kod parçacıkları dilde görüntülenir.  
  
 Kod parçacığı dizinlerle ekleyip **Ekle** ve **Kaldır** içinde düğmeleri **kod parçacıkları Yöneticisi** iletişim. Kod parçacıkları eklemek için **alma** düğmesi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İzlenecek yol: kod parçacığı oluşturma](../ide/walkthrough-creating-a-code-snippet.md)   
 [Nasıl yapılır: kod parçacıklarını dağıtma](../ide/how-to-distribute-code-snippets.md)   
 [Kod parçacıkları için en iyi uygulamalar](../ide/best-practices-for-using-code-snippets.md)   
 [Kod parçacıklarının sorunlarını giderme](../ide/troubleshooting-snippets.md)   
 [Visual C# kod parçacıkları](../ide/visual-csharp-code-snippets.md)   
 [Visual C++ kod parçacıkları](../ide/visual-cpp-code-snippets.md)   
 [Kod Parçacıkları Şema Başvurusu](../ide/code-snippets-schema-reference.md)



