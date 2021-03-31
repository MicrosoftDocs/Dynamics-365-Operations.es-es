---
title: Programación de trabajos kanban
description: Este procedimiento se centra en programar trabajos kanban de proceso para una celda de trabajo concreta.
author: ChristianRytt
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanJobSchedulingListPage, KanbanPeriodCapacityPart, SysLookupMultiSelectGrid, KanbanBoardScheduleJobForward
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 30f7c431b3d27a534e53540c41768ea55c8dd39f
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5222810"
---
# <a name="schedule-kanban-jobs"></a><span data-ttu-id="21959-103">Programación de trabajos kanban</span><span class="sxs-lookup"><span data-stu-id="21959-103">Schedule kanban jobs</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="21959-104">Este procedimiento se centra en programar trabajos kanban de proceso para una celda de trabajo concreta.</span><span class="sxs-lookup"><span data-stu-id="21959-104">This procedure focuses on scheduling process kanban jobs for a specific work cell.</span></span> <span data-ttu-id="21959-105">El procedimiento de preparación de un trabajo kanban de proceso cuando los materiales no están disponibles es requisito para poder crear este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="21959-105">The procedure "Prepare a process kanban job when materials are not available" is a prerequisite for creating this procedure.</span></span> <span data-ttu-id="21959-106">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="21959-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="21959-107">Esta tarea está pensada para el supervisor de planta y el planificador de producción que trabajan con kanbans.</span><span class="sxs-lookup"><span data-stu-id="21959-107">This task is intended for the shop floor supervisor and production planner working with kanbans.</span></span>


## <a name="select-kanban-jobs-for-a-work-cell"></a><span data-ttu-id="21959-108">Selección de trabajos kanban para una celda de trabajo</span><span class="sxs-lookup"><span data-stu-id="21959-108">Select kanban jobs for a work cell</span></span>
1. <span data-ttu-id="21959-109">Vaya a Control de producción > Kanban > Programación de trabajos kanban.</span><span class="sxs-lookup"><span data-stu-id="21959-109">Go to Production control > Kanban > Kanban job scheduling.</span></span>
2. <span data-ttu-id="21959-110">Expansión del cuadro informativo Capacidad de período</span><span class="sxs-lookup"><span data-stu-id="21959-110">Expand the Period capacity fact box</span></span>
    * <span data-ttu-id="21959-111">Expanda el cuadro informativo Kanban.</span><span class="sxs-lookup"><span data-stu-id="21959-111">Expand the Kanban FactBox.</span></span>  
3. <span data-ttu-id="21959-112">En el campo Celda de trabajo, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="21959-112">In the Work cell field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="21959-113">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="21959-113">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="21959-114">Seleccione la celda de trabajo 1250.</span><span class="sxs-lookup"><span data-stu-id="21959-114">Select work cell 1250.</span></span> <span data-ttu-id="21959-115">Esto filtrará la vista para mostrar únicamente los trabajos para la celda de trabajo 1250.</span><span class="sxs-lookup"><span data-stu-id="21959-115">This will filter the view to display only the jobs for work cell 1250.</span></span>  
5. <span data-ttu-id="21959-116">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="21959-116">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="21959-117">Haga clic en Seleccionar.</span><span class="sxs-lookup"><span data-stu-id="21959-117">Click Select.</span></span>

## <a name="schedule-a-kanban-job-in-the-first-available-period"></a><span data-ttu-id="21959-118">Programación de un trabajo kanban para el primer período disponible</span><span class="sxs-lookup"><span data-stu-id="21959-118">Schedule a kanban job in the first available period</span></span>
1. <span data-ttu-id="21959-119">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="21959-119">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="21959-120">Seleccione la primera fila de la lista con estado Sin planificar.</span><span class="sxs-lookup"><span data-stu-id="21959-120">Select the first row in the list that has the Not planned status.</span></span> <span data-ttu-id="21959-121">El icono punteado en el campo Estado de trabajo indica que no ha sido planificado.</span><span class="sxs-lookup"><span data-stu-id="21959-121">The dotted icon in the Job status field indicates not planned.</span></span>  
2. <span data-ttu-id="21959-122">Haga clic en Programar.</span><span class="sxs-lookup"><span data-stu-id="21959-122">Click Schedule.</span></span>
    * <span data-ttu-id="21959-123">Esto programará el trabajo kanban para el primer período disponible.</span><span class="sxs-lookup"><span data-stu-id="21959-123">This will schedule the kanban job in the first available period.</span></span>  
    * <span data-ttu-id="21959-124">Tenga en cuenta que el trabajo kanban se ha movido al final de la lista porque se ha agregado al período a partir de hoy.</span><span class="sxs-lookup"><span data-stu-id="21959-124">Notice that the kanban job is moved to the end of the list because it has been added to the period starting from today.</span></span>  
    * <span data-ttu-id="21959-125">Si el período a partir de hoy está reservado por completo, el trabajo se moverá al primer período disponible.</span><span class="sxs-lookup"><span data-stu-id="21959-125">If the period starting from today is fully booked, the job will be moved to the first available period.</span></span>  

## <a name="schedule-two-kanban-jobs-for-a-specific-day"></a><span data-ttu-id="21959-126">Programación de dos trabajos kanban para un día concreto</span><span class="sxs-lookup"><span data-stu-id="21959-126">Schedule two kanban jobs for a specific day</span></span>
1. <span data-ttu-id="21959-127">En la lista, seleccione la fila 1.</span><span class="sxs-lookup"><span data-stu-id="21959-127">In the list, select row 1.</span></span>
    * <span data-ttu-id="21959-128">Debe ver que la primera fila tiene el estado Sin planificar en el campo Estado del trabajo.</span><span class="sxs-lookup"><span data-stu-id="21959-128">You should see that the first row has the Not planned status in the Job status field.</span></span>  
2. <span data-ttu-id="21959-129">En la lista, seleccione la fila 2.</span><span class="sxs-lookup"><span data-stu-id="21959-129">In the list, select row 2.</span></span>
    * <span data-ttu-id="21959-130">Debe ver que la segunda fila tiene el estado Sin planificar en el campo Estado del trabajo.</span><span class="sxs-lookup"><span data-stu-id="21959-130">You should see that the second row has the Not planned status in the Job status field.</span></span> <span data-ttu-id="21959-131">Ahora tiene los dos primeros trabajos seleccionados.</span><span class="sxs-lookup"><span data-stu-id="21959-131">Now you have the first two jobs selected.</span></span>  
3. <span data-ttu-id="21959-132">Haga clic en Programar a partir de la fecha para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="21959-132">Click Schedule from date to open the drop dialog.</span></span>
4. <span data-ttu-id="21959-133">Marque la casilla Omitir reacción por escasez de capacidad, o bien quite la marca, según el caso.</span><span class="sxs-lookup"><span data-stu-id="21959-133">Check or uncheck the Override capacity shortage reaction box.</span></span>
    * <span data-ttu-id="21959-134">Esta opción permite anular la reacción por escasez de capacidad predeterminada.</span><span class="sxs-lookup"><span data-stu-id="21959-134">This option allows you to override the default capacity shortage reaction.</span></span>  
5. <span data-ttu-id="21959-135">En el campo Reacción por escasez de capacidad, seleccione Agregar al período solicitado.</span><span class="sxs-lookup"><span data-stu-id="21959-135">In the Capacity shortage reaction field, select 'Add to the requested period'.</span></span>
    * <span data-ttu-id="21959-136">Esta opción garantizará que el trabajo se agregue al período solicitado, independientemente de que la celda de trabajo pueda estar sobrecargada.</span><span class="sxs-lookup"><span data-stu-id="21959-136">This option will ensure that the job is added to the requested period, regardless if the work cell might be overloaded.</span></span>  
6. <span data-ttu-id="21959-137">Haga clic en Programar.</span><span class="sxs-lookup"><span data-stu-id="21959-137">Click Schedule.</span></span>
    * <span data-ttu-id="21959-138">Observe que los dos trabajos se han agregado al período deseado.</span><span class="sxs-lookup"><span data-stu-id="21959-138">Notice that both jobs are added to the desired period.</span></span>  
    * <span data-ttu-id="21959-139">En la sección de la Capacidad de período puede ver la carga para cada período.</span><span class="sxs-lookup"><span data-stu-id="21959-139">In the Period capacity section, you can see the load for each period.</span></span> <span data-ttu-id="21959-140">El campo Consumo muestra el consumo programado en este período.</span><span class="sxs-lookup"><span data-stu-id="21959-140">The Consumption field shows the scheduled consumption in this period.</span></span> <span data-ttu-id="21959-141">Si el consumo programado es superior a la capacidad disponible en este período, se seleccionará el consumo sobrecargado.</span><span class="sxs-lookup"><span data-stu-id="21959-141">If the scheduled consumption is higher than the available capacity in this period, the overloaded consumption will be selected.</span></span>  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]