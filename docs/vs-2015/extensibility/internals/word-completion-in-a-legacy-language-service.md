---
title: Eski dil hizmetinde Sözcük tamamlama | Microsoft Docs
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
- language services [managed package framework], IntelliSense Complete Word
- IntelliSense, Complete Word
- Complete Word
ms.assetid: 0ace5ac3-f9e1-4e6d-add4-42967b1f96a6
caps.latest.revision: 16
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: cd176c232bafd0d5a7a2b6735ba71b2bb490781d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42692819"
---
# <a name="word-completion-in-a-legacy-language-service"></a>Eski Dil Hizmetinde Sözcük Tamamlama
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [eski dil hizmetinde Sözcük tamamlama](https://docs.microsoft.com/visualstudio/extensibility/internals/word-completion-in-a-legacy-language-service).  
  
Kısmen belirlenmiş bir Word eksik karakter Sözcük tamamlama doldurur. Yalnızca bir olası tamamlanma varsa, sözcük tamamlama karakter girildiğinde tamamlandı. Kısmi sözcüğün birden fazla olasılığını eşleşiyorsa tamamlanabilir listesi görüntülenir. Bir tamamlama karakter tanımlayıcıları için kullanılmayan herhangi bir karakter olabilir.  
  
 Eski dil Hizmetleri bir VSPackage'ı bir parçası olarak uygulanır, ancak dil hizmeti özellikleri uygulamak için daha yeni MEF uzantıları kullanmaktır. Daha fazla bilgi için bkz. [düzenleyiciyi ve dil hizmetlerini genişletme](../../extensibility/extending-the-editor-and-language-services.md).  
  
> [!NOTE]
>  Yeni bir düzenleyici API hemen kullanmaya başlamak öneririz. Bu dil hizmetinizin performansını ve yeni düzenleyici özellikleri yararlanmanıza olanak tanır.  
  
## <a name="implementation-steps"></a>Uygulama adımları  
  
1.  Kullanıcı seçtiğinde **tam sözcük** gelen **IntelliSense** menüsünde <xref:Microsoft.VisualStudio.VSConstants.VSStd2KCmdID> komut dil hizmetine gönderilir.  
  
2.  <xref:Microsoft.VisualStudio.Package.ViewFilter> Sınıfı komut ve çağrılarını yakalar <xref:Microsoft.VisualStudio.Package.Source.Completion%2A> yöntemi ayrıştırma nedeni ile <xref:Microsoft.VisualStudio.Package.ParseReason>.  
  
3.  <xref:Microsoft.VisualStudio.Package.Source> Sınıfı ardından çağrıları <xref:Microsoft.VisualStudio.Package.LanguageService.ParseSource%2A> olası sözcük tamamlamaları ve araç ipucu sözcükler listesi kullanarak sonra görüntüler listesini almak için yöntemi <xref:Microsoft.VisualStudio.Package.CompletionSet> sınıfı.  
  
     Eşleşen tek bir sözcük ise <xref:Microsoft.VisualStudio.Package.Source> sınıfı word tamamlar.  
  
 Alternatif olarak, tarayıcı tetikleme değerini döndürürse <xref:Microsoft.VisualStudio.Package.TokenTriggers> bir tanımlayıcının ilk karakteri yazıldığında <xref:Microsoft.VisualStudio.Package.Source> sınıfı, bunu algılar ve çağıran <xref:Microsoft.VisualStudio.Package.Source.Completion%2A> yöntemi ayrıştırma nedeni ile <xref:Microsoft.VisualStudio.Package.ParseReason>. Bu durumda ayrıştırıcı bir üye seçimi karakterin varolup olmadığını algılamak ve bu üye listesini sağlamanız gerekir.  
  
## <a name="enabling-support-for-the-complete-word"></a>Tam sözcük desteğini etkinleştirme  
 Sözcük tamamlama kümesi desteğini etkinleştirmek için `CodeSense` geçirilen parametre adlı <xref:Microsoft.VisualStudio.Shell.ProvideLanguageServiceAttribute> dil paket ile ilişkili kullanıcı özniteliği. Bu ayarlar <xref:Microsoft.VisualStudio.Package.LanguagePreferences.EnableCodeSense%2A> özelliği <xref:Microsoft.VisualStudio.Package.LanguagePreferences> sınıfı.  
  
 Ayrıştırma neden değeri için yanıt bildirimleri listesi, ayrıştırıcı döndürmelidir <xref:Microsoft.VisualStudio.Package.ParseReason>, sözcük tamamlama çalışılacak.  
  
## <a name="implementing-complete-word-in-the-parsesource-method"></a>Tam sözcük ParseSource yöntemi uygulama  
 Sözcük tamamlama <xref:Microsoft.VisualStudio.Package.Source> sınıf çağrıları <xref:Microsoft.VisualStudio.Package.AuthoringScope.GetDeclarations%2A> metodunda <xref:Microsoft.VisualStudio.Package.AuthoringScope> olası sözcük eşleşme listesini almak için sınıf. Türetilen bir sınıfta listenin uygulamalıdır <xref:Microsoft.VisualStudio.Package.Declarations> sınıfı. Bkz: <xref:Microsoft.VisualStudio.Package.Declarations> uygulanmalı yöntemleri hakkında ayrıntılar için sınıf.  
  
 Listede yalnızca tek bir sözcük, varsa sonra <xref:Microsoft.VisualStudio.Package.Source> sınıfı kısmi sözcük yerine bu sözcüğü otomatik olarak ekler. Listede birden fazla sözcük varsa <xref:Microsoft.VisualStudio.Package.Source> sınıfı sunan bir araç ipucu listesi, kullanıcının uygun seçeneği seçebilirsiniz.  
  
 Aynı zamanda örneğe bakmaktır bir <xref:Microsoft.VisualStudio.Package.Declarations> sınıfı uygulamasında [eski dil hizmetinde üye tamamlama](../../extensibility/internals/member-completion-in-a-legacy-language-service.md).

