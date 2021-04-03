---
title: Función NUMERALSTOTEXT de ER
description: Este tema proporciona información general sobre cómo usar la función NUMERALSTOTEXT de informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 12/10/2019
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
ms.openlocfilehash: 0dfb36e21259eada97b158cb38b22ae19e0afa07
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "5562766"
---
# <a name="numeralstotext-er-function"></a><span data-ttu-id="901db-103">Función NUMERALSTOTEXT de ER</span><span class="sxs-lookup"><span data-stu-id="901db-103">NUMERALSTOTEXT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="901db-104">La función `NUMERALSTOTEXT` devuelve el número especificado como un valor de tipo *Cadena* después de que se haya deletreado (es decir, convertido a cadenas de texto) en el idioma especificado.</span><span class="sxs-lookup"><span data-stu-id="901db-104">The `NUMERALSTOTEXT` function returns the specified number as a *String* value after it has been spelled out (that is, converted to text strings) in the specified language.</span></span>

## <a name="syntax"></a><span data-ttu-id="901db-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="901db-105">Syntax</span></span>

```vb
NUMERALSTOTEXT (number, language, currency, print currency name flag, decimal points)
```

## <a name="arguments"></a><span data-ttu-id="901db-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="901db-106">Arguments</span></span>

<span data-ttu-id="901db-107">`number`: *Entero* o *Real*</span><span class="sxs-lookup"><span data-stu-id="901db-107">`number`: *Integer* or *Real*</span></span>

<span data-ttu-id="901db-108">Valor numérico que especifica el número que se debe deletrear.</span><span class="sxs-lookup"><span data-stu-id="901db-108">A numeric value that specifies the number that must be spelled out.</span></span>

<span data-ttu-id="901db-109">`language`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="901db-109">`language`: *String*</span></span>

<span data-ttu-id="901db-110">Valor de tipo *Cadena* que representa el código de idioma.</span><span class="sxs-lookup"><span data-stu-id="901db-110">A *String* value that represents the language code.</span></span>

<span data-ttu-id="901db-111">`currency`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="901db-111">`currency`: *String*</span></span>

<span data-ttu-id="901db-112">Valor de tipo *Cadena* que representa el código de divisa.</span><span class="sxs-lookup"><span data-stu-id="901db-112">A *String* value that represents the currency code.</span></span>

<span data-ttu-id="901db-113">`print currency name flag`: *Booleano*</span><span class="sxs-lookup"><span data-stu-id="901db-113">`print currency name flag`: *Boolean*</span></span>

<span data-ttu-id="901db-114">Valor de tipo *Booleano* que indica si se debe agregar un nombre de divisa al texto deletreado.</span><span class="sxs-lookup"><span data-stu-id="901db-114">A *Boolean* value that indicates whether a currency name must be added to the spelled-out text.</span></span>

<span data-ttu-id="901db-115">`decimal points`: *Entero*</span><span class="sxs-lookup"><span data-stu-id="901db-115">`decimal points`: *Integer*</span></span>

<span data-ttu-id="901db-116">Valor de tipo *Entero* que indica el número de decimales que debe tener el texto deletreado.</span><span class="sxs-lookup"><span data-stu-id="901db-116">An *Integer* value that indicates the number of decimal places that the spelled-out text should have.</span></span>

## <a name="return-values"></a><span data-ttu-id="901db-117">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="901db-117">Return values</span></span>

<span data-ttu-id="901db-118">*Cadena*</span><span class="sxs-lookup"><span data-stu-id="901db-118">*String*</span></span>

<span data-ttu-id="901db-119">El valor de texto resultante.</span><span class="sxs-lookup"><span data-stu-id="901db-119">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="901db-120">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="901db-120">Usage notes</span></span>

<span data-ttu-id="901db-121">El código de idioma es opcional.</span><span class="sxs-lookup"><span data-stu-id="901db-121">The language code is optional.</span></span> <span data-ttu-id="901db-122">Cuando se define como una cadena vacía, se utiliza el código de idioma para el contexto en ejecución.</span><span class="sxs-lookup"><span data-stu-id="901db-122">If it's defined as an empty string, the language code for the running context is used.</span></span> <span data-ttu-id="901db-123">El código de idioma predeterminado es **EN-US**.</span><span class="sxs-lookup"><span data-stu-id="901db-123">The default language code is **EN-US**.</span></span> <span data-ttu-id="901db-124">El código de idioma para el contexto en ejecución se define en un elemento **Carpeta** o **Archivo** del formato de informe electrónico (ER) que se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="901db-124">The language code for the running context is defined in a **Folder** or **File** element of the Electronic reporting (ER) format that is running.</span></span>

<span data-ttu-id="901db-125">El código de divisa es opcional.</span><span class="sxs-lookup"><span data-stu-id="901db-125">The currency code is optional.</span></span> <span data-ttu-id="901db-126">Cuando se define como una cadena vacía, se utiliza la divisa de empresa para el contexto en ejecución.</span><span class="sxs-lookup"><span data-stu-id="901db-126">If it's defined as an empty string, the company currency for the running context is used.</span></span>

> [!NOTE] 
> <span data-ttu-id="901db-127">Los argumentos `print currency name flag` y `decimal points` se analizan únicamente para los siguientes códigos de idioma: **CS**, **ET**, **HU**, **LT**, **LV**, **PL** y **RU**.</span><span class="sxs-lookup"><span data-stu-id="901db-127">The `print currency name flag` and `decimal points` arguments are analyzed only for the following language codes: **CS**, **ET**, **HU**, **LT**, **LV**, **PL**, and **RU**.</span></span> <span data-ttu-id="901db-128">Asimismo, el argumento `print currency name flag` solo se analiza para las empresas en las que el contexto del país o la región permite la declinación de nombres de divisa.</span><span class="sxs-lookup"><span data-stu-id="901db-128">Additionally, the `print currency name flag` argument is analyzed only for companies where the country's or region's context supports declension of currency names.</span></span>

## <a name="example-1"></a><span data-ttu-id="901db-129">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="901db-129">Example 1</span></span>

<span data-ttu-id="901db-130">`NUMERALSTOTEXT (1234.56, "EN-US", "", false, 2)` devuelve **"One Thousand Two Hundred Thirty Four and 56"**.</span><span class="sxs-lookup"><span data-stu-id="901db-130">`NUMERALSTOTEXT (1234.56, "EN-US", "", false, 2)` returns **"One Thousand Two Hundred Thirty Four and 56"**.</span></span>

## <a name="example-2"></a><span data-ttu-id="901db-131">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="901db-131">Example 2</span></span>

<span data-ttu-id="901db-132">`NUMERALSTOTEXT (120, "PL", "", false, 0)` devuelve **"Sto dwadzieścia"**.</span><span class="sxs-lookup"><span data-stu-id="901db-132">`NUMERALSTOTEXT (120, "PL", "", false, 0)` returns **"Sto dwadzieścia"**.</span></span> 

## <a name="example-3"></a><span data-ttu-id="901db-133">Ejemplo 3</span><span class="sxs-lookup"><span data-stu-id="901db-133">Example 3</span></span>

<span data-ttu-id="901db-134">`NUMERALSTOTEXT (120.21, "RU", "EUR", true, 2)` devuelve **"Сто двадцать евро 21 евроцент"**.</span><span class="sxs-lookup"><span data-stu-id="901db-134">`NUMERALSTOTEXT (120.21, "RU", "EUR", true, 2)` returns **"Сто двадцать евро 21 евроцент"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="901db-135">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="901db-135">Additional resources</span></span>

[<span data-ttu-id="901db-136">Funciones de texto</span><span class="sxs-lookup"><span data-stu-id="901db-136">Text functions</span></span>](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]