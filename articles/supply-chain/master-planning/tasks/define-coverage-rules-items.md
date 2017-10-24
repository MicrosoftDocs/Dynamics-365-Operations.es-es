--- 
title: "Definir reglas de cobertura para los artículos"
description: La empresa de datos de prueba utilizada para crear este procedimiento es USMF.
author: YuyuScheller
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 14f56c30753da9458d66a46da8935305619fd0b8
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="define-coverage-rules-for-items"></a><span data-ttu-id="98ffc-103">Definir reglas de cobertura para los artículos</span><span class="sxs-lookup"><span data-stu-id="98ffc-103">Define coverage rules for items</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="98ffc-104">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="98ffc-104">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="98ffc-105">Este procedimiento muestra cómo crear reglas de cobertura y anular opciones de cobertura para un artículo específico.</span><span class="sxs-lookup"><span data-stu-id="98ffc-105">This procedure shows how to create coverage rules and override coverage settings for a specific item.</span></span> <span data-ttu-id="98ffc-106">También se muestra cómo especificar parámetros de inventario predeterminados.</span><span class="sxs-lookup"><span data-stu-id="98ffc-106">It also shows how to specify default inventory settings.</span></span>


## <a name="create-a-coverage-group"></a><span data-ttu-id="98ffc-107">Crear un grupo de cobertura</span><span class="sxs-lookup"><span data-stu-id="98ffc-107">Create a coverage group</span></span>
1. <span data-ttu-id="98ffc-108">Vaya a Grupos de cobertura.</span><span class="sxs-lookup"><span data-stu-id="98ffc-108">Go to Coverage groups.</span></span>
2. <span data-ttu-id="98ffc-109">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="98ffc-109">Click New.</span></span>
3. <span data-ttu-id="98ffc-110">En el campo Grupo de cobertura, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="98ffc-110">In the Coverage group field, type a value.</span></span>
4. <span data-ttu-id="98ffc-111">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="98ffc-111">In the Name field, type a value.</span></span>
5. <span data-ttu-id="98ffc-112">En el campo Calendario, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="98ffc-112">In the Calendar field, type a value.</span></span>
    * <span data-ttu-id="98ffc-113">Elija el calendario que utiliza la planificación maestra para crear sugerencias de reabastecimiento para los artículos en el grupo.</span><span class="sxs-lookup"><span data-stu-id="98ffc-113">Choose the calendar that master planning uses to create replenishment suggestions for items in this group.</span></span>  
6. <span data-ttu-id="98ffc-114">En el campo Código de cobertura, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="98ffc-114">In the Coverage code field, select an option.</span></span>
    * <span data-ttu-id="98ffc-115">Seleccione Requisito para este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="98ffc-115">Select Requirement for this procedure.</span></span>  
7. <span data-ttu-id="98ffc-116">En el campo Límite de tiempo de cobertura (días), escriba "90".</span><span class="sxs-lookup"><span data-stu-id="98ffc-116">In the Coverage time fence (days) field, enter '90'.</span></span>
    * <span data-ttu-id="98ffc-117">Para los artículos de este grupo, la planificación maestra creará las sugerencias de reabastecimiento de hasta 90 días en el futuro.</span><span class="sxs-lookup"><span data-stu-id="98ffc-117">For items in this group, master planning will create replenishment suggestions for up to 90 days in the future.</span></span>  
8. <span data-ttu-id="98ffc-118">En el campo Días negativos, especifique “1".</span><span class="sxs-lookup"><span data-stu-id="98ffc-118">In the Negative days field, enter '1'.</span></span>
9. <span data-ttu-id="98ffc-119">En el campo Días positivos, especifique “1".</span><span class="sxs-lookup"><span data-stu-id="98ffc-119">In the Positive days field, enter '1'.</span></span>
10. <span data-ttu-id="98ffc-120">Expanda o contraiga la sección Otros.</span><span class="sxs-lookup"><span data-stu-id="98ffc-120">Expand or collapse the Other section.</span></span>
11. <span data-ttu-id="98ffc-121">En el campo Días de recepción sumados a la fecha de requisito, especifique “1".</span><span class="sxs-lookup"><span data-stu-id="98ffc-121">In the Receipt margin added to requirement date field, enter '1'.</span></span>
    * <span data-ttu-id="98ffc-122">Por ejemplo, si el margen de recepción se establece en 1 día y se programa la recepción de una línea de pedido de compra para el 15 de mayo, la planificación maestra calcula la fecha de recepción ajustada como el 16 de mayo.</span><span class="sxs-lookup"><span data-stu-id="98ffc-122">For example, if the receipt margin is set to 1 day, and a purchase order line is scheduled for receipt on May 15, master planning calculates the adjusted receipt date as May 16.</span></span>  
12. <span data-ttu-id="98ffc-123">En el campo Días de emisión deducidos de la fecha de requisito, especifique “1".</span><span class="sxs-lookup"><span data-stu-id="98ffc-123">In the Issue margin deducted from requirement date field, enter '1'.</span></span>
    * <span data-ttu-id="98ffc-124">Por ejemplo, si el margen de seguridad se establece en 1 día y se programa la entrega de una línea del pedido de ventas para el 15 de mayo, la programación maestra calcula la fecha de entrega ajustada como el 14 de mayo.</span><span class="sxs-lookup"><span data-stu-id="98ffc-124">For example, if the safety margin is set to 1 day, and a sales order line is scheduled for delivery on May 15, master scheduling calculates the adjusted delivery date as May 14.</span></span>  
13. <span data-ttu-id="98ffc-125">En el campo Días de administración agregados al plazo del artículo, especifique “1".</span><span class="sxs-lookup"><span data-stu-id="98ffc-125">In the Reorder margin added to item lead time field, enter '1'.</span></span>
14. <span data-ttu-id="98ffc-126">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="98ffc-126">Click Save.</span></span>

## <a name="create-a-new-product"></a><span data-ttu-id="98ffc-127">Crear un nuevo producto</span><span class="sxs-lookup"><span data-stu-id="98ffc-127">Create a new product</span></span>
1. <span data-ttu-id="98ffc-128">Vaya a Productos emitidos.</span><span class="sxs-lookup"><span data-stu-id="98ffc-128">Go to Released products.</span></span>
2. <span data-ttu-id="98ffc-129">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="98ffc-129">Click New.</span></span>
3. <span data-ttu-id="98ffc-130">En el campo Número de producto, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="98ffc-130">In the Product number field, type a value.</span></span>
4. <span data-ttu-id="98ffc-131">En el campo Nombre de producto, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="98ffc-131">In the Product name field, type a value.</span></span>
5. <span data-ttu-id="98ffc-132">En el campo Grupo de modelos de artículo, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="98ffc-132">In the Item model group field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="98ffc-133">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="98ffc-133">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="98ffc-134">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="98ffc-134">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="98ffc-135">En el campo Grupo de artículos, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="98ffc-135">In the Item group field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="98ffc-136">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="98ffc-136">In the list, find and select the desired record.</span></span>
10. <span data-ttu-id="98ffc-137">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="98ffc-137">In the list, click the link in the selected row.</span></span>
11. <span data-ttu-id="98ffc-138">En el campo Grupo de dimensiones de almacenamiento, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="98ffc-138">In the Storage dimension group field, click the drop-down button to open the lookup.</span></span>
12. <span data-ttu-id="98ffc-139">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="98ffc-139">In the list, find and select the desired record.</span></span>
13. <span data-ttu-id="98ffc-140">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="98ffc-140">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="98ffc-141">En el campo Grupo de dimensiones de seguimiento, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="98ffc-141">In the Tracking dimension group field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="98ffc-142">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="98ffc-142">In the list, find and select the desired record.</span></span>
16. <span data-ttu-id="98ffc-143">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="98ffc-143">In the list, click the link in the selected row.</span></span>
17. <span data-ttu-id="98ffc-144">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="98ffc-144">Click OK.</span></span>

## <a name="setup-default-order-settings"></a><span data-ttu-id="98ffc-145">Configuración de ajustes predeterminados de pedido</span><span class="sxs-lookup"><span data-stu-id="98ffc-145">Setup default order settings</span></span>
1. <span data-ttu-id="98ffc-146">En el panel de acciones, haga clic en Plan.</span><span class="sxs-lookup"><span data-stu-id="98ffc-146">On the Action Pane, click Plan.</span></span>
2. <span data-ttu-id="98ffc-147">Haga clic en Configuración predeterminada de pedido.</span><span class="sxs-lookup"><span data-stu-id="98ffc-147">Click Default order settings.</span></span>
3. <span data-ttu-id="98ffc-148">En el campo Sitio de compras, escriba el sitio usado como predeterminado cuando se crean los pedidos de compra.</span><span class="sxs-lookup"><span data-stu-id="98ffc-148">In the Purchase site field, type the site used as default when purchase orders are created.</span></span>
4. <span data-ttu-id="98ffc-149">En el campo Sitio de inventario, escriba el sitio donde está almacenado el artículo.</span><span class="sxs-lookup"><span data-stu-id="98ffc-149">In the Inventory site field, type the site where the item is stored.</span></span>
5. <span data-ttu-id="98ffc-150">Expanda o contraiga la sección Inventario.</span><span class="sxs-lookup"><span data-stu-id="98ffc-150">Expand or collapse the Inventory section.</span></span>
6. <span data-ttu-id="98ffc-151">Establezca Múltiplo en “10".</span><span class="sxs-lookup"><span data-stu-id="98ffc-151">Set Multiple to '10'.</span></span>
7. <span data-ttu-id="98ffc-152">Establezca Cantidad mínima</span><span class="sxs-lookup"><span data-stu-id="98ffc-152">Set Min.</span></span> <span data-ttu-id="98ffc-153">de pedido en "10".</span><span class="sxs-lookup"><span data-stu-id="98ffc-153">order quantity to '10'.</span></span>
8. <span data-ttu-id="98ffc-154">Establezca Cantidad máxima</span><span class="sxs-lookup"><span data-stu-id="98ffc-154">Set Max.</span></span> <span data-ttu-id="98ffc-155">de pedido en "100".</span><span class="sxs-lookup"><span data-stu-id="98ffc-155">order quantity to '100'.</span></span>
9. <span data-ttu-id="98ffc-156">Establezca Cantidad de pedido estándar en "10".</span><span class="sxs-lookup"><span data-stu-id="98ffc-156">Set Standard order quantity to '10'.</span></span>
10. <span data-ttu-id="98ffc-157">En el campo Plazo de compra, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="98ffc-157">In the Purchase lead time field, enter a number.</span></span>
11. <span data-ttu-id="98ffc-158">Active o desactive la casilla Días laborales.</span><span class="sxs-lookup"><span data-stu-id="98ffc-158">Select or clear the Working days check box.</span></span>
12. <span data-ttu-id="98ffc-159">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="98ffc-159">Click Save.</span></span>
13. <span data-ttu-id="98ffc-160">En el campo Tipo de pedido predeterminado, seleccione "Pedido de compra".</span><span class="sxs-lookup"><span data-stu-id="98ffc-160">In the Default order type field select 'Purchase order'.</span></span>
14. <span data-ttu-id="98ffc-161">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="98ffc-161">Click Save.</span></span>
15. <span data-ttu-id="98ffc-162">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="98ffc-162">Close the page.</span></span>
    * <span data-ttu-id="98ffc-163">Cierre la página Configuración predeterminada de pedido.</span><span class="sxs-lookup"><span data-stu-id="98ffc-163">Close the Default order settings page.</span></span>  

## <a name="add-an-item-to-a-coverage-group"></a><span data-ttu-id="98ffc-164">Agregar un artículo a un grupo de cobertura</span><span class="sxs-lookup"><span data-stu-id="98ffc-164">Add an item to a coverage group</span></span>
1. <span data-ttu-id="98ffc-165">Expanda o contraiga la sección Plan.</span><span class="sxs-lookup"><span data-stu-id="98ffc-165">Expand or collapse the Plan section.</span></span>
2. <span data-ttu-id="98ffc-166">En el campo Grupo de cobertura, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="98ffc-166">In the Coverage group field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="98ffc-167">En la lista, busque el grupo de cobertura que ha creado.</span><span class="sxs-lookup"><span data-stu-id="98ffc-167">In the list, find the Coverage group you have created.</span></span>
4. <span data-ttu-id="98ffc-168">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="98ffc-168">In the list, click the link in the selected row.</span></span>

## <a name="create-item-coverage-rules"></a><span data-ttu-id="98ffc-169">Crear reglas de cobertura de artículos</span><span class="sxs-lookup"><span data-stu-id="98ffc-169">Create item coverage rules</span></span>
1. <span data-ttu-id="98ffc-170">En el panel de acciones, haga clic en Plan.</span><span class="sxs-lookup"><span data-stu-id="98ffc-170">On the Action Pane, click Plan.</span></span>
2. <span data-ttu-id="98ffc-171">Haga clic en Cobertura de artículos.</span><span class="sxs-lookup"><span data-stu-id="98ffc-171">Click Item coverage.</span></span>
3. <span data-ttu-id="98ffc-172">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="98ffc-172">Click New.</span></span>
4. <span data-ttu-id="98ffc-173">Haga clic en la pestaña General.</span><span class="sxs-lookup"><span data-stu-id="98ffc-173">Click the General tab.</span></span>
5. <span data-ttu-id="98ffc-174">Marque la casilla en el encabezado de Anular configuración de grupo de cobertura.</span><span class="sxs-lookup"><span data-stu-id="98ffc-174">Check the box on the header of Override coverage group settings.</span></span>
6. <span data-ttu-id="98ffc-175">En el campo Límite de tiempo de cobertura (días), escriba "60".</span><span class="sxs-lookup"><span data-stu-id="98ffc-175">In the Coverage time fence (days) field, enter '60'.</span></span>
    * <span data-ttu-id="98ffc-176">Aunque los artículos del grupo de cobertura Requisito se planifiquen con 90 días de adelanto, este artículo se planea con 60 días de adelanto.</span><span class="sxs-lookup"><span data-stu-id="98ffc-176">Although items in coverage group Requiremen are planned 90 days ahead, this item will be planned 60 days ahead.</span></span>  
7. <span data-ttu-id="98ffc-177">En el campo Días negativos, especifique “2".</span><span class="sxs-lookup"><span data-stu-id="98ffc-177">In the Negative days field, enter '2'.</span></span>
8. <span data-ttu-id="98ffc-178">En el campo Días positivos, especifique “2".</span><span class="sxs-lookup"><span data-stu-id="98ffc-178">In the Positive days field, enter '2'.</span></span>
9. <span data-ttu-id="98ffc-179">Haga clic en la pestaña Plazo.</span><span class="sxs-lookup"><span data-stu-id="98ffc-179">Click the Lead time tab.</span></span>
10. <span data-ttu-id="98ffc-180">Marque la casilla en el encabezado de Compra.</span><span class="sxs-lookup"><span data-stu-id="98ffc-180">Check the box on the header of Purchase.</span></span>
11. <span data-ttu-id="98ffc-181">En el campo Hora de compra, especifique "5".</span><span class="sxs-lookup"><span data-stu-id="98ffc-181">In the Purchase time field, enter '5'.</span></span>
12. <span data-ttu-id="98ffc-182">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="98ffc-182">Click Save.</span></span>


