---
title: Layers.ItemU property (Visio)
keywords: vis_sdr.chm11951980
f1_keywords:
- vis_sdr.chm11951980
ms.prod: visio
api_name:
- Visio.Layers.ItemU
ms.assetid: e8e5e70e-0626-27df-3fbc-00c348e0a444
ms.date: 06/08/2017
ms.localizationpriority: medium
---


# Layers.ItemU property (Visio)

Returns an object from a collection. Read-only.


## Syntax

_expression_.**ItemU** (_NameOrIndex_)

_expression_ A variable that represents a **[Layers](Visio.Layers.md)** object.


## Parameters

|Name|Required/Optional|Data type|Description|
|:-----|:-----|:-----|:-----|
| _NameOrIndex_|Required| **Variant**|Contains the universal name, unique ID, or index of the object to retrieve.|

## Return value

Layer


## Remarks

You can retrieve an object in an **Addons**, **Hyperlinks**, **Layers**, **Masters**, **MasterShortcuts**, **Pages**, **Shapes**, or **Styles** collection by passing the object's name as a string expression in a **Variant**.

If you retrieve a **Shape** object by name, the **ItemU** property searches all shapes in the **Shapes** collection's containing page or containing master, in addition to the collection's containing shape. Therefore, the **Shape** object returned by the **ItemU** property can be a shape that is not in the **Shapes** collection.

You can also pass the unique ID string of a **Master** or **Shape** object to the **ItemU** property. For example:

```vb
objRet = vsoShapes.ItemU("{2287DC42-B167-11CE-88E9-0020AFDDD917}")
```

If such a string is passed to the **ItemU** property of a **Shapes** collection, all the shapes contained in the collection are searched. Shapes within the group shapes in the containing shape are not searched.

To search all shapes in the collection, plus the shapes inside groups and the containing shape of the collection, prefix the unique ID string with an asterisk (*). For example:

```vb
objRet = vsoShapes.ItemU("*{2287DC42-B167-11CE-88E9-0020AFDDD917}")
```



## Example

This Microsoft Visual Basic macro shows how to use the **ItemU** property of the **Pages** collection to get the **Shapes** collection. It then uses the **ItemU** property of the **Shapes** collection to print the universal names of all shapes on Page-1 in the Immediate window.

To run this macro, make sure the active document has shapes on Page-1.

```vb
Public Sub ItemU_Example() 
  
    Dim intCounter As Integer 
    Dim intShapeCount As Integer 
    Dim vsoShapes As Visio.Shapes  
 
    Set vsoShapes = ActiveDocument.Pages.ItemU(1).Shapes  
 
    Debug.Print "Shapes in Document: "; ActiveDocument.Name  
    Debug.Print "          on  Page: "; ActiveDocument.Pages.ItemU(1).Name  
 
    intShapeCount = vsoShapes.Count  
 
    If intShapeCount > 0 Then 
 
        For intCounter = 1 To intShapeCount  
            Debug.Print " "; vsoShapes.ItemU(intCounter).Name  
        Next intCounter 
  
    Else 
 
        Debug.Print " No Shapes On Page" 
  
    End If   
 
End Sub
```

[!include[Support and feedback](~/includes/feedback-boilerplate.md)]