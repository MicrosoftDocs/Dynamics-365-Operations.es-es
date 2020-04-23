---
title: Ejecutar trabajos de proceso kanban
description: Este procedimiento se centra en la ejecución de trabajos de procesos kanban.
author: ChristianRytt
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanBoardWorkCell, KanbanJobStatusUpdate
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a1c32b577007c400f3528a110436eb97aaabefe2
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2020
ms.locfileid: "3207034"
---
# <a name="execute-kanban-process-jobs"></a><span data-ttu-id="e4db2-103">Ejecutar trabajos de proceso kanban</span><span class="sxs-lookup"><span data-stu-id="e4db2-103">Execute kanban process jobs</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="e4db2-104">Este procedimiento se centra en la ejecución de trabajos de procesos kanban.</span><span class="sxs-lookup"><span data-stu-id="e4db2-104">This procedure focuses on executing kanban process jobs.</span></span> <span data-ttu-id="e4db2-105">El primer trabajo se completa con la cantidad prevista y no tiene errores.</span><span class="sxs-lookup"><span data-stu-id="e4db2-105">The first job is completed with the expected quantity and has no errors.</span></span> <span data-ttu-id="e4db2-106">El segundo trabajo se completa con errores.</span><span class="sxs-lookup"><span data-stu-id="e4db2-106">The second job is completed with errors.</span></span> <span data-ttu-id="e4db2-107">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="e4db2-107">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="e4db2-108">Este procedimiento va destinado al operario de la máquina.</span><span class="sxs-lookup"><span data-stu-id="e4db2-108">This procedure is intended for the machine operator.</span></span>


## <a name="select-a-kanban-job"></a><span data-ttu-id="e4db2-109">Seleccionar un trabajo kanban</span><span class="sxs-lookup"><span data-stu-id="e4db2-109">Select a kanban job</span></span>
1. <span data-ttu-id="e4db2-110">Vaya a Control de producción > Kanban > Tablero kanban para trabajos de proceso.</span><span class="sxs-lookup"><span data-stu-id="e4db2-110">Go to Production control > Kanban > Kanban board for process jobs.</span></span>
2. <span data-ttu-id="e4db2-111">En el campo Celda de trabajo, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="e4db2-111">In the Work cell field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="e4db2-112">Haga clic en la fila con el grupo de recursos 1250.</span><span class="sxs-lookup"><span data-stu-id="e4db2-112">Click the row with resource group 1250.</span></span> <span data-ttu-id="e4db2-113">Esto filtra la lista Trabajos para mostrar únicamente los trabajos para la celda de trabajo 1250.</span><span class="sxs-lookup"><span data-stu-id="e4db2-113">This filters the Jobs list to display only the jobs for work cell 1250.</span></span>
    * <span data-ttu-id="e4db2-114">Marque la fila que tiene el estado de trabajo Planificado.</span><span class="sxs-lookup"><span data-stu-id="e4db2-114">Mark the row that has the Planned job status.</span></span>  

## <a name="complete-a-job-with-expected-quantity"></a><span data-ttu-id="e4db2-115">Completar un trabajo con cantidad prevista</span><span class="sxs-lookup"><span data-stu-id="e4db2-115">Complete a job with expected quantity</span></span>
1. <span data-ttu-id="e4db2-116">Expanda o contraiga la sección Detalles.</span><span class="sxs-lookup"><span data-stu-id="e4db2-116">Expand or collapse the Details section.</span></span>
    * <span data-ttu-id="e4db2-117">En esta sección se muestra información importante sobre el número de la tarjeta, el número de artículo, la cantidad solicitada y el nombre de la actividad.</span><span class="sxs-lookup"><span data-stu-id="e4db2-117">This section displays important information about card number, item number, quantity ordered, and activity name.</span></span>  
2. <span data-ttu-id="e4db2-118">Expanda o contraiga la sección Instrucciones de producción.</span><span class="sxs-lookup"><span data-stu-id="e4db2-118">Expand or collapse the Production instructions section.</span></span>
    * <span data-ttu-id="e4db2-119">En esta sección se muestran las instrucciones de producción para la actividad.</span><span class="sxs-lookup"><span data-stu-id="e4db2-119">This section displays production instructions for the activity.</span></span> <span data-ttu-id="e4db2-120">Las instrucciones pueden ser texto, imágenes, dibujos y otros documentos.</span><span class="sxs-lookup"><span data-stu-id="e4db2-120">The instructions can be text, pictures, drawings, and other documents.</span></span>  
3. <span data-ttu-id="e4db2-121">Haga clic en Inicio.</span><span class="sxs-lookup"><span data-stu-id="e4db2-121">Click Start.</span></span>
    * <span data-ttu-id="e4db2-122">Seleccione un trabajo que no esté completado.</span><span class="sxs-lookup"><span data-stu-id="e4db2-122">Select a job that is not completed.</span></span> <span data-ttu-id="e4db2-123">Utilice iconos de estado en el campo Estado del trabajo para ver el estado del trabajo.</span><span class="sxs-lookup"><span data-stu-id="e4db2-123">Use status icons in the Job status field to view job status.</span></span>      
4. <span data-ttu-id="e4db2-124">Haga clic en Completar.</span><span class="sxs-lookup"><span data-stu-id="e4db2-124">Click Complete.</span></span>
    * <span data-ttu-id="e4db2-125">El trabajo se completa con la calidad prevista.</span><span class="sxs-lookup"><span data-stu-id="e4db2-125">The job is completed with the expected quality.</span></span>  

## <a name="complete-a-job-with-errors"></a><span data-ttu-id="e4db2-126">Completar un trabajo con errores</span><span class="sxs-lookup"><span data-stu-id="e4db2-126">Complete a job with errors</span></span>
1. <span data-ttu-id="e4db2-127">Haga clic en Inicio.</span><span class="sxs-lookup"><span data-stu-id="e4db2-127">Click Start.</span></span>
    * <span data-ttu-id="e4db2-128">Cuando se complete un trabajo, el siguiente trabajo de la lista se selecciona automáticamente.</span><span class="sxs-lookup"><span data-stu-id="e4db2-128">When a job is completed, the next job on the list is selected automatically.</span></span> <span data-ttu-id="e4db2-129">Este es el motivo por el cual no es necesario seleccionar un trabajo antes de hacer clic en Inicio.</span><span class="sxs-lookup"><span data-stu-id="e4db2-129">This is why you don't need to select a job before you click Start.</span></span>  
2. <span data-ttu-id="e4db2-130">En el panel de acciones, haga clic en Fabricación.</span><span class="sxs-lookup"><span data-stu-id="e4db2-130">On the Action Pane, click Manufacture.</span></span>
3. <span data-ttu-id="e4db2-131">Haga clic en Completar (detalles).</span><span class="sxs-lookup"><span data-stu-id="e4db2-131">Click Complete (details).</span></span>
4. <span data-ttu-id="e4db2-132">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="e4db2-132">In the list, mark the selected row.</span></span>
5. <span data-ttu-id="e4db2-133">En el campo Cantidad con errores, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="e4db2-133">In the Error quantity field, enter a number.</span></span>
6. <span data-ttu-id="e4db2-134">En el campo Cantidad sin errores, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="e4db2-134">In the Good quantity field, enter a number.</span></span>
7. <span data-ttu-id="e4db2-135">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="e4db2-135">Click OK.</span></span>

