---
title: Función MOD_97 de ER
description: Este tema proporciona información general sobre cómo usar la función MOD_97 de informes electrónicos (ER).
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
ms.openlocfilehash: ce2192c7bc849996e08573d71d8ed43956c8fb89
ms.sourcegitcommit: 3dede95a3b17de920bb0adcb33029f990682752b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/18/2020
ms.locfileid: "3070538"
---
# <span data-ttu-id="81939-103"><a name="MOD_97">Función MOD_97 de ER</a></span><span class="sxs-lookup"><span data-stu-id="81939-103"><a name="MOD_97">MOD_97 ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="81939-104">La función `MOD_97` devuelve un valor *Cadena* que representa una referencia de acreedor como una expresión MOD97, basada en los dígitos del número de factura especificado.</span><span class="sxs-lookup"><span data-stu-id="81939-104">The `MOD_97` function returns a *String* value that represents a creditor reference as a MOD97 expression, based on the digits of the specified invoice number.</span></span>

## <a name="syntax"></a><span data-ttu-id="81939-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="81939-105">Syntax</span></span>

```vb
MOD_97 (invoice number digits)
```

## <a name="arguments"></a><span data-ttu-id="81939-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="81939-106">Arguments</span></span>

<span data-ttu-id="81939-107">`invoice number digits`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="81939-107">`invoice number digits`: *String*</span></span>

<span data-ttu-id="81939-108">Un valor de texto que representa los dígitos de un número de factura.</span><span class="sxs-lookup"><span data-stu-id="81939-108">A text value that represents the digits of an invoice number.</span></span>

## <a name="return-values"></a><span data-ttu-id="81939-109">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="81939-109">Return values</span></span>

<span data-ttu-id="81939-110">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="81939-110">*String*</span></span>

<span data-ttu-id="81939-111">El valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="81939-111">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="81939-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="81939-112">Example</span></span>

<span data-ttu-id="81939-113">`MOD_97 ("VEND-200002")` devuelve **"20000285"**.</span><span class="sxs-lookup"><span data-stu-id="81939-113">`MOD_97 ("VEND-200002")` returns **"20000285"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="81939-114">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="81939-114">Additional resources</span></span>

[<span data-ttu-id="81939-115">Otras funciones (específicas de dominio empresarial)</span><span class="sxs-lookup"><span data-stu-id="81939-115">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)
