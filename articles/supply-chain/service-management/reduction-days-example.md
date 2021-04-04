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
ms.openlocfilehash: df528bf7e95ee7ea74a792894b5e1c2f50c57730
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5234762"
---
# <a name="reduction-days-example"></a><span data-ttu-id="380fe-103">Ejemplo de días de reducción</span><span class="sxs-lookup"><span data-stu-id="380fe-103">Reduction days example</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="380fe-104">Ha creado una transacción de suscripción para la suscripción de mantenimiento de un cliente, tal como se describe en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="380fe-104">You have created a subscription transaction for a customer's maintenance subscription, as described in the following table.</span></span>

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
<th><p><span data-ttu-id="380fe-105">Desde fecha</span><span class="sxs-lookup"><span data-stu-id="380fe-105">From date</span></span></p></th>
<th><p><span data-ttu-id="380fe-106">Hasta fecha</span><span class="sxs-lookup"><span data-stu-id="380fe-106">To date</span></span></p></th>
<th><p><span data-ttu-id="380fe-107">Suscripción</span><span class="sxs-lookup"><span data-stu-id="380fe-107">Subscription</span></span></p></th>
<th><p><span data-ttu-id="380fe-108">Tipo de suscripción</span><span class="sxs-lookup"><span data-stu-id="380fe-108">Subscription type</span></span></p></th>
<th><p><span data-ttu-id="380fe-109">Proyecto</span><span class="sxs-lookup"><span data-stu-id="380fe-109">Project</span></span></p></th>
<th><p><span data-ttu-id="380fe-110">Categoría</span><span class="sxs-lookup"><span data-stu-id="380fe-110">Category</span></span></p></th>
<th><p><span data-ttu-id="380fe-111">Divisa de ventas</span><span class="sxs-lookup"><span data-stu-id="380fe-111">Sales currency</span></span></p></th>
<th><p><span data-ttu-id="380fe-112">Precio de venta</span><span class="sxs-lookup"><span data-stu-id="380fe-112">Sales price</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="380fe-113">01 de marzo de 2011</span><span class="sxs-lookup"><span data-stu-id="380fe-113">March 01, 2011</span></span></p></td>
<td><p><span data-ttu-id="380fe-114">31 de marzo de 2011</span><span class="sxs-lookup"><span data-stu-id="380fe-114">March 31, 2011</span></span></p></td>
<td><p><span data-ttu-id="380fe-115">NR-2</span><span class="sxs-lookup"><span data-stu-id="380fe-115">NR-2</span></span></p></td>
<td><p><span data-ttu-id="380fe-116"><strong>Normal</strong></span><span class="sxs-lookup"><span data-stu-id="380fe-116"><strong>Regular</strong></span></span></p></td>
<td><p><span data-ttu-id="380fe-117">9013</span><span class="sxs-lookup"><span data-stu-id="380fe-117">9013</span></span></p></td>
<td><p><span data-ttu-id="380fe-118">SubCat2</span><span class="sxs-lookup"><span data-stu-id="380fe-118">SubCat2</span></span></p></td>
<td><p><span data-ttu-id="380fe-119">EUR</span><span class="sxs-lookup"><span data-stu-id="380fe-119">EUR</span></span></p></td>
<td><p><span data-ttu-id="380fe-120">200,00</span><span class="sxs-lookup"><span data-stu-id="380fe-120">200.00</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="380fe-121">El cliente indica que no necesita cobertura de servicio durante dos días (el 10 de marzo y el 11 de marzo)</span><span class="sxs-lookup"><span data-stu-id="380fe-121">The customer reports that it does not need service coverage for two days (March 10 and March 11).</span></span> <span data-ttu-id="380fe-122">y el usuario acepta reducir la suscripción por estos dos días.</span><span class="sxs-lookup"><span data-stu-id="380fe-122">You agree to reduce the subscription by these two days.</span></span>

<span data-ttu-id="380fe-123">Se crea una nueva transacción del tipo **Días de reducción**, tal como se describe en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="380fe-123">You create a new transaction of the **Reduction days** type, as described in the following table.</span></span>

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
<th><p><span data-ttu-id="380fe-124">Desde fecha</span><span class="sxs-lookup"><span data-stu-id="380fe-124">From date</span></span></p></th>
<th><p><span data-ttu-id="380fe-125">Hasta fecha</span><span class="sxs-lookup"><span data-stu-id="380fe-125">To date</span></span></p></th>
<th><p><span data-ttu-id="380fe-126">Suscripción</span><span class="sxs-lookup"><span data-stu-id="380fe-126">Subscription</span></span></p></th>
<th><p><span data-ttu-id="380fe-127">Tipo de suscripción</span><span class="sxs-lookup"><span data-stu-id="380fe-127">Subscription type</span></span></p></th>
<th><p><span data-ttu-id="380fe-128">Proyecto</span><span class="sxs-lookup"><span data-stu-id="380fe-128">Project</span></span></p></th>
<th><p><span data-ttu-id="380fe-129">Categoría</span><span class="sxs-lookup"><span data-stu-id="380fe-129">Category</span></span></p></th>
<th><p><span data-ttu-id="380fe-130">Divisa de ventas</span><span class="sxs-lookup"><span data-stu-id="380fe-130">Sales currency</span></span></p></th>
<th><p><span data-ttu-id="380fe-131">Precio de venta</span><span class="sxs-lookup"><span data-stu-id="380fe-131">Sales price</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="380fe-132">10 de marzo de 2011</span><span class="sxs-lookup"><span data-stu-id="380fe-132">March 10, 2011</span></span></p></td>
<td><p><span data-ttu-id="380fe-133">11 de marzo de 2011</span><span class="sxs-lookup"><span data-stu-id="380fe-133">March 11, 2011</span></span></p></td>
<td><p><span data-ttu-id="380fe-134">NR-2</span><span class="sxs-lookup"><span data-stu-id="380fe-134">NR-2</span></span></p></td>
<td><p><span data-ttu-id="380fe-135"><strong>Días de reducción</strong></span><span class="sxs-lookup"><span data-stu-id="380fe-135"><strong>Reduction days</strong></span></span></p></td>
<td><p><span data-ttu-id="380fe-136">9013</span><span class="sxs-lookup"><span data-stu-id="380fe-136">9013</span></span></p></td>
<td><p><span data-ttu-id="380fe-137">SubCat2</span><span class="sxs-lookup"><span data-stu-id="380fe-137">SubCat2</span></span></p></td>
<td><p><span data-ttu-id="380fe-138">EUR</span><span class="sxs-lookup"><span data-stu-id="380fe-138">EUR</span></span></p></td>
<td><p><span data-ttu-id="380fe-139">-12,90</span><span class="sxs-lookup"><span data-stu-id="380fe-139">-12.90</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="380fe-140">Cuando se facturen las transacciones de marzo de 2011, el precio de ventas de EUR 200 se reduce en EUR 12,90.</span><span class="sxs-lookup"><span data-stu-id="380fe-140">When the transactions for March 2011 are invoiced, the sales price of EUR 200 is reduced by EUR 12.90.</span></span> <span data-ttu-id="380fe-141">Por lo tanto, el importe imputable para la transacción es EUR 187,10 y se facturan dos transacciones por un total de EUR 187,10.</span><span class="sxs-lookup"><span data-stu-id="380fe-141">The chargeable amount for the subscription transaction is therefore EUR 187.10, and two transactions are invoiced at a total of EUR 187.10.</span></span>

## <a name="see-also"></a><span data-ttu-id="380fe-142">Consulte también</span><span class="sxs-lookup"><span data-stu-id="380fe-142">See also</span></span>

[<span data-ttu-id="380fe-143">Reducir los días de las cuotas de suscripción</span><span class="sxs-lookup"><span data-stu-id="380fe-143">Reduce the days on subscription fees</span></span>](reduce-the-days-on-subscription-fees.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]