---
title: Visual Studio Enterprise 2017 iş yükü ve Bileşen kimlikleri
titleSuffix: ''
description: İş yükü ve Bileşen kimlikleri komut satırını kullanarak Visual Studio'yu yükleyin veya bağımlılık VSIX bildirimi olarak belirtmek için kullanın.
keywords: ''
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.date: 2/12/2019
ms.prod: visual-studio-windows
ms.technology: vs-installation
ms.topic: include
ms.openlocfilehash: 1e9ac9e8371c1dab482fd16ce4d10e8982ba1aee
ms.sourcegitcommit: 3ca33862c1cfc3ccb83de3e95f1e69e860ab143a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2019
ms.locfileid: "58161126"
---
## <a name="visual-studio-core-editor-included-with-visual-studio-enterprise-2017"></a>(Visual Studio Enterprise 2017 ile dahil) visual Studio temel Düzenleyicisi

**KİMLİĞİ:** Microsoft.VisualStudio.Workload.CoreEditor

**Açıklama:** Visual Studio söz dizimine duyarlı kod düzenleme, kaynak kodu denetimi de dahil olmak üzere, temel Kabuk deneyimi ve iş öğesi yönetimi.

### <a name="components-included-by-this-workload"></a>Bu iş yükü tarafından bulunan bileşenler

Bileşen kimliği | Ad | Sürüm | Bağımlılık türü
--- | --- | --- | ---
Microsoft.VisualStudio.Component.CoreEditor | Visual Studio temel Düzenleyicisi | 15.8.27729.1 | Gerekli
Microsoft.VisualStudio.Component.StartPageExperiment.Cpp | Visual Studio başlangıç sayfasını C++ kullanıcılar | 15.0.27128.1 | İsteğe Bağlı

## <a name="azure-development"></a>Azure geliştirme

**KİMLİĞİ:** Microsoft.VisualStudio.Workload.Azure

**Açıklama:** Azure SDK'ları, araçları ve projeleri bulut uygulamaları geliştirmek için kaynakları oluşturmak ve Docker dahil kapsayıcılar oluşturmak destekler.

### <a name="components-included-by-this-workload"></a>Bu iş yükü tarafından bulunan bileşenler

Bileşen kimliği | Ad | Sürüm | Bağımlılık türü
--- | --- | --- | ---
Component.Microsoft.VisualStudio.RazorExtension | Razor dil Hizmetleri | 15.0.26720.2 | Gerekli
Component.Microsoft.VisualStudio.Web.AzureFunctions | Microsoft Azure Web işleri araçları | 15.7.27617.1 | Gerekli
Component.Microsoft.Web.LibraryManager | Kitaplık Yöneticisi | 15.8.27705.0 | Gerekli
Component.WebSocket | WebSocket4Net | 15.0.26606.0 | Gerekli
Microsoft.Component.ClickOnce | ClickOnce yayımlama | 15.8.27825.0 | Gerekli
Microsoft.Component.MSBuild | MSBuild | 15.7.27520.0 | Gerekli
Microsoft.Component.NetFX.Core.Runtime | .NET core çalışma zamanı | 15.0.26208.0 | Gerekli
Microsoft.Net.Component.4.5.2.TargetingPack | .NET framework 4.5.2 targeting pack | 15.6.27406.0 | Gerekli
Microsoft.Net.Component.4.5.TargetingPack | .NET framework 4.5 targeting pack | 15.6.27406.0 | Gerekli
Microsoft.Net.Component.4.6.1.SDK | .NET framework 4.6.1 SDK'sı | 15.6.27406.0 | Gerekli
Microsoft.Net.Component.4.6.1.TargetingPack | .NET framework 4.6.1 targeting pack | 15.6.27406.0 | Gerekli
Microsoft.Net.ComponentGroup.DevelopmentPrerequisites | .NET framework 4.6.1 geliştirme araçları | 15.8.27825.0 | Gerekli
Microsoft.Net.Core.Component.SDK.2.1 | .NET core 2.1 geliştirme araçları | 15.8.27924.0 | Gerekli
Microsoft.NetCore.ComponentGroup.DevelopmentTools.2.1 | .NET core 2.1 geliştirme araçları | 15.8.27924.0 | Gerekli
Microsoft.NetCore.ComponentGroup.Web.2.1 | .NET core 2.1 geliştirme araçları | 15.8.27924.0 | Gerekli
Microsoft.VisualStudio.Component.Azure.AuthoringTools | Azure yazma araçları | 15.9.28307.421 | Gerekli
Microsoft.VisualStudio.Component.Azure.ClientLibs | .NET için Azure kitaplıkları | 15.0.26208.0 | Gerekli
Microsoft.VisualStudio.Component.Azure.Compute.Emulator | Azure işlem öykünücüsü | 15.9.28307.421 | Gerekli
Microsoft.VisualStudio.Component.Azure.Storage.Emulator | Azure depolama öykünücüsü | 15.9.28125.51 | Gerekli
Microsoft.VisualStudio.Component.CloudExplorer | Cloud Explorer | 15.9.28230.55 | Gerekli
Microsoft.VisualStudio.Component.Common.Azure.Tools | Bağlantı ve yayımlama araçları | 15.9.28107.0 | Gerekli
Microsoft.VisualStudio.Component.DockerTools | Kapsayıcı geliştirme araçları | 15.8.27906.1 | Gerekli
Microsoft.VisualStudio.Component.DockerTools.BuildTools | Kapsayıcı geliştirme araçları - derleme araçları | 15.7.27617.1 | Gerekli
Microsoft.VisualStudio.Component.FSharp | F#dil desteği | 15.8.27825.0 | Gerekli
Microsoft.VisualStudio.Component.FSharp.WebTemplates | F#web projeleri için dil desteği | 15.9.28307.421 | Gerekli
Microsoft.VisualStudio.Component.IISExpress | IIS Express  | 15.0.26208.0 | Gerekli
Microsoft.VisualStudio.Component.JavaScript.Diagnostics | JavaScript tanılamaları | 15.8.27729.1 | Gerekli
Microsoft.VisualStudio.Component.JavaScript.TypeScript | JavaScript ve TypeScript dil desteği | 15.9.28125.51 | Gerekli
Microsoft.VisualStudio.Component.ManagedDesktop.Core | Yönetilen masaüstü iş yükü Çekirdeği | 15.8.27729.1 | Gerekli
Microsoft.VisualStudio.Component.NuGet | NuGet Paket Yöneticisi | 15.9.28016.0 | Gerekli
Microsoft.VisualStudio.Component.PortableLibrary | .NET taşınabilir kitaplık targeting pack | 15.6.27309.0 | Gerekli
Microsoft.VisualStudio.Component.Roslyn.Compiler | C# ve Visual Basic Roslyn derleyicileri | 15.6.27309.0 | Gerekli
Microsoft.VisualStudio.Component.Roslyn.LanguageServices | C# ve Visual Basic | 15.8.27729.1 | Gerekli
Microsoft.VisualStudio.Component.SQL.ADAL | SQL ADAL çalışma zamanı | 15.6.27406.0 | Gerekli
Microsoft.VisualStudio.Component.SQL.CLR | SQL Server için CLR veri türleri | 15.0.26208.0 | Gerekli
Microsoft.VisualStudio.Component.SQL.CMDUtils | SQL Server komut satırı yardımcı programları | 15.0.26208.0 | Gerekli
Microsoft.VisualStudio.Component.SQL.DataSources | Veri kaynakları için SQL Server desteği | 15.0.26621.2 | Gerekli
Microsoft.VisualStudio.Component.SQL.LocalDB.Runtime | SQL Server Express 2016 LocalDB | 15.7.27617.1 | Gerekli
Microsoft.VisualStudio.Component.SQL.NCLI | SQL Server yerel istemcisi | 15.0.26208.0 | Gerekli
Microsoft.VisualStudio.Component.SQL.SSDT | SQL Server Veri Araçları | 15.9.28107.0 | Gerekli
Microsoft.VisualStudio.Component.Static.Analysis.Tools | Statik analiz araçları | 15.0.26208.0 | Gerekli
Microsoft.VisualStudio.Component.TextTemplating | Metin şablonu dönüştürme | 15.0.26208.0 | Gerekli
Microsoft.VisualStudio.Component.TypeScript.3.1 | 3.1 TypeScript SDK'sı | 15.0.28218.60 | Gerekli
Microsoft.VisualStudio.Component.VisualStudioData | Veri kaynakları ve hizmet başvuruları | 15.6.27406.0 | Gerekli
Microsoft.VisualStudio.Component.Web | ASP.NET ve web geliştirme araçları | 15.8.27825.0 | Gerekli
Microsoft.VisualStudio.ComponentGroup.Azure.Prerequisites | Azure geliştirme önkoşulları | 15.9.28107.0 | Gerekli
Microsoft.VisualStudio.ComponentGroup.AzureFunctions | Microsoft Azure Web işleri araçları | 15.7.27617.1 | Gerekli
Microsoft.VisualStudio.ComponentGroup.Web | ASP.NET ve web geliştirme araçları önkoşulları | 15.9.28219.51 | Gerekli
Microsoft.VisualStudio.ComponentGroup.WebToolsExtensions | ASP.NET ve web geliştirme | 15.8.27825.0 | Gerekli
Microsoft.Component.Azure.DataLake.Tools | Azure Data Lake ve Stream Analytics araçları | 15.9.28107.0 | Önerilen
Microsoft.Net.Component.4.5.1.TargetingPack | .NET framework 4.5.1 targeting pack | 15.6.27406.0 | Önerilen
Microsoft.Net.Component.4.6.TargetingPack | .NET framework 4.6 targeting pack | 15.6.27406.0 | Önerilen
Microsoft.Net.Component.4.TargetingPack | .NET framework 4 targeting pack | 15.6.27406.0 | Önerilen
Microsoft.Net.ComponentGroup.TargetingPacks.Common | .NET framework 4-4.6 geliştirme araçları | 15.6.27406.0 | Önerilen
Microsoft.VisualStudio.Component.AspNet45 | Gelişmiş ASP.NET özellikleri | 15.7.27625.0 | Önerilen
Microsoft.VisualStudio.Component.Azure.MobileAppsSdk | Azure Mobile Apps SDK'sı | 15.7.27625.0 | Önerilen
Microsoft.VisualStudio.Component.Azure.ResourceManager.Tools | Azure Resource Manager temel araçları | 15.9.28107.0 | Önerilen
Microsoft.VisualStudio.Component.Azure.ServiceFabric.Tools | Service Fabric Araçları | 15.8.27825.0 | Önerilen
Microsoft.VisualStudio.Component.Azure.Waverton | Azure Cloud Services temel araçları | 15.9.28107.0 | Önerilen
Microsoft.VisualStudio.Component.Azure.Waverton.BuildTools | Azure Cloud Services derleme araçları | 15.7.27617.1 | Önerilen
Microsoft.VisualStudio.Component.Debugger.Snapshot | Anlık görüntü hata ayıklayıcısı | 15.8.28010.0 | Önerilen
Microsoft.VisualStudio.Component.DiagnosticTools | .NET profil oluşturma araçları | 15.8.27729.1 | Önerilen
Microsoft.VisualStudio.Component.IntelliTrace.FrontEnd | IntelliTrace | 15.8.27729.1 | Önerilen
Microsoft.VisualStudio.Component.WebDeploy | Web Dağıtımı | 15.8.27729.1 | Önerilen
Microsoft.VisualStudio.ComponentGroup.Azure.CloudServices | Azure Cloud Services araçları | 15.0.26504.0 | Önerilen
Microsoft.VisualStudio.ComponentGroup.Azure.ResourceManager.Tools | Azure Resource Manager araçları | 15.0.27005.2 | Önerilen
Microsoft.Net.Component.4.6.2.SDK | .NET framework 4.6.2 SDK'sı | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Component.4.6.2.TargetingPack | .NET framework 4.6.2 targeting pack | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Component.4.7.1.SDK | .NET framework 4.7.1 SDK'sı | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Component.4.7.1.TargetingPack | .NET framework 4.7.1 targeting pack | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Component.4.7.2.SDK | .NET framework 4.7.2 SDK'sı | 15.8.27825.0 | İsteğe Bağlı
Microsoft.Net.Component.4.7.2.TargetingPack | .NET framework 4.7.2 targeting pack | 15.8.27825.0 | İsteğe Bağlı
Microsoft.Net.Component.4.7.SDK | .NET framework 4.7 SDK'sı | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Component.4.7.TargetingPack | .NET framework 4.7 targeting pack | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.ComponentGroup.4.6.2.DeveloperTools | .NET framework 4.6.2 geliştirme araçları | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.ComponentGroup.4.7.1.DeveloperTools | .NET framework 4.7.1 geliştirme araçları | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.ComponentGroup.4.7.2.DeveloperTools | .NET framework 4.7.2 geliştirme araçları | 15.8.27825.0 | İsteğe Bağlı
Microsoft.Net.ComponentGroup.4.7.DeveloperTools | .NET framework 4.7 geliştirme araçları | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Core.Component.SDK | .NET core 2.0 geliştirme araçları | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Core.Component.SDK.1x | .NET core 1.0-1.1 geliştirme araçları | 15.6.27406.0 | İsteğe Bağlı
Microsoft.NetCore.1x.ComponentGroup.Web | Web için .NET core 1.0-1.1 geliştirme araçları | 15.6.27406.0 | İsteğe Bağlı
Microsoft.NetCore.ComponentGroup.DevelopmentTools | .NET core 2.0 geliştirme araçları | 15.8.27729.1 | İsteğe Bağlı
Microsoft.NetCore.ComponentGroup.Web | .NET core 2.0 geliştirme araçları | 15.7.27625.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Azure.Storage.AzCopy | Azure depolama AzCopy | 15.0.26906.1 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Wcf.Tooling | Windows Communication Foundation | 15.8.27924.0 | İsteğe Bağlı

## <a name="data-storage-and-processing"></a>Veri depolama ve işleme

**KİMLİĞİ:** Microsoft.VisualStudio.Workload.Data

**Açıklama:** Bağlayın, geliştirin ve SQL Server, Azure Data Lake veya Hadoop veri çözümleriyle test.

### <a name="components-included-by-this-workload"></a>Bu iş yükü tarafından bulunan bileşenler

Bileşen kimliği | Ad | Sürüm | Bağımlılık türü
--- | --- | --- | ---
Component.Microsoft.VisualStudio.RazorExtension | Razor dil Hizmetleri | 15.0.26720.2 | Önerilen
Component.Microsoft.Web.LibraryManager | Kitaplık Yöneticisi | 15.8.27705.0 | Önerilen
Component.Redgate.ReadyRoll | Redgate ReadyRoll Core | 1.17.18155.10346 | Önerilen
Component.Redgate.SQLPrompt.VsPackage | Redgate SQL Prompt Core | 9.2.0.5601 | Önerilen
Component.Redgate.SQLSearch.VSExtension | Redgate SQL Araması | 3.1.7.2062 | Önerilen
Component.WebSocket | WebSocket4Net | 15.0.26606.0 | Önerilen
Microsoft.Component.Azure.DataLake.Tools | Azure Data Lake ve Stream Analytics araçları | 15.9.28107.0 | Önerilen
Microsoft.Component.ClickOnce | ClickOnce yayımlama | 15.8.27825.0 | Önerilen
Microsoft.Component.MSBuild | MSBuild | 15.7.27520.0 | Önerilen
Microsoft.Net.Component.4.5.1.TargetingPack | .NET framework 4.5.1 targeting pack | 15.6.27406.0 | Önerilen
Microsoft.Net.Component.4.5.2.TargetingPack | .NET framework 4.5.2 targeting pack | 15.6.27406.0 | Önerilen
Microsoft.Net.Component.4.5.TargetingPack | .NET framework 4.5 targeting pack | 15.6.27406.0 | Önerilen
Microsoft.Net.Component.4.6.1.SDK | .NET framework 4.6.1 SDK'sı | 15.6.27406.0 | Önerilen
Microsoft.Net.Component.4.6.1.TargetingPack | .NET framework 4.6.1 targeting pack | 15.6.27406.0 | Önerilen
Microsoft.Net.Component.4.6.TargetingPack | .NET framework 4.6 targeting pack | 15.6.27406.0 | Önerilen
Microsoft.Net.Component.4.TargetingPack | .NET framework 4 targeting pack | 15.6.27406.0 | Önerilen
Microsoft.Net.ComponentGroup.DevelopmentPrerequisites | .NET framework 4.6.1 geliştirme araçları | 15.8.27825.0 | Önerilen
Microsoft.Net.ComponentGroup.TargetingPacks.Common | .NET framework 4-4.6 geliştirme araçları | 15.6.27406.0 | Önerilen
Microsoft.Net.Core.Component.SDK.2.1 | .NET core 2.1 geliştirme araçları | 15.8.27924.0 | Önerilen
Microsoft.VisualStudio.Component.Azure.AuthoringTools | Azure yazma araçları | 15.9.28307.421 | Önerilen
Microsoft.VisualStudio.Component.Azure.ClientLibs | .NET için Azure kitaplıkları | 15.0.26208.0 | Önerilen
Microsoft.VisualStudio.Component.Azure.Compute.Emulator | Azure işlem öykünücüsü | 15.9.28307.421 | Önerilen
Microsoft.VisualStudio.Component.Azure.Storage.Emulator | Azure depolama öykünücüsü | 15.9.28125.51 | Önerilen
Microsoft.VisualStudio.Component.Azure.Waverton | Azure Cloud Services temel araçları | 15.9.28107.0 | Önerilen
Microsoft.VisualStudio.Component.Azure.Waverton.BuildTools | Azure Cloud Services derleme araçları | 15.7.27617.1 | Önerilen
Microsoft.VisualStudio.Component.CloudExplorer | Cloud Explorer | 15.9.28230.55 | Önerilen
Microsoft.VisualStudio.Component.Common.Azure.Tools | Bağlantı ve yayımlama araçları | 15.9.28107.0 | Önerilen
Microsoft.VisualStudio.Component.DockerTools | Kapsayıcı geliştirme araçları | 15.8.27906.1 | Önerilen
Microsoft.VisualStudio.Component.DockerTools.BuildTools | Kapsayıcı geliştirme araçları - derleme araçları | 15.7.27617.1 | Önerilen
Microsoft.VisualStudio.Component.IISExpress | IIS Express  | 15.0.26208.0 | Önerilen
Microsoft.VisualStudio.Component.JavaScript.Diagnostics | JavaScript tanılamaları | 15.8.27729.1 | Önerilen
Microsoft.VisualStudio.Component.JavaScript.TypeScript | JavaScript ve TypeScript dil desteği | 15.9.28125.51 | Önerilen
Microsoft.VisualStudio.Component.ManagedDesktop.Core | Yönetilen masaüstü iş yükü Çekirdeği | 15.8.27729.1 | Önerilen
Microsoft.VisualStudio.Component.NuGet | NuGet Paket Yöneticisi | 15.9.28016.0 | Önerilen
Microsoft.VisualStudio.Component.PortableLibrary | .NET taşınabilir kitaplık targeting pack | 15.6.27309.0 | Önerilen
Microsoft.VisualStudio.Component.Roslyn.Compiler | C# ve Visual Basic Roslyn derleyicileri | 15.6.27309.0 | Önerilen
Microsoft.VisualStudio.Component.Roslyn.LanguageServices | C# ve Visual Basic | 15.8.27729.1 | Önerilen
Microsoft.VisualStudio.Component.SQL.ADAL | SQL ADAL çalışma zamanı | 15.6.27406.0 | Önerilen
Microsoft.VisualStudio.Component.SQL.CLR | SQL Server için CLR veri türleri | 15.0.26208.0 | Önerilen
Microsoft.VisualStudio.Component.SQL.CMDUtils | SQL Server komut satırı yardımcı programları | 15.0.26208.0 | Önerilen
Microsoft.VisualStudio.Component.SQL.DataSources | Veri kaynakları için SQL Server desteği | 15.0.26621.2 | Önerilen
Microsoft.VisualStudio.Component.SQL.LocalDB.Runtime | SQL Server Express 2016 LocalDB | 15.7.27617.1 | Önerilen
Microsoft.VisualStudio.Component.SQL.NCLI | SQL Server yerel istemcisi | 15.0.26208.0 | Önerilen
Microsoft.VisualStudio.Component.SQL.SSDT | SQL Server Veri Araçları | 15.9.28107.0 | Önerilen
Microsoft.VisualStudio.Component.Static.Analysis.Tools | Statik analiz araçları | 15.0.26208.0 | Önerilen
Microsoft.VisualStudio.Component.TextTemplating | Metin şablonu dönüştürme | 15.0.26208.0 | Önerilen
Microsoft.VisualStudio.Component.TypeScript.3.1 | 3.1 TypeScript SDK'sı | 15.0.28218.60 | Önerilen
Microsoft.VisualStudio.Component.VisualStudioData | Veri kaynakları ve hizmet başvuruları | 15.6.27406.0 | Önerilen
Microsoft.VisualStudio.Component.Web | ASP.NET ve web geliştirme araçları | 15.8.27825.0 | Önerilen
Microsoft.VisualStudio.ComponentGroup.Web | ASP.NET ve web geliştirme araçları önkoşulları | 15.9.28219.51 | Önerilen
Microsoft.VisualStudio.ComponentGroup.WebToolsExtensions | ASP.NET ve web geliştirme | 15.8.27825.0 | Önerilen
Microsoft.VisualStudio.Component.FSharp.Desktop | F#Masaüstü dil desteği | 15.8.27825.0 | İsteğe Bağlı

## <a name="data-science-and-analytical-applications"></a>Veri bilimi ve analitik uygulamalar

**KİMLİĞİ:** Microsoft.VisualStudio.Workload.DataScience

**Açıklama:** Diller ve Python, R dahil olmak üzere veri bilimi uygulamaları oluşturmaya yönelik araçlar ve F#.

### <a name="components-included-by-this-workload"></a>Bu iş yükü tarafından bulunan bileşenler

Bileşen kimliği | Ad | Sürüm | Bağımlılık türü
--- | --- | --- | ---
Component.Anaconda3.x64 | Anaconda3 64-bit (5.2.0) | 5.2.0 | Önerilen
Microsoft.Component.CookiecutterTools | Cookiecutter şablonu desteği | 15.0.26621.2 | Önerilen
Microsoft.Component.PythonTools | Python dil desteği | 15.0.26823.1 | Önerilen
Microsoft.Component.PythonTools.Web | Python web desteği | 15.9.28107.0 | Önerilen
Microsoft.Net.Component.4.6.1.TargetingPack | .NET framework 4.6.1 targeting pack | 15.6.27406.0 | Önerilen
Microsoft.VisualStudio.Component.Common.Azure.Tools | Bağlantı ve yayımlama araçları | 15.9.28107.0 | Önerilen
Microsoft.VisualStudio.Component.FSharp.Desktop | F#Masaüstü dil desteği | 15.8.27825.0 | Önerilen
Microsoft.VisualStudio.Component.JavaScript.TypeScript | JavaScript ve TypeScript dil desteği | 15.9.28125.51 | Önerilen
Microsoft.VisualStudio.Component.NuGet | NuGet Paket Yöneticisi | 15.9.28016.0 | Önerilen
Microsoft.VisualStudio.Component.R.Open | Microsoft R istemcisi (3.3.2) | 15.6.27406.0 | Önerilen
Microsoft.VisualStudio.Component.RHost | R geliştirme araçları için çalışma zamanı desteği | 15.6.27406.0 | Önerilen
Microsoft.VisualStudio.Component.Roslyn.Compiler | C# ve Visual Basic Roslyn derleyicileri | 15.6.27309.0 | Önerilen
Microsoft.VisualStudio.Component.Roslyn.LanguageServices | C# ve Visual Basic | 15.8.27729.1 | Önerilen
Microsoft.VisualStudio.Component.RTools | R dil desteği | 15.0.26919.1 | Önerilen
Microsoft.VisualStudio.Component.SQL.CLR | SQL Server için CLR veri türleri | 15.0.26208.0 | Önerilen
Microsoft.VisualStudio.Component.Static.Analysis.Tools | Statik analiz araçları | 15.0.26208.0 | Önerilen
Microsoft.VisualStudio.Component.TypeScript.3.1 | 3.1 TypeScript SDK'sı | 15.0.28218.60 | Önerilen
Microsoft.VisualStudio.Component.VisualStudioData | Veri kaynakları ve hizmet başvuruları | 15.6.27406.0 | Önerilen
Microsoft.VisualStudio.Component.WebDeploy | Web Dağıtımı | 15.8.27729.1 | Önerilen
Microsoft.VisualStudio.ComponentGroup.WebToolsExtensions | ASP.NET ve web geliştirme | 15.8.27825.0 | Önerilen
Component.Anaconda2.x64 | Anaconda2 64-bit (5.2.0) | 5.2.0 | İsteğe Bağlı
Component.Anaconda2.x86 | Anaconda2 32-bit (5.2.0) | 5.2.0 | İsteğe Bağlı
Component.Anaconda3.x86 | Anaconda3 32-bit (5.2.0) | 5.2.0 | İsteğe Bağlı
Microsoft.Component.VC.Runtime.UCRTSDK | Windows Evrensel CRT SDK | 15.6.27309.0 | İsteğe Bağlı
Microsoft.ComponentGroup.PythonTools.NativeDevelopment | Python yerel geliştirme araçları | 15.9.28307.102 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Graphics.Tools | DirectX için grafik hata ayıklayıcı ve GPU | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Graphics.Win81 | Grafik araçları Windows 8.1 SDK'sı | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.VC.140 | Masaüstü için VC ++ 2015.3 v14.00 (v140) araç | 15.7.27617.1 | İsteğe Bağlı
Microsoft.VisualStudio.Component.VC.CoreIde | Visual Studio C++ temel özellikler | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.VC.DiagnosticTools | C++ profil oluşturma araçları | 15.0.26823.1 | İsteğe Bağlı
Microsoft.VisualStudio.Component.VC.Tools.x86.x64 | VC ++ 2017 sürüm 15.9 v14.16 en yeni v141 araçları | 15.9.28230.55 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows10SDK | Windows Evrensel C çalışma zamanı | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows10SDK.17763 | Windows 10 SDK (10.0.17763.0) | 15.9.28307.102 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows81SDK | Windows 8.1 SDK | 15.6.27406.0 | İsteğe Bağlı

## <a name="net-desktop-development"></a>.NET masaüstü geliştirme

**KİMLİĞİ:** Microsoft.VisualStudio.Workload.ManagedDesktop

**Açıklama:** WPF, Windows Forms ve konsol uygulamaları kullanarak yapı C#, Visual Basic ve F#.

### <a name="components-included-by-this-workload"></a>Bu iş yükü tarafından bulunan bileşenler

Bileşen kimliği | Ad | Sürüm | Bağımlılık türü
--- | --- | --- | ---
Microsoft.Component.ClickOnce | ClickOnce yayımlama | 15.8.27825.0 | Gerekli
Microsoft.Component.MSBuild | MSBuild | 15.7.27520.0 | Gerekli
Microsoft.Net.Component.4.6.1.SDK | .NET framework 4.6.1 SDK'sı | 15.6.27406.0 | Gerekli
Microsoft.Net.Component.4.6.1.TargetingPack | .NET framework 4.6.1 targeting pack | 15.6.27406.0 | Gerekli
Microsoft.Net.ComponentGroup.DevelopmentPrerequisites | .NET framework 4.6.1 geliştirme araçları | 15.8.27825.0 | Gerekli
Microsoft.VisualStudio.Component.ManagedDesktop.Core | Yönetilen masaüstü iş yükü Çekirdeği | 15.8.27729.1 | Gerekli
Microsoft.VisualStudio.Component.ManagedDesktop.Prerequisites | .NET masaüstü geliştirme araçları | 15.7.27625.0 | Gerekli
Microsoft.VisualStudio.Component.PortableLibrary | .NET taşınabilir kitaplık targeting pack | 15.6.27309.0 | Gerekli
Microsoft.VisualStudio.Component.Roslyn.Compiler | C# ve Visual Basic Roslyn derleyicileri | 15.6.27309.0 | Gerekli
Microsoft.VisualStudio.Component.Roslyn.LanguageServices | C# ve Visual Basic | 15.8.27729.1 | Gerekli
Microsoft.VisualStudio.Component.SQL.CLR | SQL Server için CLR veri türleri | 15.0.26208.0 | Gerekli
Microsoft.VisualStudio.Component.Static.Analysis.Tools | Statik analiz araçları | 15.0.26208.0 | Gerekli
Microsoft.VisualStudio.Component.TextTemplating | Metin şablonu dönüştürme | 15.0.26208.0 | Gerekli
Microsoft.VisualStudio.Component.VisualStudioData | Veri kaynakları ve hizmet başvuruları | 15.6.27406.0 | Gerekli
Microsoft.ComponentGroup.Blend | Visual Studio için Blend | 15.6.27406.0 | Önerilen
Microsoft.Net.Component.4.5.1.TargetingPack | .NET framework 4.5.1 targeting pack | 15.6.27406.0 | Önerilen
Microsoft.Net.Component.4.5.2.TargetingPack | .NET framework 4.5.2 targeting pack | 15.6.27406.0 | Önerilen
Microsoft.Net.Component.4.5.TargetingPack | .NET framework 4.5 targeting pack | 15.6.27406.0 | Önerilen
Microsoft.Net.Component.4.6.TargetingPack | .NET framework 4.6 targeting pack | 15.6.27406.0 | Önerilen
Microsoft.Net.Component.4.TargetingPack | .NET framework 4 targeting pack | 15.6.27406.0 | Önerilen
Microsoft.Net.ComponentGroup.TargetingPacks.Common | .NET framework 4-4.6 geliştirme araçları | 15.6.27406.0 | Önerilen
Microsoft.VisualStudio.Component.Debugger.JustInTime | Just-In-Time hata ayıklayıcı | 15.0.27005.2 | Önerilen
Microsoft.VisualStudio.Component.DiagnosticTools | .NET profil oluşturma araçları | 15.8.27729.1 | Önerilen
Microsoft.VisualStudio.Component.EntityFramework | Entity Framework 6 araçları | 15.6.27406.0 | Önerilen
Microsoft.VisualStudio.Component.IntelliTrace.FrontEnd | IntelliTrace | 15.8.27729.1 | Önerilen
Microsoft.VisualStudio.Component.LiveUnitTesting | Live Unit Testing | 15.0.26720.2 | Önerilen
Component.Dotfuscator | PreEmptive koruma - Dotfuscator | 15.0.26208.0 | İsteğe Bağlı
Component.Microsoft.VisualStudio.RazorExtension | Razor dil Hizmetleri | 15.0.26720.2 | İsteğe Bağlı
Component.Microsoft.Web.LibraryManager | Kitaplık Yöneticisi | 15.8.27705.0 | İsteğe Bağlı
Component.WebSocket | WebSocket4Net | 15.0.26606.0 | İsteğe Bağlı
Microsoft.Net.Component.4.6.2.SDK | .NET framework 4.6.2 SDK'sı | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Component.4.6.2.TargetingPack | .NET framework 4.6.2 targeting pack | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Component.4.7.1.SDK | .NET framework 4.7.1 SDK'sı | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Component.4.7.1.TargetingPack | .NET framework 4.7.1 targeting pack | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Component.4.7.2.SDK | .NET framework 4.7.2 SDK'sı | 15.8.27825.0 | İsteğe Bağlı
Microsoft.Net.Component.4.7.2.TargetingPack | .NET framework 4.7.2 targeting pack | 15.8.27825.0 | İsteğe Bağlı
Microsoft.Net.Component.4.7.SDK | .NET framework 4.7 SDK'sı | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Component.4.7.TargetingPack | .NET framework 4.7 targeting pack | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.ComponentGroup.4.6.2.DeveloperTools | .NET framework 4.6.2 geliştirme araçları | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.ComponentGroup.4.7.1.DeveloperTools | .NET framework 4.7.1 geliştirme araçları | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.ComponentGroup.4.7.2.DeveloperTools | .NET framework 4.7.2 geliştirme araçları | 15.8.27825.0 | İsteğe Bağlı
Microsoft.Net.ComponentGroup.4.7.DeveloperTools | .NET framework 4.7 geliştirme araçları | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Core.Component.SDK | .NET core 2.0 geliştirme araçları | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Core.Component.SDK.1x | .NET core 1.0-1.1 geliştirme araçları | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Core.Component.SDK.2.1 | .NET core 2.1 geliştirme araçları | 15.8.27924.0 | İsteğe Bağlı
Microsoft.NetCore.ComponentGroup.DevelopmentTools | .NET core 2.0 geliştirme araçları | 15.8.27729.1 | İsteğe Bağlı
Microsoft.NetCore.ComponentGroup.DevelopmentTools.2.1 | .NET core 2.1 geliştirme araçları | 15.8.27924.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.CodeClone | Kod kopyası | 15.0.26208.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.CodeMap | Kod Haritası | 15.0.26208.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Common.Azure.Tools | Bağlantı ve yayımlama araçları | 15.9.28107.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.DependencyValidation.Enterprise | Canlı bağımlılık doğrulama | 15.0.26208.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.DockerTools | Kapsayıcı geliştirme araçları | 15.8.27906.1 | İsteğe Bağlı
Microsoft.VisualStudio.Component.DockerTools.BuildTools | Kapsayıcı geliştirme araçları - derleme araçları | 15.7.27617.1 | İsteğe Bağlı
Microsoft.VisualStudio.Component.FSharp | F#dil desteği | 15.8.27825.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.FSharp.Desktop | F#Masaüstü dil desteği | 15.8.27825.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.GraphDocument | DGML Düzenleyici | 15.0.27005.2 | İsteğe Bağlı
Microsoft.VisualStudio.Component.IISExpress | IIS Express  | 15.0.26208.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.JavaScript.Diagnostics | JavaScript tanılamaları | 15.8.27729.1 | İsteğe Bağlı
Microsoft.VisualStudio.Component.JavaScript.TypeScript | JavaScript ve TypeScript dil desteği | 15.9.28125.51 | İsteğe Bağlı
Microsoft.VisualStudio.Component.NuGet | NuGet Paket Yöneticisi | 15.9.28016.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.SQL.ADAL | SQL ADAL çalışma zamanı | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.SQL.CMDUtils | SQL Server komut satırı yardımcı programları | 15.0.26208.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.SQL.DataSources | Veri kaynakları için SQL Server desteği | 15.0.26621.2 | İsteğe Bağlı
Microsoft.VisualStudio.Component.SQL.LocalDB.Runtime | SQL Server Express 2016 LocalDB | 15.7.27617.1 | İsteğe Bağlı
Microsoft.VisualStudio.Component.SQL.NCLI | SQL Server yerel istemcisi | 15.0.26208.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.SQL.SSDT | SQL Server Veri Araçları | 15.9.28107.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.TypeScript.3.1 | 3.1 TypeScript SDK'sı | 15.0.28218.60 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Wcf.Tooling | Windows Communication Foundation | 15.8.27924.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Web | ASP.NET ve web geliştirme araçları | 15.8.27825.0 | İsteğe Bağlı
Microsoft.VisualStudio.ComponentGroup.ArchitectureTools.Managed | Mimari ve analiz araçları | 15.0.26208.0 | İsteğe Bağlı
Microsoft.VisualStudio.ComponentGroup.Web | ASP.NET ve web geliştirme araçları önkoşulları | 15.9.28219.51 | İsteğe Bağlı
Microsoft.VisualStudio.ComponentGroup.WebToolsExtensions | ASP.NET ve web geliştirme | 15.8.27825.0 | İsteğe Bağlı

## <a name="game-development-with-unity"></a>Unity ile oyun geliştirme

**KİMLİĞİ:** Microsoft.VisualStudio.Workload.ManagedGame

**Açıklama:** Güçlü bir platformlar arası geliştirme ortamı olan Unity ile 2B ve 3B oyunlar oluşturun.

### <a name="components-included-by-this-workload"></a>Bu iş yükü tarafından bulunan bileşenler

Bileşen kimliği | Ad | Sürüm | Bağımlılık türü
--- | --- | --- | ---
Microsoft.Net.Component.3.5.DeveloperTools | .NET framework 3.5 geliştirme araçları | 15.6.27406.0 | Gerekli
Microsoft.Net.Component.4.7.1.TargetingPack | .NET framework 4.7.1 targeting pack | 15.6.27406.0 | Gerekli
Microsoft.VisualStudio.Component.NuGet | NuGet Paket Yöneticisi | 15.9.28016.0 | Gerekli
Microsoft.VisualStudio.Component.Roslyn.Compiler | C# ve Visual Basic Roslyn derleyicileri | 15.6.27309.0 | Gerekli
Microsoft.VisualStudio.Component.Roslyn.LanguageServices | C# ve Visual Basic | 15.8.27729.1 | Gerekli
Microsoft.VisualStudio.Component.Static.Analysis.Tools | Statik analiz araçları | 15.0.26208.0 | Gerekli
Microsoft.VisualStudio.Component.Unity | Unity için Visual Studio Araçları | 15.7.27617.1 | Gerekli
Component.UnityEngine.x64 | Unity 2018.3 64 bit Düzenleyici | 15.9.28307.271 | Önerilen
Component.UnityEngine.x86 | Unity 5.6 32 bit Düzenleyici | 15.6.27406.0 | Önerilen

## <a name="linux-development-with-c"></a>C++ ile Linux geliştirme

**KİMLİĞİ:** Microsoft.VisualStudio.Workload.NativeCrossPlat

**Açıklama:** Oluşturun ve bir Linux ortamında çalışan uygulamalarda hata ayıklayın.

### <a name="components-included-by-this-workload"></a>Bu iş yükü tarafından bulunan bileşenler

Bileşen kimliği | Ad | Sürüm | Bağımlılık türü
--- | --- | --- | ---
Component.MDD.Linux | Linux geliştirme için Visual C++ | 15.6.27406.0 | Gerekli
Microsoft.VisualStudio.Component.VC.CoreIde | Visual Studio C++ temel özellikler | 15.6.27406.0 | Gerekli
Microsoft.VisualStudio.Component.Windows10SDK | Windows Evrensel C çalışma zamanı | 15.6.27406.0 | Gerekli
Component.Linux.CMake | CMake ve Linux için Visual C++ Araçları | 15.9.28307.102 | Önerilen
Microsoft.VisualStudio.Component.Static.Analysis.Tools | Statik analiz araçları | 15.0.26208.0 | Önerilen
Microsoft.VisualStudio.Component.VC.Tools.x86.x64 | VC ++ 2017 sürüm 15.9 v14.16 en yeni v141 araçları | 15.9.28230.55 | Önerilen
Microsoft.VisualStudio.Component.Windows10SDK.17763 | Windows 10 SDK (10.0.17763.0) | 15.9.28307.102 | Önerilen
Microsoft.VisualStudio.ComponentGroup.WebToolsExtensions | ASP.NET ve web geliştirme | 15.8.27825.0 | Önerilen
Component.MDD.Linux.GCC.arm | Gömülü geliştirme ve IOT geliştirmesi | 15.6.27309.0 | İsteğe Bağlı

## <a name="desktop-development-with-c"></a>C++ ile masaüstü geliştirme

**KİMLİĞİ:** Microsoft.VisualStudio.Workload.NativeDesktop

**Açıklama:** Microsoft C++ araç takımı, ATL veya MFC kullanarak Windows Masaüstü uygulamaları oluşturun.

### <a name="components-included-by-this-workload"></a>Bu iş yükü tarafından bulunan bileşenler

Bileşen kimliği | Ad | Sürüm | Bağımlılık türü
--- | --- | --- | ---
Microsoft.Component.MSBuild | MSBuild | 15.7.27520.0 | Gerekli
Microsoft.VisualStudio.Component.ClassDesigner | Sınıf Tasarımcısı | 15.0.26208.0 | Gerekli
Microsoft.VisualStudio.Component.CodeMap | Kod Haritası | 15.0.26208.0 | Gerekli
Microsoft.VisualStudio.Component.GraphDocument | DGML Düzenleyici | 15.0.27005.2 | Gerekli
Microsoft.VisualStudio.Component.Roslyn.Compiler | C# ve Visual Basic Roslyn derleyicileri | 15.6.27309.0 | Gerekli
Microsoft.VisualStudio.Component.SQL.LocalDB.Runtime | SQL Server Express 2016 LocalDB | 15.7.27617.1 | Gerekli
Microsoft.VisualStudio.Component.SQL.NCLI | SQL Server yerel istemcisi | 15.0.26208.0 | Gerekli
Microsoft.VisualStudio.Component.TextTemplating | Metin şablonu dönüştürme | 15.0.26208.0 | Gerekli
Microsoft.VisualStudio.Component.VC.CoreIde | Visual Studio C++ temel özellikler | 15.6.27406.0 | Gerekli
Microsoft.VisualStudio.Component.VC.Redist.14.Latest | Visual C++ 2017 yeniden dağıtılabilir güncelleştirme | 15.6.27406.0 | Gerekli
Microsoft.VisualStudio.ComponentGroup.ArchitectureTools.Native | C++ için Mimari Araçları | 15.0.26208.0 | Gerekli
Microsoft.VisualStudio.ComponentGroup.NativeDesktop.Core | Visual C++ temel masaüstü özellikleri | 15.8.27729.1 | Gerekli
Microsoft.VisualStudio.Component.Debugger.JustInTime | Just-In-Time hata ayıklayıcı | 15.0.27005.2 | Önerilen
Microsoft.VisualStudio.Component.Graphics.Tools | DirectX için grafik hata ayıklayıcı ve GPU | 15.6.27406.0 | Önerilen
Microsoft.VisualStudio.Component.Graphics.Win81 | Grafik araçları Windows 8.1 SDK'sı | 15.6.27406.0 | Önerilen
Microsoft.VisualStudio.Component.IntelliTrace.FrontEnd | IntelliTrace | 15.8.27729.1 | Önerilen
Microsoft.VisualStudio.Component.NuGet | NuGet Paket Yöneticisi | 15.9.28016.0 | Önerilen
Microsoft.VisualStudio.Component.Static.Analysis.Tools | Statik analiz araçları | 15.0.26208.0 | Önerilen
Microsoft.VisualStudio.Component.VC.ATL | X86 ve x64 için Visual C++ ATL | 15.7.27625.0 | Önerilen
Microsoft.VisualStudio.Component.VC.CMake.Project | CMake için Visual C++ Araçları | 15.9.28307.102 | Önerilen
Microsoft.VisualStudio.Component.VC.DiagnosticTools | C++ profil oluşturma araçları | 15.0.26823.1 | Önerilen
Microsoft.VisualStudio.Component.VC.TestAdapterForBoostTest | Boost.Test için test bağdaştırıcısı | 15.8.27906.1 | Önerilen
Microsoft.VisualStudio.Component.VC.TestAdapterForGoogleTest | Google Test için test bağdaştırıcısı | 15.8.27906.1 | Önerilen
Microsoft.VisualStudio.Component.VC.Tools.x86.x64 | VC ++ 2017 sürüm 15.9 v14.16 en yeni v141 araçları | 15.9.28230.55 | Önerilen
Microsoft.VisualStudio.Component.Windows10SDK.17763 | Windows 10 SDK (10.0.17763.0) | 15.9.28307.102 | Önerilen
Microsoft.VisualStudio.ComponentGroup.WebToolsExtensions | ASP.NET ve web geliştirme | 15.8.27825.0 | Önerilen
Component.Incredibuild | IncrediBuild - derleme hızlandırma | 15.7.27617.1 | İsteğe Bağlı
Component.IncredibuildMenu | IncrediBuildMenu | 1.5.0.2 | İsteğe Bağlı
Microsoft.Component.VC.Runtime.UCRTSDK | Windows Evrensel CRT SDK | 15.6.27309.0 | İsteğe Bağlı
Microsoft.Net.Component.4.6.1.SDK | .NET framework 4.6.1 SDK'sı | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Component.4.6.1.TargetingPack | .NET framework 4.6.1 targeting pack | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.VC.140 | Masaüstü için VC ++ 2015.3 v14.00 (v140) araç | 15.7.27617.1 | İsteğe Bağlı
Microsoft.VisualStudio.Component.VC.ATLMFC | X86 ve x64 için Visual C++ MFC | 15.7.27625.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.VC.CLI.Support | C + +/ CLI desteği | 15.6.27309.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.VC.Modules.x86.x64 | (Deneysel) standart kitaplık modülleri | 15.6.27309.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows10SDK.10240 | Windows 10 SDK (10.0.10240.0) | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows10SDK.10586 | Windows 10 SDK (10.0.10586.0) | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows10SDK.14393 | Windows 10 SDK (10.0.14393.0) | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows10SDK.15063.Desktop | Windows 10 SDK (10.0.15063.0) Masaüstü C++ [x86 ve x64] için | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows10SDK.15063.UWP | Windows 10 SDK (10.0.15063.0) UWP için: C#, VB, JS | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows10SDK.15063.UWP.Native | Windows 10 SDK (10.0.15063.0) UWP için: C++ | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows10SDK.16299.Desktop | Windows 10 SDK (10.0.16299.0) Masaüstü C++ [x86 ve x64] için | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows10SDK.16299.Desktop.arm | Windows 10 SDK (10.0.16299.0) Masaüstü C++ [ARM ve ARM64] için | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows10SDK.16299.UWP | Windows 10 SDK (10.0.16299.0) UWP için: C#, VB, JS | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows10SDK.16299.UWP.Native | Windows 10 SDK (10.0.16299.0) UWP için: C++ | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows10SDK.17134 | Windows 10 SDK (10.0.17134.0) | 15.9.28307.102 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows81SDK | Windows 8.1 SDK | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.WinXP | C++ için Windows XP desteği | 15.8.27924.0 | İsteğe Bağlı
Microsoft.VisualStudio.ComponentGroup.NativeDesktop.Win81 | Windows 8.1 SDK ve UCRT SDK | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.ComponentGroup.NativeDesktop.WinXP | C++ için Windows XP desteği | 15.8.27705.0 | İsteğe Bağlı
Microsoft.VisualStudio.ComponentGroup.Windows10SDK.15063 | Windows 10 SDK (10.0.15063.0) | 15.8.27825.0 | İsteğe Bağlı
Microsoft.VisualStudio.ComponentGroup.Windows10SDK.16299 | Windows 10 SDK (10.0.16299.0) | 15.8.27825.0 | İsteğe Bağlı

## <a name="game-development-with-c"></a>C++ ile oyun geliştirme

**KİMLİĞİ:** Microsoft.VisualStudio.Workload.NativeGame

**Açıklama:** DirectX, Unreal veya Cocos2d tarafından desteklenen profesyonel oyunlar oluşturmak için C++'ın gücünü kullanın.

### <a name="components-included-by-this-workload"></a>Bu iş yükü tarafından bulunan bileşenler

Bileşen kimliği | Ad | Sürüm | Bağımlılık türü
--- | --- | --- | ---
Microsoft.VisualStudio.Component.Static.Analysis.Tools | Statik analiz araçları | 15.0.26208.0 | Gerekli
Microsoft.VisualStudio.Component.VC.CoreIde | Visual Studio C++ temel özellikler | 15.6.27406.0 | Gerekli
Microsoft.VisualStudio.Component.VC.Redist.14.Latest | Visual C++ 2017 yeniden dağıtılabilir güncelleştirme | 15.6.27406.0 | Gerekli
Microsoft.VisualStudio.Component.VC.Tools.x86.x64 | VC ++ 2017 sürüm 15.9 v14.16 en yeni v141 araçları | 15.9.28230.55 | Gerekli
Microsoft.VisualStudio.Component.Windows10SDK | Windows Evrensel C çalışma zamanı | 15.6.27406.0 | Gerekli
Microsoft.VisualStudio.Component.Graphics.Tools | DirectX için grafik hata ayıklayıcı ve GPU | 15.6.27406.0 | Önerilen
Microsoft.VisualStudio.Component.Graphics.Win81 | Grafik araçları Windows 8.1 SDK'sı | 15.6.27406.0 | Önerilen
Microsoft.VisualStudio.Component.IntelliTrace.FrontEnd | IntelliTrace | 15.8.27729.1 | Önerilen
Microsoft.VisualStudio.Component.VC.DiagnosticTools | C++ profil oluşturma araçları | 15.0.26823.1 | Önerilen
Microsoft.VisualStudio.Component.Windows10SDK.17763 | Windows 10 SDK (10.0.17763.0) | 15.9.28307.102 | Önerilen
Component.Android.NDK.R12B | Android NDK (R12B) | 12.1.10 | İsteğe Bağlı
Component.Android.SDK23.Private | Android SDK kurulumu (API düzeyi 23) (JavaScript ile Mobil Geliştirme için yerel yükleme / C++) | 15.9.28016.0 | İsteğe Bağlı
Component.Ant | Apache Ant (1.9.3) | 1.9.3.8 | İsteğe Bağlı
Component.Cocos | Cocos | 15.0.26906.1 | İsteğe Bağlı
Component.Incredibuild | IncrediBuild - derleme hızlandırma | 15.7.27617.1 | İsteğe Bağlı
Component.IncredibuildMenu | IncrediBuildMenu | 1.5.0.2 | İsteğe Bağlı
Component.MDD.Android | C++ Android geliştirici araçları | 15.0.26606.0 | İsteğe Bağlı
Component.OpenJDK | Microsoft Dağıtım OpenJDK | 15.9.28125.51 | İsteğe Bağlı
Component.Unreal | Unreal Engine yükleyicisi | 15.8.27729.1 | İsteğe Bağlı
Component.Unreal.Android | Unreal Engine için Visual Studio Android desteği | 15.9.28307.341 | İsteğe Bağlı
Microsoft.Component.VC.Runtime.UCRTSDK | Windows Evrensel CRT SDK | 15.6.27309.0 | İsteğe Bağlı
Microsoft.Net.Component.4.5.1.TargetingPack | .NET framework 4.5.1 targeting pack | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Component.4.5.2.TargetingPack | .NET framework 4.5.2 targeting pack | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Component.4.5.TargetingPack | .NET framework 4.5 targeting pack | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Component.4.6.1.SDK | .NET framework 4.6.1 SDK'sı | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Component.4.6.1.TargetingPack | .NET framework 4.6.1 targeting pack | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Component.4.6.TargetingPack | .NET framework 4.6 targeting pack | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Component.4.TargetingPack | .NET framework 4 targeting pack | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.ComponentGroup.DevelopmentPrerequisites | .NET framework 4.6.1 geliştirme araçları | 15.8.27825.0 | İsteğe Bağlı
Microsoft.Net.ComponentGroup.TargetingPacks.Common | .NET framework 4-4.6 geliştirme araçları | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.NuGet.BuildTools | NuGet hedefleri ve derleme görevleri | 15.9.28016.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Roslyn.Compiler | C# ve Visual Basic Roslyn derleyicileri | 15.6.27309.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Roslyn.LanguageServices | C# ve Visual Basic | 15.8.27729.1 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows10SDK.10240 | Windows 10 SDK (10.0.10240.0) | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows10SDK.10586 | Windows 10 SDK (10.0.10586.0) | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows10SDK.14393 | Windows 10 SDK (10.0.14393.0) | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows10SDK.15063.Desktop | Windows 10 SDK (10.0.15063.0) Masaüstü C++ [x86 ve x64] için | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows10SDK.15063.UWP | Windows 10 SDK (10.0.15063.0) UWP için: C#, VB, JS | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows10SDK.15063.UWP.Native | Windows 10 SDK (10.0.15063.0) UWP için: C++ | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows10SDK.16299.Desktop | Windows 10 SDK (10.0.16299.0) Masaüstü C++ [x86 ve x64] için | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows10SDK.16299.Desktop.arm | Windows 10 SDK (10.0.16299.0) Masaüstü C++ [ARM ve ARM64] için | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows10SDK.16299.UWP | Windows 10 SDK (10.0.16299.0) UWP için: C#, VB, JS | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows10SDK.16299.UWP.Native | Windows 10 SDK (10.0.16299.0) UWP için: C++ | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows10SDK.17134 | Windows 10 SDK (10.0.17134.0) | 15.9.28307.102 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows81SDK | Windows 8.1 SDK | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.ComponentGroup.NativeDesktop.Win81 | Windows 8.1 SDK ve UCRT SDK | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.ComponentGroup.Windows10SDK.15063 | Windows 10 SDK (10.0.15063.0) | 15.8.27825.0 | İsteğe Bağlı
Microsoft.VisualStudio.ComponentGroup.Windows10SDK.16299 | Windows 10 SDK (10.0.16299.0) | 15.8.27825.0 | İsteğe Bağlı

## <a name="mobile-development-with-c"></a>C++ ile Mobil Geliştirme

**KİMLİĞİ:** Microsoft.VisualStudio.Workload.NativeMobile

**Açıklama:** İOS, Android veya C++ kullanarak Windows için platformlar arası uygulamalar oluşturun.

### <a name="components-included-by-this-workload"></a>Bu iş yükü tarafından bulunan bileşenler

Bileşen kimliği | Ad | Sürüm | Bağımlılık türü
--- | --- | --- | ---
Component.Android.SDK19.Private | Android SDK kurulumu (API düzey 19) (JavaScript ile Mobil Geliştirme için yerel yükleme / C++) | 15.9.28107.0 | Gerekli
Component.Android.SDK21.Private | Android SDK kurulumu (API düzey 21) (JavaScript ile Mobil Geliştirme için yerel yükleme / C++) | 15.9.28016.0 | Gerekli
Component.Android.SDK22.Private | Android SDK kurulumu (API düzeyi 22) (JavaScript ile Mobil Geliştirme için yerel yükleme / C++) | 15.9.28016.0 | Gerekli
Component.Android.SDK23.Private | Android SDK kurulumu (API düzeyi 23) (JavaScript ile Mobil Geliştirme için yerel yükleme / C++) | 15.9.28016.0 | Gerekli
Component.Android.SDK25.Private | Android SDK kurulumu (API düzeyi 25) (JavaScript ile Mobil Geliştirme için yerel yükleme / C++) | 15.9.28016.0 | Gerekli
Component.OpenJDK | Microsoft Dağıtım OpenJDK | 15.9.28125.51 | Gerekli
Microsoft.VisualStudio.Component.VC.CoreIde | Visual Studio C++ temel özellikler | 15.6.27406.0 | Gerekli
Component.Android.NDK.R15C | Android NDK (R15C) | 15.2.1 | Önerilen
Component.Ant | Apache Ant (1.9.3) | 1.9.3.8 | Önerilen
Component.MDD.Android | C++ Android geliştirici araçları | 15.0.26606.0 | Önerilen
Component.Android.NDK.R12B | Android NDK (R12B) | 12.1.10 | İsteğe Bağlı
Component.Android.NDK.R12B_3264 | Android NDK (R12B) (32 bit) | 12.1.11 | İsteğe Bağlı
Component.Android.NDK.R13B | Android NDK (R13B) | 13.1.7 | İsteğe Bağlı
Component.Android.NDK.R13B_3264 | Android NDK (R13B) (32 bit) | 13.1.8 | İsteğe Bağlı
Component.Android.NDK.R15C_3264 | Android NDK (R15C) (32 bit) | 15.2.1 | İsteğe Bağlı
Component.Google.Android.Emulator.API23.Private | Google Android Emulator (API düzeyi 23) (yerel kurulum) | 15.6.27413.0 | İsteğe Bağlı
Component.HAXM.Private | Intel donanım hızlandırılmış yürütme Yöneticisi (HAXM) (yerel kurulum) | 15.9.28307.421 | İsteğe Bağlı
Component.Incredibuild | IncrediBuild - derleme hızlandırma | 15.7.27617.1 | İsteğe Bağlı
Component.IncredibuildMenu | IncrediBuildMenu | 1.5.0.2 | İsteğe Bağlı
Component.MDD.IOS | C++ iOS geliştirici araçları | 15.0.26621.2 | İsteğe Bağlı

## <a name="net-core-cross-platform-development"></a>.NET core platformlar arası geliştirme

**KİMLİĞİ:** Microsoft.VisualStudio.Workload.NetCoreTools

**Açıklama:** .NET Core, ASP.NET Core, HTML/JavaScript ve Docker desteği içeren kapsayıcıları kullanarak platformlar arası uygulamalar oluşturun.

### <a name="components-included-by-this-workload"></a>Bu iş yükü tarafından bulunan bileşenler

Bileşen kimliği | Ad | Sürüm | Bağımlılık türü
--- | --- | --- | ---
Component.Microsoft.VisualStudio.RazorExtension | Razor dil Hizmetleri | 15.0.26720.2 | Gerekli
Component.Microsoft.Web.LibraryManager | Kitaplık Yöneticisi | 15.8.27705.0 | Gerekli
Component.WebSocket | WebSocket4Net | 15.0.26606.0 | Gerekli
Microsoft.Component.ClickOnce | ClickOnce yayımlama | 15.8.27825.0 | Gerekli
Microsoft.Component.MSBuild | MSBuild | 15.7.27520.0 | Gerekli
Microsoft.Net.Component.4.5.2.TargetingPack | .NET framework 4.5.2 targeting pack | 15.6.27406.0 | Gerekli
Microsoft.Net.Component.4.5.TargetingPack | .NET framework 4.5 targeting pack | 15.6.27406.0 | Gerekli
Microsoft.Net.Component.4.6.1.SDK | .NET framework 4.6.1 SDK'sı | 15.6.27406.0 | Gerekli
Microsoft.Net.Component.4.6.1.TargetingPack | .NET framework 4.6.1 targeting pack | 15.6.27406.0 | Gerekli
Microsoft.Net.ComponentGroup.DevelopmentPrerequisites | .NET framework 4.6.1 geliştirme araçları | 15.8.27825.0 | Gerekli
Microsoft.Net.Core.Component.SDK.2.1 | .NET core 2.1 geliştirme araçları | 15.8.27924.0 | Gerekli
Microsoft.NetCore.ComponentGroup.DevelopmentTools.2.1 | .NET core 2.1 geliştirme araçları | 15.8.27924.0 | Gerekli
Microsoft.NetCore.ComponentGroup.Web.2.1 | .NET core 2.1 geliştirme araçları | 15.8.27924.0 | Gerekli
Microsoft.VisualStudio.Component.Common.Azure.Tools | Bağlantı ve yayımlama araçları | 15.9.28107.0 | Gerekli
Microsoft.VisualStudio.Component.DockerTools | Kapsayıcı geliştirme araçları | 15.8.27906.1 | Gerekli
Microsoft.VisualStudio.Component.DockerTools.BuildTools | Kapsayıcı geliştirme araçları - derleme araçları | 15.7.27617.1 | Gerekli
Microsoft.VisualStudio.Component.FSharp | F#dil desteği | 15.8.27825.0 | Gerekli
Microsoft.VisualStudio.Component.FSharp.WebTemplates | F#web projeleri için dil desteği | 15.9.28307.421 | Gerekli
Microsoft.VisualStudio.Component.IISExpress | IIS Express  | 15.0.26208.0 | Gerekli
Microsoft.VisualStudio.Component.JavaScript.Diagnostics | JavaScript tanılamaları | 15.8.27729.1 | Gerekli
Microsoft.VisualStudio.Component.JavaScript.TypeScript | JavaScript ve TypeScript dil desteği | 15.9.28125.51 | Gerekli
Microsoft.VisualStudio.Component.ManagedDesktop.Core | Yönetilen masaüstü iş yükü Çekirdeği | 15.8.27729.1 | Gerekli
Microsoft.VisualStudio.Component.NuGet | NuGet Paket Yöneticisi | 15.9.28016.0 | Gerekli
Microsoft.VisualStudio.Component.PortableLibrary | .NET taşınabilir kitaplık targeting pack | 15.6.27309.0 | Gerekli
Microsoft.VisualStudio.Component.Roslyn.Compiler | C# ve Visual Basic Roslyn derleyicileri | 15.6.27309.0 | Gerekli
Microsoft.VisualStudio.Component.Roslyn.LanguageServices | C# ve Visual Basic | 15.8.27729.1 | Gerekli
Microsoft.VisualStudio.Component.SQL.ADAL | SQL ADAL çalışma zamanı | 15.6.27406.0 | Gerekli
Microsoft.VisualStudio.Component.SQL.CLR | SQL Server için CLR veri türleri | 15.0.26208.0 | Gerekli
Microsoft.VisualStudio.Component.SQL.CMDUtils | SQL Server komut satırı yardımcı programları | 15.0.26208.0 | Gerekli
Microsoft.VisualStudio.Component.SQL.DataSources | Veri kaynakları için SQL Server desteği | 15.0.26621.2 | Gerekli
Microsoft.VisualStudio.Component.SQL.LocalDB.Runtime | SQL Server Express 2016 LocalDB | 15.7.27617.1 | Gerekli
Microsoft.VisualStudio.Component.SQL.NCLI | SQL Server yerel istemcisi | 15.0.26208.0 | Gerekli
Microsoft.VisualStudio.Component.SQL.SSDT | SQL Server Veri Araçları | 15.9.28107.0 | Gerekli
Microsoft.VisualStudio.Component.Static.Analysis.Tools | Statik analiz araçları | 15.0.26208.0 | Gerekli
Microsoft.VisualStudio.Component.TextTemplating | Metin şablonu dönüştürme | 15.0.26208.0 | Gerekli
Microsoft.VisualStudio.Component.TypeScript.3.1 | 3.1 TypeScript SDK'sı | 15.0.28218.60 | Gerekli
Microsoft.VisualStudio.Component.VisualStudioData | Veri kaynakları ve hizmet başvuruları | 15.6.27406.0 | Gerekli
Microsoft.VisualStudio.ComponentGroup.Web | ASP.NET ve web geliştirme araçları önkoşulları | 15.9.28219.51 | Gerekli
Microsoft.VisualStudio.ComponentGroup.WebToolsExtensions | ASP.NET ve web geliştirme | 15.8.27825.0 | Gerekli
Component.Microsoft.VisualStudio.Web.AzureFunctions | Microsoft Azure Web işleri araçları | 15.7.27617.1 | Önerilen
Microsoft.VisualStudio.Component.AppInsights.Tools | Geliştirici analiz araçları | 15.8.27825.0 | Önerilen
Microsoft.VisualStudio.Component.Azure.AuthoringTools | Azure yazma araçları | 15.9.28307.421 | Önerilen
Microsoft.VisualStudio.Component.Azure.ClientLibs | .NET için Azure kitaplıkları | 15.0.26208.0 | Önerilen
Microsoft.VisualStudio.Component.Azure.Compute.Emulator | Azure işlem öykünücüsü | 15.9.28307.421 | Önerilen
Microsoft.VisualStudio.Component.Azure.Storage.Emulator | Azure depolama öykünücüsü | 15.9.28125.51 | Önerilen
Microsoft.VisualStudio.Component.CloudExplorer | Cloud Explorer | 15.9.28230.55 | Önerilen
Microsoft.VisualStudio.Component.Debugger.Snapshot | Anlık görüntü hata ayıklayıcısı | 15.8.28010.0 | Önerilen
Microsoft.VisualStudio.Component.DiagnosticTools | .NET profil oluşturma araçları | 15.8.27729.1 | Önerilen
Microsoft.VisualStudio.Component.IntelliTrace.FrontEnd | IntelliTrace | 15.8.27729.1 | Önerilen
Microsoft.VisualStudio.Component.LiveUnitTesting | Live Unit Testing | 15.0.26720.2 | Önerilen
Microsoft.VisualStudio.Component.Web | ASP.NET ve web geliştirme araçları | 15.8.27825.0 | Önerilen
Microsoft.VisualStudio.Component.WebDeploy | Web Dağıtımı | 15.8.27729.1 | Önerilen
Microsoft.VisualStudio.ComponentGroup.AzureFunctions | Microsoft Azure Web işleri araçları | 15.7.27617.1 | Önerilen
Microsoft.VisualStudio.ComponentGroup.Web.CloudTools | Web geliştirme için bulut araçları | 15.8.27729.1 | Önerilen
Microsoft.Net.Core.Component.SDK | .NET core 2.0 geliştirme araçları | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Core.Component.SDK.1x | .NET core 1.0-1.1 geliştirme araçları | 15.6.27406.0 | İsteğe Bağlı
Microsoft.NetCore.1x.ComponentGroup.Web | Web için .NET core 1.0-1.1 geliştirme araçları | 15.6.27406.0 | İsteğe Bağlı
Microsoft.NetCore.ComponentGroup.DevelopmentTools | .NET core 2.0 geliştirme araçları | 15.8.27729.1 | İsteğe Bağlı
Microsoft.NetCore.ComponentGroup.Web | .NET core 2.0 geliştirme araçları | 15.7.27625.0 | İsteğe Bağlı
Microsoft.VisualStudio.ComponentGroup.IISDevelopment | Geliştirme zamanı IIS desteği | 15.9.28219.51 | İsteğe Bağlı

## <a name="mobile-development-with-net"></a>.NET ile Mobil Geliştirme

**KİMLİĞİ:** Microsoft.VisualStudio.Workload.NetCrossPlat

**Açıklama:** İOS, Android veya Xamarin kullanarak Windows için platformlar arası uygulamalar oluşturun.

### <a name="components-included-by-this-workload"></a>Bu iş yükü tarafından bulunan bileşenler

Bileşen kimliği | Ad | Sürüm | Bağımlılık türü
--- | --- | --- | ---
Component.Xamarin | Xamarin | 15.8.27906.1 | Gerekli
Component.Xamarin.RemotedSimulator | Xamarin uzak simülatör | 15.6.27323.2 | Gerekli
Microsoft.Component.MSBuild | MSBuild | 15.7.27520.0 | Gerekli
Microsoft.Net.Component.4.6.1.SDK | .NET framework 4.6.1 SDK'sı | 15.6.27406.0 | Gerekli
Microsoft.Net.Component.4.6.1.TargetingPack | .NET framework 4.6.1 targeting pack | 15.6.27406.0 | Gerekli
Microsoft.Net.ComponentGroup.DevelopmentPrerequisites | .NET framework 4.6.1 geliştirme araçları | 15.8.27825.0 | Gerekli
Microsoft.Net.Core.Component.SDK | .NET core 2.0 geliştirme araçları | 15.6.27406.0 | Gerekli
Microsoft.NetCore.ComponentGroup.DevelopmentTools | .NET core 2.0 geliştirme araçları | 15.8.27729.1 | Gerekli
Microsoft.VisualStudio.Component.FSharp | F#dil desteği | 15.8.27825.0 | Gerekli
Microsoft.VisualStudio.Component.Merq | Ortak Xamarin iç araçları | 15.8.27924.0 | Gerekli
Microsoft.VisualStudio.Component.MonoDebugger | Mono hata ayıklayıcısı | 15.0.26720.2 | Gerekli
Microsoft.VisualStudio.Component.NuGet | NuGet Paket Yöneticisi | 15.9.28016.0 | Gerekli
Microsoft.VisualStudio.Component.PortableLibrary | .NET taşınabilir kitaplık targeting pack | 15.6.27309.0 | Gerekli
Microsoft.VisualStudio.Component.Roslyn.Compiler | C# ve Visual Basic Roslyn derleyicileri | 15.6.27309.0 | Gerekli
Microsoft.VisualStudio.Component.Roslyn.LanguageServices | C# ve Visual Basic | 15.8.27729.1 | Gerekli
Microsoft.VisualStudio.Component.Static.Analysis.Tools | Statik analiz araçları | 15.0.26208.0 | Gerekli
Microsoft.VisualStudio.ComponentGroup.WebToolsExtensions.TemplateEngine | ASP.NET şablon oluşturma altyapısı | 15.8.27729.1 | Gerekli
Component.Android.SDK27 | Android SDK kurulumu (API düzeyi 27) | 15.9.28016.0 | Önerilen
Component.Google.Android.Emulator.API27 | Google Android Emulator (API düzeyi 27) | 15.9.28307.421 | Önerilen
Component.HAXM | Intel donanım hızlandırılmış yürütme Yöneticisi (HAXM) (genel yükleme) | 15.9.28307.421 | Önerilen
Component.OpenJDK | Microsoft Dağıtım OpenJDK | 15.9.28125.51 | Önerilen
Component.Xamarin.Profiler | Xamarin Profiler | 15.0.27005.2 | Önerilen
Component.Xamarin.Inspector | Xamarin Workbooks | 15.0.26606.0 | İsteğe Bağlı
Microsoft.Component.ClickOnce | ClickOnce yayımlama | 15.8.27825.0 | İsteğe Bağlı
Microsoft.Component.NetFX.Native | .NET Yerel | 15.0.26208.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.AppInsights.Tools | Geliştirici analiz araçları | 15.8.27825.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.CodeClone | Kod kopyası | 15.0.26208.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.CodeMap | Kod Haritası | 15.0.26208.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.DependencyValidation.Enterprise | Canlı bağımlılık doğrulama | 15.0.26208.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.DiagnosticTools | .NET profil oluşturma araçları | 15.8.27729.1 | İsteğe Bağlı
Microsoft.VisualStudio.Component.GraphDocument | DGML Düzenleyici | 15.0.27005.2 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Graphics | Görüntü ve 3B model düzenleyicileri | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.SQL.CLR | SQL Server için CLR veri türleri | 15.0.26208.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.SQL.LocalDB.Runtime | SQL Server Express 2016 LocalDB | 15.7.27617.1 | İsteğe Bağlı
Microsoft.VisualStudio.Component.SQL.NCLI | SQL Server yerel istemcisi | 15.0.26208.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.VisualStudioData | Veri kaynakları ve hizmet başvuruları | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows10SDK.17763 | Windows 10 SDK (10.0.17763.0) | 15.9.28307.102 | İsteğe Bağlı
Microsoft.VisualStudio.ComponentGroup.ArchitectureTools.Managed | Mimari ve analiz araçları | 15.0.26208.0 | İsteğe Bağlı
Microsoft.VisualStudio.ComponentGroup.UWP.Xamarin | Xamarin için evrensel Windows platformu araçları | 15.9.28307.102 | İsteğe Bağlı

## <a name="aspnet-and-web-development"></a>ASP.NET ve web geliştirme

**KİMLİĞİ:** Microsoft.VisualStudio.Workload.NetWeb

**Açıklama:** ASP.NET, ASP.NET Core, HTML/JavaScript ve Docker desteği içeren kapsayıcıları kullanarak web uygulamaları oluşturun.

### <a name="components-included-by-this-workload"></a>Bu iş yükü tarafından bulunan bileşenler

Bileşen kimliği | Ad | Sürüm | Bağımlılık türü
--- | --- | --- | ---
Component.Microsoft.VisualStudio.RazorExtension | Razor dil Hizmetleri | 15.0.26720.2 | Gerekli
Component.Microsoft.Web.LibraryManager | Kitaplık Yöneticisi | 15.8.27705.0 | Gerekli
Component.WebSocket | WebSocket4Net | 15.0.26606.0 | Gerekli
Microsoft.Component.ClickOnce | ClickOnce yayımlama | 15.8.27825.0 | Gerekli
Microsoft.Component.MSBuild | MSBuild | 15.7.27520.0 | Gerekli
Microsoft.Net.Component.4.5.2.TargetingPack | .NET framework 4.5.2 targeting pack | 15.6.27406.0 | Gerekli
Microsoft.Net.Component.4.5.TargetingPack | .NET framework 4.5 targeting pack | 15.6.27406.0 | Gerekli
Microsoft.Net.Component.4.6.1.SDK | .NET framework 4.6.1 SDK'sı | 15.6.27406.0 | Gerekli
Microsoft.Net.Component.4.6.1.TargetingPack | .NET framework 4.6.1 targeting pack | 15.6.27406.0 | Gerekli
Microsoft.Net.ComponentGroup.DevelopmentPrerequisites | .NET framework 4.6.1 geliştirme araçları | 15.8.27825.0 | Gerekli
Microsoft.Net.Core.Component.SDK.2.1 | .NET core 2.1 geliştirme araçları | 15.8.27924.0 | Gerekli
Microsoft.NetCore.ComponentGroup.DevelopmentTools.2.1 | .NET core 2.1 geliştirme araçları | 15.8.27924.0 | Gerekli
Microsoft.NetCore.ComponentGroup.Web.2.1 | .NET core 2.1 geliştirme araçları | 15.8.27924.0 | Gerekli
Microsoft.VisualStudio.Component.Common.Azure.Tools | Bağlantı ve yayımlama araçları | 15.9.28107.0 | Gerekli
Microsoft.VisualStudio.Component.DockerTools | Kapsayıcı geliştirme araçları | 15.8.27906.1 | Gerekli
Microsoft.VisualStudio.Component.DockerTools.BuildTools | Kapsayıcı geliştirme araçları - derleme araçları | 15.7.27617.1 | Gerekli
Microsoft.VisualStudio.Component.FSharp | F#dil desteği | 15.8.27825.0 | Gerekli
Microsoft.VisualStudio.Component.FSharp.WebTemplates | F#web projeleri için dil desteği | 15.9.28307.421 | Gerekli
Microsoft.VisualStudio.Component.IISExpress | IIS Express  | 15.0.26208.0 | Gerekli
Microsoft.VisualStudio.Component.JavaScript.Diagnostics | JavaScript tanılamaları | 15.8.27729.1 | Gerekli
Microsoft.VisualStudio.Component.JavaScript.TypeScript | JavaScript ve TypeScript dil desteği | 15.9.28125.51 | Gerekli
Microsoft.VisualStudio.Component.ManagedDesktop.Core | Yönetilen masaüstü iş yükü Çekirdeği | 15.8.27729.1 | Gerekli
Microsoft.VisualStudio.Component.NuGet | NuGet Paket Yöneticisi | 15.9.28016.0 | Gerekli
Microsoft.VisualStudio.Component.PortableLibrary | .NET taşınabilir kitaplık targeting pack | 15.6.27309.0 | Gerekli
Microsoft.VisualStudio.Component.Roslyn.Compiler | C# ve Visual Basic Roslyn derleyicileri | 15.6.27309.0 | Gerekli
Microsoft.VisualStudio.Component.Roslyn.LanguageServices | C# ve Visual Basic | 15.8.27729.1 | Gerekli
Microsoft.VisualStudio.Component.SQL.ADAL | SQL ADAL çalışma zamanı | 15.6.27406.0 | Gerekli
Microsoft.VisualStudio.Component.SQL.CLR | SQL Server için CLR veri türleri | 15.0.26208.0 | Gerekli
Microsoft.VisualStudio.Component.SQL.CMDUtils | SQL Server komut satırı yardımcı programları | 15.0.26208.0 | Gerekli
Microsoft.VisualStudio.Component.SQL.DataSources | Veri kaynakları için SQL Server desteği | 15.0.26621.2 | Gerekli
Microsoft.VisualStudio.Component.SQL.LocalDB.Runtime | SQL Server Express 2016 LocalDB | 15.7.27617.1 | Gerekli
Microsoft.VisualStudio.Component.SQL.NCLI | SQL Server yerel istemcisi | 15.0.26208.0 | Gerekli
Microsoft.VisualStudio.Component.SQL.SSDT | SQL Server Veri Araçları | 15.9.28107.0 | Gerekli
Microsoft.VisualStudio.Component.Static.Analysis.Tools | Statik analiz araçları | 15.0.26208.0 | Gerekli
Microsoft.VisualStudio.Component.TextTemplating | Metin şablonu dönüştürme | 15.0.26208.0 | Gerekli
Microsoft.VisualStudio.Component.TypeScript.3.1 | 3.1 TypeScript SDK'sı | 15.0.28218.60 | Gerekli
Microsoft.VisualStudio.Component.VisualStudioData | Veri kaynakları ve hizmet başvuruları | 15.6.27406.0 | Gerekli
Microsoft.VisualStudio.Component.Web | ASP.NET ve web geliştirme araçları | 15.8.27825.0 | Gerekli
Microsoft.VisualStudio.ComponentGroup.Web | ASP.NET ve web geliştirme araçları önkoşulları | 15.9.28219.51 | Gerekli
Microsoft.VisualStudio.ComponentGroup.WebToolsExtensions | ASP.NET ve web geliştirme | 15.8.27825.0 | Gerekli
Component.Microsoft.VisualStudio.Web.AzureFunctions | Microsoft Azure Web işleri araçları | 15.7.27617.1 | Önerilen
Microsoft.Net.Component.4.5.1.TargetingPack | .NET framework 4.5.1 targeting pack | 15.6.27406.0 | Önerilen
Microsoft.Net.Component.4.6.TargetingPack | .NET framework 4.6 targeting pack | 15.6.27406.0 | Önerilen
Microsoft.Net.Component.4.TargetingPack | .NET framework 4 targeting pack | 15.6.27406.0 | Önerilen
Microsoft.Net.ComponentGroup.TargetingPacks.Common | .NET framework 4-4.6 geliştirme araçları | 15.6.27406.0 | Önerilen
Microsoft.VisualStudio.Component.AppInsights.Tools | Geliştirici analiz araçları | 15.8.27825.0 | Önerilen
Microsoft.VisualStudio.Component.AspNet45 | Gelişmiş ASP.NET özellikleri | 15.7.27625.0 | Önerilen
Microsoft.VisualStudio.Component.Azure.AuthoringTools | Azure yazma araçları | 15.9.28307.421 | Önerilen
Microsoft.VisualStudio.Component.Azure.ClientLibs | .NET için Azure kitaplıkları | 15.0.26208.0 | Önerilen
Microsoft.VisualStudio.Component.Azure.Compute.Emulator | Azure işlem öykünücüsü | 15.9.28307.421 | Önerilen
Microsoft.VisualStudio.Component.Azure.Storage.Emulator | Azure depolama öykünücüsü | 15.9.28125.51 | Önerilen
Microsoft.VisualStudio.Component.CloudExplorer | Cloud Explorer | 15.9.28230.55 | Önerilen
Microsoft.VisualStudio.Component.Debugger.Snapshot | Anlık görüntü hata ayıklayıcısı | 15.8.28010.0 | Önerilen
Microsoft.VisualStudio.Component.DiagnosticTools | .NET profil oluşturma araçları | 15.8.27729.1 | Önerilen
Microsoft.VisualStudio.Component.EntityFramework | Entity Framework 6 araçları | 15.6.27406.0 | Önerilen
Microsoft.VisualStudio.Component.IntelliTrace.FrontEnd | IntelliTrace | 15.8.27729.1 | Önerilen
Microsoft.VisualStudio.Component.LiveUnitTesting | Live Unit Testing | 15.0.26720.2 | Önerilen
Microsoft.VisualStudio.Component.Wcf.Tooling | Windows Communication Foundation | 15.8.27924.0 | Önerilen
Microsoft.VisualStudio.Component.WebDeploy | Web Dağıtımı | 15.8.27729.1 | Önerilen
Microsoft.VisualStudio.ComponentGroup.AzureFunctions | Microsoft Azure Web işleri araçları | 15.7.27617.1 | Önerilen
Microsoft.VisualStudio.ComponentGroup.Web.CloudTools | Web geliştirme için bulut araçları | 15.8.27729.1 | Önerilen
Microsoft.Net.Component.4.6.2.SDK | .NET framework 4.6.2 SDK'sı | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Component.4.6.2.TargetingPack | .NET framework 4.6.2 targeting pack | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Component.4.7.1.SDK | .NET framework 4.7.1 SDK'sı | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Component.4.7.1.TargetingPack | .NET framework 4.7.1 targeting pack | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Component.4.7.2.SDK | .NET framework 4.7.2 SDK'sı | 15.8.27825.0 | İsteğe Bağlı
Microsoft.Net.Component.4.7.2.TargetingPack | .NET framework 4.7.2 targeting pack | 15.8.27825.0 | İsteğe Bağlı
Microsoft.Net.Component.4.7.SDK | .NET framework 4.7 SDK'sı | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Component.4.7.TargetingPack | .NET framework 4.7 targeting pack | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.ComponentGroup.4.6.2.DeveloperTools | .NET framework 4.6.2 geliştirme araçları | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.ComponentGroup.4.7.1.DeveloperTools | .NET framework 4.7.1 geliştirme araçları | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.ComponentGroup.4.7.2.DeveloperTools | .NET framework 4.7.2 geliştirme araçları | 15.8.27825.0 | İsteğe Bağlı
Microsoft.Net.ComponentGroup.4.7.DeveloperTools | .NET framework 4.7 geliştirme araçları | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Core.Component.SDK | .NET core 2.0 geliştirme araçları | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Core.Component.SDK.1x | .NET core 1.0-1.1 geliştirme araçları | 15.6.27406.0 | İsteğe Bağlı
Microsoft.NetCore.1x.ComponentGroup.Web | Web için .NET core 1.0-1.1 geliştirme araçları | 15.6.27406.0 | İsteğe Bağlı
Microsoft.NetCore.ComponentGroup.DevelopmentTools | .NET core 2.0 geliştirme araçları | 15.8.27729.1 | İsteğe Bağlı
Microsoft.NetCore.ComponentGroup.Web | .NET core 2.0 geliştirme araçları | 15.7.27625.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.CodeClone | Kod kopyası | 15.0.26208.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.CodeMap | Kod Haritası | 15.0.26208.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.DependencyValidation.Enterprise | Canlı bağımlılık doğrulama | 15.0.26208.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.GraphDocument | DGML Düzenleyici | 15.0.27005.2 | İsteğe Bağlı
Microsoft.VisualStudio.Component.TestTools.WebLoadTest | Web performansı ve yük testi araçları | 15.8.27729.1 | İsteğe Bağlı
Microsoft.VisualStudio.ComponentGroup.ArchitectureTools.Managed | Mimari ve analiz araçları | 15.0.26208.0 | İsteğe Bağlı
Microsoft.VisualStudio.ComponentGroup.IISDevelopment | Geliştirme zamanı IIS desteği | 15.9.28219.51 | İsteğe Bağlı
Microsoft.VisualStudio.Web.Mvc4.ComponentGroup | ASP.NET MVC 4 | 15.6.27406.0 | İsteğe Bağlı

## <a name="nodejs-development"></a>Node.js geliştirme

**KİMLİĞİ:** Microsoft.VisualStudio.Workload.Node

**Açıklama:** Zaman uyumsuz olay temelli JavaScript çalışma zamanı olan node.js kullanarak Ölçeklenebilir Ağ uygulamaları oluşturun. 

### <a name="components-included-by-this-workload"></a>Bu iş yükü tarafından bulunan bileşenler

Bileşen kimliği | Ad | Sürüm | Bağımlılık türü
--- | --- | --- | ---
Component.WebSocket | WebSocket4Net | 15.0.26606.0 | Gerekli
Microsoft.VisualStudio.Component.JavaScript.Diagnostics | JavaScript tanılamaları | 15.8.27729.1 | Gerekli
Microsoft.VisualStudio.Component.JavaScript.TypeScript | JavaScript ve TypeScript dil desteği | 15.9.28125.51 | Gerekli
Microsoft.VisualStudio.Component.Node.Build | Node.js MSBuild desteği | 15.8.27825.0 | Gerekli
Microsoft.VisualStudio.Component.Node.Tools | Node.js geliştirme desteği | 15.8.27825.0 | Gerekli
Microsoft.VisualStudio.Component.NuGet | NuGet Paket Yöneticisi | 15.9.28016.0 | Gerekli
Microsoft.VisualStudio.Component.TestTools.Core | Test Araçları temel özellikleri | 15.7.27520.0 | Gerekli
Microsoft.VisualStudio.Component.TypeScript.3.1 | 3.1 TypeScript SDK'sı | 15.0.28218.60 | Gerekli
Microsoft.VisualStudio.ComponentGroup.WebToolsExtensions | ASP.NET ve web geliştirme | 15.8.27825.0 | Gerekli
Microsoft.VisualStudio.Component.WebDeploy | Web Dağıtımı | 15.8.27729.1 | Önerilen
Microsoft.VisualStudio.Component.AppInsights.Tools | Geliştirici analiz araçları | 15.8.27825.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Common.Azure.Tools | Bağlantı ve yayımlama araçları | 15.9.28107.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Static.Analysis.Tools | Statik analiz araçları | 15.0.26208.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.VC.CoreIde | Visual Studio C++ temel özellikler | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.VC.Tools.x86.x64 | VC ++ 2017 sürüm 15.9 v14.16 en yeni v141 araçları | 15.9.28230.55 | İsteğe Bağlı

## <a name="officesharepoint-development"></a>Office/SharePoint geliştirme

**KİMLİĞİ:** Microsoft.VisualStudio.Workload.Office

**Açıklama:** Office ve SharePoint eklentileri, SharePoint çözümleri ve kullanarak VSTO eklentileri oluşturma C#, VB ve JavaScript.

### <a name="components-included-by-this-workload"></a>Bu iş yükü tarafından bulunan bileşenler

Bileşen kimliği | Ad | Sürüm | Bağımlılık türü
--- | --- | --- | ---
Component.Microsoft.VisualStudio.RazorExtension | Razor dil Hizmetleri | 15.0.26720.2 | Gerekli
Component.Microsoft.Web.LibraryManager | Kitaplık Yöneticisi | 15.8.27705.0 | Gerekli
Component.WebSocket | WebSocket4Net | 15.0.26606.0 | Gerekli
Microsoft.Component.ClickOnce | ClickOnce yayımlama | 15.8.27825.0 | Gerekli
Microsoft.Component.MSBuild | MSBuild | 15.7.27520.0 | Gerekli
Microsoft.Net.Component.4.5.2.TargetingPack | .NET framework 4.5.2 targeting pack | 15.6.27406.0 | Gerekli
Microsoft.Net.Component.4.5.TargetingPack | .NET framework 4.5 targeting pack | 15.6.27406.0 | Gerekli
Microsoft.Net.Component.4.6.1.SDK | .NET framework 4.6.1 SDK'sı | 15.6.27406.0 | Gerekli
Microsoft.Net.Component.4.6.1.TargetingPack | .NET framework 4.6.1 targeting pack | 15.6.27406.0 | Gerekli
Microsoft.Net.Component.4.TargetingPack | .NET framework 4 targeting pack | 15.6.27406.0 | Gerekli
Microsoft.Net.ComponentGroup.DevelopmentPrerequisites | .NET framework 4.6.1 geliştirme araçları | 15.8.27825.0 | Gerekli
Microsoft.Net.Core.Component.SDK.2.1 | .NET core 2.1 geliştirme araçları | 15.8.27924.0 | Gerekli
Microsoft.VisualStudio.Component.AppInsights.Tools | Geliştirici analiz araçları | 15.8.27825.0 | Gerekli
Microsoft.VisualStudio.Component.Common.Azure.Tools | Bağlantı ve yayımlama araçları | 15.9.28107.0 | Gerekli
Microsoft.VisualStudio.Component.DockerTools | Kapsayıcı geliştirme araçları | 15.8.27906.1 | Gerekli
Microsoft.VisualStudio.Component.DockerTools.BuildTools | Kapsayıcı geliştirme araçları - derleme araçları | 15.7.27617.1 | Gerekli
Microsoft.VisualStudio.Component.IISExpress | IIS Express  | 15.0.26208.0 | Gerekli
Microsoft.VisualStudio.Component.JavaScript.Diagnostics | JavaScript tanılamaları | 15.8.27729.1 | Gerekli
Microsoft.VisualStudio.Component.JavaScript.TypeScript | JavaScript ve TypeScript dil desteği | 15.9.28125.51 | Gerekli
Microsoft.VisualStudio.Component.ManagedDesktop.Core | Yönetilen masaüstü iş yükü Çekirdeği | 15.8.27729.1 | Gerekli
Microsoft.VisualStudio.Component.ManagedDesktop.Prerequisites | .NET masaüstü geliştirme araçları | 15.7.27625.0 | Gerekli
Microsoft.VisualStudio.Component.NuGet | NuGet Paket Yöneticisi | 15.9.28016.0 | Gerekli
Microsoft.VisualStudio.Component.PortableLibrary | .NET taşınabilir kitaplık targeting pack | 15.6.27309.0 | Gerekli
Microsoft.VisualStudio.Component.Roslyn.Compiler | C# ve Visual Basic Roslyn derleyicileri | 15.6.27309.0 | Gerekli
Microsoft.VisualStudio.Component.Roslyn.LanguageServices | C# ve Visual Basic | 15.8.27729.1 | Gerekli
Microsoft.VisualStudio.Component.Sharepoint.Tools | Visual Studio için Office Geliştirici Araçları | 15.8.27924.0 | Gerekli
Microsoft.VisualStudio.Component.SQL.ADAL | SQL ADAL çalışma zamanı | 15.6.27406.0 | Gerekli
Microsoft.VisualStudio.Component.SQL.CLR | SQL Server için CLR veri türleri | 15.0.26208.0 | Gerekli
Microsoft.VisualStudio.Component.SQL.CMDUtils | SQL Server komut satırı yardımcı programları | 15.0.26208.0 | Gerekli
Microsoft.VisualStudio.Component.SQL.DataSources | Veri kaynakları için SQL Server desteği | 15.0.26621.2 | Gerekli
Microsoft.VisualStudio.Component.SQL.LocalDB.Runtime | SQL Server Express 2016 LocalDB | 15.7.27617.1 | Gerekli
Microsoft.VisualStudio.Component.SQL.NCLI | SQL Server yerel istemcisi | 15.0.26208.0 | Gerekli
Microsoft.VisualStudio.Component.SQL.SSDT | SQL Server Veri Araçları | 15.9.28107.0 | Gerekli
Microsoft.VisualStudio.Component.Static.Analysis.Tools | Statik analiz araçları | 15.0.26208.0 | Gerekli
Microsoft.VisualStudio.Component.TextTemplating | Metin şablonu dönüştürme | 15.0.26208.0 | Gerekli
Microsoft.VisualStudio.Component.TypeScript.3.1 | 3.1 TypeScript SDK'sı | 15.0.28218.60 | Gerekli
Microsoft.VisualStudio.Component.VisualStudioData | Veri kaynakları ve hizmet başvuruları | 15.6.27406.0 | Gerekli
Microsoft.VisualStudio.Component.Wcf.Tooling | Windows Communication Foundation | 15.8.27924.0 | Gerekli
Microsoft.VisualStudio.Component.Web | ASP.NET ve web geliştirme araçları | 15.8.27825.0 | Gerekli
Microsoft.VisualStudio.Component.Workflow | Windows Workflow Foundation | 15.8.27825.0 | Gerekli
Microsoft.VisualStudio.ComponentGroup.Web | ASP.NET ve web geliştirme araçları önkoşulları | 15.9.28219.51 | Gerekli
Microsoft.VisualStudio.ComponentGroup.WebToolsExtensions | ASP.NET ve web geliştirme | 15.8.27825.0 | Gerekli
Microsoft.VisualStudio.Component.TeamOffice | (VSTO) Office için Visual Studio Araçları | 15.7.27625.0 | Önerilen
Microsoft.VisualStudio.Component.WebDeploy | Web Dağıtımı | 15.8.27729.1 | Önerilen
Microsoft.Net.Component.4.6.2.SDK | .NET framework 4.6.2 SDK'sı | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Component.4.6.2.TargetingPack | .NET framework 4.6.2 targeting pack | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Component.4.7.1.SDK | .NET framework 4.7.1 SDK'sı | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Component.4.7.1.TargetingPack | .NET framework 4.7.1 targeting pack | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Component.4.7.2.SDK | .NET framework 4.7.2 SDK'sı | 15.8.27825.0 | İsteğe Bağlı
Microsoft.Net.Component.4.7.2.TargetingPack | .NET framework 4.7.2 targeting pack | 15.8.27825.0 | İsteğe Bağlı
Microsoft.Net.Component.4.7.SDK | .NET framework 4.7 SDK'sı | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Component.4.7.TargetingPack | .NET framework 4.7 targeting pack | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.ComponentGroup.4.6.2.DeveloperTools | .NET framework 4.6.2 geliştirme araçları | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.ComponentGroup.4.7.1.DeveloperTools | .NET framework 4.7.1 geliştirme araçları | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.ComponentGroup.4.7.2.DeveloperTools | .NET framework 4.7.2 geliştirme araçları | 15.8.27825.0 | İsteğe Bağlı
Microsoft.Net.ComponentGroup.4.7.DeveloperTools | .NET framework 4.7 geliştirme araçları | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.IntelliTrace.FrontEnd | IntelliTrace | 15.8.27729.1 | İsteğe Bağlı

## <a name="python-development"></a>Python geliştirme

**KİMLİĞİ:** Microsoft.VisualStudio.Workload.Python

**Açıklama:** Düzenleme, hata ayıklama, etkileşimli geliştirme ve Python için kaynak denetimi.

### <a name="components-included-by-this-workload"></a>Bu iş yükü tarafından bulunan bileşenler

Bileşen kimliği | Ad | Sürüm | Bağımlılık türü
--- | --- | --- | ---
Microsoft.Component.PythonTools | Python dil desteği | 15.0.26823.1 | Gerekli
Component.CPython3.x64 | Python 3 64 bit (3.6.6) | 3.6.6 | Önerilen
Microsoft.Component.CookiecutterTools | Cookiecutter şablonu desteği | 15.0.26621.2 | Önerilen
Microsoft.Component.PythonTools.Web | Python web desteği | 15.9.28107.0 | Önerilen
Microsoft.VisualStudio.Component.Common.Azure.Tools | Bağlantı ve yayımlama araçları | 15.9.28107.0 | Önerilen
Microsoft.VisualStudio.Component.JavaScript.TypeScript | JavaScript ve TypeScript dil desteği | 15.9.28125.51 | Önerilen
Microsoft.VisualStudio.Component.SQL.CLR | SQL Server için CLR veri türleri | 15.0.26208.0 | Önerilen
Microsoft.VisualStudio.Component.TypeScript.3.1 | 3.1 TypeScript SDK'sı | 15.0.28218.60 | Önerilen
Microsoft.VisualStudio.Component.VisualStudioData | Veri kaynakları ve hizmet başvuruları | 15.6.27406.0 | Önerilen
Microsoft.VisualStudio.Component.WebDeploy | Web Dağıtımı | 15.8.27729.1 | Önerilen
Microsoft.VisualStudio.ComponentGroup.WebToolsExtensions | ASP.NET ve web geliştirme | 15.8.27825.0 | Önerilen
Component.Anaconda2.x64 | Anaconda2 64-bit (5.2.0) | 5.2.0 | İsteğe Bağlı
Component.Anaconda2.x86 | Anaconda2 32-bit (5.2.0) | 5.2.0 | İsteğe Bağlı
Component.Anaconda3.x64 | Anaconda3 64-bit (5.2.0) | 5.2.0 | İsteğe Bağlı
Component.Anaconda3.x86 | Anaconda3 32-bit (5.2.0) | 5.2.0 | İsteğe Bağlı
Component.CPython2.x64 | Python 2 64-bit (2.7.14) | 2.7.14 | İsteğe Bağlı
Component.CPython2.x86 | Python 2 32 bit (2.7.14) | 2.7.14 | İsteğe Bağlı
Component.CPython3.x86 | Python 3 32 bit (3.6.6) | 3.6.6 | İsteğe Bağlı
Component.Microsoft.VisualStudio.RazorExtension | Razor dil Hizmetleri | 15.0.26720.2 | İsteğe Bağlı
Component.Microsoft.Web.LibraryManager | Kitaplık Yöneticisi | 15.8.27705.0 | İsteğe Bağlı
Component.WebSocket | WebSocket4Net | 15.0.26606.0 | İsteğe Bağlı
Microsoft.Component.ClickOnce | ClickOnce yayımlama | 15.8.27825.0 | İsteğe Bağlı
Microsoft.Component.MSBuild | MSBuild | 15.7.27520.0 | İsteğe Bağlı
Microsoft.Component.NetFX.Native | .NET Yerel | 15.0.26208.0 | İsteğe Bağlı
Microsoft.Component.PythonTools.UWP | Python IOT desteği | 15.0.26606.0 | İsteğe Bağlı
Microsoft.Component.VC.Runtime.UCRTSDK | Windows Evrensel CRT SDK | 15.6.27309.0 | İsteğe Bağlı
Microsoft.ComponentGroup.PythonTools.NativeDevelopment | Python yerel geliştirme araçları | 15.9.28307.102 | İsteğe Bağlı
Microsoft.Net.Component.4.5.2.TargetingPack | .NET framework 4.5.2 targeting pack | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Component.4.5.TargetingPack | .NET framework 4.5 targeting pack | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Component.4.6.1.SDK | .NET framework 4.6.1 SDK'sı | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Component.4.6.1.TargetingPack | .NET framework 4.6.1 targeting pack | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.ComponentGroup.DevelopmentPrerequisites | .NET framework 4.6.1 geliştirme araçları | 15.8.27825.0 | İsteğe Bağlı
Microsoft.Net.Core.Component.SDK.2.1 | .NET core 2.1 geliştirme araçları | 15.8.27924.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.AppInsights.Tools | Geliştirici analiz araçları | 15.8.27825.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Azure.AuthoringTools | Azure yazma araçları | 15.9.28307.421 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Azure.ClientLibs | .NET için Azure kitaplıkları | 15.0.26208.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Azure.Compute.Emulator | Azure işlem öykünücüsü | 15.9.28307.421 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Azure.Storage.Emulator | Azure depolama öykünücüsü | 15.9.28125.51 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Azure.Waverton | Azure Cloud Services temel araçları | 15.9.28107.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Azure.Waverton.BuildTools | Azure Cloud Services derleme araçları | 15.7.27617.1 | İsteğe Bağlı
Microsoft.VisualStudio.Component.ClassDesigner | Sınıf Tasarımcısı | 15.0.26208.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.CodeClone | Kod kopyası | 15.0.26208.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.CodeMap | Kod Haritası | 15.0.26208.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.DiagnosticTools | .NET profil oluşturma araçları | 15.8.27729.1 | İsteğe Bağlı
Microsoft.VisualStudio.Component.DockerTools | Kapsayıcı geliştirme araçları | 15.8.27906.1 | İsteğe Bağlı
Microsoft.VisualStudio.Component.DockerTools.BuildTools | Kapsayıcı geliştirme araçları - derleme araçları | 15.7.27617.1 | İsteğe Bağlı
Microsoft.VisualStudio.Component.GraphDocument | DGML Düzenleyici | 15.0.27005.2 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Graphics | Görüntü ve 3B model düzenleyicileri | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Graphics.Tools | DirectX için grafik hata ayıklayıcı ve GPU | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Graphics.Win81 | Grafik araçları Windows 8.1 SDK'sı | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.IISExpress | IIS Express  | 15.0.26208.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.IntelliTrace.FrontEnd | IntelliTrace | 15.8.27729.1 | İsteğe Bağlı
Microsoft.VisualStudio.Component.JavaScript.Diagnostics | JavaScript tanılamaları | 15.8.27729.1 | İsteğe Bağlı
Microsoft.VisualStudio.Component.ManagedDesktop.Core | Yönetilen masaüstü iş yükü Çekirdeği | 15.8.27729.1 | İsteğe Bağlı
Microsoft.VisualStudio.Component.NuGet | NuGet Paket Yöneticisi | 15.9.28016.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.PortableLibrary | .NET taşınabilir kitaplık targeting pack | 15.6.27309.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Roslyn.Compiler | C# ve Visual Basic Roslyn derleyicileri | 15.6.27309.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Roslyn.LanguageServices | C# ve Visual Basic | 15.8.27729.1 | İsteğe Bağlı
Microsoft.VisualStudio.Component.SQL.ADAL | SQL ADAL çalışma zamanı | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.SQL.CMDUtils | SQL Server komut satırı yardımcı programları | 15.0.26208.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.SQL.DataSources | Veri kaynakları için SQL Server desteği | 15.0.26621.2 | İsteğe Bağlı
Microsoft.VisualStudio.Component.SQL.LocalDB.Runtime | SQL Server Express 2016 LocalDB | 15.7.27617.1 | İsteğe Bağlı
Microsoft.VisualStudio.Component.SQL.NCLI | SQL Server yerel istemcisi | 15.0.26208.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.SQL.SSDT | SQL Server Veri Araçları | 15.9.28107.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Static.Analysis.Tools | Statik analiz araçları | 15.0.26208.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.TextTemplating | Metin şablonu dönüştürme | 15.0.26208.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.VC.140 | Masaüstü için VC ++ 2015.3 v14.00 (v140) araç | 15.7.27617.1 | İsteğe Bağlı
Microsoft.VisualStudio.Component.VC.CoreIde | Visual Studio C++ temel özellikler | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.VC.DiagnosticTools | C++ profil oluşturma araçları | 15.0.26823.1 | İsteğe Bağlı
Microsoft.VisualStudio.Component.VC.Tools.x86.x64 | VC ++ 2017 sürüm 15.9 v14.16 en yeni v141 araçları | 15.9.28230.55 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Web | ASP.NET ve web geliştirme araçları | 15.8.27825.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows10SDK | Windows Evrensel C çalışma zamanı | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows10SDK.10586 | Windows 10 SDK (10.0.10586.0) | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows10SDK.17763 | Windows 10 SDK (10.0.17763.0) | 15.9.28307.102 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows81SDK | Windows 8.1 SDK | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.ComponentGroup.Web | ASP.NET ve web geliştirme araçları önkoşulları | 15.9.28219.51 | İsteğe Bağlı

## <a name="universal-windows-platform-development"></a>Evrensel Windows platformu geliştirme

**KİMLİĞİ:** Microsoft.VisualStudio.Workload.Universal

**Açıklama:** Evrensel Windows platformu uygulamaları oluşturmak C#, VB, JavaScript veya isteğe bağlı olarak C++.

### <a name="components-included-by-this-workload"></a>Bu iş yükü tarafından bulunan bileşenler

Bileşen kimliği | Ad | Sürüm | Bağımlılık türü
--- | --- | --- | ---
Component.WebSocket | WebSocket4Net | 15.0.26606.0 | Gerekli
Microsoft.Component.ClickOnce | ClickOnce yayımlama | 15.8.27825.0 | Gerekli
Microsoft.Component.NetFX.Native | .NET Yerel | 15.0.26208.0 | Gerekli
Microsoft.ComponentGroup.Blend | Visual Studio için Blend | 15.6.27406.0 | Gerekli
Microsoft.Net.Component.4.5.TargetingPack | .NET framework 4.5 targeting pack | 15.6.27406.0 | Gerekli
Microsoft.Net.Component.4.6.1.SDK | .NET framework 4.6.1 SDK'sı | 15.6.27406.0 | Gerekli
Microsoft.Net.Core.Component.SDK.2.1 | .NET core 2.1 geliştirme araçları | 15.8.27924.0 | Gerekli
Microsoft.VisualStudio.Component.AppInsights.Tools | Geliştirici analiz araçları | 15.8.27825.0 | Gerekli
Microsoft.VisualStudio.Component.DiagnosticTools | .NET profil oluşturma araçları | 15.8.27729.1 | Gerekli
Microsoft.VisualStudio.Component.Graphics | Görüntü ve 3B model düzenleyicileri | 15.6.27406.0 | Gerekli
Microsoft.VisualStudio.Component.JavaScript.Diagnostics | JavaScript tanılamaları | 15.8.27729.1 | Gerekli
Microsoft.VisualStudio.Component.JavaScript.TypeScript | JavaScript ve TypeScript dil desteği | 15.9.28125.51 | Gerekli
Microsoft.VisualStudio.Component.NuGet | NuGet Paket Yöneticisi | 15.9.28016.0 | Gerekli
Microsoft.VisualStudio.Component.PortableLibrary | .NET taşınabilir kitaplık targeting pack | 15.6.27309.0 | Gerekli
Microsoft.VisualStudio.Component.Roslyn.Compiler | C# ve Visual Basic Roslyn derleyicileri | 15.6.27309.0 | Gerekli
Microsoft.VisualStudio.Component.Roslyn.LanguageServices | C# ve Visual Basic | 15.8.27729.1 | Gerekli
Microsoft.VisualStudio.Component.SQL.CLR | SQL Server için CLR veri türleri | 15.0.26208.0 | Gerekli
Microsoft.VisualStudio.Component.Static.Analysis.Tools | Statik analiz araçları | 15.0.26208.0 | Gerekli
Microsoft.VisualStudio.Component.TypeScript.3.1 | 3.1 TypeScript SDK'sı | 15.0.28218.60 | Gerekli
Microsoft.VisualStudio.Component.UWP.Support | Evrensel Windows platformu araçları | 15.9.28119.51 | Gerekli
Microsoft.VisualStudio.Component.VisualStudioData | Veri kaynakları ve hizmet başvuruları | 15.6.27406.0 | Gerekli
Microsoft.VisualStudio.Component.Windows10SDK.17763 | Windows 10 SDK (10.0.17763.0) | 15.9.28307.102 | Gerekli
Microsoft.VisualStudio.ComponentGroup.UWP.Cordova | Cordova için evrensel Windows platformu araçları | 15.9.28307.102 | Gerekli
Microsoft.VisualStudio.ComponentGroup.UWP.NetCoreAndStandard | .NET native ve .NET Standard | 15.8.27906.1 | Gerekli
Microsoft.VisualStudio.ComponentGroup.UWP.Xamarin | Xamarin için evrensel Windows platformu araçları | 15.9.28307.102 | Gerekli
Microsoft.VisualStudio.ComponentGroup.WebToolsExtensions | ASP.NET ve web geliştirme | 15.8.27825.0 | Gerekli
Microsoft.VisualStudio.Component.IntelliTrace.FrontEnd | IntelliTrace | 15.8.27729.1 | Önerilen
Microsoft.Component.VC.Runtime.OSSupport | UWP için Visual C++ çalışma zamanı | 15.6.27406.0 | İsteğe Bağlı
Microsoft.Net.Component.4.7.2.SDK | .NET framework 4.7.2 SDK'sı | 15.8.27825.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.CodeClone | Kod kopyası | 15.0.26208.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.CodeMap | Kod Haritası | 15.0.26208.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.DependencyValidation.Enterprise | Canlı bağımlılık doğrulama | 15.0.26208.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.GraphDocument | DGML Düzenleyici | 15.0.27005.2 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Graphics.Tools | DirectX için grafik hata ayıklayıcı ve GPU | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Graphics.Win81 | Grafik araçları Windows 8.1 SDK'sı | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Phone.Emulator.15254 | Windows 10 Mobile öykünücüsü (Fall Creators Update) | 15.0.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.SQL.LocalDB.Runtime | SQL Server Express 2016 LocalDB | 15.7.27617.1 | İsteğe Bağlı
Microsoft.VisualStudio.Component.SQL.NCLI | SQL Server yerel istemcisi | 15.0.26208.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.UWP.VC.ARM64 | ARM64 için C++ Evrensel Windows platformu araçları | 15.0.28125.51 | İsteğe Bağlı
Microsoft.VisualStudio.Component.VC.CoreIde | Visual Studio C++ temel özellikler | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.VC.Tools.ARM | ARM için Visual C++ Derleyicileri ve kitaplıkları | 15.8.27825.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.VC.Tools.ARM64 | ARM64 için Visual C++ Derleyicileri ve kitaplıkları | 15.9.28230.55 | İsteğe Bağlı
Microsoft.VisualStudio.Component.VC.Tools.x86.x64 | VC ++ 2017 sürüm 15.9 v14.16 en yeni v141 araçları | 15.9.28230.55 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows10SDK.10240 | Windows 10 SDK (10.0.10240.0) | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows10SDK.10586 | Windows 10 SDK (10.0.10586.0) | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows10SDK.14393 | Windows 10 SDK (10.0.14393.0) | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows10SDK.15063.Desktop | Windows 10 SDK (10.0.15063.0) Masaüstü C++ [x86 ve x64] için | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows10SDK.15063.UWP | Windows 10 SDK (10.0.15063.0) UWP için: C#, VB, JS | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows10SDK.15063.UWP.Native | Windows 10 SDK (10.0.15063.0) UWP için: C++ | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows10SDK.16299.Desktop | Windows 10 SDK (10.0.16299.0) Masaüstü C++ [x86 ve x64] için | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows10SDK.16299.Desktop.arm | Windows 10 SDK (10.0.16299.0) Masaüstü C++ [ARM ve ARM64] için | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows10SDK.16299.UWP | Windows 10 SDK (10.0.16299.0) UWP için: C#, VB, JS | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows10SDK.16299.UWP.Native | Windows 10 SDK (10.0.16299.0) UWP için: C++ | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows10SDK.17134 | Windows 10 SDK (10.0.17134.0) | 15.9.28307.102 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows10SDK.IpOverUsb | USB cihaz bağlantısı | 15.9.28307.102 | İsteğe Bağlı
Microsoft.VisualStudio.ComponentGroup.ArchitectureTools.Managed | Mimari ve analiz araçları | 15.0.26208.0 | İsteğe Bağlı
Microsoft.VisualStudio.ComponentGroup.UWP.VC | C++ Evrensel Windows platformu araçları | 15.9.28307.102 | İsteğe Bağlı
Microsoft.VisualStudio.ComponentGroup.Windows10SDK.15063 | Windows 10 SDK (10.0.15063.0) | 15.8.27825.0 | İsteğe Bağlı
Microsoft.VisualStudio.ComponentGroup.Windows10SDK.16299 | Windows 10 SDK (10.0.16299.0) | 15.8.27825.0 | İsteğe Bağlı

## <a name="visual-studio-extension-development"></a>Visual Studio uzantısı geliştirme

**KİMLİĞİ:** Microsoft.VisualStudio.Workload.VisualStudioExtension

**Açıklama:** Visual Studio için yeni komutlar, kod Çözümleyicileri ve araç pencerelerini de dahil olmak üzere, eklentileri ve uzantıları oluşturun.

### <a name="components-included-by-this-workload"></a>Bu iş yükü tarafından bulunan bileşenler

Bileşen kimliği | Ad | Sürüm | Bağımlılık türü
--- | --- | --- | ---
Microsoft.Component.ClickOnce | ClickOnce yayımlama | 15.8.27825.0 | Gerekli
Microsoft.Component.MSBuild | MSBuild | 15.7.27520.0 | Gerekli
Microsoft.Net.Component.4.6.1.SDK | .NET framework 4.6.1 SDK'sı | 15.6.27406.0 | Gerekli
Microsoft.Net.Component.4.6.1.TargetingPack | .NET framework 4.6.1 targeting pack | 15.6.27406.0 | Gerekli
Microsoft.Net.Component.4.6.TargetingPack | .NET framework 4.6 targeting pack | 15.6.27406.0 | Gerekli
Microsoft.Net.ComponentGroup.DevelopmentPrerequisites | .NET framework 4.6.1 geliştirme araçları | 15.8.27825.0 | Gerekli
Microsoft.VisualStudio.Component.NuGet | NuGet Paket Yöneticisi | 15.9.28016.0 | Gerekli
Microsoft.VisualStudio.Component.PortableLibrary | .NET taşınabilir kitaplık targeting pack | 15.6.27309.0 | Gerekli
Microsoft.VisualStudio.Component.Roslyn.Compiler | C# ve Visual Basic Roslyn derleyicileri | 15.6.27309.0 | Gerekli
Microsoft.VisualStudio.Component.Roslyn.LanguageServices | C# ve Visual Basic | 15.8.27729.1 | Gerekli
Microsoft.VisualStudio.Component.Static.Analysis.Tools | Statik analiz araçları | 15.0.26208.0 | Gerekli
Microsoft.VisualStudio.Component.VSSDK | Visual Studio SDK | 15.8.27729.1 | Gerekli
Microsoft.VisualStudio.ComponentGroup.VisualStudioExtension.Prerequisites | Visual Studio uzantı geliştirme önkoşulları | 15.7.27625.0 | Gerekli
Microsoft.VisualStudio.Component.DiagnosticTools | .NET profil oluşturma araçları | 15.8.27729.1 | Önerilen
Microsoft.VisualStudio.Component.IntelliTrace.FrontEnd | IntelliTrace | 15.8.27729.1 | Önerilen
Microsoft.VisualStudio.Component.TextTemplating | Metin şablonu dönüştürme | 15.0.26208.0 | Önerilen
Component.Dotfuscator | PreEmptive koruma - Dotfuscator | 15.0.26208.0 | İsteğe Bağlı
Microsoft.Component.CodeAnalysis.SDK | .NET Compiler Platform SDK’sı | 15.0.27729.1 | İsteğe Bağlı
Microsoft.Component.VC.Runtime.OSSupport | UWP için Visual C++ çalışma zamanı | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.AppInsights.Tools | Geliştirici analiz araçları | 15.8.27825.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.ClassDesigner | Sınıf Tasarımcısı | 15.0.26208.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.CodeClone | Kod kopyası | 15.0.26208.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.CodeMap | Kod Haritası | 15.0.26208.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.DependencyValidation.Enterprise | Canlı bağımlılık doğrulama | 15.0.26208.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.DslTools | Modelleme SDK'sı | 15.0.27005.2 | İsteğe Bağlı
Microsoft.VisualStudio.Component.GraphDocument | DGML Düzenleyici | 15.0.27005.2 | İsteğe Bağlı
Microsoft.VisualStudio.Component.SQL.LocalDB.Runtime | SQL Server Express 2016 LocalDB | 15.7.27617.1 | İsteğe Bağlı
Microsoft.VisualStudio.Component.SQL.NCLI | SQL Server yerel istemcisi | 15.0.26208.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.VC.ATL | X86 ve x64 için Visual C++ ATL | 15.7.27625.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.VC.ATLMFC | X86 ve x64 için Visual C++ MFC | 15.7.27625.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.VC.CoreIde | Visual Studio C++ temel özellikler | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.VC.Tools.x86.x64 | VC ++ 2017 sürüm 15.9 v14.16 en yeni v141 araçları | 15.9.28230.55 | İsteğe Bağlı
Microsoft.VisualStudio.ComponentGroup.ArchitectureTools.Managed | Mimari ve analiz araçları | 15.0.26208.0 | İsteğe Bağlı

## <a name="mobile-development-with-javascript"></a>JavaScript ile Mobil Geliştirme

**KİMLİĞİ:** Microsoft.VisualStudio.Workload.WebCrossPlat

**Açıklama:** Apache Cordova için Araçları'nı kullanarak Android, iOS ve UWP uygulamaları oluşturun.

### <a name="components-included-by-this-workload"></a>Bu iş yükü tarafından bulunan bileşenler

Bileşen kimliği | Ad | Sürüm | Bağımlılık türü
--- | --- | --- | ---
Component.CordovaToolset.6.3.1 | Cordova 6.3.1 araç takımı | 15.7.27625.0 | Gerekli
Component.WebSocket | WebSocket4Net | 15.0.26606.0 | Gerekli
Microsoft.VisualStudio.Component.Cordova | JavaScript temel özellikleriyle mobil geliştirme | 15.0.26606.0 | Gerekli
Microsoft.VisualStudio.Component.JavaScript.Diagnostics | JavaScript tanılamaları | 15.8.27729.1 | Gerekli
Microsoft.VisualStudio.Component.JavaScript.ProjectSystem | JavaScript proje sistemi ve paylaşılan Araçlar | 15.0.26606.0 | Gerekli
Microsoft.VisualStudio.Component.JavaScript.TypeScript | JavaScript ve TypeScript dil desteği | 15.9.28125.51 | Gerekli
Microsoft.VisualStudio.Component.TypeScript.2.3 | TypeScript 2.3 SDK'sı | 15.8.27729.1 | Gerekli
Microsoft.VisualStudio.Component.TypeScript.3.1 | 3.1 TypeScript SDK'sı | 15.0.28218.60 | Gerekli
Microsoft.VisualStudio.ComponentGroup.WebToolsExtensions | ASP.NET ve web geliştirme | 15.8.27825.0 | Gerekli
Component.Android.SDK23.Private | Android SDK kurulumu (API düzeyi 23) (JavaScript ile Mobil Geliştirme için yerel yükleme / C++) | 15.9.28016.0 | İsteğe Bağlı
Component.Google.Android.Emulator.API23.Private | Google Android Emulator (API düzeyi 23) (yerel kurulum) | 15.6.27413.0 | İsteğe Bağlı
Component.HAXM.Private | Intel donanım hızlandırılmış yürütme Yöneticisi (HAXM) (yerel kurulum) | 15.9.28307.421 | İsteğe Bağlı
Component.OpenJDK | Microsoft Dağıtım OpenJDK | 15.9.28125.51 | İsteğe Bağlı
Microsoft.Component.ClickOnce | ClickOnce yayımlama | 15.8.27825.0 | İsteğe Bağlı
Microsoft.Component.NetFX.Native | .NET Yerel | 15.0.26208.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.AppInsights.Tools | Geliştirici analiz araçları | 15.8.27825.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.DiagnosticTools | .NET profil oluşturma araçları | 15.8.27729.1 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Git | Windows için Git | 15.0.26208.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Graphics | Görüntü ve 3B model düzenleyicileri | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Phone.Emulator.15254 | Windows 10 Mobile öykünücüsü (Fall Creators Update) | 15.0.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.SQL.CLR | SQL Server için CLR veri türleri | 15.0.26208.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.VisualStudioData | Veri kaynakları ve hizmet başvuruları | 15.6.27406.0 | İsteğe Bağlı
Microsoft.VisualStudio.Component.Windows10SDK.17763 | Windows 10 SDK (10.0.17763.0) | 15.9.28307.102 | İsteğe Bağlı
Microsoft.VisualStudio.ComponentGroup.UWP.Cordova | Cordova için evrensel Windows platformu araçları | 15.9.28307.102 | İsteğe Bağlı

## <a name="unaffiliated-components"></a>Kullanıcıyla bağlantılı olmayan bileşenleri

Bu, her türlü iş yükü ile dahil edilmez, ancak tek bir bileşeni olarak seçilebilir bileşenlerdir.

Bileşen kimliği | Ad | Sürüm
--- | --- | ---
Component.Android.Emulator | Android için Visual Studio Öykünücüsü | 15.6.27413.0
Component.Android.NDK.R11C | Android NDK (R11C) | 11.3.14
Component.Android.NDK.R11C_3264 | Android NDK (R11C) (32 bit) | 11.3.16
Component.Android.SDK23 | Android SDK kurulumu (API düzeyi 23) (genel yükleme) | 15.9.28107.0
Component.Android.SDK25 | Android SDK kurulumu (API düzeyi 25) | 15.9.28107.0
Component.GitHub.VisualStudio | Visual Studio için GitHub uzantısı | 2.5.2.2500
Component.Google.Android.Emulator.API23.V2 | Google Android Emulator (API düzeyi 23) (genel yükleme) | 15.6.27413.0
Component.Google.Android.Emulator.API25 | Google Android Emulator (API düzeyi 25) | 15.7.27604.0
Microsoft.Component.Blend.SDK.WPF | .NET için Visual Studio SDK'sı için Blend | 15.6.27406.0
Microsoft.Component.HelpViewer | Yardım Görüntüleyicisi | 15.9.28307.421
Microsoft.VisualStudio.Component.LinqToSql | LINQ to SQL araçları | 15.6.27406.0
Microsoft.VisualStudio.Component.Phone.Emulator | Windows 10 Mobile öykünücüsü (Anniversary Edition) | 15.6.27406.0
Microsoft.VisualStudio.Component.Phone.Emulator.15063 | Windows 10 Mobile öykünücüsü (Creators Update) | 15.6.27406.0
Microsoft.VisualStudio.Component.Runtime.Node.x86.6.4.0 | (X86) Node.js v6.4.0 tabanlı bileşenler için çalışma zamanı | 15.7.27617.1
Microsoft.VisualStudio.Component.Runtime.Node.x86.7.4.0 | (X86) Node.js v7.4.0 tabanlı bileşenler için çalışma zamanı | 15.7.27617.1
Microsoft.VisualStudio.Component.TestTools.CodedUITest | Kodlanmış UI testi | 15.0.26606.0
Microsoft.VisualStudio.Component.TestTools.FeedbackClient | Microsoft Geri Bildirim İstemcisi | 15.6.27406.0
Microsoft.VisualStudio.Component.TestTools.MicrosoftTestManager | Microsoft Test Manager | 15.6.27406.0
Microsoft.VisualStudio.Component.TypeScript.2.0 | TypeScript 2.0 SDK'sı | 15.8.27729.1
Microsoft.VisualStudio.Component.TypeScript.2.1 | TypeScript 2.1 SDK'sı | 15.8.27729.1
Microsoft.VisualStudio.Component.TypeScript.2.2 | TypeScript 2.2 SDK'sı | 15.8.27729.1
Microsoft.VisualStudio.Component.TypeScript.2.5 | TypeScript 2.5 SDK'sı | 15.6.27406.0
Microsoft.VisualStudio.Component.TypeScript.2.6 | TypeScript 2.6 SDK'sı | 15.0.27729.1
Microsoft.VisualStudio.Component.TypeScript.2.7 | TypeScript 2.7 SDK'sı | 15.0.27729.1
Microsoft.VisualStudio.Component.TypeScript.2.8 | TypeScript 2.8 SDK'sı | 15.0.27729.1
Microsoft.VisualStudio.Component.TypeScript.2.9 | TypeScript 2.9 SDK'sı | 15.0.27924.0
Microsoft.VisualStudio.Component.TypeScript.3.0 | 3.0 TypeScript SDK'sı | 15.0.27924.0
Microsoft.VisualStudio.Component.VC.ATL.ARM | ARM için Visual C++ ATL | 15.7.27625.0
Microsoft.VisualStudio.Component.VC.ATL.ARM.Spectre | Spectre azaltmaları ile ARM için Visual C++ ATL | 15.7.27625.0
Microsoft.VisualStudio.Component.VC.ATL.ARM64 | ARM64 için Visual C++ ATL | 15.7.27625.0
Microsoft.VisualStudio.Component.VC.ATL.ARM64.Spectre | Spectre azaltmaları ile ARM64 için Visual C++ ATL | 15.7.27625.0
Microsoft.VisualStudio.Component.VC.ATL.Spectre | Spectre azaltmaları ile Visual C++ ATL (x86/x64) | 15.7.27625.0
Microsoft.VisualStudio.Component.VC.ATLMFC.Spectre | Spectre azaltmaları ile x86/x64 için Visual C++ MFC | 15.7.27625.0
Microsoft.VisualStudio.Component.VC.ClangC2 | Clang/C2 (Deneysel) | 15.7.27520.0
Microsoft.VisualStudio.Component.VC.MFC.ARM | ARM için Visual C++ MFC | 15.7.27625.0
Microsoft.VisualStudio.Component.VC.MFC.ARM.Spectre | Spectre azaltmaları ile ARM için Visual C++ MFC | 15.7.27625.0
Microsoft.VisualStudio.Component.VC.MFC.ARM64 | ARM64 için Visual C++ MFC | 15.7.27625.0
Microsoft.VisualStudio.Component.VC.MFC.ARM64.Spectre | Spectre azaltmaları ile ARM64 için Visual C++ MFC desteği | 15.7.27625.0
Microsoft.VisualStudio.Component.VC.Runtimes.ARM.Spectre | VC ++ 2017 sürüm 15.9 v14.16 kitaplıklar için Spectre (ARM) | 15.9.28230.55
Microsoft.VisualStudio.Component.VC.Runtimes.ARM64.Spectre | VC ++ 2017 sürüm 15.9 v14.16 (ARM64) Spectre için kitaplıklar | 15.9.28230.55
Microsoft.VisualStudio.Component.VC.Runtimes.x86.x64.Spectre | VC ++ 2017 sürüm 15.9 v14.16 (x86 ve x64) Spectre için kitaplıklar | 15.9.28230.55
Microsoft.VisualStudio.Component.VC.Tools.14.11 | VC ++ 2017 sürüm 15.4 v14.11 araç takımı | 15.0.27924.0
Microsoft.VisualStudio.Component.VC.Tools.14.12 | VC ++ 2017 sürüm 15.5 v14.12 araç takımı | 15.0.27924.0
Microsoft.VisualStudio.Component.VC.Tools.14.13 | VC ++ 2017 sürüm 15.6 v14.13 araç takımı | 15.0.27924.0
Microsoft.VisualStudio.Component.VC.Tools.14.14 | VC ++ 2017 sürüm 15.7 v14.14 araç takımı | 15.0.27924.0
Microsoft.VisualStudio.Component.VC.Tools.14.15 | VC ++ 2017 sürüm 15,8 v14.15 araç takımı | 15.0.28230.55
