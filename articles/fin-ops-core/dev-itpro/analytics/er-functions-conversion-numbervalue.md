---
title: Función NUMBERVALUE ER
description: En este tema se proporciona información sobre cómo usar la función NUMBERVALUE de informes electrónicos (ER).
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
ms.openlocfilehash: 13346c4810d6c93d4ef47ce525831332562c7f51
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2020
ms.locfileid: "3743408"
---
# <a name="numbervalue-er-function"></a><span data-ttu-id="16899-103">Función NUMBERVALUE ER</span><span class="sxs-lookup"><span data-stu-id="16899-103">NUMBERVALUE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="16899-104">La función `NUMBERVALUE` devuelve un valor *Real* que se convierte del valor *Cadena* especificado.</span><span class="sxs-lookup"><span data-stu-id="16899-104">The `NUMBERVALUE` function returns a *Real* value that is converted from the specified *String* value.</span></span> <span data-ttu-id="16899-105">Durante la conversión, se consideran los separadores de agrupación decimal y de dígitos especificados.</span><span class="sxs-lookup"><span data-stu-id="16899-105">During the conversion, the specified decimal and digit grouping separators are considered.</span></span>

## <a name="syntax"></a><span data-ttu-id="16899-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="16899-106">Syntax</span></span>

```vb
NUMBERVALUE (text, decimal separator, digit grouping separator)
```

## <a name="arguments"></a><span data-ttu-id="16899-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="16899-107">Arguments</span></span>

<span data-ttu-id="16899-108">`text`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="16899-108">`text`: *String*</span></span>

<span data-ttu-id="16899-109">Un valor de texto que debe convertirse en un número *Real*.</span><span class="sxs-lookup"><span data-stu-id="16899-109">A text value that must be converted to a *Real* number.</span></span>

<span data-ttu-id="16899-110">`decimal separator`: Cadena</span><span class="sxs-lookup"><span data-stu-id="16899-110">`decimal separator`: String</span></span>

<span data-ttu-id="16899-111">Un separador decimal.</span><span class="sxs-lookup"><span data-stu-id="16899-111">A decimal separator.</span></span> <span data-ttu-id="16899-112">Se utiliza para separar las partes enteras y fraccionarias de un número decimal.</span><span class="sxs-lookup"><span data-stu-id="16899-112">It's used to separate the integer and fractional parts of a decimal number.</span></span>

<span data-ttu-id="16899-113">`digit grouping separator`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="16899-113">`digit grouping separator`: *String*</span></span>

<span data-ttu-id="16899-114">Un separador de agrupación de dígitos.</span><span class="sxs-lookup"><span data-stu-id="16899-114">A digit grouping separator.</span></span> <span data-ttu-id="16899-115">Se usa como el separador de miles.</span><span class="sxs-lookup"><span data-stu-id="16899-115">It's used as the thousands separator.</span></span>

## <a name="return-values"></a><span data-ttu-id="16899-116">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="16899-116">Return values</span></span>

<span data-ttu-id="16899-117">*Real*</span><span class="sxs-lookup"><span data-stu-id="16899-117">*Real*</span></span>

<span data-ttu-id="16899-118">El valor numérico resultante.</span><span class="sxs-lookup"><span data-stu-id="16899-118">The resulting numeric value.</span></span>

## <a name="example"></a><span data-ttu-id="16899-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="16899-119">Example</span></span>

<span data-ttu-id="16899-120">`NUMBERVALUE( "1 234,56", ",", " ")` devuelve **1234,56**.</span><span class="sxs-lookup"><span data-stu-id="16899-120">`NUMBERVALUE( "1 234,56", ",", " ")` returns **1234.56**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="16899-121">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="16899-121">Additional resources</span></span>

[<span data-ttu-id="16899-122">Funciones de conversión de tipos</span><span class="sxs-lookup"><span data-stu-id="16899-122">Type conversion functions</span></span>](er-functions-category-type-conversion.md)
