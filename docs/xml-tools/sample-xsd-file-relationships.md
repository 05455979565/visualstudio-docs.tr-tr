---
title: 'Örnek XSD Dosyası: İlişkiler'
ms.date: 11/04/2016
ms.topic: sample
ms.assetid: 60126510-b7dd-4cb4-92d3-9883590b92f2
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 5a52d152a78ee585cc2724d8504feff1e72558cf
ms.sourcegitcommit: 2975d722a6d6e45f7887b05e9b526e91cffb0bcf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/20/2020
ms.locfileid: "75592561"
---
# <a name="sample-xsd-file-relationships"></a>Örnek XSD dosyası: İlişkiler

Aşağıdaki XSD dosyası, XSD Şema Tasarımcısı belgelerinde çeşitli örneklerde kullanılır. Bu dosya ek açıklamalar ve belgeler ile bir satınalma sipariş şemasıdır.

```xml
<xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema">

  <xs:element name="pet" type="PetType"/>

  <xs:attributeGroup name="NameAgeAttributes">
    <xs:attribute name="age" type="xs:integer" use="required"/>
    <xs:attribute name="name" type="xs:string" use="required"/>
  </xs:attributeGroup>

  <xs:complexType name="PetType">
    <xs:attributeGroup ref="NameAgeAttributes"/>
  </xs:complexType>

  <xs:element name="cat" substitutionGroup="pet">
    <xs:complexType>
      <xs:complexContent>
        <xs:extension base="PetType">
          <xs:sequence>
            <xs:element name="weight" type="xs:integer"/>
            <xs:element name="color" type="xs:string"/>
            <xs:element name="breed" type="xs:integer"/>
          </xs:sequence>
        </xs:extension>
      </xs:complexContent>
    </xs:complexType>
  </xs:element>

  <xs:element name="dog" substitutionGroup="pet">
    <xs:complexType>
      <xs:complexContent>
        <xs:extension base="PetType">
          <xs:sequence>
            <xs:element name="weight" type="xs:integer"/>
            <xs:element name="color" type="xs:string"/>
            <xs:element name="breed" type="xs:integer"/>
          </xs:sequence>
        </xs:extension>
      </xs:complexContent>
    </xs:complexType>
  </xs:element>

</xs:schema>
```

> [!NOTE]
> Örnek şirketler, kuruluşlar, ürünler, alan adları, e-posta adresleri, logolar, kişiler, yerler ve burada gösterilen olaylar hayalidir. Herhangi bir gerçek şirket, kuruluş, ürün, etki alanı adı, e-posta adresi, logo, kişi, yer veya olaylarla hiçbir ilişki amaçlanmamıştır veya çıkarılmalıdır.
