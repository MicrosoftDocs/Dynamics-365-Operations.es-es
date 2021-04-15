---
title: Función ROUNDDOWN de ER
description: Este tema proporciona información general sobre cómo usar la función ROUNDDOWN de informes electrónicos (ER).
author: NickSelin
ms.date: 12/17/2019
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
ms.openlocfilehash: 89fc134ec11a47506211ce68ec3aaf966d9a308b
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5744472"
---
# <a name="rounddown-er-function"></a><span data-ttu-id="e8d7a-103">Función ROUNDDOWN de ER</span><span class="sxs-lookup"><span data-stu-id="e8d7a-103">ROUNDDOWN ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e8d7a-104">La función `ROUNDDOWN` devuelve el número especificado como un valor *Real* después de que se haya redondeado hacia abajo al número especificado de posiciones decimales.</span><span class="sxs-lookup"><span data-stu-id="e8d7a-104">The `ROUNDDOWN` function returns the specified number as a *Real* value after it has been rounded down to the specified number of decimal places.</span></span>

## <a name="syntax"></a><span data-ttu-id="e8d7a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e8d7a-105">Syntax</span></span>

```vb
ROUNDDOWN (number, decimals)
```

## <a name="arguments"></a><span data-ttu-id="e8d7a-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="e8d7a-106">Arguments</span></span>

<span data-ttu-id="e8d7a-107">`number`: *Real*</span><span class="sxs-lookup"><span data-stu-id="e8d7a-107">`number`: *Real*</span></span>

<span data-ttu-id="e8d7a-108">Un valor numérico que debe redondearse hacia abajo.</span><span class="sxs-lookup"><span data-stu-id="e8d7a-108">A numeric value that must be rounded down.</span></span>

<span data-ttu-id="e8d7a-109">`decimals`: *Entero*</span><span class="sxs-lookup"><span data-stu-id="e8d7a-109">`decimals`: *Integer*</span></span>

<span data-ttu-id="e8d7a-110">Un valor numérico que representa el número de lugares decimales.</span><span class="sxs-lookup"><span data-stu-id="e8d7a-110">A numeric value that represents the number of decimal places.</span></span>

## <a name="return-values"></a><span data-ttu-id="e8d7a-111">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="e8d7a-111">Return values</span></span>

<span data-ttu-id="e8d7a-112">*Real*</span><span class="sxs-lookup"><span data-stu-id="e8d7a-112">*Real*</span></span>

<span data-ttu-id="e8d7a-113">El valor numérico resultante.</span><span class="sxs-lookup"><span data-stu-id="e8d7a-113">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="e8d7a-114">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="e8d7a-114">Usage notes</span></span>

<span data-ttu-id="e8d7a-115">Esta función se comporta como [ROUND](er-functions-mathematical-round.md), pero siempre redondea hacia abajo del número especificado (hacia cero).</span><span class="sxs-lookup"><span data-stu-id="e8d7a-115">This function behaves like [ROUND](er-functions-mathematical-round.md), but it always rounds the specified number down (toward zero).</span></span>

## <a name="example-1"></a><span data-ttu-id="e8d7a-116">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="e8d7a-116">Example 1</span></span>

<span data-ttu-id="e8d7a-117">`ROUNDDOWN (1200.767, 2)` redondea hacia abajo a dos lugares decimales y devuelve **1200,76**.</span><span class="sxs-lookup"><span data-stu-id="e8d7a-117">`ROUNDDOWN (1200.767, 2)` rounds down to two decimal places and returns **1200.76**.</span></span> 

## <a name="example-2"></a><span data-ttu-id="e8d7a-118">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="e8d7a-118">Example 2</span></span>

<span data-ttu-id="e8d7a-119">`ROUNDDOWN (1700.767, -3)` redondea hacia abajo al múltiplo más cercano de 1000 y devuelve **1000**.</span><span class="sxs-lookup"><span data-stu-id="e8d7a-119">`ROUNDDOWN (1700.767, -3)` rounds down to the nearest multiple of 1,000 and returns **1000**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e8d7a-120">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="e8d7a-120">Additional resources</span></span>

[<span data-ttu-id="e8d7a-121">Funciones matemáticas</span><span class="sxs-lookup"><span data-stu-id="e8d7a-121">Mathematical functions</span></span>](er-functions-category-mathematical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]