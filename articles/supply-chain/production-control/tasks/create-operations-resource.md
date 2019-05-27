---
title: Crear un recurso de operaciones
description: Un recurso de operaciones realiza las actividades de un proyecto o de un proceso de producción.
author: sorenva
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WrkCtrTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f9d8f13e29ea813eb9721ddca795b67837e2aa5e
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1558158"
---
# <a name="create-an-operations-resource"></a><span data-ttu-id="70640-103">Crear un recurso de operaciones</span><span class="sxs-lookup"><span data-stu-id="70640-103">Create an operations resource</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="70640-104">Un recurso de operaciones realiza las actividades de un proyecto o de un proceso de producción.</span><span class="sxs-lookup"><span data-stu-id="70640-104">An operations resource performs the activities of a project or a production process.</span></span> <span data-ttu-id="70640-105">En este procedimiento se muestra cómo definir un recurso de operaciones.</span><span class="sxs-lookup"><span data-stu-id="70640-105">This procedures shows you how to define an operations resource.</span></span> <span data-ttu-id="70640-106">Puede revisar este procedimiento con los datos de prueba de la empresa USMF o utilizar sus propios datos.</span><span class="sxs-lookup"><span data-stu-id="70640-106">You can walk through this procedure in demo data company USMF, or using your own data.</span></span>

1. <span data-ttu-id="70640-107">Vaya a Recursos.</span><span class="sxs-lookup"><span data-stu-id="70640-107">Go to Resources.</span></span>
2. <span data-ttu-id="70640-108">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="70640-108">Click New.</span></span>
3. <span data-ttu-id="70640-109">En el campo Recurso, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="70640-109">In the Resource field, type a value.</span></span>
4. <span data-ttu-id="70640-110">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="70640-110">In the Description field, type a value.</span></span>

## <a name="define-capacity-and-consumption-parameters"></a><span data-ttu-id="70640-111">Definir los parámetros de programación y de consumo</span><span class="sxs-lookup"><span data-stu-id="70640-111">Define capacity and consumption parameters</span></span>
1. <span data-ttu-id="70640-112">Expanda la sección Operación.</span><span class="sxs-lookup"><span data-stu-id="70640-112">Expand the Operation section.</span></span>
2. <span data-ttu-id="70640-113">En el campo Porcentaje de residuos, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="70640-113">In the Scrap percentage field, enter a number.</span></span>
3. <span data-ttu-id="70640-114">En el campo Categoría de configuración, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="70640-114">In the Setup category field, enter or select a value.</span></span>
    * <span data-ttu-id="70640-115">Especifique la categoría de coste que define cómo contabilizar el coste de la configuración.</span><span class="sxs-lookup"><span data-stu-id="70640-115">Specify the cost category that defines how to account for the cost of setup.</span></span>  
4. <span data-ttu-id="70640-116">En el campo Tiempo de ejecución, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="70640-116">In the Run time category field, enter or select a value.</span></span>
    * <span data-ttu-id="70640-117">Especifique la categoría de coste que define cómo contabilizar el coste del tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="70640-117">Specify the cost category that defines how to account for the cost of run time.</span></span>  
5. <span data-ttu-id="70640-118">En el campo Categoría por unidad/pieza, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="70640-118">In the Quantity category field, enter or select a value.</span></span>
    * <span data-ttu-id="70640-119">Especifique la categoría de coste que define cómo contabilizar el coste de recursos a partir de la cantidad de salida.</span><span class="sxs-lookup"><span data-stu-id="70640-119">Specify the cost category that defines how to account for the resource cost based on the output quantity.</span></span>  
6. <span data-ttu-id="70640-120">En el campo Unidad de capacidad, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="70640-120">In the Capacity unit field, select an option.</span></span>
    * <span data-ttu-id="70640-121">Especifique la unidad en la que desea expresar la capacidad del recurso de operaciones.</span><span class="sxs-lookup"><span data-stu-id="70640-121">Specify the unit in which to express the capacity of the operations resource.</span></span>  
7. <span data-ttu-id="70640-122">En el campo Capacidad, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="70640-122">In the Capacity field, enter a number.</span></span>
8. <span data-ttu-id="70640-123">En el campo Porcentaje de eficacia, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="70640-123">In the Efficiency percentage field, enter a number.</span></span>
    * <span data-ttu-id="70640-124">Especifique la eficacia que espera del recurso de operaciones.</span><span class="sxs-lookup"><span data-stu-id="70640-124">Specify the efficiency that you expect from the operations resource.</span></span> <span data-ttu-id="70640-125">El porcentaje de eficacia ajusta el rendimiento del recurso de operaciones y afecta al tiempo reservado para el recurso.</span><span class="sxs-lookup"><span data-stu-id="70640-125">The efficiency percentage adjusts the throughput of the operations resource and affects the time that is reserved for the resource.</span></span>  
9. <span data-ttu-id="70640-126">En el campo Porcentaje de programación de operaciones, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="70640-126">In the Operations scheduling percentage field, enter a number.</span></span>
    * <span data-ttu-id="70640-127">Especifique el porcentaje máximo de capacidad del recurso de operaciones que desea utilizar en la programación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="70640-127">Specify the maximum percentage of capacity of the operations resource that you want to use in operations scheduling.</span></span>  
10. <span data-ttu-id="70640-128">Seleccione Sí en el campo Capacidad limitada.</span><span class="sxs-lookup"><span data-stu-id="70640-128">Select Yes in the Finite capacity field.</span></span>
    * <span data-ttu-id="70640-129">Establezca esta opción en Sí si el recurso de operaciones debe programarse en función de la capacidad real disponible y si deben tenerse en cuenta las reservas de capacidad existentes.</span><span class="sxs-lookup"><span data-stu-id="70640-129">Set this option to Yes if the operations resource should be scheduled based on the actual capacity that is available, and if existing capacity reservations should be considered.</span></span> <span data-ttu-id="70640-130">Si esta opción se establece en No, se supone que el recurso de operaciones tiene capacidad infinita y el recurso puede estar reservado en exceso.</span><span class="sxs-lookup"><span data-stu-id="70640-130">If this option is set to No, the operations resource is assumed to have infinite capacity, and the resource might be overbooked.</span></span>  
11. <span data-ttu-id="70640-131">Seleccione Sí en el campo Recurso de cuello de botella.</span><span class="sxs-lookup"><span data-stu-id="70640-131">Select Yes in the Bottleneck resource field.</span></span>

## <a name="define-working-times"></a><span data-ttu-id="70640-132">Definir los horarios de trabajo</span><span class="sxs-lookup"><span data-stu-id="70640-132">Define working times</span></span>
1. <span data-ttu-id="70640-133">Expanda la sección Calendarios.</span><span class="sxs-lookup"><span data-stu-id="70640-133">Expand the Calendars section.</span></span>
2. <span data-ttu-id="70640-134">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="70640-134">Click Add.</span></span>
3. <span data-ttu-id="70640-135">En el campo Calendario, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="70640-135">In the Calendar field, enter or select a value.</span></span>
    * <span data-ttu-id="70640-136">Especifique el calendario laboral que define la capacidad (en horas) del recurso.</span><span class="sxs-lookup"><span data-stu-id="70640-136">Specify the working time calendar that defines the capacity (in hours) of the resource.</span></span>  
4. <span data-ttu-id="70640-137">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="70640-137">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="70640-138">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="70640-138">In the list, click the link in the selected row.</span></span>

## <a name="define-resource-capabilities"></a><span data-ttu-id="70640-139">Definir capacidades de recursos</span><span class="sxs-lookup"><span data-stu-id="70640-139">Define resource capabilities</span></span>
1. <span data-ttu-id="70640-140">Expanda la sección Capacidades.</span><span class="sxs-lookup"><span data-stu-id="70640-140">Expand the Capabilities section.</span></span>
2. <span data-ttu-id="70640-141">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="70640-141">Click Add.</span></span>
    * <span data-ttu-id="70640-142">Una capacidad es la posibilidad de que un recurso de operaciones realice una actividad concreta.</span><span class="sxs-lookup"><span data-stu-id="70640-142">A capability is the ability of an operations resource to perform a particular activity.</span></span> <span data-ttu-id="70640-143">El motor de programación asigna los recursos emparejando los requisitos de recurso de cada actividad con las capacidades de recursos de operaciones disponibles.</span><span class="sxs-lookup"><span data-stu-id="70640-143">The scheduling engine allocates resources by matching the resource requirements of each activity to the capabilities of the available operations resources.</span></span>  
3. <span data-ttu-id="70640-144">En el campo Capacidad, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="70640-144">In the Capability field, enter or select a value.</span></span>
4. <span data-ttu-id="70640-145">En el campo Nivel, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="70640-145">In the Level field, enter a number.</span></span>
    * <span data-ttu-id="70640-146">Especifique el nivel de aptitud por el que el recurso procesa la capacidad.</span><span class="sxs-lookup"><span data-stu-id="70640-146">Specify the level of proficiency by which the resource processes the capability.</span></span>  
5. <span data-ttu-id="70640-147">En el campo Prioridad, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="70640-147">In the Priority field, enter a number.</span></span>
    * <span data-ttu-id="70640-148">Especifique la prioridad del recurso de operaciones con respecto a la capacidad.</span><span class="sxs-lookup"><span data-stu-id="70640-148">Specify the priority of the operations resource with respect to the capability.</span></span> <span data-ttu-id="70640-149">Al programar por prioridad, seleccione primero el recurso de operaciones con la máxima prioridad (el menor valor numérico).</span><span class="sxs-lookup"><span data-stu-id="70640-149">When scheduling by priority, the operations resource with the highest priority (lowest numeric value) is selected first.</span></span>  

## <a name="assign-resource-to-resource-group"></a><span data-ttu-id="70640-150">Asignar un recurso a un grupo de recursos</span><span class="sxs-lookup"><span data-stu-id="70640-150">Assign resource to resource group</span></span>
1. <span data-ttu-id="70640-151">Expanda la sección Grupos de recursos.</span><span class="sxs-lookup"><span data-stu-id="70640-151">Expand the Resource groups section.</span></span>
2. <span data-ttu-id="70640-152">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="70640-152">Click Add.</span></span>
    * <span data-ttu-id="70640-153">El grupo de recursos define el sitio, la unida de producción y el contexto de almacén para los recursos de operaciones.</span><span class="sxs-lookup"><span data-stu-id="70640-153">The resource group defines the site, production unit, and warehouse context for operations resources.</span></span> <span data-ttu-id="70640-154">El recurso de operaciones solo puede programarse cuando está asignado a un grupo de recursos y solo en el sitio en el que se encuentra el grupo de recursos.</span><span class="sxs-lookup"><span data-stu-id="70640-154">The operations resource can only be scheduled when assigned to a resource group, and only on the site where the resource group is located.</span></span>  
3. <span data-ttu-id="70640-155">En el campo Grupo de recursos, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="70640-155">In the Resource group field, enter or select a value.</span></span>
4. <span data-ttu-id="70640-156">En el campo Ubicación de entrada, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="70640-156">In the Input location field, enter or select a value.</span></span>
    * <span data-ttu-id="70640-157">Especifique la ubicación de almacén cuyos materiales utiliza el recurso de operaciones.</span><span class="sxs-lookup"><span data-stu-id="70640-157">Specify the warehouse location from where the operations resource is consuming materials.</span></span>  

