---
title: Event.Application property (Visio)
keywords: vis_sdr.chm12613090
f1_keywords:
- vis_sdr.chm12613090
ms.prod: visio
api_name:
- Visio.Event.Application
ms.assetid: 1262cbe7-99f1-936a-b1d5-b9cd2cc7f68e
ms.date: 06/08/2017
ms.localizationpriority: medium
---


# Event.Application property (Visio)

Returns the instance of Microsoft Visio that is associated with an object. Read-only.


## Syntax

_expression_.**Application**

_expression_ A variable that represents an **[Event](Visio.Event.md)** object.


## Return value

**[Application](visio.application.md)**


## Example

The following Microsoft Visual Basic for Applications (VBA) macro gets the **Application** object associated with the active document and prints its process ID number in the Immediate window.


```vb
 
Public Sub Application_Example() 
 
 Dim vsoApplication As Visio.Application 
 Dim vsoDocument As Visio.Document 
 
 Set vsoDocument = ActiveDocument 
 
 'Get the instance of Visio associated with the Document object. 
 Set vsoApplication = vsoDocument.Application 
 Debug.Print "The process ID of the Application object associated with the active document is: " & vsoApplication.ProcessID 
 
End Sub
```

[!include[Support and feedback](~/includes/feedback-boilerplate.md)]