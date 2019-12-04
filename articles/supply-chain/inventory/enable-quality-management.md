---
title: Visión general de la gestión de la calidad
description: Este tema describe cómo puede usar la gestión de calidad en Dynamics 365 Supply Chain Management para ayudar a mejorar la calidad del producto dentro de la cadena de suministro.
author: perlynne
manager: AnnBe
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventTestAssociationTable, InventTestGroup, InventTestItemQualityGroup, InventTestTable, InventTestVariable, InventTestVariableOutcome
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c2d51c659d9d06f075458359d81de978e7a6d14b
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2019
ms.locfileid: "2814407"
---
# <a name="quality-management-overview"></a><span data-ttu-id="bab0e-103">Visión general de la gestión de la calidad</span><span class="sxs-lookup"><span data-stu-id="bab0e-103">Quality management overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="bab0e-104">Este tema describe cómo puede usar la gestión de calidad en Dynamics 365 Supply Chain Management para ayudar a mejorar la calidad del producto dentro de la cadena de suministro.</span><span class="sxs-lookup"><span data-stu-id="bab0e-104">This topic describes how you can use quality management in Dynamics 365 Supply Chain Management to help improve product quality within your supply chain.</span></span>

<span data-ttu-id="bab0e-105">La gestión de calidad puede ayudarle a gestionar los plazos de entrega cuando maneja productos de disconformidad, independientemente de su punto de origen.</span><span class="sxs-lookup"><span data-stu-id="bab0e-105">Quality management can help you manage turnaround times when you handle nonconforming products, regardless of their point of origin.</span></span> <span data-ttu-id="bab0e-106">Dado que los tipos de diagnóstico están vinculados a la corrección de los informes, Supply Chain Management puede programar las tareas para corregir los problemas y evitar que se repitan.</span><span class="sxs-lookup"><span data-stu-id="bab0e-106">Because diagnostic types are linked to correction reporting, Supply Chain Management can schedule tasks to correct problems and prevent them from recurring.</span></span>

<span data-ttu-id="bab0e-107">Además de la funcionalidad para gestionar la no conformidad, la gestión de calidad incluye la funcionalidad de realizar un seguimiento de las incidencias por tipo de problema (incluso problemas internos) y para identificar soluciones a corto plazo o a largo plazo.</span><span class="sxs-lookup"><span data-stu-id="bab0e-107">In addition to functionality for managing nonconformance, quality management includes functionality for tracking issues by problem type (even internal problems), and for identifying solutions as short-term or long-term.</span></span> <span data-ttu-id="bab0e-108">Las estadísticas acerca de los indicadores clave de rendimiento (KPI) proporcionan información sobre el historial de problemas de disconformidad anteriores y las soluciones utilizadas para corregirlos.</span><span class="sxs-lookup"><span data-stu-id="bab0e-108">Statistics about key performance indicators (KPIs) provide insight into the history of previous nonconformance issues and the solutions that were used to correct them.</span></span> <span data-ttu-id="bab0e-109">Puede usar los datos históricos para revisar la eficacia de las medidas de calidad anteriores y determinar las medidas adecuadas que se deben usar en el futuro.</span><span class="sxs-lookup"><span data-stu-id="bab0e-109">You can use historical data to review the effectiveness of previous quality measures and determine appropriate measures to use in the future.</span></span>

<span data-ttu-id="bab0e-110">Al configurar una asociación de calidad, Supply Chain Management puede generar pedidos de calidad para varios procesos empresariales, eventos y condiciones.</span><span class="sxs-lookup"><span data-stu-id="bab0e-110">When you set up a quality association, Supply Chain Management can generate quality orders for various business processes, events, and conditions.</span></span> <span data-ttu-id="bab0e-111">La asociación de calidad puede cubrir un artículo concreto, un determinado grupo de éstos o todos los artículos.</span><span class="sxs-lookup"><span data-stu-id="bab0e-111">The quality association can cover a specific item, a specific group of items, or all items.</span></span>

## <a name="examples-of-the-use-of-quality-management"></a><span data-ttu-id="bab0e-112">Ejemplos del uso de la gestión de calidad</span><span class="sxs-lookup"><span data-stu-id="bab0e-112">Examples of the use of quality management</span></span>
<span data-ttu-id="bab0e-113">La gestión de calidad es flexible y puede ejecutarse de distintas maneras para satisfacer los requisitos de niveles específicos de operaciones de la cadena de suministro.</span><span class="sxs-lookup"><span data-stu-id="bab0e-113">Quality management is flexible and can be implemented in various ways to meet the requirements of specific levels of supply chain operations.</span></span> <span data-ttu-id="bab0e-114">En los ejemplos siguientes se muestran usos posibles de estas características:</span><span class="sxs-lookup"><span data-stu-id="bab0e-114">The following examples illustrate possible uses of these features:</span></span>

-   <span data-ttu-id="bab0e-115">Inicie automáticamente un proceso de control de calidad en función de los criterios predefinidos (sobre el registro del almacén de un pedido de compra para un proveedor específico).</span><span class="sxs-lookup"><span data-stu-id="bab0e-115">Automatically start a quality control process, based on predefined criteria (upon warehouse registration of a purchase order from a specific vendor).</span></span>
-   <span data-ttu-id="bab0e-116">Bloquear el inventario durante la inspección para evitar que el inventario no aprobado se use (bloqueo completo de las cantidades de pedido de compra).</span><span class="sxs-lookup"><span data-stu-id="bab0e-116">Block inventory during inspection to prevent non-approved inventory from being used (full blocking of purchase order quantities).</span></span>
-   <span data-ttu-id="bab0e-117">Use el muestreo del artículo como parte de una asociación de calidad para definir la cantidad de inventario físico actual que debe inspeccionarse.</span><span class="sxs-lookup"><span data-stu-id="bab0e-117">Use item sampling as part of a quality association to define the amount of current physical inventory that must be inspected.</span></span> <span data-ttu-id="bab0e-118">El muestreo puede basarse en cantidades fijas o en un porcentaje.</span><span class="sxs-lookup"><span data-stu-id="bab0e-118">Sampling can be based on fixed quantities or a percentage.</span></span>
-   <span data-ttu-id="bab0e-119">Crear pedidos de calidad para recepciones parciales.</span><span class="sxs-lookup"><span data-stu-id="bab0e-119">Create quality orders for partial receipts.</span></span> <span data-ttu-id="bab0e-120">Para crear un pedido de calidad basado en la cantidad que se recibe físicamente con un pedido, debe seleccionar la casilla de verificación **Por cantidad actualizada** en el formulario **Muestreo de artículos** .</span><span class="sxs-lookup"><span data-stu-id="bab0e-120">To create a quality order that is based on the quantity that is physically received with an order, you must select the **Per updated quantity** check box on the **Item sampling** form.</span></span>
-   <span data-ttu-id="bab0e-121">Permite crear tipos de prueba que incluyen mínimo, máximo y valores de prueba de destino, y realizar pruebas cualitativas en contraposición a cuantitativas que tengan resultados de validación predefinidos.</span><span class="sxs-lookup"><span data-stu-id="bab0e-121">Create test types that include minimum, maximum, and target test values, and perform qualitative-versus-quantitative testing that has predefined validation results.</span></span>
-   <span data-ttu-id="bab0e-122">Especifique un nivel de calidad aceptable (AQL) para controlar las tolerancias de medida de calidad.</span><span class="sxs-lookup"><span data-stu-id="bab0e-122">Specify an acceptable quality level (AQL) to control quality measure tolerances.</span></span>
-   <span data-ttu-id="bab0e-123">Especifique los recursos que una operación de inspección requiere, por ejemplo instrumentos de prueba y un área de prueba.</span><span class="sxs-lookup"><span data-stu-id="bab0e-123">Specify the resources that an inspection operation requires, such as a test area and test instruments.</span></span>

## <a name="working-with-quality-associations"></a><span data-ttu-id="bab0e-124">Trabajar con asociaciones de calidad</span><span class="sxs-lookup"><span data-stu-id="bab0e-124">Working with quality associations</span></span>
<span data-ttu-id="bab0e-125">El proceso empresarial que utiliza una asociación de calidad puede estar relacionado con varios documentos de origen, como pedidos de compra, pedidos de ventas o pedidos de producción.</span><span class="sxs-lookup"><span data-stu-id="bab0e-125">The business process that uses a quality association can be related to various source documents, such as purchase orders, sales orders, or production orders.</span></span>

<span data-ttu-id="bab0e-126">Cada registro de asociación de calidad define el conjunto de pruebas, el nivel de calidad aceptable y el plan de muestreo que se aplica a los pedidos de calidad generados.</span><span class="sxs-lookup"><span data-stu-id="bab0e-126">Each quality association record defines the set of tests, the AQL, and the sampling plan that applies to the quality orders that are generated.</span></span> <span data-ttu-id="bab0e-127">Debe definir un registro de asociación de calidad para cada variación de un proceso empresarial.</span><span class="sxs-lookup"><span data-stu-id="bab0e-127">You must define a quality association record for each variation in a business process.</span></span> <span data-ttu-id="bab0e-128">Por ejemplo, puede configurar una asociación de calidad que genere un pedido de calidad cuando se actualice una recepción de producto de pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="bab0e-128">For example, you can set up a quality association that generates a quality order when a purchase order product receipt is updated.</span></span> <span data-ttu-id="bab0e-129">En función de la configuración del plan de ejecución, el propio proceso de activación puede bloquearse mientras que haya un pedido de calidad abierto o los siguientes procesos, por ejemplo, una factura de pedido de compra, se pueden bloquear.</span><span class="sxs-lookup"><span data-stu-id="bab0e-129">Depending on the setup of the execution plan, the triggering process itself can be blocked while there is an open quality order, or the next processes, such as purchase order invoicing, can be blocked.</span></span>

<span data-ttu-id="bab0e-130">**Nota:** mientras haya pedidos de calidad abiertos, las cantidades de inventario se bloquean automáticamente para evitar su emisión.</span><span class="sxs-lookup"><span data-stu-id="bab0e-130">**Note:** While there are open quality orders, inventory quantities are automatically blocked from being issued.</span></span> <span data-ttu-id="bab0e-131">En función del ajuste **Bloqueo completo** de la página **Muestreos de artículos**, la cantidad es la cantidad en el pedido de calidad o la cantidad en la línea del documento de origen.</span><span class="sxs-lookup"><span data-stu-id="bab0e-131">Depending on the **Full blocking** setting on the **Item samplings** page, the quantity is either the quantity on the quality order or the quantity on the source document line.</span></span>

<span data-ttu-id="bab0e-132">Para un determinado proceso empresarial, el registro de la asociación de calidad identifica el evento y las condiciones para las que se genera un pedido de calidad.</span><span class="sxs-lookup"><span data-stu-id="bab0e-132">For a given business process, the quality association record identifies the event and the conditions that a quality order is generated for.</span></span> <span data-ttu-id="bab0e-133">Las condiciones pueden especificarse para un sitio o para una entidad jurídica.</span><span class="sxs-lookup"><span data-stu-id="bab0e-133">The conditions can be specific to either a site or a legal entity.</span></span> <span data-ttu-id="bab0e-134">Un pedido de calidad que requiera pruebas destructivas solo se puede generar si hay un inventario disponible para el evento.</span><span class="sxs-lookup"><span data-stu-id="bab0e-134">A quality order that involves destructive tests can be generated only when on-hand inventory exists for the event.</span></span>

<span data-ttu-id="bab0e-135">En los siguientes ejemplos se muestra cómo se define un registro de asociación de calidad para las variantes de cada proceso empresarial.</span><span class="sxs-lookup"><span data-stu-id="bab0e-135">The following examples illustrate how a quality association record is defined for the variations in each business process.</span></span> <span data-ttu-id="bab0e-136">Para cada ejemplo, la siguiente tabla resume los eventos y las condiciones definidos por un registro de asociación de calidad.</span><span class="sxs-lookup"><span data-stu-id="bab0e-136">For each example, the following table summarizes the events and conditions that are defined by a quality association record.</span></span>

<table>
<tbody>
<tr>
<th><span data-ttu-id="bab0e-137">Tipo de referencia</span><span class="sxs-lookup"><span data-stu-id="bab0e-137">Reference type</span></span></th>
<th><span data-ttu-id="bab0e-138">Tipo de evento</span><span class="sxs-lookup"><span data-stu-id="bab0e-138">Event type</span></span></th>
<th><span data-ttu-id="bab0e-139">Ejecución</span><span class="sxs-lookup"><span data-stu-id="bab0e-139">Execution</span></span></th>
<th><span data-ttu-id="bab0e-140">Bloqueo de eventos</span><span class="sxs-lookup"><span data-stu-id="bab0e-140">Event blocking</span></span></th>
<th><span data-ttu-id="bab0e-141">Referencia del documento</span><span class="sxs-lookup"><span data-stu-id="bab0e-141">Document reference</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="bab0e-142">Inventario</span><span class="sxs-lookup"><span data-stu-id="bab0e-142">Inventory</span></span></td>
<td><span data-ttu-id="bab0e-143">No aplicable</span><span class="sxs-lookup"><span data-stu-id="bab0e-143">Not applicable</span></span></td>
<td><span data-ttu-id="bab0e-144">No aplicable</span><span class="sxs-lookup"><span data-stu-id="bab0e-144">Not applicable</span></span></td>
<td><span data-ttu-id="bab0e-145">Ninguna</span><span class="sxs-lookup"><span data-stu-id="bab0e-145">None</span></span></td>
<td><span data-ttu-id="bab0e-146">Todas</span><span class="sxs-lookup"><span data-stu-id="bab0e-146">All</span></span></td>
</tr>
<tr>
<td rowspan="7"><span data-ttu-id="bab0e-147">Ventas</span><span class="sxs-lookup"><span data-stu-id="bab0e-147">Sales</span></span></td>
<td rowspan="4"><span data-ttu-id="bab0e-148">Proceso de picking programado</span><span class="sxs-lookup"><span data-stu-id="bab0e-148">Picking process is scheduled</span></span></td>
<td rowspan="4"><span data-ttu-id="bab0e-149">Anterior</span><span class="sxs-lookup"><span data-stu-id="bab0e-149">Before</span></span></td>
<td><span data-ttu-id="bab0e-150">Ninguna</span><span class="sxs-lookup"><span data-stu-id="bab0e-150">None</span></span></td>
<td rowspan="22"><span data-ttu-id="bab0e-151">Solo Id. específico, Grupo o Todo</span><span class="sxs-lookup"><span data-stu-id="bab0e-151">Specific ID, Group, or All only</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bab0e-152">Proceso de picking</span><span class="sxs-lookup"><span data-stu-id="bab0e-152">Picking process</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bab0e-153">Albarán</span><span class="sxs-lookup"><span data-stu-id="bab0e-153">Packing slip</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bab0e-154">Factura</span><span class="sxs-lookup"><span data-stu-id="bab0e-154">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="bab0e-155">Albarán</span><span class="sxs-lookup"><span data-stu-id="bab0e-155">Packing slip</span></span></td>
<td rowspan="3"><span data-ttu-id="bab0e-156">Anterior</span><span class="sxs-lookup"><span data-stu-id="bab0e-156">Before</span></span></td>
<td><span data-ttu-id="bab0e-157">Ninguna</span><span class="sxs-lookup"><span data-stu-id="bab0e-157">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bab0e-158">Albarán</span><span class="sxs-lookup"><span data-stu-id="bab0e-158">Packing slip</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bab0e-159">Factura</span><span class="sxs-lookup"><span data-stu-id="bab0e-159">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="15"><span data-ttu-id="bab0e-160">Compra</span><span class="sxs-lookup"><span data-stu-id="bab0e-160">Purchase</span></span></td>
<td rowspan="7"><span data-ttu-id="bab0e-161">Lista de recepciones</span><span class="sxs-lookup"><span data-stu-id="bab0e-161">Receipt list</span></span></td>
<td rowspan="4"><span data-ttu-id="bab0e-162">Anterior</span><span class="sxs-lookup"><span data-stu-id="bab0e-162">Before</span></span></td>
<td><span data-ttu-id="bab0e-163">Ninguna</span><span class="sxs-lookup"><span data-stu-id="bab0e-163">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bab0e-164">Lista de recepciones</span><span class="sxs-lookup"><span data-stu-id="bab0e-164">Receipt list</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bab0e-165">Recepción de producto</span><span class="sxs-lookup"><span data-stu-id="bab0e-165">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bab0e-166">Factura</span><span class="sxs-lookup"><span data-stu-id="bab0e-166">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="bab0e-167">Posterior</span><span class="sxs-lookup"><span data-stu-id="bab0e-167">After</span></span></td>
<td><span data-ttu-id="bab0e-168">Ninguna</span><span class="sxs-lookup"><span data-stu-id="bab0e-168">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bab0e-169">Recepción de producto</span><span class="sxs-lookup"><span data-stu-id="bab0e-169">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bab0e-170">Factura</span><span class="sxs-lookup"><span data-stu-id="bab0e-170">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="bab0e-171">Registro</span><span class="sxs-lookup"><span data-stu-id="bab0e-171">Registration</span></span></td>
<td rowspan="3"><span data-ttu-id="bab0e-172">No aplicable</span><span class="sxs-lookup"><span data-stu-id="bab0e-172">Not applicable</span></span></td>
<td><span data-ttu-id="bab0e-173">Ninguna</span><span class="sxs-lookup"><span data-stu-id="bab0e-173">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bab0e-174">Recepción de producto</span><span class="sxs-lookup"><span data-stu-id="bab0e-174">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bab0e-175">Factura</span><span class="sxs-lookup"><span data-stu-id="bab0e-175">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="5"><span data-ttu-id="bab0e-176">Recepción de producto</span><span class="sxs-lookup"><span data-stu-id="bab0e-176">Product receipt</span></span></td>
<td rowspan="3"><span data-ttu-id="bab0e-177">Anterior</span><span class="sxs-lookup"><span data-stu-id="bab0e-177">Before</span></span></td>
<td><span data-ttu-id="bab0e-178">Ninguna</span><span class="sxs-lookup"><span data-stu-id="bab0e-178">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bab0e-179">Recepción de producto</span><span class="sxs-lookup"><span data-stu-id="bab0e-179">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bab0e-180">Factura</span><span class="sxs-lookup"><span data-stu-id="bab0e-180">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="2"><span data-ttu-id="bab0e-181">Posterior</span><span class="sxs-lookup"><span data-stu-id="bab0e-181">After</span></span></td>
<td><span data-ttu-id="bab0e-182">Ninguna</span><span class="sxs-lookup"><span data-stu-id="bab0e-182">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bab0e-183">Factura</span><span class="sxs-lookup"><span data-stu-id="bab0e-183">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="8"><span data-ttu-id="bab0e-184">Producción</span><span class="sxs-lookup"><span data-stu-id="bab0e-184">Production</span></span></td>
<td rowspan="3"><span data-ttu-id="bab0e-185">Registro</span><span class="sxs-lookup"><span data-stu-id="bab0e-185">Registration</span></span></td>
<td rowspan="3"><span data-ttu-id="bab0e-186">No aplicable</span><span class="sxs-lookup"><span data-stu-id="bab0e-186">Not applicable</span></span></td>
<td><span data-ttu-id="bab0e-187">Ninguna</span><span class="sxs-lookup"><span data-stu-id="bab0e-187">None</span></span></td>
<td rowspan="12"><span data-ttu-id="bab0e-188">Todas</span><span class="sxs-lookup"><span data-stu-id="bab0e-188">All</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bab0e-189">Notificar como terminado</span><span class="sxs-lookup"><span data-stu-id="bab0e-189">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bab0e-190">Fin</span><span class="sxs-lookup"><span data-stu-id="bab0e-190">End</span></span></td>
</tr>
<tr>
<td rowspan="5"><span data-ttu-id="bab0e-191">Notificar como terminado</span><span class="sxs-lookup"><span data-stu-id="bab0e-191">Report as finished</span></span></td>
<td rowspan="3"><span data-ttu-id="bab0e-192">Anterior</span><span class="sxs-lookup"><span data-stu-id="bab0e-192">Before</span></span></td>
<td><span data-ttu-id="bab0e-193">Ninguna</span><span class="sxs-lookup"><span data-stu-id="bab0e-193">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bab0e-194">Notificar como terminado</span><span class="sxs-lookup"><span data-stu-id="bab0e-194">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bab0e-195">Fin</span><span class="sxs-lookup"><span data-stu-id="bab0e-195">End</span></span></td>
</tr>
<tr>
<td rowspan="2"><span data-ttu-id="bab0e-196">Posterior</span><span class="sxs-lookup"><span data-stu-id="bab0e-196">After</span></span></td>
<td><span data-ttu-id="bab0e-197">Ninguna</span><span class="sxs-lookup"><span data-stu-id="bab0e-197">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bab0e-198">Fin</span><span class="sxs-lookup"><span data-stu-id="bab0e-198">End</span></span></td>
</tr>
<tr>
<td rowspan="4"><span data-ttu-id="bab0e-199">Cuarentena</span><span class="sxs-lookup"><span data-stu-id="bab0e-199">Quarantine</span></span></td>
<td rowspan="3"><span data-ttu-id="bab0e-200">Notificar como terminado</span><span class="sxs-lookup"><span data-stu-id="bab0e-200">Report as finished</span></span></td>
<td rowspan="2"><span data-ttu-id="bab0e-201">Anterior</span><span class="sxs-lookup"><span data-stu-id="bab0e-201">Before</span></span></td>
<td><span data-ttu-id="bab0e-202">Notificar como terminado</span><span class="sxs-lookup"><span data-stu-id="bab0e-202">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bab0e-203">Fin</span><span class="sxs-lookup"><span data-stu-id="bab0e-203">End</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bab0e-204">Posterior</span><span class="sxs-lookup"><span data-stu-id="bab0e-204">After</span></span></td>
<td><span data-ttu-id="bab0e-205">Fin</span><span class="sxs-lookup"><span data-stu-id="bab0e-205">End</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bab0e-206">Fin</span><span class="sxs-lookup"><span data-stu-id="bab0e-206">End</span></span></td>
<td><span data-ttu-id="bab0e-207">Anterior</span><span class="sxs-lookup"><span data-stu-id="bab0e-207">Before</span></span></td>
<td><span data-ttu-id="bab0e-208">Fin</span><span class="sxs-lookup"><span data-stu-id="bab0e-208">End</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="bab0e-209">Operación de ruta</span><span class="sxs-lookup"><span data-stu-id="bab0e-209">Route operation</span></span></td>
<td rowspan="3"><span data-ttu-id="bab0e-210">Notificar como terminado</span><span class="sxs-lookup"><span data-stu-id="bab0e-210">Report as finished</span></span></td>
<td rowspan="2"><span data-ttu-id="bab0e-211">Anterior</span><span class="sxs-lookup"><span data-stu-id="bab0e-211">Before</span></span></td>
<td><span data-ttu-id="bab0e-212">Ninguna</span><span class="sxs-lookup"><span data-stu-id="bab0e-212">None</span></span></td>
<td rowspan="3"><span data-ttu-id="bab0e-213">Id. específico, Grupo o Todo, y Recurso específico, Grupo o Todo</span><span class="sxs-lookup"><span data-stu-id="bab0e-213">Specific ID, Group, or All, and Resource specific, Group, or All</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bab0e-214">Notificar como terminado</span><span class="sxs-lookup"><span data-stu-id="bab0e-214">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bab0e-215">Posterior</span><span class="sxs-lookup"><span data-stu-id="bab0e-215">After</span></span></td>
<td><span data-ttu-id="bab0e-216">Ninguna</span><span class="sxs-lookup"><span data-stu-id="bab0e-216">None</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="bab0e-217">Producción de coproductos</span><span class="sxs-lookup"><span data-stu-id="bab0e-217">Co-product production</span></span></td>
<td><span data-ttu-id="bab0e-218">Registro</span><span class="sxs-lookup"><span data-stu-id="bab0e-218">Registration</span></span></td>
<td><span data-ttu-id="bab0e-219">No aplicable</span><span class="sxs-lookup"><span data-stu-id="bab0e-219">Not applicable</span></span></td>
<td rowspan="3"><span data-ttu-id="bab0e-220">Ninguna</span><span class="sxs-lookup"><span data-stu-id="bab0e-220">None</span></span></td>
<td rowspan="3"><span data-ttu-id="bab0e-221">Todas</span><span class="sxs-lookup"><span data-stu-id="bab0e-221">All</span></span></td>
</tr>
<tr>
<td rowspan="2"><span data-ttu-id="bab0e-222">Notificar como terminado</span><span class="sxs-lookup"><span data-stu-id="bab0e-222">Report as finished</span></span></td>
<td><span data-ttu-id="bab0e-223">Anterior</span><span class="sxs-lookup"><span data-stu-id="bab0e-223">Before</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bab0e-224">Posterior</span><span class="sxs-lookup"><span data-stu-id="bab0e-224">After</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="bab0e-225">La siguiente tabla proporciona más información acerca de cómo se pueden generar los pedidos de calidad para tipos de procesos concretos.</span><span class="sxs-lookup"><span data-stu-id="bab0e-225">The following table provides more information about how quality orders can be generated for specific types of processes.</span></span>
<div class="tableSection">

<table>
<tbody>
<tr>
<th><span data-ttu-id="bab0e-226">Tipo de proceso</span><span class="sxs-lookup"><span data-stu-id="bab0e-226">Type of process</span></span></th>
<th><span data-ttu-id="bab0e-227">Cuando los pedidos de calidad se pueden generar automáticamente</span><span class="sxs-lookup"><span data-stu-id="bab0e-227">When quality orders can be automatically generated</span></span></th>
<th><span data-ttu-id="bab0e-228">Cuando los pedidos de calidad se pueden generar si se requiere una prueba destructiva</span><span class="sxs-lookup"><span data-stu-id="bab0e-228">When quality orders can be generated if destructive testing is required</span></span></th>
<th><span data-ttu-id="bab0e-229">Información acerca de la condición</span><span class="sxs-lookup"><span data-stu-id="bab0e-229">Condition information</span></span></th>
<th><span data-ttu-id="bab0e-230">Información acerca de la generación manual</span><span class="sxs-lookup"><span data-stu-id="bab0e-230">Manual generation information</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="bab0e-231">Pedido de compra</span><span class="sxs-lookup"><span data-stu-id="bab0e-231">Purchase order</span></span></td>
<td><span data-ttu-id="bab0e-232">Antes o después de que se registre una lista de recepciones o una recepción de producto del material recibido</span><span class="sxs-lookup"><span data-stu-id="bab0e-232">Before or after a receipts list or product receipt for the material that is received is posted</span></span></td>
<td><span data-ttu-id="bab0e-233">Después del registro de la recepción de producto, ya que el material debe estar disponible para la prueba destructiva</span><span class="sxs-lookup"><span data-stu-id="bab0e-233">After the product receipt for the material that is received is posted, because the material must be available for destructive testing</span></span></td>
<td><span data-ttu-id="bab0e-234">El requisito de un pedido de calidad puede reflejar un sitio, un artículo o proveedor en concreto, además de una combinación de estas condiciones.</span><span class="sxs-lookup"><span data-stu-id="bab0e-234">The requirement for a quality order can reflect a particular site, item, or vendor, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="bab0e-235">Un pedido de calidad generado manualmente que hace referencia a un pedido de compra puede usar la información de un registro de asociación de calidad, como el plan de muestreo de la prueba.</span><span class="sxs-lookup"><span data-stu-id="bab0e-235">A manually generated quality order that refers to a purchase order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bab0e-236">Orden de cuarentena</span><span class="sxs-lookup"><span data-stu-id="bab0e-236">Quarantine order</span></span></td>
<td><span data-ttu-id="bab0e-237">Antes o después de que se notifique que ha finalizado la orden de cuarentena</span><span class="sxs-lookup"><span data-stu-id="bab0e-237">Before or after the quarantine order is reported as finished or ended</span></span></td>
<td><span data-ttu-id="bab0e-238">No se pueden generar pedidos de calidad que necesiten pruebas destructivas.</span><span class="sxs-lookup"><span data-stu-id="bab0e-238">Quality orders that require destructive tests can&#39;t be generated.</span></span> <span data-ttu-id="bab0e-239">Se supone que la funcionalidad de la orden de cuarentena gestiona la disposición del material destruido.</span><span class="sxs-lookup"><span data-stu-id="bab0e-239">It&#39;s assumed that the quarantine order functionality handles the disposition of the material that is destroyed.</span></span></td>
<td><span data-ttu-id="bab0e-240">El requisito de un pedido de calidad puede reflejar un sitio, un artículo o proveedor en concreto, además de una combinación de estas condiciones.</span><span class="sxs-lookup"><span data-stu-id="bab0e-240">The requirement for a quality order can reflect a particular site, item, or vendor, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="bab0e-241">Un pedido de calidad generado manualmente que hace referencia a una orden de cuarentena puede usar la información de un registro de asociación de calidad, como el plan de muestreo de la prueba.</span><span class="sxs-lookup"><span data-stu-id="bab0e-241">A manually generated quality order that refers to a quarantine order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bab0e-242">Pedido de ventas</span><span class="sxs-lookup"><span data-stu-id="bab0e-242">Sales order</span></span></td>
<td><span data-ttu-id="bab0e-243">Antes de una actualización programada del proceso de selección o del albarán para los artículos que se envían</span><span class="sxs-lookup"><span data-stu-id="bab0e-243">Before a scheduled picking process or packing slip update for the items that are being shipped</span></span></td>
<td><span data-ttu-id="bab0e-244">En cualquier paso</span><span class="sxs-lookup"><span data-stu-id="bab0e-244">At any step</span></span></td>
<td><span data-ttu-id="bab0e-245">El requisito de un pedido de calidad puede reflejar un sitio, un artículo o un cliente concreto, además de una combinación de estas condiciones.</span><span class="sxs-lookup"><span data-stu-id="bab0e-245">The requirement for a quality order can reflect a particular site, item, or customer, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="bab0e-246">Un pedido de calidad generado manualmente que hace referencia a un pedido de ventas puede usar la información de un registro de asociación de calidad, como el plan de muestreo de la prueba.</span><span class="sxs-lookup"><span data-stu-id="bab0e-246">A manually generated quality order that refers to a sales order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bab0e-247">Pedido de producción</span><span class="sxs-lookup"><span data-stu-id="bab0e-247">Production order</span></span></td>
<td><span data-ttu-id="bab0e-248">Antes o después de que se registre la cantidad finalizada del pedido de producción</span><span class="sxs-lookup"><span data-stu-id="bab0e-248">Before or after the finished quantity for the production order is reported</span></span></td>
<td><span data-ttu-id="bab0e-249">Después de que se registre la cantidad finalizada del pedido de producción</span><span class="sxs-lookup"><span data-stu-id="bab0e-249">After the finished quantity for the production order is reported</span></span></td>
<td><span data-ttu-id="bab0e-250">El requisito de un pedido de calidad puede reflejar un sitio o un artículo concreto, además de una combinación de estas condiciones.</span><span class="sxs-lookup"><span data-stu-id="bab0e-250">The requirement for a quality order can reflect a particular site or item, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="bab0e-251">Un pedido de calidad generado manualmente que hace referencia a un pedido de producción puede usar la información de un registro de asociación de calidad, como el plan de muestreo de la prueba.</span><span class="sxs-lookup"><span data-stu-id="bab0e-251">A manually generated quality order that refers to a production order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bab0e-252">Pedido de producción con una operación de ruta</span><span class="sxs-lookup"><span data-stu-id="bab0e-252">Production order that has a route operation</span></span></td>
<td><span data-ttu-id="bab0e-253">Antes o después de finalizar el informe de la operación</span><span class="sxs-lookup"><span data-stu-id="bab0e-253">Before or after the report is finished for an operation</span></span></td>
<td><span data-ttu-id="bab0e-254">Después de finalizar el informe de producción de la última operación</span><span class="sxs-lookup"><span data-stu-id="bab0e-254">After the reporting production is finished for the last operation</span></span></td>
<td><span data-ttu-id="bab0e-255">El requisito de un pedido de calidad puede reflejar un sitio, un artículo o un recurso de operaciones concreto, además de una combinación de estas condiciones.</span><span class="sxs-lookup"><span data-stu-id="bab0e-255">The requirement for a quality order can reflect a particular, site, item, or operations resource, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="bab0e-256">Un pedido de calidad generado manualmente que hace referencia a una operación de ruta puede usar la información de un registro de asociación de calidad, como el plan de muestreo de la prueba.</span><span class="sxs-lookup"><span data-stu-id="bab0e-256">A manually generated quality order that refers to a route operation can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="bab0e-257">Inventario</span><span class="sxs-lookup"><span data-stu-id="bab0e-257">Inventory</span></span></td>
<td><span data-ttu-id="bab0e-258">Un pedido de calidad no se puede generar automáticamente para una transacción en un diario de inventario o para las transacciones de un pedido de transferencia.</span><span class="sxs-lookup"><span data-stu-id="bab0e-258">A quality order cannot be automatically generated for a transaction in an inventory journal or for transfer order transactions.</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="bab0e-259">Un pedido de calidad se debe crear manualmente para la cantidad de inventario de un artículo.</span><span class="sxs-lookup"><span data-stu-id="bab0e-259">A quality order must be created manually for an item&#39;s inventory quantity.</span></span> <span data-ttu-id="bab0e-260">Se requiere el inventario físico disponible.</span><span class="sxs-lookup"><span data-stu-id="bab0e-260">Physical on-hand inventory is required.</span></span></td>
</tr>
</tbody>
</table>

## <a name="quality-order-auto-generation-examples"></a><span data-ttu-id="bab0e-261">Ejemplos de la generación automática del pedido de calidad</span><span class="sxs-lookup"><span data-stu-id="bab0e-261">Quality order auto-generation examples</span></span>

### <a name="purchasing"></a><span data-ttu-id="bab0e-262">Compras</span><span class="sxs-lookup"><span data-stu-id="bab0e-262">Purchasing</span></span>

<span data-ttu-id="bab0e-263">En la compra, si establece el campo **Tipo de evento** en **Recepción de producto** y el campo **Ejecución** en **Después** en la página **Asociaciones de calidad**, obtiene los resultados siguientes:</span><span class="sxs-lookup"><span data-stu-id="bab0e-263">In purchasing, if you set the **Event type** field to **Product receipt** and the **Execution** field to **After** on the **Quality associations** page, you get the following results:</span></span> 

- <span data-ttu-id="bab0e-264">Si la opción **Por cantidad actualizada** se establece en **Sí**, un pedido de calidad se genera para cada recepción con el pedido de compra, en función de la cantidad y los valores recibidos en el muestreo de artículos.</span><span class="sxs-lookup"><span data-stu-id="bab0e-264">If the **Per updated quantity** option is set to **Yes**, a quality order is generated for every receipt against the purchase order, based on the received quantity and settings in the item sampling.</span></span> <span data-ttu-id="bab0e-265">Cada vez que una cantidad se reciba contra el pedido de compra, los nuevos pedidos de calidad se generan en función de la cantidad recién recibida.</span><span class="sxs-lookup"><span data-stu-id="bab0e-265">Every time that a quantity is received against the purchase order, new quality orders are generated based on the newly received quantity.</span></span>
- <span data-ttu-id="bab0e-266">Si la opción **Por cantidad actualizada** se establece en **No**, un pedido de calidad se genera para la primera recepción con el pedido de compra, en función de la cantidad recibida.</span><span class="sxs-lookup"><span data-stu-id="bab0e-266">If the **Per updated quantity** option is set to **No**, a quality order is generated for the first receipt against the purchase order, based on the received quantity.</span></span> <span data-ttu-id="bab0e-267">Además, uno o más pedidos de calidad se crean en función de la cantidad restante, en función de las dimensiones de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="bab0e-267">Additionally, one or more quality orders are created based on the remaining quantity, depending on the tracking dimensions.</span></span> <span data-ttu-id="bab0e-268">Los pedidos de calidad no se generan para las recepciones posteriores con el pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="bab0e-268">Quality orders aren't generated for subsequent receipts against the purchase order.</span></span>

<table>
<tbody>
<tr>
<th><span data-ttu-id="bab0e-269">Especificación de calidad</span><span class="sxs-lookup"><span data-stu-id="bab0e-269">Quality specification</span></span></th>
<th><span data-ttu-id="bab0e-270">Por cantidad actualizada</span><span class="sxs-lookup"><span data-stu-id="bab0e-270">Per updated quantity</span></span></th>
<th><span data-ttu-id="bab0e-271">Por dimensión de seguimiento</span><span class="sxs-lookup"><span data-stu-id="bab0e-271">Per tracking dimension</span></span></th>
<th><span data-ttu-id="bab0e-272">Resultado</span><span class="sxs-lookup"><span data-stu-id="bab0e-272">Result</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="bab0e-273">Porcentaje: 10 %</span><span class="sxs-lookup"><span data-stu-id="bab0e-273">Percentage: 10%</span></span></td>
<td><span data-ttu-id="bab0e-274">Sí</span><span class="sxs-lookup"><span data-stu-id="bab0e-274">Yes</span></span></td>
<td>
<p><span data-ttu-id="bab0e-275">Número de lote: No</span><span class="sxs-lookup"><span data-stu-id="bab0e-275">Batch number: No</span></span></p>
<p><span data-ttu-id="bab0e-276">Número de serie: No</span><span class="sxs-lookup"><span data-stu-id="bab0e-276">Serial number: No</span></span></p>
</td>
<td>
<p><span data-ttu-id="bab0e-277">Cantidad de pedido: 100</span><span class="sxs-lookup"><span data-stu-id="bab0e-277">Order quantity: 100</span></span></p>
<ol>
<li><span data-ttu-id="bab0e-278">Notificar como terminado para 30</span><span class="sxs-lookup"><span data-stu-id="bab0e-278">Report as finished for 30</span></span>
<ul>
<li><span data-ttu-id="bab0e-279">Pedido de calidad #1 para 3 (10 % de 30)</span><span class="sxs-lookup"><span data-stu-id="bab0e-279">Quality order #1 for 3 (10% of 30)</span></span></li>
</ul>
</li>
<li><span data-ttu-id="bab0e-280">Notificar como terminado para 70</span><span class="sxs-lookup"><span data-stu-id="bab0e-280">Report as finished for 70</span></span>
<ul>
<li><span data-ttu-id="bab0e-281">Pedido de calidad #2 para 7 (10% de la cantidad de pedido restantes, que es igual a 70 en este caso)</span><span class="sxs-lookup"><span data-stu-id="bab0e-281">Quality order #2 for 7 (10% of the remaining order quantity, which equals 70 in this case)</span></span></li>
</ul>
</li>
</ol>
</td>
</tr>
<tr>
<td><span data-ttu-id="bab0e-282">Cantidad fija: 1</span><span class="sxs-lookup"><span data-stu-id="bab0e-282">Fixed quantity: 1</span></span></td>
<td><span data-ttu-id="bab0e-283">No</span><span class="sxs-lookup"><span data-stu-id="bab0e-283">No</span></span></td>
<td>
<p><span data-ttu-id="bab0e-284">Número de lote: No</span><span class="sxs-lookup"><span data-stu-id="bab0e-284">Batch number: No</span></span></p>
<p><span data-ttu-id="bab0e-285">Número de serie: No</span><span class="sxs-lookup"><span data-stu-id="bab0e-285">Serial number: No</span></span></p>
</td>
<td><span data-ttu-id="bab0e-286">Cantidad de pedido: 100</span><span class="sxs-lookup"><span data-stu-id="bab0e-286">Order quantity: 100</span></span>
<ol>
<li><span data-ttu-id="bab0e-287">Notificar como terminado para 30</span><span class="sxs-lookup"><span data-stu-id="bab0e-287">Report as finished for 30</span></span>
<ul>
<li><span data-ttu-id="bab0e-288">El pedido de calidad #1 se crea para 1 (para la primera cantidad notificada como terminada, que tiene un valor fijo de 1).</span><span class="sxs-lookup"><span data-stu-id="bab0e-288">Quality order #1 is created for 1 (for the first reported-as-finished quantity, which has a fixed value of 1).</span></span></li>
<li><span data-ttu-id="bab0e-289">No se crean más de pedidos de calidad con la cantidad restante.</span><span class="sxs-lookup"><span data-stu-id="bab0e-289">No more quality orders are created against the remaining quantity.</span></span></li>
</ul>
</li>
<li><span data-ttu-id="bab0e-290">Notificar como terminado para 10</span><span class="sxs-lookup"><span data-stu-id="bab0e-290">Report as finished for 10</span></span>
<ul>
<li><span data-ttu-id="bab0e-291">No se crea ningún pedido de calidad.</span><span class="sxs-lookup"><span data-stu-id="bab0e-291">No quality orders are created.</span></span></li>
</ul>
</li>
<li><span data-ttu-id="bab0e-292">Notificar como terminado para 60</span><span class="sxs-lookup"><span data-stu-id="bab0e-292">Report as finished for 60</span></span>
<ul>
<li><span data-ttu-id="bab0e-293">No se crea ningún pedido de calidad.</span><span class="sxs-lookup"><span data-stu-id="bab0e-293">No quality orders are created.</span></span></li>
</ul>
</li>
</ol>
</td>
</tr>
<tr>
<td><span data-ttu-id="bab0e-294">Cantidad fija: 1</span><span class="sxs-lookup"><span data-stu-id="bab0e-294">Fixed quantity: 1</span></span></td>
<td><span data-ttu-id="bab0e-295">Sí</span><span class="sxs-lookup"><span data-stu-id="bab0e-295">Yes</span></span></td>
<td>
<p><span data-ttu-id="bab0e-296">Número de lote: Sí</span><span class="sxs-lookup"><span data-stu-id="bab0e-296">Batch number: Yes</span></span></p>
<p><span data-ttu-id="bab0e-297">Número de serie: Sí</span><span class="sxs-lookup"><span data-stu-id="bab0e-297">Serial number: Yes</span></span></p>
</td>
<td>
<p><span data-ttu-id="bab0e-298">Cantidad de pedido: 10</span><span class="sxs-lookup"><span data-stu-id="bab0e-298">Order quantity: 10</span></span></p>
<ol>
<li><span data-ttu-id="bab0e-299">Notificar como terminado para 3</span><span class="sxs-lookup"><span data-stu-id="bab0e-299">Report as finished for 3</span></span>
<ul>
<li><span data-ttu-id="bab0e-300">Pedido de calidad #1 para 1 del lote #b1, serie #s1</span><span class="sxs-lookup"><span data-stu-id="bab0e-300">Quality order #1 for 1 of batch #b1, serial #s1</span></span></li>
<li><span data-ttu-id="bab0e-301">Pedido de calidad #2 para 1 del lote #b2, serie #s2</span><span class="sxs-lookup"><span data-stu-id="bab0e-301">Quality order #2 for 1 of batch #b2, serial #s2</span></span></li>
<li><span data-ttu-id="bab0e-302">Pedido de calidad #3 para 1 del lote #b3, serie #s3</span><span class="sxs-lookup"><span data-stu-id="bab0e-302">Quality order #3 for 1 of batch #b3, serial #s3</span></span></li>
</ul>
</li>
<li><span data-ttu-id="bab0e-303">Notificar como terminado para 2</span><span class="sxs-lookup"><span data-stu-id="bab0e-303">Report as finished for 2</span></span>
<ul>
<li><span data-ttu-id="bab0e-304">Pedido de calidad #4 para 1 del lote #b4, serie #s4</span><span class="sxs-lookup"><span data-stu-id="bab0e-304">Quality order #4 for 1 of batch #b4, serial #s4</span></span></li>
<li><span data-ttu-id="bab0e-305">Pedido de calidad #5 para 1 del lote #b5, serie #s5</span><span class="sxs-lookup"><span data-stu-id="bab0e-305">Quality order #5 for 1 of batch #b5, serial #s5</span></span></li>
</ul>
</li>
</ol>
<p><span data-ttu-id="bab0e-306"><strong>Nota:</strong> El lote se puede volver a utilizar.</span><span class="sxs-lookup"><span data-stu-id="bab0e-306"><strong>Note:</strong> The batch can be reused.</span></span></p>
</td>
</tr>
<tr>
<td><span data-ttu-id="bab0e-307">Cantidad fija: 2</span><span class="sxs-lookup"><span data-stu-id="bab0e-307">Fixed quantity: 2</span></span></td>
<td><span data-ttu-id="bab0e-308">No</span><span class="sxs-lookup"><span data-stu-id="bab0e-308">No</span></span></td>
<td>
<p><span data-ttu-id="bab0e-309">Número de lote: Sí</span><span class="sxs-lookup"><span data-stu-id="bab0e-309">Batch number: Yes</span></span></p>
<p><span data-ttu-id="bab0e-310">Número de serie: Sí</span><span class="sxs-lookup"><span data-stu-id="bab0e-310">Serial number: Yes</span></span></p>
</td>
<td>
<p><span data-ttu-id="bab0e-311">Cantidad de pedido: 10</span><span class="sxs-lookup"><span data-stu-id="bab0e-311">Order quantity: 10</span></span></p>
<ol>
<li><span data-ttu-id="bab0e-312">Notificar como terminado para 4</span><span class="sxs-lookup"><span data-stu-id="bab0e-312">Report as finished for 4</span></span>
<ul>
<li><span data-ttu-id="bab0e-313">Pedido de calidad #1 para 1 del lote #b1, serie #s1.</span><span class="sxs-lookup"><span data-stu-id="bab0e-313">Quality order #1 for 1 of batch #b1, serial #s1.</span></span></li>
<li><span data-ttu-id="bab0e-314">Pedido de calidad #2 para 1 del lote #b2, serie #s2.</span><span class="sxs-lookup"><span data-stu-id="bab0e-314">Quality order #2 for 1 of batch #b2, serial #s2.</span></span></li>
<li><span data-ttu-id="bab0e-315">Pedido de calidad #3 para 1 del lote #b3, serie #s3.</span><span class="sxs-lookup"><span data-stu-id="bab0e-315">Quality order #3 for 1 of batch #b3, serial #s3.</span></span></li>
<li><span data-ttu-id="bab0e-316">Pedido de calidad #4 para 1 del lote #b4, serie #s4.</span><span class="sxs-lookup"><span data-stu-id="bab0e-316">Quality order #4 for 1 of batch #b4, serial #s4.</span></span></li>
<li><span data-ttu-id="bab0e-317">No se crean más de pedidos de calidad con la cantidad restante.</span><span class="sxs-lookup"><span data-stu-id="bab0e-317">No more quality orders are created against the remaining quantity.</span></span></li>
</ul>
</li>
<li><span data-ttu-id="bab0e-318">Notificar como terminado para 6</span><span class="sxs-lookup"><span data-stu-id="bab0e-318">Report as finished for 6</span></span>
<ul>
<li><span data-ttu-id="bab0e-319">No se crea ningún pedido de calidad.</span><span class="sxs-lookup"><span data-stu-id="bab0e-319">No quality orders are created.</span></span></li>
</ul>
</li>
</ol>
</td>
</tr>
</tbody>
</table>

### <a name="production"></a><span data-ttu-id="bab0e-320">Producción</span><span class="sxs-lookup"><span data-stu-id="bab0e-320">Production</span></span>

<span data-ttu-id="bab0e-321">En la producción, si establece el campo **Tipo de evento** en **Informar como completado** y el campo **Ejecución** en **Después** en la página **Asociaciones de calidad**, obtiene los resultados siguientes:</span><span class="sxs-lookup"><span data-stu-id="bab0e-321">In production, if you set the **Event type** field to **Report as finished** and the **Execution** field to **After** on the **Quality associations** page, you get the following results:</span></span>

- <span data-ttu-id="bab0e-322">Si la opción **Por cantidad actualizada** se establece en **Sí**, un pedido de calidad se genera para cada cantidad y valores completados en el muestreo de artículos.</span><span class="sxs-lookup"><span data-stu-id="bab0e-322">If the **Per updated quantity** option is set to **Yes**, a quality order is generated based on every finished quantity and settings in the item sampling.</span></span> <span data-ttu-id="bab0e-323">Cada vez que una cantidad se notifique como terminado con el pedido de producción, los nuevos pedidos de calidad se generan en función de la cantidad recién terminada.</span><span class="sxs-lookup"><span data-stu-id="bab0e-323">Every time that a quantity is reported as finished against the production order, new quality orders are generated based on newly finished quantity.</span></span> <span data-ttu-id="bab0e-324">Esta lógica de la generación es coherente con la compra.</span><span class="sxs-lookup"><span data-stu-id="bab0e-324">This generation logic is consistent with purchasing.</span></span>
- <span data-ttu-id="bab0e-325">Si la opción **Por cantidad actualizada** se establece en **No**, un pedido de calidad se genera para la primera vez que una cantidad se notifica como terminada, en función de la cantidad terminada.</span><span class="sxs-lookup"><span data-stu-id="bab0e-325">If the **Per updated quantity** option is set to **No**, a quality order is generated the first time that a quantity is reported as finished, based on the finished quantity.</span></span> <span data-ttu-id="bab0e-326">Además, uno o más pedidos de calidad se crean en función de la cantidad restante, en función de las dimensiones de seguimiento del muestreo del artículo.</span><span class="sxs-lookup"><span data-stu-id="bab0e-326">Additionally, one or more quality orders are created based on the remaining quantity, depending on the tracking dimensions of the item sampling.</span></span> <span data-ttu-id="bab0e-327">Los pedidos de calidad no se generan para las cantidades finalizadas posteriores.</span><span class="sxs-lookup"><span data-stu-id="bab0e-327">Quality orders aren't generated for subsequent finished quantities.</span></span>

<table>
<tbody>
<tr>
<th><span data-ttu-id="bab0e-328">Especificación de calidad</span><span class="sxs-lookup"><span data-stu-id="bab0e-328">Quality specification</span></span></th>
<th><span data-ttu-id="bab0e-329">Por cantidad actualizada</span><span class="sxs-lookup"><span data-stu-id="bab0e-329">Per updated quantity</span></span></th>
<th><span data-ttu-id="bab0e-330">Por dimensión de seguimiento</span><span class="sxs-lookup"><span data-stu-id="bab0e-330">Per tracking dimension</span></span></th>
<th><span data-ttu-id="bab0e-331">Resultado</span><span class="sxs-lookup"><span data-stu-id="bab0e-331">Result</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="bab0e-332">Porcentaje: 10 %</span><span class="sxs-lookup"><span data-stu-id="bab0e-332">Percentage: 10%</span></span></td>
<td><span data-ttu-id="bab0e-333">Sí</span><span class="sxs-lookup"><span data-stu-id="bab0e-333">Yes</span></span></td>
<td>
<p><span data-ttu-id="bab0e-334">Número de lote: No</span><span class="sxs-lookup"><span data-stu-id="bab0e-334">Batch number: No</span></span></p>
<p><span data-ttu-id="bab0e-335">Número de serie: No</span><span class="sxs-lookup"><span data-stu-id="bab0e-335">Serial number: No</span></span></p>
</td>
<td>
<p><span data-ttu-id="bab0e-336">Cantidad de pedido: 100</span><span class="sxs-lookup"><span data-stu-id="bab0e-336">Order quantity: 100</span></span></p>
<ol>
<li><span data-ttu-id="bab0e-337">Notificar como terminado para 30</span><span class="sxs-lookup"><span data-stu-id="bab0e-337">Report as finished for 30</span></span>
<ul>
<li><span data-ttu-id="bab0e-338">Pedido de calidad #1 para 3 (10 % de 30)</span><span class="sxs-lookup"><span data-stu-id="bab0e-338">Quality order #1 for 3 (10% of 30)</span></span></li>
</ul>
</li>
<li><span data-ttu-id="bab0e-339">Notificar como terminado para 70</span><span class="sxs-lookup"><span data-stu-id="bab0e-339">Report as finished for 70</span></span>
<ul>
<li><span data-ttu-id="bab0e-340">Pedido de calidad #2 para 7 (10% de la cantidad de pedido restantes, que es igual a 70 en este caso)</span><span class="sxs-lookup"><span data-stu-id="bab0e-340">Quality order #2 for 7 (10% of the remaining order quantity, which equals 70 in this case)</span></span></li>
</ul>
</li>
</ol>
</td>
</tr>
<tr>
<td><span data-ttu-id="bab0e-341">Cantidad fija: 1</span><span class="sxs-lookup"><span data-stu-id="bab0e-341">Fixed quantity: 1</span></span></td>
<td><span data-ttu-id="bab0e-342">No</span><span class="sxs-lookup"><span data-stu-id="bab0e-342">No</span></span></td>
<td>
<p><span data-ttu-id="bab0e-343">Número de lote: No</span><span class="sxs-lookup"><span data-stu-id="bab0e-343">Batch number: No</span></span></p>
<p><span data-ttu-id="bab0e-344">Número de serie: No</span><span class="sxs-lookup"><span data-stu-id="bab0e-344">Serial number: No</span></span></p>
</td>
<td><span data-ttu-id="bab0e-345">Cantidad de pedido: 100</span><span class="sxs-lookup"><span data-stu-id="bab0e-345">Order quantity: 100</span></span>
<ol>
<li><span data-ttu-id="bab0e-346">Notificar como terminado para 30</span><span class="sxs-lookup"><span data-stu-id="bab0e-346">Report as finished for 30</span></span>
<ul>
<li><span data-ttu-id="bab0e-347">El pedido de calidad #1para 1 (para la primera cantidad notificada como terminada, que tiene un valor fijo de 1)</span><span class="sxs-lookup"><span data-stu-id="bab0e-347">Quality order #1 for 1 (for the first reported-as-finished quantity, which has a fixed value of 1)</span></span></li>
<li><span data-ttu-id="bab0e-348">El pedido de calidad #2 para 1 (para la cantidad restante, que todavía un valor fijo de 1)</span><span class="sxs-lookup"><span data-stu-id="bab0e-348">Quality order #2 for 1 (for the remaining quantity, which still has a fixed value of 1)</span></span></li>
</ul>
</li>
<li><span data-ttu-id="bab0e-349">Notificar como terminado para 10</span><span class="sxs-lookup"><span data-stu-id="bab0e-349">Report as finished for 10</span></span>
<ul>
<li><span data-ttu-id="bab0e-350">No se crea ningún pedido de calidad.</span><span class="sxs-lookup"><span data-stu-id="bab0e-350">No quality orders are created.</span></span></li>
</ul>
</li>
<li><span data-ttu-id="bab0e-351">Notificar como terminado para 60</span><span class="sxs-lookup"><span data-stu-id="bab0e-351">Report as finished for 60</span></span>
<ul>
<li><span data-ttu-id="bab0e-352">No se crea ningún pedido de calidad.</span><span class="sxs-lookup"><span data-stu-id="bab0e-352">No quality orders are created.</span></span></li>
</ul>
</li>
</ol>
</td>
</tr>
<tr>
<td><span data-ttu-id="bab0e-353">Cantidad fija: 1</span><span class="sxs-lookup"><span data-stu-id="bab0e-353">Fixed quantity: 1</span></span></td>
<td><span data-ttu-id="bab0e-354">Sí</span><span class="sxs-lookup"><span data-stu-id="bab0e-354">Yes</span></span></td>
<td>
<p><span data-ttu-id="bab0e-355">Número de lote: Sí</span><span class="sxs-lookup"><span data-stu-id="bab0e-355">Batch number: Yes</span></span></p>
<p><span data-ttu-id="bab0e-356">Número de serie: Sí</span><span class="sxs-lookup"><span data-stu-id="bab0e-356">Serial number: Yes</span></span></p>
</td>
<td>
<p><span data-ttu-id="bab0e-357">Cantidad de pedido: 10</span><span class="sxs-lookup"><span data-stu-id="bab0e-357">Order quantity: 10</span></span></p>
<ol>
<li><span data-ttu-id="bab0e-358">Notificar como terminado para 3: 1 para #b1, #s1; 1 para #b2, #s2; y 1 para #b3, #s3</span><span class="sxs-lookup"><span data-stu-id="bab0e-358">Report as finished for 3: 1 for #b1, #s1; 1 for #b2, #s2; and 1 for #b3, #s3</span></span>
<ul>
<li><span data-ttu-id="bab0e-359">Pedido de calidad #1 para 1 del lote #b1, serie #s1</span><span class="sxs-lookup"><span data-stu-id="bab0e-359">Quality order #1 for 1 of batch #b1, serial #s1</span></span></li>
<li><span data-ttu-id="bab0e-360">Pedido de calidad #2 para 1 del lote #b2, serie #s2</span><span class="sxs-lookup"><span data-stu-id="bab0e-360">Quality order #2 for 1 of batch #b2, serial #s2</span></span></li>
<li><span data-ttu-id="bab0e-361">Pedido de calidad #3 para 1 del lote #b3, serie #s3</span><span class="sxs-lookup"><span data-stu-id="bab0e-361">Quality order #3 for 1 of batch #b3, serial #s3</span></span></li>
</ul>
</li>
<li><span data-ttu-id="bab0e-362">Notificar como terminado para 2: 1 para #b4, #s4; y 1 para #b5, #s5</span><span class="sxs-lookup"><span data-stu-id="bab0e-362">Report as finished for 2: 1 for #b4, #s4; and 1 for #b5, #s5</span></span>
<ul>
<li><span data-ttu-id="bab0e-363">Pedido de calidad #4 para 1 del lote #b4, serie #s4</span><span class="sxs-lookup"><span data-stu-id="bab0e-363">Quality order #4 for 1 of batch #b4, serial #s4</span></span></li>
<li><span data-ttu-id="bab0e-364">Pedido de calidad #5 para 1 del lote #b5, serie #s5</span><span class="sxs-lookup"><span data-stu-id="bab0e-364">Quality order #5 for 1 of batch #b5, serial #s5</span></span></li>
</ul>
</li>
</ol>
<p><span data-ttu-id="bab0e-365"><strong>Nota:</strong> El lote se puede volver a utilizar.</span><span class="sxs-lookup"><span data-stu-id="bab0e-365"><strong>Note:</strong> The batch can be reused.</span></span></p>
</td>
</tr>
<tr>
<td><span data-ttu-id="bab0e-366">Cantidad fija: 2</span><span class="sxs-lookup"><span data-stu-id="bab0e-366">Fixed quantity: 2</span></span></td>
<td><span data-ttu-id="bab0e-367">No</span><span class="sxs-lookup"><span data-stu-id="bab0e-367">No</span></span></td>
<td>
<p><span data-ttu-id="bab0e-368">Número de lote: Sí</span><span class="sxs-lookup"><span data-stu-id="bab0e-368">Batch number: Yes</span></span></p>
<p><span data-ttu-id="bab0e-369">Número de serie: Sí</span><span class="sxs-lookup"><span data-stu-id="bab0e-369">Serial number: Yes</span></span></p>
</td>
<td>
<p><span data-ttu-id="bab0e-370">Cantidad de pedido: 10</span><span class="sxs-lookup"><span data-stu-id="bab0e-370">Order quantity: 10</span></span></p>
<ol>
<li><span data-ttu-id="bab0e-371">Notificar como terminado para 4: 1 para #b1, #s1; 1 para #b2, #s2; 1 para #b3, #s3; y 1 para #b4 #s4</span><span class="sxs-lookup"><span data-stu-id="bab0e-371">Report as finished for 4: 1 for #b1, #s1; 1 for #b2, #s2; 1 for #b3, #s3; and 1 for #b4, #s4</span></span>
<ul>
<li><span data-ttu-id="bab0e-372">Pedido de calidad #1 para 1 del lote #b1, serie #s1</span><span class="sxs-lookup"><span data-stu-id="bab0e-372">Quality order #1 for 1 of batch #b1, serial #s1</span></span></li>
<li><span data-ttu-id="bab0e-373">Pedido de calidad #2 para 1 del lote #b2, serie #s2</span><span class="sxs-lookup"><span data-stu-id="bab0e-373">Quality order #2 for 1 of batch #b2, serial #s2</span></span></li>
<li><span data-ttu-id="bab0e-374">Pedido de calidad #3 para 1 del lote #b3, serie #s3</span><span class="sxs-lookup"><span data-stu-id="bab0e-374">Quality order #3 for 1 of batch #b3, serial #s3</span></span></li>
<li><span data-ttu-id="bab0e-375">Pedido de calidad #4 para 1 del lote #b4, serie #s4</span><span class="sxs-lookup"><span data-stu-id="bab0e-375">Quality order #4 for 1 of batch #b4, serial #s4</span></span></li>
</ul>
<ul>
<li><span data-ttu-id="bab0e-376">Pedido de calidad #5 para 2, sin una referencia a un lote y un número de serie</span><span class="sxs-lookup"><span data-stu-id="bab0e-376">Quality order #5 for 2, without a reference to a batch and a serial number</span></span></li>
</ul>
</li>
<li><span data-ttu-id="bab0e-377">Notificar como terminado para 6: 1 para #b5, #s5; 1 para #b6, #s6; 1 para #b7, #s7; 1 para #b8, #s8; 1 para #b9, #s9; y 1 para #b10, #s10</span><span class="sxs-lookup"><span data-stu-id="bab0e-377">Report as finished for 6: 1 for #b5, #s5; 1 for #b6, #s6; 1 for #b7, #s7; 1 for #b8, #s8; 1 for #b9, #s9; and 1 for #b10, #s10</span></span>
<ul>
<li><span data-ttu-id="bab0e-378">No se crea ningún pedido de calidad.</span><span class="sxs-lookup"><span data-stu-id="bab0e-378">No quality orders are created.</span></span></li>
</ul>
</li>
</ol>
</td>
</tr>
</tbody>
</table>

## <a name="quality-management-pages"></a><span data-ttu-id="bab0e-379">Páginas de administración de calidad</span><span class="sxs-lookup"><span data-stu-id="bab0e-379">Quality management pages</span></span>
<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bab0e-380">Página</span><span class="sxs-lookup"><span data-stu-id="bab0e-380">Page</span></span></th>
<th><span data-ttu-id="bab0e-381">Descripción</span><span class="sxs-lookup"><span data-stu-id="bab0e-381">Description</span></span></th>
<th><span data-ttu-id="bab0e-382">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bab0e-382">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="bab0e-383">Asociaciones de calidad</span><span class="sxs-lookup"><span data-stu-id="bab0e-383">Quality associations</span></span></td>
<td><span data-ttu-id="bab0e-384">Consulte las secciones anteriores de este artículo.</span><span class="sxs-lookup"><span data-stu-id="bab0e-384">See the previous sections of this article.</span></span></td>
<td><span data-ttu-id="bab0e-385">Una asociación de calidad define toda la información siguiente para un pedido de calidad que se genera:</span><span class="sxs-lookup"><span data-stu-id="bab0e-385">A quality association defines all the following information for a quality order that is generated:</span></span>
<ul>
<li><span data-ttu-id="bab0e-386">El evento de transacción</span><span class="sxs-lookup"><span data-stu-id="bab0e-386">The transaction event</span></span></li>
<li><span data-ttu-id="bab0e-387">El conjunto de pruebas que se deben realizar en los artículos</span><span class="sxs-lookup"><span data-stu-id="bab0e-387">The set of tests that must be performed on the items</span></span></li>
<li><span data-ttu-id="bab0e-388">El nivel de calidad aceptable</span><span class="sxs-lookup"><span data-stu-id="bab0e-388">The AQL</span></span></li>
<li><span data-ttu-id="bab0e-389">El plan de muestreo</span><span class="sxs-lookup"><span data-stu-id="bab0e-389">The sampling plan</span></span></li>
</ul>
<span data-ttu-id="bab0e-390">Debe definir una asociación de calidad para cada variación de un proceso empresarial que requiera la generación automática de pedidos de calidad.</span><span class="sxs-lookup"><span data-stu-id="bab0e-390">You must define a quality association for each variation in a business process that requires automatic generation of quality orders.</span></span> <span data-ttu-id="bab0e-391">Por ejemplo, un pedido de calidad se puede generar en los procesos empresariales para los pedidos de compra, pedidos de cuarentena, pedidos de ventas y pedidos de producción.</span><span class="sxs-lookup"><span data-stu-id="bab0e-391">For example, a quality order can be generated in the business processes for purchase orders, quarantine orders, sales orders, and production orders.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="bab0e-392">Pruebas</span><span class="sxs-lookup"><span data-stu-id="bab0e-392">Tests</span></span></td>
<td><span data-ttu-id="bab0e-393">Utilice esta página para definir y visualizar las pruebas individuales que determinan si sus productos cumplen las especificaciones de calidad.</span><span class="sxs-lookup"><span data-stu-id="bab0e-393">Use this page to define and view the individual tests that determine whether your products meet quality specifications.</span></span> <span data-ttu-id="bab0e-394">Puede asignar una o varias pruebas individuales a un grupo de pruebas.</span><span class="sxs-lookup"><span data-stu-id="bab0e-394">You can assign one or more individual tests to a test group.</span></span> <span data-ttu-id="bab0e-395">En este caso, también especifica la información específica de la prueba, como los valores de medida aceptables.</span><span class="sxs-lookup"><span data-stu-id="bab0e-395">In this case, you also specify test-specific information, such as the acceptable measurement values.</span></span> <span data-ttu-id="bab0e-396">Los valores de medida se usan para pruebas cuantitativas y las variables de prueba se usan para las pruebas cualitativas.</span><span class="sxs-lookup"><span data-stu-id="bab0e-396">Measurement values are used for quantitative tests, and test variables are used for qualitative tests.</span></span>
<ul>
<li><span data-ttu-id="bab0e-397">Una prueba cuantitativa tiene un tipo de prueba de <strong>Entero</strong> o <strong>Fracción</strong> y una unidad de medida designada.</span><span class="sxs-lookup"><span data-stu-id="bab0e-397">A quantitative test has a test type of <strong>Integer</strong> or <strong>Fraction</strong>, and also has a designated unit of measure.</span></span> <span data-ttu-id="bab0e-398">Las especificaciones de calidad y los resultados de la prueba se expresan como números.</span><span class="sxs-lookup"><span data-stu-id="bab0e-398">Quality specifications and test results are expressed as numbers.</span></span></li>
<li><span data-ttu-id="bab0e-399">Una prueba cualitativa tiene una prueba de tipo <strong>Opción</strong>.</span><span class="sxs-lookup"><span data-stu-id="bab0e-399">A qualitative test has a test type of <strong>Option</strong>.</span></span> <span data-ttu-id="bab0e-400">Las pruebas cualitativas requieren información adicional sobre la variable de prueba que se está midiendo y sus opciones enumeradas.</span><span class="sxs-lookup"><span data-stu-id="bab0e-400">Qualitative tests require additional information about the test variable that is being measured and its enumerated options.</span></span> <span data-ttu-id="bab0e-401">Las especificaciones de calidad y los resultados de la prueba se expresan en función de un resultado.</span><span class="sxs-lookup"><span data-stu-id="bab0e-401">Quality specifications and test results are expressed according to an outcome.</span></span></li>
</ul></td>
<td><span data-ttu-id="bab0e-402">Una empresa de fabricación realiza dos pruebas en el material adquirido: una prueba cuantitativa sobre la calidad del material y una prueba cualitativa sobre los daños de embalaje.</span><span class="sxs-lookup"><span data-stu-id="bab0e-402">A manufacturing company performs two tests on purchased material: a quantitative test about material quality and a qualitative test about packaging damage.</span></span> <span data-ttu-id="bab0e-403">La empresa define información adicional sobre la prueba cualitativa para identificar la variable de prueba (embalaje dañado) y sus resultados.</span><span class="sxs-lookup"><span data-stu-id="bab0e-403">The company defines additional information about the qualitative test to identify the test variable (damaged packaging) and its outcomes.</span></span> <span data-ttu-id="bab0e-404">La empresa usa la página <strong>Grupos de prueba</strong> para asignar las dos pruebas a un grupo de pruebas y para especificar la información específica de la prueba.</span><span class="sxs-lookup"><span data-stu-id="bab0e-404">The company uses the <strong>Test groups</strong> page to assign the two tests to a test group and to specify the test-specific information.</span></span> <span data-ttu-id="bab0e-405">El grupo de pruebas se asigna a un pedido de calidad, de modo que la empresa puede informar de los resultados de la prueba para las dos pruebas.</span><span class="sxs-lookup"><span data-stu-id="bab0e-405">The test group is assigned to a quality order, so that the company can report test results for the two tests.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="bab0e-406">Grupos de prueba</span><span class="sxs-lookup"><span data-stu-id="bab0e-406">Test groups</span></span></td>
<td><span data-ttu-id="bab0e-407">Use esta página para establecer, editar y ver los grupos de prueba y las pruebas individuales asignadas a un grupo de prueba.</span><span class="sxs-lookup"><span data-stu-id="bab0e-407">Use this page to set up, edit, and view test groups and the individual tests that are assigned to a test group.</span></span> <span data-ttu-id="bab0e-408">En el panel superior se muestran los grupos de pruebas y en el inferior se muestran las pruebas asignadas a un grupo de pruebas seleccionado.</span><span class="sxs-lookup"><span data-stu-id="bab0e-408">The upper pane displays test groups, and the lower pane displays the tests that are assigned to a selected test group.</span></span> <span data-ttu-id="bab0e-409">A un grupo de pruebas se le asignan varias directivas, por ejemplo, un plan de muestreo, un nivel de calidad aceptable (AQL) y el requisito de la prueba destructiva.</span><span class="sxs-lookup"><span data-stu-id="bab0e-409">You assign several policies to a test group, such as a sampling plan, an AQL, and the requirement for destructive testing.</span></span> <span data-ttu-id="bab0e-410">Al asignar una prueba individual a un grupo de prueba, define información adicional, como la secuencia, los documentos, y las fechas de validez.</span><span class="sxs-lookup"><span data-stu-id="bab0e-410">When you assign an individual test to a test group, you define additional information, such as the sequence, documents, and validity dates.</span></span> <span data-ttu-id="bab0e-411">Para una prueba cuantitativa, la información que define también incluye los valores de medida aceptables.</span><span class="sxs-lookup"><span data-stu-id="bab0e-411">For a quantitative test, the information that you define also includes the acceptable measurement values.</span></span> <span data-ttu-id="bab0e-412">Para una prueba cualitativa, la información incluye la variable de prueba y el resultado predeterminado.</span><span class="sxs-lookup"><span data-stu-id="bab0e-412">For a qualitative test, the information includes the test variable and default outcome.</span></span> <span data-ttu-id="bab0e-413">El grupo de prueba asignado a un pedido de calidad define el conjunto predeterminado de pruebas que se tienen que realizar sobre el artículo especificado.</span><span class="sxs-lookup"><span data-stu-id="bab0e-413">The test group that is assigned to a quality order defines the default set of tests that must be performed on the specified item.</span></span> <span data-ttu-id="bab0e-414">No obstante, puede agregar, cambiar o eliminar las pruebas en el pedido de calidad.</span><span class="sxs-lookup"><span data-stu-id="bab0e-414">However, you can add, delete, or change tests on the quality order.</span></span> <span data-ttu-id="bab0e-415">Los resultados de prueba se notifican para cada prueba de un pedido de calidad.</span><span class="sxs-lookup"><span data-stu-id="bab0e-415">Test results are reported for each test on a quality order.</span></span></td>
<td><span data-ttu-id="bab0e-416">Un fabricante define un grupo de pruebas para cada variación de sus criterios de calidad.</span><span class="sxs-lookup"><span data-stu-id="bab0e-416">A manufacturing company defines a test group for each variation of its quality guidelines.</span></span> <span data-ttu-id="bab0e-417">Los distintos grupos de pruebas reflejan las diferencias de los planes de muestreo, los conjuntos de pruebas que se deben realizar en conjunto, el AQL y otros factores.</span><span class="sxs-lookup"><span data-stu-id="bab0e-417">The various test groups reflect differences in the sampling plans, the sets of tests that must be performed together, the AQL, and other factors.</span></span> <span data-ttu-id="bab0e-418">Para las pruebas cuantitativas también hay diferencias en los valores de medida aceptables.</span><span class="sxs-lookup"><span data-stu-id="bab0e-418">For quantitative tests, there are also differences in the acceptable measurement values.</span></span> <span data-ttu-id="bab0e-419">Para aplicar sus criterios de calidad, la empresa asigna un grupo de prueba a cada regla con el fin de generar automáticamente pedidos de calidad en la página <strong>Asociaciones de calidad</strong> y también asigna un grupo de prueba a los pedidos de calidad creados manualmente.</span><span class="sxs-lookup"><span data-stu-id="bab0e-419">To enforce its quality guidelines, the company assigns a test group to each rule for automatically generating quality orders on the <strong>Quality associations</strong> page, and also assigns a test group to quality orders that are manually created.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="bab0e-420">Grupos de calidad de artículos</span><span class="sxs-lookup"><span data-stu-id="bab0e-420">Item quality groups</span></span></td>
<td><span data-ttu-id="bab0e-421">Use esta página para configurar, editar y ver los artículos asignados a un grupo de calidad o a los grupos de calidad asignados a un artículo.</span><span class="sxs-lookup"><span data-stu-id="bab0e-421">Use this page to set up, edit, and view the items that are assigned to a quality group or the quality groups that are assigned to an item.</span></span> <span data-ttu-id="bab0e-422">Un grupo de calidad representa requisitos de prueba comunes para los artículos.</span><span class="sxs-lookup"><span data-stu-id="bab0e-422">A quality group represents common testing requirements for items.</span></span> <span data-ttu-id="bab0e-423">Cuando haya definido los requisitos de prueba en la página <strong>Grupos de prueba</strong>, puede definir las reglas para generar automáticamente pedidos de calidad.</span><span class="sxs-lookup"><span data-stu-id="bab0e-423">After you define the test requirements on the <strong>Test groups</strong> page, you can define the rules for automatically generating quality orders.</span></span> <span data-ttu-id="bab0e-424">Para simplificar el proceso, no se definen reglas para artículos individuales.</span><span class="sxs-lookup"><span data-stu-id="bab0e-424">To simplify the process, you don&#39;t define rules for individual items.</span></span> <span data-ttu-id="bab0e-425">En su lugar, puede definir las reglas para un grupo de calidad mediante la página <strong>Asociaciones de calidad</strong>.</span><span class="sxs-lookup"><span data-stu-id="bab0e-425">Instead, you define rules for a quality group, by using the <strong>Quality associations</strong> page.</span></span> <span data-ttu-id="bab0e-426">También puede usar la página <strong>Grupos de calidad de artículos</strong> para un grupo de calidad seleccionado para asignar artículos relevantes a dicho grupo.</span><span class="sxs-lookup"><span data-stu-id="bab0e-426">You can also use the <strong>Item quality groups</strong> page for a selected quality group to assign relevant items to that group.</span></span> <span data-ttu-id="bab0e-427">También puede usar la página <strong>Grupos de calidad de artículos</strong> para un artículo seleccionado para asignar grupos de calidad relevantes a dicho artículo.</span><span class="sxs-lookup"><span data-stu-id="bab0e-427">You can also use the <strong>Item quality groups</strong> page for a selected item to assign relevant quality groups to that item.</span></span></td>
<td><span data-ttu-id="bab0e-428">Un fabricante compra varias materias primas con los mismos requisitos de prueba para una inspección entrante.</span><span class="sxs-lookup"><span data-stu-id="bab0e-428">A manufacturing company purchases various raw materials that have the same testing requirements for incoming inspection.</span></span> <span data-ttu-id="bab0e-429">La empresa define un grupo de calidad y, después, le asigna números de artículo asociados con las materias primas para ese grupo.</span><span class="sxs-lookup"><span data-stu-id="bab0e-429">The company defines a quality group and then assigns the item numbers that are associated with the raw materials to that group.</span></span> <span data-ttu-id="bab0e-430">Más adelante, la empresa compra un nuevo tipo de materia prima con los mismos requisitos de prueba.</span><span class="sxs-lookup"><span data-stu-id="bab0e-430">Later, the company purchases a new type of raw material that has the same testing requirements.</span></span> <span data-ttu-id="bab0e-431">En lugar de configurar requisitos de prueba nuevos para el nuevo material, la empresa añade el número de artículo del nuevo material al grupo de calidad existente.</span><span class="sxs-lookup"><span data-stu-id="bab0e-431">Instead of setting up new testing requirements for the new material, the company adds the item number for the new material to the existing quality group.</span></span> <span data-ttu-id="bab0e-432">El mismo fabricante también produce artículos con los mismos requisitos de prueba y envía artículos con los mismos requisitos para las pruebas anteriores al envío.</span><span class="sxs-lookup"><span data-stu-id="bab0e-432">The same manufacturing company also produces items that have the same production testing requirements and ships items that have the same requirement for pre-shipment testing.</span></span> <span data-ttu-id="bab0e-433">La empresa define dos grupos de calidad adicionales y, después, asigna números de artículo pertinentes a cada grupo.</span><span class="sxs-lookup"><span data-stu-id="bab0e-433">The company defines two additional quality groups and then assigns the relevant item numbers to each group.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="bab0e-434">Variables de prueba</span><span class="sxs-lookup"><span data-stu-id="bab0e-434">Test variables</span></span></td>
<td><span data-ttu-id="bab0e-435">Use esta página para definir y ver las variables asociadas a una prueba cualitativa.</span><span class="sxs-lookup"><span data-stu-id="bab0e-435">Use this page to define and view the variables that are associated with a qualitative test.</span></span> <span data-ttu-id="bab0e-436">Para cada variable, define los resultados enumerados que representan las posibles opciones.</span><span class="sxs-lookup"><span data-stu-id="bab0e-436">For each variable, you define enumerated outcomes that represent the possible options.</span></span> <span data-ttu-id="bab0e-437">Puede definir pruebas en la página <strong>Pruebas</strong>.</span><span class="sxs-lookup"><span data-stu-id="bab0e-437">You define tests on the <strong>Tests</strong> page.</span></span> <span data-ttu-id="bab0e-438">Para las pruebas cualitativas, debe definir el tipo de prueba en <strong>Opción</strong>.</span><span class="sxs-lookup"><span data-stu-id="bab0e-438">For qualitative tests, you must set the test type to <strong>Option</strong>.</span></span> <span data-ttu-id="bab0e-439">Use la página <strong>Grupos de prueba</strong> para asignar una variable de prueba a una prueba individual.</span><span class="sxs-lookup"><span data-stu-id="bab0e-439">Use the <strong>Test groups</strong> page to assign a test variable to an individual test.</span></span></td>
<td><span data-ttu-id="bab0e-440">Una fábrica de galletas utiliza una prueba de inspección para el producto terminado.</span><span class="sxs-lookup"><span data-stu-id="bab0e-440">A manufacturing company that produces cookies uses an inspection test for the finished product.</span></span> <span data-ttu-id="bab0e-441">Esta prueba de inspección tiene varias variables.</span><span class="sxs-lookup"><span data-stu-id="bab0e-441">This inspection test has several variables.</span></span> <span data-ttu-id="bab0e-442">Una variable es el gusto y los posibles resultados para esta variable son bueno y malo.</span><span class="sxs-lookup"><span data-stu-id="bab0e-442">One variable is taste, and the possible outcomes for this variable are good and bad.</span></span> <span data-ttu-id="bab0e-443">Una segunda variable es el color y los posibles resultados son demasiado oscuro, demasiado claro y correcto.</span><span class="sxs-lookup"><span data-stu-id="bab0e-443">A second variable is color, and the possible outcomes are too dark, too light, and correct.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="bab0e-444">Resultados de la variable de prueba</span><span class="sxs-lookup"><span data-stu-id="bab0e-444">Test variable outcomes</span></span></td>
<td><span data-ttu-id="bab0e-445">Utilice esta página para configurar, editar y visualizar los resultados posibles de una variable de prueba asociada a una prueba cualitativa.</span><span class="sxs-lookup"><span data-stu-id="bab0e-445">Use this page to set up, edit, and to view the possible test results for a test variable that is associated with a qualitative test.</span></span> <span data-ttu-id="bab0e-446">Para cada resultado, asigne un estado de <strong>correcto</strong> o <strong>erróneo</strong>.</span><span class="sxs-lookup"><span data-stu-id="bab0e-446">For each outcome, you assign a <strong>pass</strong> or <strong>fail</strong> status.</span></span> <span data-ttu-id="bab0e-447">Deberá definir una variable y sus resultados para cada prueba cualitativa definida en la página <strong>Pruebas</strong>.</span><span class="sxs-lookup"><span data-stu-id="bab0e-447">You must define a variable and its outcomes for each qualitative test that is defined on the <strong>Tests</strong> page.</span></span> <span data-ttu-id="bab0e-448">(Para las pruebas cualitativas, el tipo de prueba se establece en <strong>Opción</strong> en la página <strong>Pruebas</strong>). Utilice la página <strong>Grupos de prueba</strong> para asignar una variable de prueba y el resultado predeterminado a una prueba cualitativa individual.</span><span class="sxs-lookup"><span data-stu-id="bab0e-448">(For qualitative tests, the test type is set to <strong>Option</strong> on the <strong>Tests</strong> page.) Use the <strong>Test groups</strong> page to assign a test variable and the default outcome to an individual qualitative test.</span></span></td>
<td><span data-ttu-id="bab0e-449">Una fábrica de galletas utiliza una prueba de inspección para el producto terminado.</span><span class="sxs-lookup"><span data-stu-id="bab0e-449">A manufacturing company that produces cookies uses an inspection test for the finished product.</span></span> <span data-ttu-id="bab0e-450">Esta prueba de inspección tiene varias variables.</span><span class="sxs-lookup"><span data-stu-id="bab0e-450">This inspection test has of several variables.</span></span> <span data-ttu-id="bab0e-451">Una variable es el gusto y los posibles resultados para esta variable son bueno y malo.</span><span class="sxs-lookup"><span data-stu-id="bab0e-451">One variable is taste, and the possible outcomes for this variable are good and bad.</span></span> <span data-ttu-id="bab0e-452">Una segunda variable es el color y los posibles resultados son demasiado oscuro, demasiado claro y correcto.</span><span class="sxs-lookup"><span data-stu-id="bab0e-452">A second variable is color, and the possible outcomes are too dark, too light, and correct.</span></span> <span data-ttu-id="bab0e-453">Cada resultado tiene asignado un estado de <strong>correcto</strong> o <strong>erróneo</strong>.</span><span class="sxs-lookup"><span data-stu-id="bab0e-453">A status of <strong>pass</strong> or <strong>fail</strong> is assigned to each outcome.</span></span> <span data-ttu-id="bab0e-454">Durante la prueba de inspección de cada variable, el inspector notifica el resultado de la prueba seleccionando uno de los resultados.</span><span class="sxs-lookup"><span data-stu-id="bab0e-454">During the inspection test for each variable, the inspector reports the test result by selecting one of the outcomes.</span></span></td>
</tr>
</tbody>
</table>



<a name="additional-resources"></a><span data-ttu-id="bab0e-455">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="bab0e-455">Additional resources</span></span>
--------

[<span data-ttu-id="bab0e-456">Procesos de administración de la calidad</span><span class="sxs-lookup"><span data-stu-id="bab0e-456">Quality management processes</span></span>](quality-management-processes.md)

[<span data-ttu-id="bab0e-457">Gestión de disconformidad</span><span class="sxs-lookup"><span data-stu-id="bab0e-457">Nonconformance management</span></span>](enable-nonconformance-management.md)
