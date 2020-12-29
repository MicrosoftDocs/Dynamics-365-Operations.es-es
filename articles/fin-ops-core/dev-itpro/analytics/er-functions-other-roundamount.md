---
title: Función ROUNDAMOUNT de ER
description: En este tema se proporciona información sobre cómo usar la función ROUNDAMOUNT de informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: 15a84b086b324ec390d88e8b2617022ad4773977
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "4683072"
---
# <a name="roundamount-er-function"></a><span data-ttu-id="bd2cd-103">Función ROUNDAMOUNT de ER</span><span class="sxs-lookup"><span data-stu-id="bd2cd-103">ROUNDAMOUNT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="bd2cd-104">La función `ROUNDAMOUNT` devuelve un valor de tipo *Real* que representa el resultado de redondear la cantidad especificada al múltiplo más cercano de otro número, de acuerdo con la regla de redondeo especificada.</span><span class="sxs-lookup"><span data-stu-id="bd2cd-104">The `ROUNDAMOUNT` function returns a *Real* value as the result of the rounding of the specified number to the nearest multiple of another number according to the specified rounding rule.</span></span>

## <a name="syntax"></a><span data-ttu-id="bd2cd-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bd2cd-105">Syntax</span></span>

```vb
ROUNDAMOUNT (number, decimals, round rule)
```

## <a name="arguments"></a><span data-ttu-id="bd2cd-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="bd2cd-106">Arguments</span></span>

<span data-ttu-id="bd2cd-107">`number`: *Entero* o *Real*</span><span class="sxs-lookup"><span data-stu-id="bd2cd-107">`number`: *Int* or *Real*</span></span>

<span data-ttu-id="bd2cd-108">Un valor numérico que debe redondearse.</span><span class="sxs-lookup"><span data-stu-id="bd2cd-108">A numeric value that must be rounded.</span></span>

<span data-ttu-id="bd2cd-109">`decimals`: *Entero* o *Real*</span><span class="sxs-lookup"><span data-stu-id="bd2cd-109">`decimals`: *Int* or *Real*</span></span>

<span data-ttu-id="bd2cd-110">El número a cuyo múltiplo se debe redondear el valor del parámetro `number`.</span><span class="sxs-lookup"><span data-stu-id="bd2cd-110">The number that the value of the `number` parameter must be rounded to a multiple of.</span></span>

<span data-ttu-id="bd2cd-111">`round rule`: *Valor de enumeración*</span><span class="sxs-lookup"><span data-stu-id="bd2cd-111">`round rule`: *Enum value*</span></span>

<span data-ttu-id="bd2cd-112">Un valor de enumeración de la enumeración **RoundOffType** que define la regla de redondeo.</span><span class="sxs-lookup"><span data-stu-id="bd2cd-112">An enumeration value of the **RoundOffType** enumeration that defines the rounding rule.</span></span> <span data-ttu-id="bd2cd-113">Esta enumeración ofrece los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="bd2cd-113">This enumeration offers the following values:</span></span>

- <span data-ttu-id="bd2cd-114">Normal (ordinario)</span><span class="sxs-lookup"><span data-stu-id="bd2cd-114">Normal (Ordinary)</span></span>
- <span data-ttu-id="bd2cd-115">Hacia abajo (RoundDown)</span><span class="sxs-lookup"><span data-stu-id="bd2cd-115">Downward (RoundDown)</span></span>
- <span data-ttu-id="bd2cd-116">Hacia arriba (RoundUp)</span><span class="sxs-lookup"><span data-stu-id="bd2cd-116">Rounding-up (RoundUp)</span></span>

## <a name="return-values"></a><span data-ttu-id="bd2cd-117">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="bd2cd-117">Return values</span></span>

<span data-ttu-id="bd2cd-118">*Real*</span><span class="sxs-lookup"><span data-stu-id="bd2cd-118">*Real*</span></span>

<span data-ttu-id="bd2cd-119">El valor numérico resultante es un múltiplo del valor especificado por el parámetro `decimals` y es el más cercano al valor especificado por el parámetro `number`.</span><span class="sxs-lookup"><span data-stu-id="bd2cd-119">The resulting numeric value is a multiple of the value specified by the `decimals` parameter and is closest to the value specified by the `number` parameter.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="bd2cd-120">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="bd2cd-120">Usage notes</span></span>

<span data-ttu-id="bd2cd-121">Cuando el valor del parámetro `number` es cero, esta función siempre devuelve cero.</span><span class="sxs-lookup"><span data-stu-id="bd2cd-121">When the `number` parameter is zero, this function always returns zero.</span></span>

<span data-ttu-id="bd2cd-122">Cuando el valor del parámetro `decimals` es cero, esta función se redondea al valor de redondeo predeterminado.</span><span class="sxs-lookup"><span data-stu-id="bd2cd-122">When the `decimals` parameter is zero, this function rounds to the default round-off value.</span></span> <span data-ttu-id="bd2cd-123">Cuando el parámetro `round rule` se establece en **RoundOffType.Ordinary**, el valor de redondeo predeterminado es **0.01**.</span><span class="sxs-lookup"><span data-stu-id="bd2cd-123">When the `round rule` parameter is set to **RoundOffType.Ordinary**, the default round-off value is **0.01**.</span></span> <span data-ttu-id="bd2cd-124">De lo contrario, el valor de redondeo predeterminado es **1.0**.</span><span class="sxs-lookup"><span data-stu-id="bd2cd-124">Otherwise, the default round-off value is **1.0**.</span></span>

<span data-ttu-id="bd2cd-125">Cuando el parámetro `round rule` se establece en **RoundOffType.Ordinary**, esta función redondea a la cantidad de redondeo más cercana.</span><span class="sxs-lookup"><span data-stu-id="bd2cd-125">When the `round rule` parameter is set to **RoundOffType.Ordinary**, this function rounds to the nearest round-off amount.</span></span>

<span data-ttu-id="bd2cd-126">Cuando el parámetro `round rule` se establece en **RoundOffType.RoundDown**, esta función redondea hacia abajo a la cantidad de redondeo más cercana.</span><span class="sxs-lookup"><span data-stu-id="bd2cd-126">When the `round rule` parameter is set to **RoundOffType.RoundDown**, this function rounds towards zero to the nearest round-off amount.</span></span>

<span data-ttu-id="bd2cd-127">Cuando el parámetro `round rule` se establece en **RoundOffType.RoundUp**, esta función redondea hacia arriba a la cantidad de redondeo más cercana.</span><span class="sxs-lookup"><span data-stu-id="bd2cd-127">When the `round rule` parameter is set to **RoundOffType.RoundUp**, this function rounds away from zero to the nearest round-off amount.</span></span>

<span data-ttu-id="bd2cd-128">Cuando el parámetro `round rule` se establece en **RoundOffType.Ordinary**, esta función se comporta como la función de Excel [MROUND](https://support.office.com/article/mround-function-c299c3b0-15a5-426d-aa4b-d2d5b3baf427) y la función de X++ [ROUND](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/dev-ref/xpp-math-run-time-functions#round).</span><span class="sxs-lookup"><span data-stu-id="bd2cd-128">When the `round rule` parameter is set to **RoundOffType.Ordinary**, this function behaves like the [MROUND](https://support.office.com/article/mround-function-c299c3b0-15a5-426d-aa4b-d2d5b3baf427) Excel function and the [ROUND](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/dev-ref/xpp-math-run-time-functions#round) X++ function.</span></span>

## <a name="remarks"></a><span data-ttu-id="bd2cd-129">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bd2cd-129">Remarks</span></span>

<span data-ttu-id="bd2cd-130">Para redondear un valor numérico a un número específico de posiciones decimales, use la función [ROUND](er-functions-mathematical-round.md).</span><span class="sxs-lookup"><span data-stu-id="bd2cd-130">To round a numeric value to a specified number of decimal places, use the [ROUND](er-functions-mathematical-round.md) function.</span></span>

## <a name="example"></a><span data-ttu-id="bd2cd-131">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bd2cd-131">Example</span></span>

<span data-ttu-id="bd2cd-132">Si el parámetro **model.RoundOff** se establece en **RoundOffType.Ordinary**, `ROUNDAMOUNT (7.45, 1.05, model.RoundOff)` devuelve 7.35.</span><span class="sxs-lookup"><span data-stu-id="bd2cd-132">If the **model.RoundOff** parameter is set to **RoundOffType.Ordinary**, `ROUNDAMOUNT (7.45, 1.05, model.RoundOff)` returns 7.35.</span></span> 

<span data-ttu-id="bd2cd-133">Si el parámetro **model.RoundOff** se establece en **RoundOffType.RoundDown**, `ROUNDAMOUNT (7.45, 1.05, model.RoundOff)` devuelve 7.35.</span><span class="sxs-lookup"><span data-stu-id="bd2cd-133">If the **model.RoundOff** parameter is set to **RoundOffType.RoundDown**, `ROUNDAMOUNT (7.45, 1.05, model.RoundOff)` returns 7.35.</span></span> 

<span data-ttu-id="bd2cd-134">Si el parámetro **model.RoundOff** se establece en **RoundOffType.RoundUp**, `ROUNDAMOUNT (7.45, 1.05, model.RoundOff)` devuelve 8.4.</span><span class="sxs-lookup"><span data-stu-id="bd2cd-134">If the **model.RoundOff** parameter is set to **RoundOffType.RoundUp**, `ROUNDAMOUNT (7.45, 1.05, model.RoundOff)` returns 8.4.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="bd2cd-135">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="bd2cd-135">Additional resources</span></span>

[<span data-ttu-id="bd2cd-136">Otras funciones (específicas de dominio empresarial)</span><span class="sxs-lookup"><span data-stu-id="bd2cd-136">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)

[<span data-ttu-id="bd2cd-137">Funciones matemáticas</span><span class="sxs-lookup"><span data-stu-id="bd2cd-137">Mathematical functions</span></span>](er-functions-category-mathematical.md)
