---
title: Función CH_BANK_MOD_10 de ER
description: Este tema proporciona información general sobre cómo usar la función CH_BANK_MOD_10 de informes electrónicos (ER).
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
ms.openlocfilehash: c18a7f96096fbc6bbc7b6d15135c11bd70960d26
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2020
ms.locfileid: "3744479"
---
# <a name="ch_bank_mod_10-er-function"></a><span data-ttu-id="dca48-103">Función CH_BANK_MOD_10 de ER</span><span class="sxs-lookup"><span data-stu-id="dca48-103">CH_BANK_MOD_10 ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="dca48-104">La función `CH_BANK_MOD_10` devuelve un valor *Cadena* que representa una referencia de acreedor como una expresión MOD10, basada en los dígitos del número de factura especificado.</span><span class="sxs-lookup"><span data-stu-id="dca48-104">The `CH_BANK_MOD_10` function returns a *String* value that represents a creditor reference as an MOD10 expression, based on the digits of the specified invoice number.</span></span>

## <a name="syntax"></a><span data-ttu-id="dca48-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dca48-105">Syntax</span></span>

```vb
CH_BANK_MOD_10 (invoice number digits)
```

## <a name="arguments"></a><span data-ttu-id="dca48-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="dca48-106">Arguments</span></span>

<span data-ttu-id="dca48-107">`invoice number digits`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="dca48-107">`invoice number digits`: *String*</span></span>

<span data-ttu-id="dca48-108">Un valor de texto que representa los dígitos de un número de factura.</span><span class="sxs-lookup"><span data-stu-id="dca48-108">A text value that represents the digits of an invoice number.</span></span>

## <a name="return-values"></a><span data-ttu-id="dca48-109">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="dca48-109">Return values</span></span>

<span data-ttu-id="dca48-110">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="dca48-110">*String*</span></span>

<span data-ttu-id="dca48-111">El valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="dca48-111">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="dca48-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="dca48-112">Example</span></span>

<span data-ttu-id="dca48-113">`CH_BANK_MOD_10 ("VEND-200002")` devuelve **3**.</span><span class="sxs-lookup"><span data-stu-id="dca48-113">`CH_BANK_MOD_10 ("VEND-200002")` returns **3**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="dca48-114">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="dca48-114">Additional resources</span></span>

[<span data-ttu-id="dca48-115">Otras funciones (específicas de dominio empresarial)</span><span class="sxs-lookup"><span data-stu-id="dca48-115">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)
