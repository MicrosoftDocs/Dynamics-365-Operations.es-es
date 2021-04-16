---
title: Órdenes de trabajo creadas manualmente
description: En este tema se explica cómo crear órdenes de trabajo manualmente en Administración de activos.
author: johanhoffmann
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetWorkOrderTableCreateRelated, EntAssetWorkOrderTableCreate, EntAssetWorkOrderTableCopy
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 8962cbbc8f413093eef0fb3783aa6ced22f7bc2d
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5839568"
---
# <a name="manually-created-work-orders"></a><span data-ttu-id="fe515-103">Órdenes de trabajo creadas manualmente</span><span class="sxs-lookup"><span data-stu-id="fe515-103">Manually created work orders</span></span>

[!include [banner](../../includes/banner.md)]


<span data-ttu-id="fe515-104">Puede crear órdenes de trabajo de manera manual de dos formas:</span><span class="sxs-lookup"><span data-stu-id="fe515-104">You can create work orders manually in two ways:</span></span>

- <span data-ttu-id="fe515-105">En **Todas las órdenes de trabajo** o la página **Órdenes de trabajo activas**</span><span class="sxs-lookup"><span data-stu-id="fe515-105">On the **All work orders** or **Active work orders** page</span></span> 
- <span data-ttu-id="fe515-106">En **Todas las solicitudes de mantenimiento** o **Solicitudes de mantenimiento activas** o **Mis solicitudes de mantenimiento de la ubicación técnica**.</span><span class="sxs-lookup"><span data-stu-id="fe515-106">On the **All maintenance requests** or **Active maintenance requests** or **My functional location maintenance requests** page</span></span> 

## <a name="create-work-order"></a><span data-ttu-id="fe515-107">Crear orden de trabajo</span><span class="sxs-lookup"><span data-stu-id="fe515-107">Create work order</span></span>

1. <span data-ttu-id="fe515-108">Seleccione **Administración de activos** > **Común** > **Órdenes de trabajo** > **Todas las órdenes de trabajo** u **Órdenes de trabajo activas**.</span><span class="sxs-lookup"><span data-stu-id="fe515-108">Selece **Asset management** > **Common** > **Work orders** > **All work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="fe515-109">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="fe515-109">Select **New**.</span></span>

3. <span data-ttu-id="fe515-110">En el cuadro de diálogo **Crear orden de trabajo**, seleccione un tipo de orden del trabajo en el campo **Tipo de orden de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="fe515-110">In the **Create work order** dialog, select a work order type in the **Work order type** field.</span></span>

4. <span data-ttu-id="fe515-111">Si es necesario, seleccione una **Descripción**.</span><span class="sxs-lookup"><span data-stu-id="fe515-111">If required, select a **Description**.</span></span>

5. <span data-ttu-id="fe515-112">Seleccione el activo en el campo **Activo**.</span><span class="sxs-lookup"><span data-stu-id="fe515-112">In the **Asset** field, select the asset.</span></span>

>[!NOTE]
><span data-ttu-id="fe515-113">Al seleccionar un activo, tres fichas pueden estar disponibles en el menú desplegable **Activo**:</span><span class="sxs-lookup"><span data-stu-id="fe515-113">When you select an asset, three tabs might be available in the **Asset** drop-down:</span></span> 

- <span data-ttu-id="fe515-114">**Activos activos**: esta ficha contiene una lista de todos los activos cuyo estado de ciclo de vida es "Activo".</span><span class="sxs-lookup"><span data-stu-id="fe515-114">**Active assets** - This tab contains a list of all assets that have an "Active" asset lifecycle state.</span></span> 
- <span data-ttu-id="fe515-115">**Vista de activos**: esta ficha muestra una vista de árbol de las ubicaciones técnicas y los activos instalados en ellas.</span><span class="sxs-lookup"><span data-stu-id="fe515-115">**Asset view** - This tab displays a tree view of functional locations and the assets installed on them.</span></span>
- <span data-ttu-id="fe515-116">**Mis activos**: esta ficha contiene los activos que están relacionados con las ubicaciones técnicas y que se le pueden asignar (al trabajador que ha iniciado sesión en el sistema).</span><span class="sxs-lookup"><span data-stu-id="fe515-116">**My assets** - This tab contains assets that are related to the functional locations that you (the worker who is signed in to the system) may be allocated to.</span></span> <span data-ttu-id="fe515-117">(Para obtener información sobre la configuración, consulte [Trabajadores de mantenimiento y grupos de trabajadores](../setup-for-objects/workers-and-worker-groups.md).) Si no se ha configurado ninguna ubicación técnica de un trabajador en [Trabajadores de mantenimiento y grupos de trabajadores](../setup-for-objects/workers-and-worker-groups.md), la ficha **Mis activos** no está disponible.</span><span class="sxs-lookup"><span data-stu-id="fe515-117">(For information about the setup, see [Maintenance workers and worker groups](../setup-for-objects/workers-and-worker-groups.md).) If no functional locations are set up on a worker in [Maintenance workers and worker groups](../setup-for-objects/workers-and-worker-groups.md), the **My assets** tab isn't available.</span></span> 

6. <span data-ttu-id="fe515-118">Seleccione el tipo de trabajo de mantenimiento para la orden de trabajo en el campo **Tipo de trabajo de mantenimiento**.</span><span class="sxs-lookup"><span data-stu-id="fe515-118">In the **Maintenance job type** field, select a maintenance job type for the work order.</span></span>

7. <span data-ttu-id="fe515-119">Si es necesario, seleccione **Variante de tipo de trabajo de mantenimiento** y **Comercio**.</span><span class="sxs-lookup"><span data-stu-id="fe515-119">If required, select **Maintenance job type variant** and **Trade**.</span></span>

8. <span data-ttu-id="fe515-120">Si es necesario, puede cambiar el nivel de servicio de la orden de trabajo en el campo **Nivel de servicio**.</span><span class="sxs-lookup"><span data-stu-id="fe515-120">If required, you can change the work order service level in the **Service level** field.</span></span>

9. <span data-ttu-id="fe515-121">Seleccione las fechas **Inicio previsto** y **Final previsto** en los campos relacionados.</span><span class="sxs-lookup"><span data-stu-id="fe515-121">Select **Expected start** and **Expected end** dates in the related fields.</span></span>

10. <span data-ttu-id="fe515-122">Haga clic en **Aceptar** para crear la orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="fe515-122">Click **OK** to create the work order.</span></span>

11. <span data-ttu-id="fe515-123">En la página de lista **Todas las órdenes de trabajo**, puede editar las órdenes de trabajo como sea necesario.</span><span class="sxs-lookup"><span data-stu-id="fe515-123">On the **All work orders** list page, you can edit the work order as you require.</span></span>

<span data-ttu-id="fe515-124">Tenga en cuenta los aspectos siguientes:</span><span class="sxs-lookup"><span data-stu-id="fe515-124">Note the following points:</span></span>

- <span data-ttu-id="fe515-125">En la vista de detalles de la página de lista **Todas las órdenes de trabajo**, puede agregar varios activos a una orden de trabajo agregando líneas en la ficha desplegable **Trabajos de mantenimiento de órdenes de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="fe515-125">In the details view on the **All work orders** list page, you can add several assets to a work order by adding lines on the **Work order maintenance jobs** FastTab.</span></span> <span data-ttu-id="fe515-126">En el activo, solo puede seleccionar los tipos de trabajo de mantenimiento que se definen en el tipo de activo seleccionando para el activo.</span><span class="sxs-lookup"><span data-stu-id="fe515-126">On an asset, you can select only the maintenance job types that are defined on the asset type that is selected on the asset.</span></span>  

- <span data-ttu-id="fe515-127">Si modifica el nivel de servicio de activos o una importancia de activo después de utilizar el activo en una orden de trabajo, el nivel de servicio o la importancia de la orden de trabajo no se actualiza como corresponde.</span><span class="sxs-lookup"><span data-stu-id="fe515-127">If you change an asset service level or an asset criticality after you've used the asset on a work order, the service level or criticality on the work order isn't updated accordingly.</span></span> <span data-ttu-id="fe515-128">Para obtener más información sobre los niveles de servicio y las importancias, consulte [Niveles del servicio de activos](../setup-for-objects/object-priorities.md) e [Tipos de importancia de activos](../setup-for-objects/object-criticalities.md).</span><span class="sxs-lookup"><span data-stu-id="fe515-128">For more information about service levels and criticalities, see [Asset service levels](../setup-for-objects/object-priorities.md) and [Asset criticality types](../setup-for-objects/object-criticalities.md).</span></span>

- <span data-ttu-id="fe515-129">La importancia de una orden de trabajo se actualiza cada vez que se agrega o se elimina un trabajo de una orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="fe515-129">Criticality on a work order is recalculated every time a work order job is added to or deleted from the work order.</span></span>

- <span data-ttu-id="fe515-130">En la vista de detalles **Todas las órdenes de trabajo** > ficha **Encabezado** > ficha desplegable **Programar**, puede seleccionar un trabajador o grupo de trabajadores responsable del mantenimiento en los campos **Grupo responsable** o **Responsable**.</span><span class="sxs-lookup"><span data-stu-id="fe515-130">In the **All work orders** details view > **Header** tab > **Schedule** FastTab, in the **Responsible group** or **Responsible** field, you can select a responsible maintenance worker group or a responsible maintenance worker.</span></span> <span data-ttu-id="fe515-131">Estos valores se pueden cambiar mientras que la orden de trabajo está activa.</span><span class="sxs-lookup"><span data-stu-id="fe515-131">These settings can be changed while the work order is active.</span></span> <span data-ttu-id="fe515-132">Por ejemplo, se pueden cambiar cuando cambia el estado del ciclo de vida de la orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="fe515-132">For example, they can be changed when the work order lifecycle state changes.</span></span> <span data-ttu-id="fe515-133">La selección automática realizada durante la creación de la orden de trabajo se basa en la configuración en la página **Trabajadores responsables del mantenimiento**.</span><span class="sxs-lookup"><span data-stu-id="fe515-133">The automatic selection that is made during work order creation is based on the setup on the **Responsible maintenance workers** page.</span></span> <span data-ttu-id="fe515-134">Si agrega o elimina tareas de una orden de trabajo después de haber creado una orden de trabajo, y los campos **Grupo responsable** y **Responsable** están en blanco cuando actualiza la orden de trabajo, la Administración de activos intenta buscar una posible coincidencia en la página de configuración para un trabajador o grupo de trabajadores responsable del mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="fe515-134">If you add or remove work order jobs after you've created a work order, and if the **Responsible group** and **Responsible** fields are blank when you update the work order, Asset Management tries to find a responsible maintenance worker group or a responsible maintenance worker for a possible match on the setup page.</span></span> <span data-ttu-id="fe515-135">Si los campos **Grupo responsable** o **Responsable** ya están definidos cuando actualice la orden de trabajo, no se realiza ningún cambio.</span><span class="sxs-lookup"><span data-stu-id="fe515-135">If the **Responsible group** or **Responsible** field is already set when you update the work order, no changes are made.</span></span> <span data-ttu-id="fe515-136">Para obtener más información sobre los trabajadores y grupos de trabajadores de mantenimiento responsables, consulte [Trabajadores de mantenimiento responsables](../setup-for-maintenance-requests/responsible-workers.md).</span><span class="sxs-lookup"><span data-stu-id="fe515-136">For more information about responsible maintenance workers and worker groups, see [Responsible maintenance workers](../setup-for-maintenance-requests/responsible-workers.md).</span></span>

- <span data-ttu-id="fe515-137">En la página [Estado del mantenimiento](../controlling-and-reporting/maintenance-status.md), puede hacer un cálculo para obtener una visión general de la carga de trabajo relativa a las órdenes de trabajo entrantes y completadas.</span><span class="sxs-lookup"><span data-stu-id="fe515-137">From the [Maintenance status](../controlling-and-reporting/maintenance-status.md) page, you can do a calculation to get an overview of the workload for incoming and completed work orders.</span></span>  

- <span data-ttu-id="fe515-138">En la vista detalles de la página **Todas las órdenes de trabajo**, en la ficha desplegable **Detalles de línea**, puede utilizar los campos **Latitud** y **Longitud** para agregar las coordenadas geográficas para el activo que se selecciona en la tarea de la orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="fe515-138">In the details view of the **All work orders** page, on the **Line details** FastTab, you can use the **Latitude** and **Longitude** fields to add geographic coordinates for the asset that is selected on the work order job.</span></span>  


## <a name="create-related-work-order"></a><span data-ttu-id="fe515-139">Crear orden de trabajo relacionada</span><span class="sxs-lookup"><span data-stu-id="fe515-139">Create related work order</span></span>

<span data-ttu-id="fe515-140">Puede crear una orden de trabajo relacionada con una orden de trabajo existente.</span><span class="sxs-lookup"><span data-stu-id="fe515-140">You can create a work order that is related to an existing work order.</span></span> <span data-ttu-id="fe515-141">Esta capacidad resulta útil, por ejemplo, si se desea trabajar con órdenes de trabajo principales y secundarios.</span><span class="sxs-lookup"><span data-stu-id="fe515-141">This capability is useful if, for example, you want to work with primary and secondary work orders.</span></span> <span data-ttu-id="fe515-142">Una nueva orden de trabajo se basa en una tarea de la orden de trabajo a partir de una orden de trabajo existente.</span><span class="sxs-lookup"><span data-stu-id="fe515-142">A new work order is based on a work order job from an existing work order.</span></span>

1. <span data-ttu-id="fe515-143">Seleccione **Administración de activos** > **Común** > **Órdenes de trabajo** > **Todas las órdenes de trabajo** u **Órdenes de trabajo activas**.</span><span class="sxs-lookup"><span data-stu-id="fe515-143">Select **Asset management** > **Common** > **Work orders** > **All work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="fe515-144">Seleccione la orden de trabajo para crear una orden de trabajo relacionada.</span><span class="sxs-lookup"><span data-stu-id="fe515-144">Select the work order to create a related work order for.</span></span>

3. <span data-ttu-id="fe515-145">En el panel de acciones, en la ficha **Orden de trabajo**, en el grupo **Nuevo**, seleccione **Orden de trabajo relacionada**.</span><span class="sxs-lookup"><span data-stu-id="fe515-145">On the Action Pane, on the **Work order** tab, in the **New** group, select **Related work order**.</span></span>

4. <span data-ttu-id="fe515-146">En el cuadro de diálogo desplegable **Crear orden de trabajo relacionada**, seleccione la orden de trabajo para la que desea crear una orden de trabajo relacionada en el campo **Tarea de orden de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="fe515-146">In the **Create related work order** dialog, in the **Work order job** field, select the work order job to create a related work order for.</span></span>

5. <span data-ttu-id="fe515-147">En el campo **Tipo de trabajo de mantenimiento**, seleccione el tipo de trabajo de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="fe515-147">Select a maintenance job type in the **Maintenance job type** field.</span></span>

6. <span data-ttu-id="fe515-148">En los campos **Variante del tipo de trabajo de mantenimiento** y **Comercio**, seleccione la variante y el comercio relacionados con el tipo de trabajo de mantenimiento que sean necesarios.</span><span class="sxs-lookup"><span data-stu-id="fe515-148">Select a related maintenance job type variant and trade in the **Maintenance job type variant** and **Trade** fields, as you require.</span></span>

7. <span data-ttu-id="fe515-149">Si esta orden de trabajo es la primera orden de trabajo relacionada que se ha creado para la orden de trabajo seleccionada, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="fe515-149">If this work order is the first related work order that has been created for the selected work order, follow these steps:</span></span>
    1. <span data-ttu-id="fe515-150">Seleccione la opción **Nueva orden de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="fe515-150">Select the **New work order** option.</span></span>
    2. <span data-ttu-id="fe515-151">En el campo **Tipo de orden de trabajo**, seleccione un tipo de orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="fe515-151">In  the **Work order type** field, select a work order type.</span></span>
    3. <span data-ttu-id="fe515-152">En **Descripción**, escriba una descripción.</span><span class="sxs-lookup"><span data-stu-id="fe515-152">In the **Description**, enter a description.</span></span>
    4. <span data-ttu-id="fe515-153">Si es necesario, cambie el nivel de servicio de la orden de trabajo en el campo **Nivel de servicio**.</span><span class="sxs-lookup"><span data-stu-id="fe515-153">In the **Service level** field, change the work order service level as you require.</span></span>
    5. <span data-ttu-id="fe515-154">En los campos **Inicio previsto** y **Final previsto**, seleccione las fechas inicial y final previstas.</span><span class="sxs-lookup"><span data-stu-id="fe515-154">In the **Expected start** and **Expected end** fields, select the expected start and end dates.</span></span>
    6. <span data-ttu-id="fe515-155">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="fe515-155">Select **OK**.</span></span> <span data-ttu-id="fe515-156">La nueva orden de trabajo relacionada se muestra en la página de lista **Todas las órdenes de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="fe515-156">The new related work order is shown on the **All work orders** list page.</span></span>  

8. <span data-ttu-id="fe515-157">Si la orden de trabajo para la que está creando esta orden de trabajo relacionada ya tiene órdenes de trabajo relacionadas, siga estos pasos para agregar una nueva tarea de orden de trabajo a una orden de trabajo relacionada existente:</span><span class="sxs-lookup"><span data-stu-id="fe515-157">If the work order that you're creating this related work order for already has related work orders, follow these steps to add a new work order job to an existing related work order:</span></span>
    1. <span data-ttu-id="fe515-158">Seleccione la opción **Agregar a orden de trabajo relacionada**.</span><span class="sxs-lookup"><span data-stu-id="fe515-158">Select the **Add to related work order** option.</span></span>
    2. <span data-ttu-id="fe515-159">A continuación, en el campo **Orden de trabajo** seleccione la orden de trabajo relacionada a la que desea agregar una nueva tarea de orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="fe515-159">In the **Work order** field, select the related work order to add a new work order job to.</span></span>
    3. <span data-ttu-id="fe515-160">Si es necesario, cambie el nivel de servicio de la orden de trabajo en el campo **Nivel de servicio**.</span><span class="sxs-lookup"><span data-stu-id="fe515-160">In the **Service level** field, change the work order service level as you require.</span></span>
    4. <span data-ttu-id="fe515-161">En los campos **Inicio previsto** y **Final previsto**, cambie las fechas inicial y final previstas en la medida en que sea necesario.</span><span class="sxs-lookup"><span data-stu-id="fe515-161">In the **Expected start** and **Expected end** fields, change the expected start and end dates as you require.</span></span>
    5. <span data-ttu-id="fe515-162">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="fe515-162">Select **OK**.</span></span> <span data-ttu-id="fe515-163">La orden de trabajo se agrega a la orden de trabajo relacionada que ya existe.</span><span class="sxs-lookup"><span data-stu-id="fe515-163">The work order job is added to the existing related work order.</span></span>

<span data-ttu-id="fe515-164">La ilustración muestra un ejemplo del cuadro de diálogo **Crear orden de trabajo relacionada**.</span><span class="sxs-lookup"><span data-stu-id="fe515-164">The illustration below shows an example of the **Create related work order** dialog.</span></span>

![Figura 1](media/03-work-orders.png)

>[!NOTE]
><span data-ttu-id="fe515-166">Si ha configurado una máscara de orden de trabajo relacionada en la ficha **Parámetros de administración de activos** > **Órdenes de trabajo** > campo **Máscara de orden de trabajo relacionada**, los id. de orden de trabajo se crearán de acuerdo con la configuración de la máscara.</span><span class="sxs-lookup"><span data-stu-id="fe515-166">If you've set up a related work order mask in **Asset management parameters** > **Work orders** tab > **Related work order mask** field, work order IDs are created according to the mask setup.</span></span> <span data-ttu-id="fe515-167">Si no se ha configurado ninguna máscara de orden de trabajo relacionada, se utiliza el siguiente id. de orden de trabajo disponible para las órdenes de trabajo relacionadas.</span><span class="sxs-lookup"><span data-stu-id="fe515-167">If no related work order mask is set up, the next available work order ID is used for related work orders.</span></span>

## <a name="copy-a-work-order"></a><span data-ttu-id="fe515-168">Copiar una orden de trabajo</span><span class="sxs-lookup"><span data-stu-id="fe515-168">Copy a work order</span></span>

<span data-ttu-id="fe515-169">Puede crear rápidamente una nueva orden de trabajo a partir de una orden de trabajo existente.</span><span class="sxs-lookup"><span data-stu-id="fe515-169">You can quickly create a new work order from an existing work order.</span></span> <span data-ttu-id="fe515-170">Esta forma de trabajar con órdenes de trabajo es diferente a la de crear órdenes de trabajo basadas en [planes de mantenimiento](../preventive-and-reactive-maintenance/maintenance-plans.md).</span><span class="sxs-lookup"><span data-stu-id="fe515-170">This way of working with work orders differs from the creation of work orders based on [maintenance plans](../preventive-and-reactive-maintenance/maintenance-plans.md).</span></span> <span data-ttu-id="fe515-171">Resulta útil si, por ejemplo, tiene una orden de trabajo que contiene muchas tareas con distintas tareas en diferentes activos que se deben completar a intervalos periódicos.</span><span class="sxs-lookup"><span data-stu-id="fe515-171">It's useful if, for example, a work order contains many work order jobs, and the various jobs should be completed on different assets at regular intervals.</span></span>

1. <span data-ttu-id="fe515-172">Seleccione **Administración de activos** > **Común** > **Órdenes de trabajo** > **Todas las órdenes de trabajo** u **Órdenes de trabajo activas**.</span><span class="sxs-lookup"><span data-stu-id="fe515-172">Select **Asset management** > **Common** > **Work orders** > **All work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="fe515-173">Seleccione la orden de trabajo desde la que desea copiar el contenido.</span><span class="sxs-lookup"><span data-stu-id="fe515-173">Select the work order to copy content from.</span></span>

3. <span data-ttu-id="fe515-174">En el panel de acciones, en la ficha **Orden de trabajo**, en el grupo **Nuevo**, seleccione **Copiar orden de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="fe515-174">On the Action Pane > **Work order** tab > **New** group, select **Copy work order**.</span></span>

4. <span data-ttu-id="fe515-175">Se muestra la configuración de la orden de trabajo desde la orden de trabajo seleccionada.</span><span class="sxs-lookup"><span data-stu-id="fe515-175">The work order setup from the selected work order is shown.</span></span> <span data-ttu-id="fe515-176">Si es necesario, puede editar algunos campos.</span><span class="sxs-lookup"><span data-stu-id="fe515-176">You can edit some of the fields as you require.</span></span>

5. <span data-ttu-id="fe515-177">Seleccione **Aceptar** para crear la nueva orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="fe515-177">Select **OK** to create the new work order.</span></span>

6. <span data-ttu-id="fe515-178">En la página de lista **Todas las órdenes de trabajo**, puede editar las órdenes de trabajo como sea necesario.</span><span class="sxs-lookup"><span data-stu-id="fe515-178">On the **All work orders** list page, you can edit the work order as you require.</span></span>

>[!NOTE]
><span data-ttu-id="fe515-179">Cuando se crea la nueva orden de trabajo, alguna información se copia directamente desde la orden de trabajo existente.</span><span class="sxs-lookup"><span data-stu-id="fe515-179">When the new work order is created, some information is copied directly from the existing work order.</span></span> <span data-ttu-id="fe515-180">La información sobre las previsiones, herramientas, listas de comprobación de mantenimiento, la ubicación funcional, direcciones, y la programación no se copia.</span><span class="sxs-lookup"><span data-stu-id="fe515-180">Information about forecasts, tools, maintenance checklists, functional location, addresses, and scheduling isn't copied.</span></span> <span data-ttu-id="fe515-181">En su lugar, se inicializa de la configuración actual en Administración de activos.</span><span class="sxs-lookup"><span data-stu-id="fe515-181">Instead, it's initialized from the current setup in Asset Management.</span></span> <span data-ttu-id="fe515-182">Por lo tanto, si la información se cambió entre el momento en que se creó la primera orden de trabajo y el momento en que hizo una copia de la orden de trabajo, los cambios se incluyen en la nueva orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="fe515-182">Therefore, if that information was changed between the time when the first work order was created and the time when you made a copy of the work order, the changes are included in the new work order.</span></span> <span data-ttu-id="fe515-183">Algunos ejemplos son los cambios en las previsiones y las actualizaciones de las listas de comprobación de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="fe515-183">Examples include changes to forecasts and updates to maintenance checklists.</span></span>

<span data-ttu-id="fe515-184">La ilustración siguiente muestra un ejemplo del diálogo **Copiar orden de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="fe515-184">The illustration below shows an example of the **Copy work order** dialog.</span></span>

![Figura 2](media/04-work-orders.png)


## <a name="create-a-work-order-based-on-a-maintenance-request"></a><span data-ttu-id="fe515-186">Crear una orden de trabajo basada en una solicitud de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="fe515-186">Create a work order based on a maintenance request</span></span>

1. <span data-ttu-id="fe515-187">Seleccione **Administración de activos** > **Común** > **Solicitudes de mantenimiento** > **Todas las solicitudes de mantenimiento** o **Solicitudes de mantenimiento activas**.</span><span class="sxs-lookup"><span data-stu-id="fe515-187">Select **Asset management** > **Common** > **Maintenance requests** > **All maintenance requests** or **Active maintenance requests**.</span></span>

2. <span data-ttu-id="fe515-188">Seleccione las solicitudes de mantenimiento para las que desea crear una orden de trabajo y haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="fe515-188">Select the maintenance request to create a work order for, and click **Edit**.</span></span>

3. <span data-ttu-id="fe515-189">En el panel de acciones, en la ficha **Solicitud de mantenimiento**, en el grupo **Nuevo**, seleccione **Orden de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="fe515-189">On the Action Pane > **Maintenance request** tab > **New** group, select **Work order**.</span></span>

4. <span data-ttu-id="fe515-190">En el cuadro de diálogo **Orden de trabajo**, establezca los campos.</span><span class="sxs-lookup"><span data-stu-id="fe515-190">In the **Work order** dialog, set the fields.</span></span> <span data-ttu-id="fe515-191">Si se ha seleccionado un tipo de trabajo de mantenimiento en la solicitud de mantenimiento, puede seleccionar otro tipo de trabajo de mantenimiento, si es necesario, al crear la orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="fe515-191">If a maintenance job type has been selected in the maintenance request, you can select a different maintenance job type when you create the work order, as you require.</span></span>

5. <span data-ttu-id="fe515-192">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="fe515-192">Select **OK**.</span></span> <span data-ttu-id="fe515-193">Un mensaje informa de que se ha creado la orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="fe515-193">A message notifies you that the work order has been created.</span></span>

6. <span data-ttu-id="fe515-194">Para ver las órdenes de trabajo que están conectadas a una solicitud de mantenimiento, seleccione la solicitud de mantenimiento en la página de lista **Todas las solicitudes de mantenimiento** o **Solicitudes de mantenimiento activas**.</span><span class="sxs-lookup"><span data-stu-id="fe515-194">To view the work orders that are connected to a maintenance request, on the **All maintenance requests** or **Active maintenance requests** list page, select the maintenance request.</span></span> <span data-ttu-id="fe515-195">A continuación, en el panel de acciones, en la ficha **Solicitud de mantenimiento**, en el grupo **Vista**, seleccione **Órdenes de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="fe515-195">Then, on the Action Pane, on the **Maintenance request** tab, in the **View** group, select **Work orders**.</span></span>


<span data-ttu-id="fe515-196">La ilustración siguiente muestra un ejemplo del diálogo **Crear orden de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="fe515-196">The illustration below shows an example of the **Create work order** dialog.</span></span>

![Figura 3](media/05-work-orders.png)


>[!NOTE]
><span data-ttu-id="fe515-198">Si desea que las órdenes de trabajo se creen automáticamente, puede programar tareas del plan de mantenimiento, o bien configurar "Crear automáticamente" [planes de mantenimiento](../preventive-and-reactive-maintenance/maintenance-plans.md) o [rondas de mantenimiento](../preventive-and-reactive-maintenance/maintenance-rounds.md) en un activo.</span><span class="sxs-lookup"><span data-stu-id="fe515-198">If you want work orders to be created automatically, you can schedule maintenance plan jobs, or you can set up "Auto create" [maintenance plans](../preventive-and-reactive-maintenance/maintenance-plans.md) or [maintenance rounds](../preventive-and-reactive-maintenance/maintenance-rounds.md) on an asset.</span></span> <span data-ttu-id="fe515-199">Las órdenes de trabajo creadas a partir de solicitudes de mantenimiento en la página de lista **Todo el programa de mantenimiento** tienen tipos de trabajo de mantenimiento seleccionados en las solicitudes de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="fe515-199">Work orders that are created from maintenance requests on the **All maintenance schedule** list page have the maintenance job types that are selected on the maintenance requests.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]