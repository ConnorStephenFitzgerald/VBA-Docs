---
title: ShapeRange.MoveOutOfTextFlow method (Publisher)
keywords: vbapb10.chm2294032
f1_keywords:
- vbapb10.chm2294032
ms.prod: publisher
api_name:
- Publisher.ShapeRange.MoveOutOfTextFlow
ms.assetid: 36d6b22d-f041-6dd8-ce2c-9514ac6af5ae
ms.date: 06/14/2019
ms.localizationpriority: medium
---


# ShapeRange.MoveOutOfTextFlow method (Publisher)

Moves a given inline shape out of its containing text range, defined by the **[TextRange](Publisher.TextRange.md)** object, and makes the shape fixed.


## Syntax

_expression_.**MoveOutOfTextFlow**

_expression_ A variable that represents a **[ShapeRange](Publisher.ShapeRange.md)** object.


## Return value

Nothing


## Remarks

An automation error is returned if the shape to be moved is not already inline.

After the **MoveOutOfTextFlow** method is called on an inline shape, the shape will maintain its position on the page, but it will no longer be inline.


## Example

The following example moves the first inline shape contained in a given text range out of the text flow.

```vb
Dim theShape As Shape 
 
Set theShape = ActiveDocument.Pages(2).Shapes(1) _ 
 .TextFrame.TextRange.InlineShapes(1) 
 
theShape.MoveOutOfTextFlow
```

[!include[Support and feedback](~/includes/feedback-boilerplate.md)]