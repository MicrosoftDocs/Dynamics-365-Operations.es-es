---
title: Crear una regla kanban con un evento de existencias mínimas
description: Este procedimiento se centra en la configuración necesaria para crear una regla kanban usando un evento de existencias mínimas para garantizar que un producto específico siempre está disponible en una ubicación específica.
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanRules, LeanProductionFlowActivityLookup, InventItemIdLookupSimple, EcoResProductInformationDialog, EcoResProductDetailsExtended, ReqItemTable, InventLocationIdLookup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2a9ba8ec2abb26e3b9ee7e14bdf882c1ffcb205b
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "311091"
---
# <a name="create-a-kanban-rule-using-a-minimum-stock-event"></a><span data-ttu-id="8186e-103">Crear una regla kanban con un evento de existencias mínimas</span><span class="sxs-lookup"><span data-stu-id="8186e-103">Create a kanban rule using a minimum stock event</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="8186e-104">Este procedimiento se centra en la configuración necesaria para crear una regla kanban usando un evento de existencias mínimas para garantizar que un producto específico siempre está disponible en una ubicación específica.</span><span class="sxs-lookup"><span data-stu-id="8186e-104">This procedure focuses on the setup needed to create a kanban rule using a minimum stock event to ensure that a specific product is always available at a specific location.</span></span> <span data-ttu-id="8186e-105">Una regla kanban se crea para transferir material a la ubicación cuando el nivel de inventario cae por debajo de 200 piezas.</span><span class="sxs-lookup"><span data-stu-id="8186e-105">A kanban rule is created to transfer material to the location when the inventory level drops below 200 pieces.</span></span> <span data-ttu-id="8186e-106">Al ejecutar el procesamiento de eventos de pedidos, se crean los kanbans necesarios.</span><span class="sxs-lookup"><span data-stu-id="8186e-106">By running the Pegging event processing, the needed kanbans are created.</span></span> <span data-ttu-id="8186e-107">La empresa de datos de prueba utilizada para crear esta tarea es USMF.</span><span class="sxs-lookup"><span data-stu-id="8186e-107">The demo data company used to create this task is USMF.</span></span> <span data-ttu-id="8186e-108">Esta tarea está pensada para el ingeniero de procesos o el administrador de flujo de valor, conforme preparan la producción de un producto nuevo o modificado en un entorno de producción ajustada.</span><span class="sxs-lookup"><span data-stu-id="8186e-108">This task is intended for the process engineer or the value stream manager, as they prepare production of a new or modified product in a lean environment.</span></span>


## <a name="create-a-new-kanban-rule"></a><span data-ttu-id="8186e-109">Crear una nueva regla kanban</span><span class="sxs-lookup"><span data-stu-id="8186e-109">Create a new kanban rule</span></span>
1. <span data-ttu-id="8186e-110">Vaya a Gestión de información de productos > Producción ajustada > Reglas kanban.</span><span class="sxs-lookup"><span data-stu-id="8186e-110">Go to Product information management > Lean manufacturing > Kanban rules.</span></span>
2. <span data-ttu-id="8186e-111">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="8186e-111">Click New.</span></span>
3. <span data-ttu-id="8186e-112">En el campo Tipo, seleccione "Retirada".</span><span class="sxs-lookup"><span data-stu-id="8186e-112">In the Type field, select 'Withdrawal'.</span></span>
    * <span data-ttu-id="8186e-113">Este tipo se usa para crear kanbans de transferencia.</span><span class="sxs-lookup"><span data-stu-id="8186e-113">This type is used to create transfer kanbans.</span></span>  
4. <span data-ttu-id="8186e-114">En el campo Estrategia de reabastecimiento, seleccione "Evento".</span><span class="sxs-lookup"><span data-stu-id="8186e-114">In the Replenishment strategy field, select 'Event'.</span></span>
    * <span data-ttu-id="8186e-115">La estrategia de evento se usa para crear la transferencia de los kanbans basados en un evento.</span><span class="sxs-lookup"><span data-stu-id="8186e-115">The Event strategy is used to create the transfer kanbans based on an event.</span></span> <span data-ttu-id="8186e-116">Más adelante en el procedimiento, desencadenará kanbans de transferencia mediante el reabastecimiento de existencias.</span><span class="sxs-lookup"><span data-stu-id="8186e-116">Later in the procedure, you will trigger transfer kanbans by using stock replenishment.</span></span>  
5. <span data-ttu-id="8186e-117">En el campo Actividad del primer plan, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="8186e-117">In the First plan activity field, enter or select a value.</span></span>
    * <span data-ttu-id="8186e-118">Especifique o seleccione ReplenishSpeakerComponents.</span><span class="sxs-lookup"><span data-stu-id="8186e-118">Enter or select ReplenishSpeakerComponents.</span></span> <span data-ttu-id="8186e-119">Esta actividad de transferencia tiene el almacén de recepción (salida) y ubicación 12, lo que significa que los materiales se moverán a la ubicación 12 del almacén 12.</span><span class="sxs-lookup"><span data-stu-id="8186e-119">This transfer activity has receipt (output) warehouse and location 12, which means that materials will be moved to location 12 in warehouse 12.</span></span>  
6. <span data-ttu-id="8186e-120">Expanda la sección Detalles.</span><span class="sxs-lookup"><span data-stu-id="8186e-120">Expand the Details section.</span></span>
7. <span data-ttu-id="8186e-121">En el campo Producto, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="8186e-121">In the Product field, enter or select a value.</span></span>
    * <span data-ttu-id="8186e-122">Seleccione M0007.</span><span class="sxs-lookup"><span data-stu-id="8186e-122">Select M0007.</span></span>  
8. <span data-ttu-id="8186e-123">Expanda la sección Eventos.</span><span class="sxs-lookup"><span data-stu-id="8186e-123">Expand the Events section.</span></span>
9. <span data-ttu-id="8186e-124">En el campo Evento de reabastecimiento de existencias, seleccione "Lote".</span><span class="sxs-lookup"><span data-stu-id="8186e-124">In the Stock replenishment event field, select 'Batch'.</span></span>
    * <span data-ttu-id="8186e-125">Esto crea kanbans para satisfacer las necesidades de material en la ubicación relacionada durante el procesamiento de evento de pedido.</span><span class="sxs-lookup"><span data-stu-id="8186e-125">This creates kanbans to fulfill material needs at the related location during Pegging event processing.</span></span>  

## <a name="set-the-minimum-quantity-for-the-item"></a><span data-ttu-id="8186e-126">Establecer la cantidad mínima para el artículo</span><span class="sxs-lookup"><span data-stu-id="8186e-126">Set the minimum quantity for the item</span></span>
1. <span data-ttu-id="8186e-127">Haga clic para seguir el vínculo en el campo Producto.</span><span class="sxs-lookup"><span data-stu-id="8186e-127">Click to follow the link in the Product field.</span></span>
2. <span data-ttu-id="8186e-128">Haga clic para seguir el vínculo en el campo Número de artículo.</span><span class="sxs-lookup"><span data-stu-id="8186e-128">Click to follow the link in the Item number field.</span></span>
3. <span data-ttu-id="8186e-129">Expanda el cuadro informativo Imagen del producto.</span><span class="sxs-lookup"><span data-stu-id="8186e-129">Expand the Product image FactBox.</span></span>
4. <span data-ttu-id="8186e-130">En el panel de acciones, haga clic en Plan.</span><span class="sxs-lookup"><span data-stu-id="8186e-130">On the Action Pane, click Plan.</span></span>
5. <span data-ttu-id="8186e-131">Haga clic en Cobertura de artículos.</span><span class="sxs-lookup"><span data-stu-id="8186e-131">Click Item coverage.</span></span>
6. <span data-ttu-id="8186e-132">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="8186e-132">Click New.</span></span>
7. <span data-ttu-id="8186e-133">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="8186e-133">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="8186e-134">En el campo Almacén, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="8186e-134">In the Warehouse field, enter or select a value.</span></span>
    * <span data-ttu-id="8186e-135">Establezca el almacén en 12.</span><span class="sxs-lookup"><span data-stu-id="8186e-135">Set Warehouse to 12.</span></span>  
9. <span data-ttu-id="8186e-136">Establezca el mínimo en “200".</span><span class="sxs-lookup"><span data-stu-id="8186e-136">Set Minimum to '200'.</span></span>

## <a name="run-the-batch-event-creation-job"></a><span data-ttu-id="8186e-137">Ejecutar el trabajo de creación de eventos por lotes</span><span class="sxs-lookup"><span data-stu-id="8186e-137">Run the batch event creation job</span></span>
1. <span data-ttu-id="8186e-138">Vaya a Control de producción > Tareas periódicas > Procesamiento por lotes de trabajo kanban > Procesamiento de evento de pedido.</span><span class="sxs-lookup"><span data-stu-id="8186e-138">Go to Production control > Periodic tasks > Kanban job batch processing > Pegging event processing.</span></span>
2. <span data-ttu-id="8186e-139">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="8186e-139">Click OK.</span></span>
3. <span data-ttu-id="8186e-140">Vaya a Gestión de información de productos > Producción ajustada > Reglas kanban.</span><span class="sxs-lookup"><span data-stu-id="8186e-140">Go to Product information management > Lean manufacturing > Kanban rules.</span></span>
4. <span data-ttu-id="8186e-141">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="8186e-141">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="8186e-142">Seleccione la regla kanban que creó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="8186e-142">Select the kanban rule that you created earlier.</span></span>  
5. <span data-ttu-id="8186e-143">Expanda la sección Kanbans.</span><span class="sxs-lookup"><span data-stu-id="8186e-143">Expand the Kanbans section.</span></span>
    * <span data-ttu-id="8186e-144">Observe que un kanban se creó para transferir el material necesario para el almacén 12.</span><span class="sxs-lookup"><span data-stu-id="8186e-144">Notice that a kanban was created to transfer the needed material to warehouse 12.</span></span>  

