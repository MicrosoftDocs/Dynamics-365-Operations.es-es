---
title: Códigos de motivo para recuento de inventario
description: En este tema se describe cómo configurar y aplicar códigos de motivo para tareas de recuento.
author: Mirzaab
manager: tfehr
ms.date: 03/15/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventCountingReasonCodePolicy, InventCountingReasonCode
audience: Application User
ms.reviewer: kamaybac
ms.custom: 1705903
ms.assetid: 427e01b3-4968-4cff-9b85-1717530f72e4
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: 66e1fb9f32aa31221f85180339b8b6ee55836be1
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4996157"
---
# <a name="reason-codes-for-inventory-counting"></a><span data-ttu-id="18c40-103">Códigos de motivo para recuento de inventario</span><span class="sxs-lookup"><span data-stu-id="18c40-103">Reason codes for inventory counting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="18c40-104">Los códigos de motivo le permiten analizar los resultados de un proceso de recuento y cualquier discrepancia que surja durante dicho proceso.</span><span class="sxs-lookup"><span data-stu-id="18c40-104">Reason codes let you analyze the results of a counting process and any discrepancies that occur during that process.</span></span> <span data-ttu-id="18c40-105">Puede especificar el motivo por el que se realiza el recuento, como un pallet roto o un ajuste de existencias basado en ejemplos de inventario.</span><span class="sxs-lookup"><span data-stu-id="18c40-105">You can specify the reason for doing the count, such as a broken pallet or a stock adjustment that is based on inventory samples.</span></span>

## <a name="recommendation"></a><span data-ttu-id="18c40-106">Recomendación</span><span class="sxs-lookup"><span data-stu-id="18c40-106">Recommendation</span></span>

<span data-ttu-id="18c40-107">Antes de configurar el sistema, le recomendamos que defina una estrategia para trabajar con códigos de motivo.</span><span class="sxs-lookup"><span data-stu-id="18c40-107">Before you set up the system, we recommend that you define a strategy for working with reason codes.</span></span> <span data-ttu-id="18c40-108">Por ejemplo, intente responder a las siguientes preguntas:</span><span class="sxs-lookup"><span data-stu-id="18c40-108">For example, try to answer the following questions:</span></span>

- <span data-ttu-id="18c40-109">¿Los códigos de motivo deben ser obligatorios en los almacenes?</span><span class="sxs-lookup"><span data-stu-id="18c40-109">Should reason codes be mandatory on warehouses?</span></span>
- <span data-ttu-id="18c40-110">¿Los códigos de motivo deben ser obligatorios u opcionales en algunos artículos?</span><span class="sxs-lookup"><span data-stu-id="18c40-110">Should reason codes be mandatory or optional on some items?</span></span>
- <span data-ttu-id="18c40-111">¿Cuántos códigos de motivo necesita?</span><span class="sxs-lookup"><span data-stu-id="18c40-111">How many reason codes do you require?</span></span>
- <span data-ttu-id="18c40-112">¿Cómo deben usar los usuarios de escáneres de códigos de barras los códigos de motivo?</span><span class="sxs-lookup"><span data-stu-id="18c40-112">How should users of barcode scanners use reason codes?</span></span> <span data-ttu-id="18c40-113">¿Los códigos de motivo deben ser preseleccionados, obligatorioo o no editables?</span><span class="sxs-lookup"><span data-stu-id="18c40-113">Should the reason codes be preselected, mandatory, or not editable?</span></span>
- <span data-ttu-id="18c40-114">¿Los trabajadores de almacén requieren un comportamiento de código de motivo diferente en los escáneres móviles?</span><span class="sxs-lookup"><span data-stu-id="18c40-114">Do warehouse workers require different reason code behavior on mobile scanners?</span></span> <span data-ttu-id="18c40-115">Si la respuesta es afirmativa, puede crear más elementos de menú y asignarlos a diferentes personas.</span><span class="sxs-lookup"><span data-stu-id="18c40-115">If the answer is yes, you can create more menu items and assign them to different people.</span></span>

## <a name="where-reason-codes-apply"></a><span data-ttu-id="18c40-116">Donde se aplican los códigos de motivo</span><span class="sxs-lookup"><span data-stu-id="18c40-116">Where reason codes apply</span></span>

<span data-ttu-id="18c40-117">Puede crear varias directivas de código de motivo, y cada una puede tener dos directivas de código de motivo de recuento.</span><span class="sxs-lookup"><span data-stu-id="18c40-117">You can create multiple reason code policies, and each reason code policy can have two counting reason code policies.</span></span> <span data-ttu-id="18c40-118">Las directivas de código de motivo de recuento se pueden utilizar en el nivel de almacén o en el nivel de artículo.</span><span class="sxs-lookup"><span data-stu-id="18c40-118">The counting reason code policies can be used at the warehouse level or the item level.</span></span>

## <a name="set-up-reason-code-policies"></a><span data-ttu-id="18c40-119">Configurar directivas de código de motivo</span><span class="sxs-lookup"><span data-stu-id="18c40-119">Set up reason code policies</span></span>

1. <span data-ttu-id="18c40-120">Seleccione **Gestión del inventario** \> **Configuración** \> **Inventario** \> **Directivas de código de motivo de recuento** y cree una nueva directiva de código de motivo.</span><span class="sxs-lookup"><span data-stu-id="18c40-120">Select **Inventory management** \> **Setup** \> **Inventory** \> **Counting reason code policies**, and create a new reason code policy.</span></span>
2. <span data-ttu-id="18c40-121">En el campo **Tipo de código de motivo de recuento**, seleccione **Obligatorio** u **Opcional** para especificar si la selección de un código de motivo debe ser una acción opcional u obligatoria en uno de los siguientes diarios de recuento:</span><span class="sxs-lookup"><span data-stu-id="18c40-121">In the **Counting reason code type** field, select either **Mandatory** or **Optional** to specify whether selection of a reason code should be an optional or mandatory action in one of the following counting journals:</span></span>

    - <span data-ttu-id="18c40-122">Recuento cíclico (dispositivo móvil)</span><span class="sxs-lookup"><span data-stu-id="18c40-122">Cycle Count (mobile device)</span></span>
    - <span data-ttu-id="18c40-123">Recuento puntual (dispositivo móvil)</span><span class="sxs-lookup"><span data-stu-id="18c40-123">Spot Count (mobile device)</span></span>
    - <span data-ttu-id="18c40-124">Recuento de umbral (dispositivo móvil)</span><span class="sxs-lookup"><span data-stu-id="18c40-124">Threshold Count (mobile device)</span></span>
    - <span data-ttu-id="18c40-125">Entrada de ajuste (dispositivo móvil)</span><span class="sxs-lookup"><span data-stu-id="18c40-125">Adjustment In (mobile device)</span></span>
    - <span data-ttu-id="18c40-126">Salida de ajuste (dispositivo móvil)</span><span class="sxs-lookup"><span data-stu-id="18c40-126">Adjustment Out (mobile device)</span></span>
    - <span data-ttu-id="18c40-127">Diario de recuento (cliente rico)</span><span class="sxs-lookup"><span data-stu-id="18c40-127">Counting Journal (rich client)</span></span>

<span data-ttu-id="18c40-128">También puede configurar códigos de motivo para almacenes individuales y para productos.</span><span class="sxs-lookup"><span data-stu-id="18c40-128">You can also set up reason codes for individual warehouses and for products.</span></span> <span data-ttu-id="18c40-129">La configuración del código de motivo para productos puede omitir la configuración para almacenes.</span><span class="sxs-lookup"><span data-stu-id="18c40-129">The reason code setup for products can disregard the setup for warehouses.</span></span>

## <a name="mandatory-reason-codes"></a><span data-ttu-id="18c40-130">Códigos de motivo obligatorios</span><span class="sxs-lookup"><span data-stu-id="18c40-130">Mandatory reason codes</span></span>

<span data-ttu-id="18c40-131">Si el parámetro **Obligatorio** se establece en la configuración de códigos de motivo para almacenes o artículos, el diario de recuento no se podrá completar y cerrar hasta que se proporcione un código de motivo.</span><span class="sxs-lookup"><span data-stu-id="18c40-131">If the **Mandatory** parameter is set in the configuration of reason codes for warehouses or items, the counting journal can't be completed and closed until a reason code is provided.</span></span>

### <a name="set-up-reason-codes-for-warehouses"></a><span data-ttu-id="18c40-132">Configurar códigos de motivo para almacenes</span><span class="sxs-lookup"><span data-stu-id="18c40-132">Set up reason codes for warehouses</span></span>

1. <span data-ttu-id="18c40-133">Seleccione **Gestión del inventario** \> **Configurar** \> **Desglose del inventario** \> **Almacenes**.</span><span class="sxs-lookup"><span data-stu-id="18c40-133">Select **Inventory Management** \> **Setup** \> **Inventory breakdown** \> **Warehouses**.</span></span>
2. <span data-ttu-id="18c40-134">En la pestaña **Almacén**, en el campo **Directiva de código de motivo de recuento**, seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="18c40-134">On the **Warehouse** tab, in the **Counting reason code policy** field, select one of the following options:</span></span>

    - <span data-ttu-id="18c40-135">**En blanco**: el parámetro configurado para el artículo se utiliza para determinar si los diarios de recuento son obligatorios para el producto.</span><span class="sxs-lookup"><span data-stu-id="18c40-135">**Blank** – The parameter that is set up for the item is used to determine whether counting journals are mandatory for the product.</span></span>
    - <span data-ttu-id="18c40-136">**Obligatorio**: siempre es neceario un código de motivo en los diarios de recuento para el almacén.</span><span class="sxs-lookup"><span data-stu-id="18c40-136">**Mandatory** – A reason code is always required on counting journals for the warehouse.</span></span>
    - <span data-ttu-id="18c40-137">**Opcional**: no es necesario un código de motivo en los diarios de recuento para el almacén.</span><span class="sxs-lookup"><span data-stu-id="18c40-137">**Optional** – A reason code isn't required on counting journals for the warehouse.</span></span>

### <a name="set-up-reason-codes-for-products"></a><span data-ttu-id="18c40-138">Configurar códigos de motivo para productos</span><span class="sxs-lookup"><span data-stu-id="18c40-138">Set up reason codes for products</span></span>

1. <span data-ttu-id="18c40-139">Seleccione **Gestión de información de productos** \> **Productos** \> **Productos emitidos**.</span><span class="sxs-lookup"><span data-stu-id="18c40-139">Select **Product information management** \> **Products** \> **Released products**.</span></span>
2. <span data-ttu-id="18c40-140">En la pestaña **Producto**, seleccione **Directiva de código de motivo de recuento** y, a continuación, seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="18c40-140">On the **Product** tab, select **Counting reason code policy**, and then select one of the following options:</span></span>

    - <span data-ttu-id="18c40-141">**En blanco**: el parámetro configurado para el almacén se utiliza para determinar si los diarios de recuento son obligatorios para el producto.</span><span class="sxs-lookup"><span data-stu-id="18c40-141">**Blank** – The parameter that is set up for the warehouse is used to determine whether counting journals are mandatory for the product.</span></span>
    - <span data-ttu-id="18c40-142">**Obligatorio**: siempre es neceario un código de motivo en los diarios de recuento para el producto.</span><span class="sxs-lookup"><span data-stu-id="18c40-142">**Mandatory** – A reason code is always required on counting journals for the product.</span></span> <span data-ttu-id="18c40-143">Esta configuración anula cualquier configuración del código de motivo en el nivel de almacén.</span><span class="sxs-lookup"><span data-stu-id="18c40-143">This setting overrides any reason code setting at the warehouse level.</span></span>
    - <span data-ttu-id="18c40-144">**Opcional**: no es necesario un código de motivo en los diarios de recuento para el producto.</span><span class="sxs-lookup"><span data-stu-id="18c40-144">**Optional** – A reason code isn't required on counting journals for the product.</span></span> <span data-ttu-id="18c40-145">Esta configuración anula cualquier configuración del código de motivo en el nivel de almacén.</span><span class="sxs-lookup"><span data-stu-id="18c40-145">This setting overrides any reason code setting at the warehouse level.</span></span>

### <a name="use-reason-codes-in-counting-journals"></a><span data-ttu-id="18c40-146">Utilice códigos de motivo en diarios de recuento</span><span class="sxs-lookup"><span data-stu-id="18c40-146">Use reason codes in counting journals</span></span>

<span data-ttu-id="18c40-147">En un diario de recuento, puede agregar códigos de motivo para recuentos de los siguientes tipos:</span><span class="sxs-lookup"><span data-stu-id="18c40-147">In a counting journal, you can add reason codes for counts of the following types:</span></span>

- <span data-ttu-id="18c40-148">Recuento cíclico</span><span class="sxs-lookup"><span data-stu-id="18c40-148">Cycle Count</span></span>
- <span data-ttu-id="18c40-149">Recuento puntual</span><span class="sxs-lookup"><span data-stu-id="18c40-149">Spot Count</span></span>
- <span data-ttu-id="18c40-150">Recuento de umbral</span><span class="sxs-lookup"><span data-stu-id="18c40-150">Threshold Count</span></span>
- <span data-ttu-id="18c40-151">Entrada de ajuste</span><span class="sxs-lookup"><span data-stu-id="18c40-151">Adjustment In</span></span>
- <span data-ttu-id="18c40-152">Salida de ajuste</span><span class="sxs-lookup"><span data-stu-id="18c40-152">Adjustment Out</span></span>

<span data-ttu-id="18c40-153">Los códigos de motivo se agregan a las líneas del diario en los diarios de recuento del tipo **Diario de recuento**.</span><span class="sxs-lookup"><span data-stu-id="18c40-153">Reason codes are added to the journal lines in counting journals of the **Counting journal** type.</span></span>

1. <span data-ttu-id="18c40-154">Seleccione **Gestión del inventario** \> **Movimiento de diario** \> **Recuento de artículos** \> **Recuento**.</span><span class="sxs-lookup"><span data-stu-id="18c40-154">Select **Inventory management** \> **Journal entries** \> **Item counting** \> **Counting**.</span></span>
2. <span data-ttu-id="18c40-155">En los detalles de línea del diario de recuento, en el campo **Código de motivo de recuento**, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="18c40-155">In the line details of the counting journal, in the **Counting reason code** field, select an option.</span></span>

### <a name="view-the-counting-history-as-its-recorded-by-reason-codes"></a><span data-ttu-id="18c40-156">Ver el historial de recuento tal como está registrado por códigos de motivo</span><span class="sxs-lookup"><span data-stu-id="18c40-156">View the counting history as it's recorded by reason codes</span></span>

- <span data-ttu-id="18c40-157">Seleccione **Gestión del inventario** \> **Consultas e informes** \> **Historial de recuento** y, a continuación, en el campo **Código de motivo de recuento**, vea el historial de recuento que se ha registrado a través del código de motivo.</span><span class="sxs-lookup"><span data-stu-id="18c40-157">Select **Inventory management** \> **Inquiries and reports** \> **Counting history**, and then, in the **Counting reason code** field, view the counting history that has been recorded through a reason code.</span></span>

### <a name="use-a-reason-code-for-a-quantity-adjustment"></a><span data-ttu-id="18c40-158">Utilice un código de motivo para un ajuste de cantidad</span><span class="sxs-lookup"><span data-stu-id="18c40-158">Use a reason code for a quantity adjustment</span></span>

1. <span data-ttu-id="18c40-159">En la página **Inventario disponible**, seleccione **Ajustar cantidad**.</span><span class="sxs-lookup"><span data-stu-id="18c40-159">On the **On-hand inventory** page, select **Adjust quantity**.</span></span> <span data-ttu-id="18c40-160">Puede abrir la página **Inventario disponible** de varias maneras.</span><span class="sxs-lookup"><span data-stu-id="18c40-160">You can open the **On-hand inventory** page in several ways.</span></span> <span data-ttu-id="18c40-161">Por ejemplo, seleccione **Gestión del inventario** \> **Consultas e informes** \> **Inventario disponible**.</span><span class="sxs-lookup"><span data-stu-id="18c40-161">For example, select **Inventory management** \> **Inquiries and reports** \> **On-hand inventory**.</span></span>
2. <span data-ttu-id="18c40-162">Seleccione **Ajustar cantidad** y, a continuación, en el campo **Código de motivo de recuento**, seleccione un código de motivo.</span><span class="sxs-lookup"><span data-stu-id="18c40-162">Select **Adjust quantity**, and then, in the **Counting reason code** field, select a reason code.</span></span>

### <a name="configure-reason-codes-for-mobile-device-menu-items"></a><span data-ttu-id="18c40-163">Configurar códigos de motivo para elementos de menú del dispositivo móvil</span><span class="sxs-lookup"><span data-stu-id="18c40-163">Configure reason codes for mobile device menu items</span></span>

<span data-ttu-id="18c40-164">Puede configurar códigos de motivo para cualquier tipo de recuento en un elemento de menú del dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="18c40-164">You can configure reason codes for any type of count on a mobile device menu item.</span></span> <span data-ttu-id="18c40-165">La configuración del elemento de menú del dispositivo móvil incluye la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="18c40-165">The configuration of the mobile device menu item includes the following information:</span></span>

- <span data-ttu-id="18c40-166">Si el código de motivo se muestra al trabajador del dispositivo móvil durante el recuento.</span><span class="sxs-lookup"><span data-stu-id="18c40-166">Whether the reason code is shown to the mobile device worker during counting.</span></span>
- <span data-ttu-id="18c40-167">El código de motivo predeterminado que se muestra en un elemento de menú del dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="18c40-167">The default reason code that is shown on a mobile device menu item.</span></span>
- <span data-ttu-id="18c40-168">Si el usuario puede editar el código de motivo.</span><span class="sxs-lookup"><span data-stu-id="18c40-168">Whether the user can edit the reason code.</span></span>

### <a name="set-up-reason-codes-on-a-mobile-device"></a><span data-ttu-id="18c40-169">Configurar códigos de motivo en un dispositivo móvil</span><span class="sxs-lookup"><span data-stu-id="18c40-169">Set up reason codes on a mobile device</span></span>

1. <span data-ttu-id="18c40-170">Seleccione **Gestión de almacenes** \> **Configurar** \> **Dispositivo móvil** \> **Elementos de menú del dispositivo móvil**.</span><span class="sxs-lookup"><span data-stu-id="18c40-170">Select **Warehouse management** \> **Setup** \> **Mobile device** \> **Mobile device menu items**.</span></span>
2. <span data-ttu-id="18c40-171">En la pestaña **Recuento cíclico**, seleccione **Recuento cíclico**.</span><span class="sxs-lookup"><span data-stu-id="18c40-171">On the **Cycle count** tab, select **Cycle counting**.</span></span>
3. <span data-ttu-id="18c40-172">En el campo **Código de motivo de recuento predeterminado**, establezca el código de motivo predeterminado que debe registrarse cuando el recuento se realiza mediante el elemento de menú del dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="18c40-172">In the **Default counting reason code** field, set the default reason code that should be recorded when counting is done by using the mobile device menu item.</span></span>
4. <span data-ttu-id="18c40-173">En el campo **Visualizar código de motivo de recuento**, seleccione **Línea** para mostrar el código de motivo después de que se registre cada desviación.</span><span class="sxs-lookup"><span data-stu-id="18c40-173">In the **Display counting reason code** field, select **Line** to show the reason code after each variance is recorded.</span></span> <span data-ttu-id="18c40-174">De manera alternativa, seleccione **Ocultar** si no debe mostrarse el código de motivo.</span><span class="sxs-lookup"><span data-stu-id="18c40-174">Alternatively, select **Hide** if the reason code shouldn't be shown.</span></span>
5. <span data-ttu-id="18c40-175">Establezca la opción **Editar código de motivo de recuento** en **Sí** o **No**.</span><span class="sxs-lookup"><span data-stu-id="18c40-175">Set the **Edit counting reason code** option to either **Yes** or **No**.</span></span> <span data-ttu-id="18c40-176">Si establece esta opción en **Sí**, el trabajador puede editar el código de motivo cuando se muestre en el dispositivo móvil durante el recuento.</span><span class="sxs-lookup"><span data-stu-id="18c40-176">If you set this option to **Yes**, the worker can edit the reason code when it's shown on the mobile device during counting.</span></span>

> [!NOTE]
> <span data-ttu-id="18c40-177">El botón **Recuento cíclico** se puede habilitar en cualquier elemento de menú del dispositivo móvil en el que se puedan hacer recuentos.</span><span class="sxs-lookup"><span data-stu-id="18c40-177">The **Cycle counting** button can be enabled on any mobile device menu item where counting can be done.</span></span> <span data-ttu-id="18c40-178">El ejemplo incluye los elementos de menú para recuentos puntuales, trabajo dirigido por el usuario y trabajo dirigido por el sistema.</span><span class="sxs-lookup"><span data-stu-id="18c40-178">Example include the menu items for spot counts, user-directed work, and system-directed work.</span></span>

## <a name="cycle-count-approvals"></a><span data-ttu-id="18c40-179">Aprobaciones de recuento cíclico</span><span class="sxs-lookup"><span data-stu-id="18c40-179">Cycle count approvals</span></span>

<span data-ttu-id="18c40-180">Antes de que se apruebe un recuento, el usuario puede cambiar el código de motivo asociado al recuento.</span><span class="sxs-lookup"><span data-stu-id="18c40-180">Before a count is approved, the user can change the reason code that is associated with the count.</span></span> <span data-ttu-id="18c40-181">Cuando se aprueba el recuento, el código de motivo se introduce en las líneas del diario de recuento.</span><span class="sxs-lookup"><span data-stu-id="18c40-181">When the count is approved, the reason code is entered on the counting journal lines.</span></span>

### <a name="modify-cycle-count-approvals"></a><span data-ttu-id="18c40-182">Modificar aprobaciones de recuento cíclico</span><span class="sxs-lookup"><span data-stu-id="18c40-182">Modify cycle count approvals</span></span>

1. <span data-ttu-id="18c40-183">Seleccione **Gestión de almacenes** \> **Recuento cíclico** \> **Revisión pendiente del trabajo de recuento cíclico**.</span><span class="sxs-lookup"><span data-stu-id="18c40-183">Select **Warehouse management** \> **Cycle counting** \> **Cycle count work pending review**.</span></span>
2. <span data-ttu-id="18c40-184">Seleccione **Recuento cíclico** y, a continuación, en el campo **Código de motivo**, seleccione un nuevo código de motivo.</span><span class="sxs-lookup"><span data-stu-id="18c40-184">Select **Cycle counting**, and then, in the **Reason code** field, select a new reason code.</span></span>

### <a name="modify-the-mobile-device-menu-item-for-adjustment-in-and-adjustment-out"></a><span data-ttu-id="18c40-185">Modificar el elemento de menú del dispositivo móvil para la entrada de ajuste y la salida de ajuste</span><span class="sxs-lookup"><span data-stu-id="18c40-185">Modify the mobile device menu item for Adjustment in and Adjustment out</span></span>

1. <span data-ttu-id="18c40-186">Seleccione **Gestión de almacenes** \> **Configurar** \> **Dispositivo móvil** \> **Elementos de menú del dispositivo móvil** y, a continuación, seleccione **Entrada de ajuste y salida ajuste**.</span><span class="sxs-lookup"><span data-stu-id="18c40-186">Select **Warehouse management** \> **Setup** \> **Mobile device** \> **Mobile device menu items**, and then select **Adjustment in and out**.</span></span>
2. <span data-ttu-id="18c40-187">Establezca la opción **Usar trabajo existente** en **No**.</span><span class="sxs-lookup"><span data-stu-id="18c40-187">Set the **Use existing work** option to **No**.</span></span>
3. <span data-ttu-id="18c40-188">En el campo **Proceso de creación de trabajo**, seleccione **Entrada de ajuste**.</span><span class="sxs-lookup"><span data-stu-id="18c40-188">In the **Work creation process** field, select **Adjustment in**.</span></span>

<span data-ttu-id="18c40-189">Los siguientes campos se agregarán al elemento de menú del dispositivo móvil cuando se selecciona **Entrada de ajuste** o **Salida de ajuste** durante el proceso de creación de trabajo:</span><span class="sxs-lookup"><span data-stu-id="18c40-189">The following fields will be added to the mobile device menu item when **Adjustment in** or **Adjustment out** is selected during the work creation process:</span></span>

- <span data-ttu-id="18c40-190">Código de motivo de recuento predeterminado</span><span class="sxs-lookup"><span data-stu-id="18c40-190">Default counting reason code</span></span>
- <span data-ttu-id="18c40-191">Visualizar código de motivo de recuento</span><span class="sxs-lookup"><span data-stu-id="18c40-191">Display counting reason code</span></span>
- <span data-ttu-id="18c40-192">Editar código de motivo de recuento</span><span class="sxs-lookup"><span data-stu-id="18c40-192">Edit counting reason code</span></span>
