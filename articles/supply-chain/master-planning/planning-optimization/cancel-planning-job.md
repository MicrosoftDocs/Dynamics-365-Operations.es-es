---
title: Cancelar un trabajo de planificación
description: Este tema explica cómo cancelar un trabajo activo de planificación que utilice la función de ajuste de planificación.
author: ChristianRytt
manager: tfehr
ms.date: 02/18/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 4b65d344cd764740cc1485969c2fc4c2052e55e2
ms.sourcegitcommit: 68092ed283bfbb7b6f611cce1b62c791f9b6a208
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/30/2020
ms.locfileid: "3323471"
---
# <a name="cancel-a-planning-job"></a><span data-ttu-id="e4910-103">Cancelar un trabajo de planificación</span><span class="sxs-lookup"><span data-stu-id="e4910-103">Cancel a planning job</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="e4910-104">En Microsoft Dynamics 365 Supply Chain Management puede cancelar un trabajo activo de planificación que utilice la función de ajuste de planificación.</span><span class="sxs-lookup"><span data-stu-id="e4910-104">In Microsoft Dynamics 365 Supply Chain Management, you can cancel an active planning job that uses the Planning optimization functionality.</span></span> <span data-ttu-id="e4910-105">Cuando seleccionas **Cancelar** en el cuadro de diálogo cuando un trabajo de optimización de Planificación se activa directamente desde la interfaz de usuario (no en segundo plano), esto no cancelará el trabajo de optimización de Planificación.</span><span class="sxs-lookup"><span data-stu-id="e4910-105">When you select **Cancel** in the dialog box when a Planning optimization job is triggered directly from the user interface (not in the background), this will not cancel the Planning optimization job.</span></span> <span data-ttu-id="e4910-106">Incluso si recibe una advertencia como "Operación cancelada", deberá seguir los siguientes pasos para cancelar un trabajo de planificación con la optimización de planificación.</span><span class="sxs-lookup"><span data-stu-id="e4910-106">Even if you receive a warning such as “Operation canceled”, you will still need to use the following steps to cancel a planning job with Planning optimization.</span></span>


<span data-ttu-id="e4910-107">Para cancelar un trabajo activo de planificación, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="e4910-107">To cancel an active planning job, follow these steps.</span></span> 

> [!NOTE]
> <span data-ttu-id="e4910-108">Sólo puede cancelar trabajos activos.</span><span class="sxs-lookup"><span data-stu-id="e4910-108">Only active jobs can be canceled.</span></span>

1. <span data-ttu-id="e4910-109">Vaya a **Planificación maestra \> Configuración \> Planes**.</span><span class="sxs-lookup"><span data-stu-id="e4910-109">Go to **Master planning \> Setup \> Plans**.</span></span>
2. <span data-ttu-id="e4910-110">Seleccione un plan apropiado para la ejecución de planificación.</span><span class="sxs-lookup"><span data-stu-id="e4910-110">Select an appropriate plan for the planning run.</span></span>
3. <span data-ttu-id="e4910-111">Seleccione **Historial**.</span><span class="sxs-lookup"><span data-stu-id="e4910-111">Select **History**.</span></span>
4. <span data-ttu-id="e4910-112">Seleccione el trabajo de planificación que se desea cancelar.</span><span class="sxs-lookup"><span data-stu-id="e4910-112">Select the planning job to cancel.</span></span>
5. <span data-ttu-id="e4910-113">Seleccione **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="e4910-113">Select **Cancel**.</span></span>

<span data-ttu-id="e4910-114">El estado del trabajo será **Cancelando** hasta que el servicio de optimización de la planificación confirme que el trabajo se ha cancelado.</span><span class="sxs-lookup"><span data-stu-id="e4910-114">The job status will be **Canceling** until the Planning Optimization service confirms that the job has been canceled.</span></span> <span data-ttu-id="e4910-115">El estado se cambiará a **Cancelado**.</span><span class="sxs-lookup"><span data-stu-id="e4910-115">The status will then be changed to **Canceled**.</span></span>

> [!NOTE]
> <span data-ttu-id="e4910-116">Para ver cambios de estado, debe actualizar la página seleccionando el botón **Actualizar**.</span><span class="sxs-lookup"><span data-stu-id="e4910-116">To see status changes, you must refresh the page by selecting the **Refresh** button.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e4910-117">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="e4910-117">Additional resources</span></span>

[<span data-ttu-id="e4910-118">Visión general de la optimización de la planificación</span><span class="sxs-lookup"><span data-stu-id="e4910-118">Planning Optimization overview</span></span>](planning-optimization-overview.md)

[<span data-ttu-id="e4910-119">Introducción a la optimización de la planificación</span><span class="sxs-lookup"><span data-stu-id="e4910-119">Get started with Planning Optimization</span></span>](get-started.md)

[<span data-ttu-id="e4910-120">Análisis de aptitud de la optimización de la planificación</span><span class="sxs-lookup"><span data-stu-id="e4910-120">Planning Optimization fit analysis</span></span>](planning-optimization-fit-analysis.md)

[<span data-ttu-id="e4910-121">Ver el historial del plan y los registros de planificación</span><span class="sxs-lookup"><span data-stu-id="e4910-121">View plan history and planning logs</span></span>](plan-history-logs.md)

[<span data-ttu-id="e4910-122">Aplicar filtros a un plan</span><span class="sxs-lookup"><span data-stu-id="e4910-122">Apply filters to a plan</span></span>](plan-filters.md)
