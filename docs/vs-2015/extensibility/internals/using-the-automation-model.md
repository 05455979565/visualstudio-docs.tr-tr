---
title: Otomasyon modelini kullanma | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- automation [Visual Studio SDK], automation model
ms.assetid: 0c7f7889-fbfb-4b19-804f-b742138baecd
caps.latest.revision: 16
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 22ee836f5a4330c551181f01229e82eb14623fb8
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65675205"
---
# <a name="using-the-automation-model"></a>Otomasyon Modelini Kullanma
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Otomasyon ile VSPackage'ı bağladıktan sonra özellikleri ve yöntemleri çağırarak elde edebileceğiniz <xref:EnvDTE.DTEClass.GetObject%2A> metodunda <xref:EnvDTE._DTE> nesne, almak istediğiniz nesnesini temsil eden bir dizeye geçiliyor.  
  
## <a name="obtaining-project-objects"></a>Proje nesnelerini alma  
 Bir Otomasyon Tüketici Proje Otomasyon nesneleri nasıl alacağını gösteren iki kod örneği aşağıda verilmiştir. DTE nesnesini alma hakkında daha fazla bilgi için bkz: [nasıl yapılır: DTE ve DTE2 nesnelerine başvurular alma](https://msdn.microsoft.com/library/c92e3c8e-82e6-4a67-85da-e43c50ffd8e4).  
  
```vb  
Sub DoAutomation()  
    Dim MyProjects As Projects  
    MyProjects = DTE.GetObject("AcmeProject")  
End Sub  
```  
  
```cpp#  
void DoAutomation(void)  
{  
  CComQIPtr<Projects> pMyPkg; // Use an IDispatch-derived object type.  
    pMyPkg = pDTE->GetObject("AcmeProjects");   
  
   // The '=' performs a Query Interface.  
   // Assumes pDTE is already available as a global.  
   // Use pMyPkg to access your projects object's properties and methods.  
}  
  
```  
  
 Bu noktada, hiyerarşi modeli taşımak için belirli bir VSPackage parçası olan standart proje nesneleri kullanabilirsiniz.  
  
 Aşağıdaki kod örneği, bir özel proje türünde bir özellik olan özel bir nesne almak gösterilmektedir.:  
  
```vb  
Dim MyPrj As Project  
Dim MyPrjItem As ProjectItem  
Dim objMyObject as MyExtendedObject  
  
MyPrj = MyProjects.Item(1) 'use the Projects collection to get a project  
objMyObject = MyPrj.Object 'You call .Object to get to special Project  
                           'implementation  
objMyObject.MySpecialMethodOrProperty  
```  
  
 Aşağıdaki kod tüm özelliklerin adları listeler [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] ortam **genel** seçeneğini **Araçları** menüsü:  
  
```vb  
dim objDTE  
dim objEnv  
set objDTE = CreateObject("VisualStudio.DTE")  
set objEnv = objDTE.Properties("Environment", "General")  
for each obj in ObjEnv  
MsgBox obj.Name  
Next  
  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:EnvDTE.DTEClass.GetObject%2A>
