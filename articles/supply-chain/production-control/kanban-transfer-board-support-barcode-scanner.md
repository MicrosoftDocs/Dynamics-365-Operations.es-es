---
title: "Compatibilidad del tablero de transferencia kanban para escáneres de códigos de barras"
description: "El tablero de transferencia kanban admite la entrada del escáner desde un lector de códigos de barras de widget para seleccionar, iniciar, completar y vaciar un trabajo kanban."
author: ChristianRytt
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: KanbanBoardTransferJob
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 19391
ms.assetid: a426f645-d59b-4c98-8d78-eba8d64a562e
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 0696580dcf50139639dace641169d041021cf1b8
ms.contentlocale: es-es
ms.lasthandoff: 04/13/2018

---

# <a name="kanban-transfer-board-support-for-barcode-scanners"></a><span data-ttu-id="aaebf-103">Compatibilidad del tablero de transferencia kanban para escáneres de códigos de barras</span><span class="sxs-lookup"><span data-stu-id="aaebf-103">Kanban transfer board support for barcode scanners</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="aaebf-104">El tablero de transferencia kanban admite la entrada del escáner desde un lector de códigos de barras de widget para seleccionar, iniciar, completar y vaciar un trabajo kanban.</span><span class="sxs-lookup"><span data-stu-id="aaebf-104">The Kanban transfer board supports scanner input from a widget barcode scanner to Select, Start, Complete, and Empty a kanban job.</span></span>

<a name="registration-modes"></a><span data-ttu-id="aaebf-105">Modos de registro</span><span class="sxs-lookup"><span data-stu-id="aaebf-105">Registration modes</span></span>
------------------

<span data-ttu-id="aaebf-106">En la ficha desplegable **Registro de escáner**, puede seleccionar el modo de registro, que controla la acción cuando se escanea un número de tarjeta kanban o se escribe manualmente el número en el campo de número de tarjeta kanban.</span><span class="sxs-lookup"><span data-stu-id="aaebf-106">On the **Scanner registration** FastTab you can select the registration mode, which controls the action when you scan a kanban card number or manually type the number in the Kanban card number field.</span></span>

| <span data-ttu-id="aaebf-107">Establecer modo de registro</span><span class="sxs-lookup"><span data-stu-id="aaebf-107">Set registration mode</span></span> | <span data-ttu-id="aaebf-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="aaebf-108">Description</span></span>                                                                                     |
|-----------------------|-------------------------------------------------------------------------------------------------|
| <span data-ttu-id="aaebf-109">Iniciar</span><span class="sxs-lookup"><span data-stu-id="aaebf-109">Start</span></span>                 | <span data-ttu-id="aaebf-110">Registra un trabajo de transferencia kanban como en curso.</span><span class="sxs-lookup"><span data-stu-id="aaebf-110">Registers a Kanban transfer job as in progress.</span></span>                                                 |
| <span data-ttu-id="aaebf-111">Completada</span><span class="sxs-lookup"><span data-stu-id="aaebf-111">Complete</span></span>              | <span data-ttu-id="aaebf-112">Registra un trabajo de transferencia kanban como completado.</span><span class="sxs-lookup"><span data-stu-id="aaebf-112">Registers a Kanban transfer job as completed.</span></span>                                                   |
| <span data-ttu-id="aaebf-113">Vacía</span><span class="sxs-lookup"><span data-stu-id="aaebf-113">Empty</span></span>                 | <span data-ttu-id="aaebf-114">Registra la unidad de gestión de material a la que hace referencia una tarjeta kanban como vacía.</span><span class="sxs-lookup"><span data-stu-id="aaebf-114">Registers the material handling unit that is referenced by a Kanban card as empty.</span></span>              |
| <span data-ttu-id="aaebf-115">Seleccionar</span><span class="sxs-lookup"><span data-stu-id="aaebf-115">Select</span></span>                | <span data-ttu-id="aaebf-116">Registra un número de tarjeta kanban y selecciona automáticamente el trabajo al que se hace referencia en la lista de trabajos kanban.</span><span class="sxs-lookup"><span data-stu-id="aaebf-116">Registers a Kanban card number and automatically selects the referenced job in the Kanban list.</span></span> |

 
<a name="registration-mode-select"></a><span data-ttu-id="aaebf-117">Seleccionar el modo de registro</span><span class="sxs-lookup"><span data-stu-id="aaebf-117">Registration mode Select</span></span>
------------------------

<span data-ttu-id="aaebf-118">Cuando se usa un lector de códigos de barras para seleccionar un trabajo, el modo de visualización del tablero kanban cambia.</span><span class="sxs-lookup"><span data-stu-id="aaebf-118">When you use a bar code reader to select a job, the display mode of the kanban board changes.</span></span> <span data-ttu-id="aaebf-119">De esta manera, se aplicarán las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="aaebf-119">In this mode, the following conditions apply:</span></span>

-   <span data-ttu-id="aaebf-120">Solo se muestra el trabajo kanban escaneado.</span><span class="sxs-lookup"><span data-stu-id="aaebf-120">Only the scanned kanban job is displayed.</span></span>
-   <span data-ttu-id="aaebf-121">Los detalles del trabajo seleccionado se muestran en la ficha desplegable **Detalles**.</span><span class="sxs-lookup"><span data-stu-id="aaebf-121">The details of the selected job are displayed in the **Details** FastTab.</span></span>
-   <span data-ttu-id="aaebf-122">La ficha desplegable **Mensajes** muestra mensajes solo para el trabajo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="aaebf-122">The **Messages** FastTab displays messages only for the selected job.</span></span>
-   <span data-ttu-id="aaebf-123">Puede cambiar el estado del trabajo mediante las funciones disponibles en el Panel de acciones.</span><span class="sxs-lookup"><span data-stu-id="aaebf-123">You can change the status of the job by using the functions that are available on the Action Pane.</span></span> <span data-ttu-id="aaebf-124">El tablero kanban de transferencia sigue mostrando un solo trabajo durante este tiempo.</span><span class="sxs-lookup"><span data-stu-id="aaebf-124">The Kanban transfer board continues to display only a single job during this time.</span></span>
-   <span data-ttu-id="aaebf-125">Puede actualizar la información de la lista de trabajos manualmente haciendo clic en **Actualizar** (Mayús+F5) en el Panel de acciones.</span><span class="sxs-lookup"><span data-stu-id="aaebf-125">You can update the information in the list of jobs manually by clicking **Refresh** (Shift+F5) on the Action Pane.</span></span> <span data-ttu-id="aaebf-126">Tras actualizar la información, los resultados completos del filtro de trabajo se muestran de nuevo.</span><span class="sxs-lookup"><span data-stu-id="aaebf-126">After you refresh the information, the full results for the job filter are displayed again.</span></span>

## <a name="job-status-and-possible-actions"></a><span data-ttu-id="aaebf-127">Estado del trabajo y acciones posibles</span><span class="sxs-lookup"><span data-stu-id="aaebf-127">Job status and possible actions</span></span>
<span data-ttu-id="aaebf-128">El estado del trabajo seleccionado y el estado de cualquier trabajo fijado para los kanban de evento determinan si puede seguir procesando el trabajo.</span><span class="sxs-lookup"><span data-stu-id="aaebf-128">The status of the selected job and the status of any pegged jobs for event kanbans, determine whether you can process the job further.</span></span> <span data-ttu-id="aaebf-129">La tabla siguiente muestra información acerca de estos estados y tareas:</span><span class="sxs-lookup"><span data-stu-id="aaebf-129">The following table displays information about these statuses and tasks:</span></span>
-   <span data-ttu-id="aaebf-130">Los estados disponibles para los trabajos o para las unidades de gestión de material a los que hacen referencia los trabajos.</span><span class="sxs-lookup"><span data-stu-id="aaebf-130">The statuses that are available for jobs, or for the handling units that are referenced by the jobs.</span></span>
-   <span data-ttu-id="aaebf-131">Todas las tareas que puede realizar para el trabajo.</span><span class="sxs-lookup"><span data-stu-id="aaebf-131">Each task that you can perform for the job.</span></span>

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
<th><span data-ttu-id="aaebf-132">Tipo de trabajo</span><span class="sxs-lookup"><span data-stu-id="aaebf-132">Job type</span></span></th>
<th><span data-ttu-id="aaebf-133">El estado del trabajo o el estado de la unidad de gestión de material</span><span class="sxs-lookup"><span data-stu-id="aaebf-133">Job status or handling unit status</span></span></th>
<th><span data-ttu-id="aaebf-134">Actualizar lista de selección</span><span class="sxs-lookup"><span data-stu-id="aaebf-134">Update picking list</span></span></th>
<th><span data-ttu-id="aaebf-135">Iniciar</span><span class="sxs-lookup"><span data-stu-id="aaebf-135">Start</span></span></th>
<th><span data-ttu-id="aaebf-136">Actualizar registro</span><span class="sxs-lookup"><span data-stu-id="aaebf-136">Update registration</span></span></th>
<th><span data-ttu-id="aaebf-137">Completada</span><span class="sxs-lookup"><span data-stu-id="aaebf-137">Complete</span></span></th>
<th><span data-ttu-id="aaebf-138">Vacía</span><span class="sxs-lookup"><span data-stu-id="aaebf-138">Empty</span></span></th>
<th><span data-ttu-id="aaebf-139">Crear kanbans de evento</span><span class="sxs-lookup"><span data-stu-id="aaebf-139">Create event kanbans</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="aaebf-140">Transferir</span><span class="sxs-lookup"><span data-stu-id="aaebf-140">Transfer</span></span></td>
<td><ul>
<li><span data-ttu-id="aaebf-141">Sin planificar</span><span class="sxs-lookup"><span data-stu-id="aaebf-141">Not planned</span></span></li>
<li><span data-ttu-id="aaebf-142">No hay trabajos fijados o estos están completados</span><span class="sxs-lookup"><span data-stu-id="aaebf-142">No pegged jobs, or pegged jobs are Completed</span></span></li>
</ul></td>
<td><span data-ttu-id="aaebf-143">Sí</span><span class="sxs-lookup"><span data-stu-id="aaebf-143">Yes</span></span></td>
<td><span data-ttu-id="aaebf-144">Sí</span><span class="sxs-lookup"><span data-stu-id="aaebf-144">Yes</span></span></td>
<td><span data-ttu-id="aaebf-145">Sí</span><span class="sxs-lookup"><span data-stu-id="aaebf-145">Yes</span></span></td>
<td><span data-ttu-id="aaebf-146">Sí</span><span class="sxs-lookup"><span data-stu-id="aaebf-146">Yes</span></span></td>
<td><span data-ttu-id="aaebf-147">No</span><span class="sxs-lookup"><span data-stu-id="aaebf-147">No</span></span></td>
<td><span data-ttu-id="aaebf-148">Sí</span><span class="sxs-lookup"><span data-stu-id="aaebf-148">Yes</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="aaebf-149">Transferir</span><span class="sxs-lookup"><span data-stu-id="aaebf-149">Transfer</span></span></td>
<td><ul>
<li><span data-ttu-id="aaebf-150">Sin planificar</span><span class="sxs-lookup"><span data-stu-id="aaebf-150">Not planned</span></span></li>
<li><span data-ttu-id="aaebf-151">El trabajo fijado no está completado</span><span class="sxs-lookup"><span data-stu-id="aaebf-151">The pegged job is not Completed</span></span></li>
</ul></td>
<td><span data-ttu-id="aaebf-152">Sí</span><span class="sxs-lookup"><span data-stu-id="aaebf-152">Yes</span></span></td>
<td><span data-ttu-id="aaebf-153">No</span><span class="sxs-lookup"><span data-stu-id="aaebf-153">No</span></span></td>
<td><span data-ttu-id="aaebf-154">Sí</span><span class="sxs-lookup"><span data-stu-id="aaebf-154">Yes</span></span></td>
<td><span data-ttu-id="aaebf-155">No</span><span class="sxs-lookup"><span data-stu-id="aaebf-155">No</span></span></td>
<td><span data-ttu-id="aaebf-156">No</span><span class="sxs-lookup"><span data-stu-id="aaebf-156">No</span></span></td>
<td><span data-ttu-id="aaebf-157">No</span><span class="sxs-lookup"><span data-stu-id="aaebf-157">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="aaebf-158">Transferir</span><span class="sxs-lookup"><span data-stu-id="aaebf-158">Transfer</span></span></td>
<td><span data-ttu-id="aaebf-159">En curso</span><span class="sxs-lookup"><span data-stu-id="aaebf-159">In progress</span></span></td>
<td><span data-ttu-id="aaebf-160">Sí</span><span class="sxs-lookup"><span data-stu-id="aaebf-160">Yes</span></span></td>
<td><span data-ttu-id="aaebf-161">No</span><span class="sxs-lookup"><span data-stu-id="aaebf-161">No</span></span></td>
<td><span data-ttu-id="aaebf-162">Sí</span><span class="sxs-lookup"><span data-stu-id="aaebf-162">Yes</span></span></td>
<td><span data-ttu-id="aaebf-163">Sí</span><span class="sxs-lookup"><span data-stu-id="aaebf-163">Yes</span></span></td>
<td><span data-ttu-id="aaebf-164">No</span><span class="sxs-lookup"><span data-stu-id="aaebf-164">No</span></span></td>
<td><span data-ttu-id="aaebf-165">No</span><span class="sxs-lookup"><span data-stu-id="aaebf-165">No</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="aaebf-166">Transferir</span><span class="sxs-lookup"><span data-stu-id="aaebf-166">Transfer</span></span></td>
<td><span data-ttu-id="aaebf-167">Completada</span><span class="sxs-lookup"><span data-stu-id="aaebf-167">Completed</span></span></td>
<td><span data-ttu-id="aaebf-168">No</span><span class="sxs-lookup"><span data-stu-id="aaebf-168">No</span></span></td>
<td><span data-ttu-id="aaebf-169">No</span><span class="sxs-lookup"><span data-stu-id="aaebf-169">No</span></span></td>
<td><span data-ttu-id="aaebf-170">No</span><span class="sxs-lookup"><span data-stu-id="aaebf-170">No</span></span></td>
<td><span data-ttu-id="aaebf-171">No</span><span class="sxs-lookup"><span data-stu-id="aaebf-171">No</span></span></td>
<td><span data-ttu-id="aaebf-172">Sí</span><span class="sxs-lookup"><span data-stu-id="aaebf-172">Yes</span></span></td>
<td><span data-ttu-id="aaebf-173">No</span><span class="sxs-lookup"><span data-stu-id="aaebf-173">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="aaebf-174">Transferir o procesar</span><span class="sxs-lookup"><span data-stu-id="aaebf-174">Transfer or process</span></span></td>
<td><span data-ttu-id="aaebf-175">Vacía</span><span class="sxs-lookup"><span data-stu-id="aaebf-175">Empty</span></span></td>
<td><span data-ttu-id="aaebf-176">No</span><span class="sxs-lookup"><span data-stu-id="aaebf-176">No</span></span></td>
<td><span data-ttu-id="aaebf-177">No</span><span class="sxs-lookup"><span data-stu-id="aaebf-177">No</span></span></td>
<td><span data-ttu-id="aaebf-178">No</span><span class="sxs-lookup"><span data-stu-id="aaebf-178">No</span></span></td>
<td><span data-ttu-id="aaebf-179">No</span><span class="sxs-lookup"><span data-stu-id="aaebf-179">No</span></span></td>
<td><span data-ttu-id="aaebf-180">No</span><span class="sxs-lookup"><span data-stu-id="aaebf-180">No</span></span></td>
<td><span data-ttu-id="aaebf-181">No</span><span class="sxs-lookup"><span data-stu-id="aaebf-181">No</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="aaebf-182">Transferir o procesar</span><span class="sxs-lookup"><span data-stu-id="aaebf-182">Transfer or process</span></span></td>
<td><span data-ttu-id="aaebf-183">No se encuentra una tarjeta kanban</span><span class="sxs-lookup"><span data-stu-id="aaebf-183">A kanban card is not found</span></span></td>
<td><span data-ttu-id="aaebf-184">Nº</span><span class="sxs-lookup"><span data-stu-id="aaebf-184">No</span></span></td>
<td><span data-ttu-id="aaebf-185">Nº</span><span class="sxs-lookup"><span data-stu-id="aaebf-185">No</span></span></td>
<td><span data-ttu-id="aaebf-186">Nº</span><span class="sxs-lookup"><span data-stu-id="aaebf-186">No</span></span></td>
<td><span data-ttu-id="aaebf-187">Nº</span><span class="sxs-lookup"><span data-stu-id="aaebf-187">No</span></span></td>
<td><span data-ttu-id="aaebf-188">Nº</span><span class="sxs-lookup"><span data-stu-id="aaebf-188">No</span></span></td>
<td><span data-ttu-id="aaebf-189">Nº</span><span class="sxs-lookup"><span data-stu-id="aaebf-189">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="aaebf-190">Transferir o procesar</span><span class="sxs-lookup"><span data-stu-id="aaebf-190">Transfer or process</span></span></td>
<td><span data-ttu-id="aaebf-191">Se encuentra una tarjeta kanban, pero no está asignada a un kanban</span><span class="sxs-lookup"><span data-stu-id="aaebf-191">A kanban card is found, but it is not assigned to a kanban</span></span></td>
<td><span data-ttu-id="aaebf-192">No</span><span class="sxs-lookup"><span data-stu-id="aaebf-192">No</span></span></td>
<td><span data-ttu-id="aaebf-193">No</span><span class="sxs-lookup"><span data-stu-id="aaebf-193">No</span></span></td>
<td><span data-ttu-id="aaebf-194">No</span><span class="sxs-lookup"><span data-stu-id="aaebf-194">No</span></span></td>
<td><span data-ttu-id="aaebf-195">No</span><span class="sxs-lookup"><span data-stu-id="aaebf-195">No</span></span></td>
<td><span data-ttu-id="aaebf-196">No</span><span class="sxs-lookup"><span data-stu-id="aaebf-196">No</span></span></td>
<td><span data-ttu-id="aaebf-197">No</span><span class="sxs-lookup"><span data-stu-id="aaebf-197">No</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="aaebf-198">Procesar</span><span class="sxs-lookup"><span data-stu-id="aaebf-198">Process</span></span></td>
<td><ul>
<li><span data-ttu-id="aaebf-199">Sin planificar</span><span class="sxs-lookup"><span data-stu-id="aaebf-199">Not planned</span></span></li>
<li><span data-ttu-id="aaebf-200">Preparado</span><span class="sxs-lookup"><span data-stu-id="aaebf-200">Prepared</span></span></li>
<li><span data-ttu-id="aaebf-201">En curso</span><span class="sxs-lookup"><span data-stu-id="aaebf-201">In progress</span></span></li>
</ul></td>
<td><span data-ttu-id="aaebf-202">No</span><span class="sxs-lookup"><span data-stu-id="aaebf-202">No</span></span></td>
<td><span data-ttu-id="aaebf-203">No</span><span class="sxs-lookup"><span data-stu-id="aaebf-203">No</span></span></td>
<td><span data-ttu-id="aaebf-204">No</span><span class="sxs-lookup"><span data-stu-id="aaebf-204">No</span></span></td>
<td><span data-ttu-id="aaebf-205">No</span><span class="sxs-lookup"><span data-stu-id="aaebf-205">No</span></span></td>
<td><span data-ttu-id="aaebf-206">No</span><span class="sxs-lookup"><span data-stu-id="aaebf-206">No</span></span></td>
<td><span data-ttu-id="aaebf-207">No</span><span class="sxs-lookup"><span data-stu-id="aaebf-207">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="aaebf-208">Procesar</span><span class="sxs-lookup"><span data-stu-id="aaebf-208">Process</span></span></td>
<td><span data-ttu-id="aaebf-209">Completada</span><span class="sxs-lookup"><span data-stu-id="aaebf-209">Completed</span></span></td>
<td><span data-ttu-id="aaebf-210">No</span><span class="sxs-lookup"><span data-stu-id="aaebf-210">No</span></span></td>
<td><span data-ttu-id="aaebf-211">No</span><span class="sxs-lookup"><span data-stu-id="aaebf-211">No</span></span></td>
<td><span data-ttu-id="aaebf-212">No</span><span class="sxs-lookup"><span data-stu-id="aaebf-212">No</span></span></td>
<td><span data-ttu-id="aaebf-213">No</span><span class="sxs-lookup"><span data-stu-id="aaebf-213">No</span></span></td>
<td><span data-ttu-id="aaebf-214">No</span><span class="sxs-lookup"><span data-stu-id="aaebf-214">No</span></span></td>
<td><span data-ttu-id="aaebf-215">No</span><span class="sxs-lookup"><span data-stu-id="aaebf-215">No</span></span></td>
</tr>
</tbody>
</table>






