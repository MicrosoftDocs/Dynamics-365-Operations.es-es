--- 
title: "Preparación de un trabajo kanban de proceso cuando los materiales no están disponibles para la celda de trabajo"
description: "Este procedimiento se centra en la preparación de un trabajo kanban de proceso cuando algunos materiales no están disponibles para la celda de trabajo, por lo que es necesario seleccionar materiales del almacén."
author: ChristianRytt
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 5a47af6910a9686e74ab6d1069dd02079e60cb8a
ms.contentlocale: es-es
ms.lasthandoff: 08/29/2017

---
# <a name="prepare-a-process-kanban-job-when-materials-are-not-available-for-the-work-cell"></a><span data-ttu-id="f05ac-103">Preparación de un trabajo kanban de proceso cuando los materiales no están disponibles para la celda de trabajo</span><span class="sxs-lookup"><span data-stu-id="f05ac-103">Prepare a process kanban job when materials are not available for the work cell</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f05ac-104">Este procedimiento se centra en la preparación de un trabajo kanban de proceso cuando algunos materiales no están disponibles para la celda de trabajo, por lo que es necesario seleccionar materiales del almacén.</span><span class="sxs-lookup"><span data-stu-id="f05ac-104">This procedure focuses on preparing a process kanban job when some materials are not available for the work cell, therefore it's necessary to pick materials from the warehouse.</span></span> <span data-ttu-id="f05ac-105">Para poder crear este procedimiento, es preciso haber realizado el procedimiento de preparación de un trabajo kanban de proceso cuando los materiales están disponibles.</span><span class="sxs-lookup"><span data-stu-id="f05ac-105">The procedure "Prepare a process kanban job when materials are available" is a prerequisite for creating this procedure.</span></span> <span data-ttu-id="f05ac-106">Este procedimiento va destinado al operario de la máquina.</span><span class="sxs-lookup"><span data-stu-id="f05ac-106">This procedure is intended for the machine operator.</span></span> <span data-ttu-id="f05ac-107">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="f05ac-107">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="f05ac-108">Vaya a Control de producción > Kanban > Tablero kanban para trabajos de proceso.</span><span class="sxs-lookup"><span data-stu-id="f05ac-108">Go to Production control > Kanban > Kanban board for process jobs.</span></span>
2. <span data-ttu-id="f05ac-109">En el campo Celda de trabajo, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="f05ac-109">In the Work cell field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="f05ac-110">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="f05ac-110">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="f05ac-111">Seleccione la celda de trabajo 1250.</span><span class="sxs-lookup"><span data-stu-id="f05ac-111">Select work cell 1250.</span></span>  
4. <span data-ttu-id="f05ac-112">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="f05ac-112">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="f05ac-113">Seleccione Kanban 000356.</span><span class="sxs-lookup"><span data-stu-id="f05ac-113">Select Kanban 000356.</span></span>  
5. <span data-ttu-id="f05ac-114">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="f05ac-114">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="f05ac-115">En la lista, desmarque la fila 4.</span><span class="sxs-lookup"><span data-stu-id="f05ac-115">In the list, deselect row 4.</span></span> <span data-ttu-id="f05ac-116">o seleccione la fila 4 si no ha completado la tarea de "Preparación de un proceso de trabajo kanban cuando los materiales están disponibles".</span><span class="sxs-lookup"><span data-stu-id="f05ac-116">or Select row 4 if you haven't completed the task "Prepare a process kanban job when materials are available."</span></span>  
6. <span data-ttu-id="f05ac-117">Expanda la sección de la lista de selección.</span><span class="sxs-lookup"><span data-stu-id="f05ac-117">Toggle the expansion of the Picking list section.</span></span>
    * <span data-ttu-id="f05ac-118">El icono de prohibido en el estado de suministro indica que faltan 48 unidades del artículo P0002 para la celda de trabajo.</span><span class="sxs-lookup"><span data-stu-id="f05ac-118">The No entry icon in the supply status indicates that 48 ea of item P0002 are missing for the work cell.</span></span>  

## <a name="transfer-materials-to-work-cell"></a><span data-ttu-id="f05ac-119">Transferencia de materiales a la celda de trabajo</span><span class="sxs-lookup"><span data-stu-id="f05ac-119">Transfer materials to work cell</span></span>
1. <span data-ttu-id="f05ac-120">Expanda la sección Transferir trabajos.</span><span class="sxs-lookup"><span data-stu-id="f05ac-120">Toggle the expansion of the Transfer jobs section.</span></span>
2. <span data-ttu-id="f05ac-121">Use un filtro rápido para filtrar por el campo Código de artículo con el valor 'P0002'.</span><span class="sxs-lookup"><span data-stu-id="f05ac-121">Use the Quick Filter to filter on the Item number field with a value of 'P0002'.</span></span>
3. <span data-ttu-id="f05ac-122">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="f05ac-122">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="f05ac-123">Haga clic en Inicio.</span><span class="sxs-lookup"><span data-stu-id="f05ac-123">Click Start.</span></span>
    * <span data-ttu-id="f05ac-124">El proceso de transferencia está en curso.</span><span class="sxs-lookup"><span data-stu-id="f05ac-124">Transfer is in progress.</span></span>  
5. <span data-ttu-id="f05ac-125">Haga clic en Completar.</span><span class="sxs-lookup"><span data-stu-id="f05ac-125">Click Complete.</span></span>
    * <span data-ttu-id="f05ac-126">El artículo P0002 está ahora disponible en la lista de selección para el trabajo kanban.</span><span class="sxs-lookup"><span data-stu-id="f05ac-126">Item P0002 is now available in the picking list for the kanban job.</span></span> <span data-ttu-id="f05ac-127">Esto significa que podemos preparar el kanban con todos los materiales necesarios.</span><span class="sxs-lookup"><span data-stu-id="f05ac-127">This means that we can prepare the kanban with all the needed materials.</span></span>  
6. <span data-ttu-id="f05ac-128">Haga clic en Preparar.</span><span class="sxs-lookup"><span data-stu-id="f05ac-128">Click Prepare.</span></span>
    * <span data-ttu-id="f05ac-129">Observe que un icono en el estado del trabajo indica que el trabajo está ahora listo.</span><span class="sxs-lookup"><span data-stu-id="f05ac-129">Notice that an icon in the Job status indicates that the job is now ready.</span></span>  


