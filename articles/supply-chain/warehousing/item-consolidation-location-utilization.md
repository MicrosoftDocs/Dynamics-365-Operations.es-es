---
title: 'Consolidación de artículos: utilización de ubicación'
description: Este tema proporciona información sobre la funcionalidad que facilita a los gerentes de almacén ver y filtrar la utilización volumétrica de ubicaciones en todo el almacén. Los gerentes pueden seleccionar ubicaciones y crear trabajos de movimiento de inventario directamente desde la página Consolidación de artículos para consolidar artículos y, por lo tanto, hacer un mejor uso del espacio de almacén.
author: Mirzaab
manager: tfehr
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSPhysDimUOM, WHSMovementType, WHSItemConsolidationForm, WHSRFMenu, WHSRFMenuItem
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-16
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: 6a328b20c1cfb2fc376ab4656c64cf585a5aa015
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "4437178"
---
# <a name="item-consolidation---location-utilization"></a><span data-ttu-id="fdaf9-104">Consolidación de artículos: utilización de ubicación</span><span class="sxs-lookup"><span data-stu-id="fdaf9-104">Item consolidation - location utilization</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="fdaf9-105">Este tema proporciona información sobre la funcionalidad que facilita a los gerentes de almacén ver y filtrar la utilización volumétrica de ubicaciones en todo el almacén.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-105">This topic provides information about functionality that makes it easy for warehouse managers to view and filter the volumetric utilization of locations across the warehouse.</span></span> <span data-ttu-id="fdaf9-106">Los gerentes pueden seleccionar ubicaciones y crear trabajos de movimiento de inventario directamente desde la página **Consolidación de artículos** para consolidar artículos y, por lo tanto, hacer un mejor uso del espacio de almacén.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-106">Managers can select locations and create inventory movement work directly from the **Item Consolidation** page to consolidate items and therefore make better use of warehouse space.</span></span>

## <a name="turn-on-the-features"></a><span data-ttu-id="fdaf9-107">Activar las características</span><span class="sxs-lookup"><span data-stu-id="fdaf9-107">Turn on the features</span></span>

<span data-ttu-id="fdaf9-108">Antes de poder usar las funciones que se describen en este tema, debe activarlas en su sistema.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-108">Before you can use the features that are described in this topic, you must turn them on in your system.</span></span> <span data-ttu-id="fdaf9-109">Los administradores pueden usar la configuración de [Gestión de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de estas funciones y activarlas si es necesario.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-109">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the features and turn them on if they are required.</span></span> <span data-ttu-id="fdaf9-110">Active las dos siguientes características, en el orden en que se enumeran.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-110">Turn on both the following features, in the order that they are listed in.</span></span> <span data-ttu-id="fdaf9-111">(Ambas características son para el módulo **Gestión de almacenes**).</span><span class="sxs-lookup"><span data-stu-id="fdaf9-111">(Both features are for the **Warehouse management** module.)</span></span>

1. <span data-ttu-id="fdaf9-112">Estado de ubicación de almacén</span><span class="sxs-lookup"><span data-stu-id="fdaf9-112">Warehouse location status</span></span>
2. <span data-ttu-id="fdaf9-113">Uso de la ubicación de consolidación de artículos</span><span class="sxs-lookup"><span data-stu-id="fdaf9-113">Item consolidation location utilization</span></span>

## <a name="warehouse-location-status"></a><span data-ttu-id="fdaf9-114">Estado de ubicación de almacén</span><span class="sxs-lookup"><span data-stu-id="fdaf9-114">Warehouse location status</span></span>

<span data-ttu-id="fdaf9-115">La característica *Estado de ubicación del almacén* agrega cuatro nuevos campos a la página **Ubicaciones** para rastrear información adicional sobre el estado actual de la ubicación:</span><span class="sxs-lookup"><span data-stu-id="fdaf9-115">The *Warehouse location status* feature adds four new fields to the **Locations** page to track additional information about the current state of the location:</span></span>

- <span data-ttu-id="fdaf9-116">**Número de artículo**: el artículo que se encuentra actualmente en la ubicación.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-116">**Item number** – The item that is currently in the location.</span></span> <span data-ttu-id="fdaf9-117">Si la ubicación contiene varios artículos, este campo estará en blanco.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-117">If the location contains multiple items, this field will be blank.</span></span>
- <span data-ttu-id="fdaf9-118">**Fecha y hora de la última actividad**: la marca de tiempo de la última transacción de almacén que se realizó en la ubicación.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-118">**Last activity date and time** – The timestamp of the last warehouse transaction that was performed against the location.</span></span>
- <span data-ttu-id="fdaf9-119">**Fecha de vencimiento**: la fecha en la que se llevó al almacén el inventario en la ubicación.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-119">**Aging date** – The date when the inventory in the location was brought into the warehouse.</span></span> <span data-ttu-id="fdaf9-120">Esta fecha se calcula en función de la fecha de vencimiento de la matrícula.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-120">This date is calculated based on the license plate aging date.</span></span> <span data-ttu-id="fdaf9-121">Aunque esta fecha es precisa para ubicaciones que tienen seguimiento de matrícula, podría no serla para ubicaciones que no lo tienen.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-121">Although this date is accurate for license plate–tracked locations, it might not be accurate for locations that aren't license plate–tracked.</span></span>
- <span data-ttu-id="fdaf9-122">**Estado de ubicación**: el estado de la ubicación.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-122">**Location status** – The status of the location.</span></span> <span data-ttu-id="fdaf9-123">Hay cuatro valores disponibles:</span><span class="sxs-lookup"><span data-stu-id="fdaf9-123">Four values are available:</span></span>

    - <span data-ttu-id="fdaf9-124">**Indeterminado**: el perfil de ubicación no sigue el estado.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-124">**Undetermined** – The location profile doesn't track status.</span></span> <span data-ttu-id="fdaf9-125">Por lo tanto, el estado actual es desconocido.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-125">Therefore, the current status is unknown.</span></span>
    - <span data-ttu-id="fdaf9-126">**Vacío**: actualmente no hay inventario en la ubicación.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-126">**Empty** – No inventory is currently in the location.</span></span>
    - <span data-ttu-id="fdaf9-127">**Selección**: se han realizado transacciones de salida en la ubicación después de estar vacía por última vez.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-127">**Picking** – Outbound transactions have been performed against the location after it was last empty.</span></span>
    - <span data-ttu-id="fdaf9-128">**Almacenamiento**: se han realizado transacciones de entrada desde que estuvo vacía por última vez.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-128">**Storage** – Only inbound transactions have been performed since the location was last empty.</span></span>

<span data-ttu-id="fdaf9-129">Estos campos permiten a los directores de almacén obtener una mejor visión general del estado de las ubicaciones del almacén.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-129">These fields let warehouse managers get a better overview of the status of the locations in the warehouse.</span></span> <span data-ttu-id="fdaf9-130">También permiten generar informes y filtros más avanzados.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-130">They also allow for more advanced reporting and filtering.</span></span>

## <a name="set-up-item-consolidation-and-location-utilization"></a><span data-ttu-id="fdaf9-131">Configurar la consolidación de artículos y la utilización de ubicación</span><span class="sxs-lookup"><span data-stu-id="fdaf9-131">Set up item consolidation and location utilization</span></span>

<span data-ttu-id="fdaf9-132">Esta sección describe cómo preparar su sistema para utilizar la consolidación de artículos y la utilización de la ubicación.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-132">This section describes how to prepare your system to use item consolidation and location utilization.</span></span> <span data-ttu-id="fdaf9-133">Los procedimientos utilizan valores de muestra de los datos de demostración estándar.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-133">The procedures use sample values from the standard demo data.</span></span> <span data-ttu-id="fdaf9-134">Si planea trabajar en el escenario de ejemplo que se proporciona más adelante en este tema, seleccione la entidad jurídica **USMF** (que contiene los datos de demostración estándar) y cree cada registro que se describe en esta sección.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-134">If you plan to work through the example scenario that is provided later in this topic, select the **USMF** legal entity (which contains the standard demo data), and create each record that is described in this section.</span></span> <span data-ttu-id="fdaf9-135">Si no planea trabajar en el escenario de ejemplo, los valores que se proporcionan aquí pueden considerarse ejemplos de los tipos de configuración que debe completar para usar las funciones.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-135">If you don't plan to work through the example scenario, the values that are provided here can be considered examples of the types of setup that you must complete to use the features.</span></span>

### <a name="released-product"></a><span data-ttu-id="fdaf9-136">Producto emitido</span><span class="sxs-lookup"><span data-stu-id="fdaf9-136">Released product</span></span>

1. <span data-ttu-id="fdaf9-137">Vaya a **Gestión de información de productos \> Productos \> Productos despachados**.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-137">Go to **Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="fdaf9-138">En el campo **Número de artículo**, seleccione *M9201* y abra la página de detalles.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-138">In the **Item number** field, select *M9201*, and open the details page.</span></span>
1. <span data-ttu-id="fdaf9-139">En el panel Acciones, en la pestaña **Administrar inventario**, en el grupo **Almacén**, seleccione **Dimensiones físicas**.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-139">On the Action Pane, on the **Manage inventory** tab, in the **Warehouse** group, select **Physical dimensions**.</span></span>
1. <span data-ttu-id="fdaf9-140">En la página **Dimensión física**, en el panel Acciones, seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-140">On the **Physical dimension** page, on the Action Pane, select **New**.</span></span>

    <span data-ttu-id="fdaf9-141">Se agrega una nueva línea a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-141">A new line is added to the grid.</span></span> <span data-ttu-id="fdaf9-142">El campo **Número de artículo** está preestablecido.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-142">The **Item number** field is preset.</span></span>

1. <span data-ttu-id="fdaf9-143">En el campo **Unidad**, seleccione *ea*.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-143">In the **Unit** field, select *ea*.</span></span> <span data-ttu-id="fdaf9-144">Los campos restantes de la línea se configuran automáticamente.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-144">The remaining fields on the line are automatically set.</span></span>
1. <span data-ttu-id="fdaf9-145">Seleccione **Guardar** y cierre la página.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-145">Select **Save**, and close the page.</span></span>

### <a name="location-profile"></a><span data-ttu-id="fdaf9-146">Perfil de ubicación</span><span class="sxs-lookup"><span data-stu-id="fdaf9-146">Location profile</span></span>

1. <span data-ttu-id="fdaf9-147">Vaya a **Gestión de almacenes \> Configurar \> Almacén \> Perfiles de ubicación**.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-147">Go to **Warehouse management \> Setup \> Warehouse \> Location profiles**.</span></span>
1. <span data-ttu-id="fdaf9-148">En la lista de perfiles de ubicación, seleccione **PLANTA-05**.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-148">In the list of location profiles, select **FLOOR-05**.</span></span>
1. <span data-ttu-id="fdaf9-149">En el panel Acciones, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-149">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="fdaf9-150">En la ficha desplegable **General**, asegúrese de que las siguientes opciones estén configuradas en *Sí*:</span><span class="sxs-lookup"><span data-stu-id="fdaf9-150">On the **General** FastTab, make sure that both the following options are set to *Yes*:</span></span>

    - <span data-ttu-id="fdaf9-151">Habilitar artículo en ubicación</span><span class="sxs-lookup"><span data-stu-id="fdaf9-151">Enable item in location</span></span>
    - <span data-ttu-id="fdaf9-152">Habilitar estado de la ubicación</span><span class="sxs-lookup"><span data-stu-id="fdaf9-152">Enable location status</span></span>

1. <span data-ttu-id="fdaf9-153">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-153">Select **Save**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="fdaf9-154">Si las opciones **Habilitar elemento en la ubicación** y **Habilitar estado de ubicación** ya estaban configuradas en *Sí*, salte a las instrucciones para configurar la ficha desplegable **Dimensiones** en el paso 10.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-154">If the **Enable item in location** and **Enable location status** options were already set to *Yes*, skip ahead to the instructions for setting up the **Dimensions** FastTab in step 10.</span></span> <span data-ttu-id="fdaf9-155">Si las opciones aún no estaban configuradas en *Sí*, debe ejecutar una comprobación de coherencia para el módulo **Gestión de almacenes** después de configurarlos manualmente.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-155">If the options weren't already set to *Yes*, you must run a consistency check for the **Warehouse management** module after you manually set them.</span></span> <span data-ttu-id="fdaf9-156">En este caso, continúe con el siguiente paso.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-156">In this case, continue to the next step.</span></span>

1. <span data-ttu-id="fdaf9-157">Para ejecutar la comprobación de coherencia, vaya a **Administración del sistema \> Tareas periódicas \> Base de datos \> Verificación de coherencia**.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-157">To run the consistency check, go to **System administration \> Periodic tasks \> Database \> Consistency check**.</span></span>
1. <span data-ttu-id="fdaf9-158">En el cuadro de diálogo **Comprobación de coherencia**, establezca los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="fdaf9-158">In the **Consistency check** dialog box, set the following values:</span></span>

    - <span data-ttu-id="fdaf9-159">**Módulo:** *Gestión de almacén*</span><span class="sxs-lookup"><span data-stu-id="fdaf9-159">**Module:** *Warehouse management*</span></span>
    - <span data-ttu-id="fdaf9-160">**Comprobar/corregir:** *Comprobar*</span><span class="sxs-lookup"><span data-stu-id="fdaf9-160">**Check/Fix:** *Check*</span></span>
    - <span data-ttu-id="fdaf9-161">**Fecha desde**: deje este campo en blanco.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-161">**From date:** Leave this field blank.</span></span>
    - <span data-ttu-id="fdaf9-162">**Comprobación de consistencia del estado de ubicación del almacén:** seleccione esta casilla de verificación.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-162">**Warehouse location status consistency check:** Select this check box.</span></span>

1. <span data-ttu-id="fdaf9-163">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-163">Select **OK**.</span></span>

    > [!TIP]
    > <span data-ttu-id="fdaf9-164">Recibirá una notificación cuando se complete la comprobación de coherencia.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-164">When the consistency check is completed, you receive a notification.</span></span> <span data-ttu-id="fdaf9-165">Abra el [Centro de acciones](../../fin-ops-core/fin-ops/get-started/user-interface-elements.md#notifications) para ver el mensaje.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-165">Open the [Action Center](../../fin-ops-core/fin-ops/get-started/user-interface-elements.md#notifications) to view the message.</span></span> <span data-ttu-id="fdaf9-166">Seleccione **Detalles del mensaje** para ver los detalles.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-166">Select **Message details** to view the details.</span></span>
    >
    > <span data-ttu-id="fdaf9-167">Si el mensaje para la comprobación de coherencia dice: "Se encontró información de estado de ubicación incorrecta para la ubicación XXXX en el almacén XX", debe volver a ejecutar la comprobación de coherencia.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-167">If the message for the consistency check states, "Incorrect location status information found for location XXXX in warehouse XX," you must run the consistency check again.</span></span> <span data-ttu-id="fdaf9-168">Esta vez, configure el campo **Comprobar/arreglar** en *Arreglar error*.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-168">This time, set the **Check/Fix** field to *Fix error*.</span></span> <span data-ttu-id="fdaf9-169">Vea los mensajes para asegurarse de que no se encontraron errores.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-169">View the messages to make sure that no errors were found.</span></span>

1. <span data-ttu-id="fdaf9-170">Ahora debe terminar de configurar el perfil de ubicación.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-170">You must now finish setting up the location profile.</span></span> <span data-ttu-id="fdaf9-171">Vuelva a **Gestión de almacenes \> Configurar \> Almacén \> Perfiles de ubicación**, seleccione el perfil de ubicación **PLANTA-05** y luego, en el panel de acciones, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-171">Go back to **Warehouse management \> Setup \> Warehouse \> Location profiles**, select location profile **FLOOR-05**, and then, on the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="fdaf9-172">En la ficha desplegable **Dimensiones**, establezca los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="fdaf9-172">On the **Dimensions** FastTab, set the following values:</span></span>

    - <span data-ttu-id="fdaf9-173">**Porcentaje de utilización de volumen:** *100*</span><span class="sxs-lookup"><span data-stu-id="fdaf9-173">**Volume utilization percentage:** *100*</span></span>
    - <span data-ttu-id="fdaf9-174">**Método volumétrico utilizado para la ubicación del inventario:** *usar volumen de ubicación*</span><span class="sxs-lookup"><span data-stu-id="fdaf9-174">**Volumetric method used for inventory location:** *Use location volume*</span></span>
    - <span data-ttu-id="fdaf9-175">**Altura real de la ubicación:** *10*</span><span class="sxs-lookup"><span data-stu-id="fdaf9-175">**Actual location height:** *10*</span></span>
    - <span data-ttu-id="fdaf9-176">**Ancho real de la ubicación:** *10*</span><span class="sxs-lookup"><span data-stu-id="fdaf9-176">**Actual location width:** *10*</span></span>
    - <span data-ttu-id="fdaf9-177">**Profundidad real de la ubicación:** *10*</span><span class="sxs-lookup"><span data-stu-id="fdaf9-177">**Actual location depth:** *10*</span></span>
    - <span data-ttu-id="fdaf9-178">**Peso máximo:** *100*</span><span class="sxs-lookup"><span data-stu-id="fdaf9-178">**Maximum weight:** *100*</span></span>

1. <span data-ttu-id="fdaf9-179">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-179">Select **Save**.</span></span>

### <a name="mobile-device-menu-items"></a><span data-ttu-id="fdaf9-180">Elementos de menú del dispositivo móvil</span><span class="sxs-lookup"><span data-stu-id="fdaf9-180">Mobile device menu items</span></span>

1. <span data-ttu-id="fdaf9-181">Vaya a **Administración de almacenes \> Configurar \> Dispositivo móvil \> Elementos de menú del dispositivo móvil**.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-181">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu items**.</span></span>
1. <span data-ttu-id="fdaf9-182">En el panel Acciones, seleccione **Nuevo** para crear un elemento de menú para ordenación.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-182">On the Action Pane, select **New** to create a menu item for sorting.</span></span>
1. <span data-ttu-id="fdaf9-183">Establezca los siguientes valores en el encabezado:</span><span class="sxs-lookup"><span data-stu-id="fdaf9-183">In the header, set the following values:</span></span>

    - <span data-ttu-id="fdaf9-184">**Nombre del elemento del menú:** *Ajustar en*</span><span class="sxs-lookup"><span data-stu-id="fdaf9-184">**Menu item name:** *Adjust In*</span></span>
    - <span data-ttu-id="fdaf9-185">**Título:** *Ajustar en*</span><span class="sxs-lookup"><span data-stu-id="fdaf9-185">**Title:** *Adjust In*</span></span>
    - <span data-ttu-id="fdaf9-186">**Modo:** *Trabajo*</span><span class="sxs-lookup"><span data-stu-id="fdaf9-186">**Mode:** *Work*</span></span>
    - <span data-ttu-id="fdaf9-187">**Usar trabajo existente:** *No*</span><span class="sxs-lookup"><span data-stu-id="fdaf9-187">**Use existing work:** *No*</span></span>

1. <span data-ttu-id="fdaf9-188">En la ficha desplegable **General**, establezca los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="fdaf9-188">On the **General** FastTab, set the following values:</span></span>

    - <span data-ttu-id="fdaf9-189">**Proceso de creación de trabajo:** *Ajuste en*</span><span class="sxs-lookup"><span data-stu-id="fdaf9-189">**Work creation process:** *Adjustment in*</span></span>
    - <span data-ttu-id="fdaf9-190">**Tipos de ajuste de inventario:** *Ajustar en*</span><span class="sxs-lookup"><span data-stu-id="fdaf9-190">**Inventory adjustment types:** *Adjust in*</span></span>

1. <span data-ttu-id="fdaf9-191">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-191">Select **Save**.</span></span>

### <a name="mobile-device-menu"></a><span data-ttu-id="fdaf9-192">Menú del dispositivo móvil</span><span class="sxs-lookup"><span data-stu-id="fdaf9-192">Mobile device menu</span></span>

1. <span data-ttu-id="fdaf9-193">Vaya a **Administración de almacenes \> Configuración \> Dispositivo móvil \> Menú del dispositivo móvil**.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-193">Go to **Warehouse management \> Setup \> Mobile device \> Mobile device menu**.</span></span>
1. <span data-ttu-id="fdaf9-194">En la lista de menús, seleccione **Inventario**.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-194">In the list of menus, select **Inventory**.</span></span>
1. <span data-ttu-id="fdaf9-195">En el panel Acciones, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-195">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="fdaf9-196">En la lista **Menús disponibles y elementos de menú**, busque y seleccione el elemento de menú **Ajustar en**.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-196">In the **Available Menus And Menu Items** list, find and select the **Adjust In** menu item.</span></span>
1. <span data-ttu-id="fdaf9-197">Seleccione el botón de flecha derecha para mover **Ajustar en** a la lista **Estructura del menú**.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-197">Select the right arrow button to move **Adjust In** to the **Menu Structure** list.</span></span> <span data-ttu-id="fdaf9-198">De esta manera, agrega su nuevo elemento de menú al menú seleccionado.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-198">In this way, you add the new menu item to the selected menu.</span></span>
1. <span data-ttu-id="fdaf9-199">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-199">Select **Save**.</span></span>

### <a name="movement-types"></a><span data-ttu-id="fdaf9-200">Tipos de movimiento</span><span class="sxs-lookup"><span data-stu-id="fdaf9-200">Movement types</span></span>

1. <span data-ttu-id="fdaf9-201">Vaya a **Gestión de almacenes \> Configurar \> Inventario \> Tipos de movimiento**.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-201">Go to **Warehouse management \> Setup \> Inventory \> Movement types**.</span></span>
1. <span data-ttu-id="fdaf9-202">En el panel de acción, seleccione **Nuevo** y luego establezca los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="fdaf9-202">On the Action Pane, select **New**, and then set the following values:</span></span>

    - <span data-ttu-id="fdaf9-203">**Código de tipo de movimiento:** *CONSOLIDAR*</span><span class="sxs-lookup"><span data-stu-id="fdaf9-203">**Movement type code:** *CONSOLIDATE*</span></span>
    - <span data-ttu-id="fdaf9-204">**Descripción:** *Consolidar ubicaciones*</span><span class="sxs-lookup"><span data-stu-id="fdaf9-204">**Description:** *Consolidate locations*</span></span>
    - <span data-ttu-id="fdaf9-205">**Id. de la clase de trabajo:** *InvMov*</span><span class="sxs-lookup"><span data-stu-id="fdaf9-205">**Work class ID:** *InvMov*</span></span>

1. <span data-ttu-id="fdaf9-206">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-206">Select **Save**.</span></span>

## <a name="example-scenario"></a><span data-ttu-id="fdaf9-207">Supuesto de ejemplo</span><span class="sxs-lookup"><span data-stu-id="fdaf9-207">Example scenario</span></span>

<span data-ttu-id="fdaf9-208">El siguiente escenario usa la aplicación de almacén en un dispositivo móvil para hacer un *ajuste en* inventario a dos ubicaciones del almacén.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-208">The following scenario uses the warehouse app on a mobile device to make an inventory *adjustment in* to two locations in the warehouse.</span></span>

### <a name="add-inventory-to-locations"></a><span data-ttu-id="fdaf9-209">Agregar inventario a ubicaciones</span><span class="sxs-lookup"><span data-stu-id="fdaf9-209">Add inventory to locations</span></span>

1. <span data-ttu-id="fdaf9-210">Inicie sesión en el dispositivo móvil como un usuario configurado para el almacén *51*.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-210">Sign in to the mobile device as a user who is set up for warehouse *51*.</span></span>
1. <span data-ttu-id="fdaf9-211">Vaya a **Inventario \> Ajustar en**.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-211">Go to **Inventory \> Adjust In**.</span></span>

    <span data-ttu-id="fdaf9-212">Ahora introducirá el primer ajuste de ubicación.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-212">You will now enter the first location adjustment.</span></span>

1. <span data-ttu-id="fdaf9-213">En la tarea **Ajuste en**, seleccione la ubicación para realizar el ajuste de inventario.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-213">In the **Adjustment in** task, select the location to make the inventory adjustment for.</span></span> <span data-ttu-id="fdaf9-214">En el campo **Ubicación**, seleccione *LP-001*.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-214">In the **LOC** field, select *LP-001*.</span></span>
1. <span data-ttu-id="fdaf9-215">Confirme la ubicación.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-215">Confirm the location.</span></span>
1. <span data-ttu-id="fdaf9-216">Cree un Id. de matrícula para el artículo que se agregará a la ubicación.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-216">Create a license plate ID for the item that will be added to the location.</span></span> <span data-ttu-id="fdaf9-217">En el campo **Matrícula**, introduzca *LP00101*.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-217">In the **LP** field, enter *LP00101*.</span></span>
1. <span data-ttu-id="fdaf9-218">Confirme la matrícula.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-218">Confirm the license plate.</span></span>
1. <span data-ttu-id="fdaf9-219">Introduzca el artículo que se agregará a la matrícula.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-219">Enter the item that will be added to the license plate.</span></span> <span data-ttu-id="fdaf9-220">En el campo **ITEM**, introduzca *M9201*.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-220">In the **ITEM** field, enter *M9201*.</span></span>
1. <span data-ttu-id="fdaf9-221">Confirme el artículo.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-221">Confirm the item.</span></span>
1. <span data-ttu-id="fdaf9-222">Introduzca la cantidad del artículo que se agregará.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-222">Enter the quantity of the item that will be added.</span></span> <span data-ttu-id="fdaf9-223">En el campo **CANTIDAD**, escriba *10*.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-223">In the **QTY** field, enter *10*.</span></span>
1. <span data-ttu-id="fdaf9-224">Confirme la cantidad.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-224">Confirm the quantity.</span></span>

    <span data-ttu-id="fdaf9-225">Recibe un mensaje "Trabajo completado".</span><span class="sxs-lookup"><span data-stu-id="fdaf9-225">You receive a "Work Completed" message.</span></span> <span data-ttu-id="fdaf9-226">Ahora introducirá el segundo ajuste de ubicación.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-226">You will now enter the second location adjustment.</span></span>

1. <span data-ttu-id="fdaf9-227">En la tarea **Ajuste en**, seleccione la ubicación para realizar el ajuste de inventario.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-227">In the **Adjustment in** task, select the location to make the inventory adjustment for.</span></span> <span data-ttu-id="fdaf9-228">En el campo **Ubicación**, seleccione *LP-002*.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-228">In the **LOC** field, select *LP-002*.</span></span>
1. <span data-ttu-id="fdaf9-229">Confirme la ubicación.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-229">Confirm the location.</span></span>
1. <span data-ttu-id="fdaf9-230">Cree un Id. de matrícula para el artículo que se agregará a la ubicación.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-230">Create a license plate ID for the item that will be added to the location.</span></span> <span data-ttu-id="fdaf9-231">En el campo **Matrícula**, introduzca *LP00201*.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-231">In the **LP** field, enter *LP00201*.</span></span>
1. <span data-ttu-id="fdaf9-232">Confirme la matrícula.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-232">Confirm the license plate.</span></span>
1. <span data-ttu-id="fdaf9-233">Introduzca el artículo que se agregará a la matrícula.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-233">Enter the item that will be added to the license plate.</span></span> <span data-ttu-id="fdaf9-234">En el campo **ITEM**, introduzca *M9201*.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-234">In the **ITEM** field, enter *M9201*.</span></span>
1. <span data-ttu-id="fdaf9-235">Confirme el artículo.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-235">Confirm the item.</span></span>
1. <span data-ttu-id="fdaf9-236">Introduzca la cantidad del artículo que se agregará.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-236">Enter the quantity of the item that will be added.</span></span> <span data-ttu-id="fdaf9-237">En el campo **CANTIDAD**, escriba *15*.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-237">In the **QTY** field, enter *15*.</span></span>
1. <span data-ttu-id="fdaf9-238">Confirme la cantidad.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-238">Confirm the quantity.</span></span>

    <span data-ttu-id="fdaf9-239">Recibe un mensaje "Trabajo completado".</span><span class="sxs-lookup"><span data-stu-id="fdaf9-239">You receive a "Work Completed" message.</span></span>

1. <span data-ttu-id="fdaf9-240">Seleccione el botón Menú (a veces denominado hamburguesa o botón de hamburguesa) y luego seleccione **Cancelar** para salir de la tarea **Ajuste en**.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-240">Select the Menu button (sometimes referred to as the hamburger or the hamburger button), and then select **Cancel** to exit the **Adjustment in** task.</span></span>

### <a name="consolidate-locations"></a><span data-ttu-id="fdaf9-241">Consolidar ubicaciones</span><span class="sxs-lookup"><span data-stu-id="fdaf9-241">Consolidate locations</span></span>

1. <span data-ttu-id="fdaf9-242">Vaya a **Gestión de almacenes \> Tareas periódicas \> Consolidación de artículos**.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-242">Go to **Warehouse management \> Periodic tasks \> Item consolidation**.</span></span>
1. <span data-ttu-id="fdaf9-243">En el encabezado, seleccione un almacén para realizar la consolidación.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-243">In the header, select a warehouse to do the consolidation for.</span></span> <span data-ttu-id="fdaf9-244">En el campo **Almacén**, introduzca *51*.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-244">In the **Warehouse** field, enter *51*.</span></span>

    <span data-ttu-id="fdaf9-245">Se muestra un registro para cada ubicación donde el artículo *M9201* se ajustó.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-245">A record is shown for each location where item *M9201* was adjusted.</span></span> <span data-ttu-id="fdaf9-246">La columna **Porcentaje de utilización** muestra la utilización volumétrica de cada ubicación.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-246">The **Utilization percentage** column shows the volumetric utilization of each location.</span></span>

1. <span data-ttu-id="fdaf9-247">Para consolidar el inventario, seleccione todas las ubicaciones que deben consolidarse y luego, en el panel Acciones, seleccione **Consolidar inventario**.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-247">To consolidate inventory, select all the locations that must be consolidated, and then, on the Action Pane, select **Consolidate Inventory**.</span></span>
1. <span data-ttu-id="fdaf9-248">En el cuadro de diálogo **Consolidar inventario**, especifique la ubicación y el tipo de movimiento que se debe utilizar para crear el trabajo para el movimiento de inventario.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-248">In the **Consolidate inventory** dialog box, specify the location and movement type that should be used to create the work for inventory movement.</span></span> <span data-ttu-id="fdaf9-249">Establezca los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="fdaf9-249">Set the following values:</span></span>

    - <span data-ttu-id="fdaf9-250">**Ubicación:** *LP-001*</span><span class="sxs-lookup"><span data-stu-id="fdaf9-250">**Location:** *LP-001*</span></span>
    - <span data-ttu-id="fdaf9-251">**Código de tipo de movimiento:** *CONSOLIDAR*</span><span class="sxs-lookup"><span data-stu-id="fdaf9-251">**Movement type code:** *CONSOLIDATE*</span></span>

1. <span data-ttu-id="fdaf9-252">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-252">Select **OK**.</span></span>
1. <span data-ttu-id="fdaf9-253">Recibirá un mensaje informativo que muestra el trabajo de movimiento que se ha creado.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-253">You receive an informational message that shows the movement work that was created.</span></span> <span data-ttu-id="fdaf9-254">Anote el Id. del trabajo de movimiento.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-254">Make a note of the movement work ID.</span></span>

### <a name="view-movement-work"></a><span data-ttu-id="fdaf9-255">Ver trabajo de movimiento</span><span class="sxs-lookup"><span data-stu-id="fdaf9-255">View movement work</span></span>

1. <span data-ttu-id="fdaf9-256">Vaya a **Gestión de almacenes \> Trabajo \> Detalles de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-256">Go to **Warehouse management \> Work \> Work details**.</span></span>
1. <span data-ttu-id="fdaf9-257">Ver el trabajo que se creó.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-257">View the work that was created.</span></span> <span data-ttu-id="fdaf9-258">Use el Id. de trabajo de movimiento de la consolidación de inventario para filtrar o buscar en la cuadrícula de trabajo.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-258">Use the movement work ID from the inventory consolidation to filter or search the work grid.</span></span>

    <span data-ttu-id="fdaf9-259">En este escenario, se utilizó una ubicación existente que tenía inventario como ubicación de consolidación de inventario.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-259">In this scenario, an existing location that had inventory was used as the inventory consolidation location.</span></span> <span data-ttu-id="fdaf9-260">Por lo tanto, solo se creó un Id. de trabajo.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-260">Therefore, only one work ID was created.</span></span>

    > [!NOTE]
   > <span data-ttu-id="fdaf9-261">El sistema crea un Id. de trabajo para cada movimiento que debe completarse.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-261">The system creates one work ID for each move that must be completed.</span></span> <span data-ttu-id="fdaf9-262">Si especifica una ubicación que ya contiene inventario, solo se crea un Id. de trabajo.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-262">If you specify a location that already contains inventory, only one work ID is created.</span></span> <span data-ttu-id="fdaf9-263">Si especifica una nueva ubicación, se crean dos Id. de trabajo.</span><span class="sxs-lookup"><span data-stu-id="fdaf9-263">If you specify a new location, two work IDs are created.</span></span>
