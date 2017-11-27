---
title: "Claves de reducción"
description: "Este artículo proporciona ejemplos que muestran cómo configurar una clave de reducción. Incluye información sobre los distintos ajustes de la clave de reducción y los resultados de cada uno. Puede usar una clave de reducción para definir cómo reducir los requisitos de previsión."
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqPlanSched
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 19251
ms.assetid: aa9e0dfb-6052-4a2e-9378-89507c02fdf2
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 506ca3aac7ad271ca7472f3b74627e94d97a74ee
ms.contentlocale: es-es
ms.lasthandoff: 11/03/2017

---

# <a name="reduction-keys"></a><span data-ttu-id="638eb-105">Claves de reducción</span><span class="sxs-lookup"><span data-stu-id="638eb-105">Reduction keys</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="638eb-106">Este artículo proporciona ejemplos que muestran cómo configurar una clave de reducción.</span><span class="sxs-lookup"><span data-stu-id="638eb-106">This articles provides examples that show how to set up a reduction key.</span></span> <span data-ttu-id="638eb-107">Incluye información sobre los distintos ajustes de la clave de reducción y los resultados de cada uno.</span><span class="sxs-lookup"><span data-stu-id="638eb-107">It includes information about the various reduction key settings and the results of each.</span></span> <span data-ttu-id="638eb-108">Puede usar una clave de reducción para definir cómo reducir los requisitos de previsión.</span><span class="sxs-lookup"><span data-stu-id="638eb-108">You can use a reduction key to define how to reduce forecast requirements.</span></span>

<a name="example-1-percent---reduction-key-forecast-reduction-principle"></a><span data-ttu-id="638eb-109">Ejemplo 1: Porcentaje: principio de reducción de previsión clave de reducción</span><span class="sxs-lookup"><span data-stu-id="638eb-109">Example 1: Percent - reduction key forecast reduction principle</span></span>
---------------------------------------------------------------

<span data-ttu-id="638eb-110">Este ejemplo muestra cómo reduce una clave de reducción los requisitos de previsión de la demanda en función de los porcentajes y los períodos definidos por la clave de reducción.</span><span class="sxs-lookup"><span data-stu-id="638eb-110">This example shows how a reduction key reduces demand forecast requirements according to the percentages and periods that are defined by the reduction key.</span></span>

1.  <span data-ttu-id="638eb-111">En la página **Claves de reducción**, configure las siguientes líneas.</span><span class="sxs-lookup"><span data-stu-id="638eb-111">On the **Reduction keys** page, set up the following lines.</span></span>
    | <span data-ttu-id="638eb-112">Cambio</span><span class="sxs-lookup"><span data-stu-id="638eb-112">Change</span></span> | <span data-ttu-id="638eb-113">Unidad</span><span class="sxs-lookup"><span data-stu-id="638eb-113">Unit</span></span>  | <span data-ttu-id="638eb-114">Porcentaje</span><span class="sxs-lookup"><span data-stu-id="638eb-114">Percent</span></span> |
    |--------|-------|---------|
    | <span data-ttu-id="638eb-115">1</span><span class="sxs-lookup"><span data-stu-id="638eb-115">1</span></span>      | <span data-ttu-id="638eb-116">Mes</span><span class="sxs-lookup"><span data-stu-id="638eb-116">Month</span></span> | <span data-ttu-id="638eb-117">100</span><span class="sxs-lookup"><span data-stu-id="638eb-117">100</span></span>     |
    | <span data-ttu-id="638eb-118">2</span><span class="sxs-lookup"><span data-stu-id="638eb-118">2</span></span>      | <span data-ttu-id="638eb-119">Mes</span><span class="sxs-lookup"><span data-stu-id="638eb-119">Month</span></span> | <span data-ttu-id="638eb-120">75</span><span class="sxs-lookup"><span data-stu-id="638eb-120">75</span></span>      |
    | <span data-ttu-id="638eb-121">3</span><span class="sxs-lookup"><span data-stu-id="638eb-121">3</span></span>      | <span data-ttu-id="638eb-122">Mes</span><span class="sxs-lookup"><span data-stu-id="638eb-122">Month</span></span> | <span data-ttu-id="638eb-123">50</span><span class="sxs-lookup"><span data-stu-id="638eb-123">50</span></span>      |
    | <span data-ttu-id="638eb-124">4</span><span class="sxs-lookup"><span data-stu-id="638eb-124">4</span></span>      | <span data-ttu-id="638eb-125">Mes</span><span class="sxs-lookup"><span data-stu-id="638eb-125">Month</span></span> | <span data-ttu-id="638eb-126">25</span><span class="sxs-lookup"><span data-stu-id="638eb-126">25</span></span>      |

2.  <span data-ttu-id="638eb-127">Vincule la clave de reducción al grupo de cobertura del artículo.</span><span class="sxs-lookup"><span data-stu-id="638eb-127">Link the reduction key to the item's coverage group.</span></span>
3.  <span data-ttu-id="638eb-128">En la página **Planes maestros**, en el campo **Principio de reducción**, seleccione **Porcentaje - clave de reducción**.</span><span class="sxs-lookup"><span data-stu-id="638eb-128">On the **Master plans** page, in the **Reduction principle** field, select **Percent - reduction key**.</span></span>
4.  <span data-ttu-id="638eb-129">Cree una previsión de la demanda de 1000 piezas por mes.</span><span class="sxs-lookup"><span data-stu-id="638eb-129">Create a demand forecast of 1,000 pieces per month.</span></span>

<span data-ttu-id="638eb-130">Si ejecuta la programación de previsión el 1 de enero, los requisitos de previsión de la demanda se consumen de acuerdo con los porcentajes configurados en la página **Claves de reducción**:</span><span class="sxs-lookup"><span data-stu-id="638eb-130">If you run forecast scheduling on January 1, the demand forecast requirements are consumed according to the percentages that you set up on the **Reduction keys** page.</span></span> <span data-ttu-id="638eb-131">las siguientes cantidades de requisitos se transfieren al plan maestro.</span><span class="sxs-lookup"><span data-stu-id="638eb-131">The following requirement quantities are transferred to the master plan.</span></span>

| <span data-ttu-id="638eb-132">Mes</span><span class="sxs-lookup"><span data-stu-id="638eb-132">Month</span></span>                | <span data-ttu-id="638eb-133">Número de piezas requeridas</span><span class="sxs-lookup"><span data-stu-id="638eb-133">Number of pieces required</span></span> |
|----------------------|---------------------------|
| <span data-ttu-id="638eb-134">Enero</span><span class="sxs-lookup"><span data-stu-id="638eb-134">January</span></span>              | <span data-ttu-id="638eb-135">0</span><span class="sxs-lookup"><span data-stu-id="638eb-135">0</span></span>                         |
| <span data-ttu-id="638eb-136">Febrero</span><span class="sxs-lookup"><span data-stu-id="638eb-136">February</span></span>             | <span data-ttu-id="638eb-137">250</span><span class="sxs-lookup"><span data-stu-id="638eb-137">250</span></span>                       |
| <span data-ttu-id="638eb-138">Marzo</span><span class="sxs-lookup"><span data-stu-id="638eb-138">March</span></span>                | <span data-ttu-id="638eb-139">500</span><span class="sxs-lookup"><span data-stu-id="638eb-139">500</span></span>                       |
| <span data-ttu-id="638eb-140">Abril</span><span class="sxs-lookup"><span data-stu-id="638eb-140">April</span></span>                | <span data-ttu-id="638eb-141">750</span><span class="sxs-lookup"><span data-stu-id="638eb-141">750</span></span>                       |
| <span data-ttu-id="638eb-142">De mayo a diciembre</span><span class="sxs-lookup"><span data-stu-id="638eb-142">May through December</span></span> | <span data-ttu-id="638eb-143">1.000</span><span class="sxs-lookup"><span data-stu-id="638eb-143">1,000</span></span>                     |

## <a name="example-2-transactions--reduction-key-forecast-reduction-principle"></a><span data-ttu-id="638eb-144">Ejemplo 2: Principio de reducción de previsión clave de reducción de transacciones</span><span class="sxs-lookup"><span data-stu-id="638eb-144">Example 2: Transactions  reduction key forecast reduction principle</span></span>
<span data-ttu-id="638eb-145">Este ejemplo muestra cómo los pedidos reales, que se producen en períodos definidos por la clave de reducción, reducen los requisitos de previsión de la demanda.</span><span class="sxs-lookup"><span data-stu-id="638eb-145">This example shows how actual orders that occur during the periods that are defined by the reduction key reduce demand forecast requirements.</span></span>

-   <span data-ttu-id="638eb-146">En la página **Planes maestros**, en el campo **Principio de reducción**, seleccione **Transacciones - clave de reducción**.</span><span class="sxs-lookup"><span data-stu-id="638eb-146">On the **Master plans** page, in the **Reduction principle** field, select **Transactions - reduction key**.</span></span>

<span data-ttu-id="638eb-147">Los siguientes pedidos de ventas existen el 1 de enero.</span><span class="sxs-lookup"><span data-stu-id="638eb-147">The following sales orders exist on January 1.</span></span>

| <span data-ttu-id="638eb-148">Mes</span><span class="sxs-lookup"><span data-stu-id="638eb-148">Month</span></span>    | <span data-ttu-id="638eb-149">Número de piezas solicitadas</span><span class="sxs-lookup"><span data-stu-id="638eb-149">Number of pieces ordered</span></span> |
|----------|--------------------------|
| <span data-ttu-id="638eb-150">Enero</span><span class="sxs-lookup"><span data-stu-id="638eb-150">January</span></span>  | <span data-ttu-id="638eb-151">956</span><span class="sxs-lookup"><span data-stu-id="638eb-151">956</span></span>                      |
| <span data-ttu-id="638eb-152">Febrero</span><span class="sxs-lookup"><span data-stu-id="638eb-152">February</span></span> | <span data-ttu-id="638eb-153">1.176</span><span class="sxs-lookup"><span data-stu-id="638eb-153">1,176</span></span>                    |
| <span data-ttu-id="638eb-154">Marzo</span><span class="sxs-lookup"><span data-stu-id="638eb-154">March</span></span>    | <span data-ttu-id="638eb-155">451</span><span class="sxs-lookup"><span data-stu-id="638eb-155">451</span></span>                      |
| <span data-ttu-id="638eb-156">Abril</span><span class="sxs-lookup"><span data-stu-id="638eb-156">April</span></span>    | <span data-ttu-id="638eb-157">119</span><span class="sxs-lookup"><span data-stu-id="638eb-157">119</span></span>                      |

<span data-ttu-id="638eb-158">Si utiliza la misma previsión de la demanda de 1000 piezas por mes, se transfieren las siguientes cantidades de requisitos al plan maestro.</span><span class="sxs-lookup"><span data-stu-id="638eb-158">If you use the same demand forecast of 1,000 pieces per month, the following requirement quantities are transferred to the master plan.</span></span>

| <span data-ttu-id="638eb-159">Mes</span><span class="sxs-lookup"><span data-stu-id="638eb-159">Month</span></span>                | <span data-ttu-id="638eb-160">Número de piezas requeridas</span><span class="sxs-lookup"><span data-stu-id="638eb-160">Number of pieces required</span></span> |
|----------------------|---------------------------|
| <span data-ttu-id="638eb-161">Enero</span><span class="sxs-lookup"><span data-stu-id="638eb-161">January</span></span>              | <span data-ttu-id="638eb-162">44</span><span class="sxs-lookup"><span data-stu-id="638eb-162">44</span></span>                        |
| <span data-ttu-id="638eb-163">Febrero</span><span class="sxs-lookup"><span data-stu-id="638eb-163">February</span></span>             | <span data-ttu-id="638eb-164">0</span><span class="sxs-lookup"><span data-stu-id="638eb-164">0</span></span>                         |
| <span data-ttu-id="638eb-165">Marzo</span><span class="sxs-lookup"><span data-stu-id="638eb-165">March</span></span>                | <span data-ttu-id="638eb-166">549</span><span class="sxs-lookup"><span data-stu-id="638eb-166">549</span></span>                       |
| <span data-ttu-id="638eb-167">Abril</span><span class="sxs-lookup"><span data-stu-id="638eb-167">April</span></span>                | <span data-ttu-id="638eb-168">881</span><span class="sxs-lookup"><span data-stu-id="638eb-168">881</span></span>                       |
| <span data-ttu-id="638eb-169">De mayo a diciembre</span><span class="sxs-lookup"><span data-stu-id="638eb-169">May through December</span></span> | <span data-ttu-id="638eb-170">1.000</span><span class="sxs-lookup"><span data-stu-id="638eb-170">1,000</span></span>                     |

## <a name="example-3-transactions--dynamic-period-forecast-reduction-principle"></a><span data-ttu-id="638eb-171">Ejemplo 3: Principio de reducción de previsión del período dinámico de transacciones</span><span class="sxs-lookup"><span data-stu-id="638eb-171">Example 3: Transactions  dynamic period forecast reduction principle</span></span>
<span data-ttu-id="638eb-172">En la mayoría de los casos, se configuran los sistemas de modo que las transacciones reduzcan la previsión de la demanda dentro de períodos específicos de previsión: semanas, meses, y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="638eb-172">In most cases, systems are set up so that transactions reduce demand forecast within specific forecast periods: weeks, months, and so on.</span></span> <span data-ttu-id="638eb-173">Estos períodos se definen en la clave de reducción.</span><span class="sxs-lookup"><span data-stu-id="638eb-173">These periods are defined in the reduction key.</span></span> <span data-ttu-id="638eb-174">No obstante, el tiempo entre dos líneas de previsión de la demanda también puede *implicar* a un período.</span><span class="sxs-lookup"><span data-stu-id="638eb-174">However, the time between two demand forecast lines can also *imply* a period.</span></span>

1.  <span data-ttu-id="638eb-175">Cree una previsión de la demanda para las fechas y las cantidades siguientes.</span><span class="sxs-lookup"><span data-stu-id="638eb-175">Create a demand forecast for the following dates and quantities.</span></span>
    | <span data-ttu-id="638eb-176">Fecha</span><span class="sxs-lookup"><span data-stu-id="638eb-176">Date</span></span>       | <span data-ttu-id="638eb-177">Previsión de la demanda</span><span class="sxs-lookup"><span data-stu-id="638eb-177">Demand forecast</span></span> |
    |------------|-----------------|
    | <span data-ttu-id="638eb-178">1 de enero</span><span class="sxs-lookup"><span data-stu-id="638eb-178">January 1</span></span>  | <span data-ttu-id="638eb-179">1.000</span><span class="sxs-lookup"><span data-stu-id="638eb-179">1,000</span></span>           |
    | <span data-ttu-id="638eb-180">5 de enero</span><span class="sxs-lookup"><span data-stu-id="638eb-180">January 5</span></span>  | <span data-ttu-id="638eb-181">500</span><span class="sxs-lookup"><span data-stu-id="638eb-181">500</span></span>             |
    | <span data-ttu-id="638eb-182">12 de enero</span><span class="sxs-lookup"><span data-stu-id="638eb-182">January 12</span></span> | <span data-ttu-id="638eb-183">1.000</span><span class="sxs-lookup"><span data-stu-id="638eb-183">1,000</span></span>           |

    <span data-ttu-id="638eb-184">En esta previsión, no hay un período claro entre las fechas de previsión: entre la primera y la segunda fecha hay un lapso de cuatro días, y entre la segunda y la tercera fecha hay un lapso de siete días.</span><span class="sxs-lookup"><span data-stu-id="638eb-184">In this forecast, there isn't a clear period between the forecast dates: between the first and second dates there is a four-day span, and between the second and third dates there is a seven-day span.</span></span> <span data-ttu-id="638eb-185">Estos distintos lapsos son períodos dinámicos.</span><span class="sxs-lookup"><span data-stu-id="638eb-185">These various spans are the dynamic periods.</span></span>
2.  <span data-ttu-id="638eb-186">Cree líneas de pedidos de venta como sigue.</span><span class="sxs-lookup"><span data-stu-id="638eb-186">Create sales order lines as follows.</span></span>
    | <span data-ttu-id="638eb-187">Fecha</span><span class="sxs-lookup"><span data-stu-id="638eb-187">Date</span></span>                             | <span data-ttu-id="638eb-188">Cantidad de pedido de ventas</span><span class="sxs-lookup"><span data-stu-id="638eb-188">Sales order quantity</span></span> |
    |----------------------------------|----------------------|
    | <span data-ttu-id="638eb-189">15 de diciembre en el año anterior</span><span class="sxs-lookup"><span data-stu-id="638eb-189">December 15 in the previous year</span></span> | <span data-ttu-id="638eb-190">500</span><span class="sxs-lookup"><span data-stu-id="638eb-190">500</span></span>                  |
    | <span data-ttu-id="638eb-191">3 de enero</span><span class="sxs-lookup"><span data-stu-id="638eb-191">January 3</span></span>                        | <span data-ttu-id="638eb-192">100</span><span class="sxs-lookup"><span data-stu-id="638eb-192">100</span></span>                  |
    | <span data-ttu-id="638eb-193">10 de enero</span><span class="sxs-lookup"><span data-stu-id="638eb-193">January 10</span></span>                       | <span data-ttu-id="638eb-194">200</span><span class="sxs-lookup"><span data-stu-id="638eb-194">200</span></span>                  |

<span data-ttu-id="638eb-195">La previsión se reducirá como sigue:</span><span class="sxs-lookup"><span data-stu-id="638eb-195">The forecast will be reduced as follows:</span></span>

-   <span data-ttu-id="638eb-196">El primer pedido de ventas no se encuentra dentro de ningún período, por lo que no se reducirá ninguna previsión.</span><span class="sxs-lookup"><span data-stu-id="638eb-196">The first sales order isn't within any period, so it won't reduce any forecast.</span></span>
-   <span data-ttu-id="638eb-197">El segundo pedido de ventas es para entre el 1 de enero y el 5 de enero, por lo que se reducirá la previsión para el 1 de enero por 100.</span><span class="sxs-lookup"><span data-stu-id="638eb-197">The second sales order is between January 1 and January 5, so it will reduce the forecast for January 1 by 100.</span></span>
-   <span data-ttu-id="638eb-198">El tercer pedido de ventas es para entre el 5 de enero y el 12 de enero, por lo que se reducirá la previsión para el 5 de enero por 200.</span><span class="sxs-lookup"><span data-stu-id="638eb-198">The third sales order is between January 5 and January 12, so it will reduce the forecast for January 5 by 200.</span></span>

<span data-ttu-id="638eb-199">Se creará el pedido planificado siguiente para satisfacer la previsión.</span><span class="sxs-lookup"><span data-stu-id="638eb-199">The following planned order will be created to fulfill the forecast.</span></span>

| <span data-ttu-id="638eb-200">Fecha de previsión de la demanda</span><span class="sxs-lookup"><span data-stu-id="638eb-200">Demand forecast date</span></span> | <span data-ttu-id="638eb-201">Cantidad reducida</span><span class="sxs-lookup"><span data-stu-id="638eb-201">Reduced quantity</span></span> |
|----------------------|------------------|
| <span data-ttu-id="638eb-202">1 de enero</span><span class="sxs-lookup"><span data-stu-id="638eb-202">January 1</span></span>            | <span data-ttu-id="638eb-203">900</span><span class="sxs-lookup"><span data-stu-id="638eb-203">900</span></span>              |
| <span data-ttu-id="638eb-204">5 de enero</span><span class="sxs-lookup"><span data-stu-id="638eb-204">January 5</span></span>            | <span data-ttu-id="638eb-205">300</span><span class="sxs-lookup"><span data-stu-id="638eb-205">300</span></span>              |
| <span data-ttu-id="638eb-206">12 de enero</span><span class="sxs-lookup"><span data-stu-id="638eb-206">January 12</span></span>           | <span data-ttu-id="638eb-207">1.000</span><span class="sxs-lookup"><span data-stu-id="638eb-207">1,000</span></span>            |

<span data-ttu-id="638eb-208">Este es un resumen de la reducción **Transacciones - período dinámico**:</span><span class="sxs-lookup"><span data-stu-id="638eb-208">Here is a summary of **Transactions - dynamic period** reduction:</span></span>

-   <span data-ttu-id="638eb-209">Los requisitos de previsión se reducirán por las transacciones de pedidos reales que se producen durante el período dinámico.</span><span class="sxs-lookup"><span data-stu-id="638eb-209">Forecast requirements are reduced by the actual order transactions that occur during the dynamic period.</span></span> <span data-ttu-id="638eb-210">El período dinámico cubre las fechas de previsión actuales y finaliza con el inicio de la próxima previsión.</span><span class="sxs-lookup"><span data-stu-id="638eb-210">The dynamic period covers the current forecast dates and ends at the start of the next forecast.</span></span>
-   <span data-ttu-id="638eb-211">Este método no usa ni requiere una clave de reducción.</span><span class="sxs-lookup"><span data-stu-id="638eb-211">This method doesn't use or require a reduction key.</span></span>
-   <span data-ttu-id="638eb-212">Cuando se utiliza esta opción, el comportamiento es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="638eb-212">When this option is used, the following behavior occurs:</span></span>
    -   <span data-ttu-id="638eb-213">Si la previsión se reduce por completo, los requisitos de previsión para la previsión actual se convierten en 0 (cero).</span><span class="sxs-lookup"><span data-stu-id="638eb-213">If the forecast is reduced completely, the forecast requirements for the current forecast become 0 (zero).</span></span>
    -   <span data-ttu-id="638eb-214">Si no hay previsión futura, se reducen los requisitos de previsión de la última previsión que se introdujo.</span><span class="sxs-lookup"><span data-stu-id="638eb-214">If there is no future forecast, forecast requirements from the last forecast that was entered are reduced.</span></span>
    -   <span data-ttu-id="638eb-215">Se incluyen límites de tiempo en el cálculo de la reducción de previsión.</span><span class="sxs-lookup"><span data-stu-id="638eb-215">Time fences are included in the forecast reduction calculation.</span></span>
    -   <span data-ttu-id="638eb-216">Se incluyen días positivos en el cálculo de la reducción de previsión.</span><span class="sxs-lookup"><span data-stu-id="638eb-216">Positive days are included in the forecast reduction calculation.</span></span>
    -   <span data-ttu-id="638eb-217">Si las transacciones de pedidos reales sobrepasan a los requisitos previstos, las transacciones restantes no se reenvían al próximo período de previsión.</span><span class="sxs-lookup"><span data-stu-id="638eb-217">If actual order transactions exceed the forecasted requirements, the remaining transactions aren't forwarded to the next forecast period.</span></span>


<a name="see-also"></a><span data-ttu-id="638eb-218">Consulte también</span><span class="sxs-lookup"><span data-stu-id="638eb-218">See also</span></span>
--------

[<span data-ttu-id="638eb-219">Planes maestros</span><span class="sxs-lookup"><span data-stu-id="638eb-219">Master plans</span></span>](master-plans.md)




