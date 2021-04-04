---
title: Función AND de ER
description: Este tema proporciona información general sobre cómo usar la función AND de informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 12/12/2019
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
ms.openlocfilehash: 068b9a3b2cf2e5bffe895bc4e8a7cbb2d8025ad7
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "5560094"
---
# <a name="and-er-function"></a><span data-ttu-id="923b4-103">Función AND de ER</span><span class="sxs-lookup"><span data-stu-id="923b4-103">AND ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="923b4-104">La función `AND` devuelve un valor *Booleano* de **TRUE** si todas las condiciones especificadas son ciertas.</span><span class="sxs-lookup"><span data-stu-id="923b4-104">The `AND` function returns a *Boolean* value of **TRUE** if all the specified conditions are true.</span></span> <span data-ttu-id="923b4-105">De lo contrario, la expresión devuelve un valor *Booleano* de **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="923b4-105">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span>

## <a name="syntax"></a><span data-ttu-id="923b4-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="923b4-106">Syntax</span></span>

```vb
AND (condition 1[, condition 2, …, condition N])
```

## <a name="arguments"></a><span data-ttu-id="923b4-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="923b4-107">Arguments</span></span>

<span data-ttu-id="923b4-108">`condition 1`: *Booleano*</span><span class="sxs-lookup"><span data-stu-id="923b4-108">`condition 1`: *Boolean*</span></span>

<span data-ttu-id="923b4-109">Una expresión condicional válida que debe probarse.</span><span class="sxs-lookup"><span data-stu-id="923b4-109">A valid conditional expression that must be tested.</span></span> <span data-ttu-id="923b4-110">Este argumento es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="923b4-110">This argument is required.</span></span>

<span data-ttu-id="923b4-111">`condition N`: *Booleano*</span><span class="sxs-lookup"><span data-stu-id="923b4-111">`condition N`: *Boolean*</span></span>

<span data-ttu-id="923b4-112">Una expresión condicional válida que debe probarse.</span><span class="sxs-lookup"><span data-stu-id="923b4-112">A valid conditional expression that must be tested.</span></span> <span data-ttu-id="923b4-113">Estos argumentos adicionales son opcionales.</span><span class="sxs-lookup"><span data-stu-id="923b4-113">These additional arguments are optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="923b4-114">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="923b4-114">Return values</span></span>

<span data-ttu-id="923b4-115">*Booleano*</span><span class="sxs-lookup"><span data-stu-id="923b4-115">*Boolean*</span></span>

<span data-ttu-id="923b4-116">El valor *Booleano* resultante.</span><span class="sxs-lookup"><span data-stu-id="923b4-116">The resulting *Boolean* value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="923b4-117">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="923b4-117">Usage notes</span></span>

<span data-ttu-id="923b4-118">En los argumentos de las funciones lógicas, puede utilizar referencias de orígenes de datos, valores numéricos y de texto, valores booleanos, operadores de comparación y otras funciones de informes electrónicos (ER).</span><span class="sxs-lookup"><span data-stu-id="923b4-118">In the arguments of logical functions, you can use data source references, numeric and text values, Boolean values, comparison operators, and other Electronic reporting (ER) functions.</span></span> <span data-ttu-id="923b4-119">Sin embargo, todos los argumentos deben evaluarse según un valor *Booleano* de **TRUE** o **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="923b4-119">However, all the arguments must be evaluated to a *Boolean* value of **TRUE** or **FALSE**.</span></span>

## <a name="example"></a><span data-ttu-id="923b4-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="923b4-120">Example</span></span>

<span data-ttu-id="923b4-121">`AND (1=1, "a"="a")` devuelve **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="923b4-121">`AND (1=1, "a"="a")` returns **TRUE**.</span></span>

<span data-ttu-id="923b4-122">`AND (1=2, "a"="a")` devuelve **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="923b4-122">`AND (1=2, "a"="a")` returns **FALSE**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="923b4-123">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="923b4-123">Additional resources</span></span>

[<span data-ttu-id="923b4-124">Funciones lógicas</span><span class="sxs-lookup"><span data-stu-id="923b4-124">Logical functions</span></span>](er-functions-category-logical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]