---
title: Función DATEFORMAT ER
description: En este tema se proporciona información sobre cómo usar la función DATEFORMAT de informes electrónicos (ER).
author: NickSelin
ms.date: 01/04/2021
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
ms.openlocfilehash: 1b3a0a2608328b233004034f7ab2ccfa833c17e3
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "5890919"
---
# <a name="dateformat-er-function"></a><span data-ttu-id="bb3b2-103">Función DATEFORMAT ER</span><span class="sxs-lookup"><span data-stu-id="bb3b2-103">DATEFORMAT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="bb3b2-104">La función `DATEFORMAT` devuelve un valor *Cadena* que presenta un valor determinado de fecha como texto en el formato especificado y en una [cultura](/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes) opcional especificada.</span><span class="sxs-lookup"><span data-stu-id="bb3b2-104">The `DATEFORMAT` function returns a *String* value that presents a given date value as text in the specified format and in an optionally specified [culture](/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes).</span></span> <span data-ttu-id="bb3b2-105">Para obtener información acerca de los formatos admitidos, vea [estándar](/dotnet/standard/base-types/standard-date-and-time-format-strings) y [personalizado](/dotnet/standard/base-types/custom-date-and-time-format-strings).</span><span class="sxs-lookup"><span data-stu-id="bb3b2-105">For information about the supported formats, see [standard](/dotnet/standard/base-types/standard-date-and-time-format-strings) and [custom](/dotnet/standard/base-types/custom-date-and-time-format-strings).</span></span>

## <a name="syntax-1"></a><span data-ttu-id="bb3b2-106">Sintaxis 1</span><span class="sxs-lookup"><span data-stu-id="bb3b2-106">Syntax 1</span></span>

```vb
DATEFORMAT (date, format)
```

## <a name="syntax-2"></a><span data-ttu-id="bb3b2-107">Sintaxis 2</span><span class="sxs-lookup"><span data-stu-id="bb3b2-107">Syntax 2</span></span>

```vb
DATEFORMAT (date, format, culture)
```

## <a name="arguments"></a><span data-ttu-id="bb3b2-108">Argumentos</span><span class="sxs-lookup"><span data-stu-id="bb3b2-108">Arguments</span></span>

<span data-ttu-id="bb3b2-109">`date`: *Fecha*</span><span class="sxs-lookup"><span data-stu-id="bb3b2-109">`date`: *Date*</span></span>

<span data-ttu-id="bb3b2-110">Un valor de fecha / hora que representa la fecha a formatear.</span><span class="sxs-lookup"><span data-stu-id="bb3b2-110">A date value that represents the date to format.</span></span>

<span data-ttu-id="bb3b2-111">`format`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="bb3b2-111">`format`: *String*</span></span>

<span data-ttu-id="bb3b2-112">El formato de la cadena de salida.</span><span class="sxs-lookup"><span data-stu-id="bb3b2-112">The format of the output string.</span></span>

> [!NOTE]
> <span data-ttu-id="bb3b2-113">La cadena de formato distingue mayúsculas de minúsculas cuando utiliza un formato estándar o un formato personalizado.</span><span class="sxs-lookup"><span data-stu-id="bb3b2-113">The format string is case-sensitive when you use either a standard format or a custom format.</span></span> <span data-ttu-id="bb3b2-114">Por ejemplo, el especificador de formato "d" [estándar](/dotnet/standard/base-types/standard-date-and-time-format-strings) devuelve la fecha utilizando el patrón de fecha corta, mientras que el especificador de formato estándar "D" devuelve la fecha utilizando el patrón de fecha larga.</span><span class="sxs-lookup"><span data-stu-id="bb3b2-114">For example, the [standard](/dotnet/standard/base-types/standard-date-and-time-format-strings) "d" format specifier returns the date by using the short date pattern, whereas the standard "D" format specifier returns the date by using the long date pattern.</span></span> <span data-ttu-id="bb3b2-115">Además, el especificador de formato "M" [personalizado](/dotnet/standard/base-types/custom-date-and-time-format-strings) devuelve los meses del 1 al 12, mientras que el especificador de formato personalizado "m" devuelve los minutos del 0 al 59.</span><span class="sxs-lookup"><span data-stu-id="bb3b2-115">Additionally, the [custom](/dotnet/standard/base-types/custom-date-and-time-format-strings) "M" format specifier returns the month from 1 through 12, whereas the custom "m" format specifier returns the minute from 0 through 59.</span></span>

<span data-ttu-id="bb3b2-116">`culture`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="bb3b2-116">`culture`: *String*</span></span>

<span data-ttu-id="bb3b2-117">La cultura a utilizar para formatear.</span><span class="sxs-lookup"><span data-stu-id="bb3b2-117">The culture to use for formatting.</span></span>

## <a name="return-values"></a><span data-ttu-id="bb3b2-118">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="bb3b2-118">Return values</span></span>

<span data-ttu-id="bb3b2-119">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="bb3b2-119">*String*</span></span>

<span data-ttu-id="bb3b2-120">El valor de cadena resultante.</span><span class="sxs-lookup"><span data-stu-id="bb3b2-120">The resulting string value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="bb3b2-121">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="bb3b2-121">Usage notes</span></span>

<span data-ttu-id="bb3b2-122">Si la cultura no se define como un argumento de la función llamada, el valor de `culture` está definido por el contexto de llamada.</span><span class="sxs-lookup"><span data-stu-id="bb3b2-122">If the culture isn't defined as an argument of the called function, the value of `culture` is defined by the calling context.</span></span> <span data-ttu-id="bb3b2-123">Por ejemplo, si la función `DATEFORMAT` se llama mediante el uso de la sintaxis 1 en un formato de informe electrónico (ER) para un elemento **ARCHIVO** configurado para usar la cultura alemana, la conversión se realizará utilizando la cultura alemana.</span><span class="sxs-lookup"><span data-stu-id="bb3b2-123">For example, if the `DATEFORMAT` function is called by using syntax 1 in an Electronic reporting (ER) format for a **FILE** element that is configured to use the German culture, the conversion will be done by using the German culture.</span></span> <span data-ttu-id="bb3b2-124">El valor de `culture` predeterminado es **EN-US**.</span><span class="sxs-lookup"><span data-stu-id="bb3b2-124">The default `culture` value is **EN-US**.</span></span>

## <a name="example-1"></a><span data-ttu-id="bb3b2-125">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="bb3b2-125">Example 1</span></span>

<span data-ttu-id="bb3b2-126">`DATEFORMAT (TODAY (), "dd-MM-yyyy")` devuelve la fecha del servidor actual, 24 de diciembre de 2015, como la cadena **“24-12-2015”**, basado en el formato personalizado especificado.</span><span class="sxs-lookup"><span data-stu-id="bb3b2-126">`DATEFORMAT (TODAY (), "dd-MM-yyyy")` returns the current application server date, December 24, 2015, as the string **"24-12-2015"**, based on the specified custom format.</span></span>

## <a name="example-2"></a><span data-ttu-id="bb3b2-127">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="bb3b2-127">Example 2</span></span>

<span data-ttu-id="bb3b2-128">`DATEFORMAT (SESSIONTODAY (), "d", "DE")` devuelve la fecha de sesión de la aplicación actual, 24 de diciembre de 2015, como la cadena **"24-12-2015"**, basado en la cultura alemana seleccionada y el formato especificado.</span><span class="sxs-lookup"><span data-stu-id="bb3b2-128">`DATEFORMAT (SESSIONTODAY (), "d", "DE")` returns the current application session date, December 24, 2015, as the string **"24-12-2015"**, based on the selected German culture and the specified format.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="bb3b2-129">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="bb3b2-129">Additional resources</span></span>

[<span data-ttu-id="bb3b2-130">Funciones de fecha y de tiempo</span><span class="sxs-lookup"><span data-stu-id="bb3b2-130">Date and time functions</span></span>](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]