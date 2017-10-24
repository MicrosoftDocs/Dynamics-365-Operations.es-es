--- 
title: "Crear actividades de proceso para lean manufacturing (producción ajustada)"
description: Cree una actividad de proceso para lean manufacturing.
author: cvocph
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: dd77c20b622fd8a14e1cdf77883043699f9a6317
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="create-process-activities-for-lean-manufacturing"></a><span data-ttu-id="e84b2-103">Crear actividades de proceso para lean manufacturing (producción ajustada)</span><span class="sxs-lookup"><span data-stu-id="e84b2-103">Create process activities for lean manufacturing</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e84b2-104">Cree una actividad de proceso para lean manufacturing.</span><span class="sxs-lookup"><span data-stu-id="e84b2-104">Create a process activity for lean manufacturing.</span></span> 

<span data-ttu-id="e84b2-105">Requisitos previos:</span><span class="sxs-lookup"><span data-stu-id="e84b2-105">Prerequisites:</span></span> 

1. <span data-ttu-id="e84b2-106">Se deben crear un flujo de producción y una versión que no estén activas.</span><span class="sxs-lookup"><span data-stu-id="e84b2-106">A production flow and version that is not active must be created.</span></span>

2. <span data-ttu-id="e84b2-107">Se debe crear una celda de trabajo.</span><span class="sxs-lookup"><span data-stu-id="e84b2-107">A work cell must be created.</span></span>


## <a name="find-the-production-flow-version"></a><span data-ttu-id="e84b2-108">Buscar la versión del flujo de producción</span><span class="sxs-lookup"><span data-stu-id="e84b2-108">Find the production flow version</span></span>
1. <span data-ttu-id="e84b2-109">Vaya a Control de producción > Configuración > Flujo de producción lean > Flujos de producción.</span><span class="sxs-lookup"><span data-stu-id="e84b2-109">Go to Production control > Setup > Lean production flow > Production flows.</span></span>
2. <span data-ttu-id="e84b2-110">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="e84b2-110">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="e84b2-111">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="e84b2-111">In the list, click the link in the selected row.</span></span>

## <a name="create-a-new-activity"></a><span data-ttu-id="e84b2-112">Crear una actividad nueva</span><span class="sxs-lookup"><span data-stu-id="e84b2-112">Create a new activity</span></span>
1. <span data-ttu-id="e84b2-113">Haga clic en Actividades.</span><span class="sxs-lookup"><span data-stu-id="e84b2-113">Click Activities.</span></span>
    * <span data-ttu-id="e84b2-114">Asegúrese de que el flujo de producción seleccionado tiene una versión en borrador y seleccione esa versión.</span><span class="sxs-lookup"><span data-stu-id="e84b2-114">Ensure that the selected production flow has a version in draft and select that version.</span></span>  
2. <span data-ttu-id="e84b2-115">Haga clic en Crear actividad de plan nueva.</span><span class="sxs-lookup"><span data-stu-id="e84b2-115">Click Create new plan activity.</span></span>
3. <span data-ttu-id="e84b2-116">Haga clic en Siguiente.</span><span class="sxs-lookup"><span data-stu-id="e84b2-116">Click Next.</span></span>
4. <span data-ttu-id="e84b2-117">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="e84b2-117">In the Name field, type a value.</span></span>
5. <span data-ttu-id="e84b2-118">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="e84b2-118">In the Name field, type a value.</span></span>
    * <span data-ttu-id="e84b2-119">Tenga en cuenta que el nombre debe ser único para un flujo de producción dado para todas las versiones.</span><span class="sxs-lookup"><span data-stu-id="e84b2-119">Note that the name must be unique for a given production flow for all versions.</span></span>  
6. <span data-ttu-id="e84b2-120">En el campo Cantidad del proceso, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="e84b2-120">In the Process quantity field, enter a number.</span></span>
    * <span data-ttu-id="e84b2-121">Tenga en cuenta que no importa cuál sea la cantidad de trabajo que se procesará, esta es la cantidad mínima por trabajo para calcular el coste de mano de obra.</span><span class="sxs-lookup"><span data-stu-id="e84b2-121">Note that no matter what job quantity will be processed, this is the minimum quantity per job to calculate the labor cost.</span></span> <span data-ttu-id="e84b2-122">Si las cantidades de trabajo se desvían de esta cantidad, se creará la desviación del coste de mano de obra.</span><span class="sxs-lookup"><span data-stu-id="e84b2-122">If job quantities deviate from this quantity, labor cost variance will be created.</span></span>  
7. <span data-ttu-id="e84b2-123">Haga clic en Siguiente.</span><span class="sxs-lookup"><span data-stu-id="e84b2-123">Click Next.</span></span>

## <a name="select-the-work-cell"></a><span data-ttu-id="e84b2-124">Seleccionar la celda de trabajo</span><span class="sxs-lookup"><span data-stu-id="e84b2-124">Select the work cell</span></span>
1. <span data-ttu-id="e84b2-125">En el campo Celda de trabajo, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="e84b2-125">In the Work cell field, click the drop-down button to open the lookup.</span></span>
2. <span data-ttu-id="e84b2-126">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="e84b2-126">In the list, click the link in the selected row.</span></span>

## <a name="define-the-inventory-updates"></a><span data-ttu-id="e84b2-127">Definir las actualizaciones de inventario</span><span class="sxs-lookup"><span data-stu-id="e84b2-127">Define the inventory updates</span></span>
1. <span data-ttu-id="e84b2-128">Active o desactive la casilla Actualizar recepción disponible.</span><span class="sxs-lookup"><span data-stu-id="e84b2-128">Select or clear the Update on hand receipt check box.</span></span>
    * <span data-ttu-id="e84b2-129">Si Actualizar disponible = No, puede definir la actividad para recibir un producto semiterminado (la actividad no llega al siguiente nivel de L. MAT).</span><span class="sxs-lookup"><span data-stu-id="e84b2-129">If Update On hand = No, you can define the activity to receive a semi-finished product (the activity does not reach the next BOM level).</span></span>    <span data-ttu-id="e84b2-130">También puede seleccionar consumir productos semiterminados.</span><span class="sxs-lookup"><span data-stu-id="e84b2-130">You can also select to consume semi-finished products.</span></span>  

## <a name="define-the-picking-activities"></a><span data-ttu-id="e84b2-131">Definir las actividades de picking</span><span class="sxs-lookup"><span data-stu-id="e84b2-131">Define the picking activities</span></span>
1. <span data-ttu-id="e84b2-132">Haga clic en Siguiente.</span><span class="sxs-lookup"><span data-stu-id="e84b2-132">Click Next.</span></span>
2. <span data-ttu-id="e84b2-133">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="e84b2-133">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="e84b2-134">Se creará una actividad de selección predeterminada para la ubicación de entrada de la celda de trabajo seleccionada.</span><span class="sxs-lookup"><span data-stu-id="e84b2-134">A default picking activity is created for the input location of the selected work cell.</span></span>  
3. <span data-ttu-id="e84b2-135">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="e84b2-135">Click Add.</span></span>
    * <span data-ttu-id="e84b2-136">Puede crear actividades de picking adicionales para productos específicos, que no se almacenan provisionalmente en la actividad de entrada de la celda de trabajo.</span><span class="sxs-lookup"><span data-stu-id="e84b2-136">You can create additional picking activities for specific products, that are not staged at the work cell input activity.</span></span>  
4. <span data-ttu-id="e84b2-137">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="e84b2-137">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="e84b2-138">En el campo Código de artículo, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="e84b2-138">In the Item number field, type a value.</span></span>
6. <span data-ttu-id="e84b2-139">En el campo Almacén, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="e84b2-139">In the Warehouse field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="e84b2-140">Con esta definición, todos los materiales consumidos en la actividad se seleccionan de la ubicación y del almacén de entrada predeterminada excepto el artículo que se define en la segunda actividad de selección.</span><span class="sxs-lookup"><span data-stu-id="e84b2-140">With this definition, all materials consumed in the activity are picked from the default input warehouse and location except the item that is defined in the second picking activity.</span></span> <span data-ttu-id="e84b2-141">Este artículo se seleccionará de una ubicación y almacén distintos.</span><span class="sxs-lookup"><span data-stu-id="e84b2-141">This item will be picked from a different warehouse and location.</span></span>  
7. <span data-ttu-id="e84b2-142">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="e84b2-142">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="e84b2-143">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="e84b2-143">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="e84b2-144">Active o desactive la casilla Registrar residuo.</span><span class="sxs-lookup"><span data-stu-id="e84b2-144">Select or clear the Register scrap check box.</span></span>
10. <span data-ttu-id="e84b2-145">Haga clic en Siguiente.</span><span class="sxs-lookup"><span data-stu-id="e84b2-145">Click Next.</span></span>

## <a name="define-the-activity-times"></a><span data-ttu-id="e84b2-146">Defina los tiempos de actividad</span><span class="sxs-lookup"><span data-stu-id="e84b2-146">Define the activity times</span></span>
1. <span data-ttu-id="e84b2-147">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="e84b2-147">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="e84b2-148">Se requiere la definición de un tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="e84b2-148">The definition of a Runtime is required.</span></span> <span data-ttu-id="e84b2-149">El tiempo de ejecución se usa para calcular costes y los tiempos de procesamiento de los trabajos kanban.</span><span class="sxs-lookup"><span data-stu-id="e84b2-149">The Runtime is used to calculate costs and the throughput times of the kanban jobs.</span></span> <span data-ttu-id="e84b2-150">Los tiempos de ejecución no se usan para calcular la carga de capacidad y el consumo; esto se calcula por el tiempo de ciclo, derivado de la tarea de la versión del flujo de producción.</span><span class="sxs-lookup"><span data-stu-id="e84b2-150">Runtimes are not used to calculate capacity load and consumption, this is calculated by cycle time, derived from the production flow version task.</span></span>  
2. <span data-ttu-id="e84b2-151">En campo de tiempo, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="e84b2-151">In the Time field, enter a number.</span></span>
3. <span data-ttu-id="e84b2-152">En el campo Unidad, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="e84b2-152">In the Unit field, type a value.</span></span>
4. <span data-ttu-id="e84b2-153">Seleccione la unidad de tiempo.</span><span class="sxs-lookup"><span data-stu-id="e84b2-153">Select the Time unit.</span></span>
5. <span data-ttu-id="e84b2-154">En el campo Por cantidad, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="e84b2-154">In the Per quantity field, enter a number.</span></span>
6. <span data-ttu-id="e84b2-155">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="e84b2-155">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="e84b2-156">Los tiempos de cola son opcionales.</span><span class="sxs-lookup"><span data-stu-id="e84b2-156">Queue times are optional.</span></span>  
7. <span data-ttu-id="e84b2-157">En campo de tiempo, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="e84b2-157">In the Time field, enter a number.</span></span>
8. <span data-ttu-id="e84b2-158">En el campo Unidad, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="e84b2-158">In the Unit field, type a value.</span></span>
9. <span data-ttu-id="e84b2-159">Seleccione la unidad de tiempo.</span><span class="sxs-lookup"><span data-stu-id="e84b2-159">Select the Time unit.</span></span>
10. <span data-ttu-id="e84b2-160">En el campo Por cantidad, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="e84b2-160">In the Per quantity field, enter a number.</span></span>
11. <span data-ttu-id="e84b2-161">Haga clic en Siguiente.</span><span class="sxs-lookup"><span data-stu-id="e84b2-161">Click Next.</span></span>
12. <span data-ttu-id="e84b2-162">Haga clic en Finalizar.</span><span class="sxs-lookup"><span data-stu-id="e84b2-162">Click Finish.</span></span>
13. <span data-ttu-id="e84b2-163">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="e84b2-163">Close the page.</span></span>


