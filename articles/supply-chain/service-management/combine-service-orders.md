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
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7bd3ac8cf3c025b082b33247fcd020aebc010bc8
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5247727"
---
# <a name="combine-service-orders"></a><span data-ttu-id="5bcfb-103">Combinación de pedidos de servicio</span><span class="sxs-lookup"><span data-stu-id="5bcfb-103">Combine service orders</span></span>   

[!include [banner](../includes/banner.md)]


<span data-ttu-id="5bcfb-104">Al crear líneas de pedido de servicio automáticamente en el formulario **Acuerdos de servicio**, puede elegir una de las siguientes opciones para especificar cómo desea agruparlas:</span><span class="sxs-lookup"><span data-stu-id="5bcfb-104">When you create service order lines automatically in the **Service agreements** form, you can choose one of the following options to specify how you want to group them:</span></span>

  - <span data-ttu-id="5bcfb-105">**Por acuerdo de servicio**</span><span class="sxs-lookup"><span data-stu-id="5bcfb-105">**By service agreement**</span></span>

  - <span data-ttu-id="5bcfb-106">**Por tarea de servicio**</span><span class="sxs-lookup"><span data-stu-id="5bcfb-106">**By service task**</span></span>

  - <span data-ttu-id="5bcfb-107">**Por empleado**</span><span class="sxs-lookup"><span data-stu-id="5bcfb-107">**By employee**</span></span>

  - <span data-ttu-id="5bcfb-108">**Por objeto de servicio**</span><span class="sxs-lookup"><span data-stu-id="5bcfb-108">**By service object**</span></span>

## <a name="example"></a><span data-ttu-id="5bcfb-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5bcfb-109">Example</span></span>

<span data-ttu-id="5bcfb-110">Imagine que crea un acuerdo de servicio que incluya la fecha de inicio del 31-03-2007.</span><span class="sxs-lookup"><span data-stu-id="5bcfb-110">You create a service agreement that has a start date on 03-31-2007.</span></span> <span data-ttu-id="5bcfb-111">En el campo **Combinar pedidos de servicio**, especifique **Por objeto de servicio**.</span><span class="sxs-lookup"><span data-stu-id="5bcfb-111">In the **Combine service orders** field, you specify **By service object**.</span></span> <span data-ttu-id="5bcfb-112">A continuación, crea las siguientes líneas de acuerdo de servicio:</span><span class="sxs-lookup"><span data-stu-id="5bcfb-112">You then create the following service agreement lines:</span></span>

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
<th><p><span data-ttu-id="5bcfb-113">Número de línea del acuerdo</span><span class="sxs-lookup"><span data-stu-id="5bcfb-113">Agreement line number</span></span></p></th>
<th><p><span data-ttu-id="5bcfb-114">Tipo de transacción</span><span class="sxs-lookup"><span data-stu-id="5bcfb-114">Transaction type</span></span></p></th>
<th><p><span data-ttu-id="5bcfb-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="5bcfb-115">Description</span></span></p></th>
<th><p><span data-ttu-id="5bcfb-116">Intervalo</span><span class="sxs-lookup"><span data-stu-id="5bcfb-116">Interval</span></span></p></th>
<th><p><span data-ttu-id="5bcfb-117">Objeto de servicio</span><span class="sxs-lookup"><span data-stu-id="5bcfb-117">Service object</span></span></p></th>
<th><p><span data-ttu-id="5bcfb-118">Fecha de inicio</span><span class="sxs-lookup"><span data-stu-id="5bcfb-118">Start date</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5bcfb-119">1</span><span class="sxs-lookup"><span data-stu-id="5bcfb-119">1</span></span></p></td>
<td><p><span data-ttu-id="5bcfb-120"><strong>Hora</strong></span><span class="sxs-lookup"><span data-stu-id="5bcfb-120"><strong>Hour</strong></span></span></p></td>
<td><p><span data-ttu-id="5bcfb-121">SAL1</span><span class="sxs-lookup"><span data-stu-id="5bcfb-121">SAL1</span></span></p></td>
<td><p><span data-ttu-id="5bcfb-122">Semanalmente</span><span class="sxs-lookup"><span data-stu-id="5bcfb-122">Weekly</span></span></p></td>
<td><p><span data-ttu-id="5bcfb-123">X-1</span><span class="sxs-lookup"><span data-stu-id="5bcfb-123">X-1</span></span></p></td>
<td><p><span data-ttu-id="5bcfb-124">01-04-2007</span><span class="sxs-lookup"><span data-stu-id="5bcfb-124">04-01-2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5bcfb-125">2</span><span class="sxs-lookup"><span data-stu-id="5bcfb-125">2</span></span></p></td>
<td><p><span data-ttu-id="5bcfb-126"><strong>Hora</strong></span><span class="sxs-lookup"><span data-stu-id="5bcfb-126"><strong>Hour</strong></span></span></p></td>
<td><p><span data-ttu-id="5bcfb-127">SAL2</span><span class="sxs-lookup"><span data-stu-id="5bcfb-127">SAL2</span></span></p></td>
<td><p><span data-ttu-id="5bcfb-128">Quincenal</span><span class="sxs-lookup"><span data-stu-id="5bcfb-128">Biweekly</span></span></p></td>
<td><p><span data-ttu-id="5bcfb-129">X-2</span><span class="sxs-lookup"><span data-stu-id="5bcfb-129">X-2</span></span></p></td>
<td><p><span data-ttu-id="5bcfb-130">01-04-2007</span><span class="sxs-lookup"><span data-stu-id="5bcfb-130">04-01-2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5bcfb-131">3</span><span class="sxs-lookup"><span data-stu-id="5bcfb-131">3</span></span></p></td>
<td><p><span data-ttu-id="5bcfb-132"><strong>Hora</strong></span><span class="sxs-lookup"><span data-stu-id="5bcfb-132"><strong>Hour</strong></span></span></p></td>
<td><p><span data-ttu-id="5bcfb-133">SAL3</span><span class="sxs-lookup"><span data-stu-id="5bcfb-133">SAL3</span></span></p></td>
<td><p><span data-ttu-id="5bcfb-134">Semanalmente</span><span class="sxs-lookup"><span data-stu-id="5bcfb-134">Weekly</span></span></p></td>
<td><p><span data-ttu-id="5bcfb-135">X-2</span><span class="sxs-lookup"><span data-stu-id="5bcfb-135">X-2</span></span></p></td>
<td><p><span data-ttu-id="5bcfb-136">01-04-2007</span><span class="sxs-lookup"><span data-stu-id="5bcfb-136">04-01-2007</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="5bcfb-137">No especifica ventanas de tiempo para ninguna línea de acuerdo de servicio.</span><span class="sxs-lookup"><span data-stu-id="5bcfb-137">You do not specify time windows for any of the service agreement lines.</span></span> <span data-ttu-id="5bcfb-138">Por lo tanto, las líneas de acuerdo de servicio no se transferirán del día calculado en el que se encuentren.</span><span class="sxs-lookup"><span data-stu-id="5bcfb-138">Therefore, the service order lines will not move from the calculated day on which they fall.</span></span>

<span data-ttu-id="5bcfb-139">A continuación, genere líneas de pedido de servicio desde el formulario **Crear pedidos de servicio** del 01-04-2007 al 30-04-2007.</span><span class="sxs-lookup"><span data-stu-id="5bcfb-139">Next, you generate service order lines from the **Create service orders** form from 04-01-2007 until 04-30-2007.</span></span>

<span data-ttu-id="5bcfb-140">En total, se crean 10 pedidos de servicio.</span><span class="sxs-lookup"><span data-stu-id="5bcfb-140">In total, 10 service orders are created.</span></span> <span data-ttu-id="5bcfb-141">Dado que la configuración combinada que seleccionó fue **Por objeto de servicio**, todos los pedidos de servicio que se crean sólo tienen líneas de pedido de servicio con un objeto de servicio específico.</span><span class="sxs-lookup"><span data-stu-id="5bcfb-141">Because the combined setting that you selected was **By service object**, all service orders that are created have only service order lines with one specific service object.</span></span> <span data-ttu-id="5bcfb-142">Las líneas de pedido de servicio que se generan a partir del acuerdo de servicio que tienen la misma fecha de servicio y el mismo objeto se combinan en el mismo pedido de servicio.</span><span class="sxs-lookup"><span data-stu-id="5bcfb-142">Service order lines that are generated from the service agreement and have the same service date and object are combined on the same service order.</span></span>


> [!NOTE]
> <P><span data-ttu-id="5bcfb-143">En este ejemplo, el calendario especificado en el formulario <STRONG>Parámetros de gestión de servicio</STRONG> no tiene días cerrados.</span><span class="sxs-lookup"><span data-stu-id="5bcfb-143">In this example, the calendar that is specified in the <STRONG>Service management parameters</STRONG> form has no closed days.</span></span></P>



<span data-ttu-id="5bcfb-144">Se producen más agrupaciones de líneas de pedido de servicio en pedidos de servicio en función de las ventanas de tiempo que especifique en las líneas de acuerdo de servicio.</span><span class="sxs-lookup"><span data-stu-id="5bcfb-144">Additional grouping of service order lines into service orders occurs according to any time window that you specify on the service agreement lines.</span></span>

## <a name="see-also"></a><span data-ttu-id="5bcfb-145">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5bcfb-145">See also</span></span>

[<span data-ttu-id="5bcfb-146">Crear pedidos de servicio automáticamente</span><span class="sxs-lookup"><span data-stu-id="5bcfb-146">Create service orders automatically</span></span>](create-service-orders-automatically.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]