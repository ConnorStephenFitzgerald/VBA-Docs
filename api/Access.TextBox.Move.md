---
title: TextBox.Move method (Access)
keywords: vbaac10.chm11144
f1_keywords:
- vbaac10.chm11144
ms.prod: access
api_name:
- Access.TextBox.Move
ms.assetid: 50b25305-0b91-378d-514f-d35b8d7aed6e
ms.date: 02/20/2019
ms.localizationpriority: medium
---


# TextBox.Move method (Access)

Moves the specified object to the coordinates specified by the argument values.


## Syntax

_expression_.**Move** (_Left_, _Top_, _Width_, _Height_)

_expression_ A variable that represents a **[TextBox](Access.TextBox.md)** object.

## Parameters

|Name|Required/Optional|Data type|Description|
|:-----|:-----|:-----|:-----|
| _Left_|Required|**Variant**|The screen position in [twips](../language/glossary/vbe-glossary.md#twip) for the left edge of the object relative to the left edge of the Microsoft Access window.|
| _Top_|Optional|**Variant**|The screen position in twips for the top edge of the object relative to the top edge of the Access window.|
| _Width_|Optional|**Variant**|The desired width of the object in twips.|
| _Height_|Optional|**Variant**|The desired height of the object in twips.|

## Remarks

Only the _Left_ argument is required. However, to specify any other arguments, you must specify all the arguments that precede it. For example, you cannot specify _Width_ without specifying _Left_ and _Top_. Any trailing arguments that are unspecified remain unchanged.

This method overrides the **Moveable** property.

In Datasheet view or Print Preview, changes made by using the **Move** method are saved if the user explicitly saves the database, but Access does not prompt the user to save such changes.




[!include[Support and feedback](~/includes/feedback-boilerplate.md)]