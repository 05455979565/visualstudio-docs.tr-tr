---
title: Intellitest Başvuru Kılavuzu | Microsoft Geliştirici Test Araçları
ms.date: 05/02/2017
ms.topic: conceptual
helpviewer_keywords:
  - 'IntelliTest Reference Manual, IntelliTest'
ms.author: gewarren
manager: jillfra
ms.workload:
  - multiple
author: gewarren
---
# <a name="intellitest-reference-manual"></a>Intellitest Başvuru Kılavuzu

## <a name="contents"></a>İçindekiler

* **[Intellitest genel bakış](introduction.md)**
  - [Intellitest, Merhaba Dünya](introduction.md#the-hello-world-of-intellitest)
  - [Sınırlamalar](introduction.md#limitations)
    * [Nondeterminism](introduction.md#nondeterminism)
    * [Eşzamanlılık](introduction.md#concurrency)
    * [Yerel kod](introduction.md#native-code)
    * [Platform](introduction.md#platform)
    * [Dil](introduction.md#language)
    * [Sembolik akıl yürütme](introduction.md#symbolic-reasoning)
    * [Yanlış Yığın izlemeleri](introduction.md#incorrect-stack-traces)
  - [Daha fazla bilgi](introduction.md#further-reading)

* **[Intellitest ile çalışmaya başlama](getting-started.md)**
  - [Önemli öznitelikleri](getting-started.md#important-attributes)
  - [Önemli statik yardımcı sınıfları](getting-started.md#helper-classes)

* **[Test oluşturma](test-generation.md)**
  - [Test oluşturucuları](test-generation.md#test-generators)
  - [Parametreli birim testi](test-generation.md#parameterized-unit-testing)
  - [Genel parametreli birim testi](test-generation.md#generic-parameterized)
  - [Özel durumlara izin vermek](test-generation.md#allowing-exceptions)
  - [İç test türleri](test-generation.md#internal-types)
  - [Varsayımlar ve onaylar](test-generation.md#assumptions-and-assertions)
  - [Önkoşulu](test-generation.md#precondition)
  - [Sonkoşul](test-generation.md#postcondition)
  - [Test hataları](test-generation.md#test-failures)
  - [Kurulum ve kapatabilirsiniz](test-generation.md#setup-teardown)
  - [Daha fazla bilgi](test-generation.md#further-reading)

* **[Giriş oluşturma](input-generation.md)**
  - [Kısıtlama Çözücü](input-generation.md#constraint-solver)
  - [Dinamik kod kapsamı](input-generation.md#dynamic-code-coverage)
  - [Tamsayıları ve float](input-generation.md#integers-and-floats)
  - [Nesneler](input-generation.md#objects)
  - [Varolan bir sınıf oluşturma](input-generation.md#existing-classes)
  - [Görünürlük](input-generation.md#visibility)
  - [Parametreli mocks](input-generation.md#parameterized-mocks)
  - [Yapılar](input-generation.md#structs)
  - [Diziler ve dizeler](input-generation.md#arrays-and-strings)
  - [Ek girişler alma](input-generation.md#additional-inputs)
  - [Daha fazla bilgi](input-generation.md#further-reading)

* **[Keşif sınırları](exploration-bounds.md)**
  - [MaxConstraintSolverTime](exploration-bounds.md#maxconstraintsolvertime)
  - [MaxConstraintSolverMemory](exploration-bounds.md#maxconstraintsolvermemory)
  - [MaxBranches](exploration-bounds.md#maxbranches)
  - [MaxCalls](exploration-bounds.md#maxcalls)
  - [MaxStack](exploration-bounds.md#maxstack)
  - [MaxConditions](exploration-bounds.md#maxconditions)
  - [MaxRuns](exploration-bounds.md#maxruns)
  - [MaxRunsWithoutNewTests](exploration-bounds.md#maxrunswithoutnewtests)
  - [MaxRunsWithUniquePaths](exploration-bounds.md#maxrunswithuniquepaths)
  - [Maxexceptions yapılandırma](exploration-bounds.md#maxexceptions)
  - [TestExcludePathBoundsExceeded](exploration-bounds.md#testexcludepathboundsexceeded)
  - [TestEmissionFilter](exploration-bounds.md#testemissionfilter)
  - [TestEmissionBranchHits](exploration-bounds.md#testemissionbranchhits)

* **[Öznitelik sözlüğü](attribute-glossary.md)**
  - [PexAssumeNotNull](attribute-glossary.md#pexassumenotnull)
  - [PexClass](attribute-glossary.md#pexclass)
  - [PexGenericArguments](attribute-glossary.md#pexgenericarguments)
  - [PexMethod](attribute-glossary.md#pexmethod)
  - [PexExplorationAttributeBase](attribute-glossary.md#pexexplorationattributebase)
  - [PexAssemblySettings](attribute-glossary.md#pexassemblysettings)
  - [PexAssemblyUnderTest](attribute-glossary.md#pexassemblyundertest)
  - [PexInstrumentAssemblyAttribute](attribute-glossary.md#pexinstrumentassemblyattribute)
  - [PexUseType](attribute-glossary.md#pexusetype)
  - [PexAllowedException](attribute-glossary.md#pexallowedexception)
  - [PexAllowedExceptionFromAssembly](attribute-glossary.md#pexallowedexceptionfromassembly)
  - [PexAllowedExceptionFromType](attribute-glossary.md#pexallowedexceptionfromtype)
  - [PexAllowedExceptionFromTypeUnderTest](attribute-glossary.md#pexallowedexceptionfromtypeundertest)

* **[Ayarlar Şelalesi](settings-waterfall.md)**

* **[Statik yardımcı sınıfları](static-helper-classes.md)**
  - [PexAssume](static-helper-classes.md#pexassume)
  - [PexAssert](static-helper-classes.md#pexassert)
  - [PexChoose](static-helper-classes.md#pexchoose)
  - [PexObserve](static-helper-classes.md#pexobserve)
  - [PexSymbolicValue](static-helper-classes.md#pexsymbolicvalue)

* **[Uyarıları ve hataları](warnings-and-errors.md)**
  - [MaxBranches aşıldı](warnings-and-errors.md#maxbranches-exceeded)
  - [MaxConstraintSolverTime aşıldı](warnings-and-errors.md#maxconstraintsolvertime-exceeded)
  - [MaxConditions aşıldı](warnings-and-errors.md#maxconditions-exceeded)
  - [MaxCalls aşıldı](warnings-and-errors.md#maxcalls-exceeded)
  - [MaxStack aşıldı](warnings-and-errors.md#maxstack-exceeded)
  - [MaxRuns aşıldı](warnings-and-errors.md#maxruns-exceeded)
  - [MaxRunsWithoutNewTests aşıldı](warnings-and-errors.md#maxrunswithoutnewtests-exceeded)
  - [Çözüm somutlaştırılamıyor](warnings-and-errors.md#cannot-concretize-solution)
  - [Nesnesi oluşturmak için Yardım gerekiyor](warnings-and-errors.md#help-construct)
  - [Türleri bulmak için Yardım gerekiyor](warnings-and-errors.md#help-types)
  - [Tahmin kullanılabilir türü](warnings-and-errors.md#usable-type-guessed)
  - [Araştırma sırasında beklenmeyen hata](warnings-and-errors.md#unexpected-exploration)
  - [TargetInvocationException](warnings-and-errors.md#targetinvocationexception)
  - [İzlemesiz yöntemi çağrılır](warnings-and-errors.md#uninstrumented-method-called)
  - [Adlı dış yöntemi](warnings-and-errors.md#external-method-called)
  - [Adlı izlenemeyen yöntemi](warnings-and-errors.md#uninstrumentable-method-called)
  - [Test Edilebilirlik sorununu](warnings-and-errors.md#testability-issue)
  - [Sınırlama](warnings-and-errors.md#limitation)
  - [Çağrı uyuşmazlığı gözlemlendi](warnings-and-errors.md#observed-call-mismatch)
  - [Statik alanda depolanan değer](warnings-and-errors.md#value-static-field)

## <a name="got-feedback"></a>Geri bildirim var mı?

Fikirlerinizi gönderin ve özellik istekleri [Geliştirici topluluğu](https://developercommunity.visualstudio.com/content/idea/post.html?space=8).