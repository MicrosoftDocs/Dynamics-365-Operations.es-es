--- 
title: "Crear una regla kanban con un evento de línea de kanban"
description: "Este procedimiento crea una regla kanban mediante el evento de línea kanban para desencadenar una extracción de una actividad de proceso."
author: ChristianRytt
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: KanbanRules, LeanProductionFlowActivityLookup, SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 32d71167fdad65cb1dec37671999a497759ca484
ms.openlocfilehash: 31a7bf0466855defa90fbe746f2d7a9b7445099c
ms.contentlocale: es-es
ms.lasthandoff: 09/11/2018

---
# <a name="create-a-kanban-rule-using-a-kanban-line-event"></a><span data-ttu-id="23e78-103">Crear una regla kanban con un evento de línea de kanban</span><span class="sxs-lookup"><span data-stu-id="23e78-103">Create a kanban rule using a kanban line event</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="23e78-104">Este procedimiento crea una regla kanban mediante el evento de línea kanban para desencadenar una extracción de una actividad de proceso.</span><span class="sxs-lookup"><span data-stu-id="23e78-104">This procedure creates a kanban rule by using the kanban line event setting to trigger pull from a process activity.</span></span> <span data-ttu-id="23e78-105">La regla kanban es desencadena por una actividad de proceso kanban, con una cantidad igual o superior a 25 cada una.</span><span class="sxs-lookup"><span data-stu-id="23e78-105">The kanban rule is triggered by a kanban process activity, with a quantity equal to or greater than 25 each.</span></span> <span data-ttu-id="23e78-106">La empresa de datos de prueba utilizada para crear esta tarea es USMF.</span><span class="sxs-lookup"><span data-stu-id="23e78-106">The demo data company used to create this task is USMF.</span></span> <span data-ttu-id="23e78-107">Esta tarea está pensada para el ingeniero de procesos o el administrador de flujo de valor, conforme preparan la producción de un producto nuevo o modificado en un entorno de producción ajustada.</span><span class="sxs-lookup"><span data-stu-id="23e78-107">This task is intended for the process engineer or the value stream manager, as they prepare production of a new or modified product in a lean environment.</span></span>


## <a name="create-a-kanban-rule"></a><span data-ttu-id="23e78-108">Crear una regla kanban</span><span class="sxs-lookup"><span data-stu-id="23e78-108">Create a kanban rule</span></span>
1. <span data-ttu-id="23e78-109">Vaya a Gestión de información de productos > Producción ajustada > Reglas kanban.</span><span class="sxs-lookup"><span data-stu-id="23e78-109">Go to Product information management > Lean manufacturing > Kanban rules.</span></span>
2. <span data-ttu-id="23e78-110">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="23e78-110">Click New.</span></span>
3. <span data-ttu-id="23e78-111">En el campo Estrategia de reabastecimiento, seleccione "Evento".</span><span class="sxs-lookup"><span data-stu-id="23e78-111">In the Replenishment strategy field, select 'Event'.</span></span>
    * <span data-ttu-id="23e78-112">Esto genera kanbans directamente desde la demanda.</span><span class="sxs-lookup"><span data-stu-id="23e78-112">This generates kanbans directly from demand.</span></span> <span data-ttu-id="23e78-113">Se utiliza para configurar las reglas que definen una situación de fabricación sobre pedido.</span><span class="sxs-lookup"><span data-stu-id="23e78-113">It is used to set up rules that define a make-to-order scenario.</span></span>  
4. <span data-ttu-id="23e78-114">En el campo Actividad del primer plan, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="23e78-114">In the First plan activity field, enter or select a value.</span></span>
    * <span data-ttu-id="23e78-115">Especifique o seleccione SpeakerAssemblyAndPolish.</span><span class="sxs-lookup"><span data-stu-id="23e78-115">Enter or select SpeakerAssemblyAndPolish.</span></span> <span data-ttu-id="23e78-116">La primera actividad de una regla kanban de fabricación es una actividad de proceso en el flujo de producción.</span><span class="sxs-lookup"><span data-stu-id="23e78-116">The first activity of a manufacturing kanban rule is a process activity in the production flow.</span></span> <span data-ttu-id="23e78-117">Cuando selecciona la actividad, las fechas de validez de la actividad se copian en las fechas de validez de la regla kanban.</span><span class="sxs-lookup"><span data-stu-id="23e78-117">When you select the activity, the validity dates of the activity are copied to the validity dates of the kanban rule.</span></span>  
5. <span data-ttu-id="23e78-118">Expanda la sección Detalles.</span><span class="sxs-lookup"><span data-stu-id="23e78-118">Expand the Details section.</span></span>
6. <span data-ttu-id="23e78-119">En el campo Producto, escriba "L0001".</span><span class="sxs-lookup"><span data-stu-id="23e78-119">In the Product field, type 'L0001'.</span></span>
7. <span data-ttu-id="23e78-120">Expanda la sección Eventos.</span><span class="sxs-lookup"><span data-stu-id="23e78-120">Expand the Events section.</span></span>
8. <span data-ttu-id="23e78-121">En el campo Evento de línea de kanban, seleccione "Automático".</span><span class="sxs-lookup"><span data-stu-id="23e78-121">In the Kanban line event field, select 'Automatic'.</span></span>
    * <span data-ttu-id="23e78-122">Esto genera kanbans de eventos a petición.</span><span class="sxs-lookup"><span data-stu-id="23e78-122">This generates event kanbans on demand.</span></span>  <span data-ttu-id="23e78-123">Este campo se utiliza para configurar reglas kanban que reabastecen el material necesario para una actividad de proceso en sentido descendente.</span><span class="sxs-lookup"><span data-stu-id="23e78-123">The field is used to configure kanban rules that replenish material that is required for a downstream process activity.</span></span> <span data-ttu-id="23e78-124">Al seleccionar Automático, se crean los kanbans de eventos con la demanda.</span><span class="sxs-lookup"><span data-stu-id="23e78-124">When you select Automatic, the event kanbans are created with the demand.</span></span> <span data-ttu-id="23e78-125">Se recomienda este configuración si espera ejecutar la producción el mismo día.</span><span class="sxs-lookup"><span data-stu-id="23e78-125">This setting is recommended if you expect to execute production on the same day.</span></span>  
9. <span data-ttu-id="23e78-126">Establezca la Cantidad mínima de eventos en "25".</span><span class="sxs-lookup"><span data-stu-id="23e78-126">Set Minimum event quantity to '25'.</span></span>
    * <span data-ttu-id="23e78-127">Se crean kanbans de evento cuando la cantidad de demanda es igual o superior a este campo.</span><span class="sxs-lookup"><span data-stu-id="23e78-127">Event kanbans are generated when the demand quantity is equal to or more than this field.</span></span> <span data-ttu-id="23e78-128">Esto es útil si desea producir una cantidad de pedido menor que este campo en una máquina y mayor que este campo en otra máquina.</span><span class="sxs-lookup"><span data-stu-id="23e78-128">This is useful if you want to produce an order quantity less than this field on one machine and more than this field on another machine.</span></span>  
10. <span data-ttu-id="23e78-129">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="23e78-129">Click Save.</span></span>

## <a name="create-sales-order-and-trigger-kanban-chain"></a><span data-ttu-id="23e78-130">Crear el pedido de ventas y desencadenar la cadena kanban</span><span class="sxs-lookup"><span data-stu-id="23e78-130">Create sales order and trigger kanban chain</span></span>
1. <span data-ttu-id="23e78-131">Vaya a Ventas y marketing > Pedidos de ventas > Todos los pedidos de ventas.</span><span class="sxs-lookup"><span data-stu-id="23e78-131">Go to Sales and marketing > Sales orders > All sales orders.</span></span>
2. <span data-ttu-id="23e78-132">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="23e78-132">Click New.</span></span>
3. <span data-ttu-id="23e78-133">En el campo Cuenta de cliente, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="23e78-133">In the Customer account field, enter or select a value.</span></span>
    * <span data-ttu-id="23e78-134">Seleccione Cuenta de cliente US-003, Forest Wholesales.</span><span class="sxs-lookup"><span data-stu-id="23e78-134">Select Customer account US-003, Forest Wholesales.</span></span>  
4. <span data-ttu-id="23e78-135">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="23e78-135">Click OK.</span></span>
5. <span data-ttu-id="23e78-136">En el campo Código de artículo, escriba 'L0001'.</span><span class="sxs-lookup"><span data-stu-id="23e78-136">In the Item number field, type 'L0001'.</span></span>
    * <span data-ttu-id="23e78-137">L0001 es el artículo para el que ha creado la regla kanban.</span><span class="sxs-lookup"><span data-stu-id="23e78-137">L0001 is the item for which you created the kanban rule.</span></span>  
6. <span data-ttu-id="23e78-138">Establezca el valor de cantidad en '27'.</span><span class="sxs-lookup"><span data-stu-id="23e78-138">Set Quantity to '27'.</span></span>
    * <span data-ttu-id="23e78-139">Porque 27 es superior a la cantidad mínima de 25 en la regla kanban, esto desencadenará un kanban de evento.</span><span class="sxs-lookup"><span data-stu-id="23e78-139">Because 27 is higher than the minimum quantity of 25 on the kanban rule, this will trigger an event kanban.</span></span>  
7. <span data-ttu-id="23e78-140">En el campo Sitio, escriba "1".</span><span class="sxs-lookup"><span data-stu-id="23e78-140">In the Site field, type '1'.</span></span>
8. <span data-ttu-id="23e78-141">En el campo Almacén, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="23e78-141">In the Warehouse field, enter or select a value.</span></span>
    * <span data-ttu-id="23e78-142">Seleccione el almacén 13.</span><span class="sxs-lookup"><span data-stu-id="23e78-142">Select warehouse 13.</span></span>  
9. <span data-ttu-id="23e78-143">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="23e78-143">Click Save.</span></span>

## <a name="view-the-kanban-generated-by-the-kanban-rule"></a><span data-ttu-id="23e78-144">Ver el kanban generado por la regla kanban</span><span class="sxs-lookup"><span data-stu-id="23e78-144">View the kanban generated by the kanban rule</span></span>
1. <span data-ttu-id="23e78-145">Vaya a Gestión de información de productos > Producción ajustada > Reglas kanban.</span><span class="sxs-lookup"><span data-stu-id="23e78-145">Go to Product information management > Lean manufacturing > Kanban rules.</span></span>
2. <span data-ttu-id="23e78-146">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="23e78-146">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="23e78-147">Expanda la sección Kanbans.</span><span class="sxs-lookup"><span data-stu-id="23e78-147">Expand the Kanbans section.</span></span>
    * <span data-ttu-id="23e78-148">Observe que se creó un kanban para 27 para procesar la actividad basada en la regla kanban creada.</span><span class="sxs-lookup"><span data-stu-id="23e78-148">Notice that a kanban for 27 was created to process the  activity based on the created kanban rule.</span></span>  
    * <span data-ttu-id="23e78-149">Este es el último paso.</span><span class="sxs-lookup"><span data-stu-id="23e78-149">This is the last step.</span></span>  


