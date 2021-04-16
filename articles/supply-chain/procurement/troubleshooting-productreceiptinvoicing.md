---
title: Solución de problemas de recepción y facturación de productos
description: Este tema describe cómo solucionar problemas que pueden surgir al trabajar con recepción y facturación de productos.
author: SmithaNataraj
ms.date: 09/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-9-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 3522a024261ff6dfffb53f2101139460be7669e4
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5832019"
---
# <a name="troubleshoot-product-receipts-and-invoicing"></a><span data-ttu-id="9f075-103">Solución de problemas de recepción y facturación de productos</span><span class="sxs-lookup"><span data-stu-id="9f075-103">Troubleshoot product receipts and invoicing</span></span>

<span data-ttu-id="9f075-104">Este tema describe cómo solucionar problemas que pueden surgir al trabajar con recepción y facturación de productos.</span><span class="sxs-lookup"><span data-stu-id="9f075-104">This topic describes how to fix issues that you might encounter while you work with product receipts and invoicing.</span></span>

## <a name="i-cant-post-more-than-one-invoice-for-a-purchase-order-line-that-has-category-based-items"></a><span data-ttu-id="9f075-105">No puedo registrar más de una factura para una línea de pedido de compra que tiene artículos basados en categorías.</span><span class="sxs-lookup"><span data-stu-id="9f075-105">I can't post more than one invoice for a purchase order line that has category-based items.</span></span>

<span data-ttu-id="9f075-106">Es obligatorio especificar una cantidad si desea contabilizar facturas.</span><span class="sxs-lookup"><span data-stu-id="9f075-106">A quantity is mandatory if you want to post invoices.</span></span> <span data-ttu-id="9f075-107">Por lo tanto, si la cantidad total de una línea se ha facturado solo por un importe parcial, no podrá facturar el importe restante en otra factura.</span><span class="sxs-lookup"><span data-stu-id="9f075-107">Therefore, if the full quantity of a line has been invoiced for only a partial amount, you won't be able to invoice the remaining amount on another invoice.</span></span>

## <a name="i-receive-an-object-reference-not-set-error-during-purchase-order-confirmation-or-an-exception-has-been-thrown-by-the-target-of-an-invocation-exception-occurs-during-vendor-invoice-posting"></a><span data-ttu-id="9f075-108">Recibo un error de "Referencia de objeto no establecida" durante la confirmación de un pedido de compra, o se produce una excepción "El destino de una invocación ha generado una excepción" durante la contabilización de la factura del proveedor.</span><span class="sxs-lookup"><span data-stu-id="9f075-108">I receive an "Object reference not set" error during purchase order confirmation, or an "Exception has been thrown by the target of an invocation" exception occurs during vendor invoice posting.</span></span>

<span data-ttu-id="9f075-109">Este problema se puede producir debido a incoherencias en las distribuciones de pedidos de compra.</span><span class="sxs-lookup"><span data-stu-id="9f075-109">This issue can occur because of inconsistency in purchase order distributions.</span></span>

<span data-ttu-id="9f075-110">Para desbloquear este problema y restablecer el pedido de compra al estado *Borrador*, vaya a **Adquisiciones y abastecimiento \> Tareas periódicas \> Limpiar \> Restablecimiento de distribución de pedido de compra**.</span><span class="sxs-lookup"><span data-stu-id="9f075-110">To unblock this issue and reset the purchase order to a *Draft* state, go to **Procurement and sourcing \> Periodic tasks \> Clean up \> Purchase order distribution reset**.</span></span> <span data-ttu-id="9f075-111">Para obtener más información, consulte la siguiente publicación de blog: [Resolver errores de distribución de pedidos de compra en Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).</span><span class="sxs-lookup"><span data-stu-id="9f075-111">For more information, see the following blog post: [Resolve PO distribution errors in Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).</span></span>

## <a name="i-cant-consolidate-multiple-product-receipts-into-a-single-purchase-order"></a><span data-ttu-id="9f075-112">No puedo consolidar varias recepciones de productos en un solo pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="9f075-112">I can't consolidate multiple product receipts into a single purchase order.</span></span>

<span data-ttu-id="9f075-113">No puede consolidar múltiples recepciones de productos en un solo pedido de compra si las diferentes líneas de recepciones de productos tienen fechas contables distintas.</span><span class="sxs-lookup"><span data-stu-id="9f075-113">You can't consolidate multiple product receipts into a single purchase order if the different product receipt lines have different accounting dates.</span></span>

<span data-ttu-id="9f075-114">En versiones anteriores de Microsoft Dynamics 365 Supply Chain Management se permitía la consolidación en esta situación.</span><span class="sxs-lookup"><span data-stu-id="9f075-114">In earlier versions of Microsoft Dynamics 365 Supply Chain Management, consolidation was allowed in this situation.</span></span> <span data-ttu-id="9f075-115">Sin embargo, esta práctica es propensa a errores.</span><span class="sxs-lookup"><span data-stu-id="9f075-115">However, the practice is prone to error.</span></span> <span data-ttu-id="9f075-116">La fecha contable en las líneas de pedido de compra que se crean no debe diferir de la fecha contable en las líneas de recepción de productos a partir de las cuales se crearon esas líneas de pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="9f075-116">The accounting date on the purchase order lines that are created should not differ from the accounting date on the product receipt lines that those purchase order lines were created from.</span></span> <span data-ttu-id="9f075-117">(La fecha contable en las líneas del pedido de compra coincide con la fecha contable en el encabezado del pedido de compra). Por lo tanto, ya no se permite la consolidación de múltiples recepciones de productos en un solo pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="9f075-117">(The accounting date on the purchase order lines matches the accounting date on the purchase order header.) Therefore, the consolidation of multiple product receipts into a single purchase orders is no longer allowed.</span></span>

<span data-ttu-id="9f075-118">La fecha contable se usa, por ejemplo, para reservas presupuestarias y reserva de gasto.</span><span class="sxs-lookup"><span data-stu-id="9f075-118">The accounting date is used, for example, for budget reservations and encumbrance.</span></span> <span data-ttu-id="9f075-119">Por lo tanto, debe conservarse durante la transición de la recepción del producto al pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="9f075-119">Therefore, it should be kept during the transition from product receipt to purchase order.</span></span>

## <a name="when-product-receipts-are-canceled-transactions-can-be-posted-to-a-suspended-ledger-account"></a><span data-ttu-id="9f075-120">Cuando se cancelan las recepciones de productos, las transacciones se pueden registrar en una cuenta contable suspendida.</span><span class="sxs-lookup"><span data-stu-id="9f075-120">When product receipts are canceled, transactions can be posted to a suspended ledger account.</span></span>

### <a name="issue-description"></a><span data-ttu-id="9f075-121">Descripción del problema</span><span class="sxs-lookup"><span data-stu-id="9f075-121">Issue description</span></span>

<span data-ttu-id="9f075-122">Si se cancela la recepción de un producto, el sistema permite que las transacciones se registren en cuentas contables suspendidas, aunque las cuentas principales estén suspendidas.</span><span class="sxs-lookup"><span data-stu-id="9f075-122">If a product receipt is canceled, the system allows transactions to be posted to suspended ledger accounts, even though the main accounts are suspended.</span></span>

### <a name="reproduce-the-issue"></a><span data-ttu-id="9f075-123">Reproducir el problema</span><span class="sxs-lookup"><span data-stu-id="9f075-123">Reproduce the issue</span></span>

<span data-ttu-id="9f075-124">El siguiente procedimiento muestra una manera de reproducir el problema.</span><span class="sxs-lookup"><span data-stu-id="9f075-124">The following procedure shows one way to reproduce the issue.</span></span>

1. <span data-ttu-id="9f075-125">En la página **Parámetros de proveedores**, en la pestaña **General**, asegúrese de que la opción **Registrar recepción de producto en el libro mayor** está establecida en *Sí*.</span><span class="sxs-lookup"><span data-stu-id="9f075-125">On the **Accounts payable parameters** page, on the **General** tab, make sure that the **Post product receipt in ledger** option is set to *Yes*.</span></span>
1. <span data-ttu-id="9f075-126">Cree un pedido de compra y agregue una línea de pedido que tenga como cantidad *1000* para un producto.</span><span class="sxs-lookup"><span data-stu-id="9f075-126">Create a purchase order, and add an order line that has a quantity of *1,000* for a product.</span></span>
1. <span data-ttu-id="9f075-127">Confirme el pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="9f075-127">Confirm the purchase order.</span></span>
1. <span data-ttu-id="9f075-128">Registre la recepción del producto y compruebe los asientos.</span><span class="sxs-lookup"><span data-stu-id="9f075-128">Post the product receipt, and check the vouchers.</span></span>
1. <span data-ttu-id="9f075-129">Suspenda las cuentas principales relevantes, *200140* y *140200*.</span><span class="sxs-lookup"><span data-stu-id="9f075-129">Suspend the relevant main accounts, *200140* and *140200*.</span></span>
1. <span data-ttu-id="9f075-130">Cancele la recepción de producto registrada.</span><span class="sxs-lookup"><span data-stu-id="9f075-130">Cancel the posted product receipt.</span></span>
1. <span data-ttu-id="9f075-131">Tenga en cuenta que las transacciones se pueden registrar en las cuentas de libro mayor suspendidas.</span><span class="sxs-lookup"><span data-stu-id="9f075-131">Notice that transactions can be posted to the suspended leger accounts.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="9f075-132">Solución del problema</span><span class="sxs-lookup"><span data-stu-id="9f075-132">Issue resolution</span></span>

<span data-ttu-id="9f075-133">Las transacciones se pueden contabilizar en las cuentas de libro mayor suspendidas cuando se cancelan recepciones de productos, ya que este comportamiento permite contabilizaciones correctas.</span><span class="sxs-lookup"><span data-stu-id="9f075-133">Transactions can be posted to the suspended leger accounts when product receipts are canceled, because this behavior allows for correct postings.</span></span>

## <a name="a-product-receipt-voucher-number-is-consumed-even-if-no-financial-voucher-is-generated-during-product-receipt"></a><span data-ttu-id="9f075-134">Se consume un número de asiento de recepción de producto incluso si no se genera ningún comprobante financiero durante la recepción del producto.</span><span class="sxs-lookup"><span data-stu-id="9f075-134">A product receipt voucher number is consumed even if no financial voucher is generated during product receipt.</span></span>

<span data-ttu-id="9f075-135">Si la opción **Acumular pasivo en la recepción del producto** está establecida en *No* para el grupo de modelos de artículo, no se producirán contabilizaciones en el libro mayor.</span><span class="sxs-lookup"><span data-stu-id="9f075-135">If the **Accrue liability on product receipt** option is set to *No* for the item model group, no postings to the general ledger will occur.</span></span> <span data-ttu-id="9f075-136">Sin embargo, se registrará un evento físico con el propósito de contabilizarlo en un libro mayor auxiliar y ese evento requiere un número de asiento.</span><span class="sxs-lookup"><span data-stu-id="9f075-136">However, a physical event will be recorded for the purpose of accounting in a subledger, and that event requires a voucher number.</span></span> <span data-ttu-id="9f075-137">Este número de asiento es el número al que se hace referencia en las transacciones de inventario.</span><span class="sxs-lookup"><span data-stu-id="9f075-137">This voucher number is the voucher number that is referenced in the inventory transactions.</span></span>

<span data-ttu-id="9f075-138">Le recomendamos que establezca la opción **Acumular pasivo en la recepción del producto** en *Sí*, como se describe en la siguiente publicación del blog: [Contabilizar cargos varios en la recepción del producto](https://cloudblogs.microsoft.com/dynamics365/no-audience/2014/11/11/post-misc-charges-at-time-of-product-receipt/).</span><span class="sxs-lookup"><span data-stu-id="9f075-138">We recommend that you set the **Accrue liability on product receipt** option to *Yes*, as described in the following blog post: [Post Misc. charges at time of product receipt](https://cloudblogs.microsoft.com/dynamics365/no-audience/2014/11/11/post-misc-charges-at-time-of-product-receipt/).</span></span>

## <a name="the-post-to-charge-account-in-ledger-setting-isnt-turned-on"></a><span data-ttu-id="9f075-139">La opción Registrar en la cuenta de gastos del libro mayor no está activada.</span><span class="sxs-lookup"><span data-stu-id="9f075-139">The Post to charge account in ledger setting isn't turned on.</span></span>

### <a name="issue-description"></a><span data-ttu-id="9f075-140">Descripción del problema</span><span class="sxs-lookup"><span data-stu-id="9f075-140">Issue description</span></span>

<span data-ttu-id="9f075-141">Este problema se produce cuando se factura un pedido de compra, si la opción **Registrar en la cuenta de gastos del libro mayor** está establecida en *Sí* en la pestaña **Factura** de la página **Parámetros de proveedores**.</span><span class="sxs-lookup"><span data-stu-id="9f075-141">This issue occurs when a purchase order is invoiced, if the **Post to charge account in ledger** option is set to *Yes* on the **Invoice** tab of the **Accounts payable parameters** page.</span></span>

### <a name="reproduce-the-issue"></a><span data-ttu-id="9f075-142">Reproducir el problema</span><span class="sxs-lookup"><span data-stu-id="9f075-142">Reproduce the issue</span></span>

<span data-ttu-id="9f075-143">El siguiente procedimiento muestra una manera de reproducir el problema.</span><span class="sxs-lookup"><span data-stu-id="9f075-143">The following procedure shows one way to reproduce the issue.</span></span>

1. <span data-ttu-id="9f075-144">Vaya a **Proveedores \> Configuración \> Parámetros de proveedores**.</span><span class="sxs-lookup"><span data-stu-id="9f075-144">Go to **Accounts payable \> Setup \> Accounts payable parameters**.</span></span>
1. <span data-ttu-id="9f075-145">En la pestaña **Factura**, establezca la opción **Registrar en la cuenta de gastos del libro mayor** en *Sí*.</span><span class="sxs-lookup"><span data-stu-id="9f075-145">On the **Invoice** tab, set the **Post to charge account in ledger** option to *Yes*.</span></span>
1. <span data-ttu-id="9f075-146">Vaya a **Gestión de inventarios \> Preparar \> Registro \> Registro**.</span><span class="sxs-lookup"><span data-stu-id="9f075-146">Go to **Inventory management \> Setup \> Posting \> Posting**.</span></span>
1. <span data-ttu-id="9f075-147">En la pestaña **Pedido de compra**, asegúrese de haber eliminado todas las líneas del gasto de compra del producto.</span><span class="sxs-lookup"><span data-stu-id="9f075-147">On the **Purchase order** tab, make sure that you've deleted all the lines in the purchase expenditure for the product.</span></span>
1. <span data-ttu-id="9f075-148">Vaya a **Proveedores \> Pedidos de compra \> Todos los pedidos de compra**.</span><span class="sxs-lookup"><span data-stu-id="9f075-148">Go to **Accounts payable \> Purchase orders \> All purchase orders**.</span></span>
1. <span data-ttu-id="9f075-149">Cree un pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="9f075-149">Create a purchase order.</span></span> <span data-ttu-id="9f075-150">En el campo **Cuenta del proveedor**, seleccione *1001 Suministros de oficina Acme*.</span><span class="sxs-lookup"><span data-stu-id="9f075-150">In the **Vendor account** field, select *1001 Acme Office Supplies*.</span></span>
1. <span data-ttu-id="9f075-151">Agregue una línea de pedido con la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="9f075-151">Add a purchase order line that has the following settings:</span></span>

    - <span data-ttu-id="9f075-152">**Número de artículo:** *Proyector láser D0011*</span><span class="sxs-lookup"><span data-stu-id="9f075-152">**Item number:** *D0011 Laser Projector*</span></span>
    - <span data-ttu-id="9f075-153">**Sitio**: *1*</span><span class="sxs-lookup"><span data-stu-id="9f075-153">**Site:** *1*</span></span>
    - <span data-ttu-id="9f075-154">**Almacén**: *11*</span><span class="sxs-lookup"><span data-stu-id="9f075-154">**Warehouse:** *11*</span></span>
    - <span data-ttu-id="9f075-155">**Cantidad:** *4*</span><span class="sxs-lookup"><span data-stu-id="9f075-155">**Quantity:** *4*</span></span>

1. <span data-ttu-id="9f075-156">En el panel de acciones, en la ficha **Compra**, en el grupo **Acción**, seleccione **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="9f075-156">On the Action Pane, on the **Purchase** tab, in the **Action** group, select **Confirm**.</span></span>
1. <span data-ttu-id="9f075-157">En el panel Acciones, en la pestaña **Recepción** del grupo **Generar**, seleccione **Recepción de producto**.</span><span class="sxs-lookup"><span data-stu-id="9f075-157">On the Action Pane, on the **Receive** tab, in the **Generate** group, select **Product receipt**.</span></span>
1. <span data-ttu-id="9f075-158">En el cuadro de diálogo **Registro de recepción de productos**, en el campo **Recepción de producto**, escriba un número arbitrario y seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9f075-158">In the **Posting product receipt** dialog box, in the **Product receipt** field, enter an arbitrary number, and then select **OK**.</span></span>
1. <span data-ttu-id="9f075-159">En el panel de acciones, en la ficha **Factura**, en el grupo **Generar**, seleccione **Factura**.</span><span class="sxs-lookup"><span data-stu-id="9f075-159">On the Action Pane, on the **Invoice** tab, in the **Generate** group, select **Invoice**.</span></span>
1. <span data-ttu-id="9f075-160">En el campo **Número**, escriba un número arbitrario como número de factura.</span><span class="sxs-lookup"><span data-stu-id="9f075-160">In the **Number** field, enter an arbitrary number as the invoice number.</span></span>
1. <span data-ttu-id="9f075-161">Actualice el estado de conciliación y registre.</span><span class="sxs-lookup"><span data-stu-id="9f075-161">Update the match status, and post.</span></span>
1. <span data-ttu-id="9f075-162">Observe que ahora aparece el siguiente error al generar una factura de un pedido de compra: "Número de cuenta para el tipo de transacción: No existe el gasto de compra del producto".</span><span class="sxs-lookup"><span data-stu-id="9f075-162">Notice that you now receive the following error when you generate an invoice from a purchase order: "Account number for transaction type Purchase expenditure for product does not exist."</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="9f075-163">Solución del problema</span><span class="sxs-lookup"><span data-stu-id="9f075-163">Issue resolution</span></span>

<span data-ttu-id="9f075-164">Depende de la configuración de parámetros para facturas y grupos de facturas.</span><span class="sxs-lookup"><span data-stu-id="9f075-164">This depends on the parameter settings for invoices and invoice groups.</span></span> <span data-ttu-id="9f075-165">Para obtener más información, vea la siguiente publicación de blog: [Contabilización del cargo de compra y variación de existencias](https://cloudblogs.microsoft.com/dynamics365/no-audience/2014/12/15/accounting-for-purchase-charge-and-stock-variation/).</span><span class="sxs-lookup"><span data-stu-id="9f075-165">For more information, see the following blog post: [Accounting for Purchase charge and Stock variation](https://cloudblogs.microsoft.com/dynamics365/no-audience/2014/12/15/accounting-for-purchase-charge-and-stock-variation/).</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]