---
title: Función DATEFORMAT ER
description: En este tema se proporciona información sobre cómo usar la función DATEFORMAT de informes electrónicos (ER).
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
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c1453be0c93764f9f0364206822a9e3899061a58
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917589"
---
# <span data-ttu-id="0ca77-103"><a name="DATEFORMAT">Función DATEFORMAT ER</a></span><span class="sxs-lookup"><span data-stu-id="0ca77-103"><a name="DATEFORMAT">DATEFORMAT ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0ca77-104">La función `DATEFORMAT` devuelve un valor *Cadena* que presenta un valor determinado de fecha como texto en el formato especificado y en una [cultura](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes) opcional especificada.</span><span class="sxs-lookup"><span data-stu-id="0ca77-104">The `DATEFORMAT` function returns a *String* value that presents a given date value as text in the specified format and in an optionally specified [culture](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes).</span></span> <span data-ttu-id="0ca77-105">Para obtener información acerca de los formatos admitidos, vea [estándar](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) y [personalizado](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).</span><span class="sxs-lookup"><span data-stu-id="0ca77-105">For information about the supported formats, see [standard](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) and [custom](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).</span></span>

## <a name="syntax-1"></a><span data-ttu-id="0ca77-106">Sintaxis 1</span><span class="sxs-lookup"><span data-stu-id="0ca77-106">Syntax 1</span></span>

```
DATEFORMAT (date, format)
```

## <a name="syntax-2"></a><span data-ttu-id="0ca77-107">Sintaxis 2</span><span class="sxs-lookup"><span data-stu-id="0ca77-107">Syntax 2</span></span>

```
DATEFORMAT (date, format, culture)
```

## <a name="arguments"></a><span data-ttu-id="0ca77-108">Argumentos</span><span class="sxs-lookup"><span data-stu-id="0ca77-108">Arguments</span></span>

<span data-ttu-id="0ca77-109">`date`: *Fecha*</span><span class="sxs-lookup"><span data-stu-id="0ca77-109">`date`: *Date*</span></span>

<span data-ttu-id="0ca77-110">Un valor de fecha / hora que representa la fecha a formatear.</span><span class="sxs-lookup"><span data-stu-id="0ca77-110">A date value that represents the date to format.</span></span>

<span data-ttu-id="0ca77-111">`format`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="0ca77-111">`format`: *String*</span></span>

<span data-ttu-id="0ca77-112">El formato de la cadena de salida.</span><span class="sxs-lookup"><span data-stu-id="0ca77-112">The format of the output string.</span></span>

<span data-ttu-id="0ca77-113">`culture`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="0ca77-113">`culture`: *String*</span></span>

<span data-ttu-id="0ca77-114">La cultura a utilizar para formatear.</span><span class="sxs-lookup"><span data-stu-id="0ca77-114">The culture to use for formatting.</span></span>

## <a name="return-values"></a><span data-ttu-id="0ca77-115">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="0ca77-115">Return values</span></span>

<span data-ttu-id="0ca77-116">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="0ca77-116">*String*</span></span>

<span data-ttu-id="0ca77-117">El valor de cadena resultante.</span><span class="sxs-lookup"><span data-stu-id="0ca77-117">The resulting string value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="0ca77-118">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="0ca77-118">Usage notes</span></span>

<span data-ttu-id="0ca77-119">Cuando la cultura no se define como un argumento de la función llamada, el valor de `culture` está definido por el contexto de llamada.</span><span class="sxs-lookup"><span data-stu-id="0ca77-119">When the culture isn't defined as an argument of the called function, the value of `culture` is defined by the calling context.</span></span> <span data-ttu-id="0ca77-120">Por ejemplo, si la función `DATEFORMAT` se llama mediante el uso de la sintaxis 1 en un formato de informe electrónico (ER) para un elemento **ARCHIVO** configurado para usar la cultura alemana, la conversión se realizará utilizando la cultura alemana.</span><span class="sxs-lookup"><span data-stu-id="0ca77-120">For example, if the `DATEFORMAT` function is called by using syntax 1 in an Electronic reporting (ER) format for a **FILE** element that is configured to use the German culture, the conversion will be done by using the German culture.</span></span> <span data-ttu-id="0ca77-121">El valor de `culture` predeterminado es **EN-US**.</span><span class="sxs-lookup"><span data-stu-id="0ca77-121">The default `culture` value is **EN-US**.</span></span>

## <a name="example-1"></a><span data-ttu-id="0ca77-122">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="0ca77-122">Example 1</span></span>

<span data-ttu-id="0ca77-123">`DATEFORMAT (TODAY (), "dd-MM-yyyy")` devuelve la fecha del servidor actual, 24 de diciembre de 2015, como la cadena **“24-12-2015”**, basado en el formato personalizado especificado.</span><span class="sxs-lookup"><span data-stu-id="0ca77-123">`DATEFORMAT (TODAY (), "dd-MM-yyyy")` returns the current application server date, December 24, 2015, as the string **"24-12-2015"**, based on the specified custom format.</span></span>

## <a name="example-2"></a><span data-ttu-id="0ca77-124">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="0ca77-124">Example 2</span></span>

<span data-ttu-id="0ca77-125">`DATEFORMAT (SESSIONTODAY (), "d", "DE")` devuelve la fecha de sesión de la aplicación actual, 24 de diciembre de 2015, como la cadena **"24-12-2015"**, basado en la cultura alemana seleccionada y el formato especificado.</span><span class="sxs-lookup"><span data-stu-id="0ca77-125">`DATEFORMAT (SESSIONTODAY (), "d", "DE")` returns the current application session date, December 24, 2015, as the string  **"24-12-2015"**, based on the selected German culture and the specified format.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0ca77-126">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="0ca77-126">Additional resources</span></span>

[<span data-ttu-id="0ca77-127">Funciones de fecha y de tiempo</span><span class="sxs-lookup"><span data-stu-id="0ca77-127">Date and time functions</span></span>](er-functions-category-datetime.md)
