--- 
title: Cumplimiento de acuerdos de venta
description: "Este procedimiento le muestra cómo satisfacer un acuerdo de venta asociando pedidos de ventas a él."
author: omulvad
manager: AnnBe
ms.date: 11/10/2016
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
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: b36777be0abcbd17e96b42b81553155aeb909943
ms.contentlocale: es-es
ms.lasthandoff: 04/13/2018

---
# <a name="fulfill-sales-agreements"></a><span data-ttu-id="bf5f8-103">Cumplimiento de acuerdos de venta</span><span class="sxs-lookup"><span data-stu-id="bf5f8-103">Fulfill sales agreements</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="bf5f8-104">Este procedimiento le muestra cómo satisfacer un acuerdo de venta asociando pedidos de ventas a él.</span><span class="sxs-lookup"><span data-stu-id="bf5f8-104">This procedure shows you how to fulfill a sales agreement by associating sales orders with it.</span></span> <span data-ttu-id="bf5f8-105">Puede ejecutar este procedimiento con los datos de la empresa de demostración USMF o utilizar sus propios datos.</span><span class="sxs-lookup"><span data-stu-id="bf5f8-105">You can run this procedure in demo data company USMF or on your own data.</span></span> <span data-ttu-id="bf5f8-106">Antes de comenzar este guía, asegúrese de que tiene un acuerdo de venta vigente del tipo "Compromiso de valor de producto".</span><span class="sxs-lookup"><span data-stu-id="bf5f8-106">Before starting this guide, make sure you have an effective sales agreement of type "Product value commitment".</span></span> <span data-ttu-id="bf5f8-107">Como alternativa, puede ejecutar la guía de tareas llamada "Crear o acuerdos de venta".</span><span class="sxs-lookup"><span data-stu-id="bf5f8-107">Alternatively, you can run the task guide called "Create sales agreements".</span></span>  




## <a name="release-a-sales-order-from-the-agreement"></a><span data-ttu-id="bf5f8-108">Liberar un pedido de ventas del acuerdo</span><span class="sxs-lookup"><span data-stu-id="bf5f8-108">Release a sales order from the agreement</span></span>
1. <span data-ttu-id="bf5f8-109">Vaya a Ventas y marketing > Acuerdos de venta > Acuerdos de venta.</span><span class="sxs-lookup"><span data-stu-id="bf5f8-109">Go to Sales and marketing > Sales agreements > Sales agreements.</span></span>
2. <span data-ttu-id="bf5f8-110">En la lista, abra el acuerdo con el que desea liberar el pedido.</span><span class="sxs-lookup"><span data-stu-id="bf5f8-110">In the list, open the agreement against which you want to release the order.</span></span>
3. <span data-ttu-id="bf5f8-111">En el panel de acciones, haga clic en Acuerdo de venta</span><span class="sxs-lookup"><span data-stu-id="bf5f8-111">On the Action Pane, click Sales agreement.</span></span>
4. <span data-ttu-id="bf5f8-112">Haga clic en Pedido parcial.</span><span class="sxs-lookup"><span data-stu-id="bf5f8-112">Click Release order.</span></span>
    * <span data-ttu-id="bf5f8-113">A medida que se muestra el texto de la parte superior de la página Crear pedido parcial, los detalles necesarios para las líneas de pedidos de ventas serán diferentes en función de si el contrato se basa en una cantidad o en un valor.</span><span class="sxs-lookup"><span data-stu-id="bf5f8-113">As the text on top of the  Create release order page points out, the details required for the sales order lines will differ depending on whether the agreement is quantity- or value-based.</span></span>  
    * <span data-ttu-id="bf5f8-114">El acuerdo de esta guía es de tipo “Compromiso de valor de producto”.</span><span class="sxs-lookup"><span data-stu-id="bf5f8-114">The agreement in this guide is of type "Product value commitment".</span></span> <span data-ttu-id="bf5f8-115">Este es el motivo por el que la sección Líneas de esta página está en blanco.</span><span class="sxs-lookup"><span data-stu-id="bf5f8-115">This is why the Lines section of this page is blank.</span></span> <span data-ttu-id="bf5f8-116">Si el compromiso se basa en la cantidad, se copiará del acuerdo la información de la línea.</span><span class="sxs-lookup"><span data-stu-id="bf5f8-116">If the commitment was based on quantity, the line information would be copied from the agreement.</span></span>  
5. <span data-ttu-id="bf5f8-117">Haga clic en Crear.</span><span class="sxs-lookup"><span data-stu-id="bf5f8-117">Click Create.</span></span>
    * <span data-ttu-id="bf5f8-118">El mensaje informa de que se ha creado un pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="bf5f8-118">The message informs you that a sales order has been created.</span></span> <span data-ttu-id="bf5f8-119">Dado que el pedido no contiene ninguna línea, debe agregar los detalles de la línea de pedido para completar el proceso de lanzamiento.</span><span class="sxs-lookup"><span data-stu-id="bf5f8-119">Since the order does not contain any lines, you must add order line details to complete the release process.</span></span>   
6. <span data-ttu-id="bf5f8-120">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="bf5f8-120">Close the page.</span></span>
7. <span data-ttu-id="bf5f8-121">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="bf5f8-121">Close the page.</span></span>
8. <span data-ttu-id="bf5f8-122">Vaya a Ventas y marketing > Pedidos de ventas > Todos los pedidos de ventas.</span><span class="sxs-lookup"><span data-stu-id="bf5f8-122">Go to Sales and marketing > Sales orders > All sales orders.</span></span>
9. <span data-ttu-id="bf5f8-123">En la lista, busque y abra el pedido creado como resultado de la emisión de pedido de la tarea anterior.</span><span class="sxs-lookup"><span data-stu-id="bf5f8-123">In the list, find and open the order that was created as the result of the order release in the previous task.</span></span>
10. <span data-ttu-id="bf5f8-124">Haga clic en Agregar línea.</span><span class="sxs-lookup"><span data-stu-id="bf5f8-124">Click Add line.</span></span>
11. <span data-ttu-id="bf5f8-125">En el campo Código de artículo, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="bf5f8-125">In the Item number field, click the drop-down button to open the lookup.</span></span>
12. <span data-ttu-id="bf5f8-126">En el campo Código de artículo, escriba o seleccione el artículo que se especifica en el acuerdo de venta asociado.</span><span class="sxs-lookup"><span data-stu-id="bf5f8-126">In the Item number field, type or select the item that is specified on the associated sales agreement.</span></span>
13. <span data-ttu-id="bf5f8-127">En el campo Cantidad, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="bf5f8-127">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="bf5f8-128">Asegúrese de especificar una cantidad que lleve el Importe neto bajo el valor del acuerdo de venta asociado.</span><span class="sxs-lookup"><span data-stu-id="bf5f8-128">Make sure that you enter a quantity that brings the Net amount under the value of the associated sales agreement.</span></span>  
    * <span data-ttu-id="bf5f8-129">Observe que dado que el pedido de ventas está vinculado al acuerdo, el porcentaje de descuento negociado se aplica a la línea de pedido.</span><span class="sxs-lookup"><span data-stu-id="bf5f8-129">Notice that because the sales order is linked to the agreement, the negotiated discount percent is applied to the order line.</span></span>  
14. <span data-ttu-id="bf5f8-130">Haga clic en Actualizar línea.</span><span class="sxs-lookup"><span data-stu-id="bf5f8-130">Click Update line.</span></span>
15. <span data-ttu-id="bf5f8-131">Haga clic en Adjunto.</span><span class="sxs-lookup"><span data-stu-id="bf5f8-131">Click Attached.</span></span>
    * <span data-ttu-id="bf5f8-132">La página Acuerdo adjunto muestra el id. y las condiciones del acuerdo desde el que se libera la línea.</span><span class="sxs-lookup"><span data-stu-id="bf5f8-132">The Attached agreement page shows the ID and terms of the agreement from which the line is released.</span></span>  
16. <span data-ttu-id="bf5f8-133">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="bf5f8-133">Close the page.</span></span>
17. <span data-ttu-id="bf5f8-134">En el panel de acciones, haga clic en General.</span><span class="sxs-lookup"><span data-stu-id="bf5f8-134">On the Action Pane, click General.</span></span>
18. <span data-ttu-id="bf5f8-135">Haga clic en Acuerdo de venta adjunto.</span><span class="sxs-lookup"><span data-stu-id="bf5f8-135">Click Attached sales agreement.</span></span>
19. <span data-ttu-id="bf5f8-136">Expanda la sección Detalles de línea.</span><span class="sxs-lookup"><span data-stu-id="bf5f8-136">Expand the Line details section.</span></span>
20. <span data-ttu-id="bf5f8-137">Haga clic en la pestaña Suministro.</span><span class="sxs-lookup"><span data-stu-id="bf5f8-137">Click the Fulfillment tab.</span></span>
    * <span data-ttu-id="bf5f8-138">La etiqueta Suministro muestra un resumen de todas las líneas de pedidos de ventas asociadas a este compromiso, y su estado de cumplimiento, junto con el importe o la cantidad que aún no se han liberado.</span><span class="sxs-lookup"><span data-stu-id="bf5f8-138">The Fulfillment tab shows a summary of all the sales order lines that are associated with this commitment, and their fulfillment state, as well as the amount or quantity that has not yet been released.</span></span>   
21. <span data-ttu-id="bf5f8-139">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="bf5f8-139">Close the page.</span></span>
22. <span data-ttu-id="bf5f8-140">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="bf5f8-140">Close the page.</span></span>
23. <span data-ttu-id="bf5f8-141">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="bf5f8-141">Close the page.</span></span>

## <a name="apply-sales-agreement-in-the-order-process"></a><span data-ttu-id="bf5f8-142">Aplicar el acuerdo de ventas en el proceso de pedidos</span><span class="sxs-lookup"><span data-stu-id="bf5f8-142">Apply sales agreement in the order process</span></span>
1. <span data-ttu-id="bf5f8-143">Vaya a Ventas y marketing > Pedidos de ventas > Todos los pedidos de ventas.</span><span class="sxs-lookup"><span data-stu-id="bf5f8-143">Go to Sales and marketing > Sales orders > All sales orders.</span></span>
2. <span data-ttu-id="bf5f8-144">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="bf5f8-144">Click New.</span></span>
3. <span data-ttu-id="bf5f8-145">En el campo Cuenta de cliente, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="bf5f8-145">In the Customer account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="bf5f8-146">En la lista, busque y seleccione el cliente especificado en el acuerdo de venta.</span><span class="sxs-lookup"><span data-stu-id="bf5f8-146">In the list, find and select the customer specified on the sales agreement.</span></span>
5. <span data-ttu-id="bf5f8-147">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="bf5f8-147">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="bf5f8-148">Expanda la sección General.</span><span class="sxs-lookup"><span data-stu-id="bf5f8-148">Expand the General section.</span></span>
7. <span data-ttu-id="bf5f8-149">En el campo Id. del acuerdo de venta, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="bf5f8-149">In the Sales agreement ID field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="bf5f8-150">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="bf5f8-150">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="bf5f8-151">Haga clic en Sí.</span><span class="sxs-lookup"><span data-stu-id="bf5f8-151">Click Yes.</span></span>
10. <span data-ttu-id="bf5f8-152">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="bf5f8-152">Click OK.</span></span>
11. <span data-ttu-id="bf5f8-153">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="bf5f8-153">In the list, mark the selected row.</span></span>
12. <span data-ttu-id="bf5f8-154">En el campo Código de artículo, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="bf5f8-154">In the Item number field, click the drop-down button to open the lookup.</span></span>
13. <span data-ttu-id="bf5f8-155">En el campo Código de artículo, escriba o seleccione el artículo que se especifica en el acuerdo de venta asociado.</span><span class="sxs-lookup"><span data-stu-id="bf5f8-155">In the Item number field, type or select the item that is specified on the associated sales agreement.</span></span>
14. <span data-ttu-id="bf5f8-156">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="bf5f8-156">In the list, click the link in the selected row.</span></span>
15. <span data-ttu-id="bf5f8-157">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="bf5f8-157">Click Save.</span></span>
16. <span data-ttu-id="bf5f8-158">En el panel de acciones, haga clic en Seleccionar y empaquetar.</span><span class="sxs-lookup"><span data-stu-id="bf5f8-158">On the Action Pane, click Pick and pack.</span></span>
17. <span data-ttu-id="bf5f8-159">Haga clic en Registrar albarán.</span><span class="sxs-lookup"><span data-stu-id="bf5f8-159">Click Post packing slip.</span></span>
18. <span data-ttu-id="bf5f8-160">Expanda la sección Parámetros.</span><span class="sxs-lookup"><span data-stu-id="bf5f8-160">Expand the Parameters section.</span></span>
19. <span data-ttu-id="bf5f8-161">Seleccione Sí en el campo Registro.</span><span class="sxs-lookup"><span data-stu-id="bf5f8-161">Select Yes in the Posting field.</span></span>
20. <span data-ttu-id="bf5f8-162">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="bf5f8-162">Click OK.</span></span>
21. <span data-ttu-id="bf5f8-163">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="bf5f8-163">Click OK.</span></span>
22. <span data-ttu-id="bf5f8-164">En el panel de acciones, haga clic en General.</span><span class="sxs-lookup"><span data-stu-id="bf5f8-164">On the Action Pane, click General.</span></span>
23. <span data-ttu-id="bf5f8-165">Haga clic en Acuerdo de venta adjunto.</span><span class="sxs-lookup"><span data-stu-id="bf5f8-165">Click Attached sales agreement.</span></span>
24. <span data-ttu-id="bf5f8-166">Haga clic en la pestaña Suministro.</span><span class="sxs-lookup"><span data-stu-id="bf5f8-166">Click the Fulfillment tab.</span></span>


