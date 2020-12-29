---
title: Función ABS de ER
description: Este tema proporciona información general sobre cómo usar la función ABS de informes electrónicos (ER).
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
ms.openlocfilehash: 3c7156b9990397822a6bea9ed8b3df8f65490572
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "4683290"
---
# <a name="abs-er-function"></a><span data-ttu-id="4284c-103">Función ABS de ER</span><span class="sxs-lookup"><span data-stu-id="4284c-103">ABS ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4284c-104">La función `ABS` devuelve el valor absoluto (módulo) de la cifra especificada como un número *Real*.</span><span class="sxs-lookup"><span data-stu-id="4284c-104">The `ABS` function returns the absolute value (modulus) of the specified number as a *Real* value.</span></span> <span data-ttu-id="4284c-105">Es decir, devuelve el número sin su signo.</span><span class="sxs-lookup"><span data-stu-id="4284c-105">In other words, it returns the number without its sign.</span></span>

## <a name="syntax"></a><span data-ttu-id="4284c-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4284c-106">Syntax</span></span>

```vb
ABS (number)
```

## <a name="arguments"></a><span data-ttu-id="4284c-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="4284c-107">Arguments</span></span>

<span data-ttu-id="4284c-108">`number`: *Real*</span><span class="sxs-lookup"><span data-stu-id="4284c-108">`number`: *Real*</span></span>

<span data-ttu-id="4284c-109">Un valor numérico del que desea el módulo.</span><span class="sxs-lookup"><span data-stu-id="4284c-109">A numeric value that you want the modulus of.</span></span>

## <a name="return-values"></a><span data-ttu-id="4284c-110">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="4284c-110">Return values</span></span>

<span data-ttu-id="4284c-111">*Real*</span><span class="sxs-lookup"><span data-stu-id="4284c-111">*Real*</span></span>

<span data-ttu-id="4284c-112">El valor numérico resultante.</span><span class="sxs-lookup"><span data-stu-id="4284c-112">The resulting numeric value.</span></span>

## <a name="example"></a><span data-ttu-id="4284c-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4284c-113">Example</span></span>

<span data-ttu-id="4284c-114">`ABS (-1)` devuelve **1**.</span><span class="sxs-lookup"><span data-stu-id="4284c-114">`ABS (-1)` returns **1**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="4284c-115">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="4284c-115">Additional resources</span></span>

[<span data-ttu-id="4284c-116">Funciones matemáticas</span><span class="sxs-lookup"><span data-stu-id="4284c-116">Mathematical functions</span></span>](er-functions-category-mathematical.md)
