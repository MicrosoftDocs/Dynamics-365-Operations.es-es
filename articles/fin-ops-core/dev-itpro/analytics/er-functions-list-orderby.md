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
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0a6b5cddc325625dc5b3d677ffcc1da1f8b829cd
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041961"
---
# <span data-ttu-id="e7c1a-103"><a name="ORDERBY">Función ORDERBY de ER</a></span><span class="sxs-lookup"><span data-stu-id="e7c1a-103"><a name="ORDERBY">ORDERBY ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e7c1a-104">La función `ORDERBY` devuelve la lista especificada como un valor *Lista de registros* después de que se haya ordenado de acuerdo con los argumentos especificados.</span><span class="sxs-lookup"><span data-stu-id="e7c1a-104">The `ORDERBY` function returns the specified list as a *Record list* value after it has been sorted according to the specified arguments.</span></span> <span data-ttu-id="e7c1a-105">Estos argumentos se pueden definir como expresiones.</span><span class="sxs-lookup"><span data-stu-id="e7c1a-105">These arguments can be defined as expressions.</span></span>

## <a name="syntax"></a><span data-ttu-id="e7c1a-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e7c1a-106">Syntax</span></span>

```vb
ORDERBY (list , expression 1[, expression 2, …, expression N])
```

## <a name="arguments"></a><span data-ttu-id="e7c1a-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="e7c1a-107">Arguments</span></span>

<span data-ttu-id="e7c1a-108">`list`: *Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="e7c1a-108">`list`: *Record list*</span></span>

<span data-ttu-id="e7c1a-109">La ruta válida de un origen de datos del tipo de datos *Lista de registros*.</span><span class="sxs-lookup"><span data-stu-id="e7c1a-109">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="e7c1a-110">`expression 1`: *Campo*</span><span class="sxs-lookup"><span data-stu-id="e7c1a-110">`expression 1`: *Field*</span></span>

<span data-ttu-id="e7c1a-111">La ruta válida de un campo del origen de datos al que hace referencia el argumento `list` de la función llamada.</span><span class="sxs-lookup"><span data-stu-id="e7c1a-111">The valid path of a field of the data source that is referenced by the `list` argument of the called function.</span></span> <span data-ttu-id="e7c1a-112">El campo referenciado debe ser un campo del tipo de datos primitivo.</span><span class="sxs-lookup"><span data-stu-id="e7c1a-112">The referenced field must be a field of the primitive data type.</span></span> <span data-ttu-id="e7c1a-113">Este argumento es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="e7c1a-113">This argument is required.</span></span>

<span data-ttu-id="e7c1a-114">`expression N`: *Campo*</span><span class="sxs-lookup"><span data-stu-id="e7c1a-114">`expression N`: *Field*</span></span>

<span data-ttu-id="e7c1a-115">La ruta válida de un campo del origen de datos al que hace referencia el argumento `list` de la función llamada.</span><span class="sxs-lookup"><span data-stu-id="e7c1a-115">The valid path of a field of the data source that is referenced by the `list` argument of the called function.</span></span> <span data-ttu-id="e7c1a-116">El campo referenciado debe ser un campo del tipo de datos primitivo.</span><span class="sxs-lookup"><span data-stu-id="e7c1a-116">The referenced field must be a field of the primitive data type.</span></span> <span data-ttu-id="e7c1a-117">Estos argumentos adicionales son opcionales.</span><span class="sxs-lookup"><span data-stu-id="e7c1a-117">These additional arguments are optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="e7c1a-118">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="e7c1a-118">Return values</span></span>

<span data-ttu-id="e7c1a-119">*Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="e7c1a-119">*Record list*</span></span>

<span data-ttu-id="e7c1a-120">La lista de registros resultante.</span><span class="sxs-lookup"><span data-stu-id="e7c1a-120">The resulting list of records.</span></span>

## <a name="example-1"></a><span data-ttu-id="e7c1a-121">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="e7c1a-121">Example 1</span></span>

<span data-ttu-id="e7c1a-122">Si especifica el origen de datos **DS** del tipo *Campo calculado* y contiene la expresión `SPLIT ("C|B|A", "|")`, la expresión `FIRST( ORDERBY( DS, DS. Value)).Value` devuelve el valor de texto **"A"**.</span><span class="sxs-lookup"><span data-stu-id="e7c1a-122">If you enter data source **DS** of the *Calculated field* type, and it contains the expression `SPLIT ("C|B|A", "|")`, the expression `FIRST( ORDERBY( DS, DS. Value)).Value` returns the text value **"A"**.</span></span>

## <a name="example-2"></a><span data-ttu-id="e7c1a-123">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="e7c1a-123">Example 2</span></span>

<span data-ttu-id="e7c1a-124">Cuando **Proveedor** se configura como origen de datos de ER que hace referencia a la tabla VendTable, la expresión `ORDERBY (Vendors, Vendors.'name()')` devuelva la lista de proveedores que se clasifica por nombre en orden ascendente.</span><span class="sxs-lookup"><span data-stu-id="e7c1a-124">If **Vendor** is configured as an Electronic reporting (ER) data source that refers to the VendTable table, the expression `ORDERBY (Vendors, Vendors.'name()')` returns a list of vendors that is sorted by name in ascending order.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e7c1a-125">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="e7c1a-125">Additional resources</span></span>

[<span data-ttu-id="e7c1a-126">Funciones de lista</span><span class="sxs-lookup"><span data-stu-id="e7c1a-126">List functions</span></span>](er-functions-category-list.md)
