---
title: Visión general de la gestión de la calidad
description: Este tema describe cómo puede usar la gestión de calidad en Dynamics 365 Supply Chain Management para ayudar a mejorar la calidad del producto dentro de la cadena de suministro.
author: perlynne
manager: tfehr
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventTestAssociationTable, InventTestGroup, InventTestItemQualityGroup, InventTestTable, InventTestVariable, InventTestVariableOutcome
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 65858838b0fbb245a9330fab4e3b65b36a9eb944
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5219374"
---
# <a name="quality-management-overview"></a><span data-ttu-id="5da21-103">Visión general de la gestión de la calidad</span><span class="sxs-lookup"><span data-stu-id="5da21-103">Quality management overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5da21-104">Este tema describe cómo puede usar la gestión de calidad en Dynamics 365 Supply Chain Management para ayudar a mejorar la calidad del producto dentro de la cadena de suministro.</span><span class="sxs-lookup"><span data-stu-id="5da21-104">This topic describes how you can use quality management in Dynamics 365 Supply Chain Management to help improve product quality within your supply chain.</span></span>

<span data-ttu-id="5da21-105">La gestión de calidad puede ayudarle a gestionar los plazos de entrega cuando maneja productos de disconformidad, independientemente de su punto de origen.</span><span class="sxs-lookup"><span data-stu-id="5da21-105">Quality management can help you manage turnaround times when you handle nonconforming products, regardless of their point of origin.</span></span> <span data-ttu-id="5da21-106">Dado que los tipos de diagnóstico están vinculados a la corrección de los informes, Supply Chain Management puede programar las tareas para corregir los problemas y evitar que se repitan.</span><span class="sxs-lookup"><span data-stu-id="5da21-106">Because diagnostic types are linked to correction reporting, Supply Chain Management can schedule tasks to correct problems and prevent them from recurring.</span></span>

<span data-ttu-id="5da21-107">Además de la funcionalidad para gestionar la no conformidad, la gestión de calidad incluye la funcionalidad de realizar un seguimiento de las incidencias por tipo de problema (incluso problemas internos) y para identificar soluciones a corto plazo o a largo plazo.</span><span class="sxs-lookup"><span data-stu-id="5da21-107">In addition to functionality for managing nonconformance, quality management includes functionality for tracking issues by problem type (even internal problems), and for identifying solutions as short-term or long-term.</span></span> <span data-ttu-id="5da21-108">Las estadísticas acerca de los indicadores clave de rendimiento (KPI) proporcionan información sobre el historial de problemas de disconformidad anteriores y las soluciones utilizadas para corregirlos.</span><span class="sxs-lookup"><span data-stu-id="5da21-108">Statistics about key performance indicators (KPIs) provide insight into the history of previous nonconformance issues and the solutions that were used to correct them.</span></span> <span data-ttu-id="5da21-109">Puede usar los datos históricos para revisar la eficacia de las medidas de calidad anteriores y determinar las medidas adecuadas que se deben usar en el futuro.</span><span class="sxs-lookup"><span data-stu-id="5da21-109">You can use historical data to review the effectiveness of previous quality measures and determine appropriate measures to use in the future.</span></span>

<span data-ttu-id="5da21-110">Al configurar una asociación de calidad, Supply Chain Management puede generar pedidos de calidad para varios procesos empresariales, eventos y condiciones.</span><span class="sxs-lookup"><span data-stu-id="5da21-110">When you set up a quality association, Supply Chain Management can generate quality orders for various business processes, events, and conditions.</span></span> <span data-ttu-id="5da21-111">La asociación de calidad puede cubrir un artículo concreto, un determinado grupo de éstos o todos los artículos.</span><span class="sxs-lookup"><span data-stu-id="5da21-111">The quality association can cover a specific item, a specific group of items, or all items.</span></span>

## <a name="examples-of-the-use-of-quality-management"></a><span data-ttu-id="5da21-112">Ejemplos del uso de la gestión de calidad</span><span class="sxs-lookup"><span data-stu-id="5da21-112">Examples of the use of quality management</span></span>
<span data-ttu-id="5da21-113">La gestión de calidad es flexible y puede ejecutarse de distintas maneras para satisfacer los requisitos de niveles específicos de operaciones de la cadena de suministro.</span><span class="sxs-lookup"><span data-stu-id="5da21-113">Quality management is flexible and can be implemented in various ways to meet the requirements of specific levels of supply chain operations.</span></span> <span data-ttu-id="5da21-114">En los ejemplos siguientes se muestran usos posibles de estas características:</span><span class="sxs-lookup"><span data-stu-id="5da21-114">The following examples illustrate possible uses of these features:</span></span>

-   <span data-ttu-id="5da21-115">Inicie automáticamente un proceso de control de calidad en función de los criterios predefinidos (sobre el registro del almacén de un pedido de compra para un proveedor específico).</span><span class="sxs-lookup"><span data-stu-id="5da21-115">Automatically start a quality control process, based on predefined criteria (upon warehouse registration of a purchase order from a specific vendor).</span></span>
-   <span data-ttu-id="5da21-116">Bloquear el inventario durante la inspección para evitar que el inventario no aprobado se use (bloqueo completo de las cantidades de pedido de compra).</span><span class="sxs-lookup"><span data-stu-id="5da21-116">Block inventory during inspection to prevent non-approved inventory from being used (full blocking of purchase order quantities).</span></span>
-   <span data-ttu-id="5da21-117">Use el muestreo del artículo como parte de una asociación de calidad para definir la cantidad de inventario físico actual que debe inspeccionarse.</span><span class="sxs-lookup"><span data-stu-id="5da21-117">Use item sampling as part of a quality association to define the amount of current physical inventory that must be inspected.</span></span> <span data-ttu-id="5da21-118">El muestreo puede basarse en cantidades fijas o en un porcentaje, o en una matrícula completa.</span><span class="sxs-lookup"><span data-stu-id="5da21-118">Sampling can be based on fixed quantities, a percentage, or full license plate.</span></span>

> [!NOTE]
> <span data-ttu-id="5da21-119">La característica _Administración de la calidad para procesos de almacén_ amplía las capacidades de la gestión de calidad.</span><span class="sxs-lookup"><span data-stu-id="5da21-119">The _Quality management for warehouse processes_ feature extends the capabilities of quality management.</span></span> <span data-ttu-id="5da21-120">Si está utilizando esta función, vea [Gestión de calidad para procesos de almacén](quality-management-for-warehouses-processes.md) para ver ejemplos de cómo funciona la gestión de calidad cuando está habilitada.</span><span class="sxs-lookup"><span data-stu-id="5da21-120">If you are using this feature, then see [Quality management for warehouse processes](quality-management-for-warehouses-processes.md) for examples of how quality management works when it's enabled.</span></span>

-   <span data-ttu-id="5da21-121">Crear pedidos de calidad para recepciones parciales.</span><span class="sxs-lookup"><span data-stu-id="5da21-121">Create quality orders for partial receipts.</span></span> <span data-ttu-id="5da21-122">Para crear un pedido de calidad basado en la cantidad que se recibe físicamente con un pedido, debe seleccionar la casilla de verificación **Por cantidad actualizada** en el formulario **Muestreo de artículos** .</span><span class="sxs-lookup"><span data-stu-id="5da21-122">To create a quality order that is based on the quantity that is physically received with an order, you must select the **Per updated quantity** check box on the **Item sampling** form.</span></span>
-   <span data-ttu-id="5da21-123">Permite crear tipos de prueba que incluyen mínimo, máximo y valores de prueba de destino, y realizar pruebas cualitativas en contraposición a cuantitativas que tengan resultados de validación predefinidos.</span><span class="sxs-lookup"><span data-stu-id="5da21-123">Create test types that include minimum, maximum, and target test values, and perform qualitative-versus-quantitative testing that has predefined validation results.</span></span>
-   <span data-ttu-id="5da21-124">Especifique un nivel de calidad aceptable (AQL) para controlar las tolerancias de medida de calidad.</span><span class="sxs-lookup"><span data-stu-id="5da21-124">Specify an acceptable quality level (AQL) to control quality measure tolerances.</span></span>
-   <span data-ttu-id="5da21-125">Especifique los recursos que una operación de inspección requiere, por ejemplo instrumentos de prueba y un área de prueba.</span><span class="sxs-lookup"><span data-stu-id="5da21-125">Specify the resources that an inspection operation requires, such as a test area and test instruments.</span></span>

## <a name="working-with-quality-associations"></a><span data-ttu-id="5da21-126">Trabajar con asociaciones de calidad</span><span class="sxs-lookup"><span data-stu-id="5da21-126">Working with quality associations</span></span>
<span data-ttu-id="5da21-127">El proceso empresarial que utiliza una asociación de calidad puede estar relacionado con varios documentos de origen, como pedidos de compra, pedidos de ventas o pedidos de producción.</span><span class="sxs-lookup"><span data-stu-id="5da21-127">The business process that uses a quality association can be related to various source documents, such as purchase orders, sales orders, or production orders.</span></span>

<span data-ttu-id="5da21-128">Cada registro de asociación de calidad define el conjunto de pruebas, el nivel de calidad aceptable y el plan de muestreo que se aplica a los pedidos de calidad generados.</span><span class="sxs-lookup"><span data-stu-id="5da21-128">Each quality association record defines the set of tests, the AQL, and the sampling plan that applies to the quality orders that are generated.</span></span> <span data-ttu-id="5da21-129">Debe definir un registro de asociación de calidad para cada variación de un proceso empresarial.</span><span class="sxs-lookup"><span data-stu-id="5da21-129">You must define a quality association record for each variation in a business process.</span></span> <span data-ttu-id="5da21-130">Por ejemplo, puede configurar una asociación de calidad que genere un pedido de calidad cuando se actualice una recepción de producto de pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="5da21-130">For example, you can set up a quality association that generates a quality order when a purchase order product receipt is updated.</span></span> <span data-ttu-id="5da21-131">En función de la configuración del plan de ejecución, el propio proceso de activación puede bloquearse mientras que haya un pedido de calidad abierto o los siguientes procesos, por ejemplo, una factura de pedido de compra, se pueden bloquear.</span><span class="sxs-lookup"><span data-stu-id="5da21-131">Depending on the setup of the execution plan, the triggering process itself can be blocked while there is an open quality order, or the next processes, such as purchase order invoicing, can be blocked.</span></span>

<span data-ttu-id="5da21-132">**Nota:** mientras haya pedidos de calidad abiertos, las cantidades de inventario se bloquean automáticamente para evitar su emisión.</span><span class="sxs-lookup"><span data-stu-id="5da21-132">**Note:** While there are open quality orders, inventory quantities are automatically blocked from being issued.</span></span> <span data-ttu-id="5da21-133">En función del ajuste **Bloqueo completo** de la página **Muestreos de artículos**, la cantidad es la cantidad en el pedido de calidad o la cantidad en la línea del documento de origen.</span><span class="sxs-lookup"><span data-stu-id="5da21-133">Depending on the **Full blocking** setting on the **Item samplings** page, the quantity is either the quantity on the quality order or the quantity on the source document line.</span></span>

<span data-ttu-id="5da21-134">Para un determinado proceso empresarial, el registro de la asociación de calidad identifica el evento y las condiciones para las que se genera un pedido de calidad.</span><span class="sxs-lookup"><span data-stu-id="5da21-134">For a given business process, the quality association record identifies the event and the conditions that a quality order is generated for.</span></span> <span data-ttu-id="5da21-135">Las condiciones pueden especificarse para un sitio o para una entidad jurídica.</span><span class="sxs-lookup"><span data-stu-id="5da21-135">The conditions can be specific to either a site or a legal entity.</span></span> <span data-ttu-id="5da21-136">Un pedido de calidad que requiera pruebas destructivas solo se puede generar si hay un inventario disponible para el evento.</span><span class="sxs-lookup"><span data-stu-id="5da21-136">A quality order that involves destructive tests can be generated only when on-hand inventory exists for the event.</span></span>

<span data-ttu-id="5da21-137">En los siguientes ejemplos se muestra cómo se define un registro de asociación de calidad para las variantes de cada proceso empresarial.</span><span class="sxs-lookup"><span data-stu-id="5da21-137">The following examples illustrate how a quality association record is defined for the variations in each business process.</span></span> <span data-ttu-id="5da21-138">Para cada ejemplo, la siguiente tabla resume los eventos y las condiciones definidos por un registro de asociación de calidad.</span><span class="sxs-lookup"><span data-stu-id="5da21-138">For each example, the following table summarizes the events and conditions that are defined by a quality association record.</span></span>

<table>
<tbody>
<tr>
<th><span data-ttu-id="5da21-139">Tipo de referencia</span><span class="sxs-lookup"><span data-stu-id="5da21-139">Reference type</span></span></th>
<th><span data-ttu-id="5da21-140">Tipo de evento</span><span class="sxs-lookup"><span data-stu-id="5da21-140">Event type</span></span></th>
<th><span data-ttu-id="5da21-141">Ejecución</span><span class="sxs-lookup"><span data-stu-id="5da21-141">Execution</span></span></th>
<th><span data-ttu-id="5da21-142">Bloqueo de eventos</span><span class="sxs-lookup"><span data-stu-id="5da21-142">Event blocking</span></span></th>
<th><span data-ttu-id="5da21-143">Referencia del documento</span><span class="sxs-lookup"><span data-stu-id="5da21-143">Document reference</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="5da21-144">Inventario</span><span class="sxs-lookup"><span data-stu-id="5da21-144">Inventory</span></span></td>
<td><span data-ttu-id="5da21-145">No aplicable</span><span class="sxs-lookup"><span data-stu-id="5da21-145">Not applicable</span></span></td>
<td><span data-ttu-id="5da21-146">No aplicable</span><span class="sxs-lookup"><span data-stu-id="5da21-146">Not applicable</span></span></td>
<td><span data-ttu-id="5da21-147">Ninguna</span><span class="sxs-lookup"><span data-stu-id="5da21-147">None</span></span></td>
<td><span data-ttu-id="5da21-148">Todas</span><span class="sxs-lookup"><span data-stu-id="5da21-148">All</span></span></td>
</tr>
<tr>
<td rowspan="7"><span data-ttu-id="5da21-149">Ventas</span><span class="sxs-lookup"><span data-stu-id="5da21-149">Sales</span></span></td>
<td rowspan="4"><span data-ttu-id="5da21-150">Proceso de picking programado</span><span class="sxs-lookup"><span data-stu-id="5da21-150">Picking process is scheduled</span></span></td>
<td rowspan="4"><span data-ttu-id="5da21-151">Anterior</span><span class="sxs-lookup"><span data-stu-id="5da21-151">Before</span></span></td>
<td><span data-ttu-id="5da21-152">Ninguna</span><span class="sxs-lookup"><span data-stu-id="5da21-152">None</span></span></td>
<td rowspan="22"><span data-ttu-id="5da21-153">Solo Id. específico, Grupo o Todo</span><span class="sxs-lookup"><span data-stu-id="5da21-153">Specific ID, Group, or All only</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5da21-154">Proceso de picking</span><span class="sxs-lookup"><span data-stu-id="5da21-154">Picking process</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5da21-155">Albarán</span><span class="sxs-lookup"><span data-stu-id="5da21-155">Packing slip</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5da21-156">Factura</span><span class="sxs-lookup"><span data-stu-id="5da21-156">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="5da21-157">Albarán</span><span class="sxs-lookup"><span data-stu-id="5da21-157">Packing slip</span></span></td>
<td rowspan="3"><span data-ttu-id="5da21-158">Anterior</span><span class="sxs-lookup"><span data-stu-id="5da21-158">Before</span></span></td>
<td><span data-ttu-id="5da21-159">Ninguna</span><span class="sxs-lookup"><span data-stu-id="5da21-159">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5da21-160">Albarán</span><span class="sxs-lookup"><span data-stu-id="5da21-160">Packing slip</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5da21-161">Factura</span><span class="sxs-lookup"><span data-stu-id="5da21-161">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="15"><span data-ttu-id="5da21-162">Compra</span><span class="sxs-lookup"><span data-stu-id="5da21-162">Purchase</span></span></td>
<td rowspan="7"><span data-ttu-id="5da21-163">Lista de recepciones</span><span class="sxs-lookup"><span data-stu-id="5da21-163">Receipt list</span></span></td>
<td rowspan="4"><span data-ttu-id="5da21-164">Anterior</span><span class="sxs-lookup"><span data-stu-id="5da21-164">Before</span></span></td>
<td><span data-ttu-id="5da21-165">Ninguna</span><span class="sxs-lookup"><span data-stu-id="5da21-165">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5da21-166">Lista de recepciones</span><span class="sxs-lookup"><span data-stu-id="5da21-166">Receipt list</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5da21-167">Recepción de producto</span><span class="sxs-lookup"><span data-stu-id="5da21-167">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5da21-168">Factura</span><span class="sxs-lookup"><span data-stu-id="5da21-168">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="5da21-169">Posterior</span><span class="sxs-lookup"><span data-stu-id="5da21-169">After</span></span></td>
<td><span data-ttu-id="5da21-170">Ninguna</span><span class="sxs-lookup"><span data-stu-id="5da21-170">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5da21-171">Recepción de producto</span><span class="sxs-lookup"><span data-stu-id="5da21-171">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5da21-172">Factura</span><span class="sxs-lookup"><span data-stu-id="5da21-172">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="5da21-173">Registro</span><span class="sxs-lookup"><span data-stu-id="5da21-173">Registration</span></span></td>
<td rowspan="3"><span data-ttu-id="5da21-174">No aplicable</span><span class="sxs-lookup"><span data-stu-id="5da21-174">Not applicable</span></span></td>
<td><span data-ttu-id="5da21-175">Ninguna</span><span class="sxs-lookup"><span data-stu-id="5da21-175">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5da21-176">Recepción de producto</span><span class="sxs-lookup"><span data-stu-id="5da21-176">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5da21-177">Factura</span><span class="sxs-lookup"><span data-stu-id="5da21-177">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="5"><span data-ttu-id="5da21-178">Recepción de producto</span><span class="sxs-lookup"><span data-stu-id="5da21-178">Product receipt</span></span></td>
<td rowspan="3"><span data-ttu-id="5da21-179">Anterior</span><span class="sxs-lookup"><span data-stu-id="5da21-179">Before</span></span></td>
<td><span data-ttu-id="5da21-180">Ninguna</span><span class="sxs-lookup"><span data-stu-id="5da21-180">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5da21-181">Recepción de producto</span><span class="sxs-lookup"><span data-stu-id="5da21-181">Product receipt</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5da21-182">Factura</span><span class="sxs-lookup"><span data-stu-id="5da21-182">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="2"><span data-ttu-id="5da21-183">Posterior</span><span class="sxs-lookup"><span data-stu-id="5da21-183">After</span></span></td>
<td><span data-ttu-id="5da21-184">Ninguna</span><span class="sxs-lookup"><span data-stu-id="5da21-184">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5da21-185">Factura</span><span class="sxs-lookup"><span data-stu-id="5da21-185">Invoice</span></span></td>
</tr>
<tr>
<td rowspan="8"><span data-ttu-id="5da21-186">Producción</span><span class="sxs-lookup"><span data-stu-id="5da21-186">Production</span></span></td>
<td rowspan="3"><span data-ttu-id="5da21-187">Registro</span><span class="sxs-lookup"><span data-stu-id="5da21-187">Registration</span></span></td>
<td rowspan="3"><span data-ttu-id="5da21-188">No aplicable</span><span class="sxs-lookup"><span data-stu-id="5da21-188">Not applicable</span></span></td>
<td><span data-ttu-id="5da21-189">Ninguna</span><span class="sxs-lookup"><span data-stu-id="5da21-189">None</span></span></td>
<td rowspan="12"><span data-ttu-id="5da21-190">Todas</span><span class="sxs-lookup"><span data-stu-id="5da21-190">All</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5da21-191">Notificar como terminado</span><span class="sxs-lookup"><span data-stu-id="5da21-191">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5da21-192">Fin</span><span class="sxs-lookup"><span data-stu-id="5da21-192">End</span></span></td>
</tr>
<tr>
<td rowspan="5"><span data-ttu-id="5da21-193">Notificar como terminado</span><span class="sxs-lookup"><span data-stu-id="5da21-193">Report as finished</span></span></td>
<td rowspan="3"><span data-ttu-id="5da21-194">Anterior</span><span class="sxs-lookup"><span data-stu-id="5da21-194">Before</span></span></td>
<td><span data-ttu-id="5da21-195">Ninguna</span><span class="sxs-lookup"><span data-stu-id="5da21-195">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5da21-196">Notificar como terminado</span><span class="sxs-lookup"><span data-stu-id="5da21-196">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5da21-197">Fin</span><span class="sxs-lookup"><span data-stu-id="5da21-197">End</span></span></td>
</tr>
<tr>
<td rowspan="2"><span data-ttu-id="5da21-198">Posterior</span><span class="sxs-lookup"><span data-stu-id="5da21-198">After</span></span></td>
<td><span data-ttu-id="5da21-199">Ninguna</span><span class="sxs-lookup"><span data-stu-id="5da21-199">None</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5da21-200">Fin</span><span class="sxs-lookup"><span data-stu-id="5da21-200">End</span></span></td>
</tr>
<tr>
<td rowspan="4"><span data-ttu-id="5da21-201">Cuarentena</span><span class="sxs-lookup"><span data-stu-id="5da21-201">Quarantine</span></span></td>
<td rowspan="3"><span data-ttu-id="5da21-202">Notificar como terminado</span><span class="sxs-lookup"><span data-stu-id="5da21-202">Report as finished</span></span></td>
<td rowspan="2"><span data-ttu-id="5da21-203">Anterior</span><span class="sxs-lookup"><span data-stu-id="5da21-203">Before</span></span></td>
<td><span data-ttu-id="5da21-204">Notificar como terminado</span><span class="sxs-lookup"><span data-stu-id="5da21-204">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5da21-205">Fin</span><span class="sxs-lookup"><span data-stu-id="5da21-205">End</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5da21-206">Posterior</span><span class="sxs-lookup"><span data-stu-id="5da21-206">After</span></span></td>
<td><span data-ttu-id="5da21-207">Fin</span><span class="sxs-lookup"><span data-stu-id="5da21-207">End</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5da21-208">Fin</span><span class="sxs-lookup"><span data-stu-id="5da21-208">End</span></span></td>
<td><span data-ttu-id="5da21-209">Anterior</span><span class="sxs-lookup"><span data-stu-id="5da21-209">Before</span></span></td>
<td><span data-ttu-id="5da21-210">Fin</span><span class="sxs-lookup"><span data-stu-id="5da21-210">End</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="5da21-211">Operación de ruta</span><span class="sxs-lookup"><span data-stu-id="5da21-211">Route operation</span></span></td>
<td rowspan="3"><span data-ttu-id="5da21-212">Notificar como terminado</span><span class="sxs-lookup"><span data-stu-id="5da21-212">Report as finished</span></span></td>
<td rowspan="2"><span data-ttu-id="5da21-213">Anterior</span><span class="sxs-lookup"><span data-stu-id="5da21-213">Before</span></span></td>
<td><span data-ttu-id="5da21-214">Ninguna</span><span class="sxs-lookup"><span data-stu-id="5da21-214">None</span></span></td>
<td rowspan="3"><span data-ttu-id="5da21-215">Id. específico, Grupo o Todo, y Recurso específico, Grupo o Todo</span><span class="sxs-lookup"><span data-stu-id="5da21-215">Specific ID, Group, or All, and Resource specific, Group, or All</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5da21-216">Notificar como terminado</span><span class="sxs-lookup"><span data-stu-id="5da21-216">Report as finished</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5da21-217">Posterior</span><span class="sxs-lookup"><span data-stu-id="5da21-217">After</span></span></td>
<td><span data-ttu-id="5da21-218">Ninguna</span><span class="sxs-lookup"><span data-stu-id="5da21-218">None</span></span></td>
</tr>
<tr>
<td rowspan="3"><span data-ttu-id="5da21-219">Producción de coproductos</span><span class="sxs-lookup"><span data-stu-id="5da21-219">Co-product production</span></span></td>
<td><span data-ttu-id="5da21-220">Registro</span><span class="sxs-lookup"><span data-stu-id="5da21-220">Registration</span></span></td>
<td><span data-ttu-id="5da21-221">No aplicable</span><span class="sxs-lookup"><span data-stu-id="5da21-221">Not applicable</span></span></td>
<td rowspan="3"><span data-ttu-id="5da21-222">Ninguna</span><span class="sxs-lookup"><span data-stu-id="5da21-222">None</span></span></td>
<td rowspan="3"><span data-ttu-id="5da21-223">Todas</span><span class="sxs-lookup"><span data-stu-id="5da21-223">All</span></span></td>
</tr>
<tr>
<td rowspan="2"><span data-ttu-id="5da21-224">Notificar como terminado</span><span class="sxs-lookup"><span data-stu-id="5da21-224">Report as finished</span></span></td>
<td><span data-ttu-id="5da21-225">Anterior</span><span class="sxs-lookup"><span data-stu-id="5da21-225">Before</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5da21-226">Posterior</span><span class="sxs-lookup"><span data-stu-id="5da21-226">After</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="5da21-227">La siguiente tabla proporciona más información acerca de cómo se pueden generar los pedidos de calidad para tipos de procesos concretos.</span><span class="sxs-lookup"><span data-stu-id="5da21-227">The following table provides more information about how quality orders can be generated for specific types of processes.</span></span>
<div class="tableSection">

<table>
<tbody>
<tr>
<th><span data-ttu-id="5da21-228">Tipo de proceso</span><span class="sxs-lookup"><span data-stu-id="5da21-228">Type of process</span></span></th>
<th><span data-ttu-id="5da21-229">Cuando los pedidos de calidad se pueden generar automáticamente</span><span class="sxs-lookup"><span data-stu-id="5da21-229">When quality orders can be automatically generated</span></span></th>
<th><span data-ttu-id="5da21-230">Cuando los pedidos de calidad se pueden generar si se requiere una prueba destructiva</span><span class="sxs-lookup"><span data-stu-id="5da21-230">When quality orders can be generated if destructive testing is required</span></span></th>
<th><span data-ttu-id="5da21-231">Información acerca de la condición</span><span class="sxs-lookup"><span data-stu-id="5da21-231">Condition information</span></span></th>
<th><span data-ttu-id="5da21-232">Información acerca de la generación manual</span><span class="sxs-lookup"><span data-stu-id="5da21-232">Manual generation information</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="5da21-233">Pedido de compra</span><span class="sxs-lookup"><span data-stu-id="5da21-233">Purchase order</span></span></td>
<td><span data-ttu-id="5da21-234">Antes o después de que se registre una lista de recepciones o una recepción de producto del material recibido</span><span class="sxs-lookup"><span data-stu-id="5da21-234">Before or after a receipts list or product receipt for the material that is received is posted</span></span></td>
<td><span data-ttu-id="5da21-235">Después del registro de la recepción de producto, ya que el material debe estar disponible para la prueba destructiva</span><span class="sxs-lookup"><span data-stu-id="5da21-235">After the product receipt for the material that is received is posted, because the material must be available for destructive testing</span></span></td>
<td><span data-ttu-id="5da21-236">El requisito de un pedido de calidad puede reflejar un sitio, un artículo o proveedor en concreto, además de una combinación de estas condiciones.</span><span class="sxs-lookup"><span data-stu-id="5da21-236">The requirement for a quality order can reflect a particular site, item, or vendor, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="5da21-237">Un pedido de calidad generado manualmente que hace referencia a un pedido de compra puede usar la información de un registro de asociación de calidad, como el plan de muestreo de la prueba.</span><span class="sxs-lookup"><span data-stu-id="5da21-237">A manually generated quality order that refers to a purchase order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5da21-238">Orden de cuarentena</span><span class="sxs-lookup"><span data-stu-id="5da21-238">Quarantine order</span></span></td>
<td><span data-ttu-id="5da21-239">Antes o después de que se notifique que ha finalizado la orden de cuarentena</span><span class="sxs-lookup"><span data-stu-id="5da21-239">Before or after the quarantine order is reported as finished or ended</span></span></td>
<td><span data-ttu-id="5da21-240">No se pueden generar pedidos de calidad que necesiten pruebas destructivas.</span><span class="sxs-lookup"><span data-stu-id="5da21-240">Quality orders that require destructive tests can&#39;t be generated.</span></span> <span data-ttu-id="5da21-241">Se supone que la funcionalidad de la orden de cuarentena gestiona la disposición del material destruido.</span><span class="sxs-lookup"><span data-stu-id="5da21-241">It&#39;s assumed that the quarantine order functionality handles the disposition of the material that is destroyed.</span></span></td>
<td><span data-ttu-id="5da21-242">El requisito de un pedido de calidad puede reflejar un sitio, un artículo o proveedor en concreto, además de una combinación de estas condiciones.</span><span class="sxs-lookup"><span data-stu-id="5da21-242">The requirement for a quality order can reflect a particular site, item, or vendor, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="5da21-243">Un pedido de calidad generado manualmente que hace referencia a una orden de cuarentena puede usar la información de un registro de asociación de calidad, como el plan de muestreo de la prueba.</span><span class="sxs-lookup"><span data-stu-id="5da21-243">A manually generated quality order that refers to a quarantine order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5da21-244">Pedido de ventas</span><span class="sxs-lookup"><span data-stu-id="5da21-244">Sales order</span></span></td>
<td><span data-ttu-id="5da21-245">Antes de una actualización programada del proceso de selección o del albarán para los artículos que se envían</span><span class="sxs-lookup"><span data-stu-id="5da21-245">Before a scheduled picking process or packing slip update for the items that are being shipped</span></span></td>
<td><span data-ttu-id="5da21-246">En cualquier paso</span><span class="sxs-lookup"><span data-stu-id="5da21-246">At any step</span></span></td>
<td><span data-ttu-id="5da21-247">El requisito de un pedido de calidad puede reflejar un sitio, un artículo o un cliente concreto, además de una combinación de estas condiciones.</span><span class="sxs-lookup"><span data-stu-id="5da21-247">The requirement for a quality order can reflect a particular site, item, or customer, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="5da21-248">Un pedido de calidad generado manualmente que hace referencia a un pedido de ventas puede usar la información de un registro de asociación de calidad, como el plan de muestreo de la prueba.</span><span class="sxs-lookup"><span data-stu-id="5da21-248">A manually generated quality order that refers to a sales order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5da21-249">Pedido de producción</span><span class="sxs-lookup"><span data-stu-id="5da21-249">Production order</span></span></td>
<td><span data-ttu-id="5da21-250">Antes o después de que se registre la cantidad finalizada del pedido de producción</span><span class="sxs-lookup"><span data-stu-id="5da21-250">Before or after the finished quantity for the production order is reported</span></span></td>
<td><span data-ttu-id="5da21-251">Después de que se registre la cantidad finalizada del pedido de producción</span><span class="sxs-lookup"><span data-stu-id="5da21-251">After the finished quantity for the production order is reported</span></span></td>
<td><span data-ttu-id="5da21-252">El requisito de un pedido de calidad puede reflejar un sitio o un artículo concreto, además de una combinación de estas condiciones.</span><span class="sxs-lookup"><span data-stu-id="5da21-252">The requirement for a quality order can reflect a particular site or item, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="5da21-253">Un pedido de calidad generado manualmente que hace referencia a un pedido de producción puede usar la información de un registro de asociación de calidad, como el plan de muestreo de la prueba.</span><span class="sxs-lookup"><span data-stu-id="5da21-253">A manually generated quality order that refers to a production order can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5da21-254">Pedido de producción con una operación de ruta</span><span class="sxs-lookup"><span data-stu-id="5da21-254">Production order that has a route operation</span></span></td>
<td><span data-ttu-id="5da21-255">Antes o después de finalizar el informe de la operación</span><span class="sxs-lookup"><span data-stu-id="5da21-255">Before or after the report is finished for an operation</span></span></td>
<td><span data-ttu-id="5da21-256">Después de finalizar el informe de producción de la última operación</span><span class="sxs-lookup"><span data-stu-id="5da21-256">After the reporting production is finished for the last operation</span></span></td>
<td><span data-ttu-id="5da21-257">El requisito de un pedido de calidad puede reflejar un sitio, un artículo o un recurso de operaciones concreto, además de una combinación de estas condiciones.</span><span class="sxs-lookup"><span data-stu-id="5da21-257">The requirement for a quality order can reflect a particular, site, item, or operations resource, or a combination of these conditions.</span></span></td>
<td><span data-ttu-id="5da21-258">Un pedido de calidad generado manualmente que hace referencia a una operación de ruta puede usar la información de un registro de asociación de calidad, como el plan de muestreo de la prueba.</span><span class="sxs-lookup"><span data-stu-id="5da21-258">A manually generated quality order that refers to a route operation can use information in a quality association record, such as the test sampling plan.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="5da21-259">Inventario</span><span class="sxs-lookup"><span data-stu-id="5da21-259">Inventory</span></span></td>
<td><span data-ttu-id="5da21-260">Un pedido de calidad no se puede generar automáticamente para una transacción en un diario de inventario o para las transacciones de un pedido de transferencia.</span><span class="sxs-lookup"><span data-stu-id="5da21-260">A quality order cannot be automatically generated for a transaction in an inventory journal or for transfer order transactions.</span></span></td>
<td></td>
<td></td>
<td><span data-ttu-id="5da21-261">Un pedido de calidad se debe crear manualmente para la cantidad de inventario de un artículo.</span><span class="sxs-lookup"><span data-stu-id="5da21-261">A quality order must be created manually for an item&#39;s inventory quantity.</span></span> <span data-ttu-id="5da21-262">Se requiere el inventario físico disponible.</span><span class="sxs-lookup"><span data-stu-id="5da21-262">Physical on-hand inventory is required.</span></span></td>
</tr>
</tbody>
</table>

## <a name="quality-order-auto-generation-examples"></a><span data-ttu-id="5da21-263">Ejemplos de la generación automática del pedido de calidad</span><span class="sxs-lookup"><span data-stu-id="5da21-263">Quality order auto-generation examples</span></span>

### <a name="purchasing"></a><span data-ttu-id="5da21-264">Compras</span><span class="sxs-lookup"><span data-stu-id="5da21-264">Purchasing</span></span>

<span data-ttu-id="5da21-265">En la compra, si establece el campo **Tipo de evento** en **Recepción de producto** y el campo **Ejecución** en **Después** en la página **Asociaciones de calidad**, obtiene los resultados siguientes:</span><span class="sxs-lookup"><span data-stu-id="5da21-265">In purchasing, if you set the **Event type** field to **Product receipt** and the **Execution** field to **After** on the **Quality associations** page, you get the following results:</span></span> 

- <span data-ttu-id="5da21-266">Si la opción **Por cantidad actualizada** se establece en **Sí**, un pedido de calidad se genera para cada recepción con el pedido de compra, en función de la cantidad y los valores recibidos en el muestreo de artículos.</span><span class="sxs-lookup"><span data-stu-id="5da21-266">If the **Per updated quantity** option is set to **Yes**, a quality order is generated for every receipt against the purchase order, based on the received quantity and settings in the item sampling.</span></span> <span data-ttu-id="5da21-267">Cada vez que una cantidad se reciba contra el pedido de compra, los nuevos pedidos de calidad se generan en función de la cantidad recién recibida.</span><span class="sxs-lookup"><span data-stu-id="5da21-267">Every time that a quantity is received against the purchase order, new quality orders are generated based on the newly received quantity.</span></span>
- <span data-ttu-id="5da21-268">Si la opción **Por cantidad actualizada** se establece en **No**, un pedido de calidad se genera para la primera recepción con el pedido de compra, en función de la cantidad recibida.</span><span class="sxs-lookup"><span data-stu-id="5da21-268">If the **Per updated quantity** option is set to **No**, a quality order is generated for the first receipt against the purchase order, based on the received quantity.</span></span> <span data-ttu-id="5da21-269">Además, uno o más pedidos de calidad se crean en función de la cantidad restante, en función de las dimensiones de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="5da21-269">Additionally, one or more quality orders are created based on the remaining quantity, depending on the tracking dimensions.</span></span> <span data-ttu-id="5da21-270">Los pedidos de calidad no se generan para las recepciones posteriores con el pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="5da21-270">Quality orders aren't generated for subsequent receipts against the purchase order.</span></span>

### <a name="production"></a><span data-ttu-id="5da21-271">Producción</span><span class="sxs-lookup"><span data-stu-id="5da21-271">Production</span></span>

<span data-ttu-id="5da21-272">En la producción, si establece el campo **Tipo de evento** en **Informar como completado** y el campo **Ejecución** en **Después** en la página **Asociaciones de calidad**, obtiene los resultados siguientes:</span><span class="sxs-lookup"><span data-stu-id="5da21-272">In production, if you set the **Event type** field to **Report as finished** and the **Execution** field to **After** on the **Quality associations** page, you get the following results:</span></span>

- <span data-ttu-id="5da21-273">Si la opción **Por cantidad actualizada** se establece en **Sí**, un pedido de calidad se genera para cada cantidad y valores completados en el muestreo de artículos.</span><span class="sxs-lookup"><span data-stu-id="5da21-273">If the **Per updated quantity** option is set to **Yes**, a quality order is generated based on every finished quantity and settings in the item sampling.</span></span> <span data-ttu-id="5da21-274">Cada vez que una cantidad se notifique como terminado con el pedido de producción, los nuevos pedidos de calidad se generan en función de la cantidad recién terminada.</span><span class="sxs-lookup"><span data-stu-id="5da21-274">Every time that a quantity is reported as finished against the production order, new quality orders are generated based on newly finished quantity.</span></span> <span data-ttu-id="5da21-275">Esta lógica de la generación es coherente con la compra.</span><span class="sxs-lookup"><span data-stu-id="5da21-275">This generation logic is consistent with purchasing.</span></span>
- <span data-ttu-id="5da21-276">Si la opción **Por cantidad actualizada** se establece en **No**, un pedido de calidad se genera para la primera vez que una cantidad se notifica como terminada, en función de la cantidad terminada.</span><span class="sxs-lookup"><span data-stu-id="5da21-276">If the **Per updated quantity** option is set to **No**, a quality order is generated the first time that a quantity is reported as finished, based on the finished quantity.</span></span> <span data-ttu-id="5da21-277">Además, uno o más pedidos de calidad se crean en función de la cantidad restante, en función de las dimensiones de seguimiento del muestreo del artículo.</span><span class="sxs-lookup"><span data-stu-id="5da21-277">Additionally, one or more quality orders are created based on the remaining quantity, depending on the tracking dimensions of the item sampling.</span></span> <span data-ttu-id="5da21-278">Los pedidos de calidad no se generan para las cantidades finalizadas posteriores.</span><span class="sxs-lookup"><span data-stu-id="5da21-278">Quality orders aren't generated for subsequent finished quantities.</span></span>

<table>
<tbody>
<tr>
<th><span data-ttu-id="5da21-279">Especificación de calidad</span><span class="sxs-lookup"><span data-stu-id="5da21-279">Quality specification</span></span></th>
<th><span data-ttu-id="5da21-280">Por cantidad actualizada</span><span class="sxs-lookup"><span data-stu-id="5da21-280">Per updated quantity</span></span></th>
<th><span data-ttu-id="5da21-281">Por dimensión de seguimiento</span><span class="sxs-lookup"><span data-stu-id="5da21-281">Per tracking dimension</span></span></th>
<th><span data-ttu-id="5da21-282">Resultado</span><span class="sxs-lookup"><span data-stu-id="5da21-282">Result</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="5da21-283">Porcentaje: 10 %</span><span class="sxs-lookup"><span data-stu-id="5da21-283">Percentage: 10%</span></span></td>
<td><span data-ttu-id="5da21-284">Sí</span><span class="sxs-lookup"><span data-stu-id="5da21-284">Yes</span></span></td>
<td>
<p><span data-ttu-id="5da21-285">Número de lote: No</span><span class="sxs-lookup"><span data-stu-id="5da21-285">Batch number: No</span></span></p>
<p><span data-ttu-id="5da21-286">Número de serie: No</span><span class="sxs-lookup"><span data-stu-id="5da21-286">Serial number: No</span></span></p>
</td>
<td>
<p><span data-ttu-id="5da21-287">Cantidad de pedido: 100</span><span class="sxs-lookup"><span data-stu-id="5da21-287">Order quantity: 100</span></span></p>
<ol>
<li><span data-ttu-id="5da21-288">Notificar como terminado para 30</span><span class="sxs-lookup"><span data-stu-id="5da21-288">Report as finished for 30</span></span>
<ul>
<li><span data-ttu-id="5da21-289">Pedido de calidad #1 para 3 (10 % de 30)</span><span class="sxs-lookup"><span data-stu-id="5da21-289">Quality order #1 for 3 (10% of 30)</span></span></li>
</ul>
</li>
<li><span data-ttu-id="5da21-290">Notificar como terminado para 70</span><span class="sxs-lookup"><span data-stu-id="5da21-290">Report as finished for 70</span></span>
<ul>
<li><span data-ttu-id="5da21-291">Pedido de calidad #2 para 7 (10% de la cantidad de pedido restantes, que es igual a 70 en este caso)</span><span class="sxs-lookup"><span data-stu-id="5da21-291">Quality order #2 for 7 (10% of the remaining order quantity, which equals 70 in this case)</span></span></li>
</ul>
</li>
</ol>
</td>
</tr>
<tr>
<td><span data-ttu-id="5da21-292">Cantidad fija: 1</span><span class="sxs-lookup"><span data-stu-id="5da21-292">Fixed quantity: 1</span></span></td>
<td><span data-ttu-id="5da21-293">No</span><span class="sxs-lookup"><span data-stu-id="5da21-293">No</span></span></td>
<td>
<p><span data-ttu-id="5da21-294">Número de lote: No</span><span class="sxs-lookup"><span data-stu-id="5da21-294">Batch number: No</span></span></p>
<p><span data-ttu-id="5da21-295">Número de serie: No</span><span class="sxs-lookup"><span data-stu-id="5da21-295">Serial number: No</span></span></p>
</td>
<td><span data-ttu-id="5da21-296">Cantidad de pedido: 100</span><span class="sxs-lookup"><span data-stu-id="5da21-296">Order quantity: 100</span></span>
<ol>
<li><span data-ttu-id="5da21-297">Notificar como terminado para 30</span><span class="sxs-lookup"><span data-stu-id="5da21-297">Report as finished for 30</span></span>
<ul>
<li><span data-ttu-id="5da21-298">El pedido de calidad #1para 1 (para la primera cantidad notificada como terminada, que tiene un valor fijo de 1)</span><span class="sxs-lookup"><span data-stu-id="5da21-298">Quality order #1 for 1 (for the first reported-as-finished quantity, which has a fixed value of 1)</span></span></li>
<li><span data-ttu-id="5da21-299">El pedido de calidad #2 para 1 (para la cantidad restante, que todavía un valor fijo de 1)</span><span class="sxs-lookup"><span data-stu-id="5da21-299">Quality order #2 for 1 (for the remaining quantity, which still has a fixed value of 1)</span></span></li>
</ul>
</li>
<li><span data-ttu-id="5da21-300">Notificar como terminado para 10</span><span class="sxs-lookup"><span data-stu-id="5da21-300">Report as finished for 10</span></span>
<ul>
<li><span data-ttu-id="5da21-301">No se crea ningún pedido de calidad.</span><span class="sxs-lookup"><span data-stu-id="5da21-301">No quality orders are created.</span></span></li>
</ul>
</li>
<li><span data-ttu-id="5da21-302">Notificar como terminado para 60</span><span class="sxs-lookup"><span data-stu-id="5da21-302">Report as finished for 60</span></span>
<ul>
<li><span data-ttu-id="5da21-303">No se crea ningún pedido de calidad.</span><span class="sxs-lookup"><span data-stu-id="5da21-303">No quality orders are created.</span></span></li>
</ul>
</li>
</ol>
</td>
</tr>
<tr>
<td><span data-ttu-id="5da21-304">Cantidad fija: 1</span><span class="sxs-lookup"><span data-stu-id="5da21-304">Fixed quantity: 1</span></span></td>
<td><span data-ttu-id="5da21-305">Sí</span><span class="sxs-lookup"><span data-stu-id="5da21-305">Yes</span></span></td>
<td>
<p><span data-ttu-id="5da21-306">Número de lote: Sí</span><span class="sxs-lookup"><span data-stu-id="5da21-306">Batch number: Yes</span></span></p>
<p><span data-ttu-id="5da21-307">Número de serie: Sí</span><span class="sxs-lookup"><span data-stu-id="5da21-307">Serial number: Yes</span></span></p>
</td>
<td>
<p><span data-ttu-id="5da21-308">Cantidad de pedido: 10</span><span class="sxs-lookup"><span data-stu-id="5da21-308">Order quantity: 10</span></span></p>
<ol>
<li><span data-ttu-id="5da21-309">Notificar como terminado para 3: 1 para #b1, #s1; 1 para #b2, #s2; y 1 para #b3, #s3</span><span class="sxs-lookup"><span data-stu-id="5da21-309">Report as finished for 3: 1 for #b1, #s1; 1 for #b2, #s2; and 1 for #b3, #s3</span></span>
<ul>
<li><span data-ttu-id="5da21-310">Pedido de calidad #1 para 1 del lote #b1, serie #s1</span><span class="sxs-lookup"><span data-stu-id="5da21-310">Quality order #1 for 1 of batch #b1, serial #s1</span></span></li>
<li><span data-ttu-id="5da21-311">Pedido de calidad #2 para 1 del lote #b2, serie #s2</span><span class="sxs-lookup"><span data-stu-id="5da21-311">Quality order #2 for 1 of batch #b2, serial #s2</span></span></li>
<li><span data-ttu-id="5da21-312">Pedido de calidad #3 para 1 del lote #b3, serie #s3</span><span class="sxs-lookup"><span data-stu-id="5da21-312">Quality order #3 for 1 of batch #b3, serial #s3</span></span></li>
</ul>
</li>
<li><span data-ttu-id="5da21-313">Notificar como terminado para 2: 1 para #b4, #s4; y 1 para #b5, #s5</span><span class="sxs-lookup"><span data-stu-id="5da21-313">Report as finished for 2: 1 for #b4, #s4; and 1 for #b5, #s5</span></span>
<ul>
<li><span data-ttu-id="5da21-314">Pedido de calidad #4 para 1 del lote #b4, serie #s4</span><span class="sxs-lookup"><span data-stu-id="5da21-314">Quality order #4 for 1 of batch #b4, serial #s4</span></span></li>
<li><span data-ttu-id="5da21-315">Pedido de calidad #5 para 1 del lote #b5, serie #s5</span><span class="sxs-lookup"><span data-stu-id="5da21-315">Quality order #5 for 1 of batch #b5, serial #s5</span></span></li>
</ul>
</li>
</ol>
<p><span data-ttu-id="5da21-316"><strong>Nota:</strong> El lote se puede volver a utilizar.</span><span class="sxs-lookup"><span data-stu-id="5da21-316"><strong>Note:</strong> The batch can be reused.</span></span></p>
</td>
</tr>
<tr>
<td><span data-ttu-id="5da21-317">Cantidad fija: 2</span><span class="sxs-lookup"><span data-stu-id="5da21-317">Fixed quantity: 2</span></span></td>
<td><span data-ttu-id="5da21-318">No</span><span class="sxs-lookup"><span data-stu-id="5da21-318">No</span></span></td>
<td>
<p><span data-ttu-id="5da21-319">Número de lote: Sí</span><span class="sxs-lookup"><span data-stu-id="5da21-319">Batch number: Yes</span></span></p>
<p><span data-ttu-id="5da21-320">Número de serie: Sí</span><span class="sxs-lookup"><span data-stu-id="5da21-320">Serial number: Yes</span></span></p>
</td>
<td>
<p><span data-ttu-id="5da21-321">Cantidad de pedido: 10</span><span class="sxs-lookup"><span data-stu-id="5da21-321">Order quantity: 10</span></span></p>
<ol>
<li><span data-ttu-id="5da21-322">Notificar como terminado para 4: 1 para #b1, #s1; 1 para #b2, #s2; 1 para #b3, #s3; y 1 para #b4 #s4</span><span class="sxs-lookup"><span data-stu-id="5da21-322">Report as finished for 4: 1 for #b1, #s1; 1 for #b2, #s2; 1 for #b3, #s3; and 1 for #b4, #s4</span></span>
<ul>
<li><span data-ttu-id="5da21-323">Pedido de calidad #1 para 1 del lote #b1, serie #s1</span><span class="sxs-lookup"><span data-stu-id="5da21-323">Quality order #1 for 1 of batch #b1, serial #s1</span></span></li>
<li><span data-ttu-id="5da21-324">Pedido de calidad #2 para 1 del lote #b2, serie #s2</span><span class="sxs-lookup"><span data-stu-id="5da21-324">Quality order #2 for 1 of batch #b2, serial #s2</span></span></li>
<li><span data-ttu-id="5da21-325">Pedido de calidad #3 para 1 del lote #b3, serie #s3</span><span class="sxs-lookup"><span data-stu-id="5da21-325">Quality order #3 for 1 of batch #b3, serial #s3</span></span></li>
<li><span data-ttu-id="5da21-326">Pedido de calidad #4 para 1 del lote #b4, serie #s4</span><span class="sxs-lookup"><span data-stu-id="5da21-326">Quality order #4 for 1 of batch #b4, serial #s4</span></span></li>
</ul>
<ul>
<li><span data-ttu-id="5da21-327">Pedido de calidad #5 para 2, sin una referencia a un lote y un número de serie</span><span class="sxs-lookup"><span data-stu-id="5da21-327">Quality order #5 for 2, without a reference to a batch and a serial number</span></span></li>
</ul>
</li>
<li><span data-ttu-id="5da21-328">Notificar como terminado para 6: 1 para #b5, #s5; 1 para #b6, #s6; 1 para #b7, #s7; 1 para #b8, #s8; 1 para #b9, #s9; y 1 para #b10, #s10</span><span class="sxs-lookup"><span data-stu-id="5da21-328">Report as finished for 6: 1 for #b5, #s5; 1 for #b6, #s6; 1 for #b7, #s7; 1 for #b8, #s8; 1 for #b9, #s9; and 1 for #b10, #s10</span></span>
<ul>
<li><span data-ttu-id="5da21-329">No se crea ningún pedido de calidad.</span><span class="sxs-lookup"><span data-stu-id="5da21-329">No quality orders are created.</span></span></li>
</ul>
</li>
</ol>
</td>
</tr>
</tbody>
</table>

> [!NOTE]
> <span data-ttu-id="5da21-330">La característica *Gestión de calidad para procesos de almacén* agrega capacidades para el procesamiento de pedidos de calidad para la producción con **Tipo de evento** establecido en *Informar como terminado* y **Ejecución** establecido en *Después*, y para compras con **Tipo de evento** establecido en *Registro*.</span><span class="sxs-lookup"><span data-stu-id="5da21-330">The *Quality management for warehouse processes* feature adds capabilities for quality order processing for production with **Event type** set to *Report as finished* and **Execution** set to *After*, and for purchases with **Event type** set to *Registration*.</span></span> <span data-ttu-id="5da21-331">Para más detalles, vea [Administración de la calidad para procesos de almacén](quality-management-for-warehouses-processes.md).</span><span class="sxs-lookup"><span data-stu-id="5da21-331">For details, see [Quality management for warehouse processes](quality-management-for-warehouses-processes.md).</span></span>

## <a name="quality-management-pages"></a><span data-ttu-id="5da21-332">Páginas de administración de calidad</span><span class="sxs-lookup"><span data-stu-id="5da21-332">Quality management pages</span></span>
<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5da21-333">Página</span><span class="sxs-lookup"><span data-stu-id="5da21-333">Page</span></span></th>
<th><span data-ttu-id="5da21-334">Descripción</span><span class="sxs-lookup"><span data-stu-id="5da21-334">Description</span></span></th>
<th><span data-ttu-id="5da21-335">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5da21-335">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="5da21-336">Asociaciones de calidad</span><span class="sxs-lookup"><span data-stu-id="5da21-336">Quality associations</span></span></td>
<td><span data-ttu-id="5da21-337">Consulte las secciones anteriores de este artículo.</span><span class="sxs-lookup"><span data-stu-id="5da21-337">See the previous sections of this article.</span></span></td>
<td><span data-ttu-id="5da21-338">Una asociación de calidad define toda la información siguiente para un pedido de calidad que se genera:</span><span class="sxs-lookup"><span data-stu-id="5da21-338">A quality association defines all the following information for a quality order that is generated:</span></span>
<ul>
<li><span data-ttu-id="5da21-339">El evento de transacción</span><span class="sxs-lookup"><span data-stu-id="5da21-339">The transaction event</span></span></li>
<li><span data-ttu-id="5da21-340">El conjunto de pruebas que se deben realizar en los artículos</span><span class="sxs-lookup"><span data-stu-id="5da21-340">The set of tests that must be performed on the items</span></span></li>
<li><span data-ttu-id="5da21-341">El nivel de calidad aceptable</span><span class="sxs-lookup"><span data-stu-id="5da21-341">The AQL</span></span></li>
<li><span data-ttu-id="5da21-342">El plan de muestreo</span><span class="sxs-lookup"><span data-stu-id="5da21-342">The sampling plan</span></span></li>
</ul>
<span data-ttu-id="5da21-343">Debe definir una asociación de calidad para cada variación de un proceso empresarial que requiera la generación automática de pedidos de calidad.</span><span class="sxs-lookup"><span data-stu-id="5da21-343">You must define a quality association for each variation in a business process that requires automatic generation of quality orders.</span></span> <span data-ttu-id="5da21-344">Por ejemplo, un pedido de calidad se puede generar en los procesos empresariales para los pedidos de compra, pedidos de cuarentena, pedidos de ventas y pedidos de producción.</span><span class="sxs-lookup"><span data-stu-id="5da21-344">For example, a quality order can be generated in the business processes for purchase orders, quarantine orders, sales orders, and production orders.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="5da21-345">Pruebas</span><span class="sxs-lookup"><span data-stu-id="5da21-345">Tests</span></span></td>
<td><span data-ttu-id="5da21-346">Utilice esta página para definir y visualizar las pruebas individuales que determinan si sus productos cumplen las especificaciones de calidad.</span><span class="sxs-lookup"><span data-stu-id="5da21-346">Use this page to define and view the individual tests that determine whether your products meet quality specifications.</span></span> <span data-ttu-id="5da21-347">Puede asignar una o varias pruebas individuales a un grupo de pruebas.</span><span class="sxs-lookup"><span data-stu-id="5da21-347">You can assign one or more individual tests to a test group.</span></span> <span data-ttu-id="5da21-348">En este caso, también especifica la información específica de la prueba, como los valores de medida aceptables.</span><span class="sxs-lookup"><span data-stu-id="5da21-348">In this case, you also specify test-specific information, such as the acceptable measurement values.</span></span> <span data-ttu-id="5da21-349">Los valores de medida se usan para pruebas cuantitativas y las variables de prueba se usan para las pruebas cualitativas.</span><span class="sxs-lookup"><span data-stu-id="5da21-349">Measurement values are used for quantitative tests, and test variables are used for qualitative tests.</span></span>
<ul>
<li><span data-ttu-id="5da21-350">Una prueba cuantitativa tiene un tipo de prueba de <strong>Entero</strong> o <strong>Fracción</strong> y una unidad de medida designada.</span><span class="sxs-lookup"><span data-stu-id="5da21-350">A quantitative test has a test type of <strong>Integer</strong> or <strong>Fraction</strong>, and also has a designated unit of measure.</span></span> <span data-ttu-id="5da21-351">Las especificaciones de calidad y los resultados de la prueba se expresan como números.</span><span class="sxs-lookup"><span data-stu-id="5da21-351">Quality specifications and test results are expressed as numbers.</span></span></li>
<li><span data-ttu-id="5da21-352">Una prueba cualitativa tiene una prueba de tipo <strong>Opción</strong>.</span><span class="sxs-lookup"><span data-stu-id="5da21-352">A qualitative test has a test type of <strong>Option</strong>.</span></span> <span data-ttu-id="5da21-353">Las pruebas cualitativas requieren información adicional sobre la variable de prueba que se está midiendo y sus opciones enumeradas.</span><span class="sxs-lookup"><span data-stu-id="5da21-353">Qualitative tests require additional information about the test variable that is being measured and its enumerated options.</span></span> <span data-ttu-id="5da21-354">Las especificaciones de calidad y los resultados de la prueba se expresan en función de un resultado.</span><span class="sxs-lookup"><span data-stu-id="5da21-354">Quality specifications and test results are expressed according to an outcome.</span></span></li>
</ul></td>
<td><span data-ttu-id="5da21-355">Una empresa de fabricación realiza dos pruebas en el material adquirido: una prueba cuantitativa sobre la calidad del material y una prueba cualitativa sobre los daños de embalaje.</span><span class="sxs-lookup"><span data-stu-id="5da21-355">A manufacturing company performs two tests on purchased material: a quantitative test about material quality and a qualitative test about packaging damage.</span></span> <span data-ttu-id="5da21-356">La empresa define información adicional sobre la prueba cualitativa para identificar la variable de prueba (embalaje dañado) y sus resultados.</span><span class="sxs-lookup"><span data-stu-id="5da21-356">The company defines additional information about the qualitative test to identify the test variable (damaged packaging) and its outcomes.</span></span> <span data-ttu-id="5da21-357">La empresa usa la página <strong>Grupos de prueba</strong> para asignar las dos pruebas a un grupo de pruebas y para especificar la información específica de la prueba.</span><span class="sxs-lookup"><span data-stu-id="5da21-357">The company uses the <strong>Test groups</strong> page to assign the two tests to a test group and to specify the test-specific information.</span></span> <span data-ttu-id="5da21-358">El grupo de pruebas se asigna a un pedido de calidad, de modo que la empresa puede informar de los resultados de la prueba para las dos pruebas.</span><span class="sxs-lookup"><span data-stu-id="5da21-358">The test group is assigned to a quality order, so that the company can report test results for the two tests.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="5da21-359">Grupos de prueba</span><span class="sxs-lookup"><span data-stu-id="5da21-359">Test groups</span></span></td>
<td><span data-ttu-id="5da21-360">Use esta página para establecer, editar y ver los grupos de prueba y las pruebas individuales asignadas a un grupo de prueba.</span><span class="sxs-lookup"><span data-stu-id="5da21-360">Use this page to set up, edit, and view test groups and the individual tests that are assigned to a test group.</span></span> <span data-ttu-id="5da21-361">En el panel superior se muestran los grupos de pruebas y en el inferior se muestran las pruebas asignadas a un grupo de pruebas seleccionado.</span><span class="sxs-lookup"><span data-stu-id="5da21-361">The upper pane displays test groups, and the lower pane displays the tests that are assigned to a selected test group.</span></span> <span data-ttu-id="5da21-362">A un grupo de pruebas se le asignan varias directivas, por ejemplo, un plan de muestreo, un nivel de calidad aceptable (AQL) y el requisito de la prueba destructiva.</span><span class="sxs-lookup"><span data-stu-id="5da21-362">You assign several policies to a test group, such as a sampling plan, an AQL, and the requirement for destructive testing.</span></span> <span data-ttu-id="5da21-363">Al asignar una prueba individual a un grupo de prueba, define información adicional, como la secuencia, los documentos, y las fechas de validez.</span><span class="sxs-lookup"><span data-stu-id="5da21-363">When you assign an individual test to a test group, you define additional information, such as the sequence, documents, and validity dates.</span></span> <span data-ttu-id="5da21-364">Para una prueba cuantitativa, la información que define también incluye los valores de medida aceptables.</span><span class="sxs-lookup"><span data-stu-id="5da21-364">For a quantitative test, the information that you define also includes the acceptable measurement values.</span></span> <span data-ttu-id="5da21-365">Para una prueba cualitativa, la información incluye la variable de prueba y el resultado predeterminado.</span><span class="sxs-lookup"><span data-stu-id="5da21-365">For a qualitative test, the information includes the test variable and default outcome.</span></span> <span data-ttu-id="5da21-366">El grupo de prueba asignado a un pedido de calidad define el conjunto predeterminado de pruebas que se tienen que realizar sobre el artículo especificado.</span><span class="sxs-lookup"><span data-stu-id="5da21-366">The test group that is assigned to a quality order defines the default set of tests that must be performed on the specified item.</span></span> <span data-ttu-id="5da21-367">No obstante, puede agregar, cambiar o eliminar las pruebas en el pedido de calidad.</span><span class="sxs-lookup"><span data-stu-id="5da21-367">However, you can add, delete, or change tests on the quality order.</span></span> <span data-ttu-id="5da21-368">Los resultados de prueba se notifican para cada prueba de un pedido de calidad.</span><span class="sxs-lookup"><span data-stu-id="5da21-368">Test results are reported for each test on a quality order.</span></span></td>
<td><span data-ttu-id="5da21-369">Un fabricante define un grupo de pruebas para cada variación de sus criterios de calidad.</span><span class="sxs-lookup"><span data-stu-id="5da21-369">A manufacturing company defines a test group for each variation of its quality guidelines.</span></span> <span data-ttu-id="5da21-370">Los distintos grupos de pruebas reflejan las diferencias de los planes de muestreo, los conjuntos de pruebas que se deben realizar en conjunto, el AQL y otros factores.</span><span class="sxs-lookup"><span data-stu-id="5da21-370">The various test groups reflect differences in the sampling plans, the sets of tests that must be performed together, the AQL, and other factors.</span></span> <span data-ttu-id="5da21-371">Para las pruebas cuantitativas también hay diferencias en los valores de medida aceptables.</span><span class="sxs-lookup"><span data-stu-id="5da21-371">For quantitative tests, there are also differences in the acceptable measurement values.</span></span> <span data-ttu-id="5da21-372">Para aplicar sus criterios de calidad, la empresa asigna un grupo de prueba a cada regla con el fin de generar automáticamente pedidos de calidad en la página <strong>Asociaciones de calidad</strong> y también asigna un grupo de prueba a los pedidos de calidad creados manualmente.</span><span class="sxs-lookup"><span data-stu-id="5da21-372">To enforce its quality guidelines, the company assigns a test group to each rule for automatically generating quality orders on the <strong>Quality associations</strong> page, and also assigns a test group to quality orders that are manually created.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="5da21-373">Grupos de calidad de artículos</span><span class="sxs-lookup"><span data-stu-id="5da21-373">Item quality groups</span></span></td>
<td><span data-ttu-id="5da21-374">Use esta página para configurar, editar y ver los artículos asignados a un grupo de calidad o a los grupos de calidad asignados a un artículo.</span><span class="sxs-lookup"><span data-stu-id="5da21-374">Use this page to set up, edit, and view the items that are assigned to a quality group or the quality groups that are assigned to an item.</span></span> <span data-ttu-id="5da21-375">Un grupo de calidad representa requisitos de prueba comunes para los artículos.</span><span class="sxs-lookup"><span data-stu-id="5da21-375">A quality group represents common testing requirements for items.</span></span> <span data-ttu-id="5da21-376">Cuando haya definido los requisitos de prueba en la página <strong>Grupos de prueba</strong>, puede definir las reglas para generar automáticamente pedidos de calidad.</span><span class="sxs-lookup"><span data-stu-id="5da21-376">After you define the test requirements on the <strong>Test groups</strong> page, you can define the rules for automatically generating quality orders.</span></span> <span data-ttu-id="5da21-377">Para simplificar el proceso, no se definen reglas para artículos individuales.</span><span class="sxs-lookup"><span data-stu-id="5da21-377">To simplify the process, you don&#39;t define rules for individual items.</span></span> <span data-ttu-id="5da21-378">En su lugar, puede definir las reglas para un grupo de calidad mediante la página <strong>Asociaciones de calidad</strong>.</span><span class="sxs-lookup"><span data-stu-id="5da21-378">Instead, you define rules for a quality group, by using the <strong>Quality associations</strong> page.</span></span> <span data-ttu-id="5da21-379">También puede usar la página <strong>Grupos de calidad de artículos</strong> para un grupo de calidad seleccionado para asignar artículos relevantes a dicho grupo.</span><span class="sxs-lookup"><span data-stu-id="5da21-379">You can also use the <strong>Item quality groups</strong> page for a selected quality group to assign relevant items to that group.</span></span> <span data-ttu-id="5da21-380">También puede usar la página <strong>Grupos de calidad de artículos</strong> para un artículo seleccionado para asignar grupos de calidad relevantes a dicho artículo.</span><span class="sxs-lookup"><span data-stu-id="5da21-380">You can also use the <strong>Item quality groups</strong> page for a selected item to assign relevant quality groups to that item.</span></span></td>
<td><span data-ttu-id="5da21-381">Un fabricante compra varias materias primas con los mismos requisitos de prueba para una inspección entrante.</span><span class="sxs-lookup"><span data-stu-id="5da21-381">A manufacturing company purchases various raw materials that have the same testing requirements for incoming inspection.</span></span> <span data-ttu-id="5da21-382">La empresa define un grupo de calidad y, después, le asigna números de artículo asociados con las materias primas para ese grupo.</span><span class="sxs-lookup"><span data-stu-id="5da21-382">The company defines a quality group and then assigns the item numbers that are associated with the raw materials to that group.</span></span> <span data-ttu-id="5da21-383">Más adelante, la empresa compra un nuevo tipo de materia prima con los mismos requisitos de prueba.</span><span class="sxs-lookup"><span data-stu-id="5da21-383">Later, the company purchases a new type of raw material that has the same testing requirements.</span></span> <span data-ttu-id="5da21-384">En lugar de configurar requisitos de prueba nuevos para el nuevo material, la empresa añade el número de artículo del nuevo material al grupo de calidad existente.</span><span class="sxs-lookup"><span data-stu-id="5da21-384">Instead of setting up new testing requirements for the new material, the company adds the item number for the new material to the existing quality group.</span></span> <span data-ttu-id="5da21-385">El mismo fabricante también produce artículos con los mismos requisitos de prueba y envía artículos con los mismos requisitos para las pruebas anteriores al envío.</span><span class="sxs-lookup"><span data-stu-id="5da21-385">The same manufacturing company also produces items that have the same production testing requirements and ships items that have the same requirement for pre-shipment testing.</span></span> <span data-ttu-id="5da21-386">La empresa define dos grupos de calidad adicionales y, después, asigna números de artículo pertinentes a cada grupo.</span><span class="sxs-lookup"><span data-stu-id="5da21-386">The company defines two additional quality groups and then assigns the relevant item numbers to each group.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="5da21-387">Variables de prueba</span><span class="sxs-lookup"><span data-stu-id="5da21-387">Test variables</span></span></td>
<td><span data-ttu-id="5da21-388">Use esta página para definir y ver las variables asociadas a una prueba cualitativa.</span><span class="sxs-lookup"><span data-stu-id="5da21-388">Use this page to define and view the variables that are associated with a qualitative test.</span></span> <span data-ttu-id="5da21-389">Para cada variable, define los resultados enumerados que representan las posibles opciones.</span><span class="sxs-lookup"><span data-stu-id="5da21-389">For each variable, you define enumerated outcomes that represent the possible options.</span></span> <span data-ttu-id="5da21-390">Puede definir pruebas en la página <strong>Pruebas</strong>.</span><span class="sxs-lookup"><span data-stu-id="5da21-390">You define tests on the <strong>Tests</strong> page.</span></span> <span data-ttu-id="5da21-391">Para las pruebas cualitativas, debe definir el tipo de prueba en <strong>Opción</strong>.</span><span class="sxs-lookup"><span data-stu-id="5da21-391">For qualitative tests, you must set the test type to <strong>Option</strong>.</span></span> <span data-ttu-id="5da21-392">Use la página <strong>Grupos de prueba</strong> para asignar una variable de prueba a una prueba individual.</span><span class="sxs-lookup"><span data-stu-id="5da21-392">Use the <strong>Test groups</strong> page to assign a test variable to an individual test.</span></span></td>
<td><span data-ttu-id="5da21-393">Una fábrica de galletas utiliza una prueba de inspección para el producto terminado.</span><span class="sxs-lookup"><span data-stu-id="5da21-393">A manufacturing company that produces cookies uses an inspection test for the finished product.</span></span> <span data-ttu-id="5da21-394">Esta prueba de inspección tiene varias variables.</span><span class="sxs-lookup"><span data-stu-id="5da21-394">This inspection test has several variables.</span></span> <span data-ttu-id="5da21-395">Una variable es el gusto y los posibles resultados para esta variable son bueno y malo.</span><span class="sxs-lookup"><span data-stu-id="5da21-395">One variable is taste, and the possible outcomes for this variable are good and bad.</span></span> <span data-ttu-id="5da21-396">Una segunda variable es el color y los posibles resultados son demasiado oscuro, demasiado claro y correcto.</span><span class="sxs-lookup"><span data-stu-id="5da21-396">A second variable is color, and the possible outcomes are too dark, too light, and correct.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="5da21-397">Resultados de la variable de prueba</span><span class="sxs-lookup"><span data-stu-id="5da21-397">Test variable outcomes</span></span></td>
<td><span data-ttu-id="5da21-398">Utilice esta página para configurar, editar y visualizar los resultados posibles de una variable de prueba asociada a una prueba cualitativa.</span><span class="sxs-lookup"><span data-stu-id="5da21-398">Use this page to set up, edit, and to view the possible test results for a test variable that is associated with a qualitative test.</span></span> <span data-ttu-id="5da21-399">Para cada resultado, asigne un estado de <strong>correcto</strong> o <strong>erróneo</strong>.</span><span class="sxs-lookup"><span data-stu-id="5da21-399">For each outcome, you assign a <strong>pass</strong> or <strong>fail</strong> status.</span></span> <span data-ttu-id="5da21-400">Deberá definir una variable y sus resultados para cada prueba cualitativa definida en la página <strong>Pruebas</strong>.</span><span class="sxs-lookup"><span data-stu-id="5da21-400">You must define a variable and its outcomes for each qualitative test that is defined on the <strong>Tests</strong> page.</span></span> <span data-ttu-id="5da21-401">(Para las pruebas cualitativas, el tipo de prueba se establece en <strong>Opción</strong> en la página <strong>Pruebas</strong>). Utilice la página <strong>Grupos de prueba</strong> para asignar una variable de prueba y el resultado predeterminado a una prueba cualitativa individual.</span><span class="sxs-lookup"><span data-stu-id="5da21-401">(For qualitative tests, the test type is set to <strong>Option</strong> on the <strong>Tests</strong> page.) Use the <strong>Test groups</strong> page to assign a test variable and the default outcome to an individual qualitative test.</span></span></td>
<td><span data-ttu-id="5da21-402">Una fábrica de galletas utiliza una prueba de inspección para el producto terminado.</span><span class="sxs-lookup"><span data-stu-id="5da21-402">A manufacturing company that produces cookies uses an inspection test for the finished product.</span></span> <span data-ttu-id="5da21-403">Esta prueba de inspección tiene varias variables.</span><span class="sxs-lookup"><span data-stu-id="5da21-403">This inspection test has of several variables.</span></span> <span data-ttu-id="5da21-404">Una variable es el gusto y los posibles resultados para esta variable son bueno y malo.</span><span class="sxs-lookup"><span data-stu-id="5da21-404">One variable is taste, and the possible outcomes for this variable are good and bad.</span></span> <span data-ttu-id="5da21-405">Una segunda variable es el color y los posibles resultados son demasiado oscuro, demasiado claro y correcto.</span><span class="sxs-lookup"><span data-stu-id="5da21-405">A second variable is color, and the possible outcomes are too dark, too light, and correct.</span></span> <span data-ttu-id="5da21-406">Cada resultado tiene asignado un estado de <strong>correcto</strong> o <strong>erróneo</strong>.</span><span class="sxs-lookup"><span data-stu-id="5da21-406">A status of <strong>pass</strong> or <strong>fail</strong> is assigned to each outcome.</span></span> <span data-ttu-id="5da21-407">Durante la prueba de inspección de cada variable, el inspector notifica el resultado de la prueba seleccionando uno de los resultados.</span><span class="sxs-lookup"><span data-stu-id="5da21-407">During the inspection test for each variable, the inspector reports the test result by selecting one of the outcomes.</span></span></td>
</tr>
</tbody>
</table>



<a name="additional-resources"></a><span data-ttu-id="5da21-408">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="5da21-408">Additional resources</span></span>
--------

[<span data-ttu-id="5da21-409">Procesos de administración de la calidad</span><span class="sxs-lookup"><span data-stu-id="5da21-409">Quality management processes</span></span>](quality-management-processes.md)

[<span data-ttu-id="5da21-410">Gestión de disconformidad</span><span class="sxs-lookup"><span data-stu-id="5da21-410">Nonconformance management</span></span>](enable-nonconformance-management.md)

[<span data-ttu-id="5da21-411">Administración de la calidad para procesos de almacén</span><span class="sxs-lookup"><span data-stu-id="5da21-411">Quality management for warehouse processes</span></span>](quality-management-for-warehouses-processes.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]