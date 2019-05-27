---
title: Introducir datos de factura en el sistema de proveedores mediante un grupo de facturas
description: Esta guía de la tarea le mostrará cómo usar el registro de facturas para crear facturas.
author: abruer
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4b4e9a52a383d4acc0bf2adc669fd88c0c0f7402
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1550360"
---
# <a name="key-invoice-data-into-the-ap-system-using-invoice-pool"></a><span data-ttu-id="e755e-103">Introducir datos de factura en el sistema de proveedores mediante un grupo de facturas</span><span class="sxs-lookup"><span data-stu-id="e755e-103">Key invoice data into the AP system using invoice pool</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e755e-104">Esta guía de la tarea le mostrará cómo usar el registro de facturas para crear facturas.</span><span class="sxs-lookup"><span data-stu-id="e755e-104">This task guide will show you how to use the invoice register to create invoices.</span></span>  <span data-ttu-id="e755e-105">A continuación use el grupo de facturas para que coincida con la factura de un pedido de compra y para finalizar el gasto en la página de la factura de proveedor.</span><span class="sxs-lookup"><span data-stu-id="e755e-105">Then use the invoice pool to match the invoice to a purchase order and finalize the expense in the vendor invoice page.</span></span>


## <a name="create-a-purchase-order"></a><span data-ttu-id="e755e-106">Crear un pedido de compra</span><span class="sxs-lookup"><span data-stu-id="e755e-106">Create a purchase order</span></span>
1. <span data-ttu-id="e755e-107">Vaya a Proveedores > Pedidos de compra > Pedidos de compra.</span><span class="sxs-lookup"><span data-stu-id="e755e-107">Go to Accounts payable > Purchase orders > Purchase orders.</span></span>
2. <span data-ttu-id="e755e-108">Haga clic en Nuevo para crear un pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="e755e-108">Click New to create a purchase order.</span></span>
3. <span data-ttu-id="e755e-109">En el campo Cuenta de proveedor, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="e755e-109">In the Vendor account field, click the drop down button to open the lookup.</span></span>
4. <span data-ttu-id="e755e-110">Seleccionar el proveedor en la lista.</span><span class="sxs-lookup"><span data-stu-id="e755e-110">Select the vendor from the list.</span></span> <span data-ttu-id="e755e-111">Por ejemplo, el proveedor 1001.</span><span class="sxs-lookup"><span data-stu-id="e755e-111">For example, vendor 1001.</span></span>
5. <span data-ttu-id="e755e-112">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="e755e-112">Click OK.</span></span>
6. <span data-ttu-id="e755e-113">En el campo Código de artículo, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="e755e-113">In the Item number field, click the drop down button to open the lookup.</span></span>
7. <span data-ttu-id="e755e-114">Busque el número de artículo de servicios en la lista.</span><span class="sxs-lookup"><span data-stu-id="e755e-114">Find the services item number in the list.</span></span> <span data-ttu-id="e755e-115">Por ejemplo, seleccione S0001.</span><span class="sxs-lookup"><span data-stu-id="e755e-115">For example, select S0001.</span></span>
8. <span data-ttu-id="e755e-116">Haga clic en el número de artículo y selecciónelo.</span><span class="sxs-lookup"><span data-stu-id="e755e-116">Click on the item number and select it.</span></span>
    * <span data-ttu-id="e755e-117">El importe neto es 75,00.</span><span class="sxs-lookup"><span data-stu-id="e755e-117">The net amount is 75.00.</span></span>  <span data-ttu-id="e755e-118">Este es el importe que se espera en la factura.</span><span class="sxs-lookup"><span data-stu-id="e755e-118">That is the amount that we will expect on the invoice.</span></span>  
9. <span data-ttu-id="e755e-119">En el panel de acciones, haga clic en Compra.</span><span class="sxs-lookup"><span data-stu-id="e755e-119">On the action pane, click Purchase.</span></span>
10. <span data-ttu-id="e755e-120">Haga clic en Confirmar.</span><span class="sxs-lookup"><span data-stu-id="e755e-120">Click Confirm.</span></span>

## <a name="create-and-post-and-invoice"></a><span data-ttu-id="e755e-121">Crear y registrar una factura</span><span class="sxs-lookup"><span data-stu-id="e755e-121">Create and post and invoice</span></span>
1. <span data-ttu-id="e755e-122">Vaya a Proveedores > Facturas > Registro de facturas.</span><span class="sxs-lookup"><span data-stu-id="e755e-122">Go to Accounts payable > Invoices > Invoice register.</span></span>
2. <span data-ttu-id="e755e-123">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="e755e-123">Click New.</span></span>
3. <span data-ttu-id="e755e-124">Abra la búsqueda para seleccionar el nombre del registro de facturas que desea usar.</span><span class="sxs-lookup"><span data-stu-id="e755e-124">Open the lookup to select the name of the invoice register that you want to use.</span></span>
4. <span data-ttu-id="e755e-125">Seleccione el nombre del registro de facturas que desee usar.</span><span class="sxs-lookup"><span data-stu-id="e755e-125">Select the name of the invoice register that you want to use.</span></span>
5. <span data-ttu-id="e755e-126">Haga clic en las líneas para abrir el registro y especificar las líneas de gastos.</span><span class="sxs-lookup"><span data-stu-id="e755e-126">Click on Lines to open the register and enter expense lines.</span></span>
6. <span data-ttu-id="e755e-127">En la búsqueda, seleccione un proveedor.</span><span class="sxs-lookup"><span data-stu-id="e755e-127">In the lookup, select a vendor.</span></span> <span data-ttu-id="e755e-128">Por ejemplo, haga clic en el proveedor 1001.</span><span class="sxs-lookup"><span data-stu-id="e755e-128">For example, click on vendor 1001.</span></span>
7. <span data-ttu-id="e755e-129">En el campo Factura, especifique el número de factura.</span><span class="sxs-lookup"><span data-stu-id="e755e-129">In the Invoice field, enter the invoice number.</span></span>
8. <span data-ttu-id="e755e-130">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="e755e-130">In the Description field, type a value.</span></span>
9. <span data-ttu-id="e755e-131">En el campo Crédito, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="e755e-131">In the Credit field, enter a number.</span></span>
10. <span data-ttu-id="e755e-132">En el campo Pedido de compra, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="e755e-132">In the Purchase order field, click the drop down button to open the lookup.</span></span>
11. <span data-ttu-id="e755e-133">Seleccione el pedido de compra que ha creado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="e755e-133">Select the purchase order that you created earlier.</span></span>
12. <span data-ttu-id="e755e-134">En el campo Aprobado por, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="e755e-134">In the Approved by field, click the drop down button to open the lookup.</span></span>
13. <span data-ttu-id="e755e-135">Resalte un aprobador y haga clic en Seleccionar para seleccionar el aprobador.</span><span class="sxs-lookup"><span data-stu-id="e755e-135">Highlight an approver and click Select to select that approver.</span></span>
14. <span data-ttu-id="e755e-136">Haga clic en Registrar.</span><span class="sxs-lookup"><span data-stu-id="e755e-136">Click Post.</span></span>
15. <span data-ttu-id="e755e-137">Cierre el formulario.</span><span class="sxs-lookup"><span data-stu-id="e755e-137">Close the form.</span></span>
16. <span data-ttu-id="e755e-138">Cierre el formulario.</span><span class="sxs-lookup"><span data-stu-id="e755e-138">Close the form.</span></span>

## <a name="open-an-invoice-from-the-pool-and-match-it-to-a-purchase-order-to-complete-the-invoice-process"></a><span data-ttu-id="e755e-139">Abrir una factura del grupo y conciliarla con un pedido de compra para completar el proceso de la factura</span><span class="sxs-lookup"><span data-stu-id="e755e-139">Open an invoice from the pool and match it to a purchase order to complete the invoice process</span></span>
1. <span data-ttu-id="e755e-140">Vaya a Proveedores > Facturas > Grupo de facturas.</span><span class="sxs-lookup"><span data-stu-id="e755e-140">Go to Accounts payable > Invoices > Invoice pool.</span></span>
2. <span data-ttu-id="e755e-141">Haga clic en Pedido de compra para crear una factura de proveedor a partir de la factura del grupo.</span><span class="sxs-lookup"><span data-stu-id="e755e-141">Click Purchase order to create a vendor invoice from the invoice in the pool.</span></span>
3. <span data-ttu-id="e755e-142">Seleccione la factura que desea revisar.</span><span class="sxs-lookup"><span data-stu-id="e755e-142">Select the invoice that you want to review.</span></span>
4. <span data-ttu-id="e755e-143">Haga clic en Actualizar estado de conciliación para completar la conciliación.</span><span class="sxs-lookup"><span data-stu-id="e755e-143">Click Update match status to complete the matching.</span></span>
5. <span data-ttu-id="e755e-144">En el panel de acciones, haga clic en Opciones.</span><span class="sxs-lookup"><span data-stu-id="e755e-144">On the action pane, click Options.</span></span>
6. <span data-ttu-id="e755e-145">Haga clic en Cambiar vista.</span><span class="sxs-lookup"><span data-stu-id="e755e-145">Click Change view.</span></span>
7. <span data-ttu-id="e755e-146">Haga clic en Vista de cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="e755e-146">Click Grid view.</span></span>
8. <span data-ttu-id="e755e-147">Haga clic en Registrar.</span><span class="sxs-lookup"><span data-stu-id="e755e-147">Click Post.</span></span>
9. <span data-ttu-id="e755e-148">Cierre el formulario.</span><span class="sxs-lookup"><span data-stu-id="e755e-148">Close the form.</span></span>
10. <span data-ttu-id="e755e-149">Vaya a Proveedores > Proveedores > Proveedores.</span><span class="sxs-lookup"><span data-stu-id="e755e-149">Go to Accounts payable > Vendors > Vendors.</span></span>
11. <span data-ttu-id="e755e-150">Seleccione el proveedor que estaba en el pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="e755e-150">Select the vendor that was on the purchase order.</span></span> <span data-ttu-id="e755e-151">Por ejemplo, seleccione el proveedor 1001.</span><span class="sxs-lookup"><span data-stu-id="e755e-151">For example, select vendor 1001.</span></span>
12. <span data-ttu-id="e755e-152">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="e755e-152">In the list, click the link in the selected row.</span></span>
13. <span data-ttu-id="e755e-153">En el panel de acciones, haga clic en Proveedor.</span><span class="sxs-lookup"><span data-stu-id="e755e-153">On the action pane, click Vendor.</span></span>
14. <span data-ttu-id="e755e-154">Haga clic en Transacciones.</span><span class="sxs-lookup"><span data-stu-id="e755e-154">Click Transactions.</span></span>
15. <span data-ttu-id="e755e-155">Seleccione la factura que ha creado.</span><span class="sxs-lookup"><span data-stu-id="e755e-155">Select the invoice that you created.</span></span>
    * <span data-ttu-id="e755e-156">La acumulación de registro de facturas se ha invertido y registrado en la cuenta de gastos apropiada.</span><span class="sxs-lookup"><span data-stu-id="e755e-156">The invoice register accrual was reversed and posted to the appropriate expense account.</span></span>  

