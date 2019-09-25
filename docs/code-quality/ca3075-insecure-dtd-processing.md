---
title: 'CA3075: Güvensiz DTD İşleme'
ms.date: 03/18/2019
ms.topic: reference
ms.assetid: 65798d66-7a30-4359-b064-61a8660c1eed
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 42efb51dfe9c447538fe8f01bdd37c73bf993d8f
ms.sourcegitcommit: 0c2523d975d48926dd2b35bcd2d32a8ae14c06d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/24/2019
ms.locfileid: "71237113"
---
# <a name="ca3075-insecure-dtd-processing"></a>CA3075: Güvensiz DTD İşleme

|||
|-|-|
|TypeName|Insecuredtdprocessing|
|CheckId|CA3075|
|Kategori|Microsoft.Security|
|Son değişiklik|Kırılmamış|

## <a name="cause"></a>Sebep

Güvenli olmayan <xref:System.Xml.XmlReaderSettings.DtdProcessing%2A> örnekler kullanırsanız veya dış varlık kaynaklarına başvurdıysanız, ayrıştırıcı güvenilmeyen girişi kabul edebilir ve duyarlı bilgileri saldırganlar 'e açığa çıkarabilir.

## <a name="rule-description"></a>Kural açıklaması

Bir *belge türü tanımı (DTD)* , bir XML ayrıştırıcısının, [World Wide Web Konsorsiyumu (W3C) Genişletilebilir Biçimlendirme Dili (XML) 1,0](http://www.w3.org/TR/2008/REC-xml-20081126/)tarafından tanımlanan bir belgenin geçerliliğini belirleyebilmesi için iki yönden biridir. Bu kural, geliştiricilerin olası [bilgi açığa çıkması](/dotnet/framework/wcf/feature-details/information-disclosure) tehditleri veya [hizmet reddi (DOS)](/dotnet/framework/wcf/feature-details/denial-of-service) saldırıları hakkında uyarması için güvenilmeyen verilerin kabul edildiği özellikleri ve örnekleri arar. Bu kural şu durumlarda tetiklenir:

- DtdProcessing, kullanarak <xref:System.Xml.XmlUrlResolver>dış XML <xref:System.Xml.XmlReader> varlıklarını çözen örnek üzerinde etkindir.

- XML <xref:System.Xml.XmlNode.InnerXml%2A> 'deki özelliği ayarlanır.

- <xref:System.Xml.XmlReaderSettings.DtdProcessing%2A>Özellik Parse olarak ayarlandı.

- Güvenilmeyen giriş, <xref:System.Xml.XmlSecureResolver>yerine kullanılarak <xref:System.Xml.XmlResolver> işlenir.

- Yöntemi <xref:System.Xml.XmlReader.Create%2A?displayProperty=nameWithType> , güvenli olmayan <xref:System.Xml.XmlReaderSettings> bir örnekle veya hiç örnek olmadan çağrılır.

- <xref:System.Xml.XmlReader>, güvenli olmayan varsayılan ayarlarla veya değerlerle oluşturulur.

Bu durumların her birinde, sonuç aynıdır: XML 'nin işlendiği makinedeki dosya sistemi veya ağ paylaşımlarından içerik saldırgana sunulur veya DTD işleme bir DoS vektörü olarak kullanılabilir.

## <a name="how-to-fix-violations"></a>İhlalleri çözme

- Yol bilgilerinin açığa çıkmasını önlemek için tüm XmlTextReader özel durumlarını doğru bir şekilde yakalayın ve işleyin.

- XmlTextReader 'ın erişebileceği kaynakları kısıtlamak içinkullanın.<xref:System.Xml.XmlSecureResolver>

- <xref:System.Xml.XmlResolver> Özelliği **null**olarak ayarlayarak <xref:System.Xml.XmlReader> herhangi bir dış kaynağı açmaya izin vermeyin.

- <xref:System.Data.DataViewManager.DataViewSettingCollectionString%2A?displayProperty=nameWithType> Özelliğin güvenilir bir kaynaktan atandığından emin olun.

**.NET 3,5 ve öncesi**

- <xref:System.Xml.XmlReaderSettings.ProhibitDtd%2A> Özelliği **true**olarak ayarlayarak güvenilmeyen kaynaklarla uğraşıyorsanız DTD işlemesini devre dışı bırakın.

- XmlTextReader sınıfı tam güven devralma talebine sahiptir.

**.NET 4 ve üzeri**

- <xref:System.Xml.XmlReaderSettings.DtdProcessing%2A?displayProperty=nameWithType> Özelliği **yasakla** veya **Yoksay**olarak ayarlayarak güvenilmeyen kaynaklarla uğraşıyorsanız DtdProcessing 'ı etkinleştirmemeye özen gösterin.

- Load () yönteminin tüm InnerXml durumlarında bir XmlReader örneği aldığından emin olun.

> [!NOTE]
> Bu kural, bazı geçerli XmlSecureResolver örneklerinde hatalı pozitif sonuçlar bildirebilir.

## <a name="when-to-suppress-warnings"></a>Uyarıların ne zaman bastırılamıyor

Girişin güvenilen bir kaynaktan geldiğinden emin olmadığınız için, bu uyarıdan bir kuralı engellemez.

## <a name="pseudo-code-examples"></a>Sözde kod örnekleri

### <a name="violation"></a>Edildiği

```csharp
using System.IO;
using System.Xml.Schema;

class TestClass
{
    public XmlSchema Test
    {
        get
        {
            var src = "";
            TextReader tr = new StreamReader(src);
            XmlSchema schema = XmlSchema.Read(tr, null); // warn
            return schema;
        }
    }
}
```

### <a name="solution"></a>Çözüm

```csharp
using System.IO;
using System.Xml;
using System.Xml.Schema;

class TestClass
{
    public XmlSchema Test
    {
        get
        {
            var src = "";
            TextReader tr = new StreamReader(src);
            XmlTextReader reader = new XmlTextReader(tr) { DtdProcessing = DtdProcessing.Prohibit };
            XmlSchema schema = XmlSchema.Read(reader , null);
            return schema;
        }
    }
}
```

### <a name="violation"></a>Edildiği

```csharp
using System.Xml;

namespace TestNamespace
{
    public class TestClass
    {
        public XmlReaderSettings settings = new XmlReaderSettings();
        public void TestMethod(string path)
        {
            var reader = XmlReader.Create(path, settings);  // warn
        }
    }
}
```

### <a name="solution"></a>Çözüm

```csharp
using System.Xml;

namespace TestNamespace
{
    public class TestClass
    {
        public XmlReaderSettings settings = new XmlReaderSettings()
        {
            DtdProcessing = DtdProcessing.Prohibit
        };

        public void TestMethod(string path)
        {
            var reader = XmlReader.Create(path, settings);
        }
    }
}
```

### <a name="violations"></a>Lerinden

```csharp
using System.Xml;

namespace TestNamespace
{
    public class DoNotUseSetInnerXml
    {
        public void TestMethod(string xml)
        {
            XmlDocument doc = new XmlDocument() { XmlResolver = null };
            doc.InnerXml = xml; // warn
        }
    }
}
```

```csharp
using System.Xml;

namespace TestNamespace
{
    public class DoNotUseLoadXml
    {
        public void TestMethod(string xml)
        {
            XmlDocument doc = new XmlDocument(){ XmlResolver = null };
            doc.LoadXml(xml); // warn
        }
    }
}
```

### <a name="solution"></a>Çözüm

```csharp
using System.Xml;

public static void TestMethod(string xml)
{
    XmlDocument doc = new XmlDocument() { XmlResolver = null };
    System.IO.StringReader sreader = new System.IO.StringReader(xml);
    XmlReader reader = XmlReader.Create(sreader, new XmlReaderSettings() { XmlResolver = null });
    doc.Load(reader);
}
```

### <a name="violation"></a>Edildiği

```csharp
using System.IO;
using System.Xml;
using System.Xml.Serialization;

namespace TestNamespace
{
    public class UseXmlReaderForDeserialize
    {
        public void TestMethod(Stream stream)
        {
            XmlSerializer serializer = new XmlSerializer(typeof(UseXmlReaderForDeserialize));
            serializer.Deserialize(stream); // warn
        }
    }
}
```

### <a name="solution"></a>Çözüm

```csharp
using System.IO;
using System.Xml;
using System.Xml.Serialization;

namespace TestNamespace
{
    public class UseXmlReaderForDeserialize
    {
        public void TestMethod(Stream stream)
        {
            XmlSerializer serializer = new XmlSerializer(typeof(UseXmlReaderForDeserialize));
            XmlReader reader = XmlReader.Create(stream, new XmlReaderSettings() { XmlResolver = null });
            serializer.Deserialize(reader );
        }
    }
}
```

### <a name="violation"></a>Edildiği

```csharp
using System.Xml;
using System.Xml.XPath;

namespace TestNamespace
{
    public class UseXmlReaderForXPathDocument
    {
        public void TestMethod(string path)
        {
            XPathDocument doc = new XPathDocument(path); // warn
        }
    }
}
```

### <a name="solution"></a>Çözüm

```csharp
using System.Xml;
using System.Xml.XPath;

namespace TestNamespace
{
    public class UseXmlReaderForXPathDocument
    {
        public void TestMethod(string path)
        {
            XmlReader reader = XmlReader.Create(path, new XmlReaderSettings() { XmlResolver = null });
            XPathDocument doc = new XPathDocument(reader);
        }
    }
}
```

### <a name="violation"></a>Edildiği

```csharp
using System.Xml;

namespace TestNamespace
{
    class TestClass
    {
        public XmlDocument doc = new XmlDocument() { XmlResolver = new XmlUrlResolver() };
    }
}
```

### <a name="solution"></a>Çözüm

```csharp
using System.Xml;

namespace TestNamespace
{
    class TestClass
    {
        public XmlDocument doc = new XmlDocument() { XmlResolver = null }; // or set to a XmlSecureResolver instance
    }
}
```

### <a name="violations"></a>Lerinden

```csharp
using System.Xml;

namespace TestNamespace
{
    class TestClass
    {
        private static void TestMethod()
        {
            var reader = XmlTextReader.Create(""doc.xml""); //warn
        }
    }
}
```

```csharp
using System.Xml;

namespace TestNamespace
{
    public class TestClass
    {
        public void TestMethod(string path)
        {
            try {
                XmlTextReader reader = new XmlTextReader(path); // warn
            }
            catch { throw ; }
            finally {}
        }
    }
}
```

### <a name="solution"></a>Çözüm

```csharp
using System.Xml;

namespace TestNamespace
{
    public class TestClass
    {
        public void TestMethod(string path)
        {
            XmlReaderSettings settings = new XmlReaderSettings() { XmlResolver = null };
            XmlReader reader = XmlReader.Create(path, settings);
        }
    }
}
```
