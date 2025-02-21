---
title: Form.BeforeRender event (Access)
keywords: vbaac10.chm13679
f1_keywords:
- vbaac10.chm13679
ms.prod: access
api_name:
- Access.Form.BeforeRender
ms.assetid: 5661065e-472d-c073-948c-40b19c965848
ms.date: 03/08/2019
ms.localizationpriority: medium
---


# Form.BeforeRender event (Access)

Occurs before any object in the specified PivotChart view has been rendered.


## Syntax

_expression_.**BeforeRender** (_drawObject_, _chartObject_, _Cancel_)

_expression_ A variable that represents a **[Form](Access.Form.md)** object.


## Parameters

|Name|Required/Optional|Data type|Description|
|:-----|:-----|:-----|:-----|
| _drawObject_|Required|**Object**|A reference to the **ChChartDraw** object. Use the **DrawType** property of the returned object to determine what type of rendering is about to occur.|
| _chartObject_|Required|**Object**| The object that is to be rendered. Use the **TypeName** function to determine the type of the object.|
| _Cancel_|Required|**Object**| Set the **Value** property of this object to **True** to cancel the rendering of the PivotChart view object.|

## Return value

Nothing


## Example

The following example demonstrates the syntax for a subroutine that traps the **BeforeRender** event.

```vb
Private Sub Form_BeforeRender( _ 
 ByVal drawObject As Object, _ 
 ByVal chartObject As Object, _ 
 ByVal Cancel As Object) 
 Dim intResponse As Integer 
 Dim strPrompt As String 
 
 strPrompt = "Cancel render of current object?" 
 
 intResponse = MsgBox(strPrompt, vbYesNo) 
 
 If intResponse = vbYes Then 
 Cancel.Value = True 
 Else 
 Cancel.Value = False 
 End If 
End Sub
```




[!include[Support and feedback](~/includes/feedback-boilerplate.md)]