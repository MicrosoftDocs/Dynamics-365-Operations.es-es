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
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b15277dba26dc7864193b11a127944daca6b989f
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916048"
---
# <span data-ttu-id="84dd6-103"><a name="NOT">Función NOT de ER</a></span><span class="sxs-lookup"><span data-stu-id="84dd6-103"><a name="NOT">NOT ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="84dd6-104">La función `NOT` devuelve el valor lógico invertido de la condición especificada como un valor *Booleano*.</span><span class="sxs-lookup"><span data-stu-id="84dd6-104">The `NOT` function returns the reversed logical value of the specified condition as a *Boolean* value.</span></span>

## <a name="syntax"></a><span data-ttu-id="84dd6-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="84dd6-105">Syntax</span></span>

```
NOT (condition)
```

## <a name="arguments"></a><span data-ttu-id="84dd6-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="84dd6-106">Arguments</span></span>

<span data-ttu-id="84dd6-107">`condition`: *Booleano*</span><span class="sxs-lookup"><span data-stu-id="84dd6-107">`condition`: *Boolean*</span></span>

<span data-ttu-id="84dd6-108">Una expresión condicional válida que debe revertirse.</span><span class="sxs-lookup"><span data-stu-id="84dd6-108">A valid conditional expression that must be reversed.</span></span>

## <a name="return-values"></a><span data-ttu-id="84dd6-109">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="84dd6-109">Return values</span></span>

<span data-ttu-id="84dd6-110">*Booleano*</span><span class="sxs-lookup"><span data-stu-id="84dd6-110">*Boolean*</span></span>

<span data-ttu-id="84dd6-111">El valor *Booleano* resultante.</span><span class="sxs-lookup"><span data-stu-id="84dd6-111">The resulting *Boolean* value.</span></span>

## <a name="example"></a><span data-ttu-id="84dd6-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="84dd6-112">Example</span></span>

<span data-ttu-id="84dd6-113">`NOT (TRUE)` devuelve **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="84dd6-113">`NOT (TRUE)` returns **FALSE**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="84dd6-114">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="84dd6-114">Additional resources</span></span>

[<span data-ttu-id="84dd6-115">Funciones lógicas</span><span class="sxs-lookup"><span data-stu-id="84dd6-115">Logical functions</span></span>](er-functions-category-logical.md)
