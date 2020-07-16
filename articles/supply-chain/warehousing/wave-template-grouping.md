---
title: Agrupación de plantillas de oleada
description: La agrupación de plantillas de oleada permite que el sistema utilice configuraciones de plantilla de oleada para determinar, según los criterios que defina, cómo debe dividir las líneas liberadas y asignarlas a oleadas nuevas o existentes. Esta característica puede ser útil en almacenes en los que se crean oleadas según determinados criterios, pero donde los administradores prefieren crear oleadas automáticamente en lugar de hacerlo manualmente.
author: Mirzaab
manager: tfehr
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 4dd188cbd17cfed372283ecb3389633b0c0021eb
ms.sourcegitcommit: a7a7303004620d2e9cef0642b16d89163911dbb4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "3530475"
---
# <a name="wave-template-grouping"></a><span data-ttu-id="71f01-104">Agrupación de plantillas de oleada</span><span class="sxs-lookup"><span data-stu-id="71f01-104">Wave template grouping</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="71f01-105">La agrupación de plantillas de oleada permite que el sistema utilice configuraciones de [plantilla de oleada](tasks/configure-wave-processing.md) para determinar, según los criterios que defina, cómo debe dividir las líneas liberadas y asignarlas a oleadas nuevas o existentes.</span><span class="sxs-lookup"><span data-stu-id="71f01-105">Wave template grouping enables the system to use [wave template](tasks/configure-wave-processing.md) setups to determine, based on criteria that you define, how it should split released lines and assign them to new or existing waves.</span></span> <span data-ttu-id="71f01-106">Esta característica puede ser útil en almacenes en los que se crean oleadas según determinados criterios, pero donde los administradores prefieren crear oleadas automáticamente en lugar de hacerlo manualmente.</span><span class="sxs-lookup"><span data-stu-id="71f01-106">This feature can be useful in warehouses where waves are created based on specific criteria, but where managers prefer to create waves automatically instead of manually.</span></span> <span data-ttu-id="71f01-107">Permite que el sistema agregue cada envío recién liberado a la primera oleada que encuentre que tenga valores de campo de agrupación coincidentes.</span><span class="sxs-lookup"><span data-stu-id="71f01-107">It enables the system to add each newly released shipment to the first wave that it finds that has matching grouping field values.</span></span> <span data-ttu-id="71f01-108">Si no se encuentra ninguna coincidencia, el sistema crea una nueva oleada para el nuevo envío.</span><span class="sxs-lookup"><span data-stu-id="71f01-108">If no match is found, the system creates a new wave for the new shipment.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="71f01-109">La agrupación de plantillas de oleada no es compatible con los tipos de trabajo *picking de materia prima de producción* o *picking de kanban*.</span><span class="sxs-lookup"><span data-stu-id="71f01-109">Wave template grouping isn't supported for the work types *production raw material picking* or *Kanban picking*.</span></span> <span data-ttu-id="71f01-110">Esto se debe a que la agrupación de oleadas se basa en envíos y estos tipos de trabajo no utilizan envíos.</span><span class="sxs-lookup"><span data-stu-id="71f01-110">This is because wave grouping is based on shipments and these work types don't use shipments.</span></span>

## <a name="turn-on-the-wave-template-grouping-feature"></a><span data-ttu-id="71f01-111">Activar la característica Agrupación de plantillas de oleada</span><span class="sxs-lookup"><span data-stu-id="71f01-111">Turn on the Wave template grouping feature</span></span>

<span data-ttu-id="71f01-112">Antes de poder usar la característica *Agrupación de plantillas de oleada*, esta debe estar activada en su sistema.</span><span class="sxs-lookup"><span data-stu-id="71f01-112">Before you can use the *Wave template grouping* feature, it must be turned on in your system.</span></span> <span data-ttu-id="71f01-113">Los administradores pueden usar la configuración de [gestión de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de la función y activarla si es necesario.</span><span class="sxs-lookup"><span data-stu-id="71f01-113">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="71f01-114">En el espacio de trabajo **Administración de funciones**, la función aparece de la siguiente forma:</span><span class="sxs-lookup"><span data-stu-id="71f01-114">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="71f01-115">**Módulo:** *Gestión de almacén*</span><span class="sxs-lookup"><span data-stu-id="71f01-115">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="71f01-116">**Nombre de característica**: *Agrupación de plantillas de oleada*</span><span class="sxs-lookup"><span data-stu-id="71f01-116">**Feature name:** *Wave template grouping*</span></span>

## <a name="set-a-wave-template-to-use-wave-template-grouping"></a><a name="set-up-template"></a><span data-ttu-id="71f01-117">Establecer una plantilla de oleada para usar una agrupación de plantillas de oleada</span><span class="sxs-lookup"><span data-stu-id="71f01-117">Set a wave template to use wave template grouping</span></span>

<span data-ttu-id="71f01-118">Para que la agrupación de plantillas de oleada esté disponible, siga estos pasos para configurar su [plantilla de oleada](tasks/configure-wave-processing.md).</span><span class="sxs-lookup"><span data-stu-id="71f01-118">To make wave template grouping available, follow these steps to set up your [wave template](tasks/configure-wave-processing.md).</span></span>

1. <span data-ttu-id="71f01-119">Vaya a **Gestión de almacenes \> Configurar \> Oleadas \> Plantillas de oleada**.</span><span class="sxs-lookup"><span data-stu-id="71f01-119">Go to **Warehouse management \> Setup \> Waves \> Wave templates**.</span></span>
1. <span data-ttu-id="71f01-120">En el panel izquierdo, seleccione la plantilla de oleada que desea configurar.</span><span class="sxs-lookup"><span data-stu-id="71f01-120">In the left pane, select the wave template to set up.</span></span> <span data-ttu-id="71f01-121">Si se está preparando para trabajar en el escenario que aparece más adelante en este tema utilizando datos de demostración, seleccione la plantilla **62 Envío predeterminado**.</span><span class="sxs-lookup"><span data-stu-id="71f01-121">If you're preparing to work through the scenario later in this topic by using demo data, select the **62 Shipping default** template.</span></span>
1. <span data-ttu-id="71f01-122">Seleccione **Editar** para poner la página en modo de edición.</span><span class="sxs-lookup"><span data-stu-id="71f01-122">Select **Edit** to put the page into edit mode.</span></span>
1. <span data-ttu-id="71f01-123">En la ficha desplegable **General**, establezca los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="71f01-123">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="71f01-124">**Automatizar la creación de oleadas:** *Sí*</span><span class="sxs-lookup"><span data-stu-id="71f01-124">**Automate wave creation:** *Yes*</span></span>
    - <span data-ttu-id="71f01-125">**Asignar a oleadas abiertas:** *Sí*</span><span class="sxs-lookup"><span data-stu-id="71f01-125">**Assign to open waves:** *Yes*</span></span>
    - <span data-ttu-id="71f01-126">**Procesar oleada para su liberación al almacén:** *No*</span><span class="sxs-lookup"><span data-stu-id="71f01-126">**Process wave at release to warehouse:** *No*</span></span>

1. <span data-ttu-id="71f01-127">En el panel de acciones, seleccione **Editar consulta** para abrir el cuadro de diálogo de consulta.</span><span class="sxs-lookup"><span data-stu-id="71f01-127">On the Action Pane, select **Edit query** to open the query dialog box.</span></span>
1. <span data-ttu-id="71f01-128">En el cuadro de diálogo de consulta, en la pestaña **Ordenación**, revise los criterios de ordenación y asegúrese de que haya una regla que incluya el campo que desea usar para agrupar sus oleadas.</span><span class="sxs-lookup"><span data-stu-id="71f01-128">In the query dialog box, on the **Sorting** tab, review the sorting criteria, and make sure that there is a rule that includes the field that you want to use to group your waves.</span></span>

    <span data-ttu-id="71f01-129">Si se está preparando para trabajar en el escenario utilizando datos de demostración, agregue una fila que tenga los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="71f01-129">If you're preparing to work through the scenario by using demo data, add a row that has the following values:</span></span>

    - <span data-ttu-id="71f01-130">**Tabla:** *Envíos*</span><span class="sxs-lookup"><span data-stu-id="71f01-130">**Table:** *Shipments*</span></span>
    - <span data-ttu-id="71f01-131">**Tabla derivada:** *Envíos*</span><span class="sxs-lookup"><span data-stu-id="71f01-131">**Derived table:** *Shipments*</span></span>
    - <span data-ttu-id="71f01-132">**Campo:** *Servicio de transportista*</span><span class="sxs-lookup"><span data-stu-id="71f01-132">**Field:** *Carrier service*</span></span>

        > [!NOTE]
        > <span data-ttu-id="71f01-133">Después de seleccionar este valor, puede que reciba el siguiente mensaje: "El campo Servicio de transportista no es un campo de índice.</span><span class="sxs-lookup"><span data-stu-id="71f01-133">After you select this value, you might receive the following message: "Field Carrier service is not an index field.</span></span> <span data-ttu-id="71f01-134">¿Desea agregar una ordenación a esto?"</span><span class="sxs-lookup"><span data-stu-id="71f01-134">Do you want to add sorting on this?"</span></span> <span data-ttu-id="71f01-135">Seleccione **Sí** para agregar una ordenación.</span><span class="sxs-lookup"><span data-stu-id="71f01-135">Select **Yes** to add sorting.</span></span>

    - <span data-ttu-id="71f01-136">**Dirección de búsqueda:** *Ascendente*</span><span class="sxs-lookup"><span data-stu-id="71f01-136">**Search direction:** *Ascending*</span></span>

1. <span data-ttu-id="71f01-137">Seleccione **Aceptar** para guardar sus cambios y cerrar el cuadro de diálogo de consulta.</span><span class="sxs-lookup"><span data-stu-id="71f01-137">Select **OK** to save your changes and close the query dialog box.</span></span>
1. <span data-ttu-id="71f01-138">En el panel de acciones, seleccione **Agrupación de plantillas de oleada**.</span><span class="sxs-lookup"><span data-stu-id="71f01-138">On the Action Pane, select **Wave template grouping**.</span></span>
1. <span data-ttu-id="71f01-139">En la página **Agrupación de plantillas de oleada**, seleccione la casilla **Agrupar por** para cada fila que desee utilizar para agrupar sus líneas de pedido en oleadas, según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="71f01-139">On the **Wave template grouping** page, select the **Group by** check box for each row that you want to use to group your order lines into waves, as required.</span></span> <span data-ttu-id="71f01-140">Si se está preparando para trabajar en el escenario utilizando datos de demostración, seleccione la casilla **Agrupar por** para la fila *Servicio de transportista*.</span><span class="sxs-lookup"><span data-stu-id="71f01-140">If you're preparing to work through the scenario by using demo data, select the **Group by** check box for the *Carrier service* row.</span></span>
1. <span data-ttu-id="71f01-141">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="71f01-141">Select **Save**.</span></span>
1. <span data-ttu-id="71f01-142">Cierre la página **Agrupación de plantillas de oleada**.</span><span class="sxs-lookup"><span data-stu-id="71f01-142">Close the **Wave template grouping** page.</span></span>
1. <span data-ttu-id="71f01-143">Seleccione **Guardar** para guardar la plantilla.</span><span class="sxs-lookup"><span data-stu-id="71f01-143">Select **Save** to save your template.</span></span>

## <a name="scenario"></a><span data-ttu-id="71f01-144">Situación</span><span class="sxs-lookup"><span data-stu-id="71f01-144">Scenario</span></span>

<span data-ttu-id="71f01-145">En esta sección se ofrece un script en el que puede trabajar para aprender qué hace esta característica y cómo trabajar con ella.</span><span class="sxs-lookup"><span data-stu-id="71f01-145">This section provides a script that you can work through to learn what this feature does and how to work with it.</span></span>

### <a name="make-sample-data-available"></a><span data-ttu-id="71f01-146">Hacer que los datos de muestra estén disponibles</span><span class="sxs-lookup"><span data-stu-id="71f01-146">Make sample data available</span></span>

<span data-ttu-id="71f01-147">Para trabajar en este escenario mediante el uso de los registros y valores de muestra que se especifican aquí, debe estar en un sistema donde estén instalados los [datos de demostración](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) estándar.</span><span class="sxs-lookup"><span data-stu-id="71f01-147">To work through this scenario by using the sample records and values that are specified here, you must be on a system where the standard [demo data](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) is installed.</span></span> <span data-ttu-id="71f01-148">Además, también debe seleccionar la entidad legal **USMF** antes de empezar.</span><span class="sxs-lookup"><span data-stu-id="71f01-148">Additionally, you must select the **USMF** legal entity before you begin.</span></span>

<span data-ttu-id="71f01-149">También puede usar este escenario como guía para usar la característica cuando trabaje en un sistema de producción.</span><span class="sxs-lookup"><span data-stu-id="71f01-149">You can also use this scenario as guidance for using the feature when you work on a production system.</span></span> <span data-ttu-id="71f01-150">Sin embargo, en ese caso, debe sustituir sus propios valores y puede que le falten algunos tipos de registros necesarios que proporcionan los datos de demostración estándar.</span><span class="sxs-lookup"><span data-stu-id="71f01-150">However, in that case, you must substitute your own values, and you might be missing some types of required records that the standard demo data provides.</span></span>

### <a name="scenario-wave-template-grouping"></a><span data-ttu-id="71f01-151">Escenario: Agrupación de plantillas de oleada</span><span class="sxs-lookup"><span data-stu-id="71f01-151">Scenario: Wave template grouping</span></span>

<span data-ttu-id="71f01-152">En este escenario se muestra cómo utilizar la agrupación de plantillas de oleada para crear automáticamente varias oleadas, según los criterios de agrupación que se definen en una plantilla de oleada.</span><span class="sxs-lookup"><span data-stu-id="71f01-152">This scenario shows how to use wave template grouping to automatically create multiple waves, based on grouping criteria that are defined in a wave template.</span></span> <span data-ttu-id="71f01-153">En este escenario, la plantilla de oleada se configura en el sistema para crear una oleada por servicio de transportista.</span><span class="sxs-lookup"><span data-stu-id="71f01-153">In this scenario, the wave template is set up in the system to create one wave per carrier service.</span></span>

<span data-ttu-id="71f01-154">Antes de empezar, prepare su plantilla de oleada como se describe en la sección [Establecer una plantilla de oleada para usar una agrupación de plantillas de oleada](#set-up-template) que aparece anteriormente en este tema.</span><span class="sxs-lookup"><span data-stu-id="71f01-154">Before you begin, prepare your wave template as described in the [Set a wave template to use wave template grouping](#set-up-template) section earlier in this topic.</span></span> <span data-ttu-id="71f01-155">Si va a trabajar con datos de demostración para este escenario, asegúrese de utilizar los valores de datos de demostración que se sugieren en ese procedimiento.</span><span class="sxs-lookup"><span data-stu-id="71f01-155">If you will be working with demo data for this scenario, be sure to use the demo data values that are suggested in that procedure.</span></span> <span data-ttu-id="71f01-156">Esta configuración agrupará sus oleadas de acuerdo con el servicio de transportista que se establece para cada pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="71f01-156">This setup will group your waves according to the carrier service that is set for each sales order.</span></span>

#### <a name="create-sales-order-1"></a><span data-ttu-id="71f01-157">Crear pedido de ventas 1</span><span class="sxs-lookup"><span data-stu-id="71f01-157">Create sales order 1</span></span>

1. <span data-ttu-id="71f01-158">Vaya a **Ventas y marketing \> Pedidos de ventas \> Todos los pedidos de ventas**.</span><span class="sxs-lookup"><span data-stu-id="71f01-158">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="71f01-159">Seleccione **Nuevo** para crear un pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="71f01-159">Select **New** to create a sales order.</span></span>
1. <span data-ttu-id="71f01-160">En el cuadro de diálogo **Crear pedido de ventas**, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="71f01-160">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="71f01-161">En la ficha desplegable **Cliente**, establezca el campo **Cuenta de cliente** en *US-004*.</span><span class="sxs-lookup"><span data-stu-id="71f01-161">On the **Customer** FastTab, set the **Customer account** field to *US-004*.</span></span>
    - <span data-ttu-id="71f01-162">En la ficha desplegable **General**, establezca el campo **Almacén** en *62*.</span><span class="sxs-lookup"><span data-stu-id="71f01-162">On the **General** FastTab, set the **Warehouse** field to *62*.</span></span>

1. <span data-ttu-id="71f01-163">Seleccione **Aceptar** para crear el pedido de ventas y cierre el cuadro de diálogo **Crear pedido de ventas**.</span><span class="sxs-lookup"><span data-stu-id="71f01-163">Select **OK** to create the sales order and close the **Create sales order** dialog box.</span></span>
1. <span data-ttu-id="71f01-164">El nuevo pedido de ventas se abre en la vista **Líneas**.</span><span class="sxs-lookup"><span data-stu-id="71f01-164">The new sales order is opened in the **Lines** view.</span></span> <span data-ttu-id="71f01-165">Anote el número del pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="71f01-165">Make a note of the sales order number.</span></span>
1. <span data-ttu-id="71f01-166">Cambie a la vista **Encabezado**.</span><span class="sxs-lookup"><span data-stu-id="71f01-166">Switch to the **Header** view.</span></span>
1. <span data-ttu-id="71f01-167">En la ficha desplegable **Entrega**, en la sección **Transporte**, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="71f01-167">On the **Delivery** FastTab, in the **Transportation** section, set the following values:</span></span>

    - <span data-ttu-id="71f01-168">**Transportista de envío:** *Carga aérea*</span><span class="sxs-lookup"><span data-stu-id="71f01-168">**Shipping carrier:** *Air cargo*</span></span>
    - <span data-ttu-id="71f01-169">**Servicio de transportista:** *Aire*</span><span class="sxs-lookup"><span data-stu-id="71f01-169">**Carrier service:** *Air*</span></span>

1. <span data-ttu-id="71f01-170">Vuelva a la vista **Líneas**.</span><span class="sxs-lookup"><span data-stu-id="71f01-170">Switch back to the **Lines** view.</span></span>
1. <span data-ttu-id="71f01-171">En la sección **Líneas de pedido de ventas**, seleccione **Agregar línea** para agregar una línea a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="71f01-171">In the **Sales order lines** section, select **Add line** to add a line to the grid.</span></span>
1. <span data-ttu-id="71f01-172">En la nueva línea, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="71f01-172">On the new line, set the following values:</span></span>

    - <span data-ttu-id="71f01-173">**Código de artículo:** *A0002*</span><span class="sxs-lookup"><span data-stu-id="71f01-173">**Item number:** *A0002*</span></span>
    - <span data-ttu-id="71f01-174">**Cantidad:** *2*</span><span class="sxs-lookup"><span data-stu-id="71f01-174">**Quantity:** *2*</span></span>

1. <span data-ttu-id="71f01-175">Seleccione la nueva línea de pedido y, en el menú **Inventario** encima de la cuadrícula, seleccione **Reserva**.</span><span class="sxs-lookup"><span data-stu-id="71f01-175">Select the new order line, and then, on the **Inventory** menu above the grid, select **Reservation**.</span></span>
1. <span data-ttu-id="71f01-176">En la página **Reserva**, en el panel de acciones, seleccione **Reservar lote** para reservar la cantidad completa de la línea seleccionada en el almacén.</span><span class="sxs-lookup"><span data-stu-id="71f01-176">On the **Reservation** page, on the Action Pane, select **Reserve lot** to reserve the full quantity of the selected line in the warehouse.</span></span>
1. <span data-ttu-id="71f01-177">Cierre la página **Reserva** para volver al pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="71f01-177">Close the **Reservation** page to return to the sales order.</span></span>
1. <span data-ttu-id="71f01-178">En el panel de acciones, en la pestaña **Almacén**, en el grupo **Acciones**, seleccione **Liberar al almacén**.</span><span class="sxs-lookup"><span data-stu-id="71f01-178">On the Action Pane, on the **Warehouse** tab, in the **Actions** group, select **Release to warehouse**.</span></span>
1. <span data-ttu-id="71f01-179">Recibirá un mensaje informativo que muestra el envío y la oleada de este pedido.</span><span class="sxs-lookup"><span data-stu-id="71f01-179">You receive an informational message that shows the shipment and wave for this order.</span></span> <span data-ttu-id="71f01-180">Anote el número de id. de la oleada y los números de id. del envío.</span><span class="sxs-lookup"><span data-stu-id="71f01-180">Make a note of the wave ID number and the shipment ID numbers.</span></span>

#### <a name="view-the-wave-that-was-created-from-sales-order-1"></a><span data-ttu-id="71f01-181">Ver la oleada que se creó a partir del pedido de ventas 1</span><span class="sxs-lookup"><span data-stu-id="71f01-181">View the wave that was created from sales order 1</span></span>

1. <span data-ttu-id="71f01-182">Vaya a **Gestión de almacenes \> Oleadas de salida \> Oleadas de envío \> Todas las oleadas**.</span><span class="sxs-lookup"><span data-stu-id="71f01-182">Go to **Warehouse management \> Outbound waves \> Shipment waves \> All waves**.</span></span>
1. <span data-ttu-id="71f01-183">Seleccione el id. de oleada que se creó a partir del pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="71f01-183">Select the wave ID that was created from the sales order.</span></span>
1. <span data-ttu-id="71f01-184">Seleccione el enlace de id. de oleada para abrir la página Detalles de oleada.</span><span class="sxs-lookup"><span data-stu-id="71f01-184">Select the wave ID link to open the wave details page.</span></span>
1. <span data-ttu-id="71f01-185">Observe que el envío se ha agregado a la ficha desplegable **Líneas de oleada**.</span><span class="sxs-lookup"><span data-stu-id="71f01-185">Notice that the shipment has been added to the **Wave lines** FastTab.</span></span>

#### <a name="create-sales-order-2"></a><span data-ttu-id="71f01-186">Crear pedido de ventas 2</span><span class="sxs-lookup"><span data-stu-id="71f01-186">Create sales order 2</span></span>

1. <span data-ttu-id="71f01-187">Vaya a **Ventas y marketing \> Pedidos de ventas \> Todos los pedidos de ventas**.</span><span class="sxs-lookup"><span data-stu-id="71f01-187">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="71f01-188">Seleccione **Nuevo** para crear un pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="71f01-188">Select **New** to create a sales order.</span></span>
1. <span data-ttu-id="71f01-189">En el cuadro de diálogo **Crear pedido de ventas**, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="71f01-189">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="71f01-190">En la ficha desplegable **Cliente**, establezca el campo **Cuenta de cliente** en *US-005*.</span><span class="sxs-lookup"><span data-stu-id="71f01-190">On the **Customer** FastTab, set the **Customer account** field to *US-005*.</span></span>
    - <span data-ttu-id="71f01-191">En la ficha desplegable **General**, establezca el campo **Almacén** en *62*.</span><span class="sxs-lookup"><span data-stu-id="71f01-191">On the **General** FastTab, set the **Warehouse** field to *62*.</span></span>

1. <span data-ttu-id="71f01-192">Seleccione **Aceptar** para crear el pedido de ventas y cierre el cuadro de diálogo **Crear pedido de ventas**.</span><span class="sxs-lookup"><span data-stu-id="71f01-192">Select **OK** to create the sales order and close the **Create sales order** dialog box.</span></span>
1. <span data-ttu-id="71f01-193">El nuevo pedido de ventas se abre en la vista **Líneas**.</span><span class="sxs-lookup"><span data-stu-id="71f01-193">The new sales order is opened in the **Lines** view.</span></span> <span data-ttu-id="71f01-194">Anote el número del pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="71f01-194">Make a note of the sales order number.</span></span>
1. <span data-ttu-id="71f01-195">Cambie a la vista **Encabezado**.</span><span class="sxs-lookup"><span data-stu-id="71f01-195">Switch to the **Header** view.</span></span>
1. <span data-ttu-id="71f01-196">En la ficha desplegable **Entrega**, en la sección **Transporte**, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="71f01-196">On the **Delivery** FastTab, in the **Transportation** section, set the following values:</span></span>

    - <span data-ttu-id="71f01-197">**Transportista de envío:** *Flower Moving*</span><span class="sxs-lookup"><span data-stu-id="71f01-197">**Shipping carrier:** *Flower moving*</span></span>
    - <span data-ttu-id="71f01-198">**Servicio de transportista:** *Estándar*</span><span class="sxs-lookup"><span data-stu-id="71f01-198">**Carrier service:** *Std*</span></span>

1. <span data-ttu-id="71f01-199">Vuelva a la vista **Líneas**.</span><span class="sxs-lookup"><span data-stu-id="71f01-199">Switch back to the **Lines** view.</span></span>
1. <span data-ttu-id="71f01-200">En la sección **Líneas de pedido de ventas**, seleccione **Agregar línea** para agregar una línea a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="71f01-200">In the **Sales order lines** section, select **Add line** to add a line to the grid.</span></span>
1. <span data-ttu-id="71f01-201">En la nueva línea, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="71f01-201">On the new line, set the following values:</span></span>

    - <span data-ttu-id="71f01-202">**Código de artículo:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="71f01-202">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="71f01-203">**Cantidad:** *1*</span><span class="sxs-lookup"><span data-stu-id="71f01-203">**Quantity:** *1*</span></span>

1. <span data-ttu-id="71f01-204">Seleccione la nueva línea de pedido y, en el menú **Inventario** encima de la cuadrícula, seleccione **Reserva**.</span><span class="sxs-lookup"><span data-stu-id="71f01-204">Select the new order line, and then, on the **Inventory** menu above the grid, select **Reservation**.</span></span>
1. <span data-ttu-id="71f01-205">En la página **Reserva**, en el panel de acciones, seleccione **Reservar lote** para reservar la cantidad completa de la línea seleccionada en el almacén.</span><span class="sxs-lookup"><span data-stu-id="71f01-205">On the **Reservation** page, on the Action Pane, select **Reserve lot** to reserve the full quantity of the selected line in the warehouse.</span></span>
1. <span data-ttu-id="71f01-206">Cierre la página **Reserva** para volver al pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="71f01-206">Close the **Reservation** page to return to the sales order.</span></span>
1. <span data-ttu-id="71f01-207">En el panel de acciones, en la pestaña **Almacén**, en el grupo **Acciones**, seleccione **Liberar al almacén**.</span><span class="sxs-lookup"><span data-stu-id="71f01-207">On the Action Pane, on the **Warehouse** tab, in the **Actions** group, select **Release to warehouse**.</span></span>
1. <span data-ttu-id="71f01-208">Recibirá un mensaje informativo que muestra el envío y la oleada de este pedido.</span><span class="sxs-lookup"><span data-stu-id="71f01-208">You receive an informational message that shows the shipment and wave for this order.</span></span> <span data-ttu-id="71f01-209">Anote el número de id. de la oleada y los números de id. del envío.</span><span class="sxs-lookup"><span data-stu-id="71f01-209">Make a note of the wave ID number and the shipment ID numbers.</span></span> <span data-ttu-id="71f01-210">Observe que el id. de oleada difiere del id. de oleada del primer pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="71f01-210">Notice that the wave ID differs from the wave ID of the first sales order.</span></span>

#### <a name="view-the-wave-that-was-created-from-sales-order-2"></a><span data-ttu-id="71f01-211">Ver la oleada que se creó a partir del pedido de ventas 2</span><span class="sxs-lookup"><span data-stu-id="71f01-211">View the wave that was created from sales order 2</span></span>

1. <span data-ttu-id="71f01-212">Vaya a **Gestión de almacenes \> Oleadas de salida \> Oleadas de envío \> Todas las oleadas**.</span><span class="sxs-lookup"><span data-stu-id="71f01-212">Go to **Warehouse management \> Outbound waves \> Shipment waves \> All waves**.</span></span>
1. <span data-ttu-id="71f01-213">Seleccione el id. de oleada que se creó a partir del segundo pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="71f01-213">Select the wave ID that was created from the second sales order.</span></span>
1. <span data-ttu-id="71f01-214">Seleccione el enlace de id. de oleada para abrir la página Detalles de oleada.</span><span class="sxs-lookup"><span data-stu-id="71f01-214">Select the wave ID link to open the wave details page.</span></span>
1. <span data-ttu-id="71f01-215">Observe que el envío se ha agregado a la ficha desplegable **Líneas de oleada**.</span><span class="sxs-lookup"><span data-stu-id="71f01-215">Notice that the shipment has been added to the **Wave lines** FastTab.</span></span>

<span data-ttu-id="71f01-216">Se creó una nueva oleada para este envío, ya que utiliza un servicio de transportista diferente al primer pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="71f01-216">A new wave was created for this shipment, because it uses a different carrier service than the first sales order.</span></span>

#### <a name="create-sales-order-3"></a><span data-ttu-id="71f01-217">Crear pedido de ventas 3</span><span class="sxs-lookup"><span data-stu-id="71f01-217">Create sales order 3</span></span>

1. <span data-ttu-id="71f01-218">Vaya a **Ventas y marketing \> Pedidos de ventas \> Todos los pedidos de ventas**.</span><span class="sxs-lookup"><span data-stu-id="71f01-218">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="71f01-219">Seleccione **Nuevo** para crear un pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="71f01-219">Select **New** to create a sales order.</span></span>
1. <span data-ttu-id="71f01-220">En el cuadro de diálogo **Crear pedido de ventas**, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="71f01-220">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="71f01-221">En la ficha desplegable **Cliente**, establezca el campo **Cuenta de cliente** en *US-006*.</span><span class="sxs-lookup"><span data-stu-id="71f01-221">On the **Customer** FastTab, set the **Customer account** field to *US-006*.</span></span>
    - <span data-ttu-id="71f01-222">En la ficha desplegable **General**, establezca el campo **Almacén** en *62*.</span><span class="sxs-lookup"><span data-stu-id="71f01-222">On the **General** FastTab, set the **Warehouse** field to *62*.</span></span>

1. <span data-ttu-id="71f01-223">Seleccione **Aceptar** para crear el pedido de ventas y cierre el cuadro de diálogo **Crear pedido de ventas**.</span><span class="sxs-lookup"><span data-stu-id="71f01-223">Select **OK** to create the sales order and close the **Create sales order** dialog box.</span></span>
1. <span data-ttu-id="71f01-224">El nuevo pedido de ventas se abre en la vista **Líneas**.</span><span class="sxs-lookup"><span data-stu-id="71f01-224">The new sales order is opened in the **Lines** view.</span></span> <span data-ttu-id="71f01-225">Anote el número del pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="71f01-225">Make a note of the sales order number.</span></span>
1. <span data-ttu-id="71f01-226">Cambie a la vista **Encabezado**.</span><span class="sxs-lookup"><span data-stu-id="71f01-226">Switch to the **Header** view.</span></span>
1. <span data-ttu-id="71f01-227">En la ficha desplegable **Entrega**, en la sección **Transporte**, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="71f01-227">On the **Delivery** FastTab, in the **Transportation** section, set the following values:</span></span>

    - <span data-ttu-id="71f01-228">**Transportista de envío:** *Air Cargo*</span><span class="sxs-lookup"><span data-stu-id="71f01-228">**Shipping carrier:** *Air Cargo*</span></span>
    - <span data-ttu-id="71f01-229">**Servicio de transportista:** *Aire*</span><span class="sxs-lookup"><span data-stu-id="71f01-229">**Carrier service:** *Air*</span></span>

1. <span data-ttu-id="71f01-230">Vuelva a la vista **Líneas**.</span><span class="sxs-lookup"><span data-stu-id="71f01-230">Switch back to the **Lines** view.</span></span>
1. <span data-ttu-id="71f01-231">En la sección **Líneas de pedido de ventas**, seleccione **Agregar línea** para agregar una línea a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="71f01-231">In the **Sales order lines** section, select **Add line** to add a line to the grid.</span></span>
1. <span data-ttu-id="71f01-232">En la nueva línea, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="71f01-232">On the new line, set the following values:</span></span>

    - <span data-ttu-id="71f01-233">**Código de artículo:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="71f01-233">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="71f01-234">**Cantidad:** *1*</span><span class="sxs-lookup"><span data-stu-id="71f01-234">**Quantity:** *1*</span></span>

1. <span data-ttu-id="71f01-235">Seleccione la nueva línea de pedido y, en el menú **Inventario** encima de la cuadrícula, seleccione **Reserva**.</span><span class="sxs-lookup"><span data-stu-id="71f01-235">Select the new order line, and then, on the **Inventory** menu above the grid, select **Reservation**.</span></span>
1. <span data-ttu-id="71f01-236">En la página **Reserva**, en el panel de acciones, seleccione **Reservar lote** para reservar la cantidad completa de la línea seleccionada en el almacén.</span><span class="sxs-lookup"><span data-stu-id="71f01-236">On the **Reservation** page, on the Action Pane, select **Reserve lot** to reserve the full quantity of the selected line in the warehouse.</span></span>
1. <span data-ttu-id="71f01-237">Cierre la página **Reserva** para volver al pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="71f01-237">Close the **Reservation** page to return to the sales order.</span></span>
1. <span data-ttu-id="71f01-238">En el panel de acciones, en la pestaña **Almacén**, en el grupo **Acciones**, seleccione **Liberar al almacén**.</span><span class="sxs-lookup"><span data-stu-id="71f01-238">On the Action Pane, on the **Warehouse** tab, in the **Actions** group, select **Release to warehouse**.</span></span>
1. <span data-ttu-id="71f01-239">Recibirá un mensaje informativo que muestra el envío y la oleada de este pedido.</span><span class="sxs-lookup"><span data-stu-id="71f01-239">You receive an informational message that shows the shipment and wave for this order.</span></span> <span data-ttu-id="71f01-240">Anote el número de id. de la oleada y los números de id. del envío.</span><span class="sxs-lookup"><span data-stu-id="71f01-240">Make a note of the wave ID number and the shipment ID numbers.</span></span> <span data-ttu-id="71f01-241">El envío se ha asignado a la oleada existente desde el primer pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="71f01-241">The shipment has been assigned to the existing wave from the first sales order.</span></span>

#### <a name="view-the-wave-for-sales-orders-1-and-3"></a><span data-ttu-id="71f01-242">Ver la oleada para pedidos de ventas 1 y 3</span><span class="sxs-lookup"><span data-stu-id="71f01-242">View the wave for sales orders 1 and 3</span></span>

1. <span data-ttu-id="71f01-243">Vaya a **Gestión de almacenes \> Oleadas de salida \> Oleadas de envío \> Todas las oleadas**.</span><span class="sxs-lookup"><span data-stu-id="71f01-243">Go to **Warehouse management \> Outbound waves \> Shipment waves \> All waves**.</span></span>
1. <span data-ttu-id="71f01-244">Seleccione el id. de oleada que se creó a partir del tercer pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="71f01-244">Select the wave ID that was created from the third sales order.</span></span>
1. <span data-ttu-id="71f01-245">Seleccione el enlace de id. de oleada para abrir la página Detalles de oleada.</span><span class="sxs-lookup"><span data-stu-id="71f01-245">Select the wave ID link to open the wave details page.</span></span>
1. <span data-ttu-id="71f01-246">Observe que el envío se ha agregado a la ficha desplegable **Líneas de oleada**, junto con el envío para el primer pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="71f01-246">Notice that the shipment has been added to the **Wave lines** FastTab, together with the shipment for the first sales order.</span></span>
