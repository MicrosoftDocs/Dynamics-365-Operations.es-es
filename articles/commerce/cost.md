---
title: Configuración de costes para la gestión de pedidos distribuida (DOM)
description: En este tema se describe la configuración de costes para la funcionalidad de gestión de pedidos distribuida (DOM) de Dynamics 365 Commerce.
author: josaw1
ms.date: 12/05/2018
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-12-15
ms.dyn365.ops.version: ''
ms.openlocfilehash: f3ed387bf7925785c33e2f0c07e9aba898334567
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5795988"
---
# <a name="cost-configuration-for-distributed-order-management-dom"></a><span data-ttu-id="7956d-103">Configuración de costes para la gestión de pedidos distribuida (DOM)</span><span class="sxs-lookup"><span data-stu-id="7956d-103">Cost configuration for distributed order management (DOM)</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7956d-104">Las organizaciones tienen en cuenta varios componentes de costes para determinar la ubicación óptima desde la que satisfacer un pedido.</span><span class="sxs-lookup"><span data-stu-id="7956d-104">Organizations consider multiple cost components to determine the optimal location to fulfill an order from.</span></span> <span data-ttu-id="7956d-105">Algunos de estos componentes de costes son el coste de envío, el coste de manipulación y el coste de empaquetado.</span><span class="sxs-lookup"><span data-stu-id="7956d-105">Some of these cost components are shipping cost, handling cost, and packaging cost.</span></span> <span data-ttu-id="7956d-106">Se calcula una combinación de estos costes para determinar la ubicación de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="7956d-106">A combination of these costs is calculated to determine the fulfillment location.</span></span>

<span data-ttu-id="7956d-107">Cuando la primera iteración de gestión de pedidos distribuida (DOM) de Dynamics 365 Commerce optimizó la asignación de pedidos a las ubicaciones de cumplimiento, solo se tuvo en cuenta en la distancia.</span><span class="sxs-lookup"><span data-stu-id="7956d-107">When the first iteration of distributed order management (DOM) in Dynamics 365 Commerce optimized the assignment of orders to fulfillment locations, it factored in distance only.</span></span> <span data-ttu-id="7956d-108">Aunque la distancia pueda estar correlacionada con el coste, no es lo mismo que el coste.</span><span class="sxs-lookup"><span data-stu-id="7956d-108">Although distance can be correlated with cost, it isn't the same as cost.</span></span> <span data-ttu-id="7956d-109">Por ejemplo, un método de envío durante la noche cuesta más que el envío de tres días o el envío de siete días en la misma distancia.</span><span class="sxs-lookup"><span data-stu-id="7956d-109">For example, an overnight shipping method costs more than three-day shipping or seven-day shipping over the same distance.</span></span>

<span data-ttu-id="7956d-110">La característica de configuración de costes permite a los minoristas definir y configurar componentes de costes adicionales que se calcularán y tendrán en cuenta para determinar la ubicación óptima desde la que satisfacer las líneas de pedido.</span><span class="sxs-lookup"><span data-stu-id="7956d-110">The cost configuration feature lets retailers define and configure additional cost components that will be calculated and factored in to determine the optimal location to fulfill order lines from.</span></span>

<span data-ttu-id="7956d-111">Cuando los componentes de costes se configuran, el solucionador de DOM usa solo esas definiciones de costes para determinar la ubicación óptima para el cumplimiento del pedido.</span><span class="sxs-lookup"><span data-stu-id="7956d-111">When cost components are configured, the DOM solver uses only those cost definitions to determine the optimal location for order fulfillment.</span></span> <span data-ttu-id="7956d-112">No tiene en cuenta el componente de la distancia como coste.</span><span class="sxs-lookup"><span data-stu-id="7956d-112">It doesn't consider the distance component as a cost.</span></span> <span data-ttu-id="7956d-113">Sin embargo, si no hay componentes de costes configurados, el solucionador de DOM usa el componente de la distancia como coste para determinar la ubicación óptima para el cumplimiento del pedido.</span><span class="sxs-lookup"><span data-stu-id="7956d-113">However, if no cost components are configured, the DOM solver does use the distance component as a cost to determine the optimal location for order fulfillment.</span></span>

## <a name="set-up-cost-components"></a><span data-ttu-id="7956d-114">Configurar componentes de costes</span><span class="sxs-lookup"><span data-stu-id="7956d-114">Set up cost components</span></span>

<span data-ttu-id="7956d-115">Se pueden definir dos tipos de componentes de costes principales en el sistema: **Envío** y **Otros**.</span><span class="sxs-lookup"><span data-stu-id="7956d-115">Two major cost component types can be defined in the system: **Shipping** and **Other**.</span></span>

<span data-ttu-id="7956d-116">Ambos tipos de componentes de costes admiten varias bases de cálculo, como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="7956d-116">Both cost component types support multiple calculation bases, as shown in the following table.</span></span>

<table>
<thead>
<tr>
<th><span data-ttu-id="7956d-117">Tipo de componente de costes</span><span class="sxs-lookup"><span data-stu-id="7956d-117">Cost component type</span></span></th>
<th><span data-ttu-id="7956d-118">Base de cálculo</span><span class="sxs-lookup"><span data-stu-id="7956d-118">Calculation basis</span></span></th>
</tr>
</thead>
<tbody>
<tr>
<td><span data-ttu-id="7956d-119">Envío</span><span class="sxs-lookup"><span data-stu-id="7956d-119">Shipping</span></span></td>
<td>
<ul>
<li><span data-ttu-id="7956d-120">Sencillo</span><span class="sxs-lookup"><span data-stu-id="7956d-120">Simple</span></span></li>
<li><span data-ttu-id="7956d-121">Por niveles</span><span class="sxs-lookup"><span data-stu-id="7956d-121">Tiered</span></span></li>
</ul>
</td>
</tr>
<tr>
<td><span data-ttu-id="7956d-122">Otros</span><span class="sxs-lookup"><span data-stu-id="7956d-122">Other</span></span></td>
<td>
<ul>
<li><span data-ttu-id="7956d-123">Pedido de ventas</span><span class="sxs-lookup"><span data-stu-id="7956d-123">Sales order</span></span></li>
<li><span data-ttu-id="7956d-124">Línea de ventas</span><span class="sxs-lookup"><span data-stu-id="7956d-124">Sales line</span></span></li>
<li><span data-ttu-id="7956d-125">Ubicación</span><span class="sxs-lookup"><span data-stu-id="7956d-125">Location</span></span></li>
</ul>
</td>
</tr>
</tbody>
</table>

### <a name="shipping-cost-component-type"></a><span data-ttu-id="7956d-126">Tipo de componente de costes de envío</span><span class="sxs-lookup"><span data-stu-id="7956d-126">Shipping cost component type</span></span>

<span data-ttu-id="7956d-127">En esta sección se explica cómo configurar cada combinación del tipo de componente de costes **Envío** y una base del cálculo para los gastos de envío.</span><span class="sxs-lookup"><span data-stu-id="7956d-127">This section explains how to set up each combination of the **Shipping** cost component type and a calculation basis for shipping costs.</span></span> <span data-ttu-id="7956d-128">También explica cómo el solucionador de DOM usa cada combinación.</span><span class="sxs-lookup"><span data-stu-id="7956d-128">It also explains how the DOM solver uses each combination.</span></span>

#### <a name="cost-component-type--shipping-and-calculation-basis--simple"></a><span data-ttu-id="7956d-129">Tipo de componente de costes = Base de envío y cálculo = Sencillo</span><span class="sxs-lookup"><span data-stu-id="7956d-129">Cost component type = Shipping and Calculation basis = Simple</span></span>

<span data-ttu-id="7956d-130">Si se usa una combinación del tipo de componente de costes **Envío** y la base de cálculo **Sencillo**, el coste de envío para un modo de entrega se basa en una distancia o coste fijo.</span><span class="sxs-lookup"><span data-stu-id="7956d-130">If a combination of the **Shipping** cost component type and the **Simple** calculation basis is used, the shipping cost for a mode of delivery is based on either a flat cost or distance.</span></span>

<span data-ttu-id="7956d-131">Debe configurar los siguientes campos para esta combinación:</span><span class="sxs-lookup"><span data-stu-id="7956d-131">You must set up the following fields for this combination:</span></span>

- <span data-ttu-id="7956d-132">**Factor de coste**: especifique un identificador único para el factor de coste.</span><span class="sxs-lookup"><span data-stu-id="7956d-132">**Cost factor** – Enter a unique identifier for the cost factor.</span></span>
- <span data-ttu-id="7956d-133">**Descripción**: escriba el nombre y la descripción del factor de coste.</span><span class="sxs-lookup"><span data-stu-id="7956d-133">**Description** – Enter the name and description of the cost factor.</span></span>
- <span data-ttu-id="7956d-134">**Fecha inicial** y **Fecha de finalización**: puede usar estos campos para limitar el factor de coste para un intervalo de fechas específico.</span><span class="sxs-lookup"><span data-stu-id="7956d-134">**Start date** and **End date** – You can use these fields to limit the cost factor for a specific date range.</span></span> <span data-ttu-id="7956d-135">Si deja estos campos en blanco, el factor de coste es válido por un período indefinido.</span><span class="sxs-lookup"><span data-stu-id="7956d-135">If you leave these fields blank, the cost factor is valid for an indefinite period.</span></span>
- <span data-ttu-id="7956d-136">**Activo**: indica si el factor de coste está activo.</span><span class="sxs-lookup"><span data-stu-id="7956d-136">**Active** – Indicate whether the cost factor is active.</span></span> <span data-ttu-id="7956d-137">DOM solo tiene en cuenta los factores de coste activos que están asociados al perfil de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="7956d-137">The DOM considers only active cost factors that are associated with the fulfillment profile.</span></span>
- <span data-ttu-id="7956d-138">**Empresa**: especifica la entidad jurídica para la que está configurado el factor de coste.</span><span class="sxs-lookup"><span data-stu-id="7956d-138">**Company** – Specify the legal entity that the cost factor is configured for.</span></span> <span data-ttu-id="7956d-139">Todas las líneas de los criterios de cálculo deben ser para la misma entidad jurídica.</span><span class="sxs-lookup"><span data-stu-id="7956d-139">All lines of the calculation criteria must be for the same legal entity.</span></span>
- <span data-ttu-id="7956d-140">**Modos de entrega**: especifique los modos de entrega para los que está configurado el coste.</span><span class="sxs-lookup"><span data-stu-id="7956d-140">**Modes of delivery** – Specify the modes of delivery that the cost is configured for.</span></span>
- <span data-ttu-id="7956d-141">**Tipo de cálculo**: especifique cómo se debe calcular el coste para un modo de entrega concreto.</span><span class="sxs-lookup"><span data-stu-id="7956d-141">**Calculation type** – Specify how the cost should be calculated for a specific mode of delivery.</span></span> <span data-ttu-id="7956d-142">Se admiten dos tipos de cálculo:</span><span class="sxs-lookup"><span data-stu-id="7956d-142">Two calculation types are supported:</span></span>

    - <span data-ttu-id="7956d-143">**Fijo**: se usa un coste fijo para el modo de entrega.</span><span class="sxs-lookup"><span data-stu-id="7956d-143">**Fixed** – A flat cost is used for the mode of delivery.</span></span> <span data-ttu-id="7956d-144">Si selecciona este tipo de cálculo, el campo **Coste** define el coste fijo.</span><span class="sxs-lookup"><span data-stu-id="7956d-144">If you select this calculation type, the **Cost** field defines the flat cost.</span></span>
    - <span data-ttu-id="7956d-145">**Por unidad de distancia**: el coste para el modo de entrega se calcula como el valor de coste que se especifica en el campo **Coste** multiplicado por la distancia entre la dirección de entrega y las ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="7956d-145">**Per-distance unit** – The cost for the mode of delivery is calculated as the cost value that is specified in the **Cost** field times the distance between the delivery address and the locations.</span></span>

- <span data-ttu-id="7956d-146">**Coste**: especifique el valor del coste que se usa junto con el campo **Tipo de cálculo** para calcular el coste de un modo de entrega.</span><span class="sxs-lookup"><span data-stu-id="7956d-146">**Cost** – Specify the cost value that is used in conjunction with the **Calculation type** field to compute the cost for a mode of delivery.</span></span>

#### <a name="cost-component-type--shipping-and-calculation-basis--tiered"></a><span data-ttu-id="7956d-147">Tipo de componente de costes = Base de envío y cálculo = Por niveles</span><span class="sxs-lookup"><span data-stu-id="7956d-147">Cost component type = Shipping and Calculation basis = Tiered</span></span>

<span data-ttu-id="7956d-148">Si se usa una combinación del tipo de componente de costes **Envío** y la base de cálculo **Por niveles** , el coste de envío para un modo de entrega se basa en una distancia o coste fijo.</span><span class="sxs-lookup"><span data-stu-id="7956d-148">If a combination of the **Shipping** cost component type and the **Tiered** calculation basis is used, the shipping cost for a mode of delivery is based on either a flat cost or distance.</span></span> <span data-ttu-id="7956d-149">Sin embargo, en esta combinación, la distancia se basa en un intervalo por niveles de distancias.</span><span class="sxs-lookup"><span data-stu-id="7956d-149">However, in this combination, the distance is based on a tiered range of distances.</span></span>

<span data-ttu-id="7956d-150">Debe configurar los siguientes campos para esta combinación:</span><span class="sxs-lookup"><span data-stu-id="7956d-150">You must set up the following fields for this combination:</span></span>

- <span data-ttu-id="7956d-151">**Factor de coste**: especifique un identificador único para el factor de coste.</span><span class="sxs-lookup"><span data-stu-id="7956d-151">**Cost factor** – Enter a unique identifier for the cost factor.</span></span>
- <span data-ttu-id="7956d-152">**Descripción**: escriba el nombre y la descripción del factor de coste.</span><span class="sxs-lookup"><span data-stu-id="7956d-152">**Description** – Enter the name and description of the cost factor.</span></span>
- <span data-ttu-id="7956d-153">**Coste predeterminado**: especifique el coste que se debe usar para un modo de entrega si la distancia entre la dirección de entrega y la ubicación no se encuentra en ninguna de las distancias por niveles para el modo de entrega.</span><span class="sxs-lookup"><span data-stu-id="7956d-153">**Default cost** – Specify the cost that should be used for a mode of delivery if the distance between the delivery address and the location doesn't fall into any of the tiered distances for the mode of delivery.</span></span>
- <span data-ttu-id="7956d-154">**Fecha inicial** y **Fecha de finalización**: puede usar estos campos para limitar el factor de coste para un intervalo de fechas específico.</span><span class="sxs-lookup"><span data-stu-id="7956d-154">**Start date** and **End date** – You can use these fields to limit the cost factor for a specific date range.</span></span> <span data-ttu-id="7956d-155">Si deja estos campos en blanco, el factor de coste es válido por un período indefinido.</span><span class="sxs-lookup"><span data-stu-id="7956d-155">If you leave these fields blank, the cost factor is valid for an indefinite period.</span></span>
- <span data-ttu-id="7956d-156">**Activo**: indica si el factor de coste está activo.</span><span class="sxs-lookup"><span data-stu-id="7956d-156">**Active** – Indicate whether the cost factor is active.</span></span> <span data-ttu-id="7956d-157">DOM solo tiene en cuenta los factores de coste activos que están asociados al perfil de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="7956d-157">The DOM considers only active cost factors that are associated with the fulfillment profile.</span></span>
- <span data-ttu-id="7956d-158">**Empresa**: especifica la entidad jurídica para la que está configurado el factor de coste.</span><span class="sxs-lookup"><span data-stu-id="7956d-158">**Company** – Specify the legal entity that the cost factor is configured for.</span></span> <span data-ttu-id="7956d-159">Todas las líneas de los criterios de cálculo deben ser para la misma entidad jurídica.</span><span class="sxs-lookup"><span data-stu-id="7956d-159">All lines of the calculation criteria must be for the same legal entity.</span></span>
- <span data-ttu-id="7956d-160">**Modos de entrega**: especifique los modos de entrega para los que está configurado el coste.</span><span class="sxs-lookup"><span data-stu-id="7956d-160">**Modes of delivery** – Specify the modes of delivery that the cost is configured for.</span></span>
- <span data-ttu-id="7956d-161">**Tipo de distancia**: especifique si la definición de distancia por niveles es una distancia aérea o una distancia por carretera.</span><span class="sxs-lookup"><span data-stu-id="7956d-161">**Distance type** – Specify whether the tiered distance definition is an aerial distance or a road distance.</span></span>
- <span data-ttu-id="7956d-162">**Unidades de distancia**: especifique la unidad en la que se mide la distancia por niveles.</span><span class="sxs-lookup"><span data-stu-id="7956d-162">**Distance units** – Specify the unit that the tiered distance is measured in.</span></span>
- <span data-ttu-id="7956d-163">**Distancia desde**: especifique el intervalo de inicio de la distancia por niveles.</span><span class="sxs-lookup"><span data-stu-id="7956d-163">**Distance from** – Specify the start range for the tiered distance.</span></span>
- <span data-ttu-id="7956d-164">**Distancia a**: especifique el intervalo de finalización de la distancia por niveles.</span><span class="sxs-lookup"><span data-stu-id="7956d-164">**Distance to** – Specify the end range for the tiered distance.</span></span>
- <span data-ttu-id="7956d-165">**Tipo de cálculo**: especifique cómo se debe calcular el coste para un modo de entrega concreto y una distancia por niveles.</span><span class="sxs-lookup"><span data-stu-id="7956d-165">**Calculation type** – Specify how the cost should be calculated for a specific mode of delivery and tiered distance.</span></span> <span data-ttu-id="7956d-166">Se admiten dos tipos de cálculo:</span><span class="sxs-lookup"><span data-stu-id="7956d-166">Two calculation types are supported:</span></span>

    - <span data-ttu-id="7956d-167">**Fijo**: se usa un coste fijo para el modo de entrega.</span><span class="sxs-lookup"><span data-stu-id="7956d-167">**Fixed** – A flat cost is used for the mode of delivery.</span></span> <span data-ttu-id="7956d-168">Si selecciona este tipo de cálculo, el campo **Coste** define el coste fijo.</span><span class="sxs-lookup"><span data-stu-id="7956d-168">If you select this calculation type, the **Cost** field defines the flat cost.</span></span>
    - <span data-ttu-id="7956d-169">**Por unidad de distancia**: el coste para el modo de entrega y la distancia por niveles se calcula como el valor de coste que se especifica en el campo **Coste** y la distancia entre la dirección de entrega y las ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="7956d-169">**Per distance unit** – The cost for the mode of delivery and tiered distance is calculated as the cost value that is specified in the **Cost** field times the distance between the delivery address and the locations.</span></span>

- <span data-ttu-id="7956d-170">**Coste**: especifique el valor del coste que se usa junto con el campo **Tipo de cálculo** para calcular el coste de un modo de entrega.</span><span class="sxs-lookup"><span data-stu-id="7956d-170">**Cost** – Specify the cost value that is used in conjunction with the **Calculation type** field to compute the cost for a mode of delivery.</span></span>

> [!NOTE]
> - <span data-ttu-id="7956d-171">Al definir distancias por niveles, el sistema valida que no haya distancias que falten o que se superpongan.</span><span class="sxs-lookup"><span data-stu-id="7956d-171">When you define tiered distances, the system validates that there are no missing or overlapping distances.</span></span>
> - <span data-ttu-id="7956d-172">El tipo de distancia que se usa para un modo de entrega debe ser igual en todas las distancias por niveles.</span><span class="sxs-lookup"><span data-stu-id="7956d-172">The distance type that is used for a mode of delivery must be the same across all the tiered distances.</span></span>

### <a name="other-cost-component-type"></a><span data-ttu-id="7956d-173">Otro tipo de componente de costes</span><span class="sxs-lookup"><span data-stu-id="7956d-173">Other cost component type</span></span>

<span data-ttu-id="7956d-174">Esta sección explica cómo configurar cada combinación de tipo de componente de costes **Otros** y otro tipo de coste para gastos que no sean de envío.</span><span class="sxs-lookup"><span data-stu-id="7956d-174">This section explains how to set up each combination of the **Other** cost component type and an other cost type for non-shipping costs.</span></span> <span data-ttu-id="7956d-175">También explica cómo el solucionador de DOM usa cada combinación.</span><span class="sxs-lookup"><span data-stu-id="7956d-175">It also explains how the DOM solver uses each combination.</span></span>

#### <a name="cost-component-type--other-and-other-cost-type--sales-order"></a><span data-ttu-id="7956d-176">Tipo de componente de costes = Otros y Otro tipo de coste = Pedido de ventas</span><span class="sxs-lookup"><span data-stu-id="7956d-176">Cost component type = Other and Other cost type = Sales order</span></span>

<span data-ttu-id="7956d-177">Se usa una combinación de tipo de componente de costes **Otro** y el otro tipo de coste **Pedido de ventas** para definir gastos que no sean de envío en el nivel de pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="7956d-177">A combination of the **Other** cost component type and the **Sales order** other cost type is used to define non-shipping costs at the sales order level.</span></span>

<span data-ttu-id="7956d-178">Debe configurar los siguientes campos para esta combinación:</span><span class="sxs-lookup"><span data-stu-id="7956d-178">You must set up the following fields for this combination:</span></span>

- <span data-ttu-id="7956d-179">**Factor de coste**: especifique un identificador único para el factor de coste.</span><span class="sxs-lookup"><span data-stu-id="7956d-179">**Cost factor** – Enter a unique identifier for the cost factor.</span></span>
- <span data-ttu-id="7956d-180">**Descripción**: escriba el nombre y la descripción del factor de coste.</span><span class="sxs-lookup"><span data-stu-id="7956d-180">**Description** – Enter the name and description of the cost factor.</span></span>
- <span data-ttu-id="7956d-181">**Fecha inicial** y **Fecha de finalización**: puede usar estos campos para limitar el factor de coste para un intervalo de fechas específico.</span><span class="sxs-lookup"><span data-stu-id="7956d-181">**Start date** and **End date** – You can use these fields to limit the cost factor for a specific date range.</span></span> <span data-ttu-id="7956d-182">Si deja estos campos en blanco, el factor de coste es válido por un período indefinido.</span><span class="sxs-lookup"><span data-stu-id="7956d-182">If you leave these fields blank, the cost factor is valid for an indefinite period.</span></span>
- <span data-ttu-id="7956d-183">**Activo**: indica si el factor de coste está activo.</span><span class="sxs-lookup"><span data-stu-id="7956d-183">**Active** – Indicate whether the cost factor is active.</span></span> <span data-ttu-id="7956d-184">DOM solo tiene en cuenta los factores de coste activos que están asociados al perfil de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="7956d-184">The DOM considers only active cost factors that are associated with the fulfillment profile.</span></span>
- <span data-ttu-id="7956d-185">**Coste**: especifique el valor de coste de un gasto que no sea de envío en el nivel de pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="7956d-185">**Cost** – Specify the cost value for a non-shipping cost at the sales order level.</span></span>

#### <a name="cost-component-type--other-and-other-cost-type--sales-line"></a><span data-ttu-id="7956d-186">Tipo de componente de costes = Otros y Otro tipo de coste = Línea de ventas</span><span class="sxs-lookup"><span data-stu-id="7956d-186">Cost component type = Other and Other cost type = Sales line</span></span>

<span data-ttu-id="7956d-187">Se usa una combinación de tipo de componente de costes **Otro** y el otro tipo de coste **Línea de ventas** para definir gastos que no sean de envío en el nivel de línea de pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="7956d-187">A combination of the **Other** cost component type and the **Sales line** other cost type is used to define non-shipping costs at the sales order line level.</span></span>

<span data-ttu-id="7956d-188">Debe configurar los siguientes campos para esta combinación:</span><span class="sxs-lookup"><span data-stu-id="7956d-188">You must set up the following fields for this combination:</span></span>

- <span data-ttu-id="7956d-189">**Factor de coste**: especifique un identificador único para el factor de coste.</span><span class="sxs-lookup"><span data-stu-id="7956d-189">**Cost factor** – Enter a unique identifier for the cost factor.</span></span>
- <span data-ttu-id="7956d-190">**Descripción**: escriba el nombre y la descripción del factor de coste.</span><span class="sxs-lookup"><span data-stu-id="7956d-190">**Description** – Enter the name and description of the cost factor.</span></span>
- <span data-ttu-id="7956d-191">**Fecha inicial** y **Fecha de finalización**: puede usar estos campos para limitar el factor de coste para un intervalo de fechas específico.</span><span class="sxs-lookup"><span data-stu-id="7956d-191">**Start date** and **End date** – You can use these fields to limit the cost factor for a specific date range.</span></span> <span data-ttu-id="7956d-192">Si deja estos campos en blanco, el factor de coste es válido por un período indefinido.</span><span class="sxs-lookup"><span data-stu-id="7956d-192">If you leave these fields blank, the cost factor is valid for an indefinite period.</span></span>
- <span data-ttu-id="7956d-193">**Activo**: indica si el factor de coste está activo.</span><span class="sxs-lookup"><span data-stu-id="7956d-193">**Active** – Indicate whether the cost factor is active.</span></span> <span data-ttu-id="7956d-194">DOM solo tiene en cuenta los factores de coste activos que están asociados al perfil de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="7956d-194">The DOM considers only active cost factors that are associated with the fulfillment profile.</span></span>
- <span data-ttu-id="7956d-195">**Coste**: especifique el valor de coste de un gasto que no sea de envío en el nivel de línea de pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="7956d-195">**Cost** – Specify the cost value for a non-shipping cost at the sales order line level.</span></span>

#### <a name="cost-component-type--other-and-other-cost-type--location"></a><span data-ttu-id="7956d-196">Tipo de componente de costes = Otros y Otro tipo de coste = Ubicación</span><span class="sxs-lookup"><span data-stu-id="7956d-196">Cost component type = Other and Other cost type = Location</span></span>

<span data-ttu-id="7956d-197">Se usa una combinación del tipo de componente de costes **Otros** y el otro tipo de coste **Ubicación** para definir los gastos que no son de envío para un grupo de ubicaciones o una ubicación individual.</span><span class="sxs-lookup"><span data-stu-id="7956d-197">A combination of the **Other** cost component type and the **Location** other cost type is used to define non-shipping costs for a group of locations or an individual location.</span></span>

<span data-ttu-id="7956d-198">Debe configurar los siguientes campos para esta combinación:</span><span class="sxs-lookup"><span data-stu-id="7956d-198">You must set up the following fields for this combination:</span></span>

- <span data-ttu-id="7956d-199">**Factor de coste**: especifique un identificador único para el factor de coste.</span><span class="sxs-lookup"><span data-stu-id="7956d-199">**Cost factor** – Enter a unique identifier for the cost factor.</span></span>
- <span data-ttu-id="7956d-200">**Descripción**: escriba el nombre y la descripción del factor de coste.</span><span class="sxs-lookup"><span data-stu-id="7956d-200">**Description** – Enter the name and description of the cost factor.</span></span>
- <span data-ttu-id="7956d-201">**Fecha inicial** y **Fecha de finalización**: puede usar estos campos para limitar el factor de coste para un intervalo de fechas específico.</span><span class="sxs-lookup"><span data-stu-id="7956d-201">**Start date** and **End date** – You can use these fields to limit the cost factor for a specific date range.</span></span> <span data-ttu-id="7956d-202">Si deja estos campos en blanco, el factor de coste es válido por un período indefinido.</span><span class="sxs-lookup"><span data-stu-id="7956d-202">If you leave these fields blank, the cost factor is valid for an indefinite period.</span></span>
- <span data-ttu-id="7956d-203">**Activo**: indica si el factor de coste está activo.</span><span class="sxs-lookup"><span data-stu-id="7956d-203">**Active** – Indicate whether the cost factor is active.</span></span> <span data-ttu-id="7956d-204">DOM solo tiene en cuenta los factores de coste activos que están asociados al perfil de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="7956d-204">The DOM considers only active cost factors that are associated with the fulfillment profile.</span></span>
- <span data-ttu-id="7956d-205">**Grupo de cumplimiento**: especifique el grupo de ubicaciones para las que se define el gasto que no es de envío.</span><span class="sxs-lookup"><span data-stu-id="7956d-205">**Fulfillment group** – Specify the group of locations that the non-shipping cost is defined for.</span></span>
- <span data-ttu-id="7956d-206">**Ubicación de cumplimiento** especifique la ubicación para la que se define el gasto que no es de envío.</span><span class="sxs-lookup"><span data-stu-id="7956d-206">**Fulfillment location** – Specify the location that the non-shipping cost is defined for.</span></span>

    > [!NOTE]
    > <span data-ttu-id="7956d-207">No puede especificar un grupo de cumplimiento y una ubicación de cumplimiento en la misma línea para los criterios de cálculo basados en ubicación.</span><span class="sxs-lookup"><span data-stu-id="7956d-207">You can't specify a fulfillment group and a fulfillment location on the same line for location-based calculation criteria.</span></span>

- <span data-ttu-id="7956d-208">**Coste**: especifique el valor de coste de un gasto que no sea de envío en el nivel de grupo de cumplimiento o en el nivel de ubicación de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="7956d-208">**Cost** – Specify the cost value for a non-shipping cost at the fulfillment group level or fulfillment location level.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7956d-209">Para que DOM tenga en cuenta estos costes cuando se ejecuta, debe agregar el factor de coste al perfil de cumplimiento pertinente.</span><span class="sxs-lookup"><span data-stu-id="7956d-209">For DOM to consider these costs when it's run, you must add the cost factor to the relevant fulfillment profile.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]