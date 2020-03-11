---
title: Función TRANSLATE de ER
description: Este tema proporciona información general sobre cómo usar la función TRANSLATE de informes electrónicos (ER).
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
ms.openlocfilehash: 07fe19c5f66c33e336f76f3a72d3bbda0c7e8d86
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2020
ms.locfileid: "3040926"
---
# <span data-ttu-id="25e1d-103"><a name="TRANSLATE">Función TRANSLATE de ER</a></span><span class="sxs-lookup"><span data-stu-id="25e1d-103"><a name="TRANSLATE">TRANSLATE ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="25e1d-104">La función `TRANSLATE` devuelve la cadena de texto especificada como un valor de tipo *Cadena* después de reemplazarla total o parcialmente por otra cadena.</span><span class="sxs-lookup"><span data-stu-id="25e1d-104">The `TRANSLATE` function returns the specified text string as a *String* value after all or part of it has been replaced with another string.</span></span>

## <a name="syntax"></a><span data-ttu-id="25e1d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="25e1d-105">Syntax</span></span>

```vb
TRANSLATE (text , pattern, replacement)
```

## <a name="arguments"></a><span data-ttu-id="25e1d-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="25e1d-106">Arguments</span></span>

<span data-ttu-id="25e1d-107">`text`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="25e1d-107">`text`: *String*</span></span>

<span data-ttu-id="25e1d-108">La ruta válida de un origen de datos de tipo *Cadena*.</span><span class="sxs-lookup"><span data-stu-id="25e1d-108">The valid path of a data source of the *String* type.</span></span>

<span data-ttu-id="25e1d-109">`pattern`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="25e1d-109">`pattern`: *String*</span></span>

<span data-ttu-id="25e1d-110">El texto que se va a reemplazar.</span><span class="sxs-lookup"><span data-stu-id="25e1d-110">The text that must be replaced.</span></span>

<span data-ttu-id="25e1d-111">`replacement`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="25e1d-111">`replacement`: *String*</span></span>

<span data-ttu-id="25e1d-112">El texto que se va a usar como reemplazo.</span><span class="sxs-lookup"><span data-stu-id="25e1d-112">The text to use as a replacement.</span></span>

## <a name="return-values"></a><span data-ttu-id="25e1d-113">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="25e1d-113">Return values</span></span>

<span data-ttu-id="25e1d-114">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="25e1d-114">*String*</span></span>

<span data-ttu-id="25e1d-115">El valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="25e1d-115">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="25e1d-116">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="25e1d-116">Example</span></span>

<span data-ttu-id="25e1d-117">`TRANSLATE ("abcdef", "cd", "GH")` reemplaza el patrón **"cd"** por la cadena **"GH"** y devuelve **"abGHef"**.</span><span class="sxs-lookup"><span data-stu-id="25e1d-117">`TRANSLATE ("abcdef", "cd", "GH")` replaces the pattern **"cd"** with the string **"GH"** and returns **"abGHef"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="25e1d-118">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="25e1d-118">Additional resources</span></span>

[<span data-ttu-id="25e1d-119">Funciones de texto</span><span class="sxs-lookup"><span data-stu-id="25e1d-119">Text functions</span></span>](er-functions-category-text.md)
