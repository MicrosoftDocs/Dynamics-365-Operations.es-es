---
title: Función INTVALUE ER
description: Este tema proporciona información general sobre cómo usar la función INTVALUE de informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: c5c3e4c8bd918fa1154d2c111970d2f6d0e90e08
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2020
ms.locfileid: "3743648"
---
# <a name="intvalue-er-function"></a><span data-ttu-id="7c1b2-103">Función INTVALUE ER</span><span class="sxs-lookup"><span data-stu-id="7c1b2-103">INTVALUE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7c1b2-104">La función `INTVALUE` devuelve un valor *Int* que representa la cadena especificada.</span><span class="sxs-lookup"><span data-stu-id="7c1b2-104">The `INTVALUE` function returns an *Int* value that represents the specified string.</span></span>

## <a name="syntax-1"></a><span data-ttu-id="7c1b2-105">Sintaxis 1</span><span class="sxs-lookup"><span data-stu-id="7c1b2-105">Syntax 1</span></span>

```vb
INTVALUE (text)
```

## <a name="syntax-2"></a><span data-ttu-id="7c1b2-106">Sintaxis 2</span><span class="sxs-lookup"><span data-stu-id="7c1b2-106">Syntax 2</span></span>

```vb
INTVALUE (number)
```

## <a name="arguments"></a><span data-ttu-id="7c1b2-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="7c1b2-107">Arguments</span></span>

<span data-ttu-id="7c1b2-108">`text`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="7c1b2-108">`text`: *String*</span></span>

<span data-ttu-id="7c1b2-109">Un valor de texto que debe convertirse en un número *Int*.</span><span class="sxs-lookup"><span data-stu-id="7c1b2-109">A text value that must be converted to an *Int* number.</span></span>

<span data-ttu-id="7c1b2-110">`number`: *Real* o *Entero*</span><span class="sxs-lookup"><span data-stu-id="7c1b2-110">`number`: *Real* or *Integer*</span></span>

<span data-ttu-id="7c1b2-111">Un valor numérico *Real* o *Entero* que debe convertirse en un número *Int*.</span><span class="sxs-lookup"><span data-stu-id="7c1b2-111">A numeric *Real* or *Integer* value that must be converted to an *Int* number.</span></span>

## <a name="return-values"></a><span data-ttu-id="7c1b2-112">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="7c1b2-112">Return values</span></span>

<span data-ttu-id="7c1b2-113">*Int*</span><span class="sxs-lookup"><span data-stu-id="7c1b2-113">*Int*</span></span>

<span data-ttu-id="7c1b2-114">El valor numérico resultante.</span><span class="sxs-lookup"><span data-stu-id="7c1b2-114">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="7c1b2-115">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="7c1b2-115">Usage notes</span></span>

<span data-ttu-id="7c1b2-116">Se trunca cualquier posición decimal.</span><span class="sxs-lookup"><span data-stu-id="7c1b2-116">Any decimal places are truncated.</span></span>

## <a name="example-1"></a><span data-ttu-id="7c1b2-117">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="7c1b2-117">Example 1</span></span>

<span data-ttu-id="7c1b2-118">`INTVALUE ("100.77")` devuelve el valor *Int* **100**.</span><span class="sxs-lookup"><span data-stu-id="7c1b2-118">`INTVALUE ("100.77")` returns the *Int* value **100**.</span></span>

## <a name="example-2"></a><span data-ttu-id="7c1b2-119">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="7c1b2-119">Example 2</span></span>

<span data-ttu-id="7c1b2-120">`INTVALUE (-100.77)` devuelve el valor *Int* **-100**.</span><span class="sxs-lookup"><span data-stu-id="7c1b2-120">`INTVALUE (-100.77)` returns the *Int* value **-100**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="7c1b2-121">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="7c1b2-121">Additional resources</span></span>

[<span data-ttu-id="7c1b2-122">Funciones de conversión de tipos</span><span class="sxs-lookup"><span data-stu-id="7c1b2-122">Type conversion functions</span></span>](er-functions-category-type-conversion.md)
