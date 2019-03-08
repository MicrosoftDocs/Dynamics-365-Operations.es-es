---
title: Crear una regla kanban de eventos de línea de L. MAT.
description: Esta tarea se centra en la configuración necesaria para crear una regla kanban de evento para asegurar el suministro de las líneas de L. MAT de producción en un entorno mixto de producción lean y clásico.
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanRules, LeanProductionFlowActivityLookup, InventItemIdLookupSimple, ProdTableListPage, ProdTableCreate, InventItemIdLookupPurchase, ProdTable, ProdBOM, ProdParmCostEstimation
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 82a4252548fd030f2a044436ff607da5125d2854
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "337104"
---
# <a name="create-a-bom-line-event-kanban-rule"></a><span data-ttu-id="663d1-103">Crear una regla kanban de eventos de línea de L. MAT.</span><span class="sxs-lookup"><span data-stu-id="663d1-103">Create a BOM line event kanban rule</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="663d1-104">Esta tarea se centra en la configuración necesaria para crear una regla kanban de evento para asegurar el suministro de las líneas de L. MAT de producción en un entorno mixto de producción lean y clásico.</span><span class="sxs-lookup"><span data-stu-id="663d1-104">This task focuses on the setup needed to create an event kanban rule to ensure supply for production BOM lines in a mixed lean and classic production environment.</span></span> <span data-ttu-id="663d1-105">La empresa de datos de prueba utilizada para crear esta tarea es USMF.</span><span class="sxs-lookup"><span data-stu-id="663d1-105">The demo data company used to create this task is USMF.</span></span> <span data-ttu-id="663d1-106">Esta tarea está pensada para el ingeniero de procesos o el administrador de flujo de valor, ya que preparan la producción de un producto nuevo o modificado.</span><span class="sxs-lookup"><span data-stu-id="663d1-106">This task is intended for the process engineer or the value stream manager, as they prepare production of a new or modified product.</span></span>


## <a name="create-a-new-kanban-rule"></a><span data-ttu-id="663d1-107">Crear una nueva regla kanban</span><span class="sxs-lookup"><span data-stu-id="663d1-107">Create a new kanban rule</span></span>
1. <span data-ttu-id="663d1-108">Vaya a Control de producción > Tareas periódicas > Cálculo de cantidad kanban > Reglas kanban.</span><span class="sxs-lookup"><span data-stu-id="663d1-108">Go to Production control > Periodic tasks > Kanban quantity calculation > Kanban rules.</span></span>
2. <span data-ttu-id="663d1-109">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="663d1-109">Click New.</span></span>
3. <span data-ttu-id="663d1-110">En el campo Tipo, seleccione "Retirada".</span><span class="sxs-lookup"><span data-stu-id="663d1-110">In the Type field, select 'Withdrawal'.</span></span>
    * <span data-ttu-id="663d1-111">El tipo Retirada se usa para crear kanbans de transferencia.</span><span class="sxs-lookup"><span data-stu-id="663d1-111">The Withdrawal type is used to create transfer kanbans.</span></span>  
4. <span data-ttu-id="663d1-112">En el campo Estrategia de reabastecimiento, seleccione "Evento".</span><span class="sxs-lookup"><span data-stu-id="663d1-112">In the Replenishment strategy field, select 'Event'.</span></span>
    * <span data-ttu-id="663d1-113">La estrategia de evento se selecciona para crear la transferencia de los kanbans basados en un evento.</span><span class="sxs-lookup"><span data-stu-id="663d1-113">The Event strategy is selected to create the transfer of kanbans based on an event.</span></span> <span data-ttu-id="663d1-114">Más adelante en la guía de tareas, lo desencadenaremos calculando un pedido de producción.</span><span class="sxs-lookup"><span data-stu-id="663d1-114">Later in the task guide, we will trigger it by estimating a production order.</span></span>  
5. <span data-ttu-id="663d1-115">En el campo Actividad del primer plan, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="663d1-115">In the First plan activity field, enter or select a value.</span></span>
    * <span data-ttu-id="663d1-116">Especifique o seleccione ReplenishSpeakerComponents.</span><span class="sxs-lookup"><span data-stu-id="663d1-116">Enter or select ReplenishSpeakerComponents.</span></span> <span data-ttu-id="663d1-117">Esta actividad de transferencia tiene el almacén de recepción (salida) y ubicación 12, lo que significa que el material se moverá a la ubicación 12 del almacén 12.</span><span class="sxs-lookup"><span data-stu-id="663d1-117">This transfer activity has receipt (output) warehouse and location 12, which means that material will be moved to location 12 in warehouse 12.</span></span>  
6. <span data-ttu-id="663d1-118">Expanda la sección Detalles.</span><span class="sxs-lookup"><span data-stu-id="663d1-118">Expand the Details section.</span></span>
7. <span data-ttu-id="663d1-119">En el campo Producto, especifique o seleccione M0001.</span><span class="sxs-lookup"><span data-stu-id="663d1-119">In the Product field, enter or select M0001.</span></span>
8. <span data-ttu-id="663d1-120">Expanda la sección Eventos.</span><span class="sxs-lookup"><span data-stu-id="663d1-120">Expand the Events section.</span></span>
9. <span data-ttu-id="663d1-121">En el campo Evento de línea de L. MAT, seleccione "Automático".</span><span class="sxs-lookup"><span data-stu-id="663d1-121">In the BOM line event field, select 'Automatic'.</span></span>
    * <span data-ttu-id="663d1-122">Con el campo Evento de línea de L. MAT establecido en Automático, el kanban se creará para satisfacer las necesidades de material para las líneas de L. MAT del pedido de producción.</span><span class="sxs-lookup"><span data-stu-id="663d1-122">With the BOM line event field set to Automatic, kanban will be created to fulfill material needs for production order BOM lines.</span></span>  
10. <span data-ttu-id="663d1-123">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="663d1-123">Close the page.</span></span>

## <a name="create-and-modify-a-new-production-order"></a><span data-ttu-id="663d1-124">Crear y modificar una nueva orden de producción</span><span class="sxs-lookup"><span data-stu-id="663d1-124">Create and modify a new production order</span></span>
1. <span data-ttu-id="663d1-125">Vaya a Control de producción > Pedidos de producción > Todos los pedidos de producción.</span><span class="sxs-lookup"><span data-stu-id="663d1-125">Go to Production control > Production orders > All production orders.</span></span>
2. <span data-ttu-id="663d1-126">Haga clic en Nuevo pedido de producción.</span><span class="sxs-lookup"><span data-stu-id="663d1-126">Click New production order.</span></span>
3. <span data-ttu-id="663d1-127">En el campo Número de artículo, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="663d1-127">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="663d1-128">Escriba o seleccione “L0001”.</span><span class="sxs-lookup"><span data-stu-id="663d1-128">Enter or select 'L0001'.</span></span> <span data-ttu-id="663d1-129">Usamos el artículo L0001 porque el artículo M0001 se incluye en la L. MAT para el artículo L0001.</span><span class="sxs-lookup"><span data-stu-id="663d1-129">We use item L0001 because item M0001 is included in the BOM for item L0001.</span></span>  
4. <span data-ttu-id="663d1-130">Haga clic en Crear.</span><span class="sxs-lookup"><span data-stu-id="663d1-130">Click Create.</span></span>
5. <span data-ttu-id="663d1-131">En la lista, haga clic en el vínculo de la fila para L0001</span><span class="sxs-lookup"><span data-stu-id="663d1-131">In the list, click the link in the row for L0001</span></span>
6. <span data-ttu-id="663d1-132">Haga clic en L. MAT.</span><span class="sxs-lookup"><span data-stu-id="663d1-132">Click BOM.</span></span>
7. <span data-ttu-id="663d1-133">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="663d1-133">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="663d1-134">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="663d1-134">Click Edit.</span></span>
9. <span data-ttu-id="663d1-135">En el campo Tipo de línea, seleccione "Suministro asegurado".</span><span class="sxs-lookup"><span data-stu-id="663d1-135">In the Line type field, select 'Pegged supply'.</span></span>
    * <span data-ttu-id="663d1-136">El suministro asegurado se selecciona para desencadenar la creación de la suministro de un kanban.</span><span class="sxs-lookup"><span data-stu-id="663d1-136">Pegged supply is selected to trigger the supply creation of a kanban.</span></span>  
10. <span data-ttu-id="663d1-137">Seleccione No en el campo Consumo del recurso.</span><span class="sxs-lookup"><span data-stu-id="663d1-137">Select No in the Resource consumption field.</span></span>
    * <span data-ttu-id="663d1-138">La desactivación de la casilla Consumo del recurso nos permite cambiar el almacén.</span><span class="sxs-lookup"><span data-stu-id="663d1-138">Clearing the check box of Resource consumption lets us change the warehouse.</span></span>  
11. <span data-ttu-id="663d1-139">Expanda la sección Dimensiones de inventario.</span><span class="sxs-lookup"><span data-stu-id="663d1-139">Expand the Inventory dimensions section.</span></span>
12. <span data-ttu-id="663d1-140">En el campo Almacén, escriba "12".</span><span class="sxs-lookup"><span data-stu-id="663d1-140">In the Warehouse field, type '12'.</span></span>
    * <span data-ttu-id="663d1-141">El almacén se establece en 12 porque este es el almacén de salida para la actividad de retirada.</span><span class="sxs-lookup"><span data-stu-id="663d1-141">Warehouse is set to 12 because this is the output warehouse for the withdrawal activity.</span></span>  
13. <span data-ttu-id="663d1-142">En el campo Ubicación, escriba "12".</span><span class="sxs-lookup"><span data-stu-id="663d1-142">In the Location field, type '12'.</span></span>
    * <span data-ttu-id="663d1-143">La ubicación se establece en 12 porque este es la ubicación de salida de la actividad de retirada.</span><span class="sxs-lookup"><span data-stu-id="663d1-143">Location is set to 12 because this is the output location of the withdrawal activity.</span></span>  
14. <span data-ttu-id="663d1-144">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="663d1-144">Close the page.</span></span>
15. <span data-ttu-id="663d1-145">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="663d1-145">Close the page.</span></span>

## <a name="estimate-the-production-order-and-view-the-kanban-created"></a><span data-ttu-id="663d1-146">Calcular el pedido de producción y ver el kanban creado</span><span class="sxs-lookup"><span data-stu-id="663d1-146">Estimate the production order and view the kanban created</span></span>
1. <span data-ttu-id="663d1-147">Haga clic en Estimación.</span><span class="sxs-lookup"><span data-stu-id="663d1-147">Click Estimate.</span></span>
    * <span data-ttu-id="663d1-148">El cálculo del pedido de producción desencadenará la creación del kanban asociado para suministrar el artículo M0001.</span><span class="sxs-lookup"><span data-stu-id="663d1-148">Estimating the production order will trigger the creation of the associated kanban to supply item M0001.</span></span>  
2. <span data-ttu-id="663d1-149">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="663d1-149">Click OK.</span></span>
3. <span data-ttu-id="663d1-150">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="663d1-150">Close the page.</span></span>
4. <span data-ttu-id="663d1-151">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="663d1-151">Close the page.</span></span>
5. <span data-ttu-id="663d1-152">Vaya a Gestión de información de productos > Producción ajustada > Reglas kanban.</span><span class="sxs-lookup"><span data-stu-id="663d1-152">Go to Product information management > Lean manufacturing > Kanban rules.</span></span>
6. <span data-ttu-id="663d1-153">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="663d1-153">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="663d1-154">Seleccione la regla de kanban de evento creada para el artículo M0001.</span><span class="sxs-lookup"><span data-stu-id="663d1-154">Select the event kanban rule created for item M0001.</span></span>  
7. <span data-ttu-id="663d1-155">Expanda la sección Kanbans.</span><span class="sxs-lookup"><span data-stu-id="663d1-155">Expand the Kanbans section.</span></span>
8. <span data-ttu-id="663d1-156">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="663d1-156">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="663d1-157">Observe el kanban creado para suministrar M0001 para el pedido de producción estimado.</span><span class="sxs-lookup"><span data-stu-id="663d1-157">Notice the kanban created to supply M0001 for the estimated production order.</span></span>  
    * <span data-ttu-id="663d1-158">Este es el último paso.</span><span class="sxs-lookup"><span data-stu-id="663d1-158">This is the last step!</span></span>  

