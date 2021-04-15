---
title: Función TRANSLATE de ER
description: Este tema proporciona información general sobre cómo usar la función TRANSLATE de informes electrónicos (ER).
author: NickSelin
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
ms.openlocfilehash: 7e4d6417757e27190ab7cabf2bf01243bb87b55c
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746082"
---
# <a name="translate-er-function"></a><span data-ttu-id="9eb71-103">Función TRANSLATE de ER</span><span class="sxs-lookup"><span data-stu-id="9eb71-103">TRANSLATE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9eb71-104">La función `TRANSLATE` devuelve un valor *Cadena* que contiene el resultado del reemplazo de caracteres del texto especificado en caracteres de otro conjunto proporcionado.</span><span class="sxs-lookup"><span data-stu-id="9eb71-104">The `TRANSLATE` function returns a *String* value that contains the result of the character replacement of specified text in characters of another provided set.</span></span>

## <a name="syntax"></a><span data-ttu-id="9eb71-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9eb71-105">Syntax</span></span>

```vb
TRANSLATE (text , pattern, replacement)
```

## <a name="arguments"></a><span data-ttu-id="9eb71-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="9eb71-106">Arguments</span></span>

<span data-ttu-id="9eb71-107">`text`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="9eb71-107">`text`: *String*</span></span>

<span data-ttu-id="9eb71-108">La ruta válida de un origen de datos de tipo *Cadena*.</span><span class="sxs-lookup"><span data-stu-id="9eb71-108">The valid path of a data source of the *String* type.</span></span>

<span data-ttu-id="9eb71-109">`pattern`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="9eb71-109">`pattern`: *String*</span></span>

<span data-ttu-id="9eb71-110">El texto que se va a reemplazar.</span><span class="sxs-lookup"><span data-stu-id="9eb71-110">The text that must be replaced.</span></span>

<span data-ttu-id="9eb71-111">`replacement`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="9eb71-111">`replacement`: *String*</span></span>

<span data-ttu-id="9eb71-112">El texto que se va a usar como reemplazo.</span><span class="sxs-lookup"><span data-stu-id="9eb71-112">The text to use as a replacement.</span></span>

## <a name="return-values"></a><span data-ttu-id="9eb71-113">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="9eb71-113">Return values</span></span>

<span data-ttu-id="9eb71-114">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="9eb71-114">*String*</span></span>

<span data-ttu-id="9eb71-115">El valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="9eb71-115">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="9eb71-116">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="9eb71-116">Usage notes</span></span>

<span data-ttu-id="9eb71-117">La función `TRANSLATE` reemplaza un carácter a la vez.</span><span class="sxs-lookup"><span data-stu-id="9eb71-117">The `TRANSLATE` function replaces one character at a time.</span></span> <span data-ttu-id="9eb71-118">La función reemplaza el primer carácter del argumento `text` con el primer personaje del argumento `pattern` y luego el segundo carácter y sigue el mismo flujo hasta que termine.</span><span class="sxs-lookup"><span data-stu-id="9eb71-118">The function replaces the first character of the `text` argument with the first character of the `pattern` argument and then the second character and follows the same flow until finished.</span></span> <span data-ttu-id="9eb71-119">Cuando un carácter de los argumentos `text` y `pattern` coincide, se reemplaza por un carácter del argumento `replacement` que se encuentra en la misma posición que el personaje del argumento `pattern`.</span><span class="sxs-lookup"><span data-stu-id="9eb71-119">When a character from the `text` and `pattern` arguments match, it is replaced by a character from the `replacement` argument that is located in the same position as the character from the `pattern` argument.</span></span> <span data-ttu-id="9eb71-120">Si un personaje aparece varias veces en el argumento `pattern`, el argumento `replacement` asignará el que corresponde a la primera aparición de este carácter.</span><span class="sxs-lookup"><span data-stu-id="9eb71-120">If a character appears multiple times in the `pattern` argument, the `replacement` argument mapping that corresponds to the first occurrence of this character is used.</span></span>

## <a name="example-1"></a><span data-ttu-id="9eb71-121">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="9eb71-121">Example 1</span></span>

<span data-ttu-id="9eb71-122">`TRANSLATE ("abcdef", "cd", "GH")` reemplaza el carácter **"c"** del texto especificado **"abcedef"** con el carácter **"G"** del texto `replacement` debido a lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9eb71-122">`TRANSLATE ("abcdef", "cd", "GH")` replaces the **"c"** character of the specified  **“abcdef”** text with the **"G"** character of the `replacement` text due to the following:</span></span>
-   <span data-ttu-id="9eb71-123">El carácter **"c"** está presente en el texto `pattern` en la primera posición.</span><span class="sxs-lookup"><span data-stu-id="9eb71-123">The **"c"** character is presented in the `pattern` text in the first position.</span></span>
-   <span data-ttu-id="9eb71-124">La primera posición del texto `replacement` contiene el carácter **"G"**.</span><span class="sxs-lookup"><span data-stu-id="9eb71-124">The first position of the `replacement` text contains the **"G"** character.</span></span>

## <a name="example-2"></a><span data-ttu-id="9eb71-125">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="9eb71-125">Example 2</span></span>

<span data-ttu-id="9eb71-126">`TRANSLATE ("abcdef", "ccd", "GH")` devuelve **"abGdef"**.</span><span class="sxs-lookup"><span data-stu-id="9eb71-126">`TRANSLATE ("abcdef", "ccd", "GH")` returns **"abGdef"**.</span></span>

## <a name="example-3"></a><span data-ttu-id="9eb71-127">Ejemplo 3</span><span class="sxs-lookup"><span data-stu-id="9eb71-127">Example 3</span></span>

<span data-ttu-id="9eb71-128">`TRANSLATE ("abccba", "abc", "123")` devuelve **"123321"**.</span><span class="sxs-lookup"><span data-stu-id="9eb71-128">`TRANSLATE ("abccba", "abc", "123")` returns **"123321"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9eb71-129">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="9eb71-129">Additional resources</span></span>

[<span data-ttu-id="9eb71-130">Funciones de texto</span><span class="sxs-lookup"><span data-stu-id="9eb71-130">Text functions</span></span>](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]