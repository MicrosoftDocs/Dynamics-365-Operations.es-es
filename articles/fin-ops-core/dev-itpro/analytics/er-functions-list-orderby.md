---
title: Función ORDERBY de ER
description: En este tema se proporciona información sobre cómo usar la función ORDERBY de informes electrónicos (ER).
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
ms.openlocfilehash: c39700fab90265ed1915b4815a6bb27af58d9516
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686473"
---
# <a name="orderby-er-function"></a><span data-ttu-id="fffea-103">Función ORDERBY de ER</span><span class="sxs-lookup"><span data-stu-id="fffea-103">ORDERBY ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="fffea-104">La función `ORDERBY` devuelve la lista especificada como un valor *Lista de registros* después de que se haya ordenado de acuerdo con los argumentos especificados.</span><span class="sxs-lookup"><span data-stu-id="fffea-104">The `ORDERBY` function returns the specified list as a *Record list* value after it has been sorted according to the specified arguments.</span></span> <span data-ttu-id="fffea-105">Estos argumentos se pueden definir como expresiones.</span><span class="sxs-lookup"><span data-stu-id="fffea-105">These arguments can be defined as expressions.</span></span>

## <a name="syntax"></a><span data-ttu-id="fffea-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fffea-106">Syntax</span></span>

```vb
ORDERBY (list , expression 1[, expression 2, …, expression N])
```

## <a name="arguments"></a><span data-ttu-id="fffea-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="fffea-107">Arguments</span></span>

<span data-ttu-id="fffea-108">`list`: *Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="fffea-108">`list`: *Record list*</span></span>

<span data-ttu-id="fffea-109">La ruta válida de un origen de datos del tipo de datos *Lista de registros*.</span><span class="sxs-lookup"><span data-stu-id="fffea-109">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="fffea-110">`expression 1`: *Campo*</span><span class="sxs-lookup"><span data-stu-id="fffea-110">`expression 1`: *Field*</span></span>

<span data-ttu-id="fffea-111">La ruta válida de un campo del origen de datos al que hace referencia el argumento `list` de la función llamada.</span><span class="sxs-lookup"><span data-stu-id="fffea-111">The valid path of a field of the data source that is referenced by the `list` argument of the called function.</span></span> <span data-ttu-id="fffea-112">El campo referenciado debe ser un campo del tipo de datos primitivo.</span><span class="sxs-lookup"><span data-stu-id="fffea-112">The referenced field must be a field of the primitive data type.</span></span> <span data-ttu-id="fffea-113">Este argumento es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="fffea-113">This argument is required.</span></span>

<span data-ttu-id="fffea-114">`expression N`: *Campo*</span><span class="sxs-lookup"><span data-stu-id="fffea-114">`expression N`: *Field*</span></span>

<span data-ttu-id="fffea-115">La ruta válida de un campo del origen de datos al que hace referencia el argumento `list` de la función llamada.</span><span class="sxs-lookup"><span data-stu-id="fffea-115">The valid path of a field of the data source that is referenced by the `list` argument of the called function.</span></span> <span data-ttu-id="fffea-116">El campo referenciado debe ser un campo del tipo de datos primitivo.</span><span class="sxs-lookup"><span data-stu-id="fffea-116">The referenced field must be a field of the primitive data type.</span></span> <span data-ttu-id="fffea-117">Estos argumentos adicionales son opcionales.</span><span class="sxs-lookup"><span data-stu-id="fffea-117">These additional arguments are optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="fffea-118">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="fffea-118">Return values</span></span>

<span data-ttu-id="fffea-119">*Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="fffea-119">*Record list*</span></span>

<span data-ttu-id="fffea-120">La lista de registros resultante.</span><span class="sxs-lookup"><span data-stu-id="fffea-120">The resulting list of records.</span></span>

## <a name="example-1"></a><span data-ttu-id="fffea-121">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="fffea-121">Example 1</span></span>

<span data-ttu-id="fffea-122">Si especifica el origen de datos **DS** del tipo *Campo calculado* y contiene la expresión `SPLIT ("C|B|A", "|")`, la expresión `FIRST( ORDERBY( DS, DS. Value)).Value` devuelve el valor de texto **"A"**.</span><span class="sxs-lookup"><span data-stu-id="fffea-122">If you enter data source **DS** of the *Calculated field* type, and it contains the expression `SPLIT ("C|B|A", "|")`, the expression `FIRST( ORDERBY( DS, DS. Value)).Value` returns the text value **"A"**.</span></span>

## <a name="example-2"></a><span data-ttu-id="fffea-123">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="fffea-123">Example 2</span></span>

<span data-ttu-id="fffea-124">Cuando **Proveedor** se configura como origen de datos de ER que hace referencia a la tabla VendTable, la expresión `ORDERBY (Vendors, Vendors.'name()')` devuelva la lista de proveedores que se clasifica por nombre en orden ascendente.</span><span class="sxs-lookup"><span data-stu-id="fffea-124">If **Vendor** is configured as an Electronic reporting (ER) data source that refers to the VendTable table, the expression `ORDERBY (Vendors, Vendors.'name()')` returns a list of vendors that is sorted by name in ascending order.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="fffea-125">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="fffea-125">Additional resources</span></span>

[<span data-ttu-id="fffea-126">Funciones de lista</span><span class="sxs-lookup"><span data-stu-id="fffea-126">List functions</span></span>](er-functions-category-list.md)
