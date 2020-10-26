---
title: Valores de objeto de inventario
description: Este artículo proporciona información sobre cómo se calculan los valores de un objeto de inventario.
author: AndersGirke
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventCostOnhandItem
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 19111
ms.assetid: 56a7c8ba-bf4a-4b1d-918d-56bb96926c4f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: daa36dad4009cc25b89363dcff6b4496205522e3
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/10/2020
ms.locfileid: "3981496"
---
# <a name="inventory-object-values"></a><span data-ttu-id="d48f1-103">Valores de objeto de inventario</span><span class="sxs-lookup"><span data-stu-id="d48f1-103">Inventory object values</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d48f1-104">Este artículo proporciona información sobre cómo se calculan los valores de un objeto de inventario.</span><span class="sxs-lookup"><span data-stu-id="d48f1-104">This article provides information about how the values of an inventory object are calculated.</span></span> 

<span data-ttu-id="d48f1-105">Una nueva funcionalidad que se denomina **cantidad física** le permite ver los valores de un objeto de inventario específico.</span><span class="sxs-lookup"><span data-stu-id="d48f1-105">A new functionality that is named **physical quantity** lets you see the values of a specific inventory object.</span></span> 

<span data-ttu-id="d48f1-106">Un objeto de coste representa el nivel de entidad donde se realiza la contabilidad de inventario.</span><span class="sxs-lookup"><span data-stu-id="d48f1-106">A cost object represents the entity level where inventory accounting is performed.</span></span> <span data-ttu-id="d48f1-107">Para obtener más información acerca de los objetos de coste, consulte [Objetos de coste](cost-object.md).</span><span class="sxs-lookup"><span data-stu-id="d48f1-107">For more information about cost objects, see [Cost objects](cost-object.md).</span></span> 

<span data-ttu-id="d48f1-108">Para ver los valores de un objeto de inventario específico, haga clic en **Cantidad física** en la página **Objeto de coste**.</span><span class="sxs-lookup"><span data-stu-id="d48f1-108">To see the values of a specific inventory object, click **Physical quantity** on the **Cost object** page.</span></span> <span data-ttu-id="d48f1-109">A continuación se ve cómo se calcula el valor de un objeto de inventario:</span><span class="sxs-lookup"><span data-stu-id="d48f1-109">Here is how the value of an inventory object is calculated:</span></span> 

<span data-ttu-id="d48f1-110">Valor de objeto de inventario. Valor = Coste objeto.Coste unitario promedio × Objeto inventario.Cantidad</span><span class="sxs-lookup"><span data-stu-id="d48f1-110">Inventory object.Value = Cost object.Average unit cost × Inventory object.Quantity</span></span> 

<span data-ttu-id="d48f1-111">El siguiente ejemplo muestra cómo se calculan los valores de un objeto de inventario y un objeto de coste.</span><span class="sxs-lookup"><span data-stu-id="d48f1-111">The following example shows how the values of an inventory object and a cost object are calculated.</span></span> <span data-ttu-id="d48f1-112">Dos eventos de recepción de producto se registran en el artículo A:</span><span class="sxs-lookup"><span data-stu-id="d48f1-112">Two product receipt events are registered on item A:</span></span>

-   <span data-ttu-id="d48f1-113">Recepción de producto 1: Cantidad = 100 uds, Importe = 1.000,00 $, Sitio = 1, Almacén =11, N.º de lote</span><span class="sxs-lookup"><span data-stu-id="d48f1-113">Product receipt 1: Quantity = 100 pcs., Amount = $1,000.00, Site = 1, Warehouse =11, Batch No.</span></span> <span data-ttu-id="d48f1-114">= B1</span><span class="sxs-lookup"><span data-stu-id="d48f1-114">= B1</span></span>
-   <span data-ttu-id="d48f1-115">Recepción de producto 2: Cantidad = 50 uds, Importe = 800,00 $, Sitio = 1, Almacén =11, N.º de lote</span><span class="sxs-lookup"><span data-stu-id="d48f1-115">Product receipt 2: Quantity = 50 pcs., Amount = $800.00, Site = 1, Warehouse =11, Batch No.</span></span> <span data-ttu-id="d48f1-116">= B2</span><span class="sxs-lookup"><span data-stu-id="d48f1-116">= B2</span></span>

<span data-ttu-id="d48f1-117">La tabla siguiente muestra el resultado del cálculo de un objeto de coste.</span><span class="sxs-lookup"><span data-stu-id="d48f1-117">The following table shows the calculation result for a cost object.</span></span> <span data-ttu-id="d48f1-118">Puede ver el resultado en la página **Objeto de coste**.</span><span class="sxs-lookup"><span data-stu-id="d48f1-118">You can view the result on the **Cost object** page.</span></span>

<table style="width:100%;">
<colgroup>
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d48f1-119">Tipo de objeto</span><span class="sxs-lookup"><span data-stu-id="d48f1-119">Object type</span></span></th>
<th><span data-ttu-id="d48f1-120">Número de artículo</span><span class="sxs-lookup"><span data-stu-id="d48f1-120">Item number</span></span></th>
<th><span data-ttu-id="d48f1-121">Sitio</span><span class="sxs-lookup"><span data-stu-id="d48f1-121">Site</span></span></th>
<th><span data-ttu-id="d48f1-122">Cantidad</span><span class="sxs-lookup"><span data-stu-id="d48f1-122">Quantity</span></span></th>
<th><span data-ttu-id="d48f1-123">Unidad de inventario</span><span class="sxs-lookup"><span data-stu-id="d48f1-123">Inventory unit</span></span></th>
<th><span data-ttu-id="d48f1-124">Valor</span><span class="sxs-lookup"><span data-stu-id="d48f1-124">Value</span></span></th>
<th><span data-ttu-id="d48f1-125">Coste unitario promedio</span><span class="sxs-lookup"><span data-stu-id="d48f1-125">Average unit cost</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="d48f1-126">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="d48f1-126">Cost object</span></span></td>
<td><span data-ttu-id="d48f1-127">A</span><span class="sxs-lookup"><span data-stu-id="d48f1-127">A</span></span></td>
<td><span data-ttu-id="d48f1-128">1</span><span class="sxs-lookup"><span data-stu-id="d48f1-128">1</span></span></td>
<td><span data-ttu-id="d48f1-129">150</span><span class="sxs-lookup"><span data-stu-id="d48f1-129">150</span></span></td>
<td><span data-ttu-id="d48f1-130">Periodos</span><span class="sxs-lookup"><span data-stu-id="d48f1-130">Pcs.</span></span></td>
<td><p><span data-ttu-id="d48f1-131">1800,00 $</span><span class="sxs-lookup"><span data-stu-id="d48f1-131">$1800.00</span></span></p></td>
<td><p><span data-ttu-id="d48f1-132">12,00 $</span><span class="sxs-lookup"><span data-stu-id="d48f1-132">$12.00</span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="d48f1-133">La tabla siguiente muestra el resultado del cálculo de un objeto de inventario.</span><span class="sxs-lookup"><span data-stu-id="d48f1-133">The following table shows the calculation result for an inventory object.</span></span> <span data-ttu-id="d48f1-134">Puede ver el resultado haciendo clic en **Cantidad física** en la página **Objeto de coste**.</span><span class="sxs-lookup"><span data-stu-id="d48f1-134">You can view the result by clicking **Physical quantity** on the **Cost object** page.</span></span>

<table style="width:100%;">
<colgroup>
<col width="11%" />
<col width="11%" />
<col width="11%" />
<col width="11%" />
<col width="11%" />
<col width="11%" />
<col width="11%" />
<col width="11%" />
<col width="11%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d48f1-135">Tipo de objeto</span><span class="sxs-lookup"><span data-stu-id="d48f1-135">Object type</span></span></th>
<th><span data-ttu-id="d48f1-136">Número de artículo</span><span class="sxs-lookup"><span data-stu-id="d48f1-136">Item number</span></span></th>
<th><span data-ttu-id="d48f1-137">Sitio</span><span class="sxs-lookup"><span data-stu-id="d48f1-137">Site</span></span></th>
<th><span data-ttu-id="d48f1-138">Almacén</span><span class="sxs-lookup"><span data-stu-id="d48f1-138">Warehouse</span></span></th>
<th><span data-ttu-id="d48f1-139">N.º de lote</span><span class="sxs-lookup"><span data-stu-id="d48f1-139">Batch No.</span></span></th>
<th><span data-ttu-id="d48f1-140">Cantidad</span><span class="sxs-lookup"><span data-stu-id="d48f1-140">Quantity</span></span></th>
<th><span data-ttu-id="d48f1-141">Unidad de inventario</span><span class="sxs-lookup"><span data-stu-id="d48f1-141">Inventory unit</span></span></th>
<th><span data-ttu-id="d48f1-142">Valor</span><span class="sxs-lookup"><span data-stu-id="d48f1-142">Value</span></span></th>
<th><span data-ttu-id="d48f1-143">Coste unitario promedio</span><span class="sxs-lookup"><span data-stu-id="d48f1-143">Average unit cost</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="d48f1-144">Objeto de inventario</span><span class="sxs-lookup"><span data-stu-id="d48f1-144">Inventory object</span></span></td>
<td><span data-ttu-id="d48f1-145">A</span><span class="sxs-lookup"><span data-stu-id="d48f1-145">A</span></span></td>
<td><span data-ttu-id="d48f1-146">1</span><span class="sxs-lookup"><span data-stu-id="d48f1-146">1</span></span></td>
<td><span data-ttu-id="d48f1-147">11</span><span class="sxs-lookup"><span data-stu-id="d48f1-147">11</span></span></td>
<td><span data-ttu-id="d48f1-148">B1</span><span class="sxs-lookup"><span data-stu-id="d48f1-148">B1</span></span></td>
<td><span data-ttu-id="d48f1-149">100</span><span class="sxs-lookup"><span data-stu-id="d48f1-149">100</span></span></td>
<td><span data-ttu-id="d48f1-150">Periodos</span><span class="sxs-lookup"><span data-stu-id="d48f1-150">Pcs.</span></span></td>
<td><p><span data-ttu-id="d48f1-151">1200,00 $</span><span class="sxs-lookup"><span data-stu-id="d48f1-151">$1200.00</span></span></p></td>
<td><p><span data-ttu-id="d48f1-152">12,00 $</span><span class="sxs-lookup"><span data-stu-id="d48f1-152">$12.00</span></span></p></td>
</tr>
<tr class="even">
<td><span data-ttu-id="d48f1-153">Objeto de inventario</span><span class="sxs-lookup"><span data-stu-id="d48f1-153">Inventory object</span></span></td>
<td><span data-ttu-id="d48f1-154">C</span><span class="sxs-lookup"><span data-stu-id="d48f1-154">A</span></span></td>
<td><span data-ttu-id="d48f1-155">1</span><span class="sxs-lookup"><span data-stu-id="d48f1-155">1</span></span></td>
<td><span data-ttu-id="d48f1-156">11</span><span class="sxs-lookup"><span data-stu-id="d48f1-156">11</span></span></td>
<td><span data-ttu-id="d48f1-157">B2</span><span class="sxs-lookup"><span data-stu-id="d48f1-157">B2</span></span></td>
<td><span data-ttu-id="d48f1-158">50</span><span class="sxs-lookup"><span data-stu-id="d48f1-158">50</span></span></td>
<td><span data-ttu-id="d48f1-159">Periodos</span><span class="sxs-lookup"><span data-stu-id="d48f1-159">Pcs.</span></span></td>
<td><p><span data-ttu-id="d48f1-160">600,00 $</span><span class="sxs-lookup"><span data-stu-id="d48f1-160">$600.00</span></span></p></td>
<td><p><span data-ttu-id="d48f1-161">12,00 $</span><span class="sxs-lookup"><span data-stu-id="d48f1-161">$12.00</span></span></p></td>
</tr>
</tbody>
</table>



<a name="additional-resources"></a><span data-ttu-id="d48f1-162">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="d48f1-162">Additional resources</span></span>
--------

[<span data-ttu-id="d48f1-163">Objetos de coste</span><span class="sxs-lookup"><span data-stu-id="d48f1-163">Cost objects</span></span>](cost-object.md)

[<span data-ttu-id="d48f1-164">Entradas de costes</span><span class="sxs-lookup"><span data-stu-id="d48f1-164">Cost entries</span></span>](cost-entries.md)

[<span data-ttu-id="d48f1-165">Novedades y cambios</span><span class="sxs-lookup"><span data-stu-id="d48f1-165">What's new and changed</span></span>](../../fin-and-ops/get-started/whats-new-changed.md)



