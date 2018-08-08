--- 
title: Desplazamiento de trabajos kanban programados
description: "Este procedimiento se centra en mover trabajos kanban de proceso planificados a un período diferente."
author: ChristianRytt
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 6461e5638eaddeaeaef82304b7976bad350b331e
ms.contentlocale: es-es
ms.lasthandoff: 08/07/2018

---
# <a name="move-scheduled-kanban-jobs"></a><span data-ttu-id="bc92d-103">Desplazamiento de trabajos kanban programados</span><span class="sxs-lookup"><span data-stu-id="bc92d-103">Move scheduled kanban jobs</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="bc92d-104">Este procedimiento se centra en mover trabajos kanban de proceso planificados a un período diferente.</span><span class="sxs-lookup"><span data-stu-id="bc92d-104">This procedure focuses on moving planned process kanban jobs to a different period.</span></span> <span data-ttu-id="bc92d-105">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="bc92d-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="bc92d-106">Este procedimiento está pensado para el supervisor de planta o el planificador de producción que trabajan con kanbans.</span><span class="sxs-lookup"><span data-stu-id="bc92d-106">This procedure is intended for the shop floor supervisor or production planner working with kanbans.</span></span>


## <a name="select-scheduled-kanban-jobs"></a><span data-ttu-id="bc92d-107">Selección de trabajos kanban programados</span><span class="sxs-lookup"><span data-stu-id="bc92d-107">Select scheduled kanban jobs</span></span>
1. <span data-ttu-id="bc92d-108">Gå til Produktionsstyring > Kanban > Tidsplanlægning af kanban-job.</span><span class="sxs-lookup"><span data-stu-id="bc92d-108">Gå til Produktionsstyring > Kanban > Tidsplanlægning af kanban-job.</span></span>
2. <span data-ttu-id="bc92d-109">!MtCMR!En el campo Celda de trabajo, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="bc92d-109">!MtCMR!In the Work cell field, click the drop-down button to open the lookup.</span></span> <span data-ttu-id="bc92d-110">áçêìõý !</span><span class="sxs-lookup"><span data-stu-id="bc92d-110">áçêìõý !</span></span>
3. <span data-ttu-id="bc92d-111">Markér den valgte række på listen.</span><span class="sxs-lookup"><span data-stu-id="bc92d-111">Markér den valgte række på listen.</span></span>
    * <span data-ttu-id="bc92d-112">Seleccione la celda de trabajo 1250.</span><span class="sxs-lookup"><span data-stu-id="bc92d-112">Select work cell 1250.</span></span>  
4. <span data-ttu-id="bc92d-113">Klik på Select.</span><span class="sxs-lookup"><span data-stu-id="bc92d-113">Klik på Select.</span></span>
5. <span data-ttu-id="bc92d-114">Vælg 'Planlagt' i feltet Display job status.</span><span class="sxs-lookup"><span data-stu-id="bc92d-114">Vælg 'Planlagt' i feltet Display job status.</span></span>
    * <span data-ttu-id="bc92d-115">Esto filtra la lista de trabajos para mostrar solo los trabajos kanban programados.</span><span class="sxs-lookup"><span data-stu-id="bc92d-115">This filters the job list to display only the scheduled kanban jobs.</span></span>  

## <a name="move-kanban-jobs-to-a-different-period"></a><span data-ttu-id="bc92d-116">Desplazamiento de trabajos kanban a otro período diferente</span><span class="sxs-lookup"><span data-stu-id="bc92d-116">Move kanban jobs to a different period</span></span>
1. <span data-ttu-id="bc92d-117">Find og vælg den ønskede post på listen.</span><span class="sxs-lookup"><span data-stu-id="bc92d-117">Find og vælg den ønskede post på listen.</span></span>
    * <span data-ttu-id="bc92d-118">Seleccione un trabajo con estado de trabajo Planificado, por ejemplo, un trabajo programado el 20 de diciembre de 2012, en el campo Período planificado.</span><span class="sxs-lookup"><span data-stu-id="bc92d-118">Select a job that has the Planned job status, for example, a job scheduled on December 20, 2012  in the Planned period field.</span></span> <span data-ttu-id="bc92d-119">A continuación, mueva el trabajo al período anterior.</span><span class="sxs-lookup"><span data-stu-id="bc92d-119">Then move the job to the previous period.</span></span>  
2. <span data-ttu-id="bc92d-120">Klik på Previous period.</span><span class="sxs-lookup"><span data-stu-id="bc92d-120">Klik på Previous period.</span></span>
3. <span data-ttu-id="bc92d-121">Klik på End.</span><span class="sxs-lookup"><span data-stu-id="bc92d-121">Klik på End.</span></span>
    * <span data-ttu-id="bc92d-122">Esto moverá el trabajo al final de la lista de trabajos como el último trabajo en el período anterior.</span><span class="sxs-lookup"><span data-stu-id="bc92d-122">This will move the job to the end of the job list as the last job in the previous period.</span></span>  
4. <span data-ttu-id="bc92d-123">Find og vælg den ønskede post på listen.</span><span class="sxs-lookup"><span data-stu-id="bc92d-123">Find og vælg den ønskede post på listen.</span></span>
    * <span data-ttu-id="bc92d-124">Seleccione un trabajo con estado de trabajo Planificado, por ejemplo, un trabajo programado el 18 de diciembre de 2012 en el campo Período planificado.</span><span class="sxs-lookup"><span data-stu-id="bc92d-124">Select a job that has the Planned job status, for example, a job scheduled on December 18, 2012 in the Planned period field.</span></span> <span data-ttu-id="bc92d-125">A continuación, mueva el trabajo al período siguiente.</span><span class="sxs-lookup"><span data-stu-id="bc92d-125">Then move the job to the next period.</span></span>  
5. <span data-ttu-id="bc92d-126">Klik på Next period.</span><span class="sxs-lookup"><span data-stu-id="bc92d-126">Klik på Next period.</span></span>
6. <span data-ttu-id="bc92d-127">Klik på Start.</span><span class="sxs-lookup"><span data-stu-id="bc92d-127">Klik på Start.</span></span>
    * <span data-ttu-id="bc92d-128">Esto moverá el trabajo al inicio de la lista de trabajos como el primer trabajo en el período anterior.</span><span class="sxs-lookup"><span data-stu-id="bc92d-128">This will move the job to the start of the job list as the first job in the previous period.</span></span>  

## <a name="task-move-a-job-within-a-period"></a><span data-ttu-id="bc92d-129">Tarea: Mover un trabajo dentro de un período</span><span class="sxs-lookup"><span data-stu-id="bc92d-129">Task: Move a job within a period</span></span>
1. <span data-ttu-id="bc92d-130">Find og vælg den ønskede post på listen.</span><span class="sxs-lookup"><span data-stu-id="bc92d-130">Find og vælg den ønskede post på listen.</span></span>
    * <span data-ttu-id="bc92d-131">Seleccione un trabajo con estado Planificado, por ejemplo, el segundo trabajo programado el 19 de diciembre de 2012, en el campo Período planificado.</span><span class="sxs-lookup"><span data-stu-id="bc92d-131">Select a job that has the Planned job status, for example, the second job scheduled on December 19, 2012 in the Planned period field.</span></span> <span data-ttu-id="bc92d-132">A continuación, mueva el trabajo dentro del período planificado.</span><span class="sxs-lookup"><span data-stu-id="bc92d-132">Then move the job within the planned period.</span></span>  
2. <span data-ttu-id="bc92d-133">Klik på Forward.</span><span class="sxs-lookup"><span data-stu-id="bc92d-133">Klik på Forward.</span></span>
    * <span data-ttu-id="bc92d-134">Observe cómo el trabajo baja una línea en la lista.</span><span class="sxs-lookup"><span data-stu-id="bc92d-134">Notice that the job is moved one line down on the list.</span></span>  
3. <span data-ttu-id="bc92d-135">Klik på Backward.</span><span class="sxs-lookup"><span data-stu-id="bc92d-135">Klik på Backward.</span></span>
    * <span data-ttu-id="bc92d-136">Observe cómo el trabajo sube una línea en la lista.</span><span class="sxs-lookup"><span data-stu-id="bc92d-136">Notice that the job is moved one line up on the list.</span></span>  


