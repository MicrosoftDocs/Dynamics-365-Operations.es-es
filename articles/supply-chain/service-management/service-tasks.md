---
title: Visión general de las tareas de servicio
description: Utilice tareas de servicios para describir la tarea que hay que realizar durante un pedido de servicio. Tanto técnicos como clientes pueden ver esta información.
author: ShylaThompson
manager: tfehr
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceTask
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c2864b481c67c078df73436d752069a6b6c78640
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2020
ms.locfileid: "3206044"
---
# <a name="service-tasks-overview"></a><span data-ttu-id="5a517-104">Visión general de las tareas de servicio</span><span class="sxs-lookup"><span data-stu-id="5a517-104">Service tasks overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5a517-105">Utilice tareas de servicios para describir la tarea que hay que realizar durante un pedido de servicio.</span><span class="sxs-lookup"><span data-stu-id="5a517-105">Use service tasks to describe the task to be completed during a service order.</span></span>
<span data-ttu-id="5a517-106">Tanto técnicos como clientes pueden ver esta información.</span><span class="sxs-lookup"><span data-stu-id="5a517-106">Both technicians and customers can see this information.</span></span>

<span data-ttu-id="5a517-107">Crea tareas de servicio en la página **Tareas de servicio** y asocia tareas de servicio a un contrato de servicio o pedido de servicio específico creando relaciones de tareas de servicio.</span><span class="sxs-lookup"><span data-stu-id="5a517-107">You create service tasks in the **Service tasks** page, and you associate service tasks with a specific service agreement or service order by creating service task relations.</span></span> <span data-ttu-id="5a517-108">Cada vez que crea una relación de tarea de servicio, puede crear:</span><span class="sxs-lookup"><span data-stu-id="5a517-108">Every time that you create a service task relation, you can create the following:</span></span>

-  <span data-ttu-id="5a517-109">Notas internas para la tarea, como solicitudes técnicas detalladas para la tarea que es importante que conozca el técnico.</span><span class="sxs-lookup"><span data-stu-id="5a517-109">Internal notes for the task, such as detailed technical requests for the task that are important for the technician to know.</span></span>

-  <span data-ttu-id="5a517-110">Notas externas que puede ver el cliente.</span><span class="sxs-lookup"><span data-stu-id="5a517-110">External notes that the customer can see.</span></span> <span data-ttu-id="5a517-111">Pueden proporcionar una explicación menos técnica de la tarea que se está realizando, de contrato con el contrato entre el cliente y la empresa de servicios.</span><span class="sxs-lookup"><span data-stu-id="5a517-111">These might provide a less technical explanation of the task that is being completed, according to the agreement between the customer and the service company.</span></span>

<span data-ttu-id="5a517-112">Una vez que haya configurado una relación de tarea de servicio entre una tarea de servicio y un pedido de servicio o un acuerdo de servicio, puede especificar esta tarea de servicio al crear líneas de pedido de servicio o líneas de acuerdo de servicio para el pedido de servicio o el acuerdo de servicio actual.</span><span class="sxs-lookup"><span data-stu-id="5a517-112">When you have set up a service task relation between a service task and a service order or service agreement, you can specify this service task when you create service order lines or service agreement lines for the current service order or service agreement.</span></span>

<span data-ttu-id="5a517-113">Al generar pedidos de servicio a partir de un acuerdo de servicio, puede usar las tareas de servicio asignadas a cada línea de acuerdo de servicio para agrupar las líneas de pedido de servicio en pedidos de servicio.</span><span class="sxs-lookup"><span data-stu-id="5a517-113">When you generate service orders from a service agreement, you can use the service tasks that are assigned to each service agreement line to group service order lines into service orders.</span></span>

## <a name="create-a-service-task"></a><span data-ttu-id="5a517-114">Crear a tarea de servicio</span><span class="sxs-lookup"><span data-stu-id="5a517-114">Create a service task</span></span>

1. <span data-ttu-id="5a517-115">Haga clic en **Gestión de servicio** \> **Configuración** \> **Tareas de servicio**.</span><span class="sxs-lookup"><span data-stu-id="5a517-115">Click **Service management** \> **Setup** \> **Service tasks**.</span></span>
2. <span data-ttu-id="5a517-116">Cree una línea nueva.</span><span class="sxs-lookup"><span data-stu-id="5a517-116">Create a new line.</span></span>
3. <span data-ttu-id="5a517-117">Especifique el id. del servicio y su descripción.</span><span class="sxs-lookup"><span data-stu-id="5a517-117">Enter the service ID and description.</span></span>

## <a name="example"></a><span data-ttu-id="5a517-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5a517-118">Example</span></span>

<span data-ttu-id="5a517-119">Un técnico debe realizar dos trabajos en una caja de cambios (objeto de servicio GB-1234) en un sitio de cliente.</span><span class="sxs-lookup"><span data-stu-id="5a517-119">A technician must complete two jobs on a gearbox (service object GB-1234) at a customer site.</span></span> <span data-ttu-id="5a517-120">Se crea un acuerdo de servicio para el cliente y varias transacciones se asocian a los trabajos.</span><span class="sxs-lookup"><span data-stu-id="5a517-120">A service agreement is created for the customer, and several transactions are associated with the jobs.</span></span> <span data-ttu-id="5a517-121">A continuación se muestra el acuerdo de servicio y las líneas de acuerdo de servicio para los dos trabajos:</span><span class="sxs-lookup"><span data-stu-id="5a517-121">The service agreement and service agreement lines for the two jobs are as follows:</span></span>

### <a name="service-agreement"></a><span data-ttu-id="5a517-122">Acuerdo de servicio</span><span class="sxs-lookup"><span data-stu-id="5a517-122">Service agreement</span></span>

| <span data-ttu-id="5a517-123">Project</span><span class="sxs-lookup"><span data-stu-id="5a517-123">Project</span></span> | <span data-ttu-id="5a517-124">Acuerdo de servicio</span><span class="sxs-lookup"><span data-stu-id="5a517-124">Service agreement</span></span> | <span data-ttu-id="5a517-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="5a517-125">Description</span></span>                                  | <span data-ttu-id="5a517-126">Grupo</span><span class="sxs-lookup"><span data-stu-id="5a517-126">Group</span></span>   |
|---------|-------------------|----------------------------------------------|---------|
| <span data-ttu-id="5a517-127">9012</span><span class="sxs-lookup"><span data-stu-id="5a517-127">9012</span></span>    | <span data-ttu-id="5a517-128">000008\_001</span><span class="sxs-lookup"><span data-stu-id="5a517-128">000008\_001</span></span>       | <span data-ttu-id="5a517-129">Inspección y sustitución de rutina – GB-1234</span><span class="sxs-lookup"><span data-stu-id="5a517-129">Inspection and routine replacement – GB-1234</span></span> | <span data-ttu-id="5a517-130">Bonificación</span><span class="sxs-lookup"><span data-stu-id="5a517-130">Premium</span></span> |

### <a name="service-agreement-lines"></a><span data-ttu-id="5a517-131">Líneas de acuerdo de servicio</span><span class="sxs-lookup"><span data-stu-id="5a517-131">Service agreement lines</span></span>

| <span data-ttu-id="5a517-132">Descripción</span><span class="sxs-lookup"><span data-stu-id="5a517-132">Description</span></span>             | <span data-ttu-id="5a517-133">Tipo de transacción</span><span class="sxs-lookup"><span data-stu-id="5a517-133">Transaction type</span></span> | <span data-ttu-id="5a517-134">Objeto de servicio</span><span class="sxs-lookup"><span data-stu-id="5a517-134">Service object</span></span> | <span data-ttu-id="5a517-135">Tarea de servicio</span><span class="sxs-lookup"><span data-stu-id="5a517-135">Service task</span></span> |
|-------------------------|------------------|----------------|--------------|
| <span data-ttu-id="5a517-136">Inspección y limpieza</span><span class="sxs-lookup"><span data-stu-id="5a517-136">Inspection and cleaning</span></span> | <span data-ttu-id="5a517-137">Hora</span><span class="sxs-lookup"><span data-stu-id="5a517-137">Hour</span></span>             | <span data-ttu-id="5a517-138">GB-1234</span><span class="sxs-lookup"><span data-stu-id="5a517-138">GB-1234</span></span>        | <span data-ttu-id="5a517-139">I/C - GB1234</span><span class="sxs-lookup"><span data-stu-id="5a517-139">I/C - GB1234</span></span> |
| <span data-ttu-id="5a517-140">Viajes</span><span class="sxs-lookup"><span data-stu-id="5a517-140">Travel</span></span>                  | <span data-ttu-id="5a517-141">Expense</span><span class="sxs-lookup"><span data-stu-id="5a517-141">Expense</span></span>          | <span data-ttu-id="5a517-142">GB-1234</span><span class="sxs-lookup"><span data-stu-id="5a517-142">GB-1234</span></span>        | <span data-ttu-id="5a517-143">I/C - GB1234</span><span class="sxs-lookup"><span data-stu-id="5a517-143">I/C - GB1234</span></span> |
| <span data-ttu-id="5a517-144">Materiales</span><span class="sxs-lookup"><span data-stu-id="5a517-144">Materials</span></span>               | <span data-ttu-id="5a517-145">Artículo</span><span class="sxs-lookup"><span data-stu-id="5a517-145">Item</span></span>             | <span data-ttu-id="5a517-146">GB-1234</span><span class="sxs-lookup"><span data-stu-id="5a517-146">GB-1234</span></span>        | <span data-ttu-id="5a517-147">I/C - GB1234</span><span class="sxs-lookup"><span data-stu-id="5a517-147">I/C - GB1234</span></span> |
| <span data-ttu-id="5a517-148">Sustitución de rutina</span><span class="sxs-lookup"><span data-stu-id="5a517-148">Routine replacement</span></span>     | <span data-ttu-id="5a517-149">Hora</span><span class="sxs-lookup"><span data-stu-id="5a517-149">Hour</span></span>             | <span data-ttu-id="5a517-150">GB-1234</span><span class="sxs-lookup"><span data-stu-id="5a517-150">GB-1234</span></span>        | <span data-ttu-id="5a517-151">RR - GB1234</span><span class="sxs-lookup"><span data-stu-id="5a517-151">RR - GB1234</span></span>  |
| <span data-ttu-id="5a517-152">GR-1</span><span class="sxs-lookup"><span data-stu-id="5a517-152">GR-1</span></span>                    | <span data-ttu-id="5a517-153">Artículo</span><span class="sxs-lookup"><span data-stu-id="5a517-153">Item</span></span>             | <span data-ttu-id="5a517-154">GB-1234</span><span class="sxs-lookup"><span data-stu-id="5a517-154">GB-1234</span></span>        | <span data-ttu-id="5a517-155">RR - GB1234</span><span class="sxs-lookup"><span data-stu-id="5a517-155">RR - GB1234</span></span>  |
| <span data-ttu-id="5a517-156">GR-5</span><span class="sxs-lookup"><span data-stu-id="5a517-156">GR-5</span></span>                    | <span data-ttu-id="5a517-157">Artículo</span><span class="sxs-lookup"><span data-stu-id="5a517-157">Item</span></span>             | <span data-ttu-id="5a517-158">GB-1234</span><span class="sxs-lookup"><span data-stu-id="5a517-158">GB-1234</span></span>        | <span data-ttu-id="5a517-159">RR - GB1234</span><span class="sxs-lookup"><span data-stu-id="5a517-159">RR - GB1234</span></span>  |

<span data-ttu-id="5a517-160">Las líneas de acuerdo de servicio para los dos trabajos tienen dos tareas de servicio vinculadas.</span><span class="sxs-lookup"><span data-stu-id="5a517-160">The service agreement lines for the two jobs have two service tasks attached to them.</span></span> <span data-ttu-id="5a517-161">Las tareas de servicio determinan las transacciones que pertenecen a cada trabajo.</span><span class="sxs-lookup"><span data-stu-id="5a517-161">The service tasks determine the transactions that belong to each job.</span></span> <span data-ttu-id="5a517-162">En el primer caso, la tarea de servicio I/C - GB1234 identifica todas las líneas de acuerdo de servicio implicadas en la inspección y limpieza del objeto GB-1234.</span><span class="sxs-lookup"><span data-stu-id="5a517-162">In the first case, service task I/C - GB1234 identifies all the service agreement lines that are involved in the inspection and cleaning of object GB-1234.</span></span> <span data-ttu-id="5a517-163">En el segundo caso, la tarea de servicio RR - GB1234 identifica todas las líneas de acuerdo de servicio implicadas en la finalización de un trabajo de sustitución de rutina.</span><span class="sxs-lookup"><span data-stu-id="5a517-163">In the second case, service task RR - GB1234 identifies all the service agreement lines that are involved in completing a routine replacement job.</span></span>

<span data-ttu-id="5a517-164">Las relaciones de tareas de servicio que conectan las tareas de servicio con el contrato específico son como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="5a517-164">The service task relations that connect the service tasks to the specific agreement are as follows:</span></span>

### <a name="service-tasks"></a><span data-ttu-id="5a517-165">Tareas de servicio</span><span class="sxs-lookup"><span data-stu-id="5a517-165">Service tasks</span></span>

| <span data-ttu-id="5a517-166">Tarea de servicio</span><span class="sxs-lookup"><span data-stu-id="5a517-166">Service task</span></span> | <span data-ttu-id="5a517-167">Descripción</span><span class="sxs-lookup"><span data-stu-id="5a517-167">Description</span></span>                             | <span data-ttu-id="5a517-168">Nota interna</span><span class="sxs-lookup"><span data-stu-id="5a517-168">Internal note</span></span>                                                                                                                 | <span data-ttu-id="5a517-169">Nota externa</span><span class="sxs-lookup"><span data-stu-id="5a517-169">External note</span></span>                 |
|--------------|-----------------------------------------|-------------------------------------------------------------------------------------------------------------------------------|-------------------------------|
| <span data-ttu-id="5a517-170">I/C - GB1234</span><span class="sxs-lookup"><span data-stu-id="5a517-170">I/C - GB1234</span></span> | <span data-ttu-id="5a517-171">Inspección de la caja de cambios GB-1234</span><span class="sxs-lookup"><span data-stu-id="5a517-171">Inspection of gearbox GB-1234</span></span>           | <span data-ttu-id="5a517-172">Inspección visual y mecánica y limpieza de la caja de cambios GB-1234</span><span class="sxs-lookup"><span data-stu-id="5a517-172">Visual and mechanical inspection and cleaning of gearbox GB-1234</span></span>                                                              | <span data-ttu-id="5a517-173">Inspección de rutina de la caja de cambios</span><span class="sxs-lookup"><span data-stu-id="5a517-173">Routine inspection of gearbox</span></span> |
| <span data-ttu-id="5a517-174">RR - GB1234</span><span class="sxs-lookup"><span data-stu-id="5a517-174">RR - GB1234</span></span>  | <span data-ttu-id="5a517-175">Sustitución de rutina de piezas en GB-1234</span><span class="sxs-lookup"><span data-stu-id="5a517-175">Routine replacement of parts in GB-1234</span></span> | <span data-ttu-id="5a517-176">Sustitución de servicio de rutina de componentes de GR-1 y GR-5 (para cajas de cambio fabricadas antes de 2002, sustituir también el componente GR-2)</span><span class="sxs-lookup"><span data-stu-id="5a517-176">Routine service replacement of GR-1 and GR-5 components (for gearboxes manufactured before 2002, also replace GR-2 component)</span></span> | <span data-ttu-id="5a517-177">Sustitución de piezas de rutina</span><span class="sxs-lookup"><span data-stu-id="5a517-177">Routine replacement of parts</span></span>  |

## <a name="group-service-orders"></a><span data-ttu-id="5a517-178">Agrupar pedidos de servicio</span><span class="sxs-lookup"><span data-stu-id="5a517-178">Group service orders</span></span>

<span data-ttu-id="5a517-179">Al crear pedidos de servicio automáticamente, puede usar las tareas de servicio como criterio de agrupación.</span><span class="sxs-lookup"><span data-stu-id="5a517-179">When you create service orders automatically, you can use service tasks as grouping criteria.</span></span> <span data-ttu-id="5a517-180">Para agrupar pedidos de servicios por tareas de servicio, defina el acuerdo de servicio que los pedidos de servicio basados en el acuerdo de servicio deben agruparse por identificador de tarea de servicio como criterio de agrupación inicial.</span><span class="sxs-lookup"><span data-stu-id="5a517-180">To group service orders by service tasks, define on the service agreement that service orders that are based on the service agreement should be grouped by service task ID as their initial grouping criteria.</span></span>

<span data-ttu-id="5a517-181">**Agrupar por tarea de servicio**</span><span class="sxs-lookup"><span data-stu-id="5a517-181">**Group by service task**</span></span>

1. <span data-ttu-id="5a517-182">Haga clic en **Gestión de servicio** \> **Común** \> **Contratos de servicio** \> **Contratos de servicio**.</span><span class="sxs-lookup"><span data-stu-id="5a517-182">Click **Service management** \> **Common** \> **Service agreements** \> **Service agreements**.</span></span>
2. <span data-ttu-id="5a517-183">En la pestaña **Configuración**, seleccione **Por tarea de servicio** en el campo **Combinar pedidos de servicio** .</span><span class="sxs-lookup"><span data-stu-id="5a517-183">On the **Setup** tab, select **By service task** in the **Combine service orders** field.</span></span>


