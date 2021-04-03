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
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 772c7584549b30a34e371a7911131edc01214ed8
ms.sourcegitcommit: c88b54ba13a4dfe39b844ffaced4dc435560c47d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2021
ms.locfileid: "5477643"
---
# <a name="warehouse-set-up"></a><span data-ttu-id="956a4-103">Configuración de almacén</span><span class="sxs-lookup"><span data-stu-id="956a4-103">Warehouse set up</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="956a4-104">En este tema se describe cómo configurar un almacén para utilizarlo con un nuevo canal en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="956a4-104">This topic describes how to set up a warehouse to be used with a new channel in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="956a4-105">Cada canal de Commerce requiere que se le asocie un almacén configurado.</span><span class="sxs-lookup"><span data-stu-id="956a4-105">Each Commerce channel requires a configured warehouse to be associated with it.</span></span> <span data-ttu-id="956a4-106">Los siguientes procedimientos proporcionan la configuración mínima requerida para configurar un almacén para un canal de Commerce.</span><span class="sxs-lookup"><span data-stu-id="956a4-106">The following procedures provide the minimum configuration required to set up a warehouse for a Commerce channel.</span></span> <span data-ttu-id="956a4-107">Para obtener más información sobre la configuración del almacén, consulte la [Visión general de la gestión de almacenes](../supply-chain/warehousing/warehouse-management-overview.md?toc=/dynamics365/commerce/toc.json).</span><span class="sxs-lookup"><span data-stu-id="956a4-107">For more information regarding warehouse setup, please see the [Warehouse management overview](../supply-chain/warehousing/warehouse-management-overview.md?toc=/dynamics365/commerce/toc.json).</span></span>

## <a name="configure-a-warehouse-site"></a><span data-ttu-id="956a4-108">Configurar un sitio de almacén</span><span class="sxs-lookup"><span data-stu-id="956a4-108">Configure a warehouse site</span></span>

<span data-ttu-id="956a4-109">Antes de configurar un almacén, debe configurar un sitio de almacén.</span><span class="sxs-lookup"><span data-stu-id="956a4-109">Before setting up a warehouse, you need to configure a warehouse site.</span></span>

<span data-ttu-id="956a4-110">Para configurar un sitio de almacén, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="956a4-110">To configure a warehouse site, follow these steps.</span></span>

1. <span data-ttu-id="956a4-111">En el panel de navegación, vaya a **Módulos \> Retail y Commerce \> Configuración de canal \> Sitios**.</span><span class="sxs-lookup"><span data-stu-id="956a4-111">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Sites**.</span></span>
1. <span data-ttu-id="956a4-112">En el panel de acciones, seleccione **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="956a4-112">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="956a4-113">En el campo **Sitio**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="956a4-113">In the **Site** field, enter a value.</span></span>
1. <span data-ttu-id="956a4-114">En el campo **Nombre**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="956a4-114">In the **Name** field, enter a value.</span></span>
1. <span data-ttu-id="956a4-115">En la sección **General**, establezca la **Zona horaria** apropiada.</span><span class="sxs-lookup"><span data-stu-id="956a4-115">In the **General** section, set the appropriate **Time zone**.</span></span>
1. <span data-ttu-id="956a4-116">En la sección **Direcciones**, escriba una dirección.</span><span class="sxs-lookup"><span data-stu-id="956a4-116">In the **Addresses** section, enter an address.</span></span>
1. <span data-ttu-id="956a4-117">En el panel de acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="956a4-117">On the action pane, select **Save**.</span></span>

<span data-ttu-id="956a4-118">La siguiente imagen muestra un ejemplo de sitio de almacén.</span><span class="sxs-lookup"><span data-stu-id="956a4-118">The following image shows an example warehouse site.</span></span>

![Ejemplo de sitio de almacén](media/warehouse-site.png)

## <a name="set-up-a-warehouse"></a><span data-ttu-id="956a4-120">Configurar un almacén</span><span class="sxs-lookup"><span data-stu-id="956a4-120">Set up a warehouse</span></span>

<span data-ttu-id="956a4-121">Para configurar un almacén, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="956a4-121">To set up a warehouse, follow these steps.</span></span>

1. <span data-ttu-id="956a4-122">En el panel de navegación, vaya a **Módulos \> Retail y Commerce \> Configuración de canal \> Almacenes**.</span><span class="sxs-lookup"><span data-stu-id="956a4-122">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Warehouses**.</span></span>
1. <span data-ttu-id="956a4-123">En el panel de acciones, seleccione **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="956a4-123">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="956a4-124">En el campo **Almacén**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="956a4-124">In the **Warehouse** field, enter a value.</span></span>  <span data-ttu-id="956a4-125">Si se trata de una asignación 1:1 a una tienda, considere la posibilidad de usar el nombre de la tienda o el nombre de un centro de distribución regional.</span><span class="sxs-lookup"><span data-stu-id="956a4-125">If this is a 1:1 mapping to a store, consider using the store name or the name of a regional distribution center.</span></span>
1. <span data-ttu-id="956a4-126">En el campo **Nombre**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="956a4-126">In the **Name** field, enter a value.</span></span>
1. <span data-ttu-id="956a4-127">En la lista desplegable **Sitio**, seleccione el sitio de almacén creado previamente.</span><span class="sxs-lookup"><span data-stu-id="956a4-127">In the **Site** drop-down list, select the warehouse site created previously.</span></span>
1. <span data-ttu-id="956a4-128">En el campo **Tipo**, seleccione **Predeterminado**.</span><span class="sxs-lookup"><span data-stu-id="956a4-128">In the **Type** field, select **Default**.</span></span>
    - <span data-ttu-id="956a4-129">Si desea establecer un **Almacén de cuarentena**, primero deberá seguir estos pasos para crear un almacén adicional donde se establezca **Tipo** en **Cuarentena**.</span><span class="sxs-lookup"><span data-stu-id="956a4-129">If you want to set a **Quarantine warehouse**, first you'll need to follow these steps to create an additional warehouse where the **Type** is set to **Quarantine**.</span></span>
    - <span data-ttu-id="956a4-130">Si desea establecer un **Almacén de tránsito**, primero debe seguir estos pasos para crear un almacén adicional donde se establezca **Tipo** en **Tránsito**.</span><span class="sxs-lookup"><span data-stu-id="956a4-130">If you want to set a **Transit warehouse**, first you'll need to follow these steps to create an additional warehouse where the **Type** is set to **Transit**.</span></span>
1. <span data-ttu-id="956a4-131">En el panel de acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="956a4-131">On the action pane, select **Save**.</span></span>

## <a name="set-up-inventory-aisles"></a><span data-ttu-id="956a4-132">Configurar pasillos de inventario</span><span class="sxs-lookup"><span data-stu-id="956a4-132">Set up inventory aisles</span></span>

<span data-ttu-id="956a4-133">Para configurar pasillos de inventario, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="956a4-133">To set up inventory aisles, follow these steps.</span></span>

1. <span data-ttu-id="956a4-134">En el panel de navegación, vaya a **Módulos \> Retail y Commerce \> Configuración de canal \> Configuración de la ubicación \> Pasillos de inventario**.</span><span class="sxs-lookup"><span data-stu-id="956a4-134">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Location setup \> Inventory aisles**.</span></span>
1. <span data-ttu-id="956a4-135">En el panel de acciones, seleccione **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="956a4-135">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="956a4-136">En la lista desplegable **Almacén**, seleccione el almacén creado previamente.</span><span class="sxs-lookup"><span data-stu-id="956a4-136">In the **Warehouse** drop-down list, select the warehouse created previously.</span></span>
1. <span data-ttu-id="956a4-137">En el campo **Pasillo**, especifique un nombre (por ejemplo, "Predet").</span><span class="sxs-lookup"><span data-stu-id="956a4-137">In the **Aisle** field, enter a name (for example, "Def").</span></span>
1. <span data-ttu-id="956a4-138">En el campo **Nombre**, escriba un nombre (por ejemplo, "Pasillo predeterminado").</span><span class="sxs-lookup"><span data-stu-id="956a4-138">In the **Name** field, enter a name (for example, "Default aisle").</span></span>
1. <span data-ttu-id="956a4-139">En el panel de acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="956a4-139">On the action pane, select **Save**.</span></span>

## <a name="set-up-warehouse-inventory-locations"></a><span data-ttu-id="956a4-140">Configurar ubicaciones de inventario de almacén</span><span class="sxs-lookup"><span data-stu-id="956a4-140">Set up warehouse inventory locations</span></span>

<span data-ttu-id="956a4-141">Para configurar ubicaciones de inventario de almacén para inventario estándar, dañado o devuelto, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="956a4-141">To set up warehouse inventory locations for standard, damaged, and returned inventory, follow these steps.</span></span>

1. <span data-ttu-id="956a4-142">En el panel de navegación, vaya a **Módulos \> Retail y Commerce \> Configuración de canal \> Almacenes**.</span><span class="sxs-lookup"><span data-stu-id="956a4-142">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Warehouses**.</span></span>
1. <span data-ttu-id="956a4-143">Seleccione el almacén que creó previamente.</span><span class="sxs-lookup"><span data-stu-id="956a4-143">Select the warehouse you created previously.</span></span>
1. <span data-ttu-id="956a4-144">En el panel de acciones, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="956a4-144">On the action pane, select **Edit**.</span></span>
1. <span data-ttu-id="956a4-145">En el panel de acciones, seleccione **Almacén** y, a continuación, seleccione **Ubicación del inventario**.</span><span class="sxs-lookup"><span data-stu-id="956a4-145">On the action pane, select **Warehouse**, and then select **Inventory location**.</span></span>
1. <span data-ttu-id="956a4-146">En el panel de acciones, seleccione **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="956a4-146">On the action pane, select **New**.</span></span> <span data-ttu-id="956a4-147">La opción predeterminada de la lista desplegable **Almacén** debe ser su nuevo almacén.</span><span class="sxs-lookup"><span data-stu-id="956a4-147">The **Warehouse** drop-down list should default to your new warehouse.</span></span>
    1. <span data-ttu-id="956a4-148">En el cuadro **Pasillo**, introduzca el nombre del pasillo que especificó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="956a4-148">In the **Aisle** box, enter the name of the aisle you specified earlier.</span></span> 
    1. <span data-ttu-id="956a4-149">Establezca **Actualización manual** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="956a4-149">Set **Manual update** to **Yes**</span></span>
    1. <span data-ttu-id="956a4-150">En el cuadro **Ubicación**, introduzca el nombre del almacén.</span><span class="sxs-lookup"><span data-stu-id="956a4-150">In the **Location** box, enter the name of the warehouse.</span></span>
    1. <span data-ttu-id="956a4-151">En el panel de acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="956a4-151">On the action pane, select **Save**.</span></span>
 1. <span data-ttu-id="956a4-152">En el panel de acciones, seleccione **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="956a4-152">On the action pane, select **New**.</span></span>  <span data-ttu-id="956a4-153">La opción predeterminada de la lista desplegable **Almacén** debe ser su nuevo almacén.</span><span class="sxs-lookup"><span data-stu-id="956a4-153">The **Warehouse** drop-down list should default to your new warehouse.</span></span>
    1. <span data-ttu-id="956a4-154">En el cuadro **Pasillo**, introduzca el nombre del pasillo que especificó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="956a4-154">In the **Aisle** box, enter the name of the aisle you specified earlier.</span></span>  
    1. <span data-ttu-id="956a4-155">Establezca **Actualización manual** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="956a4-155">Set **Manual update** to **Yes**</span></span>
    1. <span data-ttu-id="956a4-156">En el cuadro **Ubicación**, introduzca "Dañado".</span><span class="sxs-lookup"><span data-stu-id="956a4-156">In the **Location** box, enter "Damaged".</span></span>
    1. <span data-ttu-id="956a4-157">En el panel de acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="956a4-157">On the action pane, select **Save**.</span></span>
 1. <span data-ttu-id="956a4-158">En el panel de acciones, seleccione **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="956a4-158">On the action pane, select **New**.</span></span>  <span data-ttu-id="956a4-159">La opción predeterminada de la lista desplegable **Almacén** debe ser su nuevo almacén.</span><span class="sxs-lookup"><span data-stu-id="956a4-159">The **Warehouse** drop-down list should default to your new warehouse.</span></span>
    1. <span data-ttu-id="956a4-160">En el cuadro **Pasillo**, introduzca el nombre del pasillo que especificó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="956a4-160">In the **Aisle** box, enter the name of the aisle you specified earlier.</span></span> 
    1. <span data-ttu-id="956a4-161">Establezca **Actualización manual** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="956a4-161">Set **Manual update** to **Yes**</span></span>
    1. <span data-ttu-id="956a4-162">En el cuadro **Ubicación**, introduzca "Devolución".</span><span class="sxs-lookup"><span data-stu-id="956a4-162">In the **Location** box, enter "Returns".</span></span>
    1. <span data-ttu-id="956a4-163">En el panel de acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="956a4-163">On the action pane, select **Save**.</span></span>
    
<span data-ttu-id="956a4-164">La siguiente imagen muestra una configuración de ubicación de inventario de almacén en San Francisco.</span><span class="sxs-lookup"><span data-stu-id="956a4-164">The following image shows a San Francisco warehouse inventory location setup.</span></span>

![Ejemplo de configuración de ubicación de inventario](media/warehouse-inventory-locations.png)
    
## <a name="complete-warehouse-setup"></a><span data-ttu-id="956a4-166">Configuración de almacén completo</span><span class="sxs-lookup"><span data-stu-id="956a4-166">Complete warehouse setup</span></span>

<span data-ttu-id="956a4-167">Para completar la configuración de almacén, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="956a4-167">To complete warehouse setup, follow these steps.</span></span>

1. <span data-ttu-id="956a4-168">En el panel de navegación, vaya a **Módulos \> Retail y Commerce \> Configuración de canal \> Almacenes**.</span><span class="sxs-lookup"><span data-stu-id="956a4-168">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Warehouses**.</span></span>
1. <span data-ttu-id="956a4-169">Seleccione el almacén que creó previamente.</span><span class="sxs-lookup"><span data-stu-id="956a4-169">Select the warehouse you previously created.</span></span>
1. <span data-ttu-id="956a4-170">En el panel de acciones, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="956a4-170">On the action pane, select **Edit**.</span></span>
1. <span data-ttu-id="956a4-171">En **Módulo de gestión de inventario y almacenes**:</span><span class="sxs-lookup"><span data-stu-id="956a4-171">Under **Inventory and warehouse management**:</span></span>
    1. <span data-ttu-id="956a4-172">Establezca **Ubicación predeterminada de la recepción** en la ubicación predeterminada que se creó previamente.</span><span class="sxs-lookup"><span data-stu-id="956a4-172">Set **Default receipt location** to the default location created above.</span></span>
    1. <span data-ttu-id="956a4-173">Establezca **Ubicación predeterminada de emisión** en la ubicación predeterminada que se creó previamente.</span><span class="sxs-lookup"><span data-stu-id="956a4-173">Select **Default issue location** to the default location created above.</span></span>
1. <span data-ttu-id="956a4-174">En la sección **Direcciones**, introduzca una dirección de almacén.</span><span class="sxs-lookup"><span data-stu-id="956a4-174">Under the **Addresses** section, enter a warehouse address.</span></span>
1. <span data-ttu-id="956a4-175">En la sección **Venta minorista**:</span><span class="sxs-lookup"><span data-stu-id="956a4-175">Under the **Retail** section:</span></span> 
    1. <span data-ttu-id="956a4-176">En el cuadro **Ubicación de devolución predeterminada**, introduzca la ubicación de devoluciones que creó previamente.</span><span class="sxs-lookup"><span data-stu-id="956a4-176">In the **Default return location** box, enter the returns location created previously.</span></span>
    1. <span data-ttu-id="956a4-177">Establezca **Tienda** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="956a4-177">Set **Store** to **Yes**.</span></span>
    1. <span data-ttu-id="956a4-178">Establezca **Peso** en **1,00**.</span><span class="sxs-lookup"><span data-stu-id="956a4-178">Set **Weight** to **1.00**.</span></span> 
    1. <span data-ttu-id="956a4-179">En el cuadro **Dimensiones de almacenamiento**, introduzca la ubicación predeterminada que creó previamente.</span><span class="sxs-lookup"><span data-stu-id="956a4-179">In the **Storage Dimensions** box, enter the default location created previously.</span></span>
1. <span data-ttu-id="956a4-180">En la sección **Almacén**, establezca **Inventario físico negativo** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="956a4-180">Under the **Warehouse** section, set **Physical negative inventory** to **Yes**.</span></span>
1. <span data-ttu-id="956a4-181">En el panel de acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="956a4-181">On the action pane, select **Save**.</span></span>

<span data-ttu-id="956a4-182">La siguiente imagen muestra los detalles de un almacén configurado.</span><span class="sxs-lookup"><span data-stu-id="956a4-182">The following image shows details for a configured warehouse.</span></span>

![Ejemplo de almacén configurado](media/warehouse-sample.png)

## <a name="additional-resources"></a><span data-ttu-id="956a4-184">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="956a4-184">Additional resources</span></span>

[<span data-ttu-id="956a4-185">Visión general de la gestión de almacenes</span><span class="sxs-lookup"><span data-stu-id="956a4-185">Warehouse management overview</span></span>](../supply-chain/warehousing/warehouse-management-overview.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="956a4-186">Resumen de canales</span><span class="sxs-lookup"><span data-stu-id="956a4-186">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="956a4-187">Requisitos previos de configuración de canales</span><span class="sxs-lookup"><span data-stu-id="956a4-187">Channel setup prerequisites</span></span>](channels-prerequisites.md)

[<span data-ttu-id="956a4-188">Configurar un canal comercial</span><span class="sxs-lookup"><span data-stu-id="956a4-188">Set up a retail channel</span></span>](channel-setup-retail.md)
    
[<span data-ttu-id="956a4-189">Configurar un canal en línea</span><span class="sxs-lookup"><span data-stu-id="956a4-189">Set up an online channel</span></span>](channel-setup-online.md)

[<span data-ttu-id="956a4-190">Configurar un canal de centro de llamadas</span><span class="sxs-lookup"><span data-stu-id="956a4-190">Set up a call center channel</span></span>](channel-setup-callcenter.md)







[!INCLUDE[footer-include](../includes/footer-banner.md)]
