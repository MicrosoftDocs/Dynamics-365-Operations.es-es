---
title: Solución de problemas de configuración de almacén
description: Este tema describe cómo solucionar problemas comunes que pueden surgir al configurar Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
manager: tfehr
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 1fe285f05e5f1ddcb7bd206290b9954cbdaffc75
ms.sourcegitcommit: 105f65468b45799761c26e5d0ad9df4ff162c38d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "5487106"
---
# <a name="troubleshoot-warehouse-configuration"></a><span data-ttu-id="42ac6-103">Solución de problemas de configuración de almacén</span><span class="sxs-lookup"><span data-stu-id="42ac6-103">Troubleshoot warehouse configuration</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="42ac6-104">Este tema describe cómo solucionar problemas comunes que pueden surgir al configurar Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="42ac6-104">This topic describes how to fix common issues that you might encounter while you configure Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="i-receive-the-following-error-message-the-license-plate-or-location-is-not-valid"></a><span data-ttu-id="42ac6-105">Recibo el siguiente mensaje de error: "La matrícula o la ubicación no es válida".</span><span class="sxs-lookup"><span data-stu-id="42ac6-105">I receive the following error message: "The license plate or location is not valid."</span></span>

### <a name="issue-description"></a><span data-ttu-id="42ac6-106">Descripción del problema</span><span class="sxs-lookup"><span data-stu-id="42ac6-106">Issue description</span></span>

<span data-ttu-id="42ac6-107">Recibe este mensaje de error cuando escanea la identificación o ubicación de una placa de matrícula.</span><span class="sxs-lookup"><span data-stu-id="42ac6-107">You receive this error message when you scan a license plate ID or location.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="42ac6-108">Solución del problema</span><span class="sxs-lookup"><span data-stu-id="42ac6-108">Issue resolution</span></span>

<span data-ttu-id="42ac6-109">Asegúrese de que la identificación de la matrícula no esté reservada por otra persona.</span><span class="sxs-lookup"><span data-stu-id="42ac6-109">Make sure that the license plate ID isn't reserved by something else.</span></span> <span data-ttu-id="42ac6-110">Este problema solía ocurrir cuando el valor que un usuario escaneaba en la aplicación del almacén era tanto una ubicación válida como una identificación de matrícula válida.</span><span class="sxs-lookup"><span data-stu-id="42ac6-110">This issue used to occur when the value that a user scanned in the warehouse app was both a valid location and a valid license plate ID.</span></span> <span data-ttu-id="42ac6-111">Sin embargo, este problema se resolvió en la versión 10.0.11.</span><span class="sxs-lookup"><span data-stu-id="42ac6-111">However, this issue was resolved in version 10.0.11.</span></span>

## <a name="i-receive-the-following-error-message-license-plate-must-be-specified-for-this-location"></a><span data-ttu-id="42ac6-112">Recibo el siguiente mensaje de error: "La matrícula se debe especificar para esta ubicación".</span><span class="sxs-lookup"><span data-stu-id="42ac6-112">I receive the following error message: "License plate must be specified for this location."</span></span>

### <a name="issue-description"></a><span data-ttu-id="42ac6-113">Descripción del problema</span><span class="sxs-lookup"><span data-stu-id="42ac6-113">Issue description</span></span>

<span data-ttu-id="42ac6-114">Recibirá este mensaje de error si crea una orden de transferencia utilizando un almacén que está habilitado para la administración avanzada de almacenes (WMS) y, luego, una vez completado el trabajo, intenta confirmar el envío.</span><span class="sxs-lookup"><span data-stu-id="42ac6-114">You receive this error message if you create a transfer order by using a warehouse that is enabled for advanced warehouse management (WMS), and then, after the work is completed, you try to confirm the shipment.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="42ac6-115">Solución del problema</span><span class="sxs-lookup"><span data-stu-id="42ac6-115">Issue resolution</span></span>

<span data-ttu-id="42ac6-116">El campo **Ubicación de recibo predeterminada** está en blanco para un almacén de tránsito del almacén "desde".</span><span class="sxs-lookup"><span data-stu-id="42ac6-116">The **Default receipt location** field is blank for a transit warehouse of the "from" warehouse.</span></span> <span data-ttu-id="42ac6-117">Para solucionar este problema, especifique una ubicación de recepción predeterminada en el almacén de tránsito.</span><span class="sxs-lookup"><span data-stu-id="42ac6-117">To fix this issue, specify a default receipt location in the transit warehouse.</span></span> <span data-ttu-id="42ac6-118">Asegúrese de que esta ubicación esté controlada por matrículas.</span><span class="sxs-lookup"><span data-stu-id="42ac6-118">Make sure that this location is license plate–controlled.</span></span>

## <a name="i-receive-the-following-error-message-you-cant-create-a-work-template-line-for-inventory-status-change-because-the-work-type-is-not-valid-select-a-different-work-type"></a><span data-ttu-id="42ac6-119">Recibo el siguiente mensaje de error: "No puede crear una línea de plantilla de trabajo para el cambio de estado de inventario porque el tipo de trabajo no es válido.</span><span class="sxs-lookup"><span data-stu-id="42ac6-119">I receive the following error message: "You can't create a work template line for Inventory status change because the work type is not valid.</span></span> <span data-ttu-id="42ac6-120">Seleccione un tipo de trabajo diferente ".</span><span class="sxs-lookup"><span data-stu-id="42ac6-120">Select a different work type."</span></span>

### <a name="issue-description"></a><span data-ttu-id="42ac6-121">Descripción del problema</span><span class="sxs-lookup"><span data-stu-id="42ac6-121">Issue description</span></span>

<span data-ttu-id="42ac6-122">Para una plantilla de trabajo, no puede seleccionar *Cambio de estado de inventario* en la columna **Tipo de trabajo** columna de la sección **Detalles de la plantilla de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="42ac6-122">For a work template, you can't select *Inventory status change* in the **Work type** column of the **Work template details** section.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="42ac6-123">Solución del problema</span><span class="sxs-lookup"><span data-stu-id="42ac6-123">Issue resolution</span></span>

<span data-ttu-id="42ac6-124">Este comportamiento se debe al diseño.</span><span class="sxs-lookup"><span data-stu-id="42ac6-124">This behavior is by design.</span></span> <span data-ttu-id="42ac6-125">El tipo de trabajo *Cambio de estado de inventario* solo lo utilizan los procesos del sistema.</span><span class="sxs-lookup"><span data-stu-id="42ac6-125">The *Inventory status change* work type is used only by system processes.</span></span> <span data-ttu-id="42ac6-126">No se puede configurar.</span><span class="sxs-lookup"><span data-stu-id="42ac6-126">It can't be configured.</span></span> <span data-ttu-id="42ac6-127">Debido a que la lista de tipos de trabajo se fija como una enumeración, las entradas adicionales no se pueden filtrar del menú desplegable **Tipo de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="42ac6-127">Because the list of work types is fixed as an enumeration, the extra entries can't be filtered out of the **Work type** drop-down menu.</span></span>

## <a name="i-receive-the-following-error-message-the-quantity-is-not-valid-for-unit-1"></a><span data-ttu-id="42ac6-128">Recibo el siguiente mensaje de error: "La cantidad no es válida para la unidad 1%".</span><span class="sxs-lookup"><span data-stu-id="42ac6-128">I receive the following error message: "The Quantity is not valid for unit 1%."</span></span>

### <a name="issue-description"></a><span data-ttu-id="42ac6-129">Descripción del problema</span><span class="sxs-lookup"><span data-stu-id="42ac6-129">Issue description</span></span>

<span data-ttu-id="42ac6-130">La cantidad no es válida para la unidad *ea* cuando hay trabajo de recolección que tiene varias placas en un solo lugar.</span><span class="sxs-lookup"><span data-stu-id="42ac6-130">The quantity isn't valid for the *ea* unit when there is picking work that has multiple license plates in one location.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="42ac6-131">Solución del problema</span><span class="sxs-lookup"><span data-stu-id="42ac6-131">Issue resolution</span></span>

<span data-ttu-id="42ac6-132">Verifique que los campos **ID de grupo de secuencia de unidad** y **Conversiones de unidades** del producto lanzado o la variante del producto están configurados correctamente.</span><span class="sxs-lookup"><span data-stu-id="42ac6-132">Verify that the **Unit sequence group ID** and **Unit conversions** fields on the released product or product variant are set correctly.</span></span>

<span data-ttu-id="42ac6-133">Tenga en cuenta que el mensaje de error se ha mejorado en la versión 10.0.15 (consulte [KB 4581627](https://fix.lcs.dynamics.com/Issue/Details/?bugId=486531)).</span><span class="sxs-lookup"><span data-stu-id="42ac6-133">Note that the error message has been improved in version 10.0.15 (see [KB 4581627](https://fix.lcs.dynamics.com/Issue/Details/?bugId=486531)).</span></span> <span data-ttu-id="42ac6-134">El nuevo mensaje de error es "La cantidad no es válida.</span><span class="sxs-lookup"><span data-stu-id="42ac6-134">The new error message is, "The quantity is not valid.</span></span> <span data-ttu-id="42ac6-135">Se esperaba %1 %2."</span><span class="sxs-lookup"><span data-stu-id="42ac6-135">Expected %1 %2."</span></span>

## <a name="in-location-directives-for-sales-order-put-work-the-multiple-sku-option-doesnt-evaluate-multiple-location-directive-actions"></a><span data-ttu-id="42ac6-136">En las directivas de ubicación para el trabajo de colocación de pedidos de ventas, la opción de SKU múltiple no evalúa múltiples acciones de directiva de ubicación.</span><span class="sxs-lookup"><span data-stu-id="42ac6-136">In location directives for sales order put work, the multiple SKU option doesn't evaluate multiple location directive actions.</span></span>

### <a name="issue-description"></a><span data-ttu-id="42ac6-137">Descripción del problema</span><span class="sxs-lookup"><span data-stu-id="42ac6-137">Issue description</span></span>

<span data-ttu-id="42ac6-138">Las directivas de ubicación del tipo de orden de trabajo *Ordenes de venta* y del tipo de trabajo *Ubicación* no evalúan múltiples acciones de directiva de ubicación cuando está seleccionada la opción **Varios SKU** .</span><span class="sxs-lookup"><span data-stu-id="42ac6-138">Location directives of the *Sales orders* work order type and the *Put* work type don't evaluate multiple location directive actions when the **Multiple SKU** option is selected.</span></span> <span data-ttu-id="42ac6-139">Solo se evalúa la primera acción directiva de ubicación.</span><span class="sxs-lookup"><span data-stu-id="42ac6-139">Only the first location directive action is evaluated.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="42ac6-140">Solución del problema</span><span class="sxs-lookup"><span data-stu-id="42ac6-140">Issue resolution</span></span>

<span data-ttu-id="42ac6-141">Una nueva característica, *Evaluar todas las acciones para las directivas de ubicación de múltiples SKU*, se ha agregado en la versión 10.0.15 (ver [KB 4579866](https://fix.lcs.dynamics.com/Issue/Details?kb=4579866&bugId=475946&dbType=3&qc=1bc41a56de7a3ee419fa76397a6bf282fce5be9b93e427c08a6d916d1dfa3091)).</span><span class="sxs-lookup"><span data-stu-id="42ac6-141">A new feature, *Evaluate all actions for Multi SKU location directives*, has been added in version 10.0.15 (see [KB 4579866](https://fix.lcs.dynamics.com/Issue/Details?kb=4579866&bugId=475946&dbType=3&qc=1bc41a56de7a3ee419fa76397a6bf282fce5be9b93e427c08a6d916d1dfa3091)).</span></span> <span data-ttu-id="42ac6-142">Esta función evalúa todas las acciones para las directivas de ubicación de varios SKU.</span><span class="sxs-lookup"><span data-stu-id="42ac6-142">This feature evaluates all actions for multi-SKU location directives.</span></span> <span data-ttu-id="42ac6-143">Si necesita esta función, utilice [Gestión de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para activarla.</span><span class="sxs-lookup"><span data-stu-id="42ac6-143">If you require this feature, use [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) to turn it on.</span></span>

## <a name="i-cant-use-the-warehouse-app-to-do-partial-picking"></a><span data-ttu-id="42ac6-144">No puedo usar la aplicación del almacén para hacer picking parcial.</span><span class="sxs-lookup"><span data-stu-id="42ac6-144">I can't use the warehouse app to do partial picking.</span></span>

### <a name="issue-description"></a><span data-ttu-id="42ac6-145">Descripción del problema</span><span class="sxs-lookup"><span data-stu-id="42ac6-145">Issue description</span></span>

<span data-ttu-id="42ac6-146">Para las órdenes de venta y transferencia, no puede omitir artículos y realizar un picking parcial.</span><span class="sxs-lookup"><span data-stu-id="42ac6-146">For sales and transfer orders, you can't skip items and do partial picking.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="42ac6-147">Solución del problema</span><span class="sxs-lookup"><span data-stu-id="42ac6-147">Issue resolution</span></span>

<span data-ttu-id="42ac6-148">En la página **Elementos del menú del dispositivo móvil**, para cada elemento del menú que está configurado para procesar órdenes de venta o órdenes de transferencia, establezca la opción **Permitir la división del trabajo** en la ficha desplegable **General** en *Sí*.</span><span class="sxs-lookup"><span data-stu-id="42ac6-148">On the **Mobile device menu items** page, for each menu item that is set up to process sales orders or transfer orders, set the **Allow splitting of work** option on the **General** FastTab to *Yes*.</span></span>

## <a name="how-can-i-do-an-inventory-status-change-for-partial-quantity-work"></a><span data-ttu-id="42ac6-149">¿Cómo puedo hacer un cambio de estado de inventario para trabajo de cantidad parcial?</span><span class="sxs-lookup"><span data-stu-id="42ac6-149">How can I do an inventory status change for partial quantity work?</span></span>

### <a name="issue-description"></a><span data-ttu-id="42ac6-150">Descripción del problema</span><span class="sxs-lookup"><span data-stu-id="42ac6-150">Issue description</span></span>

<span data-ttu-id="42ac6-151">Desea realizar un cambio de estado de inventario para una cantidad parcial de un lote.</span><span class="sxs-lookup"><span data-stu-id="42ac6-151">You want to do an inventory status change for a partial quantity of a batch.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="42ac6-152">Solución del problema</span><span class="sxs-lookup"><span data-stu-id="42ac6-152">Issue resolution</span></span>

<span data-ttu-id="42ac6-153">Para permitir que los trabajadores realicen este cambio, puede crear un elemento de menú para la aplicación del almacén.</span><span class="sxs-lookup"><span data-stu-id="42ac6-153">To enable workers to make this change, you can create a menu item for the warehouse app.</span></span> <span data-ttu-id="42ac6-154">En la página **Elementos de menú del dispositivo móvil**, cree (o edite) un elemento de menú con la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="42ac6-154">On the **Mobile device menu items** page, create (or edit) a menu item that has the following settings:</span></span>

- <span data-ttu-id="42ac6-155">**Modo:** *Trabajo*</span><span class="sxs-lookup"><span data-stu-id="42ac6-155">**Mode:** *Work*</span></span>
- <span data-ttu-id="42ac6-156">**Usar trabajo existente:** *No*</span><span class="sxs-lookup"><span data-stu-id="42ac6-156">**Use existing work:** *No*</span></span>
- <span data-ttu-id="42ac6-157">**Proceso de creación de trabajo:** *Movimiento*</span><span class="sxs-lookup"><span data-stu-id="42ac6-157">**Work creation process:** *Movement*</span></span>
- <span data-ttu-id="42ac6-158">**Mostrar estado de inventario**: *Sí*</span><span class="sxs-lookup"><span data-stu-id="42ac6-158">**Display inventory status:** *Yes*</span></span>

<span data-ttu-id="42ac6-159">Puede configurar otros campos en la página según sus necesidades.</span><span class="sxs-lookup"><span data-stu-id="42ac6-159">You can set other fields on the page as you require.</span></span>

## <a name="the-dock-management-profile-of-a-location-profile-is-not-preventing-inventory-types-from-being-mixed"></a><span data-ttu-id="42ac6-160">El perfil de gestión de muelle de un perfil de ubicación no impide que se mezclen los tipos de inventario.</span><span class="sxs-lookup"><span data-stu-id="42ac6-160">The dock management profile of a location profile is not preventing inventory types from being mixed.</span></span>

### <a name="issue-description"></a><span data-ttu-id="42ac6-161">Descripción del problema</span><span class="sxs-lookup"><span data-stu-id="42ac6-161">Issue description</span></span>

<span data-ttu-id="42ac6-162">Está usando *directivas de consolidación de envíos*.</span><span class="sxs-lookup"><span data-stu-id="42ac6-162">You are using *shipment consolidation policies*.</span></span> <span data-ttu-id="42ac6-163">Ha configurado un *perfil de gestión del muelle* para *perfil de ubicación*, pero cuando se crea el trabajo, los tipos de inventario se mezclan en la ubicación final.</span><span class="sxs-lookup"><span data-stu-id="42ac6-163">You have set up a *dock management profile* for a *location profile*, but when work is created, the inventory types are mixed at the final location.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="42ac6-164">Solución del problema</span><span class="sxs-lookup"><span data-stu-id="42ac6-164">Issue resolution</span></span>

<span data-ttu-id="42ac6-165">Los perfiles de gestión de muelles requieren que el trabajo se divida por adelantado.</span><span class="sxs-lookup"><span data-stu-id="42ac6-165">Dock management profiles require work to be split up front.</span></span> <span data-ttu-id="42ac6-166">En otras palabras, el perfil de administración del muelle espera que un encabezado de trabajo no tenga múltiples ubicaciones de colocación.</span><span class="sxs-lookup"><span data-stu-id="42ac6-166">In other words, the dock management profile expects that a work header won't have multiple put locations.</span></span>

<span data-ttu-id="42ac6-167">Para que el perfil de administración del muelle administre de manera efectiva la mezcla de inventario, se debe configurar una pausa en el encabezado de trabajo.</span><span class="sxs-lookup"><span data-stu-id="42ac6-167">For the dock management profile to effectively manage the mixing of inventory, a work header break must be set up.</span></span>

<span data-ttu-id="42ac6-168">En este ejemplo, nuestro perfil de gestión de muelles está configurado de manera que **Tipos de inventario que no deben mezclarse** se establece en *Identificación del envío*, y configuraremos un descanso de encabezado de trabajo para ello:</span><span class="sxs-lookup"><span data-stu-id="42ac6-168">In this example our dock management profile is configured such that **Inventory types that should not be mixed** is set to *Shipment ID*, and we'll set up a work header break for it:</span></span>

1. <span data-ttu-id="42ac6-169">Vaya a **Administración de almacenes \> Configuración \> Trabajo \> Plantillas de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="42ac6-169">Go to **Warehouse management \> Setup \> Work \> Work templates**.</span></span>
1. <span data-ttu-id="42ac6-170">Seleccione el **Tipo de orden de trabajo** para editar (por ejemplo, *Ordenes de compra*).</span><span class="sxs-lookup"><span data-stu-id="42ac6-170">Select the **Work order type** to edit (for example, *Purchase orders*).</span></span>
1. <span data-ttu-id="42ac6-171">Seleccione la plantilla de trabajo para editar.</span><span class="sxs-lookup"><span data-stu-id="42ac6-171">Select the work template to edit.</span></span>
1. <span data-ttu-id="42ac6-172">En el panel Acciones, seleccione **Editar consulta**.</span><span class="sxs-lookup"><span data-stu-id="42ac6-172">On the Action Pane, select **Edit query**.</span></span>
1. <span data-ttu-id="42ac6-173">Abra la pestaña **Clasificación** y agregue una fila con la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="42ac6-173">Open the **Sorting** tab and add a row with the following settings:</span></span>
    - <span data-ttu-id="42ac6-174">**Tabla** - *Transacciones laborales temporales*</span><span class="sxs-lookup"><span data-stu-id="42ac6-174">**Table** - *Temporary work transactions*</span></span>
    - <span data-ttu-id="42ac6-175">**Tabla derivada** - *Transacciones laborales temporales*</span><span class="sxs-lookup"><span data-stu-id="42ac6-175">**Derived table** - *Temporary work transactions*</span></span>
    - <span data-ttu-id="42ac6-176">**Campo** - *Identificación del envío*</span><span class="sxs-lookup"><span data-stu-id="42ac6-176">**Field** - *Shipment ID*</span></span>
1. <span data-ttu-id="42ac6-177">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="42ac6-177">Select **OK**.</span></span>
1. <span data-ttu-id="42ac6-178">Regresa a la página **Plantillas de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="42ac6-178">You return to the **Work templates** page.</span></span> <span data-ttu-id="42ac6-179">En el panel de acciones, seleccione **Saltos de encabezado de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="42ac6-179">On the Action Pane, select **Work header breaks**.</span></span>
1. <span data-ttu-id="42ac6-180">En el panel Acciones, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="42ac6-180">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="42ac6-181">Seleccione la casilla de verificación asociada con el **Nombre del campo** *Identificación del envío*.</span><span class="sxs-lookup"><span data-stu-id="42ac6-181">Select the check box associated with the **Field name** *Shipment ID*.</span></span>
1. <span data-ttu-id="42ac6-182">En el panel Acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="42ac6-182">On the Action Pane, select **Save**.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
