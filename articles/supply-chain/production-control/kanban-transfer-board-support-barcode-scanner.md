---
title: Compatibilidad del tablero de transferencia kanban para escáneres de códigos de barras
description: El tablero de transferencia kanban admite la entrada del escáner desde un lector de códigos de barras de widget para seleccionar, iniciar, completar y vaciar un trabajo kanban.
author: ChristianRytt
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanBoardTransferJob
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19391
ms.assetid: a426f645-d59b-4c98-8d78-eba8d64a562e
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c48c4737c260004ea44109cfb2a0478a3e8653cc
ms.sourcegitcommit: ff09736563d3cd2bc74c7664edd1767b218401cb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2021
ms.locfileid: "6190073"
---
# <a name="kanban-transfer-board-support-for-barcode-scanners"></a><span data-ttu-id="1aaae-103">Compatibilidad del tablero de transferencia kanban para escáneres de códigos de barras</span><span class="sxs-lookup"><span data-stu-id="1aaae-103">Kanban transfer board support for barcode scanners</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1aaae-104">El tablero de transferencia kanban admite la entrada del escáner desde un lector de códigos de barras de widget para seleccionar, iniciar, completar y vaciar un trabajo kanban.</span><span class="sxs-lookup"><span data-stu-id="1aaae-104">The Kanban transfer board supports scanner input from a widget barcode scanner to Select, Start, Complete, and Empty a kanban job.</span></span>

## <a name="registration-modes"></a><span data-ttu-id="1aaae-105">Modos de registro</span><span class="sxs-lookup"><span data-stu-id="1aaae-105">Registration modes</span></span>

<span data-ttu-id="1aaae-106">En la ficha desplegable **Registro de escáner**, puede seleccionar el modo de registro, que controla la acción cuando se escanea un número de tarjeta kanban o se escribe manualmente el número en el campo de número de tarjeta kanban.</span><span class="sxs-lookup"><span data-stu-id="1aaae-106">On the **Scanner registration** FastTab you can select the registration mode, which controls the action when you scan a kanban card number or manually type the number in the Kanban card number field.</span></span>

| <span data-ttu-id="1aaae-107">Establecer modo de registro</span><span class="sxs-lookup"><span data-stu-id="1aaae-107">Set registration mode</span></span> | <span data-ttu-id="1aaae-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="1aaae-108">Description</span></span>                                                                                     |
|-----------------------|-------------------------------------------------------------------------------------------------|
| <span data-ttu-id="1aaae-109">Iniciar</span><span class="sxs-lookup"><span data-stu-id="1aaae-109">Start</span></span>                 | <span data-ttu-id="1aaae-110">Registra un trabajo de transferencia kanban como en curso.</span><span class="sxs-lookup"><span data-stu-id="1aaae-110">Registers a Kanban transfer job as in progress.</span></span>                                                 |
| <span data-ttu-id="1aaae-111">Completada</span><span class="sxs-lookup"><span data-stu-id="1aaae-111">Complete</span></span>              | <span data-ttu-id="1aaae-112">Registra un trabajo de transferencia kanban como completado.</span><span class="sxs-lookup"><span data-stu-id="1aaae-112">Registers a Kanban transfer job as completed.</span></span>                                                   |
| <span data-ttu-id="1aaae-113">Vacía</span><span class="sxs-lookup"><span data-stu-id="1aaae-113">Empty</span></span>                 | <span data-ttu-id="1aaae-114">Registra la unidad de gestión de material a la que hace referencia una tarjeta kanban como vacía.</span><span class="sxs-lookup"><span data-stu-id="1aaae-114">Registers the material handling unit that is referenced by a Kanban card as empty.</span></span>              |
| <span data-ttu-id="1aaae-115">Seleccionar</span><span class="sxs-lookup"><span data-stu-id="1aaae-115">Select</span></span>                | <span data-ttu-id="1aaae-116">Registra un número de tarjeta kanban y selecciona automáticamente el trabajo al que se hace referencia en la lista de trabajos kanban.</span><span class="sxs-lookup"><span data-stu-id="1aaae-116">Registers a Kanban card number and automatically selects the referenced job in the Kanban list.</span></span> |

 
## <a name="registration-mode-select"></a><span data-ttu-id="1aaae-117">Seleccionar el modo de registro</span><span class="sxs-lookup"><span data-stu-id="1aaae-117">Registration mode Select</span></span>

<span data-ttu-id="1aaae-118">Cuando se usa un lector de códigos de barras para seleccionar un trabajo, el modo de visualización del tablero kanban cambia.</span><span class="sxs-lookup"><span data-stu-id="1aaae-118">When you use a bar code reader to select a job, the display mode of the kanban board changes.</span></span> <span data-ttu-id="1aaae-119">De esta manera, se aplicarán las condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="1aaae-119">In this mode, the following conditions apply:</span></span>

-   <span data-ttu-id="1aaae-120">Solo se muestra el trabajo kanban escaneado.</span><span class="sxs-lookup"><span data-stu-id="1aaae-120">Only the scanned kanban job is displayed.</span></span>
-   <span data-ttu-id="1aaae-121">Los detalles del trabajo seleccionado se muestran en la ficha desplegable **Detalles**.</span><span class="sxs-lookup"><span data-stu-id="1aaae-121">The details of the selected job are displayed in the **Details** FastTab.</span></span>
-   <span data-ttu-id="1aaae-122">La ficha desplegable **Mensajes** muestra mensajes solo para el trabajo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="1aaae-122">The **Messages** FastTab displays messages only for the selected job.</span></span>
-   <span data-ttu-id="1aaae-123">Puede cambiar el estado del trabajo mediante las funciones disponibles en el Panel de acciones.</span><span class="sxs-lookup"><span data-stu-id="1aaae-123">You can change the status of the job by using the functions that are available on the Action Pane.</span></span> <span data-ttu-id="1aaae-124">El tablero kanban de transferencia sigue mostrando un solo trabajo durante este tiempo.</span><span class="sxs-lookup"><span data-stu-id="1aaae-124">The Kanban transfer board continues to display only a single job during this time.</span></span>
-   <span data-ttu-id="1aaae-125">Puede actualizar la información de la lista de trabajos manualmente haciendo clic en **Actualizar** (Mayús+F5) en el Panel de acciones.</span><span class="sxs-lookup"><span data-stu-id="1aaae-125">You can update the information in the list of jobs manually by clicking **Refresh** (Shift+F5) on the Action Pane.</span></span> <span data-ttu-id="1aaae-126">Tras actualizar la información, los resultados completos del filtro de trabajo se muestran de nuevo.</span><span class="sxs-lookup"><span data-stu-id="1aaae-126">After you refresh the information, the full results for the job filter are displayed again.</span></span>

## <a name="job-status-and-possible-actions"></a><span data-ttu-id="1aaae-127">Estado del trabajo y acciones posibles</span><span class="sxs-lookup"><span data-stu-id="1aaae-127">Job status and possible actions</span></span>
<span data-ttu-id="1aaae-128">El estado del trabajo seleccionado y el estado de cualquier trabajo fijado para los kanban de evento determinan si puede seguir procesando el trabajo.</span><span class="sxs-lookup"><span data-stu-id="1aaae-128">The status of the selected job and the status of any pegged jobs for event kanbans, determine whether you can process the job further.</span></span> <span data-ttu-id="1aaae-129">La tabla siguiente muestra información acerca de estos estados y tareas:</span><span class="sxs-lookup"><span data-stu-id="1aaae-129">The following table displays information about these statuses and tasks:</span></span>
-   <span data-ttu-id="1aaae-130">Los estados disponibles para los trabajos o para las unidades de gestión de material a los que hacen referencia los trabajos.</span><span class="sxs-lookup"><span data-stu-id="1aaae-130">The statuses that are available for jobs, or for the handling units that are referenced by the jobs.</span></span>
-   <span data-ttu-id="1aaae-131">Todas las tareas que puede realizar para el trabajo.</span><span class="sxs-lookup"><span data-stu-id="1aaae-131">Each task that you can perform for the job.</span></span>

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
<th><span data-ttu-id="1aaae-132">Tipo de trabajo</span><span class="sxs-lookup"><span data-stu-id="1aaae-132">Job type</span></span></th>
<th><span data-ttu-id="1aaae-133">El estado del trabajo o el estado de la unidad de gestión de material</span><span class="sxs-lookup"><span data-stu-id="1aaae-133">Job status or handling unit status</span></span></th>
<th><span data-ttu-id="1aaae-134">Actualizar lista de selección</span><span class="sxs-lookup"><span data-stu-id="1aaae-134">Update picking list</span></span></th>
<th><span data-ttu-id="1aaae-135">Iniciar</span><span class="sxs-lookup"><span data-stu-id="1aaae-135">Start</span></span></th>
<th><span data-ttu-id="1aaae-136">Actualizar registro</span><span class="sxs-lookup"><span data-stu-id="1aaae-136">Update registration</span></span></th>
<th><span data-ttu-id="1aaae-137">Completada</span><span class="sxs-lookup"><span data-stu-id="1aaae-137">Complete</span></span></th>
<th><span data-ttu-id="1aaae-138">Vacía</span><span class="sxs-lookup"><span data-stu-id="1aaae-138">Empty</span></span></th>
<th><span data-ttu-id="1aaae-139">Crear kanbans de evento</span><span class="sxs-lookup"><span data-stu-id="1aaae-139">Create event kanbans</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="1aaae-140">Transferir</span><span class="sxs-lookup"><span data-stu-id="1aaae-140">Transfer</span></span></td>
<td><ul>
<li><span data-ttu-id="1aaae-141">Sin planificar</span><span class="sxs-lookup"><span data-stu-id="1aaae-141">Not planned</span></span></li>
<li><span data-ttu-id="1aaae-142">No hay trabajos fijados o estos están completados</span><span class="sxs-lookup"><span data-stu-id="1aaae-142">No pegged jobs, or pegged jobs are Completed</span></span></li>
</ul></td>
<td><span data-ttu-id="1aaae-143">Sí</span><span class="sxs-lookup"><span data-stu-id="1aaae-143">Yes</span></span></td>
<td><span data-ttu-id="1aaae-144">Sí</span><span class="sxs-lookup"><span data-stu-id="1aaae-144">Yes</span></span></td>
<td><span data-ttu-id="1aaae-145">Sí</span><span class="sxs-lookup"><span data-stu-id="1aaae-145">Yes</span></span></td>
<td><span data-ttu-id="1aaae-146">Sí</span><span class="sxs-lookup"><span data-stu-id="1aaae-146">Yes</span></span></td>
<td><span data-ttu-id="1aaae-147">No</span><span class="sxs-lookup"><span data-stu-id="1aaae-147">No</span></span></td>
<td><span data-ttu-id="1aaae-148">Sí</span><span class="sxs-lookup"><span data-stu-id="1aaae-148">Yes</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="1aaae-149">Transferir</span><span class="sxs-lookup"><span data-stu-id="1aaae-149">Transfer</span></span></td>
<td><ul>
<li><span data-ttu-id="1aaae-150">Sin planificar</span><span class="sxs-lookup"><span data-stu-id="1aaae-150">Not planned</span></span></li>
<li><span data-ttu-id="1aaae-151">El trabajo fijado no está completado</span><span class="sxs-lookup"><span data-stu-id="1aaae-151">The pegged job is not Completed</span></span></li>
</ul></td>
<td><span data-ttu-id="1aaae-152">Sí</span><span class="sxs-lookup"><span data-stu-id="1aaae-152">Yes</span></span></td>
<td><span data-ttu-id="1aaae-153">No</span><span class="sxs-lookup"><span data-stu-id="1aaae-153">No</span></span></td>
<td><span data-ttu-id="1aaae-154">Sí</span><span class="sxs-lookup"><span data-stu-id="1aaae-154">Yes</span></span></td>
<td><span data-ttu-id="1aaae-155">No</span><span class="sxs-lookup"><span data-stu-id="1aaae-155">No</span></span></td>
<td><span data-ttu-id="1aaae-156">No</span><span class="sxs-lookup"><span data-stu-id="1aaae-156">No</span></span></td>
<td><span data-ttu-id="1aaae-157">No</span><span class="sxs-lookup"><span data-stu-id="1aaae-157">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="1aaae-158">Transferir</span><span class="sxs-lookup"><span data-stu-id="1aaae-158">Transfer</span></span></td>
<td><span data-ttu-id="1aaae-159">En curso</span><span class="sxs-lookup"><span data-stu-id="1aaae-159">In progress</span></span></td>
<td><span data-ttu-id="1aaae-160">Sí</span><span class="sxs-lookup"><span data-stu-id="1aaae-160">Yes</span></span></td>
<td><span data-ttu-id="1aaae-161">No</span><span class="sxs-lookup"><span data-stu-id="1aaae-161">No</span></span></td>
<td><span data-ttu-id="1aaae-162">Sí</span><span class="sxs-lookup"><span data-stu-id="1aaae-162">Yes</span></span></td>
<td><span data-ttu-id="1aaae-163">Sí</span><span class="sxs-lookup"><span data-stu-id="1aaae-163">Yes</span></span></td>
<td><span data-ttu-id="1aaae-164">No</span><span class="sxs-lookup"><span data-stu-id="1aaae-164">No</span></span></td>
<td><span data-ttu-id="1aaae-165">No</span><span class="sxs-lookup"><span data-stu-id="1aaae-165">No</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="1aaae-166">Transferir</span><span class="sxs-lookup"><span data-stu-id="1aaae-166">Transfer</span></span></td>
<td><span data-ttu-id="1aaae-167">Completada</span><span class="sxs-lookup"><span data-stu-id="1aaae-167">Completed</span></span></td>
<td><span data-ttu-id="1aaae-168">No</span><span class="sxs-lookup"><span data-stu-id="1aaae-168">No</span></span></td>
<td><span data-ttu-id="1aaae-169">No</span><span class="sxs-lookup"><span data-stu-id="1aaae-169">No</span></span></td>
<td><span data-ttu-id="1aaae-170">No</span><span class="sxs-lookup"><span data-stu-id="1aaae-170">No</span></span></td>
<td><span data-ttu-id="1aaae-171">No</span><span class="sxs-lookup"><span data-stu-id="1aaae-171">No</span></span></td>
<td><span data-ttu-id="1aaae-172">Sí</span><span class="sxs-lookup"><span data-stu-id="1aaae-172">Yes</span></span></td>
<td><span data-ttu-id="1aaae-173">No</span><span class="sxs-lookup"><span data-stu-id="1aaae-173">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="1aaae-174">Transferir o procesar</span><span class="sxs-lookup"><span data-stu-id="1aaae-174">Transfer or process</span></span></td>
<td><span data-ttu-id="1aaae-175">Vacía</span><span class="sxs-lookup"><span data-stu-id="1aaae-175">Empty</span></span></td>
<td><span data-ttu-id="1aaae-176">No</span><span class="sxs-lookup"><span data-stu-id="1aaae-176">No</span></span></td>
<td><span data-ttu-id="1aaae-177">No</span><span class="sxs-lookup"><span data-stu-id="1aaae-177">No</span></span></td>
<td><span data-ttu-id="1aaae-178">No</span><span class="sxs-lookup"><span data-stu-id="1aaae-178">No</span></span></td>
<td><span data-ttu-id="1aaae-179">No</span><span class="sxs-lookup"><span data-stu-id="1aaae-179">No</span></span></td>
<td><span data-ttu-id="1aaae-180">No</span><span class="sxs-lookup"><span data-stu-id="1aaae-180">No</span></span></td>
<td><span data-ttu-id="1aaae-181">No</span><span class="sxs-lookup"><span data-stu-id="1aaae-181">No</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="1aaae-182">Transferir o procesar</span><span class="sxs-lookup"><span data-stu-id="1aaae-182">Transfer or process</span></span></td>
<td><span data-ttu-id="1aaae-183">No se encuentra una tarjeta kanban</span><span class="sxs-lookup"><span data-stu-id="1aaae-183">A kanban card is not found</span></span></td>
<td><span data-ttu-id="1aaae-184">Nº</span><span class="sxs-lookup"><span data-stu-id="1aaae-184">No</span></span></td>
<td><span data-ttu-id="1aaae-185">Nº</span><span class="sxs-lookup"><span data-stu-id="1aaae-185">No</span></span></td>
<td><span data-ttu-id="1aaae-186">Nº</span><span class="sxs-lookup"><span data-stu-id="1aaae-186">No</span></span></td>
<td><span data-ttu-id="1aaae-187">Nº</span><span class="sxs-lookup"><span data-stu-id="1aaae-187">No</span></span></td>
<td><span data-ttu-id="1aaae-188">Nº</span><span class="sxs-lookup"><span data-stu-id="1aaae-188">No</span></span></td>
<td><span data-ttu-id="1aaae-189">Nº</span><span class="sxs-lookup"><span data-stu-id="1aaae-189">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="1aaae-190">Transferir o procesar</span><span class="sxs-lookup"><span data-stu-id="1aaae-190">Transfer or process</span></span></td>
<td><span data-ttu-id="1aaae-191">Se encuentra una tarjeta kanban, pero no está asignada a un kanban</span><span class="sxs-lookup"><span data-stu-id="1aaae-191">A kanban card is found, but it is not assigned to a kanban</span></span></td>
<td><span data-ttu-id="1aaae-192">No</span><span class="sxs-lookup"><span data-stu-id="1aaae-192">No</span></span></td>
<td><span data-ttu-id="1aaae-193">No</span><span class="sxs-lookup"><span data-stu-id="1aaae-193">No</span></span></td>
<td><span data-ttu-id="1aaae-194">No</span><span class="sxs-lookup"><span data-stu-id="1aaae-194">No</span></span></td>
<td><span data-ttu-id="1aaae-195">No</span><span class="sxs-lookup"><span data-stu-id="1aaae-195">No</span></span></td>
<td><span data-ttu-id="1aaae-196">No</span><span class="sxs-lookup"><span data-stu-id="1aaae-196">No</span></span></td>
<td><span data-ttu-id="1aaae-197">No</span><span class="sxs-lookup"><span data-stu-id="1aaae-197">No</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="1aaae-198">Procesar</span><span class="sxs-lookup"><span data-stu-id="1aaae-198">Process</span></span></td>
<td><ul>
<li><span data-ttu-id="1aaae-199">Sin planificar</span><span class="sxs-lookup"><span data-stu-id="1aaae-199">Not planned</span></span></li>
<li><span data-ttu-id="1aaae-200">Preparado</span><span class="sxs-lookup"><span data-stu-id="1aaae-200">Prepared</span></span></li>
<li><span data-ttu-id="1aaae-201">En curso</span><span class="sxs-lookup"><span data-stu-id="1aaae-201">In progress</span></span></li>
</ul></td>
<td><span data-ttu-id="1aaae-202">No</span><span class="sxs-lookup"><span data-stu-id="1aaae-202">No</span></span></td>
<td><span data-ttu-id="1aaae-203">No</span><span class="sxs-lookup"><span data-stu-id="1aaae-203">No</span></span></td>
<td><span data-ttu-id="1aaae-204">No</span><span class="sxs-lookup"><span data-stu-id="1aaae-204">No</span></span></td>
<td><span data-ttu-id="1aaae-205">No</span><span class="sxs-lookup"><span data-stu-id="1aaae-205">No</span></span></td>
<td><span data-ttu-id="1aaae-206">No</span><span class="sxs-lookup"><span data-stu-id="1aaae-206">No</span></span></td>
<td><span data-ttu-id="1aaae-207">No</span><span class="sxs-lookup"><span data-stu-id="1aaae-207">No</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="1aaae-208">Procesar</span><span class="sxs-lookup"><span data-stu-id="1aaae-208">Process</span></span></td>
<td><span data-ttu-id="1aaae-209">Completada</span><span class="sxs-lookup"><span data-stu-id="1aaae-209">Completed</span></span></td>
<td><span data-ttu-id="1aaae-210">No</span><span class="sxs-lookup"><span data-stu-id="1aaae-210">No</span></span></td>
<td><span data-ttu-id="1aaae-211">No</span><span class="sxs-lookup"><span data-stu-id="1aaae-211">No</span></span></td>
<td><span data-ttu-id="1aaae-212">No</span><span class="sxs-lookup"><span data-stu-id="1aaae-212">No</span></span></td>
<td><span data-ttu-id="1aaae-213">No</span><span class="sxs-lookup"><span data-stu-id="1aaae-213">No</span></span></td>
<td><span data-ttu-id="1aaae-214">No</span><span class="sxs-lookup"><span data-stu-id="1aaae-214">No</span></span></td>
<td><span data-ttu-id="1aaae-215">No</span><span class="sxs-lookup"><span data-stu-id="1aaae-215">No</span></span></td>
</tr>
</tbody>
</table>







[!INCLUDE[footer-include](../../includes/footer-banner.md)]