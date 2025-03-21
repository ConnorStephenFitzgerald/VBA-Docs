---
title: EmptyCell.SizeToFit method (Access)
keywords: vbaac10.chm14300
f1_keywords:
- vbaac10.chm14300
ms.prod: access
api_name:
- Access.EmptyCell.SizeToFit
ms.assetid: ac4daffa-e89d-7d22-3885-3fe54ba9e155
ms.date: 02/20/2019
ms.localizationpriority: medium
---


# EmptyCell.SizeToFit method (Access)

Use the **SizeToFit** method to size a control so that it fits the text or image that it contains.


## Syntax

_expression_.**SizeToFit**

_expression_ A variable that represents an **[EmptyCell](Access.EmptyCell.md)** object.


## Remarks

For example, you can apply the **SizeToFit** method to a command button that is too small to display all the text in its **Caption** property.

You can apply the **SizeToFit** method to controls only in form Design view or report Design view.

The **SizeToFit** method makes a control larger or smaller, depending on the size of the text or image that it contains.

Use the **SizeToFit** method in conjunction with the **[CreateControl](Access.Application.CreateControl.md)** method to size new controls that you have created in code.

> [!NOTE] 
> Not all controls that contain text or an image can be sized by the **SizeToFit** method. Several controls are bound to data that can vary in size from one record to the next. These controls include the text box, list box, combo box, and bound object frame controls. The **SizeToFit** method does not apply to controls on data access pages.


## Example

The following example creates a new form and a command button on the form. The procedure then sets the control's **Caption** property and sizes the control to fit the caption.

```vb
Sub SizeNewControl() 
 Dim frm As Form, ctl As Control 
 
 ' Create new form. 
 Set frm = CreateForm 
 ' Create new command button. 
 Set ctl = CreateControl(frm.Name, _ 
 acCommandButton, , , , 500, 500) 
 ' Restore form. 
 DoCmd.Restore 
 ' Set control's Caption property. 
 ctl.Caption = "Extremely Long Control Caption" 
 ' Size control to fit caption. 
 ctl.SizeToFit 
End Sub
```




[!include[Support and feedback](~/includes/feedback-boilerplate.md)]