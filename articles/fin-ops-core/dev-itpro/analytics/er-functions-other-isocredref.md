---
title: Función ISOCREDREF de ER
description: En este tema se proporciona información sobre cómo usar la función ISOCREDREF de informes electrónicos (ER).
author: NickSelin
ms.date: 12/17/2019
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
ms.openlocfilehash: 51adc6392b07ba4061a475f3072fb35452f15ad2
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5748326"
---
# <a name="isocredref-er-function"></a><span data-ttu-id="9afb8-103">Función ISOCREDREF de ER</span><span class="sxs-lookup"><span data-stu-id="9afb8-103">ISOCREDREF ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9afb8-104">La función `ISOCREDREF` devuelve un valor *Cadena* que representa una referencia de acreedor de la Organización Internacional de Normalización (ISO), basada en los dígitos y los símbolos alfabéticos del número de factura especificado.</span><span class="sxs-lookup"><span data-stu-id="9afb8-104">The `ISOCREDREF` function returns a *String* value that represents an International Organization for Standardization (ISO) creditor reference, based on the digits and alphabetic symbols of the specified invoice number.</span></span>

## <a name="syntax"></a><span data-ttu-id="9afb8-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9afb8-105">Syntax</span></span>

```vb
ISOCREDREF (invoice number digits)
```

## <a name="arguments"></a><span data-ttu-id="9afb8-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="9afb8-106">Arguments</span></span>

<span data-ttu-id="9afb8-107">`invoice number digits`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="9afb8-107">`invoice number digits`: *String*</span></span>

<span data-ttu-id="9afb8-108">Un valor de texto que representa los dígitos de un número de factura.</span><span class="sxs-lookup"><span data-stu-id="9afb8-108">A text value that represents the digits of an invoice number.</span></span>

## <a name="return-values"></a><span data-ttu-id="9afb8-109">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="9afb8-109">Return values</span></span>

<span data-ttu-id="9afb8-110">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="9afb8-110">*String*</span></span>

<span data-ttu-id="9afb8-111">El valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="9afb8-111">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="9afb8-112">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="9afb8-112">Usage notes</span></span>

> [!NOTE] 
> <span data-ttu-id="9afb8-113">Para anular símbolos de los alfabetos que no son compatibles con ISO, el argumento `invoice number digits` se debe traducir antes de que se pase a esta función.</span><span class="sxs-lookup"><span data-stu-id="9afb8-113">To eliminate symbols from alphabets that are't ISO-compliant, the `invoice number digits` argument must be translated before it's passed to this function.</span></span>

## <a name="example"></a><span data-ttu-id="9afb8-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9afb8-114">Example</span></span>

<span data-ttu-id="9afb8-115">`ISOCredRef ("VEND-200002")` devuelve **"RF23VEND-200002"**.</span><span class="sxs-lookup"><span data-stu-id="9afb8-115">`ISOCredRef ("VEND-200002")` returns **"RF23VEND-200002"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9afb8-116">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="9afb8-116">Additional resources</span></span>

[<span data-ttu-id="9afb8-117">Otras funciones (específicas de dominio empresarial)</span><span class="sxs-lookup"><span data-stu-id="9afb8-117">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]