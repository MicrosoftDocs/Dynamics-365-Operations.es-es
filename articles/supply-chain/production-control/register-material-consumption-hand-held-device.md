---
title: Registrar el material de consumo mediante un dispositivo móvil
description: Este tema describe un flujo de trabajo que habilita el registro de consumo de materias primas en la producción mediante un dispositivo de mano.
author: johanhoffmann
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFMenuItem
audience: Application User
ms.reviewer: kamaybac
ms.custom: 1706093
ms.assetid: 75ee68e0-4b9f-4f4d-b286-f498e0eb73fa
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4a4afc4b0c8d9a7109201326169311e85798d532
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5209403"
---
# <a name="register-material-consumption-using-a-mobile-device"></a><span data-ttu-id="223bb-103">Registrar el material de consumo mediante un dispositivo móvil</span><span class="sxs-lookup"><span data-stu-id="223bb-103">Register material consumption using a mobile device</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="223bb-104">Este tema describe un flujo de trabajo que habilita el registro de consumo de materias primas en la producción mediante un dispositivo de mano.</span><span class="sxs-lookup"><span data-stu-id="223bb-104">This topic describes a workflow that enables registration of raw material consumption in production by using a handheld device.</span></span>

<a name="introduction"></a><span data-ttu-id="223bb-105">Introducción</span><span class="sxs-lookup"><span data-stu-id="223bb-105">Introduction</span></span>
------------

<span data-ttu-id="223bb-106">Este flujo de trabajo es relevante si hay un requisito estricto para la trazabilidad del material.</span><span class="sxs-lookup"><span data-stu-id="223bb-106">This workflow is relevant if there is a strict requirement for material traceability.</span></span> <span data-ttu-id="223bb-107">En tales casos, para mantener la trazabilidad de los materiales, la hora y la cantidad exactas se deben notificar para el consumo.</span><span class="sxs-lookup"><span data-stu-id="223bb-107">In those cases, to maintain traceability of the materials, the exact time and quantity must be reported for the consumption.</span></span> <span data-ttu-id="223bb-108">Este proceso se puede ver en comparación con operaciones de autoconsumo o flujo invertido, donde hay una demora entre la hora de registro y la hora en la que tiene lugar el consumo real.</span><span class="sxs-lookup"><span data-stu-id="223bb-108">This process can be seen as opposed to pre- or back-flushing operations, where there is an offset between the time of registration and the time when the actual consumption takes place.</span></span> <span data-ttu-id="223bb-109">Esto explica por qué una estrategia de consumo automático no se puede usar para algunos materiales con requisitos de la trazabilidad.</span><span class="sxs-lookup"><span data-stu-id="223bb-109">This explains why a strategy of automatic consumption cannot be used for some materials with traceability requirements.</span></span> <span data-ttu-id="223bb-110">Miremos una situación de ejemplo sencilla que explica cómo configurar un flujo de trabajo para habilitar el registro de consumo de materias primas en la producción mediante un dispositivo de mano.</span><span class="sxs-lookup"><span data-stu-id="223bb-110">Let’s look at a simple scenario that explains how to set up a workflow to enable registration of raw material consumption in production by using a handheld device.</span></span> <span data-ttu-id="223bb-111">[![configurar un flujo de trabajo para habilitar el registro de consumo de materias primas mediante un dispositivo de mano](./media/scenario3.png)](./media/scenario3.png)</span><span class="sxs-lookup"><span data-stu-id="223bb-111">[![set up a workflow to enable registration of raw material consumption by using a handheld device](./media/scenario3.png)](./media/scenario3.png)</span></span>

### <a name="scenario-details"></a><span data-ttu-id="223bb-112">Detalles del escenario</span><span class="sxs-lookup"><span data-stu-id="223bb-112">Scenario details</span></span>

<span data-ttu-id="223bb-113">Un proceso continuo de producción (5) consume la materia prima RM-100 controlada por lotes.</span><span class="sxs-lookup"><span data-stu-id="223bb-113">A continuous production process (5) consumes the batch-controlled raw material RM-100.</span></span> <span data-ttu-id="223bb-114">El material está disponible en la ubicación Bulk-001 (1), en la matrícula PL -1 con dos lotes, B1 y B2, ambos con una cantidad de 100 lbs.</span><span class="sxs-lookup"><span data-stu-id="223bb-114">The material is on-hand on location Bulk-001 (1) on license plate PL-1 with two batches, B1 and B2, both with a quantity of 100 lbs.</span></span> <span data-ttu-id="223bb-115">El trabajo de almacén (2) se libera y se procesa para RM-100, y se recoge el material de Bulk-001 a la ubicación de entrada de producción PIL-01 (3), que se define como sin control de matrículas.</span><span class="sxs-lookup"><span data-stu-id="223bb-115">Warehouse work (2) is released and processed for RM-100, and the material is picked from Bulk-001 to the production input location PIL-01 (3), which is defined as non-license plate controlled.</span></span> <span data-ttu-id="223bb-116">El operador de maquinaria pesa el material de la ubicación de entrada de producción (3) y registra el peso y el número de lote como consumido (4).</span><span class="sxs-lookup"><span data-stu-id="223bb-116">The machine operator weighs out material from the production input location (3) and registers the weight and batch number as consumed (4).</span></span> <span data-ttu-id="223bb-117">Desde la ubicación de entrada de producción, se agrega una parte del material manualmente al proceso de producción a intervalos de tiempo definidos.</span><span class="sxs-lookup"><span data-stu-id="223bb-117">From the production input location, a portion of the material is manually added to the production process in defined time intervals.</span></span> <span data-ttu-id="223bb-118">Cuando el operador de maquinaria agrega el material, se pesa en una báscula y se registra el número de lote.</span><span class="sxs-lookup"><span data-stu-id="223bb-118">When the machine operator adds material, it is weighed on a scale and the batch number is registered.</span></span>

## <a name="set-up-the-workflow-to-register-consumption-using-a-handheld-device"></a><span data-ttu-id="223bb-119">Configuración del flujo de trabajo para registrar el consumo mediante un dispositivo de mano</span><span class="sxs-lookup"><span data-stu-id="223bb-119">Set up the workflow to register consumption using a handheld device</span></span>
<span data-ttu-id="223bb-120">Cree un producto de bien terminado, FG-100, con una lista de materiales con la materia prima controlada por lotes RM-100.</span><span class="sxs-lookup"><span data-stu-id="223bb-120">Create a finished-good product, FG-100, with a bill of material that has the batch-controlled raw material RM-100.</span></span> <span data-ttu-id="223bb-121">Agregue dos lotes, B1 y B2, de RM-100 en una cantidad de 100 a la ubicación: Bulk-001 en la matrícula: PL-1.</span><span class="sxs-lookup"><span data-stu-id="223bb-121">Add two batches, B1 and B2, of RM-100 in a quantity of 100 to location: Bulk-001 on license plate: PL-1.</span></span> <span data-ttu-id="223bb-122">El principio de vaciado de la línea de lista de materiales para RM-100 se establece en **Manual**.</span><span class="sxs-lookup"><span data-stu-id="223bb-122">The flushing principle on the bill of material line for RM-100 is set to **Manual**.</span></span> <span data-ttu-id="223bb-123">Configure la ubicación de entrada de producción como PIL-01.</span><span class="sxs-lookup"><span data-stu-id="223bb-123">Set  the production input location to PIL-01.</span></span> <span data-ttu-id="223bb-124">Puede hacerlo seleccionando esta ubicación como ubicación de entrada de producción predeterminada en el almacén 51.</span><span class="sxs-lookup"><span data-stu-id="223bb-124">You can do that by selecting this location as the default production input location on warehouse 51.</span></span>

1.  <span data-ttu-id="223bb-125">Cree un nuevo elemento de menú del dispositivo móvil:</span><span class="sxs-lookup"><span data-stu-id="223bb-125">Create a new mobile device menu item:</span></span> 

-    <span data-ttu-id="223bb-126">**Nombre de elemento de menú**: Registrar el consumo de material.</span><span class="sxs-lookup"><span data-stu-id="223bb-126">**Menu item name** - Register material consumption.</span></span> 
-    <span data-ttu-id="223bb-127">**Título**: Registrar el consumo de material.</span><span class="sxs-lookup"><span data-stu-id="223bb-127">**Title** - Register material consumption.</span></span> 
-    <span data-ttu-id="223bb-128">**Modo**: Indirecto.</span><span class="sxs-lookup"><span data-stu-id="223bb-128">**Mode** - Indirect.</span></span> 
-    <span data-ttu-id="223bb-129">**Código de actividad**: Registrar el consumo de material.</span><span class="sxs-lookup"><span data-stu-id="223bb-129">**Activity code** - Register material consumption.</span></span>

2.  <span data-ttu-id="223bb-130">Añada el elemento de menú al menú de dispositivo **Móvil de producción**.</span><span class="sxs-lookup"><span data-stu-id="223bb-130">Add the menu item to the **Production Mobile** device menu.</span></span>
3.  <span data-ttu-id="223bb-131">Cree un pedido de producción para el producto acabado:</span><span class="sxs-lookup"><span data-stu-id="223bb-131">Create a production order for the finished product:</span></span> 

-    <span data-ttu-id="223bb-132">**Número de artículo**: FG-100</span><span class="sxs-lookup"><span data-stu-id="223bb-132">**Item number** - FG-100</span></span> 
-    <span data-ttu-id="223bb-133">**Sitio**: 5</span><span class="sxs-lookup"><span data-stu-id="223bb-133">**Site** - 5</span></span> 
-    <span data-ttu-id="223bb-134">**Almacén**: 51</span><span class="sxs-lookup"><span data-stu-id="223bb-134">**Warehouse** - 51</span></span> 
-    <span data-ttu-id="223bb-135">**Cantidad**: 150</span><span class="sxs-lookup"><span data-stu-id="223bb-135">**Quantity** - 150</span></span>

<span data-ttu-id="223bb-136">El pedido de producción es **Estimado** y **Liberado** y se crea el trabajo de almacén.</span><span class="sxs-lookup"><span data-stu-id="223bb-136">The production order is **Estimated** and **Released** and warehouse work is created.</span></span>

4.  <span data-ttu-id="223bb-137">Complete el trabajo mediante el flujo de trabajo para la selección de materias primas para el dispositivo de mano.</span><span class="sxs-lookup"><span data-stu-id="223bb-137">Complete the work using the workflow for raw material picking for the handheld device.</span></span>

<span data-ttu-id="223bb-138">Esto traerá el material de la ubicación de almacenaje a la ubicación de entrada de producción PIL-01.</span><span class="sxs-lookup"><span data-stu-id="223bb-138">This will bring the material from the bulk location to the production input location PIL-01.</span></span> <span data-ttu-id="223bb-139">Una vez que haya terminado el trabajo, el material tiene el estado **Seleccionado en la ubicación de entrada de producción**.</span><span class="sxs-lookup"><span data-stu-id="223bb-139">After the work is completed, the material has the status **Picked on the production input location**.</span></span> <span data-ttu-id="223bb-140">El estado después de que se haya procesado el trabajo puede ser **Seleccionado** o **Reservado físicamente**.</span><span class="sxs-lookup"><span data-stu-id="223bb-140">The status after work has been processed can be either **Picked** or **Reserved physical**.</span></span> <span data-ttu-id="223bb-141">Esto se configura con el parámetro **Estado de emisión después de puesto el formulario Almacén**.</span><span class="sxs-lookup"><span data-stu-id="223bb-141">This is configured with the parameter **Issue status after put on the warehouse form**.</span></span>

5.  <span data-ttu-id="223bb-142">Iniciar el pedido de producción desde el cliente o desde el dispositivo de mano mediante el elemento de menú **Iniciar producción** .</span><span class="sxs-lookup"><span data-stu-id="223bb-142">Start the production order either from the client or from the handheld device by using the **Production start** menu item.</span></span>

<span data-ttu-id="223bb-143">Una vez iniciado el pedido de producción, puede registrar el consumo de materiales mediante el flujo de trabajo del dispositivo de mano.</span><span class="sxs-lookup"><span data-stu-id="223bb-143">After the production order has been started, you can register material consumption with the workflow for the handheld device.</span></span> <span data-ttu-id="223bb-144">Comencemos por registrar el consumo de 25 libras del lote B1.</span><span class="sxs-lookup"><span data-stu-id="223bb-144">Let's start by registering consumption of 25 lbs of batch B1.</span></span>

6.  <span data-ttu-id="223bb-145">Seleccione el elemento de menú **Registrar el** **consumo de material** en el menú del dispositivo de mano, especifique los detalles siguientes:</span><span class="sxs-lookup"><span data-stu-id="223bb-145">Select the **Register material** **consumption** menu item in the menu for the hand held device, enter the following details:</span></span> 

-    <span data-ttu-id="223bb-146">El número de pedido de producción.</span><span class="sxs-lookup"><span data-stu-id="223bb-146">The production order number.</span></span> 
-    <span data-ttu-id="223bb-147">La ubicación en la que el material se va a consumir, en este caso PIL-01.</span><span class="sxs-lookup"><span data-stu-id="223bb-147">The location on which the material is going to be consumed, in this case PIL-01.</span></span> 
-    <span data-ttu-id="223bb-148">Número de artículo RM-100.</span><span class="sxs-lookup"><span data-stu-id="223bb-148">Item number RM-100.</span></span> 
-    <span data-ttu-id="223bb-149">Número de lote B1.</span><span class="sxs-lookup"><span data-stu-id="223bb-149">Batch number B1.</span></span> 
-    <span data-ttu-id="223bb-150">Cantidad de 25.</span><span class="sxs-lookup"><span data-stu-id="223bb-150">A quantity of 25.</span></span>

7.  <span data-ttu-id="223bb-151">Seleccionar **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="223bb-151">Select **OK**.</span></span>

<span data-ttu-id="223bb-152">Tenga en cuenta que el mensaje “Se creó la línea de diario” aparece en la pantalla.</span><span class="sxs-lookup"><span data-stu-id="223bb-152">Note that the message "Journal line is created" appears on the display.</span></span> <span data-ttu-id="223bb-153">En el pedido de producción existe un diario abierto del tipo **Lista de selección de producción** para el número de artículo RM-100 y el número de lote B1.</span><span class="sxs-lookup"><span data-stu-id="223bb-153">On the production order there is an open journal of the type **Production picking list** for item number RM-100 and batch number B1.</span></span> 

<span data-ttu-id="223bb-154">Ahora puede optar por continuar su registro, por ejemplo en el número de lote B2, y cada vez que se seleccione **Aceptar,** una nueva línea de diario se agrega al diario abierto.</span><span class="sxs-lookup"><span data-stu-id="223bb-154">You can now choose to continue your registration, for example on batch number B2, and each time you select **OK,** a new journal line is added to the open journal.</span></span> 

<span data-ttu-id="223bb-155">Una vez que haya terminado su registro, seleccione **Hecho** para registrar el diario y finalizar el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="223bb-155">After you have finished your registration, select **Done** to post the journal and end the workflow.</span></span>

### <a name="additional-comments"></a><span data-ttu-id="223bb-156">Comentarios adicionales</span><span class="sxs-lookup"><span data-stu-id="223bb-156">Additional comments</span></span> 

-   <span data-ttu-id="223bb-157">Si un usuario cancela el flujo de trabajo después de que se cree una línea de diario, el diario se encuentra en estado sin registrar, pero si el usuario en un momento posterior utiliza el flujo de trabajo para el mismo pedido de producción, las líneas se agregarán al diario abierto en lugar de un nuevo diario.</span><span class="sxs-lookup"><span data-stu-id="223bb-157">If a user cancels the workflow after a journal line is created, the journal is in an unposted state but if the user at a later point uses the workflow for the same production order, then the lines will be added to the open journal rather than to a new journal.</span></span>
-   <span data-ttu-id="223bb-158">El nuevo flujo de trabajo también admite el registro de números de serie.</span><span class="sxs-lookup"><span data-stu-id="223bb-158">The new workflow also supports the registration of serial numbers.</span></span>
-   <span data-ttu-id="223bb-159">Es posible registrar sólo un número de artículo definido en la lista de materiales o en la fórmula del pedido de producción seleccionado o del pedido de lote.</span><span class="sxs-lookup"><span data-stu-id="223bb-159">It is only possible to register an item number that is defined in the bill of material or in the formula for the selected production order or batch order.</span></span>
-   <span data-ttu-id="223bb-160">El material puede sobreconsumirse.</span><span class="sxs-lookup"><span data-stu-id="223bb-160">Material can be overconsumed.</span></span> <span data-ttu-id="223bb-161">Por ejemplo, si se estima que el material se consumirá con la cantidad de 100 libras, después puede sobreconsumirse con una cantidad de, por ejemplo, 105 lbs.</span><span class="sxs-lookup"><span data-stu-id="223bb-161">For example, if the material is estimated to be consumed with the quantity of 100 lbs, then it can be overconsumed with a quantity of, for example, 105 lbs.</span></span>




[!INCLUDE[footer-include](../../includes/footer-banner.md)]