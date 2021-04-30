---
title: Tránsito directo planificado
description: Este tema describe la planificación avanzada del tránsito directo, donde la cantidad de inventario que se requiere para un pedido se dirige directamente desde la recepción o la creación hasta el muelle de salida o el área de preparación correcta. Todo el inventario restante de la fuente entrante se dirige a la ubicación de almacenamiento correcta a través del proceso regular de almacenamiento.
author: Mirzaab
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSCrossDockingTemplate, WHSLoadPostMethod, WHSWorkClass, WHSWorkTemplateTable, WHSLocDirTable, WHSPlannedCrossDocking
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: 11e044e04e05c68af676bf97e6085e9975da5c1d
ms.sourcegitcommit: bef7bd2aac00d7eb837fd275d383b7a5c3f1c1ee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/19/2021
ms.locfileid: "5911257"
---
# <a name="planned-cross-docking"></a><span data-ttu-id="54d47-104">Tránsito directo planificado</span><span class="sxs-lookup"><span data-stu-id="54d47-104">Planned cross-docking</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="54d47-105">Este tema describe la planificación avanzada del tránsito directo.</span><span class="sxs-lookup"><span data-stu-id="54d47-105">This topic describes advanced planned cross-docking.</span></span> <span data-ttu-id="54d47-106">El tránsito directo es un proceso de almacén, donde la cantidad de inventario que se requiere para un pedido se dirige directamente desde la recepción o la creación hasta el muelle de salida o el área de preparación correcta.</span><span class="sxs-lookup"><span data-stu-id="54d47-106">Cross-docking is a warehouse process where the inventory quantity that is required for an order is directed straight from receipt or creation to the correct outbound dock or staging area.</span></span> <span data-ttu-id="54d47-107">Todo el inventario restante de la fuente entrante se dirige a la ubicación de almacenamiento correcta a través del proceso regular de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="54d47-107">All remaining inventory from the inbound source is directed to the correct storage location through the regular put-away process.</span></span>

<span data-ttu-id="54d47-108">El tránsito directo permite a los trabajadores omitir la recogida entrante y la selección saliente del inventario que ya está marcado para un pedido saliente.</span><span class="sxs-lookup"><span data-stu-id="54d47-108">Cross-docking lets workers skip inbound put-away and outbound picking of inventory that is already marked for an outbound order.</span></span> <span data-ttu-id="54d47-109">Por lo tanto, el número de veces que se toca el inventario se minimiza, siempre que sea posible.</span><span class="sxs-lookup"><span data-stu-id="54d47-109">Therefore, the number of times that inventory is touched is minimized, where possible.</span></span> <span data-ttu-id="54d47-110">Además, debido a que hay menos interacción con el sistema, se incrementan los ahorros de tiempo y espacio en el piso del almacén.</span><span class="sxs-lookup"><span data-stu-id="54d47-110">Additionally, because there is less interaction with the system, time and space savings on the warehouse shop floor are increased.</span></span>

<span data-ttu-id="54d47-111">Para poder ejecutar el tránsito directo, debe configurar una nueva plantilla de tránsito directo, donde se especifique la fuente de suministro y otros conjuntos de requisitos para el tránsito directo.</span><span class="sxs-lookup"><span data-stu-id="54d47-111">Before you can run cross-docking, you must configure a new cross-docking template, where the supply source and other sets of requirements for cross-docking are specified.</span></span> <span data-ttu-id="54d47-112">A medida que se crea la orden de salida, la línea debe marcarse contra una orden de entrada que contiene el mismo artículo.</span><span class="sxs-lookup"><span data-stu-id="54d47-112">As the outbound order is created, the line must be marked against an inbound order that contains the same item.</span></span> <span data-ttu-id="54d47-113">Puede seleccionar el campo de código de directiva en la plantilla de cross-docking, de forma similar a la forma en que configura el reabastecimiento y las órdenes de compra.</span><span class="sxs-lookup"><span data-stu-id="54d47-113">You can select the directive code field on the cross-docking template, similar to the way you set up replenishment and purchase orders.</span></span>

<span data-ttu-id="54d47-114">En el momento de la recepción de la orden entrante, la configuración de tránsito directo identifica automáticamente la necesidad de tránsito directo y crea el trabajo de movimiento para la cantidad requerida, en función de la configuración de la directiva de ubicación.</span><span class="sxs-lookup"><span data-stu-id="54d47-114">At the time of inbound order receiving, the cross-docking setup automatically identifies the need for cross-docking and creates the movement work for the required quantity, based on the setup of the location directive.</span></span>

> [!NOTE]
> <span data-ttu-id="54d47-115">Las transacciones de inventario son *no* sin registrar cuando se cancela el trabajo de tránsito directo, incluso si la configuración de esta capacidad está activada en los parámetros de gestión de Almacén.</span><span class="sxs-lookup"><span data-stu-id="54d47-115">Inventory transactions are *not* unregistered when crossing-dock work is canceled, even if the setting for this capability is turned on in Warehouse management parameters.</span></span>

## <a name="turn-on-the-planned-cross-docking-features"></a><span data-ttu-id="54d47-116">Active las funciones de tránsito directo planificado</span><span class="sxs-lookup"><span data-stu-id="54d47-116">Turn on the planned cross docking features</span></span>

<span data-ttu-id="54d47-117">Si su sistema aún no incluye las funciones descritas en este tema, vaya a [Gestión de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) y active las características siguientes por este orden:</span><span class="sxs-lookup"><span data-stu-id="54d47-117">If your system doesn't already include the features described in this topic, go to [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) and turn on the following features in the following order:</span></span>

1. <span data-ttu-id="54d47-118">*Tránsito directo planificado*</span><span class="sxs-lookup"><span data-stu-id="54d47-118">*Planned cross docking*</span></span>
1. <span data-ttu-id="54d47-119">*Plantillas de tránsito directo con directivas de ubicación*</span><span class="sxs-lookup"><span data-stu-id="54d47-119">*Cross docking templates with location directives*</span></span>
    > [!NOTE]
    > <span data-ttu-id="54d47-120">Esta característica habilita el cmpo **Código de directiva** que se especificará en la plantilla de cross-docking, similar a la forma en que configura las plantillas de reabastecimiento.</span><span class="sxs-lookup"><span data-stu-id="54d47-120">This feature enables the **Directive code** field to be specified on the cross-docking template, similar to the way you set up replenishment templates.</span></span> <span data-ttu-id="54d47-121">Habilitar esta función le impide agregar un código de directiva en las líneas de la plantilla de trabajo de cross-docking para la línea *Put*.</span><span class="sxs-lookup"><span data-stu-id="54d47-121">Enabling this feature prevents you from adding a directive code on the cross-docking work template lines for the final *Put* line.</span></span> <span data-ttu-id="54d47-122">Esto asegura que la ubicación de colocación final se pueda determinar durante la creación del trabajo antes de considerar las plantillas de trabajo.</span><span class="sxs-lookup"><span data-stu-id="54d47-122">This ensures that the final put location can be determined during work creation before considering work templates.</span></span>

## <a name="setup"></a><span data-ttu-id="54d47-123">Configurar</span><span class="sxs-lookup"><span data-stu-id="54d47-123">Setup</span></span>

### <a name="regenerate-load-posting-methods"></a><span data-ttu-id="54d47-124">Regenerar métodos de registro de carga</span><span class="sxs-lookup"><span data-stu-id="54d47-124">Regenerate load posting methods</span></span>

<span data-ttu-id="54d47-125">El tránsito directo planificado se implementa como un método de registro de carga.</span><span class="sxs-lookup"><span data-stu-id="54d47-125">Planned cross-docking is implemented as a load posting method.</span></span> <span data-ttu-id="54d47-126">Después de activar la función, debe volver a generar los métodos.</span><span class="sxs-lookup"><span data-stu-id="54d47-126">After you turn on the feature, you must regenerate the methods.</span></span>

1. <span data-ttu-id="54d47-127">Vaya a **Administración de almacenes \> Configuración \> Métodos de registro de carga**.</span><span class="sxs-lookup"><span data-stu-id="54d47-127">Go to **Warehouse management \> Setup \> Load posting methods**.</span></span>
1. <span data-ttu-id="54d47-128">En el panel acciones, seleccione **Regenerar métodos**.</span><span class="sxs-lookup"><span data-stu-id="54d47-128">On the Action Pane, select **Regenerate methods**.</span></span>

    <span data-ttu-id="54d47-129">Cuando se completa la regeneración, debería ver un método que tiene un **Nombre del método** con el valor de *planCrossDocking*.</span><span class="sxs-lookup"><span data-stu-id="54d47-129">When regeneration is completed, you should see a method that has a **Method name** value of *planCrossDocking*.</span></span>

1. <span data-ttu-id="54d47-130">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="54d47-130">Close the page.</span></span>

### <a name="create-a-cross-docking-template"></a><span data-ttu-id="54d47-131">Cree una plantilla de tránsito directo</span><span class="sxs-lookup"><span data-stu-id="54d47-131">Create a cross-docking template</span></span>

1. <span data-ttu-id="54d47-132">Vaya a **Gestión de almacenes \> Configuración \> Trabajo \> Plantillas de tránsito directo**.</span><span class="sxs-lookup"><span data-stu-id="54d47-132">Go to **Warehouse management \> Setup \> Work \> Cross docking templates**.</span></span>
1. <span data-ttu-id="54d47-133">En el Panel de acciones, haga clic en **Nuevo** para crear una plantilla.</span><span class="sxs-lookup"><span data-stu-id="54d47-133">On the Action Pane, select **New** to create a template.</span></span>
1. <span data-ttu-id="54d47-134">Establezca los siguientes valores en el encabezado:</span><span class="sxs-lookup"><span data-stu-id="54d47-134">In the header, set the following values:</span></span>

    - <span data-ttu-id="54d47-135">**Secuencia**: *1*</span><span class="sxs-lookup"><span data-stu-id="54d47-135">**Sequence:** *1*</span></span>

        <span data-ttu-id="54d47-136">Este campo define el orden en que se evalúan las plantillas.</span><span class="sxs-lookup"><span data-stu-id="54d47-136">This field defines the order that templates are evaluated in.</span></span>

    - <span data-ttu-id="54d47-137">**Identificación de plantilla de tránsito directo:** *51*</span><span class="sxs-lookup"><span data-stu-id="54d47-137">**Cross docking template ID:** *51*</span></span>
    - <span data-ttu-id="54d47-138">**Descripción:** *Almacén 51*</span><span class="sxs-lookup"><span data-stu-id="54d47-138">**Description:** *Warehouse 51*</span></span>
    - <span data-ttu-id="54d47-139">**Directiva de liberación de demanda:** *Antes del recibo de suministro*</span><span class="sxs-lookup"><span data-stu-id="54d47-139">**Demand release policy:** *Before supply receipt*</span></span>
    - <span data-ttu-id="54d47-140">**Almacén**: *51*</span><span class="sxs-lookup"><span data-stu-id="54d47-140">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="54d47-141">La configuración en la ficha desplegable **Planificación** controla cómo funciona la plantilla.</span><span class="sxs-lookup"><span data-stu-id="54d47-141">The setup on the **Planning** FastTab controls how the template works.</span></span> <span data-ttu-id="54d47-142">Establezca los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="54d47-142">Set the following values:</span></span>

    - <span data-ttu-id="54d47-143">**Requisitos de demanda:** *Ninguno*</span><span class="sxs-lookup"><span data-stu-id="54d47-143">**Demand requirements:** *None*</span></span>

        <span data-ttu-id="54d47-144">Este campo define los requisitos del inventario de demanda.</span><span class="sxs-lookup"><span data-stu-id="54d47-144">This field defines the requirements of the demand inventory.</span></span> <span data-ttu-id="54d47-145">Si la demanda debe estar vinculada a la oferta antes del lanzamiento, seleccione *Calificación*.</span><span class="sxs-lookup"><span data-stu-id="54d47-145">If the demand must be linked to the supply before release, select *Marking*.</span></span> <span data-ttu-id="54d47-146">Si la demanda debe reservarse para el pedido antes del lanzamiento, seleccione *Reserva de pedidos*.</span><span class="sxs-lookup"><span data-stu-id="54d47-146">If the demand must be order-reserved against the supply before release, select *Order reservation*.</span></span>

    - <span data-ttu-id="54d47-147">**Tipo de ubicación:** *Ubicaciones de envío*</span><span class="sxs-lookup"><span data-stu-id="54d47-147">**Locating type:** *Shipment locations*</span></span>

        <span data-ttu-id="54d47-148">Este campo define si el trabajo de tránsito directo debe usar las ubicaciones de carga / preparación del envío, o si debe usar directivas de ubicación para encontrar sus propias ubicaciones de almacenamiento provisional / carga.</span><span class="sxs-lookup"><span data-stu-id="54d47-148">This field defines whether the cross-docking work should use the staging/load locations from the shipment, or whether it should use location directives to find its own staging/load locations.</span></span>

    - <span data-ttu-id="54d47-149">**Plantilla de trabajo**: deje este campo en blanco.</span><span class="sxs-lookup"><span data-stu-id="54d47-149">**Work template:** Leave this field blank.</span></span>

        <span data-ttu-id="54d47-150">Este campo define la plantilla de trabajo que debe usarse cuando se crea trabajo de tránsito directo.</span><span class="sxs-lookup"><span data-stu-id="54d47-150">This field defines the work template that should be used when cross-docking work is created.</span></span>

    - <span data-ttu-id="54d47-151">**Revalidar con el recibo de suministro:** *No*</span><span class="sxs-lookup"><span data-stu-id="54d47-151">**Revalidate on supply receipt:** *No*</span></span>

        <span data-ttu-id="54d47-152">Esta opción define si el suministro debe revalidarse durante la recepción.</span><span class="sxs-lookup"><span data-stu-id="54d47-152">This option defines whether the supply should be revalidated during receipt.</span></span> <span data-ttu-id="54d47-153">Si esta opción está establecida en *Sí*, se verifican tanto la ventana de tiempo máximo como el rango de días de vencimiento.</span><span class="sxs-lookup"><span data-stu-id="54d47-153">If this option is set to *Yes*, both the maximum time window and the expiration days range are checked.</span></span>

    - <span data-ttu-id="54d47-154">**Código de directiva:** deje en blanco este campo</span><span class="sxs-lookup"><span data-stu-id="54d47-154">**Directive code:** Leave this field blank</span></span>

        <span data-ttu-id="54d47-155">Esta opción está habilitada por la característica *Plantillas de cross docking con directivas de ubicación*.</span><span class="sxs-lookup"><span data-stu-id="54d47-155">This option is enabled by the *Cross docking templates with location directives* feature.</span></span> <span data-ttu-id="54d47-156">El sistema utiliza directivas de ubicación para ayudar a determinar la mejor ubicación para mover el inventario de cross-docking.</span><span class="sxs-lookup"><span data-stu-id="54d47-156">The system uses location directives to help determine the best location to move cross-docking inventory to.</span></span> <span data-ttu-id="54d47-157">Puede configurarlo asignando un código de directiva a cada plantilla de cross-docking relevante.</span><span class="sxs-lookup"><span data-stu-id="54d47-157">You can set it up by assigning a directive code to each relevant cross-docking template.</span></span> <span data-ttu-id="54d47-158">Si se establece un código de directiva, cuando haya que generar trabajo el sistema buscará las directivas de ubicación por código de directiva cuando se genera trabajo.</span><span class="sxs-lookup"><span data-stu-id="54d47-158">If a directive code is set, the system will search location directives by directive code when work is generated.</span></span> <span data-ttu-id="54d47-159">De esta forma, puede limitar las directivas de ubicación que se utilizan para una plantilla de cross-docking en particular.</span><span class="sxs-lookup"><span data-stu-id="54d47-159">In this way, you can limit location directives that are used for a particular cross-docking template.</span></span>

    - <span data-ttu-id="54d47-160">**Validar ventana de tiempo:** *Sí*</span><span class="sxs-lookup"><span data-stu-id="54d47-160">**Validate time window:** *Yes*</span></span>

        <span data-ttu-id="54d47-161">Esta opción define si se debe evaluar la ventana de tiempo máximo cuando se selecciona una fuente de suministro.</span><span class="sxs-lookup"><span data-stu-id="54d47-161">This option defines whether the maximum time window should be evaluated when a supply source is selected.</span></span> <span data-ttu-id="54d47-162">Si esta opción está establecida en *Sí*, los campos relacionados con las ventanas de tiempo máximo y mínimo están disponibles.</span><span class="sxs-lookup"><span data-stu-id="54d47-162">If this option is set to *Yes*, the fields that are related to the maximum and minimum time windows become available.</span></span>

    - <span data-ttu-id="54d47-163">**Ventana de tiempo máxima:** *5*</span><span class="sxs-lookup"><span data-stu-id="54d47-163">**Maximum time window:** *5*</span></span>

        <span data-ttu-id="54d47-164">Este campo define el período máximo permitido entre la llegada del suministro y la salida de demanda.</span><span class="sxs-lookup"><span data-stu-id="54d47-164">This field defines the maximum period that is allowed between supply arrival and demand departure.</span></span>

    - <span data-ttu-id="54d47-165">**Unidad de ventana de tiempo máximo:** *Días*</span><span class="sxs-lookup"><span data-stu-id="54d47-165">**Maximum time window unit:** *Days*</span></span>
    - <span data-ttu-id="54d47-166">**Ventana de tiempo mínima:** *0*</span><span class="sxs-lookup"><span data-stu-id="54d47-166">**Minimum time window:** *0*</span></span>

        <span data-ttu-id="54d47-167">Este campo define el período mínimo permitido entre la llegada del suministro y la salida de demanda.</span><span class="sxs-lookup"><span data-stu-id="54d47-167">This field defines the minimum period that is allowed between supply arrival and demand departure.</span></span>

    - <span data-ttu-id="54d47-168">**Unidad de ventana de tiempo mínimo:** *Días*</span><span class="sxs-lookup"><span data-stu-id="54d47-168">**Minimum time window unit:** *Days*</span></span>
    - <span data-ttu-id="54d47-169">**Intervalo de días de caducidad:** *0*</span><span class="sxs-lookup"><span data-stu-id="54d47-169">**Expiration days range:** *0*</span></span>

        <span data-ttu-id="54d47-170">*Criterios de primera caducidad, primera salida (FEFO):* este campo define el número máximo de días entre la fecha de vencimiento del primer lote que está actualmente en el almacén y el lote que se está recibiendo.</span><span class="sxs-lookup"><span data-stu-id="54d47-170">*First expiry first out (FEFO) criteria:* This field defines the maximum number of days between the expiration date of the first-expiring batch that is currently in the warehouse and the batch that is being received.</span></span>

1. <span data-ttu-id="54d47-171">En la ficha desplegable **Fuentes de suministro**, especifique los tipos de suministro que son válidos para esta plantilla.</span><span class="sxs-lookup"><span data-stu-id="54d47-171">On the **Supply sources** FastTab, you specify the types of supply that are valid for this template.</span></span> <span data-ttu-id="54d47-172">Seleccione **Nuevo** y establezca los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="54d47-172">Select **New**, and then set the following values:</span></span>

    - <span data-ttu-id="54d47-173">**Número de secuencia:** *1*</span><span class="sxs-lookup"><span data-stu-id="54d47-173">**Sequence number:** *1*</span></span>
    - <span data-ttu-id="54d47-174">**Fuente de suministro:** *Orden de compra*</span><span class="sxs-lookup"><span data-stu-id="54d47-174">**Supply source:** *Purchase order*</span></span>

### <a name="create-a-work-class"></a><span data-ttu-id="54d47-175">Crear una clase de trabajo</span><span class="sxs-lookup"><span data-stu-id="54d47-175">Create a work class</span></span>

1. <span data-ttu-id="54d47-176">Vaya a **Gestión de almacenes \> Configurar \> Trabajo \> Clases de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="54d47-176">Go to **Warehouse management \> Setup \> Work \> Work classes**.</span></span>
1. <span data-ttu-id="54d47-177">En el Panel de acciones, seleccione **Nuevo** para crear una clase de trabajo.</span><span class="sxs-lookup"><span data-stu-id="54d47-177">On the Action Pane, select **New** to create a work class.</span></span>
1. <span data-ttu-id="54d47-178">Establezca los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="54d47-178">Set the following values:</span></span>

    - <span data-ttu-id="54d47-179">**Identificador de la clase de trabajo**: *CrossDock*</span><span class="sxs-lookup"><span data-stu-id="54d47-179">**Work class ID:** *CrossDock*</span></span>
    - <span data-ttu-id="54d47-180">**Descripción:** *Tránsito directo*</span><span class="sxs-lookup"><span data-stu-id="54d47-180">**Description:** *Cross Dock*</span></span>
    - <span data-ttu-id="54d47-181">**Tipo de orden de trabajo:** *Tránsito directo*</span><span class="sxs-lookup"><span data-stu-id="54d47-181">**Work order type:** *Cross docking*</span></span>

### <a name="create-a-work-template"></a><span data-ttu-id="54d47-182">Crear una plantilla de trabajo</span><span class="sxs-lookup"><span data-stu-id="54d47-182">Create a work template</span></span>

1. <span data-ttu-id="54d47-183">Vaya a **Administración de almacenes \> Configuración \> Trabajo \> Plantillas de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="54d47-183">Go to **Warehouse management \> Setup \> Work \> Work templates**.</span></span>
1. <span data-ttu-id="54d47-184">Establezca el campo **Tipo de orden de trabajo** a *Tránsito directo*.</span><span class="sxs-lookup"><span data-stu-id="54d47-184">Set the **Work order type** field to *Cross docking*.</span></span>
1. <span data-ttu-id="54d47-185">En el Panel de acciones, seleccione **Nuevo** para agregar una línea a la pestaña **Resumen**.</span><span class="sxs-lookup"><span data-stu-id="54d47-185">On the Action Pane, select **New** to add a line to the **Overview** tab.</span></span>
1. <span data-ttu-id="54d47-186">En la nueva línea, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="54d47-186">On the new line, set the following values:</span></span>

    - <span data-ttu-id="54d47-187">**Número de secuencia:** *1*</span><span class="sxs-lookup"><span data-stu-id="54d47-187">**Sequence number:** *1*</span></span>
    - <span data-ttu-id="54d47-188">**Plantilla de trabajo:** *51 Cross Dock*</span><span class="sxs-lookup"><span data-stu-id="54d47-188">**Work template:** *51 Cross Dock*</span></span>
    - <span data-ttu-id="54d47-189">**Descripción de la plantilla de trabajo:** *51 Cross Dock*</span><span class="sxs-lookup"><span data-stu-id="54d47-189">**Work template description:** *51 Cross Dock*</span></span>

1. <span data-ttu-id="54d47-190">Seleccione **Guardar** para tener disponible la ficha desplegable **Detalles de plantilla de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="54d47-190">Select **Save** to make the **Work Template Details** FastTab available.</span></span>
1. <span data-ttu-id="54d47-191">En la ficha desplegable **Detalles de plantilla de trabajo**, seleccione **Nuevo** para agregar una línea a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="54d47-191">On the **Work Template Details** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="54d47-192">En la nueva línea, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="54d47-192">On the new line, set the following values:</span></span>

    - <span data-ttu-id="54d47-193">**Tipo de trabajo**: *Recoger*</span><span class="sxs-lookup"><span data-stu-id="54d47-193">**Work type:** *Pick*</span></span>
    - <span data-ttu-id="54d47-194">**Identificador de la clase de trabajo**: *CrossDock*</span><span class="sxs-lookup"><span data-stu-id="54d47-194">**Work class ID:** *CrossDock*</span></span>

1. <span data-ttu-id="54d47-195">Seleccione **Nuevo** para agregar otra línea y establezca los siguientes valores en ella:</span><span class="sxs-lookup"><span data-stu-id="54d47-195">Select **New** to add another line, and set the following values on it:</span></span>

    - <span data-ttu-id="54d47-196">**Tipo de trabajo**: *Ubicar*</span><span class="sxs-lookup"><span data-stu-id="54d47-196">**Work type:** *Put*</span></span>
    - <span data-ttu-id="54d47-197">**Identificador de la clase de trabajo**: *CrossDock*</span><span class="sxs-lookup"><span data-stu-id="54d47-197">**Work class ID:** *CrossDock*</span></span>

1. <span data-ttu-id="54d47-198">Seleccione **Guardar** y confirme que la casilla de verificación **Válido** está seleccionada para la plantilla *51 Cross Dock*.</span><span class="sxs-lookup"><span data-stu-id="54d47-198">Select **Save**, and confirm that the **Valid** check box is selected for the *51 Cross Dock* template.</span></span>

> [!NOTE]
> <span data-ttu-id="54d47-199">Los identificadores de clase de trabajo para los tipos de trabajo *Recoger* y *Colocar* deben ser iguales.</span><span class="sxs-lookup"><span data-stu-id="54d47-199">The work class IDs for the *Pick* and *Put* work types must be the same.</span></span>

### <a name="create-location-directives"></a><span data-ttu-id="54d47-200">Crear directivas de ubicación</span><span class="sxs-lookup"><span data-stu-id="54d47-200">Create location directives</span></span>

1. <span data-ttu-id="54d47-201">Vaya a **Gestión de almacenes \> Configurar \> Directivas de ubicación**.</span><span class="sxs-lookup"><span data-stu-id="54d47-201">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="54d47-202">En el panel izquierdo, establezca el campo **Tipo de orden de trabajo** a *Tránsito directo*.</span><span class="sxs-lookup"><span data-stu-id="54d47-202">In the left pane, set the **Work order type** field to *Cross docking*.</span></span>
1. <span data-ttu-id="54d47-203">En el panel de acción, seleccione **Nuevo** y establezca los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="54d47-203">On the Action Pane, select **New**, and set the following values:</span></span>

    - <span data-ttu-id="54d47-204">**Número de secuencia:** *1*</span><span class="sxs-lookup"><span data-stu-id="54d47-204">**Sequence number:** *1*</span></span>
    - <span data-ttu-id="54d47-205">**Nombre:** *51 Cross Dock Colocar*</span><span class="sxs-lookup"><span data-stu-id="54d47-205">**Name:** *51 Cross Dock Put*</span></span>
    - <span data-ttu-id="54d47-206">**Tipo de trabajo**: *Ubicar*</span><span class="sxs-lookup"><span data-stu-id="54d47-206">**Work type:** *Put*</span></span>
    - <span data-ttu-id="54d47-207">**Sitio**: *5*</span><span class="sxs-lookup"><span data-stu-id="54d47-207">**Site:** *5*</span></span>
    - <span data-ttu-id="54d47-208">**Almacén**: *51*</span><span class="sxs-lookup"><span data-stu-id="54d47-208">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="54d47-209">Seleccione **Guardar** para tener disponible la ficha desplegable **Líneas**.</span><span class="sxs-lookup"><span data-stu-id="54d47-209">Select **Save** to make the **Lines** FastTab available.</span></span>
1. <span data-ttu-id="54d47-210">En la ficha desplegable **Líneas**, seleccione **Nuevo** para agregar una línea a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="54d47-210">On the **Lines** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="54d47-211">En la nueva línea, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="54d47-211">On the new line, set the following values:</span></span>

    - <span data-ttu-id="54d47-212">**Cantidad inicial**: *1*</span><span class="sxs-lookup"><span data-stu-id="54d47-212">**From quantity:** *1*</span></span>
    - <span data-ttu-id="54d47-213">**Cantidad final**: *1000000*</span><span class="sxs-lookup"><span data-stu-id="54d47-213">**To quantity:** *1,000,000*</span></span>

1. <span data-ttu-id="54d47-214">Seleccione **Guardar** para tener disponible la ficha desplegable **Acciones directivas de ubicación**.</span><span class="sxs-lookup"><span data-stu-id="54d47-214">Select **Save** to make the **Location Directive Actions** FastTab available.</span></span>
1. <span data-ttu-id="54d47-215">En la ficha desplegable **Acciones de directiva de ubicación**, seleccione **Nuevo** para agregar una línea a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="54d47-215">On the **Location Directive Actions** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="54d47-216">En la nueva línea, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="54d47-216">On the new line, set the following values:</span></span>

    - <span data-ttu-id="54d47-217">**Nombre:** *Baydoor*</span><span class="sxs-lookup"><span data-stu-id="54d47-217">**Name:** *Baydoor*</span></span>
    - <span data-ttu-id="54d47-218">**Uso de ubicación fija:** *Ubicaciones fijas y no fijas*</span><span class="sxs-lookup"><span data-stu-id="54d47-218">**Fixed location usage:** *Fixed and non-fixed locations*</span></span>

1. <span data-ttu-id="54d47-219">Seleccione **Guardar** para tener disponible el botón **Editar consulta** en la barra de herramientas de **Acciones de directiva de ubicación**.</span><span class="sxs-lookup"><span data-stu-id="54d47-219">Select **Save** to make the **Edit query** button on the **Location Directive Actions** toolbar available.</span></span>
1. <span data-ttu-id="54d47-220">Seleccione **Editar consulta** para abrir el editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="54d47-220">Select **Edit query** to open the query editor.</span></span>
1. <span data-ttu-id="54d47-221">En la pestaña **Rango**, asegúrese de que las siguientes dos líneas estén configuradas:</span><span class="sxs-lookup"><span data-stu-id="54d47-221">On the **Range** tab, make sure that the following two lines are configured:</span></span>

    - <span data-ttu-id="54d47-222">Línea 1:</span><span class="sxs-lookup"><span data-stu-id="54d47-222">Line 1:</span></span>

        - <span data-ttu-id="54d47-223">**Tabla**: *Ubicaciones*</span><span class="sxs-lookup"><span data-stu-id="54d47-223">**Table:** *Locations*</span></span>
        - <span data-ttu-id="54d47-224">**Tabla derivada:** *Ubicaciones*</span><span class="sxs-lookup"><span data-stu-id="54d47-224">**Derived Table:** *Locations*</span></span>
        - <span data-ttu-id="54d47-225">**Campo:** *Almacén*</span><span class="sxs-lookup"><span data-stu-id="54d47-225">**Field:** *Warehouse*</span></span>
        - <span data-ttu-id="54d47-226">**Criterio:** *51*</span><span class="sxs-lookup"><span data-stu-id="54d47-226">**Criteria:** *51*</span></span>

    - <span data-ttu-id="54d47-227">Línea 2:</span><span class="sxs-lookup"><span data-stu-id="54d47-227">Line 2:</span></span>

        - <span data-ttu-id="54d47-228">**Tabla**: *Ubicaciones*</span><span class="sxs-lookup"><span data-stu-id="54d47-228">**Table:** *Locations*</span></span>
        - <span data-ttu-id="54d47-229">**Tabla derivada:** *Ubicaciones*</span><span class="sxs-lookup"><span data-stu-id="54d47-229">**Derived Table:** *Locations*</span></span>
        - <span data-ttu-id="54d47-230">**Campo:** *Ubicación*</span><span class="sxs-lookup"><span data-stu-id="54d47-230">**Field:** *Location*</span></span>
        - <span data-ttu-id="54d47-231">**Criterio:** *Baydoor*</span><span class="sxs-lookup"><span data-stu-id="54d47-231">**Criteria:** *Baydoor*</span></span>

1. <span data-ttu-id="54d47-232">Seleccione **Aceptar** para cerrar el editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="54d47-232">Select **OK** to close the query editor.</span></span>

### <a name="create-a-mobile-device-menu-item"></a><span data-ttu-id="54d47-233">Crear un elemento de menú del dispositivo móvil</span><span class="sxs-lookup"><span data-stu-id="54d47-233">Create a mobile device menu item</span></span>

1. <span data-ttu-id="54d47-234">Vaya a **Administración de almacenes \> Configurar \> Dispositivo móvil \> Elementos de menú del dispositivo móvil**.</span><span class="sxs-lookup"><span data-stu-id="54d47-234">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="54d47-235">En la lista de elementos de menú en el panel izquierdo, seleccione **Ubicación de compra**.</span><span class="sxs-lookup"><span data-stu-id="54d47-235">In the list of menu items in the left pane, select **Purchase Put-away**.</span></span>
1. <span data-ttu-id="54d47-236">Seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="54d47-236">Select **Edit**.</span></span>
1. <span data-ttu-id="54d47-237">En la ficha desplegable **Clases de trabajo**, seleccione **Nuevo** para agregar una línea a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="54d47-237">On the **Work classes** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="54d47-238">En la nueva línea, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="54d47-238">On the new line, set the following values:</span></span>

    - <span data-ttu-id="54d47-239">**Identificador de la clase de trabajo**: *CrossDock*</span><span class="sxs-lookup"><span data-stu-id="54d47-239">**Work class ID:** *CrossDock*</span></span>
    - <span data-ttu-id="54d47-240">**Tipo de orden de trabajo:** *Tránsito directo*</span><span class="sxs-lookup"><span data-stu-id="54d47-240">**Work order type:** *Cross docking*</span></span>

1. <span data-ttu-id="54d47-241">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="54d47-241">Select **Save**.</span></span>

## <a name="scenario"></a><span data-ttu-id="54d47-242">Situación</span><span class="sxs-lookup"><span data-stu-id="54d47-242">Scenario</span></span>

### <a name="create-a-purchase-order"></a><span data-ttu-id="54d47-243">Crear un pedido de compra</span><span class="sxs-lookup"><span data-stu-id="54d47-243">Create a purchase order</span></span>

<span data-ttu-id="54d47-244">Siga estos pasos para crear una orden de compra como fuente de suministro.</span><span class="sxs-lookup"><span data-stu-id="54d47-244">Follow these steps to create a purchase order as a source of supply.</span></span>

1. <span data-ttu-id="54d47-245">Vaya a **Adquisición y abastecimiento \> Pedidos de compra \> Todos los pedidos de compra**.</span><span class="sxs-lookup"><span data-stu-id="54d47-245">Go to **Procurement and sourcing \> Purchase orders \> All purchase orders**.</span></span>
1. <span data-ttu-id="54d47-246">En el panel de acciones, haga clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="54d47-246">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="54d47-247">En el cuadro de diálogo **Crear pedido de compras**, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="54d47-247">In the **Create purchase order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="54d47-248">**Cuenta del proveedor:** *104*</span><span class="sxs-lookup"><span data-stu-id="54d47-248">**Vendor account:** *104*</span></span>
    - <span data-ttu-id="54d47-249">**Almacén**: *51*</span><span class="sxs-lookup"><span data-stu-id="54d47-249">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="54d47-250">Seleccione **Aceptar** y anote el número de pedido.</span><span class="sxs-lookup"><span data-stu-id="54d47-250">Select **OK**, and make a note of the order number.</span></span>
1. <span data-ttu-id="54d47-251">Se agrega una nueva línea a la ficha desplegable **Líneas de orden de compra**.</span><span class="sxs-lookup"><span data-stu-id="54d47-251">A new line is added to the **Purchase order lines** FastTab.</span></span> <span data-ttu-id="54d47-252">En esta línea, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="54d47-252">On this line, set the following values:</span></span>

    - <span data-ttu-id="54d47-253">**Código de artículo:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="54d47-253">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="54d47-254">**Cantidad:** *5*</span><span class="sxs-lookup"><span data-stu-id="54d47-254">**Quantity:** *5*</span></span>

### <a name="create-a-sales-order"></a><span data-ttu-id="54d47-255">Crear un pedido de ventas</span><span class="sxs-lookup"><span data-stu-id="54d47-255">Create a sales order</span></span>

<span data-ttu-id="54d47-256">Siga estos pasos para crear un pedido de ventas como fuente de demanda.</span><span class="sxs-lookup"><span data-stu-id="54d47-256">Follow these steps to create a sales order as a source of demand.</span></span>

1. <span data-ttu-id="54d47-257">Vaya a **Ventas y marketing \> Pedidos de ventas \> Todos los pedidos de ventas**.</span><span class="sxs-lookup"><span data-stu-id="54d47-257">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="54d47-258">En el panel de acciones, haga clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="54d47-258">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="54d47-259">En el cuadro de diálogo **Crear pedido de ventas**, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="54d47-259">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="54d47-260">**Cuenta de cliente:** *US-002*</span><span class="sxs-lookup"><span data-stu-id="54d47-260">**Customer account:** *US-002*</span></span>
    - <span data-ttu-id="54d47-261">**Almacén**: *51*</span><span class="sxs-lookup"><span data-stu-id="54d47-261">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="54d47-262">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="54d47-262">Select **OK**.</span></span>
1. <span data-ttu-id="54d47-263">Se agrega una nueva línea a la ficha desplegable **Líneas de pedido de ventas**.</span><span class="sxs-lookup"><span data-stu-id="54d47-263">A new line is added to the **Sales order lines** FastTab.</span></span> <span data-ttu-id="54d47-264">En esta línea, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="54d47-264">On this line, set the following values:</span></span>

    - <span data-ttu-id="54d47-265">**Código de artículo:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="54d47-265">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="54d47-266">**Cantidad:** *3*</span><span class="sxs-lookup"><span data-stu-id="54d47-266">**Quantity:** *3*</span></span>

### <a name="create-planned-cross-docking"></a><span data-ttu-id="54d47-267">Crear tránsito directo planificado</span><span class="sxs-lookup"><span data-stu-id="54d47-267">Create planned cross-docking</span></span>

<span data-ttu-id="54d47-268">Siga estos pasos para crear el tránsito directo planificado a partir del pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="54d47-268">Follow these steps to create the planned cross-docking from the sales order.</span></span>

1. <span data-ttu-id="54d47-269">En la página **Detalles del pedido de ventas** para el pedido de ventas que acaba de crear, en el Panel de acciones, en la pestaña **Almacén**, en el grupo **Acciones**, seleccione **Liberar al almacén**.</span><span class="sxs-lookup"><span data-stu-id="54d47-269">In the **Sales order details** page for the sales order that you just created, on the Action Pane, on the **Warehouse** tab, in the **Actions** group, select **Release to warehouse**.</span></span>

    <span data-ttu-id="54d47-270">La acción de liberación al almacén crea una línea de envío y carga para la línea de pedido de ventas e intenta asignar inventario.</span><span class="sxs-lookup"><span data-stu-id="54d47-270">The release to warehouse action creates a shipment and load line for the sales order line, and tries to allocate inventory.</span></span>
    
    <span data-ttu-id="54d47-271">Recibirá un mensaje informativo.</span><span class="sxs-lookup"><span data-stu-id="54d47-271">You receive an informational message.</span></span> <span data-ttu-id="54d47-272">También recibirá el siguiente mensaje de advertencia: "No se creó ningún trabajo para la oleada XXXX.</span><span class="sxs-lookup"><span data-stu-id="54d47-272">You also receive the following warning message: "No work was created for wave XXXX.</span></span> <span data-ttu-id="54d47-273">Consulte el registro del historial de creación de trabajo para obtener más detalles".</span><span class="sxs-lookup"><span data-stu-id="54d47-273">See the work creation history log for details."</span></span> <span data-ttu-id="54d47-274">Se espera este comportamiento, porque no hay inventario en el almacén.</span><span class="sxs-lookup"><span data-stu-id="54d47-274">This behavior is expected, because there is no inventory in the warehouse.</span></span>

1. <span data-ttu-id="54d47-275">En la ficha desplegable **Líneas de pedido de ventas**, en el menú **Almacén**, seleccione **Detalles del envío**.</span><span class="sxs-lookup"><span data-stu-id="54d47-275">On the **Sales order lines** FastTab, on the **Warehouse** menu, select **Shipment details**.</span></span>

    <span data-ttu-id="54d47-276">Aparecerá la página **Detalles del envío** y muestra el envío que se creó para el pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="54d47-276">The **Shipment details** page appears and shows the shipment that was created for the sales order.</span></span>

1. <span data-ttu-id="54d47-277">En la ficha desplegable **Líneas de carga**, observe que el campo **Cantidad prevista de tránsito directo** se establece en *3*.</span><span class="sxs-lookup"><span data-stu-id="54d47-277">On the **Load lines** FastTab, notice that the **Planned cross docking quantity** field is set to *3*.</span></span> <span data-ttu-id="54d47-278">Debido a que no había inventario disponible en el almacén, pero una fuente de suministro válida llegará dentro de la ventana de tiempo definida en la plantilla de tránsito directo, se creó la cantidad de tránsito directo.</span><span class="sxs-lookup"><span data-stu-id="54d47-278">Because no inventory was available in the warehouse, but a valid supply source will arrive within the time window that is defined in the cross-docking template, the cross-docking quantity was created.</span></span>
1. <span data-ttu-id="54d47-279">En la ficha desplegable **Líneas de carga**, seleccione **Tránsito directo planeado** para ver los detalles del tránsito directo que se creó.</span><span class="sxs-lookup"><span data-stu-id="54d47-279">On the **Load lines** FastTab, select **Planned cross docking** to view the details of the cross-docking that was created.</span></span>

## <a name="process-the-cross-docking"></a><span data-ttu-id="54d47-280">Procesar el tránsito directo</span><span class="sxs-lookup"><span data-stu-id="54d47-280">Process the cross-docking</span></span>

### <a name="purchase-order-receiving-on-the-warehousing-mobile-app"></a><span data-ttu-id="54d47-281">Pedido de compra recibido en la aplicación móvil del almacén</span><span class="sxs-lookup"><span data-stu-id="54d47-281">Purchase order receiving on the warehousing mobile app</span></span>

<span data-ttu-id="54d47-282">El sistema recibirá la cantidad de 5 del pedido de compra en la ubicación de recepción y creará dos partes de trabajo.</span><span class="sxs-lookup"><span data-stu-id="54d47-282">The system will receive the quantity of 5 from the purchase order into the receiving location and create two pieces of work.</span></span>

<span data-ttu-id="54d47-283">La primera identificación de trabajo que se crea tiene un valor de **Tipo de orden de trabajo** *Tránsito directo* y está vinculado al pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="54d47-283">The first work ID that is created has a **Work order type** value of *Cross docking* and is linked to the sales order.</span></span> <span data-ttu-id="54d47-284">Tiene una cantidad de 3 y se dirige a la ubicación de envío final para que pueda enviarse de inmediato.</span><span class="sxs-lookup"><span data-stu-id="54d47-284">It has a quantity of 3 and is directed to the final shipping location so that it can be shipped out immediately.</span></span>

<span data-ttu-id="54d47-285">La segunda identificación de trabajo que se crea tiene un valor de **Tipo de orden de trabajo** *Pedidos de compra* y está vinculado al pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="54d47-285">The second work ID that is created has a **Work order type** value of *Purchase orders* and is linked to the purchase order.</span></span> <span data-ttu-id="54d47-286">Tiene la cantidad restante de 2 que no se cruzó y se dirige al almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="54d47-286">It has the remaining quantity of 2 that wasn't cross-docked and is directed to put-away to storage.</span></span>

1. <span data-ttu-id="54d47-287">Inicie sesión en el dispositivo móvil como un usuario en el almacén *51*.</span><span class="sxs-lookup"><span data-stu-id="54d47-287">Sign in to the mobile device as a user in warehouse *51*.</span></span>
1. <span data-ttu-id="54d47-288">Vaya **Entrante \> Recibir compra**.</span><span class="sxs-lookup"><span data-stu-id="54d47-288">Go to **Inbound \> Purchase Receive**.</span></span>
1. <span data-ttu-id="54d47-289">En el campo **PONUM**, introduzca su número de orden de compra.</span><span class="sxs-lookup"><span data-stu-id="54d47-289">In the **PONum** field, enter your purchase order number.</span></span>
1. <span data-ttu-id="54d47-290">En el campo **Cantidad**, especifique *5*.</span><span class="sxs-lookup"><span data-stu-id="54d47-290">In the **Qty** field, enter *5*.</span></span>
1. <span data-ttu-id="54d47-291">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="54d47-291">Select **OK**.</span></span>
1. <span data-ttu-id="54d47-292">En la página siguiente, establezca el campo **Artículo** a *A0001*.</span><span class="sxs-lookup"><span data-stu-id="54d47-292">On the next page, set the **Item** field to *A0001*.</span></span>
1. <span data-ttu-id="54d47-293">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="54d47-293">Select **OK**.</span></span>
1. <span data-ttu-id="54d47-294">En la página siguiente, confirme los valores **PONUM**, **Artículo** y **Cantidad** seleccionando **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="54d47-294">On the next page, confirm the **PONum**, **Item**, and **Qty** values by selecting **OK**.</span></span>

    <span data-ttu-id="54d47-295">Recibe un mensaje "Trabajo completado".</span><span class="sxs-lookup"><span data-stu-id="54d47-295">You receive a "Work Completed" message.</span></span>

1. <span data-ttu-id="54d47-296">Seleccione **Cancelar** para salir.</span><span class="sxs-lookup"><span data-stu-id="54d47-296">Select **Cancel** to exit.</span></span>

### <a name="put-away-to-cross-docking-and-bulk"></a><span data-ttu-id="54d47-297">Ubicación a tránsito directo y a granel</span><span class="sxs-lookup"><span data-stu-id="54d47-297">Put-away to cross-docking and bulk</span></span>

<span data-ttu-id="54d47-298">Actualmente, ambas identificaciones de trabajo tienen la misma matrícula de entidad objetivo.</span><span class="sxs-lookup"><span data-stu-id="54d47-298">Currently, both work IDs have the same target license plate.</span></span> <span data-ttu-id="54d47-299">Para completar los siguientes pasos, debe obtener la identificación del trabajo y la identificación de la matrícula de identidad.</span><span class="sxs-lookup"><span data-stu-id="54d47-299">To complete the next steps, you must get the work ID and the target license plate ID.</span></span> <span data-ttu-id="54d47-300">Puede obtener esta información de los detalles de trabajo para la línea de orden de compra y la línea de pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="54d47-300">You can get this information from the work details for the purchase order line and the sales order line.</span></span> <span data-ttu-id="54d47-301">Alternativamente, puede ir a **Gestión de almacenes \> Trabajo \> Detalles del trabajo** y filtrar para el trabajo donde el valor de **Almacén** es *51*.</span><span class="sxs-lookup"><span data-stu-id="54d47-301">Alternately, you can go to **Warehouse management \> Work \> Work details** and filter for work where the **Warehouse** value is *51*.</span></span>

1. <span data-ttu-id="54d47-302">En el dispositivo móvil, vaya a **Entrante \> Ubicación de compra** e introduzca la matricula de identidad de destino del trabajo.</span><span class="sxs-lookup"><span data-stu-id="54d47-302">On the mobile device, go to **Inbound \> Purchase put-away**, and enter the target license plate from the work.</span></span>
1. <span data-ttu-id="54d47-303">En campo **Identificación**, introduzca la identificación de la matrícula de entidad de destino de los detalles del trabajo.</span><span class="sxs-lookup"><span data-stu-id="54d47-303">In the **ID** field, enter the target license plate ID from the work details.</span></span>

    <span data-ttu-id="54d47-304">La página de selección de tránsito directo muestra la ubicación de selección (*RECV*), matrícula de entidad objetivo (*matrícula de entidad*), artículo (*A0001*) y cantidad (*3*).</span><span class="sxs-lookup"><span data-stu-id="54d47-304">The cross-docking pick page shows the picking location (*RECV*), target license plate (*license plate*), item (*A0001*), and quantity (*3*).</span></span>

1. <span data-ttu-id="54d47-305">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="54d47-305">Select **OK**.</span></span>
1. <span data-ttu-id="54d47-306">En el campo **LP objetivo**, introduzca una matrícula de entidad de destino para la identificación de la matrícula que debe colocarse (tránsito directo) en la ubicación de envío.</span><span class="sxs-lookup"><span data-stu-id="54d47-306">In the **Target LP** field, enter a target license plate for the license plate ID that should be put (cross-docked) to the shipping location.</span></span> <span data-ttu-id="54d47-307">Puede seleccionar cualquier identificación de matrícula de su elección.</span><span class="sxs-lookup"><span data-stu-id="54d47-307">You can select any license plate ID of your choice.</span></span>
1. <span data-ttu-id="54d47-308">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="54d47-308">Select **OK**.</span></span>
1. <span data-ttu-id="54d47-309">En la página siguiente, en campo **Identificación**, introduzca la identificación de la matrícula de entidad de destino.</span><span class="sxs-lookup"><span data-stu-id="54d47-309">On the next page, in the **ID** field, enter the target license plate ID.</span></span>
1. <span data-ttu-id="54d47-310">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="54d47-310">Select **OK**.</span></span>
1. <span data-ttu-id="54d47-311">Confirme el trabajo para elegir la cantidad restante de 2 y luego seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="54d47-311">Confirm the work for picking the remaining quantity of 2, and then select **OK**.</span></span>
1. <span data-ttu-id="54d47-312">En la página siguiente, seleccione **Hecho** para finalizar el proceso de selección y comenzar el proceso de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="54d47-312">On the next page, select **Done** to end the picking process and begin the put-away process.</span></span>

    <span data-ttu-id="54d47-313">La aplicación móvil le presenta la ubicación y la matrícula de entidad para colocar el artículo.</span><span class="sxs-lookup"><span data-stu-id="54d47-313">The mobile app presents you with the location and license plate to put the item to.</span></span>

1. <span data-ttu-id="54d47-314">Confirme el almacenamiento a granel **Colocar** seleccionando **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="54d47-314">Confirm the bulk storage **Put** by selecting **OK**.</span></span>
1. <span data-ttu-id="54d47-315">En la página siguiente, confirme el tránsito directo **Colocar** seleccionando **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="54d47-315">On the next page, confirm the cross-docking **Put** by selecting **OK**.</span></span>

    <span data-ttu-id="54d47-316">Recibe un mensaje "Trabajo completado".</span><span class="sxs-lookup"><span data-stu-id="54d47-316">You receive a "Work Completed" message.</span></span>

1. <span data-ttu-id="54d47-317">Seleccione **Cancelar** para salir.</span><span class="sxs-lookup"><span data-stu-id="54d47-317">Select **Cancel** to exit.</span></span>

<span data-ttu-id="54d47-318">La siguiente ilustración muestra cómo puede aparecer el trabajo de tránsito directo completado en Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="54d47-318">The following illustration shows how the completed cross-docking work might appear in Microsoft Dynamics 365 Supply Chain Management.</span></span>

<span data-ttu-id="54d47-319">![Trabajo de tránsito directo completado](media/PlannedCrossDockingWork.png "Trabajo de tránsito directo completado")</span><span class="sxs-lookup"><span data-stu-id="54d47-319">![Cross-docking work completed](media/PlannedCrossDockingWork.png "Cross-docking work completed")</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]