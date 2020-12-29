---
title: Función de ER LISTDISTINCT
description: En este tema se proporciona información sobre cómo usar la función LISTDISTINCT de informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 7/30/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-08-01
ms.dyn365.ops.version: AX 10.0.14
ms.openlocfilehash: 2333cfc21a16a5905acadd590982020fdf878330
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "4682276"
---
# <a name="listdistinct-er-function"></a><span data-ttu-id="850fb-103">Función de ER LISTDISTINCT</span><span class="sxs-lookup"><span data-stu-id="850fb-103">LISTDISTINCT ER Function</span></span>

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="850fb-104">La función `LISTDISTINCT` calcula la expresión especificada como un selector para cada registro de la lista especificada.</span><span class="sxs-lookup"><span data-stu-id="850fb-104">The `LISTDISTINCT` function calculates the specified expression as a selector for every record of the specified list.</span></span> <span data-ttu-id="850fb-105">Devuelve un nuevo valor de *Lista de registros* que contiene un solo registro para cada valor único del selector.</span><span class="sxs-lookup"><span data-stu-id="850fb-105">It returns a new *Record list* value that contains a single record for each unique selector value.</span></span>

## <a name="syntax"></a><span data-ttu-id="850fb-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="850fb-106">Syntax</span></span>

```
LISTDISTINCT (list, selector)
```

## <a name="arguments"></a><span data-ttu-id="850fb-107">Argumentos</span><span class="sxs-lookup"><span data-stu-id="850fb-107">Arguments</span></span>

<span data-ttu-id="850fb-108">`list`: *Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="850fb-108">`list`: *Record list*</span></span>

<span data-ttu-id="850fb-109">La ruta válida de un origen de datos del tipo de datos *Lista de registros*.</span><span class="sxs-lookup"><span data-stu-id="850fb-109">The valid path of a data source of the *Record list* data type.</span></span>

<span data-ttu-id="850fb-110">`selector`: *Tipo de datos primitivo*</span><span class="sxs-lookup"><span data-stu-id="850fb-110">`selector`: *Primitive data type*</span></span>

<span data-ttu-id="850fb-111">Una expresión válida que se usa para calcular un valor de selector para cada registro de la lista especificada.</span><span class="sxs-lookup"><span data-stu-id="850fb-111">A valid expression that is used to calculate a selector value for every record in the specified list.</span></span>

<span data-ttu-id="850fb-112">Se admiten los siguientes tipos de datos para este parámetro:</span><span class="sxs-lookup"><span data-stu-id="850fb-112">The following data types are supported for this parameter:</span></span>

- <span data-ttu-id="850fb-113">Booleano</span><span class="sxs-lookup"><span data-stu-id="850fb-113">Boolean</span></span>
- <span data-ttu-id="850fb-114">Fecha</span><span class="sxs-lookup"><span data-stu-id="850fb-114">Date</span></span>
- <span data-ttu-id="850fb-115">Fecha y hora</span><span class="sxs-lookup"><span data-stu-id="850fb-115">DateTime</span></span>
- <span data-ttu-id="850fb-116">GUID</span><span class="sxs-lookup"><span data-stu-id="850fb-116">GUID</span></span>
- <span data-ttu-id="850fb-117">Entero</span><span class="sxs-lookup"><span data-stu-id="850fb-117">Integer</span></span>
- <span data-ttu-id="850fb-118">Int64</span><span class="sxs-lookup"><span data-stu-id="850fb-118">Int64</span></span>
- <span data-ttu-id="850fb-119">Real</span><span class="sxs-lookup"><span data-stu-id="850fb-119">Real</span></span>
- <span data-ttu-id="850fb-120">Cadena</span><span class="sxs-lookup"><span data-stu-id="850fb-120">String</span></span>

## <a name="return-values"></a><span data-ttu-id="850fb-121">Valores de retorno</span><span class="sxs-lookup"><span data-stu-id="850fb-121">Return values</span></span>

<span data-ttu-id="850fb-122">*Lista de registros*</span><span class="sxs-lookup"><span data-stu-id="850fb-122">*Record list*</span></span>

<span data-ttu-id="850fb-123">La lista de registros resultante.</span><span class="sxs-lookup"><span data-stu-id="850fb-123">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="850fb-124">Notas de uso</span><span class="sxs-lookup"><span data-stu-id="850fb-124">Usage notes</span></span>

<span data-ttu-id="850fb-125">La estructura de la lista que se crea coincide con la estructura de la lista especificada.</span><span class="sxs-lookup"><span data-stu-id="850fb-125">The structure of the list that is created matches the structure of the specified list.</span></span>

<span data-ttu-id="850fb-126">El mismo valor de selector se puede calcular para varios registros en la lista especificada.</span><span class="sxs-lookup"><span data-stu-id="850fb-126">The same selector value might be calculated for multiple records in the specified list.</span></span> <span data-ttu-id="850fb-127">En este caso, los valores de campo del registro correspondiente en la lista creada son iguales a los valores del primer registro de la lista especificada para el que se calcula el valor del selector.</span><span class="sxs-lookup"><span data-stu-id="850fb-127">In this case, field values of the corresponding record in the created list equal the values of the first record from the specified list that the selector value is calculated for.</span></span>

<span data-ttu-id="850fb-128">La ejecución de esta función se realiza en cualquier origen de datos de [Informes electrónicos (ER)](general-electronic-reporting.md) del tipo *Lista de registros* que está presente en la memoria.</span><span class="sxs-lookup"><span data-stu-id="850fb-128">The execution of this function is done on any [Electronic reporting (ER)](general-electronic-reporting.md) data source of the *Record list* type that is present in memory.</span></span>

<span data-ttu-id="850fb-129">El origen de datos **GROUPBY** también se puede utilizar para generar la lista de registros para la que se calcular el selector que tiene valores distintos.</span><span class="sxs-lookup"><span data-stu-id="850fb-129">The **GROUPBY** data source can also be used to generate the list of records that the selector that has distinct values is calculated for.</span></span> <span data-ttu-id="850fb-130">Sin embargo, desde una perspectiva de rendimiento y consumo de memoria, es mejor utilizar la función `LISTDISTINCT` que el origen de datos **GROUPBY**, ya que la ejecución de la función se realiza en memoria.</span><span class="sxs-lookup"><span data-stu-id="850fb-130">However, from a performance and memory consumption perspective, it's better to use the `LISTDISTINCT` function than the **GROUPBY** data source, because the execution of the function is done in memory.</span></span>

## <a name="example"></a><span data-ttu-id="850fb-131">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="850fb-131">Example</span></span>

<span data-ttu-id="850fb-132">El siguiente ejemplo muestra cómo puede obtener la lista de números de cuenta de cliente únicos para los que se ha emitido al menos una factura de venta o factura de proyecto durante un período específico.</span><span class="sxs-lookup"><span data-stu-id="850fb-132">The following example shows how you can get the list of unique customer account numbers that at least one sales invoice or project invoice has been issued to during a specific period.</span></span>

1. <span data-ttu-id="850fb-133">Especifique el origen de datos **SalesInvoice** de tipo `Record list` que hace referencia a la tabla de aplicación **CustInvoiceJour** y filtra las facturas de venta para períodos específicos.</span><span class="sxs-lookup"><span data-stu-id="850fb-133">Enter the **SalesInvoice** data source of the `Record list` type that refers to the **CustInvoiceJour** application table and filters sales invoices for specific periods.</span></span>

    <span data-ttu-id="850fb-134">El campo `InvoiceAccount` de este origen de datos devuelve el número de cuenta de un cliente facturado.</span><span class="sxs-lookup"><span data-stu-id="850fb-134">The `InvoiceAccount` field of this data source returns the account number of an invoiced customer.</span></span>

2. <span data-ttu-id="850fb-135">Especifique el origen de datos **ProjectInvoice** de tipo `Record list` que hace referencia a la tabla de aplicación **ProjInvoiceJour** y filtra las facturas de proyecto para períodos específicos.</span><span class="sxs-lookup"><span data-stu-id="850fb-135">Enter the **ProjectInvoice** data source of the `Record list` type that refers to the **ProjInvoiceJour** application table and filters project invoices for specific periods.</span></span>

    <span data-ttu-id="850fb-136">El campo `InvoiceAccount` de este origen de datos devuelve el número de cuenta de un cliente facturado.</span><span class="sxs-lookup"><span data-stu-id="850fb-136">The `InvoiceAccount` field of this data source returns the account number of an invoiced customer.</span></span>

3. <span data-ttu-id="850fb-137">Configure el origen de datos **AllInvoices** de tipo `Calculated field` que contiene la expression `LISTJOIN(SalesInvoice, ProjectInvoice)`.</span><span class="sxs-lookup"><span data-stu-id="850fb-137">Configure the **AllInvoices** data source of the `Calculated field` type that contains the expression `LISTJOIN(SalesInvoice, ProjectInvoice)`.</span></span>

    <span data-ttu-id="850fb-138">Este origen de datos devuelve la lista combinada de facturas de ventas y facturas de proyectos.</span><span class="sxs-lookup"><span data-stu-id="850fb-138">This data source returns the joined list of sales invoices and project invoices.</span></span>

4. <span data-ttu-id="850fb-139">Configure el origen de datos **InvoicedCustomer** de tipo `Record list` que contiene la expression `LISTDISTINCT(AllInvoices, AllInvoices.InvoiceAccount)`.</span><span class="sxs-lookup"><span data-stu-id="850fb-139">Configure the **InvoicedCustomer** data source of the `Record list` type that contains the expression `LISTDISTINCT(AllInvoices, AllInvoices.InvoiceAccount)`.</span></span>

    <span data-ttu-id="850fb-140">Este origen de datos devuelve una nueva lista que contiene un solo registro para cada cliente único que se ha facturado durante el período definido.</span><span class="sxs-lookup"><span data-stu-id="850fb-140">This data source returns a new list that contains a single record for every unique customer that has been invoiced during the defined period.</span></span> <span data-ttu-id="850fb-141">El campo `InvoiceAccount` de esta lista contiene un número de cuenta de cliente.</span><span class="sxs-lookup"><span data-stu-id="850fb-141">The `InvoiceAccount` field of this list contains a customer account number.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="850fb-142">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="850fb-142">Additional resources</span></span>

[<span data-ttu-id="850fb-143">Funciones de lista</span><span class="sxs-lookup"><span data-stu-id="850fb-143">List functions</span></span>](er-functions-category-list.md)
