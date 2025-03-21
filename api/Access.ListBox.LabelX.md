---
title: ListBox.LabelX property (Access)
keywords: vbaac10.chm11268
f1_keywords:
- vbaac10.chm11268
ms.prod: access
api_name:
- Access.ListBox.LabelX
ms.assetid: 12335d2b-92e1-185b-df3e-db1e9002f757
ms.date: 02/22/2019
ms.localizationpriority: medium
---


# ListBox.LabelX property (Access)

The **LabelX** property (along with the **LabelY** property) specifies the placement of the label for a new control. Read/write **Integer**.


## Syntax

_expression_.**LabelX**

_expression_ A variable that represents a **[ListBox](Access.ListBox.md)** object.


## Remarks

If the orientation is left to right for a form or report, **LabelX** and **LabelY** behavior matches standard Microsoft Access left-to-right orientation. For more information about orientation, see the **[Orientation](access.form.orientation.md)** property.

If the orientation is right to left, the origin of the coordinate system for **LabelX** and **LabelY** is the upper-right corner of the attached control. A negative number for **LabelX** places the label to the right of the control. A negative number for **LabelY** places the label above the control.

For General and Right alignment when the orientation is right to left, **LabelX** and **LabelY** specify the location of the upper-right corner of the label relative to the upper-right corner of the label's attached control. 

For Left and Center alignment, **LabelX** and **LabelY** specify the location of the upper-left corner and top center, respectively, of the label relative to the upper-right corner of the label's attached control.


[!include[Support and feedback](~/includes/feedback-boilerplate.md)]