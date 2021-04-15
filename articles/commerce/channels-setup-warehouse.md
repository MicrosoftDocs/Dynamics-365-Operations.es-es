---
title: Configurar un almacén
description: En este tema se describe cómo configurar un almacén para utilizarlo con un nuevo canal en Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 154ec719e16e4826b0e24deb5ecadf587d938e3c
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5800504"
---
# <a name="warehouse-set-up"></a><span data-ttu-id="a9405-103">Configuración de almacén</span><span class="sxs-lookup"><span data-stu-id="a9405-103">Warehouse set up</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="a9405-104">En este tema se describe cómo configurar un almacén para utilizarlo con un nuevo canal en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="a9405-104">This topic describes how to set up a warehouse to be used with a new channel in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="a9405-105">Cada canal de Commerce requiere que se le asocie un almacén configurado.</span><span class="sxs-lookup"><span data-stu-id="a9405-105">Each Commerce channel requires a configured warehouse to be associated with it.</span></span> <span data-ttu-id="a9405-106">Los siguientes procedimientos proporcionan la configuración mínima requerida para configurar un almacén para un canal de Commerce.</span><span class="sxs-lookup"><span data-stu-id="a9405-106">The following procedures provide the minimum configuration required to set up a warehouse for a Commerce channel.</span></span> <span data-ttu-id="a9405-107">Para obtener más información sobre la configuración del almacén, consulte la [Visión general de la gestión de almacenes](../supply-chain/warehousing/warehouse-management-overview.md?toc=/dynamics365/commerce/toc.json).</span><span class="sxs-lookup"><span data-stu-id="a9405-107">For more information regarding warehouse setup, please see the [Warehouse management overview](../supply-chain/warehousing/warehouse-management-overview.md?toc=/dynamics365/commerce/toc.json).</span></span>

## <a name="configure-a-warehouse-site"></a><span data-ttu-id="a9405-108">Configurar un sitio de almacén</span><span class="sxs-lookup"><span data-stu-id="a9405-108">Configure a warehouse site</span></span>

<span data-ttu-id="a9405-109">Antes de configurar un almacén, debe configurar un sitio de almacén.</span><span class="sxs-lookup"><span data-stu-id="a9405-109">Before setting up a warehouse, you need to configure a warehouse site.</span></span>

<span data-ttu-id="a9405-110">Para configurar un sitio de almacén, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="a9405-110">To configure a warehouse site, follow these steps.</span></span>

1. <span data-ttu-id="a9405-111">En el panel de navegación, vaya a **Módulos \> Retail y Commerce \> Configuración de canal \> Sitios**.</span><span class="sxs-lookup"><span data-stu-id="a9405-111">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Sites**.</span></span>
1. <span data-ttu-id="a9405-112">En el panel de acciones, seleccione **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="a9405-112">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="a9405-113">En el campo **Sitio**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="a9405-113">In the **Site** field, enter a value.</span></span>
1. <span data-ttu-id="a9405-114">En el campo **Nombre**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="a9405-114">In the **Name** field, enter a value.</span></span>
1. <span data-ttu-id="a9405-115">En la sección **General**, establezca la **Zona horaria** apropiada.</span><span class="sxs-lookup"><span data-stu-id="a9405-115">In the **General** section, set the appropriate **Time zone**.</span></span>
1. <span data-ttu-id="a9405-116">En la sección **Direcciones**, escriba una dirección.</span><span class="sxs-lookup"><span data-stu-id="a9405-116">In the **Addresses** section, enter an address.</span></span>
1. <span data-ttu-id="a9405-117">En el panel de acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="a9405-117">On the action pane, select **Save**.</span></span>

<span data-ttu-id="a9405-118">La siguiente imagen muestra un ejemplo de sitio de almacén.</span><span class="sxs-lookup"><span data-stu-id="a9405-118">The following image shows an example warehouse site.</span></span>

![Ejemplo de sitio de almacén](media/warehouse-site.png)

## <a name="set-up-a-warehouse&quot;></a><span data-ttu-id=&quot;a9405-120&quot;>Configurar un almacén</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;a9405-120&quot;>Set up a warehouse</span></span>

<span data-ttu-id=&quot;a9405-121&quot;>Para configurar un almacén, siga estos pasos.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;a9405-121&quot;>To set up a warehouse, follow these steps.</span></span>

1. <span data-ttu-id=&quot;a9405-122&quot;>En el panel de navegación, vaya a **Módulos \> Retail y Commerce \> Configuración de canal \> Almacenes**.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;a9405-122&quot;>In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Warehouses**.</span></span>
1. <span data-ttu-id=&quot;a9405-123&quot;>En el panel de acciones, seleccione **Nueva**.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;a9405-123&quot;>On the action pane, select **New**.</span></span>
1. <span data-ttu-id=&quot;a9405-124&quot;>En el campo **Almacén**, especifique o seleccione un valor.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;a9405-124&quot;>In the **Warehouse** field, enter a value.</span></span>  <span data-ttu-id=&quot;a9405-125&quot;>Si se trata de una asignación 1:1 a una tienda, considere la posibilidad de usar el nombre de la tienda o el nombre de un centro de distribución regional.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;a9405-125&quot;>If this is a 1:1 mapping to a store, consider using the store name or the name of a regional distribution center.</span></span>
1. <span data-ttu-id=&quot;a9405-126&quot;>En el campo **Nombre**, escriba un valor.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;a9405-126&quot;>In the **Name** field, enter a value.</span></span>
1. <span data-ttu-id=&quot;a9405-127&quot;>En la lista desplegable **Sitio**, seleccione el sitio de almacén creado previamente.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;a9405-127&quot;>In the **Site** drop-down list, select the warehouse site created previously.</span></span>
1. <span data-ttu-id=&quot;a9405-128&quot;>En el campo **Tipo**, seleccione **Predeterminado**.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;a9405-128&quot;>In the **Type** field, select **Default**.</span></span>
    - <span data-ttu-id=&quot;a9405-129&quot;>Si desea establecer un **Almacén de cuarentena**, primero deberá seguir estos pasos para crear un almacén adicional donde se establezca **Tipo** en **Cuarentena**.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;a9405-129&quot;>If you want to set a **Quarantine warehouse**, first you'll need to follow these steps to create an additional warehouse where the **Type** is set to **Quarantine**.</span></span>
    - <span data-ttu-id=&quot;a9405-130&quot;>Si desea establecer un **Almacén de tránsito**, primero debe seguir estos pasos para crear un almacén adicional donde se establezca **Tipo** en **Tránsito**.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;a9405-130&quot;>If you want to set a **Transit warehouse**, first you'll need to follow these steps to create an additional warehouse where the **Type** is set to **Transit**.</span></span>
1. <span data-ttu-id=&quot;a9405-131&quot;>En el panel de acciones, seleccione **Guardar**.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;a9405-131&quot;>On the action pane, select **Save**.</span></span>

## <a name=&quot;set-up-inventory-aisles&quot;></a><span data-ttu-id=&quot;a9405-132&quot;>Configurar pasillos de inventario</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;a9405-132&quot;>Set up inventory aisles</span></span>

<span data-ttu-id=&quot;a9405-133&quot;>Para configurar pasillos de inventario, siga estos pasos.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;a9405-133&quot;>To set up inventory aisles, follow these steps.</span></span>

1. <span data-ttu-id=&quot;a9405-134&quot;>En el panel de navegación, vaya a **Módulos \> Retail y Commerce \> Configuración de canal \> Configuración de la ubicación \> Pasillos de inventario**.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;a9405-134&quot;>In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Location setup \> Inventory aisles**.</span></span>
1. <span data-ttu-id=&quot;a9405-135&quot;>En el panel de acciones, seleccione **Nueva**.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;a9405-135&quot;>On the action pane, select **New**.</span></span>
1. <span data-ttu-id=&quot;a9405-136&quot;>En la lista desplegable **Almacén**, seleccione el almacén creado previamente.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;a9405-136&quot;>In the **Warehouse** drop-down list, select the warehouse created previously.</span></span>
1. <span data-ttu-id=&quot;a9405-137&quot;>En el campo **Pasillo**, especifique un nombre (por ejemplo, &quot;Predet").</span><span class="sxs-lookup"><span data-stu-id="a9405-137">In the **Aisle** field, enter a name (for example, "Def").</span></span>
1. <span data-ttu-id="a9405-138">En el campo **Nombre**, escriba un nombre (por ejemplo, "Pasillo predeterminado").</span><span class="sxs-lookup"><span data-stu-id="a9405-138">In the **Name** field, enter a name (for example, "Default aisle").</span></span>
1. <span data-ttu-id="a9405-139">En el panel de acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="a9405-139">On the action pane, select **Save**.</span></span>

## <a name="set-up-warehouse-inventory-locations"></a><span data-ttu-id="a9405-140">Configurar ubicaciones de inventario de almacén</span><span class="sxs-lookup"><span data-stu-id="a9405-140">Set up warehouse inventory locations</span></span>

<span data-ttu-id="a9405-141">Para configurar ubicaciones de inventario de almacén para inventario estándar, dañado o devuelto, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="a9405-141">To set up warehouse inventory locations for standard, damaged, and returned inventory, follow these steps.</span></span>

1. <span data-ttu-id="a9405-142">En el panel de navegación, vaya a **Módulos \> Retail y Commerce \> Configuración de canal \> Almacenes**.</span><span class="sxs-lookup"><span data-stu-id="a9405-142">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Warehouses**.</span></span>
1. <span data-ttu-id="a9405-143">Seleccione el almacén que creó previamente.</span><span class="sxs-lookup"><span data-stu-id="a9405-143">Select the warehouse you created previously.</span></span>
1. <span data-ttu-id="a9405-144">En el panel de acciones, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="a9405-144">On the action pane, select **Edit**.</span></span>
1. <span data-ttu-id="a9405-145">En el panel de acciones, seleccione **Almacén** y, a continuación, seleccione **Ubicación del inventario**.</span><span class="sxs-lookup"><span data-stu-id="a9405-145">On the action pane, select **Warehouse**, and then select **Inventory location**.</span></span>
1. <span data-ttu-id="a9405-146">En el panel de acciones, seleccione **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="a9405-146">On the action pane, select **New**.</span></span> <span data-ttu-id="a9405-147">La opción predeterminada de la lista desplegable **Almacén** debe ser su nuevo almacén.</span><span class="sxs-lookup"><span data-stu-id="a9405-147">The **Warehouse** drop-down list should default to your new warehouse.</span></span>
    1. <span data-ttu-id="a9405-148">En el cuadro **Pasillo**, introduzca el nombre del pasillo que especificó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="a9405-148">In the **Aisle** box, enter the name of the aisle you specified earlier.</span></span> 
    1. <span data-ttu-id="a9405-149">Establezca **Actualización manual** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="a9405-149">Set **Manual update** to **Yes**</span></span>
    1. <span data-ttu-id="a9405-150">En el cuadro **Ubicación**, introduzca el nombre del almacén.</span><span class="sxs-lookup"><span data-stu-id="a9405-150">In the **Location** box, enter the name of the warehouse.</span></span>
    1. <span data-ttu-id="a9405-151">En el panel de acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="a9405-151">On the action pane, select **Save**.</span></span>
 1. <span data-ttu-id="a9405-152">En el panel de acciones, seleccione **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="a9405-152">On the action pane, select **New**.</span></span>  <span data-ttu-id="a9405-153">La opción predeterminada de la lista desplegable **Almacén** debe ser su nuevo almacén.</span><span class="sxs-lookup"><span data-stu-id="a9405-153">The **Warehouse** drop-down list should default to your new warehouse.</span></span>
    1. <span data-ttu-id="a9405-154">En el cuadro **Pasillo**, introduzca el nombre del pasillo que especificó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="a9405-154">In the **Aisle** box, enter the name of the aisle you specified earlier.</span></span>  
    1. <span data-ttu-id="a9405-155">Establezca **Actualización manual** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="a9405-155">Set **Manual update** to **Yes**</span></span>
    1. <span data-ttu-id="a9405-156">En el cuadro **Ubicación**, introduzca "Dañado".</span><span class="sxs-lookup"><span data-stu-id="a9405-156">In the **Location** box, enter "Damaged".</span></span>
    1. <span data-ttu-id="a9405-157">En el panel de acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="a9405-157">On the action pane, select **Save**.</span></span>
 1. <span data-ttu-id="a9405-158">En el panel de acciones, seleccione **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="a9405-158">On the action pane, select **New**.</span></span>  <span data-ttu-id="a9405-159">La opción predeterminada de la lista desplegable **Almacén** debe ser su nuevo almacén.</span><span class="sxs-lookup"><span data-stu-id="a9405-159">The **Warehouse** drop-down list should default to your new warehouse.</span></span>
    1. <span data-ttu-id="a9405-160">En el cuadro **Pasillo**, introduzca el nombre del pasillo que especificó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="a9405-160">In the **Aisle** box, enter the name of the aisle you specified earlier.</span></span> 
    1. <span data-ttu-id="a9405-161">Establezca **Actualización manual** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="a9405-161">Set **Manual update** to **Yes**</span></span>
    1. <span data-ttu-id="a9405-162">En el cuadro **Ubicación**, introduzca "Devolución".</span><span class="sxs-lookup"><span data-stu-id="a9405-162">In the **Location** box, enter "Returns".</span></span>
    1. <span data-ttu-id="a9405-163">En el panel de acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="a9405-163">On the action pane, select **Save**.</span></span>
    
<span data-ttu-id="a9405-164">La siguiente imagen muestra una configuración de ubicación de inventario de almacén en San Francisco.</span><span class="sxs-lookup"><span data-stu-id="a9405-164">The following image shows a San Francisco warehouse inventory location setup.</span></span>

![Ejemplo de configuración de ubicación de inventario](media/warehouse-inventory-locations.png)
    
## <a name="complete-warehouse-setup"></a><span data-ttu-id="a9405-166">Configuración de almacén completo</span><span class="sxs-lookup"><span data-stu-id="a9405-166">Complete warehouse setup</span></span>

<span data-ttu-id="a9405-167">Para completar la configuración de almacén, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="a9405-167">To complete warehouse setup, follow these steps.</span></span>

1. <span data-ttu-id="a9405-168">En el panel de navegación, vaya a **Módulos \> Retail y Commerce \> Configuración de canal \> Almacenes**.</span><span class="sxs-lookup"><span data-stu-id="a9405-168">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Warehouses**.</span></span>
1. <span data-ttu-id="a9405-169">Seleccione el almacén que creó previamente.</span><span class="sxs-lookup"><span data-stu-id="a9405-169">Select the warehouse you previously created.</span></span>
1. <span data-ttu-id="a9405-170">En el panel de acciones, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="a9405-170">On the action pane, select **Edit**.</span></span>
1. <span data-ttu-id="a9405-171">En **Módulo de gestión de inventario y almacenes**:</span><span class="sxs-lookup"><span data-stu-id="a9405-171">Under **Inventory and warehouse management**:</span></span>
    1. <span data-ttu-id="a9405-172">Establezca **Ubicación predeterminada de la recepción** en la ubicación predeterminada que se creó previamente.</span><span class="sxs-lookup"><span data-stu-id="a9405-172">Set **Default receipt location** to the default location created above.</span></span>
    1. <span data-ttu-id="a9405-173">Establezca **Ubicación predeterminada de emisión** en la ubicación predeterminada que se creó previamente.</span><span class="sxs-lookup"><span data-stu-id="a9405-173">Select **Default issue location** to the default location created above.</span></span>
1. <span data-ttu-id="a9405-174">En la sección **Direcciones**, introduzca una dirección de almacén.</span><span class="sxs-lookup"><span data-stu-id="a9405-174">Under the **Addresses** section, enter a warehouse address.</span></span>
1. <span data-ttu-id="a9405-175">En la sección **Venta minorista**:</span><span class="sxs-lookup"><span data-stu-id="a9405-175">Under the **Retail** section:</span></span> 
    1. <span data-ttu-id="a9405-176">En el cuadro **Ubicación de devolución predeterminada**, introduzca la ubicación de devoluciones que creó previamente.</span><span class="sxs-lookup"><span data-stu-id="a9405-176">In the **Default return location** box, enter the returns location created previously.</span></span>
    1. <span data-ttu-id="a9405-177">Establezca **Tienda** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="a9405-177">Set **Store** to **Yes**.</span></span>
    1. <span data-ttu-id="a9405-178">Establezca **Peso** en **1,00**.</span><span class="sxs-lookup"><span data-stu-id="a9405-178">Set **Weight** to **1.00**.</span></span> 
    1. <span data-ttu-id="a9405-179">En el cuadro **Dimensiones de almacenamiento**, introduzca la ubicación predeterminada que creó previamente.</span><span class="sxs-lookup"><span data-stu-id="a9405-179">In the **Storage Dimensions** box, enter the default location created previously.</span></span>
1. <span data-ttu-id="a9405-180">En la sección **Almacén**, establezca **Inventario físico negativo** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="a9405-180">Under the **Warehouse** section, set **Physical negative inventory** to **Yes**.</span></span>
1. <span data-ttu-id="a9405-181">En el panel de acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="a9405-181">On the action pane, select **Save**.</span></span>

<span data-ttu-id="a9405-182">La siguiente imagen muestra los detalles de un almacén configurado.</span><span class="sxs-lookup"><span data-stu-id="a9405-182">The following image shows details for a configured warehouse.</span></span>

![Ejemplo de almacén configurado](media/warehouse-sample.png)

## <a name="additional-resources"></a><span data-ttu-id="a9405-184">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="a9405-184">Additional resources</span></span>

[<span data-ttu-id="a9405-185">Visión general de la gestión de almacenes</span><span class="sxs-lookup"><span data-stu-id="a9405-185">Warehouse management overview</span></span>](../supply-chain/warehousing/warehouse-management-overview.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="a9405-186">Resumen de canales</span><span class="sxs-lookup"><span data-stu-id="a9405-186">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="a9405-187">Requisitos previos de configuración de canales</span><span class="sxs-lookup"><span data-stu-id="a9405-187">Channel setup prerequisites</span></span>](channels-prerequisites.md)

[<span data-ttu-id="a9405-188">Configurar un canal comercial</span><span class="sxs-lookup"><span data-stu-id="a9405-188">Set up a retail channel</span></span>](channel-setup-retail.md)
    
[<span data-ttu-id="a9405-189">Configurar un canal en línea</span><span class="sxs-lookup"><span data-stu-id="a9405-189">Set up an online channel</span></span>](channel-setup-online.md)

[<span data-ttu-id="a9405-190">Configurar un canal de centro de llamadas</span><span class="sxs-lookup"><span data-stu-id="a9405-190">Set up a call center channel</span></span>](channel-setup-callcenter.md)







[!INCLUDE[footer-include](../includes/footer-banner.md)]
