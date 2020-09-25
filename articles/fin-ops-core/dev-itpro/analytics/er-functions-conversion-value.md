---
title: Función VALUE ER
description: Este tema proporciona información general sobre cómo usar la función VALUE de informes electrónicos (ER).
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
ms.openlocfilehash: ecbffb7e39d7f2f2bccdfe32d593512a65da163c
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2020
ms.locfileid: "3745522"
---
# <a name="value-er-function"></a><span data-ttu-id="d9f92-103">Función VALUE ER</span><span class="sxs-lookup"><span data-stu-id="d9f92-103">VALUE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d9f92-104">La función `VALUE` devuelve un valor *Real* que se convierte de la cadena especificada.</span><span class="sxs-lookup"><span data-stu-id="d9f92-104">The `VALUE` function returns a *Real* value that is converted from the specified string.</span></span>

## <a name="syntax"></a><span data-ttu-id="d9f92-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d9f92-105">Syntax</span></span>

```vb
VALUE (text)
```

## <a name="arguments"></a><span data-ttu-id="d9f92-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="d9f92-106">Arguments</span></span>

<span data-ttu-id="d9f92-107">`text`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="d9f92-107">`text`: *String*</span></span>

<span data-ttu-id="d9f92-108">Un valor de cadena que debe convertirse en un valor numérico.</span><span class="sxs-lookup"><span data-stu-id="d9f92-108">A string value that must be converted to a numeric value.</span></span>

## <a name="return-values"></a><span data-ttu-id="d9f92-109">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="d9f92-109">Return values</span></span>

<span data-ttu-id="d9f92-110">*Real*</span><span class="sxs-lookup"><span data-stu-id="d9f92-110">*Real*</span></span>

<span data-ttu-id="d9f92-111">El valor numérico resultante.</span><span class="sxs-lookup"><span data-stu-id="d9f92-111">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="d9f92-112">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="d9f92-112">Usage notes</span></span>

<span data-ttu-id="d9f92-113">Las comas y los caracteres de punto (.) se consideran separadores decimales y los guiones iniciales (-) se usan como signo negativo.</span><span class="sxs-lookup"><span data-stu-id="d9f92-113">Commas and dot characters (.) are considered decimal separators, and a leading hyphen (-) is used as a negative sign.</span></span> <span data-ttu-id="d9f92-114">Se generará una excepción en el tiempo de ejecución si la cadena especificada contiene otros caracteres no numéricos.</span><span class="sxs-lookup"><span data-stu-id="d9f92-114">An exception is thrown at runtime if the specified string contains other non-numeric characters.</span></span>

## <a name="example-1"></a><span data-ttu-id="d9f92-115">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="d9f92-115">Example 1</span></span>

<span data-ttu-id="d9f92-116">`VALUE ("1 234,56")` genera una excepción.</span><span class="sxs-lookup"><span data-stu-id="d9f92-116">`VALUE ("1 234,56")` throws an exception.</span></span>

## <a name="example-2"></a><span data-ttu-id="d9f92-117">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="d9f92-117">Example 2</span></span>

<span data-ttu-id="d9f92-118">`VALUE ("1234,56")` devuelve **1234,56**.</span><span class="sxs-lookup"><span data-stu-id="d9f92-118">`VALUE ("1234,56")` returns **1234.56**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d9f92-119">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="d9f92-119">Additional resources</span></span>

[<span data-ttu-id="d9f92-120">Funciones de conversión de tipos</span><span class="sxs-lookup"><span data-stu-id="d9f92-120">Type conversion functions</span></span>](er-functions-category-type-conversion.md)
