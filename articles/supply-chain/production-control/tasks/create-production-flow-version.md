---
title: Crear una versión de flujo de producción
description: Este procedimiento se centra en crear una nueva versión de flujo de producción.
author: cvocph
manager: tfehr
ms.date: 11/03/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d513e6898827de9a3fb1ed59006b817fb9006019
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4436569"
---
# <a name="create-a-production-flow-version"></a><span data-ttu-id="990ea-103">Crear una versión de flujo de producción</span><span class="sxs-lookup"><span data-stu-id="990ea-103">Create a production flow version</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="990ea-104">Este procedimiento se centra en crear una nueva versión de flujo de producción.</span><span class="sxs-lookup"><span data-stu-id="990ea-104">This procedure focuses on creating a new production flow version.</span></span> <span data-ttu-id="990ea-105">Para este procedimiento, deben definirse los parámetros de producción de lean manufacturing y las unidades de medida para la clase de tiempo.</span><span class="sxs-lookup"><span data-stu-id="990ea-105">For this procedure, the production parameters for lean manufacturing and the units of measurement for class time must be defined.</span></span> <span data-ttu-id="990ea-106">Debe definir también un flujo de valor y un grupo de producción.</span><span class="sxs-lookup"><span data-stu-id="990ea-106">You also need to define a value stream and a production group.</span></span> <span data-ttu-id="990ea-107">Para obtener más información acerca de los flujos de producción y las actividades de lean manufacturing (producción ajustada), consulte la documentación al respecto de Microsoft Dynamics AX.</span><span class="sxs-lookup"><span data-stu-id="990ea-107">To learn more about production flows and activities in lean manufacturing, see the white papers on Lean manufacturing for Microsoft Dynamics AX.</span></span> <span data-ttu-id="990ea-108">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="990ea-108">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-a-production-flow"></a><span data-ttu-id="990ea-109">Crear flujos de producción</span><span class="sxs-lookup"><span data-stu-id="990ea-109">Create a production flow</span></span>
1. <span data-ttu-id="990ea-110">Vaya a Control de producción > Configuración > Flujo de producción lean > Flujos de producción.</span><span class="sxs-lookup"><span data-stu-id="990ea-110">Go to Production control > Setup > Lean production flow > Production flows.</span></span>
2. <span data-ttu-id="990ea-111">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="990ea-111">Click New.</span></span>
3. <span data-ttu-id="990ea-112">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="990ea-112">In the Name field, type a value.</span></span>
4. <span data-ttu-id="990ea-113">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="990ea-113">In the Description field, type a value.</span></span>
5. <span data-ttu-id="990ea-114">En el campo Nombre, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="990ea-114">In the Name field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="990ea-115">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="990ea-115">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="990ea-116">Seleccione una unidad operativa de tipo Flujo de valor.</span><span class="sxs-lookup"><span data-stu-id="990ea-116">Select an operating unit of type value stream.</span></span> <span data-ttu-id="990ea-117">Un flujo de valor es una unidad operativa que abarca todas las actividades y los flujos del flujo de valor.</span><span class="sxs-lookup"><span data-stu-id="990ea-117">A value stream is an operating unit that spans all activities and flows of the value stream.</span></span> <span data-ttu-id="990ea-118">En esta fase, las unidades operativas se limitan a una entidad jurídica y no tienen más funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="990ea-118">At this stage, operating units are limited to a legal entity and have no further functionality.</span></span>  
7. <span data-ttu-id="990ea-119">En el campo Grupo de producción, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="990ea-119">In the Production group field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="990ea-120">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="990ea-120">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="990ea-121">Seleccione un grupo de producción para el flujo de producción.</span><span class="sxs-lookup"><span data-stu-id="990ea-121">Select a production group for the production flow.</span></span> <span data-ttu-id="990ea-122">Los grupos de producción permiten definir las cuentas de trabajo en curso, material y manos de obra para un proceso de producción.</span><span class="sxs-lookup"><span data-stu-id="990ea-122">Production groups allow the definition of material, labor, and WIP accounts for a production process.</span></span> <span data-ttu-id="990ea-123">Para asociar el contexto de contabilidad a un flujo de producción, debe seleccionarse un grupo de producción.</span><span class="sxs-lookup"><span data-stu-id="990ea-123">To associate the accounting context to a production flow, a production group must be selected.</span></span>  
9. <span data-ttu-id="990ea-124">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="990ea-124">Click Save.</span></span>

## <a name="create-a-production-flow-version"></a><span data-ttu-id="990ea-125">Crear una versión de flujo de producción</span><span class="sxs-lookup"><span data-stu-id="990ea-125">Create a production flow version</span></span>
1. <span data-ttu-id="990ea-126">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="990ea-126">Click Add.</span></span>
2. <span data-ttu-id="990ea-127">En el campo Fecha de vencimiento, especifique una fecha y una hora.</span><span class="sxs-lookup"><span data-stu-id="990ea-127">In the Expiration date field, enter a date and time.</span></span>
    * <span data-ttu-id="990ea-128">Si procede, defina una fecha de vencimiento para la versión.</span><span class="sxs-lookup"><span data-stu-id="990ea-128">If required, define an Expiration date for the version.</span></span> <span data-ttu-id="990ea-129">Puede actualizarla en un cualquier momento, incluso las versiones activas.</span><span class="sxs-lookup"><span data-stu-id="990ea-129">You can update it at any given time, even for active versions.</span></span> <span data-ttu-id="990ea-130">Puede utilizarla para planificar la finalización de una versión.</span><span class="sxs-lookup"><span data-stu-id="990ea-130">You can use it to plan to phase out a version.</span></span>  
3. <span data-ttu-id="990ea-131">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="990ea-131">Click OK.</span></span>
4. <span data-ttu-id="990ea-132">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="990ea-132">In the list, mark the selected row.</span></span>
5. <span data-ttu-id="990ea-133">En el campo Unidad, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="990ea-133">In the Unit field, type a value.</span></span>
6. <span data-ttu-id="990ea-134">Resuelva los cambios en la unidad de producción.</span><span class="sxs-lookup"><span data-stu-id="990ea-134">ResolveChanges the Takt unit.</span></span>
7. <span data-ttu-id="990ea-135">En campo Ritmo de producción promedio, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="990ea-135">In the Average takt time field, enter a number.</span></span>
    * <span data-ttu-id="990ea-136">Defina el ritmo de producción promedio de la versión.</span><span class="sxs-lookup"><span data-stu-id="990ea-136">Define the Average takt time of the version.</span></span> <span data-ttu-id="990ea-137">Para el control de producción de la versión de flujo de producción, defina un ritmo de producción promedio objetivo.</span><span class="sxs-lookup"><span data-stu-id="990ea-137">For the takt control of the production flow version, define a targeted average takt time.</span></span> <span data-ttu-id="990ea-138">El ritmo de producción se define como cantidad por período de tiempo.</span><span class="sxs-lookup"><span data-stu-id="990ea-138">The takt is defined as quantity per time period.</span></span> <span data-ttu-id="990ea-139">En el ejemplo, el ritmo de producción es 0,2 horas por 10 piezas.</span><span class="sxs-lookup"><span data-stu-id="990ea-139">In the example, the takt time is 0.2 hours per 10 pieces.</span></span> <span data-ttu-id="990ea-140">Por un horario de trabajo de 8 horas, esto se corresponde con una capacidad de rendimiento diario de 400 piezas.</span><span class="sxs-lookup"><span data-stu-id="990ea-140">For a working time of 8 hours, this corresponds to a daily throughput capacity of 400 pieces.</span></span>  
8. <span data-ttu-id="990ea-141">En el campo Cantidad por ciclo, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="990ea-141">In the Quantity per cycle field, enter a number.</span></span>
    * <span data-ttu-id="990ea-142">Defina la cantidad por el ciclo relacionado con el ritmo de producción promedio.</span><span class="sxs-lookup"><span data-stu-id="990ea-142">Define the quantity per cycle related to the Average takt time.</span></span>  
9. <span data-ttu-id="990ea-143">Expanda la sección Detalles de versión.</span><span class="sxs-lookup"><span data-stu-id="990ea-143">Toggle the expansion of the Version details section.</span></span>
10. <span data-ttu-id="990ea-144">En campo Ritmo de producción mínimo, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="990ea-144">In the Minimum takt time field, enter a number.</span></span>
    * <span data-ttu-id="990ea-145">Defina el ritmo de producción mínimo.</span><span class="sxs-lookup"><span data-stu-id="990ea-145">Define the minimum takt time.</span></span> <span data-ttu-id="990ea-146">El ritmo de producción mínimo debe ser inferior o igual al ritmo de producción promedio.</span><span class="sxs-lookup"><span data-stu-id="990ea-146">The minimum takt time must be less than or equal to the average takt time.</span></span>  
11. <span data-ttu-id="990ea-147">En campo Ritmo de producción máximo, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="990ea-147">In the Maximum takt time field, enter a number.</span></span>
    * <span data-ttu-id="990ea-148">El ritmo de producción máximo debe ser superior o igual al ritmo de producción promedio.</span><span class="sxs-lookup"><span data-stu-id="990ea-148">The maximum takt time must be higher than or equal to the Average takt time.</span></span>  
12. <span data-ttu-id="990ea-149">Escriba un número en el campo Período para tiempo de ciclo real (días).</span><span class="sxs-lookup"><span data-stu-id="990ea-149">In the Period for actual cycle time (days) field, enter a number.</span></span>
    * <span data-ttu-id="990ea-150">Escriba un número de días en el período para tiempo de ciclo real.</span><span class="sxs-lookup"><span data-stu-id="990ea-150">Enter the number of days in the Period for actual cycle time.</span></span> <span data-ttu-id="990ea-151">El período para el tiempo de ciclo real es el número de días que los trabajos se agregan a partir del minuto real y hacia atrás, para calcular el tiempo de ciclo real.</span><span class="sxs-lookup"><span data-stu-id="990ea-151">The period for actual cycle time is the number of days that jobs are aggregated from the actual minute backwards to calculate the actual cycle time.</span></span> <span data-ttu-id="990ea-152">El valor se puede cambiar en cualquier momento y solo se usa para calcular los tiempos de ciclo reales.</span><span class="sxs-lookup"><span data-stu-id="990ea-152">The value can be changed at any time and is only used for the calculation of the actual cycle times.</span></span>  
13. <span data-ttu-id="990ea-153">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="990ea-153">Click Save.</span></span>

