---
title: Función ROUNDUP de ER
description: Este tema proporciona información general sobre cómo usar la función ROUNDUP de informes electrónicos (ER).
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
ms.openlocfilehash: 1784ab3587a090c8e5535509a1ba52fc85111daa
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041593"
---
# <span data-ttu-id="42545-103"><a name="ROUNDUP">Función ROUNDUP de ER</a></span><span class="sxs-lookup"><span data-stu-id="42545-103"><a name="ROUNDUP">ROUNDUP ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="42545-104">La función `ROUNDUP` devuelve el número especificado como un valor *Real* después de que se haya redondeado hacia arriba al número especificado de posiciones decimales.</span><span class="sxs-lookup"><span data-stu-id="42545-104">The `ROUNDUP` function returns the specified number as a *Real* value after it has been rounded up to the specified number of decimal places.</span></span>

## <a name="syntax"></a><span data-ttu-id="42545-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="42545-105">Syntax</span></span>

```vb
ROUNDDOWN (number, decimals)
```

## <a name="arguments"></a><span data-ttu-id="42545-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="42545-106">Arguments</span></span>

<span data-ttu-id="42545-107">`number`: *Real*</span><span class="sxs-lookup"><span data-stu-id="42545-107">`number`: *Real*</span></span>

<span data-ttu-id="42545-108">Un valor numérico que debe redondearse hacia arriba.</span><span class="sxs-lookup"><span data-stu-id="42545-108">A numeric value that must be rounded up.</span></span>

<span data-ttu-id="42545-109">`decimals`: *Entero*</span><span class="sxs-lookup"><span data-stu-id="42545-109">`decimals`: *Integer*</span></span>

<span data-ttu-id="42545-110">Un valor numérico que representa el número de lugares decimales.</span><span class="sxs-lookup"><span data-stu-id="42545-110">A numeric value that represents the number of decimal places.</span></span>

## <a name="return-values"></a><span data-ttu-id="42545-111">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="42545-111">Return values</span></span>

<span data-ttu-id="42545-112">*Real*</span><span class="sxs-lookup"><span data-stu-id="42545-112">*Real*</span></span>

<span data-ttu-id="42545-113">El valor numérico resultante.</span><span class="sxs-lookup"><span data-stu-id="42545-113">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="42545-114">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="42545-114">Usage notes</span></span>

<span data-ttu-id="42545-115">Esta función se comporta como [ROUND](er-functions-mathematical-round.md), pero siempre redondea hacia arriba el número especificado (lejos de cero).</span><span class="sxs-lookup"><span data-stu-id="42545-115">This function behaves like [ROUND](er-functions-mathematical-round.md), but it always rounds the specified number up (away from zero).</span></span>

## <a name="example-1"></a><span data-ttu-id="42545-116">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="42545-116">Example 1</span></span>

<span data-ttu-id="42545-117">`ROUNDUP (1200.763, 2)` redondea hacia arriba a dos lugares decimales y devuelve **1200,77**.</span><span class="sxs-lookup"><span data-stu-id="42545-117">`ROUNDUP (1200.763, 2)` rounds up to two decimal places and returns **1200.77**.</span></span>

## <a name="example-2"></a><span data-ttu-id="42545-118">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="42545-118">Example 2</span></span>

<span data-ttu-id="42545-119">`ROUNDUP (1200.767, -3)` redondea hacia arriba al múltiplo más cercano de 1000 y devuelve **2000**.</span><span class="sxs-lookup"><span data-stu-id="42545-119">`ROUNDUP (1200.767, -3)` rounds up to the nearest multiple of 1,000 and returns **2000**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="42545-120">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="42545-120">Additional resources</span></span>

[<span data-ttu-id="42545-121">Funciones matemáticas</span><span class="sxs-lookup"><span data-stu-id="42545-121">Mathematical functions</span></span>](er-functions-category-mathematical.md)
