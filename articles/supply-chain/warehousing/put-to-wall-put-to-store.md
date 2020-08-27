---
title: Asignar a contenedor/Asignar a tienda
description: En este tema se proporciona información sobre la funcionalidad Asignar a contenedor/Asignar a tienda. Esta funcionalidad le permite manejar escenarios en los que debe consolidar un producto en un área de almacenamiento provisional de preempaquetado, de acuerdo con criterios configurables. Ayuda a reducir el tiempo de selección porque permite seleccionar una única matrícula de entidad de almacén de destino y puede usar más posiciones de asignación que la selección de clústeres.
author: Mirzaab
manager: tfehr
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-16
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: 10eb32f75ccfe1521af9ebfe1e73ef08ea4238f7
ms.sourcegitcommit: f64fce03ec52f844b05a9e8cac286cb201385002
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/16/2020
ms.locfileid: "3597561"
---
# <a name="put-to-wall---put-to-store"></a><span data-ttu-id="ad790-105">Asignar a contenedor/Asignar a tienda</span><span class="sxs-lookup"><span data-stu-id="ad790-105">Put to wall - put to store</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ad790-106">La funcionalidad *Asignar a contenedor/Asignar a tienda* le permite manejar escenarios en los que debe consolidar un producto en un área de almacenamiento provisional de preempaquetado, de acuerdo con criterios configurables.</span><span class="sxs-lookup"><span data-stu-id="ad790-106">The *Put to wall - put to store* functionality lets you handle scenarios where you must consolidate a product to a prepack staging area, based on configurable criteria.</span></span> <span data-ttu-id="ad790-107">Dado que esta funcionalidad permite seleccionar una única matrícula de entidad de almacén de destino y puede usar más posiciones de asignación que la selección de clústeres, las empresas que envían a tiendas o manipulan artículos pequeños se beneficiarán de un menor tiempo de selección.</span><span class="sxs-lookup"><span data-stu-id="ad790-107">Because this functionality allows for picking to a single target license plate and can use more put positions than cluster picking, companies that ship to stores or handle small items will benefit from decreased picking time.</span></span>

<span data-ttu-id="ad790-108">El flujo de trabajo para esta funcionalidad dirige el producto seleccionado a una ubicación de ordenación para su distribución a varios tipos de contenedores.</span><span class="sxs-lookup"><span data-stu-id="ad790-108">The workflow for this functionality directs picked product to a sorting location for distribution into various types of containers.</span></span> <span data-ttu-id="ad790-109">Por lo general, cada ubicación de ordenación incluye varias posiciones de ordenación.</span><span class="sxs-lookup"><span data-stu-id="ad790-109">Generally, each sorting location includes multiple sort positions.</span></span> <span data-ttu-id="ad790-110">Cada posición de ordenación se asigna de acuerdo con los criterios establecidos por el proceso empresarial.</span><span class="sxs-lookup"><span data-stu-id="ad790-110">Each sort position is assigned according to the criteria that are set by the business process.</span></span> <span data-ttu-id="ad790-111">Los criterios típicos son el destino final, el envío o la carga.</span><span class="sxs-lookup"><span data-stu-id="ad790-111">Typical criteria are the final destination, shipment, or load.</span></span> <span data-ttu-id="ad790-112">Una vez que llega un producto, se distribuye a cada posición de ordenación, en función de la cantidad asociada al pedido, al destino, al envío o la carga.</span><span class="sxs-lookup"><span data-stu-id="ad790-112">After a product arrives, it's distributed to each sort position, based on the quantity that is associated with the order, destination, shipment, or load.</span></span> <span data-ttu-id="ad790-113">Cuando un contenedor esté lleno o completo, se mueve a una ubicación de almacenamiento provisional o una ubicación de envío para su posterior manipulación, según el proceso empresarial.</span><span class="sxs-lookup"><span data-stu-id="ad790-113">When a container is full or complete, it's moved to a staging location or a shipping location for further handling, depending on the business process.</span></span>

<span data-ttu-id="ad790-114">Esta funcionalidad de almacenamiento también se conoce con otros nombres, como put-to-light y break opens.</span><span class="sxs-lookup"><span data-stu-id="ad790-114">This warehousing functionality is also referred to by other names, such as put-to-light and break opens.</span></span>

## <a name="turn-on-the-outbound-sorting-feature"></a><span data-ttu-id="ad790-115">Active la característica de ordenación de salida</span><span class="sxs-lookup"><span data-stu-id="ad790-115">Turn on the Outbound sorting feature</span></span>

<span data-ttu-id="ad790-116">Antes de poder usar la funcionalidad *Asignar a contenedor/Asignar a tienda*, la característica *Ordenación de salida* debe estar activada en su sistema.</span><span class="sxs-lookup"><span data-stu-id="ad790-116">Before you can use the *Put to wall - put to store* functionality, the *Outbound sorting* feature must be turned on in your system.</span></span> <span data-ttu-id="ad790-117">Los administradores pueden usar el espacio de trabajo [Administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de la característica y activarla si es necesario.</span><span class="sxs-lookup"><span data-stu-id="ad790-117">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="ad790-118">Allí, la característica se enumera de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="ad790-118">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="ad790-119">**Módulo:** *Gestión de almacén*</span><span class="sxs-lookup"><span data-stu-id="ad790-119">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="ad790-120">**Nombre de la característica:** *Ordenación de salida*</span><span class="sxs-lookup"><span data-stu-id="ad790-120">**Feature name:** *Outbound sorting*</span></span>

<span data-ttu-id="ad790-121">La característica *Ordenación de salida* se puede utilizar junto con la característica *Código de paso de oleada de toda la organización* si está activada.</span><span class="sxs-lookup"><span data-stu-id="ad790-121">The *Outbound sorting* feature can be used in conjunction with the *Organization wide wave step code* feature if it's turned on.</span></span> <span data-ttu-id="ad790-122">También debe activar esta característica si va a utilizar códigos predefinidos que está configurados en códigos de paso de oleada.</span><span class="sxs-lookup"><span data-stu-id="ad790-122">You must also turn on this feature if you will use predefined codes that are set up in wave step codes.</span></span> <span data-ttu-id="ad790-123">En el espacio de trabajo **Administración de características**, esta característica aparece de la siguiente forma:</span><span class="sxs-lookup"><span data-stu-id="ad790-123">In the **Feature management** workspace, this feature is listed in the following way:</span></span>

- <span data-ttu-id="ad790-124">**Módulo:** *Gestión de almacén*</span><span class="sxs-lookup"><span data-stu-id="ad790-124">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="ad790-125">**Nombre de la característica:** *Código de paso de oleada de toda la organización*</span><span class="sxs-lookup"><span data-stu-id="ad790-125">**Feature name:** *Organization wide wave step code*</span></span>

## <a name="setup"></a><span data-ttu-id="ad790-126">Configurar</span><span class="sxs-lookup"><span data-stu-id="ad790-126">Setup</span></span>

<span data-ttu-id="ad790-127">Para esta demostración, se utilizan datos estándar de Contoso y el almacén *62*.</span><span class="sxs-lookup"><span data-stu-id="ad790-127">For this demo, standard Contoso data and warehouse *62* are used.</span></span> <span data-ttu-id="ad790-128">También se usan algunas adiciones que se indican más adelante.</span><span class="sxs-lookup"><span data-stu-id="ad790-128">Some additions that are noted later are also used.</span></span>

### <a name="location-type"></a><span data-ttu-id="ad790-129">Tipo de ubicación</span><span class="sxs-lookup"><span data-stu-id="ad790-129">Location type</span></span>

1. <span data-ttu-id="ad790-130">Vaya a **Gestión de almacenes \> Configurar \> Almacén \> Tipos de ubicación**.</span><span class="sxs-lookup"><span data-stu-id="ad790-130">Go to **Warehouse management \> Setup \> Warehouse \> Location types**.</span></span>
1. <span data-ttu-id="ad790-131">En el panel de acciones, seleccione **Nuevo** para crear un tipo de ubicación para ordenar.</span><span class="sxs-lookup"><span data-stu-id="ad790-131">On the Action Pane, select **New** to create a location type for sorting.</span></span>
1. <span data-ttu-id="ad790-132">Establezca los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="ad790-132">Set the following values:</span></span>

    - <span data-ttu-id="ad790-133">**Tipo de ubicación:** *SORT*</span><span class="sxs-lookup"><span data-stu-id="ad790-133">**Location type:** *SORT*</span></span>
    - <span data-ttu-id="ad790-134">**Descripción:** *Ordenar*</span><span class="sxs-lookup"><span data-stu-id="ad790-134">**Description:** *Sort*</span></span>

1. <span data-ttu-id="ad790-135">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="ad790-135">Select **Save**.</span></span>

### <a name="warehouse-management-parameters"></a><span data-ttu-id="ad790-136">Parámetros de gestión de almacenes</span><span class="sxs-lookup"><span data-stu-id="ad790-136">Warehouse management parameters</span></span>

1. <span data-ttu-id="ad790-137">Vaya a **Gestión de almacenes \> Configuración \> Parámetros de gestión de almacenes**.</span><span class="sxs-lookup"><span data-stu-id="ad790-137">Go to **Warehouse management \> Setup \> Warehouse management parameters**.</span></span>
1. <span data-ttu-id="ad790-138">En la pestaña **General**, en la ficha desplegable **Tipos de ubicación**, en el campo **Tipo de ubicación de ordenación**, introduzca *SORT*.</span><span class="sxs-lookup"><span data-stu-id="ad790-138">On the **General** tab, on the **Location types** FastTab, in the **Sorting location type** field, enter *SORT*.</span></span>
1. <span data-ttu-id="ad790-139">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="ad790-139">Select **Save**.</span></span>

### <a name="location-profile"></a><span data-ttu-id="ad790-140">Perfil de ubicación</span><span class="sxs-lookup"><span data-stu-id="ad790-140">Location profile</span></span>

1. <span data-ttu-id="ad790-141">Vaya a **Gestión de almacenes \> Configurar \> Almacén \> Perfiles de ubicación**.</span><span class="sxs-lookup"><span data-stu-id="ad790-141">Go to **Warehouse management \> Setup \> Warehouse \> Location profiles**.</span></span>
1. <span data-ttu-id="ad790-142">En el panel de acciones, seleccione **Nuevo** para crear un perfil de ubicación para la ubicación de ordenación.</span><span class="sxs-lookup"><span data-stu-id="ad790-142">On the Action Pane, select **New** to create a location profile for the sorting location.</span></span>
1. <span data-ttu-id="ad790-143">Establezca los siguientes valores en el encabezado:</span><span class="sxs-lookup"><span data-stu-id="ad790-143">In the header, set the following values:</span></span>

    - <span data-ttu-id="ad790-144">**Id. de perfil de ubicación:** *Ordenar*</span><span class="sxs-lookup"><span data-stu-id="ad790-144">**Location profile ID:** *Sort*</span></span>
    - <span data-ttu-id="ad790-145">**Nombre:** *Ordenar*</span><span class="sxs-lookup"><span data-stu-id="ad790-145">**Name:** *Sort*</span></span>

1. <span data-ttu-id="ad790-146">En la ficha desplegable **General**, establezca los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="ad790-146">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="ad790-147">**Formato de ubicación:** *PACK*</span><span class="sxs-lookup"><span data-stu-id="ad790-147">**Location format:** *PACK*</span></span>
    - <span data-ttu-id="ad790-148">**Tipo de ubicación:** *SORT*</span><span class="sxs-lookup"><span data-stu-id="ad790-148">**Location type:** *SORT*</span></span>
    - <span data-ttu-id="ad790-149">**Usar seguimiento de matrículas de entidad de almacén:** *Sí*</span><span class="sxs-lookup"><span data-stu-id="ad790-149">**Use license plate tracking:** *Yes*</span></span>
    - <span data-ttu-id="ad790-150">**Permitir artículos combinados:** *Sí*</span><span class="sxs-lookup"><span data-stu-id="ad790-150">**Allow mixed items:** *Yes*</span></span>
    - <span data-ttu-id="ad790-151">**Permitir estados de inventario combinados:** *Sí*</span><span class="sxs-lookup"><span data-stu-id="ad790-151">**Allow mixed inventory statuses:** *Yes*</span></span>

1. <span data-ttu-id="ad790-152">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="ad790-152">Select **Save**.</span></span>

### <a name="locations"></a><span data-ttu-id="ad790-153">Ubicaciones</span><span class="sxs-lookup"><span data-stu-id="ad790-153">Locations</span></span>

1. <span data-ttu-id="ad790-154">Vaya a **Gestión de almacenes \> Configurar \> Almacén \> Ubicaciones**.</span><span class="sxs-lookup"><span data-stu-id="ad790-154">Go to **Warehouse management \> Setup \> Warehouse \> Locations**.</span></span>
1. <span data-ttu-id="ad790-155">Borre la casilla **Generar dígitos de control para la ubicación**.</span><span class="sxs-lookup"><span data-stu-id="ad790-155">Clear the **Generate check digits for location** check box.</span></span>
1. <span data-ttu-id="ad790-156">En el panel de acción, seleccione **Nuevo** y luego establezca los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="ad790-156">On the Action Pane, select **New**, and then set the following values:</span></span>

    - <span data-ttu-id="ad790-157">**Almacén**: *62*</span><span class="sxs-lookup"><span data-stu-id="ad790-157">**Warehouse:** *62*</span></span>
    - <span data-ttu-id="ad790-158">**Ubicación:** *Ordenar*</span><span class="sxs-lookup"><span data-stu-id="ad790-158">**Location:** *Sort*</span></span>
    - <span data-ttu-id="ad790-159">**Id. de perfil de ubicación:** *Ordenar*</span><span class="sxs-lookup"><span data-stu-id="ad790-159">**Location profile ID:** *Sort*</span></span>

1. <span data-ttu-id="ad790-160">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="ad790-160">Select **Save**.</span></span>

### <a name="packing-profiles"></a><span data-ttu-id="ad790-161">Perfiles de embalaje</span><span class="sxs-lookup"><span data-stu-id="ad790-161">Packing profiles</span></span>

1. <span data-ttu-id="ad790-162">Vaya a **Gestión de almacenes \> Configurar \> Embalaje \> Perfiles de embalaje**.</span><span class="sxs-lookup"><span data-stu-id="ad790-162">Go to **Warehouse management \> Setup \> Packing \> Packing profiles**.</span></span>
1. <span data-ttu-id="ad790-163">En el panel de acción, seleccione **Nuevo** y luego establezca los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="ad790-163">On the Action Pane, select **New**, and then set the following values:</span></span>

    - <span data-ttu-id="ad790-164">**Id. de perfil de empaquetado:** *Ordenar*</span><span class="sxs-lookup"><span data-stu-id="ad790-164">**Packing profile ID:** *Sort*</span></span>
    - <span data-ttu-id="ad790-165">**Descripción:** *Ordenar*</span><span class="sxs-lookup"><span data-stu-id="ad790-165">**Description:** *Sort*</span></span>
    - <span data-ttu-id="ad790-166">**Directiva de embalaje de contenedores:** Deje este campo en blanco.</span><span class="sxs-lookup"><span data-stu-id="ad790-166">**Container packing policy:** Leave this field blank.</span></span>
    - <span data-ttu-id="ad790-167">**Modo del id. de contenedor:** *Automático*</span><span class="sxs-lookup"><span data-stu-id="ad790-167">**Container ID mode:** *Auto*</span></span>
    - <span data-ttu-id="ad790-168">**Tipo de contenedor:** *PALLET 48X48*</span><span class="sxs-lookup"><span data-stu-id="ad790-168">**Container type:** *PALLET 48X48*</span></span>
    - <span data-ttu-id="ad790-169">**Crear contenedor automáticamente al cerrar el contenedor:** Deje este campo en blanco.</span><span class="sxs-lookup"><span data-stu-id="ad790-169">**Autocreate container at container close:** Leave this field blank.</span></span>

1. <span data-ttu-id="ad790-170">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="ad790-170">Select **Save**.</span></span>

### <a name="wave-step-codes"></a><span data-ttu-id="ad790-171">Códigos de paso de oleada</span><span class="sxs-lookup"><span data-stu-id="ad790-171">Wave step codes</span></span>

<span data-ttu-id="ad790-172">Si activó la característica *Código de paso de oleada de toda la organización*, configure el siguiente código.</span><span class="sxs-lookup"><span data-stu-id="ad790-172">If you turned on the *Organization wide wave step code* feature, set up the following code.</span></span>

1. <span data-ttu-id="ad790-173">Vaya a **Gestión de almacenes \> Configurar \> Oleadas \> Códigos de paso de oleada**.</span><span class="sxs-lookup"><span data-stu-id="ad790-173">Go to **Warehouse management \> Setup \> Waves \> Wave step codes**.</span></span>
1. <span data-ttu-id="ad790-174">En el panel de acción, seleccione **Nuevo** y luego establezca los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="ad790-174">On the Action Pane, select **New**, and then set the following values:</span></span>

    - <span data-ttu-id="ad790-175">**Código de paso de oleada:** *Ordenar*</span><span class="sxs-lookup"><span data-stu-id="ad790-175">**Wave step code:** *Sort*</span></span>
    - <span data-ttu-id="ad790-176">**Descripción de paso de oleada:** *Ordenar*</span><span class="sxs-lookup"><span data-stu-id="ad790-176">**Wave step description:** *Sort*</span></span>
    - <span data-ttu-id="ad790-177">**Tipo de paso de oleada:** *Plantilla de ordenación*</span><span class="sxs-lookup"><span data-stu-id="ad790-177">**Wave step type:** *Sort template*</span></span>

1. <span data-ttu-id="ad790-178">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="ad790-178">Select **Save**.</span></span>

### <a name="outbound-sorting-template"></a><span data-ttu-id="ad790-179">Plantilla de ordenación de salida</span><span class="sxs-lookup"><span data-stu-id="ad790-179">Outbound sorting template</span></span>

<span data-ttu-id="ad790-180">La plantilla de ordenación controla si se crean las posiciones de ordenación, los criterios que se utilizan y otros atributos del proceso de ordenación.</span><span class="sxs-lookup"><span data-stu-id="ad790-180">The sorting template controls whether sort positions are created, what criteria are used, and other attributes of the sorting process.</span></span>

1. <span data-ttu-id="ad790-181">Vaya a **Gestión de almacenes \> Configuración \> Embalado \> Plantillas de ordenación salientes**.</span><span class="sxs-lookup"><span data-stu-id="ad790-181">Go to **Warehouse management \> Setup \> Packing \> Outbound sorting template**.</span></span>
1. <span data-ttu-id="ad790-182">En el panel de acciones, seleccione **Nuevo** para crear una plantilla de ordenación.</span><span class="sxs-lookup"><span data-stu-id="ad790-182">On the Action Pane, select **New** to create a sorting template.</span></span>
1. <span data-ttu-id="ad790-183">En el encabezado de la nueva plantilla, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="ad790-183">In the header of the new template, set the following values:</span></span>

    - <span data-ttu-id="ad790-184">**Id. de plantilla de ordenación de salida:** *Ordenación de oleadas*</span><span class="sxs-lookup"><span data-stu-id="ad790-184">**Outbound sorting template ID:** *Wave Sort*</span></span>
    - <span data-ttu-id="ad790-185">**Descripción:** *Ordenación de oleadas*</span><span class="sxs-lookup"><span data-stu-id="ad790-185">**Description:** *Wave sort*</span></span>
    - <span data-ttu-id="ad790-186">**Tipo de plantilla de ordenación:** *Demanda de oleadas*</span><span class="sxs-lookup"><span data-stu-id="ad790-186">**Sort template type:** *Wave demand*</span></span>

        <span data-ttu-id="ad790-187">Este campo define el proceso para el que se utiliza la plantilla de ordenación.</span><span class="sxs-lookup"><span data-stu-id="ad790-187">This field defines the process that the sorting template is used for.</span></span> <span data-ttu-id="ad790-188">Los siguientes valores están disponibles:</span><span class="sxs-lookup"><span data-stu-id="ad790-188">The following values are available:</span></span>

        - <span data-ttu-id="ad790-189">**Demanda de oleadas:** la plantilla de ordenación se utiliza para el proceso *Asignar a contenedor*.</span><span class="sxs-lookup"><span data-stu-id="ad790-189">**Wave demand** – The sorting template is used for the *Put to wall* process.</span></span> <span data-ttu-id="ad790-190">Este tipo de plantilla se usa para omitir la estación de embalaje y procesar el inventario directamente fuera de la oleada.</span><span class="sxs-lookup"><span data-stu-id="ad790-190">This template type is used to bypass the pack station and process inventory directly out of the wave.</span></span> <span data-ttu-id="ad790-191">Puede usar este tipo solo si el el proceso de la oleada de **ordenación** se incluye en la plantilla de la oleada.</span><span class="sxs-lookup"><span data-stu-id="ad790-191">You can use this type only if the **sorting** wave process method is included in the wave template.</span></span>
        - <span data-ttu-id="ad790-192">**Contenedor:** la plantilla de ordenación se usa para el proceso *Construcción de pallets después del empaquetado*.</span><span class="sxs-lookup"><span data-stu-id="ad790-192">**Container** – The sorting template is used for the *Pallet building after packing* process.</span></span> <span data-ttu-id="ad790-193">Este tipo de plantilla se usa para procesar los contenedores que están cerrados en esa estación de embalaje y debe ordenados sobre pallets.</span><span class="sxs-lookup"><span data-stu-id="ad790-193">This template type is used to process containers that are closed at the pack station and must be sorted onto pallets.</span></span>

    - <span data-ttu-id="ad790-194">**Almacén**: *62*</span><span class="sxs-lookup"><span data-stu-id="ad790-194">**Warehouse:** *62*</span></span>
    - <span data-ttu-id="ad790-195">**Ubicación:** *Ordenar*</span><span class="sxs-lookup"><span data-stu-id="ad790-195">**Location:** *Sort*</span></span>

1. <span data-ttu-id="ad790-196">En la ficha desplegable **General**, establezca los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="ad790-196">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="ad790-197">**Comprobación del orden:** *Escaneo de posición*.</span><span class="sxs-lookup"><span data-stu-id="ad790-197">**Sort verification:** *Position scan*</span></span>

        <span data-ttu-id="ad790-198">Este campo define la verificación que se requiere durante la ordenación.</span><span class="sxs-lookup"><span data-stu-id="ad790-198">This field defines the verification that is required during sorting.</span></span> <span data-ttu-id="ad790-199">Los siguientes valores están disponibles:</span><span class="sxs-lookup"><span data-stu-id="ad790-199">The following values are available:</span></span>

        - <span data-ttu-id="ad790-200">None</span><span class="sxs-lookup"><span data-stu-id="ad790-200">None</span></span>
        - <span data-ttu-id="ad790-201">Escaneo de matrícula de entidad de almacén</span><span class="sxs-lookup"><span data-stu-id="ad790-201">License plate scan</span></span>
        - <span data-ttu-id="ad790-202">Escaneo de posición</span><span class="sxs-lookup"><span data-stu-id="ad790-202">Position scan</span></span>

    - <span data-ttu-id="ad790-203">**Crear trabajo en posición cerrada:** *Sí*</span><span class="sxs-lookup"><span data-stu-id="ad790-203">**Create work on position close:** *Yes*</span></span>

        <span data-ttu-id="ad790-204">Si la opción se establece en *Sí*, cuando la posición se cierre, se creará el trabajo para mover el inventario a la ubicación de envío final.</span><span class="sxs-lookup"><span data-stu-id="ad790-204">If this option is set to *Yes*, when the position is closed, work will be created to move inventory to the final shipping location.</span></span> <span data-ttu-id="ad790-205">Si se establece en *No*, el inventario se seleccionará inmediatamente para el pedido cuando se cierre la posición.</span><span class="sxs-lookup"><span data-stu-id="ad790-205">If it's set to *No*, inventory will immediately be picked to the order when the position is closed.</span></span>

    - <span data-ttu-id="ad790-206">**Asignación de posición:** *Manual*</span><span class="sxs-lookup"><span data-stu-id="ad790-206">**Position assignment:** *Manual*</span></span>

        <span data-ttu-id="ad790-207">Este campo define el tipo de asignación de posición.</span><span class="sxs-lookup"><span data-stu-id="ad790-207">This field defines the type of position assignment.</span></span> <span data-ttu-id="ad790-208">Los siguientes valores están disponibles:</span><span class="sxs-lookup"><span data-stu-id="ad790-208">The following values are available:</span></span>

        - <span data-ttu-id="ad790-209">**Manual**: el usuario debe indicar siempre en qué posición se debe ordenar el inventario.</span><span class="sxs-lookup"><span data-stu-id="ad790-209">**Manual** – The user must always indicate which position the inventory should be sorted to.</span></span>
        - <span data-ttu-id="ad790-210">**Automático:** el sistema automáticamente dirigirá el inventario a una posición cuando sea posible, en función de los descansos de la plantilla de ordenación.</span><span class="sxs-lookup"><span data-stu-id="ad790-210">**Automatic** – The system will automatically guide the inventory to a position whenever it can, based on the sort template breaks.</span></span>

    - <span data-ttu-id="ad790-211">**Asignar criterios de posición de ordenación:** *Usar solo una posición vacía*</span><span class="sxs-lookup"><span data-stu-id="ad790-211">**Assign sort position criteria:** *Only use empty position*</span></span>

        <span data-ttu-id="ad790-212">Este campo controla si el inventario que ya está presente en puestos clasificados se tiene en cuenta cuando se asigna un puesto para la demanda.</span><span class="sxs-lookup"><span data-stu-id="ad790-212">This field controls whether inventory that is already present on sort positions is taken into account when a position is assigned for the demand.</span></span> <span data-ttu-id="ad790-213">Los siguientes valores están disponibles:</span><span class="sxs-lookup"><span data-stu-id="ad790-213">The following values are available:</span></span>

        - <span data-ttu-id="ad790-214">**Usar solo una posición vacía:** se tendrán en cuenta las posiciones que ya tienen inventario asociado a ellas.</span><span class="sxs-lookup"><span data-stu-id="ad790-214">**Only use empty position** – Positions that already have inventory associated with them will be taken into account</span></span>
        - <span data-ttu-id="ad790-215">**Asumir posición vacía:** cualquier inventario que ya esté en la posición no se tendrá en cuenta durante la asignación.</span><span class="sxs-lookup"><span data-stu-id="ad790-215">**Assume position empty** – Any inventory that is already on the position will be disregarded during assignment.</span></span> <span data-ttu-id="ad790-216">Se utilizarán todas las posiciones disponibles.</span><span class="sxs-lookup"><span data-stu-id="ad790-216">All available positions will be used.</span></span>

    - <span data-ttu-id="ad790-217">**Código de paso de oleada:** *Ordenar*</span><span class="sxs-lookup"><span data-stu-id="ad790-217">**Wave step code:** *Sort*</span></span>

        <span data-ttu-id="ad790-218">Si la característica *Código de paso de oleada de toda la organización* está activada, el código de paso de oleada *Ordenación* también debe configurarse en códigos de paso de oleada.</span><span class="sxs-lookup"><span data-stu-id="ad790-218">If the *Organization wide wave step code* feature is turned on, the *Sort* wave step code must also be set up in wave step codes.</span></span>

    - <span data-ttu-id="ad790-219">**Posición de ordenación de cierre automático:** *Sí*</span><span class="sxs-lookup"><span data-stu-id="ad790-219">**Auto close sort position:** *Yes*</span></span>

        <span data-ttu-id="ad790-220">Si esta opción se establece en *Sí*, la posición de la ordenación se cerrará automáticamente cuando todo el trabajo que viene a la ubicación se haya completado.</span><span class="sxs-lookup"><span data-stu-id="ad790-220">If this option is set to *Yes*, the sort position will automatically be closed when all work that comes to the position has been completed.</span></span>

    - <span data-ttu-id="ad790-221">**Número de posiciones de ordenación:** *3*</span><span class="sxs-lookup"><span data-stu-id="ad790-221">**Number of sort positions:** *3*</span></span>

        <span data-ttu-id="ad790-222">Este campo define el número máximo de posiciones de ordenación que creará el sistema.</span><span class="sxs-lookup"><span data-stu-id="ad790-222">This field defines the maximum number of sort positions that the system will create.</span></span>

    - <span data-ttu-id="ad790-223">**Prefijo de posición de ordenación:** *SP*</span><span class="sxs-lookup"><span data-stu-id="ad790-223">**Sort position prefix:** *SP-*</span></span>

        <span data-ttu-id="ad790-224">Este campo define el prefijo que el sistema asigna antes del número de posición.</span><span class="sxs-lookup"><span data-stu-id="ad790-224">This field defines the prefix that the system assigns before the position number.</span></span>

    - <span data-ttu-id="ad790-225">**Posición de ordenación de empaquetado automático:** *Sí*</span><span class="sxs-lookup"><span data-stu-id="ad790-225">**Auto pack sort position:** *Yes*</span></span>

        <span data-ttu-id="ad790-226">Si esta opción se establece en *Sí*, el inventario en la posición de ordenación se envasará en un contenedor cuando se cierra la posición.</span><span class="sxs-lookup"><span data-stu-id="ad790-226">If this option is set to *Yes*, the inventory on the sort position will be packed into a container when the position is closed.</span></span>

    - <span data-ttu-id="ad790-227">**Id. de perfil de empaquetado:** *Ordenar*</span><span class="sxs-lookup"><span data-stu-id="ad790-227">**Packing profile ID:** *Sort*</span></span>

        <span data-ttu-id="ad790-228">Este campo define el perfil de embalaje que se usará cuando la posición de ordenación sea embalada en un contenedor.</span><span class="sxs-lookup"><span data-stu-id="ad790-228">This field defines the packing profile that will be used when the sort position is packed into a container.</span></span>

1. <span data-ttu-id="ad790-229">En el panel de acciones, seleccione **Editar consulta** para especificar los criterios que se utilizan para esta plantilla de ordenación.</span><span class="sxs-lookup"><span data-stu-id="ad790-229">On the Action Pane, select **Edit query** to specify the criteria that are used for this sorting template.</span></span>
1. <span data-ttu-id="ad790-230">En el cuadro de diálogo de consulta, en la pestaña **Ordenación**, seleccione **Nuevo** para agregar una línea y luego establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="ad790-230">In the query dialog box, on the **Sorting** tab, select **New** to add a line, and then set the following values:</span></span>

    - <span data-ttu-id="ad790-231">**Tabla:** *Detalles de carga*</span><span class="sxs-lookup"><span data-stu-id="ad790-231">**Table:** *Load details*</span></span>
    - <span data-ttu-id="ad790-232">**Tabla derivada:** *Detalles de carga*</span><span class="sxs-lookup"><span data-stu-id="ad790-232">**Derived table:** *Load details*</span></span>
    - <span data-ttu-id="ad790-233">**Campo:** *Identificación del envío*</span><span class="sxs-lookup"><span data-stu-id="ad790-233">**Field:** *Shipment ID*</span></span>
    - <span data-ttu-id="ad790-234">**Dirección de búsqueda:** *Ascendente*</span><span class="sxs-lookup"><span data-stu-id="ad790-234">**Search direction:** *Ascending*</span></span>

1. <span data-ttu-id="ad790-235">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ad790-235">Select **OK**.</span></span>
1. <span data-ttu-id="ad790-236">Es posible que reciba el siguiente mensaje: "La agrupación se restablecerá, ¿continuar?"</span><span class="sxs-lookup"><span data-stu-id="ad790-236">You might receive the following message: "Grouping will be reset, continue?"</span></span> <span data-ttu-id="ad790-237">Seleccione **Sí**.</span><span class="sxs-lookup"><span data-stu-id="ad790-237">Select **Yes**.</span></span>

    <span data-ttu-id="ad790-238">El botón **Descansos de la plantilla de ordenación de salida** del panel de acciones estará disponible.</span><span class="sxs-lookup"><span data-stu-id="ad790-238">The **Outbound sorting template breaks** button on the Action Pane becomes available.</span></span>

1. <span data-ttu-id="ad790-239">En el panel de acciones, seleccione **Descansos de la plantilla de ordenación de salida**.</span><span class="sxs-lookup"><span data-stu-id="ad790-239">On the Action Pane, select **Outbound sorting template breaks**.</span></span>
1. <span data-ttu-id="ad790-240">Seleccione la casilla **Agrupar por campo** para agrupar por id. de envío.</span><span class="sxs-lookup"><span data-stu-id="ad790-240">Select the **Group by field** check box to group by shipment ID.</span></span>

    <span data-ttu-id="ad790-241">Esta configuración creará una posición de ordenación por envío que es un contenedor en la oleada.</span><span class="sxs-lookup"><span data-stu-id="ad790-241">This setting will create one sort position per shipment that is a container in the wave.</span></span>

1. <span data-ttu-id="ad790-242">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ad790-242">Select **OK**.</span></span>

### <a name="wave-process-methods"></a><span data-ttu-id="ad790-243">Métodos de procesamiento de oleada</span><span class="sxs-lookup"><span data-stu-id="ad790-243">Wave process methods</span></span>

1. <span data-ttu-id="ad790-244">Vaya a **Gestión de almacenes \> Configuración \> Oleadas \> Métodos de proceso de oleadas**.</span><span class="sxs-lookup"><span data-stu-id="ad790-244">Go to **Warehouse management \> Setup \> Waves \> Wave process methods**.</span></span>
1. <span data-ttu-id="ad790-245">En el panel acciones, seleccione **Regenerar métodos**.</span><span class="sxs-lookup"><span data-stu-id="ad790-245">On the Action Pane, select **Regenerate methods**.</span></span>

    <span data-ttu-id="ad790-246">El método de **ordenación** se agrega a la lista de métodos disponibles, y se selecciona el tipo de plantilla de oleada *Envío* para ello.</span><span class="sxs-lookup"><span data-stu-id="ad790-246">The **sorting** method is added to the list of available methods, and the *Shipping* wave template type is selected for it.</span></span>

### <a name="wave-templates"></a><span data-ttu-id="ad790-247">Plantillas de oleada</span><span class="sxs-lookup"><span data-stu-id="ad790-247">Wave templates</span></span>

<span data-ttu-id="ad790-248">Edite la plantilla de oleada que se utiliza para la ordenación de la demanda de oleadas.</span><span class="sxs-lookup"><span data-stu-id="ad790-248">Edit the wave template that is used for wave demand sorting.</span></span>

1. <span data-ttu-id="ad790-249">Vaya a **Gestión de almacenes \> Configurar \> Oleadas \> Plantillas de oleada**.</span><span class="sxs-lookup"><span data-stu-id="ad790-249">Go to **Warehouse management \> Setup \> Waves \> Wave templates**.</span></span>
1. <span data-ttu-id="ad790-250">En el campo **Tipo de plantilla de oleada**, seleccione *Envío*.</span><span class="sxs-lookup"><span data-stu-id="ad790-250">In the **Wave template type** field, select *Shipping*.</span></span>
1. <span data-ttu-id="ad790-251">Seleccione la plantilla **62 Envío predeterminado** existente.</span><span class="sxs-lookup"><span data-stu-id="ad790-251">Select the existing **62 Shipping default** template.</span></span>
1. <span data-ttu-id="ad790-252">En el panel Acciones, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="ad790-252">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="ad790-253">En la ficha desplegable **General**, haga los siguientes cambios:</span><span class="sxs-lookup"><span data-stu-id="ad790-253">On the **General** FastTab, make the following changes:</span></span>

    - <span data-ttu-id="ad790-254">Establezca la opción **Procesar oleada para su despacho al almacén** en *No*.</span><span class="sxs-lookup"><span data-stu-id="ad790-254">Set the **Process wave at release to warehouse** option to *No*.</span></span>
    - <span data-ttu-id="ad790-255">Establezca la opción **Asignar a oleadas abiertas** en *Sí*.</span><span class="sxs-lookup"><span data-stu-id="ad790-255">Set the **Assign to open waves** option to *Yes*.</span></span>

1. <span data-ttu-id="ad790-256">En la ficha desplegable **Métodos**, configure el método de **ordenación**:</span><span class="sxs-lookup"><span data-stu-id="ad790-256">On the **Methods** FastTab, set up the **sorting** method:</span></span>

    1. <span data-ttu-id="ad790-257">En la cuadrícula **Métodos restantes**, seleccione **ordenación**.</span><span class="sxs-lookup"><span data-stu-id="ad790-257">In the **Remaining Methods** grid, select **sorting**.</span></span>
    2. <span data-ttu-id="ad790-258">Seleccione el botón de flecha derecha para mover la **ordenación** a la cuadrícula **Métodos seleccionados**.</span><span class="sxs-lookup"><span data-stu-id="ad790-258">Select the right arrow button to move **sorting** to the **Selected Methods** grid.</span></span>
    3. <span data-ttu-id="ad790-259">En la cuadrícula **Métodos seleccionados**, seleccione **ordenación**.</span><span class="sxs-lookup"><span data-stu-id="ad790-259">In the **Selected Methods** grid, select **sorting**.</span></span>
    4. <span data-ttu-id="ad790-260">Establezca el campo **Código de paso de oleada** en *Ordenación*.</span><span class="sxs-lookup"><span data-stu-id="ad790-260">Set the **Wave step code** field to *Sort*.</span></span>

1. <span data-ttu-id="ad790-261">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="ad790-261">Select **Save**.</span></span>

### <a name="mobile-device-menu-items"></a><span data-ttu-id="ad790-262">Elementos de menú del dispositivo móvil</span><span class="sxs-lookup"><span data-stu-id="ad790-262">Mobile device menu items</span></span>

1. <span data-ttu-id="ad790-263">Vaya a **Administración de almacenes \> Configurar \> Dispositivo móvil \> Elementos de menú del dispositivo móvil**.</span><span class="sxs-lookup"><span data-stu-id="ad790-263">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="ad790-264">En el panel de acciones, haga clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="ad790-264">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="ad790-265">Establezca los siguientes valores en el encabezado:</span><span class="sxs-lookup"><span data-stu-id="ad790-265">In the header, set the following values:</span></span>

    - <span data-ttu-id="ad790-266">**Nombre del elemento de menú:** *Ordenar*</span><span class="sxs-lookup"><span data-stu-id="ad790-266">**Menu item name:** *Sort*</span></span>
    - <span data-ttu-id="ad790-267">**Título:** *Ordenar*</span><span class="sxs-lookup"><span data-stu-id="ad790-267">**Title:** *Sort*</span></span>
    - <span data-ttu-id="ad790-268">**Modo:** *Indirecto*</span><span class="sxs-lookup"><span data-stu-id="ad790-268">**Mode:** *Indirect*</span></span>
    - <span data-ttu-id="ad790-269">**Usar trabajo existente:** *No*</span><span class="sxs-lookup"><span data-stu-id="ad790-269">**Use existing work:** *No*</span></span>

1. <span data-ttu-id="ad790-270">En la ficha desplegable **General**, establezca los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="ad790-270">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="ad790-271">**Código de actividad:** *Ordenación de salida*</span><span class="sxs-lookup"><span data-stu-id="ad790-271">**Activity code:** *Outbound sorting*</span></span>
    - <span data-ttu-id="ad790-272">**Usar guía de proceso:** *Sí* (valor predeterminado)</span><span class="sxs-lookup"><span data-stu-id="ad790-272">**Use process guide:** *Yes* (default value)</span></span>
    - <span data-ttu-id="ad790-273">**Id. de plantilla de ordenación de salida:** *Ordenación de oleadas*</span><span class="sxs-lookup"><span data-stu-id="ad790-273">**Outbound sorting template ID:** *Wave Sort*</span></span>

1. <span data-ttu-id="ad790-274">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="ad790-274">Select **Save**.</span></span>

### <a name="mobile-device-menu"></a><span data-ttu-id="ad790-275">Menú del dispositivo móvil</span><span class="sxs-lookup"><span data-stu-id="ad790-275">Mobile device menu</span></span>

1. <span data-ttu-id="ad790-276">Vaya a **Administración de almacenes \> Configuración \> Dispositivo móvil \> Menú del dispositivo móvil**.</span><span class="sxs-lookup"><span data-stu-id="ad790-276">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu**.</span></span>
1. <span data-ttu-id="ad790-277">En la lista de menús, seleccione **Saliente**.</span><span class="sxs-lookup"><span data-stu-id="ad790-277">In the list of menus, select **Outbound**.</span></span>
1. <span data-ttu-id="ad790-278">En el panel Acciones, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="ad790-278">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="ad790-279">En la cuadrícula **Menús disponibles y elementos de menú**, busque y seleccione el elemento de menú **Ordenar** que acaba de crear.</span><span class="sxs-lookup"><span data-stu-id="ad790-279">In the **Available Menus And Menu Items** grid, find and select the **Sort** menu item that you just created.</span></span>
1. <span data-ttu-id="ad790-280">Seleccione el botón de flecha derecha para mover **Ordenar** a la cuadrícula **Estructura del menú**.</span><span class="sxs-lookup"><span data-stu-id="ad790-280">Select the right arrow button to move **Sort** to the **Menu Structure** grid.</span></span> <span data-ttu-id="ad790-281">De esta manera, agrega el elemento de menú al menú **Saliente**.</span><span class="sxs-lookup"><span data-stu-id="ad790-281">In this way, you add the menu item to the **Outbound** menu.</span></span>
1. <span data-ttu-id="ad790-282">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="ad790-282">Select **Save**.</span></span>

### <a name="location-directives"></a><span data-ttu-id="ad790-283">Directivas de ubicación</span><span class="sxs-lookup"><span data-stu-id="ad790-283">Location directives</span></span>

<span data-ttu-id="ad790-284">Debe crear directivas de ubicación para guiar el trabajo que se crea después de que se complete la ordenación.</span><span class="sxs-lookup"><span data-stu-id="ad790-284">You must create location directives to guide the work that is created after the sorting is completed.</span></span>

1. <span data-ttu-id="ad790-285">Vaya a **Gestión de almacenes \> Configurar \> Directivas de ubicación**.</span><span class="sxs-lookup"><span data-stu-id="ad790-285">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="ad790-286">En el campo **Tipo de orden de trabajo**, seleccione *Selección de inventario ordenado*.</span><span class="sxs-lookup"><span data-stu-id="ad790-286">In the **Work order type** field, select *Sorted inventory picking*.</span></span>
1. <span data-ttu-id="ad790-287">En el panel de acciones, haga clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="ad790-287">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="ad790-288">Establezca los siguientes valores en el encabezado:</span><span class="sxs-lookup"><span data-stu-id="ad790-288">In the header, set the following values:</span></span>

    - <span data-ttu-id="ad790-289">**Secuencia**: *1*</span><span class="sxs-lookup"><span data-stu-id="ad790-289">**Sequence:** *1*</span></span>
    - <span data-ttu-id="ad790-290">**Nombre:** *Asignar a Baydoor*</span><span class="sxs-lookup"><span data-stu-id="ad790-290">**Name:** *Put to Baydoor*</span></span>

1. <span data-ttu-id="ad790-291">En la ficha desplegable **Directivas generales**, establezca los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="ad790-291">On the **Location directives** FastTab, set the following values:</span></span>

    - <span data-ttu-id="ad790-292">**Tipo de trabajo**: *Ubicar*</span><span class="sxs-lookup"><span data-stu-id="ad790-292">**Work type:** *Put*</span></span>
    - <span data-ttu-id="ad790-293">**Sitio**: *6*</span><span class="sxs-lookup"><span data-stu-id="ad790-293">**Site:** *6*</span></span>
    - <span data-ttu-id="ad790-294">**Almacén**: *62*</span><span class="sxs-lookup"><span data-stu-id="ad790-294">**Warehouse:** *62*</span></span>
    - <span data-ttu-id="ad790-295">**Código de directiva:** deje en blanco este campo.</span><span class="sxs-lookup"><span data-stu-id="ad790-295">**Directive code:** Leave this field blank.</span></span>
    - <span data-ttu-id="ad790-296">**Varios SKU:** *No*</span><span class="sxs-lookup"><span data-stu-id="ad790-296">**Multiple SKU:** *No*</span></span>

1. <span data-ttu-id="ad790-297">Seleccione **Guardar** para tener disponible la ficha desplegable **Líneas**.</span><span class="sxs-lookup"><span data-stu-id="ad790-297">Select **Save** to make the **Lines** FastTab available.</span></span>
1. <span data-ttu-id="ad790-298">En la ficha desplegable **Líneas**, seleccione **Nuevo** y luego establezca los valores siguientes.</span><span class="sxs-lookup"><span data-stu-id="ad790-298">On the **Lines** FastTab, select **New**, and then set the following values.</span></span> <span data-ttu-id="ad790-299">Acepte los valores predeterminados del resto de campos.</span><span class="sxs-lookup"><span data-stu-id="ad790-299">Accept the default values for all the other fields.</span></span>

    - <span data-ttu-id="ad790-300">**Número de secuencia:** *1*</span><span class="sxs-lookup"><span data-stu-id="ad790-300">**Sequence number:** *1*</span></span>
    - <span data-ttu-id="ad790-301">**Cantidad inicial**: *0*</span><span class="sxs-lookup"><span data-stu-id="ad790-301">**From quantity:** *0*</span></span>
    - <span data-ttu-id="ad790-302">**Cantidad final**: *1000000*</span><span class="sxs-lookup"><span data-stu-id="ad790-302">**To quantity:** *1000000*</span></span>

1. <span data-ttu-id="ad790-303">Seleccione **Guardar** para tener disponible la ficha desplegable **Acciones directivas de ubicación**.</span><span class="sxs-lookup"><span data-stu-id="ad790-303">Select **Save** to make the **Location Directive Actions** FastTab available.</span></span>
1. <span data-ttu-id="ad790-304">En la ficha desplegable **Acciones de directiva de ubicación**, seleccione **Nuevo** y luego establezca los valores siguientes.</span><span class="sxs-lookup"><span data-stu-id="ad790-304">On the **Location Directive Actions** FastTab, select **New**, and then set the following values.</span></span> <span data-ttu-id="ad790-305">Acepte los valores predeterminados del resto de campos.</span><span class="sxs-lookup"><span data-stu-id="ad790-305">Accept the default values for all the other fields.</span></span>

    - <span data-ttu-id="ad790-306">**Número de secuencia:** *1*</span><span class="sxs-lookup"><span data-stu-id="ad790-306">**Sequence number:** *1*</span></span>
    - <span data-ttu-id="ad790-307">**Nombre:** *Baydoor*</span><span class="sxs-lookup"><span data-stu-id="ad790-307">**Name:** *Baydoor*</span></span>

1. <span data-ttu-id="ad790-308">Seleccione **Guardar** para tener disponible el botón **Editar consulta** en la ficha desplegable **Acciones de directiva de ubicación**.</span><span class="sxs-lookup"><span data-stu-id="ad790-308">Select **Save** to make the **Edit query** button on the **Location Directive Actions** FastTab available.</span></span>
1. <span data-ttu-id="ad790-309">En la ficha desplegable **Acciones de directiva de ubicación**, seleccione **Editar consulta**.</span><span class="sxs-lookup"><span data-stu-id="ad790-309">On the **Location Directive Actions** FastTab, select **Edit query**.</span></span>
1. <span data-ttu-id="ad790-310">En el cuadro de diálogo de consulta, en la pestaña **Rango**, busque la fila donde el campo **Campo** esté establecido en *Ubicación*.</span><span class="sxs-lookup"><span data-stu-id="ad790-310">In the query dialog box, on the **Range** tab, find the row where the **Field** field is set to *Location*.</span></span> <span data-ttu-id="ad790-311">Seleccione el campo **Criterios** en esta fila para *Baydoor*.</span><span class="sxs-lookup"><span data-stu-id="ad790-311">Set the **Criteria** field for this row to *Baydoor*.</span></span>
1. <span data-ttu-id="ad790-312">Seleccione **Aceptar** para confirmar la edición.</span><span class="sxs-lookup"><span data-stu-id="ad790-312">Select **OK** to confirm the edit.</span></span>

### <a name="work-classes"></a><span data-ttu-id="ad790-313">Clases de trabajo</span><span class="sxs-lookup"><span data-stu-id="ad790-313">Work classes</span></span>

1. <span data-ttu-id="ad790-314">Vaya a **Gestión de almacenes \> Configurar \> Trabajo \> Clases de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="ad790-314">Go to **Warehouse management \> Setup \> Work \> Work classes**.</span></span>
1. <span data-ttu-id="ad790-315">En el panel de acciones, haga clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="ad790-315">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="ad790-316">Establezca los siguientes valores en el encabezado:</span><span class="sxs-lookup"><span data-stu-id="ad790-316">In the header, set the following values:</span></span>

    - <span data-ttu-id="ad790-317">**Id. de la clase de trabajo:** *Ordenación*</span><span class="sxs-lookup"><span data-stu-id="ad790-317">**Work class ID:** *Sorting*</span></span>
    - <span data-ttu-id="ad790-318">**Descripción:** *Ordenación*</span><span class="sxs-lookup"><span data-stu-id="ad790-318">**Description:** *Sorting*</span></span>
    - <span data-ttu-id="ad790-319">**Tipo de orden de trabajo:** *Selección de inventario ordenado*</span><span class="sxs-lookup"><span data-stu-id="ad790-319">**Work order type:** *Sorted inventory picking*</span></span>

1. <span data-ttu-id="ad790-320">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="ad790-320">Select **Save**.</span></span>

### <a name="work-templates"></a><span data-ttu-id="ad790-321">Plantillas de trabajo</span><span class="sxs-lookup"><span data-stu-id="ad790-321">Work templates</span></span>

1. <span data-ttu-id="ad790-322">Vaya a **Gestión de almacenes \> Trabajo \> Plantillas de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="ad790-322">Go to **Warehouse management \> Work \> Work templates**.</span></span>
1. <span data-ttu-id="ad790-323">En el campo **Tipo de orden de trabajo**, seleccione *Pedidos de ventas*.</span><span class="sxs-lookup"><span data-stu-id="ad790-323">In the **Work order type** field, select *Sales orders*.</span></span>
1. <span data-ttu-id="ad790-324">En la cuadrícula, seleccione la plantilla de trabajo **62 Selección para empaquetar**.</span><span class="sxs-lookup"><span data-stu-id="ad790-324">In the grid, select the **62 Pick to pack** work template.</span></span>
1. <span data-ttu-id="ad790-325">En el panel de acciones, seleccione **Saltos de encabezado de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="ad790-325">On the Action Pane, select **Work header breaks**.</span></span>
1. <span data-ttu-id="ad790-326">En el panel Acciones, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="ad790-326">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="ad790-327">En la línea donde el campo **Nombre del campo** esté establecido en *Id. del envío*, desactive la casilla **Agrupar por este campo**.</span><span class="sxs-lookup"><span data-stu-id="ad790-327">On the line where the **Field name** field is set to *Shipment ID*, clear the **Group by this field** check box.</span></span>
1. <span data-ttu-id="ad790-328">Seleccione **Guardar** y luego cierre el cuadro de diálogo **Saltos de encabezado de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="ad790-328">Select **Save**, and then close the **Work header breaks** dialog box.</span></span>
1. <span data-ttu-id="ad790-329">En el campo **Tipo de orden de trabajo**, seleccione *Selección de inventario ordenado*.</span><span class="sxs-lookup"><span data-stu-id="ad790-329">In the **Work order type** field, select *Sorted inventory picking*.</span></span>
1. <span data-ttu-id="ad790-330">Seleccione **Nuevo** para crear una plantilla de trabajo.</span><span class="sxs-lookup"><span data-stu-id="ad790-330">Select **New** to create a work template.</span></span>
1. <span data-ttu-id="ad790-331">En la sección **Visión general**, establezca los siguientes valores.</span><span class="sxs-lookup"><span data-stu-id="ad790-331">In the **Overview** section, set the following values.</span></span> <span data-ttu-id="ad790-332">Acepte los valores predeterminados del resto de campos.</span><span class="sxs-lookup"><span data-stu-id="ad790-332">Accept the default values for all the other fields.</span></span>

    - <span data-ttu-id="ad790-333">**Plantilla de trabajo:** *Selección ordenada*</span><span class="sxs-lookup"><span data-stu-id="ad790-333">**Work template:** *Sorted picking*</span></span>
    - <span data-ttu-id="ad790-334">**Descripción de la plantilla de trabajo:** *Selección ordenada*</span><span class="sxs-lookup"><span data-stu-id="ad790-334">**Work template description:** *Sorted picking*</span></span>

1. <span data-ttu-id="ad790-335">Seleccione **Guardar** para tener disponible la sección **Detalles de plantilla de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="ad790-335">Select **Save** to make the **Work Template Details** section available.</span></span>
1. <span data-ttu-id="ad790-336">En la sección **Detalles de plantilla de trabajo**, creará dos líneas.</span><span class="sxs-lookup"><span data-stu-id="ad790-336">In the **Work Template Details** section, you will create two lines.</span></span> <span data-ttu-id="ad790-337">Seleccione **Nuevo** y establezca los valores siguientes para la línea 1:</span><span class="sxs-lookup"><span data-stu-id="ad790-337">Select **New**, and then set the following values for line 1:</span></span>

    - <span data-ttu-id="ad790-338">**Tipo de trabajo**: *Recoger*</span><span class="sxs-lookup"><span data-stu-id="ad790-338">**Work type:** *Pick*</span></span>
    - <span data-ttu-id="ad790-339">**Obligatorio:** Seleccionado (= *Sí*)</span><span class="sxs-lookup"><span data-stu-id="ad790-339">**Mandatory:** Selected (= *Yes*)</span></span>
    - <span data-ttu-id="ad790-340">**Id. de la clase de trabajo:** *Ordenación*</span><span class="sxs-lookup"><span data-stu-id="ad790-340">**Work class ID:** *Sorting*</span></span>

1. <span data-ttu-id="ad790-341">Seleccione **Nuevo** una vez más y establezca los valores siguientes para la línea 2:</span><span class="sxs-lookup"><span data-stu-id="ad790-341">Select **New** again, and then set the following values for line 2:</span></span>

    - <span data-ttu-id="ad790-342">**Tipo de trabajo**: *Ubicar*</span><span class="sxs-lookup"><span data-stu-id="ad790-342">**Work type:** *Put*</span></span>
    - <span data-ttu-id="ad790-343">**Obligatorio:** Seleccionado (= *Sí*)</span><span class="sxs-lookup"><span data-stu-id="ad790-343">**Mandatory:** Selected (= *Yes*)</span></span>
    - <span data-ttu-id="ad790-344">**Id. de la clase de trabajo:** *Ordenación*</span><span class="sxs-lookup"><span data-stu-id="ad790-344">**Work class ID:** *Sorting*</span></span>

1. <span data-ttu-id="ad790-345">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="ad790-345">Select **Save**.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="ad790-346">Supuesto de ejemplo</span><span class="sxs-lookup"><span data-stu-id="ad790-346">Example scenario</span></span>

<span data-ttu-id="ad790-347">Este escenario simula una situación en la que el almacén almacena artículos pequeños en ubicaciones y debe empaquetarlos en cajas antes de enviarlos, y donde la funcionalidad de la estación de empaquetado no es realmente adecuada.</span><span class="sxs-lookup"><span data-stu-id="ad790-347">This scenario simulates a situation where the warehouse stores small items in locations and must pack them into boxes before they are shipped, and where packing station functionality isn't really suitable.</span></span> <span data-ttu-id="ad790-348">Para aumentar la velocidad de selección, los trabajadores seleccionan pedidos para varios clientes y diferentes direcciones al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="ad790-348">Workers pick orders for multiple customers and different addresses at the same time to increase the picking speed.</span></span> <span data-ttu-id="ad790-349">Una vez que se ha completado la selección, los trabajadores llegan a la ubicación de ordenación, donde los artículos seleccionados se pueden ordenar en la casilla correcta, según los criterios requeridos.</span><span class="sxs-lookup"><span data-stu-id="ad790-349">After picking has been completed, the workers arrive at the sorting location, where the picked items can be sorted to the correct box, based on required criteria.</span></span> <span data-ttu-id="ad790-350">En este ejemplo, el id. del envío se utilizará para determinar la casilla correcta, porque cada envío tiene una dirección diferente.</span><span class="sxs-lookup"><span data-stu-id="ad790-350">In this example, the shipment ID will be used to determine the correct box, because each shipment has a different address.</span></span> <span data-ttu-id="ad790-351">Después de que todos los artículos de la carga se empaqueten y ordenen por envío, las cajas se moverán al área de almacenamiento provisional y finalmente se cargarán en un camión.</span><span class="sxs-lookup"><span data-stu-id="ad790-351">After all items from the load are packed and sorted by shipment, the boxes will be moved to the staging area and eventually loaded onto a truck.</span></span>

<span data-ttu-id="ad790-352">Antes de comenzar el escenario, asegúrese de que toda la funcionalidad estándar del almacén esté configurada correctamente para su almacén.</span><span class="sxs-lookup"><span data-stu-id="ad790-352">Before you start the scenario, make sure that all standard warehouse functionality is set up correctly for your warehouse.</span></span> <span data-ttu-id="ad790-353">El almacén estándar *62* de Contoso se utiliza para este propósito.</span><span class="sxs-lookup"><span data-stu-id="ad790-353">Standard Contoso warehouse *62* is used for this purpose.</span></span> <span data-ttu-id="ad790-354">No se han cambiado las configuraciones estándar, aparte de lo que se describe en la configuración.</span><span class="sxs-lookup"><span data-stu-id="ad790-354">Standard configurations haven't been changed, besides what is described in the setup.</span></span>

### <a name="create-demand"></a><span data-ttu-id="ad790-355">Crear demanda</span><span class="sxs-lookup"><span data-stu-id="ad790-355">Create demand</span></span>

<span data-ttu-id="ad790-356">Antes de que se pueda demostrar la funcionalidad, debe crear cierta demanda.</span><span class="sxs-lookup"><span data-stu-id="ad790-356">Before the functionality can be demonstrated, you must create some demand.</span></span> <span data-ttu-id="ad790-357">Para este escenario, creará tres pedidos de ventas para tres clientes diferentes a fin de simular distintas direcciones de entrega.</span><span class="sxs-lookup"><span data-stu-id="ad790-357">For this scenario, you will create three sales orders for three different customers to simulate different delivery addresses.</span></span> <span data-ttu-id="ad790-358">De esta manera, creará tres envíos independientes.</span><span class="sxs-lookup"><span data-stu-id="ad790-358">In this way, you will create three separate shipments.</span></span>

<span data-ttu-id="ad790-359">Antes de crear pedidos de ventas y envíos, asegúrese de que las ubicaciones de selección tengan suficiente inventario para todos los artículos en los pedidos.</span><span class="sxs-lookup"><span data-stu-id="ad790-359">Before you create sales orders and shipments, make sure that the pick locations have enough inventory for all the items on the orders.</span></span> <span data-ttu-id="ad790-360">Revise la configuración de la directiva de ubicación para confirmar las ubicaciones de selección que se utilizan para la selección de pedidos de ventas.</span><span class="sxs-lookup"><span data-stu-id="ad790-360">Review the location directive settings to confirm the picking locations that are used for sales order picking.</span></span> <span data-ttu-id="ad790-361">Si debe ajustar el inventario, puede crear movimientos manuales, utilizar la reposición o utilizar cualquier otro flujo.</span><span class="sxs-lookup"><span data-stu-id="ad790-361">If you must adjust the inventory, you can create manual movements, use replenishment, or use any other flow.</span></span> <span data-ttu-id="ad790-362">A continuación, reserve el inventario.</span><span class="sxs-lookup"><span data-stu-id="ad790-362">Then reserve the inventory.</span></span>

1. <span data-ttu-id="ad790-363">Vaya a **Ventas y marketing \> Pedidos de ventas \> Todos los pedidos de ventas**.</span><span class="sxs-lookup"><span data-stu-id="ad790-363">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="ad790-364">Seleccione **Nuevo** para crear un pedido de ventas para el pedido 1.</span><span class="sxs-lookup"><span data-stu-id="ad790-364">Select **New** to create a sales order for order 1.</span></span>
1. <span data-ttu-id="ad790-365">En el cuadro de diálogo **Crear pedido de ventas**, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="ad790-365">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="ad790-366">**Cliente:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="ad790-366">**Customer:** *US-001*</span></span>
    - <span data-ttu-id="ad790-367">**Almacén**: *62*</span><span class="sxs-lookup"><span data-stu-id="ad790-367">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="ad790-368">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ad790-368">Select **OK**.</span></span>
1. <span data-ttu-id="ad790-369">Se agrega una nueva línea a la ficha desplegable **Líneas de pedido de ventas**.</span><span class="sxs-lookup"><span data-stu-id="ad790-369">A new line is added to the **Sales order lines** FastTab.</span></span> <span data-ttu-id="ad790-370">Establezca los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="ad790-370">Set the following values:</span></span>

    - <span data-ttu-id="ad790-371">**Código de artículo:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="ad790-371">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="ad790-372">**Cantidad:** *5*</span><span class="sxs-lookup"><span data-stu-id="ad790-372">**Quantity:** *5*</span></span>

1. <span data-ttu-id="ad790-373">Seleccione **Agregar línea** para agregar una segunda línea de pedido de compra y establecer los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="ad790-373">Select **Add line** to add a second line, and set the following values:</span></span>

    - <span data-ttu-id="ad790-374">**Código de artículo:** *A0002*</span><span class="sxs-lookup"><span data-stu-id="ad790-374">**Item number:** *A0002*</span></span>
    - <span data-ttu-id="ad790-375">**Cantidad:** *10*</span><span class="sxs-lookup"><span data-stu-id="ad790-375">**Quantity:** *10*</span></span>

1. <span data-ttu-id="ad790-376">Repita los siguientes pasos para cada línea de ventas en el pedido para reservar inventario para este:</span><span class="sxs-lookup"><span data-stu-id="ad790-376">Repeat the following steps for each sales line on the order to reserve inventory for it:</span></span>

    1. <span data-ttu-id="ad790-377">En la ficha desplegable **Líneas de pedido de ventas**, en el menú **Inventario**, seleccione **Reserva**.</span><span class="sxs-lookup"><span data-stu-id="ad790-377">On the **Sales order lines** FastTab, on the **Inventory** menu, select **Reservation**.</span></span>
    1. <span data-ttu-id="ad790-378">En la página **Reserva**, seleccione **Reservar lote** y después cierre la página.</span><span class="sxs-lookup"><span data-stu-id="ad790-378">On the **Reservation** page, select **Reserve lot**, and then close the page.</span></span>
    1. <span data-ttu-id="ad790-379">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="ad790-379">Select **Save**.</span></span>

1. <span data-ttu-id="ad790-380">Seleccione **Nuevo** para crear un pedido de ventas para el pedido 2.</span><span class="sxs-lookup"><span data-stu-id="ad790-380">Select **New** to create a sales order for order 2.</span></span>
1. <span data-ttu-id="ad790-381">En el cuadro de diálogo **Crear pedido de ventas**, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="ad790-381">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="ad790-382">**Cliente:** *US-004*</span><span class="sxs-lookup"><span data-stu-id="ad790-382">**Customer:** *US-004*</span></span>
    - <span data-ttu-id="ad790-383">**Almacén**: *62*</span><span class="sxs-lookup"><span data-stu-id="ad790-383">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="ad790-384">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ad790-384">Select **OK**.</span></span>
1. <span data-ttu-id="ad790-385">Se agrega una nueva línea a la ficha desplegable **Líneas de pedido de ventas**.</span><span class="sxs-lookup"><span data-stu-id="ad790-385">A new line is added to the **Sales order lines** FastTab.</span></span> <span data-ttu-id="ad790-386">Establezca los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="ad790-386">Set the following values:</span></span>

    - <span data-ttu-id="ad790-387">**Código de artículo:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="ad790-387">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="ad790-388">**Cantidad:** *7*</span><span class="sxs-lookup"><span data-stu-id="ad790-388">**Quantity:** *7*</span></span>

1. <span data-ttu-id="ad790-389">Seleccione **Agregar línea** para agregar una segunda línea de pedido de compra y establecer los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="ad790-389">Select **Add line** to add a second line, and set the following values:</span></span>

    - <span data-ttu-id="ad790-390">**Código de artículo:** *A0002*</span><span class="sxs-lookup"><span data-stu-id="ad790-390">**Item number:** *A0002*</span></span>
    - <span data-ttu-id="ad790-391">**Cantidad:** *3*</span><span class="sxs-lookup"><span data-stu-id="ad790-391">**Quantity:** *3*</span></span>

1. <span data-ttu-id="ad790-392">Repita los siguientes pasos para cada línea de ventas en el pedido para reservar inventario para este:</span><span class="sxs-lookup"><span data-stu-id="ad790-392">Repeat the following steps for each sales line on the order to reserve inventory for it:</span></span>

    1. <span data-ttu-id="ad790-393">En la ficha desplegable **Líneas de pedido de ventas**, en el menú **Inventario**, seleccione **Reserva**.</span><span class="sxs-lookup"><span data-stu-id="ad790-393">On the **Sales order lines** FastTab, on the **Inventory** menu, select **Reservation**.</span></span>
    1. <span data-ttu-id="ad790-394">En la página **Reserva**, seleccione **Reservar lote** y después cierre la página.</span><span class="sxs-lookup"><span data-stu-id="ad790-394">On the **Reservation** page, select **Reserve lot**, and then close the page.</span></span>
    1. <span data-ttu-id="ad790-395">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="ad790-395">Select **Save**.</span></span>

1. <span data-ttu-id="ad790-396">Seleccione **Nuevo** para crear un pedido de ventas para el pedido 3.</span><span class="sxs-lookup"><span data-stu-id="ad790-396">Select **New** to create a sales order for order 3.</span></span>
1. <span data-ttu-id="ad790-397">En el cuadro de diálogo **Crear pedido de ventas**, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="ad790-397">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="ad790-398">**Cliente:** *US-007*</span><span class="sxs-lookup"><span data-stu-id="ad790-398">**Customer:** *US-007*</span></span>
    - <span data-ttu-id="ad790-399">**Almacén**: *62*</span><span class="sxs-lookup"><span data-stu-id="ad790-399">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="ad790-400">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ad790-400">Select **OK**.</span></span>
1. <span data-ttu-id="ad790-401">Se agrega una nueva línea a la ficha desplegable **Líneas de pedido de ventas**.</span><span class="sxs-lookup"><span data-stu-id="ad790-401">A new line is added to the **Sales order lines** FastTab.</span></span> <span data-ttu-id="ad790-402">Establezca los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="ad790-402">Set the following values:</span></span>

    - <span data-ttu-id="ad790-403">**Código de artículo:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="ad790-403">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="ad790-404">**Cantidad:** *8*</span><span class="sxs-lookup"><span data-stu-id="ad790-404">**Quantity:** *8*</span></span>

1. <span data-ttu-id="ad790-405">Siga estos pasos para reservar el inventario para la línea de ventas:</span><span class="sxs-lookup"><span data-stu-id="ad790-405">Follow these steps to reserve inventory for the sales line:</span></span>

    1. <span data-ttu-id="ad790-406">En la ficha desplegable **Líneas de pedido de ventas**, en el menú **Inventario**, seleccione **Reserva**.</span><span class="sxs-lookup"><span data-stu-id="ad790-406">On the **Sales order lines** FastTab, on the **Inventory** menu, select **Reservation**.</span></span>
    1. <span data-ttu-id="ad790-407">En la página **Reserva**, seleccione **Reservar lote** y después cierre la página.</span><span class="sxs-lookup"><span data-stu-id="ad790-407">On the **Reservation** page, select **Reserve lot**, and then close the page.</span></span>
    1. <span data-ttu-id="ad790-408">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="ad790-408">Select **Save**.</span></span>

<span data-ttu-id="ad790-409">Complete el siguiente procedimiento para liberar cada pedido de ventas al almacén.</span><span class="sxs-lookup"><span data-stu-id="ad790-409">Complete the following procedure to release each sales order to the warehouse.</span></span> <span data-ttu-id="ad790-410">Se crearán tres envíos diferentes.</span><span class="sxs-lookup"><span data-stu-id="ad790-410">Three different shipments will be created.</span></span> <span data-ttu-id="ad790-411">A continuación, agregará los tres envíos a una nueva oleada.</span><span class="sxs-lookup"><span data-stu-id="ad790-411">You will then add all three shipments to one new wave.</span></span>

1. <span data-ttu-id="ad790-412">Vaya a **Ventas y marketing \> Pedidos de ventas \> Todos los pedidos de ventas**.</span><span class="sxs-lookup"><span data-stu-id="ad790-412">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="ad790-413">En la cuadrícula, seleccione el primer pedido de ventas que creó.</span><span class="sxs-lookup"><span data-stu-id="ad790-413">In the grid, select the first sales order that you created.</span></span>
1. <span data-ttu-id="ad790-414">En el panel de acciones, en la pestaña **Almacén**, seleccione **Liberar al almacén**.</span><span class="sxs-lookup"><span data-stu-id="ad790-414">On the Action Pane, on the **Warehouse** tab, select **Release to warehouse**.</span></span>

    <span data-ttu-id="ad790-415">Recibirá un mensaje informativo que muestra el id. de oleada y el id. de envío que se crearon.</span><span class="sxs-lookup"><span data-stu-id="ad790-415">You receive an informational message that shows the wave ID and shipment ID that were created.</span></span>

1. <span data-ttu-id="ad790-416">Repita los pasos anteriores para liberar los pedidos de ventas 2 y 3 al almacén.</span><span class="sxs-lookup"><span data-stu-id="ad790-416">Repeat the previous steps to release sales orders 2 and 3 to the warehouse.</span></span> <span data-ttu-id="ad790-417">Observe que el mensaje informativo que recibe indica que se ha agregado un envío a la oleada que se creó cuando liberó el pedido de ventas 1.</span><span class="sxs-lookup"><span data-stu-id="ad790-417">Notice that the informational message that you receive indicates that a shipment has been added to the wave that was created when you released sales order 1.</span></span>
1. <span data-ttu-id="ad790-418">Vaya a **Gestión de almacenes \> Oleadas de salida \> Oleadas de envío \> Todas las oleadas**.</span><span class="sxs-lookup"><span data-stu-id="ad790-418">Go to **Warehouse management \> Outbound waves \> Shipment waves \> All waves**.</span></span>
1. <span data-ttu-id="ad790-419">Seleccione el id. de oleada que se creó a partir de la liberación de los pedidos de ventas para abrir la página **Oleadas**.</span><span class="sxs-lookup"><span data-stu-id="ad790-419">Select the wave ID that was created from the release of the sales orders to open the **Waves** page.</span></span> <span data-ttu-id="ad790-420">Esta página muestra los detalles de la oleada.</span><span class="sxs-lookup"><span data-stu-id="ad790-420">This page shows the wave details.</span></span> <span data-ttu-id="ad790-421">La ficha desplegable **Líneas de oleada** muestra los envíos que se crearon.</span><span class="sxs-lookup"><span data-stu-id="ad790-421">The **Wave lines** FastTab shows the shipments that were created.</span></span>

    <span data-ttu-id="ad790-422">Ahora debe crear un trabajo para llevar artículos de las ubicaciones de selección a la ubicación de ordenación.</span><span class="sxs-lookup"><span data-stu-id="ad790-422">You must now create work to bring items from the picking locations to the sorting location.</span></span>

1. <span data-ttu-id="ad790-423">En el panel de acciones, seleccione **Proceso**.</span><span class="sxs-lookup"><span data-stu-id="ad790-423">On the Action Pane, select **Process**.</span></span>

    <span data-ttu-id="ad790-424">Durante el procesamiento de oleadas, el método de ordenación utilizará la plantilla de ordenación para asignar el inventario a las posiciones de ordenación.</span><span class="sxs-lookup"><span data-stu-id="ad790-424">During wave processing, the sorting method will use the sorting template to assign the inventory to sort positions.</span></span> <span data-ttu-id="ad790-425">Cuando se completa el procesamiento de oleadas, recibe un mensaje informativo que indica que se ha registrado la oleada y se ha creado el trabajo.</span><span class="sxs-lookup"><span data-stu-id="ad790-425">When wave processing is completed, you receive an informational message that states that the wave has been posted and work has been created.</span></span>

1. <span data-ttu-id="ad790-426">En el panel de acciones, en la pestaña **Oleada**, en el grupo **Información relacionada**, seleccione **Trabajo** para ver el trabajo que se creó.</span><span class="sxs-lookup"><span data-stu-id="ad790-426">On the Action Pane, on the **Wave** tab, in the **Related information** group, select **Work** to view the work that was created.</span></span> <span data-ttu-id="ad790-427">Anote el id. de trabajo.</span><span class="sxs-lookup"><span data-stu-id="ad790-427">Make a note of the work ID.</span></span>
1. <span data-ttu-id="ad790-428">Vaya a **Gestión de almacenes \> Embalaje y puesta en contenedores \> Asignaciones de posición de ordenación de salida**.</span><span class="sxs-lookup"><span data-stu-id="ad790-428">Go to **Warehouse management \> Packing and containerization \> Outbound sorting position assignments**.</span></span>
1. <span data-ttu-id="ad790-429">En la columna izquierda, puede ver la posición de ordenación de salida que se creó para cada envío.</span><span class="sxs-lookup"><span data-stu-id="ad790-429">In the left column, you can view the outbound sorting position that was created for each shipment.</span></span>
1. <span data-ttu-id="ad790-430">En la ficha desplegable **Criterios de posición de ordenación**, puede ver el id. del envío para esa posición.</span><span class="sxs-lookup"><span data-stu-id="ad790-430">On the **Sort position criteria** FastTab, you can view the shipment ID for that position.</span></span>

<span data-ttu-id="ad790-431">Se ha creado un id. de trabajo para llevar el inventario de las ubicaciones de selección a la ubicación de ordenación.</span><span class="sxs-lookup"><span data-stu-id="ad790-431">One work ID has been created to bring inventory from the picking locations to the sorting location.</span></span> <span data-ttu-id="ad790-432">Para completar el trabajo, necesitará el id. de trabajo que se creó durante el procesamiento de oleadas.</span><span class="sxs-lookup"><span data-stu-id="ad790-432">To complete the work, you will need the work ID that was created during wave processing.</span></span>

### <a name="sales-order-picking-to-the-sorting-location"></a><span data-ttu-id="ad790-433">Selección del pedido de ventas en la ubicación de ordenación</span><span class="sxs-lookup"><span data-stu-id="ad790-433">Sales order picking to the sorting location</span></span>

1. <span data-ttu-id="ad790-434">Inicie sesión en la aplicación móvil como un trabajador en el almacén *62*.</span><span class="sxs-lookup"><span data-stu-id="ad790-434">Sign in to the mobile app as a worker in warehouse *62*.</span></span>
1. <span data-ttu-id="ad790-435">En el menú principal, seleccione **Saliente**.</span><span class="sxs-lookup"><span data-stu-id="ad790-435">On the main menu, select **Outbound**.</span></span>
1. <span data-ttu-id="ad790-436">En el menú **Saliente**, seleccione **Selección de ventas**.</span><span class="sxs-lookup"><span data-stu-id="ad790-436">On the **Outbound** menu, select **Sales Picking**.</span></span>
1. <span data-ttu-id="ad790-437">Selecciona el campo **Id.** y luego introduzca el id. de trabajo del procesamiento de oleadas.</span><span class="sxs-lookup"><span data-stu-id="ad790-437">Select the **ID** field, and then enter the work ID from the wave processing.</span></span>
1. <span data-ttu-id="ad790-438">Confirme su entrada.</span><span class="sxs-lookup"><span data-stu-id="ad790-438">Confirm your entry.</span></span>

    <span data-ttu-id="ad790-439">A continuación, se le pide que introduzca una matrícula de entidad de almacén de destino.</span><span class="sxs-lookup"><span data-stu-id="ad790-439">Next, you're prompted to enter a target license plate (LP).</span></span> <span data-ttu-id="ad790-440">Observe que la línea 1 del pedido de cliente 1 es lo que debe seleccionarse y agregarse a la matrícula de entidad de almacén de destino.</span><span class="sxs-lookup"><span data-stu-id="ad790-440">Notice that line 1 from sales order 1 is what must be picked and added to the target license plate.</span></span> <span data-ttu-id="ad790-441">Se muestran el número de artículo, la cantidad, la descripción del artículo y la ubicación de selección.</span><span class="sxs-lookup"><span data-stu-id="ad790-441">The item number, quantity, item description, and pick location are shown.</span></span>

1. <span data-ttu-id="ad790-442">En el campo **Matrícula de destino**, introduzca una matrícula de entidad de almacén.</span><span class="sxs-lookup"><span data-stu-id="ad790-442">In the **Target LP** field, enter a license plate number.</span></span>

    <span data-ttu-id="ad790-443">Seleccionará todas las líneas que se crearon a partir de la oleada procesada en la misma matrícula de entidad de almacén de destino.</span><span class="sxs-lookup"><span data-stu-id="ad790-443">You will pick all lines that were created from the processed wave onto the same target license plate.</span></span>

1. <span data-ttu-id="ad790-444">Confirme su entrada.</span><span class="sxs-lookup"><span data-stu-id="ad790-444">Confirm your entry.</span></span>

    <span data-ttu-id="ad790-445">La aplicación móvil ahora presenta una serie de páginas **Selección** que le dirigen a la ubicación de selección, y al artículo y la cantidad que debe seleccionarse.</span><span class="sxs-lookup"><span data-stu-id="ad790-445">The mobile app now presents a series of **Pick** pages that point you to the picking location, and to the item and quantity that must be picked.</span></span> <span data-ttu-id="ad790-446">Después de agregar el artículo seleccionado a la matrícula de entidad de almacén, confirmará el trabajo de selección.</span><span class="sxs-lookup"><span data-stu-id="ad790-446">After the picked item is added to the license plate, you will confirm the pick work.</span></span> <span data-ttu-id="ad790-447">La última página será el trabajo para colocar los artículos seleccionados en la ubicación de ordenación.</span><span class="sxs-lookup"><span data-stu-id="ad790-447">The last page will be the work to put the picked items into the sorting location.</span></span>

1. <span data-ttu-id="ad790-448">Confirme el primer trabajo de selección.</span><span class="sxs-lookup"><span data-stu-id="ad790-448">Confirm the first pick work.</span></span>
1. <span data-ttu-id="ad790-449">Se muestra el siguiente trabajo de selección.</span><span class="sxs-lookup"><span data-stu-id="ad790-449">The next pick work is shown.</span></span> <span data-ttu-id="ad790-450">Confirme la selección.</span><span class="sxs-lookup"><span data-stu-id="ad790-450">Confirm the pick.</span></span>
1. <span data-ttu-id="ad790-451">Siga confirmando el trabajo de selección restante.</span><span class="sxs-lookup"><span data-stu-id="ad790-451">Continue to confirm the remaining pick work.</span></span>
1. <span data-ttu-id="ad790-452">El último paso es completar el trabajo de colocación.</span><span class="sxs-lookup"><span data-stu-id="ad790-452">The last step is to complete the put work.</span></span> <span data-ttu-id="ad790-453">Confirme la ubicación en la ubicación de ordenación.</span><span class="sxs-lookup"><span data-stu-id="ad790-453">Confirm the put-away to the sorting location.</span></span>

    <span data-ttu-id="ad790-454">Recibe un mensaje "Trabajo completado".</span><span class="sxs-lookup"><span data-stu-id="ad790-454">You receive a "Work completed" message.</span></span>

1. <span data-ttu-id="ad790-455">Salga de **Selección de ventas** en la aplicación móvil.</span><span class="sxs-lookup"><span data-stu-id="ad790-455">Exit **Sales Picking** on the mobile app.</span></span>

### <a name="sortingput-to-wall"></a><span data-ttu-id="ad790-456">Ordenación/Asignar a contenedor</span><span class="sxs-lookup"><span data-stu-id="ad790-456">Sorting/put-to-wall</span></span>

<span data-ttu-id="ad790-457">Ahora que todo el inventario se ha colocado en la ubicación de ordenación, debe ordenarse en la posición de ordenación correcta.</span><span class="sxs-lookup"><span data-stu-id="ad790-457">Now that all inventory has been put to the sorting location, it must be sorted to the correct sort position.</span></span>

1. <span data-ttu-id="ad790-458">Inicie sesión en la aplicación móvil.</span><span class="sxs-lookup"><span data-stu-id="ad790-458">Sign in to the mobile app.</span></span>
1. <span data-ttu-id="ad790-459">En el menú principal, seleccione **Saliente**.</span><span class="sxs-lookup"><span data-stu-id="ad790-459">On the main menu, select **Outbound**.</span></span>
1. <span data-ttu-id="ad790-460">En el menú **Saliente**, seleccione **Ordenar** para empezar a ordenar los artículos.</span><span class="sxs-lookup"><span data-stu-id="ad790-460">On the **Outbound** menu, select **Sort** to start to sort the items.</span></span>
1. <span data-ttu-id="ad790-461">En el campo **Matrícula/CON**, introduzca la matrícula de entidad de almacén de destino del trabajo de pedido de ventas seleccionado.</span><span class="sxs-lookup"><span data-stu-id="ad790-461">In the **LP/CON** field, enter the target license plate of the picked sales order work.</span></span>
1. <span data-ttu-id="ad790-462">Confirme su entrada.</span><span class="sxs-lookup"><span data-stu-id="ad790-462">Confirm your entry.</span></span>
1. <span data-ttu-id="ad790-463">Introduzca el número de artículo para ordenarlo primero.</span><span class="sxs-lookup"><span data-stu-id="ad790-463">Enter the item number to sort first.</span></span>
1. <span data-ttu-id="ad790-464">El sistema determina la primera posición de ordenación que se debe mostrar.</span><span class="sxs-lookup"><span data-stu-id="ad790-464">The system determines the first sort position that should be shown.</span></span> <span data-ttu-id="ad790-465">Confirme la posición de ordenación.</span><span class="sxs-lookup"><span data-stu-id="ad790-465">Confirm the sort position.</span></span>
1. <span data-ttu-id="ad790-466">Se le pedirá que asigne una matrícula de entidad de almacén a la posición de ordenación.</span><span class="sxs-lookup"><span data-stu-id="ad790-466">You're prompted to assign a license plate to the sort position.</span></span> <span data-ttu-id="ad790-467">Seleccione el campo **Matrícula**, introduzca una matrícula de entidad de almacén y luego confirme su entrada.</span><span class="sxs-lookup"><span data-stu-id="ad790-467">Select the **LP** field, enter a license plate number, and then confirm your entry.</span></span>

    <span data-ttu-id="ad790-468">Debido a que la posición de ordenación está relacionada con el id. de envío, ordenará los artículos seleccionados en una matrícula de entidad de almacén específica para el envío saliente y el pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="ad790-468">Because the sort position is related to the shipment ID, you will sort the picked items into a license plate that is specific to the outbound shipment and sales order.</span></span>

    <span data-ttu-id="ad790-469">La siguiente página muestra el id. del artículo, la cantidad, el id. de posición de ordenación y los id. de matrícula de entidad de almacén "desde" (selección) y "hasta" (ordenación).</span><span class="sxs-lookup"><span data-stu-id="ad790-469">The next page shows the item ID, quantity, sort position ID, and the "from" (picking) and "to" (sorting) license plate IDs.</span></span> <span data-ttu-id="ad790-470">La información de esta página le indica que ordene el artículo y las cantidades especificadas de la matrícula de entidad de almacén de selección en la matrícula de entidad de almacén de ordenación.</span><span class="sxs-lookup"><span data-stu-id="ad790-470">The information on this page instructs you to sort the specified item and quantities from the picking license plate into the sorting license plate.</span></span>

1. <span data-ttu-id="ad790-471">Confirme la posición de ordenación.</span><span class="sxs-lookup"><span data-stu-id="ad790-471">Confirm the sort position.</span></span>
1. <span data-ttu-id="ad790-472">Ordene los artículos en la primera posición de ordenación.</span><span class="sxs-lookup"><span data-stu-id="ad790-472">Sort the items in the first sort position.</span></span> <span data-ttu-id="ad790-473">Cuando haya terminado, el sistema le dirige a la siguiente posición de ordenación.</span><span class="sxs-lookup"><span data-stu-id="ad790-473">When you've finished, the system directs you to the next sort position.</span></span>
1. <span data-ttu-id="ad790-474">Repita este proceso para todas las líneas seleccionadas en la orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="ad790-474">Repeat this process for all picked lines on the work order.</span></span> <span data-ttu-id="ad790-475">También debe usar este proceso cuando haya varias líneas de selección que tengan el mismo número de artículo.</span><span class="sxs-lookup"><span data-stu-id="ad790-475">You should also use this process when there are multiple pick lines that have the same item number.</span></span>

    <span data-ttu-id="ad790-476">A medida que repita este proceso para todos los artículos, el sistema evalúa los criterios del siguiente artículo escaneado (línea de trabajo) y determina en qué posición de ordenación debe colocarse.</span><span class="sxs-lookup"><span data-stu-id="ad790-476">As you repeat this process for all items, the system evaluates the criteria from the next scanned item (work line) and determines which sorting position it should be put to.</span></span> <span data-ttu-id="ad790-477">Se le dirige automáticamente para que coloque el artículo en la posición de ordenación correcta.</span><span class="sxs-lookup"><span data-stu-id="ad790-477">You're automatically directed to put the item to the correct sort position.</span></span> <span data-ttu-id="ad790-478">Según de la configuración de la confirmación, también se le pide que confirme esta acción introduciendo el número de posición o el id. de matrícula de entidad de almacén.</span><span class="sxs-lookup"><span data-stu-id="ad790-478">Depending on the confirmation setup, you're also directed to confirm this action by entering the position number or license plate ID.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ad790-479">Si la ordenación automática está activada, la anulación manual no está disponible.</span><span class="sxs-lookup"><span data-stu-id="ad790-479">If automatic sorting is turned on, manual override isn't available.</span></span>

1. <span data-ttu-id="ad790-480">Cuando haya terminado, en Microsoft Dynamics 365 Supply Chain Management, abra la página **Asignaciones de posición de ordenación de salida** para revisar el estado de las posiciones.</span><span class="sxs-lookup"><span data-stu-id="ad790-480">When you've finished, in Microsoft Dynamics 365 Supply Chain Management, open the **Outbound sorting position assignments** page to review the status of the positions.</span></span>

    - <span data-ttu-id="ad790-481">Si las posiciones se cierran automáticamente, seleccione **Mostrar cerrado** para mostrar las posiciones cerradas.</span><span class="sxs-lookup"><span data-stu-id="ad790-481">If positions are closed automatically, select **Show closed** to show the closed positions.</span></span>
    - <span data-ttu-id="ad790-482">Observe que se muestran las transacciones de posición de ordenación.</span><span class="sxs-lookup"><span data-stu-id="ad790-482">Notice that sort position transactions are shown.</span></span> <span data-ttu-id="ad790-483">Se muestran el artículo y la cantidad que se procesaron a través de la posición.</span><span class="sxs-lookup"><span data-stu-id="ad790-483">The item and quantity that were processed through the position are shown.</span></span>

    <span data-ttu-id="ad790-484">Cuando configura la plantilla de ordenación de salida, establece la opción **Posición de ordenación de cierre automático** en *Sí*.</span><span class="sxs-lookup"><span data-stu-id="ad790-484">When you set up the outbound sorting template, you set the **Auto close sort position** option to *Yes*.</span></span> <span data-ttu-id="ad790-485">Por lo tanto, la posición se cierra automáticamente una vez que se le asigna el último inventario esperado.</span><span class="sxs-lookup"><span data-stu-id="ad790-485">Therefore, the position is automatically closed after the last expected inventory is put to it.</span></span> <span data-ttu-id="ad790-486">Las posiciones de ordenación están en estado **Cerrado** y se ha creado un trabajo para mover el inventario ordenado a una ubicación *Baydoor*.</span><span class="sxs-lookup"><span data-stu-id="ad790-486">The sort positions are in **Closed** status, and work has been created to move the sorted inventory to *Baydoor* location.</span></span>

1. <span data-ttu-id="ad790-487">Complete el trabajo de selección de inventario ordenado para mover el inventario a la ubicación de envío.</span><span class="sxs-lookup"><span data-stu-id="ad790-487">Complete the sorted inventory picking work to move the inventory to the shipping location.</span></span> <span data-ttu-id="ad790-488">Cuando el inventario esté listo, envíelo y confírmelo.</span><span class="sxs-lookup"><span data-stu-id="ad790-488">When the inventory is ready, ship-confirm it.</span></span>

> [!NOTE]
> <span data-ttu-id="ad790-489">Para que el trabajo de selección de inventario ordenado se procese correctamente, un elemento de menú del dispositivo móvil con un id. de clase de trabajo donde el campo **Tipo de orden de trabajo** está establecido en *Selección de inventario ordenado* debe usarse para el movimiento y el proceso de carga.</span><span class="sxs-lookup"><span data-stu-id="ad790-489">For sorted inventory picking work to be processed correctly, a mobile device menu item that has a work class ID where the **Work order type** field is set to *Sorted inventory picking* should be used for the movement and loading process.</span></span>

### <a name="manually-close-a-position-optional"></a><span data-ttu-id="ad790-490">Cerrar manualmente una posición (opcional)</span><span class="sxs-lookup"><span data-stu-id="ad790-490">Manually close a position (optional)</span></span>

<span data-ttu-id="ad790-491">Si las posiciones de ordenación deben cerrarse manualmente, la opción **Posición de ordenación de cierre automático** para la plantilla de ordenación de salida debe establecerse en *No*, y el cierre debe hacerse antes de que el inventario se pueda mover al área de la compuerta.</span><span class="sxs-lookup"><span data-stu-id="ad790-491">If sort positions should be closed manually, the **Auto close sort position** option for the outbound sorting template must be set to *No*, and closing must be done before inventory can be moved to the bay door area.</span></span> <span data-ttu-id="ad790-492">Las posiciones se pueden cerrar de varias maneras:</span><span class="sxs-lookup"><span data-stu-id="ad790-492">Positions can be closed in various ways:</span></span>

- <span data-ttu-id="ad790-493">A través la aplicación de almacén:</span><span class="sxs-lookup"><span data-stu-id="ad790-493">Via the warehouse app:</span></span>

    - <span data-ttu-id="ad790-494">El usuario puede escanear uno de los artículos que ya están en la posición y luego seleccionar **Cerrar** para cerrar la posición.</span><span class="sxs-lookup"><span data-stu-id="ad790-494">The user can scan one of the items that are already on the position and then select **Close** to close the position.</span></span>
    - <span data-ttu-id="ad790-495">Si el usuario escanea un contenedor que ya se ha ordenado, se muestra un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="ad790-495">If the user scans a container that has already been sorted container, an error message is shown.</span></span> <span data-ttu-id="ad790-496">Sin embargo, el usuario puede seguir cerrando la posición.</span><span class="sxs-lookup"><span data-stu-id="ad790-496">However, the user can still continue to close the position.</span></span>

- <span data-ttu-id="ad790-497">Desde la página **Asignaciones de posición de ordenación de salida** de Microsoft Dynamics 365 Supply Chain Management:</span><span class="sxs-lookup"><span data-stu-id="ad790-497">From the Microsoft Dynamics 365 Supply Chain Management **Outbound sorting position assignments** page:</span></span>

    - <span data-ttu-id="ad790-498">El usuario puede seleccionar el registro de posición de ordenación de salida y luego seleccionar **Cerrar posición** en el panel de acciones.</span><span class="sxs-lookup"><span data-stu-id="ad790-498">The user can select the outbound sorting position record and then select **Close position** on the Action Pane.</span></span>

## <a name="tips"></a><span data-ttu-id="ad790-499">Sugerencias</span><span class="sxs-lookup"><span data-stu-id="ad790-499">Tips</span></span>

- <span data-ttu-id="ad790-500">Los artículos no se pueden mover entre posiciones después de haber sido asignados a una.</span><span class="sxs-lookup"><span data-stu-id="ad790-500">Items can't be moved between positions after they have been assigned to one.</span></span> <span data-ttu-id="ad790-501">El sistema evalúa cuántos de cada artículo deben ir a una posición concreta.</span><span class="sxs-lookup"><span data-stu-id="ad790-501">The system evaluates how many of each item should go to a specific position.</span></span>
- <span data-ttu-id="ad790-502">Se puede configurar una plantilla de ordenación para crear contenedores automáticamente cuando las posiciones estén cerradas.</span><span class="sxs-lookup"><span data-stu-id="ad790-502">Sorts template can be configured to automatically create containers when positions are closed.</span></span> <span data-ttu-id="ad790-503">Este enfoque creará una estructura de id. de contenedor estándar que se basa en el perfil de embalaje especificado.</span><span class="sxs-lookup"><span data-stu-id="ad790-503">This approach will create standard container ID structure that is based on the specified packing profile.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ad790-504">Una vez que se haya creado un trabajo de movimiento desde la ubicación de ordenación, no debe cancelar el trabajo.</span><span class="sxs-lookup"><span data-stu-id="ad790-504">After movement work has been created from the sorting location, you must not cancel the work.</span></span> <span data-ttu-id="ad790-505">De lo contrario, la posición y los contenedores que contiene se eliminarán del sistema y no estarán disponibles para su posterior procesamiento.</span><span class="sxs-lookup"><span data-stu-id="ad790-505">Otherwise, the position and the containers in it will be deleted from the system and unavailable for further processing.</span></span> <span data-ttu-id="ad790-506">El inventario también se eliminará.</span><span class="sxs-lookup"><span data-stu-id="ad790-506">The inventory will also be removed.</span></span>