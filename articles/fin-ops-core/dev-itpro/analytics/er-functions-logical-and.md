---
title: Función AND de ER
description: Este tema proporciona información general sobre cómo usar la función AND de informes electrónicos (ER).
author: NickSelin
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
ms.openlocfilehash: 9851321137b4c7744634df30f85aa3a0b1a0a588
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5745482"
---
# <a name="and-er-function"></a><span data-ttu-id="0088e-103">Función AND de ER</span><span class="sxs-lookup"><span data-stu-id="0088e-103">AND ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0088e-104">La función `AND` devuelve un valor *Booleano* de **TRUE** si todas las condiciones especificadas son ciertas.</span><span class="sxs-lookup"><span data-stu-id="0088e-104">The `AND` function returns a *Boolean* value of **TRUE** if all the specified conditions are true.</span></span> <span data-ttu-id="0088e-105">De lo contrario, la expresión devuelve un valor *Booleano* de **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="0088e-105">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span>

## <a name="syntax"></a><span data-ttu-id="0088e-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0088e-106">Syntax</span></span>

```vb
AND (condition 1[, condition 2, …, condition N])
```

## <a name="arguments"></a><span data-ttu-id="0088e-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="0088e-107">Arguments</span></span>

<span data-ttu-id="0088e-108">`condition 1`: *Booleano*</span><span class="sxs-lookup"><span data-stu-id="0088e-108">`condition 1`: *Boolean*</span></span>

<span data-ttu-id="0088e-109">Una expresión condicional válida que debe probarse.</span><span class="sxs-lookup"><span data-stu-id="0088e-109">A valid conditional expression that must be tested.</span></span> <span data-ttu-id="0088e-110">Este argumento es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="0088e-110">This argument is required.</span></span>

<span data-ttu-id="0088e-111">`condition N`: *Booleano*</span><span class="sxs-lookup"><span data-stu-id="0088e-111">`condition N`: *Boolean*</span></span>

<span data-ttu-id="0088e-112">Una expresión condicional válida que debe probarse.</span><span class="sxs-lookup"><span data-stu-id="0088e-112">A valid conditional expression that must be tested.</span></span> <span data-ttu-id="0088e-113">Estos argumentos adicionales son opcionales.</span><span class="sxs-lookup"><span data-stu-id="0088e-113">These additional arguments are optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="0088e-114">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="0088e-114">Return values</span></span>

<span data-ttu-id="0088e-115">*Booleano*</span><span class="sxs-lookup"><span data-stu-id="0088e-115">*Boolean*</span></span>

<span data-ttu-id="0088e-116">El valor *Booleano* resultante.</span><span class="sxs-lookup"><span data-stu-id="0088e-116">The resulting *Boolean* value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="0088e-117">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="0088e-117">Usage notes</span></span>

<span data-ttu-id="0088e-118">En los argumentos de las funciones lógicas, puede utilizar referencias de orígenes de datos, valores numéricos y de texto, valores booleanos, operadores de comparación y otras funciones de informes electrónicos (ER).</span><span class="sxs-lookup"><span data-stu-id="0088e-118">In the arguments of logical functions, you can use data source references, numeric and text values, Boolean values, comparison operators, and other Electronic reporting (ER) functions.</span></span> <span data-ttu-id="0088e-119">Sin embargo, todos los argumentos deben evaluarse según un valor *Booleano* de **TRUE** o **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="0088e-119">However, all the arguments must be evaluated to a *Boolean* value of **TRUE** or **FALSE**.</span></span>

## <a name="example"></a><span data-ttu-id="0088e-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0088e-120">Example</span></span>

<span data-ttu-id="0088e-121">`AND (1=1, "a"="a")` devuelve **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="0088e-121">`AND (1=1, "a"="a")` returns **TRUE**.</span></span>

<span data-ttu-id="0088e-122">`AND (1=2, "a"="a")` devuelve **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="0088e-122">`AND (1=2, "a"="a")` returns **FALSE**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0088e-123">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="0088e-123">Additional resources</span></span>

[<span data-ttu-id="0088e-124">Funciones lógicas</span><span class="sxs-lookup"><span data-stu-id="0088e-124">Logical functions</span></span>](er-functions-category-logical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]