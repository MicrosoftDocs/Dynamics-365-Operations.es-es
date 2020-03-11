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
ms.openlocfilehash: c95663f1aacaf93c1c4bfc8d36d9515f495bf61e
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2020
ms.locfileid: "3040834"
---
# <span data-ttu-id="c955a-103"><a name="TRIM">Función TRIM de ER</a></span><span class="sxs-lookup"><span data-stu-id="c955a-103"><a name="TRIM">TRIM ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c955a-104">La función `TRIM` devuelve la cadena de texto especificada como un valor de tipo *Cadena* después de truncar los espacios principales y finales, y después de haber quitado múltiples espacios entre palabras.</span><span class="sxs-lookup"><span data-stu-id="c955a-104">The `TRIM` function returns the specified text string as a *String* value after leading and trailing spaces have been truncated, and after multiple spaces between words have been removed.</span></span>

## <a name="syntax"></a><span data-ttu-id="c955a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c955a-105">Syntax</span></span>

```vb
TRIM (text )
```

## <a name="arguments"></a><span data-ttu-id="c955a-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="c955a-106">Arguments</span></span>

<span data-ttu-id="c955a-107">`text`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="c955a-107">`text`: *String*</span></span>

<span data-ttu-id="c955a-108">La ruta válida de un origen de datos de tipo *Cadena*.</span><span class="sxs-lookup"><span data-stu-id="c955a-108">The valid path of a data source of the *String* type.</span></span>

## <a name="return-values"></a><span data-ttu-id="c955a-109">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="c955a-109">Return values</span></span>

<span data-ttu-id="c955a-110">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="c955a-110">*String*</span></span>

<span data-ttu-id="c955a-111">El valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="c955a-111">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="c955a-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c955a-112">Example</span></span>

<span data-ttu-id="c955a-113">`TRIM ("`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`Sample`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`text`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`")` devuelve **"Sample text"**.</span><span class="sxs-lookup"><span data-stu-id="c955a-113">`TRIM ("`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`Sample`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`text`&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;`")` returns **"Sample text"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c955a-114">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="c955a-114">Additional resources</span></span>

[<span data-ttu-id="c955a-115">Funciones de texto</span><span class="sxs-lookup"><span data-stu-id="c955a-115">Text functions</span></span>](er-functions-category-text.md)
