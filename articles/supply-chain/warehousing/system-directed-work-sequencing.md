---
title: Secuenciación del trabajo dirigida por el sistema
description: En este tema se ofrece información sobre la secuencia del trabajo dirigida por el sistema. Esta funcionalidad le permite ordenar y filtrar las órdenes de trabajo que el sistema presenta a los usuarios para su ejecución. Resulta útil en escenarios donde se requieren criterios adicionales para realizar el proceso de picking del almacén.
author: Mirzaab
manager: tfehr
ms.date: 07/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFSystemDirectedWorkSequenceQuery, WHSLocDirTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-03
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: 3811486a31d079cac7f7c27ea6323f16de4478d5
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4970215"
---
# <a name="system-directed-work-sequencing"></a><span data-ttu-id="a840f-105">Secuenciación del trabajo dirigida por el sistema</span><span class="sxs-lookup"><span data-stu-id="a840f-105">System-directed work sequencing</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a840f-106">La secuenciación del trabajo dirigida por el sistema le permite ordenar y filtrar las órdenes de trabajo que el sistema presenta a los usuarios para su ejecución.</span><span class="sxs-lookup"><span data-stu-id="a840f-106">System-directed work sequencing lets you sort and filter the work orders that the system presents to users for execution.</span></span> <span data-ttu-id="a840f-107">Resulta útil en escenarios donde se requieren criterios adicionales (como el tiempo de envío, la zona de picking, el perfil de ubicación o una combinación de varios criterios) para realizar el proceso de picking del almacén.</span><span class="sxs-lookup"><span data-stu-id="a840f-107">It's helpful in scenarios where additional criteria (such as the time of shipping, the picking zone, the location profile, or a combination of various criteria) are required to drive the warehouse picking process.</span></span>

<span data-ttu-id="a840f-108">Esta funcionalidad amplía la funcionalidad actual de picking dirigido por el sistema al agregar una orden de consulta dirigida por el sistema, donde los usuarios pueden configurar una secuencia y una o más consultas que evaluarán todas las órdenes de trabajo que se crean.</span><span class="sxs-lookup"><span data-stu-id="a840f-108">This functionality extends the current system-directed picking functionality by adding a system-directed query order, where users can set up a sequence and one or more queries that will evaluate all work orders that are created.</span></span> <span data-ttu-id="a840f-109">Solo se capturarán y presentarán las órdenes de trabajo que cumplan los criterios especificados en la configuración del elemento del menú del dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="a840f-109">Only work orders that meet the criteria that are specified in the setup of the mobile device menu item will be captured and presented.</span></span>

<span data-ttu-id="a840f-110">Por lo tanto, esta funcionalidad permite una mayor optimización de los procesos de picking del almacén, ya que identifica las órdenes de trabajo que coinciden con los criterios especificados, las asigna al elemento de menú correcto del dispositivo móvil y luego las presenta a un trabajador, en función de un conjunto de habilidades concretas, equipo de picking u otro requisito.</span><span class="sxs-lookup"><span data-stu-id="a840f-110">Therefore, this functionality allows for further optimization of warehouse picking processes as it identifies work orders that match the specified criteria, assigns them to the correct mobile device menu item, and then presents them to a worker, based on a specific skill set, picking equipment, or other requirement.</span></span>

> [!NOTE]
> <span data-ttu-id="a840f-111">Si se necesitan diferentes criterios, se deben usar varios elementos del menú del dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="a840f-111">If different criteria are needed, multiple mobile device menu items must be used.</span></span>

## <a name="turn-on-the-organization-wide-system-directed-work-sequencing-feature"></a><span data-ttu-id="a840f-112">Activar la característica Secuenciación del trabajo dirigida por el sistema en toda la organización</span><span class="sxs-lookup"><span data-stu-id="a840f-112">Turn on the Organization-wide system directed work sequencing feature</span></span>

<span data-ttu-id="a840f-113">Antes de poder usar la secuenciación del trabajo dirigida por el sistema, la característica debe estar activada en su sistema.</span><span class="sxs-lookup"><span data-stu-id="a840f-113">Before you can use system-directed work sequencing, the feature must be turned on in your system.</span></span> <span data-ttu-id="a840f-114">Los administradores pueden usar el espacio de trabajo [Administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de la característica y activarla si es necesario.</span><span class="sxs-lookup"><span data-stu-id="a840f-114">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="a840f-115">Allí, la característica se enumera de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="a840f-115">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="a840f-116">**Módulo:** *Gestión de almacén*</span><span class="sxs-lookup"><span data-stu-id="a840f-116">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="a840f-117">**Nombre de la característica**: *Secuencia de trabajo dirigida al sistema de secuenciación de trabajo*</span><span class="sxs-lookup"><span data-stu-id="a840f-117">**Feature name:** *Organization-wide system directed work sequencing*</span></span>

## <a name="setup"></a><span data-ttu-id="a840f-118">Configurar</span><span class="sxs-lookup"><span data-stu-id="a840f-118">Setup</span></span>

### <a name="make-demo-data-available"></a><span data-ttu-id="a840f-119">Hacer que los datos de demostración estén disponibles</span><span class="sxs-lookup"><span data-stu-id="a840f-119">Make demo data available</span></span>

<span data-ttu-id="a840f-120">Para resolver el escenario utilizando los valores que se presentan en este tema, debe trabajar en un sistema donde se instalen datos de demostración estándar.</span><span class="sxs-lookup"><span data-stu-id="a840f-120">To work through the scenario by using the values that are presented in this topic, you must work on a system where the standard demo data is installed.</span></span> <span data-ttu-id="a840f-121">Además, también debe seleccionar la entidad legal **USMF**.</span><span class="sxs-lookup"><span data-stu-id="a840f-121">Additionally, you must select the **USMF** legal entity.</span></span> <span data-ttu-id="a840f-122">El escenario utiliza el almacén *51* de los datos de demostración.</span><span class="sxs-lookup"><span data-stu-id="a840f-122">The scenario uses warehouse *51* from the demo data.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a840f-123">Antes de liberar los pedidos al almacén, asegúrese de que las ubicaciones de picking tengan suficiente inventario para todos los artículos de los pedidos.</span><span class="sxs-lookup"><span data-stu-id="a840f-123">Before you release the orders to the warehouse, make sure that the pick locations have enough inventory for all the items on the orders.</span></span>
>
> <span data-ttu-id="a840f-124">Los datos predeterminados de USMF deberían admitir este escenario.</span><span class="sxs-lookup"><span data-stu-id="a840f-124">Default USMF data should support this scenario.</span></span> <span data-ttu-id="a840f-125">Si no va a usar datos de demostración, revise la configuración de **Directiva de ubicación** para descubrir qué ubicaciones de picking se utilizan para el picking de pedidos de ventas.</span><span class="sxs-lookup"><span data-stu-id="a840f-125">If you aren't using demo data, review the **Location directive** setting to learn which picking locations are used for sales order picking.</span></span> <span data-ttu-id="a840f-126">Si debe ajustar el inventario, puede crear movimientos manuales, utilizar la reposición o utilizar cualquier otro flujo.</span><span class="sxs-lookup"><span data-stu-id="a840f-126">If you must adjust the inventory, you can create manual movements, use replenishment, or use any other flow.</span></span>

### <a name="set-up-a-mobile-device-menu-item"></a><span data-ttu-id="a840f-127">Configurar un elemento de menú del dispositivo móvil</span><span class="sxs-lookup"><span data-stu-id="a840f-127">Set up a mobile device menu item</span></span>

1. <span data-ttu-id="a840f-128">Vaya a **Administración de almacenes \> Configurar \> Dispositivo móvil \> Elementos de menú del dispositivo móvil**.</span><span class="sxs-lookup"><span data-stu-id="a840f-128">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="a840f-129">En la lista de elementos de menú del dispositivo móvil, seleccione **Picking de ventas - Sistema**.</span><span class="sxs-lookup"><span data-stu-id="a840f-129">In the list of mobile device menu items, select **Sales Picking – System**.</span></span> <span data-ttu-id="a840f-130">El elemento de menú requerido ya debería existir.</span><span class="sxs-lookup"><span data-stu-id="a840f-130">The required menu item should already exist.</span></span> 
1. <span data-ttu-id="a840f-131">Confirme los siguientes ajustes:</span><span class="sxs-lookup"><span data-stu-id="a840f-131">Confirm the following settings:</span></span>

    - <span data-ttu-id="a840f-132">En la ficha desplegable **General**, el campo **Dirigido por** debe establecerse en *Sistema dirigido*.</span><span class="sxs-lookup"><span data-stu-id="a840f-132">On the **General** FastTab, the **Directed by** field should be set to *System directed*.</span></span>
    - <span data-ttu-id="a840f-133">La ficha rápida **Clases de trabajo** debería mostrar la siguiente configuración.</span><span class="sxs-lookup"><span data-stu-id="a840f-133">The **Work classes** FastTab should show the following settings.</span></span>

        | <span data-ttu-id="a840f-134">Identificador de la clase de trabajo</span><span class="sxs-lookup"><span data-stu-id="a840f-134">Work class ID</span></span> | <span data-ttu-id="a840f-135">Tipo de pedido de trabajo</span><span class="sxs-lookup"><span data-stu-id="a840f-135">Work order type</span></span> |
        |---|---|
        | <span data-ttu-id="a840f-136">Sales</span><span class="sxs-lookup"><span data-stu-id="a840f-136">Sales</span></span> | <span data-ttu-id="a840f-137">Pedidos de ventas</span><span class="sxs-lookup"><span data-stu-id="a840f-137">Sales orders</span></span> |
        | <span data-ttu-id="a840f-138">Picking de pedidos de ventas</span><span class="sxs-lookup"><span data-stu-id="a840f-138">SO Pick</span></span> | <span data-ttu-id="a840f-139">Pedidos de ventas</span><span class="sxs-lookup"><span data-stu-id="a840f-139">Sales orders</span></span> |

1. <span data-ttu-id="a840f-140">En el panel de acciones, seleccione **Consultas de secuencias de trabajo dirigidas por el sistema**.</span><span class="sxs-lookup"><span data-stu-id="a840f-140">On the Action Pane, select **System directed work sequence queries**.</span></span>
1. <span data-ttu-id="a840f-141">Seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="a840f-141">Select **Edit**.</span></span>
1. <span data-ttu-id="a840f-142">Elimine la línea existente y luego confirme la acción seleccionando **Sí**.</span><span class="sxs-lookup"><span data-stu-id="a840f-142">Delete the existing line, and then confirm the action by selecting **Yes**.</span></span>
1. <span data-ttu-id="a840f-143">En el panel de acciones, haga clic en **Nuevo** para crear una línea.</span><span class="sxs-lookup"><span data-stu-id="a840f-143">On the Action Pane, select **New** to create a line.</span></span>
1. <span data-ttu-id="a840f-144">En la nueva línea, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="a840f-144">On the new line, set the following values:</span></span>

    - <span data-ttu-id="a840f-145">**Número de secuencia:** *1*</span><span class="sxs-lookup"><span data-stu-id="a840f-145">**Sequence number:** *1*</span></span>
    - <span data-ttu-id="a840f-146">**Campo de descripción:** *Cantidad de trabajo inferior a 20 y descendente*</span><span class="sxs-lookup"><span data-stu-id="a840f-146">**Description field:** *Work quantity less than 20 and Descending*</span></span>

1. <span data-ttu-id="a840f-147">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="a840f-147">Select **Save**.</span></span>
1. <span data-ttu-id="a840f-148">En el panel de acciones, seleccione **Editar consulta**.</span><span class="sxs-lookup"><span data-stu-id="a840f-148">On the Action Pane, select **Edit Query**.</span></span>
1. <span data-ttu-id="a840f-149">En la pestaña **Combinaciones**, expanda la jerarquía de combinación para mostrar la tabla **Lineas de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="a840f-149">On the **Joins** tab, expand the join hierarchy to show the **Work lines** table.</span></span>
1. <span data-ttu-id="a840f-150">Seleccione la combinación de tabla **Lineas de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="a840f-150">Select the **Work lines** table join.</span></span>
1. <span data-ttu-id="a840f-151">Seleccione **Agregar unión de tabla**.</span><span class="sxs-lookup"><span data-stu-id="a840f-151">Select **Add table join**.</span></span>
1. <span data-ttu-id="a840f-152">En la lista que aparece, busque y seleccione la fila que tiene la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="a840f-152">In the list that appears, find and select the row that has the following settings:</span></span>

    - <span data-ttu-id="a840f-153">**Modo de combinación:** *n:1*</span><span class="sxs-lookup"><span data-stu-id="a840f-153">**Join mode:** *n:1*</span></span>
    - <span data-ttu-id="a840f-154">**Relación:** *Ubicaciones (ubicación)*</span><span class="sxs-lookup"><span data-stu-id="a840f-154">**Relation:** *Locations (Location)*</span></span>

1. <span data-ttu-id="a840f-155">Seleccione **Seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="a840f-155">Select **Select**.</span></span>

    <span data-ttu-id="a840f-156">Las ubicaciones se agregan a la combinación de tabla.</span><span class="sxs-lookup"><span data-stu-id="a840f-156">Locations are added to the table join.</span></span>

1. <span data-ttu-id="a840f-157">En la pestaña **Ordenación**, seleccione **Agregar** para agregar una línea.</span><span class="sxs-lookup"><span data-stu-id="a840f-157">On the **Sorting** tab, select **Add** to add a line.</span></span>
1. <span data-ttu-id="a840f-158">En la nueva línea, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="a840f-158">On the new line, set the following values:</span></span>

    - <span data-ttu-id="a840f-159">**Tabla:** *Lineas de trabajo*</span><span class="sxs-lookup"><span data-stu-id="a840f-159">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="a840f-160">**Tabla derivada:** *Líneas de trabajo*</span><span class="sxs-lookup"><span data-stu-id="a840f-160">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="a840f-161">**Campo:** *Cantidad de trabajo* (En el cuadro de mensaje que aparece, seleccione **Sí** para agregar una ordenación a este campo).</span><span class="sxs-lookup"><span data-stu-id="a840f-161">**Field:** *Work quantity* (In the message box that appears, select **Yes** to add sorting to this field.)</span></span>
    - <span data-ttu-id="a840f-162">**Dirección de búsqueda:** *Descendente*</span><span class="sxs-lookup"><span data-stu-id="a840f-162">**Search direction:** *Descending*</span></span>

1. <span data-ttu-id="a840f-163">Seleccione la ficha **Intervalo**.</span><span class="sxs-lookup"><span data-stu-id="a840f-163">Select the **Range** tab.</span></span>

    <span data-ttu-id="a840f-164">Si solo se deben incluir criterios de trabajo concretos en la secuenciación, puede especificarlos en la pestaña **Intervalo**. En este ejemplo, desea incluir solo el trabajo donde la cantidad es inferior a 20 ea (la unidad de medida más baja).</span><span class="sxs-lookup"><span data-stu-id="a840f-164">If only specific work criteria should be included in the sequencing, you can specify them on the **Range** tab. In this example, you want to include only work where the quantity is less than 20 ea (the lowest unit of measure).</span></span>

    <span data-ttu-id="a840f-165">Tenga en cuenta que algunas líneas ya están incluidas.</span><span class="sxs-lookup"><span data-stu-id="a840f-165">Notice that some lines are already included.</span></span> <span data-ttu-id="a840f-166">Esas líneas no deben eliminarse.</span><span class="sxs-lookup"><span data-stu-id="a840f-166">Those lines should not be removed.</span></span>

1. <span data-ttu-id="a840f-167">Seleccione **Agregar** para agregar una línea.</span><span class="sxs-lookup"><span data-stu-id="a840f-167">Select **Add** to add a line.</span></span>
1. <span data-ttu-id="a840f-168">En la nueva línea, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="a840f-168">On the new line, set the following values:</span></span>

    - <span data-ttu-id="a840f-169">**Tabla:** *Lineas de trabajo*</span><span class="sxs-lookup"><span data-stu-id="a840f-169">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="a840f-170">**Tabla derivada:** *Líneas de trabajo*</span><span class="sxs-lookup"><span data-stu-id="a840f-170">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="a840f-171">**Campo:** *Cantidad de trabajo de inventario*</span><span class="sxs-lookup"><span data-stu-id="a840f-171">**Field:** *Inventory work quantity*</span></span>
    - <span data-ttu-id="a840f-172">**Criterios:** *\<20* (menos de 20)</span><span class="sxs-lookup"><span data-stu-id="a840f-172">**Criteria:** *\<20* (less than 20)</span></span>

1. <span data-ttu-id="a840f-173">Seleccione **Agregar** para agregar otra línea.</span><span class="sxs-lookup"><span data-stu-id="a840f-173">Select **Add** to add another line.</span></span>
1. <span data-ttu-id="a840f-174">En la nueva línea, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="a840f-174">On the new line, set the following values:</span></span>

    - <span data-ttu-id="a840f-175">**Tabla:** *Lineas de trabajo*</span><span class="sxs-lookup"><span data-stu-id="a840f-175">**Table:** *Work lines*</span></span>
    - <span data-ttu-id="a840f-176">**Tabla derivada:** *Líneas de trabajo*</span><span class="sxs-lookup"><span data-stu-id="a840f-176">**Derived table:** *Work lines*</span></span>
    - <span data-ttu-id="a840f-177">**Campo:** *Tipo de trabajo*</span><span class="sxs-lookup"><span data-stu-id="a840f-177">**Field:** *Work type*</span></span>
    - <span data-ttu-id="a840f-178">**Criterios:** *Seleccionar*</span><span class="sxs-lookup"><span data-stu-id="a840f-178">**Criteria:** *Pick*</span></span>

1. <span data-ttu-id="a840f-179">Seleccione **Agregar** para agregar otra línea.</span><span class="sxs-lookup"><span data-stu-id="a840f-179">Select **Add** to add another line.</span></span>
1. <span data-ttu-id="a840f-180">En la nueva línea, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="a840f-180">On the new line, set the following values:</span></span>

    - <span data-ttu-id="a840f-181">**Tabla**: *Ubicaciones*</span><span class="sxs-lookup"><span data-stu-id="a840f-181">**Table:** *Locations*</span></span>
    - <span data-ttu-id="a840f-182">**Tabla derivada:** *Ubicaciones*</span><span class="sxs-lookup"><span data-stu-id="a840f-182">**Derived table:** *Locations*</span></span>
    - <span data-ttu-id="a840f-183">**Campo**: *ID de perfil de ubicación*</span><span class="sxs-lookup"><span data-stu-id="a840f-183">**Field:** *Location profile ID*</span></span>
    - <span data-ttu-id="a840f-184">**Criterios:** *!ALMACENAR*</span><span class="sxs-lookup"><span data-stu-id="a840f-184">**Criteria:** *!STAGE*</span></span>

        > [!IMPORTANT]
        > <span data-ttu-id="a840f-185">Asegúrese de incluir el signo de exclamación (*!*) delante de *ALMACENAR*.</span><span class="sxs-lookup"><span data-stu-id="a840f-185">Be sure to include the exclamation point (*!*) in front of *STAGE*.</span></span>

1. <span data-ttu-id="a840f-186">Seleccione **Aceptar** para guardar y cerrar la consulta.</span><span class="sxs-lookup"><span data-stu-id="a840f-186">Select **OK** to save and close the query.</span></span>
1. <span data-ttu-id="a840f-187">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="a840f-187">Select **Save**.</span></span>
1. <span data-ttu-id="a840f-188">Cierre la página para volver a la página **Elementos de menú del dispositivo móvil**.</span><span class="sxs-lookup"><span data-stu-id="a840f-188">Close the page to return to the **Mobile device menu items** page.</span></span>

> [!NOTE]
> <span data-ttu-id="a840f-189">Esta configuración define los criterios que se utilizarán para alimentar el trabajo elegible al elemento del menú del dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="a840f-189">This setup defines the criteria that will be used to feed eligible work to the mobile device menu item.</span></span> <span data-ttu-id="a840f-190">Si agrega más líneas de criterios a la consulta, el sistema usará primero la línea de consulta que tenga el número de secuencia más bajo.</span><span class="sxs-lookup"><span data-stu-id="a840f-190">If you add more criteria lines to the query, the system will use the query line that has lowest sequence number first.</span></span> <span data-ttu-id="a840f-191">Es decir, primero se presentará al usuario todo el trabajo elegible para la secuencia número 1 y después todo el trabajo para la secuencia número 2.</span><span class="sxs-lookup"><span data-stu-id="a840f-191">In other words, all eligible work for sequence number 1 will be presented to the user first, and then all work for sequence number 2.</span></span> <span data-ttu-id="a840f-192">Por lo tanto, si un rango y ordenación concretos deben usarse juntos, deben especificarse en la misma consulta de secuencia de trabajo dirigida por el sistema.</span><span class="sxs-lookup"><span data-stu-id="a840f-192">Therefore, if a specific range and sorting must be used together, they should be specified in the same system-directed work sequence query.</span></span>
>
> <span data-ttu-id="a840f-193">Esta configuración capturará cualquier trabajo que tenga al menos una línea donde la cantidad sea inferior a 20 ea.</span><span class="sxs-lookup"><span data-stu-id="a840f-193">This setup will capture any work that has at least one line where the quantity is less than 20 ea.</span></span> <span data-ttu-id="a840f-194">Por lo tanto, si el trabajo tiene una línea donde la cantidad es exactamente 20 ea o más de 20 ea, será válido siempre que también tenga al menos una línea donde la cantidad sea menor que 20 ea.</span><span class="sxs-lookup"><span data-stu-id="a840f-194">Therefore, if the work has a line where the quantity is exactly 20 ea or more than 20 ea, it will be valid, provided that it also has at least one line where the quantity is less than 20 ea.</span></span>

### <a name="location-directives"></a><span data-ttu-id="a840f-195">Directivas de ubicación</span><span class="sxs-lookup"><span data-stu-id="a840f-195">Location directives</span></span>

<span data-ttu-id="a840f-196">Si va a utilizar datos de Contoso predeterminados, la consulta de la acción de directiva de ubicación no requerirá cambios.</span><span class="sxs-lookup"><span data-stu-id="a840f-196">If you're using default Contoso data, the query for the location directive action won't require changes.</span></span> <span data-ttu-id="a840f-197">No obstante, para asegurarse de que las directivas de ubicación capturarán los artículos en los pedidos de ventas cuando aplique la característica en un entorno que no sea de Contoso, cree una nueva directiva de ubicación.</span><span class="sxs-lookup"><span data-stu-id="a840f-197">However, to make sure that the location directives will capture the items on the sales orders when you apply the feature in a non-Contoso environment, create a new location directive.</span></span> <span data-ttu-id="a840f-198">Para verificar la configuración en el entorno de demostración, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="a840f-198">To verify the settings in the demo environment, follow these steps.</span></span>

1. <span data-ttu-id="a840f-199">Vaya a **Gestión de almacenes** \> **Configurar** \> **Directivas de ubicación**.</span><span class="sxs-lookup"><span data-stu-id="a840f-199">Go to **Warehouse management** \> **Setup** \> **Location directives**.</span></span>
1. <span data-ttu-id="a840f-200">En el campo **Tipo de orden de trabajo**, seleccione *Pedidos de ventas*.</span><span class="sxs-lookup"><span data-stu-id="a840f-200">In the **Work order type** field, select *Sales orders*.</span></span>
1. <span data-ttu-id="a840f-201">Seleccione la directiva de ubicación que se denomina *51 Seleccionar*.</span><span class="sxs-lookup"><span data-stu-id="a840f-201">Select the location directive that is named *51 Pick*.</span></span>
1. <span data-ttu-id="a840f-202">En la ficha desplegable **Acciones de directiva de ubicación**, seleccione la línea para la acción **Seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="a840f-202">On the **Location Directive Actions** FastTab, select the line for the **Pick** action.</span></span>
1. <span data-ttu-id="a840f-203">Seleccione **Editar consulta** encima de la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="a840f-203">Select **Edit query** above the grid.</span></span>
1. <span data-ttu-id="a840f-204">Revise la consulta **Intervalo**.</span><span class="sxs-lookup"><span data-stu-id="a840f-204">Review the **Range** query.</span></span>

    1. <span data-ttu-id="a840f-205">Encuentre la línea donde el campo **Campo** se establece en *Ubicación*.</span><span class="sxs-lookup"><span data-stu-id="a840f-205">Find the line where the **Field** field is set to *Location*.</span></span>
    2. <span data-ttu-id="a840f-206">Asegúrese de que el campo **Criterios** está en blanco (es decir, no hay restricciones).</span><span class="sxs-lookup"><span data-stu-id="a840f-206">Make sure that the **Criteria** field is blank (that is, there are no restrictions).</span></span>

## <a name="scenario"></a><span data-ttu-id="a840f-207">Situación</span><span class="sxs-lookup"><span data-stu-id="a840f-207">Scenario</span></span>

### <a name="create-sales-order-picking-work"></a><span data-ttu-id="a840f-208">Crear trabajo de picking de pedido de ventas</span><span class="sxs-lookup"><span data-stu-id="a840f-208">Create sales order picking work</span></span>

<span data-ttu-id="a840f-209">Antes de ejecutar el picking dirigido por el sistema, debe crearse un trabajo de salida.</span><span class="sxs-lookup"><span data-stu-id="a840f-209">Before system-directed picking is run, some outbound work should be created.</span></span> <span data-ttu-id="a840f-210">Para este escenario, creará cuatro pedidos de ventas que se basan en las consultas de secuencia de trabajo dirigidas por el sistema especificadas.</span><span class="sxs-lookup"><span data-stu-id="a840f-210">For this scenario, you will create four sales orders that are based on the specified system-directed work sequence queries.</span></span>

<span data-ttu-id="a840f-211">Reservará cantidades de inventario para cada pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="a840f-211">You will reserve inventory quantities for each sales order.</span></span> <span data-ttu-id="a840f-212">Por tanto, el inventario reservado no se puede sacar del almacén para otros pedidos excepto que se cancele la reserva de inventario o parte de esta.</span><span class="sxs-lookup"><span data-stu-id="a840f-212">Therefore, reserved inventory can't be withdrawn from the warehouse for other orders unless the inventory reservation, or part of the inventory reservation, is canceled.</span></span>

<span data-ttu-id="a840f-213">A continuación, liberará cada pedido de ventas al almacén para crear el trabajo de salida.</span><span class="sxs-lookup"><span data-stu-id="a840f-213">You will then release each sales order to the warehouse to create the outbound work.</span></span>

#### <a name="sales-order-1"></a><span data-ttu-id="a840f-214">Pedido de ventas 1</span><span class="sxs-lookup"><span data-stu-id="a840f-214">Sales order 1</span></span>

1. <span data-ttu-id="a840f-215">Vaya a **Ventas y marketing \> Pedidos de ventas \> Todos los pedidos de ventas**.</span><span class="sxs-lookup"><span data-stu-id="a840f-215">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="a840f-216">En el panel de acciones, haga clic en **Nuevo** para crear un pedido de ventas 1.</span><span class="sxs-lookup"><span data-stu-id="a840f-216">On the Action Pane, select **New** to create sales order 1.</span></span>
1. <span data-ttu-id="a840f-217">En el cuadro de diálogo **Crear pedido de ventas**, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="a840f-217">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="a840f-218">En la sección **Cliente**, establezca el campo **Cuenta de cliente** en *US-004*.</span><span class="sxs-lookup"><span data-stu-id="a840f-218">In the **Customer** section, set the **Customer account** field to *US-004*.</span></span>
    - <span data-ttu-id="a840f-219">En la sección **General**, establezca el campo **Almacén** en *51*.</span><span class="sxs-lookup"><span data-stu-id="a840f-219">In the **General** section, set the **Warehouse** field to *51*.</span></span>

1. <span data-ttu-id="a840f-220">Haga clic en **Aceptar** para cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="a840f-220">Select **OK** to close the dialog box.</span></span> <span data-ttu-id="a840f-221">Anote el número del pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="a840f-221">Make a note of the sales order number.</span></span>
1. <span data-ttu-id="a840f-222">Agregue una línea al nuevo pedido de ventas y establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="a840f-222">Add a line to the new sales order, and set the following values:</span></span>

    - <span data-ttu-id="a840f-223">**Código de artículo:** *M9200*</span><span class="sxs-lookup"><span data-stu-id="a840f-223">**Item number:** *M9200*</span></span>
    - <span data-ttu-id="a840f-224">**Cantidad:** *20*</span><span class="sxs-lookup"><span data-stu-id="a840f-224">**Quantity:** *20*</span></span>

1. <span data-ttu-id="a840f-225">En el menú **Inventario** sobre la cuadrícula, seleccione **Reserva**.</span><span class="sxs-lookup"><span data-stu-id="a840f-225">On the **Inventory** menu above the grid, select **Reservation**.</span></span>
1. <span data-ttu-id="a840f-226">En la página **Reserva**, seleccione **Reservar lote** para reservar el inventario.</span><span class="sxs-lookup"><span data-stu-id="a840f-226">On the **Reservation** page, select **Reserve lot** to reserve the inventory.</span></span>
1. <span data-ttu-id="a840f-227">Cierre la página **Reserva**.</span><span class="sxs-lookup"><span data-stu-id="a840f-227">Close the **Reservation** page.</span></span>
1. <span data-ttu-id="a840f-228">En el panel de acciones, en la pestaña **Almacén**, seleccione **Liberar al almacén** para crear un trabajo para el almacén.</span><span class="sxs-lookup"><span data-stu-id="a840f-228">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse** to create work for the warehouse.</span></span>

    <span data-ttu-id="a840f-229">Recibirá mensajes informativos que muestran el trabajo, el id. de oleada y los id. de envío que se crean para el pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="a840f-229">You receive informational messages that show the wave ID and shipment IDs that were created for the sales order.</span></span>

#### <a name="sales-order-2"></a><span data-ttu-id="a840f-230">Pedido de ventas 2</span><span class="sxs-lookup"><span data-stu-id="a840f-230">Sales order 2</span></span>

1. <span data-ttu-id="a840f-231">En el panel de acciones, haga clic en **Nuevo** para crear un pedido de ventas 2.</span><span class="sxs-lookup"><span data-stu-id="a840f-231">On the Action Pane, select **New** to create sales order 2.</span></span>
1. <span data-ttu-id="a840f-232">En el cuadro de diálogo **Crear pedido de ventas**, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="a840f-232">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="a840f-233">**Cuenta de cliente:** *US-007*</span><span class="sxs-lookup"><span data-stu-id="a840f-233">**Customer account:** *US-007*</span></span>
    - <span data-ttu-id="a840f-234">**Almacén**: *51*</span><span class="sxs-lookup"><span data-stu-id="a840f-234">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="a840f-235">Haga clic en **Aceptar** para cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="a840f-235">Select **OK** to close the dialog box.</span></span> <span data-ttu-id="a840f-236">Anote el número del pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="a840f-236">Make a note of the sales order number.</span></span>
1. <span data-ttu-id="a840f-237">Agregue una línea al nuevo pedido de ventas y establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="a840f-237">Add a line to the new sales order, and set the following values:</span></span>

    - <span data-ttu-id="a840f-238">**Código de artículo:** *M9200*</span><span class="sxs-lookup"><span data-stu-id="a840f-238">**Item number:** *M9200*</span></span>
    - <span data-ttu-id="a840f-239">**Cantidad:** *5*</span><span class="sxs-lookup"><span data-stu-id="a840f-239">**Quantity:** *5*</span></span>

1. <span data-ttu-id="a840f-240">Seleccione **Agregar línea** para agregar una segunda línea de pedido de compra y establecer los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="a840f-240">Select **Add line** to add a second line, and set the following values:</span></span>

    - <span data-ttu-id="a840f-241">**Código de artículo:** *M9201*</span><span class="sxs-lookup"><span data-stu-id="a840f-241">**Item number:** *M9201*</span></span>
    - <span data-ttu-id="a840f-242">**Cantidad:** *1*</span><span class="sxs-lookup"><span data-stu-id="a840f-242">**Quantity:** *1*</span></span>

1. <span data-ttu-id="a840f-243">Reserve inventario para ambas líneas.</span><span class="sxs-lookup"><span data-stu-id="a840f-243">Reserve inventory for both lines.</span></span>
1. <span data-ttu-id="a840f-244">Libere el pedido al almacén.</span><span class="sxs-lookup"><span data-stu-id="a840f-244">Release the order to the warehouse.</span></span>

#### <a name="sales-order-3"></a><span data-ttu-id="a840f-245">Pedido de ventas 3</span><span class="sxs-lookup"><span data-stu-id="a840f-245">Sales order 3</span></span>

1. <span data-ttu-id="a840f-246">En el panel de acciones, haga clic en **Nuevo** para crear un pedido de ventas 3.</span><span class="sxs-lookup"><span data-stu-id="a840f-246">On the Action Pane, select **New** to create sales order 3.</span></span>
1. <span data-ttu-id="a840f-247">En el cuadro de diálogo **Crear pedido de ventas**, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="a840f-247">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="a840f-248">**Cuenta de cliente:** *US-009*</span><span class="sxs-lookup"><span data-stu-id="a840f-248">**Customer account:** *US-009*</span></span>
    - <span data-ttu-id="a840f-249">**Almacén**: *51*</span><span class="sxs-lookup"><span data-stu-id="a840f-249">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="a840f-250">Haga clic en **Aceptar** para cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="a840f-250">Select **OK** to close the dialog box.</span></span> <span data-ttu-id="a840f-251">Anote el número del pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="a840f-251">Make a note of the sales order number.</span></span>
1. <span data-ttu-id="a840f-252">Agregue una línea al nuevo pedido de ventas y establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="a840f-252">Add a line to the new sales order, and set the following values:</span></span>

    - <span data-ttu-id="a840f-253">**Código de artículo:** *M9200*</span><span class="sxs-lookup"><span data-stu-id="a840f-253">**Item number:** *M9200*</span></span>
    - <span data-ttu-id="a840f-254">**Cantidad:** *7*</span><span class="sxs-lookup"><span data-stu-id="a840f-254">**Quantity:** *7*</span></span>

1. <span data-ttu-id="a840f-255">Seleccione **Agregar línea** para agregar una segunda línea de pedido de compra y establecer los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="a840f-255">Select **Add line** to add a second line, and set the following values:</span></span>

    - <span data-ttu-id="a840f-256">**Código de artículo:** *M9202*</span><span class="sxs-lookup"><span data-stu-id="a840f-256">**Item number:** *M9202*</span></span>
    - <span data-ttu-id="a840f-257">**Cantidad:** *8*</span><span class="sxs-lookup"><span data-stu-id="a840f-257">**Quantity:** *8*</span></span>

1. <span data-ttu-id="a840f-258">Reserve inventario para ambas líneas.</span><span class="sxs-lookup"><span data-stu-id="a840f-258">Reserve inventory for both lines.</span></span>
1. <span data-ttu-id="a840f-259">Libere el pedido al almacén.</span><span class="sxs-lookup"><span data-stu-id="a840f-259">Release the order to the warehouse.</span></span>

#### <a name="sales-order-4"></a><span data-ttu-id="a840f-260">Pedido de ventas 4</span><span class="sxs-lookup"><span data-stu-id="a840f-260">Sales order 4</span></span>

1. <span data-ttu-id="a840f-261">En el panel de acciones, haga clic en **Nuevo** para crear un pedido de ventas 4.</span><span class="sxs-lookup"><span data-stu-id="a840f-261">On the Action Pane, select **New** to create sales order 4.</span></span>
1. <span data-ttu-id="a840f-262">En el cuadro de diálogo **Crear pedido de ventas**, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="a840f-262">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="a840f-263">**Cuenta de cliente:** *US-010*</span><span class="sxs-lookup"><span data-stu-id="a840f-263">**Customer account:** *US-010*</span></span>
    - <span data-ttu-id="a840f-264">**Almacén**: *51*</span><span class="sxs-lookup"><span data-stu-id="a840f-264">**Warehouse:** *51*</span></span>

1. <span data-ttu-id="a840f-265">Haga clic en **Aceptar** para cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="a840f-265">Select **OK** to close the dialog box.</span></span> <span data-ttu-id="a840f-266">Anote el número del pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="a840f-266">Make a note of the sales order number.</span></span>
1. <span data-ttu-id="a840f-267">Agregue una línea al nuevo pedido de ventas y establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="a840f-267">Add a line to the new sales order, and set the following values:</span></span>

    - <span data-ttu-id="a840f-268">**Código de artículo:** *M9200*</span><span class="sxs-lookup"><span data-stu-id="a840f-268">**Item number:** *M9200*</span></span>
    - <span data-ttu-id="a840f-269">**Cantidad:** *25*</span><span class="sxs-lookup"><span data-stu-id="a840f-269">**Quantity:** *25*</span></span>

1. <span data-ttu-id="a840f-270">Seleccione **Agregar línea** para agregar una segunda línea de pedido de compra y establecer los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="a840f-270">Select **Add line** to add a second line, and set the following values:</span></span>

    - <span data-ttu-id="a840f-271">**Código de artículo:** *M9202*</span><span class="sxs-lookup"><span data-stu-id="a840f-271">**Item number:** *M9202*</span></span>
    - <span data-ttu-id="a840f-272">**Cantidad:** *10*</span><span class="sxs-lookup"><span data-stu-id="a840f-272">**Quantity:** *10*</span></span>

1. <span data-ttu-id="a840f-273">Reserve inventario para ambas líneas.</span><span class="sxs-lookup"><span data-stu-id="a840f-273">Reserve inventory for both lines.</span></span>
1. <span data-ttu-id="a840f-274">Libere el pedido al almacén.</span><span class="sxs-lookup"><span data-stu-id="a840f-274">Release the order to the warehouse.</span></span>

### <a name="get-work-ids-for-the-work-that-was-created"></a><span data-ttu-id="a840f-275">Obtener id. de trabajo para el trabajo que se creó</span><span class="sxs-lookup"><span data-stu-id="a840f-275">Get work IDs for the work that was created</span></span>

1. <span data-ttu-id="a840f-276">Vaya a **Gestión de almacenes \> Trabajo \> Detalles de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="a840f-276">Go to **Warehouse management \> Work \> Work details**.</span></span>
1. <span data-ttu-id="a840f-277">Filtre el campo **Almacén** para que solo se muestre el trabajo para el almacén *51*.</span><span class="sxs-lookup"><span data-stu-id="a840f-277">Filter on the **Warehouse** field so that only work for warehouse *51* is shown.</span></span>
1. <span data-ttu-id="a840f-278">Deben haberse creado cuatro id. de trabajo.</span><span class="sxs-lookup"><span data-stu-id="a840f-278">Four work IDs should have been created.</span></span> <span data-ttu-id="a840f-279">Anote el id. de trabajo de cada pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="a840f-279">Make a note of the work ID for each sales order.</span></span>

    | <span data-ttu-id="a840f-280">Id. de pedido de ventas</span><span class="sxs-lookup"><span data-stu-id="a840f-280">Sales order ID</span></span> | <span data-ttu-id="a840f-281">Id. de trabajo</span><span class="sxs-lookup"><span data-stu-id="a840f-281">Work ID</span></span> | <span data-ttu-id="a840f-282">Cantidad de trabajo</span><span class="sxs-lookup"><span data-stu-id="a840f-282">Work quantity</span></span> |
    |---|---|---|
    | <span data-ttu-id="a840f-283">Pedido de ventas 1</span><span class="sxs-lookup"><span data-stu-id="a840f-283">Sales Order 1</span></span> | <span data-ttu-id="a840f-284">Id. de trabajo 1</span><span class="sxs-lookup"><span data-stu-id="a840f-284">Work ID 1</span></span> | <span data-ttu-id="a840f-285">20 ea</span><span class="sxs-lookup"><span data-stu-id="a840f-285">20 ea</span></span> |
    | <span data-ttu-id="a840f-286">Pedido de ventas 2</span><span class="sxs-lookup"><span data-stu-id="a840f-286">Sales Order 2</span></span> | <span data-ttu-id="a840f-287">Id. de trabajo 2</span><span class="sxs-lookup"><span data-stu-id="a840f-287">Work ID 2</span></span> | <span data-ttu-id="a840f-288">6 ea (suma de ambas líneas)</span><span class="sxs-lookup"><span data-stu-id="a840f-288">6 ea (sum of both lines)</span></span> |
    | <span data-ttu-id="a840f-289">Pedido de ventas 3</span><span class="sxs-lookup"><span data-stu-id="a840f-289">Sales Order 3</span></span> | <span data-ttu-id="a840f-290">Id. de trabajo 3</span><span class="sxs-lookup"><span data-stu-id="a840f-290">Work ID 3</span></span> | <span data-ttu-id="a840f-291">15 ea (suma de ambas líneas)</span><span class="sxs-lookup"><span data-stu-id="a840f-291">15 ea (sum of both lines)</span></span> |
    | <span data-ttu-id="a840f-292">Pedido de ventas 4</span><span class="sxs-lookup"><span data-stu-id="a840f-292">Sales Order 4</span></span> | <span data-ttu-id="a840f-293">Id. de trabajo 4</span><span class="sxs-lookup"><span data-stu-id="a840f-293">Work ID 4</span></span> | <span data-ttu-id="a840f-294">35 ea (suma de ambas líneas)</span><span class="sxs-lookup"><span data-stu-id="a840f-294">35 ea (sum of both lines)</span></span> |

<span data-ttu-id="a840f-295">Antes de ejecutar el flujo en el dispositivo móvil, asegúrese de que solo el trabajo que acaba de crear esté en estado *Abierto* para el almacén *51* y el tipo de pedido de trabajo *Pedido de ventas*.</span><span class="sxs-lookup"><span data-stu-id="a840f-295">Before you run the flow on the mobile device, make sure that only the work that you just created is in *Open* status for warehouse *51* and the *Sales order* work order type.</span></span> <span data-ttu-id="a840f-296">De lo contrario, los resultados de la prueba pueden variar, porque el picking dirigido por el sistema incluirá todo el trabajo elegible.</span><span class="sxs-lookup"><span data-stu-id="a840f-296">Otherwise, the results of the test might vary, because the system-direct picking will include all eligible work.</span></span>

1. <span data-ttu-id="a840f-297">Vaya **Gestión de almacenes \> Trabajo \> Salida \> Trabajo de ventas abierto**.</span><span class="sxs-lookup"><span data-stu-id="a840f-297">Go to **Warehouse management \> Work \> Outbound \> Open sales work**.</span></span>
1. <span data-ttu-id="a840f-298">En la cuadrícula **Trabajo de ventas abierto**, filtre el campo **Almacén** para que solo se muestre el trabajo para el almacén *51*.</span><span class="sxs-lookup"><span data-stu-id="a840f-298">In the **Open sales work** grid, filter on the **Warehouse** field so that only work for warehouse *51* is shown.</span></span>
1. <span data-ttu-id="a840f-299">Confirme que solo se muestran los cuatro id. de trabajo que creó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="a840f-299">Confirm that only the four work IDs that you created earlier are shown.</span></span>
1. <span data-ttu-id="a840f-300">Cierre la página **Trabajo**.</span><span class="sxs-lookup"><span data-stu-id="a840f-300">Close the **Work** page.</span></span>

### <a name="mobile-device-flow-execution"></a><span data-ttu-id="a840f-301">Ejecución de flujo del dispositivo móvil</span><span class="sxs-lookup"><span data-stu-id="a840f-301">Mobile device flow execution</span></span>

<span data-ttu-id="a840f-302">Según la configuración, el sistema alimentará el trabajo del usuario que se ordena de la cantidad de línea de trabajo más alta a la más baja.</span><span class="sxs-lookup"><span data-stu-id="a840f-302">Based on the setup, the system will feed the user work that is sorted from the highest work line quantity to the lowest.</span></span> <span data-ttu-id="a840f-303">La cantidad en cada línea será inferior a 20 ea.</span><span class="sxs-lookup"><span data-stu-id="a840f-303">The quantity on every line will be less than 20 ea.</span></span>

<span data-ttu-id="a840f-304">Recuerde que esta configuración capturará cualquier trabajo que tenga al menos una línea donde la cantidad sea inferior a 20 ea.</span><span class="sxs-lookup"><span data-stu-id="a840f-304">Remember that this setup will capture any work that has at least one line where the quantity is less than 20 ea.</span></span> <span data-ttu-id="a840f-305">Por lo tanto, si el trabajo tiene otra línea donde la cantidad es exactamente 20 ea o más de 20 ea, también será válida.</span><span class="sxs-lookup"><span data-stu-id="a840f-305">Therefore, if the work has another line where the quantity is exactly 20 ea or more than 20 ea, it will also be valid.</span></span>

#### <a name="mobile-app"></a><span data-ttu-id="a840f-306">Aplicación móvil</span><span class="sxs-lookup"><span data-stu-id="a840f-306">Mobile app</span></span>

1. <span data-ttu-id="a840f-307">Inicie sesión en la aplicación de almacén como un usuario en el almacén *51*.</span><span class="sxs-lookup"><span data-stu-id="a840f-307">Sign in to the warehousing app as a user in warehouse *51*.</span></span>
1. <span data-ttu-id="a840f-308">Vaya a **Salida \> Picking de ventas - Sistema**.</span><span class="sxs-lookup"><span data-stu-id="a840f-308">Go to **Outbound \> Sales Picking - System**.</span></span>

    <span data-ttu-id="a840f-309">Se presenta el paso de selección para el id. de trabajo *4*.</span><span class="sxs-lookup"><span data-stu-id="a840f-309">The pick step for work ID *4* is presented.</span></span> <span data-ttu-id="a840f-310">Este id. de trabajo se presenta primero debido a la configuración de la orden de consulta dirigida por el sistema, donde especificó que el trabajo debe secuenciarse según una cantidad de línea de trabajo descendente.</span><span class="sxs-lookup"><span data-stu-id="a840f-310">This work ID is presented first because of the setup of the system-directed query order, where you specified that work should be sequenced based on descending work line quantity.</span></span>

1. <span data-ttu-id="a840f-311">Complete la selección requerida y colóquela para cerrar el id. de trabajo.</span><span class="sxs-lookup"><span data-stu-id="a840f-311">Complete the required pick and put to close the work ID.</span></span>

    <span data-ttu-id="a840f-312">A continuación, se presenta el id. de trabajo *3*.</span><span class="sxs-lookup"><span data-stu-id="a840f-312">Next, work ID *3* is presented.</span></span> <span data-ttu-id="a840f-313">Una de sus líneas de trabajo es la siguiente en la secuencia, según la cantidad de línea de trabajo.</span><span class="sxs-lookup"><span data-stu-id="a840f-313">One of its work lines is next in the sequence, based on the work line quantity.</span></span>

1. <span data-ttu-id="a840f-314">Complete la selección y colóquela para cerrar el id. de trabajo.</span><span class="sxs-lookup"><span data-stu-id="a840f-314">Complete the pick and put to close the work ID.</span></span>

    <span data-ttu-id="a840f-315">A continuación, se presenta el id. de trabajo *2*.</span><span class="sxs-lookup"><span data-stu-id="a840f-315">Next, work ID *2* is presented.</span></span> <span data-ttu-id="a840f-316">La línea de selección de este trabajo es la siguiente en la secuencia.</span><span class="sxs-lookup"><span data-stu-id="a840f-316">This work's pick line is next in the sequence.</span></span>

1. <span data-ttu-id="a840f-317">Complete la selección y colóquela para cerrar el id. de trabajo.</span><span class="sxs-lookup"><span data-stu-id="a840f-317">Complete the pick and put to close the work ID.</span></span>

    <span data-ttu-id="a840f-318">No se le debe presentar más trabajo.</span><span class="sxs-lookup"><span data-stu-id="a840f-318">No further work should be presented to you.</span></span> <span data-ttu-id="a840f-319">El id. de trabajo *1* no es elegible para este elemento de menú del dispositivo móvil, ya que la consulta especifica que los encabezados de trabajo se consideran solo si la cantidad en las líneas de trabajo es inferior a 20 ea.</span><span class="sxs-lookup"><span data-stu-id="a840f-319">Work ID *1* isn't eligible for this mobile device menu item, because the query specifies that work headers are considered only if the quantity on the work lines is less than 20 ea.</span></span>

## <a name="tips"></a><span data-ttu-id="a840f-320">Sugerencias</span><span class="sxs-lookup"><span data-stu-id="a840f-320">Tips</span></span>

<span data-ttu-id="a840f-321">Las consultas de secuencia de trabajo dirigidas por el sistema son *inclusivas*.</span><span class="sxs-lookup"><span data-stu-id="a840f-321">The system-directed work sequence queries are *inclusive*.</span></span> <span data-ttu-id="a840f-322">Es importante que recuerde este hecho para algunas configuraciones.</span><span class="sxs-lookup"><span data-stu-id="a840f-322">It's important that you remember this fact for some setups.</span></span> <span data-ttu-id="a840f-323">Por ejemplo, desea que un determinado elemento de menú procese solo el trabajo donde la unidad de trabajo es *ea* y especifica esa restricción en la pestaña **Intervalo** de la consulta.</span><span class="sxs-lookup"><span data-stu-id="a840f-323">For example, you want a specific menu item to process only work where the work unit is *ea*, and you specify that restriction on the **Range** tab of the query.</span></span> <span data-ttu-id="a840f-324">En este caso, todo trabajo en el que al menos una línea de trabajo tenga la unidad de trabajo establecida en *ea* será alimentado al trabajo.</span><span class="sxs-lookup"><span data-stu-id="a840f-324">In this case, all work where at least one work line has the work unit set to *ea* will be fed to the worker.</span></span> <span data-ttu-id="a840f-325">Por lo tanto, este trabajo también puede incluir el trabajo en el que las líneas de trabajo tengan una unidad de trabajo distinta de *ea* (como *caja* o *pallet*).</span><span class="sxs-lookup"><span data-stu-id="a840f-325">Therefore, this work might also include work where work lines have a work unit other than *ea* (such as *box* or *pallet*).</span></span> <span data-ttu-id="a840f-326">La consulta excluirá solo el trabajo en el que ninguna línea de trabajo tenga la unidad de trabajo establecida en *ea*.</span><span class="sxs-lookup"><span data-stu-id="a840f-326">The query will exclude only work where no work line has the work unit set to *ea*.</span></span>

<span data-ttu-id="a840f-327">Por lo tanto, en el ejemplo de este escenario, la consulta también capturó el id. de trabajo *4*.</span><span class="sxs-lookup"><span data-stu-id="a840f-327">Therefore, in the example from this scenario, work ID *4* was also captured by the query.</span></span> <span data-ttu-id="a840f-328">Cuando se creó, se agregaron dos líneas: una para 25 ea y otra para 10 ea.</span><span class="sxs-lookup"><span data-stu-id="a840f-328">When it was created, two lines were added: one for 25 ea and another for 10 ea.</span></span> <span data-ttu-id="a840f-329">El trabajo se siguió presentando al usuario, porque al menos una línea de trabajo tiene una cantidad inferior a 20 ea.</span><span class="sxs-lookup"><span data-stu-id="a840f-329">The work was still presented to the user, because at least one work line has a quantity of less than 20 ea.</span></span>

<span data-ttu-id="a840f-330">Dependiendo del escenario, puede evitar este comportamiento utilizando interrupciones de trabajo.</span><span class="sxs-lookup"><span data-stu-id="a840f-330">Depending on the scenario, you can prevent this behavior by using work breaks.</span></span>
