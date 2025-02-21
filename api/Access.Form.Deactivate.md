---
title: Form.Deactivate event (Access)
keywords: vbaac10.chm13647
f1_keywords:
- vbaac10.chm13647
ms.prod: access
api_name:
- Access.Form.Deactivate
ms.assetid: 8702b30b-d38e-fcb6-141e-0ac4e53c63ad
ms.date: 03/08/2019
ms.localizationpriority: medium
---


# Form.Deactivate event (Access)

The **Deactivate** event occurs when a form loses the focus to a Table, Query, Form, Report, Macro, or Module window, or to the Database window.


## Syntax

_expression_.**Deactivate**

_expression_ A variable that represents a **[Form](Access.Form.md)** object.


## Return value

Nothing


## Remarks

When you switch between two open forms, the **Deactivate** event occurs for the form being switched from, and the **Activate** event occurs for the form being switched to. If the forms contain no visible, enabled controls, the **LostFocus** event occurs for the first form before the **Deactivate** event, and the **GotFocus** event occurs for the second form after the **Activate** event.

When you first open a form, the following events occur in this order:

> **Open** → **Load** → **Resize** → **Activate** → **Current**

When you close a form, the following events occur in this order:

> **Unload** → **Deactivate** → **Close**




[!include[Support and feedback](~/includes/feedback-boilerplate.md)]