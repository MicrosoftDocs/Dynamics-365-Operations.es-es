---
title: Configurar un almacén
description: En este tema se describe cómo configurar un almacén para utilizarlo con un nuevo canal en Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: fe785e3bfd503193a588958ae5df0d1c0fdb9e52
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/01/2020
ms.locfileid: "3002321"
---
# <a name="warehouse-set-up"></a><span data-ttu-id="6e52d-103">Configuración de almacén</span><span class="sxs-lookup"><span data-stu-id="6e52d-103">Warehouse set up</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="6e52d-104">En este tema se describe cómo configurar un almacén para utilizarlo con un nuevo canal en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="6e52d-104">This topic describes how to set up a warehouse to be used with a new channel in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="6e52d-105">Visión general</span><span class="sxs-lookup"><span data-stu-id="6e52d-105">Overview</span></span>

<span data-ttu-id="6e52d-106">Cada canal de Commerce requiere que se le asocie un almacén configurado.</span><span class="sxs-lookup"><span data-stu-id="6e52d-106">Each Commerce channel requires a configured warehouse to be associated with it.</span></span> <span data-ttu-id="6e52d-107">Los siguientes procedimientos proporcionan la configuración mínima requerida para configurar un almacén para un canal de Commerce.</span><span class="sxs-lookup"><span data-stu-id="6e52d-107">The following procedures provide the minimum configuration required to set up a warehouse for a Commerce channel.</span></span> <span data-ttu-id="6e52d-108">Para obtener más información sobre la configuración del almacén, consulte la [Visión general de la gestión de almacenes](https://docs.microsoft.com/en-us/dynamics365/supply-chain/warehousing/warehouse-management-overview).</span><span class="sxs-lookup"><span data-stu-id="6e52d-108">For more information regarding warehouse setup, please see the [Warehouse management overview](https://docs.microsoft.com/en-us/dynamics365/supply-chain/warehousing/warehouse-management-overview).</span></span>

## <a name="configure-a-warehouse-site"></a><span data-ttu-id="6e52d-109">Configurar un sitio de almacén</span><span class="sxs-lookup"><span data-stu-id="6e52d-109">Configure a warehouse site</span></span>

<span data-ttu-id="6e52d-110">Antes de configurar un almacén, debe configurar un sitio de almacén.</span><span class="sxs-lookup"><span data-stu-id="6e52d-110">Before setting up a warehouse, you need to configure a warehouse site.</span></span>

<span data-ttu-id="6e52d-111">Para configurar un sitio de almacén, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="6e52d-111">To configure a warehouse site, follow these steps.</span></span>

1. <span data-ttu-id="6e52d-112">En el panel de navegación, vaya a **Módulos \> Retail y Commerce \> Configuración de canal \> Sitios**.</span><span class="sxs-lookup"><span data-stu-id="6e52d-112">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Sites**.</span></span>
1. <span data-ttu-id="6e52d-113">En el panel de acciones, seleccione **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="6e52d-113">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="6e52d-114">En el campo **Sitio**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="6e52d-114">In the **Site** field, enter a value.</span></span>
1. <span data-ttu-id="6e52d-115">En el campo **Nombre**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="6e52d-115">In the **Name** field, enter a value.</span></span>
1. <span data-ttu-id="6e52d-116">En la sección **General**, establezca la **Zona horaria** apropiada.</span><span class="sxs-lookup"><span data-stu-id="6e52d-116">In the **General** section, set the appropriate **Time zone**.</span></span>
1. <span data-ttu-id="6e52d-117">En la sección **Direcciones**, escriba una dirección.</span><span class="sxs-lookup"><span data-stu-id="6e52d-117">In the **Addresses** section, enter an address.</span></span>
1. <span data-ttu-id="6e52d-118">En el panel de acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="6e52d-118">On the action pane, select **Save**.</span></span>

<span data-ttu-id="6e52d-119">La siguiente imagen muestra un ejemplo de sitio de almacén.</span><span class="sxs-lookup"><span data-stu-id="6e52d-119">The following image shows an example warehouse site.</span></span>

![Ejemplo de sitio de almacén](media/warehouse-site.png)

## <a name="set-up-a-warehouse"></a><span data-ttu-id="6e52d-121">Configurar un almacén</span><span class="sxs-lookup"><span data-stu-id="6e52d-121">Set up a warehouse</span></span>

<span data-ttu-id="6e52d-122">Para configurar un almacén, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="6e52d-122">To set up a warehouse, follow these steps.</span></span>

1. <span data-ttu-id="6e52d-123">En el panel de navegación, vaya a **Módulos \> Retail y Commerce \> Configuración de canal \> Almacenes**.</span><span class="sxs-lookup"><span data-stu-id="6e52d-123">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Warehouses**.</span></span>
1. <span data-ttu-id="6e52d-124">En el panel de acciones, seleccione **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="6e52d-124">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="6e52d-125">En el campo **Almacén**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="6e52d-125">In the **Warehouse** field, enter a value.</span></span>  <span data-ttu-id="6e52d-126">Si se trata de una asignación 1:1 a una tienda, considere la posibilidad de usar el nombre de la tienda o el nombre de un centro de distribución regional.</span><span class="sxs-lookup"><span data-stu-id="6e52d-126">If this is a 1:1 mapping to a retail store, consider using the store name or the name of a regional distribution center.</span></span>
1. <span data-ttu-id="6e52d-127">En el campo **Nombre**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="6e52d-127">In the **Name** field, enter a value.</span></span>
1. <span data-ttu-id="6e52d-128">En la lista desplegable **Sitio**, seleccione el sitio de almacén creado previamente.</span><span class="sxs-lookup"><span data-stu-id="6e52d-128">In the **Site** drop-down list, select the warehouse site created previously.</span></span>
1. <span data-ttu-id="6e52d-129">En el campo **Tipo**, seleccione **Predeterminado**.</span><span class="sxs-lookup"><span data-stu-id="6e52d-129">In the **Type** field, select **Default**.</span></span>
    - <span data-ttu-id="6e52d-130">Si desea establecer un **Almacén de cuarentena**, primero deberá seguir estos pasos para crear un almacén adicional donde se establezca **Tipo** en **Cuarentena**.</span><span class="sxs-lookup"><span data-stu-id="6e52d-130">If you want to set a **Quarantine warehouse**, first you'll need to follow these steps to create an additional warehouse where the **Type** is set to **Quarantine**.</span></span>
    - <span data-ttu-id="6e52d-131">Si desea establecer un **Almacén de tránsito**, primero debe seguir estos pasos para crear un almacén adicional donde se establezca **Tipo** en **Tránsito**.</span><span class="sxs-lookup"><span data-stu-id="6e52d-131">If you want to set a **Transit warehouse**, first you'll need to follow these steps to create an additional warehouse where the **Type** is set to **Transit**.</span></span>
1. <span data-ttu-id="6e52d-132">En el panel de acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="6e52d-132">On the action pane, select **Save**.</span></span>

## <a name="set-up-inventory-aisles"></a><span data-ttu-id="6e52d-133">Configurar pasillos de inventario</span><span class="sxs-lookup"><span data-stu-id="6e52d-133">Set up inventory aisles</span></span>

<span data-ttu-id="6e52d-134">Para configurar pasillos de inventario, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="6e52d-134">To set up inventory aisles, follow these steps.</span></span>

1. <span data-ttu-id="6e52d-135">En el panel de navegación, vaya a **Módulos \> Retail y Commerce \> Configuración de canal \> Configuración de la ubicación \> Pasillos de inventario**.</span><span class="sxs-lookup"><span data-stu-id="6e52d-135">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Location setup \> Inventory aisles**.</span></span>
1. <span data-ttu-id="6e52d-136">En el panel de acciones, seleccione **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="6e52d-136">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="6e52d-137">En la lista desplegable **Almacén**, seleccione el almacén creado previamente.</span><span class="sxs-lookup"><span data-stu-id="6e52d-137">In the **Warehouse** drop-down list, select the warehouse created previously.</span></span>
1. <span data-ttu-id="6e52d-138">En el campo **Pasillo**, especifique un nombre (por ejemplo, "Predet").</span><span class="sxs-lookup"><span data-stu-id="6e52d-138">In the **Aisle** field, enter a name (for example, "Def").</span></span>
1. <span data-ttu-id="6e52d-139">En el campo **Nombre**, escriba un nombre (por ejemplo, "Pasillo predeterminado").</span><span class="sxs-lookup"><span data-stu-id="6e52d-139">In the **Name** field, enter a name (for example, "Default aisle").</span></span>
1. <span data-ttu-id="6e52d-140">En el panel de acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="6e52d-140">On the action pane, select **Save**.</span></span>

## <a name="set-up-warehouse-inventory-locations"></a><span data-ttu-id="6e52d-141">Configurar ubicaciones de inventario de almacén</span><span class="sxs-lookup"><span data-stu-id="6e52d-141">Set up warehouse inventory locations</span></span>

<span data-ttu-id="6e52d-142">Para configurar ubicaciones de inventario de almacén para inventario estándar, dañado o devuelto, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="6e52d-142">To set up warehouse inventory locations for standard, damaged, and returned inventory, follow these steps.</span></span>

1. <span data-ttu-id="6e52d-143">En el panel de navegación, vaya a **Módulos \> Retail y Commerce \> Configuración de canal \> Almacenes**.</span><span class="sxs-lookup"><span data-stu-id="6e52d-143">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Warehouses**.</span></span>
1. <span data-ttu-id="6e52d-144">Seleccione el almacén que creó previamente.</span><span class="sxs-lookup"><span data-stu-id="6e52d-144">Select the warehouse you created previously.</span></span>
1. <span data-ttu-id="6e52d-145">En el panel de acciones, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="6e52d-145">On the action pane, select **Edit**.</span></span>
1. <span data-ttu-id="6e52d-146">En el panel de acciones, seleccione **Almacén** y, a continuación, seleccione **Ubicación del inventario**.</span><span class="sxs-lookup"><span data-stu-id="6e52d-146">On the action pane, select **Warehouse**, and then select **Inventory location**.</span></span>
1. <span data-ttu-id="6e52d-147">En el panel de acciones, seleccione **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="6e52d-147">On the action pane, select **New**.</span></span> <span data-ttu-id="6e52d-148">La opción predeterminada de la lista desplegable **Almacén** debe ser su nuevo almacén.</span><span class="sxs-lookup"><span data-stu-id="6e52d-148">The **Warehouse** drop-down list should default to your new warehouse.</span></span>
    1. <span data-ttu-id="6e52d-149">En el cuadro **Pasillo**, introduzca el nombre del pasillo que especificó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="6e52d-149">In the **Aisle** box, enter the name of the aisle you specified earlier.</span></span> 
    1. <span data-ttu-id="6e52d-150">Establezca **Actualización manual** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="6e52d-150">Set **Manual update** to **Yes**</span></span>
    1. <span data-ttu-id="6e52d-151">En el cuadro **Ubicación**, introduzca el nombre del almacén.</span><span class="sxs-lookup"><span data-stu-id="6e52d-151">In the **Location** box, enter the name of the warehouse.</span></span>
    1. <span data-ttu-id="6e52d-152">En el panel de acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="6e52d-152">On the action pane, select **Save**.</span></span>
 1. <span data-ttu-id="6e52d-153">En el panel de acciones, seleccione **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="6e52d-153">On the action pane, select **New**.</span></span>  <span data-ttu-id="6e52d-154">La opción predeterminada de la lista desplegable **Almacén** debe ser su nuevo almacén.</span><span class="sxs-lookup"><span data-stu-id="6e52d-154">The **Warehouse** drop-down list should default to your new warehouse.</span></span>
    1. <span data-ttu-id="6e52d-155">En el cuadro **Pasillo**, introduzca el nombre del pasillo que especificó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="6e52d-155">In the **Aisle** box, enter the name of the aisle you specified earlier.</span></span>  
    1. <span data-ttu-id="6e52d-156">Establezca **Actualización manual** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="6e52d-156">Set **Manual update** to **Yes**</span></span>
    1. <span data-ttu-id="6e52d-157">En el cuadro **Ubicación**, introduzca "Dañado".</span><span class="sxs-lookup"><span data-stu-id="6e52d-157">In the **Location** box, enter "Damaged".</span></span>
    1. <span data-ttu-id="6e52d-158">En el panel de acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="6e52d-158">On the action pane, select **Save**.</span></span>
 1. <span data-ttu-id="6e52d-159">En el panel de acciones, seleccione **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="6e52d-159">On the action pane, select **New**.</span></span>  <span data-ttu-id="6e52d-160">La opción predeterminada de la lista desplegable **Almacén** debe ser su nuevo almacén.</span><span class="sxs-lookup"><span data-stu-id="6e52d-160">The **Warehouse** drop-down list should default to your new warehouse.</span></span>
    1. <span data-ttu-id="6e52d-161">En el cuadro **Pasillo**, introduzca el nombre del pasillo que especificó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="6e52d-161">In the **Aisle** box, enter the name of the aisle you specified earlier.</span></span> 
    1. <span data-ttu-id="6e52d-162">Establezca **Actualización manual** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="6e52d-162">Set **Manual update** to **Yes**</span></span>
    1. <span data-ttu-id="6e52d-163">En el cuadro **Ubicación**, introduzca "Devolución".</span><span class="sxs-lookup"><span data-stu-id="6e52d-163">In the **Location** box, enter "Returns".</span></span>
    1. <span data-ttu-id="6e52d-164">En el panel de acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="6e52d-164">On the action pane, select **Save**.</span></span>
    
<span data-ttu-id="6e52d-165">La siguiente imagen muestra una configuración de ubicación de inventario de almacén en San Francisco.</span><span class="sxs-lookup"><span data-stu-id="6e52d-165">The following image shows a San Francisco warehouse inventory location setup.</span></span>

![Ejemplo de configuración de ubicación de inventario](media/warehouse-inventory-locations.png)
    
## <a name="complete-warehouse-setup"></a><span data-ttu-id="6e52d-167">Configuración de almacén completo</span><span class="sxs-lookup"><span data-stu-id="6e52d-167">Complete warehouse setup</span></span>

<span data-ttu-id="6e52d-168">Para completar la configuración de almacén, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="6e52d-168">To complete warehouse setup, follow these steps.</span></span>

1. <span data-ttu-id="6e52d-169">En el panel de navegación, vaya a **Módulos \> Retail y Commerce \> Configuración de canal \> Almacenes**.</span><span class="sxs-lookup"><span data-stu-id="6e52d-169">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Warehouses**.</span></span>
1. <span data-ttu-id="6e52d-170">Seleccione el almacén que creó previamente.</span><span class="sxs-lookup"><span data-stu-id="6e52d-170">Select the warehouse you previously created.</span></span>
1. <span data-ttu-id="6e52d-171">En el panel de acciones, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="6e52d-171">On the action pane, select **Edit**.</span></span>
1. <span data-ttu-id="6e52d-172">En **Módulo de gestión de inventario y almacenes**:</span><span class="sxs-lookup"><span data-stu-id="6e52d-172">Under **Inventory and warehouse management**:</span></span>
    1. <span data-ttu-id="6e52d-173">Establezca **Ubicación predeterminada de la recepción** en la ubicación predeterminada que se creó previamente.</span><span class="sxs-lookup"><span data-stu-id="6e52d-173">Set **Default receipt location** to the default location created above.</span></span>
    1. <span data-ttu-id="6e52d-174">Establezca **Ubicación predeterminada de emisión** en la ubicación predeterminada que se creó previamente.</span><span class="sxs-lookup"><span data-stu-id="6e52d-174">Select **Default issue location** to the default location created above.</span></span>
1. <span data-ttu-id="6e52d-175">En la sección **Direcciones**, introduzca una dirección de almacén.</span><span class="sxs-lookup"><span data-stu-id="6e52d-175">Under the **Addresses** section, enter a warehouse address.</span></span>
1. <span data-ttu-id="6e52d-176">En la sección **Venta minorista**:</span><span class="sxs-lookup"><span data-stu-id="6e52d-176">Under the **Retail** section:</span></span> 
    1. <span data-ttu-id="6e52d-177">En el cuadro **Ubicación de devolución predeterminada**, introduzca la ubicación de devoluciones que creó previamente.</span><span class="sxs-lookup"><span data-stu-id="6e52d-177">In the **Default return location** box, enter the returns location created previously.</span></span>
    1. <span data-ttu-id="6e52d-178">Establezca **Tienda** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="6e52d-178">Set **Store** to **Yes**.</span></span>
    1. <span data-ttu-id="6e52d-179">Establezca **Peso** en **1,00**.</span><span class="sxs-lookup"><span data-stu-id="6e52d-179">Set **Weight** to **1.00**.</span></span> 
    1. <span data-ttu-id="6e52d-180">En el cuadro **Dimensiones de almacenamiento**, introduzca la ubicación predeterminada que creó previamente.</span><span class="sxs-lookup"><span data-stu-id="6e52d-180">In the **Storage Dimensions** box, enter the default location created previously.</span></span>
1. <span data-ttu-id="6e52d-181">En la sección **Almacén**, establezca **Inventario físico negativo** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="6e52d-181">Under the **Warehouse** section, set **Physical negative inventory** to **Yes**.</span></span>
1. <span data-ttu-id="6e52d-182">En el panel de acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="6e52d-182">On the action pane, select **Save**.</span></span>

<span data-ttu-id="6e52d-183">La siguiente imagen muestra los detalles de un almacén configurado.</span><span class="sxs-lookup"><span data-stu-id="6e52d-183">The following image shows details for a configured warehouse.</span></span>

![Ejemplo de almacén configurado](media/warehouse-sample.png)

## <a name="additional-resources"></a><span data-ttu-id="6e52d-185">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="6e52d-185">Additional resources</span></span>

[<span data-ttu-id="6e52d-186">Visión general de la gestión de almacenes</span><span class="sxs-lookup"><span data-stu-id="6e52d-186">Warehouse management overview</span></span>](https://docs.microsoft.com/en-us/dynamics365/supply-chain/warehousing/warehouse-management-overview)

[<span data-ttu-id="6e52d-187">Resumen de canales</span><span class="sxs-lookup"><span data-stu-id="6e52d-187">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="6e52d-188">Requisitos previos de configuración de canales</span><span class="sxs-lookup"><span data-stu-id="6e52d-188">Channel setup prerequisites</span></span>](channels-prerequisites.md)

[<span data-ttu-id="6e52d-189">Configurar un canal comercial</span><span class="sxs-lookup"><span data-stu-id="6e52d-189">Set up a retail channel</span></span>](channel-setup-retail.md)
    
[<span data-ttu-id="6e52d-190">Configurar un canal en línea</span><span class="sxs-lookup"><span data-stu-id="6e52d-190">Set up an online channel</span></span>](channel-setup-online.md)

[<span data-ttu-id="6e52d-191">Configurar un canal de centro de llamadas</span><span class="sxs-lookup"><span data-stu-id="6e52d-191">Set up a call center channel</span></span>](channel-setup-callcenter.md)





