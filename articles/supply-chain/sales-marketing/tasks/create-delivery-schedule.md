---
title: Creación de una programación de entrega
description: En este procedimiento se demuestra cómo crear una programación de entrega para un pedido de ventas.
author: omulvad
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, SalesDeliverySchedule, SalesEditLines,  SrsReportViewerForm
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7341ec21a89bf952e2fd21e9bebf7de65a1b2648
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4436660"
---
# <a name="create-delivery-schedule"></a><span data-ttu-id="bba6a-103">Creación de una programación de entrega</span><span class="sxs-lookup"><span data-stu-id="bba6a-103">Create delivery schedule</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="bba6a-104">En este procedimiento se demuestra cómo crear una programación de entrega para un pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="bba6a-104">This procedure demonstrates how to create a delivery schedule for a sales order.</span></span> <span data-ttu-id="bba6a-105">Se usa una programación de entrega cuando se solicita que una cantidad de un pedido o un presupuesto se entregue en varios envíos.</span><span class="sxs-lookup"><span data-stu-id="bba6a-105">A delivery schedule is used when a quantity on an order or a quotation is requested to be delivered in multiple shipments.</span></span> <span data-ttu-id="bba6a-106">Puede ejecutar este procedimiento con los datos de la empresa de demostración USMF o utilizar sus propios datos.</span><span class="sxs-lookup"><span data-stu-id="bba6a-106">You can run this procedure in demo data company USMF or on your own data.</span></span>


## <a name="create-delivery-schedule"></a><span data-ttu-id="bba6a-107">Creación de una programación de entrega</span><span class="sxs-lookup"><span data-stu-id="bba6a-107">Create delivery schedule</span></span>
1. <span data-ttu-id="bba6a-108">Vaya a Todos los pedidos de ventas.</span><span class="sxs-lookup"><span data-stu-id="bba6a-108">Go to All sales orders.</span></span>
2. <span data-ttu-id="bba6a-109">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="bba6a-109">Click New.</span></span>
3. <span data-ttu-id="bba6a-110">En el campo Cuenta de cliente, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="bba6a-110">In the Customer account field, enter or select a value.</span></span>
4. <span data-ttu-id="bba6a-111">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="bba6a-111">Click OK.</span></span>
5. <span data-ttu-id="bba6a-112">En el campo Número de artículo, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="bba6a-112">In the Item number field, enter or select a value.</span></span>
6. <span data-ttu-id="bba6a-113">En el campo Cantidad, especifique un número mayor que 1.</span><span class="sxs-lookup"><span data-stu-id="bba6a-113">In the Quantity field, enter a number that is bigger than 1.</span></span>
7. <span data-ttu-id="bba6a-114">Haga clic en Línea de pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="bba6a-114">Click Sales order line.</span></span>
8. <span data-ttu-id="bba6a-115">Haga clic en Programación de entrega.</span><span class="sxs-lookup"><span data-stu-id="bba6a-115">Click Delivery schedule.</span></span>
    * <span data-ttu-id="bba6a-116">La página Programación de entrega es el lugar en el que puede especificar el número de envíos en los que la cantidad total de la línea de pedido se entregará al cliente.</span><span class="sxs-lookup"><span data-stu-id="bba6a-116">The Delivery schedule page is the place where you can specify the number of shipments in which the total quantity of the order line will be delivered to the customer.</span></span>    
    * <span data-ttu-id="bba6a-117">De forma predeterminada, el sistema copia la cantidad total y otros detalles de entrega de la línea de ventas original en la primera línea de la programación de entrega.</span><span class="sxs-lookup"><span data-stu-id="bba6a-117">By default, the system copies the total quantity and other delivery details of the original sales line into the first delivery schedule line.</span></span> <span data-ttu-id="bba6a-118">En este ejemplo, crearemos una programación para dos envíos, con la fecha del segundo envío una semana después que la del primero.</span><span class="sxs-lookup"><span data-stu-id="bba6a-118">In this example, we'll create a schedule for two shipments, with the second shipment's date offset by a week from the first one.</span></span>  
9. <span data-ttu-id="bba6a-119">En el campo Cantidad, especifique un número que forme parte de la cantidad total.</span><span class="sxs-lookup"><span data-stu-id="bba6a-119">In the Quantity field, enter a number that is part of the total quantity.</span></span>
10. <span data-ttu-id="bba6a-120">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="bba6a-120">Click New.</span></span>
11. <span data-ttu-id="bba6a-121">En el campo Cantidad, escriba la cantidad restante.</span><span class="sxs-lookup"><span data-stu-id="bba6a-121">In the Quantity field, enter the remaining quantity.</span></span>
12. <span data-ttu-id="bba6a-122">En el campo Fecha de envío solicitada, especifique una fecha que sea una semana después de la fecha de la primera línea de entrega.</span><span class="sxs-lookup"><span data-stu-id="bba6a-122">In the Requested ship date field, enter a date a date that is one week ahead from the date of the first delivery line.</span></span>
    * <span data-ttu-id="bba6a-123">Las dos opciones de la ficha desplegable Conversión de gastos controlan cómo desea que los gastos se distribuyan entre las líneas de la programación de entrega, una vez que se han asignado a la línea de pedido original.</span><span class="sxs-lookup"><span data-stu-id="bba6a-123">The two options on the Charges conversion FastTab control how you want the charges to be distributed across the delivery schedule lines, once they've been assigned to the original order line.</span></span> <span data-ttu-id="bba6a-124">Si selecciona Importes brutos de copia, el mismo importe de gasto se copia en cada línea.</span><span class="sxs-lookup"><span data-stu-id="bba6a-124">If you select Copy gross amounts, the same charge amount is copied to each line.</span></span> <span data-ttu-id="bba6a-125">La opción Asignar a líneas de entrega divide el gasto por igual entre las líneas de entrega.</span><span class="sxs-lookup"><span data-stu-id="bba6a-125">The Allocate to delivery lines option divides the charge equally across the delivery lines.</span></span>  
    * <span data-ttu-id="bba6a-126">Solo se pueden dividir los gastos fijos, mientras que los gastos variables se copiarán en las líneas.</span><span class="sxs-lookup"><span data-stu-id="bba6a-126">Only fixed charges can be divided, whereas variable charges will still be copied to the lines.</span></span>  
13. <span data-ttu-id="bba6a-127">Mueva el cursor fuera de la segunda línea de entrega para actualizar la página.</span><span class="sxs-lookup"><span data-stu-id="bba6a-127">Move the cursor away from the second delivery line to update the page.</span></span>
    * <span data-ttu-id="bba6a-128">Puede realizar un seguimiento de la cantidad total que está asignada a las líneas de la programación de entrega si mira los campos Total y Restante.</span><span class="sxs-lookup"><span data-stu-id="bba6a-128">You can keep track of the total quantity that's allocated to the delivery schedule lines by looking at the Total and Remaining fields.</span></span> <span data-ttu-id="bba6a-129">Cuando la cantidad restante es cero, la cantidad completa de la línea original se ha asignado a la programación.</span><span class="sxs-lookup"><span data-stu-id="bba6a-129">When the remaining quantity is zero, the full quantity from the original line has been allocated to the schedule.</span></span>   
14. <span data-ttu-id="bba6a-130">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="bba6a-130">Click OK.</span></span>
    * <span data-ttu-id="bba6a-131">La programación de entrega se ha copiado a las líneas de pedido.</span><span class="sxs-lookup"><span data-stu-id="bba6a-131">The delivery schedule has now been copied to the order lines.</span></span>   
    * <span data-ttu-id="bba6a-132">La línea de pedido original, conocida como línea comercial, se ha convertido en una línea de pedido con varias entregas.</span><span class="sxs-lookup"><span data-stu-id="bba6a-132">The original order line, referred to as a Commercial line, has been converted to an Order line with multiple deliveries.</span></span> <span data-ttu-id="bba6a-133">Se marca con un icono distinto y actúa como encabezado de las líneas de entrega.</span><span class="sxs-lookup"><span data-stu-id="bba6a-133">It is marked with a distinct icon and acts as a header for the delivery lines.</span></span>  
    * <span data-ttu-id="bba6a-134">Las dos líneas nuevas, designadas líneas de entrega, forman una programación de entrega.</span><span class="sxs-lookup"><span data-stu-id="bba6a-134">The two new lines, referred to as delivery lines, make up one delivery schedule.</span></span> <span data-ttu-id="bba6a-135">El pedido se procesará con dichas líneas y no con la línea original.</span><span class="sxs-lookup"><span data-stu-id="bba6a-135">The order will be processed against these lines and not the original line.</span></span> <span data-ttu-id="bba6a-136">Si los documentos como resguardos de confirmación, listas de selección, albaranes o facturas se imprimen, solo se muestran las líneas de entrega.</span><span class="sxs-lookup"><span data-stu-id="bba6a-136">If documents such as confirmation slips, picking lists, packing slips, or invoices are printed, only the delivery lines are shown.</span></span>   
    * <span data-ttu-id="bba6a-137">Las líneas de entrega pueden tener diferentes fechas de entrega, cantidades, modos de entrega y dimensiones de almacenamiento como el sitio y el almacén.</span><span class="sxs-lookup"><span data-stu-id="bba6a-137">The delivery lines can have different delivery dates, quantities, modes of delivery, and storage dimensions, such as site and warehouse.</span></span> <span data-ttu-id="bba6a-138">Sin embargo, las dimensiones del producto deben coincidir siempre con los que se encuentran en la línea comercial y no se pueden modificar.</span><span class="sxs-lookup"><span data-stu-id="bba6a-138">However, the product dimensions must always match the ones on the commercial line and can't be changed.</span></span>  
15. <span data-ttu-id="bba6a-139">En el campo Cantidad, especifique un número mayor que el actual.</span><span class="sxs-lookup"><span data-stu-id="bba6a-139">In the Quantity field, enter a number that's bigger than the current one.</span></span>
16. <span data-ttu-id="bba6a-140">Seleccione la línea comercial para ver el efecto del recálculo de la cantidad.</span><span class="sxs-lookup"><span data-stu-id="bba6a-140">Select the commercial line to see the effect of the quantity recalculation.</span></span>
17. <span data-ttu-id="bba6a-141">En el panel de acciones, haga clic en Seleccionar y empaquetar.</span><span class="sxs-lookup"><span data-stu-id="bba6a-141">On the Action Pane, click Pick and pack.</span></span>
18. <span data-ttu-id="bba6a-142">Haga clic en Registrar albarán.</span><span class="sxs-lookup"><span data-stu-id="bba6a-142">Click Post packing slip.</span></span>
19. <span data-ttu-id="bba6a-143">Expanda la sección Parámetros.</span><span class="sxs-lookup"><span data-stu-id="bba6a-143">Expand the Parameters section.</span></span>
20. <span data-ttu-id="bba6a-144">En el campo Cantidad, seleccione 'Todo'.</span><span class="sxs-lookup"><span data-stu-id="bba6a-144">In the Quantity field, select 'All'.</span></span>
    * <span data-ttu-id="bba6a-145">Tenga en cuenta que el albarán se creará para las dos líneas de la programación de entrega y no para la línea de pedido original.</span><span class="sxs-lookup"><span data-stu-id="bba6a-145">Note that the packing slip will be created for the two delivery schedule lines and not the original order line.</span></span>  
21. <span data-ttu-id="bba6a-146">Seleccione Sí en el campo Imprimir albarán.</span><span class="sxs-lookup"><span data-stu-id="bba6a-146">Select Yes in the Print packing slip field.</span></span>
22. <span data-ttu-id="bba6a-147">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="bba6a-147">Click OK.</span></span>
23. <span data-ttu-id="bba6a-148">Haga clic en Sí.</span><span class="sxs-lookup"><span data-stu-id="bba6a-148">Click Yes.</span></span>
24. <span data-ttu-id="bba6a-149">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="bba6a-149">Close the page.</span></span>
