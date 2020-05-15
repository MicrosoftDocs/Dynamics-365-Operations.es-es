---
title: Visión general de la optimización de la planificación
description: Este tema proporciona una visión general de la funcionalidad de la optimización de la planificación.
author: ChristianRytt
manager: tfehr
ms.date: 10/31/2019
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
ms.openlocfilehash: 110045d4c7e4f32c29b73096dd4df3a09b5434ac
ms.sourcegitcommit: 68092ed283bfbb7b6f611cce1b62c791f9b6a208
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/30/2020
ms.locfileid: "3323402"
---
# <a name="planning-optimization-overview"></a><span data-ttu-id="82714-103">Visión general de la optimización de la planificación</span><span class="sxs-lookup"><span data-stu-id="82714-103">Planning Optimization overview</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="82714-104">El complemento de la optimización de la planificación para Microsoft Dynamics 365 Supply Chain Management permite que el cálculo de la planificación maestra se produzca fuera de Dynamics 365 Supply Chain Management y de la base de datos SQL relacionada.</span><span class="sxs-lookup"><span data-stu-id="82714-104">The Planning Optimization Add-in for Microsoft Dynamics 365 Supply Chain Management enables master planning calculation to occur outside Dynamics 365 Supply Chain Management and the related SQL database.</span></span> <span data-ttu-id="82714-105">Los beneficios que están asociados con la funcionalidad de optimización de la planificación incluyen un rendimiento mejorado y un impacto mínimo en la base de datos SQL durante las ejecuciones de la planificación maestra.</span><span class="sxs-lookup"><span data-stu-id="82714-105">The benefits that are associated with the Planning Optimization functionality include improved performance and minimal impact on SQL database during master planning runs.</span></span> <span data-ttu-id="82714-106">Las ejecuciones rápidas de la planificación se pueden realizar incluso durante las horas de oficina, de modo que los planificadores puedan inmediatamente reaccionar a los cambios de la demanda o configuración de parámetros.</span><span class="sxs-lookup"><span data-stu-id="82714-106">Quick planning runs can be done even during office hours, so that planners can immediately react to demand or parameter changes.</span></span>

<span data-ttu-id="82714-107">Para usar la optimización de la planificación, debe instalar el complemento de optimización de la planificación de su proyecto en Microsoft Dynamics Lifecycle Services (LCS) y activar la funcionalidad de optimización de la planificación en Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="82714-107">To use Planning Optimization, you must install the Planning Optimization Add-in from your project in Microsoft Dynamics Lifecycle Services (LCS) and turn on the Planning Optimization functionality in Supply Chain Management.</span></span> <span data-ttu-id="82714-108">Para obtener más información, consulte [Empezar a utilizar la optimización de la planificación](get-started.md).</span><span class="sxs-lookup"><span data-stu-id="82714-108">For more information, see [Get started with Planning Optimization](get-started.md).</span></span>

<span data-ttu-id="82714-109">La ilustración siguiente muestra la ventaja de ejecutar el ajuste de optimización de la planificación durante las horas de oficina.</span><span class="sxs-lookup"><span data-stu-id="82714-109">The following illustration shows the advantage of running Planning Optimization during office hours.</span></span>

![Ventaja de ejecutar el ajuste de optimización de la planificación durante las horas de oficina](media/PlanningOptimization1.png)

## <a name="improved-performance"></a><span data-ttu-id="82714-111">rendimiento mejorado</span><span class="sxs-lookup"><span data-stu-id="82714-111">Improved performance</span></span>

<span data-ttu-id="82714-112">La optimización de la planificación se puede usar en situaciones que implican planes maestros de larga ejecución.</span><span class="sxs-lookup"><span data-stu-id="82714-112">Planning Optimization can be used in scenarios that involve long-running master plans.</span></span> <span data-ttu-id="82714-113">Se diseña específicamente para los cálculos muy rápidos que implican volúmenes de datos muy grandes.</span><span class="sxs-lookup"><span data-stu-id="82714-113">It's specifically designed for very fast calculations that involve very large volumes of data.</span></span> <span data-ttu-id="82714-114">Dado que se ha creado como servicio para varios inquilinos con alta capacidad de escalabilidad, varias instancias pueden trabajar conjuntamente de forma simultánea para calcular el plan.</span><span class="sxs-lookup"><span data-stu-id="82714-114">Because it's built as a hyper-scalable multitenant service, multiple instances can work together simultaneously to calculate the plan.</span></span> <span data-ttu-id="82714-115">Además, el servicio de planificación quita la carga de la planificación maestra del sistema y trabaja con una secuencia de datos que minimiza la carga del servidor.</span><span class="sxs-lookup"><span data-stu-id="82714-115">Additionally, the planning service removes the load of master planning from your system and works with a data stream that minimizes the server load.</span></span>

<span data-ttu-id="82714-116">La optimización de la planificación le puede servir de ayuda para lograr los objetivos siguientes:</span><span class="sxs-lookup"><span data-stu-id="82714-116">Planning Optimization can help you achieve the following goals:</span></span>

- <span data-ttu-id="82714-117">Mejorar el rendimiento de la planificación con un tiempo de ejecución más corto.</span><span class="sxs-lookup"><span data-stu-id="82714-117">Improve planning performance through a shorter runtime.</span></span>
- <span data-ttu-id="82714-118">Reducir el impacto en otros procesos durante la ejecución de la planificación maestra.</span><span class="sxs-lookup"><span data-stu-id="82714-118">Reduce the impact on other processes during the master planning run.</span></span>
- <span data-ttu-id="82714-119">Hacer ejecución de planificación más frecuentes.</span><span class="sxs-lookup"><span data-stu-id="82714-119">Do more frequent planning runs.</span></span> <span data-ttu-id="82714-120">(No está limitado a ejecuciones durante el día).</span><span class="sxs-lookup"><span data-stu-id="82714-120">(You aren't limited to daily runs.)</span></span>
- <span data-ttu-id="82714-121">Esté seguro de que el crecimiento futuro del negocio no sobrecargará el sistema de planificación.</span><span class="sxs-lookup"><span data-stu-id="82714-121">Be confident that future business growth won't overload the planning system.</span></span>

## <a name="architecture-and-data-flow"></a><span data-ttu-id="82714-122">Arquitectura y flujo de datos</span><span class="sxs-lookup"><span data-stu-id="82714-122">Architecture and data flow</span></span>

<span data-ttu-id="82714-123">Cuando el complemento de optimización de la planificación está instalado desde LCS, se establece una conexión segura al servicio de optimización de la planificación.</span><span class="sxs-lookup"><span data-stu-id="82714-123">When the Planning Optimization Add-in is installed from LCS, a secure connection to the Planning Optimization service is established.</span></span> <span data-ttu-id="82714-124">El servicio se encuentra en el mismo país o región del centro de datos que la instancia relacionada de Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="82714-124">The service is located in the same data center country or region as the related Supply Chain Management instance.</span></span> <span data-ttu-id="82714-125">Después de configurar la optimización de la planificación, cuando se ejecuta la planificación maestra, los datos maestros y los datos transaccionales se envían desde Supply Chain Management al servicio de optimización de la planificación.</span><span class="sxs-lookup"><span data-stu-id="82714-125">After Planning Optimization is set up, when master planning is run, master data and transactional data are sent from Supply Chain Management to the Planning Optimization service.</span></span>

<span data-ttu-id="82714-126">Si se desinstala el complemento de optimización de la planificación, todos los datos relacionados en el servicio de optimización de la planificación se eliminan.</span><span class="sxs-lookup"><span data-stu-id="82714-126">If the Planning Optimization Add-in is uninstalled, all related data in the Planning Optimization service is removed.</span></span>

### <a name="high-level-data-flow-for-regeneration-runs"></a><span data-ttu-id="82714-127">Flujo de datos de alto nivel para ejecuciones de regeneración</span><span class="sxs-lookup"><span data-stu-id="82714-127">High-level data flow for regeneration runs</span></span>

1. <span data-ttu-id="82714-128">El cliente de Supply Chain Management registra una señal para solicitar una ejecución de la planificación desde la optimización de la planificación.</span><span class="sxs-lookup"><span data-stu-id="82714-128">The Supply Chain Management client sends a signal to request a planning run from Planning Optimization.</span></span>
2. <span data-ttu-id="82714-129">La optimización de la planificación solicita los datos necesarios mediante el conector integrado.</span><span class="sxs-lookup"><span data-stu-id="82714-129">Planning Optimization requests the required data via the integrated connector.</span></span>
3. <span data-ttu-id="82714-130">La base de datos SQL envía la información solicitada sobre la configuración, la planificación maestra y los datos transaccionales para la optimización de la planificación a través del conector.</span><span class="sxs-lookup"><span data-stu-id="82714-130">The SQL database sends the requested information about setup, master, and transactional data to Planning Optimization via the connector.</span></span> <span data-ttu-id="82714-131">El conector traduce la información entre Supply Chain Management y el servicio de optimización de la planificación.</span><span class="sxs-lookup"><span data-stu-id="82714-131">The connector translates information between Supply Chain Management and the Planning Optimization service.</span></span>
4. <span data-ttu-id="82714-132">El servicio de optimización de la planificación contiene datos relacionados con la planificación en la memoria y realiza los cálculos necesarios.</span><span class="sxs-lookup"><span data-stu-id="82714-132">The Planning Optimization service holds planning-related data in memory and does the required calculations.</span></span>
5. <span data-ttu-id="82714-133">El resultado de la planificación se envía a la base de datos de Supply Chain Management a través del conector.</span><span class="sxs-lookup"><span data-stu-id="82714-133">The planning result is sent to the Supply Chain Management database via the connector.</span></span> <span data-ttu-id="82714-134">Los resultados incluyen información como pedidos planificados e información de diagrama de árbol.</span><span class="sxs-lookup"><span data-stu-id="82714-134">The results include information such as planned orders and pegging information.</span></span> <span data-ttu-id="82714-135">La optimización de la planificación envía una señal a Supply Chain Management para indicar que la ejecución de la planificación se ha completado.</span><span class="sxs-lookup"><span data-stu-id="82714-135">Planning Optimization sends a signal to Supply Chain Management to indicate that the planning run has been completed.</span></span> <span data-ttu-id="82714-136">También envía mensajes y advertencias relevantes.</span><span class="sxs-lookup"><span data-stu-id="82714-136">It also sends any relevant messages and warnings.</span></span>

<span data-ttu-id="82714-137">La ilustración siguientes muestran el flujo de datos.</span><span class="sxs-lookup"><span data-stu-id="82714-137">The following illustration shows the data flow.</span></span>

![Flujo de datos para ejecuciones de regeneración](media/PlanningOptimization2.png)

## <a name="related-resources"></a><span data-ttu-id="82714-139">Recursos relacionados</span><span class="sxs-lookup"><span data-stu-id="82714-139">Related resources</span></span>

[<span data-ttu-id="82714-140">Introducción a la optimización de planificación</span><span class="sxs-lookup"><span data-stu-id="82714-140">Get started with Planning Optimization</span></span>](get-started.md)

[<span data-ttu-id="82714-141">Análisis de aptitud de la optimización de la planificación</span><span class="sxs-lookup"><span data-stu-id="82714-141">Planning Optimization fit analysis</span></span>](planning-optimization-fit-analysis.md)

[<span data-ttu-id="82714-142">Ver el historial del plan y los registros de planificación</span><span class="sxs-lookup"><span data-stu-id="82714-142">View plan history and planning logs</span></span>](plan-history-logs.md)

[<span data-ttu-id="82714-143">Aplicar filtros a un plan</span><span class="sxs-lookup"><span data-stu-id="82714-143">Apply filters to a plan</span></span>](plan-filters.md)

[<span data-ttu-id="82714-144">Cancelar un trabajo de planificación</span><span class="sxs-lookup"><span data-stu-id="82714-144">Cancel a planning job</span></span>](cancel-planning-job.md)
