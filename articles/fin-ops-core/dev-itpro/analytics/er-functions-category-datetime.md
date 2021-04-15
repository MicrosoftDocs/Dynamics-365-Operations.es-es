---
title: Lista de funciones ER en la categoría de fecha y hora
description: Este tema proporciona información sobre las funciones de fecha y hora que son compatibles con los informes electrónicos (ER).
author: NickSelin
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
ms.openlocfilehash: 2dd8524c9cd368f0fe64347e3212b419bb0902b4
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5744570"
---
# <a name="list-of-er-functions-in-the-date-and-time-category"></a><span data-ttu-id="70049-103">Lista de funciones ER en la categoría de fecha y hora</span><span class="sxs-lookup"><span data-stu-id="70049-103">List of ER functions in the Date and time category</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="70049-104">Las funciones de fecha y hora de informes electrónicos (ER) se pueden usar para extraer información de los valores de fecha y hora, y para realizar operaciones en ellos.</span><span class="sxs-lookup"><span data-stu-id="70049-104">Electronic reporting (ER) date and time functions can be used to extract information from date and time values, and to perform operations on them.</span></span> <span data-ttu-id="70049-105">Este tema proporciona un resumen de estas funciones.</span><span class="sxs-lookup"><span data-stu-id="70049-105">This topic provides a summary of these functions.</span></span>

## <a name="list-of-supported-functions"></a><span data-ttu-id="70049-106">Lista de funciones permitidas.</span><span class="sxs-lookup"><span data-stu-id="70049-106">List of supported functions</span></span>

| <span data-ttu-id="70049-107">Función</span><span class="sxs-lookup"><span data-stu-id="70049-107">Function</span></span> | <span data-ttu-id="70049-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="70049-108">Description</span></span> |
|----------|-------------|
| [<span data-ttu-id="70049-109">AddDays</span><span class="sxs-lookup"><span data-stu-id="70049-109">AddDays</span></span>](er-functions-datetime-adddays.md) | <span data-ttu-id="70049-110">Esta función devuelve un valor *Fecha y hora* que es el número especificado de días antes o después de una fecha de inicio especificada.</span><span class="sxs-lookup"><span data-stu-id="70049-110">This function returns a *DateTime* value that is the specified number of days before or after a specified start date.</span></span> |
| [<span data-ttu-id="70049-111">DateFormat</span><span class="sxs-lookup"><span data-stu-id="70049-111">DateFormat</span></span>](er-functions-datetime-dateformat.md) | <span data-ttu-id="70049-112">Esta función devuelve un valor *Cadena* que presenta un valor determinado de fecha como texto en el formato especificado y en una cultura opcional especificada.</span><span class="sxs-lookup"><span data-stu-id="70049-112">This function returns a *String* value that presents a given date value as text in the specified format and in an optionally specified culture.</span></span> |
| [<span data-ttu-id="70049-113">DateTimeFormat</span><span class="sxs-lookup"><span data-stu-id="70049-113">DateTimeFormat</span></span>](er-functions-datetime-datetimeformat.md) | <span data-ttu-id="70049-114">Esta función devuelve un valor *Cadena* que presenta un valor determinado de fecha/hora como texto en el formato especificado y en una cultura opcional especificada.</span><span class="sxs-lookup"><span data-stu-id="70049-114">This function returns a *String* value that presents a given date/time value as text in the specified format and in an optionally specified culture.</span></span> |
| [<span data-ttu-id="70049-115">DateTimeValue</span><span class="sxs-lookup"><span data-stu-id="70049-115">DateTimeValue</span></span>](er-functions-datetime-datetimevalue.md) | <span data-ttu-id="70049-116">Esta función devuelve un valor *Fecha y hora* que se convierte de un determinado valor de texto en el formato especificado y en una cultura opcionalmente especificada a un valor de fecha / hora.</span><span class="sxs-lookup"><span data-stu-id="70049-116">This function returns a *DateTime* value that is converted from a given text value in the specified format and in an optionally specified culture to a date/time value.</span></span> |
| [<span data-ttu-id="70049-117">DateToDateTime</span><span class="sxs-lookup"><span data-stu-id="70049-117">DateToDateTime</span></span>](er-functions-datetime-datetodatetime.md) | <span data-ttu-id="70049-118">Esta función devuelve un valor *Fecha y hora* que se convierte de un determinado valor de datos a un valor de fecha / hora en hora universal coordinada (hora meridiano de Greenwich \[GMT\]).</span><span class="sxs-lookup"><span data-stu-id="70049-118">This function returns a *DateTime* value that is converted from a given date value to a date/time value in Coordinated Universal Time (Greenwich Mean Time \[GMT\]).</span></span> |
| [<span data-ttu-id="70049-119">DateValue</span><span class="sxs-lookup"><span data-stu-id="70049-119">DateValue</span></span>](er-functions-datetime-datevalue.md) | <span data-ttu-id="70049-120">Esta función devuelve un valor *Fecha* que se convierte de un determinado valor de texto en el formato especificado y en una cultura opcionalmente especificada a un valor de fecha.</span><span class="sxs-lookup"><span data-stu-id="70049-120">This function returns a *Date* value that is converted from a given text value in the specified format and in an optionally specified culture to a date value.</span></span> |
| [<span data-ttu-id="70049-121">DayOfYear</span><span class="sxs-lookup"><span data-stu-id="70049-121">DayOfYear</span></span>](er-functions-datetime-dayofyear.md) | <span data-ttu-id="70049-122">Esta función devuelve un valor *Entero* que representa el número de días entre el 1 de enero y la fecha especificada.</span><span class="sxs-lookup"><span data-stu-id="70049-122">This function returns an *Integer* value that represents the number of days between January 1 and the specified date.</span></span> |
| [<span data-ttu-id="70049-123">Días</span><span class="sxs-lookup"><span data-stu-id="70049-123">Days</span></span>](er-functions-datetime-days.md) | <span data-ttu-id="70049-124">Esta función devuelve un valor *Entero* que representa el número de días entre una fecha especificada y una segunda fecha especificada.</span><span class="sxs-lookup"><span data-stu-id="70049-124">This function returns an *Integer* value that represents the number of days between one specified date and a second specified date.</span></span> |
| [<span data-ttu-id="70049-125">Now</span><span class="sxs-lookup"><span data-stu-id="70049-125">Now</span></span>](er-functions-datetime-now.md) | <span data-ttu-id="70049-126">Esta función devuelve un valor *Fecha y hora* que representa la fecha y hora actuales del servidor de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="70049-126">This function returns a *DateTime* value that represents the current application server date and time.</span></span> |
| [<span data-ttu-id="70049-127">NullDate</span><span class="sxs-lookup"><span data-stu-id="70049-127">NullDate</span></span>](er-functions-datetime-nulldate.md) | <span data-ttu-id="70049-128">Esta función devuelve un valor *Fecha* que representa la fecha **nulo** (1 de enero de 1900).</span><span class="sxs-lookup"><span data-stu-id="70049-128">This function returns a *Date* value that represents the **null** date (January 1, 1900).</span></span> |
| [<span data-ttu-id="70049-129">NullDateTime</span><span class="sxs-lookup"><span data-stu-id="70049-129">NullDateTime</span></span>](er-functions-datetime-nulldatetime.md) | <span data-ttu-id="70049-130">Esta función devuelve un valor *Fecha y hora* que representa el valor **nulo** de fecha / hora (1 de enero de 1900) en hora universal coordinada.</span><span class="sxs-lookup"><span data-stu-id="70049-130">This function returns a *DateTime* value that represents the **null** date/time value (January 1, 1900) in Coordinated Universal Time.</span></span> |
| [<span data-ttu-id="70049-131">SessionNow</span><span class="sxs-lookup"><span data-stu-id="70049-131">SessionNow</span></span>](er-functions-datetime-sessionnow.md) | <span data-ttu-id="70049-132">Esta función devuelve un valor *Fecha y hora* que representa la fecha y hora actuales de la sesión de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="70049-132">This function returns a *DateTime* value that represents the current application session date and time.</span></span> |
| [<span data-ttu-id="70049-133">SessionToday</span><span class="sxs-lookup"><span data-stu-id="70049-133">SessionToday</span></span>](er-functions-datetime-sessiontoday.md) | <span data-ttu-id="70049-134">Esta función devuelve un valor *Fecha* que representa la fecha actual de la sesión de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="70049-134">This function returns a *Date* value that represents the current application session date.</span></span> |
| [<span data-ttu-id="70049-135">Hoy</span><span class="sxs-lookup"><span data-stu-id="70049-135">Today</span></span>](er-functions-datetime-today.md) | <span data-ttu-id="70049-136">Esta función devuelve un valor *Fecha* que representa la fecha actual del servidor de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="70049-136">This function returns a *Date* value that represents the current application server date.</span></span> |

## <a name="additional-resources"></a><span data-ttu-id="70049-137">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="70049-137">Additional resources</span></span>

[<span data-ttu-id="70049-138">Visión general de los informes electrónicos</span><span class="sxs-lookup"><span data-stu-id="70049-138">Electronic Reporting overview</span></span>](general-electronic-reporting.md)

[<span data-ttu-id="70049-139">Diseñador de fórmulas en los informes electrónicos</span><span class="sxs-lookup"><span data-stu-id="70049-139">Formula designer in Electronic reporting</span></span>](general-electronic-reporting-formula-designer.md)

[<span data-ttu-id="70049-140">Idioma de fórmulas en los informes electrónicos</span><span class="sxs-lookup"><span data-stu-id="70049-140">Electronic reporting formula language</span></span>](er-formula-language.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]