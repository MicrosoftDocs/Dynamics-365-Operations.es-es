---
title: Función DATETIMEVALUE ER
description: Este tema proporciona información general sobre cómo usar la función DATETIMEVALUE de informes electrónicos (ER).
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
ms.openlocfilehash: de601ad08b85797a4241ef74ecb3eba37eda37ca
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917543"
---
# <span data-ttu-id="723fa-103"><a name="DATETIMEVALUE">Función DATETIMEVALUE ER</a></span><span class="sxs-lookup"><span data-stu-id="723fa-103"><a name="DATETIMEVALUE">DATETIMEVALUE ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="723fa-104">La función `DATETIMEVALUE` devuelve un valor *Fecha y hora* que se convierte de un determinado valor de texto en el formato especificado y en una [cultura](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes) opcionalmente especificada a un valor de fecha / hora.</span><span class="sxs-lookup"><span data-stu-id="723fa-104">The `DATETIMEVALUE` function returns a *DateTime* value that is converted from a given text value in the specified format and in an optionally specified [culture](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes) to a date/time value.</span></span> <span data-ttu-id="723fa-105">Para obtener información acerca de los formatos admitidos, vea [estándar](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) y [personalizado](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).</span><span class="sxs-lookup"><span data-stu-id="723fa-105">For information about the supported formats, see [standard](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) and [custom](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).</span></span>

## <a name="syntax-1"></a><span data-ttu-id="723fa-106">Sintaxis 1</span><span class="sxs-lookup"><span data-stu-id="723fa-106">Syntax 1</span></span>

```
DATETIMEVALUE (text, format)
```

## <a name="syntax-2"></a><span data-ttu-id="723fa-107">Sintaxis 2</span><span class="sxs-lookup"><span data-stu-id="723fa-107">Syntax 2</span></span>

```
DATETIMEVALUE (text, format, culture)
```

## <a name="arguments"></a><span data-ttu-id="723fa-108">Argumentos</span><span class="sxs-lookup"><span data-stu-id="723fa-108">Arguments</span></span>

<span data-ttu-id="723fa-109">`text`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="723fa-109">`text`: *String*</span></span>

<span data-ttu-id="723fa-110">Texto que representa el valor a formatear.</span><span class="sxs-lookup"><span data-stu-id="723fa-110">Text that represents the value to format.</span></span>

<span data-ttu-id="723fa-111">`format`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="723fa-111">`format`: *String*</span></span>

<span data-ttu-id="723fa-112">El formato del texto proporcionado.</span><span class="sxs-lookup"><span data-stu-id="723fa-112">The format of the given text.</span></span>

<span data-ttu-id="723fa-113">`culture`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="723fa-113">`culture`: *String*</span></span>

<span data-ttu-id="723fa-114">La cultura que se utiliza para formatear el texto dado.</span><span class="sxs-lookup"><span data-stu-id="723fa-114">The culture that is used for formatting of the given text.</span></span>

## <a name="return-values"></a><span data-ttu-id="723fa-115">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="723fa-115">Return values</span></span>

<span data-ttu-id="723fa-116">*DateTime*</span><span class="sxs-lookup"><span data-stu-id="723fa-116">*DateTime*</span></span>

<span data-ttu-id="723fa-117">El valor de fecha/hora resultante.</span><span class="sxs-lookup"><span data-stu-id="723fa-117">The resulting date/time value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="723fa-118">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="723fa-118">Usage notes</span></span>

<span data-ttu-id="723fa-119">Cuando la cultura no se define como un argumento de la función llamada, el valor de `culture` está definido por el contexto de llamada.</span><span class="sxs-lookup"><span data-stu-id="723fa-119">When the culture isn't defined as an argument of the called function, the value of `culture` is defined by the calling context.</span></span> <span data-ttu-id="723fa-120">Por ejemplo, si la función `DATETIMEVALUE` se llama mediante el uso de la sintaxis 1 en un formato de informe electrónico (ER) para un elemento **ARCHIVO** configurado para usar la cultura alemana, la conversión se realizará utilizando la cultura alemana.</span><span class="sxs-lookup"><span data-stu-id="723fa-120">For example, if the `DATETIMEVALUE` function is called by using syntax 1 in an Electronic reporting (ER) format for a **FILE** element that is configured to use the German culture, the conversion will be done by using the German culture.</span></span> <span data-ttu-id="723fa-121">El valor de `culture` predeterminado es **EN-US**.</span><span class="sxs-lookup"><span data-stu-id="723fa-121">The default `culture` value is **EN-US**.</span></span>

## <a name="example-1"></a><span data-ttu-id="723fa-122">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="723fa-122">Example 1</span></span>

<span data-ttu-id="723fa-123">`DATETIMEVALUE ("21-Dec-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss")` devuelve la **2:55:00 AM del 21 de diciembre de 2016** basada el formato especificado y la cultura predeterminada **EN-US** de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="723fa-123">`DATETIMEVALUE ("21-Dec-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss")` returns **2:55:00 AM on December 21, 2016**, based on the specified custom format and the default application's **EN-US** culture.</span></span>

## <a name="example-2"></a><span data-ttu-id="723fa-124">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="723fa-124">Example 2</span></span>

<span data-ttu-id="723fa-125">`DATETIMEVALUE ("21-Gen-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss", "IT")` devuelve **2:55:00 a.m. del 21 de diciembre de 2016**, según el formato y la cultura personalizados especificados.</span><span class="sxs-lookup"><span data-stu-id="723fa-125">`DATETIMEVALUE ("21-Gen-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss", "IT")` returns **2:55:00 AM on December 21, 2016**, based on the specified custom format and culture.</span></span>

<span data-ttu-id="723fa-126">Sin embargo, `DATETIMEVALUE ("21-Gen-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss", "EN-US")` lanza una excepción para informar al usuario de que la cadena especificada no se reconoce como valor fecha/hora válido para la cultura especificada.</span><span class="sxs-lookup"><span data-stu-id="723fa-126">However, `DATETIMEVALUE ("21-Gen-2016 02:55:00", "dd-MMM-yyyy hh:mm:ss", "EN-US")` throws an exception to inform the user that the specified string isn't recognized as a valid date/time value for the specified culture.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="723fa-127">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="723fa-127">Additional resources</span></span>

[<span data-ttu-id="723fa-128">Funciones de fecha y de tiempo</span><span class="sxs-lookup"><span data-stu-id="723fa-128">Date and time functions</span></span>](er-functions-category-datetime.md)