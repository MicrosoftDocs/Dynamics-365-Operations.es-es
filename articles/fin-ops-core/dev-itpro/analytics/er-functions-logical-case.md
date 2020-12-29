---
title: Función CASE de ER
description: Este tema proporciona información general sobre cómo usar la función CASE de informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: 69b76a06bcd3ba002d9543447e60afa14d5a6ce6
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "4687035"
---
# <a name="case-er-function"></a><span data-ttu-id="c91cb-103">Función CASE de ER</span><span class="sxs-lookup"><span data-stu-id="c91cb-103">CASE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c91cb-104">La función `CASE` evalúa el valor de la expresión especificada frente a las opciones alternativas especificadas y devuelve el resultado de la primera opción que es igual al valor de la expresión especificada.</span><span class="sxs-lookup"><span data-stu-id="c91cb-104">The `CASE` function evaluates the value of the specified expression against the specified alternative options and returns the result of the first option that equals the value of the specified expression.</span></span> <span data-ttu-id="c91cb-105">De lo contrario, devuelve el resultado predeterminado opcional, si se especifica un resultado predeterminado como el último argumento de la función llamada que no está precedida por una opción.</span><span class="sxs-lookup"><span data-stu-id="c91cb-105">Otherwise, it returns the optional default result, if a default result is specified as the last argument of the called function that isn't preceded by an option.</span></span> <span data-ttu-id="c91cb-106">El valor que se devuelve puede ser un valor de cualquiera de los tipos de datos admitidos.</span><span class="sxs-lookup"><span data-stu-id="c91cb-106">The value that is returned can be a value of any of the supported data types.</span></span>

## <a name="syntax"></a><span data-ttu-id="c91cb-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c91cb-107">Syntax</span></span>

```vb
CASE (expression, option 1, result 1[, option 2, result 2, …, option N, result N, default result])
```

## <a name="arguments"></a><span data-ttu-id="c91cb-108">Argumentos</span><span class="sxs-lookup"><span data-stu-id="c91cb-108">Arguments</span></span>

<span data-ttu-id="c91cb-109">`expression`: *Tipo de datos primitivo* (Booleano, numérico o texto)</span><span class="sxs-lookup"><span data-stu-id="c91cb-109">`expression`: *Primitive data type* (Boolean, numeric, or text)</span></span>

<span data-ttu-id="c91cb-110">Una expresión válida que devuelve un valor del tipo de datos primitivo.</span><span class="sxs-lookup"><span data-stu-id="c91cb-110">A valid expression that returns a value of the primitive data type.</span></span>

<span data-ttu-id="c91cb-111">`option 1`: *Tipo de datos primitivo* (Booleano, numérico o texto)</span><span class="sxs-lookup"><span data-stu-id="c91cb-111">`option 1`: *Primitive data type* (Boolean, numeric, or text)</span></span>

<span data-ttu-id="c91cb-112">Una expresión válida que devuelve un valor del mismo tipo de datos primitivos que el argumento `expression` de la función llamada.</span><span class="sxs-lookup"><span data-stu-id="c91cb-112">A valid expression that returns a value of the same primitive data type as the `expression` argument of the called function.</span></span> <span data-ttu-id="c91cb-113">Este argumento es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="c91cb-113">This argument is required.</span></span>

<span data-ttu-id="c91cb-114">`result 1`: *Cualquiera de los tipos de datos admitidos*</span><span class="sxs-lookup"><span data-stu-id="c91cb-114">`result 1`: *Any of the supported data types*</span></span>

<span data-ttu-id="c91cb-115">El resultado devuelto que corresponde con la opción anterior.</span><span class="sxs-lookup"><span data-stu-id="c91cb-115">The returned result that corresponds to the preceding option.</span></span> <span data-ttu-id="c91cb-116">Este argumento es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="c91cb-116">This argument is required.</span></span>

<span data-ttu-id="c91cb-117">`option N`: *Tipo de datos primitivo* (Booleano, numérico o texto)</span><span class="sxs-lookup"><span data-stu-id="c91cb-117">`option N`: *Primitive data type* (Boolean, numeric, or text)</span></span>

<span data-ttu-id="c91cb-118">Una expresión válida que devuelve un valor del mismo tipo de datos primitivos que el argumento `expression` de la función llamada.</span><span class="sxs-lookup"><span data-stu-id="c91cb-118">A valid expression that returns a value of the same primitive data type as the `expression` argument of the called function.</span></span> <span data-ttu-id="c91cb-119">Este argumento es opcional.</span><span class="sxs-lookup"><span data-stu-id="c91cb-119">This argument is optional.</span></span>

<span data-ttu-id="c91cb-120">`result N`: *Cualquiera de los tipos de datos admitidos*</span><span class="sxs-lookup"><span data-stu-id="c91cb-120">`result N`: *Any of the supported data types*</span></span>

<span data-ttu-id="c91cb-121">El resultado devuelto que corresponde con la opción anterior.</span><span class="sxs-lookup"><span data-stu-id="c91cb-121">The returned result that corresponds to the preceding option.</span></span> <span data-ttu-id="c91cb-122">Este argumento es opcional.</span><span class="sxs-lookup"><span data-stu-id="c91cb-122">This argument is optional.</span></span>

<span data-ttu-id="c91cb-123">`default result`: *Cualquiera de los tipos de datos admitidos*</span><span class="sxs-lookup"><span data-stu-id="c91cb-123">`default result`: *Any of the supported data types*</span></span>

<span data-ttu-id="c91cb-124">El resultado que debe devolverse si no hay coincidencia.</span><span class="sxs-lookup"><span data-stu-id="c91cb-124">The result that should be returned if there is no match.</span></span> <span data-ttu-id="c91cb-125">Este argumento es opcional.</span><span class="sxs-lookup"><span data-stu-id="c91cb-125">This argument is optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="c91cb-126">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="c91cb-126">Return values</span></span>

<span data-ttu-id="c91cb-127">*Cualquiera de los tipos de datos admitidos*</span><span class="sxs-lookup"><span data-stu-id="c91cb-127">*Any of the supported data types*</span></span>

<span data-ttu-id="c91cb-128">El valor resultante de cualquiera de los tipos de datos admitidos.</span><span class="sxs-lookup"><span data-stu-id="c91cb-128">The resulting value of any of the supported data types.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="c91cb-129">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="c91cb-129">Usage notes</span></span>

<span data-ttu-id="c91cb-130">Se lanza una excepción en tiempo de ejecución si no hay coincidencia y no se define un resultado predeterminado opcional.</span><span class="sxs-lookup"><span data-stu-id="c91cb-130">An exception is thrown at runtime if there is no match and an optional default result isn't defined.</span></span>

<span data-ttu-id="c91cb-131">Todos los resultados deben especificarse utilizando el mismo tipo de datos.</span><span class="sxs-lookup"><span data-stu-id="c91cb-131">All results must be specified by using the same data type.</span></span> <span data-ttu-id="c91cb-132">Se produce una excepción en tiempo de diseño si los tipos de datos de los resultados configurados no coinciden.</span><span class="sxs-lookup"><span data-stu-id="c91cb-132">An exception is thrown at design time if the data types of the configured results don't match.</span></span>

<span data-ttu-id="c91cb-133">Si el primer valor del resultado y el resultado número *N* son valores del tipo de datos *Contenedor (registro)* o *Lista de registros*, el resultado solo tiene los campos que existen en ambos valores.</span><span class="sxs-lookup"><span data-stu-id="c91cb-133">If the first result value and the *N* th result value are values of the *Container (record)* or *Record list* data type, the result has only the fields that exist in both values.</span></span>

## <a name="example"></a><span data-ttu-id="c91cb-134">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c91cb-134">Example</span></span>

<span data-ttu-id="c91cb-135">`CASE( DATETIMEFORMAT( NOW(), "MM"), "10", "WINTER", "11", "WINTER", "12", "WINTER", "")` devuelve la cadena **"INVIERNO"** si la fecha de la sesión de solicitud actual es entre octubre y diciembre.</span><span class="sxs-lookup"><span data-stu-id="c91cb-135">`CASE( DATETIMEFORMAT( NOW(), "MM"), "10", "WINTER", "11", "WINTER", "12", "WINTER", "")` returns the string **"WINTER"** if the current application session date is between October and December.</span></span> <span data-ttu-id="c91cb-136">En caso contrario, devuelve una cadena en blanco.</span><span class="sxs-lookup"><span data-stu-id="c91cb-136">Otherwise, it returns a blank string.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c91cb-137">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="c91cb-137">Additional resources</span></span>

[<span data-ttu-id="c91cb-138">Funciones lógicas</span><span class="sxs-lookup"><span data-stu-id="c91cb-138">Logical functions</span></span>](er-functions-category-logical.md)
