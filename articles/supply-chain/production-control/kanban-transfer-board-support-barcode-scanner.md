---
title: Compatibilidad del tablero de transferencia kanban para escáneres de códigos de barras
description: El tablero de transferencia kanban admite la entrada del escáner desde un lector de códigos de barras de widget para seleccionar, iniciar, completar y vaciar un trabajo kanban.
author: ChristianRytt
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanBoardTransferJob
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 19391
ms.assetid: a426f645-d59b-4c98-8d78-eba8d64a562e
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e63a33af63144b78d0c375022b9802e11c255598
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1569226"
---
# <a name="kanban-transfer-board-support-for-barcode-scanners"></a><span data-ttu-id="c50b6-103">Compatibilidad del tablero de transferencia kanban para escáneres de códigos de barras</span><span class="sxs-lookup"><span data-stu-id="c50b6-103">Kanban transfer board support for barcode scanners</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c50b6-104">El tablero de transferencia kanban admite la entrada del escáner desde un lector de códigos de barras de widget para seleccionar, iniciar, completar y vaciar un trabajo kanban.</span><span class="sxs-lookup"><span data-stu-id="c50b6-104">The Kanban transfer board supports scanner input from a widget barcode scanner to Select, Start, Complete, and Empty a kanban job.</span></span>

<a name="registration-modes"></a><span data-ttu-id="c50b6-105">Modos de registro</span><span class="sxs-lookup"><span data-stu-id="c50b6-105">Registration modes</span></span>
------------------

<span data-ttu-id="c50b6-106">En la ficha desplegable **Registro de escáner**, puede seleccionar el modo de registro, que controla la acción cuando se escanea un número de tarjeta kanban o se escribe manualmente el número en el campo de número de tarjeta kanban.</span><span class="sxs-lookup"><span data-stu-id="c50b6-106">On the **Scanner registration** FastTab you can select the registration mode, which controls the action when you scan a kanban card number or manually type the number in the Kanban card number field.</span></span>

| <span data-ttu-id="c50b6-107">Establecer modo de registro</span><span class="sxs-lookup"><span data-stu-id="c50b6-107">Set registration mode</span></span> | <span data-ttu-id="c50b6-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="c50b6-108">Description</span></span>                                                                                     |
|-----------------------|-------------------------------------------------------------------------------------------------|
| <span data-ttu-id="c50b6-109">Iniciar</span><span class="sxs-lookup"><span data-stu-id="c50b6-109">Start</span></span>                 | <span data-ttu-id="c50b6-110">Registra un trabajo de transferencia kanban como en curso.</span><span class="sxs-lookup"><span data-stu-id="c50b6-110">Registers a Kanban transfer job as in progress.</span></span>                                                 |
| <span data-ttu-id="c50b6-111">Completada</span><span class="sxs-lookup"><span data-stu-id="c50b6-111">Complete</span></span>              | <span data-ttu-id="c50b6-112">Registra un trabajo de transferencia kanban como completado.</span><span class="sxs-lookup"><span data-stu-id="c50b6-112">Registers a Kanban transfer job as completed.</span></span>                                                   |
| <span data-ttu-id="c50b6-113">Vacía</span><span class="sxs-lookup"><span data-stu-id="c50b6-113">Empty</span></span>                 | <span data-ttu-id="c50b6-114">Registra la unidad de gestión de material a la que hace referencia una tarjeta kanban como vacía.</span><span class="sxs-lookup"><span data-stu-id="c50b6-114">Registers the material handling unit that is referenced by a Kanban card as empty.</span></span>              |
| <span data-ttu-id="c50b6-115">Seleccionar</span><span class="sxs-lookup"><span data-stu-id="c50b6-115">Select</span></span>                | <span data-ttu-id="c50b6-116">Registra un número de tarjeta kanban y selecciona automáticamente el trabajo al que se hace referencia en la lista de trabajos kanban.</span><span class="sxs-lookup"><span data-stu-id="c50b6-116">Registers a Kanban card number and automatically selects the referenced job in the Kanban list.</span></span> |

 
<span data-ttu-id="c50b6-117">Seleccionar el modo de registro</span><span class="sxs-lookup"><span data-stu-id="c50b6-117">Registration mode Select</span></span>
------------------------

<span data-ttu-id="c50b6-118">Cuando se usa un lector de códigos de barras para seleccionar un trabajo, el modo de visualización del tablero kanban cambia.</span><span class="sxs-lookup"><span data-stu-id="c50b6-118">When you use a bar code reader to select a job, the display mode of the kanban board changes.</span></span><span data-ttu-id="c50b6-119">De esta manera, se aplicarán las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="c50b6-119"> In this mode, the following conditions apply:</span></span>

-   <span data-ttu-id="c50b6-120">Solo se muestra el trabajo kanban escaneado.</span><span class="sxs-lookup"><span data-stu-id="c50b6-120">Only the scanned kanban job is displayed.</span></span>
-   <span data-ttu-id="c50b6-121">Los detalles del trabajo seleccionado se muestran en la ficha desplegable **Detalles**.</span><span class="sxs-lookup"><span data-stu-id="c50b6-121">The details of the selected job are displayed in the **Details** FastTab.</span></span>
-   <span data-ttu-id="c50b6-122">La ficha desplegable **Mensajes** muestra mensajes solo para el trabajo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="c50b6-122">The **Messages** FastTab displays messages only for the selected job.</span></span>
-   <span data-ttu-id="c50b6-123">Puede cambiar el estado del trabajo mediante las funciones disponibles en el Panel de acciones.</span><span class="sxs-lookup"><span data-stu-id="c50b6-123">You can change the status of the job by using the functions that are available on the Action Pane.</span></span> <span data-ttu-id="c50b6-124">El tablero kanban de transferencia sigue mostrando un solo trabajo durante este tiempo.</span><span class="sxs-lookup"><span data-stu-id="c50b6-124">The Kanban transfer board continues to display only a single job during this time.</span></span>
-   <span data-ttu-id="c50b6-125">Puede actualizar la información de la lista de trabajos manualmente haciendo clic en **Actualizar** (Mayús+F5) en el Panel de acciones.</span><span class="sxs-lookup"><span data-stu-id="c50b6-125">You can update the information in the list of jobs manually by clicking **Refresh** (Shift+F5) on the Action Pane.</span></span> <span data-ttu-id="c50b6-126">Tras actualizar la información, los resultados completos del filtro de trabajo se muestran de nuevo.</span><span class="sxs-lookup"><span data-stu-id="c50b6-126">After you refresh the information, the full results for the job filter are displayed again.</span></span>

## <a name="job-status-and-possible-actions"></a><span data-ttu-id="c50b6-127">Estado del trabajo y acciones posibles</span><span class="sxs-lookup"><span data-stu-id="c50b6-127">Job status and possible actions</span></span>
<span data-ttu-id="c50b6-128">El estado del trabajo seleccionado y el estado de cualquier trabajo fijado para los kanban de evento determinan si puede seguir procesando el trabajo.</span><span class="sxs-lookup"><span data-stu-id="c50b6-128">The status of the selected job and the status of any pegged jobs for event kanbans, determine whether you can process the job further.</span></span> <span data-ttu-id="c50b6-129">La tabla siguiente muestra información acerca de estos estados y tareas:</span><span class="sxs-lookup"><span data-stu-id="c50b6-129">The following table displays information about these statuses and tasks:</span></span>
-   <span data-ttu-id="c50b6-130">Los estados disponibles para los trabajos o para las unidades de gestión de material a los que hacen referencia los trabajos.</span><span class="sxs-lookup"><span data-stu-id="c50b6-130">The statuses that are available for jobs, or for the handling units that are referenced by the jobs.</span></span>
-   <span data-ttu-id="c50b6-131">Todas las tareas que puede realizar para el trabajo.</span><span class="sxs-lookup"><span data-stu-id="c50b6-131">Each task that you can perform for the job.</span></span>

<table>
<colgroup>
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c50b6-132">Tipo de trabajo</span><span class="sxs-lookup"><span data-stu-id="c50b6-132">Job type</span></span></th>
<th><span data-ttu-id="c50b6-133">El estado del trabajo o el estado de la unidad de gestión de material</span><span class="sxs-lookup"><span data-stu-id="c50b6-133">Job status or handling unit status</span></span></th>
<th><span data-ttu-id="c50b6-134">Actualizar lista de selección</span><span class="sxs-lookup"><span data-stu-id="c50b6-134">Update picking list</span></span></th>
<th><span data-ttu-id="c50b6-135">Iniciar</span><span class="sxs-lookup"><span data-stu-id="c50b6-135">Start</span></span></th>
<th><span data-ttu-id="c50b6-136">Actualizar registro</span><span class="sxs-lookup"><span data-stu-id="c50b6-136">Update registration</span></span></th>
<th><span data-ttu-id="c50b6-137">Completada</span><span class="sxs-lookup"><span data-stu-id="c50b6-137">Complete</span></span></th>
<th><span data-ttu-id="c50b6-138">Vacía</span><span class="sxs-lookup"><span data-stu-id="c50b6-138">Empty</span></span></th>
<th><span data-ttu-id="c50b6-139">Crear kanbans de evento</span><span class="sxs-lookup"><span data-stu-id="c50b6-139">Create event kanbans</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="c50b6-140">Transferir</span><span class="sxs-lookup"><span data-stu-id="c50b6-140">Transfer</span></span></td>
<td><ul>
<li><span data-ttu-id="c50b6-141">Sin planificar</span><span class="sxs-lookup"><span data-stu-id="c50b6-141">Not planned</span></span></li>
<li><span data-ttu-id="c50b6-142">No hay trabajos fijados o estos están completados</span><span class="sxs-lookup"><span data-stu-id="c50b6-142">No pegged jobs, or pegged jobs are Completed</span></span></li>
</ul></td>
<td><span data-ttu-id="c50b6-143">Sí</span><span class="sxs-lookup"><span data-stu-id="c50b6-143">Yes</span></span></td>
<td><span data-ttu-id="c50b6-144">Sí</span><span class="sxs-lookup"><span data-stu-id="c50b6-144">Yes</span></span></td>
<td><span data-ttu-id="c50b6-145">Sí</span><span class="sxs-lookup"><span data-stu-id="c50b6-145">Yes</span></span></td>
<td><span data-ttu-id="c50b6-146">Sí</span><span class="sxs-lookup"><span data-stu-id="c50b6-146">Yes</span></span></td>
<td><span data-ttu-id="c50b6-147">No</span><span class="sxs-lookup"><span data-stu-id="c50b6-147">No</span></span></td>
<td><span data-ttu-id="c50b6-148">Sí</span><span class="sxs-lookup"><span data-stu-id="c50b6-148">Yes</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="c50b6-149">Transferir</span><span class="sxs-lookup"><span data-stu-id="c50b6-149">Transfer</span></span></td>
<td><ul>
<li><span data-ttu-id="c50b6-150">Sin planificar</span><span class="sxs-lookup"><span data-stu-id="c50b6-150">Not planned</span></span></li>
<li><span data-ttu-id="c50b6-151">El trabajo fijado no está completado</span><span class="sxs-lookup"><span data-stu-id="c50b6-151">The pegged job is not Completed</span></span></li>
</ul></td>
<td><span data-ttu-id="c50b6-152">Sí</span><span class="sxs-lookup"><span data-stu-id="c50b6-152">Yes</span></span></td>
<td><span data-ttu-id="c50b6-153">No</span><span class="sxs-lookup"><span data-stu-id="c50b6-153">No</span></span></td>
<td><span data-ttu-id="c50b6-154">Sí</span><span class="sxs-lookup"><span data-stu-id="c50b6-154">Yes</span></span></td>
<td><span data-ttu-id="c50b6-155">No</span><span class="sxs-lookup"><span data-stu-id="c50b6-155">No</span></span></td>
<td><span data-ttu-id="c50b6-156">No</span><span class="sxs-lookup"><span data-stu-id="c50b6-156">No</span></span></td>
<td><span data-ttu-id="c50b6-157">No</span><span class="sxs-lookup"><span data-stu-id="c50b6-157">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="c50b6-158">Transferir</span><span class="sxs-lookup"><span data-stu-id="c50b6-158">Transfer</span></span></td>
<td><span data-ttu-id="c50b6-159">En curso</span><span class="sxs-lookup"><span data-stu-id="c50b6-159">In progress</span></span></td>
<td><span data-ttu-id="c50b6-160">Sí</span><span class="sxs-lookup"><span data-stu-id="c50b6-160">Yes</span></span></td>
<td><span data-ttu-id="c50b6-161">No</span><span class="sxs-lookup"><span data-stu-id="c50b6-161">No</span></span></td>
<td><span data-ttu-id="c50b6-162">Sí</span><span class="sxs-lookup"><span data-stu-id="c50b6-162">Yes</span></span></td>
<td><span data-ttu-id="c50b6-163">Sí</span><span class="sxs-lookup"><span data-stu-id="c50b6-163">Yes</span></span></td>
<td><span data-ttu-id="c50b6-164">No</span><span class="sxs-lookup"><span data-stu-id="c50b6-164">No</span></span></td>
<td><span data-ttu-id="c50b6-165">No</span><span class="sxs-lookup"><span data-stu-id="c50b6-165">No</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="c50b6-166">Transferir</span><span class="sxs-lookup"><span data-stu-id="c50b6-166">Transfer</span></span></td>
<td><span data-ttu-id="c50b6-167">Completada</span><span class="sxs-lookup"><span data-stu-id="c50b6-167">Completed</span></span></td>
<td><span data-ttu-id="c50b6-168">No</span><span class="sxs-lookup"><span data-stu-id="c50b6-168">No</span></span></td>
<td><span data-ttu-id="c50b6-169">No</span><span class="sxs-lookup"><span data-stu-id="c50b6-169">No</span></span></td>
<td><span data-ttu-id="c50b6-170">No</span><span class="sxs-lookup"><span data-stu-id="c50b6-170">No</span></span></td>
<td><span data-ttu-id="c50b6-171">No</span><span class="sxs-lookup"><span data-stu-id="c50b6-171">No</span></span></td>
<td><span data-ttu-id="c50b6-172">Sí</span><span class="sxs-lookup"><span data-stu-id="c50b6-172">Yes</span></span></td>
<td><span data-ttu-id="c50b6-173">No</span><span class="sxs-lookup"><span data-stu-id="c50b6-173">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="c50b6-174">Transferir o procesar</span><span class="sxs-lookup"><span data-stu-id="c50b6-174">Transfer or process</span></span></td>
<td><span data-ttu-id="c50b6-175">Vacía</span><span class="sxs-lookup"><span data-stu-id="c50b6-175">Empty</span></span></td>
<td><span data-ttu-id="c50b6-176">No</span><span class="sxs-lookup"><span data-stu-id="c50b6-176">No</span></span></td>
<td><span data-ttu-id="c50b6-177">No</span><span class="sxs-lookup"><span data-stu-id="c50b6-177">No</span></span></td>
<td><span data-ttu-id="c50b6-178">No</span><span class="sxs-lookup"><span data-stu-id="c50b6-178">No</span></span></td>
<td><span data-ttu-id="c50b6-179">No</span><span class="sxs-lookup"><span data-stu-id="c50b6-179">No</span></span></td>
<td><span data-ttu-id="c50b6-180">No</span><span class="sxs-lookup"><span data-stu-id="c50b6-180">No</span></span></td>
<td><span data-ttu-id="c50b6-181">No</span><span class="sxs-lookup"><span data-stu-id="c50b6-181">No</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="c50b6-182">Transferir o procesar</span><span class="sxs-lookup"><span data-stu-id="c50b6-182">Transfer or process</span></span></td>
<td><span data-ttu-id="c50b6-183">No se encuentra una tarjeta kanban</span><span class="sxs-lookup"><span data-stu-id="c50b6-183">A kanban card is not found</span></span></td>
<td><span data-ttu-id="c50b6-184">Nº</span><span class="sxs-lookup"><span data-stu-id="c50b6-184">No</span></span></td>
<td><span data-ttu-id="c50b6-185">Nº</span><span class="sxs-lookup"><span data-stu-id="c50b6-185">No</span></span></td>
<td><span data-ttu-id="c50b6-186">Nº</span><span class="sxs-lookup"><span data-stu-id="c50b6-186">No</span></span></td>
<td><span data-ttu-id="c50b6-187">Nº</span><span class="sxs-lookup"><span data-stu-id="c50b6-187">No</span></span></td>
<td><span data-ttu-id="c50b6-188">Nº</span><span class="sxs-lookup"><span data-stu-id="c50b6-188">No</span></span></td>
<td><span data-ttu-id="c50b6-189">Nº</span><span class="sxs-lookup"><span data-stu-id="c50b6-189">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="c50b6-190">Transferir o procesar</span><span class="sxs-lookup"><span data-stu-id="c50b6-190">Transfer or process</span></span></td>
<td><span data-ttu-id="c50b6-191">Se encuentra una tarjeta kanban, pero no está asignada a un kanban</span><span class="sxs-lookup"><span data-stu-id="c50b6-191">A kanban card is found, but it is not assigned to a kanban</span></span></td>
<td><span data-ttu-id="c50b6-192">No</span><span class="sxs-lookup"><span data-stu-id="c50b6-192">No</span></span></td>
<td><span data-ttu-id="c50b6-193">No</span><span class="sxs-lookup"><span data-stu-id="c50b6-193">No</span></span></td>
<td><span data-ttu-id="c50b6-194">No</span><span class="sxs-lookup"><span data-stu-id="c50b6-194">No</span></span></td>
<td><span data-ttu-id="c50b6-195">No</span><span class="sxs-lookup"><span data-stu-id="c50b6-195">No</span></span></td>
<td><span data-ttu-id="c50b6-196">No</span><span class="sxs-lookup"><span data-stu-id="c50b6-196">No</span></span></td>
<td><span data-ttu-id="c50b6-197">No</span><span class="sxs-lookup"><span data-stu-id="c50b6-197">No</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="c50b6-198">Procesar</span><span class="sxs-lookup"><span data-stu-id="c50b6-198">Process</span></span></td>
<td><ul>
<li><span data-ttu-id="c50b6-199">Sin planificar</span><span class="sxs-lookup"><span data-stu-id="c50b6-199">Not planned</span></span></li>
<li><span data-ttu-id="c50b6-200">Preparado</span><span class="sxs-lookup"><span data-stu-id="c50b6-200">Prepared</span></span></li>
<li><span data-ttu-id="c50b6-201">En curso</span><span class="sxs-lookup"><span data-stu-id="c50b6-201">In progress</span></span></li>
</ul></td>
<td><span data-ttu-id="c50b6-202">No</span><span class="sxs-lookup"><span data-stu-id="c50b6-202">No</span></span></td>
<td><span data-ttu-id="c50b6-203">No</span><span class="sxs-lookup"><span data-stu-id="c50b6-203">No</span></span></td>
<td><span data-ttu-id="c50b6-204">No</span><span class="sxs-lookup"><span data-stu-id="c50b6-204">No</span></span></td>
<td><span data-ttu-id="c50b6-205">No</span><span class="sxs-lookup"><span data-stu-id="c50b6-205">No</span></span></td>
<td><span data-ttu-id="c50b6-206">No</span><span class="sxs-lookup"><span data-stu-id="c50b6-206">No</span></span></td>
<td><span data-ttu-id="c50b6-207">No</span><span class="sxs-lookup"><span data-stu-id="c50b6-207">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="c50b6-208">Procesar</span><span class="sxs-lookup"><span data-stu-id="c50b6-208">Process</span></span></td>
<td><span data-ttu-id="c50b6-209">Completada</span><span class="sxs-lookup"><span data-stu-id="c50b6-209">Completed</span></span></td>
<td><span data-ttu-id="c50b6-210">No</span><span class="sxs-lookup"><span data-stu-id="c50b6-210">No</span></span></td>
<td><span data-ttu-id="c50b6-211">No</span><span class="sxs-lookup"><span data-stu-id="c50b6-211">No</span></span></td>
<td><span data-ttu-id="c50b6-212">No</span><span class="sxs-lookup"><span data-stu-id="c50b6-212">No</span></span></td>
<td><span data-ttu-id="c50b6-213">No</span><span class="sxs-lookup"><span data-stu-id="c50b6-213">No</span></span></td>
<td><span data-ttu-id="c50b6-214">No</span><span class="sxs-lookup"><span data-stu-id="c50b6-214">No</span></span></td>
<td><span data-ttu-id="c50b6-215">No</span><span class="sxs-lookup"><span data-stu-id="c50b6-215">No</span></span></td>
</tr>
</tbody>
</table>





