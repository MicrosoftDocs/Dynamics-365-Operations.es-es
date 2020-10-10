---
title: Cancelar un trabajo de planificación maestro
description: Este tema explica cómo cancelar un trabajo activo de planificación que utilice la función planificación integrada.
author: ChristianRytt
manager: tfehr
ms.date: 05/14/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace, ReqProcessList
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-12-16
ms.dyn365.ops.version: ''
ms.openlocfilehash: 6f5ce460cc2915d1d4d9b5699723a62ed7f94599
ms.sourcegitcommit: cde71bc7d14ea6cdff2c4e991057d39a6a0473d9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "3886880"
---
# <a name="cancel-a-master-planning-job"></a><span data-ttu-id="242e5-103">Cancelar un trabajo de planificación maestro</span><span class="sxs-lookup"><span data-stu-id="242e5-103">Cancel a master planning job</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="242e5-104">En Microsoft Dynamics 365 Supply Chain Management, hay varias opciones para cancelar un trabajo de planificación maestro.</span><span class="sxs-lookup"><span data-stu-id="242e5-104">In Microsoft Dynamics 365 Supply Chain Management, there are multiple options for canceling a master planning job.</span></span> <span data-ttu-id="242e5-105">Por ejemplo, es posible que desee cancelar un trabajo de planificación maestra si se inició por error o si se está ejecutando por más tiempo de lo esperado y desea finalizarlo.</span><span class="sxs-lookup"><span data-stu-id="242e5-105">For example, you may want to cancel a master planning job if it was started by mistake or is running longer than expected and you want to end it.</span></span> <span data-ttu-id="242e5-106">La mejor manera de cancelar un trabajo de planificación es desde la **Procesos de planificación inacabados** página.</span><span class="sxs-lookup"><span data-stu-id="242e5-106">The best way to cancel a planning job is from  the **Unfinished planning processes** page.</span></span> <span data-ttu-id="242e5-107">Las opciones alternativas de las páginas **Trabajos por lotes** y **Trabajos por lotes mejorados** solo deben usarse si cancelar el trabajo de planificación maestra desde la página **Procesos de planificación inacabados** no se completó en unos minutos.</span><span class="sxs-lookup"><span data-stu-id="242e5-107">Alternative options from the **Batch jobs** and **Batch jobs enhanced** pages should only be used if canceling the master planning job from the **Unfinished planning processes** page did not complete within a few minutes.</span></span>

## <a name="preferred-cancel-option"></a><span data-ttu-id="242e5-108">Opción de cancelación preferida</span><span class="sxs-lookup"><span data-stu-id="242e5-108">Preferred cancel option</span></span>
### <a name="cancel-master-planning-job-from-unfinished-planning-processes-page"></a><span data-ttu-id="242e5-109">Cancelar el trabajo de planificación maestra desde la página **Procesos de planificación inacabados**</span><span class="sxs-lookup"><span data-stu-id="242e5-109">Cancel master planning job from **Unfinished planning processes** page</span></span>
1. <span data-ttu-id="242e5-110">Vaya a **Planificación maestra > Consultas e informes > Planificación maestra > Procesos de planificación inacabados**.</span><span class="sxs-lookup"><span data-stu-id="242e5-110">Go to **Master planning > Inquiries and reports > Master planning > Unfinished planning processes**.</span></span>
2. <span data-ttu-id="242e5-111">Seleccione la línea con el proceso de planificación que quiera cancelar.</span><span class="sxs-lookup"><span data-stu-id="242e5-111">Select the line with the planning process that you want to cancel.</span></span>
3. <span data-ttu-id="242e5-112">Haga clic en **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="242e5-112">Click **Cancel**.</span></span>

## <a name="additional-cancel-options"></a><span data-ttu-id="242e5-113">Opciones adicionales de cancelación</span><span class="sxs-lookup"><span data-stu-id="242e5-113">Additional cancel options</span></span>
<span data-ttu-id="242e5-114">Estas solo deben usarse si la cancelación del trabajo de planificación maestra desde la página **Procesos de planificación inacabados** no se completó en unos minutos.</span><span class="sxs-lookup"><span data-stu-id="242e5-114">These should only be used if canceling the master planning job from the **Unfinished planning processes** page did not complete within a few minutes.</span></span>

### <a name="delete-master-planning-job-from-the-batch-jobs-page"></a><span data-ttu-id="242e5-115">Eliminar el trabajo de planificación maestra de la página **Trabajos por lotes**</span><span class="sxs-lookup"><span data-stu-id="242e5-115">Delete master planning job from the **Batch jobs** page</span></span>
1. <span data-ttu-id="242e5-116">Vaya **Administración del sistema > Consultas > Trabajos por lotes**.</span><span class="sxs-lookup"><span data-stu-id="242e5-116">Go to **System administration > Inquiries > Batch jobs**.</span></span>
2. <span data-ttu-id="242e5-117">Seleccione la línea con el trabajo de planificación que quiera eliminar.</span><span class="sxs-lookup"><span data-stu-id="242e5-117">Select the line with the planning job that you want to delete.</span></span>
3. <span data-ttu-id="242e5-118">Haga clic **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="242e5-118">Click **Delete**.</span></span>

### <a name="abort-master-planning-job-task-from-the-batch-jobs-enhanced-page"></a><span data-ttu-id="242e5-119">Anular la tarea de planificación maestra desde la página **Trabajos por lotes mejorados**</span><span class="sxs-lookup"><span data-stu-id="242e5-119">Abort master planning job task from the **Batch jobs enhanced** page</span></span>
1. <span data-ttu-id="242e5-120">Vaya **Administración del sistema > Consultas > Trabajos por lotes**.</span><span class="sxs-lookup"><span data-stu-id="242e5-120">Go to **System administration > Inquiries > Batch jobs**.</span></span>
2. <span data-ttu-id="242e5-121">Si la ID del trabajo no se muestra en la lista, haga clic en **Cambiar a forma mejorada**, de lo contrario, continúe con el siguiente paso.</span><span class="sxs-lookup"><span data-stu-id="242e5-121">If the job ID is not shown in the list, click **Switch to enhanced form**, otherwise proceed with the next step.</span></span>
3. <span data-ttu-id="242e5-122">Abra el trabajo por lotes.</span><span class="sxs-lookup"><span data-stu-id="242e5-122">Open the batch job.</span></span> <span data-ttu-id="242e5-123">Haga clic en la **Identificación del trabajo** para el trabajo por lotes con tareas que desea finalizar.</span><span class="sxs-lookup"><span data-stu-id="242e5-123">Click the **Job ID** for the batch job with tasks that you want to end.</span></span>
4. <span data-ttu-id="242e5-124">En **Tareas por lotes**, seleccione las tareas para finalizar.</span><span class="sxs-lookup"><span data-stu-id="242e5-124">In **Batch tasks**, select the tasks to end.</span></span>
5. <span data-ttu-id="242e5-125">Haga clic en **Cambiar Estado**, elija **Cancelación** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="242e5-125">Click **Change status**, choose **Canceling** and click **OK**.</span></span>
6. <span data-ttu-id="242e5-126">En la ficha desplegable **Tareas por lotes**, haga clic en **Anular**.</span><span class="sxs-lookup"><span data-stu-id="242e5-126">On the **Batch tasks** FastTab, click **Abort**.</span></span>
