---
title: Transferencia de materiales con trabajos kanban
description: Este procedimiento se centra en la ejecución de un trabajo kanban de retirada para transferir materiales.
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanBoardTransferJob
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: bcab5d27d1e5bb2f86910fe083168e7b97c52e2f
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2020
ms.locfileid: "3148820"
---
# <a name="transfer-materials-with-kanban-jobs"></a><span data-ttu-id="83f5f-103">Transferencia de materiales con trabajos kanban</span><span class="sxs-lookup"><span data-stu-id="83f5f-103">Transfer materials with kanban jobs</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="83f5f-104">Este procedimiento se centra en la ejecución de un trabajo kanban de retirada para transferir materiales.</span><span class="sxs-lookup"><span data-stu-id="83f5f-104">This procedure focuses on executing a withdrawal kanban job to transfer materials.</span></span> <span data-ttu-id="83f5f-105">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="83f5f-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="83f5f-106">Este procedimiento va destinado al trabajador de almacén.</span><span class="sxs-lookup"><span data-stu-id="83f5f-106">This procedure is intended for the warehouse worker.</span></span>


## <a name="display-transfer-jobs"></a><span data-ttu-id="83f5f-107">Visualización de trabajos de transferencia</span><span class="sxs-lookup"><span data-stu-id="83f5f-107">Display transfer jobs</span></span>
1. <span data-ttu-id="83f5f-108">Vaya a Control de producción > Kanban > Tablero kanban para trabajos de transferencia.</span><span class="sxs-lookup"><span data-stu-id="83f5f-108">Go to Production control > Kanban > Kanban board for transfer jobs.</span></span>
2. <span data-ttu-id="83f5f-109">Expanda o contraiga la sección Filtros.</span><span class="sxs-lookup"><span data-stu-id="83f5f-109">Expand or collapse the Filters section.</span></span>
    * <span data-ttu-id="83f5f-110">En la sección Filtros, puede especificar qué trabajos desea ver filtrando por el flujo de producción, el nombre de la actividad, el almacén y la ubicación de origen y el almacén y la ubicación de destino.</span><span class="sxs-lookup"><span data-stu-id="83f5f-110">In the Filters section, you can specify what jobs you want to see by filtering on Production flow, Activity name, From warehouse and location, and To warehouse and location.</span></span>  
3. <span data-ttu-id="83f5f-111">En el campo Almacén de origen, escriba "11".</span><span class="sxs-lookup"><span data-stu-id="83f5f-111">In the From warehouse field, type '11'.</span></span>
4. <span data-ttu-id="83f5f-112">En el campo Ubicación de destino, escriba "12".</span><span class="sxs-lookup"><span data-stu-id="83f5f-112">In the To location field, type '12'.</span></span>

## <a name="start-a-transfer-job"></a><span data-ttu-id="83f5f-113">Iniciar un trabajo de transferencia</span><span class="sxs-lookup"><span data-stu-id="83f5f-113">Start a transfer job</span></span>
1. <span data-ttu-id="83f5f-114">En la lista, anule la selección de la fila que esté seleccionada, si la hay.</span><span class="sxs-lookup"><span data-stu-id="83f5f-114">In the list, deselect the selected row - if any.</span></span>
2. <span data-ttu-id="83f5f-115">En la lista, seleccione la fila 4.</span><span class="sxs-lookup"><span data-stu-id="83f5f-115">In the list, select row 4.</span></span>
    * <span data-ttu-id="83f5f-116">Seleccione el primer trabajo con estado Sin planificar.</span><span class="sxs-lookup"><span data-stu-id="83f5f-116">Select the first job with status Not planned.</span></span> <span data-ttu-id="83f5f-117">Asegúrese de que este sea el único trabajo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="83f5f-117">Make sure this is the only job selected.</span></span>  
3. <span data-ttu-id="83f5f-118">Haga clic en Inicio.</span><span class="sxs-lookup"><span data-stu-id="83f5f-118">Click Start.</span></span>
    * <span data-ttu-id="83f5f-119">Observe que el icono indica que el trabajo se ha iniciado.</span><span class="sxs-lookup"><span data-stu-id="83f5f-119">Notice that an icon indicates that the job is started.</span></span>  

## <a name="select-a-second-transfer-job-and-change-quantity"></a><span data-ttu-id="83f5f-120">Selección de un segundo trabajo de transferencia y cambio de cantidad</span><span class="sxs-lookup"><span data-stu-id="83f5f-120">Select a second transfer job and change quantity</span></span>
1. <span data-ttu-id="83f5f-121">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="83f5f-121">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="83f5f-122">Puede tener varios trabajos seleccionados, pero por ahora seleccione la fila 5.</span><span class="sxs-lookup"><span data-stu-id="83f5f-122">You can have multiple jobs selected, but for now select row 5.</span></span>  
2. <span data-ttu-id="83f5f-123">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="83f5f-123">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="83f5f-124">Asegúrese de que el trabajo en el paso anterior es el único seleccionado.</span><span class="sxs-lookup"><span data-stu-id="83f5f-124">Make sure the job in the previous step is the only one selected.</span></span> <span data-ttu-id="83f5f-125">Anule la selección del resto de trabajos.</span><span class="sxs-lookup"><span data-stu-id="83f5f-125">Deselect all other jobs.</span></span>  
3. <span data-ttu-id="83f5f-126">Observe el valor del campo Cantidad de trabajo para hacer referencia a él más adelante.</span><span class="sxs-lookup"><span data-stu-id="83f5f-126">Note the value in the Job quantity field to reference later</span></span>
4. <span data-ttu-id="83f5f-127">Defina la cantidad del trabajo en "30".</span><span class="sxs-lookup"><span data-stu-id="83f5f-127">Set Job quantity to '30'.</span></span>
    * <span data-ttu-id="83f5f-128">¡Observe la advertencia!</span><span class="sxs-lookup"><span data-stu-id="83f5f-128">Notice the warning!</span></span> <span data-ttu-id="83f5f-129">No tiene permiso para transferir 30.</span><span class="sxs-lookup"><span data-stu-id="83f5f-129">You are not allowed to transfer 30.</span></span> <span data-ttu-id="83f5f-130">De acuerdo con la configuración de la regla kanban, solo puede transferir la cantidad original.</span><span class="sxs-lookup"><span data-stu-id="83f5f-130">According to the setup of the kanban rule, you can only transfer the original quantity.</span></span>  
5. <span data-ttu-id="83f5f-131">Use el valor observado previamente en el campo Cantidad de trabajo.</span><span class="sxs-lookup"><span data-stu-id="83f5f-131">Use the value noted previously in the Job quantity field</span></span>
    * <span data-ttu-id="83f5f-132">Defina la cantidad de trabajo en el valor anterior.</span><span class="sxs-lookup"><span data-stu-id="83f5f-132">Set the Job quantity to the previous value.</span></span>  

## <a name="start-the-second-transfer-job"></a><span data-ttu-id="83f5f-133">Inicio del segundo trabajo de transferencia</span><span class="sxs-lookup"><span data-stu-id="83f5f-133">Start the second transfer job</span></span>
1. <span data-ttu-id="83f5f-134">Haga clic en Inicio.</span><span class="sxs-lookup"><span data-stu-id="83f5f-134">Click Start.</span></span>
    * <span data-ttu-id="83f5f-135">Esto iniciará la transferencia del trabajo en la fila 5.</span><span class="sxs-lookup"><span data-stu-id="83f5f-135">This will start the transfer of the job in row 5.</span></span>  

## <a name="complete-both-transfer-jobs"></a><span data-ttu-id="83f5f-136">Finalización de ambos trabajos de transferencia</span><span class="sxs-lookup"><span data-stu-id="83f5f-136">Complete both transfer jobs</span></span>
1. <span data-ttu-id="83f5f-137">En la lista, seleccione la fila 4.</span><span class="sxs-lookup"><span data-stu-id="83f5f-137">In the list, select row 4.</span></span>
    * <span data-ttu-id="83f5f-138">Ahora hay dos trabajos de transferencia seleccionados en la fila 4 y la fila 5.</span><span class="sxs-lookup"><span data-stu-id="83f5f-138">Now two transfer jobs are selected on row 4 and row 5.</span></span>  
2. <span data-ttu-id="83f5f-139">Haga clic en Completar.</span><span class="sxs-lookup"><span data-stu-id="83f5f-139">Click Complete.</span></span>
    * <span data-ttu-id="83f5f-140">Esto completará la transferencia de los dos trabajos.</span><span class="sxs-lookup"><span data-stu-id="83f5f-140">This will complete the transfer of both jobs.</span></span>  

