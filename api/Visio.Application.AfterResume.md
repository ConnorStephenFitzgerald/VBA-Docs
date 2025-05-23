---
title: Application.AfterResume event (Visio)
ms.prod: visio
api_name:
- Visio.Application.AfterResume
ms.assetid: 73cac713-6559-ae7c-32a6-5c421302a3d9
ms.date: 06/24/2019
ms.localizationpriority: medium
---


# Application.AfterResume event (Visio)

Occurs when the operating system resumes normal operation after having been suspended.


## Syntax

_expression_.**AfterResume** (_app_)

_expression_ A variable that represents an **[Application](Visio.Application.md)** object.


## Parameters

|Name|Required/Optional|Data type|Description|
|:-----|:-----|:-----|:-----|
| _app_|Required| **[IVAPPLICATION]**|The instance of Visio that resumes after the operating system resumes normal operation.|

## Remarks

Use the **AfterResume** event to reopen any network files that you may have closed in response to the **BeforeSuspend** event.

If your solution runs outside the Microsoft Visio process, you cannot be assured of receiving this event. For this reason, you should monitor window messages in your program.

If you are using Microsoft Visual Basic or Visual Basic for Applications (VBA), the syntax in this topic describes a common, efficient way to handle events.

If you want to create your own **Event** objects, use the **[Add](visio.eventlist.add.md)** or **[AddAdvise](visio.eventlist.addadvise.md)** method. 

To create an **Event** object that runs an add-on, use the **Add** method as it applies to the **EventList** collection. 

To create an **Event** object that receives notification, use the **AddAdvise** method. 

To find an event code for the event that you want to create, see [Event codes](../visio/Concepts/event-codesvisio.md).

[!include[Support and feedback](~/includes/feedback-boilerplate.md)]