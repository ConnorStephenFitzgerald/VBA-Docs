---
title: Application.EndUndoScope method (Visio)
keywords: vis_sdr.chm10016250
f1_keywords:
- vis_sdr.chm10016250
ms.prod: visio
api_name:
- Visio.Application.EndUndoScope
ms.assetid: 352188d2-8a2a-1a6d-674e-93fce9245810
ms.date: 06/26/2019
ms.localizationpriority: medium
---


# Application.EndUndoScope method (Visio)

Ends or cancels a transaction that has a unique scope.


## Syntax

_expression_.**EndUndoScope** (_nScopeID_, _bCommit_)

_expression_ A variable that represents an **[Application](Visio.Application.md)** object.


## Parameters

|Name|Required/Optional|Data type|Description|
|:-----|:-----|:-----|:-----|
| _nScopeID_|Required| **Long**|The ID of the scope to close.|
| _bCommit_|Required| **Boolean**| A flag indicating that the changes made during the scope should be accepted (**True**) or canceled (**False**).|

## Return value

Nothing


## Remarks

If you need to know whether events you receive are the result of a particular operation that you initiated, use the **BeginUndoScope** and **EndUndoScope** methods to wrap your operation. In your event handlers, use the **IsInScope** property to test whether the scope ID returned by the **BeginUndoScope** method is part of the current context. Make sure that you clear the scope ID that you stored from the **BeginUndoScope** property when you receive the **ExitScope** event with that ID.

You must balance calls to the **BeginUndoScope** method with calls to the **EndUndoScope** method. If you call the **BeginUndoScope** method, you should call the **EndUndoScope** method as soon as you are done with the actions that constitute your scope. Also, while actions to multiple documents should be robust within a single scope, closing a document may have the side effect of clearing the undo information for the currently open scope as well as clearing the undo and redo stacks. If that happens, passing _bCommit_ = **False** to **EndUndoScope** does not restore the undo information.

You can also use the **BeginUndoScope** and **EndUndoScope** methods to add an action defined by an add-on to the Microsoft Visio undo stream. This is useful when you are operating from modeless scenarios where the initiating agent is part of an add-on's user interface or a modeless programmatic action.

> [!NOTE] 
> Most Visio actions are already wrapped in internal undo scopes, so add-ons running within the application don't need to call this method.

If your Visual Studio solution includes the [Microsoft.Office.Interop.Visio](https://docs.microsoft.com/visualstudio/vsto/office-primary-interop-assemblies?view=vs-2019) reference, this method maps to the following type:

- **Microsoft.Office.Interop.Visio.IVApplication.EndUndoScope(int, bool)**
    

## Example

This example shows how to use the **EndUndoScope** method to end a transaction that has a unique scope ID for an instance of Visio.

```vb
 
Private WithEvents vsoApplication As Visio.Application  
Private lngScopeID As Long 
     
Public Sub EndUndoScope_Example()  
 
    Dim vsoShape As Visio.Shape  
 
    'Set the module-level application variable to  
    'trap Application-level events.  
    Set vsoApplication = Visio.Application  
 
    'Begin a scope and set the module-level variable.  
    lngScopeID = vsoApplication.BeginUndoScope("Draw Shapes")  
 
    'Draw three shapes.  
    Set vsoShape = ActivePage.DrawRectangle(1, 2, 2, 1) 
  
    ActivePage.DrawOval 3, 4, 4, 3  
    ActivePage.DrawLine 4, 5, 5, 4  
 
    'Change a cell to trigger a CellChanged event.  
    vsoShape.Cells("Width").Formula = 5  
 
    'End and commit this scope.  
    vsoApplication.EndUndoScope lngScopeID, True  
 
End Sub    
 
Private Sub vsoApplication_CellChanged(ByVal Cell As IVCell)  
 
    'Check to see if this cell change is the result of something  
    'happening within the scope.  
    If vsoApplication.IsInScope(lngScopeID) Then  
        Debug.Print Cell.Name & " changed in scope "; lngScopeID  
    End If 
   
End Sub   
 
Private Sub vsoApplication_EnterScope(ByVal app As IVApplication, _  
    ByVal nScopeID As Long, _  
    ByVal bstrDescription As 
     String)  
 
    If vsoApplication.CurrentScope = lngScopeID Then  
        Debug.Print "Entering my scope " & nScopeID  
    Else  
        Debug.Print "Enter Scope " & bstrDescription & "(" & nScopeID & ")"  
    End If 
   
End Sub   
 
Private Sub vsoApplication_ExitScope(ByVal app As IVApplication, _  
    ByVal nScopeID As Long, _  
    ByVal bstrDescription As String, _  
    ByVal bErrOrCancelled As Boolean)  
 
    If vsoApplication.CurrentScope = lngScopeID Then  
        Debug.Print "Exiting my scope " & nScopeID  
    Else  
        Debug.Print "Exit Scope " & bstrDescription & "(" & nScopeID & ")"  
    End If  
  
End Sub
```

[!include[Support and feedback](~/includes/feedback-boilerplate.md)]