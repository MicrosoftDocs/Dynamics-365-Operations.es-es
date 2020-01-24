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
ms.openlocfilehash: 81a596f5206b23001feea553adcdf6c904572775
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917129"
---
# <span data-ttu-id="1eac9-103"><a name="OR">Función OR de ER</a></span><span class="sxs-lookup"><span data-stu-id="1eac9-103"><a name="OR">OR ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1eac9-104">La función `OR` devuelve un valor *Booleano* de **FALSE** si todas las condiciones especificadas son falsas.</span><span class="sxs-lookup"><span data-stu-id="1eac9-104">The `OR` function returns a *Boolean* value of **FALSE** if all the specified conditions are false.</span></span> <span data-ttu-id="1eac9-105">Si cualquier condición especificada es cierta, esta función devuelve un valor *Booleano* de **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="1eac9-105">If any specified condition is true, the function returns a *Boolean* value of **TRUE**.</span></span>

## <a name="syntax"></a><span data-ttu-id="1eac9-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1eac9-106">Syntax</span></span>

```
OR (condition 1[, condition 2, …, condition N])
```

## <a name="arguments"></a><span data-ttu-id="1eac9-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="1eac9-107">Arguments</span></span>

<span data-ttu-id="1eac9-108">`condition 1`: *Booleano*</span><span class="sxs-lookup"><span data-stu-id="1eac9-108">`condition 1`: *Boolean*</span></span>

<span data-ttu-id="1eac9-109">Una expresión condicional válida que debe probarse.</span><span class="sxs-lookup"><span data-stu-id="1eac9-109">A valid conditional expression that must be tested.</span></span> <span data-ttu-id="1eac9-110">Este argumento es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="1eac9-110">This argument is required.</span></span>

<span data-ttu-id="1eac9-111">`condition N`: *Booleano*</span><span class="sxs-lookup"><span data-stu-id="1eac9-111">`condition N`: *Boolean*</span></span>

<span data-ttu-id="1eac9-112">Una expresión condicional válida que debe probarse.</span><span class="sxs-lookup"><span data-stu-id="1eac9-112">A valid conditional expression that must be tested.</span></span> <span data-ttu-id="1eac9-113">Estos argumentos adicionales son opcionales.</span><span class="sxs-lookup"><span data-stu-id="1eac9-113">These additional arguments are optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="1eac9-114">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="1eac9-114">Return values</span></span>

<span data-ttu-id="1eac9-115">*Booleano*</span><span class="sxs-lookup"><span data-stu-id="1eac9-115">*Boolean*</span></span>

<span data-ttu-id="1eac9-116">El valor *Booleano* resultante.</span><span class="sxs-lookup"><span data-stu-id="1eac9-116">The resulting *Boolean* value.</span></span>

## <a name="example"></a><span data-ttu-id="1eac9-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1eac9-117">Example</span></span>

<span data-ttu-id="1eac9-118">`OR (1=2, "a"="a")` devuelve **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="1eac9-118">`OR (1=2, "a"="a")` returns **TRUE**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="1eac9-119">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="1eac9-119">Additional resources</span></span>

[<span data-ttu-id="1eac9-120">Funciones lógicas</span><span class="sxs-lookup"><span data-stu-id="1eac9-120">Logical functions</span></span>](er-functions-category-logical.md)
