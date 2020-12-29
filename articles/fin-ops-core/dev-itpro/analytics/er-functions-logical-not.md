---
title: Función NOT de ER
description: Este tema proporciona información general sobre cómo usar la función NOT de informes electrónicos (ER).
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
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2308ab4d222863312441b3f17559ac4d3afbfb29
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686963"
---
# <a name="not-er-function"></a><span data-ttu-id="15b21-103">Función NOT de ER</span><span class="sxs-lookup"><span data-stu-id="15b21-103">NOT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="15b21-104">La función `NOT` devuelve el valor lógico invertido de la condición especificada como un valor *Booleano*.</span><span class="sxs-lookup"><span data-stu-id="15b21-104">The `NOT` function returns the reversed logical value of the specified condition as a *Boolean* value.</span></span>

## <a name="syntax"></a><span data-ttu-id="15b21-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="15b21-105">Syntax</span></span>

```vb
NOT (condition)
```

## <a name="arguments"></a><span data-ttu-id="15b21-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="15b21-106">Arguments</span></span>

<span data-ttu-id="15b21-107">`condition`: *Booleano*</span><span class="sxs-lookup"><span data-stu-id="15b21-107">`condition`: *Boolean*</span></span>

<span data-ttu-id="15b21-108">Una expresión condicional válida que debe revertirse.</span><span class="sxs-lookup"><span data-stu-id="15b21-108">A valid conditional expression that must be reversed.</span></span>

## <a name="return-values"></a><span data-ttu-id="15b21-109">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="15b21-109">Return values</span></span>

<span data-ttu-id="15b21-110">*Booleano*</span><span class="sxs-lookup"><span data-stu-id="15b21-110">*Boolean*</span></span>

<span data-ttu-id="15b21-111">El valor *Booleano* resultante.</span><span class="sxs-lookup"><span data-stu-id="15b21-111">The resulting *Boolean* value.</span></span>

## <a name="example"></a><span data-ttu-id="15b21-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="15b21-112">Example</span></span>

<span data-ttu-id="15b21-113">`NOT (TRUE)` devuelve **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="15b21-113">`NOT (TRUE)` returns **FALSE**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="15b21-114">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="15b21-114">Additional resources</span></span>

[<span data-ttu-id="15b21-115">Funciones lógicas</span><span class="sxs-lookup"><span data-stu-id="15b21-115">Logical functions</span></span>](er-functions-category-logical.md)
