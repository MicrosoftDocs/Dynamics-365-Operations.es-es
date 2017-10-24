--- 
title: Enviar pedidos de ventas sin almacenamiento
description: "Esta guía muestra cómo actualizar un pedido de ventas cuando los productos se envían al cliente."
author: omulvad
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 3f1b9dd4b99bcbcc6cfbc5cfd8e3271fa80c628c
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="ship-sales-orders-without-warehousing"></a><span data-ttu-id="d91f1-103">Enviar pedidos de ventas sin almacenamiento</span><span class="sxs-lookup"><span data-stu-id="d91f1-103">Ship sales orders without warehousing</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d91f1-104">Esta guía muestra cómo actualizar un pedido de ventas cuando los productos se envían al cliente.</span><span class="sxs-lookup"><span data-stu-id="d91f1-104">This guide demonstrates how to update a sales order when products are shipped to the customer.</span></span> <span data-ttu-id="d91f1-105">La guía es aplicable al flujo de cumplimiento que no se ha configurado para la gestión de almacenes (ni el almacenamiento básico o avanzado) y, por tanto. no requiere que se registre la selección del producto antes del envío.</span><span class="sxs-lookup"><span data-stu-id="d91f1-105">The guide is applicable to the fulfillment flow that is not set up for warehouse management (neither basic or advanced warehousing), and therefore does not require product picking to be registered before shipment.</span></span> <span data-ttu-id="d91f1-106">Puede ejecutar este procedimiento en sus propios datos o en la empresa de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="d91f1-106">You can run this procedure on your own data or in demo data company USMF.</span></span> <span data-ttu-id="d91f1-107">En ambos casos, antes de comenzar esta tarea, cree un pedido de ventas para un producto del inventario con una cantidad de mayor de 1.</span><span class="sxs-lookup"><span data-stu-id="d91f1-107">In both cases, before you start this task, create a sales order for an inventoried product with a quantity of greater than 1.</span></span> <span data-ttu-id="d91f1-108">Para evitar un error de registro, necesita comprobar que la cantidad de producto disponible en el sitio y el almacén que ha seleccionado para pedir cubre la cantidad de pedido.</span><span class="sxs-lookup"><span data-stu-id="d91f1-108">To avoid a posting error, you need to check that the product's on-hand quantity in the site and warehouse that you’ve selected on the order covers the order quantity.</span></span>


## <a name="post-packing-slip-for-an-order"></a><span data-ttu-id="d91f1-109">Registrar albarán para un pedido</span><span class="sxs-lookup"><span data-stu-id="d91f1-109">Post packing slip for an order</span></span>
1. <span data-ttu-id="d91f1-110">Vaya a Ventas y marketing > Pedidos de ventas > Todos los pedidos de ventas.</span><span class="sxs-lookup"><span data-stu-id="d91f1-110">Go to Sales and marketing > Sales orders > All sales orders.</span></span>
2. <span data-ttu-id="d91f1-111">En la lista, busque y seleccione el pedido que ha creado para esta tarea.</span><span class="sxs-lookup"><span data-stu-id="d91f1-111">In the list, find and select the order you have created for this task.</span></span>
3. <span data-ttu-id="d91f1-112">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="d91f1-112">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="d91f1-113">En el panel de acciones, haga clic en Seleccionar y empaquetar.</span><span class="sxs-lookup"><span data-stu-id="d91f1-113">On the Action Pane, click Pick and pack.</span></span>
5. <span data-ttu-id="d91f1-114">Haga clic en Registrar albarán.</span><span class="sxs-lookup"><span data-stu-id="d91f1-114">Click Post packing slip.</span></span>
6. <span data-ttu-id="d91f1-115">Expanda o contraiga la sección Parámetros.</span><span class="sxs-lookup"><span data-stu-id="d91f1-115">Expand or collapse the Parameters section.</span></span>
7. <span data-ttu-id="d91f1-116">En el campo Cantidad, seleccione 'Todo'.</span><span class="sxs-lookup"><span data-stu-id="d91f1-116">In the Quantity field, select 'All'.</span></span>
    * <span data-ttu-id="d91f1-117">Otras opciones incluyen Entregar ahora y Seleccionado.</span><span class="sxs-lookup"><span data-stu-id="d91f1-117">Other options include Deliver now and Picked.</span></span> <span data-ttu-id="d91f1-118">Si la línea de pedido se va a enviar parcialmente y el campo Entregar ahora de la línea de pedido contiene una cantidad, seleccionaría Entregar ahora.</span><span class="sxs-lookup"><span data-stu-id="d91f1-118">If the order line is to be shipped partially and the Deliver now field on the order line contains a quantity, you would select Deliver now.</span></span> <span data-ttu-id="d91f1-119">Si el flujo de cumplimiento de la organización incluye la selección como un proceso independiente que se administra por una lista de selección y se registra con ella, seleccionaría Seleccionado.</span><span class="sxs-lookup"><span data-stu-id="d91f1-119">If your organization's fulfillment flow includes picking as a separate process that is managed by and registered with a picking list, you would select Picked.</span></span>  
    * <span data-ttu-id="d91f1-120">Compruebe que la opción Registro está establecida en Sí.</span><span class="sxs-lookup"><span data-stu-id="d91f1-120">Check that the Posting option is set to Yes.</span></span>  
8. <span data-ttu-id="d91f1-121">Establezca la opción Imprimir albarán en Sí.</span><span class="sxs-lookup"><span data-stu-id="d91f1-121">Set the Print packing slip option to Yes.</span></span>
    * <span data-ttu-id="d91f1-122">La ficha Visión general contiene una lista de albaranes que se generarán en este registro.</span><span class="sxs-lookup"><span data-stu-id="d91f1-122">The Overview tab contains a list of packing slips to be generated in this posting.</span></span> <span data-ttu-id="d91f1-123">Si va a enviar un pedido individual, habrá normalmente un albarán.</span><span class="sxs-lookup"><span data-stu-id="d91f1-123">If you are shipping an individual order, there will typically be one packing slip.</span></span> <span data-ttu-id="d91f1-124">Sin embargo, si las líneas del pedido se van a enviar desde distintos sitios, el registro se dividirá automáticamente en el número adecuado de documentos.</span><span class="sxs-lookup"><span data-stu-id="d91f1-124">However, if that order's lines are to be shipped from different sites, posting will automatically be split into the appropriate number of documents.</span></span> <span data-ttu-id="d91f1-125">Esta es una condición obligatoria que no puede modificarse.</span><span class="sxs-lookup"><span data-stu-id="d91f1-125">This is a mandatory condition that cannot be changed.</span></span> <span data-ttu-id="d91f1-126">Del mismo modo, el registro también se dividirá en varios documentos si las líneas del pedido se van a enviar a diferentes direcciones de entrega y la directiva de envío se configura para requerir una división.</span><span class="sxs-lookup"><span data-stu-id="d91f1-126">Similarly, the posting will also be split into multiple documents if the order’s lines are to be shipped to different delivery addresses, and the shipping policy is set up to require a split.</span></span>  
9. <span data-ttu-id="d91f1-127">En la pestaña Líneas, seleccione la fila para la línea de pedido que se va enviar.</span><span class="sxs-lookup"><span data-stu-id="d91f1-127">On the Lines tab, select the row for the order line to be shipped.</span></span>
10. <span data-ttu-id="d91f1-128">En el campo Actualizar, escriba un número menor que la cantidad original.</span><span class="sxs-lookup"><span data-stu-id="d91f1-128">In the Update field, enter a number lower than the original quantity.</span></span>
11. <span data-ttu-id="d91f1-129">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="d91f1-129">Click OK.</span></span>
12. <span data-ttu-id="d91f1-130">Haga clic en Sí.</span><span class="sxs-lookup"><span data-stu-id="d91f1-130">Click Yes.</span></span>
13. <span data-ttu-id="d91f1-131">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="d91f1-131">Close the page.</span></span>
14. <span data-ttu-id="d91f1-132">En el panel de acciones, haga clic en Opciones.</span><span class="sxs-lookup"><span data-stu-id="d91f1-132">On the Action Pane, click Options.</span></span>
15. <span data-ttu-id="d91f1-133">Haga clic en Cambiar vista.</span><span class="sxs-lookup"><span data-stu-id="d91f1-133">Click Change view.</span></span>
16. <span data-ttu-id="d91f1-134">Haga clic en Visualización de encabezado.</span><span class="sxs-lookup"><span data-stu-id="d91f1-134">Click Header view.</span></span>
    * <span data-ttu-id="d91f1-135">Si todas las líneas del pedido se han enviado completamente, el estado del pedido cambia de Abierto a Entregado.</span><span class="sxs-lookup"><span data-stu-id="d91f1-135">If all of the lines on the order have been fully shipped, the order status changes from Open to Delivered.</span></span>  
    * <span data-ttu-id="d91f1-136">En este ejemplo, la línea de pedido se ha enviado parcialmente.</span><span class="sxs-lookup"><span data-stu-id="d91f1-136">In this example, the order line has been shipped partially.</span></span> <span data-ttu-id="d91f1-137">Este es el motivo por el cual el estado del pedido permanece abierto.</span><span class="sxs-lookup"><span data-stu-id="d91f1-137">This is why the the order status remains Open.</span></span>     
    * <span data-ttu-id="d91f1-138">El campo Estado del documento se establece en Albarán porque se ha enviado al menos una de las líneas del pedido.</span><span class="sxs-lookup"><span data-stu-id="d91f1-138">The Document status field is set to Packing slip because at least one of the order lines have been shipped.</span></span>  
17. <span data-ttu-id="d91f1-139">En el panel de acciones, haga clic en General.</span><span class="sxs-lookup"><span data-stu-id="d91f1-139">On the Action Pane, click General.</span></span>
18. <span data-ttu-id="d91f1-140">Haga clic en Cantidad de línea.</span><span class="sxs-lookup"><span data-stu-id="d91f1-140">Click Line quantity.</span></span>
19. <span data-ttu-id="d91f1-141">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="d91f1-141">Close the page.</span></span>
20. <span data-ttu-id="d91f1-142">En el panel de acciones, haga clic en Seleccionar y empaquetar.</span><span class="sxs-lookup"><span data-stu-id="d91f1-142">On the Action Pane, click Pick and pack.</span></span>
21. <span data-ttu-id="d91f1-143">Haga clic en Albarán.</span><span class="sxs-lookup"><span data-stu-id="d91f1-143">Click Packing slip.</span></span>
    * <span data-ttu-id="d91f1-144">La página Diario del albarán contiene todos los documentos de albaranes generados para el pedido.</span><span class="sxs-lookup"><span data-stu-id="d91f1-144">The Packing slip journal page contains all the packing slip documents that were generated for your order.</span></span> <span data-ttu-id="d91f1-145">Puede revisar los detalles de cada documento e imprimirlos, si lo desea.</span><span class="sxs-lookup"><span data-stu-id="d91f1-145">You can review details of each document and print them, if you wish.</span></span>  


