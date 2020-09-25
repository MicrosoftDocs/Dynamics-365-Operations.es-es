---
title: Función ISOCREDREF de ER
description: En este tema se proporciona información sobre cómo usar la función ISOCREDREF de informes electrónicos (ER).
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
ms.openlocfilehash: d6e5d025e7de15c27b19711ea5b597d75bdf3d41
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2020
ms.locfileid: "3744104"
---
# <a name="isocredref-er-function"></a><span data-ttu-id="2980a-103">Función ISOCREDREF de ER</span><span class="sxs-lookup"><span data-stu-id="2980a-103">ISOCREDREF ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2980a-104">La función `ISOCREDREF` devuelve un valor *Cadena* que representa una referencia de acreedor de la Organización Internacional de Normalización (ISO), basada en los dígitos y los símbolos alfabéticos del número de factura especificado.</span><span class="sxs-lookup"><span data-stu-id="2980a-104">The `ISOCREDREF` function returns a *String* value that represents an International Organization for Standardization (ISO) creditor reference, based on the digits and alphabetic symbols of the specified invoice number.</span></span>

## <a name="syntax"></a><span data-ttu-id="2980a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2980a-105">Syntax</span></span>

```vb
ISOCREDREF (invoice number digits)
```

## <a name="arguments"></a><span data-ttu-id="2980a-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="2980a-106">Arguments</span></span>

<span data-ttu-id="2980a-107">`invoice number digits`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="2980a-107">`invoice number digits`: *String*</span></span>

<span data-ttu-id="2980a-108">Un valor de texto que representa los dígitos de un número de factura.</span><span class="sxs-lookup"><span data-stu-id="2980a-108">A text value that represents the digits of an invoice number.</span></span>

## <a name="return-values"></a><span data-ttu-id="2980a-109">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="2980a-109">Return values</span></span>

<span data-ttu-id="2980a-110">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="2980a-110">*String*</span></span>

<span data-ttu-id="2980a-111">El valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="2980a-111">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="2980a-112">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="2980a-112">Usage notes</span></span>

> [!NOTE] 
> <span data-ttu-id="2980a-113">Para anular símbolos de los alfabetos que no son compatibles con ISO, el argumento `invoice number digits` se debe traducir antes de que se pase a esta función.</span><span class="sxs-lookup"><span data-stu-id="2980a-113">To eliminate symbols from alphabets that are't ISO-compliant, the `invoice number digits` argument must be translated before it's passed to this function.</span></span>

## <a name="example"></a><span data-ttu-id="2980a-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2980a-114">Example</span></span>

<span data-ttu-id="2980a-115">`ISOCredRef ("VEND-200002")` devuelve **"RF23VEND-200002"**.</span><span class="sxs-lookup"><span data-stu-id="2980a-115">`ISOCredRef ("VEND-200002")` returns **"RF23VEND-200002"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2980a-116">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="2980a-116">Additional resources</span></span>

[<span data-ttu-id="2980a-117">Otras funciones (específicas de dominio empresarial)</span><span class="sxs-lookup"><span data-stu-id="2980a-117">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)
