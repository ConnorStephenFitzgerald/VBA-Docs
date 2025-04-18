---
title: PageBreak.ControlType property (Access)
keywords: vbaac10.chm11673
f1_keywords:
- vbaac10.chm11673
ms.prod: access
api_name:
- Access.PageBreak.ControlType
ms.assetid: 79977aab-29e3-7a25-38ee-a01645a87cdb
ms.date: 02/21/2019
ms.localizationpriority: medium
---


# PageBreak.ControlType property (Access)

Use the **ControlType** property in Visual Basic to determine the type of control on a form or report. Read/write **Byte**.


## Syntax

_expression_.**ControlType**

_expression_ A variable that represents a **[PageBreak](Access.PageBreak.md)** object.


## Remarks

The **ControlType** property setting is an intrinsic constant that specifies the control type. For a complete list of controls created by the **[CreateControl](Access.Application.CreateControl.md)** and **[CreateReportControl](access.application.createreportcontrol.md)** methods, see the **[AcControlType](access.accontroltype.md)** enumeration.

The **ControlType** property can only be set by using Visual Basic in form Design view or report Design view, but it can be read in all views.

The **ControlType** property is useful not only for checking for a specific control type in code, but also for changing the type of control to another type. For example, you can change a text box to a combo box by setting the **ControlType** property for the text box to **acComboBox** while in form Design view.

Use the **ControlType** property to change characteristics of similar controls on a form according to certain conditions. For example, if you don't want users to edit existing data in text boxes, you can set the **SpecialEffect** property for all text boxes to Flat and set the form's **AllowEdits** property to No. (The **SpecialEffect** property doesn't affect whether data can be edited; it's used here to provide a visual cue that the control behavior has changed.)

The **ControlType** property is also used to specify the type of control to create when you are using the **CreateControl** method.


## Example

The following example examines the **ControlType** property for all controls on a form. For each label and text box control, the procedure toggles the **SpecialEffect** property for those controls. 

When the **SpecialEffect** property of the label control is set to Shadowed, and the **SpecialEffect** property of the text box control is set to Normal, and the **AllowAdditions**, **AllowDeletions**, and **AllowEdits** properties are all set to **True**, the `intCanEdit` variable is toggled to allow editing of the underlying data.


```vb
Sub ToggleControl(frm As Form) 
 Dim ctl As Control 
 Dim intI As Integer, intCanEdit As Integer 
 Const conTransparent = 0 
 Const conWhite = 16777215 
 For Each ctl in frm.Controls 
 With ctl 
 Select Case .ControlType 
 Case acLabel 
 If .SpecialEffect = acEffectShadow Then 
 .SpecialEffect = acEffectNormal 
 .BorderStyle = conTransparent 
 intCanEdit = True 
 Else 
 .SpecialEffect = acEffectShadow 
 intCanEdit = False 
 End If 
 Case acTextBox 
 If .SpecialEffect = acEffectNormal Then 
 .SpecialEffect = acEffectSunken 
 .BackColor = conWhite 
 Else 
 .SpecialEffect = acEffectNormal 
 .BackColor = frm.Detail.BackColor 
 End If 
 End Select 
 End With 
 Next ctl 
 If intCanEdit = IFalse Then 
 With frm 
 .AllowAdditions = False 
 .AllowDeletions = False 
 .AllowEdits = False 
 End With 
 Else 
 With frm 
 .AllowAdditions = True 
 .AllowDeletions = True 
 .AllowEdits = True 
 End With 
 End If 
End Sub
```



[!include[Support and feedback](~/includes/feedback-boilerplate.md)]