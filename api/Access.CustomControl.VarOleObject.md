---
title: CustomControl.VarOleObject property (Access)
keywords: vbaac10.chm10954
f1_keywords:
- vbaac10.chm10954
ms.prod: access
api_name:
- Access.CustomControl.VarOleObject
ms.assetid: 7de5433c-a2da-bb8e-35d2-9c7aae1ff2cd
ms.date: 03/06/2019
ms.localizationpriority: medium
---


# CustomControl.VarOleObject property (Access)

Gets a pointer to an **IOLEObject** that represents the memory address of an OLE object. Read-only **Variant**.


## Syntax

_expression_.**VarOleObject**

_expression_ A variable that represents a **[CustomControl](Access.CustomControl.md)** object.


## Remarks

> [!NOTE] 
> The **VarOleObject** property is compatible with 32-bit and 64-bit OLE objects. It replaces the **LpOLEObject**, which was available in earlier versions of Microsoft Access.

Use the **VarOleObject** property to refer to the address of the active OLE object. If no object is displayed, the setting is 0.

This property setting is not available in Design view and is read-only in other views.

In the OLE dynamic link libraries (DLLs), many function calls require the address of the OLE object as an argument. You can pass the value specified by the **VarOleObject** property when you make application programming interface (API) calls to the OLE DLLs.

If an API call is made to a function that performs a callback to the control, the results are unpredictable.




[!include[Support and feedback](~/includes/feedback-boilerplate.md)]