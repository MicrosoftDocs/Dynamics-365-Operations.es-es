---
title: Visión general de la gestión de la calidad
description: Este tema describe cómo puede usar la gestión de calidad en Dynamics 365 Supply Chain Management para ayudar a mejorar la calidad del producto dentro de la cadena de suministro.
author: perlynne
manager: AnnBe
ms.date: 11/02/2017
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
ms.openlocfilehash: c9600e165da76948bb53a0188ec0b212a0fed84a
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2019
ms.locfileid: "2249595"
---
# <a name="quality-management-overview"></a><span data-ttu-id="32e99-103">Visión general de la gestión de la calidad</span><span class="sxs-lookup"><span data-stu-id="32e99-103">Quality management overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="32e99-104">Este tema describe cómo puede usar la gestión de calidad en Dynamics 365 Supply Chain Management para ayudar a mejorar la calidad del producto dentro de la cadena de suministro.</span><span class="sxs-lookup"><span data-stu-id="32e99-104">This topic describes how you can use quality management in Dynamics 365 Supply Chain Management to help improve product quality within your supply chain.</span></span>

<span data-ttu-id="32e99-105">La gestión de calidad puede ayudarle a gestionar los plazos de entrega cuando maneja productos de disconformidad, independientemente de su punto de origen.</span><span class="sxs-lookup"><span data-stu-id="32e99-105">Quality management can help you manage turnaround times when you handle nonconforming products, regardless of their point of origin.</span></span> <span data-ttu-id="32e99-106">Dado que los tipos de diagnóstico están vinculados a la corrección de los informes, Finance and Operations puede programar las tareas para corregir los problemas y evitar que se repitan.</span><span class="sxs-lookup"><span data-stu-id="32e99-106">Because diagnostic types are linked to correction reporting, Finance and Operations can schedule tasks to correct problems and prevent them from recurring.</span></span>

<span data-ttu-id="32e99-107">Además de la funcionalidad para gestionar la no conformidad, la gestión de calidad incluye la funcionalidad de realizar un seguimiento de las incidencias por tipo de problema (incluso problemas internos) y para identificar soluciones a corto plazo o a largo plazo.</span><span class="sxs-lookup"><span data-stu-id="32e99-107">In addition to functionality for managing nonconformance, quality management includes functionality for tracking issues by problem type (even internal problems), and for identifying solutions as short-term or long-term.</span></span> <span data-ttu-id="32e99-108">Las estadísticas acerca de los indicadores clave de rendimiento (KPI) proporcionan información sobre el historial de problemas de disconformidad anteriores y las soluciones utilizadas para corregirlos.</span><span class="sxs-lookup"><span data-stu-id="32e99-108">Statistics about key performance indicators (KPIs) provide insight into the history of previous nonconformance issues and the solutions that were used to correct them.</span></span> <span data-ttu-id="32e99-109">Puede usar los datos históricos para revisar la eficacia de las medidas de calidad anteriores y determinar las medidas adecuadas que se deben usar en el futuro.</span><span class="sxs-lookup"><span data-stu-id="32e99-109">You can use historical data to review the effectiveness of previous quality measures and determine appropriate measures to use in the future.</span></span>

<span data-ttu-id="32e99-110">Al configurar una asociación de calidad, Supply Chain Management puede generar pedidos de calidad para varios procesos empresariales, eventos y condiciones.</span><span class="sxs-lookup"><span data-stu-id="32e99-110">When you set up a quality association, Supply Chain Management can generate quality orders for various business processes, events, and conditions.</span></span> <span data-ttu-id="32e99-111">La asociación de calidad puede cubrir un artículo concreto, un determinado grupo de éstos o todos los artículos.</span><span class="sxs-lookup"><span data-stu-id="32e99-111">The quality association can cover a specific item, a specific group of items, or all items.</span></span>

## <a name="examples-of-the-use-of-quality-management"></a><span data-ttu-id="32e99-112">Ejemplos del uso de la gestión de calidad</span><span class="sxs-lookup"><span data-stu-id="32e99-112">Examples of the use of quality management</span></span>
<span data-ttu-id="32e99-113">La gestión de calidad es flexible y puede ejecutarse de distintas maneras para satisfacer los requisitos de niveles específicos de operaciones de la cadena de suministro.</span><span class="sxs-lookup"><span data-stu-id="32e99-113">Quality management is flexible and can be implemented in various ways to meet the requirements of specific levels of supply chain operations.</span></span> <span data-ttu-id="32e99-114">En los ejemplos siguientes se muestran usos posibles de estas características:</span><span class="sxs-lookup"><span data-stu-id="32e99-114">The following examples illustrate possible uses of these features:</span></span>

-   <span data-ttu-id="32e99-115">Inicie automáticamente un proceso de control de calidad en función de los criterios predefinidos (sobre el registro del almacén de un pedido de compra para un proveedor específico).</span><span class="sxs-lookup"><span data-stu-id="32e99-115">Automatically start a quality control process, based on predefined criteria (upon warehouse registration of a purchase order from a specific vendor).</span></span>
-   <span data-ttu-id="32e99-116">Bloquear el inventario durante la inspección para evitar que el inventario no aprobado se use (bloqueo completo de las cantidades de pedido de compra).</span><span class="sxs-lookup"><span data-stu-id="32e99-116">Block inventory during inspection to prevent non-approved inventory from being used (full blocking of purchase order quantities).</span></span>
-   <span data-ttu-id="32e99-117">Use el muestreo del artículo como parte de una asociación de calidad para definir la cantidad de inventario físico actual que debe inspeccionarse.</span><span class="sxs-lookup"><span data-stu-id="32e99-117">Use item sampling as part of a quality association to define the amount of current physical inventory that must be inspected.</span></span> <span data-ttu-id="32e99-118">El muestreo puede basarse en cantidades fijas o en un porcentaje.</span><span class="sxs-lookup"><span data-stu-id="32e99-118">Sampling can be based on fixed quantities or a percentage.</span></span>
-   <span data-ttu-id="32e99-119">Crear pedidos de calidad para recepciones parciales.</span><span class="sxs-lookup"><span data-stu-id="32e99-119">Create quality orders for partial receipts.</span></span> <span data-ttu-id="32e99-120">Para crear un pedido de calidad basado en la cantidad que se recibe físicamente con un pedido, debe seleccionar la casilla de verificación **Por cantidad actualizada** en el formulario **Muestreo de artículos** .</span><span class="sxs-lookup"><span data-stu-id="32e99-120">To create a quality order that is based on the quantity that is physically received with an order, you must select the **Per updated quantity** check box on the **Item sampling** form.</span></span>
-   <span data-ttu-id="32e99-121">Permite crear tipos de prueba que incluyen mínimo, máximo y valores de prueba de destino, y realizar pruebas cualitativas en contraposición a cuantitativas que tengan resultados de validación predefinidos.</span><span class="sxs-lookup"><span data-stu-id="32e99-121">Create test types that include minimum, maximum, and target test values, and perform qualitative-versus-quantitative testing that has predefined validation results.</span></span>
-   <span data-ttu-id="32e99-122">Especifique un nivel de calidad aceptable (AQL) para controlar las tolerancias de medida de calidad.</span><span class="sxs-lookup"><span data-stu-id="32e99-122">Specify an acceptable quality level (AQL) to control quality measure tolerances.</span></span>
-   <span data-ttu-id="32e99-123">Especifique los recursos que una operación de inspección requiere, por ejemplo instrumentos de prueba y un área de prueba.</span><span class="sxs-lookup"><span data-stu-id="32e99-123">Specify the resources that an inspection operation requires, such as a test area and test instruments.</span></span>

## <a name="working-with-quality-associations"></a><span data-ttu-id="32e99-124">Trabajar con asociaciones de calidad</span><span class="sxs-lookup"><span data-stu-id="32e99-124">Working with quality associations</span></span>
<span data-ttu-id="32e99-125">El proceso empresarial que utiliza una asociación de calidad puede estar relacionado con varios documentos de origen, como pedidos de compra, pedidos de ventas o pedidos de producción.</span><span class="sxs-lookup"><span data-stu-id="32e99-125">The business process that uses a quality association can be related to various source documents, such as purchase orders, sales orders, or production orders.</span></span>

<span data-ttu-id="32e99-126">Cada registro de asociación de calidad define el conjunto de pruebas, el nivel de calidad aceptable y el plan de muestreo que se aplica a los pedidos de calidad generados.</span><span class="sxs-lookup"><span data-stu-id="32e99-126">Each quality association record defines the set of tests, the AQL, and the sampling plan that applies to the quality orders that are generated.</span></span> <span data-ttu-id="32e99-127">Debe definir un registro de asociación de calidad para cada variación de un proceso empresarial.</span><span class="sxs-lookup"><span data-stu-id="32e99-127">You must define a quality association record for each variation in a business process.</span></span> <span data-ttu-id="32e99-128">Por ejemplo, puede configurar una asociación de calidad que genere un pedido de calidad cuando se actualice una recepción de producto de pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="32e99-128">For example, you can set up a quality association that generates a quality order when a purchase order product receipt is updated.</span></span> <span data-ttu-id="32e99-129">En función de la configuración del plan de ejecución, el propio proceso de activación puede bloquearse mientras que haya un pedido de calidad abierto o los siguientes procesos, por ejemplo, una factura de pedido de compra, se pueden bloquear.</span><span class="sxs-lookup"><span data-stu-id="32e99-129">Depending on the setup of the execution plan, the triggering process itself can be blocked while there is an open quality order, or the next processes, such as purchase order invoicing, can be blocked.</span></span>

<span data-ttu-id="32e99-130">**Nota:** mientras haya pedidos de calidad abiertos, las cantidades de inventario se bloquean automáticamente para evitar su emisión.</span><span class="sxs-lookup"><span data-stu-id="32e99-130">**Note:** While there are open quality orders, inventory quantities are automatically blocked from being issued.</span></span> <span data-ttu-id="32e99-131">En función del ajuste **Bloqueo completo** de la página **Muestreos de artículos**, la cantidad es la cantidad en el pedido de calidad o la cantidad en la línea del documento de origen.</span><span class="sxs-lookup"><span data-stu-id="32e99-131">Depending on the **Full blocking** setting on the **Item samplings** page, the quantity is either the quantity on the quality order or the quantity on the source document line.</span></span>

<span data-ttu-id="32e99-132">Para un determinado proceso empresarial, el registro de la asociación de calidad identifica el evento y las condiciones para las que se genera un pedido de calidad.</span><span class="sxs-lookup"><span data-stu-id="32e99-132">For a given business process, the quality association record identifies the event and the conditions that a quality order is generated for.</span></span> <span data-ttu-id="32e99-133">Las condiciones pueden especificarse para un sitio o para una entidad jurídica.</span><span class="sxs-lookup"><span data-stu-id="32e99-133">The conditions can be specific to either a site or a legal entity.</span></span> <span data-ttu-id="32e99-134">Un pedido de calidad que requiera pruebas destructivas solo se puede generar si hay un inventario disponible para el evento.</span><span class="sxs-lookup"><span data-stu-id="32e99-134">A quality order that involves destructive tests can be generated only when on-hand inventory exists for the event.</span></span>

<span data-ttu-id="32e99-135">En los siguientes ejemplos se muestra cómo se define un registro de asociación de calidad para las variantes de cada proceso empresarial.</span><span class="sxs-lookup"><span data-stu-id="32e99-135">The following examples illustrate how a quality association record is defined for the variations in each business process.</span></span> <span data-ttu-id="32e99-136">Para cada ejemplo, la siguiente tabla resume los eventos y las condiciones definidos por un registro de asociación de calidad.</span><span class="sxs-lookup"><span data-stu-id="32e99-136">For each example, the following table summarizes the events and conditions that are defined by a quality association record.</span></span>

<table>
<tbody>
<tr>
<th><span data-ttu-id="32e99-137">Tipo de referencia</span><span class="sxs-lookup"><span data-stu-id="32e99-137">Reference type</span></span></th>
<th><span data-ttu-id="32e99-138">Tipo de evento</span><span class="sxs-lookup"><span data-stu-id="32e99-138">Event type</span></span></th>
<th><span data-ttu-id="32e99-139">Ejecución</span><span class="sxs-lookup"><span data-stu-id="32e99-139">Execution</span></span></th>
<th><span data-ttu-id="32e99-140">Bloqueo de eventos</span><span class="sxs-lookup"><span data-stu-id="32e99-140">Event blocking</span></span></th>
<th><span data-ttu-id="32e99-141">Referencia del documento</span><span class="sxs-lookup"><span data-stu-id="32e99-141">Document reference</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="32e99-142">Inventario</span><span class="sxs-lookup"><span data-stu-id="32e99-142">Inventory</span></span></td>
<td><span data-ttu-id="32e99-143">No aplicable</span><span class="sxs-lookup"><span data-stu-id="32e99-143">Not applicable</span></span></td>
<td><span data-ttu-id="32e99-144">No aplicable</span><span class="sxs-lookup"><span data-stu-id="32e99-144">Not applicable</span></span></td>
<td><span data-ttu-id="32e99-145">Ninguna</span><span class="sxs-lookup"><span data-stu-id="32e99-145">None</span></span></td>
<td><span data-ttu-id="32e99-146">Todas</span><span class="sxs-lookup"><span data-stu-id="32e99-146">All</span></span></td>
</tr>
<tr>
<td rowspan="7"><span data-ttu-id="32e99-147">Ventas</span><span class="sxs-lookup"><span data-stu-id="32e99-147">Sales</span></span></td>
<td rowspan="4"><span data-ttu-id="32e99-148">Proceso de picking programado</span><span class="sxs-lookup"><span data-stu-id="32e99-148">Picking process is scheduled</span></span></td>
<td rowspan="4"><span data-ttu-id="32e99-149">Anterior</span><span class="sxs-lookup"><span data-stu-id="32e99-149">Before</span></span></td>
<td><span data-ttu-id="32e99-150">Ninguna</span><span class="sxs-lookup"><span data-stu-id="32e99-150">None</span></span></td>
<td rowspan="22"><span data-ttu-id="32e99-151">Solo Id. específico, Grupo o Todo</span><span class="sxs-lookup"><span data-stu-id="32e99-151">Specific ID, Group, or All only</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="32e99-152">Proceso de picking</span><span class="sxs-lookup"><span data-stu-id="32e99-152">Picking process</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="32e99-153">Albarán</span><span class="sxs-lookup"><span data-stu-id="32e99-153">Packing slip</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="32e99-154">Factura</span><span class="sxs-lookup"><span data-stu-id="32e99-154">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="32e99-155">Albarán</span><span class="sxs-lookup"><span data-stu-id="32e99-155">Packing slip</span></span></td>
<td rowspan="3"><span data-ttu-id="32e99-156">Anterior</span><span class="sxs-lookup"><span data-stu-id="32e99-156">Before</span></span></td>
<td><span data-ttu-id="32e99-157">Ninguna</span><span class="sxs-lookup"><span data-stu-id="32e99-157">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="32e99-158">Albarán</span><span class="sxs-lookup"><span data-stu-id="32e99-158">Packing slip</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="32e99-159">Factura</span><span class="sxs-lookup"><span data-stu-id="32e99-159">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="15"><span data-ttu-id="32e99-160">Compra</span><span class="sxs-lookup"><span data-stu-id="32e99-160">Purchase</span></span></td>
<td rowspan="7"><span data-ttu-id="32e99-161">Lista de recepciones</span><span class="sxs-lookup"><span data-stu-id="32e99-161">Receipt list</span></span></td>
<td rowspan="4"><span data-ttu-id="32e99-162">Anterior</span><span class="sxs-lookup"><span data-stu-id="32e99-162">Before</span></span></td>
<td><span data-ttu-id="32e99-163">Ninguna</span><span class="sxs-lookup"><span data-stu-id="32e99-163">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="32e99-164">Lista de recepciones</span><span class="sxs-lookup"><span data-stu-id="32e99-164">Receipt list</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="32e99-165">Recepción de producto</span><span class="sxs-lookup"><span data-stu-id="32e99-165">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="32e99-166">Factura</span><span class="sxs-lookup"><span data-stu-id="32e99-166">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="32e99-167">Posterior</span><span class="sxs-lookup"><span data-stu-id="32e99-167">After</span></span></td>
<td><span data-ttu-id="32e99-168">Ninguna</span><span class="sxs-lookup"><span data-stu-id="32e99-168">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="32e99-169">Recepción de producto</span><span class="sxs-lookup"><span data-stu-id="32e99-169">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="32e99-170">Factura</span><span class="sxs-lookup"><span data-stu-id="32e99-170">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="32e99-171">Registro</span><span class="sxs-lookup"><span data-stu-id="32e99-171">Registration</span></span></td>
<td rowspan="3"><span data-ttu-id="32e99-172">No aplicable</span><span class="sxs-lookup"><span data-stu-id="32e99-172">Not applicable</span></span></td>
<td><span data-ttu-id="32e99-173">Ninguna</span><span class="sxs-lookup"><span data-stu-id="32e99-173">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="32e99-174">Recepción de producto</span><span class="sxs-lookup"><span data-stu-id="32e99-174">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="32e99-175">Factura</span><span class="sxs-lookup"><span data-stu-id="32e99-175">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="5"><span data-ttu-id="32e99-176">Recepción de producto</span><span class="sxs-lookup"><span data-stu-id="32e99-176">Product receipt</span></span></td>
<td rowspan="3"><span data-ttu-id="32e99-177">Anterior</span><span class="sxs-lookup"><span data-stu-id="32e99-177">Before</span></span></td>
<td><span data-ttu-id="32e99-178">Ninguna</span><span class="sxs-lookup"><span data-stu-id="32e99-178">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="32e99-179">Recepción de producto</span><span class="sxs-lookup"><span data-stu-id="32e99-179">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="32e99-180">Factura</span><span class="sxs-lookup"><span data-stu-id="32e99-180">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="2"><span data-ttu-id="32e99-181">Posterior</span><span class="sxs-lookup"><span data-stu-id="32e99-181">After</span></span></td>
<td><span data-ttu-id="32e99-182">Ninguna</span><span class="sxs-lookup"><span data-stu-id="32e99-182">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="32e99-183">Factura</span><span class="sxs-lookup"><span data-stu-id="32e99-183">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="8"><span data-ttu-id="32e99-184">Producción</span><span class="sxs-lookup"><span data-stu-id="32e99-184">Production</span></span></td>
<td rowspan="3"><span data-ttu-id="32e99-185">Registro</span><span class="sxs-lookup"><span data-stu-id="32e99-185">Registration</span></span></td>
<td rowspan="3"><span data-ttu-id="32e99-186">No aplicable</span><span class="sxs-lookup"><span data-stu-id="32e99-186">Not applicable</span></span></td>
<td><span data-ttu-id="32e99-187">Ninguna</span><span class="sxs-lookup"><span data-stu-id="32e99-187">None</span></span></td>
<td rowspan="12"><span data-ttu-id="32e99-188">Todas</span><span class="sxs-lookup"><span data-stu-id="32e99-188">All</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="32e99-189">Notificar como terminado</span><span class="sxs-lookup"><span data-stu-id="32e99-189">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="32e99-190">Fin</span><span class="sxs-lookup"><span data-stu-id="32e99-190">End</span></span></td>
</tr>
<tr>
<td rowspan="5"><span data-ttu-id="32e99-191">Notificar como terminado</span><span class="sxs-lookup"><span data-stu-id="32e99-191">Report as finished</span></span></td>
<td rowspan="3"><span data-ttu-id="32e99-192">Anterior</span><span class="sxs-lookup"><span data-stu-id="32e99-192">Before</span></span></td>
<td><span data-ttu-id="32e99-193">Ninguna</span><span class="sxs-lookup"><span data-stu-id="32e99-193">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="32e99-194">Notificar como terminado</span><span class="sxs-lookup"><span data-stu-id="32e99-194">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="32e99-195">Fin</span><span class="sxs-lookup"><span data-stu-id="32e99-195">End</span></span></td>
</tr>
<tr>
<td rowspan="2"><span data-ttu-id="32e99-196">Posterior</span><span class="sxs-lookup"><span data-stu-id="32e99-196">After</span></span></td>
<td><span data-ttu-id="32e99-197">Ninguna</span><span class="sxs-lookup"><span data-stu-id="32e99-197">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="32e99-198">Fin</span><span class="sxs-lookup"><span data-stu-id="32e99-198">End</span></span></td>
</tr>
<tr>
<td rowspan="4"><span data-ttu-id="32e99-199">Cuarentena</span><span class="sxs-lookup"><span data-stu-id="32e99-199">Quarantine</span></span></td>
<td rowspan="3"><span data-ttu-id="32e99-200">Notificar como terminado</span><span class="sxs-lookup"><span data-stu-id="32e99-200">Report as finished</span></span></td>
<td rowspan="2"><span data-ttu-id="32e99-201">Anterior</span><span class="sxs-lookup"><span data-stu-id="32e99-201">Before</span></span></td>
<td><span data-ttu-id="32e99-202">Notificar como terminado</span><span class="sxs-lookup"><span data-stu-id="32e99-202">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="32e99-203">Fin</span><span class="sxs-lookup"><span data-stu-id="32e99-203">End</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="32e99-204">Posterior</span><span class="sxs-lookup"><span data-stu-id="32e99-204">After</span></span></td>
<td><span data-ttu-id="32e99-205">Fin</span><span class="sxs-lookup"><span data-stu-id="32e99-205">End</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="32e99-206">Fin</span><span class="sxs-lookup"><span data-stu-id="32e99-206">End</span></span></td>
<td><span data-ttu-id="32e99-207">Anterior</span><span class="sxs-lookup"><span data-stu-id="32e99-207">Before</span></span></td>
<td><span data-ttu-id="32e99-208">Fin</span><span class="sxs-lookup"><span data-stu-id="32e99-208">End</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="32e99-209">Operación de ruta</span><span class="sxs-lookup"><span data-stu-id="32e99-209">Route operation</span></span></td>
<td rowspan="3"><span data-ttu-id="32e99-210">Notificar como terminado</span><span class="sxs-lookup"><span data-stu-id="32e99-210">Report as finished</span></span></td>
<td rowspan="2"><span data-ttu-id="32e99-211">Anterior</span><span class="sxs-lookup"><span data-stu-id="32e99-211">Before</span></span></td>
<td><span data-ttu-id="32e99-212">Ninguna</span><span class="sxs-lookup"><span data-stu-id="32e99-212">None</span></span></td>
<td rowspan="3"><span data-ttu-id="32e99-213">Id. específico, Grupo o Todo, y Recurso específico, Grupo o Todo</span><span class="sxs-lookup"><span data-stu-id="32e99-213">Specific ID, Group, or All, and Resource specific, Group, or All</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="32e99-214">Notificar como terminado</span><span class="sxs-lookup"><span data-stu-id="32e99-214">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="32e99-215">Posterior</span><span class="sxs-lookup"><span data-stu-id="32e99-215">After</span></span></td>
<td><span data-ttu-id="32e99-216">Ninguna</span><span class="sxs-lookup"><span data-stu-id="32e99-216">None</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="32e99-217">Producción de coproductos</span><span class="sxs-lookup"><span data-stu-id="32e99-217">Co-product production</span></span></td>
<td><span data-ttu-id="32e99-218">Registro</span><span class="sxs-lookup"><span data-stu-id="32e99-218">Registration</span></span></td>
<td><span data-ttu-id="32e99-219">No aplicable</span><span class="sxs-lookup"><span data-stu-id="32e99-219">Not applicable</span></span></td>
<td rowspan="3"><span data-ttu-id="32e99-220">Ninguna</span><span class="sxs-lookup"><span data-stu-id="32e99-220">None</span></span></td>
<td rowspan="3"><span data-ttu-id="32e99-221">Todas</span><span class="sxs-lookup"><span data-stu-id="32e99-221">All</span></span></td>
</tr>
<tr>
<td rowspan="2"><span data-ttu-id="32e99-222">Notificar como terminado</span><span class="sxs-lookup"><span data-stu-id="32e99-222">Report as finished</span></span></td>
<td><span data-ttu-id="32e99-223">Anterior</span><span class="sxs-lookup"><span data-stu-id="32e99-223">Before</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="32e99-224">Posterior</span><span class="sxs-lookup"><span data-stu-id="32e99-224">After</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="32e99-225">La siguiente tabla proporciona más información acerca de cómo se pueden generar los pedidos de calidad para tipos de procesos concretos.</span><span class="sxs-lookup"><span data-stu-id="32e99-225">The following table provides more information about how quality orders can be generated for specific types of processes.</span></span>
<div class="tableSection">

<table>
<tbody>
<tr>
<th><span data-ttu-id="32e99-226">Tipo de proceso</span><span class="sxs-lookup"><span data-stu-id="32e99-226">Type of process</span></span></th>
<th><span data-ttu-id="32e99-227">Cuando los pedidos de calidad se pueden generar automáticamente</span><span class="sxs-lookup"><span data-stu-id="32e99-227">When quality orders can be automatically generated</span></span></th>
<th><span data-ttu-id="32e99-228">Cuando los pedidos de calidad se pueden generar si se requiere una prueba destructiva</span><span class="sxs-lookup"><span data-stu-id="32e99-228">When quality orders can be generated if destructive testing is required</span></span></th>
<th><span data-ttu-id="32e99-229">Información acerca de la condición</span><span class="sxs-lookup"><span data-stu-id="32e99-229">Condition information</span></span></th>
<th><span data-ttu-id="32e99-230">Información acerca de la generación manual</span><span class="sxs-lookup"><span data-stu-id="32e99-230">Manual generation information</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="32e99-231">Pedido de compra</span><span class="sxs-lookup"><span data-stu-id="32e99-231">Purchase order</span></span></td>
<td><span data-ttu-id="32e99-232">Antes o después de que se registre una lista de recepciones o una recepción de producto del material recibido</span><span class="sxs-lookup"><span data-stu-id="32e99-232">Before or after a receipts list or product receipt for the material that is received is posted</span></span></td>
<td><span data-ttu-id="32e99-233">Después del registro de la recepción de producto, ya que el material debe estar disponible para la prueba destructiva</span><span class="sxs-lookup"><span data-stu-id="32e99-233">After the product receipt for the material that is received is posted, because the material must be available for destructive testing</span></span></td>
<td><span data-ttu-id="32e99-234">El requisito de un pedido de calidad puede reflejar un sitio, un artículo o proveedor en concreto, además de una combinación de estas condiciones.</span><span class="sxs-lookup"><span data-stu-id="32e99-234">The requirement for a quality order can reflect a particular site, item, or vendor, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="32e99-235">Un pedido de calidad generado manualmente que hace referencia a un pedido de compra puede usar la información de un registro de asociación de calidad, como el plan de muestreo de la prueba.</span><span class="sxs-lookup"><span data-stu-id="32e99-235">A manually generated quality order that refers to a purchase order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="32e99-236">Orden de cuarentena</span><span class="sxs-lookup"><span data-stu-id="32e99-236">Quarantine order</span></span></td>
<td><span data-ttu-id="32e99-237">Antes o después de que se notifique que ha finalizado la orden de cuarentena</span><span class="sxs-lookup"><span data-stu-id="32e99-237">Before or after the quarantine order is reported as finished or ended</span></span></td>
<td><span data-ttu-id="32e99-238">No se pueden generar pedidos de calidad que necesiten pruebas destructivas.</span><span class="sxs-lookup"><span data-stu-id="32e99-238">Quality orders that require destructive tests can&#39;t be generated.</span></span> <span data-ttu-id="32e99-239">Se supone que la funcionalidad de la orden de cuarentena gestiona la disposición del material destruido.</span><span class="sxs-lookup"><span data-stu-id="32e99-239">It&#39;s assumed that the quarantine order functionality handles the disposition of the material that is destroyed.</span></span></td>
<td><span data-ttu-id="32e99-240">El requisito de un pedido de calidad puede reflejar un sitio, un artículo o proveedor en concreto, además de una combinación de estas condiciones.</span><span class="sxs-lookup"><span data-stu-id="32e99-240">The requirement for a quality order can reflect a particular site, item, or vendor, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="32e99-241">Un pedido de calidad generado manualmente que hace referencia a una orden de cuarentena puede usar la información de un registro de asociación de calidad, como el plan de muestreo de la prueba.</span><span class="sxs-lookup"><span data-stu-id="32e99-241">A manually generated quality order that refers to a quarantine order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="32e99-242">Pedido de ventas</span><span class="sxs-lookup"><span data-stu-id="32e99-242">Sales order</span></span></td>
<td><span data-ttu-id="32e99-243">Antes de una actualización programada del proceso de selección o del albarán para los artículos que se envían</span><span class="sxs-lookup"><span data-stu-id="32e99-243">Before a scheduled picking process or packing slip update for the items that are being shipped</span></span></td>
<td><span data-ttu-id="32e99-244">En cualquier paso</span><span class="sxs-lookup"><span data-stu-id="32e99-244">At any step</span></span></td>
<td><span data-ttu-id="32e99-245">El requisito de un pedido de calidad puede reflejar un sitio, un artículo o un cliente concreto, además de una combinación de estas condiciones.</span><span class="sxs-lookup"><span data-stu-id="32e99-245">The requirement for a quality order can reflect a particular site, item, or customer, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="32e99-246">Un pedido de calidad generado manualmente que hace referencia a un pedido de ventas puede usar la información de un registro de asociación de calidad, como el plan de muestreo de la prueba.</span><span class="sxs-lookup"><span data-stu-id="32e99-246">A manually generated quality order that refers to a sales order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="32e99-247">Pedido de producción</span><span class="sxs-lookup"><span data-stu-id="32e99-247">Production order</span></span></td>
<td><span data-ttu-id="32e99-248">Antes o después de que se registre la cantidad finalizada del pedido de producción</span><span class="sxs-lookup"><span data-stu-id="32e99-248">Before or after the finished quantity for the production order is reported</span></span></td>
<td><span data-ttu-id="32e99-249">Después de que se registre la cantidad finalizada del pedido de producción</span><span class="sxs-lookup"><span data-stu-id="32e99-249">After the finished quantity for the production order is reported</span></span></td>
<td><span data-ttu-id="32e99-250">El requisito de un pedido de calidad puede reflejar un sitio o un artículo concreto, además de una combinación de estas condiciones.</span><span class="sxs-lookup"><span data-stu-id="32e99-250">The requirement for a quality order can reflect a particular site or item, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="32e99-251">Un pedido de calidad generado manualmente que hace referencia a un pedido de producción puede usar la información de un registro de asociación de calidad, como el plan de muestreo de la prueba.</span><span class="sxs-lookup"><span data-stu-id="32e99-251">A manually generated quality order that refers to a production order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="32e99-252">Pedido de producción con una operación de ruta</span><span class="sxs-lookup"><span data-stu-id="32e99-252">Production order that has a route operation</span></span></td>
<td><span data-ttu-id="32e99-253">Antes o después de finalizar el informe de la operación</span><span class="sxs-lookup"><span data-stu-id="32e99-253">Before or after the report is finished for an operation</span></span></td>
<td><span data-ttu-id="32e99-254">Después de finalizar el informe de producción de la última operación</span><span class="sxs-lookup"><span data-stu-id="32e99-254">After the reporting production is finished for the last operation</span></span></td>
<td><span data-ttu-id="32e99-255">El requisito de un pedido de calidad puede reflejar un sitio, un artículo o un recurso de operaciones concreto, además de una combinación de estas condiciones.</span><span class="sxs-lookup"><span data-stu-id="32e99-255">The requirement for a quality order can reflect a particular, site, item, or operations resource, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="32e99-256">Un pedido de calidad generado manualmente que hace referencia a una operación de ruta puede usar la información de un registro de asociación de calidad, como el plan de muestreo de la prueba.</span><span class="sxs-lookup"><span data-stu-id="32e99-256">A manually generated quality order that refers to a route operation can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="32e99-257">Inventario</span><span class="sxs-lookup"><span data-stu-id="32e99-257">Inventory</span></span></td>
<td><span data-ttu-id="32e99-258">Un pedido de calidad no se puede generar automáticamente para una transacción en un diario de inventario o para las transacciones de un pedido de transferencia.</span><span class="sxs-lookup"><span data-stu-id="32e99-258">A quality order cannot be automatically generated for a transaction in an inventory journal or for transfer order transactions.</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="32e99-259">Un pedido de calidad se debe crear manualmente para la cantidad de inventario de un artículo.</span><span class="sxs-lookup"><span data-stu-id="32e99-259">A quality order must be created manually for an item&#39;s inventory quantity.</span></span> <span data-ttu-id="32e99-260">Se requiere el inventario físico disponible.</span><span class="sxs-lookup"><span data-stu-id="32e99-260">Physical on-hand inventory is required.</span></span></td>
</tr>
</tbody>
</table>

## <a name="quality-management-pages"></a><span data-ttu-id="32e99-261">Páginas de administración de calidad</span><span class="sxs-lookup"><span data-stu-id="32e99-261">Quality management pages</span></span>
<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="32e99-262">Página</span><span class="sxs-lookup"><span data-stu-id="32e99-262">Page</span></span></th>
<th><span data-ttu-id="32e99-263">Descripción</span><span class="sxs-lookup"><span data-stu-id="32e99-263">Description</span></span></th>
<th><span data-ttu-id="32e99-264">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="32e99-264">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="32e99-265">Asociaciones de calidad</span><span class="sxs-lookup"><span data-stu-id="32e99-265">Quality associations</span></span></td>
<td><span data-ttu-id="32e99-266">Consulte las secciones anteriores de este artículo.</span><span class="sxs-lookup"><span data-stu-id="32e99-266">See the previous sections of this article.</span></span></td>
<td><span data-ttu-id="32e99-267">Una asociación de calidad define toda la información siguiente para un pedido de calidad que se genera:</span><span class="sxs-lookup"><span data-stu-id="32e99-267">A quality association defines all the following information for a quality order that is generated:</span></span>
<ul>
<li><span data-ttu-id="32e99-268">El evento de transacción</span><span class="sxs-lookup"><span data-stu-id="32e99-268">The transaction event</span></span></li>
<li><span data-ttu-id="32e99-269">El conjunto de pruebas que se deben realizar en los artículos</span><span class="sxs-lookup"><span data-stu-id="32e99-269">The set of tests that must be performed on the items</span></span></li>
<li><span data-ttu-id="32e99-270">El nivel de calidad aceptable</span><span class="sxs-lookup"><span data-stu-id="32e99-270">The AQL</span></span></li>
<li><span data-ttu-id="32e99-271">El plan de muestreo</span><span class="sxs-lookup"><span data-stu-id="32e99-271">The sampling plan</span></span></li>
</ul>
<span data-ttu-id="32e99-272">Debe definir una asociación de calidad para cada variación de un proceso empresarial que requiera la generación automática de pedidos de calidad.</span><span class="sxs-lookup"><span data-stu-id="32e99-272">You must define a quality association for each variation in a business process that requires automatic generation of quality orders.</span></span> <span data-ttu-id="32e99-273">Por ejemplo, un pedido de calidad se puede generar en los procesos empresariales para los pedidos de compra, pedidos de cuarentena, pedidos de ventas y pedidos de producción.</span><span class="sxs-lookup"><span data-stu-id="32e99-273">For example, a quality order can be generated in the business processes for purchase orders, quarantine orders, sales orders, and production orders.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="32e99-274">Pruebas</span><span class="sxs-lookup"><span data-stu-id="32e99-274">Tests</span></span></td>
<td><span data-ttu-id="32e99-275">Utilice esta página para definir y visualizar las pruebas individuales que determinan si sus productos cumplen las especificaciones de calidad.</span><span class="sxs-lookup"><span data-stu-id="32e99-275">Use this page to define and view the individual tests that determine whether your products meet quality specifications.</span></span> <span data-ttu-id="32e99-276">Puede asignar una o varias pruebas individuales a un grupo de pruebas.</span><span class="sxs-lookup"><span data-stu-id="32e99-276">You can assign one or more individual tests to a test group.</span></span> <span data-ttu-id="32e99-277">En este caso, también especifica la información específica de la prueba, como los valores de medida aceptables.</span><span class="sxs-lookup"><span data-stu-id="32e99-277">In this case, you also specify test-specific information, such as the acceptable measurement values.</span></span> <span data-ttu-id="32e99-278">Los valores de medida se usan para pruebas cuantitativas y las variables de prueba se usan para las pruebas cualitativas.</span><span class="sxs-lookup"><span data-stu-id="32e99-278">Measurement values are used for quantitative tests, and test variables are used for qualitative tests.</span></span>
<ul>
<li><span data-ttu-id="32e99-279">Una prueba cuantitativa tiene un tipo de prueba de <strong>Entero</strong> o <strong>Fracción</strong> y una unidad de medida designada.</span><span class="sxs-lookup"><span data-stu-id="32e99-279">A quantitative test has a test type of <strong>Integer</strong> or <strong>Fraction</strong>, and also has a designated unit of measure.</span></span> <span data-ttu-id="32e99-280">Las especificaciones de calidad y los resultados de la prueba se expresan como números.</span><span class="sxs-lookup"><span data-stu-id="32e99-280">Quality specifications and test results are expressed as numbers.</span></span></li>
<li><span data-ttu-id="32e99-281">Una prueba cualitativa tiene una prueba de tipo <strong>Opción</strong>.</span><span class="sxs-lookup"><span data-stu-id="32e99-281">A qualitative test has a test type of <strong>Option</strong>.</span></span> <span data-ttu-id="32e99-282">Las pruebas cualitativas requieren información adicional sobre la variable de prueba que se está midiendo y sus opciones enumeradas.</span><span class="sxs-lookup"><span data-stu-id="32e99-282">Qualitative tests require additional information about the test variable that is being measured and its enumerated options.</span></span> <span data-ttu-id="32e99-283">Las especificaciones de calidad y los resultados de la prueba se expresan en función de un resultado.</span><span class="sxs-lookup"><span data-stu-id="32e99-283">Quality specifications and test results are expressed according to an outcome.</span></span></li>
</ul></td>
<td><span data-ttu-id="32e99-284">Una empresa de fabricación realiza dos pruebas en el material adquirido: una prueba cuantitativa sobre la calidad del material y una prueba cualitativa sobre los daños de embalaje.</span><span class="sxs-lookup"><span data-stu-id="32e99-284">A manufacturing company performs two tests on purchased material: a quantitative test about material quality and a qualitative test about packaging damage.</span></span> <span data-ttu-id="32e99-285">La empresa define información adicional sobre la prueba cualitativa para identificar la variable de prueba (embalaje dañado) y sus resultados.</span><span class="sxs-lookup"><span data-stu-id="32e99-285">The company defines additional information about the qualitative test to identify the test variable (damaged packaging) and its outcomes.</span></span> <span data-ttu-id="32e99-286">La empresa usa la página <strong>Grupos de prueba</strong> para asignar las dos pruebas a un grupo de pruebas y para especificar la información específica de la prueba.</span><span class="sxs-lookup"><span data-stu-id="32e99-286">The company uses the <strong>Test groups</strong> page to assign the two tests to a test group and to specify the test-specific information.</span></span> <span data-ttu-id="32e99-287">El grupo de pruebas se asigna a un pedido de calidad, de modo que la empresa puede informar de los resultados de la prueba para las dos pruebas.</span><span class="sxs-lookup"><span data-stu-id="32e99-287">The test group is assigned to a quality order, so that the company can report test results for the two tests.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="32e99-288">Grupos de prueba</span><span class="sxs-lookup"><span data-stu-id="32e99-288">Test groups</span></span></td>
<td><span data-ttu-id="32e99-289">Use esta página para establecer, editar y ver los grupos de prueba y las pruebas individuales asignadas a un grupo de prueba.</span><span class="sxs-lookup"><span data-stu-id="32e99-289">Use this page to set up, edit, and view test groups and the individual tests that are assigned to a test group.</span></span> <span data-ttu-id="32e99-290">En el panel superior se muestran los grupos de pruebas y en el inferior se muestran las pruebas asignadas a un grupo de pruebas seleccionado.</span><span class="sxs-lookup"><span data-stu-id="32e99-290">The upper pane displays test groups, and the lower pane displays the tests that are assigned to a selected test group.</span></span> <span data-ttu-id="32e99-291">A un grupo de pruebas se le asignan varias directivas, por ejemplo, un plan de muestreo, un nivel de calidad aceptable (AQL) y el requisito de la prueba destructiva.</span><span class="sxs-lookup"><span data-stu-id="32e99-291">You assign several policies to a test group, such as a sampling plan, an AQL, and the requirement for destructive testing.</span></span> <span data-ttu-id="32e99-292">Al asignar una prueba individual a un grupo de prueba, define información adicional, como la secuencia, los documentos, y las fechas de validez.</span><span class="sxs-lookup"><span data-stu-id="32e99-292">When you assign an individual test to a test group, you define additional information, such as the sequence, documents, and validity dates.</span></span> <span data-ttu-id="32e99-293">Para una prueba cuantitativa, la información que define también incluye los valores de medida aceptables.</span><span class="sxs-lookup"><span data-stu-id="32e99-293">For a quantitative test, the information that you define also includes the acceptable measurement values.</span></span> <span data-ttu-id="32e99-294">Para una prueba cualitativa, la información incluye la variable de prueba y el resultado predeterminado.</span><span class="sxs-lookup"><span data-stu-id="32e99-294">For a qualitative test, the information includes the test variable and default outcome.</span></span> <span data-ttu-id="32e99-295">El grupo de prueba asignado a un pedido de calidad define el conjunto predeterminado de pruebas que se tienen que realizar sobre el artículo especificado.</span><span class="sxs-lookup"><span data-stu-id="32e99-295">The test group that is assigned to a quality order defines the default set of tests that must be performed on the specified item.</span></span> <span data-ttu-id="32e99-296">No obstante, puede agregar, cambiar o eliminar las pruebas en el pedido de calidad.</span><span class="sxs-lookup"><span data-stu-id="32e99-296">However, you can add, delete, or change tests on the quality order.</span></span> <span data-ttu-id="32e99-297">Los resultados de prueba se notifican para cada prueba de un pedido de calidad.</span><span class="sxs-lookup"><span data-stu-id="32e99-297">Test results are reported for each test on a quality order.</span></span></td>
<td><span data-ttu-id="32e99-298">Un fabricante define un grupo de pruebas para cada variación de sus criterios de calidad.</span><span class="sxs-lookup"><span data-stu-id="32e99-298">A manufacturing company defines a test group for each variation of its quality guidelines.</span></span> <span data-ttu-id="32e99-299">Los distintos grupos de pruebas reflejan las diferencias de los planes de muestreo, los conjuntos de pruebas que se deben realizar en conjunto, el AQL y otros factores.</span><span class="sxs-lookup"><span data-stu-id="32e99-299">The various test groups reflect differences in the sampling plans, the sets of tests that must be performed together, the AQL, and other factors.</span></span> <span data-ttu-id="32e99-300">Para las pruebas cuantitativas también hay diferencias en los valores de medida aceptables.</span><span class="sxs-lookup"><span data-stu-id="32e99-300">For quantitative tests, there are also differences in the acceptable measurement values.</span></span> <span data-ttu-id="32e99-301">Para aplicar sus criterios de calidad, la empresa asigna un grupo de prueba a cada regla con el fin de generar automáticamente pedidos de calidad en la página <strong>Asociaciones de calidad</strong> y también asigna un grupo de prueba a los pedidos de calidad creados manualmente.</span><span class="sxs-lookup"><span data-stu-id="32e99-301">To enforce its quality guidelines, the company assigns a test group to each rule for automatically generating quality orders on the <strong>Quality associations</strong> page, and also assigns a test group to quality orders that are manually created.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="32e99-302">Grupos de calidad de artículos</span><span class="sxs-lookup"><span data-stu-id="32e99-302">Item quality groups</span></span></td>
<td><span data-ttu-id="32e99-303">Use esta página para configurar, editar y ver los artículos asignados a un grupo de calidad o a los grupos de calidad asignados a un artículo.</span><span class="sxs-lookup"><span data-stu-id="32e99-303">Use this page to set up, edit, and view the items that are assigned to a quality group or the quality groups that are assigned to an item.</span></span> <span data-ttu-id="32e99-304">Un grupo de calidad representa requisitos de prueba comunes para los artículos.</span><span class="sxs-lookup"><span data-stu-id="32e99-304">A quality group represents common testing requirements for items.</span></span> <span data-ttu-id="32e99-305">Cuando haya definido los requisitos de prueba en la página <strong>Grupos de prueba</strong>, puede definir las reglas para generar automáticamente pedidos de calidad.</span><span class="sxs-lookup"><span data-stu-id="32e99-305">After you define the test requirements on the <strong>Test groups</strong> page, you can define the rules for automatically generating quality orders.</span></span> <span data-ttu-id="32e99-306">Para simplificar el proceso, no se definen reglas para artículos individuales.</span><span class="sxs-lookup"><span data-stu-id="32e99-306">To simplify the process, you don&#39;t define rules for individual items.</span></span> <span data-ttu-id="32e99-307">En su lugar, puede definir las reglas para un grupo de calidad mediante la página <strong>Asociaciones de calidad</strong>.</span><span class="sxs-lookup"><span data-stu-id="32e99-307">Instead, you define rules for a quality group, by using the <strong>Quality associations</strong> page.</span></span> <span data-ttu-id="32e99-308">También puede usar la página <strong>Grupos de calidad de artículos</strong> para un grupo de calidad seleccionado para asignar artículos relevantes a dicho grupo.</span><span class="sxs-lookup"><span data-stu-id="32e99-308">You can also use the <strong>Item quality groups</strong> page for a selected quality group to assign relevant items to that group.</span></span> <span data-ttu-id="32e99-309">También puede usar la página <strong>Grupos de calidad de artículos</strong> para un artículo seleccionado para asignar grupos de calidad relevantes a dicho artículo.</span><span class="sxs-lookup"><span data-stu-id="32e99-309">You can also use the <strong>Item quality groups</strong> page for a selected item to assign relevant quality groups to that item.</span></span></td>
<td><span data-ttu-id="32e99-310">Un fabricante compra varias materias primas con los mismos requisitos de prueba para una inspección entrante.</span><span class="sxs-lookup"><span data-stu-id="32e99-310">A manufacturing company purchases various raw materials that have the same testing requirements for incoming inspection.</span></span> <span data-ttu-id="32e99-311">La empresa define un grupo de calidad y, después, le asigna números de artículo asociados con las materias primas para ese grupo.</span><span class="sxs-lookup"><span data-stu-id="32e99-311">The company defines a quality group and then assigns the item numbers that are associated with the raw materials to that group.</span></span> <span data-ttu-id="32e99-312">Más adelante, la empresa compra un nuevo tipo de materia prima con los mismos requisitos de prueba.</span><span class="sxs-lookup"><span data-stu-id="32e99-312">Later, the company purchases a new type of raw material that has the same testing requirements.</span></span> <span data-ttu-id="32e99-313">En lugar de configurar requisitos de prueba nuevos para el nuevo material, la empresa añade el número de artículo del nuevo material al grupo de calidad existente.</span><span class="sxs-lookup"><span data-stu-id="32e99-313">Instead of setting up new testing requirements for the new material, the company adds the item number for the new material to the existing quality group.</span></span> <span data-ttu-id="32e99-314">El mismo fabricante también produce artículos con los mismos requisitos de prueba y envía artículos con los mismos requisitos para las pruebas anteriores al envío.</span><span class="sxs-lookup"><span data-stu-id="32e99-314">The same manufacturing company also produces items that have the same production testing requirements and ships items that have the same requirement for pre-shipment testing.</span></span> <span data-ttu-id="32e99-315">La empresa define dos grupos de calidad adicionales y, después, asigna números de artículo pertinentes a cada grupo.</span><span class="sxs-lookup"><span data-stu-id="32e99-315">The company defines two additional quality groups and then assigns the relevant item numbers to each group.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="32e99-316">Variables de prueba</span><span class="sxs-lookup"><span data-stu-id="32e99-316">Test variables</span></span></td>
<td><span data-ttu-id="32e99-317">Use esta página para definir y ver las variables asociadas a una prueba cualitativa.</span><span class="sxs-lookup"><span data-stu-id="32e99-317">Use this page to define and view the variables that are associated with a qualitative test.</span></span> <span data-ttu-id="32e99-318">Para cada variable, define los resultados enumerados que representan las posibles opciones.</span><span class="sxs-lookup"><span data-stu-id="32e99-318">For each variable, you define enumerated outcomes that represent the possible options.</span></span> <span data-ttu-id="32e99-319">Puede definir pruebas en la página <strong>Pruebas</strong>.</span><span class="sxs-lookup"><span data-stu-id="32e99-319">You define tests on the <strong>Tests</strong> page.</span></span> <span data-ttu-id="32e99-320">Para las pruebas cualitativas, debe definir el tipo de prueba en <strong>Opción</strong>.</span><span class="sxs-lookup"><span data-stu-id="32e99-320">For qualitative tests, you must set the test type to <strong>Option</strong>.</span></span> <span data-ttu-id="32e99-321">Use la página <strong>Grupos de prueba</strong> para asignar una variable de prueba a una prueba individual.</span><span class="sxs-lookup"><span data-stu-id="32e99-321">Use the <strong>Test groups</strong> page to assign a test variable to an individual test.</span></span></td>
<td><span data-ttu-id="32e99-322">Una fábrica de galletas utiliza una prueba de inspección para el producto terminado.</span><span class="sxs-lookup"><span data-stu-id="32e99-322">A manufacturing company that produces cookies uses an inspection test for the finished product.</span></span> <span data-ttu-id="32e99-323">Esta prueba de inspección tiene varias variables.</span><span class="sxs-lookup"><span data-stu-id="32e99-323">This inspection test has several variables.</span></span> <span data-ttu-id="32e99-324">Una variable es el gusto y los posibles resultados para esta variable son bueno y malo.</span><span class="sxs-lookup"><span data-stu-id="32e99-324">One variable is taste, and the possible outcomes for this variable are good and bad.</span></span> <span data-ttu-id="32e99-325">Una segunda variable es el color y los posibles resultados son demasiado oscuro, demasiado claro y correcto.</span><span class="sxs-lookup"><span data-stu-id="32e99-325">A second variable is color, and the possible outcomes are too dark, too light, and correct.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="32e99-326">Resultados de la variable de prueba</span><span class="sxs-lookup"><span data-stu-id="32e99-326">Test variable outcomes</span></span></td>
<td><span data-ttu-id="32e99-327">Utilice esta página para configurar, editar y visualizar los resultados posibles de una variable de prueba asociada a una prueba cualitativa.</span><span class="sxs-lookup"><span data-stu-id="32e99-327">Use this page to set up, edit, and to view the possible test results for a test variable that is associated with a qualitative test.</span></span> <span data-ttu-id="32e99-328">Para cada resultado, asigne un estado de <strong>correcto</strong> o <strong>erróneo</strong>.</span><span class="sxs-lookup"><span data-stu-id="32e99-328">For each outcome, you assign a <strong>pass</strong> or <strong>fail</strong> status.</span></span> <span data-ttu-id="32e99-329">Deberá definir una variable y sus resultados para cada prueba cualitativa definida en la página <strong>Pruebas</strong>.</span><span class="sxs-lookup"><span data-stu-id="32e99-329">You must define a variable and its outcomes for each qualitative test that is defined on the <strong>Tests</strong> page.</span></span> <span data-ttu-id="32e99-330">(Para las pruebas cualitativas, el tipo de prueba se establece en <strong>Opción</strong> en la página <strong>Pruebas</strong>). Utilice la página <strong>Grupos de prueba</strong> para asignar una variable de prueba y el resultado predeterminado a una prueba cualitativa individual.</span><span class="sxs-lookup"><span data-stu-id="32e99-330">(For qualitative tests, the test type is set to <strong>Option</strong> on the <strong>Tests</strong> page.) Use the <strong>Test groups</strong> page to assign a test variable and the default outcome to an individual qualitative test.</span></span></td>
<td><span data-ttu-id="32e99-331">Una fábrica de galletas utiliza una prueba de inspección para el producto terminado.</span><span class="sxs-lookup"><span data-stu-id="32e99-331">A manufacturing company that produces cookies uses an inspection test for the finished product.</span></span> <span data-ttu-id="32e99-332">Esta prueba de inspección tiene varias variables.</span><span class="sxs-lookup"><span data-stu-id="32e99-332">This inspection test has of several variables.</span></span> <span data-ttu-id="32e99-333">Una variable es el gusto y los posibles resultados para esta variable son bueno y malo.</span><span class="sxs-lookup"><span data-stu-id="32e99-333">One variable is taste, and the possible outcomes for this variable are good and bad.</span></span> <span data-ttu-id="32e99-334">Una segunda variable es el color y los posibles resultados son demasiado oscuro, demasiado claro y correcto.</span><span class="sxs-lookup"><span data-stu-id="32e99-334">A second variable is color, and the possible outcomes are too dark, too light, and correct.</span></span> <span data-ttu-id="32e99-335">Cada resultado tiene asignado un estado de <strong>correcto</strong> o <strong>erróneo</strong>.</span><span class="sxs-lookup"><span data-stu-id="32e99-335">A status of <strong>pass</strong> or <strong>fail</strong> is assigned to each outcome.</span></span> <span data-ttu-id="32e99-336">Durante la prueba de inspección de cada variable, el inspector notifica el resultado de la prueba seleccionando uno de los resultados.</span><span class="sxs-lookup"><span data-stu-id="32e99-336">During the inspection test for each variable, the inspector reports the test result by selecting one of the outcomes.</span></span></td>
</tr>
</tbody>
</table>



<a name="additional-resources"></a><span data-ttu-id="32e99-337">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="32e99-337">Additional resources</span></span>
--------

[<span data-ttu-id="32e99-338">Procesos de administración de calidad</span><span class="sxs-lookup"><span data-stu-id="32e99-338">Quality management processes</span></span>](quality-management-processes.md)

[<span data-ttu-id="32e99-339">Activación de la gestión de disconformidades</span><span class="sxs-lookup"><span data-stu-id="32e99-339">Enabling nonconformance management</span></span>](enable-nonconformance-management.md)
