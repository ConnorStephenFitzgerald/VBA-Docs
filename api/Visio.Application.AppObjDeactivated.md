---
title: Application.AppObjDeactivated event (Visio)
ms.prod: visio
api_name:
- Visio.Application.AppObjDeactivated
ms.assetid: 0a401a6e-6aee-3175-6834-55a828a9c864
ms.date: 06/24/2019
ms.localizationpriority: medium
---


# Application.AppObjDeactivated event (Visio)

Occurs after a Microsoft Visio instance becomes inactive.


## Syntax

_expression_.**AppObjDeactivated** (_app_)

_expression_ A variable that represents an **[Application](Visio.Application.md)** object.


## Parameters

|Name|Required/Optional|Data type|Description|
|:-----|:-----|:-----|:-----|
| _app_|Required| **[IVAPPLICATION]**|The instance of Visio that is no longer the active instance.|

## Remarks

The **AppObjDeactivated** event indicates that the instance of Visio is no longer the active instance of Visio (the instance of Visio that is retrieved by the **GetObject** method in a Microsoft Visual Basic program). The **AppObjDeactivated** event is different from the **AppDeactivated** event, which occurs after an instance of Visio is no longer the active instance on the Microsoft Windows desktop.

If you are using Microsoft Visual Basic or Visual Basic for Applications (VBA), the syntax in this topic describes a common, efficient way to handle events.

If you want to create your own **Event** objects, use the **[Add](visio.eventlist.add.md)** or **[AddAdvise](visio.eventlist.addadvise.md)** method. 

To create an **Event** object that runs an add-on, use the **Add** method as it applies to the **EventList** collection. 

To create an **Event** object that receives notification, use the **AddAdvise** method. 

To find an event code for the event that you want to create, see [Event codes](../visio/Concepts/event-codesvisio.md).


[!include[Support and feedback](~/includes/feedback-boilerplate.md)]