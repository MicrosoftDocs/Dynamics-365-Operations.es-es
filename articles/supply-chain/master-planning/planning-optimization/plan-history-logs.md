---
title: Ver el historial del plan y los registros de planificación
description: Este tema explica cómo ver el historial de los trabajos de planificación desencadenados por la funcionalidad de optimización de la planificación.
author: ChristianRytt
ms.date: 10/30/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: MPSPlanRegenerationJobList, MPSPlanRegenerationJobLogs
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: d7bba084b03f8698c8bf31d171d5e4e486ed06ad
ms.sourcegitcommit: a7649b361ec54b49c0e9ee1c1c63a8815f320225
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2021
ms.locfileid: "6187256"
---
# <a name="view-plan-history-and-planning-logs"></a><span data-ttu-id="78be3-103">Ver el historial del plan y los registros de planificación</span><span class="sxs-lookup"><span data-stu-id="78be3-103">View plan history and planning logs</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="78be3-104">Este tema explica cómo ver el historial de los trabajos de planificación desencadenados por la funcionalidad de optimización de la planificación en Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="78be3-104">This topic explains how to view the history of planning jobs that are triggered by the Planning Optimization functionality in Microsoft Dynamics 365 Supply Chain Management.</span></span>

<span data-ttu-id="78be3-105">Para ver el historial de un plan, abra el plan; para ello, vaya a **Planificación maestra** \> **Configuración** \> **Planes** \> **Planes maestros** y seleccionando **Historial**.</span><span class="sxs-lookup"><span data-stu-id="78be3-105">To view the history for a plan, open the plan by going to **Master planning** \> **Setup** \> **Plans** \> **Master plans** and selecting **History**.</span></span> <span data-ttu-id="78be3-106">El historial contiene todos los trabajos para el plan seleccionado.</span><span class="sxs-lookup"><span data-stu-id="78be3-106">The history lists all the jobs for the selected plan.</span></span> <span data-ttu-id="78be3-107">La lista incluye los trabajos completados y trabajos.</span><span class="sxs-lookup"><span data-stu-id="78be3-107">The list includes completed and active jobs.</span></span>

<span data-ttu-id="78be3-108">El historial de trabajos para las ejecuciones de planificación maestra de Planning Optimization mantiene solo hasta 60 registros por plan maestro.</span><span class="sxs-lookup"><span data-stu-id="78be3-108">The history of jobs for Planning Optimization master planning runs keeps only up to 60 records per master plan.</span></span> <span data-ttu-id="78be3-109">Siempre que ejecuta un nuevo cálculo de planificación maestra, se elimina el registro histórico más antiguo de ese plan.</span><span class="sxs-lookup"><span data-stu-id="78be3-109">Whenever you run a new master planning calculation, that plan's earliest history record is deleted.</span></span>

<span data-ttu-id="78be3-110">Además de ver la hora de inicio y el estado de los trabajos, puede ver el registro para un trabajo específico.</span><span class="sxs-lookup"><span data-stu-id="78be3-110">In addition to seeing the start time and status of jobs, you can view the log for a specific job.</span></span> <span data-ttu-id="78be3-111">El registro incluye información adicional y advertencias.</span><span class="sxs-lookup"><span data-stu-id="78be3-111">The log includes additional information and warnings.</span></span> <span data-ttu-id="78be3-112">No todos los trabajos tienen un registro.</span><span class="sxs-lookup"><span data-stu-id="78be3-112">Not all jobs have a log.</span></span> <span data-ttu-id="78be3-113">Para ver el registro de un trabajo, seleccione **Registro**.</span><span class="sxs-lookup"><span data-stu-id="78be3-113">To view the log for a job, select **Log**.</span></span> <span data-ttu-id="78be3-114">Las entradas del registro solo se almacenan durante 30 días después de la fecha en que finalizó el trabajo, después de eso se eliminan automáticamente.</span><span class="sxs-lookup"><span data-stu-id="78be3-114">Log entries are only stored for 30 days after the date the job finished, after that they are automatically deleted.</span></span>

## <a name="related-resources"></a><span data-ttu-id="78be3-115">Recursos relacionados</span><span class="sxs-lookup"><span data-stu-id="78be3-115">Related resources</span></span>

- [<span data-ttu-id="78be3-116">Información general de la optimización de la planificación</span><span class="sxs-lookup"><span data-stu-id="78be3-116">Planning Optimization overview</span></span>](planning-optimization-overview.md)
- [<span data-ttu-id="78be3-117">Introducción a la optimización de la planificación</span><span class="sxs-lookup"><span data-stu-id="78be3-117">Get started with Planning Optimization</span></span>](get-started.md)
- [<span data-ttu-id="78be3-118">Análisis de aptitud de la optimización de la planificación</span><span class="sxs-lookup"><span data-stu-id="78be3-118">Planning Optimization fit analysis</span></span>](planning-optimization-fit-analysis.md)
- [<span data-ttu-id="78be3-119">Aplicar filtros a un plan</span><span class="sxs-lookup"><span data-stu-id="78be3-119">Apply filters to a plan</span></span>](plan-filters.md)
- [<span data-ttu-id="78be3-120">Cancelar un trabajo de planificación</span><span class="sxs-lookup"><span data-stu-id="78be3-120">Cancel a planning job</span></span>](cancel-planning-job.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]