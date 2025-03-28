---
title: Report.OnOpen property (Access)
keywords: vbaac10.chm13763
f1_keywords:
- vbaac10.chm13763
ms.prod: access
api_name:
- Access.Report.OnOpen
ms.assetid: e381f9a5-c409-7ae5-e266-cb3a046eb919
ms.date: 03/15/2019
ms.localizationpriority: medium
---


# Report.OnOpen property (Access)

Sets or returns the value of the **On Open** box in the Properties window of a form or report. Read/write **String**.


## Syntax

_expression_.**OnOpen**

_expression_ A variable that represents a **[Report](Access.Report.md)** object.


## Remarks

This property is helpful for programmatically changing the action that Microsoft Access takes when an event is triggered. For example, between event calls you may want to change an expression's parameters, or switch from an event procedure to an expression or macro, depending on the circumstances under which the event was triggered.

The **Open** event occurs when a form is opened, but before the first record is displayed. For reports, the event occurs before a report is previewed or printed.

The **OnOpen** value will be one of the following, depending on the selection chosen in the Choose Builder window (accessed by choosing the **Build** button next to the **On Open** box in the object's Properties window):

- If you choose Expression Builder, the value will be =_expression_, where _expression_ is the expression from the Expression Builder window.
    
- If you choose Macro Builder, the value is the name of the macro. 
    
- If you choose Code Builder, the value will be [Event Procedure]. 
    
If the **On Open** box is blank, the property value is an empty string.



[!include[Support and feedback](~/includes/feedback-boilerplate.md)]