--- 
title: Gestionar retenciones de pedidos
description: "Este procedimiento demuestra cómo poner en espera los pedidos de ventas del cliente, cómo trabajar con retenciones de pedidos desprotegidas y cómo quitar retenciones de pedido."
author: omulvad
manager: AnnBe
ms.date: 01/09/2017
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
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: e9a520b2af7cdfef325f1fa96504f2a20078ed80
ms.contentlocale: es-es
ms.lasthandoff: 08/29/2017

---
# <a name="manage-order-holds"></a><span data-ttu-id="a27ae-103">Gestionar retenciones de pedidos</span><span class="sxs-lookup"><span data-stu-id="a27ae-103">Manage order holds</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="a27ae-104">Este procedimiento demuestra cómo poner en espera los pedidos de ventas del cliente, cómo trabajar con retenciones de pedidos desprotegidas y cómo quitar retenciones de pedido.</span><span class="sxs-lookup"><span data-stu-id="a27ae-104">This procedure demonstrates how to place customer sales orders on hold, how to work with order hold checkouts, and how to remove order holds.</span></span> <span data-ttu-id="a27ae-105">Un pedido se puede retener por una variedad de motivos.</span><span class="sxs-lookup"><span data-stu-id="a27ae-105">An order might be placed on hold for a variety of reasons.</span></span> <span data-ttu-id="a27ae-106">Por ejemplo, puede retener un pedido hasta que la dirección o el método de pago de un cliente se pueda comprobar o hasta que un director pueda revisar el límite de crédito del cliente.</span><span class="sxs-lookup"><span data-stu-id="a27ae-106">For example, you might hold an order until a customer address or payment method can be verified or until a manager can review the customer’s credit limit.</span></span> <span data-ttu-id="a27ae-107">Mientras el pedido se encuentra en espera, el almacén no se puede procesar para su envío.</span><span class="sxs-lookup"><span data-stu-id="a27ae-107">While the order on hold, it cannot be processed by the warehouse for shipping.</span></span> 

<span data-ttu-id="a27ae-108">Puede ejecutar este procedimiento con los datos de la empresa de demostración USMF o utilizar sus propios datos.</span><span class="sxs-lookup"><span data-stu-id="a27ae-108">You can run this procedure in demo data company USMF or on your own data.</span></span>


## <a name="set-up-order-holds"></a><span data-ttu-id="a27ae-109">Configuración de retenciones de pedidos</span><span class="sxs-lookup"><span data-stu-id="a27ae-109">Set up order holds</span></span>
1. <span data-ttu-id="a27ae-110">Vaya a Ventas y marketing > Configuración > Pedidos de ventas > Códigos de retención de pedido.</span><span class="sxs-lookup"><span data-stu-id="a27ae-110">Go to Sales and marketing > Setup > Sales orders > Order hold codes.</span></span>
2. <span data-ttu-id="a27ae-111">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="a27ae-111">Click New.</span></span>
3. <span data-ttu-id="a27ae-112">En el campo Código de retención, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="a27ae-112">In the Hold code field, type a value.</span></span>
    * <span data-ttu-id="a27ae-113">Por ejemplo, tipo Volver a llamar.</span><span class="sxs-lookup"><span data-stu-id="a27ae-113">For example, type Call back.</span></span>  
4. <span data-ttu-id="a27ae-114">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="a27ae-114">In the Description field, type a value.</span></span>
    * <span data-ttu-id="a27ae-115">Por ejemplo, el Pedido se encuentra retenido en espera de devolución de llamada del cliente.</span><span class="sxs-lookup"><span data-stu-id="a27ae-115">For example, Order held waiting for customer callback.</span></span>  
    * <span data-ttu-id="a27ae-116">De manera opcional, seleccione la casilla Quitar reservas para eliminar las reservas físicas del pedido cuando se agrega este código de retención.</span><span class="sxs-lookup"><span data-stu-id="a27ae-116">Optionally, select the Remove reservations check box to remove any physical reservations from the order when this hold code is added.</span></span>  
5. <span data-ttu-id="a27ae-117">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="a27ae-117">Click Save.</span></span>

## <a name="place-order-on-hold"></a><span data-ttu-id="a27ae-118">Retenga el pedido</span><span class="sxs-lookup"><span data-stu-id="a27ae-118">Place order on hold</span></span>
1. <span data-ttu-id="a27ae-119">Vaya a Ventas y marketing > Pedidos de ventas > Todos los pedidos de ventas.</span><span class="sxs-lookup"><span data-stu-id="a27ae-119">Go to Sales and marketing > Sales orders > All sales orders.</span></span>
2. <span data-ttu-id="a27ae-120">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="a27ae-120">Click New.</span></span>
3. <span data-ttu-id="a27ae-121">En el campo Cuenta de cliente, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="a27ae-121">In the Customer account field, enter or select a value.</span></span>
4. <span data-ttu-id="a27ae-122">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="a27ae-122">Click OK.</span></span>
5. <span data-ttu-id="a27ae-123">En el campo Número de artículo, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="a27ae-123">In the Item number field, enter or select a value.</span></span>
6. <span data-ttu-id="a27ae-124">En el campo Cantidad, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="a27ae-124">In the Quantity field, enter a number.</span></span>
7. <span data-ttu-id="a27ae-125">En el panel de acciones, haga clic en Pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="a27ae-125">On the Action Pane, click Sales order.</span></span>
8. <span data-ttu-id="a27ae-126">Haga clic en Retenciones de pedido.</span><span class="sxs-lookup"><span data-stu-id="a27ae-126">Click Order holds.</span></span>
9. <span data-ttu-id="a27ae-127">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="a27ae-127">Click New.</span></span>
10. <span data-ttu-id="a27ae-128">En el campo Código de retención, seleccione el código que ha creado en la subtarea anterior.</span><span class="sxs-lookup"><span data-stu-id="a27ae-128">In the Hold code field, select the code you have created in the previous subtask.</span></span>
11. <span data-ttu-id="a27ae-129">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="a27ae-129">Click Save.</span></span>
12. <span data-ttu-id="a27ae-130">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="a27ae-130">Close the page.</span></span>
13. <span data-ttu-id="a27ae-131">Vaya a Ventas y marketing > Pedidos de ventas > Todos los pedidos de ventas.</span><span class="sxs-lookup"><span data-stu-id="a27ae-131">Go to Sales and marketing > Sales orders > All sales orders.</span></span>
14. <span data-ttu-id="a27ae-132">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="a27ae-132">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="a27ae-133">Los pedidos que están actualmente en espera tienen marcados los campos "No procesar" y "En espera".</span><span class="sxs-lookup"><span data-stu-id="a27ae-133">Orders that are currently on hold have the "Do not process" and "Hold" fields marked.</span></span>    
15. <span data-ttu-id="a27ae-134">En el panel de acciones, haga clic en Seleccionar y empaquetar.</span><span class="sxs-lookup"><span data-stu-id="a27ae-134">On the Action Pane, click Pick and pack.</span></span>

## <a name="manage-order-holds"></a><span data-ttu-id="a27ae-135">Gestionar retenciones de pedidos</span><span class="sxs-lookup"><span data-stu-id="a27ae-135">Manage order holds</span></span>
1. <span data-ttu-id="a27ae-136">Vaya a Ventas y marketing > Pedidos de ventas > Pedidos abiertos > Retenciones de pedido.</span><span class="sxs-lookup"><span data-stu-id="a27ae-136">Go to Sales and marketing > Sales orders > Open orders > Order holds.</span></span>
    * <span data-ttu-id="a27ae-137">La página de retenciones de pedido funciona como un área de trabajo que le proporciona una visión general de todas las retenciones (en curso y procesadas), donde podrá gestionarlas junto con los pedidos de ventas relacionados.</span><span class="sxs-lookup"><span data-stu-id="a27ae-137">Order holds page functions as a workbench where you can get an overview of all the current and processed holds, and handle them and associated sales orders.</span></span>      
2. <span data-ttu-id="a27ae-138">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="a27ae-138">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="a27ae-139">En el Panel de acciones, haga clic en Retener finalización de la compra.</span><span class="sxs-lookup"><span data-stu-id="a27ae-139">On the Action Pane, click Hold checkout.</span></span>
4. <span data-ttu-id="a27ae-140">Haga clic en Registro de salida del conductor.</span><span class="sxs-lookup"><span data-stu-id="a27ae-140">Click Check out.</span></span>
5. <span data-ttu-id="a27ae-141">En la lista, desmarque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="a27ae-141">In the list, unmark the selected row.</span></span>
    * <span data-ttu-id="a27ae-142">El campo Desprotegido para ahora muestra su Id. de usuario.</span><span class="sxs-lookup"><span data-stu-id="a27ae-142">The Checkout out to field now shows your user ID.</span></span>   
6. <span data-ttu-id="a27ae-143">Haga clic en Liberar desprotección.</span><span class="sxs-lookup"><span data-stu-id="a27ae-143">Click Clear checkout.</span></span>
7. <span data-ttu-id="a27ae-144">En el Panel de acciones, haga clic en Liberar retención.</span><span class="sxs-lookup"><span data-stu-id="a27ae-144">On the Action Pane, click Clear hold.</span></span>
    * <span data-ttu-id="a27ae-145">Cuando esté listo para quitar la retención y permitir que el pedido pase a la siguiente fase de la entrega, deberá desactivar la retención.</span><span class="sxs-lookup"><span data-stu-id="a27ae-145">When you are ready to remove the hold and allow the order to proceed to the next fulfilment step, you must clear the hold.</span></span> <span data-ttu-id="a27ae-146">Si el pedido no requiere ninguna modificación, puede ejecutar la acción Liberar retenciones.</span><span class="sxs-lookup"><span data-stu-id="a27ae-146">If the order requires no changes, you can run the Clear holds action.</span></span> <span data-ttu-id="a27ae-147">Sin embargo, puede usar la acción Liberar y modificar si el pedido necesita actualizarse en el momento de liberar la retención.</span><span class="sxs-lookup"><span data-stu-id="a27ae-147">However, you can use the Clear and modify action if, when clearing a hold, the order has to be updated.</span></span>      
    * <span data-ttu-id="a27ae-148">La acción Borrar y Enviar sólo es aplicable cuando utilice la funcionalidad del Centro de llamadas.</span><span class="sxs-lookup"><span data-stu-id="a27ae-148">The Clear and submit action is only applicable when you use Call center functionality.</span></span>  
8. <span data-ttu-id="a27ae-149">Haga clic en Liberar retenciones.</span><span class="sxs-lookup"><span data-stu-id="a27ae-149">Click Clear holds.</span></span>
    * <span data-ttu-id="a27ae-150">La retención se ha liberado del pedido y se ha quitado de la lista de retenciones activas.</span><span class="sxs-lookup"><span data-stu-id="a27ae-150">The hold has now been cleared from the order and removed from the list of Active holds.</span></span> <span data-ttu-id="a27ae-151">Para ver todas las retenciones o su subconjunto en función de un estado específico, cambie el valor del campo Mostrar.</span><span class="sxs-lookup"><span data-stu-id="a27ae-151">To see all the holds or their subset according to a specific status, change the value in the Show field.</span></span>     


