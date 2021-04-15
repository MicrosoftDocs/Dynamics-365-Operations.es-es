---
title: Función NUMBERVALUE ER
description: En este tema se proporciona información sobre cómo usar la función NUMBERVALUE de informes electrónicos (ER).
author: NickSelin
ms.date: 12/05/2019
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
ms.openlocfilehash: 84d7f17f37a83547522cf09047b72100f6f5b859
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5755357"
---
# <a name="numbervalue-er-function"></a><span data-ttu-id="a2e05-103">Función NUMBERVALUE ER</span><span class="sxs-lookup"><span data-stu-id="a2e05-103">NUMBERVALUE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a2e05-104">La función `NUMBERVALUE` devuelve un valor *Real* que se convierte del valor *Cadena* especificado.</span><span class="sxs-lookup"><span data-stu-id="a2e05-104">The `NUMBERVALUE` function returns a *Real* value that is converted from the specified *String* value.</span></span> <span data-ttu-id="a2e05-105">Durante la conversión, se consideran los separadores de agrupación decimal y de dígitos especificados.</span><span class="sxs-lookup"><span data-stu-id="a2e05-105">During the conversion, the specified decimal and digit grouping separators are considered.</span></span>

## <a name="syntax"></a><span data-ttu-id="a2e05-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a2e05-106">Syntax</span></span>

```vb
NUMBERVALUE (text, decimal separator, digit grouping separator)
```

## <a name="arguments"></a><span data-ttu-id="a2e05-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="a2e05-107">Arguments</span></span>

<span data-ttu-id="a2e05-108">`text`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="a2e05-108">`text`: *String*</span></span>

<span data-ttu-id="a2e05-109">Un valor de texto que debe convertirse en un número *Real*.</span><span class="sxs-lookup"><span data-stu-id="a2e05-109">A text value that must be converted to a *Real* number.</span></span>

<span data-ttu-id="a2e05-110">`decimal separator`: Cadena</span><span class="sxs-lookup"><span data-stu-id="a2e05-110">`decimal separator`: String</span></span>

<span data-ttu-id="a2e05-111">Un separador decimal.</span><span class="sxs-lookup"><span data-stu-id="a2e05-111">A decimal separator.</span></span> <span data-ttu-id="a2e05-112">Se utiliza para separar las partes enteras y fraccionarias de un número decimal.</span><span class="sxs-lookup"><span data-stu-id="a2e05-112">It's used to separate the integer and fractional parts of a decimal number.</span></span>

<span data-ttu-id="a2e05-113">`digit grouping separator`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="a2e05-113">`digit grouping separator`: *String*</span></span>

<span data-ttu-id="a2e05-114">Un separador de agrupación de dígitos.</span><span class="sxs-lookup"><span data-stu-id="a2e05-114">A digit grouping separator.</span></span> <span data-ttu-id="a2e05-115">Se usa como el separador de miles.</span><span class="sxs-lookup"><span data-stu-id="a2e05-115">It's used as the thousands separator.</span></span>

## <a name="return-values"></a><span data-ttu-id="a2e05-116">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="a2e05-116">Return values</span></span>

<span data-ttu-id="a2e05-117">*Real*</span><span class="sxs-lookup"><span data-stu-id="a2e05-117">*Real*</span></span>

<span data-ttu-id="a2e05-118">El valor numérico resultante.</span><span class="sxs-lookup"><span data-stu-id="a2e05-118">The resulting numeric value.</span></span>

## <a name="example"></a><span data-ttu-id="a2e05-119">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a2e05-119">Example</span></span>

<span data-ttu-id="a2e05-120">`NUMBERVALUE( "1 234,56", ",", " ")` devuelve **1234,56**.</span><span class="sxs-lookup"><span data-stu-id="a2e05-120">`NUMBERVALUE( "1 234,56", ",", " ")` returns **1234.56**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a2e05-121">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="a2e05-121">Additional resources</span></span>

[<span data-ttu-id="a2e05-122">Funciones de conversión de tipos</span><span class="sxs-lookup"><span data-stu-id="a2e05-122">Type conversion functions</span></span>](er-functions-category-type-conversion.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]