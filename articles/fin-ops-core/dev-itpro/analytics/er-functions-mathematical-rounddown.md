---
title: Función ROUNDDOWN de ER
description: Este tema proporciona información general sobre cómo usar la función ROUNDDOWN de informes electrónicos (ER).
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
ms.openlocfilehash: 7ac559983609d4fdb80c9ac70d84031e4a231889
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2020
ms.locfileid: "3744536"
---
# <a name="rounddown-er-function"></a><span data-ttu-id="28b98-103">Función ROUNDDOWN de ER</span><span class="sxs-lookup"><span data-stu-id="28b98-103">ROUNDDOWN ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="28b98-104">La función `ROUNDDOWN` devuelve el número especificado como un valor *Real* después de que se haya redondeado hacia abajo al número especificado de posiciones decimales.</span><span class="sxs-lookup"><span data-stu-id="28b98-104">The `ROUNDDOWN` function returns the specified number as a *Real* value after it has been rounded down to the specified number of decimal places.</span></span>

## <a name="syntax"></a><span data-ttu-id="28b98-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="28b98-105">Syntax</span></span>

```vb
ROUNDDOWN (number, decimals)
```

## <a name="arguments"></a><span data-ttu-id="28b98-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="28b98-106">Arguments</span></span>

<span data-ttu-id="28b98-107">`number`: *Real*</span><span class="sxs-lookup"><span data-stu-id="28b98-107">`number`: *Real*</span></span>

<span data-ttu-id="28b98-108">Un valor numérico que debe redondearse hacia abajo.</span><span class="sxs-lookup"><span data-stu-id="28b98-108">A numeric value that must be rounded down.</span></span>

<span data-ttu-id="28b98-109">`decimals`: *Entero*</span><span class="sxs-lookup"><span data-stu-id="28b98-109">`decimals`: *Integer*</span></span>

<span data-ttu-id="28b98-110">Un valor numérico que representa el número de lugares decimales.</span><span class="sxs-lookup"><span data-stu-id="28b98-110">A numeric value that represents the number of decimal places.</span></span>

## <a name="return-values"></a><span data-ttu-id="28b98-111">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="28b98-111">Return values</span></span>

<span data-ttu-id="28b98-112">*Real*</span><span class="sxs-lookup"><span data-stu-id="28b98-112">*Real*</span></span>

<span data-ttu-id="28b98-113">El valor numérico resultante.</span><span class="sxs-lookup"><span data-stu-id="28b98-113">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="28b98-114">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="28b98-114">Usage notes</span></span>

<span data-ttu-id="28b98-115">Esta función se comporta como [ROUND](er-functions-mathematical-round.md), pero siempre redondea hacia abajo del número especificado (hacia cero).</span><span class="sxs-lookup"><span data-stu-id="28b98-115">This function behaves like [ROUND](er-functions-mathematical-round.md), but it always rounds the specified number down (toward zero).</span></span>

## <a name="example-1"></a><span data-ttu-id="28b98-116">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="28b98-116">Example 1</span></span>

<span data-ttu-id="28b98-117">`ROUNDDOWN (1200.767, 2)` redondea hacia abajo a dos lugares decimales y devuelve **1200,76**.</span><span class="sxs-lookup"><span data-stu-id="28b98-117">`ROUNDDOWN (1200.767, 2)` rounds down to two decimal places and returns **1200.76**.</span></span> 

## <a name="example-2"></a><span data-ttu-id="28b98-118">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="28b98-118">Example 2</span></span>

<span data-ttu-id="28b98-119">`ROUNDDOWN (1700.767, -3)` redondea hacia abajo al múltiplo más cercano de 1000 y devuelve **1000**.</span><span class="sxs-lookup"><span data-stu-id="28b98-119">`ROUNDDOWN (1700.767, -3)` rounds down to the nearest multiple of 1,000 and returns **1000**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="28b98-120">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="28b98-120">Additional resources</span></span>

[<span data-ttu-id="28b98-121">Funciones matemáticas</span><span class="sxs-lookup"><span data-stu-id="28b98-121">Mathematical functions</span></span>](er-functions-category-mathematical.md)
