---
title: TextBox.InSelection property (Access)
keywords: vbaac10.chm11114
f1_keywords:
- vbaac10.chm11114
ms.prod: access
api_name:
- Access.TextBox.InSelection
ms.assetid: 6ebb497c-00d0-a854-be22-6b034deae98a
ms.date: 02/22/2019
ms.localizationpriority: medium
---


# TextBox.InSelection property (Access)

Use the **InSelection** property to determine or specify whether a control on a form in Design view is selected. Read/write **Boolean**.


## Syntax

_expression_.**InSelection**

_expression_ A variable that represents a **[TextBox](Access.TextBox.md)** object.


## Remarks

When a control is selected, its sizing handles are visible, and it can be resized by the user. More than one control can be selected at a time.


## Example

The following function uses the **InSelection** property to determine whether the **strControlName** control on a form is selected.

To test this code, paste the **IsControlSelected** function code in the Declarations section of a code module in the Northwind sample database, open the **Customers** form in Design view, and select the **CompanyName** control. Enter the following line in the Debug window.


```vb
? IsControlSelected (Forms!Customers, "CompanyName") 
 
Function IsControlSelected(frm As Form, _ 
 strControlName As String) As Boolean 
 Dim intI As Integer, ctl As Control 
 If frm.CurrentView <> 0 Then 
 ' Form is not in Design view. 
 Exit Function 
 Else 
 For intI = 0 To frm.Count - 1 
 Set ctl = frm(intI) 
 If ctl.InSelection = True Then 
 ' Is desired control selected? 
 If UCase(ctl.Name) = UCase(strControlName) Then 
 IsControlSelected = True 
 Exit Function 
 End If 
 Else 
 IsControlSelected = False 
 End If 
 Next intI 
 End If 
End Function
```




[!include[Support and feedback](~/includes/feedback-boilerplate.md)]