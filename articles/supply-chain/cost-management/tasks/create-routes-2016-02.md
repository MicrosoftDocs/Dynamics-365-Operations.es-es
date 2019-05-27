---
title: Crear rutas (febrero de 2016 únicamente)
description: Esta tarea se centra en la creación de rutas de producción para un producto terminado y para un producto semiterminado.
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
ms.openlocfilehash: 63ad2cc0c41a5931750dffbfc64bc7ce965a1da4
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1563213"
---
# <a name="create-routes-february-2016-only"></a><span data-ttu-id="64bc2-103">Crear rutas (febrero de 2016 únicamente)</span><span class="sxs-lookup"><span data-stu-id="64bc2-103">Create routes (February 2016 only)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="64bc2-104">Esta tarea se centra en la creación de rutas de producción para un producto terminado y para un producto semiterminado.</span><span class="sxs-lookup"><span data-stu-id="64bc2-104">This task focuses on creating the production routes for a finished product and a semi-finished product.</span></span> <span data-ttu-id="64bc2-105">Es la quinta tarea en las series de cálculo BOM.</span><span class="sxs-lookup"><span data-stu-id="64bc2-105">It is the fifth task in the BOM calculation series.</span></span> <span data-ttu-id="64bc2-106">La empresa de datos de prueba utilizada para crear esta tarea es USMF.</span><span class="sxs-lookup"><span data-stu-id="64bc2-106">The demo data company used to create this task is USMF.</span></span>


## <a name="create-a-route-for-a-semi-finished-product"></a><span data-ttu-id="64bc2-107">Cree una ruta para un producto semi-acabado.</span><span class="sxs-lookup"><span data-stu-id="64bc2-107">Create a route for a semi-finished product</span></span>
1. <span data-ttu-id="64bc2-108">Vaya a Gestión de información de productos > Productos > Productos emitidos.</span><span class="sxs-lookup"><span data-stu-id="64bc2-108">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="64bc2-109">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="64bc2-109">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="64bc2-110">Seleccione el número de artículo BOM_2.</span><span class="sxs-lookup"><span data-stu-id="64bc2-110">Select the item number BOM_2.</span></span>  
3. <span data-ttu-id="64bc2-111">En el panel de acciones, haga clic en Ingeniero.</span><span class="sxs-lookup"><span data-stu-id="64bc2-111">On the Action Pane, click Engineer.</span></span>
4. <span data-ttu-id="64bc2-112">Haga clic en Ruta.</span><span class="sxs-lookup"><span data-stu-id="64bc2-112">Click Route.</span></span>
5. <span data-ttu-id="64bc2-113">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="64bc2-113">Click New.</span></span>
6. <span data-ttu-id="64bc2-114">Haga clic en Ruta y en versión de ruta.</span><span class="sxs-lookup"><span data-stu-id="64bc2-114">Click Route and route version.</span></span>
7. <span data-ttu-id="64bc2-115">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="64bc2-115">In the Description field, type a value.</span></span>
    * <span data-ttu-id="64bc2-116">Por ejemplo, introduzca ROUTE_2.</span><span class="sxs-lookup"><span data-stu-id="64bc2-116">For example, type ROUTE_2.</span></span>  
8. <span data-ttu-id="64bc2-117">En el campo Sitio, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="64bc2-117">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="64bc2-118">Para este ejemplo, introduzca o seleccione el Sitio 1.</span><span class="sxs-lookup"><span data-stu-id="64bc2-118">For this example, enter or select Site 1.</span></span>  
9. <span data-ttu-id="64bc2-119">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="64bc2-119">Click OK.</span></span>
10. <span data-ttu-id="64bc2-120">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="64bc2-120">Click New.</span></span>
11. <span data-ttu-id="64bc2-121">En el campo Operación, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="64bc2-121">In the Operation field, enter or select a value.</span></span>
    * <span data-ttu-id="64bc2-122">Para este ejemplo, seleccione Ensamblado.</span><span class="sxs-lookup"><span data-stu-id="64bc2-122">For this example, select Assembly.</span></span>  
12. <span data-ttu-id="64bc2-123">En el campo Tiempo de ejecución, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="64bc2-123">In the Run time field, enter a number.</span></span>
    * <span data-ttu-id="64bc2-124">Por ejemplo, escriba 1.</span><span class="sxs-lookup"><span data-stu-id="64bc2-124">For example, type 1.</span></span> <span data-ttu-id="64bc2-125">Los tiempos de ejecución suelen ser parte del precio calculado para un artículo.</span><span class="sxs-lookup"><span data-stu-id="64bc2-125">Run times are often part of the price that is calculated for an item.</span></span>  
13. <span data-ttu-id="64bc2-126">En el campo Grupo de rutas, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="64bc2-126">In the Route group field, enter or select a value.</span></span>
    * <span data-ttu-id="64bc2-127">Para este ejemplo, seleccione Std.</span><span class="sxs-lookup"><span data-stu-id="64bc2-127">For this example, select Std.</span></span>  
14. <span data-ttu-id="64bc2-128">Haga clic en la pestaña Configurar.</span><span class="sxs-lookup"><span data-stu-id="64bc2-128">Click the Setup tab.</span></span>
15. <span data-ttu-id="64bc2-129">En el campo Categoría de configuración, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="64bc2-129">In the Setup category field, enter or select a value.</span></span>
    * <span data-ttu-id="64bc2-130">Para este ejemplo, seleccione Ensamblado.</span><span class="sxs-lookup"><span data-stu-id="64bc2-130">For this example, select Assembly.</span></span>  
16. <span data-ttu-id="64bc2-131">Haga clic en la ficha Tiempos.</span><span class="sxs-lookup"><span data-stu-id="64bc2-131">Click the Times tab.</span></span>
17. <span data-ttu-id="64bc2-132">En el campo Tiempo de configuración, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="64bc2-132">In the Setup time field, enter a number.</span></span>
    * <span data-ttu-id="64bc2-133">Para este ejemplo, especifique 1.</span><span class="sxs-lookup"><span data-stu-id="64bc2-133">For this example, type 1.</span></span> <span data-ttu-id="64bc2-134">Los tiempos de configuración suelen ser parte de un precio calculado para un artículo.</span><span class="sxs-lookup"><span data-stu-id="64bc2-134">Setup times are often part of the price that is calculated for an item.</span></span>  
18. <span data-ttu-id="64bc2-135">En el Panel de acciones, haga clic en Versión de ruta.</span><span class="sxs-lookup"><span data-stu-id="64bc2-135">On the Action Pane, click Route version.</span></span>
19. <span data-ttu-id="64bc2-136">Haga clic en Aprobar.</span><span class="sxs-lookup"><span data-stu-id="64bc2-136">Click Approve.</span></span>
20. <span data-ttu-id="64bc2-137">Seleccione Sí en ¿Desea aprobar también la ruta? .</span><span class="sxs-lookup"><span data-stu-id="64bc2-137">Select Yes in the Do you also want to approve the route? field.</span></span>
21. <span data-ttu-id="64bc2-138">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="64bc2-138">Click OK.</span></span>
22. <span data-ttu-id="64bc2-139">En el Panel de acciones, haga clic en Versión de ruta.</span><span class="sxs-lookup"><span data-stu-id="64bc2-139">On the Action Pane, click Route version.</span></span>
23. <span data-ttu-id="64bc2-140">Haga clic en Activar.</span><span class="sxs-lookup"><span data-stu-id="64bc2-140">Click Activate.</span></span>
24. <span data-ttu-id="64bc2-141">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="64bc2-141">Close the page.</span></span>
25. <span data-ttu-id="64bc2-142">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="64bc2-142">Close the page.</span></span>

## <a name="create-a-route-for-a-finished-product"></a><span data-ttu-id="64bc2-143">Cree una ruta para un producto acabado</span><span class="sxs-lookup"><span data-stu-id="64bc2-143">Create a route for a finished product</span></span>
1. <span data-ttu-id="64bc2-144">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="64bc2-144">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="64bc2-145">Seleccione el número de artículo BOM_1.</span><span class="sxs-lookup"><span data-stu-id="64bc2-145">Select the item number BOM_1.</span></span>  
2. <span data-ttu-id="64bc2-146">En el panel de acciones, haga clic en Ingeniero.</span><span class="sxs-lookup"><span data-stu-id="64bc2-146">On the Action Pane, click Engineer.</span></span>
3. <span data-ttu-id="64bc2-147">Haga clic en Ruta.</span><span class="sxs-lookup"><span data-stu-id="64bc2-147">Click Route.</span></span>
4. <span data-ttu-id="64bc2-148">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="64bc2-148">Click New.</span></span>
5. <span data-ttu-id="64bc2-149">Haga clic en Ruta y en versión de ruta.</span><span class="sxs-lookup"><span data-stu-id="64bc2-149">Click Route and route version.</span></span>
6. <span data-ttu-id="64bc2-150">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="64bc2-150">In the Description field, type a value.</span></span>
    * <span data-ttu-id="64bc2-151">Para este ejemplo, introduzca ROUTE_1.</span><span class="sxs-lookup"><span data-stu-id="64bc2-151">For this example, type ROUTE_1.</span></span>  
7. <span data-ttu-id="64bc2-152">En el campo Sitio, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="64bc2-152">In the Site field, enter or select a value.</span></span>
    * <span data-ttu-id="64bc2-153">Para este ejemplo, introduzca o seleccione el Sitio 1.</span><span class="sxs-lookup"><span data-stu-id="64bc2-153">For this example, enter or select Site 1.</span></span>  
8. <span data-ttu-id="64bc2-154">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="64bc2-154">Click OK.</span></span>
9. <span data-ttu-id="64bc2-155">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="64bc2-155">Click New.</span></span>
10. <span data-ttu-id="64bc2-156">En el campo Operación, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="64bc2-156">In the Operation field, enter or select a value.</span></span>
    * <span data-ttu-id="64bc2-157">Para este ejemplo, seleccione Embalaje.</span><span class="sxs-lookup"><span data-stu-id="64bc2-157">For this example, select Packing.</span></span>  
11. <span data-ttu-id="64bc2-158">En el campo Tiempo de ejecución, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="64bc2-158">In the Run time field, enter a number.</span></span>
    * <span data-ttu-id="64bc2-159">Para este ejemplo, especifique 1.</span><span class="sxs-lookup"><span data-stu-id="64bc2-159">For this example, type 1.</span></span>  
12. <span data-ttu-id="64bc2-160">En el campo Grupo de rutas, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="64bc2-160">In the Route group field, enter or select a value.</span></span>
    * <span data-ttu-id="64bc2-161">Para este ejemplo, seleccione Std.</span><span class="sxs-lookup"><span data-stu-id="64bc2-161">For this example, select Std.</span></span>  
13. <span data-ttu-id="64bc2-162">Haga clic en la pestaña Configurar.</span><span class="sxs-lookup"><span data-stu-id="64bc2-162">Click the Setup tab.</span></span>
14. <span data-ttu-id="64bc2-163">En el campo Categoría de configuración, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="64bc2-163">In the Setup category field, enter or select a value.</span></span>
    * <span data-ttu-id="64bc2-164">Para este ejemplo, seleccione Embalaje.</span><span class="sxs-lookup"><span data-stu-id="64bc2-164">For this example, select Packing.</span></span>  
15. <span data-ttu-id="64bc2-165">Haga clic en la ficha Tiempos.</span><span class="sxs-lookup"><span data-stu-id="64bc2-165">Click the Times tab.</span></span>
16. <span data-ttu-id="64bc2-166">En el campo Tiempo de configuración, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="64bc2-166">In the Setup time field, enter a number.</span></span>
    * <span data-ttu-id="64bc2-167">Para este ejemplo, especifique 1.</span><span class="sxs-lookup"><span data-stu-id="64bc2-167">For this example, type 1.</span></span>  
17. <span data-ttu-id="64bc2-168">En el Panel de acciones, haga clic en Versión de ruta.</span><span class="sxs-lookup"><span data-stu-id="64bc2-168">On the Action Pane, click Route version.</span></span>
18. <span data-ttu-id="64bc2-169">Haga clic en Aprobar.</span><span class="sxs-lookup"><span data-stu-id="64bc2-169">Click Approve.</span></span>
19. <span data-ttu-id="64bc2-170">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="64bc2-170">Click OK.</span></span>
20. <span data-ttu-id="64bc2-171">En el Panel de acciones, haga clic en Versión de ruta.</span><span class="sxs-lookup"><span data-stu-id="64bc2-171">On the Action Pane, click Route version.</span></span>
21. <span data-ttu-id="64bc2-172">Haga clic en Activar.</span><span class="sxs-lookup"><span data-stu-id="64bc2-172">Click Activate.</span></span>
22. <span data-ttu-id="64bc2-173">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="64bc2-173">Close the page.</span></span>
23. <span data-ttu-id="64bc2-174">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="64bc2-174">Close the page.</span></span>

## <a name="enable-automatic-consumption-of-setup-time"></a><span data-ttu-id="64bc2-175">Habilite el consumo automático del tiempo de configuración</span><span class="sxs-lookup"><span data-stu-id="64bc2-175">Enable automatic consumption of setup time</span></span>
1. <span data-ttu-id="64bc2-176">Vaya al Control de producción > Configuración > Rutas > Grupos de rutas.</span><span class="sxs-lookup"><span data-stu-id="64bc2-176">Go to Production control > Setup > Routes > Route groups.</span></span>
2. <span data-ttu-id="64bc2-177">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="64bc2-177">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="64bc2-178">Seleccione Std en la lista.</span><span class="sxs-lookup"><span data-stu-id="64bc2-178">Select Std in the list.</span></span>  
3. <span data-ttu-id="64bc2-179">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="64bc2-179">Click Edit.</span></span>
4. <span data-ttu-id="64bc2-180">Seleccione Sí en el campo Tiempo de configuración.</span><span class="sxs-lookup"><span data-stu-id="64bc2-180">Select Yes in the Setup time field.</span></span>
    * <span data-ttu-id="64bc2-181">Los tiempos de configuración suelen ser parte de un precio calculado para un artículo.</span><span class="sxs-lookup"><span data-stu-id="64bc2-181">Setup times are often part of the price that is calculated for an item.</span></span>  
5. <span data-ttu-id="64bc2-182">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="64bc2-182">Click Save.</span></span>
6. <span data-ttu-id="64bc2-183">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="64bc2-183">Close the page.</span></span>

