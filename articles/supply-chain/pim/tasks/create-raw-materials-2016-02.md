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
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "351065"
---
# <a name="create-raw-materials-february-2016"></a><span data-ttu-id="78b82-103">Crear materias primas (febrero de 2016)</span><span class="sxs-lookup"><span data-stu-id="78b82-103">Create raw materials (February 2016)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="78b82-104">Esta tarea tarea se centra en crear los componentes de productos terminados y semiterminados.</span><span class="sxs-lookup"><span data-stu-id="78b82-104">This task focuses on creating the components of finished and semi-finished products.</span></span> <span data-ttu-id="78b82-105">Es la tercera tarea en las series de cálculo BOM.</span><span class="sxs-lookup"><span data-stu-id="78b82-105">It is the third task in the BOM calculation series.</span></span> <span data-ttu-id="78b82-106">La empresa de datos de prueba utilizada para crear esta tarea es USMF.</span><span class="sxs-lookup"><span data-stu-id="78b82-106">The demo data company used to create this task is USMF.</span></span>


## <a name="create-the-first-material"></a><span data-ttu-id="78b82-107">Cree el primer material</span><span class="sxs-lookup"><span data-stu-id="78b82-107">Create the first material</span></span>
1. <span data-ttu-id="78b82-108">Vaya a Gestión de información de productos > Productos > Productos emitidos.</span><span class="sxs-lookup"><span data-stu-id="78b82-108">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="78b82-109">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="78b82-109">Click New.</span></span>
3. <span data-ttu-id="78b82-110">En el campo Número de producto, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="78b82-110">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="78b82-111">Para este ejemplo, escriba ITEM_A.</span><span class="sxs-lookup"><span data-stu-id="78b82-111">For this example, enter ITEM_A.</span></span>  
4. <span data-ttu-id="78b82-112">En el campo Grupo de modelos de artículo, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="78b82-112">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="78b82-113">Seleccione STD.</span><span class="sxs-lookup"><span data-stu-id="78b82-113">Select STD.</span></span> <span data-ttu-id="78b82-114">El STD representa el coste estándar y es el modelo más usado al trabajar con cálculos de coste.</span><span class="sxs-lookup"><span data-stu-id="78b82-114">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
5. <span data-ttu-id="78b82-115">En el campo Grupo de artículos, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="78b82-115">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="78b82-116">Por ejemplo, seleccione Audio.</span><span class="sxs-lookup"><span data-stu-id="78b82-116">For example, select Audio.</span></span> <span data-ttu-id="78b82-117">Esto no tiene aafecta de ninguna manera a los cálculos de coste.</span><span class="sxs-lookup"><span data-stu-id="78b82-117">This has no impact on cost calculations.</span></span>  
6. <span data-ttu-id="78b82-118">En el campo Grupo de dimensiones de almacenamiento, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="78b82-118">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="78b82-119">Seleccione SiteWH.</span><span class="sxs-lookup"><span data-stu-id="78b82-119">Select SiteWH.</span></span> <span data-ttu-id="78b82-120">Para la demostración solo se usarán el Sitio y el Almacén.</span><span class="sxs-lookup"><span data-stu-id="78b82-120">Only Site and Warehouse will be used for the demonstration.</span></span>  
7. <span data-ttu-id="78b82-121">En el campo Grupo de dimensiones de seguimiento, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="78b82-121">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="78b82-122">Las dimensiones de seguimiento no se usarán en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="78b82-122">Tracking dimensions will not be used for this example.</span></span> <span data-ttu-id="78b82-123">Seleccione Ninguno.</span><span class="sxs-lookup"><span data-stu-id="78b82-123">Select None.</span></span>  
8. <span data-ttu-id="78b82-124">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="78b82-124">Click OK.</span></span>
9. <span data-ttu-id="78b82-125">En el panel de acciones, haga clic en Administrar inventario.</span><span class="sxs-lookup"><span data-stu-id="78b82-125">On the Action Pane, click Manage inventory.</span></span>
10. <span data-ttu-id="78b82-126">Haga clic en Configuración predeterminada de pedido.</span><span class="sxs-lookup"><span data-stu-id="78b82-126">Click Default order settings.</span></span>
11. <span data-ttu-id="78b82-127">En el campo Sitio de compra, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="78b82-127">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="78b82-128">Para este ejemplo, seleccione Sitio 1.</span><span class="sxs-lookup"><span data-stu-id="78b82-128">For this example, select Site 1.</span></span>  
12. <span data-ttu-id="78b82-129">En el campo Sitio de inventario, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="78b82-129">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="78b82-130">Para este ejemplo, seleccione Sitio 1.</span><span class="sxs-lookup"><span data-stu-id="78b82-130">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="78b82-131">En el campo Sitio de centas, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="78b82-131">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="78b82-132">Para este ejemplo, seleccione Sitio 1.</span><span class="sxs-lookup"><span data-stu-id="78b82-132">For this example, select Site 1.</span></span>  
14. <span data-ttu-id="78b82-133">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="78b82-133">Close the page.</span></span>
15. <span data-ttu-id="78b82-134">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="78b82-134">Close the page.</span></span>
16. <span data-ttu-id="78b82-135">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="78b82-135">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="78b82-136">Haga clic en ITEM_A.</span><span class="sxs-lookup"><span data-stu-id="78b82-136">Click ITEM_A.</span></span>  
17. <span data-ttu-id="78b82-137">Expanda la sección Administrar costes.</span><span class="sxs-lookup"><span data-stu-id="78b82-137">Expand the Manage costs section.</span></span>
18. <span data-ttu-id="78b82-138">Introduzca un valor en el campo Grupo de costes.</span><span class="sxs-lookup"><span data-stu-id="78b82-138">In the Cost group field, type a value.</span></span>
    * <span data-ttu-id="78b82-139">Para este ejemplo, introduzca M2.</span><span class="sxs-lookup"><span data-stu-id="78b82-139">For this example, type M2.</span></span>  
19. <span data-ttu-id="78b82-140">En el panel de acciones, haga clic en Gestionar costes.</span><span class="sxs-lookup"><span data-stu-id="78b82-140">On the Action Pane, click Manage costs.</span></span>
20. <span data-ttu-id="78b82-141">Haga clic en Precio de artículo.</span><span class="sxs-lookup"><span data-stu-id="78b82-141">Click Item price.</span></span>
21. <span data-ttu-id="78b82-142">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="78b82-142">Click New.</span></span>
22. <span data-ttu-id="78b82-143">En el campo Versión, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="78b82-143">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="78b82-144">Para este ejemplo, seleccione 10, que es el Tipo de gestión de costes de coste estándar.</span><span class="sxs-lookup"><span data-stu-id="78b82-144">For this example, select 10, which is the Standard cost costing type.</span></span>  
23. <span data-ttu-id="78b82-145">En el campo Sitio, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="78b82-145">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="78b82-146">Para este ejemplo, seleccione Sitio 1.</span><span class="sxs-lookup"><span data-stu-id="78b82-146">For this example, select Site 1.</span></span>  
24. <span data-ttu-id="78b82-147">En el campo Precio, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="78b82-147">In the Price field, enter a number.</span></span>
    * <span data-ttu-id="78b82-148">Para este ejemplo, especifique 10.</span><span class="sxs-lookup"><span data-stu-id="78b82-148">For this example, type 10.</span></span>  
25. <span data-ttu-id="78b82-149">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="78b82-149">Click Save.</span></span>
26. <span data-ttu-id="78b82-150">Haga clic en Activar precios pendientes.</span><span class="sxs-lookup"><span data-stu-id="78b82-150">Click Activate pending price(s).</span></span>
27. <span data-ttu-id="78b82-151">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="78b82-151">Close the page.</span></span>
28. <span data-ttu-id="78b82-152">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="78b82-152">Close the page.</span></span>

## <a name="create-the-second-material"></a><span data-ttu-id="78b82-153">Cree el segundo material</span><span class="sxs-lookup"><span data-stu-id="78b82-153">Create the second material</span></span>
1. <span data-ttu-id="78b82-154">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="78b82-154">Click New.</span></span>
2. <span data-ttu-id="78b82-155">En el campo Número de producto, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="78b82-155">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="78b82-156">Para este ejemplo, especifique ITEM_B.</span><span class="sxs-lookup"><span data-stu-id="78b82-156">For this example, type ITEM_B.</span></span>  
3. <span data-ttu-id="78b82-157">En el campo Grupo de modelos de artículo, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="78b82-157">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="78b82-158">Seleccione STD.</span><span class="sxs-lookup"><span data-stu-id="78b82-158">Select STD.</span></span> <span data-ttu-id="78b82-159">El STD representa el coste estándar y es el modelo más usado al trabajar con cálculos de coste.</span><span class="sxs-lookup"><span data-stu-id="78b82-159">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
4. <span data-ttu-id="78b82-160">En el campo Grupo de artículos, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="78b82-160">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="78b82-161">Por ejemplo, seleccione Audio.</span><span class="sxs-lookup"><span data-stu-id="78b82-161">For example, select Audio.</span></span> <span data-ttu-id="78b82-162">Esto no tiene aafecta de ninguna manera a los cálculos de coste.</span><span class="sxs-lookup"><span data-stu-id="78b82-162">This has no impact on cost calculations.</span></span>  
5. <span data-ttu-id="78b82-163">En el campo Grupo de dimensiones de almacenamiento, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="78b82-163">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="78b82-164">Seleccione SiteWH.</span><span class="sxs-lookup"><span data-stu-id="78b82-164">Select SiteWH.</span></span> <span data-ttu-id="78b82-165">Para este ejemplo solo se usarán el Sitio y el Almacén.</span><span class="sxs-lookup"><span data-stu-id="78b82-165">Only Site and Warehouse will be used for this example.</span></span>  
6. <span data-ttu-id="78b82-166">En el campo Grupo de dimensiones de seguimiento, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="78b82-166">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="78b82-167">Las dimensiones de seguimiento no se usarán en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="78b82-167">Tracking dimensions will not be used for this example.</span></span> <span data-ttu-id="78b82-168">Seleccione Ninguno.</span><span class="sxs-lookup"><span data-stu-id="78b82-168">Select None.</span></span>  
7. <span data-ttu-id="78b82-169">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="78b82-169">Click OK.</span></span>
8. <span data-ttu-id="78b82-170">En el panel de acciones, haga clic en Administrar inventario.</span><span class="sxs-lookup"><span data-stu-id="78b82-170">On the Action Pane, click Manage inventory.</span></span>
9. <span data-ttu-id="78b82-171">Haga clic en Configuración predeterminada de pedido.</span><span class="sxs-lookup"><span data-stu-id="78b82-171">Click Default order settings.</span></span>
10. <span data-ttu-id="78b82-172">En el campo Sitio de compra, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="78b82-172">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="78b82-173">Para este ejemplo, seleccione Sitio 1.</span><span class="sxs-lookup"><span data-stu-id="78b82-173">For this example, select Site 1.</span></span>  
11. <span data-ttu-id="78b82-174">En el campo Sitio de inventario, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="78b82-174">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="78b82-175">Para este ejemplo, seleccione Sitio 1.</span><span class="sxs-lookup"><span data-stu-id="78b82-175">For this example, select Site 1.</span></span>  
12. <span data-ttu-id="78b82-176">En el campo Sitio de centas, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="78b82-176">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="78b82-177">Para este ejemplo, seleccione Sitio 1.</span><span class="sxs-lookup"><span data-stu-id="78b82-177">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="78b82-178">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="78b82-178">Close the page.</span></span>
14. <span data-ttu-id="78b82-179">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="78b82-179">Close the page.</span></span>
15. <span data-ttu-id="78b82-180">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="78b82-180">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="78b82-181">Haga clic en ITEM_B. </span><span class="sxs-lookup"><span data-stu-id="78b82-181">Click ITEM_B.</span></span>  
16. <span data-ttu-id="78b82-182">Expanda la sección Administrar costes.</span><span class="sxs-lookup"><span data-stu-id="78b82-182">Expand the Manage costs section.</span></span>
17. <span data-ttu-id="78b82-183">Introduzca un valor en el campo Grupo de costes.</span><span class="sxs-lookup"><span data-stu-id="78b82-183">In the Cost group field, type a value.</span></span>
    * <span data-ttu-id="78b82-184">Para este ejemplo, introduzca M2.</span><span class="sxs-lookup"><span data-stu-id="78b82-184">For this example, type M2.</span></span>  
18. <span data-ttu-id="78b82-185">En el panel de acciones, haga clic en Gestionar costes.</span><span class="sxs-lookup"><span data-stu-id="78b82-185">On the Action Pane, click Manage costs.</span></span>
19. <span data-ttu-id="78b82-186">Haga clic en Precio de artículo.</span><span class="sxs-lookup"><span data-stu-id="78b82-186">Click Item price.</span></span>
20. <span data-ttu-id="78b82-187">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="78b82-187">Click New.</span></span>
21. <span data-ttu-id="78b82-188">En el campo Versión, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="78b82-188">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="78b82-189">Para este ejemplo, seleccione 10.</span><span class="sxs-lookup"><span data-stu-id="78b82-189">For this example, select 10.</span></span> <span data-ttu-id="78b82-190">Este es el Tipo de gestión de costes de coste estándar.</span><span class="sxs-lookup"><span data-stu-id="78b82-190">This is the Standard cost costing type.</span></span>  
22. <span data-ttu-id="78b82-191">En el campo Sitio, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="78b82-191">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="78b82-192">Para este ejemplo, seleccione Sitio 1.</span><span class="sxs-lookup"><span data-stu-id="78b82-192">For this example, select Site 1.</span></span>  
23. <span data-ttu-id="78b82-193">En el campo Precio, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="78b82-193">In the Price field, enter a number.</span></span>
    * <span data-ttu-id="78b82-194">Para la demostración, especifique 10.</span><span class="sxs-lookup"><span data-stu-id="78b82-194">For the demonstration, type 10.</span></span>  
24. <span data-ttu-id="78b82-195">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="78b82-195">Click Save.</span></span>
25. <span data-ttu-id="78b82-196">Haga clic en Activar precios pendientes.</span><span class="sxs-lookup"><span data-stu-id="78b82-196">Click Activate pending price(s).</span></span>
26. <span data-ttu-id="78b82-197">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="78b82-197">Close the page.</span></span>
27. <span data-ttu-id="78b82-198">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="78b82-198">Close the page.</span></span>

## <a name="create-the-third-material"></a><span data-ttu-id="78b82-199">Cree el tercer material</span><span class="sxs-lookup"><span data-stu-id="78b82-199">Create the third material</span></span>
1. <span data-ttu-id="78b82-200">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="78b82-200">Click New.</span></span>
2. <span data-ttu-id="78b82-201">En el campo Número de producto, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="78b82-201">In the Product number field, type a value.</span></span>
    * <span data-ttu-id="78b82-202">Para la demostración, especifique ITEM_C.</span><span class="sxs-lookup"><span data-stu-id="78b82-202">For the demonstration, type ITEM_C</span></span>  
3. <span data-ttu-id="78b82-203">En el campo Grupo de modelos de artículo, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="78b82-203">In the Item model group field, enter or select a value.</span></span>
    * <span data-ttu-id="78b82-204">Seleccione STD.</span><span class="sxs-lookup"><span data-stu-id="78b82-204">Select STD.</span></span> <span data-ttu-id="78b82-205">El STD representa el coste estándar y es el modelo más usado al trabajar con cálculos de coste.</span><span class="sxs-lookup"><span data-stu-id="78b82-205">STD stands for standard cost and is the most commonly used model when working with cost calculations.</span></span>  
4. <span data-ttu-id="78b82-206">En el campo Grupo de artículos, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="78b82-206">In the Item group field, enter or select a value.</span></span>
    * <span data-ttu-id="78b82-207">Por ejemplo, seleccione Audio.</span><span class="sxs-lookup"><span data-stu-id="78b82-207">For example, select Audio.</span></span> <span data-ttu-id="78b82-208">Esto no tiene aafecta de ninguna manera a los cálculos de coste.</span><span class="sxs-lookup"><span data-stu-id="78b82-208">This has no impact on cost calculations.</span></span>  
5. <span data-ttu-id="78b82-209">En el campo Grupo de dimensiones de almacenamiento, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="78b82-209">In the Storage dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="78b82-210">Seleccione SiteWH.</span><span class="sxs-lookup"><span data-stu-id="78b82-210">Select SiteWH.</span></span> <span data-ttu-id="78b82-211">Para la demostración solo se usarán el Sitio y el Almacén.</span><span class="sxs-lookup"><span data-stu-id="78b82-211">Only Site and Warehouse will be used for the demonstration.</span></span>  
6. <span data-ttu-id="78b82-212">En el campo Grupo de dimensiones de seguimiento, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="78b82-212">In the Tracking dimension group field, enter or select a value.</span></span>
    * <span data-ttu-id="78b82-213">Las dimensiones de seguimiento no se usarán en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="78b82-213">Tracking dimensions will not be used for this example.</span></span> <span data-ttu-id="78b82-214">Seleccione Ninguno.</span><span class="sxs-lookup"><span data-stu-id="78b82-214">Select None.</span></span>  
7. <span data-ttu-id="78b82-215">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="78b82-215">Click OK.</span></span>
8. <span data-ttu-id="78b82-216">En el panel de acciones, haga clic en Administrar inventario.</span><span class="sxs-lookup"><span data-stu-id="78b82-216">On the Action Pane, click Manage inventory.</span></span>
9. <span data-ttu-id="78b82-217">Haga clic en Configuración predeterminada de pedido.</span><span class="sxs-lookup"><span data-stu-id="78b82-217">Click Default order settings.</span></span>
10. <span data-ttu-id="78b82-218">En el campo Sitio de compra, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="78b82-218">In the Purchase site field, enter or select a value.</span></span>
    * <span data-ttu-id="78b82-219">Para este ejemplo, seleccione Sitio 1.</span><span class="sxs-lookup"><span data-stu-id="78b82-219">For this example, select Site 1.</span></span>  
11. <span data-ttu-id="78b82-220">En el campo Sitio de inventario, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="78b82-220">In the Inventory site field, enter or select a value.</span></span>
    * <span data-ttu-id="78b82-221">Para este ejemplo, seleccione Sitio 1.</span><span class="sxs-lookup"><span data-stu-id="78b82-221">For this example, select Site 1.</span></span>  
12. <span data-ttu-id="78b82-222">En el campo Sitio de centas, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="78b82-222">In the Sales site field, enter or select a value.</span></span>
    * <span data-ttu-id="78b82-223">Para este ejemplo, seleccione Sitio 1.</span><span class="sxs-lookup"><span data-stu-id="78b82-223">For this example, select Site 1.</span></span>  
13. <span data-ttu-id="78b82-224">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="78b82-224">Close the page.</span></span>
14. <span data-ttu-id="78b82-225">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="78b82-225">Close the page.</span></span>
15. <span data-ttu-id="78b82-226">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="78b82-226">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="78b82-227">Haga clic en ITEM_C. </span><span class="sxs-lookup"><span data-stu-id="78b82-227">Click ITEM_C.</span></span>  
16. <span data-ttu-id="78b82-228">Expanda la sección Administrar costes.</span><span class="sxs-lookup"><span data-stu-id="78b82-228">Expand the Manage costs section.</span></span>
17. <span data-ttu-id="78b82-229">Introduzca un valor en el campo Grupo de costes.</span><span class="sxs-lookup"><span data-stu-id="78b82-229">In the Cost group field, type a value.</span></span>
    * <span data-ttu-id="78b82-230">Para este ejemplo, especifique M1.</span><span class="sxs-lookup"><span data-stu-id="78b82-230">For this example, type M1.</span></span>  
18. <span data-ttu-id="78b82-231">En el panel de acciones, haga clic en Gestionar costes.</span><span class="sxs-lookup"><span data-stu-id="78b82-231">On the Action Pane, click Manage costs.</span></span>
19. <span data-ttu-id="78b82-232">Haga clic en Precio de artículo.</span><span class="sxs-lookup"><span data-stu-id="78b82-232">Click Item price.</span></span>
20. <span data-ttu-id="78b82-233">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="78b82-233">Click New.</span></span>
21. <span data-ttu-id="78b82-234">En el campo Versión, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="78b82-234">In the Version field, enter or select a value.</span></span>
    * <span data-ttu-id="78b82-235">Para este ejemplo, seleccione 10.</span><span class="sxs-lookup"><span data-stu-id="78b82-235">For this example, select 10.</span></span> <span data-ttu-id="78b82-236">Este es el Tipo de gestión de costes de coste estándar.</span><span class="sxs-lookup"><span data-stu-id="78b82-236">This is the Standard cost costing type.</span></span>  
22. <span data-ttu-id="78b82-237">En el campo Sitio, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="78b82-237">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="78b82-238">Para este ejemplo, seleccione Sitio 1.</span><span class="sxs-lookup"><span data-stu-id="78b82-238">For this example, select Site 1.</span></span>  
23. <span data-ttu-id="78b82-239">En el campo Precio, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="78b82-239">In the Price field, enter a number.</span></span>
    * <span data-ttu-id="78b82-240">Para este ejemplo, especifique 10.</span><span class="sxs-lookup"><span data-stu-id="78b82-240">For this example, type 10.</span></span>  
24. <span data-ttu-id="78b82-241">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="78b82-241">Click Save.</span></span>
25. <span data-ttu-id="78b82-242">Haga clic en Activar precios pendientes.</span><span class="sxs-lookup"><span data-stu-id="78b82-242">Click Activate pending price(s).</span></span>
26. <span data-ttu-id="78b82-243">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="78b82-243">Close the page.</span></span>
27. <span data-ttu-id="78b82-244">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="78b82-244">Close the page.</span></span>

