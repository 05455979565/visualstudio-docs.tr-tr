---
title: Görsel C++ kod parçacıkları
ms.date: 11/04/2016
ms.topic: reference
author: mikeblome
ms.author: mblome
manager: markl
dev_langs:
- CPP
ms.workload:
- cplusplus
ms.openlocfilehash: 9c1bcef00116e0c5f09099344926d924113e5982
ms.sourcegitcommit: 85d66dc9fea3fa49018263064876b15aeb6f9584
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68461630"
---
# <a name="visual-c-code-snippets"></a>Görsel C++ kod parçacıkları

Visual Studio 'da kod dosyalarınıza yaygın olarak kullanılan kodu C++ eklemek için kod parçacıklarını kullanabilirsiniz. Genel olarak, kod parçacıklarını ile aynı şekilde kullanabilirsiniz C#, ancak varsayılan kod parçacıkları kümesi farklıdır.

Kodunuzda belirli bir konuma (ekleme) bir kod parçacığı ekleyebilir veya seçili bir kodu kod parçacığı ile çevreleyin.

## <a name="insert-a-code-snippet"></a>Kod parçacığı Ekle

Bir kod parçacığı eklemek için bir C++ kod dosyası ( *. cpp* veya *. h*) açın, dosyanın içinde herhangi bir yere tıklayın ve aşağıdakilerden birini yapın:

- Bağlam menüsünü almak için sağ tıklayın ve **kod parçacığı Ekle** ' yi seçin.

- **Düzenle/IntelliSense** menüsünde **kod parçacığı Ekle** ' yi seçin.

- Kısayol tuşlarını kullanın: **CTRL**+**K** X+

**#İf**başlayan seçeneklerin bir listesini görmeniz gerekir. **#İf**' yi seçtiğinizde, dosyaya aşağıdaki kodun eklendiğini görmeniz gerekir:

```cpp
#if 0

#endif // 0
```

Daha sonra **0** değerini doğru koşulla değiştirebilirsiniz.

## <a name="use-a-code-snippet-to-surround-selected-code"></a>Seçilen kodu çevrelemek için bir kod parçacığı kullanın

Seçilen kodu çevrelemek için bir kod parçacığı kullanmak için bir satır (veya birden çok satır) seçin ve aşağıdakilerden birini yapın:

- Bağlam menüsünü almak için sağ tıklayın ve şununla **Çevrele** ' yi seçin

- **IntelliSense** **düzenleme** > menüsünde **Şununla Çevrele** ' yi seçin

- Klavye kullanarak şunları bas: **CTRL**+**K** S+

**#İf**seçin. Şuna benzer bir şey görmeniz gerekir:

```cpp
#if 0
#include "pch.h"  // or whatever line you had selected
#endif // 0
```

Daha sonra 0 değerini doğru koşulla değiştirebilirsiniz.

## <a name="where-can-i-find-a-complete-list-of-the-c-code-snippets"></a>C++ Kod parçacıklarının tamamen bir listesini nerede bulabilirim?

Kod parçacıkları **yöneticisine** ( **Araçlar** menüsünde) C++ gidip **dili** **C++görsele**ayarlayarak kod parçacıklarının tüm listesini bulabilirsiniz. Aşağıdaki pencerede, **görsel C++** ' i genişletin. Tüm C++ kod parçacıklarının adlarını alfabetik sırada görmeniz gerekir.

Çoğu kod parçacıklarının adı kendi kendine açıklayıcıdır, ancak bazı adlar kafa karıştırıcı olabilir.

## <a name="class-vs-classi"></a>Sınıf ve classı karşılaştırması

**Sınıf** parçacığı, uygun varsayılan Oluşturucu ve yıkıcısı ile `MyClass`adlı bir sınıfın tanımını sağlar; burada Oluşturucu ve yıkıcının tanımlarının sınıfın dışında bulunduğu yer vardır:

```cpp
class MyClass
{
public:
    MyClass();
    ~MyClass();

private:

};

MyClass::MyClass()
{
}

MyClass::~MyClass()
{
}
```

**Classı** kod parçacığı ayrıca adlı `MyClass`bir sınıfın tanımını da sağlar, ancak varsayılan Oluşturucu ve yıkıcısı sınıf tanımı içinde tanımlanmıştır:

```cpp
class MyClass
{
public:
    MyClass()
    {
    }

    ~MyClass()
    {
    }

private:

};
```

## <a name="for-vs-forr-vs-rfor"></a>vs. öğrencilerinize vs rfor için

Farklı türlerde `for` döngüler sağlayan kod parçacıkları **için** üç farklı vardır.

**Rfor** kod parçacığı, [Aralık tabanlı](/cpp/cpp/range-based-for-statement-cpp) bir for döngüsü (bağlantı) sağlar. Bu yapı, dizin tabanlı `for` Döngülerde tercih edilir.

```cpp
for (auto& i : v)
{

}
```

**For** kod parçacığında, koşulun `for` bir nesnenin uzunluğuna (içindeki `size_t`) göre kullanıldığı bir döngü sağlar.

```cpp
for (size_t i = 0; i < length; i++)
{

}
```

**Öğrencilerinize** kod parçacığı, koşulun bir `for` nesnenin uzunluğuna (tamsayı cinsinden) dayanmakta olduğu ters bir döngü sağlar.

```cpp
for (int i = length - 1; i >= 0; i--)
{

}
```

## <a name="the-destructor-snippet-"></a>Yıkıcı parçacığı (~)

Yıkıcı parçacığı ( **~** ) farklı bağlamlarda farklı davranışlar gösterir. Bu kod parçacığını bir sınıfın içine eklerseniz, bu sınıf için bir yıkıcı sağlar. Örneğin, aşağıdaki kod verildiğinde:

```cpp
class SomeClass {

};
```

Yıkıcı parçacığı eklerseniz, için `SomeClass`bir yıkıcı sağlar:

```cpp
class SomeClass {
    ~SomeClass()
    {

    }
};
```

Yıkıcı parçacığı bir sınıfın dışında eklemeye çalışırsanız, yer tutucu adına sahip bir yıkıcı sağlar:

```cpp
~TypeNamePlaceholder()
{
```

## <a name="see-also"></a>Ayrıca bkz.

- [Kod parçacıkları](../ide/code-snippets.md)