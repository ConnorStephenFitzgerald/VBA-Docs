---
title: ParagraphFormat.LineSpacing property (Publisher)
keywords: vbapb10.chm5439504
f1_keywords:
- vbapb10.chm5439504
ms.prod: publisher
api_name:
- Publisher.ParagraphFormat.LineSpacing
ms.assetid: cb9abe6a-794c-6a58-2706-e12bbb5a302b
ms.date: 06/12/2019
ms.localizationpriority: medium
---


# ParagraphFormat.LineSpacing property (Publisher)

Returns or sets a **Variant** that represents the line spacing (in number of lines) for the specified paragraphs. Read/write.


## Syntax

_expression_.**LineSpacing**

_expression_ A variable that represents a **[ParagraphFormat](Publisher.ParagraphFormat.md)** object.


## Return value

Variant


## Remarks

Use the **[LineSpacingRule](Publisher.ParagraphFormat.LineSpacingRule.md)** property to set the line spacing to a preset value.


## Example

This example sets the line spacing of the paragraph at the cursor position to three lines. This example assumes that the cursor is in a text box.

```vb
Sub SetLineSpacing() 
 Selection.TextRange.ParagraphFormat.LineSpacing = 3 
End Sub
```

[!include[Support and feedback](~/includes/feedback-boilerplate.md)]