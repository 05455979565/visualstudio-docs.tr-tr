---
title: C++ için CTest kullanma
ms.date: 01/23/2020
ms.topic: how-to
ms.author: corob
manager: jillfra
ms.workload:
- cplusplus
author: corob-msft
ms.openlocfilehash: c429c9e676ead54bb9f168e3220bf2d4791fac63
ms.sourcegitcommit: 1d4f6cc80ea343a667d16beec03220cfe1f43b8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85287239"
---
# <a name="how-to-use-ctest-for-c-in-visual-studio-2017-and-later"></a>Visual Studio 2017 ve üzeri sürümlerde C++ için CTest kullanma

CMake (CTest içeren), C++ iş yükünde **Masaüstü geliştirmenin** bir bileşeni olarak varsayılan olarak VISUAL Studio IDE ile tümleşiktir. Makinenize yüklemeniz gerekiyorsa Visual Studio Yükleyicisi programını açın, **C++ Ile masaüstü geliştirme** düğmesine tıklayın ve ardından **Değiştir**' e tıklayın. İş yükü bileşenleri listesi altında **Windows için C++ CMake Araçları ' nı** seçin.

## <a name="to-write-tests"></a>Testleri yazmak için

Visual Studio 'da CMake desteği, Visual Studio proje sistemini kapsamaz. Bu nedenle, CTest testlerini tıpkı herhangi bir CMake ortamında olduğu gibi yazar ve yapılandırırsınız. `enable_testing()`Testi etkinleştirmek için komutunu ve `add_test()` `gtest_discover_tests()` Yeni bir test eklemek için veya komutunu kullanın. CTest hakkında daha fazla bilgi için bkz. [CMake belgeleri](https://gitlab.kitware.com/cmake/community/wikis/doc/ctest/Testing-With-CTest). 

Visual Studio 'da CMake 'i kullanma hakkında daha fazla bilgi için bkz. [Visual Studio 'Da CMake projeleri](/cpp/build/cmake-projects-in-visual-studio).

## <a name="to-run-tests"></a>Testleri çalıştırmak için

CTest, **Test Gezgini** ile tamamen tümleşiktir ve hem Google hem de Boost birim testi çerçevelerini destekler. Bu çerçeveler, varsayılan olarak C++ iş yükünde **masaüstü geliştirme** içindeki bileşenler olarak dahil edilmiştir. Ancak, bir projeyi Visual Studio 'nun eski bir sürümünden yükseltiyorsanız, Visual Studio Yükleyicisi programını kullanarak bu çerçeveleri yüklemeniz gerekebilir.

Aşağıdaki çizimde Google Test Framework kullanarak bir CTest çalıştırmasının sonuçları gösterilmektedir:

![Visual Studio 'da Google Test Framework ile CTest](media/ctest-test-explorer.png)

CTest kullanıyorsanız, Google veya Boost bağdaştırıcılarını kullandıysanız, sonuçları bireysel test yöntemi düzeyi yerine CTest düzeyinde görürsünüz. Hata ayıklamanıza ve yalnızca CTest yürütülebilir dosyalarında hata verebilir, ancak tek testlerin yığın izlemeleri desteklenmez.

## <a name="see-also"></a>Ayrıca bkz.

- [C/C++ için birim testleri yazma](writing-unit-tests-for-c-cpp.md)
