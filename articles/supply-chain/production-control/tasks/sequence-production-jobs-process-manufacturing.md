--- 
title: "Secuenciar trabajos de producción para fabricación en procesos"
description: "Este procedimiento usa productos de pintura como ejemplo para mostrar cómo establecer la secuencia de los pedidos planificados según la prioridad de color y tamaño de paquete."
author: ChristianRytt
manager: AnnBe
ms.date: 11/03/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 0cf90ff7be59150e20d61a831e57062f9d9996d5
ms.contentlocale: es-es
ms.lasthandoff: 04/13/2018

---
# <a name="sequence-production-jobs-for-process-manufacturing"></a><span data-ttu-id="f28af-103">Secuenciar trabajos de producción para fabricación en procesos</span><span class="sxs-lookup"><span data-stu-id="f28af-103">Sequence production jobs for process manufacturing</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f28af-104">Este procedimiento usa productos de pintura como ejemplo para mostrar cómo establecer la secuencia de los pedidos planificados según la prioridad de color y tamaño de paquete.</span><span class="sxs-lookup"><span data-stu-id="f28af-104">This procedure uses paint products as an example to show how to sequence planned orders according to the priority of color and package size.</span></span> <span data-ttu-id="f28af-105">La empresa de datos de prueba utilizada para crear este procedimiento es USPI.</span><span class="sxs-lookup"><span data-stu-id="f28af-105">The demo data company used to create this procedure is USPI.</span></span> <span data-ttu-id="f28af-106">Este procedimiento se va a utilizar para el planificador de producción.</span><span class="sxs-lookup"><span data-stu-id="f28af-106">This procedure is intended for the production planner.</span></span>


## <a name="run-master-planning-for-uspi"></a><span data-ttu-id="f28af-107">Ejecutar planificación maestra para USPI</span><span class="sxs-lookup"><span data-stu-id="f28af-107">Run master planning for USPI</span></span>
1. <span data-ttu-id="f28af-108">Vaya a Planificación maestra > Planificación maestra > Ejecutar > lanificación maestra.</span><span class="sxs-lookup"><span data-stu-id="f28af-108">Go to Master planning > Master planning > Run > Master planning.</span></span>
2. <span data-ttu-id="f28af-109">En el campo Plan maestro, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="f28af-109">In the Master plan field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="f28af-110">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="f28af-110">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="f28af-111">Seleccione MasterPlan.</span><span class="sxs-lookup"><span data-stu-id="f28af-111">Select MasterPlan.</span></span>  
4. <span data-ttu-id="f28af-112">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="f28af-112">Click OK.</span></span>
    * <span data-ttu-id="f28af-113">Esto inicia la Planificación maestra, incluido el proceso de la secuencia.</span><span class="sxs-lookup"><span data-stu-id="f28af-113">This starts Master Planning, including the sequence process.</span></span> <span data-ttu-id="f28af-114">El proceso puede tardar unos minutos.</span><span class="sxs-lookup"><span data-stu-id="f28af-114">This process can take a few minutes.</span></span>  

## <a name="view-planned-orders-for-the-paint-products"></a><span data-ttu-id="f28af-115">Ver pedidos planificados para los productos de pintura</span><span class="sxs-lookup"><span data-stu-id="f28af-115">View planned orders for the paint products</span></span>
1. <span data-ttu-id="f28af-116">Vaya a Planificación maestra > Planificación maestra > Pedidos planificados.</span><span class="sxs-lookup"><span data-stu-id="f28af-116">Go to Master planning > Master planning > Planned orders.</span></span>
2. <span data-ttu-id="f28af-117">Expanda el cuadro informativo Detalles del artículo.</span><span class="sxs-lookup"><span data-stu-id="f28af-117">Expand the Item details FactBox.</span></span>
3. <span data-ttu-id="f28af-118">Expanda el cuadro informativo Detalles de programación.</span><span class="sxs-lookup"><span data-stu-id="f28af-118">Expand the Schedule details FactBox.</span></span>
4. <span data-ttu-id="f28af-119">En el campo Plan, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="f28af-119">In the Plan field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="f28af-120">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="f28af-120">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="f28af-121">Seleccione MasterPlan.</span><span class="sxs-lookup"><span data-stu-id="f28af-121">Select MasterPlan.</span></span>  
6. <span data-ttu-id="f28af-122">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="f28af-122">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="f28af-123">Use un filtro rápido para filtrar por el campo Código de artículo con el valor 'P300'.</span><span class="sxs-lookup"><span data-stu-id="f28af-123">Use the Quick Filter to filter on the Item number field with a value of 'P300'.</span></span>
    * <span data-ttu-id="f28af-124">Desbloquee para desplazarse a la derecha para ver la fecha de la orden y la fecha de entrega.</span><span class="sxs-lookup"><span data-stu-id="f28af-124">Unlock to scroll to the right to see the order date and delivery date.</span></span> <span data-ttu-id="f28af-125">Observe que estos artículos tienen una fecha de pedido de Hoy y las fechas de entrega para los pedidos planificados no están establecidas en frecuencia tras la prioridad de color y el tamaño del paquete, como se muestra en el nombre del producto.</span><span class="sxs-lookup"><span data-stu-id="f28af-125">Notice that these items have an order date of Today and the delivery dates for the planned orders are not sequenced after the priority of color and package size, as shown in the product name.</span></span> <span data-ttu-id="f28af-126">Puede mantener el puntero sobre un número de artículo para ver el nombre del producto y la prioridad.</span><span class="sxs-lookup"><span data-stu-id="f28af-126">You can hover over an item number to see the product name and priority.</span></span>  

## <a name="sequence-planned-orders-for-paint"></a><span data-ttu-id="f28af-127">Establecer en secuencia pedidos planificados para pintura</span><span class="sxs-lookup"><span data-stu-id="f28af-127">Sequence planned orders for paint</span></span>
1. <span data-ttu-id="f28af-128">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="f28af-128">Close the page.</span></span>
2. <span data-ttu-id="f28af-129">Vaya a Planificación maestra > Planificación maestra > Pedidos planificados en secuencia.</span><span class="sxs-lookup"><span data-stu-id="f28af-129">Go to Master planning > Master planning > Sequenced planned orders.</span></span>
3. <span data-ttu-id="f28af-130">Expanda el cuadro informativo Detalles del artículo.</span><span class="sxs-lookup"><span data-stu-id="f28af-130">Expand the Item details FactBox.</span></span>
4. <span data-ttu-id="f28af-131">Expanda el cuadro informativo Detalles de programación.</span><span class="sxs-lookup"><span data-stu-id="f28af-131">Expand the Schedule details FactBox.</span></span>
    * <span data-ttu-id="f28af-132">Nota: Aquí ve que la fecha y la hora iniciales para los pedidos planificados se establecen en secuencia de acuerdo con el color y el tamaño del paquete dentro de un período de cubo de 28 días.</span><span class="sxs-lookup"><span data-stu-id="f28af-132">Note: Here you see that the Start date/time for the planned orders are sequenced according to color and package size within a bucket period of 28 days.</span></span> <span data-ttu-id="f28af-133">Estos períodos se definen por un número en el campo Campaña.</span><span class="sxs-lookup"><span data-stu-id="f28af-133">These periods are defined by a number in the field Campaign.</span></span> <span data-ttu-id="f28af-134">El formulario de pedido planificado secuenciado actúa como el formulario de pedido planificado típico y el planificador de producción puede poner en firme los pedidos planificados aquí.</span><span class="sxs-lookup"><span data-stu-id="f28af-134">The sequenced planned order form acts like the typical planned order form, and the production planner can firm the planned orders here.</span></span>  
5. <span data-ttu-id="f28af-135">Marca todas las filas.</span><span class="sxs-lookup"><span data-stu-id="f28af-135">Mark all rows.</span></span>
6. <span data-ttu-id="f28af-136">Haga clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="f28af-136">Click Accept.</span></span>
    * <span data-ttu-id="f28af-137">Esto actualizará los pedidos planificados con la acción de secuencia seleccionada de Posponer o Adelantar.</span><span class="sxs-lookup"><span data-stu-id="f28af-137">This will update the planned orders with the selected sequence action of either Postpone or Advance.</span></span>  

## <a name="verify-the-sequence-of-the-planned-orders"></a><span data-ttu-id="f28af-138">Comprobar la secuencia de los pedidos planificados</span><span class="sxs-lookup"><span data-stu-id="f28af-138">Verify the sequence of the planned orders</span></span>
1. <span data-ttu-id="f28af-139">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="f28af-139">Close the page.</span></span>
2. <span data-ttu-id="f28af-140">Vaya a Planificación maestra > Planificación maestra > Pedidos planificados.</span><span class="sxs-lookup"><span data-stu-id="f28af-140">Go to Master planning > Master planning > Planned orders.</span></span>
3. <span data-ttu-id="f28af-141">Expanda el cuadro informativo Detalles del artículo.</span><span class="sxs-lookup"><span data-stu-id="f28af-141">Expand the Item details FactBox.</span></span>
4. <span data-ttu-id="f28af-142">Expanda el cuadro informativo Detalles de programación.</span><span class="sxs-lookup"><span data-stu-id="f28af-142">Expand the Schedule details FactBox.</span></span>
5. <span data-ttu-id="f28af-143">En el campo Plan, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="f28af-143">In the Plan field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="f28af-144">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="f28af-144">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="f28af-145">Seleccione MasterPlan.</span><span class="sxs-lookup"><span data-stu-id="f28af-145">Select MasterPlan.</span></span>  
7. <span data-ttu-id="f28af-146">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="f28af-146">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="f28af-147">Use un filtro rápido para filtrar por el campo Código de artículo con el valor 'P300'.</span><span class="sxs-lookup"><span data-stu-id="f28af-147">Use the Quick Filter to filter on the Item number field with a value of 'P300'.</span></span>
    * <span data-ttu-id="f28af-148">Observe que los pedidos se establecen ahora en secuencia según la prioridad de color y tamaño y los pedidos planificados empiezan en la primera fecha de pedido y fecha de entrega.</span><span class="sxs-lookup"><span data-stu-id="f28af-148">Notice that the orders now are sequenced according to the priority of color and size and the planned orders start at the earliest order date and delivery date.</span></span> <span data-ttu-id="f28af-149">Valide la columna Fecha del pedido o la Fecha inicial en el cuadro informativo Detalles de programación.</span><span class="sxs-lookup"><span data-stu-id="f28af-149">Validate the Order date column or the Start date in the Schedule details FactBox.</span></span>  


