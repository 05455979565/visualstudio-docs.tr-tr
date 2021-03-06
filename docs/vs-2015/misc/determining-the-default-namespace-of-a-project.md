---
title: Bir projenin varsayılan Namespace belirleme | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: devlang-csharp
ms.topic: conceptual
helpviewer_keywords:
- custom tools, computing default namespace
ms.assetid: 6d890676-7016-458c-8a6a-95cc0a068612
caps.latest.revision: 13
manager: jillfra
ms.openlocfilehash: 1d58c8986922c30192d6300a623a635b24c34ed5
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65705766"
---
# <a name="determining-the-default-namespace-of-a-project"></a>Bir projenin varsayılan Namespace belirleme
İçin [!INCLUDE[vbprvb](../includes/vbprvb-md.md)], `CustomToolNamespace` özelliği değeri, ardından giriş dosyası ayarlanmış `CustomToolNamespace` geçirilen varsayılan ad alanı parametre değeri <xref:Microsoft.VisualStudio.Shell.Interop.IVsSingleFileGenerator.Generate%2A> yöntemi. Aksi takdirde, `wszDefaultNamespace` geçirilen `Generate` her zaman kök ad alanına eşittir. Ad alanları hakkında daha fazla bilgi için bkz. [Namespace anahtar sözcükleri](https://msdn.microsoft.com/library/091a66eb-b10d-4f54-9102-5ac0d4bdb84b).  
  
 [!INCLUDE[csprcs](../includes/csprcs-md.md)] Klasör tabanlı ad alanları kullanır. Diğer bir deyişle, kök ad alanının yanı sıra özel aracı içeren bir klasör adları ad alanı oluşur. Her bir klasör adı geçerli bir tanımlayıcı dönüştürülür ve tüm adları nokta ayırın. Örneğin, giriş dosyası FolderA\FolderB\FolderC\MyInput.txt ve kök ad CL9 ise, submiturl hesaplanan varsayılan ad alanı olabilir **CL9. FolderA.FolderB.FolderC**.  
  
 Hiyerarşi zincirini Web başvuru klasörü içeriyorsa bu kural için bir özel durum oluşur. Örneğin, varsa:  
  
- FolderC Web başvuru klasörü, ad alanı olacaktır **CL9. FolderC**.  
  
- FolderB Web başvuru klasörü, ad alanı olacaktır **CL9. FolderB.FolderC**.  
  
  Diğer bir deyişle, ad alanına aşağıdaki biçimdedir:  
  
```  
rootNamespace.webReferenceFolder.containedFolder.containedFolder ...  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Tek dosya oluşturucular ekleme](../extensibility/internals/implementing-single-file-generators.md)   
 [Tek dosya oluşturucuları kaydetme](../extensibility/internals/registering-single-file-generators.md)   
 [Türleri Görsel Tasarımcıların Kullanımına Sunma](../extensibility/internals/exposing-types-to-visual-designers.md)