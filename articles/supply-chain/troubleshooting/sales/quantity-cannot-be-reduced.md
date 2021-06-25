---
title: La cantidad no se puede reducir cuando se cancela un pedido de cliente.
description: La cantidad no se puede reducir cuando se cancela un pedido de ventas.
author: hja-ms
ms.date: 5/17/2021
ms.topic: troubleshooting
ms.search.form: SalesTable_SalesCancelOrder, SalesTableListPage_SalesCancelOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: hja
ms.search.validFrom: 2021-05-17
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 1a2cc9c9fd3d085508fc652bc9ee0a352d869dee
ms.sourcegitcommit: a02d3d64c899f8554b74342d5a1856d824bf1abe
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/11/2021
ms.locfileid: "6230845"
---
# <a name="the-quantity-cant-be-reduced-when-a-sales-order-is-canceled"></a><span data-ttu-id="d51a0-103">La cantidad no se puede reducir cuando se cancela un pedido de cliente.</span><span class="sxs-lookup"><span data-stu-id="d51a0-103">The quantity can't be reduced when a sales order is canceled</span></span>

<span data-ttu-id="d51a0-104">Código de error: SYS138831</span><span class="sxs-lookup"><span data-stu-id="d51a0-104">Error code: SYS138831</span></span>

## <a name="symptoms"></a><span data-ttu-id="d51a0-105">Síntomas</span><span class="sxs-lookup"><span data-stu-id="d51a0-105">Symptoms</span></span>

<span data-ttu-id="d51a0-106">El sistema muestra el siguiente mensaje de error:</span><span class="sxs-lookup"><span data-stu-id="d51a0-106">The system shows the following error message:</span></span>

> <span data-ttu-id="d51a0-107">La cantidad no se puede reducir.</span><span class="sxs-lookup"><span data-stu-id="d51a0-107">The quantity cannot be reduced.</span></span> <span data-ttu-id="d51a0-108">El número de transacciones de inventario en el pedido es demasiado bajo porque la cantidad o parte de ella está referenciada por una orden de salida o una orden de producción o está marcada con otras transacciones.</span><span class="sxs-lookup"><span data-stu-id="d51a0-108">The number of inventory transactions on order is too low because the quantity or part of it is referenced by an output order or a production order or is marked against other transactions.</span></span>

## <a name="cause"></a><span data-ttu-id="d51a0-109">Causa</span><span class="sxs-lookup"><span data-stu-id="d51a0-109">Cause</span></span>

<span data-ttu-id="d51a0-110">Si el trabajo está asociado con un pedido de venta, no puede cancelar el pedido de venta hasta que el trabajo se cancele y se revierta.</span><span class="sxs-lookup"><span data-stu-id="d51a0-110">If work is associated with a sales order, you can't cancel the sales order until the work is canceled and reversed.</span></span> <span data-ttu-id="d51a0-111">Este requisito se aplica incluso si el trabajo asociado con el pedido de ventas está cerrado.</span><span class="sxs-lookup"><span data-stu-id="d51a0-111">This requirement applies even if the work that is associated with the sales order is closed.</span></span>

## <a name="resolution"></a><span data-ttu-id="d51a0-112">Resolución</span><span class="sxs-lookup"><span data-stu-id="d51a0-112">Resolution</span></span>

<span data-ttu-id="d51a0-113">Para solucionar este problema, complete las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="d51a0-113">To fix this issue, complete the following tasks:</span></span>

1. <span data-ttu-id="d51a0-114">Cancele el trabajo abierto.</span><span class="sxs-lookup"><span data-stu-id="d51a0-114">Cancel open work.</span></span>
1. <span data-ttu-id="d51a0-115">Elimina la carga.</span><span class="sxs-lookup"><span data-stu-id="d51a0-115">Delete the load.</span></span>
1. <span data-ttu-id="d51a0-116">Reduzca la cantidad seleccionada.</span><span class="sxs-lookup"><span data-stu-id="d51a0-116">Reduce the picked quantity.</span></span>

### <a name="cancel-open-work"></a><span data-ttu-id="d51a0-117">Cancele el trabajo abierto</span><span class="sxs-lookup"><span data-stu-id="d51a0-117">Cancel open work</span></span>

<span data-ttu-id="d51a0-118">Para cancelar el trabajo abierto, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="d51a0-118">To cancel open work, follow these steps.</span></span>

1. <span data-ttu-id="d51a0-119">Vaya a **Gestion de almacenes \> Tareas periódicas \> Limpiar \> Cancelar trabajo**.</span><span class="sxs-lookup"><span data-stu-id="d51a0-119">Go to **Warehouse management \> Periodic tasks \> Clean up \> Cancel work**.</span></span>
1. <span data-ttu-id="d51a0-120">En el campo **Id. de trabajo**, especifique el id. del trabajo que desea cancelar, y que actualmente tiene un valor de **Estado del trabajo** de *Abierto*, *En curso*, *Cancelado*, *Combinado* o *Cerrado*.</span><span class="sxs-lookup"><span data-stu-id="d51a0-120">In the **Work ID** field, specify the ID of the work that you want to cancel, and that currently has a **Work status** value of *Open*, *In progress*, *Canceled*, *Combined*, or *Closed*.</span></span>
1. <span data-ttu-id="d51a0-121">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d51a0-121">Select **OK**.</span></span>
1. <span data-ttu-id="d51a0-122">Seleccione **Sí** para confirmar que desea cancelar el trabajo.</span><span class="sxs-lookup"><span data-stu-id="d51a0-122">Select **Yes** to confirm that you want to cancel the work.</span></span>

### <a name="delete-the-load"></a><span data-ttu-id="d51a0-123">Eliminar la carga</span><span class="sxs-lookup"><span data-stu-id="d51a0-123">Delete the load</span></span>

<span data-ttu-id="d51a0-124">Para eliminar una carga, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="d51a0-124">To delete a load, follow these steps.</span></span>

1. <span data-ttu-id="d51a0-125">Vaya a **Ventas y marketing \> Pedidos de ventas \> Todos los pedidos de ventas**.</span><span class="sxs-lookup"><span data-stu-id="d51a0-125">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="d51a0-126">Abra el pedido de ventas pertinente.</span><span class="sxs-lookup"><span data-stu-id="d51a0-126">Open the relevant sales order.</span></span>
1. <span data-ttu-id="d51a0-127">En la ficha desplegable **Líneas de pedido de venta**, seleccione **Almacén \> Detalles del trabajo**.</span><span class="sxs-lookup"><span data-stu-id="d51a0-127">On the **Sales order lines** FastTab, select **Warehouse \> Work details**.</span></span>
1. <span data-ttu-id="d51a0-128">En la página **Trabajo**, en el panel de acciones, en la pestaña **Trabajo**, en el grupo **Trabajo**, seleccione **Cancelar trabajo**.</span><span class="sxs-lookup"><span data-stu-id="d51a0-128">On the **Work** page, on the Action Pane, on the **Work** tab, in the **Work** group, select **Cancel work**.</span></span>
1. <span data-ttu-id="d51a0-129">Confirme que el campo **Situación de trabajo** está configurado en *Cancelado*.</span><span class="sxs-lookup"><span data-stu-id="d51a0-129">Confirm that the **Work status** field is set to *Canceled*.</span></span>
1. <span data-ttu-id="d51a0-130">Cierre la página **Trabajo**.</span><span class="sxs-lookup"><span data-stu-id="d51a0-130">Close the **Work** page.</span></span>
1. <span data-ttu-id="d51a0-131">En la página de detalles del pedido de venta, en la ficha desplegable **Líneas de pedido de ventas**, seleccione **Almacén \> Detalles de carga**.</span><span class="sxs-lookup"><span data-stu-id="d51a0-131">On the sales order details page, on the **Sales order lines** FastTab, select **Warehouse \> Load details**.</span></span>
1. <span data-ttu-id="d51a0-132">En el panel de acciones, seleccione **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="d51a0-132">On the Action Pane, select **Delete**.</span></span>
1. <span data-ttu-id="d51a0-133">Seleccione **Sí** para confirmar que desea eliminar la carga.</span><span class="sxs-lookup"><span data-stu-id="d51a0-133">Select **Yes** to confirm that you want to delete the load.</span></span>
1. <span data-ttu-id="d51a0-134">Cierre la página **Carga**.</span><span class="sxs-lookup"><span data-stu-id="d51a0-134">Close the **Load** page.</span></span>

### <a name="reduce-the-picked-quantity"></a><span data-ttu-id="d51a0-135">Reduzca la cantidad seleccionada</span><span class="sxs-lookup"><span data-stu-id="d51a0-135">Reduce the picked quantity</span></span>

<span data-ttu-id="d51a0-136">Una vez cancelado todo el trabajo, siga estos pasos para reducir la cantidad recogida.</span><span class="sxs-lookup"><span data-stu-id="d51a0-136">After all work has been canceled, follow these steps to reduce the picked quantity.</span></span>

1. <span data-ttu-id="d51a0-137">Vaya a **Ventas y marketing \> Pedidos de ventas \> Todos los pedidos de ventas**.</span><span class="sxs-lookup"><span data-stu-id="d51a0-137">Go to **Sales and marketing \> Sales orders \> All sales orders**.</span></span>
1. <span data-ttu-id="d51a0-138">Abra el pedido de ventas pertinente.</span><span class="sxs-lookup"><span data-stu-id="d51a0-138">Open the relevant sales order.</span></span>
1. <span data-ttu-id="d51a0-139">En la ficha desplegable **Líneas de pedido de ventas**, seleccione **Línea de actualización \> Seleccionar** desde la barra de herramientas.</span><span class="sxs-lookup"><span data-stu-id="d51a0-139">On the **Sales order lines** FastTab, select **Update line \> Pick** from the toolbar.</span></span>
1. <span data-ttu-id="d51a0-140">En la página **Seleccionar**, en la sección **Transacciones**, seleccione la línea donde el campo **Estado de incidencia** está configurado en *Seleccionado*.</span><span class="sxs-lookup"><span data-stu-id="d51a0-140">On the **Pick** page, in the **Transactions** section, select the line where the **Issue status** field is set to *Picked*.</span></span>
1. <span data-ttu-id="d51a0-141">En la sección **Transacciones**, seleccione **Agregar línea de selección** desde la barra de herramientas.</span><span class="sxs-lookup"><span data-stu-id="d51a0-141">In the **Transactions** section, select **Add picking line** from the toolbar.</span></span>
1. <span data-ttu-id="d51a0-142">En la sección **Líneas de selección**, seleccione **Confirmar la selección de todo** desde la barra de herramientas.</span><span class="sxs-lookup"><span data-stu-id="d51a0-142">In the **Picking lines** section, select **Confirm pick all** from the toolbar.</span></span>
1. <span data-ttu-id="d51a0-143">Cierre la página **Selección**.</span><span class="sxs-lookup"><span data-stu-id="d51a0-143">Close the **Pick** page.</span></span>
1. <span data-ttu-id="d51a0-144">En la página de detalles del pedido de ventas, en el panel de acciones, en la pestaña Pedido **de ventas**, en el grupo **Mantener**, seleccione **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="d51a0-144">On the sales order details page, on the Action Pane, on the **Sales order** tab, in the **Maintain** group, select **Cancel**.</span></span>
1. <span data-ttu-id="d51a0-145">Seleccione **Sí** para confirmar que desea cancelar el pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="d51a0-145">Select **Yes** to confirm that you want to cancel the sales order.</span></span>
