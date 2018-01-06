---
title: "İzlenecek yol: özel yönerge işlemcisi oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- text templates, custom directive processors
- walkthroughs [text templates], directive processor
ms.assetid: b8f35a36-14e1-4467-8f5f-e01402af14d5
caps.latest.revision: "74"
author: alancameronwills
ms.author: awills
manager: douge
ms.workload: multiple
ms.openlocfilehash: 0eb95bdd83780aa000ea6e3c696c24e319dcd4fa
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-creating-a-custom-directive-processor"></a>İzlenecek yol: Özel Yönerge İşlemcisi Oluşturma
*Yönerge işlemcileri* kodu ekleyerek iş *dönüştürme sınıfı oluşturulan*. Çağırırsanız bir *yönergesi* gelen bir *metin şablonu*, rest, metin şablonu yazma kod yönergesi sağlayan işlevselliğini güvenebilirsiniz.  
  
 Kendi özel yönerge işlemcilerinizi yazabilirsiniz. Bu metin şablonlarınızı özelleştirmenize olanak sağlar. Özel yönerge işlemcisi oluşturmak için herhangi birinden devralan bir sınıf oluşturun. <xref:Microsoft.VisualStudio.TextTemplating.DirectiveProcessor> veya <xref:Microsoft.VisualStudio.TextTemplating.RequiresProvidesDirectiveProcessor>.  
  
 Bu kılavuzda gösterilen görevler aşağıdakileri içerir:  
  
-   Özel yönerge işlemcisi oluşturma  
  
-   Yönerge işlemcisini kaydetme  
  
-   Yönerge işlemcisini test etme  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu kılavuzu tamamlamak için şunlara ihtiyacınız olacak:  
  
-   Visual Studio 2010  
  
-   Visual Studio 2010 SDK  
  
## <a name="creating-a-custom-directive-processor"></a>Özel Yönerge İşlemcisi Oluşturma  
 Bu kılavuzda, özel bir yönerge işlemcisi oluşturursunuz. Bir XML dosyasını okur, depolar özel bir yönerge eklediğiniz bir <xref:System.Xml.XmlDocument> , değişken ve bir özelliği üzerinden kullanıma sunar. "Yönerge İşlemcisini Test Etme" bölümünde, XML dosyasına erişmek için metin şablonunda bu özelliği kullanırsınız.  
  
 Özel yönergenize yaptığınız çağrı aşağıdaki gibi görünür:  
  
 `<#@ CoolDirective Processor="CustomDirectiveProcessor" FileName="<Your Path>DocFile.xml" #>`  
  
 Özel yönerge işlemcisi, değişkeni ve özelliği oluşturulan dönüştürme sınıfına ekler. Kullandığı yazma yönergesi <xref:System.CodeDom> altyapısı için oluşturulan dönüşüm sınıfı ekler kodu oluşturmak için sınıflar. <xref:System.CodeDom> Sınıfları kod oluşturmak ya da Visual C# dilinde veya [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]belirtilen dilde bağlı olarak `language` parametresinin `template` yönergesi. Yönerge işlemcisinin dili ve yönerge işlemcisine erişen metin şablonunun dilinin eşleşmesi gerekmez.  
  
 Yönergenin oluşturduğu kod aşağıdaki gibi görünür:  
  
```csharp  
private System.Xml.XmlDocument document0Value;  
  
public virtual System.Xml.XmlDocument Document0  
{  
  get  
  {  
    if ((this.document0Value == null))  
    {  
      this.document0Value = XmlReaderHelper.ReadXml(<FileNameParameterValue>);  
    }  
    return this.document0Value;  
  }  
}  
```  
  
```vb  
Private document0Value As System.Xml.XmlDocument  
  
Public Overridable ReadOnly Property Document0() As System.Xml.XmlDocument  
    Get  
        If (Me.document0Value Is Nothing) Then  
            Me.document0Value = XmlReaderHelper.ReadXml(<FileNameParameterValue>)  
        End If  
        Return Me.document0Value  
    End Get  
End Property  
```  
  
#### <a name="to-create-a-custom-directive-processor"></a>Özel yönerge işlemcisi oluşturmak için  
  
1.  Visual Studio'da, CustomDP adlı bir C# veya Visual Basic kitaplık projesi oluşturun.  
  
    > [!NOTE]
    >  Yönerge işlemcisi birden fazla bilgisayara yüklemek istiyorsanız, kullanmak en iyisidir bir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] uzantısı (VSIX) proje ve .pkgdef dosya uzantısına dahil etme. Daha fazla bilgi için bkz: [özel yönerge işlemcisi dağıtma](../modeling/deploying-a-custom-directive-processor.md).  
  
2.  Aşağıdaki derlemelere başvurular ekleyin:  
  
    -   **Microsoft.VisualStudio.TextTemplating. \*.0**  
  
    -   **Microsoft.VisualStudio.TextTemplating.Interfaces. \*.0**  
  
3.  Kodla **Class1** aşağıdaki kod ile. Bu kod devraldığı CustomDirectiveProcessor sınıfı tanımlar <xref:Microsoft.VisualStudio.TextTemplating.DirectiveProcessor> sınıfı ve gerekli yöntemlerini uygular.  
  
    ```csharp  
    using System;  
    using System.CodeDom;  
    using System.CodeDom.Compiler;  
    using System.Collections.Generic;  
    using System.Globalization;  
    using System.IO;  
    using System.Text;  
    using System.Xml;  
    using System.Xml.Serialization;  
    using Microsoft.VisualStudio.TextTemplating;  
  
    namespace CustomDP  
    {  
        public class CustomDirectiveProcessor : DirectiveProcessor  
        {  
            //this buffer stores the code that is added to the   
            //generated transformation class after all the processing is done   
            //---------------------------------------------------------------------  
            private StringBuilder codeBuffer;  
  
            //Using a Code Dom Provider creates code for the   
            //generated transformation class in either Visual Basic or C#.  
            //If you want your directive processor to support only one language, you  
            //can hard code the code you add to the generated transformation class.  
            //In that case, you do not need this field.  
            //--------------------------------------------------------------------------  
            private CodeDomProvider codeDomProvider;  
  
            //this stores the full contents of the text template that is being processed  
            //--------------------------------------------------------------------------  
            private String templateContents;  
  
            //These are the errors that occur during processing. The engine passes   
            //the errors to the host, and the host can decide how to display them,  
            //for example the the host can display the errors in the UI  
            //or write them to a file.  
            //---------------------------------------------------------------------  
            private CompilerErrorCollection errorsValue;  
            public new CompilerErrorCollection Errors  
            {  
                get { return errorsValue; }  
            }  
  
            //Each time this directive processor is called, it creates a new property.  
            //We count how many times we are called, and append "n" to each new  
            //property name. The property names are therefore unique.  
            //-----------------------------------------------------------------------------  
            private int directiveCount = 0;  
  
            public override void Initialize(ITextTemplatingEngineHost host)  
            {  
                //we do not need to do any initialization work  
            }  
  
            public override void StartProcessingRun(CodeDomProvider languageProvider, String templateContents, CompilerErrorCollection errors)  
            {  
                //the engine has passed us the language of the text template  
                //we will use that language to generate code later  
                //----------------------------------------------------------  
                this.codeDomProvider = languageProvider;  
                this.templateContents = templateContents;  
                this.errorsValue = errors;  
  
                this.codeBuffer = new StringBuilder();  
            }  
  
            //Before calling the ProcessDirective method for a directive, the   
            //engine calls this function to see whether the directive is supported.  
            //Notice that one directive processor might support many directives.  
            //---------------------------------------------------------------------  
            public override bool IsDirectiveSupported(string directiveName)  
            {  
                if (string.Compare(directiveName, "CoolDirective", StringComparison.OrdinalIgnoreCase) == 0)  
                {  
                    return true;  
                }  
                if (string.Compare(directiveName, "SuperCoolDirective", StringComparison.OrdinalIgnoreCase) == 0)  
                {  
                    return true;  
                }  
                return false;  
            }  
  
            public override void ProcessDirective(string directiveName, IDictionary<string, string> arguments)  
            {  
                if (string.Compare(directiveName, "CoolDirective", StringComparison.OrdinalIgnoreCase) == 0)  
                {  
                    string fileName;  
  
                    if (!arguments.TryGetValue("FileName", out fileName))  
                    {  
                        throw new DirectiveProcessorException("Required argument 'FileName' not specified.");  
                    }  
  
                    if (string.IsNullOrEmpty(fileName))  
                    {  
                        throw new DirectiveProcessorException("Argument 'FileName' is null or empty.");  
                    }  
  
                    //Now we add code to the generated transformation class.  
                    //This directive supports either Visual Basic or C#, so we must use the  
                    //System.CodeDom to create the code.  
                    //If a directive supports only one language, you can hard code the code.  
                    //--------------------------------------------------------------------------  
  
                    CodeMemberField documentField = new CodeMemberField();  
  
                    documentField.Name = "document" + directiveCount + "Value";  
                    documentField.Type = new CodeTypeReference(typeof(XmlDocument));  
                    documentField.Attributes = MemberAttributes.Private;  
  
                    CodeMemberProperty documentProperty = new CodeMemberProperty();  
  
                    documentProperty.Name = "Document" + directiveCount;  
                    documentProperty.Type = new CodeTypeReference(typeof(XmlDocument));  
                    documentProperty.Attributes = MemberAttributes.Public;  
                    documentProperty.HasSet = false;  
                    documentProperty.HasGet = true;  
  
                    CodeExpression fieldName = new CodeFieldReferenceExpression(new CodeThisReferenceExpression(), documentField.Name);  
                    CodeExpression booleanTest = new CodeBinaryOperatorExpression(fieldName, CodeBinaryOperatorType.IdentityEquality, new CodePrimitiveExpression(null));  
                    CodeExpression rightSide = new CodeMethodInvokeExpression(new CodeTypeReferenceExpression("XmlReaderHelper"), "ReadXml", new CodePrimitiveExpression(fileName));  
                    CodeStatement[] thenSteps = new CodeStatement[] { new CodeAssignStatement(fieldName, rightSide) };  
  
                    CodeConditionStatement ifThen = new CodeConditionStatement(booleanTest, thenSteps);  
                    documentProperty.GetStatements.Add(ifThen);  
  
                    CodeStatement s = new CodeMethodReturnStatement(fieldName);  
                    documentProperty.GetStatements.Add(s);  
  
                    CodeGeneratorOptions options = new CodeGeneratorOptions();  
                    options.BlankLinesBetweenMembers = true;  
                    options.IndentString = "    ";  
                    options.VerbatimOrder = true;  
                    options.BracingStyle = "C";  
  
                    using (StringWriter writer = new StringWriter(codeBuffer, CultureInfo.InvariantCulture))  
                    {  
                        codeDomProvider.GenerateCodeFromMember(documentField, writer, options);  
                        codeDomProvider.GenerateCodeFromMember(documentProperty, writer, options);  
                    }  
  
                }//end CoolDirective  
  
                //One directive processor can contain many directives.  
                //If you want to support more directives, the code goes here...  
                //-----------------------------------------------------------------  
                if (string.Compare(directiveName, "supercooldirective", StringComparison.OrdinalIgnoreCase) == 0)  
                {  
                    //code for SuperCoolDirective goes here...  
                }//end SuperCoolDirective  
  
                //Track how many times the processor has been called.  
                //-----------------------------------------------------------------  
                directiveCount++;  
  
            }//end ProcessDirective  
  
            public override void FinishProcessingRun()  
            {  
                this.codeDomProvider = null;  
  
                //important: do not do this:  
                //the get methods below are called after this method   
                //and the get methods can access this field  
                //-----------------------------------------------------------------  
                //this.codeBuffer = null;  
            }  
  
            public override string GetPreInitializationCodeForProcessingRun()  
            {  
                //Use this method to add code to the start of the   
                //Initialize() method of the generated transformation class.  
                //We do not need any pre-initialization, so we will just return "".  
                //-----------------------------------------------------------------  
                //GetPreInitializationCodeForProcessingRun runs before the   
                //Initialize() method of the base class.  
                //-----------------------------------------------------------------  
                return String.Empty;  
            }  
  
            public override string GetPostInitializationCodeForProcessingRun()  
            {  
                //Use this method to add code to the end of the   
                //Initialize() method of the generated transformation class.  
                //We do not need any post-initialization, so we will just return "".  
                //------------------------------------------------------------------  
                //GetPostInitializationCodeForProcessingRun runs after the  
                //Initialize() method of the base class.  
                //-----------------------------------------------------------------  
                return String.Empty;  
            }  
  
            public override string GetClassCodeForProcessingRun()  
            {  
                //Return the code to add to the generated transformation class.  
                //-----------------------------------------------------------------  
                return codeBuffer.ToString();  
            }  
  
            public override string[] GetReferencesForProcessingRun()  
            {  
                //This returns the references that we want to use when   
                //compiling the generated transformation class.  
                //-----------------------------------------------------------------  
                //We need a reference to this assembly to be able to call   
                //XmlReaderHelper.ReadXml from the generated transformation class.  
                //-----------------------------------------------------------------  
                return new string[]  
                {  
                    "System.Xml",  
                    this.GetType().Assembly.Location  
                };  
            }  
  
            public override string[] GetImportsForProcessingRun()  
            {  
                //This returns the imports or using statements that we want to   
                //add to the generated transformation class.  
                //-----------------------------------------------------------------  
                //We need CustomDP to be able to call XmlReaderHelper.ReadXml  
                //from the generated transformation class.  
                //-----------------------------------------------------------------  
                return new string[]  
                {  
                    "System.Xml",  
                    "CustomDP"  
                };  
            }  
        }//end class CustomDirectiveProcessor  
  
        //-------------------------------------------------------------------------  
        // the code that we are adding to the generated transformation class   
        // will call this method  
        //-------------------------------------------------------------------------  
        public static class XmlReaderHelper  
        {  
            public static XmlDocument ReadXml(string fileName)  
            {  
                XmlDocument d = new XmlDocument();  
  
                using (XmlTextReader reader = new XmlTextReader(fileName))  
                {  
                    try  
                    {  
                        d.Load(reader);  
                    }  
                    catch (System.Xml.XmlException e)  
                    {  
                        throw new DirectiveProcessorException("Unable to read the XML file.", e);  
                    }  
                }  
                return d;  
            }  
        }//end class XmlReaderHelper  
    }//end namespace CustomDP  
    ```  
  
    ```vb  
    Imports System  
    Imports System.CodeDom  
    Imports System.CodeDom.Compiler  
    Imports System.Collections.Generic  
    Imports System.Globalization  
    Imports System.IO  
    Imports System.Text  
    Imports System.Xml  
    Imports System.Xml.Serialization  
    Imports Microsoft.VisualStudio.TextTemplating  
  
    Namespace CustomDP  
  
        Public Class CustomDirectiveProcessor  
        Inherits DirectiveProcessor  
  
            'this buffer stores the code that is added to the   
            'generated transformation class after all the processing is done   
            '---------------------------------------------------------------  
            Private codeBuffer As StringBuilder  
  
            'Using a Code Dom Provider creates code for the  
            'generated transformation class in either Visual Basic or C#.  
            'If you want your directive processor to support only one language, you  
            'can hard code the code you add to the generated transformation class.  
            'In that case, you do not need this field.  
            '--------------------------------------------------------------------------  
            Private codeDomProvider As CodeDomProvider  
  
            'this stores the full contents of the text template that is being processed  
            '--------------------------------------------------------------------------  
            Private templateContents As String  
  
            'These are the errors that occur during processing. The engine passes   
            'the errors to the host, and the host can decide how to display them,  
            'for example the the host can display the errors in the UI  
            'or write them to a file.  
            '---------------------------------------------------------------------  
            Private errorsValue As CompilerErrorCollection  
            Public Shadows ReadOnly Property Errors() As CompilerErrorCollection  
                Get  
                    Return errorsValue  
                End Get  
            End Property  
  
            'Each time this directive processor is called, it creates a new property.  
            'We count how many times we are called, and append "n" to each new  
            'property name. The property names are therefore unique.  
            '--------------------------------------------------------------------------  
            Private directiveCount As Integer = 0  
  
            Public Overrides Sub Initialize(ByVal host As ITextTemplatingEngineHost)  
  
                'we do not need to do any initialization work  
            End Sub  
  
            Public Overrides Sub StartProcessingRun(ByVal languageProvider As CodeDomProvider, ByVal templateContents As String, ByVal errors As CompilerErrorCollection)  
  
                'the engine has passed us the language of the text template  
                'we will use that language to generate code later  
                '----------------------------------------------------------  
                Me.codeDomProvider = languageProvider  
                Me.templateContents = templateContents  
                Me.errorsValue = errors  
  
                Me.codeBuffer = New StringBuilder()  
            End Sub  
  
            'Before calling the ProcessDirective method for a directive, the   
            'engine calls this function to see whether the directive is supported.  
            'Notice that one directive processor might support many directives.  
            '---------------------------------------------------------------------  
            Public Overrides Function IsDirectiveSupported(ByVal directiveName As String) As Boolean  
  
                If String.Compare(directiveName, "CoolDirective", StringComparison.OrdinalIgnoreCase) = 0 Then  
                    Return True  
                End If  
  
                If String.Compare(directiveName, "SuperCoolDirective", StringComparison.OrdinalIgnoreCase) = 0 Then  
                    Return True  
                End If  
  
                Return False  
            End Function  
  
            Public Overrides Sub ProcessDirective(ByVal directiveName As String, ByVal arguments As IDictionary(Of String, String))  
  
                If String.Compare(directiveName, "CoolDirective", StringComparison.OrdinalIgnoreCase) = 0 Then  
  
                    Dim fileName As String  
  
                    If Not (arguments.TryGetValue("FileName", fileName)) Then  
                        Throw New DirectiveProcessorException("Required argument 'FileName' not specified.")  
                    End If  
  
                    If String.IsNullOrEmpty(fileName) Then  
                        Throw New DirectiveProcessorException("Argument 'FileName' is null or empty.")  
                    End If  
  
                    'Now we add code to the generated transformation class.  
                    'This directive supports either Visual Basic or C#, so we must use the  
                    'System.CodeDom to create the code.  
                    'If a directive supports only one language, you can hard code the code.  
                    '--------------------------------------------------------------------------  
  
                    Dim documentField As CodeMemberField = New CodeMemberField()  
  
                    documentField.Name = "document" & directiveCount & "Value"  
                    documentField.Type = New CodeTypeReference(GetType(XmlDocument))  
                    documentField.Attributes = MemberAttributes.Private  
  
                    Dim documentProperty As CodeMemberProperty = New CodeMemberProperty()  
  
                    documentProperty.Name = "Document" & directiveCount  
                    documentProperty.Type = New CodeTypeReference(GetType(XmlDocument))  
                    documentProperty.Attributes = MemberAttributes.Public  
                    documentProperty.HasSet = False  
                    documentProperty.HasGet = True  
  
                    Dim fieldName As CodeExpression = New CodeFieldReferenceExpression(New CodeThisReferenceExpression(), documentField.Name)  
                    Dim booleanTest As CodeExpression = New CodeBinaryOperatorExpression(fieldName, CodeBinaryOperatorType.IdentityEquality, New CodePrimitiveExpression(Nothing))  
                    Dim rightSide As CodeExpression = New CodeMethodInvokeExpression(New CodeTypeReferenceExpression("XmlReaderHelper"), "ReadXml", New CodePrimitiveExpression(fileName))  
                    Dim thenSteps As CodeStatement() = New CodeStatement() {New CodeAssignStatement(fieldName, rightSide)}  
  
                    Dim ifThen As CodeConditionStatement = New CodeConditionStatement(booleanTest, thenSteps)  
                    documentProperty.GetStatements.Add(ifThen)  
  
                    Dim s As CodeStatement = New CodeMethodReturnStatement(fieldName)  
                    documentProperty.GetStatements.Add(s)  
  
                    Dim options As CodeGeneratorOptions = New CodeGeneratorOptions()  
                    options.BlankLinesBetweenMembers = True  
                    options.IndentString = "    "  
                    options.VerbatimOrder = True  
                    options.BracingStyle = "VB"  
  
                    Using writer As StringWriter = New StringWriter(codeBuffer, CultureInfo.InvariantCulture)  
  
                        codeDomProvider.GenerateCodeFromMember(documentField, writer, options)  
                        codeDomProvider.GenerateCodeFromMember(documentProperty, writer, options)  
                    End Using  
  
                End If  'CoolDirective  
  
                'One directive processor can contain many directives.  
                'If you want to support more directives, the code goes here...  
                '-----------------------------------------------------------------  
                If String.Compare(directiveName, "supercooldirective", StringComparison.OrdinalIgnoreCase) = 0 Then  
  
                    'code for SuperCoolDirective goes here  
                End If 'SuperCoolDirective  
  
                'Track how many times the processor has been called.  
                '-----------------------------------------------------------------  
                directiveCount += 1  
            End Sub 'ProcessDirective  
  
            Public Overrides Sub FinishProcessingRun()  
  
                Me.codeDomProvider = Nothing  
  
                'important: do not do this:  
                'the get methods below are called after this method   
                'and the get methods can access this field  
                '-----------------------------------------------------------------  
                'Me.codeBuffer = Nothing  
            End Sub  
  
            Public Overrides Function GetPreInitializationCodeForProcessingRun() As String  
  
                'Use this method to add code to the start of the   
                'Initialize() method of the generated transformation class.  
                'We do not need any pre-initialization, so we will just return "".  
                '-----------------------------------------------------------------  
                'GetPreInitializationCodeForProcessingRun runs before the   
                'Initialize() method of the base class.  
                '-----------------------------------------------------------------  
                Return String.Empty  
            End Function  
  
            Public Overrides Function GetPostInitializationCodeForProcessingRun() As String  
  
                'Use this method to add code to the end of the   
                'Initialize() method of the generated transformation class.  
                'We do not need any post-initialization, so we will just return "".  
                '------------------------------------------------------------------  
                'GetPostInitializationCodeForProcessingRun runs after the  
                'Initialize() method of the base class.  
                '-----------------------------------------------------------------  
                Return String.Empty  
            End Function  
  
            Public Overrides Function GetClassCodeForProcessingRun() As String  
  
                'Return the code to add to the generated transformation class.  
                '-----------------------------------------------------------------  
                Return codeBuffer.ToString()  
            End Function  
  
            Public Overrides Function GetReferencesForProcessingRun() As String()  
  
                'This returns the references that we want to use when   
                'compiling the generated transformation class.  
                '-----------------------------------------------------------------  
                'We need a reference to this assembly to be able to call   
                'XmlReaderHelper.ReadXml from the generated transformation class.  
                '-----------------------------------------------------------------  
                Return New String() {"System.Xml", Me.GetType().Assembly.Location}  
            End Function  
  
            Public Overrides Function GetImportsForProcessingRun() As String()  
  
                'This returns the imports or using statements that we want to   
                'add to the generated transformation class.  
                '-----------------------------------------------------------------  
                'We need CustomDP to be able to call XmlReaderHelper.ReadXml  
                'from the generated transformation class.  
                '-----------------------------------------------------------------  
                Return New String() {"System.Xml", "CustomDP"}  
            End Function  
        End Class 'CustomDirectiveProcessor  
  
        '--------------------------------------------------------------------------  
        ' the code that we are adding to the generated transformation class   
        ' will call this method  
        '--------------------------------------------------------------------------  
        Public Class XmlReaderHelper  
  
            Public Shared Function ReadXml(ByVal fileName As String) As XmlDocument  
  
                Dim d As XmlDocument = New XmlDocument()  
  
                Using reader As XmlTextReader = New XmlTextReader(fileName)  
  
                    Try  
                        d.Load(reader)  
  
                    Catch e As System.Xml.XmlException  
  
                        Throw New DirectiveProcessorException("Unable to read the XML file.", e)  
                    End Try  
                End Using  
  
                Return d  
            End Function  
        End Class 'XmlReaderHelper  
  
    End Namespace  
    ```  
  
4.  İçin [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] yalnızca, açık **proje** menüsüne ve ardından **CustomDP özellikleri**. Üzerinde **uygulama** sekmesinde **kök ad alanı**, varsayılan değeri Sil `CustomDP`.  
  
5.  Üzerinde **dosya** menüsünde tıklatın **Tümünü Kaydet**.  
  
6.  Üzerinde **yapı** menüsünde tıklatın **yapı çözümü**.  
  
### <a name="build-the-project"></a>Projeyi Oluşturma  
 Projeyi oluşturun. Üzerinde **yapı** menüsünde tıklatın **yapı çözümü**.  
  
## <a name="registering-the-directive-processor"></a>Yönerge İşlemcisini Kaydetme  
 Bir metin şablonunda bir yönerge çağırmadan önce [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)], yönerge işlemcisi için bir kayıt defteri anahtarı eklemeniz gerekir.  
  
> [!NOTE]
>  Yönerge işlemcisi birden fazla bilgisayara yüklemek istiyorsanız, daha iyi tanımlamak bir [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] .pkgdef dosya derlemenizi birlikte içeren uzantısı (VSIX). Daha fazla bilgi için bkz: [özel yönerge işlemcisi dağıtma](../modeling/deploying-a-custom-directive-processor.md).  
  
 Yönerge işlemcilerinin anahtarları, kayıt defterinde aşağıdaki konumda bulunur:  
  
```  
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\*.0\TextTemplating\DirectiveProcessors  
```  
  
 64-bit sistemler için kayıt defteri konumu şudur:  
  
```  
HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\VisualStudio\*.0\TextTemplating\DirectiveProcessors  
```  
  
 Bu bölümde, özel bir yönerge işlemciniz için aynı konumda kayıt defterine bir anahtar eklersiniz.  
  
> [!CAUTION]
>  Kayıt defterinin hatalı şekilde düzenlenmesi sisteminizde ciddi arızalara yol açabilir. Kayıt defterinde değişiklikler yapmadan önce, bilgisayarınızdaki tüm değerli verileri yedekleyin.  
  
#### <a name="to-add-a-registry-key-for-the-directive-processor"></a>Yönerge işlemcisi için bir kayıt defteri anahtarı eklemek için  
  
1.  Çalıştırma `regedit` Başlat menüsünden veya komut satırını kullanarak komutu.  
  
2.  Konuma göz atın **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\\\*.0\TextTemplating\DirectiveProcessors**ve düğümünü tıklatın.  
  
     64 bitlik sistemlerde kullanmak **HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\VisualStudio\\\*.0\TextTemplating\DirectiveProcessors**  
  
3.  CustomDirectiveProcessor adlı yeni bir anahtar ekleyin.  
  
    > [!NOTE]
    >  Bu, özel yönergelerinizin İşlemci alanına kullanacağınız addır. Bu adın, yönergenin adıyla, yönerge işlemcisi sınıfının adıyla veya yönerge işlemcisinin alan adıyla eşleşmesi gerekmez.  
  
4.  Yeni dizenin adı olarak CustomDP.CustomDirectiveProcessor sahip, Sınıf adlı yeni bir dize değeri ekleyin.  
  
5.  Bu kılavuzda daha önce oluşturduğunuz CustomDP.dll dosyasının yoluna eşit değere sahip, CodeBase adlı yeni bir dize değeri ekleyin.  
  
     Örneğin, yol aşağıdaki gibi görünmelidir `C:\UserFiles\CustomDP\bin\Debug\CustomDP.dll`.  
  
     Kayıt defteri anahtarınız aşağıdaki değerlere sahip olmalı:  
  
    |Ad|Tür|Veri|  
    |----------|----------|----------|  
    |(Varsayılan)|REG_SZ|(değer ayarlı değil)|  
    |örneği|REG_SZ|CustomDP.CustomDirectiveProcessor|  
    |CodeBase|REG_SZ|**\<Çözümünüzü yolu >**CustomDP\bin\Debug\CustomDP.dll|  
  
     Derlemeyi GAC içine koyduysanız, değerler aşağıdaki gibi görünmelidir:  
  
    |Ad|Tür|Veri|  
    |----------|----------|----------|  
    |(Varsayılan)|REG_SZ|(değer ayarlı değil)|  
    |örneği|REG_SZ|CustomDP.CustomDirectiveProcessor|  
    |Derleme|REG_SZ|CustomDP.dll|  
  
6.  Visual Studio'yu yeniden başlatın.  
  
## <a name="testing-the-directive-processor"></a>Yönerge İşlemcisini Test Etme  
 Yönerge işlemcisini sınamak için onu çağıran bir metin şablonu yazmanız gerekir.  
  
 Bu örnekte, metin şablonu yönergeyi çağırır ve bir sınıf dosyasının belgelerini içeren bir XML dosyası adını geçirir.
  
 Metin şablonu sonra kullanır <xref:System.Xml.XmlDocument> XML gidin ve belge açıklamaları yazdırmak için yönergesi oluşturur özelliği.  
  
#### <a name="to-create-an-xml-file-for-use-in-testing-the-directive-processor"></a>Yönerge işlemcisini sınamada kullanmak için bir XML dosyası oluşturmak için  
  
1.  Adlı bir metin dosyası oluşturun `DocFile.xml` herhangi bir metin düzenleyicisi (örneğin, Not Defteri) kullanarak.  
  
    > [!NOTE]
    >  Bu dosyayı herhangi bir konumda (örneğin, C:\Test\DocFile.xml) oluşturabilirsiniz.  
  
2.  Aşağıdakileri metin dosyasına ekleyin:  
  
    ```  
    <?xml version="1.0"?>  
    <doc>  
        <assembly>  
            <name>xmlsample</name>  
        </assembly>  
        <members>  
            <member name="T:SomeClass">  
                <summary>Class level summary documentation goes here.</summary>  
                <remarks>Longer comments can be associated with a type or member through the remarks tag</remarks>  
            </member>  
            <member name="F:SomeClass.m_Name">  
                <summary>Store for the name property</summary>  
            </member>   
            <member name="M:SomeClass.#ctor">  
                <summary>The class constructor.</summary>   
            </member>  
            <member name="M:SomeClass.SomeMethod(System.String)">  
                <summary>Description for SomeMethod.</summary>  
                <param name="s">Parameter description for s goes here</param>  
                <seealso cref="T:System.String">You can use the cref attribute on any tag to reference a type or member and the compiler will check that the reference exists.</seealso>  
            </member>  
            <member name="M:SomeClass.SomeOtherMethod">  
                <summary>Some other method.</summary>  
                <returns>Return results are described through the returns tag.</returns>  
                <seealso cref="M:SomeClass.SomeMethod(System.String)">Notice the use of the cref attribute to reference a specific method</seealso>  
            </member>  
            <member name="M:SomeClass.Main(System.String[])">  
                <summary>The entry point for the application.</summary>  
                <param name="args">A list of command line arguments</param>  
            </member>  
            <member name="P:SomeClass.Name">  
                <summary>Name property</summary>  
                <value>A value tag is used to describe the property value</value>  
            </member>  
        </members>  
    </doc>  
    ```  
  
3.  Dosyayı kaydedin ve kapatın.  
  
#### <a name="to-create-a-text-template-to-test-the-directive-processor"></a>Yönerge işlemcisini sınamak için bir metin şablonu oluşturmak için  
  
1.  Visual Studio'da, TemplateTest adlı bir C# veya Visual Basic kitaplık projesi oluşturun.  
  
2.  TestDP.tt adlı yeni bir metin şablonu dosyasını ekleyin.  
  
3.  Olduğundan emin olun **özel araç** TestDP.tt özelliği ayarlanmış `TextTemplatingFileGenerator`.  
  
4.  TestDP.tt içeriğini aşağıdaki metin olarak değiştirin.  
  
    > [!NOTE]
    >  Dize değiştirdiğinizden emin olun <`YOUR PATH>` DocFile.xml dosya yoluna sahip.  
  
     Metin şablonunun dilinin yönerge işlemcisinin diliyle eşleşmesine gerek yoktur.  
  
    ```csharp  
    <#@ assembly name="System.Xml" #>  
    <#@ template debug="true" #>  
    <#@ output extension=".txt" #>  
  
    <#  //This will call the custom directive processor. #>  
    <#@ CoolDirective Processor="CustomDirectiveProcessor" FileName="<YOUR PATH>\DocFile.xml" #>  
  
    <#  //Uncomment this line if you want to see the generated transformation class. #>  
    <#  //System.Diagnostics.Debugger.Break(); #>  
  
    <#  //This will use the results of the directive processor. #>  
    <#  //The directive processor has read the XML and stored it in Document0. #>  
    <#  
        XmlNode node = Document0.DocumentElement.SelectSingleNode("members");  
  
        foreach (XmlNode member in node.ChildNodes)  
        {  
            XmlNode name = member.Attributes.GetNamedItem("name");  
            WriteLine("{0,7}:  {1}", "Name", name.Value);  
  
            foreach (XmlNode comment in member.ChildNodes)  
            {  
                WriteLine("{0,7}:  {1}", comment.Name, comment.InnerText);  
            }  
            WriteLine("");  
        }  
    #>  
  
    <#  //You can call the directive processor again and pass it a different file. #>  
    <# //@ CoolDirective Processor="CustomDirectiveProcessor" FileName="<YOUR PATH>\<Your Second File>" #>  
  
    <#  //To use the results of the second directive call, use Document1. #>  
    <#  
        //XmlNode node2 = Document1.DocumentElement.SelectSingleNode("members");  
  
        //...  
    #>  
    ```  
  
    ```vb  
    <#@ assembly name="System.Xml" #>  
    <#@ template debug="true" language="vb" #>  
    <#@ output extension=".txt" #>  
  
    <#  'This will call the custom directive processor. #>  
    <#@ CoolDirective Processor="CustomDirectiveProcessor" FileName="<YOUR PATH>\DocFile.xml" #>  
  
    <#  'Uncomment this line if you want to see the generated transformation class. #>  
    <#  'System.Diagnostics.Debugger.Break() #>  
  
    <#  'This will use the results of the directive processor. #>  
    <#  'The directive processor has read the XML and stored it in Document0. #>  
    <#  
        Dim node as XmlNode = Document0.DocumentElement.SelectSingleNode("members")  
  
        Dim member As XmlNode  
        For Each member In node.ChildNodes  
  
            Dim name As XmlNode = member.Attributes.GetNamedItem("name")  
            WriteLine("{0,7}:  {1}", "Name", name.Value)  
  
            Dim comment As XmlNode  
            For Each comment In member.ChildNodes  
                WriteLine("{0,7}:  {1}", comment.Name, comment.InnerText)  
            Next  
  
            WriteLine("")  
        Next  
    #>  
  
    <#  'You can call the directive processor again and pass it a different file. #>  
    <# '@ CoolDirective Processor="CustomDirectiveProcessor" FileName="<YOUR PATH>\DocFileTwo.xml" #>  
  
    <#  'To use the results of the second directive call, use Document1. #>  
    <#  
        'node = Document1.DocumentElement.SelectSingleNode("members")  
  
        '...  
    #>  
    ```  
  
    > [!NOTE]
    >  Bu örnekte, değeri `Processor` parametresi `CustomDirectiveProcessor`. Değeri `Processor` parametresi processor'ın kayıt defteri anahtarı adını eşleşmesi gerekir.  
  
5.  Üzerinde **dosya** menüsünde tıklatın **Tümünü Kaydet**.  
  
#### <a name="to-test-the-directive-processor"></a>Yönerge işlemcisini sınamak için  
  
1.  İçinde **Çözüm Gezgini**, TestDP.tt sağ tıklayın ve ardından **çalıştırmak özel araç**.  
  
     İçin [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] kullanıcılar, TestDP.txt değil görüntülenebilir içinde **Çözüm Gezgini** varsayılan olarak. Projeye atanan tüm dosyaları görüntülemek için açık **proje** menüsüne ve ardından **tüm dosyaları göster**.  
  
2.  İçinde **Çözüm Gezgini**TestDP.txt düğümünü genişletin ve ardından TestDP.txt düzenleyicisinde açmak için çift tıklayın.  
  
     Oluşturulan metin çıktısı görüntülenir. Çıktı aşağıdaki gibi görünmelidir:  
  
    ```  
       Name:  T:SomeClass  
    summary:  Class level summary documentation goes here.  
    remarks:  Longer comments can be associated with a type or member through the remarks tag  
  
       Name:  F:SomeClass.m_Name  
    summary:  Store for the name property  
  
       Name:  M:SomeClass.#ctor  
    summary:  The class constructor.  
  
       Name:  M:SomeClass.SomeMethod(System.String)  
    summary:  Description for SomeMethod.  
      param:  Parameter description for s goes here  
    seealso:  You can use the cref attribute on any tag to reference a type or member and the compiler will check that the reference exists.  
  
       Name:  M:SomeClass.SomeOtherMethod  
    summary:  Some other method.  
    returns:  Return results are described through the returns tag.  
    seealso:  Notice the use of the cref attribute to reference a specific method  
  
       Name:  M:SomeClass.Main(System.String[])  
    summary:  The entry point for the application.  
      param:  A list of command line arguments  
  
       Name:  P:SomeClass.Name  
    summary:  Name property  
      value:  A value tag is used to describe the property value  
    ```  
  
## <a name="adding-html-to-generated-text"></a>Oluşturulan Metne HTML Ekleme  
 Özel yönerge işlemcinizi sınadıktan sonra, oluşturulan metninize HTML eklemek isteyebilirsiniz.  
  
#### <a name="to-add-html-to-the-generated-text"></a>Oluşturulan metninize HTML eklemek için  
  
1.  TestDP.tt öğesindeki kodu aşağıdakiyle değiştirin. HTML vurgulanır. Dize değiştirdiğinizden emin olun `YOUR PATH` DocFile.xml dosya yoluna sahip.  
  
    > [!NOTE]
    >  Ek açık \<# ve Kapat #> etiketleri HTML etiketleri deyimi kodunu ayırın.  
  
    ```csharp  
    <#@ assembly name="System.Xml" #>  
    <#@ template debug="true" #>  
    <#@ output extension=".htm" #>  
  
    <#  //this will call the custom directive processor #>  
    <#@ CoolDirective Processor="CustomDirectiveProcessor" FileName="<YOUR PATH>\DocFile.xml" #>  
  
    <#  //uncomment this line if you want to see the generated transformation class #>  
    <#  //System.Diagnostics.Debugger.Break(); #>  
  
    <html><body>  
  
    <#  //this will use the results of the directive processor #>  
    <#  //the directive processor has read the XML and stored it in Document0#>  
    <#  
        XmlNode node = Document0.DocumentElement.SelectSingleNode("members");  
  
        foreach (XmlNode member in node.ChildNodes)  
        {  
    #>  
    <h3>  
    <#      
            XmlNode name = member.Attributes.GetNamedItem("name");  
            WriteLine("{0,7}:  {1}", "Name", name.Value);  
    #>  
    </h3>  
    <#  
            foreach (XmlNode comment in member.ChildNodes)  
            {  
                WriteLine("{0,7}:  {1}", comment.Name, comment.InnerText);  
    #>  
    <br/>  
    <#  
            }  
        }  
    #>  
    </body></html>  
    ```  
  
    ```vb  
    <#@ assembly name="System.Xml" #>  
    <#@ template debug="true" language="vb" #>  
    <#@ output extension=".htm" #>  
  
    <#  'this will call the custom directive processor #>  
    <#@ CoolDirective Processor="CustomDirectiveProcessor" FileName="<YOUR PATH>\DocFile.xml" #>  
  
    <#  'uncomment this line if you want to see the generated transformation class #>  
    <#  'System.Diagnostics.Debugger.Break() #>  
  
    <html><body>  
  
    <#  'this will use the results of the directive processor #>  
    <#  'the directive processor has read the XML and stored it in Document0#>  
    <#  
        Dim node as XmlNode = Document0.DocumentElement.SelectSingleNode("members")  
  
        Dim member As XmlNode  
        For Each member In node.ChildNodes  
    #>  
    <h3>  
    <#      
            Dim name As XmlNode = member.Attributes.GetNamedItem("name")  
            WriteLine("{0,7}:  {1}", "Name", name.Value)  
    #>  
    </h3>  
    <#  
            Dim comment As XmlNode  
            For Each comment In member.ChildNodes  
                WriteLine("{0,7}:  {1}", comment.Name, comment.InnerText)  
    #>  
    <br/>  
    <#  
            Next  
        Next  
    #>  
    </body></html>  
    ```  
  
2.  Üzerinde **dosya** menüsünde tıklatın **kaydetmek TestDP.txt**.  
  
3.  Çıktı bir tarayıcıda görüntülemek için **Çözüm Gezgini**, TestDP.htm sağ tıklayın ve **görünüm tarayıcıda**.  
  
     Çıktınız orijinal metinle aynı olmalıdır, aralarındaki tek fark çıktınıza HTML biçiminin uygulanmış olmasıdır. Her öğe adı kalın yazı tipinde görüntülenmelidir.
