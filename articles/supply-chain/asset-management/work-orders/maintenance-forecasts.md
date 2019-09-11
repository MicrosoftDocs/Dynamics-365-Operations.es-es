---
title: Previsiones de mantenimiento
description: En este tema se explican las previsiones de mantenimiento en Administración de activos.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 1a416bbb79be3f25998d3c0da8d231d0df808685
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875885"
---
# <a name="maintenance-forecasts"></a><span data-ttu-id="8408d-103">Previsiones de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="8408d-103">Maintenance forecasts</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


<span data-ttu-id="8408d-104">Cuando cree una orden de trabajo, cree tareas de la orden de trabajo con activos y tipos de trabajo de mantenimiento relacionados.</span><span class="sxs-lookup"><span data-stu-id="8408d-104">When you create a work order, you create work order jobs with related assets and maintenance job types.</span></span> <span data-ttu-id="8408d-105">Cuando seleccione un tipo de trabajo de mantenimiento que contenga previsiones de mantenimiento, las previsiones se copian automáticamente en la orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="8408d-105">When you select a maintenance job type containing maintenance forecasts, the forecasts are automatically copied to the work order.</span></span>

<span data-ttu-id="8408d-106">Es posible que pueda agregar o eliminar líneas de previsión en una orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="8408d-106">You may be able to add or delete forecast lines on a work order.</span></span> <span data-ttu-id="8408d-107">La configuración del estado de ciclo de vida de una orden de trabajo, el tipo de proyecto relacionado y las reglas de etapa relacionadas con el tipo de proyecto determinan si puede agregar o editar líneas de previsión.</span><span class="sxs-lookup"><span data-stu-id="8408d-107">The setup of a work order lifecycle state, the related project type, and the stage rules related to the project type determines if you are able to add or edit forecast lines.</span></span> 

1. <span data-ttu-id="8408d-108">Haga clic en **Administración de activos** > **Común** > **Órdenes de trabajo** > **Todas las órdenes de trabajo** u **Órdenes de trabajo activas**.</span><span class="sxs-lookup"><span data-stu-id="8408d-108">Click **Asset management** > **Common** > **Work orders** > **All work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="8408d-109">Seleccione la orden de trabajo en la lista y haga clic en **Previsión**.</span><span class="sxs-lookup"><span data-stu-id="8408d-109">Select the work order in the list, and click **Forecast**.</span></span> <span data-ttu-id="8408d-110">En **Previsión de mantenimiento de orden de trabajo** se muestran las líneas de previsión del tipo de trabajo de mantenimiento seleccionado en la tarea de la orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="8408d-110">In **Work order maintenance forecast**, forecast lines from the maintenance job type selected on the work order job are displayed.</span></span>


## <a name="add-hours-forecast-to-a-work-order"></a><span data-ttu-id="8408d-111">Agregar previsión de horas a una orden de trabajo</span><span class="sxs-lookup"><span data-stu-id="8408d-111">Add hours forecast to a work order</span></span>

1. <span data-ttu-id="8408d-112">Seleccione la tarea de la orden de trabajo a la que desea agregar una previsión.</span><span class="sxs-lookup"><span data-stu-id="8408d-112">Select the work order job to which you want to add a forecast.</span></span>

2. <span data-ttu-id="8408d-113">En la ficha desplegable **Horas**, haga clic en **Agregar** para crear una línea nueva.</span><span class="sxs-lookup"><span data-stu-id="8408d-113">On the **Hours** FastTab, click **Add** to create a new line.</span></span>

3. <span data-ttu-id="8408d-114">Seleccione una categoría en el campo **Categoría**.</span><span class="sxs-lookup"><span data-stu-id="8408d-114">Select a category in the **Category** field.</span></span>

4. <span data-ttu-id="8408d-115">Inserte el número de horas previstas en el campo **Horas**.</span><span class="sxs-lookup"><span data-stu-id="8408d-115">Insert number of forecasted hours in the **Hours** field.</span></span>

5. <span data-ttu-id="8408d-116">En el campo **Propiedad de la línea**, seleccione el tipo de cargo que se usará en la línea.</span><span class="sxs-lookup"><span data-stu-id="8408d-116">In the **Line property** field, select the charge type to be used on the line.</span></span>


## <a name="add-items-forecast-to-a-work-order"></a><span data-ttu-id="8408d-117">Agregar previsión de artículos a una orden de trabajo</span><span class="sxs-lookup"><span data-stu-id="8408d-117">Add items forecast to a work order</span></span>

<span data-ttu-id="8408d-118">Hay tres formas de agregar artículos a una previsión de mantenimiento de orden de trabajo: puede crear líneas para artículos (recambios) que no se incluyen en la lista de recambios o L. MAT de activos, puede seleccionar recambios de la lista de recambios aprobadas, y puede seleccionar artículos de la L. MAT de activos.</span><span class="sxs-lookup"><span data-stu-id="8408d-118">There are three ways to add items to a work order maintenance forecast: You can create lines for items (spare parts) that are not included in the spare parts list or asset BOM, you can select spare parts from the approved spare parts list, and you can select items from the asset BOM.</span></span>

1. <span data-ttu-id="8408d-119">Seleccione la tarea de la orden de trabajo a la que desea agregar una previsión.</span><span class="sxs-lookup"><span data-stu-id="8408d-119">Select the work order job to which you want to add a forecast.</span></span>

2. <span data-ttu-id="8408d-120">Seleccione la ficha desplegable **Artículos**.</span><span class="sxs-lookup"><span data-stu-id="8408d-120">Select the **Items** FastTab.</span></span>

3. <span data-ttu-id="8408d-121">Haga clic en **Agregar** para crear una nueva línea para un recambio que no está en la lista de recambios o en la lista de L. MAT de activos.</span><span class="sxs-lookup"><span data-stu-id="8408d-121">Click **Add** to create a new line for a spare part that is not on the spare parts list or the asset BOM list.</span></span>

4. <span data-ttu-id="8408d-122">Seleccione el elemento el campo **Número de artículo**.</span><span class="sxs-lookup"><span data-stu-id="8408d-122">Select the item in the **Item number** field.</span></span>

5. <span data-ttu-id="8408d-123">Inserte la cantidad en el campo **Cantidad de ventas** y seleccione una unidad de cantidad en el campo **Unidad**.</span><span class="sxs-lookup"><span data-stu-id="8408d-123">Insert quantity in the **Sales quantity** field, and select a quantity unit in the **Unit** field.</span></span>

6. <span data-ttu-id="8408d-124">Inserte el precio de coste y la divisa en los campos pertinentes y seleccione **Propiedad de línea**.</span><span class="sxs-lookup"><span data-stu-id="8408d-124">Insert cost price and currency in the relevant fields, and select a **Line property**.</span></span>

7. <span data-ttu-id="8408d-125">Si desea cambiar la lista de dimensiones que se muestran en las líneas de artículos, haga clic en **Inventario** > **Mostrar dimensiones**, seleccione "Sí" en el botón de alternancia **Guardar configuración**.</span><span class="sxs-lookup"><span data-stu-id="8408d-125">If you want to change the list of dimensions displayed on the item lines, click **Inventory** > **Display dimensions**, select the dimensions, and select "Yes" on the **Save setup** toggle button.</span></span>

8. <span data-ttu-id="8408d-126">Si desea agregar un recambio aprobado a la previsión de mantenimiento, haga clic en **Agregar recambios**, seleccione el recambio, edite la información relacionada si es necesario y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8408d-126">If you want to add an approved spare part to the maintenance forecast, click **Add spare parts**, select the spare part, edit related information if required, and click **OK**.</span></span>

9. <span data-ttu-id="8408d-127">Si desea agregar artículos de la L. MAT de activos a la previsión, haga clic en **Agregar artículos de L. MAT**, seleccione el artículo, edite la información relacionada si es necesario y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8408d-127">If you want to add asset BOM items to the forecast, click **Add BOM items**, select the item, edit related information if required, and click **OK**.</span></span>

10. <span data-ttu-id="8408d-128">Haga clic en **Dónde se usa el artículo** si desea obtener una visión general de dónde se usa el artículo de la línea seleccionada en Administración de activos, en relación con los activos, los valores predeterminados de tipo de trabajo de mantenimiento, lo recambios y las órdenes de trabajo.</span><span class="sxs-lookup"><span data-stu-id="8408d-128">Click **Item where used** if you want to get an overview of where the item on the selected line is used in Asset Management in relation to assets, maintenance job type defaults, spare parts, and work orders.</span></span> 



## <a name="add-expense-forecast-to-a-work-order"></a><span data-ttu-id="8408d-129">Agregar previsión de gastos a una orden de trabajo</span><span class="sxs-lookup"><span data-stu-id="8408d-129">Add expense forecast to a work order</span></span>

1. <span data-ttu-id="8408d-130">En este tema se explica cómo agregar una previsión de gastos a una orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="8408d-130">This topic explains how to add an expense forecast to a work order.</span></span> <span data-ttu-id="8408d-131">En el lado izquierdo del formulario, seleccione la tarea de la orden de trabajo a la que desea agregar una previsión.</span><span class="sxs-lookup"><span data-stu-id="8408d-131">In the left-hand side of the form, select the work order job to which you want to add a forecast.</span></span>

2. <span data-ttu-id="8408d-132">Seleccione la ficha desplegable **Gasto**.</span><span class="sxs-lookup"><span data-stu-id="8408d-132">Select the **Expense** FastTab.</span></span>

3. <span data-ttu-id="8408d-133">Haga clic en **Agregar** para crear una línea nueva.</span><span class="sxs-lookup"><span data-stu-id="8408d-133">Click **Add** to create a new line.</span></span>

4. <span data-ttu-id="8408d-134">Seleccione una categoría en el campo **Categoría**.</span><span class="sxs-lookup"><span data-stu-id="8408d-134">Select a category in the **Category** field.</span></span>

5. <span data-ttu-id="8408d-135">Inserte la cantidad en el campo **Cantidad**.</span><span class="sxs-lookup"><span data-stu-id="8408d-135">Insert quantity in the **Quantity** field.</span></span>

6. <span data-ttu-id="8408d-136">Inserte el precio de coste, la divisa de ventas y el precio de venta en los campos correspondientes.</span><span class="sxs-lookup"><span data-stu-id="8408d-136">Insert cost price, sales currency, and sales price in the relevant fields.</span></span>

7. <span data-ttu-id="8408d-137">En el campo **Propiedad de la línea**, seleccione el tipo de cargo que se usará en la línea.</span><span class="sxs-lookup"><span data-stu-id="8408d-137">In the **Line property** field, select the charge type to be used on the line.</span></span>

>[!NOTE]
><span data-ttu-id="8408d-138">En la ficha desplegable **Totales de previsión de mantenimiento** puede obtener una visión general del número de líneas creadas en cada pestaña, para la tarea de la orden de trabajo seleccionada y para la orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="8408d-138">On the **Maintenance forecast totals** FastTab, you can see an overview of the number of lines created on each tab, for the selected work order job and for the work order.</span></span> <span data-ttu-id="8408d-139">Además, puede ver una suma de las horas de trabajo previstas para la tarea de la orden de trabajo y para la orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="8408d-139">Also, you can see a sum of forecasted work hours for the work order job and for the work order.</span></span>

![Figura 1](media/06-work-orders.png)


## <a name="automatic-update-of-work-order-forecasts"></a><span data-ttu-id="8408d-141">Actualización automática de previsiones de orden de trabajo</span><span class="sxs-lookup"><span data-stu-id="8408d-141">Automatic update of work order forecasts</span></span>

<span data-ttu-id="8408d-142">En Administración de activos, puede actualizar automáticamente cualquier cambio en las previsiones de orden de trabajo en lo que respecta a costes por hora, costes de artículo y gastos, que se han actualizado en otros módulos de Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="8408d-142">In Asset Management, you can automatically update any changes in work order forecasts regarding hour costs, item costs, and expenses, which have been updated in other modules in Dynamics 365 for Finance and Operations.</span></span> <span data-ttu-id="8408d-143">Esto se hace para garantizar que los últimos precios de coste se utilizan siempre en sus previsiones de orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="8408d-143">This is done to ensure that the latest cost prices are always used in your work order forecasts.</span></span> <span data-ttu-id="8408d-144">También es posible realizar actualizaciones similares para [previsiones de tipo de trabajo de mantenimiento](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md).</span><span class="sxs-lookup"><span data-stu-id="8408d-144">It is also possible to make similar updates for [maintenance job type forecasts](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md).</span></span>

1. <span data-ttu-id="8408d-145">Haga clic en **Administración de activos** > **Periódico** > **Previsión** > **Actualizar previsión de orden de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="8408d-145">Click **Asset management** > **Periodic** > **Forecast** > **Update work order forecast**.</span></span>

2. <span data-ttu-id="8408d-146">En el cuadro de diálogo desplegable **Actualizar previsión de orden de trabajo**, puede agregar selecciones relativas a determinadas órdenes de trabajo o tareas de orden de trabajo, si es necesario.</span><span class="sxs-lookup"><span data-stu-id="8408d-146">In the **Update work order forecast** drop-down dialog, you can add selections regarding specific work orders or work order jobs, if required.</span></span> <span data-ttu-id="8408d-147">Haga clic en **Filtrar** para hacer esas selecciones.</span><span class="sxs-lookup"><span data-stu-id="8408d-147">Click **Filter** to make those selections.</span></span>

3. <span data-ttu-id="8408d-148">Si es necesario, puede configurar la actualización automática como un trabajo por lotes en la ficha desplegable **Ejecutar en segundo plano**.</span><span class="sxs-lookup"><span data-stu-id="8408d-148">If required, you can set up the automatic update as a batch job on the **Run in the background** FastTab.</span></span>

4. <span data-ttu-id="8408d-149">Haga clic en **Aceptar** para iniciar la actualización de la previsión.</span><span class="sxs-lookup"><span data-stu-id="8408d-149">Click **OK** to start the forecast update.</span></span>


![Figura 2](media/07-work-orders.png)

