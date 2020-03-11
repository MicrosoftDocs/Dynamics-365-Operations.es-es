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
ms.openlocfilehash: 5e06236bf1d158a4cf579b8b89cc0a5f7d815c38
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042668"
---
# <span data-ttu-id="bf5ff-103"><a name="INTVALUE">Función INTVALUE ER</a></span><span class="sxs-lookup"><span data-stu-id="bf5ff-103"><a name="INTVALUE">INTVALUE ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="bf5ff-104">La función `INTVALUE` devuelve un valor *Int* que representa la cadena especificada.</span><span class="sxs-lookup"><span data-stu-id="bf5ff-104">The `INTVALUE` function returns an *Int* value that represents the specified string.</span></span>

## <a name="syntax-1"></a><span data-ttu-id="bf5ff-105">Sintaxis 1</span><span class="sxs-lookup"><span data-stu-id="bf5ff-105">Syntax 1</span></span>

```vb
INTVALUE (text)
```

## <a name="syntax-2"></a><span data-ttu-id="bf5ff-106">Sintaxis 2</span><span class="sxs-lookup"><span data-stu-id="bf5ff-106">Syntax 2</span></span>

```vb
INTVALUE (number)
```

## <a name="arguments"></a><span data-ttu-id="bf5ff-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="bf5ff-107">Arguments</span></span>

<span data-ttu-id="bf5ff-108">`text`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="bf5ff-108">`text`: *String*</span></span>

<span data-ttu-id="bf5ff-109">Un valor de texto que debe convertirse en un número *Int*.</span><span class="sxs-lookup"><span data-stu-id="bf5ff-109">A text value that must be converted to an *Int* number.</span></span>

<span data-ttu-id="bf5ff-110">`number`: *Real* o *Entero*</span><span class="sxs-lookup"><span data-stu-id="bf5ff-110">`number`: *Real* or *Integer*</span></span>

<span data-ttu-id="bf5ff-111">Un valor numérico *Real* o *Entero* que debe convertirse en un número *Int*.</span><span class="sxs-lookup"><span data-stu-id="bf5ff-111">A numeric *Real* or *Integer* value that must be converted to an *Int* number.</span></span>

## <a name="return-values"></a><span data-ttu-id="bf5ff-112">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="bf5ff-112">Return values</span></span>

<span data-ttu-id="bf5ff-113">*Int*</span><span class="sxs-lookup"><span data-stu-id="bf5ff-113">*Int*</span></span>

<span data-ttu-id="bf5ff-114">El valor numérico resultante.</span><span class="sxs-lookup"><span data-stu-id="bf5ff-114">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="bf5ff-115">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="bf5ff-115">Usage notes</span></span>

<span data-ttu-id="bf5ff-116">Se trunca cualquier posición decimal.</span><span class="sxs-lookup"><span data-stu-id="bf5ff-116">Any decimal places are truncated.</span></span>

## <a name="example-1"></a><span data-ttu-id="bf5ff-117">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="bf5ff-117">Example 1</span></span>

<span data-ttu-id="bf5ff-118">`INTVALUE ("100.77")` devuelve el valor *Int* **100**.</span><span class="sxs-lookup"><span data-stu-id="bf5ff-118">`INTVALUE ("100.77")` returns the *Int* value **100**.</span></span>

## <a name="example-2"></a><span data-ttu-id="bf5ff-119">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="bf5ff-119">Example 2</span></span>

<span data-ttu-id="bf5ff-120">`INTVALUE (-100.77)` devuelve el valor *Int* **-100**.</span><span class="sxs-lookup"><span data-stu-id="bf5ff-120">`INTVALUE (-100.77)` returns the *Int* value **-100**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="bf5ff-121">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="bf5ff-121">Additional resources</span></span>

[<span data-ttu-id="bf5ff-122">Funciones de conversión de tipos</span><span class="sxs-lookup"><span data-stu-id="bf5ff-122">Type conversion functions</span></span>](er-functions-category-type-conversion.md)
