---
title: La cantidad seleccionada no es suficiente durante la generación del albarán
description: Cuando genera un albarán, la carga de salida contiene una cantidad seleccionada que no coincide con la cantidad de trabajo creada en la línea de carga.
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
ms.openlocfilehash: fa6054dc26e4306ec16e37b0e6c320342ed40fe0
ms.sourcegitcommit: e6437d994c3be0c5bb4a9263af3aa8351020d83a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/14/2021
ms.locfileid: "6249168"
---
# <a name="picked-quantity-isnt-sufficient-during-packing-slip-generation"></a><span data-ttu-id="a891a-103">La cantidad seleccionada no es suficiente durante la generación del albarán</span><span class="sxs-lookup"><span data-stu-id="a891a-103">Picked quantity isn't sufficient during packing slip generation</span></span>

<span data-ttu-id="a891a-104">Código de error: SYS54073</span><span class="sxs-lookup"><span data-stu-id="a891a-104">Error code: SYS54073</span></span>

## <a name="symptoms"></a><span data-ttu-id="a891a-105">Síntomas</span><span class="sxs-lookup"><span data-stu-id="a891a-105">Symptoms</span></span>

<span data-ttu-id="a891a-106">Cuando genera un albarán, la carga de salida contiene una cantidad seleccionada que no coincide con la cantidad de trabajo creada en la línea de carga.</span><span class="sxs-lookup"><span data-stu-id="a891a-106">When you generate a packing slip, the outbound load contains a picked quantity that doesn't match the created work quantity on the load line.</span></span>

<span data-ttu-id="a891a-107">Cuando intenta generar un albarán, el sistema muestra el siguiente mensaje de error:</span><span class="sxs-lookup"><span data-stu-id="a891a-107">When you try to generate a packing slip, the system shows the following error message:</span></span>

> <span data-ttu-id="a891a-108">Como %1 se han seleccionado, no es suficiente actualizar %2, cuando, por consiguiente, el resto debe ser %3.</span><span class="sxs-lookup"><span data-stu-id="a891a-108">As %1 have been picked, it is not sufficient to update %2, when, subsequently, the remainder must be %3.</span></span>

<span data-ttu-id="a891a-109">Por lo tanto, no puede generar el albarán de la carga.</span><span class="sxs-lookup"><span data-stu-id="a891a-109">Therefore, you can't generate the packing slip for the load.</span></span>

## <a name="cause"></a><span data-ttu-id="a891a-110">Causa</span><span class="sxs-lookup"><span data-stu-id="a891a-110">Cause</span></span>

<span data-ttu-id="a891a-111">El albarán no se puede generar en su estado actual porque podría existir una de las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="a891a-111">The packing slip can't be generated in its current state because one of the following conditions might exist:</span></span>

- <span data-ttu-id="a891a-112">El trabajo relacionado aún no se ha seleccionado y trasladado a la ubicación de envío final.</span><span class="sxs-lookup"><span data-stu-id="a891a-112">The related work hasn't yet been picked and moved to the final shipping location.</span></span>
- <span data-ttu-id="a891a-113">La cantidad de trabajo escogido no coincide con la cantidad de trabajo creada en la línea de carga.</span><span class="sxs-lookup"><span data-stu-id="a891a-113">The picked work quantity doesn't match the created work quantity on the load line.</span></span>
- <span data-ttu-id="a891a-114">La cantidad de línea de carga, la cantidad de trabajo creada y la cantidad elegida no coinciden.</span><span class="sxs-lookup"><span data-stu-id="a891a-114">The load line quantity, work created quantity, and picked quantity don't match.</span></span>

## <a name="resolution"></a><span data-ttu-id="a891a-115">Resolución</span><span class="sxs-lookup"><span data-stu-id="a891a-115">Resolution</span></span>

<span data-ttu-id="a891a-116">La carga o el envío se encuentran actualmente en un estado en el que falla la generación del albarán.</span><span class="sxs-lookup"><span data-stu-id="a891a-116">The load or shipment is currently in a state where packing slip generation fails.</span></span> <span data-ttu-id="a891a-117">Para solucionar este problema, complete una o más de las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="a891a-117">To fix this issue, complete one of the following tasks:</span></span>

- <span data-ttu-id="a891a-118">Revise las líneas de carga y asegúrese de que todo el trabajo relacionado se haya completado en la ubicación de envío final y que las cantidades coincidan.</span><span class="sxs-lookup"><span data-stu-id="a891a-118">Review your load lines, and make sure that all the related work has been completed at the final shipping location, and that the quantities match.</span></span>
- <span data-ttu-id="a891a-119">Ajuste la cantidad de la línea de carga.</span><span class="sxs-lookup"><span data-stu-id="a891a-119">Adjust the load line quantity.</span></span>
- <span data-ttu-id="a891a-120">Invierta todos los registros de picking y vuelva a realizar el picking.</span><span class="sxs-lookup"><span data-stu-id="a891a-120">Reverse all pick registrations, and redo picking.</span></span>

### <a name="review-your-load-lines-and-make-sure-that-all-the-related-work-has-been-completed-at-the-final-shipping-location-and-that-the-quantities-match"></a><span data-ttu-id="a891a-121">Revise las líneas de carga y asegúrese de que todo el trabajo relacionado se haya completado en la ubicación de envío final y que las cantidades coincidan</span><span class="sxs-lookup"><span data-stu-id="a891a-121">Review your load lines, and make sure that all the related work has been completed at the final shipping location, and that the quantities match</span></span>

<span data-ttu-id="a891a-122">Use el siguiente procedimiento para revisar las líneas de carga y asegúrese de que todo el trabajo relacionado se haya completado en la ubicación de envío final y que las cantidades coincidan.</span><span class="sxs-lookup"><span data-stu-id="a891a-122">Use the following procedure to review your load lines and make sure that all the related work has been completed at the final shipping location, and that the quantities match.</span></span>

1. <span data-ttu-id="a891a-123">Vaya a **Gestión de almacenes \> Cargas \> Todas las cargas**.</span><span class="sxs-lookup"><span data-stu-id="a891a-123">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="a891a-124">Seleccione la carga para la que el albarán no se puede generar.</span><span class="sxs-lookup"><span data-stu-id="a891a-124">Select the load that the packing slip can't be generated for.</span></span>
1. <span data-ttu-id="a891a-125">En la ficha desplegable **Líneas de carga**, seleccione la línea de carga.</span><span class="sxs-lookup"><span data-stu-id="a891a-125">On the **Load lines** FastTab, select the load line.</span></span>
1. <span data-ttu-id="a891a-126">Anote el valor del campo **Cantidad de trabajo creado**.</span><span class="sxs-lookup"><span data-stu-id="a891a-126">Make a note of the value of the **Work created quantity** field.</span></span>
1. <span data-ttu-id="a891a-127">En el panel de acciones, en la pestaña **Cargas** del grupo **Información relacionada**, seleccione **Trabajo**.</span><span class="sxs-lookup"><span data-stu-id="a891a-127">On the Action Pane, on the **Loads** tab, in the **Related information** group, select **Work**.</span></span>
1. <span data-ttu-id="a891a-128">Verifique que el trabajo se haya completado en la ubicación de envío final y que la cantidad de trabajo recogido coincida con la cantidad de trabajo creada en la línea de carga.</span><span class="sxs-lookup"><span data-stu-id="a891a-128">Verify that the work has been completed at the final shipping location, and that the picked work quantity matches the created work quantity on the load line.</span></span>
1. <span data-ttu-id="a891a-129">Repita este procedimiento para todas las líneas de carga para asegurarse de que se cumplan todos los criterios.</span><span class="sxs-lookup"><span data-stu-id="a891a-129">Repeat this procedure for all load lines to make sure that all criteria are met.</span></span>

### <a name="adjust-the-load-line-quantity"></a><span data-ttu-id="a891a-130">Ajuste la cantidad de la línea de carga</span><span class="sxs-lookup"><span data-stu-id="a891a-130">Adjust the load line quantity</span></span>

<span data-ttu-id="a891a-131">Utilice el siguiente procedimiento para ajustar la cantidad de la línea de carga.</span><span class="sxs-lookup"><span data-stu-id="a891a-131">Use the following procedure to adjust the load line quantity.</span></span>

1. <span data-ttu-id="a891a-132">Vaya a **Gestión de almacenes \> Cargas \> Todas las cargas**.</span><span class="sxs-lookup"><span data-stu-id="a891a-132">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="a891a-133">Seleccione la carga para la que el albarán no se puede generar.</span><span class="sxs-lookup"><span data-stu-id="a891a-133">Select the load that the packing slip can't be generated for.</span></span>
1. <span data-ttu-id="a891a-134">En el panel de acciones, en la pestaña **Enviar y recibir**, en el grupo **Contrarrestar**, seleccione **Invertir confirmación de envíos**.</span><span class="sxs-lookup"><span data-stu-id="a891a-134">On the Action Pane, on the **Ship and receive** tab, in the **Reverse** group, select **Reverse shipment confirmation**.</span></span>
1. <span data-ttu-id="a891a-135">En la pestaña  **Líneas de carga**, seleccione la línea de carga para el artículo que causa un problema.</span><span class="sxs-lookup"><span data-stu-id="a891a-135">On the **Load lines** tab, select the load line for the item that causes an issue.</span></span>
1. <span data-ttu-id="a891a-136">Seleccione **Reducir la cantidad recolectada** para ajustar la cantidad recogida.</span><span class="sxs-lookup"><span data-stu-id="a891a-136">Select **Reduce picked quantity** to adjust the picked quantity.</span></span>
1. <span data-ttu-id="a891a-137">Seleccione el campo **Reducir la línea de carga** para reflejar los ajustes en la línea de carga.</span><span class="sxs-lookup"><span data-stu-id="a891a-137">Set the **Reduce load line** field to reflect adjustments on the load line.</span></span>

### <a name="reverse-all-pick-registrations-and-redo-picking"></a><span data-ttu-id="a891a-138">Invierta todos los registros de picking y vuelva a realizar el picking</span><span class="sxs-lookup"><span data-stu-id="a891a-138">Reverse all pick registrations, and redo picking</span></span>

<span data-ttu-id="a891a-139">El problema puede ocurrir porque alguien usó el registro de picking para cerrar una línea de carga sin trabajo.</span><span class="sxs-lookup"><span data-stu-id="a891a-139">The issue might occur because someone used pick registration to close a load line without work.</span></span> <span data-ttu-id="a891a-140">En este caso, se debe revertir el registro de picking manual y luego se debe completar el picking mediante la aplicación móvil Warehouse Management.</span><span class="sxs-lookup"><span data-stu-id="a891a-140">In this case, manual pick registration must be reversed, and picking must then be completed by using the Warehouse Management mobile app.</span></span>

<span data-ttu-id="a891a-141">Utilice el siguiente procedimiento para invertir el registro de recogida.</span><span class="sxs-lookup"><span data-stu-id="a891a-141">Use the following procedure to reverse the pick registration.</span></span>

1. <span data-ttu-id="a891a-142">Vaya a **Clientes \> Pedidos \> Todos los pedidos**.</span><span class="sxs-lookup"><span data-stu-id="a891a-142">Go to **Accounts receivable \> Orders \> All orders**.</span></span>
1. <span data-ttu-id="a891a-143">Seleccione el pedido de cliente para el que no puede contabilizar un albarán para la carga.</span><span class="sxs-lookup"><span data-stu-id="a891a-143">Select the sales order for which you can't post a packing slip for the load.</span></span>
1. <span data-ttu-id="a891a-144">Sobre la pesetaña **Líneas de orden de venta**, seleccione la línea de orden de venta para la que se realizó el registro de picking.</span><span class="sxs-lookup"><span data-stu-id="a891a-144">On the **Sales order lines** tab, select the sales order line that pick registration was done for.</span></span>
1. <span data-ttu-id="a891a-145">Seleccione **Línea de actualización \> Elegir** para despegar los artículos.</span><span class="sxs-lookup"><span data-stu-id="a891a-145">Select **Update line \> Pick** to unpick the items.</span></span>
