---
title: Posición completa del clúster
description: Este tema proporciona información acerca de la característica Posición completa de clústeres. Esta característica ofrece una alternativa a la aplicación más estricta de las reglas de las pausas laborales cuando se utiliza el picking en clúster, ya que permite un mayor margen de error en las restricciones volumétricas de los contenedores o bolsas.
author: Mirzaab
manager: tfehr
ms.date: 08/25/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSClusterProfile
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: b6a7cad070377de58d21a8eb91ee3e1ffaf1c660
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5233016"
---
# <a name="cluster-position-full"></a><span data-ttu-id="5d4db-104">Posición completa del clúster</span><span class="sxs-lookup"><span data-stu-id="5d4db-104">Cluster position full</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5d4db-105">La característica *Posición completa del clúster* ofrece una alternativa a la aplicación más estricta de las reglas de las pausas laborales cuando se utiliza el picking en clúster, ya que permite un mayor margen de error en las restricciones volumétricas de los contenedores o bolsas.</span><span class="sxs-lookup"><span data-stu-id="5d4db-105">The *Cluster position full* feature offers an alternative to more rigid enforcement of work break rules when cluster picking is used, because it enables a larger margin of error in the volumetric constraints of containers or totes.</span></span> <span data-ttu-id="5d4db-106">En un escenario común, no todos los elementos de una orden de trabajo caben en un contenedor seleccionado.</span><span class="sxs-lookup"><span data-stu-id="5d4db-106">In a common scenario, not all items on a work order fit into a selected container.</span></span> <span data-ttu-id="5d4db-107">Los trabajadores del almacén que realizan picking en clúster tienen pocas opciones en este escenario: deben cambiar a un tamaño de contenedor más grande o trabajar con su supervisor para encontrar una solución diferente.</span><span class="sxs-lookup"><span data-stu-id="5d4db-107">Warehouse workers who are cluster picking have few options in this scenario: they must either change to a larger container size or work with their supervisor to come up with a different solution.</span></span>

<span data-ttu-id="5d4db-108">Esta característica introduce la capacidad de ejecutar el botón **Completo** en una de las unidades de trabajo en un clúster.</span><span class="sxs-lookup"><span data-stu-id="5d4db-108">This feature introduces the ability to run the **Full** button on one of the work units in a cluster.</span></span> <span data-ttu-id="5d4db-109">En versiones anteriores, esta opción solo estaba disponible para el picking de pedidos normal, no para el picking en clúster.</span><span class="sxs-lookup"><span data-stu-id="5d4db-109">In older versions, this option was available only for regular order picking, not for cluster picking.</span></span> <span data-ttu-id="5d4db-110">Sin embargo, esta característica difiere del botón estándar **Completo** en el que cancela el trabajo restante.</span><span class="sxs-lookup"><span data-stu-id="5d4db-110">However, this feature differs from the standard **Full** button in that it cancels the remaining work.</span></span> <span data-ttu-id="5d4db-111">No sugiere que el usuario agregue otro contenedor al mismo clúster y no crea automáticamente un nuevo trabajo.</span><span class="sxs-lookup"><span data-stu-id="5d4db-111">It doesn't suggest that the user add another bin to the same cluster, and it doesn't automatically create new work.</span></span>

## <a name="turn-on-the-cluster-position-full-feature"></a><span data-ttu-id="5d4db-112">Activar la característica Posición completa del clúster</span><span class="sxs-lookup"><span data-stu-id="5d4db-112">Turn on the Cluster position full feature</span></span>

<span data-ttu-id="5d4db-113">Antes de poder usar esta característica debe estar activada en su sistema.</span><span class="sxs-lookup"><span data-stu-id="5d4db-113">Before you can use this feature, it must be turned on in your system.</span></span> <span data-ttu-id="5d4db-114">Los administradores pueden usar la configuración de [gestión de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de la función y activarla.</span><span class="sxs-lookup"><span data-stu-id="5d4db-114">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on.</span></span> <span data-ttu-id="5d4db-115">En el espacio de trabajo **Administración de funciones**, la función aparece de la siguiente forma:</span><span class="sxs-lookup"><span data-stu-id="5d4db-115">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="5d4db-116">**Módulo:** *Gestión de almacén*</span><span class="sxs-lookup"><span data-stu-id="5d4db-116">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="5d4db-117">**Nombre de la característica**: *Posición completa del clúster*</span><span class="sxs-lookup"><span data-stu-id="5d4db-117">**Feature name:** *Cluster position full*</span></span>

## <a name="setup"></a><span data-ttu-id="5d4db-118">Configurar</span><span class="sxs-lookup"><span data-stu-id="5d4db-118">Setup</span></span>

<span data-ttu-id="5d4db-119">Esta sección proporciona pautas y un ejemplo que muestra cómo configurar y usar la característica *Posición completa del clúster*.</span><span class="sxs-lookup"><span data-stu-id="5d4db-119">This section provides guidelines, and an example that shows how to set up and use the *Cluster position full* feature.</span></span>

### <a name="make-sample-data-available"></a><span data-ttu-id="5d4db-120">Hacer que los datos de muestra estén disponibles</span><span class="sxs-lookup"><span data-stu-id="5d4db-120">Make sample data available</span></span>

<span data-ttu-id="5d4db-121">Para trabajar en el [escenario de ejemplo](#example-scenario) mediante el uso de los registros y valores de muestra que se especifican aquí, debe estar en un sistema donde estén instalados los [datos de demostración](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) estándar.</span><span class="sxs-lookup"><span data-stu-id="5d4db-121">To work through the [example scenario](#example-scenario) by using the sample records and values that are specified here, you must be on a system where the standard [demo data](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) is installed.</span></span> <span data-ttu-id="5d4db-122">Además, también debe seleccionar la entidad legal **USMF** antes de empezar.</span><span class="sxs-lookup"><span data-stu-id="5d4db-122">Additionally, you must select the **USMF** legal entity before you begin.</span></span>

<span data-ttu-id="5d4db-123">También puede usar este escenario de ejemplo como guía para trabajar con esta en un sistema de producción.</span><span class="sxs-lookup"><span data-stu-id="5d4db-123">You can also use the example scenario as guidance for working with this feature on a production system.</span></span> <span data-ttu-id="5d4db-124">Sin embargo, en ese caso, debe sustituir sus propios valores para los valores de configuración que se describen aquí.</span><span class="sxs-lookup"><span data-stu-id="5d4db-124">However, in that case, you must substitute your own values for the settings that are described here.</span></span>

### <a name="cluster-profiles"></a><span data-ttu-id="5d4db-125">Perfiles de clúster</span><span class="sxs-lookup"><span data-stu-id="5d4db-125">Cluster profiles</span></span>

<span data-ttu-id="5d4db-126">Debe especificar si los identificadores de clúster se generan automáticamente, cuántas posiciones se utilizan, cuándo se rompen los clústeres y cómo se secuencia y verifica el trabajo de picking.</span><span class="sxs-lookup"><span data-stu-id="5d4db-126">You must specify whether cluster IDs are automatically generated, how many positions are used, when clusters are broken, and how the picking work is sequenced and verified.</span></span>

1. <span data-ttu-id="5d4db-127">Vaya a **Administración de almacenes \> Configuración \> Dispositivo móvil \> Perfiles de clúster**.</span><span class="sxs-lookup"><span data-stu-id="5d4db-127">Go to **Warehouse management \> Setup \> Mobile device \> Cluster profiles**.</span></span>
1. <span data-ttu-id="5d4db-128">En el panel de lista, seleccione el registro **Crear clúster**.</span><span class="sxs-lookup"><span data-stu-id="5d4db-128">In the list pane, select the **Create Cluster** record.</span></span>
1. <span data-ttu-id="5d4db-129">En la ficha desplegable **General**, compruebe los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="5d4db-129">On the **General** FastTab, verify the following values:</span></span>

    - <span data-ttu-id="5d4db-130">**Generar Id. de clúster**: seleccione *Sí*.</span><span class="sxs-lookup"><span data-stu-id="5d4db-130">**Generate cluster ID:** *Yes*</span></span>
    - <span data-ttu-id="5d4db-131">**Activar posiciones**: *Sí*</span><span class="sxs-lookup"><span data-stu-id="5d4db-131">**Activate positions:** *Yes*</span></span>
    - <span data-ttu-id="5d4db-132">**Número de posiciones**: *2*</span><span class="sxs-lookup"><span data-stu-id="5d4db-132">**Number of positions:** *2*</span></span>
    - <span data-ttu-id="5d4db-133">**Nombre de la posición**: *Numérico*</span><span class="sxs-lookup"><span data-stu-id="5d4db-133">**Position name:** *Numeric*</span></span>
    - <span data-ttu-id="5d4db-134">**Dividir clúster en**: *Colocar*</span><span class="sxs-lookup"><span data-stu-id="5d4db-134">**Break cluster at:** *Put*</span></span>
    - <span data-ttu-id="5d4db-135">**Tipo de comprobación del orden**: *Escaneo de posición*</span><span class="sxs-lookup"><span data-stu-id="5d4db-135">**Sort verification type:** *Position scan*</span></span>

1. <span data-ttu-id="5d4db-136">En la ficha desplegable **Clasificación de clústeres**.</span><span class="sxs-lookup"><span data-stu-id="5d4db-136">In the **Cluster sorting** FastTab.</span></span> <span data-ttu-id="5d4db-137">La cuadrícula debe estar en blanco (es decir, no debe contener líneas).</span><span class="sxs-lookup"><span data-stu-id="5d4db-137">The grid should be blank (that is, it should contain no lines).</span></span>

### <a name="work-templates"></a><span data-ttu-id="5d4db-138">Plantillas de trabajo</span><span class="sxs-lookup"><span data-stu-id="5d4db-138">Work templates</span></span>

<span data-ttu-id="5d4db-139">Debe definir cómo crear el trabajo de picking para el picking en clúster.</span><span class="sxs-lookup"><span data-stu-id="5d4db-139">You must define how the picking work for cluster picking is created.</span></span>

1. <span data-ttu-id="5d4db-140">Vaya a **Administración de almacenes \> Configuración \> Trabajo \> Plantillas de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="5d4db-140">Go to **Warehouse management \> Setup \> Work \> Work templates**.</span></span>
1. <span data-ttu-id="5d4db-141">En la parte superior de la página, establezca el campo **Tipo de orden de trabajo** en *Pedidos de venta*.</span><span class="sxs-lookup"><span data-stu-id="5d4db-141">At the top of the page, set the **Work order type** field to *Sales orders*.</span></span>
1. <span data-ttu-id="5d4db-142">Asegúrese de que se enumeren las siguientes plantillas de trabajo de los datos de demostración.</span><span class="sxs-lookup"><span data-stu-id="5d4db-142">Make sure that the following work templates from the demo data are listed.</span></span> <span data-ttu-id="5d4db-143">Si no están disponibles, no podrá completar el escenario.</span><span class="sxs-lookup"><span data-stu-id="5d4db-143">If they aren't available, you won't be able to complete the scenario.</span></span>

    - <span data-ttu-id="5d4db-144">61 SO Etapa</span><span class="sxs-lookup"><span data-stu-id="5d4db-144">61 SO Stage</span></span>
    - <span data-ttu-id="5d4db-145">61 SO Picking en clúster</span><span class="sxs-lookup"><span data-stu-id="5d4db-145">61 SO Cluster pick</span></span>

### <a name="location-directives"></a><span data-ttu-id="5d4db-146">Directivas de ubicación</span><span class="sxs-lookup"><span data-stu-id="5d4db-146">Location directives</span></span>

<span data-ttu-id="5d4db-147">Debe especificar dónde se recogen los artículos y dónde se colocan.</span><span class="sxs-lookup"><span data-stu-id="5d4db-147">You must specify where items are picked from and where they are put.</span></span>

1. <span data-ttu-id="5d4db-148">Vaya a **Gestión de almacenes \> Configurar \> Directivas de ubicación**.</span><span class="sxs-lookup"><span data-stu-id="5d4db-148">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="5d4db-149">En el encabezado de lista, establezca el campo **Tipo de orden de trabajo** en *Pedidos de venta*.</span><span class="sxs-lookup"><span data-stu-id="5d4db-149">In the list header, set the **Work order type** field to *Sales orders*.</span></span>
1. <span data-ttu-id="5d4db-150">Asegúrese de que se enumeren las siguientes directivas de pedido de venta de los datos de demostración.</span><span class="sxs-lookup"><span data-stu-id="5d4db-150">Make sure that the following sales order directives from the demo data are listed.</span></span> <span data-ttu-id="5d4db-151">Si no están disponibles, no podrá completar el escenario.</span><span class="sxs-lookup"><span data-stu-id="5d4db-151">If they aren't available, you won't be able to complete the scenario.</span></span>

    - <span data-ttu-id="5d4db-152">61 Picking en clúster</span><span class="sxs-lookup"><span data-stu-id="5d4db-152">61 Cluster pick</span></span>
    - <span data-ttu-id="5d4db-153">61 SO Orden de picking</span><span class="sxs-lookup"><span data-stu-id="5d4db-153">61 SO Pick order</span></span>

### <a name="mobile-device-menu-items"></a><span data-ttu-id="5d4db-154">Elementos de menú del dispositivo móvil</span><span class="sxs-lookup"><span data-stu-id="5d4db-154">Mobile device menu items</span></span>

<span data-ttu-id="5d4db-155">Debe configurar un elemento de menú del dispositivo móvil para usar el trabajo existente realizado mediante picking en clúster.</span><span class="sxs-lookup"><span data-stu-id="5d4db-155">You must configure a mobile device menu item to use existing work that is directed by cluster picking.</span></span> <span data-ttu-id="5d4db-156">En el elemento del menú del dispositivo móvil para el picking en clúster, el parámetro **Permitir la división del trabajo** debe estar activado y la clase de trabajo *SO picking* debe agregarse la clase de trabajo.</span><span class="sxs-lookup"><span data-stu-id="5d4db-156">In the mobile device menu item for cluster picking, the **Allow splitting of work** parameter must be turned on, and the *SO Pick* work class must be added.</span></span>

1. <span data-ttu-id="5d4db-157">Vaya a **Administración de almacenes \> Configurar \> Dispositivo móvil \> Elementos de menú del dispositivo móvil**.</span><span class="sxs-lookup"><span data-stu-id="5d4db-157">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="5d4db-158">En el panel de lista, seleccione el registro **Crear picking en clúster**.</span><span class="sxs-lookup"><span data-stu-id="5d4db-158">In the list pane, select the **Cluster Pick Create** record.</span></span>
1. <span data-ttu-id="5d4db-159">Seleccione **Editar** en el Panel de acciones.</span><span class="sxs-lookup"><span data-stu-id="5d4db-159">Select **Edit** in the Action pane.</span></span>
1. <span data-ttu-id="5d4db-160">En la ficha desplegable **General**, establezca los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="5d4db-160">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="5d4db-161">**Dirigido por**: *Picking de clústeres*</span><span class="sxs-lookup"><span data-stu-id="5d4db-161">**Directed by:** *Cluster picking*</span></span>
    - <span data-ttu-id="5d4db-162">**Generar matrícula de entidad de almacén:** *Sí*</span><span class="sxs-lookup"><span data-stu-id="5d4db-162">**Generate license plate:** *Yes*</span></span>
    - <span data-ttu-id="5d4db-163">**Permitir división del trabajo**: *Sí*</span><span class="sxs-lookup"><span data-stu-id="5d4db-163">**Allow splitting of work:** *Yes*</span></span>
    - <span data-ttu-id="5d4db-164">**Id. de perfil de clúster**: *Crear clúster*</span><span class="sxs-lookup"><span data-stu-id="5d4db-164">**Cluster profile ID:** *Create Cluster*</span></span>

    <span data-ttu-id="5d4db-165">Acepte los valores predeterminados para el resto de campos.</span><span class="sxs-lookup"><span data-stu-id="5d4db-165">Accept the default values for all other fields.</span></span>

1. <span data-ttu-id="5d4db-166">En la ficha desplegable **Clases de trabajo**, agregue las siguientes dos líneas, según sea necesario:</span><span class="sxs-lookup"><span data-stu-id="5d4db-166">On the **Work classes** FastTab, add the following two lines, as required:</span></span>

    - <span data-ttu-id="5d4db-167">Línea 1 (generalmente presente en los datos de demostración):</span><span class="sxs-lookup"><span data-stu-id="5d4db-167">Line 1 (usually present in demo data):</span></span>

        - <span data-ttu-id="5d4db-168">**Id. de la clase de trabajo**: *Ventas*</span><span class="sxs-lookup"><span data-stu-id="5d4db-168">**Work class ID:** *Sales*</span></span> 
        - <span data-ttu-id="5d4db-169">**Tipo de orden de trabajo**: *Pedidos de venta*</span><span class="sxs-lookup"><span data-stu-id="5d4db-169">**Work order type:** *Sales orders*</span></span>

    - <span data-ttu-id="5d4db-170">Línea 2 (probablemente no está presente en los datos de demostración):</span><span class="sxs-lookup"><span data-stu-id="5d4db-170">Line 2 (probably not present in demo data):</span></span>

        - <span data-ttu-id="5d4db-171">**Identificador de la clase de trabajo**: *SO picking*</span><span class="sxs-lookup"><span data-stu-id="5d4db-171">**Work class ID:** *SO Pick*</span></span>
        - <span data-ttu-id="5d4db-172">**Tipo de orden de trabajo**: *Pedidos de venta*</span><span class="sxs-lookup"><span data-stu-id="5d4db-172">**Work order type:** *Sales orders*</span></span>

1. <span data-ttu-id="5d4db-173">Vaya a **Configuración de confirmación de trabajo** en el Panel de acciones.</span><span class="sxs-lookup"><span data-stu-id="5d4db-173">Go to **Work confirmation setup** in the Action pane.</span></span>
1. <span data-ttu-id="5d4db-174">Seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="5d4db-174">Select **Edit**.</span></span>
1. <span data-ttu-id="5d4db-175">Especifique uno de los valores siguientes en la línea en la cuadrícula:</span><span class="sxs-lookup"><span data-stu-id="5d4db-175">Enter the following values on the line in grid.</span></span>
    - <span data-ttu-id="5d4db-176">**Tipo de trabajo** - *Picking*</span><span class="sxs-lookup"><span data-stu-id="5d4db-176">**Work type** - *Pick*</span></span>
    - <span data-ttu-id="5d4db-177">**Confirmación del producto** - *Seleccionar la casilla de verificación*</span><span class="sxs-lookup"><span data-stu-id="5d4db-177">**Product confirmation** - *Select the check box*</span></span>

1. <span data-ttu-id="5d4db-178">Seleccione **Guardar** en el Panel de acciones y cierre la página.</span><span class="sxs-lookup"><span data-stu-id="5d4db-178">Select **Save** in the Action pane and close the page.</span></span>

## <a name="create-picking-work"></a><span data-ttu-id="5d4db-179">Crear trabajo de selección</span><span class="sxs-lookup"><span data-stu-id="5d4db-179">Create picking work</span></span>

<span data-ttu-id="5d4db-180">Antes de que pueda iniciar el picking en clúster, debe crear algún trabajo de salida.</span><span class="sxs-lookup"><span data-stu-id="5d4db-180">Before you can start cluster picking, you must create some outbound work.</span></span> <span data-ttu-id="5d4db-181">El perfil de clúster que creó anteriormente especifica dos posiciones de clúster.</span><span class="sxs-lookup"><span data-stu-id="5d4db-181">The cluster profile that you created earlier specifies two cluster positions.</span></span> <span data-ttu-id="5d4db-182">Por lo tanto, se deben crear al menos dos identificadores de trabajo para el picking de pedidos de venta.</span><span class="sxs-lookup"><span data-stu-id="5d4db-182">Therefore, at least two work IDs must be created for sales order picking.</span></span> <span data-ttu-id="5d4db-183">Para este escenario, las transacciones ocurrirán en el almacén *61*, y usarán los elementos *L0101* y *T0100*.</span><span class="sxs-lookup"><span data-stu-id="5d4db-183">For this scenario, transactions will occur in warehouse *61*, and they will use items *L0101* and *T0100*.</span></span> <span data-ttu-id="5d4db-184">Los datos de demostración deben tener suficiente inventario disponible de estos artículos.</span><span class="sxs-lookup"><span data-stu-id="5d4db-184">The demo data should have enough on-hand inventory of these items.</span></span> <span data-ttu-id="5d4db-185">Asegúrese de tener suficiente inventario para completar las transacciones.</span><span class="sxs-lookup"><span data-stu-id="5d4db-185">Make sure that you have enough inventory to complete the transactions.</span></span>

### <a name="create-sales-order-1"></a><span data-ttu-id="5d4db-186">Crear pedido de ventas 1</span><span class="sxs-lookup"><span data-stu-id="5d4db-186">Create sales order 1</span></span>

1. <span data-ttu-id="5d4db-187">Vaya a **Ventas y marketing \> Pedidos de ventas \> Todos los pedidos de ventas**.</span><span class="sxs-lookup"><span data-stu-id="5d4db-187">Go to **Sales and Marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="5d4db-188">Seleccione **Nuevo** para crear un pedido de ventas 1.</span><span class="sxs-lookup"><span data-stu-id="5d4db-188">Select **New** to create sales order 1.</span></span>
1. <span data-ttu-id="5d4db-189">En el cuadro de diálogo **Crear pedido de ventas**, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="5d4db-189">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="5d4db-190">**Cuenta de cliente:** *US-010*</span><span class="sxs-lookup"><span data-stu-id="5d4db-190">**Customer account:** *US-010*</span></span>
    - <span data-ttu-id="5d4db-191">**Almacén**: *61*</span><span class="sxs-lookup"><span data-stu-id="5d4db-191">**Warehouse:** *61*</span></span>

1. <span data-ttu-id="5d4db-192">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5d4db-192">Select **OK**.</span></span>
1. <span data-ttu-id="5d4db-193">Se abre el nuevo pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="5d4db-193">The new sales order is opened.</span></span> <span data-ttu-id="5d4db-194">En la ficha desplegable **Líneas de pedido de venta**, agregue una línea que tenga los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="5d4db-194">On the **Sales order lines** FastTab, add a line that has the following settings:</span></span>

    - <span data-ttu-id="5d4db-195">**Código de artículo:** *T0100*</span><span class="sxs-lookup"><span data-stu-id="5d4db-195">**Item number:** *T0100*</span></span>
    - <span data-ttu-id="5d4db-196">**Cantidad:** *5*</span><span class="sxs-lookup"><span data-stu-id="5d4db-196">**Quantity:** *5*</span></span>

1. <span data-ttu-id="5d4db-197">En la ficha desplegable **Detalles de línea**, en la pestaña **Entrega**, establezca el campo **Fecha de entrega confirmada** en la fecha de hoy.</span><span class="sxs-lookup"><span data-stu-id="5d4db-197">On the **Line details** FastTab, on the **Delivery** tab, set the **Confirmed ship date** field to today's date.</span></span>
1. <span data-ttu-id="5d4db-198">En la ficha desplegable **Líneas de pedido de venta**, agregue una segunda línea que tenga los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="5d4db-198">On the **Sales order lines** FastTab, add a second line that has the following settings:</span></span>

    - <span data-ttu-id="5d4db-199">**Código de artículo:** *L0101*</span><span class="sxs-lookup"><span data-stu-id="5d4db-199">**Item number:** *L0101*</span></span>
    - <span data-ttu-id="5d4db-200">**Cantidad:** *20*</span><span class="sxs-lookup"><span data-stu-id="5d4db-200">**Quantity:** *20*</span></span>

1. <span data-ttu-id="5d4db-201">En la ficha desplegable **Detalles de línea**, en la pestaña **Entrega**, establezca el campo **Fecha de entrega confirmada** en la fecha de hoy.</span><span class="sxs-lookup"><span data-stu-id="5d4db-201">On the **Line details** FastTab, on the **Delivery** tab, set the **Confirmed ship date** field to today's date.</span></span>
1. <span data-ttu-id="5d4db-202">Para cada línea que acaba de agregar, siga estos pasos para reservar el inventario:</span><span class="sxs-lookup"><span data-stu-id="5d4db-202">For each line that you just added, follow these steps to reserve inventory:</span></span>

    1. <span data-ttu-id="5d4db-203">Seleccione la línea que desea reservar.</span><span class="sxs-lookup"><span data-stu-id="5d4db-203">Select the line to reserve.</span></span>
    2. <span data-ttu-id="5d4db-204">En la ficha desplegable **Líneas de pedido de ventas**, en el menú **Inventario \> Reserva**.</span><span class="sxs-lookup"><span data-stu-id="5d4db-204">On the **Sales order lines** FastTab, select **Inventory \> Reservation**.</span></span>
    3. <span data-ttu-id="5d4db-205">En la página **Reserva**, en el Panel de acciones, seleccione **Reservar lote** para reservar inventario.</span><span class="sxs-lookup"><span data-stu-id="5d4db-205">On the **Reservation** page, on the Action Pane, select **Reserve lot** to reserve the inventory.</span></span>
    4. <span data-ttu-id="5d4db-206">Cierre la página **Reserva**.</span><span class="sxs-lookup"><span data-stu-id="5d4db-206">Close the **Reservation** page.</span></span>

1. <span data-ttu-id="5d4db-207">En el panel de acciones, en la pestaña **Almacén**, seleccione **Liberar al almacén**.</span><span class="sxs-lookup"><span data-stu-id="5d4db-207">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>

    <span data-ttu-id="5d4db-208">Cuando se complete la emisión, recibirá mensajes informativos que muestran la oleada y los identificadores de carga que se crearon.</span><span class="sxs-lookup"><span data-stu-id="5d4db-208">When the release is completed, you receive informational messages that show the wave and load IDs that were created.</span></span>

### <a name="create-sales-order-2"></a><span data-ttu-id="5d4db-209">Crear pedido de ventas 2</span><span class="sxs-lookup"><span data-stu-id="5d4db-209">Create sales order 2</span></span>

1. <span data-ttu-id="5d4db-210">Vaya a **Ventas y marketing \> Pedidos de ventas \> Todos los pedidos de ventas**.</span><span class="sxs-lookup"><span data-stu-id="5d4db-210">Go to **Sales and Marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="5d4db-211">Seleccione **Nuevo** para crear un pedido de ventas 2.</span><span class="sxs-lookup"><span data-stu-id="5d4db-211">Select **New** to create sales order 2.</span></span>
1. <span data-ttu-id="5d4db-212">En el cuadro de diálogo **Crear pedido de ventas**, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="5d4db-212">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="5d4db-213">**Cuenta de cliente:** *US-011*</span><span class="sxs-lookup"><span data-stu-id="5d4db-213">**Customer account:** *US-011*</span></span>
    - <span data-ttu-id="5d4db-214">**Almacén**: *61*</span><span class="sxs-lookup"><span data-stu-id="5d4db-214">**Warehouse:** *61*</span></span>

1. <span data-ttu-id="5d4db-215">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5d4db-215">Select **OK**.</span></span>
1. <span data-ttu-id="5d4db-216">Se abre el nuevo pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="5d4db-216">The new sales order is opened.</span></span> <span data-ttu-id="5d4db-217">En la ficha desplegable **Líneas de pedido de venta**, agregue una línea que tenga los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="5d4db-217">On the **Sales order lines** FastTab, add a line that has the following settings:</span></span>

    - <span data-ttu-id="5d4db-218">**Código de artículo:** *L0101*</span><span class="sxs-lookup"><span data-stu-id="5d4db-218">**Item number:** *L0101*</span></span>
    - <span data-ttu-id="5d4db-219">**Cantidad:** *20*</span><span class="sxs-lookup"><span data-stu-id="5d4db-219">**Quantity:** *20*</span></span>

1. <span data-ttu-id="5d4db-220">En la ficha desplegable **Detalles de línea**, en la pestaña **Entrega**, establezca el campo **Fecha de entrega confirmada** en la fecha de hoy.</span><span class="sxs-lookup"><span data-stu-id="5d4db-220">On the **Line details** FastTab, on the **Delivery** tab, set the **Confirmed ship date** field to today's date.</span></span>
1. <span data-ttu-id="5d4db-221">En la ficha desplegable **Líneas de pedido de venta**, agregue una segunda línea que tenga los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="5d4db-221">On the **Sales order lines** FastTab, add a second line that has the following settings:</span></span>

    - <span data-ttu-id="5d4db-222">**Código de artículo:** *T0100*</span><span class="sxs-lookup"><span data-stu-id="5d4db-222">**Item number:** *T0100*</span></span>
    - <span data-ttu-id="5d4db-223">**Cantidad:** *2*</span><span class="sxs-lookup"><span data-stu-id="5d4db-223">**Quantity:** *2*</span></span>

1. <span data-ttu-id="5d4db-224">En la ficha desplegable **Detalles de línea**, en la pestaña **Entrega**, establezca el campo **Fecha de entrega confirmada** en la fecha de hoy.</span><span class="sxs-lookup"><span data-stu-id="5d4db-224">On the **Line details** FastTab, on the **Delivery** tab, set the **Confirmed ship date** field to today's date.</span></span>
1. <span data-ttu-id="5d4db-225">Para cada línea que acaba de agregar, siga estos pasos para reservar el inventario:</span><span class="sxs-lookup"><span data-stu-id="5d4db-225">For each line that you just added, follow these steps to reserve inventory:</span></span>

    1. <span data-ttu-id="5d4db-226">Seleccione la línea que desea reservar.</span><span class="sxs-lookup"><span data-stu-id="5d4db-226">Select the line to reserve.</span></span>
    2. <span data-ttu-id="5d4db-227">En la ficha desplegable **Líneas de pedido de ventas**, en el menú **Inventario \> Reserva**.</span><span class="sxs-lookup"><span data-stu-id="5d4db-227">On the **Sales order lines** FastTab, select **Inventory \> Reservation**.</span></span>
    3. <span data-ttu-id="5d4db-228">En la página **Reserva**, en el Panel de acciones, seleccione **Reservar lote** para reservar inventario.</span><span class="sxs-lookup"><span data-stu-id="5d4db-228">On the **Reservation** page, on the Action Pane, select **Reserve lot** to reserve the inventory.</span></span>
    4. <span data-ttu-id="5d4db-229">Cierre la página **Reserva**.</span><span class="sxs-lookup"><span data-stu-id="5d4db-229">Close the **Reservation** page.</span></span>

1. <span data-ttu-id="5d4db-230">En el panel de acciones, en la pestaña **Almacén**, seleccione **Liberar al almacén**.</span><span class="sxs-lookup"><span data-stu-id="5d4db-230">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>

    <span data-ttu-id="5d4db-231">Cuando se complete la emisión, recibirá mensajes informativos que muestran la oleada y los identificadores de carga que se crearon.</span><span class="sxs-lookup"><span data-stu-id="5d4db-231">When the release is completed, you receive informational messages that show the wave and load IDs that were created.</span></span>

### <a name="get-work-ids-and-license-plate-numbers"></a><span data-ttu-id="5d4db-232">Obtener identificaciones de trabajo y números de entidad de almacén</span><span class="sxs-lookup"><span data-stu-id="5d4db-232">Get work IDs and license plate numbers</span></span>

<span data-ttu-id="5d4db-233">Se deberían haber creado dos identificadores de trabajo, cada uno de los cuales tiene dos líneas de picking.</span><span class="sxs-lookup"><span data-stu-id="5d4db-233">Two work IDs should have been created, each of which has two pick lines.</span></span> <span data-ttu-id="5d4db-234">Siga estos pasos para encontrar los identificadores de trabajo y las asignaciones de matrículas de entidad de almacén.</span><span class="sxs-lookup"><span data-stu-id="5d4db-234">Follow these steps to find the work IDs and license plate assignments.</span></span>

1. <span data-ttu-id="5d4db-235">Vaya a **Gestión de almacenes \> Trabajo \> Detalles de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="5d4db-235">Go to **Warehouse management \> Work \> Work details**.</span></span>
1. <span data-ttu-id="5d4db-236">En la cuadrícula **Información general**, busque la columna **Número de pedido** para los dos pedidos de venta que acaba de crear.</span><span class="sxs-lookup"><span data-stu-id="5d4db-236">In the **Overview** grid, search the **Order number** column for the two sales orders that you just created.</span></span> <span data-ttu-id="5d4db-237">Para cada pedido de venta, anote el identificador de trabajo correspondiente.</span><span class="sxs-lookup"><span data-stu-id="5d4db-237">For each sales order, make a note of the corresponding work ID.</span></span>
1. <span data-ttu-id="5d4db-238">Seleccione la fila de cada pedido de ventas para mostrar información relacionada en la cuadrícula **Líneas**.</span><span class="sxs-lookup"><span data-stu-id="5d4db-238">Select the row for each sales order to show related information in the **Lines** grid.</span></span> <span data-ttu-id="5d4db-239">Tome nota de la ubicación desde la que se recogerá cada artículo.</span><span class="sxs-lookup"><span data-stu-id="5d4db-239">Make a note of the location that each item will be picked from.</span></span>
1. <span data-ttu-id="5d4db-240">Vaya a **Gestión de inventario \> Consultas e informes \> Inventario disponible**.</span><span class="sxs-lookup"><span data-stu-id="5d4db-240">Go to **Inventory management \> Inquiries and reports \> On-hand list**.</span></span>
1. <span data-ttu-id="5d4db-241">En el panel de acciones, seleccione **Dimensiones** para abrir el cuadro de diálogo **Mostrar dimensión**.</span><span class="sxs-lookup"><span data-stu-id="5d4db-241">On the Action Pane, select **Dimensions** to open the **Dimension display** dialog box.</span></span>
1. <span data-ttu-id="5d4db-242">Asegúrese de que las casillas de verificación **Matrícula de entidad de almacén**, **Almacén** y **Número de artículo** están seleccionadas y luego seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5d4db-242">Make sure that the **License plate**, **Warehouse**, and **Item number** check boxes are selected, and then select **OK**.</span></span>
1. <span data-ttu-id="5d4db-243">En el panel **Filtrar**, configure los siguientes filtros:</span><span class="sxs-lookup"><span data-stu-id="5d4db-243">In the **Filter** pane, set the following filters:</span></span>

    - <span data-ttu-id="5d4db-244">**Número de artículo** - **es uno de** - *L0101* y *T100*</span><span class="sxs-lookup"><span data-stu-id="5d4db-244">**Item number** – **is one of** – *L0101* and *T100*</span></span>
    - <span data-ttu-id="5d4db-245">**Almacén** - **empieza con** - *61*</span><span class="sxs-lookup"><span data-stu-id="5d4db-245">**Warehouse** – **begins with** – *61*</span></span>

1. <span data-ttu-id="5d4db-246">Anote los valores de la **Matrícula de entidad de licencia** que se muestran.</span><span class="sxs-lookup"><span data-stu-id="5d4db-246">Make a note of the **License plate** values that are shown.</span></span>

## <a name="example-scenario"></a><a name="example-scenario"></a><span data-ttu-id="5d4db-247">Supuesto de ejemplo</span><span class="sxs-lookup"><span data-stu-id="5d4db-247">Example scenario</span></span>

### <a name="mobile-device-flow-execution--work-confirmation-setup-for-the-product"></a><span data-ttu-id="5d4db-248">Ejecución del flujo de dispositivos móviles: configuración de la confirmación de trabajo para el producto</span><span class="sxs-lookup"><span data-stu-id="5d4db-248">Mobile device flow execution – Work confirmation setup for the product</span></span>

1. <span data-ttu-id="5d4db-249">Inicie sesión en la aplicación de almacén como un usuario en el almacén *61*.</span><span class="sxs-lookup"><span data-stu-id="5d4db-249">Sign in to the warehouse app as a user in warehouse *61*.</span></span>
1. <span data-ttu-id="5d4db-250">Vaya a **Saliente \> Creación de picking en clúster**.</span><span class="sxs-lookup"><span data-stu-id="5d4db-250">Go to **Outbound \> Cluster pick create**.</span></span>

    <span data-ttu-id="5d4db-251">La página **TAREA: Asignar trabajo al clúster** aparece.</span><span class="sxs-lookup"><span data-stu-id="5d4db-251">The **TASK: Assign work to Cluster** page appears.</span></span>

1. <span data-ttu-id="5d4db-252">Especifique el identificador de trabajo para el pedido de venta 1 para asignarlo a la posición 1 del grupo.</span><span class="sxs-lookup"><span data-stu-id="5d4db-252">Enter the work ID for sales order 1 to assign it to cluster position 1.</span></span>
1. <span data-ttu-id="5d4db-253">Seleccione **Aceptar** (símbolo de marca de verificación).</span><span class="sxs-lookup"><span data-stu-id="5d4db-253">Select **OK** (check mark symbol).</span></span>
1. <span data-ttu-id="5d4db-254">Especifique el identificador de trabajo para el pedido de venta 2 para asignarlo a la posición 2 del grupo.</span><span class="sxs-lookup"><span data-stu-id="5d4db-254">Enter the work ID for sales order 2 to assign it to cluster position 2.</span></span>
1. <span data-ttu-id="5d4db-255">Seleccione **Aceptar** (símbolo de marca de verificación).</span><span class="sxs-lookup"><span data-stu-id="5d4db-255">Select **OK** (check mark symbol).</span></span>

    <span data-ttu-id="5d4db-256">La página **TAREA: Creación de picking en clúster: picking** aparece y muestra *Elemento L0101 2 PL*.</span><span class="sxs-lookup"><span data-stu-id="5d4db-256">The **TASK: Cluster Pick Create: Pick** page appears and shows *Item L0101 2 PL*.</span></span>

<span data-ttu-id="5d4db-257">Debido a que el perfil del clúster estableció el número de posiciones en 2, el sistema lo dirige automáticamente a la primera selección de consolidación: dos palés (PL) del artículo *L0101*.</span><span class="sxs-lookup"><span data-stu-id="5d4db-257">Because the cluster profile set the number of positions to 2, the system automatically directs you to the first consolidate pick: two pallets (PL) of item *L0101*.</span></span>

<span data-ttu-id="5d4db-258">En cualquier momento durante los siguientes pasos, puede seleccionar la pestaña **Detalles** para ver información adicional sobre la tarea, como la ubicación de picking.</span><span class="sxs-lookup"><span data-stu-id="5d4db-258">At any time during the following steps, you can select the **Details** tab to view additional information about the task, such as the picking location.</span></span>

1. <span data-ttu-id="5d4db-259">Defina el campo **ARTÍCULO** en *L0101*.</span><span class="sxs-lookup"><span data-stu-id="5d4db-259">Set the **ITEM** field to *L0101*.</span></span> <span data-ttu-id="5d4db-260">Esto confirma el número de elemento, que es necesario para este elemento de menú (lo configuró anteriormente seleccionando **Configuración de confirmación de trabajo** desde la página **Elemento de menú del dispositivo móvil** cuando creó este elemento de menú).</span><span class="sxs-lookup"><span data-stu-id="5d4db-260">This confirms the item number, which is required for this menu item (you configured this earlier by selecting **Work confirmation setup**  from the **Mobile device menu item** page when you created this menu item).</span></span>
1. <span data-ttu-id="5d4db-261">Ingrese el número de la matrícula de la entidad de almacén que está asociada con el artículo en la ubicación que se está recogiendo.</span><span class="sxs-lookup"><span data-stu-id="5d4db-261">Enter the license plate number that is associated with the item in the location that is being picked.</span></span> <span data-ttu-id="5d4db-262">Escogerá dos palés.</span><span class="sxs-lookup"><span data-stu-id="5d4db-262">You will pick two pallets.</span></span>
1. <span data-ttu-id="5d4db-263">Selecciona el campo **LP** en *LP\_PICK\_01*.</span><span class="sxs-lookup"><span data-stu-id="5d4db-263">Set the **LP** field to *LP\_PICK\_01*.</span></span>
1. <span data-ttu-id="5d4db-264">Seleccione **Aceptar** (símbolo de marca de verificación).</span><span class="sxs-lookup"><span data-stu-id="5d4db-264">Select **OK** (check mark symbol).</span></span>

    <span data-ttu-id="5d4db-265">La página **TAREA: Ordenar: Creación de picking en clúster** aparece.</span><span class="sxs-lookup"><span data-stu-id="5d4db-265">The **TASK: Sort: Cluster Pick Create** page appears.</span></span> <span data-ttu-id="5d4db-266">Aquí, clasificará los dos palets recogidos en una posición de recogida.</span><span class="sxs-lookup"><span data-stu-id="5d4db-266">Here, you will sort the two picked pallets into a pick position.</span></span> <span data-ttu-id="5d4db-267">Esta posición puede ser una bolsa o un contenedor que se utiliza para separar el inventario recogido por pedido de venta.</span><span class="sxs-lookup"><span data-stu-id="5d4db-267">This position might be a tote or container that is used to separate the picked inventory by sales order.</span></span>

1. <span data-ttu-id="5d4db-268">Vea los detalles que se muestran para el artículo (*L0101*) y la cantidad (*20* por unidad) que se clasificará en la posición 1 (para el pedido de cliente 1).</span><span class="sxs-lookup"><span data-stu-id="5d4db-268">View the details that are shown for the item (*L0101*) and quantity (*20* ea) that will be sorted into position 1 (for sales order 1).</span></span>
1. <span data-ttu-id="5d4db-269">Establezca el campo **POSICIÓN NA** en *1*.</span><span class="sxs-lookup"><span data-stu-id="5d4db-269">Set the **POSITION NA** field to *1*.</span></span>
1. <span data-ttu-id="5d4db-270">Seleccione **Aceptar** (símbolo de marca de verificación).</span><span class="sxs-lookup"><span data-stu-id="5d4db-270">Select **OK** (check mark symbol).</span></span>
1. <span data-ttu-id="5d4db-271">Vea los detalles que se muestran para el artículo (*L0101*) y la cantidad (*20* por unidad) que se clasificará en la posición 2 (para el pedido de cliente 2).</span><span class="sxs-lookup"><span data-stu-id="5d4db-271">View the details that are shown for the item (*L0101*) and quantity (*20* ea) that will be sorted into position 2 (for sales order 2).</span></span>
1. <span data-ttu-id="5d4db-272">Establezca el campo **POSICIÓN NA** en *2*.</span><span class="sxs-lookup"><span data-stu-id="5d4db-272">Set the **POSITION NA** field to *2*.</span></span>
1. <span data-ttu-id="5d4db-273">Seleccione **Aceptar** (símbolo de marca de verificación).</span><span class="sxs-lookup"><span data-stu-id="5d4db-273">Select **OK** (check mark symbol).</span></span>

    <span data-ttu-id="5d4db-274">La página **TAREA: Creación de picking en clúster: picking** aparece y muestra *Elemento T0100 7 por unidad*.</span><span class="sxs-lookup"><span data-stu-id="5d4db-274">The **TASK: Cluster Pick Create: Pick** page appears and shows *Item T0100 7 ea*.</span></span>

<span data-ttu-id="5d4db-275">En este escenario, la posición 1 no puede aceptar la cantidad total de artículos que deben seleccionarse para satisfacer el pedido de venta 1.</span><span class="sxs-lookup"><span data-stu-id="5d4db-275">In this scenario, position 1 can't accept the full quantity of items that must be picked to fulfill sales order 1.</span></span> <span data-ttu-id="5d4db-276">Una posición debe estar marcada como completa.</span><span class="sxs-lookup"><span data-stu-id="5d4db-276">A position must be marked as full.</span></span> <span data-ttu-id="5d4db-277">En este escenario, hará una selección parcial del segundo artículo.</span><span class="sxs-lookup"><span data-stu-id="5d4db-277">In this scenario, you will do a partial pick of the second item.</span></span> <span data-ttu-id="5d4db-278">El segundo artículo se recogerá parcialmente para la posición 1 y se creará un nuevo trabajo para recoger la cantidad restante para cumplir con el pedido.</span><span class="sxs-lookup"><span data-stu-id="5d4db-278">The second item will be partially picked for position 1, and new work will be created to pick the remaining quantity to fulfill the order.</span></span>

1. <span data-ttu-id="5d4db-279">Seleccione el botón Menú (a veces denominado hamburguesa o botón de hamburguesa) y luego seleccione **Posición completa**.</span><span class="sxs-lookup"><span data-stu-id="5d4db-279">Select the Menu button (sometimes referred to as the hamburger or the hamburger button), and then select **Position full**.</span></span>
1. <span data-ttu-id="5d4db-280">Identifique el puesto que está completo y seleccione *1*.</span><span class="sxs-lookup"><span data-stu-id="5d4db-280">Identify the position that is full, and select *1*.</span></span>
1. <span data-ttu-id="5d4db-281">Seleccione **Aceptar** (símbolo de marca de verificación).</span><span class="sxs-lookup"><span data-stu-id="5d4db-281">Select **OK** (check mark symbol).</span></span>
1. <span data-ttu-id="5d4db-282">Escriba la cantidad de picking que aún se recoger en la posición 1.</span><span class="sxs-lookup"><span data-stu-id="5d4db-282">Enter the pick quantity that can still be picked into position 1.</span></span> <span data-ttu-id="5d4db-283">El sistema puede determinar qué número de artículo se está recogiendo.</span><span class="sxs-lookup"><span data-stu-id="5d4db-283">The system can determine which item number is being picked.</span></span>
1. <span data-ttu-id="5d4db-284">Introduzca *2*.</span><span class="sxs-lookup"><span data-stu-id="5d4db-284">Enter *2*.</span></span>
1. <span data-ttu-id="5d4db-285">Seleccione **Aceptar** (símbolo de marca de verificación).</span><span class="sxs-lookup"><span data-stu-id="5d4db-285">Select **OK** (check mark symbol).</span></span>
1. <span data-ttu-id="5d4db-286">Confirme el número de artículo para completar el picking del artículo restante en la posición 2.</span><span class="sxs-lookup"><span data-stu-id="5d4db-286">Confirm the item number to complete the pick of the remaining item into position 2.</span></span>
1. <span data-ttu-id="5d4db-287">Establezca el campo **ARTÍCULO** en *T0100*.</span><span class="sxs-lookup"><span data-stu-id="5d4db-287">Set the **ITEM** field to *T0100*.</span></span>
1. <span data-ttu-id="5d4db-288">Seleccione **Aceptar** (símbolo de marca de verificación).</span><span class="sxs-lookup"><span data-stu-id="5d4db-288">Select **OK** (check mark symbol).</span></span>
1. <span data-ttu-id="5d4db-289">Especifique la matrícula de entidad de almacén de la cual se está recogiendo el artículo configurando el campo **LP** en *LPREPL04*.</span><span class="sxs-lookup"><span data-stu-id="5d4db-289">Enter the license plate that the item is being picked from by setting the **LP** field to *LPREPL04*.</span></span>
1. <span data-ttu-id="5d4db-290">Seleccione **Aceptar** (símbolo de marca de verificación).</span><span class="sxs-lookup"><span data-stu-id="5d4db-290">Select **OK** (check mark symbol).</span></span>
1. <span data-ttu-id="5d4db-291">Vea los detalles que se muestran para el artículo (*T0100*) y la cantidad (*2* por unidad) que se clasificará en la posición 2 (para el pedido de cliente 2).</span><span class="sxs-lookup"><span data-stu-id="5d4db-291">View the details that are shown for the item (*T0100*) and quantity (*2* ea) that will be sorted into position 2 (for sales order 2).</span></span>
1. <span data-ttu-id="5d4db-292">Establezca el campo **POSICIÓN NA** en *2*.</span><span class="sxs-lookup"><span data-stu-id="5d4db-292">Set the **POSITION NA** field to *2*.</span></span>
1. <span data-ttu-id="5d4db-293">Seleccione **Aceptar** (símbolo de marca de verificación).</span><span class="sxs-lookup"><span data-stu-id="5d4db-293">Select **OK** (check mark symbol).</span></span>
1. <span data-ttu-id="5d4db-294">Vea los detalles que se muestran para el artículo (*T0100*) y la cantidad (*2* por unidad) que se clasificará en la posición 1 (para el pedido de cliente 1).</span><span class="sxs-lookup"><span data-stu-id="5d4db-294">View the details that are shown for the item (*T0100*) and quantity (*2* ea) that will be sorted into position 1 (for sales order 1).</span></span>
1. <span data-ttu-id="5d4db-295">Establezca el campo **POSICIÓN NA** en *1*.</span><span class="sxs-lookup"><span data-stu-id="5d4db-295">Set the **POSITION NA** field to *1*.</span></span>
1. <span data-ttu-id="5d4db-296">Seleccione **Aceptar** (símbolo de marca de verificación).</span><span class="sxs-lookup"><span data-stu-id="5d4db-296">Select **OK** (check mark symbol).</span></span>

    <span data-ttu-id="5d4db-297">La página **TAREA: Ordenar: Creación de picking en clúster: Colocar** aparece.</span><span class="sxs-lookup"><span data-stu-id="5d4db-297">The **TASK: Cluster Pick Create: Put** page appears.</span></span>

<span data-ttu-id="5d4db-298">En este escenario, el picking en clúster se ha completado y se redirige al usuario para que guarde los artículos recogidos de la posición 1 y la posición 2 en la ubicación de almacenamiento provisional *ETAPA01*.</span><span class="sxs-lookup"><span data-stu-id="5d4db-298">In this scenario, the cluster pick has been completed, and the user is directed to put away the picked items from position 1 and position 2 into staging location *STAGE01*.</span></span>

1. <span data-ttu-id="5d4db-299">Revise la información en la página.</span><span class="sxs-lookup"><span data-stu-id="5d4db-299">Review the information on the page.</span></span> <span data-ttu-id="5d4db-300">Muestra que una cantidad total de *44* se colocará en la ubicación de almacenamiento provisional.</span><span class="sxs-lookup"><span data-stu-id="5d4db-300">It shows that a total quantity of *44* will be put to the staging location.</span></span>
1. <span data-ttu-id="5d4db-301">Seleccione **Aceptar** (símbolo de marca de verificación).</span><span class="sxs-lookup"><span data-stu-id="5d4db-301">Select **OK** (check mark symbol).</span></span>

    <span data-ttu-id="5d4db-302">Recibe un mensaje "Clúster completado".</span><span class="sxs-lookup"><span data-stu-id="5d4db-302">You receive a "Cluster Completed" message.</span></span>

<span data-ttu-id="5d4db-303">Ahora puede usar el elemento de menú **Picking de ventas** para elegir la cantidad restante.</span><span class="sxs-lookup"><span data-stu-id="5d4db-303">You can now use the **Sales Picking** menu item to pick the remaining quantity.</span></span> <span data-ttu-id="5d4db-304">A continuación, puede utilizar el elemento de menú **Carga de ventas** para mover los elementos desde la ubicación de almacenamiento provisional al muelle de carga.</span><span class="sxs-lookup"><span data-stu-id="5d4db-304">You can then use the **Sales loading** menu item to move the items from the staging location to the loading dock.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]