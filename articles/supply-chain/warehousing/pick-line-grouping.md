---
title: Picking de agrupación de líneas
description: Este tema proporciona una descripción general de la agrupación de líneas de selección.
author: Mirzaab
manager: tfehr
ms.date: 12/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFMenuItem,WHSWorkTemplateTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2019-12-31
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: e70244d46ec2787fefdb097d0354af7910b55e9c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4989727"
---
# <a name="pick-line-grouping"></a><span data-ttu-id="54001-103">Picking de agrupación de líneas</span><span class="sxs-lookup"><span data-stu-id="54001-103">Pick line grouping</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="54001-104">La agrupación de líneas de selección habilita varias líneas de trabajo que tienen el mismo artículo y ubicación para combinarlas en una sola selección que se presenta al usuario en el dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="54001-104">Pick line grouping enables multiple work lines that have the same item and location to be combined into a single pick that is presented to the user on the mobile device.</span></span> <span data-ttu-id="54001-105">Esto permite que los trabajadores del almacén puedan recibir las instrucciones más eficaces, pero la separación de líneas de trabajo requeridas (para diferentes contenedores, pedidos, etc.) aún se puede mantener en el sistema.</span><span class="sxs-lookup"><span data-stu-id="54001-105">Therefore, warehouse workers can receive the most efficient instructions, but required work line separation (for different containers, orders, and so on) can still be maintained in the system.</span></span>

## <a name="turn-on-the-pick-line-grouping-feature"></a><span data-ttu-id="54001-106">Activar la característica de agrupación de la línea de selección</span><span class="sxs-lookup"><span data-stu-id="54001-106">Turn on the pick line grouping feature</span></span>

<span data-ttu-id="54001-107">Antes de poder usar esta característica debe estar activada en su sistema.</span><span class="sxs-lookup"><span data-stu-id="54001-107">Before you can use this feature, it must be turned on in your system.</span></span> <span data-ttu-id="54001-108">Los administradores pueden usar el espacio de trabajo [Gestión de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de la función y activarla si es necesario.</span><span class="sxs-lookup"><span data-stu-id="54001-108">Administrators can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="54001-109">Allí, la característica se enumera de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="54001-109">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="54001-110">**Módulo:** *Gestión de almacén*</span><span class="sxs-lookup"><span data-stu-id="54001-110">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="54001-111">**Nombre de la función:** *Seleccionar agrupación de líneas*</span><span class="sxs-lookup"><span data-stu-id="54001-111">**Feature name:** *Pick line grouping*</span></span>

## <a name="set-up-pick-line-grouping"></a><span data-ttu-id="54001-112">Configurar la agrupación de líneas de selección</span><span class="sxs-lookup"><span data-stu-id="54001-112">Set up pick line grouping</span></span>

### <a name="create-a-mobile-device-menu-item"></a><span data-ttu-id="54001-113">Crear un elemento de menú del dispositivo móvil</span><span class="sxs-lookup"><span data-stu-id="54001-113">Create a mobile device menu item</span></span>

1. <span data-ttu-id="54001-114">Vaya a **Administración de almacenes \> Configurar \> Dispositivo móvil \> Elementos de menú del dispositivo móvil**.</span><span class="sxs-lookup"><span data-stu-id="54001-114">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="54001-115">En el panel de acciones, haga clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="54001-115">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="54001-116">En el campo **Nombre del elemento del menú**, especifique *Selección de línea de grupo de ventas*.</span><span class="sxs-lookup"><span data-stu-id="54001-116">In the **Menu item name** field, enter *Sales group line picking*.</span></span>
1. <span data-ttu-id="54001-117">En el campo **Título**, especifique *Selección de línea de grupo de ventas*.</span><span class="sxs-lookup"><span data-stu-id="54001-117">In the **Title** field, enter *Sales group line picking*.</span></span> <span data-ttu-id="54001-118">Este título se mostrará en el menú del dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="54001-118">This title will be shown on the mobile device menu.</span></span>
1. <span data-ttu-id="54001-119">En el campo **Modo**, seleccione *Trabajo*.</span><span class="sxs-lookup"><span data-stu-id="54001-119">In the **Mode** field, select *Work*.</span></span>
1. <span data-ttu-id="54001-120">Establezca la opción **Usar trabajo existente** en *Sí*.</span><span class="sxs-lookup"><span data-stu-id="54001-120">Set the **Use existing work** option to *Yes*.</span></span>
1. <span data-ttu-id="54001-121">En la ficha desplegable **General**, establezca los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="54001-121">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="54001-122">En el campo **Dirigido por**, seleccione *Dirigido por el usuario*.</span><span class="sxs-lookup"><span data-stu-id="54001-122">In the **Directed by** field, select *User directed*.</span></span>
    - <span data-ttu-id="54001-123">Seleccione la opción **Generar matrícula de entidad de almacén** en *Sí*.</span><span class="sxs-lookup"><span data-stu-id="54001-123">Set the **Generate license plate** option to *Yes*.</span></span>
    - <span data-ttu-id="54001-124">Establezca la opción **Selección de grupo** en *Sí*.</span><span class="sxs-lookup"><span data-stu-id="54001-124">Set the **Group pick** option to *Yes*.</span></span>
    - <span data-ttu-id="54001-125">Acepte los valores predeterminados del resto de opciones.</span><span class="sxs-lookup"><span data-stu-id="54001-125">Accept the default values for the remaining options.</span></span>

1. <span data-ttu-id="54001-126">Siga estos pasos para configurar las clases de trabajo válidas para el elemento de menú del dispositivo móvil:</span><span class="sxs-lookup"><span data-stu-id="54001-126">Follow these steps to configure the valid work classes for the mobile device menu item:</span></span>

    1. <span data-ttu-id="54001-127">En la ficha desplegable **Clases de trabajo**, seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="54001-127">On the **Work classes** FastTab, elect **New**.</span></span>
    2. <span data-ttu-id="54001-128">En el campo **Identificador de la clase de trabajo**, puede seleccionar tanto *Ventas* como *Selección de pedidos de ventas* en función del almacén que vaya a utilizar.</span><span class="sxs-lookup"><span data-stu-id="54001-128">In the **Work class ID** field, you can select either *Sales* or *SO Pick*, depending on the warehouse that you will use.</span></span> <span data-ttu-id="54001-129">Para este escenario, seleccione *Selección de pedidos de ventas*.</span><span class="sxs-lookup"><span data-stu-id="54001-129">For this scenario, select *SO Pick*.</span></span>

        <span data-ttu-id="54001-130">El campo **Tipo de orden de trabajo** se configura automáticamente en *Pedidos de ventas*.</span><span class="sxs-lookup"><span data-stu-id="54001-130">The **Work order type** field is automatically set to *Sales orders*.</span></span>

### <a name="set-up-a-mobile-device-menu"></a><span data-ttu-id="54001-131">Configurar un menú de dispositivo móvil</span><span class="sxs-lookup"><span data-stu-id="54001-131">Set up a mobile device menu</span></span>

<span data-ttu-id="54001-132">Siga estos pasos para agregar el elemento de menú que acaba de crear al menú **Salida**.</span><span class="sxs-lookup"><span data-stu-id="54001-132">Follow these steps to add the menu item that you just created to the **Outbound** menu.</span></span>

1. <span data-ttu-id="54001-133">Vaya a **Administración de almacenes \> Configuración \> Dispositivo móvil \> Menú del dispositivo móvil**.</span><span class="sxs-lookup"><span data-stu-id="54001-133">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu**.</span></span>
1. <span data-ttu-id="54001-134">En el panel Acciones, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="54001-134">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="54001-135">El panel de lista muestra todos los menús de dispositivos móviles existentes.</span><span class="sxs-lookup"><span data-stu-id="54001-135">The list pane shows all existing mobile device menus.</span></span> <span data-ttu-id="54001-136">En la lista, seleccione *Salida*.</span><span class="sxs-lookup"><span data-stu-id="54001-136">Select *Outbound* in the list.</span></span>
1. <span data-ttu-id="54001-137">En la lista **Elementos de menús y menús disponibles**, busque y seleccione el elemento de menú *Selección de línea de grupo de ventas* que ha creado.</span><span class="sxs-lookup"><span data-stu-id="54001-137">In the **Available menus and menu items** list, find and select the *Sales group line picking* menu item that you created.</span></span>
1. <span data-ttu-id="54001-138">Seleccione el botón de flecha derecha para mover el elemento de menú *Selección de línea de grupo de ventas* a la lista **Estructura del menú**.</span><span class="sxs-lookup"><span data-stu-id="54001-138">Select the right arrow button to move the *Sales group line picking* menu item to the **Menu structure** list.</span></span>
1. <span data-ttu-id="54001-139">Utilice los botones de flecha hacia arriba o flecha hacia abajo para mover el elemento del menú a la posición deseada en la estructura de menú.</span><span class="sxs-lookup"><span data-stu-id="54001-139">Use the up arrow and down arrow buttons to move the menu item into the desired position in the menu structure.</span></span>
1. <span data-ttu-id="54001-140">En el panel Acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="54001-140">On the Action Pane, select **Save**.</span></span>

### <a name="set-up-a-work-template"></a><span data-ttu-id="54001-141">Configurar una plantilla de trabajo</span><span class="sxs-lookup"><span data-stu-id="54001-141">Set up a work template</span></span>

1. <span data-ttu-id="54001-142">Vaya a **Administración de almacenes \> Configuración \> Trabajo \> Plantillas de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="54001-142">Go to **Warehouse management \> Setup \> Work \> Work templates**.</span></span>
1. <span data-ttu-id="54001-143">En el campo **Tipo de orden de trabajo**, seleccione *Pedidos de ventas*.</span><span class="sxs-lookup"><span data-stu-id="54001-143">In the **Work order type** field, select *Sales orders*.</span></span>
1. <span data-ttu-id="54001-144">En la cuadrícula **Visión general**, busque y seleccione la plantilla de trabajo que debe usarse con esta función.</span><span class="sxs-lookup"><span data-stu-id="54001-144">In the **Overview** grid, find and select the work template that should be used with this function.</span></span> <span data-ttu-id="54001-145">Para este escenario, seleccione la plantilla *51 Recoger para preparar*.</span><span class="sxs-lookup"><span data-stu-id="54001-145">For this scenario, select the *51 Pick to stage* template.</span></span>
1. <span data-ttu-id="54001-146">En el panel Acciones, seleccione **Editar consulta**.</span><span class="sxs-lookup"><span data-stu-id="54001-146">On the Action Pane, select **Edit query**.</span></span>
1. <span data-ttu-id="54001-147">En el cuadro de diálogo de editor de consulta, en la pestaña **Ordenación**, seleccione **Añadir** y luego establezca los siguientes valores para la nueva fila:</span><span class="sxs-lookup"><span data-stu-id="54001-147">In the query editor dialog box, on the **Sorting** tab, select **Add**, and then set the following values for the new row:</span></span>

    - <span data-ttu-id="54001-148">En la columna **Tabla**, seleccione *Transacciones de trabajo temporal*.</span><span class="sxs-lookup"><span data-stu-id="54001-148">In the **Table** column, select *Temporary work transactions*.</span></span>
    - <span data-ttu-id="54001-149">En la columna **Tabla derivada**, seleccione *Transacciones de trabajo temporal*.</span><span class="sxs-lookup"><span data-stu-id="54001-149">In the **Derived table** column, select *Temporary work transactions*.</span></span>
    - <span data-ttu-id="54001-150">En la columna **Campo**, seleccione *Número de artículo*.</span><span class="sxs-lookup"><span data-stu-id="54001-150">In the **Field** column, select *Item number*.</span></span>
    - <span data-ttu-id="54001-151">En la columna **Dirección de búsqueda**, seleccione *Ascendente*.</span><span class="sxs-lookup"><span data-stu-id="54001-151">In the **Search direction** column, select *Ascending*.</span></span>

1. <span data-ttu-id="54001-152">Seleccione **Aceptar** para cerrar el cuadro de diálogo y guardar la selección.</span><span class="sxs-lookup"><span data-stu-id="54001-152">Select **OK** to close the dialog box and save your selection.</span></span>
1. <span data-ttu-id="54001-153">Recibirá el siguiente mensaje: "La agrupación se restablecerá, ¿continuar?"</span><span class="sxs-lookup"><span data-stu-id="54001-153">You receive the following message: "Grouping will be reset, continue?"</span></span> <span data-ttu-id="54001-154">Seleccione **Sí** para continuar.</span><span class="sxs-lookup"><span data-stu-id="54001-154">Select **Yes** to continue.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="54001-155">Para que la funcionalidad de agrupación de líneas de selección funcione, las líneas de trabajo deben ordenarse por id. de artículo.</span><span class="sxs-lookup"><span data-stu-id="54001-155">For the pick line grouping functionality to work, the work lines must be sorted by item ID.</span></span> <span data-ttu-id="54001-156">Si las líneas que tienen los mismos artículos no se secuencian una tras otra, no se agruparán.</span><span class="sxs-lookup"><span data-stu-id="54001-156">If lines that have the same items aren't sequenced one after another, they won't be grouped.</span></span>

## <a name="example"></a><span data-ttu-id="54001-157">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="54001-157">Example</span></span>

### <a name="create-picking-work"></a><span data-ttu-id="54001-158">Crear trabajo de selección</span><span class="sxs-lookup"><span data-stu-id="54001-158">Create picking work</span></span>

<span data-ttu-id="54001-159">Antes de poder configurar la agrupación de líneas de clúster debe crear un trabajo de salida válido.</span><span class="sxs-lookup"><span data-stu-id="54001-159">Before you can set up pick line grouping, you must create some eligible outbound work.</span></span>

1. <span data-ttu-id="54001-160">Vaya a **Ventas y marketing \> Pedidos de ventas \> Todos los pedidos de ventas**.</span><span class="sxs-lookup"><span data-stu-id="54001-160">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="54001-161">Seleccione **Nuevo** para crear un pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="54001-161">Select **New** to create a sales order.</span></span>
1. <span data-ttu-id="54001-162">En el campo **Cuenta de cliente**, seleccione *US-004*.</span><span class="sxs-lookup"><span data-stu-id="54001-162">In the **Customer account** field, select *US-004*.</span></span>
1. <span data-ttu-id="54001-163">En la ficha desplegable **General**, en el campo **Almacén**, seleccione el almacén *51*.</span><span class="sxs-lookup"><span data-stu-id="54001-163">On the **General** FastTab, in the **Warehouse** field, select *51*.</span></span>
1. <span data-ttu-id="54001-164">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="54001-164">Select **OK**.</span></span>
1. <span data-ttu-id="54001-165">En la ficha desplegable **Líneas de pedido de ventas**, agregue las seis líneas siguientes:</span><span class="sxs-lookup"><span data-stu-id="54001-165">On the **Sales order lines** FastTab, add the following six lines:</span></span>

    - <span data-ttu-id="54001-166">**Línea 1:** en el campo **Número de artículo**, seleccione *M9200*.</span><span class="sxs-lookup"><span data-stu-id="54001-166">**Line 1:** In the **Item number** field, select *M9200*.</span></span> <span data-ttu-id="54001-167">En el campo **Cantidad**, especifique *3*.</span><span class="sxs-lookup"><span data-stu-id="54001-167">In the **Quantity** field, enter *3*.</span></span>
    - <span data-ttu-id="54001-168">**Línea 2:** en el campo **Número de artículo**, seleccione *M9201*.</span><span class="sxs-lookup"><span data-stu-id="54001-168">**Line 2:** In the **Item number** field, select *M9201*.</span></span> <span data-ttu-id="54001-169">En el campo **Cantidad**, especifique *3*.</span><span class="sxs-lookup"><span data-stu-id="54001-169">In the **Quantity** field, enter *3*.</span></span>
    - <span data-ttu-id="54001-170">**Línea 3:** en el campo **Número de artículo**, seleccione *M9202*.</span><span class="sxs-lookup"><span data-stu-id="54001-170">**Line 3:** In the **Item number** field, select *M9202*.</span></span> <span data-ttu-id="54001-171">En el campo **Cantidad**, especifique *2*.</span><span class="sxs-lookup"><span data-stu-id="54001-171">In the **Quantity** field, enter *2*.</span></span>
    - <span data-ttu-id="54001-172">**Línea 4:** en el campo **Número de artículo**, seleccione *M9200*.</span><span class="sxs-lookup"><span data-stu-id="54001-172">**Line 4:** In the **Item number** field, select *M9200*.</span></span> <span data-ttu-id="54001-173">En el campo **Cantidad**, especifique *1*.</span><span class="sxs-lookup"><span data-stu-id="54001-173">In the **Quantity** field, enter *1*.</span></span>
    - <span data-ttu-id="54001-174">**Línea 5:** en el campo **Número de artículo**, seleccione *M9200*.</span><span class="sxs-lookup"><span data-stu-id="54001-174">**Line 5:** In the **Item number** field, select *M9200*.</span></span> <span data-ttu-id="54001-175">En el campo **Cantidad**, especifique *3*.</span><span class="sxs-lookup"><span data-stu-id="54001-175">In the **Quantity** field, enter *3*.</span></span>
    - <span data-ttu-id="54001-176">**Línea 6:** en el campo **Número de artículo**, seleccione *M9202*.</span><span class="sxs-lookup"><span data-stu-id="54001-176">**Line 6:** In the **Item number** field, select *M9202*.</span></span> <span data-ttu-id="54001-177">En el campo **Cantidad**, especifique *7*.</span><span class="sxs-lookup"><span data-stu-id="54001-177">In the **Quantity** field, enter *7*.</span></span>

    <span data-ttu-id="54001-178">A continuación se muestra un resumen de las cantidades totales para cada artículo:</span><span class="sxs-lookup"><span data-stu-id="54001-178">Here is a summary of the total quantities for each item:</span></span>

    - <span data-ttu-id="54001-179">**Artículo M9200:** *7* cada uno</span><span class="sxs-lookup"><span data-stu-id="54001-179">**Item M9200:** *7* each</span></span>
    - <span data-ttu-id="54001-180">**Artículo M9201:** *3* cada uno</span><span class="sxs-lookup"><span data-stu-id="54001-180">**Item M9201:** *3* each</span></span>
    - <span data-ttu-id="54001-181">**Artículo M9202:** *9* cada uno</span><span class="sxs-lookup"><span data-stu-id="54001-181">**Item M9202:** *9* each</span></span>

1. <span data-ttu-id="54001-182">Antes de liberar los pedidos al almacén, debe asegurarse de que las ubicaciones de selección tengan suficiente inventario para todos los artículos en todos los pedidos.</span><span class="sxs-lookup"><span data-stu-id="54001-182">Before you release the orders to the warehouse, you must make sure that the pick locations have enough inventory for all the items on all the orders.</span></span> <span data-ttu-id="54001-183">Revisa la configuración de **Directiva de ubicación** para determinar qué ubicaciones de selección se utilizan para la selección de pedidos de ventas.</span><span class="sxs-lookup"><span data-stu-id="54001-183">Review the **Location directive** setting to determine which picking locations are used for sales order picking.</span></span> <span data-ttu-id="54001-184">Si usa el entorno de datos de demostración de Contoso para el almacén *51*, confirme que hay inventario disponible.</span><span class="sxs-lookup"><span data-stu-id="54001-184">If you're using the Contoso demo data environment for warehouse *51*, confirm that there is available inventory.</span></span>

    <span data-ttu-id="54001-185">Ahora debe reservar el inventario para cada línea.</span><span class="sxs-lookup"><span data-stu-id="54001-185">You must now reserve the inventory for each line.</span></span>

1. <span data-ttu-id="54001-186">En la ficha desplegable **Líneas de orden de venta**, seleccione una de las líneas que se deben reservar.</span><span class="sxs-lookup"><span data-stu-id="54001-186">On the **Sales order lines** FastTab, select one of the lines that must be reserved.</span></span>
1. <span data-ttu-id="54001-187">En el menú **Inventario** sobre la cuadrícula, seleccione **Reserva**.</span><span class="sxs-lookup"><span data-stu-id="54001-187">On the **Inventory** menu above the grid, select **Reservation**.</span></span>
1. <span data-ttu-id="54001-188">En la página **Reserva**, en el Panel de acciones, seleccione **Reservar lote** para aplicar la reserva.</span><span class="sxs-lookup"><span data-stu-id="54001-188">On the **Reservation** page, on the Action Pane, select **Reserve lot** to apply the reservation.</span></span> <span data-ttu-id="54001-189">A continuación, cierre la página.</span><span class="sxs-lookup"><span data-stu-id="54001-189">Then close the page.</span></span>
1. <span data-ttu-id="54001-190">Repita los pasos del 8 al 10 para las líneas restantes que se deben reservar.</span><span class="sxs-lookup"><span data-stu-id="54001-190">Repeat steps 8 through 10 for the remaining lines that must be reserved.</span></span>

    <span data-ttu-id="54001-191">Ahora debe lanzar el pedido de ventas al almacén.</span><span class="sxs-lookup"><span data-stu-id="54001-191">You must now release the sales order to the warehouse.</span></span>

1. <span data-ttu-id="54001-192">En el panel de acciones, en la pestaña **Almacén**, seleccione **Liberar al almacén**.</span><span class="sxs-lookup"><span data-stu-id="54001-192">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>

    <span data-ttu-id="54001-193">Recibe un mensaje que indica que se ha creado un envío y un lanzamiento, y que el lanzamiento se ha enviado para ejecutarse en un lote.</span><span class="sxs-lookup"><span data-stu-id="54001-193">You receive a message that states that a shipment and a wave have been created, and that the wave has been submitted to run in a batch.</span></span>

    <span data-ttu-id="54001-194">Cuando se han completado el lanzamiento y todos los trabajos posteriores, se crea un ID de trabajo para el trabajo que tiene seis líneas.</span><span class="sxs-lookup"><span data-stu-id="54001-194">When the wave and all downstream jobs have been completed, a work ID is created for work that has six lines.</span></span> <span data-ttu-id="54001-195">Las líneas se ordenan por número de artículo.</span><span class="sxs-lookup"><span data-stu-id="54001-195">The lines are sorted by item number.</span></span>

1. <span data-ttu-id="54001-196">Vaya a **Gestión de almacenes \> Trabajo \> Todo el trabajo** para ver el trabajo que se ha creado.</span><span class="sxs-lookup"><span data-stu-id="54001-196">Go to **Warehouse management \> Work \> All work** to view the work that was created.</span></span> <span data-ttu-id="54001-197">Tome nota del valor **Id. de trabajo**, porque lo necesitará en el siguiente procedimiento.</span><span class="sxs-lookup"><span data-stu-id="54001-197">Make a note of the **Work ID** value, because you will need it in the next procedure.</span></span>

### <a name="initiate-picking-from-the-mobile-device"></a><span data-ttu-id="54001-198">Iniciar la recolección desde el dispositivo móvil</span><span class="sxs-lookup"><span data-stu-id="54001-198">Initiate picking from the mobile device</span></span>

1. <span data-ttu-id="54001-199">Inicie sesión en el dispositivo móvil como un usuario configurado para el almacén *51*.</span><span class="sxs-lookup"><span data-stu-id="54001-199">Sign in to the mobile device as a user who is set up for warehouse *51*.</span></span>
1. <span data-ttu-id="54001-200">En el dispositivo móvil, seleccione el menú que incluye el nuevo elemento de menú del dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="54001-200">On the mobile device, select the menu that includes the new mobile device menu item.</span></span> <span data-ttu-id="54001-201">Para este escenario, seleccione **Salida**.</span><span class="sxs-lookup"><span data-stu-id="54001-201">For this scenario, select **Outbound**.</span></span>
1. <span data-ttu-id="54001-202">Seleccione el elemento de menú **Selección de línea de grupo de ventas** para iniciar la selección.</span><span class="sxs-lookup"><span data-stu-id="54001-202">Select the **Sales group line picking** menu item to initiate the pick.</span></span>
1. <span data-ttu-id="54001-203">Introducir el valor del **ID de trabajo** que anotó en el procedimiento anterior.</span><span class="sxs-lookup"><span data-stu-id="54001-203">Enter the **Work ID** value that you made a note of in the previous procedure.</span></span>

    <span data-ttu-id="54001-204">Debería ver un paso de selección donde todas las líneas de selección para el artículo *M9200* están agrupadas y debería recibir una instrucción para elegir *7* de cada uno de los elementos *M9200*.</span><span class="sxs-lookup"><span data-stu-id="54001-204">You should see a pick step where all pick lines for item *M9200* are grouped, and you should receive an instruction to pick *7* each of item *M9200*.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="54001-205">En el dispositivo móvil, el trabajo de selección para las tres líneas de trabajo de selección se ha agregado en un paso de selección para el usuario.</span><span class="sxs-lookup"><span data-stu-id="54001-205">On the mobile device, the pick work for the three pick work lines has been aggregated into one picking step for the user.</span></span>

1. <span data-ttu-id="54001-206">Confirme el paso de selección.</span><span class="sxs-lookup"><span data-stu-id="54001-206">Confirm the pick step.</span></span>
1. <span data-ttu-id="54001-207">Vaya a la pantalla de trabajo para el ID del trabajo y observe que las tres líneas de selección para el artículo *M9200* se han cerrado simultáneamente.</span><span class="sxs-lookup"><span data-stu-id="54001-207">Go to the work page for the work ID, and notice that all three pick lines for item *M9200* were closed simultaneously.</span></span>
1. <span data-ttu-id="54001-208">Regrese al dispositivo móvil y continúe con la selección.</span><span class="sxs-lookup"><span data-stu-id="54001-208">Go back to the mobile device, and continue to pick.</span></span> <span data-ttu-id="54001-209">La línea de trabajo 4 para el artículo *M9201* debe ser presentada.</span><span class="sxs-lookup"><span data-stu-id="54001-209">Work line 4 for item *M9201* should be presented.</span></span> <span data-ttu-id="54001-210">Debido a que solo había una línea de trabajo en el pedido, no hay nada que agregar.</span><span class="sxs-lookup"><span data-stu-id="54001-210">Because there was only one work line on the order, there is nothing to aggregate.</span></span>
1. <span data-ttu-id="54001-211">Confirme el paso de selección.</span><span class="sxs-lookup"><span data-stu-id="54001-211">Confirm the pick step.</span></span>
1. <span data-ttu-id="54001-212">El último paso de selección en el dispositivo móvil agrega las dos últimas líneas de selección de la orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="54001-212">The last pick step on the mobile device aggregates the last two pick lines from the work order.</span></span>
1. <span data-ttu-id="54001-213">Complete el paso de selección para *9* de cada uno del artículo *M9202*.</span><span class="sxs-lookup"><span data-stu-id="54001-213">Complete the pick step for *9* each of item *M9202*.</span></span>
1. <span data-ttu-id="54001-214">Confirme el paso de colocación y cualquier par adicional de selección/colocación para completar el trabajo.</span><span class="sxs-lookup"><span data-stu-id="54001-214">Confirm the put step and any additional pick/put pairs to complete the work.</span></span>

> [!IMPORTANT]
>
> - <span data-ttu-id="54001-215">Las líneas de trabajo solo se pueden agrupar si están en secuencia.</span><span class="sxs-lookup"><span data-stu-id="54001-215">Work lines can be grouped only if they are in sequence.</span></span>
> - <span data-ttu-id="54001-216">No se admite la siguiente funcionalidad:</span><span class="sxs-lookup"><span data-stu-id="54001-216">The following functionality isn't supported:</span></span>
>
>   - <span data-ttu-id="54001-217">Artículos con peso capturado</span><span class="sxs-lookup"><span data-stu-id="54001-217">Catch-weight items</span></span>
>
>    <span data-ttu-id="54001-218">Si hay artículos con peso capturado en el trabajo, recibirá un mensaje de error antes de iniciar la selección.</span><span class="sxs-lookup"><span data-stu-id="54001-218">If there are any catch-weight items on the work, you receive an error message before you start to pick.</span></span>
>
>   - <span data-ttu-id="54001-219">Selección de piezas</span><span class="sxs-lookup"><span data-stu-id="54001-219">Piece picking</span></span>
>   - <span data-ttu-id="54001-220">Líneas de trabajo que tienen trabajo de reabastecimiento sin terminar</span><span class="sxs-lookup"><span data-stu-id="54001-220">Work lines that have unfinished replenishment work</span></span>
>   - <span data-ttu-id="54001-221">Selección en exceso</span><span class="sxs-lookup"><span data-stu-id="54001-221">Over-picking</span></span>
>   - <span data-ttu-id="54001-222">Selección corta con reasignación de artículos</span><span class="sxs-lookup"><span data-stu-id="54001-222">Short picking with item reallocation</span></span>
