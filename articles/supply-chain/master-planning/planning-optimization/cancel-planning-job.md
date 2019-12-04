---
title: Cancelar un trabajo de planificación
description: Este tema explica cómo cancelar un trabajo activo de planificación que utilice la función de ajuste de planificación.
author: ChristianRytt
manager: AnnBe
ms.date: 10/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: a2d90f04985fdd66ca83582ee676100fffb26981
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/06/2019
ms.locfileid: "2774048"
---
[!include [banner](../../includes/banner.md)]
[!include [banner](../../includes/preview-banner.md)]

# <a name="cancel-a-planning-job"></a><span data-ttu-id="2942a-103">Cancelar un trabajo de planificación</span><span class="sxs-lookup"><span data-stu-id="2942a-103">Cancel a planning job</span></span>

<span data-ttu-id="2942a-104">En Microsoft Dynamics 365 Supply Chain Management puede cancelar un trabajo activo de planificación que utilice la función de ajuste de planificación.</span><span class="sxs-lookup"><span data-stu-id="2942a-104">In Microsoft Dynamics 365 Supply Chain Management, you can cancel an active planning job that uses the Planning Optimization functionality.</span></span>

<span data-ttu-id="2942a-105">Para cancelar un trabajo activo de planificación, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="2942a-105">To cancel an active planning job, follow these steps.</span></span>

> [!NOTE]
> <span data-ttu-id="2942a-106">Sólo puede cancelar trabajos activos.</span><span class="sxs-lookup"><span data-stu-id="2942a-106">Only active jobs can be canceled.</span></span>

1. <span data-ttu-id="2942a-107">Vaya a **Planificación maestra \> Configuración \> Planes**.</span><span class="sxs-lookup"><span data-stu-id="2942a-107">Go to **Master planning \> Setup \> Plans**.</span></span>
2. <span data-ttu-id="2942a-108">Seleccione un plan apropiado para la ejecución de planificación.</span><span class="sxs-lookup"><span data-stu-id="2942a-108">Select an appropriate plan for the planning run.</span></span>
3. <span data-ttu-id="2942a-109">Seleccione **Historial**.</span><span class="sxs-lookup"><span data-stu-id="2942a-109">Select **History**.</span></span>
4. <span data-ttu-id="2942a-110">Seleccione el trabajo de planificación que se desea cancelar.</span><span class="sxs-lookup"><span data-stu-id="2942a-110">Select the planning job to cancel.</span></span>
5. <span data-ttu-id="2942a-111">Seleccione **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="2942a-111">Select **Cancel**.</span></span>

<span data-ttu-id="2942a-112">El estado del trabajo será **Cancelando** hasta que el servicio de optimización de la planificación confirme que el trabajo se ha cancelado.</span><span class="sxs-lookup"><span data-stu-id="2942a-112">The job status will be **Canceling** until the Planning Optimization service confirms that the job has been canceled.</span></span> <span data-ttu-id="2942a-113">El estado se cambiará a **Cancelado**.</span><span class="sxs-lookup"><span data-stu-id="2942a-113">The status will then be changed to **Canceled**.</span></span>

> [!NOTE]
> <span data-ttu-id="2942a-114">Para ver cambios de estado, debe actualizar la página seleccionando el botón **Actualizar**.</span><span class="sxs-lookup"><span data-stu-id="2942a-114">To see status changes, you must refresh the page by selecting the **Refresh** button.</span></span>

## <a name="related-resources"></a><span data-ttu-id="2942a-115">Recursos relacionados</span><span class="sxs-lookup"><span data-stu-id="2942a-115">Related resources</span></span>

[<span data-ttu-id="2942a-116">Visión general de la optimización de planificación</span><span class="sxs-lookup"><span data-stu-id="2942a-116">Planning Optimization overview</span></span>](planning-optimization-overview.md)

[<span data-ttu-id="2942a-117">Introducción a la optimización de planificación</span><span class="sxs-lookup"><span data-stu-id="2942a-117">Get started with Planning Optimization</span></span>](get-started.md)

[<span data-ttu-id="2942a-118">Análisis de aptitud de la optimización de la planificación</span><span class="sxs-lookup"><span data-stu-id="2942a-118">Planning Optimization fit analysis</span></span>](planning-optimization-fit-analysis.md)

[<span data-ttu-id="2942a-119">Ver el historial del plan y los registros de planificación</span><span class="sxs-lookup"><span data-stu-id="2942a-119">View plan history and planning logs</span></span>](plan-history-logs.md)

[<span data-ttu-id="2942a-120">Aplicar filtros a un plan</span><span class="sxs-lookup"><span data-stu-id="2942a-120">Apply filters to a plan</span></span>](plan-filters.md)
