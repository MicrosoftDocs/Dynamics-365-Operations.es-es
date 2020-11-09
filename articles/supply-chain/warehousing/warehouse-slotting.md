---
title: Slotting de almacén
description: En este tema se proporciona información acerca del slotting de almacén. El slotting de almacén le permite consolidar la demanda por artículo y unidad de medida de los pedidos que tienen un estado de Pedido, Reservado o Liberado. Ayuda a los directores de almacén a planificar de manera inteligente las ubicaciones de picking antes de liberar pedidos al almacén y crear trabajos de picking.
author: mirzaab
manager: tfehr
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSInventFixedLocation, WHSSlotDemandLocated, WHSSlotDemand, WHSSlotUOMTier, WHSSlotTemplate, WHSLocDirHint, WHSLocDirTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: ed9e6eae2ecc8de8d5eeef4699678e93dd74f193
ms.sourcegitcommit: a36a4f9915ae3eb36bf8220111cf1486387713d9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "4017423"
---
# <a name="warehouse-slotting"></a><span data-ttu-id="1f2d6-105">Slotting de almacén</span><span class="sxs-lookup"><span data-stu-id="1f2d6-105">Warehouse slotting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1f2d6-106">El slotting de almacén le permite consolidar la demanda por artículo y unidad de medida de los pedidos que tienen un estado de *Pedido* , *Reservado* o *Liberado*.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-106">Warehouse slotting lets you consolidate demand by item and unit of measure from orders that have a status of *Ordered* , *Reserved* , or *Released*.</span></span> <span data-ttu-id="1f2d6-107">La demanda generada se puede aplicar a las ubicaciones que se utilizarán para el picking, en función de la cantidad, la unidad, las dimensiones físicas, las ubicaciones fijas y más.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-107">Generated demand can then be applied to locations that will be used for picking, based on quantity, unit, physical dimensions, fixed locations, and more.</span></span> <span data-ttu-id="1f2d6-108">Una vez que se ha establecido el plan de slotting, se puede crear un trabajo de reabastecimiento para llevar la cantidad adecuada de inventario a cada ubicación.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-108">After the slotting plan has been established, replenishment work can be created to bring the appropriate amount of inventory to each location.</span></span>

<span data-ttu-id="1f2d6-109">Esta funcionalidad ayuda a los directores de almacén a planificar de manera inteligente las ubicaciones de picking antes de liberar pedidos al almacén y crear trabajos de picking.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-109">This functionality helps warehouse managers intelligently plan picking locations before they release orders to the warehouse and create picking work.</span></span>

## <a name="turn-on-the-warehouse-slotting-feature"></a><span data-ttu-id="1f2d6-110">Activar la característica de slotting de almacén</span><span class="sxs-lookup"><span data-stu-id="1f2d6-110">Turn on the warehouse slotting feature</span></span>

<span data-ttu-id="1f2d6-111">Antes de poder usar esta característica debe estar activada en su sistema.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-111">Before you can use this feature, it must be turned on in your system.</span></span> <span data-ttu-id="1f2d6-112">Los administradores pueden usar la configuración de [gestión de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de la función y activarla si es necesario.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-112">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="1f2d6-113">En el espacio de trabajo **Administración de funciones** , la función aparece de la siguiente forma:</span><span class="sxs-lookup"><span data-stu-id="1f2d6-113">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="1f2d6-114">**Módulo:** *Gestión de almacén*</span><span class="sxs-lookup"><span data-stu-id="1f2d6-114">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="1f2d6-115">**Nombre de característica:** *Característica de slotting de almacén*</span><span class="sxs-lookup"><span data-stu-id="1f2d6-115">**Feature name:** *Warehouse slotting feature*</span></span>

## <a name="set-up-warehouse-slotting"></a><span data-ttu-id="1f2d6-116">Configurar slotting de almacén</span><span class="sxs-lookup"><span data-stu-id="1f2d6-116">Set up warehouse slotting</span></span>

<span data-ttu-id="1f2d6-117">Antes de utilizar el slotting de almacén, debe configurar los siguiente elementos en su sistema.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-117">To use warehouse slotting, you must set up the following elements in your system.</span></span>

### <a name="create-unit-of-measure-tiers-for-slotting"></a><a name="unit-tiers"></a><span data-ttu-id="1f2d6-118">Crear niveles de unidad de medida para slotting</span><span class="sxs-lookup"><span data-stu-id="1f2d6-118">Create unit-of-measure tiers for slotting</span></span>

<span data-ttu-id="1f2d6-119">Los niveles de unidad de medida permiten agrupar varias unidades de medida a efectos de slotting.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-119">Unit-of-measure tiers enable multiple units of measure to be grouped together for the purposes of slotting.</span></span> <span data-ttu-id="1f2d6-120">Por ejemplo, si se seleccionan varios tamaños de cajas de la misma área de picking de cajas, se puede crear un nivel para todos los tamaños.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-120">For example, if multiple sizes of boxes are all picked from the same box picking area, one tier can be created for all the sizes.</span></span> <span data-ttu-id="1f2d6-121">**Se debe crear una línea para cada unidad de medida que debe formar parte del nivel.**</span><span class="sxs-lookup"><span data-stu-id="1f2d6-121">**A line must be created for each unit of measure that should be part of the tier.**</span></span>

1. <span data-ttu-id="1f2d6-122">Vaya a **Gestión de almacenes \> Configuración \> Reabastecimiento \> Niveles de unidad de medida de slotting**.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-122">Go to **Warehouse management \> Setup \> Replenishment \> Slotting unit of measure tiers**.</span></span>
1. <span data-ttu-id="1f2d6-123">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-123">Select **New**.</span></span>
1. <span data-ttu-id="1f2d6-124">Establezca los siguientes valores en el encabezado:</span><span class="sxs-lookup"><span data-stu-id="1f2d6-124">In the header, set the following values:</span></span>

    - <span data-ttu-id="1f2d6-125">**Nivel de unidad de medida:** *EaBoxPl*</span><span class="sxs-lookup"><span data-stu-id="1f2d6-125">**Unit of measure tier:** *EaBoxPl*</span></span>
    - <span data-ttu-id="1f2d6-126">**Descripción:** *cada pallet de cajas*</span><span class="sxs-lookup"><span data-stu-id="1f2d6-126">**Description:** *Each box pallet*</span></span>

1. <span data-ttu-id="1f2d6-127">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-127">Select **Save**.</span></span>
1. <span data-ttu-id="1f2d6-128">En la ficha desplegable **Unidades de medida** , seleccione **Nuevo** para agregar una línea a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-128">On the **Units of measure** FastTab, select **New** to add a line to the grid.</span></span>
1. <span data-ttu-id="1f2d6-129">En la nueva línea, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="1f2d6-129">On the new line, set the following values:</span></span>

    - <span data-ttu-id="1f2d6-130">**Unidad:** *caja*</span><span class="sxs-lookup"><span data-stu-id="1f2d6-130">**Unit:** *Box*</span></span>
    - <span data-ttu-id="1f2d6-131">**Descripción** : deje este campo en blanco.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-131">**Description:** Leave this field blank.</span></span> <span data-ttu-id="1f2d6-132">Se rellenará automáticamente cuando guarde los cambios.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-132">It will be filled in automatically when you save your changes.</span></span>
    - <span data-ttu-id="1f2d6-133">**Clase de unidad:** *cantidad*</span><span class="sxs-lookup"><span data-stu-id="1f2d6-133">**Unit class:** *Quantity*</span></span>

1. <span data-ttu-id="1f2d6-134">Seleccione **Nuevo** para agregar una segunda línea a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-134">Select **New** to add a second line to the grid.</span></span>
1. <span data-ttu-id="1f2d6-135">En la nueva línea, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="1f2d6-135">On the new line, set the following values:</span></span>

    - <span data-ttu-id="1f2d6-136">**Unidad** : *u*</span><span class="sxs-lookup"><span data-stu-id="1f2d6-136">**Unit:** *ea*</span></span>
    - <span data-ttu-id="1f2d6-137">**Descripción** : deje este campo en blanco.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-137">**Description:** Leave this field blank.</span></span> <span data-ttu-id="1f2d6-138">Se rellenará automáticamente cuando guarde los cambios.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-138">It will be filled in automatically when you save your changes.</span></span>
    - <span data-ttu-id="1f2d6-139">**Clase de unidad:** *cantidad*</span><span class="sxs-lookup"><span data-stu-id="1f2d6-139">**Unit class:** *Quantity*</span></span>

1. <span data-ttu-id="1f2d6-140">Seleccione **Nuevo** para agregar una tercera línea a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-140">Select **New** to add a third line to the grid.</span></span>
1. <span data-ttu-id="1f2d6-141">En la nueva línea, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="1f2d6-141">On the new line, set the following values:</span></span>

    - <span data-ttu-id="1f2d6-142">**Unidad:** *PL*</span><span class="sxs-lookup"><span data-stu-id="1f2d6-142">**Unit:** *PL*</span></span>
    - <span data-ttu-id="1f2d6-143">**Descripción** : deje este campo en blanco.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-143">**Description:** Leave this field blank.</span></span> <span data-ttu-id="1f2d6-144">Se rellenará automáticamente cuando guarde los cambios.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-144">It will be filled in automatically when you save your changes.</span></span>
    - <span data-ttu-id="1f2d6-145">**Clase de unidad:** *Cantidad*</span><span class="sxs-lookup"><span data-stu-id="1f2d6-145">**Unit class:** *Quantity*</span></span>

1. <span data-ttu-id="1f2d6-146">Seleccione **Guardar** para guardar el nivel.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-146">Select **Save** to save the tier.</span></span>

### <a name="create-a-directive-code-for-slotting"></a><span data-ttu-id="1f2d6-147">Crear un código de directiva para slotting</span><span class="sxs-lookup"><span data-stu-id="1f2d6-147">Create a directive code for slotting</span></span>

<span data-ttu-id="1f2d6-148">Debe seleccionar el código de directiva que debe asociarse a una plantilla.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-148">You must select the directive code that should be associated with a template.</span></span>

1. <span data-ttu-id="1f2d6-149">Vaya a **Gestión de almacenes \> Configurar \> Códigos de directivas**.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-149">Go to **Warehouse management \> Setup \> Directive codes**.</span></span>
1. <span data-ttu-id="1f2d6-150">En el panel de acciones, haga clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-150">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="1f2d6-151">En el campo **Código de la directiva** , introduzca *Slotting*.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-151">In the **Directive code** field, enter *Slotting*.</span></span>
1. <span data-ttu-id="1f2d6-152">En el campo **Descripción de la directiva** , introduzca *Slotting*.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-152">In the **Directive description** field, enter *Slotting*.</span></span>

### <a name="set-up-slotting-templates"></a><span data-ttu-id="1f2d6-153">Configurar plantillas de slotting</span><span class="sxs-lookup"><span data-stu-id="1f2d6-153">Set up slotting templates</span></span>

<span data-ttu-id="1f2d6-154">Cada plantilla de slotting controla cómo se asigna el inventario a las ubicaciones de un determinado almacén.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-154">Each slotting template controls how inventory is assigned to locations for a specific warehouse.</span></span> <span data-ttu-id="1f2d6-155">Cada plantilla debe incluir una línea para cada especificación de slotting.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-155">Each template must include a line for each slotting specification.</span></span> <span data-ttu-id="1f2d6-156">Use los procedimientos de esta sección para configurar plantillas de slotting.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-156">Use the procedures in this section to set up slotting templates.</span></span>

1. <span data-ttu-id="1f2d6-157">Vaya a **Administración de almacenes \> Configurar \> Reabastecimiento \> Plantillas de reabastecimiento**.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-157">Go to **Warehouse management \> Setup \> Replenishment \> Slotting templates**.</span></span>
1. <span data-ttu-id="1f2d6-158">Seleccione **Nuevo** para crear una página.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-158">Select **New** to create a template.</span></span>

<span data-ttu-id="1f2d6-159">A continuación, debe configurar el encabezado de la plantilla, las especificaciones de slotting y las directivas de ubicación, como se explica en las subsecciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-159">Next, you must set up the template header, slotting specifications, and location directives, as explained in the following subsections.</span></span>

#### <a name="set-up-a-slotting-template-header"></a><span data-ttu-id="1f2d6-160">Configurar un encabezado de plantilla de slotting</span><span class="sxs-lookup"><span data-stu-id="1f2d6-160">Set up a slotting template header</span></span>

1. <span data-ttu-id="1f2d6-161">En el encabezado de la plantilla, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="1f2d6-161">In the header for the template, set the following values:</span></span>

    - <span data-ttu-id="1f2d6-162">**Plantilla de slotting:** _61_</span><span class="sxs-lookup"><span data-stu-id="1f2d6-162">**Slotting template:** _61_</span></span>
    - <span data-ttu-id="1f2d6-163">**Descripción:** _61_</span><span class="sxs-lookup"><span data-stu-id="1f2d6-163">**Description:** _61_</span></span>
    - <span data-ttu-id="1f2d6-164">**Tipo de demanda:** *Pedido de ventas*</span><span class="sxs-lookup"><span data-stu-id="1f2d6-164">**Demand type:** *Sales order*</span></span>

        <span data-ttu-id="1f2d6-165">Actualmente, *Pedido de ventas* es el único tipo de demanda que se admite.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-165">Currently, *Sales order* is the only demand type that is supported.</span></span>

    - <span data-ttu-id="1f2d6-166">**Estrategia de demanda:** _Pedido_</span><span class="sxs-lookup"><span data-stu-id="1f2d6-166">**Demand strategy:** _Ordered_</span></span>

        <span data-ttu-id="1f2d6-167">Los siguientes valores están disponibles en este campo:</span><span class="sxs-lookup"><span data-stu-id="1f2d6-167">The following values are available in this field:</span></span>

        - <span data-ttu-id="1f2d6-168">**Pedido** : la cantidad pedida completa en el pedido de ventas debe considerarse demanda.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-168">**Ordered** – The full ordered quantity on the sales order should be considered demand.</span></span>
        - <span data-ttu-id="1f2d6-169">**Reservado** : solo las cantidades de la línea de pedido de ventas que se reservan (físicas y pedidas) deben considerarse demanda.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-169">**Reserved** – Only the sales order line quantities that are reserved (physical and ordered) should be considered demand.</span></span>

    - <span data-ttu-id="1f2d6-170">**Almacén** : _61_</span><span class="sxs-lookup"><span data-stu-id="1f2d6-170">**Warehouse:** _61_</span></span>
    - <span data-ttu-id="1f2d6-171">**Permitir demanda de oleadas para usar cantidades sin reservar:** _sí_</span><span class="sxs-lookup"><span data-stu-id="1f2d6-171">**Allow wave demand to use unreserved quantities:** _Yes_</span></span>

<span data-ttu-id="1f2d6-172">También puede especificar una consulta para reducir el alcance de la demanda que se evalúa.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-172">You can also specify a query to narrow the scope of the demand that is evaluated.</span></span>

#### <a name="set-up-slotting-specifications-for-each-template"></a><span data-ttu-id="1f2d6-173">Configurar especificaciones de slotting para cada plantilla</span><span class="sxs-lookup"><span data-stu-id="1f2d6-173">Set up slotting specifications for each template</span></span>

<span data-ttu-id="1f2d6-174">Para cada plantilla que cree, siga estos pasos para agregar una línea para cada especificación de slotting.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-174">For each template that you create, follow these steps to add a line for each slotting specification.</span></span>

1. <span data-ttu-id="1f2d6-175">En la ficha desplegable **Detalles de plantilla de slotting** , seleccione **Nuevo** para crear una línea de plantilla.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-175">On the **Slotting template details** FastTab, select **New** to create a template line.</span></span>
1. <span data-ttu-id="1f2d6-176">En la nueva línea, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="1f2d6-176">On the new line, set the following values:</span></span>

    - <span data-ttu-id="1f2d6-177">**Secuencia** : _1_</span><span class="sxs-lookup"><span data-stu-id="1f2d6-177">**Sequence:** _1_</span></span>
    - <span data-ttu-id="1f2d6-178">**Descripción:** _Ubicación fija_</span><span class="sxs-lookup"><span data-stu-id="1f2d6-178">**Description:** _Fixed location_</span></span>
    - <span data-ttu-id="1f2d6-179">**Cantidad mínima** : _1_</span><span class="sxs-lookup"><span data-stu-id="1f2d6-179">**Minimum quantity:** _1_</span></span>

        <span data-ttu-id="1f2d6-180">Este campo define la cantidad mínima de demanda que se requiere para la línea.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-180">This field defines the minimum quantity of demand that is required for the line.</span></span>

    - <span data-ttu-id="1f2d6-181">**Cantidad máxima:** _1000000_</span><span class="sxs-lookup"><span data-stu-id="1f2d6-181">**Maximum quantity:** _1000000_</span></span>

        <span data-ttu-id="1f2d6-182">Este campo define la cantidad máxima de demanda que es válida para la línea.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-182">This field defines the maximum quantity of demand that is valid for the line.</span></span>

    - <span data-ttu-id="1f2d6-183">**Unidad:** deje este campo en blanco.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-183">**Unit:** Leave this field blank.</span></span>

        <span data-ttu-id="1f2d6-184">Este campo define la unidad de medida a la que hacen referencia las cantidades mínima y máxima.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-184">This field defines the unit of measure that the minimum and maximum quantities refer to.</span></span>

    - <span data-ttu-id="1f2d6-185">**Nivel de unidad de medida:** _EaBoxPl_</span><span class="sxs-lookup"><span data-stu-id="1f2d6-185">**Unit of Measure Tier:** _EaBoxPl_</span></span>

        <span data-ttu-id="1f2d6-186">Este campo define las unidades de medida de demanda que son válidas para la línea.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-186">This field defines the units of measure of demand that are valid for the line.</span></span> <span data-ttu-id="1f2d6-187">(Para obtener más información, consulte la sección [Configurar niveles de unidad de medida para slotting](#unit-tiers) que se indica previamente en este tema.)</span><span class="sxs-lookup"><span data-stu-id="1f2d6-187">(For more information, see the [Set up unit-of-measure tiers for slotting](#unit-tiers) section earlier in this topic.)</span></span>

    - <span data-ttu-id="1f2d6-188">**Asignar criterios de posición:** _Considere la cantidad_</span><span class="sxs-lookup"><span data-stu-id="1f2d6-188">**Assign slot criteria:** _Consider qty_</span></span>

        <span data-ttu-id="1f2d6-189">Los siguientes valores están disponibles en este campo:</span><span class="sxs-lookup"><span data-stu-id="1f2d6-189">The following values are available in this field:</span></span>

        - <span data-ttu-id="1f2d6-190">**Asumir vacío** : este sistema debe asumir que todas las ubicaciones en el área de picking están vacías y no debe comprobar esas ubicaciones para el inventario.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-190">**Assume empty** – This system should assume that all locations in the picking area are empty and should not check those locations for inventory.</span></span>
        - <span data-ttu-id="1f2d6-191">**Considerar cantidad** : el sistema debe comprobar las ubicaciones en el área de picking para el inventario y no debe omitir las ubicaciones que estén vacías.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-191">**Consider qty** – The system should check the locations in the picking area for inventory and should skip any locations that aren't empty.</span></span>

    - <span data-ttu-id="1f2d6-192">**Código de directiva:** _Slotting_</span><span class="sxs-lookup"><span data-stu-id="1f2d6-192">**Directive code:** _Slotting_</span></span>

        <span data-ttu-id="1f2d6-193">Este campo define la directiva de ubicación que se utiliza para encontrar la ubicación de picking del trabajo de reabastecimiento.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-193">This field defines the location directive that is used to find the picking location of the replenishment work.</span></span>

    - <span data-ttu-id="1f2d6-194">**Ubicación de desbordamiento:** deje este campo en blanco.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-194">**Overflow location:** Leave this field blank.</span></span>

        <span data-ttu-id="1f2d6-195">Este campo define la ubicación en la que se coloca el inventario si no se puede encontrar una ubicación para la cantidad cuando se procesa la línea.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-195">This field defines the location that inventory that is put to if a location can't be found for the quantity when the line is processed.</span></span>

    - <span data-ttu-id="1f2d6-196">**Permitir interrupción:** _Sí_</span><span class="sxs-lookup"><span data-stu-id="1f2d6-196">**Allow let up:** _Yes_</span></span>

        <span data-ttu-id="1f2d6-197">Cuando esta opción se establece en *Sí* , si no se puede crear la posición de ninguna demanda, se creará un trabajo de movimiento para sacar el inventario de las ubicaciones donde hay inventario, pero donde no se creó la posición de nada.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-197">When this option is set to *Yes* , if any demand can't be slotted, movement work will be created to take inventory out of locations where there is inventory, but where nothing was slotted.</span></span> <span data-ttu-id="1f2d6-198">La plantilla se ejecuta de nuevo.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-198">The template is then run again.</span></span> <span data-ttu-id="1f2d6-199">Esta vez, ignora el inventario en las ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-199">This time, it ignores the inventory in the locations.</span></span> <span data-ttu-id="1f2d6-200">Esta funcionalidad funciona mejor cuando el campo **Asignar criterios de posición** se establece en _Considerar cantidad_.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-200">This functionality works best when the **Assign slot criteria** field is set to _Consider qty_.</span></span>

    - <span data-ttu-id="1f2d6-201">**Uso de ubicaciones fijas:** _Solo ubicaciones fijas para el producto_</span><span class="sxs-lookup"><span data-stu-id="1f2d6-201">**Fixed location usage:** _Only fixed locations for the product_</span></span>

        <span data-ttu-id="1f2d6-202">Los siguientes valores están disponibles en este campo:</span><span class="sxs-lookup"><span data-stu-id="1f2d6-202">The following values are available in this field:</span></span>

        - <span data-ttu-id="1f2d6-203">**Ubicaciones fijas y no fijas** : el sistema no debe limitarse a usar solo ubicaciones fijas.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-203">**Fixed and non-fixed locations** – The system should not be limited to using only fixed locations.</span></span>
        - <span data-ttu-id="1f2d6-204">**Solo ubicaciones fijas para el producto:** el sistema debe colocarse solo en ubicaciones que son ubicaciones fijas para el producto.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-204">**Only fixed locations for the product** – The system should slot only to locations that are fixed locations for the product.</span></span>
        - <span data-ttu-id="1f2d6-205">**Solo ubicaciones fijas para la variante del producto:** el sistema debe colocarse solo en ubicaciones que son ubicaciones fijas para la variante del producto.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-205">**Only fixed locations for the product variant** – The system should slot only to locations that are fixed locations for the product variant.</span></span>

1. <span data-ttu-id="1f2d6-206">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-206">Select **Save**.</span></span>
1. <span data-ttu-id="1f2d6-207">Seleccione **Nuevo** para crear una segunda línea de plantilla.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-207">Select **New** to create a second template line.</span></span>
1. <span data-ttu-id="1f2d6-208">En la nueva línea, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="1f2d6-208">On the new line, set the following values:</span></span>

    - <span data-ttu-id="1f2d6-209">**Secuencia** : _2_</span><span class="sxs-lookup"><span data-stu-id="1f2d6-209">**Sequence:** _2_</span></span>
    - <span data-ttu-id="1f2d6-210">**Descripción:** _Otro_</span><span class="sxs-lookup"><span data-stu-id="1f2d6-210">**Description:** _Other_</span></span>
    - <span data-ttu-id="1f2d6-211">**Cantidad mínima:** _1_</span><span class="sxs-lookup"><span data-stu-id="1f2d6-211">**Minimum Qty:** _1_</span></span>
    - <span data-ttu-id="1f2d6-212">**Cantidad máxima:** _1000000_</span><span class="sxs-lookup"><span data-stu-id="1f2d6-212">**Maximum Qty:** _1000000_</span></span>
    - <span data-ttu-id="1f2d6-213">**Unidad:** deje este campo en blanco.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-213">**Unit:** Leave this field blank.</span></span>
    - <span data-ttu-id="1f2d6-214">**Nivel de unidad de medida:** _EaBoxPl_</span><span class="sxs-lookup"><span data-stu-id="1f2d6-214">**Unit of measure tier:** _EaBoxPl_</span></span>
    - <span data-ttu-id="1f2d6-215">**Asignar criterios de posición:** _Considere la cantidad_</span><span class="sxs-lookup"><span data-stu-id="1f2d6-215">**Assign slot criteria:** _Consider qty_</span></span>
    - <span data-ttu-id="1f2d6-216">**Código de directiva:** _Slotting_</span><span class="sxs-lookup"><span data-stu-id="1f2d6-216">**Directive code:** _Slotting_</span></span>
    - <span data-ttu-id="1f2d6-217">**Ubicación de desbordamiento:** deje este campo en blanco.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-217">**Overflow location:** Leave this field blank.</span></span>
    - <span data-ttu-id="1f2d6-218">**Permitir interrupción:** _Sí_</span><span class="sxs-lookup"><span data-stu-id="1f2d6-218">**Allow let up:** _Yes_</span></span>
    - <span data-ttu-id="1f2d6-219">**Usar ubicaciones fijas:** _Ubicaciones fijas y no fijas_</span><span class="sxs-lookup"><span data-stu-id="1f2d6-219">**Use fixed locations:** _Fixed and non-fixed locations_</span></span>

    <span data-ttu-id="1f2d6-220">En la consulta de la segunda línea, ahora especificará los criterios que se utilizan para determinar a qué ubicaciones se puede crear la posición de la demanda para esa línea.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-220">In the query for the second line, you will now specify the criteria that are used to determine what locations the demand for that line can be slotted to.</span></span>

1. <span data-ttu-id="1f2d6-221">Seleccione la línea donde el campo **Secuencia** se establece en *2*.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-221">Select the line where the **Sequence** field is set to *2*.</span></span>
1. <span data-ttu-id="1f2d6-222">Seleccione **Editar consulta**.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-222">Select **Edit query**.</span></span>
1. <span data-ttu-id="1f2d6-223">En la ficha **Rango** , seleccione **Nuevo** para agregar una línea a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-223">On the **Range** tab, select **Add** to add a line to the grid.</span></span>
1. <span data-ttu-id="1f2d6-224">En la nueva línea, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="1f2d6-224">On the new line, set the following values:</span></span>

    - <span data-ttu-id="1f2d6-225">**Tabla** : *Ubicaciones*</span><span class="sxs-lookup"><span data-stu-id="1f2d6-225">**Table:** *Locations*</span></span>
    - <span data-ttu-id="1f2d6-226">**Tabla derivada:** *Ubicaciones*</span><span class="sxs-lookup"><span data-stu-id="1f2d6-226">**Derived table:** *Locations*</span></span>
    - <span data-ttu-id="1f2d6-227">**Campo** : *ID de perfil de ubicación*</span><span class="sxs-lookup"><span data-stu-id="1f2d6-227">**Field:** *Location profile ID*</span></span>
    - <span data-ttu-id="1f2d6-228">**Criterios:** *Pick-06* (Seleccione el signo más doble \[**++**\] en el campo para expandir la lista y luego seleccione *Pick-06* - *Sitio de picking 6*.)</span><span class="sxs-lookup"><span data-stu-id="1f2d6-228">**Criteria:** *Pick-06* (Select the double plus sign \[**++**\] in the field to expand the list, and then select *Pick-06* - *Picking Site 6*.)</span></span>

1. <span data-ttu-id="1f2d6-229">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-229">Select **OK**.</span></span>

#### <a name="set-up-location-directives"></a><span data-ttu-id="1f2d6-230">Configurar directivas de ubicación</span><span class="sxs-lookup"><span data-stu-id="1f2d6-230">Set up location directives</span></span>

<span data-ttu-id="1f2d6-231">Se debe configurar al menos una directiva de ubicación para admitir selecciones de slotting.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-231">At least one location directive must be set up to support slotting picks.</span></span> <span data-ttu-id="1f2d6-232">Use los procedimientos de esta sección para configurar una nueva *directiva de ubicación de reabastecimiento* para selecciones de slotting.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-232">Use the procedures in this section to set up a new *replenishment location directive* for slotting picks.</span></span>

1. <span data-ttu-id="1f2d6-233">Vaya a **Gestión de almacenes \> Configurar \> Directivas de ubicación**.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-233">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="1f2d6-234">En el panel izquierdo, en el campo **Tipo de orden de trabajo** , seleccione *Reabastecimiento*.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-234">In the left pane, in the **Work order type** field, select *Replenishment*.</span></span>
1. <span data-ttu-id="1f2d6-235">En el panel de acciones, haga clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-235">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="1f2d6-236">En el encabezado de la nueva directiva de ubicación, en el campo **Nombre** , introduzca *61 Selección de slotting*.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-236">In the header for the new location directive, in the **Name** field, enter *61 Slotting pick*.</span></span>

##### <a name="configure-the-location-directives-fasttab"></a><span data-ttu-id="1f2d6-237">Configurar la ficha desplegable Directivas de ubicación</span><span class="sxs-lookup"><span data-stu-id="1f2d6-237">Configure the Location directives FastTab</span></span>

1. <span data-ttu-id="1f2d6-238">En la ficha desplegable **Directivas generales** , establezca los valores siguientes.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-238">On the **Location directives** FastTab, set the following values.</span></span> <span data-ttu-id="1f2d6-239">Acepte los valores predeterminados para el resto de campos.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-239">Accept the default values for all other fields.</span></span>

    - <span data-ttu-id="1f2d6-240">**Tipo de trabajo** : _Recoger_</span><span class="sxs-lookup"><span data-stu-id="1f2d6-240">**Work type:** _Pick_</span></span>
    - <span data-ttu-id="1f2d6-241">**Sitio** : _6_</span><span class="sxs-lookup"><span data-stu-id="1f2d6-241">**Site:** _6_</span></span>
    - <span data-ttu-id="1f2d6-242">**Almacén** : _61_</span><span class="sxs-lookup"><span data-stu-id="1f2d6-242">**Warehouse:** _61_</span></span>
    - <span data-ttu-id="1f2d6-243">**Código de directiva:** _Slotting_</span><span class="sxs-lookup"><span data-stu-id="1f2d6-243">**Directive code:** _Slotting_</span></span>

1. <span data-ttu-id="1f2d6-244">Seleccione **Guardar** para tener disponible la ficha desplegable **Líneas**.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-244">Select **Save** to make the **Lines** FastTab available.</span></span>

##### <a name="configure-the-lines-fasttab"></a><span data-ttu-id="1f2d6-245">Configurar la ficha desplegable Líneas</span><span class="sxs-lookup"><span data-stu-id="1f2d6-245">Configure the Lines FastTab</span></span>

1. <span data-ttu-id="1f2d6-246">En la ficha desplegable **Líneas** , seleccione **Nuevo** para crear una línea.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-246">On the **Lines** FastTab, select **New** to create a line.</span></span>
1. <span data-ttu-id="1f2d6-247">En la nueva línea, establezca los siguientes valores.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-247">On the new line, set the following values.</span></span> <span data-ttu-id="1f2d6-248">Acepte los valores predeterminados para el resto de campos.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-248">Accept the default values for all other fields.</span></span>

    - <span data-ttu-id="1f2d6-249">**Cantidad inicial** : _0_</span><span class="sxs-lookup"><span data-stu-id="1f2d6-249">**From quantity:** _0_</span></span>
    - <span data-ttu-id="1f2d6-250">**Cantidad final** : _1000000_</span><span class="sxs-lookup"><span data-stu-id="1f2d6-250">**To quantity:** _1000000_</span></span>

1. <span data-ttu-id="1f2d6-251">Seleccione **Guardar** para tener disponible la ficha desplegable **Acciones directivas de ubicación**.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-251">Select **Save** to make the **Location Directive Actions** FastTab available.</span></span>

##### <a name="configure-the-location-directive-actions-fasttab"></a><span data-ttu-id="1f2d6-252">Configurar la ficha desplegable Acciones de directiva de ubicación</span><span class="sxs-lookup"><span data-stu-id="1f2d6-252">Configure the Location Directive Actions FastTab</span></span>

1. <span data-ttu-id="1f2d6-253">En la ficha desplegable **Acciones de directiva de ubicación** , seleccione **Nuevo** para crear una línea.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-253">On the **Location Directive Actions** FastTab, select **New** to create a line.</span></span>
1. <span data-ttu-id="1f2d6-254">En la nueva línea, establezca los siguientes valores.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-254">On the new line, set the following values.</span></span> <span data-ttu-id="1f2d6-255">Acepte los valores predeterminados para el resto de campos.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-255">Accept the default values for all other fields.</span></span>

    - <span data-ttu-id="1f2d6-256">**Nombre:** _Masivo_</span><span class="sxs-lookup"><span data-stu-id="1f2d6-256">**Name:** _Bulk_</span></span>
    - <span data-ttu-id="1f2d6-257">**Estrategia:** _Ninguna_</span><span class="sxs-lookup"><span data-stu-id="1f2d6-257">**Strategy:** _None_</span></span>

1. <span data-ttu-id="1f2d6-258">Seleccione **Guardar** para que hacer que el botón **Editar consulta** esté disponible.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-258">Select **Save** to make the **Edit query** button available.</span></span>

##### <a name="edit-the-query"></a><span data-ttu-id="1f2d6-259">Editar la consulta</span><span class="sxs-lookup"><span data-stu-id="1f2d6-259">Edit the query</span></span>

1. <span data-ttu-id="1f2d6-260">En la ficha desplegable **Acciones de directiva de ubicación** , seleccione **Editar consulta**.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-260">On the **Location Directive Actions** FastTab, select **Edit query**.</span></span>
1. <span data-ttu-id="1f2d6-261">En la ficha **Rango** , seleccione **Nuevo** para agregar una línea a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-261">On the **Range** tab, select **Add** to add a line to the grid.</span></span>
1. <span data-ttu-id="1f2d6-262">En la nueva línea, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="1f2d6-262">On the new line, set the following values:</span></span>

    - <span data-ttu-id="1f2d6-263">**Tabla** : *Ubicaciones*</span><span class="sxs-lookup"><span data-stu-id="1f2d6-263">**Table:** *Locations*</span></span>
    - <span data-ttu-id="1f2d6-264">**Tabla derivada:** *Ubicaciones*</span><span class="sxs-lookup"><span data-stu-id="1f2d6-264">**Derived table:** *Locations*</span></span>
    - <span data-ttu-id="1f2d6-265">**Campo** : *ID de zona*</span><span class="sxs-lookup"><span data-stu-id="1f2d6-265">**Field:** *Zone ID*</span></span>
    - <span data-ttu-id="1f2d6-266">**Criterios:** *Masivo* (Seleccione el signo más doble \[**++**\] en el campo para expandir la lista y luego seleccione *Masivo*.)</span><span class="sxs-lookup"><span data-stu-id="1f2d6-266">**Criteria:** *Bulk* (Select the double plus sign \[**++**\] in the field to expand the list, and then select *Bulk*.)</span></span>

1. <span data-ttu-id="1f2d6-267">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-267">Select **OK**.</span></span>

## <a name="scenario"></a><span data-ttu-id="1f2d6-268">Situación</span><span class="sxs-lookup"><span data-stu-id="1f2d6-268">Scenario</span></span>

### <a name="set-up-the-scenario"></a><span data-ttu-id="1f2d6-269">Configuración el escenario</span><span class="sxs-lookup"><span data-stu-id="1f2d6-269">Set up the scenario</span></span>

<span data-ttu-id="1f2d6-270">Para este escenario, use los datos de muestra integrados y cree los registros que se describen en esta sección.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-270">For this scenario, use the built-in sample data, and create the records that are described in this section.</span></span>

#### <a name="use-the-usmf-sample-data"></a><span data-ttu-id="1f2d6-271">Utilice los datos de muestra de USMF</span><span class="sxs-lookup"><span data-stu-id="1f2d6-271">Use the USMF sample data</span></span>

<span data-ttu-id="1f2d6-272">Para trabajar en este escenario mediante el uso de los registros y valores de muestra que se especifican aquí, debe estar en un sistema donde estén instalados los [datos de demostración](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) estándar.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-272">To work through this scenario by using the sample records and values that are specified here, you must be on a system where the standard [demo data](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) is installed.</span></span> <span data-ttu-id="1f2d6-273">Además, también debe seleccionar la entidad legal **USMF** antes de empezar.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-273">Additionally, you must select the **USMF** legal entity before you begin.</span></span>

#### <a name="create-demand"></a><span data-ttu-id="1f2d6-274">Crear demanda</span><span class="sxs-lookup"><span data-stu-id="1f2d6-274">Create demand</span></span>

<span data-ttu-id="1f2d6-275">Siga estos pasos para crear la demanda a la que aplicará el slotting.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-275">Follow these steps to create the demand that you will apply slotting to.</span></span>

1. <span data-ttu-id="1f2d6-276">Vaya a **Ventas y marketing \> Pedidos de ventas \> Todos los pedidos de ventas**.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-276">Go to **Sales and marketing \> Sales orders \> All sales order**.</span></span>
1. <span data-ttu-id="1f2d6-277">Seleccione **Nuevo** para crear un pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-277">Select **New** to create a sales order.</span></span>
1. <span data-ttu-id="1f2d6-278">En el cuadro de diálogo **Crear pedido de ventas** , en el campo **Cuenta de cliente** , seleccione _US-007_.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-278">In the **Create sales order** dialog box, in the **Customer account** field, select _US-007_.</span></span>
1. <span data-ttu-id="1f2d6-279">En el campo **Almacén** , seleccione _61_.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-279">In the **Warehouse** field, select _61_.</span></span>
1. <span data-ttu-id="1f2d6-280">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-280">Select **OK**.</span></span>
1. <span data-ttu-id="1f2d6-281">Se abre el nuevo pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-281">The new sales order is opened.</span></span> <span data-ttu-id="1f2d6-282">Incluye una línea vacía en la ficha desplegable **Líneas de pedido de ventas**.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-282">It includes an empty line on the **Sales order lines** FastTab.</span></span> <span data-ttu-id="1f2d6-283">En esta línea, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="1f2d6-283">On this line, set the following values:</span></span>

    - <span data-ttu-id="1f2d6-284">**Artículo** : _L0101_</span><span class="sxs-lookup"><span data-stu-id="1f2d6-284">**Item:** _L0101_</span></span>
    - <span data-ttu-id="1f2d6-285">**Cantidad:** _20_</span><span class="sxs-lookup"><span data-stu-id="1f2d6-285">**Quantity:** _20_</span></span>

1. <span data-ttu-id="1f2d6-286">Seleccione **Agregar línea** para agregar una nueva línea y establecer los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="1f2d6-286">Select **Add line** to add a new line, and set the following values:</span></span>

    - <span data-ttu-id="1f2d6-287">**Artículo** : _T0100_</span><span class="sxs-lookup"><span data-stu-id="1f2d6-287">**Item:** _T0100_</span></span>
    - <span data-ttu-id="1f2d6-288">**Cantidad:** _8_</span><span class="sxs-lookup"><span data-stu-id="1f2d6-288">**Quantity:** _8_</span></span>

1. <span data-ttu-id="1f2d6-289">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-289">Select **Save**.</span></span>
1. <span data-ttu-id="1f2d6-290">Seleccione **Nuevo** para crear un segundo pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-290">Select **New** to create a second sales order.</span></span>
1. <span data-ttu-id="1f2d6-291">En el cuadro de diálogo **Crear pedido de ventas** , en el campo **Cuenta de cliente** , seleccione _US-008_.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-291">In the **Create sales order** dialog box, in the **Customer account** field, select _US-008_.</span></span>
1. <span data-ttu-id="1f2d6-292">En el campo **Almacén** , seleccione _61_.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-292">In the **Warehouse** field, select _61_.</span></span>
1. <span data-ttu-id="1f2d6-293">Se abre el nuevo pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-293">The new sales order is opened.</span></span> <span data-ttu-id="1f2d6-294">Incluye una línea vacía en la ficha desplegable **Líneas de pedido de ventas**.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-294">It includes an empty line on the **Sales order lines** FastTab.</span></span> <span data-ttu-id="1f2d6-295">En esta línea, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="1f2d6-295">On this line, set the following values:</span></span>

    - <span data-ttu-id="1f2d6-296">**Artículo** : _T0100_</span><span class="sxs-lookup"><span data-stu-id="1f2d6-296">**Item:** _T0100_</span></span>
    - <span data-ttu-id="1f2d6-297">**Cantidad:** _1_</span><span class="sxs-lookup"><span data-stu-id="1f2d6-297">**Quantity:** _1_</span></span>

1. <span data-ttu-id="1f2d6-298">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-298">Select **Save**.</span></span>

### <a name="walk-through-a-typical-slotting-scenario"></a><span data-ttu-id="1f2d6-299">Recorrer un escenario típico de slotting</span><span class="sxs-lookup"><span data-stu-id="1f2d6-299">Walk through a typical slotting scenario</span></span>

<span data-ttu-id="1f2d6-300">Una vez que todos los elementos de los requisitos previos estén en su lugar, como se describe en la sección anterior, estará listo para probar la característica trabajando en cada ejercicio de esta sección.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-300">After all the prerequisite elements are in place, as described in the previous section, you're ready to try out the feature by working through each exercise in this section.</span></span>

#### <a name="generate-demand"></a><span data-ttu-id="1f2d6-301">Generar demanda</span><span class="sxs-lookup"><span data-stu-id="1f2d6-301">Generate demand</span></span>

1. <span data-ttu-id="1f2d6-302">Vaya a **Gestión de almacén \> Configuración \> Reabastecimiento \> Plantillas de slotting** y seleccione la plantilla de slotting que creó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-302">Go to **Warehouse management \> Setup \> Replenishment \> Slotting templates** , and select the slotting template that you created earlier.</span></span>
1. <span data-ttu-id="1f2d6-303">En el panel de acciones, seleccione **Generar demanda**.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-303">On the Action Pane, select **Generate demand**.</span></span> <span data-ttu-id="1f2d6-304">Este comando evalúa toda la demanda que hay en el sistema y que coincide con la consulta de plantilla de slotting.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-304">This command evaluates all demand that is in the system, and that matches the slotting template query.</span></span> <span data-ttu-id="1f2d6-305">La demanda total en todos los pedidos se consolida en una línea por cantidad/unidad de medida.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-305">The total demand across all orders is then consolidated onto one line per quantity/unit of measure.</span></span> <span data-ttu-id="1f2d6-306">Aparece un mensaje informativo cuando se completa el proceso.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-306">An informational message appears when the process is completed.</span></span>

#### <a name="slotting-demand"></a><span data-ttu-id="1f2d6-307">Demanda de slotting</span><span class="sxs-lookup"><span data-stu-id="1f2d6-307">Slotting demand</span></span>

<span data-ttu-id="1f2d6-308">La *demanda de slotting* muestra los resultados de la generación de demanda, en función de la configuración de la plantilla de slotting.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-308">The *slotting demand* shows the results of demand generation, based on the setup of the slotting template.</span></span>

- <span data-ttu-id="1f2d6-309">En el panel de acciones, seleccione **Demanda de slotting** para ver los resultados del comando **Generar demanda**.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-309">On the Action Pane, select **Slotting demand** to view the results from the **Generate demand** command.</span></span> <span data-ttu-id="1f2d6-310">Las líneas en la demanda de slotting se pueden editar.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-310">The lines in the slotting demand can be edited.</span></span> <span data-ttu-id="1f2d6-311">Puede eliminar una línea, agregar una nueva línea o editar los detalles de la línea.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-311">You can delete a line, add a new line, or edit the line details.</span></span>

> [!NOTE]
> <span data-ttu-id="1f2d6-312">Puede editar la demanda manualmente o puede importarla desde un sistema externo mediante la administración de datos.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-312">You can edit demand manually, or you can import it from an external system by using data management.</span></span> <span data-ttu-id="1f2d6-313">Cualquier artículo que esté en la demanda de slotting se utilizará en el siguiente paso, independientemente de su origen.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-313">Whatever is in the slotting demand will be used in the next step, regardless of where it came from.</span></span>

#### <a name="locate-demand"></a><span data-ttu-id="1f2d6-314">Localizar demanda</span><span class="sxs-lookup"><span data-stu-id="1f2d6-314">Locate demand</span></span>

<span data-ttu-id="1f2d6-315">Una vez que se ha generado la demanda, debe usar el comando **Localizar demanda** para generar el *plan de slotting*.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-315">After demand has been generated, you must use the **Locate demand** command to generate the *slotting plan*.</span></span>

- <span data-ttu-id="1f2d6-316">En el panel de acciones, seleccione **Localizar demanda**.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-316">On the Action Pane, select **Locate demand**.</span></span> <span data-ttu-id="1f2d6-317">Se ejecuta el proceso de slotting.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-317">The slotting process runs.</span></span> <span data-ttu-id="1f2d6-318">Aparece un mensaje informativo cuando se completa el proceso.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-318">An informational message appears when the process is completed.</span></span>

#### <a name="slotting-plan"></a><span data-ttu-id="1f2d6-319">Asignar plan</span><span class="sxs-lookup"><span data-stu-id="1f2d6-319">Slotting plan</span></span>

<span data-ttu-id="1f2d6-320">El plan de slotting muestra la ubicación a la que se asignó cada artículo/cantidad, si se usó el desbordamiento, si se creó el trabajo de interrupción y la línea de plantilla que se usó.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-320">The slotting plan shows the location that each item/quantity was assigned to, whether overflow was used, whether let-up work was created, and the template line that was used.</span></span> <span data-ttu-id="1f2d6-321">**Las demandas a las que no se pudo crear una posición se resaltan en rojo.**</span><span class="sxs-lookup"><span data-stu-id="1f2d6-321">**Any demand that could not be slotted is highlighted in red.**</span></span>

- <span data-ttu-id="1f2d6-322">En el panel de acciones, seleccione **Plan de slotting** para ver los resultados.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-322">On the Action Pane, select **Slotting plan** to view the results.</span></span>

#### <a name="create-replenishment"></a><span data-ttu-id="1f2d6-323">Crear reabastecimiento</span><span class="sxs-lookup"><span data-stu-id="1f2d6-323">Create replenishment</span></span>

<span data-ttu-id="1f2d6-324">Una vez creado el plan de slotting, debe crear un *trabajo de reabastecimiento* basado en el plan.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-324">After the slotting plan has been created, you must create *replenishment work* , based on the plan.</span></span>

- <span data-ttu-id="1f2d6-325">En el panel de acciones, seleccione **Ejecutar reabastecimiento**.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-325">On the Action Pane, select **Run replenishment**.</span></span> <span data-ttu-id="1f2d6-326">Aparece un mensaje informativo cuando se completa el proceso.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-326">An informational message appears when the process is completed.</span></span> <span data-ttu-id="1f2d6-327">Este mensaje indica el número de encabezados que se crearon para el id. de creación de trabajo.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-327">This message indicates the number of headers that were created for the work build ID.</span></span>

<span data-ttu-id="1f2d6-328">Las directivas de ubicación que se utilizarán se identifican en función del código de directiva que se especifica en cada línea de plantilla.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-328">Location directives that will be used are identified based on the directive code that is specified on each template line.</span></span>

## <a name="tips"></a><span data-ttu-id="1f2d6-329">Sugerencias</span><span class="sxs-lookup"><span data-stu-id="1f2d6-329">Tips</span></span>

### <a name="set-up-automatic-slotting"></a><span data-ttu-id="1f2d6-330">Configurar slotting automático</span><span class="sxs-lookup"><span data-stu-id="1f2d6-330">Set up automatic slotting</span></span>

<span data-ttu-id="1f2d6-331">Una vez que todos los elementos requeridos estén en su lugar, puede configurar el slotting para que se ejecute automáticamente siguiendo estos pasos.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-331">After all the required elements are in place, you can set up slotting to run automatically by following these steps.</span></span>

1. <span data-ttu-id="1f2d6-332">Vaya a **Gestión de almacenes \> Reabastecimiento \> Ejecutar slotting**.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-332">Go to **Warehouse management \> Replenishment \> Run slotting**.</span></span>
1. <span data-ttu-id="1f2d6-333">Especifique los pasos de slotting que se van a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-333">Specify the slotting steps to run.</span></span> <span data-ttu-id="1f2d6-334">Seleccione uno o varias de las siguientes pasos de slotting:</span><span class="sxs-lookup"><span data-stu-id="1f2d6-334">Select one or more of the following slotting steps:</span></span>

    - <span data-ttu-id="1f2d6-335">Generar demanda</span><span class="sxs-lookup"><span data-stu-id="1f2d6-335">Generate demand</span></span>
    - <span data-ttu-id="1f2d6-336">Localizar demanda</span><span class="sxs-lookup"><span data-stu-id="1f2d6-336">Locate demand</span></span>
    - <span data-ttu-id="1f2d6-337">Crear trabajo de reabastecimiento</span><span class="sxs-lookup"><span data-stu-id="1f2d6-337">Create replenishment work</span></span>

    > [!NOTE]
    > <span data-ttu-id="1f2d6-338">Los pasos de slotting son progresivos.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-338">The slotting steps are progressive.</span></span> <span data-ttu-id="1f2d6-339">Si quiere seleccionar *Localizar demanda* , primero debe seleccionar *Generar demanda*.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-339">If you want to select *Locate demand* , you must first select *Generate demand*.</span></span>

1. <span data-ttu-id="1f2d6-340">Especifique la plantilla de slotting que va a utilizar.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-340">Specify the slotting template to use.</span></span>
1. <span data-ttu-id="1f2d6-341">Establezca la periodicidad para que se ejecute automáticamente, si lo desea.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-341">Set the recurrence to run automatically, if you want.</span></span>

<span data-ttu-id="1f2d6-342">Para los ejercicios del escenario, **no** configure el slotting automático.</span><span class="sxs-lookup"><span data-stu-id="1f2d6-342">For the exercises in the scenario, do **not** set up automatic slotting.</span></span>
