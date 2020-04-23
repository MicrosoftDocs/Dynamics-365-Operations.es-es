---
title: Compatibilidad del tablero de transferencia kanban para escáneres de códigos de barras
description: El tablero de transferencia kanban admite la entrada del escáner desde un lector de códigos de barras de widget para seleccionar, iniciar, completar y vaciar un trabajo kanban.
author: ChristianRytt
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanBoardTransferJob
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 19391
ms.assetid: a426f645-d59b-4c98-8d78-eba8d64a562e
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1bd6f1bdd847f74cee7d3594d19b72454063c0cb
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2020
ms.locfileid: "3207195"
---
# <a name="kanban-transfer-board-support-for-barcode-scanners"></a><span data-ttu-id="21ff7-103">Compatibilidad del tablero de transferencia kanban para escáneres de códigos de barras</span><span class="sxs-lookup"><span data-stu-id="21ff7-103">Kanban transfer board support for barcode scanners</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="21ff7-104">El tablero de transferencia kanban admite la entrada del escáner desde un lector de códigos de barras de widget para seleccionar, iniciar, completar y vaciar un trabajo kanban.</span><span class="sxs-lookup"><span data-stu-id="21ff7-104">The Kanban transfer board supports scanner input from a widget barcode scanner to Select, Start, Complete, and Empty a kanban job.</span></span>

<a name="registration-modes"></a><span data-ttu-id="21ff7-105">Modos de registro</span><span class="sxs-lookup"><span data-stu-id="21ff7-105">Registration modes</span></span>
------------------

<span data-ttu-id="21ff7-106">En la ficha desplegable **Registro de escáner**, puede seleccionar el modo de registro, que controla la acción cuando se escanea un número de tarjeta kanban o se escribe manualmente el número en el campo de número de tarjeta kanban.</span><span class="sxs-lookup"><span data-stu-id="21ff7-106">On the **Scanner registration** FastTab you can select the registration mode, which controls the action when you scan a kanban card number or manually type the number in the Kanban card number field.</span></span>

| <span data-ttu-id="21ff7-107">Establecer modo de registro</span><span class="sxs-lookup"><span data-stu-id="21ff7-107">Set registration mode</span></span> | <span data-ttu-id="21ff7-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="21ff7-108">Description</span></span>                                                                                     |
|-----------------------|-------------------------------------------------------------------------------------------------|
| <span data-ttu-id="21ff7-109">Iniciar</span><span class="sxs-lookup"><span data-stu-id="21ff7-109">Start</span></span>                 | <span data-ttu-id="21ff7-110">Registra un trabajo de transferencia kanban como en curso.</span><span class="sxs-lookup"><span data-stu-id="21ff7-110">Registers a Kanban transfer job as in progress.</span></span>                                                 |
| <span data-ttu-id="21ff7-111">Completada</span><span class="sxs-lookup"><span data-stu-id="21ff7-111">Complete</span></span>              | <span data-ttu-id="21ff7-112">Registra un trabajo de transferencia kanban como completado.</span><span class="sxs-lookup"><span data-stu-id="21ff7-112">Registers a Kanban transfer job as completed.</span></span>                                                   |
| <span data-ttu-id="21ff7-113">Vacía</span><span class="sxs-lookup"><span data-stu-id="21ff7-113">Empty</span></span>                 | <span data-ttu-id="21ff7-114">Registra la unidad de gestión de material a la que hace referencia una tarjeta kanban como vacía.</span><span class="sxs-lookup"><span data-stu-id="21ff7-114">Registers the material handling unit that is referenced by a Kanban card as empty.</span></span>              |
| <span data-ttu-id="21ff7-115">Seleccionar</span><span class="sxs-lookup"><span data-stu-id="21ff7-115">Select</span></span>                | <span data-ttu-id="21ff7-116">Registra un número de tarjeta kanban y selecciona automáticamente el trabajo al que se hace referencia en la lista de trabajos kanban.</span><span class="sxs-lookup"><span data-stu-id="21ff7-116">Registers a Kanban card number and automatically selects the referenced job in the Kanban list.</span></span> |

 
<span data-ttu-id="21ff7-117">Seleccionar el modo de registro</span><span class="sxs-lookup"><span data-stu-id="21ff7-117">Registration mode Select</span></span>
------------------------

<span data-ttu-id="21ff7-118">Cuando se usa un lector de códigos de barras para seleccionar un trabajo, el modo de visualización del tablero kanban cambia.</span><span class="sxs-lookup"><span data-stu-id="21ff7-118">When you use a bar code reader to select a job, the display mode of the kanban board changes.</span></span><span data-ttu-id="21ff7-119">De esta manera, se aplicarán las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="21ff7-119"> In this mode, the following conditions apply:</span></span>

-   <span data-ttu-id="21ff7-120">Solo se muestra el trabajo kanban escaneado.</span><span class="sxs-lookup"><span data-stu-id="21ff7-120">Only the scanned kanban job is displayed.</span></span>
-   <span data-ttu-id="21ff7-121">Los detalles del trabajo seleccionado se muestran en la ficha desplegable **Detalles**.</span><span class="sxs-lookup"><span data-stu-id="21ff7-121">The details of the selected job are displayed in the **Details** FastTab.</span></span>
-   <span data-ttu-id="21ff7-122">La ficha desplegable **Mensajes** muestra mensajes solo para el trabajo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="21ff7-122">The **Messages** FastTab displays messages only for the selected job.</span></span>
-   <span data-ttu-id="21ff7-123">Puede cambiar el estado del trabajo mediante las funciones disponibles en el Panel de acciones.</span><span class="sxs-lookup"><span data-stu-id="21ff7-123">You can change the status of the job by using the functions that are available on the Action Pane.</span></span> <span data-ttu-id="21ff7-124">El tablero kanban de transferencia sigue mostrando un solo trabajo durante este tiempo.</span><span class="sxs-lookup"><span data-stu-id="21ff7-124">The Kanban transfer board continues to display only a single job during this time.</span></span>
-   <span data-ttu-id="21ff7-125">Puede actualizar la información de la lista de trabajos manualmente haciendo clic en **Actualizar** (Mayús+F5) en el Panel de acciones.</span><span class="sxs-lookup"><span data-stu-id="21ff7-125">You can update the information in the list of jobs manually by clicking **Refresh** (Shift+F5) on the Action Pane.</span></span> <span data-ttu-id="21ff7-126">Tras actualizar la información, los resultados completos del filtro de trabajo se muestran de nuevo.</span><span class="sxs-lookup"><span data-stu-id="21ff7-126">After you refresh the information, the full results for the job filter are displayed again.</span></span>

## <a name="job-status-and-possible-actions"></a><span data-ttu-id="21ff7-127">Estado del trabajo y acciones posibles</span><span class="sxs-lookup"><span data-stu-id="21ff7-127">Job status and possible actions</span></span>
<span data-ttu-id="21ff7-128">El estado del trabajo seleccionado y el estado de cualquier trabajo fijado para los kanban de evento determinan si puede seguir procesando el trabajo.</span><span class="sxs-lookup"><span data-stu-id="21ff7-128">The status of the selected job and the status of any pegged jobs for event kanbans, determine whether you can process the job further.</span></span> <span data-ttu-id="21ff7-129">La tabla siguiente muestra información acerca de estos estados y tareas:</span><span class="sxs-lookup"><span data-stu-id="21ff7-129">The following table displays information about these statuses and tasks:</span></span>
-   <span data-ttu-id="21ff7-130">Los estados disponibles para los trabajos o para las unidades de gestión de material a los que hacen referencia los trabajos.</span><span class="sxs-lookup"><span data-stu-id="21ff7-130">The statuses that are available for jobs, or for the handling units that are referenced by the jobs.</span></span>
-   <span data-ttu-id="21ff7-131">Todas las tareas que puede realizar para el trabajo.</span><span class="sxs-lookup"><span data-stu-id="21ff7-131">Each task that you can perform for the job.</span></span>

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
<th><span data-ttu-id="21ff7-132">Tipo de trabajo</span><span class="sxs-lookup"><span data-stu-id="21ff7-132">Job type</span></span></th>
<th><span data-ttu-id="21ff7-133">El estado del trabajo o el estado de la unidad de gestión de material</span><span class="sxs-lookup"><span data-stu-id="21ff7-133">Job status or handling unit status</span></span></th>
<th><span data-ttu-id="21ff7-134">Actualizar lista de selección</span><span class="sxs-lookup"><span data-stu-id="21ff7-134">Update picking list</span></span></th>
<th><span data-ttu-id="21ff7-135">Iniciar</span><span class="sxs-lookup"><span data-stu-id="21ff7-135">Start</span></span></th>
<th><span data-ttu-id="21ff7-136">Actualizar registro</span><span class="sxs-lookup"><span data-stu-id="21ff7-136">Update registration</span></span></th>
<th><span data-ttu-id="21ff7-137">Completada</span><span class="sxs-lookup"><span data-stu-id="21ff7-137">Complete</span></span></th>
<th><span data-ttu-id="21ff7-138">Vacía</span><span class="sxs-lookup"><span data-stu-id="21ff7-138">Empty</span></span></th>
<th><span data-ttu-id="21ff7-139">Crear kanbans de evento</span><span class="sxs-lookup"><span data-stu-id="21ff7-139">Create event kanbans</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="21ff7-140">Transferir</span><span class="sxs-lookup"><span data-stu-id="21ff7-140">Transfer</span></span></td>
<td><ul>
<li><span data-ttu-id="21ff7-141">Sin planificar</span><span class="sxs-lookup"><span data-stu-id="21ff7-141">Not planned</span></span></li>
<li><span data-ttu-id="21ff7-142">No hay trabajos fijados o estos están completados</span><span class="sxs-lookup"><span data-stu-id="21ff7-142">No pegged jobs, or pegged jobs are Completed</span></span></li>
</ul></td>
<td><span data-ttu-id="21ff7-143">Sí</span><span class="sxs-lookup"><span data-stu-id="21ff7-143">Yes</span></span></td>
<td><span data-ttu-id="21ff7-144">Sí</span><span class="sxs-lookup"><span data-stu-id="21ff7-144">Yes</span></span></td>
<td><span data-ttu-id="21ff7-145">Sí</span><span class="sxs-lookup"><span data-stu-id="21ff7-145">Yes</span></span></td>
<td><span data-ttu-id="21ff7-146">Sí</span><span class="sxs-lookup"><span data-stu-id="21ff7-146">Yes</span></span></td>
<td><span data-ttu-id="21ff7-147">No</span><span class="sxs-lookup"><span data-stu-id="21ff7-147">No</span></span></td>
<td><span data-ttu-id="21ff7-148">Sí</span><span class="sxs-lookup"><span data-stu-id="21ff7-148">Yes</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="21ff7-149">Transferir</span><span class="sxs-lookup"><span data-stu-id="21ff7-149">Transfer</span></span></td>
<td><ul>
<li><span data-ttu-id="21ff7-150">Sin planificar</span><span class="sxs-lookup"><span data-stu-id="21ff7-150">Not planned</span></span></li>
<li><span data-ttu-id="21ff7-151">El trabajo fijado no está completado</span><span class="sxs-lookup"><span data-stu-id="21ff7-151">The pegged job is not Completed</span></span></li>
</ul></td>
<td><span data-ttu-id="21ff7-152">Sí</span><span class="sxs-lookup"><span data-stu-id="21ff7-152">Yes</span></span></td>
<td><span data-ttu-id="21ff7-153">No</span><span class="sxs-lookup"><span data-stu-id="21ff7-153">No</span></span></td>
<td><span data-ttu-id="21ff7-154">Sí</span><span class="sxs-lookup"><span data-stu-id="21ff7-154">Yes</span></span></td>
<td><span data-ttu-id="21ff7-155">No</span><span class="sxs-lookup"><span data-stu-id="21ff7-155">No</span></span></td>
<td><span data-ttu-id="21ff7-156">No</span><span class="sxs-lookup"><span data-stu-id="21ff7-156">No</span></span></td>
<td><span data-ttu-id="21ff7-157">No</span><span class="sxs-lookup"><span data-stu-id="21ff7-157">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="21ff7-158">Transferir</span><span class="sxs-lookup"><span data-stu-id="21ff7-158">Transfer</span></span></td>
<td><span data-ttu-id="21ff7-159">En curso</span><span class="sxs-lookup"><span data-stu-id="21ff7-159">In progress</span></span></td>
<td><span data-ttu-id="21ff7-160">Sí</span><span class="sxs-lookup"><span data-stu-id="21ff7-160">Yes</span></span></td>
<td><span data-ttu-id="21ff7-161">No</span><span class="sxs-lookup"><span data-stu-id="21ff7-161">No</span></span></td>
<td><span data-ttu-id="21ff7-162">Sí</span><span class="sxs-lookup"><span data-stu-id="21ff7-162">Yes</span></span></td>
<td><span data-ttu-id="21ff7-163">Sí</span><span class="sxs-lookup"><span data-stu-id="21ff7-163">Yes</span></span></td>
<td><span data-ttu-id="21ff7-164">No</span><span class="sxs-lookup"><span data-stu-id="21ff7-164">No</span></span></td>
<td><span data-ttu-id="21ff7-165">No</span><span class="sxs-lookup"><span data-stu-id="21ff7-165">No</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="21ff7-166">Transferir</span><span class="sxs-lookup"><span data-stu-id="21ff7-166">Transfer</span></span></td>
<td><span data-ttu-id="21ff7-167">Completada</span><span class="sxs-lookup"><span data-stu-id="21ff7-167">Completed</span></span></td>
<td><span data-ttu-id="21ff7-168">No</span><span class="sxs-lookup"><span data-stu-id="21ff7-168">No</span></span></td>
<td><span data-ttu-id="21ff7-169">No</span><span class="sxs-lookup"><span data-stu-id="21ff7-169">No</span></span></td>
<td><span data-ttu-id="21ff7-170">No</span><span class="sxs-lookup"><span data-stu-id="21ff7-170">No</span></span></td>
<td><span data-ttu-id="21ff7-171">No</span><span class="sxs-lookup"><span data-stu-id="21ff7-171">No</span></span></td>
<td><span data-ttu-id="21ff7-172">Sí</span><span class="sxs-lookup"><span data-stu-id="21ff7-172">Yes</span></span></td>
<td><span data-ttu-id="21ff7-173">No</span><span class="sxs-lookup"><span data-stu-id="21ff7-173">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="21ff7-174">Transferir o procesar</span><span class="sxs-lookup"><span data-stu-id="21ff7-174">Transfer or process</span></span></td>
<td><span data-ttu-id="21ff7-175">Vacía</span><span class="sxs-lookup"><span data-stu-id="21ff7-175">Empty</span></span></td>
<td><span data-ttu-id="21ff7-176">No</span><span class="sxs-lookup"><span data-stu-id="21ff7-176">No</span></span></td>
<td><span data-ttu-id="21ff7-177">No</span><span class="sxs-lookup"><span data-stu-id="21ff7-177">No</span></span></td>
<td><span data-ttu-id="21ff7-178">No</span><span class="sxs-lookup"><span data-stu-id="21ff7-178">No</span></span></td>
<td><span data-ttu-id="21ff7-179">No</span><span class="sxs-lookup"><span data-stu-id="21ff7-179">No</span></span></td>
<td><span data-ttu-id="21ff7-180">No</span><span class="sxs-lookup"><span data-stu-id="21ff7-180">No</span></span></td>
<td><span data-ttu-id="21ff7-181">No</span><span class="sxs-lookup"><span data-stu-id="21ff7-181">No</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="21ff7-182">Transferir o procesar</span><span class="sxs-lookup"><span data-stu-id="21ff7-182">Transfer or process</span></span></td>
<td><span data-ttu-id="21ff7-183">No se encuentra una tarjeta kanban</span><span class="sxs-lookup"><span data-stu-id="21ff7-183">A kanban card is not found</span></span></td>
<td><span data-ttu-id="21ff7-184">Nº</span><span class="sxs-lookup"><span data-stu-id="21ff7-184">No</span></span></td>
<td><span data-ttu-id="21ff7-185">Nº</span><span class="sxs-lookup"><span data-stu-id="21ff7-185">No</span></span></td>
<td><span data-ttu-id="21ff7-186">Nº</span><span class="sxs-lookup"><span data-stu-id="21ff7-186">No</span></span></td>
<td><span data-ttu-id="21ff7-187">Nº</span><span class="sxs-lookup"><span data-stu-id="21ff7-187">No</span></span></td>
<td><span data-ttu-id="21ff7-188">Nº</span><span class="sxs-lookup"><span data-stu-id="21ff7-188">No</span></span></td>
<td><span data-ttu-id="21ff7-189">Nº</span><span class="sxs-lookup"><span data-stu-id="21ff7-189">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="21ff7-190">Transferir o procesar</span><span class="sxs-lookup"><span data-stu-id="21ff7-190">Transfer or process</span></span></td>
<td><span data-ttu-id="21ff7-191">Se encuentra una tarjeta kanban, pero no está asignada a un kanban</span><span class="sxs-lookup"><span data-stu-id="21ff7-191">A kanban card is found, but it is not assigned to a kanban</span></span></td>
<td><span data-ttu-id="21ff7-192">No</span><span class="sxs-lookup"><span data-stu-id="21ff7-192">No</span></span></td>
<td><span data-ttu-id="21ff7-193">No</span><span class="sxs-lookup"><span data-stu-id="21ff7-193">No</span></span></td>
<td><span data-ttu-id="21ff7-194">No</span><span class="sxs-lookup"><span data-stu-id="21ff7-194">No</span></span></td>
<td><span data-ttu-id="21ff7-195">No</span><span class="sxs-lookup"><span data-stu-id="21ff7-195">No</span></span></td>
<td><span data-ttu-id="21ff7-196">No</span><span class="sxs-lookup"><span data-stu-id="21ff7-196">No</span></span></td>
<td><span data-ttu-id="21ff7-197">No</span><span class="sxs-lookup"><span data-stu-id="21ff7-197">No</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="21ff7-198">Procesar</span><span class="sxs-lookup"><span data-stu-id="21ff7-198">Process</span></span></td>
<td><ul>
<li><span data-ttu-id="21ff7-199">Sin planificar</span><span class="sxs-lookup"><span data-stu-id="21ff7-199">Not planned</span></span></li>
<li><span data-ttu-id="21ff7-200">Preparado</span><span class="sxs-lookup"><span data-stu-id="21ff7-200">Prepared</span></span></li>
<li><span data-ttu-id="21ff7-201">En curso</span><span class="sxs-lookup"><span data-stu-id="21ff7-201">In progress</span></span></li>
</ul></td>
<td><span data-ttu-id="21ff7-202">No</span><span class="sxs-lookup"><span data-stu-id="21ff7-202">No</span></span></td>
<td><span data-ttu-id="21ff7-203">No</span><span class="sxs-lookup"><span data-stu-id="21ff7-203">No</span></span></td>
<td><span data-ttu-id="21ff7-204">No</span><span class="sxs-lookup"><span data-stu-id="21ff7-204">No</span></span></td>
<td><span data-ttu-id="21ff7-205">No</span><span class="sxs-lookup"><span data-stu-id="21ff7-205">No</span></span></td>
<td><span data-ttu-id="21ff7-206">No</span><span class="sxs-lookup"><span data-stu-id="21ff7-206">No</span></span></td>
<td><span data-ttu-id="21ff7-207">No</span><span class="sxs-lookup"><span data-stu-id="21ff7-207">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="21ff7-208">Procesar</span><span class="sxs-lookup"><span data-stu-id="21ff7-208">Process</span></span></td>
<td><span data-ttu-id="21ff7-209">Completada</span><span class="sxs-lookup"><span data-stu-id="21ff7-209">Completed</span></span></td>
<td><span data-ttu-id="21ff7-210">No</span><span class="sxs-lookup"><span data-stu-id="21ff7-210">No</span></span></td>
<td><span data-ttu-id="21ff7-211">No</span><span class="sxs-lookup"><span data-stu-id="21ff7-211">No</span></span></td>
<td><span data-ttu-id="21ff7-212">No</span><span class="sxs-lookup"><span data-stu-id="21ff7-212">No</span></span></td>
<td><span data-ttu-id="21ff7-213">No</span><span class="sxs-lookup"><span data-stu-id="21ff7-213">No</span></span></td>
<td><span data-ttu-id="21ff7-214">No</span><span class="sxs-lookup"><span data-stu-id="21ff7-214">No</span></span></td>
<td><span data-ttu-id="21ff7-215">No</span><span class="sxs-lookup"><span data-stu-id="21ff7-215">No</span></span></td>
</tr>
</tbody>
</table>





