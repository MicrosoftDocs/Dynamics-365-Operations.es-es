---
title: La cantidad física de actualización en la unidad tiene que ser distinta de cero
description: Cuando genera un albarán, los datos que se le proporcionan tienen una cantidad de inventario distinta de cero pero una cantidad de ventas cero.
author: GalynaFedorova
ms.date: 5/31/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadPlanningListPage_WHSSalesPackingSlipPost, WHSLoadTable_WHSSalesPackingSlipPost
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: bfd381160bcfd1e6e5489e16cc22178b8a5142ee
ms.sourcegitcommit: e6437d994c3be0c5bb4a9263af3aa8351020d83a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/14/2021
ms.locfileid: "6248802"
---
# <a name="physical-remaining-quantity-in-the-unit-must-not-be-zero"></a><span data-ttu-id="d35eb-103">La cantidad física de actualización en la unidad tiene que ser distinta de cero</span><span class="sxs-lookup"><span data-stu-id="d35eb-103">Physical remaining quantity in the unit must not be zero</span></span>

<span data-ttu-id="d35eb-104">Código de error: SYS19591</span><span class="sxs-lookup"><span data-stu-id="d35eb-104">Error code: SYS19591</span></span>

## <a name="symptoms"></a><span data-ttu-id="d35eb-105">Síntomas</span><span class="sxs-lookup"><span data-stu-id="d35eb-105">Symptoms</span></span>

<span data-ttu-id="d35eb-106">Cuando genera un albarán, los datos que se le proporcionan tienen una cantidad de inventario distinta de cero pero una cantidad de ventas cero.</span><span class="sxs-lookup"><span data-stu-id="d35eb-106">When you generate a packing slip, the data that is supplied to it has a non-zero inventory quantity but a zero sales quantity.</span></span>

<span data-ttu-id="d35eb-107">Cuando intenta generar un albarán, el sistema muestra el siguiente mensaje de error:</span><span class="sxs-lookup"><span data-stu-id="d35eb-107">When you try to generate the packing slip, the system shows the following error message:</span></span>

> <span data-ttu-id="d35eb-108">La cantidad física de actualización en la unidad %1 tiene que ser distinta de cero.</span><span class="sxs-lookup"><span data-stu-id="d35eb-108">Physical remaining quantity in the unit %1 must be other than zero.</span></span>

<span data-ttu-id="d35eb-109">Por lo tanto, no puede generar el albarán de la carga.</span><span class="sxs-lookup"><span data-stu-id="d35eb-109">Therefore, you can't generate the packing slip for the load.</span></span>

## <a name="cause"></a><span data-ttu-id="d35eb-110">Causa</span><span class="sxs-lookup"><span data-stu-id="d35eb-110">Cause</span></span>

<span data-ttu-id="d35eb-111">El sistema evalúa la cantidad física restante en la unidad de inventario y la cantidad física restante en la unidad de envío.</span><span class="sxs-lookup"><span data-stu-id="d35eb-111">The system evaluates the physical remaining quantity in the inventory unit and the physical remaining quantity in the shipping unit.</span></span> <span data-ttu-id="d35eb-112">Si el sistema encuentra que la cantidad física restante en la unidad de envío es 0 (cero), pero la cantidad física restante en la unidad de inventario no es 0, no puede generar el albarán.</span><span class="sxs-lookup"><span data-stu-id="d35eb-112">If the system finds that the physical remaining quantity in the shipping unit is 0 (zero), but the physical remaining quantity in the inventory unit isn't 0, you can't generate the packing slip.</span></span> <span data-ttu-id="d35eb-113">Por ejemplo, este problema puede ocurrir si la unidad de ventas y la unidad de inventario del artículo difieren y la conversión entre unidades no es precisa.</span><span class="sxs-lookup"><span data-stu-id="d35eb-113">For example, this issue might occur if the sales unit and inventory unit for the item differ, and the conversion between units isn't accurate.</span></span>

## <a name="resolution"></a><span data-ttu-id="d35eb-114">Resolución</span><span class="sxs-lookup"><span data-stu-id="d35eb-114">Resolution</span></span>

<span data-ttu-id="d35eb-115">La carga o el envío se encuentran actualmente en un estado en el que falla la generación del albarán.</span><span class="sxs-lookup"><span data-stu-id="d35eb-115">The load or shipment is currently in a state where packing slip generation fails.</span></span> <span data-ttu-id="d35eb-116">Para solucionar este problema, complete una o más de las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="d35eb-116">To fix this issue, complete one of the following tasks:</span></span>

- <span data-ttu-id="d35eb-117">Revise las líneas de carga y asegúrese de que todo el trabajo relacionado se haya completado en la ubicación de envío final y que las cantidades coincidan.</span><span class="sxs-lookup"><span data-stu-id="d35eb-117">Review your load lines, and make sure that all the related work has been completed at the final shipping location, and that the quantities match.</span></span>
- <span data-ttu-id="d35eb-118">Revise sus líneas de carga y realice ajustes para asegurarse de que la cantidad se pueda convertir limpiamente sin problemas de redondeo.</span><span class="sxs-lookup"><span data-stu-id="d35eb-118">Review your load lines, and make adjustments to ensure that the quantity can be cleanly converted without rounding issues.</span></span>
- <span data-ttu-id="d35eb-119">Revise sus líneas de carga y realice ajustes para asegurarse de que la unidad y la cantidad estén alineadas con la precisión decimal de la unidad.</span><span class="sxs-lookup"><span data-stu-id="d35eb-119">Review your load lines, and make adjustments to ensure that the unit and quantity are aligned with the decimal precision of the unit.</span></span>
- <span data-ttu-id="d35eb-120">Asegúrese de que la unidad de medida del inventario sea menor que la unidad de medida de las ventas.</span><span class="sxs-lookup"><span data-stu-id="d35eb-120">Make sure that the inventory unit of measure is smaller than the sales unit of measure.</span></span>

### <a name="review-your-load-lines-and-make-sure-that-all-the-related-work-has-been-completed-at-the-final-shipping-location-and-that-the-quantities-match"></a><span data-ttu-id="d35eb-121">Revise las líneas de carga y asegúrese de que todo el trabajo relacionado se haya completado en la ubicación de envío final y que las cantidades coincidan</span><span class="sxs-lookup"><span data-stu-id="d35eb-121">Review your load lines, and make sure that all the related work has been completed at the final shipping location, and that the quantities match</span></span>

<span data-ttu-id="d35eb-122">Use el siguiente procedimiento para revisar las líneas de carga y asegúrese de que todo el trabajo relacionado se haya completado en la ubicación de envío final y que las cantidades coincidan.</span><span class="sxs-lookup"><span data-stu-id="d35eb-122">Use the following procedure to review your load lines and make sure that all the related work has been completed at the final shipping location, and that the quantities match.</span></span>

1. <span data-ttu-id="d35eb-123">Vaya a **Gestión de almacenes \> Cargas \> Todas las cargas**.</span><span class="sxs-lookup"><span data-stu-id="d35eb-123">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="d35eb-124">Seleccione la carga para la que el envío no se puede confirmar.</span><span class="sxs-lookup"><span data-stu-id="d35eb-124">Select the load that the shipment can't be confirmed for.</span></span>
1. <span data-ttu-id="d35eb-125">En la ficha desplegable **Líneas de carga**, seleccione la línea de carga.</span><span class="sxs-lookup"><span data-stu-id="d35eb-125">On the **Load lines** FastTab, select the load line.</span></span>
1. <span data-ttu-id="d35eb-126">Anote el valor del campo **Cantidad de trabajo creado**.</span><span class="sxs-lookup"><span data-stu-id="d35eb-126">Make a note of the value of the **Work created quantity** field.</span></span>
1. <span data-ttu-id="d35eb-127">En el panel de acciones, en la pestaña **Cargas** del grupo **Información relacionada**, seleccione **Trabajo**.</span><span class="sxs-lookup"><span data-stu-id="d35eb-127">On the Action Pane, on the **Loads** tab, in the **Related information** group, select **Work**.</span></span>
1. <span data-ttu-id="d35eb-128">Verifique que el trabajo se haya completado en la ubicación de envío final y que la cantidad de trabajo recogido coincida con la cantidad de trabajo creada en la línea de carga.</span><span class="sxs-lookup"><span data-stu-id="d35eb-128">Verify that the work has been completed at the final shipping location, and that the picked work quantity matches the created work quantity on the load line.</span></span>
1. <span data-ttu-id="d35eb-129">Repita este procedimiento para todas las líneas de carga para asegurarse de que se cumplan todos los criterios.</span><span class="sxs-lookup"><span data-stu-id="d35eb-129">Repeat this procedure for all load lines to make sure that all criteria are met.</span></span>

### <a name="review-your-load-lines-and-make-adjustments-to-ensure-that-the-quantity-can-be-cleanly-converted-without-rounding-issues"></a><span data-ttu-id="d35eb-130">Revise sus líneas de carga y realice ajustes para asegurarse de que la cantidad se pueda convertir limpiamente sin problemas de redondeo</span><span class="sxs-lookup"><span data-stu-id="d35eb-130">Review your load lines, and make adjustments to ensure that the quantity can be cleanly converted without rounding issues</span></span>

<span data-ttu-id="d35eb-131">Use el siguiente procedimiento para revisar las líneas de carga y realizar ajustes para asegurarse de que la cantidad se pueda convertir limpiamente sin problemas de redondeo.</span><span class="sxs-lookup"><span data-stu-id="d35eb-131">Use the following procedure to review your load lines and make adjustments to ensure that the quantity can be cleanly converted without rounding issues.</span></span>

1. <span data-ttu-id="d35eb-132">Vaya a **Gestión de almacenes \> Cargas \> Todas las cargas**.</span><span class="sxs-lookup"><span data-stu-id="d35eb-132">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="d35eb-133">Seleccione la carga para la que el albarán no se puede generar.</span><span class="sxs-lookup"><span data-stu-id="d35eb-133">Select the load that the packing slip can't be generated for.</span></span>
1. <span data-ttu-id="d35eb-134">En el panel de acciones, en la pestaña **Enviar y recibir**, en el grupo **Contrarrestar**, seleccione **Invertir confirmación de envíos**.</span><span class="sxs-lookup"><span data-stu-id="d35eb-134">On the Action Pane, on the **Ship and receive** tab, in the **Reverse** group, select **Reverse shipment confirmation**.</span></span>
1. <span data-ttu-id="d35eb-135">En la ficha **Líneas de carga**, seleccione la línea de carga del artículo que supera la sobreentrega.</span><span class="sxs-lookup"><span data-stu-id="d35eb-135">On the **Load lines** tab, select the load line for the item that exceeds the over-delivery.</span></span>
1. <span data-ttu-id="d35eb-136">Seleccione **Reducir la cantidad recolectada** para ajustar la cantidad recogida.</span><span class="sxs-lookup"><span data-stu-id="d35eb-136">Select **Reduce picked quantity** to adjust the picked quantity.</span></span>
1. <span data-ttu-id="d35eb-137">En la pestaña  **Detalles de la línea**, seleccione **Pedido**.</span><span class="sxs-lookup"><span data-stu-id="d35eb-137">On the  **Line details** tab, select **Order**.</span></span>
1. <span data-ttu-id="d35eb-138">Establezca el campo **Cantidad** en la cantidad recogida (es decir, el valor del campo **Cantidad creada por trabajo**), para que pueda ocurrir la generación del albarán.</span><span class="sxs-lookup"><span data-stu-id="d35eb-138">Set the **Quantity** field to the picked quantity (that is, the value of the **Work created quantity** field), so that packing slip generation can proceed.</span></span>

### <a name="review-your-load-lines-and-make-adjustments-to-ensure-that-the-unit-and-quantity-are-aligned-with-the-decimal-precision-of-the-unit"></a><span data-ttu-id="d35eb-139">Revise sus líneas de carga y realice ajustes para asegurarse de que la unidad y la cantidad estén alineadas con la precisión decimal de la unidad</span><span class="sxs-lookup"><span data-stu-id="d35eb-139">Review your load lines, and make adjustments to ensure that the unit and quantity are aligned with the decimal precision of the unit</span></span>

<span data-ttu-id="d35eb-140">Use el procedimiento siguiente para revisar sus líneas de carga y realice ajustes para asegurarse de que la unidad y la cantidad estén alineadas con la precisión decimal de la unidad.</span><span class="sxs-lookup"><span data-stu-id="d35eb-140">Use the following procedure to review your load lines and make adjustments to ensure that the unit and quantity are aligned with the decimal precision of the unit.</span></span>

1. <span data-ttu-id="d35eb-141">Vaya a **Gestión de almacenes \> Cargas \> Todas las cargas**.</span><span class="sxs-lookup"><span data-stu-id="d35eb-141">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="d35eb-142">Seleccione la carga para la que el albarán no se puede generar.</span><span class="sxs-lookup"><span data-stu-id="d35eb-142">Select the load that the packing slip can't be generated for.</span></span>
1. <span data-ttu-id="d35eb-143">En la ficha desplegable **Líneas de carga**, seleccione la línea de carga para el artículo que causa un problema.</span><span class="sxs-lookup"><span data-stu-id="d35eb-143">On the **Load lines** FastTab, select the load line for the item that causes an issue.</span></span> <span data-ttu-id="d35eb-144">Anote el valor de los campos **Cantidad** y **Unidad**.</span><span class="sxs-lookup"><span data-stu-id="d35eb-144">Make a note of the value of the **Quantity** and **Unit** fields.</span></span>
1. <span data-ttu-id="d35eb-145">Vaya a **Administración de la organización \> Unidades \> Unidades**.</span><span class="sxs-lookup"><span data-stu-id="d35eb-145">Go to **Organization administration \> Units \> Units**.</span></span>
1. <span data-ttu-id="d35eb-146">Seleccione la unidad para la que el albarán no se puede generar.</span><span class="sxs-lookup"><span data-stu-id="d35eb-146">Select the unit that the packing slip can't be generated for.</span></span>
1. <span data-ttu-id="d35eb-147">Ajuste el valor del campo **Precisión decimal** según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="d35eb-147">Adjust the value of the **Decimal precision** field as required.</span></span>

### <a name="make-sure-that-the-inventory-unit-of-measure-is-smaller-than-the-sales-unit-of-measure"></a><span data-ttu-id="d35eb-148">Asegúrese de que la unidad de medida del inventario sea menor que la unidad de medida de las ventas</span><span class="sxs-lookup"><span data-stu-id="d35eb-148">Make sure that the inventory unit of measure is smaller than the sales unit of measure</span></span>

<span data-ttu-id="d35eb-149">Asegúrese de que la unidad de medida del inventario sea menor que la unidad de medida de las ventas.</span><span class="sxs-lookup"><span data-stu-id="d35eb-149">Make sure that the inventory unit of measure is smaller than the sales unit of measure.</span></span> <span data-ttu-id="d35eb-150">Considere la posibilidad de reconfigurar la unidad de medida del artículo según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="d35eb-150">Consider reconfiguring the unit of measure for the item as required.</span></span>
