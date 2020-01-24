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
ms.openlocfilehash: 23e63f6b7999399fd5365c616613cbc603774d53
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916945"
---
# <span data-ttu-id="ed12f-103"><a name="MOD_97">Función MOD_97 de ER</a></span><span class="sxs-lookup"><span data-stu-id="ed12f-103"><a name="MOD_97">MOD_97 ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ed12f-104">La función `MOD_97` devuelve un valor *Cadena* que representa una referencia de acreedor como una expresión MOD97, basada en los dígitos del número de factura especificado.</span><span class="sxs-lookup"><span data-stu-id="ed12f-104">The `MOD_97` function returns a *String* value that represents a creditor reference as a MOD97 expression, based on the digits of the specified invoice number.</span></span>

## <a name="syntax"></a><span data-ttu-id="ed12f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ed12f-105">Syntax</span></span>

```
MOD_97 (invoice number digits)
```

## <a name="arguments"></a><span data-ttu-id="ed12f-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="ed12f-106">Arguments</span></span>

<span data-ttu-id="ed12f-107">`invoice number digits`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="ed12f-107">`invoice number digits`: *String*</span></span>

<span data-ttu-id="ed12f-108">Un valor de texto que representa los dígitos de un número de factura.</span><span class="sxs-lookup"><span data-stu-id="ed12f-108">A text value that represents the digits of an invoice number.</span></span>

## <a name="return-values"></a><span data-ttu-id="ed12f-109">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="ed12f-109">Return values</span></span>

<span data-ttu-id="ed12f-110">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="ed12f-110">*String*</span></span>

<span data-ttu-id="ed12f-111">El valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="ed12f-111">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="ed12f-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ed12f-112">Example</span></span>

<span data-ttu-id="ed12f-113">`MOD_97 ("VEND-200002")` devuelve **"20000285"**.</span><span class="sxs-lookup"><span data-stu-id="ed12f-113">`MOD_97 ("VEND-200002")` returns **"20000285"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ed12f-114">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="ed12f-114">Additional resources</span></span>

[<span data-ttu-id="ed12f-115">Otras funciones (específicas de dominio empresarial)</span><span class="sxs-lookup"><span data-stu-id="ed12f-115">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)