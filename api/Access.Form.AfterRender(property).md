---
title: Form.AfterRender property (Access)
keywords: vbaac10.chm13549,vbaac10.chm5114
f1_keywords:
- vbaac10.chm13549,vbaac10.chm5114
ms.prod: access
api_name:
- Access.Form.AfterRender
ms.assetid: 868b9a9d-a1e3-d460-fa7c-26cb5791c5ad
ms.date: 03/09/2019
ms.localizationpriority: medium
---


# Form.AfterRender property (Access)

Returns or sets a **String** indicating which macro, event procedure, or user-defined function runs when the **[AfterRender](Access.Form.AfterRender(even).md)** event occurs. Read/write.


## Syntax

_expression_.**AfterRender**

_expression_ A variable that represents a **[Form](Access.Form.md)** object.


## Remarks

Valid values for this property are:

- _macroname_, where _macroname_ is the name of a macro.

- [Event Procedure], which indicates the event procedure associated with the **AfterRender** event for the specified object.

- _=functionname()_, where _functionname_ is the name of a user-defined function.


## Example

The following example specifies that when the **AfterRender** event occurs on the first form of the current project, the associated event procedure should run.


```vb
Forms(0).AfterRender = "[Event Procedure]" 

```




[!include[Support and feedback](~/includes/feedback-boilerplate.md)]