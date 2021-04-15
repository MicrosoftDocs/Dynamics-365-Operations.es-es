---
title: Función CURCREDREF de ER
description: En este tema se proporciona información sobre cómo usar la función CURCREDREF de informes electrónicos (ER).
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
ms.openlocfilehash: 65f04e23000e4d2429574db71b18b6907403855e
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5744352"
---
# <a name="curcredref-er-function"></a><span data-ttu-id="9e8e8-103">Función CURCREDREF de ER</span><span class="sxs-lookup"><span data-stu-id="9e8e8-103">CURCREDREF ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9e8e8-104">La función `CURCREDREF` devuelve un valor *Cadena* que representa una referencia de acreedor basada en los dígitos del número de factura especificado.</span><span class="sxs-lookup"><span data-stu-id="9e8e8-104">The `CURCREDREF` function returns a *String* value that represents a creditor reference, based on the digits of the specified invoice number.</span></span>

## <a name="syntax"></a><span data-ttu-id="9e8e8-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9e8e8-105">Syntax</span></span>

```vb
CURCREDREF (invoice number digits)
```

## <a name="arguments"></a><span data-ttu-id="9e8e8-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="9e8e8-106">Arguments</span></span>

<span data-ttu-id="9e8e8-107">`invoice number digits`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="9e8e8-107">`invoice number digits`: *String*</span></span>

<span data-ttu-id="9e8e8-108">Un valor de texto que representa los dígitos de un número de factura.</span><span class="sxs-lookup"><span data-stu-id="9e8e8-108">A text value that represents the digits of an invoice number.</span></span>

## <a name="return-values"></a><span data-ttu-id="9e8e8-109">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="9e8e8-109">Return values</span></span>

<span data-ttu-id="9e8e8-110">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="9e8e8-110">*String*</span></span>

<span data-ttu-id="9e8e8-111">El valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="9e8e8-111">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="9e8e8-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9e8e8-112">Example</span></span>

<span data-ttu-id="9e8e8-113">`CURCredRef ("VEND-200002")` devuelve **"2200002"**.</span><span class="sxs-lookup"><span data-stu-id="9e8e8-113">`CURCredRef ("VEND-200002")` returns **"2200002"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9e8e8-114">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="9e8e8-114">Additional resources</span></span>

[<span data-ttu-id="9e8e8-115">Otras funciones (específicas de dominio empresarial)</span><span class="sxs-lookup"><span data-stu-id="9e8e8-115">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]