---
title: La cantidad que está intentando actualizar supera la cantidad recibida / entregada.
description: Cuando genera un albarán, la carga de salida contiene una cantidad que excede la cantidad de trabajo que se seleccionó y reservó para la orden de venta.
author: GalynaFedorova
ms.date: 5/31/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadTable_WHSSalesPackingSlipPost,WHSLoadPlanningListPage_WHSSalesPackingSlipPost,WHSLoadPlanningWorkbench_WHSSalesPackingSlipPost
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 66d9cd80cc61e00d1d88ab4f59d03054d746cdd9
ms.sourcegitcommit: e6437d994c3be0c5bb4a9263af3aa8351020d83a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/14/2021
ms.locfileid: "6249169"
---
# <a name="quantity-that-youre-trying-to-update-exceeds-the-receiveddelivered-quantity"></a><span data-ttu-id="0f10d-103">La cantidad que está intentando actualizar supera la cantidad recibida / entregada</span><span class="sxs-lookup"><span data-stu-id="0f10d-103">Quantity that you're trying to update exceeds the received/delivered quantity</span></span>

<span data-ttu-id="0f10d-104">Código de error: SYS7676</span><span class="sxs-lookup"><span data-stu-id="0f10d-104">Error code: SYS7676</span></span>

## <a name="symptoms"></a><span data-ttu-id="0f10d-105">Síntomas</span><span class="sxs-lookup"><span data-stu-id="0f10d-105">Symptoms</span></span>

<span data-ttu-id="0f10d-106">Cuando genera un albarán, la carga de salida contiene una cantidad que excede la cantidad de trabajo que se seleccionó y reservó para la orden de venta.</span><span class="sxs-lookup"><span data-stu-id="0f10d-106">When you generate a packing slip, the outbound load contains a quantity that exceeds the work quantity that was picked and reserved for the sales order.</span></span>

<span data-ttu-id="0f10d-107">Cuando intenta generar un albarán, el sistema muestra el siguiente mensaje de error:</span><span class="sxs-lookup"><span data-stu-id="0f10d-107">When you try to generate a packing slip, the system shows the following error message:</span></span>

> <span data-ttu-id="0f10d-108">La cantidad que intenta actualizar supera la cantidad recibida o entregada.</span><span class="sxs-lookup"><span data-stu-id="0f10d-108">The quantity that you are trying to update exceeds the quantity received/delivered.</span></span>

<span data-ttu-id="0f10d-109">Por lo tanto, no puede generar el albarán de la carga.</span><span class="sxs-lookup"><span data-stu-id="0f10d-109">Therefore, you can't generate the packing slip for the load.</span></span>

## <a name="cause"></a><span data-ttu-id="0f10d-110">Causa</span><span class="sxs-lookup"><span data-stu-id="0f10d-110">Cause</span></span>

<span data-ttu-id="0f10d-111">La cantidad de trabajo escogido no coincide con la cantidad de trabajo creada en la línea de carga.</span><span class="sxs-lookup"><span data-stu-id="0f10d-111">The picked work quantity doesn't match the created work quantity on the load line.</span></span> <span data-ttu-id="0f10d-112">Por ejemplo, este problema puede ocurrir si la cantidad de la línea de carga, la cantidad de trabajo creado o la cantidad recolectada no son precisas.</span><span class="sxs-lookup"><span data-stu-id="0f10d-112">For example, this issue might occur if the load line quantity, work created quantity, or picked quantity isn't accurate.</span></span>

## <a name="resolution"></a><span data-ttu-id="0f10d-113">Resolución</span><span class="sxs-lookup"><span data-stu-id="0f10d-113">Resolution</span></span>

<span data-ttu-id="0f10d-114">La carga o el envío se encuentran actualmente en un estado en el que falla la generación del albarán.</span><span class="sxs-lookup"><span data-stu-id="0f10d-114">The load or shipment is currently in a state where packing slip generation fails.</span></span> <span data-ttu-id="0f10d-115">Para solucionar este problema, complete una o más de las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="0f10d-115">To fix this issue, complete one of the following tasks:</span></span>

- <span data-ttu-id="0f10d-116">Revise las líneas de carga y asegúrese de que todo el trabajo relacionado se haya completado en la ubicación de envío final y que las cantidades coincidan.</span><span class="sxs-lookup"><span data-stu-id="0f10d-116">Review your load lines, and make sure that all the related work has been completed at the final shipping location, and that the quantities match.</span></span>
- <span data-ttu-id="0f10d-117">Ajuste la cantidad de la línea de carga.</span><span class="sxs-lookup"><span data-stu-id="0f10d-117">Adjust the load line quantity.</span></span>
- <span data-ttu-id="0f10d-118">Invierta todos los registros de picking y vuelva a realizar el picking.</span><span class="sxs-lookup"><span data-stu-id="0f10d-118">Reverse all pick registrations, and redo picking.</span></span>

### <a name="review-your-load-lines-and-make-sure-that-all-the-related-work-has-been-completed-at-the-final-shipping-location-and-that-the-quantities-match"></a><span data-ttu-id="0f10d-119">Revise las líneas de carga y asegúrese de que todo el trabajo relacionado se haya completado en la ubicación de envío final y que las cantidades coincidan</span><span class="sxs-lookup"><span data-stu-id="0f10d-119">Review your load lines, and make sure that all the related work has been completed at the final shipping location, and that the quantities match</span></span>

<span data-ttu-id="0f10d-120">Use el siguiente procedimiento para revisar las líneas de carga y asegúrese de que todo el trabajo relacionado se haya completado en la ubicación de envío final y que las cantidades coincidan.</span><span class="sxs-lookup"><span data-stu-id="0f10d-120">Use the following procedure to review your load lines and make sure that all the related work has been completed at the final shipping location, and that the quantities match.</span></span>

1. <span data-ttu-id="0f10d-121">Vaya a **Gestión de almacenes \> Cargas \> Todas las cargas**.</span><span class="sxs-lookup"><span data-stu-id="0f10d-121">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="0f10d-122">Seleccione la carga para la que el envío no se puede generar.</span><span class="sxs-lookup"><span data-stu-id="0f10d-122">Select the load that the shipment can't be generated for.</span></span>
1. <span data-ttu-id="0f10d-123">En la ficha desplegable **Líneas de carga**, seleccione la línea de carga.</span><span class="sxs-lookup"><span data-stu-id="0f10d-123">On the **Load lines** FastTab, select the load line.</span></span>
1. <span data-ttu-id="0f10d-124">Anote el valor del campo **Cantidad de trabajo creado**.</span><span class="sxs-lookup"><span data-stu-id="0f10d-124">Make a note of the value of the **Work created quantity** field.</span></span>
1. <span data-ttu-id="0f10d-125">En el panel de acciones, en la pestaña **Cargas** del grupo **Información relacionada**, seleccione **Trabajo**.</span><span class="sxs-lookup"><span data-stu-id="0f10d-125">On the Action Pane, on the **Loads** tab, in the **Related information** group, select **Work**.</span></span>
1. <span data-ttu-id="0f10d-126">Verifique que el trabajo se haya completado en la ubicación de envío final y que la cantidad de trabajo recogido coincida con la cantidad de trabajo creada en la línea de carga.</span><span class="sxs-lookup"><span data-stu-id="0f10d-126">Verify that the work has been completed at the final shipping location, and that the picked work quantity matches the created work quantity on the load line.</span></span>
1. <span data-ttu-id="0f10d-127">Repita este procedimiento para todas las líneas de carga para asegurarse de que se cumplan todos los criterios.</span><span class="sxs-lookup"><span data-stu-id="0f10d-127">Repeat this procedure for all load lines to make sure that all criteria are met.</span></span>

### <a name="adjust-the-load-line-quantity"></a><span data-ttu-id="0f10d-128">Ajuste la cantidad de la línea de carga</span><span class="sxs-lookup"><span data-stu-id="0f10d-128">Adjust the load line quantity</span></span>

<span data-ttu-id="0f10d-129">Utilice el siguiente procedimiento para ajustar la cantidad de la línea de carga.</span><span class="sxs-lookup"><span data-stu-id="0f10d-129">Use the following procedure to adjust the load line quantity.</span></span>

1. <span data-ttu-id="0f10d-130">Vaya a **Gestión de almacenes \> Cargas \> Todas las cargas**.</span><span class="sxs-lookup"><span data-stu-id="0f10d-130">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="0f10d-131">Seleccione la carga para la que el albarán no se puede generar.</span><span class="sxs-lookup"><span data-stu-id="0f10d-131">Select the load that the packing slip can't be generated for.</span></span>
1. <span data-ttu-id="0f10d-132">En el panel de acciones, en la pestaña **Enviar y recibir**, en el grupo **Contrarrestar**, seleccione **Invertir confirmación de envíos**.</span><span class="sxs-lookup"><span data-stu-id="0f10d-132">On the Action Pane, on the **Ship and receive** tab, in the **Reverse** group, select **Reverse shipment confirmation**.</span></span>
1. <span data-ttu-id="0f10d-133">En la pestaña  **Líneas de carga**, seleccione la línea de carga para el artículo que causa un problema.</span><span class="sxs-lookup"><span data-stu-id="0f10d-133">On the **Load lines** tab, select the load line for the item that causes an issue.</span></span>
1. <span data-ttu-id="0f10d-134">Seleccione **Reducir la cantidad recolectada** para ajustar la cantidad recogida.</span><span class="sxs-lookup"><span data-stu-id="0f10d-134">Select **Reduce picked quantity** to adjust the picked quantity.</span></span>
1. <span data-ttu-id="0f10d-135">Seleccione el campo **Reducir la línea de carga** para reflejar los ajustes en la línea de carga.</span><span class="sxs-lookup"><span data-stu-id="0f10d-135">Set the **Reduce load line** field to reflect adjustments on the load line.</span></span>

### <a name="reverse-all-pick-registrations-and-redo-picking"></a><span data-ttu-id="0f10d-136">Invierta todos los registros de picking y vuelva a realizar el picking</span><span class="sxs-lookup"><span data-stu-id="0f10d-136">Reverse all pick registrations, and redo picking</span></span>

<span data-ttu-id="0f10d-137">Si alguien usó el registro de recolección para cerrar una línea de carga sin trabajo, puede ocurrir una discrepancia entre la cantidad de la línea de carga y la cantidad recolectada.</span><span class="sxs-lookup"><span data-stu-id="0f10d-137">If someone used pick registration to close a load line without work, a discrepancy can occur between the load line quantity and the picked quantity.</span></span> <span data-ttu-id="0f10d-138">En este caso, se debe revertir el registro de picking manual y luego se debe completar el picking mediante la aplicación móvil Warehouse Management.</span><span class="sxs-lookup"><span data-stu-id="0f10d-138">In this case, manual pick registration must be reversed, and picking must then be completed by using the Warehouse Management mobile app.</span></span>

<span data-ttu-id="0f10d-139">Utilice el siguiente procedimiento para invertir el registro de recogida.</span><span class="sxs-lookup"><span data-stu-id="0f10d-139">Use the following procedure to reverse the pick registration.</span></span>

1. <span data-ttu-id="0f10d-140">Vaya a **Clientes \> Pedidos \> Todos los pedidos**.</span><span class="sxs-lookup"><span data-stu-id="0f10d-140">Go to **Accounts receivable \> Orders \> All orders**.</span></span>
1. <span data-ttu-id="0f10d-141">Seleccione el pedido de cliente para el que no puede contabilizar un albarán para la carga.</span><span class="sxs-lookup"><span data-stu-id="0f10d-141">Select the sales order for which you can't post a packing slip for the load.</span></span>
1. <span data-ttu-id="0f10d-142">Sobre la pesetaña **Líneas de orden de venta**, seleccione la línea de orden de venta para la que se realizó el registro de picking.</span><span class="sxs-lookup"><span data-stu-id="0f10d-142">On the **Sales order lines** tab, select the sales order line that pick registration was done for.</span></span>
1. <span data-ttu-id="0f10d-143">Seleccione **Línea de actualización \> Elegir** para despegar los artículos.</span><span class="sxs-lookup"><span data-stu-id="0f10d-143">Select **Update line \> Pick** to unpick the items.</span></span>
