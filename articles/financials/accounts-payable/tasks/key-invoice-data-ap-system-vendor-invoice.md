---
title: Datos clave en el sistema de proveedores mediante factura de proveedor
description: Esta guía de tareas le ayudará a crear una factura de proveedor de un pedido de compra y a ver los resultados de conciliación del pedido de compra, la recepción y la factura (triple conciliación).
author: abruer
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchCreateOrder, InventItemIdLookupPurchase, PurchEditLines, VendEditInvoice, InventItemIdLookupSimple, VendInvoiceMatchingDetails
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e1d2e31a5de7cefd20996c18bf4771296a587997
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "359115"
---
# <a name="key-invoice-data-in-ap-system-using-vendor-invoice"></a><span data-ttu-id="78170-103">Datos clave en el sistema de proveedores mediante factura de proveedor</span><span class="sxs-lookup"><span data-stu-id="78170-103">Key invoice data in AP system using vendor invoice</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="78170-104">Esta guía de tareas le ayudará a crear una factura de proveedor de un pedido de compra y a ver los resultados de conciliación del pedido de compra, la recepción y la factura (triple conciliación).</span><span class="sxs-lookup"><span data-stu-id="78170-104">This task guide will help you create a vendor invoice from a purchase order and view the results of matching the purchase order, receipt, and invoice (3 way matching).</span></span>


## <a name="create-a-purchase-order"></a><span data-ttu-id="78170-105">Crear un pedido de compra</span><span class="sxs-lookup"><span data-stu-id="78170-105">Create a purchase order</span></span>
1. <span data-ttu-id="78170-106">Vaya a Proveedores > Pedidos de compra > Todos los pedidos de compra.</span><span class="sxs-lookup"><span data-stu-id="78170-106">Go to Accounts payable > Purchase orders > All purchase orders.</span></span>
2. <span data-ttu-id="78170-107">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="78170-107">Click New.</span></span>
3. <span data-ttu-id="78170-108">En el campo Cuenta de proveedor, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="78170-108">In the Vendor account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="78170-109">Busque un proveedor para seleccionarlo.</span><span class="sxs-lookup"><span data-stu-id="78170-109">Find a vendor to select.</span></span> <span data-ttu-id="78170-110">Por ejemplo, desplácese hasta US-104.</span><span class="sxs-lookup"><span data-stu-id="78170-110">For example, scroll down to US-104.</span></span>
5. <span data-ttu-id="78170-111">Seleccione el proveedor US-104.</span><span class="sxs-lookup"><span data-stu-id="78170-111">Select vendor US-104.</span></span>
6. <span data-ttu-id="78170-112">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="78170-112">Click OK.</span></span>
7. <span data-ttu-id="78170-113">En el campo Código de artículo, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="78170-113">In the Item number field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="78170-114">Seleccione un artículo de inventario.</span><span class="sxs-lookup"><span data-stu-id="78170-114">Select an inventory item.</span></span> <span data-ttu-id="78170-115">Para este ejemplo, seleccione el código de artículo 1000.</span><span class="sxs-lookup"><span data-stu-id="78170-115">For example, select item number 1000.</span></span>
9. <span data-ttu-id="78170-116">Expanda o contraiga la sección Detalles de línea.</span><span class="sxs-lookup"><span data-stu-id="78170-116">Expand or collapse the Line details section.</span></span>
10. <span data-ttu-id="78170-117">Haga clic en la pestaña Configurar.</span><span class="sxs-lookup"><span data-stu-id="78170-117">Click the Setup tab.</span></span>
    * <span data-ttu-id="78170-118">Puede anular la directiva de conciliación para no usar ninguna conciliación, doble conciliación o triple conciliación.</span><span class="sxs-lookup"><span data-stu-id="78170-118">You can override the matching policy to use no matching, 2-way matching, or 3-way matching.</span></span>  
11. <span data-ttu-id="78170-119">Expanda o contraiga la sección Detalles de línea.</span><span class="sxs-lookup"><span data-stu-id="78170-119">Expand or collapse the Line details section.</span></span>
12. <span data-ttu-id="78170-120">En el panel de acciones, haga clic en Compra.</span><span class="sxs-lookup"><span data-stu-id="78170-120">On the Action Pane, click Purchase.</span></span>
13. <span data-ttu-id="78170-121">Haga clic en Confirmar.</span><span class="sxs-lookup"><span data-stu-id="78170-121">Click Confirm.</span></span>

## <a name="receive-the-products"></a><span data-ttu-id="78170-122">Recibir los productos</span><span class="sxs-lookup"><span data-stu-id="78170-122">Receive the products</span></span>
1. <span data-ttu-id="78170-123">En el panel de acciones, haga clic en Recibir.</span><span class="sxs-lookup"><span data-stu-id="78170-123">On the Action Pane, click Receive.</span></span>
2. <span data-ttu-id="78170-124">Haga clic en Recepción de producto.</span><span class="sxs-lookup"><span data-stu-id="78170-124">Click Product receipt.</span></span>
3. <span data-ttu-id="78170-125">En el campo Recepción de producto, especifique el número de recepción de producto.</span><span class="sxs-lookup"><span data-stu-id="78170-125">In the Product receipt field, enter the product receipt number.</span></span> <span data-ttu-id="78170-126">Por ejemplo, escriba PR123.</span><span class="sxs-lookup"><span data-stu-id="78170-126">For example, enter PR123.</span></span>
4. <span data-ttu-id="78170-127">Haga clic en Aceptar para registrar la recepción de producto.</span><span class="sxs-lookup"><span data-stu-id="78170-127">Click OK to post the product receipt.</span></span>
5. <span data-ttu-id="78170-128">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="78170-128">Close the page.</span></span>

## <a name="create-a-vendor-invoice"></a><span data-ttu-id="78170-129">Crear una factura de proveedor</span><span class="sxs-lookup"><span data-stu-id="78170-129">Create a vendor invoice</span></span>
1. <span data-ttu-id="78170-130">Vaya a Clientes > Pedidos de compra > Pedidos de compra recibidos pero no facturados.</span><span class="sxs-lookup"><span data-stu-id="78170-130">Go to Accounts payable > Purchase orders > Purchase orders received but not invoiced.</span></span>
2. <span data-ttu-id="78170-131">Seleccione el pedido de compra que ha creado.</span><span class="sxs-lookup"><span data-stu-id="78170-131">Select the purchase order that you created.</span></span>
3. <span data-ttu-id="78170-132">En el panel de acciones, haga clic en Factura.</span><span class="sxs-lookup"><span data-stu-id="78170-132">On the Action Pane, click Invoice.</span></span>
4. <span data-ttu-id="78170-133">Haga clic en Factura.</span><span class="sxs-lookup"><span data-stu-id="78170-133">Click Invoice.</span></span>
5. <span data-ttu-id="78170-134">En el campo Número, especifique el número de factura.</span><span class="sxs-lookup"><span data-stu-id="78170-134">In the Number field, enter the invoice number.</span></span>
6. <span data-ttu-id="78170-135">En el campo Descripción de factura, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="78170-135">In the Invoice description field, type a value.</span></span>
7. <span data-ttu-id="78170-136">En el campo Fecha de la factura, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="78170-136">In the Invoice date field, enter a date.</span></span>
8. <span data-ttu-id="78170-137">En el campo Precio unitario, escriba 1200.</span><span class="sxs-lookup"><span data-stu-id="78170-137">In the Unit price field, enter 1200.</span></span>
9. <span data-ttu-id="78170-138">Haga clic en Agregar línea.</span><span class="sxs-lookup"><span data-stu-id="78170-138">Click Add line.</span></span>
10. <span data-ttu-id="78170-139">En el campo Código de artículo, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="78170-139">In the Item number field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="78170-140">En la lista, busque el número de artículo de cargo de la instalación.</span><span class="sxs-lookup"><span data-stu-id="78170-140">In the list, find the installation charge item number.</span></span> <span data-ttu-id="78170-141">Por ejemplo, S0001</span><span class="sxs-lookup"><span data-stu-id="78170-141">For example, S0001</span></span>
12. <span data-ttu-id="78170-142">Seleccione el número de artículo de cargo de la instalación.</span><span class="sxs-lookup"><span data-stu-id="78170-142">Select the installation charge item number.</span></span>
    * <span data-ttu-id="78170-143">Tenga en cuenta que no se ha realizado ninguna conciliación desde que realizó los cambios.</span><span class="sxs-lookup"><span data-stu-id="78170-143">Note that matching has not been performed since you made the changes.</span></span>  
13. <span data-ttu-id="78170-144">Haga clic en Actualizar estado de conciliación.</span><span class="sxs-lookup"><span data-stu-id="78170-144">Click Update match status.</span></span>
14. <span data-ttu-id="78170-145">En el panel de acciones, haga clic en Revisar.</span><span class="sxs-lookup"><span data-stu-id="78170-145">On the Action Pane, click Review.</span></span>
15. <span data-ttu-id="78170-146">Haga clic en Detalles coincidentes.</span><span class="sxs-lookup"><span data-stu-id="78170-146">Click Matching details.</span></span>
    * <span data-ttu-id="78170-147">La nueva línea con servicios no tiene que conciliarse, por lo que el estado sigue siendo “No se realizó”.</span><span class="sxs-lookup"><span data-stu-id="78170-147">The new line with services does not need to be matched so the status stays "Not performed".</span></span>  
16. <span data-ttu-id="78170-148">Seleccione la recepción de producto para el artículo de inventario que ha recibido.</span><span class="sxs-lookup"><span data-stu-id="78170-148">Select the product receipt for the inventory item that you received.</span></span>
    * <span data-ttu-id="78170-149">La línea con la recepción de producto se concilió, pero no existe coincidencia de cantidad o de precio, por lo que se ha producido algún error.</span><span class="sxs-lookup"><span data-stu-id="78170-149">The line with the product receipt was matched but there is a mismatch of quantity or price so it fails.</span></span>  
17. <span data-ttu-id="78170-150">En el campo Precio unitario, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="78170-150">In the Unit price field, enter a number.</span></span>
    * <span data-ttu-id="78170-151">Ahora que el precio unitario coincide, el estado se actualiza a Aprobado.</span><span class="sxs-lookup"><span data-stu-id="78170-151">Now that the unit price matches, the status is updated to Passed.</span></span> <span data-ttu-id="78170-152">Si la directiva permite las discrepancias o si la conciliación solo es una advertencia, podrá registrar la factura.</span><span class="sxs-lookup"><span data-stu-id="78170-152">If your policy allows discrepancies or if matching is only a warning, you can still post the invoice.</span></span>  
18. <span data-ttu-id="78170-153">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="78170-153">Close the page.</span></span>
19. <span data-ttu-id="78170-154">Haga clic en Registrar.</span><span class="sxs-lookup"><span data-stu-id="78170-154">Click Post.</span></span>
20. <span data-ttu-id="78170-155">Cierre el formulario.</span><span class="sxs-lookup"><span data-stu-id="78170-155">Close the form.</span></span>
    * <span data-ttu-id="78170-156">Tenga en cuenta que el pedido de compra ya no aparece en la lista como recibido, sino como no facturado.</span><span class="sxs-lookup"><span data-stu-id="78170-156">Note that the purchase order is no longer listed as received but not invoiced.</span></span>  

