---
title: Función TRIM de ER
description: Este tema proporciona información general sobre cómo usar la función TRIM de informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: b671ef72a3558c17fb16db939770394b225656da
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "5560046"
---
# <a name="trim-er-function"></a><span data-ttu-id="30265-103">Función TRIM de ER</span><span class="sxs-lookup"><span data-stu-id="30265-103">TRIM ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="30265-104">La función `TRIM` devuelve la cadena de texto especificada como un valor de tipo *Cadena* después de truncar los espacios principales y finales, y después de haber quitado múltiples espacios entre palabras.</span><span class="sxs-lookup"><span data-stu-id="30265-104">The `TRIM` function returns the specified text string as a *String* value after leading and trailing spaces have been truncated, and after multiple spaces between words have been removed.</span></span>

## <a name="syntax"></a><span data-ttu-id="30265-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="30265-105">Syntax</span></span>

```vb
TRIM (text )
```

## <a name="arguments"></a><span data-ttu-id="30265-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="30265-106">Arguments</span></span>

<span data-ttu-id="30265-107">`text`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="30265-107">`text`: *String*</span></span>

<span data-ttu-id="30265-108">La ruta válida de un origen de datos de tipo *Cadena*.</span><span class="sxs-lookup"><span data-stu-id="30265-108">The valid path of a data source of the *String* type.</span></span>

## <a name="return-values"></a><span data-ttu-id="30265-109">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="30265-109">Return values</span></span>

<span data-ttu-id="30265-110">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="30265-110">*String*</span></span>

<span data-ttu-id="30265-111">El valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="30265-111">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="30265-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="30265-112">Example</span></span>

<span data-ttu-id="30265-113">`TRIM ("`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`Sample`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`text`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`")` devuelve **"Sample text"**.</span><span class="sxs-lookup"><span data-stu-id="30265-113">`TRIM ("`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`Sample`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`text`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`")` returns **"Sample text"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="30265-114">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="30265-114">Additional resources</span></span>

[<span data-ttu-id="30265-115">Funciones de texto</span><span class="sxs-lookup"><span data-stu-id="30265-115">Text functions</span></span>](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]