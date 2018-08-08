--- 
title: "Crear una regla kanban de cantidad fija para fabricación"
description: "Este procedimiento se centra en la configuración necesaria para crear una regla kanban de fabricación fija para activar actividades de transformación, en una celda de trabajo, en un entorno de producción ajustada."
author: ChristianRytt
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 555d79e8bacbae0287472e68701a04a3c1d635aa
ms.contentlocale: es-es
ms.lasthandoff: 08/07/2018

---
# <a name="create-a-fixed-quantity-kanban-rule-for-manufacturing"></a><span data-ttu-id="93f13-103">Crear una regla kanban de cantidad fija para fabricación</span><span class="sxs-lookup"><span data-stu-id="93f13-103">Create a fixed quantity kanban rule for manufacturing</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="93f13-104">Este procedimiento se centra en la configuración necesaria para crear una regla kanban de fabricación fija para activar actividades de transformación, en una celda de trabajo, en un entorno de producción ajustada.</span><span class="sxs-lookup"><span data-stu-id="93f13-104">This procedure focuses on the setup needed to create a fixed manufacturing kanban rule for triggering transforming activities, at a work cell, in a lean environment.</span></span> <span data-ttu-id="93f13-105">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="93f13-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="93f13-106">Este procedimiento está pensado para el Ingeniero de procesos o el Administrador de flujo de valor, ya que preparan la producción de un producto nuevo o modificado.</span><span class="sxs-lookup"><span data-stu-id="93f13-106">This procedure is intended for the Process Engineer or the Value Stream Manager, as they prepare production of a new or modified product.</span></span>


## <a name="create-new-kanban-rule"></a><span data-ttu-id="93f13-107">Crear nueva regla kanban</span><span class="sxs-lookup"><span data-stu-id="93f13-107">Create new kanban rule</span></span>
1. <span data-ttu-id="93f13-108">Vaya a Reglas kanban.</span><span class="sxs-lookup"><span data-stu-id="93f13-108">Go to Kanban rules.</span></span>
2. <span data-ttu-id="93f13-109">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="93f13-109">Click New.</span></span>
    * <span data-ttu-id="93f13-110">Observe que el tipo predeterminado es Fabricación y la estrategia de reabastecimiento es Fijo.</span><span class="sxs-lookup"><span data-stu-id="93f13-110">Notice that the default Type is Manufacturing and Replenishment strategy is Fixed.</span></span> <span data-ttu-id="93f13-111">No tiene que cambiar estos parámetros.</span><span class="sxs-lookup"><span data-stu-id="93f13-111">You do not have to change these parameters.</span></span>  
3. <span data-ttu-id="93f13-112">En el campo Actividad del primer plan, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="93f13-112">In the First plan activity field, enter or select a value.</span></span>
    * <span data-ttu-id="93f13-113">Esta es la actividad que se realizará para los kanbans creados según esta regla kanban.</span><span class="sxs-lookup"><span data-stu-id="93f13-113">This is the activity that will be performed for kanbans created based on this kanban rule.</span></span>  <span data-ttu-id="93f13-114">Seleccione “SpeakerTestAndPackaging”.</span><span class="sxs-lookup"><span data-stu-id="93f13-114">Select 'SpeakerTestAndPackaging'.</span></span>  
4. <span data-ttu-id="93f13-115">Expanda la sección Detalles.</span><span class="sxs-lookup"><span data-stu-id="93f13-115">Expand the Details section.</span></span>
5. <span data-ttu-id="93f13-116">En el campo Producto, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="93f13-116">In the Product field, enter or select a value.</span></span>
    * <span data-ttu-id="93f13-117">Seleccione L0050.</span><span class="sxs-lookup"><span data-stu-id="93f13-117">Select L0050.</span></span>  
6. <span data-ttu-id="93f13-118">En el campo Unidad de medida, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="93f13-118">In the Unit of measure field, enter or select a value.</span></span>
    * <span data-ttu-id="93f13-119">Seleccione minutos.</span><span class="sxs-lookup"><span data-stu-id="93f13-119">Select minutes.</span></span>  
7. <span data-ttu-id="93f13-120">En el campo Plazo, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="93f13-120">In the Lead time field, enter a number.</span></span>
    * <span data-ttu-id="93f13-121">Escriba 5.</span><span class="sxs-lookup"><span data-stu-id="93f13-121">Enter 5.</span></span>  

## <a name="set-quantities"></a><span data-ttu-id="93f13-122">Definir cantidades</span><span class="sxs-lookup"><span data-stu-id="93f13-122">Set quantities</span></span>
1. <span data-ttu-id="93f13-123">Expanda la sección Cantidades.</span><span class="sxs-lookup"><span data-stu-id="93f13-123">Expand the Quantities section.</span></span>
2. <span data-ttu-id="93f13-124">Defina la cantidad predeterminada en "10".</span><span class="sxs-lookup"><span data-stu-id="93f13-124">Set Default quantity to '10'.</span></span>
    * <span data-ttu-id="93f13-125">Esta es la cantidad que se transferirá para cada kanban.</span><span class="sxs-lookup"><span data-stu-id="93f13-125">This is the quantity that will be transferred for each kanban.</span></span>  
3. <span data-ttu-id="93f13-126">Active la casilla Desviación de cantidad de productos.</span><span class="sxs-lookup"><span data-stu-id="93f13-126">Select the Product quantity variance check box.</span></span>
    * <span data-ttu-id="93f13-127">Con esto, los kanbans seleccionados se puedan completar con una desviación de la cantidad predeterminada.</span><span class="sxs-lookup"><span data-stu-id="93f13-127">With this, selected kanbans can be completed with a variance from the default quantity.</span></span>  <span data-ttu-id="93f13-128">Para permitir que se completen los kanbans con una cantidad comprendida entre 8 y 12, establezca las desviaciones en 2.</span><span class="sxs-lookup"><span data-stu-id="93f13-128">To allow kanbans to be completed with a quantity from 8 to 12, set both variances to 2.</span></span>  
4. <span data-ttu-id="93f13-129">Establezca la desviación por debajo de "2".</span><span class="sxs-lookup"><span data-stu-id="93f13-129">Set Variance below to '2'.</span></span>
    * <span data-ttu-id="93f13-130">Esto le permitirá completar hasta 10 - 2 = 8</span><span class="sxs-lookup"><span data-stu-id="93f13-130">This will allow completing down to 10 - 2 = 8</span></span>  
5. <span data-ttu-id="93f13-131">Establezca la desviación por encima de "2".</span><span class="sxs-lookup"><span data-stu-id="93f13-131">Set Variance above to '2'.</span></span>
    * <span data-ttu-id="93f13-132">Esto le permitirá completar hasta 10 + 2 = 12</span><span class="sxs-lookup"><span data-stu-id="93f13-132">This will allow completing up to 10 + 2 = 12</span></span>  
6. <span data-ttu-id="93f13-133">En el campo Cantidad kanban fija, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="93f13-133">In the Fixed kanban quantity field, enter a number.</span></span>
    * <span data-ttu-id="93f13-134">Este es el importe de kanbans que deben estar activos.</span><span class="sxs-lookup"><span data-stu-id="93f13-134">This is the amount of kanbans that should be active.</span></span> <span data-ttu-id="93f13-135">En este caso, 5 kanban que procesan 10 por cada uno.</span><span class="sxs-lookup"><span data-stu-id="93f13-135">In this case, 5 kanbans processing 10 each.</span></span>  
7. <span data-ttu-id="93f13-136">En el campo Mínimo de límite de alerta, especifique "2".</span><span class="sxs-lookup"><span data-stu-id="93f13-136">In the Alert boundary minimum field, enter '2'.</span></span>
    * <span data-ttu-id="93f13-137">Se usa para realizar el seguimiento del importe mínimo de kanbans completos que deben encontrarse en el destino.</span><span class="sxs-lookup"><span data-stu-id="93f13-137">Used to keep track of the minimum amount of full kanbans that should be at the destination.</span></span> <span data-ttu-id="93f13-138">Por ejemplo, esto se usa en la visión general de la cantidad kanban.</span><span class="sxs-lookup"><span data-stu-id="93f13-138">For example, this is used on the kanban quantity overview.</span></span>  
8. <span data-ttu-id="93f13-139">En el campo Máximo de límite de alerta, especifique "4".</span><span class="sxs-lookup"><span data-stu-id="93f13-139">In the Alert boundary maximum field, enter '4'.</span></span>
    * <span data-ttu-id="93f13-140">Se usa para realizar el seguimiento del importe máximo de kanbans completos que deben encontrarse en el destino.</span><span class="sxs-lookup"><span data-stu-id="93f13-140">Used to keep track of the maximum amount of full kanbans that should be at the destination.</span></span> <span data-ttu-id="93f13-141">Por ejemplo, esto se usa en la visión general de la cantidad kanban.</span><span class="sxs-lookup"><span data-stu-id="93f13-141">For example, this is used on the kanban quantity overview.</span></span>  
9. <span data-ttu-id="93f13-142">En el campo Cantidad de planificación automática, especifique "1".</span><span class="sxs-lookup"><span data-stu-id="93f13-142">In the Automatic planning quantity field, enter '1'.</span></span>
    * <span data-ttu-id="93f13-143">La configuración de este valor en 1 significa que cada kanban se planeará automáticamente.</span><span class="sxs-lookup"><span data-stu-id="93f13-143">Setting this to 1 means that every kanban will be automatically planned.</span></span>   <span data-ttu-id="93f13-144">Si especificamos 3, los kanbans no se planificarán hasta que 3 kanbans vacíos estén listos para planificación.</span><span class="sxs-lookup"><span data-stu-id="93f13-144">If we entered 3, the kanbans would not be planned until 3 empty kanbans are ready for planning.</span></span> <span data-ttu-id="93f13-145">Esto resulta útil para agrupar el trabajo y evitar una configuración excesiva.</span><span class="sxs-lookup"><span data-stu-id="93f13-145">This is useful for grouping work and avoiding too much setup.</span></span>  

## <a name="create-kanbans"></a><span data-ttu-id="93f13-146">Crear kanbans</span><span class="sxs-lookup"><span data-stu-id="93f13-146">Create Kanbans</span></span>
1. <span data-ttu-id="93f13-147">Expanda la sección Kanbans.</span><span class="sxs-lookup"><span data-stu-id="93f13-147">Expand the Kanbans section.</span></span>
2. <span data-ttu-id="93f13-148">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="93f13-148">Click Save.</span></span>
    * <span data-ttu-id="93f13-149">La regla kanban se tiene que guardar para que se puedan crear los kanbans.</span><span class="sxs-lookup"><span data-stu-id="93f13-149">The kanban rule needs to be saved before kanbans can be created.</span></span>  
3. <span data-ttu-id="93f13-150">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="93f13-150">Click Add.</span></span>
    * <span data-ttu-id="93f13-151">Tenga en cuenta que no hay kanbans activos, debido a esto el 'Número de los nuevos kanbans' sugerido es 5.</span><span class="sxs-lookup"><span data-stu-id="93f13-151">Note that there are no active kanbans, due to this the suggested 'Number of new kanbans' are 5.</span></span> <span data-ttu-id="93f13-152">Esto es igual a “la cantidad kanban fija”.</span><span class="sxs-lookup"><span data-stu-id="93f13-152">This is equal to the 'Fixed kanban quantity'.</span></span>  
4. <span data-ttu-id="93f13-153">Haga clic en Crear.</span><span class="sxs-lookup"><span data-stu-id="93f13-153">Click Create.</span></span>
    * <span data-ttu-id="93f13-154">Esto creará 5 kanbans.</span><span class="sxs-lookup"><span data-stu-id="93f13-154">This will create 5 kanbans.</span></span>  
    * <span data-ttu-id="93f13-155">Tenga en cuenta que se crearon 5 kanbans, para 10 cada uno, para esta regla kanban de fabricación.</span><span class="sxs-lookup"><span data-stu-id="93f13-155">Note that 5 kanbans, for 10 each, was created for this manufacturing kanban rule.</span></span> <span data-ttu-id="93f13-156">Este es el último paso de este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="93f13-156">This is the last step in this procedure.</span></span>  


