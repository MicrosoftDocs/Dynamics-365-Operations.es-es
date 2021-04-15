---
title: Función OR de ER
description: Este tema proporciona información general sobre cómo usar la función OR de informes electrónicos (ER).
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
ms.openlocfilehash: 9763cdbabfbaba1af433c1fd753b03982ecb550d
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5751744"
---
# <a name="or-er-function"></a><span data-ttu-id="dddea-103">Función OR de ER</span><span class="sxs-lookup"><span data-stu-id="dddea-103">OR ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="dddea-104">La función `OR` devuelve un valor *Booleano* de **FALSE** si todas las condiciones especificadas son falsas.</span><span class="sxs-lookup"><span data-stu-id="dddea-104">The `OR` function returns a *Boolean* value of **FALSE** if all the specified conditions are false.</span></span> <span data-ttu-id="dddea-105">Si cualquier condición especificada es cierta, esta función devuelve un valor *Booleano* de **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="dddea-105">If any specified condition is true, the function returns a *Boolean* value of **TRUE**.</span></span>

## <a name="syntax"></a><span data-ttu-id="dddea-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dddea-106">Syntax</span></span>

```vb
OR (condition 1[, condition 2, …, condition N])
```

## <a name="arguments"></a><span data-ttu-id="dddea-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="dddea-107">Arguments</span></span>

<span data-ttu-id="dddea-108">`condition 1`: *Booleano*</span><span class="sxs-lookup"><span data-stu-id="dddea-108">`condition 1`: *Boolean*</span></span>

<span data-ttu-id="dddea-109">Una expresión condicional válida que debe probarse.</span><span class="sxs-lookup"><span data-stu-id="dddea-109">A valid conditional expression that must be tested.</span></span> <span data-ttu-id="dddea-110">Este argumento es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="dddea-110">This argument is required.</span></span>

<span data-ttu-id="dddea-111">`condition N`: *Booleano*</span><span class="sxs-lookup"><span data-stu-id="dddea-111">`condition N`: *Boolean*</span></span>

<span data-ttu-id="dddea-112">Una expresión condicional válida que debe probarse.</span><span class="sxs-lookup"><span data-stu-id="dddea-112">A valid conditional expression that must be tested.</span></span> <span data-ttu-id="dddea-113">Estos argumentos adicionales son opcionales.</span><span class="sxs-lookup"><span data-stu-id="dddea-113">These additional arguments are optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="dddea-114">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="dddea-114">Return values</span></span>

<span data-ttu-id="dddea-115">*Booleano*</span><span class="sxs-lookup"><span data-stu-id="dddea-115">*Boolean*</span></span>

<span data-ttu-id="dddea-116">El valor *Booleano* resultante.</span><span class="sxs-lookup"><span data-stu-id="dddea-116">The resulting *Boolean* value.</span></span>

## <a name="example"></a><span data-ttu-id="dddea-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="dddea-117">Example</span></span>

<span data-ttu-id="dddea-118">`OR (1=2, "a"="a")` devuelve **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="dddea-118">`OR (1=2, "a"="a")` returns **TRUE**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="dddea-119">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="dddea-119">Additional resources</span></span>

[<span data-ttu-id="dddea-120">Funciones lógicas</span><span class="sxs-lookup"><span data-stu-id="dddea-120">Logical functions</span></span>](er-functions-category-logical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]