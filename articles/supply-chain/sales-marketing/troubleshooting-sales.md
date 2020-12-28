---
title: Solucionar problemas de pedidos de ventas
description: Este tema describe cómo solucionar problemas que pueden surgir al trabajar con pedidos de ventas.
author: SmithaNataraj
manager: tfehr
ms.date: 09/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTable, SalesTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-9-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 6e51723915892f465ce09d09ee9ed622bab9451e
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4436810"
---
# <a name="troubleshoot-sales-orders"></a><span data-ttu-id="c74a4-103">Solucionar problemas de pedidos de ventas</span><span class="sxs-lookup"><span data-stu-id="c74a4-103">Troubleshoot sales orders</span></span>

<span data-ttu-id="c74a4-104">Este tema describe cómo solucionar problemas que pueden surgir al trabajar con pedidos de ventas.</span><span class="sxs-lookup"><span data-stu-id="c74a4-104">This topic describes how to fix issues that you might encounter while you work with sales orders.</span></span>

## <a name="the-tax-information-isnt-updated-if-i-change-the-location-on-a-sales-order-header"></a><span data-ttu-id="c74a4-105">La información fiscal no se actualiza si cambio la ubicación en el encabezado de un pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="c74a4-105">The tax information isn't updated if I change the location on a sales order header.</span></span>

### <a name="issue-description"></a><span data-ttu-id="c74a4-106">Descripción del problema</span><span class="sxs-lookup"><span data-stu-id="c74a4-106">Issue description</span></span>

<span data-ttu-id="c74a4-107">Si se cambia el sitio, el almacén o la dirección de entrega, ya sea en el encabezado de un pedido de ventas o en el nivel de línea, la información fiscal del caso no se actualiza automáticamente en las líneas.</span><span class="sxs-lookup"><span data-stu-id="c74a4-107">If the site, warehouse, or delivery address is changed either on a sales order header or at the line level, the case tax information isn't automatically updated for the lines.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="c74a4-108">Solución del problema</span><span class="sxs-lookup"><span data-stu-id="c74a4-108">Issue resolution</span></span>

<span data-ttu-id="c74a4-109">Este comportamiento se debe al diseño.</span><span class="sxs-lookup"><span data-stu-id="c74a4-109">This behavior is by design.</span></span> <span data-ttu-id="c74a4-110">El problema se produce porque la dirección de entrega, el sitio y el almacén tampoco se cambian automáticamente en las líneas.</span><span class="sxs-lookup"><span data-stu-id="c74a4-110">The issue occurs because the delivery address, site, and warehouse aren't automatically changed at the line level either.</span></span> <span data-ttu-id="c74a4-111">Debe actualizarlos manualmente.</span><span class="sxs-lookup"><span data-stu-id="c74a4-111">You must update them manually.</span></span>

## <a name="if-there-are-two-trade-agreements-for-the-same-period-or-overlapping-periods-the-same-agreement-line-is-always-selected"></a><span data-ttu-id="c74a4-112">Si hay dos acuerdos comerciales para el mismo período o para períodos superpuestos, siempre se selecciona la misma línea de acuerdo.</span><span class="sxs-lookup"><span data-stu-id="c74a4-112">If there are two trade agreements for the same period or overlapping periods, the same agreement line is always selected.</span></span>

### <a name="issue-description"></a><span data-ttu-id="c74a4-113">Descripción del problema</span><span class="sxs-lookup"><span data-stu-id="c74a4-113">Issue description</span></span>

<span data-ttu-id="c74a4-114">Si se definen dos acuerdos comerciales para el mismo período o para períodos superpuestos, parece que se selecciona el mismo acuerdo comercial cada vez que se crean líneas de pedido de ventas que contengan esos artículos.</span><span class="sxs-lookup"><span data-stu-id="c74a4-114">If two trade agreements are defined for the same period or overlapping periods, the same trade agreement seems to be selected every time when you create sales order lines that contain those items.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="c74a4-115">Solución del problema</span><span class="sxs-lookup"><span data-stu-id="c74a4-115">Issue resolution</span></span>

<span data-ttu-id="c74a4-116">Si hay más de un acuerdo comercial para una fecha determinada, siempre se selecciona el acuerdo comercial que tiene el precio más bajo.</span><span class="sxs-lookup"><span data-stu-id="c74a4-116">If there is more than one trade agreement for a given date, the trade agreement that has the lowest price is always selected.</span></span> <span data-ttu-id="c74a4-117">Para obtener más información, descargue las notas del producto siguientes: [Acuerdos comerciales en Microsoft Dynamics AX 2012](https://www.axug.com/HigherLogic/System/DownloadDocumentFile.ashx?DocumentFileKey=3396a3a8-1f48-4d85-8cd6-5fa982f62e90).</span><span class="sxs-lookup"><span data-stu-id="c74a4-117">For more information, download the following white paper: [Trade agreements in Microsoft Dynamics AX 2012](https://www.axug.com/HigherLogic/System/DownloadDocumentFile.ashx?DocumentFileKey=3396a3a8-1f48-4d85-8cd6-5fa982f62e90).</span></span>

## <a name="can-i-link-a-purchase-order-to-a-sales-order-to-fulfill-demand"></a><span data-ttu-id="c74a4-118">¿Puedo vincular un pedido de compra a un pedido de ventas para satisfacer la demanda?</span><span class="sxs-lookup"><span data-stu-id="c74a4-118">Can I link a purchase order to a sales order to fulfill demand?</span></span>

<span data-ttu-id="c74a4-119">Puede crear un pedido de compra desde un pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="c74a4-119">You can create a purchase order from a sales order.</span></span> <span data-ttu-id="c74a4-120">Para obtener más información, consulte [Crear un pedido de compra desde un pedido de ventas](tasks/create-purchase-order-sales-order.md).</span><span class="sxs-lookup"><span data-stu-id="c74a4-120">For more information, see [Create a purchase order from a sales order](tasks/create-purchase-order-sales-order.md).</span></span>

## <a name="i-cant-cancel-or-delete-a-return-order-or-a-sales-order"></a><span data-ttu-id="c74a4-121">No puedo cancelar ni eliminar una orden de devolución o un pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="c74a4-121">I can't cancel or delete a return order or a sales order.</span></span>

<span data-ttu-id="c74a4-122">Puede cancelar solo pedidos de ventas y órdenes de devolución que estén en estado *Creado*.</span><span class="sxs-lookup"><span data-stu-id="c74a4-122">You can cancel only sales orders and return orders that are in a *Created* state.</span></span> <span data-ttu-id="c74a4-123">Para obtener más información, vea [Cancelar una orden de devolución](../service-management/cancel-return-order.md).</span><span class="sxs-lookup"><span data-stu-id="c74a4-123">For more information, see [Cancel a return order](../service-management/cancel-return-order.md).</span></span>

## <a name="when-i-try-to-cancel-a-sales-order-i-receive-a-reservations-cannot-be-removed-because-there-is-work-created-which-relies-on-the-reservations-error"></a><span data-ttu-id="c74a4-124">Cuando intento cancelar un pedido de venta, aparece el error "No se pueden quitar las reservas porque se ha creado un trabajo que depende de ellas".</span><span class="sxs-lookup"><span data-stu-id="c74a4-124">When I try to cancel a sales order, I receive a "Reservations cannot be removed because there is work created which relies on the reservations" error.</span></span>

<span data-ttu-id="c74a4-125">Si el trabajo está asociado con un pedido de venta, no puede cancelar el pedido de venta hasta que el trabajo se cancele y se revierta.</span><span class="sxs-lookup"><span data-stu-id="c74a4-125">If work is associated with a sales order, you can't cancel the sales order until the work is canceled and reversed.</span></span> <span data-ttu-id="c74a4-126">Este requisito se aplica incluso si el trabajo asociado con el pedido de ventas está cerrado.</span><span class="sxs-lookup"><span data-stu-id="c74a4-126">This requirement applies even if the work that is associated with the sales order is closed.</span></span>

<span data-ttu-id="c74a4-127">Para arreglar este problema, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="c74a4-127">To fix this issue, follow these steps.</span></span>

1. <span data-ttu-id="c74a4-128">Cancele el trabajo y vuelva a colocar el inventario en la ubicación deseada.</span><span class="sxs-lookup"><span data-stu-id="c74a4-128">Cancel the work, and put inventory back into the desired location.</span></span> <span data-ttu-id="c74a4-129">Vaya a la carga relevante del pedido de ventas y seleccione **Reducir cantidad seleccionada** en la línea de carga o **Invertir el trabajo** en el panel de acciones.</span><span class="sxs-lookup"><span data-stu-id="c74a4-129">Go to the relevant load of the sales order, and select either **Reduce picked quantity** on the load line or **Reverse work** on the Action Pane.</span></span>

    <span data-ttu-id="c74a4-130">Ahora el trabajo tiene el estado *Cancelado* y se crea y procesa automáticamente un nuevo trabajo de movimiento de inventario para volver a colocar el inventario en la ubicación que se describió en el momento de la reversión.</span><span class="sxs-lookup"><span data-stu-id="c74a4-130">The work now has a status of *Canceled*, and new inventory movement work is automatically created and processed to put inventory back into the location that was described at the time of reversal.</span></span>

2. <span data-ttu-id="c74a4-131">Elimina la carga.</span><span class="sxs-lookup"><span data-stu-id="c74a4-131">Delete the load.</span></span> <span data-ttu-id="c74a4-132">También se elimina el envío.</span><span class="sxs-lookup"><span data-stu-id="c74a4-132">The shipment is also deleted.</span></span>
3. <span data-ttu-id="c74a4-133">Ahora debería poder ir al pedido de ventas y cancelarlo.</span><span class="sxs-lookup"><span data-stu-id="c74a4-133">You should now be able to go to the sales order and cancel it.</span></span>

## <a name="i-cant-cancel-an-intercompany-purchase-order-that-is-linked-to-a-sales-order"></a><span data-ttu-id="c74a4-134">No puedo cancelar un pedido de compra de empresas vinculadas que está vinculado a un pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="c74a4-134">I can't cancel an intercompany purchase order that is linked to a sales order.</span></span>

### <a name="issue-description"></a><span data-ttu-id="c74a4-135">Descripción del problema</span><span class="sxs-lookup"><span data-stu-id="c74a4-135">Issue description</span></span>

<span data-ttu-id="c74a4-136">Si intenta cancelar un pedido de compra de empresas vinculadas que esté vinculado a un pedido de ventas, es posible que aparezca el siguiente mensaje de error: "La cantidad no se puede reducir porque la cantidad de actualización restante cambia de signo".</span><span class="sxs-lookup"><span data-stu-id="c74a4-136">If you try to cancel an intercompany purchase order that is linked to a sales order, you might receive the following error message: "Quantity cannot be reduced because the remaining update quantity changes sign."</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="c74a4-137">Solución del problema</span><span class="sxs-lookup"><span data-stu-id="c74a4-137">Issue resolution</span></span>

<span data-ttu-id="c74a4-138">Este problema se corrigió en Microsoft Dynamics 365 Supply Chain Management versión 10.0.13.</span><span class="sxs-lookup"><span data-stu-id="c74a4-138">This issue was fixed in Microsoft Dynamics 365 Supply Chain Management version 10.0.13.</span></span> <span data-ttu-id="c74a4-139">Desde esa versión y las versiones posteriores podrá cancelar un pedido de compra de empresas vinculadas que esté vinculado a un pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="c74a4-139">In that version and later versions, you can now cancel an intercompany purchase order that is linked to a sales order.</span></span>

## <a name="can-i-restore-an-invoiced-sales-order-that-was-deleted"></a><span data-ttu-id="c74a4-140">¿Puedo restaurar un pedido de ventas facturado que se eliminó?</span><span class="sxs-lookup"><span data-stu-id="c74a4-140">Can I restore an invoiced sales order that was deleted?</span></span>

### <a name="issue-description"></a><span data-ttu-id="c74a4-141">Descripción del problema</span><span class="sxs-lookup"><span data-stu-id="c74a4-141">Issue description</span></span>

<span data-ttu-id="c74a4-142">Un pedido de ventas facturado se eliminó por error y desea restaurarlo o ver sus detalles.</span><span class="sxs-lookup"><span data-stu-id="c74a4-142">An invoiced sales order was deleted by mistake, and you want to restore it or view its details.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="c74a4-143">Solución del problema</span><span class="sxs-lookup"><span data-stu-id="c74a4-143">Issue resolution</span></span>

<span data-ttu-id="c74a4-144">Si el pedido de ventas eliminado ya se ha facturado, vaya a **Cuenta de cliente \> Transacciones \> Documento original \> Ver detalles**.</span><span class="sxs-lookup"><span data-stu-id="c74a4-144">If the deleted sales order has already been invoiced, go to **Customer account \> Transactions \> Original document \> View details**.</span></span> <span data-ttu-id="c74a4-145">Busque la factura que necesita y selecciónela para ver sus detalles.</span><span class="sxs-lookup"><span data-stu-id="c74a4-145">Find the invoice that you're looking for, and select it to view its details.</span></span> <span data-ttu-id="c74a4-146">Estos detalles incluyen la referencia del pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="c74a4-146">These details include the sales order reference.</span></span> <span data-ttu-id="c74a4-147">También debería poder acceder a los detalles del pedido de ventas desde esa página.</span><span class="sxs-lookup"><span data-stu-id="c74a4-147">You should also be able to access the sales order details from that page.</span></span>

## <a name="the-deadline-of-a-sales-order-header-cant-be-found-in-the-salesorderheaderv2entity-data-entity"></a><span data-ttu-id="c74a4-148">No se encuentra la fecha límite de un encabezado de pedido de ventas en la entidad de datos SalesOrderHeaderV2Entity.</span><span class="sxs-lookup"><span data-stu-id="c74a4-148">The deadline of a sales order header can't be found in the SalesOrderHeaderV2Entity data entity.</span></span>

<span data-ttu-id="c74a4-149">El campo de fecha límite no existe en la entidad *SalesOrderHeaderV2Entity*.</span><span class="sxs-lookup"><span data-stu-id="c74a4-149">The deadline field doesn't exist on the *SalesOrderHeaderV2Entity* entity.</span></span>

## <a name="i-must-delete-orphaned-sales-order-records"></a><span data-ttu-id="c74a4-150">Debo eliminar los registros de pedido de ventas huérfanos.</span><span class="sxs-lookup"><span data-stu-id="c74a4-150">I must delete orphaned sales order records.</span></span>

<span data-ttu-id="c74a4-151">Para limpiar los registros de pedido de ventas huérfanos, ejecute el trabajo periódico *Eliminación de pedido de ventas* desde alguno de los lugares siguientes:</span><span class="sxs-lookup"><span data-stu-id="c74a4-151">To clean up orphaned sales order records, run the *Sales order deletion* periodic job by going to either of the following places:</span></span>

- <span data-ttu-id="c74a4-152">Ventas y marketing \> Tareas periódicas \> Limpiar \> Eliminar pedidos de ventas</span><span class="sxs-lookup"><span data-stu-id="c74a4-152">Sales and marketing \> Periodic tasks \> Clean up \> Delete sales orders</span></span>
- <span data-ttu-id="c74a4-153">Venta minorista y comercio \> TI de Retail y Commerce \> Limpiar \> Eliminar pedidos de ventas</span><span class="sxs-lookup"><span data-stu-id="c74a4-153">Retail and commerce \> Retail and commerce IT \> Clean up \> Delete sales orders</span></span>

## <a name="is-there-a-way-to-calculate-commissions-on-invoices-that-have-already-been-posted"></a><span data-ttu-id="c74a4-154">¿Existe alguna forma de calcular las comisiones de las facturas que ya se han contabilizado?</span><span class="sxs-lookup"><span data-stu-id="c74a4-154">Is there a way to calculate commissions on invoices that have already been posted?</span></span>

<span data-ttu-id="c74a4-155">Actualmente Supply Chain Management no admite el cálculo de comisiones para facturas contabilizadas.</span><span class="sxs-lookup"><span data-stu-id="c74a4-155">Supply Chain Management doesn't currently support the calculation of commissions for posted invoices.</span></span>

## <a name="a-bundle-item-isnt-supported-in-an-intercompany-process"></a><span data-ttu-id="c74a4-156">Un proceso de empresas vinculadas no admite artículos de agrupación.</span><span class="sxs-lookup"><span data-stu-id="c74a4-156">A bundle item isn't supported in an intercompany process.</span></span>

<span data-ttu-id="c74a4-157">El artículo de agrupación no está disponible para el pedido de compra porque, si examina las líneas del pedido de ventas del artículo de la agrupación, notará que la cantidad es *0* (cero) y el estado es *Cancelado*.</span><span class="sxs-lookup"><span data-stu-id="c74a4-157">The bundle item isn't available for the purchase order because, if you examine the sales order lines for the bundle item, you will notice that the quantity is *0* (zero) and the status is *Cancelled*.</span></span> <span data-ttu-id="c74a4-158">Este comportamiento se debe al diseño.</span><span class="sxs-lookup"><span data-stu-id="c74a4-158">This behavior is by design.</span></span> <span data-ttu-id="c74a4-159">El pedido de cliente compra solo los componentes del artículo de agrupación.</span><span class="sxs-lookup"><span data-stu-id="c74a4-159">The sales order buys only the components of the bundle item.</span></span> <span data-ttu-id="c74a4-160">No compra el artículo de agrupación en sí.</span><span class="sxs-lookup"><span data-stu-id="c74a4-160">It doesn't buy the bundle item itself.</span></span>

<span data-ttu-id="c74a4-161">Si tiene que comprar una agrupación, considere si debe marcarlo como artículo de agrupación, ya que esta funcionalidad está diseñada para escenarios de reconocimiento de ingresos.</span><span class="sxs-lookup"><span data-stu-id="c74a4-161">If you must buy a bundle, consider whether you have to mark it as bundle item, because this functionality is actually designed for revenue recognition scenarios.</span></span> <span data-ttu-id="c74a4-162">Para obtener más información acerca de los artículos de agrupación, consulte [Agrupaciones](../../finance/accounts-receivable/revenue-recognition-setup.md#bundles).</span><span class="sxs-lookup"><span data-stu-id="c74a4-162">For more information about bundle items, see [Bundles](../../finance/accounts-receivable/revenue-recognition-setup.md#bundles).</span></span>
