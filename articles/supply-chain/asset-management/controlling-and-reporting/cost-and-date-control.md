---
title: Controlar costes y fechas
description: Este tema explica el control de los costes y las fechas en la Administración de activos.
author: josaw1
manager: AnnBe
ms.date: 08/23/2019
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
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 2bcd1584f6a858f7589387fbfe96267b7c16176a
ms.sourcegitcommit: 2292b54e2da96f71b59ec9ccf17cd32d3d1d8b21
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2019
ms.locfileid: "1918404"
---
# <a name="cost-and-date-control"></a><span data-ttu-id="acfd1-103">Controlar costes y fechas</span><span class="sxs-lookup"><span data-stu-id="acfd1-103">Cost and date control</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="acfd1-104">En Administración de activos, puede calcular los costes para obtener una visión general de los costes reales comparados con los costes del presupuesto sobre los activos, ubicaciones técnicas y órdenes de trabajo.</span><span class="sxs-lookup"><span data-stu-id="acfd1-104">In Asset Management, you can calculate costs to get an overview of actual costs compared to budget costs on assets, functional locations, and work orders.</span></span> <span data-ttu-id="acfd1-105">Los costes reales se basan en las transacciones registradas.</span><span class="sxs-lookup"><span data-stu-id="acfd1-105">Actual costs are based on posted transactions.</span></span> <span data-ttu-id="acfd1-106">También puede crear un cálculo de fecha si desea comparar las fechas de inicio y fin programadas con las fechas de inicio y fin reales en las órdenes de trabajo.</span><span class="sxs-lookup"><span data-stu-id="acfd1-106">You can also make a date calculation if you want to compare scheduled start and end dates to actual start and end dates on work orders.</span></span>

## <a name="cost-control-for-assets-functional-locations-and-work-orders"></a><span data-ttu-id="acfd1-107">Control de costes para los activos, las ubicaciones técnicas y las órdenes de trabajo</span><span class="sxs-lookup"><span data-stu-id="acfd1-107">Cost control for assets, functional locations, and work orders</span></span>

<span data-ttu-id="acfd1-108">Los cálculos realizados para los activos, las ubicaciones técnicas y las órdenes de trabajo son idénticos casi.</span><span class="sxs-lookup"><span data-stu-id="acfd1-108">The calculations made for assets, functional locations, and work orders are almost identical.</span></span> <span data-ttu-id="acfd1-109">Únicamente la diferencia es que en los activos y las ubicaciones técnicas, también puede incluir subactivos y sububicaciones en el cálculo.</span><span class="sxs-lookup"><span data-stu-id="acfd1-109">Only difference is that for assets and functional locations, you can also include sub assets and sub locations in your calculation.</span></span> <span data-ttu-id="acfd1-110">La fecha es la fecha de la transacción en la que el registro se ha registrado.</span><span class="sxs-lookup"><span data-stu-id="acfd1-110">The date is the transaction date when the registration was recorded.</span></span>

1. <span data-ttu-id="acfd1-111">Haga clic en **Administración de activos** > **Consultas** > **Activos** > **Control de costes de activos** o **Control de costes de ubicación técnica** o **Administración de activos** > **Consultas** > **Órdenes de trabajo** > **Control de costes de órdenes de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="acfd1-111">Click **Asset management** > **Inquiries** > **Assets** > **Asset cost control** or **Functional location cost control**, or **Asset management** > **Inquiries** > **Work orders** > **Work order cost control**.</span></span>

2. <span data-ttu-id="acfd1-112">En el diálogo**Control de costes de activos** / **Control de costes de la ubicación técnica** / **Control de costes de órdenes de pedido**, seleccione un período para el cálculo.</span><span class="sxs-lookup"><span data-stu-id="acfd1-112">In the **Asset cost control** / **Functional location cost control** / **Work order cost control** dialog, select a period to be calculated.</span></span>

3. <span data-ttu-id="acfd1-113">Si es necesario, seleccione un conjunto de dimensiones financieras que se incluirá en el cálculo.</span><span class="sxs-lookup"><span data-stu-id="acfd1-113">If required, select a financial dimension set to be included in the calculation.</span></span>

4. <span data-ttu-id="acfd1-114">Seleccione "Sí" en el botón de alternar **Omitir cero** si no desea mostrar los resultados con un coste de cero.</span><span class="sxs-lookup"><span data-stu-id="acfd1-114">Select "Yes" on the **Skip zero** toggle button if you don't want to show results with a cost of zero.</span></span>

5. <span data-ttu-id="acfd1-115">Puede usar el campo **Nivel** para indicar el nivel de detalle que desea para las líneas de control de costes con respecto a las ubicaciones técnicas.</span><span class="sxs-lookup"><span data-stu-id="acfd1-115">You can use the **Level** field to indicate how detailed you want the cost control lines to be regarding functional locations.</span></span> <span data-ttu-id="acfd1-116">Por ejemplo, si especifica el número "1 "en el campo, y tiene una jerarquía de ubicación técnica de varios niveles, todas las líneas de control de costes de defectos del activo para una ubicación técnica se mostrarán en el nivel superior, y por tanto, las horas en una línea se pueden agregar desde las ubicaciones técnicas ubicadas en un nivel inferior.</span><span class="sxs-lookup"><span data-stu-id="acfd1-116">For example, if you insert the number "1" in the field, and you have a multi-level functional location hierarchy, all cost control lines for a functional location will be shown on the top level, and therefore the hours on a line may be added up from functional locations located at a lower level.</span></span> <span data-ttu-id="acfd1-117">Si especifica el número "0 "en el campo **Nivel** , verá un resultado detallado que muestra todas las líneas de control de costes en todo el nivel de la ubicación técnica con el que están relacionadas.</span><span class="sxs-lookup"><span data-stu-id="acfd1-117">If you insert the number "0" in the **Level** field, you will see a detailed result showing all cost control lines on all the functional location level to which they are related.</span></span>

6. <span data-ttu-id="acfd1-118">Seleccione "Sí" en el botón de alternar **Mostrar gasto comprometido abierto** si desea incluir esa columna en el cálculo.</span><span class="sxs-lookup"><span data-stu-id="acfd1-118">Select "Yes" on the **Show open committed cost** toggle button if you want to include that column in the calculation.</span></span>

7. <span data-ttu-id="acfd1-119">Seleccione "Sí" en el botón de alternar **Incluir subactivos** para mostrar costes relacionados con los activos secundaria como líneas independientes.</span><span class="sxs-lookup"><span data-stu-id="acfd1-119">Select "Yes" on the **Include sub assets** toggle button to show costs related to sub assets as separate lines.</span></span>

8. <span data-ttu-id="acfd1-120">Si desea limitar la búsqueda, puede seleccionar activos específicos, fechas de ubicaciones técnicas y órdenes de trabajo en la ficha desplegable **Registros a incluir**.</span><span class="sxs-lookup"><span data-stu-id="acfd1-120">If you want to limit the search, you can select specific assets / functional locations / work orders on the **Records to include** FastTab.</span></span>

9. <span data-ttu-id="acfd1-121">Haga clic en **Aceptar** para iniciar el cálculo.</span><span class="sxs-lookup"><span data-stu-id="acfd1-121">Click **OK** to start the calculation.</span></span>

<span data-ttu-id="acfd1-122">La ilustración siguiente muestra un ejemplo del cuadro de diálogo **Control de costes de activos**.</span><span class="sxs-lookup"><span data-stu-id="acfd1-122">The figure below shows an example of the **Asset cost control** dialog.</span></span>

![Figura 1](media/01-controlling-and-reporting.png)

10. <span data-ttu-id="acfd1-124">En los grupos del panel de acciones **Agrupar por...** en la página **Control de costes de activos**, haga clic en los botones relevantes para mostrar el nivel de detalle necesario del cálculo de costes.</span><span class="sxs-lookup"><span data-stu-id="acfd1-124">In the **Group by...** action pane groups on the **Asset cost control** page, click the relevant buttons to show the required detail level of the calculation.</span></span> <span data-ttu-id="acfd1-125">Se resaltarán los botones del panel de acciones seleccionados.</span><span class="sxs-lookup"><span data-stu-id="acfd1-125">The selected action pane buttons are highlighted.</span></span> <span data-ttu-id="acfd1-126">Haga clic en un botón para activarlo o desactivarlo.</span><span class="sxs-lookup"><span data-stu-id="acfd1-126">Click on a button to activate or deactivate it.</span></span>

<span data-ttu-id="acfd1-127">La ilustración siguiente muestra un ejemplo de resultados del cálculo en **Control de costes de activos**.</span><span class="sxs-lookup"><span data-stu-id="acfd1-127">The figure below shows an example of calculation results in **Asset cost control**.</span></span>

![Figura 2](media/02-controlling-and-reporting.png)

<span data-ttu-id="acfd1-129">Otra forma de realizar un cálculo de costes se seleccionar múltiples activos en **Todos los activos** o **Activos activos**.</span><span class="sxs-lookup"><span data-stu-id="acfd1-129">Another way of making a cost calculation is to multi-select assets in **All assets** or **Active assets**.</span></span> <span data-ttu-id="acfd1-130">A continuación, haga clic en el botón **Control de costes** en la pestaña **General**. En el diálogo **Control de costes de activos**, los activos seleccionados se insertan automáticamente en el campo **Activo** en la ficha desplegable **Registros que incluir**.</span><span class="sxs-lookup"><span data-stu-id="acfd1-130">Then, you click the **Cost control** button on the **General** tab. In the **Asset cost control** dialog, the selected assets are automatically inserted in the **Asset** field on the **Records to include** FastTab.</span></span> <span data-ttu-id="acfd1-131">Haga clic en **Aceptar** y aparece un cálculo de costes de los activos seleccionados.</span><span class="sxs-lookup"><span data-stu-id="acfd1-131">Click **OK**, and a cost calculation for the selected assets is shown.</span></span> <span data-ttu-id="acfd1-132">El mismo procedimiento se puede realizar para las ubicaciones técnicas en **Todas las ubicaciones técnicas** o **Ubicaciones técnicas activas**, y para las órdenes de trabajo en **Todas las órdenes de trabajo** o **Órdenes de trabajo activas**.</span><span class="sxs-lookup"><span data-stu-id="acfd1-132">The same procedure can be done for functional locations in **All functional locations** or **Active functional locations**, and for work orders in **All work orders** or **Active work orders**.</span></span>

>[!NOTE]
><span data-ttu-id="acfd1-133">El campo **Presupuesto original** muestra los costes del presupuesto según la previsión de órdenes de trabajo.</span><span class="sxs-lookup"><span data-stu-id="acfd1-133">The **Original budget** field shows budget costs from the work order forecast.</span></span> <span data-ttu-id="acfd1-134">El campo **Gasto comprometido** muestra el importe total de gastos que una entidad jurídica se ha comprometido a pagar.</span><span class="sxs-lookup"><span data-stu-id="acfd1-134">The **Committed cost** field shows the total amount of expenses that a legal entity has committed itself to pay.</span></span> <span data-ttu-id="acfd1-135">El campo **Gasto comprometido abierto** muestra los compromisos de pago de artículos, las horas y los servicios que pedido o recibido pero que aún no pagado.</span><span class="sxs-lookup"><span data-stu-id="acfd1-135">The **Open committed cost** field shows commitments to pay for items, hours, and services you have ordered or received but not yet paid for.</span></span> <span data-ttu-id="acfd1-136">Cuando se han enviado todos los registros de consumo, los costes relacionados se incluyen en el campo **Coste real** .</span><span class="sxs-lookup"><span data-stu-id="acfd1-136">When all consumption registrations have been posted, the related costs are included in the **Actual cost** field.</span></span>

## <a name="work-order-date-control"></a><span data-ttu-id="acfd1-137">Control de fecha de orden de trabajo</span><span class="sxs-lookup"><span data-stu-id="acfd1-137">Work order date control</span></span>

<span data-ttu-id="acfd1-138">Use esta página para obtener una visión general de las fechas de inicio y fin en comparación con las fechas de inicio y fin reales en las órdenes de trabajo.</span><span class="sxs-lookup"><span data-stu-id="acfd1-138">Use this page to get an overview of expected start and end dates compared to actual start and end dates on work orders.</span></span>

1. <span data-ttu-id="acfd1-139">Haga clic en **Administración de activos** > **Consultas** > **Órdenes de trabajo** > **Control de fechas de la orden de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="acfd1-139">Click **Asset management** > **Inquiries** > **Work orders** > **Work order date control**.</span></span>

2. <span data-ttu-id="acfd1-140">Haga clic en **Calcular**.</span><span class="sxs-lookup"><span data-stu-id="acfd1-140">Click **Calculate**.</span></span>

3. <span data-ttu-id="acfd1-141">Seleccione una ubicación técnica en el campo **Ubicación técnica**.</span><span class="sxs-lookup"><span data-stu-id="acfd1-141">Select a functional location in the **Functional location** field.</span></span>

4. <span data-ttu-id="acfd1-142">Inserte el período para el que desea crear el cálculo en los campos **Fecha inicial** y **Fecha final**.</span><span class="sxs-lookup"><span data-stu-id="acfd1-142">Insert the period for which you want to make the calculation in the **From date** and **To date** fields.</span></span> <span data-ttu-id="acfd1-143">Todas las órdenes de trabajo con el inicio esperado dentro del período se incluirán.</span><span class="sxs-lookup"><span data-stu-id="acfd1-143">All work orders with expected start within the period will be included.</span></span>

5. <span data-ttu-id="acfd1-144">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="acfd1-144">Click **OK**.</span></span>

6. <span data-ttu-id="acfd1-145">En los grupos del panel de acciones **Agrupar por...**, haga clic en los botones relevantes para mostrar el nivel de detalle necesario del cálculo.</span><span class="sxs-lookup"><span data-stu-id="acfd1-145">In the **Group by...** action pane groups, click the relevant buttons to show the required detail level of the calculation.</span></span> <span data-ttu-id="acfd1-146">Se resaltarán los botones del panel de acciones seleccionados.</span><span class="sxs-lookup"><span data-stu-id="acfd1-146">The selected action pane buttons are highlighted.</span></span> <span data-ttu-id="acfd1-147">Haga clic en un botón para activarlo o desactivarlo.</span><span class="sxs-lookup"><span data-stu-id="acfd1-147">Click on a button to activate or deactivate it.</span></span>

<span data-ttu-id="acfd1-148">La ilustración siguiente muestra un ejemplo de resultados del cálculo en **Control de fechas de órdenes de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="acfd1-148">The figure below shows an example of calculation results in **Work order date control**.</span></span>

![Figura 3](media/03-controlling-and-reporting.png)

- <span data-ttu-id="acfd1-150">El campo **Retraso de inicio promedio** muestra la diferencia en días entre la fecha de inicio programada para una orden de trabajo en comparación con la fecha de inicio real.</span><span class="sxs-lookup"><span data-stu-id="acfd1-150">The **Avg. start delay** field shows the difference in days between scheduled start date for a work order compared to actual start date.</span></span> <span data-ttu-id="acfd1-151">Si, por ejemplo, la fecha de inicio real era dos días antes de la fecha de inicio programada, "-2 "se mostrará en este campo.</span><span class="sxs-lookup"><span data-stu-id="acfd1-151">If, for example, the actual start date was two days before the scheduled start date, "-2" will be displayed in this field.</span></span>  
- <span data-ttu-id="acfd1-152">El campo **Retraso de fin promedio** muestra la diferencia en días entre la fecha de fin programada para una orden de trabajo en comparación con la fecha de fin real.</span><span class="sxs-lookup"><span data-stu-id="acfd1-152">The **Avg. end delay** field shows the difference in days between scheduled end date for a work order compared to actual end date.</span></span> <span data-ttu-id="acfd1-153">Si, por ejemplo, la fecha de fin real era tres días después de la fecha de fin programada, "3 "se mostrará en este campo.</span><span class="sxs-lookup"><span data-stu-id="acfd1-153">If, for example, the actual end date was three days after the scheduled end date, "3" will be displayed in this field.</span></span>  
- <span data-ttu-id="acfd1-154">Los campos **Repeticiones** muestran el número de veces que se producen desviaciones en relación con la fecha de inicio programada y real y la fecha de fin programada y real en la orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="acfd1-154">The **Occurrences** fields show the number of times deviations occur in relation to scheduled and actual start date, and scheduled and actual end date on the work order.</span></span>

