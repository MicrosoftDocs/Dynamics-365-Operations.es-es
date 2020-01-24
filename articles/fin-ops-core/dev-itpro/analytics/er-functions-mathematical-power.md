---
title: Función POWER de ER
description: Este tema proporciona información general sobre cómo usar la función POWER de informes electrónicos (ER).
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
ms.openlocfilehash: cb768b400e3ddb99e7c8b05905d7a2dd9e4392de
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/20/2019
ms.locfileid: "2915910"
---
# <span data-ttu-id="8f398-103"><a name="POWER">Función POWER de ER</a></span><span class="sxs-lookup"><span data-stu-id="8f398-103"><a name="POWER">POWER ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8f398-104">La función `POWER` devuelve un valor *Real* que representa el resultado de elevar el número positivo especificado a la potencia especificada.</span><span class="sxs-lookup"><span data-stu-id="8f398-104">The `POWER` function returns a *Real* value that represents the result of raising the specified positive number to the specified power.</span></span>

## <a name="syntax"></a><span data-ttu-id="8f398-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8f398-105">Syntax</span></span>

```
POWER (number, power)
```

## <a name="arguments"></a><span data-ttu-id="8f398-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="8f398-106">Arguments</span></span>

<span data-ttu-id="8f398-107">`number`: *Real* o *Entero*</span><span class="sxs-lookup"><span data-stu-id="8f398-107">`number`: *Real* or *Integer*</span></span>

<span data-ttu-id="8f398-108">Un valor numérico que debe elevarse a la potencia especificada.</span><span class="sxs-lookup"><span data-stu-id="8f398-108">A numeric value that must be raised to the specified power.</span></span>

<span data-ttu-id="8f398-109">`power`: *Real* o *Entero*</span><span class="sxs-lookup"><span data-stu-id="8f398-109">`power`: *Real* or *Integer*</span></span>

<span data-ttu-id="8f398-110">Un valor numérico que representa la potencia específica.</span><span class="sxs-lookup"><span data-stu-id="8f398-110">A numeric value that represents the specific power.</span></span>

## <a name="return-values"></a><span data-ttu-id="8f398-111">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="8f398-111">Return values</span></span>

<span data-ttu-id="8f398-112">*Real*</span><span class="sxs-lookup"><span data-stu-id="8f398-112">*Real*</span></span>

<span data-ttu-id="8f398-113">El valor numérico resultante.</span><span class="sxs-lookup"><span data-stu-id="8f398-113">The resulting numeric value.</span></span>

## <a name="example-1"></a><span data-ttu-id="8f398-114">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="8f398-114">Example 1</span></span>

<span data-ttu-id="8f398-115">`POWER (10, 2)` devuelve **100**.</span><span class="sxs-lookup"><span data-stu-id="8f398-115">`POWER (10, 2)` returns **100**.</span></span>

## <a name="example-2"></a><span data-ttu-id="8f398-116">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="8f398-116">Example 2</span></span>

<span data-ttu-id="8f398-117">`POWER (4, 0.5)` devuelve **2**.</span><span class="sxs-lookup"><span data-stu-id="8f398-117">`POWER (4, 0.5)` returns **2**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8f398-118">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="8f398-118">Additional resources</span></span>

[<span data-ttu-id="8f398-119">Funciones matemáticas</span><span class="sxs-lookup"><span data-stu-id="8f398-119">Mathematical functions</span></span>](er-functions-category-mathematical.md)
