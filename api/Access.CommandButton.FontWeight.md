---
title: CommandButton.FontWeight property (Access)
keywords: vbaac10.chm10474
f1_keywords:
- vbaac10.chm10474
ms.prod: access
api_name:
- Access.CommandButton.FontWeight
ms.assetid: a7c0b157-c25c-24e5-b05d-cc8ab726ac7b
ms.date: 03/02/2019
ms.localizationpriority: medium
---


# CommandButton.FontWeight property (Access)

Use the **FontWeight** property to specify the line width that Windows uses to display and print characters in a control. Read/write **Integer**.

## Syntax

_expression_.**FontWeight**

_expression_ A variable that represents a **[CommandButton](Access.CommandButton.md)** object.


## Remarks

The **FontWeight** property uses the following settings.

|Setting|Visual Basic|
|:-----|:-----|
|Thin|100|
|Extra Light|200|
|Light|300|
|Normal|400|
|Medium|500|
|Semi-bold|600|
|Bold|700|
|Extra Bold|800|
|Heavy|900|

You can set the default for this property by using a control's default control style or the **[DefaultControl](access.form.defaultcontrol.md)** property in Visual Basic.

A font's appearance on screen and in print may differ, depending on your computer and printer. For example, a **FontWeight** property setting of Thin may look identical to Normal on screen but appear lighter when printed.

The **FontBold** property, which is available only in Visual Basic and macros, can also be used to set the line width for a control's or report's text to bold. The **FontBold** property gives you a quick way to make text bold; the **FontWeight** property gives you finer control over the line width setting for text. The following table shows the relationship between these properties' settings.

|If|Then|
|:-----|:-----|
|**FontBold** = **False**|**FontWeight** = Normal (400)|
|**FontBold** = **True**|**FontWeight** = Bold (700)|
|**FontWeight** < 700|**FontBold** = **False**|
|**FontWeight** > = 700|**FontBold** = **True**|

## See also

- [DatasheetFontWeight property](access.form.datasheetfontweight.md)

[!include[Support and feedback](~/includes/feedback-boilerplate.md)]