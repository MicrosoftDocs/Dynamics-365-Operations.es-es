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
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 3a33e3f7c2bdc54bab255960cebdeb3edec6d20d
ms.contentlocale: es-es
ms.lasthandoff: 05/08/2018

---
# <a name="create-raw-materials-february-2016-only"></a><span data-ttu-id="57a57-103">Crear materias primas (febrero de 2016 únicamente)</span><span class="sxs-lookup"><span data-stu-id="57a57-103">Create raw materials (February 2016 only)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="57a57-104">Esta tarea tarea se centra en crear los componentes de productos terminados y semiterminados.</span><span class="sxs-lookup"><span data-stu-id="57a57-104">This task focuses on creating the components of finished and semi-finished products.</span></span> <span data-ttu-id="57a57-105">Es la tercera tarea en las series de cálculo BOM.</span><span class="sxs-lookup"><span data-stu-id="57a57-105">It is the third task in the BOM calculation series.</span></span> <span data-ttu-id="57a57-106">La empresa de datos de prueba utilizada para crear esta tarea es USMF.</span><span class="sxs-lookup"><span data-stu-id="57a57-106">The demo data company used to create this task is USMF.</span></span>


## <a name="create-the-first-material"></a><span data-ttu-id="57a57-107">Cree el primer material</span><span class="sxs-lookup"><span data-stu-id="57a57-107">Create the first material</span></span>
1. <span data-ttu-id="57a57-108">Vaya a Gestión de información de productos > Productos > Productos emitidos.</span><span class="sxs-lookup"><span data-stu-id="57a57-108">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="57a57-109">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="57a57-109">Click New.</span></span>
3. <span data-ttu-id="57a57-110">En el campo Número de producto, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="57a57-110">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="57a57-111">Para este ejemplo, escriba ITEM_A.</span><span class="sxs-lookup"><span data-stu-id="57a57-111">For this example, enter ITEM_A.</span></span>  
4. <span data-ttu-id="57a57-112">En el campo Grupo de modelos de artículo, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="57a57-112">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="57a57-113">Seleccione STD.</span><span class="sxs-lookup"><span data-stu-id="57a57-113">Select STD.</span></span> <span data-ttu-id="57a57-114">El STD representa el coste estándar y es el modelo más usado al trabajar con cálculos de coste.</span><span class="sxs-lookup"><span data-stu-id="57a57-114">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
5. <span data-ttu-id="57a57-115">En el campo Grupo de artículos, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="57a57-115">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="57a57-116">Por ejemplo, seleccione Audio.</span><span class="sxs-lookup"><span data-stu-id="57a57-116">For example, select Audio.</span></span> <span data-ttu-id="57a57-117">Esto no tiene aafecta de ninguna manera a los cálculos de coste.</span><span class="sxs-lookup"><span data-stu-id="57a57-117">This has no impact on cost calculations.</span></span>  
6. <span data-ttu-id="57a57-118">En el campo Grupo de dimensiones de almacenamiento, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="57a57-118">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="57a57-119">Seleccione SiteWH.</span><span class="sxs-lookup"><span data-stu-id="57a57-119">Select SiteWH.</span></span> <span data-ttu-id="57a57-120">Para la demostración solo se usarán el Sitio y el Almacén.</span><span class="sxs-lookup"><span data-stu-id="57a57-120">Only Site and Warehouse will be used for the demonstration.</span></span>  
7. <span data-ttu-id="57a57-121">En el campo Grupo de dimensiones de seguimiento, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="57a57-121">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="57a57-122">Las dimensiones de seguimiento no se usarán en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="57a57-122">Tracking dimensions will not be used for this example.</span></span> <span data-ttu-id="57a57-123">Seleccione Ninguno.</span><span class="sxs-lookup"><span data-stu-id="57a57-123">Select None.</span></span>  
8. <span data-ttu-id="57a57-124">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="57a57-124">Click OK.</span></span>
9. <span data-ttu-id="57a57-125">En el panel de acciones, haga clic en Administrar inventario.</span><span class="sxs-lookup"><span data-stu-id="57a57-125">On the Action Pane, click Manage inventory.</span></span>
10. <span data-ttu-id="57a57-126">Haga clic en Configuración predeterminada de pedido.</span><span class="sxs-lookup"><span data-stu-id="57a57-126">Click Default order settings.</span></span>
11. <span data-ttu-id="57a57-127">En el campo Sitio de compra, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="57a57-127">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="57a57-128">Para este ejemplo, seleccione Sitio 1.</span><span class="sxs-lookup"><span data-stu-id="57a57-128">For this example, select Site 1.</span></span>  
12. <span data-ttu-id="57a57-129">En el campo Sitio de inventario, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="57a57-129">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="57a57-130">Para este ejemplo, seleccione Sitio 1.</span><span class="sxs-lookup"><span data-stu-id="57a57-130">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="57a57-131">En el campo Sitio de centas, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="57a57-131">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="57a57-132">Para este ejemplo, seleccione Sitio 1.</span><span class="sxs-lookup"><span data-stu-id="57a57-132">For this example, select Site 1.</span></span>  
14. <span data-ttu-id="57a57-133">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="57a57-133">Close the page.</span></span>
15. <span data-ttu-id="57a57-134">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="57a57-134">Close the page.</span></span>
16. <span data-ttu-id="57a57-135">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="57a57-135">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="57a57-136">Haga clic en ITEM_A.</span><span class="sxs-lookup"><span data-stu-id="57a57-136">Click ITEM_A.</span></span>  
17. <span data-ttu-id="57a57-137">Expanda la sección Administrar costes.</span><span class="sxs-lookup"><span data-stu-id="57a57-137">Expand the Manage costs section.</span></span>
18. <span data-ttu-id="57a57-138">Introduzca un valor en el campo Grupo de costes.</span><span class="sxs-lookup"><span data-stu-id="57a57-138">In the Cost group field, type a value.</span></span>
    * <span data-ttu-id="57a57-139">Para este ejemplo, introduzca M2.</span><span class="sxs-lookup"><span data-stu-id="57a57-139">For this example, type M2.</span></span>  
19. <span data-ttu-id="57a57-140">En el panel de acciones, haga clic en Gestionar costes.</span><span class="sxs-lookup"><span data-stu-id="57a57-140">On the Action Pane, click Manage costs.</span></span>
20. <span data-ttu-id="57a57-141">Haga clic en Precio de artículo.</span><span class="sxs-lookup"><span data-stu-id="57a57-141">Click Item price.</span></span>
21. <span data-ttu-id="57a57-142">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="57a57-142">Click New.</span></span>
22. <span data-ttu-id="57a57-143">En el campo Versión, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="57a57-143">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="57a57-144">Para este ejemplo, seleccione 10, que es el Tipo de gestión de costes de coste estándar.</span><span class="sxs-lookup"><span data-stu-id="57a57-144">For this example, select 10, which is the Standard cost costing type.</span></span>  
23. <span data-ttu-id="57a57-145">En el campo Sitio, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="57a57-145">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="57a57-146">Para este ejemplo, seleccione Sitio 1.</span><span class="sxs-lookup"><span data-stu-id="57a57-146">For this example, select Site 1.</span></span>  
24. <span data-ttu-id="57a57-147">En el campo Precio, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="57a57-147">In the Price field, enter a number.</span></span>
    * <span data-ttu-id="57a57-148">Para este ejemplo, especifique 10.</span><span class="sxs-lookup"><span data-stu-id="57a57-148">For this example, type 10.</span></span>  
25. <span data-ttu-id="57a57-149">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="57a57-149">Click Save.</span></span>
26. <span data-ttu-id="57a57-150">Haga clic en Activar precios pendientes.</span><span class="sxs-lookup"><span data-stu-id="57a57-150">Click Activate pending price(s).</span></span>
27. <span data-ttu-id="57a57-151">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="57a57-151">Close the page.</span></span>
28. <span data-ttu-id="57a57-152">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="57a57-152">Close the page.</span></span>

## <a name="create-the-second-material"></a><span data-ttu-id="57a57-153">Cree el segundo material</span><span class="sxs-lookup"><span data-stu-id="57a57-153">Create the second material</span></span>
1. <span data-ttu-id="57a57-154">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="57a57-154">Click New.</span></span>
2. <span data-ttu-id="57a57-155">En el campo Número de producto, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="57a57-155">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="57a57-156">Para este ejemplo, especifique ITEM_B.</span><span class="sxs-lookup"><span data-stu-id="57a57-156">For this example, type ITEM_B.</span></span>  
3. <span data-ttu-id="57a57-157">En el campo Grupo de modelos de artículo, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="57a57-157">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="57a57-158">Seleccione STD.</span><span class="sxs-lookup"><span data-stu-id="57a57-158">Select STD.</span></span> <span data-ttu-id="57a57-159">El STD representa el coste estándar y es el modelo más usado al trabajar con cálculos de coste.</span><span class="sxs-lookup"><span data-stu-id="57a57-159">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
4. <span data-ttu-id="57a57-160">En el campo Grupo de artículos, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="57a57-160">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="57a57-161">Por ejemplo, seleccione Audio.</span><span class="sxs-lookup"><span data-stu-id="57a57-161">For example, select Audio.</span></span> <span data-ttu-id="57a57-162">Esto no tiene aafecta de ninguna manera a los cálculos de coste.</span><span class="sxs-lookup"><span data-stu-id="57a57-162">This has no impact on cost calculations.</span></span>  
5. <span data-ttu-id="57a57-163">En el campo Grupo de dimensiones de almacenamiento, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="57a57-163">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="57a57-164">Seleccione SiteWH.</span><span class="sxs-lookup"><span data-stu-id="57a57-164">Select SiteWH.</span></span> <span data-ttu-id="57a57-165">Para este ejemplo solo se usarán el Sitio y el Almacén.</span><span class="sxs-lookup"><span data-stu-id="57a57-165">Only Site and Warehouse will be used for this example.</span></span>  
6. <span data-ttu-id="57a57-166">En el campo Grupo de dimensiones de seguimiento, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="57a57-166">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="57a57-167">Las dimensiones de seguimiento no se usarán en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="57a57-167">Tracking dimensions will not be used for this example.</span></span> <span data-ttu-id="57a57-168">Seleccione Ninguno.</span><span class="sxs-lookup"><span data-stu-id="57a57-168">Select None.</span></span>  
7. <span data-ttu-id="57a57-169">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="57a57-169">Click OK.</span></span>
8. <span data-ttu-id="57a57-170">En el panel de acciones, haga clic en Administrar inventario.</span><span class="sxs-lookup"><span data-stu-id="57a57-170">On the Action Pane, click Manage inventory.</span></span>
9. <span data-ttu-id="57a57-171">Haga clic en Configuración predeterminada de pedido.</span><span class="sxs-lookup"><span data-stu-id="57a57-171">Click Default order settings.</span></span>
10. <span data-ttu-id="57a57-172">En el campo Sitio de compra, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="57a57-172">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="57a57-173">Para este ejemplo, seleccione Sitio 1.</span><span class="sxs-lookup"><span data-stu-id="57a57-173">For this example, select Site 1.</span></span>  
11. <span data-ttu-id="57a57-174">En el campo Sitio de inventario, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="57a57-174">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="57a57-175">Para este ejemplo, seleccione Sitio 1.</span><span class="sxs-lookup"><span data-stu-id="57a57-175">For this example, select Site 1.</span></span>  
12. <span data-ttu-id="57a57-176">En el campo Sitio de centas, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="57a57-176">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="57a57-177">Para este ejemplo, seleccione Sitio 1.</span><span class="sxs-lookup"><span data-stu-id="57a57-177">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="57a57-178">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="57a57-178">Close the page.</span></span>
14. <span data-ttu-id="57a57-179">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="57a57-179">Close the page.</span></span>
15. <span data-ttu-id="57a57-180">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="57a57-180">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="57a57-181">Haga clic en ITEM_B. </span><span class="sxs-lookup"><span data-stu-id="57a57-181">Click ITEM_B.</span></span>  
16. <span data-ttu-id="57a57-182">Expanda la sección Administrar costes.</span><span class="sxs-lookup"><span data-stu-id="57a57-182">Expand the Manage costs section.</span></span>
17. <span data-ttu-id="57a57-183">Introduzca un valor en el campo Grupo de costes.</span><span class="sxs-lookup"><span data-stu-id="57a57-183">In the Cost group field, type a value.</span></span>
    * <span data-ttu-id="57a57-184">Para este ejemplo, introduzca M2.</span><span class="sxs-lookup"><span data-stu-id="57a57-184">For this example, type M2.</span></span>  
18. <span data-ttu-id="57a57-185">En el panel de acciones, haga clic en Gestionar costes.</span><span class="sxs-lookup"><span data-stu-id="57a57-185">On the Action Pane, click Manage costs.</span></span>
19. <span data-ttu-id="57a57-186">Haga clic en Precio de artículo.</span><span class="sxs-lookup"><span data-stu-id="57a57-186">Click Item price.</span></span>
20. <span data-ttu-id="57a57-187">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="57a57-187">Click New.</span></span>
21. <span data-ttu-id="57a57-188">En el campo Versión, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="57a57-188">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="57a57-189">Para este ejemplo, seleccione 10.</span><span class="sxs-lookup"><span data-stu-id="57a57-189">For this example, select 10.</span></span> <span data-ttu-id="57a57-190">Este es el Tipo de gestión de costes de coste estándar.</span><span class="sxs-lookup"><span data-stu-id="57a57-190">This is the Standard cost costing type.</span></span>  
22. <span data-ttu-id="57a57-191">En el campo Sitio, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="57a57-191">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="57a57-192">Para este ejemplo, seleccione Sitio 1.</span><span class="sxs-lookup"><span data-stu-id="57a57-192">For this example, select Site 1.</span></span>  
23. <span data-ttu-id="57a57-193">En el campo Precio, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="57a57-193">In the Price field, enter a number.</span></span>
    * <span data-ttu-id="57a57-194">Para la demostración, especifique 10.</span><span class="sxs-lookup"><span data-stu-id="57a57-194">For the demonstration, type 10.</span></span>  
24. <span data-ttu-id="57a57-195">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="57a57-195">Click Save.</span></span>
25. <span data-ttu-id="57a57-196">Haga clic en Activar precios pendientes.</span><span class="sxs-lookup"><span data-stu-id="57a57-196">Click Activate pending price(s).</span></span>
26. <span data-ttu-id="57a57-197">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="57a57-197">Close the page.</span></span>
27. <span data-ttu-id="57a57-198">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="57a57-198">Close the page.</span></span>

## <a name="create-the-third-material"></a><span data-ttu-id="57a57-199">Cree el tercer material</span><span class="sxs-lookup"><span data-stu-id="57a57-199">Create the third material</span></span>
1. <span data-ttu-id="57a57-200">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="57a57-200">Click New.</span></span>
2. <span data-ttu-id="57a57-201">En el campo Número de producto, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="57a57-201">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="57a57-202">Para la demostración, especifique ITEM_C.</span><span class="sxs-lookup"><span data-stu-id="57a57-202">For the demonstration, type ITEM_C</span></span>  
3. <span data-ttu-id="57a57-203">En el campo Grupo de modelos de artículo, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="57a57-203">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="57a57-204">Seleccione STD.</span><span class="sxs-lookup"><span data-stu-id="57a57-204">Select STD.</span></span> <span data-ttu-id="57a57-205">El STD representa el coste estándar y es el modelo más usado al trabajar con cálculos de coste.</span><span class="sxs-lookup"><span data-stu-id="57a57-205">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
4. <span data-ttu-id="57a57-206">En el campo Grupo de artículos, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="57a57-206">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="57a57-207">Por ejemplo, seleccione Audio.</span><span class="sxs-lookup"><span data-stu-id="57a57-207">For example, select Audio.</span></span> <span data-ttu-id="57a57-208">Esto no tiene aafecta de ninguna manera a los cálculos de coste.</span><span class="sxs-lookup"><span data-stu-id="57a57-208">This has no impact on cost calculations.</span></span>  
5. <span data-ttu-id="57a57-209">En el campo Grupo de dimensiones de almacenamiento, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="57a57-209">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="57a57-210">Seleccione SiteWH.</span><span class="sxs-lookup"><span data-stu-id="57a57-210">Select SiteWH.</span></span> <span data-ttu-id="57a57-211">Para la demostración solo se usarán el Sitio y el Almacén.</span><span class="sxs-lookup"><span data-stu-id="57a57-211">Only Site and Warehouse will be used for the demonstration.</span></span>  
6. <span data-ttu-id="57a57-212">En el campo Grupo de dimensiones de seguimiento, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="57a57-212">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="57a57-213">Las dimensiones de seguimiento no se usarán en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="57a57-213">Tracking dimensions will not be used for this example.</span></span> <span data-ttu-id="57a57-214">Seleccione Ninguno.</span><span class="sxs-lookup"><span data-stu-id="57a57-214">Select None.</span></span>  
7. <span data-ttu-id="57a57-215">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="57a57-215">Click OK.</span></span>
8. <span data-ttu-id="57a57-216">En el panel de acciones, haga clic en Administrar inventario.</span><span class="sxs-lookup"><span data-stu-id="57a57-216">On the Action Pane, click Manage inventory.</span></span>
9. <span data-ttu-id="57a57-217">Haga clic en Configuración predeterminada de pedido.</span><span class="sxs-lookup"><span data-stu-id="57a57-217">Click Default order settings.</span></span>
10. <span data-ttu-id="57a57-218">En el campo Sitio de compra, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="57a57-218">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="57a57-219">Para este ejemplo, seleccione Sitio 1.</span><span class="sxs-lookup"><span data-stu-id="57a57-219">For this example, select Site 1.</span></span>  
11. <span data-ttu-id="57a57-220">En el campo Sitio de inventario, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="57a57-220">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="57a57-221">Para este ejemplo, seleccione Sitio 1.</span><span class="sxs-lookup"><span data-stu-id="57a57-221">For this example, select Site 1.</span></span>  
12. <span data-ttu-id="57a57-222">En el campo Sitio de centas, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="57a57-222">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="57a57-223">Para este ejemplo, seleccione Sitio 1.</span><span class="sxs-lookup"><span data-stu-id="57a57-223">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="57a57-224">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="57a57-224">Close the page.</span></span>
14. <span data-ttu-id="57a57-225">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="57a57-225">Close the page.</span></span>
15. <span data-ttu-id="57a57-226">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="57a57-226">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="57a57-227">Haga clic en ITEM_C. </span><span class="sxs-lookup"><span data-stu-id="57a57-227">Click ITEM_C.</span></span>  
16. <span data-ttu-id="57a57-228">Expanda la sección Administrar costes.</span><span class="sxs-lookup"><span data-stu-id="57a57-228">Expand the Manage costs section.</span></span>
17. <span data-ttu-id="57a57-229">Introduzca un valor en el campo Grupo de costes.</span><span class="sxs-lookup"><span data-stu-id="57a57-229">In the Cost group field, type a value.</span></span>
    * <span data-ttu-id="57a57-230">Para este ejemplo, especifique M1.</span><span class="sxs-lookup"><span data-stu-id="57a57-230">For this example, type M1.</span></span>  
18. <span data-ttu-id="57a57-231">En el panel de acciones, haga clic en Gestionar costes.</span><span class="sxs-lookup"><span data-stu-id="57a57-231">On the Action Pane, click Manage costs.</span></span>
19. <span data-ttu-id="57a57-232">Haga clic en Precio de artículo.</span><span class="sxs-lookup"><span data-stu-id="57a57-232">Click Item price.</span></span>
20. <span data-ttu-id="57a57-233">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="57a57-233">Click New.</span></span>
21. <span data-ttu-id="57a57-234">En el campo Versión, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="57a57-234">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="57a57-235">Para este ejemplo, seleccione 10.</span><span class="sxs-lookup"><span data-stu-id="57a57-235">For this example, select 10.</span></span> <span data-ttu-id="57a57-236">Este es el Tipo de gestión de costes de coste estándar.</span><span class="sxs-lookup"><span data-stu-id="57a57-236">This is the Standard cost costing type.</span></span>  
22. <span data-ttu-id="57a57-237">En el campo Sitio, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="57a57-237">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="57a57-238">Para este ejemplo, seleccione Sitio 1.</span><span class="sxs-lookup"><span data-stu-id="57a57-238">For this example, select Site 1.</span></span>  
23. <span data-ttu-id="57a57-239">En el campo Precio, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="57a57-239">In the Price field, enter a number.</span></span>
    * <span data-ttu-id="57a57-240">Para este ejemplo, especifique 10.</span><span class="sxs-lookup"><span data-stu-id="57a57-240">For this example, type 10.</span></span>  
24. <span data-ttu-id="57a57-241">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="57a57-241">Click Save.</span></span>
25. <span data-ttu-id="57a57-242">Haga clic en Activar precios pendientes.</span><span class="sxs-lookup"><span data-stu-id="57a57-242">Click Activate pending price(s).</span></span>
26. <span data-ttu-id="57a57-243">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="57a57-243">Close the page.</span></span>
27. <span data-ttu-id="57a57-244">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="57a57-244">Close the page.</span></span>


