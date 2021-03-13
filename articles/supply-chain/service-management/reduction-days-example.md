---
title: Ejemplo de días de reducción
description: Ejemplo de días de reducción.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMASubscriptionTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 509d1a9e2abd79938376209d8feab1b935394833
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "5010531"
---
# <a name="reduction-days-example"></a><span data-ttu-id="158c9-103">Ejemplo de días de reducción</span><span class="sxs-lookup"><span data-stu-id="158c9-103">Reduction days example</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="158c9-104">Ha creado una transacción de suscripción para la suscripción de mantenimiento de un cliente, tal como se describe en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="158c9-104">You have created a subscription transaction for a customer's maintenance subscription, as described in the following table.</span></span>

<table>
<colgroup>
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="158c9-105">Desde fecha</span><span class="sxs-lookup"><span data-stu-id="158c9-105">From date</span></span></p></th>
<th><p><span data-ttu-id="158c9-106">Hasta fecha</span><span class="sxs-lookup"><span data-stu-id="158c9-106">To date</span></span></p></th>
<th><p><span data-ttu-id="158c9-107">Suscripción</span><span class="sxs-lookup"><span data-stu-id="158c9-107">Subscription</span></span></p></th>
<th><p><span data-ttu-id="158c9-108">Tipo de suscripción</span><span class="sxs-lookup"><span data-stu-id="158c9-108">Subscription type</span></span></p></th>
<th><p><span data-ttu-id="158c9-109">Proyecto</span><span class="sxs-lookup"><span data-stu-id="158c9-109">Project</span></span></p></th>
<th><p><span data-ttu-id="158c9-110">Categoría</span><span class="sxs-lookup"><span data-stu-id="158c9-110">Category</span></span></p></th>
<th><p><span data-ttu-id="158c9-111">Divisa de ventas</span><span class="sxs-lookup"><span data-stu-id="158c9-111">Sales currency</span></span></p></th>
<th><p><span data-ttu-id="158c9-112">Precio de venta</span><span class="sxs-lookup"><span data-stu-id="158c9-112">Sales price</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="158c9-113">01 de marzo de 2011</span><span class="sxs-lookup"><span data-stu-id="158c9-113">March 01, 2011</span></span></p></td>
<td><p><span data-ttu-id="158c9-114">31 de marzo de 2011</span><span class="sxs-lookup"><span data-stu-id="158c9-114">March 31, 2011</span></span></p></td>
<td><p><span data-ttu-id="158c9-115">NR-2</span><span class="sxs-lookup"><span data-stu-id="158c9-115">NR-2</span></span></p></td>
<td><p><span data-ttu-id="158c9-116"><strong>Normal</strong></span><span class="sxs-lookup"><span data-stu-id="158c9-116"><strong>Regular</strong></span></span></p></td>
<td><p><span data-ttu-id="158c9-117">9013</span><span class="sxs-lookup"><span data-stu-id="158c9-117">9013</span></span></p></td>
<td><p><span data-ttu-id="158c9-118">SubCat2</span><span class="sxs-lookup"><span data-stu-id="158c9-118">SubCat2</span></span></p></td>
<td><p><span data-ttu-id="158c9-119">EUR</span><span class="sxs-lookup"><span data-stu-id="158c9-119">EUR</span></span></p></td>
<td><p><span data-ttu-id="158c9-120">200,00</span><span class="sxs-lookup"><span data-stu-id="158c9-120">200.00</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="158c9-121">El cliente indica que no necesita cobertura de servicio durante dos días (el 10 de marzo y el 11 de marzo)</span><span class="sxs-lookup"><span data-stu-id="158c9-121">The customer reports that it does not need service coverage for two days (March 10 and March 11).</span></span> <span data-ttu-id="158c9-122">y el usuario acepta reducir la suscripción por estos dos días.</span><span class="sxs-lookup"><span data-stu-id="158c9-122">You agree to reduce the subscription by these two days.</span></span>

<span data-ttu-id="158c9-123">Se crea una nueva transacción del tipo **Días de reducción**, tal como se describe en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="158c9-123">You create a new transaction of the **Reduction days** type, as described in the following table.</span></span>

<table>
<colgroup>
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
<col style="width: 12%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="158c9-124">Desde fecha</span><span class="sxs-lookup"><span data-stu-id="158c9-124">From date</span></span></p></th>
<th><p><span data-ttu-id="158c9-125">Hasta fecha</span><span class="sxs-lookup"><span data-stu-id="158c9-125">To date</span></span></p></th>
<th><p><span data-ttu-id="158c9-126">Suscripción</span><span class="sxs-lookup"><span data-stu-id="158c9-126">Subscription</span></span></p></th>
<th><p><span data-ttu-id="158c9-127">Tipo de suscripción</span><span class="sxs-lookup"><span data-stu-id="158c9-127">Subscription type</span></span></p></th>
<th><p><span data-ttu-id="158c9-128">Proyecto</span><span class="sxs-lookup"><span data-stu-id="158c9-128">Project</span></span></p></th>
<th><p><span data-ttu-id="158c9-129">Categoría</span><span class="sxs-lookup"><span data-stu-id="158c9-129">Category</span></span></p></th>
<th><p><span data-ttu-id="158c9-130">Divisa de ventas</span><span class="sxs-lookup"><span data-stu-id="158c9-130">Sales currency</span></span></p></th>
<th><p><span data-ttu-id="158c9-131">Precio de venta</span><span class="sxs-lookup"><span data-stu-id="158c9-131">Sales price</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="158c9-132">10 de marzo de 2011</span><span class="sxs-lookup"><span data-stu-id="158c9-132">March 10, 2011</span></span></p></td>
<td><p><span data-ttu-id="158c9-133">11 de marzo de 2011</span><span class="sxs-lookup"><span data-stu-id="158c9-133">March 11, 2011</span></span></p></td>
<td><p><span data-ttu-id="158c9-134">NR-2</span><span class="sxs-lookup"><span data-stu-id="158c9-134">NR-2</span></span></p></td>
<td><p><span data-ttu-id="158c9-135"><strong>Días de reducción</strong></span><span class="sxs-lookup"><span data-stu-id="158c9-135"><strong>Reduction days</strong></span></span></p></td>
<td><p><span data-ttu-id="158c9-136">9013</span><span class="sxs-lookup"><span data-stu-id="158c9-136">9013</span></span></p></td>
<td><p><span data-ttu-id="158c9-137">SubCat2</span><span class="sxs-lookup"><span data-stu-id="158c9-137">SubCat2</span></span></p></td>
<td><p><span data-ttu-id="158c9-138">EUR</span><span class="sxs-lookup"><span data-stu-id="158c9-138">EUR</span></span></p></td>
<td><p><span data-ttu-id="158c9-139">-12,90</span><span class="sxs-lookup"><span data-stu-id="158c9-139">-12.90</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="158c9-140">Cuando se facturen las transacciones de marzo de 2011, el precio de ventas de EUR 200 se reduce en EUR 12,90.</span><span class="sxs-lookup"><span data-stu-id="158c9-140">When the transactions for March 2011 are invoiced, the sales price of EUR 200 is reduced by EUR 12.90.</span></span> <span data-ttu-id="158c9-141">Por lo tanto, el importe imputable para la transacción es EUR 187,10 y se facturan dos transacciones por un total de EUR 187,10.</span><span class="sxs-lookup"><span data-stu-id="158c9-141">The chargeable amount for the subscription transaction is therefore EUR 187.10, and two transactions are invoiced at a total of EUR 187.10.</span></span>

## <a name="see-also"></a><span data-ttu-id="158c9-142">Consulte también</span><span class="sxs-lookup"><span data-stu-id="158c9-142">See also</span></span>

[<span data-ttu-id="158c9-143">Reducir los días de las cuotas de suscripción</span><span class="sxs-lookup"><span data-stu-id="158c9-143">Reduce the days on subscription fees</span></span>](reduce-the-days-on-subscription-fees.md)

  


