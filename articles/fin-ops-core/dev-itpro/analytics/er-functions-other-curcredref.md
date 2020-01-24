---
title: Función CURCREDREF de ER
description: En este tema se proporciona información sobre cómo usar la función CURCREDREF de informes electrónicos (ER).
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
ms.openlocfilehash: 5633541b1c7e25a0cfb837c4679691506806421b
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917014"
---
# <span data-ttu-id="68eb7-103"><a name="CURCREDREF">Función CURCREDREF de ER</a></span><span class="sxs-lookup"><span data-stu-id="68eb7-103"><a name="CURCREDREF">CURCREDREF ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="68eb7-104">La función `CURCREDREF` devuelve un valor *Cadena* que representa una referencia de acreedor basada en los dígitos del número de factura especificado.</span><span class="sxs-lookup"><span data-stu-id="68eb7-104">The `CURCREDREF` function returns a *String* value that represents a creditor reference, based on the digits of the specified invoice number.</span></span>

## <a name="syntax"></a><span data-ttu-id="68eb7-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="68eb7-105">Syntax</span></span>

```
CURCREDREF (invoice number digits)
```

## <a name="arguments"></a><span data-ttu-id="68eb7-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="68eb7-106">Arguments</span></span>

<span data-ttu-id="68eb7-107">`invoice number digits`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="68eb7-107">`invoice number digits`: *String*</span></span>

<span data-ttu-id="68eb7-108">Un valor de texto que representa los dígitos de un número de factura.</span><span class="sxs-lookup"><span data-stu-id="68eb7-108">A text value that represents the digits of an invoice number.</span></span>

## <a name="return-values"></a><span data-ttu-id="68eb7-109">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="68eb7-109">Return values</span></span>

<span data-ttu-id="68eb7-110">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="68eb7-110">*String*</span></span>

<span data-ttu-id="68eb7-111">El valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="68eb7-111">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="68eb7-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="68eb7-112">Example</span></span>

<span data-ttu-id="68eb7-113">`CURCredRef ("VEND-200002")` devuelve **"2200002"**.</span><span class="sxs-lookup"><span data-stu-id="68eb7-113">`CURCredRef ("VEND-200002")` returns **"2200002"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="68eb7-114">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="68eb7-114">Additional resources</span></span>

[<span data-ttu-id="68eb7-115">Otras funciones (específicas de dominio empresarial)</span><span class="sxs-lookup"><span data-stu-id="68eb7-115">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)