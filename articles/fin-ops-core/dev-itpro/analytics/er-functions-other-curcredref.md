---
title: Función CURCREDREF de ER
description: En este tema se proporciona información sobre cómo usar la función CURCREDREF de informes electrónicos (ER).
author: NickSelin
manager: kfend
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
ms.openlocfilehash: d5f126d71abdc9e3e488b4e8476850dc7763fe5a
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "5567625"
---
# <a name="curcredref-er-function"></a><span data-ttu-id="071d4-103">Función CURCREDREF de ER</span><span class="sxs-lookup"><span data-stu-id="071d4-103">CURCREDREF ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="071d4-104">La función `CURCREDREF` devuelve un valor *Cadena* que representa una referencia de acreedor basada en los dígitos del número de factura especificado.</span><span class="sxs-lookup"><span data-stu-id="071d4-104">The `CURCREDREF` function returns a *String* value that represents a creditor reference, based on the digits of the specified invoice number.</span></span>

## <a name="syntax"></a><span data-ttu-id="071d4-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="071d4-105">Syntax</span></span>

```vb
CURCREDREF (invoice number digits)
```

## <a name="arguments"></a><span data-ttu-id="071d4-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="071d4-106">Arguments</span></span>

<span data-ttu-id="071d4-107">`invoice number digits`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="071d4-107">`invoice number digits`: *String*</span></span>

<span data-ttu-id="071d4-108">Un valor de texto que representa los dígitos de un número de factura.</span><span class="sxs-lookup"><span data-stu-id="071d4-108">A text value that represents the digits of an invoice number.</span></span>

## <a name="return-values"></a><span data-ttu-id="071d4-109">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="071d4-109">Return values</span></span>

<span data-ttu-id="071d4-110">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="071d4-110">*String*</span></span>

<span data-ttu-id="071d4-111">El valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="071d4-111">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="071d4-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="071d4-112">Example</span></span>

<span data-ttu-id="071d4-113">`CURCredRef ("VEND-200002")` devuelve **"2200002"**.</span><span class="sxs-lookup"><span data-stu-id="071d4-113">`CURCredRef ("VEND-200002")` returns **"2200002"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="071d4-114">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="071d4-114">Additional resources</span></span>

[<span data-ttu-id="071d4-115">Otras funciones (específicas de dominio empresarial)</span><span class="sxs-lookup"><span data-stu-id="071d4-115">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]