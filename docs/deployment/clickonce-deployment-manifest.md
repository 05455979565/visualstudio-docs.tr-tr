---
title: ClickOnce dağıtım bildirimi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce, deployment manifests
- deployment manifests [ClickOnce]
ms.assetid: 8457e615-e3b6-4990-8dcf-11bc590e4e9b
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: dd67f3db61662535a0a8522575e716886602f5b7
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/19/2018
---
# <a name="clickonce-deployment-manifest"></a>ClickOnce Dağıtım Bildirimi
Bir dağıtım bildirimi tanımlayan bir XML dosyasıdır bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] geçerli tanımlaması dahil olmak üzere dağıtım [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] dağıtmak için uygulama sürümü.  
  
 Dağıtım bildirimleri aşağıdaki öğeleri ve öznitelikleri vardır.  
  
|Öğe|Açıklama|Öznitelikler|  
|-------------|-----------------|----------------|  
|[\<Assembly > öğesi](../deployment/assembly-element-clickonce-deployment.md)|Gerekli. En üst düzey öğesi.|`manifestVersion`|  
|[\<assemblyIdentity > öğesi](../deployment/assemblyidentity-element-clickonce-deployment.md)|Gerekli. İçin uygulama bildirimini tanımlar [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] uygulama.|`name`<br /><br /> `version`<br /><br /> `publicKeyToken`<br /><br /> `processorArchitecture`<br /><br /> `culture`|  
|[\<Açıklama > öğesi](../deployment/description-element-clickonce-deployment.md)|Gerekli. Kabuk varlığı oluşturmak için kullanılan uygulama bilgilerini tanımlar ve **Program Ekle veya Kaldır** Denetim Masası.|`publisher`<br /><br /> `product`<br /><br /> `supportUrl`|  
|[\<Dağıtım > öğesi](../deployment/deployment-element-clickonce-deployment.md)|İsteğe bağlı. Güncelleştirmeleri ve sistem maruz dağıtımı için kullanılan öznitelikleri tanımlar.|`install`<br /><br /> `minimumRequiredVersion`<br /><br /> `mapFileExtensions`<br /><br /> `disallowUrlActivation`<br /><br /> `trustUrlParameters`|  
|[\<compatibleFrameworks > öğesi](../deployment/compatibleframeworks-element-clickonce-deployment.md)|Gerekli. Burada bu uygulamayı yükleyip çalıştırabileceği .NET Framework sürümleri tanımlar.|`SupportUrl`|  
|[\<bağımlılık > öğesi](../deployment/dependency-element-clickonce-deployment.md)|Gerekli. Dağıtım için yüklemek için uygulama sürümü, uygulama bildirimi konumunu tanımlar.|`preRequisite`<br /><br /> `visible`<br /><br /> `dependencyType`<br /><br /> `codebase`<br /><br /> `size`|  
|[\<publisherIdentity > öğesi](../deployment/publisheridentity-element-clickonce-deployment.md)|İmzalanmış bildirimler için gerekli. Bu dağıtım bildirimini imzalamış yayımcı hakkında bilgi içerir.|`Name`<br /><br /> `issuerKeyHash`|  
|[\<İmza > öğesi](../deployment/signature-element-clickonce-deployment.md)|İsteğe bağlı. Bu dağıtım bildirimini dijital olarak imzalamak için gerekli bilgileri içerir.|Yok.|  
|[\<customErrorReporting > öğesi](../deployment/customerrorreporting-element-clickonce-deployment.md)|İsteğe bağlı. Bir hata oluştuğunda göstermek için bir URI belirtir.|URI|  
  
## <a name="remarks"></a>Açıklamalar  
 Dağıtım bildirimi dosyasını tanımlayan bir [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] güncel sürüm ve diğer dağıtım ayarlarını içeren uygulama dağıtımı. Uygulama ve dağıtım içinde yer alan tüm dosyaların geçerli sürümü açıklanmaktadır uygulama bildirimi başvurur.  
  
 Daha fazla bilgi için bkz: [ClickOnce güvenliği ve dağıtımı](../deployment/clickonce-security-and-deployment.md).  
  
## <a name="file-location"></a>Dosya konumu  
 Dağıtım bildirim dosyası uygulamanın geçerli sürümü için doğru uygulama bildirimine başvurur. Bir uygulama dağıtımı yeni bir sürümü kullanılabilir duruma getirdiğinizde, yeni bir uygulama bildirimi başvurmak için dağıtım bildirimi güncelleştirmeniz gerekir.  
  
 Dağıtım bildirimi dosyası kesin adlandırılmış olmalıdır ve yayımcı doğrulaması için sertifikaları da içerebilir.  
  
## <a name="file-name-syntax"></a>Dosya adı sözdizimi  
 Dağıtım bildirim dosyasının adı .application uzantısı ile bitmelidir.  
  
## <a name="examples"></a>Örnekler  
 Aşağıdaki kod örnek bir dağıtım bildirimi gösterilmektedir.  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<asmv1:assembly xsi:schemaLocation="urn:schemas-microsoft-com:asm.v1 assembly.adaptive.xsd"  
  manifestVersion="1.0"  
  xmlns:asmv3="urn:schemas-microsoft-com:asm.v3"  
  xmlns:dsig=http://www.w3.org/2000/09/xmldsig#  
  xmlns:co.v1="urn:schemas-microsoft-com:clickonce.v1"  
  xmlns:co.v2="urn:schemas-microsoft-com:clickonce.v2"  
  xmlns="urn:schemas-microsoft-com:asm.v2"  
  xmlns:asmv1="urn:schemas-microsoft-com:asm.v1"  
  xmlns:asmv2="urn:schemas-microsoft-com:asm.v2"  
  xmlns:xrml="urn:mpeg:mpeg21:2003:01-REL-R-NS"  
  xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
  <assemblyIdentity   
    name="My Application Deployment.app"  
    version="1.0.0.0"  
    publicKeyToken="43cb1e8e7a352766"  
    language="neutral"  
    processorArchitecture="x86"  
    xmlns="urn:schemas-microsoft-com:asm.v1" />  
  <description  
    asmv2:publisher="My Company Name"  
    asmv2:product="My Application"  
    xmlns="urn:schemas-microsoft-com:asm.v1" />  
  <deployment install="true">  
    <subscription>  
      <update>  
        <expiration maximumAge="0" unit="days" />  
      </update>  
    </subscription>  
    <deploymentProvider codebase="\\myServer\sampleDeployment\MyApplicationDeployment.application" />  
  </deployment>  
  <compatibleFrameworks xmlns="urn:schemas-microsoft-com:clickonce.v2">  
    <framework targetVersion="4.0" profile="Full" supportedRuntime="4.0.20506" />  
    <framework targetVersion="4.0" profile="Client" supportedRuntime="4.0.20506" />  
  </compatibleFrameworks>  
  <dependency>  
    <dependentAssembly  
      dependencyType="install"  
      codebase="1.0.0.0\My Application Deployment.exe.manifest"  
      size="6756">  
      <assemblyIdentity  
        name="My Application Deployment.exe"  
        version="1.0.0.0"  
        publicKeyToken="43cb1e8e7a352766"  
        language="neutral"  
        processorArchitecture="x86"  
        type="win32" />  
      <hash>  
        <dsig:Transforms>  
          <dsig:Transform Algorithm="urn:schemas-microsoft-com:HashTransforms.Identity" />  
        </dsig:Transforms>  
        <dsig:DigestMethod Algorithm="http://www.w3.org/2000/09/xmldsig#sha1" />  
        <dsig:DigestValue>E506x9FwNauks7UjQywmzgtd3FE=</dsig:DigestValue>  
      </hash>  
    </dependentAssembly>  
  </dependency>  
<publisherIdentity name="CN=DOMAIN\MyUsername" issuerKeyHash="18312a18a21b215ecf4cdb20f5a0e0b0dd263c08" /><Signature Id="StrongNameSignature" xmlns="http://www.w3.org/2000/09/xmldsig#">  
...  
</Signature></asmv1:assembly>  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ClickOnce Uygulamalarını Yayımlama](../deployment/publishing-clickonce-applications.md)