---
title: Función VALUEIN de ER
description: Este tema proporciona información general sobre cómo usar la función VALUEIN de informes electrónicos (ER).
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
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d0df97234df41d11897473dea4e85354e82d36ec
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041708"
---
# <span data-ttu-id="0b683-103"><a name="VALUEIN">Función VALUEIN de ER</a></span><span class="sxs-lookup"><span data-stu-id="0b683-103"><a name="VALUEIN">VALUEIN ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0b683-104">La función `VALUEIN` determina si la entrada especificada coincide con algún valor de un elemento específico de la lista especificada.</span><span class="sxs-lookup"><span data-stu-id="0b683-104">The `VALUEIN` function determines whether the specified input matches any value of a specified item in the specified list.</span></span> <span data-ttu-id="0b683-105">Devuelve un *Booleano* valor de **TRUE** si la entrada especificada coincide con el resultado de ejecutar la expresión especificada para al menos un registro de la lista especificada.</span><span class="sxs-lookup"><span data-stu-id="0b683-105">It returns a *Boolean* value of **TRUE** if the specified input matches the result of running the specified expression for at least one record of the specified list.</span></span> <span data-ttu-id="0b683-106">De lo contrario, la expresión devuelve un valor *Booleano* de **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="0b683-106">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span>

## <a name="syntax"></a><span data-ttu-id="0b683-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0b683-107">Syntax</span></span>

```vb
VALUEIN (input, list, list item expression)
```

## <a name="arguments"></a><span data-ttu-id="0b683-108">Argumentos</span><span class="sxs-lookup"><span data-stu-id="0b683-108">Arguments</span></span>

<span data-ttu-id="0b683-109">`input`: *Campo*</span><span class="sxs-lookup"><span data-stu-id="0b683-109">`input`: *Field*</span></span>

<span data-ttu-id="0b683-110">La ruta válida de un elemento de un origen de datos del tipo *Lista de registros*.</span><span class="sxs-lookup"><span data-stu-id="0b683-110">The valid path of an item of a data source of the *Record list* type.</span></span> <span data-ttu-id="0b683-111">El valor de este elemento se conciliará.</span><span class="sxs-lookup"><span data-stu-id="0b683-111">The value of this item will be matched.</span></span>

<span data-ttu-id="0b683-112">`list`: *Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="0b683-112">`list`: *Record list*</span></span>

<span data-ttu-id="0b683-113">La ruta válida de un origen de datos del tipo de datos *Lista de registros*.</span><span class="sxs-lookup"><span data-stu-id="0b683-113">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="0b683-114">`list item expression`: *Booleano*</span><span class="sxs-lookup"><span data-stu-id="0b683-114">`list item expression`: *Boolean*</span></span>

<span data-ttu-id="0b683-115">Un expresión condicional válida que señala o contiene un único campo de la lista especificada que se debe usar para la asignación.</span><span class="sxs-lookup"><span data-stu-id="0b683-115">A valid conditional expression that either points to or contains a single field of the specified list that should be used for the matching.</span></span>

## <a name="return-values"></a><span data-ttu-id="0b683-116">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="0b683-116">Return values</span></span>

<span data-ttu-id="0b683-117">*Booleano*</span><span class="sxs-lookup"><span data-stu-id="0b683-117">*Boolean*</span></span>

<span data-ttu-id="0b683-118">El valor *Booleano* resultante.</span><span class="sxs-lookup"><span data-stu-id="0b683-118">The resulting *Boolean* value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="0b683-119">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="0b683-119">Usage notes</span></span>

<span data-ttu-id="0b683-120">En general, la función `VALUEIN` se convierte a un conjunto de condiciones **OR**.</span><span class="sxs-lookup"><span data-stu-id="0b683-120">In general, the `VALUEIN` function is translated to a set of **OR** conditions.</span></span>

```vb
(input = list.item1.value) OR (input = list.item2.value) OR …
```

<span data-ttu-id="0b683-121">En algunos casos, se puede traducir a una instrucción de la base de datos SQL mediante el uso del operador `EXISTS JOIN`.</span><span class="sxs-lookup"><span data-stu-id="0b683-121">In some cases, it can be translated to a database SQL statement by using the `EXISTS JOIN` operator.</span></span>

## <a name="example-1"></a><span data-ttu-id="0b683-122">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="0b683-122">Example 1</span></span>

<span data-ttu-id="0b683-123">En su modelo de asignación, define el origen de datos **Lista** del tipo *Campo calculado*.</span><span class="sxs-lookup"><span data-stu-id="0b683-123">In your model mapping, you define the **List** data source of the *Calculated field* type.</span></span> <span data-ttu-id="0b683-124">Este origen de datos contiene la expresión `SPLIT ("a,b,c", ",")`.</span><span class="sxs-lookup"><span data-stu-id="0b683-124">This data source contains the expression `SPLIT ("a,b,c", ",")`.</span></span>

<span data-ttu-id="0b683-125">Cuando se llama a un origen de datos, si se ha configurado como la expresión `VALUEIN ("B", List, List.Value)`, devuelve **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="0b683-125">When a data source is called, if it has been configured as the `VALUEIN ("B", List, List.Value)` expression, it returns **TRUE**.</span></span> <span data-ttu-id="0b683-126">En este caso, la función `VALUEIN` se traduce al conjunto de condiciones siguiente: `(("B" = "a") or ("B" = "b") or ("B" = "c"))`, donde `("B" = "b")` es igual a **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="0b683-126">In this case, the `VALUEIN` function is translated to the following set of conditions: `(("B" = "a") or ("B" = "b") or ("B" = "c"))`, where `("B" = "b")` equals **TRUE**.</span></span>

<span data-ttu-id="0b683-127">Cuando se llama a un origen de datos, si se ha configurado como la expresión `VALUEIN ("B", List, LEFT(List.Value, 0))`, devuelve **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="0b683-127">When a data source is called, if it has been configured as the `VALUEIN ("B", List, LEFT(List.Value, 0))` expression, it returns **FALSE**.</span></span> <span data-ttu-id="0b683-128">En este caso, la función `VALUEIN` se traduce a la condición siguiente: `("B" = "")`, que no es igual a **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="0b683-128">In this case, the `VALUEIN` function is translated to the following condition: `("B" = "")`, which doesn't equal **TRUE**.</span></span>

<span data-ttu-id="0b683-129">El límite superior del número de caracteres en el texto de esta condición es 32 768 caracteres.</span><span class="sxs-lookup"><span data-stu-id="0b683-129">The upper limit for the number of characters in the text of such a condition is 32,768 characters.</span></span> <span data-ttu-id="0b683-130">Por lo tanto, no es necesario crear orígenes de datos que puedan superar este límite en el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="0b683-130">Therefore, you should not create data sources that might exceed this limit at runtime.</span></span> <span data-ttu-id="0b683-131">Si se supera el límite, la aplicación dejará de ejecutarse, y se generará una excepción.</span><span class="sxs-lookup"><span data-stu-id="0b683-131">If the limit is exceeded, the application stops running, and an exception is thrown.</span></span> <span data-ttu-id="0b683-132">Por ejemplo, esta situación puede producirse si el origen de datos se configura como `WHERE (List1, VALUEIN (List1.ID, List2, List2.ID)`, y las listas **List1** y **List2** contienen un gran número de registros.</span><span class="sxs-lookup"><span data-stu-id="0b683-132">For example, this situation can occur if the data source is configured as `WHERE (List1, VALUEIN (List1.ID, List2, List2.ID)`, and the **List1** and **List2** lists contain a large volume of records.</span></span>

<span data-ttu-id="0b683-133">En algunos casos, la función `VALUEIN` se convierte en una instrucción de una base de datos mediante el operador `EXISTS JOIN`.</span><span class="sxs-lookup"><span data-stu-id="0b683-133">In some cases, the `VALUEIN` function is translated to a database statement by using the `EXISTS JOIN` operator.</span></span> <span data-ttu-id="0b683-134">Este comportamiento aparece cuando se utiliza la función [FILTER](er-functions-list-filter.md) y se cumplen las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="0b683-134">This behavior occurs when the [FILTER](er-functions-list-filter.md) function is used and the following conditions are met:</span></span>

- <span data-ttu-id="0b683-135">La opción **PEDIR CONSULTA** se desactiva para el origen de datos de la función `VALUEIN` que se refiere a la lista de registros.</span><span class="sxs-lookup"><span data-stu-id="0b683-135">The **ASK FOR QUERY** option is turned off for the data source of the `VALUEIN` function that refers to the list of records.</span></span> <span data-ttu-id="0b683-136">No se aplicarán condiciones adicionales a este origen de datos en el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="0b683-136">No additional conditions will be applied to this data source at runtime.</span></span>
- <span data-ttu-id="0b683-137">No se configuran expresiones anidadas para el origen de datos de la función `VALUEIN` que se refiere a la lista de registros.</span><span class="sxs-lookup"><span data-stu-id="0b683-137">No nested expressions are configured for the data source of the `VALUEIN` function that refers to the list of records.</span></span>
- <span data-ttu-id="0b683-138">Un elemento de lista de la función `VALUEIN` hace referencia a un campo del origen de datos especificado, no una expresión o un método.</span><span class="sxs-lookup"><span data-stu-id="0b683-138">A list item of the `VALUEIN` function refers to a field of the specified data source, not to an expression or method of that data source.</span></span>

<span data-ttu-id="0b683-139">Considere usar esta opción en lugar de la función [WHERE](er-functions-list-where.md) que se describe anteriormente en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="0b683-139">Consider using this option instead of the [WHERE](er-functions-list-where.md) function that is described earlier in this example.</span></span>

## <a name="example-2"></a><span data-ttu-id="0b683-140">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="0b683-140">Example 2</span></span>

<span data-ttu-id="0b683-141">Defina los siguientes orígenes de datos en la asignación de su modelo:</span><span class="sxs-lookup"><span data-stu-id="0b683-141">You define the following data sources in your model mapping:</span></span>

- <span data-ttu-id="0b683-142">El origen de datos **En** del tipo *Registros de la tabla*.</span><span class="sxs-lookup"><span data-stu-id="0b683-142">The **In** data source of the *Table records* type.</span></span> <span data-ttu-id="0b683-143">Este origen de datos se refiere a la tabla Intrastat.</span><span class="sxs-lookup"><span data-stu-id="0b683-143">This data source refers to the Intrastat table.</span></span>
- <span data-ttu-id="0b683-144">El origen de datos **Puerto** del tipo *Registros de la tabla*.</span><span class="sxs-lookup"><span data-stu-id="0b683-144">The **Port** data source of the *Table records* type.</span></span> <span data-ttu-id="0b683-145">Este origen de datos se refiere a la tabla IntrastatPort.</span><span class="sxs-lookup"><span data-stu-id="0b683-145">This data source refers to the IntrastatPort table.</span></span>

<span data-ttu-id="0b683-146">Cuando se llama a un origen de datos que está configurado como la expresión `FILTER (In, VALUEIN(In.Port, Port, Port.PortId)`, la instrucción SQL siguiente se genera para devolver registros filtrados de la tabla Intrastat.</span><span class="sxs-lookup"><span data-stu-id="0b683-146">When a data source is called that has been configured as the `FILTER (In, VALUEIN(In.Port, Port, Port.PortId)` expression, the following SQL statement is generated to return filtered records of the Intrastat table.</span></span>

```vb
select … from Intrastat
exists join TableId from IntrastatPort
where IntrastatPort.PortId = Intrastat.Port
```

<span data-ttu-id="0b683-147">Para los campos **dataAreaId** , la instrucción SQL final se genera usando el operador `IN`.</span><span class="sxs-lookup"><span data-stu-id="0b683-147">For **dataAreaId** fields, the final SQL statement is generated by the using `IN` operator.</span></span>

## <a name="example-3"></a><span data-ttu-id="0b683-148">Ejemplo 3</span><span class="sxs-lookup"><span data-stu-id="0b683-148">Example 3</span></span>

<span data-ttu-id="0b683-149">Defina los siguientes orígenes de datos en la asignación de su modelo:</span><span class="sxs-lookup"><span data-stu-id="0b683-149">You define the following data sources in your model mapping:</span></span>

- <span data-ttu-id="0b683-150">Agregue el origen de datos **Le** al tipo de datos *Campo calculado*.</span><span class="sxs-lookup"><span data-stu-id="0b683-150">The **Le** data source of the *Calculated field* type.</span></span> <span data-ttu-id="0b683-151">Este origen de datos contiene la expresión `SPLIT ("DEMF,GBSI,USMF", ",")`.</span><span class="sxs-lookup"><span data-stu-id="0b683-151">This data source contains the expression `SPLIT ("DEMF,GBSI,USMF", ",")`.</span></span>
- <span data-ttu-id="0b683-152">El origen de datos **En** del tipo *Registros de la tabla*.</span><span class="sxs-lookup"><span data-stu-id="0b683-152">The **In** data source of the *Table records* type.</span></span> <span data-ttu-id="0b683-153">Esta fuente de datos se refiere a la tabla Intrastat, y la opción **Entre empresas** está desactivada para ello.</span><span class="sxs-lookup"><span data-stu-id="0b683-153">This data source refers to the Intrastat table, and the **Cross-company** option is turned on for it.</span></span>

<span data-ttu-id="0b683-154">Cuando se llama a un origen de datos que se configuró como la expresión `FILTER (In, VALUEIN (In.dataAreaId, Le, Le.Value)`, la instrucción SQL final contiene la siguiente condición.</span><span class="sxs-lookup"><span data-stu-id="0b683-154">When a data source is called that has been configured as the `FILTER (In, VALUEIN (In.dataAreaId, Le, Le.Value)` expression, the final SQL statement contains the following condition.</span></span>

```vb
Intrastat.dataAreaId IN ('DEMF', 'GBSI', 'USMF')
```

## <a name="additional-resources"></a><span data-ttu-id="0b683-155">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="0b683-155">Additional resources</span></span>

[<span data-ttu-id="0b683-156">Funciones lógicas</span><span class="sxs-lookup"><span data-stu-id="0b683-156">Logical functions</span></span>](er-functions-category-logical.md)
