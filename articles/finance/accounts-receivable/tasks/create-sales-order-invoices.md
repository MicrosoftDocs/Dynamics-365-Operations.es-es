---
title: Crear facturas de pedidos de ventas
description: Esta guía de tarea describe la facturación de un pedido de ventas e incluye la combinación de facturas y el procesamiento por lotes.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 06/25/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTableListPage, SalesEditLines,  SysQueryForm, SysRecurrence
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2a41524c773284812aa6eebddcd832c78bd29166
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "2179822"
---
# <a name="create-sales-order-invoices"></a><span data-ttu-id="8cd17-103">Crear facturas de pedidos de ventas</span><span class="sxs-lookup"><span data-stu-id="8cd17-103">Create sales order invoices</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="8cd17-104">Esta guía de tarea describe la facturación de un pedido de ventas e incluye la combinación de facturas y el procesamiento por lotes.</span><span class="sxs-lookup"><span data-stu-id="8cd17-104">This task guide describes invoicing a sales order, including merging invoices and batch processing.</span></span> <span data-ttu-id="8cd17-105">Este procedimiento usa la empresa de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="8cd17-105">This procedure uses the USMF demo company.</span></span>


## <a name="create-an-invoice-from-a-sales-order"></a><span data-ttu-id="8cd17-106">Crear una factura a partir de un pedido de ventas</span><span class="sxs-lookup"><span data-stu-id="8cd17-106">Create an invoice from a sales order</span></span>
1. <span data-ttu-id="8cd17-107">Vaya a **Panel de navegación > Módulos > Clientes > Pedidos > Pedidos de ventas enviados pero no facturados**.</span><span class="sxs-lookup"><span data-stu-id="8cd17-107">Go to **Navigation pane > Modules > Accounts receivable > Orders > Shipped but not invoiced sales orders**.</span></span>
2. <span data-ttu-id="8cd17-108">Seleccione un pedido de ventas en la lista.</span><span class="sxs-lookup"><span data-stu-id="8cd17-108">Select a sales order in the list.</span></span> 
3. <span data-ttu-id="8cd17-109">En el **panel de acciones**, haga clic en **Factura > Generar > Factura**.</span><span class="sxs-lookup"><span data-stu-id="8cd17-109">On the **Action Pane**, click **Invoice > Generate > Invoice**.</span></span> <span data-ttu-id="8cd17-110">Tenga en cuenta que este pedido de ventas tiene varios albaranes asociados con él.</span><span class="sxs-lookup"><span data-stu-id="8cd17-110">Note that this sales order has multiple packing slips associated with it.</span></span> <span data-ttu-id="8cd17-111">Solo mostrará la palabra <multiple> en lugar del número de albarán.</span><span class="sxs-lookup"><span data-stu-id="8cd17-111">It will only show the word <multiple> instead of the packing slip number.</span></span>  
4. <span data-ttu-id="8cd17-112">Expanda la sección **Parámetros**.</span><span class="sxs-lookup"><span data-stu-id="8cd17-112">Expand the **Parameters** section.</span></span>
    - <span data-ttu-id="8cd17-113">El registro se debe establecer en Sí para registrar la factura.</span><span class="sxs-lookup"><span data-stu-id="8cd17-113">Posting must be set to Yes to post the invoice.</span></span> <span data-ttu-id="8cd17-114">También puede desactivar el registro y solo imprimir la factura.</span><span class="sxs-lookup"><span data-stu-id="8cd17-114">You can also turn off posting and just print the invoice.</span></span> <span data-ttu-id="8cd17-115">Sin embargo, puede lograr el mismo resultado creando una factura de proforma en lugar de una factura.</span><span class="sxs-lookup"><span data-stu-id="8cd17-115">However, you can accomplish the same result by creating a proforma invoice instead of an invoice.</span></span>  
    - <span data-ttu-id="8cd17-116">Esta opción es la que se usa para trabajos por lotes.</span><span class="sxs-lookup"><span data-stu-id="8cd17-116">This option is used for batch jobs.</span></span> <span data-ttu-id="8cd17-117">El trabajo por lotes se ejecuta al registrar pedidos de ventas.</span><span class="sxs-lookup"><span data-stu-id="8cd17-117">The query is run when the batch job is run.</span></span>
5. <span data-ttu-id="8cd17-118">En el campo **Imprimir**, seleccione "Después de".</span><span class="sxs-lookup"><span data-stu-id="8cd17-118">In the **Print** field, select 'After'.</span></span>
6. <span data-ttu-id="8cd17-119">Seleccione **Sí** para **Imprimir factura**.</span><span class="sxs-lookup"><span data-stu-id="8cd17-119">Select **Yes** for **Print invoice**.</span></span> <span data-ttu-id="8cd17-120">La gestión de impresión puede imprimir varias copias de la factura y también enviar la factura por correo electrónico como archivo PDF.</span><span class="sxs-lookup"><span data-stu-id="8cd17-120">Print management can print  multiple copies of the invoice and also send the invoice via email as a PDF file.</span></span>  
7. <span data-ttu-id="8cd17-121">En el campo **Imprimir costes**, seleccione "Resumir".</span><span class="sxs-lookup"><span data-stu-id="8cd17-121">In the **Print charges** field, select 'Summarize'.</span></span>
8. <span data-ttu-id="8cd17-122">En el campo **Comprobar límite de crédito**, seleccione "Saldo".</span><span class="sxs-lookup"><span data-stu-id="8cd17-122">In the **Check credit limit** field, select 'Balance'.</span></span>
9. <span data-ttu-id="8cd17-123">Haga clic en **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="8cd17-123">Click **Cancel**.</span></span>

## <a name="combine-orders-into-a-single-invoice"></a><span data-ttu-id="8cd17-124">Combinar pedidos en una única factura</span><span class="sxs-lookup"><span data-stu-id="8cd17-124">Combine orders into a single invoice</span></span>
1. <span data-ttu-id="8cd17-125">Vaya a **panel de navegación > Módulos > Clientes > Pedidos > Todos los pedidos de vents**.</span><span class="sxs-lookup"><span data-stu-id="8cd17-125">Go to **Navigation pane > Modules > Accounts receivable > Orders > All sales orders**.</span></span>
2. <span data-ttu-id="8cd17-126">Localice a un cliente que tenga varias facturas abiertas.</span><span class="sxs-lookup"><span data-stu-id="8cd17-126">Locate a customer that has multiple invoices open.</span></span>
3. <span data-ttu-id="8cd17-127">Seleccione varios pedidos de ventas abiertos del mismo cliente.</span><span class="sxs-lookup"><span data-stu-id="8cd17-127">Select multiple open sales orders from the same customer.</span></span>
4. <span data-ttu-id="8cd17-128">En el **panel de acciones**, haga clic en **Factura > Generar > Factura**.</span><span class="sxs-lookup"><span data-stu-id="8cd17-128">On the **Action Pane**, click **Invoice > Generate > Invoice**.</span></span>
5. <span data-ttu-id="8cd17-129">Expanda la sección **Parámetros**.</span><span class="sxs-lookup"><span data-stu-id="8cd17-129">Expand the **Parameters** section.</span></span>
6. <span data-ttu-id="8cd17-130">En el campo **Cantidad**, seleccione "Todo".</span><span class="sxs-lookup"><span data-stu-id="8cd17-130">In the **Quantity** field, select 'All'.</span></span> <span data-ttu-id="8cd17-131">Tenga en cuenta que hay dos facturas que aparecen en la sección de descripción.</span><span class="sxs-lookup"><span data-stu-id="8cd17-131">Note that there are two invoices listed in the overview section.</span></span> <span data-ttu-id="8cd17-132">Ahora vamos a combinarlas en una única factura.</span><span class="sxs-lookup"><span data-stu-id="8cd17-132">Now let's merge them into a single invoice.</span></span>  
7. <span data-ttu-id="8cd17-133">En el campo **Actualización conjunta para**, seleccione "Cuenta de facturación".</span><span class="sxs-lookup"><span data-stu-id="8cd17-133">In the **Summary update for** field, select 'Invoice account'.</span></span>
8. <span data-ttu-id="8cd17-134">Haga clic en **Organizar** para combinar los pedidos de ventas en una única factura.</span><span class="sxs-lookup"><span data-stu-id="8cd17-134">Click **Arrange** to merge the sales orders into a single invoice.</span></span> <span data-ttu-id="8cd17-135">Los dos pedidos de ventas se combinan ahora en una única factura.</span><span class="sxs-lookup"><span data-stu-id="8cd17-135">The two sales orders are now merged into a single invoice.</span></span>   
9. <span data-ttu-id="8cd17-136">Haga clic en **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="8cd17-136">Click **Cancel**.</span></span>
10. <span data-ttu-id="8cd17-137">Haga clic en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="8cd17-137">Click **Yes**.</span></span>

## <a name="post-invoices-in-a-batch"></a><span data-ttu-id="8cd17-138">Registrar facturas en un lote</span><span class="sxs-lookup"><span data-stu-id="8cd17-138">Post invoices in a batch</span></span>
1. <span data-ttu-id="8cd17-139">Vaya a **Panel de exploración >Módulos > Clientes > Facturas > Facturación por lotes > Factura de clientes abiertas**.</span><span class="sxs-lookup"><span data-stu-id="8cd17-139">Go to **Navigation pane > Modules > Accounts receivable > Invoices > Batch invoicing > Invoice**.</span></span>
2. <span data-ttu-id="8cd17-140">Haga clic en **Seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="8cd17-140">Click **Select**.</span></span>
3. <span data-ttu-id="8cd17-141">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8cd17-141">Click **OK**.</span></span>
4. <span data-ttu-id="8cd17-142">Haga clic en **Lote**.</span><span class="sxs-lookup"><span data-stu-id="8cd17-142">Click **Batch**.</span></span>
5. <span data-ttu-id="8cd17-143">Seleccione **Sí** para el **procesamiento por lotes**.</span><span class="sxs-lookup"><span data-stu-id="8cd17-143">Select **Yes** in **Batch processing**.</span></span>
6. <span data-ttu-id="8cd17-144">Haga clic en **Periodicidad**.</span><span class="sxs-lookup"><span data-stu-id="8cd17-144">Click **Recurrence**.</span></span>
7. <span data-ttu-id="8cd17-145">Seleccione **Días**.</span><span class="sxs-lookup"><span data-stu-id="8cd17-145">Select **Days**.</span></span>
8. <span data-ttu-id="8cd17-146">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8cd17-146">Click **OK**.</span></span>
9. <span data-ttu-id="8cd17-147">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8cd17-147">Click **OK**.</span></span>
10. <span data-ttu-id="8cd17-148">Haga clic en **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="8cd17-148">Click **Cancel**.</span></span>
11. <span data-ttu-id="8cd17-149">Haga clic en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="8cd17-149">Click **Yes**.</span></span>

