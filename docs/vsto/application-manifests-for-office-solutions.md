---
title: Office çözümleri için uygulama bildirimleri
ms.custom: ''
ms.date: 02/02/2017
ms.technology: office-development
ms.prod: visual-studio-dev15
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- application manifests [Office development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: df388fb346c43f173ec1f96e3869088d7ce5b9dc
ms.sourcegitcommit: 6944ceb7193d410a2a913ecee6f40c6e87e8a54b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/06/2018
ms.locfileid: "35677774"
---
# <a name="application-manifests-for-office-solutions"></a>Office çözümleri için uygulama bildirimleri
  Bir uygulama bildirimi, Microsoft Office çözümü yüklenen derlemeler açıklayan bir XML dosyasıdır. Microsoft Office geliştirme araçlarını Visual Studio'da kullanmak [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)] tanımlanan uygulama bildirim şeması [ClickOnce Uygulama bildirimi](/visualstudio/deployment/clickonce-application-manifest) başvuru.  
  
 Office çözümleri için uygulama bildirimleri kullanmak aşağıdaki [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)] öğeler ve öznitelikler.  
  
|Öğe|Açıklama|Öznitelikler|  
|-------------|-----------------|----------------|  
|[&#60;derleme&#62; öğesi &#40;ClickOnce uygulaması&#41;](/visualstudio/deployment/assembly-element-clickonce-deployment)|Gerekli. En üst düzey öğe.|**ManifestVersion**|  
|[&#60;assemblyIdentity&#62; öğesi &#40;ClickOnce uygulaması&#41;](/visualstudio/deployment/assemblyidentity-element-clickonce-deployment)|Gerekli. Tanımlayan [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)] uygulamanın birincil derlemesi.|**Adı**<br /><br /> **Sürüm**<br /><br /> **PublicKeyToken**<br /><br /> **ProcessorArchitecture**<br /><br /> **Dil**|  
|[&#60;trustInfo&#62; öğesi &#40;ClickOnce uygulaması&#41;](/visualstudio/deployment/trustinfo-element-clickonce-application)|Uygulama güvenlik gereksinimlerini tanımlar.|Yok.|  
|[&#60;entryPoint&#62; öğesi &#40;ClickOnce uygulaması&#41;](/visualstudio/deployment/entrypoint-element-clickonce-application)|Gerekli. Yürütme için uygulama kodu giriş noktasını tanımlar.|**Adı**<br /><br /> **dependencyName**<br /><br /> **customHostSpecified**|  
|[&#60;bağımlılık&#62; öğesi &#40;ClickOnce uygulaması&#41;](/visualstudio/deployment/dependency-element-clickonce-deployment)|Gerekli. Uygulamayı çalıştırmak için gereken her bir bağımlılığın tanımlar. İsteğe bağlı olarak önceden yüklenmiş gereken bütünleştirilmiş kodları tanımlar.|Yok.|  
|[&#60;Dosya&#62; öğesi &#40;ClickOnce uygulaması&#41;](/visualstudio/deployment/file-element-clickonce-application)|Gerekli. Uygulama tarafından kullanılan her bir derleme olmayan dosya tanımlar. Dosya ile ilgili Bileşen Nesne Modeli (COM) yalıtım veriler içerebilir.|**Adı**<br /><br /> **Boyutu**|  
  
 Office çözümleri için uygulama bildirimleri öğesi sahip `co.v1` ad alanı.  
  
```xml  
<entryPoint>  
    <co.v1:customHostSpecified />  
</entryPoint>   
```  
  
 Bu uygulama bildirimleri aşağıdaki öğeleri ve öznitelikleri de `vstav3` ad alanı.  
  
```xml  
<addIn>  
  <entryPointsCollection>  
    <entryPoints>  
      <entryPoint>  
      </entryPoint>  
    </entryPoints>  
  </entryPointsCollection>  
  <update></update>  
  <postActions>  
    <postAction>  
      <postActionData>  
      </postActionData>  
    <postAction>  
  </postActions>  
  <application>  
    <customizations>  
      <customization>  
      </customization>  
    </customizations>  
  </application  
</addIn>  
```  
  
|Öğe|Açıklama|Öznitelikler|  
|-------------|-----------------|----------------|  
|[&#60;customHostSpecified&#62; öğesi &#40;Visual Studio'da Office geliştirme&#41;](../vsto/customhostspecified-element-office-development-in-visual-studio.md)|Gerekli. Bildirimi, özellikle bir Office çözümü olarak işaretler.|Yok.|  
|[&#60;eklenti&#62; öğesi &#40;Visual Studio'da Office geliştirme&#41;](../vsto/addin-element-office-development-in-visual-studio.md)|Gerekli. Giriş noktaları, tek bir ad alanında depolar.|Yok.|  
|[&#60;entryPointsCollection&#62; öğesi &#40;Visual Studio'da Office geliştirme&#41;](../vsto/entrypointscollection-element-office-development-in-visual-studio.md)|Gerekli. Bir veya daha fazla Office çözümleri için tüm derlemeleri gruplandırır.|**id**|  
|[&#60;giriş noktaları&#62; öğesi &#40;Visual Studio'da Office geliştirme&#41;](../vsto/entrypoints-element-office-development-in-visual-studio.md)|Gerekli. Bir Office çözümü çalıştırmak için tüm derlemeleri gruplandırır.|Yok.|  
|[&#60;entryPoint&#62; öğesi &#40;Visual Studio'da Office geliştirme&#41;](../vsto/entrypoint-element-office-development-in-visual-studio.md)|Gerekli. Office çözümünü çalıştırmak için derleme tanımlar.|**class**<br /><br /> **Sözleşme**|  
|[&#60;Güncelleştirme&#62; öğesi &#40;Visual Studio'da Office geliştirme&#41;](../vsto/update-element-office-development-in-visual-studio.md)|Gerekli. Güncelleştirmeler çözümü yapılandırır.|**Etkin**<br /><br /> **süre sonu**|  
|[&#60;postActions&#62; öğesi &#40;Visual Studio'da Office geliştirme&#41;](../vsto/postactions-element-office-development-in-visual-studio.md)|İsteğe bağlı. Office çözümleri yüklendikten sonra çalışan tüm dağıtım sonrası eylemleri, gruplandırır.|Yok.|  
|[&#60;postAction&#62; öğesi &#40;Visual Studio'da Office geliştirme&#41;](../vsto/postaction-element-office-development-in-visual-studio.md)|İsteğe bağlı. Dağıtım sonrası eylemi tanımlar.|Yok.|  
|[&#60;postActionData&#62; öğesi &#40;Visual Studio'da Office geliştirme&#41;](../vsto/postactiondata-element-office-development-in-visual-studio.md)|İsteğe bağlı. Dağıtım sonrası eylemi için verileri yapılandırır.|Yok.|  
|[&#60;Uygulama&#62; öğesi &#40;Visual Studio'da Office geliştirme&#41;](../vsto/application-element-office-development-in-visual-studio.md)|Gerekli. Uygulamaya özgü bilgilerin tek bir düğümde sarmalar.|Yok.|  
|[&#60;Özelleştirmeleri&#62; öğesi &#40;Visual Studio'da Office geliştirme&#41;](../vsto/customizations-element-office-development-in-visual-studio.md)|Gerekli. Ayrı bir ad alanındaki tüm uygulama ana bilgisayarı özel bilgileri depolar.|Yok.|  
|[&#60;özelleştirme&#62; öğesi &#40;Visual Studio'da Office geliştirme&#41;](../vsto/customization-element-office-development-in-visual-studio.md)|Gerekli. Uygulama konak özgü bilgileri ayrı bir ad alanında depolar.|**xmlns**|  
|[&#60;Belge&#62; öğesi &#40;Visual Studio'da Office geliştirme&#41;](../vsto/document-element-office-development-in-visual-studio.md)|Yalnızca belge düzeyi çözümleri için gereklidir. Özelleştirme-özel bilgileri depolar.|**SolutionID**|  
|[&#60;appAddin&#62; öğesi &#40;Visual Studio'da Office geliştirme&#41;](../vsto/appaddin-element-office-development-in-visual-studio.md)|Yalnızca uygulama düzeyinde çözümler için gereklidir. Özelleştirme-özel bilgileri depolar.|**Uygulama**<br /><br /> **LoadBehavior**<br /><br /> **anahtar adı**|  
|[&#60;friendlyName&#62; öğesi &#40;Visual Studio'da Office geliştirme&#41;](../vsto/friendlyname-element-office-development-in-visual-studio.md)|İsteğe bağlı. VSTO görünen Eklentisi adı yüklü VSTO eklentileri listesinde yer depolar.|Yok.|  
|[&#60;Açıklama&#62; öğesi &#40;Visual Studio'da Office geliştirme&#41;](../vsto/description-element-office-development-in-visual-studio.md)|Yalnızca VSTO eklentileri için gereklidir. Yüklü programlar listesinde açıklamasını depolar.|Yok.|  
|[&#60;formRegions&#62; öğesi &#40;Visual Studio'da Office geliştirme&#41;](../vsto/formregions-element-office-development-in-visual-studio.md)|Yalnızca Outlook VSTO form bölgeleri içeren eklentileri için gereklidir.|Yok.|  
|[&#60;formRegion&#62; öğesi &#40;Visual Studio'da Office geliştirme&#41;](../vsto/formregion-element-office-development-in-visual-studio.md)|Yalnızca Outlook VSTO form bölgeleri içeren eklentileri için gereklidir.|**Ad**|  
|[&#60;vstoRuntime&#62; öğesi &#40;Visual Studio'da Office geliştirme&#41;](../vsto/vstoruntime-element-office-development-in-visual-studio.md)|Gerekli. Office çözüm tarafından desteklenen Office çalışma zamanı için Visual Studio Araçları'nın belirli bir sürümünü açıklar.|**Yayın**<br /><br /> **Sürüm**<br /><br /> **supportUrl**|  
  
## <a name="remarks"></a>Açıklamalar  
 Uygulamayı el ile düzenleyebilirsiniz ve Office çözümlerinde dağıtım bildirimleri. Ardından, uygulamayı yeniden imzalamak gerekir ve dağıtım bildirimlerini bildirim oluşturma ve düzenleme aracı kullanarak (*mage.exe* ve *mageui.exe*). Daha fazla bilgi için [nasıl yapılır: yeniden, uygulama ve dağıtım bildirimlerini imzalama](/visualstudio/deployment/how-to-re-sign-application-and-deployment-manifests).  
  
## <a name="file-location"></a>Dosya konumu  
 Bir uygulama bildirimi, tek bir çözüm sürümüne özeldir. Bu nedenle, uygulama bildirimleri ayrı ayrı dağıtım bildirimlerinden depolanmalıdır. [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] sonra ilişkili sürümünde adlı bir alt sürüme özgü dosyaları yerleştirir *uygulama dosyaları* yayımlama klasörünün alt.  
  
## <a name="file-name-syntax"></a>Dosya adı sözdizimi  
 Bir uygulama bildirimi dosyasının adı tam adını ve uzantısını uygulamanın tanımlandığı gibi olmalıdır **assemblyIdentity** uzantısı tarafından izlenen öğesini *.manifest*. Örneğin, başvuran bir uygulama bildirimi *OutlookAddIn1.dll* özelleştirme aşağıdaki dosya adı sözdizimi kullanmanız.  
  
 `OutlookAddIn1.dll.manifest`  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Office çözümleri için dağıtım bildirimleri](../vsto/deployment-manifests-for-office-solutions.md)   
 [ClickOnce Uygulama bildirimi](/visualstudio/deployment/clickonce-application-manifest)  
  
  