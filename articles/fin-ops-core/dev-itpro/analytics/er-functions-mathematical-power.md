---
title: Función POWER de ER
description: Este tema proporciona información general sobre cómo usar la función POWER de informes electrónicos (ER).
author: NickSelin
manager: kfend
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
ms.openlocfilehash: 9c45e7f9b47a3f0ff4445b1dd160def0ada3a56e
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "5570431"
---
# <a name="power-er-function"></a><span data-ttu-id="6ac3d-103">Función POWER de ER</span><span class="sxs-lookup"><span data-stu-id="6ac3d-103">POWER ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6ac3d-104">La función `POWER` devuelve un valor *Real* que representa el resultado de elevar el número positivo especificado a la potencia especificada.</span><span class="sxs-lookup"><span data-stu-id="6ac3d-104">The `POWER` function returns a *Real* value that represents the result of raising the specified positive number to the specified power.</span></span>

## <a name="syntax"></a><span data-ttu-id="6ac3d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6ac3d-105">Syntax</span></span>

```vb
POWER (number, power)
```

## <a name="arguments"></a><span data-ttu-id="6ac3d-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="6ac3d-106">Arguments</span></span>

<span data-ttu-id="6ac3d-107">`number`: *Real* o *Entero*</span><span class="sxs-lookup"><span data-stu-id="6ac3d-107">`number`: *Real* or *Integer*</span></span>

<span data-ttu-id="6ac3d-108">Un valor numérico que debe elevarse a la potencia especificada.</span><span class="sxs-lookup"><span data-stu-id="6ac3d-108">A numeric value that must be raised to the specified power.</span></span>

<span data-ttu-id="6ac3d-109">`power`: *Real* o *Entero*</span><span class="sxs-lookup"><span data-stu-id="6ac3d-109">`power`: *Real* or *Integer*</span></span>

<span data-ttu-id="6ac3d-110">Un valor numérico que representa la potencia específica.</span><span class="sxs-lookup"><span data-stu-id="6ac3d-110">A numeric value that represents the specific power.</span></span>

## <a name="return-values"></a><span data-ttu-id="6ac3d-111">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="6ac3d-111">Return values</span></span>

<span data-ttu-id="6ac3d-112">*Real*</span><span class="sxs-lookup"><span data-stu-id="6ac3d-112">*Real*</span></span>

<span data-ttu-id="6ac3d-113">El valor numérico resultante.</span><span class="sxs-lookup"><span data-stu-id="6ac3d-113">The resulting numeric value.</span></span>

## <a name="example-1"></a><span data-ttu-id="6ac3d-114">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="6ac3d-114">Example 1</span></span>

<span data-ttu-id="6ac3d-115">`POWER (10, 2)` devuelve **100**.</span><span class="sxs-lookup"><span data-stu-id="6ac3d-115">`POWER (10, 2)` returns **100**.</span></span>

## <a name="example-2"></a><span data-ttu-id="6ac3d-116">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="6ac3d-116">Example 2</span></span>

<span data-ttu-id="6ac3d-117">`POWER (4, 0.5)` devuelve **2**.</span><span class="sxs-lookup"><span data-stu-id="6ac3d-117">`POWER (4, 0.5)` returns **2**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6ac3d-118">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="6ac3d-118">Additional resources</span></span>

[<span data-ttu-id="6ac3d-119">Funciones matemáticas</span><span class="sxs-lookup"><span data-stu-id="6ac3d-119">Mathematical functions</span></span>](er-functions-category-mathematical.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]