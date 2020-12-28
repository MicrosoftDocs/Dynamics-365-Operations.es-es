---
title: Supervisar una ejecución de planificación maestra
description: Este tema explica cómo el planificador de la producción puede ver si una ejecución de la planificación maestra está en curso.
author: josaw1
manager: tfehr
ms.date: 11/04/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, ReqCreatePlanWorkspace, ReqTransPlanCard, SysQueryForm, InventItemIdLookupSimple, ReqLog, ReqProcessTaskTrace
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 045b82af6f65b22e1c683f8de47a6df282711e6a
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4436629"
---
# <a name="monitor-a-master-planning-run"></a><span data-ttu-id="a7d44-103">Supervisar una ejecución de planificación maestra</span><span class="sxs-lookup"><span data-stu-id="a7d44-103">Monitor a master planning run</span></span>

[!include [banner](../../includes/banner.md)]

## <a name="use-a-gantt-chart-to-visualize-master-planning-progress"></a><span data-ttu-id="a7d44-104">Usar un gráfico de Gantt para visualizar el progreso de la planificación maestra</span><span class="sxs-lookup"><span data-stu-id="a7d44-104">Use a Gantt chart to visualize master planning progress</span></span>

<span data-ttu-id="a7d44-105">En la página **Ver el progreso de la planificación maestra**, puede ver los detalles de las ejecuciones históricos de la planificación maestra como gráfico de Gantt.</span><span class="sxs-lookup"><span data-stu-id="a7d44-105">From the **View master planning progress** page, you can view details of historical master planning runs as a Gantt chart.</span></span> <span data-ttu-id="a7d44-106">Esta función puede ayudarle a comprender el tiempo que se emplea en las distintas fases de la planificación maestra.</span><span class="sxs-lookup"><span data-stu-id="a7d44-106">This functionality can help you understand the time that is spent on the various phases of master planning.</span></span> <span data-ttu-id="a7d44-107">Para un trabajo de planificación de activo actual, la página **Ver el progreso de la planificación maestra** se puede usar para realizar el seguimiento del progreso y ver el tiempo estimado restante.</span><span class="sxs-lookup"><span data-stu-id="a7d44-107">For a current active planning job, the **View master planning progress** page can be used to track progress and view the estimated remaining time.</span></span>

### <a name="turn-on-and-use-the-master-plan-progress-visualization-feature"></a><span data-ttu-id="a7d44-108">Activar y usar la función de la visualización del progreso del plan maestro</span><span class="sxs-lookup"><span data-stu-id="a7d44-108">Turn on and use the Master plan progress visualization feature</span></span>

<span data-ttu-id="a7d44-109">Para usar esta funcionalidad, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="a7d44-109">To use this functionality, follow these steps.</span></span>

1. <span data-ttu-id="a7d44-110">En el espacio de trabajo **Administración de características**, en la pestaña **Nuevo**, seleccione **Visualización del progreso de la planificación maestra** en la lista.</span><span class="sxs-lookup"><span data-stu-id="a7d44-110">In the **Feature management** workspace, on the **New** tab, select **Master planning progress visualization** in the list.</span></span> <span data-ttu-id="a7d44-111">Si la característica no aparece en la pestaña **Nuevo**, mire en las pestañas **No habilitado** y **Todo**.</span><span class="sxs-lookup"><span data-stu-id="a7d44-111">If the feature doesn't appear on the **New** tab, look on the **Not enabled** and **All** tabs.</span></span>
1. <span data-ttu-id="a7d44-112">Seleccione **Habilitar ahora**.</span><span class="sxs-lookup"><span data-stu-id="a7d44-112">Select **Enable now**.</span></span> <span data-ttu-id="a7d44-113">Como alternativa, seleccione **Programación** y el tiempo en que desea que la función esté activada.</span><span class="sxs-lookup"><span data-stu-id="a7d44-113">Alternatively, select **Schedule**, and then select the time when you want the feature to be turned on.</span></span>

<span data-ttu-id="a7d44-114">La página **Ver el progreso de la planificación maestra** puede mostrar trabajos históricos de planificación y trabajos activos de planificación.</span><span class="sxs-lookup"><span data-stu-id="a7d44-114">The **View master planning progress** page can display both historical planning jobs and active planning jobs.</span></span> 

<span data-ttu-id="a7d44-115">Para ver los trabajos históricos de planificación, hay dos opciones.</span><span class="sxs-lookup"><span data-stu-id="a7d44-115">To view historical planning jobs, there are two options.</span></span> 

1. <span data-ttu-id="a7d44-116">Vaya a **Planificación maestra \> Configuración \> Planes \> Planes maestros** y, después en el panel Acciones, seleccione **Historial**.</span><span class="sxs-lookup"><span data-stu-id="a7d44-116">Go to **Master planning \> Setup \> Plans \> Master plans**, and then, on the Action Pane, select **History**.</span></span> <span data-ttu-id="a7d44-117">Con el trabajo deseado seleccionado, seleccione **Consultas**, y después seleccione **Progreso de la vista**.</span><span class="sxs-lookup"><span data-stu-id="a7d44-117">With the desired job selected, select **Inquiries**,  and then select **View progress**</span></span>
1. <span data-ttu-id="a7d44-118">Vaya a **Planificación maestra \> Espacios de trabajo \> Planificación maestra**, en el mosaico de planificación maestra hacen clic en **Historial**.</span><span class="sxs-lookup"><span data-stu-id="a7d44-118">Go to **Master planning \> Workspaces \> Master planning**, on the Master planning tile click **History**.</span></span> <span data-ttu-id="a7d44-119">Con el trabajo deseado seleccionado, seleccione **Consultas**, y después seleccione **Progreso de la vista**.</span><span class="sxs-lookup"><span data-stu-id="a7d44-119">With the desired job selected, select **Inquiries**,  and then select **View progress**</span></span>

<span data-ttu-id="a7d44-120">Para ver los trabajos activos de planificación, hay dos opciones.</span><span class="sxs-lookup"><span data-stu-id="a7d44-120">To view active planning jobs, there are two options.</span></span> 
1. <span data-ttu-id="a7d44-121">Vaya a **Planificación maestra \> Espacios de trabajo \> Planificación maestra**, en el panel de Acciones, seleccione **Proceso de planificación inacabado**.</span><span class="sxs-lookup"><span data-stu-id="a7d44-121">Go to **Master planning \> Workspaces \> Master planning**, on the Action Pane, select **Unfinished planning process**.</span></span> <span data-ttu-id="a7d44-122">Con el trabajo deseado seleccionado, seleccione **Consultas**, y después seleccione **Progreso de la vista**.</span><span class="sxs-lookup"><span data-stu-id="a7d44-122">With the desired job selected, select **Inquiries**,  and then select **View progress**.</span></span>
1. <span data-ttu-id="a7d44-123">Vaya a **Planificación maestra \> Espacios de trabajo \> Planificación maestra**, en el mosaico de planificación maestra hacen clic en **Ver progresos**.</span><span class="sxs-lookup"><span data-stu-id="a7d44-123">Go to **Master planning \> Workspaces \> Master planning**, on the Master planning tile click **View progress**.</span></span> <span data-ttu-id="a7d44-124">Con el trabajo deseado seleccionado, seleccione **Consultas**, y después seleccione **Progreso de la vista**.</span><span class="sxs-lookup"><span data-stu-id="a7d44-124">With the desired job selected, select **Inquiries**,  and then select **View progress**</span></span>

<span data-ttu-id="a7d44-125">Nota: Puede ver trabajos activos solo cuando un trabajo de planificación se está procesando.</span><span class="sxs-lookup"><span data-stu-id="a7d44-125">Note you can view active jobs only when a planning job is processing.</span></span>

### <a name="analyze-a-master-planning-job"></a><span data-ttu-id="a7d44-126">Analizar un trabajo de planificación maestra</span><span class="sxs-lookup"><span data-stu-id="a7d44-126">Analyze a master planning job</span></span>

<span data-ttu-id="a7d44-127">En el gráfico de Gantt, puede expandir cada uno de los procesos de planificación siguientes para ver los detalles adicionales sobre el tiempo dedicado:</span><span class="sxs-lookup"><span data-stu-id="a7d44-127">In the Gantt chart, you can expand each of the following planning processes to view additional details about the time that is spent:</span></span>

- <span data-ttu-id="a7d44-128">Inicializando</span><span class="sxs-lookup"><span data-stu-id="a7d44-128">Initializing</span></span>
- <span data-ttu-id="a7d44-129">Eliminando e insertando datos</span><span class="sxs-lookup"><span data-stu-id="a7d44-129">Deleting and inserting data</span></span>
- <span data-ttu-id="a7d44-130">Planificación de la cobertura</span><span class="sxs-lookup"><span data-stu-id="a7d44-130">Coverage planning</span></span>
- <span data-ttu-id="a7d44-131">Retrasos</span><span class="sxs-lookup"><span data-stu-id="a7d44-131">Delays</span></span>
- <span data-ttu-id="a7d44-132">Mensajes de acción</span><span class="sxs-lookup"><span data-stu-id="a7d44-132">Action messages</span></span>
- <span data-ttu-id="a7d44-133">Finalización</span><span class="sxs-lookup"><span data-stu-id="a7d44-133">Finalization</span></span>
- <span data-ttu-id="a7d44-134">Puesta en firme automática</span><span class="sxs-lookup"><span data-stu-id="a7d44-134">Auto-firming</span></span>

<span data-ttu-id="a7d44-135">El gráfico de Gantt es una herramienta útil si desea ver el impacto de usar mensajes de acción.</span><span class="sxs-lookup"><span data-stu-id="a7d44-135">The Gantt chart is a useful tool if you want to view the impact of using action messages.</span></span>

#### <a name="navigation-in-the-gantt-chart"></a><span data-ttu-id="a7d44-136">Exploración en el gráfico de Gantt</span><span class="sxs-lookup"><span data-stu-id="a7d44-136">Navigation in the Gantt chart</span></span>

- <span data-ttu-id="a7d44-137">Para ampliar el grupo seleccionado y mostrar los detalles, seleccione el signo más (**+**) en la vista de árbol.</span><span class="sxs-lookup"><span data-stu-id="a7d44-137">To expand the selected group and show the details, select the plus sign (**+**) in the tree view.</span></span>
- <span data-ttu-id="a7d44-138">Para contraer el grupo seleccionado, seleccione el signo menos (**–**) en la vista de árbol.</span><span class="sxs-lookup"><span data-stu-id="a7d44-138">To collapse the selected group, select the minus sign (**–**) in the tree view.</span></span>
- <span data-ttu-id="a7d44-139">Puede usar la teclado para la exploración.</span><span class="sxs-lookup"><span data-stu-id="a7d44-139">You can use your keyboard for navigation.</span></span> <span data-ttu-id="a7d44-140">Use las teclas **Flecha arriba** y **Flecha abajo** para desplazarse entre las filas.</span><span class="sxs-lookup"><span data-stu-id="a7d44-140">Use the **Up arrow** and **Down arrow** keys to move between rows.</span></span> <span data-ttu-id="a7d44-141">Use las teclas **Flecha derecha** y **Flecha izquierda** para expandir y contraer los grupos.</span><span class="sxs-lookup"><span data-stu-id="a7d44-141">Use the **Right arrow** and **Left arrow** keys to expand and collapse groups.</span></span>
- <span data-ttu-id="a7d44-142">Para abrir o cerrar todos los niveles en el gráfico de Gantt, seleccione **Ampliar todo** o **Contraer todo**.</span><span class="sxs-lookup"><span data-stu-id="a7d44-142">To open or close all levels in the Gantt chart, select **Expand all** or **Collapse all**.</span></span>
- <span data-ttu-id="a7d44-143">Para ver el tiempo de procesamiento relacionado, mantenga el puntero sobre la tarea.</span><span class="sxs-lookup"><span data-stu-id="a7d44-143">To view the related processing time, hover over a task.</span></span> <span data-ttu-id="a7d44-144">(Las tareas son el nivel inferior en el gráfico de Gantt).</span><span class="sxs-lookup"><span data-stu-id="a7d44-144">(Tasks are the lowest level in the Gantt chart.)</span></span>

#### <a name="view-an-additional-master-planning-run-to-compare-jobs"></a><span data-ttu-id="a7d44-145">Ver una ejecución adicional de la planificación maestra para comparar trabajos</span><span class="sxs-lookup"><span data-stu-id="a7d44-145">View an additional master planning run to compare jobs</span></span>

<span data-ttu-id="a7d44-146">Si se selecciona un trabajo de planificación maestra en el campo **Mostrar ejecución adicional de planificación maestra**, puede ver una ejecución adicional de la planificación maestra en el gráfico de Gantt y comparar los dos trabajos.</span><span class="sxs-lookup"><span data-stu-id="a7d44-146">By selecting a master planning job on field **Show additional master planning run**, you can view an additional master planning run in the Gantt chart and compare the two jobs.</span></span>

#### <a name="bom-level-display"></a><span data-ttu-id="a7d44-147">Presentación a nivel de L.MAT</span><span class="sxs-lookup"><span data-stu-id="a7d44-147">BOM-level display</span></span>

<span data-ttu-id="a7d44-148">Los niveles la lista de materiales (L.MAT) se muestran de forma distinta para la cobertura de la planificación, los retrasos, las acciones y la puesta en firme.</span><span class="sxs-lookup"><span data-stu-id="a7d44-148">Bill of materials (BOM) levels are shown differently for coverage planning, delays, actions, and firming.</span></span>

- <span data-ttu-id="a7d44-149">**Planificación de cobertura**: los niveles de L.MAT se muestran como esperado.</span><span class="sxs-lookup"><span data-stu-id="a7d44-149">**Coverage planning** – BOM levels are shown as expected.</span></span> <span data-ttu-id="a7d44-150">Se calculan de arriba hacia abajo.</span><span class="sxs-lookup"><span data-stu-id="a7d44-150">They are calculated from the top down.</span></span>

    <span data-ttu-id="a7d44-151">**Ejemplo**: nivel 0, 1, 2 de la L.MAT</span><span class="sxs-lookup"><span data-stu-id="a7d44-151">**Example:** BOM level 0, 1, 2</span></span>

- <span data-ttu-id="a7d44-152">**Retrasos**: los niveles de L.MAT se muestran como los niveles de planificación de L.MAT multiplicados por –1.</span><span class="sxs-lookup"><span data-stu-id="a7d44-152">**Delays** – BOM levels are shown as the coverage planning BOM levels multiplied by –1.</span></span> <span data-ttu-id="a7d44-153">Es decir (tienen un signo negativo).</span><span class="sxs-lookup"><span data-stu-id="a7d44-153">(In other words, they have a negative sign.)</span></span>

    <span data-ttu-id="a7d44-154">**Ejemplo**: nivel –2, –1, 0 de la L.MAT</span><span class="sxs-lookup"><span data-stu-id="a7d44-154">**Example:** BOM level –2, –1, 0</span></span>

- <span data-ttu-id="a7d44-155">**Mensaje de acción**: los niveles de L.MAT se muestran como esperado.</span><span class="sxs-lookup"><span data-stu-id="a7d44-155">**Action message** – BOM levels are shown as expected.</span></span> <span data-ttu-id="a7d44-156">Se calculan de arriba hacia abajo.</span><span class="sxs-lookup"><span data-stu-id="a7d44-156">They are calculated from the top down.</span></span>

    <span data-ttu-id="a7d44-157">**Ejemplo**: nivel 0, 1, 2 de la L.MAT</span><span class="sxs-lookup"><span data-stu-id="a7d44-157">**Example:** BOM level 0, 1, 2</span></span>

- <span data-ttu-id="a7d44-158">**Puesta en firme automática**: los niveles de L.MAT aparecen como 999 menos el nivel de L.MAT de planificación de cobertura.</span><span class="sxs-lookup"><span data-stu-id="a7d44-158">**Auto-firming** – BOM levels are shown as 999 minus the coverage planning BOM level.</span></span>

    <span data-ttu-id="a7d44-159">**Ejemplo**: nivel 999, 998, 997 de la L.MAT</span><span class="sxs-lookup"><span data-stu-id="a7d44-159">**Example:** BOM level 999, 998, 997</span></span>

<span data-ttu-id="a7d44-160">En la tabla siguiente se resume el comportamiento.</span><span class="sxs-lookup"><span data-stu-id="a7d44-160">The following table summarizes the behavior.</span></span>

| <span data-ttu-id="a7d44-161">Nivel de L.MAT que se muestra</span><span class="sxs-lookup"><span data-stu-id="a7d44-161">BOM level that is shown</span></span> | <span data-ttu-id="a7d44-162">Artículo final</span><span class="sxs-lookup"><span data-stu-id="a7d44-162">End item</span></span> | <span data-ttu-id="a7d44-163">Subcomponente</span><span class="sxs-lookup"><span data-stu-id="a7d44-163">Subcomponent</span></span> | <span data-ttu-id="a7d44-164">Materia prima</span><span class="sxs-lookup"><span data-stu-id="a7d44-164">Raw material</span></span> |
|---|---|---|---|
| <span data-ttu-id="a7d44-165">Planificación de la cobertura</span><span class="sxs-lookup"><span data-stu-id="a7d44-165">Coverage planning</span></span> | <span data-ttu-id="a7d44-166">0</span><span class="sxs-lookup"><span data-stu-id="a7d44-166">0</span></span> | <span data-ttu-id="a7d44-167">1</span><span class="sxs-lookup"><span data-stu-id="a7d44-167">1</span></span> | <span data-ttu-id="a7d44-168">2</span><span class="sxs-lookup"><span data-stu-id="a7d44-168">2</span></span> |
| <span data-ttu-id="a7d44-169">Retrasos</span><span class="sxs-lookup"><span data-stu-id="a7d44-169">Delays</span></span> | <span data-ttu-id="a7d44-170">0</span><span class="sxs-lookup"><span data-stu-id="a7d44-170">0</span></span> | <span data-ttu-id="a7d44-171">–1</span><span class="sxs-lookup"><span data-stu-id="a7d44-171">–1</span></span> | <span data-ttu-id="a7d44-172">–2</span><span class="sxs-lookup"><span data-stu-id="a7d44-172">–2</span></span> |
| <span data-ttu-id="a7d44-173">Mensaje de acción</span><span class="sxs-lookup"><span data-stu-id="a7d44-173">Action message</span></span> | <span data-ttu-id="a7d44-174">0</span><span class="sxs-lookup"><span data-stu-id="a7d44-174">0</span></span> | <span data-ttu-id="a7d44-175">1</span><span class="sxs-lookup"><span data-stu-id="a7d44-175">1</span></span> | <span data-ttu-id="a7d44-176">2</span><span class="sxs-lookup"><span data-stu-id="a7d44-176">2</span></span> |
| <span data-ttu-id="a7d44-177">Puesta en firme automática</span><span class="sxs-lookup"><span data-stu-id="a7d44-177">Auto-firming</span></span> | <span data-ttu-id="a7d44-178">999</span><span class="sxs-lookup"><span data-stu-id="a7d44-178">999</span></span> | <span data-ttu-id="a7d44-179">998</span><span class="sxs-lookup"><span data-stu-id="a7d44-179">998</span></span> | <span data-ttu-id="a7d44-180">997</span><span class="sxs-lookup"><span data-stu-id="a7d44-180">997</span></span> |

#### <a name="visualize-progress"></a><span data-ttu-id="a7d44-181">Visualizar el progreso</span><span class="sxs-lookup"><span data-stu-id="a7d44-181">Visualize progress</span></span>

<span data-ttu-id="a7d44-182">Si ve un trabajo de planificación maestra que se esté ejecutando actualmente, el progreso se muestra con colores en el gráfico de Gantt.</span><span class="sxs-lookup"><span data-stu-id="a7d44-182">If you view a master planning job that is currently running, progress is shown through colors in the Gantt chart.</span></span> <span data-ttu-id="a7d44-183">Se aplican los siguientes colores al tema azul.</span><span class="sxs-lookup"><span data-stu-id="a7d44-183">The following colors apply to the blue theme.</span></span> <span data-ttu-id="a7d44-184">Para otros temas de color, los colores serán diferentes.</span><span class="sxs-lookup"><span data-stu-id="a7d44-184">For other color themes, the colors will differ.</span></span>

- <span data-ttu-id="a7d44-185">**Azul oscuro**: tareas de planificación completadas.</span><span class="sxs-lookup"><span data-stu-id="a7d44-185">**Dark blue** – Completed planning tasks.</span></span>
- <span data-ttu-id="a7d44-186">**Naranja**: la tarea está actualmente en curso.</span><span class="sxs-lookup"><span data-stu-id="a7d44-186">**Orange** – The task that is currently in progress.</span></span>
- <span data-ttu-id="a7d44-187">**Azul claro**: la previsión de tareas restantes.</span><span class="sxs-lookup"><span data-stu-id="a7d44-187">**Light blue** – The estimate for remaining tasks.</span></span>

<span data-ttu-id="a7d44-188">El color solo se muestra en el nivel más bajo en el gráfico de Gantt.</span><span class="sxs-lookup"><span data-stu-id="a7d44-188">The color is shown only on the lowest level in the Gantt chart.</span></span> <span data-ttu-id="a7d44-189">Seleccione **Ampliar todo** para ver todas las tareas en el trabajo de la planificación maestra.</span><span class="sxs-lookup"><span data-stu-id="a7d44-189">Select **Expand all** to view all tasks in the master planning job.</span></span> <span data-ttu-id="a7d44-190">La estimación de tareas restantes se basa en trabajos históricos de planificación maestra.</span><span class="sxs-lookup"><span data-stu-id="a7d44-190">The estimate of remaining tasks is based on historical master planning jobs.</span></span>

## <a name="run-master-planning-and-track-processing-time"></a><span data-ttu-id="a7d44-191">Ejecutar planificación maestra y hacer un seguimiento del tiempo de procesamiento</span><span class="sxs-lookup"><span data-stu-id="a7d44-191">Run master planning and track processing time</span></span>

1. <span data-ttu-id="a7d44-192">En el panel predeterminado, seleccione **Planificación maestra**.</span><span class="sxs-lookup"><span data-stu-id="a7d44-192">On the default dashboard, select **Master planning**.</span></span>
1. <span data-ttu-id="a7d44-193">En el campo **Plan**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="a7d44-193">In the **Plan** field, enter or select a value.</span></span>
1. <span data-ttu-id="a7d44-194">Seleccione **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="a7d44-194">Select **Run**.</span></span>
1. <span data-ttu-id="a7d44-195">Establezca la opción **Realizar seguimiento del tiempo de procesamiento** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="a7d44-195">Set the **Track processing time** option to **Yes**.</span></span>
1. <span data-ttu-id="a7d44-196">En el campo **Número de subprocesos**, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="a7d44-196">In the **Number of threads** field, enter a number.</span></span>
1. <span data-ttu-id="a7d44-197">En la ficha desplegable **Registros a incluir**, seleccione **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="a7d44-197">On the **Records to include** FastTab, select **Filter**.</span></span>
1. <span data-ttu-id="a7d44-198">En la cuadrícula, seleccione la fila donde el campo **Campo** está establecido en **Número de artículo**.</span><span class="sxs-lookup"><span data-stu-id="a7d44-198">In the grid, select the row where the **Field** field is set to **Item number**.</span></span>
1. <span data-ttu-id="a7d44-199">En el campo **Criterios**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="a7d44-199">In the **Criteria** field, enter a value.</span></span>
1. <span data-ttu-id="a7d44-200">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a7d44-200">Select **OK**.</span></span>
