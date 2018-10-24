--- 
title: Crear L. MAT (febrero de 2016)
description: "Esta tarea se centra en la creación de la estructura de una lista de materiales para un producto terminado y un producto semiterminado."
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResProductDetailsExtended, BOMConsistOf, BOMTable, InventLocationIdLookup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 6c5cfb8aae1a61d14f7a7969f688cb282530840d
ms.contentlocale: es-es
ms.lasthandoff: 09/14/2018

---
# <a name="create-boms-february-2016"></a><span data-ttu-id="fac97-103">Crear L. MAT (febrero de 2016)</span><span class="sxs-lookup"><span data-stu-id="fac97-103">Create BOMs (February 2016)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="fac97-104">Esta tarea se centra en la creación de la estructura de una lista de materiales para un producto terminado y un producto semiterminado.</span><span class="sxs-lookup"><span data-stu-id="fac97-104">This task focuses on creating the bill of materials structure for a finished product and a semi-finished product.</span></span> <span data-ttu-id="fac97-105">Es la cuarta tarea en las series de cálculo BOM.</span><span class="sxs-lookup"><span data-stu-id="fac97-105">It is the fourth task in the BOM calculation series.</span></span> <span data-ttu-id="fac97-106">La empresa de datos de prueba utilizada para crear esta tarea es USMF.</span><span class="sxs-lookup"><span data-stu-id="fac97-106">The demo data company used to create this task is USMF.</span></span>


## <a name="create-bom-for-a-semi-finished-product"></a><span data-ttu-id="fac97-107">Cree un BOM para un producto semi-acabado.</span><span class="sxs-lookup"><span data-stu-id="fac97-107">Create BOM for a semi-finished product</span></span>
1. <span data-ttu-id="fac97-108">Vaya a Gestión de información de productos > Productos > Productos emitidos.</span><span class="sxs-lookup"><span data-stu-id="fac97-108">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="fac97-109">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="fac97-109">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="fac97-110">Seleccione el número de artículo BOM_2.</span><span class="sxs-lookup"><span data-stu-id="fac97-110">Select the item number BOM_2.</span></span>  
3. <span data-ttu-id="fac97-111">En el panel de acciones, haga clic en Ingeniero.</span><span class="sxs-lookup"><span data-stu-id="fac97-111">On the Action Pane, click Engineer.</span></span>
4. <span data-ttu-id="fac97-112">Haga clic en Versiones de L. MAT.</span><span class="sxs-lookup"><span data-stu-id="fac97-112">Click BOM versions.</span></span>
5. <span data-ttu-id="fac97-113">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="fac97-113">Click New.</span></span>
6. <span data-ttu-id="fac97-114">Haga clic en L. MAT y versión de L. MAT.</span><span class="sxs-lookup"><span data-stu-id="fac97-114">Click BOM and BOM version.</span></span>
7. <span data-ttu-id="fac97-115">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="fac97-115">In the Name field, type a value.</span></span>
    * <span data-ttu-id="fac97-116">Por ejemplo, introduzca BOM_2.</span><span class="sxs-lookup"><span data-stu-id="fac97-116">For example, type BOM_2.</span></span>  
8. <span data-ttu-id="fac97-117">En el campo Sitio, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="fac97-117">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="fac97-118">Para este ejemplo, introduzca o seleccione el Sitio 1.</span><span class="sxs-lookup"><span data-stu-id="fac97-118">For this example, enter or select Site 1.</span></span>  
9. <span data-ttu-id="fac97-119">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="fac97-119">Click OK.</span></span>
10. <span data-ttu-id="fac97-120">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="fac97-120">Click New.</span></span>
11. <span data-ttu-id="fac97-121">En el campo Código de artículo, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="fac97-121">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="fac97-122">Para este ejemplo, introduzca ITEM_C.</span><span class="sxs-lookup"><span data-stu-id="fac97-122">For this example, type ITEM_C.</span></span>  
12. <span data-ttu-id="fac97-123">En el campo Almacén, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="fac97-123">In the Warehouse field, enter or select a value.</span></span>
    * <span data-ttu-id="fac97-124">Para este ejemplo, introduzca o seleccione 11.</span><span class="sxs-lookup"><span data-stu-id="fac97-124">For this example, enter or select 11.</span></span>  
13. <span data-ttu-id="fac97-125">Haga clic en Encabezado.</span><span class="sxs-lookup"><span data-stu-id="fac97-125">Click Header.</span></span>
14. <span data-ttu-id="fac97-126">Haga clic en Aprobación para aprobar listas de materiales.</span><span class="sxs-lookup"><span data-stu-id="fac97-126">Click Approval to approve bills of materials.</span></span>
15. <span data-ttu-id="fac97-127">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="fac97-127">Click OK.</span></span>
16. <span data-ttu-id="fac97-128">Haga clic en Aprobar.</span><span class="sxs-lookup"><span data-stu-id="fac97-128">Click Approve.</span></span>
    * <span data-ttu-id="fac97-129">El botón Aprobar se encuentra en la ToolBar en la sección de versiones BOM.</span><span class="sxs-lookup"><span data-stu-id="fac97-129">The Approve button is on the ToolBar in the  BOM versions section.</span></span> <span data-ttu-id="fac97-130">Si no está visible, haga clic en Cabecera en la parte superior derecha de la página de Listas de materiales para mostrar Aprobar.</span><span class="sxs-lookup"><span data-stu-id="fac97-130">If it is invisible, click Header at the upper right of the Bills of materials page to display Approve.</span></span>  
17. <span data-ttu-id="fac97-131">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="fac97-131">Click OK.</span></span>
18. <span data-ttu-id="fac97-132">Haga clic en Activar.</span><span class="sxs-lookup"><span data-stu-id="fac97-132">Click Activate.</span></span>
19. <span data-ttu-id="fac97-133">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="fac97-133">Close the page.</span></span>
20. <span data-ttu-id="fac97-134">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="fac97-134">Close the page.</span></span>
21. <span data-ttu-id="fac97-135">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="fac97-135">Close the page.</span></span>

## <a name="create-bom-for-a-finished-product"></a><span data-ttu-id="fac97-136">Cree un BOM para un producto acabado.</span><span class="sxs-lookup"><span data-stu-id="fac97-136">Create BOM for a finished product</span></span>
1. <span data-ttu-id="fac97-137">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="fac97-137">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="fac97-138">Seleccione el número de artículo BOM_1.</span><span class="sxs-lookup"><span data-stu-id="fac97-138">Select the item number BOM_1.</span></span>  
2. <span data-ttu-id="fac97-139">En el panel de acciones, haga clic en Ingeniero.</span><span class="sxs-lookup"><span data-stu-id="fac97-139">On the Action Pane, click Engineer.</span></span>
3. <span data-ttu-id="fac97-140">Haga clic en Versiones de L. MAT.</span><span class="sxs-lookup"><span data-stu-id="fac97-140">Click BOM versions.</span></span>
4. <span data-ttu-id="fac97-141">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="fac97-141">Click New.</span></span>
5. <span data-ttu-id="fac97-142">Haga clic en L. MAT y versión de L. MAT.</span><span class="sxs-lookup"><span data-stu-id="fac97-142">Click BOM and BOM version.</span></span>
6. <span data-ttu-id="fac97-143">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="fac97-143">In the Name field, type a value.</span></span>
    * <span data-ttu-id="fac97-144">Por ejemplo, introduzca BOM_1.</span><span class="sxs-lookup"><span data-stu-id="fac97-144">For example, type BOM_1.</span></span>  
7. <span data-ttu-id="fac97-145">En el campo Sitio, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="fac97-145">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="fac97-146">Para este ejemplo, introduzca o seleccione el Sitio 1.</span><span class="sxs-lookup"><span data-stu-id="fac97-146">For this example, enter or select Site 1.</span></span>  
8. <span data-ttu-id="fac97-147">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="fac97-147">Click OK.</span></span>
9. <span data-ttu-id="fac97-148">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="fac97-148">Click New.</span></span>
10. <span data-ttu-id="fac97-149">En el campo Código de artículo, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="fac97-149">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="fac97-150">Para este ejemplo, introduzca ITEM_A.</span><span class="sxs-lookup"><span data-stu-id="fac97-150">For this example, type ITEM_A.</span></span>  
11. <span data-ttu-id="fac97-151">En el campo Almacén, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="fac97-151">In the Warehouse field, enter or select a value.</span></span>
    * <span data-ttu-id="fac97-152">Para este ejemplo, seleccione 11.</span><span class="sxs-lookup"><span data-stu-id="fac97-152">For this example, select 11.</span></span>  
12. <span data-ttu-id="fac97-153">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="fac97-153">Click New.</span></span>
13. <span data-ttu-id="fac97-154">En el campo Código de artículo, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="fac97-154">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="fac97-155">Para este ejemplo, especifique ITEM_B.</span><span class="sxs-lookup"><span data-stu-id="fac97-155">For this example, type ITEM_B.</span></span>  
14. <span data-ttu-id="fac97-156">En el campo Almacén, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="fac97-156">In the Warehouse field, enter or select a value.</span></span>
    * <span data-ttu-id="fac97-157">Para este ejemplo, introduzca o seleccione 11.</span><span class="sxs-lookup"><span data-stu-id="fac97-157">For this example, enter or select 11.</span></span>  
15. <span data-ttu-id="fac97-158">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="fac97-158">Click New.</span></span>
16. <span data-ttu-id="fac97-159">En el campo Código de artículo, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="fac97-159">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="fac97-160">Para este ejemplo, especifique BOM 2.</span><span class="sxs-lookup"><span data-stu-id="fac97-160">For this example, type BOM_2.</span></span>  
17. <span data-ttu-id="fac97-161">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="fac97-161">In the list, mark the selected row.</span></span>
18. <span data-ttu-id="fac97-162">En el campo Almacén, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="fac97-162">In the Warehouse field, enter or select a value.</span></span>
    * <span data-ttu-id="fac97-163">Para este ejemplo, introduzca o seleccione el almacén 11.</span><span class="sxs-lookup"><span data-stu-id="fac97-163">For this example, enter or select warehouse 11.</span></span>  
19. <span data-ttu-id="fac97-164">Haga clic en Encabezado.</span><span class="sxs-lookup"><span data-stu-id="fac97-164">Click Header.</span></span>
20. <span data-ttu-id="fac97-165">Haga clic en Aprobación para aprobar listas de materiales.</span><span class="sxs-lookup"><span data-stu-id="fac97-165">Click Approval to approve bills of materials.</span></span>
21. <span data-ttu-id="fac97-166">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="fac97-166">Click OK.</span></span>
22. <span data-ttu-id="fac97-167">Haga clic en Aprobar.</span><span class="sxs-lookup"><span data-stu-id="fac97-167">Click Approve.</span></span>
    * <span data-ttu-id="fac97-168">El botón Aprobar se encuentra en la ToolBar en la sección de versiones BOM.</span><span class="sxs-lookup"><span data-stu-id="fac97-168">The Approve button is on the ToolBar in the  BOM versions section.</span></span> <span data-ttu-id="fac97-169">Si no está visible, haga clic en Cabecera en la parte superior derecha de la página de Listas de materiales para mostrar Aprobar.</span><span class="sxs-lookup"><span data-stu-id="fac97-169">If it is invisible, click Header at the upper right of the Bills of materials page to display Approve.</span></span>  
23. <span data-ttu-id="fac97-170">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="fac97-170">Click OK.</span></span>
24. <span data-ttu-id="fac97-171">Haga clic en Activar.</span><span class="sxs-lookup"><span data-stu-id="fac97-171">Click Activate.</span></span>
25. <span data-ttu-id="fac97-172">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="fac97-172">Close the page.</span></span>
26. <span data-ttu-id="fac97-173">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="fac97-173">Close the page.</span></span>
27. <span data-ttu-id="fac97-174">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="fac97-174">Close the page.</span></span>


