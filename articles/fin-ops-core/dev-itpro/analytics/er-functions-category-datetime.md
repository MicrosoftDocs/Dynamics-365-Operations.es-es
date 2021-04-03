---
title: Lista de funciones ER en la categoría de fecha y hora
description: Este tema proporciona información sobre las funciones de fecha y hora que son compatibles con los informes electrónicos (ER).
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
ms.openlocfilehash: 52b84f9b611f703fd390eca58c1364a4992bece2
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "5561719"
---
# <a name="list-of-er-functions-in-the-date-and-time-category"></a><span data-ttu-id="5a2da-103">Lista de funciones ER en la categoría de fecha y hora</span><span class="sxs-lookup"><span data-stu-id="5a2da-103">List of ER functions in the Date and time category</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5a2da-104">Las funciones de fecha y hora de informes electrónicos (ER) se pueden usar para extraer información de los valores de fecha y hora, y para realizar operaciones en ellos.</span><span class="sxs-lookup"><span data-stu-id="5a2da-104">Electronic reporting (ER) date and time functions can be used to extract information from date and time values, and to perform operations on them.</span></span> <span data-ttu-id="5a2da-105">Este tema proporciona un resumen de estas funciones.</span><span class="sxs-lookup"><span data-stu-id="5a2da-105">This topic provides a summary of these functions.</span></span>

## <a name="list-of-supported-functions"></a><span data-ttu-id="5a2da-106">Lista de funciones permitidas.</span><span class="sxs-lookup"><span data-stu-id="5a2da-106">List of supported functions</span></span>

| <span data-ttu-id="5a2da-107">Función</span><span class="sxs-lookup"><span data-stu-id="5a2da-107">Function</span></span> | <span data-ttu-id="5a2da-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="5a2da-108">Description</span></span> |
|----------|-------------|
| [<span data-ttu-id="5a2da-109">AddDays</span><span class="sxs-lookup"><span data-stu-id="5a2da-109">AddDays</span></span>](er-functions-datetime-adddays.md) | <span data-ttu-id="5a2da-110">Esta función devuelve un valor *Fecha y hora* que es el número especificado de días antes o después de una fecha de inicio especificada.</span><span class="sxs-lookup"><span data-stu-id="5a2da-110">This function returns a *DateTime* value that is the specified number of days before or after a specified start date.</span></span> |
| [<span data-ttu-id="5a2da-111">DateFormat</span><span class="sxs-lookup"><span data-stu-id="5a2da-111">DateFormat</span></span>](er-functions-datetime-dateformat.md) | <span data-ttu-id="5a2da-112">Esta función devuelve un valor *Cadena* que presenta un valor determinado de fecha como texto en el formato especificado y en una cultura opcional especificada.</span><span class="sxs-lookup"><span data-stu-id="5a2da-112">This function returns a *String* value that presents a given date value as text in the specified format and in an optionally specified culture.</span></span> |
| [<span data-ttu-id="5a2da-113">DateTimeFormat</span><span class="sxs-lookup"><span data-stu-id="5a2da-113">DateTimeFormat</span></span>](er-functions-datetime-datetimeformat.md) | <span data-ttu-id="5a2da-114">Esta función devuelve un valor *Cadena* que presenta un valor determinado de fecha/hora como texto en el formato especificado y en una cultura opcional especificada.</span><span class="sxs-lookup"><span data-stu-id="5a2da-114">This function returns a *String* value that presents a given date/time value as text in the specified format and in an optionally specified culture.</span></span> |
| [<span data-ttu-id="5a2da-115">DateTimeValue</span><span class="sxs-lookup"><span data-stu-id="5a2da-115">DateTimeValue</span></span>](er-functions-datetime-datetimevalue.md) | <span data-ttu-id="5a2da-116">Esta función devuelve un valor *Fecha y hora* que se convierte de un determinado valor de texto en el formato especificado y en una cultura opcionalmente especificada a un valor de fecha / hora.</span><span class="sxs-lookup"><span data-stu-id="5a2da-116">This function returns a *DateTime* value that is converted from a given text value in the specified format and in an optionally specified culture to a date/time value.</span></span> |
| [<span data-ttu-id="5a2da-117">DateToDateTime</span><span class="sxs-lookup"><span data-stu-id="5a2da-117">DateToDateTime</span></span>](er-functions-datetime-datetodatetime.md) | <span data-ttu-id="5a2da-118">Esta función devuelve un valor *Fecha y hora* que se convierte de un determinado valor de datos a un valor de fecha / hora en hora universal coordinada (hora meridiano de Greenwich \[GMT\]).</span><span class="sxs-lookup"><span data-stu-id="5a2da-118">This function returns a *DateTime* value that is converted from a given date value to a date/time value in Coordinated Universal Time (Greenwich Mean Time \[GMT\]).</span></span> |
| [<span data-ttu-id="5a2da-119">DateValue</span><span class="sxs-lookup"><span data-stu-id="5a2da-119">DateValue</span></span>](er-functions-datetime-datevalue.md) | <span data-ttu-id="5a2da-120">Esta función devuelve un valor *Fecha* que se convierte de un determinado valor de texto en el formato especificado y en una cultura opcionalmente especificada a un valor de fecha.</span><span class="sxs-lookup"><span data-stu-id="5a2da-120">This function returns a *Date* value that is converted from a given text value in the specified format and in an optionally specified culture to a date value.</span></span> |
| [<span data-ttu-id="5a2da-121">DayOfYear</span><span class="sxs-lookup"><span data-stu-id="5a2da-121">DayOfYear</span></span>](er-functions-datetime-dayofyear.md) | <span data-ttu-id="5a2da-122">Esta función devuelve un valor *Entero* que representa el número de días entre el 1 de enero y la fecha especificada.</span><span class="sxs-lookup"><span data-stu-id="5a2da-122">This function returns an *Integer* value that represents the number of days between January 1 and the specified date.</span></span> |
| [<span data-ttu-id="5a2da-123">Días</span><span class="sxs-lookup"><span data-stu-id="5a2da-123">Days</span></span>](er-functions-datetime-days.md) | <span data-ttu-id="5a2da-124">Esta función devuelve un valor *Entero* que representa el número de días entre una fecha especificada y una segunda fecha especificada.</span><span class="sxs-lookup"><span data-stu-id="5a2da-124">This function returns an *Integer* value that represents the number of days between one specified date and a second specified date.</span></span> |
| [<span data-ttu-id="5a2da-125">Now</span><span class="sxs-lookup"><span data-stu-id="5a2da-125">Now</span></span>](er-functions-datetime-now.md) | <span data-ttu-id="5a2da-126">Esta función devuelve un valor *Fecha y hora* que representa la fecha y hora actuales del servidor de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="5a2da-126">This function returns a *DateTime* value that represents the current application server date and time.</span></span> |
| [<span data-ttu-id="5a2da-127">NullDate</span><span class="sxs-lookup"><span data-stu-id="5a2da-127">NullDate</span></span>](er-functions-datetime-nulldate.md) | <span data-ttu-id="5a2da-128">Esta función devuelve un valor *Fecha* que representa la fecha **nulo** (1 de enero de 1900).</span><span class="sxs-lookup"><span data-stu-id="5a2da-128">This function returns a *Date* value that represents the **null** date (January 1, 1900).</span></span> |
| [<span data-ttu-id="5a2da-129">NullDateTime</span><span class="sxs-lookup"><span data-stu-id="5a2da-129">NullDateTime</span></span>](er-functions-datetime-nulldatetime.md) | <span data-ttu-id="5a2da-130">Esta función devuelve un valor *Fecha y hora* que representa el valor **nulo** de fecha / hora (1 de enero de 1900) en hora universal coordinada.</span><span class="sxs-lookup"><span data-stu-id="5a2da-130">This function returns a *DateTime* value that represents the **null** date/time value (January 1, 1900) in Coordinated Universal Time.</span></span> |
| [<span data-ttu-id="5a2da-131">SessionNow</span><span class="sxs-lookup"><span data-stu-id="5a2da-131">SessionNow</span></span>](er-functions-datetime-sessionnow.md) | <span data-ttu-id="5a2da-132">Esta función devuelve un valor *Fecha y hora* que representa la fecha y hora actuales de la sesión de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5a2da-132">This function returns a *DateTime* value that represents the current application session date and time.</span></span> |
| [<span data-ttu-id="5a2da-133">SessionToday</span><span class="sxs-lookup"><span data-stu-id="5a2da-133">SessionToday</span></span>](er-functions-datetime-sessiontoday.md) | <span data-ttu-id="5a2da-134">Esta función devuelve un valor *Fecha* que representa la fecha actual de la sesión de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5a2da-134">This function returns a *Date* value that represents the current application session date.</span></span> |
| [<span data-ttu-id="5a2da-135">Hoy</span><span class="sxs-lookup"><span data-stu-id="5a2da-135">Today</span></span>](er-functions-datetime-today.md) | <span data-ttu-id="5a2da-136">Esta función devuelve un valor *Fecha* que representa la fecha actual del servidor de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5a2da-136">This function returns a *Date* value that represents the current application server date.</span></span> |

## <a name="additional-resources"></a><span data-ttu-id="5a2da-137">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="5a2da-137">Additional resources</span></span>

[<span data-ttu-id="5a2da-138">Visión general de los informes electrónicos</span><span class="sxs-lookup"><span data-stu-id="5a2da-138">Electronic Reporting overview</span></span>](general-electronic-reporting.md)

[<span data-ttu-id="5a2da-139">Diseñador de fórmulas en los informes electrónicos</span><span class="sxs-lookup"><span data-stu-id="5a2da-139">Formula designer in Electronic reporting</span></span>](general-electronic-reporting-formula-designer.md)

[<span data-ttu-id="5a2da-140">Idioma de fórmulas en los informes electrónicos</span><span class="sxs-lookup"><span data-stu-id="5a2da-140">Electronic reporting formula language</span></span>](er-formula-language.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]