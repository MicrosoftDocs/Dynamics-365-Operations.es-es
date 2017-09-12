--- 
title: "Crear una regla kanban de eventos de línea de L. MAT."
description: "Esta tarea se centra en la configuración necesaria para crear una regla kanban de evento para asegurar el suministro de las líneas de L. MAT de producción en un entorno mixto de producción lean y clásico."
author: ChristianRytt
manager: AnnBe
ms.date: 11/07/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 452cc5cf6060b71f91ad43e39e756dc23d759448
ms.contentlocale: es-es
ms.lasthandoff: 08/29/2017

---
# <a name="create-a-bom-line-event-kanban-rule"></a><span data-ttu-id="ab516-103">Crear una regla kanban de eventos de línea de L. MAT.</span><span class="sxs-lookup"><span data-stu-id="ab516-103">Create a BOM line event kanban rule</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="ab516-104">Esta tarea se centra en la configuración necesaria para crear una regla kanban de evento para asegurar el suministro de las líneas de L. MAT de producción en un entorno mixto de producción lean y clásico.</span><span class="sxs-lookup"><span data-stu-id="ab516-104">This task focuses on the setup needed to create an event kanban rule to ensure supply for production BOM lines in a mixed lean and classic production environment.</span></span> <span data-ttu-id="ab516-105">La empresa de datos de prueba utilizada para crear esta tarea es USMF.</span><span class="sxs-lookup"><span data-stu-id="ab516-105">The demo data company used to create this task is USMF.</span></span> <span data-ttu-id="ab516-106">Esta tarea está pensada para el ingeniero de procesos o el administrador de flujo de valor, ya que preparan la producción de un producto nuevo o modificado.</span><span class="sxs-lookup"><span data-stu-id="ab516-106">This task is intended for the process engineer or the value stream manager, as they prepare production of a new or modified product.</span></span>


## <a name="create-a-new-kanban-rule"></a><span data-ttu-id="ab516-107">Crear una nueva regla kanban</span><span class="sxs-lookup"><span data-stu-id="ab516-107">Create a new kanban rule</span></span>
1. <span data-ttu-id="ab516-108">Vaya a Control de producción > Tareas periódicas > Cálculo de cantidad kanban > Reglas kanban.</span><span class="sxs-lookup"><span data-stu-id="ab516-108">Go to Production control > Periodic tasks > Kanban quantity calculation > Kanban rules.</span></span>
2. <span data-ttu-id="ab516-109">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="ab516-109">Click New.</span></span>
3. <span data-ttu-id="ab516-110">En el campo Tipo, seleccione "Retirada".</span><span class="sxs-lookup"><span data-stu-id="ab516-110">In the Type field, select 'Withdrawal'.</span></span>
    * <span data-ttu-id="ab516-111">El tipo Retirada se usa para crear kanbans de transferencia.</span><span class="sxs-lookup"><span data-stu-id="ab516-111">The Withdrawal type is used to create transfer kanbans.</span></span>  
4. <span data-ttu-id="ab516-112">En el campo Estrategia de reabastecimiento, seleccione "Evento".</span><span class="sxs-lookup"><span data-stu-id="ab516-112">In the Replenishment strategy field, select 'Event'.</span></span>
    * <span data-ttu-id="ab516-113">La estrategia de evento se selecciona para crear la transferencia de los kanbans basados en un evento.</span><span class="sxs-lookup"><span data-stu-id="ab516-113">The Event strategy is selected to create the transfer of kanbans based on an event.</span></span> <span data-ttu-id="ab516-114">Más adelante en la guía de tareas, lo desencadenaremos calculando un pedido de producción.</span><span class="sxs-lookup"><span data-stu-id="ab516-114">Later in the task guide, we will trigger it by estimating a production order.</span></span>  
5. <span data-ttu-id="ab516-115">En el campo Actividad del primer plan, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="ab516-115">In the First plan activity field, enter or select a value.</span></span>
    * <span data-ttu-id="ab516-116">Especifique o seleccione ReplenishSpeakerComponents.</span><span class="sxs-lookup"><span data-stu-id="ab516-116">Enter or select ReplenishSpeakerComponents.</span></span> <span data-ttu-id="ab516-117">Esta actividad de transferencia tiene el almacén de recepción (salida) y ubicación 12, lo que significa que el material se moverá a la ubicación 12 del almacén 12.</span><span class="sxs-lookup"><span data-stu-id="ab516-117">This transfer activity has receipt (output) warehouse and location 12, which means that material will be moved to location 12 in warehouse 12.</span></span>  
6. <span data-ttu-id="ab516-118">Expanda la sección Detalles.</span><span class="sxs-lookup"><span data-stu-id="ab516-118">Expand the Details section.</span></span>
7. <span data-ttu-id="ab516-119">En el campo Producto, especifique o seleccione M0001.</span><span class="sxs-lookup"><span data-stu-id="ab516-119">In the Product field, enter or select M0001.</span></span>
8. <span data-ttu-id="ab516-120">Expanda la sección Eventos.</span><span class="sxs-lookup"><span data-stu-id="ab516-120">Expand the Events section.</span></span>
9. <span data-ttu-id="ab516-121">En el campo Evento de línea de L. MAT, seleccione "Automático".</span><span class="sxs-lookup"><span data-stu-id="ab516-121">In the BOM line event field, select 'Automatic'.</span></span>
    * <span data-ttu-id="ab516-122">Con el campo Evento de línea de L. MAT establecido en Automático, el kanban se creará para satisfacer las necesidades de material para las líneas de L. MAT del pedido de producción.</span><span class="sxs-lookup"><span data-stu-id="ab516-122">With the BOM line event field set to Automatic, kanban will be created to fulfill material needs for production order BOM lines.</span></span>  
10. <span data-ttu-id="ab516-123">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="ab516-123">Close the page.</span></span>

## <a name="create-and-modify-a-new-production-order"></a><span data-ttu-id="ab516-124">Crear y modificar una nueva orden de producción</span><span class="sxs-lookup"><span data-stu-id="ab516-124">Create and modify a new production order</span></span>
1. <span data-ttu-id="ab516-125">Vaya a Control de producción > Pedidos de producción > Todos los pedidos de producción.</span><span class="sxs-lookup"><span data-stu-id="ab516-125">Go to Production control > Production orders > All production orders.</span></span>
2. <span data-ttu-id="ab516-126">Haga clic en Nuevo pedido de producción.</span><span class="sxs-lookup"><span data-stu-id="ab516-126">Click New production order.</span></span>
3. <span data-ttu-id="ab516-127">En el campo Número de artículo, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="ab516-127">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="ab516-128">Escriba o seleccione “L0001”.</span><span class="sxs-lookup"><span data-stu-id="ab516-128">Enter or select 'L0001'.</span></span> <span data-ttu-id="ab516-129">Usamos el artículo L0001 porque el artículo M0001 se incluye en la L. MAT para el artículo L0001.</span><span class="sxs-lookup"><span data-stu-id="ab516-129">We use item L0001 because item M0001 is included in the BOM for item L0001.</span></span>  
4. <span data-ttu-id="ab516-130">Haga clic en Crear.</span><span class="sxs-lookup"><span data-stu-id="ab516-130">Click Create.</span></span>
5. <span data-ttu-id="ab516-131">En la lista, haga clic en el vínculo de la fila para L0001</span><span class="sxs-lookup"><span data-stu-id="ab516-131">In the list, click the link in the row for L0001</span></span>
6. <span data-ttu-id="ab516-132">Haga clic en L. MAT.</span><span class="sxs-lookup"><span data-stu-id="ab516-132">Click BOM.</span></span>
7. <span data-ttu-id="ab516-133">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="ab516-133">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="ab516-134">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="ab516-134">Click Edit.</span></span>
9. <span data-ttu-id="ab516-135">En el campo Tipo de línea, seleccione "Suministro asegurado".</span><span class="sxs-lookup"><span data-stu-id="ab516-135">In the Line type field, select 'Pegged supply'.</span></span>
    * <span data-ttu-id="ab516-136">El suministro asegurado se selecciona para desencadenar la creación de la suministro de un kanban.</span><span class="sxs-lookup"><span data-stu-id="ab516-136">Pegged supply is selected to trigger the supply creation of a kanban.</span></span>  
10. <span data-ttu-id="ab516-137">Seleccione No en el campo Consumo del recurso.</span><span class="sxs-lookup"><span data-stu-id="ab516-137">Select No in the Resource consumption field.</span></span>
    * <span data-ttu-id="ab516-138">La desactivación de la casilla Consumo del recurso nos permite cambiar el almacén.</span><span class="sxs-lookup"><span data-stu-id="ab516-138">Clearing the check box of Resource consumption lets us change the warehouse.</span></span>  
11. <span data-ttu-id="ab516-139">Expanda la sección Dimensiones de inventario.</span><span class="sxs-lookup"><span data-stu-id="ab516-139">Expand the Inventory dimensions section.</span></span>
12. <span data-ttu-id="ab516-140">En el campo Almacén, escriba "12".</span><span class="sxs-lookup"><span data-stu-id="ab516-140">In the Warehouse field, type '12'.</span></span>
    * <span data-ttu-id="ab516-141">El almacén se establece en 12 porque este es el almacén de salida para la actividad de retirada.</span><span class="sxs-lookup"><span data-stu-id="ab516-141">Warehouse is set to 12 because this is the output warehouse for the withdrawal activity.</span></span>  
13. <span data-ttu-id="ab516-142">En el campo Ubicación, escriba "12".</span><span class="sxs-lookup"><span data-stu-id="ab516-142">In the Location field, type '12'.</span></span>
    * <span data-ttu-id="ab516-143">La ubicación se establece en 12 porque este es la ubicación de salida de la actividad de retirada.</span><span class="sxs-lookup"><span data-stu-id="ab516-143">Location is set to 12 because this is the output location of the withdrawal activity.</span></span>  
14. <span data-ttu-id="ab516-144">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="ab516-144">Close the page.</span></span>
15. <span data-ttu-id="ab516-145">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="ab516-145">Close the page.</span></span>

## <a name="estimate-the-production-order-and-view-the-kanban-created"></a><span data-ttu-id="ab516-146">Calcular el pedido de producción y ver el kanban creado</span><span class="sxs-lookup"><span data-stu-id="ab516-146">Estimate the production order and view the kanban created</span></span>
1. <span data-ttu-id="ab516-147">Haga clic en Estimación.</span><span class="sxs-lookup"><span data-stu-id="ab516-147">Click Estimate.</span></span>
    * <span data-ttu-id="ab516-148">El cálculo del pedido de producción desencadenará la creación del kanban asociado para suministrar el artículo M0001.</span><span class="sxs-lookup"><span data-stu-id="ab516-148">Estimating the production order will trigger the creation of the associated kanban to supply item M0001.</span></span>  
2. <span data-ttu-id="ab516-149">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="ab516-149">Click OK.</span></span>
3. <span data-ttu-id="ab516-150">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="ab516-150">Close the page.</span></span>
4. <span data-ttu-id="ab516-151">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="ab516-151">Close the page.</span></span>
5. <span data-ttu-id="ab516-152">Vaya a Gestión de información de productos > Producción ajustada > Reglas kanban.</span><span class="sxs-lookup"><span data-stu-id="ab516-152">Go to Product information management > Lean manufacturing > Kanban rules.</span></span>
6. <span data-ttu-id="ab516-153">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="ab516-153">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="ab516-154">Seleccione la regla de kanban de evento creada para el artículo M0001.</span><span class="sxs-lookup"><span data-stu-id="ab516-154">Select the event kanban rule created for item M0001.</span></span>  
7. <span data-ttu-id="ab516-155">Expanda la sección Kanbans.</span><span class="sxs-lookup"><span data-stu-id="ab516-155">Expand the Kanbans section.</span></span>
8. <span data-ttu-id="ab516-156">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="ab516-156">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="ab516-157">Observe el kanban creado para suministrar M0001 para el pedido de producción estimado.</span><span class="sxs-lookup"><span data-stu-id="ab516-157">Notice the kanban created to supply M0001 for the estimated production order.</span></span>  
    * <span data-ttu-id="ab516-158">Este es el último paso.</span><span class="sxs-lookup"><span data-stu-id="ab516-158">This is the last step!</span></span>  


