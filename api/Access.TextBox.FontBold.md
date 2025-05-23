---
title: TextBox.FontBold property (Access)
keywords: vbaac10.chm11091
f1_keywords:
- vbaac10.chm11091
ms.prod: access
api_name:
- Access.TextBox.FontBold
ms.assetid: 147d151a-b51c-5be2-56ef-8a94c212cb0b
ms.date: 03/01/2019
ms.localizationpriority: medium
---


# TextBox.FontBold property (Access)

Use the **FontBold** property to specify whether a font appears in a bold style in the following situations:

- When displaying or printing controls on forms and reports.   
- When using the **[Print](Access.Report.Print.md)** method on a report.
    
Read/write **Boolean**.

## Syntax

_expression_.**FontBold**

_expression_ A variable that represents a **[TextBox](Access.TextBox.md)** object.


## Remarks

The **FontBold** property uses the following settings.

|Setting|Description|
|:-----|:-----|
|**True**|The text is bold.|
|**False**|(Default) The text isn't bold.|

To use the **FontBold** property on a report, first create a **Print** event procedure that prints the desired text.

A font's appearance on screen and in print may differ, depending on your computer and printer.

The **FontWeight** property, which is available in the property sheet for controls, can also be used to set the line width for a control's text. The **FontBold** property gives you a quick way to make text bold; the **FontWeight** property gives you finer control over the line width setting for text. The following table shows the relationship between these properties' settings.

|If|Then|
|:-----|:-----|
|**FontBold** = **False**|**FontWeight** = Normal (400)|
|**FontBold** = **True**|**FontWeight** = Bold (700)|
|**FontWeight** < 700|**FontBold** = **False**|
|**FontWeight** > = 700|**FontBold** = **True**|

## Example

The following **Print** event procedure prints a report title and the current date in a bold style on a report at the coordinates specified by the **CurrentX** and **CurrentY** property settings.


```vb
Private Sub ReportHeader0_Print(Cancel As Integer, _ 
 PrintCount As Integer) 
 Dim MyDate 
 
 MyDate = Date 
 Me.FontBold = True 
 ' Print report title in bold. 
 Me.Print("Sales Management Report") 
 Me.Print(MyDate) 
End Sub
```


[!include[Support and feedback](~/includes/feedback-boilerplate.md)]