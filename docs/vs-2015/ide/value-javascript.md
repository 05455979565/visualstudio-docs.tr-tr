---
title: '&lt;değer&gt; (JavaScript) | Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- <value> JavaScript XML tag
- value JavaScript XML tag
ms.assetid: 983e31de-cb1d-411e-b60d-eea6698a26f6
caps.latest.revision: 11
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: bdb645bed570df019c4f4fe15b6865e1197bec67
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42694346"
---
# <a name="ltvaluegt-javascript"></a>&lt;değer&gt; (JavaScript)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [Visual Studio 2017 belgeleri](https://docs.microsoft.com/en-us/visualstudio/).  
  
Belgeleri bilgilerini belirtir `get` ve `set` ECMAScript 3 özellikleri için işlevleri.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
<value type="ValueType" integer="true|false"  
    domElement="true|false" mayBeNull="true|false"  
    elementType="ArrayElementType" elementInteger="true|false"  
    elementDomElement="true|false" elementMayBeNull="true|false"  
    locid="descriptionID">description  
</value>  
```  
  
#### <a name="parameters"></a>Parametreler  
 `type`  
 İsteğe bağlı. Özelliğin veri türü. Tür aşağıdakilerden biri olabilir:  
  
-   Olduğu gibi ECMAScript 5 açıklamasında bir ECMAScript dil türü `Number` ve `Object`.  
  
-   Gibi bir DOM nesnesi `HTMLElement`, `Window`, ve `Document`.  
  
-   Bir JavaScript oluşturucu işlevi.  
  
 `integer`  
 İsteğe bağlı. Varsa `type` olduğu `Number`, özelliği bir tamsayı olup olmadığını belirtir. Kümesine `true` özelliği bir tamsayı; olduğunu belirtmek için Aksi takdirde, kümesine `false`. Bu öznitelik, IntelliSense bilgilerini sağlamak için Visual Studio tarafından kullanılmaz.  
  
 `domElement`  
 İsteğe bağlı. Bu öznitelik kullanım dışı; `type` özniteliği bu öznitelik göre önceliklidir. Bu öznitelik, belgelenmiş özelliği bir DOM öğesi olup olmadığını belirtir. Kümesine `true` özelliği bir DOM öğesi; olduğunu belirtmek için Aksi takdirde, kümesine `false`. Varsa `type` özniteliği ayarlanmamıştır ve `domElement` ayarlanır `true`, IntelliSense belgelenmiş özelliği olarak değerlendirir bir `HTMLElement` deyim tamamlama gerçekleştirirken.  
  
 `mayBeNull`  
 İsteğe bağlı. Belgelenen özelliği ayarlayıp ayarlayamayacağını belirler null. Kümesine `true` özellik ayarlanabilir, aksi takdirde çok belirtmek için ayarlanmış `false`. Varsayılan değer `false` şeklindedir. Bu öznitelik, IntelliSense bilgilerini sağlamak için Visual Studio tarafından kullanılmaz.  
  
 `elementType`  
 İsteğe bağlı. Varsa `type` olduğu `Array`, bu öznitelik, dizideki öğelerin türünü belirtir.  
  
 `elementInteger`  
 İsteğe bağlı. Varsa `type` olduğu `Array` ve `elementType` olduğu `Number`, bu öznitelik, dizideki öğelerin tamsayılar olup olmadığını belirtir. Kümesine `true` göstermek için dizideki öğelerin tamsayılardır; Aksi takdirde, kümesine `false`. Bu öznitelik, IntelliSense bilgilerini sağlamak için Visual Studio tarafından kullanılmaz.  
  
 `elementDomElement`  
 İsteğe bağlı. Bu öznitelik kullanım dışı; `elementType` özniteliği bu öznitelik göre önceliklidir. Varsa `type` olduğu `Array`, bu öznitelik, dizideki öğelerin DOM öğeleri olup olmadığını belirtir. Kümesine `true` belirtmek için öğeleri DOM öğeleri; Aksi takdirde, kümesine `false`. Varsa `elementType` özniteliği ayarlanmamıştır ve `elementDomElement` ayarlanır `true`, IntelliSense her öğe dizisi değerlendirir bir `HTMLElement` deyim tamamlama gerçekleştirirken.  
  
 `elementMayBeNull`  
 İsteğe bağlı. Varsa `type` olduğu `Array`, dizideki öğelerin ayarlayıp ayarlayamayacağını belirler null. Kümesine `true` dizideki öğelerin ayarlanabilir, aksi takdirde çok belirtmek için ayarlanmış `false`. Varsayılan değer `false` şeklindedir. Bu öznitelik, IntelliSense bilgilerini sağlamak için Visual Studio tarafından kullanılmaz.  
  
 `locid`  
 İsteğe bağlı. Yerelleştirme özelliği hakkında bilgi için tanımlayıcı. Tanımlayıcıdır ya da bir üye kimliği veya karşılık gelen `name` öznitelik değeri bir ileti paketteki OpenAjax meta verileri tarafından tanımlanır. Belirtilen biçim tanımlayıcı türü bağımlı [ \<loc >](../ide/loc-javascript.md) öğesi.  
  
 `description`  
 İsteğe bağlı. Özellik açıklaması.  
  
## <a name="remarks"></a>Açıklamalar  
 ECMAScript 5 özellikleri kullanım [ \<Özet >](../ide/summary-javascript.md) öğesi.  
  
 Kullanım `<value>` öğesi hemen önce `get` veya `set` işlevi.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örneği kullanma işlemini gösterir `<value>` öğe üzerinde bir `get` işlevi.  
  
```javascript  
function Sys$CancelEventArgs$get_cancel() {  
    /// <value type="Boolean" locid="P:J#Sys.CancelEventArgs.cancel"></value>  
    if (arguments.length !== 0) throw Error.parameterCount();  
    return this._cancel();  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [XML Belge Açıklamaları](../ide/xml-documentation-comments-javascript.md)



