---
title: ColorSchemes.Count property (Publisher)
keywords: vbapb10.chm2752514
f1_keywords:
- vbapb10.chm2752514
ms.prod: publisher
api_name:
- Publisher.ColorSchemes.Count
ms.assetid: cd3fe69f-df35-8dcd-1133-634983155592
ms.date: 06/06/2019
ms.localizationpriority: medium
---


# ColorSchemes.Count property (Publisher)

Returns a **Long** that represents the number of items in the specified collection.


## Syntax

_expression_.**Count**

_expression_ A variable that represents a **[ColorSchemes](Publisher.ColorSchemes.md)** object.


## Example

This example displays the number of pages in the active document.

```vb
Sub CountNumberOfPages() 
 MsgBox "Your publication contains " & _ 
 ActiveDocument.Pages.Count & " page(s)." 
End Sub
```

<br/>

This example displays the number of shapes in the active document.

```vb
Sub CountNumberOfShapes() 
 Dim intShapes As Integer 
 Dim pg As Page 
 
 For Each pg In ActiveDocument.Pages 
 intShapes = intShapes + pg.Shapes.Count 
 Next 
 
 MsgBox "Your publication contains " & intShapes & " shape(s)." 
End Sub
```

[!include[Support and feedback](~/includes/feedback-boilerplate.md)]