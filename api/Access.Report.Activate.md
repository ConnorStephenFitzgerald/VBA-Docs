---
title: Report.Activate event (Access)
keywords: vbaac10.chm13878
f1_keywords:
- vbaac10.chm13878
ms.prod: access
api_name:
- Access.Report.Activate
ms.assetid: 565cf35c-e7ea-e1ec-b23b-b84a6318fde7
ms.date: 03/08/2019
ms.localizationpriority: medium
---


# Report.Activate event (Access)

The **Activate** event occurs when a report receives the focus and becomes the active window.


## Syntax

_expression_.**Activate**

_expression_ A variable that represents a **[Report](Access.Report.md)** object.


## Return value

Nothing


## Remarks

To run a macro or event procedure when these events occur, set the **OnActivate** or **OnDeactivate** property to the name of the macro or to [Event Procedure].

You can make a report active by opening it, or by choosing it or a control on it.

The **Activate** event can occur only when a report is visible.

The **Activate** event occurs before the **GotFocus** event; the **Deactivate** event occurs after the **LostFocus** event.


[!include[Support and feedback](~/includes/feedback-boilerplate.md)]