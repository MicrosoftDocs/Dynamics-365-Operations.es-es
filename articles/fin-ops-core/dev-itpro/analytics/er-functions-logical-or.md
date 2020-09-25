---
title: Función OR de ER
description: Este tema proporciona información general sobre cómo usar la función OR de informes electrónicos (ER).
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
ms.openlocfilehash: faf07c5d8b30cd3babe8a6a55ae7effe5ce457a0
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2020
ms.locfileid: "3744632"
---
# <a name="or-er-function"></a><span data-ttu-id="e0244-103">Función OR de ER</span><span class="sxs-lookup"><span data-stu-id="e0244-103">OR ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e0244-104">La función `OR` devuelve un valor *Booleano* de **FALSE** si todas las condiciones especificadas son falsas.</span><span class="sxs-lookup"><span data-stu-id="e0244-104">The `OR` function returns a *Boolean* value of **FALSE** if all the specified conditions are false.</span></span> <span data-ttu-id="e0244-105">Si cualquier condición especificada es cierta, esta función devuelve un valor *Booleano* de **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="e0244-105">If any specified condition is true, the function returns a *Boolean* value of **TRUE**.</span></span>

## <a name="syntax"></a><span data-ttu-id="e0244-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e0244-106">Syntax</span></span>

```vb
OR (condition 1[, condition 2, …, condition N])
```

## <a name="arguments"></a><span data-ttu-id="e0244-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="e0244-107">Arguments</span></span>

<span data-ttu-id="e0244-108">`condition 1`: *Booleano*</span><span class="sxs-lookup"><span data-stu-id="e0244-108">`condition 1`: *Boolean*</span></span>

<span data-ttu-id="e0244-109">Una expresión condicional válida que debe probarse.</span><span class="sxs-lookup"><span data-stu-id="e0244-109">A valid conditional expression that must be tested.</span></span> <span data-ttu-id="e0244-110">Este argumento es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="e0244-110">This argument is required.</span></span>

<span data-ttu-id="e0244-111">`condition N`: *Booleano*</span><span class="sxs-lookup"><span data-stu-id="e0244-111">`condition N`: *Boolean*</span></span>

<span data-ttu-id="e0244-112">Una expresión condicional válida que debe probarse.</span><span class="sxs-lookup"><span data-stu-id="e0244-112">A valid conditional expression that must be tested.</span></span> <span data-ttu-id="e0244-113">Estos argumentos adicionales son opcionales.</span><span class="sxs-lookup"><span data-stu-id="e0244-113">These additional arguments are optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="e0244-114">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="e0244-114">Return values</span></span>

<span data-ttu-id="e0244-115">*Booleano*</span><span class="sxs-lookup"><span data-stu-id="e0244-115">*Boolean*</span></span>

<span data-ttu-id="e0244-116">El valor *Booleano* resultante.</span><span class="sxs-lookup"><span data-stu-id="e0244-116">The resulting *Boolean* value.</span></span>

## <a name="example"></a><span data-ttu-id="e0244-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e0244-117">Example</span></span>

<span data-ttu-id="e0244-118">`OR (1=2, "a"="a")` devuelve **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="e0244-118">`OR (1=2, "a"="a")` returns **TRUE**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e0244-119">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="e0244-119">Additional resources</span></span>

[<span data-ttu-id="e0244-120">Funciones lógicas</span><span class="sxs-lookup"><span data-stu-id="e0244-120">Logical functions</span></span>](er-functions-category-logical.md)
