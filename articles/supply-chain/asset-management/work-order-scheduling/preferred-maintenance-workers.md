---
title: Configurar trabajadores de mantenimiento preferidos
description: En este tema se explica cómo configurar trabajadores de mantenimiento preferidos en Administración de activos.
author: josaw1
manager: AnnBe
ms.date: 08/19/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 8f26be81e7057d0cea1473d81452216251633ad9
ms.sourcegitcommit: f93ead945afe5ae18706c66bce6e64a6b57aac50
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/19/2019
ms.locfileid: "1887420"
---
# <a name="preferred-maintenance-workers"></a><span data-ttu-id="5cbac-103">Trabajadores de mantenimiento preferidos</span><span class="sxs-lookup"><span data-stu-id="5cbac-103">Preferred maintenance workers</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="5cbac-104">Puede crear una preferencia en cuanto a qué trabajadores de mantenimiento se asignan para completar órdenes de trabajo durante la programación de órdenes de trabajo.</span><span class="sxs-lookup"><span data-stu-id="5cbac-104">You can make a preference regarding which maintenance workers are allocated to complete work orders during work order scheduling.</span></span> <span data-ttu-id="5cbac-105">El uso de esta función es opcional, pero puede ayudarle a elegir al trabajador de mantenimiento más cualificado para que complete un trabajo en función de las aptitudes y competencias del trabajador.</span><span class="sxs-lookup"><span data-stu-id="5cbac-105">The use of this functionality is optional, but it can help you make a choice for the most qualified maintenance worker to complete a job, based on worker skills and competencies.</span></span> <span data-ttu-id="5cbac-106">Por lo tanto, durante la programación de una orden de trabajo, la configuración en **Trabajadores de mantenimiento preferidos** se utiliza para determinar si debe programarse un determinado trabajador o grupo de trabajadores de mantenimiento para una orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="5cbac-106">Therefore, during work order scheduling, the setup in **Preferred maintenance workers** is used to determine if a specific maintenance worker or worker group should be scheduled for a work order.</span></span> <span data-ttu-id="5cbac-107">Solo se programarán trabajadores de mantenimiento que estén disponibles en el momento de la programación.</span><span class="sxs-lookup"><span data-stu-id="5cbac-107">Only maintenance workers that are available at scheduling time will be scheduled.</span></span> <span data-ttu-id="5cbac-108">Si una configuración de trabajador de mantenimiento preferido coincide con una orden de trabajo durante la programación, pero el trabajador de mantenimiento está asignado a otros trabajos, la orden de trabajo se programará a otro trabajado de mantenimiento, en caso de que esté disponible.</span><span class="sxs-lookup"><span data-stu-id="5cbac-108">If a preferred maintenance worker setup matches a work order during scheduling, but the maintenance worker is allocated to other jobs, the work order will be scheduled to another, available, maintenance worker.</span></span>

<span data-ttu-id="5cbac-109">Para poder configurar trabajadores de mantenimiento preferidos, primero debe configurar los trabajadores y grupos de trabajadores de mantenimiento que deben estar disponibles para la selección.</span><span class="sxs-lookup"><span data-stu-id="5cbac-109">Before you can set up preferred maintenance workers, you must first set up the maintenance workers and worker groups that should be available for selection.</span></span> <span data-ttu-id="5cbac-110">Consulte [Trabajadores y grupos de trabajadores de mantenimiento](../setup-for-objects/workers-and-worker-groups.md) para ver una descripción acerca de cómo configurar trabajadores y grupos de trabajadores de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="5cbac-110">Refer to [Maintenance workers and worker groups](../setup-for-objects/workers-and-worker-groups.md) for a description on how to set up maintenance workers and worker groups.</span></span>

## <a name="set-up-preferred-workers"></a><span data-ttu-id="5cbac-111">Configurar trabajadores preferidos</span><span class="sxs-lookup"><span data-stu-id="5cbac-111">Set up preferred workers</span></span>

<span data-ttu-id="5cbac-112">Un trabajador o un grupo de trabajadores de mantenimiento preferido puede estar relacionado con un determinado</span><span class="sxs-lookup"><span data-stu-id="5cbac-112">A preferred maintenance worker or worker group can be related to a specific</span></span>

- <span data-ttu-id="5cbac-113">comercio</span><span class="sxs-lookup"><span data-stu-id="5cbac-113">trade</span></span>  
- <span data-ttu-id="5cbac-114">variante de tipo de trabajo de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="5cbac-114">maintenance job type variant</span></span>  
- <span data-ttu-id="5cbac-115">tipo de trabajo de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="5cbac-115">maintenance job type</span></span>  
- <span data-ttu-id="5cbac-116">categoría de tipo de trabajo de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="5cbac-116">maintenance job type category</span></span>  
- <span data-ttu-id="5cbac-117">activo</span><span class="sxs-lookup"><span data-stu-id="5cbac-117">asset</span></span>  
- <span data-ttu-id="5cbac-118">tipo de activo</span><span class="sxs-lookup"><span data-stu-id="5cbac-118">asset type</span></span>  

<span data-ttu-id="5cbac-119">o una combinación de dichas selecciones.</span><span class="sxs-lookup"><span data-stu-id="5cbac-119">or a combination of those selections.</span></span> <span data-ttu-id="5cbac-120">Cuantas más selecciones haga para el mismo registro, más específica será la configuración.</span><span class="sxs-lookup"><span data-stu-id="5cbac-120">The more selections you make for the same record, the more specific your setup will be.</span></span>

1. <span data-ttu-id="5cbac-121">Haga clic en **Administración de activos** > **Configuración** > **Trabajadores** > **Trabajadores de mantenimiento preferidos**.</span><span class="sxs-lookup"><span data-stu-id="5cbac-121">Click **Asset management** > **Setup** > **Workers** > **Preferred maintenance workers**.</span></span>

2. <span data-ttu-id="5cbac-122">Haga clic en **Nuevo** para crear un nuevo registro.</span><span class="sxs-lookup"><span data-stu-id="5cbac-122">Click **New** to create a new record.</span></span>

3. <span data-ttu-id="5cbac-123">Empiece por crear un trabajador de mantenimiento "predeterminado" o una configuración de un grupo de trabajadores que no tenga selecciones en los campos que se muestran en la lista de viñetas de abajo.</span><span class="sxs-lookup"><span data-stu-id="5cbac-123">Start by creating a "default" maintenance worker or worker group setup that has no selections in the fields shown in the bullet list above.</span></span> <span data-ttu-id="5cbac-124">Esto significa que solo crea una selección en el campo **Grupo de trabajadores de mantenimiento preferido** o en el campo **Trabajador de mantenimiento preferido**.</span><span class="sxs-lookup"><span data-stu-id="5cbac-124">This means that you only make a selection in the **Preferred maintenance worker group** field or the **Preferred maintenance worker** field.</span></span> <span data-ttu-id="5cbac-125">En la siguiente ilustración, verá un ejemplo en el primer registro en el que se selecciona "Solicitudes" como grupo de trabajadores de mantenimiento preferido.</span><span class="sxs-lookup"><span data-stu-id="5cbac-125">In the figure below, you see an example in the first record in which "Requests" is selected as preferred maintenance worker group.</span></span>

>[!NOTE]
><span data-ttu-id="5cbac-126">La configuración predeterminada se usará durante la programación de la orden de trabajo en caso de que no haya ninguna otra combinación más específica que coincida con el contenido de la orden de trabajo durante la programación de la orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="5cbac-126">The default setup will be used during work order scheduling in case no other, more specific, combination matches the contents of the work order during work order scheduling.</span></span>

4. <span data-ttu-id="5cbac-127">Repita el paso 2 para crear un nuevo registro.</span><span class="sxs-lookup"><span data-stu-id="5cbac-127">Repeat step 2 to create a new record.</span></span> <span data-ttu-id="5cbac-128">Haga las selecciones necesarias en función del nivel de detalle del trabajador o grupo de trabajadores preferido.</span><span class="sxs-lookup"><span data-stu-id="5cbac-128">Make the required selections, depending on the detail level for the preferred worker or worker group.</span></span> <span data-ttu-id="5cbac-129">*Ejemplo:* en la ilustración siguiente, en el sexto registro, el trabajador de mantenimiento Shawn Richardson es seleccionado como trabajador preferido.</span><span class="sxs-lookup"><span data-stu-id="5cbac-129">*Example:* In the figure below, in the sixth record, the maintenance worker Shawn Richardson is selected as preferred worker.</span></span> <span data-ttu-id="5cbac-130">Será seleccionado automáticamente durante la programación de una orden de trabajo que incluya el activo "CH-BP1-03-02" y el tipo de trabajo de mantenimiento "Evaluación de la instalación", si este está disponible a la hora programada.</span><span class="sxs-lookup"><span data-stu-id="5cbac-130">He will automatically be selected during scheduling of a work order that includes the asset "CH-BP1-03-02 and the maintennace job type "Facility assessment", if he is available at the scheduled time.</span></span>

>[!NOTE]
><span data-ttu-id="5cbac-131">Por lo general, cuando se selecciona un trabajador de mantenimiento preferido durante la programación de una orden de trabajo, la Administración de activos pasa por todos los registros **Trabajadores de mantenimiento preferidos** para comprobar si existe una coincidencia posible, comprobando siempre en primer lugar la combinación más específica.</span><span class="sxs-lookup"><span data-stu-id="5cbac-131">Generally, when a preferred maintenance worker is selected during work order scheduling, Asset Management goes through all **Preferred maintenance workers** records to check for a possible match, always checking the most specific combination first.</span></span> <span data-ttu-id="5cbac-132">Si no se encuentra ninguna coincidencia, se utiliza el registro "predeterminado" con una selección en el campo **Grupo de trabajadores de mantenimiento preferido** o en el campo **Trabajador de mantenimiento preferido**.</span><span class="sxs-lookup"><span data-stu-id="5cbac-132">If no match is found, the "default" record with a selection in either the **Preferred maintenance worker group** field or the **Preferred maintenance worker** field is used.</span></span>


![Figura 1](media/02-work-order-scheduling.png)

<span data-ttu-id="5cbac-134">También puede configurar los trabajadores responsables del mantenimiento que se pueden seleccionar cuando se crea una solicitud de mantenimiento o una orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="5cbac-134">You can also set up responsible maintenance workers who can be selected when a maintenance request or a work order is created.</span></span> <span data-ttu-id="5cbac-135">Si es necesario, puede editar la selección en **Todas las órdenes de trabajo** y **Todas las solicitudes de mantenimiento**.</span><span class="sxs-lookup"><span data-stu-id="5cbac-135">In **All work orders** and **All maintenance requests**, you can edit the selection, if required.</span></span> <span data-ttu-id="5cbac-136">Consulte [Trabajadores responsables del mantenimiento](../setup-for-maintenance-requests/responsible-workers.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="5cbac-136">Refer to [Responsible maintenance workers](../setup-for-maintenance-requests/responsible-workers.md) for more information.</span></span>

<span data-ttu-id="5cbac-137">Durante la programación de órdenes de trabajo, se calculan distintas puntuaciones para determinar qué trabajadores deben completar los trabajos relacionados con una orden de trabajo (esas puntuaciones se configuran en el vínculo **Parámetros de administración de activos** > **Programación de órdenes de trabajo**).</span><span class="sxs-lookup"><span data-stu-id="5cbac-137">During work order scheduling, different scores are calculated to determine which workers should complete the jobs related to a work order (those scores are set up in **Asset management parameters** > **Work order scheduling** link).</span></span> <span data-ttu-id="5cbac-138">Si dos o más trabajadores de mantenimiento preferidos o trabajadores responsables del mantenimiento obtienen la misma puntuación durante la programación de órdenes de trabajo, se selecciona a un trabajador al azar.</span><span class="sxs-lookup"><span data-stu-id="5cbac-138">If two or more preferred maintenance workers or responsible maintenance workers get the same score during work order scheduling, one worker is randomly selected.</span></span> <span data-ttu-id="5cbac-139">De lo contrario, se asignará siempre al trabajador con la puntuación más alta para que complete una orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="5cbac-139">Otherwise, it is always the worker with the highest score who is allocated to complete a work order.</span></span>

