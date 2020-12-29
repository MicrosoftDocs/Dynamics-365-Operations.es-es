---
title: Lista de funciones ER en la categoría lógica.
description: Este tema proporciona información sobre las funciones lógicas que son compatibles con los informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 08/19/2020
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
ms.openlocfilehash: a37b3341b05fde1283a21a0c52faec26cd1a7030
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686203"
---
# <a name="list-of-er-functions-in-the-logical-category"></a><span data-ttu-id="23686-103">Lista de funciones ER en la categoría lógica.</span><span class="sxs-lookup"><span data-stu-id="23686-103">List of ER functions in the logical category</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="23686-104">Las funciones lógicas de informes electrónicos (ER) se pueden utilizar para trabajar con valores lógicos para realizar más de una comparación en una sola expresión o probar múltiples condiciones.</span><span class="sxs-lookup"><span data-stu-id="23686-104">Electronic reporting (ER) logical functions can be used to work with logical values to perform more than one comparison in a single expression or test multiple conditions.</span></span> <span data-ttu-id="23686-105">Este tema proporciona un resumen de estas funciones.</span><span class="sxs-lookup"><span data-stu-id="23686-105">This topic provides a summary of these functions.</span></span>

## <a name="list-of-supported-functions"></a><span data-ttu-id="23686-106">Lista de funciones permitidas.</span><span class="sxs-lookup"><span data-stu-id="23686-106">List of supported functions</span></span>

| <span data-ttu-id="23686-107">Función</span><span class="sxs-lookup"><span data-stu-id="23686-107">Function</span></span> | <span data-ttu-id="23686-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="23686-108">Description</span></span> |
|----------|-------------|
| [<span data-ttu-id="23686-109">Y</span><span class="sxs-lookup"><span data-stu-id="23686-109">And</span></span>](er-functions-logical-and.md)                       | <span data-ttu-id="23686-110">Esta función devuelve un valor *Booleano* de **TRUE** si todas las condiciones especificadas son ciertas.</span><span class="sxs-lookup"><span data-stu-id="23686-110">This function returns a *Boolean* value of **TRUE** if all the specified conditions are true.</span></span> <span data-ttu-id="23686-111">De lo contrario, la expresión devuelve un valor *Booleano* de **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="23686-111">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span> |
| [<span data-ttu-id="23686-112">Caso</span><span class="sxs-lookup"><span data-stu-id="23686-112">Case</span></span>](er-functions-logical-case.md)                     | <span data-ttu-id="23686-113">Esta función evalúa el valor de la expresión especificada frente a las opciones alternativas especificadas y devuelve el resultado de la primera opción que es igual al valor de la expresión especificada.</span><span class="sxs-lookup"><span data-stu-id="23686-113">This function evaluates the value of the specified expression against the specified alternative options and returns the result of the first option that equals the value of the specified expression.</span></span> <span data-ttu-id="23686-114">De lo contrario, devuelve un resultado predeterminado opcional, si se especifica un resultado predeterminado como el último argumento de la función llamada que no está precedida por una opción.</span><span class="sxs-lookup"><span data-stu-id="23686-114">Otherwise, it returns an optional default result, if a default result is specified as the last argument of the called function that isn't preceded by an option.</span></span> <span data-ttu-id="23686-115">El valor que se devuelve puede ser un valor de cualquiera de los tipos de datos admitidos.</span><span class="sxs-lookup"><span data-stu-id="23686-115">The value that is returned can be a value of any of the supported data types.</span></span> |
| [<span data-ttu-id="23686-116">Si</span><span class="sxs-lookup"><span data-stu-id="23686-116">If</span></span>](er-functions-logical-if.md)                         | <span data-ttu-id="23686-117">Esta función devuelve el primer valor especificado si se cumple la condición especificada.</span><span class="sxs-lookup"><span data-stu-id="23686-117">This function returns the first specified value if the specified condition is met.</span></span> <span data-ttu-id="23686-118">De lo contrario, devuelve el segundo valor especificado.</span><span class="sxs-lookup"><span data-stu-id="23686-118">Otherwise, it returns the second specified value.</span></span> <span data-ttu-id="23686-119">El valor que se devuelve puede ser un valor de cualquiera de los tipos de datos admitidos.</span><span class="sxs-lookup"><span data-stu-id="23686-119">The value that is returned can be a value of any of the supported data types.</span></span> |
| [<span data-ttu-id="23686-120">No</span><span class="sxs-lookup"><span data-stu-id="23686-120">Not</span></span>](er-functions-logical-not.md)                       | <span data-ttu-id="23686-121">Esta función devuelve el valor lógico invertido de la condición especificada como un valor *Booleano*.</span><span class="sxs-lookup"><span data-stu-id="23686-121">This function returns the reversed logical value of the specified condition as a *Boolean* value.</span></span> |
| [<span data-ttu-id="23686-122">Or</span><span class="sxs-lookup"><span data-stu-id="23686-122">Or</span></span>](er-functions-logical-or.md)                         | <span data-ttu-id="23686-123">Esta función devuelve un valor *Booleano* de **FALSE** si todas las condiciones especificadas son falsas.</span><span class="sxs-lookup"><span data-stu-id="23686-123">This function returns a *Boolean* value of **FALSE** if all the specified conditions are false.</span></span> <span data-ttu-id="23686-124">Si cualquier condición especificada es cierta, esta función devuelve un valor *Booleano* de **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="23686-124">If any specified condition is true, the function returns a *Boolean* value of **TRUE**.</span></span> |
| [<span data-ttu-id="23686-125">ValueIn</span><span class="sxs-lookup"><span data-stu-id="23686-125">ValueIn</span></span>](er-functions-logical-valuein.md)               | <span data-ttu-id="23686-126">Esta función determina si la entrada especificada coincide con algún valor de un elemento específico de la lista especificada.</span><span class="sxs-lookup"><span data-stu-id="23686-126">This function determines whether the specified input matches any value of a specified item in the specified list.</span></span> <span data-ttu-id="23686-127">Devuelve un *Booleano* valor de **TRUE** si la entrada especificada coincide con el resultado de ejecutar la expresión especificada para al menos un registro de la lista especificada.</span><span class="sxs-lookup"><span data-stu-id="23686-127">It returns a *Boolean* value of **TRUE** if the specified input matches the result of running the specified expression for at least one record of the specified list.</span></span> <span data-ttu-id="23686-128">De lo contrario, la expresión devuelve un valor *Booleano* de **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="23686-128">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span> |
| [<span data-ttu-id="23686-129">ValueInLarge</span><span class="sxs-lookup"><span data-stu-id="23686-129">ValueInLarge</span></span>](er-functions-logical-valueinlarge.md)     | <span data-ttu-id="23686-130">Esta función determina si la entrada especificada del tipo *Int64* o *Entero* coincide con algún valor de un elemento específico de la lista especificada.</span><span class="sxs-lookup"><span data-stu-id="23686-130">This function determines whether the specified input of the *Int64* or *Integer* type matches any value of a specified item in the specified list.</span></span> <span data-ttu-id="23686-131">Devuelve un *Booleano* valor de **TRUE** si la entrada especificada coincide con el resultado de ejecutar la expresión especificada para al menos un registro de la lista especificada.</span><span class="sxs-lookup"><span data-stu-id="23686-131">It returns a *Boolean* value of **TRUE** if the specified input matches the result of running the specified expression for at least one record of the specified list.</span></span> <span data-ttu-id="23686-132">De lo contrario, la expresión devuelve un valor *Booleano* de **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="23686-132">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span> |


## <a name="additional-resources"></a><span data-ttu-id="23686-133">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="23686-133">Additional resources</span></span>

[<span data-ttu-id="23686-134">Visión general de los informes electrónicos</span><span class="sxs-lookup"><span data-stu-id="23686-134">Electronic Reporting overview</span></span>](general-electronic-reporting.md)

[<span data-ttu-id="23686-135">Diseñador de fórmulas en los informes electrónicos</span><span class="sxs-lookup"><span data-stu-id="23686-135">Formula designer in Electronic reporting</span></span>](general-electronic-reporting-formula-designer.md)

[<span data-ttu-id="23686-136">Idioma de fórmulas en los informes electrónicos</span><span class="sxs-lookup"><span data-stu-id="23686-136">Electronic reporting formula language</span></span>](er-formula-language.md)
