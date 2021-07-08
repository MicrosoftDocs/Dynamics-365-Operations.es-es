---
title: La cantidad excede el porcentaje de entrega insuficiente durante la generación del albarán
description: Cuando genera un albarán, la carga de salida contiene una cantidad que supera el porcentaje de entrega insuficiente.
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
ms.openlocfilehash: ecdd377d12faf40f64736e93671dcf42ff132403
ms.sourcegitcommit: e6437d994c3be0c5bb4a9263af3aa8351020d83a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/14/2021
ms.locfileid: "6249164"
---
# <a name="quantity-exceeds-under-delivery-percentage-during-packing-slip-generation"></a><span data-ttu-id="935f1-103">La cantidad excede el porcentaje de entrega insuficiente durante la generación del albarán</span><span class="sxs-lookup"><span data-stu-id="935f1-103">Quantity exceeds under-delivery percentage during packing slip generation</span></span>

<span data-ttu-id="935f1-104">Código de error: SYS24921</span><span class="sxs-lookup"><span data-stu-id="935f1-104">Error code: SYS24921</span></span>

## <a name="symptoms"></a><span data-ttu-id="935f1-105">Síntomas</span><span class="sxs-lookup"><span data-stu-id="935f1-105">Symptoms</span></span>

<span data-ttu-id="935f1-106">Cuando genera un albarán, la carga de salida contiene una cantidad que supera el porcentaje de entrega insuficiente.</span><span class="sxs-lookup"><span data-stu-id="935f1-106">When you generate a packing slip, the outbound load contains a quantity that exceeds the under-delivery percentage.</span></span>

<span data-ttu-id="935f1-107">Cuando intenta generar un albarán, el sistema muestra el siguiente mensaje de error:</span><span class="sxs-lookup"><span data-stu-id="935f1-107">When you try to generate a packing slip, the system shows the following error message:</span></span>

> <span data-ttu-id="935f1-108">La entrega incompleta de la línea es del %1 %, pero la entrega incompleta permitida es sólo del %2 %.</span><span class="sxs-lookup"><span data-stu-id="935f1-108">Underdelivery of line is %1 percent, but the allowed underdelivery is only %2 percent.</span></span>

<span data-ttu-id="935f1-109">Por lo tanto, no puede generar el albarán de la carga.</span><span class="sxs-lookup"><span data-stu-id="935f1-109">Therefore, you can't generate the packing slip for the load.</span></span>

## <a name="cause"></a><span data-ttu-id="935f1-110">Causa</span><span class="sxs-lookup"><span data-stu-id="935f1-110">Cause</span></span>

<span data-ttu-id="935f1-111">La cantidad recolectada para la carga o envío es menor que la cantidad solicitada y no está dentro del rango del porcentaje de entrega insuficiente.</span><span class="sxs-lookup"><span data-stu-id="935f1-111">The picked quantity for the load or shipment is less than the ordered quantity and isn't within the range of the under-delivery percentage.</span></span>

## <a name="resolution"></a><span data-ttu-id="935f1-112">Resolución</span><span class="sxs-lookup"><span data-stu-id="935f1-112">Resolution</span></span>

<span data-ttu-id="935f1-113">La carga o el envío se encuentran actualmente en un estado en el que falla la generación del albarán.</span><span class="sxs-lookup"><span data-stu-id="935f1-113">The load or shipment is currently in a state where packing slip generation fails.</span></span> <span data-ttu-id="935f1-114">Para solucionar este problema, complete una o más de las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="935f1-114">To fix this issue, complete one of the following tasks:</span></span>

- <span data-ttu-id="935f1-115">Ajuste el porcentaje de infraentrega.</span><span class="sxs-lookup"><span data-stu-id="935f1-115">Adjust the under-delivery percentage.</span></span>
- <span data-ttu-id="935f1-116">Invierta y haga ajustes.</span><span class="sxs-lookup"><span data-stu-id="935f1-116">Reverse and make adjustments.</span></span>

### <a name="adjust-the-under-delivery-percentage"></a><span data-ttu-id="935f1-117">Ajuste el porcentaje de infraentrega</span><span class="sxs-lookup"><span data-stu-id="935f1-117">Adjust the under-delivery percentage</span></span>

<span data-ttu-id="935f1-118">Utilice el siguiente procedimiento para ajustar el porcentaje de entrega insuficiente.</span><span class="sxs-lookup"><span data-stu-id="935f1-118">Use the following procedure to adjust the under-delivery percentage.</span></span>

1. <span data-ttu-id="935f1-119">Vaya a **Clientes \> Pedidos \> Todos los pedidos**.</span><span class="sxs-lookup"><span data-stu-id="935f1-119">Go to **Accounts receivable \> Orders \> All orders**.</span></span>
1. <span data-ttu-id="935f1-120">Seleccione el pedido de cliente para el que no puede contabilizar un albarán para la carga.</span><span class="sxs-lookup"><span data-stu-id="935f1-120">Select the sales order for which you can't post a packing slip for the load.</span></span>
1. <span data-ttu-id="935f1-121">En la ficha **Líneas de pedido de ventas**, seleccione la línea de pedido de ventas del artículo que supera el porcentaje de entrega insuficiente.</span><span class="sxs-lookup"><span data-stu-id="935f1-121">On the **Sales order lines** tab, select the sales order line for the item that exceeds the under-delivery percentage.</span></span>
1. <span data-ttu-id="935f1-122">En la pestaña  **Detalles de la línea**, seleccione **Entrega**.</span><span class="sxs-lookup"><span data-stu-id="935f1-122">On the  **Line details** tab, select **Delivery**.</span></span>
1. <span data-ttu-id="935f1-123">Estabelzca el campo **Infraentrega** en un porcentaje mayor que se adapte a la cantidad que se ha recogido frente a la cantidad de carga, de modo que pueda producirse la generación del albarán.</span><span class="sxs-lookup"><span data-stu-id="935f1-123">Set the **Underdelivery** field to a larger percentage that accommodates the quantity that was picked against the load quantity, so that packing slip generation can proceed.</span></span>

### <a name="reverse-and-make-adjustments"></a><span data-ttu-id="935f1-124">Invierta y haga ajustes</span><span class="sxs-lookup"><span data-stu-id="935f1-124">Reverse and make adjustments</span></span>

<span data-ttu-id="935f1-125">Invierta todo lo que se ha contabilizado para la carga (por ejemplo, el albarán, la confirmación del envío y el trabajo), realice ajustes en la orden de venta, vuelva a enviar la orden al almacén y complete el procedimiento de envío.</span><span class="sxs-lookup"><span data-stu-id="935f1-125">Reverse everything that has been posted for the load (for example, the packing slip, shipment confirmation, and work), make sales order adjustments, re-release the order to the warehouse, and complete the shipment procedure.</span></span>

<span data-ttu-id="935f1-126">Utilice el siguiente procedimiento para cancelar un albarán.</span><span class="sxs-lookup"><span data-stu-id="935f1-126">Use the following procedure to cancel a packing slip.</span></span>

1. <span data-ttu-id="935f1-127">Vaya a **Gestión de almacenes \> Cargas \> Todas las cargas**.</span><span class="sxs-lookup"><span data-stu-id="935f1-127">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="935f1-128">En el panel de acciones, en la pestaña **Enviar y recibir**, en el grupo **Contrarrestar**, seleccione **Cancelar albaranes**.</span><span class="sxs-lookup"><span data-stu-id="935f1-128">On the Action Pane, on the **Ship and receive** tab, in the **Reverse** group, select **Cancel packing slips**.</span></span>

<span data-ttu-id="935f1-129">Utilice el siguiente procedimiento para revertir una confirmación de envío.</span><span class="sxs-lookup"><span data-stu-id="935f1-129">Use the following procedure to reverse a shipment confirmation.</span></span>

1. <span data-ttu-id="935f1-130">Vaya a **Gestión de almacenes \> Cargas \> Todas las cargas**.</span><span class="sxs-lookup"><span data-stu-id="935f1-130">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="935f1-131">En el panel de acciones, en la pestaña **Enviar y recibir**, en el grupo **Contrarrestar**, seleccione **Invertir confirmación de envíos**.</span><span class="sxs-lookup"><span data-stu-id="935f1-131">On the Action Pane, on the **Ship and receive** tab, in the **Reverse** group, select **Reverse shipment confirmation**.</span></span>

<span data-ttu-id="935f1-132">Utilice el siguiente procedimiento para revertir el trabajo.</span><span class="sxs-lookup"><span data-stu-id="935f1-132">Use the following procedure to reverse work.</span></span>

1. <span data-ttu-id="935f1-133">Vaya a **Gestión de almacenes \> Cargas \> Todas las cargas**.</span><span class="sxs-lookup"><span data-stu-id="935f1-133">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="935f1-134">En el panel de acciones, en la pestaña **Cargas**, en el grupo **Trabajo**, seleccione **Invertir el trabajo**.</span><span class="sxs-lookup"><span data-stu-id="935f1-134">On the Action Pane, on the **Loads** tab, in the **Work** group, select **Reverse work**.</span></span>
