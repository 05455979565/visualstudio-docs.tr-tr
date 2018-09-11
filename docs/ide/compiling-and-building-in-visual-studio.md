---
title: Derleme ve Visual Studio'da oluşturma
ms.date: 07/14/2017
ms.prod: visual-studio-dev15
ms.technology: vs-ide-compile
ms.topic: conceptual
helpviewer_keywords:
- builds [Visual Studio], about building in Visual Studio
- custom build steps, types of builds
ms.assetid: c7958821-285f-4e28-9e7a-b5d8b40336a1
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d7ee37ddd9899b979d8440202c89d03284b26f48
ms.sourcegitcommit: 1ab675a872848c81a44d6b4bd3a49958fe673c56
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2018
ms.locfileid: "44279082"
---
# <a name="compile-and-build-in-visual-studio"></a>Derleme ve Visual Studio'da derleyin

Bir derlemeyi çalıştırmaya derlemeler ve yürütülebilir uygulamalar herhangi bir noktada, kaynak kodunuzu geliştirme döngüsü sırasında oluşturur. Genel olarak, derleme işlemi Windows, ASP.NET, mobil uygulamalar ve diğerleri gibi birçok farklı proje türlerinde çok benzer. Derleme işlemi ayrıca C#, Visual Basic, C++ ve F # gibi programlama dilleri arasında çok benzer.

Kodunuzu genellikle oluşturarak hızlı bir şekilde sözdizimi, yanlış yazılmış anahtar sözcükler gibi derleme zamanı hataları belirlemek ve uyuşmazlıkları yazın. Ayrıca hızlı bir şekilde algılayın ve sık sık oluşturma ve kod hata ayıklama sürümlerini çalıştıran mantık hataları ve anlamsal hataları gibi çalışma zamanı hataları düzeltin.

Başarılı bir derleme, aslında bir doğrulama uygulamanın kaynak kodunu doğru söz dizimini içerir ve kitaplıkları, derlemeler ve diğer bileşenleri için tüm statik başvuruları Çözüldü ' dir. Bunun ardından uygun her ikisinde de çalışması için test edilebilir çalıştırılabilir bir uygulamaya üreten bir [ortam hata ayıklama](../debugger/index.md) ve el ile ve otomatik testler için çeşitli [kod kalitesini doğrulamak](../test/improve-code-quality.md). Uygulamanın tam olarak test sonra müşterilerinize dağıtmak için bir yayın sürümünü ardından derleyebilirsiniz. Bu işlem, giriş için bkz. [izlenecek yol: uygulama oluşturma](../ide/walkthrough-building-an-application.md).

Bir uygulama oluşturmak için aşağıdaki yöntemlerden herhangi birini kullanabilirsiniz: Visual Studio IDE, MSBuild komut satırı araçları, Team Foundation Build ve Azure DevOps Hizmetleri:

| Derleme yöntemi | Yararları |
| --- |--- | --- |
| IDE |-Derlemeleri hemen oluşturun ve bunları bir hata ayıklayıcıda test edin.<br />-C++ ve C# projeleri için birden çok işlemcili derlemeleri çalıştırın.<br />-Derleme sistemin farklı yönlerini özelleştirin. |
| MSBuild komut satırı| -Visual Studio yüklemeden projeleri oluşturun.<br />-Çalışma birden çok işlemcili için tüm proje türleri oluşturur.<br />-Birçok alan yapı sisteminin özelleştirin.|
| Team Foundation Derlemesi | -Bir sürekli tümleştirme/sürekli teslim işlem hattı bir parçası olarak yapı sürecinizi otomatik hale getirin.<br />-Her derleme ile otomatik testler için geçerlidir.<br />-Yapı işlemleri için neredeyse sınırsız bulut tabanlı kaynakların paylaşmayan kullanır.<br />-Yapı iş akışını değiştirin ve ayrıntılı bir şekilde özelleştirilmiş görevleri gerçekleştirmek için yapı etkinlikleri oluşturun.|

Bu bölümdeki belgeler, daha fazla IDE tabanlı yapı işleminin ayrıntılarına gider. Diğer yöntemler hakkında daha fazla bilgi için bkz. [MSBuild](../msbuild/msbuild.md) ve [Azure işlem hatları](/azure/devops/pipelines/index?view=vsts)sırasıyla.

## <a name="overview-of-building-from-the-ide"></a>IDE'den oluşturmaya genel bakış

Bir proje oluşturduğunuzda, Visual Studio projeyi ve projeyi içeren çözüm derleme yapılandırmaları varsayılan oluşturulur.  Bu yapılandırmaları nasıl çözümler ve projeler dağıtılan ve derlenen tanımlar. Proje yapılandırmaları, özellikle bir hedef Platformu (örneğin, Windows veya Linux) için benzersizdir ve türlerinin (örneğin, hata ayıklama veya sürüm) oluşturun. İster ve kendi yapılandırmalarınızı gerektiği gibi oluşturabilirsiniz ancak bu yapılandırmalar düzenleyebilirsiniz.

IDE içinden yapı ilk bir giriş için bkz. [izlenecek yol: uygulama oluşturma](walkthrough-building-an-application.md).

Ardından, bkz: [oluşturma ve projeler ve çözümler Visual Studio'da Temizleme](building-and-cleaning-projects-and-solutions-in-visual-studio.md) farklı yönlerini özelleştirmeleri hakkında bilgi edinmek için işlemi yapabilirsiniz. Özelleştirmeleri içerir [çıktı dizini değiştirerek](how-to-change-the-build-output-directory.md), [derleme olayları belirtme özel](specifying-custom-build-events-in-visual-studio.md), [proje bağımlılıkları yönetmek](how-to-create-and-remove-project-dependencies.md), [yapı günlüğünü yönetme dosyaları](how-to-view-save-and-configure-build-log-files.md), ve [Derleyici uyarılarını gizleme](how-to-suppress-compiler-warnings.md).

Burada, çeşitli diğer görevleri keşfedebilirsiniz:
- [Derleme yapılandırmalarını anlama](understanding-build-configurations.md)
- [Derleme platformlarını anlama](understanding-build-platforms.md)
- [Proje ve çözüm özelliklerini yönetme](managing-project-and-solution-properties.md).
- Derleme olayları belirtme [C#](how-to-specify-build-events-csharp.md) ve [Visual Basic](how-to-specify-build-events-visual-basic.md).
- [Derleme seçeneklerini ayarlama](reference/options-dialog-box-projects-and-solutions-build-and-run.md)
- [Paralel olarak birden çok proje derleme](../msbuild/building-multiple-projects-in-parallel-with-msbuild.md).

## <a name="see-also"></a>Ayrıca bkz.

- [Web sitesi projeleri oluşturma (derleme)](http://msdn.microsoft.com/Library/a9cbb88c-8fff-4c67-848b-98fbfd823193)
