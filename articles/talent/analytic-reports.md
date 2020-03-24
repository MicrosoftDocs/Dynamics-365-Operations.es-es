---
title: Utilizar informes de análisis en Attract
description: Este tema describe los informes analíticos para el proceso de contratación en Microsoft Dynamics 365 Talent - Attract
author: fewatson
manager: AnnBe
ms.date: 04/30/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: fewatson
ms.search.validFrom: 2019-04-30
ms.dyn365.ops.version: Talent April 2019 update
ms.openlocfilehash: 081988e8b8cfe1e2ddb533247b678ba38a07f5f1
ms.sourcegitcommit: f38302b9430f2ab3efe91d0a7beff946bc610e8f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "3092232"
---
# <a name="use-analytic-reports-in-attract"></a><span data-ttu-id="53acf-103">Utilizar informes de análisis en Attract</span><span class="sxs-lookup"><span data-stu-id="53acf-103">Use analytic reports in Attract</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="53acf-104">Los informes analíticos en Microsoft Dynamics 365 Talent: Attract proporcionan una solución de (OOTB) lista para usarse y obtener información del proceso de contratación.</span><span class="sxs-lookup"><span data-stu-id="53acf-104">Analytic reports in Microsoft Dynamics 365 Talent: Attract provide an out-of-the-box (OOTB) solution for hiring process insights.</span></span> <span data-ttu-id="53acf-105">Entre las características disponibles se incluyen:</span><span class="sxs-lookup"><span data-stu-id="53acf-105">Availabe features include:</span></span>

- <span data-ttu-id="53acf-106">**Análisis de trabajo:** haga clic en la pestaña **Análisis** dentro de las medidas de un trabajo en los candidatos al trabajo.</span><span class="sxs-lookup"><span data-stu-id="53acf-106">**Job analytics:** Click the **Analytics** tab within a job for metrics on the job's applicants.</span></span>
- <span data-ttu-id="53acf-107">**Centro de análisis:** haga clic en **Análisis** en la barra izquierda para ver las medidas agregadas a lo largo de los trabajos.</span><span class="sxs-lookup"><span data-stu-id="53acf-107">**Analytics hub:** Click **Analytics** on the left navigation for aggregated metrics across jobs.</span></span>
- <span data-ttu-id="53acf-108">**Seguridad específica de usuario:** el acceso a los informes se controla en Attract mediante [roles](security-attract.md) y el rol del participante en el trabajo.</span><span class="sxs-lookup"><span data-stu-id="53acf-108">**User-specific security:** Access to reports is controlled by Attract [role](security-attract.md) and job participant role.</span></span>
- <span data-ttu-id="53acf-109">**Filtro cruzado:** haga clic en las imágenes en un informe para ver otras medidas filtradas por los datos seleccionados.</span><span class="sxs-lookup"><span data-stu-id="53acf-109">**Cross-filtering:** Click visuals within a report to view other metrics filtered by selected data.</span></span>

>[!NOTE] 
>- <span data-ttu-id="53acf-110">Esta característica está actualmente en [vista previa](access-preview-feature.md).</span><span class="sxs-lookup"><span data-stu-id="53acf-110">This feature is currently in [preview](access-preview-feature.md).</span></span> <span data-ttu-id="53acf-111">Para probarla, debe tener el [**Complemento de contratación completo**](attract-comprehensive-hiring.md).</span><span class="sxs-lookup"><span data-stu-id="53acf-111">To try it, you must have the [**Comprehensive Hiring Add-On**](attract-comprehensive-hiring.md).</span></span>
>- <span data-ttu-id="53acf-112">Todos los informes público de vista previa se muestran en inglés.</span><span class="sxs-lookup"><span data-stu-id="53acf-112">All public preview reports are displayed in English.</span></span>
>- <span data-ttu-id="53acf-113">Los informes se actualizan cada 3 horas.</span><span class="sxs-lookup"><span data-stu-id="53acf-113">Reports refresh every 3 hours.</span></span> <span data-ttu-id="53acf-114">La última hora de actualización (en la zona horaria local) se encuentra en la parte superior del informe.</span><span class="sxs-lookup"><span data-stu-id="53acf-114">The last refresh time (in the local timezone) is located at the top of the report.</span></span> <span data-ttu-id="53acf-115">Los tiempos de actualización son una aproximación y varían en función del volumen de datos y carga del recurso en la región.</span><span class="sxs-lookup"><span data-stu-id="53acf-115">Refresh times are an approximation and vary based on data volume and resource load in your region.</span></span>

## <a name="job-analytics"></a><span data-ttu-id="53acf-116">Análisis de trabajos</span><span class="sxs-lookup"><span data-stu-id="53acf-116">Job Analytics</span></span>

<span data-ttu-id="53acf-117">Los informes de Análisis de trabajo ofrecen una instantánea del proceso de contratación para un trabajo.</span><span class="sxs-lookup"><span data-stu-id="53acf-117">Job Analytics reports are a snapshot of the hiring process for a job.</span></span>  <span data-ttu-id="53acf-118">Entre las medidas clave están:</span><span class="sxs-lookup"><span data-stu-id="53acf-118">Key metrics include:</span></span>

- <span data-ttu-id="53acf-119">Candidatos activos por etapa</span><span class="sxs-lookup"><span data-stu-id="53acf-119">Active applicants by stage</span></span>
- <span data-ttu-id="53acf-120">Origen del candidato</span><span class="sxs-lookup"><span data-stu-id="53acf-120">Applicant source</span></span>
- <span data-ttu-id="53acf-121">Tipo de candidato (interno o externo)</span><span class="sxs-lookup"><span data-stu-id="53acf-121">Applicant type (internal or external)</span></span>

## <a name="analytics-hub"></a><span data-ttu-id="53acf-122">Centro de análisis</span><span class="sxs-lookup"><span data-stu-id="53acf-122">Analytics Hub</span></span>

<span data-ttu-id="53acf-123">Los informes del Centro de análisis agregan datos a lo largo de los trabajos para revelar tendencias superficiales en el proceso de contratación.</span><span class="sxs-lookup"><span data-stu-id="53acf-123">Analytics Hub reports aggregate data across jobs to surface trends in the hiring process.</span></span> <span data-ttu-id="53acf-124">Attract incluye dos informes de OOTB: Componentes del resumen y el Análisis de embudo.</span><span class="sxs-lookup"><span data-stu-id="53acf-124">Attract includes two OOTB reports: Pipeline Summary and Funnel Analysis.</span></span>

### <a name="pipeline-summary"></a><span data-ttu-id="53acf-125">Resumen de proceso</span><span class="sxs-lookup"><span data-stu-id="53acf-125">Pipeline Summary</span></span>

<span data-ttu-id="53acf-126">El informe de resumen de proceso agrega los datos para las vacantes.</span><span class="sxs-lookup"><span data-stu-id="53acf-126">The Pipeline Summary report aggregates data for open jobs.</span></span> <span data-ttu-id="53acf-127">Entre las medidas clave están:</span><span class="sxs-lookup"><span data-stu-id="53acf-127">Key metrics include:</span></span>

- <span data-ttu-id="53acf-128">Candidatos en todos los trabajos por etapa</span><span class="sxs-lookup"><span data-stu-id="53acf-128">Applicants across all jobs by stage</span></span>
- <span data-ttu-id="53acf-129">Origen del candidato</span><span class="sxs-lookup"><span data-stu-id="53acf-129">Applicant source</span></span>
- <span data-ttu-id="53acf-130">Vacantes por nivel de antigüedad</span><span class="sxs-lookup"><span data-stu-id="53acf-130">Open jobs by seniority level</span></span>

### <a name="funnel-analysis"></a><span data-ttu-id="53acf-131">Análisis de embudo</span><span class="sxs-lookup"><span data-stu-id="53acf-131">Funnel Analysis</span></span>

<span data-ttu-id="53acf-132">El informe análisis de embudo agrega los datos para los trabajos que se han cerrado como ocupados.</span><span class="sxs-lookup"><span data-stu-id="53acf-132">The Funnel Analysis report aggregates data for jobs that have been closed as filled.</span></span> <span data-ttu-id="53acf-133">Entre las medidas clave están:</span><span class="sxs-lookup"><span data-stu-id="53acf-133">Key metrics include:</span></span>

- <span data-ttu-id="53acf-134">Tiempo para contratar</span><span class="sxs-lookup"><span data-stu-id="53acf-134">Time to hire</span></span>
- <span data-ttu-id="53acf-135">Métricas de conversión (manteniendo el puntero)</span><span class="sxs-lookup"><span data-stu-id="53acf-135">Conversion metrics (on hover)</span></span>
- <span data-ttu-id="53acf-136">Tasa de aceptación de la propuesta</span><span class="sxs-lookup"><span data-stu-id="53acf-136">Offer acceptance rate</span></span>

<span data-ttu-id="53acf-137">Nota: para obtener el tiempo para contratar más preciso en el informe, se recomienda el uso de [Administración de la propuesta](offer-setup.md), una característica disponibles como parte del complemento de contratación completo.</span><span class="sxs-lookup"><span data-stu-id="53acf-137">Note: For the most accurate time to hire reporting, it is recommended that you use [Offer management](offer-setup.md), a feature available as part of the Comprehensive Hiring Add-On.</span></span>

>[!TIP] 
><span data-ttu-id="53acf-138">Pruebe a mantener el puntero sobre los gráficos para obtener información adicional.</span><span class="sxs-lookup"><span data-stu-id="53acf-138">Try hovering over visuals for additional information.</span></span> <span data-ttu-id="53acf-139">Por ejemplo, al mantener el puntero sobre los gráficos de **Candidatos activos**, estos mostrarán los días medios en etapa.</span><span class="sxs-lookup"><span data-stu-id="53acf-139">For example, hovering over **Active applicants** visuals will display the average days in stage.</span></span> <span data-ttu-id="53acf-140">Analizar esta información puede proporcionar datos críticos para reducir el tiempo de contratación y permitir a los reclutadores centrarse en formas de reducir el tiempo empleado en cada etapa.</span><span class="sxs-lookup"><span data-stu-id="53acf-140">Analyzing this information can provide insights critical to reducing time to hire and enable recruiters to focus on ways to reduce the time spent in each stage.</span></span>

## <a name="user-specific-security"></a><span data-ttu-id="53acf-141">Seguridad específica del usuario.</span><span class="sxs-lookup"><span data-stu-id="53acf-141">User-specific security</span></span>

<span data-ttu-id="53acf-142">Los informes de Attract están accesibles para los [roles](security-attract.md) de Administradores, Leer todos, Reclutador y el Jefe de contratación.</span><span class="sxs-lookup"><span data-stu-id="53acf-142">Attract reports are accessible for Admin, Read All, Recruiter, and Hiring Manager [roles](security-attract.md).</span></span> <span data-ttu-id="53acf-143">Los usuarios no asignados no tienen acceso a las páginas del informe de análisis (Análisis de trabajo y Centro de análisis)</span><span class="sxs-lookup"><span data-stu-id="53acf-143">Unassigned users do not have access to either of the analytic report pages (Job Analytics or Analytics Hub).</span></span>

<span data-ttu-id="53acf-144">Los informes de Análisis de trabajo muestran datos para el trabajo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="53acf-144">Job Analytics reports display data for the selected job.</span></span> <span data-ttu-id="53acf-145">Los informes del Centro de análisis agregan datos a lo largo de todos los trabajos que puede ver un usuario.</span><span class="sxs-lookup"><span data-stu-id="53acf-145">Analytics Hub reports aggregate data across all jobs a user can view.</span></span> <span data-ttu-id="53acf-146">Los usuarios que pueden ver Mis trabajos y Todos los trabajos en la página de los trabajos tienen las mismas vistas disponibles en el Centro de análisis.</span><span class="sxs-lookup"><span data-stu-id="53acf-146">Users that can view both My jobs and All jobs on the Jobs page have the same views available in the Analytics Hub.</span></span>

## <a name="cross-filter"></a><span data-ttu-id="53acf-147">Filtro cruzado</span><span class="sxs-lookup"><span data-stu-id="53acf-147">Cross-filter</span></span>

<span data-ttu-id="53acf-148">Una de las grandes características de Power BI es la forma que todas las representaciones visuales en una página del informe se interconectan.</span><span class="sxs-lookup"><span data-stu-id="53acf-148">One of the great features of Power BI is the way all visuals on a report page are interconnected.</span></span> <span data-ttu-id="53acf-149">Si selecciona un punto de datos en una de las representaciones visuales, el resto de representaciones visuales en la página que contengan ese dato cambiarán, basándose en esa selección.</span><span class="sxs-lookup"><span data-stu-id="53acf-149">If you select a data point on one of the visuals, all the other visuals on the page that contain that data change, based on that selection.</span></span> <span data-ttu-id="53acf-150">Descubra más y ver un ejemplo en [Cómo las representaciones cruzadas usan filtros cruzados en un informe de Power BI](https://docs.microsoft.com/power-bi/consumer/end-user-interactions).</span><span class="sxs-lookup"><span data-stu-id="53acf-150">Find out more and see an example in [How visuals cross-filter each other in a Power BI report](https://docs.microsoft.com/power-bi/consumer/end-user-interactions).</span></span>

## <a name="export-to-excel"></a><span data-ttu-id="53acf-151">Exportar a Excel</span><span class="sxs-lookup"><span data-stu-id="53acf-151">Export to Excel</span></span>

<span data-ttu-id="53acf-152">Para ver los datos del informe en Excel, puede hacer clic en el menú de las opciones (tres puntos) en una representación visual y seleccionar **Exportar los datos subyacentes**.</span><span class="sxs-lookup"><span data-stu-id="53acf-152">To view report data in Excel, you can click the options menu (three dots) on a visual and select **Export underlying data**.</span></span> <span data-ttu-id="53acf-153">Los datos exportados se exportarán filtrados, respetando los permisos de usuario en Attract.</span><span class="sxs-lookup"><span data-stu-id="53acf-153">Exported data will export as filtered, respecting user permissions in Attract.</span></span> <span data-ttu-id="53acf-154">Para obtener más información, consulte [Exportar los datos de visualizaciones](https://docs.microsoft.com/power-bi/visuals/power-bi-visualization-export-data).</span><span class="sxs-lookup"><span data-stu-id="53acf-154">For more information, see [Export data from visualizations](https://docs.microsoft.com/power-bi/visuals/power-bi-visualization-export-data).</span></span>
