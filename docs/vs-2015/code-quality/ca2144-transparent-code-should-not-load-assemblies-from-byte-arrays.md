---
title: 'CA2144: Saydam kod derlemeleri bayt dizilerinden yok | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- CA2144
ms.assetid: 777b1310-6e16-4413-b4ee-5f3136304f82
caps.latest.revision: 14
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: a3ecbf57bf8b4af2bf8edd66a406d27f96809b39
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/24/2018
ms.locfileid: "42900393"
---
# <a name="ca2144-transparent-code-should-not-load-assemblies-from-byte-arrays"></a>CA2144: Saydam kod derlemeleri bayt dizilerinden yüklememelidir
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CA2144: saydam kod yüklenmemesi derlemeleri bayt dizileri](https://docs.microsoft.com/visualstudio/code-quality/ca2144-transparent-code-should-not-load-assemblies-from-byte-arrays).

|||
|-|-|
|TypeName|TransparentMethodsShouldNotLoadAssembliesFromByteArrays|
|CheckId|CA2144|
|Kategori|Microsoft.Security|
|Yeni Değişiklik|Yeni|

## <a name="cause"></a>Sebep
 Saydam bir yöntem, aşağıdaki yöntemlerden birini kullanarak bir bayt dizisinden bir derleme yükler:

-   <xref:System.Reflection.Assembly.Load%2A>

-   <xref:System.Reflection.Assembly.Load%2A>

-   <xref:System.Reflection.Assembly.Load%2A>

## <a name="rule-description"></a>Kural Tanımı
 Saydam kod için güvenlik incelemesi kritik kod için güvenlik incelemesi kadar kapsamlı değildir, çünkü saydam kod güvenlik duyarlı eylemleri gerçekleştiremez. Bir bayt dizisinden yüklenen derlemeler saydam kodda fark edilmeyebilir ve o bayt dizisi denetlenmesi gereken kritik ya da daha da önemlisi güvenli kritik kod içerebilir. Bu nedenle, saydam kod derlemeleri bayt dizisinden yüklenmemelidir.

## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?
 Bu kural ihlalini düzeltmek için derleme ile yüklenirken yöntemi işaretlemek <xref:System.Security.SecurityCriticalAttribute> veya <xref:System.Security.SecuritySafeCriticalAttribute> özniteliği.

## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında
 Bu kuraldan uyarıyı bastırmayın.

## <a name="example"></a>Örnek
 Kural, saydam bir yöntem, bir bayt dizisinden bir derleme yükler için aşağıdaki kodu tetikler.

 [!code-csharp[FxCop.Security.CA2144.TransparentMethodsShouldNotLoadAssembliesFromByteArrays#1](../snippets/csharp/VS_Snippets_CodeAnalysis/fxcop.security.ca2144.transparentmethodsshouldnotloadassembliesfrombytearrays/cs/ca2144 - transparentmethodsshouldnotloadassembliesfrombytearrays.cs#1)]



