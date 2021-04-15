---
title: Función ROUND de ER
description: Este tema proporciona información general sobre cómo usar la función ROUND de informes electrónicos (ER).
author: NickSelin
ms.date: 10/21/2020
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
ms.openlocfilehash: ce0f50cd5e544455626862e44b774dba39cf6e57
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5744496"
---
# <a name="round-er-function"></a><span data-ttu-id="0ffa7-103">Función ROUND de ER</span><span class="sxs-lookup"><span data-stu-id="0ffa7-103">ROUND ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0ffa7-104">La función `ROUND` devuelve el número especificado como un valor *Real* después de que se haya redondeado al número especificado de posiciones decimales.</span><span class="sxs-lookup"><span data-stu-id="0ffa7-104">The `ROUND` function returns the specified number as a *Real* value after it has been rounded to the specified number of decimal places.</span></span>

## <a name="syntax"></a><span data-ttu-id="0ffa7-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0ffa7-105">Syntax</span></span>

```vb
ROUND (number, decimals)
```

## <a name="arguments"></a><span data-ttu-id="0ffa7-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="0ffa7-106">Arguments</span></span>

<span data-ttu-id="0ffa7-107">`number`: *Real*</span><span class="sxs-lookup"><span data-stu-id="0ffa7-107">`number`: *Real*</span></span>

<span data-ttu-id="0ffa7-108">Un valor numérico que debe redondearse.</span><span class="sxs-lookup"><span data-stu-id="0ffa7-108">A numeric value that must be rounded.</span></span>

<span data-ttu-id="0ffa7-109">`decimals`: *Entero*</span><span class="sxs-lookup"><span data-stu-id="0ffa7-109">`decimals`: *Integer*</span></span>

<span data-ttu-id="0ffa7-110">Un valor numérico que representa el número de lugares decimales.</span><span class="sxs-lookup"><span data-stu-id="0ffa7-110">A numeric value that represents the number of decimal places.</span></span>

## <a name="return-values"></a><span data-ttu-id="0ffa7-111">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="0ffa7-111">Return values</span></span>

<span data-ttu-id="0ffa7-112">*Real*</span><span class="sxs-lookup"><span data-stu-id="0ffa7-112">*Real*</span></span>

<span data-ttu-id="0ffa7-113">El valor numérico resultante.</span><span class="sxs-lookup"><span data-stu-id="0ffa7-113">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="0ffa7-114">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="0ffa7-114">Usage notes</span></span>

<span data-ttu-id="0ffa7-115">Si el valor del argumento `decimals` es superior a 0 (cero), el número especificado se redondea a ese número de decimales.</span><span class="sxs-lookup"><span data-stu-id="0ffa7-115">If the value of the `decimals` argument is more than 0 (zero), the specified number is rounded to that many decimal places.</span></span>

<span data-ttu-id="0ffa7-116">Si el valor del argumento `decimals` es **0** (cero), el número especificado se redondea al número par entero más cercano.</span><span class="sxs-lookup"><span data-stu-id="0ffa7-116">If the value of the `decimals` argument is **0** (zero), the specified number is rounded to the nearest even integer.</span></span>

<span data-ttu-id="0ffa7-117">Si el valor del argumento `decimals` es inferior a 0 (cero), el número especificado se redondea a la izquierda de la coma decimal.</span><span class="sxs-lookup"><span data-stu-id="0ffa7-117">If the value of the `decimals` argument is less than 0 (zero), the specified number is rounded to the left of the decimal point.</span></span>

## <a name="example-1"></a><span data-ttu-id="0ffa7-118">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="0ffa7-118">Example 1</span></span>

<span data-ttu-id="0ffa7-119">`ROUND (1200.767, 2)` redondea a dos lugares decimales y devuelve **1200,77**.</span><span class="sxs-lookup"><span data-stu-id="0ffa7-119">`ROUND (1200.767, 2)` rounds to two decimal places and returns **1200.77**.</span></span>

## <a name="example-2"></a><span data-ttu-id="0ffa7-120">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="0ffa7-120">Example 2</span></span>

<span data-ttu-id="0ffa7-121">`ROUND (1200.767, -3)` redondea al múltiplo más cercano de 1000 y devuelve **1000**.</span><span class="sxs-lookup"><span data-stu-id="0ffa7-121">`ROUND (1200.767, -3)` rounds to the nearest multiple of 1,000 and returns **1000**.</span></span>

## <a name="example-3"></a><span data-ttu-id="0ffa7-122">Ejemplo 3</span><span class="sxs-lookup"><span data-stu-id="0ffa7-122">Example 3</span></span>

<span data-ttu-id="0ffa7-123">`ROUND (1200.5, 0)` redondea al entero par más cercano y devuelve **1200**, mientras `ROUND (1201.5, 0)` hace lo mismo y vuelve **1202**.</span><span class="sxs-lookup"><span data-stu-id="0ffa7-123">`ROUND (1200.5, 0)` rounds to the nearest even integer and returns **1200**, while `ROUND (1201.5, 0)` does the same and returns **1202**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0ffa7-124">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="0ffa7-124">Additional resources</span></span>

[<span data-ttu-id="0ffa7-125">Funciones matemáticas</span><span class="sxs-lookup"><span data-stu-id="0ffa7-125">Mathematical functions</span></span>](er-functions-category-mathematical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]