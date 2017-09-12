--- 
title: "Preparación de un trabajo kanban de proceso cuando los materiales están disponibles para la celda de trabajo"
description: "Esta tarea se centra en la preparación de un trabajo kanban de proceso cuando todos los materiales están disponibles para la celda de trabajo."
author: johanhoffmann
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 62f3f71cc5e47f0fb027211a911e61673ca2e375
ms.contentlocale: es-es
ms.lasthandoff: 08/29/2017

---
# <a name="prepare-a-process-kanban-job-when-materials-are-available-for-the-work-cell"></a><span data-ttu-id="468dc-103">Preparación de un trabajo kanban de proceso cuando los materiales están disponibles para la celda de trabajo</span><span class="sxs-lookup"><span data-stu-id="468dc-103">Prepare a process kanban job when materials are available for the work cell</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="468dc-104">Esta tarea se centra en la preparación de un trabajo kanban de proceso cuando todos los materiales están disponibles para la celda de trabajo.</span><span class="sxs-lookup"><span data-stu-id="468dc-104">This task focuses on preparing a process kanban job when all materials are available for the work cell.</span></span> <span data-ttu-id="468dc-105">La empresa de datos de prueba utilizada para crear esta tarea es USMF.</span><span class="sxs-lookup"><span data-stu-id="468dc-105">The demo data company used to create this task is USMF.</span></span> <span data-ttu-id="468dc-106">Esta tarea va destinada al operario de la máquina.</span><span class="sxs-lookup"><span data-stu-id="468dc-106">This task is intended for the machine operator.</span></span>

1. <span data-ttu-id="468dc-107">Vaya a Tablero kanban para trabajos de proceso.</span><span class="sxs-lookup"><span data-stu-id="468dc-107">Go to Kanban board for process jobs.</span></span>
2. <span data-ttu-id="468dc-108">En el campo Celda de trabajo, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="468dc-108">In the Work cell field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="468dc-109">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="468dc-109">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="468dc-110">Seleccione la celda de trabajo 1250 y haga clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="468dc-110">Select work cell 1250 and click OK.</span></span>  
4. <span data-ttu-id="468dc-111">En la lista, seleccione la fila 4.</span><span class="sxs-lookup"><span data-stu-id="468dc-111">In the list, select row 4.</span></span>
    * <span data-ttu-id="468dc-112">En la empresa de demostración limpia, el kanban 000329 en la fila 4 es el primer trabajo aún sin completar.</span><span class="sxs-lookup"><span data-stu-id="468dc-112">In the clean demo company, Kanban 000329 in row 4 is the first job that is not completed yet.</span></span>  
5. <span data-ttu-id="468dc-113">Expanda la sección de la lista de selección.</span><span class="sxs-lookup"><span data-stu-id="468dc-113">Toggle the expansion of the Picking list section.</span></span>
    * <span data-ttu-id="468dc-114">Compruebe que el estado de suministro sea disponible para todos los artículos de la lista de selección.</span><span class="sxs-lookup"><span data-stu-id="468dc-114">Verify that the supply status is available for all items in the picking list.</span></span>  
    * <span data-ttu-id="468dc-115">Si se seleccionan varios trabajos, la lista de selección mostrará la suma de todos los artículos necesarios para los trabajos seleccionados.</span><span class="sxs-lookup"><span data-stu-id="468dc-115">If multiple jobs are selected, the picking list will show the sum of all items needed for the selected jobs.</span></span>  
6. <span data-ttu-id="468dc-116">Haga clic en Preparar.</span><span class="sxs-lookup"><span data-stu-id="468dc-116">Click Prepare.</span></span>
    * <span data-ttu-id="468dc-117">El proceso de preparación está ahora terminado.</span><span class="sxs-lookup"><span data-stu-id="468dc-117">The preparation process is now completed.</span></span> <span data-ttu-id="468dc-118">La casilla de verificación seleccionada para todas las filas de la lista de selección indica que el estado de suministro es el de seleccionado.</span><span class="sxs-lookup"><span data-stu-id="468dc-118">The selected check box for all rows in the picking list indicates that the supply status is picked.</span></span>  


