---
title: "Registrar el material de consumo mediante un dispositivo móvil"
description: "Este tema describe un flujo de trabajo que habilita el registro de consumo de materias primas en la producción mediante un dispositivo de mano."
author: johanhoffmann
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: AX 7.0.0, Operations, UnifiedOperations
ms.custom: 1706093
ms.assetid: 75ee68e0-4b9f-4f4d-b286-f498e0eb73fa
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 97d374230cc6e833b9f585de000e1252f2a78b9d
ms.openlocfilehash: 83703d962d6099ba8ac107548a569c8d1f34882f
ms.contentlocale: es-es
ms.lasthandoff: 08/30/2017

---

# <a name="register-material-consumption-using-a-mobile-device"></a><span data-ttu-id="0fb6e-103">Registrar el material de consumo mediante un dispositivo móvil</span><span class="sxs-lookup"><span data-stu-id="0fb6e-103">Register material consumption using a mobile device</span></span>
<span data-ttu-id="0fb6e-104">Este tema describe un flujo de trabajo que habilita el registro de consumo de materias primas en la producción mediante un dispositivo de mano.</span><span class="sxs-lookup"><span data-stu-id="0fb6e-104">This topic describes a workflow that enables registration of raw material consumption in production by using a handheld device.</span></span>

<a name="introduction"></a><span data-ttu-id="0fb6e-105">Introducción</span><span class="sxs-lookup"><span data-stu-id="0fb6e-105">Introduction</span></span>
------------

<span data-ttu-id="0fb6e-106">Este flujo de trabajo es relevante si hay un requisito estricto para la trazabilidad del material.</span><span class="sxs-lookup"><span data-stu-id="0fb6e-106">This workflow is relevant if there is a strict requirement for material traceability.</span></span> <span data-ttu-id="0fb6e-107">En tales casos, para mantener la trazabilidad de los materiales, la hora y la cantidad exactas se deben notificar para el consumo.</span><span class="sxs-lookup"><span data-stu-id="0fb6e-107">In those cases, to maintain traceability of the materials, the exact time and quantity must be reported for the consumption.</span></span> <span data-ttu-id="0fb6e-108">Este proceso se puede ver en comparación con operaciones de autoconsumo o flujo invertido, donde hay una demora entre la hora de registro y la hora en la que tiene lugar el consumo real.</span><span class="sxs-lookup"><span data-stu-id="0fb6e-108">This process can be seen as opposed to pre- or back-flushing operations, where there is an offset between the time of registration and the time when the actual consumption takes place.</span></span> <span data-ttu-id="0fb6e-109">Esto explica por qué una estrategia de consumo automático no se puede usar para algunos materiales con requisitos de la trazabilidad.</span><span class="sxs-lookup"><span data-stu-id="0fb6e-109">This explains why a strategy of automatic consumption cannot be used for some materials with traceability requirements.</span></span> <span data-ttu-id="0fb6e-110">Miremos una situación de ejemplo sencilla que explica cómo configurar un flujo de trabajo para habilitar el registro de consumo de materias primas en la producción mediante un dispositivo de mano.</span><span class="sxs-lookup"><span data-stu-id="0fb6e-110">Let’s look at a simple scenario that explains how to set up a workflow to enable registration of raw material consumption in production by using a handheld device.</span></span> [![](./media/scenario3.png)](./media/scenario3.png)

### <a name="scenario-details"></a><span data-ttu-id="0fb6e-111">Detalles del escenario</span><span class="sxs-lookup"><span data-stu-id="0fb6e-111">Scenario details</span></span>

<span data-ttu-id="0fb6e-112">Un proceso continuo de producción (5) consume la materia prima RM-100 controlada por lotes.</span><span class="sxs-lookup"><span data-stu-id="0fb6e-112">A continuous production process (5) consumes the batch-controlled raw material RM-100.</span></span> <span data-ttu-id="0fb6e-113">El material está disponible en la ubicación Bulk-001 (1), en la matrícula PL -1 con dos lotes, B1 y B2, ambos con una cantidad de 100 lbs.</span><span class="sxs-lookup"><span data-stu-id="0fb6e-113">The material is on-hand on location Bulk-001 (1) on license plate PL-1 with two batches, B1 and B2, both with a quantity of 100 lbs.</span></span> <span data-ttu-id="0fb6e-114">El trabajo de almacén (2) se libera y se procesa para RM-100, y se recoge el material de Bulk-001 a la ubicación de entrada de producción PIL-01 (3), que se define como sin control de matrículas.</span><span class="sxs-lookup"><span data-stu-id="0fb6e-114">Warehouse work (2) is released and processed for RM-100, and the material is picked from Bulk-001 to the production input location PIL-01 (3), which is defined as non-license plate controlled.</span></span> <span data-ttu-id="0fb6e-115">El operador de maquinaria pesa el material de la ubicación de entrada de producción (3) y registra el peso y el número de lote como consumido (4).</span><span class="sxs-lookup"><span data-stu-id="0fb6e-115">The machine operator weighs out material from the production input location (3) and registers the weight and batch number as consumed (4).</span></span> <span data-ttu-id="0fb6e-116">Desde la ubicación de entrada de producción, se agrega una parte del material manualmente al proceso de producción a intervalos de tiempo definidos.</span><span class="sxs-lookup"><span data-stu-id="0fb6e-116">From the production input location, a portion of the material is manually added to the production process in defined time intervals.</span></span> <span data-ttu-id="0fb6e-117">Cuando el operador de maquinaria agrega el material, se pesa en una báscula y se registra el número de lote.</span><span class="sxs-lookup"><span data-stu-id="0fb6e-117">When the machine operator adds material, it is weighed on a scale and the batch number is registered.</span></span>

## <a name="set-up-the-workflow-to-register-consumption-using-a-handheld-device"></a><span data-ttu-id="0fb6e-118">Configuración del flujo de trabajo para registrar el consumo mediante un dispositivo de mano</span><span class="sxs-lookup"><span data-stu-id="0fb6e-118">Set up the workflow to register consumption using a handheld device</span></span>
<span data-ttu-id="0fb6e-119">Cree un producto de bien terminado, FG-100, con una lista de materiales con la materia prima controlada por lotes RM-100.</span><span class="sxs-lookup"><span data-stu-id="0fb6e-119">Create a finished-good product, FG-100, with a bill of material that has the batch-controlled raw material RM-100.</span></span> <span data-ttu-id="0fb6e-120">Agregue dos lotes, B1 y B2, de RM-100 en una cantidad de 100 a la ubicación: Bulk-001 en la matrícula: PL-1.</span><span class="sxs-lookup"><span data-stu-id="0fb6e-120">Add two batches, B1 and B2, of RM-100 in a quantity of 100 to location: Bulk-001 on license plate: PL-1.</span></span> <span data-ttu-id="0fb6e-121">El principio de vaciado de la línea de lista de materiales para RM-100 se establece en **Manual**.</span><span class="sxs-lookup"><span data-stu-id="0fb6e-121">The flushing principle on the bill of material line for RM-100 is set to **Manual**.</span></span> <span data-ttu-id="0fb6e-122">Configure la ubicación de entrada de producción como PIL-01.</span><span class="sxs-lookup"><span data-stu-id="0fb6e-122">Set  the production input location to PIL-01.</span></span> <span data-ttu-id="0fb6e-123">Puede hacerlo seleccionando esta ubicación como ubicación de entrada de producción predeterminada en el almacén 51.</span><span class="sxs-lookup"><span data-stu-id="0fb6e-123">You can do that by selecting this location as the default production input location on warehouse 51.</span></span>

1.  <span data-ttu-id="0fb6e-124">Cree un nuevo elemento de menú del dispositivo móvil:</span><span class="sxs-lookup"><span data-stu-id="0fb6e-124">Create a new mobile device menu item:</span></span> 

-    <span data-ttu-id="0fb6e-125">**Nombre de elemento de menú**: Registrar el consumo de material.</span><span class="sxs-lookup"><span data-stu-id="0fb6e-125">**Menu item name** - Register material consumption.</span></span> 
-    <span data-ttu-id="0fb6e-126">**Título**: Registrar el consumo de material.</span><span class="sxs-lookup"><span data-stu-id="0fb6e-126">**Title** - Register material consumption.</span></span> 
-    <span data-ttu-id="0fb6e-127">**Modo**: Indirecto.</span><span class="sxs-lookup"><span data-stu-id="0fb6e-127">**Mode** - Indirect.</span></span> 
-    <span data-ttu-id="0fb6e-128">**Código de actividad**: Registrar el consumo de material.</span><span class="sxs-lookup"><span data-stu-id="0fb6e-128">**Activity code** - Register material consumption.</span></span>

2.  <span data-ttu-id="0fb6e-129">Añada el elemento de menú al menú de dispositivo **Móvil de producción**.</span><span class="sxs-lookup"><span data-stu-id="0fb6e-129">Add the menu item to the **Production Mobile** device menu.</span></span>
3.  <span data-ttu-id="0fb6e-130">Cree un pedido de producción para el producto acabado:</span><span class="sxs-lookup"><span data-stu-id="0fb6e-130">Create a production order for the finished product:</span></span> 

-    <span data-ttu-id="0fb6e-131">**Número de artículo**: FG-100</span><span class="sxs-lookup"><span data-stu-id="0fb6e-131">**Item number** - FG-100</span></span> 
-    <span data-ttu-id="0fb6e-132">**Sitio**: 5</span><span class="sxs-lookup"><span data-stu-id="0fb6e-132">**Site** - 5</span></span> 
-    <span data-ttu-id="0fb6e-133">**Almacén**: 51</span><span class="sxs-lookup"><span data-stu-id="0fb6e-133">**Warehouse** - 51</span></span> 
-    <span data-ttu-id="0fb6e-134">**Cantidad**: 150</span><span class="sxs-lookup"><span data-stu-id="0fb6e-134">**Quantity** - 150</span></span>

<span data-ttu-id="0fb6e-135">El pedido de producción es **Estimado** y **Liberado** y se crea el trabajo de almacén.</span><span class="sxs-lookup"><span data-stu-id="0fb6e-135">The production order is **Estimated** and **Released** and warehouse work is created.</span></span>

4.  <span data-ttu-id="0fb6e-136">Complete el trabajo mediante el flujo de trabajo para la selección de materias primas para el dispositivo de mano.</span><span class="sxs-lookup"><span data-stu-id="0fb6e-136">Complete the work using the workflow for raw material picking for the handheld device.</span></span>

<span data-ttu-id="0fb6e-137">Esto traerá el material de la ubicación de almacenaje a la ubicación de entrada de producción PIL-01.</span><span class="sxs-lookup"><span data-stu-id="0fb6e-137">This will bring the material from the bulk location to the production input location PIL-01.</span></span> <span data-ttu-id="0fb6e-138">Una vez que haya terminado el trabajo, el material tiene el estado **Seleccionado en la ubicación de entrada de producción**.</span><span class="sxs-lookup"><span data-stu-id="0fb6e-138">After the work is completed, the material has the status **Picked on the production input location**.</span></span> <span data-ttu-id="0fb6e-139">El estado después de que se haya procesado el trabajo puede ser **Seleccionado** o **Reservado físicamente**.</span><span class="sxs-lookup"><span data-stu-id="0fb6e-139">The status after work has been processed can be either **Picked** or **Reserved physical**.</span></span> <span data-ttu-id="0fb6e-140">Esto se configura con el parámetro **Estado de emisión después de puesto el formulario Almacén**.</span><span class="sxs-lookup"><span data-stu-id="0fb6e-140">This is configured with the parameter **Issue status after put on the warehouse form**.</span></span>

5.  <span data-ttu-id="0fb6e-141">Iniciar el pedido de producción desde el cliente o desde el dispositivo de mano mediante el elemento de menú **Iniciar producción** .</span><span class="sxs-lookup"><span data-stu-id="0fb6e-141">Start the production order either from the client or from the handheld device by using the **Production start** menu item.</span></span>

<span data-ttu-id="0fb6e-142">Una vez iniciado el pedido de producción, puede registrar el consumo de materiales mediante el flujo de trabajo del dispositivo de mano.</span><span class="sxs-lookup"><span data-stu-id="0fb6e-142">After the production order has been started, you can register material consumption with the workflow for the handheld device.</span></span> <span data-ttu-id="0fb6e-143">Comencemos por registrar el consumo de 25 libras del lote B1.</span><span class="sxs-lookup"><span data-stu-id="0fb6e-143">Let's start by registering consumption of 25 lbs of batch B1.</span></span>

6.  <span data-ttu-id="0fb6e-144">Seleccione el elemento de menú **Registrar el** **consumo de material** en el menú del dispositivo de mano, especifique los detalles siguientes:</span><span class="sxs-lookup"><span data-stu-id="0fb6e-144">Select the **Register material** **consumption** menu item in the menu for the hand held device, enter the following details:</span></span> 

-    <span data-ttu-id="0fb6e-145">El número de pedido de producción.</span><span class="sxs-lookup"><span data-stu-id="0fb6e-145">The production order number.</span></span> 
-    <span data-ttu-id="0fb6e-146">La ubicación en la que el material se va a consumir, en este caso PIL-01.</span><span class="sxs-lookup"><span data-stu-id="0fb6e-146">The location on which the material is going to be consumed, in this case PIL-01.</span></span> 
-    <span data-ttu-id="0fb6e-147">Número de artículo RM-100.</span><span class="sxs-lookup"><span data-stu-id="0fb6e-147">Item number RM-100.</span></span> 
-    <span data-ttu-id="0fb6e-148">Número de lote B1.</span><span class="sxs-lookup"><span data-stu-id="0fb6e-148">Batch number B1.</span></span> 
-    <span data-ttu-id="0fb6e-149">Cantidad de 25.</span><span class="sxs-lookup"><span data-stu-id="0fb6e-149">A quantity of 25.</span></span>

7.  <span data-ttu-id="0fb6e-150">Seleccionar **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0fb6e-150">Select **OK**.</span></span>

<span data-ttu-id="0fb6e-151">Tenga en cuenta que el mensaje “Se creó la línea de diario” aparece en la pantalla.</span><span class="sxs-lookup"><span data-stu-id="0fb6e-151">Note that the message "Journal line is created" appears on the display.</span></span> <span data-ttu-id="0fb6e-152">En el pedido de producción existe un diario abierto del tipo **Lista de selección de producción** para el número de artículo RM-100 y el número de lote B1.</span><span class="sxs-lookup"><span data-stu-id="0fb6e-152">On the production order there is an open journal of the type **Production picking list** for item number RM-100 and batch number B1.</span></span> 

<span data-ttu-id="0fb6e-153">Ahora puede optar por continuar su registro, por ejemplo en el número de lote B2, y cada vez que se seleccione **Aceptar,** una nueva línea de diario se agrega al diario abierto.</span><span class="sxs-lookup"><span data-stu-id="0fb6e-153">You can now choose to continue your registration, for example on batch number B2, and each time you select **OK,** a new journal line is added to the open journal.</span></span> 

<span data-ttu-id="0fb6e-154">Una vez que haya terminado su registro, seleccione **Hecho** para registrar el diario y finalizar el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="0fb6e-154">After you have finished your registration, select **Done** to post the journal and end the workflow.</span></span>

### <a name="additional-comments"></a><span data-ttu-id="0fb6e-155">Comentarios adicionales</span><span class="sxs-lookup"><span data-stu-id="0fb6e-155">Additional comments</span></span> 

-   <span data-ttu-id="0fb6e-156">Si un usuario cancela el flujo de trabajo después de que se cree una línea de diario, el diario se encuentra en estado sin registrar, pero si el usuario en un momento posterior utiliza el flujo de trabajo para el mismo pedido de producción, las líneas se agregarán al diario abierto en lugar de a un nuevo diario.</span><span class="sxs-lookup"><span data-stu-id="0fb6e-156">If a user cancels the workflow after a journal line is created, the journal is in an unposted state but if the user at a later point uses the workflow for the same production order, then the lines will be added to the open journal rather than to a new journal.</span></span>
-   <span data-ttu-id="0fb6e-157">El nuevo flujo de trabajo también admite el registro de números de serie.</span><span class="sxs-lookup"><span data-stu-id="0fb6e-157">The new workflow also supports the registration of serial numbers.</span></span>
-   <span data-ttu-id="0fb6e-158">Es posible registrar sólo un número de artículo definido en la lista de materiales o en la fórmula del pedido de producción seleccionado o del pedido de lote.</span><span class="sxs-lookup"><span data-stu-id="0fb6e-158">It is only possible to register an item number that is defined in the bill of material or in the formula for the selected production order or batch order.</span></span>
-   <span data-ttu-id="0fb6e-159">El material puede sobreconsumirse.</span><span class="sxs-lookup"><span data-stu-id="0fb6e-159">Material can be overconsumed.</span></span> <span data-ttu-id="0fb6e-160">Por ejemplo, si se estima que el material se consumirá con la cantidad de 100 libras, después puede sobreconsumirse con una cantidad de, por ejemplo, 105 lbs.</span><span class="sxs-lookup"><span data-stu-id="0fb6e-160">For example, if the material is estimated to be consumed with the quantity of 100 lbs, then it can be overconsumed with a quantity of, for example, 105 lbs.</span></span>



