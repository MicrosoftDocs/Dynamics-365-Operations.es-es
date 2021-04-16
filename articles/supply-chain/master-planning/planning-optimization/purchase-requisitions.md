---
title: Solicitudes de compra
description: Este tema describe cómo se admiten las solicitudes de compra en Planning Optimization.
author: ChristianRytt
ms.date: 01/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqPlanSched, ReqGroup
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2021-01-04
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 564f87fe78e79107feb103f953ed4769e4734aa1
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5808049"
---
# <a name="purchase-requisitions"></a><span data-ttu-id="3af7a-103">Solicitudes de compra</span><span class="sxs-lookup"><span data-stu-id="3af7a-103">Purchase requisitions</span></span>

<span data-ttu-id="3af7a-104">La planificación maestra puede reponer las solicitudes de compra aprobadas.</span><span class="sxs-lookup"><span data-stu-id="3af7a-104">Master planning can replenish approved purchase requisitions.</span></span> <span data-ttu-id="3af7a-105">Por lo tanto, para cubrir las solicitudes de compra, los usuarios no tienen que usar un flujo de trabajo para crear pedidos de compra.</span><span class="sxs-lookup"><span data-stu-id="3af7a-105">Therefore, to cover purchase requisitions, users don't have to use a workflow to create purchase orders.</span></span> <span data-ttu-id="3af7a-106">En cambio, las solicitudes de compra se pueden cubrir mediante la planificación maestra.</span><span class="sxs-lookup"><span data-stu-id="3af7a-106">Instead, purchase requisitions can be covered by master planning.</span></span> <span data-ttu-id="3af7a-107">Debido a esta funcionalidad, una solicitud de compra puede producir un pedido de compra, un pedido de transferencia o un pedido de producción, según el valor del **Tipo de pedido planificado** que se establece para el producto relacionado.</span><span class="sxs-lookup"><span data-stu-id="3af7a-107">Because of this functionality, a purchase requisition can produce a purchase order, a transfer order, or a production order, depending on the **Planned order type** value that is set for the related product.</span></span>

## <a name="enable-master-plans-to-include-requisitions"></a><span data-ttu-id="3af7a-108">Habilitar planes maestros para incluir solicitudes</span><span class="sxs-lookup"><span data-stu-id="3af7a-108">Enable master plans to include requisitions</span></span>

<span data-ttu-id="3af7a-109">Para incluir solicitudes durante el cálculo de cobertura para un plan maestro, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="3af7a-109">To include requisitions during the coverage calculation for a master plan, follow these steps.</span></span>

1. <span data-ttu-id="3af7a-110">Vaya a **Planificación maestra** \> **Configurar** \> **Planes** \> **Planes maestros**.</span><span class="sxs-lookup"><span data-stu-id="3af7a-110">Go to **Master planning** \> **Setup** \> **Plans** \> **Master plans**.</span></span>
1. <span data-ttu-id="3af7a-111">Seleccionar o crear un plan maestro.</span><span class="sxs-lookup"><span data-stu-id="3af7a-111">Create or select a master plan.</span></span>
1. <span data-ttu-id="3af7a-112">En la ficha desplegable **General**, configure la opción **Incluir solicitudes** en *Sí*.</span><span class="sxs-lookup"><span data-stu-id="3af7a-112">On the **General** FastTab, set the **Include requisitions** option to *Yes*.</span></span>
1. <span data-ttu-id="3af7a-113">Repita los pasos 2 y 3 para cada plan maestro adicional en el que desee incluir solicitudes.</span><span class="sxs-lookup"><span data-stu-id="3af7a-113">Repeat steps 2 and 3 for each additional master plan where you want to include requisitions.</span></span>

## <a name="approved-requisitions-time-fence"></a><span data-ttu-id="3af7a-114">Límite de tiempo de solicitudes aprobadas</span><span class="sxs-lookup"><span data-stu-id="3af7a-114">Approved requisitions time fence</span></span>

<span data-ttu-id="3af7a-115">El *Límite de tiempo de requisiciones aprobadas* establece cuánto tiempo atrás (en días) un plan maestro incluirá la demanda de las solicitudes de reabastecimiento aprobadas.</span><span class="sxs-lookup"><span data-stu-id="3af7a-115">The *approved requisitions time fence* establishes how far back (in days) a master plan will include demand from approved replenishment requisitions.</span></span> <span data-ttu-id="3af7a-116">Puede establecer un límite de tiempo para solicitudes aprobadas tanto a nivel de grupo de cobertura como a nivel de plan maestro.</span><span class="sxs-lookup"><span data-stu-id="3af7a-116">You can set an approved requisitions time fence at both the coverage group level and the master plan level.</span></span>

### <a name="set-the-approved-requisitions-time-fence-for-a-coverage-group"></a><span data-ttu-id="3af7a-117">Establecer el límite de tiempo de solicitudes aprobadas para un grupo de cobertura</span><span class="sxs-lookup"><span data-stu-id="3af7a-117">Set the approved requisitions time fence for a coverage group</span></span>

1. <span data-ttu-id="3af7a-118">Vaya a **Planificación maestra** \> **Configurar** \> **Cobertura** \> **Grupos de cobertura**.</span><span class="sxs-lookup"><span data-stu-id="3af7a-118">Go to **Master planning** \> **Setup** \> **Coverage** \> **Coverage groups**.</span></span>
1. <span data-ttu-id="3af7a-119">Cree o seleccione un grupo de cobertura.</span><span class="sxs-lookup"><span data-stu-id="3af7a-119">Create or select a coverage group.</span></span>
1. <span data-ttu-id="3af7a-120">En la ficha desplegable **Otro**, establezca el campo **Límite de tiempo de solicitudes aprobadas (días)** en el número de días que se incluirán en el límite de tiempo.</span><span class="sxs-lookup"><span data-stu-id="3af7a-120">On the **Other** FastTab, set the **Approved requisitions time fence (days)** field to the number of days to include in the time fence.</span></span>
1. <span data-ttu-id="3af7a-121">Repita los pasos 2 y 3 para cada grupo de cobertura adicional en el que desee establecer un límite de tiempo para solicitudes aprobadas.</span><span class="sxs-lookup"><span data-stu-id="3af7a-121">Repeat steps 2 and 3 for each additional coverage group where you want to set an approved requisitions time fence.</span></span>

### <a name="set-the-approved-requisitions-time-fence-for-individual-master-plans"></a><span data-ttu-id="3af7a-122">Establecer el límite de tiempo de solicitudes aprobadas para un plan maestro individual</span><span class="sxs-lookup"><span data-stu-id="3af7a-122">Set the approved requisitions time fence for individual master plans</span></span>

<span data-ttu-id="3af7a-123">Cuando establece un límite de tiempo de solicitudes aprobado para un plan maestro individual, la configuración anula la configuración de límite de tiempo para cualquier grupo de cobertura aplicable.</span><span class="sxs-lookup"><span data-stu-id="3af7a-123">When you set an approved requisitions time fence for an individual master plan, the setting overrides the time fence setting for any applicable coverage group.</span></span>

1. <span data-ttu-id="3af7a-124">Vaya a **Planificación maestra** \> **Configurar** \> **Planes** \> **Planes maestros**.</span><span class="sxs-lookup"><span data-stu-id="3af7a-124">Go to **Master planning** \> **Setup** \> **Plans** \> **Master plans**.</span></span>
1. <span data-ttu-id="3af7a-125">Seleccionar o crear un plan maestro.</span><span class="sxs-lookup"><span data-stu-id="3af7a-125">Create or select a master plan.</span></span>
1. <span data-ttu-id="3af7a-126">En la ficha desplegable **Límites de tiempo en días**, establezca el campo **Límite de tiempo de solicitudes aprobadas (días)** en el número de días que se incluirán en el límite de tiempo.</span><span class="sxs-lookup"><span data-stu-id="3af7a-126">On the **TIme fences in days** FastTab, set the **Approved requisitions time fence (days)** field to the number of days to include in the time fence.</span></span>
1. <span data-ttu-id="3af7a-127">Repita los pasos 2 y 3 para cada plan maestro adicional en el que desee establecer un límite de tiempo para solicitudes aprobadas.</span><span class="sxs-lookup"><span data-stu-id="3af7a-127">Repeat steps 2 and 3 for each additional master plan where you want to set an approved requisitions time fence.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3af7a-128">**Próximamente:** Los límites de tiempo de solicitudes aprobadas aún no son compatibles con Planning Optimization.</span><span class="sxs-lookup"><span data-stu-id="3af7a-128">**Coming soon:** Approved requisitions time fences aren't yet supported for Planning Optimization.</span></span> <span data-ttu-id="3af7a-129">Hasta que sean compatibles, todos los valores que ingrese en el campo **Límite de tiempo de solicitudes aprobadas (días)** se ignorará.</span><span class="sxs-lookup"><span data-stu-id="3af7a-129">Until they are supported, all values that you enter in the **Approved requisitions time fence (days)** field will be ignored.</span></span>

## <a name="independent-supply-regardless-of-coverage-code"></a><span data-ttu-id="3af7a-130">Suministro independiente, independientemente del código de cobertura</span><span class="sxs-lookup"><span data-stu-id="3af7a-130">Independent supply, regardless of coverage code</span></span>

<span data-ttu-id="3af7a-131">Las solicitudes de compra siempre están cubiertas por pedidos planificados independientes, independientemente del código de cobertura.</span><span class="sxs-lookup"><span data-stu-id="3af7a-131">Purchase requisitions are always covered by independent planned orders, regardless of the coverage code.</span></span> <span data-ttu-id="3af7a-132">Este comportamiento asegura una trazabilidad clara y flujos de trabajo entre las solicitudes de compra y los pedidos de reabastecimiento.</span><span class="sxs-lookup"><span data-stu-id="3af7a-132">This behavior ensures clear traceability and workflows between purchase requisitions and replenishment orders.</span></span>

### <a name="example-1"></a><span data-ttu-id="3af7a-133">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="3af7a-133">Example 1</span></span>

<span data-ttu-id="3af7a-134">Un producto está configurado para que tenga un valor de **Código de cobertura** de *Mínimo/máximo*. Tiene los siguientes estados de inventario y solicitud:</span><span class="sxs-lookup"><span data-stu-id="3af7a-134">A product is set up so that it has a **Coverage code** value of *Min/max*. It has the following inventory and requisition statuses:</span></span>

- <span data-ttu-id="3af7a-135">Cantidad de inventario disponible = 10.</span><span class="sxs-lookup"><span data-stu-id="3af7a-135">Inventory on-hand quantity = 10.</span></span>
- <span data-ttu-id="3af7a-136">Cantidad de inventario mínima = 15.</span><span class="sxs-lookup"><span data-stu-id="3af7a-136">Minimum inventory quantity = 15.</span></span>
- <span data-ttu-id="3af7a-137">Cantidad de inventario máxima = 20.</span><span class="sxs-lookup"><span data-stu-id="3af7a-137">Maximum inventory quantity = 20.</span></span>
- <span data-ttu-id="3af7a-138">Existe una solicitud de compra para una pieza.</span><span class="sxs-lookup"><span data-stu-id="3af7a-138">A purchase requisition for one piece exists.</span></span> <span data-ttu-id="3af7a-139">Tiene una fecha solicitada de hoy.</span><span class="sxs-lookup"><span data-stu-id="3af7a-139">It has a requested date of today.</span></span>

<span data-ttu-id="3af7a-140">Cuando se ejecuta la planificación maestra, se crean dos órdenes planificadas: una para 10 piezas para reabastecer el inventario hasta la cantidad máxima y otra para una pieza para reabastecer la solicitud de compra.</span><span class="sxs-lookup"><span data-stu-id="3af7a-140">When master planning runs, two planned orders are created: one for 10 pieces to replenish inventory to the maximum quantity, and one for one piece to replenish the purchase requisition.</span></span>

### <a name="example-2"></a><span data-ttu-id="3af7a-141">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="3af7a-141">Example 2</span></span>

<span data-ttu-id="3af7a-142">Un producto está configurado para que tenga un valor de **Código de cobertura** de *Mínimo/máximo*. Tiene los siguientes estados de inventario y solicitud:</span><span class="sxs-lookup"><span data-stu-id="3af7a-142">A product is set up so that it has a **Coverage code** value of *Min/max*. It has the following inventory and requisition statuses:</span></span>

- <span data-ttu-id="3af7a-143">Cantidad de inventario disponible = 17.</span><span class="sxs-lookup"><span data-stu-id="3af7a-143">Inventory on-hand quantity = 17.</span></span>
- <span data-ttu-id="3af7a-144">Cantidad de inventario mínima = 15.</span><span class="sxs-lookup"><span data-stu-id="3af7a-144">Minimum inventory quantity = 15.</span></span>
- <span data-ttu-id="3af7a-145">Cantidad de inventario máxima = 20.</span><span class="sxs-lookup"><span data-stu-id="3af7a-145">Maximum inventory quantity = 20.</span></span>
- <span data-ttu-id="3af7a-146">Existe una solicitud de compra para una pieza.</span><span class="sxs-lookup"><span data-stu-id="3af7a-146">A purchase requisition for one piece exists.</span></span> <span data-ttu-id="3af7a-147">Tiene una fecha solicitada de hoy.</span><span class="sxs-lookup"><span data-stu-id="3af7a-147">It has a requested date of today.</span></span>

<span data-ttu-id="3af7a-148">Cuando se ejecuta la planificación maestra, se crea un pedido planificado para una pieza para reponer la solicitud de compra.</span><span class="sxs-lookup"><span data-stu-id="3af7a-148">When master planning runs, one planned order for one piece is created to replenish the purchase requisition.</span></span>

### <a name="example-3"></a><span data-ttu-id="3af7a-149">Ejemplo 3</span><span class="sxs-lookup"><span data-stu-id="3af7a-149">Example 3</span></span>

<span data-ttu-id="3af7a-150">Un producto está configurado para que tenga un valor de **Código de cobertura** de *Período* y una duración del período de siete días.</span><span class="sxs-lookup"><span data-stu-id="3af7a-150">A product is set up so that it has a **Coverage code** value of *Period* and a period length of seven days.</span></span> <span data-ttu-id="3af7a-151">Tiene los siguientes estados de inventario, pedido de ventas y solicitud:</span><span class="sxs-lookup"><span data-stu-id="3af7a-151">It has the following inventory, sales order, and requisition statuses:</span></span>

- <span data-ttu-id="3af7a-152">Cantidad de inventario disponible = 0.</span><span class="sxs-lookup"><span data-stu-id="3af7a-152">Inventory on-hand quantity = 0.</span></span>
- <span data-ttu-id="3af7a-153">Existe un pedido de venta de cinco piezas.</span><span class="sxs-lookup"><span data-stu-id="3af7a-153">A sales order for five pieces exists.</span></span> <span data-ttu-id="3af7a-154">Tiene una fecha de envío prevista de hoy más un día.</span><span class="sxs-lookup"><span data-stu-id="3af7a-154">It has an expected ship date of today plus one day.</span></span>
- <span data-ttu-id="3af7a-155">Existe una solicitud de compra para tres piezas.</span><span class="sxs-lookup"><span data-stu-id="3af7a-155">A purchase requisition for three pieces exists.</span></span> <span data-ttu-id="3af7a-156">Tiene una fecha solicitada de hoy más tres días.</span><span class="sxs-lookup"><span data-stu-id="3af7a-156">It has a requested date of today plus three days.</span></span>

<span data-ttu-id="3af7a-157">Cuando se ejecuta la planificación maestra, se crean dos órdenes planificadas: una para tres piezas para reabastecer la solicitud de compra y una para cinco piezas para reabastecer la demanda del pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="3af7a-157">When master planning runs, two planned orders are created: one for three pieces to replenish the purchase requisition and one for five pieces to replenish sales order demand.</span></span>

> [!NOTE]
> <span data-ttu-id="3af7a-158">Después de que se firme una orden planificada que está vinculada a una solicitud de compra, el motor de planificación mantiene el diagrama de árbol a la solicitud de compra.</span><span class="sxs-lookup"><span data-stu-id="3af7a-158">After a planned order that is pegged to a purchase requisition is firmed, the planning engine keeps the pegging to the purchase requisition.</span></span> <span data-ttu-id="3af7a-159">Si posteriormente se descubre que en el pedido firme falta alguna cantidad necesaria para cumplir con la solicitud de compra, el sistema creará un nuevo pedido planificado por la diferencia.</span><span class="sxs-lookup"><span data-stu-id="3af7a-159">If the firmed order is later found to be missing some quantity that is required to fulfill the purchase requisition, the system will create a new planned order for the difference.</span></span>

<span data-ttu-id="3af7a-160">Para obtener más información sobre las solicitudes de compra, consulte [Descripción general de la solicitud de compra](../../procurement/purchase-requisitions-overview.md).</span><span class="sxs-lookup"><span data-stu-id="3af7a-160">For more information about purchase requisitions, see [Purchase requisition overview](../../procurement/purchase-requisitions-overview.md).</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]