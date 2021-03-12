---
title: Ordenación de salida
description: Este tema proporciona información acerca de la ordenación de salida. Esta funcionalidad facilita el manejo de contenedores pequeños y ayuda a los empleados del almacén a planificar y organizar mejor la capacidad de los pallets en el camión.
author: Mirzaab
manager: tfehr
ms.date: 07/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSPack, WHSOutboundSortTemplate, WHSOutboundSortPositionAssignments, WHSLocationType, WHSLoactionProfile
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-15
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: 2b0049269b69c0777420b3ecd9b1f649c4a1ab11
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4963419"
---
# <a name="outbound-sorting"></a><span data-ttu-id="a8314-104">Ordenación de salida</span><span class="sxs-lookup"><span data-stu-id="a8314-104">Outbound sorting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a8314-105">Esta funcionalidad facilita el manejo de contenedores pequeños y ayuda a los empleados del almacén a planificar y organizar mejor la capacidad de los pallets en el camión.</span><span class="sxs-lookup"><span data-stu-id="a8314-105">This functionality makes it easier to handle small containers and helps warehouse workers better plan and organize pallet capacity in the truck.</span></span> <span data-ttu-id="a8314-106">Cuando utiliza la ordenación de salida, puede ordenar los contenedores empaquetados en el pallet correcto después de que hayan estado en una estación de empaquetado.</span><span class="sxs-lookup"><span data-stu-id="a8314-106">When you use outbound sorting, you can sort packed containers to the correct pallet after they have been at a packing station.</span></span> <span data-ttu-id="a8314-107">También puede crear una jerarquía de empaquetado.</span><span class="sxs-lookup"><span data-stu-id="a8314-107">You can also build a packing hierarchy.</span></span>

<span data-ttu-id="a8314-108">Esta funcionalidad le permite crear pallets a partir de contenedores que se empaquetan a través de la funcionalidad de embalaje.</span><span class="sxs-lookup"><span data-stu-id="a8314-108">This functionality lets you build pallets from containers that are packed through the packing functionality.</span></span> <span data-ttu-id="a8314-109">El contenedor no se envía a la ubicación de envío final, ya que está en el flujo de embalaje original.</span><span class="sxs-lookup"><span data-stu-id="a8314-109">The container isn't sent to the final shipping location as it is in the original packing flow.</span></span> <span data-ttu-id="a8314-110">Por el contrario, los empleados pueden cerrar el contenedor y moverlo a una ubicación de tipo de ordenación.</span><span class="sxs-lookup"><span data-stu-id="a8314-110">Instead, workers can close the container and move it to a sort type location.</span></span> <span data-ttu-id="a8314-111">Luego pueden ordenar los contenedores por posiciones, cada uno de los cuales tiene una matrícula (LP).</span><span class="sxs-lookup"><span data-stu-id="a8314-111">They can then sort containers to positions, each of which has a license plate (LP).</span></span> <span data-ttu-id="a8314-112">Una vez que se han ordenado los contenedores, se puede crear un trabajo para enviar toda la matrícula al muelle de envío final o a las ubicaciones del escenario, según las directivas de ubicación o sus propios requisitos.</span><span class="sxs-lookup"><span data-stu-id="a8314-112">After the containers have been sorted, work can be created to send the whole LP to the final shipping dock or stage locations, based on location directives or your own requirements.</span></span> <span data-ttu-id="a8314-113">Además, la acción de cerrar la posición de ordenación permite mover inmediatamente el inventario a la ubicación de envío final y seleccionarlo para el pedido.</span><span class="sxs-lookup"><span data-stu-id="a8314-113">Additionally, the action of closing of the sort position can immediately move the inventory to the final shipping location and pick it to the order.</span></span>

## <a name="turn-on-the-outbound-sorting-feature"></a><span data-ttu-id="a8314-114">Active la característica de ordenación de salida</span><span class="sxs-lookup"><span data-stu-id="a8314-114">Turn on the Outbound sorting feature</span></span>

<span data-ttu-id="a8314-115">Antes de poder usar la característica debe estar activada en su sistema.</span><span class="sxs-lookup"><span data-stu-id="a8314-115">Before you can use the feature, it must be turned on in your system.</span></span> <span data-ttu-id="a8314-116">Los administradores pueden usar el espacio de trabajo [Administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de la característica y activarla si es necesario.</span><span class="sxs-lookup"><span data-stu-id="a8314-116">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="a8314-117">Allí, la característica se enumera de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="a8314-117">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="a8314-118">**Módulo:** *Gestión de almacén*</span><span class="sxs-lookup"><span data-stu-id="a8314-118">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="a8314-119">**Nombre de la característica:** *Ordenación de salida*</span><span class="sxs-lookup"><span data-stu-id="a8314-119">**Feature name:** *Outbound sorting*</span></span>

## <a name="setup"></a><span data-ttu-id="a8314-120">Configurar</span><span class="sxs-lookup"><span data-stu-id="a8314-120">Setup</span></span>

<span data-ttu-id="a8314-121">En este escenario, debe usar los datos de demostración **USMF** estándar y el almacén *62*.</span><span class="sxs-lookup"><span data-stu-id="a8314-121">For this scenario, you must use standard **USMF** demo data and warehouse *62*.</span></span> <span data-ttu-id="a8314-122">También debe completar la configuración que se describe en las siguientes subsecciones.</span><span class="sxs-lookup"><span data-stu-id="a8314-122">You must also complete the setup that is described in the following subsections.</span></span>

### <a name="set-up-a-wave-template"></a><span data-ttu-id="a8314-123">Configurar una plantilla de oleada</span><span class="sxs-lookup"><span data-stu-id="a8314-123">Set up a wave template</span></span>

<span data-ttu-id="a8314-124">Esta configuración procesa automáticamente la oleada y crear el trabajo cuando una línea se libera al almacén.</span><span class="sxs-lookup"><span data-stu-id="a8314-124">This setup automatically processes the wave and creates work when a line is released to the warehouse.</span></span>

1. <span data-ttu-id="a8314-125">Vaya a **Gestión de almacenes \> Configurar \> Oleadas \> Plantillas de oleada**.</span><span class="sxs-lookup"><span data-stu-id="a8314-125">Go to **Warehouse management \> Setup \> Waves \> Wave templates**.</span></span>
1. <span data-ttu-id="a8314-126">En la lista de plantillas, seleccione **Almacén 62**.</span><span class="sxs-lookup"><span data-stu-id="a8314-126">In the template list, select **Warehouse 62**.</span></span>
1. <span data-ttu-id="a8314-127">En la ficha desplegable **General**, asegúrese de que la opción **Procesar oleada para su liberación al almacén** está establecida en *Sí*.</span><span class="sxs-lookup"><span data-stu-id="a8314-127">On the **General** FastTab, make sure that the **Process wave at release to warehouse** option is set to *Yes*.</span></span>

### <a name="set-up-a-worker"></a><span data-ttu-id="a8314-128">Configuración de un empleado</span><span class="sxs-lookup"><span data-stu-id="a8314-128">Set up a worker</span></span>

<span data-ttu-id="a8314-129">La estación de empaquetado se considera una ubicación.</span><span class="sxs-lookup"><span data-stu-id="a8314-129">The packing station is considered a location.</span></span> <span data-ttu-id="a8314-130">Los empleados del almacén que inician sesión en la estación de empaquetado solo ven y trabajan en envíos y contenedores que están planificados en ese lugar de empaquetado específico.</span><span class="sxs-lookup"><span data-stu-id="a8314-130">Warehouse workers who sign in at the packing station see and work on only shipments and containers that are planned at that specific packing location.</span></span> <span data-ttu-id="a8314-131">Un usuario que inicia sesión en Microsoft Dynamics 365 debe configurarse como empleado en la gestión de almacenes.</span><span class="sxs-lookup"><span data-stu-id="a8314-131">A user who signs in to Microsoft Dynamics 365 must be set up as a worker in Warehouse management.</span></span> <span data-ttu-id="a8314-132">Si el nombre del usuario no aparece en la lista de usuarios del trabajo, utilice el siguiente procedimiento para agregarlo.</span><span class="sxs-lookup"><span data-stu-id="a8314-132">If the user's name doesn't appear in the list of work users, use the following procedure to add it.</span></span>

> [!NOTE]
> <span data-ttu-id="a8314-133">Estos pasos asumen que el usuario ya existe en el sistema y se ha asociado como empleado o trabajador en el módulo **Recursos humanos**.</span><span class="sxs-lookup"><span data-stu-id="a8314-133">These steps assume that the user already exists in the system and has been associated as an employee or worker in the **Human Resources** module.</span></span>

1. <span data-ttu-id="a8314-134">Vaya a **Gestión de almacenes \> Configuración \> Empleado**.</span><span class="sxs-lookup"><span data-stu-id="a8314-134">Go to **Warehouse management \> Setup \> Worker**.</span></span>
1. <span data-ttu-id="a8314-135">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="a8314-135">Select **New**.</span></span>
1. <span data-ttu-id="a8314-136">En el campo **Empleado**, seleccione el usuario de destino en la lista de empleados.</span><span class="sxs-lookup"><span data-stu-id="a8314-136">In the **Worker** field, select the target user in the list of employees.</span></span>
1. <span data-ttu-id="a8314-137">Seleccione **Seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="a8314-137">Select **Select**.</span></span>
1. <span data-ttu-id="a8314-138">En el panel Acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="a8314-138">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="a8314-139">En la ficha desplegable **Usuarios**, seleccione **Nuevo** para crear una cuenta de dispositivo móvil y establezca los siguientes valores para ella:</span><span class="sxs-lookup"><span data-stu-id="a8314-139">On the **Users** FastTab, select **New** to create a mobile device account, and set the following values for it:</span></span>

    - <span data-ttu-id="a8314-140">**Id. de usuario:** introduzca un id. exclusivo.</span><span class="sxs-lookup"><span data-stu-id="a8314-140">**User ID:** Enter a unique ID.</span></span>
    - <span data-ttu-id="a8314-141">**Nombre de usuario:** introduzca un nombre para el Id.</span><span class="sxs-lookup"><span data-stu-id="a8314-141">**User name:** Enter a name for the ID.</span></span>
    - <span data-ttu-id="a8314-142">**Almacén predeterminado:** *62*</span><span class="sxs-lookup"><span data-stu-id="a8314-142">**Default warehouse:** *62*</span></span>
    - <span data-ttu-id="a8314-143">**Nombre del menú:** *Principal*</span><span class="sxs-lookup"><span data-stu-id="a8314-143">**Menu name:** *Main*</span></span>

1. <span data-ttu-id="a8314-144">En el panel Acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="a8314-144">On the Action Pane, select **Save**.</span></span>
1. <span data-ttu-id="a8314-145">Aparece el cuadro de diálogo **Establecer contraseña** donde puede crear una contraseña sencilla que el usuario puede usar para iniciar sesión en la aplicación móvil.</span><span class="sxs-lookup"><span data-stu-id="a8314-145">The **Set password** dialog box appears, where you can create a simple password that the user can use to sign in to the mobile app.</span></span> <span data-ttu-id="a8314-146">Establezca los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="a8314-146">Set the following values:</span></span>

    - <span data-ttu-id="a8314-147">**Contraseña:** introduzca una contraseña sencilla.</span><span class="sxs-lookup"><span data-stu-id="a8314-147">**Password:** Enter a simple password.</span></span>
    - <span data-ttu-id="a8314-148">**Confirmar contraseña:** introduzca de nuevo la misma contraseña.</span><span class="sxs-lookup"><span data-stu-id="a8314-148">**Confirm password:** Enter the same password again.</span></span>

1. <span data-ttu-id="a8314-149">Seleccione **Establecer contraseña**.</span><span class="sxs-lookup"><span data-stu-id="a8314-149">Select **Set password**.</span></span>

    <span data-ttu-id="a8314-150">Una notificación en el Centro de acciones le informa de que la contraseña se ha establecido para el usuario creado.</span><span class="sxs-lookup"><span data-stu-id="a8314-150">A notification in the Action Center informs you that the password has been set for the user that you created.</span></span>

### <a name="create-a-location-type"></a><span data-ttu-id="a8314-151">Crear tipo de ubicación</span><span class="sxs-lookup"><span data-stu-id="a8314-151">Create a location type</span></span>

1. <span data-ttu-id="a8314-152">Vaya a **Gestión de almacenes \> Configurar \> Almacén \> Tipos de ubicación**.</span><span class="sxs-lookup"><span data-stu-id="a8314-152">Go to **Warehouse management \> Setup \> Warehouse \> Location types**.</span></span>
1. <span data-ttu-id="a8314-153">En el panel de acciones, seleccione **Nuevo** para crear un tipo de ubicación y establecer los siguientes valores para él:</span><span class="sxs-lookup"><span data-stu-id="a8314-153">On the Action Pane, select **New** to create a location type, and set the following values for it:</span></span>

    - <span data-ttu-id="a8314-154">**Tipo de ubicación:** *ORDENAR*</span><span class="sxs-lookup"><span data-stu-id="a8314-154">**Location type:** *SORT*</span></span>
    - <span data-ttu-id="a8314-155">**Descripción:** *Ordenar*</span><span class="sxs-lookup"><span data-stu-id="a8314-155">**Description:** *Sort*</span></span>

1. <span data-ttu-id="a8314-156">En el panel Acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="a8314-156">On the Action Pane, select **Save**.</span></span>

### <a name="set-up-warehouse-management-parameters"></a><span data-ttu-id="a8314-157">Configurar parámetros de gestión de almacenes</span><span class="sxs-lookup"><span data-stu-id="a8314-157">Set up Warehouse management parameters</span></span>

1. <span data-ttu-id="a8314-158">Vaya a **Gestión de almacenes \> Configuración \> Parámetros de gestión de almacenes**.</span><span class="sxs-lookup"><span data-stu-id="a8314-158">Go to **Warehouse management \> Setup \> Warehouse management parameters**.</span></span>
1. <span data-ttu-id="a8314-159">En la pestaña **General**, en la ficha desplegable **Tipos de ubicación**, establezca el campo **Tipo de ubicación de ordenación** en *ORDENAR*.</span><span class="sxs-lookup"><span data-stu-id="a8314-159">On the **General** tab, on the **Location types** FastTab, set the **Sorting location type** field to *SORT*.</span></span>
1. <span data-ttu-id="a8314-160">En el panel Acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="a8314-160">On the Action Pane, select **Save**.</span></span>

### <a name="set-up-a-location-profile"></a><span data-ttu-id="a8314-161">Configurar un perfil de ubicación</span><span class="sxs-lookup"><span data-stu-id="a8314-161">Set up a location profile</span></span>

1. <span data-ttu-id="a8314-162">Vaya a **Gestión de almacenes \> Configurar \> Almacén \> Perfiles de ubicación**.</span><span class="sxs-lookup"><span data-stu-id="a8314-162">Go to **Warehouse management \> Setup \> Warehouse \> Location profiles**.</span></span>
1. <span data-ttu-id="a8314-163">En el panel de acciones, haga clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="a8314-163">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="a8314-164">Establezca los siguientes valores en el encabezado:</span><span class="sxs-lookup"><span data-stu-id="a8314-164">In the header, set the following values:</span></span>

    - <span data-ttu-id="a8314-165">**Id. de perfil de ubicación:** *Ordenación*</span><span class="sxs-lookup"><span data-stu-id="a8314-165">**Location profile ID:** *Sorting*</span></span>
    - <span data-ttu-id="a8314-166">**Nombre:** *Ordenación*</span><span class="sxs-lookup"><span data-stu-id="a8314-166">**Name:** *Sorting*</span></span>

1. <span data-ttu-id="a8314-167">En la ficha desplegable **General**, establezca los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="a8314-167">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="a8314-168">**Formato de ubicación:** *ASRB* (pasillo, estantería, balda y hueco)</span><span class="sxs-lookup"><span data-stu-id="a8314-168">**Location format:** *ASRB* (Aisle-Rack-Shelf-Bin)</span></span>
    - <span data-ttu-id="a8314-169">**Tipo de ubicación:** *ORDENAR*</span><span class="sxs-lookup"><span data-stu-id="a8314-169">**Location type:** *SORT*</span></span>
    - <span data-ttu-id="a8314-170">**Usar seguimiento de matrículas de entidad de almacén:** *Sí*</span><span class="sxs-lookup"><span data-stu-id="a8314-170">**Use license plate tracking:** *Yes*</span></span>
    - <span data-ttu-id="a8314-171">**Permitir artículos combinados:** *Sí* (Cuando configura esta opción en *Sí*, la opción **Permitir lotes de inventario mixtos** se configura automáticamente en *Sí* y no se puede cambiar de forma independiente).</span><span class="sxs-lookup"><span data-stu-id="a8314-171">**Allow mixed items:** *Yes* (When you set this option to *Yes*, the **Allow mixed inventory batches** option is automatically set to *Yes* and can't be changed independently.)</span></span>

1. <span data-ttu-id="a8314-172">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="a8314-172">Select **Save**.</span></span>

### <a name="set-up-a-location"></a><span data-ttu-id="a8314-173">Configurar una ubicación</span><span class="sxs-lookup"><span data-stu-id="a8314-173">Set up a location</span></span>

1. <span data-ttu-id="a8314-174">Vaya a **Gestión de almacenes \> Configurar \> Almacén \> Ubicaciones**.</span><span class="sxs-lookup"><span data-stu-id="a8314-174">Go to **Warehouse management \> Setup \> Warehouse \> Locations**.</span></span>
1. <span data-ttu-id="a8314-175">En el encabezado, borre la casilla **Generar dígitos de control para la ubicación**.</span><span class="sxs-lookup"><span data-stu-id="a8314-175">In the header, clear the **Generate check digits for location** check box.</span></span>
1. <span data-ttu-id="a8314-176">En el panel de acciones, seleccione **Nuevo** para crear una ubicación y establecer los siguientes valores para él:</span><span class="sxs-lookup"><span data-stu-id="a8314-176">On the Action Pane, select **New** to create a location, and set the following values for it:</span></span>

    - <span data-ttu-id="a8314-177">**Almacén**: *62*</span><span class="sxs-lookup"><span data-stu-id="a8314-177">**Warehouse:** *62*</span></span>
    - <span data-ttu-id="a8314-178">**Ubicación:** *SORT*</span><span class="sxs-lookup"><span data-stu-id="a8314-178">**Location:** *SORT*</span></span>
    - <span data-ttu-id="a8314-179">**Id. de perfil de ubicación:** *ORDENACIÓN*</span><span class="sxs-lookup"><span data-stu-id="a8314-179">**Location profile ID:** *SORTING*</span></span>

1. <span data-ttu-id="a8314-180">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="a8314-180">Select **Save**.</span></span>

### <a name="set-up-an-outbound-sorting-template"></a><span data-ttu-id="a8314-181">Configurar una plantilla de ordenación de salida</span><span class="sxs-lookup"><span data-stu-id="a8314-181">Set up an outbound sorting template</span></span>

<span data-ttu-id="a8314-182">La plantilla de ordenación de salida determina si el trabajo se crea fuera de la ubicación de ordenación y si la ordenación se realiza de forma manual o automática.</span><span class="sxs-lookup"><span data-stu-id="a8314-182">The outbound sorting template determines whether work is created out of the sort location, and whether sorting is done manually or automatically.</span></span>

<span data-ttu-id="a8314-183">En este escenario, creará una plantilla de ordenación de salida para crear pallets después de la estación de empaquetado.</span><span class="sxs-lookup"><span data-stu-id="a8314-183">For this scenario, you will create an outbound sorting template to build pallets after the packing station.</span></span>

1. <span data-ttu-id="a8314-184">Vaya a **Gestión de almacenes \> Configuración \> Embalado \> Plantillas de ordenación salientes**.</span><span class="sxs-lookup"><span data-stu-id="a8314-184">Go to **Warehouse Management \> Setup \> Packing \> Outbound sorting template**.</span></span>
1. <span data-ttu-id="a8314-185">En el panel de acciones, haga clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="a8314-185">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="a8314-186">En el encabezado de la nueva plantilla, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="a8314-186">In the header of the new template, set the following values:</span></span>

    - <span data-ttu-id="a8314-187">**Id. de plantilla de ordenación de salida:** *AutoWork*</span><span class="sxs-lookup"><span data-stu-id="a8314-187">**Outbound sorting template ID:** *AutoWork*</span></span>
    - <span data-ttu-id="a8314-188">**Descripción:** *Creación de AutoWork*</span><span class="sxs-lookup"><span data-stu-id="a8314-188">**Description:** *Auto Work Creation*</span></span>
    - <span data-ttu-id="a8314-189">**Tipo de plantilla de ordenación de salida:** *Contenedor*</span><span class="sxs-lookup"><span data-stu-id="a8314-189">**Outbound sorting template type:** *Container*</span></span>
    - <span data-ttu-id="a8314-190">**Almacén**: *62*</span><span class="sxs-lookup"><span data-stu-id="a8314-190">**Warehouse:** *62*</span></span>
    - <span data-ttu-id="a8314-191">**Ubicación:** *SORT*</span><span class="sxs-lookup"><span data-stu-id="a8314-191">**Location:** *SORT*</span></span>

1. <span data-ttu-id="a8314-192">En la ficha desplegable **General**, establezca los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="a8314-192">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="a8314-193">**Comprobación del orden:** *Escaneo de posición*.</span><span class="sxs-lookup"><span data-stu-id="a8314-193">**Sort verification:** *Position scan*</span></span>
    - <span data-ttu-id="a8314-194">**Crear trabajo en posición cerrada:** *Sí*</span><span class="sxs-lookup"><span data-stu-id="a8314-194">**Create work on position close:** *Yes*</span></span>

        <span data-ttu-id="a8314-195">Si la opción se establece en *Sí*, cuando la posición se cierre, se creará el trabajo para mover el inventario a la ubicación de envío final.</span><span class="sxs-lookup"><span data-stu-id="a8314-195">If this option is set to *Yes*, when the position is closed, work will be created to move inventory to the final shipping location.</span></span> <span data-ttu-id="a8314-196">Si se establece en *No*, el inventario se seleccionará inmediatamente para el pedido cuando se cierre la posición.</span><span class="sxs-lookup"><span data-stu-id="a8314-196">If it's set to *No*, inventory will immediately be picked to the order when the position is closed.</span></span>

    - <span data-ttu-id="a8314-197">**Asignación de posición:** *Automática*</span><span class="sxs-lookup"><span data-stu-id="a8314-197">**Position assignment:** *Automatic*</span></span>

        <span data-ttu-id="a8314-198">Si este campo se establece en *Manual*, el usuario debe indicar siempre en qué posición se debe ordenar el inventario.</span><span class="sxs-lookup"><span data-stu-id="a8314-198">If this field is set to *Manual*, the user must always indicate which position the inventory should be sorted to.</span></span> <span data-ttu-id="a8314-199">Si este campo se establece en *Automático*, el sistema automáticamente dirigirá el inventario a una posición cuando sea posible, en función de los descansos de la plantilla de ordenación.</span><span class="sxs-lookup"><span data-stu-id="a8314-199">If it's set to *Automatic*, the system will automatically guide the inventory to a position whenever it can, based on the sort template breaks.</span></span>

1. <span data-ttu-id="a8314-200">Seleccione **Guardar** para hacer que el botón **Editar consulta** esté disponible en el panel de acciones.</span><span class="sxs-lookup"><span data-stu-id="a8314-200">Select **Save** to make the **Edit query** button on the Action Pane available.</span></span>
1. <span data-ttu-id="a8314-201">En el panel de acciones, seleccione **Editar consulta**.</span><span class="sxs-lookup"><span data-stu-id="a8314-201">On the Action Pane, select **Edit Query**.</span></span>
1. <span data-ttu-id="a8314-202">En el cuadro editor de consultas, en la pestaña **Ordenación**, seleccione una línea que tenga los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="a8314-202">In the query editor, on the **Sorting** tab, add a line that has the following values:</span></span>

    - <span data-ttu-id="a8314-203">**Tabla:** *Envíos*</span><span class="sxs-lookup"><span data-stu-id="a8314-203">**Table:** *Shipments*</span></span>
    - <span data-ttu-id="a8314-204">**Tabla derivada:** *Envíos*</span><span class="sxs-lookup"><span data-stu-id="a8314-204">**Derived table:** *Shipments*</span></span>
    - <span data-ttu-id="a8314-205">**Campo:** *Servicio de transportista*</span><span class="sxs-lookup"><span data-stu-id="a8314-205">**Field:** *Carrier service*</span></span>

        <span data-ttu-id="a8314-206">Al seleccionar este valor, puede que reciba el siguiente mensaje: "El campo Servicio de transportista no es un campo de índice.</span><span class="sxs-lookup"><span data-stu-id="a8314-206">When you select this value, you might receive the following message: "Field Carrier service is not an index field.</span></span> <span data-ttu-id="a8314-207">¿Desea agregar una ordenación a esto?"</span><span class="sxs-lookup"><span data-stu-id="a8314-207">Do you want to add sorting on this?"</span></span> <span data-ttu-id="a8314-208">Seleccione **Sí**.</span><span class="sxs-lookup"><span data-stu-id="a8314-208">Select **Yes**.</span></span>

    - <span data-ttu-id="a8314-209">**Dirección de búsqueda:** *Ascendente*</span><span class="sxs-lookup"><span data-stu-id="a8314-209">**Search direction:** *Ascending*</span></span>

1. <span data-ttu-id="a8314-210">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a8314-210">Select **OK**.</span></span>
1. <span data-ttu-id="a8314-211">Es posible que reciba el siguiente mensaje: "La agrupación se restablecerá, ¿continuar?"</span><span class="sxs-lookup"><span data-stu-id="a8314-211">You might receive the following message: "Grouping will be reset, continue?"</span></span> <span data-ttu-id="a8314-212">Seleccione **Sí**.</span><span class="sxs-lookup"><span data-stu-id="a8314-212">Select **Yes**.</span></span>

    <span data-ttu-id="a8314-213">El botón **Descansos de la plantilla de ordenación de salida** del panel de acciones estará disponible.</span><span class="sxs-lookup"><span data-stu-id="a8314-213">The **Outbound sorting template breaks** button on the Action Pane becomes available.</span></span>

1. <span data-ttu-id="a8314-214">En el panel de acciones, seleccione **Descansos de la plantilla de ordenación de salida**.</span><span class="sxs-lookup"><span data-stu-id="a8314-214">On the Action Pane, select **Outbound sorting template breaks**.</span></span>
1. <span data-ttu-id="a8314-215">En el cuadro de diálogo **Criterios de ordenación de salida**, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="a8314-215">In the **Outbound sorting criteria** dialog box, set the following values:</span></span>

    - <span data-ttu-id="a8314-216">**Nombre de la tabla de referencia:** *Envíos*</span><span class="sxs-lookup"><span data-stu-id="a8314-216">**Reference table name:** *Shipments*</span></span>
    - <span data-ttu-id="a8314-217">**Nombre del campo de referencia:** *Servicio de transportista*</span><span class="sxs-lookup"><span data-stu-id="a8314-217">**Reference field name:** *Carrier service*</span></span>
    - <span data-ttu-id="a8314-218">**Agrupar por campo**: seleccione esta casilla para agrupar los envíos por servicio de transportista.</span><span class="sxs-lookup"><span data-stu-id="a8314-218">**Group by field:** Select this check box to group shipments by carrier service.</span></span>

1. <span data-ttu-id="a8314-219">Seleccione **Aceptar** para guardar la configuración y cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="a8314-219">Select **OK** to save your settings and close the dialog box.</span></span>

### <a name="set-up-container-packing-policies"></a><span data-ttu-id="a8314-220">Configurar políticas de embalaje de contenedores</span><span class="sxs-lookup"><span data-stu-id="a8314-220">Set up container packing policies</span></span>

1. <span data-ttu-id="a8314-221">Vaya a **Administración de almacenes \> Configurar \> Contenedores \> Perfiles de cierre de contenedor**.</span><span class="sxs-lookup"><span data-stu-id="a8314-221">Go to **Warehouse management \> Setup \> Containers \> Container packing policies**.</span></span>
1. <span data-ttu-id="a8314-222">En el panel de acciones, haga clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="a8314-222">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="a8314-223">En el encabezado de la nueva política, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="a8314-223">In the header of the new policy, set the following values:</span></span>

    - <span data-ttu-id="a8314-224">**Directiva de embalaje de contenedores:** *Ordenar*</span><span class="sxs-lookup"><span data-stu-id="a8314-224">**Container packing policy:** *Sort*</span></span>
    - <span data-ttu-id="a8314-225">**Descripción:** *Ordenar*</span><span class="sxs-lookup"><span data-stu-id="a8314-225">**Description:** *Sort*</span></span>

1. <span data-ttu-id="a8314-226">En la ficha desplegable **Visión general**, establezca los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="a8314-226">On the **Overview** FastTab, set the following values:</span></span>

    - <span data-ttu-id="a8314-227">**Almacén**: *62*</span><span class="sxs-lookup"><span data-stu-id="a8314-227">**Warehouse:** *62*</span></span>
    - <span data-ttu-id="a8314-228">**Ubicación predeterminada para ordenación:** *ORDENAR*</span><span class="sxs-lookup"><span data-stu-id="a8314-228">**Default location for sorting:** *SORT*</span></span>
    - <span data-ttu-id="a8314-229">**Unidad de peso:** *kg*</span><span class="sxs-lookup"><span data-stu-id="a8314-229">**Weight unit:** *kg*</span></span>
    - <span data-ttu-id="a8314-230">**Directiva de cierre del contenedor:** *Liberación automática*</span><span class="sxs-lookup"><span data-stu-id="a8314-230">**Container closing policy:** *Automatic release*</span></span>
    - <span data-ttu-id="a8314-231">**Directiva de lanzamiento de contenedores:** *Asignar contenedor a la posición de ordenación de salida*</span><span class="sxs-lookup"><span data-stu-id="a8314-231">**Container release policy:** *Assign container to outbound sorting position*</span></span>

1. <span data-ttu-id="a8314-232">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="a8314-232">Select **Save**.</span></span>

### <a name="set-up-packing-profiles"></a><span data-ttu-id="a8314-233">Configurar perfiles de embalaje</span><span class="sxs-lookup"><span data-stu-id="a8314-233">Set up packing profiles</span></span>

<span data-ttu-id="a8314-234">Cree un nuevo perfil de embalaje que se usará junto con la funcionalidad de ordenación.</span><span class="sxs-lookup"><span data-stu-id="a8314-234">Create a new packing profile that will be used together with the sorting functionality.</span></span>

1. <span data-ttu-id="a8314-235">Vaya a **Gestión de almacenes \> Configurar \> Embalaje \> Perfiles de embalaje**.</span><span class="sxs-lookup"><span data-stu-id="a8314-235">Go to **Warehouse management \> Setup \> Packing \> Packing profiles**.</span></span>
1. <span data-ttu-id="a8314-236">En el panel de acciones, seleccione **Nuevo** para crear una línea y establecer los siguientes valores para él:</span><span class="sxs-lookup"><span data-stu-id="a8314-236">On the Action Pane, select **New** to create a line, and set the following values for it:</span></span>

    - <span data-ttu-id="a8314-237">**Id. de perfil de empaquetado:** *Ordenar*</span><span class="sxs-lookup"><span data-stu-id="a8314-237">**Packing profile ID:** *Sort*</span></span>
    - <span data-ttu-id="a8314-238">**Descripción:** *Ordenar*</span><span class="sxs-lookup"><span data-stu-id="a8314-238">**Description:** *Sort*</span></span>
    - <span data-ttu-id="a8314-239">**Directiva de embalaje de contenedores:** *Ordenar*</span><span class="sxs-lookup"><span data-stu-id="a8314-239">**Container packing policy:** *Sort*</span></span>
    - <span data-ttu-id="a8314-240">**Modo del id. de contenedor:** *Automático*</span><span class="sxs-lookup"><span data-stu-id="a8314-240">**Container ID mode:** *Auto*</span></span>
    - <span data-ttu-id="a8314-241">**Tipo de contenedor:** *Caja grande*</span><span class="sxs-lookup"><span data-stu-id="a8314-241">**Container type:** *Box-Large*</span></span>
    - <span data-ttu-id="a8314-242">**Crear contenedor automáticamente al cerrar el contenedor:** Desactivado (= *No*)</span><span class="sxs-lookup"><span data-stu-id="a8314-242">**Auto create container at container close:** Cleared (= *No*)</span></span>

1. <span data-ttu-id="a8314-243">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="a8314-243">Select **Save**.</span></span>

### <a name="set-up-work-classes"></a><span data-ttu-id="a8314-244">Configurar de clases de trabajo</span><span class="sxs-lookup"><span data-stu-id="a8314-244">Set up work classes</span></span>

<span data-ttu-id="a8314-245">Configure una clase de trabajo que se usará junto con la ordenación.</span><span class="sxs-lookup"><span data-stu-id="a8314-245">Set up a work class that will be used together with sorting.</span></span>

1. <span data-ttu-id="a8314-246">Vaya a **Gestión de almacenes \> Configurar \> Trabajo \> Clases de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="a8314-246">Go to **Warehouse management \> Setup \> Work \> Work classes**.</span></span>
1. <span data-ttu-id="a8314-247">En el panel de acciones, seleccione **Nuevo** para crear una clase de trabajo para la ordenación y establecer los siguientes valores para él:</span><span class="sxs-lookup"><span data-stu-id="a8314-247">On the Action Pane, select **New** to create a work class for sorting, and set the following values for it:</span></span>

    - <span data-ttu-id="a8314-248">**Id. de la clase de trabajo:** *Ordenar*</span><span class="sxs-lookup"><span data-stu-id="a8314-248">**Work class ID:** *Sort*</span></span>
    - <span data-ttu-id="a8314-249">**Descripción:** *Ordenar*</span><span class="sxs-lookup"><span data-stu-id="a8314-249">**Description:** *Sort*</span></span>
    - <span data-ttu-id="a8314-250">**Tipo de orden de trabajo:** *Selección de inventario ordenado*</span><span class="sxs-lookup"><span data-stu-id="a8314-250">**Work order type:** *Sorted inventory picking*</span></span>

1. <span data-ttu-id="a8314-251">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="a8314-251">Select **Save**.</span></span>

### <a name="set-up-mobile-device-menu-items"></a><span data-ttu-id="a8314-252">Configurar elementos de menú del dispositivo móvil</span><span class="sxs-lookup"><span data-stu-id="a8314-252">Set up mobile device menu items</span></span>

#### <a name="set-up-a-new-pallet-menu-item"></a><span data-ttu-id="a8314-253">Configurar un nuevo elemento de menú de pallet</span><span class="sxs-lookup"><span data-stu-id="a8314-253">Set up a new pallet menu item</span></span>

<span data-ttu-id="a8314-254">Cree un elemento de menú del dispositivo móvil para crear pallets durante la ordenación.</span><span class="sxs-lookup"><span data-stu-id="a8314-254">Create a mobile device menu item to build pallets during sorting.</span></span>

1. <span data-ttu-id="a8314-255">Vaya a **Administración de almacenes \> Configurar \> Dispositivo móvil \> Elementos de menú del dispositivo móvil**.</span><span class="sxs-lookup"><span data-stu-id="a8314-255">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="a8314-256">En el panel de acciones, haga clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="a8314-256">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="a8314-257">Establezca los siguientes valores en el encabezado:</span><span class="sxs-lookup"><span data-stu-id="a8314-257">In the header, set the following values:</span></span>

    - <span data-ttu-id="a8314-258">**Nombre del elemento del menú:** *Crear pallet*</span><span class="sxs-lookup"><span data-stu-id="a8314-258">**Menu item name:** *Pallet build*</span></span>
    - <span data-ttu-id="a8314-259">**Título:** *Crear pallet*</span><span class="sxs-lookup"><span data-stu-id="a8314-259">**Title:** *Pallet build*</span></span>
    - <span data-ttu-id="a8314-260">**Modo:** *Indirecto*</span><span class="sxs-lookup"><span data-stu-id="a8314-260">**Mode:** *Indirect*</span></span>
    - <span data-ttu-id="a8314-261">**Usar trabajo existente:** *No*</span><span class="sxs-lookup"><span data-stu-id="a8314-261">**Use existing work:** *No*</span></span>

1. <span data-ttu-id="a8314-262">En la ficha desplegable **General**, establezca los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="a8314-262">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="a8314-263">**Código de actividad:** *Ordenación de salida*</span><span class="sxs-lookup"><span data-stu-id="a8314-263">**Activity code:** *Outbound sorting*</span></span>

        <span data-ttu-id="a8314-264">Cuando este campo se establece en *Ordenación de salida*, aparece el campo **Id. de plantilla de ordenación de salida**.</span><span class="sxs-lookup"><span data-stu-id="a8314-264">When this field is set to *Outbound sorting*, the **Outbound sorting template ID** field is shown.</span></span>

    - <span data-ttu-id="a8314-265">**Usar guía de proceso:** *Sí*</span><span class="sxs-lookup"><span data-stu-id="a8314-265">**Use process guide:** *Yes*</span></span>

        <span data-ttu-id="a8314-266">Cuando el campo **Código de actividad** se establece en *Ordenación de salida*, esta opción se establece automáticamente en *Sí*.</span><span class="sxs-lookup"><span data-stu-id="a8314-266">When the **Activity code** field is set to *Outbound sorting*, this option is automatically set to *Yes*.</span></span>

    - <span data-ttu-id="a8314-267">**Id. de plantilla de ordenación de salida:** *AutoWork*</span><span class="sxs-lookup"><span data-stu-id="a8314-267">**Outbound sorting template ID:** *AutoWork*</span></span>

1. <span data-ttu-id="a8314-268">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="a8314-268">Select **Save**.</span></span>

#### <a name="set-up-a-new-loading-menu-item"></a><span data-ttu-id="a8314-269">Configurar un nuevo elemento de menú de carga</span><span class="sxs-lookup"><span data-stu-id="a8314-269">Set up a new loading menu item</span></span>

<span data-ttu-id="a8314-270">A continuación, cree un elemento de menú que permita a los usuarios mover los elementos de inventario ordenados a la ubicación de envío.</span><span class="sxs-lookup"><span data-stu-id="a8314-270">Next, create a menu item that lets users move the sorted inventory items to the shipping location.</span></span>

1. <span data-ttu-id="a8314-271">Vaya a **Administración de almacenes \> Configurar \> Dispositivo móvil \> Elementos de menú del dispositivo móvil**.</span><span class="sxs-lookup"><span data-stu-id="a8314-271">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="a8314-272">En el panel de acciones, haga clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="a8314-272">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="a8314-273">Establezca los siguientes valores en el encabezado:</span><span class="sxs-lookup"><span data-stu-id="a8314-273">In the header, set the following values:</span></span>

    - <span data-ttu-id="a8314-274">**Nombre del elemento del menú:** *Cargar desde ordenación*</span><span class="sxs-lookup"><span data-stu-id="a8314-274">**Menu item name:** *Load from Sorting*</span></span>
    - <span data-ttu-id="a8314-275">**Título:** *Cargar desde ordenación*</span><span class="sxs-lookup"><span data-stu-id="a8314-275">**Title:** *Load from Sorting*</span></span>
    - <span data-ttu-id="a8314-276">**Modo:** *Trabajo*</span><span class="sxs-lookup"><span data-stu-id="a8314-276">**Mode:** *Work*</span></span>
    - <span data-ttu-id="a8314-277">**Usar trabajo existente:** *Sí*</span><span class="sxs-lookup"><span data-stu-id="a8314-277">**Use existing work:** *Yes*</span></span>

1. <span data-ttu-id="a8314-278">En la ficha desplegable **General**, establezca el campo **Dirigido por** en *Dirigido por el usuario*.</span><span class="sxs-lookup"><span data-stu-id="a8314-278">On the **General** FastTab, set the **Directed by** field to *User directed*.</span></span>
1. <span data-ttu-id="a8314-279">En la ficha desplegable **Clases de trabajo**, seleccione **Nuevo** y luego establezca los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="a8314-279">On the **Work classes** FastTab, select **New**, and then set the following values:</span></span>

    - <span data-ttu-id="a8314-280">**Id. de la clase de trabajo:** *ORDENAR*</span><span class="sxs-lookup"><span data-stu-id="a8314-280">**Work class ID:** *SORT*</span></span>
    - <span data-ttu-id="a8314-281">**Tipo de orden de trabajo:** *Selección de inventario ordenado*</span><span class="sxs-lookup"><span data-stu-id="a8314-281">**Work order type:** *Sorted inventory picking*</span></span>

1. <span data-ttu-id="a8314-282">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="a8314-282">Select **Save**.</span></span>

### <a name="set-up-the-mobile-device-menu"></a><span data-ttu-id="a8314-283">Configurar el menú de dispositivo móvil</span><span class="sxs-lookup"><span data-stu-id="a8314-283">Set up the mobile device menu</span></span>

<span data-ttu-id="a8314-284">Ahora debe agregar los nuevos elementos del menú al menú del dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="a8314-284">You must now add the new menu items to the mobile device menu.</span></span>

1. <span data-ttu-id="a8314-285">Vaya a **Administración de almacenes \> Configuración \> Dispositivo móvil \> Menú del dispositivo móvil**.</span><span class="sxs-lookup"><span data-stu-id="a8314-285">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu**.</span></span>
1. <span data-ttu-id="a8314-286">Seleccione el menú **Saliente**.</span><span class="sxs-lookup"><span data-stu-id="a8314-286">Select the **Outbound** menu.</span></span>
1. <span data-ttu-id="a8314-287">En el panel Acciones, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="a8314-287">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="a8314-288">En la columna **Menús disponibles y elementos de menú**, busque y seleccione **Crear pallet**.</span><span class="sxs-lookup"><span data-stu-id="a8314-288">In the **Available menus and menu items** column, find and select **Pallet build**.</span></span>
1. <span data-ttu-id="a8314-289">Seleccione el botón de flecha derecha para mover **Crear pallet** a la columna **Estructura del menú**.</span><span class="sxs-lookup"><span data-stu-id="a8314-289">Select the right arrow button to move **Pallet build** to the **Menu structure** column.</span></span>
1. <span data-ttu-id="a8314-290">Use los botones de flecha arriba y flecha abajo para poner el elemento del menú **Crear pallet** en la posición deseada del menú del dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="a8314-290">Use the up arrow and down arrow buttons to put the **Pallet build** menu item in the desired position on the mobile device menu.</span></span>
1. <span data-ttu-id="a8314-291">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="a8314-291">Select **Save**.</span></span>
1. <span data-ttu-id="a8314-292">Repita este procedimiento para agregar el elemento del menú **Cargar desde ordenación** al menú **Salida**.</span><span class="sxs-lookup"><span data-stu-id="a8314-292">Repeat this procedure to add the **Load from Sorting** menu item to the **Outbound** menu.</span></span>

### <a name="set-up-location-directives"></a><span data-ttu-id="a8314-293">Configurar directivas de ubicación</span><span class="sxs-lookup"><span data-stu-id="a8314-293">Set up location directives</span></span>

<span data-ttu-id="a8314-294">Las *directivas de ubicación* son reglas que ayudan a identifica las ubicaciones de picking y de colocación para el movimiento de inventario.</span><span class="sxs-lookup"><span data-stu-id="a8314-294">*Location directives* are rules that help identify pick and put locations for inventory movement.</span></span> <span data-ttu-id="a8314-295">Ahora debe crear una regla para administrar el trabajo de ordenación.</span><span class="sxs-lookup"><span data-stu-id="a8314-295">You must now create a rule to manage the sorting work.</span></span>

#### <a name="set-up-a-single-sku-directive"></a><span data-ttu-id="a8314-296">Configurar una directiva SKU única</span><span class="sxs-lookup"><span data-stu-id="a8314-296">Set up a single-SKU directive</span></span>

1. <span data-ttu-id="a8314-297">Vaya a **Gestión de almacenes \> Configurar \> Directivas de ubicación**.</span><span class="sxs-lookup"><span data-stu-id="a8314-297">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="a8314-298">En el panel izquierdo, cambie el valor del campo **Tipo de orden de trabajo** a *Selección de inventario ordenado*.</span><span class="sxs-lookup"><span data-stu-id="a8314-298">In the left pane, change the value of the **Work order type** field to *Sorted inventory picking*.</span></span>
1. <span data-ttu-id="a8314-299">En el panel de acciones, haga clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="a8314-299">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="a8314-300">Establezca los siguientes valores en el encabezado:</span><span class="sxs-lookup"><span data-stu-id="a8314-300">In the header, set the following values:</span></span>

    - <span data-ttu-id="a8314-301">**Secuencia**: *1*</span><span class="sxs-lookup"><span data-stu-id="a8314-301">**Sequence:** *1*</span></span>
    - <span data-ttu-id="a8314-302">**Nombre:** *Baydoor*</span><span class="sxs-lookup"><span data-stu-id="a8314-302">**Name:** *Baydoor*</span></span>

1. <span data-ttu-id="a8314-303">En la ficha desplegable **Directivas generales**, establezca los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="a8314-303">On the **Location directives** FastTab, set the following values:</span></span>

    - <span data-ttu-id="a8314-304">**Tipo de trabajo**: *Ubicar*</span><span class="sxs-lookup"><span data-stu-id="a8314-304">**Work type:** *Put*</span></span>
    - <span data-ttu-id="a8314-305">**Sitio**: *6*</span><span class="sxs-lookup"><span data-stu-id="a8314-305">**Site:** *6*</span></span>
    - <span data-ttu-id="a8314-306">**Almacén**: *62*</span><span class="sxs-lookup"><span data-stu-id="a8314-306">**Warehouse:** *62*</span></span>
    - <span data-ttu-id="a8314-307">**Varios SKU:** *No*</span><span class="sxs-lookup"><span data-stu-id="a8314-307">**Multiple SKU:** *No*</span></span>

1. <span data-ttu-id="a8314-308">Seleccione **Guardar** para tener disponible la barra de herramientas en la ficha desplegable **Líneas**.</span><span class="sxs-lookup"><span data-stu-id="a8314-308">Select **Save** to make the toolbar on the **Lines** FastTab available.</span></span>
1. <span data-ttu-id="a8314-309">En la ficha desplegable **Líneas**, seleccione **Nuevo** y luego establezca los valores siguientes en la nueva línea.</span><span class="sxs-lookup"><span data-stu-id="a8314-309">On the **Lines** FastTab, select **New**, and then set the following values on the new line.</span></span> <span data-ttu-id="a8314-310">Acepte los valores predeterminados del resto de campos.</span><span class="sxs-lookup"><span data-stu-id="a8314-310">Accept the default values for all the other fields.</span></span>

    - <span data-ttu-id="a8314-311">**Secuencia**: *1*</span><span class="sxs-lookup"><span data-stu-id="a8314-311">**Sequence:** *1*</span></span>
    - <span data-ttu-id="a8314-312">**De:** *0*</span><span class="sxs-lookup"><span data-stu-id="a8314-312">**From:** *0*</span></span>
    - <span data-ttu-id="a8314-313">**A:** *1 000 000*</span><span class="sxs-lookup"><span data-stu-id="a8314-313">**To:** *1,000,000*</span></span>

1. <span data-ttu-id="a8314-314">Seleccione **Guardar** para tener disponible la barra de herramientas de la ficha desplegable **Acciones directivas de ubicación**.</span><span class="sxs-lookup"><span data-stu-id="a8314-314">Select **Save** to make the toolbar on the **Location Directive Actions** FastTab available.</span></span>
1. <span data-ttu-id="a8314-315">En la ficha desplegable **Acciones de directiva de ubicación**, seleccione **Nuevo** y luego establezca los valores siguientes en la nueva línea.</span><span class="sxs-lookup"><span data-stu-id="a8314-315">On the **Location Directive Actions** FastTab, select **New**, and then set the following values on the new line.</span></span> <span data-ttu-id="a8314-316">Acepte los valores predeterminados del resto de campos.</span><span class="sxs-lookup"><span data-stu-id="a8314-316">Accept the default values for all the other fields.</span></span>

    - <span data-ttu-id="a8314-317">**Secuencia**: *1*</span><span class="sxs-lookup"><span data-stu-id="a8314-317">**Sequence:** *1*</span></span>
    - <span data-ttu-id="a8314-318">**Nombre:** *Baydoor*</span><span class="sxs-lookup"><span data-stu-id="a8314-318">**Name:** *Baydoor*</span></span>

1. <span data-ttu-id="a8314-319">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="a8314-319">Select **Save**.</span></span>
1. <span data-ttu-id="a8314-320">En la ficha desplegable **Acciones de directiva de ubicación**, seleccione **Editar consulta**.</span><span class="sxs-lookup"><span data-stu-id="a8314-320">On the **Location Directive Actions** FastTab, select **Edit query**.</span></span>
1. <span data-ttu-id="a8314-321">En el editor de consultas, en la pestaña **Rango**, busque la fila donde el campo **Campo** esté establecido en *Ubicación*.</span><span class="sxs-lookup"><span data-stu-id="a8314-321">In the query editor, on the **Range** tab, find the row where the **Field** field is set to *Location*.</span></span> <span data-ttu-id="a8314-322">Seleccione el campo **Criterios** en esta fila para *Baydoor*.</span><span class="sxs-lookup"><span data-stu-id="a8314-322">Set the **Criteria** field for this row to *Baydoor*.</span></span>
1. <span data-ttu-id="a8314-323">Seleccione **Aceptar** para guardar los ajustes y cerrar el editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="a8314-323">Select **OK** to save your settings and close the query editor.</span></span>

#### <a name="set-up-a-multiple-sku-directive"></a><span data-ttu-id="a8314-324">Configurar varias directivas SKU</span><span class="sxs-lookup"><span data-stu-id="a8314-324">Set up a multiple-SKU directive</span></span>

1. <span data-ttu-id="a8314-325">Vaya a **Gestión de almacenes \> Configurar \> Directivas de ubicación**.</span><span class="sxs-lookup"><span data-stu-id="a8314-325">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="a8314-326">En el panel izquierdo, cambie el valor del campo **Tipo de orden de trabajo** a *Selección de inventario ordenado*.</span><span class="sxs-lookup"><span data-stu-id="a8314-326">In the left pane, change the value of the **Work order type** field to *Sorted inventory picking*.</span></span>
1. <span data-ttu-id="a8314-327">En el panel de acciones, haga clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="a8314-327">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="a8314-328">Establezca los siguientes valores en el encabezado:</span><span class="sxs-lookup"><span data-stu-id="a8314-328">In the header, set the following values:</span></span>

    - <span data-ttu-id="a8314-329">**Secuencia**: *2*</span><span class="sxs-lookup"><span data-stu-id="a8314-329">**Sequence:** *2*</span></span>
    - <span data-ttu-id="a8314-330">**Nombre:** *Baydoor Multi*</span><span class="sxs-lookup"><span data-stu-id="a8314-330">**Name:** *Baydoor Multi*</span></span>

1. <span data-ttu-id="a8314-331">En la ficha desplegable **Directivas generales**, establezca los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="a8314-331">On the **Location directives** FastTab, set the following values:</span></span>

    - <span data-ttu-id="a8314-332">**Tipo de trabajo**: *Ubicar*</span><span class="sxs-lookup"><span data-stu-id="a8314-332">**Work type:** *Put*</span></span>
    - <span data-ttu-id="a8314-333">**Sitio**: *6*</span><span class="sxs-lookup"><span data-stu-id="a8314-333">**Site:** *6*</span></span>
    - <span data-ttu-id="a8314-334">**Almacén**: *62*</span><span class="sxs-lookup"><span data-stu-id="a8314-334">**Warehouse:** *62*</span></span>
    - <span data-ttu-id="a8314-335">**SKU múltiple:** *Sí*</span><span class="sxs-lookup"><span data-stu-id="a8314-335">**Multiple SKU:** *Yes*</span></span>

1. <span data-ttu-id="a8314-336">Seleccione **Guardar** para tener disponible la barra de herramientas en la ficha desplegable **Líneas**.</span><span class="sxs-lookup"><span data-stu-id="a8314-336">Select **Save** to make the toolbar on the **Lines** FastTab available.</span></span>
1. <span data-ttu-id="a8314-337">En la ficha desplegable **Líneas**, seleccione **Nuevo** y luego establezca los valores siguientes en la nueva línea.</span><span class="sxs-lookup"><span data-stu-id="a8314-337">On the **Lines** FastTab, select **New**, and then set the following values on the new line.</span></span> <span data-ttu-id="a8314-338">Acepte los valores predeterminados del resto de campos.</span><span class="sxs-lookup"><span data-stu-id="a8314-338">Accept the default values for all the other fields.</span></span>

    - <span data-ttu-id="a8314-339">**Secuencia**: *1*</span><span class="sxs-lookup"><span data-stu-id="a8314-339">**Sequence:** *1*</span></span>
    - <span data-ttu-id="a8314-340">**De:** *0*</span><span class="sxs-lookup"><span data-stu-id="a8314-340">**From:** *0*</span></span>
    - <span data-ttu-id="a8314-341">**A:** *1 000 000*</span><span class="sxs-lookup"><span data-stu-id="a8314-341">**To:** *1,000,000*</span></span>

1. <span data-ttu-id="a8314-342">Seleccione **Guardar** para tener disponible la barra de herramientas de la ficha desplegable **Acciones directivas de ubicación**.</span><span class="sxs-lookup"><span data-stu-id="a8314-342">Select **Save** to make the toolbar on the **Location Directive Actions** FastTab available.</span></span>
1. <span data-ttu-id="a8314-343">En la ficha desplegable **Acciones de directiva de ubicación**, seleccione **Nuevo** y luego establezca los valores siguientes en la nueva línea.</span><span class="sxs-lookup"><span data-stu-id="a8314-343">On the **Location Directive Actions** FastTab, select **New**, and then set the following values on the new line.</span></span> <span data-ttu-id="a8314-344">Acepte los valores predeterminados del resto de campos.</span><span class="sxs-lookup"><span data-stu-id="a8314-344">Accept the default values for all the other fields.</span></span>

    - <span data-ttu-id="a8314-345">**Secuencia**: *1*</span><span class="sxs-lookup"><span data-stu-id="a8314-345">**Sequence:** *1*</span></span>
    - <span data-ttu-id="a8314-346">**Nombre:** *Baydoor Multi*</span><span class="sxs-lookup"><span data-stu-id="a8314-346">**Name:** *Baydoor Multi*</span></span>

1. <span data-ttu-id="a8314-347">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="a8314-347">Select **Save**.</span></span>
1. <span data-ttu-id="a8314-348">En la ficha desplegable **Acciones de directiva de ubicación**, seleccione **Editar consulta**.</span><span class="sxs-lookup"><span data-stu-id="a8314-348">On the **Location Directive Actions** FastTab, select **Edit query**.</span></span>
1. <span data-ttu-id="a8314-349">En el editor de consultas, en la pestaña **Rango**, busque la fila donde el campo **Campo** esté establecido en *Ubicación*.</span><span class="sxs-lookup"><span data-stu-id="a8314-349">In the query editor, on the **Range** tab, find the row where the **Field** field is set to *Location*.</span></span> <span data-ttu-id="a8314-350">Seleccione el campo **Criterios** en esta fila para *Baydoor*.</span><span class="sxs-lookup"><span data-stu-id="a8314-350">Set the **Criteria** field for this row to *Baydoor*.</span></span>
1. <span data-ttu-id="a8314-351">Seleccione **Aceptar** para guardar los ajustes y cerrar el editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="a8314-351">Select **OK** to save your settings and close the query editor.</span></span>

### <a name="set-up-work-templates"></a><span data-ttu-id="a8314-352">Configurar plantillas de trabajo</span><span class="sxs-lookup"><span data-stu-id="a8314-352">Set up work templates</span></span>

1. <span data-ttu-id="a8314-353">Vaya a **Administración de almacenes \> Configuración \> Trabajo \> Plantillas de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="a8314-353">Go to **Warehouse management \> Setup \> Work \> Work templates**.</span></span>
1. <span data-ttu-id="a8314-354">Cambie el valor del campo **Tipo de orden de trabajo** a *Selección de inventario ordenado*.</span><span class="sxs-lookup"><span data-stu-id="a8314-354">Change the value of the **Work order type** field to *Sorted inventory picking*.</span></span>
1. <span data-ttu-id="a8314-355">En el panel de acciones, seleccione **Nuevo** para crear una plantilla de trabajo.</span><span class="sxs-lookup"><span data-stu-id="a8314-355">On the Action Pane, select **New** to create a work template.</span></span>
1. <span data-ttu-id="a8314-356">En la pestaña **Visión general**, establezca los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="a8314-356">On the **Overview** tab, set the following values:</span></span>

    - <span data-ttu-id="a8314-357">**Secuencia**: *1*</span><span class="sxs-lookup"><span data-stu-id="a8314-357">**Sequence:** *1*</span></span>
    - <span data-ttu-id="a8314-358">**Plantilla de trabajo:** *Ordenar*</span><span class="sxs-lookup"><span data-stu-id="a8314-358">**Work template:** *Sort*</span></span>
    - <span data-ttu-id="a8314-359">**Descripción de plantilla de trabajo:** *Ordenar*</span><span class="sxs-lookup"><span data-stu-id="a8314-359">**Work template description:** *Sort*</span></span>

1. <span data-ttu-id="a8314-360">Seleccione **Guardar** para tener disponible la ficha desplegable **Detalles de plantilla de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="a8314-360">Select **Save** to make the **Work Template Details** FastTab available.</span></span>
1. <span data-ttu-id="a8314-361">En la ficha desplegable **Detalles de plantilla de trabajo**, seleccione **Nuevo** para agregar una línea y luego establecer los siguientes valores en ella:</span><span class="sxs-lookup"><span data-stu-id="a8314-361">On the **Work Template Details** FastTab, select **New** to add a line, and then set the following values for it:</span></span>

    - <span data-ttu-id="a8314-362">**Tipo de trabajo**: *Recoger*</span><span class="sxs-lookup"><span data-stu-id="a8314-362">**Work type:** *Pick*</span></span>
    - <span data-ttu-id="a8314-363">**Id. de la clase de trabajo:** *ORDENAR*</span><span class="sxs-lookup"><span data-stu-id="a8314-363">**Work class ID:** *SORT*</span></span>

1. <span data-ttu-id="a8314-364">Seleccione de nuevo **Nuevo** para agregar una segunda línea y establezca los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="a8314-364">Select **New** again to add a second line, and then set the following values for it:</span></span>

    - <span data-ttu-id="a8314-365">**Tipo de trabajo**: *Ubicar*</span><span class="sxs-lookup"><span data-stu-id="a8314-365">**Work type:** *Put*</span></span>
    - <span data-ttu-id="a8314-366">**Id. de la clase de trabajo:** *ORDENAR*</span><span class="sxs-lookup"><span data-stu-id="a8314-366">**Work class ID:** *SORT*</span></span>

1. <span data-ttu-id="a8314-367">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="a8314-367">Select **Save**.</span></span>

## <a name="scenario"></a><span data-ttu-id="a8314-368">Situación</span><span class="sxs-lookup"><span data-stu-id="a8314-368">Scenario</span></span>

<span data-ttu-id="a8314-369">Este escenario simula una situación en la que los contenedores empaquetados deben ordenarse automáticamente en diferentes posiciones (pallets) después de la estación de embalaje, dependiendo del servicio del transportista.</span><span class="sxs-lookup"><span data-stu-id="a8314-369">This scenario simulates a situation where packed containers should automatically be sorted to different positions (pallets) after the packing station, depending on the shipping carrier service.</span></span> <span data-ttu-id="a8314-370">Una vez que todos los artículos de la carga se hayan empaquetado y ordenado por dirección, los pallets se moverán a la compuerta.</span><span class="sxs-lookup"><span data-stu-id="a8314-370">After all items from the load are packed and sorted by address, the pallets will be moved to the bay door.</span></span>

### <a name="create-sales-orders-and-picking-work"></a><span data-ttu-id="a8314-371">Crear pedidos de ventas y trabajos de selección</span><span class="sxs-lookup"><span data-stu-id="a8314-371">Create sales orders and picking work</span></span>

#### <a name="create-sales-order-1"></a><span data-ttu-id="a8314-372">Crear pedido de ventas 1</span><span class="sxs-lookup"><span data-stu-id="a8314-372">Create sales order 1</span></span>

1. <span data-ttu-id="a8314-373">Vaya a **Ventas y marketing \> Pedidos de ventas \> Todos los pedidos de ventas**.</span><span class="sxs-lookup"><span data-stu-id="a8314-373">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="a8314-374">En el panel de acciones, haga clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="a8314-374">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="a8314-375">En el cuadro de diálogo **Crear pedido de ventas**, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="a8314-375">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="a8314-376">**Cuenta de cliente:** *US-005*</span><span class="sxs-lookup"><span data-stu-id="a8314-376">**Customer account:** *US-005*</span></span>
    - <span data-ttu-id="a8314-377">**Almacén**: *62*</span><span class="sxs-lookup"><span data-stu-id="a8314-377">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="a8314-378">Haga clic en **Aceptar** para cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="a8314-378">Select **OK** to close the dialog box.</span></span>

    <span data-ttu-id="a8314-379">Se abre el nuevo pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="a8314-379">The new sales order is opened.</span></span>

1. <span data-ttu-id="a8314-380">Cambie a la vista **Encabezado**.</span><span class="sxs-lookup"><span data-stu-id="a8314-380">Switch to the **Header** view.</span></span>
1. <span data-ttu-id="a8314-381">En la ficha desplegable **Entrega**, en la sección **Transporte**, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="a8314-381">On the **Delivery** FastTab, in the **Transportation** section, set the following values:</span></span>

    - <span data-ttu-id="a8314-382">**Transportista de envío:** *Carga aérea*</span><span class="sxs-lookup"><span data-stu-id="a8314-382">**Shipping carrier:** *Air cargo*</span></span>
    - <span data-ttu-id="a8314-383">**Servicio de transportista:** *Aire*</span><span class="sxs-lookup"><span data-stu-id="a8314-383">**Carrier service:** *Air*</span></span>

1. <span data-ttu-id="a8314-384">Cambie a la vista **Líneas**.</span><span class="sxs-lookup"><span data-stu-id="a8314-384">Switch to the **Lines** view.</span></span>
1. <span data-ttu-id="a8314-385">Si no se agrega automáticamente una línea nueva vacía a la cuadrícula en la ficha desplegable **Líneas de pedido de venta**, seleccione **Agregar línea** para agregar una.</span><span class="sxs-lookup"><span data-stu-id="a8314-385">If a new, empty line isn't automatically added to the grid on the **Sales order lines** FastTab, select **Add line** to add one.</span></span>
1. <span data-ttu-id="a8314-386">En la nueva línea de pedido, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="a8314-386">On the new order line, set the following values:</span></span>

    - <span data-ttu-id="a8314-387">**Código de artículo:** *A0001*</span><span class="sxs-lookup"><span data-stu-id="a8314-387">**Item number:** *A0001*</span></span>
    - <span data-ttu-id="a8314-388">**Cantidad:** *2*</span><span class="sxs-lookup"><span data-stu-id="a8314-388">**Quantity:** *2*</span></span>

1. <span data-ttu-id="a8314-389">Con la nueva línea de pedido seleccionada en la ficha desplegable **Líneas de pedido de ventas**, en el menú **Inventario** sobre la cuadrícula seleccione **Reserva**.</span><span class="sxs-lookup"><span data-stu-id="a8314-389">While the new order line is still selected on the **Sales order lines** FastTab, on the **Inventory** menu above the grid, select **Reservation**.</span></span>
1. <span data-ttu-id="a8314-390">En la página **Reserva**, seleccione **Reservar lote** para reservar la cantidad completa de la línea seleccionada en el almacén.</span><span class="sxs-lookup"><span data-stu-id="a8314-390">On the **Reservation** page, select **Reserve lot** to reserve the full quantity of the selected line in the warehouse.</span></span>
1. <span data-ttu-id="a8314-391">Cierre la página **Reserva** para volver al pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="a8314-391">Close the **Reservation** page to return to the sales order.</span></span>
1. <span data-ttu-id="a8314-392">En el panel de acciones, en la pestaña **Almacén**, en el grupo **Acciones**, seleccione **Liberar al almacén**.</span><span class="sxs-lookup"><span data-stu-id="a8314-392">On the Action Pane, on the **Warehouse** tab, in the **Actions** group, select **Release to warehouse**.</span></span>
1. <span data-ttu-id="a8314-393">Recibirá un mensaje informativo que muestra el envío y la oleada de este pedido.</span><span class="sxs-lookup"><span data-stu-id="a8314-393">You receive an informational message that shows the shipment and wave for this order.</span></span> <span data-ttu-id="a8314-394">Anote los números del id. de la oleada y de id. del envío.</span><span class="sxs-lookup"><span data-stu-id="a8314-394">Make a note of the wave ID and shipment ID numbers.</span></span>

#### <a name="sales-order-2"></a><span data-ttu-id="a8314-395">Pedido de ventas 2</span><span class="sxs-lookup"><span data-stu-id="a8314-395">Sales order 2</span></span>

1. <span data-ttu-id="a8314-396">Vaya a **Ventas y marketing \> Pedidos de ventas \> Todos los pedidos de ventas**.</span><span class="sxs-lookup"><span data-stu-id="a8314-396">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="a8314-397">En el panel de acciones, haga clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="a8314-397">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="a8314-398">En el cuadro de diálogo **Crear pedido de ventas**, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="a8314-398">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="a8314-399">**Cuenta de cliente:** *US-006*</span><span class="sxs-lookup"><span data-stu-id="a8314-399">**Customer account:** *US-006*</span></span>
    - <span data-ttu-id="a8314-400">**Almacén**: *62*</span><span class="sxs-lookup"><span data-stu-id="a8314-400">**Warehouse:** *62*</span></span>

1. <span data-ttu-id="a8314-401">Haga clic en **Aceptar** para cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="a8314-401">Select **OK** to close the dialog box.</span></span>
1. <span data-ttu-id="a8314-402">Se abre el nuevo pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="a8314-402">The new sales order is opened.</span></span> <span data-ttu-id="a8314-403">Debe incluir una nueva línea vacía en la cuadrícula en la ficha desplegable **Líneas de pedido de venta**.</span><span class="sxs-lookup"><span data-stu-id="a8314-403">It should include a new, empty line in the grid on the **Sales order lines** FastTab.</span></span> <span data-ttu-id="a8314-404">En esta línea de pedido, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="a8314-404">Set the following values on this order line:</span></span>

    - <span data-ttu-id="a8314-405">**Artículo**: *A0001*</span><span class="sxs-lookup"><span data-stu-id="a8314-405">**Item:** *A0001*</span></span>
    - <span data-ttu-id="a8314-406">**Cantidad:** *1*</span><span class="sxs-lookup"><span data-stu-id="a8314-406">**Quantity:** *1*</span></span>

1. <span data-ttu-id="a8314-407">Sobre la ficha desplegable **Detalles de línea**, en la pestaña **Entrega**, configure el campo **Modo de entrega** en *Flowe-STD*.</span><span class="sxs-lookup"><span data-stu-id="a8314-407">On the **Line details** FastTab, on the **Delivery** tab, set the **Mode of delivery** field to *Flowe-STD*.</span></span>
1. <span data-ttu-id="a8314-408">En la ficha desplegable **Líneas de pedido de ventas**, seleccione **Agregar línea** y luego establezca los valores siguientes en la segunda línea.</span><span class="sxs-lookup"><span data-stu-id="a8314-408">On the **Sales order lines** FastTab, select **Add line**, and then set the following values on the second order line:</span></span>

    - <span data-ttu-id="a8314-409">**Artículo**: *A0002*</span><span class="sxs-lookup"><span data-stu-id="a8314-409">**Item:** *A0002*</span></span>
    - <span data-ttu-id="a8314-410">**Cantidad:** *1*</span><span class="sxs-lookup"><span data-stu-id="a8314-410">**Quantity:** *1*</span></span>

1. <span data-ttu-id="a8314-411">En la ficha desplegable **Detalles de línea**, en la pestaña **Entrega**, cambie el valor de **Modo de entrega** a *Air C-Air*.</span><span class="sxs-lookup"><span data-stu-id="a8314-411">On the **Line details** FastTab, on the **Delivery** tab, change the value of the **Mode of delivery** field to *Air C-Air*.</span></span>
1. <span data-ttu-id="a8314-412">En la ficha desplegable **Líneas de pedido de ventas**, seleccione la primera línea.</span><span class="sxs-lookup"><span data-stu-id="a8314-412">On the **Sales order lines** FastTab, select the first order line.</span></span> <span data-ttu-id="a8314-413">A continuación, en el menú **Inventario** sobre la cuadrícula, seleccione **Reserva**.</span><span class="sxs-lookup"><span data-stu-id="a8314-413">Then, on the **Inventory** menu above the grid, select **Reservation**.</span></span>
1. <span data-ttu-id="a8314-414">En la página **Reserva**, seleccione **Reservar lote** para reservar la cantidad completa de la línea seleccionada en el almacén.</span><span class="sxs-lookup"><span data-stu-id="a8314-414">On the **Reservation** page, select **Reserve lot** to reserve the full quantity of the selected line in the warehouse.</span></span>
1. <span data-ttu-id="a8314-415">Cierre la página **Reserva** para volver al pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="a8314-415">Close the **Reservation** page to return to the sales order.</span></span>
1. <span data-ttu-id="a8314-416">En la ficha desplegable **Líneas de pedido de ventas**, seleccione la segunda línea.</span><span class="sxs-lookup"><span data-stu-id="a8314-416">On the **Sales order lines** FastTab, select the second order line.</span></span> <span data-ttu-id="a8314-417">A continuación, en el menú **Inventario** sobre la cuadrícula, seleccione **Reserva**.</span><span class="sxs-lookup"><span data-stu-id="a8314-417">Then, on the **Inventory** menu above the grid, select **Reservation**.</span></span>
1. <span data-ttu-id="a8314-418">En la página **Reserva**, seleccione **Reservar lote** para reservar la cantidad completa de la línea seleccionada en el almacén.</span><span class="sxs-lookup"><span data-stu-id="a8314-418">On the **Reservation** page, select **Reserve lot** to reserve the full quantity of the selected line in the warehouse.</span></span>
1. <span data-ttu-id="a8314-419">Cierre la página **Reserva** para volver al pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="a8314-419">Close the **Reservation** page to return to the sales order.</span></span>
1. <span data-ttu-id="a8314-420">En el panel de acciones, en la pestaña **Almacén**, en el grupo **Acciones**, seleccione **Liberar al almacén**.</span><span class="sxs-lookup"><span data-stu-id="a8314-420">On the Action Pane, on the **Warehouse** tab, in the **Actions** group, select **Release to warehouse**.</span></span>
1. <span data-ttu-id="a8314-421">Recibirá un mensaje informativo que muestra el envío y la oleada de este pedido.</span><span class="sxs-lookup"><span data-stu-id="a8314-421">You receive an informational message that shows the shipment and wave for this order.</span></span> <span data-ttu-id="a8314-422">Observe que se han creado dos números de Id. de oleada y dos números de Id. de envío, uno para cada modo de entrega para las líneas de pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="a8314-422">Notice that two wave ID numbers and two shipment ID numbers have been created, one for each mode of delivery for the sales order lines.</span></span>

#### <a name="get-the-work-ids-from-the-work-details"></a><span data-ttu-id="a8314-423">Obtenga los Id. de trabajo de los detalles del trabajo</span><span class="sxs-lookup"><span data-stu-id="a8314-423">Get the work IDs from the work details</span></span>

1. <span data-ttu-id="a8314-424">Vaya a **Gestión de almacenes \> Trabajo \> Detalles de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="a8314-424">Go to **Warehouse management \> Work \> Work details**.</span></span>
1. <span data-ttu-id="a8314-425">La página muestra los Id. de trabajo que se han creado a partir de pedidos de ventas.</span><span class="sxs-lookup"><span data-stu-id="a8314-425">The page shows the work IDs that have been created from sales orders.</span></span> <span data-ttu-id="a8314-426">Utilice los Id. de oleada y los Id. de envío de los pedidos de ventas que creó para encontrar el Id. de trabajo de cada oleada y envío.</span><span class="sxs-lookup"><span data-stu-id="a8314-426">Use the wave IDs and shipment IDs from the sales orders that you created to find the work ID for each wave and shipment.</span></span> <span data-ttu-id="a8314-427">Tome nota de esos Id. de trabajo, ya que los necesitará en los próximos pasos.</span><span class="sxs-lookup"><span data-stu-id="a8314-427">Make a note of those work IDs, because you will need them in the next steps.</span></span> <span data-ttu-id="a8314-428">Observe que se han creado dos Id. de trabajo para el segundo pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="a8314-428">Notice that two work IDs were created for the second sales order.</span></span> <span data-ttu-id="a8314-429">Si se seleccionan diferentes artículos de diferentes ubicaciones, se generan Id. con palabras separadas.</span><span class="sxs-lookup"><span data-stu-id="a8314-429">If different items are picked from different locations, separate word IDs are generated.</span></span>

### <a name="pick-items-for-the-sales-orders"></a><span data-ttu-id="a8314-430">Seleccionar artículos para los pedidos de ventas</span><span class="sxs-lookup"><span data-stu-id="a8314-430">Pick items for the sales orders</span></span>

<span data-ttu-id="a8314-431">Complete el trabajo creado utilizando el dispositivo móvil para mover los elementos a la estación de embalaje.</span><span class="sxs-lookup"><span data-stu-id="a8314-431">Complete the created work by using the mobile device to move the items to the pack station.</span></span>

1. <span data-ttu-id="a8314-432">En el dispositivo móvil, inicie sesión en el almacén *62* utilizando el id. de usuario que creó para este escenario (o el Id. de usuario de un usuario de datos de demostración existente).</span><span class="sxs-lookup"><span data-stu-id="a8314-432">On the mobile device, sign in to warehouse *62* by using the user ID that you created for this scenario (or the user ID of an existing demo data user).</span></span>
1. <span data-ttu-id="a8314-433">En el menú principal, seleccione **Saliente**.</span><span class="sxs-lookup"><span data-stu-id="a8314-433">On the main menu, select **Outbound**.</span></span>
1. <span data-ttu-id="a8314-434">En el menú **Saliente**, seleccione **Selección de ventas**.</span><span class="sxs-lookup"><span data-stu-id="a8314-434">On the **Outbound** menu, select **Sales Picking**.</span></span>
1. <span data-ttu-id="a8314-435">En el campo **Id.**, introduzca el Id. de trabajo que se creó para el pedido de ventas 1.</span><span class="sxs-lookup"><span data-stu-id="a8314-435">In the **ID** field, enter the work ID that was created for sales order 1.</span></span>
1. <span data-ttu-id="a8314-436">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a8314-436">Select **OK**.</span></span>
1. <span data-ttu-id="a8314-437">En la página **Pedidos de venta: Picking**, introduzca una matrícula de destino que se creó para el pedido de ventas 1.</span><span class="sxs-lookup"><span data-stu-id="a8314-437">On the **Sales orders - Pick** page, enter a target LP that was created for sales order 1.</span></span> <span data-ttu-id="a8314-438">Observe que aparecen la ubicación de picking (*bulk-001*), articulo (*A0001*) y cantidad (*2 piezas*).</span><span class="sxs-lookup"><span data-stu-id="a8314-438">Notice that the picking location (*bulk-001*), item (*A0001*), and quantity (*2 pcs*) are shown.</span></span>
1. <span data-ttu-id="a8314-439">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a8314-439">Select **OK**.</span></span>
1. <span data-ttu-id="a8314-440">Revise la información en la página **Órdenes de venta: Colocar**.</span><span class="sxs-lookup"><span data-stu-id="a8314-440">Review the information on the **Sales orders - Put** page.</span></span> <span data-ttu-id="a8314-441">El campo **Loc** debe indicar que los elementos seleccionados van a la ubicación *Paquete*.</span><span class="sxs-lookup"><span data-stu-id="a8314-441">The **Loc** field should indicate that the picked items are going to the *Pack* location.</span></span>
1. <span data-ttu-id="a8314-442">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a8314-442">Select **OK**.</span></span>

    <span data-ttu-id="a8314-443">En la página **Escanear una identificación de trabajo / identificación de matrícula de entidad**, recibirá un mensaje de "Trabajo completado", que indica que el id. de trabajo del pedido de ventas 1 se ha completado.</span><span class="sxs-lookup"><span data-stu-id="a8314-443">On the **Scan a work ID / license plate ID** page, you receive a "Work Completed" message, which indicates that the work ID from sales order 1 has been completed.</span></span>

    <span data-ttu-id="a8314-444">Ahora seleccionará el pedido de ventas 2.</span><span class="sxs-lookup"><span data-stu-id="a8314-444">You will now pick sales order 2.</span></span>

1. <span data-ttu-id="a8314-445">En el campo **Id.**, introduzca el Id. de trabajo que se creó para el pedido de ventas 2, donde la línea 1 tiene el artículo *A0001*.</span><span class="sxs-lookup"><span data-stu-id="a8314-445">In the **ID** field, enter the work ID that was created for sales order 2, where line 1 has item *A0001*.</span></span>
1. <span data-ttu-id="a8314-446">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a8314-446">Select **OK**.</span></span>
1. <span data-ttu-id="a8314-447">En la página **Pedidos de venta: Picking**, introduzca una matrícula de destino.</span><span class="sxs-lookup"><span data-stu-id="a8314-447">On the **Sales orders - Pick** page, enter a target LP.</span></span> <span data-ttu-id="a8314-448">Observe que aparecen la ubicación de picking (*bulk-001*), articulo (*A0001*) y cantidad (*1 piezas*).</span><span class="sxs-lookup"><span data-stu-id="a8314-448">Notice that the picking location (*bulk-001*), item (*A0001*), and quantity (*1 pcs*) are shown.</span></span>
1. <span data-ttu-id="a8314-449">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a8314-449">Select **OK**.</span></span>
1. <span data-ttu-id="a8314-450">Revise la información en la página **Órdenes de venta: Colocar**.</span><span class="sxs-lookup"><span data-stu-id="a8314-450">Review the information on the **Sales orders - Put** page.</span></span> <span data-ttu-id="a8314-451">El campo **Loc** debe indicar que los elementos seleccionados van a la ubicación *Paquete*.</span><span class="sxs-lookup"><span data-stu-id="a8314-451">The **Loc** field should indicate that the picked items are going to the *Pack* location.</span></span>
1. <span data-ttu-id="a8314-452">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a8314-452">Select **OK**.</span></span>

    <span data-ttu-id="a8314-453">En la página **Escanear una identificación de trabajo / identificación de matrícula de entidad**, recibirá un mensaje de "Trabajo completado".</span><span class="sxs-lookup"><span data-stu-id="a8314-453">On the **Scan a work ID / license plate ID** page, you receive a "Work Completed" message.</span></span> <span data-ttu-id="a8314-454">Este mensaje indica que el id. de trabajo de la línea 1 del pedido de ventas 2 se ha completado.</span><span class="sxs-lookup"><span data-stu-id="a8314-454">This message indicates that the work ID from line 1 of sales order 2 has been completed.</span></span>

1. <span data-ttu-id="a8314-455">En el campo **Id.**, introduzca el Id. de trabajo que se creó para el pedido de ventas 2, donde la línea 2 tiene el artículo *A0002*.</span><span class="sxs-lookup"><span data-stu-id="a8314-455">In the **ID** field, enter the work ID that was created for sales order 2, where line 2 has item *A0002*.</span></span>
1. <span data-ttu-id="a8314-456">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a8314-456">Select **OK**.</span></span>
1. <span data-ttu-id="a8314-457">En la página **Pedidos de venta: Picking**, introduzca una matrícula de destino.</span><span class="sxs-lookup"><span data-stu-id="a8314-457">On the **Sales orders - Pick** page, enter a target LP.</span></span> <span data-ttu-id="a8314-458">Observe que aparecen la ubicación de picking (*bulk-002*), articulo (*A0001*) y cantidad (*1 piezas*).</span><span class="sxs-lookup"><span data-stu-id="a8314-458">Notice that the picking location (*bulk-002*), item (*A0001*), and quantity (*1 pcs*) are shown.</span></span>
1. <span data-ttu-id="a8314-459">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a8314-459">Select **OK**.</span></span>
1. <span data-ttu-id="a8314-460">Revise la información en la página **Órdenes de venta: Colocar**.</span><span class="sxs-lookup"><span data-stu-id="a8314-460">Review the information on the **Sales orders - Put** page.</span></span> <span data-ttu-id="a8314-461">El campo **Loc** debe indicar que los elementos seleccionados van a la ubicación *Paquete*.</span><span class="sxs-lookup"><span data-stu-id="a8314-461">The **Loc** field should indicate that the picked items are going to the *Pack* location.</span></span>
1. <span data-ttu-id="a8314-462">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a8314-462">Select **OK**.</span></span>

    <span data-ttu-id="a8314-463">En la página **Escanear una identificación de trabajo / identificación de matrícula de entidad**, recibirá un mensaje de "Trabajo completado".</span><span class="sxs-lookup"><span data-stu-id="a8314-463">On the **Scan a work ID / license plate ID** page, you receive a "Work Completed" message.</span></span> <span data-ttu-id="a8314-464">Este mensaje indica que el id. de trabajo de la línea 2 del pedido de ventas 2 se ha completado.</span><span class="sxs-lookup"><span data-stu-id="a8314-464">This message indicates that the work ID from line 2 of sales order 2 has been completed.</span></span>

### <a name="pack-sales-orders-into-containers"></a><span data-ttu-id="a8314-465">Embalaje de pedidos de venta en contenedores</span><span class="sxs-lookup"><span data-stu-id="a8314-465">Pack sales orders into containers</span></span>

#### <a name="pack-sales-order-1-into-containers"></a><span data-ttu-id="a8314-466">Embalaje de pedido de venta 1 en contenedores</span><span class="sxs-lookup"><span data-stu-id="a8314-466">Pack sales order 1 into containers</span></span>

1. <span data-ttu-id="a8314-467">Vaya a **Gestión de almacenes \> Embalaje y puesta en contenedores \> Paquete**.</span><span class="sxs-lookup"><span data-stu-id="a8314-467">Go to **Warehouse management \> Packing and containerization \> Pack**.</span></span>

    <span data-ttu-id="a8314-468">Aparece el cuadro de diálogo **Seleccionar estación de embalaje**.</span><span class="sxs-lookup"><span data-stu-id="a8314-468">The **Select packing station** dialog box appears.</span></span> <span data-ttu-id="a8314-469">De manera predeterminada, el campo **Trabajador** debe establecerse con el nombre del trabajador que configuró anteriormente.</span><span class="sxs-lookup"><span data-stu-id="a8314-469">By default, the **Worker** field should be set to the name of the worker that you set up earlier.</span></span>

1. <span data-ttu-id="a8314-470">Establezca los siguientes valores para ver y trabajar en envíos y contenedores que están planificados en la ubicación de embalaje específica:</span><span class="sxs-lookup"><span data-stu-id="a8314-470">Set the following values to view and work on shipments and containers that are planned at the specific packing location:</span></span>

    - <span data-ttu-id="a8314-471">**Sitio**: *6*</span><span class="sxs-lookup"><span data-stu-id="a8314-471">**Site:** *6*</span></span>
    - <span data-ttu-id="a8314-472">**Almacén**: *62*</span><span class="sxs-lookup"><span data-stu-id="a8314-472">**Warehouse:** *62*</span></span>
    - <span data-ttu-id="a8314-473">**Ubicación:** *Paquete*</span><span class="sxs-lookup"><span data-stu-id="a8314-473">**Location:** *Pack*</span></span>
    - <span data-ttu-id="a8314-474">**Id. de perfil de empaquetado:** *Ordenar*</span><span class="sxs-lookup"><span data-stu-id="a8314-474">**Packing profile ID:** *Sort*</span></span>

1. <span data-ttu-id="a8314-475">Haga clic en **Aceptar** para cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="a8314-475">Select **OK** to close the dialog box.</span></span>
1. <span data-ttu-id="a8314-476">En la página **Paquete**, en el campo **Matrícula o envío**, introduzca la matrícula de destino para el pedido de venta 1.</span><span class="sxs-lookup"><span data-stu-id="a8314-476">On the **Pack** page, in the **License plate or shipment** field, enter the target LP for sales order 1.</span></span> <span data-ttu-id="a8314-477">Luego seleccione la **Pestaña** o la tecla **Entrar** en su teclado para salir del campo.</span><span class="sxs-lookup"><span data-stu-id="a8314-477">Then select the **Tab** or **Enter** key on your keyboard to move out of the field.</span></span>
1. <span data-ttu-id="a8314-478">En el panel de acciones, seleccione **Nuevo contenedor**.</span><span class="sxs-lookup"><span data-stu-id="a8314-478">On the Action Pane, select **New container**.</span></span>
1. <span data-ttu-id="a8314-479">Acepte todas las configuraciones predeterminadas y seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a8314-479">Accept all the default settings, and select **OK**.</span></span> <span data-ttu-id="a8314-480">Anote el id. de contenedor.</span><span class="sxs-lookup"><span data-stu-id="a8314-480">Make a note of the container ID.</span></span>
1. <span data-ttu-id="a8314-481">En la ficha desplegable **Embalaje de artículo**, establezca los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="a8314-481">On the **Item packing** FastTab, set the following values:</span></span>

    - <span data-ttu-id="a8314-482">**Cantidad:** *1*</span><span class="sxs-lookup"><span data-stu-id="a8314-482">**Quantity:** *1*</span></span>
    - <span data-ttu-id="a8314-483">**Identificador:** Articulo *A0001*</span><span class="sxs-lookup"><span data-stu-id="a8314-483">**Identifier:** Item *A0001*</span></span>

1. <span data-ttu-id="a8314-484">En el panel de acciones, seleccione **Cerrar contenedor**.</span><span class="sxs-lookup"><span data-stu-id="a8314-484">On the Action Pane, select **Close container**.</span></span>
1. <span data-ttu-id="a8314-485">En el cuadro de diálogo **Cerrar contenedor**, seleccione **Obtener peso del sistema** para que el sistema actualice el campo **Peso bruto**.</span><span class="sxs-lookup"><span data-stu-id="a8314-485">In the **Close container** dialog box, select **Get system weight** to have the system update the **Gross weight** field.</span></span>
1. <span data-ttu-id="a8314-486">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a8314-486">Select **OK**.</span></span> <span data-ttu-id="a8314-487">El contenedor se mueve a la ubicación *ORDENAR* y está listo para ordenar.</span><span class="sxs-lookup"><span data-stu-id="a8314-487">The container is moved to the *SORT* location and is ready for sorting.</span></span>
1. <span data-ttu-id="a8314-488">Cree un segundo contenedor para agregar el segundo artículo de la matrícula para el pedido de ventas 1 a un nuevo contenedor.</span><span class="sxs-lookup"><span data-stu-id="a8314-488">Create a second container to add the second item from the LP for sales order 1 to a new container.</span></span>
1. <span data-ttu-id="a8314-489">En el panel de acciones, seleccione **Nuevo contenedor**.</span><span class="sxs-lookup"><span data-stu-id="a8314-489">On the Action Pane, select **New container**.</span></span>
1. <span data-ttu-id="a8314-490">Acepte todas las configuraciones predeterminadas y seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a8314-490">Accept all the default settings, and select **OK**.</span></span> <span data-ttu-id="a8314-491">Anote el id. de contenedor.</span><span class="sxs-lookup"><span data-stu-id="a8314-491">Make a note of the container ID.</span></span>
1. <span data-ttu-id="a8314-492">En la ficha desplegable **Embalaje de artículo**, establezca los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="a8314-492">On the **Item packing** FastTab, set the following values:</span></span>

    - <span data-ttu-id="a8314-493">**Cantidad:** *1*</span><span class="sxs-lookup"><span data-stu-id="a8314-493">**Quantity:** *1*</span></span>
    - <span data-ttu-id="a8314-494">**Identificador:** Articulo *A0001*</span><span class="sxs-lookup"><span data-stu-id="a8314-494">**Identifier:** Item *A0001*</span></span>

1. <span data-ttu-id="a8314-495">En el panel de acciones, seleccione **Cerrar contenedor**.</span><span class="sxs-lookup"><span data-stu-id="a8314-495">On the Action Pane, select **Close container**.</span></span>
1. <span data-ttu-id="a8314-496">En el cuadro de diálogo **Cerrar contenedor**, seleccione **Obtener peso del sistema** para que el sistema actualice el campo **Peso bruto**.</span><span class="sxs-lookup"><span data-stu-id="a8314-496">In the **Close container** dialog box, select **Get system weight** to have the system update the **Gross weight** field.</span></span>
1. <span data-ttu-id="a8314-497">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a8314-497">Select **OK**.</span></span> <span data-ttu-id="a8314-498">El contenedor se mueve a la ubicación *ORDENAR* y está listo para ordenar.</span><span class="sxs-lookup"><span data-stu-id="a8314-498">The container is moved to the *SORT* location and is ready for sorting.</span></span>

#### <a name="pack-sales-order-2-into-containers"></a><span data-ttu-id="a8314-499">Embalaje de pedido de venta 2 en contenedores</span><span class="sxs-lookup"><span data-stu-id="a8314-499">Pack sales order 2 into containers</span></span>

1. <span data-ttu-id="a8314-500">En la página **Paquete**, en el campo **Matrícula o envío**, introduzca la matrícula de destino para la línea 1 del pedido de venta 2.</span><span class="sxs-lookup"><span data-stu-id="a8314-500">On the **Pack** page, in the **License plate or shipment** field, enter the target LP for line 1 of sales order 2.</span></span> <span data-ttu-id="a8314-501">Luego seleccione la **Pestaña** o la tecla **Entrar** en su teclado para salir del campo.</span><span class="sxs-lookup"><span data-stu-id="a8314-501">Then select the **Tab** or **Enter** key on your keyboard to move out of the field.</span></span>
1. <span data-ttu-id="a8314-502">En el panel de acciones, seleccione **Nuevo contenedor**.</span><span class="sxs-lookup"><span data-stu-id="a8314-502">On the Action Pane, select **New container**.</span></span>
1. <span data-ttu-id="a8314-503">Acepte todas las configuraciones predeterminadas y seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a8314-503">Accept all the default settings, and select **OK**.</span></span> <span data-ttu-id="a8314-504">Anote el id. de contenedor.</span><span class="sxs-lookup"><span data-stu-id="a8314-504">Make a note of the container ID.</span></span>
1. <span data-ttu-id="a8314-505">En la ficha desplegable **Embalaje de artículo**, establezca los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="a8314-505">On the **Item packing** FastTab, set the following values:</span></span>

    - <span data-ttu-id="a8314-506">**Cantidad:** *1*</span><span class="sxs-lookup"><span data-stu-id="a8314-506">**Quantity:** *1*</span></span>
    - <span data-ttu-id="a8314-507">**Identificador:** Articulo *A0001*</span><span class="sxs-lookup"><span data-stu-id="a8314-507">**Identifier:** Item *A0001*</span></span>

1. <span data-ttu-id="a8314-508">En el panel de acciones, seleccione **Cerrar contenedor**.</span><span class="sxs-lookup"><span data-stu-id="a8314-508">On the Action Pane, select **Close container**.</span></span>
1. <span data-ttu-id="a8314-509">En el cuadro de diálogo **Cerrar contenedor**, seleccione **Obtener peso del sistema** para que el sistema actualice el campo **Peso bruto**.</span><span class="sxs-lookup"><span data-stu-id="a8314-509">In the **Close container** dialog box, select **Get system weight** to have the system update the **Gross weight** field.</span></span>
1. <span data-ttu-id="a8314-510">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a8314-510">Select **OK**.</span></span> <span data-ttu-id="a8314-511">El contenedor se mueve a la ubicación *ORDENAR* y está listo para ordenar.</span><span class="sxs-lookup"><span data-stu-id="a8314-511">The container is moved to the *SORT* location and is ready for sorting.</span></span>
1. <span data-ttu-id="a8314-512">En el campo **Matrícula o envío**, introduzca la matrícula de destino para la línea 2 del pedido de venta 2.</span><span class="sxs-lookup"><span data-stu-id="a8314-512">In the **License plate or shipment** field, enter the target LP for line 2 of the sales order 2.</span></span> <span data-ttu-id="a8314-513">Luego seleccione la **Pestaña** o la tecla **Entrar** en su teclado para salir del campo.</span><span class="sxs-lookup"><span data-stu-id="a8314-513">Then select the **Tab** or **Enter** key on your keyboard to move out of the field.</span></span>
1. <span data-ttu-id="a8314-514">En el panel de acciones, seleccione **Nuevo contenedor**.</span><span class="sxs-lookup"><span data-stu-id="a8314-514">On the Action Pane, select **New container**.</span></span>
1. <span data-ttu-id="a8314-515">Acepte todas las configuraciones predeterminadas y seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a8314-515">Accept all the default settings, and select **OK**.</span></span> <span data-ttu-id="a8314-516">Anote el id. de contenedor.</span><span class="sxs-lookup"><span data-stu-id="a8314-516">Make a note of the container ID.</span></span>
1. <span data-ttu-id="a8314-517">En la ficha desplegable **Embalaje de artículo**, establezca los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="a8314-517">On the **Item packing** FastTab, set the following values:</span></span>

    - <span data-ttu-id="a8314-518">**Cantidad:** *1*</span><span class="sxs-lookup"><span data-stu-id="a8314-518">**Quantity:** *1*</span></span>
    - <span data-ttu-id="a8314-519">**Campo identificador:** Artículo *A0002*</span><span class="sxs-lookup"><span data-stu-id="a8314-519">**Identifier field:** Item *A0002*</span></span>

1. <span data-ttu-id="a8314-520">En el panel de acciones, seleccione **Cerrar contenedor**.</span><span class="sxs-lookup"><span data-stu-id="a8314-520">On the Action Pane, select **Close container**.</span></span>
1. <span data-ttu-id="a8314-521">En el cuadro de diálogo **Cerrar contenedor**, seleccione **Obtener peso del sistema** para que el sistema actualice el campo **Peso bruto**.</span><span class="sxs-lookup"><span data-stu-id="a8314-521">In the **Close container** dialog box, select **Get system weight** to have the system update the **Gross weight** field.</span></span>
1. <span data-ttu-id="a8314-522">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a8314-522">Select **OK**.</span></span> <span data-ttu-id="a8314-523">El contenedor se mueve a la ubicación *ORDENAR* y está listo para ordenar.</span><span class="sxs-lookup"><span data-stu-id="a8314-523">The container is moved to the *SORT* location and is ready for sorting.</span></span>

<span data-ttu-id="a8314-524">Para ver los detalles del contenedor, vaya a **Gestión de almacenes \> Embalaje y puesta en contenedores \> Contenedores** y busque los Id. de contenedores que se crearon durante el embalaje.</span><span class="sxs-lookup"><span data-stu-id="a8314-524">To view the container details, go to **Warehouse management \> Packing and containerization \> Containers**, and search for the container IDs that were created during packing.</span></span>

### <a name="sort-the-containers"></a><span data-ttu-id="a8314-525">Ordenar los contenedores</span><span class="sxs-lookup"><span data-stu-id="a8314-525">Sort the containers</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a8314-526">Cuando acceda al elemento de menú **Crear pallet** en la aplicación móvil para hacer la ordenación de salida, verá un botón que está etiquetado como **Completo**.</span><span class="sxs-lookup"><span data-stu-id="a8314-526">When you access the **Pallet build** menu item on the mobile app to do outbound sorting, you will see a button that is labeled **Full**.</span></span> <span data-ttu-id="a8314-527">*No use el botón **Completo** para ordenar o cerrar la posición.*</span><span class="sxs-lookup"><span data-stu-id="a8314-527">*Don't use the **Full** button to sort or close the position.*</span></span>
>
> <span data-ttu-id="a8314-528">El botón **Completo** se proporciona de manera predeterminada y no se puede deshabilitar ni eliminar de la página.</span><span class="sxs-lookup"><span data-stu-id="a8314-528">The **Full** button is provided by default and can't be disabled or removed from the page.</span></span> <span data-ttu-id="a8314-529">No se usa para la característica *Ordenación de salida*.</span><span class="sxs-lookup"><span data-stu-id="a8314-529">It isn't used for the *Outbound sorting* feature.</span></span>

#### <a name="sort-the-first-container"></a><span data-ttu-id="a8314-530">Ordenar el primer contenedor</span><span class="sxs-lookup"><span data-stu-id="a8314-530">Sort the first container</span></span>

1. <span data-ttu-id="a8314-531">En el dispositivo móvil, inicie sesión en el almacén *62* utilizando el id. de usuario que creó para este escenario (o el Id. de usuario de un usuario de datos de demostración existente).</span><span class="sxs-lookup"><span data-stu-id="a8314-531">On the mobile device, sign in to warehouse *62* by using the user ID that you created for this scenario (or the user ID of an existing demo data user).</span></span>
1. <span data-ttu-id="a8314-532">En el menú principal, seleccione **Saliente**.</span><span class="sxs-lookup"><span data-stu-id="a8314-532">On the main menu, select **Outbound**.</span></span>
1. <span data-ttu-id="a8314-533">En el menú **Saliente**, seleccione **Crear pallet**.</span><span class="sxs-lookup"><span data-stu-id="a8314-533">On the **Outbound** menu, select **Pallet build**.</span></span>
1. <span data-ttu-id="a8314-534">En el campo **Matrícula de entidad de almacén/Con**, introduzca el primer Id. de contenedor asociado con el pedido de ventas 1.</span><span class="sxs-lookup"><span data-stu-id="a8314-534">In the **LP/Con** field, enter the first container ID that is associated with sales order 1.</span></span>
1. <span data-ttu-id="a8314-535">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a8314-535">Select **OK**.</span></span>
1. <span data-ttu-id="a8314-536">Como actualmente no existen posiciones de ordenación, debe especificar una.</span><span class="sxs-lookup"><span data-stu-id="a8314-536">Because no sort positions currently exist, you must specify one.</span></span> <span data-ttu-id="a8314-537">En el campo **Id. de posición de ordenación**, escriba *SP01*.</span><span class="sxs-lookup"><span data-stu-id="a8314-537">In the **Sort position ID** field, enter *SP01*.</span></span>
1. <span data-ttu-id="a8314-538">Como actualmente no hay matrículas asociadas a la posición de ordenación *SP01*, debe especificar una.</span><span class="sxs-lookup"><span data-stu-id="a8314-538">Because no LP is currently associated with sort position *SP01*, you must specify one.</span></span> <span data-ttu-id="a8314-539">En el campo **Matrícula**, introduzca *PLP01*.</span><span class="sxs-lookup"><span data-stu-id="a8314-539">In the **LP** field, enter *PLP01*.</span></span>
1. <span data-ttu-id="a8314-540">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a8314-540">Select **OK**.</span></span>
1. <span data-ttu-id="a8314-541">Como la validación de posición de ordenación está activada, debe introducir nuevamente el id. de posición de ordenación.</span><span class="sxs-lookup"><span data-stu-id="a8314-541">Because sort position validation is turned on, you must enter the sort position ID again.</span></span> <span data-ttu-id="a8314-542">En el campo **Id. de posición de ordenación**, escriba *SP01*.</span><span class="sxs-lookup"><span data-stu-id="a8314-542">In the **Sort Position ID** field, enter *SP01*.</span></span>
1. <span data-ttu-id="a8314-543">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a8314-543">Select **OK**.</span></span>

    <span data-ttu-id="a8314-544">Recibe un mensaje "Trabajo completado".</span><span class="sxs-lookup"><span data-stu-id="a8314-544">You receive a "Work completed" message.</span></span>

> [!TIP]
> <span data-ttu-id="a8314-545">Para ver la posición de ordenación y la matrícula que contiene, vaya a **Gestión de almacenes \> Embalaje y puesta en contenedores \> Asignaciones de posición de ordenación de salida**.</span><span class="sxs-lookup"><span data-stu-id="a8314-545">To view the sort position and the LP in it, go to **Warehouse management \> Packing and containerization \> Outbound sorting position assignments**.</span></span>
>
> <span data-ttu-id="a8314-546">La pagina **Asignaciones de posición de ordenación de salida** muestra todas las posiciones de ordenación que están activas actualmente.</span><span class="sxs-lookup"><span data-stu-id="a8314-546">The **Outbound sorting position assignments** page shows all the sort positions that are currently active.</span></span> <span data-ttu-id="a8314-547">Los campos **Ordenar posición de transacciones** muestran la matrícula asociada con cada posición de ordenación y los contenedores que están en la posición de ordenación.</span><span class="sxs-lookup"><span data-stu-id="a8314-547">The **Sort position transactions** field shows the LP that is associated with each sort position, and the containers that are in the sort position.</span></span> <span data-ttu-id="a8314-548">Observe que actualmente existe una posición de ordenación y que la ficha desplegable **Criterios de posición de ordenación** muestra un criterio de **Envío - Servicio de transportista - Air**.</span><span class="sxs-lookup"><span data-stu-id="a8314-548">Notice that one sort position currently exists, and that the **Sort position criteria** FastTab shows a criterion of **Shipment – Carrier service - Air**.</span></span>

#### <a name="sort-the-remaining-containers"></a><span data-ttu-id="a8314-549">Ordenar los contenedores restantes</span><span class="sxs-lookup"><span data-stu-id="a8314-549">Sort the remaining containers</span></span>

1. <span data-ttu-id="a8314-550">En el dispositivo móvil, inicie sesión en el almacén *62* utilizando el id. de usuario que creó para este escenario (o el Id. de usuario de un usuario de datos de demostración existente).</span><span class="sxs-lookup"><span data-stu-id="a8314-550">On the mobile device, sign in to warehouse *62* by using the user ID that you created for this scenario (or the user ID of an existing demo data user).</span></span>
1. <span data-ttu-id="a8314-551">En el menú principal, seleccione **Saliente**.</span><span class="sxs-lookup"><span data-stu-id="a8314-551">On the main menu, select **Outbound**.</span></span>
1. <span data-ttu-id="a8314-552">En el menú **Saliente**, seleccione **Crear pallet**.</span><span class="sxs-lookup"><span data-stu-id="a8314-552">On the **Outbound** menu, select **Pallet build**.</span></span>
1. <span data-ttu-id="a8314-553">En el campo **Matrícula de entidad de almacén/Con**, introduzca el segundo Id. de contenedor asociado con el pedido de ventas 1.</span><span class="sxs-lookup"><span data-stu-id="a8314-553">In the **LP/Con** field, enter the second container ID that is associated with sales order 1.</span></span>
1. <span data-ttu-id="a8314-554">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a8314-554">Select **OK**.</span></span> <span data-ttu-id="a8314-555">Como la plantilla de ordenación está configurada para ordenar automáticamente, y ya existe una posición de ordenación que tiene criterios coincidentes, se le dirige automáticamente a la posición de ordenación correcta.</span><span class="sxs-lookup"><span data-stu-id="a8314-555">Because the sorting template is set up to sort automatically, and a sort position that has matching criteria already exists, you're automatically directed to the correct sort position.</span></span>
1. <span data-ttu-id="a8314-556">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a8314-556">Select **OK**.</span></span>
1. <span data-ttu-id="a8314-557">Confirme el Id. de posición de ordenación para indicar que el inventario está en el lugar correcto.</span><span class="sxs-lookup"><span data-stu-id="a8314-557">Confirm the sort position ID to indicate that the inventory is in the correct place.</span></span> <span data-ttu-id="a8314-558">En el campo **Id. de posición de ordenación**, escriba *SP01*.</span><span class="sxs-lookup"><span data-stu-id="a8314-558">In the **Sort Position ID** field, enter *SP01*.</span></span>
1. <span data-ttu-id="a8314-559">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a8314-559">Select **OK**.</span></span>

    <span data-ttu-id="a8314-560">El trabajo se completa en el segundo contenedor del pedido de venta 1.</span><span class="sxs-lookup"><span data-stu-id="a8314-560">Work is completed on the second container from sales order 1.</span></span> <span data-ttu-id="a8314-561">Ahora ordenará los contenedores restantes del pedido de venta 2.</span><span class="sxs-lookup"><span data-stu-id="a8314-561">You will now sort the remaining containers from sales order 2.</span></span>

1. <span data-ttu-id="a8314-562">En el campo **Matrícula de entidad de almacén/Con**, introduzca el Id. del contenedor del contenedor del pedido de venta 2 que contiene el artículo *A0001*.</span><span class="sxs-lookup"><span data-stu-id="a8314-562">In the **LP/Con** field, enter the container ID of the container from sales order 2 that holds item *A0001*.</span></span> <span data-ttu-id="a8314-563">Como el servicio de transportista es diferente, se le solicita que introduzca una nueva posición de ordenación y asigne una matrícula a esa posición.</span><span class="sxs-lookup"><span data-stu-id="a8314-563">Because the carrier service differs, you're prompted to enter a new sort position and assign an LP to that position.</span></span> <span data-ttu-id="a8314-564">Usar posición de ordenación *SP02* y la matrícula *PLP02*.</span><span class="sxs-lookup"><span data-stu-id="a8314-564">Use sort position *SP02* and LP *PLP02*.</span></span>
1. <span data-ttu-id="a8314-565">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a8314-565">Select **OK**.</span></span>
1. <span data-ttu-id="a8314-566">Confirme la posición de ordenación introduciendo *SP02* en el campo **Id. de posición de ordenación**.</span><span class="sxs-lookup"><span data-stu-id="a8314-566">Confirm the sort position by entering *SP02* in the **Sort Position ID** field.</span></span>
1. <span data-ttu-id="a8314-567">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a8314-567">Select **OK**.</span></span>

    <span data-ttu-id="a8314-568">El trabajo se completa en el contenedor.</span><span class="sxs-lookup"><span data-stu-id="a8314-568">Work is completed on the container.</span></span>

1. <span data-ttu-id="a8314-569">En el campo **Matrícula de entidad de almacén/Con**, introduzca el Id. del contenedor restante del pedido de venta 2 que contiene el artículo *A0002*.</span><span class="sxs-lookup"><span data-stu-id="a8314-569">In the **LP/Con** field, enter the container ID for the remaining container from sales order 2 that holds item *A0002*.</span></span> <span data-ttu-id="a8314-570">Como el servicio de transportista es el mismo que el servicio de transportista del pedido de venta 1, el sistema muestra la posición de ordenación existente que tiene criterios coincidentes.</span><span class="sxs-lookup"><span data-stu-id="a8314-570">Because the carrier service is the same as the carrier service for sales order 1, the system shows the existing sort position that has matching criteria.</span></span>
1. <span data-ttu-id="a8314-571">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a8314-571">Select **OK**.</span></span>
1. <span data-ttu-id="a8314-572">Confirme la posición de ordenación introduciendo *SP01* en el campo **Id. de posición de ordenación**.</span><span class="sxs-lookup"><span data-stu-id="a8314-572">Confirm the sort position by entering *SP01* in the **Sort Position ID** field.</span></span>
1. <span data-ttu-id="a8314-573">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a8314-573">Select **OK**.</span></span>

    <span data-ttu-id="a8314-574">El trabajo se completa en el contenedor.</span><span class="sxs-lookup"><span data-stu-id="a8314-574">Work is completed on the container.</span></span>

### <a name="close-the-outbound-sorting-positions"></a><span data-ttu-id="a8314-575">Cerrar las posiciones de ordenación de salida</span><span class="sxs-lookup"><span data-stu-id="a8314-575">Close the outbound sorting positions</span></span>

<span data-ttu-id="a8314-576">Cuando se haya ordenado todo el inventario, la posición debe cerrarse para poder crear el trabajo.</span><span class="sxs-lookup"><span data-stu-id="a8314-576">When all inventory has been sorted, the position must be closed before work can be created.</span></span> <span data-ttu-id="a8314-577">El trabajo de selección de inventario ordenado se creará para llevar el inventario a compuerta.</span><span class="sxs-lookup"><span data-stu-id="a8314-577">Sorted inventory picking work will be created to take the inventory to the bay door.</span></span>

#### <a name="close-a-position-from-the-mobile-device"></a><span data-ttu-id="a8314-578">Cerrar una posición desde el dispositivo móvil</span><span class="sxs-lookup"><span data-stu-id="a8314-578">Close a position from the mobile device</span></span>

1. <span data-ttu-id="a8314-579">En el dispositivo móvil, inicie sesión en el almacén *62* utilizando el id. de usuario que creó para este escenario (o el Id. de usuario de un usuario de datos de demostración existente).</span><span class="sxs-lookup"><span data-stu-id="a8314-579">On the mobile device, sign in to warehouse *62* by using the user ID that you created for this scenario (or the user ID of an existing demo data user).</span></span>
1. <span data-ttu-id="a8314-580">En el menú principal, seleccione **Saliente**.</span><span class="sxs-lookup"><span data-stu-id="a8314-580">On the main menu, select **Outbound**.</span></span>
1. <span data-ttu-id="a8314-581">En el menú **Saliente**, seleccione **Crear pallet**.</span><span class="sxs-lookup"><span data-stu-id="a8314-581">On the **Outbound** menu, select **Pallet build**.</span></span>
1. <span data-ttu-id="a8314-582">En el campo **Matrícula de entidad de almacén/Con**, introduzca un Id. de contenedor que se haya ordenado a la posición de ordenación *SP01*.</span><span class="sxs-lookup"><span data-stu-id="a8314-582">In the **LP/Con** field, enter a container ID that was sorted to sort position *SP01*.</span></span>
1. <span data-ttu-id="a8314-583">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a8314-583">Select **OK**.</span></span>
1. <span data-ttu-id="a8314-584">Recibirá el siguiente mensaje: "El contenedor ya está ordenado en la posición SP01.</span><span class="sxs-lookup"><span data-stu-id="a8314-584">You receive the following message: "The container is already sorted to position SP01.</span></span> <span data-ttu-id="a8314-585">¿Desea cerrar la posición?"</span><span class="sxs-lookup"><span data-stu-id="a8314-585">Close the position?"</span></span> <span data-ttu-id="a8314-586">Seleccione **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="a8314-586">Select **Close**.</span></span>

    <span data-ttu-id="a8314-587">El trabajo se completó.</span><span class="sxs-lookup"><span data-stu-id="a8314-587">Work is completed.</span></span>

#### <a name="close-a-position-from-outbound-sorting-position-assignments"></a><span data-ttu-id="a8314-588">Cerrar una posición de las asignaciones de posición de ordenación de salida</span><span class="sxs-lookup"><span data-stu-id="a8314-588">Close a position from outbound sorting position assignments</span></span>

1. <span data-ttu-id="a8314-589">Vaya a **Gestión de almacenes \> Embalaje y puesta en contenedores \> Asignaciones de posición de ordenación de salida**.</span><span class="sxs-lookup"><span data-stu-id="a8314-589">Go to **Warehouse management \> Packing and containerization \> Outbound sorting position assignments**.</span></span>
1. <span data-ttu-id="a8314-590">En la columna izquierda, seleccione **SP02**.</span><span class="sxs-lookup"><span data-stu-id="a8314-590">In the left column, select **SP02**.</span></span> <span data-ttu-id="a8314-591">Esta fila de posición de ordenación de salida es la que cerrará.</span><span class="sxs-lookup"><span data-stu-id="a8314-591">This outbound sorting position row is the one that you will close.</span></span>
1. <span data-ttu-id="a8314-592">En el panel de acciones, seleccione **Cerrar posición**.</span><span class="sxs-lookup"><span data-stu-id="a8314-592">On the Action Pane, select **Close position**.</span></span> <span data-ttu-id="a8314-593">El registro de posición de ordenación está cerrado y ya no se muestra.</span><span class="sxs-lookup"><span data-stu-id="a8314-593">The sorting position record is closed and is no longer shown.</span></span>

    > [!TIP]
    > <span data-ttu-id="a8314-594">Para mostrar todos los registros de posición cerradlos, seleccione la casilla de verificación **Mostrar cerrados**.</span><span class="sxs-lookup"><span data-stu-id="a8314-594">To show all closed position records, select the **Show closed** check box.</span></span>

### <a name="sorted-inventory-picking"></a><span data-ttu-id="a8314-595">Picking de inventario ordenado</span><span class="sxs-lookup"><span data-stu-id="a8314-595">Sorted inventory picking</span></span>

<span data-ttu-id="a8314-596">Debe completar el trabajo de selección de inventario ordenado.</span><span class="sxs-lookup"><span data-stu-id="a8314-596">You must complete the sorted inventory picking work.</span></span> <span data-ttu-id="a8314-597">Cuando se complete, el inventario se seleccionará para el pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="a8314-597">When it's completed, the inventory will be picked to the sales order.</span></span> <span data-ttu-id="a8314-598">En ese punto, se aplican todos los demás procesos de almacén.</span><span class="sxs-lookup"><span data-stu-id="a8314-598">At that point, all other warehouse processes apply.</span></span>

1. <span data-ttu-id="a8314-599">En el dispositivo móvil, inicie sesión en el almacén *62* utilizando el id. de usuario que creó para este escenario (o el Id. de usuario de un usuario de datos de demostración existente).</span><span class="sxs-lookup"><span data-stu-id="a8314-599">On the mobile device, sign in to warehouse *62* by using the user ID that you created for this scenario (or the user ID of an existing demo data user).</span></span>
1. <span data-ttu-id="a8314-600">En el menú principal, seleccione **Saliente**.</span><span class="sxs-lookup"><span data-stu-id="a8314-600">On the main menu, select **Outbound**.</span></span>
1. <span data-ttu-id="a8314-601">En el menú **Saliente**, seleccione **Cargar desde ordenación**.</span><span class="sxs-lookup"><span data-stu-id="a8314-601">On the **Outbound** menu, select **Load from Sorting**.</span></span>
1. <span data-ttu-id="a8314-602">Introduzca el id. de matrícula de destino de la primera posición de ordenación, *SP01*.</span><span class="sxs-lookup"><span data-stu-id="a8314-602">Enter the target LP ID from the first sort position, *SP01*.</span></span> <span data-ttu-id="a8314-603">Establezca el campo **Id.** en *PLP01*.</span><span class="sxs-lookup"><span data-stu-id="a8314-603">Set the **ID** field to *PLP01*.</span></span>
1. <span data-ttu-id="a8314-604">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a8314-604">Select **OK**.</span></span>
1. <span data-ttu-id="a8314-605">La página **Selección de inventario ordenado: selección** muestra el trabajo de selección que debe realizarse.</span><span class="sxs-lookup"><span data-stu-id="a8314-605">The **Sorted inventory picking: Pick** page shows the pick work that must be done.</span></span> <span data-ttu-id="a8314-606">Seleccione la ubicación *ORDENAR* y la matrícula de destino *PLP01*, que tiene varios artículos y una cantidad de *3*.</span><span class="sxs-lookup"><span data-stu-id="a8314-606">Pick from the *SORT* location and target LP *PLP01*, which has multiple items and a quantity of *3*.</span></span>
1. <span data-ttu-id="a8314-607">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a8314-607">Select **OK**.</span></span>
1. <span data-ttu-id="a8314-608">La página **Selección de inventario ordenado: colocación** muestra el trabajo de colocación que debe realizarse.</span><span class="sxs-lookup"><span data-stu-id="a8314-608">The **Sorted inventory picking: Put** page shows the put work that must be done.</span></span> <span data-ttu-id="a8314-609">Realice la colocación en la ubicación *Baydoor* y la matrícula de destino *PLP01*, que tiene varios artículos y una cantidad de *3*.</span><span class="sxs-lookup"><span data-stu-id="a8314-609">Put to the *Baydoor* location and target LP *PLP01*, which has multiple items and a quantity of *3*.</span></span>
1. <span data-ttu-id="a8314-610">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a8314-610">Select **OK**.</span></span>

    <span data-ttu-id="a8314-611">El trabajo se completó.</span><span class="sxs-lookup"><span data-stu-id="a8314-611">Work is completed.</span></span>

1. <span data-ttu-id="a8314-612">Introduzca el id. de matrícula de destino de la segunda posición de ordenación, *SP02*.</span><span class="sxs-lookup"><span data-stu-id="a8314-612">Enter the target license plate ID from the second sort position, *SP02*.</span></span> <span data-ttu-id="a8314-613">Establezca el campo **Id.** en *PLP02*.</span><span class="sxs-lookup"><span data-stu-id="a8314-613">Set the **ID** field to *PLP02*.</span></span>
1. <span data-ttu-id="a8314-614">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a8314-614">Select **OK**.</span></span>
1. <span data-ttu-id="a8314-615">La página **Selección de inventario ordenado: selección** muestra el trabajo de selección que debe realizarse.</span><span class="sxs-lookup"><span data-stu-id="a8314-615">The **Sorted inventory picking: Pick** page shows the pick work that must be done.</span></span> <span data-ttu-id="a8314-616">Seleccione la ubicación *ORDENAR* y la matrícula de destino *PLP02*, que tiene varios artículos y una cantidad de *1*.</span><span class="sxs-lookup"><span data-stu-id="a8314-616">Pick from the *SORT* location and target LP *PLP02*, which has multiple items and a quantity of *1*.</span></span>
1. <span data-ttu-id="a8314-617">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a8314-617">Select **OK**.</span></span>
1. <span data-ttu-id="a8314-618">La página **Selección de inventario ordenado: colocación** muestra el trabajo de colocación que debe realizarse.</span><span class="sxs-lookup"><span data-stu-id="a8314-618">The **Sorted inventory picking: Put** page shows the put work that must be done.</span></span> <span data-ttu-id="a8314-619">Realice la colocación en la ubicación *Baydoor* y la matrícula de destino *PLP02*, que tiene varios artículos y una cantidad de *1*.</span><span class="sxs-lookup"><span data-stu-id="a8314-619">Put to the *Baydoor* location and target LP *PLP02*, which has multiple items and a quantity of *1*.</span></span>
1. <span data-ttu-id="a8314-620">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a8314-620">Select **OK**.</span></span>

    <span data-ttu-id="a8314-621">El trabajo se completó.</span><span class="sxs-lookup"><span data-stu-id="a8314-621">Work is completed.</span></span>

<span data-ttu-id="a8314-622">A partir de ese punto, se aplican todos los demás procesos de almacén.</span><span class="sxs-lookup"><span data-stu-id="a8314-622">From this point forward, all other warehouse processes apply.</span></span>
