---
title: AllModules.Item property (Access)
keywords: vbaac10.chm12680
f1_keywords:
- vbaac10.chm12680
ms.prod: access
api_name:
- Access.AllModules.Item
ms.assetid: 9dfffe9b-afb2-a7e8-04f4-fbedb12a14a9
ms.date: 02/01/2019
ms.localizationpriority: medium
---


# AllModules.Item property (Access)

The **Item** property returns a specific member of a collection either by position or by index. Read-only **AccessObject**.


## Syntax

_expression_.**Item** (_var_)

_expression_ A variable that represents an **[AllModules](Access.AllModules.md)** object.


## Parameters

|Name|Required/Optional|Data type|Description|
|:-----|:-----|:-----|:-----|
| _var_|Required|**Variant**|An expression that specifies the position of a member of the collection referred to by the _expression_ argument.<br/><br/>If a numeric expression, the _index_ argument must be a number from 0 to the value of the collection's **Count** property minus 1.<br/><br/>If a string expression, the _index_ argument must be the name of a member of the collection.|

## Remarks

If the value provided for the _index_ argument doesn't match any existing member of the collection, an error occurs.

The **Item** property is the default member of a collection, so you don't have to specify it explicitly. For example, the following two lines of code are equivalent.

```vb
Debug.Print Modules(0)
```


```vb
Debug.Print Modules.Item(0)
```




[!include[Support and feedback](~/includes/feedback-boilerplate.md)]