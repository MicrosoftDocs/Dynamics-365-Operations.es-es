---
title: Lista de funciones ER en la categoría de fecha y hora
description: Este tema proporciona información sobre las funciones de fecha y hora que son compatibles con los informes electrónicos (ER).
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
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fa8e725ac6bd7d280dc0269a70e3f7abf1ad4d43
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916577"
---
# <a name="list-of-er-functions-in-the-date-and-time-category"></a><span data-ttu-id="7f46e-103">Lista de funciones ER en la categoría de fecha y hora</span><span class="sxs-lookup"><span data-stu-id="7f46e-103">List of ER functions in the Date and time category</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7f46e-104">Las funciones de fecha y hora de informes electrónicos (ER) se pueden usar para extraer información de los valores de fecha y hora, y para realizar operaciones en ellos.</span><span class="sxs-lookup"><span data-stu-id="7f46e-104">Electronic reporting (ER) date and time functions can be used to extract information from date and time values, and to perform operations on them.</span></span> <span data-ttu-id="7f46e-105">Este tema proporciona un resumen de estas funciones.</span><span class="sxs-lookup"><span data-stu-id="7f46e-105">This topic provides a summary of these functions.</span></span>

## <a name="list-of-supported-functions"></a><span data-ttu-id="7f46e-106">Lista de funciones permitidas.</span><span class="sxs-lookup"><span data-stu-id="7f46e-106">List of supported functions</span></span>

| <span data-ttu-id="7f46e-107">Función</span><span class="sxs-lookup"><span data-stu-id="7f46e-107">Function</span></span> | <span data-ttu-id="7f46e-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="7f46e-108">Description</span></span> |
|----------|-------------|
| [<span data-ttu-id="7f46e-109">AddDays</span><span class="sxs-lookup"><span data-stu-id="7f46e-109">AddDays</span></span>](er-functions-datetime-adddays.md) | <span data-ttu-id="7f46e-110">Esta función devuelve un valor *Fecha y hora* que es el número especificado de días antes o después de una fecha de inicio especificada.</span><span class="sxs-lookup"><span data-stu-id="7f46e-110">This function returns a *DateTime* value that is the specified number of days before or after a specified start date.</span></span> |
| [<span data-ttu-id="7f46e-111">DateFormat</span><span class="sxs-lookup"><span data-stu-id="7f46e-111">DateFormat</span></span>](er-functions-datetime-dateformat.md) | <span data-ttu-id="7f46e-112">Esta función devuelve un valor *Cadena* que presenta un valor determinado de fecha como texto en el formato especificado y en una cultura opcional especificada.</span><span class="sxs-lookup"><span data-stu-id="7f46e-112">This function returns a *String* value that presents a given date value as text in the specified format and in an optionally specified culture.</span></span> |
| [<span data-ttu-id="7f46e-113">DateTimeFormat</span><span class="sxs-lookup"><span data-stu-id="7f46e-113">DateTimeFormat</span></span>](er-functions-datetime-datetimeformat.md) | <span data-ttu-id="7f46e-114">Esta función devuelve un valor *Cadena* que presenta un valor determinado de fecha/hora como texto en el formato especificado y en una cultura opcional especificada.</span><span class="sxs-lookup"><span data-stu-id="7f46e-114">This function returns a *String* value that presents a given date/time value as text in the specified format and in an optionally specified culture.</span></span> |
| [<span data-ttu-id="7f46e-115">DateTimeValue</span><span class="sxs-lookup"><span data-stu-id="7f46e-115">DateTimeValue</span></span>](er-functions-datetime-datetimevalue.md) | <span data-ttu-id="7f46e-116">Esta función devuelve un valor *Fecha y hora* que se convierte de un determinado valor de texto en el formato especificado y en una cultura opcionalmente especificada a un valor de fecha / hora.</span><span class="sxs-lookup"><span data-stu-id="7f46e-116">This function returns a *DateTime* value that is converted from a given text value in the specified format and in an optionally specified culture to a date/time value.</span></span> |
| [<span data-ttu-id="7f46e-117">DateToDateTime</span><span class="sxs-lookup"><span data-stu-id="7f46e-117">DateToDateTime</span></span>](er-functions-datetime-datetodatetime.md) | <span data-ttu-id="7f46e-118">Esta función devuelve un valor *Fecha y hora* que se convierte de un determinado valor de datos a un valor de fecha / hora en hora universal coordinada (hora meridiano de Greenwich \[GMT\]).</span><span class="sxs-lookup"><span data-stu-id="7f46e-118">This function returns a *DateTime* value that is converted from a given date value to a date/time value in Coordinated Universal Time (Greenwich Mean Time \[GMT\]).</span></span> |
| [<span data-ttu-id="7f46e-119">DateValue</span><span class="sxs-lookup"><span data-stu-id="7f46e-119">DateValue</span></span>](er-functions-datetime-datevalue.md) | <span data-ttu-id="7f46e-120">Esta función devuelve un valor *Fecha* que se convierte de un determinado valor de texto en el formato especificado y en una cultura opcionalmente especificada a un valor de fecha.</span><span class="sxs-lookup"><span data-stu-id="7f46e-120">This function returns a *Date* value that is converted from a given text value in the specified format and in an optionally specified culture to a date value.</span></span> |
| [<span data-ttu-id="7f46e-121">DayOfYear</span><span class="sxs-lookup"><span data-stu-id="7f46e-121">DayOfYear</span></span>](er-functions-datetime-dayofyear.md) | <span data-ttu-id="7f46e-122">Esta función devuelve un valor *Entero* que representa el número de días entre el 1 de enero y la fecha especificada.</span><span class="sxs-lookup"><span data-stu-id="7f46e-122">This function returns an *Integer* value that represents the number of days between January 1 and the specified date.</span></span> |
| [<span data-ttu-id="7f46e-123">Días</span><span class="sxs-lookup"><span data-stu-id="7f46e-123">Days</span></span>](er-functions-datetime-days.md) | <span data-ttu-id="7f46e-124">Esta función devuelve un valor *Entero* que representa el número de días entre una fecha especificada y una segunda fecha especificada.</span><span class="sxs-lookup"><span data-stu-id="7f46e-124">This function returns an *Integer* value that represents the number of days between one specified date and a second specified date.</span></span> |
| [<span data-ttu-id="7f46e-125">Now</span><span class="sxs-lookup"><span data-stu-id="7f46e-125">Now</span></span>](er-functions-datetime-now.md) | <span data-ttu-id="7f46e-126">Esta función devuelve un valor *Fecha y hora* que representa la fecha y hora actuales del servidor de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="7f46e-126">This function returns a *DateTime* value that represents the current application server date and time.</span></span> |
| [<span data-ttu-id="7f46e-127">NullDate</span><span class="sxs-lookup"><span data-stu-id="7f46e-127">NullDate</span></span>](er-functions-datetime-nulldate.md) | <span data-ttu-id="7f46e-128">Esta función devuelve un valor *Fecha* que representa la fecha **nulo** (1 de enero de 1900).</span><span class="sxs-lookup"><span data-stu-id="7f46e-128">This function returns a *Date* value that represents the **null** date (January 1, 1900).</span></span> |
| [<span data-ttu-id="7f46e-129">NullDateTime</span><span class="sxs-lookup"><span data-stu-id="7f46e-129">NullDateTime</span></span>](er-functions-datetime-nulldatetime.md) | <span data-ttu-id="7f46e-130">Esta función devuelve un valor *Fecha y hora* que representa el valor **nulo** de fecha / hora (1 de enero de 1900) en hora universal coordinada.</span><span class="sxs-lookup"><span data-stu-id="7f46e-130">This function returns a *DateTime* value that represents the **null** date/time value (January 1, 1900) in Coordinated Universal Time.</span></span> |
| [<span data-ttu-id="7f46e-131">SessionNow</span><span class="sxs-lookup"><span data-stu-id="7f46e-131">SessionNow</span></span>](er-functions-datetime-sessionnow.md) | <span data-ttu-id="7f46e-132">Esta función devuelve un valor *Fecha y hora* que representa la fecha y hora actuales de la sesión de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7f46e-132">This function returns a *DateTime* value that represents the current application session date and time.</span></span> |
| [<span data-ttu-id="7f46e-133">SessionToday</span><span class="sxs-lookup"><span data-stu-id="7f46e-133">SessionToday</span></span>](er-functions-datetime-sessiontoday.md) | <span data-ttu-id="7f46e-134">Esta función devuelve un valor *Fecha* que representa la fecha actual de la sesión de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7f46e-134">This function returns a *Date* value that represents the current application session date.</span></span> |
| [<span data-ttu-id="7f46e-135">Hoy</span><span class="sxs-lookup"><span data-stu-id="7f46e-135">Today</span></span>](er-functions-datetime-today.md) | <span data-ttu-id="7f46e-136">Esta función devuelve un valor *Fecha* que representa la fecha actual del servidor de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7f46e-136">This function returns a *Date* value that represents the current application server date.</span></span> |

## <a name="additional-resources"></a><span data-ttu-id="7f46e-137">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="7f46e-137">Additional resources</span></span>

[<span data-ttu-id="7f46e-138">Visión general de los informes electrónicos</span><span class="sxs-lookup"><span data-stu-id="7f46e-138">Electronic Reporting overview</span></span>](general-electronic-reporting.md)

[<span data-ttu-id="7f46e-139">Diseñador de fórmulas en los informes electrónicos</span><span class="sxs-lookup"><span data-stu-id="7f46e-139">Formula designer in Electronic reporting</span></span>](general-electronic-reporting-formula-designer.md)

[<span data-ttu-id="7f46e-140">Idioma de fórmulas en los informes electrónicos</span><span class="sxs-lookup"><span data-stu-id="7f46e-140">Electronic reporting formula language</span></span>](er-formula-language.md)
