---
title: Secuenciar trabajos de producción para fabricación en procesos
description: Este procedimiento usa productos de pintura como ejemplo para mostrar cómo establecer la secuencia de los pedidos planificados según la prioridad de color y tamaño de paquete.
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqTransPo, PMFSeqReqRouteChangesListPage
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4e064f55ed451d44f58e60ba0aa722166981c129
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1571505"
---
# <a name="sequence-production-jobs-for-process-manufacturing"></a><span data-ttu-id="ca288-103">Secuenciar trabajos de producción para fabricación en procesos</span><span class="sxs-lookup"><span data-stu-id="ca288-103">Sequence production jobs for process manufacturing</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="ca288-104">Este procedimiento usa productos de pintura como ejemplo para mostrar cómo establecer la secuencia de los pedidos planificados según la prioridad de color y tamaño de paquete.</span><span class="sxs-lookup"><span data-stu-id="ca288-104">This procedure uses paint products as an example to show how to sequence planned orders according to the priority of color and package size.</span></span> <span data-ttu-id="ca288-105">La empresa de datos de prueba utilizada para crear este procedimiento es USPI.</span><span class="sxs-lookup"><span data-stu-id="ca288-105">The demo data company used to create this procedure is USPI.</span></span> <span data-ttu-id="ca288-106">Este procedimiento se va a utilizar para el planificador de producción.</span><span class="sxs-lookup"><span data-stu-id="ca288-106">This procedure is intended for the production planner.</span></span>


## <a name="run-master-planning-for-uspi"></a><span data-ttu-id="ca288-107">Ejecutar planificación maestra para USPI</span><span class="sxs-lookup"><span data-stu-id="ca288-107">Run master planning for USPI</span></span>
1. <span data-ttu-id="ca288-108">Vaya a Planificación maestra > Planificación maestra > Ejecutar > lanificación maestra.</span><span class="sxs-lookup"><span data-stu-id="ca288-108">Go to Master planning > Master planning > Run > Master planning.</span></span>
2. <span data-ttu-id="ca288-109">En el campo Plan maestro, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="ca288-109">In the Master plan field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="ca288-110">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="ca288-110">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="ca288-111">Seleccione MasterPlan.</span><span class="sxs-lookup"><span data-stu-id="ca288-111">Select MasterPlan.</span></span>  
4. <span data-ttu-id="ca288-112">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="ca288-112">Click OK.</span></span>
    * <span data-ttu-id="ca288-113">Esto inicia la Planificación maestra, incluido el proceso de la secuencia.</span><span class="sxs-lookup"><span data-stu-id="ca288-113">This starts Master Planning, including the sequence process.</span></span> <span data-ttu-id="ca288-114">El proceso puede tardar unos minutos.</span><span class="sxs-lookup"><span data-stu-id="ca288-114">This process can take a few minutes.</span></span>  

## <a name="view-planned-orders-for-the-paint-products"></a><span data-ttu-id="ca288-115">Ver pedidos planificados para los productos de pintura</span><span class="sxs-lookup"><span data-stu-id="ca288-115">View planned orders for the paint products</span></span>
1. <span data-ttu-id="ca288-116">Vaya a Planificación maestra > Planificación maestra > Pedidos planificados.</span><span class="sxs-lookup"><span data-stu-id="ca288-116">Go to Master planning > Master planning > Planned orders.</span></span>
2. <span data-ttu-id="ca288-117">Expanda el cuadro informativo Detalles del artículo.</span><span class="sxs-lookup"><span data-stu-id="ca288-117">Expand the Item details FactBox.</span></span>
3. <span data-ttu-id="ca288-118">Expanda el cuadro informativo Detalles de programación.</span><span class="sxs-lookup"><span data-stu-id="ca288-118">Expand the Schedule details FactBox.</span></span>
4. <span data-ttu-id="ca288-119">En el campo Plan, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="ca288-119">In the Plan field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="ca288-120">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="ca288-120">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="ca288-121">Seleccione MasterPlan.</span><span class="sxs-lookup"><span data-stu-id="ca288-121">Select MasterPlan.</span></span>  
6. <span data-ttu-id="ca288-122">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="ca288-122">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="ca288-123">Use un filtro rápido para filtrar por el campo Código de artículo con el valor 'P300'.</span><span class="sxs-lookup"><span data-stu-id="ca288-123">Use the Quick Filter to filter on the Item number field with a value of 'P300'.</span></span>
    * <span data-ttu-id="ca288-124">Desbloquee para desplazarse a la derecha para ver la fecha de la orden y la fecha de entrega.</span><span class="sxs-lookup"><span data-stu-id="ca288-124">Unlock to scroll to the right to see the order date and delivery date.</span></span> <span data-ttu-id="ca288-125">Observe que estos artículos tienen una fecha de pedido de Hoy y las fechas de entrega para los pedidos planificados no están establecidas en frecuencia tras la prioridad de color y el tamaño del paquete, como se muestra en el nombre del producto.</span><span class="sxs-lookup"><span data-stu-id="ca288-125">Notice that these items have an order date of Today and the delivery dates for the planned orders are not sequenced after the priority of color and package size, as shown in the product name.</span></span> <span data-ttu-id="ca288-126">Puede mantener el puntero sobre un número de artículo para ver el nombre del producto y la prioridad.</span><span class="sxs-lookup"><span data-stu-id="ca288-126">You can hover over an item number to see the product name and priority.</span></span>  

## <a name="sequence-planned-orders-for-paint"></a><span data-ttu-id="ca288-127">Establecer en secuencia pedidos planificados para pintura</span><span class="sxs-lookup"><span data-stu-id="ca288-127">Sequence planned orders for paint</span></span>
1. <span data-ttu-id="ca288-128">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="ca288-128">Close the page.</span></span>
2. <span data-ttu-id="ca288-129">Vaya a Planificación maestra > Planificación maestra > Pedidos planificados en secuencia.</span><span class="sxs-lookup"><span data-stu-id="ca288-129">Go to Master planning > Master planning > Sequenced planned orders.</span></span>
3. <span data-ttu-id="ca288-130">Expanda el cuadro informativo Detalles del artículo.</span><span class="sxs-lookup"><span data-stu-id="ca288-130">Expand the Item details FactBox.</span></span>
4. <span data-ttu-id="ca288-131">Expanda el cuadro informativo Detalles de programación.</span><span class="sxs-lookup"><span data-stu-id="ca288-131">Expand the Schedule details FactBox.</span></span>
    * <span data-ttu-id="ca288-132">Nota: Aquí ve que la fecha y la hora iniciales para los pedidos planificados se establecen en secuencia de acuerdo con el color y el tamaño del paquete dentro de un período de cubo de 28 días.</span><span class="sxs-lookup"><span data-stu-id="ca288-132">Note: Here you see that the Start date/time for the planned orders are sequenced according to color and package size within a bucket period of 28 days.</span></span> <span data-ttu-id="ca288-133">Estos períodos se definen por un número en el campo Campaña.</span><span class="sxs-lookup"><span data-stu-id="ca288-133">These periods are defined by a number in the field Campaign.</span></span> <span data-ttu-id="ca288-134">El formulario de pedido planificado secuenciado actúa como el formulario de pedido planificado típico y el planificador de producción puede poner en firme los pedidos planificados aquí.</span><span class="sxs-lookup"><span data-stu-id="ca288-134">The sequenced planned order form acts like the typical planned order form, and the production planner can firm the planned orders here.</span></span>  
5. <span data-ttu-id="ca288-135">Marca todas las filas.</span><span class="sxs-lookup"><span data-stu-id="ca288-135">Mark all rows.</span></span>
6. <span data-ttu-id="ca288-136">Haga clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="ca288-136">Click Accept.</span></span>
    * <span data-ttu-id="ca288-137">Esto actualizará los pedidos planificados con la acción de secuencia seleccionada de Posponer o Adelantar.</span><span class="sxs-lookup"><span data-stu-id="ca288-137">This will update the planned orders with the selected sequence action of either Postpone or Advance.</span></span>  

## <a name="verify-the-sequence-of-the-planned-orders"></a><span data-ttu-id="ca288-138">Comprobar la secuencia de los pedidos planificados</span><span class="sxs-lookup"><span data-stu-id="ca288-138">Verify the sequence of the planned orders</span></span>
1. <span data-ttu-id="ca288-139">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="ca288-139">Close the page.</span></span>
2. <span data-ttu-id="ca288-140">Vaya a Planificación maestra > Planificación maestra > Pedidos planificados.</span><span class="sxs-lookup"><span data-stu-id="ca288-140">Go to Master planning > Master planning > Planned orders.</span></span>
3. <span data-ttu-id="ca288-141">Expanda el cuadro informativo Detalles del artículo.</span><span class="sxs-lookup"><span data-stu-id="ca288-141">Expand the Item details FactBox.</span></span>
4. <span data-ttu-id="ca288-142">Expanda el cuadro informativo Detalles de programación.</span><span class="sxs-lookup"><span data-stu-id="ca288-142">Expand the Schedule details FactBox.</span></span>
5. <span data-ttu-id="ca288-143">En el campo Plan, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="ca288-143">In the Plan field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="ca288-144">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="ca288-144">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="ca288-145">Seleccione MasterPlan.</span><span class="sxs-lookup"><span data-stu-id="ca288-145">Select MasterPlan.</span></span>  
7. <span data-ttu-id="ca288-146">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="ca288-146">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="ca288-147">Use un filtro rápido para filtrar por el campo Código de artículo con el valor 'P300'.</span><span class="sxs-lookup"><span data-stu-id="ca288-147">Use the Quick Filter to filter on the Item number field with a value of 'P300'.</span></span>
    * <span data-ttu-id="ca288-148">Observe que los pedidos se establecen ahora en secuencia según la prioridad de color y tamaño y los pedidos planificados empiezan en la primera fecha de pedido y fecha de entrega.</span><span class="sxs-lookup"><span data-stu-id="ca288-148">Notice that the orders now are sequenced according to the priority of color and size and the planned orders start at the earliest order date and delivery date.</span></span> <span data-ttu-id="ca288-149">Valide la columna Fecha del pedido o la Fecha inicial en el cuadro desplegable Detalles de programación.</span><span class="sxs-lookup"><span data-stu-id="ca288-149">Validate the Order date column or the Start date in the Schedule details FactBbox.</span></span>  

