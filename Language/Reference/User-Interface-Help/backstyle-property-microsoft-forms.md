---
title: BackStyle property (Microsoft Forms)
keywords: fm20.chm5225007
f1_keywords:
- fm20.chm5225007
ms.prod: office
ms.assetid: 65930aae-92c1-0cd8-2bed-d657321151e7
ms.date: 11/15/2018
ms.localizationpriority: medium
---


# BackStyle property (Microsoft Forms)

Returns or sets the background style for an object.

## Syntax

_object_.**BackStyle** [= _fmBackStyle_ ]

The **BackStyle** property syntax has these parts:

|Part|Description|
|:-----|:-----|
| _object_|Required. A valid object.|
| _fmBackStyle_|Optional. Specifies the control background.|

## Settings

The settings for _fmBackStyle_ are:

|Constant|Value|Description|
|:-----|:-----|:-----|
| _fmBackStyleTransparent_|0|The background is transparent.|
| _fmBackStyleOpaque_|1|The background is opaque (default).|

## Remarks

The **BackStyle** property determines whether a control is [transparent](../../Glossary/glossary-vba.md#transparent). If **BackStyle** is **fmBackStyleOpaque**, the control is not transparent and you cannot see anything behind the control on a form. If **BackStyle** is **fmBackStyleTransparent**, you can see through the control and look at anything on the form located behind the control.

> [!NOTE] 
> **BackStyle** does not affect the transparency of bitmaps. You must use a picture editor such as Paintbrush to make a bitmap transparent. Not all controls support transparent bitmaps.

## See also

- [Microsoft Forms examples](examples-microsoft-forms.md)
- [Microsoft Forms reference](reference-microsoft-forms.md)
- [Microsoft Forms concepts](concepts-microsoft-forms.md)

[!include[Support and feedback](~/includes/feedback-boilerplate.md)]