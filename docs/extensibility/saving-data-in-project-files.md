---
title: Proje dosyaları veri kaydetme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- data [Visual Studio], saving in project files
- project files
- project files, saving data
ms.assetid: a3d4b15b-a91e-41ba-b235-e62632d11bc5
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 35514385a4ed1d28052ebb21d12ed0b053dd52dc
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
ms.locfileid: "31140183"
---
# <a name="saving-data-in-project-files"></a>Proje dosyalarındaki verileri kaydetme
Proje alt kaydetmek ve proje dosyasında alt özgü verileri alın. Yönetilen paket Framework (MPF), bu görevi gerçekleştirmek için iki arabirim sağlar:  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildPropertyStorage> Arabirim sağlayan erişim özellik değerleri için **MSBuild** proje dosyasının bölümü. Tarafından sağlanan yöntemleri <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildPropertyStorage> ilgili verileri yüklemek veya kaydetmek için kullanıcı gereksinimlerini yapı her herhangi bir kullanıcı tarafından çağrılabilir.  
  
-   <xref:Microsoft.VisualStudio.Shell.Interop.IPersistXMLFragment> Derleme olmayan ilgili verileri de serbest biçimli XML kalıcı hale getirmek için kullanılır. Tarafından sağlanan yöntemleri <xref:Microsoft.VisualStudio.Shell.Interop.IPersistXMLFragment> tarafından çağrılır [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] her [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] derleme olmayan ilgili verileri proje dosyasında kalıcı hale getirmek gerekiyor.  
  
 Yapı ve yapı olmayan ilgili tüm verileri kalıcı hakkında daha fazla bilgi için bkz: [kalıcı veri MSBuild proje dosyası içinde](../extensibility/internals/persisting-data-in-the-msbuild-project-file.md).  
  
## <a name="saving-and-retrieving-build-related-data"></a>İlgili verileri kaydetme ve derleme alma  
  
#### <a name="to-save-a-build-related-data-in-the-project-file"></a>İlgili verileri proje dosyasında bir yapı kaydetmek için  
  
-   Çağrı <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildPropertyStorage.SetPropertyValue%2A> proje dosyasının tam yolunu kaydetmek için yöntem.  
  
    ```  
    private SpecializedProject project;  
    IVsBuildPropertyStorage projectStorage = (IVsBuildPropertyStorage)project;  
    string newFullPath = GetNewFullPath();  
    // Set a full path of the project file.  
    ErrorHandler.ThrowOnFailure(projectStorage.SetPropertyValue(  
        "MSBuildProjectDirectory",  
        String.Empty,  
        (uint)_PersistStorageType.PST_PROJECT_FILE, newFullPath));  
    ```  
  
#### <a name="to-retrieve-build-related-data-from-the-project-file"></a>Proje dosyasından ilgili verileri yapı almak için  
  
-   Çağrı <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildPropertyStorage.GetPropertyValue%2A> proje dosyasının tam yolunu alma yöntemi.  
  
    ```  
    private SpecializedProject project;  
    IVsBuildPropertyStorage projectStorage = (IVsBuildPropertyStorage)project;  
    string fullPath;  
    // Get a full path of the project file.  
    ErrorHandler.ThrowOnFailure(projectStorage.GetPropertyValue(  
        "MSBuildProjectDirectory",  
        String.Empty,  
        (uint)_PersistStorageType.PST_PROJECT_FILE, out fullPath));  
    ```  
  
## <a name="saving-and-retrieving-non-build-related-data"></a>Kaydetme ve alma olmayan ilgili verileri oluştur  
  
#### <a name="to-save-non-build-related-data-in-the-project-file"></a>İlgili verileri proje dosyasında yapı olmayan kaydetmek için  
  
1.  Uygulama <xref:Microsoft.VisualStudio.Shell.Interop.IPersistXMLFragment.IsFragmentDirty%2A> son başlatıldığından beri bir XML parçası değişip değişmediğini belirlemek amacıyla yöntemi geçerli dosyasına kaydedilir.  
  
    ```  
    public int IsFragmentDirty(uint storage, out int pfDirty)  
    {  
        pfDirty = 0;  
        switch (storage)  
        {  
            case (uint)_PersistStorageType.PST_PROJECT_FILE:  
            {  
                if (isDirty)  
                    pfDirty |= 1;  
                break;  
            }  
            case (uint)_PersistStorageType.PST_USER_FILE:  
            {  
                // We do not store anything in the user file.  
                break;  
            }  
        }  
  
        // Forward the call to inner flavor(s)   
        if (pfDirty == 0 && innerCfg != null && this.innerCfg is IPersistXMLFragment)  
            return ((IPersistXMLFragment)this.innerCfg).IsFragmentDirty(storage, out pfDirty);  
  
        return VSConstants.S_OK;  
  
    }  
    ```  
  
2.  Uygulama <xref:Microsoft.VisualStudio.Shell.Interop.IPersistXMLFragment.Save%2A> proje dosyasında XML verileri kaydetmek için yöntem.  
  
    ```  
    public int Save(ref Guid guidFlavor, uint storage, out string pbstrXMLFragment, int fClearDirty)  
    {  
        pbstrXMLFragment = null;  
  
        if (IsMyFlavorGuid(ref guidFlavor))  
        {  
            switch (storage)  
            {  
                case (uint)_PersistStorageType.PST_PROJECT_FILE:  
                {  
                    // Create XML for our data.  
                    XmlDocument doc = new XmlDocument();  
                    XmlNode root = doc.CreateElement(this.GetType().Name);  
  
                    XmlNode node = doc.CreateElement(targetsTag);  
                    node.AppendChild(doc.CreateTextNode(this.TargetsToExecute));  
                    root.AppendChild(node);  
  
                    node = doc.CreateElement(updateTargetsTag);  
                    node.AppendChild(doc.CreateTextNode(this.UpdateTargetList.ToString()));  
                    root.AppendChild(node);  
  
                    doc.AppendChild(root);  
                    // Get XML fragment representing our data  
                    pbstrXMLFragment = doc.InnerXml;  
  
                    if (fClearDirty != 0)  
                        isDirty = false;  
                    break;  
                }  
                case (uint)_PersistStorageType.PST_USER_FILE:  
                {  
                    // We do not store anything in the user file.  
                    break;  
                }  
            }  
        }  
  
        // Forward the call to inner flavor(s)  
        if (this.innerCfg != null && this.innerCfg is IPersistXMLFragment)  
            return ((IPersistXMLFragment)this.innerCfg).Save(ref guidFlavor, storage, out pbstrXMLFragment, fClearDirty);  
  
        return VSConstants.S_OK;  
    }  
    ```  
  
#### <a name="to-retrieve-non-build-related-data-in-the-project-file"></a>Proje dosyası derleme olmayan ilgili verileri almak için  
  
1.  Uygulama <xref:Microsoft.VisualStudio.Shell.Interop.IPersistXMLFragment.InitNew%2A> yöntemi proje uzantısı özellikleri ve diğer yapı bağımsız veriler başlatılamadı. XML yapılandırma verilerini proje dosyasında mevcut ise, bu yöntem çağrılır.  
  
    ```  
    public int InitNew(ref Guid guidFlavor, uint storage)  
    {  
        //Return,if it is our guid.  
        if (IsMyFlavorGuid(ref guidFlavor))  
            return VSConstants.S_OK;  
  
        //Forward the call to inner flavor(s).  
        if (this.innerCfg != null && this.innerCfg is IPersistXMLFragment)  
            return ((IPersistXMLFragment)this.innerCfg).InitNew(ref guidFlavor, storage);  
  
        return VSConstants.S_OK;  
    ```  
  
2.  Uygulama <xref:Microsoft.VisualStudio.Shell.Interop.IPersistXMLFragment.Load%2A> proje dosyasından XML verilerini yüklemek için yöntem.  
  
    ```  
    public int Load(ref Guid guidFlavor, uint storage, string pszXMLFragment)  
    {  
        if (IsMyFlavorGuid(ref guidFlavor))  
        {  
            switch (storage)  
            {  
                case (uint)_PersistStorageType.PST_PROJECT_FILE:  
                {  
                    // Load our data from the XML fragment.  
                    XmlDocument doc = new XmlDocument();  
                    XmlNode node = doc.CreateElement(this.GetType().Name);  
                    node.InnerXml = pszXMLFragment;  
                    if (node == null  
                        || node.FirstChild == null  
                        || node.FirstChild.ChildNodes.Count == 0  
                        || node.FirstChild.ChildNodes[0].Name != targetsTag)  
                        break;  
                    this.TargetsToExecute = node.FirstChild.ChildNodes[0].InnerText;  
  
                    if (node.FirstChild.ChildNodes.Count <= 1  
                        || node.FirstChild.ChildNodes[1].Name != updateTargetsTag)  
                        break;  
                    this.UpdateTargetList = bool.Parse(node.FirstChild.ChildNodes[1].InnerText);  
                    break;  
                }  
                case (uint)_PersistStorageType.PST_USER_FILE:  
                {  
                    // We do not store anything in the user file.  
                    break;  
                }  
            }  
        }  
  
        // Forward the call to inner flavor(s)  
        if (this.innerCfg != null && this.innerCfg is IPersistXMLFragment)  
            return ((IPersistXMLFragment)this.innerCfg).Load(ref guidFlavor, storage, pszXMLFragment);  
  
        return VSConstants.S_OK;  
    }  
    ```  
  
> [!NOTE]
>  Bu konuda sağlanan tüm kod örnekleri daha büyük bir örneğin bölümlerdir [VSSDK örnekleri](http://aka.ms/vs2015sdksamples).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MSBuild Proje Dosyasında Verileri Kalıcı Hale Getirme](../extensibility/internals/persisting-data-in-the-msbuild-project-file.md)