---
title: Tránsito directo planificado
description: Este tema describe la planificación avanzada del tránsito directo, donde la cantidad de inventario que se requiere para un pedido se dirige directamente desde la recepción o la creación hasta el muelle de salida o el área de preparación correcta. Todo el inventario restante de la fuente entrante se dirige a la ubicación de almacenamiento correcta a través del proceso regular de almacenamiento.
author: Mirzaab
manager: tfehr
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSCrossDockingTemplate, WHSLoadPostMethod, WHSWorkClass, WHSWorkTemplateTable, WHSLocDirTable, WHSPlannedCrossDocking
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: 722b004e607cb2e6b7de292d92b67b18c2024696
ms.sourcegitcommit: 70b1567d316f19c15a4b032b4897f15c8dcdca09
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2021
ms.locfileid: "5556275"
---
# <a name="planned-cross-docking"></a><span data-ttu-id="db9e6-104">Tránsito directo planificado</span><span class="sxs-lookup"><span data-stu-id="db9e6-104">Planned cross-docking</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="db9e6-105">Este tema describe la planificación avanzada del tránsito directo.</span><span class="sxs-lookup"><span data-stu-id="db9e6-105">This topic describes advanced planned cross-docking.</span></span> <span data-ttu-id="db9e6-106">El tránsito directo es un proceso de almacén, donde la cantidad de inventario que se requiere para un pedido se dirige directamente desde la recepción o la creación hasta el muelle de salida o el área de preparación correcta.</span><span class="sxs-lookup"><span data-stu-id="db9e6-106">Cross-docking is a warehouse process where the inventory quantity that is required for an order is directed straight from receipt or creation to the correct outbound dock or staging area.</span></span> <span data-ttu-id="db9e6-107">Todo el inventario restante de la fuente entrante se dirige a la ubicación de almacenamiento correcta a través del proceso regular de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="db9e6-107">All remaining inventory from the inbound source is directed to the correct storage location through the regular put-away process.</span></span>

<span data-ttu-id="db9e6-108">El tránsito directo permite a los trabajadores omitir la recogida entrante y la selección saliente del inventario que ya está marcado para un pedido saliente.</span><span class="sxs-lookup"><span data-stu-id="db9e6-108">Cross-docking lets workers skip inbound put-away and outbound picking of inventory that is already marked for an outbound order.</span></span> <span data-ttu-id="db9e6-109">Por lo tanto, el número de veces que se toca el inventario se minimiza, siempre que sea posible.</span><span class="sxs-lookup"><span data-stu-id="db9e6-109">Therefore, the number of times that inventory is touched is minimized, where possible.</span></span> <span data-ttu-id="db9e6-110">Además, debido a que hay menos interacción con el sistema, se incrementan los ahorros de tiempo y espacio en el piso del almacén.</span><span class="sxs-lookup"><span data-stu-id="db9e6-110">Additionally, because there is less interaction with the system, time and space savings on the warehouse shop floor are increased.</span></span>

<span data-ttu-id="db9e6-111">Antes de que se pueda ejecutar el tránsito directo, el usuario debe configurar una nueva plantilla de tránsito directo, donde se especifique la fuente de suministro y otros conjuntos de requisitos para el tránsito directo.</span><span class="sxs-lookup"><span data-stu-id="db9e6-111">Before cross-docking can be run, the user must configure a new cross-docking template, where the supply source and other sets of requirements for cross-docking are specified.</span></span> <span data-ttu-id="db9e6-112">A medida que se crea la orden de salida, la línea debe marcarse contra una orden de entrada que contiene el mismo artículo.</span><span class="sxs-lookup"><span data-stu-id="db9e6-112">As the outbound order is created, the line must be marked against an inbound order that contains the same item.</span></span>

<span data-ttu-id="db9e6-113">En el momento de la recepción de la orden entrante, la configuración de tránsito directo identifica automáticamente la necesidad de tránsito directo y crea el trabajo de movimiento para la cantidad requerida, en función de la configuración de la directiva de ubicación.</span><span class="sxs-lookup"><span data-stu-id="db9e6-113">At the time of inbound order receiving, the cross-docking setup automatically identifies the need for cross-docking and creates the movement work for the required quantity, based on the setup of the location directive.</span></span>

> [!NOTE]
> <span data-ttu-id="db9e6-114">Las transacciones de inventario son **no** sin registrar cuando se cancela el trabajo de tránsito directo, incluso si la configuración de esta capacidad está activada en los parámetros de gestión de Almacén.</span><span class="sxs-lookup"><span data-stu-id="db9e6-114">Inventory transactions are **not** unregistered when crossing-dock work is canceled, even if the setting for this capability is turned on in Warehouse management parameters.</span></span>

## <a name="turn-on-the-planned-cross-docking-features"></a><span data-ttu-id="db9e6-115">Active las funciones de tránsito directo planificado</span><span class="sxs-lookup"><span data-stu-id="db9e6-115">Turn on the planned cross docking features</span></span>

<span data-ttu-id="db9e6-116">Si su sistema aún no incluye las funciones descritas en este tema, vaya a [Gestión de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) y active las características siguientes por este orden:</span><span class="sxs-lookup"><span data-stu-id="db9e6-116">If your system doesn't already include the features described in this topic, go to [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) and turn on the following features in the following order:</span></span>

1. <span data-ttu-id="db9e6-117">*Tránsito directo planificado*</span><span class="sxs-lookup"><span data-stu-id="db9e6-117">*Planned cross docking*</span></span>
2. <span data-ttu-id="db9e6-118">*Plantillas de tránsito directo con directivas de ubicación*</span><span class="sxs-lookup"><span data-stu-id="db9e6-118">*Cross docking templates with location directives*</span></span>

## <a name="setup"></a><span data-ttu-id="db9e6-119">Configurar</span><span class="sxs-lookup"><span data-stu-id="db9e6-119">Setup</span></span>

### <a name="regenerate-load-posting-methods"></a><span data-ttu-id="db9e6-120">Regenerar métodos de registro de carga</span><span class="sxs-lookup"><span data-stu-id="db9e6-120">Regenerate load posting methods</span></span>

<span data-ttu-id="db9e6-121">El tránsito directo planificado se implementa como un método de registro de carga.</span><span class="sxs-lookup"><span data-stu-id="db9e6-121">Planned cross-docking is implemented as a load posting method.</span></span> <span data-ttu-id="db9e6-122">Después de activar la función, debe volver a generar los métodos.</span><span class="sxs-lookup"><span data-stu-id="db9e6-122">After you turn on the feature, you must regenerate the methods.</span></span>

1. <span data-ttu-id="db9e6-123">Vaya a **Administración de almacenes \> Configuración \> Métodos de registro de carga**.</span><span class="sxs-lookup"><span data-stu-id="db9e6-123">Go to **Warehouse management \> Setup \> Load posting methods**.</span></span>
1. <span data-ttu-id="db9e6-124">En el panel acciones, seleccione **Regenerar métodos**.</span><span class="sxs-lookup"><span data-stu-id="db9e6-124">On the Action Pane, select **Regenerate methods**.</span></span>

    <span data-ttu-id="db9e6-125">Cuando se completa la regeneración, debería ver un método que tiene un **Nombre del método** con el valor de *planCrossDocking*.</span><span class="sxs-lookup"><span data-stu-id="db9e6-125">When regeneration is completed, you should see a method that has a **Method name** value of *planCrossDocking*.</span></span>

1. <span data-ttu-id="db9e6-126">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="db9e6-126">Close the page.</span></span>

### <a name="create-a-cross-docking-template"></a><span data-ttu-id="db9e6-127">Cree una plantilla de tránsito directo</span><span class="sxs-lookup"><span data-stu-id="db9e6-127">Create a cross-docking template</span></span>

1. <span data-ttu-id="db9e6-128">Vaya a **Gestión de almacenes \> Configuración \> Trabajo \> Plantillas de tránsito directo**.</span><span class="sxs-lookup"><span data-stu-id="db9e6-128">Go to **Warehouse management \> Setup \> Work \> Cross docking templates**.</span></span>
1. <span data-ttu-id="db9e6-129">En el Panel de acciones, haga clic en **Nuevo** para crear una plantilla.</span><span class="sxs-lookup"><span data-stu-id="db9e6-129">On the Action Pane, select **New** to create a template.</span></span>
1. <span data-ttu-id="db9e6-130">Establezca los siguientes valores en el encabezado:</span><span class="sxs-lookup"><span data-stu-id="db9e6-130">In the header, set the following values:</span></span>

    - <span data-ttu-id="db9e6-131">**Secuencia**: *1*</span><span class="sxs-lookup"><span data-stu-id="db9e6-131">**Sequence:** *1*</span></span>

        <span data-ttu-id="db9e6-132">Este campo define el orden en que se evalúan las plantillas.</span><span class="sxs-lookup"><span data-stu-id="db9e6-132">This field defines the order that templates are evaluated in.</span></span>

    - <span data-ttu-id="db9e6-133">**Identificación de plantilla de tránsito directo:** *51*</span><span class="sxs-lookup"><span data-stu-id="db9e6-133">**Cross docking template ID:** *51*</span></span>
    - <span data-ttu-id="db9e6-134">**Descripción:** *Almacén 51*</span><span class="sxs-lookup"><span data-stu-id="db9e6-134">**Description:** *Warehouse 51*</span></span>
    - <span data-ttu-id="db9e6-135">**Directiva de liberación de demanda:** *Antes del recibo de suministro*</span><span class="sxs-lookup"><span data-stu-id="db9e6-135">**Demand release policy:** *Before supply receipt*</span></span>
    - <span data-ttu-id="db9e6-136">**Almacén**: *51*</span><span class="sxs-lookup"><span data-stu-id="db9e6-136">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="db9e6-137">La configuración en la ficha desplegable **Planificación** controla cómo funciona la plantilla.</span><span class="sxs-lookup"><span data-stu-id="db9e6-137">The setup on the **Planning** FastTab controls how the template works.</span></span> <span data-ttu-id="db9e6-138">Establezca los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="db9e6-138">Set the following values:</span></span>

    - <span data-ttu-id="db9e6-139">**Requisitos de demanda:** *Ninguno*</span><span class="sxs-lookup"><span data-stu-id="db9e6-139">**Demand requirements:** *None*</span></span>

        <span data-ttu-id="db9e6-140">Este campo define los requisitos del inventario de demanda.</span><span class="sxs-lookup"><span data-stu-id="db9e6-140">This field defines the requirements of the demand inventory.</span></span> <span data-ttu-id="db9e6-141">Si la demanda debe estar vinculada a la oferta antes del lanzamiento, seleccione *Calificación*.</span><span class="sxs-lookup"><span data-stu-id="db9e6-141">If the demand must be linked to the supply before release, select *Marking*.</span></span> <span data-ttu-id="db9e6-142">Si la demanda debe reservarse para el pedido antes del lanzamiento, seleccione *Reserva de pedidos*.</span><span class="sxs-lookup"><span data-stu-id="db9e6-142">If the demand must be order-reserved against the supply before release, select *Order reservation*.</span></span>

    - <span data-ttu-id="db9e6-143">**Tipo de ubicación:** *Ubicaciones de envío*</span><span class="sxs-lookup"><span data-stu-id="db9e6-143">**Locating type:** *Shipment locations*</span></span>

        <span data-ttu-id="db9e6-144">Este campo define si el trabajo de tránsito directo debe usar las ubicaciones de carga / preparación del envío, o si debe usar directivas de ubicación para encontrar sus propias ubicaciones de almacenamiento provisional / carga.</span><span class="sxs-lookup"><span data-stu-id="db9e6-144">This field defines whether the cross-docking work should use the staging/load locations from the shipment, or whether it should use location directives to find its own staging/load locations.</span></span>

    - <span data-ttu-id="db9e6-145">**Plantilla de trabajo**: deje este campo en blanco.</span><span class="sxs-lookup"><span data-stu-id="db9e6-145">**Work template:** Leave this field blank.</span></span>

        <span data-ttu-id="db9e6-146">Este campo define la plantilla de trabajo que debe usarse cuando se crea trabajo de tránsito directo.</span><span class="sxs-lookup"><span data-stu-id="db9e6-146">This field defines the work template that should be used when cross-docking work is created.</span></span>

    - <span data-ttu-id="db9e6-147">**Revalidar con el recibo de suministro:** *No*</span><span class="sxs-lookup"><span data-stu-id="db9e6-147">**Revalidate on supply receipt:** *No*</span></span>

        <span data-ttu-id="db9e6-148">Esta opción define si el suministro debe revalidarse durante la recepción.</span><span class="sxs-lookup"><span data-stu-id="db9e6-148">This option defines whether the supply should be revalidated during receipt.</span></span> <span data-ttu-id="db9e6-149">Si esta opción está establecida en *Sí*, se verifican tanto la ventana de tiempo máximo como el rango de días de vencimiento.</span><span class="sxs-lookup"><span data-stu-id="db9e6-149">If this option is set to *Yes*, both the maximum time window and the expiration days range are checked.</span></span>

    - <span data-ttu-id="db9e6-150">**Código de directiva:** deje en blanco este campo.</span><span class="sxs-lookup"><span data-stu-id="db9e6-150">**Directive code** Leave this field blank</span></span>

        <span data-ttu-id="db9e6-151">Esta opción permite que el sistema utilice directivas de ubicación para ayudar a determinar la mejor ubicación para mover el inventario de cross-docking.</span><span class="sxs-lookup"><span data-stu-id="db9e6-151">This option enables the system to use location directives to help determine the best location to move cross-docking inventory to.</span></span> <span data-ttu-id="db9e6-152">Puede configurarlo asignando un código de directiva a cada plantilla de cross-docking relevante.</span><span class="sxs-lookup"><span data-stu-id="db9e6-152">You can set it up by assigning a directive code to each relevant cross-docking template.</span></span> <span data-ttu-id="db9e6-153">Cada código de directiva identifica una directiva de ubicación única.</span><span class="sxs-lookup"><span data-stu-id="db9e6-153">Each directive code identifies a unique location directive.</span></span>

    - <span data-ttu-id="db9e6-154">**Validar ventana de tiempo:** *Sí*</span><span class="sxs-lookup"><span data-stu-id="db9e6-154">**Validate time window:** *Yes*</span></span>

        <span data-ttu-id="db9e6-155">Esta opción define si se debe evaluar la ventana de tiempo máximo cuando se selecciona una fuente de suministro.</span><span class="sxs-lookup"><span data-stu-id="db9e6-155">This option defines whether the maximum time window should be evaluated when a supply source is selected.</span></span> <span data-ttu-id="db9e6-156">Si esta opción está establecida en *Sí*, los campos relacionados con las ventanas de tiempo máximo y mínimo están disponibles.</span><span class="sxs-lookup"><span data-stu-id="db9e6-156">If this option is set to *Yes*, the fields that are related to the maximum and minimum time windows become available.</span></span>

    - <span data-ttu-id="db9e6-157">**Ventana de tiempo máxima:** *5*</span><span class="sxs-lookup"><span data-stu-id="db9e6-157">**Maximum time window:** *5*</span></span>

        <span data-ttu-id="db9e6-158">Este campo define el período máximo permitido entre la llegada del suministro y la salida de demanda.</span><span class="sxs-lookup"><span data-stu-id="db9e6-158">This field defines the maximum period that is allowed between supply arrival and demand departure.</span></span>

    - <span data-ttu-id="db9e6-159">**Unidad de ventana de tiempo máximo:** *Días*</span><span class="sxs-lookup"><span data-stu-id="db9e6-159">**Maximum time window unit:** *Days*</span></span>
    - <span data-ttu-id="db9e6-160">**Ventana de tiempo mínima:** *0*</span><span class="sxs-lookup"><span data-stu-id="db9e6-160">**Minimum time window:** *0*</span></span>

        <span data-ttu-id="db9e6-161">Este campo define el período mínimo permitido entre la llegada del suministro y la salida de demanda.</span><span class="sxs-lookup"><span data-stu-id="db9e6-161">This field defines the minimum period that is allowed between supply arrival and demand departure.</span></span>

    - <span data-ttu-id="db9e6-162">**Unidad de ventana de tiempo mínimo:** *Días*</span><span class="sxs-lookup"><span data-stu-id="db9e6-162">**Minimum time window unit:** *Days*</span></span>
    - <span data-ttu-id="db9e6-163">**Intervalo de días de caducidad:** *0*</span><span class="sxs-lookup"><span data-stu-id="db9e6-163">**Expiration days range:** *0*</span></span>

        <span data-ttu-id="db9e6-164">*Criterios de primera caducidad, primera salida (FEFO):* este campo define el número máximo de días entre la fecha de vencimiento del primer lote que está actualmente en el almacén y el lote que se está recibiendo.</span><span class="sxs-lookup"><span data-stu-id="db9e6-164">*First expiry first out (FEFO) criteria:* This field defines the maximum number of days between the expiration date of the first-expiring batch that is currently in the warehouse and the batch that is being received.</span></span>

1. <span data-ttu-id="db9e6-165">En la ficha desplegable **Fuentes de suministro**, especifique los tipos de suministro que son válidos para esta plantilla.</span><span class="sxs-lookup"><span data-stu-id="db9e6-165">On the **Supply sources** FastTab, you specify the types of supply that are valid for this template.</span></span> <span data-ttu-id="db9e6-166">Seleccione **Nuevo** y establezca los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="db9e6-166">Select **New**, and then set the following values:</span></span>

    - <span data-ttu-id="db9e6-167">**Número de secuencia:** *1*</span><span class="sxs-lookup"><span data-stu-id="db9e6-167">**Sequence number:** *1*</span></span>
    - <span data-ttu-id="db9e6-168">**Fuente de suministro:** *Orden de compra*</span><span class="sxs-lookup"><span data-stu-id="db9e6-168">**Supply source:** *Purchase order*</span></span>

### <a name="create-a-work-class"></a><span data-ttu-id="db9e6-169">Crear una clase de trabajo</span><span class="sxs-lookup"><span data-stu-id="db9e6-169">Create a work class</span></span>

1. <span data-ttu-id="db9e6-170">Vaya a **Gestión de almacenes \> Configurar \> Trabajo \> Clases de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="db9e6-170">Go to **Warehouse management \> Setup \> Work \> Work classes**.</span></span>
1. <span data-ttu-id="db9e6-171">En el Panel de acciones, seleccione **Nuevo** para crear una clase de trabajo.</span><span class="sxs-lookup"><span data-stu-id="db9e6-171">On the Action Pane, select **New** to create a work class.</span></span>
1. <span data-ttu-id="db9e6-172">Establezca los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="db9e6-172">Set the following values:</span></span>

    - <span data-ttu-id="db9e6-173">**Identificador de la clase de trabajo**: *CrossDock*</span><span class="sxs-lookup"><span data-stu-id="db9e6-173">**Work class ID:** *CrossDock*</span></span>
    - <span data-ttu-id="db9e6-174">**Descripción:** *Tránsito directo*</span><span class="sxs-lookup"><span data-stu-id="db9e6-174">**Description:** *Cross Dock*</span></span>
    - <span data-ttu-id="db9e6-175">**Tipo de orden de trabajo:** *Tránsito directo*</span><span class="sxs-lookup"><span data-stu-id="db9e6-175">**Work order type:** *Cross docking*</span></span>

### <a name="create-a-work-template"></a><span data-ttu-id="db9e6-176">Crear una plantilla de trabajo</span><span class="sxs-lookup"><span data-stu-id="db9e6-176">Create a work template</span></span>

1. <span data-ttu-id="db9e6-177">Vaya a **Administración de almacenes \> Configuración \> Trabajo \> Plantillas de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="db9e6-177">Go to **Warehouse management \> Setup \> Work \> Work templates**.</span></span>
1. <span data-ttu-id="db9e6-178">Establezca el campo **Tipo de orden de trabajo** a *Tránsito directo*.</span><span class="sxs-lookup"><span data-stu-id="db9e6-178">Set the **Work order type** field to *Cross docking*.</span></span>
1. <span data-ttu-id="db9e6-179">En el Panel de acciones, seleccione **Nuevo** para agregar una línea a la pestaña **Resumen**.</span><span class="sxs-lookup"><span data-stu-id="db9e6-179">On the Action Pane, select **New** to add a line to the **Overview** tab.</span></span>
1. <span data-ttu-id="db9e6-180">En la nueva línea, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="db9e6-180">On the new line, set the following values:</span></span>

    - <span data-ttu-id="db9e6-181">**Número de secuencia:** *1*</span><span class="sxs-lookup"><span data-stu-id="db9e6-181">**Sequence number:** *1*</span></span>
    - <span data-ttu-id="db9e6-182">**Plantilla de trabajo:** *51 Cross Dock*</span><span class="sxs-lookup"><span data-stu-id="db9e6-182">**Work template:** *51 Cross Dock*</span></span>
    - <span data-ttu-id="db9e6-183">**Descripción de la plantilla de trabajo:** *51 Cross Dock*</span><span class="sxs-lookup"><span data-stu-id="db9e6-183">**Work template description:** *51 Cross Dock*</span></span>

1. <span data-ttu-id="db9e6-184">Seleccione **Guardar** para tener disponible la ficha desplegable **Detalles de plantilla de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="db9e6-184">Select **Save** to make the **Work Template Details** FastTab available.</span></span>
1. <span data-ttu-id="db9e6-185">En la ficha desplegable **Detalles de plantilla de trabajo**, seleccione **Nuevo** para agregar una línea a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="db9e6-185">On the **Work Template Details** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="db9e6-186">En la nueva línea, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="db9e6-186">On the new line, set the following values:</span></span>

    - <span data-ttu-id="db9e6-187">**Tipo de trabajo**: *Recoger*</span><span class="sxs-lookup"><span data-stu-id="db9e6-187">**Work type:** *Pick*</span></span>
    - <span data-ttu-id="db9e6-188">**Identificador de la clase de trabajo**: *CrossDock*</span><span class="sxs-lookup"><span data-stu-id="db9e6-188">**Work class ID:** *CrossDock*</span></span>

1. <span data-ttu-id="db9e6-189">Seleccione **Nuevo** para agregar otra línea y establezca los siguientes valores en ella:</span><span class="sxs-lookup"><span data-stu-id="db9e6-189">Select **New** to add another line, and set the following values on it:</span></span>

    - <span data-ttu-id="db9e6-190">**Tipo de trabajo**: *Ubicar*</span><span class="sxs-lookup"><span data-stu-id="db9e6-190">**Work type:** *Put*</span></span>
    - <span data-ttu-id="db9e6-191">**Identificador de la clase de trabajo**: *CrossDock*</span><span class="sxs-lookup"><span data-stu-id="db9e6-191">**Work class ID:** *CrossDock*</span></span>

1. <span data-ttu-id="db9e6-192">Seleccione **Guardar** y confirme que la casilla de verificación **Válido** está seleccionada para la plantilla *51 Cross Dock*.</span><span class="sxs-lookup"><span data-stu-id="db9e6-192">Select **Save**, and confirm that the **Valid** check box is selected for the *51 Cross Dock* template.</span></span>

> [!NOTE]
> <span data-ttu-id="db9e6-193">Los identificadores de clase de trabajo para los tipos de trabajo *Recoger* y *Colocar* deben ser iguales.</span><span class="sxs-lookup"><span data-stu-id="db9e6-193">The work class IDs for the *Pick* and *Put* work types must be the same.</span></span>

### <a name="create-location-directives"></a><span data-ttu-id="db9e6-194">Crear directivas de ubicación</span><span class="sxs-lookup"><span data-stu-id="db9e6-194">Create location directives</span></span>

1. <span data-ttu-id="db9e6-195">Vaya a **Gestión de almacenes \> Configurar \> Directivas de ubicación**.</span><span class="sxs-lookup"><span data-stu-id="db9e6-195">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="db9e6-196">En el panel izquierdo, establezca el campo **Tipo de orden de trabajo** a *Tránsito directo*.</span><span class="sxs-lookup"><span data-stu-id="db9e6-196">In the left pane, set the **Work order type** field to *Cross docking*.</span></span>
1. <span data-ttu-id="db9e6-197">En el panel de acción, seleccione **Nuevo** y establezca los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="db9e6-197">On the Action Pane, select **New**, and set the following values:</span></span>

    - <span data-ttu-id="db9e6-198">**Número de secuencia:** *1*</span><span class="sxs-lookup"><span data-stu-id="db9e6-198">**Sequence number:** *1*</span></span>
    - <span data-ttu-id="db9e6-199">**Nombre:** *51 Cross Dock Colocar*</span><span class="sxs-lookup"><span data-stu-id="db9e6-199">**Name:** *51 Cross Dock Put*</span></span>
    - <span data-ttu-id="db9e6-200">**Tipo de trabajo**: *Ubicar*</span><span class="sxs-lookup"><span data-stu-id="db9e6-200">**Work type:** *Put*</span></span>
    - <span data-ttu-id="db9e6-201">**Sitio**: *5*</span><span class="sxs-lookup"><span data-stu-id="db9e6-201">**Site:** *5*</span></span>
    - <span data-ttu-id="db9e6-202">**Almacén**: *51*</span><span class="sxs-lookup"><span data-stu-id="db9e6-202">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="db9e6-203">Seleccione **Guardar** para tener disponible la ficha desplegable **Líneas**.</span><span class="sxs-lookup"><span data-stu-id="db9e6-203">Select **Save** to make the **Lines** FastTab available.</span></span>
1. <span data-ttu-id="db9e6-204">En la ficha desplegable **Líneas**, seleccione **Nuevo** para agregar una línea a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="db9e6-204">On the **Lines** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="db9e6-205">En la nueva línea, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="db9e6-205">On the new line, set the following values:</span></span>

    - <span data-ttu-id="db9e6-206">**Cantidad inicial**: *1*</span><span class="sxs-lookup"><span data-stu-id="db9e6-206">**From quantity:** *1*</span></span>
    - <span data-ttu-id="db9e6-207">**Cantidad final**: *1000000*</span><span class="sxs-lookup"><span data-stu-id="db9e6-207">**To quantity:** *1,000,000*</span></span>

1. <span data-ttu-id="db9e6-208">Seleccione **Guardar** para tener disponible la ficha desplegable **Acciones directivas de ubicación**.</span><span class="sxs-lookup"><span data-stu-id="db9e6-208">Select **Save** to make the **Location Directive Actions** FastTab available.</span></span>
1. <span data-ttu-id="db9e6-209">En la ficha desplegable **Acciones de directiva de ubicación**, seleccione **Nuevo** para agregar una línea a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="db9e6-209">On the **Location Directive Actions** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="db9e6-210">En la nueva línea, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="db9e6-210">On the new line, set the following values:</span></span>

    - <span data-ttu-id="db9e6-211">**Nombre:** *Baydoor*</span><span class="sxs-lookup"><span data-stu-id="db9e6-211">**Name:** *Baydoor*</span></span>
    - <span data-ttu-id="db9e6-212">**Uso de ubicación fija:** *Ubicaciones fijas y no fijas*</span><span class="sxs-lookup"><span data-stu-id="db9e6-212">**Fixed location usage:** *Fixed and non-fixed locations*</span></span>

1. <span data-ttu-id="db9e6-213">Seleccione **Guardar** para tener disponible el botón **Editar consulta** en la barra de herramientas de **Acciones de directiva de ubicación**.</span><span class="sxs-lookup"><span data-stu-id="db9e6-213">Select **Save** to make the **Edit query** button on the **Location Directive Actions** toolbar available.</span></span>
1. <span data-ttu-id="db9e6-214">Seleccione **Editar consulta** para abrir el editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="db9e6-214">Select **Edit query** to open the query editor.</span></span>
1. <span data-ttu-id="db9e6-215">En la pestaña **Rango**, asegúrese de que las siguientes dos líneas estén configuradas:</span><span class="sxs-lookup"><span data-stu-id="db9e6-215">On the **Range** tab, make sure that the following two lines are configured:</span></span>

    - <span data-ttu-id="db9e6-216">Línea 1:</span><span class="sxs-lookup"><span data-stu-id="db9e6-216">Line 1:</span></span>

        - <span data-ttu-id="db9e6-217">**Tabla**: *Ubicaciones*</span><span class="sxs-lookup"><span data-stu-id="db9e6-217">**Table:** *Locations*</span></span>
        - <span data-ttu-id="db9e6-218">**Tabla derivada:** *Ubicaciones*</span><span class="sxs-lookup"><span data-stu-id="db9e6-218">**Derived Table:** *Locations*</span></span>
        - <span data-ttu-id="db9e6-219">**Campo:** *Almacén*</span><span class="sxs-lookup"><span data-stu-id="db9e6-219">**Field:** *Warehouse*</span></span>
        - <span data-ttu-id="db9e6-220">**Criterio:** *51*</span><span class="sxs-lookup"><span data-stu-id="db9e6-220">**Criteria:** *51*</span></span>

    - <span data-ttu-id="db9e6-221">Línea 2:</span><span class="sxs-lookup"><span data-stu-id="db9e6-221">Line 2:</span></span>

        - <span data-ttu-id="db9e6-222">**Tabla**: *Ubicaciones*</span><span class="sxs-lookup"><span data-stu-id="db9e6-222">**Table:** *Locations*</span></span>
        - <span data-ttu-id="db9e6-223">**Tabla derivada:** *Ubicaciones*</span><span class="sxs-lookup"><span data-stu-id="db9e6-223">**Derived Table:** *Locations*</span></span>
        - <span data-ttu-id="db9e6-224">**Campo:** *Ubicación*</span><span class="sxs-lookup"><span data-stu-id="db9e6-224">**Field:** *Location*</span></span>
        - <span data-ttu-id="db9e6-225">**Criterio:** *Baydoor*</span><span class="sxs-lookup"><span data-stu-id="db9e6-225">**Criteria:** *Baydoor*</span></span>

1. <span data-ttu-id="db9e6-226">Seleccione **Aceptar** para cerrar el editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="db9e6-226">Select **OK** to close the query editor.</span></span>

### <a name="create-a-mobile-device-menu-item"></a><span data-ttu-id="db9e6-227">Crear un elemento de menú del dispositivo móvil</span><span class="sxs-lookup"><span data-stu-id="db9e6-227">Create a mobile device menu item</span></span>

1. <span data-ttu-id="db9e6-228">Vaya a **Administración de almacenes \> Configurar \> Dispositivo móvil \> Elementos de menú del dispositivo móvil**.</span><span class="sxs-lookup"><span data-stu-id="db9e6-228">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="db9e6-229">En la lista de elementos de menú en el panel izquierdo, seleccione **Ubicación de compra**.</span><span class="sxs-lookup"><span data-stu-id="db9e6-229">In the list of menu items in the left pane, select **Purchase Put-away**.</span></span>
1. <span data-ttu-id="db9e6-230">Seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="db9e6-230">Select **Edit**.</span></span>
1. <span data-ttu-id="db9e6-231">En la ficha desplegable **Clases de trabajo**, seleccione **Nuevo** para agregar una línea a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="db9e6-231">On the **Work classes** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="db9e6-232">En la nueva línea, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="db9e6-232">On the new line, set the following values:</span></span>

    - <span data-ttu-id="db9e6-233">**Identificador de la clase de trabajo**: *CrossDock*</span><span class="sxs-lookup"><span data-stu-id="db9e6-233">**Work class ID:** *CrossDock*</span></span>
    - <span data-ttu-id="db9e6-234">**Tipo de orden de trabajo:** *Tránsito directo*</span><span class="sxs-lookup"><span data-stu-id="db9e6-234">**Work order type:** *Cross docking*</span></span>

1. <span data-ttu-id="db9e6-235">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="db9e6-235">Select **Save**.</span></span>

## <a name="scenario"></a><span data-ttu-id="db9e6-236">Situación</span><span class="sxs-lookup"><span data-stu-id="db9e6-236">Scenario</span></span>

### <a name="create-a-purchase-order"></a><span data-ttu-id="db9e6-237">Crear un pedido de compra</span><span class="sxs-lookup"><span data-stu-id="db9e6-237">Create a purchase order</span></span>

<span data-ttu-id="db9e6-238">Siga estos pasos para crear una orden de compra como fuente de suministro.</span><span class="sxs-lookup"><span data-stu-id="db9e6-238">Follow these steps to create a purchase order as a source of supply.</span></span>

1. <span data-ttu-id="db9e6-239">Vaya a **Adquisición y abastecimiento \> Pedidos de compra \> Todos los pedidos de compra**.</span><span class="sxs-lookup"><span data-stu-id="db9e6-239">Go to **Procurement and sourcing \> Purchase orders \> All purchase orders**.</span></span>
1. <span data-ttu-id="db9e6-240">En el panel de acciones, haga clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="db9e6-240">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="db9e6-241">En el cuadro de diálogo **Crear pedido de compras**, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="db9e6-241">In the **Create purchase order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="db9e6-242">**Cuenta del proveedor:** *104*</span><span class="sxs-lookup"><span data-stu-id="db9e6-242">**Vendor account:** *104*</span></span>
    - <span data-ttu-id="db9e6-243">**Almacén**: *51*</span><span class="sxs-lookup"><span data-stu-id="db9e6-243">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="db9e6-244">Seleccione **Aceptar** y anote el número de pedido.</span><span class="sxs-lookup"><span data-stu-id="db9e6-244">Select **OK**, and make a note of the order number.</span></span>
1. <span data-ttu-id="db9e6-245">Se agrega una nueva línea a la ficha desplegable **Líneas de orden de compra**.</span><span class="sxs-lookup"><span data-stu-id="db9e6-245">A new line is added to the **Purchase order lines** FastTab.</span></span> <span data-ttu-id="db9e6-246">En esta línea, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="db9e6-246">On this line, set the following values:</span></span>

    - <span data-ttu-id="db9e6-247">**Código de artículo:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="db9e6-247">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="db9e6-248">**Cantidad:** *5*</span><span class="sxs-lookup"><span data-stu-id="db9e6-248">**Quantity:** *5*</span></span>

### <a name="create-a-sales-order"></a><span data-ttu-id="db9e6-249">Crear un pedido de ventas</span><span class="sxs-lookup"><span data-stu-id="db9e6-249">Create a sales order</span></span>

<span data-ttu-id="db9e6-250">Siga estos pasos para crear un pedido de ventas como fuente de demanda.</span><span class="sxs-lookup"><span data-stu-id="db9e6-250">Follow these steps to create a sales order as a source of demand.</span></span>

1. <span data-ttu-id="db9e6-251">Vaya a **Ventas y marketing \> Pedidos de ventas \> Todos los pedidos de ventas**.</span><span class="sxs-lookup"><span data-stu-id="db9e6-251">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="db9e6-252">En el panel de acciones, haga clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="db9e6-252">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="db9e6-253">En el cuadro de diálogo **Crear pedido de ventas**, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="db9e6-253">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="db9e6-254">**Cuenta de cliente:** *US-002*</span><span class="sxs-lookup"><span data-stu-id="db9e6-254">**Customer account:** *US-002*</span></span>
    - <span data-ttu-id="db9e6-255">**Almacén**: *51*</span><span class="sxs-lookup"><span data-stu-id="db9e6-255">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="db9e6-256">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="db9e6-256">Select **OK**.</span></span>
1. <span data-ttu-id="db9e6-257">Se agrega una nueva línea a la ficha desplegable **Líneas de pedido de ventas**.</span><span class="sxs-lookup"><span data-stu-id="db9e6-257">A new line is added to the **Sales order lines** FastTab.</span></span> <span data-ttu-id="db9e6-258">En esta línea, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="db9e6-258">On this line, set the following values:</span></span>

    - <span data-ttu-id="db9e6-259">**Código de artículo:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="db9e6-259">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="db9e6-260">**Cantidad:** *3*</span><span class="sxs-lookup"><span data-stu-id="db9e6-260">**Quantity:** *3*</span></span>

### <a name="create-planned-cross-docking"></a><span data-ttu-id="db9e6-261">Crear tránsito directo planificado</span><span class="sxs-lookup"><span data-stu-id="db9e6-261">Create planned cross-docking</span></span>

<span data-ttu-id="db9e6-262">Siga estos pasos para crear el tránsito directo planificado a partir del pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="db9e6-262">Follow these steps to create the planned cross-docking from the sales order.</span></span>

1. <span data-ttu-id="db9e6-263">En la página **Detalles del pedido de ventas** para el pedido de ventas que acaba de crear, en el Panel de acciones, en la pestaña **Almacén**, en el grupo **Acciones**, seleccione **Liberar al almacén**.</span><span class="sxs-lookup"><span data-stu-id="db9e6-263">In the **Sales order details** page for the sales order that you just created, on the Action Pane, on the **Warehouse** tab, in the **Actions** group, select **Release to warehouse**.</span></span>

    <span data-ttu-id="db9e6-264">La acción de liberación al almacén crea una línea de envío y carga para la línea de pedido de ventas e intenta asignar inventario.</span><span class="sxs-lookup"><span data-stu-id="db9e6-264">The release to warehouse action creates a shipment and load line for the sales order line, and tries to allocate inventory.</span></span>
    
    <span data-ttu-id="db9e6-265">Recibirá un mensaje informativo.</span><span class="sxs-lookup"><span data-stu-id="db9e6-265">You receive an informational message.</span></span> <span data-ttu-id="db9e6-266">También recibirá el siguiente mensaje de advertencia: "No se creó ningún trabajo para la oleada XXXX.</span><span class="sxs-lookup"><span data-stu-id="db9e6-266">You also receive the following warning message: "No work was created for wave XXXX.</span></span> <span data-ttu-id="db9e6-267">Consulte el registro del historial de creación de trabajo para obtener más detalles".</span><span class="sxs-lookup"><span data-stu-id="db9e6-267">See the work creation history log for details."</span></span> <span data-ttu-id="db9e6-268">Se espera este comportamiento, porque no hay inventario en el almacén.</span><span class="sxs-lookup"><span data-stu-id="db9e6-268">This behavior is expected, because there is no inventory in the warehouse.</span></span>

1. <span data-ttu-id="db9e6-269">En la ficha desplegable **Líneas de pedido de ventas**, en el menú **Almacén**, seleccione **Detalles del envío**.</span><span class="sxs-lookup"><span data-stu-id="db9e6-269">On the **Sales order lines** FastTab, on the **Warehouse** menu, select **Shipment details**.</span></span>

    <span data-ttu-id="db9e6-270">Aparecerá la página **Detalles del envío** y muestra el envío que se creó para el pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="db9e6-270">The **Shipment details** page appears and shows the shipment that was created for the sales order.</span></span>

1. <span data-ttu-id="db9e6-271">En la ficha desplegable **Líneas de carga**, observe que el campo **Cantidad prevista de tránsito directo** se establece en *3*.</span><span class="sxs-lookup"><span data-stu-id="db9e6-271">On the **Load lines** FastTab, notice that the **Planned cross docking quantity** field is set to *3*.</span></span> <span data-ttu-id="db9e6-272">Debido a que no había inventario disponible en el almacén, pero una fuente de suministro válida llegará dentro de la ventana de tiempo definida en la plantilla de tránsito directo, se creó la cantidad de tránsito directo.</span><span class="sxs-lookup"><span data-stu-id="db9e6-272">Because no inventory was available in the warehouse, but a valid supply source will arrive within the time window that is defined in the cross-docking template, the cross-docking quantity was created.</span></span>
1. <span data-ttu-id="db9e6-273">En la ficha desplegable **Líneas de carga**, seleccione **Tránsito directo planeado** para ver los detalles del tránsito directo que se creó.</span><span class="sxs-lookup"><span data-stu-id="db9e6-273">On the **Load lines** FastTab, select **Planned cross docking** to view the details of the cross-docking that was created.</span></span>

## <a name="process-the-cross-docking"></a><span data-ttu-id="db9e6-274">Procesar el tránsito directo</span><span class="sxs-lookup"><span data-stu-id="db9e6-274">Process the cross-docking</span></span>

### <a name="purchase-order-receiving-on-the-warehousing-mobile-app"></a><span data-ttu-id="db9e6-275">Pedido de compra recibido en la aplicación móvil del almacén</span><span class="sxs-lookup"><span data-stu-id="db9e6-275">Purchase order receiving on the warehousing mobile app</span></span>

<span data-ttu-id="db9e6-276">El sistema recibirá la cantidad de 5 del pedido de compra en la ubicación de recepción y creará dos partes de trabajo.</span><span class="sxs-lookup"><span data-stu-id="db9e6-276">The system will receive the quantity of 5 from the purchase order into the receiving location and create two pieces of work.</span></span>

<span data-ttu-id="db9e6-277">La primera identificación de trabajo que se crea tiene un valor de **Tipo de orden de trabajo** *Tránsito directo* y está vinculado al pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="db9e6-277">The first work ID that is created has a **Work order type** value of *Cross docking* and is linked to the sales order.</span></span> <span data-ttu-id="db9e6-278">Tiene una cantidad de 3 y se dirige a la ubicación de envío final para que pueda enviarse de inmediato.</span><span class="sxs-lookup"><span data-stu-id="db9e6-278">It has a quantity of 3 and is directed to the final shipping location so that it can be shipped out immediately.</span></span>

<span data-ttu-id="db9e6-279">La segunda identificación de trabajo que se crea tiene un valor de **Tipo de orden de trabajo** *Pedidos de compra* y está vinculado al pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="db9e6-279">The second work ID that is created has a **Work order type** value of *Purchase orders* and is linked to the purchase order.</span></span> <span data-ttu-id="db9e6-280">Tiene la cantidad restante de 2 que no se cruzó y se dirige al almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="db9e6-280">It has the remaining quantity of 2 that wasn't cross-docked and is directed to put-away to storage.</span></span>

1. <span data-ttu-id="db9e6-281">Inicie sesión en el dispositivo móvil como un usuario en el almacén *51*.</span><span class="sxs-lookup"><span data-stu-id="db9e6-281">Sign in to the mobile device as a user in warehouse *51*.</span></span>
1. <span data-ttu-id="db9e6-282">Vaya **Entrante \> Recibir compra**.</span><span class="sxs-lookup"><span data-stu-id="db9e6-282">Go to **Inbound \> Purchase Receive**.</span></span>
1. <span data-ttu-id="db9e6-283">En el campo **PONUM**, introduzca su número de orden de compra.</span><span class="sxs-lookup"><span data-stu-id="db9e6-283">In the **PONum** field, enter your purchase order number.</span></span>
1. <span data-ttu-id="db9e6-284">En el campo **Cantidad**, especifique *5*.</span><span class="sxs-lookup"><span data-stu-id="db9e6-284">In the **Qty** field, enter *5*.</span></span>
1. <span data-ttu-id="db9e6-285">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="db9e6-285">Select **OK**.</span></span>
1. <span data-ttu-id="db9e6-286">En la página siguiente, establezca el campo **Artículo** a *A0001*.</span><span class="sxs-lookup"><span data-stu-id="db9e6-286">On the next page, set the **Item** field to *A0001*.</span></span>
1. <span data-ttu-id="db9e6-287">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="db9e6-287">Select **OK**.</span></span>
1. <span data-ttu-id="db9e6-288">En la página siguiente, confirme los valores **PONUM**, **Artículo** y **Cantidad** seleccionando **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="db9e6-288">On the next page, confirm the **PONum**, **Item**, and **Qty** values by selecting **OK**.</span></span>

    <span data-ttu-id="db9e6-289">Recibe un mensaje "Trabajo completado".</span><span class="sxs-lookup"><span data-stu-id="db9e6-289">You receive a "Work Completed" message.</span></span>

1. <span data-ttu-id="db9e6-290">Seleccione **Cancelar** para salir.</span><span class="sxs-lookup"><span data-stu-id="db9e6-290">Select **Cancel** to exit.</span></span>

### <a name="put-away-to-cross-docking-and-bulk"></a><span data-ttu-id="db9e6-291">Ubicación a tránsito directo y a granel</span><span class="sxs-lookup"><span data-stu-id="db9e6-291">Put-away to cross-docking and bulk</span></span>

<span data-ttu-id="db9e6-292">Actualmente, ambas identificaciones de trabajo tienen la misma matrícula de entidad objetivo.</span><span class="sxs-lookup"><span data-stu-id="db9e6-292">Currently, both work IDs have the same target license plate.</span></span> <span data-ttu-id="db9e6-293">Para completar los siguientes pasos, debe obtener la identificación del trabajo y la identificación de la matrícula de identidad.</span><span class="sxs-lookup"><span data-stu-id="db9e6-293">To complete the next steps, you must get the work ID and the target license plate ID.</span></span> <span data-ttu-id="db9e6-294">Puede obtener esta información de los detalles de trabajo para la línea de orden de compra y la línea de pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="db9e6-294">You can get this information from the work details for the purchase order line and the sales order line.</span></span> <span data-ttu-id="db9e6-295">Alternativamente, puede ir a **Gestión de almacenes \> Trabajo \> Detalles del trabajo** y filtrar para el trabajo donde el valor de **Almacén** es *51*.</span><span class="sxs-lookup"><span data-stu-id="db9e6-295">Alternately, you can go to **Warehouse management \> Work \> Work details** and filter for work where the **Warehouse** value is *51*.</span></span>

1. <span data-ttu-id="db9e6-296">En el dispositivo móvil, vaya a **Entrante \> Ubicación de compra** e introduzca la matricula de identidad de destino del trabajo.</span><span class="sxs-lookup"><span data-stu-id="db9e6-296">On the mobile device, go to **Inbound \> Purchase put-away**, and enter the target license plate from the work.</span></span>
1. <span data-ttu-id="db9e6-297">En campo **Identificación**, introduzca la identificación de la matrícula de entidad de destino de los detalles del trabajo.</span><span class="sxs-lookup"><span data-stu-id="db9e6-297">In the **ID** field, enter the target license plate ID from the work details.</span></span>

    <span data-ttu-id="db9e6-298">La página de selección de tránsito directo muestra la ubicación de selección (*RECV*), matrícula de entidad objetivo (*matrícula de entidad*), artículo (*A0001*) y cantidad (*3*).</span><span class="sxs-lookup"><span data-stu-id="db9e6-298">The cross-docking pick page shows the picking location (*RECV*), target license plate (*license plate*), item (*A0001*), and quantity (*3*).</span></span>

1. <span data-ttu-id="db9e6-299">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="db9e6-299">Select **OK**.</span></span>
1. <span data-ttu-id="db9e6-300">En el campo **LP objetivo**, introduzca una matrícula de entidad de destino para la identificación de la matrícula que debe colocarse (tránsito directo) en la ubicación de envío.</span><span class="sxs-lookup"><span data-stu-id="db9e6-300">In the **Target LP** field, enter a target license plate for the license plate ID that should be put (cross-docked) to the shipping location.</span></span> <span data-ttu-id="db9e6-301">Puede seleccionar cualquier identificación de matrícula de su elección.</span><span class="sxs-lookup"><span data-stu-id="db9e6-301">You can select any license plate ID of your choice.</span></span>
1. <span data-ttu-id="db9e6-302">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="db9e6-302">Select **OK**.</span></span>
1. <span data-ttu-id="db9e6-303">En la página siguiente, en campo **Identificación**, introduzca la identificación de la matrícula de entidad de destino.</span><span class="sxs-lookup"><span data-stu-id="db9e6-303">On the next page, in the **ID** field, enter the target license plate ID.</span></span>
1. <span data-ttu-id="db9e6-304">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="db9e6-304">Select **OK**.</span></span>
1. <span data-ttu-id="db9e6-305">Confirme el trabajo para elegir la cantidad restante de 2 y luego seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="db9e6-305">Confirm the work for picking the remaining quantity of 2, and then select **OK**.</span></span>
1. <span data-ttu-id="db9e6-306">En la página siguiente, seleccione **Hecho** para finalizar el proceso de selección y comenzar el proceso de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="db9e6-306">On the next page, select **Done** to end the picking process and begin the put-away process.</span></span>

    <span data-ttu-id="db9e6-307">La aplicación móvil le presenta la ubicación y la matrícula de entidad para colocar el artículo.</span><span class="sxs-lookup"><span data-stu-id="db9e6-307">The mobile app presents you with the location and license plate to put the item to.</span></span>

1. <span data-ttu-id="db9e6-308">Confirme el almacenamiento a granel **Colocar** seleccionando **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="db9e6-308">Confirm the bulk storage **Put** by selecting **OK**.</span></span>
1. <span data-ttu-id="db9e6-309">En la página siguiente, confirme el tránsito directo **Colocar** seleccionando **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="db9e6-309">On the next page, confirm the cross-docking **Put** by selecting **OK**.</span></span>

    <span data-ttu-id="db9e6-310">Recibe un mensaje "Trabajo completado".</span><span class="sxs-lookup"><span data-stu-id="db9e6-310">You receive a "Work Completed" message.</span></span>

1. <span data-ttu-id="db9e6-311">Seleccione **Cancelar** para salir.</span><span class="sxs-lookup"><span data-stu-id="db9e6-311">Select **Cancel** to exit.</span></span>

<span data-ttu-id="db9e6-312">La siguiente ilustración muestra cómo puede aparecer el trabajo de tránsito directo completado en Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="db9e6-312">The following illustration shows how the completed cross-docking work might appear in Microsoft Dynamics 365 Supply Chain Management.</span></span>

<span data-ttu-id="db9e6-313">![Trabajo de tránsito directo completado](media/PlannedCrossDockingWork.png "Trabajo de tránsito directo completado")</span><span class="sxs-lookup"><span data-stu-id="db9e6-313">![Cross-docking work completed](media/PlannedCrossDockingWork.png "Cross-docking work completed")</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]