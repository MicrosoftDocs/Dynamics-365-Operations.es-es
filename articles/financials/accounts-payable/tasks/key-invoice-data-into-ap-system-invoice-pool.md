---
title: Introducir datos de factura en el sistema de proveedores mediante un grupo de facturas
description: En este tema se describe cómo utilizar el registro de facturas para crear facturas.
author: abruer
manager: AnnBe
ms.date: 07/31/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f7d72c1d98100d1313109e8b5e55df02e2163174
ms.sourcegitcommit: a368682f9cf3897347d155f1a2d4b33e555cc2c4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/08/2019
ms.locfileid: "1867711"
---
# <a name="key-invoice-data-into-the-ap-system-using-invoice-pool"></a><span data-ttu-id="bd040-103">Introducir datos de factura en el sistema de proveedores mediante un grupo de facturas</span><span class="sxs-lookup"><span data-stu-id="bd040-103">Key invoice data into the AP system using invoice pool</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="bd040-104">En este tema se describe cómo utilizar el registro de facturas para crear facturas.</span><span class="sxs-lookup"><span data-stu-id="bd040-104">This topic describes how to use the invoice register to create invoices.</span></span> <span data-ttu-id="bd040-105">A continuación use el grupo de facturas para que coincida con la factura de un pedido de compra y para finalizar el gasto en la página de la factura de proveedor.</span><span class="sxs-lookup"><span data-stu-id="bd040-105">Then use the invoice pool to match the invoice to a purchase order and finalize the expense in the vendor invoice page.</span></span>


## <a name="create-a-purchase-order"></a><span data-ttu-id="bd040-106">Crear un pedido de compra</span><span class="sxs-lookup"><span data-stu-id="bd040-106">Create a purchase order</span></span>
1. <span data-ttu-id="bd040-107">En el Panel de exploración, vaya a **Módulos > Proveedores > Pedidos de compra > Pedidos de compra**.</span><span class="sxs-lookup"><span data-stu-id="bd040-107">In the navigation pane, go to **Modules > Accounts payable > Purchase orders > Purchase orders**.</span></span>
2. <span data-ttu-id="bd040-108">Seleccione **Nuevo** para crear un pedido de compra nuevo.</span><span class="sxs-lookup"><span data-stu-id="bd040-108">Select **New** to create a purchase order.</span></span>
3. <span data-ttu-id="bd040-109">En el campo **Cuenta de proveedor**, seleccione un proveedor en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="bd040-109">In the **Vendor account** field, select a vendor for the drop-down list.</span></span> <span data-ttu-id="bd040-110">Por ejemplo, seleccione el proveedor **1001**.</span><span class="sxs-lookup"><span data-stu-id="bd040-110">For example, select vendor **1001**.</span></span>
4. <span data-ttu-id="bd040-111">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="bd040-111">Select **OK**.</span></span>
5. <span data-ttu-id="bd040-112">En el campo **Número de artículo**, seleccione el número del artículo de servicios en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="bd040-112">In the **Item number** field, select the services item number in the drop-down list.</span></span> <span data-ttu-id="bd040-113">Por ejemplo, **S0001**.</span><span class="sxs-lookup"><span data-stu-id="bd040-113">For example, select **S0001**.</span></span> <span data-ttu-id="bd040-114">El importe neto es 75,00.</span><span class="sxs-lookup"><span data-stu-id="bd040-114">The net amount is 75.00.</span></span>  <span data-ttu-id="bd040-115">Este es el importe que se espera en la factura.</span><span class="sxs-lookup"><span data-stu-id="bd040-115">That is the amount that we will expect on the invoice.</span></span>  
6. <span data-ttu-id="bd040-116">En el panel de acciones, seleccione **Compra.**</span><span class="sxs-lookup"><span data-stu-id="bd040-116">On the action pane, select **Purchase**.</span></span>
7. <span data-ttu-id="bd040-117">Seleccione **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="bd040-117">Select **Confirm**.</span></span>

## <a name="create-and-post-and-invoice"></a><span data-ttu-id="bd040-118">Crear y registrar una factura</span><span class="sxs-lookup"><span data-stu-id="bd040-118">Create and post and invoice</span></span>
1. <span data-ttu-id="bd040-119">En el panel de exploración, vaya a **Módulos > Proveedores > Facturas > Registro de facturas**.</span><span class="sxs-lookup"><span data-stu-id="bd040-119">In the navigation pane, go to **Modules > Accounts payable > Invoices > Invoice register**.</span></span>
2. <span data-ttu-id="bd040-120">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="bd040-120">Select **New**.</span></span>
3. <span data-ttu-id="bd040-121">Abra la búsqueda para seleccionar el nombre del registro de facturas que desea usar.</span><span class="sxs-lookup"><span data-stu-id="bd040-121">Open the lookup to select the name of the invoice register that you want to use.</span></span>
4. <span data-ttu-id="bd040-122">Seleccione el nombre del registro de facturas que desee usar.</span><span class="sxs-lookup"><span data-stu-id="bd040-122">Select the name of the invoice register that you want to use.</span></span>
5. <span data-ttu-id="bd040-123">Seleccione **Líneas** para abrir el registro y especificar las líneas de gastos.</span><span class="sxs-lookup"><span data-stu-id="bd040-123">Select **Lines** to open the register and enter expense lines.</span></span>
6. <span data-ttu-id="bd040-124">En la búsqueda, seleccione un proveedor.</span><span class="sxs-lookup"><span data-stu-id="bd040-124">In the lookup, select a vendor.</span></span> <span data-ttu-id="bd040-125">Por ejemplo, seleccione el proveedor **1001**.</span><span class="sxs-lookup"><span data-stu-id="bd040-125">For example, select vendor **1001**.</span></span>
7. <span data-ttu-id="bd040-126">En el campo **Factura**, especifique el número de factura.</span><span class="sxs-lookup"><span data-stu-id="bd040-126">In the **Invoice** field, enter the invoice number.</span></span>
8. <span data-ttu-id="bd040-127">En el campo **Descripción**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="bd040-127">In the **Description** field, type a value.</span></span>
9. <span data-ttu-id="bd040-128">En el campo **Crédito**, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="bd040-128">In the **Credit** field, enter a number.</span></span>
10. <span data-ttu-id="bd040-129">En el campo **Pedido de compra**, abra la lista desplegable para seleccionar el pedido de compra que creó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="bd040-129">In the **Purchase order** field, open the drop-down list to select the purchase order that you created earlier.</span></span>
11. <span data-ttu-id="bd040-130">En el campo **Aprobado por**, resalte un aprobador en la lista desplegable y haga clic en **Seleccionar** para seleccione dicho aprobador.</span><span class="sxs-lookup"><span data-stu-id="bd040-130">In the **Approved by** field, highlight an approver in the drop-down list and click **Select** to select that approver.</span></span>
12. <span data-ttu-id="bd040-131">Seleccione **Registrar**.</span><span class="sxs-lookup"><span data-stu-id="bd040-131">Select **Post**.</span></span>

## <a name="open-an-invoice-from-the-pool-and-match-it-to-a-purchase-order-to-complete-the-invoice-process"></a><span data-ttu-id="bd040-132">Abrir una factura del grupo y conciliarla con un pedido de compra para completar el proceso de la factura</span><span class="sxs-lookup"><span data-stu-id="bd040-132">Open an invoice from the pool and match it to a purchase order to complete the invoice process</span></span>
1. <span data-ttu-id="bd040-133">En el panel de exploración, vaya a **Módulos > Proveedores > Facturas > Grupo de facturas**.</span><span class="sxs-lookup"><span data-stu-id="bd040-133">In the navigation pane, go to **Modules > Accounts payable > Invoices > Invoice pool**.</span></span>
2. <span data-ttu-id="bd040-134">Seleccione **Pedido de compra** para crear una factura de proveedor a partir de la factura del grupo.</span><span class="sxs-lookup"><span data-stu-id="bd040-134">Select **Purchase order** to create a vendor invoice from the invoice in the pool.</span></span>
3. <span data-ttu-id="bd040-135">Seleccione la factura que desea revisar.</span><span class="sxs-lookup"><span data-stu-id="bd040-135">Select the invoice that you want to review.</span></span>
4. <span data-ttu-id="bd040-136">Seleccione **Actualizar estado de conciliación** para completar la conciliación.</span><span class="sxs-lookup"><span data-stu-id="bd040-136">Select **Update match status** to complete the matching.</span></span>
5. <span data-ttu-id="bd040-137">En el panel de acciones, seleccione **Opciones**.</span><span class="sxs-lookup"><span data-stu-id="bd040-137">On the action pane, select **Options**.</span></span>
6. <span data-ttu-id="bd040-138">Seleccione **Cambiar vista**.</span><span class="sxs-lookup"><span data-stu-id="bd040-138">Select **Change view**.</span></span>
7. <span data-ttu-id="bd040-139">Seleccione **Vista de cuadrícula**.</span><span class="sxs-lookup"><span data-stu-id="bd040-139">Select **Grid view**.</span></span>
8. <span data-ttu-id="bd040-140">Seleccione **Registrar**.</span><span class="sxs-lookup"><span data-stu-id="bd040-140">Select **Post**.</span></span>
9. <span data-ttu-id="bd040-141">Cierre el formulario.</span><span class="sxs-lookup"><span data-stu-id="bd040-141">Close the form.</span></span>
10. <span data-ttu-id="bd040-142">En el panel de exploración, vaya a **Módulos > Proveedores > Proveedores > Proveedores**.</span><span class="sxs-lookup"><span data-stu-id="bd040-142">In the navigation pane, go to **Modules > Accounts payable > Vendors > Vendors**.</span></span>
11. <span data-ttu-id="bd040-143">Seleccione el proveedor que estaba en el pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="bd040-143">Select the vendor that was on the purchase order.</span></span> <span data-ttu-id="bd040-144">Por ejemplo, seleccione el proveedor **1001**.</span><span class="sxs-lookup"><span data-stu-id="bd040-144">For example, select vendor **1001**.</span></span>
12. <span data-ttu-id="bd040-145">En el panel de acciones, seleccione **Proveedor**.</span><span class="sxs-lookup"><span data-stu-id="bd040-145">On the action pane, select **Vendor**.</span></span>
13. <span data-ttu-id="bd040-146">Seleccione **Transacciones**.</span><span class="sxs-lookup"><span data-stu-id="bd040-146">Select **Transactions**.</span></span>
14. <span data-ttu-id="bd040-147">Seleccione la factura que ha creado.</span><span class="sxs-lookup"><span data-stu-id="bd040-147">Select the invoice that you created.</span></span> <span data-ttu-id="bd040-148">La acumulación de registro de facturas se ha invertido y registrado en la cuenta de gastos apropiada.</span><span class="sxs-lookup"><span data-stu-id="bd040-148">The invoice register accrual was reversed and posted to the appropriate expense account.</span></span>  

