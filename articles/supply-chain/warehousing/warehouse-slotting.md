---
title: Slotting de almacén
description: En este tema se proporciona información acerca del slotting de almacén. El slotting de almacén le permite consolidar la demanda por artículo y unidad de medida de los pedidos que tienen un estado de Pedido, Reservado o Liberado. Ayuda a los directores de almacén a planificar de manera inteligente las ubicaciones de picking antes de liberar pedidos al almacén y crear trabajos de picking.
author: mirzaab
manager: tfehr
ms.date: 11/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSInventFixedLocation, WHSSlotDemandLocated, WHSSlotDemand, WHSSlotUOMTier, WHSSlotTemplate, WHSLocDirHint, WHSLocDirTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: fb39daba393944471ee5d412b1eb61754843926f
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4993762"
---
# <a name="warehouse-slotting"></a><span data-ttu-id="fd516-105">Slotting de almacén</span><span class="sxs-lookup"><span data-stu-id="fd516-105">Warehouse slotting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="fd516-106">Se encuentran disponibles varias funciones de asignación de posiciones en el almacén para ayudar a los gerentes de almacén a planificar de manera inteligente las ubicaciones de picking antes de entregar los pedidos al almacén y crear el trabajo de picking.</span><span class="sxs-lookup"><span data-stu-id="fd516-106">Several warehouse slotting features are available to help warehouse managers intelligently plan picking locations before they release orders to the warehouse and create picking work.</span></span>

<span data-ttu-id="fd516-107">La *característica de slotting de almacén* le permite consolidar la demanda por artículo y unidad de medida de los pedidos que tienen un estado de *Pedido*, *Reservado* o *Liberado*.</span><span class="sxs-lookup"><span data-stu-id="fd516-107">The *Warehouse slotting feature* lets you consolidate demand by item and unit of measure from orders that have a status of *Ordered*, *Reserved*, or *Released*.</span></span> <span data-ttu-id="fd516-108">La demanda generada se puede aplicar a las ubicaciones que se utilizarán para el picking, en función de la cantidad, la unidad, las dimensiones físicas, las ubicaciones fijas y más.</span><span class="sxs-lookup"><span data-stu-id="fd516-108">Generated demand can then be applied to locations that will be used for picking, based on quantity, unit, physical dimensions, fixed locations, and more.</span></span> <span data-ttu-id="fd516-109">Una vez que se ha establecido el plan de slotting, se puede crear un trabajo de reabastecimiento para llevar la cantidad adecuada de inventario a cada ubicación.</span><span class="sxs-lookup"><span data-stu-id="fd516-109">After the slotting plan has been established, replenishment work can be created to bring the appropriate amount of inventory to each location.</span></span>

<span data-ttu-id="fd516-110">La función *Posicionamiento de almacén para órdenes de transferencia* permite a los gerentes de almacén reabastecer las ubicaciones de preparación de pedidos, según la demanda de los pedidos de transferencia que aún no se entregan al almacén.</span><span class="sxs-lookup"><span data-stu-id="fd516-110">The *Warehouse slotting for transfer orders* feature lets warehouse managers replenish picking locations, based on demand from transfer orders that aren't yet released to the warehouse.</span></span> <span data-ttu-id="fd516-111">Asegura que las ubicaciones de picking incluyan todos los artículos que se requieren para las órdenes de transferencia después de que se entregan al almacén.</span><span class="sxs-lookup"><span data-stu-id="fd516-111">It ensures that picking locations will include all the items that are required for the transfer orders after they are released to warehouse.</span></span> <span data-ttu-id="fd516-112">Esta función requiere que también active la *Función de posicionamiento de almacén*.</span><span class="sxs-lookup"><span data-stu-id="fd516-112">This feature requires that you also turn on the *Warehouse slotting feature* feature.</span></span>

<span data-ttu-id="fd516-113">La función *Mejoras en la asignación de espacios en el almacén* agrega una opción para las líneas de plantilla que son utilizadas por la *Función de posicionamiento de almacén*.</span><span class="sxs-lookup"><span data-stu-id="fd516-113">The *Warehouse slotting allocation enhancements* feature adds an option for the template lines that are used by the *Warehouse slotting feature* feature.</span></span> <span data-ttu-id="fd516-114">La opción permite que el sistema considere el inventario disponible existente en una ubicación objetivo.</span><span class="sxs-lookup"><span data-stu-id="fd516-114">The option enables the system to consider existing on-hand inventory at a target location.</span></span> <span data-ttu-id="fd516-115">Por lo tanto, se podrían generar menos reposiciones para la asignación.</span><span class="sxs-lookup"><span data-stu-id="fd516-115">Therefore, fewer replenishments might be generated for slotting.</span></span> <span data-ttu-id="fd516-116">La función *Mejoras en la asignación de espacios en el almacén* requiere que también active la *Función de slotting de almacén*.</span><span class="sxs-lookup"><span data-stu-id="fd516-116">The *Warehouse slotting allocation enhancements* feature requires that you also turn on the *Warehouse slotting feature* feature.</span></span> <span data-ttu-id="fd516-117">Opcionalmente se puede utilizar junto con la característica *Posicionamiento de almacén para órdenes de transferencia*.</span><span class="sxs-lookup"><span data-stu-id="fd516-117">It can optionally be used together with the *Warehouse slotting for transfer orders* feature.</span></span>

## <a name="turn-on-the-warehouse-slotting-features"></a><span data-ttu-id="fd516-118">Activar las características de slotting de almacén</span><span class="sxs-lookup"><span data-stu-id="fd516-118">Turn on the warehouse slotting features</span></span>

<span data-ttu-id="fd516-119">Antes de poder usar estas características, deben estar activadas en su sistema.</span><span class="sxs-lookup"><span data-stu-id="fd516-119">Before you can use these features, they must be turned on in your system.</span></span> <span data-ttu-id="fd516-120">Los administradores pueden usar la configuración de [gestión de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de estas características y activarlas si es necesario.</span><span class="sxs-lookup"><span data-stu-id="fd516-120">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the features and turn them on if they are required.</span></span> <span data-ttu-id="fd516-121">Active las siguientes funciones según sea necesario:</span><span class="sxs-lookup"><span data-stu-id="fd516-121">Turn on the following features as required:</span></span>

- <span data-ttu-id="fd516-122">Función de asignación de almacén</span><span class="sxs-lookup"><span data-stu-id="fd516-122">Warehouse slotting feature</span></span>
- <span data-ttu-id="fd516-123">Slotting de almacén para pedidos de transferencia</span><span class="sxs-lookup"><span data-stu-id="fd516-123">Warehouse slotting for transfer orders</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="fd516-124">La *Función de posicionamiento de almacén* debe estar activada antes de esta función.</span><span class="sxs-lookup"><span data-stu-id="fd516-124">The *Warehouse slotting feature* feature must be turned on before this feature.</span></span>

- <span data-ttu-id="fd516-125">Mejoras de asignación de slotting de almacén</span><span class="sxs-lookup"><span data-stu-id="fd516-125">Warehouse slotting allocation enhancements</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="fd516-126">La *Función de posicionamiento de almacén* debe estar activada antes de esta función.</span><span class="sxs-lookup"><span data-stu-id="fd516-126">The *Warehouse slotting feature* feature must be turned on before this feature.</span></span>

## <a name="set-up-warehouse-slotting"></a><span data-ttu-id="fd516-127">Configurar slotting de almacén</span><span class="sxs-lookup"><span data-stu-id="fd516-127">Set up warehouse slotting</span></span>

<span data-ttu-id="fd516-128">Antes de utilizar el slotting de almacén, debe configurar los siguiente elementos en su sistema:</span><span class="sxs-lookup"><span data-stu-id="fd516-128">To use warehouse slotting, you must set up the following elements in your system:</span></span>

- <span data-ttu-id="fd516-129">Niveles de unidad de medida de slotting</span><span class="sxs-lookup"><span data-stu-id="fd516-129">Slotting unit of measure tiers</span></span>
- <span data-ttu-id="fd516-130">Códigos de directiva</span><span class="sxs-lookup"><span data-stu-id="fd516-130">Directive codes</span></span>
- <span data-ttu-id="fd516-131">Plantillas de slotting</span><span class="sxs-lookup"><span data-stu-id="fd516-131">Slotting templates</span></span>
- <span data-ttu-id="fd516-132">Directivas de ubicación</span><span class="sxs-lookup"><span data-stu-id="fd516-132">Location directives</span></span>

### <a name="create-unit-of-measure-tiers-for-slotting"></a><a name="unit-tiers"></a><span data-ttu-id="fd516-133">Crear niveles de unidad de medida para slotting</span><span class="sxs-lookup"><span data-stu-id="fd516-133">Create unit-of-measure tiers for slotting</span></span>

<span data-ttu-id="fd516-134">Los niveles de unidad de medida permiten agrupar varias unidades de medida a efectos de slotting.</span><span class="sxs-lookup"><span data-stu-id="fd516-134">Unit-of-measure tiers enable multiple units of measure to be grouped together for the purposes of slotting.</span></span> <span data-ttu-id="fd516-135">Por ejemplo, si se seleccionan varios tamaños de cajas de la misma área de picking de cajas, se puede crear un nivel para todos los tamaños.</span><span class="sxs-lookup"><span data-stu-id="fd516-135">For example, if multiple sizes of boxes are all picked from the same box picking area, one tier can be created for all the sizes.</span></span> <span data-ttu-id="fd516-136">**Se debe crear una línea para cada unidad de medida que debe formar parte del nivel.**</span><span class="sxs-lookup"><span data-stu-id="fd516-136">**A line must be created for each unit of measure that should be part of the tier.**</span></span>

1. <span data-ttu-id="fd516-137">Vaya a **Gestión de almacenes \> Configuración \> Reabastecimiento \> Niveles de unidad de medida de slotting**.</span><span class="sxs-lookup"><span data-stu-id="fd516-137">Go to **Warehouse management \> Setup \> Replenishment \> Slotting unit of measure tiers**.</span></span>
1. <span data-ttu-id="fd516-138">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="fd516-138">Select **New**.</span></span>
1. <span data-ttu-id="fd516-139">Establezca los siguientes valores en el encabezado:</span><span class="sxs-lookup"><span data-stu-id="fd516-139">In the header, set the following values:</span></span>

    - <span data-ttu-id="fd516-140">**Nivel de unidad de medida:** *EaBoxPl*</span><span class="sxs-lookup"><span data-stu-id="fd516-140">**Unit of measure tier:** *EaBoxPl*</span></span>
    - <span data-ttu-id="fd516-141">**Descripción:** *cada pallet de cajas*</span><span class="sxs-lookup"><span data-stu-id="fd516-141">**Description:** *Each box pallet*</span></span>

1. <span data-ttu-id="fd516-142">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="fd516-142">Select **Save**.</span></span>
1. <span data-ttu-id="fd516-143">En la ficha desplegable **Unidades de medida**, seleccione **Nuevo** para agregar una línea a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="fd516-143">On the **Units of measure** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="fd516-144">En la nueva línea, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="fd516-144">On the new line, set the following values:</span></span>

    - <span data-ttu-id="fd516-145">**Unidad:** *caja*</span><span class="sxs-lookup"><span data-stu-id="fd516-145">**Unit:** *Box*</span></span>
    - <span data-ttu-id="fd516-146">**Descripción**: deje este campo en blanco.</span><span class="sxs-lookup"><span data-stu-id="fd516-146">**Description:** Leave this field blank.</span></span> <span data-ttu-id="fd516-147">Se rellenará automáticamente cuando guarde los cambios.</span><span class="sxs-lookup"><span data-stu-id="fd516-147">It will be filled in automatically when you save your changes.</span></span>
    - <span data-ttu-id="fd516-148">**Clase de unidad:** *cantidad*</span><span class="sxs-lookup"><span data-stu-id="fd516-148">**Unit class:** *Quantity*</span></span>

1. <span data-ttu-id="fd516-149">Seleccione **Nuevo** para agregar una segunda línea a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="fd516-149">Select **New** to add a second line to the grid.</span></span>
1. <span data-ttu-id="fd516-150">En la nueva línea, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="fd516-150">On the new line, set the following values:</span></span>

    - <span data-ttu-id="fd516-151">**Unidad**: *u*</span><span class="sxs-lookup"><span data-stu-id="fd516-151">**Unit:** *ea*</span></span>
    - <span data-ttu-id="fd516-152">**Descripción**: deje este campo en blanco.</span><span class="sxs-lookup"><span data-stu-id="fd516-152">**Description:** Leave this field blank.</span></span> <span data-ttu-id="fd516-153">Se rellenará automáticamente cuando guarde los cambios.</span><span class="sxs-lookup"><span data-stu-id="fd516-153">It will be filled in automatically when you save your changes.</span></span>
    - <span data-ttu-id="fd516-154">**Clase de unidad:** *cantidad*</span><span class="sxs-lookup"><span data-stu-id="fd516-154">**Unit class:** *Quantity*</span></span>

1. <span data-ttu-id="fd516-155">Seleccione **Nuevo** para agregar una tercera línea a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="fd516-155">Select **New** to add a third line to the grid.</span></span>
1. <span data-ttu-id="fd516-156">En la nueva línea, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="fd516-156">On the new line, set the following values:</span></span>

    - <span data-ttu-id="fd516-157">**Unidad:** *PL*</span><span class="sxs-lookup"><span data-stu-id="fd516-157">**Unit:** *PL*</span></span>
    - <span data-ttu-id="fd516-158">**Descripción**: deje este campo en blanco.</span><span class="sxs-lookup"><span data-stu-id="fd516-158">**Description:** Leave this field blank.</span></span> <span data-ttu-id="fd516-159">Se rellenará automáticamente cuando guarde los cambios.</span><span class="sxs-lookup"><span data-stu-id="fd516-159">It will be filled in automatically when you save your changes.</span></span>
    - <span data-ttu-id="fd516-160">**Clase de unidad:** *Cantidad*</span><span class="sxs-lookup"><span data-stu-id="fd516-160">**Unit class:** *Quantity*</span></span>

1. <span data-ttu-id="fd516-161">Seleccione **Guardar** para guardar el nivel.</span><span class="sxs-lookup"><span data-stu-id="fd516-161">Select **Save** to save the tier.</span></span>

### <a name="create-a-directive-code-for-slotting"></a><span data-ttu-id="fd516-162">Crear un código de directiva para slotting</span><span class="sxs-lookup"><span data-stu-id="fd516-162">Create a directive code for slotting</span></span>

<span data-ttu-id="fd516-163">Debe seleccionar el código de directiva que debe asociarse a una plantilla.</span><span class="sxs-lookup"><span data-stu-id="fd516-163">You must select the directive code that should be associated with a template.</span></span>

1. <span data-ttu-id="fd516-164">Vaya a **Gestión de almacenes \> Configurar \> Códigos de directivas**.</span><span class="sxs-lookup"><span data-stu-id="fd516-164">Go to **Warehouse management \> Setup \> Directive codes**.</span></span>
1. <span data-ttu-id="fd516-165">En el panel de acciones, haga clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="fd516-165">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="fd516-166">En el campo **Código de la directiva**, introduzca *Slotting*.</span><span class="sxs-lookup"><span data-stu-id="fd516-166">In the **Directive code** field, enter *Slotting*.</span></span>
1. <span data-ttu-id="fd516-167">En el campo **Descripción de la directiva**, introduzca *Slotting*.</span><span class="sxs-lookup"><span data-stu-id="fd516-167">In the **Directive description** field, enter *Slotting*.</span></span>

### <a name="set-up-slotting-templates"></a><span data-ttu-id="fd516-168">Configurar plantillas de slotting</span><span class="sxs-lookup"><span data-stu-id="fd516-168">Set up slotting templates</span></span>

<span data-ttu-id="fd516-169">Cada plantilla de slotting controla cómo se asigna el inventario a las ubicaciones de un determinado almacén.</span><span class="sxs-lookup"><span data-stu-id="fd516-169">Each slotting template controls how inventory is assigned to locations for a specific warehouse.</span></span> <span data-ttu-id="fd516-170">Cada plantilla debe incluir una línea para cada especificación de slotting.</span><span class="sxs-lookup"><span data-stu-id="fd516-170">Each template must include a line for each slotting specification.</span></span> <span data-ttu-id="fd516-171">Use los procedimientos de esta sección para configurar plantillas de slotting.</span><span class="sxs-lookup"><span data-stu-id="fd516-171">Use the procedures in this section to set up slotting templates.</span></span>

1. <span data-ttu-id="fd516-172">Vaya a **Administración de almacenes \> Configurar \> Reabastecimiento \> Plantillas de reabastecimiento**.</span><span class="sxs-lookup"><span data-stu-id="fd516-172">Go to **Warehouse management \> Setup \> Replenishment \> Slotting templates**.</span></span>
1. <span data-ttu-id="fd516-173">Seleccione **Nuevo** para crear una página.</span><span class="sxs-lookup"><span data-stu-id="fd516-173">Select **New** to create a template.</span></span>

<span data-ttu-id="fd516-174">A continuación, debe configurar el encabezado de la plantilla, las especificaciones de slotting y las directivas de ubicación, como se explica en las subsecciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="fd516-174">Next, you must set up the template header, slotting specifications, and location directives, as explained in the following subsections.</span></span> <span data-ttu-id="fd516-175">La configuración de asignación para órdenes de transferencia se parece a la configuración para asignación de órdenes de venta, pero el campo **Tipo de demanda** está configurado como *Órdenes de transferencia* en lugar de *Órdenes de venta*.</span><span class="sxs-lookup"><span data-stu-id="fd516-175">The setup for slotting for transfer orders resembles the setup for slotting for sales orders, but the **Demand type** field is set *Transfer orders* instead of *Sales order*.</span></span>

#### <a name="set-up-the-header-for-a-sales-order-slotting-template"></a><span data-ttu-id="fd516-176">Configurar el encabezado para una plantilla de asignación de pedidos de ventas</span><span class="sxs-lookup"><span data-stu-id="fd516-176">Set up the header for a sales order slotting template</span></span>

1. <span data-ttu-id="fd516-177">En el encabezado de la plantilla, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="fd516-177">In the header for the template, set the following values:</span></span>

    - <span data-ttu-id="fd516-178">**Plantilla de slotting:** _61_</span><span class="sxs-lookup"><span data-stu-id="fd516-178">**Slotting template:** _61_</span></span>
    - <span data-ttu-id="fd516-179">**Descripción:** _61_</span><span class="sxs-lookup"><span data-stu-id="fd516-179">**Description:** _61_</span></span>
    - <span data-ttu-id="fd516-180">**Tipo de demanda:** *Pedido de ventas*</span><span class="sxs-lookup"><span data-stu-id="fd516-180">**Demand type:** *Sales order*</span></span>

        > [!NOTE]
        > <span data-ttu-id="fd516-181">Actualmente, *Ordenes de venta* y *Órdenes de transferencia* son los únicos tipos de demanda admitidos.</span><span class="sxs-lookup"><span data-stu-id="fd516-181">Currently, *Sales orders* and *Transfer orders* are the only demand types that are supported.</span></span> <span data-ttu-id="fd516-182">Puede elegir *Órdenes de transferencia* solo si la función *Slotting de almacén para órdenes de transporte* está activada.</span><span class="sxs-lookup"><span data-stu-id="fd516-182">You can select *Transfer orders* only if the *Warehouse Slotting for transfer orders* feature is turned on.</span></span>

    - <span data-ttu-id="fd516-183">**Estrategia de demanda:** _Pedido_</span><span class="sxs-lookup"><span data-stu-id="fd516-183">**Demand strategy:** _Ordered_</span></span>

        <span data-ttu-id="fd516-184">Los siguientes valores están disponibles en este campo:</span><span class="sxs-lookup"><span data-stu-id="fd516-184">The following values are available in this field:</span></span>

        - <span data-ttu-id="fd516-185">**Pedido**: la cantidad pedida completa en el pedido de ventas debe considerarse demanda.</span><span class="sxs-lookup"><span data-stu-id="fd516-185">**Ordered** – The full ordered quantity on the sales order should be considered demand.</span></span>
        - <span data-ttu-id="fd516-186">**Reservado**: solo las cantidades de la línea de pedido de ventas que se reservan (físicas y pedidas) deben considerarse demanda.</span><span class="sxs-lookup"><span data-stu-id="fd516-186">**Reserved** – Only the sales order line quantities that are reserved (physical and ordered) should be considered demand.</span></span>
        - <span data-ttu-id="fd516-187">**Liberado** - La cantidad liberada debe considerarse demanda.</span><span class="sxs-lookup"><span data-stu-id="fd516-187">**Released** – The released quantity should be considered demand.</span></span>

    - <span data-ttu-id="fd516-188">**Almacén**: _61_</span><span class="sxs-lookup"><span data-stu-id="fd516-188">**Warehouse:** _61_</span></span>
    - <span data-ttu-id="fd516-189">**Permitir demanda de oleadas para usar cantidades sin reservar:** _sí_</span><span class="sxs-lookup"><span data-stu-id="fd516-189">**Allow wave demand to use unreserved quantities:** _Yes_</span></span>

<span data-ttu-id="fd516-190">También puede especificar una consulta para reducir el alcance de la demanda que se evalúa.</span><span class="sxs-lookup"><span data-stu-id="fd516-190">You can also specify a query to narrow the scope of the demand that is evaluated.</span></span>

#### <a name="set-up-slotting-specifications-for-each-template"></a><span data-ttu-id="fd516-191">Configurar especificaciones de slotting para cada plantilla</span><span class="sxs-lookup"><span data-stu-id="fd516-191">Set up slotting specifications for each template</span></span>

<span data-ttu-id="fd516-192">Para cada plantilla de pedido de ventas que cree, siga estos pasos para agregar una línea para cada especificación de slotting.</span><span class="sxs-lookup"><span data-stu-id="fd516-192">For each sales order template that you create, follow these steps to add a line for each slotting specification.</span></span>

1. <span data-ttu-id="fd516-193">En la ficha desplegable **Detalles de plantilla de slotting**, seleccione **Nuevo** para crear una línea de plantilla.</span><span class="sxs-lookup"><span data-stu-id="fd516-193">On the **Slotting template details** FastTab, select **New** to create a template line.</span></span>
1. <span data-ttu-id="fd516-194">En la nueva línea, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="fd516-194">On the new line, set the following values:</span></span>

    - <span data-ttu-id="fd516-195">**Secuencia**: _1_</span><span class="sxs-lookup"><span data-stu-id="fd516-195">**Sequence:** _1_</span></span>
    - <span data-ttu-id="fd516-196">**Descripción:** _Ubicación fija_</span><span class="sxs-lookup"><span data-stu-id="fd516-196">**Description:** _Fixed location_</span></span>
    - <span data-ttu-id="fd516-197">**Cantidad mínima**: _1_</span><span class="sxs-lookup"><span data-stu-id="fd516-197">**Minimum quantity:** _1_</span></span>

        <span data-ttu-id="fd516-198">Este campo define la cantidad mínima de demanda que se requiere para la línea.</span><span class="sxs-lookup"><span data-stu-id="fd516-198">This field defines the minimum quantity of demand that is required for the line.</span></span>

    - <span data-ttu-id="fd516-199">**Cantidad máxima:** _1000000_</span><span class="sxs-lookup"><span data-stu-id="fd516-199">**Maximum quantity:** _1000000_</span></span>

        <span data-ttu-id="fd516-200">Este campo define la cantidad máxima de demanda que es válida para la línea.</span><span class="sxs-lookup"><span data-stu-id="fd516-200">This field defines the maximum quantity of demand that is valid for the line.</span></span>

    - <span data-ttu-id="fd516-201">**Unidad:** deje este campo en blanco.</span><span class="sxs-lookup"><span data-stu-id="fd516-201">**Unit:** Leave this field blank.</span></span>

        <span data-ttu-id="fd516-202">Este campo define la unidad de medida a la que hacen referencia las cantidades mínima y máxima.</span><span class="sxs-lookup"><span data-stu-id="fd516-202">This field defines the unit of measure that the minimum and maximum quantities refer to.</span></span>

    - <span data-ttu-id="fd516-203">**Nivel de unidad de medida:** _EaBoxPl_</span><span class="sxs-lookup"><span data-stu-id="fd516-203">**Unit of Measure Tier:** _EaBoxPl_</span></span>

        <span data-ttu-id="fd516-204">Este campo define las unidades de medida de demanda que son válidas para la línea.</span><span class="sxs-lookup"><span data-stu-id="fd516-204">This field defines the units of measure of demand that are valid for the line.</span></span> <span data-ttu-id="fd516-205">(Para obtener más información, consulte la sección [Configurar niveles de unidad de medida para slotting](#unit-tiers) que se indica previamente en este tema.)</span><span class="sxs-lookup"><span data-stu-id="fd516-205">(For more information, see the [Set up unit-of-measure tiers for slotting](#unit-tiers) section earlier in this topic.)</span></span>

    - <span data-ttu-id="fd516-206">**Asignar criterios de posición:** _Considere la cantidad_</span><span class="sxs-lookup"><span data-stu-id="fd516-206">**Assign slot criteria:** _Consider qty_</span></span>

        <span data-ttu-id="fd516-207">Los siguientes valores están disponibles en este campo:</span><span class="sxs-lookup"><span data-stu-id="fd516-207">The following values are available in this field:</span></span>

        - <span data-ttu-id="fd516-208">**Asumir vacío**: este sistema debe asumir que todas las ubicaciones en el área de picking están vacías y no debe comprobar esas ubicaciones para el inventario.</span><span class="sxs-lookup"><span data-stu-id="fd516-208">**Assume empty** – This system should assume that all locations in the picking area are empty and should not check those locations for inventory.</span></span>
        - <span data-ttu-id="fd516-209">**Considerar cantidad**: el sistema debe comprobar las ubicaciones en el área de picking para el inventario y no debe omitir las ubicaciones que estén vacías.</span><span class="sxs-lookup"><span data-stu-id="fd516-209">**Consider qty** – The system should check the locations in the picking area for inventory and should skip any locations that aren't empty.</span></span>
        - <span data-ttu-id="fd516-210">**Considerar disponible** - El sistema debe verificar si alguna ubicación de destino contiene cantidades no reservadas para el artículo en la línea de demanda.</span><span class="sxs-lookup"><span data-stu-id="fd516-210">**Consider on-hand** – The system should check whether any target location contains unreserved quantities for the item on the demand line.</span></span> <span data-ttu-id="fd516-211">Si la cantidad es lo suficientemente grande para satisfacer al menos una unidad de la línea de demanda, el registro del plan de distribución generado se reduce por la cantidad disponible.</span><span class="sxs-lookup"><span data-stu-id="fd516-211">If the quantity is large enough to satisfy at least one unit of the demand line, the generated slotting plan record is reduced by the available amount.</span></span> <span data-ttu-id="fd516-212">Por ejemplo, si la demanda es de 10 cajas y hay una caja disponible, la demanda localizada será de nueve cajas.</span><span class="sxs-lookup"><span data-stu-id="fd516-212">For example, if the demand is 10 cases, and one case is on hand, the located demand will be nine cases.</span></span> <span data-ttu-id="fd516-213">Si la demanda es de 10 cajas y hay una caja de cada disponible, la demanda localizada será de 10 cajas.</span><span class="sxs-lookup"><span data-stu-id="fd516-213">If the demand is 10 cases, and one each is on hand, the located demand will be 10 cases.</span></span> <span data-ttu-id="fd516-214">Este valor solo está disponible cuando la función *Mejoras de asignación de slotting de almacén* está activada.</span><span class="sxs-lookup"><span data-stu-id="fd516-214">This value is available only when the *Warehouse slotting allocation enhancements* feature is turned on.</span></span>

    - <span data-ttu-id="fd516-215">**Código de directiva:** _Slotting_</span><span class="sxs-lookup"><span data-stu-id="fd516-215">**Directive code:** _Slotting_</span></span>

        <span data-ttu-id="fd516-216">Este campo define la directiva de ubicación que se utiliza para encontrar la ubicación de picking del trabajo de reabastecimiento.</span><span class="sxs-lookup"><span data-stu-id="fd516-216">This field defines the location directive that is used to find the picking location of the replenishment work.</span></span>

    - <span data-ttu-id="fd516-217">**Ubicación de desbordamiento:** deje este campo en blanco.</span><span class="sxs-lookup"><span data-stu-id="fd516-217">**Overflow location:** Leave this field blank.</span></span>

        <span data-ttu-id="fd516-218">Este campo define la ubicación en la que se coloca el inventario si no se puede encontrar una ubicación para la cantidad cuando se procesa la línea.</span><span class="sxs-lookup"><span data-stu-id="fd516-218">This field defines the location that inventory that is put to if a location can't be found for the quantity when the line is processed.</span></span>

    - <span data-ttu-id="fd516-219">**Permitir interrupción:** _Sí_</span><span class="sxs-lookup"><span data-stu-id="fd516-219">**Allow let up:** _Yes_</span></span>

        <span data-ttu-id="fd516-220">Cuando esta opción se establece en *Sí*, si no se puede crear la posición de ninguna demanda, se creará un trabajo de movimiento para sacar el inventario de las ubicaciones donde hay inventario, pero donde no se creó la posición de nada.</span><span class="sxs-lookup"><span data-stu-id="fd516-220">When this option is set to *Yes*, if any demand can't be slotted, movement work will be created to take inventory out of locations where there is inventory, but where nothing was slotted.</span></span> <span data-ttu-id="fd516-221">La plantilla se ejecuta de nuevo.</span><span class="sxs-lookup"><span data-stu-id="fd516-221">The template is then run again.</span></span> <span data-ttu-id="fd516-222">Esta vez, ignora el inventario en las ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="fd516-222">This time, it ignores the inventory in the locations.</span></span> <span data-ttu-id="fd516-223">Esta funcionalidad funciona mejor cuando el campo **Asignar criterios de posición** se establece en _Considerar cantidad_.</span><span class="sxs-lookup"><span data-stu-id="fd516-223">This functionality works best when the **Assign slot criteria** field is set to _Consider qty_.</span></span>

    - <span data-ttu-id="fd516-224">**Uso de ubicaciones fijas:** _Solo ubicaciones fijas para el producto_</span><span class="sxs-lookup"><span data-stu-id="fd516-224">**Fixed location usage:** _Only fixed locations for the product_</span></span>

        <span data-ttu-id="fd516-225">Los siguientes valores están disponibles en este campo:</span><span class="sxs-lookup"><span data-stu-id="fd516-225">The following values are available in this field:</span></span>

        - <span data-ttu-id="fd516-226">**Ubicaciones fijas y no fijas**: el sistema no debe limitarse a usar solo ubicaciones fijas.</span><span class="sxs-lookup"><span data-stu-id="fd516-226">**Fixed and non-fixed locations** – The system should not be limited to using only fixed locations.</span></span>
        - <span data-ttu-id="fd516-227">**Solo ubicaciones fijas para el producto:** el sistema debe colocarse solo en ubicaciones que son ubicaciones fijas para el producto.</span><span class="sxs-lookup"><span data-stu-id="fd516-227">**Only fixed locations for the product** – The system should slot only to locations that are fixed locations for the product.</span></span>
        - <span data-ttu-id="fd516-228">**Solo ubicaciones fijas para la variante del producto:** el sistema debe colocarse solo en ubicaciones que son ubicaciones fijas para la variante del producto.</span><span class="sxs-lookup"><span data-stu-id="fd516-228">**Only fixed locations for the product variant** – The system should slot only to locations that are fixed locations for the product variant.</span></span>

> [!NOTE]
> <span data-ttu-id="fd516-229">Si la plantilla de ranuras contiene al menos una línea donde el campo **Asignar criterios de espacio** está configurado en *Considerar disponible*, las pausas ya no están permitidas para ninguna línea en la plantilla.</span><span class="sxs-lookup"><span data-stu-id="fd516-229">If the slotting template contains at least one line where the **Assign slot criteria** field is set to *Consider on-hand*, let-ups are no longer allowed for any line in the template.</span></span>

1. <span data-ttu-id="fd516-230">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="fd516-230">Select **Save**.</span></span>
1. <span data-ttu-id="fd516-231">Seleccione **Nuevo** para crear una segunda línea de plantilla.</span><span class="sxs-lookup"><span data-stu-id="fd516-231">Select **New** to create a second template line.</span></span>
1. <span data-ttu-id="fd516-232">En la nueva línea, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="fd516-232">On the new line, set the following values:</span></span>

    - <span data-ttu-id="fd516-233">**Secuencia**: _2_</span><span class="sxs-lookup"><span data-stu-id="fd516-233">**Sequence:** _2_</span></span>
    - <span data-ttu-id="fd516-234">**Descripción:** _Otro_</span><span class="sxs-lookup"><span data-stu-id="fd516-234">**Description:** _Other_</span></span>
    - <span data-ttu-id="fd516-235">**Cantidad mínima:** _1_</span><span class="sxs-lookup"><span data-stu-id="fd516-235">**Minimum Qty:** _1_</span></span>
    - <span data-ttu-id="fd516-236">**Cantidad máxima:** _1000000_</span><span class="sxs-lookup"><span data-stu-id="fd516-236">**Maximum Qty:** _1000000_</span></span>
    - <span data-ttu-id="fd516-237">**Unidad:** deje este campo en blanco.</span><span class="sxs-lookup"><span data-stu-id="fd516-237">**Unit:** Leave this field blank.</span></span>
    - <span data-ttu-id="fd516-238">**Nivel de unidad de medida:** _EaBoxPl_</span><span class="sxs-lookup"><span data-stu-id="fd516-238">**Unit of measure tier:** _EaBoxPl_</span></span>
    - <span data-ttu-id="fd516-239">**Asignar criterios de posición:** _Considere la cantidad_</span><span class="sxs-lookup"><span data-stu-id="fd516-239">**Assign slot criteria:** _Consider qty_</span></span>
    - <span data-ttu-id="fd516-240">**Código de directiva:** _Slotting_</span><span class="sxs-lookup"><span data-stu-id="fd516-240">**Directive code:** _Slotting_</span></span>
    - <span data-ttu-id="fd516-241">**Ubicación de desbordamiento:** deje este campo en blanco.</span><span class="sxs-lookup"><span data-stu-id="fd516-241">**Overflow location:** Leave this field blank.</span></span>
    - <span data-ttu-id="fd516-242">**Permitir interrupción:** _Sí_</span><span class="sxs-lookup"><span data-stu-id="fd516-242">**Allow let up:** _Yes_</span></span>
    - <span data-ttu-id="fd516-243">**Usar ubicaciones fijas:** _Ubicaciones fijas y no fijas_</span><span class="sxs-lookup"><span data-stu-id="fd516-243">**Use fixed locations:** _Fixed and non-fixed locations_</span></span>

    <span data-ttu-id="fd516-244">En la consulta de la segunda línea, ahora especificará los criterios que se utilizan para determinar a qué ubicaciones se puede crear la posición de la demanda para esa línea.</span><span class="sxs-lookup"><span data-stu-id="fd516-244">In the query for the second line, you will now specify the criteria that are used to determine what locations the demand for that line can be slotted to.</span></span>

1. <span data-ttu-id="fd516-245">Seleccione la línea donde el campo **Secuencia** se establece en *2*.</span><span class="sxs-lookup"><span data-stu-id="fd516-245">Select the line where the **Sequence** field is set to *2*.</span></span>
1. <span data-ttu-id="fd516-246">Seleccione **Editar consulta**.</span><span class="sxs-lookup"><span data-stu-id="fd516-246">Select **Edit query**.</span></span>
1. <span data-ttu-id="fd516-247">En la ficha **Rango**, seleccione **Nuevo** para agregar una línea a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="fd516-247">On the **Range** tab, select **Add** to add a line to the grid.</span></span>
1. <span data-ttu-id="fd516-248">En la nueva línea, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="fd516-248">On the new line, set the following values:</span></span>

    - <span data-ttu-id="fd516-249">**Tabla**: *Ubicaciones*</span><span class="sxs-lookup"><span data-stu-id="fd516-249">**Table:** *Locations*</span></span>
    - <span data-ttu-id="fd516-250">**Tabla derivada:** *Ubicaciones*</span><span class="sxs-lookup"><span data-stu-id="fd516-250">**Derived table:** *Locations*</span></span>
    - <span data-ttu-id="fd516-251">**Campo**: *ID de perfil de ubicación*</span><span class="sxs-lookup"><span data-stu-id="fd516-251">**Field:** *Location profile ID*</span></span>
    - <span data-ttu-id="fd516-252">**Criterios:** *Pick-06* (Seleccione el signo más doble \[**++**\] en el campo para expandir la lista y luego seleccione *Pick-06* - *Sitio de picking 6*.)</span><span class="sxs-lookup"><span data-stu-id="fd516-252">**Criteria:** *Pick-06* (Select the double plus sign \[**++**\] in the field to expand the list, and then select *Pick-06* - *Picking Site 6*.)</span></span>

1. <span data-ttu-id="fd516-253">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="fd516-253">Select **OK**.</span></span>

#### <a name="set-up-location-directives"></a><span data-ttu-id="fd516-254">Configurar directivas de ubicación</span><span class="sxs-lookup"><span data-stu-id="fd516-254">Set up location directives</span></span>

<span data-ttu-id="fd516-255">Se debe configurar al menos una directiva de ubicación para admitir selecciones de slotting.</span><span class="sxs-lookup"><span data-stu-id="fd516-255">At least one location directive must be set up to support slotting picks.</span></span> <span data-ttu-id="fd516-256">Use los procedimientos de esta sección para configurar una nueva *directiva de ubicación de reabastecimiento* para selecciones de slotting.</span><span class="sxs-lookup"><span data-stu-id="fd516-256">Use the procedures in this section to set up a new *replenishment location directive* for slotting picks.</span></span>

1. <span data-ttu-id="fd516-257">Vaya a **Gestión de almacenes \> Configurar \> Directivas de ubicación**.</span><span class="sxs-lookup"><span data-stu-id="fd516-257">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="fd516-258">En el panel izquierdo, en el campo **Tipo de orden de trabajo**, seleccione *Reabastecimiento*.</span><span class="sxs-lookup"><span data-stu-id="fd516-258">In the left pane, in the **Work order type** field, select *Replenishment*.</span></span>
1. <span data-ttu-id="fd516-259">En el panel de acciones, haga clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="fd516-259">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="fd516-260">En el encabezado de la nueva directiva de ubicación, en el campo **Nombre**, introduzca *61 Selección de slotting*.</span><span class="sxs-lookup"><span data-stu-id="fd516-260">In the header for the new location directive, in the **Name** field, enter *61 Slotting pick*.</span></span>
1. <span data-ttu-id="fd516-261">En el campo **Número de secuencia**, acepte el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="fd516-261">In the **Sequence number** field, accept the default value.</span></span>

##### <a name="configure-the-location-directives-fasttab"></a><span data-ttu-id="fd516-262">Configurar la ficha desplegable Directivas de ubicación</span><span class="sxs-lookup"><span data-stu-id="fd516-262">Configure the Location directives FastTab</span></span>

1. <span data-ttu-id="fd516-263">En la ficha desplegable **Directivas generales**, establezca los valores siguientes.</span><span class="sxs-lookup"><span data-stu-id="fd516-263">On the **Location directives** FastTab, set the following values.</span></span> <span data-ttu-id="fd516-264">Acepte los valores predeterminados para el resto de campos.</span><span class="sxs-lookup"><span data-stu-id="fd516-264">Accept the default values for all other fields.</span></span>

    - <span data-ttu-id="fd516-265">**Tipo de trabajo**: _Recoger_</span><span class="sxs-lookup"><span data-stu-id="fd516-265">**Work type:** _Pick_</span></span>
    - <span data-ttu-id="fd516-266">**Sitio**: _6_</span><span class="sxs-lookup"><span data-stu-id="fd516-266">**Site:** _6_</span></span>
    - <span data-ttu-id="fd516-267">**Almacén**: _61_</span><span class="sxs-lookup"><span data-stu-id="fd516-267">**Warehouse:** _61_</span></span>
    - <span data-ttu-id="fd516-268">**Código de directiva:** _Slotting_</span><span class="sxs-lookup"><span data-stu-id="fd516-268">**Directive code:** _Slotting_</span></span>

1. <span data-ttu-id="fd516-269">Seleccione **Guardar** para tener disponible la ficha desplegable **Líneas**.</span><span class="sxs-lookup"><span data-stu-id="fd516-269">Select **Save** to make the **Lines** FastTab available.</span></span>

##### <a name="configure-the-lines-fasttab"></a><span data-ttu-id="fd516-270">Configurar la ficha desplegable Líneas</span><span class="sxs-lookup"><span data-stu-id="fd516-270">Configure the Lines FastTab</span></span>

1. <span data-ttu-id="fd516-271">En la ficha desplegable **Líneas**, seleccione **Nuevo** para crear una línea.</span><span class="sxs-lookup"><span data-stu-id="fd516-271">On the **Lines** FastTab, select **New** to create a line.</span></span>
1. <span data-ttu-id="fd516-272">En la nueva línea, establezca los siguientes valores.</span><span class="sxs-lookup"><span data-stu-id="fd516-272">On the new line, set the following values.</span></span>

    - <span data-ttu-id="fd516-273">**Cantidad inicial**: _0_</span><span class="sxs-lookup"><span data-stu-id="fd516-273">**From quantity:** _0_</span></span>
    - <span data-ttu-id="fd516-274">**Cantidad final**: _1000000_</span><span class="sxs-lookup"><span data-stu-id="fd516-274">**To quantity:** _1000000_</span></span>

1. <span data-ttu-id="fd516-275">Acepte los valores predeterminados del resto de campos.</span><span class="sxs-lookup"><span data-stu-id="fd516-275">Accept the default values for the remaining fields.</span></span>
1. <span data-ttu-id="fd516-276">Seleccione **Guardar** para tener disponible la ficha desplegable **Acciones directivas de ubicación**.</span><span class="sxs-lookup"><span data-stu-id="fd516-276">Select **Save** to make the **Location Directive Actions** FastTab available.</span></span>

##### <a name="configure-the-location-directive-actions-fasttab"></a><span data-ttu-id="fd516-277">Configurar la ficha desplegable Acciones de directiva de ubicación</span><span class="sxs-lookup"><span data-stu-id="fd516-277">Configure the Location Directive Actions FastTab</span></span>

1. <span data-ttu-id="fd516-278">En la ficha desplegable **Acciones de directiva de ubicación**, seleccione **Nuevo** para crear una línea.</span><span class="sxs-lookup"><span data-stu-id="fd516-278">On the **Location Directive Actions** FastTab, select **New** to create a line.</span></span>
1. <span data-ttu-id="fd516-279">En la nueva línea, establezca los siguientes valores.</span><span class="sxs-lookup"><span data-stu-id="fd516-279">On the new line, set the following values.</span></span> <span data-ttu-id="fd516-280">Acepte los valores predeterminados para el resto de campos.</span><span class="sxs-lookup"><span data-stu-id="fd516-280">Accept the default values for all other fields.</span></span>

    - <span data-ttu-id="fd516-281">**Número de secuencia:** acepte el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="fd516-281">**Sequence number:** Accept the default value.</span></span>
    - <span data-ttu-id="fd516-282">**Nombre:** _Masivo_</span><span class="sxs-lookup"><span data-stu-id="fd516-282">**Name:** _Bulk_</span></span>
    - <span data-ttu-id="fd516-283">**Estrategia:** _Ninguna_</span><span class="sxs-lookup"><span data-stu-id="fd516-283">**Strategy:** _None_</span></span>

1. <span data-ttu-id="fd516-284">Acepte los valores predeterminados del resto de campos.</span><span class="sxs-lookup"><span data-stu-id="fd516-284">Accept the default values for the remaining fields.</span></span>
1. <span data-ttu-id="fd516-285">Seleccione **Guardar** para que hacer que el botón **Editar consulta** esté disponible.</span><span class="sxs-lookup"><span data-stu-id="fd516-285">Select **Save** to make the **Edit query** button available.</span></span>

##### <a name="edit-the-query"></a><span data-ttu-id="fd516-286">Editar la consulta</span><span class="sxs-lookup"><span data-stu-id="fd516-286">Edit the query</span></span>

1. <span data-ttu-id="fd516-287">En la ficha desplegable **Acciones de directiva de ubicación**, seleccione **Editar consulta**.</span><span class="sxs-lookup"><span data-stu-id="fd516-287">On the **Location Directive Actions** FastTab, select **Edit query**.</span></span>
1. <span data-ttu-id="fd516-288">En la ficha **Rango**, seleccione **Nuevo** para agregar una línea a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="fd516-288">On the **Range** tab, select **Add** to add a line to the grid.</span></span>
1. <span data-ttu-id="fd516-289">En la nueva línea, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="fd516-289">On the new line, set the following values:</span></span>

    - <span data-ttu-id="fd516-290">**Tabla**: *Ubicaciones*</span><span class="sxs-lookup"><span data-stu-id="fd516-290">**Table:** *Locations*</span></span>
    - <span data-ttu-id="fd516-291">**Tabla derivada:** *Ubicaciones*</span><span class="sxs-lookup"><span data-stu-id="fd516-291">**Derived table:** *Locations*</span></span>
    - <span data-ttu-id="fd516-292">**Campo**: *ID de zona*</span><span class="sxs-lookup"><span data-stu-id="fd516-292">**Field:** *Zone ID*</span></span>
    - <span data-ttu-id="fd516-293">**Criterios:** *Masivo* (Seleccione el signo más doble \[**++**\] en el campo para expandir la lista y luego seleccione *Masivo*.)</span><span class="sxs-lookup"><span data-stu-id="fd516-293">**Criteria:** *Bulk* (Select the double plus sign \[**++**\] in the field to expand the list, and then select *Bulk*.)</span></span>

1. <span data-ttu-id="fd516-294">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="fd516-294">Select **OK**.</span></span>

## <a name="scenario"></a><span data-ttu-id="fd516-295">Situación</span><span class="sxs-lookup"><span data-stu-id="fd516-295">Scenario</span></span>

### <a name="set-up-the-scenario"></a><span data-ttu-id="fd516-296">Configuración el escenario</span><span class="sxs-lookup"><span data-stu-id="fd516-296">Set up the scenario</span></span>

<span data-ttu-id="fd516-297">Para este escenario, use los datos de muestra integrados y cree los registros que se describen en esta sección.</span><span class="sxs-lookup"><span data-stu-id="fd516-297">For this scenario, use the built-in sample data, and create the records that are described in this section.</span></span>

#### <a name="use-the-usmf-sample-data"></a><span data-ttu-id="fd516-298">Utilice los datos de muestra de USMF</span><span class="sxs-lookup"><span data-stu-id="fd516-298">Use the USMF sample data</span></span>

<span data-ttu-id="fd516-299">Para trabajar en este escenario mediante el uso de los registros y valores de muestra que se especifican aquí, debe estar en un sistema donde estén instalados los [datos de demostración](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) estándar.</span><span class="sxs-lookup"><span data-stu-id="fd516-299">To work through this scenario by using the sample records and values that are specified here, you must be on a system where the standard [demo data](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) is installed.</span></span> <span data-ttu-id="fd516-300">Además, también debe seleccionar la entidad legal **USMF** antes de empezar.</span><span class="sxs-lookup"><span data-stu-id="fd516-300">Additionally, you must select the **USMF** legal entity before you begin.</span></span>

#### <a name="create-demand"></a><span data-ttu-id="fd516-301">Crear demanda</span><span class="sxs-lookup"><span data-stu-id="fd516-301">Create demand</span></span>

<span data-ttu-id="fd516-302">Siga estos pasos para crear la demanda a la que aplicará el slotting.</span><span class="sxs-lookup"><span data-stu-id="fd516-302">Follow these steps to create the demand that you will apply slotting to.</span></span>

1. <span data-ttu-id="fd516-303">Vaya a **Ventas y marketing \> Pedidos de ventas \> Todos los pedidos de ventas**.</span><span class="sxs-lookup"><span data-stu-id="fd516-303">Go to **Sales and marketing \> Sales orders \> All sales order**.</span></span>
1. <span data-ttu-id="fd516-304">Seleccione **Nuevo** para crear un pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="fd516-304">Select **New** to create a sales order.</span></span>
1. <span data-ttu-id="fd516-305">En el cuadro de diálogo **Crear pedido de ventas**, en el campo **Cuenta de cliente**, seleccione _US-007_.</span><span class="sxs-lookup"><span data-stu-id="fd516-305">In the **Create sales order** dialog box, in the **Customer account** field, select _US-007_.</span></span>
1. <span data-ttu-id="fd516-306">En el campo **Almacén**, seleccione _61_.</span><span class="sxs-lookup"><span data-stu-id="fd516-306">In the **Warehouse** field, select _61_.</span></span>
1. <span data-ttu-id="fd516-307">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="fd516-307">Select **OK**.</span></span>
1. <span data-ttu-id="fd516-308">Se abre el nuevo pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="fd516-308">The new sales order is opened.</span></span> <span data-ttu-id="fd516-309">Incluye una línea vacía en la ficha desplegable **Líneas de pedido de ventas**.</span><span class="sxs-lookup"><span data-stu-id="fd516-309">It includes an empty line on the **Sales order lines** FastTab.</span></span> <span data-ttu-id="fd516-310">En esta línea, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="fd516-310">On this line, set the following values:</span></span>

    - <span data-ttu-id="fd516-311">**Artículo**: _L0101_</span><span class="sxs-lookup"><span data-stu-id="fd516-311">**Item:** _L0101_</span></span>
    - <span data-ttu-id="fd516-312">**Cantidad:** _20_</span><span class="sxs-lookup"><span data-stu-id="fd516-312">**Quantity:** _20_</span></span>

1. <span data-ttu-id="fd516-313">Seleccione **Agregar línea** para agregar una nueva línea y establecer los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="fd516-313">Select **Add line** to add a new line, and set the following values:</span></span>

    - <span data-ttu-id="fd516-314">**Artículo**: _T0100_</span><span class="sxs-lookup"><span data-stu-id="fd516-314">**Item:** _T0100_</span></span>
    - <span data-ttu-id="fd516-315">**Cantidad:** _8_</span><span class="sxs-lookup"><span data-stu-id="fd516-315">**Quantity:** _8_</span></span>

1. <span data-ttu-id="fd516-316">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="fd516-316">Select **Save**.</span></span>
1. <span data-ttu-id="fd516-317">Seleccione **Nuevo** para crear un segundo pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="fd516-317">Select **New** to create a second sales order.</span></span>
1. <span data-ttu-id="fd516-318">En el cuadro de diálogo **Crear pedido de ventas**, en el campo **Cuenta de cliente**, seleccione _US-008_.</span><span class="sxs-lookup"><span data-stu-id="fd516-318">In the **Create sales order** dialog box, in the **Customer account** field, select _US-008_.</span></span>
1. <span data-ttu-id="fd516-319">En el campo **Almacén**, seleccione _61_.</span><span class="sxs-lookup"><span data-stu-id="fd516-319">In the **Warehouse** field, select _61_.</span></span>
1. <span data-ttu-id="fd516-320">Se abre el nuevo pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="fd516-320">The new sales order is opened.</span></span> <span data-ttu-id="fd516-321">Incluye una línea vacía en la ficha desplegable **Líneas de pedido de ventas**.</span><span class="sxs-lookup"><span data-stu-id="fd516-321">It includes an empty line on the **Sales order lines** FastTab.</span></span> <span data-ttu-id="fd516-322">En esta línea, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="fd516-322">On this line, set the following values:</span></span>

    - <span data-ttu-id="fd516-323">**Artículo**: _T0100_</span><span class="sxs-lookup"><span data-stu-id="fd516-323">**Item:** _T0100_</span></span>
    - <span data-ttu-id="fd516-324">**Cantidad:** _1_</span><span class="sxs-lookup"><span data-stu-id="fd516-324">**Quantity:** _1_</span></span>

1. <span data-ttu-id="fd516-325">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="fd516-325">Select **Save**.</span></span>

### <a name="walk-through-a-typical-slotting-scenario"></a><span data-ttu-id="fd516-326">Recorrer un escenario típico de slotting</span><span class="sxs-lookup"><span data-stu-id="fd516-326">Walk through a typical slotting scenario</span></span>

<span data-ttu-id="fd516-327">Una vez que todos los elementos de los requisitos previos estén en su lugar, como se describe en la sección anterior, estará listo para probar la característica trabajando en cada ejercicio de esta sección.</span><span class="sxs-lookup"><span data-stu-id="fd516-327">After all the prerequisite elements are in place, as described in the previous section, you're ready to try out the feature by working through each exercise in this section.</span></span>

#### <a name="generate-demand"></a><span data-ttu-id="fd516-328">Generar demanda</span><span class="sxs-lookup"><span data-stu-id="fd516-328">Generate demand</span></span>

1. <span data-ttu-id="fd516-329">Vaya a **Gestión de almacén \> Configuración \> Reabastecimiento \> Plantillas de slotting** y seleccione la plantilla de slotting que creó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="fd516-329">Go to **Warehouse management \> Setup \> Replenishment \> Slotting templates**, and select the slotting template that you created earlier.</span></span>
1. <span data-ttu-id="fd516-330">En el panel de acciones, seleccione **Generar demanda**.</span><span class="sxs-lookup"><span data-stu-id="fd516-330">On the Action Pane, select **Generate demand**.</span></span> <span data-ttu-id="fd516-331">Este comando evalúa toda la demanda que hay en el sistema y que coincide con la consulta de plantilla de slotting.</span><span class="sxs-lookup"><span data-stu-id="fd516-331">This command evaluates all demand that is in the system, and that matches the slotting template query.</span></span> <span data-ttu-id="fd516-332">La demanda total en todos los pedidos se consolida en una línea por cantidad/unidad de medida.</span><span class="sxs-lookup"><span data-stu-id="fd516-332">The total demand across all orders is then consolidated onto one line per quantity/unit of measure.</span></span> <span data-ttu-id="fd516-333">Aparece un mensaje informativo cuando se completa el proceso.</span><span class="sxs-lookup"><span data-stu-id="fd516-333">An informational message appears when the process is completed.</span></span>

#### <a name="slotting-demand"></a><span data-ttu-id="fd516-334">Demanda de slotting</span><span class="sxs-lookup"><span data-stu-id="fd516-334">Slotting demand</span></span>

<span data-ttu-id="fd516-335">La *demanda de slotting* muestra los resultados de la generación de demanda, en función de la configuración de la plantilla de slotting.</span><span class="sxs-lookup"><span data-stu-id="fd516-335">The *slotting demand* shows the results of demand generation, based on the setup of the slotting template.</span></span>

- <span data-ttu-id="fd516-336">En el panel de acciones, seleccione **Demanda de slotting** para ver los resultados del comando **Generar demanda**.</span><span class="sxs-lookup"><span data-stu-id="fd516-336">On the Action Pane, select **Slotting demand** to view the results from the **Generate demand** command.</span></span> <span data-ttu-id="fd516-337">Las líneas en la demanda de slotting se pueden editar.</span><span class="sxs-lookup"><span data-stu-id="fd516-337">The lines in the slotting demand can be edited.</span></span> <span data-ttu-id="fd516-338">Puede eliminar una línea, agregar una nueva línea o editar los detalles de la línea.</span><span class="sxs-lookup"><span data-stu-id="fd516-338">You can delete a line, add a new line, or edit the line details.</span></span>

> [!NOTE]
> <span data-ttu-id="fd516-339">Puede editar la demanda manualmente o puede importarla desde un sistema externo mediante la administración de datos.</span><span class="sxs-lookup"><span data-stu-id="fd516-339">You can edit demand manually, or you can import it from an external system by using data management.</span></span> <span data-ttu-id="fd516-340">Cualquier artículo que esté en la demanda de slotting se utilizará en el siguiente paso, independientemente de su origen.</span><span class="sxs-lookup"><span data-stu-id="fd516-340">Whatever is in the slotting demand will be used in the next step, regardless of where it came from.</span></span>

#### <a name="locate-demand"></a><span data-ttu-id="fd516-341">Localizar demanda</span><span class="sxs-lookup"><span data-stu-id="fd516-341">Locate demand</span></span>

<span data-ttu-id="fd516-342">Una vez que se ha generado la demanda, debe usar el comando **Localizar demanda** para generar el *plan de slotting*.</span><span class="sxs-lookup"><span data-stu-id="fd516-342">After demand has been generated, you must use the **Locate demand** command to generate the *slotting plan*.</span></span>

- <span data-ttu-id="fd516-343">En el panel de acciones, seleccione **Localizar demanda**.</span><span class="sxs-lookup"><span data-stu-id="fd516-343">On the Action Pane, select **Locate demand**.</span></span> <span data-ttu-id="fd516-344">Se ejecuta el proceso de slotting.</span><span class="sxs-lookup"><span data-stu-id="fd516-344">The slotting process runs.</span></span> <span data-ttu-id="fd516-345">Aparece un mensaje informativo cuando se completa el proceso.</span><span class="sxs-lookup"><span data-stu-id="fd516-345">An informational message appears when the process is completed.</span></span>

#### <a name="slotting-plan"></a><span data-ttu-id="fd516-346">Asignar plan</span><span class="sxs-lookup"><span data-stu-id="fd516-346">Slotting plan</span></span>

<span data-ttu-id="fd516-347">El plan de slotting muestra la ubicación a la que se asignó cada artículo/cantidad, si se usó el desbordamiento, si se creó el trabajo de interrupción y la línea de plantilla que se usó.</span><span class="sxs-lookup"><span data-stu-id="fd516-347">The slotting plan shows the location that each item/quantity was assigned to, whether overflow was used, whether let-up work was created, and the template line that was used.</span></span> <span data-ttu-id="fd516-348">*Las demandas a las que no se pudo crear una posición se resaltan en rojo.*</span><span class="sxs-lookup"><span data-stu-id="fd516-348">*Any demand that could not be slotted is highlighted in red.*</span></span>

- <span data-ttu-id="fd516-349">En el panel de acciones, seleccione **Plan de slotting** para ver los resultados.</span><span class="sxs-lookup"><span data-stu-id="fd516-349">On the Action Pane, select **Slotting plan** to view the results.</span></span>

> [!NOTE]
> - <span data-ttu-id="fd516-350">Los procesos **Generar demanda**, **Localizar demanda** y **Ejecutar reposición** ahora se ejecutan en un espacio aislado.</span><span class="sxs-lookup"><span data-stu-id="fd516-350">The **Generate demand**, **Locate demand**, and **Run replenishment** processes are now run in a sandbox.</span></span> <span data-ttu-id="fd516-351">(Estos procesos están disponibles en el Panel de acciones, en la página **Plantillas de posicionamiento**).</span><span class="sxs-lookup"><span data-stu-id="fd516-351">(These processes are available from the Action Pane on the **Slotting templates** page.)</span></span>
> - <span data-ttu-id="fd516-352">Los procesos **Generar demanda**, **Localizar demanda** y **Ejecutar reposición** tienen un bloqueo para garantizar que no se puedan activar al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="fd516-352">The **Generate demand**, **Locate demand**, and **Run replenishment** processes have a lock to ensure that they can't be triggered at the same time.</span></span> <span data-ttu-id="fd516-353">De lo contrario, los datos que se utilizan podrían eliminarse.</span><span class="sxs-lookup"><span data-stu-id="fd516-353">Otherwise, the data that is used could be deleted.</span></span>
> - <span data-ttu-id="fd516-354">Los procesos **Generar demanda** y **Localizar demanda** muestran una advertencia si la ejecución no generó registros o si a los registros les falta información.</span><span class="sxs-lookup"><span data-stu-id="fd516-354">The **Generate demand** and **Locate demand** processes show a warning if the run didn't generate records, or if the records are missing information.</span></span>
> - <span data-ttu-id="fd516-355">Cuando selecciona **Plan de posicionamiento**, la página no tiene los botones **Nuevo**, **Editar** o **Eliminar** en el Panel de acciones, porque el origen de datos no se puede editar.</span><span class="sxs-lookup"><span data-stu-id="fd516-355">When you select **Slotting plan**, the page doesn't have **New**, **Edit**, or **Delete** buttons on the Action Pane, because the data source can't be edited.</span></span>
> - <span data-ttu-id="fd516-356">Cuando selecciona **Ejecutar reposición**, el sistema valida la plantilla de ranura seleccionada y procesa.</span><span class="sxs-lookup"><span data-stu-id="fd516-356">When you select **Run replenishment**, the system validates the selected slot template and processes.</span></span>

#### <a name="create-replenishment"></a><span data-ttu-id="fd516-357">Crear reabastecimiento</span><span class="sxs-lookup"><span data-stu-id="fd516-357">Create replenishment</span></span>

<span data-ttu-id="fd516-358">Una vez creado el plan de slotting, debe crear un *trabajo de reabastecimiento* basado en el plan.</span><span class="sxs-lookup"><span data-stu-id="fd516-358">After the slotting plan has been created, you must create *replenishment work*, based on the plan.</span></span>

- <span data-ttu-id="fd516-359">En el panel de acciones, seleccione **Ejecutar reabastecimiento**.</span><span class="sxs-lookup"><span data-stu-id="fd516-359">On the Action Pane, select **Run replenishment**.</span></span> <span data-ttu-id="fd516-360">Aparece un mensaje informativo cuando se completa el proceso.</span><span class="sxs-lookup"><span data-stu-id="fd516-360">An informational message appears when the process is completed.</span></span> <span data-ttu-id="fd516-361">Este mensaje indica el número de encabezados que se crearon para el id. de creación de trabajo.</span><span class="sxs-lookup"><span data-stu-id="fd516-361">This message indicates the number of headers that were created for the work build ID.</span></span>

<span data-ttu-id="fd516-362">Las directivas de ubicación que se utilizarán se identifican en función del código de directiva que se especifica en cada línea de plantilla.</span><span class="sxs-lookup"><span data-stu-id="fd516-362">Location directives that will be used are identified based on the directive code that is specified on each template line.</span></span>

## <a name="tips"></a><span data-ttu-id="fd516-363">Sugerencias</span><span class="sxs-lookup"><span data-stu-id="fd516-363">Tips</span></span>

### <a name="set-up-automatic-slotting"></a><span data-ttu-id="fd516-364">Configurar slotting automático</span><span class="sxs-lookup"><span data-stu-id="fd516-364">Set up automatic slotting</span></span>

<span data-ttu-id="fd516-365">Una vez que todos los elementos requeridos estén en su lugar, puede configurar el slotting para que se ejecute automáticamente siguiendo estos pasos.</span><span class="sxs-lookup"><span data-stu-id="fd516-365">After all the required elements are in place, you can set up slotting to run automatically by following these steps.</span></span>

1. <span data-ttu-id="fd516-366">Vaya a **Gestión de almacenes \> Reabastecimiento \> Ejecutar slotting**.</span><span class="sxs-lookup"><span data-stu-id="fd516-366">Go to **Warehouse management \> Replenishment \> Run slotting**.</span></span>
1. <span data-ttu-id="fd516-367">Especifique los pasos de slotting que se van a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="fd516-367">Specify the slotting steps to run.</span></span> <span data-ttu-id="fd516-368">Seleccione uno o varias de las siguientes pasos de slotting:</span><span class="sxs-lookup"><span data-stu-id="fd516-368">Select one or more of the following slotting steps:</span></span>

    - <span data-ttu-id="fd516-369">Generar demanda</span><span class="sxs-lookup"><span data-stu-id="fd516-369">Generate demand</span></span>
    - <span data-ttu-id="fd516-370">Localizar demanda</span><span class="sxs-lookup"><span data-stu-id="fd516-370">Locate demand</span></span>
    - <span data-ttu-id="fd516-371">Crear trabajo de reabastecimiento</span><span class="sxs-lookup"><span data-stu-id="fd516-371">Create replenishment work</span></span>

    > [!NOTE]
    > <span data-ttu-id="fd516-372">Los pasos de slotting son progresivos.</span><span class="sxs-lookup"><span data-stu-id="fd516-372">The slotting steps are progressive.</span></span> <span data-ttu-id="fd516-373">Si quiere seleccionar *Localizar demanda*, primero debe seleccionar *Generar demanda*.</span><span class="sxs-lookup"><span data-stu-id="fd516-373">If you want to select *Locate demand*, you must first select *Generate demand*.</span></span>

1. <span data-ttu-id="fd516-374">Especifique la plantilla de slotting que va a utilizar.</span><span class="sxs-lookup"><span data-stu-id="fd516-374">Specify the slotting template to use.</span></span>
1. <span data-ttu-id="fd516-375">Establezca la periodicidad para que se ejecute automáticamente, si lo desea.</span><span class="sxs-lookup"><span data-stu-id="fd516-375">Set the recurrence to run automatically, if you want.</span></span>

<span data-ttu-id="fd516-376">Para los ejercicios del escenario, **no** configure el slotting automático.</span><span class="sxs-lookup"><span data-stu-id="fd516-376">For the exercises in the scenario, do **not** set up automatic slotting.</span></span>
