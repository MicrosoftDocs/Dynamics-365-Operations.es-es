--- 
title: "Crear materias primas (febrero de 2016 únicamente)"
description: Esta tarea tarea se centra en crear los componentes de productos terminados y semiterminados.
author: YuyuScheller
manager: AnnBe
ms.date: 02/07/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Operations
ms.search.region: Global
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 3d77dcc20fe7402af83dd724e7fef848977e5bf8
ms.openlocfilehash: f6af7b93d8d1d9a6f7474f24177b16e5295e90d6
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="create-raw-materials-february-2016-only"></a><span data-ttu-id="0077e-103">Crear materias primas (febrero de 2016 únicamente)</span><span class="sxs-lookup"><span data-stu-id="0077e-103">Create raw materials (February 2016 only)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="0077e-104">Esta tarea tarea se centra en crear los componentes de productos terminados y semiterminados.</span><span class="sxs-lookup"><span data-stu-id="0077e-104">This task focuses on creating the components of finished and semi-finished products.</span></span> <span data-ttu-id="0077e-105">Es la tercera tarea en las series de cálculo BOM.</span><span class="sxs-lookup"><span data-stu-id="0077e-105">It is the third task in the BOM calculation series.</span></span> <span data-ttu-id="0077e-106">La empresa de datos de prueba utilizada para crear esta tarea es USMF.</span><span class="sxs-lookup"><span data-stu-id="0077e-106">The demo data company used to create this task is USMF.</span></span>


## <a name="create-the-first-material"></a><span data-ttu-id="0077e-107">Cree el primer material</span><span class="sxs-lookup"><span data-stu-id="0077e-107">Create the first material</span></span>
1. <span data-ttu-id="0077e-108">Vaya a Gestión de información de productos > Productos > Productos emitidos.</span><span class="sxs-lookup"><span data-stu-id="0077e-108">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="0077e-109">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="0077e-109">Click New.</span></span>
3. <span data-ttu-id="0077e-110">En el campo Número de producto, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="0077e-110">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="0077e-111">Para este ejemplo, escriba ITEM_A.</span><span class="sxs-lookup"><span data-stu-id="0077e-111">For this example, enter ITEM_A.</span></span>  
4. <span data-ttu-id="0077e-112">En el campo Grupo de modelos de artículo, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="0077e-112">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="0077e-113">Seleccione STD.</span><span class="sxs-lookup"><span data-stu-id="0077e-113">Select STD.</span></span> <span data-ttu-id="0077e-114">El STD representa el coste estándar y es el modelo más usado al trabajar con cálculos de coste.</span><span class="sxs-lookup"><span data-stu-id="0077e-114">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
5. <span data-ttu-id="0077e-115">En el campo Grupo de artículos, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="0077e-115">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="0077e-116">Por ejemplo, seleccione Audio.</span><span class="sxs-lookup"><span data-stu-id="0077e-116">For example, select Audio.</span></span> <span data-ttu-id="0077e-117">Esto no tiene aafecta de ninguna manera a los cálculos de coste.</span><span class="sxs-lookup"><span data-stu-id="0077e-117">This has no impact on cost calculations.</span></span>  
6. <span data-ttu-id="0077e-118">En el campo Grupo de dimensiones de almacenamiento, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="0077e-118">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="0077e-119">Seleccione SiteWH.</span><span class="sxs-lookup"><span data-stu-id="0077e-119">Select SiteWH.</span></span> <span data-ttu-id="0077e-120">Para la demostración solo se usarán el Sitio y el Almacén.</span><span class="sxs-lookup"><span data-stu-id="0077e-120">Only Site and Warehouse will be used for the demonstration.</span></span>  
7. <span data-ttu-id="0077e-121">En el campo Grupo de dimensiones de seguimiento, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="0077e-121">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="0077e-122">Las dimensiones de seguimiento no se usarán en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="0077e-122">Tracking dimensions will not be used for this example.</span></span> <span data-ttu-id="0077e-123">Seleccione Ninguno.</span><span class="sxs-lookup"><span data-stu-id="0077e-123">Select None.</span></span>  
8. <span data-ttu-id="0077e-124">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="0077e-124">Click OK.</span></span>
9. <span data-ttu-id="0077e-125">En el panel de acciones, haga clic en Administrar inventario.</span><span class="sxs-lookup"><span data-stu-id="0077e-125">On the Action Pane, click Manage inventory.</span></span>
10. <span data-ttu-id="0077e-126">Haga clic en Configuración predeterminada de pedido.</span><span class="sxs-lookup"><span data-stu-id="0077e-126">Click Default order settings.</span></span>
11. <span data-ttu-id="0077e-127">En el campo Sitio de compra, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="0077e-127">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="0077e-128">Para este ejemplo, seleccione Sitio 1.</span><span class="sxs-lookup"><span data-stu-id="0077e-128">For this example, select Site 1.</span></span>  
12. <span data-ttu-id="0077e-129">En el campo Sitio de inventario, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="0077e-129">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="0077e-130">Para este ejemplo, seleccione Sitio 1.</span><span class="sxs-lookup"><span data-stu-id="0077e-130">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="0077e-131">En el campo Sitio de centas, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="0077e-131">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="0077e-132">Para este ejemplo, seleccione Sitio 1.</span><span class="sxs-lookup"><span data-stu-id="0077e-132">For this example, select Site 1.</span></span>  
14. <span data-ttu-id="0077e-133">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="0077e-133">Close the page.</span></span>
15. <span data-ttu-id="0077e-134">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="0077e-134">Close the page.</span></span>
16. <span data-ttu-id="0077e-135">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="0077e-135">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="0077e-136">Haga clic en ITEM_A.</span><span class="sxs-lookup"><span data-stu-id="0077e-136">Click ITEM_A.</span></span>  
17. <span data-ttu-id="0077e-137">Expanda la sección Administrar costes.</span><span class="sxs-lookup"><span data-stu-id="0077e-137">Expand the Manage costs section.</span></span>
18. <span data-ttu-id="0077e-138">Introduzca un valor en el campo Grupo de costes.</span><span class="sxs-lookup"><span data-stu-id="0077e-138">In the Cost group field, type a value.</span></span>
    * <span data-ttu-id="0077e-139">Para este ejemplo, introduzca M2.</span><span class="sxs-lookup"><span data-stu-id="0077e-139">For this example, type M2.</span></span>  
19. <span data-ttu-id="0077e-140">En el panel de acciones, haga clic en Gestionar costes.</span><span class="sxs-lookup"><span data-stu-id="0077e-140">On the Action Pane, click Manage costs.</span></span>
20. <span data-ttu-id="0077e-141">Haga clic en Precio de artículo.</span><span class="sxs-lookup"><span data-stu-id="0077e-141">Click Item price.</span></span>
21. <span data-ttu-id="0077e-142">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="0077e-142">Click New.</span></span>
22. <span data-ttu-id="0077e-143">En el campo Versión, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="0077e-143">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="0077e-144">Para este ejemplo, seleccione 10, que es el Tipo de gestión de costes de coste estándar.</span><span class="sxs-lookup"><span data-stu-id="0077e-144">For this example, select 10, which is the Standard cost costing type.</span></span>  
23. <span data-ttu-id="0077e-145">En el campo Sitio, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="0077e-145">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="0077e-146">Para este ejemplo, seleccione Sitio 1.</span><span class="sxs-lookup"><span data-stu-id="0077e-146">For this example, select Site 1.</span></span>  
24. <span data-ttu-id="0077e-147">En el campo Precio, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="0077e-147">In the Price field, enter a number.</span></span>
    * <span data-ttu-id="0077e-148">Para este ejemplo, especifique 10.</span><span class="sxs-lookup"><span data-stu-id="0077e-148">For this example, type 10.</span></span>  
25. <span data-ttu-id="0077e-149">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="0077e-149">Click Save.</span></span>
26. <span data-ttu-id="0077e-150">Haga clic en Activar precios pendientes.</span><span class="sxs-lookup"><span data-stu-id="0077e-150">Click Activate pending price(s).</span></span>
27. <span data-ttu-id="0077e-151">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="0077e-151">Close the page.</span></span>
28. <span data-ttu-id="0077e-152">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="0077e-152">Close the page.</span></span>

## <a name="create-the-second-material"></a><span data-ttu-id="0077e-153">Cree el segundo material</span><span class="sxs-lookup"><span data-stu-id="0077e-153">Create the second material</span></span>
1. <span data-ttu-id="0077e-154">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="0077e-154">Click New.</span></span>
2. <span data-ttu-id="0077e-155">En el campo Número de producto, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="0077e-155">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="0077e-156">Para este ejemplo, especifique ITEM_B.</span><span class="sxs-lookup"><span data-stu-id="0077e-156">For this example, type ITEM_B.</span></span>  
3. <span data-ttu-id="0077e-157">En el campo Grupo de modelos de artículo, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="0077e-157">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="0077e-158">Seleccione STD.</span><span class="sxs-lookup"><span data-stu-id="0077e-158">Select STD.</span></span> <span data-ttu-id="0077e-159">El STD representa el coste estándar y es el modelo más usado al trabajar con cálculos de coste.</span><span class="sxs-lookup"><span data-stu-id="0077e-159">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
4. <span data-ttu-id="0077e-160">En el campo Grupo de artículos, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="0077e-160">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="0077e-161">Por ejemplo, seleccione Audio.</span><span class="sxs-lookup"><span data-stu-id="0077e-161">For example, select Audio.</span></span> <span data-ttu-id="0077e-162">Esto no tiene aafecta de ninguna manera a los cálculos de coste.</span><span class="sxs-lookup"><span data-stu-id="0077e-162">This has no impact on cost calculations.</span></span>  
5. <span data-ttu-id="0077e-163">En el campo Grupo de dimensiones de almacenamiento, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="0077e-163">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="0077e-164">Seleccione SiteWH.</span><span class="sxs-lookup"><span data-stu-id="0077e-164">Select SiteWH.</span></span> <span data-ttu-id="0077e-165">Para este ejemplo solo se usarán el Sitio y el Almacén.</span><span class="sxs-lookup"><span data-stu-id="0077e-165">Only Site and Warehouse will be used for this example.</span></span>  
6. <span data-ttu-id="0077e-166">En el campo Grupo de dimensiones de seguimiento, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="0077e-166">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="0077e-167">Las dimensiones de seguimiento no se usarán en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="0077e-167">Tracking dimensions will not be used for this example.</span></span> <span data-ttu-id="0077e-168">Seleccione Ninguno.</span><span class="sxs-lookup"><span data-stu-id="0077e-168">Select None.</span></span>  
7. <span data-ttu-id="0077e-169">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="0077e-169">Click OK.</span></span>
8. <span data-ttu-id="0077e-170">En el panel de acciones, haga clic en Administrar inventario.</span><span class="sxs-lookup"><span data-stu-id="0077e-170">On the Action Pane, click Manage inventory.</span></span>
9. <span data-ttu-id="0077e-171">Haga clic en Configuración predeterminada de pedido.</span><span class="sxs-lookup"><span data-stu-id="0077e-171">Click Default order settings.</span></span>
10. <span data-ttu-id="0077e-172">En el campo Sitio de compra, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="0077e-172">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="0077e-173">Para este ejemplo, seleccione Sitio 1.</span><span class="sxs-lookup"><span data-stu-id="0077e-173">For this example, select Site 1.</span></span>  
11. <span data-ttu-id="0077e-174">En el campo Sitio de inventario, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="0077e-174">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="0077e-175">Para este ejemplo, seleccione Sitio 1.</span><span class="sxs-lookup"><span data-stu-id="0077e-175">For this example, select Site 1.</span></span>  
12. <span data-ttu-id="0077e-176">En el campo Sitio de centas, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="0077e-176">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="0077e-177">Para este ejemplo, seleccione Sitio 1.</span><span class="sxs-lookup"><span data-stu-id="0077e-177">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="0077e-178">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="0077e-178">Close the page.</span></span>
14. <span data-ttu-id="0077e-179">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="0077e-179">Close the page.</span></span>
15. <span data-ttu-id="0077e-180">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="0077e-180">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="0077e-181">Haga clic en ITEM_B. </span><span class="sxs-lookup"><span data-stu-id="0077e-181">Click ITEM_B.</span></span>  
16. <span data-ttu-id="0077e-182">Expanda la sección Administrar costes.</span><span class="sxs-lookup"><span data-stu-id="0077e-182">Expand the Manage costs section.</span></span>
17. <span data-ttu-id="0077e-183">Introduzca un valor en el campo Grupo de costes.</span><span class="sxs-lookup"><span data-stu-id="0077e-183">In the Cost group field, type a value.</span></span>
    * <span data-ttu-id="0077e-184">Para este ejemplo, introduzca M2.</span><span class="sxs-lookup"><span data-stu-id="0077e-184">For this example, type M2.</span></span>  
18. <span data-ttu-id="0077e-185">En el panel de acciones, haga clic en Gestionar costes.</span><span class="sxs-lookup"><span data-stu-id="0077e-185">On the Action Pane, click Manage costs.</span></span>
19. <span data-ttu-id="0077e-186">Haga clic en Precio de artículo.</span><span class="sxs-lookup"><span data-stu-id="0077e-186">Click Item price.</span></span>
20. <span data-ttu-id="0077e-187">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="0077e-187">Click New.</span></span>
21. <span data-ttu-id="0077e-188">En el campo Versión, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="0077e-188">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="0077e-189">Para este ejemplo, seleccione 10.</span><span class="sxs-lookup"><span data-stu-id="0077e-189">For this example, select 10.</span></span> <span data-ttu-id="0077e-190">Este es el Tipo de gestión de costes de coste estándar.</span><span class="sxs-lookup"><span data-stu-id="0077e-190">This is the Standard cost costing type.</span></span>  
22. <span data-ttu-id="0077e-191">En el campo Sitio, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="0077e-191">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="0077e-192">Para este ejemplo, seleccione Sitio 1.</span><span class="sxs-lookup"><span data-stu-id="0077e-192">For this example, select Site 1.</span></span>  
23. <span data-ttu-id="0077e-193">En el campo Precio, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="0077e-193">In the Price field, enter a number.</span></span>
    * <span data-ttu-id="0077e-194">Para la demostración, especifique 10.</span><span class="sxs-lookup"><span data-stu-id="0077e-194">For the demonstration, type 10.</span></span>  
24. <span data-ttu-id="0077e-195">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="0077e-195">Click Save.</span></span>
25. <span data-ttu-id="0077e-196">Haga clic en Activar precios pendientes.</span><span class="sxs-lookup"><span data-stu-id="0077e-196">Click Activate pending price(s).</span></span>
26. <span data-ttu-id="0077e-197">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="0077e-197">Close the page.</span></span>
27. <span data-ttu-id="0077e-198">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="0077e-198">Close the page.</span></span>

## <a name="create-the-third-material"></a><span data-ttu-id="0077e-199">Cree el tercer material</span><span class="sxs-lookup"><span data-stu-id="0077e-199">Create the third material</span></span>
1. <span data-ttu-id="0077e-200">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="0077e-200">Click New.</span></span>
2. <span data-ttu-id="0077e-201">En el campo Número de producto, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="0077e-201">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="0077e-202">Para la demostración, especifique ITEM_C.</span><span class="sxs-lookup"><span data-stu-id="0077e-202">For the demonstration, type ITEM_C</span></span>  
3. <span data-ttu-id="0077e-203">En el campo Grupo de modelos de artículo, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="0077e-203">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="0077e-204">Seleccione STD.</span><span class="sxs-lookup"><span data-stu-id="0077e-204">Select STD.</span></span> <span data-ttu-id="0077e-205">El STD representa el coste estándar y es el modelo más usado al trabajar con cálculos de coste.</span><span class="sxs-lookup"><span data-stu-id="0077e-205">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
4. <span data-ttu-id="0077e-206">En el campo Grupo de artículos, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="0077e-206">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="0077e-207">Por ejemplo, seleccione Audio.</span><span class="sxs-lookup"><span data-stu-id="0077e-207">For example, select Audio.</span></span> <span data-ttu-id="0077e-208">Esto no tiene aafecta de ninguna manera a los cálculos de coste.</span><span class="sxs-lookup"><span data-stu-id="0077e-208">This has no impact on cost calculations.</span></span>  
5. <span data-ttu-id="0077e-209">En el campo Grupo de dimensiones de almacenamiento, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="0077e-209">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="0077e-210">Seleccione SiteWH.</span><span class="sxs-lookup"><span data-stu-id="0077e-210">Select SiteWH.</span></span> <span data-ttu-id="0077e-211">Para la demostración solo se usarán el Sitio y el Almacén.</span><span class="sxs-lookup"><span data-stu-id="0077e-211">Only Site and Warehouse will be used for the demonstration.</span></span>  
6. <span data-ttu-id="0077e-212">En el campo Grupo de dimensiones de seguimiento, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="0077e-212">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="0077e-213">Las dimensiones de seguimiento no se usarán en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="0077e-213">Tracking dimensions will not be used for this example.</span></span> <span data-ttu-id="0077e-214">Seleccione Ninguno.</span><span class="sxs-lookup"><span data-stu-id="0077e-214">Select None.</span></span>  
7. <span data-ttu-id="0077e-215">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="0077e-215">Click OK.</span></span>
8. <span data-ttu-id="0077e-216">En el panel de acciones, haga clic en Administrar inventario.</span><span class="sxs-lookup"><span data-stu-id="0077e-216">On the Action Pane, click Manage inventory.</span></span>
9. <span data-ttu-id="0077e-217">Haga clic en Configuración predeterminada de pedido.</span><span class="sxs-lookup"><span data-stu-id="0077e-217">Click Default order settings.</span></span>
10. <span data-ttu-id="0077e-218">En el campo Sitio de compra, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="0077e-218">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="0077e-219">Para este ejemplo, seleccione Sitio 1.</span><span class="sxs-lookup"><span data-stu-id="0077e-219">For this example, select Site 1.</span></span>  
11. <span data-ttu-id="0077e-220">En el campo Sitio de inventario, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="0077e-220">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="0077e-221">Para este ejemplo, seleccione Sitio 1.</span><span class="sxs-lookup"><span data-stu-id="0077e-221">For this example, select Site 1.</span></span>  
12. <span data-ttu-id="0077e-222">En el campo Sitio de centas, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="0077e-222">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="0077e-223">Para este ejemplo, seleccione Sitio 1.</span><span class="sxs-lookup"><span data-stu-id="0077e-223">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="0077e-224">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="0077e-224">Close the page.</span></span>
14. <span data-ttu-id="0077e-225">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="0077e-225">Close the page.</span></span>
15. <span data-ttu-id="0077e-226">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="0077e-226">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="0077e-227">Haga clic en ITEM_C. </span><span class="sxs-lookup"><span data-stu-id="0077e-227">Click ITEM_C.</span></span>  
16. <span data-ttu-id="0077e-228">Expanda la sección Administrar costes.</span><span class="sxs-lookup"><span data-stu-id="0077e-228">Expand the Manage costs section.</span></span>
17. <span data-ttu-id="0077e-229">Introduzca un valor en el campo Grupo de costes.</span><span class="sxs-lookup"><span data-stu-id="0077e-229">In the Cost group field, type a value.</span></span>
    * <span data-ttu-id="0077e-230">Para este ejemplo, especifique M1.</span><span class="sxs-lookup"><span data-stu-id="0077e-230">For this example, type M1.</span></span>  
18. <span data-ttu-id="0077e-231">En el panel de acciones, haga clic en Gestionar costes.</span><span class="sxs-lookup"><span data-stu-id="0077e-231">On the Action Pane, click Manage costs.</span></span>
19. <span data-ttu-id="0077e-232">Haga clic en Precio de artículo.</span><span class="sxs-lookup"><span data-stu-id="0077e-232">Click Item price.</span></span>
20. <span data-ttu-id="0077e-233">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="0077e-233">Click New.</span></span>
21. <span data-ttu-id="0077e-234">En el campo Versión, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="0077e-234">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="0077e-235">Para este ejemplo, seleccione 10.</span><span class="sxs-lookup"><span data-stu-id="0077e-235">For this example, select 10.</span></span> <span data-ttu-id="0077e-236">Este es el Tipo de gestión de costes de coste estándar.</span><span class="sxs-lookup"><span data-stu-id="0077e-236">This is the Standard cost costing type.</span></span>  
22. <span data-ttu-id="0077e-237">En el campo Sitio, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="0077e-237">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="0077e-238">Para este ejemplo, seleccione Sitio 1.</span><span class="sxs-lookup"><span data-stu-id="0077e-238">For this example, select Site 1.</span></span>  
23. <span data-ttu-id="0077e-239">En el campo Precio, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="0077e-239">In the Price field, enter a number.</span></span>
    * <span data-ttu-id="0077e-240">Para este ejemplo, especifique 10.</span><span class="sxs-lookup"><span data-stu-id="0077e-240">For this example, type 10.</span></span>  
24. <span data-ttu-id="0077e-241">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="0077e-241">Click Save.</span></span>
25. <span data-ttu-id="0077e-242">Haga clic en Activar precios pendientes.</span><span class="sxs-lookup"><span data-stu-id="0077e-242">Click Activate pending price(s).</span></span>
26. <span data-ttu-id="0077e-243">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="0077e-243">Close the page.</span></span>
27. <span data-ttu-id="0077e-244">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="0077e-244">Close the page.</span></span>


