---
title: ListBox.ControlTipText property (Access)
keywords: vbaac10.chm11261
f1_keywords:
- vbaac10.chm11261
ms.prod: access
api_name:
- Access.ListBox.ControlTipText
ms.assetid: 27abccf5-e3f2-2c0c-06ee-4160eb447374
ms.date: 02/21/2019
ms.localizationpriority: medium
---


# ListBox.ControlTipText property (Access)

Use the **ControlTipText** property to specify the text that appears in a ScreenTip when you hold the mouse pointer over a control. Read/write **String**.


## Syntax

_expression_.**ControlTipText**

_expression_ A variable that represents a **[ListBox](Access.ListBox.md)** object.


## Remarks

You set the **ControlTipText** property by using a string expression up to 255 characters long.

For controls on forms, you can set the default for this property by using the default control style or the **[DefaultControl](access.form.defaultcontrol.md)** property in Visual Basic.

You can set the **ControlTipText** property in any view.

The **ControlTipText** property provides an easy way to provide helpful information about controls on a form.

There are other ways to provide information about a form or a control on a form. Use the **StatusBarText** property to display information in the status bar about a control. To provide more extensive help for a form or control, use the **[HelpFile](access.form.helpfile.md)** and **[HelpContextID](access.form.helpcontextid.md)** properties.




[!include[Support and feedback](~/includes/feedback-boilerplate.md)]