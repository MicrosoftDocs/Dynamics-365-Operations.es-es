--- 
title: "Validar un flujo de producción y una versión"
description: "Este procedimiento muestra cómo crear un nuevo flujo de producción y una primera versión de lean manufacturing."
author: ChristianRytt
manager: AnnBe
ms.date: 02/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: bc563eac09fffc191a34041da7c91e7a3ffbd2e1
ms.contentlocale: es-es
ms.lasthandoff: 05/08/2018

---
# <a name="validate-a-production-flow-and-version"></a><span data-ttu-id="62b13-103">Validar un flujo de producción y una versión</span><span class="sxs-lookup"><span data-stu-id="62b13-103">Validate a production flow and version</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="62b13-104">Este procedimiento muestra cómo crear un nuevo flujo de producción y una primera versión de lean manufacturing.</span><span class="sxs-lookup"><span data-stu-id="62b13-104">This procedure shows how to create a new production flow and a first version for lean manufacturing.</span></span> <span data-ttu-id="62b13-105">Requisitos previos: deben definirse los parámetros de producción de lean manufacturing y las unidades de medida para la clase de tiempo.</span><span class="sxs-lookup"><span data-stu-id="62b13-105">Prerequisites: The production parameters for Lean manufacturing and the units of measure for class time must be defined.</span></span> <span data-ttu-id="62b13-106">Debe definir un flujo de valor y un grupo de producción.</span><span class="sxs-lookup"><span data-stu-id="62b13-106">You need to define a Value stream and a Production group.</span></span> <span data-ttu-id="62b13-107">Consulte las notas del producto sobre lean manufacturing para familiarizarse con los conceptos de flujos de producción y actividades.</span><span class="sxs-lookup"><span data-stu-id="62b13-107">Refer to the white papers on Lean manufacturing to familiarize yourself with the concepts of production flows and activities.</span></span> <span data-ttu-id="62b13-108">Este procedimiento hace referencia a la entidad jurídica USMF en los datos de demostración.</span><span class="sxs-lookup"><span data-stu-id="62b13-108">This procedure refers to the legal entity USMF in demo data.</span></span> <span data-ttu-id="62b13-109">Sin embargo, si se supone que se configura la entidad jurídica para lean manufacturing, se pueden usar otras entidades jurídicas.</span><span class="sxs-lookup"><span data-stu-id="62b13-109">However, assuming that the legal entity is configured for Lean manufacturing, other legal entities can be used.</span></span>


## <a name="create-a-production-flow"></a><span data-ttu-id="62b13-110">Crear flujos de producción</span><span class="sxs-lookup"><span data-stu-id="62b13-110">Create a production flow</span></span>
1. <span data-ttu-id="62b13-111">Vaya a Control de producción > Configuración > Flujo de producción lean > Flujos de producción.</span><span class="sxs-lookup"><span data-stu-id="62b13-111">Go to Production control > Setup > Lean production flow > Production flows.</span></span>
2. <span data-ttu-id="62b13-112">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="62b13-112">Click New.</span></span>
3. <span data-ttu-id="62b13-113">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="62b13-113">In the Name field, type a value.</span></span>
4. <span data-ttu-id="62b13-114">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="62b13-114">In the Description field, type a value.</span></span>
5. <span data-ttu-id="62b13-115">En el campo Nombre, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="62b13-115">In the Name field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="62b13-116">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="62b13-116">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="62b13-117">Un flujo de valor es una unidad operativa que abarca todas las actividades y los flujos del flujo de valor.</span><span class="sxs-lookup"><span data-stu-id="62b13-117">A value stream is an operating unit that spans over all activities and flows of the value stream.</span></span>   <span data-ttu-id="62b13-118">En esta fase, las unidades operativas se limitan a una entidad jurídica y no tienen más funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="62b13-118">At this stage, operating units are limited to a legal entity and have no further functionality.</span></span>  
7. <span data-ttu-id="62b13-119">En el campo Grupo de producción, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="62b13-119">In the Production group field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="62b13-120">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="62b13-120">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="62b13-121">Los grupos de producción permiten definir las cuentas de trabajo en curso, material y manos de obra para un proceso de producción.</span><span class="sxs-lookup"><span data-stu-id="62b13-121">Production groups allow the definition of material, labor, and WIP accounts for a production process.</span></span> <span data-ttu-id="62b13-122">Para asociar el contexto de contabilidad a un flujo de producción, debe seleccionarse un grupo de producción.</span><span class="sxs-lookup"><span data-stu-id="62b13-122">To associate the accounting context to a production flow, a production group must be selected.</span></span>  
9. <span data-ttu-id="62b13-123">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="62b13-123">Click Save.</span></span>

## <a name="create-a-production-flow-version"></a><span data-ttu-id="62b13-124">Crear una versión de flujo de producción</span><span class="sxs-lookup"><span data-stu-id="62b13-124">Create a production flow version</span></span>
1. <span data-ttu-id="62b13-125">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="62b13-125">Click Add.</span></span>
2. <span data-ttu-id="62b13-126">En el campo Fecha de vencimiento, especifique una fecha y una hora.</span><span class="sxs-lookup"><span data-stu-id="62b13-126">In the Expiration date field, enter a date and time.</span></span>
    * <span data-ttu-id="62b13-127">Puede actualizar la fecha de vencimiento de la versión en cualquier momento dado, incluso para las versiones activas.</span><span class="sxs-lookup"><span data-stu-id="62b13-127">You can update the Expiration date of the version at any given time, even for active versions.</span></span> <span data-ttu-id="62b13-128">Use el vencimiento de la versión para planear la retirada de una versión.</span><span class="sxs-lookup"><span data-stu-id="62b13-128">Use the expiration of the version to plan for a phase out of a version.</span></span>  
3. <span data-ttu-id="62b13-129">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="62b13-129">Click OK.</span></span>
4. <span data-ttu-id="62b13-130">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="62b13-130">In the list, mark the selected row.</span></span>
5. <span data-ttu-id="62b13-131">En el campo Unidad, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="62b13-131">In the Unit field, type a value.</span></span>
6. <span data-ttu-id="62b13-132">Seleccione la unidad de producción.</span><span class="sxs-lookup"><span data-stu-id="62b13-132">Select the Takt unit.</span></span>
7. <span data-ttu-id="62b13-133">En campo Ritmo de producción promedio, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="62b13-133">In the Average takt time field, enter a number.</span></span>
    * <span data-ttu-id="62b13-134">Para el control de producción de la versión de flujo de producción, defina un ritmo de producción promedio objetivo.</span><span class="sxs-lookup"><span data-stu-id="62b13-134">For the takt control of the production flow version, define a targeted average takt time.</span></span>   <span data-ttu-id="62b13-135">El ritmo se define como cantidad por período de tiempo.</span><span class="sxs-lookup"><span data-stu-id="62b13-135">The takt is defined as quantity  per time period.</span></span>  <span data-ttu-id="62b13-136">En el ejemplo determinado, el ritmo de producción es 0,2 horas por 10 piezas.</span><span class="sxs-lookup"><span data-stu-id="62b13-136">In the given example, the takt time is 0.2 hours per 10 pieces.</span></span> <span data-ttu-id="62b13-137">Por un horario de trabajo de 8 horas, esto se corresponde con una capacidad de rendimiento diario de 400 piezas.</span><span class="sxs-lookup"><span data-stu-id="62b13-137">For a working time of 8 hours, this corresponds to a daily throughput capacity of 400 pieces.</span></span>  
8. <span data-ttu-id="62b13-138">En el campo Cantidad por ciclo, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="62b13-138">In the Quantity per cycle field, enter a number.</span></span>
9. <span data-ttu-id="62b13-139">Expanda o contraiga la sección Detalles de versión.</span><span class="sxs-lookup"><span data-stu-id="62b13-139">Expand or collapse the Version details section.</span></span>
10. <span data-ttu-id="62b13-140">En campo Ritmo de producción mínimo, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="62b13-140">In the Minimum takt time field, enter a number.</span></span>
    * <span data-ttu-id="62b13-141">El ritmo de producción mínimo debe ser inferior o igual al ritmo de producción promedio.</span><span class="sxs-lookup"><span data-stu-id="62b13-141">The minimum takt time must be less than or equal to the average takt time.</span></span>  
11. <span data-ttu-id="62b13-142">En campo Ritmo de producción máximo, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="62b13-142">In the Maximum takt time field, enter a number.</span></span>
    * <span data-ttu-id="62b13-143">El ritmo de producción máximo debe ser superior o igual al ritmo de producción promedio.</span><span class="sxs-lookup"><span data-stu-id="62b13-143">The maximum takt time must be higher than or equal to the Average takt time.</span></span>  
12. <span data-ttu-id="62b13-144">Escribir un número de días en el Período para tiempo de ciclo real</span><span class="sxs-lookup"><span data-stu-id="62b13-144">Enter a number of days in the Period for actual cycle time</span></span>
    * <span data-ttu-id="62b13-145">El período para el tiempo de ciclo real es el número de días que los trabajos se agregan a partir del minuto real y hacia atrás, para calcular el tiempo de ciclo real.</span><span class="sxs-lookup"><span data-stu-id="62b13-145">The period for actual cycle time is the number of days that jobs are aggregated from the actual minute backwards to calculate the actual cycle time.</span></span> <span data-ttu-id="62b13-146">El valor se puede cambiar en cualquier momento y solo se usa para calcular los tiempos de ciclo reales.</span><span class="sxs-lookup"><span data-stu-id="62b13-146">The value can be changed at any time and is only used for the calculation of the actual cycle times.</span></span>  
13. <span data-ttu-id="62b13-147">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="62b13-147">Click Save.</span></span>


