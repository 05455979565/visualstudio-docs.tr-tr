---
title: Using Microsoft.VisualStudio.TestTools.UnitTesting Members in Unit Tests | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-test
ms.topic: conceptual
ms.assetid: 0fa335fd-e442-448f-913f-25a19df90a93
caps.latest.revision: 8
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 93a62b6fe5493b78a3c18c1adb87761cdb894670
ms.sourcegitcommit: 2da366ba9ad124366f6502927ecc720985fc2f9e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68871551"
---
# <a name="using-microsoftvisualstudiotesttoolsunittesting-members-in-unit-tests"></a>Birim Testlerinde Microsoft.VisualStudio.TestTools.UnitTesting Üyelerini Kullanma
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]
Birim testi çerçevesi içinde [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]birim testini destekler. Birim testlerini kodlarunuzda, <xref:Microsoft.VisualStudio.TestTools.UnitTesting> ad alanındaki sınıfları ve üyeleri kullanın. Birim testini sıfırdan yazdığınızda veya sınamakta olduğunuz koddan oluşturulmuş bir birim testini iyileştirirken bunları kullanabilirsiniz.

## <a name="groups-of-elements"></a>Öğe grupları
 Birim testi çerçevesine daha net bir genel bakış sağlamaya yardımcı olmak için, bu bölüm UnitTesting Ad alanının öğelerini ilgili işlevsellik grupları halinde düzenler.

> [!NOTE]
> Adları dize özniteliğiyle sonuçlu öznitelik öğeleri, dize özniteliğiyle veya olmadan kullanılabilir. Örneğin, aşağıdaki iki kod örneği aynı şekilde çalışır:
>
> `[TestClass()]`
>
> `[TestClassAttribute()]`

### <a name="elements-used-for-data-driven-testing"></a>Veri odaklı test için kullanılan öğeler
 Veri tabanlı birim testlerini ayarlamak için aşağıdaki öğeleri kullanın. Daha fazla bilgi için bkz [. nasıl yapılır: Veri tabanlı birim testi](../test/how-to-create-a-data-driven-unit-test.md) ve [izlenecek yol oluşturun: Bir veri kaynağı](../test/walkthrough-using-a-configuration-file-to-define-a-data-source.md)tanımlamak için yapılandırma dosyası kullanma.

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.DataAccessMethod>

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.DataSourceAttribute>

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.DataSourceElement>

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.DataSourceElementCollection>

## <a name="attributes-used-to-establish-a-calling-order"></a>Arama sırası oluşturmak için kullanılan öznitelikler
 Aşağıdaki özniteliklerden biriyle donatılmış bir kod öğesi, belirttiğiniz anda çağırılır. Daha fazla bilgi için bkz. [birim testinin anatomi](https://msdn.microsoft.com/a03d1ee7-9999-4e7c-85df-7d9073976144).

### <a name="for-assemblies"></a>Derlemeler için
 AssemblyInitialize ve AssemblyCleanup, derleme yüklenmeden hemen önce ve derleme bellekten kaldırıldıktan hemen sonra çağrılır.

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.AssemblyInitializeAttribute>

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.AssemblyCleanupAttribute>

### <a name="for-classes"></a>Sınıflar için
 Sınıfınız yüklenmeden ve sınıfınız bellekten kaldırılmadan önce ClassInitialize ve Classctaanup değeri hemen çağırılır.

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.ClassInitializeAttribute>

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.ClassCleanupAttribute>

### <a name="for-test-methods"></a>Test yöntemleri için

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestInitializeAttribute>

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestCleanupAttribute>

## <a name="attributes-used-to-identify-test-classes-and-methods"></a>Test sınıflarını ve yöntemlerini tanımlamak için kullanılan öznitelikler
 Her test sınıfının TestClass özniteliği olmalıdır ve her test yönteminin TestMethod özniteliği olmalıdır. Daha fazla bilgi için bkz. [birim testinin anatomi](https://msdn.microsoft.com/a03d1ee7-9999-4e7c-85df-7d9073976144).

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestClassAttribute>

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestMethodAttribute>

## <a name="assert-classes-and-related-exceptions"></a>Onaylama sınıfları ve Ilgili özel durumlar
 Birim testleri, çeşitli onay deyimleri, özel durumlar ve özniteliklerin kullanımıyla belirli uygulama davranışlarını doğrulayabilirler. Daha fazla bilgi için bkz. [onaylama sınıflarını kullanma](../test/using-the-assert-classes.md).

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert>

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.CollectionAssert>

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.StringAssert>

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.AssertFailedException>

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.AssertInconclusiveException>

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.UnitTestAssertException>

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.ExpectedExceptionAttribute>

## <a name="the-testcontext-class"></a>TestContext sınıfı
 Aşağıdaki öznitelikler ve bunlara atanan değerler belirli bir test yöntemi için [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] Özellikler penceresi görüntülenir. Bu özniteliklere birim testinin kodu aracılığıyla erişilmek üzere tasarlanmamıştır. Bunun yerine, ' nin [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]IDE veya [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] test motoru aracılığıyla sizin tarafınızdan, birim testinin kullanıldığı ya da çalıştırıldığı yolları etkiler. Örneğin, bu özniteliklerin bazıları Test Yöneticisi penceresinde ve Test Sonuçları penceresinde sütun olarak görünür, bu da testleri ve test sonuçlarını gruplamak ve sıralamak için bunları kullanabileceğiniz anlamına gelir. Bu tür bir öznitelik, birim testlerine rastgele meta veriler eklemek için kullandığınız TestPropertyAttribute ' dir. Örneğin, birim testini ile `[TestProperty("TestPass", "Accessibility")]`işaretleyerek, bu testin kapsamakta olduğu bir test geçişinin adını depolamak için kullanabilirsiniz. Ya da bunu, test türünün bir göstergesini depolamak için kullanabilirsiniz: `[TestProperty("TestKind", "Localization")]`. Bu özniteliği kullanarak oluşturduğunuz özellik ve atadığınız Özellik değeri, her ikisi de başlık [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] **testine özgü**Özellikler penceresi görüntülenir.

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.OwnerAttribute>

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.DeploymentItemAttribute>

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.DescriptionAttribute>

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.IgnoreAttribute>

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.PriorityAttribute>

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestPropertyAttribute>

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.WorkItemAttribute>

## <a name="test-configuration-classes"></a>Test yapılandırması sınıfları

- [ObjectTypes](/previous-versions/visualstudio/visual-studio-2013/dd987428(v=vs.120))

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestConfigurationSection>

## <a name="attributes-used-for-generating-reports"></a>Rapor oluşturmak için kullanılan öznitelikler
 Bu bölümdeki öznitelikler, bir [!INCLUDE[esprtfs](../includes/esprtfs-md.md)] takım projesinin proje hiyerarşisindeki varlıklarıyla süsledikleri test yöntemiyle ilgilidir.

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.CssIterationAttribute>

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.CssProjectStructureAttribute>

## <a name="classes-used-with-private-accessors"></a>Özel Erişimcilerde kullanılan sınıflar
 [Özel bir erişimci oluşturmak Için Publicize kullanma](https://msdn.microsoft.com/2056c6a7-6672-42a7-8f53-fead33c56deb)bölümünde açıklandığı gibi, özel bir yöntem için bir birim testi oluşturabilirsiniz. Bu kuşak, PrivateObject sınıfının bir nesnesini örnekleyen özel bir erişimci sınıfı oluşturur. PrivateObject sınıfı, özel erişimci sürecinin bir parçası olarak yansıma kullanan bir sarmalayıcı sınıftır. PrivateType sınıfı benzerdir, ancak özel örnek yöntemleri çağırmak yerine özel statik yöntemleri çağırmak için kullanılır.

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.PrivateObject>

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.PrivateType>

## <a name="see-also"></a>Ayrıca bkz.

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting>