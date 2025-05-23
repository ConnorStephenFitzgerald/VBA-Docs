---
title: Form.Recordset property (Access)
keywords: vbaac10.chm13497
f1_keywords:
- vbaac10.chm13497
ms.prod: access
api_name:
- Access.Form.Recordset
ms.assetid: baf6c8c4-b4ac-8618-ecbf-4444ae5e88d4
ms.date: 03/02/2019
ms.localizationpriority: medium
---


# Form.Recordset property (Access)

Returns or sets the ADO **Recordset** or DAO **Recordset** object that represents the record source for the specified object. Read/write **Object**.


## Syntax

_expression_.**Recordset**

_expression_ A variable that represents a **[Form](Access.Form.md)** object.


## Remarks

The **Recordset** property returns the **Recordset** object that provides the data being browsed in a form, report, list box control, or combo box control. If a form is based on a query, for example, referring to the **Recordset** property is the equivalent of cloning a **Recordset** object by using the same query. However, unlike using the **RecordsetClone** property, changing which record is current in the recordset returned by the form's **Recordset** property also sets the current record of the form.

The read/write behavior of the **Recordset** property is determined by the type of recordset (ADO or DAO) and the type of data (Access or SQL) contained in the recordset identified by the property.

|Recordset type|Based on SQL data|Based on data stored by the Access database engine|
|:-----|:-----|:-----|
|**ADO**|Read/write|Read/write|
|**DAO**|N/A|Read/write|

The following example opens a form, opens a recordset, and then binds the form to the recordset by setting the form's **Recordset** property to the newly created **Recordset** object.

```vb
Global rstSuppliers As ADODB.Recordset 
Sub MakeRW()      
    DoCmd.OpenForm "Suppliers" 
    Set rstSuppliers = New ADODB.Recordset 
    rstSuppliers.CursorLocation = adUseClient 
    rstSuppliers.Open "Select * From Suppliers", _ 
         CurrentProject.Connection, adOpenKeyset, adLockOptimistic      
    Set Forms("Suppliers").Recordset = rstSuppliers 
End Sub
```

Use the **Recordset** property to:

- Use methods with the **Recordset** object that aren't directly supported on forms. For example, you can use the **Recordset** property with the ADO **Find** or DAO **Find** methods in a custom dialog for finding a record.
    
- Wrap a transaction (which can be rolled back) around a set of edits that affect multiple forms.
    
  Changing a form's **Recordset** property may also change the **RecordSource**, **RecordsetType**, and **RecordLocks** properties. Also, some data-related properties may be overridden, for example, the **Filter**, **FilterOn**, **OrderBy**, and **OrderByOn** properties.

  Calling the **Requery** method of a form's recordset (for example, `Forms(0).Recordset.Requery`) can cause the form to become unbound. To refresh the data in a form bound to a recordset, set the **RecordSource** property of the form to itself: `Forms(0).RecordSource = Forms(0).RecordSource`.

- Bind multiple forms to a common data set. This allows synchronization of multiple forms. For example:
    
  ```vb
    Set Me.Recordset = Forms!Form1.Recordset
  ```

> [!NOTE] 
> When a form is bound to a recordset, an error occurs if you use the **Filter by Form** command.


## Example

The following example uses the **Recordset** property to create a new copy of the **Recordset** object from the current form and then prints the names of the fields in the Debug window.

```vb
Sub Print_Field_Names() 
    Dim rst As DAO.Recordset, intI As Integer 
    Dim fld As Field 
 
    Set rst = Me.Recordset 
    For Each fld in rst.Fields 
        ' Print field names. 
        Debug.Print fld.Name 
    Next 
End Sub
```

The following example uses the **Recordset** property and the **Recordset** object to synchronize a recordset with the form's current record. When a company name is selected from a combo box, the **FindFirst** method is used to locate the record for that company, causing the form to display the found record.

```vb
Sub SupplierID_AfterUpdate() 
    Dim rst As DAO.Recordset 
    Dim strSearchName As String 
 
    Set rst = Me.Recordset 
    strSearchName = CStr(Me!SupplierID) 
    rst.FindFirst "SupplierID = " & strSearchName 
    If rst.NoMatch Then 
        MsgBox "Record not found" 
    End If 
    rst.Close 
End Sub
```

The following code helps to determine what type of recordset is returned by the **Recordset** property under different conditions.

```vb
Sub CheckRSType() 
    Dim rs as Object 
 
    Set rs=Forms(0).Recordset 
    If TypeOf rs Is DAO.Recordset Then 
        MsgBox "DAO Recordset" 
    ElseIf TypeOf rs is ADODB.Recordset Then 
        MsgBox "ADO Recordset" 
    End If 
End Sub
```



[!include[Support and feedback](~/includes/feedback-boilerplate.md)]
