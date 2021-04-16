---
title: Configurar trabajadores de mantenimiento preferidos
description: En este tema se explica cómo configurar trabajadores de mantenimiento preferidos en Administración de activos.
author: johanhoffmann
ms.date: 08/19/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetWorkerPreferred
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 5b044e4616555559be51b0846327b1d55bfe47b3
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5822548"
---
# <a name="set-up-preferred-maintenance-workers"></a><span data-ttu-id="89264-103">Configurar trabajadores de mantenimiento preferidos</span><span class="sxs-lookup"><span data-stu-id="89264-103">Set up preferred maintenance workers</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="89264-104">Durante la programación de la orden de trabajo, puede crear una preferencia en cuanto a qué trabajador o grupo de trabajadores de mantenimiento se asigna para completar la orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="89264-104">During work order scheduling, you can make a preference regarding which maintenance worker or worker group is allocated to complete the work order.</span></span> <span data-ttu-id="89264-105">El uso de esta función es opcional, pero puede ayudarle a elegir al trabajador de mantenimiento más cualificado para que complete un trabajo en función de las aptitudes y competencias del trabajador.</span><span class="sxs-lookup"><span data-stu-id="89264-105">The use of this functionality is optional, but it can help you make a choice for the most qualified maintenance worker to complete a job, based on worker skills and competencies.</span></span> <span data-ttu-id="89264-106">Solo se programarán trabajadores de mantenimiento que estén disponibles en el momento de la programación.</span><span class="sxs-lookup"><span data-stu-id="89264-106">Only maintenance workers that are available at scheduling time will be scheduled.</span></span> <span data-ttu-id="89264-107">Si una configuración de trabajador de mantenimiento preferido coincide con una orden de trabajo durante la programación, pero el trabajador de mantenimiento está asignado a otros trabajos, la orden de trabajo se programará a otro trabajado de mantenimiento, en caso de que esté disponible.</span><span class="sxs-lookup"><span data-stu-id="89264-107">If a preferred maintenance worker setup matches a work order during scheduling, but the maintenance worker is allocated to other jobs, the work order will be scheduled to another available maintenance worker.</span></span>

<span data-ttu-id="89264-108">Para poder configurar trabajadores de mantenimiento preferidos, primero debe configurar los trabajadores y los grupos de trabajadores de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="89264-108">Before you can set up preferred maintenance workers, you must first set up the maintenance workers and worker groups.</span></span> <span data-ttu-id="89264-109">Para obtener una descripción sobre cómo configurar los trabajadores y grupos de trabajadores de mantenimiento, consulte [Trabajadores y grupos de trabajadores de mantenimiento](../setup-for-objects/workers-and-worker-groups.md).</span><span class="sxs-lookup"><span data-stu-id="89264-109">For a description about how to set up maintenance workers and worker groups, see to [Maintenance workers and worker groups](../setup-for-objects/workers-and-worker-groups.md).</span></span>

## <a name="set-up-preferred-workers"></a><span data-ttu-id="89264-110">Configurar trabajadores preferidos</span><span class="sxs-lookup"><span data-stu-id="89264-110">Set up preferred workers</span></span>

<span data-ttu-id="89264-111">Un trabajador o un grupo de trabajadores de mantenimiento preferido puede estar relacionado con uno o varios de los siguientes:</span><span class="sxs-lookup"><span data-stu-id="89264-111">A preferred maintenance worker or worker group can be related to one or more of the following:</span></span>

- <span data-ttu-id="89264-112">comercio</span><span class="sxs-lookup"><span data-stu-id="89264-112">trade</span></span>  
- <span data-ttu-id="89264-113">variante de tipo de trabajo de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="89264-113">maintenance job type variant</span></span>  
- <span data-ttu-id="89264-114">tipo de trabajo de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="89264-114">maintenance job type</span></span>  
- <span data-ttu-id="89264-115">categoría de tipo de trabajo de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="89264-115">maintenance job type category</span></span>  
- <span data-ttu-id="89264-116">activo</span><span class="sxs-lookup"><span data-stu-id="89264-116">asset</span></span>  
- <span data-ttu-id="89264-117">tipo de activo</span><span class="sxs-lookup"><span data-stu-id="89264-117">asset type</span></span>  

<span data-ttu-id="89264-118">Cuantas más selecciones haga para el mismo registro, más específica será la configuración.</span><span class="sxs-lookup"><span data-stu-id="89264-118">The more selections you make for the same record, the more specific your setup will be.</span></span>

1. <span data-ttu-id="89264-119">Haga clic en **Administración de activos** > **Configuración** > **Trabajadores** > **Trabajadores de mantenimiento preferidos**.</span><span class="sxs-lookup"><span data-stu-id="89264-119">Click **Asset management** > **Setup** > **Workers** > **Preferred maintenance workers**.</span></span>

2. <span data-ttu-id="89264-120">Haga clic en **Nuevo** para crear un nuevo registro.</span><span class="sxs-lookup"><span data-stu-id="89264-120">Click **New** to create a new record.</span></span>

3. <span data-ttu-id="89264-121">Empiece con la creación de un trabajador o un grupo de trabajadores "predeterminado".</span><span class="sxs-lookup"><span data-stu-id="89264-121">Start by creating a "default" maintenance worker or worker group.</span></span> <span data-ttu-id="89264-122">Esto significa que solo crea una selección en el campo **Grupo de trabajadores de mantenimiento preferido** o en el campo **Trabajador de mantenimiento preferido**.</span><span class="sxs-lookup"><span data-stu-id="89264-122">This means that you only make a selection in the **Preferred maintenance worker group** field or the **Preferred maintenance worker** field.</span></span> <span data-ttu-id="89264-123">En la siguiente captura de pantalla, verá un ejemplo en el primer registro en el que se selecciona "Solicitudes" como **grupo de trabajadores de mantenimiento preferido**.</span><span class="sxs-lookup"><span data-stu-id="89264-123">In the screenshot below, you see an example in the first record in which "Requests" is selected as **Preferred maintenance worker group**.</span></span>

    [!NOTE] <span data-ttu-id="89264-124">La configuración predeterminada se usará durante la programación de la orden de trabajo si hay ninguna otra combinación más específica que coincida con el contenido de la orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="89264-124">The default setup will be used during work order scheduling if no other, more specific, combination matches the contents of the work order.</span></span>

4. <span data-ttu-id="89264-125">Repita el paso 2 para crear un nuevo registro.</span><span class="sxs-lookup"><span data-stu-id="89264-125">Repeat step 2 to create a new record.</span></span> <span data-ttu-id="89264-126">Haga las selecciones necesarias en función del nivel de detalle del trabajador o grupo de trabajadores preferido.</span><span class="sxs-lookup"><span data-stu-id="89264-126">Make the required selections, depending on the detail level for the preferred worker or worker group.</span></span> 

    <span data-ttu-id="89264-127">*Ejemplo:* en la captura de pantalla siguiente, en el sexto registro, el trabajador de mantenimiento Shawn Richardson es seleccionado como trabajador preferido.</span><span class="sxs-lookup"><span data-stu-id="89264-127">*Example:* In the screenshot below, in the sixth record, the maintenance worker Shawn Richardson is selected as preferred worker.</span></span> <span data-ttu-id="89264-128">Será seleccionado automáticamente durante la programación de una orden de trabajo que incluya el activo "CH-BP1-03-02" y el tipo de trabajo de mantenimiento "Evaluación de la instalación", si este está disponible a la hora programada.</span><span class="sxs-lookup"><span data-stu-id="89264-128">He will automatically be selected during scheduling of a work order that includes the asset "CH-BP1-03-02 and the maintenance job type "Facility assessment", if he is available at the scheduled time.</span></span>

    [!NOTE] <span data-ttu-id="89264-129">Por lo general, cuando se selecciona un trabajador de mantenimiento preferido durante la programación de una orden de trabajo, la Administración de activos pasa por todos los registros **Trabajadores de mantenimiento preferidos** para comprobar si existe una coincidencia posible, comprobando siempre en primer lugar la combinación más específica.</span><span class="sxs-lookup"><span data-stu-id="89264-129">Generally, when a preferred maintenance worker is selected during work order scheduling, Asset Management goes through all **Preferred maintenance workers** records to check for a possible match, always checking the most specific combination first.</span></span> <span data-ttu-id="89264-130">Si no se encuentra ninguna coincidencia, se utiliza el registro "predeterminado" con una selección en el campo **Grupo de trabajadores de mantenimiento preferido** o en el campo **Trabajador de mantenimiento preferido**.</span><span class="sxs-lookup"><span data-stu-id="89264-130">If no match is found, the "default" record with a selection in either the **Preferred maintenance worker group** field or the **Preferred maintenance worker** field is used.</span></span>

![Figura 1](media/02-work-order-scheduling.png)

<span data-ttu-id="89264-132">También puede configurar los trabajadores *responsables* del mantenimiento que se pueden seleccionar cuando se crea una solicitud de mantenimiento o una orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="89264-132">You can also set up *responsible* maintenance workers who can be selected when a maintenance request or a work order is created.</span></span> <span data-ttu-id="89264-133">Puede editar la selección en **Todas las órdenes de trabajo** y **Todas las solicitudes de mantenimiento**.</span><span class="sxs-lookup"><span data-stu-id="89264-133">You can edit the selection in **All work orders** and **All maintenance requests**, if required.</span></span> <span data-ttu-id="89264-134">Para obtener más información, consulte [Trabajadores responsables del mantenimiento](../setup-for-maintenance-requests/responsible-workers.md).</span><span class="sxs-lookup"><span data-stu-id="89264-134">For more information, see [Responsible maintenance workers](../setup-for-maintenance-requests/responsible-workers.md).</span></span>

<span data-ttu-id="89264-135">Durante la programación de órdenes de trabajo, se calculan distintas puntuaciones para determinar qué trabajadores deben completar los trabajos relacionados con una orden de trabajo (esas puntuaciones se configuran en el vínculo **Parámetros de administración de activos** > **Programación de órdenes de trabajo**).</span><span class="sxs-lookup"><span data-stu-id="89264-135">During work order scheduling, different scores are calculated to determine which workers should complete the jobs related to a work order (those scores are set up in **Asset management parameters** > **Work order scheduling** link).</span></span> <span data-ttu-id="89264-136">Si dos o más trabajadores de mantenimiento preferidos o trabajadores responsables del mantenimiento obtienen la misma puntuación durante la programación de órdenes de trabajo, se selecciona a un trabajador al azar.</span><span class="sxs-lookup"><span data-stu-id="89264-136">If two or more preferred maintenance workers or responsible maintenance workers get the same score during work order scheduling, one worker is randomly selected.</span></span> <span data-ttu-id="89264-137">De lo contrario, se asignará siempre al trabajador con la puntuación más alta para que complete una orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="89264-137">Otherwise, it is always the worker with the highest score who is allocated to complete a work order.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]