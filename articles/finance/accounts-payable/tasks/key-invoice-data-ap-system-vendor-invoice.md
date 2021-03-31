---
title: Datos de factura clave en proveedores mediante una factura de proveedor
description: Esta guía de tareas le ayudará a crear una factura de proveedor de un pedido de compra y a ver los resultados de conciliación del pedido de compra, la recepción y la factura (triple conciliación).
author: abruer
manager: AnnBe
ms.date: 07/22/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchCreateOrder, InventItemIdLookupPurchase, PurchEditLines, VendEditInvoice, InventItemIdLookupSimple, VendInvoiceMatchingDetails
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 20a058eb17bcab11056c91ab3570d6cd5b84b631
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5227217"
---
# <a name="key-invoice-data-in-ap-using-a-vendor-invoice"></a><span data-ttu-id="e9451-103">Datos de factura clave en proveedores mediante una factura de proveedor</span><span class="sxs-lookup"><span data-stu-id="e9451-103">Key invoice data in AP using a vendor invoice</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="e9451-104">Esta guía de tareas le ayudará a crear una factura de proveedor de un pedido de compra y a ver los resultados de conciliación del pedido de compra, la recepción y la factura (triple conciliación).</span><span class="sxs-lookup"><span data-stu-id="e9451-104">This task guide will help you create a vendor invoice from a purchase order and view the results of matching the purchase order, receipt, and invoice (3 way matching).</span></span>


## <a name="create-a-purchase-order"></a><span data-ttu-id="e9451-105">Crear un pedido de compra</span><span class="sxs-lookup"><span data-stu-id="e9451-105">Create a purchase order</span></span>
1. <span data-ttu-id="e9451-106">En el panel de exploración, vaya a **Módulos > Proveedores > Pedidos de compra > Todos los pedidos de compra**.</span><span class="sxs-lookup"><span data-stu-id="e9451-106">In the Navigation pane, go to **Modules > Accounts payable > Purchase orders > All purchase orders**.</span></span>
2. <span data-ttu-id="e9451-107">Haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="e9451-107">Click **New**.</span></span>
3. <span data-ttu-id="e9451-108">En el campo **Cuenta de proveedor**, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="e9451-108">In the **Vendor account** field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="e9451-109">Busque un proveedor para seleccionarlo.</span><span class="sxs-lookup"><span data-stu-id="e9451-109">Find a vendor to select.</span></span> <span data-ttu-id="e9451-110">Por ejemplo, desplácese hasta US-104.</span><span class="sxs-lookup"><span data-stu-id="e9451-110">For example, scroll down to US-104.</span></span>
5. <span data-ttu-id="e9451-111">Seleccione el proveedor US-104.</span><span class="sxs-lookup"><span data-stu-id="e9451-111">Select vendor US-104.</span></span>
6. <span data-ttu-id="e9451-112">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e9451-112">Click **OK**.</span></span>
7. <span data-ttu-id="e9451-113">En el campo **Código de artículo**, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="e9451-113">In the **Item number** field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="e9451-114">Seleccione un artículo de inventario.</span><span class="sxs-lookup"><span data-stu-id="e9451-114">Select an inventory item.</span></span> <span data-ttu-id="e9451-115">Para este ejemplo, seleccione el código de artículo 1000.</span><span class="sxs-lookup"><span data-stu-id="e9451-115">For example, select item number 1000.</span></span>
9. <span data-ttu-id="e9451-116">Expanda la ficha desplegable **Detalles de línea**.</span><span class="sxs-lookup"><span data-stu-id="e9451-116">Expand the **Line details** fastTab.</span></span>
10. <span data-ttu-id="e9451-117">Haga clic en la pestaña **Configuración**. Puede anular la directiva de conciliación para no usar ninguna conciliación, doble conciliación o triple conciliación.</span><span class="sxs-lookup"><span data-stu-id="e9451-117">Click the **Setup** tab. You can override the matching policy to use no matching, 2-way matching, or 3-way matching.</span></span>  
11. <span data-ttu-id="e9451-118">En el panel de acciones, haga clic en **Compra.**</span><span class="sxs-lookup"><span data-stu-id="e9451-118">On the Action Pane, click **Purchase**.</span></span>
12. <span data-ttu-id="e9451-119">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="e9451-119">Click **Confirm**.</span></span>

## <a name="receive-the-products"></a><span data-ttu-id="e9451-120">Recibir los productos</span><span class="sxs-lookup"><span data-stu-id="e9451-120">Receive the products</span></span>
1. <span data-ttu-id="e9451-121">En el panel de acciones, haga clic en **Recibir.**</span><span class="sxs-lookup"><span data-stu-id="e9451-121">On the Action Pane, click **Receive**.</span></span>
2. <span data-ttu-id="e9451-122">Haga clic en **Recepción de producto.**</span><span class="sxs-lookup"><span data-stu-id="e9451-122">Click **Product receipt**.</span></span>
3. <span data-ttu-id="e9451-123">En el campo **Recepción de producto**, especifique el número de recepción de producto.</span><span class="sxs-lookup"><span data-stu-id="e9451-123">In the **Product receipt** field, enter the product receipt number.</span></span> <span data-ttu-id="e9451-124">Por ejemplo, escriba PR123.</span><span class="sxs-lookup"><span data-stu-id="e9451-124">For example, enter PR123.</span></span>
4. <span data-ttu-id="e9451-125">Haga clic en **Aceptar** para registrar la recepción de producto.</span><span class="sxs-lookup"><span data-stu-id="e9451-125">Click **OK** to post the product receipt.</span></span>
5. <span data-ttu-id="e9451-126">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="e9451-126">Close the page.</span></span>

## <a name="create-a-vendor-invoice"></a><span data-ttu-id="e9451-127">Crear una factura de proveedor</span><span class="sxs-lookup"><span data-stu-id="e9451-127">Create a vendor invoice</span></span>
1. <span data-ttu-id="e9451-128">En el panel de exploración, vaya a **Módulos > Proveedores > Pedidos de compra > Pedidos de compra recibidos pero no facturados**.</span><span class="sxs-lookup"><span data-stu-id="e9451-128">In the Navigation pane, go to **Modules > Accounts payable > Purchase orders > Purchase orders received but not invoiced**.</span></span>
2. <span data-ttu-id="e9451-129">Seleccione el pedido de compra que ha creado.</span><span class="sxs-lookup"><span data-stu-id="e9451-129">Select the purchase order that you created.</span></span>
3. <span data-ttu-id="e9451-130">En el Panel de acciones, haga clic en **Factura**.</span><span class="sxs-lookup"><span data-stu-id="e9451-130">On the Action Pane, click **Invoice**.</span></span>
4. <span data-ttu-id="e9451-131">Haga clic en **Factura**.</span><span class="sxs-lookup"><span data-stu-id="e9451-131">Click **Invoice**.</span></span>
5. <span data-ttu-id="e9451-132">En el campo **Número**, especifique el número de factura.</span><span class="sxs-lookup"><span data-stu-id="e9451-132">In the **Number** field, enter the invoice number.</span></span>
6. <span data-ttu-id="e9451-133">En el campo **Descripción de factura**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="e9451-133">In the **Invoice description** field, type a value.</span></span>
7. <span data-ttu-id="e9451-134">En el campo **Fecha de factura**, escriba una fecha.</span><span class="sxs-lookup"><span data-stu-id="e9451-134">In the **Invoice date** field, enter a date.</span></span>
8. <span data-ttu-id="e9451-135">En el campo **Precio unitario**, escriba 1200.</span><span class="sxs-lookup"><span data-stu-id="e9451-135">In the **Unit price** field, enter 1200.</span></span>
9. <span data-ttu-id="e9451-136">Haga clic en **Agregar línea.**</span><span class="sxs-lookup"><span data-stu-id="e9451-136">Click **Add line**.</span></span>
10. <span data-ttu-id="e9451-137">En el campo **Código de artículo**, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="e9451-137">In the **Item number** field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="e9451-138">En la lista, busque el número de artículo de cargo de la instalación.</span><span class="sxs-lookup"><span data-stu-id="e9451-138">In the list, find the installation charge item number.</span></span> <span data-ttu-id="e9451-139">Por ejemplo, S0001</span><span class="sxs-lookup"><span data-stu-id="e9451-139">For example, S0001</span></span>
12. <span data-ttu-id="e9451-140">Seleccione el número de artículo de cargo de la instalación.</span><span class="sxs-lookup"><span data-stu-id="e9451-140">Select the installation charge item number.</span></span> <span data-ttu-id="e9451-141">Tenga en cuenta que no se ha realizado ninguna conciliación desde que realizó los cambios.</span><span class="sxs-lookup"><span data-stu-id="e9451-141">Note that matching has not been performed since you made the changes.</span></span>  
13. <span data-ttu-id="e9451-142">Haga clic en Haga clic en **Actualizar estado de conciliación**.</span><span class="sxs-lookup"><span data-stu-id="e9451-142">Click **Update match status**.</span></span>
14. <span data-ttu-id="e9451-143">En el panel de acciones, haga clic en **Revisar**.</span><span class="sxs-lookup"><span data-stu-id="e9451-143">On the Action Pane, click **Review**.</span></span>
15. <span data-ttu-id="e9451-144">Haga clic en **Detalles coincidentes**.</span><span class="sxs-lookup"><span data-stu-id="e9451-144">Click **Matching details**.</span></span> <span data-ttu-id="e9451-145">La nueva línea con servicios no tiene que conciliarse, por lo que el estado sigue siendo “No se realizó”.</span><span class="sxs-lookup"><span data-stu-id="e9451-145">The new line with services does not need to be matched so the status stays "Not performed".</span></span>  
16. <span data-ttu-id="e9451-146">Seleccione la recepción de producto para el artículo de inventario que ha recibido.</span><span class="sxs-lookup"><span data-stu-id="e9451-146">Select the product receipt for the inventory item that you received.</span></span> <span data-ttu-id="e9451-147">La línea con la recepción de producto se concilió, pero no existe coincidencia de cantidad o de precio, por lo que se ha producido algún error.</span><span class="sxs-lookup"><span data-stu-id="e9451-147">The line with the product receipt was matched but there is a mismatch of quantity or price so it fails.</span></span>  
17. <span data-ttu-id="e9451-148">En el campo **Precio unitario**, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="e9451-148">In the **Unit price** field, enter a number.</span></span> <span data-ttu-id="e9451-149">Ahora que el precio unitario coincide, el estado se actualiza a Aprobado.</span><span class="sxs-lookup"><span data-stu-id="e9451-149">Now that the unit price matches, the status is updated to Passed.</span></span> <span data-ttu-id="e9451-150">Si la directiva permite las discrepancias o si la conciliación solo es una advertencia, podrá registrar la factura.</span><span class="sxs-lookup"><span data-stu-id="e9451-150">If your policy allows discrepancies or if matching is only a warning, you can still post the invoice.</span></span>  
18. <span data-ttu-id="e9451-151">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="e9451-151">Close the page.</span></span>
19. <span data-ttu-id="e9451-152">Haga clic en **Registrar**.</span><span class="sxs-lookup"><span data-stu-id="e9451-152">Click **Post**.</span></span>
20. <span data-ttu-id="e9451-153">Cierre el formulario.</span><span class="sxs-lookup"><span data-stu-id="e9451-153">Close the form.</span></span> <span data-ttu-id="e9451-154">Tenga en cuenta que el pedido de compra ya no aparece en la lista como recibido, sino como no facturado.</span><span class="sxs-lookup"><span data-stu-id="e9451-154">Note that the purchase order is no longer listed as received but not invoiced.</span></span>  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]