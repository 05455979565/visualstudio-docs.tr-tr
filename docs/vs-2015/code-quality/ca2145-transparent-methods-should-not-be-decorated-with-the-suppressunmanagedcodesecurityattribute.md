---
title: 'CA2145: Saydam yöntemler SuppressUnmanagedCodeSecurityAttribute ile donatılmamalıdır | Microsoft Docs'
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
- CA2145
ms.assetid: 81970700-b438-4b3b-9239-16887e16f7b7
caps.latest.revision: 13
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 605c0f30fc5be4f040885fecfc7822d367e006b0
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42632121"
---
# <a name="ca2145-transparent-methods-should-not-be-decorated-with-the-suppressunmanagedcodesecurityattribute"></a>CA2145: Saydam yöntemler SuppressUnmanagedCodeSecurityAttribute ile donatılmamalıdır
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [CA2145: saydam yöntemler değil düzenlenmiş SuppressUnmanagedCodeSecurityAttribute ile](https://docs.microsoft.com/visualstudio/code-quality/ca2145-transparent-methods-should-not-be-decorated-with-the-suppressunmanagedcodesecurityattribute).  
  
TypeName | TransparentMethodsShouldNotUseSuppressUnmanagedCodeSecurity |  
| Checkıd | CA2145 |  
| Kategori | Microsoft.Security|  
| Yeni değişiklik | Bozucu |  
  
## <a name="cause"></a>Sebep  
 Saydam bir yöntem, ile işaretlenmiş bir yöntem <xref:System.Security.SecuritySafeCriticalAttribute> yöntemi veya yöntem içeren bir tür ile işaretlenmiş <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute> özniteliği.  
  
## <a name="rule-description"></a>Kural Tanımı  
 Donatılmış yöntemler ile <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute> özniteliğine, çağıran herhangi bir yöntem yerleştirilen örtülü Linkdemand'a sahiptir. Bu LinkDemand, çağıran kodun kritik güvenlikli olmasını gerektirir. İle SuppressUnmanagedCodeSecurity kullanan yöntemi işaretlemek <xref:System.Security.SecurityCriticalAttribute> öznitelik yapar bu gereksinimi daha belirgin yöntemini arayanlar için.  
  
## <a name="how-to-fix-violations"></a>İhlaller Nasıl Düzeltilir?  
 Bu kural ihlalini düzeltmek için yöntemi işaretlemek veya tür <xref:System.Security.SecurityCriticalAttribute> özniteliği.  
  
## <a name="when-to-suppress-warnings"></a>Uyarılar Bastırıldığında  
 Bu kuraldan uyarıyı bastırmayın.  
  
### <a name="code"></a>Kod  
 [!code-csharp[FxCop.Security.CA2145.TransparentMethodsShouldNotUseSuppressUnmanagedCodeSecurity#1](../snippets/csharp/VS_Snippets_CodeAnalysis/fxcop.security.ca2145.transparentmethodsshouldnotusesuppressunmanagedcodesecurity/cs/ca2145 - transparentmethodsshouldnotusesuppressunmanagedcodesecurity.cs#1)]  
  
### <a name="comments"></a>Açıklamalar



