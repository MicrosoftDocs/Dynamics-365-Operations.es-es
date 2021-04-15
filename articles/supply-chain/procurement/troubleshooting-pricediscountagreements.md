---
title: Solucionar problemas de precios, descuentos, acuerdos y devoluciones
description: En este tema se describe cómo solucionar problemas que pueden surgir al trabajar con precios, descuentos, acuerdos y devoluciones.
author: SmithaNataraj
ms.date: 09/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart, PurchRFQTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-9-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 12bc3cbccb1577c278489f640299510b3ced17e7
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5811095"
---
# <a name="troubleshoot-prices-discounts-agreements-and-rebates"></a><span data-ttu-id="06006-103">Solucionar problemas de precios, descuentos, acuerdos y devoluciones</span><span class="sxs-lookup"><span data-stu-id="06006-103">Troubleshoot prices, discounts, agreements, and rebates</span></span>

<span data-ttu-id="06006-104">En este tema se describe cómo solucionar problemas que pueden surgir al trabajar con precios, descuentos, acuerdos y devoluciones.</span><span class="sxs-lookup"><span data-stu-id="06006-104">This topic describes how to fix issues that you might encounter while you work with prices, discounts, agreements, and rebates.</span></span>

## <a name="i-cant-link-a-purchase-agreement-to-a-purchase-order-line-after-the-purchase-order-is-created"></a><span data-ttu-id="06006-105">No puedo vincular un acuerdo de compra a una línea de pedido de compra después de que se haya creado el pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="06006-105">I can't link a purchase agreement to a purchase order line after the purchase order is created.</span></span>

<span data-ttu-id="06006-106">Un acuerdo de compra debe asociarse a un pedido de compra cuando se crea el pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="06006-106">A purchase agreement must be associated with a purchase order when the purchase order is created.</span></span> <span data-ttu-id="06006-107">De lo contrario, las líneas del pedido de compra no se pueden asociar a las líneas del acuerdo de compra.</span><span class="sxs-lookup"><span data-stu-id="06006-107">Otherwise, purchase order lines can't be associated with purchase agreement lines.</span></span>

## <a name="what-check-triggers-the-update-prices-and-discounts-entered-manually-or-external-document-message"></a><span data-ttu-id="06006-108">¿Qué comprobación genera el mensaje "Actualizar precios y descuentos introducidos manualmente o documento externo"?</span><span class="sxs-lookup"><span data-stu-id="06006-108">What check triggers the "Update prices and discounts entered manually or external document" message?</span></span>

<span data-ttu-id="06006-109">Al cambiar la fecha de envío, es posible que reciba el mensaje "Actualizar precios y descuentos introducidos manualmente o documento externo".</span><span class="sxs-lookup"><span data-stu-id="06006-109">When you change the shipping date, you might receive a message that states, "Update prices and discounts entered manually or external document."</span></span> <span data-ttu-id="06006-110">Recibe este mensaje porque, si la fecha de envío cambia, es posible que se active un acuerdo comercial o de venta diferente y esto provoque un cambio de precio.</span><span class="sxs-lookup"><span data-stu-id="06006-110">You receive this message because, if the shipping date is changed, a different trade or sales agreement might be triggered and cause a price change.</span></span> <span data-ttu-id="06006-111">Un cambio en la fecha de envío también puede afectar a la programación del almacén y a otra información relacionada.</span><span class="sxs-lookup"><span data-stu-id="06006-111">A change to the shipping date can also affect warehouse schedules and other related information.</span></span>

<span data-ttu-id="06006-112">El mensaje se genera cada vez que se cambia alguna de las fechas u otros parámetros.</span><span class="sxs-lookup"><span data-stu-id="06006-112">The message is triggered whenever any of the dates or some other parameters are changed.</span></span> <span data-ttu-id="06006-113">El propósito del mensaje es asegurarse de que esté al tanto de los cambios de precios que pueden ocurrir a causa de esos cambios.</span><span class="sxs-lookup"><span data-stu-id="06006-113">The purpose of the message is to make sure that you're aware of price changes that can occur because of those changes.</span></span>

<span data-ttu-id="06006-114">El mensaje es el aviso de evaluación del acuerdo comercial (TAE).</span><span class="sxs-lookup"><span data-stu-id="06006-114">The message is the trade agreement evaluation (TAE) prompt.</span></span> <span data-ttu-id="06006-115">Para obtener una descripción completa, consulte [Políticas de evaluación de acuerdos comerciales](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/trade-agreement-evaluation-policies-white-paper).</span><span class="sxs-lookup"><span data-stu-id="06006-115">For a full description, see [Trade agreement evaluation policies](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/trade-agreement-evaluation-policies-white-paper).</span></span>

## <a name="a-purchase-order-receipt-doesnt-include-all-charges"></a><span data-ttu-id="06006-116">El recibo de un pedido de compra no incluye todos los cargos.</span><span class="sxs-lookup"><span data-stu-id="06006-116">A purchase order receipt doesn't include all charges.</span></span>

### <a name="reproduce-the-issue"></a><span data-ttu-id="06006-117">Reproducir el problema</span><span class="sxs-lookup"><span data-stu-id="06006-117">Reproduce the issue</span></span>

<span data-ttu-id="06006-118">El siguiente procedimiento muestra una manera de reproducir el problema.</span><span class="sxs-lookup"><span data-stu-id="06006-118">The following procedure shows one way to reproduce the issue.</span></span>

1. <span data-ttu-id="06006-119">En la página **Parámetros de adquisición y abastecimiento**, en la pestaña **Entrega**, asegúrese de que la opción **Generar cargos al recibir el producto** está establecida en *Sí*.</span><span class="sxs-lookup"><span data-stu-id="06006-119">On the **Procurement and sourcing parameters** page, on the **Delivery** tab, make sure that the **Generate charges on product receipt** option is set to *Yes*.</span></span>
1. <span data-ttu-id="06006-120">Cree un pedido de compra que incluya cargos.</span><span class="sxs-lookup"><span data-stu-id="06006-120">Create a purchase order that includes charges.</span></span>
1. <span data-ttu-id="06006-121">Confirme el pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="06006-121">Confirm the purchase order.</span></span>
1. <span data-ttu-id="06006-122">Reciba el pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="06006-122">Receive the purchase order.</span></span>
1. <span data-ttu-id="06006-123">Vea el total de recepción y compárelo con el total esperado.</span><span class="sxs-lookup"><span data-stu-id="06006-123">Look at the receipt total, and compare it to the expected total.</span></span>
1. <span data-ttu-id="06006-124">Observe que no todos los cargos están incluidos en la recepción del pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="06006-124">Notice that not all the charges are included on the purchase order receipt.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="06006-125">Solución del problema</span><span class="sxs-lookup"><span data-stu-id="06006-125">Issue resolution</span></span>

<span data-ttu-id="06006-126">La resolución depende de la forma en que se hayan configurado los distintos cargos.</span><span class="sxs-lookup"><span data-stu-id="06006-126">The resolution depends on the way that the miscellaneous charges have been set up.</span></span> <span data-ttu-id="06006-127">Para obtener información sobre cómo configurar diversos cargos para cumplir con los requisitos, consulte la siguiente publicación de blog: [Contabilizar cargos varios en la recepción del producto](https://cloudblogs.microsoft.com/dynamics365/no-audience/2014/11/11/post-misc-charges-at-time-of-product-receipt/).</span><span class="sxs-lookup"><span data-stu-id="06006-127">For information about how to set up miscellaneous charges to meet your requirements, see the following blog post: [Post misc. charges at time of product receipt](https://cloudblogs.microsoft.com/dynamics365/no-audience/2014/11/11/post-misc-charges-at-time-of-product-receipt/).</span></span>

## <a name="trade-agreement-prices-and-discounts-arent-applied-on-sales-or-purchase-order-lines-that-are-imported-through-data-management"></a><span data-ttu-id="06006-128">Los precios y descuentos de acuerdos comerciales no se aplican a las líneas de pedidos de ventas o de compra que se importan a través de la administración de datos.</span><span class="sxs-lookup"><span data-stu-id="06006-128">Trade agreement prices and discounts aren't applied on sales or purchase order lines that are imported through data management.</span></span>

### <a name="issue-description"></a><span data-ttu-id="06006-129">Descripción del problema</span><span class="sxs-lookup"><span data-stu-id="06006-129">Issue description</span></span>

<span data-ttu-id="06006-130">Los acuerdos comerciales que son aplicables a las líneas de pedidos de ventas o de compra no se aplican a líneas que se importan a través de la administración de datos.</span><span class="sxs-lookup"><span data-stu-id="06006-130">Trade agreements that are applicable to sales or purchase order lines aren't applied on lines that are imported through data management.</span></span> <span data-ttu-id="06006-131">Sin embargo, los mismos acuerdos comerciales se aplican a las líneas de pedido de compra o de venta que se crean manualmente.</span><span class="sxs-lookup"><span data-stu-id="06006-131">However, the same trade agreements are applied on sales or purchase order lines that are manually created.</span></span>

### <a name="reason-for-the-issue"></a><span data-ttu-id="06006-132">Motivo del problema</span><span class="sxs-lookup"><span data-stu-id="06006-132">Reason for the issue</span></span>

<span data-ttu-id="06006-133">Si las líneas del pedido de compra que se importan a través de la administración de datos ya incluyen información de precios, el acuerdo comercial no se volverá a evaluar para esas líneas.</span><span class="sxs-lookup"><span data-stu-id="06006-133">If purchase order lines that are imported via data management already include price information, the trade agreement won't be reevaluated for those lines.</span></span> <span data-ttu-id="06006-134">Por ejemplo, si **Porcentaje de descuento de línea** o cualquiera de los valores de precio y descuento se establecen para una línea, los acuerdos comerciales no se buscarán para esa línea.</span><span class="sxs-lookup"><span data-stu-id="06006-134">For example, if **Line discount percentage** or any of the price and discount values is set for a line, then trade agreements will not be looked up for that line.</span></span>

### <a name="issue-workaround"></a><span data-ttu-id="06006-135">Solución del problema</span><span class="sxs-lookup"><span data-stu-id="06006-135">Issue workaround</span></span>

<span data-ttu-id="06006-136">Se espera este comportamiento y es similar tanto para los pedidos de ventas como para los pedidos de compra.</span><span class="sxs-lookup"><span data-stu-id="06006-136">This behavior is expected, and is similar for both sales orders and purchase orders.</span></span>

<span data-ttu-id="06006-137">Como solución temporal, importe las líneas del pedido de compra sin establecer ninguna información de precio.</span><span class="sxs-lookup"><span data-stu-id="06006-137">As a workaround, import the purchase order lines without setting any price information.</span></span> <span data-ttu-id="06006-138">A continuación se aplicarán los acuerdos comerciales y las líneas de pedido de compra se actualizarán en función de los acuerdos comerciales definidos.</span><span class="sxs-lookup"><span data-stu-id="06006-138">The trade agreements will then be applied, and the purchase order lines will be updated based on the defined trade agreements.</span></span>

## <a name="a-vendor-rebate-isnt-cumulated-based-on-invoices"></a><span data-ttu-id="06006-139">Una devolución de proveedor no se acumula según las facturas.</span><span class="sxs-lookup"><span data-stu-id="06006-139">A vendor rebate isn't cumulated based on invoices.</span></span>

### <a name="issue-description"></a><span data-ttu-id="06006-140">Descripción del problema</span><span class="sxs-lookup"><span data-stu-id="06006-140">Issue description</span></span>

<span data-ttu-id="06006-141">Si las facturas que se registran tienen diferentes fechas de vencimiento, esas facturas no se reflejan en las devoluciones de proveedores que se generan a partir de ellas.</span><span class="sxs-lookup"><span data-stu-id="06006-141">If invoices that are posted have different due dates, those invoices aren't reflected in vendor rebates that are generated from them.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="06006-142">Solución del problema</span><span class="sxs-lookup"><span data-stu-id="06006-142">Issue resolution</span></span>

<span data-ttu-id="06006-143">Porque se ha diseñado así, no se tiene en cuenta la fecha de vencimiento al calcular el reembolso del proveedor.</span><span class="sxs-lookup"><span data-stu-id="06006-143">By design, the due date isn't considered when the vendor rebate is calculated.</span></span> <span data-ttu-id="06006-144">Considere la posibilidad de personalizar el sistema para que la fecha de vencimiento y la relación con la factura sean más evidentes con respecto al reembolso real del proveedor.</span><span class="sxs-lookup"><span data-stu-id="06006-144">Consider customizing the system so that the due date and the relation to the invoice are more apparent with respect to the actual vendor rebate.</span></span>

## <a name="unit-prices-on-purchase-orders-arent-calculated-based-on-the-unit-conversion"></a><span data-ttu-id="06006-145">Los precios unitarios de los pedidos de compra no se calculan en función de la conversión de unidades.</span><span class="sxs-lookup"><span data-stu-id="06006-145">Unit prices on purchase orders aren't calculated based on the unit conversion.</span></span>

### <a name="issue-description"></a><span data-ttu-id="06006-146">Descripción del problema</span><span class="sxs-lookup"><span data-stu-id="06006-146">Issue description</span></span>

<span data-ttu-id="06006-147">Cuando se cambia una unidad en un pedido de compra, los precios de los acuerdos comerciales no se vuelven a calcular de acuerdo con las definiciones de conversión de unidades.</span><span class="sxs-lookup"><span data-stu-id="06006-147">When a unit is changed on a purchase order, trade agreement prices aren't recalculated according to unit conversion definitions.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="06006-148">Solución del problema</span><span class="sxs-lookup"><span data-stu-id="06006-148">Issue resolution</span></span>

<span data-ttu-id="06006-149">Los precios siempre se obtienen de acuerdos comerciales (u otras configuraciones de precios en el sistema, como acuerdos de venta o precios de artículos) y se establecen para una unidad.</span><span class="sxs-lookup"><span data-stu-id="06006-149">Prices are always obtained from trade agreements (or other price settings in the system, such as sales agreements or item prices), and they are set for a unit.</span></span>

<span data-ttu-id="06006-150">Si se cambia la unidad en una línea de pedido, el sistema busca un precio para la nueva unidad y aplica ese precio.</span><span class="sxs-lookup"><span data-stu-id="06006-150">If the unit is changed on an order line, the system looks for a price for the new unit and applies that price.</span></span> <span data-ttu-id="06006-151">Si no se encuentra un precio para la unidad, el sistema no aplica un precio.</span><span class="sxs-lookup"><span data-stu-id="06006-151">If no price is found for the unit, the system doesn't apply a price.</span></span> <span data-ttu-id="06006-152">La conversión de unidades no se puede utilizar para volver a calcular el precio en otra unidad.</span><span class="sxs-lookup"><span data-stu-id="06006-152">The unit conversion can't be used to recalculate the price into another unit.</span></span> <span data-ttu-id="06006-153">En teoría, el precio de una caja de diez podría no ser igual a diez veces el precio de una caja.</span><span class="sxs-lookup"><span data-stu-id="06006-153">Theoretically, the price for one box of ten might not equal ten times the price of one box.</span></span>

### <a name="issue-workaround"></a><span data-ttu-id="06006-154">Solución del problema</span><span class="sxs-lookup"><span data-stu-id="06006-154">Issue workaround</span></span>

<span data-ttu-id="06006-155">Una forma de solucionar este problema es asegurarse de que existen acuerdos comerciales para las unidades que espera que se utilicen en las líneas de pedido de artículo.</span><span class="sxs-lookup"><span data-stu-id="06006-155">One way to work around this issue is to make sure that there are trade agreements for the units that you expect will be used on order lines for the item.</span></span>

## <a name="currency-conversion-issues-occur-with-trade-agreements"></a><span data-ttu-id="06006-156">En los acuerdos comerciales se producen problemas de conversión de divisa.</span><span class="sxs-lookup"><span data-stu-id="06006-156">Currency conversion issues occur with trade agreements.</span></span>

<span data-ttu-id="06006-157">Los precios de los acuerdos comerciales no se vuelven a calcular según la divisa cuando esta difiere en un pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="06006-157">Trade agreement prices aren't recalculated according to the currency when the currency differs on a purchase order.</span></span>

<span data-ttu-id="06006-158">La característica *Divisa genérica* permite definir precios y descuentos en una sola divisa.</span><span class="sxs-lookup"><span data-stu-id="06006-158">The *Generic currency* feature lets you define prices and discounts in only one currency.</span></span> <span data-ttu-id="06006-159">A continuación, puede convertir a otras divisas que necesite.</span><span class="sxs-lookup"><span data-stu-id="06006-159">You can then convert to other currencies as you require.</span></span> <span data-ttu-id="06006-160">Además, una vez realizada la conversión, la función puede aplicar automáticamente el redondeo psicológico.</span><span class="sxs-lookup"><span data-stu-id="06006-160">Furthermore, after the conversion is done, the feature can automatically apply smart rounding.</span></span>

## <a name="when-i-open-the-purchase-agreement-page-in-a-line-view-mode-i-cant-personalize-the-page-by-adding-the-price-unit-field-in-the-overview-of-the-line"></a><span data-ttu-id="06006-161">Cuando abro la página Acuerdo de compra en un modo de vista de línea, no puedo personalizar la página agregando el campo Unidad de precio en la descripción general de la línea.</span><span class="sxs-lookup"><span data-stu-id="06006-161">When I open the Purchase agreement page in a line view mode, I can't personalize the page by adding the Price unit field in the overview of the line.</span></span>

<span data-ttu-id="06006-162">Algunos campos compartidos en el marco del acuerdo no se pueden incluir en las personalizaciones.</span><span class="sxs-lookup"><span data-stu-id="06006-162">Some shared fields in the agreement framework can't be included in personalizations.</span></span> <span data-ttu-id="06006-163">Esta limitación se produce debido al modelo de datos implementado.</span><span class="sxs-lookup"><span data-stu-id="06006-163">This limitation occurs because of the data model that is implemented.</span></span> <span data-ttu-id="06006-164">Por lo tanto, no puede personalizar el campo **Precio unitario**.</span><span class="sxs-lookup"><span data-stu-id="06006-164">Therefore, you can't personalize the **Price unit** field.</span></span>

## <a name="the-maximum-limit-from-a-purchase-agreement-isnt-effective-on-a-purchase-requisition"></a><span data-ttu-id="06006-165">El límite máximo de un acuerdo de compra no es efectivo en una solicitud de compra.</span><span class="sxs-lookup"><span data-stu-id="06006-165">The maximum limit from a purchase agreement isn't effective on a purchase requisition.</span></span>

### <a name="issue-description"></a><span data-ttu-id="06006-166">Descripción del problema</span><span class="sxs-lookup"><span data-stu-id="06006-166">Issue description</span></span>

<span data-ttu-id="06006-167">Cuando una solicitud de compra está vinculada a un acuerdo de compra, el límite máximo del acuerdo de compra no es efectivo en la solicitud de compra.</span><span class="sxs-lookup"><span data-stu-id="06006-167">When a purchase requisition is linked to a purchase agreement, the maximum limit from the purchase agreement isn't effective on the purchase requisition.</span></span> <span data-ttu-id="06006-168">La información de precio predeterminada se especificó correctamente, pero en la solicitud de compra se puede pedir más del límite máximo del acuerdo de compra.</span><span class="sxs-lookup"><span data-stu-id="06006-168">The default price information is correctly entered, but more than the maximum limit from the purchase agreement can be ordered in the purchase requisition.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="06006-169">Solución del problema</span><span class="sxs-lookup"><span data-stu-id="06006-169">Issue resolution</span></span>

<span data-ttu-id="06006-170">Este comportamiento es esperado.</span><span class="sxs-lookup"><span data-stu-id="06006-170">This behavior is expected.</span></span> <span data-ttu-id="06006-171">Debido a que las solicitudes no siempre se aprueban, no se debe reservar una cantidad o un importe en el acuerdo de compra.</span><span class="sxs-lookup"><span data-stu-id="06006-171">Because requisitions aren't always approved, a quantity or amount should not be reserved on the purchase agreement.</span></span> <span data-ttu-id="06006-172">Por lo tanto, no se alcanzará el límite máximo del acuerdo de compra.</span><span class="sxs-lookup"><span data-stu-id="06006-172">Therefore, you won't meet the maximum limit from the purchase agreement.</span></span>

## <a name="trade-agreements-can-be-created-from-rejected-rfqs-therefore-the-system-doesnt-prevent-trade-agreement-journals-from-being-created-if-the-rfq-line-hasnt-been-accepted"></a><span data-ttu-id="06006-173">Se pueden crear acuerdos comerciales a partir de solicitudes de presupuesto rechazadas.</span><span class="sxs-lookup"><span data-stu-id="06006-173">Trade agreements can be created from rejected RFQs.</span></span> <span data-ttu-id="06006-174">Por lo tanto, el sistema no impide que se creen diarios de acuerdos comerciales si no se ha aceptado la línea de solicitud de presupuesto.</span><span class="sxs-lookup"><span data-stu-id="06006-174">Therefore, the system doesn't prevent trade agreement journals from being created if the RFQ line hasn't been accepted.</span></span>

<span data-ttu-id="06006-175">Puede crear acuerdos comerciales para cualquier respuesta a una solicitud de presupuesto (RFQ), independientemente de si se aceptaron o rechazaron.</span><span class="sxs-lookup"><span data-stu-id="06006-175">You can create trade agreements for any replies for a request for quotation (RFQ), regardless of whether they were accepted or rejected.</span></span> <span data-ttu-id="06006-176">Para obtener más información, consulte [Información general sobre solicitudes de presupuesto (RFQ)](request-quotations.md).</span><span class="sxs-lookup"><span data-stu-id="06006-176">For more information, see [Requests for quotation (RFQs) overview](request-quotations.md).</span></span>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]