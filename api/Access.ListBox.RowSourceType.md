---
title: ListBox.RowSourceType property (Access)
keywords: vbaac10.chm11222
f1_keywords:
- vbaac10.chm11222
ms.prod: access
api_name:
- Access.ListBox.RowSourceType
ms.assetid: a98a44d4-b2a5-d591-9295-3222d708ee88
ms.date: 03/02/2019
ms.localizationpriority: medium
---


# ListBox.RowSourceType property (Access)

Use the **RowSourceType** property (along with the **RowSource** property) to tell Microsoft Access how to provide data to the specified object. Read/write **String**.


## Syntax

_expression_.**RowSourceType**

_expression_ A variable that represents a **[ListBox](Access.ListBox.md)** object.


## Remarks

The **RowSourceType** property uses the following settings.

|Setting|Description|
|:-----|:-----|
|Table/Query|(Default) The data is from a table, query, or SQL statement specified by the **RowSource** setting.|
|Value List|The data is a list of items specified by the **RowSource** setting.|
|Field List|The data is a list of field names from a table, query, or SQL statement specified by the **RowSource** setting.|

> [!NOTE] 
> You can also set the **RowSourceType** property with a user-defined function. The function name is entered without a preceding equal sign (=) and without the trailing pair of parentheses. You must provide [specific function code arguments](Access.RowSourceType.md) to tell Access how to fill the control. 

In Visual Basic, set the **RowSourceType** property by using a string expression with one of these values: "Table/Query", "Value List", or "Field List". You also use a string expression to set the value of the **RowSource** property. To set the **RowSourceType** property to a user-defined function, enter the name of the function.

When you have a limited number of values that don't change, you can set the **RowSourceType** property to Value List and then enter the values that make up the list in the **RowSource** property.

When you create a user-defined function to insert items into a list box or combo box, Access calls the function repeatedly to get the information it needs. User-defined **RowSourceType** functions must be written in a very specific [function format](Access.RowSourceType.md).


## Example

The following example sets the **RowSourceType** property for a combo box to Table/Query, and it sets the **RowSource** property to a query named EmployeeList.

```vb
Forms!Employees!cmboNames.RowSourceType = "Table/Query" 
Forms!Employees!cmboNames.RowSource = "EmployeeList"
```



[!include[Support and feedback](~/includes/feedback-boilerplate.md)]
