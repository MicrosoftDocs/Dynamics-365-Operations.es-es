---
title: Desplazamiento de trabajos kanban programados
description: Este procedimiento se centra en mover trabajos kanban de proceso planificados a un período diferente.
author: ChristianRytt
manager: tfehr
ms.date: 11/07/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanJobSchedulingListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2b945cdfa3e013c213e718962499831df126f09b
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5259755"
---
# <a name="move-scheduled-kanban-jobs"></a><span data-ttu-id="d26ee-103">Desplazamiento de trabajos kanban programados</span><span class="sxs-lookup"><span data-stu-id="d26ee-103">Move scheduled kanban jobs</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="d26ee-104">Este procedimiento se centra en mover trabajos kanban de proceso planificados a un período diferente.</span><span class="sxs-lookup"><span data-stu-id="d26ee-104">This procedure focuses on moving planned process kanban jobs to a different period.</span></span> <span data-ttu-id="d26ee-105">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="d26ee-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="d26ee-106">Este procedimiento está pensado para el supervisor de planta o el planificador de producción que trabajan con kanbans.</span><span class="sxs-lookup"><span data-stu-id="d26ee-106">This procedure is intended for the shop floor supervisor or production planner working with kanbans.</span></span>

## <a name="select-scheduled-kanban-jobs"></a><span data-ttu-id="d26ee-107">Selección de trabajos kanban programados.</span><span class="sxs-lookup"><span data-stu-id="d26ee-107">Select scheduled kanban jobs.</span></span> 

1. <span data-ttu-id="d26ee-108">Vaya a **Control de producción > Kanban > Programación de trabajos kanban**.</span><span class="sxs-lookup"><span data-stu-id="d26ee-108">Go to **Production control > Kanban > Kanban job scheduling**.</span></span> 

2. <span data-ttu-id="d26ee-109">En el campo **Celda de trabajo**, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="d26ee-109">In the **Work cell** field, click the drop-down button to open the lookup.</span></span> 

3. <span data-ttu-id="d26ee-110">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="d26ee-110">In the list, mark the selected row.</span></span> 
   - <span data-ttu-id="d26ee-111">Seleccione la celda de trabajo 1250.</span><span class="sxs-lookup"><span data-stu-id="d26ee-111">Select work cell 1250.</span></span> 
4. <span data-ttu-id="d26ee-112">Haga clic en **Seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="d26ee-112">Click **Select**.</span></span> 

5. <span data-ttu-id="d26ee-113">En el campo **Mostrar estado del trabajo**, seleccione **Programado**.</span><span class="sxs-lookup"><span data-stu-id="d26ee-113">In the **Display job status** field, select **Scheduled**.</span></span> <span data-ttu-id="d26ee-114">Esto filtra la lista de trabajos para mostrar solo los trabajos kanban programados.</span><span class="sxs-lookup"><span data-stu-id="d26ee-114">This filters the job list to display only the scheduled kanban jobs.</span></span> 

## <a name="move-kanban-jobs-to-a-different-period"></a><span data-ttu-id="d26ee-115">Desplazamiento de trabajos kanban a otro período diferente.</span><span class="sxs-lookup"><span data-stu-id="d26ee-115">Move kanban jobs to a different period.</span></span> 

1. <span data-ttu-id="d26ee-116">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="d26ee-116">In the list, find and select the desired record.</span></span> <span data-ttu-id="d26ee-117">Seleccione un trabajo con estado de **trabajo Planificado**, por ejemplo, un trabajo programado el 20 de diciembre de 2012, en el campo **Período planificado**.</span><span class="sxs-lookup"><span data-stu-id="d26ee-117">Select a job that has the **Planned job** status, for example, a job scheduled on December 20, 2012 in the **Planned period** field.</span></span> <span data-ttu-id="d26ee-118">A continuación, mueva el trabajo al período anterior.</span><span class="sxs-lookup"><span data-stu-id="d26ee-118">Then move the job to the previous period.</span></span> 

2. <span data-ttu-id="d26ee-119">Haga clic en **Período anterior**.</span><span class="sxs-lookup"><span data-stu-id="d26ee-119">Click **Previous period**.</span></span> 

3. <span data-ttu-id="d26ee-120">Haga clic en **Fin** para mover el trabajo al final de la lista de trabajos como el último trabajo en el período anterior.</span><span class="sxs-lookup"><span data-stu-id="d26ee-120">Click **End** to move the job to the end of the job list as the last job in the previous period.</span></span> 

4. <span data-ttu-id="d26ee-121">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="d26ee-121">In the list, find and select the desired record.</span></span> <span data-ttu-id="d26ee-122">Seleccione un trabajo con estado de **trabajo Planificado**, por ejemplo, un trabajo programado el 18 de diciembre de 2012, en el campo **Período planificado**.</span><span class="sxs-lookup"><span data-stu-id="d26ee-122">Select a job that has the **Planned job** status, for example, a job scheduled on December 18, 2012 in the **Planned period** field.</span></span> <span data-ttu-id="d26ee-123">A continuación, mueva el trabajo al período siguiente.</span><span class="sxs-lookup"><span data-stu-id="d26ee-123">Then move the job to the next period.</span></span> 

5. <span data-ttu-id="d26ee-124">Haga clic en **Período siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d26ee-124">Click **Next period**.</span></span> 

6. <span data-ttu-id="d26ee-125">Haga clic en **Inicio** para mover el trabajo al inicio de la lista de trabajos como el primer trabajo en el período anterior.</span><span class="sxs-lookup"><span data-stu-id="d26ee-125">Click **Start** to move the job to the start of the job list as the first job in the previous period.</span></span> 

## <a name="move-a-job-within-a-period"></a><span data-ttu-id="d26ee-126">Mover un trabajo dentro de un período.</span><span class="sxs-lookup"><span data-stu-id="d26ee-126">Move a job within a period.</span></span> 

1. <span data-ttu-id="d26ee-127">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="d26ee-127">In the list, find and select the desired record.</span></span> <span data-ttu-id="d26ee-128">Seleccione un trabajo con estado Planificado, por ejemplo, el segundo trabajo programado el 19 de diciembre de 2012, en el campo **Período planificado**.</span><span class="sxs-lookup"><span data-stu-id="d26ee-128">Select a job that has the Planned job status, for example, the second job scheduled on December 19, 2012 in the **Planned period** field.</span></span> <span data-ttu-id="d26ee-129">A continuación, mueva el trabajo dentro del período planificado.</span><span class="sxs-lookup"><span data-stu-id="d26ee-129">Then move the job within the planned period.</span></span> 

2. <span data-ttu-id="d26ee-130">Haga clic en **Hacia adelante.**</span><span class="sxs-lookup"><span data-stu-id="d26ee-130">Click **Forward**.</span></span> <span data-ttu-id="d26ee-131">Observe cómo el trabajo baja una línea en la lista.</span><span class="sxs-lookup"><span data-stu-id="d26ee-131">Notice that the job is moved one line down on the list.</span></span> 

3. <span data-ttu-id="d26ee-132">Haga clic en **Regresivo**.</span><span class="sxs-lookup"><span data-stu-id="d26ee-132">Click **Backward**.</span></span> <span data-ttu-id="d26ee-133">Observe cómo el trabajo sube una línea en la lista.</span><span class="sxs-lookup"><span data-stu-id="d26ee-133">Notice that the job is moved one line up on the list.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]