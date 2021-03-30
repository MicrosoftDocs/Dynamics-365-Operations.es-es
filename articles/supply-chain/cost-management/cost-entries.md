---
title: Entradas de costes
description: Este artículo proporciona información acerca de las entradas de coste y de cuándo se crean. Una entrada de coste es un registro que registra la cantidad y el coste de un evento dado.
author: AndersGirke
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventCostOnhandItem
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19131
ms.assetid: dd2663d8-bcc0-47b1-b36d-57433143487c
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6ddd263852fc328756a6dc06bc3f02c661cbd40f
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5228644"
---
# <a name="cost-entries"></a><span data-ttu-id="14d4e-104">Entradas de costes</span><span class="sxs-lookup"><span data-stu-id="14d4e-104">Cost entries</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="14d4e-105">Este artículo proporciona información acerca de las entradas de coste y de cuándo se crean.</span><span class="sxs-lookup"><span data-stu-id="14d4e-105">This article provides information about cost entries and when they are created.</span></span> <span data-ttu-id="14d4e-106">Una entrada de coste es un registro que registra la cantidad y el coste de un evento dado.</span><span class="sxs-lookup"><span data-stu-id="14d4e-106">A cost entry is a record that registers the quantity and cost of a given event.</span></span>

<span data-ttu-id="14d4e-107">Las entradas de costes son agregaciones de las transacciones de inventario que se registran en las dimensiones de inventario financieras activas.</span><span class="sxs-lookup"><span data-stu-id="14d4e-107">Cost entries are aggregations of inventory transactions that are recorded on active financial inventory dimensions.</span></span>

## <a name="examples"></a><span data-ttu-id="14d4e-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="14d4e-108">Examples</span></span>
### <a name="example-1-no-cost-entries-are-created"></a><span data-ttu-id="14d4e-109">Ejemplo 1: No se crean entradas de costes</span><span class="sxs-lookup"><span data-stu-id="14d4e-109">Example 1: No cost entries are created</span></span>

<span data-ttu-id="14d4e-110">Se registra un evento de diario de transferencia.</span><span class="sxs-lookup"><span data-stu-id="14d4e-110">A transfer journal event is registered.</span></span> <span data-ttu-id="14d4e-111">El evento transfiere una pieza del artículo A desde la ubicación A a la ubicación B. La dimensiones de inventario de ubicación no se considera parte del objeto de coste.</span><span class="sxs-lookup"><span data-stu-id="14d4e-111">The event transfers one piece of item A from location A to location B. The Location inventory dimension isn't considered part of the cost object.</span></span> <span data-ttu-id="14d4e-112">Por lo tanto, el evento crea dos transacciones de inventario y ninguna entrada de coste.</span><span class="sxs-lookup"><span data-stu-id="14d4e-112">Therefore, the event creates two inventory transactions and no cost entries.</span></span>

### <a name="example-2-cost-entries-are-created"></a><span data-ttu-id="14d4e-113">Ejemplo 2: Se crean entradas de costes</span><span class="sxs-lookup"><span data-stu-id="14d4e-113">Example 2: Cost entries are created</span></span>

<span data-ttu-id="14d4e-114">Se registra un evento de diario de transferencia.</span><span class="sxs-lookup"><span data-stu-id="14d4e-114">A transfer journal event is registered.</span></span> <span data-ttu-id="14d4e-115">El evento transfiere una pieza del artículo A desde el sitio 1 al sitio 2.</span><span class="sxs-lookup"><span data-stu-id="14d4e-115">The event transfers one piece of item A from site 1 to site 2.</span></span> <span data-ttu-id="14d4e-116">La dimensión de inventario de sitio se considera parte del objeto de coste.</span><span class="sxs-lookup"><span data-stu-id="14d4e-116">The Site inventory dimension is considered part of the cost object.</span></span> <span data-ttu-id="14d4e-117">Por lo tanto, el evento crea dos transacciones de inventario y dos entradas de coste.</span><span class="sxs-lookup"><span data-stu-id="14d4e-117">Therefore, the event creates two inventory transactions and two cost entries.</span></span>

### <a name="example-3-one-cost-entry-is-created"></a><span data-ttu-id="14d4e-118">Ejemplo 3: Se crea una entrada de coste</span><span class="sxs-lookup"><span data-stu-id="14d4e-118">Example 3: One cost entry is created</span></span>

<span data-ttu-id="14d4e-119">Se registra un evento de recepción de producto para un pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="14d4e-119">A product receipt event is registered for a purchase order.</span></span> <span data-ttu-id="14d4e-120">El evento registra 100 piezas del artículo A en un coste unitario de 10,00 dólares estadounidenses (USD).</span><span class="sxs-lookup"><span data-stu-id="14d4e-120">The event registers 100 pieces of item A at a unit cost of 10.00 U.S. dollars (USD).</span></span> <span data-ttu-id="14d4e-121">Dado que el artículo A usa un número de serie para realizar un seguimiento de la finalidad de la administración de inventario, se crea un número de serie único para cada artículo que se recibe.</span><span class="sxs-lookup"><span data-stu-id="14d4e-121">Because item A uses a serial number to track the purpose of inventory management, a unique serial number is created for each item that is received.</span></span> <span data-ttu-id="14d4e-122">Por lo tanto, el evento crea 100 transacciones de inventario y una entrada de coste.</span><span class="sxs-lookup"><span data-stu-id="14d4e-122">Therefore, the event creates 100 inventory transactions and one cost entry.</span></span>

## <a name="cost-entries-page"></a><span data-ttu-id="14d4e-123">Página Entradas de costes</span><span class="sxs-lookup"><span data-stu-id="14d4e-123">Cost entries page</span></span>
<span data-ttu-id="14d4e-124">La nueva página **Entradas de costes** le permite ver y controlar registros de cantidades y costes.</span><span class="sxs-lookup"><span data-stu-id="14d4e-124">The new **Cost entries** page lets you view and control registrations of quantities and costs.</span></span> <span data-ttu-id="14d4e-125">Esta página complementa las páginas **Transacción de inventario** y **Liquidación del inventario**.</span><span class="sxs-lookup"><span data-stu-id="14d4e-125">This page complements the **Inventory transaction** and **Inventory settlement** pages.</span></span> <span data-ttu-id="14d4e-126">Los registros se registran en orden cronológico para un evento.</span><span class="sxs-lookup"><span data-stu-id="14d4e-126">Records are registered in chronological order for an event.</span></span> <span data-ttu-id="14d4e-127">Por lo tanto, puede encontrar y controlar rápidamente los costes acumulados de un evento específico o todos los eventos relacionados con un documento.</span><span class="sxs-lookup"><span data-stu-id="14d4e-127">Therefore, you can quickly find and control the accumulated costs of a specific event or all events that are related to a document.</span></span> <span data-ttu-id="14d4e-128">Este es un ejemplo:</span><span class="sxs-lookup"><span data-stu-id="14d4e-128">Here is an example:</span></span>

-   <span data-ttu-id="14d4e-129">Se registra un evento de recepción de producto para el artículo A. Se reciben cien piezas en un coste unitario de 10,00 USD.</span><span class="sxs-lookup"><span data-stu-id="14d4e-129">A product receipt event is registered for item A. One hundred pieces are received at a unit cost of 10.00 USD.</span></span>
-   <span data-ttu-id="14d4e-130">Algunos días después del registro del evento de la factura, el coste aumenta a 11,00 USD.</span><span class="sxs-lookup"><span data-stu-id="14d4e-130">A few days after the invoice event is registered, the cost increases to 11.00 USD.</span></span> <span data-ttu-id="14d4e-131">Por tanto, el importe total es 1.100 USD.</span><span class="sxs-lookup"><span data-stu-id="14d4e-131">Therefore, the total amount is 1,100 USD.</span></span> <span data-ttu-id="14d4e-132">Se crea un segundo asiento para tener en cuenta la diferencia de 100 USD.</span><span class="sxs-lookup"><span data-stu-id="14d4e-132">A second voucher is created to account for the difference of 100 USD.</span></span>
-   <span data-ttu-id="14d4e-133">Unos días más tarde, se registra un cargo vario de 15,00 USD para cubrir el coste de transporte en el pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="14d4e-133">A few days later, a miscellaneous charge of 15.00 USD to cover the transportation cost is registered on the purchase order.</span></span>

| <span data-ttu-id="14d4e-134">Asiento</span><span class="sxs-lookup"><span data-stu-id="14d4e-134">Voucher</span></span> | <span data-ttu-id="14d4e-135">Fecha</span><span class="sxs-lookup"><span data-stu-id="14d4e-135">Date</span></span>       | <span data-ttu-id="14d4e-136">Referencia</span><span class="sxs-lookup"><span data-stu-id="14d4e-136">Reference</span></span>      | <span data-ttu-id="14d4e-137">Número</span><span class="sxs-lookup"><span data-stu-id="14d4e-137">Number</span></span> | <span data-ttu-id="14d4e-138">Id. de lote interno</span><span class="sxs-lookup"><span data-stu-id="14d4e-138">Lot ID</span></span>  | <span data-ttu-id="14d4e-139">Cantidad</span><span class="sxs-lookup"><span data-stu-id="14d4e-139">Quantity</span></span> | <span data-ttu-id="14d4e-140">Importe</span><span class="sxs-lookup"><span data-stu-id="14d4e-140">Amount</span></span>  |
|---------|------------|----------------|--------|---------|---------------|----|
| <span data-ttu-id="14d4e-141">00001</span><span class="sxs-lookup"><span data-stu-id="14d4e-141">00001</span></span>   | <span data-ttu-id="14d4e-142">01-01-2015</span><span class="sxs-lookup"><span data-stu-id="14d4e-142">01-01-2015</span></span> | <span data-ttu-id="14d4e-143">Pedido de compra</span><span class="sxs-lookup"><span data-stu-id="14d4e-143">Purchase order</span></span> | <span data-ttu-id="14d4e-144">100001</span><span class="sxs-lookup"><span data-stu-id="14d4e-144">100001</span></span> | <span data-ttu-id="14d4e-145">0000101</span><span class="sxs-lookup"><span data-stu-id="14d4e-145">0000101</span></span> | <span data-ttu-id="14d4e-146">100,00</span><span class="sxs-lookup"><span data-stu-id="14d4e-146">100.00</span></span>   | <span data-ttu-id="14d4e-147">1000.00</span><span class="sxs-lookup"><span data-stu-id="14d4e-147">1000.00</span></span> |
| <span data-ttu-id="14d4e-148">00002</span><span class="sxs-lookup"><span data-stu-id="14d4e-148">00002</span></span>   | <span data-ttu-id="14d4e-149">20-01-2015</span><span class="sxs-lookup"><span data-stu-id="14d4e-149">20-01-2015</span></span> | <span data-ttu-id="14d4e-150">Pedido de compra</span><span class="sxs-lookup"><span data-stu-id="14d4e-150">Purchase order</span></span> | <span data-ttu-id="14d4e-151">100001</span><span class="sxs-lookup"><span data-stu-id="14d4e-151">100001</span></span> | <span data-ttu-id="14d4e-152">0000101</span><span class="sxs-lookup"><span data-stu-id="14d4e-152">0000101</span></span> |          | <span data-ttu-id="14d4e-153">100,00</span><span class="sxs-lookup"><span data-stu-id="14d4e-153">100.00</span></span>  |
| <span data-ttu-id="14d4e-154">00003</span><span class="sxs-lookup"><span data-stu-id="14d4e-154">00003</span></span>   | <span data-ttu-id="14d4e-155">31-01-2015</span><span class="sxs-lookup"><span data-stu-id="14d4e-155">31-01-2015</span></span> | <span data-ttu-id="14d4e-156">Ajuste</span><span class="sxs-lookup"><span data-stu-id="14d4e-156">Adjustment</span></span>     | <span data-ttu-id="14d4e-157">100001</span><span class="sxs-lookup"><span data-stu-id="14d4e-157">100001</span></span> | <span data-ttu-id="14d4e-158">0000101</span><span class="sxs-lookup"><span data-stu-id="14d4e-158">0000101</span></span> |          | <span data-ttu-id="14d4e-159">15:00</span><span class="sxs-lookup"><span data-stu-id="14d4e-159">15.00</span></span>   |

<span data-ttu-id="14d4e-160">La página **Entradas de costes** permite el filtrado por id. de documento y fecha de documento.</span><span class="sxs-lookup"><span data-stu-id="14d4e-160">The **Cost entries** page enables filtering by document ID and document date.</span></span> 

> [!NOTE]
> <span data-ttu-id="14d4e-161">Las entradas de costes solo están disponibles para [objetos de costes](cost-object.md) o productos liberados.</span><span class="sxs-lookup"><span data-stu-id="14d4e-161">Cost entries are available only for [cost objects](cost-object.md) or released products.</span></span>

<a name="additional-resources"></a><span data-ttu-id="14d4e-162">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="14d4e-162">Additional resources</span></span>
--------

[<span data-ttu-id="14d4e-163">Objetos de coste</span><span class="sxs-lookup"><span data-stu-id="14d4e-163">Cost objects</span></span>](cost-object.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]