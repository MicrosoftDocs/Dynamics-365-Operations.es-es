---
title: Crear facturas de pedidos de ventas
description: Esta guía de tarea describe la facturación de un pedido de ventas e incluye la combinación de facturas y el procesamiento por lotes.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTableListPage, SalesEditLines,  SysQueryForm, SysRecurrence
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5a57d204c0dcb44cbce7a0cc4d2f00b75b57e219
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1565215"
---
# <a name="create-sales-order-invoices"></a><span data-ttu-id="e967a-103">Crear facturas de pedidos de ventas</span><span class="sxs-lookup"><span data-stu-id="e967a-103">Create sales order invoices</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e967a-104">Esta guía de tarea describe la facturación de un pedido de ventas e incluye la combinación de facturas y el procesamiento por lotes.</span><span class="sxs-lookup"><span data-stu-id="e967a-104">This task guide describes invoicing a sales order, including merging invoices and batch processing.</span></span> <span data-ttu-id="e967a-105">Este procedimiento usa la empresa de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="e967a-105">This procedure uses the USMF demo company.</span></span>


## <a name="create-an-invoice-from-a-sales-order"></a><span data-ttu-id="e967a-106">Crear una factura a partir de un pedido de ventas</span><span class="sxs-lookup"><span data-stu-id="e967a-106">Create an invoice from a sales order</span></span>
1. <span data-ttu-id="e967a-107">Vaya a Clientes > Pedidos > Pedidos de venta enviados pero no facturados.</span><span class="sxs-lookup"><span data-stu-id="e967a-107">Go to Accounts receivable > Orders > Shipped but not invoiced sales orders.</span></span>
2. <span data-ttu-id="e967a-108">Seleccione un pedido de ventas en la lista.</span><span class="sxs-lookup"><span data-stu-id="e967a-108">Select a sales order in the list.</span></span> 
3. <span data-ttu-id="e967a-109">En el panel de acciones, haga clic en Factura.</span><span class="sxs-lookup"><span data-stu-id="e967a-109">On the Action Pane, click Invoice.</span></span>
4. <span data-ttu-id="e967a-110">Haga clic en Factura.</span><span class="sxs-lookup"><span data-stu-id="e967a-110">Click Invoice.</span></span>
    * <span data-ttu-id="e967a-111">Tenga en cuenta que este pedido de ventas tiene varios albaranes asociados con él.</span><span class="sxs-lookup"><span data-stu-id="e967a-111">Note that this sales order has multiple packing slips associated with it.</span></span> <span data-ttu-id="e967a-112">Solo mostrará la palabra <multiple> en lugar del número de albarán.</span><span class="sxs-lookup"><span data-stu-id="e967a-112">It will only show the word <multiple> instead of the packing slip number.</span></span>  
5. <span data-ttu-id="e967a-113">Expanda la sección Parámetros.</span><span class="sxs-lookup"><span data-stu-id="e967a-113">Expand the Parameters section.</span></span>
    * <span data-ttu-id="e967a-114">El registro se debe establecer en Sí para registrar la factura.</span><span class="sxs-lookup"><span data-stu-id="e967a-114">Posting must be set to Yes to post the invoice.</span></span> <span data-ttu-id="e967a-115">También puede desactivar el registro y solo imprimir la factura.</span><span class="sxs-lookup"><span data-stu-id="e967a-115">You can also turn off posting and just print the invoice.</span></span> <span data-ttu-id="e967a-116">Sin embargo, puede lograr el mismo resultado creando una factura de proforma en lugar de una factura.</span><span class="sxs-lookup"><span data-stu-id="e967a-116">However, you can accomplish the same result by creating a proforma invoice instead of an invoice.</span></span>  
    * <span data-ttu-id="e967a-117">Esta opción es la que se usa para trabajos por lotes.</span><span class="sxs-lookup"><span data-stu-id="e967a-117">This option is used for batch jobs.</span></span> <span data-ttu-id="e967a-118">El trabajo por lotes se ejecuta al registrar pedidos de ventas.</span><span class="sxs-lookup"><span data-stu-id="e967a-118">The query is run when the batch job is run.</span></span>    
6. <span data-ttu-id="e967a-119">En el campo Imprimir, seleccione "Después de".</span><span class="sxs-lookup"><span data-stu-id="e967a-119">In the Print field, select 'After'.</span></span>
7. <span data-ttu-id="e967a-120">Seleccione Sí para Imprimir factura.</span><span class="sxs-lookup"><span data-stu-id="e967a-120">Select Yes for Print invoice.</span></span>
    * <span data-ttu-id="e967a-121">La gestión de impresión puede imprimir varias copias de la factura y también enviar la factura por correo electrónico como archivo PDF.</span><span class="sxs-lookup"><span data-stu-id="e967a-121">Print management can print  multiple copies of the invoice and also send the invoice via email as a PDF file.</span></span>  
8. <span data-ttu-id="e967a-122">En el campo Imprimir costes, seleccione "Resumir".</span><span class="sxs-lookup"><span data-stu-id="e967a-122">In the Print charges field, select 'Summarize'.</span></span>
9. <span data-ttu-id="e967a-123">En el campo Comprobar límite de crédito, seleccione "Saldo".</span><span class="sxs-lookup"><span data-stu-id="e967a-123">In the Check credit limit field, select 'Balance'.</span></span>
10. <span data-ttu-id="e967a-124">Haga clic en Cancelar.</span><span class="sxs-lookup"><span data-stu-id="e967a-124">Click Cancel.</span></span>

## <a name="combine-orders-into-a-single-invoice"></a><span data-ttu-id="e967a-125">Combinar pedidos en una única factura</span><span class="sxs-lookup"><span data-stu-id="e967a-125">Combine orders into a single invoice</span></span>
1. <span data-ttu-id="e967a-126">Vaya a Clientes > Pedidos > Todos los pedidos de venta.</span><span class="sxs-lookup"><span data-stu-id="e967a-126">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="e967a-127">Localice a un cliente que tenga varias facturas abiertas.</span><span class="sxs-lookup"><span data-stu-id="e967a-127">Locate a customer that has multiple invoices open.</span></span>
3. <span data-ttu-id="e967a-128">Seleccione un pedido de ventas abierto.</span><span class="sxs-lookup"><span data-stu-id="e967a-128">Select an open sales order.</span></span>
4. <span data-ttu-id="e967a-129">Seleccione otro pedido de ventas abierto del mismo cliente.</span><span class="sxs-lookup"><span data-stu-id="e967a-129">Select another open sales order for the same customer.</span></span>
5. <span data-ttu-id="e967a-130">En el panel de acciones, haga clic en Factura.</span><span class="sxs-lookup"><span data-stu-id="e967a-130">On the Action Pane, click Invoice.</span></span>
6. <span data-ttu-id="e967a-131">Haga clic en Factura.</span><span class="sxs-lookup"><span data-stu-id="e967a-131">Click Invoice.</span></span>
7. <span data-ttu-id="e967a-132">Expanda la sección Parámetros.</span><span class="sxs-lookup"><span data-stu-id="e967a-132">Expand the Parameters section.</span></span>
8. <span data-ttu-id="e967a-133">En el campo Cantidad, seleccione 'Todo'.</span><span class="sxs-lookup"><span data-stu-id="e967a-133">In the Quantity field, select 'All'.</span></span>
    * <span data-ttu-id="e967a-134">Tenga en cuenta que hay dos facturas que aparecen en la sección de descripción.</span><span class="sxs-lookup"><span data-stu-id="e967a-134">Note that there are two invoices listed in the overview section.</span></span> <span data-ttu-id="e967a-135">Ahora vamos a combinarlas en una única factura.</span><span class="sxs-lookup"><span data-stu-id="e967a-135">Now let's merge them into a single invoice.</span></span>  
9. <span data-ttu-id="e967a-136">En el campo Actualización conjunta para, seleccione "Cuenta de facturación".</span><span class="sxs-lookup"><span data-stu-id="e967a-136">In the Summary update for field, select 'Invoice account'.</span></span>
10. <span data-ttu-id="e967a-137">Haga clic en Organizar para combinar los pedidos de ventas en una única factura.</span><span class="sxs-lookup"><span data-stu-id="e967a-137">Click Arrange to merge the sales orders into a single invoice.</span></span>
    * <span data-ttu-id="e967a-138">Los dos pedidos de ventas se combinan ahora en una única factura.</span><span class="sxs-lookup"><span data-stu-id="e967a-138">The two sales orders are now merged into a single invoice.</span></span>   
11. <span data-ttu-id="e967a-139">Haga clic en Cancelar.</span><span class="sxs-lookup"><span data-stu-id="e967a-139">Click Cancel.</span></span>
12. <span data-ttu-id="e967a-140">Haga clic en Sí.</span><span class="sxs-lookup"><span data-stu-id="e967a-140">Click Yes.</span></span>

## <a name="post-invoices-in-a-batch"></a><span data-ttu-id="e967a-141">Registrar facturas en un lote</span><span class="sxs-lookup"><span data-stu-id="e967a-141">Post invoices in a batch</span></span>
1. <span data-ttu-id="e967a-142">Vaya a Clientes > Facturas > Facturación por lotes > Factura.</span><span class="sxs-lookup"><span data-stu-id="e967a-142">Go to Accounts receivable > Invoices > Batch invoicing > Invoice.</span></span>
2. <span data-ttu-id="e967a-143">Haga clic en Seleccionar.</span><span class="sxs-lookup"><span data-stu-id="e967a-143">Click Select.</span></span>
3. <span data-ttu-id="e967a-144">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="e967a-144">Click OK.</span></span>
4. <span data-ttu-id="e967a-145">Haga clic en Lote.</span><span class="sxs-lookup"><span data-stu-id="e967a-145">Click Batch.</span></span>
5. <span data-ttu-id="e967a-146">Haga clic en Sí para activar el procesamiento por lotes.</span><span class="sxs-lookup"><span data-stu-id="e967a-146">Click on Yes to turn on batch processing.</span></span>
6. <span data-ttu-id="e967a-147">Haga clic en Periodicidad.</span><span class="sxs-lookup"><span data-stu-id="e967a-147">Click Recurrence.</span></span>
7. <span data-ttu-id="e967a-148">Seleccione Días</span><span class="sxs-lookup"><span data-stu-id="e967a-148">Select Days</span></span>
8. <span data-ttu-id="e967a-149">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="e967a-149">Click OK.</span></span>
9. <span data-ttu-id="e967a-150">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="e967a-150">Click OK.</span></span>
10. <span data-ttu-id="e967a-151">Haga clic en Cancelar.</span><span class="sxs-lookup"><span data-stu-id="e967a-151">Click Cancel.</span></span>
11. <span data-ttu-id="e967a-152">Haga clic en Sí.</span><span class="sxs-lookup"><span data-stu-id="e967a-152">Click Yes.</span></span>

