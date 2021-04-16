---
title: Planificación con cantidades negativas disponibles
description: Este tema explica cómo se maneja la disponibilidad negativa cuando utiliza la optimización de planificación.
author: ChristianRytt
ms.date: 02/18/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-02-18
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 1c403e23309dda36dd1c99e22bbae0aa2d6d76a4
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5813108"
---
# <a name="planning-with-negative-on-hand-quantities"></a><span data-ttu-id="3ff6a-103">Planificación con cantidades negativas disponibles</span><span class="sxs-lookup"><span data-stu-id="3ff6a-103">Planning with negative on-hand quantities</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="3ff6a-104">Si el sistema muestra una cantidad agregada negativa disponible, el motor de planificación trata la cantidad como 0 (cero) para ayudar a evitar el exceso de oferta.</span><span class="sxs-lookup"><span data-stu-id="3ff6a-104">If the system shows a negative aggregate on-hand quantity, the planning engine treats the quantity as 0 (zero) to help avoid over-supply.</span></span> <span data-ttu-id="3ff6a-105">Así es como funciona esta funcionalidad:</span><span class="sxs-lookup"><span data-stu-id="3ff6a-105">Here is how this functionality works:</span></span>

1. <span data-ttu-id="3ff6a-106">La función de optimización de planificación agrega cantidades disponibles en el nivel más bajo de dimensiones de cobertura.</span><span class="sxs-lookup"><span data-stu-id="3ff6a-106">The planning optimization feature aggregates on-hand quantities at the lowest level of coverage dimensions.</span></span> <span data-ttu-id="3ff6a-107">(Por ejemplo, si *ubicación* no es una dimensión de cobertura, la optimización de planificación agrega cantidades disponibles en el nivel *almacén*).</span><span class="sxs-lookup"><span data-stu-id="3ff6a-107">(For example, if *location* isn't a coverage dimension, planning optimization aggregates on-hand quantities at the *warehouse* level.)</span></span>
1. <span data-ttu-id="3ff6a-108">Si la cantidad disponible en el nivel más bajo de las dimensiones de cobertura es negativa, el sistema supone que la cantidad disponible es realmente 0 (cero).</span><span class="sxs-lookup"><span data-stu-id="3ff6a-108">If the aggregate on-hand quantity at the lowest level of coverage dimensions is negative, the system assumes that the on-hand quantity is really 0 (zero).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3ff6a-109">El sistema de planificación solo puede ser tan preciso como los datos de entrada.</span><span class="sxs-lookup"><span data-stu-id="3ff6a-109">The planning system can be only as precise as the input data.</span></span> <span data-ttu-id="3ff6a-110">Si los datos de entrada son inexactos, los registros negativos disponibles indicarán que la información de inventario en Microsoft Dynamics 365 Supply Chain Management no está sincronizada con el mundo real.</span><span class="sxs-lookup"><span data-stu-id="3ff6a-110">If the input data is inaccurate, negative on-hand records will indicate that the inventory information in Microsoft Dynamics 365 Supply Chain Management is out of sync with the real world.</span></span> <span data-ttu-id="3ff6a-111">Por lo tanto, el resultado de la planificación será defectuoso.</span><span class="sxs-lookup"><span data-stu-id="3ff6a-111">Therefore, the planning result will be flawed.</span></span> <span data-ttu-id="3ff6a-112">Para obtener un resultado de planificación preciso, debe minimizar la cantidad de registros que muestran una cantidad disponible negativa.</span><span class="sxs-lookup"><span data-stu-id="3ff6a-112">To get a precise planning result, you should minimize the number of records that show a negative on-hand quantity.</span></span>

## <a name="example-1"></a><span data-ttu-id="3ff6a-113">Ejemplo 1</span><span class="sxs-lookup"><span data-stu-id="3ff6a-113">Example 1</span></span>

<span data-ttu-id="3ff6a-114">El almacén 13 se configura de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="3ff6a-114">Warehouse 13 is configured in the following manner:</span></span>

- <span data-ttu-id="3ff6a-115">**Código de cobertura:** Mín./Máx.</span><span class="sxs-lookup"><span data-stu-id="3ff6a-115">**Coverage code:** Min./Max.</span></span>
- <span data-ttu-id="3ff6a-116">**Mínimo:** 15 unidades (uds.)</span><span class="sxs-lookup"><span data-stu-id="3ff6a-116">**Minimum:** 15 pieces (pcs.)</span></span>
- <span data-ttu-id="3ff6a-117">**Máximo:** 25 uds.</span><span class="sxs-lookup"><span data-stu-id="3ff6a-117">**Maximum:** 25 pcs.</span></span>

<span data-ttu-id="3ff6a-118">El nivel más bajo de dimensiones de cobertura es *almacén*, y las siguientes cantidades disponibles se registran en el nivel *ubicación*:</span><span class="sxs-lookup"><span data-stu-id="3ff6a-118">The lowest level of coverage dimensions is *warehouse*, and the following on-hand quantities are recorded at the *location* level:</span></span>

- <span data-ttu-id="3ff6a-119">**Sitio 1, almacén 13, ubicación 1:** 20 uds.</span><span class="sxs-lookup"><span data-stu-id="3ff6a-119">**Site 1, warehouse 13, location 1:** 20 pcs.</span></span>
- <span data-ttu-id="3ff6a-120">**Sitio 1 almacén 13, ubicación 2:** &minus;8 uds.</span><span class="sxs-lookup"><span data-stu-id="3ff6a-120">**Site 1 warehouse 13, location 2:** &minus;8 pcs.</span></span>

<span data-ttu-id="3ff6a-121">Por lo tanto, la cantidad total disponible para el almacén 13 es de 12 unidades.</span><span class="sxs-lookup"><span data-stu-id="3ff6a-121">Therefore, the aggregate on-hand quantity for warehouse 13 is 12 pcs.</span></span> <span data-ttu-id="3ff6a-122">(= 20 uds.</span><span class="sxs-lookup"><span data-stu-id="3ff6a-122">(= 20 pcs.</span></span> <span data-ttu-id="3ff6a-123">&minus; 8 uds.).</span><span class="sxs-lookup"><span data-stu-id="3ff6a-123">&minus; 8 pcs.).</span></span>

<span data-ttu-id="3ff6a-124">En este caso, el motor de planificación utiliza una cantidad total disponible de 12 unidades.</span><span class="sxs-lookup"><span data-stu-id="3ff6a-124">In this case, the planning engine uses an aggregate on-hand quantity of 12 pcs.</span></span> <span data-ttu-id="3ff6a-125">para almacén 13.</span><span class="sxs-lookup"><span data-stu-id="3ff6a-125">for warehouse 13.</span></span>

<span data-ttu-id="3ff6a-126">El resultado es un pedido planificado de 13 uds.</span><span class="sxs-lookup"><span data-stu-id="3ff6a-126">The result is a planned order of 13 pcs.</span></span> <span data-ttu-id="3ff6a-127">(= 25 uds.</span><span class="sxs-lookup"><span data-stu-id="3ff6a-127">(= 25 pcs.</span></span> <span data-ttu-id="3ff6a-128">&minus; 12 uds.) para rellenar el almacén 13 desde 12 uds.</span><span class="sxs-lookup"><span data-stu-id="3ff6a-128">&minus; 12 pcs.) to refill warehouse 13 from 12 pcs.</span></span> <span data-ttu-id="3ff6a-129">a 25 unidades.</span><span class="sxs-lookup"><span data-stu-id="3ff6a-129">to 25 pcs.</span></span>

## <a name="example-2"></a><span data-ttu-id="3ff6a-130">Ejemplo 2</span><span class="sxs-lookup"><span data-stu-id="3ff6a-130">Example 2</span></span>

<span data-ttu-id="3ff6a-131">El almacén 13 se configura de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="3ff6a-131">Warehouse 13 is configured in the following manner:</span></span>

- <span data-ttu-id="3ff6a-132">**Código de cobertura:** Mín./Máx.</span><span class="sxs-lookup"><span data-stu-id="3ff6a-132">**Coverage code:** Min./Max.</span></span>
- <span data-ttu-id="3ff6a-133">**Mínimo:** 15 uds.</span><span class="sxs-lookup"><span data-stu-id="3ff6a-133">**Minimum:** 15 pcs.</span></span>
- <span data-ttu-id="3ff6a-134">**Máximo:** 25 uds.</span><span class="sxs-lookup"><span data-stu-id="3ff6a-134">**Maximum:** 25 pcs.</span></span>

<span data-ttu-id="3ff6a-135">El nivel más bajo de dimensiones de cobertura es *almacén*, y las siguientes cantidades disponibles se registran en el nivel *ubicación*:</span><span class="sxs-lookup"><span data-stu-id="3ff6a-135">The lowest level of coverage dimensions is *warehouse*, and the following on-hand quantities are recorded at the *location* level:</span></span>

- <span data-ttu-id="3ff6a-136">**Sitio 1, almacén 13, ubicación 1:** 4 uds.</span><span class="sxs-lookup"><span data-stu-id="3ff6a-136">**Site 1, warehouse 13, location 1:** 4 pcs.</span></span>
- <span data-ttu-id="3ff6a-137">**Sitio 1 almacén 13, ubicación 2:** &minus;8 uds.</span><span class="sxs-lookup"><span data-stu-id="3ff6a-137">**Site 1 warehouse 13, location 2:** &minus;8 pcs.</span></span>

<span data-ttu-id="3ff6a-138">Por lo tanto, la cantidad total disponible para el almacén 13 es de &minus;4 unidades.</span><span class="sxs-lookup"><span data-stu-id="3ff6a-138">Therefore, the aggregate on-hand quantity for warehouse 13 is &minus;4 pcs.</span></span> <span data-ttu-id="3ff6a-139">(= 4 uds.</span><span class="sxs-lookup"><span data-stu-id="3ff6a-139">(= 4 pcs.</span></span> <span data-ttu-id="3ff6a-140">&minus; 8 uds.).</span><span class="sxs-lookup"><span data-stu-id="3ff6a-140">&minus; 8 pcs.).</span></span> <span data-ttu-id="3ff6a-141">En otras palabras, es menor de 0 (cero).</span><span class="sxs-lookup"><span data-stu-id="3ff6a-141">In other words, it's less than 0 (zero).</span></span>

<span data-ttu-id="3ff6a-142">En este caso, el motor de planificación supone que la cantidad disponible para el almacén 13 es 0 unidades.</span><span class="sxs-lookup"><span data-stu-id="3ff6a-142">In this case, the planning engine assumes that the on-hand quantity for warehouse 13 is 0 pcs.</span></span> <span data-ttu-id="3ff6a-143">en lugar de &minus;4 uds.</span><span class="sxs-lookup"><span data-stu-id="3ff6a-143">instead of &minus;4 pcs.</span></span>

<span data-ttu-id="3ff6a-144">El resultado es un pedido planificado de 25 uds.</span><span class="sxs-lookup"><span data-stu-id="3ff6a-144">The result is a planned order of 25 pcs.</span></span> <span data-ttu-id="3ff6a-145">(= 25 uds.</span><span class="sxs-lookup"><span data-stu-id="3ff6a-145">(= 25 pcs.</span></span> <span data-ttu-id="3ff6a-146">&minus; 0 uds.) para rellenar el almacén 13 desde 0 uds.</span><span class="sxs-lookup"><span data-stu-id="3ff6a-146">&minus; 0 pcs.) to refill warehouse 13 from 0 pcs.</span></span> <span data-ttu-id="3ff6a-147">a 25 unidades.</span><span class="sxs-lookup"><span data-stu-id="3ff6a-147">to 25 pcs.</span></span>

## <a name="related-resources"></a><span data-ttu-id="3ff6a-148">Recursos relacionados</span><span class="sxs-lookup"><span data-stu-id="3ff6a-148">Related resources</span></span>

[<span data-ttu-id="3ff6a-149">Visión general de la optimización de la planificación</span><span class="sxs-lookup"><span data-stu-id="3ff6a-149">Planning Optimization overview</span></span>](planning-optimization-overview.md)

[<span data-ttu-id="3ff6a-150">Introducción a la optimización de la planificación</span><span class="sxs-lookup"><span data-stu-id="3ff6a-150">Get started with Planning Optimization</span></span>](get-started.md)

[<span data-ttu-id="3ff6a-151">Análisis de aptitud de la optimización de la planificación</span><span class="sxs-lookup"><span data-stu-id="3ff6a-151">Planning Optimization fit analysis</span></span>](planning-optimization-fit-analysis.md)

[<span data-ttu-id="3ff6a-152">Ver el historial del plan y los registros de planificación</span><span class="sxs-lookup"><span data-stu-id="3ff6a-152">View plan history and planning logs</span></span>](plan-history-logs.md)

[<span data-ttu-id="3ff6a-153">Cancelar un trabajo de planificación</span><span class="sxs-lookup"><span data-stu-id="3ff6a-153">Cancel a planning job</span></span>](cancel-planning-job.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]