---
title: Función VALUEINLARGE ER
description: Este tema proporciona información general sobre cómo usar la función VALUEINLARGE de informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 08/17/2020
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
ms.search.validFrom: 2020-08-01
ms.dyn365.ops.version: AX 10.0.14
ms.openlocfilehash: 26a7148a4caa80a191688145bac625bdf0bf83b2
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686915"
---
# <a name="valueinlarge-er-function"></a><span data-ttu-id="72a9a-103">Función VALUEINLARGE ER</span><span class="sxs-lookup"><span data-stu-id="72a9a-103">VALUEINLARGE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="72a9a-104">La función `VALUEINLARGE` determina si la entrada especificada del tipo *Int64* o *Entero* coincide con algún valor de un elemento específico de la lista especificada.</span><span class="sxs-lookup"><span data-stu-id="72a9a-104">The `VALUEINLARGE` function determines whether the specified input of the *Int64* or *Integer* type matches any value of a specified item in the specified list.</span></span> <span data-ttu-id="72a9a-105">La función devuelve un valor *booleano* de **VERDADERO** si la entrada especificada coincide con el resultado de ejecutar la expresión especificada para al menos un registro de la lista especificada.</span><span class="sxs-lookup"><span data-stu-id="72a9a-105">The function returns a *Boolean* value of **TRUE** if the specified input matches the result of running the specified expression for at least one record of the specified list.</span></span> <span data-ttu-id="72a9a-106">De lo contrario, la expresión devuelve un valor *Booleano* de **FALSE**.</span><span class="sxs-lookup"><span data-stu-id="72a9a-106">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span> <span data-ttu-id="72a9a-107">Para entender la diferencia con la función `VALUEIN`, consulte la sección [Nota de uso](#usage_note) posterior de este tema.</span><span class="sxs-lookup"><span data-stu-id="72a9a-107">To understand the difference with the `VALUEIN` function, see the [Usage note](#usage_note) section later in this topic.</span></span>

## <a name="syntax"></a><span data-ttu-id="72a9a-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="72a9a-108">Syntax</span></span>

```vb
VALUEINLARGE (input, list, list item expression)
```

## <a name="arguments"></a><span data-ttu-id="72a9a-109">Argumentos</span><span class="sxs-lookup"><span data-stu-id="72a9a-109">Arguments</span></span>

<span data-ttu-id="72a9a-110">`input`: *Campo*</span><span class="sxs-lookup"><span data-stu-id="72a9a-110">`input`: *Field*</span></span>

<span data-ttu-id="72a9a-111">La ruta válida de un elemento de origen de datos del tipo *Lista de registros*.</span><span class="sxs-lookup"><span data-stu-id="72a9a-111">The valid path of a data source item of the *Record list* type.</span></span> <span data-ttu-id="72a9a-112">El valor de este elemento se conciliará.</span><span class="sxs-lookup"><span data-stu-id="72a9a-112">The value of this item will be matched.</span></span>

<span data-ttu-id="72a9a-113">`list`: *Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="72a9a-113">`list`: *Record list*</span></span>

<span data-ttu-id="72a9a-114">La ruta válida de un origen de datos del tipo de datos *Lista de registros*.</span><span class="sxs-lookup"><span data-stu-id="72a9a-114">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="72a9a-115">`list item expression`: *Expresión*</span><span class="sxs-lookup"><span data-stu-id="72a9a-115">`list item expression`: *Expression*</span></span>

<span data-ttu-id="72a9a-116">Un expresión condicional válida que señala o contiene un único campo de la lista especificada que se debe usar para la asignación.</span><span class="sxs-lookup"><span data-stu-id="72a9a-116">A valid conditional expression that either points to or contains a single field of the specified list that should be used for the matching.</span></span>

## <a name="return-values"></a><span data-ttu-id="72a9a-117">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="72a9a-117">Return values</span></span>

<span data-ttu-id="72a9a-118">*Booleano*</span><span class="sxs-lookup"><span data-stu-id="72a9a-118">*Boolean*</span></span>

<span data-ttu-id="72a9a-119">El valor *Booleano* resultante.</span><span class="sxs-lookup"><span data-stu-id="72a9a-119">The resulting *Boolean* value.</span></span>

## <a name=""></a><span data-ttu-id="72a9a-120"><a name="usage_note">Notas de uso</a></span><span class="sxs-lookup"><span data-stu-id="72a9a-120"><a name="usage_note">Usage notes</a></span></span>

<span data-ttu-id="72a9a-121">Cuando la entrada especificada representa un tipo *Int64* o *Entero* de un elemento de origen de datos, cuya llamada se puede traducir a una declaración SQL directa, la lista especificada se convierte en una tabla SQL temporal y la coincidencia se realiza en la base de datos mediante la ejecución de una única consulta `EXISTS JOIN`.</span><span class="sxs-lookup"><span data-stu-id="72a9a-121">When the specified input represents an *Int64* or *Integer* type of a data source item, the call to which is translatable to a direct SQL statement, the specified list is converted to a temporary SQL table and matching is performed in the database by executing a single `EXISTS JOIN` query.</span></span> <span data-ttu-id="72a9a-122">De lo contrario, esta función actúa como la función [`VALUEIN`](er-functions-logical-valuein.md).</span><span class="sxs-lookup"><span data-stu-id="72a9a-122">Otherwise, this function works as the [`VALUEIN`](er-functions-logical-valuein.md) function.</span></span>

<span data-ttu-id="72a9a-123">Cuando la entrada especificada representa un elemento de origen de datos diseñado como un elemento distinto del tipo *Int64* y *Entero*, se produce un error en el momento del diseño, informándole que la función `VALUEINLARGE` no es aplicable para la expresión ER configurada.</span><span class="sxs-lookup"><span data-stu-id="72a9a-123">When the specified input represents a data source item that is designed as an item other than *Int64* and *Integer* type, an error occurs at design time informing you that the `VALUEINLARGE` function is not applicable for the configured ER expression.</span></span>

<span data-ttu-id="72a9a-124">Cuando la expresión de función `VALUEINLARGE` se ejecuta y se usa más de una tabla temporal en el ámbito de esta ejecución, se produce un error de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="72a9a-124">When the `VALUEINLARGE` function expression is executed and more than one temporary table is used in scope of this execution, a runtime error occurs.</span></span>

## <a name="example"></a><span data-ttu-id="72a9a-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="72a9a-125">Example</span></span>

<span data-ttu-id="72a9a-126">Defina los siguientes orígenes de datos en la asignación de su modelo:</span><span class="sxs-lookup"><span data-stu-id="72a9a-126">You define the following data sources in your model mapping:</span></span>

- <span data-ttu-id="72a9a-127">El origen de datos **En** del tipo *Registros de la tabla*.</span><span class="sxs-lookup"><span data-stu-id="72a9a-127">The **In** data source of the *Table records* type.</span></span>
    - <span data-ttu-id="72a9a-128">Este origen de datos se refiere a la tabla **Intrastat**.</span><span class="sxs-lookup"><span data-stu-id="72a9a-128">This data source refers to the **Intrastat** table.</span></span>
    - <span data-ttu-id="72a9a-129">La opción **Entre empresas** está configurada en **No**.</span><span class="sxs-lookup"><span data-stu-id="72a9a-129">The **Cross-company** option is set to **No**.</span></span>
- <span data-ttu-id="72a9a-130">El origen de datos **InMemory** del tipo *Campo calculado*.</span><span class="sxs-lookup"><span data-stu-id="72a9a-130">The **InMemory** data source of the *Calculated field* type.</span></span>
    - <span data-ttu-id="72a9a-131">Este origen de datos contiene la expresión `WHERE (In, In.Port <> "")`.</span><span class="sxs-lookup"><span data-stu-id="72a9a-131">This data source contains the expression `WHERE (In, In.Port <> "")`.</span></span>
- <span data-ttu-id="72a9a-132">El origen de datos **InFiltered** del tipo *Campo calculado*.</span><span class="sxs-lookup"><span data-stu-id="72a9a-132">The **InFiltered** data source of the *Calculated field* type.</span></span>
    - <span data-ttu-id="72a9a-133">Este origen de datos contiene la expresión `FILTER (In, VALUEINLARGE(In.RecId, InMemory, InMemory.RecId)`.</span><span class="sxs-lookup"><span data-stu-id="72a9a-133">This data source contains the expression `FILTER (In, VALUEINLARGE(In.RecId, InMemory, InMemory.RecId)`.</span></span>

<span data-ttu-id="72a9a-134">Cuando el origen de datos **InFiltered** se llama en el contexto de la empresa **DEMF**, se crea una nueva tabla temporal en la base de datos de la aplicación, la lista de códigos de identificación de registros recopilada en la memoria se inserta en esta tabla y se genera la siguiente declaración SQL para devolver los registros filtrados de la tabla **Intrastat**.</span><span class="sxs-lookup"><span data-stu-id="72a9a-134">When the data source **InFiltered** is called under the context of the company **DEMF**, a new temporary table is created in the application database, the collected in memory list of record identification codes are inserted to this table, and the following SQL statement is generated to return filtered records of the **Intrastat** table.</span></span>

```xpp
SELECT … from Intrastat T1
WHERE ((T1.PARTITION=?) AND (T1.DATAAREAID IN (N'DEMF'))) AND
EXISTS (SELECT 'x' FROM tempdb."DBO".? T2 WHERE ((T2.PARTITION=?) AND (T1.RecId=T2.RecId)))
```

## <a name="additional-resources"></a><span data-ttu-id="72a9a-135">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="72a9a-135">Additional resources</span></span>

[<span data-ttu-id="72a9a-136">Funciones lógicas</span><span class="sxs-lookup"><span data-stu-id="72a9a-136">Logical functions</span></span>](er-functions-category-logical.md)

[<span data-ttu-id="72a9a-137">Funciones VALUEIN</span><span class="sxs-lookup"><span data-stu-id="72a9a-137">VALUEIN functions</span></span>](er-functions-logical-valuein.md)
