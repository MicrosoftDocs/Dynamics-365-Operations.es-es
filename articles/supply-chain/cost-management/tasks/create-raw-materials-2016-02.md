---
title: Crear materias primas (febrero de 2016 únicamente)
description: Esta tarea tarea se centra en crear los componentes de productos terminados y semiterminados.
author: ShylaThompson
manager: AnnBe
ms.date: 02/07/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 869acddf6f7e9754bb4952176ded4b22c74eaffd
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1563305"
---
# <a name="create-raw-materials-february-2016-only"></a><span data-ttu-id="f675b-103">Crear materias primas (febrero de 2016 únicamente)</span><span class="sxs-lookup"><span data-stu-id="f675b-103">Create raw materials (February 2016 only)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f675b-104">Esta tarea tarea se centra en crear los componentes de productos terminados y semiterminados.</span><span class="sxs-lookup"><span data-stu-id="f675b-104">This task focuses on creating the components of finished and semi-finished products.</span></span> <span data-ttu-id="f675b-105">Es la tercera tarea en las series de cálculo BOM.</span><span class="sxs-lookup"><span data-stu-id="f675b-105">It is the third task in the BOM calculation series.</span></span> <span data-ttu-id="f675b-106">La empresa de datos de prueba utilizada para crear esta tarea es USMF.</span><span class="sxs-lookup"><span data-stu-id="f675b-106">The demo data company used to create this task is USMF.</span></span>


## <a name="create-the-first-material"></a><span data-ttu-id="f675b-107">Cree el primer material</span><span class="sxs-lookup"><span data-stu-id="f675b-107">Create the first material</span></span>
1. <span data-ttu-id="f675b-108">Vaya a Gestión de información de productos > Productos > Productos emitidos.</span><span class="sxs-lookup"><span data-stu-id="f675b-108">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="f675b-109">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="f675b-109">Click New.</span></span>
3. <span data-ttu-id="f675b-110">En el campo Número de producto, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="f675b-110">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="f675b-111">Para este ejemplo, escriba ITEM_A.</span><span class="sxs-lookup"><span data-stu-id="f675b-111">For this example, enter ITEM_A.</span></span>  
4. <span data-ttu-id="f675b-112">En el campo Grupo de modelos de artículo, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="f675b-112">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="f675b-113">Seleccione STD.</span><span class="sxs-lookup"><span data-stu-id="f675b-113">Select STD.</span></span> <span data-ttu-id="f675b-114">El STD representa el coste estándar y es el modelo más usado al trabajar con cálculos de coste.</span><span class="sxs-lookup"><span data-stu-id="f675b-114">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
5. <span data-ttu-id="f675b-115">En el campo Grupo de artículos, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="f675b-115">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="f675b-116">Por ejemplo, seleccione Audio.</span><span class="sxs-lookup"><span data-stu-id="f675b-116">For example, select Audio.</span></span> <span data-ttu-id="f675b-117">Esto no tiene aafecta de ninguna manera a los cálculos de coste.</span><span class="sxs-lookup"><span data-stu-id="f675b-117">This has no impact on cost calculations.</span></span>  
6. <span data-ttu-id="f675b-118">En el campo Grupo de dimensiones de almacenamiento, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="f675b-118">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="f675b-119">Seleccione SiteWH.</span><span class="sxs-lookup"><span data-stu-id="f675b-119">Select SiteWH.</span></span> <span data-ttu-id="f675b-120">Para la demostración solo se usarán el Sitio y el Almacén.</span><span class="sxs-lookup"><span data-stu-id="f675b-120">Only Site and Warehouse will be used for the demonstration.</span></span>  
7. <span data-ttu-id="f675b-121">En el campo Grupo de dimensiones de seguimiento, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="f675b-121">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="f675b-122">Las dimensiones de seguimiento no se usarán en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="f675b-122">Tracking dimensions will not be used for this example.</span></span> <span data-ttu-id="f675b-123">Seleccione Ninguno.</span><span class="sxs-lookup"><span data-stu-id="f675b-123">Select None.</span></span>  
8. <span data-ttu-id="f675b-124">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="f675b-124">Click OK.</span></span>
9. <span data-ttu-id="f675b-125">En el panel de acciones, haga clic en Administrar inventario.</span><span class="sxs-lookup"><span data-stu-id="f675b-125">On the Action Pane, click Manage inventory.</span></span>
10. <span data-ttu-id="f675b-126">Haga clic en Configuración predeterminada de pedido.</span><span class="sxs-lookup"><span data-stu-id="f675b-126">Click Default order settings.</span></span>
11. <span data-ttu-id="f675b-127">En el campo Sitio de compra, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="f675b-127">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="f675b-128">Para este ejemplo, seleccione Sitio 1.</span><span class="sxs-lookup"><span data-stu-id="f675b-128">For this example, select Site 1.</span></span>  
12. <span data-ttu-id="f675b-129">En el campo Sitio de inventario, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="f675b-129">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="f675b-130">Para este ejemplo, seleccione Sitio 1.</span><span class="sxs-lookup"><span data-stu-id="f675b-130">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="f675b-131">En el campo Sitio de centas, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="f675b-131">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="f675b-132">Para este ejemplo, seleccione Sitio 1.</span><span class="sxs-lookup"><span data-stu-id="f675b-132">For this example, select Site 1.</span></span>  
14. <span data-ttu-id="f675b-133">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="f675b-133">Close the page.</span></span>
15. <span data-ttu-id="f675b-134">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="f675b-134">Close the page.</span></span>
16. <span data-ttu-id="f675b-135">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="f675b-135">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="f675b-136">Haga clic en ITEM_A.</span><span class="sxs-lookup"><span data-stu-id="f675b-136">Click ITEM_A.</span></span>  
17. <span data-ttu-id="f675b-137">Expanda la sección Administrar costes.</span><span class="sxs-lookup"><span data-stu-id="f675b-137">Expand the Manage costs section.</span></span>
18. <span data-ttu-id="f675b-138">Introduzca un valor en el campo Grupo de costes.</span><span class="sxs-lookup"><span data-stu-id="f675b-138">In the Cost group field, type a value.</span></span>
    * <span data-ttu-id="f675b-139">Para este ejemplo, introduzca M2.</span><span class="sxs-lookup"><span data-stu-id="f675b-139">For this example, type M2.</span></span>  
19. <span data-ttu-id="f675b-140">En el panel de acciones, haga clic en Gestionar costes.</span><span class="sxs-lookup"><span data-stu-id="f675b-140">On the Action Pane, click Manage costs.</span></span>
20. <span data-ttu-id="f675b-141">Haga clic en Precio de artículo.</span><span class="sxs-lookup"><span data-stu-id="f675b-141">Click Item price.</span></span>
21. <span data-ttu-id="f675b-142">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="f675b-142">Click New.</span></span>
22. <span data-ttu-id="f675b-143">En el campo Versión, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="f675b-143">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="f675b-144">Para este ejemplo, seleccione 10, que es el Tipo de gestión de costes de coste estándar.</span><span class="sxs-lookup"><span data-stu-id="f675b-144">For this example, select 10, which is the Standard cost costing type.</span></span>  
23. <span data-ttu-id="f675b-145">En el campo Sitio, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="f675b-145">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="f675b-146">Para este ejemplo, seleccione Sitio 1.</span><span class="sxs-lookup"><span data-stu-id="f675b-146">For this example, select Site 1.</span></span>  
24. <span data-ttu-id="f675b-147">En el campo Precio, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="f675b-147">In the Price field, enter a number.</span></span>
    * <span data-ttu-id="f675b-148">Para este ejemplo, especifique 10.</span><span class="sxs-lookup"><span data-stu-id="f675b-148">For this example, type 10.</span></span>  
25. <span data-ttu-id="f675b-149">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="f675b-149">Click Save.</span></span>
26. <span data-ttu-id="f675b-150">Haga clic en Activar precios pendientes.</span><span class="sxs-lookup"><span data-stu-id="f675b-150">Click Activate pending price(s).</span></span>
27. <span data-ttu-id="f675b-151">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="f675b-151">Close the page.</span></span>
28. <span data-ttu-id="f675b-152">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="f675b-152">Close the page.</span></span>

## <a name="create-the-second-material"></a><span data-ttu-id="f675b-153">Cree el segundo material</span><span class="sxs-lookup"><span data-stu-id="f675b-153">Create the second material</span></span>
1. <span data-ttu-id="f675b-154">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="f675b-154">Click New.</span></span>
2. <span data-ttu-id="f675b-155">En el campo Número de producto, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="f675b-155">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="f675b-156">Para este ejemplo, especifique ITEM_B.</span><span class="sxs-lookup"><span data-stu-id="f675b-156">For this example, type ITEM_B.</span></span>  
3. <span data-ttu-id="f675b-157">En el campo Grupo de modelos de artículo, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="f675b-157">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="f675b-158">Seleccione STD.</span><span class="sxs-lookup"><span data-stu-id="f675b-158">Select STD.</span></span> <span data-ttu-id="f675b-159">El STD representa el coste estándar y es el modelo más usado al trabajar con cálculos de coste.</span><span class="sxs-lookup"><span data-stu-id="f675b-159">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
4. <span data-ttu-id="f675b-160">En el campo Grupo de artículos, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="f675b-160">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="f675b-161">Por ejemplo, seleccione Audio.</span><span class="sxs-lookup"><span data-stu-id="f675b-161">For example, select Audio.</span></span> <span data-ttu-id="f675b-162">Esto no tiene aafecta de ninguna manera a los cálculos de coste.</span><span class="sxs-lookup"><span data-stu-id="f675b-162">This has no impact on cost calculations.</span></span>  
5. <span data-ttu-id="f675b-163">En el campo Grupo de dimensiones de almacenamiento, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="f675b-163">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="f675b-164">Seleccione SiteWH.</span><span class="sxs-lookup"><span data-stu-id="f675b-164">Select SiteWH.</span></span> <span data-ttu-id="f675b-165">Para este ejemplo solo se usarán el Sitio y el Almacén.</span><span class="sxs-lookup"><span data-stu-id="f675b-165">Only Site and Warehouse will be used for this example.</span></span>  
6. <span data-ttu-id="f675b-166">En el campo Grupo de dimensiones de seguimiento, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="f675b-166">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="f675b-167">Las dimensiones de seguimiento no se usarán en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="f675b-167">Tracking dimensions will not be used for this example.</span></span> <span data-ttu-id="f675b-168">Seleccione Ninguno.</span><span class="sxs-lookup"><span data-stu-id="f675b-168">Select None.</span></span>  
7. <span data-ttu-id="f675b-169">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="f675b-169">Click OK.</span></span>
8. <span data-ttu-id="f675b-170">En el panel de acciones, haga clic en Administrar inventario.</span><span class="sxs-lookup"><span data-stu-id="f675b-170">On the Action Pane, click Manage inventory.</span></span>
9. <span data-ttu-id="f675b-171">Haga clic en Configuración predeterminada de pedido.</span><span class="sxs-lookup"><span data-stu-id="f675b-171">Click Default order settings.</span></span>
10. <span data-ttu-id="f675b-172">En el campo Sitio de compra, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="f675b-172">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="f675b-173">Para este ejemplo, seleccione Sitio 1.</span><span class="sxs-lookup"><span data-stu-id="f675b-173">For this example, select Site 1.</span></span>  
11. <span data-ttu-id="f675b-174">En el campo Sitio de inventario, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="f675b-174">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="f675b-175">Para este ejemplo, seleccione Sitio 1.</span><span class="sxs-lookup"><span data-stu-id="f675b-175">For this example, select Site 1.</span></span>  
12. <span data-ttu-id="f675b-176">En el campo Sitio de centas, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="f675b-176">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="f675b-177">Para este ejemplo, seleccione Sitio 1.</span><span class="sxs-lookup"><span data-stu-id="f675b-177">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="f675b-178">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="f675b-178">Close the page.</span></span>
14. <span data-ttu-id="f675b-179">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="f675b-179">Close the page.</span></span>
15. <span data-ttu-id="f675b-180">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="f675b-180">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="f675b-181">Haga clic en ITEM_B. </span><span class="sxs-lookup"><span data-stu-id="f675b-181">Click ITEM_B.</span></span>  
16. <span data-ttu-id="f675b-182">Expanda la sección Administrar costes.</span><span class="sxs-lookup"><span data-stu-id="f675b-182">Expand the Manage costs section.</span></span>
17. <span data-ttu-id="f675b-183">Introduzca un valor en el campo Grupo de costes.</span><span class="sxs-lookup"><span data-stu-id="f675b-183">In the Cost group field, type a value.</span></span>
    * <span data-ttu-id="f675b-184">Para este ejemplo, introduzca M2.</span><span class="sxs-lookup"><span data-stu-id="f675b-184">For this example, type M2.</span></span>  
18. <span data-ttu-id="f675b-185">En el panel de acciones, haga clic en Gestionar costes.</span><span class="sxs-lookup"><span data-stu-id="f675b-185">On the Action Pane, click Manage costs.</span></span>
19. <span data-ttu-id="f675b-186">Haga clic en Precio de artículo.</span><span class="sxs-lookup"><span data-stu-id="f675b-186">Click Item price.</span></span>
20. <span data-ttu-id="f675b-187">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="f675b-187">Click New.</span></span>
21. <span data-ttu-id="f675b-188">En el campo Versión, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="f675b-188">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="f675b-189">Para este ejemplo, seleccione 10.</span><span class="sxs-lookup"><span data-stu-id="f675b-189">For this example, select 10.</span></span> <span data-ttu-id="f675b-190">Este es el Tipo de gestión de costes de coste estándar.</span><span class="sxs-lookup"><span data-stu-id="f675b-190">This is the Standard cost costing type.</span></span>  
22. <span data-ttu-id="f675b-191">En el campo Sitio, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="f675b-191">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="f675b-192">Para este ejemplo, seleccione Sitio 1.</span><span class="sxs-lookup"><span data-stu-id="f675b-192">For this example, select Site 1.</span></span>  
23. <span data-ttu-id="f675b-193">En el campo Precio, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="f675b-193">In the Price field, enter a number.</span></span>
    * <span data-ttu-id="f675b-194">Para la demostración, especifique 10.</span><span class="sxs-lookup"><span data-stu-id="f675b-194">For the demonstration, type 10.</span></span>  
24. <span data-ttu-id="f675b-195">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="f675b-195">Click Save.</span></span>
25. <span data-ttu-id="f675b-196">Haga clic en Activar precios pendientes.</span><span class="sxs-lookup"><span data-stu-id="f675b-196">Click Activate pending price(s).</span></span>
26. <span data-ttu-id="f675b-197">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="f675b-197">Close the page.</span></span>
27. <span data-ttu-id="f675b-198">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="f675b-198">Close the page.</span></span>

## <a name="create-the-third-material"></a><span data-ttu-id="f675b-199">Cree el tercer material</span><span class="sxs-lookup"><span data-stu-id="f675b-199">Create the third material</span></span>
1. <span data-ttu-id="f675b-200">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="f675b-200">Click New.</span></span>
2. <span data-ttu-id="f675b-201">En el campo Número de producto, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="f675b-201">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="f675b-202">Para la demostración, especifique ITEM_C.</span><span class="sxs-lookup"><span data-stu-id="f675b-202">For the demonstration, type ITEM_C</span></span>  
3. <span data-ttu-id="f675b-203">En el campo Grupo de modelos de artículo, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="f675b-203">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="f675b-204">Seleccione STD.</span><span class="sxs-lookup"><span data-stu-id="f675b-204">Select STD.</span></span> <span data-ttu-id="f675b-205">El STD representa el coste estándar y es el modelo más usado al trabajar con cálculos de coste.</span><span class="sxs-lookup"><span data-stu-id="f675b-205">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
4. <span data-ttu-id="f675b-206">En el campo Grupo de artículos, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="f675b-206">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="f675b-207">Por ejemplo, seleccione Audio.</span><span class="sxs-lookup"><span data-stu-id="f675b-207">For example, select Audio.</span></span> <span data-ttu-id="f675b-208">Esto no tiene aafecta de ninguna manera a los cálculos de coste.</span><span class="sxs-lookup"><span data-stu-id="f675b-208">This has no impact on cost calculations.</span></span>  
5. <span data-ttu-id="f675b-209">En el campo Grupo de dimensiones de almacenamiento, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="f675b-209">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="f675b-210">Seleccione SiteWH.</span><span class="sxs-lookup"><span data-stu-id="f675b-210">Select SiteWH.</span></span> <span data-ttu-id="f675b-211">Para la demostración solo se usarán el Sitio y el Almacén.</span><span class="sxs-lookup"><span data-stu-id="f675b-211">Only Site and Warehouse will be used for the demonstration.</span></span>  
6. <span data-ttu-id="f675b-212">En el campo Grupo de dimensiones de seguimiento, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="f675b-212">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="f675b-213">Las dimensiones de seguimiento no se usarán en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="f675b-213">Tracking dimensions will not be used for this example.</span></span> <span data-ttu-id="f675b-214">Seleccione Ninguno.</span><span class="sxs-lookup"><span data-stu-id="f675b-214">Select None.</span></span>  
7. <span data-ttu-id="f675b-215">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="f675b-215">Click OK.</span></span>
8. <span data-ttu-id="f675b-216">En el panel de acciones, haga clic en Administrar inventario.</span><span class="sxs-lookup"><span data-stu-id="f675b-216">On the Action Pane, click Manage inventory.</span></span>
9. <span data-ttu-id="f675b-217">Haga clic en Configuración predeterminada de pedido.</span><span class="sxs-lookup"><span data-stu-id="f675b-217">Click Default order settings.</span></span>
10. <span data-ttu-id="f675b-218">En el campo Sitio de compra, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="f675b-218">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="f675b-219">Para este ejemplo, seleccione Sitio 1.</span><span class="sxs-lookup"><span data-stu-id="f675b-219">For this example, select Site 1.</span></span>  
11. <span data-ttu-id="f675b-220">En el campo Sitio de inventario, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="f675b-220">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="f675b-221">Para este ejemplo, seleccione Sitio 1.</span><span class="sxs-lookup"><span data-stu-id="f675b-221">For this example, select Site 1.</span></span>  
12. <span data-ttu-id="f675b-222">En el campo Sitio de centas, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="f675b-222">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="f675b-223">Para este ejemplo, seleccione Sitio 1.</span><span class="sxs-lookup"><span data-stu-id="f675b-223">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="f675b-224">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="f675b-224">Close the page.</span></span>
14. <span data-ttu-id="f675b-225">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="f675b-225">Close the page.</span></span>
15. <span data-ttu-id="f675b-226">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="f675b-226">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="f675b-227">Haga clic en ITEM_C. </span><span class="sxs-lookup"><span data-stu-id="f675b-227">Click ITEM_C.</span></span>  
16. <span data-ttu-id="f675b-228">Expanda la sección Administrar costes.</span><span class="sxs-lookup"><span data-stu-id="f675b-228">Expand the Manage costs section.</span></span>
17. <span data-ttu-id="f675b-229">Introduzca un valor en el campo Grupo de costes.</span><span class="sxs-lookup"><span data-stu-id="f675b-229">In the Cost group field, type a value.</span></span>
    * <span data-ttu-id="f675b-230">Para este ejemplo, especifique M1.</span><span class="sxs-lookup"><span data-stu-id="f675b-230">For this example, type M1.</span></span>  
18. <span data-ttu-id="f675b-231">En el panel de acciones, haga clic en Gestionar costes.</span><span class="sxs-lookup"><span data-stu-id="f675b-231">On the Action Pane, click Manage costs.</span></span>
19. <span data-ttu-id="f675b-232">Haga clic en Precio de artículo.</span><span class="sxs-lookup"><span data-stu-id="f675b-232">Click Item price.</span></span>
20. <span data-ttu-id="f675b-233">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="f675b-233">Click New.</span></span>
21. <span data-ttu-id="f675b-234">En el campo Versión, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="f675b-234">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="f675b-235">Para este ejemplo, seleccione 10.</span><span class="sxs-lookup"><span data-stu-id="f675b-235">For this example, select 10.</span></span> <span data-ttu-id="f675b-236">Este es el Tipo de gestión de costes de coste estándar.</span><span class="sxs-lookup"><span data-stu-id="f675b-236">This is the Standard cost costing type.</span></span>  
22. <span data-ttu-id="f675b-237">En el campo Sitio, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="f675b-237">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="f675b-238">Para este ejemplo, seleccione Sitio 1.</span><span class="sxs-lookup"><span data-stu-id="f675b-238">For this example, select Site 1.</span></span>  
23. <span data-ttu-id="f675b-239">En el campo Precio, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="f675b-239">In the Price field, enter a number.</span></span>
    * <span data-ttu-id="f675b-240">Para este ejemplo, especifique 10.</span><span class="sxs-lookup"><span data-stu-id="f675b-240">For this example, type 10.</span></span>  
24. <span data-ttu-id="f675b-241">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="f675b-241">Click Save.</span></span>
25. <span data-ttu-id="f675b-242">Haga clic en Activar precios pendientes.</span><span class="sxs-lookup"><span data-stu-id="f675b-242">Click Activate pending price(s).</span></span>
26. <span data-ttu-id="f675b-243">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="f675b-243">Close the page.</span></span>
27. <span data-ttu-id="f675b-244">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="f675b-244">Close the page.</span></span>

