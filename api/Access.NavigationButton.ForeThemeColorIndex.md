---
title: NavigationButton.ForeThemeColorIndex property (Access)
keywords: vbaac10.chm14604
f1_keywords:
- vbaac10.chm14604
ms.prod: access
api_name:
- Access.NavigationButton.ForeThemeColorIndex
ms.assetid: f0d04d84-338a-c45e-6f26-debc1a402796
ms.date: 03/01/2019
ms.localizationpriority: medium
---


# NavigationButton.ForeThemeColorIndex property (Access)

Gets or sets a value that represents a color in the applied color theme associated with the **ForeColor** property of the specified object. Read/write **Long**.


## Syntax

_expression_.**ForeThemeColorIndex**

_expression_ A variable that represents a **[NavigationButton](Access.NavigationButton.md)** object.


## Remarks

The **ForeThemeColorIndex** property contains one of the index values listed in the following table.

|Index Value|Description|
|:-----|:-----|
|0|Text 1|
|1|Background 1|
|2|Text 2|
|3|Background 2|
|4|Accent 1|
|5|Accent 2|
|6|Accent 3|
|7|Accent 4|
|8|Accent 5|
|9|Accent 6|
|10|Hyperlink|
|11|Followed Hyperlink|

If no theme is applied, the **ForeThemeColorIndex** property contains -1.

This property is not surfaced in the property sheet.


## Example

The following code example sets the fore color to the Text 2 color by setting the **ForeThemeColorIndex** property.

```vb
Me.ctl.ForeThemeColorIndex=2
```


[!include[Support and feedback](~/includes/feedback-boilerplate.md)]