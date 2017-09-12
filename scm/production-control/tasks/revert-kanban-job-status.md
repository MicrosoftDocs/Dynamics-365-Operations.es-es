--- 
title: Invertir estado del trabajo kanban
description: "Este procedimiento se centra en la inversión de un estado de trabajo kanban incorrecto."
author: YuyuScheller
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 55d359232da5f3087b1e6baed182a20da09aeff7
ms.contentlocale: es-es
ms.lasthandoff: 08/29/2017

---
# <a name="revert-kanban-job-status"></a><span data-ttu-id="81e92-103">Invertir estado del trabajo kanban</span><span class="sxs-lookup"><span data-stu-id="81e92-103">Revert kanban job status</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="81e92-104">Este procedimiento se centra en la inversión de un estado de trabajo kanban incorrecto.</span><span class="sxs-lookup"><span data-stu-id="81e92-104">This procedure focuses on reverting an incorrect kanban job status.</span></span> <span data-ttu-id="81e92-105">Esto resulta útil en el caso de que el operador de máquina actualice el trabajo incorrecto o establezca el estado incorrecto por error.</span><span class="sxs-lookup"><span data-stu-id="81e92-105">This is useful in case the machine operator updates the wrong job, or sets the wrong status by mistake.</span></span> <span data-ttu-id="81e92-106">En este procedimiento, un trabajo kanban se registra como preparado por error y el estado se revierte.</span><span class="sxs-lookup"><span data-stu-id="81e92-106">In this procedure, a kanban job is registered as prepared by mistake, and the status is reverted.</span></span> <span data-ttu-id="81e92-107">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="81e92-107">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="81e92-108">Este procedimiento está pensado para el supervisor de planta o el operador de máquina que trabaja en una empresa de lean manufacturing.</span><span class="sxs-lookup"><span data-stu-id="81e92-108">This procedure is intended for the shop supervisor or machine operator working in a lean manufacturing company.</span></span>


## <a name="open-process-board-for-the-work-cell"></a><span data-ttu-id="81e92-109">Abrir el tablero de proceso para la celda de trabajo</span><span class="sxs-lookup"><span data-stu-id="81e92-109">Open process board for the work cell</span></span>
1. <span data-ttu-id="81e92-110">Vaya a Tablero kanban para trabajos de proceso.</span><span class="sxs-lookup"><span data-stu-id="81e92-110">Go to Kanban board for process jobs.</span></span>
2. <span data-ttu-id="81e92-111">En el campo Celda de trabajo, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="81e92-111">In the Work cell field, enter or select a value.</span></span>
    * <span data-ttu-id="81e92-112">Seleccione la celda de trabajo 1260.</span><span class="sxs-lookup"><span data-stu-id="81e92-112">Select work cell 1260.</span></span>  

## <a name="prepare-kanban-job"></a><span data-ttu-id="81e92-113">Preparar el trabajo kanban</span><span class="sxs-lookup"><span data-stu-id="81e92-113">Prepare kanban job</span></span>
1. <span data-ttu-id="81e92-114">Haga clic en Preparar.</span><span class="sxs-lookup"><span data-stu-id="81e92-114">Click Prepare.</span></span>
    * <span data-ttu-id="81e92-115">Si no puede hacer clic en Preparar porque aparece atenuado, asegúrese de que el trabajo kanban seleccionado tiene el estado Planificado, que se indica con el icono de kanban vacío.</span><span class="sxs-lookup"><span data-stu-id="81e92-115">If you can't click Prepare because it is grayed out, make sure that the selected kanban job has status Planned, which is indicated by the empty kanban icon.</span></span> <span data-ttu-id="81e92-116">Si se produce un error en Preparar, asegúrese de que todos los materiales de la Lista de selección están disponibles.</span><span class="sxs-lookup"><span data-stu-id="81e92-116">If Prepare fails, make sure that all materials in the Picking list are available.</span></span>  
2. <span data-ttu-id="81e92-117">En la lista, seleccione el trabajo preparado.</span><span class="sxs-lookup"><span data-stu-id="81e92-117">In the list, select the prepared job.</span></span>
    * <span data-ttu-id="81e92-118">Seleccione el primer trabajo que acaba de preparar.</span><span class="sxs-lookup"><span data-stu-id="81e92-118">Select the first job that you have just prepared.</span></span>  
    * <span data-ttu-id="81e92-119">Observe que el estado de los trabajos es preparado, lo que se indica con un triángulo dentro del icono de kanban.</span><span class="sxs-lookup"><span data-stu-id="81e92-119">Notice that the jobs status is prepared, which is indicated with a triangle inside the kanban icon.</span></span>  

## <a name="revert-the-status-of-the-prepared-kanban-job"></a><span data-ttu-id="81e92-120">Revertir el estado del trabajo kanban preparado</span><span class="sxs-lookup"><span data-stu-id="81e92-120">Revert the status of the prepared kanban job</span></span>
1. <span data-ttu-id="81e92-121">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="81e92-121">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="81e92-122">Seleccione el primer trabajo que se preparó.</span><span class="sxs-lookup"><span data-stu-id="81e92-122">Select the first job that was prepared.</span></span>  
2. <span data-ttu-id="81e92-123">En el panel de acciones, haga clic en Fabricación.</span><span class="sxs-lookup"><span data-stu-id="81e92-123">On the Action Pane, click Manufacture.</span></span>
3. <span data-ttu-id="81e92-124">Haga clic en Revertir estado.</span><span class="sxs-lookup"><span data-stu-id="81e92-124">Click Revert status.</span></span>
    * <span data-ttu-id="81e92-125">Puede usar una regla kanban alternativa cuando las siguientes condiciones sean verdaderas: - La estrategia de reabastecimiento es la misma para ambas reglas.</span><span class="sxs-lookup"><span data-stu-id="81e92-125">You can use an alternative kanban rule when the following conditions are true:  - The replenishment strategy is the same for both rules.</span></span>  <span data-ttu-id="81e92-126">- La versión del flujo de producción es la misma para ambas reglas.</span><span class="sxs-lookup"><span data-stu-id="81e92-126">- The version of the production flow is the same for both rules.</span></span>  <span data-ttu-id="81e92-127">- El producto que se suministra es el mismo para ambas reglas.</span><span class="sxs-lookup"><span data-stu-id="81e92-127">- The product that is supplied is the same for both rules.</span></span>  <span data-ttu-id="81e92-128">- Todas las actividades en sentido descendente configuradas para la última actividad de las reglas kanban debe ser las mismas para ambas reglas.</span><span class="sxs-lookup"><span data-stu-id="81e92-128">- Any downstream activities that are configured for the last activity of the kanban rules must be the same for both rules.</span></span>  <span data-ttu-id="81e92-129">- Se deben configurar las mismas dimensiones de inventario proporcionadas para ambas reglas.</span><span class="sxs-lookup"><span data-stu-id="81e92-129">- The same supplied inventory dimensions must be configured for both rules.</span></span>  <span data-ttu-id="81e92-130">- El estado de la unidad de gestión de material debe ser No asignado.</span><span class="sxs-lookup"><span data-stu-id="81e92-130">- The status of the handling unit must be Not assigned.</span></span>  <span data-ttu-id="81e92-131">- La configuración para kanbans de eventos debe ser la misma.</span><span class="sxs-lookup"><span data-stu-id="81e92-131">- The configuration for event kanbans must be the same.</span></span>  
    * <span data-ttu-id="81e92-132">Asegúrese de que el estado nuevo es Planificado.</span><span class="sxs-lookup"><span data-stu-id="81e92-132">Ensure that the new status is Planned.</span></span>  
4. <span data-ttu-id="81e92-133">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="81e92-133">Click OK.</span></span>
5. <span data-ttu-id="81e92-134">En la lista, desmarque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="81e92-134">In the list, unmark the selected row.</span></span>
    * <span data-ttu-id="81e92-135">Seleccione el mismo trabajo.</span><span class="sxs-lookup"><span data-stu-id="81e92-135">Select the same job.</span></span>  
    * <span data-ttu-id="81e92-136">Observe que el estado del trabajo kanban se revierte a Planificado, lo que se indica con un icono de kanban vacío.</span><span class="sxs-lookup"><span data-stu-id="81e92-136">Notice that the job status for the kanban job is reverted to Planned, which is indicated by an empty kanban icon.</span></span>  


