---
title: Previsiones de mantenimiento
description: En este tema se explican las previsiones de mantenimiento en Administración de activos.
author: josaw1
manager: tfehr
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetWorkOrderForecastToJournals, EntAssetWorkOrderForecast
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: c60834a1f818b142a0f2f022d66fe1f42edeb536
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2021
ms.locfileid: "5020878"
---
# <a name="maintenance-forecasts"></a><span data-ttu-id="bac31-103">Previsiones de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="bac31-103">Maintenance forecasts</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="bac31-104">Cuando cree una orden de trabajo, cree tareas de la orden de trabajo con activos y tipos de trabajo de mantenimiento relacionados.</span><span class="sxs-lookup"><span data-stu-id="bac31-104">When you create a work order, you create work order jobs that have related assets and maintenance job types.</span></span> <span data-ttu-id="bac31-105">Cuando seleccione un tipo de trabajo de mantenimiento que contenga previsiones de mantenimiento, las previsiones se copian automáticamente en la orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="bac31-105">When you select a maintenance job type that contains maintenance forecasts, the forecasts are automatically copied to the work order.</span></span>

<span data-ttu-id="bac31-106">Es posible que pueda agregar líneas de previsión a una orden de trabajo o eliminarlas de una orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="bac31-106">You might be able to add forecast lines to a work order or delete them from a work order.</span></span> <span data-ttu-id="bac31-107">La configuración del estado de ciclo de vida de una orden de trabajo, el tipo de proyecto relacionado y las reglas de etapa relacionadas con el tipo de proyecto determinan si puede agregar o editar líneas de previsión.</span><span class="sxs-lookup"><span data-stu-id="bac31-107">The setup of the work order lifecycle state, the related project type, and the stage rules that are related to the project type determine whether you can add or edit forecast lines.</span></span> <span data-ttu-id="bac31-108">Para obtener más información sobre estados y etapas de proyecto del ciclo de vida de la orden de trabajo, consulte [Previsiones, órdenes de trabajo y proyectos](../integration-to-project-management-and-accounting/forecasts-work-orders-and-projects.md).</span><span class="sxs-lookup"><span data-stu-id="bac31-108">For more information about work order lifecycle states and related project stages, see [Forecasts, work orders, and projects](../integration-to-project-management-and-accounting/forecasts-work-orders-and-projects.md).</span></span>

1. <span data-ttu-id="bac31-109">Seleccione **Administración de activos** > **Común** > **Órdenes de trabajo** > **Todas las órdenes de trabajo** u **Órdenes de trabajo activas**.</span><span class="sxs-lookup"><span data-stu-id="bac31-109">Select **Asset management** > **Common** > **Work orders** > **All work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="bac31-110">Seleccione la orden de trabajo de la lista y, a continuación, en el panel de acciones, en la pestaña **Orden de trabajo**, en el grupo **Proyecto**, seleccione **Previsión**.</span><span class="sxs-lookup"><span data-stu-id="bac31-110">Select the work order in the list, and then, on the Action Pane > **Work order** tab > the **Project** group, select **Forecast**.</span></span> <span data-ttu-id="bac31-111">En la página **Previsión de mantenimiento de orden de trabajo** se muestran las líneas de previsión del tipo de trabajo de mantenimiento seleccionado en la tarea de la orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="bac31-111">The **Work order maintenance forecast** page shows forecast lines from the maintenance job type that is selected on the work order job.</span></span>


## <a name="add-an-hours-forecast-to-a-work-order"></a><span data-ttu-id="bac31-112">Agregar una previsión de horas a una orden de trabajo</span><span class="sxs-lookup"><span data-stu-id="bac31-112">Add an hours forecast to a work order</span></span>

1. <span data-ttu-id="bac31-113">En la página **Pronóstico de mantenimiento de órdenes de trabajo** , seleccione el trabajo de una orden de trabajo al que se va a agregar una previsión.</span><span class="sxs-lookup"><span data-stu-id="bac31-113">On the **Work order maintenance forecast** page, select the work order job to add a forecast to.</span></span>

2. <span data-ttu-id="bac31-114">En la ficha desplegable **Horas**, seleccione **Agregar** para crear una línea nueva.</span><span class="sxs-lookup"><span data-stu-id="bac31-114">On the **Hours** FastTab, select **Add** to create a new line.</span></span>

3. <span data-ttu-id="bac31-115">Seleccione una categoría en el campo **Categoría**.</span><span class="sxs-lookup"><span data-stu-id="bac31-115">In the **Category** field, select a category.</span></span>

4. <span data-ttu-id="bac31-116">Inserte el número de horas previstas en el campo **Horas**.</span><span class="sxs-lookup"><span data-stu-id="bac31-116">In the **Hours** field, enter the number of forecasted hours.</span></span>

5. <span data-ttu-id="bac31-117">En el campo **Propiedad de la línea**, seleccione el tipo de cargo que se deberá usar en la línea.</span><span class="sxs-lookup"><span data-stu-id="bac31-117">In the **Line property** field, select the type of charge that should be used on the line.</span></span>


## <a name="add-an-items-forecast-to-a-work-order"></a><span data-ttu-id="bac31-118">Agregar una previsión de artículos a una orden de trabajo</span><span class="sxs-lookup"><span data-stu-id="bac31-118">Add an items forecast to a work order</span></span>

<span data-ttu-id="bac31-119">Hay tres formas de agregar artículos a una previsión de mantenimiento de pedidos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="bac31-119">There are three ways to add items to a work order maintenance forecast.</span></span> <span data-ttu-id="bac31-120">Puede crear líneas para artículos (recambios) que no se incluyen en la lista de recambios o lista de materiales (BOM) del activo, puede seleccionar recambios de la lista de recambios aprobadas o puede seleccionar artículos de la lista de materiales (BOM) del activo.</span><span class="sxs-lookup"><span data-stu-id="bac31-120">You can create lines for items (spare parts) that aren't included on the spare parts list or the asset bill of materials (BOM), you can select spare parts from the approved spare parts list, or you can select items from the asset BOM.</span></span>

- <span data-ttu-id="bac31-121">En la página **Pronóstico de mantenimiento de órdenes de trabajo** , seleccione el trabajo de una orden de trabajo al que se va a agregar una previsión.</span><span class="sxs-lookup"><span data-stu-id="bac31-121">On the **Work order maintenance forecast** page, select the work order job to add a forecast to.</span></span>

- <span data-ttu-id="bac31-122">En el ficha desplegable **Artículos**, agregue los artículos a la previsión de mantenimiento mediante el método adecuado.</span><span class="sxs-lookup"><span data-stu-id="bac31-122">On the **Items** FastTab, add items to the maintenance forecast by using the appropriate method.</span></span>

<span data-ttu-id="bac31-123">Para crear una nueva línea para un recambio que no está en la lista de recambios o en la lista de materiales de activos, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="bac31-123">To create a line for a spare part that isn't on the spare parts list or the asset BOM, follow these steps:</span></span>

1. <span data-ttu-id="bac31-124">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="bac31-124">Select **Add**.</span></span>
2. <span data-ttu-id="bac31-125">Seleccione el artículo en el campo **Número de artículo**.</span><span class="sxs-lookup"><span data-stu-id="bac31-125">In the **Item number** field, select the item.</span></span>
3. <span data-ttu-id="bac31-126">Introduzca la cantidad en el campo **Cantidad de ventas**.</span><span class="sxs-lookup"><span data-stu-id="bac31-126">In the **Sales quantity** field, enter the quantity.</span></span>
4. <span data-ttu-id="bac31-127">En el campo **Unidad**, seleccione la unidad de medida para la cantidad.</span><span class="sxs-lookup"><span data-stu-id="bac31-127">In the **Unit** field, select the unit of measure for the quantity.</span></span>
5. <span data-ttu-id="bac31-128">En los campos **Precio de coste** y **Divisa**, introduzca los valores adecuados.</span><span class="sxs-lookup"><span data-stu-id="bac31-128">In the **Cost price** and **Currency** fields, enter appropriate values.</span></span>
6. <span data-ttu-id="bac31-129">En el campo **Propiedad de línea** , seleccione una propiedad de línea.</span><span class="sxs-lookup"><span data-stu-id="bac31-129">In the **Line property** field, select a line property.</span></span>
7. <span data-ttu-id="bac31-130">Si desea cambiar la lista de dimensiones que se muestran en las líneas de artículos, haga clic en **Inventario** > **Mostrar dimensiones**, seleccione las dimensiones y defina la opción **Guardar configuración** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="bac31-130">To change the list of dimensions that is shown on the item lines, select **Inventory** > **Display dimensions**, select the dimensions, and then set the **Save setup** option to **Yes**.</span></span>

<span data-ttu-id="bac31-131">Para agregar un repuesto de una lista de recambios aprobada, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="bac31-131">To add a spare part from an approved spare parts list, follow these steps:</span></span>

1. <span data-ttu-id="bac31-132">Seleccione **Agregar recambios**.</span><span class="sxs-lookup"><span data-stu-id="bac31-132">Select **Add spare parts**.</span></span>
2. <span data-ttu-id="bac31-133">Seleccione el recambio, y edite la información relacionada como sea necesario.</span><span class="sxs-lookup"><span data-stu-id="bac31-133">Select the spare part, and edit the related information as you require.</span></span>
3. <span data-ttu-id="bac31-134">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="bac31-134">Select **OK**.</span></span>

<span data-ttu-id="bac31-135">Para agregar un artículo de lista de materiales de activos, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="bac31-135">To add an item from the asset BOM, follow these steps:</span></span>

1. <span data-ttu-id="bac31-136">Seleccione **Agregar artículos de L. MAT**.</span><span class="sxs-lookup"><span data-stu-id="bac31-136">Select **Add BOM items**.</span></span>
2. <span data-ttu-id="bac31-137">Seleccione el artículo, y edite la información relacionada como sea necesario.</span><span class="sxs-lookup"><span data-stu-id="bac31-137">Select the item, and edit the related information as you require.</span></span>
3. <span data-ttu-id="bac31-138">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="bac31-138">Select **OK**.</span></span>

<span data-ttu-id="bac31-139">Para obtener una visión general de dónde se usa el artículo de la línea seleccionada en Administración de activos, en relación con los activos, los valores predeterminados de los tipos de trabajo de mantenimiento, las piezas de repuesto y las órdenes de trabajo en la administración de activos, seleccione **Dónde se usó el artículo**.</span><span class="sxs-lookup"><span data-stu-id="bac31-139">To get an overview that shows where the item on the selected line is used in relation to assets, maintenance job type defaults, spare parts, and work orders in Asset Management, select **Item where used**.</span></span> <span data-ttu-id="bac31-140">Para obtener más información sobre esta información general, consulte [Dónde se usó el artículo](../controlling-and-reporting/item-where-used.md).</span><span class="sxs-lookup"><span data-stu-id="bac31-140">For more information about this overview, see [Item where used](../controlling-and-reporting/item-where-used.md).</span></span>


## <a name="add-an-expense-forecast-to-a-work-order"></a><span data-ttu-id="bac31-141">Agregar una previsión de gastos a una orden de trabajo</span><span class="sxs-lookup"><span data-stu-id="bac31-141">Add an expense forecast to a work order</span></span>

1. <span data-ttu-id="bac31-142">En la página **Pronóstico de mantenimiento de órdenes de trabajo** , seleccione el trabajo de una orden de trabajo al que se va a agregar una previsión.</span><span class="sxs-lookup"><span data-stu-id="bac31-142">On the **Work order maintenance forecast** page, select the work order job to add a forecast to.</span></span>

2. <span data-ttu-id="bac31-143">En la ficha desplegable **Gasto**, seleccione **Agregar** para crear una línea.</span><span class="sxs-lookup"><span data-stu-id="bac31-143">On the **Expense** FastTab, select **Add** to create a line.</span></span>

3. <span data-ttu-id="bac31-144">Seleccione una categoría en el campo **Categoría**.</span><span class="sxs-lookup"><span data-stu-id="bac31-144">In the **Category** field, select a category.</span></span>

4. <span data-ttu-id="bac31-145">En el campo **Cantidad**, escriba la cantidad.</span><span class="sxs-lookup"><span data-stu-id="bac31-145">In the **Quantity** field, enter the quantity.</span></span>

5. <span data-ttu-id="bac31-146">En los campos **Precio de coste**, **Divisa de ventas** y **Precio de venta**, introduzca los valores adecuados.</span><span class="sxs-lookup"><span data-stu-id="bac31-146">In the **Cost price**, **Sales currency**, and **Sales price** fields, enter appropriate values.</span></span>

6. <span data-ttu-id="bac31-147">En el campo **Propiedad de la línea**, seleccione el tipo de cargo que se deberá usar en la línea.</span><span class="sxs-lookup"><span data-stu-id="bac31-147">In the **Line property** field, select the type of charge that should be used on the line.</span></span>

>[!NOTE]
><span data-ttu-id="bac31-148">En la ficha desplegable **Totales de previsión de mantenimiento** se muestra una visión general del número de líneas creadas para la tarea de la orden de trabajo seleccionada y para la orden de trabajo, en cada ficha desplegable.</span><span class="sxs-lookup"><span data-stu-id="bac31-148">The **Maintenance forecast totals** FastTab shows an overview of the number of lines that have been created, for the selected work order job and for the work order, on each FastTab.</span></span> <span data-ttu-id="bac31-149">Además, muestra la suma de las horas de trabajo previstas para la tarea de la orden de trabajo y para la orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="bac31-149">It also shows the total forecasted work hours for the work order job and the work order.</span></span>

<span data-ttu-id="bac31-150">La ilustración muestra un ejemplo de la página **Previsión de mantenimiento de orden de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="bac31-150">The illustration below shows an example of the **Work order maintenance forecast** page.</span></span>

![Figura 1](media/06-work-orders.png)


## <a name="automatic-update-of-work-order-forecasts"></a><span data-ttu-id="bac31-152">Actualización automática de previsiones de orden de trabajo</span><span class="sxs-lookup"><span data-stu-id="bac31-152">Automatic update of work order forecasts</span></span>

<span data-ttu-id="bac31-153">En Administración de activos, puede actualizar automáticamente cualquier cambio en las previsiones de orden de trabajo en lo que respecta a costes por hora, costes de artículo y gastos, que se han actualizado en otros módulos de Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="bac31-153">If hour costs, item costs, and expenses are updated in other modules in Microsoft Dynamics 365 for Finance and Operations, work order forecasts in Asset Management can automatically be updated to reflect those changes.</span></span> <span data-ttu-id="bac31-154">Esta capacidad ayuda a garantizar que los últimos precios de coste se utilizan siempre en sus previsiones de orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="bac31-154">This capability helps guarantee that the latest cost prices are always used in your work order forecasts.</span></span> <span data-ttu-id="bac31-155">También es posible realizar actualizaciones similares para [previsiones de tipo de trabajo de mantenimiento](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md).</span><span class="sxs-lookup"><span data-stu-id="bac31-155">You can also do similar updates for [maintenance job type forecasts](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md).</span></span>

1. <span data-ttu-id="bac31-156">Seleccione **Administración de activos** > **Periódico** > **Previsión** > **Actualizar previsión de orden de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="bac31-156">Select **Asset management** > **Periodic** > **Forecast** > **Update work order forecast**.</span></span>

2. <span data-ttu-id="bac31-157">En el cuadro de diálogo **Actualizar previsión de orden de trabajo**, en la ficha desplegable **Registros que incluir** puede agregar selecciones relativas a determinadas órdenes de trabajo o tareas de orden de trabajo, si es necesario.</span><span class="sxs-lookup"><span data-stu-id="bac31-157">In the **Update work order forecast** dialog, on the **Records to include** FastTab, you can add selections regarding specific work orders or work order jobs, as you require.</span></span> <span data-ttu-id="bac31-158">Haga clic en **Filtrar** para hacer las selecciones relevantes.</span><span class="sxs-lookup"><span data-stu-id="bac31-158">Click **Filter** to make the relevant selections.</span></span>

3. <span data-ttu-id="bac31-159">En la pestaña desplegable **Ejecutar en segundo plano**, puede configurar la actualización automática como un trabajo por lotes según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="bac31-159">On the **Run in the background** FastTab, you can set up the automatic update as a batch job, as you require.</span></span>

4. <span data-ttu-id="bac31-160">Seleccione **Aceptar** para iniciar la actualización de la previsión.</span><span class="sxs-lookup"><span data-stu-id="bac31-160">Select **OK** to start the forecast update.</span></span>


<span data-ttu-id="bac31-161">La ilustración muestra un ejemplo del cuadro de diálogo **Actualizar previsión de orden de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="bac31-161">The illustration below shows an example of the **Update work order forecast** dialog.</span></span>

![Figura 2](media/07-work-orders.png)
