---
title: Actualizaciones físicas y financieras
description: En este tema se proporciona un resumen de qué tipos de transacciones aumentan y reducen las cantidades de inventario.
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventTrans, InventTransVoucher
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 75023
ms.assetid: 128340e1-c573-48e6-b835-6c350d8dd0fb
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4360f9132d31c9d0038f51c68c1f6c3fcaaa2025
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2019
ms.locfileid: "2250883"
---
# <a name="physical-and-financial-updates"></a><span data-ttu-id="f7184-103">Actualizaciones físicas y financieras</span><span class="sxs-lookup"><span data-stu-id="f7184-103">Physical and financial updates</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f7184-104">En este tema se proporciona un resumen de qué tipos de transacciones aumentan y reducen las cantidades de inventario.</span><span class="sxs-lookup"><span data-stu-id="f7184-104">This topic provides an overview of which types of transactions increase or decrease inventory quantities.</span></span> 

<span data-ttu-id="f7184-105">Las transacciones de inventario se pueden actualizar físicamente y financieramente en Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="f7184-105">Inventory transactions can be physically updated and financially updated in Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="f7184-106">Algunos tipos de transacciones financieras y físicas aumentan las cantidades de inventario, mientras que otros reducen la cantidad.</span><span class="sxs-lookup"><span data-stu-id="f7184-106">Some types of physical and financial transactions increase inventory quantities, whereas others decrease the quantity.</span></span>

## <a name="physical-increases"></a><span data-ttu-id="f7184-107">Incrementos físicos</span><span class="sxs-lookup"><span data-stu-id="f7184-107">Physical increases</span></span>
<span data-ttu-id="f7184-108">Cuando se registra una transacción física, el estado del registro de la transacción es **Recibido**.</span><span class="sxs-lookup"><span data-stu-id="f7184-108">When a physical transaction is posted, the status of the transaction record is **Received**.</span></span> <span data-ttu-id="f7184-109">Las siguientes transacciones se consideran incrementos físicos:</span><span class="sxs-lookup"><span data-stu-id="f7184-109">The following transactions are considered physical increases:</span></span>

-   <span data-ttu-id="f7184-110">Recibo del pedido de compra</span><span class="sxs-lookup"><span data-stu-id="f7184-110">Purchase order receipt</span></span>
-   <span data-ttu-id="f7184-111">Devolución en albarán del pedido de ventas</span><span class="sxs-lookup"><span data-stu-id="f7184-111">Sales order packing slip return</span></span>
-   <span data-ttu-id="f7184-112">Notificación de un pedido de producción como terminado</span><span class="sxs-lookup"><span data-stu-id="f7184-112">Reporting a production order as finished</span></span>
-   <span data-ttu-id="f7184-113">Por producto en una lista de selección de pedidos de producción</span><span class="sxs-lookup"><span data-stu-id="f7184-113">By-product on a production order picking list</span></span>

## <a name="financial-increases"></a><span data-ttu-id="f7184-114">Incrementos financieros</span><span class="sxs-lookup"><span data-stu-id="f7184-114">Financial increases</span></span>
<span data-ttu-id="f7184-115">Cuando se registra una transacción de recepción financiera, el estado del registro de la transacción que aumenta la cantidad es **Comprado**.</span><span class="sxs-lookup"><span data-stu-id="f7184-115">When a financial receipt transaction is posted, the status of the transaction record that increases the quantity is **Purchased**.</span></span> <span data-ttu-id="f7184-116">Las siguientes transacciones se consideran incrementos financieros:</span><span class="sxs-lookup"><span data-stu-id="f7184-116">The following transactions are considered financial increases:</span></span>

-   <span data-ttu-id="f7184-117">Factura de proveedor</span><span class="sxs-lookup"><span data-stu-id="f7184-117">Vendor invoice</span></span>
-   <span data-ttu-id="f7184-118">Factura del pedido de ventas para una devolución</span><span class="sxs-lookup"><span data-stu-id="f7184-118">Sales order invoice for a return</span></span>
-   <span data-ttu-id="f7184-119">Gestión de costes del pedido de producción</span><span class="sxs-lookup"><span data-stu-id="f7184-119">Production order costing</span></span>
-   <span data-ttu-id="f7184-120">Diarios de inventario de cantidad positiva, como movimiento, pérdidas y ganancias, recuento, lista de materiales y transferencia</span><span class="sxs-lookup"><span data-stu-id="f7184-120">Positive quantity inventory journals, such as movement, profit and loss, counting, bill of materials, and transfer</span></span>

## <a name="transactions-that-increase-quantity"></a><span data-ttu-id="f7184-121">Transacciones que aumentan la cantidad.</span><span class="sxs-lookup"><span data-stu-id="f7184-121">Transactions that increase quantity</span></span>
<span data-ttu-id="f7184-122">Las transacciones que aumentan la cantidad se registran en el precio de coste promedio móvil.</span><span class="sxs-lookup"><span data-stu-id="f7184-122">Transactions that increase quantity are posted at the running average cost price.</span></span> <span data-ttu-id="f7184-123">El precio de coste promedio de ejecución calculado basado en el coste de cada una de las transacciones para cada dimensión de inventario de la que se efectúa un seguimiento financiero.</span><span class="sxs-lookup"><span data-stu-id="f7184-123">The calculated running average cost price is based on the cost of each of these transactions for each inventory dimension that is being tracked financially.</span></span> <span data-ttu-id="f7184-124">Para obtener información acerca del precio de coste promedio móvil, consulte [Precio de coste promedio móvil](running-average-cost-price.md).</span><span class="sxs-lookup"><span data-stu-id="f7184-124">For information about running average cost prices, see [Running average cost price](running-average-cost-price.md).</span></span>

## <a name="transactions-that-decrease-quantity"></a><span data-ttu-id="f7184-125">Transacciones que reducen la cantidad</span><span class="sxs-lookup"><span data-stu-id="f7184-125">Transactions that decrease quantity</span></span>
<span data-ttu-id="f7184-126">El precio de coste promedio de ejecución se usa cuando se registra una transacción que reduce la cantidad, independientemente de qué modelo de inventario está asociado a ese inventario.</span><span class="sxs-lookup"><span data-stu-id="f7184-126">The calculated running average cost price is used  when a transaction that decreases quantity is posted, regardless of the inventory model that is associated with that inventory.</span></span> <span data-ttu-id="f7184-127">La transacción que reduce la cantidad no debe haberse marcado para otra transacción antes de registrarse.</span><span class="sxs-lookup"><span data-stu-id="f7184-127">The transaction that decreases quantity must not have been marked to another transaction before it was posted.</span></span> <span data-ttu-id="f7184-128">Si el inventario físico disponible llega a ser negativo, se utiliza el coste de inventario definido para el artículo en la página **Artículo**.</span><span class="sxs-lookup"><span data-stu-id="f7184-128">If the physical on-hand inventory becomes negative, the inventory cost that is defined for the item on the **Item** page is used.</span></span> 

> [!NOTE]
> <span data-ttu-id="f7184-129">Si la funcionalidad multisitio está activada, este coste será en su lugar el coste de inventario definido para un sitio en la página **Configuración predeterminada de pedido**.</span><span class="sxs-lookup"><span data-stu-id="f7184-129">If multisite functionality is enabled, this cost will instead be the inventory cost that is defined for a site on the **Default order settings** page.</span></span>

## <a name="physical-issues-vs-financial-issues"></a><span data-ttu-id="f7184-130">Emisiones físicas frente a emisiones financieras</span><span class="sxs-lookup"><span data-stu-id="f7184-130">Physical issues vs. financial issues</span></span>
<span data-ttu-id="f7184-131">Cuando se registra una transacción de emisión física, el estado del registro de la transacción es **Deducido**.</span><span class="sxs-lookup"><span data-stu-id="f7184-131">When a physical issue transaction is posted, the status of the transaction record is **Deducted**.</span></span> <span data-ttu-id="f7184-132">Las siguientes transacciones se consideran emisiones físicas:</span><span class="sxs-lookup"><span data-stu-id="f7184-132">The following transactions are considered physical issues:</span></span>

-   <span data-ttu-id="f7184-133">Diario de listas de selección de órdenes de producción</span><span class="sxs-lookup"><span data-stu-id="f7184-133">Production order picking list journal</span></span>
-   <span data-ttu-id="f7184-134">Albarán del pedido de ventas</span><span class="sxs-lookup"><span data-stu-id="f7184-134">Sales order packing slip</span></span>
-   <span data-ttu-id="f7184-135">Devolución del albarán de pedido de compra</span><span class="sxs-lookup"><span data-stu-id="f7184-135">Purchase order packing slip return</span></span>

<span data-ttu-id="f7184-136">Cuando se registra una transacción financiera, el estado del registro de la transacción es **Vendido**.</span><span class="sxs-lookup"><span data-stu-id="f7184-136">When a financial transaction is posted, the status of the transaction record is **Sold**.</span></span> <span data-ttu-id="f7184-137">Las siguientes transacciones se consideran emisiones financieras:</span><span class="sxs-lookup"><span data-stu-id="f7184-137">The following transactions are considered financial issues:</span></span>

-   <span data-ttu-id="f7184-138">Finalización de un pedido de producción</span><span class="sxs-lookup"><span data-stu-id="f7184-138">Ending a production order</span></span>
-   <span data-ttu-id="f7184-139">Factura del pedido de ventas</span><span class="sxs-lookup"><span data-stu-id="f7184-139">Sales order invoice</span></span>
-   <span data-ttu-id="f7184-140">Devolución de facturas de proveedor</span><span class="sxs-lookup"><span data-stu-id="f7184-140">Vendor invoice return</span></span>
-   <span data-ttu-id="f7184-141">Diarios de inventario de cantidad negativa, como movimiento, pérdidas y ganancias, recuento, lista de materiales y transferencia</span><span class="sxs-lookup"><span data-stu-id="f7184-141">Negative quantity inventory journals, such as movement, profit and loss, counting, bill of materials, and transfer</span></span>

<span data-ttu-id="f7184-142">Las transacciones que reducen la cantidad se registran en el precio de coste promedio móvil.</span><span class="sxs-lookup"><span data-stu-id="f7184-142">Transactions that decrease quantity are posted at the running average cost price.</span></span> <span data-ttu-id="f7184-143">De este modo, el procedimiento de cierre de inventario es necesario para liquidar las transacciones de emisión con las transacciones de recepción en función del modelo de inventario asignado a cada artículo.</span><span class="sxs-lookup"><span data-stu-id="f7184-143">Therefore, the inventory close procedure is required in order to settle issue transactions to receipt transactions, based on the inventory model that is assigned to each item.</span></span>
