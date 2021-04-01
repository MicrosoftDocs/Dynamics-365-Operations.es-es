---
title: Cambiar grupo de trabajo en trabajo
description: Este tema explica cómo puede usar el botón Cambiar grupo de trabajo para elementos de trabajo, para cambiar el grupo de trabajo existente.
author: mirzaab
manager: tfehr
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWorkPool,WHSWorkTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: global
ms.author: mirzaab
ms.search.validFrom: 2020-07-16
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 61b988cf2501812e940f726e02d8fc1bcee2c035
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5233064"
---
# <a name="change-work-pool-on-work"></a><span data-ttu-id="53967-103">Cambiar grupo de trabajo en trabajo</span><span class="sxs-lookup"><span data-stu-id="53967-103">Change work pool on work</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="53967-104">Puede usar grupos de trabajo para organizar el trabajo en grupos.</span><span class="sxs-lookup"><span data-stu-id="53967-104">You can use work pools to organize work into groups.</span></span> <span data-ttu-id="53967-105">Por ejemplo, puede crear un grupo de trabajo para clasificar el trabajo que se produce en una ubicación específica del almacén.</span><span class="sxs-lookup"><span data-stu-id="53967-105">For example, you can create a work pool to classify work that occurs in a specific warehouse location.</span></span>

<span data-ttu-id="53967-106">La característica *Cambiar grupo de trabajo en el trabajo* agrega un botón **Cambiar grupo de trabajo** al Panel de acciones para elementos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="53967-106">The *Change work pool on work* feature adds a **Change work pool** button to the Action Pane for work items.</span></span> <span data-ttu-id="53967-107">Por lo tanto, los responsables de almacén pueden cambiar fácilmente el grupo de trabajo del trabajo existente.</span><span class="sxs-lookup"><span data-stu-id="53967-107">Therefore, warehouse managers can easily change the work pool of existing work.</span></span> <span data-ttu-id="53967-108">Esta característica permite a los responsables reaccionar rápidamente a los cambios en la planta del almacén, y ayuda a mejorar su capacidad de adaptarse a situaciones cambiantes y a la necesidad de transferir el trabajo a otro grupo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="53967-108">This feature lets managers react quickly to changes on the warehouse shop floor, and it helps improve their ability to adapt to changing situations and the need to transfer work to another work pool.</span></span>

## <a name="turn-on-the-change-work-pool-on-work-feature"></a><span data-ttu-id="53967-109">Activar la función Cambiar grupo de trabajo en trabajo</span><span class="sxs-lookup"><span data-stu-id="53967-109">Turn on the Change work pool on work feature</span></span>

<span data-ttu-id="53967-110">Antes de comenzar a configurar o utilizar esta función, debe asegurarse de que está disponible en su sistema.</span><span class="sxs-lookup"><span data-stu-id="53967-110">Before you begin to set up or use this feature, you must make sure that it's available in your system.</span></span> <span data-ttu-id="53967-111">Los administradores pueden usar la configuración de [gestión de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de la función y activarla si es necesario.</span><span class="sxs-lookup"><span data-stu-id="53967-111">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="53967-112">En el espacio de trabajo **Administración de funciones**, la función aparece de la siguiente forma:</span><span class="sxs-lookup"><span data-stu-id="53967-112">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="53967-113">**Módulo:** *Gestión de almacén*</span><span class="sxs-lookup"><span data-stu-id="53967-113">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="53967-114">**Nombre de la característica:** *Cambiar grupo de trabajo en trabajo*</span><span class="sxs-lookup"><span data-stu-id="53967-114">**Feature name:** *Change work pool on work*</span></span>

## <a name="set-up-the-change-work-pool-on-work-feature"></a><span data-ttu-id="53967-115">Configurar la característica Cambiar grupo de trabajo en trabajo</span><span class="sxs-lookup"><span data-stu-id="53967-115">Set up the Change work pool on work feature</span></span>

<span data-ttu-id="53967-116">Para usar esta característica, debe tener configurados algunos grupos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="53967-116">To use this feature, you must have some work pools set up.</span></span> <span data-ttu-id="53967-117">También puede configurar sus plantillas de trabajo para que asignen automáticamente un grupo.</span><span class="sxs-lookup"><span data-stu-id="53967-117">You might also set up your work templates so that they automatically assign a pool.</span></span> <span data-ttu-id="53967-118">Si desea trabajar en el escenario de ejemplo que se proporciona más adelante en este tema, configure su sistema como se describe en esta sección.</span><span class="sxs-lookup"><span data-stu-id="53967-118">If you want to work through the example scenario that is provided later in this topic, set up your system as described in this section.</span></span>

### <a name="set-up-work-pools"></a><span data-ttu-id="53967-119">Configurar grupos de trabajo</span><span class="sxs-lookup"><span data-stu-id="53967-119">Set up work pools</span></span>

<span data-ttu-id="53967-120">Los grupos de trabajo le permiten organizar los elementos de trabajo por tipo.</span><span class="sxs-lookup"><span data-stu-id="53967-120">Work pools let you organize work items by type.</span></span> <span data-ttu-id="53967-121">Para trabajar con la característica *Cambiar grupo de trabajo en trabajo*, debe tener al menos dos grupos de trabajo disponibles.</span><span class="sxs-lookup"><span data-stu-id="53967-121">To work with the *Change work pool on work* feature, you must have at least two work pools available.</span></span> <span data-ttu-id="53967-122">Siga estos pasos para ver y agregar grupos de trabajo:</span><span class="sxs-lookup"><span data-stu-id="53967-122">To view and add work pools, follow these steps.</span></span>

1. <span data-ttu-id="53967-123">Vaya a **Gestión de almacenes \> Configurar \> Trabajo \> Grupos de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="53967-123">Go to **Warehouse management \> Setup \> Work \> Work pools**.</span></span>
1. <span data-ttu-id="53967-124">Si está trabajando con datos de demostración de la empresa **USMF** y trabajará en el escenario de ejemplo más adelante en este tema, agregue dos grupos de trabajo que tengan la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="53967-124">If you're working with demo data from the **USMF** company and will work through the example scenario later in this topic, add two work pools that have the following settings:</span></span>

    - <span data-ttu-id="53967-125">Grupo de trabajo 1:</span><span class="sxs-lookup"><span data-stu-id="53967-125">Work pool 1:</span></span>

        - <span data-ttu-id="53967-126">**Id. del grupo de trabajo:** *Tiendaweb*</span><span class="sxs-lookup"><span data-stu-id="53967-126">**Work pool ID:** *Webshop*</span></span>
        - <span data-ttu-id="53967-127">**Descripción:** *Tienda web*</span><span class="sxs-lookup"><span data-stu-id="53967-127">**Description:** *Web Shop*</span></span>

    - <span data-ttu-id="53967-128">Grupo de trabajo 2:</span><span class="sxs-lookup"><span data-stu-id="53967-128">Work pool 2:</span></span>

        - <span data-ttu-id="53967-129">**Id. del grupo de trabajo:** *CentroLlamadas*</span><span class="sxs-lookup"><span data-stu-id="53967-129">**Work pool ID:** *CallCenter*</span></span>
        - <span data-ttu-id="53967-130">**Descripción:** *Centro de llamadas*</span><span class="sxs-lookup"><span data-stu-id="53967-130">**Description:** *Call Center*</span></span>

1. <span data-ttu-id="53967-131">En el panel Acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="53967-131">On the Action Pane, select **Save**.</span></span>

### <a name="set-up-work-templates"></a><span data-ttu-id="53967-132">Configurar plantillas de trabajo</span><span class="sxs-lookup"><span data-stu-id="53967-132">Set up work templates</span></span>

<span data-ttu-id="53967-133">Puede establecer un grupo de trabajo predeterminado para cada una de sus plantillas de trabajo, según lo necesite.</span><span class="sxs-lookup"><span data-stu-id="53967-133">For each of your work templates, you can set a default work pool, as you require.</span></span> <span data-ttu-id="53967-134">Asigne un grupo de trabajo para cada plantilla relevante en la columna **Id. del grupo de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="53967-134">For each relevant template, you assign a work pool in the **Work pool ID** column.</span></span> <span data-ttu-id="53967-135">En este caso, todos los elementos de trabajo que se generan utilizando una plantilla determinada heredan automáticamente el grupo de trabajo asignado.</span><span class="sxs-lookup"><span data-stu-id="53967-135">In this case, all work items that are generated by using a given template automatically inherit the assigned work pool.</span></span> <span data-ttu-id="53967-136">Si está trabajando con datos de demostración de la empresa **USMF** y trabajará en el escenario de ejemplo más adelante en este tema, siga los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="53967-136">If you're working with the demo data from the **USMF** company and will work through the example scenario later in this topic, follow these steps.</span></span>

1. <span data-ttu-id="53967-137">Vaya a **Administración de almacenes \> Configuración \> Trabajo \> Plantillas de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="53967-137">Go to **Warehouse management \> Setup \> Work \> Work templates**.</span></span>
1. <span data-ttu-id="53967-138">En el Panel de acciones, seleccione **Editar** para poner la página en modo de edición.</span><span class="sxs-lookup"><span data-stu-id="53967-138">On the Action Pane, select **Edit** to put the page into editing mode.</span></span>
1. <span data-ttu-id="53967-139">Edite la plantilla estableciendo los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="53967-139">Edit the template by setting the following values:</span></span>

    - <span data-ttu-id="53967-140">**Plantilla de trabajo:** *62 Selección para empaquetar*</span><span class="sxs-lookup"><span data-stu-id="53967-140">**Work template:** *62 Pick to pack*</span></span>
    - <span data-ttu-id="53967-141">**Id. del grupo de trabajo:** *Tiendaweb*</span><span class="sxs-lookup"><span data-stu-id="53967-141">**Work pool ID:** *Webshop*</span></span>

1. <span data-ttu-id="53967-142">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="53967-142">Select **Save**.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="53967-143">Supuesto de ejemplo</span><span class="sxs-lookup"><span data-stu-id="53967-143">Example scenario</span></span>

<span data-ttu-id="53967-144">Este escenario muestra cómo cambiar la secuencia de procesamiento de un elemento de trabajo existente cambiando su grupo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="53967-144">This scenario shows how to change the stream of processing for an existing work item by changing its work pool.</span></span> <span data-ttu-id="53967-145">Utiliza datos de muestra de la empresa **USMF** y las configuraciones sugeridas anteriormente en este tema.</span><span class="sxs-lookup"><span data-stu-id="53967-145">It uses demo data from the **USMF** company and the settings that were suggested earlier in this topic.</span></span>

### <a name="create-a-sales-order-and-release-it-to-the-warehouse"></a><span data-ttu-id="53967-146">Crear un pedido de ventas y liberarlo en el almacén</span><span class="sxs-lookup"><span data-stu-id="53967-146">Create a sales order and release it to the warehouse</span></span>

1. <span data-ttu-id="53967-147">Confirme que hay suficiente inventario disponible para los artículos *A0001* y *A0002* en el almacén *62*.</span><span class="sxs-lookup"><span data-stu-id="53967-147">Confirm that there is enough on-hand inventory for items *A0001* and *A0002* in warehouse *62*.</span></span> <span data-ttu-id="53967-148">Vaya a **Gestión de inventarios \> Consultas e informes \> Lista disponible** y edite los filtros como se muestra aquí:</span><span class="sxs-lookup"><span data-stu-id="53967-148">Go to **Inventory management \> Inquiries and reports \> On-hand list**, and edit the filters as shown here:</span></span>

    - <span data-ttu-id="53967-149">El valor **Almacén** comienza con *62*.</span><span class="sxs-lookup"><span data-stu-id="53967-149">The **Warehouse** value begins with *62*.</span></span>
    - <span data-ttu-id="53967-150">El valor **Número de artículo** es *A001* o *A002*.</span><span class="sxs-lookup"><span data-stu-id="53967-150">The **Item number** value is either *A001* or *A002*.</span></span>

    <span data-ttu-id="53967-151">Los datos de demostración deben tener una cantidad de 10 cada uno.</span><span class="sxs-lookup"><span data-stu-id="53967-151">Demo data should have a quantity of 10 each.</span></span>

    <span data-ttu-id="53967-152">A continuación, debe crear un pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="53967-152">Next, you must create a sales order.</span></span>

1. <span data-ttu-id="53967-153">Vaya a **Ventas y marketing \> Pedidos de ventas \> Todos los pedidos de ventas**.</span><span class="sxs-lookup"><span data-stu-id="53967-153">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="53967-154">En el panel de acciones, haga clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="53967-154">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="53967-155">En el cuadro de diálogo **Crear pedido de ventas**, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="53967-155">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="53967-156">**Cuenta de cliente:** *US-007*</span><span class="sxs-lookup"><span data-stu-id="53967-156">**Customer account:** *US-007*</span></span>
    - <span data-ttu-id="53967-157">**Almacén**: *62*</span><span class="sxs-lookup"><span data-stu-id="53967-157">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="53967-158">Seleccione **Aceptar** para crear el pedido de ventas y cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="53967-158">Select **OK** to create the sales order and close the dialog box.</span></span>
1. <span data-ttu-id="53967-159">Se abre el nuevo pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="53967-159">The new sales order is opened.</span></span> <span data-ttu-id="53967-160">Debe incluir una nueva línea vacía en la cuadrícula en la ficha desplegable **Líneas de pedido de venta**.</span><span class="sxs-lookup"><span data-stu-id="53967-160">It should include a new, empty line in the grid on the **Sales order lines** FastTab.</span></span> <span data-ttu-id="53967-161">En esta línea, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="53967-161">On this line, set the following values:</span></span>

    - <span data-ttu-id="53967-162">**Código de artículo:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="53967-162">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="53967-163">**Cantidad:** *2*</span><span class="sxs-lookup"><span data-stu-id="53967-163">**Quantity:** *2*</span></span>

1. <span data-ttu-id="53967-164">En el menú **Inventario** sobre la cuadrícula, seleccione **Reserva**.</span><span class="sxs-lookup"><span data-stu-id="53967-164">On the **Inventory** menu above the grid, select **Reservation**.</span></span>
1. <span data-ttu-id="53967-165">En la página **Reserva**, en el Panel de acciones, seleccione **Reservar lote** para reservar inventario.</span><span class="sxs-lookup"><span data-stu-id="53967-165">On the **Reservation** page, on the Action Pane, select **Reserve lot** to reserve the inventory.</span></span>
1. <span data-ttu-id="53967-166">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="53967-166">Close the page.</span></span>
1. <span data-ttu-id="53967-167">En la ficha desplegable **Líneas de pedido de venta**, seleccione **Agregar línea** para agregar otra línea a su pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="53967-167">On the **Sales order lines** FastTab, select **Add line** to add another line to your sales order.</span></span> <span data-ttu-id="53967-168">En esta línea, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="53967-168">On this line, set the following values:</span></span>

    - <span data-ttu-id="53967-169">**Código de artículo:** *A0002*</span><span class="sxs-lookup"><span data-stu-id="53967-169">**Item number:** *A0002*</span></span>
    - <span data-ttu-id="53967-170">**Cantidad:** *2*</span><span class="sxs-lookup"><span data-stu-id="53967-170">**Quantity:** *2*</span></span>

1. <span data-ttu-id="53967-171">En el menú **Inventario** sobre la cuadrícula, seleccione **Reserva**.</span><span class="sxs-lookup"><span data-stu-id="53967-171">On the **Inventory** menu above the grid, select **Reservation**.</span></span>
1. <span data-ttu-id="53967-172">En la página **Reserva**, en el Panel de acciones, seleccione **Reservar lote** para reservar inventario.</span><span class="sxs-lookup"><span data-stu-id="53967-172">On the **Reservation** page, on the Action Pane, select **Reserve lot** to reserve the inventory.</span></span>
1. <span data-ttu-id="53967-173">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="53967-173">Close the page.</span></span>
1. <span data-ttu-id="53967-174">En el panel de acciones, en la pestaña **Almacén**, seleccione **Liberar al almacén**.</span><span class="sxs-lookup"><span data-stu-id="53967-174">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>
1. <span data-ttu-id="53967-175">Recibirá mensajes informativos que muestran el id. de oleada y el id. de envío que se crearon a partir del lanzamiento.</span><span class="sxs-lookup"><span data-stu-id="53967-175">You receive informational messages that show the wave ID and shipment ID that were created from the release.</span></span> <span data-ttu-id="53967-176">Anote el id. de la oleada.</span><span class="sxs-lookup"><span data-stu-id="53967-176">Make a note of the wave ID.</span></span>

### <a name="review-the-outbound-wave"></a><span data-ttu-id="53967-177">Revisar la oleada de salida</span><span class="sxs-lookup"><span data-stu-id="53967-177">Review the outbound wave</span></span>

1. <span data-ttu-id="53967-178">Vaya a **Gestión de almacenes \> Oleadas de salida \> Oleadas de envío \> Todas las oleadas**.</span><span class="sxs-lookup"><span data-stu-id="53967-178">Go to **Warehouse management \> Outbound waves \> Shipment waves \> All waves**.</span></span>
1. <span data-ttu-id="53967-179">En la cuadrícula, busque el id. de oleada que se creó a partir del lanzamiento del pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="53967-179">In the grid, search for the wave ID that was created from the release of the sales order.</span></span>
1. <span data-ttu-id="53967-180">Seleccione el id. de oleada para ver los detalles.</span><span class="sxs-lookup"><span data-stu-id="53967-180">Select the wave ID to view the details.</span></span>
1. <span data-ttu-id="53967-181">En la ficha desplegable **Líneas de oleadas**, asegúrese de que se muestre un id. de envío para el pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="53967-181">On the **Wave lines** FastTab, make sure that a shipment ID is shown for the sales order.</span></span>

    > [!TIP]
    > <span data-ttu-id="53967-182">Si la opción **Procesar oleada para su liberación al almacén** está establecida en *No* en la configuración de la plantilla de envío de oleada, debe procesarla manualmente seleccionando **Procesar** desde la pestaña **Oleada** en el Panel de acciones para crear trabajo.</span><span class="sxs-lookup"><span data-stu-id="53967-182">If the **Process wave at release to warehouse** option is set to *No* in the setup for the shipping wave template, you must manually process the wave by selecting **Process** from the **Wave** tab on the Action Pane to create work.</span></span>

1. <span data-ttu-id="53967-183">Asegúrese de que se ha procesado la oleada.</span><span class="sxs-lookup"><span data-stu-id="53967-183">Make sure that the wave has been processed.</span></span> <span data-ttu-id="53967-184">Este procesamiento crea el trabajo necesario.</span><span class="sxs-lookup"><span data-stu-id="53967-184">This processing creates the required work.</span></span>

### <a name="view-work-details-and-change-the-work-pool"></a><span data-ttu-id="53967-185">Ver detalles de trabajo y cambiar el grupo de trabajo</span><span class="sxs-lookup"><span data-stu-id="53967-185">View work details and change the work pool</span></span>

<span data-ttu-id="53967-186">Puede usar la página **Detalles del trabajo** para ver el trabajo que se creó y para administrar el grupo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="53967-186">You can use the **Work details** page to view the work that was created and to manage the work pool.</span></span>

1. <span data-ttu-id="53967-187">Vaya a **Gestión de almacenes \> Trabajo \> Detalles de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="53967-187">Go to **Warehouse management \> Work \> Work details**.</span></span>
1. <span data-ttu-id="53967-188">Seleccione la fila para el trabajo que acaba de crear.</span><span class="sxs-lookup"><span data-stu-id="53967-188">Select the row for the work that was just created.</span></span> <span data-ttu-id="53967-189">La columna **Número de pedido** mostrará el número de pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="53967-189">The **Order number** column will show the sales order number.</span></span>

    <span data-ttu-id="53967-190">El campo **Id. del grupo de trabajo** se establecerá en el id. del grupo de trabajo que se configuró en la plantilla de trabajo.</span><span class="sxs-lookup"><span data-stu-id="53967-190">The **Work pool ID** field will be set to the work pool ID that was set up in the work template.</span></span>

    > [!TIP]
    > <span data-ttu-id="53967-191">Si no ve el **Id. del grupo de trabajo**, agregue la columna a la cuadrícula y luego actualice la página.</span><span class="sxs-lookup"><span data-stu-id="53967-191">If you don't see the **Work pool ID** field, add the column to the grid, and then refresh the page.</span></span>

1. <span data-ttu-id="53967-192">Para cambiar el grupo de trabajo asociado al id. de trabajo, en el Panel de acciones, seleccione **Cambiar ID de grupo de trabajo** en la pestaña **Trabajo**.</span><span class="sxs-lookup"><span data-stu-id="53967-192">To change the work pool that is associated with the work ID, on the Action Pane, on the **Work** tab, select **Change Work pool ID**.</span></span>
1. <span data-ttu-id="53967-193">En el cuadro de diálogo **Cambiar grupo de trabajo**, en la ficha desplegable **Parámetros**, en el campo **ID de grupo de trabajo**, seleccione *Centro de llamadas*.</span><span class="sxs-lookup"><span data-stu-id="53967-193">In the **Change work pool** dialog box, on the **Parameters** FastTab, in the **Work pool ID** field, select *CallCenter*.</span></span>
1. <span data-ttu-id="53967-194">Seleccione **Aceptar** para aplicar su cambio.</span><span class="sxs-lookup"><span data-stu-id="53967-194">Select **OK** to apply your change.</span></span>
1. <span data-ttu-id="53967-195">Tenga en cuenta que el valor del campo **Id. del grupo de trabajo** se ha cambiado a *CentroLlamadas*.</span><span class="sxs-lookup"><span data-stu-id="53967-195">Notice that the value of the **Work pool ID** field has now been changed to *CallCenter*.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="53967-196">Cuando aparece el cuadro de diálogo **Cambiar grupo de trabajo**, el campo **Id. del grupo de trabajo** puede estar en blanco de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="53967-196">When the **Change work pool** dialog box appears, the **Work pool ID** field might be blank by default.</span></span> <span data-ttu-id="53967-197">Si el campo está en blanco cuando selecciona **Aceptar** para aplicar cambios, eliminará el grupo de trabajo completamente del trabajo.</span><span class="sxs-lookup"><span data-stu-id="53967-197">If the field is blank when you select **OK** to apply changes, you will remove the work pool completely from the work.</span></span>
>
> <span data-ttu-id="53967-198">Además de cambiar los grupos de trabajo, puede utilizar este procedimiento para agregar un grupo de trabajo a cualquier elemento de trabajo que no tenga uno, o para eliminar un grupo de trabajo de cualquier elemento de trabajo que sí lo tenga.</span><span class="sxs-lookup"><span data-stu-id="53967-198">In addition to switching work pools, you can use this procedure to add a work pool to any work item that doesn't have one, or to remove a work pool from any work item that does have one.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]