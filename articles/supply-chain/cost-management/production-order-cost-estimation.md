---
title: "Estimación del coste del pedido de producción"
description: "Este artículo proporciona información acerca de la estimación de costes de producción. La estimación de costes de producción proporciona los costes de consumo de capacidad y material previsto de producir un artículo en la cantidad del pedido de producción planificado."
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BOMCalcTrans, InventCostTrans, ProdCalcTrans, ProdTableJour, ProdTableListPage
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 80633
ms.assetid: b4625d10-c852-4fda-b718-79df458de0d4
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 3ea3998014eb9ac2fd4610b5d52bd792d4f73869
ms.contentlocale: es-es
ms.lasthandoff: 11/03/2017

---

# <a name="production-order-cost-estimation"></a><span data-ttu-id="2d81f-104">Estimación del coste del pedido de producción</span><span class="sxs-lookup"><span data-stu-id="2d81f-104">Production order cost estimation</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="2d81f-105">Este artículo proporciona información acerca de la estimación de costes de producción.</span><span class="sxs-lookup"><span data-stu-id="2d81f-105">This article provides information about production cost estimation.</span></span> <span data-ttu-id="2d81f-106">La estimación de costes de producción proporciona los costes de consumo de capacidad y material previsto de producir un artículo en la cantidad del pedido de producción planificado.</span><span class="sxs-lookup"><span data-stu-id="2d81f-106">Production cost estimation provides the projected material and capacity consumption costs of producing an item in the planned production order quantity.</span></span> 

<span data-ttu-id="2d81f-107">Después de crear un pedido de producción, debe estimar los costes de producción.</span><span class="sxs-lookup"><span data-stu-id="2d81f-107">After you create a production order, you must estimate production costs.</span></span> <span data-ttu-id="2d81f-108">El propósito es estimar el consumo de ruta y artículos para el proceso de producción, ya que estas estimaciones se usan como la base de los siguientes procesos de programación y producción.</span><span class="sxs-lookup"><span data-stu-id="2d81f-108">The purpose is to estimate item and route consumption for the production process, because these estimates are used as the basis for subsequent scheduling and production processes.</span></span>

## <a name="production-cost-estimation"></a><span data-ttu-id="2d81f-109">Estimación de costes de producción</span><span class="sxs-lookup"><span data-stu-id="2d81f-109">Production cost estimation</span></span>
<span data-ttu-id="2d81f-110">Las estimaciones de costes de producción se basan en la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="2d81f-110">Estimates of production costs are based on the following information:</span></span>

-   <span data-ttu-id="2d81f-111">La cantidad en el pedido de producción</span><span class="sxs-lookup"><span data-stu-id="2d81f-111">The quantity on the production order</span></span>
-   <span data-ttu-id="2d81f-112">Los componentes de las listas de materiales (L. MAT) de producción</span><span class="sxs-lookup"><span data-stu-id="2d81f-112">The components on the production bills of materials (BOMs)</span></span>
-   <span data-ttu-id="2d81f-113">Las operaciones de rutas de la ruta de producción</span><span class="sxs-lookup"><span data-stu-id="2d81f-113">The routing operations in the production route</span></span>
-   <span data-ttu-id="2d81f-114">Los costes indirectos que se aplican a los componentes y las operaciones</span><span class="sxs-lookup"><span data-stu-id="2d81f-114">The indirect costs that apply to the components and operations</span></span>
-   <span data-ttu-id="2d81f-115">Los datos de coste activos a partir de la fecha de cálculo</span><span class="sxs-lookup"><span data-stu-id="2d81f-115">The active cost data as of the calculation date</span></span>

<span data-ttu-id="2d81f-116">Si existe un artículo de línea fantasma en las L. MAT de producción, los cálculos reflejan los componentes y operaciones de ruta fantasmas.</span><span class="sxs-lookup"><span data-stu-id="2d81f-116">If there is a phantom line item on the production BOMs, the calculations reflect the phantom’s components and route operations.</span></span> <span data-ttu-id="2d81f-117">Puede usar la tarea de estimación para volver a calcular los costes estimados de modo que reflejen información actualizada.</span><span class="sxs-lookup"><span data-stu-id="2d81f-117">You can use the estimation task to recalculate estimated costs so that they reflect updated information.</span></span> <span data-ttu-id="2d81f-118">Por ejemplo, esta podría referirse a cambios en la cantidad del pedido de producción, los componentes de las L. MAT de producción, las operaciones de enrutamiento de la ruta de producción, los costes indirectos que se aplican a estos componentes y operaciones o los datos de coste activos a partir de la fecha de nuevo cálculo.</span><span class="sxs-lookup"><span data-stu-id="2d81f-118">For example, the updated information might be changes to the quantity on the production order, the components on the production BOMs, the routing operations in the production route, the indirect costs that apply to these components and operations, or the active cost data as of the recalculation date.</span></span> <span data-ttu-id="2d81f-119">Además, los cálculos de coste estimado sugieren un precio de venta para un artículo de producción basado en un enfoque de marcado según coste más margen.</span><span class="sxs-lookup"><span data-stu-id="2d81f-119">The calculations of estimated cost also suggest a sales price for the production item, based on a cost-plus-markup approach.</span></span> <span data-ttu-id="2d81f-120">De manera opcional, los cálculos de coste estimado se pueden aplicar a pedidos de referencia que reflejen otros pedidos de producción vinculados al pedido de producción.</span><span class="sxs-lookup"><span data-stu-id="2d81f-120">The calculations of estimated cost can optionally apply to reference orders that reflect other production orders that are linked to the production order.</span></span>

## <a name="view-the-estimated-costs"></a><span data-ttu-id="2d81f-121">Ver costes estimados</span><span class="sxs-lookup"><span data-stu-id="2d81f-121">View the estimated costs</span></span>
<span data-ttu-id="2d81f-122">Tras ejecutar la estimación, puede ver los resultados en la página **Cálculo de precios**.</span><span class="sxs-lookup"><span data-stu-id="2d81f-122">After you run estimation, you can view the results on the **Price calculation** page.</span></span> <span data-ttu-id="2d81f-123">La estimación calcula los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="2d81f-123">The estimation calculates the following values:</span></span>

-   <span data-ttu-id="2d81f-124">**Coste de producción**: el coste de producción es la línea superior de la estimación.</span><span class="sxs-lookup"><span data-stu-id="2d81f-124">**Production cost** – The production cost is the top line of the estimate.</span></span> <span data-ttu-id="2d81f-125">Muestra el coste completo de ejecutar el pedido de producción y el precio de ventas total para la producción.</span><span class="sxs-lookup"><span data-stu-id="2d81f-125">It shows the complete cost of running the production order and the total sales price for the production.</span></span> <span data-ttu-id="2d81f-126">Es la suma de todas las líneas de coste de la estimación.</span><span class="sxs-lookup"><span data-stu-id="2d81f-126">It's the sum of all the cost lines on the estimate.</span></span>
-   <span data-ttu-id="2d81f-127">**Costes de recursos o ruta**: los costes de recursos o ruta son los costes de las operaciones de producción.</span><span class="sxs-lookup"><span data-stu-id="2d81f-127">**Route or resource costs** – Route or resource costs are the costs for the production operations.</span></span> <span data-ttu-id="2d81f-128">Incluyen el coste de elementos como el tiempo de preparación, el tiempo de ejecución y los gastos generales.</span><span class="sxs-lookup"><span data-stu-id="2d81f-128">They include the cost of elements such as setup time, run time, and overhead.</span></span>
-   <span data-ttu-id="2d81f-129">**Costes de material**: los costes de materiales son los costes y precios de los componentes de L. MAT necesarios para producir el artículo.</span><span class="sxs-lookup"><span data-stu-id="2d81f-129">**Material costs** – Material costs are the costs and prices of the BOM components that are required in order to produce the item.</span></span> <span data-ttu-id="2d81f-130">Se han establecido y especificado los costes en el sistema anteriormente.</span><span class="sxs-lookup"><span data-stu-id="2d81f-130">These costs have previously been established and entered into the system.</span></span>

## <a name="other-uses-of-cost-estimation"></a><span data-ttu-id="2d81f-131">Otros usos de la estimación de coste</span><span class="sxs-lookup"><span data-stu-id="2d81f-131">Other uses of cost estimation</span></span>
<span data-ttu-id="2d81f-132">Una estimación de coste también proporciona la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="2d81f-132">A cost estimate also provides the following information:</span></span>

-   <span data-ttu-id="2d81f-133">Presupuestos de precio significativos</span><span class="sxs-lookup"><span data-stu-id="2d81f-133">Meaningful price quotations</span></span>
-   <span data-ttu-id="2d81f-134">Estimaciones de la rentabilidad del pedido</span><span class="sxs-lookup"><span data-stu-id="2d81f-134">Estimates of the profitability of the order</span></span>
-   <span data-ttu-id="2d81f-135">Estimaciones del uso de materias primas</span><span class="sxs-lookup"><span data-stu-id="2d81f-135">Estimates of raw material usage</span></span>
-   <span data-ttu-id="2d81f-136">Comparaciones de coste de producciones anteriores</span><span class="sxs-lookup"><span data-stu-id="2d81f-136">Comparisons of cost information from previous productions</span></span>
-   <span data-ttu-id="2d81f-137">Información de presupuesto y previsión</span><span class="sxs-lookup"><span data-stu-id="2d81f-137">Budget and forecasting information</span></span>
-   <span data-ttu-id="2d81f-138">Estimación del tamaño de producción necesario para mantener un coste particular</span><span class="sxs-lookup"><span data-stu-id="2d81f-138">Estimates of the production size that is required in order to maintain a particular cost</span></span>





