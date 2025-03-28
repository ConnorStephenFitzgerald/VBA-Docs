---
title: FormatConditions.Application property (Access)
keywords: vbaac10.chm10067
f1_keywords:
- vbaac10.chm10067
ms.prod: access
api_name:
- Access.FormatConditions.Application
ms.assetid: 2c02da47-d005-ef0e-650c-106257342ed0
ms.date: 03/20/2019
ms.localizationpriority: medium
---


# FormatConditions.Application property (Access)

Use the **Application** property to access the active Microsoft Access **[Application](Access.Application.md)** object and its related properties. Read-only **Application** object.


## Syntax

_expression_.**Application**

_expression_ A variable that represents a **[FormatConditions](Access.FormatConditions.md)** object.


## Remarks

The **Application** property is set by Microsoft Access and is read-only in all views.

Each Microsoft Access object has an **Application** property that returns the current **Application** object. Use this property to access any of the object's properties. For example, you could refer to the menu bar for the **Application** object from the current form by using the following syntax.

```vb
Me.Application.MenuBar 

```



[!include[Support and feedback](~/includes/feedback-boilerplate.md)]