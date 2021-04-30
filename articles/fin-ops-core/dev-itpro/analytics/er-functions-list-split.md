---
title: Función SPLIT de ER
description: Este tema proporciona información general sobre cómo usar la función SPLIT de informes electrónicos (ER).
author: NickSelin
ms.date: 04/01/2021
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
ms.openlocfilehash: 26b6ddeb2880fc220283b6389327a497549a4511
ms.sourcegitcommit: 74f5b04b482b2ae023c728e0df0eb78305493c6a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2021
ms.locfileid: "5853452"
---
# <a name="split-er-function"></a><span data-ttu-id="34c95-103">Función SPLIT de ER</span><span class="sxs-lookup"><span data-stu-id="34c95-103">SPLIT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="34c95-104">La función `SPLIT` divide la cadena de entrada especificada en subcadenas y devuelve el resultado como un valor *Lista de registros* nuevo.</span><span class="sxs-lookup"><span data-stu-id="34c95-104">The `SPLIT` function splits the specified input string into substrings and returns the result as a new *Record list* value.</span></span>

## <a name="syntax-1"></a><span data-ttu-id="34c95-105">Sintaxis 1</span><span class="sxs-lookup"><span data-stu-id="34c95-105">Syntax 1</span></span>

```vb
SPLIT (input, length)
```

<span data-ttu-id="34c95-106">La sintaxis se usa para dividir la cadena de entrada especificada en subcadenas y cada una de las cuales tiene la duración especificada.</span><span class="sxs-lookup"><span data-stu-id="34c95-106">This syntax is used to split the specified input string into substrings, each of which has the specified length.</span></span>

## <a name="syntax-2"></a><span data-ttu-id="34c95-107">Sintaxis 2</span><span class="sxs-lookup"><span data-stu-id="34c95-107">Syntax 2</span></span>

```vb
SPLIT (input, delimiter)
```

<span data-ttu-id="34c95-108">La sintaxis se usa para dividir la cadena de entrada especificada en subcadenas, basadas en el delimitador especificado.</span><span class="sxs-lookup"><span data-stu-id="34c95-108">This syntax is used to split the specified input string into substrings, based on the specified delimiter.</span></span>

## <a name="arguments"></a><span data-ttu-id="34c95-109">Argumentos</span><span class="sxs-lookup"><span data-stu-id="34c95-109">Arguments</span></span>

<span data-ttu-id="34c95-110">`input`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="34c95-110">`input`: *String*</span></span>

<span data-ttu-id="34c95-111">Texto a dividir.</span><span class="sxs-lookup"><span data-stu-id="34c95-111">The text to split.</span></span>

<span data-ttu-id="34c95-112">`length`: *Entero*</span><span class="sxs-lookup"><span data-stu-id="34c95-112">`length`: *Integer*</span></span>

<span data-ttu-id="34c95-113">La longitud máxima de una sola subcadena.</span><span class="sxs-lookup"><span data-stu-id="34c95-113">The maximum length of a single substring.</span></span>

<span data-ttu-id="34c95-114">`delimiter`: *Cadena*</span><span class="sxs-lookup"><span data-stu-id="34c95-114">`delimiter`: *String*</span></span>

<span data-ttu-id="34c95-115">Un delimitador que se utiliza para separar subcadenas.</span><span class="sxs-lookup"><span data-stu-id="34c95-115">A delimiter that is used to separate substrings.</span></span>

## <a name="return-values"></a><span data-ttu-id="34c95-116">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="34c95-116">Return values</span></span>

<span data-ttu-id="34c95-117">*Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="34c95-117">*Record list*</span></span>

<span data-ttu-id="34c95-118">La lista de registros resultante.</span><span class="sxs-lookup"><span data-stu-id="34c95-118">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="34c95-119">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="34c95-119">Usage notes</span></span>

<span data-ttu-id="34c95-120">La estructura de registro de la lista que se devuelve consta del campo **Valor** del tipo *Cadena*.</span><span class="sxs-lookup"><span data-stu-id="34c95-120">The record structure of the list that is returned consists of the **Value** field of the *String* type.</span></span> <span data-ttu-id="34c95-121">Cada registro de la lista que se devuelve contiene subcadenas generadas en este campo.</span><span class="sxs-lookup"><span data-stu-id="34c95-121">Every record of the list that is returned contains generated substrings in this field.</span></span>

<span data-ttu-id="34c95-122">Si el argumento `delimiter` está vacío, la nueva lista que se devuelve consiste en un registro que tiene un campo **Valor** del tipo *Cadena*.</span><span class="sxs-lookup"><span data-stu-id="34c95-122">If the `delimiter` argument is empty, the new list that is returned consists of one record that has the **Value** field of the *String* type.</span></span> <span data-ttu-id="34c95-123">Este campo contiene el texto de entrada.</span><span class="sxs-lookup"><span data-stu-id="34c95-123">This field contains the input text.</span></span>

<span data-ttu-id="34c95-124">Si el argumento `input` está vacío, se devuelve una nueva lista vacía.</span><span class="sxs-lookup"><span data-stu-id="34c95-124">If the `input` argument is empty, a new empty list is returned.</span></span> <span data-ttu-id="34c95-125">Si el argumento `input` o `delimiter` están sin especificar (null), se emite una excepción de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="34c95-125">If either the `input` or `delimiter` argument is unspecified (null), an application exception is thrown.</span></span>

## <a name="example-1"></a><span data-ttu-id="34c95-126">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="34c95-126">Example 1</span></span>

<span data-ttu-id="34c95-127">`SPLIT ("abcd", 3)` devuelve una nueva lista que consta de dos registros que tienen el campo **Valor** del tipo *Cadena*.</span><span class="sxs-lookup"><span data-stu-id="34c95-127">`SPLIT ("abcd", 3)` returns a new list that consists of two records that have the **Value** field of the *String* type.</span></span> <span data-ttu-id="34c95-128">El campo **Valor** del primer registro contiene el texto **“abc”** y el campo **Valor** del segundo registro contiene el texto **“d”**.</span><span class="sxs-lookup"><span data-stu-id="34c95-128">The **Value** field in the first record contains the text **"abc"**, and the **Value** field in the second record contains the text **"d"**.</span></span>

## <a name="example-2"></a><span data-ttu-id="34c95-129">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="34c95-129">Example 2</span></span>

<span data-ttu-id="34c95-130">`SPLIT ("XAb aBy", "aB")` devuelve una nueva lista que consta de tres registros que tienen el campo **Valor** del tipo *Cadena*.</span><span class="sxs-lookup"><span data-stu-id="34c95-130">`SPLIT ("XAb aBy", "aB")` returns a new list that consists of three records that have the **Value** field of the *String* type.</span></span> <span data-ttu-id="34c95-131">El campo **Valor** del primer registro contiene el texto **"X"**, el campo **Valor** del segundo registro contiene texto **"&nbsp;"**, y el campo **Valor** del tercer registro contiene el texto **"y"**.</span><span class="sxs-lookup"><span data-stu-id="34c95-131">The **Value** field in the first record contains the text **"X"**, the **Value** field in the second record contains the text **"&nbsp;"**, and the **Value** field in the third record contains the text **"y"**.</span></span> 

## <a name="example-3"></a><span data-ttu-id="34c95-132">Ejemplo 3</span><span class="sxs-lookup"><span data-stu-id="34c95-132">Example 3</span></span>

<span data-ttu-id="34c95-133">Puede usar la función [ÍNDICE](er-functions-list-index.md) para acceder a elementos individuales de la cadena de entrada especificada.</span><span class="sxs-lookup"><span data-stu-id="34c95-133">Yo can use the [INDEX](er-functions-list-index.md) function to access individual elements of the specified input string.</span></span> <span data-ttu-id="34c95-134">Si especifica el origen de datos **MyList** del tipo **Campo calculado** y configura para él la expresión `SPLIT("abc", 1)`, la expresión `INDEX(MyList,2).Value` devuelve el valor de texto **"b"**.</span><span class="sxs-lookup"><span data-stu-id="34c95-134">If you enter the **MyList** data source of the **Calculated field** type and configure for it the `SPLIT("abc", 1)` expression, the expression `INDEX(MyList,2).Value` returns the text **"b"**.</span></span>

## <a name="example-4"></a><span data-ttu-id="34c95-135">Ejemplo 4</span><span class="sxs-lookup"><span data-stu-id="34c95-135">Example 4</span></span>

<span data-ttu-id="34c95-136">La función [ENUMERATE](er-functions-list-enumerate.md) también puede ayudarle a acceder a elementos individuales de la cadena de entrada especificada.</span><span class="sxs-lookup"><span data-stu-id="34c95-136">The [ENUMERATE](er-functions-list-enumerate.md) function can also help you access individual elements of the specified input string.</span></span> <span data-ttu-id="34c95-137">Si primero ingresa la fuente de datos **MyList** del tipo **Campo calculado** y configura para ello la expresión `SPLIT("abc", 1)` y luego ingresa la fuente de datos **EnumeratedList** del **Campo calculado**, escriba y configure para ello la expresión `ENUMERATE(MyList)`, la expresión `FIRSTORNULL(WHERE(EnumeratedList, EnumeratedList.Number=2)).Value` devuelve el texto **"b"**.</span><span class="sxs-lookup"><span data-stu-id="34c95-137">If you first enter the **MyList** data source of the **Calculated field** type and configure for it the `SPLIT("abc", 1)` expression, and then enter the **EnumeratedList** data source of the **Calculated field** type and configure for it the `ENUMERATE(MyList)` expression, the expression `FIRSTORNULL(WHERE(EnumeratedList, EnumeratedList.Number=2)).Value` returns the text **"b"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="34c95-138">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="34c95-138">Additional resources</span></span>

[<span data-ttu-id="34c95-139">Funciones de lista</span><span class="sxs-lookup"><span data-stu-id="34c95-139">List functions</span></span>](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
