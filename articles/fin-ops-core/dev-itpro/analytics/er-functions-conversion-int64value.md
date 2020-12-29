---
title: Función INT64VALUE ER
description: Este tema proporciona información general sobre cómo usar la función INT64VALUE de informes electrónicos (ER).
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
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bb750116312df82448f5a0048e380f9e5274f8e9
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686060"
---
# <a name="int64value-er-function"></a><span data-ttu-id="f2bb7-103">Función INT64VALUE ER</span><span class="sxs-lookup"><span data-stu-id="f2bb7-103">INT64VALUE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f2bb7-104">La función `INT64VALUE` devuelve un valor *Int64* que representa la cadena especificada.</span><span class="sxs-lookup"><span data-stu-id="f2bb7-104">The `INT64VALUE` function returns an *Int64* value that represents the specified string.</span></span>

## <a name="syntax-1"></a><span data-ttu-id="f2bb7-105">Sintaxis 1</span><span class="sxs-lookup"><span data-stu-id="f2bb7-105">Syntax 1</span></span>

```vb
INT64VALUE (text)
```

## <a name="syntax-2"></a><span data-ttu-id="f2bb7-106">Sintaxis 2</span><span class="sxs-lookup"><span data-stu-id="f2bb7-106">Syntax 2</span></span>

```vb
INT64VALUE (number)
```

## <a name="arguments"></a><span data-ttu-id="f2bb7-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="f2bb7-107">Arguments</span></span>

<span data-ttu-id="f2bb7-108">`text`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="f2bb7-108">`text`: *String*</span></span>

<span data-ttu-id="f2bb7-109">Un valor de texto que debe convertirse en un número *Int64*.</span><span class="sxs-lookup"><span data-stu-id="f2bb7-109">A text value that must be converted to an *Int64* number.</span></span>

<span data-ttu-id="f2bb7-110">`number`: *Real* o *Entero*</span><span class="sxs-lookup"><span data-stu-id="f2bb7-110">`number`: *Real* or *Integer*</span></span>

<span data-ttu-id="f2bb7-111">Un valor numérico *Real* o *Entero* que debe convertirse en un número *Int64*.</span><span class="sxs-lookup"><span data-stu-id="f2bb7-111">A numeric *Real* or *Integer* value that must be converted to an *Int64* number.</span></span>

## <a name="return-values"></a><span data-ttu-id="f2bb7-112">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="f2bb7-112">Return values</span></span>

<span data-ttu-id="f2bb7-113">*Int64*</span><span class="sxs-lookup"><span data-stu-id="f2bb7-113">*Int64*</span></span>

<span data-ttu-id="f2bb7-114">El valor numérico resultante.</span><span class="sxs-lookup"><span data-stu-id="f2bb7-114">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="f2bb7-115">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="f2bb7-115">Usage notes</span></span>

<span data-ttu-id="f2bb7-116">Se trunca cualquier posición decimal.</span><span class="sxs-lookup"><span data-stu-id="f2bb7-116">Any decimal places are truncated.</span></span>

## <a name="example-1"></a><span data-ttu-id="f2bb7-117">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="f2bb7-117">Example 1</span></span>

<span data-ttu-id="f2bb7-118">`INT64VALUE ("22565422744")` devuelve el valor *Int64* **22565422744**.</span><span class="sxs-lookup"><span data-stu-id="f2bb7-118">`INT64VALUE ("22565422744")` returns the *Int64* value **22565422744**.</span></span>

## <a name="example-2"></a><span data-ttu-id="f2bb7-119">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="f2bb7-119">Example 2</span></span>

<span data-ttu-id="f2bb7-120">`INT64VALUE ( VALUE("22565422744.77"))` devuelve el valor *Int64* **22565422744**.</span><span class="sxs-lookup"><span data-stu-id="f2bb7-120">`INT64VALUE ( VALUE("22565422744.77"))` returns the *Int64* value **22565422744**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f2bb7-121">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="f2bb7-121">Additional resources</span></span>

[<span data-ttu-id="f2bb7-122">Funciones de conversión de tipos</span><span class="sxs-lookup"><span data-stu-id="f2bb7-122">Type conversion functions</span></span>](er-functions-category-type-conversion.md)
