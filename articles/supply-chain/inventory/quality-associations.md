---
title: Asociaciones de calidad
description: Este tema describe cómo puede usar asociaciones de calidad en Microsoft Dynamics 365 Supply Chain Management para generar automáticamente pedidos de calidad relacionados con sus procesos de venta, compra y producción.
author: rachel-profitt
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestAssociationTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2020-06-18
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6c6fab1b89b7e58d9e443c27da03a6b13afcc9c6
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "6022333"
---
# <a name="quality-associations"></a><span data-ttu-id="18dbb-103">Asociaciones de calidad</span><span class="sxs-lookup"><span data-stu-id="18dbb-103">Quality associations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="18dbb-104">Este tema describe cómo puede usar asociaciones de calidad en Microsoft Dynamics 365 Supply Chain Management para generar automáticamente pedidos de calidad relacionados con sus procesos de venta, compra y producción.</span><span class="sxs-lookup"><span data-stu-id="18dbb-104">This topic describes how you can use quality associations in Microsoft Dynamics 365 Supply Chain Management to automatically generate quality orders that are related to your sales, purchase, and production processes.</span></span>

<span data-ttu-id="18dbb-105">Una asociación de calidad define toda la información siguiente para un pedido de calidad que se genera:</span><span class="sxs-lookup"><span data-stu-id="18dbb-105">A quality association defines all the following information for a quality order that is generated:</span></span>

- <span data-ttu-id="18dbb-106">El evento de transacción</span><span class="sxs-lookup"><span data-stu-id="18dbb-106">The transaction event</span></span>
- <span data-ttu-id="18dbb-107">El conjunto de pruebas que se deben realizar en los artículos</span><span class="sxs-lookup"><span data-stu-id="18dbb-107">The set of tests that must be performed on the items</span></span>
- <span data-ttu-id="18dbb-108">Nivel de calidad aceptable (AQL)</span><span class="sxs-lookup"><span data-stu-id="18dbb-108">The acceptable quality level (AQL)</span></span>
- <span data-ttu-id="18dbb-109">El plan de muestreo</span><span class="sxs-lookup"><span data-stu-id="18dbb-109">The sampling plan</span></span>

<span data-ttu-id="18dbb-110">Debe definir una asociación de calidad para cada variación de un proceso empresarial que requiera la generación automática de pedidos de calidad.</span><span class="sxs-lookup"><span data-stu-id="18dbb-110">You must define a quality association for each variation in a business process that requires automatic generation of quality orders.</span></span> <span data-ttu-id="18dbb-111">Por ejemplo, un pedido de calidad se puede generar en los procesos empresariales para los pedidos de compra, pedidos de cuarentena, pedidos de ventas y pedidos de producción.</span><span class="sxs-lookup"><span data-stu-id="18dbb-111">For example, a quality order can be generated in the business processes for purchase orders, quarantine orders, sales orders, and production orders.</span></span>

## <a name="working-with-quality-associations"></a><span data-ttu-id="18dbb-112">Trabajar con asociaciones de calidad</span><span class="sxs-lookup"><span data-stu-id="18dbb-112">Working with quality associations</span></span>

<span data-ttu-id="18dbb-113">El proceso empresarial que utiliza una asociación de calidad puede estar relacionado con varios documentos de origen, como pedidos de compra, pedidos de ventas o pedidos de producción.</span><span class="sxs-lookup"><span data-stu-id="18dbb-113">The business process that uses a quality association can be related to various source documents, such as purchase orders, sales orders, or production orders.</span></span>

<span data-ttu-id="18dbb-114">Cada registro de asociación de calidad define el conjunto de pruebas, el nivel de calidad aceptable y el plan de muestreo que se aplica a los pedidos de calidad generados.</span><span class="sxs-lookup"><span data-stu-id="18dbb-114">Each quality association record defines the set of tests, the AQL, and the sampling plan that applies to the quality orders that are generated.</span></span> <span data-ttu-id="18dbb-115">Debe definir un registro de asociación de calidad para cada variación de un proceso empresarial.</span><span class="sxs-lookup"><span data-stu-id="18dbb-115">You must define a quality association record for each variation in a business process.</span></span> <span data-ttu-id="18dbb-116">Por ejemplo, puede configurar una asociación de calidad que genere un pedido de calidad cuando se actualice una recepción de producto de pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="18dbb-116">For example, you can set up a quality association that generates a quality order when a purchase order product receipt is updated.</span></span> <span data-ttu-id="18dbb-117">Dependiendo de la configuración del plan de ejecución, el proceso de desencadenamiento en sí puede bloquearse mientras haya un pedido de calidad abierto.</span><span class="sxs-lookup"><span data-stu-id="18dbb-117">Depending on the setup of the execution plan, the triggering process itself can be blocked while there is an open quality order.</span></span> <span data-ttu-id="18dbb-118">Alternativamente, se pueden bloquear los procesos posteriores, como la facturación de pedidos de compra.</span><span class="sxs-lookup"><span data-stu-id="18dbb-118">Alternatively, subsequent processes, such as purchase order invoicing, can be blocked.</span></span>

> [!NOTE]
> <span data-ttu-id="18dbb-119">Mientras haya pedidos de calidad abiertos, las cantidades de inventario se bloquean automáticamente para evitar su emisión.</span><span class="sxs-lookup"><span data-stu-id="18dbb-119">While there are open quality orders, inventory quantities are automatically blocked from being issued.</span></span> <span data-ttu-id="18dbb-120">En función de la configuración del campo **Bloqueo completo** de la página **Muestreos de artículos**, la cantidad es la cantidad del pedido de calidad o la cantidad de la línea del documento de origen.</span><span class="sxs-lookup"><span data-stu-id="18dbb-120">Depending on the setting of the **Full blocking** field on the **Item samplings** page, the quantity is either the quantity on the quality order or the quantity on the source document line.</span></span> <span data-ttu-id="18dbb-121">Para más información, consulte [Muestreo de elementos de gestión de calidad](quality-item-sampling.md).</span><span class="sxs-lookup"><span data-stu-id="18dbb-121">For more information, see [Quality management item sampling](quality-item-sampling.md).</span></span>

<span data-ttu-id="18dbb-122">Para un determinado proceso empresarial, el registro de la asociación de calidad identifica el evento y las condiciones para las que se genera un pedido de calidad.</span><span class="sxs-lookup"><span data-stu-id="18dbb-122">For a given business process, the quality association record identifies the event and conditions that a quality order is generated for.</span></span> <span data-ttu-id="18dbb-123">Las condiciones pueden especificarse para un sitio o para una entidad jurídica.</span><span class="sxs-lookup"><span data-stu-id="18dbb-123">The conditions can be specific to either a site or a legal entity.</span></span> <span data-ttu-id="18dbb-124">Un pedido de calidad que requiera pruebas destructivas solo se puede generar si hay un inventario disponible para el evento.</span><span class="sxs-lookup"><span data-stu-id="18dbb-124">A quality order that involves destructive tests can be generated only when on-hand inventory exists for the event.</span></span>

<span data-ttu-id="18dbb-125">Para trabajar con asociaciones de calidad, vaya a **Gestión del inventario \> Configuración \> Control de calidad \> Asociaciones de calidad**.</span><span class="sxs-lookup"><span data-stu-id="18dbb-125">To work with quality associations, go to **Inventory management \> Setup \> Quality control \> Quality associations**.</span></span> <span data-ttu-id="18dbb-126">En los siguientes ejemplos se muestra cómo se define un registro de asociación de calidad para las variantes de cada proceso empresarial.</span><span class="sxs-lookup"><span data-stu-id="18dbb-126">The following examples show how a quality association record is defined for the variations in each business process.</span></span> <span data-ttu-id="18dbb-127">Para cada ejemplo, la siguiente tabla resume los eventos y las condiciones definidos por un registro de asociación de calidad.</span><span class="sxs-lookup"><span data-stu-id="18dbb-127">For each example, the following table summarizes the events and conditions that are defined by a quality association record.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="18dbb-128">Tipo de referencia</span><span class="sxs-lookup"><span data-stu-id="18dbb-128">Reference type</span></span></th>
<th><span data-ttu-id="18dbb-129">Tipo de evento</span><span class="sxs-lookup"><span data-stu-id="18dbb-129">Event type</span></span></th>
<th><span data-ttu-id="18dbb-130">Ejecución</span><span class="sxs-lookup"><span data-stu-id="18dbb-130">Execution</span></span></th>
<th><span data-ttu-id="18dbb-131">Bloqueo de eventos</span><span class="sxs-lookup"><span data-stu-id="18dbb-131">Event blocking</span></span></th>
<th><span data-ttu-id="18dbb-132">Referencia del documento</span><span class="sxs-lookup"><span data-stu-id="18dbb-132">Document reference</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="18dbb-133">Inventario</span><span class="sxs-lookup"><span data-stu-id="18dbb-133">Inventory</span></span></td>
<td><span data-ttu-id="18dbb-134">No aplicable</span><span class="sxs-lookup"><span data-stu-id="18dbb-134">Not applicable</span></span></td>
<td><span data-ttu-id="18dbb-135">No aplicable</span><span class="sxs-lookup"><span data-stu-id="18dbb-135">Not applicable</span></span></td>
<td><span data-ttu-id="18dbb-136">Ninguna</span><span class="sxs-lookup"><span data-stu-id="18dbb-136">None</span></span></td>
<td><span data-ttu-id="18dbb-137">Todas</span><span class="sxs-lookup"><span data-stu-id="18dbb-137">All</span></span></td>
</tr>
<tr>
<td rowspan="7"><span data-ttu-id="18dbb-138">Ventas</span><span class="sxs-lookup"><span data-stu-id="18dbb-138">Sales</span></span></td>
<td rowspan="4"><span data-ttu-id="18dbb-139">Proceso de picking programado</span><span class="sxs-lookup"><span data-stu-id="18dbb-139">Picking process is scheduled</span></span></td>
<td rowspan="4"><span data-ttu-id="18dbb-140">Anterior</span><span class="sxs-lookup"><span data-stu-id="18dbb-140">Before</span></span></td>
<td><span data-ttu-id="18dbb-141">Ninguna</span><span class="sxs-lookup"><span data-stu-id="18dbb-141">None</span></span></td>
<td rowspan="22"><span data-ttu-id="18dbb-142">Solo Id. específico, Grupo o Todo</span><span class="sxs-lookup"><span data-stu-id="18dbb-142">Specific ID, Group, or All only</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18dbb-143">Proceso de picking</span><span class="sxs-lookup"><span data-stu-id="18dbb-143">Picking process</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18dbb-144">Albarán</span><span class="sxs-lookup"><span data-stu-id="18dbb-144">Packing slip</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18dbb-145">Factura</span><span class="sxs-lookup"><span data-stu-id="18dbb-145">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="18dbb-146">Albarán</span><span class="sxs-lookup"><span data-stu-id="18dbb-146">Packing slip</span></span></td>
<td rowspan="3"><span data-ttu-id="18dbb-147">Anterior</span><span class="sxs-lookup"><span data-stu-id="18dbb-147">Before</span></span></td>
<td><span data-ttu-id="18dbb-148">Ninguna</span><span class="sxs-lookup"><span data-stu-id="18dbb-148">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18dbb-149">Albarán</span><span class="sxs-lookup"><span data-stu-id="18dbb-149">Packing slip</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18dbb-150">Factura</span><span class="sxs-lookup"><span data-stu-id="18dbb-150">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="15"><span data-ttu-id="18dbb-151">Compra</span><span class="sxs-lookup"><span data-stu-id="18dbb-151">Purchase</span></span></td>
<td rowspan="7"><span data-ttu-id="18dbb-152">Lista de recepciones</span><span class="sxs-lookup"><span data-stu-id="18dbb-152">Receipt list</span></span></td>
<td rowspan="4"><span data-ttu-id="18dbb-153">Anterior</span><span class="sxs-lookup"><span data-stu-id="18dbb-153">Before</span></span></td>
<td><span data-ttu-id="18dbb-154">Ninguna</span><span class="sxs-lookup"><span data-stu-id="18dbb-154">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18dbb-155">Lista de recepciones</span><span class="sxs-lookup"><span data-stu-id="18dbb-155">Receipt list</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18dbb-156">Recepción de producto</span><span class="sxs-lookup"><span data-stu-id="18dbb-156">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18dbb-157">Factura</span><span class="sxs-lookup"><span data-stu-id="18dbb-157">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="18dbb-158">Posterior</span><span class="sxs-lookup"><span data-stu-id="18dbb-158">After</span></span></td>
<td><span data-ttu-id="18dbb-159">Ninguna</span><span class="sxs-lookup"><span data-stu-id="18dbb-159">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18dbb-160">Recepción de producto</span><span class="sxs-lookup"><span data-stu-id="18dbb-160">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18dbb-161">Factura</span><span class="sxs-lookup"><span data-stu-id="18dbb-161">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="18dbb-162">Registro</span><span class="sxs-lookup"><span data-stu-id="18dbb-162">Registration</span></span></td>
<td rowspan="3"><span data-ttu-id="18dbb-163">No aplicable</span><span class="sxs-lookup"><span data-stu-id="18dbb-163">Not applicable</span></span></td>
<td><span data-ttu-id="18dbb-164">Ninguna</span><span class="sxs-lookup"><span data-stu-id="18dbb-164">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18dbb-165">Recepción de producto</span><span class="sxs-lookup"><span data-stu-id="18dbb-165">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18dbb-166">Factura</span><span class="sxs-lookup"><span data-stu-id="18dbb-166">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="5"><span data-ttu-id="18dbb-167">Recepción de producto</span><span class="sxs-lookup"><span data-stu-id="18dbb-167">Product receipt</span></span></td>
<td rowspan="3"><span data-ttu-id="18dbb-168">Anterior</span><span class="sxs-lookup"><span data-stu-id="18dbb-168">Before</span></span></td>
<td><span data-ttu-id="18dbb-169">Ninguna</span><span class="sxs-lookup"><span data-stu-id="18dbb-169">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18dbb-170">Recepción de producto</span><span class="sxs-lookup"><span data-stu-id="18dbb-170">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18dbb-171">Factura</span><span class="sxs-lookup"><span data-stu-id="18dbb-171">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="2"><span data-ttu-id="18dbb-172">Posterior</span><span class="sxs-lookup"><span data-stu-id="18dbb-172">After</span></span></td>
<td><span data-ttu-id="18dbb-173">Ninguna</span><span class="sxs-lookup"><span data-stu-id="18dbb-173">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18dbb-174">Factura</span><span class="sxs-lookup"><span data-stu-id="18dbb-174">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="8"><span data-ttu-id="18dbb-175">Producción</span><span class="sxs-lookup"><span data-stu-id="18dbb-175">Production</span></span></td>
<td rowspan="3"><span data-ttu-id="18dbb-176">Registro</span><span class="sxs-lookup"><span data-stu-id="18dbb-176">Registration</span></span></td>
<td rowspan="3"><span data-ttu-id="18dbb-177">No aplicable</span><span class="sxs-lookup"><span data-stu-id="18dbb-177">Not applicable</span></span></td>
<td><span data-ttu-id="18dbb-178">Ninguna</span><span class="sxs-lookup"><span data-stu-id="18dbb-178">None</span></span></td>
<td rowspan="12"><span data-ttu-id="18dbb-179">Todas</span><span class="sxs-lookup"><span data-stu-id="18dbb-179">All</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18dbb-180">Notificar como terminado</span><span class="sxs-lookup"><span data-stu-id="18dbb-180">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18dbb-181">Fin</span><span class="sxs-lookup"><span data-stu-id="18dbb-181">End</span></span></td>
</tr>
<tr>
<td rowspan="5"><span data-ttu-id="18dbb-182">Notificar como terminado</span><span class="sxs-lookup"><span data-stu-id="18dbb-182">Report as finished</span></span></td>
<td rowspan="3"><span data-ttu-id="18dbb-183">Anterior</span><span class="sxs-lookup"><span data-stu-id="18dbb-183">Before</span></span></td>
<td><span data-ttu-id="18dbb-184">Ninguna</span><span class="sxs-lookup"><span data-stu-id="18dbb-184">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18dbb-185">Notificar como terminado</span><span class="sxs-lookup"><span data-stu-id="18dbb-185">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18dbb-186">Fin</span><span class="sxs-lookup"><span data-stu-id="18dbb-186">End</span></span></td>
</tr>
<tr>
<td rowspan="2"><span data-ttu-id="18dbb-187">Posterior</span><span class="sxs-lookup"><span data-stu-id="18dbb-187">After</span></span></td>
<td><span data-ttu-id="18dbb-188">Ninguna</span><span class="sxs-lookup"><span data-stu-id="18dbb-188">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18dbb-189">Fin</span><span class="sxs-lookup"><span data-stu-id="18dbb-189">End</span></span></td>
</tr>
<tr>
<td rowspan="4"><span data-ttu-id="18dbb-190">Cuarentena</span><span class="sxs-lookup"><span data-stu-id="18dbb-190">Quarantine</span></span></td>
<td rowspan="3"><span data-ttu-id="18dbb-191">Notificar como terminado</span><span class="sxs-lookup"><span data-stu-id="18dbb-191">Report as finished</span></span></td>
<td rowspan="2"><span data-ttu-id="18dbb-192">Anterior</span><span class="sxs-lookup"><span data-stu-id="18dbb-192">Before</span></span></td>
<td><span data-ttu-id="18dbb-193">Notificar como terminado</span><span class="sxs-lookup"><span data-stu-id="18dbb-193">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18dbb-194">Fin</span><span class="sxs-lookup"><span data-stu-id="18dbb-194">End</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18dbb-195">Posterior</span><span class="sxs-lookup"><span data-stu-id="18dbb-195">After</span></span></td>
<td><span data-ttu-id="18dbb-196">Fin</span><span class="sxs-lookup"><span data-stu-id="18dbb-196">End</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18dbb-197">Fin</span><span class="sxs-lookup"><span data-stu-id="18dbb-197">End</span></span></td>
<td><span data-ttu-id="18dbb-198">Anterior</span><span class="sxs-lookup"><span data-stu-id="18dbb-198">Before</span></span></td>
<td><span data-ttu-id="18dbb-199">Fin</span><span class="sxs-lookup"><span data-stu-id="18dbb-199">End</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="18dbb-200">Operación de ruta</span><span class="sxs-lookup"><span data-stu-id="18dbb-200">Route operation</span></span></td>
<td rowspan="3"><span data-ttu-id="18dbb-201">Notificar como terminado</span><span class="sxs-lookup"><span data-stu-id="18dbb-201">Report as finished</span></span></td>
<td rowspan="2"><span data-ttu-id="18dbb-202">Antes</span><span class="sxs-lookup"><span data-stu-id="18dbb-202">Before</span></span></td>
<td><span data-ttu-id="18dbb-203">None</span><span class="sxs-lookup"><span data-stu-id="18dbb-203">None</span></span></td>
<td rowspan="3"><span data-ttu-id="18dbb-204">Id. específico, Grupo o Todo, y Recurso específico, Grupo o Todo</span><span class="sxs-lookup"><span data-stu-id="18dbb-204">Specific ID, Group, or All, and specific Resource, Group, or All</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18dbb-205">Notificar como terminado</span><span class="sxs-lookup"><span data-stu-id="18dbb-205">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18dbb-206">Posterior</span><span class="sxs-lookup"><span data-stu-id="18dbb-206">After</span></span></td>
<td><span data-ttu-id="18dbb-207">None</span><span class="sxs-lookup"><span data-stu-id="18dbb-207">None</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="18dbb-208">Producción de coproductos</span><span class="sxs-lookup"><span data-stu-id="18dbb-208">Co-product production</span></span></td>
<td><span data-ttu-id="18dbb-209">Registro</span><span class="sxs-lookup"><span data-stu-id="18dbb-209">Registration</span></span></td>
<td><span data-ttu-id="18dbb-210">No aplicable</span><span class="sxs-lookup"><span data-stu-id="18dbb-210">Not applicable</span></span></td>
<td rowspan="3"><span data-ttu-id="18dbb-211">None</span><span class="sxs-lookup"><span data-stu-id="18dbb-211">None</span></span></td>
<td rowspan="3"><span data-ttu-id="18dbb-212">Todos</span><span class="sxs-lookup"><span data-stu-id="18dbb-212">All</span></span></td>
</tr>
<tr>
<td rowspan="2"><span data-ttu-id="18dbb-213">Notificar como terminado</span><span class="sxs-lookup"><span data-stu-id="18dbb-213">Report as finished</span></span></td>
<td><span data-ttu-id="18dbb-214">Antes</span><span class="sxs-lookup"><span data-stu-id="18dbb-214">Before</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18dbb-215">Posterior</span><span class="sxs-lookup"><span data-stu-id="18dbb-215">After</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="18dbb-216">La característica *Gestión de calidad para procesos de almacén* agrega capacidades para el procesamiento de pedidos de calidad para la producción cuando el campo **Tipo de evento** está establecido en *Informar como terminado* y el campo **Ejecución** está establecido en *Después*, y para compras con el campo **Tipo de evento** establecido en *Registro*.</span><span class="sxs-lookup"><span data-stu-id="18dbb-216">The *Quality management for warehouse processes* feature adds capabilities for quality order processing for production where the **Event type** field is set to *Report as finished* and the **Execution** field is set to *After*, and for purchases where the **Event type** field is set to *Registration*.</span></span> <span data-ttu-id="18dbb-217">Para más información, consulte [Administración de calidad para procesos de almacén](quality-management-for-warehouses-processes.md).</span><span class="sxs-lookup"><span data-stu-id="18dbb-217">For more information, see [Quality management for warehouse processes](quality-management-for-warehouses-processes.md).</span></span>

<span data-ttu-id="18dbb-218">La siguiente tabla proporciona más información acerca de cómo se pueden generar los pedidos de calidad para tipos de procesos concretos.</span><span class="sxs-lookup"><span data-stu-id="18dbb-218">The following table provides more information about how quality orders can be generated for specific types of processes.</span></span>

<div class="tableSection">
<table>
<thead>
<tr>
<th><span data-ttu-id="18dbb-219">Tipo de proceso</span><span class="sxs-lookup"><span data-stu-id="18dbb-219">Type of process</span></span></th>
<th><span data-ttu-id="18dbb-220">Cuando los pedidos de calidad se pueden generar automáticamente</span><span class="sxs-lookup"><span data-stu-id="18dbb-220">When quality orders can be automatically generated</span></span></th>
<th><span data-ttu-id="18dbb-221">Cuando los pedidos de calidad se pueden generar si se requiere una prueba destructiva</span><span class="sxs-lookup"><span data-stu-id="18dbb-221">When quality orders can be generated if destructive testing is required</span></span></th>
<th><span data-ttu-id="18dbb-222">Información acerca de la condición</span><span class="sxs-lookup"><span data-stu-id="18dbb-222">Condition information</span></span></th>
<th><span data-ttu-id="18dbb-223">Información acerca de la generación manual</span><span class="sxs-lookup"><span data-stu-id="18dbb-223">Manual generation information</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="18dbb-224">Pedido de compra</span><span class="sxs-lookup"><span data-stu-id="18dbb-224">Purchase order</span></span></td>
<td><span data-ttu-id="18dbb-225">Antes o después de que se registre una lista de recepciones o una recepción de producto del material recibido</span><span class="sxs-lookup"><span data-stu-id="18dbb-225">Before or after a receipts list or product receipt for the material that is received is posted</span></span></td>
<td><span data-ttu-id="18dbb-226">Después del registro de la recepción de producto, ya que el material debe estar disponible para la prueba destructiva</span><span class="sxs-lookup"><span data-stu-id="18dbb-226">After the product receipt for the material that is received is posted, because the material must be available for destructive testing</span></span></td>
<td><span data-ttu-id="18dbb-227">El requisito de un pedido de calidad puede reflejar un sitio, un artículo o proveedor específico, además de una combinación de estas condiciones.</span><span class="sxs-lookup"><span data-stu-id="18dbb-227">The requirement for a quality order can reflect a specific site, item, or vendor, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="18dbb-228">Un pedido de calidad generado manualmente que hace referencia a un pedido de compra puede usar la información de un registro de asociación de calidad, como el plan de muestreo de la prueba.</span><span class="sxs-lookup"><span data-stu-id="18dbb-228">A manually generated quality order that refers to a purchase order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18dbb-229">Orden de cuarentena</span><span class="sxs-lookup"><span data-stu-id="18dbb-229">Quarantine order</span></span></td>
<td><span data-ttu-id="18dbb-230">Antes o después de que se notifique que ha finalizado la orden de cuarentena</span><span class="sxs-lookup"><span data-stu-id="18dbb-230">Before or after the quarantine order is reported as finished or ended</span></span></td>
<td><span data-ttu-id="18dbb-231">No se pueden generar pedidos de calidad que necesiten pruebas destructivas.</span><span class="sxs-lookup"><span data-stu-id="18dbb-231">Quality orders that require destructive tests can't be generated.</span></span> <span data-ttu-id="18dbb-232">Se supone que la funcionalidad de la orden de cuarentena gestiona la disposición del material destruido.</span><span class="sxs-lookup"><span data-stu-id="18dbb-232">It's assumed that the quarantine order functionality handles the disposition of the material that is destroyed.</span></span></td>
<td><span data-ttu-id="18dbb-233">El requisito de un pedido de calidad puede reflejar un sitio, un artículo o proveedor específico, además de una combinación de estas condiciones.</span><span class="sxs-lookup"><span data-stu-id="18dbb-233">The requirement for a quality order can reflect a specific site, item, or vendor, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="18dbb-234">Un pedido de calidad generado manualmente que hace referencia a una orden de cuarentena puede usar la información de un registro de asociación de calidad, como el plan de muestreo de la prueba.</span><span class="sxs-lookup"><span data-stu-id="18dbb-234">A manually generated quality order that refers to a quarantine order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18dbb-235">Pedido de ventas</span><span class="sxs-lookup"><span data-stu-id="18dbb-235">Sales order</span></span></td>
<td><span data-ttu-id="18dbb-236">Antes de una actualización programada del proceso de selección o del albarán para los artículos que se envían</span><span class="sxs-lookup"><span data-stu-id="18dbb-236">Before a scheduled picking process or packing slip update for the items that are being shipped</span></span></td>
<td><span data-ttu-id="18dbb-237">En cualquier paso</span><span class="sxs-lookup"><span data-stu-id="18dbb-237">At any step</span></span></td>
<td><span data-ttu-id="18dbb-238">El requisito de un pedido de calidad puede reflejar un sitio, un artículo o un cliente específico, además de una combinación de estas condiciones.</span><span class="sxs-lookup"><span data-stu-id="18dbb-238">The requirement for a quality order can reflect a specific site, item, or customer, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="18dbb-239">Un pedido de calidad generado manualmente que hace referencia a un pedido de ventas puede usar la información de un registro de asociación de calidad, como el plan de muestreo de la prueba.</span><span class="sxs-lookup"><span data-stu-id="18dbb-239">A manually generated quality order that refers to a sales order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18dbb-240">Pedido de producción</span><span class="sxs-lookup"><span data-stu-id="18dbb-240">Production order</span></span></td>
<td><span data-ttu-id="18dbb-241">Antes o después de que se registre la cantidad finalizada del pedido de producción</span><span class="sxs-lookup"><span data-stu-id="18dbb-241">Before or after the finished quantity for the production order is reported</span></span></td>
<td><span data-ttu-id="18dbb-242">Después de que se registre la cantidad finalizada del pedido de producción</span><span class="sxs-lookup"><span data-stu-id="18dbb-242">After the finished quantity for the production order is reported</span></span></td>
<td><span data-ttu-id="18dbb-243">El requisito de un pedido de calidad puede reflejar un sitio o un artículo específico, o una combinación de estas condiciones.</span><span class="sxs-lookup"><span data-stu-id="18dbb-243">The requirement for a quality order can reflect a specific site or item, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="18dbb-244">Un pedido de calidad generado manualmente que hace referencia a un pedido de producción puede usar la información de un registro de asociación de calidad, como el plan de muestreo de la prueba.</span><span class="sxs-lookup"><span data-stu-id="18dbb-244">A manually generated quality order that refers to a production order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18dbb-245">Pedido de producción con una operación de ruta</span><span class="sxs-lookup"><span data-stu-id="18dbb-245">Production order that has a route operation</span></span></td>
<td><span data-ttu-id="18dbb-246">Antes o después de finalizar el informe de la operación</span><span class="sxs-lookup"><span data-stu-id="18dbb-246">Before or after the report is finished for an operation</span></span></td>
<td><span data-ttu-id="18dbb-247">Después de finalizar el informe de producción de la última operación</span><span class="sxs-lookup"><span data-stu-id="18dbb-247">After the reporting production is finished for the last operation</span></span></td>
<td><span data-ttu-id="18dbb-248">El requisito de un pedido de calidad puede reflejar un sitio, un artículo o un recurso de operaciones específicos, además de una combinación de estas condiciones.</span><span class="sxs-lookup"><span data-stu-id="18dbb-248">The requirement for a quality order can reflect a specific site, item, or operations resource, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="18dbb-249">Un pedido de calidad generado manualmente que hace referencia a una operación de ruta puede usar la información de un registro de asociación de calidad, como el plan de muestreo de la prueba.</span><span class="sxs-lookup"><span data-stu-id="18dbb-249">A manually generated quality order that refers to a route operation can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="18dbb-250">Inventario</span><span class="sxs-lookup"><span data-stu-id="18dbb-250">Inventory</span></span></td>
<td><span data-ttu-id="18dbb-251">Un pedido de calidad no se puede generar automáticamente para una transacción en un diario de inventario ni para las transacciones de un pedido de transferencia.</span><span class="sxs-lookup"><span data-stu-id="18dbb-251">A quality order can't be automatically generated for a transaction in an inventory journal or for transfer order transactions.</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="18dbb-252">Un pedido de calidad se debe crear manualmente para la cantidad de inventario de un artículo.</span><span class="sxs-lookup"><span data-stu-id="18dbb-252">A quality order must be manually created for an item's inventory quantity.</span></span> <span data-ttu-id="18dbb-253">Se requiere el inventario físico disponible.</span><span class="sxs-lookup"><span data-stu-id="18dbb-253">Physical on-hand inventory is required.</span></span></td>
</tr>
</tbody>
</table>
</div>

## <a name="examples-of-automatic-generation-of-quality-orders"></a><span data-ttu-id="18dbb-254">Ejemplos de generación automática de pedidos de calidad</span><span class="sxs-lookup"><span data-stu-id="18dbb-254">Examples of automatic generation of quality orders</span></span>

### <a name="purchasing"></a><span data-ttu-id="18dbb-255">Compras</span><span class="sxs-lookup"><span data-stu-id="18dbb-255">Purchasing</span></span>

<span data-ttu-id="18dbb-256">En la compra, si establece el campo **Tipo de evento** en *Recepción de producto* y el campo **Ejecución** en *Después* en la página **Asociaciones de calidad**, obtiene los resultados siguientes:</span><span class="sxs-lookup"><span data-stu-id="18dbb-256">In purchasing, if you set the **Event type** field to *Product receipt* and the **Execution** field to *After* on the **Quality associations** page, you get the following results:</span></span>

- <span data-ttu-id="18dbb-257">Si la opción **Por cantidad actualizada** se establece en *Sí*, un pedido de calidad se genera para cada recepción con el pedido de compra, en función de la cantidad y los valores recibidos en el muestreo de artículos.</span><span class="sxs-lookup"><span data-stu-id="18dbb-257">If the **Per updated quantity** option is set to *Yes*, a quality order is generated for every receipt against the purchase order, based on the received quantity and settings in the item sampling.</span></span> <span data-ttu-id="18dbb-258">Cada vez que una cantidad se reciba contra el pedido de compra, los nuevos pedidos de calidad se generan en función de la cantidad recién recibida.</span><span class="sxs-lookup"><span data-stu-id="18dbb-258">Every time that a quantity is received against the purchase order, new quality orders are generated based on the newly received quantity.</span></span>
- <span data-ttu-id="18dbb-259">Si la opción **Por cantidad actualizada** se establece en *No*, un pedido de calidad se genera para la primera recepción con el pedido de compra, en función de la cantidad recibida.</span><span class="sxs-lookup"><span data-stu-id="18dbb-259">If the **Per updated quantity** option is set to *No*, a quality order is generated for the first receipt against the purchase order, based on the received quantity.</span></span> <span data-ttu-id="18dbb-260">Además, uno o más pedidos de calidad se crean en función de la cantidad restante, en función de las dimensiones de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="18dbb-260">Additionally, one or more quality orders are created based on the remaining quantity, depending on the tracking dimensions.</span></span> <span data-ttu-id="18dbb-261">Los pedidos de calidad no se generan para las recepciones posteriores con el pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="18dbb-261">Quality orders aren't generated for subsequent receipts against the purchase order.</span></span>

### <a name="production"></a><span data-ttu-id="18dbb-262">Producción</span><span class="sxs-lookup"><span data-stu-id="18dbb-262">Production</span></span>

<span data-ttu-id="18dbb-263">En la producción, si establece el campo **Tipo de evento** en *Informar como completado* y el campo **Ejecución** en *Después* en la página **Asociaciones de calidad**, obtiene los resultados siguientes:</span><span class="sxs-lookup"><span data-stu-id="18dbb-263">In production, if you set the **Event type** field to *Report as finished* and the **Execution** field to *After* on the **Quality associations** page, you get the following results:</span></span>

- <span data-ttu-id="18dbb-264">Si la opción **Por cantidad actualizada** se establece en *Sí*, un pedido de calidad se genera para cada cantidad y valores completados en el muestreo de artículos.</span><span class="sxs-lookup"><span data-stu-id="18dbb-264">If the **Per updated quantity** option is set to *Yes*, a quality order is generated based on every finished quantity and settings in the item sampling.</span></span> <span data-ttu-id="18dbb-265">Cada vez que una cantidad se notifique como terminada frente al pedido de producción, los nuevos pedidos de calidad se generan en función de la cantidad recién terminada.</span><span class="sxs-lookup"><span data-stu-id="18dbb-265">Every time that a quantity is reported as finished against the production order, new quality orders are generated based on the newly finished quantity.</span></span> <span data-ttu-id="18dbb-266">Esta lógica de la generación es coherente con la compra.</span><span class="sxs-lookup"><span data-stu-id="18dbb-266">This generation logic is consistent with purchasing.</span></span>
- <span data-ttu-id="18dbb-267">Si la opción **Por cantidad actualizada** se establece en *No*, un pedido de calidad se genera para la primera vez que una cantidad se notifica como terminada, en función de la cantidad terminada.</span><span class="sxs-lookup"><span data-stu-id="18dbb-267">If the **Per updated quantity** option is set to *No*, a quality order is generated the first time that a quantity is reported as finished, based on the finished quantity.</span></span> <span data-ttu-id="18dbb-268">Además, uno o más pedidos de calidad se crean en función de la cantidad restante, en función de las dimensiones de seguimiento del muestreo del artículo.</span><span class="sxs-lookup"><span data-stu-id="18dbb-268">Additionally, one or more quality orders are created based on the remaining quantity, depending on the tracking dimensions of the item sampling.</span></span> <span data-ttu-id="18dbb-269">Los pedidos de calidad no se generan para las cantidades finalizadas posteriores.</span><span class="sxs-lookup"><span data-stu-id="18dbb-269">Quality orders aren't generated for subsequent finished quantities.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="18dbb-270">Especificación de calidad</span><span class="sxs-lookup"><span data-stu-id="18dbb-270">Quality specification</span></span></th>
<th><span data-ttu-id="18dbb-271">Por cantidad actualizada</span><span class="sxs-lookup"><span data-stu-id="18dbb-271">Per updated quantity</span></span></th>
<th><span data-ttu-id="18dbb-272">Por dimensión de seguimiento</span><span class="sxs-lookup"><span data-stu-id="18dbb-272">Per tracking dimension</span></span></th>
<th><span data-ttu-id="18dbb-273">Resultado</span><span class="sxs-lookup"><span data-stu-id="18dbb-273">Result</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="18dbb-274">Porcentaje: 10 %</span><span class="sxs-lookup"><span data-stu-id="18dbb-274">Percentage: 10%</span></span></td>
<td><span data-ttu-id="18dbb-275">Sí</span><span class="sxs-lookup"><span data-stu-id="18dbb-275">Yes</span></span></td>
<td>
<p><span data-ttu-id="18dbb-276">Número de lote: No</span><span class="sxs-lookup"><span data-stu-id="18dbb-276">Batch number: No</span></span></p>
<p><span data-ttu-id="18dbb-277">Número de serie: No</span><span class="sxs-lookup"><span data-stu-id="18dbb-277">Serial number: No</span></span></p>
</td>
<td>
<p><span data-ttu-id="18dbb-278">Cantidad de pedido: 100</span><span class="sxs-lookup"><span data-stu-id="18dbb-278">Order quantity: 100</span></span></p>
<ol>
<li><span data-ttu-id="18dbb-279">Notificar como terminado para 30</span><span class="sxs-lookup"><span data-stu-id="18dbb-279">Report as finished for 30</span></span>
<ul>
<li><span data-ttu-id="18dbb-280">Pedido de calidad 1 para 3 (10 % de 30)</span><span class="sxs-lookup"><span data-stu-id="18dbb-280">Quality order 1 for 3 (10% of 30)</span></span></li>
</ul>
</li>
<li><span data-ttu-id="18dbb-281">Notificar como terminado para 70</span><span class="sxs-lookup"><span data-stu-id="18dbb-281">Report as finished for 70</span></span>
<ul>
<li><span data-ttu-id="18dbb-282">Pedido de calidad 2 para 7 (10 % de la cantidad de pedidos restantes, que es 70 en este caso)</span><span class="sxs-lookup"><span data-stu-id="18dbb-282">Quality order 2 for 7 (10% of the remaining order quantity, which is 70 in this case)</span></span></li>
</ul>
</li>
</ol>
</td>
</tr>
<tr>
<td><span data-ttu-id="18dbb-283">Cantidad fija: 1</span><span class="sxs-lookup"><span data-stu-id="18dbb-283">Fixed quantity: 1</span></span></td>
<td><span data-ttu-id="18dbb-284">N.º</span><span class="sxs-lookup"><span data-stu-id="18dbb-284">No</span></span></td>
<td>
<p><span data-ttu-id="18dbb-285">Número de lote: No</span><span class="sxs-lookup"><span data-stu-id="18dbb-285">Batch number: No</span></span></p>
<p><span data-ttu-id="18dbb-286">Número de serie: No</span><span class="sxs-lookup"><span data-stu-id="18dbb-286">Serial number: No</span></span></p>
</td>
<td><span data-ttu-id="18dbb-287">Cantidad de pedido: 100</span><span class="sxs-lookup"><span data-stu-id="18dbb-287">Order quantity: 100</span></span>
<ol>
<li><span data-ttu-id="18dbb-288">Notificar como terminado para 30</span><span class="sxs-lookup"><span data-stu-id="18dbb-288">Report as finished for 30</span></span>
<ul>
<li><span data-ttu-id="18dbb-289">El pedido de calidad 1 para 1 (para la primera cantidad notificada como terminada, que tiene un valor fijo de 1)</span><span class="sxs-lookup"><span data-stu-id="18dbb-289">Quality order 1 for 1 (for the first reported-as-finished quantity, which has a fixed value of 1)</span></span></li>
<li><span data-ttu-id="18dbb-290">El pedido de calidad 2 para 1 (para la cantidad restante, que todavía tiene un valor fijo de 1)</span><span class="sxs-lookup"><span data-stu-id="18dbb-290">Quality order 2 for 1 (for the remaining quantity, which still has a fixed value of 1)</span></span></li>
</ul>
</li>
<li><span data-ttu-id="18dbb-291">Notificar como terminado para 10</span><span class="sxs-lookup"><span data-stu-id="18dbb-291">Report as finished for 10</span></span>
<ul>
<li><span data-ttu-id="18dbb-292">No se crea ningún pedido de calidad.</span><span class="sxs-lookup"><span data-stu-id="18dbb-292">No quality orders are created.</span></span></li>
</ul>
</li>
<li><span data-ttu-id="18dbb-293">Notificar como terminado para 60</span><span class="sxs-lookup"><span data-stu-id="18dbb-293">Report as finished for 60</span></span>
<ul>
<li><span data-ttu-id="18dbb-294">No se crea ningún pedido de calidad.</span><span class="sxs-lookup"><span data-stu-id="18dbb-294">No quality orders are created.</span></span></li>
</ul>
</li>
</ol>
</td>
</tr>
<tr>
<td><span data-ttu-id="18dbb-295">Cantidad fija: 1</span><span class="sxs-lookup"><span data-stu-id="18dbb-295">Fixed quantity: 1</span></span></td>
<td><span data-ttu-id="18dbb-296">Sí</span><span class="sxs-lookup"><span data-stu-id="18dbb-296">Yes</span></span></td>
<td>
<p><span data-ttu-id="18dbb-297">Número de lote: Sí</span><span class="sxs-lookup"><span data-stu-id="18dbb-297">Batch number: Yes</span></span></p>
<p><span data-ttu-id="18dbb-298">Número de serie: Sí</span><span class="sxs-lookup"><span data-stu-id="18dbb-298">Serial number: Yes</span></span></p>
</td>
<td>
<p><span data-ttu-id="18dbb-299">Cantidad de pedido: 10</span><span class="sxs-lookup"><span data-stu-id="18dbb-299">Order quantity: 10</span></span></p>
<ol>
<li><span data-ttu-id="18dbb-300">Informe como terminado para 3: 1 para el número de lote b1, número de serie s1; 1 para el número de lote b2, número de serie s2; y 1 para el número de lote b3, número de serie s3</span><span class="sxs-lookup"><span data-stu-id="18dbb-300">Report as finished for 3: 1 for batch number b1, serial number s1; 1 for batch number b2, serial number s2; and 1 for batch number b3, serial number s3</span></span>
<ul>
<li><span data-ttu-id="18dbb-301">Pedido de calidad 1 para 1 del número de lote b1, número de serie s1</span><span class="sxs-lookup"><span data-stu-id="18dbb-301">Quality order 1 for 1 of batch number b1, serial number s1</span></span></li>
<li><span data-ttu-id="18dbb-302">Pedido de calidad 2 para 1 del número de lote b2, número de serie s2</span><span class="sxs-lookup"><span data-stu-id="18dbb-302">Quality order 2 for 1 of batch number b2, serial number s2</span></span></li>
<li><span data-ttu-id="18dbb-303">Pedido de calidad 3 para 1 del número de lote b3, número de serie s3</span><span class="sxs-lookup"><span data-stu-id="18dbb-303">Quality order 3 for 1 of batch number b3, serial number s3</span></span></li>
</ul>
</li>
<li><span data-ttu-id="18dbb-304">Informe como terminado para 2: 1 para el número de lote b4, número de serie s4; y 1 para el número de lote b5, número de serie s5</span><span class="sxs-lookup"><span data-stu-id="18dbb-304">Report as finished for 2: 1 for batch number b4, serial number s4; and 1 for batch number b5, serial number s5</span></span>
<ul>
<li><span data-ttu-id="18dbb-305">Pedido de calidad 4 para 1 del número de lote b4, número de serie s4</span><span class="sxs-lookup"><span data-stu-id="18dbb-305">Quality order 4 for 1 of batch number b4, serial number s4</span></span></li>
<li><span data-ttu-id="18dbb-306">Pedido de calidad 5 para 1 del número de lote b5, número de serie s5</span><span class="sxs-lookup"><span data-stu-id="18dbb-306">Quality order 5 for 1 of batch number b5, serial number s5</span></span></li>
</ul>
</li>
</ol>
<p><span data-ttu-id="18dbb-307"><strong>Nota:</strong> El lote se puede volver a utilizar.</span><span class="sxs-lookup"><span data-stu-id="18dbb-307"><strong>Note:</strong> The batch can be reused.</span></span></p>
</td>
</tr>
<tr>
<td><span data-ttu-id="18dbb-308">Cantidad fija: 2</span><span class="sxs-lookup"><span data-stu-id="18dbb-308">Fixed quantity: 2</span></span></td>
<td><span data-ttu-id="18dbb-309">N.º</span><span class="sxs-lookup"><span data-stu-id="18dbb-309">No</span></span></td>
<td>
<p><span data-ttu-id="18dbb-310">Número de lote: Sí</span><span class="sxs-lookup"><span data-stu-id="18dbb-310">Batch number: Yes</span></span></p>
<p><span data-ttu-id="18dbb-311">Número de serie: Sí</span><span class="sxs-lookup"><span data-stu-id="18dbb-311">Serial number: Yes</span></span></p>
</td>
<td>
<p><span data-ttu-id="18dbb-312">Cantidad de pedido: 10</span><span class="sxs-lookup"><span data-stu-id="18dbb-312">Order quantity: 10</span></span></p>
<ol>
<li><span data-ttu-id="18dbb-313">Informe como terminado para 4: 1 para el número de lote b1, número de serie s1; 1 para el número de lote b2, número de serie s2; y 1 para el número de lote b3, número de serie s3; y 1 para el número de lote b4, número de serie s4</span><span class="sxs-lookup"><span data-stu-id="18dbb-313">Report as finished for 4: 1 for batch number b1, serial number s1; 1 for batch number b2, serial number s2; 1 for batch number b3, serial number s3; and 1 for batch number b4, serial number s4</span></span>
<ul>
<li><span data-ttu-id="18dbb-314">Pedido de calidad 1 para 1 del número de lote b1, número de serie s1</span><span class="sxs-lookup"><span data-stu-id="18dbb-314">Quality order 1 for 1 of batch number b1, serial number s1</span></span></li>
<li><span data-ttu-id="18dbb-315">Pedido de calidad 2 para 1 del número de lote b2, número de serie s2</span><span class="sxs-lookup"><span data-stu-id="18dbb-315">Quality order 2 for 1 of batch number b2, serial number s2</span></span></li>
<li><span data-ttu-id="18dbb-316">Pedido de calidad 3 para 1 del número de lote b3, número de serie s3</span><span class="sxs-lookup"><span data-stu-id="18dbb-316">Quality order 3 for 1 of batch number b3, serial number s3</span></span></li>
<li><span data-ttu-id="18dbb-317">Pedido de calidad 4 para 1 del número de lote b4, número de serie s4</span><span class="sxs-lookup"><span data-stu-id="18dbb-317">Quality order 4 for 1 of batch number b4, serial number s4</span></span></li>
</ul>
<ul>
<li><span data-ttu-id="18dbb-318">Pedido de calidad 5 para 2, sin una referencia a un número de lote y un número de serie</span><span class="sxs-lookup"><span data-stu-id="18dbb-318">Quality order 5 for 2, without a reference to a batch number and a serial number</span></span></li>
</ul>
</li>
<li><span data-ttu-id="18dbb-319">Informe como terminado para 6: 1 para el número de lote b5, número de serie s5; 1 para el número de lote b6, número de serie s6; 1 para el número de lote b7, número de serie s7; 1 para el número de lote b8, número de serie s8; 1 para el número de lote b9, número de serie s9; y 1 para el número de lote b10, número de serie s10</span><span class="sxs-lookup"><span data-stu-id="18dbb-319">Report as finished for 6: 1 for batch number b5, serial number s5; 1 for batch number b6, serial number s6; 1 for batch number b7, serial number s7; 1 for batch number b8, serial number s8; 1 for batch number b9, serial number s9; and 1 for batch number b10, serial number s10</span></span>
<ul>
<li><span data-ttu-id="18dbb-320">No se crea ningún pedido de calidad.</span><span class="sxs-lookup"><span data-stu-id="18dbb-320">No quality orders are created.</span></span></li>
</ul>
</li>
</ol>
</td>
</tr>
</tbody>
</table>

## <a name="additional-resources"></a><span data-ttu-id="18dbb-321">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="18dbb-321">Additional resources</span></span>

- [<span data-ttu-id="18dbb-322">Procesos de administración de la calidad</span><span class="sxs-lookup"><span data-stu-id="18dbb-322">Quality management processes</span></span>](quality-management-processes.md)
- [<span data-ttu-id="18dbb-323">Habilitar la gestión de la calidad y las no conformidades</span><span class="sxs-lookup"><span data-stu-id="18dbb-323">Enable quality and nonconformance management</span></span>](enable-quality-management.md)
- [<span data-ttu-id="18dbb-324">Administración de la calidad para procesos de almacén</span><span class="sxs-lookup"><span data-stu-id="18dbb-324">Quality management for warehouse processes</span></span>](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
