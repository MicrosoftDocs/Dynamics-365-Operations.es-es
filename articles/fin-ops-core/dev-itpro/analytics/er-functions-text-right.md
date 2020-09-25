---
title: Función RIGHT de ER
description: Este tema proporciona información general sobre cómo usar la función RIGHT de informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 12/10/2019
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
ms.openlocfilehash: dd53ece77b08fc9723c838da5ba08bf3825b5e56
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2020
ms.locfileid: "3743720"
---
# <a name="right-er-function"></a><span data-ttu-id="143a4-103">Función RIGHT de ER</span><span class="sxs-lookup"><span data-stu-id="143a4-103">RIGHT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="143a4-104">La función `RIGHT` devuelve un valor de tipo *Cadena* que presenta el número especificado de caracteres desde el final de la cadena especificada.</span><span class="sxs-lookup"><span data-stu-id="143a4-104">The `RIGHT` function returns a *String* value that presents the specified number of characters from the end of the specified string.</span></span>

## <a name="syntax"></a><span data-ttu-id="143a4-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="143a4-105">Syntax</span></span>

```vb
RIGHT (text, number)
```

## <a name="arguments"></a><span data-ttu-id="143a4-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="143a4-106">Arguments</span></span>

<span data-ttu-id="143a4-107">`text`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="143a4-107">`text`: *String*</span></span>

<span data-ttu-id="143a4-108">Valor de tipo *Cadena* que representa el texto original.</span><span class="sxs-lookup"><span data-stu-id="143a4-108">A *String* value that represents the original text.</span></span>

<span data-ttu-id="143a4-109">`number`: *Entero*</span><span class="sxs-lookup"><span data-stu-id="143a4-109">`number`: *Integer*</span></span>

<span data-ttu-id="143a4-110">El número de caracteres que se deben devolver desde el final del texto original.</span><span class="sxs-lookup"><span data-stu-id="143a4-110">The number of characters that must be returned from the end of the original text.</span></span>

## <a name="return-values"></a><span data-ttu-id="143a4-111">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="143a4-111">Return values</span></span>

<span data-ttu-id="143a4-112">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="143a4-112">*String*</span></span>

<span data-ttu-id="143a4-113">El valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="143a4-113">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="143a4-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="143a4-114">Example</span></span>

<span data-ttu-id="143a4-115">`RIGHT ("Sample", 3)` devuelve **"ple"**.</span><span class="sxs-lookup"><span data-stu-id="143a4-115">`RIGHT ("Sample", 3)` returns **"ple"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="143a4-116">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="143a4-116">Additional resources</span></span>

[<span data-ttu-id="143a4-117">Funciones de texto</span><span class="sxs-lookup"><span data-stu-id="143a4-117">Text functions</span></span>](er-functions-category-text.md)
