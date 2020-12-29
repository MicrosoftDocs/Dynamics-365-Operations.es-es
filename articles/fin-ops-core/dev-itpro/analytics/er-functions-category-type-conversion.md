---
title: Lista de funciones ER en la categoría de conversión de tipo
description: Este tema proporciona información sobre las funciones de conversión que son compatibles con los informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 12/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d160c02403bf067ed523fbd634e65c622b522b97
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686084"
---
# <a name="list-of-er-functions-in-the-type-conversion-category"></a><span data-ttu-id="d22e7-103">Lista de funciones ER en la categoría de conversión de tipo</span><span class="sxs-lookup"><span data-stu-id="d22e7-103">List of ER functions in the type conversion category</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d22e7-104">Las funciones de conversión de tipo de informe electrónico (ER) se pueden usar para convertir valores entre tipos.</span><span class="sxs-lookup"><span data-stu-id="d22e7-104">Electronic reporting (ER) type conversion functions can be used to convert values between types.</span></span> <span data-ttu-id="d22e7-105">Este tema proporciona un resumen de estas funciones.</span><span class="sxs-lookup"><span data-stu-id="d22e7-105">This topic provides a summary of these functions.</span></span>

## <a name="type-conversion-functions"></a><span data-ttu-id="d22e7-106">Funciones de conversión de tipos</span><span class="sxs-lookup"><span data-stu-id="d22e7-106">Type conversion functions</span></span>

| <span data-ttu-id="d22e7-107">Función</span><span class="sxs-lookup"><span data-stu-id="d22e7-107">Function</span></span> | <span data-ttu-id="d22e7-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="d22e7-108">Description</span></span> |
|----------|-------------|
| [<span data-ttu-id="d22e7-109">Int64Value</span><span class="sxs-lookup"><span data-stu-id="d22e7-109">Int64Value</span></span>](er-functions-conversion-int64value.md)   | <span data-ttu-id="d22e7-110">Esta función devuelve un valor *Int64* que representa la cadena especificada.</span><span class="sxs-lookup"><span data-stu-id="d22e7-110">This function returns an *Int64* value that represents the specified string.</span></span> |
| [<span data-ttu-id="d22e7-111">IntValue</span><span class="sxs-lookup"><span data-stu-id="d22e7-111">IntValue</span></span>](er-functions-conversion-intvalue.md)       | <span data-ttu-id="d22e7-112">Esta función devuelve un valor *Int* que representa la cadena especificada.</span><span class="sxs-lookup"><span data-stu-id="d22e7-112">This function returns an *Int* value that represents the specified string.</span></span> |
| [<span data-ttu-id="d22e7-113">NumberValue</span><span class="sxs-lookup"><span data-stu-id="d22e7-113">NumberValue</span></span>](er-functions-conversion-numbervalue.md) | <span data-ttu-id="d22e7-114">Esta función devuelve un valor *Real* que se convierte del valor *Cadena* especificado.</span><span class="sxs-lookup"><span data-stu-id="d22e7-114">This function returns a *Real* value that is converted from the specified *String* value.</span></span> <span data-ttu-id="d22e7-115">Durante la conversión, se consideran los separadores de agrupación decimal y de dígitos especificados.</span><span class="sxs-lookup"><span data-stu-id="d22e7-115">During the conversion, the specified decimal and digit grouping separators are considered.</span></span> |
| [<span data-ttu-id="d22e7-116">Valor</span><span class="sxs-lookup"><span data-stu-id="d22e7-116">Value</span></span>](er-functions-conversion-value.md)             | <span data-ttu-id="d22e7-117">Esta función devuelve un valor *Real* que se convierte del valor *Cadena* especificado.</span><span class="sxs-lookup"><span data-stu-id="d22e7-117">This function returns a *Real* value that is converted from the specified *String* value.</span></span> |

## <a name="type-conversion-functions-in-the-date-and-time-category"></a><span data-ttu-id="d22e7-118">Funciones de conversión de tipo en la categoría hora y fecha</span><span class="sxs-lookup"><span data-stu-id="d22e7-118">Type conversion functions in the date and time category</span></span>

<span data-ttu-id="d22e7-119">La siguiente tabla describe las funciones de conversión de tipos en la [categoría de fecha y hora](er-functions-category-datetime.md).</span><span class="sxs-lookup"><span data-stu-id="d22e7-119">The following table describes the type conversion functions in the [date and time category](er-functions-category-datetime.md).</span></span>

| <span data-ttu-id="d22e7-120">Función</span><span class="sxs-lookup"><span data-stu-id="d22e7-120">Function</span></span> | <span data-ttu-id="d22e7-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="d22e7-121">Description</span></span> |
|----------|-------------|
| [<span data-ttu-id="d22e7-122">DateTimeValue</span><span class="sxs-lookup"><span data-stu-id="d22e7-122">DateTimeValue</span></span>](er-functions-datetime-datetimevalue.md)   | <span data-ttu-id="d22e7-123">Esta función devuelve un valor *Fecha y hora* que se convierte de un determinado valor *Cadena* en el formato especificado y en una cultura opcionalmente especificada a un valor de fecha / hora.</span><span class="sxs-lookup"><span data-stu-id="d22e7-123">This function returns a *DateTime* value that is converted from a given *String* value in the specified format and in an optionally specified culture to a date/time value.</span></span> |
| [<span data-ttu-id="d22e7-124">DateToDateTime</span><span class="sxs-lookup"><span data-stu-id="d22e7-124">DateToDateTime</span></span>](er-functions-datetime-datetodatetime.md) | <span data-ttu-id="d22e7-125">Esta función devuelve un valor *Fecha y hora* que se convierte de un determinado valor *Fecha* a un valor de fecha / hora en hora universal coordinada (hora meridiano de Greenwich \[GMT \]).</span><span class="sxs-lookup"><span data-stu-id="d22e7-125">This function returns a *DateTime* value that is converted from a given *Date* value to a date/time value in Coordinated Universal Time (Greenwich Mean Time \[GMT\]).</span></span> |
| [<span data-ttu-id="d22e7-126">DateValue</span><span class="sxs-lookup"><span data-stu-id="d22e7-126">DateValue</span></span>](er-functions-datetime-datevalue.md)           | <span data-ttu-id="d22e7-127">Esta función devuelve un valor *Fecha* que se convierte de un determinado valor *Cadena* en el formato especificado y en una cultura opcionalmente especificada a un valor de fecha / hora.</span><span class="sxs-lookup"><span data-stu-id="d22e7-127">This function returns a *Date* value that is converted from a given *String* value in the specified format and in an optionally specified culture to a date value.</span></span> |

## <a name="type-conversion-functions-in-the-list-category"></a><span data-ttu-id="d22e7-128">Funciones de conversión de tipo en la categoría lista</span><span class="sxs-lookup"><span data-stu-id="d22e7-128">Type conversion functions in the list category</span></span>

<span data-ttu-id="d22e7-129">La siguiente tabla describe las funciones de conversión de tipos en la [categoría lista](er-functions-category-list.md).</span><span class="sxs-lookup"><span data-stu-id="d22e7-129">The following table describes the type conversion functions in the [list category](er-functions-category-list.md).</span></span>

| <span data-ttu-id="d22e7-130">Función</span><span class="sxs-lookup"><span data-stu-id="d22e7-130">Function</span></span> | <span data-ttu-id="d22e7-131">Descripción</span><span class="sxs-lookup"><span data-stu-id="d22e7-131">Description</span></span> |
|----------|-------------|
| [<span data-ttu-id="d22e7-132">Lista</span><span class="sxs-lookup"><span data-stu-id="d22e7-132">List</span></span>](er-functions-list-list.md)                 | <span data-ttu-id="d22e7-133">Esta función devuelve un valor *Lista de registros* como una lista nueva creada a partir de los argumentos especificados del tipo *Contenedor (registro)*.</span><span class="sxs-lookup"><span data-stu-id="d22e7-133">This function returns a *Record list* value as a new list that is created from specified arguments of the *Container (record)* type.</span></span> |
| [<span data-ttu-id="d22e7-134">ListOfFields</span><span class="sxs-lookup"><span data-stu-id="d22e7-134">ListOfFields</span></span>](er-functions-list-listoffields.md) | <span data-ttu-id="d22e7-135">Esta función devuelve un valor *Lista de registros* que se crea en función de la estructura del argumento determinado del tipo *Enumeración* o *Contenedor (registro)*.</span><span class="sxs-lookup"><span data-stu-id="d22e7-135">This function returns a *Record list* value that is created based on the structure of a given argument of the *Enumeration* or *Container (record)* type.</span></span> |
| [<span data-ttu-id="d22e7-136">Dividir</span><span class="sxs-lookup"><span data-stu-id="d22e7-136">Split</span></span>](er-functions-list-split.md)               | <span data-ttu-id="d22e7-137">Esta función divide el valor *Cadena* especificado en subcadenas y devuelve el resultado como un valor *Lista de registros* nuevo.</span><span class="sxs-lookup"><span data-stu-id="d22e7-137">This function splits the specified *String* value into substrings and returns the result as a new *Record list* value.</span></span> |
| [<span data-ttu-id="d22e7-138">StringJoin</span><span class="sxs-lookup"><span data-stu-id="d22e7-138">StringJoin</span></span>](er-functions-list-stringjoin.md)     | <span data-ttu-id="d22e7-139">Esta función devuelve un valor *Cadena* que consta de valores concatenados del campo especificado del valor *Lista de registros* especificado.</span><span class="sxs-lookup"><span data-stu-id="d22e7-139">This function returns a *String* value that consists of concatenated values of the specified field from the specified *Record list* value.</span></span> <span data-ttu-id="d22e7-140">Los valores pueden estar separados por el delimitador especificado.</span><span class="sxs-lookup"><span data-stu-id="d22e7-140">The values can be separated by the specified delimiter.</span></span> |

## <a name="type-conversion-functions-in-the-text-category"></a><span data-ttu-id="d22e7-141">Funciones de conversión de tipo en la categoría texto</span><span class="sxs-lookup"><span data-stu-id="d22e7-141">Type conversion functions in the text category</span></span>

<span data-ttu-id="d22e7-142">La siguiente tabla describe las funciones de conversión de tipos en la [categoría texto](er-functions-category-text.md).</span><span class="sxs-lookup"><span data-stu-id="d22e7-142">The following table describes the type conversion functions in the [text category](er-functions-category-text.md).</span></span>

| <span data-ttu-id="d22e7-143">Función</span><span class="sxs-lookup"><span data-stu-id="d22e7-143">Function</span></span> | <span data-ttu-id="d22e7-144">Descripción</span><span class="sxs-lookup"><span data-stu-id="d22e7-144">Description</span></span> |
|----------|-------------|
| [<span data-ttu-id="d22e7-145">Char</span><span class="sxs-lookup"><span data-stu-id="d22e7-145">Char</span></span>](er-functions-text-char.md)                 | <span data-ttu-id="d22e7-146">Esta función devuelve un valor *String* que representa un solo carácter al que hace referencia el número Unicode especificado.</span><span class="sxs-lookup"><span data-stu-id="d22e7-146">This function returns a *String* value that represents a single character that is referenced by the specified Unicode number.</span></span> |
| [<span data-ttu-id="d22e7-147">GuidValue</span><span class="sxs-lookup"><span data-stu-id="d22e7-147">GuidValue</span></span>](er-functions-text-guidvalue.md)       | <span data-ttu-id="d22e7-148">Esta función convierte la entrada especificada del tipo *Cadena* a un elemento de datos del tipo *GUID*.</span><span class="sxs-lookup"><span data-stu-id="d22e7-148">This function converts the specified input of the *String* type to a data item of the *GUID* type.</span></span> |
| [<span data-ttu-id="d22e7-149">NumberFormat</span><span class="sxs-lookup"><span data-stu-id="d22e7-149">NumberFormat</span></span>](er-functions-text-numberformat.md) | <span data-ttu-id="d22e7-150">Esta función devuelve un valor *Cadena* que representa el número especificado en el formato especificado y en una cultura opcional especificada.</span><span class="sxs-lookup"><span data-stu-id="d22e7-150">This function returns a *String* value that represents the specified number in the specified format and in an optionally specified culture.</span></span> |
| [<span data-ttu-id="d22e7-151">QrCode</span><span class="sxs-lookup"><span data-stu-id="d22e7-151">QrCode</span></span>](er-functions-text-qrcode.md)             | <span data-ttu-id="d22e7-152">Esta función devuelve un valor *Contenedor* que presenta la imagen del código de Respuesta rápida (código QR) para la cadena especificada en formato binario.</span><span class="sxs-lookup"><span data-stu-id="d22e7-152">This function returns a *Container* value that presents the Quick Response code (QR code) image for the specified string in binary format.</span></span> |
| [<span data-ttu-id="d22e7-153">Texto</span><span class="sxs-lookup"><span data-stu-id="d22e7-153">Text</span></span>](er-functions-text-text.md)                 | <span data-ttu-id="d22e7-154">Esta función devuelve un valor *Cadena* que representa al número especificado después de que se haya convertido en una cadena de texto que se formatea según la configuración regional del servidor de la instancia actual de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d22e7-154">This function returns a *String* value that represents the specified number after it has been converted to a text string that is formatted according to the server locale settings of the current application instance.</span></span> |

## <a name="additional-resources"></a><span data-ttu-id="d22e7-155">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="d22e7-155">Additional resources</span></span>

[<span data-ttu-id="d22e7-156">Visión general de los informes electrónicos</span><span class="sxs-lookup"><span data-stu-id="d22e7-156">Electronic Reporting overview</span></span>](general-electronic-reporting.md)

[<span data-ttu-id="d22e7-157">Diseñador de fórmulas en los informes electrónicos</span><span class="sxs-lookup"><span data-stu-id="d22e7-157">Formula designer in Electronic reporting</span></span>](general-electronic-reporting-formula-designer.md)

[<span data-ttu-id="d22e7-158">Idioma de fórmulas en los informes electrónicos</span><span class="sxs-lookup"><span data-stu-id="d22e7-158">Electronic reporting formula language</span></span>](er-formula-language.md)
