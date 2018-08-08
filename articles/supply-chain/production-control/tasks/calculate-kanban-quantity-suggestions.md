--- 
title: "Cálculo de sugerencias de cantidades kanban"
description: "Este procedimiento se centra en la optimización del tamaño y las cantidades kanban para una regla kanban calculando la cantidad kanban."
author: ChristianRytt
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
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 540dd32c5da5859ef5e69f55d6806eada90bc840
ms.contentlocale: es-es
ms.lasthandoff: 08/07/2018

---
# <a name="calculate-kanban-quantity-suggestions"></a><span data-ttu-id="a753b-103">Cálculo de sugerencias de cantidades kanban</span><span class="sxs-lookup"><span data-stu-id="a753b-103">Calculate kanban quantity suggestions</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="a753b-104">Este procedimiento se centra en la optimización del tamaño y las cantidades kanban para una regla kanban calculando la cantidad kanban.</span><span class="sxs-lookup"><span data-stu-id="a753b-104">This procedure focuses on optimizing the kanban size and quantities for a specific kanban rule by using the kanban quantity calculation.</span></span> <span data-ttu-id="a753b-105">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="a753b-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="a753b-106">Este procedimiento va destinado al administrador del flujo de valor.</span><span class="sxs-lookup"><span data-stu-id="a753b-106">This procedure is intended for the value stream manager.</span></span> <span data-ttu-id="a753b-107">Es indispensable haber completado el procedimiento Adición de una directiva de cálculo de cantidad kanban a una regla kanban.</span><span class="sxs-lookup"><span data-stu-id="a753b-107">It is a prerequisite that you have completed the procedure Add a new kanban quantity calculation policy to a kanban rule.</span></span>


## <a name="create-a-kanban-quantity-calculation"></a><span data-ttu-id="a753b-108">Creación de un cálculo de cantidad kanban</span><span class="sxs-lookup"><span data-stu-id="a753b-108">Create a kanban quantity calculation</span></span>
1. <span data-ttu-id="a753b-109">Vaya a Control de producción > Tareas periódicas > Cálculo de cantidad kanban > Calcular cantidad kanban.</span><span class="sxs-lookup"><span data-stu-id="a753b-109">Go to Production control > Periodic tasks > Kanban quantity calculation > Calculate kanban quantity.</span></span>
2. <span data-ttu-id="a753b-110">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="a753b-110">Click New.</span></span>
3. <span data-ttu-id="a753b-111">En el campo Nombre, escriba "Speaker2016".</span><span class="sxs-lookup"><span data-stu-id="a753b-111">In the Name field, type 'Speaker2016'.</span></span>
4. <span data-ttu-id="a753b-112">En el campo Nombre, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="a753b-112">In the Name field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="a753b-113">Seleccione la directiva que ha creado en el procedimiento Adición de una directiva de cálculo de cantidad kanban a una regla kanban.</span><span class="sxs-lookup"><span data-stu-id="a753b-113">Select the policy that you have created in the procedure Add a new kanban quantity calculation policy to a kanban rule.</span></span> <span data-ttu-id="a753b-114">Por ejemplo, Speaker2016.</span><span class="sxs-lookup"><span data-stu-id="a753b-114">For example, Speaker2016.</span></span>  
5. <span data-ttu-id="a753b-115">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="a753b-115">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="a753b-116">En el campo Regla activa a partir de la fecha, defina la fecha y la hora en "2012-12-17T08:00:00".</span><span class="sxs-lookup"><span data-stu-id="a753b-116">In the Rule active as of date field, set the date and time to '2012-12-17T08:00:00'.</span></span>
    * <span data-ttu-id="a753b-117">Esta fecha se toma como base para determinar qué reglas kanban se incluyen en el cálculo de cantidad kanban.</span><span class="sxs-lookup"><span data-stu-id="a753b-117">This date serves as the basis for determining which fixed kanban rules are included in the kanban quantity calculation.</span></span>  
7. <span data-ttu-id="a753b-118">En el campo Fecha inicial del período de demanda satisfecha, defina la fecha y la hora en "2012-11-17T09:00:00".</span><span class="sxs-lookup"><span data-stu-id="a753b-118">In the Fulfilled demand period start date field, set the date and time to '2012-11-17T09:00:00'.</span></span>
    * <span data-ttu-id="a753b-119">La fecha a partir de la cual se incluyen las transacciones de demanda pasada para calcular la cantidad kanban.</span><span class="sxs-lookup"><span data-stu-id="a753b-119">The date from when past demand transactions are included to calculate the kanban quantity.</span></span>  
8. <span data-ttu-id="a753b-120">En el campo Fecha final del período de demanda satisfecha, defina la fecha y la hora en "2012-12-17T07:59:59".</span><span class="sxs-lookup"><span data-stu-id="a753b-120">In the Fulfilled demand period end date field, set the date and time to '2012-12-17T07:59:59'.</span></span>
    * <span data-ttu-id="a753b-121">La fecha hasta la cual se incluyen las transacciones de demanda pasada para calcular la cantidad kanban.</span><span class="sxs-lookup"><span data-stu-id="a753b-121">The date until when past demand transactions are included to calculate the kanban quantity.</span></span>  
9. <span data-ttu-id="a753b-122">En el campo Fecha inicial del período de demanda, defina la fecha y la hora en "2012-12-17T08:00:00".</span><span class="sxs-lookup"><span data-stu-id="a753b-122">In the Demand period start date field, set the date and time to '2012-12-17T08:00:00'.</span></span>
    * <span data-ttu-id="a753b-123">La fecha a partir de la cual se incluyen las transacciones de demanda actual para calcular la cantidad kanban.</span><span class="sxs-lookup"><span data-stu-id="a753b-123">The date from when current demand transactions are included to calculate the kanban quantity.</span></span>  
10. <span data-ttu-id="a753b-124">En el campo Fecha final del período de demanda, defina la fecha y la hora en "2013-01-16T07:59:59".</span><span class="sxs-lookup"><span data-stu-id="a753b-124">In the Demand period end date field, set the date and time to '2013-01-16T07:59:59'.</span></span>
    * <span data-ttu-id="a753b-125">La fecha hasta la cual se incluyen las transacciones de demanda actual para calcular la cantidad kanban.</span><span class="sxs-lookup"><span data-stu-id="a753b-125">The date until when current demand transactions are included to calculate the kanban quantity.</span></span>  

## <a name="generate-kanban-quantity-proposal"></a><span data-ttu-id="a753b-126">Generación de la propuesta de cantidad kanban</span><span class="sxs-lookup"><span data-stu-id="a753b-126">Generate kanban quantity proposal</span></span>
1. <span data-ttu-id="a753b-127">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="a753b-127">Click Save.</span></span>
2. <span data-ttu-id="a753b-128">Haga clic en Generar.</span><span class="sxs-lookup"><span data-stu-id="a753b-128">Click Generate.</span></span>
    * <span data-ttu-id="a753b-129">Esto genera una línea de propuesta de cantidad kanban para la regla kanban 000020.</span><span class="sxs-lookup"><span data-stu-id="a753b-129">This generates a kanban quantity proposal line for the kanban rule 000020.</span></span>  

## <a name="run-kanban-quantity-calculation"></a><span data-ttu-id="a753b-130">Ejecución del cálculo de cantidad kanban</span><span class="sxs-lookup"><span data-stu-id="a753b-130">Run kanban quantity calculation</span></span>
1. <span data-ttu-id="a753b-131">Haga clic en Calcular.</span><span class="sxs-lookup"><span data-stu-id="a753b-131">Click Calculate.</span></span>
    * <span data-ttu-id="a753b-132">Esto calcula la propuesta de cantidad kanban.</span><span class="sxs-lookup"><span data-stu-id="a753b-132">This calculates the kanban quantity proposal.</span></span>  
2. <span data-ttu-id="a753b-133">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="a753b-133">Click OK.</span></span>
3. <span data-ttu-id="a753b-134">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="a753b-134">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="a753b-135">Observe cómo la cantidad de kanban sugerida es 2.</span><span class="sxs-lookup"><span data-stu-id="a753b-135">Notice the suggested kanban quantity is 2.</span></span>  

## <a name="change-product-quantity-and-calculate-again"></a><span data-ttu-id="a753b-136">Cambio de la cantidad de producto y nuevo cálculo</span><span class="sxs-lookup"><span data-stu-id="a753b-136">Change product quantity and calculate again</span></span>
1. <span data-ttu-id="a753b-137">Defina la cantidad del producto en "5".</span><span class="sxs-lookup"><span data-stu-id="a753b-137">Set Product quantity to '5'.</span></span>
2. <span data-ttu-id="a753b-138">Haga clic en Calcular.</span><span class="sxs-lookup"><span data-stu-id="a753b-138">Click Calculate.</span></span>
3. <span data-ttu-id="a753b-139">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="a753b-139">Click OK.</span></span>
    * <span data-ttu-id="a753b-140">Observe que con una cantidad kanban de 5, la sugerencia cambia a una cantidad kanban de 4.</span><span class="sxs-lookup"><span data-stu-id="a753b-140">Notice that with a kanban quantity of 5, the suggestion is changed to a kanban quantity of 4.</span></span>  
    * <span data-ttu-id="a753b-141">Esto es así por el hecho de que con una cantidad de producto inferior, se necesitan más kanbans para satisfacer la demanda.</span><span class="sxs-lookup"><span data-stu-id="a753b-141">This is caused by the fact that with a lower product quantity, we need more kanbans to fulfill the demand.</span></span>  

## <a name="update-kanban-rule"></a><span data-ttu-id="a753b-142">Actualización de la regla kanban</span><span class="sxs-lookup"><span data-stu-id="a753b-142">Update kanban rule</span></span>
1. <span data-ttu-id="a753b-143">En el campo Fecha de vigencia de regla, especifique una fecha y una hora.</span><span class="sxs-lookup"><span data-stu-id="a753b-143">In the Rule effective date field, enter a date and time.</span></span>
    * <span data-ttu-id="a753b-144">Defina Regla activa a partir de la fecha en una fecha futura.</span><span class="sxs-lookup"><span data-stu-id="a753b-144">Set the 'Rule active as of date' to a date in the future.</span></span> <span data-ttu-id="a753b-145">Por ejemplo, hoy + un año.</span><span class="sxs-lookup"><span data-stu-id="a753b-145">For example, today + one year.</span></span>  
2. <span data-ttu-id="a753b-146">Haga clic en Actualizar.</span><span class="sxs-lookup"><span data-stu-id="a753b-146">Click Update.</span></span>
3. <span data-ttu-id="a753b-147">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="a753b-147">Click OK.</span></span>
4. <span data-ttu-id="a753b-148">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="a753b-148">Close the page.</span></span>

## <a name="validate-change-on-kanban-rule"></a><span data-ttu-id="a753b-149">Validación de cambios en reglas kanban</span><span class="sxs-lookup"><span data-stu-id="a753b-149">Validate change on kanban rule</span></span>
1. <span data-ttu-id="a753b-150">Vaya a Gestión de información de productos > Producción ajustada > Reglas kanban.</span><span class="sxs-lookup"><span data-stu-id="a753b-150">Go to Product information management > Lean manufacturing > Kanban rules.</span></span>
2. <span data-ttu-id="a753b-151">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="a753b-151">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="a753b-152">Seleccione la regla kanban que se creó en la subtarea anterior.</span><span class="sxs-lookup"><span data-stu-id="a753b-152">Select the kanban rule that was created in the previous sub-task.</span></span> <span data-ttu-id="a753b-153">Esta debe ser la primera regla kanban en la lista ordenada por número.</span><span class="sxs-lookup"><span data-stu-id="a753b-153">This should be the first kanban rule in the list sorted by number.</span></span>  
3. <span data-ttu-id="a753b-154">Expanda la sección Detalles.</span><span class="sxs-lookup"><span data-stu-id="a753b-154">Toggle the expansion of the Details section.</span></span>
    * <span data-ttu-id="a753b-155">Tenga en cuenta la fecha de vigencia, que significa que esta regla no estará activa hasta esta fecha.</span><span class="sxs-lookup"><span data-stu-id="a753b-155">Notice the effective date, which means that this rule is not activated until this date.</span></span>  
4. <span data-ttu-id="a753b-156">Expanda la sección Cantidades.</span><span class="sxs-lookup"><span data-stu-id="a753b-156">Toggle the expansion of the Quantities section.</span></span>
    * <span data-ttu-id="a753b-157">Observe que esta es la cantidad predeterminada especificada en el cálculo de la cantidad kanban.</span><span class="sxs-lookup"><span data-stu-id="a753b-157">Notice this is the default quantity that you entered on the kanban quantity calculation.</span></span>  
    * <span data-ttu-id="a753b-158">Observe que esta es la cantidad kanban fija de 4 proveniente del cálculo de cantidad kanban.</span><span class="sxs-lookup"><span data-stu-id="a753b-158">Notice this is the fixed kanban quantity of 4 from the kanban quantity calculation.</span></span>  
5. <span data-ttu-id="a753b-159">Haga clic en la ficha del panel de lista.</span><span class="sxs-lookup"><span data-stu-id="a753b-159">Click the ListPanel tab.</span></span>


