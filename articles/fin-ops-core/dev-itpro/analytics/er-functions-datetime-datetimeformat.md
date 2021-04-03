---
title: Función DATETIMEFORMAT ER
description: En este tema se proporciona información sobre cómo usar la función DATETIMEFORMAT de informes electrónicos (ER).
author: NickSelin
manager: kfend
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
ms.openlocfilehash: b7516620763e87440c0fb866ce507c744223a229
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "5563639"
---
# <a name="datetimeformat-er-function"></a><span data-ttu-id="51c72-103">Función DATETIMEFORMAT ER</span><span class="sxs-lookup"><span data-stu-id="51c72-103">DATETIMEFORMAT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="51c72-104">La función `DATETIMEFORMAT` devuelve un valor *Cadena* que presenta un valor determinado de fecha/hora como texto en el formato especificado y en una [cultura](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes) opcional especificada.</span><span class="sxs-lookup"><span data-stu-id="51c72-104">The `DATETIMEFORMAT` function returns a *String* value that presents a given date/time value as text in the specified format and in an optionally specified [culture](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes).</span></span> <span data-ttu-id="51c72-105">Para obtener información acerca de los formatos admitidos, vea [estándar](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) y [personalizado](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).</span><span class="sxs-lookup"><span data-stu-id="51c72-105">For information about the supported formats, see [standard](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) and [custom](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).</span></span>

## <a name="syntax-1"></a><span data-ttu-id="51c72-106">Sintaxis 1</span><span class="sxs-lookup"><span data-stu-id="51c72-106">Syntax 1</span></span>

```vb
DATETIMEFORMAT (datetime, format)
```

## <a name="syntax-2"></a><span data-ttu-id="51c72-107">Sintaxis 2</span><span class="sxs-lookup"><span data-stu-id="51c72-107">Syntax 2</span></span>

```vb
DATETIMEFORMAT (datetime, format, culture)
```

## <a name="arguments"></a><span data-ttu-id="51c72-108">Argumentos</span><span class="sxs-lookup"><span data-stu-id="51c72-108">Arguments</span></span>

<span data-ttu-id="51c72-109">`datetime`: *Fecha y hora*</span><span class="sxs-lookup"><span data-stu-id="51c72-109">`datetime`: *DateTime*</span></span>

<span data-ttu-id="51c72-110">Un valor de fecha / hora que representa la fecha y la hora a formatear.</span><span class="sxs-lookup"><span data-stu-id="51c72-110">A date/time value that represents the date and time to format.</span></span>

<span data-ttu-id="51c72-111">`format`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="51c72-111">`format`: *String*</span></span>

<span data-ttu-id="51c72-112">El formato de la cadena de salida.</span><span class="sxs-lookup"><span data-stu-id="51c72-112">The format of the output string.</span></span>

> [!NOTE]
> <span data-ttu-id="51c72-113">La cadena de formato distingue mayúsculas de minúsculas cuando utiliza un formato estándar o un formato personalizado.</span><span class="sxs-lookup"><span data-stu-id="51c72-113">The format string is case-sensitive when you use either a standard format or a custom format.</span></span> <span data-ttu-id="51c72-114">Por ejemplo, el especificador de formato "d" [estándar](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) devuelve la fecha utilizando el patrón de fecha corta, mientras que el especificador de formato estándar "D" devuelve la fecha utilizando el patrón de fecha larga.</span><span class="sxs-lookup"><span data-stu-id="51c72-114">For example, the [standard](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) "d" format specifier returns the date by using the short date pattern, whereas the standard "D" format specifier returns the date by using the long date pattern.</span></span> <span data-ttu-id="51c72-115">Además, el especificador de formato "M" [personalizado](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx) devuelve los meses del 1 al 12, mientras que el especificador de formato personalizado "m" devuelve los minutos del 0 al 59.</span><span class="sxs-lookup"><span data-stu-id="51c72-115">Additionally, the [custom](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx) "M" format specifier returns the month from 1 through 12, whereas the custom "m" format specifier returns the minute from 0 through 59.</span></span>

<span data-ttu-id="51c72-116">`culture`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="51c72-116">`culture`: *String*</span></span>

<span data-ttu-id="51c72-117">La cultura a utilizar para formatear.</span><span class="sxs-lookup"><span data-stu-id="51c72-117">The culture to use for formatting.</span></span>

## <a name="return-values"></a><span data-ttu-id="51c72-118">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="51c72-118">Return values</span></span>

<span data-ttu-id="51c72-119">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="51c72-119">*String*</span></span>

<span data-ttu-id="51c72-120">El valor de cadena resultante.</span><span class="sxs-lookup"><span data-stu-id="51c72-120">The resulting string value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="51c72-121">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="51c72-121">Usage notes</span></span>

<span data-ttu-id="51c72-122">Si la cultura no se define como un argumento de la función llamada, el valor de `culture` está definido por el contexto de llamada.</span><span class="sxs-lookup"><span data-stu-id="51c72-122">If the culture isn't defined as an argument of the called function, the value of `culture` is defined by the calling context.</span></span> <span data-ttu-id="51c72-123">Por ejemplo, si la función `DATETIMEFORMAT` se llama mediante el uso de la sintaxis 1 en un formato de informe electrónico (ER) para un elemento **ARCHIVO** configurado para usar la cultura alemana, la conversión se realizará utilizando la cultura alemana.</span><span class="sxs-lookup"><span data-stu-id="51c72-123">For example, if the `DATETIMEFORMAT` function is called by using syntax 1 in an Electronic reporting (ER) format for a **FILE** element that is configured to use the German culture, the conversion will be done by using the German culture.</span></span> <span data-ttu-id="51c72-124">El valor de `culture` predeterminado es **EN-US**.</span><span class="sxs-lookup"><span data-stu-id="51c72-124">The default `culture` value is **EN-US**.</span></span>

<span data-ttu-id="51c72-125">Cuando la función `DATETIMEFORMAT` convierte un valor de fecha / hora dado, considera la configuración de zona horaria del usuario de la aplicación que ejecuta el formato ER al que se llama la función en el contexto.</span><span class="sxs-lookup"><span data-stu-id="51c72-125">When the `DATETIMEFORMAT` function converts a given date/time value, it considers the time zone setting of the application user who is running the ER format that the function is called in the context of.</span></span>

## <a name="example-1"></a><span data-ttu-id="51c72-126">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="51c72-126">Example 1</span></span>

<span data-ttu-id="51c72-127">`DATETIMEFORMAT (NOW(), "dd-MM-yyyy")` devuelve la fecha/hora del servidor actual, 24 de diciembre de 2015, como **“24-12-2015”**, basado en el formato personalizado especificado.</span><span class="sxs-lookup"><span data-stu-id="51c72-127">`DATETIMEFORMAT (NOW(), "dd-MM-yyyy")` returns the current application server date/time value, December 24, 2015, as **"24-12-2015"**, based on the specified custom format.</span></span>

## <a name="example-2"></a><span data-ttu-id="51c72-128">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="51c72-128">Example 2</span></span>

<span data-ttu-id="51c72-129">`DATETIMEFORMAT (SESSIONNOW(), "d", "DE")` devuelve la fecha/hora de sesión de la aplicación actual, 24 de diciembre de 2015, como la cadena **"24.12.2015"**, basado en la cultura alemana seleccionada y el formato especificado.</span><span class="sxs-lookup"><span data-stu-id="51c72-129">`DATETIMEFORMAT (SESSIONNOW(), "d", "DE")` returns the current application session date/time value, December 24, 2015, as **"24.12.2015"**, based on the selected German culture and the specified format.</span></span>

## <a name="example-3"></a><span data-ttu-id="51c72-130">Ejemplo 3</span><span class="sxs-lookup"><span data-stu-id="51c72-130">Example 3</span></span>

<span data-ttu-id="51c72-131">`DATETIMEFORMAT (DATETIMEVALUE( "2019-11-12T09:00:00.0000000-07:00", "O"), "O")` devuelve el valor de la cadena **2019-11-12T08:00:00.0000000-08:00** cuando se llama a la función durante un proceso iniciado por un usuario de la aplicación que tiene el valor de zona horaria **(GMT-08: 00) Hora del Pacífico (EE. UU. y Canadá)** en la sección **Preferencias de idioma y país / región**.</span><span class="sxs-lookup"><span data-stu-id="51c72-131">`DATETIMEFORMAT (DATETIMEVALUE( "2019-11-12T09:00:00.0000000-07:00", "O"), "O")` returns the string value **2019-11-12T08:00:00.0000000-08:00** when the function is called during a process that was initiated by an application user who has the time zone value **(GMT-08:00) Pacific Time (US & Canada)** in the **Language and country/region preferences** section.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="51c72-132">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="51c72-132">Additional resources</span></span>

[<span data-ttu-id="51c72-133">Funciones de fecha y de tiempo</span><span class="sxs-lookup"><span data-stu-id="51c72-133">Date and time functions</span></span>](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]