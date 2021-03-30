---
title: Eliminación de un trabajo kanban de la programación
description: Este procedimiento se centra en la eliminación de un trabajo kanban planificado de la programación revirtiendo el estado del trabajo a Sin planificar.
author: ChristianRytt
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanJobSchedulingListPage, SysLookupMultiSelectGrid, KanbanJobStatusUpdate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 566a174c631391577441e0f890bd9553dac0891c
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5204529"
---
# <a name="remove-a-kanban-job-from-the-schedule"></a><span data-ttu-id="97abb-103">Eliminación de un trabajo kanban de la programación</span><span class="sxs-lookup"><span data-stu-id="97abb-103">Remove a kanban job from the schedule</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="97abb-104">Este procedimiento se centra en la eliminación de un trabajo kanban planificado de la programación revirtiendo el estado del trabajo a Sin planificar.</span><span class="sxs-lookup"><span data-stu-id="97abb-104">This procedure focuses on removing a planned process kanban job from the schedule by reverting the job status to Not planned.</span></span> <span data-ttu-id="97abb-105">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="97abb-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="97abb-106">Este procedimiento está pensado para el supervisor de planta o el planificador de producción.</span><span class="sxs-lookup"><span data-stu-id="97abb-106">This procedure is intended for the shop floor supervisor or production planner.</span></span>


## <a name="find-a-planned-kanban-job"></a><span data-ttu-id="97abb-107">Búsqueda de un trabajo kanban planificado</span><span class="sxs-lookup"><span data-stu-id="97abb-107">Find a planned kanban job</span></span>
1. <span data-ttu-id="97abb-108">Vaya a Control de producción > Kanban > Programación de trabajos kanban.</span><span class="sxs-lookup"><span data-stu-id="97abb-108">Go to Production control > Kanban > Kanban job scheduling.</span></span>
2. <span data-ttu-id="97abb-109">En el campo Celda de trabajo, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="97abb-109">In the Work cell field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="97abb-110">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="97abb-110">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="97abb-111">Seleccione la celda de trabajo 1250.</span><span class="sxs-lookup"><span data-stu-id="97abb-111">Select work cell 1250.</span></span>  
4. <span data-ttu-id="97abb-112">Haga clic en Seleccionar.</span><span class="sxs-lookup"><span data-stu-id="97abb-112">Click Select.</span></span>
5. <span data-ttu-id="97abb-113">En el campo Mostrar estado del trabajo, seleccione Programado.</span><span class="sxs-lookup"><span data-stu-id="97abb-113">In the Display job status field, select 'Scheduled'.</span></span>

## <a name="remove-the-planned-kanban-job-from-the-schedule"></a><span data-ttu-id="97abb-114">Eliminación del trabajo kanban planificado de la programación</span><span class="sxs-lookup"><span data-stu-id="97abb-114">Remove the planned kanban job from the schedule</span></span>
1. <span data-ttu-id="97abb-115">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="97abb-115">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="97abb-116">Seleccione un trabajo con estado Planificado; por ejemplo, un trabajo a partir del 19 de diciembre de 2012.</span><span class="sxs-lookup"><span data-stu-id="97abb-116">Select a job that has the Planned status, for example, a job from December 19, 2012.</span></span>  
2. <span data-ttu-id="97abb-117">En el panel de acciones, haga clic en Plan.</span><span class="sxs-lookup"><span data-stu-id="97abb-117">On the Action Pane, click Plan.</span></span>
3. <span data-ttu-id="97abb-118">Haga clic en Invertir estado del trabajo.</span><span class="sxs-lookup"><span data-stu-id="97abb-118">Click Revert job status.</span></span>
4. <span data-ttu-id="97abb-119">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="97abb-119">Click OK.</span></span>
    * <span data-ttu-id="97abb-120">Esto revertirá el estado del trabajo actual de Planificado a Sin planificar, y lo eliminará del panel de tablero de procesos.</span><span class="sxs-lookup"><span data-stu-id="97abb-120">This will revert the current job status from 'Planned' to 'Not planned' and remove it from the process board.</span></span>   



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]