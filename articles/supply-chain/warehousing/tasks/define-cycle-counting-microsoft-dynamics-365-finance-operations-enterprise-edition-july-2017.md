---
title: Definir el recuento cíclico
description: La cuenta de ciclo es un proceso de almacén que puede usar para revisar artículos de inventario disponibles.
author: MarkusFogelberg
manager: tfehr
ms.date: 08/12/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFMenuItemCycleCount, WHSCycleCountThreshold, WHSCycleCountPlan, WHSCycleCountPlanListPage, WHSParameters, WHSRFMenu, WHSRFMenuItem
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a0b94bcc1c33889f336541f3dd8ba4782fac0261
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5238999"
---
# <a name="define-cycle-counting"></a><span data-ttu-id="8b967-103">Definir el recuento cíclico</span><span class="sxs-lookup"><span data-stu-id="8b967-103">Define cycle counting</span></span> 

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="8b967-104">La cuenta de ciclo es un proceso de almacén que puede usar para revisar artículos de inventario disponibles.</span><span class="sxs-lookup"><span data-stu-id="8b967-104">Cycle counting is a warehouse process that you can use to audit on-hand inventory items.</span></span> <span data-ttu-id="8b967-105">Esta grabación de tarea muestra cómo configurar el valor predeterminado de prioridad de trabajo de recuento; cómo habilitar un elemento de menú de dispositivo móvil para procesar operaciones de selección y recuento; cómo habilitar un activador de umbral de recuento cuando una ubicación quede vacía; cómo habilitar un plan de recuento cíclico para un artículo específico dentro de un almacén concreto.</span><span class="sxs-lookup"><span data-stu-id="8b967-105">This task recording shows how to set up the default counting work priority, enable a mobile device menu item to process both picking and counting operations, enable a counting threshold trigger when a location becomes empty, and enable a cycle counting plan for a specific item in a specific warehouse.</span></span> <span data-ttu-id="8b967-106">Normalmente, estas tareas las realiza el administrador de almacén.</span><span class="sxs-lookup"><span data-stu-id="8b967-106">Typically, these tasks are performed by a warehouse manager.</span></span> <span data-ttu-id="8b967-107">Puede explorar este procedimiento en los datos de la empresa de demostración USMF o utilizar sus propios datos.</span><span class="sxs-lookup"><span data-stu-id="8b967-107">You can go through this procedure in the USMF demo data company or in your own data.</span></span>


## <a name="set-the-priority-of-counting-work"></a><span data-ttu-id="8b967-108">Definición de la prioridad del trabajo de recuento</span><span class="sxs-lookup"><span data-stu-id="8b967-108">Set the priority of counting work</span></span>
1. <span data-ttu-id="8b967-109">En el **Panel de exploración**, vaya a **Módulos > Gestión de almacenes > Configuración > Almacén >Parámetros de gestión de almacenes**.</span><span class="sxs-lookup"><span data-stu-id="8b967-109">In the **Navigation pane**, go to **Modules > Warehouse management > Setup > Warehouse management parameters**.</span></span>
2. <span data-ttu-id="8b967-110">Haga clic en la ficha **Recuento cíclico**.</span><span class="sxs-lookup"><span data-stu-id="8b967-110">Click the **Cycle counting** tab.</span></span>
3. <span data-ttu-id="8b967-111">En el campo **Prioridad de trabajo de recuento cíclico predeterminado**, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="8b967-111">In the **Default cycle count work priority** field, enter a number.</span></span> <span data-ttu-id="8b967-112">Este paso cambia la prioridad del trabajo de recuento cíclico en comparación con otros tipos de trabajo en el almacén.</span><span class="sxs-lookup"><span data-stu-id="8b967-112">This step changes the priority of cycle counting work compared to other types of work in the warehouse.</span></span> <span data-ttu-id="8b967-113">Si especifica un número menor al número de otros tipos de trabajo, aumenta la prioridad de trabajo de recuento cíclico.</span><span class="sxs-lookup"><span data-stu-id="8b967-113">By entering a number that is lower than the number for other types of work, you raise the priority of the cycle counting work.</span></span>  
4. <span data-ttu-id="8b967-114">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="8b967-114">Click **Save**.</span></span>
5. <span data-ttu-id="8b967-115">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="8b967-115">Close the page.</span></span>

## <a name="enable-the-mobile-device"></a><span data-ttu-id="8b967-116">Habilitar el dispositivo móvil</span><span class="sxs-lookup"><span data-stu-id="8b967-116">Enable the mobile device</span></span>
1. <span data-ttu-id="8b967-117">En el **Panel de exploración**, vaya a **Módulos > Administración de módulos > Configuración > Dispositivo móvil > Elementos de menú del dispositivo móvil**.</span><span class="sxs-lookup"><span data-stu-id="8b967-117">In the **Navigation pane**, go to **Modules > Warehouse management > Setup > Mobile device > Mobile device menu items**.</span></span>
2. <span data-ttu-id="8b967-118">Haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="8b967-118">Click **New**.</span></span>
3. <span data-ttu-id="8b967-119">En el campo **Nombre del elemento de menú**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="8b967-119">In the **Menu item name** field, type a value.</span></span>
4. <span data-ttu-id="8b967-120">En el campo **Título**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="8b967-120">In the **Title** field, type a value.</span></span>
5. <span data-ttu-id="8b967-121">En el campo **Modo**, seleccione "Trabajo".</span><span class="sxs-lookup"><span data-stu-id="8b967-121">In the **Mode** field, select 'Work'.</span></span>
6. <span data-ttu-id="8b967-122">Establezca la opción **Usar trabajo existente** en Sí.</span><span class="sxs-lookup"><span data-stu-id="8b967-122">Set the **Use existing work** option to Yes.</span></span> <span data-ttu-id="8b967-123">Cuando establece esta opción en Sí, el sistema buscará trabajo existente cuando se use el elemento de menú de dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="8b967-123">When you set this option to Yes, the system will look for existing work when the mobile device menu item is used.</span></span>  
7. <span data-ttu-id="8b967-124">En el campo **Dirigido por**, seleccione "Dirigido por el sistema".</span><span class="sxs-lookup"><span data-stu-id="8b967-124">In the **Directed by** field, select 'System directed'.</span></span> <span data-ttu-id="8b967-125">Cuando se selecciona "Dirigido por el sistema", se dirigirá al trabajador del almacén a abrir el trabajo que está en las clases definidas de trabajo.</span><span class="sxs-lookup"><span data-stu-id="8b967-125">When "System directed" is selected, the warehouse worker will be directed to open work that is in defined work classes.</span></span> <span data-ttu-id="8b967-126">(Crearemos estas clases de trabajo después.)</span><span class="sxs-lookup"><span data-stu-id="8b967-126">(We will create these work classes next.)</span></span>  
8. <span data-ttu-id="8b967-127">Expanda la ficha desplegable **Clases de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="8b967-127">Expand the **Work classes** fastTab.</span></span> <span data-ttu-id="8b967-128">A continuación, crearemos dos clases de trabajo que se usarán con este elemento de menú de dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="8b967-128">Next, we will create two work classes that will be used with this mobile device menu item.</span></span> <span data-ttu-id="8b967-129">Cuando se use el elemento de menú, se consultarán estas clases de trabajo y se mostrará al usuario el trabajo con la prioridad más alta.</span><span class="sxs-lookup"><span data-stu-id="8b967-129">When the menu item is used, these work classes will be queried, and the work that has the highest priority will be shown to the user.</span></span>  
9. <span data-ttu-id="8b967-130">Haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="8b967-130">Click **New**.</span></span>
10. <span data-ttu-id="8b967-131">En el campo **Id. de la clase de trabajo**, seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="8b967-131">In the **Work class ID** field, select a value.</span></span>
11. <span data-ttu-id="8b967-132">Haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="8b967-132">Click **New**.</span></span>
12. <span data-ttu-id="8b967-133">En el campo **Id. de la clase de trabajo**, seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="8b967-133">In the **Work class ID** field, select a value.</span></span>
13. <span data-ttu-id="8b967-134">En el **Panel Acciones**, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="8b967-134">In the **Action Pane**, click **Save**.</span></span>
14. <span data-ttu-id="8b967-135">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="8b967-135">Close the page.</span></span>
15. <span data-ttu-id="8b967-136">En el **Panel de exploración** vaya a **Módulos > Administración de módulos > Configuración > Dispositivo móvil > Menú del dispositivo móvil**.</span><span class="sxs-lookup"><span data-stu-id="8b967-136">In the **Navigation pane**, go to **Modules > Warehouse management > Setup > Mobile device > Mobile device menu**.</span></span>
16. <span data-ttu-id="8b967-137">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="8b967-137">In the list, find and select the desired record.</span></span>
17. <span data-ttu-id="8b967-138">En el árbol, seleccione "el elemento de menú que acaba de crear".</span><span class="sxs-lookup"><span data-stu-id="8b967-138">In the tree, select 'the menu item that you just created'.</span></span>
18. <span data-ttu-id="8b967-139">Haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="8b967-139">Click **Edit**.</span></span>
19. <span data-ttu-id="8b967-140">Haga clic en la flecha para agregar el elemento de menú al menú.</span><span class="sxs-lookup"><span data-stu-id="8b967-140">Click the arrow to add the menu item to the menu.</span></span>
20. <span data-ttu-id="8b967-141">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="8b967-141">Click **Save**.</span></span>

## <a name="create-a-counting-threshold"></a><span data-ttu-id="8b967-142">Crear un umbral de recuento</span><span class="sxs-lookup"><span data-stu-id="8b967-142">Create a counting threshold</span></span>
1. <span data-ttu-id="8b967-143">En el **Panel de exploración**, vaya **Módulos > Administración de almacenes > Configuración > Recuento cíclico > Umbrales de recuento cíclico**.</span><span class="sxs-lookup"><span data-stu-id="8b967-143">In the **Navigation pane**, go to **Modules > Warehouse management > Setup > Cycle counting > Cycle count thresholds**.</span></span>
2. <span data-ttu-id="8b967-144">Haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="8b967-144">Click **New**.</span></span>
3. <span data-ttu-id="8b967-145">En el campo **Id. de umbral de recuento cíclico**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="8b967-145">In the **Cycle counting threshold ID** field, type a value.</span></span>
4. <span data-ttu-id="8b967-146">Defina la opción **Procesar recuento cíclico inmediatamente** en Sí.</span><span class="sxs-lookup"><span data-stu-id="8b967-146">Set the **Process cycle counting immediately** option to Yes.</span></span>
5. <span data-ttu-id="8b967-147">En el campo **Descripción**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="8b967-147">In the **Description** field, type a value.</span></span>
6. <span data-ttu-id="8b967-148">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="8b967-148">Click **Save**.</span></span>
7. <span data-ttu-id="8b967-149">Haga clic en **Seleccionar ubicaciones**.</span><span class="sxs-lookup"><span data-stu-id="8b967-149">Click **Select locations**.</span></span>
8. <span data-ttu-id="8b967-150">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="8b967-150">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="8b967-151">En el campo **Criterios**, seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="8b967-151">In the **Criteria** field, select a value.</span></span>
10. <span data-ttu-id="8b967-152">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8b967-152">Click **OK**.</span></span>
11. <span data-ttu-id="8b967-153">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="8b967-153">Close the page.</span></span>

## <a name="create-a-cycle-count-plan"></a><span data-ttu-id="8b967-154">Crear un plan de recuento cíclico</span><span class="sxs-lookup"><span data-stu-id="8b967-154">Create a cycle count plan</span></span>
1. <span data-ttu-id="8b967-155">En el **Panel de exploración**, vaya **Módulos > Administración de almacenes > Configuración > Recuento cíclico > Planes de recuento cíclico**.</span><span class="sxs-lookup"><span data-stu-id="8b967-155">In the **Navigation pane**, go to **Modules > Warehouse management > Setup > Cycle counting > Cycle count plans**.</span></span>
2. <span data-ttu-id="8b967-156">Haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="8b967-156">Click **New**.</span></span>
3. <span data-ttu-id="8b967-157">En el campo **Id. de plan de recuento cíclico**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="8b967-157">In the **Cycle counting plan ID** field, type a value.</span></span>
4. <span data-ttu-id="8b967-158">En el campo **Descripción**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="8b967-158">In the **Description** field, type a value.</span></span>
5. <span data-ttu-id="8b967-159">En el campo **Número máximo de recuentos cíclicos**, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="8b967-159">In the **Maximum number of cycle counts** field, enter a number.</span></span>
6. <span data-ttu-id="8b967-160">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="8b967-160">Click **Save**.</span></span>
7. <span data-ttu-id="8b967-161">Haga clic en **Seleccionar ubicaciones**.</span><span class="sxs-lookup"><span data-stu-id="8b967-161">Click **Select locations**.</span></span>
8. <span data-ttu-id="8b967-162">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="8b967-162">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="8b967-163">En el campo **Criterios**, seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="8b967-163">In the **Criteria** field, select a value.</span></span>
10. <span data-ttu-id="8b967-164">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8b967-164">Click **OK**.</span></span>
11. <span data-ttu-id="8b967-165">En el campo **Días entre recuentos cíclicos**, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="8b967-165">In the **Days between cycle counting** field, enter a number.</span></span> <span data-ttu-id="8b967-166">Por ejemplo, si el valor en el campo **Días entre recuentos cíclicos** es 5, el trabajo de recuento cíclico se creará cada cinco días.</span><span class="sxs-lookup"><span data-stu-id="8b967-166">For example, if the **Days between cycle counting** field is set to 5, cycle counting work will be created every five days.</span></span> <span data-ttu-id="8b967-167">Sin embargo, si el trabajo de recuento cíclico se procesa el día tres, el siguiente trabajo de recuento cíclico se creará cinco días después del último recuento cíclico procesado, el día 8.</span><span class="sxs-lookup"><span data-stu-id="8b967-167">However, if cycle counting work is processed on day three, the next cycle counting work will be created five days after the last cycle counting was processed, on day 8.</span></span>  
12. <span data-ttu-id="8b967-168">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="8b967-168">Click **Save**.</span></span>
13. <span data-ttu-id="8b967-169">Haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="8b967-169">Click **New**.</span></span>
14. <span data-ttu-id="8b967-170">En el campo **Número de secuencia**, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="8b967-170">In the **Sequence number** field, enter a number.</span></span> <span data-ttu-id="8b967-171">La ordenación es del número más pequeño al número más grande.</span><span class="sxs-lookup"><span data-stu-id="8b967-171">The sort is from the smallest number to the largest number.</span></span> <span data-ttu-id="8b967-172">El valor debe ser mayor que 0 (cero).</span><span class="sxs-lookup"><span data-stu-id="8b967-172">The value must be more than 0 (zero).</span></span>  
15. <span data-ttu-id="8b967-173">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="8b967-173">In the list, mark the selected row.</span></span>
16. <span data-ttu-id="8b967-174">En el campo **Descripción**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="8b967-174">In the **Description** field, type a value.</span></span>
17. <span data-ttu-id="8b967-175">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="8b967-175">Click **Save**.</span></span>
18. <span data-ttu-id="8b967-176">Haga clic en **Definir consulta** de producto.</span><span class="sxs-lookup"><span data-stu-id="8b967-176">Click **Define product** query.</span></span>
19. <span data-ttu-id="8b967-177">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="8b967-177">In the list, mark the selected row.</span></span>
20. <span data-ttu-id="8b967-178">En el campo **Criterios**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="8b967-178">In the **Criteria** field, enter or select a value.</span></span>
21. <span data-ttu-id="8b967-179">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8b967-179">Click **OK**.</span></span>
22. <span data-ttu-id="8b967-180">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="8b967-180">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]