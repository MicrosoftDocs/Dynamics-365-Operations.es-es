---
title: Alternativas de entrega
description: "Los creadores de pedidos de ventas pueden usar la página Alternativas de entrega para detectar opciones de cumplimiento del pedido alternativas."
author: ChristianRytt
manager: AnnBe
ms.date: 04/10/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SalesLineDeliveryDetails
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 271623
ms.assetid: 527f6084-44fe-41bb-924f-4386e926358a
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: crytt
ms.dyn365.ops.intro: Version 1611
ms.search.validFrom: 2016-11-30
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: e4ddd796fb6d29c0bcc810943f668cb89698153b
ms.contentlocale: es-es
ms.lasthandoff: 08/29/2017

---

# <a name="delivery-alternatives"></a><span data-ttu-id="d3bbd-103">Alternativas de entrega</span><span class="sxs-lookup"><span data-stu-id="d3bbd-103">Delivery alternatives</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="d3bbd-104">Los creadores de pedidos de ventas pueden usar la página Alternativas de entrega para detectar opciones de cumplimiento del pedido alternativas.</span><span class="sxs-lookup"><span data-stu-id="d3bbd-104">Sales order takers can use the Delivery alternatives page to discover alternative order fulfillment options.</span></span>

<span data-ttu-id="d3bbd-105">En Microsoft Dynamics 365 for Operations versión 1611 (noviembre de 2016), los creadores de pedidos de ventas pueden usar la página **Alternativas de entrega** para detectar opciones de cumplimiento del pedido alternativas.</span><span class="sxs-lookup"><span data-stu-id="d3bbd-105">In Microsoft Dynamics 365 for Operations version 1611 (November 2016), sales order takers can use the **Delivery alternatives** page to discover alternative order fulfillment options.</span></span> <span data-ttu-id="d3bbd-106">El diseño de página rediseñado ofrece una mejor visión general de todas las opciones alternativas.</span><span class="sxs-lookup"><span data-stu-id="d3bbd-106">The redesigned page layout gives a better overview of all alternative options.</span></span> <span data-ttu-id="d3bbd-107">También permite a los creadores de pedidos buscar oportunidades de cumplimiento más allá de la empresa actual.</span><span class="sxs-lookup"><span data-stu-id="d3bbd-107">It also lets order takers look beyond the current company for fulfillment opportunities.</span></span> <span data-ttu-id="d3bbd-108">Pueden ahora ver oportunidades en empresas vinculadas y oportunidades de proveedores externos.</span><span class="sxs-lookup"><span data-stu-id="d3bbd-108">They can now view both intercompany opportunities and opportunities from external vendors.</span></span> <span data-ttu-id="d3bbd-109">Ordenando las opciones por fecha de entrega, los creadores del pedido de ventas pueden ver una lista inteligente de alternativas de la entrega.</span><span class="sxs-lookup"><span data-stu-id="d3bbd-109">By sorting the options by delivery date, sales order takers can view an intelligent list of delivery alternatives.</span></span> <span data-ttu-id="d3bbd-110">Además, los parámetros los ayudan a gestionar mejor las entregas sugeridas.</span><span class="sxs-lookup"><span data-stu-id="d3bbd-110">In addition, parameters help them better manage the suggested deliveries.</span></span> <span data-ttu-id="d3bbd-111">Dado que el tiempo de transporte puede afectar a las fechas de entrega, los creadores del pedido de ventas pueden explorar las distintas opciones de transporte que los operadores ofrecen.</span><span class="sxs-lookup"><span data-stu-id="d3bbd-111">Because transport time can affect delivery dates, sales order takers can explore the various transportation choices that carriers offer.</span></span> <span data-ttu-id="d3bbd-112">Dado que se muestra información detallada para cada sugerencia, los creadores de pedidos pueden tomar decisiones informadas directamente desde la página **Alternativas de entrega** .</span><span class="sxs-lookup"><span data-stu-id="d3bbd-112">Because detailed information is shown for each suggestion, order takers can make informed decisions directly from the **Delivery alternatives** page.</span></span>

## <a name="open-the-delivery-alternatives-page"></a><span data-ttu-id="d3bbd-113">Abrir la página de alternativas de entrega</span><span class="sxs-lookup"><span data-stu-id="d3bbd-113">Open the Delivery alternatives page</span></span>
<span data-ttu-id="d3bbd-114">Puede abrir la página **Alternativas de** **entrega** desde la línea de pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="d3bbd-114">You can open the **Delivery** **alternatives** page from the sales order line.</span></span>

1.  <span data-ttu-id="d3bbd-115">Haga clic en **Productos y suministro** &gt; **Alternativas de entrega**.</span><span class="sxs-lookup"><span data-stu-id="d3bbd-115">Click **Products and supply** &gt; **Delivery alternatives**.</span></span>
2.  <span data-ttu-id="d3bbd-116">Haga clic en **Detalles de línea** &gt; **Entrega** &gt; **Alternativas de la entrega.**</span><span class="sxs-lookup"><span data-stu-id="d3bbd-116">Click **Line details** &gt; **Delivery** &gt; **Delivery alternatives.**</span></span>

<span data-ttu-id="d3bbd-117">También puede abrir la página **Alternativas de entrega** abriendo el espacio de trabajo **Consulta y procesamiento de pedido de ventas** y, a continuación haciendo clic en **Pedidos y favoritos** &gt; **Líneas de pedidos retrasadas** &gt; **Alternativas de entrega** **Nota:** puede abrir la página **Alternativas de entrega** si se cumplen las dos condiciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="d3bbd-117">You can also open the **Delivery alternatives** page by opening the **Sales order processing and inquiry** workspace, and then clicking **Orders and favorites** &gt; **Delayed order lines** &gt; **Delivery alternatives** **Note:** You can open the **Delivery alternatives** page only if both the following conditions are met:</span></span>

-   <span data-ttu-id="d3bbd-118">Toda la información obligatoria de la línea de ventas está rellenada.</span><span class="sxs-lookup"><span data-stu-id="d3bbd-118">All mandatory sales line information is filled in.</span></span>
-   <span data-ttu-id="d3bbd-119">El campo **Control de fecha de entrega** se establece en un valor que no es **Ninguno**.</span><span class="sxs-lookup"><span data-stu-id="d3bbd-119">The **Delivery date control** field is set to a value other than **None**.</span></span>

## <a name="delivery-date-control-methods"></a><span data-ttu-id="d3bbd-120">Métodos de control de fecha de entrega</span><span class="sxs-lookup"><span data-stu-id="d3bbd-120">Delivery date control methods</span></span>
<span data-ttu-id="d3bbd-121">El método de control de fecha de entrega determina cómo el sistema establece las fechas de entrega, cómo se calculan las opciones alternativas de la entrega, y qué información se muestra.</span><span class="sxs-lookup"><span data-stu-id="d3bbd-121">The delivery date control method determines how the system establishes delivery dates, how delivery alternatives are calculated, and what information is shown.</span></span> <span data-ttu-id="d3bbd-122">Tenga en cuenta que el control de datos de entrega toma en cuenta los calendarios.</span><span class="sxs-lookup"><span data-stu-id="d3bbd-122">Note that delivery data control takes calendars into consideration.</span></span> <span data-ttu-id="d3bbd-123">Por lo tanto, los calendarios siguientes pueden afectar a la fecha de recepción sugerida: calendario de almacén, calendario de transporte, calendario del proveedor, y calendario de cliente.</span><span class="sxs-lookup"><span data-stu-id="d3bbd-123">Therefore, the following calendars can affect the suggested receipt date: Warehouse calendar, Transport calendar, Vendor calendar, and Customer calendar.</span></span> <span data-ttu-id="d3bbd-124">La tabla siguiente describe cada método de control de fecha de entrega.</span><span class="sxs-lookup"><span data-stu-id="d3bbd-124">The following table describes each method for delivery date control.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><span data-ttu-id="d3bbd-125"><strong>Método</strong></span><span class="sxs-lookup"><span data-stu-id="d3bbd-125"><strong>Method</strong></span></span></td>
<td><span data-ttu-id="d3bbd-126"><strong>Descripción</strong></span><span class="sxs-lookup"><span data-stu-id="d3bbd-126"><strong>Description</strong></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="d3bbd-127"><strong>Ninguna</strong></span><span class="sxs-lookup"><span data-stu-id="d3bbd-127"><strong>None</strong></span></span></td>
<td><ul>
<li><span data-ttu-id="d3bbd-128">Las alternativas de entrega para líneas de ventas no se admiten.</span><span class="sxs-lookup"><span data-stu-id="d3bbd-128">Delivery alternatives for sales lines aren't supported.</span></span> <span data-ttu-id="d3bbd-129">Esta opción desactiva el control de datos de la entrega.</span><span class="sxs-lookup"><span data-stu-id="d3bbd-129">This option turns off delivery data control.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="d3bbd-130"><strong>Plazo de ventas</strong></span><span class="sxs-lookup"><span data-stu-id="d3bbd-130"><strong>Sales lead time</strong></span></span></td>
<td><ul>
<li><span data-ttu-id="d3bbd-131">Las alternativas de la entrega se calculan en función del plazo de ventas predefinido.</span><span class="sxs-lookup"><span data-stu-id="d3bbd-131">Delivery alternatives are calculated based on the predefined sales lead time.</span></span> <span data-ttu-id="d3bbd-132">Los días de transporte se calculan en función del modo de entrega.</span><span class="sxs-lookup"><span data-stu-id="d3bbd-132">The transport days are calculated based on the mode of delivery.</span></span></li>
<li><span data-ttu-id="d3bbd-133">Las alternativas de la entrega incluyen los almacenes que tienen inventario disponible y pedidos de oferta/demanda.</span><span class="sxs-lookup"><span data-stu-id="d3bbd-133">Delivery alternatives include warehouses that have on-hand inventory, and supply/demand orders.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="d3bbd-134"><strong>NNC</strong></span><span class="sxs-lookup"><span data-stu-id="d3bbd-134"><strong>ATP</strong></span></span></td>
<td><ul>
<li><span data-ttu-id="d3bbd-135">Las alternativas de la entrega se calculan en función de la lógica de neto no comprometido (ATP).</span><span class="sxs-lookup"><span data-stu-id="d3bbd-135">Delivery alternatives are calculated based on available to promise (ATP) logic.</span></span> <span data-ttu-id="d3bbd-136">Se consideran la disponibilidad actual y la disponibilidad futura.</span><span class="sxs-lookup"><span data-stu-id="d3bbd-136">The current availability and expected future availability are considered.</span></span> <span data-ttu-id="d3bbd-137">Los días de transporte se calculan en función del modo de entrega.</span><span class="sxs-lookup"><span data-stu-id="d3bbd-137">The transport days are calculated based on the mode of delivery.</span></span></li>
<li><span data-ttu-id="d3bbd-138">Las alternativas de la entrega incluyen los almacenes que tienen inventario disponible y pedidos de oferta/demanda.</span><span class="sxs-lookup"><span data-stu-id="d3bbd-138">Delivery alternatives include warehouses that have on-hand inventory, and supply/demand orders.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="d3bbd-139"><strong>NNC + Margen de emisión</strong></span><span class="sxs-lookup"><span data-stu-id="d3bbd-139"><strong>ATP + Issue margin</strong></span></span></td>
<td><ul>
<li><span data-ttu-id="d3bbd-140">Las alternativas de la entrega se calculan como para el método de NNC, pero el margen de emisión se incluye en el cálculo.</span><span class="sxs-lookup"><span data-stu-id="d3bbd-140">Delivery alternatives are calculated as for the ATP method, but the issue margin is included in the calculation.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="d3bbd-141"><strong>CTP</strong></span><span class="sxs-lookup"><span data-stu-id="d3bbd-141"><strong>CTP</strong></span></span></td>
<td><ul>
<li><span data-ttu-id="d3bbd-142">Las alternativas de la entrega se calculan en función de la lógica de capaz de comprometer (CTP).</span><span class="sxs-lookup"><span data-stu-id="d3bbd-142">Delivery alternatives are calculated based on the capable to promise (CTP) logic.</span></span> <span data-ttu-id="d3bbd-143">La expansión de MRP se usa para determinar la disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="d3bbd-143">MRP explosion is used to determine availability.</span></span> <span data-ttu-id="d3bbd-144">Tenga en cuenta que, como mínimo, CTP compensa las fechas de entrega con el plazo de ventas.</span><span class="sxs-lookup"><span data-stu-id="d3bbd-144">Note that, at a minimum, CTP offsets delivery dates to the sales lead time.</span></span> <span data-ttu-id="d3bbd-145">Los días de transporte se calculan en función del modo de entrega.</span><span class="sxs-lookup"><span data-stu-id="d3bbd-145">The transport days are calculated based on the mode of delivery.</span></span></li>
<li><span data-ttu-id="d3bbd-146">Las alternativas de la entrega incluyen sugerencias para los siguientes almacenes:</span><span class="sxs-lookup"><span data-stu-id="d3bbd-146">Delivery alternatives include suggestions for the following warehouses:</span></span>
<ul>
<li><span data-ttu-id="d3bbd-147">Almacén actual</span><span class="sxs-lookup"><span data-stu-id="d3bbd-147">Current warehouse</span></span></li>
<li><span data-ttu-id="d3bbd-148">Almacén predeterminado</span><span class="sxs-lookup"><span data-stu-id="d3bbd-148">Default warehouse</span></span></li>
<li><span data-ttu-id="d3bbd-149">Todos los almacenes que tienen inventario disponible</span><span class="sxs-lookup"><span data-stu-id="d3bbd-149">All warehouses that have available on-hand inventory</span></span></li>
<li><span data-ttu-id="d3bbd-150">Todos los almacenes que tienen pedidos de suministro</span><span class="sxs-lookup"><span data-stu-id="d3bbd-150">All warehouses that have supply orders</span></span></li>
<li><span data-ttu-id="d3bbd-151">Todos los almacenes que tienen versiones activas de la lista de materiales (L. MAT)</span><span class="sxs-lookup"><span data-stu-id="d3bbd-151">All warehouses that have active bill of materials (BOM) versions</span></span></li>
</ul></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="view-information-about-delivery-alternatives"></a><span data-ttu-id="d3bbd-152">Ver información acerca de alternativas de la entrega</span><span class="sxs-lookup"><span data-stu-id="d3bbd-152">View information about delivery alternatives</span></span>
<span data-ttu-id="d3bbd-153">Esta sección describe la información sobre alternativas de entrega que está disponible en cada ficha de la página **Alternativas de entrega**.</span><span class="sxs-lookup"><span data-stu-id="d3bbd-153">This section describes the information about delivery alternatives that is available on each tab of the **Delivery alternatives** page.</span></span>

### <a name="products"></a><span data-ttu-id="d3bbd-154">Productos</span><span class="sxs-lookup"><span data-stu-id="d3bbd-154">Products</span></span>

<span data-ttu-id="d3bbd-155">Esta ficha muestra un resumen del producto y los detalles de la línea de ventas actual.</span><span class="sxs-lookup"><span data-stu-id="d3bbd-155">This tab shows a summary of the product and details of the current sales line.</span></span>

### <a name="delivery-alternatives"></a><span data-ttu-id="d3bbd-156">Alternativas de entrega</span><span class="sxs-lookup"><span data-stu-id="d3bbd-156">Delivery alternatives</span></span>

<span data-ttu-id="d3bbd-157">Esta ficha muestra una lista de alternativas de entrega que se clasifica por datos de recepción.</span><span class="sxs-lookup"><span data-stu-id="d3bbd-157">This tab shows a list of delivery alternatives that is sorted by receipt data.</span></span> <span data-ttu-id="d3bbd-158">Encima de la lista, puede seleccionar en qué opciones basar las sugerencias.</span><span class="sxs-lookup"><span data-stu-id="d3bbd-158">Above the list, you can select which options to base the suggestions on.</span></span> <span data-ttu-id="d3bbd-159">También puede seleccionar el modo de entrega, que determina los días de transporte.</span><span class="sxs-lookup"><span data-stu-id="d3bbd-159">You can also select the mode of delivery, which determines the transport days.</span></span> <span data-ttu-id="d3bbd-160">Están disponibles las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="d3bbd-160">The following options are available:</span></span>

-   <span data-ttu-id="d3bbd-161">**Incluir otras variantes del producto** - Esta opción está disponible para los productos que tienen variantes de producto.</span><span class="sxs-lookup"><span data-stu-id="d3bbd-161">**Include other product variants** - This option is available for products that have product variants.</span></span> <span data-ttu-id="d3bbd-162">Incluirá alternativas de entrega para otras variantes del producto.</span><span class="sxs-lookup"><span data-stu-id="d3bbd-162">It will include delivery alternatives for other variants of the product.</span></span> <span data-ttu-id="d3bbd-163">Esta opción no está disponible para CTP.</span><span class="sxs-lookup"><span data-stu-id="d3bbd-163">This option isn't available for CTP.</span></span>
-   <span data-ttu-id="d3bbd-164">**Incluir cantidad parcial** - De forma predeterminada, solo las sugerencias que cumplen la cantidad completa de la línea de ventas se incluyen.</span><span class="sxs-lookup"><span data-stu-id="d3bbd-164">**Include partial quantity** - By default, only suggestions that fulfill the full quantity of the sales line are included.</span></span> <span data-ttu-id="d3bbd-165">Seleccione esta opción para incluir las sugerencias que cumplen parcialmente la línea de pedido.</span><span class="sxs-lookup"><span data-stu-id="d3bbd-165">Select this option to include suggestions that only partially fulfill the order line.</span></span> <span data-ttu-id="d3bbd-166">Esta opción es útil si el cliente solicita una fecha de entrega anterior y acepta una entrega parcial.</span><span class="sxs-lookup"><span data-stu-id="d3bbd-166">This option is useful when the customer requests an earlier delivery date and accepts partial delivery.</span></span>
-   <span data-ttu-id="d3bbd-167">**Incluir fechas posteriores** - De forma predeterminada, se muestran solo las sugerencias que son mejores (anteriores) que las fechas actuales de la línea de ventas.</span><span class="sxs-lookup"><span data-stu-id="d3bbd-167">**Include later dates** - By default, only suggestions that are better (earlier) than the current dates on the sales line are shown.</span></span> <span data-ttu-id="d3bbd-168">Seleccione esta opción para incluir fechas posteriores.</span><span class="sxs-lookup"><span data-stu-id="d3bbd-168">Select this option to include later dates.</span></span> <span data-ttu-id="d3bbd-169">Esta opción puede ser útil en situaciones en las que tienen prioridad parámetros que no son la fecha.</span><span class="sxs-lookup"><span data-stu-id="d3bbd-169">This option can be useful in situations where parameters other than the date have priority.</span></span> <span data-ttu-id="d3bbd-170">Por ejemplo, podría preferirse un proveedor o un almacén específico.</span><span class="sxs-lookup"><span data-stu-id="d3bbd-170">For example, a specific vendor or warehouse might be preferred.</span></span>
-   <span data-ttu-id="d3bbd-171">**Modo de entrega** - Seleccione el modo de entrega preferido para optimizar el tiempo y el coste de transporte.</span><span class="sxs-lookup"><span data-stu-id="d3bbd-171">**Mode of delivery** - Select the preferred mode of delivery to optimize transport time and cost.</span></span> <span data-ttu-id="d3bbd-172">Verá inmediatamente el efecto en las alternativas sugeridas de entrega.</span><span class="sxs-lookup"><span data-stu-id="d3bbd-172">You will immediately see the effect on the suggested delivery alternatives.</span></span> <span data-ttu-id="d3bbd-173">Por lo tanto, es fácil comparar alternativas.</span><span class="sxs-lookup"><span data-stu-id="d3bbd-173">Therefore, it's easy to compare the alternatives.</span></span>
-   <span data-ttu-id="d3bbd-174">**Obtención compra** - Cuando se active la compra, las alternativas de entrega sugeridas incluyen opciones para comprar de proveedores externos y de otras empresas de la empresa (empresas vinculadas).</span><span class="sxs-lookup"><span data-stu-id="d3bbd-174">**Include procurement** - When procurement is selected, the suggested delivery alternatives include options to procure from both external vendors and other companies in the enterprise (intercompany).</span></span> <span data-ttu-id="d3bbd-175">La opción **Incluir compra** se admite para el control de la fecha de entrega NNC y NNC + Margen de emisión.</span><span class="sxs-lookup"><span data-stu-id="d3bbd-175">The **Include procurement** option is supported for ATP and ATP + Issue margin delivery date control.</span></span> <span data-ttu-id="d3bbd-176">Las opciones de compra del proveedor predeterminado de la compra del producto y todos los proveedores aprobados para el producto se incluyen.</span><span class="sxs-lookup"><span data-stu-id="d3bbd-176">Procurement options from the default purchase vendor for the product and all approved vendors for the product are included.</span></span>
-   <span data-ttu-id="d3bbd-177">Para los proveedores externos, el cálculo se basa en el plazo de compra.</span><span class="sxs-lookup"><span data-stu-id="d3bbd-177">For external vendors, the calculation is based on the purchase lead time.</span></span>
-   <span data-ttu-id="d3bbd-178">Para empresas vinculadas, el cálculo examina qué está disponible en la empresa de abastecimiento, en función del control de fecha de entrega en la empresa de abastecimiento.</span><span class="sxs-lookup"><span data-stu-id="d3bbd-178">For intercompany, the calculation considers what is available from the sourcing company, based on delivery date control in the sourcing company.</span></span>
-   <span data-ttu-id="d3bbd-179">**Tipo de entrega** (Relevante para la adquisición)</span><span class="sxs-lookup"><span data-stu-id="d3bbd-179">**Delivery type** (Relevant for procurement)</span></span>
    -   <span data-ttu-id="d3bbd-180">**Existencias** - Los productos se envían desde el almacén de abastecimiento al sitio/al almacén de la línea de ventas.</span><span class="sxs-lookup"><span data-stu-id="d3bbd-180">**Stock** - Products are shipped from the sourcing warehouse to the site/warehouse on the sales line.</span></span> <span data-ttu-id="d3bbd-181">A continuación se envían desde ese almacén al cliente.</span><span class="sxs-lookup"><span data-stu-id="d3bbd-181">They are then shipped from that warehouse to the customer.</span></span>
    -   <span data-ttu-id="d3bbd-182">**Entrega directa** - Los productos se envían directamente desde el almacén de abastecimiento al cliente.</span><span class="sxs-lookup"><span data-stu-id="d3bbd-182">**Direct delivery** - Products are shipped directly from the sourcing warehouse to the customer.</span></span>

### <a name="availability-information"></a><span data-ttu-id="d3bbd-183">Información de disponibilidad</span><span class="sxs-lookup"><span data-stu-id="d3bbd-183">Availability information</span></span>

<span data-ttu-id="d3bbd-184">La información de esta ficha está relacionada con la línea alternativa de entrega que está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="d3bbd-184">Information on this tab is related to the delivery alternative line that is selected.</span></span> <span data-ttu-id="d3bbd-185">La siguiente información se muestra, en función del control de fecha de entrega para la línea de ventas:</span><span class="sxs-lookup"><span data-stu-id="d3bbd-185">The following information is shown, depending on the delivery date control for the sales line:</span></span>

-   <span data-ttu-id="d3bbd-186">**Plazo de ventas**</span><span class="sxs-lookup"><span data-stu-id="d3bbd-186">**Sales lead time**</span></span>
    -   <span data-ttu-id="d3bbd-187">**Disponible hoy** - Muestra el inventario de cantidad física actual disponible, el inventario físico reservado y el inventario físico disponible.</span><span class="sxs-lookup"><span data-stu-id="d3bbd-187">**Available today** - Show the current physical on-hand, physical reserved, and available physical inventory.</span></span>
    -   <span data-ttu-id="d3bbd-188">**Parámetros** - Muestra la unidad de inventario y el plazo de ventas.</span><span class="sxs-lookup"><span data-stu-id="d3bbd-188">**Parameters** - Show the inventory unit and sales lead time.</span></span>

-   <span data-ttu-id="d3bbd-189">**NNC y NNC + Margen de emisión**</span><span class="sxs-lookup"><span data-stu-id="d3bbd-189">**ATP and ATP + Issue margin**</span></span>
    -   <span data-ttu-id="d3bbd-190">**Disponible hoy** - Muestra el inventario de cantidad física actual disponible, el inventario físico reservado y el inventario físico disponible.</span><span class="sxs-lookup"><span data-stu-id="d3bbd-190">**Available today** - Show the current physical on-hand, physical reserved, and available physical inventory.</span></span>
    -   <span data-ttu-id="d3bbd-191">**Parámetros** - Muestra la unidad de inventario y el plazo de ventas.</span><span class="sxs-lookup"><span data-stu-id="d3bbd-191">**Parameters** - Show the inventory unit and sales lead time.</span></span>
    -   <span data-ttu-id="d3bbd-192">**Disponibilidad futura** - Muestra una representación gráfica de la disponibilidad actual y futura para el sitio y el almacén seleccionados en **Alternativas de entrega**.</span><span class="sxs-lookup"><span data-stu-id="d3bbd-192">**Future availability** - Show a graphical representation of current and future availability for the selected site and warehouse under **Delivery alternatives**.</span></span> <span data-ttu-id="d3bbd-193">Puede hacer clic en las columnas del gráfico para ver más detalles sobre la disponibilidad futura del producto.</span><span class="sxs-lookup"><span data-stu-id="d3bbd-193">You can click the chart columns to see more detailed information about the future availability of the product.</span></span> <span data-ttu-id="d3bbd-194">El control deslizante muestra una lista de pedidos relevantes de oferta y demanda en el límite de tiempo del NNC.</span><span class="sxs-lookup"><span data-stu-id="d3bbd-194">The slider shows a list of relevant demand and supply orders within the ATP time fence.</span></span>

-   <span data-ttu-id="d3bbd-195">**CTP**</span><span class="sxs-lookup"><span data-stu-id="d3bbd-195">**CTP**</span></span>
    -   <span data-ttu-id="d3bbd-196">**Disponible hoy** - Muestra el inventario de cantidad física actual disponible, el inventario físico reservado y el inventario físico disponible.</span><span class="sxs-lookup"><span data-stu-id="d3bbd-196">**Available today** - Show the current physical on-hand, physical reserved, and available physical inventory.</span></span>
    -   <span data-ttu-id="d3bbd-197">**Parámetros** - Muestra la unidad de inventario y el plazo de ventas.</span><span class="sxs-lookup"><span data-stu-id="d3bbd-197">**Parameters** - Show the inventory unit and sales lead time.</span></span>
    -   <span data-ttu-id="d3bbd-198">**Expansión** - Muestra una expansión de suministro de la alternativa de entrega seleccionada.</span><span class="sxs-lookup"><span data-stu-id="d3bbd-198">**Explosion** - Show a supply explosion of the selected delivery alternative.</span></span> <span data-ttu-id="d3bbd-199">Puede usar la **Configuración** para cambiar los campos y las dimensiones de inventario que se muestran en la expansión.</span><span class="sxs-lookup"><span data-stu-id="d3bbd-199">You can use **Setup** to change the fields and inventory dimensions that are shown in the explosion.</span></span>

### <a name="impact-of-selected-alternative"></a><span data-ttu-id="d3bbd-200">Impacto de la alternativa seleccionada</span><span class="sxs-lookup"><span data-stu-id="d3bbd-200">Impact of selected alternative</span></span>

<span data-ttu-id="d3bbd-201">Esta ficha destaca el impacto de la alternativa seleccionada de entrega.</span><span class="sxs-lookup"><span data-stu-id="d3bbd-201">This tab highlights the impact of the selected delivery alternative.</span></span> <span data-ttu-id="d3bbd-202">Si hace clic en **Aceptar**, la línea de ventas se actualiza con los valores resaltados en las columnas SELECCIONADAS.</span><span class="sxs-lookup"><span data-stu-id="d3bbd-202">If you click **OK**, the sales line is updated with the highlighted values in the SELECTED columns.</span></span> <span data-ttu-id="d3bbd-203">Tenga en cuenta que, si la cantidad de la alternativa seleccionada de entrega es inferior a la cantidad de la línea de ventas, se crea una programación de entrega y la línea de pedido se divide en dos líneas: una línea para la cantidad seleccionada y una línea para la cantidad restante.</span><span class="sxs-lookup"><span data-stu-id="d3bbd-203">Note that, if the quantity on the selected delivery alternative is less than quantity on the sales line, a delivery schedule is created, and the order line is split into two lines: one line for the selected quantity and one line for the remaining quantity.</span></span> <span data-ttu-id="d3bbd-204">También puede actualizar la línea comercial para que coincida con las líneas de la programación y afecte a los precios.</span><span class="sxs-lookup"><span data-stu-id="d3bbd-204">You can also update the commercial line so that it matches the schedule lines and affects the pricing.</span></span>

<a name="see-also"></a><span data-ttu-id="d3bbd-205">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d3bbd-205">See also</span></span>
--------

[<span data-ttu-id="d3bbd-206">Compromisos de pedidos</span><span class="sxs-lookup"><span data-stu-id="d3bbd-206">Order promising</span></span>](delivery-dates-available-promise-calculations.md)





