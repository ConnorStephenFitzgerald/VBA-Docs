---
title: TabControl.KeyUp event (Access)
keywords: vbaac10.chm14277
f1_keywords:
- vbaac10.chm14277
ms.prod: access
api_name:
- Access.TabControl.KeyUp
ms.assetid: c3e9b96d-fb29-6a0c-1547-145ab8f884ca
ms.date: 02/10/2019
ms.localizationpriority: medium
---


# TabControl.KeyUp event (Access)

The **KeyUp** event occurs when the user releases a key while a form or control has the focus. This event also occurs if you send a keystroke to a form or control by using the SendKeys action in a macro or the **SendKeys** statement in Visual Basic.


## Syntax

_expression_.**KeyUp** (_KeyCode_, _Shift_)

_expression_ A variable that represents a **[TabControl](Access.TabControl.md)** object.


## Parameters

|Name|Required/Optional|Data type|Description|
|:-----|:-----|:-----|:-----|
| _KeyCode_|Required|**Integer**|A key code, such as **vbKeyF1** (the F1 key) or **vbKeyHome** (the Home key). To specify key codes, use the intrinsic constants shown in the Object Browser. You can prevent an object from receiving a keystroke by setting _KeyCode_ to 0.|
| _Shift_|Required|**Integer**|The state of the Shift, Ctrl, and Alt keys at the time of the event. If you need to test for the _Shift_ argument, you can use one of the following intrinsic constants as bit masks:<ul><li><p><b>acShiftMask</b>  The bit mask for the Shift key.</p></li><li><p><b>acCtrlMask</b>  The bit mask for the Ctrl key.</p></li><li><p><b>acAltMask</b>  The bit mask for the Alt key.</p></li></ul> |



## Remarks

To run a macro or event procedure when these events occur, set the **OnKeyUp** property to the name of the macro or to [Event Procedure].

For both events, the object with the focus receives all keystrokes. A form can have the focus only if it has no controls or all its visible controls are disabled.

A form will also receive all keyboard events, even those that occur for controls, if you set the **KeyPreview** property of the form to Yes. With this property setting, all keyboard events occur first for the form, and then for the control that has the focus. You can respond to specific keys pressed in the form, regardless of which control has the focus. For example, you may want the key combination Ctrl+X to always perform the same action on a form.

If you press and hold down a key, the **KeyDown** and **KeyPress** events alternate repeatedly (**KeyDown**, **KeyPress**, **KeyDown**, **KeyPress**, and so on) until you release the key, then the **KeyUp** event occurs.

Although the **KeyUp** event occurs when most keys are pressed, it is typically used to recognize or distinguish between:

- Extended character keys, such as function keys.
    
- Navigation keys, such as Home, End, PgUp, PgDn, Up arrow, Down arrow, Right arrow, Left arrow, and Tab. 

- Combinations of keys and standard keyboard modifiers (Shift, Ctrl, or Alt keys).
    
- The numeric keypad and keyboard number keys.
    
The **KeyUp** event does not occur when you press:

- The Enter key if the form has a command button for which the **Default** property is set to Yes.
    
- The Esc key if the form has a command button for which the **Cancel** property is set to Yes.
    
The **KeyUp** event occurs after any event for a control caused by pressing or sending the key. If a keystroke causes the focus to move from one control to another control, the **KeyDown** event occurs for the first control, while the **KeyPress** and **KeyUp** events occur for the second control.

To find out the ANSI character corresponding to the key pressed, use the **KeyPress** event.

If a modal dialog box is displayed as a result of pressing or sending a key, the **KeyDown** and **KeyPress** events occur, but the **KeyUp** event doesn't occur.




[!include[Support and feedback](~/includes/feedback-boilerplate.md)]