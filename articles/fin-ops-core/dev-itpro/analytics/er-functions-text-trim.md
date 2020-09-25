---
title: Función TRIM de ER
description: Este tema proporciona información general sobre cómo usar la función TRIM de informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: a1f7999ccbcd167280cca1abc48377c36d2bc15f
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2020
ms.locfileid: "3744224"
---
# <a name="trim-er-function"></a><span data-ttu-id="d7fcd-103">Función TRIM de ER</span><span class="sxs-lookup"><span data-stu-id="d7fcd-103">TRIM ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d7fcd-104">La función `TRIM` devuelve la cadena de texto especificada como un valor de tipo *Cadena* después de truncar los espacios principales y finales, y después de haber quitado múltiples espacios entre palabras.</span><span class="sxs-lookup"><span data-stu-id="d7fcd-104">The `TRIM` function returns the specified text string as a *String* value after leading and trailing spaces have been truncated, and after multiple spaces between words have been removed.</span></span>

## <a name="syntax"></a><span data-ttu-id="d7fcd-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d7fcd-105">Syntax</span></span>

```vb
TRIM (text )
```

## <a name="arguments"></a><span data-ttu-id="d7fcd-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="d7fcd-106">Arguments</span></span>

<span data-ttu-id="d7fcd-107">`text`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="d7fcd-107">`text`: *String*</span></span>

<span data-ttu-id="d7fcd-108">La ruta válida de un origen de datos de tipo *Cadena*.</span><span class="sxs-lookup"><span data-stu-id="d7fcd-108">The valid path of a data source of the *String* type.</span></span>

## <a name="return-values"></a><span data-ttu-id="d7fcd-109">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="d7fcd-109">Return values</span></span>

<span data-ttu-id="d7fcd-110">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="d7fcd-110">*String*</span></span>

<span data-ttu-id="d7fcd-111">El valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="d7fcd-111">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="d7fcd-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d7fcd-112">Example</span></span>

<span data-ttu-id="d7fcd-113">`TRIM ("`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`Sample`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`text`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`")` devuelve **"Sample text"**.</span><span class="sxs-lookup"><span data-stu-id="d7fcd-113">`TRIM ("`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`Sample`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`text`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`")` returns **"Sample text"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d7fcd-114">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="d7fcd-114">Additional resources</span></span>

[<span data-ttu-id="d7fcd-115">Funciones de texto</span><span class="sxs-lookup"><span data-stu-id="d7fcd-115">Text functions</span></span>](er-functions-category-text.md)
