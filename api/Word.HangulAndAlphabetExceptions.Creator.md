---
title: HangulAndAlphabetExceptions.Creator property (Word)
keywords: vbawd10.chm164692969
f1_keywords:
- vbawd10.chm164692969
ms.prod: word
api_name:
- Word.HangulAndAlphabetExceptions.Creator
ms.assetid: 5d664952-732c-cb5a-66b6-01ce3572c983
ms.date: 06/08/2017
ms.localizationpriority: medium
---


# HangulAndAlphabetExceptions.Creator property (Word)

Returns a 32-bit integer that indicates the application in which the specified object was created. Read-only **Long**.


## Syntax

_expression_.**Creator**

_expression_ Required. A variable that represents a '[HangulAndAlphabetExceptions](Word.hangulandalphabetexceptions.md)' collection.


## Remarks

If the object was created in Microsoft Word, the **Creator** property returns the hexadecimal number 4D535744, which represents the string "MSWD." This property was primarily designed to be used on the Macintosh, where each application has a four-character creator code. For example, Microsoft Word has the creator code MSWD. For additional information about this property, consult the language reference Help included with Microsoft Office Macintosh Edition.


## See also


[HangulAndAlphabetExceptions Collection Object](Word.hangulandalphabetexceptions.md)

[!include[Support and feedback](~/includes/feedback-boilerplate.md)]