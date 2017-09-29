--- 
title: "Programar un pedido de producción con programación de operaciones y trabajo"
description: "Este procedimiento se centra en la programación de un pedido de producción con programación de operaciones y programación de trabajos."
author: ChristianRytt
manager: AnnBe
ms.date: 10/27/2016
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
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: d4aac437876862e9f776264fc81f246c820bdf45
ms.contentlocale: es-es
ms.lasthandoff: 08/29/2017

---
# <a name="schedule-a-production-order-with-operations-and-job-scheduling"></a><span data-ttu-id="06594-103">Programar un pedido de producción con programación de operaciones y trabajo</span><span class="sxs-lookup"><span data-stu-id="06594-103">Schedule a production order with operations and job scheduling</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="06594-104">Este procedimiento se centra en la programación de un pedido de producción con programación de operaciones y programación de trabajos.</span><span class="sxs-lookup"><span data-stu-id="06594-104">This procedure focuses on scheduling a production order with operations scheduling and job scheduling.</span></span> <span data-ttu-id="06594-105">No se crea ningún trabajo con la programación de tareas mientras que los trabajos se crean con programación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="06594-105">No jobs are created with operations scheduling whereas jobs are created with job scheduling.</span></span> <span data-ttu-id="06594-106">La empresa de datos de prueba utilizada para crear esta tarea es USMF.</span><span class="sxs-lookup"><span data-stu-id="06594-106">The demo data company used to create this task is USMF.</span></span> <span data-ttu-id="06594-107">Este procedimiento está pensado para el director de producción, el planificador de producción o el supervisor de planta que trabaja en un entorno de fabricación discreto.</span><span class="sxs-lookup"><span data-stu-id="06594-107">This procedure is intended for the production manager, production planner, or shop floor supervisor working in a discrete manufacturing environment.</span></span>


## <a name="create-a-production-order"></a><span data-ttu-id="06594-108">Crear un pedido de producción</span><span class="sxs-lookup"><span data-stu-id="06594-108">Create a production order</span></span>
1. <span data-ttu-id="06594-109">Vaya a Control de producción > Pedidos de producción > Todos los pedidos de producción.</span><span class="sxs-lookup"><span data-stu-id="06594-109">Go to Production control > Production orders > All production orders.</span></span>
2. <span data-ttu-id="06594-110">Haga clic en Nuevo pedido de producción.</span><span class="sxs-lookup"><span data-stu-id="06594-110">Click New production order.</span></span>
3. <span data-ttu-id="06594-111">En el campo Número de artículo, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="06594-111">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="06594-112">Seleccione el número de artículo D0001.</span><span class="sxs-lookup"><span data-stu-id="06594-112">Select Item number D0001.</span></span>  
4. <span data-ttu-id="06594-113">Haga clic en Crear.</span><span class="sxs-lookup"><span data-stu-id="06594-113">Click Create.</span></span>

## <a name="schedule-operations-for-the-production-order"></a><span data-ttu-id="06594-114">Programe operaciones para el pedido de producción</span><span class="sxs-lookup"><span data-stu-id="06594-114">Schedule operations for the production order</span></span>
1. <span data-ttu-id="06594-115">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="06594-115">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="06594-116">Seleccione el pedido de producción que acaba de crear.</span><span class="sxs-lookup"><span data-stu-id="06594-116">Select the production order that you have just created.</span></span> <span data-ttu-id="06594-117">Debe estar en la parte superior de la lista.</span><span class="sxs-lookup"><span data-stu-id="06594-117">It should be at the top of the list.</span></span>      
2. <span data-ttu-id="06594-118">En el panel de acciones, haga clic en Programar.</span><span class="sxs-lookup"><span data-stu-id="06594-118">On the Action Pane, click Schedule.</span></span>
3. <span data-ttu-id="06594-119">Haga clic en Programar operaciones.</span><span class="sxs-lookup"><span data-stu-id="06594-119">Click Schedule operations.</span></span>
4. <span data-ttu-id="06594-120">En el campo Dirección de programación, seleccione “A partir de la fecha de programación”.</span><span class="sxs-lookup"><span data-stu-id="06594-120">In the Scheduling direction field, select 'Forward from scheduling date'.</span></span>
5. <span data-ttu-id="06594-121">En el campo Fecha de programación, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="06594-121">In the Scheduling date field, enter a date.</span></span>
    * <span data-ttu-id="06594-122">Seleccione una fecha futura, por ejemplo, hoy más una semana.</span><span class="sxs-lookup"><span data-stu-id="06594-122">Select a future date, for example, today plus one week.</span></span> <span data-ttu-id="06594-123">Con la dirección de programación seleccionada, el pedido de producción se programará hacia delante a partir de esta fecha.</span><span class="sxs-lookup"><span data-stu-id="06594-123">With the selected Scheduling direction, the production order will be scheduled forward from this date.</span></span>  
6. <span data-ttu-id="06594-124">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="06594-124">Click OK.</span></span>
7. <span data-ttu-id="06594-125">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="06594-125">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="06594-126">Tenga en cuenta que el estado cambia a Programado.</span><span class="sxs-lookup"><span data-stu-id="06594-126">Note that the status is changed to Scheduled.</span></span>  
8. <span data-ttu-id="06594-127">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="06594-127">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="06594-128">Haga clic en Todos los trabajos.</span><span class="sxs-lookup"><span data-stu-id="06594-128">Click All jobs.</span></span>
    * <span data-ttu-id="06594-129">Tenga en cuenta que ningún trabajo se crea con la programación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="06594-129">Note that no jobs are created with operations scheduling.</span></span>  
10. <span data-ttu-id="06594-130">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="06594-130">Close the page.</span></span>

## <a name="schedule-jobs-for-the-production-order"></a><span data-ttu-id="06594-131">Programe tareas para el pedido de producción</span><span class="sxs-lookup"><span data-stu-id="06594-131">Schedule jobs for the production order</span></span>
1. <span data-ttu-id="06594-132">En el panel de acciones, haga clic en Programar.</span><span class="sxs-lookup"><span data-stu-id="06594-132">On the Action Pane, click Schedule.</span></span>
2. <span data-ttu-id="06594-133">Haga clic en Programar trabajos.</span><span class="sxs-lookup"><span data-stu-id="06594-133">Click Schedule jobs.</span></span>
3. <span data-ttu-id="06594-134">En el campo Dirección de programación, seleccione “A partir de la fecha de programación”.</span><span class="sxs-lookup"><span data-stu-id="06594-134">In the Scheduling direction field, select 'Forward from scheduling date'.</span></span>
4. <span data-ttu-id="06594-135">En el campo Fecha de programación, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="06594-135">In the Scheduling date field, enter a date.</span></span>
    * <span data-ttu-id="06594-136">Seleccione una fecha en el futuro, por ejemplo, hoy más una semana.</span><span class="sxs-lookup"><span data-stu-id="06594-136">Select a date in the future, for example, today plus one week.</span></span> <span data-ttu-id="06594-137">Con la dirección de programación seleccionada, el pedido de producción se programará hacia delante a partir de esta fecha.</span><span class="sxs-lookup"><span data-stu-id="06594-137">With the selected Scheduling direction, the production order will be scheduled forward from this date.</span></span>  
5. <span data-ttu-id="06594-138">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="06594-138">Click OK.</span></span>
6. <span data-ttu-id="06594-139">En el panel de acciones, haga clic en Pedido de producción.</span><span class="sxs-lookup"><span data-stu-id="06594-139">On the Action Pane, click Production order.</span></span>
7. <span data-ttu-id="06594-140">Haga clic en Todos los trabajos.</span><span class="sxs-lookup"><span data-stu-id="06594-140">Click All jobs.</span></span>
    * <span data-ttu-id="06594-141">Tenga en cuenta que basándose en la ruta activa, se crean 5 trabajos con la programación de trabajos.</span><span class="sxs-lookup"><span data-stu-id="06594-141">Note that based on the active route, 5 jobs are created with job scheduling.</span></span>  


