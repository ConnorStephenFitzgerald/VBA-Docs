---
title: EmptyCell.Left property (Access)
keywords: vbaac10.chm14307
f1_keywords:
- vbaac10.chm14307
ms.prod: access
api_name:
- Access.EmptyCell.Left
ms.assetid: 69ed2465-33e0-a823-4cfe-97b9c1c55ed4
ms.date: 02/22/2019
ms.localizationpriority: medium
---


# EmptyCell.Left property (Access)

Use the **Left** property to specify an object's location on a form or report. Read/write **Integer**.


## Syntax

_expression_.**Left**

_expression_ A variable that represents an **[EmptyCell](Access.EmptyCell.md)** object.


## Remarks

In Visual Basic, use a numeric expression to set the value of this property. Values are expressed in [twips](../language/glossary/vbe-glossary.md#twip).

For reports, you can set these properties only by using a macro or event procedure in Visual Basic while the report is in Print Preview or being printed.

For reports, the **Left** property setting is the amount that the current section is offset from the left of the page. This property is expressed in twips. 

Use this property to specify how far down the page you want a section to print in the section's **Format** event procedure.


## Example

The following example checks the **Left** property setting for the current report. If the value is less than the minimum margin setting, the **NextRecord** and **PrintSection** properties are set to **False** (0). The section doesn't advance to the next record, and the next section isn't printed.


```vb
Sub Detail1_Format(Cancel As Integer, FormatCount As Integer) 
 
 Const conLeftMargin = 1880 
 
 ' Don't advance to next record or print next section 
 ' if Left property setting is less than 1880 twips. 
 If Me.Left < conLeftMargin Then 
 Me.NextRecord = False 
 Me.PrintSection = False 
 End If 
 
End Sub
```


[!include[Support and feedback](~/includes/feedback-boilerplate.md)]