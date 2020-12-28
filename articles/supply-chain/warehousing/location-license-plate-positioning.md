---
title: Posición de matrícula de entidad de almacén de ubicación
description: El posicionamiento de la ubicación de la matrícula de entidad le permite ver dónde se encuentra una matrícula de entidad en una ubicación de paletas múltiples, como una ubicación que utiliza estanterías de paletas de doble profundidad.
author: Mirzaab
manager: tfehr
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLicensePlate, WHSLocationProfile, WHSLocDirTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: 7b0ebfb965e5a8f1bfe1857a9642d998dac2faf3
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "4437175"
---
# <a name="location-license-plate-positioning"></a><span data-ttu-id="0e908-103">Posición de matrícula de entidad de almacén de ubicación</span><span class="sxs-lookup"><span data-stu-id="0e908-103">Location license plate positioning</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0e908-104">El posicionamiento de la ubicación de la matrícula de entidad le permite ver dónde se encuentra una matrícula de entidad en una ubicación de paletas múltiples, como una ubicación que utiliza estanterías de paletas de doble profundidad.</span><span class="sxs-lookup"><span data-stu-id="0e908-104">License plate location positioning lets you see where a license plate is located in a multi-pallet location, such as a location that uses double-deep pallet racking.</span></span>

<span data-ttu-id="0e908-105">La función agrega un número de secuencia a cada matrícula de entidad que se coloca en una ubicación de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="0e908-105">The feature adds a sequence number to each license plate that is put into a storage location.</span></span> <span data-ttu-id="0e908-106">Este número de secuencia se usa para pedir las matrículas de entidad en la ubicación de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="0e908-106">This sequence number is used to order the license plates in the storage location.</span></span> <span data-ttu-id="0e908-107">Por lo tanto, la función admite de manera inteligente escenarios en los que los clientes están utilizando un sistema de estantería por gravedad y deben saber, con fines de selección, qué matrícula de entidad está orientada hacia el frente.</span><span class="sxs-lookup"><span data-stu-id="0e908-107">Therefore, the feature intelligently supports scenarios where customers are using a gravity racking system and must know, for picking purposes, which license plate is front-facing.</span></span>

<span data-ttu-id="0e908-108">Este tema presenta un escenario que muestra cómo configurar y usar la función.</span><span class="sxs-lookup"><span data-stu-id="0e908-108">This topic presents a scenario that shows how to set up and use the feature.</span></span>

## <a name="turn-on-the-location-license-plate-positioning-feature"></a><span data-ttu-id="0e908-109">Active la función de posicionamiento de matrícula de ubicación</span><span class="sxs-lookup"><span data-stu-id="0e908-109">Turn on the Location license plate positioning feature</span></span>

<span data-ttu-id="0e908-110">Antes de que pueda usar el posicionamiento de ubicación de matrícula de entidad, debe activar la función en su sistema.</span><span class="sxs-lookup"><span data-stu-id="0e908-110">Before you can use license plate location positioning, the feature must be turned on in your system.</span></span> <span data-ttu-id="0e908-111">Los administradores pueden usar el espacio de trabajo [Administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de la característica y activarla si es necesario.</span><span class="sxs-lookup"><span data-stu-id="0e908-111">Admins can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) workspace to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="0e908-112">Allí, la característica se enumera de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="0e908-112">There, the feature is listed in the following way:</span></span>

- <span data-ttu-id="0e908-113">**Módulo:** *Gestión de almacén*</span><span class="sxs-lookup"><span data-stu-id="0e908-113">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="0e908-114">**Nombre de la función:** *Posicionamiento de ubicación de matrícula de entidad*</span><span class="sxs-lookup"><span data-stu-id="0e908-114">**Feature name:** *Location license plate positioning*</span></span>

## <a name="example-scenario"></a><span data-ttu-id="0e908-115">Supuesto de ejemplo</span><span class="sxs-lookup"><span data-stu-id="0e908-115">Example scenario</span></span>

### <a name="make-sample-data-available"></a><span data-ttu-id="0e908-116">Hacer que los datos de muestra estén disponibles</span><span class="sxs-lookup"><span data-stu-id="0e908-116">Make sample data available</span></span>

<span data-ttu-id="0e908-117">Para resolver este escenario utilizando los valores que se sugieren aquí, debe trabajar en un sistema donde se instalen datos de muestra.</span><span class="sxs-lookup"><span data-stu-id="0e908-117">To work through this scenario by using the values that are suggested here, you must work on a system where sample data is installed.</span></span> <span data-ttu-id="0e908-118">Además, también debe seleccionar la entidad legal **USMF** antes de comenzar.</span><span class="sxs-lookup"><span data-stu-id="0e908-118">Additionally, you must select the **USMF** legal entity before you start.</span></span>

### <a name="set-up-the-feature-for-this-scenario"></a><span data-ttu-id="0e908-119">Configure la función para este escenario</span><span class="sxs-lookup"><span data-stu-id="0e908-119">Set up the feature for this scenario</span></span>

<span data-ttu-id="0e908-120">Complete los siguientes procedimientos para configurar la característica de *Posicionamiento de ubicación de matrícula de entidad* para el escenario que se presenta en este tema.</span><span class="sxs-lookup"><span data-stu-id="0e908-120">Complete the following procedures to set up the *Location license plate positioning* feature for the scenario that is presented in this topic.</span></span>

#### <a name="location-profiles"></a><span data-ttu-id="0e908-121">Perfiles de ubicación</span><span class="sxs-lookup"><span data-stu-id="0e908-121">Location profiles</span></span>

<span data-ttu-id="0e908-122">La función debe estar activada en el perfil de ubicación para cada ubicación donde se utilizará.</span><span class="sxs-lookup"><span data-stu-id="0e908-122">The feature must be turned on in the location profile for every location where it will be used.</span></span>

1. <span data-ttu-id="0e908-123">Vaya a **Gestión de almacenes \> Configurar \> Almacén \> Perfiles de ubicación**.</span><span class="sxs-lookup"><span data-stu-id="0e908-123">Go to **Warehouse management \> Setup \> Warehouse \> Location profiles**.</span></span>
1. <span data-ttu-id="0e908-124">En la lista de perfiles de ubicación en el panel izquierdo, seleccione **BULK-06**.</span><span class="sxs-lookup"><span data-stu-id="0e908-124">In the list of location profiles in the left pane, select **BULK-06**.</span></span>
1. <span data-ttu-id="0e908-125">En la ficha desplegable **General**, la función ha agregado dos nuevas opciones.</span><span class="sxs-lookup"><span data-stu-id="0e908-125">On the **General** FastTab, two new options have been added by the feature.</span></span> <span data-ttu-id="0e908-126">Establezca los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="0e908-126">Set the following values:</span></span>

    - <span data-ttu-id="0e908-127">**Habilitar la posición de la matrícula:** *Sí*</span><span class="sxs-lookup"><span data-stu-id="0e908-127">**Enable license plate position:** *Yes*</span></span>

        <span data-ttu-id="0e908-128">Cuando esta opción se establece en *Sí*, la posición de la matrícula de entidad se mantendrá para las matrícula de entidad en la ubicación.</span><span class="sxs-lookup"><span data-stu-id="0e908-128">When this option is set to *Yes*, the license plate position will be maintained for license plates in the location.</span></span>

    - <span data-ttu-id="0e908-129">**Mostrar la posición LP del dispositivo móvil:** *Sí*</span><span class="sxs-lookup"><span data-stu-id="0e908-129">**Display mobile device LP position:** *Yes*</span></span>

        <span data-ttu-id="0e908-130">Cuando esta opción se establece en *Sí*, la posición de la matrícula de entidad se mostrará a los usuarios de dispositivos móviles durante el ajuste y el recuento.</span><span class="sxs-lookup"><span data-stu-id="0e908-130">When this option is set to *Yes*, the license plate position will be shown to mobile device users during adjustment and counting.</span></span> <span data-ttu-id="0e908-131">Puede cambiar la configuración de esta opción solo cuando la función está activada.</span><span class="sxs-lookup"><span data-stu-id="0e908-131">You can change the setting of this option only when the feature is turned on.</span></span>

1. <span data-ttu-id="0e908-132">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="0e908-132">Select **Save**.</span></span>

#### <a name="location-directives"></a><span data-ttu-id="0e908-133">Directivas de ubicación</span><span class="sxs-lookup"><span data-stu-id="0e908-133">Location directives</span></span>

1. <span data-ttu-id="0e908-134">Vaya a **Gestión de almacenes \> Configurar \> Directivas de ubicación**.</span><span class="sxs-lookup"><span data-stu-id="0e908-134">Go to **Warehouse management \> Setup \> Location directives**.</span></span>
1. <span data-ttu-id="0e908-135">En el panel izquierdo, asegúrese de que el campo **Tipo de orden de trabajo** se establece en *Pedidos de ventas*.</span><span class="sxs-lookup"><span data-stu-id="0e908-135">In the left pane, make sure that the **Work order type** field is set to *Sales orders*.</span></span>
1. <span data-ttu-id="0e908-136">En la lista de directivas de ubicación, seleccione **61 SO Orden de recogida**.</span><span class="sxs-lookup"><span data-stu-id="0e908-136">In the list of location directives, select **61 SO Pick order**.</span></span>
1. <span data-ttu-id="0e908-137">En el panel Acciones, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="0e908-137">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="0e908-138">En la ficha desplegable **Líneas**, seleccione la línea que tiene un valor de **Secuencia de números** de *2*.</span><span class="sxs-lookup"><span data-stu-id="0e908-138">On the **Lines** FastTab, select the line that has a **Sequence number** value of *2*.</span></span>
1. <span data-ttu-id="0e908-139">En la ficha desplegable **Acciones de directiva de ubicación**, seleccione la línea que tiene un valor **Nombre** de *Elija por menos de palet* (debería ser la única línea) y cambie su valor **Secuencia de números** a *2*.</span><span class="sxs-lookup"><span data-stu-id="0e908-139">On the **Location Directive Actions** FastTab, select the line that has a **Name** value of *Pick for less than pallet* (it should be the only line), and change its **Sequence number** value to *2*.</span></span>
1. <span data-ttu-id="0e908-140">Seleccione **Nuevo** encima de la cuadrícula para agregar una línea para una nueva acción directiva de ubicación.</span><span class="sxs-lookup"><span data-stu-id="0e908-140">Select **New** above the grid to add a line for a new location directive action.</span></span>
1. <span data-ttu-id="0e908-141">En la nueva línea, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="0e908-141">On the new line, set the following values:</span></span>

    - <span data-ttu-id="0e908-142">**Número de secuencia:** *1*</span><span class="sxs-lookup"><span data-stu-id="0e908-142">**Sequence number:** *1*</span></span>
    - <span data-ttu-id="0e908-143">**Nombre:** *Elegir posición 1*</span><span class="sxs-lookup"><span data-stu-id="0e908-143">**Name:** *Pick position 1*</span></span>

1. <span data-ttu-id="0e908-144">Mientras la nueva línea aún está seleccionada, seleccione **Editar consulta** sobre la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="0e908-144">While the new line is still selected, select **Edit query** above the grid.</span></span>
1. <span data-ttu-id="0e908-145">En el editor de consultas, seleccione la pestaña **Uniones**.</span><span class="sxs-lookup"><span data-stu-id="0e908-145">In the query editor, select the **Joins** tab.</span></span>
1. <span data-ttu-id="0e908-146">Expanda la tabla **Ubicaciones** de unión para mostrar la unión a la tabla **Dimensiones de inventario**.</span><span class="sxs-lookup"><span data-stu-id="0e908-146">Expand the **Locations** table join to show the join to the **Inventory dimensions** table.</span></span>
1. <span data-ttu-id="0e908-147">Expanda la tabla **Dimensiones de inventario** de unión para mostrar la unión a la tabla **Inventario disponible**.</span><span class="sxs-lookup"><span data-stu-id="0e908-147">Expand the **Inventory dimensions** table join to show the join to the **On-hand inventory** table.</span></span>
1. <span data-ttu-id="0e908-148">Seleccione **Dimensiones de inventario** y luego seleccione **Agregar unión de tabla**.</span><span class="sxs-lookup"><span data-stu-id="0e908-148">Select **Inventory dimensions**, and then select **Add table join**.</span></span>
1. <span data-ttu-id="0e908-149">En la lista de tablas que aparece, en la columna **Relación**, seleccione **Matrícula (matrícula de entidad)**.</span><span class="sxs-lookup"><span data-stu-id="0e908-149">In the list of tables that appears, in the **Relation** column, select **License plate (License plate)**.</span></span> <span data-ttu-id="0e908-150">Luego seleccione **Seleccionar** para agregar **Matrícula de entidad** a la tabla de unión **Dimensiones de inventario**.</span><span class="sxs-lookup"><span data-stu-id="0e908-150">Then select **Select** to add **License plate** to the **Inventory dimensions** table join.</span></span>
1. <span data-ttu-id="0e908-151">Mientras **Matrícula de entidad** todavía está seleccionado, seleccione **Agregar unión de tabla**.</span><span class="sxs-lookup"><span data-stu-id="0e908-151">While **License plate** is still selected, select **Add table join**.</span></span>
1. <span data-ttu-id="0e908-152">En la lista de tablas que aparece, en la columna **Relación**, seleccione **Posicionamiento de ubicación de matrícula (matrícula de entidad)**.</span><span class="sxs-lookup"><span data-stu-id="0e908-152">In the list of tables that appears, in the **Relation** column, select **Location license plate positioning (License plate)**.</span></span> <span data-ttu-id="0e908-153">Luego seleccione **Seleccionar** para agregar **Posicionamiento de ubicación de matrícula de entidad** a la tabla de unión **Dimensiones de inventario**.</span><span class="sxs-lookup"><span data-stu-id="0e908-153">Then select **Select** to add **Location license plate positioning** to the **Inventory dimensions** table join.</span></span>

    <span data-ttu-id="0e908-154">![Uniones de tabla](media/LpTableJoin.png "Uniones de tabla")</span><span class="sxs-lookup"><span data-stu-id="0e908-154">![Table joins](media/LpTableJoin.png "Table joins")</span></span>

1. <span data-ttu-id="0e908-155">Seleccione **Aceptar** para confirmar las tablas unidas actualizadas y cerrar el editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="0e908-155">Select **OK** to confirm the updated joined tables and close the query editor.</span></span>
1. <span data-ttu-id="0e908-156">En la ficha desplegable **Acciones de directiva de ubicación**, seleccione **Editar consulta** para abrir de nuevo el cuadro de diálogo del editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="0e908-156">On the **Location Directive Actions** FastTab, select **Edit query** again to reopen to the query editor.</span></span>
1. <span data-ttu-id="0e908-157">En la ficha **Rango**, seleccione **Nuevo** para agregar una línea a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="0e908-157">On the **Range** tab, select **Add** to add a line to the grid.</span></span>
1. <span data-ttu-id="0e908-158">En la nueva línea, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="0e908-158">On the new line, set the following values:</span></span>

    - <span data-ttu-id="0e908-159">**Tabla:** *Posicionamiento de ubicación de matrícula de entidad*</span><span class="sxs-lookup"><span data-stu-id="0e908-159">**Table:** *Location license plate positioning*</span></span>
    - <span data-ttu-id="0e908-160">**Tabla derivada:** *Posicionamiento de ubicación de matrícula de entidad*</span><span class="sxs-lookup"><span data-stu-id="0e908-160">**Derived table:** *Location license plate positioning*</span></span>
    - <span data-ttu-id="0e908-161">**Campo:** *Posición LP*</span><span class="sxs-lookup"><span data-stu-id="0e908-161">**Field:** *LP Position*</span></span>
    - <span data-ttu-id="0e908-162">**Criterio:** *1*</span><span class="sxs-lookup"><span data-stu-id="0e908-162">**Criteria:** *1*</span></span>

    <span data-ttu-id="0e908-163">![Nuevo rango](media/LpPositionCriteria.png "Nuevo rango")</span><span class="sxs-lookup"><span data-stu-id="0e908-163">![New range](media/LpPositionCriteria.png "New range")</span></span>

1. <span data-ttu-id="0e908-164">Seleccione **Aceptar** para confirmar sus cambios y cerrar el editor de consultas.</span><span class="sxs-lookup"><span data-stu-id="0e908-164">Select **OK** to confirm your changes and close the query editor.</span></span>

### <a name="set-up-sample-data-for-this-scenario"></a><span data-ttu-id="0e908-165">Configure los datos de muestra para este escenario</span><span class="sxs-lookup"><span data-stu-id="0e908-165">Set up sample data for this scenario</span></span>

<span data-ttu-id="0e908-166">Para este escenario, el usuario debe iniciar sesión en la aplicación móvil de almacenamiento mediante el uso de un trabajador configurado para el almacén *61* para realizar trabajo.</span><span class="sxs-lookup"><span data-stu-id="0e908-166">For this scenario, the user must sign in to the warehousing mobile app by using a worker who is set up for warehouse *61* to perform work.</span></span> <span data-ttu-id="0e908-167">El usuario también debe completar las transacciones.</span><span class="sxs-lookup"><span data-stu-id="0e908-167">The user must also complete transactions.</span></span>

<span data-ttu-id="0e908-168">Debido a que la función *Posicionamiento de ubicación de matrícula de entidad* agrega un nuevo identificador para las posiciones de matrícula en una ubicación, primero debe crear algunos datos para admitir el escenario.</span><span class="sxs-lookup"><span data-stu-id="0e908-168">Because the *Location license plate positioning* feature adds a new identifier for license plate positions in a location, you must first create some data to support the scenario.</span></span>

#### <a name="spot-count-the-first-location"></a><span data-ttu-id="0e908-169">Recuento de la primera ubicación</span><span class="sxs-lookup"><span data-stu-id="0e908-169">Spot-count the first location</span></span>

1. <span data-ttu-id="0e908-170">Abra la aplicación móvil de almacenaje e inicie sesión en el almacén *61*.</span><span class="sxs-lookup"><span data-stu-id="0e908-170">Open the warehousing mobile app, and sign in to warehouse *61*.</span></span>
1. <span data-ttu-id="0e908-171">Vaya a **Inventario \> Recuento puntual**.</span><span class="sxs-lookup"><span data-stu-id="0e908-171">Go to **Inventory \> Spot Counting**.</span></span>
1. <span data-ttu-id="0e908-172">En la página **Recuento puntual**, configure el campo **Ubicación** a *01A01R1S1B*.</span><span class="sxs-lookup"><span data-stu-id="0e908-172">On the **Spot Counting** page, set the **Location** field to *01A01R1S1B*.</span></span>
1. <span data-ttu-id="0e908-173">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0e908-173">Select **OK**.</span></span>

    <span data-ttu-id="0e908-174">La página muestra la ubicación que introdujo.</span><span class="sxs-lookup"><span data-stu-id="0e908-174">The page shows the location that you entered.</span></span> <span data-ttu-id="0e908-175">También muestra el siguiente mensaje: "¿Ubicación completa, agregar nuevo LP o artículo?"</span><span class="sxs-lookup"><span data-stu-id="0e908-175">It also shows the following message: "Location complete, add new LP or Item?"</span></span>

1. <span data-ttu-id="0e908-176">Seleccione **Actualizar** para agregar un recuento en la ubicación.</span><span class="sxs-lookup"><span data-stu-id="0e908-176">Select **Refresh** to add a count in the location.</span></span>
1. <span data-ttu-id="0e908-177">En la página **Recuento de ciclos: agregar nuevo LP o artículo**, seleccione el campo **Artículo** y luego introduzca el valor *A0001*.</span><span class="sxs-lookup"><span data-stu-id="0e908-177">On the **Cycle Count: Add New LP or Item** page, select the **Item** field, and then enter the value *A0001*.</span></span>
1. <span data-ttu-id="0e908-178">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0e908-178">Select **OK**.</span></span>
1. <span data-ttu-id="0e908-179">En la página **Recuento de ciclos: agregar nuevo LP o artículo**, seleccione el campo **LP** y luego introduzca el valor *LP1001* (o cualquier otro número de matrícula de entidad de su elección).</span><span class="sxs-lookup"><span data-stu-id="0e908-179">On the **Cycle Count: Add New LP or Item** page, select the **LP** field, and then enter the value *LP1001* (or any other license plate number of your choice).</span></span>

    <span data-ttu-id="0e908-180">La página **Recuento de ciclos: agregar nuevo LP o artículo** muestra **Matrícula de entidad Posición 1**.</span><span class="sxs-lookup"><span data-stu-id="0e908-180">The **Cycle Count: Add New LP or Item** page shows **License Plate Position 1**.</span></span>

1. <span data-ttu-id="0e908-181">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0e908-181">Select **OK**.</span></span>

    <span data-ttu-id="0e908-182">Ahora debe especificar la cantidad del artículo que se cuenta en la matrícula de entidad.</span><span class="sxs-lookup"><span data-stu-id="0e908-182">You must now specify the quantity of the item that is counted on the license plate.</span></span>

1. <span data-ttu-id="0e908-183">Establezca el campo **Cantidad** a *10*.</span><span class="sxs-lookup"><span data-stu-id="0e908-183">Set the **Qty** field to *10*.</span></span>
1. <span data-ttu-id="0e908-184">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0e908-184">Select **OK**.</span></span>

    <span data-ttu-id="0e908-185">La página muestra la ubicación que introdujo.</span><span class="sxs-lookup"><span data-stu-id="0e908-185">The page shows the location that you entered.</span></span> <span data-ttu-id="0e908-186">También muestra el siguiente mensaje: "¿Ubicación completa, agregar nuevo LP o artículo?"</span><span class="sxs-lookup"><span data-stu-id="0e908-186">It also shows the following message: "Location complete, add new LP or Item?"</span></span>

1. <span data-ttu-id="0e908-187">Seleccione **Actualizar** para agregar otro recuento en la ubicación.</span><span class="sxs-lookup"><span data-stu-id="0e908-187">Select **Refresh** to add another count in the location.</span></span>
1. <span data-ttu-id="0e908-188">En la página **Recuento de ciclos: agregar nuevo LP o artículo**, seleccione el campo **Artículo** y luego introduzca el valor *A0002*.</span><span class="sxs-lookup"><span data-stu-id="0e908-188">On the **Cycle Count: Add New LP or Item** page, select the **Item** field, and then enter the value *A0002*.</span></span>
1. <span data-ttu-id="0e908-189">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0e908-189">Select **OK**.</span></span>
1. <span data-ttu-id="0e908-190">En la página **Recuento de ciclos: agregar nuevo LP o artículo**, seleccione el campo **LP** y luego introduzca el valor *LP1002* (o cualquier otra matrícula de entidad de almacén de su elección, siempre que difiera de la matrícula de entidad de almacén que especificó anteriormente).</span><span class="sxs-lookup"><span data-stu-id="0e908-190">On the **Cycle Count: Add New LP or Item** page, select the **LP** field, and then enter the value *LP1002* (or any other license plate number of your choice, provided that it differs from the license plate number that you specified earlier).</span></span>
1. <span data-ttu-id="0e908-191">Cambie la posición de la matrícula de entidad configurando el campo **Posición LP** a *2*.</span><span class="sxs-lookup"><span data-stu-id="0e908-191">Change the license plate position by setting the **LP Position** field to *2*.</span></span>
1. <span data-ttu-id="0e908-192">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0e908-192">Select **OK**.</span></span>
1. <span data-ttu-id="0e908-193">Especifique la cantidad del artículo que se cuenta en la matrícula de entidad configurando el campo **Cantidad** a *10*.</span><span class="sxs-lookup"><span data-stu-id="0e908-193">Specify the quantity of the item that is counted on the license plate by setting the **Qty** field to *10*.</span></span>
1. <span data-ttu-id="0e908-194">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0e908-194">Select **OK**.</span></span>

    <span data-ttu-id="0e908-195">La página muestra la ubicación que introdujo.</span><span class="sxs-lookup"><span data-stu-id="0e908-195">The page shows the location that you entered.</span></span> <span data-ttu-id="0e908-196">También muestra el siguiente mensaje: "¿Ubicación completa, agregar nuevo LP o artículo?"</span><span class="sxs-lookup"><span data-stu-id="0e908-196">It also shows the following message: "Location complete, add new LP or Item?"</span></span>

1. <span data-ttu-id="0e908-197">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0e908-197">Select **OK**.</span></span>

<span data-ttu-id="0e908-198">El trabajo se completó.</span><span class="sxs-lookup"><span data-stu-id="0e908-198">Work is now completed.</span></span>

#### <a name="spot-count-the-second-location"></a><span data-ttu-id="0e908-199">Recuento de la segunda ubicación</span><span class="sxs-lookup"><span data-stu-id="0e908-199">Spot-count the second location</span></span>

1. <span data-ttu-id="0e908-200">En la página **Recuento puntual**, configure el campo **Ubicación** a *01A01R1S2B*.</span><span class="sxs-lookup"><span data-stu-id="0e908-200">On the **Spot Counting** page, set the **Location** field to *01A01R1S2B*.</span></span>
1. <span data-ttu-id="0e908-201">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0e908-201">Select **OK**.</span></span>

    <span data-ttu-id="0e908-202">La página muestra la ubicación que introdujo.</span><span class="sxs-lookup"><span data-stu-id="0e908-202">The page shows the location that you entered.</span></span> <span data-ttu-id="0e908-203">También muestra el siguiente mensaje: "¿Ubicación completa, agregar nuevo LP o artículo?"</span><span class="sxs-lookup"><span data-stu-id="0e908-203">It also shows the following message: "Location complete, add new LP or Item?"</span></span>

1. <span data-ttu-id="0e908-204">Seleccione **Actualizar** para agregar un recuento en la ubicación.</span><span class="sxs-lookup"><span data-stu-id="0e908-204">Select **Refresh** to add a count in the location.</span></span>
1. <span data-ttu-id="0e908-205">En la página **Recuento de ciclos: agregar nuevo LP o artículo**, seleccione el campo **Artículo** y luego introduzca el valor *A0002*.</span><span class="sxs-lookup"><span data-stu-id="0e908-205">On the **Cycle Count: Add New LP or Item** page, select the **Item** field, and then enter the value *A0002*.</span></span>
1. <span data-ttu-id="0e908-206">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0e908-206">Select **OK**.</span></span>
1. <span data-ttu-id="0e908-207">En la página **Recuento de ciclos: agregar nuevo LP o artículo**, seleccione el campo **LP** y luego introduzca el valor *LP1003* (o cualquier otra matrícula de entidad de almacén de su elección, siempre que difiera de ambas matrículas de entidad de almacén que especificó anteriormente).</span><span class="sxs-lookup"><span data-stu-id="0e908-207">On the **Cycle Count: Add New LP or Item** page, select the **LP** field, and then enter the value *LP1003* (or any other license plate number of your choice, provided that it differs from the both the license plate numbers that you specified in the previous procedure).</span></span>

    <span data-ttu-id="0e908-208">La página **Recuento de ciclos: agregar nuevo LP o artículo** muestra **Matrícula de entidad Posición 1**.</span><span class="sxs-lookup"><span data-stu-id="0e908-208">The **Cycle Count: Add New LP or Item** page shows **License Plate Position 1**.</span></span>

1. <span data-ttu-id="0e908-209">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0e908-209">Select **OK**.</span></span>
1. <span data-ttu-id="0e908-210">Especifique la cantidad del artículo que se cuenta en la matrícula de entidad configurando el campo **Cantidad** a *10*.</span><span class="sxs-lookup"><span data-stu-id="0e908-210">Specify the quantity of the item that is counted on the license plate by setting the **Qty** field to *10*.</span></span>
1. <span data-ttu-id="0e908-211">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0e908-211">Select **OK**.</span></span>

    <span data-ttu-id="0e908-212">La página muestra la ubicación que introdujo.</span><span class="sxs-lookup"><span data-stu-id="0e908-212">The page shows the location that you entered.</span></span> <span data-ttu-id="0e908-213">También muestra el siguiente mensaje: "¿Ubicación completa, agregar nuevo LP o artículo?"</span><span class="sxs-lookup"><span data-stu-id="0e908-213">It also shows the following message: "Location complete, add new LP or Item?"</span></span>

1. <span data-ttu-id="0e908-214">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0e908-214">Select **OK**.</span></span>

<span data-ttu-id="0e908-215">El trabajo se completó.</span><span class="sxs-lookup"><span data-stu-id="0e908-215">Work is now completed.</span></span>

#### <a name="work-details"></a><span data-ttu-id="0e908-216">Detalles del trabajo</span><span class="sxs-lookup"><span data-stu-id="0e908-216">Work details</span></span>

> [!NOTE]
> <span data-ttu-id="0e908-217">Los recuentos puntuales desde la aplicación móvil crean trabajo de recuento cíclico en Microsoft Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="0e908-217">Spot counts from the mobile app create cycle counting work in Microsoft Dynamics 365.</span></span> <span data-ttu-id="0e908-218">El trabajo requiere que se acepten los recuentos antes de contabilizarlos en el inventario.</span><span class="sxs-lookup"><span data-stu-id="0e908-218">The work requires that the counts be accepted before they are posted to inventory.</span></span>

1. <span data-ttu-id="0e908-219">Inicie sesión en Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="0e908-219">Sign in to Dynamics 365 Supply Chain Management.</span></span>
1. <span data-ttu-id="0e908-220">Vaya a **Gestión de almacenes \> Trabajo \> Detalles de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="0e908-220">Go to **Warehouse management \> Work \> Work details**.</span></span>
1. <span data-ttu-id="0e908-221">En la pestaña **Visión general**, busque las líneas que tienen los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="0e908-221">On the **Overview** tab, look for the lines that have the following values:</span></span>

    - <span data-ttu-id="0e908-222">**Tipo de orden de trabajo:** *Recuento cíclico*</span><span class="sxs-lookup"><span data-stu-id="0e908-222">**Work order type:** *Cycle counting*</span></span>
    - <span data-ttu-id="0e908-223">**Almacén**: *61*</span><span class="sxs-lookup"><span data-stu-id="0e908-223">**Warehouse:** *61*</span></span>
    - <span data-ttu-id="0e908-224">**Situación del trabajo:** *Revisión pendiente*</span><span class="sxs-lookup"><span data-stu-id="0e908-224">**Work status:** *Pending review*</span></span>

    <span data-ttu-id="0e908-225">Se deberían haber creado dos identificadores de trabajo para estas líneas.</span><span class="sxs-lookup"><span data-stu-id="0e908-225">Two work IDs should have been created for these lines.</span></span> <span data-ttu-id="0e908-226">Se deben aceptar los recuentos de ambos identificadores de trabajo.</span><span class="sxs-lookup"><span data-stu-id="0e908-226">The counts for both these work IDs must be accepted.</span></span>

1. <span data-ttu-id="0e908-227">En la cuadrícula, seleccione la primera identificación de trabajo para el tipo de orden de trabajo *Recuento cíclico*.</span><span class="sxs-lookup"><span data-stu-id="0e908-227">In the grid, select the first work ID for the *Cycle counting* work order type.</span></span>
1. <span data-ttu-id="0e908-228">En el panel de acciones, en la pestaña **Trabajo**, en el grupo **Trabajo**, seleccione **Recuento cíclico**.</span><span class="sxs-lookup"><span data-stu-id="0e908-228">On the Action Pane, on **Work** tab, in the **Work** group, select **Cycle counting**.</span></span>

    <span data-ttu-id="0e908-229">Se muestran dos líneas, una para cada artículo y matrícula de entidad.</span><span class="sxs-lookup"><span data-stu-id="0e908-229">Two lines are shown, one for each item and license plate.</span></span> <span data-ttu-id="0e908-230">Los valores en los campos **Cantidad contada**, **Ubicación**, **Matrícula de entidad** y **Artículo** deben coincidir con las entradas de recuento que creó en el dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="0e908-230">The values in the **Counted quantity**, **Location**, **License plate**, and **Item** fields should match the count entries that you created on the mobile device.</span></span> <span data-ttu-id="0e908-231">Si alguno de estos campos no está visible, seleccione **Dimensiones de la pantalla** en el Panel de acciones para agregarlos a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="0e908-231">If any of these fields aren't visible, select **Display dimensions** on the Action Pane to add them to the grid.</span></span>

1. <span data-ttu-id="0e908-232">Seleccione ambas líneas.</span><span class="sxs-lookup"><span data-stu-id="0e908-232">Select both lines.</span></span>
1. <span data-ttu-id="0e908-233">En el panel de acciones, seleccione **Aceptar recuento**.</span><span class="sxs-lookup"><span data-stu-id="0e908-233">On the Action Pane, select **Accept count**.</span></span>
1. <span data-ttu-id="0e908-234">Recibirá un mensaje de "Publicación - Diario".</span><span class="sxs-lookup"><span data-stu-id="0e908-234">You receive a "Posting - Journal" message.</span></span> <span data-ttu-id="0e908-235">Seleccione **Detalles del mensaje** para ver el número de diario publicado.</span><span class="sxs-lookup"><span data-stu-id="0e908-235">Select **Message details** to view the posted journal number.</span></span>
1. <span data-ttu-id="0e908-236">Cierre los detalles del mensaje.</span><span class="sxs-lookup"><span data-stu-id="0e908-236">Close the message details.</span></span>
1. <span data-ttu-id="0e908-237">Actualice la página **Trabajo**.</span><span class="sxs-lookup"><span data-stu-id="0e908-237">Refresh the **Work** page.</span></span>

    <span data-ttu-id="0e908-238">La primera identificación de trabajo se ha cerrado y ya no se muestra.</span><span class="sxs-lookup"><span data-stu-id="0e908-238">The first work ID has been closed and is no longer shown.</span></span>

    > [!TIP]
    > <span data-ttu-id="0e908-239">Para ver el trabajo cerrado, seleccione la casilla de verificación **Mostrar cerrado** sobre la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="0e908-239">To view closed work, select the **Show closed** check box above the grid.</span></span>

    <span data-ttu-id="0e908-240">Ahora aceptará el trabajo para la matrícula de entidad en la ubicación *01A01R1S2B*.</span><span class="sxs-lookup"><span data-stu-id="0e908-240">You will now accept the work for the license plate in the *01A01R1S2B* location.</span></span>

1. <span data-ttu-id="0e908-241">En la pestaña **Vista general**, seleccione la segunda identificación de trabajo para el tipo de orden de trabajo *Recuento cíclico*.</span><span class="sxs-lookup"><span data-stu-id="0e908-241">On the **Overview** tab, select the second work ID for the *Cycle counting* work order type.</span></span>
1. <span data-ttu-id="0e908-242">En el panel de acciones, en la pestaña **Trabajo**, en el grupo **Trabajo**, seleccione **Recuento cíclico**.</span><span class="sxs-lookup"><span data-stu-id="0e908-242">On the Action Pane, on **Work** tab, in the **Work** group, select **Cycle counting**.</span></span>

    <span data-ttu-id="0e908-243">Se muestra una línea para el artículo y la matrícula.</span><span class="sxs-lookup"><span data-stu-id="0e908-243">One line is shown, for the item and license plate.</span></span> <span data-ttu-id="0e908-244">Los valores en los campos **Cantidad contada**, **Ubicación**, **Matrícula de entidad** y **Artículo** deben coincidir con las entradas de recuento que creó en el dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="0e908-244">The values in the **Counted quantity**, **Location**, **License plate**, and **Item** fields should match the count entries that you created on the mobile device.</span></span>

1. <span data-ttu-id="0e908-245">Seleccione la línea.</span><span class="sxs-lookup"><span data-stu-id="0e908-245">Select the line.</span></span>
1. <span data-ttu-id="0e908-246">En el panel de acciones, seleccione **Aceptar recuento**.</span><span class="sxs-lookup"><span data-stu-id="0e908-246">On the Action Pane, select **Accept count**.</span></span>
1. <span data-ttu-id="0e908-247">Recibirá un mensaje de "Publicación - Diario".</span><span class="sxs-lookup"><span data-stu-id="0e908-247">You receive a "Posting - Journal" message.</span></span> <span data-ttu-id="0e908-248">Seleccione **Detalles del mensaje** para ver el número de diario publicado.</span><span class="sxs-lookup"><span data-stu-id="0e908-248">Select **Message details** to view the posted journal number.</span></span>
1. <span data-ttu-id="0e908-249">Cierre los detalles del mensaje.</span><span class="sxs-lookup"><span data-stu-id="0e908-249">Close the message details.</span></span>
1. <span data-ttu-id="0e908-250">Actualice la página **Trabajo**.</span><span class="sxs-lookup"><span data-stu-id="0e908-250">Refresh the **Work** page.</span></span>

    <span data-ttu-id="0e908-251">La segunda identificación de trabajo se ha cerrado y ya no se muestra.</span><span class="sxs-lookup"><span data-stu-id="0e908-251">The second work ID has been closed and is no longer shown.</span></span>

    > [!TIP]
    > <span data-ttu-id="0e908-252">Para ver el trabajo cerrado, seleccione la casilla de verificación **Mostrar cerrado** sobre la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="0e908-252">To view closed work, select the **Show closed** check box above the grid.</span></span>

#### <a name="on-hand-by-location"></a><span data-ttu-id="0e908-253">Inventario disponible por ubicación</span><span class="sxs-lookup"><span data-stu-id="0e908-253">On-hand by location</span></span>

1. <span data-ttu-id="0e908-254">Vaya a **Gestión de almacén \> Consultas e informes \> Inventario disponible por ubicación**.</span><span class="sxs-lookup"><span data-stu-id="0e908-254">Go to **Warehouse management \> Inquiries and reports \> On-hand by location**.</span></span>
1. <span data-ttu-id="0e908-255">Establezca los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="0e908-255">Set the following values:</span></span>

    - <span data-ttu-id="0e908-256">**Sitio**: *6*</span><span class="sxs-lookup"><span data-stu-id="0e908-256">**Site:** *6*</span></span>
    - <span data-ttu-id="0e908-257">**Almacén**: *61*</span><span class="sxs-lookup"><span data-stu-id="0e908-257">**Warehouse:** *61*</span></span>
    - <span data-ttu-id="0e908-258">**Actualizar entre ubicaciones:** *Sí*</span><span class="sxs-lookup"><span data-stu-id="0e908-258">**Refresh across locations:** *Yes*</span></span>

1. <span data-ttu-id="0e908-259">Tenga en cuenta que la ubicación *01A01R1S1B* tiene dos matrículas de entidad:</span><span class="sxs-lookup"><span data-stu-id="0e908-259">Notice that location *01A01R1S1B* has two license plates:</span></span>

    - <span data-ttu-id="0e908-260">**A0001**, donde el campo **Posición LP** se establece en *1*</span><span class="sxs-lookup"><span data-stu-id="0e908-260">**A0001**, where the **LP Position** field is set to *1*</span></span>
    - <span data-ttu-id="0e908-261">**A0002**, donde el campo **Posición LP** se establece en *2*</span><span class="sxs-lookup"><span data-stu-id="0e908-261">**A0002**, where the **LP Position** field is set to *2*</span></span>

1. <span data-ttu-id="0e908-262">Tenga en cuenta que la ubicación *01A01R1S2B* tiene una matrícula de entidad:</span><span class="sxs-lookup"><span data-stu-id="0e908-262">Notice that location *01A01R1S2B* has one license plate:</span></span>

    - <span data-ttu-id="0e908-263">**A0002**, donde el campo **Posición LP** se establece en *1*</span><span class="sxs-lookup"><span data-stu-id="0e908-263">**A0002**, where the **LP Position** field is set to *1*</span></span>

### <a name="sales-order-scenario"></a><span data-ttu-id="0e908-264">Escenario de pedidos de ventas</span><span class="sxs-lookup"><span data-stu-id="0e908-264">Sales order scenario</span></span>

<span data-ttu-id="0e908-265">Ahora que la función *Posicionamiento de ubicación de matrícula de entidad* se ha configurado y se ha organizado el inventario, debe crear un pedido de ventas para generar el trabajo de selección que indicará al trabajador del almacén que elija el artículo *A0002* desde la ubicación del inventario donde se encuentra la identificación del pallet *1*.</span><span class="sxs-lookup"><span data-stu-id="0e908-265">Now that the *Location license plate positioning* feature has been set up, and the inventory has been staged, you must create a sales order to generate picking work that will direct the warehouse worker to pick item *A0002* from the inventory location where the pallet ID is in position *1*.</span></span>

1. <span data-ttu-id="0e908-266">Vaya a **Ventas y marketing \> Pedidos de ventas \> Todos los pedidos de ventas**.</span><span class="sxs-lookup"><span data-stu-id="0e908-266">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="0e908-267">En el panel de acciones, haga clic en **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="0e908-267">On the Action Pane, select **New**.</span></span>
1. <span data-ttu-id="0e908-268">En el cuadro de diálogo **Crear pedido de ventas**, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="0e908-268">In the **Create sales order** dialog box, set the following values:</span></span>

    - <span data-ttu-id="0e908-269">**Cuenta de cliente:** *US-004*</span><span class="sxs-lookup"><span data-stu-id="0e908-269">**Customer account:** *US-004*</span></span>
    - <span data-ttu-id="0e908-270">**Almacén**: *61*</span><span class="sxs-lookup"><span data-stu-id="0e908-270">**Warehouse:** *61*</span></span>

1. <span data-ttu-id="0e908-271">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0e908-271">Select **OK**.</span></span>
1. <span data-ttu-id="0e908-272">Se agrega una nueva línea a cuadrícula en la ficha desplegable **Líneas de pedido de ventas**.</span><span class="sxs-lookup"><span data-stu-id="0e908-272">A new line is added to the grid on the **Sales order lines** FastTab.</span></span> <span data-ttu-id="0e908-273">En esta nueva línea, establezca los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="0e908-273">On this new line, set the following values:</span></span>

    - <span data-ttu-id="0e908-274">**Código de artículo:** *A0002*</span><span class="sxs-lookup"><span data-stu-id="0e908-274">**Item number:** *A0002*</span></span>
    - <span data-ttu-id="0e908-275">**Cantidad:** *1*</span><span class="sxs-lookup"><span data-stu-id="0e908-275">**Quantity:** *1*</span></span>

1. <span data-ttu-id="0e908-276">En el menú **Inventario** sobre la cuadrícula, seleccione **Reserva**.</span><span class="sxs-lookup"><span data-stu-id="0e908-276">On the **Inventory** menu above the grid, select **Reservation**.</span></span>
1. <span data-ttu-id="0e908-277">En la página **Reserva**, en el Panel de acciones, seleccione **Reservar lote** para reservar inventario para la línea de pedido.</span><span class="sxs-lookup"><span data-stu-id="0e908-277">On the **Reservation** page, on the Action Pane, select **Reserve lot** to reserve inventory for the order line.</span></span>
1. <span data-ttu-id="0e908-278">Cierre la página **Reserva**.</span><span class="sxs-lookup"><span data-stu-id="0e908-278">Close the **Reservation** page.</span></span>
1. <span data-ttu-id="0e908-279">En el panel de acciones, en la pestaña **Almacén**, en el grupo **Acciones**, seleccione **Liberar al almacén**.</span><span class="sxs-lookup"><span data-stu-id="0e908-279">On the Action Pane, on the **Warehouse** tab, in the **Actions** group, select **Release to warehouse**.</span></span>

    <span data-ttu-id="0e908-280">Recibirá un mensaje informativo que indican el trabajo, la identificación de oleada y el identificador de envío que se crean para el pedido.</span><span class="sxs-lookup"><span data-stu-id="0e908-280">You receive an informational message that indicates the wave ID and shipment ID that were created for the order.</span></span>

1. <span data-ttu-id="0e908-281">En la ficha desplegable **Líneas de pedido de ventas**, en el menú **Almacén**, sobre la cuadrícula, seleccione **Detalles del trabajo**.</span><span class="sxs-lookup"><span data-stu-id="0e908-281">On the **Sales order lines** FastTab, on the **Warehouse** menu above the grid, select **Work details**.</span></span>
1. <span data-ttu-id="0e908-282">Aparecerá la página **Trabajo** y muestra el trabajo que se creó para la línea de ventas.</span><span class="sxs-lookup"><span data-stu-id="0e908-282">The **Work** page appears and shows the work that was created for the sales line.</span></span> <span data-ttu-id="0e908-283">Anote el identificador de trabajo que se muestra.</span><span class="sxs-lookup"><span data-stu-id="0e908-283">Make a note of the work ID that is shown.</span></span>

### <a name="sales-picking-scenario"></a><span data-ttu-id="0e908-284">Escenario de selección de ventas</span><span class="sxs-lookup"><span data-stu-id="0e908-284">Sales picking scenario</span></span>

1. <span data-ttu-id="0e908-285">Abra la aplicación móvil e inicie sesión en el almacén *61*.</span><span class="sxs-lookup"><span data-stu-id="0e908-285">Open the mobile app, and sign in to warehouse *61*.</span></span>
1. <span data-ttu-id="0e908-286">Vaya a **Saliente \> Selección de ventas**.</span><span class="sxs-lookup"><span data-stu-id="0e908-286">Go to **Outbound \> Sales picking**.</span></span>
1. <span data-ttu-id="0e908-287">En la página **Escanear una identificación de trabajo / identificación de matrícula de entidad**, seleccione el campo **Identificación** y luego introduzca la identificación de trabajo desde la línea de ventas.</span><span class="sxs-lookup"><span data-stu-id="0e908-287">On the **Scan a work ID / license plate ID** page, select the **ID** field, and then enter the work ID from the sales line.</span></span>
1. <span data-ttu-id="0e908-288">Tenga en cuenta que el trabajo de selección lo dirige a elegir el artículo *A0002* desde la ubicación *01A01R1S2B*.</span><span class="sxs-lookup"><span data-stu-id="0e908-288">Notice that the picking work directs you to pick item *A0002* from location *01A01R1S2B*.</span></span> <span data-ttu-id="0e908-289">Recibe esta instrucción porque el artículo *A0002* está en una matrícula de entidad que está en la posición *1* en esa ubicación.</span><span class="sxs-lookup"><span data-stu-id="0e908-289">You receive this instruction because item *A0002* is on a license plate that is in position *1* in that location.</span></span>

    <span data-ttu-id="0e908-290">![Ubicación de la posición 1](media/LocationLicensePlatePositioning.png "Ubicación de la posición 1")</span><span class="sxs-lookup"><span data-stu-id="0e908-290">![Position 1 location](media/LocationLicensePlatePositioning.png "Position 1 location")</span></span>

1. <span data-ttu-id="0e908-291">Introduzca la identificación de la matrícula de entidad que creó para la ubicación y luego siga las indicaciones para elegir el pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="0e908-291">Enter the license plate ID that you created for the location, and then follow the prompts to pick the sales order.</span></span>
