---
title: Función DATEVALUE ER
description: Este tema proporciona información general sobre cómo usar la función DATEVALUE de informes electrónicos (ER).
author: NickSelin
ms.date: 12/04/2019
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
ms.openlocfilehash: cfaf183c61d3663442cbc244239b872b9e1957bb
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "5891242"
---
# <a name="datevalue-er-function"></a><span data-ttu-id="f0604-103">Función DATEVALUE ER</span><span class="sxs-lookup"><span data-stu-id="f0604-103">DATEVALUE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f0604-104">La función `DATEVALUE` devuelve un valor *Fecha* que se convierte de un determinado valor de texto en el formato especificado y en una [cultura](/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes) opcionalmente especificada a un valor de fecha.</span><span class="sxs-lookup"><span data-stu-id="f0604-104">The `DATEVALUE` function returns a *Date* value that is converted from a given text value in the specified format and in an optionally specified [culture](/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes) to a date value.</span></span> <span data-ttu-id="f0604-105">Para obtener información acerca de los formatos admitidos, vea [estándar](/dotnet/standard/base-types/standard-date-and-time-format-strings) y [personalizado](/dotnet/standard/base-types/custom-date-and-time-format-strings).</span><span class="sxs-lookup"><span data-stu-id="f0604-105">For information about the supported formats, see [standard](/dotnet/standard/base-types/standard-date-and-time-format-strings) and [custom](/dotnet/standard/base-types/custom-date-and-time-format-strings).</span></span>

## <a name="syntax-1"></a><span data-ttu-id="f0604-106">Sintaxis 1</span><span class="sxs-lookup"><span data-stu-id="f0604-106">Syntax 1</span></span>

```vb
DATEVALUE (text, format)
```

## <a name="syntax-2"></a><span data-ttu-id="f0604-107">Sintaxis 2</span><span class="sxs-lookup"><span data-stu-id="f0604-107">Syntax 2</span></span>

```vb
DATEVALUE (text, format, culture)
```

## <a name="arguments"></a><span data-ttu-id="f0604-108">Argumentos</span><span class="sxs-lookup"><span data-stu-id="f0604-108">Arguments</span></span>

<span data-ttu-id="f0604-109">`text`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="f0604-109">`text`: *String*</span></span>

<span data-ttu-id="f0604-110">Texto que representa el valor a formatear.</span><span class="sxs-lookup"><span data-stu-id="f0604-110">Text that represents the value to format.</span></span>

<span data-ttu-id="f0604-111">`format`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="f0604-111">`format`: *String*</span></span>

<span data-ttu-id="f0604-112">El formato del texto proporcionado.</span><span class="sxs-lookup"><span data-stu-id="f0604-112">The format of the given text.</span></span>

<span data-ttu-id="f0604-113">`culture`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="f0604-113">`culture`: *String*</span></span>

<span data-ttu-id="f0604-114">La cultura que se utiliza para formatear el texto dado.</span><span class="sxs-lookup"><span data-stu-id="f0604-114">The culture that is used for formatting of the given text.</span></span>

## <a name="return-values"></a><span data-ttu-id="f0604-115">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="f0604-115">Return values</span></span>

<span data-ttu-id="f0604-116">*Fecha*</span><span class="sxs-lookup"><span data-stu-id="f0604-116">*Date*</span></span>

<span data-ttu-id="f0604-117">El valor de fecha resultante.</span><span class="sxs-lookup"><span data-stu-id="f0604-117">The resulting date value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="f0604-118">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="f0604-118">Usage notes</span></span>

<span data-ttu-id="f0604-119">Cuando la cultura no se define como un argumento de la función llamada, el valor de `culture` está definido por el contexto de llamada.</span><span class="sxs-lookup"><span data-stu-id="f0604-119">When the culture isn't defined as an argument of the called function, the value of `culture` is defined by the calling context.</span></span> <span data-ttu-id="f0604-120">Por ejemplo, si la función `DATEVALUE` se llama mediante el uso de la sintaxis 1 en un formato de informe electrónico (ER) para un elemento **ARCHIVO** configurado para usar la cultura alemana, la conversión se realizará utilizando la cultura alemana.</span><span class="sxs-lookup"><span data-stu-id="f0604-120">For example, if the `DATEVALUE` function is called by using syntax 1 in an Electronic reporting (ER) format for a **FILE** element that is configured to use the German culture, the conversion will be done by using the German culture.</span></span> <span data-ttu-id="f0604-121">El valor de `culture` predeterminado es **EN-US**.</span><span class="sxs-lookup"><span data-stu-id="f0604-121">The default `culture` value is **EN-US**.</span></span>

## <a name="example-1"></a><span data-ttu-id="f0604-122">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="f0604-122">Example 1</span></span>

<span data-ttu-id="f0604-123">`DATEVALUE ("21-Dec-2016", "dd-MMM-yyyy")` devuelve la fecha **21 de diciembre de 2016** basada el formato especificado y la cultura predeterminada **EN-US** de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f0604-123">`DATEVALUE ("21-Dec-2016", "dd-MMM-yyyy")` returns the date value **December 21, 2016**, based on the specified custom format and the default application's **EN-US** culture.</span></span>

## <a name="example-2"></a><span data-ttu-id="f0604-124">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="f0604-124">Example 2</span></span>

<span data-ttu-id="f0604-125">`DATEVALUE ("21-Gen-2016", "dd-MMM-yyyy", "IT")` devuelve el valor de la fecha **21 de enero de 2016**, según el formato y la cultura personalizados especificados.</span><span class="sxs-lookup"><span data-stu-id="f0604-125">`DATEVALUE ("21-Gen-2016", "dd-MMM-yyyy", "IT")` returns the date value **January 21, 2016**, based on the specified custom format and culture.</span></span>

<span data-ttu-id="f0604-126">Sin embargo, `DATEVALUE ("21-Gen-2016", "dd-MMM-yyyy", "EN-US")` lanza una excepción para informar al usuario de que la cadena especificada no se reconoce como fecha válida para la cultura especificada.</span><span class="sxs-lookup"><span data-stu-id="f0604-126">However, `DATEVALUE ("21-Gen-2016", "dd-MMM-yyyy", "EN-US")` throws an exception to inform the user that the specified string isn't recognized as a valid date for the specified culture.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f0604-127">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="f0604-127">Additional resources</span></span>

[<span data-ttu-id="f0604-128">Funciones de fecha y de tiempo</span><span class="sxs-lookup"><span data-stu-id="f0604-128">Date and time functions</span></span>](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]