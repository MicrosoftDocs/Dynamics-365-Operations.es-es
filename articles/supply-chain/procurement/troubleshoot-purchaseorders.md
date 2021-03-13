---
title: Solución de problemas de pedidos de compra
description: Este tema describe cómo solucionar problemas que pueden surgir al trabajar con pedidos de compra.
author: SmithaNataraj
manager: tfehr
ms.date: 09/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
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
ms.openlocfilehash: 7b65c23fc7ac04fc30c0001bee9541a475026018
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "5007500"
---
# <a name="troubleshoot-purchase-orders"></a><span data-ttu-id="f95b5-103">Solución de problemas de pedidos de compra</span><span class="sxs-lookup"><span data-stu-id="f95b5-103">Troubleshoot purchase orders</span></span>

<span data-ttu-id="f95b5-104">Este tema describe cómo solucionar problemas que pueden surgir al trabajar con pedidos de compra.</span><span class="sxs-lookup"><span data-stu-id="f95b5-104">This topic describes how to fix issues that you might encounter while you work with purchase orders.</span></span>

## <a name="an-action-can-be-completed-only-after-the-line-number-is-fully-distributed"></a><span data-ttu-id="f95b5-105">Una acción solo se puede completar después de que el número de línea esté completamente distribuido.</span><span class="sxs-lookup"><span data-stu-id="f95b5-105">An action can be completed only after the line number is fully distributed.</span></span>

<span data-ttu-id="f95b5-106">Este problema se puede producir debido a incoherencias en las distribuciones de pedidos de compra.</span><span class="sxs-lookup"><span data-stu-id="f95b5-106">This issue can occur because of inconsistency in purchase order distributions.</span></span>

<span data-ttu-id="f95b5-107">Para desbloquear este problema y restablecer el pedido de compra al estado *Borrador*, vaya a **Adquisiciones y abastecimiento \> Tareas periódicas \> Limpiar \> Restablecimiento de distribución de pedido de compra**.</span><span class="sxs-lookup"><span data-stu-id="f95b5-107">To unblock this issue and reset the purchase order to a *Draft* state, go to **Procurement and sourcing \> Periodic tasks \> Clean up \> Purchase order distribution reset**.</span></span> <span data-ttu-id="f95b5-108">Para obtener más información, consulte la siguiente publicación de blog: [Resolver errores de distribución de pedidos de compra en Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).</span><span class="sxs-lookup"><span data-stu-id="f95b5-108">For more information, see the following blog post: [Resolve PO distribution errors in Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).</span></span>

## <a name="when-purchase-orders-are-imported-through-data-management-purchase-order-line-numbers-dont-follow-the-increment-that-defined-in-system-parameters"></a><span data-ttu-id="f95b5-109">Cuando los pedidos de compra se importan a través de la administración de datos, los números de línea del pedido de compra no siguen el incremento definido en los parámetros del sistema.</span><span class="sxs-lookup"><span data-stu-id="f95b5-109">When purchase orders are imported through data management, purchase order line numbers don't follow the increment that defined in system parameters.</span></span>

### <a name="issue-description"></a><span data-ttu-id="f95b5-110">Descripción del problema</span><span class="sxs-lookup"><span data-stu-id="f95b5-110">Issue description</span></span>

<span data-ttu-id="f95b5-111">De forma predeterminada, los números de línea generados automáticamente para las líneas de pedido de compra que se importan a través de la entidad de datos *Líneas de pedido de compra V2* no usan el incremento de número de línea del sistema que se especifica en los parámetros del sistema.</span><span class="sxs-lookup"><span data-stu-id="f95b5-111">By default, automatically generated line numbers for purchase order lines that are imported through the *Purchase order lines V2* data entity don't use the system line number increment that is specified in system parameters.</span></span> <span data-ttu-id="f95b5-112">Si crea manualmente un pedido de compra y agrega líneas a través de la interfaz de usuario, los números de línea se incrementan correctamente.</span><span class="sxs-lookup"><span data-stu-id="f95b5-112">If you manually create a purchase order and add lines through the user interface (UI), the line numbers are incremented correctly.</span></span> <span data-ttu-id="f95b5-113">Sin embargo, si usa el marco de administración de datos (DMF), no se incrementan correctamente.</span><span class="sxs-lookup"><span data-stu-id="f95b5-113">However, if you use the Data management framework (DMF), they aren't incremented correctly.</span></span>

<span data-ttu-id="f95b5-114">Este problema se produce porque, cuando importa líneas a través de DMF, si los números de línea aún no están asignados en la entidad importada, el sistema usa el método de DMF para asignarlos.</span><span class="sxs-lookup"><span data-stu-id="f95b5-114">This issue occurs because, when you import lines via DMF, if line numbers aren't already assigned in the imported entity, the system uses DMF's method for assigning them.</span></span> <span data-ttu-id="f95b5-115">Ese método siempre incrementa los números de línea en una unidad.</span><span class="sxs-lookup"><span data-stu-id="f95b5-115">That method always increments line numbers by one.</span></span>

### <a name="issue-workaround"></a><span data-ttu-id="f95b5-116">Solución del problema</span><span class="sxs-lookup"><span data-stu-id="f95b5-116">Issue workaround</span></span>

<span data-ttu-id="f95b5-117">Asegúrese de que los números de línea deseados ya estén incluidos en los campos de número de línea de la entidad de datos cuando importe las líneas del pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="f95b5-117">Make sure that the desired line numbers are already given in the data entity line number fields when you import the purchase order lines.</span></span> <span data-ttu-id="f95b5-118">En este caso, DMF no sobrescribirá los números de línea.</span><span class="sxs-lookup"><span data-stu-id="f95b5-118">In this case, DMF won't overwrite the line numbers.</span></span>

## <a name="a-default-tax-group-and-a-default-cash-discount-arent-filled-in-from-the-invoice-account"></a><span data-ttu-id="f95b5-119">Un grupo de impuestos predeterminado y un descuento por pronto pago predeterminado no se rellenan desde la cuenta de factura.</span><span class="sxs-lookup"><span data-stu-id="f95b5-119">A default tax group and a default cash discount aren't filled in from the invoice account.</span></span>

<span data-ttu-id="f95b5-120">Si utiliza una cuenta de factura que difiere de la cuenta de cliente, un grupo de impuestos predeterminado y un descuento por pronto pago predeterminado no se rellenarán desde la cuenta de factura cuando se cree un pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="f95b5-120">If you're using an invoice account that differs from the customer account, a default tax group and a default cash discount aren't filled in from the invoice account when a purchase order is created.</span></span>

<span data-ttu-id="f95b5-121">Este comportamiento se debe al diseño.</span><span class="sxs-lookup"><span data-stu-id="f95b5-121">This behavior is by design.</span></span> <span data-ttu-id="f95b5-122">Los valores predeterminados para el grupo de impuestos, descuentos por pronto pago y otra información de precios se basan en la cuenta del cliente, no en la cuenta de la factura.</span><span class="sxs-lookup"><span data-stu-id="f95b5-122">The default values for the tax group, cash discounts, and other price information are based on the customer account, not the invoice account.</span></span>

## <a name="i-receive-an-object-reference-not-set-error-during-purchase-order-confirmation-or-an-exception-has-been-thrown-by-the-target-of-an-invocation-exception-occurs-during-vendor-invoice-posting"></a><span data-ttu-id="f95b5-123">Recibo un error de "Referencia de objeto no establecida" durante la confirmación de un pedido de compra, o se produce una excepción "El destino de una invocación ha generado una excepción" durante la contabilización de la factura del proveedor.</span><span class="sxs-lookup"><span data-stu-id="f95b5-123">I receive an "Object reference not set" error during purchase order confirmation, or an "Exception has been thrown by the target of an invocation" exception occurs during vendor invoice posting.</span></span>

<span data-ttu-id="f95b5-124">Este problema se puede producir debido a incoherencias en las distribuciones de pedidos de compra.</span><span class="sxs-lookup"><span data-stu-id="f95b5-124">This issue can occur because of inconsistency in purchase order distributions.</span></span>

<span data-ttu-id="f95b5-125">Para desbloquear este problema y restablecer el pedido de compra al estado *Borrador*, vaya a **Adquisiciones y abastecimiento \> Tareas periódicas \> Limpiar \> Restablecimiento de distribución de pedido de compra**.</span><span class="sxs-lookup"><span data-stu-id="f95b5-125">To unblock this issue and reset the purchase order to a *Draft* state, go to **Procurement and sourcing \> Periodic tasks \> Clean up \> Purchase order distribution reset**.</span></span> <span data-ttu-id="f95b5-126">Para obtener más información, consulte la siguiente publicación de blog: [Resolver errores de distribución de pedidos de compra en Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).</span><span class="sxs-lookup"><span data-stu-id="f95b5-126">For more information, see the following blog post: [Resolve PO distribution errors in Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).</span></span>

## <a name="one-or-more-accounting-distributions-are-either-over-distributed-or-under-distributed"></a><span data-ttu-id="f95b5-127">Una o más distribuciones contables están distribuidas en exceso o en defecto.</span><span class="sxs-lookup"><span data-stu-id="f95b5-127">One or more accounting distributions are either over-distributed or under-distributed.</span></span>

### <a name="issue-description"></a><span data-ttu-id="f95b5-128">Descripción del problema</span><span class="sxs-lookup"><span data-stu-id="f95b5-128">Issue description</span></span>

<span data-ttu-id="f95b5-129">Aparece el siguiente error: "Una o más distribuciones contables están distribuidas en exceso o en defecto".</span><span class="sxs-lookup"><span data-stu-id="f95b5-129">You receive the following error: "One or more accounting distributions is either over-distributed or under-distributed."</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="f95b5-130">Solución del problema</span><span class="sxs-lookup"><span data-stu-id="f95b5-130">Issue resolution</span></span>

<span data-ttu-id="f95b5-131">Este problema se puede producir debido a incoherencias en las distribuciones de pedidos de compra.</span><span class="sxs-lookup"><span data-stu-id="f95b5-131">This issue can occur because of inconsistency in purchase order distributions.</span></span>

<span data-ttu-id="f95b5-132">Para desbloquear este problema y restablecer el pedido de compra al estado *Borrador*, vaya a **Adquisiciones y abastecimiento \> Tareas periódicas \> Limpiar \> Restablecimiento de distribución de pedido de compra**.</span><span class="sxs-lookup"><span data-stu-id="f95b5-132">To unblock this issue and reset the purchase order to a *Draft* state, go to **Procurement and sourcing \> Periodic tasks \> Clean up \> Purchase order distribution reset**.</span></span> <span data-ttu-id="f95b5-133">Para obtener más información, consulte la siguiente publicación de blog: [Resolver errores de distribución de pedidos de compra en Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).</span><span class="sxs-lookup"><span data-stu-id="f95b5-133">For more information, see the following blog post: [Resolve PO distribution errors in Dynamics 365 Supply Chain Management](https://cloudblogs.microsoft.com/dynamics365/it/2020/08/12/resolve-po-distribution-errors-in-dynamics-365-supply-chain-management/).</span></span>

## <a name="can-i-show-only-purchase-orders-that-i-created"></a><span data-ttu-id="f95b5-134">¿Puedo mostrar solo los pedidos de compra que he creado?</span><span class="sxs-lookup"><span data-stu-id="f95b5-134">Can I show only purchase orders that I created?</span></span>

<span data-ttu-id="f95b5-135">Esta funcionalidad no está disponible actualmente.</span><span class="sxs-lookup"><span data-stu-id="f95b5-135">This functionality isn't currently available.</span></span>

## <a name="can-i-reserve-inventory-and-create-transactions-against-registered-inventory-on-a-purchase-order"></a><span data-ttu-id="f95b5-136">¿Puedo reservar inventario y crear transacciones con el inventario registrado en un pedido de compra?</span><span class="sxs-lookup"><span data-stu-id="f95b5-136">Can I reserve inventory and create transactions against registered inventory on a purchase order?</span></span>

### <a name="issue-description"></a><span data-ttu-id="f95b5-137">Descripción del problema</span><span class="sxs-lookup"><span data-stu-id="f95b5-137">Issue description</span></span>

<span data-ttu-id="f95b5-138">Puede reservar el inventario incluso cuando los elementos están en un *Registrado* en un pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="f95b5-138">Even when items are in a *Registered* state on a purchase order, you can still reserve the inventory.</span></span> <span data-ttu-id="f95b5-139">En otras palabras, puede crear transacciones con el inventario registrado.</span><span class="sxs-lookup"><span data-stu-id="f95b5-139">In other words, you can create transactions against the registered inventory.</span></span>

### <a name="reproduce-the-issue"></a><span data-ttu-id="f95b5-140">Reproducir el problema</span><span class="sxs-lookup"><span data-stu-id="f95b5-140">Reproduce the issue</span></span>

<span data-ttu-id="f95b5-141">El siguiente procedimiento muestra una manera de reproducir el problema.</span><span class="sxs-lookup"><span data-stu-id="f95b5-141">The following procedure shows one way to reproduce the issue.</span></span>

1. <span data-ttu-id="f95b5-142">Cree un pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="f95b5-142">Create a purchase order.</span></span>
2. <span data-ttu-id="f95b5-143">Registre la línea de pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="f95b5-143">Register the purchase order line.</span></span>
3. <span data-ttu-id="f95b5-144">Tenga en cuenta que puede generar reservas o transacciones con el inventario registrado.</span><span class="sxs-lookup"><span data-stu-id="f95b5-144">Notice that you can generate reservations or transactions against the registered inventory.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="f95b5-145">Solución del problema</span><span class="sxs-lookup"><span data-stu-id="f95b5-145">Issue resolution</span></span>

<span data-ttu-id="f95b5-146">Este comportamiento se debe al diseño.</span><span class="sxs-lookup"><span data-stu-id="f95b5-146">This behavior is by design.</span></span> <span data-ttu-id="f95b5-147">La expectativa es que los artículos registrados hayan llegado físicamente al almacén o al inventario y, por lo tanto, estén disponibles para reserva.</span><span class="sxs-lookup"><span data-stu-id="f95b5-147">The expectation is that the registered items have physically arrived in the warehouse or inventory, and that they are therefore available for reservation.</span></span>

## <a name="purchase-orders-dont-reflect-the-language-settings-of-the-legal-entity"></a><span data-ttu-id="f95b5-148">Los pedidos de compra no reflejan la configuración de idioma de la entidad jurídica.</span><span class="sxs-lookup"><span data-stu-id="f95b5-148">Purchase orders don't reflect the language settings of the legal entity.</span></span>

### <a name="issue-description"></a><span data-ttu-id="f95b5-149">Descripción del problema</span><span class="sxs-lookup"><span data-stu-id="f95b5-149">Issue description</span></span>

<span data-ttu-id="f95b5-150">El nombre del producto en un pedido de compra se muestra en el idioma del sistema, no en el idioma establecido para la entidad jurídica donde se creó el pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="f95b5-150">The product name on a purchase order is shown in the system language instead of the language that is set for the legal entity where the purchase order was created.</span></span>

### <a name="reproduce-the-issue"></a><span data-ttu-id="f95b5-151">Reproducir el problema</span><span class="sxs-lookup"><span data-stu-id="f95b5-151">Reproduce the issue</span></span>

<span data-ttu-id="f95b5-152">El siguiente procedimiento muestra una manera de reproducir el problema.</span><span class="sxs-lookup"><span data-stu-id="f95b5-152">The following procedure shows one way to reproduce the issue.</span></span>

1. <span data-ttu-id="f95b5-153">Establezca el idioma del sistema en *EN-US* (inglés americano).</span><span class="sxs-lookup"><span data-stu-id="f95b5-153">Set the system language to *EN-US* (US English).</span></span>
1. <span data-ttu-id="f95b5-154">Asegúrese de que haya un producto donde se mantienen los idiomas *EN-US* y *DE* (alemán) para las traducciones del nombre del producto.</span><span class="sxs-lookup"><span data-stu-id="f95b5-154">Make sure that there is a product where the *EN-US* and *DE* (German) languages are maintained for translations of the product name.</span></span>
1. <span data-ttu-id="f95b5-155">Cambie el idioma de una entidad jurídica a *DE*.</span><span class="sxs-lookup"><span data-stu-id="f95b5-155">Change the language of a legal entity to *DE*.</span></span>
1. <span data-ttu-id="f95b5-156">En la entidad jurídica donde *DE* está configurado como idioma, cree un pedido de compra que incluya el producto.</span><span class="sxs-lookup"><span data-stu-id="f95b5-156">In the legal entity where *DE* is set as the language, create a purchase order that includes the product.</span></span>
1. <span data-ttu-id="f95b5-157">Tenga en cuenta que el nombre del producto se sigue mostrando en inglés de EE.UU. (el idioma del sistema).</span><span class="sxs-lookup"><span data-stu-id="f95b5-157">Notice that the product name is still shown in US English (the system language).</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="f95b5-158">Solución del problema</span><span class="sxs-lookup"><span data-stu-id="f95b5-158">Issue resolution</span></span>

<span data-ttu-id="f95b5-159">Este comportamiento se debe al diseño.</span><span class="sxs-lookup"><span data-stu-id="f95b5-159">This behavior is by design.</span></span> <span data-ttu-id="f95b5-160">En los pedidos de compra, el producto siempre se muestra en el idioma del sistema.</span><span class="sxs-lookup"><span data-stu-id="f95b5-160">On purchase orders, the product is always shown in the system language.</span></span> <span data-ttu-id="f95b5-161">El idioma del pedido de compra se utiliza cuando se crea un diario de confirmación.</span><span class="sxs-lookup"><span data-stu-id="f95b5-161">The purchase order language is used when a confirmation journal is created.</span></span>

## <a name="the-approved-vendor-list-by-product-entity-doesnt-allow-the-effective-date-to-be-changed"></a><span data-ttu-id="f95b5-162">La lista de proveedores aprobados por entidad de producto no permite cambiar la fecha de vigencia.</span><span class="sxs-lookup"><span data-stu-id="f95b5-162">The Approved vendor list by product entity doesn't allow the effective date to be changed.</span></span>

### <a name="issue-description"></a><span data-ttu-id="f95b5-163">Descripción del problema</span><span class="sxs-lookup"><span data-stu-id="f95b5-163">Issue description</span></span>

<span data-ttu-id="f95b5-164">Un producto tiene un proveedor aprobado que tiene, por ejemplo, una fecha de vigencia del 11 de enero de 2018 (*11/01/2018*) y *Nunca* como fecha de vencimiento.</span><span class="sxs-lookup"><span data-stu-id="f95b5-164">A product has an approved vendor that has, for example, an effective date of January 11, 2018 (*01/11/2018*), and an expiration date of *Never*.</span></span> <span data-ttu-id="f95b5-165">Si intenta cambiar la fecha de vigencia al 10 de enero de 2018 (*10/01/2018*) o al 12 de enero de 2018 (*12/01/2018*), aparecerá el siguiente error:</span><span class="sxs-lookup"><span data-stu-id="f95b5-165">If you try to change the effective date to January 10, 2018 (*01/10/2018*), or January 12, 2018 (*01/12/2018*), you receive the following error:</span></span>

> <span data-ttu-id="f95b5-166">No se puede crear un registro en la lista de proveedores aprobados (PdsApproveVendorList).</span><span class="sxs-lookup"><span data-stu-id="f95b5-166">Cannot create a record in Approved supplier list (PdsApproveVendorList).</span></span> <span data-ttu-id="f95b5-167">El valor de 'Vencimiento' debe ser mayor o igual que el valor de 'Vigencia'.</span><span class="sxs-lookup"><span data-stu-id="f95b5-167">The 'Expiration' value needs to be greater than or equal to the 'Effective' value.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="f95b5-168">Solución del problema</span><span class="sxs-lookup"><span data-stu-id="f95b5-168">Issue resolution</span></span>

<span data-ttu-id="f95b5-169">Solo puede ampliar el período para el que está aprobado el proveedor.</span><span class="sxs-lookup"><span data-stu-id="f95b5-169">You can only extend the period that the vendor is approved for.</span></span> <span data-ttu-id="f95b5-170">Se aplican las siguientes reglas:</span><span class="sxs-lookup"><span data-stu-id="f95b5-170">The following rules apply:</span></span>

- <span data-ttu-id="f95b5-171">Para cambiar la fecha de vigencia de modo que sea anterior a cualquiera de los registros (períodos) existentes para el proveedor del artículo, la fecha de vencimiento del nuevo período debe ser anterior a todas las fechas de vencimiento de los registros existentes.</span><span class="sxs-lookup"><span data-stu-id="f95b5-171">To change the effective date so that it's earlier than any of the existing records (periods) for the item vendor, the expiration date of the new period must be before all the expiration dates in the existing records.</span></span>
- <span data-ttu-id="f95b5-172">Para cambiar la fecha de vencimiento de forma que sea posterior a cualquiera de los períodos existentes, la fecha de vigencia debe ser posterior a la última fecha de vencimiento en cualquier registro existente.</span><span class="sxs-lookup"><span data-stu-id="f95b5-172">To change the expiration date so that it's later than any of the existing periods, the effective date must be after the latest expiration date in any existing record.</span></span>
- <span data-ttu-id="f95b5-173">Para reducir el período general para el que está aprobado el proveedor, debe eliminar o modificar los registros existentes.</span><span class="sxs-lookup"><span data-stu-id="f95b5-173">To reduce the overall period that the vendor is approved for, you must delete or modify existing records.</span></span> <span data-ttu-id="f95b5-174">Como alterna, puede utilizar el modificador **truncate** durante la importación.</span><span class="sxs-lookup"><span data-stu-id="f95b5-174">Alternatively, you can use the **truncate** switch during import.</span></span> <span data-ttu-id="f95b5-175">Este modificador elimina todos los registros existentes en la tabla de proveedores aprobados por artículo.</span><span class="sxs-lookup"><span data-stu-id="f95b5-175">This switch deletes all existing records in the table for approved vendors by item.</span></span>

<span data-ttu-id="f95b5-176">Para el escenario de ejemplo que se describe en la descripción del problema, donde un registro tiene como fecha de vigencia *11/01/2018* y *Nunca* como fecha de vencimiento, puede importar un nuevo registro que tenga como fecha de vigencia *10/01/2018* y *Nunca* como fecha de vencimiento.</span><span class="sxs-lookup"><span data-stu-id="f95b5-176">For the example scenario that is described in the issue description, where a record has an effective date of *01/11/2018* and an expiration date of *Never*, you can import a new record that has an effective date of *01/10/2018* and an expiration date of *Never*.</span></span> <span data-ttu-id="f95b5-177">Sin embargo, no puede reducir el período para que la fecha de vigencia se actualice a *12/01/2018* a través de la administración de datos.</span><span class="sxs-lookup"><span data-stu-id="f95b5-177">However, you can't reduce the period so that the effective date is updated to *01/12/2018* via data management.</span></span> <span data-ttu-id="f95b5-178">Debe realizar este cambio a través de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="f95b5-178">You must make this change through the UI.</span></span>

## <a name="after-i-change-the-delivery-address-on-a-purchase-order-header-the-delivery-name-isnt-synced"></a><span data-ttu-id="f95b5-179">Después de cambiar la dirección de entrega en el encabezado de un pedido de compra, no se sincroniza el nombre de entrega.</span><span class="sxs-lookup"><span data-stu-id="f95b5-179">After I change the delivery address on a purchase order header, the delivery name isn't synced.</span></span>

### <a name="issue-description"></a><span data-ttu-id="f95b5-180">Descripción del problema</span><span class="sxs-lookup"><span data-stu-id="f95b5-180">Issue description</span></span>

<span data-ttu-id="f95b5-181">La dirección en el encabezado de un pedido de compra se actualiza a una dirección que no es una dirección de entrega.</span><span class="sxs-lookup"><span data-stu-id="f95b5-181">The address on the header of a purchase order is updated to an address that isn't a delivery address.</span></span> <span data-ttu-id="f95b5-182">Aunque la dirección se actualiza en el pedido de compra, el nombre de entrega no se actualiza según la dirección actualizada.</span><span class="sxs-lookup"><span data-stu-id="f95b5-182">Although the address is updated on the purchase order, the delivery name isn't updated based on the updated address.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="f95b5-183">Solución del problema</span><span class="sxs-lookup"><span data-stu-id="f95b5-183">Issue resolution</span></span>

<span data-ttu-id="f95b5-184">Este comportamiento se debe al diseño.</span><span class="sxs-lookup"><span data-stu-id="f95b5-184">This behavior is by design.</span></span> <span data-ttu-id="f95b5-185">La dirección seleccionada debe clasificarse como dirección de entrega.</span><span class="sxs-lookup"><span data-stu-id="f95b5-185">The selected address must be classified as a delivery address.</span></span> <span data-ttu-id="f95b5-186">De lo contrario, el nombre de entrega no se actualiza en función de la dirección seleccionada.</span><span class="sxs-lookup"><span data-stu-id="f95b5-186">Otherwise, the delivery name isn't updated based on the selected address.</span></span>

## <a name="can-i-find-the-user-who-canceled-a-purchase-order"></a><span data-ttu-id="f95b5-187">¿Puedo encontrar al usuario que canceló un pedido de compra?</span><span class="sxs-lookup"><span data-stu-id="f95b5-187">Can I find the user who canceled a purchase order?</span></span>

<span data-ttu-id="f95b5-188">Esta información solo se sigue si el pedido de compra está sujeto a la administración de cambios.</span><span class="sxs-lookup"><span data-stu-id="f95b5-188">This information is tracked only if the purchase order is subject to change management.</span></span> <span data-ttu-id="f95b5-189">Si usa la administración de cambios, puede ver quién envió el cambio (la cancelación) y quién lo aprobó.</span><span class="sxs-lookup"><span data-stu-id="f95b5-189">If you use change management, you can see who submitted the change (the cancellation), and who approved it.</span></span>
