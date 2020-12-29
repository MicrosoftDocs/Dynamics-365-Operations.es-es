---
title: Función DATETIMEFORMAT ER
description: En este tema se proporciona información sobre cómo usar la función DATETIMEFORMAT de informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 12/03/2019
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
ms.openlocfilehash: d42767b814f36eb75b4a43d07c663b2dd1b2c879
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "4684963"
---
# <a name="datetimeformat-er-function"></a><span data-ttu-id="20059-103">Función DATETIMEFORMAT ER</span><span class="sxs-lookup"><span data-stu-id="20059-103">DATETIMEFORMAT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="20059-104">La función `DATETIMEFORMAT` devuelve un valor *Cadena* que presenta un valor determinado de fecha/hora como texto en el formato especificado y en una [cultura](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes) opcional especificada.</span><span class="sxs-lookup"><span data-stu-id="20059-104">The `DATETIMEFORMAT` function returns a *String* value that presents a given date/time value as text in the specified format and in an optionally specified [culture](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes).</span></span> <span data-ttu-id="20059-105">Para obtener información acerca de los formatos admitidos, vea [estándar](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) y [personalizado](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).</span><span class="sxs-lookup"><span data-stu-id="20059-105">For information about the supported formats, see [standard](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) and [custom](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).</span></span>

## <a name="syntax-1"></a><span data-ttu-id="20059-106">Sintaxis 1</span><span class="sxs-lookup"><span data-stu-id="20059-106">Syntax 1</span></span>

```vb
DATETIMEFORMAT (datetime, format)
```

## <a name="syntax-2"></a><span data-ttu-id="20059-107">Sintaxis 2</span><span class="sxs-lookup"><span data-stu-id="20059-107">Syntax 2</span></span>

```vb
DATETIMEFORMAT (datetime, format, culture)
```

## <a name="arguments"></a><span data-ttu-id="20059-108">Argumentos</span><span class="sxs-lookup"><span data-stu-id="20059-108">Arguments</span></span>

<span data-ttu-id="20059-109">`datetime`: *Fecha y hora*</span><span class="sxs-lookup"><span data-stu-id="20059-109">`datetime`: *DateTime*</span></span>

<span data-ttu-id="20059-110">Un valor de fecha / hora que representa la fecha y la hora a formatear.</span><span class="sxs-lookup"><span data-stu-id="20059-110">A date/time value that represents the date and time to format.</span></span>

<span data-ttu-id="20059-111">`format`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="20059-111">`format`: *String*</span></span>

<span data-ttu-id="20059-112">El formato de la cadena de salida.</span><span class="sxs-lookup"><span data-stu-id="20059-112">The format of the output string.</span></span>

<span data-ttu-id="20059-113">`culture`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="20059-113">`culture`: *String*</span></span>

<span data-ttu-id="20059-114">La cultura a utilizar para formatear.</span><span class="sxs-lookup"><span data-stu-id="20059-114">The culture to use for formatting.</span></span>

## <a name="return-values"></a><span data-ttu-id="20059-115">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="20059-115">Return values</span></span>

<span data-ttu-id="20059-116">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="20059-116">*String*</span></span>

<span data-ttu-id="20059-117">El valor de cadena resultante.</span><span class="sxs-lookup"><span data-stu-id="20059-117">The resulting string value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="20059-118">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="20059-118">Usage notes</span></span>

<span data-ttu-id="20059-119">Cuando la cultura no se define como un argumento de la función llamada, el valor de `culture` está definido por el contexto de llamada.</span><span class="sxs-lookup"><span data-stu-id="20059-119">When the culture isn't defined as an argument of the called function, the value of `culture` is defined by the calling context.</span></span> <span data-ttu-id="20059-120">Por ejemplo, si la función `DATETIMEFORMAT` se llama mediante el uso de la sintaxis 1 en un formato de informe electrónico (ER) para un elemento **ARCHIVO** configurado para usar la cultura alemana, la conversión se realizará utilizando la cultura alemana.</span><span class="sxs-lookup"><span data-stu-id="20059-120">For example, if the `DATETIMEFORMAT` function is called by using syntax 1 in an Electronic reporting (ER) format for a **FILE** element that is configured to use the German culture, the conversion will be done by using the German culture.</span></span> <span data-ttu-id="20059-121">El valor de `culture` predeterminado es **EN-US**.</span><span class="sxs-lookup"><span data-stu-id="20059-121">The default `culture` value is **EN-US**.</span></span>

<span data-ttu-id="20059-122">Cuando la función `DATETIMEFORMAT` convierte un valor de fecha / hora dado, considera la configuración de zona horaria del usuario de la aplicación que ejecuta el formato ER al que se llama la función en el contexto.</span><span class="sxs-lookup"><span data-stu-id="20059-122">When the `DATETIMEFORMAT` function converts a given date/time value, it considers the time zone setting of the application user who is running the ER format that the function is called in the context of.</span></span>

## <a name="example-1"></a><span data-ttu-id="20059-123">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="20059-123">Example 1</span></span>

<span data-ttu-id="20059-124">`DATETIMEFORMAT (NOW(), "dd-MM-yyyy")` devuelve la fecha/hora del servidor actual, 24 de diciembre de 2015, como **“24-12-2015”**, basado en el formato personalizado especificado.</span><span class="sxs-lookup"><span data-stu-id="20059-124">`DATETIMEFORMAT (NOW(), "dd-MM-yyyy")` returns the current application server date/time value, December 24, 2015, as **"24-12-2015"**, based on the specified custom format.</span></span>

## <a name="example-2"></a><span data-ttu-id="20059-125">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="20059-125">Example 2</span></span>

<span data-ttu-id="20059-126">`DATETIMEFORMAT (SESSIONNOW(), "d", "DE")` devuelve la fecha/hora de sesión de la aplicación actual, 24 de diciembre de 2015, como la cadena **"24.12.2015"**, basado en la cultura alemana seleccionada y el formato especificado.</span><span class="sxs-lookup"><span data-stu-id="20059-126">`DATETIMEFORMAT (SESSIONNOW(), "d", "DE")` returns the current application session date/time value, December 24, 2015, as **"24.12.2015"**, based on the selected German culture and the specified format.</span></span>

## <a name="example-3"></a><span data-ttu-id="20059-127">Ejemplo 3</span><span class="sxs-lookup"><span data-stu-id="20059-127">Example 3</span></span>

<span data-ttu-id="20059-128">`DATETIMEFORMAT (DATETIMEVALUE( "2019-11-12T09:00:00.0000000-07:00", "O"), "O")` devuelve el valor de la cadena **2019-11-12T08:00:00.0000000-08:00** cuando se llama durante un proceso iniciado por un usuario de la aplicación que tiene el valor de zona horaria **(GMT-08: 00) Hora del Pacífico (EE. UU. Y Canadá)** en la sección **Preferencias de idioma y país / región**.</span><span class="sxs-lookup"><span data-stu-id="20059-128">`DATETIMEFORMAT (DATETIMEVALUE( "2019-11-12T09:00:00.0000000-07:00", "O"), "O")` returns the string value **2019-11-12T08:00:00.0000000-08:00** when it's called during a process that was initiated by an application user who has the time zone value **(GMT-08:00) Pacific Time (US & Canada)** in the **Language and country/region preferences** section.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="20059-129">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="20059-129">Additional resources</span></span>

[<span data-ttu-id="20059-130">Funciones de fecha y de tiempo</span><span class="sxs-lookup"><span data-stu-id="20059-130">Date and time functions</span></span>](er-functions-category-datetime.md)
