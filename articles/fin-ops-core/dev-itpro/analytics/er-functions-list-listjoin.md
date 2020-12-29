---
title: Función LISTJOIN de ER
description: En este tema se proporciona información sobre cómo usar la función LISTJOIN de informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 04/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 28f03e5e6af0f252a994f2e54b57a5ef654f4e67
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "4682252"
---
# <a name="listjoin-er-function"></a><span data-ttu-id="45869-103">Función LISTJOIN de ER</span><span class="sxs-lookup"><span data-stu-id="45869-103">LISTJOIN ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="45869-104">La función `LISTJOIN` devuelve un valor *Lista de registros* que consiste en una lista de registros nueva unida creada a partir de los argumentos especificados.</span><span class="sxs-lookup"><span data-stu-id="45869-104">The `LISTJOIN` function returns a *Record list* value that represents a new joined list of records that is created from the specified arguments.</span></span>

## <a name="syntax"></a><span data-ttu-id="45869-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="45869-105">Syntax</span></span>

```vb
LIST (list 1 [, list 2, …, list N])
```

## <a name="arguments"></a><span data-ttu-id="45869-106">Argumentos</span><span class="sxs-lookup"><span data-stu-id="45869-106">Arguments</span></span>

<span data-ttu-id="45869-107">`list 1`: *Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="45869-107">`list 1`: *Record list*</span></span>

<span data-ttu-id="45869-108">Una referencia a un origen de datos de tipo de datos *Lista de registros*.</span><span class="sxs-lookup"><span data-stu-id="45869-108">A reference to a data source of the *Record list* data type.</span></span> <span data-ttu-id="45869-109">Este argumento es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="45869-109">This argument is mandatory.</span></span>

<span data-ttu-id="45869-110">`list N`: *Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="45869-110">`list N`: *Record list*</span></span>

<span data-ttu-id="45869-111">Una referencia a un origen de datos de tipo de datos *Lista de registros*.</span><span class="sxs-lookup"><span data-stu-id="45869-111">A reference to a data source of the *Record list* data type.</span></span> <span data-ttu-id="45869-112">Estos argumentos adicionales son opcionales.</span><span class="sxs-lookup"><span data-stu-id="45869-112">These additional arguments are optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="45869-113">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="45869-113">Return values</span></span>

<span data-ttu-id="45869-114">*Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="45869-114">*Record list*</span></span>

<span data-ttu-id="45869-115">La lista de registros resultante.</span><span class="sxs-lookup"><span data-stu-id="45869-115">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="45869-116">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="45869-116">Usage notes</span></span>

<span data-ttu-id="45869-117">La estructura de la lista que se crea contiene solo los campos que están presentes en la estructura de cada lista registro que se menciona en los argumentos.</span><span class="sxs-lookup"><span data-stu-id="45869-117">The structure of the list that is created contains only the fields that are present in the structure of every record list that is referenced in the arguments.</span></span>

## <a name="example"></a><span data-ttu-id="45869-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="45869-118">Example</span></span>

<span data-ttu-id="45869-119">Especifica el origen de datos **Registro 1** del tipo `Container`.</span><span class="sxs-lookup"><span data-stu-id="45869-119">You enter data source **Record 1** of the `Container` type.</span></span> <span data-ttu-id="45869-120">Esta fuente de datos contiene los siguientes campos anidados del tipo `Calculated field`:</span><span class="sxs-lookup"><span data-stu-id="45869-120">This data source contains the following nested fields of the `Calculated field` type:</span></span>

- <span data-ttu-id="45869-121">**Código**: este campo contiene una expresión que devuelve un valor de tipo `String`.</span><span class="sxs-lookup"><span data-stu-id="45869-121">**Code**: This field contains an expression that returns a value of the `String` type.</span></span>
- <span data-ttu-id="45869-122">**Cantidad**: este campo contiene una expresión que devuelve un valor de tipo `Real`.</span><span class="sxs-lookup"><span data-stu-id="45869-122">**Amount**: This field contains an expression that returns a value of the `Real` type.</span></span>

<span data-ttu-id="45869-123">Entonces especifique el origen de datos **Registro 2** del tipo `Container`.</span><span class="sxs-lookup"><span data-stu-id="45869-123">You then enter data source **Record 2** of the `Container` type.</span></span> <span data-ttu-id="45869-124">Esta fuente de datos contiene los siguientes campos anidados del tipo `Calculated field`:</span><span class="sxs-lookup"><span data-stu-id="45869-124">This data source contains the following nested fields of the `Calculated field` type:</span></span>

- <span data-ttu-id="45869-125">**Cantidad**: este campo contiene una expresión que devuelve un valor de tipo `Real`.</span><span class="sxs-lookup"><span data-stu-id="45869-125">**Amount**: This field contains an expression that returns a value of the `Real` type.</span></span>
- <span data-ttu-id="45869-126">**IsValid**: este campo contiene una expresión que devuelve un valor de tipo `Boolean`.</span><span class="sxs-lookup"><span data-stu-id="45869-126">**IsValid**: This field contains an expression that returns a value of the `Boolean` type.</span></span>

![Página de diseñador de asignación de modelos de ER](./media/er-functions-list-listjoin-image1.gif)

<span data-ttu-id="45869-128">En este caso, la expresión `LISTJOIN(LIST('Record 1'), LIST('Record 2'))` devuelve una nueva lista que contiene dos registros.</span><span class="sxs-lookup"><span data-stu-id="45869-128">In this case, the expression `LISTJOIN(LIST('Record 1'), LIST('Record 2'))` returns a new list that contains two records.</span></span>

![Página del diseñador de asignación de modelos de ER con dos registros](./media/er-functions-list-listjoin-image2.gif)

<span data-ttu-id="45869-130">La estructura de esta lista consta de un solo campo **Importe** del tipo `Real`, porque este campo es el único campo que se presenta en cada argumento de la función llamada.</span><span class="sxs-lookup"><span data-stu-id="45869-130">The structure of this list consists of a single **Amount** field of the `Real` type, because this field is the only field that is presented in every argument of the called function.</span></span>

![Campo de cantidad de la página de diseñador de asignación de modelos de ER](./media/er-functions-list-listjoin-image3.gif)

## <a name="additional-resources"></a><span data-ttu-id="45869-132">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="45869-132">Additional resources</span></span>

[<span data-ttu-id="45869-133">Funciones de lista</span><span class="sxs-lookup"><span data-stu-id="45869-133">List functions</span></span>](er-functions-category-list.md)

[<span data-ttu-id="45869-134">Depurar las fuentes de datos de un formato ER ejecutado para analizar el flujo de datos y la transformación</span><span class="sxs-lookup"><span data-stu-id="45869-134">Debug data sources of an executed ER format to analyze data flow and transformation</span></span>](er-debug-data-sources.md)
