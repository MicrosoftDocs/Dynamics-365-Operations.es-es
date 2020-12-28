---
title: Ejemplos de informes de antigüedad de inventario y lógica
description: Este tema presenta algunos ejemplos que muestran cómo interpretar los resultados de un informe de antigüedad del inventario.
author: RichardLuan
manager: tfehr
ms.date: 5/29/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventAgingStorage, InventAgingStorageChart, InventAgingStorageDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: riluan
ms.search.validFrom: 2020-5-29
ms.dyn365.ops.version: ''
ms.openlocfilehash: a6e708e4dc818f20fc8d835053da75c2fe9c98f6
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4436834"
---
# <a name="inventory-aging-report-examples-and-logic"></a><span data-ttu-id="f25b7-103">Ejemplos de informes de antigüedad de inventario y lógica</span><span class="sxs-lookup"><span data-stu-id="f25b7-103">Inventory aging report examples and logic</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f25b7-104">Este tema presenta algunos ejemplos que muestran cómo interpretar los resultados de un informe de **antigüedad del inventario**.</span><span class="sxs-lookup"><span data-stu-id="f25b7-104">This topic presents some examples that show how to interpret the results of an **Inventory aging** report.</span></span> <span data-ttu-id="f25b7-105">Este informe clasifica la cantidad disponible y los valores de inventario para un artículo seleccionado o grupo de artículos en varios períodos.</span><span class="sxs-lookup"><span data-stu-id="f25b7-105">This report categorizes on-hand quantity and inventory values for a selected item or item group into several period buckets.</span></span> <span data-ttu-id="f25b7-106">Este tema también muestra la lógica interna del informe.</span><span class="sxs-lookup"><span data-stu-id="f25b7-106">This topic also shows the internal logic of the report.</span></span>

<span data-ttu-id="f25b7-107">Los ejemplos en este tema muestran los resultados que se presentan en un informe de **antigüedad de inventario** estándar.</span><span class="sxs-lookup"><span data-stu-id="f25b7-107">The examples in this topic show results that are presented on a standard **Inventory aging** report.</span></span> <span data-ttu-id="f25b7-108">Sin embargo, en general, le recomendamos que utilice la versión [Almacenamiento de informes de antigüedad de inventario](inventory-aging-report-storage.md) de este informe, especialmente cuando tiene muchos artículos y almacenes que deben procesarse.</span><span class="sxs-lookup"><span data-stu-id="f25b7-108">However, in general, we recommend that you use the [Inventory aging report storage](inventory-aging-report-storage.md) version of this report, especially when you have many items and warehouses that must be processed.</span></span> <span data-ttu-id="f25b7-109">El almacenamiento de informes de antigüedad de inventario guarda cada informe que genera, muestra los resultados como una página interactiva y un gráfico, y le permite exportar cualquier informe guardado.</span><span class="sxs-lookup"><span data-stu-id="f25b7-109">Inventory aging report storage saves each report that you generate, shows the results as an interactive page and a chart, and lets you export any saved report.</span></span>

## <a name="sample-data-that-is-used-in-these-examples"></a><span data-ttu-id="f25b7-110">Datos de muestra que se usan en estos ejemplos</span><span class="sxs-lookup"><span data-stu-id="f25b7-110">Sample data that is used in these examples</span></span>

<span data-ttu-id="f25b7-111">Los ejemplos de este tema se basan en los datos de muestra de transacciones de inventario que se describen en esta sección.</span><span class="sxs-lookup"><span data-stu-id="f25b7-111">The examples in this topic are based on the sample inventory transaction data that is described in this section.</span></span>

### <a name="storage-dimension-setup"></a><span data-ttu-id="f25b7-112">Configuración de la dimensión de almacenamiento</span><span class="sxs-lookup"><span data-stu-id="f25b7-112">Storage dimension setup</span></span>

<span data-ttu-id="f25b7-113">El sistema de ejemplo contiene la siguiente configuración de dimensiones de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="f25b7-113">The example system contains the following setup of storage dimensions.</span></span>

| <span data-ttu-id="f25b7-114">Nombre</span><span class="sxs-lookup"><span data-stu-id="f25b7-114">Name</span></span>      | <span data-ttu-id="f25b7-115">Activas</span><span class="sxs-lookup"><span data-stu-id="f25b7-115">Active</span></span> | <span data-ttu-id="f25b7-116">Inventario físico</span><span class="sxs-lookup"><span data-stu-id="f25b7-116">Physical inventory</span></span> | <span data-ttu-id="f25b7-117">Inventario financiero</span><span class="sxs-lookup"><span data-stu-id="f25b7-117">Financial inventory</span></span> |
|-----------|--------|--------------------|---------------------|
| <span data-ttu-id="f25b7-118">Sitio</span><span class="sxs-lookup"><span data-stu-id="f25b7-118">Site</span></span>      | <span data-ttu-id="f25b7-119">Sí</span><span class="sxs-lookup"><span data-stu-id="f25b7-119">Yes</span></span>    | <span data-ttu-id="f25b7-120">Sí</span><span class="sxs-lookup"><span data-stu-id="f25b7-120">Yes</span></span>                | <span data-ttu-id="f25b7-121">Sí</span><span class="sxs-lookup"><span data-stu-id="f25b7-121">Yes</span></span>                 |
| <span data-ttu-id="f25b7-122">Almacén</span><span class="sxs-lookup"><span data-stu-id="f25b7-122">Warehouse</span></span> | <span data-ttu-id="f25b7-123">Sí</span><span class="sxs-lookup"><span data-stu-id="f25b7-123">Yes</span></span>    | <span data-ttu-id="f25b7-124">Sí</span><span class="sxs-lookup"><span data-stu-id="f25b7-124">Yes</span></span>                | <span data-ttu-id="f25b7-125">Nº</span><span class="sxs-lookup"><span data-stu-id="f25b7-125">No</span></span>                  |

### <a name="inventory-model"></a><span data-ttu-id="f25b7-126">Modelo de inventario</span><span class="sxs-lookup"><span data-stu-id="f25b7-126">Inventory model</span></span>

<span data-ttu-id="f25b7-127">Para el sistema de ejemplo, el modelo de inventario para los productos publicados es *FIFO*, y la configuración de **Precio de coste** para el modelo de inventario es *Incluir valor físico*.</span><span class="sxs-lookup"><span data-stu-id="f25b7-127">For the example system, the inventory model for the released products is *FIFO*, and the **Cost price** setting for the inventory model is *Include physical value*.</span></span>

### <a name="inventory-transactions"></a><span data-ttu-id="f25b7-128">Transacciones de inventario</span><span class="sxs-lookup"><span data-stu-id="f25b7-128">Inventory transactions</span></span>

<span data-ttu-id="f25b7-129">El sistema de ejemplo contiene las siguientes transacciones de inventario para un producto publicado que tiene el número de artículo *1000*.</span><span class="sxs-lookup"><span data-stu-id="f25b7-129">The example system contains the following inventory transactions for a released product that has the item number *1000*.</span></span>

| <span data-ttu-id="f25b7-130">Referencia</span><span class="sxs-lookup"><span data-stu-id="f25b7-130">Reference</span></span>      | <span data-ttu-id="f25b7-131">Sitio</span><span class="sxs-lookup"><span data-stu-id="f25b7-131">Site</span></span> | <span data-ttu-id="f25b7-132">Almacén</span><span class="sxs-lookup"><span data-stu-id="f25b7-132">Warehouse</span></span> | <span data-ttu-id="f25b7-133">Recepción</span><span class="sxs-lookup"><span data-stu-id="f25b7-133">Receipt</span></span>   | <span data-ttu-id="f25b7-134">Emitir</span><span class="sxs-lookup"><span data-stu-id="f25b7-134">Issue</span></span> | <span data-ttu-id="f25b7-135">Fecha física</span><span class="sxs-lookup"><span data-stu-id="f25b7-135">Physical date</span></span> | <span data-ttu-id="f25b7-136">Fecha financiera</span><span class="sxs-lookup"><span data-stu-id="f25b7-136">Financial date</span></span> | <span data-ttu-id="f25b7-137">Cantidad</span><span class="sxs-lookup"><span data-stu-id="f25b7-137">Quantity</span></span> | <span data-ttu-id="f25b7-138">Importe de coste</span><span class="sxs-lookup"><span data-stu-id="f25b7-138">Cost amount</span></span> | <span data-ttu-id="f25b7-139">Importe de coste físico</span><span class="sxs-lookup"><span data-stu-id="f25b7-139">Physical cost amount</span></span> |
|----------------|------|-----------|-----------|-------|---------------|----------------|----------|-------------|----------------------|
| <span data-ttu-id="f25b7-140">Pedido de compra</span><span class="sxs-lookup"><span data-stu-id="f25b7-140">Purchase order</span></span> | <span data-ttu-id="f25b7-141">1</span><span class="sxs-lookup"><span data-stu-id="f25b7-141">1</span></span>    | <span data-ttu-id="f25b7-142">11</span><span class="sxs-lookup"><span data-stu-id="f25b7-142">11</span></span>        | <span data-ttu-id="f25b7-143">Comprado</span><span class="sxs-lookup"><span data-stu-id="f25b7-143">Purchased</span></span> |       | <span data-ttu-id="f25b7-144">15 de marzo</span><span class="sxs-lookup"><span data-stu-id="f25b7-144">March 15</span></span>      | <span data-ttu-id="f25b7-145">15 de marzo</span><span class="sxs-lookup"><span data-stu-id="f25b7-145">March 15</span></span>       | <span data-ttu-id="f25b7-146">10</span><span class="sxs-lookup"><span data-stu-id="f25b7-146">10</span></span>       | <span data-ttu-id="f25b7-147">1.000</span><span class="sxs-lookup"><span data-stu-id="f25b7-147">1,000</span></span>       | <span data-ttu-id="f25b7-148">1.000</span><span class="sxs-lookup"><span data-stu-id="f25b7-148">1,000</span></span>                |
| <span data-ttu-id="f25b7-149">Pedido de compra</span><span class="sxs-lookup"><span data-stu-id="f25b7-149">Purchase order</span></span> | <span data-ttu-id="f25b7-150">2</span><span class="sxs-lookup"><span data-stu-id="f25b7-150">2</span></span>    | <span data-ttu-id="f25b7-151">21</span><span class="sxs-lookup"><span data-stu-id="f25b7-151">21</span></span>        | <span data-ttu-id="f25b7-152">Comprado</span><span class="sxs-lookup"><span data-stu-id="f25b7-152">Purchased</span></span> |       | <span data-ttu-id="f25b7-153">15 de marzo</span><span class="sxs-lookup"><span data-stu-id="f25b7-153">March 15</span></span>      | <span data-ttu-id="f25b7-154">15 de marzo</span><span class="sxs-lookup"><span data-stu-id="f25b7-154">March 15</span></span>       | <span data-ttu-id="f25b7-155">10</span><span class="sxs-lookup"><span data-stu-id="f25b7-155">10</span></span>       | <span data-ttu-id="f25b7-156">2,000</span><span class="sxs-lookup"><span data-stu-id="f25b7-156">2,000</span></span>       | <span data-ttu-id="f25b7-157">2,000</span><span class="sxs-lookup"><span data-stu-id="f25b7-157">2,000</span></span>                |
| <span data-ttu-id="f25b7-158">Pedido de compra</span><span class="sxs-lookup"><span data-stu-id="f25b7-158">Purchase order</span></span> | <span data-ttu-id="f25b7-159">1</span><span class="sxs-lookup"><span data-stu-id="f25b7-159">1</span></span>    | <span data-ttu-id="f25b7-160">11</span><span class="sxs-lookup"><span data-stu-id="f25b7-160">11</span></span>        | <span data-ttu-id="f25b7-161">Recibida</span><span class="sxs-lookup"><span data-stu-id="f25b7-161">Received</span></span>  |       | <span data-ttu-id="f25b7-162">15 de abril</span><span class="sxs-lookup"><span data-stu-id="f25b7-162">April 15</span></span>      |                | <span data-ttu-id="f25b7-163">5</span><span class="sxs-lookup"><span data-stu-id="f25b7-163">5</span></span>        |             | <span data-ttu-id="f25b7-164">375</span><span class="sxs-lookup"><span data-stu-id="f25b7-164">375</span></span>                  |
| <span data-ttu-id="f25b7-165">Orden de transferencia</span><span class="sxs-lookup"><span data-stu-id="f25b7-165">Transfer order</span></span> | <span data-ttu-id="f25b7-166">1</span><span class="sxs-lookup"><span data-stu-id="f25b7-166">1</span></span>    | <span data-ttu-id="f25b7-167">11</span><span class="sxs-lookup"><span data-stu-id="f25b7-167">11</span></span>        |           | <span data-ttu-id="f25b7-168">Vendido</span><span class="sxs-lookup"><span data-stu-id="f25b7-168">Sold</span></span>  | <span data-ttu-id="f25b7-169">mayo de 2</span><span class="sxs-lookup"><span data-stu-id="f25b7-169">May 2</span></span>         | <span data-ttu-id="f25b7-170">mayo de 2</span><span class="sxs-lookup"><span data-stu-id="f25b7-170">May 2</span></span>          | <span data-ttu-id="f25b7-171">-5</span><span class="sxs-lookup"><span data-stu-id="f25b7-171">-5</span></span>       | <span data-ttu-id="f25b7-172">-458,33</span><span class="sxs-lookup"><span data-stu-id="f25b7-172">-458.33</span></span>     | <span data-ttu-id="f25b7-173">-458,33</span><span class="sxs-lookup"><span data-stu-id="f25b7-173">-458.33</span></span>              |
| <span data-ttu-id="f25b7-174">Orden de transferencia</span><span class="sxs-lookup"><span data-stu-id="f25b7-174">Transfer order</span></span> | <span data-ttu-id="f25b7-175">1</span><span class="sxs-lookup"><span data-stu-id="f25b7-175">1</span></span>    | <span data-ttu-id="f25b7-176">12</span><span class="sxs-lookup"><span data-stu-id="f25b7-176">12</span></span>        | <span data-ttu-id="f25b7-177">Comprado</span><span class="sxs-lookup"><span data-stu-id="f25b7-177">Purchased</span></span> |       | <span data-ttu-id="f25b7-178">mayo de 2</span><span class="sxs-lookup"><span data-stu-id="f25b7-178">May 2</span></span>         | <span data-ttu-id="f25b7-179">mayo de 2</span><span class="sxs-lookup"><span data-stu-id="f25b7-179">May 2</span></span>          | <span data-ttu-id="f25b7-180">5</span><span class="sxs-lookup"><span data-stu-id="f25b7-180">5</span></span>        | <span data-ttu-id="f25b7-181">458.33</span><span class="sxs-lookup"><span data-stu-id="f25b7-181">458.33</span></span>      | <span data-ttu-id="f25b7-182">458.33</span><span class="sxs-lookup"><span data-stu-id="f25b7-182">458.33</span></span>               |
| <span data-ttu-id="f25b7-183">Pedido de ventas</span><span class="sxs-lookup"><span data-stu-id="f25b7-183">Sales order</span></span>    | <span data-ttu-id="f25b7-184">1</span><span class="sxs-lookup"><span data-stu-id="f25b7-184">1</span></span>    | <span data-ttu-id="f25b7-185">12</span><span class="sxs-lookup"><span data-stu-id="f25b7-185">12</span></span>        |           | <span data-ttu-id="f25b7-186">Vendido</span><span class="sxs-lookup"><span data-stu-id="f25b7-186">Sold</span></span>  | <span data-ttu-id="f25b7-187">mayo de 3</span><span class="sxs-lookup"><span data-stu-id="f25b7-187">May 3</span></span>         | <span data-ttu-id="f25b7-188">mayo de 3</span><span class="sxs-lookup"><span data-stu-id="f25b7-188">May 3</span></span>          | <span data-ttu-id="f25b7-189">-1</span><span class="sxs-lookup"><span data-stu-id="f25b7-189">-1</span></span>       | <span data-ttu-id="f25b7-190">-91,67</span><span class="sxs-lookup"><span data-stu-id="f25b7-190">-91.67</span></span>      | <span data-ttu-id="f25b7-191">-91,67</span><span class="sxs-lookup"><span data-stu-id="f25b7-191">-91.67</span></span>               |

## <a name="how-quantities-and-amounts-in-each-period-bucket-are-calculated"></a><span data-ttu-id="f25b7-192">Cómo se calculan las cantidades y los importes en cada cubo de períodos</span><span class="sxs-lookup"><span data-stu-id="f25b7-192">How quantities and amounts in each period bucket are calculated</span></span>

<span data-ttu-id="f25b7-193">Al utilizar los datos de ejemplo que se describen en las secciones anteriores, podrá ejecutar un informe de **antigüedad de inventario** que tiene la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="f25b7-193">By using the sample data that is described in the previous sections, you can run an **Inventory aging** report that has the following settings:</span></span>

- <span data-ttu-id="f25b7-194">**A partir de la fecha:** *9 de mayo de 2020*</span><span class="sxs-lookup"><span data-stu-id="f25b7-194">**As of date:** *May 9, 2020*</span></span>
- <span data-ttu-id="f25b7-195">**Sitio:** *Ver*</span><span class="sxs-lookup"><span data-stu-id="f25b7-195">**Site:** *View*</span></span>
- <span data-ttu-id="f25b7-196">**Almacén**: *No*</span><span class="sxs-lookup"><span data-stu-id="f25b7-196">**Warehouse:** *No*</span></span>
- <span data-ttu-id="f25b7-197">**Número de artículo:** *Total*</span><span class="sxs-lookup"><span data-stu-id="f25b7-197">**Item number:** *Total*</span></span>
- <span data-ttu-id="f25b7-198">**Período de antigüedad:** establezca este campo para generar depósitos mensuales.</span><span class="sxs-lookup"><span data-stu-id="f25b7-198">**Aging period:** Set this field to generate monthly buckets.</span></span>

<span data-ttu-id="f25b7-199">En este caso, el contenido del informe generado se parecerá al siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="f25b7-199">In this case, the content of the report that is generated will resemble the following example.</span></span>

<table>
<thead>
<tr>
    <th rowspan="2"><span data-ttu-id="f25b7-200">código de artículo</span><span class="sxs-lookup"><span data-stu-id="f25b7-200">Item number</span></span></th>
    <th rowspan="2"><span data-ttu-id="f25b7-201">Sitio</span><span class="sxs-lookup"><span data-stu-id="f25b7-201">Site</span></span></th>
    <th rowspan="2"><span data-ttu-id="f25b7-202">Cantidad disponible</span><span class="sxs-lookup"><span data-stu-id="f25b7-202">On-hand quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="f25b7-203">Valor disponible</span><span class="sxs-lookup"><span data-stu-id="f25b7-203">On-hand value</span></span></th>
    <th rowspan="2"><span data-ttu-id="f25b7-204">Cantidad de valor de inventario</span><span class="sxs-lookup"><span data-stu-id="f25b7-204">Inventory value quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="f25b7-205">Valor de inventario</span><span class="sxs-lookup"><span data-stu-id="f25b7-205">Inventory value</span></span></th>
    <th rowspan="2"><span data-ttu-id="f25b7-206">Coste unitario promedio</span><span class="sxs-lookup"><span data-stu-id="f25b7-206">Average unit cost</span></span></th>
    <th colspan="2"><span data-ttu-id="f25b7-207">5/8/2020 - 5/1/2020</span><span class="sxs-lookup"><span data-stu-id="f25b7-207">5/8/2020 - 5/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="f25b7-208">4/30/2020 - 4/1/2020</span><span class="sxs-lookup"><span data-stu-id="f25b7-208">4/30/2020 - 4/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="f25b7-209">3/31/2020 - 3/1/2020</span><span class="sxs-lookup"><span data-stu-id="f25b7-209">3/31/2020 - 3/1/2020</span></span></th>
</tr>
<tr>
    <th><span data-ttu-id="f25b7-210">P1:Cantidad</span><span class="sxs-lookup"><span data-stu-id="f25b7-210">P1:Quantity</span></span></th>
    <th><span data-ttu-id="f25b7-211">P1:Importe</span><span class="sxs-lookup"><span data-stu-id="f25b7-211">P1:Amount</span></span></th>
    <th><span data-ttu-id="f25b7-212">P2:Cantidad</span><span class="sxs-lookup"><span data-stu-id="f25b7-212">P2:Quantity</span></span></th>
    <th><span data-ttu-id="f25b7-213">P2:Importe</span><span class="sxs-lookup"><span data-stu-id="f25b7-213">P2:Amount</span></span></th>
    <th><span data-ttu-id="f25b7-214">P3:Cantidad</span><span class="sxs-lookup"><span data-stu-id="f25b7-214">P3:Quantity</span></span></th>
    <th><span data-ttu-id="f25b7-215">P3:Importe</span><span class="sxs-lookup"><span data-stu-id="f25b7-215">P3:Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
    <td><span data-ttu-id="f25b7-216">1000</span><span class="sxs-lookup"><span data-stu-id="f25b7-216">1000</span></span></td>
    <td><span data-ttu-id="f25b7-217">1</span><span class="sxs-lookup"><span data-stu-id="f25b7-217">1</span></span></td>
    <td><span data-ttu-id="f25b7-218">14</span><span class="sxs-lookup"><span data-stu-id="f25b7-218">14</span></span></td>
    <td><span data-ttu-id="f25b7-219">1,283.33</span><span class="sxs-lookup"><span data-stu-id="f25b7-219">1,283.33</span></span></td>
    <td><span data-ttu-id="f25b7-220">14</span><span class="sxs-lookup"><span data-stu-id="f25b7-220">14</span></span></td>
    <td><span data-ttu-id="f25b7-221">1,283.33</span><span class="sxs-lookup"><span data-stu-id="f25b7-221">1,283.33</span></span></td>
    <td><span data-ttu-id="f25b7-222">91.67</span><span class="sxs-lookup"><span data-stu-id="f25b7-222">91.67</span></span></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="f25b7-223">5.00</span><span class="sxs-lookup"><span data-stu-id="f25b7-223">5.00</span></span></td>
    <td><span data-ttu-id="f25b7-224">458.33</span><span class="sxs-lookup"><span data-stu-id="f25b7-224">458.33</span></span></td>
    <td><span data-ttu-id="f25b7-225">9.00</span><span class="sxs-lookup"><span data-stu-id="f25b7-225">9.00</span></span></td>
    <td><span data-ttu-id="f25b7-226">825.00</span><span class="sxs-lookup"><span data-stu-id="f25b7-226">825.00</span></span></td>
</tr>
<tr>
    <td><span data-ttu-id="f25b7-227">1000</span><span class="sxs-lookup"><span data-stu-id="f25b7-227">1000</span></span></td>
    <td><span data-ttu-id="f25b7-228">2</span><span class="sxs-lookup"><span data-stu-id="f25b7-228">2</span></span></td>
    <td><span data-ttu-id="f25b7-229">10</span><span class="sxs-lookup"><span data-stu-id="f25b7-229">10</span></span></td>
    <td><span data-ttu-id="f25b7-230">2,000.00</span><span class="sxs-lookup"><span data-stu-id="f25b7-230">2,000.00</span></span></td>
    <td><span data-ttu-id="f25b7-231">10</span><span class="sxs-lookup"><span data-stu-id="f25b7-231">10</span></span></td>
    <td><span data-ttu-id="f25b7-232">2,000.00</span><span class="sxs-lookup"><span data-stu-id="f25b7-232">2,000.00</span></span></td>
    <td><span data-ttu-id="f25b7-233">200.00</span><span class="sxs-lookup"><span data-stu-id="f25b7-233">200.00</span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="f25b7-234">10,00</span><span class="sxs-lookup"><span data-stu-id="f25b7-234">10.00</span></span></td>
    <td><span data-ttu-id="f25b7-235">2,000.00</span><span class="sxs-lookup"><span data-stu-id="f25b7-235">2,000.00</span></span></td>
</tr>
</tbody>
<tfoot>
<tr>
    <td><span data-ttu-id="f25b7-236"><strong>1000 Totales</strong></span><span class="sxs-lookup"><span data-stu-id="f25b7-236"><strong>1000 Totals</strong></span></span></td>
    <td></td>
    <td><span data-ttu-id="f25b7-237"><strong>24.00</strong></span><span class="sxs-lookup"><span data-stu-id="f25b7-237"><strong>24.00</strong></span></span></td>
    <td><span data-ttu-id="f25b7-238"><strong>3,283.33</strong></span><span class="sxs-lookup"><span data-stu-id="f25b7-238"><strong>3,283.33</strong></span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="f25b7-239"><strong>5.00</strong></span><span class="sxs-lookup"><span data-stu-id="f25b7-239"><strong>5.00</strong></span></span></td>
    <td><span data-ttu-id="f25b7-240"><strong>458.33</strong></span><span class="sxs-lookup"><span data-stu-id="f25b7-240"><strong>458.33</strong></span></span></td>
    <td><span data-ttu-id="f25b7-241"><strong>19</strong></span><span class="sxs-lookup"><span data-stu-id="f25b7-241"><strong>19</strong></span></span></td>
    <td><span data-ttu-id="f25b7-242"><strong>2,825.00</strong></span><span class="sxs-lookup"><span data-stu-id="f25b7-242"><strong>2,825.00</strong></span></span></td>
</tr>
</tfoot>
</table>

<span data-ttu-id="f25b7-243">Tenga en cuenta los siguientes detalles en este informe de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f25b7-243">Note the following details in this example report:</span></span>

- <span data-ttu-id="f25b7-244">Los valores **Cantidad de valor de inventario**, **Valor de inventario** y **Coste unitario promedio** que se muestran en el informe son valores para la dimensión de inventario financiero (**Sitio**, en este caso).</span><span class="sxs-lookup"><span data-stu-id="f25b7-244">The **Inventory value quantity**, **Inventory value**, and **Average unit cost** values that are shown on the report are values for the financial inventory dimension (**Site**, in this case).</span></span>

    <span data-ttu-id="f25b7-245">Por ejemplo, para el sitio 1, el informe muestra la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="f25b7-245">For example, for site 1, the report shows the following information:</span></span>

    - <span data-ttu-id="f25b7-246">El valor **Cantidad de valor de inventario** es *14* (= 10 + 5 - 5 + 5 - 1).</span><span class="sxs-lookup"><span data-stu-id="f25b7-246">The **Inventory value quantity** value is *14* (= 10 + 5 – 5 + 5 – 1).</span></span>
    - <span data-ttu-id="f25b7-247">El valor **Cantidad de valor de inventario** es *1283,33* (= 1000 + 375 - 458,33 + 458,33 - 91,67).</span><span class="sxs-lookup"><span data-stu-id="f25b7-247">The **Inventory value** value is *1,283.33* (= 1,000 + 375 – 458.33 + 458.33 – 91.67).</span></span>
    - <span data-ttu-id="f25b7-248">El valor **Coste unitario promedio** es *91,67*.</span><span class="sxs-lookup"><span data-stu-id="f25b7-248">The **Average unit cost** value is *91.67*.</span></span>
    - <span data-ttu-id="f25b7-249">El valor **Valor disponible** y el valor **Importe** en cada período se calcula utilizando el valor **Coste unitario promedio**.</span><span class="sxs-lookup"><span data-stu-id="f25b7-249">The **On-hand value** value and the **Amount** value in each period bucket are calculated by using the **Average unit cost** value.</span></span>

- <span data-ttu-id="f25b7-250">El informe determina la cantidad disponible para cada cubo de períodos resumiendo la cantidad de inventario total recibida para cada cubo de períodos.</span><span class="sxs-lookup"><span data-stu-id="f25b7-250">The report determines the on-hand quantity for each period bucket by summarizing the total received inventory quantity for each period bucket.</span></span> <span data-ttu-id="f25b7-251">Luego aplica el principio de primero en entrar, primero en salir (FIFO) para deducir la cantidad total emitida, independientemente del modelo de inventario que usan los artículos.</span><span class="sxs-lookup"><span data-stu-id="f25b7-251">It then applies the first in, first out (FIFO) principle to deduct the total issued quantity, regardless of the inventory model that the items use.</span></span>

<span data-ttu-id="f25b7-252">Si ejecuta el mismo informe nuevamente, pero esta vez configura los campos **Sitio** y **Almacén** en *Ver*, el nuevo informe se parecerá al siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="f25b7-252">If you run the same report again, but this time you set both the **Site** and **Warehouse** fields to *View*, the new report will resemble the following example.</span></span>

<table>
<thead>
<tr>
    <th rowspan="2"><span data-ttu-id="f25b7-253">código de artículo</span><span class="sxs-lookup"><span data-stu-id="f25b7-253">Item number</span></span></th>
    <th rowspan="2"><span data-ttu-id="f25b7-254">Sitio</span><span class="sxs-lookup"><span data-stu-id="f25b7-254">Site</span></span></th>
    <th rowspan="2"><span data-ttu-id="f25b7-255">Almacén</span><span class="sxs-lookup"><span data-stu-id="f25b7-255">Warehouse</span></span></th>
    <th rowspan="2"><span data-ttu-id="f25b7-256">Cantidad disponible</span><span class="sxs-lookup"><span data-stu-id="f25b7-256">On-hand quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="f25b7-257">Valor disponible</span><span class="sxs-lookup"><span data-stu-id="f25b7-257">On-hand value</span></span></th>
    <th rowspan="2"><span data-ttu-id="f25b7-258">Cantidad de valor de inventario</span><span class="sxs-lookup"><span data-stu-id="f25b7-258">Inventory value quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="f25b7-259">Valor de inventario</span><span class="sxs-lookup"><span data-stu-id="f25b7-259">Inventory value</span></span></th>
    <th rowspan="2"><span data-ttu-id="f25b7-260">Coste unitario promedio</span><span class="sxs-lookup"><span data-stu-id="f25b7-260">Average unit cost</span></span></th>
    <th colspan="2"><span data-ttu-id="f25b7-261">5/8/2020 - 5/1/2020</span><span class="sxs-lookup"><span data-stu-id="f25b7-261">5/8/2020 - 5/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="f25b7-262">4/30/2020 - 4/1/2020</span><span class="sxs-lookup"><span data-stu-id="f25b7-262">4/30/2020 - 4/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="f25b7-263">3/31/2020 - 3/1/2020</span><span class="sxs-lookup"><span data-stu-id="f25b7-263">3/31/2020 - 3/1/2020</span></span></th>
</tr>
<tr>
    <th><span data-ttu-id="f25b7-264">P1:Cantidad</span><span class="sxs-lookup"><span data-stu-id="f25b7-264">P1:Quantity</span></span></th>
    <th><span data-ttu-id="f25b7-265">P1:Importe</span><span class="sxs-lookup"><span data-stu-id="f25b7-265">P1:Amount</span></span></th>
    <th><span data-ttu-id="f25b7-266">P2:Cantidad</span><span class="sxs-lookup"><span data-stu-id="f25b7-266">P2:Quantity</span></span></th>
    <th><span data-ttu-id="f25b7-267">P2:Importe</span><span class="sxs-lookup"><span data-stu-id="f25b7-267">P2:Amount</span></span></th>
    <th><span data-ttu-id="f25b7-268">P3:Cantidad</span><span class="sxs-lookup"><span data-stu-id="f25b7-268">P3:Quantity</span></span></th>
    <th><span data-ttu-id="f25b7-269">P3:Importe</span><span class="sxs-lookup"><span data-stu-id="f25b7-269">P3:Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
    <td><span data-ttu-id="f25b7-270">1000</span><span class="sxs-lookup"><span data-stu-id="f25b7-270">1000</span></span></td>
    <td><span data-ttu-id="f25b7-271">1</span><span class="sxs-lookup"><span data-stu-id="f25b7-271">1</span></span></td>
    <td><span data-ttu-id="f25b7-272">11</span><span class="sxs-lookup"><span data-stu-id="f25b7-272">11</span></span></td>
    <td><span data-ttu-id="f25b7-273">10</span><span class="sxs-lookup"><span data-stu-id="f25b7-273">10</span></span></td>
    <td><span data-ttu-id="f25b7-274">916.67</span><span class="sxs-lookup"><span data-stu-id="f25b7-274">916.67</span></span></td>
    <td><span data-ttu-id="f25b7-275">14</span><span class="sxs-lookup"><span data-stu-id="f25b7-275">14</span></span></td>
    <td><span data-ttu-id="f25b7-276">1,283.33</span><span class="sxs-lookup"><span data-stu-id="f25b7-276">1,283.33</span></span></td>
    <td><span data-ttu-id="f25b7-277">91.67</span><span class="sxs-lookup"><span data-stu-id="f25b7-277">91.67</span></span></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="f25b7-278">5.00</span><span class="sxs-lookup"><span data-stu-id="f25b7-278">5.00</span></span></td>
    <td><span data-ttu-id="f25b7-279">458.33</span><span class="sxs-lookup"><span data-stu-id="f25b7-279">458.33</span></span></td>
    <td><span data-ttu-id="f25b7-280">5.00</span><span class="sxs-lookup"><span data-stu-id="f25b7-280">5.00</span></span></td>
    <td><span data-ttu-id="f25b7-281">458.33</span><span class="sxs-lookup"><span data-stu-id="f25b7-281">458.33</span></span></td>
</tr>
<tr>
    <td><span data-ttu-id="f25b7-282">1000</span><span class="sxs-lookup"><span data-stu-id="f25b7-282">1000</span></span></td>
    <td><span data-ttu-id="f25b7-283">1</span><span class="sxs-lookup"><span data-stu-id="f25b7-283">1</span></span></td>
    <td><span data-ttu-id="f25b7-284">12</span><span class="sxs-lookup"><span data-stu-id="f25b7-284">12</span></span></td>
    <td><span data-ttu-id="f25b7-285">4</span><span class="sxs-lookup"><span data-stu-id="f25b7-285">4</span></span></td>
    <td><span data-ttu-id="f25b7-286">366.67</span><span class="sxs-lookup"><span data-stu-id="f25b7-286">366.67</span></span></td>
    <td><span data-ttu-id="f25b7-287">14</span><span class="sxs-lookup"><span data-stu-id="f25b7-287">14</span></span></td>
    <td><span data-ttu-id="f25b7-288">1,283.33</span><span class="sxs-lookup"><span data-stu-id="f25b7-288">1,283.33</span></span></td>
    <td><span data-ttu-id="f25b7-289">91.67</span><span class="sxs-lookup"><span data-stu-id="f25b7-289">91.67</span></span></td>
    <td><span data-ttu-id="f25b7-290">4.00</span><span class="sxs-lookup"><span data-stu-id="f25b7-290">4.00</span></span></td>
    <td><span data-ttu-id="f25b7-291">366.67</span><span class="sxs-lookup"><span data-stu-id="f25b7-291">366.67</span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
</tr>
<tr>
    <td><span data-ttu-id="f25b7-292">1000</span><span class="sxs-lookup"><span data-stu-id="f25b7-292">1000</span></span></td>
    <td><span data-ttu-id="f25b7-293">2</span><span class="sxs-lookup"><span data-stu-id="f25b7-293">2</span></span></td>
    <td></td>
    <td><span data-ttu-id="f25b7-294">10</span><span class="sxs-lookup"><span data-stu-id="f25b7-294">10</span></span></td>
    <td><span data-ttu-id="f25b7-295">2,000.00</span><span class="sxs-lookup"><span data-stu-id="f25b7-295">2,000.00</span></span></td>
    <td><span data-ttu-id="f25b7-296">10</span><span class="sxs-lookup"><span data-stu-id="f25b7-296">10</span></span></td>
    <td><span data-ttu-id="f25b7-297">2,000.00</span><span class="sxs-lookup"><span data-stu-id="f25b7-297">2,000.00</span></span></td>
    <td><span data-ttu-id="f25b7-298">200.00</span><span class="sxs-lookup"><span data-stu-id="f25b7-298">200.00</span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="f25b7-299">10,00</span><span class="sxs-lookup"><span data-stu-id="f25b7-299">10.00</span></span></td>
    <td><span data-ttu-id="f25b7-300">2,000.00</span><span class="sxs-lookup"><span data-stu-id="f25b7-300">2,000.00</span></span></td>
</tr>
</tbody>
<tfoot>
<tr>
    <td><span data-ttu-id="f25b7-301"><strong>1000 Totales</strong></span><span class="sxs-lookup"><span data-stu-id="f25b7-301"><strong>1000 Totals</strong></span></span></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="f25b7-302"><strong>24.00</strong></span><span class="sxs-lookup"><span data-stu-id="f25b7-302"><strong>24.00</strong></span></span></td>
    <td><span data-ttu-id="f25b7-303"><strong>3,283.33</strong></span><span class="sxs-lookup"><span data-stu-id="f25b7-303"><strong>3,283.33</strong></span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="f25b7-304"><strong>4.00</strong></span><span class="sxs-lookup"><span data-stu-id="f25b7-304"><strong>4.00</strong></span></span></td>
    <td><span data-ttu-id="f25b7-305"><strong>366.67</strong></span><span class="sxs-lookup"><span data-stu-id="f25b7-305"><strong>366.67</strong></span></span></td>
    <td><span data-ttu-id="f25b7-306"><strong>5.00</strong></span><span class="sxs-lookup"><span data-stu-id="f25b7-306"><strong>5.00</strong></span></span></td>
    <td><span data-ttu-id="f25b7-307"><strong>458.33</strong></span><span class="sxs-lookup"><span data-stu-id="f25b7-307"><strong>458.33</strong></span></span></td>
    <td><span data-ttu-id="f25b7-308"><strong>15</strong></span><span class="sxs-lookup"><span data-stu-id="f25b7-308"><strong>15</strong></span></span></td>
    <td><span data-ttu-id="f25b7-309"><strong>2,458.33</strong></span><span class="sxs-lookup"><span data-stu-id="f25b7-309"><strong>2,458.33</strong></span></span></td>
</tr>
</tfoot>
</table>

<span data-ttu-id="f25b7-310">Esta vez, el sitio 1 se divide en dos filas, una para el almacén 11 y otra para el almacén 12.</span><span class="sxs-lookup"><span data-stu-id="f25b7-310">This time, site 1 is split into two rows, one for warehouse 11 and one for warehouse 12.</span></span> <span data-ttu-id="f25b7-311">Sin embargo, los valores **Cantidad de valor de inventario**, **Valor de inventario** y **Coste unitario promedio** son los mismos porque **Almacén** no es una dimensión de inventario financiera.</span><span class="sxs-lookup"><span data-stu-id="f25b7-311">However, the **Inventory value quantity**, **Inventory value**, and **Average unit cost** values are the same, because **Warehouse** isn't a financial inventory dimension.</span></span>

<span data-ttu-id="f25b7-312">Además, observe que la distribución de cantidad del sitio 1 es diferente.</span><span class="sxs-lookup"><span data-stu-id="f25b7-312">Additionally, notice that the quantity distribution of site 1 is different.</span></span> <span data-ttu-id="f25b7-313">En el primer informe que ejecutó, el sistema ignoró la orden de transferencia que ocurrió en el mismo sitio y dedujo la cantidad de la factura de venta del cubo de periodos **31/03/2020 - 1/3/2020** en el sitio 1.</span><span class="sxs-lookup"><span data-stu-id="f25b7-313">In the first report that you ran, the system ignored the transfer order that occurred in the same site and deducted the quantity of the sales invoice from the **3/31/2020 - 3/1/2020** period bucket in site 1.</span></span> <span data-ttu-id="f25b7-314">Sin embargo, en el nuevo informe, el sistema deduce la cantidad de la factura de venta del cubo de períodos **8/05/2020 - 5/1/2020** en el almacén 12.</span><span class="sxs-lookup"><span data-stu-id="f25b7-314">However, in the new report, the system deducts the quantity of the sales invoice from the **5/8/2020 - 5/1/2020** period bucket in warehouse 12.</span></span>

## <a name="effects-of-inventory-closing"></a><span data-ttu-id="f25b7-315">Efectos del cierre del inventario</span><span class="sxs-lookup"><span data-stu-id="f25b7-315">Effects of inventory closing</span></span>

<span data-ttu-id="f25b7-316">Si ejecuta el cierre de inventario para mayo y luego vuelve a ejecutar el informe anterior, pero configura el campo **A partir de la fecha** en el *31 de mayo de 2020*, verá los siguientes resultados:</span><span class="sxs-lookup"><span data-stu-id="f25b7-316">If you run the inventory closing for May and then run the previous report again, but you set the **As of date** field to *May 31, 2020*, you will notice the following results:</span></span>

- <span data-ttu-id="f25b7-317">Los valores **Valor de inventario** y **Coste unitario promedio** se actualizan.</span><span class="sxs-lookup"><span data-stu-id="f25b7-317">The **Inventory value** and **Average unit cost** values are updated.</span></span>
- <span data-ttu-id="f25b7-318">El valor **Valor disponible** y todos los valores de **Importe** en cada cubo de períodos se actualizan en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="f25b7-318">The **On-hand value** value and all the **Amount** values in every period bucket are updated accordingly.</span></span>

<span data-ttu-id="f25b7-319">El informe nuevo se parecerá al ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="f25b7-319">The new report will resemble the following example.</span></span>

<table>
<thead>
<tr>
    <th rowspan="2"><span data-ttu-id="f25b7-320">código de artículo</span><span class="sxs-lookup"><span data-stu-id="f25b7-320">Item number</span></span></th>
    <th rowspan="2"><span data-ttu-id="f25b7-321">Sitio</span><span class="sxs-lookup"><span data-stu-id="f25b7-321">Site</span></span></th>
    <th rowspan="2"><span data-ttu-id="f25b7-322">Almacén</span><span class="sxs-lookup"><span data-stu-id="f25b7-322">Warehouse</span></span></th>
    <th rowspan="2"><span data-ttu-id="f25b7-323">Cantidad disponible</span><span class="sxs-lookup"><span data-stu-id="f25b7-323">On-hand quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="f25b7-324">Valor disponible</span><span class="sxs-lookup"><span data-stu-id="f25b7-324">On-hand value</span></span></th>
    <th rowspan="2"><span data-ttu-id="f25b7-325">Cantidad de valor de inventario</span><span class="sxs-lookup"><span data-stu-id="f25b7-325">Inventory value quantity</span></span></th>
    <th rowspan="2"><span data-ttu-id="f25b7-326">Valor de inventario</span><span class="sxs-lookup"><span data-stu-id="f25b7-326">Inventory value</span></span></th>
    <th rowspan="2"><span data-ttu-id="f25b7-327">Coste unitario promedio</span><span class="sxs-lookup"><span data-stu-id="f25b7-327">Average unit cost</span></span></th>
    <th colspan="2"><span data-ttu-id="f25b7-328">5/31/2020 - 5/1/2020</span><span class="sxs-lookup"><span data-stu-id="f25b7-328">5/31/2020 - 5/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="f25b7-329">4/30/2020 - 4/1/2020</span><span class="sxs-lookup"><span data-stu-id="f25b7-329">4/30/2020 - 4/1/2020</span></span></th>
    <th colspan="2"><span data-ttu-id="f25b7-330">3/31/2020 - 3/1/2020</span><span class="sxs-lookup"><span data-stu-id="f25b7-330">3/31/2020 - 3/1/2020</span></span></th>
</tr>
<tr>
    <th><span data-ttu-id="f25b7-331">P1:Cantidad</span><span class="sxs-lookup"><span data-stu-id="f25b7-331">P1:Quantity</span></span></th>
    <th><span data-ttu-id="f25b7-332">P1:Importe</span><span class="sxs-lookup"><span data-stu-id="f25b7-332">P1:Amount</span></span></th>
    <th><span data-ttu-id="f25b7-333">P2:Cantidad</span><span class="sxs-lookup"><span data-stu-id="f25b7-333">P2:Quantity</span></span></th>
    <th><span data-ttu-id="f25b7-334">P2:Importe</span><span class="sxs-lookup"><span data-stu-id="f25b7-334">P2:Amount</span></span></th>
    <th><span data-ttu-id="f25b7-335">P3:Cantidad</span><span class="sxs-lookup"><span data-stu-id="f25b7-335">P3:Quantity</span></span></th>
    <th><span data-ttu-id="f25b7-336">P3:Importe</span><span class="sxs-lookup"><span data-stu-id="f25b7-336">P3:Amount</span></span></th>
</tr>
</thead>
<tbody>
<tr>
    <td><span data-ttu-id="f25b7-337">1000</span><span class="sxs-lookup"><span data-stu-id="f25b7-337">1000</span></span></td>
    <td><span data-ttu-id="f25b7-338">1</span><span class="sxs-lookup"><span data-stu-id="f25b7-338">1</span></span></td>
    <td><span data-ttu-id="f25b7-339">11</span><span class="sxs-lookup"><span data-stu-id="f25b7-339">11</span></span></td>
    <td><span data-ttu-id="f25b7-340">10</span><span class="sxs-lookup"><span data-stu-id="f25b7-340">10</span></span></td>
    <td><span data-ttu-id="f25b7-341">910.70</span><span class="sxs-lookup"><span data-stu-id="f25b7-341">910.70</span></span></td>
    <td><span data-ttu-id="f25b7-342">14</span><span class="sxs-lookup"><span data-stu-id="f25b7-342">14</span></span></td>
    <td><span data-ttu-id="f25b7-343">1,275.00</span><span class="sxs-lookup"><span data-stu-id="f25b7-343">1,275.00</span></span></td>
    <td><span data-ttu-id="f25b7-344">91.07</span><span class="sxs-lookup"><span data-stu-id="f25b7-344">91.07</span></span></td>
    <td><span data-ttu-id="f25b7-345">0,00</span><span class="sxs-lookup"><span data-stu-id="f25b7-345">0.00</span></span></td>
    <td></td>
    <td><span data-ttu-id="f25b7-346">5.00</span><span class="sxs-lookup"><span data-stu-id="f25b7-346">5.00</span></span></td>
    <td><span data-ttu-id="f25b7-347">455.36</span><span class="sxs-lookup"><span data-stu-id="f25b7-347">455.36</span></span></td>
    <td><span data-ttu-id="f25b7-348">5.00</span><span class="sxs-lookup"><span data-stu-id="f25b7-348">5.00</span></span></td>
    <td><span data-ttu-id="f25b7-349">455.36</span><span class="sxs-lookup"><span data-stu-id="f25b7-349">455.36</span></span></td>
</tr>
<tr>
    <td><span data-ttu-id="f25b7-350">1000</span><span class="sxs-lookup"><span data-stu-id="f25b7-350">1000</span></span></td>
    <td><span data-ttu-id="f25b7-351">1</span><span class="sxs-lookup"><span data-stu-id="f25b7-351">1</span></span></td>
    <td><span data-ttu-id="f25b7-352">12</span><span class="sxs-lookup"><span data-stu-id="f25b7-352">12</span></span></td>
    <td><span data-ttu-id="f25b7-353">4</span><span class="sxs-lookup"><span data-stu-id="f25b7-353">4</span></span></td>
    <td><span data-ttu-id="f25b7-354">364.29</span><span class="sxs-lookup"><span data-stu-id="f25b7-354">364.29</span></span></td>
    <td><span data-ttu-id="f25b7-355">14</span><span class="sxs-lookup"><span data-stu-id="f25b7-355">14</span></span></td>
    <td><span data-ttu-id="f25b7-356">1,275.00</span><span class="sxs-lookup"><span data-stu-id="f25b7-356">1,275.00</span></span></td>
    <td><span data-ttu-id="f25b7-357">91.07</span><span class="sxs-lookup"><span data-stu-id="f25b7-357">91.07</span></span></td>
    <td><span data-ttu-id="f25b7-358">4.00</span><span class="sxs-lookup"><span data-stu-id="f25b7-358">4.00</span></span></td>
    <td><span data-ttu-id="f25b7-359">364.29</span><span class="sxs-lookup"><span data-stu-id="f25b7-359">364.29</span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
</tr>
<tr>
    <td><span data-ttu-id="f25b7-360">1000</span><span class="sxs-lookup"><span data-stu-id="f25b7-360">1000</span></span></td>
    <td><span data-ttu-id="f25b7-361">2</span><span class="sxs-lookup"><span data-stu-id="f25b7-361">2</span></span></td>
    <td></td>
    <td><span data-ttu-id="f25b7-362">10</span><span class="sxs-lookup"><span data-stu-id="f25b7-362">10</span></span></td>
    <td><span data-ttu-id="f25b7-363">2,000.00</span><span class="sxs-lookup"><span data-stu-id="f25b7-363">2,000.00</span></span></td>
    <td><span data-ttu-id="f25b7-364">10</span><span class="sxs-lookup"><span data-stu-id="f25b7-364">10</span></span></td>
    <td><span data-ttu-id="f25b7-365">2,000.00</span><span class="sxs-lookup"><span data-stu-id="f25b7-365">2,000.00</span></span></td>
    <td><span data-ttu-id="f25b7-366">200.00</span><span class="sxs-lookup"><span data-stu-id="f25b7-366">200.00</span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="f25b7-367">10,00</span><span class="sxs-lookup"><span data-stu-id="f25b7-367">10.00</span></span></td>
    <td><span data-ttu-id="f25b7-368">2,000.00</span><span class="sxs-lookup"><span data-stu-id="f25b7-368">2,000.00</span></span></td>
</tr>
</tbody>
<tfoot>
<tr>
    <td><span data-ttu-id="f25b7-369"><strong>1000 Totales</strong></span><span class="sxs-lookup"><span data-stu-id="f25b7-369"><strong>1000 Totals</strong></span></span></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="f25b7-370"><strong>24.00</strong></span><span class="sxs-lookup"><span data-stu-id="f25b7-370"><strong>24.00</strong></span></span></td>
    <td><span data-ttu-id="f25b7-371"><strong>3,275.00</strong></span><span class="sxs-lookup"><span data-stu-id="f25b7-371"><strong>3,275.00</strong></span></span></td>
    <td></td>
    <td></td>
    <td></td>
    <td><span data-ttu-id="f25b7-372"><strong>4.00</strong></span><span class="sxs-lookup"><span data-stu-id="f25b7-372"><strong>4.00</strong></span></span></td>
    <td><span data-ttu-id="f25b7-373"><strong>364.29</strong></span><span class="sxs-lookup"><span data-stu-id="f25b7-373"><strong>364.29</strong></span></span></td>
    <td><span data-ttu-id="f25b7-374"><strong>5.00</strong></span><span class="sxs-lookup"><span data-stu-id="f25b7-374"><strong>5.00</strong></span></span></td>
    <td><span data-ttu-id="f25b7-375"><strong>455.36</strong></span><span class="sxs-lookup"><span data-stu-id="f25b7-375"><strong>455.36</strong></span></span></td>
    <td><span data-ttu-id="f25b7-376"><strong>15</strong></span><span class="sxs-lookup"><span data-stu-id="f25b7-376"><strong>15</strong></span></span></td>
    <td><span data-ttu-id="f25b7-377"><strong>2,455.36</strong></span><span class="sxs-lookup"><span data-stu-id="f25b7-377"><strong>2,455.36</strong></span></span></td>
</tr>
</tfoot>
</table>
