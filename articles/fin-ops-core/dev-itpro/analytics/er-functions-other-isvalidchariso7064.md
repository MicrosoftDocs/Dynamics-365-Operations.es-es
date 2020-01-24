---
title: Función ISVALIDCHARACTERISO7064 de ER
description: Este tema proporciona información general sobre cómo usar la función ISVALIDCHARACTERISO7064 de informes electrónicos (ER).
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
ms.openlocfilehash: 6f6f3326c9ca5cdcb3cef52f243d6d3da34251ce
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/20/2019
ms.locfileid: "2915933"
---
# <span data-ttu-id="a8f40-103"><a name="ISVALIDCHARACTERISO7064">Función ISVALIDCHARACTERISO7064 de ER</a></span><span class="sxs-lookup"><span data-stu-id="a8f40-103"><a name="ISVALIDCHARACTERISO7064">ISVALIDCHARACTERISO7064 ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a8f40-104">La función `ISVALIDCHARACTERISO7064` devuelve un valor *Booleano* de **TRUE** si la cadena especificada representa un número internacional de cuenta bancaria válido (IBAN).</span><span class="sxs-lookup"><span data-stu-id="a8f40-104">The `ISVALIDCHARACTERISO7064` function returns a *Boolean* value of **TRUE** if the specified string represents a valid international bank account number (IBAN).</span></span> <span data-ttu-id="a8f40-105">De lo contrario, la expresión devuelve un valor *Booleano* de **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="a8f40-105">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span>

## <a name="syntax"></a><span data-ttu-id="a8f40-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a8f40-106">Syntax</span></span>

```
ISVALIDCHARACTERISO7064 (text)
```

## <a name="arguments"></a><span data-ttu-id="a8f40-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="a8f40-107">Arguments</span></span>

<span data-ttu-id="a8f40-108">`text`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="a8f40-108">`text`: *String*</span></span>

<span data-ttu-id="a8f40-109">Un valor de texto que representa un IBAN.</span><span class="sxs-lookup"><span data-stu-id="a8f40-109">A text value that represents an IBAN.</span></span>

## <a name="return-values"></a><span data-ttu-id="a8f40-110">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="a8f40-110">Return values</span></span>

<span data-ttu-id="a8f40-111">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="a8f40-111">*String*</span></span>

<span data-ttu-id="a8f40-112">El valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="a8f40-112">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="a8f40-113">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a8f40-113">Example</span></span>

<span data-ttu-id="a8f40-114">`ISVALIDCHARACTERISO7064 ("AT61 1904 3002 3457 3201")` devuelve **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="a8f40-114">`ISVALIDCHARACTERISO7064 ("AT61 1904 3002 3457 3201")` returns **TRUE**.</span></span> 

<span data-ttu-id="a8f40-115">`ISVALIDCHARACTERISO7064 ("AT61")` devuelve **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="a8f40-115">`ISVALIDCHARACTERISO7064 ("AT61")` returns **FALSE**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a8f40-116">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="a8f40-116">Additional resources</span></span>

[<span data-ttu-id="a8f40-117">Otras funciones (específicas de dominio empresarial)</span><span class="sxs-lookup"><span data-stu-id="a8f40-117">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)
