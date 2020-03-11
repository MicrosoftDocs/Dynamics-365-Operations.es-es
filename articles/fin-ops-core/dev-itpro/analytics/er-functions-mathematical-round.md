---
title: Función ROUND de ER
description: Este tema proporciona información general sobre cómo usar la función ROUND de informes electrónicos (ER).
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
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6751c1321fc71419fa8b153145a057371e0f7af5
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041616"
---
# <span data-ttu-id="b573c-103"><a name="ROUND">Función ROUND de ER</a></span><span class="sxs-lookup"><span data-stu-id="b573c-103"><a name="ROUND">ROUND ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b573c-104">La función `ROUND` devuelve el número especificado como un valor *Real* después de que se haya redondeado al número especificado de posiciones decimales.</span><span class="sxs-lookup"><span data-stu-id="b573c-104">The `ROUND` function returns the specified number as a *Real* value after it has been rounded to the specified number of decimal places.</span></span>

## <a name="syntax"></a><span data-ttu-id="b573c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b573c-105">Syntax</span></span>

```vb
ROUND (number, decimals)
```

## <a name="arguments"></a><span data-ttu-id="b573c-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="b573c-106">Arguments</span></span>

<span data-ttu-id="b573c-107">`number`: *Real*</span><span class="sxs-lookup"><span data-stu-id="b573c-107">`number`: *Real*</span></span>

<span data-ttu-id="b573c-108">Un valor numérico que debe redondearse.</span><span class="sxs-lookup"><span data-stu-id="b573c-108">A numeric value that must be rounded.</span></span>

<span data-ttu-id="b573c-109">`decimals`: *Entero*</span><span class="sxs-lookup"><span data-stu-id="b573c-109">`decimals`: *Integer*</span></span>

<span data-ttu-id="b573c-110">Un valor numérico que representa el número de lugares decimales.</span><span class="sxs-lookup"><span data-stu-id="b573c-110">A numeric value that represents the number of decimal places.</span></span>

## <a name="return-values"></a><span data-ttu-id="b573c-111">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="b573c-111">Return values</span></span>

<span data-ttu-id="b573c-112">*Real*</span><span class="sxs-lookup"><span data-stu-id="b573c-112">*Real*</span></span>

<span data-ttu-id="b573c-113">El valor numérico resultante.</span><span class="sxs-lookup"><span data-stu-id="b573c-113">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="b573c-114">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="b573c-114">Usage notes</span></span>

<span data-ttu-id="b573c-115">Si el valor del argumento `decimals` es superior a 0 (cero), el número especificado se redondea a ese número de decimales.</span><span class="sxs-lookup"><span data-stu-id="b573c-115">If the value of the `decimals` argument is more than 0 (zero), the specified number is rounded to that many decimal places.</span></span>

<span data-ttu-id="b573c-116">Si el valor del argumento `decimals` es **0** (cero), el número especificado se redondea al número entero más cercano.</span><span class="sxs-lookup"><span data-stu-id="b573c-116">If the value of the `decimals` argument is **0** (zero), the specified number is rounded to the nearest integer.</span></span>

<span data-ttu-id="b573c-117">Si el valor del argumento `decimals` es inferior a 0 (cero), el número especificado se redondea a la izquierda de la coma decimal.</span><span class="sxs-lookup"><span data-stu-id="b573c-117">If the value of the `decimals` argument is less than 0 (zero), the specified number is rounded to the left of the decimal point.</span></span>

## <a name="example-1"></a><span data-ttu-id="b573c-118">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="b573c-118">Example 1</span></span>

<span data-ttu-id="b573c-119">`ROUND (1200.767, 2)` redondea a dos lugares decimales y devuelve **1200,77**.</span><span class="sxs-lookup"><span data-stu-id="b573c-119">`ROUND (1200.767, 2)` rounds to two decimal places and returns **1200.77**.</span></span>

## <a name="example-2"></a><span data-ttu-id="b573c-120">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="b573c-120">Example 2</span></span>

<span data-ttu-id="b573c-121">`ROUND (1200.767, -3)` redondea al múltiplo más cercano de 1000 y devuelve **1000**.</span><span class="sxs-lookup"><span data-stu-id="b573c-121">`ROUND (1200.767, -3)` rounds to the nearest multiple of 1,000 and returns **1000**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b573c-122">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="b573c-122">Additional resources</span></span>

[<span data-ttu-id="b573c-123">Funciones matemáticas</span><span class="sxs-lookup"><span data-stu-id="b573c-123">Mathematical functions</span></span>](er-functions-category-mathematical.md)
