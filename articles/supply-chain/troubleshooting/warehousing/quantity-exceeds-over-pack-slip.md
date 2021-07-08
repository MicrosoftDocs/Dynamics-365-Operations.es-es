---
title: La cantidad excede el porcentaje de entrega en exceso durante la generación del albarán
description: Cuando genera un albarán, la carga de salida contiene una cantidad que supera el porcentaje de entrega excesiva.
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
ms.openlocfilehash: 1106322cc3772c1b671b7fa82fb74039c028ba35
ms.sourcegitcommit: e6437d994c3be0c5bb4a9263af3aa8351020d83a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/14/2021
ms.locfileid: "6249166"
---
# <a name="quantity-exceeds-over-delivery-percentage-during-packing-slip-generation"></a><span data-ttu-id="f15f3-103">La cantidad excede el porcentaje de entrega en exceso durante la generación del albarán</span><span class="sxs-lookup"><span data-stu-id="f15f3-103">Quantity exceeds over-delivery percentage during packing slip generation</span></span>

<span data-ttu-id="f15f3-104">Código de error: SYS24920</span><span class="sxs-lookup"><span data-stu-id="f15f3-104">Error code: SYS24920</span></span>

## <a name="symptoms"></a><span data-ttu-id="f15f3-105">Síntomas</span><span class="sxs-lookup"><span data-stu-id="f15f3-105">Symptoms</span></span>

<span data-ttu-id="f15f3-106">Cuando genera un albarán, la carga de salida contiene una cantidad que supera el porcentaje de entrega excesiva.</span><span class="sxs-lookup"><span data-stu-id="f15f3-106">When you generate a packing slip, the outbound load contains a quantity that exceeds the over-delivery percentage.</span></span>

<span data-ttu-id="f15f3-107">Cuando intenta generar un albarán, el sistema muestra el siguiente mensaje de error:</span><span class="sxs-lookup"><span data-stu-id="f15f3-107">When you try to generate a packing slip, the system shows the following error message:</span></span>

> <span data-ttu-id="f15f3-108">La entrega en exceso de la línea es del %1 %, pero la entrega en exceso permitida es sólo del %2 %.</span><span class="sxs-lookup"><span data-stu-id="f15f3-108">Overdelivery of line is %1 percent, but the allowed overdelivery is only %2 percent.</span></span>

<span data-ttu-id="f15f3-109">Por lo tanto, no puede generar el albarán de la carga.</span><span class="sxs-lookup"><span data-stu-id="f15f3-109">Therefore, you can't generate the packing slip for the load.</span></span>

## <a name="cause"></a><span data-ttu-id="f15f3-110">Causa</span><span class="sxs-lookup"><span data-stu-id="f15f3-110">Cause</span></span>

<span data-ttu-id="f15f3-111">La cantidad recolectada para la carga o envío es mayor que la cantidad solicitada y no está dentro del rango del porcentaje de sobreentrega.</span><span class="sxs-lookup"><span data-stu-id="f15f3-111">The picked quantity for the load or shipment is more than the ordered quantity and isn't within the range of the over-delivery percentage.</span></span>

## <a name="resolution"></a><span data-ttu-id="f15f3-112">Resolución</span><span class="sxs-lookup"><span data-stu-id="f15f3-112">Resolution</span></span>

<span data-ttu-id="f15f3-113">La carga o el envío se encuentran actualmente en un estado en el que falla la generación del albarán.</span><span class="sxs-lookup"><span data-stu-id="f15f3-113">The load or shipment is currently in a state where packing slip generation fails.</span></span> <span data-ttu-id="f15f3-114">Para solucionar este problema, complete una o más de las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="f15f3-114">To fix this issue, complete one of the following tasks:</span></span>

- <span data-ttu-id="f15f3-115">Ajuste la cantidad de la línea de carga.</span><span class="sxs-lookup"><span data-stu-id="f15f3-115">Adjust the load line quantity.</span></span>
- <span data-ttu-id="f15f3-116">Ajuste el porcentaje de sobreentrega.</span><span class="sxs-lookup"><span data-stu-id="f15f3-116">Adjust the over-delivery percentage.</span></span>
- <span data-ttu-id="f15f3-117">Invierta y haga ajustes.</span><span class="sxs-lookup"><span data-stu-id="f15f3-117">Reverse and make adjustments.</span></span>

### <a name="adjust-the-load-line-quantity"></a><span data-ttu-id="f15f3-118">Ajuste la cantidad de la línea de carga</span><span class="sxs-lookup"><span data-stu-id="f15f3-118">Adjust the load line quantity</span></span>

<span data-ttu-id="f15f3-119">Utilice el siguiente procedimiento para ajustar la cantidad de la línea de carga.</span><span class="sxs-lookup"><span data-stu-id="f15f3-119">Use the following procedure to adjust the load line quantity.</span></span>

1. <span data-ttu-id="f15f3-120">Vaya a **Gestión de almacenes \> Cargas \> Todas las cargas**.</span><span class="sxs-lookup"><span data-stu-id="f15f3-120">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="f15f3-121">Seleccione la carga para la que el albarán no se puede generar.</span><span class="sxs-lookup"><span data-stu-id="f15f3-121">Select the load that the packing slip can't be generated for.</span></span>
1. <span data-ttu-id="f15f3-122">En el panel de acciones, en la pestaña **Enviar y recibir**, en el grupo **Contrarrestar**, seleccione **Invertir confirmación de envíos**.</span><span class="sxs-lookup"><span data-stu-id="f15f3-122">On the Action Pane, on the **Ship and receive** tab, in the **Reverse** group, select **Reverse shipment confirmation**.</span></span>
1. <span data-ttu-id="f15f3-123">En la ficha **Líneas de carga**, seleccione la línea de carga del artículo que supera el porcentaje de sobreentrega.</span><span class="sxs-lookup"><span data-stu-id="f15f3-123">On the **Load lines** tab, select the load line for the item that exceeds the over-delivery percentage.</span></span>
1. <span data-ttu-id="f15f3-124">Seleccione **Reducir la cantidad recolectada** para ajustar la cantidad recogida.</span><span class="sxs-lookup"><span data-stu-id="f15f3-124">Select **Reduce picked quantity** to adjust the picked quantity.</span></span>
1. <span data-ttu-id="f15f3-125">En la pestaña  **Detalles de la línea**, seleccione **Pedido**.</span><span class="sxs-lookup"><span data-stu-id="f15f3-125">On the  **Line details** tab, select **Order**.</span></span>
1. <span data-ttu-id="f15f3-126">Establezca el campo **Cantidad** en la cantidad recogida (es decir, el valor del campo **Cantidad creada por trabajo**), para que pueda ocurrir la generación del albarán.</span><span class="sxs-lookup"><span data-stu-id="f15f3-126">Set the **Quantity** field to the picked quantity (that is, the value of the **Work created quantity** field), so that packing slip generation can proceed.</span></span>

### <a name="adjust-the-over-delivery-percentage"></a><span data-ttu-id="f15f3-127">Ajuste el porcentaje de sobreentrega</span><span class="sxs-lookup"><span data-stu-id="f15f3-127">Adjust the over-delivery percentage</span></span>

<span data-ttu-id="f15f3-128">Utilice el siguiente procedimiento para ajustar el porcentaje de sobreentrega.</span><span class="sxs-lookup"><span data-stu-id="f15f3-128">Use the following procedure to adjust the over-delivery percentage.</span></span>

1. <span data-ttu-id="f15f3-129">Vaya a **Clientes \> Pedidos \> Todos los pedidos**.</span><span class="sxs-lookup"><span data-stu-id="f15f3-129">Go to **Accounts receivable \> Orders \> All orders**.</span></span>
1. <span data-ttu-id="f15f3-130">Seleccione el pedido de cliente para el que no puede contabilizar un albarán para la carga.</span><span class="sxs-lookup"><span data-stu-id="f15f3-130">Select the sales order for which you can't post a packing slip for the load.</span></span>
1. <span data-ttu-id="f15f3-131">En la ficha **Líneas de pedido de ventas**, seleccione la línea de pedido de ventas del artículo que supera el porcentaje de sobreentrega.</span><span class="sxs-lookup"><span data-stu-id="f15f3-131">On the **Sales order lines** tab, select the sales order line for the item that exceeds the over-delivery percentage.</span></span>
1. <span data-ttu-id="f15f3-132">En la pestaña  **Detalles de la línea**, seleccione **Entrega**.</span><span class="sxs-lookup"><span data-stu-id="f15f3-132">On the  **Line details** tab, select **Delivery**.</span></span>
1. <span data-ttu-id="f15f3-133">Estabelzca el campo **Sobreentrega** en un porcentaje mayor que se adapte a la cantidad que se ha recogido frente a la cantidad de carga, de modo que pueda producirse la generación del albarán.</span><span class="sxs-lookup"><span data-stu-id="f15f3-133">Set the **Overdelivery** field to a larger percentage that accommodates the quantity that was picked against the load quantity, so that packing slip generation can proceed.</span></span>

### <a name="reverse-and-make-adjustments"></a><span data-ttu-id="f15f3-134">Invierta y haga ajustes</span><span class="sxs-lookup"><span data-stu-id="f15f3-134">Reverse and make adjustments</span></span>

<span data-ttu-id="f15f3-135">Invierta todo lo que se ha contabilizado para la carga (por ejemplo, el albarán, la confirmación del envío y el trabajo), realice ajustes en la orden de venta, vuelva a enviar la orden al almacén y complete el procedimiento de envío.</span><span class="sxs-lookup"><span data-stu-id="f15f3-135">Reverse everything that has been posted for the load (for example, the packing slip, shipment confirmation, and work), make sales order adjustments, re-release the order to the warehouse, and complete the shipment procedure.</span></span>

<span data-ttu-id="f15f3-136">Utilice el siguiente procedimiento para cancelar un albarán.</span><span class="sxs-lookup"><span data-stu-id="f15f3-136">Use the following procedure to cancel a packing slip.</span></span>

1. <span data-ttu-id="f15f3-137">Vaya a **Gestión de almacenes \> Cargas \> Todas las cargas**.</span><span class="sxs-lookup"><span data-stu-id="f15f3-137">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="f15f3-138">En el panel de acciones, en la pestaña **Enviar y recibir**, en el grupo **Contrarrestar**, seleccione **Cancelar albaranes**.</span><span class="sxs-lookup"><span data-stu-id="f15f3-138">On the Action Pane, on the **Ship and receive** tab, in the **Reverse** group, select **Cancel packing slips**.</span></span>

<span data-ttu-id="f15f3-139">Utilice el siguiente procedimiento para revertir una confirmación de envío.</span><span class="sxs-lookup"><span data-stu-id="f15f3-139">Use the following procedure to reverse a shipment confirmation.</span></span>

1. <span data-ttu-id="f15f3-140">Vaya a **Gestión de almacenes \> Cargas \> Todas las cargas**.</span><span class="sxs-lookup"><span data-stu-id="f15f3-140">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="f15f3-141">En el panel de acciones, en la pestaña **Enviar y recibir**, en el grupo **Contrarrestar**, seleccione **Invertir confirmación de envíos**.</span><span class="sxs-lookup"><span data-stu-id="f15f3-141">On the Action Pane, on the **Ship and receive** tab, in the **Reverse** group, select **Reverse shipment confirmation**.</span></span>

<span data-ttu-id="f15f3-142">Utilice el siguiente procedimiento para revertir el trabajo.</span><span class="sxs-lookup"><span data-stu-id="f15f3-142">Use the following procedure to reverse work.</span></span>

1. <span data-ttu-id="f15f3-143">Vaya a **Gestión de almacenes \> Cargas \> Todas las cargas**.</span><span class="sxs-lookup"><span data-stu-id="f15f3-143">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="f15f3-144">En el panel de acciones, en la pestaña **Cargas**, en el grupo **Trabajo**, seleccione **Invertir el trabajo**.</span><span class="sxs-lookup"><span data-stu-id="f15f3-144">On the Action Pane, on the **Loads** tab, in the **Work** group, select **Reverse work**.</span></span>
