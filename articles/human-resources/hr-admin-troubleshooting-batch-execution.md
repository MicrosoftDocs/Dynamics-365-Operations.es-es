---
title: Restablecer trabajos por lotes atascados
description: Este tema explica cómo resolver problemas con trabajos por lotes que están atascados.
author: andreabichsel
ms.date: 03/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2021-03-19
ms.dyn365.ops.version: Platform update 42
ms.openlocfilehash: 01ef0bf8ccc486614eec42d3fb6f0b2941fc47c0
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5794958"
---
# <a name="reset-stuck-batch-jobs"></a><span data-ttu-id="4dbe1-103">Restablecer trabajos por lotes atascados</span><span class="sxs-lookup"><span data-stu-id="4dbe1-103">Reset stuck batch jobs</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

## <a name="issue"></a><span data-ttu-id="4dbe1-104">Emitir</span><span class="sxs-lookup"><span data-stu-id="4dbe1-104">Issue</span></span>

<span data-ttu-id="4dbe1-105">Microsoft Dynamics 365 Human Resources puede experimentar problemas con los trabajos por lotes que se atascan en estado **Ejecución** o **Cancelación** y no se completan.</span><span class="sxs-lookup"><span data-stu-id="4dbe1-105">Microsoft Dynamics 365 Human Resources can experience issues with batch jobs that are stuck in either an **Executing** or **Canceling** state and don't complete.</span></span>

## <a name="resolution"></a><span data-ttu-id="4dbe1-106">Resolución</span><span class="sxs-lookup"><span data-stu-id="4dbe1-106">Resolution</span></span>

<span data-ttu-id="4dbe1-107">Cuando un trabajo por lotes se atasca en un estado **Ejecución** o **Cancelación**, puede restablecer el estado forzando la cancelación del trabajo.</span><span class="sxs-lookup"><span data-stu-id="4dbe1-107">When a batch job is stuck in an **Executing** or **Canceling** state, you can reset the status by forcing the cancellation of the job.</span></span> <span data-ttu-id="4dbe1-108">Después de cancelarlo, puede restablecer el trabajo por lotes configurándolo en un estado **Esperando**.</span><span class="sxs-lookup"><span data-stu-id="4dbe1-108">After you cancel it, you can reset the batch job by setting it to a **Waiting** status.</span></span> <span data-ttu-id="4dbe1-109">A continuación, se volverá a recoger para su ejecución en la siguiente ejecución por lotes programada.</span><span class="sxs-lookup"><span data-stu-id="4dbe1-109">It will then be picked up again for execution in the next scheduled batch run.</span></span>

1. <span data-ttu-id="4dbe1-110">En el espacio de trabajo **Administracion del sistema**, seleccione la página **Vínculos** y elija **Trabajos por lotes**.</span><span class="sxs-lookup"><span data-stu-id="4dbe1-110">In the **System administration** workspace, select the **Links** page, and select **Batch jobs**.</span></span>

2. <span data-ttu-id="4dbe1-111">En la página de lista **Trabajo por lotes**, seleccione el trabajo que necesita restablecerse.</span><span class="sxs-lookup"><span data-stu-id="4dbe1-111">On the **Batch job** list page, select the job that needs to be reset.</span></span>

3. <span data-ttu-id="4dbe1-112">En la cinta de acciones, seleccione **Forzar cancelación** y confirme la acción.</span><span class="sxs-lookup"><span data-stu-id="4dbe1-112">On the action ribbon, select **Force cancel**, and confirm the action.</span></span>

   > [!NOTE]
   > <span data-ttu-id="4dbe1-113">La acción **Forzar cancelación** solo está disponible cuando el trabajo por lotes seleccionado tiene un estado de **Ejecutando** o **Cancelando** y no se están ejecutando procesos de cancelación o ejecución por lotes para el trabajo.</span><span class="sxs-lookup"><span data-stu-id="4dbe1-113">The **Force cancel** action is only available when the selected batch job has a status of either **Executing** or **Canceling**, and no batch execution or cancellation processes are running for the job.</span></span>

4. <span data-ttu-id="4dbe1-114">En la cinta de acciones, seleccione **Cambiar estado**.</span><span class="sxs-lookup"><span data-stu-id="4dbe1-114">On the action ribbon, select **Change status**.</span></span>

5. <span data-ttu-id="4dbe1-115">En la página **Seleccionar nuevo estado**, seleccione **Esperando** y luego seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="4dbe1-115">On the **Select new status** page, select **Waiting**, and then select **OK**.</span></span>

   ![Seleccionar un nuevo estado de trabajo por lotes](./media/hr-admin-reset-batch-job-status.png)

## <a name="see-also"></a><span data-ttu-id="4dbe1-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4dbe1-117">See also</span></span>

[<span data-ttu-id="4dbe1-118">Optimizar el rendimiento programando trabajos por lotes fuera del horario laboral</span><span class="sxs-lookup"><span data-stu-id="4dbe1-118">Optimize performance by scheduling batch jobs after hours</span></span>](hr-admin-troubleshooting-batch-jobs.md)<br>
[<span data-ttu-id="4dbe1-119">Optimizar el rendimiento con tareas automáticas de limpieza</span><span class="sxs-lookup"><span data-stu-id="4dbe1-119">Optimize performance with auto cleanup tasks</span></span>](hr-admin-troubleshooting-batch-history.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
