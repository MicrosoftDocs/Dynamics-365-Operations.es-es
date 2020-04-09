---
title: Crear un trabajo por lotes
description: Un trabajo por lotes es un grupo de tareas enviadas a una instancia de Application Object Server (AOS) para su procesamiento automático.
author: maertenm
manager: AnnBe
ms.date: 06/21/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BatchJob, SysRecurrence, BatchAlerts
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f6eee5c6dd7daf2b0c79dd34d15a7dde919bdd60
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2020
ms.locfileid: "3143682"
---
# <a name="create-a-batch-job"></a><span data-ttu-id="0e1df-103">Crear un trabajo por lotes</span><span class="sxs-lookup"><span data-stu-id="0e1df-103">Create a batch job</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="0e1df-104">Un trabajo por lotes es un grupo de tareas enviadas a una instancia de Application Object Server (AOS) para su procesamiento automático.</span><span class="sxs-lookup"><span data-stu-id="0e1df-104">A batch job is a group of tasks that are submitted to an Application Object Server (AOS) instance for automatic processing.</span></span> <span data-ttu-id="0e1df-105">Los trabajos por lotes se ejecutan mediante las credenciales de seguridad del usuario que creó el trabajo.</span><span class="sxs-lookup"><span data-stu-id="0e1df-105">Batch jobs are run by using the security credentials of the user who created the job.</span></span> <span data-ttu-id="0e1df-106">Realice el procedimiento siguiente para crear un trabajo por lotes.</span><span class="sxs-lookup"><span data-stu-id="0e1df-106">Use the following procedure to create a batch job.</span></span> <span data-ttu-id="0e1df-107">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="0e1df-107">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-the-batch-job"></a><span data-ttu-id="0e1df-108">Crear el trabajo por lotes</span><span class="sxs-lookup"><span data-stu-id="0e1df-108">Create the batch job</span></span>
1. <span data-ttu-id="0e1df-109">Vaya a **Panel de navegación > Módulos > Administración del sistema > Consultas > Trabajos por lotes**.</span><span class="sxs-lookup"><span data-stu-id="0e1df-109">Go to **Navigation pane > Modules > System administration > Inquiries > Batch jobs**.</span></span>
2. <span data-ttu-id="0e1df-110">Haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="0e1df-110">Click **New**.</span></span>
3. <span data-ttu-id="0e1df-111">En el campo **Descripción del trabajo**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="0e1df-111">In the **Job description** field, type a value.</span></span>
4. <span data-ttu-id="0e1df-112">En el campo **Fecha/hora de inicio programada**, especifique una fecha y una hora.</span><span class="sxs-lookup"><span data-stu-id="0e1df-112">In the **Scheduled start date/time** field, enter a date and time.</span></span>
5. <span data-ttu-id="0e1df-113">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="0e1df-113">Click **Save**.</span></span>

## <a name="create-a-recurrence"></a><span data-ttu-id="0e1df-114">Crear una periodicidad</span><span class="sxs-lookup"><span data-stu-id="0e1df-114">Create a recurrence</span></span>
1. <span data-ttu-id="0e1df-115">En el panel de acciones, haga clic en **Trabajo por lotes**.</span><span class="sxs-lookup"><span data-stu-id="0e1df-115">On the Action Pane, click **Batch job**.</span></span>
2. <span data-ttu-id="0e1df-116">Haga clic en **Periodicidad**.</span><span class="sxs-lookup"><span data-stu-id="0e1df-116">Click **Recurrence**.</span></span> <span data-ttu-id="0e1df-117">Utilice estas opciones para especificar un intervalo y un patrón para la periodicidad.</span><span class="sxs-lookup"><span data-stu-id="0e1df-117">Use these options to enter a range and pattern for the recurrence.</span></span>  
3. <span data-ttu-id="0e1df-118">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0e1df-118">Click **OK**.</span></span>

## <a name="add-alerts"></a><span data-ttu-id="0e1df-119">Agregar alertas</span><span class="sxs-lookup"><span data-stu-id="0e1df-119">Add alerts</span></span>
1. <span data-ttu-id="0e1df-120">En el panel de acciones, haga clic en **Trabajo por lotes**.</span><span class="sxs-lookup"><span data-stu-id="0e1df-120">On the Action Pane, click **Batch job**.</span></span>
2. <span data-ttu-id="0e1df-121">Haga clic en **Alertas**.</span><span class="sxs-lookup"><span data-stu-id="0e1df-121">Click **Alerts**.</span></span> <span data-ttu-id="0e1df-122">Indique si desea que se envíen mensajes de alerta cuando finalice el trabajo por lotes, tenga un error o se cancele.</span><span class="sxs-lookup"><span data-stu-id="0e1df-122">Indicate if you want alert messages sent when the batch job ends, has an error, or is canceled.</span></span> <span data-ttu-id="0e1df-123">A continuación, especifique si desea que las alertas se muestren como mensajes emergentes.</span><span class="sxs-lookup"><span data-stu-id="0e1df-123">Then specify if you want the alerts to be displayed as pop-up messages.</span></span>   
3. <span data-ttu-id="0e1df-124">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0e1df-124">Click **OK**.</span></span>

## <a name="adjust-batch-job-status"></a><span data-ttu-id="0e1df-125">Ajustar estado del trabajo por lotes</span><span class="sxs-lookup"><span data-stu-id="0e1df-125">Adjust batch job status</span></span>
1. <span data-ttu-id="0e1df-126">Vaya **Administración del sistema > Consultas > Trabajos por lotes**.</span><span class="sxs-lookup"><span data-stu-id="0e1df-126">Go to **System administration > Inquiries > Batch jobs**.</span></span>
2. <span data-ttu-id="0e1df-127">Seleccione el trabajo por lotes adecuado.</span><span class="sxs-lookup"><span data-stu-id="0e1df-127">Select the appropriate batch job.</span></span>
3. <span data-ttu-id="0e1df-128">En el panel de acciones, haga clic en **Trabajo por lotes > Funciones > Cambiar estado**.</span><span class="sxs-lookup"><span data-stu-id="0e1df-128">On the Action Pane, click **Batch job > Functions > Change status**.</span></span>
4. <span data-ttu-id="0e1df-129">Seleccione el estado adecuado:</span><span class="sxs-lookup"><span data-stu-id="0e1df-129">Select the appropriate status:</span></span>
    - <span data-ttu-id="0e1df-130">**Retenido**: establezca el trabajo por lotes como **retenido** para que se retenga del programador de trabajos por lotes.</span><span class="sxs-lookup"><span data-stu-id="0e1df-130">**Withhold**: Set the batch job as **withhold** so it is withheld from the batch job scheduler.</span></span> <span data-ttu-id="0e1df-131">Equivalente a *detenido*.</span><span class="sxs-lookup"><span data-stu-id="0e1df-131">Equivalent to *stop*.</span></span>
    - <span data-ttu-id="0e1df-132">**En espera**: establezca el trabajo por lotes como **en espera** para que quede a la espera de ser recogido por el programador de trabajos por lotes.</span><span class="sxs-lookup"><span data-stu-id="0e1df-132">**Waiting**: Set the batch job as **waiting** so it is waiting to be picked up by the batch job scheduler.</span></span> <span data-ttu-id="0e1df-133">Equivalente a *en marcha*.</span><span class="sxs-lookup"><span data-stu-id="0e1df-133">Equivalent to *go*.</span></span>
5. <span data-ttu-id="0e1df-134">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0e1df-134">Click **OK**.</span></span>
