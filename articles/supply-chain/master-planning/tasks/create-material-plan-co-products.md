---
title: Creación de un plan de materiales para coproductos
description: El planificador de producción planifica los requisitos de material para los artículos que son coproductos de la fórmula.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, SalesOrderProcessingWorkspace, SalesCreateOrder, SalesTable, ReqCreatePlanWorkspace, ReqTransPlanCard, SysQueryForm, ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b51e4b4d00da2babb5128d8c4c22139b0c1853d4
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2021
ms.locfileid: "5920738"
---
# <a name="create-a-material-plan-for-co-products"></a><span data-ttu-id="e0c9a-103">Creación de un plan de materiales para coproductos</span><span class="sxs-lookup"><span data-stu-id="e0c9a-103">Create a material plan for co products</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="e0c9a-104">El planificador de producción planifica los requisitos de material para los artículos que son coproductos de la fórmula.</span><span class="sxs-lookup"><span data-stu-id="e0c9a-104">The production planner plans the material requirements for items that are formula co-products.</span></span> <span data-ttu-id="e0c9a-105">La empresa de datos de demostración utilizada para crear este procedimiento es USP2.</span><span class="sxs-lookup"><span data-stu-id="e0c9a-105">The demo data company used to create this procedure is USP2.</span></span>

## <a name="create-requirement-for-a-co-product"></a><span data-ttu-id="e0c9a-106">Creación de un requisito para un coproducto</span><span class="sxs-lookup"><span data-stu-id="e0c9a-106">Create requirement for a co-product</span></span>

1. <span data-ttu-id="e0c9a-107">Vaya a **Ventas y marketing \> Espacios de trabajo \> Procesamiento y consulta de pedidos de venta**.</span><span class="sxs-lookup"><span data-stu-id="e0c9a-107">Go to **Sales and marketing \> Workspaces \> Sales order processing and inquiry**.</span></span>
1. <span data-ttu-id="e0c9a-108">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="e0c9a-108">Select **New**.</span></span>
1. <span data-ttu-id="e0c9a-109">Seleccione **Pedido de ventas**.</span><span class="sxs-lookup"><span data-stu-id="e0c9a-109">Select **Sales order**.</span></span>
1. <span data-ttu-id="e0c9a-110">En el campo **Cuenta de cliente**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="e0c9a-110">In the **Customer account** field, type a value.</span></span>
    * <span data-ttu-id="e0c9a-111">Ejemplo: US-001</span><span class="sxs-lookup"><span data-stu-id="e0c9a-111">Example: US-001</span></span>  
1. <span data-ttu-id="e0c9a-112">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e0c9a-112">Select **OK**.</span></span>
1. <span data-ttu-id="e0c9a-113">En el campo **Código de artículo**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="e0c9a-113">In the **Item number** field, type a value.</span></span>
    * <span data-ttu-id="e0c9a-114">Ejemplo: P6003</span><span class="sxs-lookup"><span data-stu-id="e0c9a-114">Example: P6003</span></span>  
1. <span data-ttu-id="e0c9a-115">En el campo **Cantidad**, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="e0c9a-115">In the **Quantity** field, enter a number.</span></span>
    * <span data-ttu-id="e0c9a-116">Ejemplo: 50000</span><span class="sxs-lookup"><span data-stu-id="e0c9a-116">Example: 50000</span></span>  
1. <span data-ttu-id="e0c9a-117">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="e0c9a-117">Select **Save**.</span></span>

## <a name="create-a-material-plan-for-co-products"></a><span data-ttu-id="e0c9a-118">Crear un plan de materiales para coproductos</span><span class="sxs-lookup"><span data-stu-id="e0c9a-118">Create a material plan for co-products</span></span>

1. <span data-ttu-id="e0c9a-119">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="e0c9a-119">Close the page.</span></span>
1. <span data-ttu-id="e0c9a-120">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="e0c9a-120">Close the page.</span></span>
1. <span data-ttu-id="e0c9a-121">Seleccione **Planificación maestra**.</span><span class="sxs-lookup"><span data-stu-id="e0c9a-121">Select **Master planning**.</span></span>
1. <span data-ttu-id="e0c9a-122">En el campo **Plan**, seleccione el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="e0c9a-122">In the **Plan** field, select the drop-down button to open the lookup.</span></span>
1. <span data-ttu-id="e0c9a-123">En la lista, seleccione el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="e0c9a-123">In the list, select the link in the selected row.</span></span>
    * <span data-ttu-id="e0c9a-124">Ejemplo: Plan maestro</span><span class="sxs-lookup"><span data-stu-id="e0c9a-124">Example: MasterPlan</span></span>  
1. <span data-ttu-id="e0c9a-125">Seleccione **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="e0c9a-125">Select **Run**.</span></span>
1. <span data-ttu-id="e0c9a-126">Expanda o contraiga la sección **Registros a incluir**.</span><span class="sxs-lookup"><span data-stu-id="e0c9a-126">Expand or collapse the **Records to include** section.</span></span>
1. <span data-ttu-id="e0c9a-127">Seleccione **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="e0c9a-127">Select **Filter**.</span></span>
1. <span data-ttu-id="e0c9a-128">En la lista, seleccione la fila de **Campo** = *Número de artículo*.</span><span class="sxs-lookup"><span data-stu-id="e0c9a-128">In the list, select the row for **Field** = *Item number*.</span></span>
1. <span data-ttu-id="e0c9a-129">En el campo **Criterios**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="e0c9a-129">In the **Criteria** field, type a value.</span></span>
    * <span data-ttu-id="e0c9a-130">Ejemplo: P6003</span><span class="sxs-lookup"><span data-stu-id="e0c9a-130">Example: P6003</span></span>  
1. <span data-ttu-id="e0c9a-131">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e0c9a-131">Select **OK**.</span></span>
1. <span data-ttu-id="e0c9a-132">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e0c9a-132">Select **OK**.</span></span>
1. <span data-ttu-id="e0c9a-133">Seleccione **Pedidos planificados**.</span><span class="sxs-lookup"><span data-stu-id="e0c9a-133">Select **Planned orders**.</span></span>
1. <span data-ttu-id="e0c9a-134">Use el filtro rápido para buscar registros.</span><span class="sxs-lookup"><span data-stu-id="e0c9a-134">Use the Quick Filter to find records.</span></span> <span data-ttu-id="e0c9a-135">Por ejemplo, filtre por el campo **Número de artículo** con un valor de 'P6000'.</span><span class="sxs-lookup"><span data-stu-id="e0c9a-135">For example, filter on the **Item number** field with a value of 'P6000'.</span></span>
    * <span data-ttu-id="e0c9a-136">Filtre por el producto de fórmula que tiene como coproducto el producto para el cual ha creado un pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="e0c9a-136">Filter by the formula item that has as co-product of the item that you created a sales order for.</span></span>  
1. <span data-ttu-id="e0c9a-137">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="e0c9a-137">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="e0c9a-138">Seleccione cualquiera de las filas que haya devuelto el filtro.</span><span class="sxs-lookup"><span data-stu-id="e0c9a-138">Select any of the rows returned by the filter.</span></span>  
1. <span data-ttu-id="e0c9a-139">En la lista, seleccione el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="e0c9a-139">In the list, select the link in the selected row.</span></span>
1. <span data-ttu-id="e0c9a-140">Expanda la sección **Diagrama de árbol**.</span><span class="sxs-lookup"><span data-stu-id="e0c9a-140">Expand the **Pegging** section.</span></span>
1. <span data-ttu-id="e0c9a-141">En la lista, seleccione el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="e0c9a-141">In the list, select the link in the selected row.</span></span>
    * <span data-ttu-id="e0c9a-142">El pedido planificado se adjunta al pedido de ventas para el coproducto.</span><span class="sxs-lookup"><span data-stu-id="e0c9a-142">The planned order is pegged to the sales order for the co-product.</span></span>  
1. <span data-ttu-id="e0c9a-143">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="e0c9a-143">Close the page.</span></span>

## <a name="create-a-second-requirement-for-a-co-product"></a><span data-ttu-id="e0c9a-144">Creación de un segundo requisito para un coproducto</span><span class="sxs-lookup"><span data-stu-id="e0c9a-144">Create a second requirement for a co-product</span></span>

1. <span data-ttu-id="e0c9a-145">Vaya a **Ventas y marketing \> Espacios de trabajo \> Procesamiento y consulta de pedidos de venta**.</span><span class="sxs-lookup"><span data-stu-id="e0c9a-145">Go to **Sales and marketing \> Workspaces \> Sales order processing and inquiry**.</span></span>
1. <span data-ttu-id="e0c9a-146">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="e0c9a-146">Select **New**.</span></span>
1. <span data-ttu-id="e0c9a-147">Seleccione **Pedido de ventas**.</span><span class="sxs-lookup"><span data-stu-id="e0c9a-147">Select **Sales order**.</span></span>
1. <span data-ttu-id="e0c9a-148">En el campo **Cuenta de cliente**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="e0c9a-148">In the **Customer account** field, type a value.</span></span>
    * <span data-ttu-id="e0c9a-149">Ejemplo: US-001</span><span class="sxs-lookup"><span data-stu-id="e0c9a-149">Example: US-001</span></span>  
1. <span data-ttu-id="e0c9a-150">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e0c9a-150">Select **OK**.</span></span>
1. <span data-ttu-id="e0c9a-151">En el campo **Código de artículo**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="e0c9a-151">In the **Item number** field, type a value.</span></span>
    * <span data-ttu-id="e0c9a-152">Ejemplo: P6003</span><span class="sxs-lookup"><span data-stu-id="e0c9a-152">Example: P6003</span></span>  
1. <span data-ttu-id="e0c9a-153">En el campo **Cantidad**, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="e0c9a-153">In the **Quantity** field, enter a number.</span></span>
    * <span data-ttu-id="e0c9a-154">Ejemplo: 50000</span><span class="sxs-lookup"><span data-stu-id="e0c9a-154">Example: 50000</span></span>  
1. <span data-ttu-id="e0c9a-155">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="e0c9a-155">Select **Save**.</span></span>

## <a name="create-a-second-material-plan-for-co-products"></a><span data-ttu-id="e0c9a-156">Crear un segundo plan de materiales para coproductos</span><span class="sxs-lookup"><span data-stu-id="e0c9a-156">Create a second material plan for co-products</span></span>

1. <span data-ttu-id="e0c9a-157">En el campo **Plan**, seleccione el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="e0c9a-157">In the **Plan** field, select the drop-down button to open the lookup.</span></span>
2. <span data-ttu-id="e0c9a-158">En la lista, seleccione el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="e0c9a-158">In the list, select the link in the selected row.</span></span>
    * <span data-ttu-id="e0c9a-159">Ejemplo: Plan maestro</span><span class="sxs-lookup"><span data-stu-id="e0c9a-159">Example: MasterPlan</span></span>  
3. <span data-ttu-id="e0c9a-160">Seleccione **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="e0c9a-160">Select **Run**.</span></span>
4. <span data-ttu-id="e0c9a-161">Expanda o contraiga la sección **Registros a incluir**.</span><span class="sxs-lookup"><span data-stu-id="e0c9a-161">Expand or collapse the **Records to include** section.</span></span>
5. <span data-ttu-id="e0c9a-162">Seleccione **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="e0c9a-162">Select **Filter**.</span></span>
6. <span data-ttu-id="e0c9a-163">En la lista, seleccione la fila de **Campo** = *Número de artículo*.</span><span class="sxs-lookup"><span data-stu-id="e0c9a-163">In the list, select the row for **Field** = *Item number*.</span></span>
7. <span data-ttu-id="e0c9a-164">En el campo *Criterios*, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="e0c9a-164">In the *Criteria* field, type a value.</span></span>
    * <span data-ttu-id="e0c9a-165">Ejemplo: P6003</span><span class="sxs-lookup"><span data-stu-id="e0c9a-165">Example: P6003</span></span>  
8. <span data-ttu-id="e0c9a-166">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e0c9a-166">Select **OK**.</span></span>
9. <span data-ttu-id="e0c9a-167">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e0c9a-167">Select **OK**.</span></span>
10. <span data-ttu-id="e0c9a-168">Seleccione **Pedidos planificados**.</span><span class="sxs-lookup"><span data-stu-id="e0c9a-168">Select **Planned orders**.</span></span>
11. <span data-ttu-id="e0c9a-169">Use el filtro rápido para buscar registros.</span><span class="sxs-lookup"><span data-stu-id="e0c9a-169">Use the Quick Filter to find records.</span></span> <span data-ttu-id="e0c9a-170">Por ejemplo, filtre por el campo **Número de artículo** con un valor de 'P6000'.</span><span class="sxs-lookup"><span data-stu-id="e0c9a-170">For example, filter on the **Item number** field with a value of 'P6000'.</span></span>
    * <span data-ttu-id="e0c9a-171">Filtre por el producto de fórmula que tiene como coproducto el producto para el cual ha creado un pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="e0c9a-171">Filter by the formula item that has as co-product of the item that you created a sales order for.</span></span>  
12. <span data-ttu-id="e0c9a-172">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="e0c9a-172">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="e0c9a-173">Seleccione cualquiera de las filas que haya devuelto el filtro.</span><span class="sxs-lookup"><span data-stu-id="e0c9a-173">Select any of the rows returned by the filter.</span></span>  
13. <span data-ttu-id="e0c9a-174">En la lista, seleccione el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="e0c9a-174">In the list, select the link in the selected row.</span></span>
14. <span data-ttu-id="e0c9a-175">Expanda o contraiga la sección **Diagrama de árbol**.</span><span class="sxs-lookup"><span data-stu-id="e0c9a-175">Expand or collapse the **Pegging** section.</span></span>
15. <span data-ttu-id="e0c9a-176">En la lista, seleccione el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="e0c9a-176">In the list, select the link in the selected row.</span></span>
    * <span data-ttu-id="e0c9a-177">El pedido planificado se adjunta al pedido de ventas para el coproducto.</span><span class="sxs-lookup"><span data-stu-id="e0c9a-177">The planned order is pegged to the sales order for the co-product.</span></span>  
16. <span data-ttu-id="e0c9a-178">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="e0c9a-178">Close the page.</span></span>
17. <span data-ttu-id="e0c9a-179">Seleccione **Planificación maestra**.</span><span class="sxs-lookup"><span data-stu-id="e0c9a-179">Select **Master planning**.</span></span>
18. <span data-ttu-id="e0c9a-180">Vaya a **Planificación maestra \> Configuración \> Parámetros de planificación maestra**.</span><span class="sxs-lookup"><span data-stu-id="e0c9a-180">Go to **Master planning \> Setup \> Master planning parameters**.</span></span>
19. <span data-ttu-id="e0c9a-181">Seleccione *No* en el campo **Deshabilitar todos los procesos de planificación**.</span><span class="sxs-lookup"><span data-stu-id="e0c9a-181">Select *No* in the **Disable all planning processes** field.</span></span>
20. <span data-ttu-id="e0c9a-182">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="e0c9a-182">Close the page.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]