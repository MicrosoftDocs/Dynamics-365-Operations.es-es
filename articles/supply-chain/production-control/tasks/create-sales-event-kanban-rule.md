---
title: Crear una regla kanban de eventos de ventas
description: Este procedimiento se centra en la configuración necesaria para crear una regla kanban que se activará durante la creación de pedidos de ventas.
author: ChristianRytt
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanRules, LeanProductionFlowActivityLookup, InventItemIdLookupSimple, SalesTableListPage, SalesCreateOrder, SalesTable, LeanPeggingTree
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1759adea6db8120078e2f32bff79178545c2328a
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2020
ms.locfileid: "3210865"
---
# <a name="create-a-sales-event-kanban-rule"></a><span data-ttu-id="ec3f1-103">Crear una regla kanban de eventos de ventas</span><span class="sxs-lookup"><span data-stu-id="ec3f1-103">Create a sales event kanban rule</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ec3f1-104">Este procedimiento se centra en la configuración necesaria para crear una regla kanban que se activará durante la creación de pedidos de ventas.</span><span class="sxs-lookup"><span data-stu-id="ec3f1-104">This procedure focuses on the setup needed to create a kanban rule that is triggered during sales order creation.</span></span> <span data-ttu-id="ec3f1-105">La regla kanban de evento reaprovisiona los requisitos que se originan de las líneas de pedidos de ventas.</span><span class="sxs-lookup"><span data-stu-id="ec3f1-105">The event kanban rule replenishes requirements that originate from sales order lines.</span></span> <span data-ttu-id="ec3f1-106">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="ec3f1-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="ec3f1-107">Está pensado para el ingeniero de procesos o el administrador de flujo de valor, ya que preparan la producción de un producto nuevo o modificado.</span><span class="sxs-lookup"><span data-stu-id="ec3f1-107">It is intended for the process engineer or the value stream manager as they prepare production of a new or modified product.</span></span>




## <a name="create-a-new-kanban-rule"></a><span data-ttu-id="ec3f1-108">Crear una nueva regla kanban</span><span class="sxs-lookup"><span data-stu-id="ec3f1-108">Create a new kanban rule</span></span>
1. <span data-ttu-id="ec3f1-109">Vaya a Reglas kanban.</span><span class="sxs-lookup"><span data-stu-id="ec3f1-109">Go to Kanban rules.</span></span>
2. <span data-ttu-id="ec3f1-110">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="ec3f1-110">Click New.</span></span>
3. <span data-ttu-id="ec3f1-111">En el campo Estrategia de reabastecimiento, seleccione "Evento".</span><span class="sxs-lookup"><span data-stu-id="ec3f1-111">In the Replenishment strategy field, select 'Event'.</span></span>
    * <span data-ttu-id="ec3f1-112">La selección de evento significa que la regla kanban se activa por un evento, por ejemplo, la creación de una línea de pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="ec3f1-112">Selecting Event means that the kanban rule is triggered by an event, for example, creation of a sales order line.</span></span>   <span data-ttu-id="ec3f1-113">Esto se aplica a áreas donde cada kanban debe cubrir una demanda específica.</span><span class="sxs-lookup"><span data-stu-id="ec3f1-113">This is applied to areas where each kanban should cover a specific demand.</span></span>  
4. <span data-ttu-id="ec3f1-114">En el campo Actividad del primer plan, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="ec3f1-114">In the First plan activity field, enter or select a value.</span></span>
    * <span data-ttu-id="ec3f1-115">Seleccione Ensamblado final.</span><span class="sxs-lookup"><span data-stu-id="ec3f1-115">Select Final assembly.</span></span>  
5. <span data-ttu-id="ec3f1-116">Expanda la sección Detalles.</span><span class="sxs-lookup"><span data-stu-id="ec3f1-116">Expand the Details section.</span></span>
6. <span data-ttu-id="ec3f1-117">En el campo Producto, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="ec3f1-117">In the Product field, enter or select a value.</span></span>
    * <span data-ttu-id="ec3f1-118">Seleccione L0050.</span><span class="sxs-lookup"><span data-stu-id="ec3f1-118">Select L0050.</span></span>  

## <a name="define-an-event"></a><span data-ttu-id="ec3f1-119">Definir un evento</span><span class="sxs-lookup"><span data-stu-id="ec3f1-119">Define an event</span></span>
1. <span data-ttu-id="ec3f1-120">Expanda la sección Eventos.</span><span class="sxs-lookup"><span data-stu-id="ec3f1-120">Expand the Events section.</span></span>
2. <span data-ttu-id="ec3f1-121">En el campo Evento de ventas, seleccione "Automático".</span><span class="sxs-lookup"><span data-stu-id="ec3f1-121">In the Sales event field, select 'Automatic'.</span></span>
    * <span data-ttu-id="ec3f1-122">Al seleccionar el evento de ventas Automático, esta regla kanban se activará automáticamente cuando una línea de ventas coincida con el producto y la ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="ec3f1-122">By selecting the sales event Automatic, this kanban rule will be triggered automatically when a sales line matches the product and receipt location.</span></span> <span data-ttu-id="ec3f1-123">En este procedimiento, es el producto L0050 del almacén 13.</span><span class="sxs-lookup"><span data-stu-id="ec3f1-123">In this procedure, it is product L0050 on warehouse 13.</span></span>  
3. <span data-ttu-id="ec3f1-124">Establezca la Cantidad mínima de eventos en "50".</span><span class="sxs-lookup"><span data-stu-id="ec3f1-124">Set Minimum event quantity to '50'.</span></span>
    * <span data-ttu-id="ec3f1-125">Con una cantidad de evento mínima de 50, la regla kanban solo se activará por eventos con una cantidad de 50 o más.</span><span class="sxs-lookup"><span data-stu-id="ec3f1-125">With a minimum event quantity of 50, the kanban rule will only be triggered by events with a quantity of 50 or more.</span></span>  
4. <span data-ttu-id="ec3f1-126">Expanda la sección Flujo de producción.</span><span class="sxs-lookup"><span data-stu-id="ec3f1-126">Expand the Production flow section.</span></span>
    * <span data-ttu-id="ec3f1-127">Observe que la Ubicación de recepción es el almacén 13.</span><span class="sxs-lookup"><span data-stu-id="ec3f1-127">Notice that the Receipt location is warehouse 13.</span></span> <span data-ttu-id="ec3f1-128">Esto significa que esta regla kanban se activará para esta ubicación.</span><span class="sxs-lookup"><span data-stu-id="ec3f1-128">This means that this kanban rule will be triggered for this location.</span></span>  
    * <span data-ttu-id="ec3f1-129">En este ejemplo, una línea de ventas para el producto L0050, con una cantidad de 50 o más, en el almacén 13, activará esta regla kanban.</span><span class="sxs-lookup"><span data-stu-id="ec3f1-129">In this example, a sales line for product L0050, with a quantity of 50 or more, on warehouse 13, will trigger this kanban rule.</span></span>  

## <a name="create-sales-line-to-trigger-event-kanban-rule"></a><span data-ttu-id="ec3f1-130">Crear línea de ventas para activar la regla kanban de evento</span><span class="sxs-lookup"><span data-stu-id="ec3f1-130">Create sales line to trigger event kanban rule</span></span>
1. <span data-ttu-id="ec3f1-131">Vaya a Todos los pedidos de ventas.</span><span class="sxs-lookup"><span data-stu-id="ec3f1-131">Go to All sales orders.</span></span>
    * <span data-ttu-id="ec3f1-132">Se muestra una advertencia cuando se guarda la regla kanban, lo que significa que los kanbans se crearán en tiempo real durante la creación de pedidos de ventas.</span><span class="sxs-lookup"><span data-stu-id="ec3f1-132">A warning is shown when the kanban rule is saved, which means that kanbans will be created in real-time during sales order creation.</span></span>  
2. <span data-ttu-id="ec3f1-133">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="ec3f1-133">Click New.</span></span>
3. <span data-ttu-id="ec3f1-134">En el campo Cuenta de cliente, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="ec3f1-134">In the Customer account field, enter or select a value.</span></span>
    * <span data-ttu-id="ec3f1-135">Por ejemplo, seleccione US-003.</span><span class="sxs-lookup"><span data-stu-id="ec3f1-135">For example, select US-003.</span></span>  
4. <span data-ttu-id="ec3f1-136">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="ec3f1-136">Click OK.</span></span>
5. <span data-ttu-id="ec3f1-137">En el campo Código de artículo, escriba 'L0050'.</span><span class="sxs-lookup"><span data-stu-id="ec3f1-137">In the Item number field, type 'L0050'.</span></span>
6. <span data-ttu-id="ec3f1-138">En el campo Sitio, escriba "1".</span><span class="sxs-lookup"><span data-stu-id="ec3f1-138">In the Site field, type '1'.</span></span>
    * <span data-ttu-id="ec3f1-139">Seleccione el sitio 1 porque el almacén 13 se encuentra en el sitio 1.</span><span class="sxs-lookup"><span data-stu-id="ec3f1-139">Select Site 1 because Warehouse 13 is on Site 1.</span></span>  
7. <span data-ttu-id="ec3f1-140">En el campo Almacén, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="ec3f1-140">In the Warehouse field, enter or select a value.</span></span>
    * <span data-ttu-id="ec3f1-141">Establezca el almacén en 13.</span><span class="sxs-lookup"><span data-stu-id="ec3f1-141">Set Warehouse to 13.</span></span>  
8. <span data-ttu-id="ec3f1-142">Establezca el valor de cantidad en '75'.</span><span class="sxs-lookup"><span data-stu-id="ec3f1-142">Set Quantity to '75'.</span></span>
    * <span data-ttu-id="ec3f1-143">Escriba una cantidad de 50 o superior, para activar la regla kanban creada.</span><span class="sxs-lookup"><span data-stu-id="ec3f1-143">Enter a quantity of 50 or greater, to trigger the created kanban rule.</span></span>  

## <a name="verify-that-kanban-is-created"></a><span data-ttu-id="ec3f1-144">Comprobar que se creó el kanban</span><span class="sxs-lookup"><span data-stu-id="ec3f1-144">Verify that kanban is created</span></span>
1. <span data-ttu-id="ec3f1-145">Haga clic en Producto y suministro.</span><span class="sxs-lookup"><span data-stu-id="ec3f1-145">Click Product and supply.</span></span>
2. <span data-ttu-id="ec3f1-146">Haga clic en Ver diagrama de árbol.</span><span class="sxs-lookup"><span data-stu-id="ec3f1-146">Click View pegging tree.</span></span>
    * <span data-ttu-id="ec3f1-147">Observe que se crea un kanban con la misma cantidad que la línea de ventas.</span><span class="sxs-lookup"><span data-stu-id="ec3f1-147">Notice that a kanban with the same quantity as the sales line is created.</span></span> <span data-ttu-id="ec3f1-148">También puede ver las emisiones de material necesarias para producir L0050.</span><span class="sxs-lookup"><span data-stu-id="ec3f1-148">You can also see the material issues needed to produce L0050.</span></span> <span data-ttu-id="ec3f1-149">Este es el último paso de este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="ec3f1-149">This is the last step in this procedure.</span></span>  

