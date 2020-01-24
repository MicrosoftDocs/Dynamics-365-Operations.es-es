---
title: Análisis de aptitud de la optimización de la planificación
description: Este tema explica cómo comprobar la configuración actual y los datos frente a las prestaciones de la funcionalidad de optimización de la planificación.
author: ChristianRytt
manager: AnnBe
ms.date: 10/30/2019
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
ms.openlocfilehash: a61529da63bc20fdd591afc94db960b05c284bb9
ms.sourcegitcommit: b806f0c94d703bec39680fead827733361d47045
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "2935884"
---
[!include [banner](../../includes/preview-banner.md)]
[!include [banner](../../includes/banner.md)]

# <a name="planning-optimization-fit-analysis"></a><span data-ttu-id="383f4-103">Análisis de aptitud de la optimización de la planificación</span><span class="sxs-lookup"><span data-stu-id="383f4-103">Planning Optimization fit analysis</span></span>

<span data-ttu-id="383f4-104">Para ver el grado de compatibilidad de su configuración actual y los datos con la funcionalidad de optimización de la planificación, vaya **Planificación maestra** \> **Configuración** \> **Análisis de aptitud de la optimización de la planificación** y después seleccione **Ejecutar análisis**.</span><span class="sxs-lookup"><span data-stu-id="383f4-104">To see how compatible your current setup and data are with the Planning Optimization functionality, go to **Master planning** \> **Setup** \> **Planning Optimization fit analysis**, and then select **Run analysis**.</span></span> <span data-ttu-id="383f4-105">Si el análisis detecta incoherencias, se enumeran en la misma página.</span><span class="sxs-lookup"><span data-stu-id="383f4-105">If the analysis finds any inconsistencies, they are listed on the same page.</span></span> <span data-ttu-id="383f4-106">(El análisis puede tardar algunos minutos en ejecutarse).</span><span class="sxs-lookup"><span data-stu-id="383f4-106">(The analysis can take a few minutes to run.)</span></span>

> [!NOTE]
> <span data-ttu-id="383f4-107">Si se encuentran incoherencias, puede usar la optimización de la planificación.</span><span class="sxs-lookup"><span data-stu-id="383f4-107">If inconsistencies are found, you can still use Planning Optimization.</span></span> <span data-ttu-id="383f4-108">Los resultados del análisis de aptitud solo muestran las ubicaciones en las que el servicio de planificación no coincide con la configuración actual.</span><span class="sxs-lookup"><span data-stu-id="383f4-108">The results of the fit analysis just show places where the planning service won't honor your current setup.</span></span> <span data-ttu-id="383f4-109">Es decir, muestran las ubicaciones en las que algunos procesos se pueden omitir o no están admitidos.</span><span class="sxs-lookup"><span data-stu-id="383f4-109">In other words, they show places where some processes might be ignored or might not be supported.</span></span>

## <a name="analysis-results-example-1"></a><span data-ttu-id="383f4-110">Resultados de análisis: ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="383f4-110">Analysis results: Example 1</span></span>

- <span data-ttu-id="383f4-111">**Característica:** producción</span><span class="sxs-lookup"><span data-stu-id="383f4-111">**Feature:** Production</span></span>
- <span data-ttu-id="383f4-112">**Problema:** artículos con L.MAT mayor que cero: 56</span><span class="sxs-lookup"><span data-stu-id="383f4-112">**Issue:** Items with BOM level greater than zero: 56</span></span>
- <span data-ttu-id="383f4-113">**Explicación:** el análisis de aptitud encontró 56 artículos con una lista de materiales (L.MAT) configurada para producción.</span><span class="sxs-lookup"><span data-stu-id="383f4-113">**Explanation:** The fit analysis found 56 items that have a bill of materials (BOM) setup for production.</span></span> <span data-ttu-id="383f4-114">Dado que la versión actual de la optimización de la planificación no admite la producción, la optimización de la planificación generará pedidos de compra planificados en lugar de pedidos de producción planificados.</span><span class="sxs-lookup"><span data-stu-id="383f4-114">Because the current version of Planning Optimization doesn't support production, Planning Optimization will generate planned purchase orders instead of planned production orders.</span></span> <span data-ttu-id="383f4-115">También mostrará una advertencia que enumere los artículos afectados.</span><span class="sxs-lookup"><span data-stu-id="383f4-115">It will also show a warning that lists the affected items.</span></span>

### <a name="analysis-results-example-2"></a><span data-ttu-id="383f4-116">Resultados de análisis: ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="383f4-116">Analysis results: Example 2</span></span>

- <span data-ttu-id="383f4-117">**Característica:** acciones</span><span class="sxs-lookup"><span data-stu-id="383f4-117">**Feature:** Actions</span></span>
- <span data-ttu-id="383f4-118">**Problema:** grupos de cobertura con el cálculo de las acciones habilitado: 6</span><span class="sxs-lookup"><span data-stu-id="383f4-118">**Issue:** Coverage groups with actions calculation enabled: 6</span></span>
- <span data-ttu-id="383f4-119">**Explicación:** el análisis de aptitud detectó seis grupos de cobertura donde el cálculo de la acción está activado.</span><span class="sxs-lookup"><span data-stu-id="383f4-119">**Explanation:** The fit analysis found six coverage groups where action calculation is turned on.</span></span> <span data-ttu-id="383f4-120">Dado que la versión actual de la optimización de la planificación no admite acciones, no se generarán acciones durante la planificación maestra.</span><span class="sxs-lookup"><span data-stu-id="383f4-120">Because the current version of Planning Optimization doesn't support actions, no actions will be generated during master planning.</span></span>

## <a name="related-resources"></a><span data-ttu-id="383f4-121">Recursos relacionados</span><span class="sxs-lookup"><span data-stu-id="383f4-121">Related resources</span></span>

[<span data-ttu-id="383f4-122">Visión general de la optimización de la planificación</span><span class="sxs-lookup"><span data-stu-id="383f4-122">Planning Optimization overview</span></span>](planning-optimization-overview.md)

[<span data-ttu-id="383f4-123">Introducción a la optimización de planificación</span><span class="sxs-lookup"><span data-stu-id="383f4-123">Get started with Planning Optimization</span></span>](get-started.md)

[<span data-ttu-id="383f4-124">Ver el historial del plan y los registros de planificación</span><span class="sxs-lookup"><span data-stu-id="383f4-124">View plan history and planning logs</span></span>](plan-history-logs.md)

[<span data-ttu-id="383f4-125">Aplicar filtros a un plan</span><span class="sxs-lookup"><span data-stu-id="383f4-125">Apply filters to a plan</span></span>](plan-filters.md)

[<span data-ttu-id="383f4-126">Cancelar un trabajo de planificación</span><span class="sxs-lookup"><span data-stu-id="383f4-126">Cancel a planning job</span></span>](cancel-planning-job.md)
