--- 
title: "Creación de un plan de materiales para coproductos"
description: "El planificador de producción planifica los requisitos de material para los artículos que son coproductos de la fórmula."
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: DefaultDashboard, SalesOrderProcessingWorkspace, SalesCreateOrder, SalesTable, ReqCreatePlanWorkspace, ReqTransPlanCard, SysQueryForm, ReqTransPo
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 2958f1e5c2e8a0cfa9cc6312f688d3b11b8e013c
ms.contentlocale: es-es
ms.lasthandoff: 09/14/2018

---
# <a name="create-a-material-plan-for-co-products"></a><span data-ttu-id="4e550-103">Creación de un plan de materiales para coproductos</span><span class="sxs-lookup"><span data-stu-id="4e550-103">Create a material plan for co products</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="4e550-104">El planificador de producción planifica los requisitos de material para los artículos que son coproductos de la fórmula.</span><span class="sxs-lookup"><span data-stu-id="4e550-104">The production planner plans the material requirements for items that are formula co-products.</span></span> <span data-ttu-id="4e550-105">La empresa de datos de demostración utilizada para crear este procedimiento es USP2.</span><span class="sxs-lookup"><span data-stu-id="4e550-105">The demo data company used to create this procedure is USP2.</span></span>


## <a name="create-requirement-for-a-co-product"></a><span data-ttu-id="4e550-106">Creación de un requisito para un coproducto</span><span class="sxs-lookup"><span data-stu-id="4e550-106">Create requirement for a co-product</span></span>
1. <span data-ttu-id="4e550-107">Vaya al panel predeterminado.</span><span class="sxs-lookup"><span data-stu-id="4e550-107">Go to Default dashboard.</span></span>
2. <span data-ttu-id="4e550-108">Haga clic en Consulta y procesamiento de pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="4e550-108">Click Sales order processing and inquiry.</span></span>
3. <span data-ttu-id="4e550-109">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="4e550-109">Click New.</span></span>
4. <span data-ttu-id="4e550-110">Haga clic en Pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="4e550-110">Click Sales order.</span></span>
5. <span data-ttu-id="4e550-111">En el campo Cuenta de cliente, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="4e550-111">In the Customer account field, type a value.</span></span>
    * <span data-ttu-id="4e550-112">Ejemplo: US-001</span><span class="sxs-lookup"><span data-stu-id="4e550-112">Example: US-001</span></span>  
6. <span data-ttu-id="4e550-113">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="4e550-113">Click OK.</span></span>
7. <span data-ttu-id="4e550-114">En el campo Código de artículo, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="4e550-114">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="4e550-115">Ejemplo: P6003</span><span class="sxs-lookup"><span data-stu-id="4e550-115">Example: P6003</span></span>  
8. <span data-ttu-id="4e550-116">En el campo Cantidad, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="4e550-116">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="4e550-117">Ejemplo: 50000</span><span class="sxs-lookup"><span data-stu-id="4e550-117">Example: 50000</span></span>  
9. <span data-ttu-id="4e550-118">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="4e550-118">Click Save.</span></span>

## <a name="create-a-material-plan-for-co-products"></a><span data-ttu-id="4e550-119">Crear un plan de materiales para coproductos</span><span class="sxs-lookup"><span data-stu-id="4e550-119">Create a material plan for co-products</span></span>
1. <span data-ttu-id="4e550-120">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="4e550-120">Close the page.</span></span>
2. <span data-ttu-id="4e550-121">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="4e550-121">Close the page.</span></span>
3. <span data-ttu-id="4e550-122">Haga clic en Planificación maestra.</span><span class="sxs-lookup"><span data-stu-id="4e550-122">Click Master planning.</span></span>
4. <span data-ttu-id="4e550-123">En el campo Plan, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="4e550-123">In the Plan field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="4e550-124">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="4e550-124">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="4e550-125">Ejemplo: Plan maestro</span><span class="sxs-lookup"><span data-stu-id="4e550-125">Example: MasterPlan</span></span>  
6. <span data-ttu-id="4e550-126">Haga clic en Ejecutar.</span><span class="sxs-lookup"><span data-stu-id="4e550-126">Click Run.</span></span>
7. <span data-ttu-id="4e550-127">Expanda o contraiga la sección Registros que incluir.</span><span class="sxs-lookup"><span data-stu-id="4e550-127">Expand or collapse the Records to include section.</span></span>
8. <span data-ttu-id="4e550-128">Haga clic en Filtro.</span><span class="sxs-lookup"><span data-stu-id="4e550-128">Click Filter.</span></span>
9. <span data-ttu-id="4e550-129">En la lista, seleccione la fila para Campo = Número de artículo.</span><span class="sxs-lookup"><span data-stu-id="4e550-129">In the list, select the row for Field = Item number.</span></span>
10. <span data-ttu-id="4e550-130">En el campo Criterios, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="4e550-130">In the Criteria field, type a value.</span></span>
    * <span data-ttu-id="4e550-131">Ejemplo: P6003</span><span class="sxs-lookup"><span data-stu-id="4e550-131">Example: P6003</span></span>  
11. <span data-ttu-id="4e550-132">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="4e550-132">Click OK.</span></span>
12. <span data-ttu-id="4e550-133">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="4e550-133">Click OK.</span></span>
13. <span data-ttu-id="4e550-134">Haga clic en Pedidos planificados.</span><span class="sxs-lookup"><span data-stu-id="4e550-134">Click Planned orders.</span></span>
14. <span data-ttu-id="4e550-135">Use el filtro rápido para buscar registros.</span><span class="sxs-lookup"><span data-stu-id="4e550-135">Use the Quick Filter to find records.</span></span> <span data-ttu-id="4e550-136">Por ejemplo, filtre por el campo Número de artículo con un valor de "P6000".</span><span class="sxs-lookup"><span data-stu-id="4e550-136">For example, filter on the Item number field with a value of 'P6000'.</span></span>
    * <span data-ttu-id="4e550-137">Filtre por el producto de fórmula que tiene como coproducto el producto para el cual ha creado un pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="4e550-137">Filter by the formula item that has as co-product of the item that you created a sales order for.</span></span>  
15. <span data-ttu-id="4e550-138">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="4e550-138">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="4e550-139">Seleccione cualquiera de las filas que haya devuelto el filtro.</span><span class="sxs-lookup"><span data-stu-id="4e550-139">Select any of the rows returned by the filter.</span></span>  
16. <span data-ttu-id="4e550-140">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="4e550-140">In the list, click the link in the selected row.</span></span>
17. <span data-ttu-id="4e550-141">Expanda o contraiga la sección Diagrama de árbol.</span><span class="sxs-lookup"><span data-stu-id="4e550-141">Expand or collapse the Pegging section.</span></span>
18. <span data-ttu-id="4e550-142">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="4e550-142">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="4e550-143">El pedido planificado se adjunta al pedido de ventas para el coproducto.</span><span class="sxs-lookup"><span data-stu-id="4e550-143">The planned order is pegged to the sales order for the co-product.</span></span>  
19. <span data-ttu-id="4e550-144">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="4e550-144">Close the page.</span></span>

## <a name="create-requirement-for-a-co-product"></a><span data-ttu-id="4e550-145">Creación de un requisito para un coproducto</span><span class="sxs-lookup"><span data-stu-id="4e550-145">Create requirement for a co-product</span></span>
1. <span data-ttu-id="4e550-146">Vaya al panel predeterminado.</span><span class="sxs-lookup"><span data-stu-id="4e550-146">Go to Default dashboard.</span></span>
2. <span data-ttu-id="4e550-147">Haga clic en Consulta y procesamiento de pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="4e550-147">Click Sales order processing and inquiry.</span></span>
3. <span data-ttu-id="4e550-148">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="4e550-148">Click New.</span></span>
4. <span data-ttu-id="4e550-149">Haga clic en Pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="4e550-149">Click Sales order.</span></span>
5. <span data-ttu-id="4e550-150">En el campo Cuenta de cliente, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="4e550-150">In the Customer account field, type a value.</span></span>
    * <span data-ttu-id="4e550-151">Ejemplo: US-001</span><span class="sxs-lookup"><span data-stu-id="4e550-151">Example: US-001</span></span>  
6. <span data-ttu-id="4e550-152">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="4e550-152">Click OK.</span></span>
7. <span data-ttu-id="4e550-153">En el campo Código de artículo, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="4e550-153">In the Item number field, type a value.</span></span>
    * <span data-ttu-id="4e550-154">Ejemplo: P6003</span><span class="sxs-lookup"><span data-stu-id="4e550-154">Example: P6003</span></span>  
8. <span data-ttu-id="4e550-155">En el campo Cantidad, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="4e550-155">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="4e550-156">Ejemplo: 50000</span><span class="sxs-lookup"><span data-stu-id="4e550-156">Example: 50000</span></span>  
9. <span data-ttu-id="4e550-157">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="4e550-157">Click Save.</span></span>

## <a name="create-a-material-plan-for-co-products"></a><span data-ttu-id="4e550-158">Crear un plan de materiales para coproductos</span><span class="sxs-lookup"><span data-stu-id="4e550-158">Create a material plan for co-products</span></span>
1. <span data-ttu-id="4e550-159">En el campo Plan, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="4e550-159">In the Plan field, click the drop-down button to open the lookup.</span></span>
2. <span data-ttu-id="4e550-160">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="4e550-160">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="4e550-161">Ejemplo: Plan maestro</span><span class="sxs-lookup"><span data-stu-id="4e550-161">Example: MasterPlan</span></span>  
3. <span data-ttu-id="4e550-162">Haga clic en Ejecutar.</span><span class="sxs-lookup"><span data-stu-id="4e550-162">Click Run.</span></span>
4. <span data-ttu-id="4e550-163">Expanda o contraiga la sección Registros que incluir.</span><span class="sxs-lookup"><span data-stu-id="4e550-163">Expand or collapse the Records to include section.</span></span>
5. <span data-ttu-id="4e550-164">Haga clic en Filtro.</span><span class="sxs-lookup"><span data-stu-id="4e550-164">Click Filter.</span></span>
6. <span data-ttu-id="4e550-165">En la lista, seleccione la fila para Campo = Número de artículo.</span><span class="sxs-lookup"><span data-stu-id="4e550-165">In the list, select the row for Field = Item number.</span></span>
7. <span data-ttu-id="4e550-166">En el campo Criterios, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="4e550-166">In the Criteria field, type a value.</span></span>
    * <span data-ttu-id="4e550-167">Ejemplo: P6003</span><span class="sxs-lookup"><span data-stu-id="4e550-167">Example: P6003</span></span>  
8. <span data-ttu-id="4e550-168">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="4e550-168">Click OK.</span></span>
9. <span data-ttu-id="4e550-169">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="4e550-169">Click OK.</span></span>
10. <span data-ttu-id="4e550-170">Haga clic en Pedidos planificados.</span><span class="sxs-lookup"><span data-stu-id="4e550-170">Click Planned orders.</span></span>
11. <span data-ttu-id="4e550-171">Use el filtro rápido para buscar registros.</span><span class="sxs-lookup"><span data-stu-id="4e550-171">Use the Quick Filter to find records.</span></span> <span data-ttu-id="4e550-172">Por ejemplo, filtre por el campo Número de artículo con un valor de "P6000".</span><span class="sxs-lookup"><span data-stu-id="4e550-172">For example, filter on the Item number field with a value of 'P6000'.</span></span>
    * <span data-ttu-id="4e550-173">Filtre por el producto de fórmula que tiene como coproducto el producto para el cual ha creado un pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="4e550-173">Filter by the formula item that has as co-product of the item that you created a sales order for.</span></span>  
12. <span data-ttu-id="4e550-174">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="4e550-174">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="4e550-175">Seleccione cualquiera de las filas que haya devuelto el filtro.</span><span class="sxs-lookup"><span data-stu-id="4e550-175">Select any of the rows returned by the filter.</span></span>  
13. <span data-ttu-id="4e550-176">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="4e550-176">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="4e550-177">Expanda o contraiga la sección Diagrama de árbol.</span><span class="sxs-lookup"><span data-stu-id="4e550-177">Expand or collapse the Pegging section.</span></span>
15. <span data-ttu-id="4e550-178">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="4e550-178">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="4e550-179">El pedido planificado se adjunta al pedido de ventas para el coproducto.</span><span class="sxs-lookup"><span data-stu-id="4e550-179">The planned order is pegged to the sales order for the co-product.</span></span>  
16. <span data-ttu-id="4e550-180">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="4e550-180">Close the page.</span></span>
17. <span data-ttu-id="4e550-181">Haga clic en Planificación maestra.</span><span class="sxs-lookup"><span data-stu-id="4e550-181">Click Master planning.</span></span>
18. <span data-ttu-id="4e550-182">Vaya a Planificación maestra > Configuración > Parámetros de planificación maestra.</span><span class="sxs-lookup"><span data-stu-id="4e550-182">Go to Master planning > Setup > Master planning parameters.</span></span>
19. <span data-ttu-id="4e550-183">Seleccione No en el campo Deshabilitar todos los procesos de planificación.</span><span class="sxs-lookup"><span data-stu-id="4e550-183">Select No in the Disable all planning processes field.</span></span>
20. <span data-ttu-id="4e550-184">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="4e550-184">Close the page.</span></span>


