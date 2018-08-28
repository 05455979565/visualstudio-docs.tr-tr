---
title: Tasarım uyarıları | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.codeanalysis.designrules
helpviewer_keywords:
- design warnings
- managed code analysis warnings, design warnings
- warnings, design
ms.assetid: 34e65a18-560c-423f-814f-519089e318cf
caps.latest.revision: 27
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 6f7ba768d27334052c16f13b114d990156bb4a59
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42690440"
---
# <a name="design-warnings"></a>Tasarım Uyarıları
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Bu konuda en son sürümünü şu yolda bulunabilir: [tasarım uyarıları](https://docs.microsoft.com/visualstudio/code-quality/design-warnings).  
  
Tasarım uyarıları bağlılığı .NET Framework tasarım yönergeleri için destek.  
  
## <a name="in-this-section"></a>Bu Bölümde  
  
|Kural|Açıklama|  
|----------|-----------------|  
|[CA1000: Genel türlerde statik üyeleri belirtme](../code-quality/ca1000-do-not-declare-static-members-on-generic-types.md)|Genel türün statik üyesi çağrıldığında tür bağımsız değişkeni tür için belirlenmelidir. Destek çıkarımı desteklenmeyen genel örnek üyesi çağrıldığında tür bağımsız değişkeni üye için belirlenmelidir. Bu iki durumda tür bağımsız değişkenini belirleyen sözdizimi farklıdır ve kolaylıkla karıştırılır.|  
|[CA1001: Atılabilir alanlara sahip olan türler atılabilir olmalıdır](../code-quality/ca1001-types-that-own-disposable-fields-should-be-disposable.md)|Bir sınıfı bildirir ve System.IDisposable türde bir örnek alanıyla uygular ve sınıf IDisposable'ı uygulamaz. IDisposable alanını derleyen sınıf, yönetilmeyen kaynağı dolaylı yoldan sahiplenir ve IDisposable arayüzünü uygulamalıdır.|  
|[CA1002: Genel listeleri gösterme](../code-quality/ca1002-do-not-expose-generic-lists.md)|System.Collections.Generic.List < (biri \<(T >) >) değil devralma performans için tasarlanmış bir genel koleksiyondur. Bu nedenle, Liste herhangi bir sanal üyeyi içermiyor. Bunun yerine devralma için tasarlanmış genel koleksiyonlar maruz kalmalıdır.|  
|[CA1003: Genel olay işleyici örnekleri kullan](../code-quality/ca1003-use-generic-event-handler-instances.md)|Void döndüren, imzası iki parametre (Birincisi nesne ve ikincisi Eventargs'a atanamaz türü) ve içeren derleme hedefleri içeren bir temsilci türü içeren [!INCLUDE[dnprdnlong](../includes/dnprdnlong-md.md)].|  
|[CA1004: Genel metotlar tür parametresi sağlamalıdır](../code-quality/ca1004-generic-methods-should-provide-type-parameter.md)|Tip argümanının açıkça özelleştirilmesi yerine yöntemi geçen argüman tipiyle tanımlanan genel yöntemin nasıl tip argümanı olduğunun sonucudur. Çıkarımı etkinleştirmek için bir genel yöntem parametre imzası yöntem türü parametresi gibi aynı türde bir parametre içermelidir. Bu durumda, tip bağımsız değişkeninin belirtilmesine gerek yoktur. Tüm tip parametreleri için çıkarım kullandığınızda jenerik ve jenerik olmayan örnek yöntemleri için sözdizimi aynıdır; Bu kullanılabilirlik genel yöntemlerin kullanımını kolaylaştırır.|  
|[CA1005: Genel türlerde aşırı parametrelerden kaçının](../code-quality/ca1005-avoid-excessive-parameters-on-generic-types.md)|Daha çok tip parametresi, genel tip içerir, bilmek daha zordur ve hangi tip parametrelerinin temsil ettiğini anımsamak zordur. Bu genellikle listesi olduğu gibi tek tip parametre ile açıktır\<T > ve sözlük gibi iki tür parametreleri ile belirli durumlarda\<TKey, TValue >. Ancak, iki parametreden fazla parametre varsa, birçok kullanıcı için zorluk derecesi artar.|  
|[CA1006: Üye imzalarında genel türleri iç içe kullanmayın](../code-quality/ca1006-do-not-nest-generic-types-in-member-signatures.md)|Bir yuvalanmış bağımsız değişken aynı zamanda genel tip olan bir tip bağımsız değişkendir. Yuvalanmış tip bağımsız değişkeni içeren imzası olan bir üye çağırmak için, kullanıcı bir genel tipi örneklemeli ve bu tipi ikinci bir genel tipin yapıcısına geçirmelidir. Gerekli yordam ve sözdizimi karmaşıktır ve kaçınılmalıdır.|  
|[CA1007: Uygun yerlerde genel türler kullanın](../code-quality/ca1007-use-generics-where-appropriate.md)|System.Object türünde bir başvuru parametresi dışarıdan görünen bir yöntem içerir. Bir genel yöntem kullanımı başvuru parametresi türünü ilk tür olarak atmadan yönteme aktarılan kısıtlamalar için tüm türleri ve konuları etkinleştirir.|  
|[CA1008: Numaralandırmalar sıfır değerine sahip olmalıdır](../code-quality/ca1008-enums-should-have-zero-value.md)|Tıpkı diğer türler gibi, başlatılmamış bir numaralandırmanın varsayılan değeri sıfırdır. Öznitelikli nonflags numaralandırması, böylece varsayılan değer geçerli bir numaralandırma değeri sıfır değerini kullanarak bir üye tanımlamanız gerekir. Numaralandırma FlagsAttribute özniteliği sıfır değerli üyeyi tanımlarsa, onun adı numaralandırmada hiçbir değerin ayarlanmadığı "Hiçbiri" olmalıdır.|  
|[CA1009: Olay işleyicilerini doğru bildirin](../code-quality/ca1009-declare-event-handlers-correctly.md)|Olay işleyicisi yöntemleri iki parametre alır. İlk System.Object türündedir ve "gönderen" olarak adlandırılır. Bu olayda oluşan nesnedir. İkinci parametre System.EventArgs türüdür ve "e" olarak adlandırılır. Bu olay ile ilişkilendirilmiş olan verilerdir. Olay işleyici yöntemlerine bir değer döndürmemelidir; C# programlama diliyle, dönüş türü boşluk tarafından belirtilir.|  
|[CA1010: Koleksiyonlar genel arabirim uygulamalıdır](../code-quality/ca1010-collections-should-implement-generic-interface.md)|Bir koleksiyon kullanılabilirliğini genişletmek için genel koleksiyon arabirimlerinden birini uygulayın. Daha sonra koleksiyon genel koleksiyon türlerini doldurmak için kullanılabilir.|  
|[CA1011: Temel türleri parametre olarak geçirmeyi düşünün](../code-quality/ca1011-consider-passing-base-types-as-parameters.md)|Temel tür yöntem bildiriminde parametre olarak belirtildiğinde temel türünden türetilen herhangi bir tür yöntemine karşılık gelen bağımsız değişken olarak geçirilebilir. Türetilmiş parametre türü tarafından sağlanan ek işlevler gerekmiyorsa, temel tür kullanımı yöntemi daha geniş kullanımını etkinleştirir.|  
|[CA1012: Soyut türlerde oluşturucular bulunmamalıdır](../code-quality/ca1012-abstract-types-should-not-have-constructors.md)|Soyut türler üzerindeki kurucular yalnızca türetilen türler tarafından çağrılabilir. Ortak yapıcılar türün bir örneğini yaptığından ve siz bir soyut türün örneğini yapamayacağınızdan, soyut sınıf hatalı biçimde dizayn edilmiş ortak yapıcıya sahip olur.|  
|[CA1013: Eşittir işlecini ekleme ve çıkarmayı aşırı yükleyerek aşırı yükleyin](../code-quality/ca1013-overload-operator-equals-on-overloading-add-and-subtract.md)|Bir genel ya da korumalı tür eşitlik imlecini uygulamadan ekleme ya da çıkarma işleçlerini uygular.|  
|[CA1014: Derlemeleri CLSCompliantAttribute ile işaretleyin](../code-quality/ca1014-mark-assemblies-with-clscompliantattribute.md)|Ortak Dil Tanımlaması (CLS) ad kısıtlamalarını, veri türlerini ve karşıt programlama dillerini kullanırsa derlemelerin uyması zorunlu olan kuralları tanımlar. İyi tasarım derlemelerin açıkça CLS uyumluluğu CLSCompliantAttribute kullanarak göstermesini belirler. Bu öznitelik bir derlemede yoksa, montaj uyumlu değildir.|  
|[CA1016: Derlemeleri AssemblyVersionAttribute ile işaretleyin](../code-quality/ca1016-mark-assemblies-with-assemblyversionattribute.md)|.NET Framework sürüm numarasını derlemeyi benzersiz tanımlamada ve türleri güçlü derlemelere bağlamak için kullanır. Sürüm numarası, sürüm ve yayımcı ilkesi ile birlikte kullanılır. Varsayılan olarak uygulamalar yalnızca oluşturulmuş derleme sürümlerini çalıştırır.|  
|[CA1017: Derlemeleri ComVisibleAttribute ile işaretleyin](../code-quality/ca1017-mark-assemblies-with-comvisibleattribute.md)|ComVisibleAttribute COM müşterilerinin yönetilen koda nasıl erişeceğini tanımlar. İyi tasarım derlemelerin açıkça COM görünürlüğünde gösterildiğini belirler. COM görünürlüğü tüm derleme için ayarlanabilir ve sonra bireysel tür ve tür üyeleri için geçersiz kılınabilir. Bu öznitelik yoksa, derleme içeriği COM istemcileri tarafından görülebilir.|  
|[CA1018: Öznitelikleri AttributeUsageAttribute ile işaretleyin](../code-quality/ca1018-mark-attributes-with-attributeusageattribute.md)|Özel öznitelik tanımladığınızda, AttributeUsageAttribute kullanarak özel öznitelik kaynak kodunun nerede uygulanabilir olduğunu göstermek için işaretleyin. Bir özniteliğin anlamı ve amaçlanan kullanımı, kodun içinde onun varolan konumunu tanımlar.|  
|[CA1019: Öznitelik bağımsız değişkenleri için erişimcileri tanımlayın](../code-quality/ca1019-define-accessors-for-attribute-arguments.md)|Öznitelikler özniteliği işaretlediğinizde özelleştirilen zorunlu bağımsız değişkenleri tanımlayabilir. Ayrıca bunlar konum parametreleri olarak öznitelik yapıcısına verildiğinden duruma bağlı bağımsız değişkenler olarak da bilinirler. Zorunlu her bağımsız değişken için bağımsız değişkenin değeri yürütme zamanından alınması gerektiğinden öznitelik ilgili salt okunur özelliği de sağlamalıdır. Öznitelikler adlandırılmış bağımsız değişkenler olarak bilinen duruma bağlı bağımsız değişkenler olarak da tanımlanabilir. Bu bağımsız öznitelik oluşturucular ad tarafından sağlanır ve karşılık gelen bir okuma/yazma özelliğine sahip olmalıdır.|  
|[CA1020: Birkaç türü olan ad alanlarından kaçının](../code-quality/ca1020-avoid-namespaces-with-few-types.md)|Her ad alanlarınıza mantıksal düzenlemesi vardır ve seyrek doldurulmuş bir ad alanına türleri koymak için geçerli bir nedeniniz olduğundan emin olun.|  
|[CA1021: Out parametrelerinden kaçının](../code-quality/ca1021-avoid-out-parameters.md)|Başvuruya ( out veya ref kullanarak ) göre türleri geçirmek işaretçi deneyimi gerektirir, değer türü ve referans türü arasındaki farkı ve işleme yöntemi ile birden çok değer döndürmeyi anlamak gerekir. Ayrıca, out ve ref parametreleri arasındaki fark açıkça anlaşılmadı.|  
|[CA1023: Dizin oluşturucular çok boyutlu olmamalıdır](../code-quality/ca1023-indexers-should-not-be-multidimensional.md)|Dizin oluşturucular (dizinlenmiş özellikleri) tek bir dizin kullanmalı. Çok boyutlu dizin oluşturucular kitaplığın kullanılabilirliğini önemli ölçüde azaltabilir.|  
|[CA1024: Uygun yerlerde özellikler kullanın](../code-quality/ca1024-use-properties-where-appropriate.md)|Ortak veya korumalı yöntem "Get" ile başlar, herhangi bir parametre almaz ve dizi olmayan bir değer döndüren adı vardır. Yöntem, özellik olmak için çok iyi bir aday olabilir.|  
|[CA1025: Tekrarlanan bağımsız değişkenleri params dizisi ile değiştirin](../code-quality/ca1025-replace-repetitive-arguments-with-params-array.md)|Parametre dizisini bağımsız değişkenin gerçek sayısı bilinmediğinde ve bağımsız değişkenler aynı türde olduğunda ya da aynı tür olarak geçirilebileceğinde bağımsız değişkenleri tekrarlamak için kullanın.|  
|[CA1026: Varsayılan parametreler kullanılmamalıdır](../code-quality/ca1026-default-parameters-should-not-be-used.md)|Varsayılan parametreleri kullanma yöntemleri CLS altında izin verilir; ancak, CLS derleyicileri bu parametreler için atanmış değerleri gözardı etmeye olanak sağlar. Programlama dilleri arasında istediğiniz davranışı korumak için varsayılan parametreleri kullanan yöntemler varsayılan parametreleri sağlayan tekrar yüklenen yöntem tarafından değiştirilmelidir.|  
|[CA1027: Numaralandırmaları FlagsAttribute ile işaretleyin](../code-quality/ca1027-mark-enums-with-flagsattribute.md)|Bir numaralandırma ilişkili adlandırılmış sabitler kümesini tanımlayan değer türüdür. Anlamsız olarak birleştirildiğinde numaralandırmaya FlagsAttribute özelliğini uygulayın.|  
|[CA1028: Numaralandırma depolaması Int32 olmalıdır](../code-quality/ca1028-enum-storage-should-be-int32.md)|Bir numaralandırma ilişkili adlandırılmış sabitler kümesini tanımlayan değer türüdür. Varsayılan olarak, System.Int32 veri türü sabit değerleri depolamak için kullanılır. Bu temel türünü değiştirebilirsiniz, ancak bu gerekmez veya önerilen bir senaryo.|  
|[CA1030: Uygun yerlerde olaylar kullanın](../code-quality/ca1030-use-events-where-appropriate.md)|Bu kural, normalde olaylar için kullanılan adlara sahip yöntemleri algılar. Yanıt olarak açıkça tanımlanmış bir durum değişikliği yöntemi çağrılırsa, olay işleyicisi tarafından yöntemin çağrılması gerekir. Yöntemi direkt olarak çağırmak yerine olayları yükselterek çağıran nesneler.|  
|[CA1031: Genel özel durum türlerini yakalamayın](../code-quality/ca1031-do-not-catch-general-exception-types.md)|Genel özel durum yakalanmamalı. Daha özel istisnaları yakalayın ya da yakalama bloğundaki son deyim olarak genel özel durumu yeniden.|  
|[CA1032: Standart özel durum oluşturucuları uygulayın](../code-quality/ca1032-implement-standard-exception-constructors.md)|Yapıcıların tüm ayarlamasını sağlamaktaki başarısızlık, istisnalarla başa çıkmayı zorlaştırabilir.|  
|[CA1033: Arabirim yöntemleri alt türler tarafından çağırılabilir olmalıdır](../code-quality/ca1033-interface-methods-should-be-callable-by-child-types.md)|Ağzı açık dışarıdan görünen bir tür açık yöntem uygulaması ortak bir arabirim sağlar ve aynı ada sahip alternatif dışarıdan görünen bir yöntem sağlamaz.|  
|[CA1034: İç içe türler görünebilir olmamalıdır](../code-quality/ca1034-nested-types-should-not-be-visible.md)|İç içe türü başka bir kapsamda bildirilen bir türdür. İç içe geçmiş türler, özel uygulama ayrıntılarını kapsayan türdeki kapsül oluşturma için kullanışlıdır. Bu amaçla kullanılan, iç içe türün dışarıdan görünür olmaması gerekir.|  
|[CA1035: ICollection uygulamalarında türü kesin olarak belirtilmiş üyeler olmalıdır](../code-quality/ca1035-icollection-implementations-have-strongly-typed-members.md)|Bu kural ICollection uygulamalarına türü kesin belirlenmiş üyeler sağlamak için gereklidir, böylece kullanıcıların arabirim tarafından sağlanan işlevselliği kullandığı zaman, bağımsız değişkenleri Nesne türüne atamaları gerekli değildir. Bu kural, Nesneden daha güçlü tür örnekleri topluluğunu yöneteceğinden türün ICollection uyguladığını varsayar.|  
|[CA1036: Karşılaştırılabilir türlerde geçersiz kılma yöntemleri](../code-quality/ca1036-override-methods-on-comparable-types.md)|Ortak veya korumalı tür System.IComparable arabirimini uygular. Object.Equals ne etkisiz kılınabilir ne de eşitlik için olan özel dil işleciyle aşırı yüklenebilir, eşitsizlik durumu olabilir, daha küçülebilir ya da büyüyebilir.|  
|[CA1038: Numaralandırıcıların türü kesin olarak belirtilmelidir](../code-quality/ca1038-enumerators-should-be-strongly-typed.md)|Bu kural, kullanıcı arabirimi tarafından sağlanan işlevselliği kullandığınızda güçlü tür için dönen değer atama yapmak için gerekli değildir, ayrıca süregelen özelliğinin türü kesin belirlenmiş bir sürümünü sağlamak için IEnumerator uygulamaları gereklidir.|  
|[CA1039: Listelerin türü kesin olarak belirlenmiştir](../code-quality/ca1039-lists-are-strongly-typed.md)|Bu kural türü kesin belirlenmiş üyeler sağlamak için IList uygulamaları gerektirir böylece kullanıcıların arabirim tarafından sağlanan işlevselliği kullandığı zaman, bağımsız değişkenleri System.Object türüne atamaları gerekli değildir.|  
|[CA1040: Boş arabirimlerden kaçının](../code-quality/ca1040-avoid-empty-interfaces.md)|Arayüzler bir davranış veya kullanım sözleşmesi sağlayan üyeleri tanımlar. Arabirim tarafından tanımlanan fonksiyonellik herhangi bir tür tarafından türün kalıtım hiyerarşisinde nerede belirdiği önemsenmeksizin devralınabilir. Tür arabirimin üyeleri için uygulamaları sağlayarak bir arayüz uygular. Boş bir arabirim herhangi bir üye tanımlamıyor; bu nedenle, uygulanabilir bir sözleşme tanımlamaz.|  
|[CA1041: ObsoleteAttribute iletisi sağlayın](../code-quality/ca1041-provide-obsoleteattribute-message.md)|Tür veya üye belirtilen kendi ObsoleteAttribute.Message özelliğine sahip olmayan bir System.ObsoleteAttribute özniteliği kullanılarak işaretlendi. Bir türü veya ObsoleteAttribute kullanılarak işaretlenmiş üye derlendiğinde, eski türü veya üye kullanıcı bilgilerini sağlayan özniteliğin ileti özelliği görüntülenir.|  
|[CA1043: Dizin oluşturucular için tamsayı veya dize bağımsız değişkeni kullanın](../code-quality/ca1043-use-integral-or-string-argument-for-indexers.md)|Dizinle oluşturucular (dizinlenmiş özellikleri) dizin için integral veya dize türleri kullanılmalıdır. Bu türler, genellikle veri yapılarını dizinleme için kullanılır ve bunlar kitaplığın kullanılabilirliğini artırır. Nesne türünün kullanılması için belirli bir integral veya dize türü tasarım zamanında burada tarif edilemez, bu gibi durumlarda sınırlı tutulmalıdır.|  
|[CA1044: Özellikler salt yazılır olmamalıdır](../code-quality/ca1044-properties-should-not-be-write-only.md)|Salt okunur özelliğe sahip olmasına karşın kabul edilebilir ve genellikle gereklidir, tasarıma ilişkin yönergeler salt yazılır özellik kullanılmasını engeller. Bir kullanıcı değeri ayarlar ve sonra kullanıcı bu değeri görüntülemeyi engellerse bunun için herhangi bir güvenlik yoktur. Ayrıca, okuma erişimi olmadan, yararsız olduklarını sınırlayan paylaşılan nesnelerin durumu görüntülenemez.|  
|[CA1045: Türleri başvuruya göre geçirmeyin](../code-quality/ca1045-do-not-pass-types-by-reference.md)|Başvuruya ( out veya ref kullanarak ) göre türleri geçirmek işaretçi deneyimi gerektirir, değer türü ve referans türü arasındaki farkı ve işleme yöntemi ile birden çok değer döndürmeyi anlamak gerekir. Genel kitle için tasarlayan kütüphane mimarları, kullanıcılardan out ya da ref parametrelerini asıl düzeyde kullanmalarını beklememelidir.|  
|[CA1046: Başvuru türlerinde eşittir işleçlerini aşırı yüklemeyin](../code-quality/ca1046-do-not-overload-operator-equals-on-reference-types.md)|Başvuru türleri için, varsayılan eşitlik işleci neredeyse her zaman doğrudur. Varsayılan olarak, yalnızca aynı nesneye gelirseniz iki başvuru eşit olur.|  
|[CA1047: Korumalı türlerde korunan üyeleri bildirmeyin](../code-quality/ca1047-do-not-declare-protected-members-in-sealed-types.md)|Türler, devralmasına erişebileceğiniz veya üyeyi geçersiz kılmak için korunan üyelerin türlerini bildirir. Tanım gereği, mühürlenmiş türler devralınamaz yani mühürlenmiş türler üzerindeki korunan yöntemler çağrılamaz.|  
|[CA1048: Korumalı türlerde sanal üyeleri bildirmeyin](../code-quality/ca1048-do-not-declare-virtual-members-in-sealed-types.md)|Türler yöntemi sanal olarak bildirir, böylece devralan türler sanal yöntemin uygulanmasını geçersiz kılabilir. Tanım gereği, mühürlenmiş bir tür devralınamaz. Bu, sanal yöntemi mühürlenmiş bir türde anlamsız hale getirir.|  
|[CA1049: Yerel kaynaklara sahip olan türler atılabilir olmalıdır](../code-quality/ca1049-types-that-own-native-resources-should-be-disposable.md)|Yönetilmeyen kaynakların tahsis türlerini arayanların isteğine bağlı kaynakları serbest bırakmak ve kaynakları tutan nesnelerin yaşam sürelerini kısaltmak için etkinleştirmek üzere IDisposable gerçekleştirmelisiniz.|  
|[CA1050: Ad alanlarında türleri bildirin](../code-quality/ca1050-declare-types-in-namespaces.md)|Türlerin ad çakışmalarını önlemek için ad alanlarını ve ilgili türü bir nesne sıradüzeni içinde düzenlemeniz için yöntem olarak bildirilir.|  
|[CA1051: Görünür örnek alanlarını bildirmeyin](../code-quality/ca1051-do-not-declare-visible-instance-fields.md)|Bir alanın birincil kullanım alanının uygulama ayrıntısı olması gerekir. Alanların özel veya iç olması gerekir ve özelliklerini kullanmaya maruz kalması gerekir.|  
|[CA1052: Statik tutucu türleri mühürlenmelidir](../code-quality/ca1052-static-holder-types-should-be-sealed.md)|Ortak veya korumalı tür yalnızca statik üyeleri içerir ve mühürlenmiş (C#) veya NotInheritable (Visual Basic) değiştirici kullanarak bildirilmedi. Devralınmayacak anlamına gelen tür mühürleme değiştirici kullanılarak basit tür gibi kullanılmak için işaretlenmelidir.|  
|[CA1053: Statik tutucu türlerinde oluşturucular bulunmamalıdır](../code-quality/ca1053-static-holder-types-should-not-have-constructors.md)|Ortak veya iç içe geçmiş ortak tür yalnızca statik üyeleri bildirir ve ortak veya korumalı varsayılan bir oluşturucu vardır. Statik üyeleri çağırma bir tür örneği gerektirmediğinden kurucu gereksizdir. Dize aşırı yüklemesi, emniyet ve güvenlik için dize bağımsız değişkeni kullanılarak tekdüzen kaynak tanımlayıcısı (URI) çağırmalıdır.|  
|[CA1054: URI parametreleri dizeler olmamalıdır](../code-quality/ca1054-uri-parameters-should-not-be-strings.md)|Bir yöntem URI'yı sunan bir dizeyi alırsa, bu hizmetleri sağlayan güvenli şekilde URI sınıfının bir örneğini alır, karşılık gelen aşırı olmalıdır.|  
|[CA1055: URI dönüş değerleri dizeler olmamalıdır](../code-quality/ca1055-uri-return-values-should-not-be-strings.md)|Bu kural, yöntemin URI döndürdüğünü varsayar. Bir URI'nın dize sunumu ayrıştırma ve hataları kodlama eğilimindedir ve güvenlik açıklarına yol açabilir. System.Uri sınıfı bu hizmetleri güvenli bir şekilde sağlar.|  
|[CA1056: URI özellikleri dize olmamalıdır](../code-quality/ca1056-uri-properties-should-not-be-strings.md)|Bu kural, özelliği bir URI temsil ettiğini varsayar. Bir URI'nın dize sunumu ayrıştırma ve hataları kodlama eğilimindedir ve güvenlik açıklarına yol açabilir. System.Uri sınıfı bu hizmetleri güvenli bir şekilde sağlar.|  
|[CA1057: Dize URI aşırı yüklemeleri System.Uri aşırı yüklemelerini çağırır](../code-quality/ca1057-string-uri-overloads-call-system-uri-overloads.md)|Bir tür sadece System.Uri parametresi ile dize parametresinin değiştirilmesiyle yöntem aşırı yüklemesini bildirir. Aşırı yüklemeler URI parametresiyle aşırı yüklenmiş olan dize parametresini alır.|  
|[CA1058: Türler belli temel türleri genişletmemelidir](../code-quality/ca1058-types-should-not-extend-certain-base-types.md)|Dışarıdan görünen tür belirli temel türleri genişletir. Diğer seçenekleri kullanın.|  
|[CA1059: Üyeler belli somut türleri göstermemelidir](../code-quality/ca1059-members-should-not-expose-certain-concrete-types.md)|Somut tür tam bir uygulamaya sahiptir ve bu nedenle oluşturulabilecek bir türdür. Üye yaygın kullanımını etkinleştirmek için önerilen arabirimi kullanarak somut türünü değiştirin.|  
|[CA1060: Taşıma P/Invokes öğesini NativeMethods sınıfına](../code-quality/ca1060-move-p-invokes-to-nativemethods-class.md)|Platform çağırma yöntemleri ile işaretlenenler gibi <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName> veya Declare anahtar sözcüğü kullanılarak tanımlanan yöntemleri [!INCLUDE[vbprvb](../includes/vbprvb-md.md)], yönetilmeyen koda erişebilirsiniz. Bu yöntemler, NativeMethods, SafeNativeMethods veya UnsafeNativeMethods sınıfının üyesi olmalıdır.|  
|[CA1061: Taban sınıf yöntemlerini gizlemeyin](../code-quality/ca1061-do-not-hide-base-class-methods.md)|Basit türdeki bir yöntem türetilmiş türdeki adlandırılmış yöntem tarafından gizlenmiştir, türetilmiş yöntemin parametre imzası yalnızca türetilmiş türleri ve karşılık gelen temel yöntemin parametre imzası daha zayıf türlerine göre farklı olduğunda temel türde bir yöntemin türetilmiş türle aynı adlı yöntem olarak gizlidir.|  
|[CA1062: Genel yöntemlerin bağımsız değişkenlerini doğrulayın](../code-quality/ca1062-validate-arguments-of-public-methods.md)|Dışarıdan görünen yöntemlerin null'a karşı denetlenmesi için geçirilen tüm başvuru bağımsız değişkenleri.|  
|[CA1063: IDisposable'ı doğru uygulayın](../code-quality/ca1063-implement-idisposable-correctly.md)|Tüm IDisposable türleri Dispose kalıbını doğru uygulamalıdır.|  
|[CA1064: Özel durumlar genel olmamalıdır](../code-quality/ca1064-exceptions-should-be-public.md)|Bir iç özel durum yalnızca kendi iç kapsamı içinde görülebilir. İç kapsam dışında kalan özel durumlardan sonra, sadece basit istisnalar istisna yakalamak için kullanılabilir. İç özel durum öğesinden devralınan <xref:System.Exception?displayProperty=fullName>, <xref:System.SystemException?displayProperty=fullName>, veya <xref:System.ApplicationException?displayProperty=fullName>, harici kod özel durum ne olduğunu bilmek yeterli bilgiye sahip değildir.|  
|[CA1065: Beklenmedik konumlarda özel durumlar tetiklemeyin](../code-quality/ca1065-do-not-raise-exceptions-in-unexpected-locations.md)|İstisna atılmasını beklemeyen yöntem bir istisna atar.|  
|[CA2210: Derlemelerin tanımlayıcı adı geçerli olmalıdır](../code-quality/ca2210-assemblies-should-have-valid-strong-names.md)|Güçlü ad oynanmış derlemeyi bilmeden yükleyerek istemcileri korur. Güçlü adı olmayan derlemeler oldukça sınırlı sayıda senaryo dışında kullanılmamalıdır. Düzgün imzalanmamış derlemeleri paylaşırsanız veya dağıtırsanız, derleme aslı bozuabilir, ortak dil çalışma zamanı derlemeyi yükleyemeyebilir veya kullanıcı kendi bilgisayarındaki doğrulamayı devre dışı bırakabilir.|


