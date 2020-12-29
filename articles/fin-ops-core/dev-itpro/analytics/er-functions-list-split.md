---
title: Función SPLIT de ER
description: Este tema proporciona información general sobre cómo usar la función SPLIT de informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 12/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
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
ms.openlocfilehash: e1f11d68b697fdd363f429e60a79f1e1f97bab5b
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686401"
---
# <a name="split-er-function"></a><span data-ttu-id="d8834-103">Función SPLIT de ER</span><span class="sxs-lookup"><span data-stu-id="d8834-103">SPLIT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d8834-104">La función `SPLIT` divide la cadena de entrada especificada en subcadenas y devuelve el resultado como un valor *Lista de registros* nuevo.</span><span class="sxs-lookup"><span data-stu-id="d8834-104">The `SPLIT` function splits the specified input string into substrings and returns the result as a new *Record list* value.</span></span>

## <a name="syntax-1"></a><span data-ttu-id="d8834-105">Sintaxis 1</span><span class="sxs-lookup"><span data-stu-id="d8834-105">Syntax 1</span></span>

```vb
SPLIT (input, length)
```

<span data-ttu-id="d8834-106">La sintaxis se usa para dividir la cadena de entrada especificada en subcadenas y cada una de las cuales tiene la duración especificada.</span><span class="sxs-lookup"><span data-stu-id="d8834-106">This syntax is used to split the specified input string into substrings, each of which has the specified length.</span></span>

## <a name="syntax-2"></a><span data-ttu-id="d8834-107">Sintaxis 2</span><span class="sxs-lookup"><span data-stu-id="d8834-107">Syntax 2</span></span>

```vb
SPLIT (input, delimiter)
```

<span data-ttu-id="d8834-108">La sintaxis se usa para dividir la cadena de entrada especificada en subcadenas, basadas en el delimitador especificado.</span><span class="sxs-lookup"><span data-stu-id="d8834-108">This syntax is used to split the specified input string into substrings, based on the specified delimiter.</span></span>

## <a name="arguments"></a><span data-ttu-id="d8834-109">Argumentos</span><span class="sxs-lookup"><span data-stu-id="d8834-109">Arguments</span></span>

<span data-ttu-id="d8834-110">`input`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="d8834-110">`input`: *String*</span></span>

<span data-ttu-id="d8834-111">Texto a dividir.</span><span class="sxs-lookup"><span data-stu-id="d8834-111">The text to split.</span></span>

<span data-ttu-id="d8834-112">`length`: *Entero*</span><span class="sxs-lookup"><span data-stu-id="d8834-112">`length`: *Integer*</span></span>

<span data-ttu-id="d8834-113">La longitud máxima de una sola subcadena.</span><span class="sxs-lookup"><span data-stu-id="d8834-113">The maximum length of a single substring.</span></span>

<span data-ttu-id="d8834-114">`delimiter`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="d8834-114">`delimiter`: *String*</span></span>

<span data-ttu-id="d8834-115">Un delimitador que se utiliza para separar subcadenas.</span><span class="sxs-lookup"><span data-stu-id="d8834-115">A delimiter that is used to separate substrings.</span></span>

## <a name="return-values"></a><span data-ttu-id="d8834-116">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="d8834-116">Return values</span></span>

<span data-ttu-id="d8834-117">*Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="d8834-117">*Record list*</span></span>

<span data-ttu-id="d8834-118">La lista de registros resultante.</span><span class="sxs-lookup"><span data-stu-id="d8834-118">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="d8834-119">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="d8834-119">Usage notes</span></span>

<span data-ttu-id="d8834-120">La estructura de registro de la lista que se devuelve consta del campo **Valor** del tipo *Cadena*.</span><span class="sxs-lookup"><span data-stu-id="d8834-120">The record structure of the list that is returned consists of the **Value** field of the *String* type.</span></span> <span data-ttu-id="d8834-121">Cada registro de la lista que se devuelve contiene subcadenas generadas en este campo.</span><span class="sxs-lookup"><span data-stu-id="d8834-121">Every record of the list that is returned contains generated substrings in this field.</span></span>

<span data-ttu-id="d8834-122">Si el argumento `delimiter` está vacío, la nueva lista que se devuelve consiste en un registro que tiene un campo **Valor** del tipo *Cadena*.</span><span class="sxs-lookup"><span data-stu-id="d8834-122">If the `delimiter` argument is empty, the new list that is returned consists of one record that has the **Value** field of the *String* type.</span></span> <span data-ttu-id="d8834-123">Este campo contiene el texto de entrada.</span><span class="sxs-lookup"><span data-stu-id="d8834-123">This field contains the input text.</span></span>

<span data-ttu-id="d8834-124">Si el argumento `input` está vacío, se devuelve una nueva lista vacía.</span><span class="sxs-lookup"><span data-stu-id="d8834-124">If the `input` argument is empty, a new empty list is returned.</span></span> <span data-ttu-id="d8834-125">Si el argumento `input` o `delimiter` están sin especificar (null), se emite una excepción de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d8834-125">If either the `input` or `delimiter` argument is unspecified (null), an application exception is thrown.</span></span>

## <a name="example-1"></a><span data-ttu-id="d8834-126">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="d8834-126">Example 1</span></span>

<span data-ttu-id="d8834-127">`SPLIT ("abcd", 3)` devuelve una nueva lista que consta de dos registros que tienen el campo **Valor** del tipo *Cadena*.</span><span class="sxs-lookup"><span data-stu-id="d8834-127">`SPLIT ("abcd", 3)` returns a new list that consists of two records that have the **Value** field of the *String* type.</span></span> <span data-ttu-id="d8834-128">El campo **Valor** del primer registro contiene el texto **“abc”** y el campo **Valor** del segundo registro contiene el texto **“d”**.</span><span class="sxs-lookup"><span data-stu-id="d8834-128">The **Value** field in the first record contains the text **"abc"**, and the **Value** field in the second record contains the text **"d"**.</span></span>

## <a name="example-2"></a><span data-ttu-id="d8834-129">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="d8834-129">Example 2</span></span>

<span data-ttu-id="d8834-130">`SPLIT ("XAb aBy", "aB")` devuelve una nueva lista que consta de tres registros que tienen el campo **Valor** del tipo *Cadena*.</span><span class="sxs-lookup"><span data-stu-id="d8834-130">`SPLIT ("XAb aBy", "aB")` returns a new list that consists of three records that have the **Value** field of the *String* type.</span></span> <span data-ttu-id="d8834-131">El campo **Valor** del primer registro contiene el texto **"X"**, el campo **Valor** del segundo registro contiene texto **"&nbsp;"**, y el campo **Valor** del tercer registro contiene el texto **"y"**.</span><span class="sxs-lookup"><span data-stu-id="d8834-131">The **Value** field in the first record contains the text **"X"**, the **Value** field in the second record contains the text **"&nbsp;"**, and the **Value** field in the third record contains the text **"y"**.</span></span> 

## <a name="additional-resources"></a><span data-ttu-id="d8834-132">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="d8834-132">Additional resources</span></span>

[<span data-ttu-id="d8834-133">Funciones de lista</span><span class="sxs-lookup"><span data-stu-id="d8834-133">List functions</span></span>](er-functions-category-list.md)
