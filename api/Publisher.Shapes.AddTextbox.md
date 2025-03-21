---
title: Shapes.AddTextbox method (Publisher)
keywords: vbapb10.chm2162720
f1_keywords:
- vbapb10.chm2162720
ms.prod: publisher
api_name:
- Publisher.Shapes.AddTextbox
ms.assetid: 38494902-61d5-2017-819e-248b2b7bc0d1
ms.date: 06/14/2019
ms.localizationpriority: medium
---


# Shapes.AddTextbox method (Publisher)

Adds a new **[Shape](Publisher.Shape.md)** object representing a text box to the specified **Shapes** collection.


## Syntax

_expression_.**AddTextbox** (_Orientation_, _Left_, _Top_, _Width_, _Height_)

_expression_ A variable that represents a **[Shapes](Publisher.Shapes.md)** object.


## Parameters

|Name|Required/Optional|Data type|Description|
|:-----|:-----|:-----|:-----|
|_Orientation_|Required| **[PbTextOrientation](publisher.pbtextorientation.md)**|The orientation of the text box.|
|_Left_ |Required| **Variant**|The position of the left edge of the shape representing the text box.|
|_Top_ |Required| **Variant**|The position of the top edge of the shape representing the text box.|
|_Width_|Required| **Variant**|The width of the shape representing the text box.|
|_Height_|Required| **Variant**|The height of the shape representing the text box.|

## Return value

Shape


## Remarks

For the _Left_, _Top_, _Width_, and _Height_ parameters, numeric values are evaluated in [points](../language/glossary/vbe-glossary.md#point); strings can be in any units supported by Microsoft Publisher (for example, "2.5 in").

The _Orientation_ parameter can be one of the **PbTextOrientation** constants declared in the Microsoft Publisher type library and shown in the following table.

|Constant|Description|
|:-----|:-----|
| **pbTextOrientationHorizontal**| A horizontal text box for left-to-right languages.|
| **pbTextOrientationRightToLeft**|A horizontal text box for right-to-left languages. This value has no effect if a right-to-left language is not selected.|
| **pbTextOrientationVerticalEastAsia**|A vertical text box for East Asian languages. If a non-East Asian language is selected, text appears rotated 90 degrees to the right.|

## Example

The following example adds a new horizontal text box to the first page of the active publication.

```vb
Dim shpTextBox As Shape 
 
Set shpTextBox = ActiveDocument.Pages(1).Shapes.AddTextBox _ 
 (Orientation:=pbTextOrientationHorizontal, _ 
 Left:=144, Top:=144, _ 
 Width:=72, Height:=18) 

```

[!include[Support and feedback](~/includes/feedback-boilerplate.md)]