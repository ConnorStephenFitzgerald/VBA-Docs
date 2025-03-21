---
title: DefaultWebOptions.Creator property (Word)
keywords: vbawd10.chm165872617
f1_keywords:
- vbawd10.chm165872617
ms.prod: word
api_name:
- Word.DefaultWebOptions.Creator
ms.assetid: a620693e-38bf-5ac5-0240-8d948a33c853
ms.date: 06/08/2017
ms.localizationpriority: medium
---


# DefaultWebOptions.Creator property (Word)

Returns a 32-bit integer that indicates the application in which the specified object was created. Read-only **Long**.


## Syntax

_expression_.**Creator**

_expression_ Required. A variable that represents a **[DefaultWebOptions](Word.DefaultWebOptions.md)** collection.


## Remarks

If the object was created in Microsoft Word, the **Creator** property returns the hexadecimal number 4D535744, which represents the string "MSWD." This property was primarily designed to be used on the Macintosh, where each application has a four-character creator code. For example, Microsoft Word has the creator code MSWD. For additional information about this property, consult the language reference Help included with Microsoft Office Macintosh Edition.


## See also


[DefaultWebOptions Object](Word.DefaultWebOptions.md)

[!include[Support and feedback](~/includes/feedback-boilerplate.md)]