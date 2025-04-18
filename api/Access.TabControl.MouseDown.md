---
title: TabControl.MouseDown event (Access)
keywords: vbaac10.chm14272
f1_keywords:
- vbaac10.chm14272
ms.prod: access
api_name:
- Access.TabControl.MouseDown
ms.assetid: 84fc4acb-37df-e5d1-3aa7-15726da2fcde
ms.date: 02/10/2019
ms.localizationpriority: medium
---


# TabControl.MouseDown event (Access)

The **MouseDown** event occurs when the user presses a mouse button.


## Syntax

_expression_.**MouseDown** (_Button_, _Shift_, _X_, _Y_)

_expression_ A variable that represents a **[TabControl](Access.TabControl.md)** object.


## Parameters

|Name|Required/Optional|Data type|Description|
|:-----|:-----|:-----|:-----|
| _Button_|Required|**Integer**|The button that was pressed to trigger the event. If you need to test for the _Button_ argument, you can use one of the following intrinsic constants as bit masks:<ul><li><p><b>acLeftButton</b>  The bit mask for the left mouse button.</p></li><li><p><b>acRightButton</b>  The bit mask for the right mouse button.</p></li><li><p><b>acMiddleButton</b>  The bit mask for the middle mouse button.</p></li></ul>|
| _Shift_|Required|**Integer**|The state of the Shift, Ctrl, and Alt keys when the button specified by the _Button_ argument was pressed or released. If you need to test for the _Shift_ argument, you can use one of the following intrinsic constants as bit masks:<ul><li><p><b>acShiftMask</b>  The bit mask for the Shift key.</p></li><li><p><b>acCtrlMask</b>  The bit mask for the Ctrl key.</p></li><li><p><b>acAltMask</b>  The bit mask for the Alt key.</p></li></ul>|  
| _X_|Required|**Single**|The _x_ coordinate for the current location of the mouse pointer, in [twips](../language/glossary/vbe-glossary.md#twip). |
| _Y_|Required|**Single**|The _y_ coordinate for the current location of the mouse pointer, in twips. |

## Remarks

The **MouseDown** event applies only to forms, form sections, and controls on a form, and not to controls on a report.
    
This event does not apply to a label attached to another control, such as the label for a text box. It applies only to "freestanding" labels. Pressing and releasing a mouse button in an attached label has the same effect as pressing and releasing the button in the associated control. The normal events for the control occur; no separate events occur for the attached label.
    
To run a macro or event procedure when these events occur, set the **OnMouseDown** property to the name of the macro or to [Event Procedure].

Use a **MouseDown** event to specify what happens when a particular mouse button is pressed or released. Unlike the **Click** and **DblClick** events, the **MouseDown** event enables you to distinguish between the left, right, and middle mouse buttons. You can also write code for mouse-keyboard combinations that use the Shift, Ctrl, and Alt keys.

To cause a **MouseDown** event for a form to occur, press the mouse button in a blank area or record selector on the form. To cause a **MouseDown** event for a form section to occur, press the mouse button in a blank area of the form section.

The following apply to **MouseDown** events:

- If a mouse button is pressed while the pointer is over a form or control, that object receives all mouse events up to and including the last **MouseUp** event.
    
- If mouse buttons are pressed in succession, the object that receives the mouse event after the first press receives all mouse events until all buttons are released.
    
To respond to an event caused by moving the mouse, you use a **MouseMove** event.


## Example

The following example shows how you can find out which mouse button caused a **MouseDown** event.

To try the example, add the following event procedure to a form.

```vb
Private Sub Form_MouseDown(Button As Integer, _ 
         Shift As Integer, X As Single, _ 
         Y As Single) 
    If Button = acLeftButton Then 
        MsgBox "You pressed the left button." 
    End If 
    If Button = acRightButton Then 
        MsgBox "You pressed the right button." 
    End If 
    If Button = acMiddleButton Then 
        MsgBox "You pressed the middle button." 
    End If 
End Sub
```



[!include[Support and feedback](~/includes/feedback-boilerplate.md)]