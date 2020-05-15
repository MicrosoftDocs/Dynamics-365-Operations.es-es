---
title: Aplicar filtros a un plan
description: Este tema explica cómo usar filtros en un plan cuando se utiliza la funcionalidad optimización de la planificación.
author: ChristianRytt
manager: tfehr
ms.date: 01/08/2020
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
ms.openlocfilehash: 9ddf9934965bd06ec805731a1cc1a667846fa180
ms.sourcegitcommit: 68092ed283bfbb7b6f611cce1b62c791f9b6a208
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/30/2020
ms.locfileid: "3323425"
---
# <a name="apply-filters-to-a-plan"></a><span data-ttu-id="a3aa7-103">Aplicar filtros a un plan</span><span class="sxs-lookup"><span data-stu-id="a3aa7-103">Apply filters to a plan</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="a3aa7-104">Cuando se usa la funcionalidad optimización de la planificación, puede aplicar un filtro a un plan.</span><span class="sxs-lookup"><span data-stu-id="a3aa7-104">When the Planning Optimization functionality is used, you can apply a filter to a plan.</span></span> <span data-ttu-id="a3aa7-105">El **Filtro de plan** se aplicará siempre durante la ejecución de una planificación maestra.</span><span class="sxs-lookup"><span data-stu-id="a3aa7-105">The **Plan filter** will always be applied during a master planning run.</span></span> <span data-ttu-id="a3aa7-106">Un **Filtros de plan** es útil cuando se desea restringir un plan a un determinado grupo de artículos y asegurarse de que no se incluyan otros artículos como parte de la planificación maestra resultante.</span><span class="sxs-lookup"><span data-stu-id="a3aa7-106">A **Plan filter** is useful when you want to limit a plan to a specific group of items and make sure that no other items are included as part of the resulting master planning.</span></span>

<span data-ttu-id="a3aa7-107">Si se aplica un **Filtro de plan** y también se aplica un filtro de tiempo de ejecución durante la ejecución de la planificación maestra, solo se incluirá la intersección de los dos filtros en la ejecución de la planificación.</span><span class="sxs-lookup"><span data-stu-id="a3aa7-107">If a **Plan filter** is applied, and a runtime filter is also applied during the master planning run, only the intersection of the two filters is included in the planning run.</span></span>

<span data-ttu-id="a3aa7-108">Se puede acceder al **Filtro de plan** desde **Planes maestros** cuando se utiliza la Optimización de planificación.</span><span class="sxs-lookup"><span data-stu-id="a3aa7-108">The **Plan filter** can be accessed from **Master plans** when Planning Optimization is used.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="a3aa7-109">Supuesto de ejemplo</span><span class="sxs-lookup"><span data-stu-id="a3aa7-109">Example scenario</span></span>

<span data-ttu-id="a3aa7-110">Se configura un filtro de planes que incluye los artículos A, B, y C. Después se ejecutan las planificaciones maestras para el mismo plan, pero se aplican diferentes filtros de tiempo de ejecución:</span><span class="sxs-lookup"><span data-stu-id="a3aa7-110">A plan filter is set up that includes items A, B, and C. Master planning runs are then run for the same plan, but different runtime filters are applied:</span></span>

- <span data-ttu-id="a3aa7-111">**Filtro de tiempo de ejecución que incluye el artículo D:** no hay artículos planificados, porque no hay intersección entre el filtro del plan y el filtro del tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a3aa7-111">**Runtime filter that includes item D:** No items are planned, because there is no intersection between the plan filter and the runtime filter.</span></span>
- <span data-ttu-id="a3aa7-112">**Filtro de tiempo de ejecución que incluye los artículos A y D:** solo se incluye el artículo A en la ejecución de la planificación, porque el artículo D no es parte del filtro del plan.</span><span class="sxs-lookup"><span data-stu-id="a3aa7-112">**Runtime filter that includes item A and D:** Only item A is included in the planning run, because item D isn't part of the plan filter.</span></span>
- <span data-ttu-id="a3aa7-113">**Filtro de tiempo de ejecución que incluye el artículo B:** solo se incluye el artículo B en la ejecución de la planificación, y el resultado de la planificación anterior para el artículo A se conserva.</span><span class="sxs-lookup"><span data-stu-id="a3aa7-113">**Runtime filter that includes item B:** Only item B is included in the planning run, and the previous planning output for item A is kept.</span></span>
- <span data-ttu-id="a3aa7-114">**Filtro de tiempo de ejecución que incluye todos los artículos (filtro en blanco):** los artículos A, B, y C se incluye en la ejecución de la planificación y el resultado de la planificación anterior para los artículos A y B se anula.</span><span class="sxs-lookup"><span data-stu-id="a3aa7-114">**Runtime filter that includes all items (blank filter):** Items A, B, and C are included in the planning run, and the previous planning output for items A and B is overwritten.</span></span>

> [!NOTE]
> <span data-ttu-id="a3aa7-115">Debe evitar definir un filtro del plan en el plan seleccionado como **Plan maestro dinámico actual** en la página **Parámetros de planificación maestra**.</span><span class="sxs-lookup"><span data-stu-id="a3aa7-115">You should avoid setting a plan filter on the plan that is selected as **Current dynamic master plan** on the **Master planning parameters** page.</span></span> <span data-ttu-id="a3aa7-116">De lo contrario, la funcionalidad dinámica del plan maestro se limitará a los artículos filtrados.</span><span class="sxs-lookup"><span data-stu-id="a3aa7-116">Otherwise, the dynamic master plan functionality will be limited to the filtered items.</span></span> <span data-ttu-id="a3aa7-117">Por ejemplo, si los requisitos netos se actualizan para un elemento que no sea parte del filtro del plan, no se generará ningún resultado.</span><span class="sxs-lookup"><span data-stu-id="a3aa7-117">For example, if the net requirements are updated for an item that isn't part of the plan filter, no result will be generated.</span></span>

## <a name="related-resources"></a><span data-ttu-id="a3aa7-118">Recursos relacionados</span><span class="sxs-lookup"><span data-stu-id="a3aa7-118">Related resources</span></span>

[<span data-ttu-id="a3aa7-119">Visión general de la optimización de la planificación</span><span class="sxs-lookup"><span data-stu-id="a3aa7-119">Planning Optimization overview</span></span>](planning-optimization-overview.md)

[<span data-ttu-id="a3aa7-120">Introducción a la optimización de planificación</span><span class="sxs-lookup"><span data-stu-id="a3aa7-120">Get started with Planning Optimization</span></span>](get-started.md)

[<span data-ttu-id="a3aa7-121">Análisis de aptitud de la optimización de la planificación</span><span class="sxs-lookup"><span data-stu-id="a3aa7-121">Planning Optimization fit analysis</span></span>](planning-optimization-fit-analysis.md)

[<span data-ttu-id="a3aa7-122">Ver el historial del plan y los registros de planificación</span><span class="sxs-lookup"><span data-stu-id="a3aa7-122">View plan history and planning logs</span></span>](plan-history-logs.md)

[<span data-ttu-id="a3aa7-123">Cancelar un trabajo de planificación</span><span class="sxs-lookup"><span data-stu-id="a3aa7-123">Cancel a planning job</span></span>](cancel-planning-job.md)
