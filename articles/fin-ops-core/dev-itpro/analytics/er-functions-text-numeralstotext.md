---
title: Función NUMERALSTOTEXT de ER
description: Este tema proporciona información general sobre cómo usar la función NUMERALSTOTEXT de informes electrónicos (ER).
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
ms.openlocfilehash: 459123a66dae7a3d87a22b042e1be6585959ac15
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/20/2019
ms.locfileid: "2915634"
---
# <span data-ttu-id="f3bc8-103"><a name="NUMERALSTOTEXT">Función NUMERALSTOTEXT de ER</a></span><span class="sxs-lookup"><span data-stu-id="f3bc8-103"><a name="NUMERALSTOTEXT">NUMERALSTOTEXT ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f3bc8-104">La función `NUMERALSTOTEXT` devuelve el número especificado como un valor de tipo *Cadena* después de que se haya deletreado (es decir, convertido a cadenas de texto) en el idioma especificado.</span><span class="sxs-lookup"><span data-stu-id="f3bc8-104">The `NUMERALSTOTEXT` function returns the specified number as a *String* value after it has been spelled out (that is, converted to text strings) in the specified language.</span></span>

## <a name="syntax"></a><span data-ttu-id="f3bc8-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f3bc8-105">Syntax</span></span>

```
NUMERALSTOTEXT (number, language, currency, print currency name flag, decimal points)
```

## <a name="arguments"></a><span data-ttu-id="f3bc8-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="f3bc8-106">Arguments</span></span>

<span data-ttu-id="f3bc8-107">`number`: *Entero* o *Real*</span><span class="sxs-lookup"><span data-stu-id="f3bc8-107">`number`: *Integer* or *Real*</span></span>

<span data-ttu-id="f3bc8-108">Valor numérico que especifica el número que se debe deletrear.</span><span class="sxs-lookup"><span data-stu-id="f3bc8-108">A numeric value that specifies the number that must be spelled out.</span></span>

<span data-ttu-id="f3bc8-109">`language`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="f3bc8-109">`language`: *String*</span></span>

<span data-ttu-id="f3bc8-110">Valor de tipo *Cadena* que representa el código de idioma.</span><span class="sxs-lookup"><span data-stu-id="f3bc8-110">A *String* value that represents the language code.</span></span>

<span data-ttu-id="f3bc8-111">`currency`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="f3bc8-111">`currency`: *String*</span></span>

<span data-ttu-id="f3bc8-112">Valor de tipo *Cadena* que representa el código de divisa.</span><span class="sxs-lookup"><span data-stu-id="f3bc8-112">A *String* value that represents the currency code.</span></span>

<span data-ttu-id="f3bc8-113">`print currency name flag`: *Booleano*</span><span class="sxs-lookup"><span data-stu-id="f3bc8-113">`print currency name flag`: *Boolean*</span></span>

<span data-ttu-id="f3bc8-114">Valor de tipo *Booleano* que indica si se debe agregar un nombre de divisa al texto deletreado.</span><span class="sxs-lookup"><span data-stu-id="f3bc8-114">A *Boolean* value that indicates whether a currency name must be added to the spelled-out text.</span></span>

<span data-ttu-id="f3bc8-115">`decimal points`: *Entero*</span><span class="sxs-lookup"><span data-stu-id="f3bc8-115">`decimal points`: *Integer*</span></span>

<span data-ttu-id="f3bc8-116">Valor de tipo *Entero* que indica el número de decimales que debe tener el texto deletreado.</span><span class="sxs-lookup"><span data-stu-id="f3bc8-116">An *Integer* value that indicates the number of decimal places that the spelled-out text should have.</span></span>

## <a name="return-values"></a><span data-ttu-id="f3bc8-117">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="f3bc8-117">Return values</span></span>

<span data-ttu-id="f3bc8-118">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="f3bc8-118">*String*</span></span>

<span data-ttu-id="f3bc8-119">El valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="f3bc8-119">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="f3bc8-120">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="f3bc8-120">Usage notes</span></span>

<span data-ttu-id="f3bc8-121">El código de idioma es opcional.</span><span class="sxs-lookup"><span data-stu-id="f3bc8-121">The language code is optional.</span></span> <span data-ttu-id="f3bc8-122">Cuando se define como una cadena vacía, se utiliza el código de idioma para el contexto en ejecución.</span><span class="sxs-lookup"><span data-stu-id="f3bc8-122">If it's defined as an empty string, the language code for the running context is used.</span></span> <span data-ttu-id="f3bc8-123">El código de idioma predeterminado es **EN-US**.</span><span class="sxs-lookup"><span data-stu-id="f3bc8-123">The default language code is **EN-US**.</span></span> <span data-ttu-id="f3bc8-124">El código de idioma para el contexto en ejecución se define en un elemento **Carpeta** o **Archivo** del formato de informe electrónico (ER) que se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="f3bc8-124">The language code for the running context is defined in a **Folder** or **File** element of the Electronic reporting (ER) format that is running.</span></span>

<span data-ttu-id="f3bc8-125">El código de divisa es opcional.</span><span class="sxs-lookup"><span data-stu-id="f3bc8-125">The currency code is optional.</span></span> <span data-ttu-id="f3bc8-126">Cuando se define como una cadena vacía, se utiliza la divisa de empresa para el contexto en ejecución.</span><span class="sxs-lookup"><span data-stu-id="f3bc8-126">If it's defined as an empty string, the company currency for the running context is used.</span></span>

> [!NOTE] 
> <span data-ttu-id="f3bc8-127">Los argumentos `print currency name flag` y `decimal points` se analizan únicamente para los siguientes códigos de idioma: **CS**, **ET**, **HU**, **LT**, **LV**, **PL** y **RU**.</span><span class="sxs-lookup"><span data-stu-id="f3bc8-127">The `print currency name flag` and `decimal points` arguments are analyzed only for the following language codes: **CS**, **ET**, **HU**, **LT**, **LV**, **PL**, and **RU**.</span></span> <span data-ttu-id="f3bc8-128">Asimismo, el argumento `print currency name flag` solo se analiza para las empresas en las que el contexto del país o la región permite la declinación de nombres de divisa.</span><span class="sxs-lookup"><span data-stu-id="f3bc8-128">Additionally, the `print currency name flag` argument is analyzed only for companies where the country's or region's context supports declension of currency names.</span></span>

## <a name="example-1"></a><span data-ttu-id="f3bc8-129">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="f3bc8-129">Example 1</span></span>

<span data-ttu-id="f3bc8-130">`NUMERALSTOTEXT (1234.56, "EN-US", "", false, 2)` devuelve **"One Thousand Two Hundred Thirty Four and 56"**.</span><span class="sxs-lookup"><span data-stu-id="f3bc8-130">`NUMERALSTOTEXT (1234.56, "EN-US", "", false, 2)` returns **"One Thousand Two Hundred Thirty Four and 56"**.</span></span>

## <a name="example-2"></a><span data-ttu-id="f3bc8-131">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="f3bc8-131">Example 2</span></span>

<span data-ttu-id="f3bc8-132">`NUMERALSTOTEXT (120, "PL", "", false, 0)` devuelve **"Sto dwadzieścia"**.</span><span class="sxs-lookup"><span data-stu-id="f3bc8-132">`NUMERALSTOTEXT (120, "PL", "", false, 0)` returns **"Sto dwadzieścia"**.</span></span> 

## <a name="example-3"></a><span data-ttu-id="f3bc8-133">Ejemplo 3</span><span class="sxs-lookup"><span data-stu-id="f3bc8-133">Example 3</span></span>

<span data-ttu-id="f3bc8-134">`NUMERALSTOTEXT (120.21, "RU", "EUR", true, 2)` devuelve **"Сто двадцать евро 21 евроцент"**.</span><span class="sxs-lookup"><span data-stu-id="f3bc8-134">`NUMERALSTOTEXT (120.21, "RU", "EUR", true, 2)` returns **"Сто двадцать евро 21 евроцент"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f3bc8-135">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="f3bc8-135">Additional resources</span></span>

[<span data-ttu-id="f3bc8-136">Funciones de texto</span><span class="sxs-lookup"><span data-stu-id="f3bc8-136">Text functions</span></span>](er-functions-category-text.md)
