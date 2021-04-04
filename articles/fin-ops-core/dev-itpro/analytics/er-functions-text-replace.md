---
title: Función REPLACE de ER
description: Este tema proporciona información general sobre cómo usar la función REPLACE de informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 04/02/2020
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
ms.openlocfilehash: c9f1abe397e05f816fcf226df76362d872819f57
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "5570273"
---
# <a name="replace-er-function"></a><span data-ttu-id="ee4cf-103">Función REPLACE de ER</span><span class="sxs-lookup"><span data-stu-id="ee4cf-103">REPLACE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ee4cf-104">La función `REPLACE` devuelve la cadena de texto especificada como un valor de tipo *Cadena* después de reemplazarla total o parcialmente por otra cadena.</span><span class="sxs-lookup"><span data-stu-id="ee4cf-104">The `REPLACE` function returns the specified text string as a *String* value after all or part of it has been replaced with another string.</span></span>

## <a name="syntax"></a><span data-ttu-id="ee4cf-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ee4cf-105">Syntax</span></span>

```vb
REPLACE (text, pattern, replacement, regular expression flag)
```

## <a name="arguments"></a><span data-ttu-id="ee4cf-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="ee4cf-106">Arguments</span></span>

<span data-ttu-id="ee4cf-107">`text`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="ee4cf-107">`text`: *String*</span></span>

<span data-ttu-id="ee4cf-108">La ruta válida de un origen de datos de tipo *Cadena*.</span><span class="sxs-lookup"><span data-stu-id="ee4cf-108">The valid path of a data source of the *String* type.</span></span>

<span data-ttu-id="ee4cf-109">`pattern`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="ee4cf-109">`pattern`: *String*</span></span>

<span data-ttu-id="ee4cf-110">Si el argumento `regular expression flag` es **FALSE**, este argumento contiene el texto que debe ser reemplazado.</span><span class="sxs-lookup"><span data-stu-id="ee4cf-110">If the `regular expression flag` argument is **FALSE**, this argument contains the text that must be replaced.</span></span>

<span data-ttu-id="ee4cf-111">Si el argumento `regular expression flag` es **TRUE**, este argumento contiene una expresión regular que define tanto un patrón de búsqueda como el texto de reemplazo.</span><span class="sxs-lookup"><span data-stu-id="ee4cf-111">If the `regular expression flag` argument is **TRUE**, this argument contains a regular expression that defines both a search pattern and the replacement text.</span></span>

<span data-ttu-id="ee4cf-112">`replacement`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="ee4cf-112">`replacement`: *String*</span></span>

<span data-ttu-id="ee4cf-113">Si el argumento `regular expression flag` es **FALSE**, este argumento contiene el texto que debe usarse como reemplazo.</span><span class="sxs-lookup"><span data-stu-id="ee4cf-113">If the `regular expression flag` argument is **FALSE**, this argument contains the text to use as a replacement.</span></span>

<span data-ttu-id="ee4cf-114">Si el argumento `regular expression flag` es **TRUE**, este argumento no se usa.</span><span class="sxs-lookup"><span data-stu-id="ee4cf-114">If the `regular expression flag` argument is **TRUE**, this argument isn't used.</span></span>

<span data-ttu-id="ee4cf-115">`regular expression flag`: *Booleano*</span><span class="sxs-lookup"><span data-stu-id="ee4cf-115">`regular expression flag`: *Boolean*</span></span>

<span data-ttu-id="ee4cf-116">Valor de tipo *Booleano* que indica si se usa una expresión regular para hacer el reemplazo.</span><span class="sxs-lookup"><span data-stu-id="ee4cf-116">A *Boolean* value that indicates whether a regular expression is used to do the replacement.</span></span>

## <a name="return-values"></a><span data-ttu-id="ee4cf-117">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="ee4cf-117">Return values</span></span>

<span data-ttu-id="ee4cf-118">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="ee4cf-118">*String*</span></span>

<span data-ttu-id="ee4cf-119">El valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="ee4cf-119">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="ee4cf-120">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="ee4cf-120">Usage notes</span></span>

<span data-ttu-id="ee4cf-121">Si el argumento de `regular expression flag` es **TRUE**, esta función devuelve la cadena especificada después de que haya sido modificada aplicando la expresión regular especificada por el argumento `pattern`.</span><span class="sxs-lookup"><span data-stu-id="ee4cf-121">If the `regular expression flag` argument is **TRUE**, this function returns the specified string after it has been changed by applying the regular expression that is specified by the `pattern` argument.</span></span> <span data-ttu-id="ee4cf-122">La expresión regular se usa para buscar los caracteres que hay que reemplazar.</span><span class="sxs-lookup"><span data-stu-id="ee4cf-122">The regular expression is used to find the characters that must be replaced.</span></span>

<span data-ttu-id="ee4cf-123">Si el argumento `regular expression flag` es **FALSO**, esta función devuelve la cadena especificada después de que el conjunto de caracteres que se definen en el argumento `pattern` ha sido reemplazado por caracteres del argumento `replacement`.</span><span class="sxs-lookup"><span data-stu-id="ee4cf-123">If the `regular expression flag` argument is **FALSE**, this function returns the specified string after the set of characters that are defined in the `pattern` argument have been replaced by characters of the `replacement` argument.</span></span> 

## <a name="example-1"></a><span data-ttu-id="ee4cf-124">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="ee4cf-124">Example 1</span></span>

<span data-ttu-id="ee4cf-125">`REPLACE ("+1 923 456 4971", "[^0-9]", "", true)` aplica una expresión regular que quita todos los símbolos no numéricos y devuelve **"19234564971"**.</span><span class="sxs-lookup"><span data-stu-id="ee4cf-125">`REPLACE ("+1 923 456 4971", "[^0-9]", "", true)` applies a regular expression that removes all non-numeric symbols, and it returns **"19234564971"**.</span></span> 

## <a name="example-2"></a><span data-ttu-id="ee4cf-126">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="ee4cf-126">Example 2</span></span>

<span data-ttu-id="ee4cf-127">`REPLACE ("abcdef", "cd", "GH", false)` reemplaza el patrón **"cd"** por la cadena **"GH"** y devuelve **"abGHef"**.</span><span class="sxs-lookup"><span data-stu-id="ee4cf-127">`REPLACE ("abcdef", "cd", "GH", false)` replaces the pattern **"cd"** with the string **"GH"** and returns **"abGHef"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ee4cf-128">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="ee4cf-128">Additional resources</span></span>

[<span data-ttu-id="ee4cf-129">Funciones de texto</span><span class="sxs-lookup"><span data-stu-id="ee4cf-129">Text functions</span></span>](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]