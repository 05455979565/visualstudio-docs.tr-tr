---
title: MSBuild ayrılmış ve Iyi bilinen Özellikler | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, reserved properties
ms.assetid: 99333e61-83c9-4804-84e3-eda297c2478d
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 5c3d97185446560343b36b22f73e0b320b5a28d6
ms.sourcegitcommit: 1d4f6cc80ea343a667d16beec03220cfe1f43b8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85289228"
---
# <a name="msbuild-reserved-and-well-known-properties"></a>MSBuild ayrılmış ve iyi bilinen Özellikler

MSBuild, proje dosyası ve MSBuild ikilileri hakkında bilgi depolayan önceden tanımlanmış bir özellikler kümesi sağlar. Bu özellikler, diğer MSBuild özellikleriyle aynı şekilde değerlendirilir. Örneğin, özelliğini kullanmak için `MSBuildProjectFile` , yazın `$(MSBuildProjectFile)` .

 MSBuild, ayrılmış ve iyi bilinen özellikleri önceden tanımlamak için aşağıdaki tablodaki değerleri kullanır. Ayrılmış Özellikler geçersiz kılınamaz, ancak aynı adlı ortam özellikleri, genel özellikler veya proje dosyasında belirtilen özellikler kullanılarak iyi bilinen özellikler geçersiz kılınabilir.

## <a name="reserved-and-well-known-properties"></a>Ayrılmış ve iyi bilinen Özellikler

Bu bölümdeki tabloda, önceden tanımlanmış MSBuild özellikleri gösterilmektedir. Tablodaki örnek sütun, aşağıdaki örnek proje dosyası ile ilgilidir ve içinde bulunduğu varsayılır `C:\Source\Repos\ConsoleApp1\ConsoleApp1` ve MSBuild, Visual Studio 2019 sürüm 16,7 ' in önizleme derlemesi ile özel komut satırı seçenekleri olmadan çağrıldığında bu özelliklerin değerlerini gösterir.

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp3.1</TargetFramework>
  </PropertyGroup>
</Project>
```

| Özellik | Ayrılmış veya iyi bilinen | Açıklama | Örnek |
|----------------------------------|------------------------| - | - |
| `MSBuildBinPath` | Ayrıldı | Kullanılmakta olan MSBuild ikililerinin bulunduğu klasörün mutlak yolu (örneğin, *C:\Windows\Microsoft.NET\Framework \\ \<versionNumber> *). MSBuild dizinindeki dosyalara başvurmanız gerekirse bu özellik faydalıdır.<br /><br /> Bu özelliğe son ters eğik çizgiyi eklemeyin. | `C:\Program Files (x86)\Microsoft Visual Studio\2019\Preview\MSBuild\Current\Bin` |
| `MSBuildExtensionsPath` | İyi bilinen | .NET Framework 4 ' te tanıtılan: varsayılan değerleri ve arasında bir fark yoktur `MSBuildExtensionsPath` `MSBuildExtensionsPath32` . `MSBUILDLEGACYEXTENSIONSPATH`Önceki sürümlerde varsayılan değerinin davranışını etkinleştirmek için ortam değişkenini null olmayan bir değere ayarlayabilirsiniz `MSBuildExtensionsPath` .<br /><br /> .NET Framework 3,5 ve önceki sürümlerde varsayılan değeri, `MSBuildExtensionsPath` geçerli işlemin bit büyüklüğüne bağlı olarak, *\Program Files \\ * veya *\Program Files (x86)* klasörü altındaki MSBuild alt klasörünün yolunu işaret eder. Örneğin, 64 bit bir makinedeki 32 bitlik bir işlem için bu özellik, *\Program Files (x86)* klasörünü işaret eder. 64 bit makinede 64 bitlik bir işlem için bu özellik *\Program Files* klasörünü işaret eder.<br /><br /> Bu özelliğe son ters eğik çizgiyi eklemeyin.<br /><br /> Bu konum, özel hedef dosyaları yerleştirmek için kullanışlı bir yerdir. Örneğin, hedef dosyalarınız *\Program Files\msbuild\myfiles\northwind.exe dizinine* yüklenip daha sonra bu XML kodu kullanılarak proje dosyalarına aktarılabilir:<br /><br /> `<Import Project="$(MSBuildExtensionsPath)\MyFiles\Northwind.targets"/>` | `C:\Program Files (x86)\Microsoft Visual Studio\2019\Preview\MSBuild`|
| `MSBuildExtensionsPath32` | İyi bilinen | *\Program Files* veya *\Program Files (x86)* klasörü altındaki MSBuild alt klasörünün yolu. Yol her zaman 32 bit makinedeki 32-bit *\Program Files (x86)* klasörünü ve 64-bit makinesindeki *\Program dosyalarını* işaret eder. ". Ayrıca bkz `MSBuildExtensionsPath` `MSBuildExtensionsPath64` . ve.<br /><br /> Bu özelliğe son ters eğik çizgiyi eklemeyin. | `C:\Program Files (x86)\Microsoft Visual Studio\2019\Preview\MSBuild`|
| `MSBuildExtensionsPath64` | İyi bilinen | *\Program Files* klasörü altındaki MSBuild alt klasörünün yolu. 64 bitlik bir makine için bu yol her zaman *\Program Files* klasörünü işaret eder. 32 bitlik bir makine için bu yol boştur. Ayrıca bkz `MSBuildExtensionsPath` `MSBuildExtensionsPath32` . ve.<br /><br /> Bu özelliğe son ters eğik çizgiyi eklemeyin. | `C:\Program Files\MSBuild`|
| `MSBuildInteractive` | Ayrıldı | `true`MSBuild etkileşimli çalışıyorsa, kullanıcı girişine izin verir. Bu ayar, `-interactive` komut satırı seçeneği tarafından denetlenir. | `false` |
| `MSBuildLastTaskResult` | Ayrıldı | `true`önceki görev herhangi bir hata olmadan tamamlanırsa (Uyarılar olsa bile) veya `false` önceki görevde hatalar varsa. Genellikle, bir görevde bir hata oluştuğunda, hata bu projede gerçekleşen son şeydir. Bu nedenle, bu özelliğin değeri hiçbir `false` şekilde bu senaryolar haricinde değildir:<br /><br /> - `ContinueOnError` [Task öğesi (MSBuild)](../msbuild/task-element-msbuild.md) özniteliği `WarnAndContinue` (veya `true` ) veya olarak ayarlandığında `ErrorAndContinue` .<br /><br /> -, Bir `Target` alt öğe olarak bir Ida bir [hataöğesi (MSBuild)](../msbuild/onerror-element-msbuild.md) içerir. | `true` |
| `MSBuildNodeCount` | Ayrıldı | Oluşturulurken kullanılan eşzamanlı işlem sayısı üst sınırı. Bu, komut satırında **-maxcpucount** için belirttiğiniz değerdir. Değer belirtmeden **-maxcpucount** belirttiyseniz, `MSBuildNodeCount` bilgisayardaki işlemci sayısını belirtir. Daha fazla bilgi için bkz. [komut satırı başvurusu](../msbuild/msbuild-command-line-reference.md) ve [paralel olarak birden çok proje oluşturma](../msbuild/building-multiple-projects-in-parallel-with-msbuild.md). | 1 |
| `MSBuildProgramFiles32` | Ayrıldı | 32 bit program klasörünün konumu; Örneğin, *C:\Program Files (x86)*.<br /><br /> Bu özelliğe son ters eğik çizgiyi eklemeyin. | `C:\Program Files (x86)`|
| `MSBuildProjectDefaultTargets` | Ayrıldı | Öğesinin özniteliğinde belirtilen hedeflerin tamamı listesi `DefaultTargets` `Project` . Örneğin, aşağıdaki `Project` öğe bir özellik değerine sahip olacaktır `MSBuildDefaultTargets` `A;B;C` :<br /><br /> `<Project DefaultTargets="A;B;C" >` | `Build`|
| `MSBuildProjectDirectory` | Ayrıldı | Proje dosyasının bulunduğu dizinin mutlak yolu, örneğin *C:\company\myproduct*.<br /><br /> Bu özelliğe son ters eğik çizgiyi eklemeyin. | `C:\Source\Repos\ConsoleApp1\ConsoleApp1` |
| `MSBuildProjectDirectoryNoRoot` | Ayrıldı | `MSBuildProjectDirectory`Kök sürücü hariç, özelliğin değeri.<br /><br /> Bu özelliğe son ters eğik çizgiyi eklemeyin. | `Source\Repos\ConsoleApp1\ConsoleApp1`|
| `MSBuildProjectExtension` | Ayrıldı | Proje dosyasının süresi de dahil olmak üzere dosya adı uzantısı; Örneğin, *. proj*. | `.csproj`|
| `MSBuildProjectFile` | Ayrıldı | Proje dosyasının dosya adı uzantısı da dahil olmak üzere dosyanın tamamı. Örneğin, *MyApp. proj*. | `ConsoleApp1.csproj`|
| `MSBuildProjectFullPath` | Ayrıldı | Dosya adı uzantısı da dahil olmak üzere, proje dosyasının mutlak yolu ve tam dosya adı. Örneğin, *C:\mycompany\myproduct\myapp.exe*. | `c:\Source\Repos\ConsoleApp1\ConsoleApp1\ConsoleApp1.csproj`|
| `MSBuildProjectName` | Ayrıldı | Dosya adı uzantısı olmadan proje dosyasının dosya adı; Örneğin, *MyApp*. | `ConsoleApp1` |
| `MSBuildRuntimeType` | Ayrıldı | Şu anda yürütülmekte olan çalışma zamanının türü. MSBuild 15 ' te tanıtılmıştır. Değer tanımsız (MSBuild 15 ' ten önce), MSBuild 'in `Full` `Core` .NET Core üzerinde çalıştığını (örneğin `dotnet build` , içinde) ya da MSBuild 'in `Mono` mono üzerinde çalıştığını belirten, masaüstünde .NET Framework. | `Full` |
| `MSBuildStartupDirectory` | Ayrıldı | MSBuild 'in çağrıldığı klasörün mutlak yolu. Bu özelliği kullanarak, her dizinde * \<dirs> . proj* dosyaları oluşturmadan bir proje ağacındaki belirli bir noktanın altındaki her şeyi oluşturabilirsiniz. Bunun yerine, burada gösterildiği gibi yalnızca bir projeniz vardır — örneğin, *c:\traversal.proj*.<br /><br /> `<Project ...>     <ItemGroup>         <ProjectFiles              Include="$            (MSBuildStartupDirectory)            **\*.csproj"/>     </ItemGroup>     <Target Name="build">         <MSBuild             Projects="@(ProjectFiles)"/>     </Target> </Project>`<br /><br /> Ağaçta herhangi bir noktada derlemek için şunu yazın:<br /><br /> `msbuild c:\traversal.proj`<br /><br /> Bu özelliğe son ters eğik çizgiyi eklemeyin. | `c:\Source\Repos\ConsoleApp1` |
| `MSBuildThisFile` | Ayrıldı | Öğesinin dosya adı ve dosya uzantısı kısmı `MSBuildThisFileFullPath` . | `ConsoleApp1.csproj` |
| `MSBuildThisFileDirectory` | Ayrıldı | Öğesinin dizin bölümü `MSBuildThisFileFullPath` .<br /><br /> Yola son ters eğik çizgiyi ekleyin. | `c:\Source\Repos\ConsoleApp1\ConsoleApp1\` |
| `MSBuildThisFileDirectoryNoRoot` | Ayrıldı | `MSBuildThisFileFullPath`Kök sürücü hariç, öğesinin dizin bölümü.<br /><br /> Yola son ters eğik çizgiyi ekleyin. | `Source\Repos\ConsoleApp1\ConsoleApp1\` |
| `MSBuildThisFileExtension` | Ayrıldı | Öğesinin dosya adı uzantısı kısmı `MSBuildThisFileFullPath` . | `.csproj` |
| `MSBuildThisFileFullPath` | Ayrıldı | Çalıştıran hedefi içeren projenin veya hedef dosyanın mutlak yolu.<br /><br /> İpucu: asıl proje dosyasına göre değil, hedef dosya ile ilişkili olan bir hedefler dosyasında göreli bir yol belirtebilirsiniz. | `c:\Source\Repos\ConsoleApp1\ConsoleApp1\ConsoleApp1.csproj` |
| `MSBuildThisFileName` | Ayrıldı | Dosya adı uzantısı olmadan öğesinin dosya adı kısmı `MSBuildThisFileFullPath` . | `ConsoleApp1` |
| `MSBuildToolsPath` | Ayrıldı | Değeri ile ilişkili MSBuild sürümünün yükleme yolu `MSBuildToolsVersion` .<br /><br /> Yola son ters eğik çizgiyi eklemeyin.<br /><br /> Bu özellik geçersiz kılınamaz. | `C:\Program Files (x86)\Microsoft Visual Studio\2019\Preview\MSBuild\Current\Bin` |
| `MSBuildToolsVersion` | Ayrıldı | Projeyi derlemek için kullanılan MSBuild Araç takımının sürümü.<br /><br /> Note: bir MSBuild Araç Takımı, bir uygulama oluşturmak için kullanılan görevlerden, hedeflerin ve araçlardan oluşur. Araçlar *csc.exe* ve *vbc.exe*gibi derleyiciler içerir. Daha fazla bilgi için bkz. [araç takımı (araçları sürümü)](../msbuild/msbuild-toolset-toolsversion.md)ve [Standart ve özel araç takımı yapılandırması](../msbuild/standard-and-custom-toolset-configurations.md). | `Current` |
| `MSBuildVersion` | Ayrıldı | Projeyi derlemek için kullanılan MSBuild sürümü. <br /><br/> Bu özellik geçersiz kılınamıyor, aksi takdirde hata iletisi `MSB4004 - The 'MSBuildVersion' property is reserved, and can not be modified.` döndürülür. | 16.7.0 |

## <a name="names-that-conflict-with-msbuild-elements"></a>MSBuild öğeleriyle çakışan adlar

Yukarıdaki ' a ek olarak, MSBuild dil öğelerine karşılık gelen adlar Kullanıcı tanımlı özellikler, öğeler veya öğe meta verileri için kullanılamaz:

* VisualStudioProject
* Hedef
* PropertyGroup
* Çıkış
* ItemGroup
* UsingTask
* ProjectExtensions
* OnError
* ImportGroup
* Seçin:
* Oluşturulurken
* Güvenmiyorsanız

## <a name="see-also"></a>Ayrıca bkz.

- [MSBuild başvurusu](../msbuild/msbuild-reference.md)

- [MSBuild özellikleri](../msbuild/msbuild-properties.md)
