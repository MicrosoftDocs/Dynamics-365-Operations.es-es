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
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 56b32a802674725347ab496d3a09b99c8f04446d
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "4681217"
---
# <a name="value-er-function"></a><span data-ttu-id="5e81a-103">Función VALUE ER</span><span class="sxs-lookup"><span data-stu-id="5e81a-103">VALUE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5e81a-104">La función `VALUE` devuelve un valor *Real* que se convierte de la cadena especificada.</span><span class="sxs-lookup"><span data-stu-id="5e81a-104">The `VALUE` function returns a *Real* value that is converted from the specified string.</span></span>

## <a name="syntax"></a><span data-ttu-id="5e81a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5e81a-105">Syntax</span></span>

```vb
VALUE (text)
```

## <a name="arguments"></a><span data-ttu-id="5e81a-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="5e81a-106">Arguments</span></span>

<span data-ttu-id="5e81a-107">`text`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="5e81a-107">`text`: *String*</span></span>

<span data-ttu-id="5e81a-108">Un valor de cadena que debe convertirse en un valor numérico.</span><span class="sxs-lookup"><span data-stu-id="5e81a-108">A string value that must be converted to a numeric value.</span></span>

## <a name="return-values"></a><span data-ttu-id="5e81a-109">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="5e81a-109">Return values</span></span>

<span data-ttu-id="5e81a-110">*Real*</span><span class="sxs-lookup"><span data-stu-id="5e81a-110">*Real*</span></span>

<span data-ttu-id="5e81a-111">El valor numérico resultante.</span><span class="sxs-lookup"><span data-stu-id="5e81a-111">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="5e81a-112">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="5e81a-112">Usage notes</span></span>

<span data-ttu-id="5e81a-113">Las comas y los caracteres de punto (.) se consideran separadores decimales y los guiones iniciales (-) se usan como signo negativo.</span><span class="sxs-lookup"><span data-stu-id="5e81a-113">Commas and dot characters (.) are considered decimal separators, and a leading hyphen (-) is used as a negative sign.</span></span> <span data-ttu-id="5e81a-114">Se generará una excepción en el tiempo de ejecución si la cadena especificada contiene otros caracteres no numéricos.</span><span class="sxs-lookup"><span data-stu-id="5e81a-114">An exception is thrown at runtime if the specified string contains other non-numeric characters.</span></span>

## <a name="example-1"></a><span data-ttu-id="5e81a-115">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="5e81a-115">Example 1</span></span>

<span data-ttu-id="5e81a-116">`VALUE ("1 234,56")` genera una excepción.</span><span class="sxs-lookup"><span data-stu-id="5e81a-116">`VALUE ("1 234,56")` throws an exception.</span></span>

## <a name="example-2"></a><span data-ttu-id="5e81a-117">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="5e81a-117">Example 2</span></span>

<span data-ttu-id="5e81a-118">`VALUE ("1234,56")` devuelve **1234,56**.</span><span class="sxs-lookup"><span data-stu-id="5e81a-118">`VALUE ("1234,56")` returns **1234.56**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5e81a-119">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="5e81a-119">Additional resources</span></span>

[<span data-ttu-id="5e81a-120">Funciones de conversión de tipos</span><span class="sxs-lookup"><span data-stu-id="5e81a-120">Type conversion functions</span></span>](er-functions-category-type-conversion.md)
