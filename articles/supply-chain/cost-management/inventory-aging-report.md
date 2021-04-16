---
title: Ejemplos de informes de antigüedad de inventario y lógica
description: Este tema presenta algunos ejemplos que muestran cómo interpretar los resultados de un informe de antigüedad del inventario.
author: AndersGirke
ms.date: 5/29/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventAgingStorage, InventAgingStorageChart, InventAgingStorageDetails
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2020-5-29
ms.dyn365.ops.version: ''
ms.openlocfilehash: edc974bcbd72ef62438fd6271a6fd0e56143f976
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5821594"
---
# <a name="inventory-aging-report-examples-and-logic"></a><span data-ttu-id="f4baf-103">Ejemplos de informes de antigüedad de inventario y lógica</span><span class="sxs-lookup"><span data-stu-id="f4baf-103">Inventory aging report examples and logic</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f4baf-104">Este tema presenta algunos ejemplos que muestran cómo interpretar los resultados de un informe de **antigüedad del inventario**.</span><span class="sxs-lookup"><span data-stu-id="f4baf-104">This topic presents some examples that show how to interpret the results of an **Inventory aging** report.</span></span> <span data-ttu-id="f4baf-105">Este informe clasifica la cantidad disponible y los valores de inventario para un artículo seleccionado o grupo de artículos en varios períodos.</span><span class="sxs-lookup"><span data-stu-id="f4baf-105">This report categorizes on-hand quantity and inventory values for a selected item or item group into several period buckets.</span></span> <span data-ttu-id="f4baf-106">Este tema también muestra la lógica interna del informe.</span><span class="sxs-lookup"><span data-stu-id="f4baf-106">This topic also shows the internal logic of the report.</span></span>

<span data-ttu-id="f4baf-107">Los ejemplos en este tema muestran los resultados que se presentan en un informe de **antigüedad de inventario** estándar.</span><span class="sxs-lookup"><span data-stu-id="f4baf-107">The examples in this topic show results that are presented on a standard **Inventory aging** report.</span></span> <span data-ttu-id="f4baf-108">Sin embargo, en general, le recomendamos que utilice la versión [Almacenamiento de informes de antigüedad de inventario](inventory-aging-report-storage.md) de este informe, especialmente cuando tiene muchos artículos y almacenes que deben procesarse.</span><span class="sxs-lookup"><span data-stu-id="f4baf-108">However, in general, we recommend that you use the [Inventory aging report storage](inventory-aging-report-storage.md) version of this report, especially when you have many items and warehouses that must be processed.</span></span> <span data-ttu-id="f4baf-109">El almacenamiento de informes de antigüedad de inventario guarda cada informe que genera, muestra los resultados como una página interactiva y un gráfico, y le permite exportar cualquier informe guardado.</span><span class="sxs-lookup"><span data-stu-id="f4baf-109">Inventory aging report storage saves each report that you generate, shows the results as an interactive page and a chart, and lets you export any saved report.</span></span>

## <a name="sample-data-that-is-used-in-these-examples"></a><span data-ttu-id="f4baf-110">Datos de muestra que se usan en estos ejemplos</span><span class="sxs-lookup"><span data-stu-id="f4baf-110">Sample data that is used in these examples</span></span>

<span data-ttu-id="f4baf-111">Los ejemplos de este tema se basan en los datos de muestra de transacciones de inventario que se describen en esta sección.</span><span class="sxs-lookup"><span data-stu-id="f4baf-111">The examples in this topic are based on the sample inventory transaction data that is described in this section.</span></span>

### <a name="storage-dimension-setup"></a><span data-ttu-id="f4baf-112">Configuración de la dimensión de almacenamiento</span><span class="sxs-lookup"><span data-stu-id="f4baf-112">Storage dimension setup</span></span>

<span data-ttu-id="f4baf-113">El sistema de ejemplo contiene la siguiente configuración de dimensiones de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="f4baf-113">The example system contains the following setup of storage dimensions.</span></span>

| <span data-ttu-id="f4baf-114">Nombre</span><span class="sxs-lookup"><span data-stu-id="f4baf-114">Name</span></span>      | <span data-ttu-id="f4baf-115">Activas</span><span class="sxs-lookup"><span data-stu-id="f4baf-115">Active</span></span> | <span data-ttu-id="f4baf-116">Inventario físico</span><span class="sxs-lookup"><span data-stu-id="f4baf-116">Physical inventory</span></span> | <span data-ttu-id="f4baf-117">Inventario financiero</span><span class="sxs-lookup"><span data-stu-id="f4baf-117">Financial inventory</span></span> |
|-----------|--------|--------------------|---------------------|
| <span data-ttu-id="f4baf-118">Sitio</span><span class="sxs-lookup"><span data-stu-id="f4baf-118">Site</span></span>      | <span data-ttu-id="f4baf-119">Sí</span><span class="sxs-lookup"><span data-stu-id="f4baf-119">Yes</span></span>    | <span data-ttu-id="f4baf-120">Sí</span><span class="sxs-lookup"><span data-stu-id="f4baf-120">Yes</span></span>                | <span data-ttu-id="f4baf-121">Sí</span><span class="sxs-lookup"><span data-stu-id="f4baf-121">Yes</span></span>                 |
| <span data-ttu-id="f4baf-122">Almacén</span><span class="sxs-lookup"><span data-stu-id="f4baf-122">Warehouse</span></span> | <span data-ttu-id="f4baf-123">Sí</span><span class="sxs-lookup"><span data-stu-id="f4baf-123">Yes</span></span>    | <span data-ttu-id="f4baf-124">Sí</span><span class="sxs-lookup"><span data-stu-id="f4baf-124">Yes</span></span>                | <span data-ttu-id="f4baf-125">Nº</span><span class="sxs-lookup"><span data-stu-id="f4baf-125">No</span></span>                  |

### <a name="inventory-model"></a><span data-ttu-id="f4baf-126">Modelo de inventario</span><span class="sxs-lookup"><span data-stu-id="f4baf-126">Inventory model</span></span>

<span data-ttu-id="f4baf-127">Para el sistema de ejemplo, el modelo de inventario para los productos publicados es *FIFO*, y la configuración de **Precio de coste** para el modelo de inventario es *Incluir valor físico*.</span><span class="sxs-lookup"><span data-stu-id="f4baf-127">For the example system, the inventory model for the released products is *FIFO*, and the **Cost price** setting for the inventory model is *Include physical value*.</span></span>

### <a name="inventory-transactions"></a><span data-ttu-id="f4baf-128">Transacciones de inventario</span><span class="sxs-lookup"><span data-stu-id="f4baf-128">Inventory transactions</span></span>

<span data-ttu-id="f4baf-129">El sistema de ejemplo contiene las siguientes transacciones de inventario para un producto publicado que tiene el número de artículo *1000*.</span><span class="sxs-lookup"><span data-stu-id="f4baf-129">The example system contains the following inventory transactions for a released product that has the item number *1000*.</span></span>

| <span data-ttu-id="f4baf-130">Referencia</span><span class="sxs-lookup"><span data-stu-id="f4baf-130">Reference</span></span>      | <span data-ttu-id="f4baf-131">Sitio</span><span class="sxs-lookup"><span data-stu-id="f4baf-131">Site</span></span> | <span data-ttu-id="f4baf-132">Almacén</span><span class="sxs-lookup"><span data-stu-id="f4baf-132">Warehouse</span></span> | <span data-ttu-id="f4baf-133">Recepción</span><span class="sxs-lookup"><span data-stu-id="f4baf-133">Receipt</span></span>   | <span data-ttu-id="f4baf-134">Emitir</span><span class="sxs-lookup"><span data-stu-id="f4baf-134">Issue</span></span> | <span data-ttu-id="f4baf-135">Fecha física</span><span class="sxs-lookup"><span data-stu-id="f4baf-135">Physical date</span></span> | <span data-ttu-id="f4baf-136">Fecha financiera</span><span class="sxs-lookup"><span data-stu-id="f4baf-136">Financial date</span></span> | <span data-ttu-id="f4baf-137">Cantidad</span><span class="sxs-lookup"><span data-stu-id="f4baf-137">Quantity</span></span> | <span data-ttu-id="f4baf-138">Importe de coste</span><span class="sxs-lookup"><span data-stu-id="f4baf-138">Cost amount</span></span> | <span data-ttu-id="f4baf-139">Importe de coste físico</span><span class="sxs-lookup"><span data-stu-id="f4baf-139">Physical cost amount</span></span> |
|----------------|------|-----------|-----------|-------|---------------|----------------|----------|-------------|----------------------|
| <span data-ttu-id="f4baf-140">Pedido de compra</span><span class="sxs-lookup"><span data-stu-id="f4baf-140">Purchase order</span></span> | <span data-ttu-id="f4baf-141">1</span><span class="sxs-lookup"><span data-stu-id="f4baf-141">1</span></span>    | <span data-ttu-id="f4baf-142">11</span><span class="sxs-lookup"><span data-stu-id="f4baf-142">11</span></span>        | <span data-ttu-id="f4baf-143">Comprado</span><span class="sxs-lookup"><span data-stu-id="f4baf-143">Purchased</span></span> |       | <span data-ttu-id="f4baf-144">15 de marzo</span><span class="sxs-lookup"><span data-stu-id="f4baf-144">March 15</span></span>      | <span data-ttu-id="f4baf-145">15 de marzo</span><span class="sxs-lookup"><span data-stu-id="f4baf-145">March 15</span></span>       | <span data-ttu-id="f4baf-146">10</span><span class="sxs-lookup"><span data-stu-id="f4baf-146">10</span></span>       | <span data-ttu-id="f4baf-147">1.000</span><span class="sxs-lookup"><span data-stu-id="f4baf-147">1,000</span></span>       | <span data-ttu-id="f4baf-148">1.000</span><span class="sxs-lookup"><span data-stu-id="f4baf-148">1,000</span></span>                |
| <span data-ttu-id="f4baf-149">Pedido de compra</span><span class="sxs-lookup"><span data-stu-id="f4baf-149">Purchase order</span></span> | <span data-ttu-id="f4baf-150">2</span><span class="sxs-lookup"><span data-stu-id="f4baf-150">2</span></span>    | <span data-ttu-id="f4baf-151">21</span><span class="sxs-lookup"><span data-stu-id="f4baf-151">21</span></span>        | <span data-ttu-id="f4baf-152">Comprado</span><span class="sxs-lookup"><span data-stu-id="f4baf-152">Purchased</span></span> |       | <span data-ttu-id="f4baf-153">15 de marzo</span><span class="sxs-lookup"><span data-stu-id="f4baf-153">March 15</span></span>      | <span data-ttu-id="f4baf-154">15 de marzo</span><span class="sxs-lookup"><span data-stu-id="f4baf-154">March 15</span></span>       | <span data-ttu-id="f4baf-155">10</span><span class="sxs-lookup"><span data-stu-id="f4baf-155">10</span></span>       | <span data-ttu-id="f4baf-156">2,000</span><span class="sxs-lookup"><span data-stu-id="f4baf-156">2,000</span></span>       | <span data-ttu-id="f4baf-157">2,000</span><span class="sxs-lookup"><span data-stu-id="f4baf-157">2,000</span></span>                |
| <span data-ttu-id="f4baf-158">Pedido de compra</span><span class="sxs-lookup"><span data-stu-id="f4baf-158">Purchase order</span></span> | <span data-ttu-id="f4baf-159">1</span><span class="sxs-lookup"><span data-stu-id="f4baf-159">1</span></span>    | <span data-ttu-id="f4baf-160">11</span><span class="sxs-lookup"><span data-stu-id="f4baf-160">11</span></span>        | <span data-ttu-id="f4baf-161">Recibida</span><span class="sxs-lookup"><span data-stu-id="f4baf-161">Received</span></span>  |       | <span data-ttu-id="f4baf-162">15 de abril</span><span class="sxs-lookup"><span data-stu-id="f4baf-162">April 15</span></span>      |                | <span data-ttu-id="f4baf-163">5</span><span class="sxs-lookup"><span data-stu-id="f4baf-163">5</span></span>        |             | <span data-ttu-id="f4baf-164">375</span><span class="sxs-lookup"><span data-stu-id="f4baf-164">375</span></span>                  |
| <span data-ttu-id="f4baf-165">Orden de transferencia</span><span class="sxs-lookup"><span data-stu-id="f4baf-165">Transfer order</span></span> | <span data-ttu-id="f4baf-166">1</span><span class="sxs-lookup"><span data-stu-id="f4baf-166">1</span></span>    | <span data-ttu-id="f4baf-167">11</span><span class="sxs-lookup"><span data-stu-id="f4baf-167">11</span></span>        |           | <span data-ttu-id="f4baf-168">Vendido</span><span class="sxs-lookup"><span data-stu-id="f4baf-168">Sold</span></span>  | <span data-ttu-id="f4baf-169">mayo de 2</span><span class="sxs-lookup"><span data-stu-id="f4baf-169">May 2</span></span>         | <span data-ttu-id="f4baf-170">mayo de 2</span><span class="sxs-lookup"><span data-stu-id="f4baf-170">May 2</span></span>          | <span data-ttu-id="f4baf-171">-5</span><span class="sxs-lookup"><span data-stu-id="f4baf-171">-5</span></span>       | <span data-ttu-id="f4baf-172">-458,33</span><span class="sxs-lookup"><span data-stu-id="f4baf-172">-458.33</span></span>     | <span data-ttu-id="f4baf-173">-458,33</span><span class="sxs-lookup"><span data-stu-id="f4baf-173">-458.33</span></span>              |
| <span data-ttu-id="f4baf-174">Orden de transferencia</span><span class="sxs-lookup"><span data-stu-id="f4baf-174">Transfer order</span></span> | <span data-ttu-id="f4baf-175">1</span><span class="sxs-lookup"><span data-stu-id="f4baf-175">1</span></span>    | <span data-ttu-id="f4baf-176">12</span><span class="sxs-lookup"><span data-stu-id="f4baf-176">12</span></span>        | <span data-ttu-id="f4baf-177">Comprado</span><span class="sxs-lookup"><span data-stu-id="f4baf-177">Purchased</span></span> |       | <span data-ttu-id="f4baf-178">mayo de 2</span><span class="sxs-lookup"><span data-stu-id="f4baf-178">May 2</span></span>         | <span data-ttu-id="f4baf-179">mayo de 2</span><span class="sxs-lookup"><span data-stu-id="f4baf-179">May 2</span></span>          | <span data-ttu-id="f4baf-180">5</span><span class="sxs-lookup"><span data-stu-id="f4baf-180">5</span></span>        | <span data-ttu-id="f4baf-181">458.33</span><span class="sxs-lookup"><span data-stu-id="f4baf-181">458.33</span></span>      | <span data-ttu-id="f4baf-182">458.33</span><span class="sxs-lookup"><span data-stu-id="f4baf-182">458.33</span></span>               |
| <span data-ttu-id="f4baf-183">Pedido de ventas</span><span class="sxs-lookup"><span data-stu-id="f4baf-183">Sales order</span></span>    | <span data-ttu-id="f4baf-184">1</span><span class="sxs-lookup"><span data-stu-id="f4baf-184">1</span></span>    | <span data-ttu-id="f4baf-185">12</span><span class="sxs-lookup"><span data-stu-id="f4baf-185">12</span></span>        |           | <span data-ttu-id="f4baf-186">Vendido</span><span class="sxs-lookup"><span data-stu-id="f4baf-186">Sold</span></span>  | <span data-ttu-id="f4baf-187">mayo de 3</span><span class="sxs-lookup"><span data-stu-id="f4baf-187">May 3</span></span>         | <span data-ttu-id="f4baf-188">mayo de 3</span><span class="sxs-lookup"><span data-stu-id="f4baf-188">May 3</span></span>          | <span data-ttu-id="f4baf-189">-1</span><span class="sxs-lookup"><span data-stu-id="f4baf-189">-1</span></span>       | <span data-ttu-id="f4baf-190">-91,67</span><span class="sxs-lookup"><span data-stu-id="f4baf-190">-91.67</span></span>      | <span data-ttu-id="f4baf-191">-91,67</span><span class="sxs-lookup"><span data-stu-id="f4baf-191">-91.67</span></span>               |

## <a name="how-quantities-and-amounts-in-each-period-bucket-are-calculated"></a><span data-ttu-id="f4baf-192">Cómo se calculan las cantidades y los importes en cada cubo de períodos</span><span class="sxs-lookup"><span data-stu-id="f4baf-192">How quantities and amounts in each period bucket are calculated</span></span>

<span data-ttu-id="f4baf-193">Al utilizar los datos de ejemplo que se describen en las secciones anteriores, podrá ejecutar un informe de **antigüedad de inventario** que tiene la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="f4baf-193">By using the sample data that is described in the previous sections, you can run an **Inventory aging** report that has the following settings:</span></span>

- <span data-ttu-id="f4baf-194">**A partir de la fecha:** *9 de mayo de 2020*</span><span class="sxs-lookup"><span data-stu-id="f4baf-194">**As of date:** *May 9, 2020*</span></span>
- <span data-ttu-id="f4baf-195">**Sitio:** *Ver*</span><span class="sxs-lookup"><span data-stu-id="f4baf-195">**Site:** *View*</span></span>
- <span data-ttu-id="f4baf-196">**Almacén**: *No*</span><span class="sxs-lookup"><span data-stu-id="f4baf-196">**Warehouse:** *No*</span></span>
- <span data-ttu-id="f4baf-197">**Número de artículo:** *Total*</span><span class="sxs-lookup"><span data-stu-id="f4baf-197">**Item number:** *Total*</span></span>
- <span data-ttu-id="f4baf-198">**Período de antigüedad:** establezca este campo para generar depósitos mensuales.</span><span class="sxs-lookup"><span data-stu-id="f4baf-198">**Aging period:** Set this field to generate monthly buckets.</span></span>

<span data-ttu-id="f4baf-199">En este caso, el contenido del informe generado se parecerá al siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="f4baf-199">In this case, the content of the report that is generated will resemble the following example.</span></span>

<table>
<thead>
<tr>
    <th rowspan="2"><span data-ttu-id="f4baf-200">código de artículo</span><span class="sxs-lookup"><span data-stu-id="f4baf-200">Item number</span></span></th>
    <th rowspan="2"><span data-ttu-id="f4baf-201">Sitio</span><span class="sxs-lookup"><span data-stu-id="f4baf-201">Site</span></span></th>
    <th rowspan="2"><span data-ttu-id="f4baf-202">Cantidad disponible</span><span class="sxs-lookup"><span data-stu-id="f4baf-202">On-hand quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="f4baf-203">Valor disponible</span><span class="sxs-lookup"><span data-stu-id="f4baf-203">On-hand value</span></span></th>
    <th rowspan="2"><span data-ttu-id="f4baf-204">Cantidad de valor de inventario</span><span class="sxs-lookup"><span data-stu-id="f4baf-204">Inventory value quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="f4baf-205">Valor de inventario</span><span class="sxs-lookup"><span data-stu-id="f4baf-205">Inventory value</span></span></th>
    <th rowspan="2"><span data-ttu-id="f4baf-206">Coste unitario promedio</span><span class="sxs-lookup"><span data-stu-id="f4baf-206">Average unit cost</span></span></th>
    <th colspan="2"><span data-ttu-id="f4baf-207">5/8/2020 - 5/1/2020</span><span class="sxs-lookup"><span data-stu-id="f4baf-207">5/8/2020 - 5/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="f4baf-208">4/30/2020 - 4/1/2020</span><span class="sxs-lookup"><span data-stu-id="f4baf-208">4/30/2020 - 4/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="f4baf-209">3/31/2020 - 3/1/2020</span><span class="sxs-lookup"><span data-stu-id="f4baf-209">3/31/2020 - 3/1/2020</span></span></th>
</tr>
<tr>
    <th><span data-ttu-id="f4baf-210">P1:Cantidad</span><span class="sxs-lookup"><span data-stu-id="f4baf-210">P1:Quantity</span></span></th>
    <th><span data-ttu-id="f4baf-211">P1:Importe</span><span class="sxs-lookup"><span data-stu-id="f4baf-211">P1:Amount</span></span></th>
    <th><span data-ttu-id="f4baf-212">P2:Cantidad</span><span class="sxs-lookup"><span data-stu-id="f4baf-212">P2:Quantity</span></span></th>
    <th><span data-ttu-id="f4baf-213">P2:Importe</span><span class="sxs-lookup"><span data-stu-id="f4baf-213">P2:Amount</span></span></th>
    <th><span data-ttu-id="f4baf-214">P3:Cantidad</span><span class="sxs-lookup"><span data-stu-id="f4baf-214">P3:Quantity</span></span></th>
    <th><span data-ttu-id="f4baf-215">P3:Importe</span><span class="sxs-lookup"><span data-stu-id="f4baf-215">P3:Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
    <td><span data-ttu-id="f4baf-216">1000</span><span class="sxs-lookup"><span data-stu-id="f4baf-216">1000</span></span></td>
    <td><span data-ttu-id="f4baf-217">1</span><span class="sxs-lookup"><span data-stu-id="f4baf-217">1</span></span></td>
    <td><span data-ttu-id="f4baf-218">14</span><span class="sxs-lookup"><span data-stu-id="f4baf-218">14</span></span></td>
    <td><span data-ttu-id="f4baf-219">1,283.33</span><span class="sxs-lookup"><span data-stu-id="f4baf-219">1,283.33</span></span></td>
    <td><span data-ttu-id="f4baf-220">14</span><span class="sxs-lookup"><span data-stu-id="f4baf-220">14</span></span></td>
    <td><span data-ttu-id="f4baf-221">1,283.33</span><span class="sxs-lookup"><span data-stu-id="f4baf-221">1,283.33</span></span></td>
    <td><span data-ttu-id="f4baf-222">91.67</span><span class="sxs-lookup"><span data-stu-id="f4baf-222">91.67</span></span></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="f4baf-223">5.00</span><span class="sxs-lookup"><span data-stu-id="f4baf-223">5.00</span></span></td>
    <td><span data-ttu-id="f4baf-224">458.33</span><span class="sxs-lookup"><span data-stu-id="f4baf-224">458.33</span></span></td>
    <td><span data-ttu-id="f4baf-225">9.00</span><span class="sxs-lookup"><span data-stu-id="f4baf-225">9.00</span></span></td>
    <td><span data-ttu-id="f4baf-226">825.00</span><span class="sxs-lookup"><span data-stu-id="f4baf-226">825.00</span></span></td>
</tr>
<tr>
    <td><span data-ttu-id="f4baf-227">1000</span><span class="sxs-lookup"><span data-stu-id="f4baf-227">1000</span></span></td>
    <td><span data-ttu-id="f4baf-228">2</span><span class="sxs-lookup"><span data-stu-id="f4baf-228">2</span></span></td>
    <td><span data-ttu-id="f4baf-229">10</span><span class="sxs-lookup"><span data-stu-id="f4baf-229">10</span></span></td>
    <td><span data-ttu-id="f4baf-230">2,000.00</span><span class="sxs-lookup"><span data-stu-id="f4baf-230">2,000.00</span></span></td>
    <td><span data-ttu-id="f4baf-231">10</span><span class="sxs-lookup"><span data-stu-id="f4baf-231">10</span></span></td>
    <td><span data-ttu-id="f4baf-232">2,000.00</span><span class="sxs-lookup"><span data-stu-id="f4baf-232">2,000.00</span></span></td>
    <td><span data-ttu-id="f4baf-233">200.00</span><span class="sxs-lookup"><span data-stu-id="f4baf-233">200.00</span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="f4baf-234">10,00</span><span class="sxs-lookup"><span data-stu-id="f4baf-234">10.00</span></span></td>
    <td><span data-ttu-id="f4baf-235">2,000.00</span><span class="sxs-lookup"><span data-stu-id="f4baf-235">2,000.00</span></span></td>
</tr>
</tbody>
<tfoot>
<tr>
    <td><span data-ttu-id="f4baf-236"><strong>1000 Totales</strong></span><span class="sxs-lookup"><span data-stu-id="f4baf-236"><strong>1000 Totals</strong></span></span></td>
    <td></td>
    <td><span data-ttu-id="f4baf-237"><strong>24.00</strong></span><span class="sxs-lookup"><span data-stu-id="f4baf-237"><strong>24.00</strong></span></span></td>
    <td><span data-ttu-id="f4baf-238"><strong>3,283.33</strong></span><span class="sxs-lookup"><span data-stu-id="f4baf-238"><strong>3,283.33</strong></span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="f4baf-239"><strong>5.00</strong></span><span class="sxs-lookup"><span data-stu-id="f4baf-239"><strong>5.00</strong></span></span></td>
    <td><span data-ttu-id="f4baf-240"><strong>458.33</strong></span><span class="sxs-lookup"><span data-stu-id="f4baf-240"><strong>458.33</strong></span></span></td>
    <td><span data-ttu-id="f4baf-241"><strong>19</strong></span><span class="sxs-lookup"><span data-stu-id="f4baf-241"><strong>19</strong></span></span></td>
    <td><span data-ttu-id="f4baf-242"><strong>2,825.00</strong></span><span class="sxs-lookup"><span data-stu-id="f4baf-242"><strong>2,825.00</strong></span></span></td>
</tr>
</tfoot>
</table>

<span data-ttu-id="f4baf-243">Tenga en cuenta los siguientes detalles en este informe de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f4baf-243">Note the following details in this example report:</span></span>

- <span data-ttu-id="f4baf-244">Los valores **Cantidad de valor de inventario**, **Valor de inventario** y **Coste unitario promedio** que se muestran en el informe son valores para la dimensión de inventario financiero (**Sitio**, en este caso).</span><span class="sxs-lookup"><span data-stu-id="f4baf-244">The **Inventory value quantity**, **Inventory value**, and **Average unit cost** values that are shown on the report are values for the financial inventory dimension (**Site**, in this case).</span></span>

    <span data-ttu-id="f4baf-245">Por ejemplo, para el sitio 1, el informe muestra la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="f4baf-245">For example, for site 1, the report shows the following information:</span></span>

    - <span data-ttu-id="f4baf-246">El valor **Cantidad de valor de inventario** es *14* (= 10 + 5 - 5 + 5 - 1).</span><span class="sxs-lookup"><span data-stu-id="f4baf-246">The **Inventory value quantity** value is *14* (= 10 + 5 – 5 + 5 – 1).</span></span>
    - <span data-ttu-id="f4baf-247">El valor **Cantidad de valor de inventario** es *1283,33* (= 1000 + 375 - 458,33 + 458,33 - 91,67).</span><span class="sxs-lookup"><span data-stu-id="f4baf-247">The **Inventory value** value is *1,283.33* (= 1,000 + 375 – 458.33 + 458.33 – 91.67).</span></span>
    - <span data-ttu-id="f4baf-248">El valor **Coste unitario promedio** es *91,67*.</span><span class="sxs-lookup"><span data-stu-id="f4baf-248">The **Average unit cost** value is *91.67*.</span></span>
    - <span data-ttu-id="f4baf-249">El valor **Valor disponible** y el valor **Importe** en cada período se calcula utilizando el valor **Coste unitario promedio**.</span><span class="sxs-lookup"><span data-stu-id="f4baf-249">The **On-hand value** value and the **Amount** value in each period bucket are calculated by using the **Average unit cost** value.</span></span>

- <span data-ttu-id="f4baf-250">El informe determina la cantidad disponible para cada cubo de períodos resumiendo la cantidad de inventario total recibida para cada cubo de períodos.</span><span class="sxs-lookup"><span data-stu-id="f4baf-250">The report determines the on-hand quantity for each period bucket by summarizing the total received inventory quantity for each period bucket.</span></span> <span data-ttu-id="f4baf-251">Luego aplica el principio de primero en entrar, primero en salir (FIFO) para deducir la cantidad total emitida, independientemente del modelo de inventario que usan los artículos.</span><span class="sxs-lookup"><span data-stu-id="f4baf-251">It then applies the first in, first out (FIFO) principle to deduct the total issued quantity, regardless of the inventory model that the items use.</span></span>

<span data-ttu-id="f4baf-252">Si ejecuta el mismo informe nuevamente, pero esta vez configura los campos **Sitio** y **Almacén** en *Ver*, el nuevo informe se parecerá al siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="f4baf-252">If you run the same report again, but this time you set both the **Site** and **Warehouse** fields to *View*, the new report will resemble the following example.</span></span>

<table>
<thead>
<tr>
    <th rowspan="2"><span data-ttu-id="f4baf-253">código de artículo</span><span class="sxs-lookup"><span data-stu-id="f4baf-253">Item number</span></span></th>
    <th rowspan="2"><span data-ttu-id="f4baf-254">Sitio</span><span class="sxs-lookup"><span data-stu-id="f4baf-254">Site</span></span></th>
    <th rowspan="2"><span data-ttu-id="f4baf-255">Almacén</span><span class="sxs-lookup"><span data-stu-id="f4baf-255">Warehouse</span></span></th>
    <th rowspan="2"><span data-ttu-id="f4baf-256">Cantidad disponible</span><span class="sxs-lookup"><span data-stu-id="f4baf-256">On-hand quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="f4baf-257">Valor disponible</span><span class="sxs-lookup"><span data-stu-id="f4baf-257">On-hand value</span></span></th>
    <th rowspan="2"><span data-ttu-id="f4baf-258">Cantidad de valor de inventario</span><span class="sxs-lookup"><span data-stu-id="f4baf-258">Inventory value quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="f4baf-259">Valor de inventario</span><span class="sxs-lookup"><span data-stu-id="f4baf-259">Inventory value</span></span></th>
    <th rowspan="2"><span data-ttu-id="f4baf-260">Coste unitario promedio</span><span class="sxs-lookup"><span data-stu-id="f4baf-260">Average unit cost</span></span></th>
    <th colspan="2"><span data-ttu-id="f4baf-261">5/8/2020 - 5/1/2020</span><span class="sxs-lookup"><span data-stu-id="f4baf-261">5/8/2020 - 5/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="f4baf-262">4/30/2020 - 4/1/2020</span><span class="sxs-lookup"><span data-stu-id="f4baf-262">4/30/2020 - 4/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="f4baf-263">3/31/2020 - 3/1/2020</span><span class="sxs-lookup"><span data-stu-id="f4baf-263">3/31/2020 - 3/1/2020</span></span></th>
</tr>
<tr>
    <th><span data-ttu-id="f4baf-264">P1:Cantidad</span><span class="sxs-lookup"><span data-stu-id="f4baf-264">P1:Quantity</span></span></th>
    <th><span data-ttu-id="f4baf-265">P1:Importe</span><span class="sxs-lookup"><span data-stu-id="f4baf-265">P1:Amount</span></span></th>
    <th><span data-ttu-id="f4baf-266">P2:Cantidad</span><span class="sxs-lookup"><span data-stu-id="f4baf-266">P2:Quantity</span></span></th>
    <th><span data-ttu-id="f4baf-267">P2:Importe</span><span class="sxs-lookup"><span data-stu-id="f4baf-267">P2:Amount</span></span></th>
    <th><span data-ttu-id="f4baf-268">P3:Cantidad</span><span class="sxs-lookup"><span data-stu-id="f4baf-268">P3:Quantity</span></span></th>
    <th><span data-ttu-id="f4baf-269">P3:Importe</span><span class="sxs-lookup"><span data-stu-id="f4baf-269">P3:Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
    <td><span data-ttu-id="f4baf-270">1000</span><span class="sxs-lookup"><span data-stu-id="f4baf-270">1000</span></span></td>
    <td><span data-ttu-id="f4baf-271">1</span><span class="sxs-lookup"><span data-stu-id="f4baf-271">1</span></span></td>
    <td><span data-ttu-id="f4baf-272">11</span><span class="sxs-lookup"><span data-stu-id="f4baf-272">11</span></span></td>
    <td><span data-ttu-id="f4baf-273">10</span><span class="sxs-lookup"><span data-stu-id="f4baf-273">10</span></span></td>
    <td><span data-ttu-id="f4baf-274">916.67</span><span class="sxs-lookup"><span data-stu-id="f4baf-274">916.67</span></span></td>
    <td><span data-ttu-id="f4baf-275">14</span><span class="sxs-lookup"><span data-stu-id="f4baf-275">14</span></span></td>
    <td><span data-ttu-id="f4baf-276">1,283.33</span><span class="sxs-lookup"><span data-stu-id="f4baf-276">1,283.33</span></span></td>
    <td><span data-ttu-id="f4baf-277">91.67</span><span class="sxs-lookup"><span data-stu-id="f4baf-277">91.67</span></span></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="f4baf-278">5.00</span><span class="sxs-lookup"><span data-stu-id="f4baf-278">5.00</span></span></td>
    <td><span data-ttu-id="f4baf-279">458.33</span><span class="sxs-lookup"><span data-stu-id="f4baf-279">458.33</span></span></td>
    <td><span data-ttu-id="f4baf-280">5.00</span><span class="sxs-lookup"><span data-stu-id="f4baf-280">5.00</span></span></td>
    <td><span data-ttu-id="f4baf-281">458.33</span><span class="sxs-lookup"><span data-stu-id="f4baf-281">458.33</span></span></td>
</tr>
<tr>
    <td><span data-ttu-id="f4baf-282">1000</span><span class="sxs-lookup"><span data-stu-id="f4baf-282">1000</span></span></td>
    <td><span data-ttu-id="f4baf-283">1</span><span class="sxs-lookup"><span data-stu-id="f4baf-283">1</span></span></td>
    <td><span data-ttu-id="f4baf-284">12</span><span class="sxs-lookup"><span data-stu-id="f4baf-284">12</span></span></td>
    <td><span data-ttu-id="f4baf-285">4</span><span class="sxs-lookup"><span data-stu-id="f4baf-285">4</span></span></td>
    <td><span data-ttu-id="f4baf-286">366.67</span><span class="sxs-lookup"><span data-stu-id="f4baf-286">366.67</span></span></td>
    <td><span data-ttu-id="f4baf-287">14</span><span class="sxs-lookup"><span data-stu-id="f4baf-287">14</span></span></td>
    <td><span data-ttu-id="f4baf-288">1,283.33</span><span class="sxs-lookup"><span data-stu-id="f4baf-288">1,283.33</span></span></td>
    <td><span data-ttu-id="f4baf-289">91.67</span><span class="sxs-lookup"><span data-stu-id="f4baf-289">91.67</span></span></td>
    <td><span data-ttu-id="f4baf-290">4.00</span><span class="sxs-lookup"><span data-stu-id="f4baf-290">4.00</span></span></td>
    <td><span data-ttu-id="f4baf-291">366.67</span><span class="sxs-lookup"><span data-stu-id="f4baf-291">366.67</span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
</tr>
<tr>
    <td><span data-ttu-id="f4baf-292">1000</span><span class="sxs-lookup"><span data-stu-id="f4baf-292">1000</span></span></td>
    <td><span data-ttu-id="f4baf-293">2</span><span class="sxs-lookup"><span data-stu-id="f4baf-293">2</span></span></td>
    <td></td>
    <td><span data-ttu-id="f4baf-294">10</span><span class="sxs-lookup"><span data-stu-id="f4baf-294">10</span></span></td>
    <td><span data-ttu-id="f4baf-295">2,000.00</span><span class="sxs-lookup"><span data-stu-id="f4baf-295">2,000.00</span></span></td>
    <td><span data-ttu-id="f4baf-296">10</span><span class="sxs-lookup"><span data-stu-id="f4baf-296">10</span></span></td>
    <td><span data-ttu-id="f4baf-297">2,000.00</span><span class="sxs-lookup"><span data-stu-id="f4baf-297">2,000.00</span></span></td>
    <td><span data-ttu-id="f4baf-298">200.00</span><span class="sxs-lookup"><span data-stu-id="f4baf-298">200.00</span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="f4baf-299">10,00</span><span class="sxs-lookup"><span data-stu-id="f4baf-299">10.00</span></span></td>
    <td><span data-ttu-id="f4baf-300">2,000.00</span><span class="sxs-lookup"><span data-stu-id="f4baf-300">2,000.00</span></span></td>
</tr>
</tbody>
<tfoot>
<tr>
    <td><span data-ttu-id="f4baf-301"><strong>1000 Totales</strong></span><span class="sxs-lookup"><span data-stu-id="f4baf-301"><strong>1000 Totals</strong></span></span></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="f4baf-302"><strong>24.00</strong></span><span class="sxs-lookup"><span data-stu-id="f4baf-302"><strong>24.00</strong></span></span></td>
    <td><span data-ttu-id="f4baf-303"><strong>3,283.33</strong></span><span class="sxs-lookup"><span data-stu-id="f4baf-303"><strong>3,283.33</strong></span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="f4baf-304"><strong>4.00</strong></span><span class="sxs-lookup"><span data-stu-id="f4baf-304"><strong>4.00</strong></span></span></td>
    <td><span data-ttu-id="f4baf-305"><strong>366.67</strong></span><span class="sxs-lookup"><span data-stu-id="f4baf-305"><strong>366.67</strong></span></span></td>
    <td><span data-ttu-id="f4baf-306"><strong>5.00</strong></span><span class="sxs-lookup"><span data-stu-id="f4baf-306"><strong>5.00</strong></span></span></td>
    <td><span data-ttu-id="f4baf-307"><strong>458.33</strong></span><span class="sxs-lookup"><span data-stu-id="f4baf-307"><strong>458.33</strong></span></span></td>
    <td><span data-ttu-id="f4baf-308"><strong>15</strong></span><span class="sxs-lookup"><span data-stu-id="f4baf-308"><strong>15</strong></span></span></td>
    <td><span data-ttu-id="f4baf-309"><strong>2,458.33</strong></span><span class="sxs-lookup"><span data-stu-id="f4baf-309"><strong>2,458.33</strong></span></span></td>
</tr>
</tfoot>
</table>

<span data-ttu-id="f4baf-310">Esta vez, el sitio 1 se divide en dos filas, una para el almacén 11 y otra para el almacén 12.</span><span class="sxs-lookup"><span data-stu-id="f4baf-310">This time, site 1 is split into two rows, one for warehouse 11 and one for warehouse 12.</span></span> <span data-ttu-id="f4baf-311">Sin embargo, los valores **Cantidad de valor de inventario**, **Valor de inventario** y **Coste unitario promedio** son los mismos porque **Almacén** no es una dimensión de inventario financiera.</span><span class="sxs-lookup"><span data-stu-id="f4baf-311">However, the **Inventory value quantity**, **Inventory value**, and **Average unit cost** values are the same, because **Warehouse** isn't a financial inventory dimension.</span></span>

<span data-ttu-id="f4baf-312">Además, observe que la distribución de cantidad del sitio 1 es diferente.</span><span class="sxs-lookup"><span data-stu-id="f4baf-312">Additionally, notice that the quantity distribution of site 1 is different.</span></span> <span data-ttu-id="f4baf-313">En el primer informe que ejecutó, el sistema ignoró la orden de transferencia que ocurrió en el mismo sitio y dedujo la cantidad de la factura de venta del cubo de periodos **31/03/2020 - 1/3/2020** en el sitio 1.</span><span class="sxs-lookup"><span data-stu-id="f4baf-313">In the first report that you ran, the system ignored the transfer order that occurred in the same site and deducted the quantity of the sales invoice from the **3/31/2020 - 3/1/2020** period bucket in site 1.</span></span> <span data-ttu-id="f4baf-314">Sin embargo, en el nuevo informe, el sistema deduce la cantidad de la factura de venta del cubo de períodos **8/05/2020 - 5/1/2020** en el almacén 12.</span><span class="sxs-lookup"><span data-stu-id="f4baf-314">However, in the new report, the system deducts the quantity of the sales invoice from the **5/8/2020 - 5/1/2020** period bucket in warehouse 12.</span></span>

## <a name="effects-of-inventory-closing"></a><span data-ttu-id="f4baf-315">Efectos del cierre del inventario</span><span class="sxs-lookup"><span data-stu-id="f4baf-315">Effects of inventory closing</span></span>

<span data-ttu-id="f4baf-316">Si ejecuta el cierre de inventario para mayo y luego vuelve a ejecutar el informe anterior, pero configura el campo **A partir de la fecha** en el *31 de mayo de 2020*, verá los siguientes resultados:</span><span class="sxs-lookup"><span data-stu-id="f4baf-316">If you run the inventory closing for May and then run the previous report again, but you set the **As of date** field to *May 31, 2020*, you will notice the following results:</span></span>

- <span data-ttu-id="f4baf-317">Los valores **Valor de inventario** y **Coste unitario promedio** se actualizan.</span><span class="sxs-lookup"><span data-stu-id="f4baf-317">The **Inventory value** and **Average unit cost** values are updated.</span></span>
- <span data-ttu-id="f4baf-318">El valor **Valor disponible** y todos los valores de **Importe** en cada cubo de períodos se actualizan en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="f4baf-318">The **On-hand value** value and all the **Amount** values in every period bucket are updated accordingly.</span></span>

<span data-ttu-id="f4baf-319">El informe nuevo se parecerá al ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="f4baf-319">The new report will resemble the following example.</span></span>

<table>
<thead>
<tr>
    <th rowspan="2"><span data-ttu-id="f4baf-320">código de artículo</span><span class="sxs-lookup"><span data-stu-id="f4baf-320">Item number</span></span></th>
    <th rowspan="2"><span data-ttu-id="f4baf-321">Sitio</span><span class="sxs-lookup"><span data-stu-id="f4baf-321">Site</span></span></th>
    <th rowspan="2"><span data-ttu-id="f4baf-322">Almacén</span><span class="sxs-lookup"><span data-stu-id="f4baf-322">Warehouse</span></span></th>
    <th rowspan="2"><span data-ttu-id="f4baf-323">Cantidad disponible</span><span class="sxs-lookup"><span data-stu-id="f4baf-323">On-hand quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="f4baf-324">Valor disponible</span><span class="sxs-lookup"><span data-stu-id="f4baf-324">On-hand value</span></span></th>
    <th rowspan="2"><span data-ttu-id="f4baf-325">Cantidad de valor de inventario</span><span class="sxs-lookup"><span data-stu-id="f4baf-325">Inventory value quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="f4baf-326">Valor de inventario</span><span class="sxs-lookup"><span data-stu-id="f4baf-326">Inventory value</span></span></th>
    <th rowspan="2"><span data-ttu-id="f4baf-327">Coste unitario promedio</span><span class="sxs-lookup"><span data-stu-id="f4baf-327">Average unit cost</span></span></th>
    <th colspan="2"><span data-ttu-id="f4baf-328">5/31/2020 - 5/1/2020</span><span class="sxs-lookup"><span data-stu-id="f4baf-328">5/31/2020 - 5/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="f4baf-329">4/30/2020 - 4/1/2020</span><span class="sxs-lookup"><span data-stu-id="f4baf-329">4/30/2020 - 4/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="f4baf-330">3/31/2020 - 3/1/2020</span><span class="sxs-lookup"><span data-stu-id="f4baf-330">3/31/2020 - 3/1/2020</span></span></th>
</tr>
<tr>
    <th><span data-ttu-id="f4baf-331">P1:Cantidad</span><span class="sxs-lookup"><span data-stu-id="f4baf-331">P1:Quantity</span></span></th>
    <th><span data-ttu-id="f4baf-332">P1:Importe</span><span class="sxs-lookup"><span data-stu-id="f4baf-332">P1:Amount</span></span></th>
    <th><span data-ttu-id="f4baf-333">P2:Cantidad</span><span class="sxs-lookup"><span data-stu-id="f4baf-333">P2:Quantity</span></span></th>
    <th><span data-ttu-id="f4baf-334">P2:Importe</span><span class="sxs-lookup"><span data-stu-id="f4baf-334">P2:Amount</span></span></th>
    <th><span data-ttu-id="f4baf-335">P3:Cantidad</span><span class="sxs-lookup"><span data-stu-id="f4baf-335">P3:Quantity</span></span></th>
    <th><span data-ttu-id="f4baf-336">P3:Importe</span><span class="sxs-lookup"><span data-stu-id="f4baf-336">P3:Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
    <td><span data-ttu-id="f4baf-337">1000</span><span class="sxs-lookup"><span data-stu-id="f4baf-337">1000</span></span></td>
    <td><span data-ttu-id="f4baf-338">1</span><span class="sxs-lookup"><span data-stu-id="f4baf-338">1</span></span></td>
    <td><span data-ttu-id="f4baf-339">11</span><span class="sxs-lookup"><span data-stu-id="f4baf-339">11</span></span></td>
    <td><span data-ttu-id="f4baf-340">10</span><span class="sxs-lookup"><span data-stu-id="f4baf-340">10</span></span></td>
    <td><span data-ttu-id="f4baf-341">910.70</span><span class="sxs-lookup"><span data-stu-id="f4baf-341">910.70</span></span></td>
    <td><span data-ttu-id="f4baf-342">14</span><span class="sxs-lookup"><span data-stu-id="f4baf-342">14</span></span></td>
    <td><span data-ttu-id="f4baf-343">1,275.00</span><span class="sxs-lookup"><span data-stu-id="f4baf-343">1,275.00</span></span></td>
    <td><span data-ttu-id="f4baf-344">91.07</span><span class="sxs-lookup"><span data-stu-id="f4baf-344">91.07</span></span></td>
    <td><span data-ttu-id="f4baf-345">0,00</span><span class="sxs-lookup"><span data-stu-id="f4baf-345">0.00</span></span></td>
    <td></td>
    <td><span data-ttu-id="f4baf-346">5.00</span><span class="sxs-lookup"><span data-stu-id="f4baf-346">5.00</span></span></td>
    <td><span data-ttu-id="f4baf-347">455.36</span><span class="sxs-lookup"><span data-stu-id="f4baf-347">455.36</span></span></td>
    <td><span data-ttu-id="f4baf-348">5.00</span><span class="sxs-lookup"><span data-stu-id="f4baf-348">5.00</span></span></td>
    <td><span data-ttu-id="f4baf-349">455.36</span><span class="sxs-lookup"><span data-stu-id="f4baf-349">455.36</span></span></td>
</tr>
<tr>
    <td><span data-ttu-id="f4baf-350">1000</span><span class="sxs-lookup"><span data-stu-id="f4baf-350">1000</span></span></td>
    <td><span data-ttu-id="f4baf-351">1</span><span class="sxs-lookup"><span data-stu-id="f4baf-351">1</span></span></td>
    <td><span data-ttu-id="f4baf-352">12</span><span class="sxs-lookup"><span data-stu-id="f4baf-352">12</span></span></td>
    <td><span data-ttu-id="f4baf-353">4</span><span class="sxs-lookup"><span data-stu-id="f4baf-353">4</span></span></td>
    <td><span data-ttu-id="f4baf-354">364.29</span><span class="sxs-lookup"><span data-stu-id="f4baf-354">364.29</span></span></td>
    <td><span data-ttu-id="f4baf-355">14</span><span class="sxs-lookup"><span data-stu-id="f4baf-355">14</span></span></td>
    <td><span data-ttu-id="f4baf-356">1,275.00</span><span class="sxs-lookup"><span data-stu-id="f4baf-356">1,275.00</span></span></td>
    <td><span data-ttu-id="f4baf-357">91.07</span><span class="sxs-lookup"><span data-stu-id="f4baf-357">91.07</span></span></td>
    <td><span data-ttu-id="f4baf-358">4.00</span><span class="sxs-lookup"><span data-stu-id="f4baf-358">4.00</span></span></td>
    <td><span data-ttu-id="f4baf-359">364.29</span><span class="sxs-lookup"><span data-stu-id="f4baf-359">364.29</span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
</tr>
<tr>
    <td><span data-ttu-id="f4baf-360">1000</span><span class="sxs-lookup"><span data-stu-id="f4baf-360">1000</span></span></td>
    <td><span data-ttu-id="f4baf-361">2</span><span class="sxs-lookup"><span data-stu-id="f4baf-361">2</span></span></td>
    <td></td>
    <td><span data-ttu-id="f4baf-362">10</span><span class="sxs-lookup"><span data-stu-id="f4baf-362">10</span></span></td>
    <td><span data-ttu-id="f4baf-363">2,000.00</span><span class="sxs-lookup"><span data-stu-id="f4baf-363">2,000.00</span></span></td>
    <td><span data-ttu-id="f4baf-364">10</span><span class="sxs-lookup"><span data-stu-id="f4baf-364">10</span></span></td>
    <td><span data-ttu-id="f4baf-365">2,000.00</span><span class="sxs-lookup"><span data-stu-id="f4baf-365">2,000.00</span></span></td>
    <td><span data-ttu-id="f4baf-366">200.00</span><span class="sxs-lookup"><span data-stu-id="f4baf-366">200.00</span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="f4baf-367">10,00</span><span class="sxs-lookup"><span data-stu-id="f4baf-367">10.00</span></span></td>
    <td><span data-ttu-id="f4baf-368">2,000.00</span><span class="sxs-lookup"><span data-stu-id="f4baf-368">2,000.00</span></span></td>
</tr>
</tbody>
<tfoot>
<tr>
    <td><span data-ttu-id="f4baf-369"><strong>1000 Totales</strong></span><span class="sxs-lookup"><span data-stu-id="f4baf-369"><strong>1000 Totals</strong></span></span></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="f4baf-370"><strong>24.00</strong></span><span class="sxs-lookup"><span data-stu-id="f4baf-370"><strong>24.00</strong></span></span></td>
    <td><span data-ttu-id="f4baf-371"><strong>3,275.00</strong></span><span class="sxs-lookup"><span data-stu-id="f4baf-371"><strong>3,275.00</strong></span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="f4baf-372"><strong>4.00</strong></span><span class="sxs-lookup"><span data-stu-id="f4baf-372"><strong>4.00</strong></span></span></td>
    <td><span data-ttu-id="f4baf-373"><strong>364.29</strong></span><span class="sxs-lookup"><span data-stu-id="f4baf-373"><strong>364.29</strong></span></span></td>
    <td><span data-ttu-id="f4baf-374"><strong>5.00</strong></span><span class="sxs-lookup"><span data-stu-id="f4baf-374"><strong>5.00</strong></span></span></td>
    <td><span data-ttu-id="f4baf-375"><strong>455.36</strong></span><span class="sxs-lookup"><span data-stu-id="f4baf-375"><strong>455.36</strong></span></span></td>
    <td><span data-ttu-id="f4baf-376"><strong>15</strong></span><span class="sxs-lookup"><span data-stu-id="f4baf-376"><strong>15</strong></span></span></td>
    <td><span data-ttu-id="f4baf-377"><strong>2,455.36</strong></span><span class="sxs-lookup"><span data-stu-id="f4baf-377"><strong>2,455.36</strong></span></span></td>
</tr>
</tfoot>
</table>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]