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
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 52a89f744cd37c543294522cc706ae7f47660e75
ms.sourcegitcommit: 3dede95a3b17de920bb0adcb33029f990682752b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/18/2020
ms.locfileid: "3070630"
---
# <span data-ttu-id="bec9a-103"><a name="SPLIT">Función SPLIT de ER</a></span><span class="sxs-lookup"><span data-stu-id="bec9a-103"><a name="SPLIT">SPLIT ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="bec9a-104">La función `SPLIT` divide la cadena de entrada especificada en subcadenas y devuelve el resultado como un valor *Lista de registros* nuevo.</span><span class="sxs-lookup"><span data-stu-id="bec9a-104">The `SPLIT` function splits the specified input string into substrings and returns the result as a new *Record list* value.</span></span>

## <a name="syntax-1"></a><span data-ttu-id="bec9a-105">Sintaxis 1</span><span class="sxs-lookup"><span data-stu-id="bec9a-105">Syntax 1</span></span>

```vb
SPLIT (input, length)
```

<span data-ttu-id="bec9a-106">La sintaxis se usa para dividir la cadena de entrada especificada en subcadenas y cada una de las cuales tiene la duración especificada.</span><span class="sxs-lookup"><span data-stu-id="bec9a-106">This syntax is used to split the specified input string into substrings, each of which has the specified length.</span></span>

## <a name="syntax-2"></a><span data-ttu-id="bec9a-107">Sintaxis 2</span><span class="sxs-lookup"><span data-stu-id="bec9a-107">Syntax 2</span></span>

```vb
SPLIT (input, delimiter)
```

<span data-ttu-id="bec9a-108">La sintaxis se usa para dividir la cadena de entrada especificada en subcadenas, basadas en el delimitador especificado.</span><span class="sxs-lookup"><span data-stu-id="bec9a-108">This syntax is used to split the specified input string into substrings, based on the specified delimiter.</span></span>

## <a name="arguments"></a><span data-ttu-id="bec9a-109">Argumentos</span><span class="sxs-lookup"><span data-stu-id="bec9a-109">Arguments</span></span>

<span data-ttu-id="bec9a-110">`input`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="bec9a-110">`input`: *String*</span></span>

<span data-ttu-id="bec9a-111">Texto a dividir.</span><span class="sxs-lookup"><span data-stu-id="bec9a-111">The text to split.</span></span>

<span data-ttu-id="bec9a-112">`length`: *Entero*</span><span class="sxs-lookup"><span data-stu-id="bec9a-112">`length`: *Integer*</span></span>

<span data-ttu-id="bec9a-113">La longitud máxima de una sola subcadena.</span><span class="sxs-lookup"><span data-stu-id="bec9a-113">The maximum length of a single substring.</span></span>

<span data-ttu-id="bec9a-114">`delimiter`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="bec9a-114">`delimiter`: *String*</span></span>

<span data-ttu-id="bec9a-115">Un delimitador que se utiliza para separar subcadenas.</span><span class="sxs-lookup"><span data-stu-id="bec9a-115">A delimiter that is used to separate substrings.</span></span>

## <a name="return-values"></a><span data-ttu-id="bec9a-116">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="bec9a-116">Return values</span></span>

<span data-ttu-id="bec9a-117">*Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="bec9a-117">*Record list*</span></span>

<span data-ttu-id="bec9a-118">La lista de registros resultante.</span><span class="sxs-lookup"><span data-stu-id="bec9a-118">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="bec9a-119">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="bec9a-119">Usage notes</span></span>

<span data-ttu-id="bec9a-120">La estructura de registro de la lista que se devuelve consta del campo **Valor** del tipo *Cadena*.</span><span class="sxs-lookup"><span data-stu-id="bec9a-120">The record structure of the list that is returned consists of the **Value** field of the *String* type.</span></span> <span data-ttu-id="bec9a-121">Cada registro de la lista que se devuelve contiene subcadenas generadas en este campo.</span><span class="sxs-lookup"><span data-stu-id="bec9a-121">Every record of the list that is returned contains generated substrings in this field.</span></span>

<span data-ttu-id="bec9a-122">Si el argumento `delimiter` está vacío, la nueva lista que se devuelve consiste en un registro que tiene un campo **Valor** del tipo *Cadena*.</span><span class="sxs-lookup"><span data-stu-id="bec9a-122">If the `delimiter` argument is empty, the new list that is returned consists of one record that has the **Value** field of the *String* type.</span></span> <span data-ttu-id="bec9a-123">Este campo contiene el texto de entrada.</span><span class="sxs-lookup"><span data-stu-id="bec9a-123">This field contains the input text.</span></span>

<span data-ttu-id="bec9a-124">Si el argumento `input` está vacío, se devuelve una nueva lista vacía.</span><span class="sxs-lookup"><span data-stu-id="bec9a-124">If the `input` argument is empty, a new empty list is returned.</span></span> <span data-ttu-id="bec9a-125">Si el argumento `input` o `delimiter` están sin especificar (null), se emite una excepción de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="bec9a-125">If either the `input` or `delimiter` argument is unspecified (null), an application exception is thrown.</span></span>

## <a name="example-1"></a><span data-ttu-id="bec9a-126">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="bec9a-126">Example 1</span></span>

<span data-ttu-id="bec9a-127">`SPLIT ("abcd", 3)` devuelve una nueva lista que consta de dos registros que tienen el campo **Valor** del tipo *Cadena*.</span><span class="sxs-lookup"><span data-stu-id="bec9a-127">`SPLIT ("abcd", 3)` returns a new list that consists of two records that have the **Value** field of the *String* type.</span></span> <span data-ttu-id="bec9a-128">El campo **Valor** del primer registro contiene el texto **“abc”** y el campo **Valor** del segundo registro contiene el texto **“d”**.</span><span class="sxs-lookup"><span data-stu-id="bec9a-128">The **Value** field in the first record contains the text **"abc"**, and the **Value** field in the second record contains the text **"d"**.</span></span>

## <a name="example-2"></a><span data-ttu-id="bec9a-129">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="bec9a-129">Example 2</span></span>

<span data-ttu-id="bec9a-130">`SPLIT ("XAb aBy", "aB")` devuelve una nueva lista que consta de tres registros que tienen el campo **Valor** del tipo *Cadena*.</span><span class="sxs-lookup"><span data-stu-id="bec9a-130">`SPLIT ("XAb aBy", "aB")` returns a new list that consists of three records that have the **Value** field of the *String* type.</span></span> <span data-ttu-id="bec9a-131">El campo **Valor** del primer registro contiene el texto **"X"**, el campo **Valor** del segundo registro contiene texto **"&nbsp;"**, y el campo **Valor** del tercer registro contiene el texto **"y"**.</span><span class="sxs-lookup"><span data-stu-id="bec9a-131">The **Value** field in the first record contains the text **"X"**, the **Value** field in the second record contains the text **"&nbsp;"**, and the **Value** field in the third record contains the text **"y"**.</span></span> 

## <a name="additional-resources"></a><span data-ttu-id="bec9a-132">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="bec9a-132">Additional resources</span></span>

[<span data-ttu-id="bec9a-133">Funciones de lista</span><span class="sxs-lookup"><span data-stu-id="bec9a-133">List functions</span></span>](er-functions-category-list.md)
