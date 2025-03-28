---
title: OptionButton.ColumnHidden property (Access)
keywords: vbaac10.chm10597
f1_keywords:
- vbaac10.chm10597
ms.prod: access
api_name:
- Access.OptionButton.ColumnHidden
ms.assetid: 962a7bf7-8898-d2e5-f26a-691b8c9b5d71
ms.date: 02/20/2019
ms.localizationpriority: medium
---


# OptionButton.ColumnHidden property (Access)

Use the **ColumnHidden** property to show or hide a specified column in Datasheet view. Read/write **Boolean**.


## Syntax

_expression_.**ColumnHidden**

_expression_ A variable that represents an **[OptionButton](Access.OptionButton.md)** object.


## Remarks

For example, you might want to hide a **CustomerAddress** field that's too wide so that you can view the **CustomerName** and **PhoneNumber** fields.

The **ColumnHidden** property applies to all fields in Datasheet view and to form controls when the form is in Datasheet view.

Hiding a column with the **ColumnHidden** property in Datasheet view doesn't hide fields from the same column in Form view. Similarly, setting a control's **Visible** property to **False** in Form view doesn't hide the corresponding column in Datasheet view.

> [!NOTE] 
> To set or change this property for a table or query by using Visual Basic, you must use a column's **Properties** collection. For more information about using the **Properties** collection, see **[Properties](Access.OptionButton.properties.md)**.

You can display a field in a query even though the column for the field is hidden in table Datasheet view. Use values from a hidden column as the criteria for a filter even though the column remains hidden after the filter is applied.

Setting a field's **ColumnWidth** property to 0, or resizing the field to a zero width in Datasheet view, causes Microsoft Access to set the corresponding **ColumnHidden** property to **True**. Unhiding a column restores the **ColumnWidth** property to the value it had before the field was hidden.

The **ColumnHidden** property is not available in Design view.


## Example

The following example hides the **ProductID** field in Datasheet view of the **Products** form.

```vb
Forms!Products!ProductID.ColumnHidden = -1
```

The next example hides the **ProductID** field in Datasheet view of the **Products** table.

```vb
Public Sub SetColumnHidden() 
 
 Dim dbs As DAO.Database 
 Dim fld As DAO.Field 
 Dim prp As DAO.Property 
 Const conErrPropertyNotFound = 3270 
 
 ' Turn off error trapping. 
 On Error Resume Next 
 
 Set dbs = CurrentDb 
 
 ' Set field property. 
 Set fld = dbs.TableDefs!Products.Fields!ProductID 
 fld.Properties("ColumnHidden") = True 
 
 ' Error may have occurred when value was set. 
 If Err.Number <> 0 Then 
 If Err.Number <> conErrPropertyNotFound Then 
 On Error GoTo 0 
 MsgBox "Couldn't set property 'ColumnHidden' " & _ 
 "on field '" & fld.Name & "'", vbCritical 
 Else 
 On Error GoTo 0 
 Set prp = fld.CreateProperty("ColumnHidden", dbLong, True) 
 fld.Properties.Append prp 
 End If 
 End If 
 
 Set prp = Nothing 
 Set fld = Nothing 
 Set dbs = Nothing 
 
End Sub
```




[!include[Support and feedback](~/includes/feedback-boilerplate.md)]