---
title: Órdenes de trabajo creadas manualmente
description: En este tema se explica cómo crear órdenes de trabajo manualmente en Administración de activos.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
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
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 261448a134a7c1aacfbb4ea6f954ce03a63c23e2
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875881"
---
# <a name="manually-created-work-orders"></a><span data-ttu-id="db0ec-103">Órdenes de trabajo creadas manualmente</span><span class="sxs-lookup"><span data-stu-id="db0ec-103">Manually created work orders</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


<span data-ttu-id="db0ec-104">Puede crear órdenes de trabajo de manera manual de dos formas:</span><span class="sxs-lookup"><span data-stu-id="db0ec-104">You can create work orders manually in two ways:</span></span>

- <span data-ttu-id="db0ec-105">en **Todas las órdenes de trabajo** u **Órdenes de trabajo activas**</span><span class="sxs-lookup"><span data-stu-id="db0ec-105">in **All work orders** or **Active work orders**</span></span>  
- <span data-ttu-id="db0ec-106">en **Todas las solicitudes de mantenimiento** o **Solicitudes de mantenimiento activas** o **Mis solicitudes de mantenimiento de la ubicación técnica**.</span><span class="sxs-lookup"><span data-stu-id="db0ec-106">in **All maintenance requests** or **Active maintenance requests** or **My functional location maintenance requests**</span></span>  

## <a name="create-work-order"></a><span data-ttu-id="db0ec-107">Crear orden de trabajo</span><span class="sxs-lookup"><span data-stu-id="db0ec-107">Create work order</span></span>

1. <span data-ttu-id="db0ec-108">Haga clic en **Administración de activos** > **Común** > **Órdenes de trabajo** > **Todas las órdenes de trabajo** u **Órdenes de trabajo activas**.</span><span class="sxs-lookup"><span data-stu-id="db0ec-108">Click **Asset management** > **Common** > **Work orders** > **All work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="db0ec-109">Haga clic en el botón **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="db0ec-109">Click the **New** button.</span></span>

3. <span data-ttu-id="db0ec-110">En el desplegable **Crear orden de trabajo**, seleccione un tipo de orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="db0ec-110">In the **Create work order** drop-down, select a work order type.</span></span>

4. <span data-ttu-id="db0ec-111">Si es necesario, seleccione una descripción.</span><span class="sxs-lookup"><span data-stu-id="db0ec-111">If required, select a description.</span></span>

5. <span data-ttu-id="db0ec-112">Seleccione el activo para la orden de trabajo junto con un tipo de trabajo de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="db0ec-112">Select the asset for the work order as well as a maintenance job type.</span></span>

>[!NOTE]
><span data-ttu-id="db0ec-113">Al seleccionar un activo, puede que estén disponibles tres pestañas: la pestaña **Mis activos** contiene los activos relacionados con las ubicaciones técnicas a las que usted (el trabajador conectado al sistema) puede ser asignado (se configura en [Trabajadores y grupos de trabajadores de mantenimiento](../setup-for-objects/workers-and-worker-groups.md)).</span><span class="sxs-lookup"><span data-stu-id="db0ec-113">When you select an asset, three tabs may be available: The **My assets** tab contains assets related to the functional locations to which you (the worker who is logged on the system) may be allocated (set up in [Maintenance workers and worker groups](../setup-for-objects/workers-and-worker-groups.md)).</span></span> <span data-ttu-id="db0ec-114">Si no se ha configurado ninguna ubicación técnica para un trabajador en [Trabajadores y grupos de trabajadores de mantenimiento](../setup-for-objects/workers-and-worker-groups.md), la pestaña **Mis activos** no estará visible.</span><span class="sxs-lookup"><span data-stu-id="db0ec-114">If no functional locations are set up on a worker in [Maintenance workers and worker groups](../setup-for-objects/workers-and-worker-groups.md), the **My assets** tab will not be visible.</span></span> <span data-ttu-id="db0ec-115">La pestaña **Activos activos** contiene una lista de todos los activos cuyo estado de ciclo de vida es "Activo".</span><span class="sxs-lookup"><span data-stu-id="db0ec-115">The **Active assets** tab contains a list of all assets with asset lifecycle state "Active".</span></span> <span data-ttu-id="db0ec-116">La pestaña **Vista de activos** muestra una vista de árbol de las ubicaciones técnicas y los activos instalados en esas ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="db0ec-116">The **Asset view** tab displays a tree view of functional locations and assets installed on those locations.</span></span>

6. <span data-ttu-id="db0ec-117">Si es necesario, seleccione **Variante de tipo de trabajo de mantenimiento** y **Comercio**.</span><span class="sxs-lookup"><span data-stu-id="db0ec-117">If required, select **Maintenance job type variant** and **Trade**.</span></span>

7. <span data-ttu-id="db0ec-118">Si es necesario, puede cambiar el nivel de servicio de la orden de trabajo en el campo **Nivel de servicio**.</span><span class="sxs-lookup"><span data-stu-id="db0ec-118">If required, you can change the work order service level in the **Service level** field.</span></span>

8. <span data-ttu-id="db0ec-119">Seleccione las fechas iniciales y finales previstas en los campos relacionados.</span><span class="sxs-lookup"><span data-stu-id="db0ec-119">Select expected start and end dates in the related fields.</span></span>

9. <span data-ttu-id="db0ec-120">Haga clic en **Aceptar** para crear una nueva orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="db0ec-120">Click **OK** to create a new work order.</span></span>

10. <span data-ttu-id="db0ec-121">Si es necesario, edite la orden de trabajo en **Todas las órdenes de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="db0ec-121">Edit the work order in **All work orders**, if required.</span></span>

- <span data-ttu-id="db0ec-122">En **Todas las órdenes de trabajo**, puede agregar varios activos a una orden de trabajo en la vista de detalles agregando líneas en la ficha desplegable **Trabajos de mantenimiento de órdenes de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="db0ec-122">In **All work orders**, You can add several assets to a work order in Details view by adding lines on the **Work order maintenance jobs** FastTab.</span></span> <span data-ttu-id="db0ec-123">En el activo, solo puede seleccionar los tipos de trabajo de mantenimiento que se definen en el tipo de activo seleccionando para el activo.</span><span class="sxs-lookup"><span data-stu-id="db0ec-123">On an asset, you can only select the maintenance job types that are defined on the asset type selected for the asset.</span></span>  
- <span data-ttu-id="db0ec-124">Si ha cambiado el nivel de servicio o la importancia de un activo después de que lo haya utilizado en una orden de trabajo (consulte [Niveles de servicio de activos](../setup-for-objects/object-priorities.md) e [Importancias de activos](../setup-for-objects/object-criticalities.md)), el nivel de servicio o la importancia en la orden de trabajo no se actualiza.</span><span class="sxs-lookup"><span data-stu-id="db0ec-124">If you have changed an asset service level or an asset criticality after you have used them on a work order (refer to [Asset service levels](../setup-for-objects/object-priorities.md) and [Asset criticalities](../setup-for-objects/object-criticalities.md)), the service level or criticality on the work order is not updated accordingly.</span></span>
- <span data-ttu-id="db0ec-125">La importancia de una orden de trabajo se vuelve a calcular cada vez que se agrega o se elimina una línea de la orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="db0ec-125">Criticality on a work order is re-calculated each time a work order line is added or deleted on the work order.</span></span>
- <span data-ttu-id="db0ec-126">En la vista de detalles **Todas las órdenes de trabajo** > vista **Encabezado** > ficha desplegable **Programar**, puede seleccionar un trabajador o grupo de trabajadores responsable del mantenimiento en los campos **Grupo responsable** o **Responsable**.</span><span class="sxs-lookup"><span data-stu-id="db0ec-126">In **All work orders** Details view > **Header** view > **Schedule** FastTab, you can select a responsible maintenance worker group or a responsible maintenance worker in the **Responsible group** or **Responsible** fields.</span></span> <span data-ttu-id="db0ec-127">Esta configuración se puede cambiar siempre que la orden de trabajo esté activa, por ejemplo, cuando cambia el estado del ciclo de vida de la orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="db0ec-127">These settings can be changed as long as the work order is active, for example, when the work order lifecycle state changes.</span></span> <span data-ttu-id="db0ec-128">La selección automática realizada durante la creación de la orden de trabajo se basa en la configuración en **Trabajadores responsables del mantenimiento**.</span><span class="sxs-lookup"><span data-stu-id="db0ec-128">The automatic selection made during work order creation is based on the setup in **Responsible maintenance workers**.</span></span> <span data-ttu-id="db0ec-129">Si agrega o elimina tareas de una orden de trabajo después de haber creado una orden de trabajo, y los campos **Grupo responsable** y **Responsable** están en blanco cuando actualiza la orden de trabajo, la Administración de activos busca una posible coincidencia en el formulario de configuración para un trabajador o grupo de trabajadores responsable del mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="db0ec-129">If you add or remove work order jobs after you have created a work order, and the **Responsible group** field and the **Responsible** field are blank when you update the work order, Asset Management searches for a possible match in the setup form for a responsible maintenance worker group or a responsible maintenance worker.</span></span> <span data-ttu-id="db0ec-130">Si los campos **Grupo responsable** o **Responsable** ya están rellenados cuando actualice la orden de trabajo, no se realiza ningún cambio.</span><span class="sxs-lookup"><span data-stu-id="db0ec-130">If the **Responsible group** field or the **Responsible** field is already filled out when you update the work order, no changes are made.</span></span> 

- <span data-ttu-id="db0ec-131">En **Estado del mantenimiento**, puede hacer un cálculo para obtener una visión general de la carga de trabajo relativa a las órdenes de trabajo entrantes y completadas.</span><span class="sxs-lookup"><span data-stu-id="db0ec-131">In **Maintenance status**, you can make a calculation to get an overview of workload regarding incoming and completed work orders.</span></span>  

- <span data-ttu-id="db0ec-132">En la ficha desplegable **Detalles de línea**, utilice los campos **Latitud** y **Longitud** para agregar coordenadas geográficas para el activo seleccionado en la tarea de la orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="db0ec-132">On the **Line details** FastTab, use the **Latitude** and **Longitude** fields to add geographic coordinates for the asset selected on the work order job.</span></span>  

## <a name="create-related-work-order"></a><span data-ttu-id="db0ec-133">Crear orden de trabajo relacionada</span><span class="sxs-lookup"><span data-stu-id="db0ec-133">Create related work order</span></span>

<span data-ttu-id="db0ec-134">Puede crear una orden de trabajo relacionada con una orden de trabajo existente si, por ejemplo, desea trabajar con órdenes de trabajo principales y secundarias.</span><span class="sxs-lookup"><span data-stu-id="db0ec-134">You can create a related work order to an existing work order if, for example, you want to work with primary and secondary work orders.</span></span> <span data-ttu-id="db0ec-135">Una nueva orden de trabajo se basa en una tarea de la orden de trabajo a partir de una orden de trabajo existente.</span><span class="sxs-lookup"><span data-stu-id="db0ec-135">A new work order is based on a work order job from an existing work order.</span></span>

1. <span data-ttu-id="db0ec-136">Haga clic en **Administración de activos** > **Común** > **Órdenes de trabajo** > **Todas las órdenes de trabajo** u **Órdenes de trabajo activas**.</span><span class="sxs-lookup"><span data-stu-id="db0ec-136">Click **Asset management** > **Common** > **Work orders** > **All work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="db0ec-137">Seleccione la orden de trabajo para la que desea crear una orden de trabajo relacionada.</span><span class="sxs-lookup"><span data-stu-id="db0ec-137">Select the work order for which you want to make a related work order.</span></span>

3. <span data-ttu-id="db0ec-138">Haga clic en **Orden de trabajo relacionada**.</span><span class="sxs-lookup"><span data-stu-id="db0ec-138">Click **Related work order**.</span></span>

4. <span data-ttu-id="db0ec-139">En el cuadro de diálogo desplegable **Crear orden de trabajo relacionada**, seleccione la orden de trabajo para la que desea crear una orden de trabajo relacionada en el campo **Tarea de orden de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="db0ec-139">In the **Create related work order** drop-down dialog, select the work order job for which you want to create a related work order in the **Work order job** field.</span></span>

5. <span data-ttu-id="db0ec-140">Seleccione un tipo de trabajo de mantenimiento en el campo **Tipo de trabajo de mantenimiento** y, si es necesario, una variante de tipo de trabajo de mantenimiento relacionada y un comercio en los campos **Variante de tipo de trabajo de mantenimiento** y **Comercio**.</span><span class="sxs-lookup"><span data-stu-id="db0ec-140">Select a maintenance job type in the **Maintenance job type** field and, if required, a related maintenance job type variant and trade in the **Maintenance job type variant** and **Trade** fields.</span></span>

6. <span data-ttu-id="db0ec-141">Si se trata de la primera orden de trabajo relacionada que crea, haga clic en el botón de opción **Nueva orden de trabajado**.</span><span class="sxs-lookup"><span data-stu-id="db0ec-141">If this is the first related work order you make, click the **New work order** radio button.</span></span>

7. <span data-ttu-id="db0ec-142">Seleccione una **Tipo de orden de trabajo** y una **Descripción** en los campos relacionados.</span><span class="sxs-lookup"><span data-stu-id="db0ec-142">Select a **Work order type** and a **Description** in the related fields.</span></span>

8. <span data-ttu-id="db0ec-143">Si es necesario, cambie el nivel de servicio de la orden de trabajo en el campo **Nivel de servicio**.</span><span class="sxs-lookup"><span data-stu-id="db0ec-143">If required, change the work order service level in the **Service level** field.</span></span>

9. <span data-ttu-id="db0ec-144">Inserte las fechas iniciales y finales previstas en los campos relacionados.</span><span class="sxs-lookup"><span data-stu-id="db0ec-144">Insert expected start and end dates in the related fields.</span></span>

10. <span data-ttu-id="db0ec-145">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="db0ec-145">Click **OK**.</span></span> <span data-ttu-id="db0ec-146">La nueva orden de trabajo relacionada se muestra en la lista **Todas las órdenes de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="db0ec-146">The new related work order is shown in the **All work orders** list.</span></span>

11. <span data-ttu-id="db0ec-147">Si crea una orden de trabajo relacionada en una orden de trabajo que ya tiene órdenes de trabajo relacionadas, puede agregar una tarea de orden de trabajo a una orden de trabajo ya relacionada.</span><span class="sxs-lookup"><span data-stu-id="db0ec-147">If you create a related work order on a work order that already has related work orders, you can add the work order job to an already related work order.</span></span> <span data-ttu-id="db0ec-148">Para ello, haga clic en el botón de opción **Agregar a orden de trabajo relacionada** en el paso 6.</span><span class="sxs-lookup"><span data-stu-id="db0ec-148">This is done by clicking the **Add to related work order** radio button in step 6.</span></span> <span data-ttu-id="db0ec-149">A continuación, seleccione la orden de trabajo relacionada a la que desea agregar una nueva tarea de orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="db0ec-149">Then you select the related work order to which you want to add a new work order job.</span></span> <span data-ttu-id="db0ec-150">Edite los campos **Nivel de servicio**, **Inicio previsto** y **Finalización prevista**, según sea necesario, y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="db0ec-150">Edit the **Service level**, **Expected start**, and **Expected end** fields, as required, and click **OK**.</span></span> <span data-ttu-id="db0ec-151">La orden de trabajo se agrega a la orden de trabajo relacionada que ya existe.</span><span class="sxs-lookup"><span data-stu-id="db0ec-151">The work order job is added to the existing related work order.</span></span>


![Figura 1](media/03-work-orders.png)

<span data-ttu-id="db0ec-153">**Nota**: si ha configurado una máscara de orden de trabajo relacionada en el vínculo **Parámetros de administración de activos** > **Órdenes de trabajo** > campo **Máscara de orden de trabajo relacionada**, los id. de orden de trabajo se crearán de acuerdo con la configuración de la máscara.</span><span class="sxs-lookup"><span data-stu-id="db0ec-153">**Note:** If you have set up a related work order mask in **Asset management parameters** > **Work orders** link > **Related work order mask** field, work order IDs will be created in accordance with the mask setup.</span></span> <span data-ttu-id="db0ec-154">Si no se ha configurado ninguna máscara de orden de trabajo relacionada, se utilizará el siguiente id. de orden de trabajo disponible para las órdenes de trabajo relacionadas.</span><span class="sxs-lookup"><span data-stu-id="db0ec-154">If no related work order mask is set up, the next available work order ID will be used for related work orders.</span></span>

## <a name="copy-work-order"></a><span data-ttu-id="db0ec-155">Copiar orden de trabajo</span><span class="sxs-lookup"><span data-stu-id="db0ec-155">Copy work order</span></span>

<span data-ttu-id="db0ec-156">Es posible crear rápidamente una nueva orden de trabajo a partir de una orden de trabajo existente.</span><span class="sxs-lookup"><span data-stu-id="db0ec-156">It is possible to quickly create a new work order from an existing work order.</span></span> <span data-ttu-id="db0ec-157">Esta forma de trabajar con órdenes de trabajo es diferente a la de crear órdenes de trabajo basadas en planes de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="db0ec-157">This way of working with work orders is different from creating work orders based on maintenance plans.</span></span> <span data-ttu-id="db0ec-158">Resulta útil si, por ejemplo, tiene una orden de trabajo que contiene muchas tareas con distintas tareas en diferentes activos que se deben completar a intervalos periódicos.</span><span class="sxs-lookup"><span data-stu-id="db0ec-158">It is useful if, for example, you have a work order containing many work order jobs with various jobs on different assets that should be completed at regular intervals.</span></span>

1. <span data-ttu-id="db0ec-159">Haga clic en **Administración de activos** > **Común** > **Órdenes de trabajo** > **Todas las órdenes de trabajo** u **Órdenes de trabajo activas**.</span><span class="sxs-lookup"><span data-stu-id="db0ec-159">Click **Asset management** > **Common** > **Work orders** > **All work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="db0ec-160">Seleccione la orden de trabajo desde la que desea copiar el contenido.</span><span class="sxs-lookup"><span data-stu-id="db0ec-160">Select the work order from which you want to copy content.</span></span>

3. <span data-ttu-id="db0ec-161">Haga clic en **Copiar orden de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="db0ec-161">Click **Copy work order**.</span></span> <span data-ttu-id="db0ec-162">Se muestra la configuración de la orden de trabajo desde la orden de trabajo seleccionada.</span><span class="sxs-lookup"><span data-stu-id="db0ec-162">The work order setup from the selected work order is shown.</span></span> <span data-ttu-id="db0ec-163">Si es necesario, puede editar algunos campos.</span><span class="sxs-lookup"><span data-stu-id="db0ec-163">If required, you can edit some of the fields.</span></span>

4. <span data-ttu-id="db0ec-164">Haga clic en **Aceptar** para crear la nueva orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="db0ec-164">Click **OK** to create the new work order.</span></span>

5. <span data-ttu-id="db0ec-165">Si es necesario, edite la orden de trabajo en **Todas las órdenes de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="db0ec-165">Edit the work order in **All work orders**, if required.</span></span>

>[!NOTE]
><span data-ttu-id="db0ec-166">Cuando se crea la nueva orden de trabajo, alguna información se copia directamente desde la orden de trabajo existente.</span><span class="sxs-lookup"><span data-stu-id="db0ec-166">When the new work order is created, some information is copied directly from the existing work order.</span></span> <span data-ttu-id="db0ec-167">La información acerca de previsiones, herramientas, listas de comprobación de mantenimiento, ubicación técnica, direcciones y programación no se copia, pero se inicializa desde la configuración actual en Administración de activos.</span><span class="sxs-lookup"><span data-stu-id="db0ec-167">Information regarding forecasts, tools, maintenance checklists, functional location, addresses, and scheduling is not copied, but initialized from the current setup in Asset Management.</span></span> <span data-ttu-id="db0ec-168">Esto significa que si se hicieron cambios en esos datos desde el momento de la creación de la primera orden de trabajo hasta el momento en que hizo una copia de la orden de trabajo, esos cambios se incluyen en la nueva orden de trabajo que ha creado.</span><span class="sxs-lookup"><span data-stu-id="db0ec-168">This means that if changes were made in those data from the time of creation of the first work order until the time you made a copy of the work order, those changes are included in the new work order you have created.</span></span> <span data-ttu-id="db0ec-169">Los ejemplos son cambios en las previsiones o listas de comprobación de mantenimiento actualizadas.</span><span class="sxs-lookup"><span data-stu-id="db0ec-169">Examples are changes in forecasts or updated maintenance checklists.</span></span>


![Figura 2](media/04-work-orders.png)


## <a name="create-work-order-based-on-a-maintenance-request"></a><span data-ttu-id="db0ec-171">Crear una orden de trabajo basada en una solicitud de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="db0ec-171">Create work order based on a maintenance request</span></span>

1. <span data-ttu-id="db0ec-172">Haga clic en **Administración de activos** > **Común** > **Solicitudes de mantenimiento** > **Todas las solicitudes de mantenimiento** o **Solicitudes de mantenimiento activas**.</span><span class="sxs-lookup"><span data-stu-id="db0ec-172">Click **Asset management** > **Common** > **Maintenance requests** > **All maintenance requests** or **Active maintenance requests**.</span></span>

2. <span data-ttu-id="db0ec-173">Seleccione las solicitudes de mantenimiento para las que desea crear una orden de trabajo y haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="db0ec-173">Select the maintenance request for which you want to create a work order, and click **Edit**.</span></span>

3. <span data-ttu-id="db0ec-174">En **Todas las solicitudes**, haga clic en **Orden de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="db0ec-174">In **All requests**, click **Work order**.</span></span>

4. <span data-ttu-id="db0ec-175">Rellene el desplegable **Orden de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="db0ec-175">Fill out the **Work order** drop-down.</span></span> <span data-ttu-id="db0ec-176">Si se ha seleccionado un tipo de trabajo de mantenimiento en la solicitud de mantenimiento, puede seleccionar otro tipo de trabajo de mantenimiento, si es necesario, al crear la orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="db0ec-176">If a maintenance job type has been selected in the maintenance request, you are able to select another maintenance job type, if required, when you create the work order.</span></span>

5. <span data-ttu-id="db0ec-177">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="db0ec-177">Click **OK**.</span></span> <span data-ttu-id="db0ec-178">Verá un mensaje que le informa de que se ha creado la orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="db0ec-178">You will see a message informing you that the work order has been created.</span></span>

6. <span data-ttu-id="db0ec-179">Si desea ver las órdenes de trabajo que están conectadas a una solicitud de mantenimiento, seleccione la solicitud de mantenimiento en las listas **Todas las solicitudes de mantenimiento** o **Solicitudes de mantenimiento activa** y haga clic en el botón **Órdenes de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="db0ec-179">If you want to see which work orders are connected to a maintenance request, select the maintenance request in the **All maintenance requests** or **Active maintenance requests** lists, and click the **Work orders** button.</span></span>


![Figura 3](media/05-work-orders.png)


>[!NOTE]
><span data-ttu-id="db0ec-181">Las órdenes de trabajo también se pueden crear automáticamente programando tareas del plan de mantenimiento, o bien configurando "Crear automáticamente" planes de mantenimiento o rondas de mantenimiento en un activo.</span><span class="sxs-lookup"><span data-stu-id="db0ec-181">Work orders can also be created automatically by scheduling maintenance plan jobs, or by setting up "Auto create" maintenance plans or maintenance rounds on an asset.</span></span> <span data-ttu-id="db0ec-182">Las órdenes de trabajo creadas a partir de solicitudes de mantenimiento en **Programa de mantenimiento** se crean con los tipos de trabajo de mantenimiento seleccionados en las solicitudes de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="db0ec-182">Work orders created from maintenance requests in **Maintenance schedule** are created with the maintenance job types selected in the maintenance requests.</span></span>

