---
title: Solucionar problemas de planificación maestra
description: Este tema describe cómo solucionar problemas que pueden surgir al trabajar con planificación maestra.
author: SmithaNataraj
ms.date: 11/04/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: smnatara
ms.search.validFrom: 2020-11-04
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 8e78634c0efb1c401297559ce40b2ca30519f3bf
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5809479"
---
# <a name="troubleshoot-master-planning"></a><span data-ttu-id="d256e-103">Solucionar problemas de planificación maestra</span><span class="sxs-lookup"><span data-stu-id="d256e-103">Troubleshoot master planning</span></span>

<span data-ttu-id="d256e-104">Este tema describe cómo solucionar problemas que pueden surgir al trabajar con planificación maestra.</span><span class="sxs-lookup"><span data-stu-id="d256e-104">This topic describes how to fix issues that you might encounter while you work with master planning.</span></span>

## <a name="bill-of-materials-explosion-behaves-differently-for-firmed-production-orders-and-for-estimated-production-orders-for-manually-created-work"></a><span data-ttu-id="d256e-105">La explosión de la lista de materiales se comporta de manera diferente para las órdenes de producción firmes y para las órdenes de producción estimadas para el trabajo creado manualmente.</span><span class="sxs-lookup"><span data-stu-id="d256e-105">Bill of materials explosion behaves differently for firmed production orders and for estimated production orders for manually created work.</span></span>

### <a name="issue-description"></a><span data-ttu-id="d256e-106">Descripción del problema</span><span class="sxs-lookup"><span data-stu-id="d256e-106">Issue description</span></span>

<span data-ttu-id="d256e-107">Cuando se confirma una orden de producción, los artículos no se desglosan cuando se desglosa la lista de materiales (BOM).</span><span class="sxs-lookup"><span data-stu-id="d256e-107">When a production order is firmed, the items aren't exploded when you explode the bill of materials (BOM).</span></span> <span data-ttu-id="d256e-108">Sin embargo, cuando crea manualmente una orden de trabajo y luego estima la orden de producción, los artículos se desglosan.</span><span class="sxs-lookup"><span data-stu-id="d256e-108">However, when you manually create a work order and then estimate the production order, the items are exploded.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="d256e-109">Solución del problema</span><span class="sxs-lookup"><span data-stu-id="d256e-109">Issue resolution</span></span>

<span data-ttu-id="d256e-110">El sistema funciona como se esperaba.</span><span class="sxs-lookup"><span data-stu-id="d256e-110">The system is working as expected.</span></span> <span data-ttu-id="d256e-111">La explosión que se produce cuando se confirma la orden de producción apuntará a la orden planificada, pero no parece que la orden planificada esté actualmente firme en este caso.</span><span class="sxs-lookup"><span data-stu-id="d256e-111">The explosion that occurs when the production order is firmed will point to the planned order, but it doesn't appear that the planned order is currently firmed in this case.</span></span> <span data-ttu-id="d256e-112">Sin embargo, si se ha estimado la orden de producción, la explosión se desencadena desde la orden de producción liberada donde no existe una orden previsional.</span><span class="sxs-lookup"><span data-stu-id="d256e-112">However, if the production order has been estimated, the explosion is triggered from the released production order where no planned order exists.</span></span>

## <a name="the-delay-value-isnt-updated-when-i-reschedule-a-planned-order"></a><span data-ttu-id="d256e-113">El valor de Retraso no se actualiza cuando reprogramo un pedido planificado.</span><span class="sxs-lookup"><span data-stu-id="d256e-113">The Delay value isn't updated when I reschedule a planned order.</span></span>

<span data-ttu-id="d256e-114">Para actualizar el retraso de los pedidos planificados, abra el cuadro de diálogo **Reprogramación** de la orden previsional.</span><span class="sxs-lookup"><span data-stu-id="d256e-114">To update the delay for planned orders, open the **Rescheduling** dialog box for the planned order.</span></span> <span data-ttu-id="d256e-115">En la ficha desplegable **Explosión**, asegúrese de que la opción **Realizar explosión después de reprogramación** está establecida en *Sí*.</span><span class="sxs-lookup"><span data-stu-id="d256e-115">On the **Explosion** FastTab, make sure that the **Perform explosion after rescheduling** option is set to *Yes*.</span></span>

## <a name="production-scheduling-doesnt-consider-the-safety-margins-that-are-set-on-the-item-coverage-for-pegged-supply"></a><span data-ttu-id="d256e-116">La programación de la producción no considera los márgenes de seguridad que se establecen en la cobertura del artículo para el suministro vinculado.</span><span class="sxs-lookup"><span data-stu-id="d256e-116">Production scheduling doesn't consider the safety margins that are set on the item coverage for pegged supply.</span></span>

### <a name="issue-description"></a><span data-ttu-id="d256e-117">Descripción del problema</span><span class="sxs-lookup"><span data-stu-id="d256e-117">Issue description</span></span>

<span data-ttu-id="d256e-118">La planificación maestra considera los márgenes de seguridad.</span><span class="sxs-lookup"><span data-stu-id="d256e-118">Master planning considers the safety margins.</span></span> <span data-ttu-id="d256e-119">Sin embargo, los márgenes de seguridad se ignoran cuando se programan órdenes de producción planificadas.</span><span class="sxs-lookup"><span data-stu-id="d256e-119">However, the safety margins are ignored when planned production orders are scheduled.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="d256e-120">Solución del problema</span><span class="sxs-lookup"><span data-stu-id="d256e-120">Issue resolution</span></span>

<span data-ttu-id="d256e-121">Los márgenes se consideran solo durante la planificación maestra, no durante la programación manual.</span><span class="sxs-lookup"><span data-stu-id="d256e-121">Margins are considered only during master planning, not during manual scheduling.</span></span> <span data-ttu-id="d256e-122">Los márgenes están diseñados para actuar como un amortiguador durante la fase de planificación, para dar algún "margen" para el proceso real.</span><span class="sxs-lookup"><span data-stu-id="d256e-122">Margins are designed to act as a buffer during the planning phase, to give some "margin" for the actual process.</span></span>

<span data-ttu-id="d256e-123">Para obtener el resultado deseado, puede eliminar el margen.</span><span class="sxs-lookup"><span data-stu-id="d256e-123">To get the desired result, you can remove the margin.</span></span> <span data-ttu-id="d256e-124">Luego, la ruta debe actualizarse para que incluya el tiempo deseado (por ejemplo, como tiempo de espera).</span><span class="sxs-lookup"><span data-stu-id="d256e-124">The route must then be updated so that it includes the desired time (for example, as queue time).</span></span> <span data-ttu-id="d256e-125">Tanto la planificación maestra como la programación manual deberían producir el mismo resultado.</span><span class="sxs-lookup"><span data-stu-id="d256e-125">Both master planning and manual scheduling should then produce the same result.</span></span>

## <a name="planned-orders-are-generated-even-though-we-have-items-in-stock-and-production-orders-already-exist-for-them"></a><span data-ttu-id="d256e-126">Los pedidos planificados se generan aunque tengamos artículos en stock y ya existan pedidos de producción para ellos.</span><span class="sxs-lookup"><span data-stu-id="d256e-126">Planned orders are generated even though we have items in stock and production orders already exist for them.</span></span>

<span data-ttu-id="d256e-127">Es posible que pueda solucionar este problema aumentando el valor **Días positivos** para los grupos relevantes en la página **Grupo de cobertura**.</span><span class="sxs-lookup"><span data-stu-id="d256e-127">You might be able to fix this issue by increasing the **Positive days** value for the relevant groups on the **Coverage group** page.</span></span> <span data-ttu-id="d256e-128">Este cambio hará que el sistema determine si el inventario disponible se puede utilizar para la demanda.</span><span class="sxs-lookup"><span data-stu-id="d256e-128">This change will cause the system to determine whether on-hand inventory can be used for the demand.</span></span> <span data-ttu-id="d256e-129">Entonces, no se generará un nuevo pedido planificado para los artículos que están en stock.</span><span class="sxs-lookup"><span data-stu-id="d256e-129">Then a new planned order won't be generated for the items that are in stock.</span></span>

## <a name="master-planning-doesnt-seem-to-respect-capacity-limitations-and-is-scheduling-more-than-the-available-capacity"></a><span data-ttu-id="d256e-130">La planificación maestra no parece respetar las limitaciones de capacidad y está programando más que la capacidad disponible.</span><span class="sxs-lookup"><span data-stu-id="d256e-130">Master planning doesn't seem to respect capacity limitations and is scheduling more than the available capacity.</span></span>

### <a name="issue-description"></a><span data-ttu-id="d256e-131">Descripción del problema</span><span class="sxs-lookup"><span data-stu-id="d256e-131">Issue description</span></span>

<span data-ttu-id="d256e-132">Cuando usa la programación de operaciones donde hay una capacidad finita, y donde la ruta especifica una combinación de requisitos para un grupo de recursos y recursos individuales, existe una pequeña posibilidad de overbooking debido a la forma en que el algoritmo valida los conflictos de capacidad.</span><span class="sxs-lookup"><span data-stu-id="d256e-132">When you use operation scheduling where there is finite capacity, and where the route specifies a mix of requirements for both a resource group and individual resources, there is a small chance of overbooking because of the way that the algorithm validates for capacity conflicts.</span></span> <span data-ttu-id="d256e-133">Esta sobreventa puede ocurrir cuando utiliza ayudantes para ejecutar la planificación maestra.</span><span class="sxs-lookup"><span data-stu-id="d256e-133">This overbooking can occur when you use helpers to run master planning.</span></span> <span data-ttu-id="d256e-134">Es más probable que ocurra si hay muchos trabajos que tienen un tiempo de ejecución relativamente corto.</span><span class="sxs-lookup"><span data-stu-id="d256e-134">It's most likely to occur if there are many jobs that have a relatively short runtime.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="d256e-135">Solución del problema</span><span class="sxs-lookup"><span data-stu-id="d256e-135">Issue resolution</span></span>

<span data-ttu-id="d256e-136">Si es esencial que no se produzca una sobreventa para la programación de operaciones, puede hacer que la programación sea parte de la planificación maestra de un solo subproceso activando la opción **Capacidad finita precisa para la programación de operaciones** en la página **Parámetros de planificación maestra**.</span><span class="sxs-lookup"><span data-stu-id="d256e-136">If it's essential that no overbooking occur for operation scheduling, you can make the scheduling part of master planning single-threaded by turning on the **Accurate finite capacity for Operation Scheduling** option on the **Master planning parameters** page.</span></span> <span data-ttu-id="d256e-137">Esta opción no está disponible de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="d256e-137">This option isn't available by default.</span></span> <span data-ttu-id="d256e-138">Debe agregarlo manualmente a la página mediante funciones de personalización.</span><span class="sxs-lookup"><span data-stu-id="d256e-138">You must manually add it to the page by using personalization features.</span></span> <span data-ttu-id="d256e-139">Cuando usa esta opción, la programación se ejecutará más lentamente debido a la falta de procesamiento paralelo.</span><span class="sxs-lookup"><span data-stu-id="d256e-139">When you use this option, scheduling will run more slowly because of the lack of parallel processing.</span></span>

## <a name="planned-orders-take-a-long-time-to-update"></a><span data-ttu-id="d256e-140">Los pedidos planificados tardan mucho en actualizarse.</span><span class="sxs-lookup"><span data-stu-id="d256e-140">Planned orders take a long time to update.</span></span>

### <a name="issue-description"></a><span data-ttu-id="d256e-141">Descripción del problema</span><span class="sxs-lookup"><span data-stu-id="d256e-141">Issue description</span></span>

<span data-ttu-id="d256e-142">Al actualizar la cantidad requerida y / o la fecha de entrega en un pedido planificado, generalmente se necesitan al menos 30 segundos por pedido para guardar la actualización.</span><span class="sxs-lookup"><span data-stu-id="d256e-142">When updating the requirement quantity and/or delivery date on a planned order, it typically takes at least 30 seconds per order to save the update.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="d256e-143">Solución del problema</span><span class="sxs-lookup"><span data-stu-id="d256e-143">Issue resolution</span></span>

<span data-ttu-id="d256e-144">Este es un problema conocido con el motor de planificación maestro integrado.</span><span class="sxs-lookup"><span data-stu-id="d256e-144">This is a known issue with the built-in master planning engine.</span></span> <span data-ttu-id="d256e-145">Se debe a la explosión automática subyacente a través de la estructura de la lista de materiales durante las ediciones.</span><span class="sxs-lookup"><span data-stu-id="d256e-145">It is caused by the underlying auto explosion through the BOM structure during edits.</span></span> <span data-ttu-id="d256e-146">Este problema se aborda en la Optimización de la planificación, donde un planificador puede actualizar y aprobar los pedidos relevantes y, cuando lo desee, activar una ejecución de planificación para actualizar los pedidos planificados para la estructura BOM subyacente.</span><span class="sxs-lookup"><span data-stu-id="d256e-146">This issue is addressed in Planning Optimization, where a planner can update and approve the relevant orders and, when desired, trigger a planning run to update planned orders for the underlying BOM structure.</span></span>

<span data-ttu-id="d256e-147">Una forma de mejorar el rendimiento con el motor de planificación maestro integrado es hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d256e-147">One way to improve performance with the built-in master planning engine is to do the following:</span></span>

1. <span data-ttu-id="d256e-148">Vaya a **Planificación maestra \> Configurar \> Planes \> Planes maestros**.</span><span class="sxs-lookup"><span data-stu-id="d256e-148">Go to **Master planning \> Setup \> Plans \> Master plans**.</span></span>
1. <span data-ttu-id="d256e-149">Seleccione un tipo de plan.</span><span class="sxs-lookup"><span data-stu-id="d256e-149">Select a plan.</span></span>
1. <span data-ttu-id="d256e-150">Expanda la ficha desplegable **Límites de tiempo en días**.</span><span class="sxs-lookup"><span data-stu-id="d256e-150">Expand the **Time fence in days** FastTab.</span></span>
1. <span data-ttu-id="d256e-151">Establezca **Explosión** en *Sí* y establezca el campo debajo de esta configuración en 0 (cero).</span><span class="sxs-lookup"><span data-stu-id="d256e-151">Set **Explosion** to *Yes*, and set the field below this setting to 0 (zero).</span></span>

> [!NOTE]
> <span data-ttu-id="d256e-152">Esto limitará el período de explosiones realizadas para este plan maestro a un solo día.</span><span class="sxs-lookup"><span data-stu-id="d256e-152">This will limit the period for explosions performed for this master plan to a single day.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]