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
ms.openlocfilehash: dedfe39a125e6aa6e9f7ffa62f0d7575153103e1
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2019
ms.locfileid: "1835840"
---
# <a name="transfer-materials-with-kanban-jobs"></a><span data-ttu-id="058cf-103">Transferencia de materiales con trabajos kanban</span><span class="sxs-lookup"><span data-stu-id="058cf-103">Transfer materials with kanban jobs</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="058cf-104">Este procedimiento se centra en la ejecución de un trabajo kanban de retirada para transferir materiales.</span><span class="sxs-lookup"><span data-stu-id="058cf-104">This procedure focuses on executing a withdrawal kanban job to transfer materials.</span></span> <span data-ttu-id="058cf-105">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="058cf-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="058cf-106">Este procedimiento va destinado al trabajador de almacén.</span><span class="sxs-lookup"><span data-stu-id="058cf-106">This procedure is intended for the warehouse worker.</span></span>


## <a name="display-transfer-jobs"></a><span data-ttu-id="058cf-107">Visualización de trabajos de transferencia</span><span class="sxs-lookup"><span data-stu-id="058cf-107">Display transfer jobs</span></span>
1. <span data-ttu-id="058cf-108">Vaya a Control de producción > Kanban > Tablero kanban para trabajos de transferencia.</span><span class="sxs-lookup"><span data-stu-id="058cf-108">Go to Production control > Kanban > Kanban board for transfer jobs.</span></span>
2. <span data-ttu-id="058cf-109">Expanda o contraiga la sección Filtros.</span><span class="sxs-lookup"><span data-stu-id="058cf-109">Expand or collapse the Filters section.</span></span>
    * <span data-ttu-id="058cf-110">En la sección Filtros, puede especificar qué trabajos desea ver filtrando por el flujo de producción, el nombre de la actividad, el almacén y la ubicación de origen y el almacén y la ubicación de destino.</span><span class="sxs-lookup"><span data-stu-id="058cf-110">In the Filters section, you can specify what jobs you want to see by filtering on Production flow, Activity name, From warehouse and location, and To warehouse and location.</span></span>  
3. <span data-ttu-id="058cf-111">En el campo Almacén de origen, escriba "11".</span><span class="sxs-lookup"><span data-stu-id="058cf-111">In the From warehouse field, type '11'.</span></span>
4. <span data-ttu-id="058cf-112">En el campo Ubicación de destino, escriba "12".</span><span class="sxs-lookup"><span data-stu-id="058cf-112">In the To location field, type '12'.</span></span>

## <a name="start-a-transfer-job"></a><span data-ttu-id="058cf-113">Iniciar un trabajo de transferencia</span><span class="sxs-lookup"><span data-stu-id="058cf-113">Start a transfer job</span></span>
1. <span data-ttu-id="058cf-114">En la lista, anule la selección de la fila que esté seleccionada, si la hay.</span><span class="sxs-lookup"><span data-stu-id="058cf-114">In the list, deselect the selected row - if any.</span></span>
2. <span data-ttu-id="058cf-115">En la lista, seleccione la fila 4.</span><span class="sxs-lookup"><span data-stu-id="058cf-115">In the list, select row 4.</span></span>
    * <span data-ttu-id="058cf-116">Seleccione el primer trabajo con estado Sin planificar.</span><span class="sxs-lookup"><span data-stu-id="058cf-116">Select the first job with status Not planned.</span></span> <span data-ttu-id="058cf-117">Asegúrese de que este sea el único trabajo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="058cf-117">Make sure this is the only job selected.</span></span>  
3. <span data-ttu-id="058cf-118">Haga clic en Inicio.</span><span class="sxs-lookup"><span data-stu-id="058cf-118">Click Start.</span></span>
    * <span data-ttu-id="058cf-119">Observe que el icono indica que el trabajo se ha iniciado.</span><span class="sxs-lookup"><span data-stu-id="058cf-119">Notice that an icon indicates that the job is started.</span></span>  

## <a name="select-a-second-transfer-job-and-change-quantity"></a><span data-ttu-id="058cf-120">Selección de un segundo trabajo de transferencia y cambio de cantidad</span><span class="sxs-lookup"><span data-stu-id="058cf-120">Select a second transfer job and change quantity</span></span>
1. <span data-ttu-id="058cf-121">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="058cf-121">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="058cf-122">Puede tener varios trabajos seleccionados, pero por ahora seleccione la fila 5.</span><span class="sxs-lookup"><span data-stu-id="058cf-122">You can have multiple jobs selected, but for now select row 5.</span></span>  
2. <span data-ttu-id="058cf-123">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="058cf-123">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="058cf-124">Asegúrese de que el trabajo en el paso anterior es el único seleccionado.</span><span class="sxs-lookup"><span data-stu-id="058cf-124">Make sure the job in the previous step is the only one selected.</span></span> <span data-ttu-id="058cf-125">Anule la selección del resto de trabajos.</span><span class="sxs-lookup"><span data-stu-id="058cf-125">Deselect all other jobs.</span></span>  
3. <span data-ttu-id="058cf-126">Observe el valor del campo Cantidad de trabajo para hacer referencia a él más adelante.</span><span class="sxs-lookup"><span data-stu-id="058cf-126">Note the value in the Job quantity field to reference later</span></span>
4. <span data-ttu-id="058cf-127">Defina la cantidad del trabajo en "30".</span><span class="sxs-lookup"><span data-stu-id="058cf-127">Set Job quantity to '30'.</span></span>
    * <span data-ttu-id="058cf-128">¡Observe la advertencia!</span><span class="sxs-lookup"><span data-stu-id="058cf-128">Notice the warning!</span></span> <span data-ttu-id="058cf-129">No tiene permiso para transferir 30.</span><span class="sxs-lookup"><span data-stu-id="058cf-129">You are not allowed to transfer 30.</span></span> <span data-ttu-id="058cf-130">De acuerdo con la configuración de la regla kanban, solo puede transferir la cantidad original.</span><span class="sxs-lookup"><span data-stu-id="058cf-130">According to the setup of the kanban rule, you can only transfer the original quantity.</span></span>  
5. <span data-ttu-id="058cf-131">Use el valor observado previamente en el campo Cantidad de trabajo.</span><span class="sxs-lookup"><span data-stu-id="058cf-131">Use the value noted previously in the Job quantity field</span></span>
    * <span data-ttu-id="058cf-132">Defina la cantidad de trabajo en el valor anterior.</span><span class="sxs-lookup"><span data-stu-id="058cf-132">Set the Job quantity to the previous value.</span></span>  

## <a name="start-the-second-transfer-job"></a><span data-ttu-id="058cf-133">Inicio del segundo trabajo de transferencia</span><span class="sxs-lookup"><span data-stu-id="058cf-133">Start the second transfer job</span></span>
1. <span data-ttu-id="058cf-134">Haga clic en Inicio.</span><span class="sxs-lookup"><span data-stu-id="058cf-134">Click Start.</span></span>
    * <span data-ttu-id="058cf-135">Esto iniciará la transferencia del trabajo en la fila 5.</span><span class="sxs-lookup"><span data-stu-id="058cf-135">This will start the transfer of the job in row 5.</span></span>  

## <a name="complete-both-transfer-jobs"></a><span data-ttu-id="058cf-136">Finalización de ambos trabajos de transferencia</span><span class="sxs-lookup"><span data-stu-id="058cf-136">Complete both transfer jobs</span></span>
1. <span data-ttu-id="058cf-137">En la lista, seleccione la fila 4.</span><span class="sxs-lookup"><span data-stu-id="058cf-137">In the list, select row 4.</span></span>
    * <span data-ttu-id="058cf-138">Ahora hay dos trabajos de transferencia seleccionados en la fila 4 y la fila 5.</span><span class="sxs-lookup"><span data-stu-id="058cf-138">Now two transfer jobs are selected on row 4 and row 5.</span></span>  
2. <span data-ttu-id="058cf-139">Haga clic en Completar.</span><span class="sxs-lookup"><span data-stu-id="058cf-139">Click Complete.</span></span>
    * <span data-ttu-id="058cf-140">Esto completará la transferencia de los dos trabajos.</span><span class="sxs-lookup"><span data-stu-id="058cf-140">This will complete the transfer of both jobs.</span></span>  

