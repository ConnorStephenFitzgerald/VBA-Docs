---
title: ObjectFrame.OnExit property (Access)
keywords: vbaac10.chm11616
f1_keywords:
- vbaac10.chm11616
ms.prod: access
api_name:
- Access.ObjectFrame.OnExit
ms.assetid: 47cb4cb3-1d8a-d286-a7df-832d6aa3fb55
ms.date: 02/23/2019
ms.localizationpriority: medium
---


# ObjectFrame.OnExit property (Access)

Sets or returns the value of the **On Exit** box in the Properties window of specified object. Read/write **String**. 


## Syntax

_expression_.**OnExit**

_expression_ A variable that represents an **[ObjectFrame](Access.ObjectFrame.md)** object.


## Remarks

This property is helpful for programmatically changing the action that Microsoft Access takes when an event is triggered. For example, between event calls you may want to change an expression's parameters, or switch from an event procedure to an expression or macro, depending on the circumstances under which the event was triggered. 

The **Exit** event occurs just before a control loses the focus to another control on the same form.

The **OnExit** value will be one of the following, depending on the selection chosen in the Choose Builder window (accessed by choosing the **Build** button next to the **On Exit** box in the object's Properties window):

- If you choose Expression Builder, the value will be =_expression_, where _expression_ is the expression from the Expression Builder window.
    
- If you choose Macro Builder, the value is the name of the macro. 
    
- If you choose Code Builder, the value will be [Event Procedure]. 
    
If the **On Exit** box is blank, the property value is an empty string.


## Example

The following example associates the **Exit** event with the macro **Exit_Macro** for the button named **OK** on the **Order Entry** form.


```vb
Forms("Order Entry").Controls("OK").OnExit = "Exit_Macro"
```



[!include[Support and feedback](~/includes/feedback-boilerplate.md)]