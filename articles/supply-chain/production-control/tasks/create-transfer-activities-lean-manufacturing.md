--- 
title: "Crear actividades de transferencia para lean manufacturing (producción ajustada)"
description: Cree una actividad de transferencia para lean manufacturing.
author: cvocph
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 1762d369af9e762c5f9b3833d6b982c74d41eedc
ms.contentlocale: es-es
ms.lasthandoff: 08/07/2018

---
# <a name="create-transfer-activities-for-lean-manufacturing"></a><span data-ttu-id="2e074-103">Crear actividades de transferencia para lean manufacturing (producción ajustada)</span><span class="sxs-lookup"><span data-stu-id="2e074-103">Create transfer activities for lean manufacturing</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="2e074-104">Cree una actividad de transferencia para lean manufacturing.</span><span class="sxs-lookup"><span data-stu-id="2e074-104">Create a transfer activity for lean manufacturing.</span></span> 

<span data-ttu-id="2e074-105">Requisitos previos:</span><span class="sxs-lookup"><span data-stu-id="2e074-105">Prerequisites:</span></span> 

1. <span data-ttu-id="2e074-106">Se deben crear un flujo de producción y una versión que no estén activas.</span><span class="sxs-lookup"><span data-stu-id="2e074-106">A production flow and version that is not active must be created.</span></span>

2. <span data-ttu-id="2e074-107">Se deben crear el almacén de origen y destino.</span><span class="sxs-lookup"><span data-stu-id="2e074-107">The from and to warehouse and locations must be created.</span></span> <span data-ttu-id="2e074-108">Opcionalmente, se debe crear la celda de trabajo que está reabasteciendo o que está reabastecida.</span><span class="sxs-lookup"><span data-stu-id="2e074-108">Optionally, the replenishing or the replenished work cell should be created.</span></span>


## <a name="find-the-production-flow-version"></a><span data-ttu-id="2e074-109">Buscar la versión del flujo de producción</span><span class="sxs-lookup"><span data-stu-id="2e074-109">Find the production flow version</span></span>
1. <span data-ttu-id="2e074-110">Vaya a Control de producción > Configuración > Flujo de producción lean > Flujos de producción.</span><span class="sxs-lookup"><span data-stu-id="2e074-110">Go to Production control > Setup > Lean production flow > Production flows.</span></span>
2. <span data-ttu-id="2e074-111">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="2e074-111">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="2e074-112">Tenga en cuenta que el flujo de producción debe tener una versión en estado de borrador.</span><span class="sxs-lookup"><span data-stu-id="2e074-112">Note that the production flow must have a version in draft status.</span></span>  
3. <span data-ttu-id="2e074-113">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="2e074-113">In the list, click the link in the selected row.</span></span>

## <a name="create-a-new-activity"></a><span data-ttu-id="2e074-114">Crear una actividad nueva</span><span class="sxs-lookup"><span data-stu-id="2e074-114">Create a new activity</span></span>
1. <span data-ttu-id="2e074-115">Haga clic en Actividades.</span><span class="sxs-lookup"><span data-stu-id="2e074-115">Click Activities.</span></span>
    * <span data-ttu-id="2e074-116">Asegúrese de que el flujo de producción seleccionado tiene una versión en borrador y seleccione esa versión.</span><span class="sxs-lookup"><span data-stu-id="2e074-116">Ensure that the selected production flow has a version in draft and select that version.</span></span>  
2. <span data-ttu-id="2e074-117">Haga clic en Crear actividad de plan nueva.</span><span class="sxs-lookup"><span data-stu-id="2e074-117">Click Create new plan activity.</span></span>
3. <span data-ttu-id="2e074-118">Haga clic en Siguiente.</span><span class="sxs-lookup"><span data-stu-id="2e074-118">Click Next.</span></span>
4. <span data-ttu-id="2e074-119">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="2e074-119">In the Name field, type a value.</span></span>
5. <span data-ttu-id="2e074-120">En el campo Tipo de actividad, seleccione "Transferencia".</span><span class="sxs-lookup"><span data-stu-id="2e074-120">In the Activity type field, select 'Transfer'.</span></span>
6. <span data-ttu-id="2e074-121">En el campo Cantidad del proceso, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="2e074-121">In the Process quantity field, enter a number.</span></span>
7. <span data-ttu-id="2e074-122">Haga clic en Siguiente.</span><span class="sxs-lookup"><span data-stu-id="2e074-122">Click Next.</span></span>

## <a name="select-the-work-cells"></a><span data-ttu-id="2e074-123">Seleccionar las celdas de trabajo</span><span class="sxs-lookup"><span data-stu-id="2e074-123">Select the Work cells</span></span>
1. <span data-ttu-id="2e074-124">En el campo Reabasteciendo, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="2e074-124">In the Replenishing field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="2e074-125">Para usar la ubicación de salida de la celda de trabajo como la ubicación de origen en la actividad de transferencia, seleccione una celda de trabajo.</span><span class="sxs-lookup"><span data-stu-id="2e074-125">To use the work cell output location as the from location in the transfer activity, select a work cell.</span></span> <span data-ttu-id="2e074-126">Lo mismo se puede realizar con la celda de trabajo reabastecida, que establece la ubicación de destino de la actividad de transferencia.</span><span class="sxs-lookup"><span data-stu-id="2e074-126">The same can be done with the replenished work cell, which sets the target location of the transfer activity.</span></span>  
2. <span data-ttu-id="2e074-127">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="2e074-127">In the list, click the link in the selected row.</span></span>

## <a name="define-the-inventory-updates"></a><span data-ttu-id="2e074-128">Definir las actualizaciones de inventario</span><span class="sxs-lookup"><span data-stu-id="2e074-128">Define the inventory updates</span></span>
1. <span data-ttu-id="2e074-129">En el campo Tipo de producto, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="2e074-129">In the Product type field, select an option.</span></span>
    * <span data-ttu-id="2e074-130">Tenga en cuenta que una transferencia no cambia el tipo de producto.</span><span class="sxs-lookup"><span data-stu-id="2e074-130">Note that a transfer does not change the type of product.</span></span> <span data-ttu-id="2e074-131">Puede transferir los productos terminados o los productos semiterminados (transferencia entre dos actividades de un flujo de producción y posiblemente un flujo kanban).</span><span class="sxs-lookup"><span data-stu-id="2e074-131">You can transfer finished products or semi-finished products (transfer between two activities of a production flow and possibly a kanban flow).</span></span>     <span data-ttu-id="2e074-132">Al transferir productos terminados, puede elegir si seleccionar o recibir resultados en una transacción de inventario.</span><span class="sxs-lookup"><span data-stu-id="2e074-132">When transferring finished products, you can select if picking or receiving results in an inventory transaction.</span></span>  

## <a name="define-the-transfer-locations"></a><span data-ttu-id="2e074-133">Definir las ubicaciones de transferencia</span><span class="sxs-lookup"><span data-stu-id="2e074-133">Define the transfer locations</span></span>
1. <span data-ttu-id="2e074-134">Haga clic en Siguiente.</span><span class="sxs-lookup"><span data-stu-id="2e074-134">Click Next.</span></span>
2. <span data-ttu-id="2e074-135">En el campo Almacén, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="2e074-135">In the Warehouse field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="2e074-136">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="2e074-136">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="2e074-137">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="2e074-137">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="2e074-138">En el campo Ubicación, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="2e074-138">In the Location field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="2e074-139">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="2e074-139">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="2e074-140">En el campo Fletado por, seleccione el “Expedidor”.</span><span class="sxs-lookup"><span data-stu-id="2e074-140">In the Freighted by field, select 'Shipper'.</span></span>
    * <span data-ttu-id="2e074-141">Se incluyen las siguientes opciones: Expedidor: la organización que opera el almacén del envío, Destinatario: la organización que opera el almacén de recepción, Transportista: un proveedor de terceros.</span><span class="sxs-lookup"><span data-stu-id="2e074-141">Options include: Shipper - the organization operating the shipping warehouse, Recipient -  the organization operating the receiving warehouse, Carrier - a third party vendor.</span></span> <span data-ttu-id="2e074-142">Si la organización operativa es un proveedor, la actividad de transferencia requiere un acuerdo de subcontratación.</span><span class="sxs-lookup"><span data-stu-id="2e074-142">If the operating organization is a vendor, the transfer activity requires a subcontracting agreement.</span></span>  
8. <span data-ttu-id="2e074-143">Haga clic en Siguiente.</span><span class="sxs-lookup"><span data-stu-id="2e074-143">Click Next.</span></span>

## <a name="define-the-activity-times"></a><span data-ttu-id="2e074-144">Defina los tiempos de actividad</span><span class="sxs-lookup"><span data-stu-id="2e074-144">Define the activity times</span></span>
1. <span data-ttu-id="2e074-145">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="2e074-145">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="2e074-146">Se requiere la definición de un tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="2e074-146">The definition of a Runtime is required.</span></span> <span data-ttu-id="2e074-147">El tiempo de ejecución se usa para calcular costes y los tiempos de procesamiento de los trabajos kanban.</span><span class="sxs-lookup"><span data-stu-id="2e074-147">The Runtime is used to calculate cost and the throughput times of the kanban jobs.</span></span> <span data-ttu-id="2e074-148">Los tiempos de ejecución no se usan para calcular la carga de capacidad y el consumo; esto se calcula por el tiempo de ciclo, derivado de la tarea de la versión del flujo de producción.</span><span class="sxs-lookup"><span data-stu-id="2e074-148">Runtimes are not used to calculate capacity load and consumption, which is calculated by cycle time, derived from the production flow version task.</span></span>  
2. <span data-ttu-id="2e074-149">En campo de tiempo, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="2e074-149">In the Time field, enter a number.</span></span>
3. <span data-ttu-id="2e074-150">En el campo Unidad, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="2e074-150">In the Unit field, type a value.</span></span>
4. <span data-ttu-id="2e074-151">Seleccione la unidad de tiempo.</span><span class="sxs-lookup"><span data-stu-id="2e074-151">Select the Time unit.</span></span>
5. <span data-ttu-id="2e074-152">En el campo Por cantidad, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="2e074-152">In the Per quantity field, enter a number.</span></span>
6. <span data-ttu-id="2e074-153">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="2e074-153">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="2e074-154">Los tiempos de cola son opcionales.</span><span class="sxs-lookup"><span data-stu-id="2e074-154">Queue times are optional.</span></span>  
7. <span data-ttu-id="2e074-155">En campo de tiempo, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="2e074-155">In the Time field, enter a number.</span></span>
8. <span data-ttu-id="2e074-156">En el campo Unidad, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="2e074-156">In the Unit field, type a value.</span></span>
9. <span data-ttu-id="2e074-157">Seleccione la unidad de tiempo.</span><span class="sxs-lookup"><span data-stu-id="2e074-157">Select the Time unit.</span></span>
10. <span data-ttu-id="2e074-158">En el campo Por cantidad, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="2e074-158">In the Per quantity field, enter a number.</span></span>
11. <span data-ttu-id="2e074-159">Haga clic en Siguiente.</span><span class="sxs-lookup"><span data-stu-id="2e074-159">Click Next.</span></span>
12. <span data-ttu-id="2e074-160">Haga clic en Finalizar.</span><span class="sxs-lookup"><span data-stu-id="2e074-160">Click Finish.</span></span>
13. <span data-ttu-id="2e074-161">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="2e074-161">Close the page.</span></span>


