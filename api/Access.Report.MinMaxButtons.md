---
title: Report.MinMaxButtons property (Access)
keywords: vbaac10.chm13802
f1_keywords:
- vbaac10.chm13802
ms.prod: access
api_name:
- Access.Report.MinMaxButtons
ms.assetid: 8aee0247-804a-e9ee-e11a-11c9c5d37ed6
ms.date: 03/15/2019
ms.localizationpriority: medium
---


# Report.MinMaxButtons property (Access)

Use the **MinMaxButtons** property to specify whether the **Maximize** and **Minimize** buttons will be visible on a report. Read/write **Byte**.


## Syntax

_expression_.**MinMaxButtons**

_expression_ A variable that represents a **[Report](Access.Report.md)** object.


## Remarks

The **MinMaxButtons** property uses the following settings.

|Setting|Visual Basic|Description|
|:-----|:-----|:-----|
|None|0|The **Maximize** and **Minimize** buttons aren't visible.|
|Min Enabled|1|Only the **Minimize** button is visible.|
|Max Enabled|2|Only the **Maximize** button is visible.|
|Both Enabled|3|(Default) Both the **Minimize** and **Maximize** buttons are visible.|

You can set the **MinMaxButtons** property only in form Design view.




[!include[Support and feedback](~/includes/feedback-boilerplate.md)]