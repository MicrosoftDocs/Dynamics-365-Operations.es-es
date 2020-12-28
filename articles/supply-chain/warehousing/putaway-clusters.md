---
title: Clústeres de ubicación
description: Los grupos de almacenamiento ofrecen una forma de elegir varias placas al mismo tiempo y luego llevarlas a almacenamiento en diferentes ubicaciones. Pueden ser muy útiles para negocios minoristas, donde las placas de matrícula generalmente no son paletas llenas de inventario.
author: Mirzaab
manager: tfehr
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: 6a330ddccbd17c92443232fc8488e36a59235773
ms.sourcegitcommit: cfd84321fba38e02e270d361df369a536a48efa3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/11/2020
ms.locfileid: "4512339"
---
# <a name="putaway-clusters"></a><span data-ttu-id="6f13d-104">Clústeres de ubicación</span><span class="sxs-lookup"><span data-stu-id="6f13d-104">Putaway clusters</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6f13d-105">Los grupos de almacenamiento ofrecen una forma de elegir varias placas al mismo tiempo y luego llevarlas a almacenamiento en diferentes ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="6f13d-105">Putaway clusters offer a way to pick multiple license plates at the same time and then take them for putaway in different locations.</span></span> <span data-ttu-id="6f13d-106">Este proceso suele denominarse como *recorrido*.</span><span class="sxs-lookup"><span data-stu-id="6f13d-106">This process is often referred to as a *milk run*.</span></span> <span data-ttu-id="6f13d-107">Los clústeres de ubicación pueden ser muy útiles para negocios minoristas, donde las placas de matrícula generalmente no son paletas llenas de inventario.</span><span class="sxs-lookup"><span data-stu-id="6f13d-107">Putaway clusters can be very useful for retail businesses, where license plates typically aren't full pallets of inventory.</span></span> 

## <a name="turn-on-the-cluster-putaway-feature"></a><span data-ttu-id="6f13d-108">Activar la característica de ubicación de clúster</span><span class="sxs-lookup"><span data-stu-id="6f13d-108">Turn on the cluster putaway feature</span></span>

<span data-ttu-id="6f13d-109">Antes de poder usar esta característica debe estar activada en su sistema.</span><span class="sxs-lookup"><span data-stu-id="6f13d-109">Before you can use this feature, it must be turned on in your system.</span></span> <span data-ttu-id="6f13d-110">Los administradores pueden usar el espacio de trabajo [Administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de la característica y activarla si es necesario.</span><span class="sxs-lookup"><span data-stu-id="6f13d-110">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="6f13d-111">Allí, la característica se enumera de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="6f13d-111">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="6f13d-112">**Módulo:** *Gestión de almacén*</span><span class="sxs-lookup"><span data-stu-id="6f13d-112">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="6f13d-113">**Nombre de la función:** *Función de almacenamiento en grupo*</span><span class="sxs-lookup"><span data-stu-id="6f13d-113">**Feature name:** *Cluster putaway feature*</span></span>

## <a name="setup-for-the-example-scenario"></a><span data-ttu-id="6f13d-114">Configuración para el escenario de ejemplo</span><span class="sxs-lookup"><span data-stu-id="6f13d-114">Setup for the example scenario</span></span>

### <a name="cluster-profiles"></a><span data-ttu-id="6f13d-115">Perfiles de clúster</span><span class="sxs-lookup"><span data-stu-id="6f13d-115">Cluster profiles</span></span>

<span data-ttu-id="6f13d-116">El perfil del grupo de almacenamiento determina dónde irá un artículo, según la ubicación asignada al artículo en el momento de la recepción.</span><span class="sxs-lookup"><span data-stu-id="6f13d-116">The putaway cluster profile determines where an item will go, based on the location that is assigned to the item at the time of receipt.</span></span> <span data-ttu-id="6f13d-117">Si se requieren diferentes clústeres, se deben crear un clústeres de ubicación diferentes, uno para cada elemento del menú de dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="6f13d-117">If different clusters are required, different putaway clusters should be created, one for each mobile device menu item.</span></span>

1. <span data-ttu-id="6f13d-118">Vaya a **Administración de almacenes \> Configuración \> Dispositivo móvil \> Perfiles de clúster**.</span><span class="sxs-lookup"><span data-stu-id="6f13d-118">Go to **Warehouse management \> Setup \> Mobile device \> Cluster profiles**.</span></span>
1. <span data-ttu-id="6f13d-119">En el panel de acciones, haga clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="6f13d-119">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="6f13d-120">Establezca los siguientes valores en la vista **Encabezado**:</span><span class="sxs-lookup"><span data-stu-id="6f13d-120">In the **Header** view, set the following values:</span></span>

    - <span data-ttu-id="6f13d-121">**ID de perfil de clúster de almacenamiento:** *Almacenamiento en clúster*</span><span class="sxs-lookup"><span data-stu-id="6f13d-121">**Putaway cluster profile ID:** *Cluster putaway*</span></span>
    - <span data-ttu-id="6f13d-122">**Nombre de ID de perfil de clúster de almacenamiento:** *Almacenamiento en clúster*</span><span class="sxs-lookup"><span data-stu-id="6f13d-122">**Putaway cluster profile ID Name:** *Cluster putaway*</span></span>
    - <span data-ttu-id="6f13d-123">**Tipo de clúster:** *Ubicación*</span><span class="sxs-lookup"><span data-stu-id="6f13d-123">**Cluster type:** *Putaway*</span></span>
    - <span data-ttu-id="6f13d-124">**Número de secuencia:** acepte el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="6f13d-124">**Sequence number:** Accept the default value.</span></span>

1. <span data-ttu-id="6f13d-125">Seleccione **Guardar** para tener disponibles los campos necesarios en la ficha desplegable **General**.</span><span class="sxs-lookup"><span data-stu-id="6f13d-125">Select **Save** to make the required fields on the **General** FastTab available.</span></span>
1. <span data-ttu-id="6f13d-126">En la ficha desplegable **General**, establezca los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="6f13d-126">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="6f13d-127">**Tiempo de asignación de clústeres:** *Al recibir*</span><span class="sxs-lookup"><span data-stu-id="6f13d-127">**Cluster assignment timing:** *At receipt*</span></span>

        <span data-ttu-id="6f13d-128">Este campo define si el grupo de almacenamiento debe asignarse inmediatamente cuando se recibe el inventario, o si debe clasificarse más tarde.</span><span class="sxs-lookup"><span data-stu-id="6f13d-128">This field defines whether the putaway cluster should be assigned immediately when the inventory is received, or whether it should be sorted later.</span></span>

    - <span data-ttu-id="6f13d-129">**Regla de asignación de clústeres:** *Manual*</span><span class="sxs-lookup"><span data-stu-id="6f13d-129">**Cluster assignment rule:** *Manual*</span></span>

        <span data-ttu-id="6f13d-130">Este campo define si la asignación de clúster se debería determinar automáticamente por el sistema o hacer manualmente por el usuario.</span><span class="sxs-lookup"><span data-stu-id="6f13d-130">This field defines whether the cluster assignment should be determined automatically by the system or manually by the user.</span></span>

    - <span data-ttu-id="6f13d-131">**Código de directiva:** deje en blanco este campo.</span><span class="sxs-lookup"><span data-stu-id="6f13d-131">**Directive code:** Leave this field blank.</span></span>
    - <span data-ttu-id="6f13d-132">**Ubicación del clúster de almacenamiento:** *Recepción*</span><span class="sxs-lookup"><span data-stu-id="6f13d-132">**Putaway cluster locate:** *Receipt*</span></span>

        <span data-ttu-id="6f13d-133">Los siguientes valores están disponibles:</span><span class="sxs-lookup"><span data-stu-id="6f13d-133">The following values are available:</span></span>

        - <span data-ttu-id="6f13d-134">**Recepción**: una ubicación se encuentra inmediatamente durante la recepción.</span><span class="sxs-lookup"><span data-stu-id="6f13d-134">**Receipt** – A location is found immediately during receipt.</span></span>
        - <span data-ttu-id="6f13d-135">**Cierre del clúster**: la ubicación encontrada cuando se cierra el clúster.</span><span class="sxs-lookup"><span data-stu-id="6f13d-135">**Cluster close** – A location is found when the cluster is closed.</span></span>
        - <span data-ttu-id="6f13d-136">**Dirigido por el usuario**: se encuentra una ubicación cuando se elige la placa de matrícula del grupo para guardarla.</span><span class="sxs-lookup"><span data-stu-id="6f13d-136">**User directed** – A location is found when the license plate is picked from the cluster for putaway.</span></span> <span data-ttu-id="6f13d-137">En este caso, no se especifica ninguna ubicación cuando se crea el trabajo de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="6f13d-137">In this case, no location is specified when the putaway work is created.</span></span> <span data-ttu-id="6f13d-138">Durante el almacenamiento en sí, el usuario debe escanear la matrícula o la identificación del trabajo para iniciar el paso de colocación.</span><span class="sxs-lookup"><span data-stu-id="6f13d-138">During the putaway itself, the user must scan the license plate or work ID to initiate the put step.</span></span> <span data-ttu-id="6f13d-139">Luego, el sistema encuentra la ubicación de colocación nuevamente y le dice al usuario dónde colocar la cantidad recolectada.</span><span class="sxs-lookup"><span data-stu-id="6f13d-139">The system then finds the put location again and tells the user where to put the picked quantity.</span></span>

    - <span data-ttu-id="6f13d-140">**Clúster de almacenamiento por usuario:** *No*</span><span class="sxs-lookup"><span data-stu-id="6f13d-140">**Putaway cluster per user:** *No*</span></span>

        <span data-ttu-id="6f13d-141">Este campo define si cada clúster debe ser único por usuario cuando los clústeres se asignan automáticamente.</span><span class="sxs-lookup"><span data-stu-id="6f13d-141">This field defines whether each cluster should be unique per user when clusters are automatically assigned.</span></span> <span data-ttu-id="6f13d-142">Está disponible solo cuando el campo **Regla de asignación de clústeres** está configurado en *Automático*.</span><span class="sxs-lookup"><span data-stu-id="6f13d-142">It's available only when the **Cluster assignment rule** field is set to *Automatic*.</span></span>

    - <span data-ttu-id="6f13d-143">**Restricción de unidad:** deje este campo en blanco.</span><span class="sxs-lookup"><span data-stu-id="6f13d-143">**Unit restriction:** Leave this field blank.</span></span>

        <span data-ttu-id="6f13d-144">Este campo define la unidad que se debe recibir para que el perfil sea válido.</span><span class="sxs-lookup"><span data-stu-id="6f13d-144">This field defines the unit that must be received for the profile to be valid.</span></span> <span data-ttu-id="6f13d-145">Si se deja en blanco, todas las unidades son válidas.</span><span class="sxs-lookup"><span data-stu-id="6f13d-145">If it's left blank, all units are valid.</span></span>

    - <span data-ttu-id="6f13d-146">**Rotura de la unidad de trabajo:** *Individual*</span><span class="sxs-lookup"><span data-stu-id="6f13d-146">**Work unit break:** *Individual*</span></span>

        <span data-ttu-id="6f13d-147">Este campo define si todo el inventario debe consolidarse (mediante el uso de la identificación del grupo y la placa) en una placa cuando un grupo está cerrado, y si debe guardarse como una sola placa o por separado en las placas que estaban recibido.</span><span class="sxs-lookup"><span data-stu-id="6f13d-147">This field defines whether all inventory should be consolidated (by using the cluster ID and the license plate) onto one license plate when a cluster is closed, and whether it should be put away as a single license plate or separately on the license plates that were received.</span></span> <span data-ttu-id="6f13d-148">Este campo no está disponible cuando el campo **Ubicación del clúster de almacenamiento** el campo está configurado en *Recibo*.</span><span class="sxs-lookup"><span data-stu-id="6f13d-148">This field is unavailable when the **Putaway cluster locate** field is set to *Receipt*.</span></span>

    - <span data-ttu-id="6f13d-149">**El clúster persiste como matrícula principal:** *No*</span><span class="sxs-lookup"><span data-stu-id="6f13d-149">**Cluster persists as Parent License Plate:** *No*</span></span>

        <span data-ttu-id="6f13d-150">Si esta opción se establece en *Sí*, cuando se completa el paso de colocación, la identificación del grupo se convertirá en una placa de matrícula principal y todos los elementos de la identificación de grupo se vincularán a esa placa de matrícula principal.</span><span class="sxs-lookup"><span data-stu-id="6f13d-150">If this option is set to *Yes*, when the put step is completed, the cluster ID will become a parent license plate, and all items on the cluster ID will be linked to that parent license plate.</span></span>

1. <span data-ttu-id="6f13d-151">En la ficha desplegable **Clasificación de grupos**, puede definir criterios de clasificación de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="6f13d-151">On the **Cluster sorting** FastTab, you can define putaway sorting criteria.</span></span> <span data-ttu-id="6f13d-152">Seleccione **Nuevo** en la barra de herramienats para agregar una línea y después establezca los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="6f13d-152">Select **New** on the toolbar to add a line, and then set the following values:</span></span>

    - <span data-ttu-id="6f13d-153">**Número de secuencia:** acepte el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="6f13d-153">**Sequence number:** Accept the default value.</span></span>
    - <span data-ttu-id="6f13d-154">**Nombre de campo:** introduzca *WMSLocationId*.</span><span class="sxs-lookup"><span data-stu-id="6f13d-154">**Field name:** *WMSLocationId*</span></span>

        <span data-ttu-id="6f13d-155">Este campo define el campo que esta línea debe usar como criterio de clasificación.</span><span class="sxs-lookup"><span data-stu-id="6f13d-155">This field defines the field that this line should use as a sorting criterion.</span></span>

    - <span data-ttu-id="6f13d-156">**Clasificación:** *Ascendente*</span><span class="sxs-lookup"><span data-stu-id="6f13d-156">**Sorting:** *Ascending*</span></span>

        <span data-ttu-id="6f13d-157">Este campo define si la ordenación se debe realizar en orden ascendente o descendente.</span><span class="sxs-lookup"><span data-stu-id="6f13d-157">This field defines whether sorting should be done in ascending or descending order.</span></span>

1. <span data-ttu-id="6f13d-158">En la ficha desplegable **Plantilla de trabajo de clúster**, seleccione **Nuevo** en la barra de herramientas para agregar una línea y luego establecer los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="6f13d-158">On the **Cluster work template** FastTab, select **New** on the toolbar to add a line, and then set the following values:</span></span>

    - <span data-ttu-id="6f13d-159">**Tipo de orden de trabajo**: *Pedidos de compra*</span><span class="sxs-lookup"><span data-stu-id="6f13d-159">**Work order type:** *Purchase orders*</span></span>
    - <span data-ttu-id="6f13d-160">**Plantilla de trabajo:** *PO directa 61*</span><span class="sxs-lookup"><span data-stu-id="6f13d-160">**Work template:** *61 PO Direct*</span></span>

1. <span data-ttu-id="6f13d-161">En el panel de acciones, seleccione **Salvar** y luego seleccione **Editar consulta**.</span><span class="sxs-lookup"><span data-stu-id="6f13d-161">On the Action Pane, select **Save**, and then select **Edit query**.</span></span>
1. <span data-ttu-id="6f13d-162">En el cuadro de diálogo **Ubicación de clúster**, en la pestaña **Rango**, seleccione **Agregar** para añadir una línea a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="6f13d-162">In the **Cluster putaway** dialog box, on the **Range** tab, select **Add** to add a second line to the query.</span></span> <span data-ttu-id="6f13d-163">Luego actualice las líneas de consulta como se muestra en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="6f13d-163">Then update the query lines as shown in the following table.</span></span>

    | <span data-ttu-id="6f13d-164">Tabla</span><span class="sxs-lookup"><span data-stu-id="6f13d-164">Table</span></span> | <span data-ttu-id="6f13d-165">Tabla derivada</span><span class="sxs-lookup"><span data-stu-id="6f13d-165">Derived table</span></span> | <span data-ttu-id="6f13d-166">Campo</span><span class="sxs-lookup"><span data-stu-id="6f13d-166">Field</span></span> | <span data-ttu-id="6f13d-167">Criterios</span><span class="sxs-lookup"><span data-stu-id="6f13d-167">Criteria</span></span> |
    |---|---|---|---|
    | <span data-ttu-id="6f13d-168">Trabajo</span><span class="sxs-lookup"><span data-stu-id="6f13d-168">Work</span></span> | <span data-ttu-id="6f13d-169">Trabajo</span><span class="sxs-lookup"><span data-stu-id="6f13d-169">Work</span></span> | <span data-ttu-id="6f13d-170">Almacén</span><span class="sxs-lookup"><span data-stu-id="6f13d-170">Warehouse</span></span> | <span data-ttu-id="6f13d-171">*61*</span><span class="sxs-lookup"><span data-stu-id="6f13d-171">*61*</span></span> |
    | <span data-ttu-id="6f13d-172">Trabajo</span><span class="sxs-lookup"><span data-stu-id="6f13d-172">Work</span></span> | <span data-ttu-id="6f13d-173">Trabajo</span><span class="sxs-lookup"><span data-stu-id="6f13d-173">Work</span></span> | <span data-ttu-id="6f13d-174">Id. de trabajo</span><span class="sxs-lookup"><span data-stu-id="6f13d-174">Work ID</span></span> | <span data-ttu-id="6f13d-175">Deje este campo en blanco.</span><span class="sxs-lookup"><span data-stu-id="6f13d-175">Leave this field blank.</span></span> |

1. <span data-ttu-id="6f13d-176">Seleccione **Aceptar** para guardar la consulta y cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="6f13d-176">Select **OK** to save the query and close the dialog box.</span></span>
1. <span data-ttu-id="6f13d-177">En el la panel de acciones, seleccione **Guardar** y después cierre la página.</span><span class="sxs-lookup"><span data-stu-id="6f13d-177">On the Action Pane, select **Save**, and close the page.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6f13d-178">Campos en el perfil del clúster que aparecen atenuados cuando **Generar ID de clúster** se establece en *Sí* no están disponibles y no se tendrán en cuenta cuando se utilice esta función.</span><span class="sxs-lookup"><span data-stu-id="6f13d-178">Fields in the cluster profile that appear dimmed when **Generate cluster ID** is set to *Yes* are unavailable and won't be considered when this feature is used.</span></span>

### <a name="mobile-device-menu-items"></a><span data-ttu-id="6f13d-179">Elementos de menú del dispositivo móvil</span><span class="sxs-lookup"><span data-stu-id="6f13d-179">Mobile device menu items</span></span>

<span data-ttu-id="6f13d-180">Hay dos nuevos elementos del menú del dispositivo móvil disponibles para esta función.</span><span class="sxs-lookup"><span data-stu-id="6f13d-180">Two new mobile device menu items are available for this feature.</span></span> <span data-ttu-id="6f13d-181">El elemento de menú **Recibir y ordenar clúster** se utiliza para clasificar el inventario recibido en un grupo de almacenamiento al recibirlo.</span><span class="sxs-lookup"><span data-stu-id="6f13d-181">The **Receive and sort cluster** menu item is used to sort the received inventory into a putaway cluster upon receipt.</span></span> <span data-ttu-id="6f13d-182">El elemento de menú **Ubicación de clúster** se utiliza para guardar el clúster después de haber sido asignado.</span><span class="sxs-lookup"><span data-stu-id="6f13d-182">The **Cluster putaway** menu item is used to put the cluster away after it has been assigned.</span></span>

#### <a name="receive-and-sort-cluster"></a><span data-ttu-id="6f13d-183">Recibir y ordenar clúster</span><span class="sxs-lookup"><span data-stu-id="6f13d-183">Receive and sort cluster</span></span>

<span data-ttu-id="6f13d-184">Cree un nuevo elemento de menú de dispositivo móvil para recibir inventario y clasificar en un grupo.</span><span class="sxs-lookup"><span data-stu-id="6f13d-184">Create a new mobile device menu item for receiving inventory and sorting into a cluster.</span></span> <span data-ttu-id="6f13d-185">Este elemento del menú creará trabajo entrante después de que se reciba el inventario, lo que indica que el elemento del menú de recepción se utilizará para los grupos de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="6f13d-185">This menu item will create inbound work after inventory is received, which indicates that the receiving menu item will be used for putaway clusters.</span></span>

> [!NOTE]
> <span data-ttu-id="6f13d-186">El elemento del menú **Recibir y ordenar clúster** se puede utilizar con los siguientes elementos del menú de recepción:</span><span class="sxs-lookup"><span data-stu-id="6f13d-186">The **Receive and sort cluster** menu item can be used with the following receiving menu items:</span></span>
>
> - <span data-ttu-id="6f13d-187">Recepción de línea del pedido de compra</span><span class="sxs-lookup"><span data-stu-id="6f13d-187">Purchase order line receiving</span></span>
> - <span data-ttu-id="6f13d-188">Recepción de artículo del pedido de compra</span><span class="sxs-lookup"><span data-stu-id="6f13d-188">Purchase order item receiving</span></span>
> - <span data-ttu-id="6f13d-189">Recepción de artículo de carga</span><span class="sxs-lookup"><span data-stu-id="6f13d-189">Load item receiving</span></span>

1. <span data-ttu-id="6f13d-190">Vaya a **Administración de almacenes \> Configurar \> Dispositivo móvil \> Elementos de menú del dispositivo móvil**.</span><span class="sxs-lookup"><span data-stu-id="6f13d-190">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="6f13d-191">En el panel de acciones, haga clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="6f13d-191">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="6f13d-192">Establezca los siguientes valores en la vista **Encabezado**:</span><span class="sxs-lookup"><span data-stu-id="6f13d-192">In the **Header** view, set the following values:</span></span>

    - <span data-ttu-id="6f13d-193">**Nombre del elemento del menú:** *Recibir y ordenar clúster*</span><span class="sxs-lookup"><span data-stu-id="6f13d-193">**Menu item name:** *Receive and sort cluster*</span></span>
    - <span data-ttu-id="6f13d-194">**Título:** *Recibir y ordenar clúster*</span><span class="sxs-lookup"><span data-stu-id="6f13d-194">**Title:** *Receive and sort cluster*</span></span>
    - <span data-ttu-id="6f13d-195">**Modo:** *Trabajo*</span><span class="sxs-lookup"><span data-stu-id="6f13d-195">**Mode:** *Work*</span></span>
    - <span data-ttu-id="6f13d-196">**Usar trabajo existente:** *No*</span><span class="sxs-lookup"><span data-stu-id="6f13d-196">**Use existing work:** *No*</span></span>

1. <span data-ttu-id="6f13d-197">En la ficha desplegable **General**, establezca los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="6f13d-197">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="6f13d-198">**Proceso de creación de trabajo**: *Recepción de artículos de pedido de compra*</span><span class="sxs-lookup"><span data-stu-id="6f13d-198">**Work creation process:** *Purchase order item receiving*</span></span>
    - <span data-ttu-id="6f13d-199">**Generar matrícula de entidad de almacén:** *Sí*</span><span class="sxs-lookup"><span data-stu-id="6f13d-199">**Generate license plate:** *Yes*</span></span>
    - <span data-ttu-id="6f13d-200">**Asignar clúster de almacenamiento:** *Sí*</span><span class="sxs-lookup"><span data-stu-id="6f13d-200">**Assign putaway cluster:** *Yes*</span></span>

        > [!NOTE]
        > <span data-ttu-id="6f13d-201">La opción **Asignar clúster de almacenamiento** está disponible solo para la actividad *Proceso de creación de obra* para la recepción.</span><span class="sxs-lookup"><span data-stu-id="6f13d-201">The **Assign putaway cluster** option is available only for the one-step *Work creation process* activity for receiving.</span></span>

    <span data-ttu-id="6f13d-202">Acepte los valores predeterminados del resto de campos.</span><span class="sxs-lookup"><span data-stu-id="6f13d-202">Accept the default values for the remaining fields.</span></span>

1. <span data-ttu-id="6f13d-203">En el panel Acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="6f13d-203">On the Action Pane, select **Save**.</span></span>

#### <a name="cluster-putaway"></a><span data-ttu-id="6f13d-204">Ubicación de clúster</span><span class="sxs-lookup"><span data-stu-id="6f13d-204">Cluster putaway</span></span>

<span data-ttu-id="6f13d-205">Cree un nuevo elemento de menú de dispositivo móvil para guardar el clúster después de que se haya asignado.</span><span class="sxs-lookup"><span data-stu-id="6f13d-205">Create a new mobile device menu item for putting the cluster away after it has been assigned.</span></span>

1. <span data-ttu-id="6f13d-206">Vaya a **Administración de almacenes \> Configurar \> Dispositivo móvil \> Elementos de menú del dispositivo móvil**.</span><span class="sxs-lookup"><span data-stu-id="6f13d-206">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="6f13d-207">En el panel de acciones, haga clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="6f13d-207">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="6f13d-208">Establezca los siguientes valores en la vista **Encabezado**:</span><span class="sxs-lookup"><span data-stu-id="6f13d-208">In the **Header** view, set the following values:</span></span>

    - <span data-ttu-id="6f13d-209">**Nombre del elemento del menú**: *Ubicación de clúster*</span><span class="sxs-lookup"><span data-stu-id="6f13d-209">**Menu item name:** *Cluster putaway*</span></span>
    - <span data-ttu-id="6f13d-210">**Título:** *Almacenamiento de clúster*</span><span class="sxs-lookup"><span data-stu-id="6f13d-210">**Title:** *Cluster putaway*</span></span>
    - <span data-ttu-id="6f13d-211">**Modo:** *Trabajo*</span><span class="sxs-lookup"><span data-stu-id="6f13d-211">**Mode:** *Work*</span></span>
    - <span data-ttu-id="6f13d-212">**Usar trabajo existente:** *Sí*</span><span class="sxs-lookup"><span data-stu-id="6f13d-212">**Use existing work:** *Yes*</span></span>

1. <span data-ttu-id="6f13d-213">En la ficha desplegable **General**, establezca el campo **Dirigido por** en *Ubicación de clúster*.</span><span class="sxs-lookup"><span data-stu-id="6f13d-213">On the **General** FastTab, set the **Directed by** field to *Cluster putaway*.</span></span> <span data-ttu-id="6f13d-214">Acepte los valores predeterminados del resto de campos.</span><span class="sxs-lookup"><span data-stu-id="6f13d-214">Accept the default values for the remaining fields.</span></span>
1. <span data-ttu-id="6f13d-215">En la ficha desplegable **Clases de trabajo**, configure la clase de trabajo válida para este elemento de menú de dispositivo móvil:</span><span class="sxs-lookup"><span data-stu-id="6f13d-215">On the **Work classes** FastTab, set up the valid work class for this mobile device menu item:</span></span>

    - <span data-ttu-id="6f13d-216">**Id. de la clase de trabajo**: *Compra*</span><span class="sxs-lookup"><span data-stu-id="6f13d-216">**Work class ID:** *Purchase*</span></span>
    - <span data-ttu-id="6f13d-217">**Tipo de orden de trabajo**: *Pedidos de compra*</span><span class="sxs-lookup"><span data-stu-id="6f13d-217">**Work order type:** *Purchase orders*</span></span>

1. <span data-ttu-id="6f13d-218">En el panel Acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="6f13d-218">On the Action Pane, select **Save**.</span></span>

### <a name="mobile-device-menu"></a><span data-ttu-id="6f13d-219">Menú del dispositivo móvil</span><span class="sxs-lookup"><span data-stu-id="6f13d-219">Mobile device menu</span></span>

<span data-ttu-id="6f13d-220">Agregue los elementos del menú que acaba de crear al menú de entrada de la aplicación móvil.</span><span class="sxs-lookup"><span data-stu-id="6f13d-220">Add the menu items that you just created to the inbound menu of the mobile app.</span></span>

1. <span data-ttu-id="6f13d-221">Vaya a **Administración de almacenes \> Configuración \> Dispositivo móvil \> Menú del dispositivo móvil**.</span><span class="sxs-lookup"><span data-stu-id="6f13d-221">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu**.</span></span>
1. <span data-ttu-id="6f13d-222">En el panel Acciones, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="6f13d-222">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="6f13d-223">En la lista de menús, seleccione **Entrante**.</span><span class="sxs-lookup"><span data-stu-id="6f13d-223">In the menu list, select **Inbound**.</span></span>
1. <span data-ttu-id="6f13d-224">En la lista **Menús disponibles y elementos de menú**, busque y seleccione **Recibir y ordenar clúster**.</span><span class="sxs-lookup"><span data-stu-id="6f13d-224">In the **Available menus and menu items** list, find and select **Receive and sort cluster**.</span></span>
1. <span data-ttu-id="6f13d-225">Seleccione el botón de flecha derecha para mover el elemento de menú seleccionado a la lista **Estructura del menú**.</span><span class="sxs-lookup"><span data-stu-id="6f13d-225">Select the right arrow button to move the selected menu item to the **Menu structure** list.</span></span>
1. <span data-ttu-id="6f13d-226">Utilice el botón de flecha hacia arriba o flecha hacia abajo para mover el elemento del menú a la posición deseada en el menú.</span><span class="sxs-lookup"><span data-stu-id="6f13d-226">Use the up arrow or down arrow button to move the menu item into the desired position in the menu.</span></span>
1. <span data-ttu-id="6f13d-227">En el panel Acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="6f13d-227">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="6f13d-228">Repita los pasos del 4 al 7 para agregar los elementos de menú restantes:</span><span class="sxs-lookup"><span data-stu-id="6f13d-228">Repeat steps 4 through 7 to add the remaining menu items:</span></span>

    - <span data-ttu-id="6f13d-229">Asignar clúster</span><span class="sxs-lookup"><span data-stu-id="6f13d-229">Assign cluster</span></span>
    - <span data-ttu-id="6f13d-230">Ubicación de clúster</span><span class="sxs-lookup"><span data-stu-id="6f13d-230">Cluster putaway</span></span>

## <a name="example-scenario"></a><span data-ttu-id="6f13d-231">Supuesto de ejemplo</span><span class="sxs-lookup"><span data-stu-id="6f13d-231">Example scenario</span></span>

<span data-ttu-id="6f13d-232">Este escenario simula el procesamiento del clúster de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="6f13d-232">This scenario simulates putaway cluster processing.</span></span>

### <a name="create-a-purchase-order"></a><span data-ttu-id="6f13d-233">Crear un pedido de compra</span><span class="sxs-lookup"><span data-stu-id="6f13d-233">Create a purchase order</span></span>

1. <span data-ttu-id="6f13d-234">Vaya a **Proveedores \> Pedidos de compra \> Todos los pedidos de compra**.</span><span class="sxs-lookup"><span data-stu-id="6f13d-234">Go to **Accounts payable \> Purchase orders \> All purchase orders**.</span></span>
1. <span data-ttu-id="6f13d-235">En el panel de acciones, haga clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="6f13d-235">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="6f13d-236">En el cuadro de diálogo **Crear pedido de compras**, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="6f13d-236">In the **Create purchase order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="6f13d-237">**Cuenta del proveedor:** *1001*</span><span class="sxs-lookup"><span data-stu-id="6f13d-237">**Vendor account:** *1001*</span></span>
    - <span data-ttu-id="6f13d-238">**Almacén**: *61*</span><span class="sxs-lookup"><span data-stu-id="6f13d-238">**Warehouse:** *61*</span></span>

1. <span data-ttu-id="6f13d-239">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6f13d-239">Select **OK**.</span></span>

    <span data-ttu-id="6f13d-240">Aparece la página **Todos los pedidos de compra**.</span><span class="sxs-lookup"><span data-stu-id="6f13d-240">The **All purchase orders** page appears.</span></span>

1. <span data-ttu-id="6f13d-241">En la página **Todas las órdenes de compra**, en la ficha desplegable **Líneas de orden de compra**, use el botón **Añadir línea** para agregar las siguientes líneas:</span><span class="sxs-lookup"><span data-stu-id="6f13d-241">On the **All purchase orders** page, on the **Purchase order lines** FastTab, use the **Add line** button to add the following lines:</span></span>

    - <span data-ttu-id="6f13d-242">Línea de pedido de compra 1:</span><span class="sxs-lookup"><span data-stu-id="6f13d-242">Purchase order line 1:</span></span>

        - <span data-ttu-id="6f13d-243">**Código de artículo:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="6f13d-243">**Item number:** *A0001*</span></span>
        - <span data-ttu-id="6f13d-244">**Cantidad:** *10*</span><span class="sxs-lookup"><span data-stu-id="6f13d-244">**Quantity:** *10*</span></span>

    - <span data-ttu-id="6f13d-245">Línea de pedido de compra 2:</span><span class="sxs-lookup"><span data-stu-id="6f13d-245">Purchase order line 2:</span></span>

        - <span data-ttu-id="6f13d-246">**Código de artículo:** *A0002*</span><span class="sxs-lookup"><span data-stu-id="6f13d-246">**Item number:** *A0002*</span></span>
        - <span data-ttu-id="6f13d-247">**Cantidad:** *20*</span><span class="sxs-lookup"><span data-stu-id="6f13d-247">**Quantity:** *20*</span></span>

    - <span data-ttu-id="6f13d-248">Línea de pedido de compra 3:</span><span class="sxs-lookup"><span data-stu-id="6f13d-248">Purchase order line 3:</span></span>

        - <span data-ttu-id="6f13d-249">**Código de artículo:** *M9215*</span><span class="sxs-lookup"><span data-stu-id="6f13d-249">**Item number:** *M9215*</span></span>
        - <span data-ttu-id="6f13d-250">**Cantidad:** *30*</span><span class="sxs-lookup"><span data-stu-id="6f13d-250">**Quantity:** *30*</span></span>

1. <span data-ttu-id="6f13d-251">En el panel Acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="6f13d-251">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="6f13d-252">Anote el número del pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="6f13d-252">Make a note of the purchase order number.</span></span>

### <a name="receive-inventory-and-put-it-away-from-the-mobile-device"></a><span data-ttu-id="6f13d-253">Reciba inventario y guárdelo fuera del dispositivo móvil</span><span class="sxs-lookup"><span data-stu-id="6f13d-253">Receive inventory and put it away from the mobile device</span></span>

#### <a name="receive-and-sort-the-inventory-into-a-cluster"></a><span data-ttu-id="6f13d-254">Reciba y clasifique el inventario en un grupo</span><span class="sxs-lookup"><span data-stu-id="6f13d-254">Receive and sort the inventory into a cluster</span></span>

1. <span data-ttu-id="6f13d-255">Inicie sesión en la aplicación de almacén como un usuario configurado para el almacén *61*.</span><span class="sxs-lookup"><span data-stu-id="6f13d-255">Sign in to the warehouse app as a user who is set up for warehouse *61*.</span></span>
1. <span data-ttu-id="6f13d-256">En el menú principal, seleccione **Entrada**.</span><span class="sxs-lookup"><span data-stu-id="6f13d-256">On the main menu, select **Inbound**.</span></span>
1. <span data-ttu-id="6f13d-257">En el menú **Entrante**, seleccione **Recibir y ordenar clúster**.</span><span class="sxs-lookup"><span data-stu-id="6f13d-257">On the **Inbound** menu, select **Receive and sort cluster**.</span></span>
1. <span data-ttu-id="6f13d-258">En el campo **Ponum**, introduzca el número de orden de compra.</span><span class="sxs-lookup"><span data-stu-id="6f13d-258">In the **Ponum** field, enter the purchase order number.</span></span>
1. <span data-ttu-id="6f13d-259">Seleccione **Aceptar** (botón de de marca de verificación).</span><span class="sxs-lookup"><span data-stu-id="6f13d-259">Select **OK** (the check mark button).</span></span>
1. <span data-ttu-id="6f13d-260">Seleccione el campo **Artículo**, introduzca el número de artículo *A0001* y seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6f13d-260">Select the **Item** field, enter item number *A0001*, and then select **OK**.</span></span>
1. <span data-ttu-id="6f13d-261">Seleccione el campo **Cant.**, ingrese *10* utilizando el teclado numérico y luego seleccione el botón de marca de verificación.</span><span class="sxs-lookup"><span data-stu-id="6f13d-261">Select the **Qty** field, enter *10* by using the number pad, and then select the check mark button.</span></span>
1. <span data-ttu-id="6f13d-262">En la página de tareas **Cant.**, seleccione **Aceptar** (botón de marca de verificación) para confirmar la cantidad que ingresó.</span><span class="sxs-lookup"><span data-stu-id="6f13d-262">On the **Qty** task page, select **OK** (the check mark button) to confirm the quantity that you entered.</span></span>
1. <span data-ttu-id="6f13d-263">En la página de tareas **Artículo**, seleccione **Aceptar** para confirmar que se introdujo el artículo *A0001*.</span><span class="sxs-lookup"><span data-stu-id="6f13d-263">On the **Item** task page, select **OK** to confirm that item *A0001* was entered.</span></span>
1. <span data-ttu-id="6f13d-264">Seleccione el campo **ID de clúster** e ingrese un valor para asignar un ID para el clúster que está creando.</span><span class="sxs-lookup"><span data-stu-id="6f13d-264">Select the **Cluster ID** field, and enter a value to assign an ID for the cluster that you're creating.</span></span>

    <span data-ttu-id="6f13d-265">La identificación que ingrese aquí se utilizará cuando se reciban los dos artículos restantes en la orden de compra.</span><span class="sxs-lookup"><span data-stu-id="6f13d-265">The ID that you enter here will be used when the two remaining items on the purchase order are received.</span></span>

1. <span data-ttu-id="6f13d-266">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6f13d-266">Select **OK**.</span></span>

    <span data-ttu-id="6f13d-267">La página de tareas **Ponum** aparece y muestra un mensaje de "Trabajo completado".</span><span class="sxs-lookup"><span data-stu-id="6f13d-267">The **Ponum** task page appears and shows a "Work completed" message.</span></span>

    <span data-ttu-id="6f13d-268">Ahora el artículo *A0001* ha sido recibido en la ubicación *RECV* y se asigna al ID de clúster que ingresó en el paso 10.</span><span class="sxs-lookup"><span data-stu-id="6f13d-268">Item *A0001* has now been received into the *RECV* location and assigned to the cluster ID that you entered in step 10.</span></span>

1. <span data-ttu-id="6f13d-269">Repita los pasos del 4 al 11 para recibir los dos artículos restantes de la orden de compra y asígnelos al ID del clúster:</span><span class="sxs-lookup"><span data-stu-id="6f13d-269">Repeat steps 4 through 11 to receive the remaining two items from the purchase order and assign them to the cluster ID:</span></span>

    - <span data-ttu-id="6f13d-270">Una cantidad de *20* para el artículo *A0002*</span><span class="sxs-lookup"><span data-stu-id="6f13d-270">A quantity of *20* for item *A0002*</span></span>
    - <span data-ttu-id="6f13d-271">Una cantidad de *30* para el artículo *M9215*</span><span class="sxs-lookup"><span data-stu-id="6f13d-271">A quantity of *30* for item *M9215*</span></span>

#### <a name="close-the-cluster"></a><span data-ttu-id="6f13d-272">Cerrar el clúster</span><span class="sxs-lookup"><span data-stu-id="6f13d-272">Close the cluster</span></span>

<span data-ttu-id="6f13d-273">Antes de que los elementos del clúster se puedan guardar, el clúster debe cerrarse.</span><span class="sxs-lookup"><span data-stu-id="6f13d-273">Before the items in the cluster can be put away, the cluster must be closed.</span></span>

1. <span data-ttu-id="6f13d-274">En Supply Chain Management, vaya a **Gestión de almacenes \> Trabajo \> Saliente \> Grupos de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="6f13d-274">In Supply Chain Management, go to **Warehouse management \> Work \> Outbound \> Work clusters**.</span></span>
1. <span data-ttu-id="6f13d-275">En la página **Grupos de trabajo**, en la sección **Grupo de trabajo**, busque el **ID de clúster** para el ID de clúster que ingresó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="6f13d-275">On the **Work clusters** page, in the **Work cluster** section, search the **Cluster ID** field for the cluster ID that you entered earlier.</span></span>
1. <span data-ttu-id="6f13d-276">Si no se muestra el clúster, es posible que ya se haya cerrado.</span><span class="sxs-lookup"><span data-stu-id="6f13d-276">If the cluster isn't shown, it might already have been closed.</span></span> <span data-ttu-id="6f13d-277">Para determinar si el clúster estaba cerrado, seleccione la casilla de verificación **Mostrar trabajo cerrado** y busque el ID de clúster que ingresó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="6f13d-277">To determine whether the cluster was closed, select the **Show closed work** check box, and search for the cluster ID that you entered earlier.</span></span> <span data-ttu-id="6f13d-278">Luego siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="6f13d-278">Then follow one of these steps:</span></span>

    - <span data-ttu-id="6f13d-279">Si el clúster se ha cerrado, omita los pasos restantes de este procedimiento y continúe con el siguiente procedimiento, [Guardar el clúster](#put-the-cluster-away).</span><span class="sxs-lookup"><span data-stu-id="6f13d-279">If the cluster has been closed, skip the remaining steps of this procedure, and move on to the next procedure, [Put the cluster away](#put-the-cluster-away).</span></span>
    - <span data-ttu-id="6f13d-280">Si el clúster no se ha cerrado, siga los pasos restantes de este procedimiento para cerrarlo manualmente.</span><span class="sxs-lookup"><span data-stu-id="6f13d-280">If the cluster hasn't been closed, follow the remaining steps of this procedure to manually close the cluster.</span></span> <span data-ttu-id="6f13d-281">Después vaya al procedimiento siguiente.</span><span class="sxs-lookup"><span data-stu-id="6f13d-281">Then move on to the next procedure.</span></span>

1. <span data-ttu-id="6f13d-282">En la sección **Grupo de trabajo**, seleccione el ID de clúster que ingresó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="6f13d-282">In the **Work cluster** section, select the cluster ID that you entered earlier.</span></span>
1. <span data-ttu-id="6f13d-283">En el panel de acciones, seleccione **Cerrar clúster**.</span><span class="sxs-lookup"><span data-stu-id="6f13d-283">On the Action Pane, select **Close cluster**.</span></span>

    <span data-ttu-id="6f13d-284">Una vez cerrado el clúster, ya no se muestra en la sección **Grupo de trabajo** (a menos que la casilla de verificación **Mostrar trabajo cerrado** esté seleccionada).</span><span class="sxs-lookup"><span data-stu-id="6f13d-284">After the cluster has been closed, it's no longer shown in the **Work cluster** section (unless the **Show closed work** check box is selected).</span></span>

#### <a name="put-the-cluster-away"></a><span data-ttu-id="6f13d-285">Guardar el clúster</span><span class="sxs-lookup"><span data-stu-id="6f13d-285">Put the cluster away</span></span>

1. <span data-ttu-id="6f13d-286">Inicie sesión en la aplicación de almacén como un usuario configurado para el almacén *61*.</span><span class="sxs-lookup"><span data-stu-id="6f13d-286">Sign in to the warehouse app as a user who is set up for warehouse *61*.</span></span>
1. <span data-ttu-id="6f13d-287">En el menú principal, seleccione **Entrada**.</span><span class="sxs-lookup"><span data-stu-id="6f13d-287">On the main menu, select **Inbound**.</span></span>
1. <span data-ttu-id="6f13d-288">En el menú **Entrante**, seleccione **Ubicación de clúster**.</span><span class="sxs-lookup"><span data-stu-id="6f13d-288">On the **Inbound** menu, select **Cluster putaway**.</span></span>
1. <span data-ttu-id="6f13d-289">Seleccione **ID de clúster** e ingrese el ID de clúster que ingresó anteriormente para el clúster cerrado.</span><span class="sxs-lookup"><span data-stu-id="6f13d-289">Select **Cluster ID**, and enter the cluster ID that you entered earlier for the closed cluster.</span></span>
1. <span data-ttu-id="6f13d-290">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6f13d-290">Select **OK**.</span></span>

    <span data-ttu-id="6f13d-291">Aparece la paǵina **Ubicación de clúster: selección**.</span><span class="sxs-lookup"><span data-stu-id="6f13d-291">The **Cluster putaway: Pick** page appears.</span></span> <span data-ttu-id="6f13d-292">Muestra el ID del clúster, la ubicación de recolección, los artículos (el valor *Múltiple* se mostrará) y la cantidad total en el grupo que se debe recolectar.</span><span class="sxs-lookup"><span data-stu-id="6f13d-292">It shows the cluster ID, the picking location, the items (the value *Multiple* will be shown), and the total quantity in the cluster that must be picked.</span></span>

1. <span data-ttu-id="6f13d-293">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6f13d-293">Select **OK**.</span></span>

    <span data-ttu-id="6f13d-294">Aparece la paǵina **Ubicación de clúster: ubicación**.</span><span class="sxs-lookup"><span data-stu-id="6f13d-294">The **Cluster putaway: Put** page appears.</span></span> <span data-ttu-id="6f13d-295">Las instrucciones de **Ubicación** identifican el ID del grupo, la ubicación de colocación, los artículos, la cantidad total y las identificaciones de las placas de los artículos que se han recibido en el grupo.</span><span class="sxs-lookup"><span data-stu-id="6f13d-295">The **Put** instructions identify the cluster ID, the put location, the items, the total quantity, and the license plate IDs for the items that have been received on the cluster.</span></span>

    <span data-ttu-id="6f13d-296">Tiene las opciones estándar para anular o aprobar este paso.</span><span class="sxs-lookup"><span data-stu-id="6f13d-296">You have the standard options to override or pass this step.</span></span>

    <span data-ttu-id="6f13d-297">![Página Ubicación de clúster: ubicación](media/Cluster_putaway-Put.png "Página Ubicación de clúster: ubicación")</span><span class="sxs-lookup"><span data-stu-id="6f13d-297">![Cluster putaway: Put page](media/Cluster_putaway-Put.png "Cluster putaway: Put page")</span></span>

1. <span data-ttu-id="6f13d-298">Seleccione **Aceptar** para confirmar la ubicación del clúster.</span><span class="sxs-lookup"><span data-stu-id="6f13d-298">Select **OK** to confirm the putaway of the cluster.</span></span>

    <span data-ttu-id="6f13d-299">Se muestra un mensaje "Clúster completado".</span><span class="sxs-lookup"><span data-stu-id="6f13d-299">A "Cluster completed" message is shown.</span></span>

## <a name="notes-and-tips"></a><span data-ttu-id="6f13d-300">Notas y consejos</span><span class="sxs-lookup"><span data-stu-id="6f13d-300">Notes and tips</span></span>

<span data-ttu-id="6f13d-301">Para los casos en los que la identificación del grupo se convierte en la placa de matrícula principal de un palé anidado, la posición de colocación se da automáticamente cuando se escanea la identificación del grupo.</span><span class="sxs-lookup"><span data-stu-id="6f13d-301">For cases where the cluster ID becomes the parent license plate for a nested pallet, the put position is automatically given when the cluster ID is scanned.</span></span> <span data-ttu-id="6f13d-302">No se deben escanear más matrículas, incluso si la generación de matrículas está configurada en manual.</span><span class="sxs-lookup"><span data-stu-id="6f13d-302">No further license plate must be scanned, even if license plate generation is set to manual.</span></span>
