---
title: Función ROUND de ER
description: Este tema proporciona información general sobre cómo usar la función ROUND de informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 10/21/2020
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
ms.openlocfilehash: 83fb5c04938e0aba1277f2d6017d4b66208a8858
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "4683265"
---
# <a name="round-er-function"></a><span data-ttu-id="a7ade-103">Función ROUND de ER</span><span class="sxs-lookup"><span data-stu-id="a7ade-103">ROUND ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a7ade-104">La función `ROUND` devuelve el número especificado como un valor *Real* después de que se haya redondeado al número especificado de posiciones decimales.</span><span class="sxs-lookup"><span data-stu-id="a7ade-104">The `ROUND` function returns the specified number as a *Real* value after it has been rounded to the specified number of decimal places.</span></span>

## <a name="syntax"></a><span data-ttu-id="a7ade-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a7ade-105">Syntax</span></span>

```vb
ROUND (number, decimals)
```

## <a name="arguments"></a><span data-ttu-id="a7ade-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="a7ade-106">Arguments</span></span>

<span data-ttu-id="a7ade-107">`number`: *Real*</span><span class="sxs-lookup"><span data-stu-id="a7ade-107">`number`: *Real*</span></span>

<span data-ttu-id="a7ade-108">Un valor numérico que debe redondearse.</span><span class="sxs-lookup"><span data-stu-id="a7ade-108">A numeric value that must be rounded.</span></span>

<span data-ttu-id="a7ade-109">`decimals`: *Entero*</span><span class="sxs-lookup"><span data-stu-id="a7ade-109">`decimals`: *Integer*</span></span>

<span data-ttu-id="a7ade-110">Un valor numérico que representa el número de lugares decimales.</span><span class="sxs-lookup"><span data-stu-id="a7ade-110">A numeric value that represents the number of decimal places.</span></span>

## <a name="return-values"></a><span data-ttu-id="a7ade-111">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="a7ade-111">Return values</span></span>

<span data-ttu-id="a7ade-112">*Real*</span><span class="sxs-lookup"><span data-stu-id="a7ade-112">*Real*</span></span>

<span data-ttu-id="a7ade-113">El valor numérico resultante.</span><span class="sxs-lookup"><span data-stu-id="a7ade-113">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="a7ade-114">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="a7ade-114">Usage notes</span></span>

<span data-ttu-id="a7ade-115">Si el valor del argumento `decimals` es superior a 0 (cero), el número especificado se redondea a ese número de decimales.</span><span class="sxs-lookup"><span data-stu-id="a7ade-115">If the value of the `decimals` argument is more than 0 (zero), the specified number is rounded to that many decimal places.</span></span>

<span data-ttu-id="a7ade-116">Si el valor del argumento `decimals` es **0** (cero), el número especificado se redondea al número par entero más cercano.</span><span class="sxs-lookup"><span data-stu-id="a7ade-116">If the value of the `decimals` argument is **0** (zero), the specified number is rounded to the nearest even integer.</span></span>

<span data-ttu-id="a7ade-117">Si el valor del argumento `decimals` es inferior a 0 (cero), el número especificado se redondea a la izquierda de la coma decimal.</span><span class="sxs-lookup"><span data-stu-id="a7ade-117">If the value of the `decimals` argument is less than 0 (zero), the specified number is rounded to the left of the decimal point.</span></span>

## <a name="example-1"></a><span data-ttu-id="a7ade-118">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="a7ade-118">Example 1</span></span>

<span data-ttu-id="a7ade-119">`ROUND (1200.767, 2)` redondea a dos lugares decimales y devuelve **1200,77**.</span><span class="sxs-lookup"><span data-stu-id="a7ade-119">`ROUND (1200.767, 2)` rounds to two decimal places and returns **1200.77**.</span></span>

## <a name="example-2"></a><span data-ttu-id="a7ade-120">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="a7ade-120">Example 2</span></span>

<span data-ttu-id="a7ade-121">`ROUND (1200.767, -3)` redondea al múltiplo más cercano de 1000 y devuelve **1000**.</span><span class="sxs-lookup"><span data-stu-id="a7ade-121">`ROUND (1200.767, -3)` rounds to the nearest multiple of 1,000 and returns **1000**.</span></span>

## <a name="example-3"></a><span data-ttu-id="a7ade-122">Ejemplo 3</span><span class="sxs-lookup"><span data-stu-id="a7ade-122">Example 3</span></span>

<span data-ttu-id="a7ade-123">`ROUND (1200.5, 0)` redondea al entero par más cercano y devuelve **1200**, mientras `ROUND (1201.5, 0)` hace lo mismo y vuelve **1202**.</span><span class="sxs-lookup"><span data-stu-id="a7ade-123">`ROUND (1200.5, 0)` rounds to the nearest even integer and returns **1200**, while `ROUND (1201.5, 0)` does the same and returns **1202**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a7ade-124">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="a7ade-124">Additional resources</span></span>

[<span data-ttu-id="a7ade-125">Funciones matemáticas</span><span class="sxs-lookup"><span data-stu-id="a7ade-125">Mathematical functions</span></span>](er-functions-category-mathematical.md)
