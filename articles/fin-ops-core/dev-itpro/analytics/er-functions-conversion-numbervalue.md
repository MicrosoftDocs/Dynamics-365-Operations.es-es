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
ms.openlocfilehash: 80f0606dc3842cdfa56d41e2815eccd7518218b8
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916531"
---
# <span data-ttu-id="50fa7-103"><a name="NUMBERVALUE">Función NUMBERVALUE ER</a></span><span class="sxs-lookup"><span data-stu-id="50fa7-103"><a name="NUMBERVALUE">NUMBERVALUE ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="50fa7-104">La función `NUMBERVALUE` devuelve un valor *Real* que se convierte del valor *Cadena* especificado.</span><span class="sxs-lookup"><span data-stu-id="50fa7-104">The `NUMBERVALUE` function returns a *Real* value that is converted from the specified *String* value.</span></span> <span data-ttu-id="50fa7-105">Durante la conversión, se consideran los separadores de agrupación decimal y de dígitos especificados.</span><span class="sxs-lookup"><span data-stu-id="50fa7-105">During the conversion, the specified decimal and digit grouping separators are considered.</span></span>

## <a name="syntax"></a><span data-ttu-id="50fa7-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="50fa7-106">Syntax</span></span>

```
NUMBERVALUE (text, decimal separator, digit grouping separator)
```

## <a name="arguments"></a><span data-ttu-id="50fa7-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="50fa7-107">Arguments</span></span>

<span data-ttu-id="50fa7-108">`text`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="50fa7-108">`text`: *String*</span></span>

<span data-ttu-id="50fa7-109">Un valor de texto que debe convertirse en un número *Real*.</span><span class="sxs-lookup"><span data-stu-id="50fa7-109">A text value that must be converted to a *Real* number.</span></span>

<span data-ttu-id="50fa7-110">`decimal separator`: Cadena</span><span class="sxs-lookup"><span data-stu-id="50fa7-110">`decimal separator`: String</span></span>

<span data-ttu-id="50fa7-111">Un separador decimal.</span><span class="sxs-lookup"><span data-stu-id="50fa7-111">A decimal separator.</span></span> <span data-ttu-id="50fa7-112">Se utiliza para separar las partes enteras y fraccionarias de un número decimal.</span><span class="sxs-lookup"><span data-stu-id="50fa7-112">It's used to separate the integer and fractional parts of a decimal number.</span></span>

<span data-ttu-id="50fa7-113">`digit grouping separator`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="50fa7-113">`digit grouping separator`: *String*</span></span>

<span data-ttu-id="50fa7-114">Un separador de agrupación de dígitos.</span><span class="sxs-lookup"><span data-stu-id="50fa7-114">A digit grouping separator.</span></span> <span data-ttu-id="50fa7-115">Se usa como el separador de miles.</span><span class="sxs-lookup"><span data-stu-id="50fa7-115">It's used as the thousands separator.</span></span>

## <a name="return-values"></a><span data-ttu-id="50fa7-116">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="50fa7-116">Return values</span></span>

<span data-ttu-id="50fa7-117">*Real*</span><span class="sxs-lookup"><span data-stu-id="50fa7-117">*Real*</span></span>

<span data-ttu-id="50fa7-118">El valor numérico resultante.</span><span class="sxs-lookup"><span data-stu-id="50fa7-118">The resulting numeric value.</span></span>

## <a name="example"></a><span data-ttu-id="50fa7-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="50fa7-119">Example</span></span>

<span data-ttu-id="50fa7-120">`NUMBERVALUE( "1 234,56", ",", " ")` devuelve **1234,56**.</span><span class="sxs-lookup"><span data-stu-id="50fa7-120">`NUMBERVALUE( "1 234,56", ",", " ")` returns **1234.56**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="50fa7-121">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="50fa7-121">Additional resources</span></span>

[<span data-ttu-id="50fa7-122">Funciones de conversión de tipos</span><span class="sxs-lookup"><span data-stu-id="50fa7-122">Type conversion functions</span></span>](er-functions-category-type-conversion.md)
