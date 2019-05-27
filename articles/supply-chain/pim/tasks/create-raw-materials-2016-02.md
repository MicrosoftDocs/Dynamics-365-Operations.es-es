---
title: Crear materias primas (febrero de 2016)
description: Esta tarea tarea se centra en crear los componentes de productos terminados y semiterminados.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, EcoResProductCreate, InventItemOrderSetup, InventItemPrice
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 091b6edaf43e86e6e3665bf79871648473e284c7
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1552679"
---
# <a name="create-raw-materials-february-2016"></a><span data-ttu-id="08ebf-103">Crear materias primas (febrero de 2016)</span><span class="sxs-lookup"><span data-stu-id="08ebf-103">Create raw materials (February 2016)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="08ebf-104">Esta tarea tarea se centra en crear los componentes de productos terminados y semiterminados.</span><span class="sxs-lookup"><span data-stu-id="08ebf-104">This task focuses on creating the components of finished and semi-finished products.</span></span> <span data-ttu-id="08ebf-105">Es la tercera tarea en las series de cálculo BOM.</span><span class="sxs-lookup"><span data-stu-id="08ebf-105">It is the third task in the BOM calculation series.</span></span> <span data-ttu-id="08ebf-106">La empresa de datos de prueba utilizada para crear esta tarea es USMF.</span><span class="sxs-lookup"><span data-stu-id="08ebf-106">The demo data company used to create this task is USMF.</span></span>


## <a name="create-the-first-material"></a><span data-ttu-id="08ebf-107">Cree el primer material</span><span class="sxs-lookup"><span data-stu-id="08ebf-107">Create the first material</span></span>
1. <span data-ttu-id="08ebf-108">Vaya a Gestión de información de productos > Productos > Productos emitidos.</span><span class="sxs-lookup"><span data-stu-id="08ebf-108">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="08ebf-109">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="08ebf-109">Click New.</span></span>
3. <span data-ttu-id="08ebf-110">En el campo Número de producto, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="08ebf-110">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="08ebf-111">Para este ejemplo, escriba ITEM_A.</span><span class="sxs-lookup"><span data-stu-id="08ebf-111">For this example, enter ITEM_A.</span></span>  
4. <span data-ttu-id="08ebf-112">En el campo Grupo de modelos de artículo, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="08ebf-112">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="08ebf-113">Seleccione STD.</span><span class="sxs-lookup"><span data-stu-id="08ebf-113">Select STD.</span></span> <span data-ttu-id="08ebf-114">El STD representa el coste estándar y es el modelo más usado al trabajar con cálculos de coste.</span><span class="sxs-lookup"><span data-stu-id="08ebf-114">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
5. <span data-ttu-id="08ebf-115">En el campo Grupo de artículos, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="08ebf-115">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="08ebf-116">Por ejemplo, seleccione Audio.</span><span class="sxs-lookup"><span data-stu-id="08ebf-116">For example, select Audio.</span></span> <span data-ttu-id="08ebf-117">Esto no tiene aafecta de ninguna manera a los cálculos de coste.</span><span class="sxs-lookup"><span data-stu-id="08ebf-117">This has no impact on cost calculations.</span></span>  
6. <span data-ttu-id="08ebf-118">En el campo Grupo de dimensiones de almacenamiento, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="08ebf-118">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="08ebf-119">Seleccione SiteWH.</span><span class="sxs-lookup"><span data-stu-id="08ebf-119">Select SiteWH.</span></span> <span data-ttu-id="08ebf-120">Para la demostración solo se usarán el Sitio y el Almacén.</span><span class="sxs-lookup"><span data-stu-id="08ebf-120">Only Site and Warehouse will be used for the demonstration.</span></span>  
7. <span data-ttu-id="08ebf-121">En el campo Grupo de dimensiones de seguimiento, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="08ebf-121">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="08ebf-122">Las dimensiones de seguimiento no se usarán en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="08ebf-122">Tracking dimensions will not be used for this example.</span></span> <span data-ttu-id="08ebf-123">Seleccione Ninguno.</span><span class="sxs-lookup"><span data-stu-id="08ebf-123">Select None.</span></span>  
8. <span data-ttu-id="08ebf-124">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="08ebf-124">Click OK.</span></span>
9. <span data-ttu-id="08ebf-125">En el panel de acciones, haga clic en Administrar inventario.</span><span class="sxs-lookup"><span data-stu-id="08ebf-125">On the Action Pane, click Manage inventory.</span></span>
10. <span data-ttu-id="08ebf-126">Haga clic en Configuración predeterminada de pedido.</span><span class="sxs-lookup"><span data-stu-id="08ebf-126">Click Default order settings.</span></span>
11. <span data-ttu-id="08ebf-127">En el campo Sitio de compra, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="08ebf-127">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="08ebf-128">Para este ejemplo, seleccione Sitio 1.</span><span class="sxs-lookup"><span data-stu-id="08ebf-128">For this example, select Site 1.</span></span>  
12. <span data-ttu-id="08ebf-129">En el campo Sitio de inventario, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="08ebf-129">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="08ebf-130">Para este ejemplo, seleccione Sitio 1.</span><span class="sxs-lookup"><span data-stu-id="08ebf-130">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="08ebf-131">En el campo Sitio de centas, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="08ebf-131">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="08ebf-132">Para este ejemplo, seleccione Sitio 1.</span><span class="sxs-lookup"><span data-stu-id="08ebf-132">For this example, select Site 1.</span></span>  
14. <span data-ttu-id="08ebf-133">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="08ebf-133">Close the page.</span></span>
15. <span data-ttu-id="08ebf-134">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="08ebf-134">Close the page.</span></span>
16. <span data-ttu-id="08ebf-135">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="08ebf-135">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="08ebf-136">Haga clic en ITEM_A.</span><span class="sxs-lookup"><span data-stu-id="08ebf-136">Click ITEM_A.</span></span>  
17. <span data-ttu-id="08ebf-137">Expanda la sección Administrar costes.</span><span class="sxs-lookup"><span data-stu-id="08ebf-137">Expand the Manage costs section.</span></span>
18. <span data-ttu-id="08ebf-138">Introduzca un valor en el campo Grupo de costes.</span><span class="sxs-lookup"><span data-stu-id="08ebf-138">In the Cost group field, type a value.</span></span>
    * <span data-ttu-id="08ebf-139">Para este ejemplo, introduzca M2.</span><span class="sxs-lookup"><span data-stu-id="08ebf-139">For this example, type M2.</span></span>  
19. <span data-ttu-id="08ebf-140">En el panel de acciones, haga clic en Gestionar costes.</span><span class="sxs-lookup"><span data-stu-id="08ebf-140">On the Action Pane, click Manage costs.</span></span>
20. <span data-ttu-id="08ebf-141">Haga clic en Precio de artículo.</span><span class="sxs-lookup"><span data-stu-id="08ebf-141">Click Item price.</span></span>
21. <span data-ttu-id="08ebf-142">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="08ebf-142">Click New.</span></span>
22. <span data-ttu-id="08ebf-143">En el campo Versión, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="08ebf-143">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="08ebf-144">Para este ejemplo, seleccione 10, que es el Tipo de gestión de costes de coste estándar.</span><span class="sxs-lookup"><span data-stu-id="08ebf-144">For this example, select 10, which is the Standard cost costing type.</span></span>  
23. <span data-ttu-id="08ebf-145">En el campo Sitio, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="08ebf-145">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="08ebf-146">Para este ejemplo, seleccione Sitio 1.</span><span class="sxs-lookup"><span data-stu-id="08ebf-146">For this example, select Site 1.</span></span>  
24. <span data-ttu-id="08ebf-147">En el campo Precio, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="08ebf-147">In the Price field, enter a number.</span></span>
    * <span data-ttu-id="08ebf-148">Para este ejemplo, especifique 10.</span><span class="sxs-lookup"><span data-stu-id="08ebf-148">For this example, type 10.</span></span>  
25. <span data-ttu-id="08ebf-149">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="08ebf-149">Click Save.</span></span>
26. <span data-ttu-id="08ebf-150">Haga clic en Activar precios pendientes.</span><span class="sxs-lookup"><span data-stu-id="08ebf-150">Click Activate pending price(s).</span></span>
27. <span data-ttu-id="08ebf-151">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="08ebf-151">Close the page.</span></span>
28. <span data-ttu-id="08ebf-152">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="08ebf-152">Close the page.</span></span>

## <a name="create-the-second-material"></a><span data-ttu-id="08ebf-153">Cree el segundo material</span><span class="sxs-lookup"><span data-stu-id="08ebf-153">Create the second material</span></span>
1. <span data-ttu-id="08ebf-154">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="08ebf-154">Click New.</span></span>
2. <span data-ttu-id="08ebf-155">En el campo Número de producto, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="08ebf-155">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="08ebf-156">Para este ejemplo, especifique ITEM_B.</span><span class="sxs-lookup"><span data-stu-id="08ebf-156">For this example, type ITEM_B.</span></span>  
3. <span data-ttu-id="08ebf-157">En el campo Grupo de modelos de artículo, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="08ebf-157">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="08ebf-158">Seleccione STD.</span><span class="sxs-lookup"><span data-stu-id="08ebf-158">Select STD.</span></span> <span data-ttu-id="08ebf-159">El STD representa el coste estándar y es el modelo más usado al trabajar con cálculos de coste.</span><span class="sxs-lookup"><span data-stu-id="08ebf-159">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
4. <span data-ttu-id="08ebf-160">En el campo Grupo de artículos, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="08ebf-160">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="08ebf-161">Por ejemplo, seleccione Audio.</span><span class="sxs-lookup"><span data-stu-id="08ebf-161">For example, select Audio.</span></span> <span data-ttu-id="08ebf-162">Esto no tiene aafecta de ninguna manera a los cálculos de coste.</span><span class="sxs-lookup"><span data-stu-id="08ebf-162">This has no impact on cost calculations.</span></span>  
5. <span data-ttu-id="08ebf-163">En el campo Grupo de dimensiones de almacenamiento, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="08ebf-163">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="08ebf-164">Seleccione SiteWH.</span><span class="sxs-lookup"><span data-stu-id="08ebf-164">Select SiteWH.</span></span> <span data-ttu-id="08ebf-165">Para este ejemplo solo se usarán el Sitio y el Almacén.</span><span class="sxs-lookup"><span data-stu-id="08ebf-165">Only Site and Warehouse will be used for this example.</span></span>  
6. <span data-ttu-id="08ebf-166">En el campo Grupo de dimensiones de seguimiento, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="08ebf-166">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="08ebf-167">Las dimensiones de seguimiento no se usarán en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="08ebf-167">Tracking dimensions will not be used for this example.</span></span> <span data-ttu-id="08ebf-168">Seleccione Ninguno.</span><span class="sxs-lookup"><span data-stu-id="08ebf-168">Select None.</span></span>  
7. <span data-ttu-id="08ebf-169">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="08ebf-169">Click OK.</span></span>
8. <span data-ttu-id="08ebf-170">En el panel de acciones, haga clic en Administrar inventario.</span><span class="sxs-lookup"><span data-stu-id="08ebf-170">On the Action Pane, click Manage inventory.</span></span>
9. <span data-ttu-id="08ebf-171">Haga clic en Configuración predeterminada de pedido.</span><span class="sxs-lookup"><span data-stu-id="08ebf-171">Click Default order settings.</span></span>
10. <span data-ttu-id="08ebf-172">En el campo Sitio de compra, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="08ebf-172">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="08ebf-173">Para este ejemplo, seleccione Sitio 1.</span><span class="sxs-lookup"><span data-stu-id="08ebf-173">For this example, select Site 1.</span></span>  
11. <span data-ttu-id="08ebf-174">En el campo Sitio de inventario, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="08ebf-174">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="08ebf-175">Para este ejemplo, seleccione Sitio 1.</span><span class="sxs-lookup"><span data-stu-id="08ebf-175">For this example, select Site 1.</span></span>  
12. <span data-ttu-id="08ebf-176">En el campo Sitio de centas, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="08ebf-176">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="08ebf-177">Para este ejemplo, seleccione Sitio 1.</span><span class="sxs-lookup"><span data-stu-id="08ebf-177">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="08ebf-178">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="08ebf-178">Close the page.</span></span>
14. <span data-ttu-id="08ebf-179">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="08ebf-179">Close the page.</span></span>
15. <span data-ttu-id="08ebf-180">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="08ebf-180">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="08ebf-181">Haga clic en ITEM_B. </span><span class="sxs-lookup"><span data-stu-id="08ebf-181">Click ITEM_B.</span></span>  
16. <span data-ttu-id="08ebf-182">Expanda la sección Administrar costes.</span><span class="sxs-lookup"><span data-stu-id="08ebf-182">Expand the Manage costs section.</span></span>
17. <span data-ttu-id="08ebf-183">Introduzca un valor en el campo Grupo de costes.</span><span class="sxs-lookup"><span data-stu-id="08ebf-183">In the Cost group field, type a value.</span></span>
    * <span data-ttu-id="08ebf-184">Para este ejemplo, introduzca M2.</span><span class="sxs-lookup"><span data-stu-id="08ebf-184">For this example, type M2.</span></span>  
18. <span data-ttu-id="08ebf-185">En el panel de acciones, haga clic en Gestionar costes.</span><span class="sxs-lookup"><span data-stu-id="08ebf-185">On the Action Pane, click Manage costs.</span></span>
19. <span data-ttu-id="08ebf-186">Haga clic en Precio de artículo.</span><span class="sxs-lookup"><span data-stu-id="08ebf-186">Click Item price.</span></span>
20. <span data-ttu-id="08ebf-187">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="08ebf-187">Click New.</span></span>
21. <span data-ttu-id="08ebf-188">En el campo Versión, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="08ebf-188">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="08ebf-189">Para este ejemplo, seleccione 10.</span><span class="sxs-lookup"><span data-stu-id="08ebf-189">For this example, select 10.</span></span> <span data-ttu-id="08ebf-190">Este es el Tipo de gestión de costes de coste estándar.</span><span class="sxs-lookup"><span data-stu-id="08ebf-190">This is the Standard cost costing type.</span></span>  
22. <span data-ttu-id="08ebf-191">En el campo Sitio, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="08ebf-191">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="08ebf-192">Para este ejemplo, seleccione Sitio 1.</span><span class="sxs-lookup"><span data-stu-id="08ebf-192">For this example, select Site 1.</span></span>  
23. <span data-ttu-id="08ebf-193">En el campo Precio, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="08ebf-193">In the Price field, enter a number.</span></span>
    * <span data-ttu-id="08ebf-194">Para la demostración, especifique 10.</span><span class="sxs-lookup"><span data-stu-id="08ebf-194">For the demonstration, type 10.</span></span>  
24. <span data-ttu-id="08ebf-195">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="08ebf-195">Click Save.</span></span>
25. <span data-ttu-id="08ebf-196">Haga clic en Activar precios pendientes.</span><span class="sxs-lookup"><span data-stu-id="08ebf-196">Click Activate pending price(s).</span></span>
26. <span data-ttu-id="08ebf-197">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="08ebf-197">Close the page.</span></span>
27. <span data-ttu-id="08ebf-198">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="08ebf-198">Close the page.</span></span>

## <a name="create-the-third-material"></a><span data-ttu-id="08ebf-199">Cree el tercer material</span><span class="sxs-lookup"><span data-stu-id="08ebf-199">Create the third material</span></span>
1. <span data-ttu-id="08ebf-200">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="08ebf-200">Click New.</span></span>
2. <span data-ttu-id="08ebf-201">En el campo Número de producto, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="08ebf-201">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="08ebf-202">Para la demostración, especifique ITEM_C.</span><span class="sxs-lookup"><span data-stu-id="08ebf-202">For the demonstration, type ITEM_C</span></span>  
3. <span data-ttu-id="08ebf-203">En el campo Grupo de modelos de artículo, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="08ebf-203">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="08ebf-204">Seleccione STD.</span><span class="sxs-lookup"><span data-stu-id="08ebf-204">Select STD.</span></span> <span data-ttu-id="08ebf-205">El STD representa el coste estándar y es el modelo más usado al trabajar con cálculos de coste.</span><span class="sxs-lookup"><span data-stu-id="08ebf-205">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
4. <span data-ttu-id="08ebf-206">En el campo Grupo de artículos, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="08ebf-206">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="08ebf-207">Por ejemplo, seleccione Audio.</span><span class="sxs-lookup"><span data-stu-id="08ebf-207">For example, select Audio.</span></span> <span data-ttu-id="08ebf-208">Esto no tiene aafecta de ninguna manera a los cálculos de coste.</span><span class="sxs-lookup"><span data-stu-id="08ebf-208">This has no impact on cost calculations.</span></span>  
5. <span data-ttu-id="08ebf-209">En el campo Grupo de dimensiones de almacenamiento, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="08ebf-209">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="08ebf-210">Seleccione SiteWH.</span><span class="sxs-lookup"><span data-stu-id="08ebf-210">Select SiteWH.</span></span> <span data-ttu-id="08ebf-211">Para la demostración solo se usarán el Sitio y el Almacén.</span><span class="sxs-lookup"><span data-stu-id="08ebf-211">Only Site and Warehouse will be used for the demonstration.</span></span>  
6. <span data-ttu-id="08ebf-212">En el campo Grupo de dimensiones de seguimiento, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="08ebf-212">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="08ebf-213">Las dimensiones de seguimiento no se usarán en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="08ebf-213">Tracking dimensions will not be used for this example.</span></span> <span data-ttu-id="08ebf-214">Seleccione Ninguno.</span><span class="sxs-lookup"><span data-stu-id="08ebf-214">Select None.</span></span>  
7. <span data-ttu-id="08ebf-215">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="08ebf-215">Click OK.</span></span>
8. <span data-ttu-id="08ebf-216">En el panel de acciones, haga clic en Administrar inventario.</span><span class="sxs-lookup"><span data-stu-id="08ebf-216">On the Action Pane, click Manage inventory.</span></span>
9. <span data-ttu-id="08ebf-217">Haga clic en Configuración predeterminada de pedido.</span><span class="sxs-lookup"><span data-stu-id="08ebf-217">Click Default order settings.</span></span>
10. <span data-ttu-id="08ebf-218">En el campo Sitio de compra, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="08ebf-218">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="08ebf-219">Para este ejemplo, seleccione Sitio 1.</span><span class="sxs-lookup"><span data-stu-id="08ebf-219">For this example, select Site 1.</span></span>  
11. <span data-ttu-id="08ebf-220">En el campo Sitio de inventario, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="08ebf-220">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="08ebf-221">Para este ejemplo, seleccione Sitio 1.</span><span class="sxs-lookup"><span data-stu-id="08ebf-221">For this example, select Site 1.</span></span>  
12. <span data-ttu-id="08ebf-222">En el campo Sitio de centas, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="08ebf-222">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="08ebf-223">Para este ejemplo, seleccione Sitio 1.</span><span class="sxs-lookup"><span data-stu-id="08ebf-223">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="08ebf-224">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="08ebf-224">Close the page.</span></span>
14. <span data-ttu-id="08ebf-225">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="08ebf-225">Close the page.</span></span>
15. <span data-ttu-id="08ebf-226">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="08ebf-226">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="08ebf-227">Haga clic en ITEM_C. </span><span class="sxs-lookup"><span data-stu-id="08ebf-227">Click ITEM_C.</span></span>  
16. <span data-ttu-id="08ebf-228">Expanda la sección Administrar costes.</span><span class="sxs-lookup"><span data-stu-id="08ebf-228">Expand the Manage costs section.</span></span>
17. <span data-ttu-id="08ebf-229">Introduzca un valor en el campo Grupo de costes.</span><span class="sxs-lookup"><span data-stu-id="08ebf-229">In the Cost group field, type a value.</span></span>
    * <span data-ttu-id="08ebf-230">Para este ejemplo, especifique M1.</span><span class="sxs-lookup"><span data-stu-id="08ebf-230">For this example, type M1.</span></span>  
18. <span data-ttu-id="08ebf-231">En el panel de acciones, haga clic en Gestionar costes.</span><span class="sxs-lookup"><span data-stu-id="08ebf-231">On the Action Pane, click Manage costs.</span></span>
19. <span data-ttu-id="08ebf-232">Haga clic en Precio de artículo.</span><span class="sxs-lookup"><span data-stu-id="08ebf-232">Click Item price.</span></span>
20. <span data-ttu-id="08ebf-233">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="08ebf-233">Click New.</span></span>
21. <span data-ttu-id="08ebf-234">En el campo Versión, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="08ebf-234">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="08ebf-235">Para este ejemplo, seleccione 10.</span><span class="sxs-lookup"><span data-stu-id="08ebf-235">For this example, select 10.</span></span> <span data-ttu-id="08ebf-236">Este es el Tipo de gestión de costes de coste estándar.</span><span class="sxs-lookup"><span data-stu-id="08ebf-236">This is the Standard cost costing type.</span></span>  
22. <span data-ttu-id="08ebf-237">En el campo Sitio, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="08ebf-237">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="08ebf-238">Para este ejemplo, seleccione Sitio 1.</span><span class="sxs-lookup"><span data-stu-id="08ebf-238">For this example, select Site 1.</span></span>  
23. <span data-ttu-id="08ebf-239">En el campo Precio, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="08ebf-239">In the Price field, enter a number.</span></span>
    * <span data-ttu-id="08ebf-240">Para este ejemplo, especifique 10.</span><span class="sxs-lookup"><span data-stu-id="08ebf-240">For this example, type 10.</span></span>  
24. <span data-ttu-id="08ebf-241">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="08ebf-241">Click Save.</span></span>
25. <span data-ttu-id="08ebf-242">Haga clic en Activar precios pendientes.</span><span class="sxs-lookup"><span data-stu-id="08ebf-242">Click Activate pending price(s).</span></span>
26. <span data-ttu-id="08ebf-243">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="08ebf-243">Close the page.</span></span>
27. <span data-ttu-id="08ebf-244">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="08ebf-244">Close the page.</span></span>

