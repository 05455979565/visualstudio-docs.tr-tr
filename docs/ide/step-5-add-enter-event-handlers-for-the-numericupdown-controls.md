---
title: '5\. Adım: NumericUpDown denetimleri için Enter Olay işleyicileri ekleme'
ms.date: 11/04/2016
ms.topic: tutorial
ms.prod: visual-studio-windows
ms.technology: vs-ide-general
dev_langs:
- CSharp
- VB
ms.assetid: 45a99a5d-c881-4298-b74d-adb481dec5ee
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 8edebff5af7affebf166ea07ca7aa813037c13c2
ms.sourcegitcommit: 6eed0372976c0167b9a6d42ba443f9a474b8bb91
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2019
ms.locfileid: "71118741"
---
# <a name="step-5-add-enter-event-handlers-for-the-numericupdown-controls"></a>5\. Adım: NumericUpDown denetimleri için Giriş olay işleyicileri ekleme

Bu öğreticinin beşinci kısmında, test sorunlarına yönelik yanıtları biraz <xref:System.Windows.Forms.Control.Enter> daha kolay bir şekilde girmeye yönelik olay işleyicileri ekleyeceksiniz. Bu kod, test taki seçtiği ve farklı bir değer <xref:System.Windows.Forms.NumericUpDown> girmeye başladığı anda her denetimdeki geçerli değeri seçer ve temizler.

> [!NOTE]
> Bu konu, temel kodlama kavramlarıyla ilgili bir öğretici serisinin bir parçasıdır.
> - Öğreticiye genel bakış için bkz [. öğretici 2: Süreli bir matematik testi](../ide/tutorial-2-create-a-timed-math-quiz.md)oluşturun.
> - Kodun tamamlanmış bir sürümünü indirmek için bkz. [tüm matematik testi öğreticisi örneği](https://code.msdn.microsoft.com/Complete-Math-Quiz-8581813c).

## <a name="to-verify-the-default-behavior"></a>Varsayılan davranışı doğrulamak için

1. Programınızı çalıştırın ve testi başlatın.

     Ek sorun için **NumericUpDown** denetiminde, imleç **0** (sıfır) seçeneğinin yanında yanıp sönmesini sağlar.

2. **3**girin ve denetimin **30**gösterdiğini unutmayın.

3. **5**girin ve **350** ' un göründüğünü, ancak saniyenin sonunda **100** ' e değişiklik olduğunu unutmayın.

     Bu sorunu giderdikten sonra, neler olduğunu düşünün. **3** girdiğinizde **0** ' ın neden kaybolmaması gerektiğini ve **350** neden **100** olarak değiştirildiğini düşünün.

     Bu davranış tek görünebilir, ancak kodun mantığına göre daha anlamlı hale gelir. **Başlat** düğmesini seçtiğinizde, **etkin** özelliği **false**olarak ayarlanır ve Düğme soluk görünür ve kullanılamaz olur. Programınız, geçerli seçimi (odağı), ek sorun için NumericUpDown denetimi olan bir sonraki en düşük TabIndex değerine sahip olan denetim olarak değiştirir. Bir NumericUpDown denetimine gitmek için **Tab** tuşunu kullandığınızda, imleç denetimin başlangıcında otomatik olarak konumlandırılır. Bu, girdiğiniz sayıların sağ taraftan değil, sol taraftan görünmemesinin neden olduğu. 100 olarak ayarlanan **MaximumValue** özelliğinin değerinden daha yüksek bir sayı belirttiğinizde, girdiğiniz sayı bu özelliğin değeri ile değiştirilmiştir.

## <a name="to-add-an-enter-event-handler-for-a-numericupdown-control"></a>NumericUpDown denetimine bir Enter Olay işleyicisi eklemek için

1. Form üzerinde ilk **NumericUpDown** denetimini ("Sum" adlı) seçin ve ardından **Özellikler** iletişim kutusunda, araç çubuğundaki **Olaylar** simgesini seçin.

   ![Özellikler araç çubuğunda olaylar düğmesi](media/control-properties-events.png)

   **Özellikler** Iletişim kutusundaki **Olaylar** sekmesi, formda seçtiğiniz öğe için yanıt verebildiği tüm olayları (tanıtıcı) görüntüler. NumericUpDown denetimini seçtiğinizden, listelenen tüm olaylar buna aittir.

2. **ENTER** olayını seçin, yazın `answer_Enter` **ve ENTER tuşuna** basın.

   ![Olay işleyicisi yöntem adını girin](media/enter-event.png)

   Sum NumericUpDown denetimi için bir Enter Olay işleyicisi eklediniz ve Handler **answer_Enter**olarak adlandırdınız.

3. **Answer_Enter** olay işleyicisi yönteminde aşağıdaki kodu ekleyin:

     [!code-vb[VbExpressTutorial3Step5_6#11](../ide/codesnippet/VisualBasic/step-5-add-enter-event-handlers-for-the-numericupdown-controls_1.vb)]
     [!code-csharp[VbExpressTutorial3Step5_6#11](../ide/codesnippet/CSharp/step-5-add-enter-event-handlers-for-the-numericupdown-controls_1.cs)]

     > [!IMPORTANT]
     > C# Kod parçacığını veya Visual Basic kod parçacığını görüntülemek için bu sayfanın sağ üst kısmındaki programlama dili denetimini kullanın.<br><br>![Docs.Microsoft.com için programlama dili denetimi](../ide/media/docs-programming-language-control.png)

     Bu kod karmaşık görünebilir, ancak adım adım ' a baktığınızda bunu anlayabilirsiniz. İlk olarak, yönteminin en üstüne bakın: `object sender` içinde C# veya `sender As System.Object` Visual Basic. Bu parametre, gönderen olarak bilinen, olayı oluşturan nesnesine başvurur. Bu durumda, Gönderen nesnesi NumericUpDown denetimidir. Bu nedenle, yönteminin ilk satırında, gönderenin yalnızca herhangi bir genel nesne değil, özellikle bir NumericUpDown denetimi belirtmektir. (Her NumericUpDown denetimi bir nesnedir, ancak her nesne bir NumericUpDown denetimidir.) Yalnızca Sum NumericUpDown denetimini değil, formdaki NumericUpDown denetimleri için kullanılacak olan NumericUpDown denetimi bu yöntemde **doğrulamaktadır** olarak adlandırılır. Bu yöntemde doğrulamaktadır değişkenini bildirdiğiniz için, kapsamı yalnızca bu yöntem için geçerlidir. Diğer bir deyişle, değişken yalnızca bu yöntem içinde kullanılabilir.

     Sonraki satır, doğrulamaktadır başarıyla bir nesnesinden bir NumericUpDown denetimine dönüştürülüp dönüştürülmeyeceğini doğrular. Dönüştürme başarısız olduysa, değişkenin değeri `null` (C#) veya `Nothing` (Visual Basic) olur. Üçüncü satır, NumericUpDown denetiminde görünen yanıtın uzunluğunu alır ve dördüncü satır denetimdeki geçerli değeri bu uzunluğa göre seçer. Şimdi, test takici denetimi seçtiğinde, Visual Studio bu olayı harekete geçirilir ve bu da geçerli yanıtın seçilmesine neden olur. Test takici, farklı bir yanıt girmeye başladıktan sonra, önceki yanıt temizlenir ve yeni Yanıtla değiştirilmiştir.

4. **Windows Form Tasarımcısı**, fark **NumericUpDown** denetimini seçin.

5. **Özellikler** iletişim kutusunun **Olaylar** sayfasında, **ENTER** olayına ilerleyin, satırın sonundaki açılan oku seçin ve ardından yeni eklediğiniz `answer_Enter` olay işleyicisini seçin.

6. Ürün ve bölüm NumericUpDown denetimleri için önceki adımı yineleyin.

7. Programınızı kaydedin ve çalıştırın.

     Bir **NumericUpDown** denetimi seçtiğinizde, var olan değer otomatik olarak seçilir ve sonra farklı bir değer girmeye başladığınızda temizlenir.

## <a name="to-continue-or-review"></a>Devam etmek veya gözden geçirmek için

- Sonraki öğretici adımına gitmek için bkz  **[. 6. Adım: Çıkarma sorunu](../ide/step-6-add-a-subtraction-problem.md)** ekleyin.

- Önceki öğretici adımına dönmek için bkz [. 4. Adım: CheckTheAnswer () yöntemini](../ide/step-4-add-the-checktheanswer-parens-method.md)ekleyin.
