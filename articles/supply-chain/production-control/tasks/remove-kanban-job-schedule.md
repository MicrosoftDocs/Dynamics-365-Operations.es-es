--- 
title: "Eliminación de un trabajo kanban de la programación"
description: "Este procedimiento se centra en la eliminación de un trabajo kanban planificado de la programación revirtiendo el estado del trabajo a Sin planificar."
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
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 7304c6cac1f31c179231f72d05ee4d02502d4ca3
ms.contentlocale: es-es
ms.lasthandoff: 04/13/2018

---
# <a name="remove-a-kanban-job-from-the-schedule"></a><span data-ttu-id="d4684-103">Eliminación de un trabajo kanban de la programación</span><span class="sxs-lookup"><span data-stu-id="d4684-103">Remove a kanban job from the schedule</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d4684-104">Este procedimiento se centra en la eliminación de un trabajo kanban planificado de la programación revirtiendo el estado del trabajo a Sin planificar.</span><span class="sxs-lookup"><span data-stu-id="d4684-104">This procedure focuses on removing a planned process kanban job from the schedule by reverting the job status to Not planned.</span></span> <span data-ttu-id="d4684-105">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="d4684-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="d4684-106">Este procedimiento está pensado para el supervisor de planta o el planificador de producción.</span><span class="sxs-lookup"><span data-stu-id="d4684-106">This procedure is intended for the shop floor supervisor or production planner.</span></span>


## <a name="find-a-planned-kanban-job"></a><span data-ttu-id="d4684-107">Búsqueda de un trabajo kanban planificado</span><span class="sxs-lookup"><span data-stu-id="d4684-107">Find a planned kanban job</span></span>
1. <span data-ttu-id="d4684-108">Vaya a Control de producción > Kanban > Programación de trabajos kanban.</span><span class="sxs-lookup"><span data-stu-id="d4684-108">Go to Production control > Kanban > Kanban job scheduling.</span></span>
2. <span data-ttu-id="d4684-109">En el campo Celda de trabajo, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="d4684-109">In the Work cell field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="d4684-110">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="d4684-110">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="d4684-111">Seleccione la celda de trabajo 1250.</span><span class="sxs-lookup"><span data-stu-id="d4684-111">Select work cell 1250.</span></span>  
4. <span data-ttu-id="d4684-112">Haga clic en Seleccionar.</span><span class="sxs-lookup"><span data-stu-id="d4684-112">Click Select.</span></span>
5. <span data-ttu-id="d4684-113">En el campo Mostrar estado del trabajo, seleccione Programado.</span><span class="sxs-lookup"><span data-stu-id="d4684-113">In the Display job status field, select 'Scheduled'.</span></span>

## <a name="remove-the-planned-kanban-job-from-the-schedule"></a><span data-ttu-id="d4684-114">Eliminación del trabajo kanban planificado de la programación</span><span class="sxs-lookup"><span data-stu-id="d4684-114">Remove the planned kanban job from the schedule</span></span>
1. <span data-ttu-id="d4684-115">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="d4684-115">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="d4684-116">Seleccione un trabajo con estado Planificado; por ejemplo, un trabajo a partir del 19 de diciembre de 2012.</span><span class="sxs-lookup"><span data-stu-id="d4684-116">Select a job that has the Planned status, for example, a job from December 19, 2012.</span></span>  
2. <span data-ttu-id="d4684-117">En el panel de acciones, haga clic en Plan.</span><span class="sxs-lookup"><span data-stu-id="d4684-117">On the Action Pane, click Plan.</span></span>
3. <span data-ttu-id="d4684-118">Haga clic en Invertir estado del trabajo.</span><span class="sxs-lookup"><span data-stu-id="d4684-118">Click Revert job status.</span></span>
4. <span data-ttu-id="d4684-119">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="d4684-119">Click OK.</span></span>
    * <span data-ttu-id="d4684-120">Esto revertirá el estado del trabajo actual de Planificado a Sin planificar, y lo eliminará del panel de tablero de procesos.</span><span class="sxs-lookup"><span data-stu-id="d4684-120">This will revert the current job status from 'Planned' to 'Not planned' and remove it from the process board.</span></span>   


