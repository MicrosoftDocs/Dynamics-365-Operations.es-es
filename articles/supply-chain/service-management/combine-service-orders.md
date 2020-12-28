---
title: Combinación de pedidos de servicio
description: Puede combinar pedidos de servicio.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 17fbed59b1fe7bec80f25f74451872efd61bed62
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4436641"
---
# <a name="combine-service-orders"></a><span data-ttu-id="7f192-103">Combinación de pedidos de servicio</span><span class="sxs-lookup"><span data-stu-id="7f192-103">Combine service orders</span></span>   

[!include [banner](../includes/banner.md)]


<span data-ttu-id="7f192-104">Al crear líneas de pedido de servicio automáticamente en el formulario **Acuerdos de servicio**, puede elegir una de las siguientes opciones para especificar cómo desea agruparlas:</span><span class="sxs-lookup"><span data-stu-id="7f192-104">When you create service order lines automatically in the **Service agreements** form, you can choose one of the following options to specify how you want to group them:</span></span>

  - <span data-ttu-id="7f192-105">**Por acuerdo de servicio**</span><span class="sxs-lookup"><span data-stu-id="7f192-105">**By service agreement**</span></span>

  - <span data-ttu-id="7f192-106">**Por tarea de servicio**</span><span class="sxs-lookup"><span data-stu-id="7f192-106">**By service task**</span></span>

  - <span data-ttu-id="7f192-107">**Por empleado**</span><span class="sxs-lookup"><span data-stu-id="7f192-107">**By employee**</span></span>

  - <span data-ttu-id="7f192-108">**Por objeto de servicio**</span><span class="sxs-lookup"><span data-stu-id="7f192-108">**By service object**</span></span>

## <a name="example"></a><span data-ttu-id="7f192-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7f192-109">Example</span></span>

<span data-ttu-id="7f192-110">Imagine que crea un acuerdo de servicio que incluya la fecha de inicio del 31-03-2007.</span><span class="sxs-lookup"><span data-stu-id="7f192-110">You create a service agreement that has a start date on 03-31-2007.</span></span> <span data-ttu-id="7f192-111">En el campo **Combinar pedidos de servicio**, especifique **Por objeto de servicio**.</span><span class="sxs-lookup"><span data-stu-id="7f192-111">In the **Combine service orders** field, you specify **By service object**.</span></span> <span data-ttu-id="7f192-112">A continuación, crea las siguientes líneas de acuerdo de servicio:</span><span class="sxs-lookup"><span data-stu-id="7f192-112">You then create the following service agreement lines:</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="7f192-113">Número de línea del acuerdo</span><span class="sxs-lookup"><span data-stu-id="7f192-113">Agreement line number</span></span></p></th>
<th><p><span data-ttu-id="7f192-114">Tipo de transacción</span><span class="sxs-lookup"><span data-stu-id="7f192-114">Transaction type</span></span></p></th>
<th><p><span data-ttu-id="7f192-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="7f192-115">Description</span></span></p></th>
<th><p><span data-ttu-id="7f192-116">Intervalo</span><span class="sxs-lookup"><span data-stu-id="7f192-116">Interval</span></span></p></th>
<th><p><span data-ttu-id="7f192-117">Objeto de servicio</span><span class="sxs-lookup"><span data-stu-id="7f192-117">Service object</span></span></p></th>
<th><p><span data-ttu-id="7f192-118">Fecha de inicio</span><span class="sxs-lookup"><span data-stu-id="7f192-118">Start date</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7f192-119">1</span><span class="sxs-lookup"><span data-stu-id="7f192-119">1</span></span></p></td>
<td><p><span data-ttu-id="7f192-120"><strong>Hora</strong></span><span class="sxs-lookup"><span data-stu-id="7f192-120"><strong>Hour</strong></span></span></p></td>
<td><p><span data-ttu-id="7f192-121">SAL1</span><span class="sxs-lookup"><span data-stu-id="7f192-121">SAL1</span></span></p></td>
<td><p><span data-ttu-id="7f192-122">Semanalmente</span><span class="sxs-lookup"><span data-stu-id="7f192-122">Weekly</span></span></p></td>
<td><p><span data-ttu-id="7f192-123">X-1</span><span class="sxs-lookup"><span data-stu-id="7f192-123">X-1</span></span></p></td>
<td><p><span data-ttu-id="7f192-124">01-04-2007</span><span class="sxs-lookup"><span data-stu-id="7f192-124">04-01-2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7f192-125">2</span><span class="sxs-lookup"><span data-stu-id="7f192-125">2</span></span></p></td>
<td><p><span data-ttu-id="7f192-126"><strong>Hora</strong></span><span class="sxs-lookup"><span data-stu-id="7f192-126"><strong>Hour</strong></span></span></p></td>
<td><p><span data-ttu-id="7f192-127">SAL2</span><span class="sxs-lookup"><span data-stu-id="7f192-127">SAL2</span></span></p></td>
<td><p><span data-ttu-id="7f192-128">Quincenal</span><span class="sxs-lookup"><span data-stu-id="7f192-128">Biweekly</span></span></p></td>
<td><p><span data-ttu-id="7f192-129">X-2</span><span class="sxs-lookup"><span data-stu-id="7f192-129">X-2</span></span></p></td>
<td><p><span data-ttu-id="7f192-130">01-04-2007</span><span class="sxs-lookup"><span data-stu-id="7f192-130">04-01-2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7f192-131">3</span><span class="sxs-lookup"><span data-stu-id="7f192-131">3</span></span></p></td>
<td><p><span data-ttu-id="7f192-132"><strong>Hora</strong></span><span class="sxs-lookup"><span data-stu-id="7f192-132"><strong>Hour</strong></span></span></p></td>
<td><p><span data-ttu-id="7f192-133">SAL3</span><span class="sxs-lookup"><span data-stu-id="7f192-133">SAL3</span></span></p></td>
<td><p><span data-ttu-id="7f192-134">Semanalmente</span><span class="sxs-lookup"><span data-stu-id="7f192-134">Weekly</span></span></p></td>
<td><p><span data-ttu-id="7f192-135">X-2</span><span class="sxs-lookup"><span data-stu-id="7f192-135">X-2</span></span></p></td>
<td><p><span data-ttu-id="7f192-136">01-04-2007</span><span class="sxs-lookup"><span data-stu-id="7f192-136">04-01-2007</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="7f192-137">No especifica ventanas de tiempo para ninguna línea de acuerdo de servicio.</span><span class="sxs-lookup"><span data-stu-id="7f192-137">You do not specify time windows for any of the service agreement lines.</span></span> <span data-ttu-id="7f192-138">Por lo tanto, las líneas de acuerdo de servicio no se transferirán del día calculado en el que se encuentren.</span><span class="sxs-lookup"><span data-stu-id="7f192-138">Therefore, the service order lines will not move from the calculated day on which they fall.</span></span>

<span data-ttu-id="7f192-139">A continuación, genere líneas de pedido de servicio desde el formulario **Crear pedidos de servicio** del 01-04-2007 al 30-04-2007.</span><span class="sxs-lookup"><span data-stu-id="7f192-139">Next, you generate service order lines from the **Create service orders** form from 04-01-2007 until 04-30-2007.</span></span>

<span data-ttu-id="7f192-140">En total, se crean 10 pedidos de servicio.</span><span class="sxs-lookup"><span data-stu-id="7f192-140">In total, 10 service orders are created.</span></span> <span data-ttu-id="7f192-141">Dado que la configuración combinada que seleccionó fue **Por objeto de servicio**, todos los pedidos de servicio que se crean sólo tienen líneas de pedido de servicio con un objeto de servicio específico.</span><span class="sxs-lookup"><span data-stu-id="7f192-141">Because the combined setting that you selected was **By service object**, all service orders that are created have only service order lines with one specific service object.</span></span> <span data-ttu-id="7f192-142">Las líneas de pedido de servicio que se generan a partir del acuerdo de servicio que tienen la misma fecha de servicio y el mismo objeto se combinan en el mismo pedido de servicio.</span><span class="sxs-lookup"><span data-stu-id="7f192-142">Service order lines that are generated from the service agreement and have the same service date and object are combined on the same service order.</span></span>


> [!NOTE]
> <P><span data-ttu-id="7f192-143">En este ejemplo, el calendario especificado en el formulario <STRONG>Parámetros de gestión de servicio</STRONG> no tiene días cerrados.</span><span class="sxs-lookup"><span data-stu-id="7f192-143">In this example, the calendar that is specified in the <STRONG>Service management parameters</STRONG> form has no closed days.</span></span></P>



<span data-ttu-id="7f192-144">Se producen más agrupaciones de líneas de pedido de servicio en pedidos de servicio en función de las ventanas de tiempo que especifique en las líneas de acuerdo de servicio.</span><span class="sxs-lookup"><span data-stu-id="7f192-144">Additional grouping of service order lines into service orders occurs according to any time window that you specify on the service agreement lines.</span></span>

## <a name="see-also"></a><span data-ttu-id="7f192-145">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7f192-145">See also</span></span>

[<span data-ttu-id="7f192-146">Crear pedidos de servicio automáticamente</span><span class="sxs-lookup"><span data-stu-id="7f192-146">Create service orders automatically</span></span>](create-service-orders-automatically.md)

  


