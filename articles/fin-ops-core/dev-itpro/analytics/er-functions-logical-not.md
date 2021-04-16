---
title: Función NOT de ER
description: Este tema proporciona información general sobre cómo usar la función NOT de informes electrónicos (ER).
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
ms.openlocfilehash: 7c10ed61b97dcd4d4a66a530bb3d08c539659233
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5751736"
---
# <a name="not-er-function"></a><span data-ttu-id="95c6f-103">Función NOT de ER</span><span class="sxs-lookup"><span data-stu-id="95c6f-103">NOT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="95c6f-104">La función `NOT` devuelve el valor lógico invertido de la condición especificada como un valor *Booleano*.</span><span class="sxs-lookup"><span data-stu-id="95c6f-104">The `NOT` function returns the reversed logical value of the specified condition as a *Boolean* value.</span></span>

## <a name="syntax"></a><span data-ttu-id="95c6f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="95c6f-105">Syntax</span></span>

```vb
NOT (condition)
```

## <a name="arguments"></a><span data-ttu-id="95c6f-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="95c6f-106">Arguments</span></span>

<span data-ttu-id="95c6f-107">`condition`: *Booleano*</span><span class="sxs-lookup"><span data-stu-id="95c6f-107">`condition`: *Boolean*</span></span>

<span data-ttu-id="95c6f-108">Una expresión condicional válida que debe revertirse.</span><span class="sxs-lookup"><span data-stu-id="95c6f-108">A valid conditional expression that must be reversed.</span></span>

## <a name="return-values"></a><span data-ttu-id="95c6f-109">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="95c6f-109">Return values</span></span>

<span data-ttu-id="95c6f-110">*Booleano*</span><span class="sxs-lookup"><span data-stu-id="95c6f-110">*Boolean*</span></span>

<span data-ttu-id="95c6f-111">El valor *Booleano* resultante.</span><span class="sxs-lookup"><span data-stu-id="95c6f-111">The resulting *Boolean* value.</span></span>

## <a name="example"></a><span data-ttu-id="95c6f-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="95c6f-112">Example</span></span>

<span data-ttu-id="95c6f-113">`NOT (TRUE)` devuelve **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="95c6f-113">`NOT (TRUE)` returns **FALSE**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="95c6f-114">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="95c6f-114">Additional resources</span></span>

[<span data-ttu-id="95c6f-115">Funciones lógicas</span><span class="sxs-lookup"><span data-stu-id="95c6f-115">Logical functions</span></span>](er-functions-category-logical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]