--- 
title: Crear un trabajo por lotes
description: "Un trabajo por lotes es un grupo de tareas enviadas a una instancia de Application Object Server (AOS) para su procesamiento automático."
author: maertenm
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 55b153e6044f61f16e19ae0b264e3f23538e004a
ms.contentlocale: es-es
ms.lasthandoff: 05/08/2018

---
# <a name="create-a-batch-job"></a><span data-ttu-id="89093-103">Crear un trabajo por lotes</span><span class="sxs-lookup"><span data-stu-id="89093-103">Create a batch job</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="89093-104">Un trabajo por lotes es un grupo de tareas enviadas a una instancia de Application Object Server (AOS) para su procesamiento automático.</span><span class="sxs-lookup"><span data-stu-id="89093-104">A batch job is a group of tasks that are submitted to an Application Object Server (AOS) instance for automatic processing.</span></span> <span data-ttu-id="89093-105">Los trabajos por lotes se ejecutan mediante las credenciales de seguridad del usuario que creó el trabajo.</span><span class="sxs-lookup"><span data-stu-id="89093-105">Batch jobs are run by using the security credentials of the user who created the job.</span></span> <span data-ttu-id="89093-106">Realice el procedimiento siguiente para crear un trabajo por lotes.</span><span class="sxs-lookup"><span data-stu-id="89093-106">Use the following procedure to create a batch job.</span></span> <span data-ttu-id="89093-107">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="89093-107">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-the-batch-job"></a><span data-ttu-id="89093-108">Crear el trabajo por lotes</span><span class="sxs-lookup"><span data-stu-id="89093-108">Create the batch job</span></span>
1. <span data-ttu-id="89093-109">Vaya Administración del sistema > Consultas > Trabajos por lotes.</span><span class="sxs-lookup"><span data-stu-id="89093-109">Go to System administration > Inquiries > Batch jobs.</span></span>
2. <span data-ttu-id="89093-110">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="89093-110">Click New.</span></span>
3. <span data-ttu-id="89093-111">En el campo Descripción del trabajo, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="89093-111">In the Job description field, type a value.</span></span>
4. <span data-ttu-id="89093-112">En el campo Fecha/hora de inicio programada, especifique una fecha y una hora.</span><span class="sxs-lookup"><span data-stu-id="89093-112">In the Scheduled start date/time field, enter a date and time.</span></span>
5. <span data-ttu-id="89093-113">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="89093-113">Click Save.</span></span>

## <a name="create-a-recurrence"></a><span data-ttu-id="89093-114">Crear una periodicidad</span><span class="sxs-lookup"><span data-stu-id="89093-114">Create a recurrence</span></span>
1. <span data-ttu-id="89093-115">En el panel de acciones, haga clic en Trabajo por lotes.</span><span class="sxs-lookup"><span data-stu-id="89093-115">On the Action Pane, click Batch job.</span></span>
2. <span data-ttu-id="89093-116">Haga clic en Periodicidad.</span><span class="sxs-lookup"><span data-stu-id="89093-116">Click Recurrence.</span></span>
    * <span data-ttu-id="89093-117">Utilice estas opciones para especificar un intervalo y un patrón para la periodicidad.</span><span class="sxs-lookup"><span data-stu-id="89093-117">Use these options to enter a range and pattern for the recurrence.</span></span>  
3. <span data-ttu-id="89093-118">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="89093-118">Click OK.</span></span>

## <a name="add-alerts"></a><span data-ttu-id="89093-119">Agregar alertas</span><span class="sxs-lookup"><span data-stu-id="89093-119">Add alerts</span></span>
1. <span data-ttu-id="89093-120">En el panel de acciones, haga clic en Trabajo por lotes.</span><span class="sxs-lookup"><span data-stu-id="89093-120">On the Action Pane, click Batch job.</span></span>
2. <span data-ttu-id="89093-121">Haga clic en Alertas.</span><span class="sxs-lookup"><span data-stu-id="89093-121">Click Alerts.</span></span>
    * <span data-ttu-id="89093-122">Indique si desea que se envíen mensajes de alerta cuando finalice el trabajo por lotes, tenga un error o se cancele.</span><span class="sxs-lookup"><span data-stu-id="89093-122">Indicate if you want alert messages sent when the batch job ends, has an error, or is canceled.</span></span> <span data-ttu-id="89093-123">A continuación, especifique si desea que las alertas se muestren como mensajes emergentes.</span><span class="sxs-lookup"><span data-stu-id="89093-123">Then specify if you want the alerts to be displayed as pop-up messages.</span></span>   
3. <span data-ttu-id="89093-124">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="89093-124">Click OK.</span></span>


