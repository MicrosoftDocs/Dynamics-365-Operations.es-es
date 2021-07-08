---
title: El redondeo decimal de la cantidad de actualización física es incorrecto
description: Cuando genera un albarán, la carga de salida contiene una cantidad que no coincide con la precisión decimal definida en la unidad.
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
ms.openlocfilehash: 1e63440834f516879aa8ad711bd789e62b0ee993
ms.sourcegitcommit: e6437d994c3be0c5bb4a9263af3aa8351020d83a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/14/2021
ms.locfileid: "6248803"
---
# <a name="decimal-rounding-of-the-physical-updating-quantity-is-incorrect"></a><span data-ttu-id="07e14-103">El redondeo decimal de la cantidad de actualización física es incorrecto</span><span class="sxs-lookup"><span data-stu-id="07e14-103">Decimal rounding of the physical updating quantity is incorrect</span></span>

<span data-ttu-id="07e14-104">Código de error: SYS19589</span><span class="sxs-lookup"><span data-stu-id="07e14-104">Error code: SYS19589</span></span>

## <a name="symptoms"></a><span data-ttu-id="07e14-105">Síntomas</span><span class="sxs-lookup"><span data-stu-id="07e14-105">Symptoms</span></span>

<span data-ttu-id="07e14-106">Cuando genera un albarán, la carga de salida contiene una cantidad que no coincide con la precisión decimal definida en la unidad.</span><span class="sxs-lookup"><span data-stu-id="07e14-106">When you generate a packing slip, the outbound load contains a quantity that doesn't match the decimal precision that is defined in the unit.</span></span>

<span data-ttu-id="07e14-107">Cuando intenta generar un albarán, el sistema muestra el siguiente mensaje de error:</span><span class="sxs-lookup"><span data-stu-id="07e14-107">When you try to generate a packing slip, the system shows the following error message:</span></span>

> <span data-ttu-id="07e14-108">El redondeo decimal de la cantidad de física de actualización en la unidad %1 no es correcto.</span><span class="sxs-lookup"><span data-stu-id="07e14-108">Decimal rounding of the physical updating quantity in the unit %1 is incorrect.</span></span>

<span data-ttu-id="07e14-109">Por lo tanto, no puede generar el albarán de la carga.</span><span class="sxs-lookup"><span data-stu-id="07e14-109">Therefore, you can't generate the packing slip for the load.</span></span>

## <a name="cause"></a><span data-ttu-id="07e14-110">Causa</span><span class="sxs-lookup"><span data-stu-id="07e14-110">Cause</span></span>

<span data-ttu-id="07e14-111">El sistema evalúa si el redondeo decimal de la cantidad de envío corresponde a la precisión decimal definida para la unidad de envío.</span><span class="sxs-lookup"><span data-stu-id="07e14-111">The system evaluates whether the decimal rounding of the shipping quantity corresponds to the decimal precision that is defined for the shipping unit.</span></span> <span data-ttu-id="07e14-112">Cuando el sistema redondea la cantidad de envío al número especificado de decimales, si encuentra que la cantidad de envío redondeada no coincide con la cantidad de envío real, no puede generar el albarán.</span><span class="sxs-lookup"><span data-stu-id="07e14-112">When the system rounds the shipping quantity to the specified number of decimal places, if it finds that the rounded shipping quantity doesn't match the actual shipping quantity, you can't generate the packing slip.</span></span> <span data-ttu-id="07e14-113">Por ejemplo, este problema puede ocurrir si la cantidad de ventas es 1,75 kilogramos (kg), pero la precisión decimal se establece en *1*.</span><span class="sxs-lookup"><span data-stu-id="07e14-113">For example, this issue might occur if the sales quantity is 1.75 kilograms (kg), but the decimal precision is set to *1*.</span></span>

## <a name="resolution"></a><span data-ttu-id="07e14-114">Resolución</span><span class="sxs-lookup"><span data-stu-id="07e14-114">Resolution</span></span>

<span data-ttu-id="07e14-115">La carga o el envío se encuentran actualmente en un estado en el que falla la generación del albarán.</span><span class="sxs-lookup"><span data-stu-id="07e14-115">The load or shipment is currently in a state where packing slip generation fails.</span></span> <span data-ttu-id="07e14-116">Para solucionar este problema, complete una o más de las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="07e14-116">To fix this issue, complete one of the following tasks:</span></span>

- <span data-ttu-id="07e14-117">Revise sus líneas de carga y realice ajustes para asegurarse de que la cantidad se pueda convertir limpiamente sin números decimales y cualquier otro problema de redondeo.</span><span class="sxs-lookup"><span data-stu-id="07e14-117">Review your load lines, and make adjustments to ensure that the quantity can be cleanly converted without decimal numbers and any other rounding issues.</span></span>
- <span data-ttu-id="07e14-118">Revise sus líneas de carga y realice ajustes para asegurarse de que la unidad y la cantidad estén alineadas con la precisión decimal de la unidad.</span><span class="sxs-lookup"><span data-stu-id="07e14-118">Review your load lines, and make adjustments to ensure that the unit and quantity are aligned with the decimal precision of the unit.</span></span>

### <a name="review-your-load-lines-and-make-adjustments-to-ensure-that-the-quantity-can-be-cleanly-converted-without-decimal-numbers-and-any-other-rounding-issues"></a><span data-ttu-id="07e14-119">Revise sus líneas de carga y realice ajustes para asegurarse de que la cantidad se pueda convertir limpiamente sin números decimales y cualquier otro problema de redondeo</span><span class="sxs-lookup"><span data-stu-id="07e14-119">Review your load lines, and make adjustments to ensure that the quantity can be cleanly converted without decimal numbers and any other rounding issues</span></span>

<span data-ttu-id="07e14-120">Use el siguiente procedimiento para revisar las líneas de carga y realizar ajustes para asegurarse de que la cantidad se pueda convertir limpiamente sin números decimales y cualquier otro problema de redondeo.</span><span class="sxs-lookup"><span data-stu-id="07e14-120">Use the following procedure to review your load lines and make adjustments to ensure that the quantity can be cleanly converted without decimal numbers and any other rounding issues.</span></span>

1. <span data-ttu-id="07e14-121">Vaya a **Gestión de almacenes \> Cargas \> Todas las cargas**.</span><span class="sxs-lookup"><span data-stu-id="07e14-121">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="07e14-122">Seleccione la carga para la que el albarán no se puede generar.</span><span class="sxs-lookup"><span data-stu-id="07e14-122">Select the load that the packing slip can't be generated for.</span></span>
1. <span data-ttu-id="07e14-123">En el panel de acciones, en la pestaña **Enviar y recibir**, en el grupo **Contrarrestar**, seleccione **Invertir confirmación de envíos**.</span><span class="sxs-lookup"><span data-stu-id="07e14-123">On the Action Pane, on the **Ship and receive** tab, in the **Reverse** group, select **Reverse shipment confirmation**.</span></span>
1. <span data-ttu-id="07e14-124">En la pestaña  **Líneas de carga**, seleccione la línea de carga para el artículo que causa un problema.</span><span class="sxs-lookup"><span data-stu-id="07e14-124">On the **Load lines** tab, select the load line for the item that causes an issue.</span></span>
1. <span data-ttu-id="07e14-125">Seleccione **Reducir la cantidad recolectada** para ajustar la cantidad recogida.</span><span class="sxs-lookup"><span data-stu-id="07e14-125">Select **Reduce picked quantity** to adjust the picked quantity.</span></span>
1. <span data-ttu-id="07e14-126">En la pestaña  **Detalles de la línea**, seleccione **Pedido**.</span><span class="sxs-lookup"><span data-stu-id="07e14-126">On the  **Line details** tab, select **Order**.</span></span>
1. <span data-ttu-id="07e14-127">Establezca el campo **Cantidad** en la cantidad recogida (es decir, el valor del campo **Cantidad creada por trabajo**), para que pueda ocurrir la generación del albarán.</span><span class="sxs-lookup"><span data-stu-id="07e14-127">Set the **Quantity** field to the picked quantity (that is, the value of the **Work created quantity** field), so that packing slip generation can proceed.</span></span>

### <a name="review-your-load-lines-and-make-adjustments-to-ensure-that-the-unit-and-quantity-are-aligned-with-the-decimal-precision-of-the-unit"></a><span data-ttu-id="07e14-128">Revise sus líneas de carga y realice ajustes para asegurarse de que la unidad y la cantidad estén alineadas con la precisión decimal de la unidad</span><span class="sxs-lookup"><span data-stu-id="07e14-128">Review your load lines, and make adjustments to ensure that the unit and quantity are aligned with the decimal precision of the unit</span></span>

<span data-ttu-id="07e14-129">Use el procedimiento siguiente para revisar sus líneas de carga y realice ajustes para asegurarse de que la unidad y la cantidad estén alineadas con la precisión decimal de la unidad.</span><span class="sxs-lookup"><span data-stu-id="07e14-129">Use the following procedure to review your load lines and make adjustments to ensure that the unit and quantity are aligned with the decimal precision of the unit.</span></span>

1. <span data-ttu-id="07e14-130">Vaya a **Gestión de almacenes \> Cargas \> Todas las cargas**.</span><span class="sxs-lookup"><span data-stu-id="07e14-130">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="07e14-131">Seleccione la carga para la que el albarán no se puede generar.</span><span class="sxs-lookup"><span data-stu-id="07e14-131">Select the load that the packing slip can't be generated for.</span></span>
1. <span data-ttu-id="07e14-132">En la ficha desplegable **Líneas de carga**, seleccione la línea de carga para el artículo que causa un problema.</span><span class="sxs-lookup"><span data-stu-id="07e14-132">On the **Load lines** FastTab, select the load line for the item that causes an issue.</span></span> <span data-ttu-id="07e14-133">Anote el valor de los campos **Cantidad** y **Unidad**.</span><span class="sxs-lookup"><span data-stu-id="07e14-133">Make a note of the value of the **Quantity** and **Unit** fields.</span></span>
1. <span data-ttu-id="07e14-134">Vaya a **Administración de la organización \> Unidades \> Unidades**.</span><span class="sxs-lookup"><span data-stu-id="07e14-134">Go to **Organization administration \> Units \> Units**.</span></span>
1. <span data-ttu-id="07e14-135">Seleccione la unidad para la que el albarán no se puede generar.</span><span class="sxs-lookup"><span data-stu-id="07e14-135">Select the unit that the packing slip can't be generated for.</span></span>
1. <span data-ttu-id="07e14-136">Ajuste el valor del campo **Precisión decimal** según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="07e14-136">Adjust the value of the **Decimal precision** field as required.</span></span>
