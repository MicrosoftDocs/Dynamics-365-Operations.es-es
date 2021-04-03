---
title: Lista de funciones ER en la categoría de conversión de tipo
description: Este tema proporciona información sobre las funciones de conversión que son compatibles con los informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 12/05/2019
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 5613496d3131ccd39b198cac214eb791a6d07355
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "5561527"
---
# <a name="list-of-er-functions-in-the-type-conversion-category"></a><span data-ttu-id="9402d-103">Lista de funciones ER en la categoría de conversión de tipo</span><span class="sxs-lookup"><span data-stu-id="9402d-103">List of ER functions in the type conversion category</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9402d-104">Las funciones de conversión de tipo de informe electrónico (ER) se pueden usar para convertir valores entre tipos.</span><span class="sxs-lookup"><span data-stu-id="9402d-104">Electronic reporting (ER) type conversion functions can be used to convert values between types.</span></span> <span data-ttu-id="9402d-105">Este tema proporciona un resumen de estas funciones.</span><span class="sxs-lookup"><span data-stu-id="9402d-105">This topic provides a summary of these functions.</span></span>

## <a name="type-conversion-functions"></a><span data-ttu-id="9402d-106">Funciones de conversión de tipos</span><span class="sxs-lookup"><span data-stu-id="9402d-106">Type conversion functions</span></span>

| <span data-ttu-id="9402d-107">Función</span><span class="sxs-lookup"><span data-stu-id="9402d-107">Function</span></span> | <span data-ttu-id="9402d-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="9402d-108">Description</span></span> |
|----------|-------------|
| [<span data-ttu-id="9402d-109">Int64Value</span><span class="sxs-lookup"><span data-stu-id="9402d-109">Int64Value</span></span>](er-functions-conversion-int64value.md)   | <span data-ttu-id="9402d-110">Esta función devuelve un valor *Int64* que representa la cadena especificada.</span><span class="sxs-lookup"><span data-stu-id="9402d-110">This function returns an *Int64* value that represents the specified string.</span></span> |
| [<span data-ttu-id="9402d-111">IntValue</span><span class="sxs-lookup"><span data-stu-id="9402d-111">IntValue</span></span>](er-functions-conversion-intvalue.md)       | <span data-ttu-id="9402d-112">Esta función devuelve un valor *Int* que representa la cadena especificada.</span><span class="sxs-lookup"><span data-stu-id="9402d-112">This function returns an *Int* value that represents the specified string.</span></span> |
| [<span data-ttu-id="9402d-113">NumberValue</span><span class="sxs-lookup"><span data-stu-id="9402d-113">NumberValue</span></span>](er-functions-conversion-numbervalue.md) | <span data-ttu-id="9402d-114">Esta función devuelve un valor *Real* que se convierte del valor *Cadena* especificado.</span><span class="sxs-lookup"><span data-stu-id="9402d-114">This function returns a *Real* value that is converted from the specified *String* value.</span></span> <span data-ttu-id="9402d-115">Durante la conversión, se consideran los separadores de agrupación decimal y de dígitos especificados.</span><span class="sxs-lookup"><span data-stu-id="9402d-115">During the conversion, the specified decimal and digit grouping separators are considered.</span></span> |
| [<span data-ttu-id="9402d-116">Valor</span><span class="sxs-lookup"><span data-stu-id="9402d-116">Value</span></span>](er-functions-conversion-value.md)             | <span data-ttu-id="9402d-117">Esta función devuelve un valor *Real* que se convierte del valor *Cadena* especificado.</span><span class="sxs-lookup"><span data-stu-id="9402d-117">This function returns a *Real* value that is converted from the specified *String* value.</span></span> |

## <a name="type-conversion-functions-in-the-container-category"></a><span data-ttu-id="9402d-118">Funciones de conversión de tipo en la categoría de contenedor</span><span class="sxs-lookup"><span data-stu-id="9402d-118">Type conversion functions in the container category</span></span>

<span data-ttu-id="9402d-119">La siguiente tabla describe las funciones de conversión de tipos en la categoría de [contenedor](er-functions-category-container.md).</span><span class="sxs-lookup"><span data-stu-id="9402d-119">The following table describes the type conversion functions in the [container](er-functions-category-container.md) category.</span></span>

| <span data-ttu-id="9402d-120">Función</span><span class="sxs-lookup"><span data-stu-id="9402d-120">Function</span></span> | <span data-ttu-id="9402d-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="9402d-121">Description</span></span> |
|----------|-------------|
| [<span data-ttu-id="9402d-122">Base64StringToContainer</span><span class="sxs-lookup"><span data-stu-id="9402d-122">Base64StringToContainer</span></span>](er-functions-container-base64stringtocontainer.md) | <span data-ttu-id="9402d-123">Esta función convierte la entrada especificada del tipo *Cadena* a un elemento de datos del tipo *Contenedor*.</span><span class="sxs-lookup"><span data-stu-id="9402d-123">This function converts the specified input of the *String* type to a data item of the *Container* type.</span></span> |

## <a name="type-conversion-functions-in-the-date-and-time-category"></a><span data-ttu-id="9402d-124">Funciones de conversión de tipo en la categoría hora y fecha</span><span class="sxs-lookup"><span data-stu-id="9402d-124">Type conversion functions in the date and time category</span></span>

<span data-ttu-id="9402d-125">La siguiente tabla describe las funciones de conversión de tipos en la [categoría de fecha y hora](er-functions-category-datetime.md).</span><span class="sxs-lookup"><span data-stu-id="9402d-125">The following table describes the type conversion functions in the [date and time category](er-functions-category-datetime.md).</span></span>

| <span data-ttu-id="9402d-126">Función</span><span class="sxs-lookup"><span data-stu-id="9402d-126">Function</span></span> | <span data-ttu-id="9402d-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="9402d-127">Description</span></span> |
|----------|-------------|
| [<span data-ttu-id="9402d-128">DateTimeValue</span><span class="sxs-lookup"><span data-stu-id="9402d-128">DateTimeValue</span></span>](er-functions-datetime-datetimevalue.md)   | <span data-ttu-id="9402d-129">Esta función devuelve un valor *Fecha y hora* que se convierte de un determinado valor *Cadena* en el formato especificado y en una cultura opcionalmente especificada a un valor de fecha / hora.</span><span class="sxs-lookup"><span data-stu-id="9402d-129">This function returns a *DateTime* value that is converted from a given *String* value in the specified format and in an optionally specified culture to a date/time value.</span></span> |
| [<span data-ttu-id="9402d-130">DateToDateTime</span><span class="sxs-lookup"><span data-stu-id="9402d-130">DateToDateTime</span></span>](er-functions-datetime-datetodatetime.md) | <span data-ttu-id="9402d-131">Esta función devuelve un valor *Fecha y hora* que se convierte de un determinado valor *Fecha* a un valor de fecha / hora en hora universal coordinada (hora meridiano de Greenwich \[GMT \]).</span><span class="sxs-lookup"><span data-stu-id="9402d-131">This function returns a *DateTime* value that is converted from a given *Date* value to a date/time value in Coordinated Universal Time (Greenwich Mean Time \[GMT\]).</span></span> |
| [<span data-ttu-id="9402d-132">DateValue</span><span class="sxs-lookup"><span data-stu-id="9402d-132">DateValue</span></span>](er-functions-datetime-datevalue.md)           | <span data-ttu-id="9402d-133">Esta función devuelve un valor *Fecha* que se convierte de un determinado valor *Cadena* en el formato especificado y en una cultura opcionalmente especificada a un valor de fecha / hora.</span><span class="sxs-lookup"><span data-stu-id="9402d-133">This function returns a *Date* value that is converted from a given *String* value in the specified format and in an optionally specified culture to a date value.</span></span> |

## <a name="type-conversion-functions-in-the-list-category"></a><span data-ttu-id="9402d-134">Funciones de conversión de tipo en la categoría lista</span><span class="sxs-lookup"><span data-stu-id="9402d-134">Type conversion functions in the list category</span></span>

<span data-ttu-id="9402d-135">La siguiente tabla describe las funciones de conversión de tipos en la [categoría lista](er-functions-category-list.md).</span><span class="sxs-lookup"><span data-stu-id="9402d-135">The following table describes the type conversion functions in the [list category](er-functions-category-list.md).</span></span>

| <span data-ttu-id="9402d-136">Función</span><span class="sxs-lookup"><span data-stu-id="9402d-136">Function</span></span> | <span data-ttu-id="9402d-137">Descripción</span><span class="sxs-lookup"><span data-stu-id="9402d-137">Description</span></span> |
|----------|-------------|
| [<span data-ttu-id="9402d-138">Lista</span><span class="sxs-lookup"><span data-stu-id="9402d-138">List</span></span>](er-functions-list-list.md)                 | <span data-ttu-id="9402d-139">Esta función devuelve un valor *Lista de registros* como una lista nueva creada a partir de los argumentos especificados del tipo *Contenedor (registro)*.</span><span class="sxs-lookup"><span data-stu-id="9402d-139">This function returns a *Record list* value as a new list that is created from specified arguments of the *Container (record)* type.</span></span> |
| [<span data-ttu-id="9402d-140">ListOfFields</span><span class="sxs-lookup"><span data-stu-id="9402d-140">ListOfFields</span></span>](er-functions-list-listoffields.md) | <span data-ttu-id="9402d-141">Esta función devuelve un valor *Lista de registros* que se crea en función de la estructura del argumento determinado del tipo *Enumeración* o *Contenedor (registro)*.</span><span class="sxs-lookup"><span data-stu-id="9402d-141">This function returns a *Record list* value that is created based on the structure of a given argument of the *Enumeration* or *Container (record)* type.</span></span> |
| [<span data-ttu-id="9402d-142">Dividir</span><span class="sxs-lookup"><span data-stu-id="9402d-142">Split</span></span>](er-functions-list-split.md)               | <span data-ttu-id="9402d-143">Esta función divide el valor *Cadena* especificado en subcadenas y devuelve el resultado como un valor *Lista de registros* nuevo.</span><span class="sxs-lookup"><span data-stu-id="9402d-143">This function splits the specified *String* value into substrings and returns the result as a new *Record list* value.</span></span> |
| [<span data-ttu-id="9402d-144">StringJoin</span><span class="sxs-lookup"><span data-stu-id="9402d-144">StringJoin</span></span>](er-functions-list-stringjoin.md)     | <span data-ttu-id="9402d-145">Esta función devuelve un valor *Cadena* que consta de valores concatenados del campo especificado del valor *Lista de registros* especificado.</span><span class="sxs-lookup"><span data-stu-id="9402d-145">This function returns a *String* value that consists of concatenated values of the specified field from the specified *Record list* value.</span></span> <span data-ttu-id="9402d-146">Los valores pueden estar separados por el delimitador especificado.</span><span class="sxs-lookup"><span data-stu-id="9402d-146">The values can be separated by the specified delimiter.</span></span> |

## <a name="type-conversion-functions-in-the-text-category"></a><span data-ttu-id="9402d-147">Funciones de conversión de tipo en la categoría texto</span><span class="sxs-lookup"><span data-stu-id="9402d-147">Type conversion functions in the text category</span></span>

<span data-ttu-id="9402d-148">La siguiente tabla describe las funciones de conversión de tipos en la [categoría texto](er-functions-category-text.md).</span><span class="sxs-lookup"><span data-stu-id="9402d-148">The following table describes the type conversion functions in the [text category](er-functions-category-text.md).</span></span>

| <span data-ttu-id="9402d-149">Función</span><span class="sxs-lookup"><span data-stu-id="9402d-149">Function</span></span> | <span data-ttu-id="9402d-150">Descripción</span><span class="sxs-lookup"><span data-stu-id="9402d-150">Description</span></span> |
|----------|-------------|
| [<span data-ttu-id="9402d-151">Char</span><span class="sxs-lookup"><span data-stu-id="9402d-151">Char</span></span>](er-functions-text-char.md)                 | <span data-ttu-id="9402d-152">Esta función devuelve un valor *String* que representa un solo carácter al que hace referencia el número Unicode especificado.</span><span class="sxs-lookup"><span data-stu-id="9402d-152">This function returns a *String* value that represents a single character that is referenced by the specified Unicode number.</span></span> |
| [<span data-ttu-id="9402d-153">GuidValue</span><span class="sxs-lookup"><span data-stu-id="9402d-153">GuidValue</span></span>](er-functions-text-guidvalue.md)       | <span data-ttu-id="9402d-154">Esta función convierte la entrada especificada del tipo *Cadena* a un elemento de datos del tipo *GUID*.</span><span class="sxs-lookup"><span data-stu-id="9402d-154">This function converts the specified input of the *String* type to a data item of the *GUID* type.</span></span> |
| [<span data-ttu-id="9402d-155">NumberFormat</span><span class="sxs-lookup"><span data-stu-id="9402d-155">NumberFormat</span></span>](er-functions-text-numberformat.md) | <span data-ttu-id="9402d-156">Esta función devuelve un valor *Cadena* que representa el número especificado en el formato especificado y en una cultura opcional especificada.</span><span class="sxs-lookup"><span data-stu-id="9402d-156">This function returns a *String* value that represents the specified number in the specified format and in an optionally specified culture.</span></span> |
| [<span data-ttu-id="9402d-157">QrCode</span><span class="sxs-lookup"><span data-stu-id="9402d-157">QrCode</span></span>](er-functions-text-qrcode.md)             | <span data-ttu-id="9402d-158">Esta función devuelve un valor *Contenedor* que presenta la imagen del código de Respuesta rápida (código QR) para la cadena especificada en formato binario.</span><span class="sxs-lookup"><span data-stu-id="9402d-158">This function returns a *Container* value that presents the Quick Response code (QR code) image for the specified string in binary format.</span></span> |
| [<span data-ttu-id="9402d-159">Texto</span><span class="sxs-lookup"><span data-stu-id="9402d-159">Text</span></span>](er-functions-text-text.md)                 | <span data-ttu-id="9402d-160">Esta función devuelve un valor *Cadena* que representa al número especificado después de que se haya convertido en una cadena de texto que se formatea según la configuración regional del servidor de la instancia actual de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="9402d-160">This function returns a *String* value that represents the specified number after it has been converted to a text string that is formatted according to the server locale settings of the current application instance.</span></span> |

## <a name="additional-resources"></a><span data-ttu-id="9402d-161">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="9402d-161">Additional resources</span></span>

[<span data-ttu-id="9402d-162">Visión general de los informes electrónicos</span><span class="sxs-lookup"><span data-stu-id="9402d-162">Electronic Reporting overview</span></span>](general-electronic-reporting.md)

[<span data-ttu-id="9402d-163">Diseñador de fórmulas en los informes electrónicos</span><span class="sxs-lookup"><span data-stu-id="9402d-163">Formula designer in Electronic reporting</span></span>](general-electronic-reporting-formula-designer.md)

[<span data-ttu-id="9402d-164">Idioma de fórmulas en los informes electrónicos</span><span class="sxs-lookup"><span data-stu-id="9402d-164">Electronic reporting formula language</span></span>](er-formula-language.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]