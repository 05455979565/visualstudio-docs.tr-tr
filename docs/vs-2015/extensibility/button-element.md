---
title: Button öğesi | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
helpviewer_keywords:
- Buttons element (VSCT XML schema)
- VSCT XML schema elements, Buttons
ms.assetid: 96dccf51-2b00-4700-9d28-924b34c21ecd
caps.latest.revision: 12
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 58f63968ed02f49b0ccfa4dda24f684fed339bc4
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "68184548"
---
# <a name="button-element"></a>Button Öğesi
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Kullanıcının etkileşime geçtiği bir öğe tanımlar. Düğmeler, farklı türde olabilir: Düğme, MenuButton ve SplitDropDown.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
<Button guid="guidMyCommandSet" id="MyCommand" priority="0x102" type="button">  
  <Parent>... </Parent>  
  <Icon>... </Icon>  
  <CommandFlag>... </CommandFlag>  
  <Strings>... </Strings>  
</Button>  
```  
  
## <a name="attributes-and-elements"></a>Öznitelikler ve Öğeler  
 Öznitelikler, alt ve üst öğeler aşağıdaki bölümlerde açıklanmaktadır.  
  
### <a name="attributes"></a>Öznitelikler  
  
|Öznitelik|Açıklama|  
|---------------|-----------------|  
|guid|Gerekli. GUID/ID komut tanımlayıcısı GUİD'si.|  
|kimlik|Gerekli. Kimliği bir GUID/ID komut tanımlayıcısı.|  
|priority|İsteğe bağlı. Bir sayısal değer yönelik önceliği belirtir.|  
|türü|İsteğe bağlı. Düğme türünü belirten bir numaralandırılmış değeri.<br /><br /> Belirtilmemişse, düğme kullanır.<br /><br /> Düğme<br /> Araç çubuklarında (genellikle icon bir düğme olarak), menüler ve bağlam menüleri görünür bir standart komutu.<br /><br /> MenuButton<br /> Komut yürütme değil, ancak başka bir menü üreten bir menü öğesi.<br /><br /> SplitDropDown<br /> Microsoft Word standart araç çubuğundaki Geri Al ve Yinele düğmeler gibi denetimler.|  
|Koşul|İsteğe bağlı. Bkz: [koşullu öznitelikler](../extensibility/vsct-xml-schema-conditional-attributes.md).|  
  
### <a name="child-elements"></a>Alt Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[Parent Öğesi](../extensibility/parent-element.md)|İsteğe bağlı. Düğmenin üst öğe.|  
|[Icon Öğesi](../extensibility/icon-element.md)|İsteğe bağlı. Düğme ile ilişkili simge.|  
|[Command Flag Öğesi](../extensibility/command-flag-element.md)|Gerekli. Bir düğme için geçerli CommandFlag değerler aşağıdaki gibidir.<br /><br /> -AllowParams<br /><br /> -CommandWellOnly<br /><br /> -DefaultDisabled<br /><br /> -DefaultInvisible<br /><br /> -DontCache<br /><br /> -DynamicItemStart<br /><br /> -DynamicVisibility<br /><br /> -FixMenuController<br /><br /> -IconAndText<br /><br /> -NoButtonCustomize<br /><br /> -NoCustomize<br /><br /> -NoKeyCustomize<br /><br /> -NoShowOnMenuController<br /><br /> -PICT<br /><br /> -PostExec<br /><br /> -ProfferedCmd<br /><br /> -RouteToDocs<br /><br /> -TextCascadeUseBtn<br /><br /> -TextMenuUseButton<br /><br /> -TextChanges<br /><br /> -TextChangesButton<br /><br /> -TextContextUseButton<br /><br /> -TextMenuCtrlUseMenu<br /><br /> -TextMenuUseButton<br /><br /> -TextOnly|  
|[Strings Öğesi](../extensibility/strings-element.md)|Gerekli. Alt [ButtonText öğesi](../extensibility/buttontext-element.md) tanımlanması gerekir.|  
|Ek Açıklama|İsteğe bağlı bir açıklama.|  
  
### <a name="parent-elements"></a>Üst Öğeler  
  
|Öğe|Açıklama|  
|-------------|-----------------|  
|[Buttons Öğesi](../extensibility/buttons-element.md)|Düğme öğelerini gruplandırır.|  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir düğme .vsct dosyası tanımlar.  
   
 ```xml
<Button guid="guidMenuTextCmdSet" id="cmdidMyCommand" priority="0x0100" type="Button">
    <Parent guid="guidMenuTextCmdSet" id="MyMenuGroup" />
    <Icon guid="guidImages" id="bmpPic1" />
    <CommandFlag>TextChanges</CommandFlag>
    <Strings>
          <CommandName>cmdidMyCommand</CommandName>
          <ButtonText>My Command name</ButtonText>
    </Strings>
</Button>
 ```

## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio Komut Tablosu (.Vsct) Dosyaları](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)
