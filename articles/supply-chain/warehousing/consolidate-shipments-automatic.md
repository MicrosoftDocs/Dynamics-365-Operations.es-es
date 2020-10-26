---
title: Consolidar los envíos cuando se despachan al almacén mediante Despacho automático de pedidos de ventas
description: Este tema presenta un escenario en el que se despachan múltiples pedidos al almacén en el mismo procedimiento periódico automatizado de despacho al almacén.
author: GarmMSFT
manager: tfehr
ms.date: 05/12/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSShipConsolidationPolicy, WHSShipConsolidationWorkbench
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: 10.0.3
ms.openlocfilehash: f4d095456435a3401daa173d79b80b81176a3c17
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/10/2020
ms.locfileid: "3987127"
---
# <a name="consolidate-shipments-when-they-are-released-to-the-warehouse-by-using-automatic-release-of-sales-orders"></a><span data-ttu-id="74a3e-103">Consolidar los envíos cuando se despachan al almacén mediante Despacho automático de pedidos de ventas</span><span class="sxs-lookup"><span data-stu-id="74a3e-103">Consolidate shipments when they are released to the warehouse by using Automatic release of sales orders</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="74a3e-104">Este tema presenta un escenario en el que se despachan múltiples pedidos al almacén en el mismo procedimiento periódico automatizado de despacho al almacén.</span><span class="sxs-lookup"><span data-stu-id="74a3e-104">This topic presents a scenario where multiple orders are released to the warehouse in the same automated release-to-warehouse periodic procedure.</span></span> <span data-ttu-id="74a3e-105">Los pedidos se consolidarán automáticamente en envíos, según las reglas que se definen como directivas de consolidación de envíos.</span><span class="sxs-lookup"><span data-stu-id="74a3e-105">The orders will automatically be consolidated into shipments, based on rules that are defined as shipment consolidation policies.</span></span>

<span data-ttu-id="74a3e-106">Durante el escenario, creará conjuntos de pedidos de ventas y despachará cada conjunto al almacén.</span><span class="sxs-lookup"><span data-stu-id="74a3e-106">During the scenario, you will create sets of sales orders and release each set to the warehouse.</span></span> <span data-ttu-id="74a3e-107">Luego revisará los envíos que se crean o actualizan durante la consolidación de envíos, según las directivas configuradas.</span><span class="sxs-lookup"><span data-stu-id="74a3e-107">You will then review the shipments that are created or updated during shipment consolidation, based on the configured policies.</span></span>

## <a name="make-demo-data-available"></a><span data-ttu-id="74a3e-108">Hacer que los datos de demostración estén disponibles</span><span class="sxs-lookup"><span data-stu-id="74a3e-108">Make demo data available</span></span>

<span data-ttu-id="74a3e-109">El escenario de este tema hace referencia a valores y registros que se incluyen en los datos de demostración estándar que se proporcionan para Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="74a3e-109">The scenario in this topic references values and records that are included in the standard demo data that is provided for Microsoft Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="74a3e-110">Si desea utilizar los valores que se proporcionan aquí mientras realiza los ejercicios, asegúrese de trabajar en un entorno donde estén instalados los datos de demostración y configure la entidad jurídica en **USMF** antes de empezar.</span><span class="sxs-lookup"><span data-stu-id="74a3e-110">If you want to use the values that are provided here as you do the exercises, be sure to work in an environment where the demo data is installed, and set the legal entity to **USMF** before you begin.</span></span>

## <a name="set-up-shipment-consolidation-policies-and-product-filters"></a><span data-ttu-id="74a3e-111">Configurar directivas de consolidación de envíos y filtros de productos</span><span class="sxs-lookup"><span data-stu-id="74a3e-111">Set up shipment consolidation policies and product filters</span></span>

<span data-ttu-id="74a3e-112">El escenario que se describe aquí supone que ya ha activado la función, realizado los ejercicios de [Configurar directivas de consolidación de envíos](configure-shipment-consolidation-policies.md) y creado las directivas y otros registros que se describen allí.</span><span class="sxs-lookup"><span data-stu-id="74a3e-112">The scenario that is described here assumes that you've already turned on the feature, done the exercises in [Configure shipment consolidation policies](configure-shipment-consolidation-policies.md), and created the policies and other records that are described there.</span></span> <span data-ttu-id="74a3e-113">Asegúrese de hacer esos ejercicios antes de continuar con este escenario.</span><span class="sxs-lookup"><span data-stu-id="74a3e-113">Be sure to do those exercises before you continue with this scenario.</span></span>

## <a name="create-the-sales-orders-for-this-scenario"></a><span data-ttu-id="74a3e-114">Crear los pedidos de ventas para este escenario</span><span class="sxs-lookup"><span data-stu-id="74a3e-114">Create the sales orders for this scenario</span></span>

<span data-ttu-id="74a3e-115">Comience creando una colección de pedidos de ventas con los que pueda trabajar.</span><span class="sxs-lookup"><span data-stu-id="74a3e-115">Start by creating a collection of sales orders that you can work with.</span></span> <span data-ttu-id="74a3e-116">Debe trabajar con un almacén habilitado para procesos de almacén avanzado (WMS).</span><span class="sxs-lookup"><span data-stu-id="74a3e-116">You must work with a warehouse that is enabled for advanced warehouse (WMS) processes.</span></span> <span data-ttu-id="74a3e-117">A menos que se mencione explícitamente un almacén diferente, ese mismo almacén debe utilizarse para cada uno de los siguientes conjuntos de pedidos.</span><span class="sxs-lookup"><span data-stu-id="74a3e-117">Unless a different warehouse is explicitly mentioned, that same warehouse must be used for each of the following sets of orders.</span></span>

<span data-ttu-id="74a3e-118">Vaya a **Clientes \> Pedidos \> Todos los pedidos de ventas** y cree una colección de pedidos de ventas que tengan la configuración que se describe en las siguientes subsecciones.</span><span class="sxs-lookup"><span data-stu-id="74a3e-118">Go to **Accounts receivable \> Orders \> All sales orders**, and create a collection of sales orders that have the settings that are described in the following subsections.</span></span>

### <a name="create-order-set-1"></a><span data-ttu-id="74a3e-119">Crear conjunto de pedidos 1</span><span class="sxs-lookup"><span data-stu-id="74a3e-119">Create order set 1</span></span>

#### <a name="sales-order-1-1"></a><span data-ttu-id="74a3e-120">Pedido de ventas 1-1</span><span class="sxs-lookup"><span data-stu-id="74a3e-120">Sales order 1-1</span></span>

1. <span data-ttu-id="74a3e-121">Cree un pedido de ventas con la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="74a3e-121">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="74a3e-122">**Cuenta de cliente:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="74a3e-122">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="74a3e-123">**Modo de entrega:** *Airwa-Air*</span><span class="sxs-lookup"><span data-stu-id="74a3e-123">**Mode of delivery:** *Airwa-Air*</span></span>

1. <span data-ttu-id="74a3e-124">Agregue una línea de pedido que tenga la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="74a3e-124">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="74a3e-125">**Número de artículo:** *A0001* (un artículo al que no se ha asignado el filtro **Código 4**)</span><span class="sxs-lookup"><span data-stu-id="74a3e-125">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="74a3e-126">**Cantidad:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="74a3e-126">**Quantity:** *1.00*</span></span>

#### <a name="sales-order-1-2"></a><span data-ttu-id="74a3e-127">Pedido de ventas 1-2</span><span class="sxs-lookup"><span data-stu-id="74a3e-127">Sales order 1-2</span></span>

1. <span data-ttu-id="74a3e-128">Cree un pedido de ventas con la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="74a3e-128">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="74a3e-129">**Cuenta de cliente:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="74a3e-129">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="74a3e-130">**Modo de entrega:** *Airwa-Air*</span><span class="sxs-lookup"><span data-stu-id="74a3e-130">**Mode of delivery:** *Airwa-Air*</span></span>

1. <span data-ttu-id="74a3e-131">Agregue una línea de pedido que tenga la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="74a3e-131">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="74a3e-132">**Número de artículo:** *A0001* (un artículo al que no se ha asignado el filtro **Código 4**)</span><span class="sxs-lookup"><span data-stu-id="74a3e-132">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="74a3e-133">**Cantidad:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="74a3e-133">**Quantity:** *1.00*</span></span>

#### <a name="sales-order-1-3"></a><span data-ttu-id="74a3e-134">Pedido de ventas 1-3</span><span class="sxs-lookup"><span data-stu-id="74a3e-134">Sales order 1-3</span></span>

1. <span data-ttu-id="74a3e-135">Cree un pedido de ventas con la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="74a3e-135">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="74a3e-136">**Cuenta de cliente:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="74a3e-136">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="74a3e-137">**Modo de entrega:** *10*</span><span class="sxs-lookup"><span data-stu-id="74a3e-137">**Mode of delivery:** *10*</span></span>

1. <span data-ttu-id="74a3e-138">Agregue una línea de pedido que tenga la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="74a3e-138">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="74a3e-139">**Número de artículo:** *A0001* (un artículo al que no se ha asignado el filtro **Código 4**)</span><span class="sxs-lookup"><span data-stu-id="74a3e-139">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="74a3e-140">**Cantidad:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="74a3e-140">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="74a3e-141">Agregue un segundo pedido que tenga la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="74a3e-141">Add a second order line that has the following settings:</span></span>

    - <span data-ttu-id="74a3e-142">**Número de artículo:** *A0002* (un artículo al que no se ha asignado el filtro **Código 4**)</span><span class="sxs-lookup"><span data-stu-id="74a3e-142">**Item number:** *A0002* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="74a3e-143">**Cantidad:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="74a3e-143">**Quantity:** *1.00*</span></span>
    - <span data-ttu-id="74a3e-144">**Modo de entrega:** *Airwa-Air*</span><span class="sxs-lookup"><span data-stu-id="74a3e-144">**Mode of delivery:** *Airwa-Air*</span></span>

### <a name="create-order-set-2"></a><span data-ttu-id="74a3e-145">Crear conjunto de pedidos 2</span><span class="sxs-lookup"><span data-stu-id="74a3e-145">Create order set 2</span></span>

#### <a name="sales-orders-2-1-and-2-2"></a><span data-ttu-id="74a3e-146">Pedidos de ventas 2-1 y 2-2</span><span class="sxs-lookup"><span data-stu-id="74a3e-146">Sales orders 2-1 and 2-2</span></span>

1. <span data-ttu-id="74a3e-147">Cree dos pedidos de venta idénticos que tengan la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="74a3e-147">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="74a3e-148">**Cuenta de cliente:** *US-002*</span><span class="sxs-lookup"><span data-stu-id="74a3e-148">**Customer account:** *US-002*</span></span>

1. <span data-ttu-id="74a3e-149">Agregue una línea de pedido que tenga la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="74a3e-149">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="74a3e-150">**Número de artículo:** *M9200* (un artículo donde el filtro **Código 4** está establecido en *Inflamable*)</span><span class="sxs-lookup"><span data-stu-id="74a3e-150">**Item number:** *M9200* (an item where the **Code 4** filter is set to *Flammable*)</span></span>
    - <span data-ttu-id="74a3e-151">**Cantidad:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="74a3e-151">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="74a3e-152">Agregue un segundo pedido que tenga la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="74a3e-152">Add a second order line that has the following settings:</span></span>

    - <span data-ttu-id="74a3e-153">**Número de artículo:** *M9201* (un artículo donde el filtro **Código 4** está establecido en *Explosivo*)</span><span class="sxs-lookup"><span data-stu-id="74a3e-153">**Item number:** *M9201* (an item where the **Code 4** filter is set to *Explosive*)</span></span>
    - <span data-ttu-id="74a3e-154">**Cantidad:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="74a3e-154">**Quantity:** *1.00*</span></span>
    - <span data-ttu-id="74a3e-155">**Modo de entrega:** *Airwa-Air*</span><span class="sxs-lookup"><span data-stu-id="74a3e-155">**Mode of delivery:** *Airwa-Air*</span></span>

### <a name="create-order-set-3"></a><span data-ttu-id="74a3e-156">Crear conjunto de pedidos 3</span><span class="sxs-lookup"><span data-stu-id="74a3e-156">Create order set 3</span></span>

#### <a name="sales-order-3-1"></a><span data-ttu-id="74a3e-157">Pedido de ventas 3-1</span><span class="sxs-lookup"><span data-stu-id="74a3e-157">Sales order 3-1</span></span>

1. <span data-ttu-id="74a3e-158">Cree un pedido de ventas con la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="74a3e-158">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="74a3e-159">**Cuenta de cliente:** *US-002*</span><span class="sxs-lookup"><span data-stu-id="74a3e-159">**Customer account:** *US-002*</span></span>

1. <span data-ttu-id="74a3e-160">Agregue una línea de pedido que tenga la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="74a3e-160">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="74a3e-161">**Número de artículo:** *M9200* (un artículo donde el filtro **Código 4** está establecido en *Inflamable*)</span><span class="sxs-lookup"><span data-stu-id="74a3e-161">**Item number:** *M9200* (an item where the **Code 4** filter is set to *Flammable*)</span></span>
    - <span data-ttu-id="74a3e-162">**Cantidad:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="74a3e-162">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="74a3e-163">Agregue un segundo pedido que tenga la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="74a3e-163">Add a second order line that has the following settings:</span></span>

    - <span data-ttu-id="74a3e-164">**Número de artículo:** *M9201* (un artículo donde el filtro **Código 4** está establecido en *Explosivo*)</span><span class="sxs-lookup"><span data-stu-id="74a3e-164">**Item number:** *M9201* (an item where the **Code 4** filter is set to *Explosive*)</span></span>
    - <span data-ttu-id="74a3e-165">**Cantidad:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="74a3e-165">**Quantity:** *1.00*</span></span>
    - <span data-ttu-id="74a3e-166">**Modo de entrega:** *Airwa-Air*</span><span class="sxs-lookup"><span data-stu-id="74a3e-166">**Mode of delivery:** *Airwa-Air*</span></span>

> [!NOTE]
> <span data-ttu-id="74a3e-167">Este pedido es idéntico a los dos pedidos que creó para el conjunto de pedidos 2.</span><span class="sxs-lookup"><span data-stu-id="74a3e-167">This order is identical to the two orders that you created for order set 2.</span></span> <span data-ttu-id="74a3e-168">Sin embargo, aparece en su propio conjunto de órdenes porque lo despchará por separado más adelante en este escenario.</span><span class="sxs-lookup"><span data-stu-id="74a3e-168">However, it's listed as its own order set because you will release it separately later in this scenario.</span></span>

### <a name="create-order-set-4"></a><span data-ttu-id="74a3e-169">Crear conjunto de pedidos 4</span><span class="sxs-lookup"><span data-stu-id="74a3e-169">Create order set 4</span></span>

#### <a name="sales-order-4-1"></a><span data-ttu-id="74a3e-170">Pedido de ventas 4-1</span><span class="sxs-lookup"><span data-stu-id="74a3e-170">Sales order 4-1</span></span>

1. <span data-ttu-id="74a3e-171">Cree un pedido de ventas con la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="74a3e-171">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="74a3e-172">**Cuenta de cliente:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="74a3e-172">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="74a3e-173">**Solicitud de cliente:** *1*</span><span class="sxs-lookup"><span data-stu-id="74a3e-173">**Customer requisition:** *1*</span></span>

1. <span data-ttu-id="74a3e-174">Agregue una línea de pedido que tenga la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="74a3e-174">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="74a3e-175">**Número de artículo:** *A0001* (un artículo al que no se ha asignado el filtro **Código 4**)</span><span class="sxs-lookup"><span data-stu-id="74a3e-175">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="74a3e-176">**Cantidad:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="74a3e-176">**Quantity:** *1.00*</span></span>

### <a name="create-order-set-5"></a><span data-ttu-id="74a3e-177">Crear conjunto de pedidos 5</span><span class="sxs-lookup"><span data-stu-id="74a3e-177">Create order set 5</span></span>

#### <a name="sales-orders-5-1-and-5-2"></a><span data-ttu-id="74a3e-178">Pedidos de ventas 5-1 y 5-2</span><span class="sxs-lookup"><span data-stu-id="74a3e-178">Sales orders 5-1 and 5-2</span></span>

1. <span data-ttu-id="74a3e-179">Cree dos pedidos de venta idénticos que tengan la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="74a3e-179">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="74a3e-180">**Cuenta de cliente:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="74a3e-180">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="74a3e-181">**Solicitud de cliente:** *2*</span><span class="sxs-lookup"><span data-stu-id="74a3e-181">**Customer requisition:** *2*</span></span>

1. <span data-ttu-id="74a3e-182">Agregue una línea de pedido que tenga la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="74a3e-182">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="74a3e-183">**Número de artículo:** *A0001* (un artículo al que no se ha asignado el filtro **Código 4**)</span><span class="sxs-lookup"><span data-stu-id="74a3e-183">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="74a3e-184">**Cantidad:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="74a3e-184">**Quantity:** *1.00*</span></span>

#### <a name="sales-order-5-3"></a><span data-ttu-id="74a3e-185">Pedido de ventas 5-3</span><span class="sxs-lookup"><span data-stu-id="74a3e-185">Sales order 5-3</span></span>

1. <span data-ttu-id="74a3e-186">Cree un pedido de ventas con la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="74a3e-186">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="74a3e-187">**Cuenta de cliente:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="74a3e-187">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="74a3e-188">**Solicitud de cliente:** *1*</span><span class="sxs-lookup"><span data-stu-id="74a3e-188">**Customer requisition:** *1*</span></span>

1. <span data-ttu-id="74a3e-189">Agregue una línea de pedido que tenga la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="74a3e-189">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="74a3e-190">**Número de artículo:** *A0001* (un artículo al que no se ha asignado el filtro **Código 4**)</span><span class="sxs-lookup"><span data-stu-id="74a3e-190">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="74a3e-191">**Cantidad:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="74a3e-191">**Quantity:** *1.00*</span></span>

### <a name="create-order-set-6"></a><span data-ttu-id="74a3e-192">Crear conjunto de pedidos 6</span><span class="sxs-lookup"><span data-stu-id="74a3e-192">Create order set 6</span></span>

#### <a name="sales-orders-6-1-and-6-2"></a><span data-ttu-id="74a3e-193">Pedidos de ventas 6-1 y 6-2</span><span class="sxs-lookup"><span data-stu-id="74a3e-193">Sales orders 6-1 and 6-2</span></span>

1. <span data-ttu-id="74a3e-194">Cree dos pedidos de venta idénticos que tengan la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="74a3e-194">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="74a3e-195">**Cuenta de cliente:** *US-003*</span><span class="sxs-lookup"><span data-stu-id="74a3e-195">**Customer account:** *US-003*</span></span>
    - <span data-ttu-id="74a3e-196">**Solicitud de cliente:** *2*</span><span class="sxs-lookup"><span data-stu-id="74a3e-196">**Customer requisition:** *2*</span></span>

1. <span data-ttu-id="74a3e-197">Agregue una línea de pedido que tenga la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="74a3e-197">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="74a3e-198">**Número de artículo:** *A0001* (un artículo al que no se ha asignado el filtro **Código 4**)</span><span class="sxs-lookup"><span data-stu-id="74a3e-198">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="74a3e-199">**Cantidad:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="74a3e-199">**Quantity:** *1.00*</span></span>

#### <a name="sales-orders-6-3-and-6-4"></a><span data-ttu-id="74a3e-200">Pedidos de ventas 6-3 y 6-4</span><span class="sxs-lookup"><span data-stu-id="74a3e-200">Sales orders 6-3 and 6-4</span></span>

1. <span data-ttu-id="74a3e-201">Cree dos pedidos de venta idénticos que tengan la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="74a3e-201">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="74a3e-202">**Cuenta de cliente:** *US-004*</span><span class="sxs-lookup"><span data-stu-id="74a3e-202">**Customer account:** *US-004*</span></span>
    - <span data-ttu-id="74a3e-203">**Solicitud de cliente:** *1*</span><span class="sxs-lookup"><span data-stu-id="74a3e-203">**Customer requisition:** *1*</span></span>

1. <span data-ttu-id="74a3e-204">Agregue una línea de pedido que tenga la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="74a3e-204">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="74a3e-205">**Número de artículo:** *A0001* (un artículo al que no se ha asignado el filtro **Código 4**)</span><span class="sxs-lookup"><span data-stu-id="74a3e-205">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="74a3e-206">**Cantidad:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="74a3e-206">**Quantity:** *1.00*</span></span>

#### <a name="sales-orders-6-5-and-6-6"></a><span data-ttu-id="74a3e-207">Pedidos de ventas 6-5 y 6-6</span><span class="sxs-lookup"><span data-stu-id="74a3e-207">Sales orders 6-5 and 6-6</span></span>

1. <span data-ttu-id="74a3e-208">Cree dos pedidos de venta idénticos que tengan la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="74a3e-208">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="74a3e-209">**Cuenta de cliente:** *US-007*</span><span class="sxs-lookup"><span data-stu-id="74a3e-209">**Customer account:** *US-007*</span></span>
    - <span data-ttu-id="74a3e-210">**Sitio**: *6*</span><span class="sxs-lookup"><span data-stu-id="74a3e-210">**Site:** *6*</span></span>
    - <span data-ttu-id="74a3e-211">**Almacén**: *61*</span><span class="sxs-lookup"><span data-stu-id="74a3e-211">**Warehouse:** *61*</span></span>
    - <span data-ttu-id="74a3e-212">**Grupo:** *ShipCons*</span><span class="sxs-lookup"><span data-stu-id="74a3e-212">**Pool:** *ShipCons*</span></span>

1. <span data-ttu-id="74a3e-213">Agregue una línea de pedido que tenga la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="74a3e-213">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="74a3e-214">**Número de artículo:** *A0001* (un artículo al que no se ha asignado el filtro **Código 4**)</span><span class="sxs-lookup"><span data-stu-id="74a3e-214">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="74a3e-215">**Cantidad:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="74a3e-215">**Quantity:** *1.00*</span></span>

#### <a name="sales-orders-6-7-and-6-8"></a><span data-ttu-id="74a3e-216">Pedidos de ventas 6-7 y 6-8</span><span class="sxs-lookup"><span data-stu-id="74a3e-216">Sales orders 6-7 and 6-8</span></span>

1. <span data-ttu-id="74a3e-217">Cree dos pedidos de venta idénticos que tengan la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="74a3e-217">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="74a3e-218">**Cuenta de cliente:** *US-007*</span><span class="sxs-lookup"><span data-stu-id="74a3e-218">**Customer account:** *US-007*</span></span>
    - <span data-ttu-id="74a3e-219">**Sitio**: *6*</span><span class="sxs-lookup"><span data-stu-id="74a3e-219">**Site:** *6*</span></span>
    - <span data-ttu-id="74a3e-220">**Almacén**: *61*</span><span class="sxs-lookup"><span data-stu-id="74a3e-220">**Warehouse:** *61*</span></span>
    - <span data-ttu-id="74a3e-221">**Grupo:** Deje este campo en blanco.</span><span class="sxs-lookup"><span data-stu-id="74a3e-221">**Pool:** Leave this field blank.</span></span>

1. <span data-ttu-id="74a3e-222">Agregue una línea de pedido que tenga la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="74a3e-222">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="74a3e-223">**Número de artículo:** *A0001* (un artículo al que no se ha asignado el filtro **Código 4**)</span><span class="sxs-lookup"><span data-stu-id="74a3e-223">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="74a3e-224">**Cantidad:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="74a3e-224">**Quantity:** *1.00*</span></span>

## <a name="automatic-release-of-sales-orders-to-the-warehouse"></a><span data-ttu-id="74a3e-225">Despacho automático de pedidos de ventas al almacén</span><span class="sxs-lookup"><span data-stu-id="74a3e-225">Automatic release of sales orders to the warehouse</span></span>

<span data-ttu-id="74a3e-226">Para cada conjunto de pedidos de ventas que creó anteriormente, completará un procedimiento para el despacho automático al almacén.</span><span class="sxs-lookup"><span data-stu-id="74a3e-226">For each set of sales orders that you created earlier, you will complete a procedure for automatic release to the warehouse.</span></span> <span data-ttu-id="74a3e-227">En cada caso, trabajará a través del [procedimiento básico de despacho al almacén](#release-procedure) que se proporciona aquí.</span><span class="sxs-lookup"><span data-stu-id="74a3e-227">In each case, you will work through the [basic release-to-warehouse procedure](#release-procedure) that is provided here.</span></span>

### <a name="basic-release-to-warehouse-procedure"></a><a name="release-procedure"></a><span data-ttu-id="74a3e-228">Procedimiento básico de despacho al almacén</span><span class="sxs-lookup"><span data-stu-id="74a3e-228">Basic release-to-warehouse procedure</span></span>

<span data-ttu-id="74a3e-229">Para cada conjunto de pedidos de ventas que creó anteriormente, completará los tres procedimientos que se describen en las subsecciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="74a3e-229">For each set of sales orders that you created earlier, you will complete the three procedures that are outlined in the following subsections.</span></span>

#### <a name="update-the-wave-template-that-will-be-used-during-release"></a><span data-ttu-id="74a3e-230">Actualice la plantilla de oleada que se usará durante el despacho</span><span class="sxs-lookup"><span data-stu-id="74a3e-230">Update the wave template that will be used during release</span></span>

1. <span data-ttu-id="74a3e-231">Vaya a **Gestión de almacenes \> Configurar \> Oleadas \> Plantillas de oleada**.</span><span class="sxs-lookup"><span data-stu-id="74a3e-231">Go to **Warehouse management \> Setup \> Waves \> Wave templates**.</span></span>
1. <span data-ttu-id="74a3e-232">Establezca el **Tipo de plantilla de oleada** en *Envío*.</span><span class="sxs-lookup"><span data-stu-id="74a3e-232">Set the **Wave template type** field to *Shipping*.</span></span>
1. <span data-ttu-id="74a3e-233">Busque y seleccione la plantilla de oleada asociada con el almacén que utilizó en los conjuntos de pedidos que creó para este escenario.</span><span class="sxs-lookup"><span data-stu-id="74a3e-233">Find and select the wave template that is associated with the warehouse that you used in the order sets that you created for this scenario.</span></span> <span data-ttu-id="74a3e-234">Por ejemplo, si usó el almacén *24*, seleccione la plantilla de oleada **Envío predeterminado 24**.</span><span class="sxs-lookup"><span data-stu-id="74a3e-234">For example, if you used warehouse *24*, select the **24 Shipping Default** wave template.</span></span> <span data-ttu-id="74a3e-235">Si usó el almacén *61*, seleccione la plantilla de oleada **Envío 61**.</span><span class="sxs-lookup"><span data-stu-id="74a3e-235">If you used warehouse *61*, select the **61 Shipping** wave template.</span></span>
1. <span data-ttu-id="74a3e-236">En el panel Acciones, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="74a3e-236">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="74a3e-237">Establezca la opción **Procesar oleada para su despacho al almacén** en *No*.</span><span class="sxs-lookup"><span data-stu-id="74a3e-237">Set the **Process wave at release to warehouse** option to *No*.</span></span>

#### <a name="release-to-the-warehouse"></a><span data-ttu-id="74a3e-238">Despachar al almacén</span><span class="sxs-lookup"><span data-stu-id="74a3e-238">Release to the warehouse</span></span>

1. <span data-ttu-id="74a3e-239">Ir **Gestion de almacén \> Despachar al almacén \> Despacho automático de pedidos de ventas**.</span><span class="sxs-lookup"><span data-stu-id="74a3e-239">Go to **Warehouse management \> Release to warehouse \> Automatic release of sales orders**.</span></span>
1. <span data-ttu-id="74a3e-240">Establece el campo **Cantidad a despachar** en *Todo*.</span><span class="sxs-lookup"><span data-stu-id="74a3e-240">Set the **Quantity to release** field to *All*.</span></span>
1. <span data-ttu-id="74a3e-241">En la ficha desplegable **Registros a incluir**, seleccione **Filtrar** para abrir el cuadro de diálogo de consulta.</span><span class="sxs-lookup"><span data-stu-id="74a3e-241">On the **Records to include** FastTab, select **Filter** to open the query dialog box.</span></span>
1. <span data-ttu-id="74a3e-242">En la pestaña **Rango**, seleccione **Añadir** para agregar una fila que tenga la siguiente configuración a la cuadrícula:</span><span class="sxs-lookup"><span data-stu-id="74a3e-242">On the **Range** tab, select **Add** to add a row that has the following settings to the grid:</span></span>

    - <span data-ttu-id="74a3e-243">**Tabla:** *Pedido de ventas*</span><span class="sxs-lookup"><span data-stu-id="74a3e-243">**Table:** *Sales order*</span></span>
    - <span data-ttu-id="74a3e-244">**Tabla derivada:** *Pedido de ventas*</span><span class="sxs-lookup"><span data-stu-id="74a3e-244">**Derived table:** *Sales order*</span></span>
    - <span data-ttu-id="74a3e-245">**Campo:** *Pedido de ventas*</span><span class="sxs-lookup"><span data-stu-id="74a3e-245">**Field:** *Sales order*</span></span>
    - <span data-ttu-id="74a3e-246">**Criterio:** Introduzca una lista separada por comas de los números de pedido de ventas del conjunto de pedidos deseado.</span><span class="sxs-lookup"><span data-stu-id="74a3e-246">**Criteria:** Enter a comma-separated list of the sales order numbers from the desired order set.</span></span>

1. <span data-ttu-id="74a3e-247">Seleccione **Aceptar** para guardar su consulta.</span><span class="sxs-lookup"><span data-stu-id="74a3e-247">Select **OK** to save your query.</span></span>
1. <span data-ttu-id="74a3e-248">Seleccione **Aceptar** para comenzar el procedimiento *Despacho automático al almacén*.</span><span class="sxs-lookup"><span data-stu-id="74a3e-248">Select **OK** to start the *Automatic release to warehouse* procedure.</span></span>

#### <a name="review-the-shipment-that-is-created-or-updated"></a><span data-ttu-id="74a3e-249">Revise el envío que se crea o actualiza</span><span class="sxs-lookup"><span data-stu-id="74a3e-249">Review the shipment that is created or updated</span></span>

1. <span data-ttu-id="74a3e-250">Vaya a **Gestión de almacenes \> Envíos \> Todos los envíos**.</span><span class="sxs-lookup"><span data-stu-id="74a3e-250">Go to **Warehouse management \> Shipments \> All shipments**.</span></span>
1. <span data-ttu-id="74a3e-251">Encuentre y seleccione el envío requerido.</span><span class="sxs-lookup"><span data-stu-id="74a3e-251">Find and select the required shipment.</span></span>
1. <span data-ttu-id="74a3e-252">Si se utilizó una directiva de consolidación cuando se creó o actualizó el envío, debería verla en el campo **Directiva de consolidación de envío**.</span><span class="sxs-lookup"><span data-stu-id="74a3e-252">If a consolidation policy was used when the shipment was created or updated, you should see it in the **Shipment consolidation policy** field.</span></span>

### <a name="release-sales-orders-from-order-set-1"></a><span data-ttu-id="74a3e-253">Despachar pedidos de ventas del conjunto de pedidos 1</span><span class="sxs-lookup"><span data-stu-id="74a3e-253">Release sales orders from order set 1</span></span>

<span data-ttu-id="74a3e-254">Siga el [procedimiento básico de despacho al almacén](#release-procedure) para despachar los pedidos de ventas del conjunto de pedidos 1.</span><span class="sxs-lookup"><span data-stu-id="74a3e-254">Follow the [basic release-to-warehouse procedure](#release-procedure) to release the sales orders from order set 1.</span></span>

<span data-ttu-id="74a3e-255">Cuando haya terminado, debería ver que se han creado dos envíos:</span><span class="sxs-lookup"><span data-stu-id="74a3e-255">When you've finished, you should see that two shipments were created:</span></span>

- <span data-ttu-id="74a3e-256">El primer envío contiene tres líneas y se creó utilizando la directiva de consolidación de envíos *CustomerMode*.</span><span class="sxs-lookup"><span data-stu-id="74a3e-256">The first shipment contains three lines and was created by using the *CustomerMode* shipment consolidation policy.</span></span>
- <span data-ttu-id="74a3e-257">El segundo envío, que no utiliza el modo de transporte de entrega *Vías aéreas*, se creó usando la directiva de consolidación de envíos *CustomerOrderNo*.</span><span class="sxs-lookup"><span data-stu-id="74a3e-257">The second shipment, which doesn't use the *Airways* transportation mode of delivery, was created by using the *CustomerOrderNo* shipment consolidation policy.</span></span>

### <a name="release-sales-orders-from-order-set-2"></a><span data-ttu-id="74a3e-258">Despachar pedidos de ventas del conjunto de pedidos 2</span><span class="sxs-lookup"><span data-stu-id="74a3e-258">Release sales orders from order set 2</span></span>

<span data-ttu-id="74a3e-259">Siga el [procedimiento básico de despacho al almacén](#release-procedure) para despachar los pedidos de ventas del conjunto de pedidos 2.</span><span class="sxs-lookup"><span data-stu-id="74a3e-259">Follow the [basic release-to-warehouse procedure](#release-procedure) to release the sales orders from order set 2.</span></span>

<span data-ttu-id="74a3e-260">Cuando haya terminado, debería ver que se han creado tres envíos:</span><span class="sxs-lookup"><span data-stu-id="74a3e-260">When you've finished, you should see that three shipments were created:</span></span>

- <span data-ttu-id="74a3e-261">El primer envío contiene artículos *Inflamables*.</span><span class="sxs-lookup"><span data-stu-id="74a3e-261">The first shipment contains *Flammable* items.</span></span>
- <span data-ttu-id="74a3e-262">Cada uno de los otros dos envíos contiene una línea que tiene el artículo *Explosivo*.</span><span class="sxs-lookup"><span data-stu-id="74a3e-262">Each of the other two shipments contains one line that has the *Explosive* item.</span></span>

### <a name="release-sales-orders-from-order-set-3"></a><span data-ttu-id="74a3e-263">Despachar pedidos de ventas del conjunto de pedidos 3</span><span class="sxs-lookup"><span data-stu-id="74a3e-263">Release sales orders from order set 3</span></span>

<span data-ttu-id="74a3e-264">Siga el [procedimiento básico de despacho al almacén](#release-procedure) para despachar los pedidos de ventas del conjunto de pedidos 3.</span><span class="sxs-lookup"><span data-stu-id="74a3e-264">Follow the [basic release-to-warehouse procedure](#release-procedure) to release the sales orders from order set 3.</span></span>

<span data-ttu-id="74a3e-265">Cuando haya terminado, debería ver que han tenido lugar las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="74a3e-265">When you've finished, you should see that the following actions occurred:</span></span>

- <span data-ttu-id="74a3e-266">Se actualizó un envío existente (el envío que se creó cuando el conjunto de pedidos 2 se despachó al almacén).</span><span class="sxs-lookup"><span data-stu-id="74a3e-266">One existing shipment (the shipment that was created when order set 2 was released to the warehouse) was updated.</span></span> <span data-ttu-id="74a3e-267">Se ha agregado una línea que tiene el artículo *Inflamable*.</span><span class="sxs-lookup"><span data-stu-id="74a3e-267">A line that has the *Flammable* item was added.</span></span>
- <span data-ttu-id="74a3e-268">Se ha creado un nuevo envío que contiene el artículo *Explosivo*.</span><span class="sxs-lookup"><span data-stu-id="74a3e-268">One new shipment was created that contains the *Explosive* item.</span></span>

### <a name="release-sales-orders-from-order-set-4"></a><span data-ttu-id="74a3e-269">Despachar pedidos de ventas del conjunto de pedidos 4</span><span class="sxs-lookup"><span data-stu-id="74a3e-269">Release sales orders from order set 4</span></span>

<span data-ttu-id="74a3e-270">Siga el [procedimiento básico de despacho al almacén](#release-procedure) para despachar los pedidos de ventas del conjunto de pedidos 4.</span><span class="sxs-lookup"><span data-stu-id="74a3e-270">Follow the [basic release-to-warehouse procedure](#release-procedure) to release the sales orders from order set 4.</span></span>

<span data-ttu-id="74a3e-271">Cuando haya terminado, debería ver cómo ese envío existente (donde el campo **Solicitud del cliente** está establecido en *1*) se ha actualizado.</span><span class="sxs-lookup"><span data-stu-id="74a3e-271">When you've finished, you should see that one existing shipment (where the **Customer requisition** field is set to *1*) was updated.</span></span> <span data-ttu-id="74a3e-272">Se le ha agregado una nueva línea.</span><span class="sxs-lookup"><span data-stu-id="74a3e-272">One new line was added to it.</span></span>

### <a name="release-sales-orders-from-order-set-5"></a><span data-ttu-id="74a3e-273">Despachar pedidos de ventas del conjunto de pedidos 5</span><span class="sxs-lookup"><span data-stu-id="74a3e-273">Release sales orders from order set 5</span></span>

<span data-ttu-id="74a3e-274">Siga el [procedimiento básico de despacho al almacén](#release-procedure) para despachar los pedidos de ventas del conjunto de pedidos 5.</span><span class="sxs-lookup"><span data-stu-id="74a3e-274">Follow the [basic release-to-warehouse procedure](#release-procedure) to release the sales orders from order set 5.</span></span>

<span data-ttu-id="74a3e-275">Cuando haya terminado, debería ver que han tenido lugar las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="74a3e-275">When you've finished, you should see that the following actions occurred:</span></span>

- <span data-ttu-id="74a3e-276">Se ha actualizado un envío existente (donde el campo **Solicitud del cliente** está establecido n *1*).</span><span class="sxs-lookup"><span data-stu-id="74a3e-276">One existing shipment (where the **Customer requisition** field is set to *1*) was updated.</span></span> <span data-ttu-id="74a3e-277">Se ha agregado una línea del pedido de ventas 5-3 (donde el campo **Solicitud del cliente** está establecido en *1*).</span><span class="sxs-lookup"><span data-stu-id="74a3e-277">A line from sales order 5-3 (where the **Customer requisition** field is set to *1*) was added to it.</span></span>
- <span data-ttu-id="74a3e-278">Se ha creado un nuevo envío, donde las líneas de los pedidos de ventas 5-1 y 5-2 se agrupan en un único envío.</span><span class="sxs-lookup"><span data-stu-id="74a3e-278">One new shipment was created, where lines from sales orders 5-1 and 5-2 are grouped into one shipment.</span></span>

### <a name="release-sales-orders-from-order-set-6"></a><span data-ttu-id="74a3e-279">Despachar pedidos de ventas del conjunto de pedidos 6</span><span class="sxs-lookup"><span data-stu-id="74a3e-279">Release sales orders from order set 6</span></span>

<span data-ttu-id="74a3e-280">Siga el [procedimiento básico de despacho al almacén](#release-procedure) para despachar los pedidos de ventas del conjunto de pedidos 6.</span><span class="sxs-lookup"><span data-stu-id="74a3e-280">Follow the [basic release-to-warehouse procedure](#release-procedure) to release the sales orders from order set 6.</span></span>

<span data-ttu-id="74a3e-281">Cuando haya terminado, debería ver que se han creado cuatro envíos:</span><span class="sxs-lookup"><span data-stu-id="74a3e-281">When you've finished, you should see that four shipments were created:</span></span>

- <span data-ttu-id="74a3e-282">Las líneas de dos pedidos del cliente *US-003* se han agrupado en un envío, utilizando la directiva de consolidación de envíos *Grupo de pedidos*.</span><span class="sxs-lookup"><span data-stu-id="74a3e-282">Lines from two orders for customer *US-003* were grouped into one shipment by using the *Order pool* shipment consolidation policy.</span></span>
- <span data-ttu-id="74a3e-283">Las líneas de dos pedidos del cliente *US-004* se han agrupado en un envío, utilizando la directiva de consolidación de envíos *Grupo de pedidos*.</span><span class="sxs-lookup"><span data-stu-id="74a3e-283">Lines from two orders for customer *US-004* were grouped into one shipment by using the *Order pool* shipment consolidation policy.</span></span>
- <span data-ttu-id="74a3e-284">Las líneas de pedido de ventas 6-5 y 6-6 para clientes *US-007* se han agrupado en un envío, utilizando la directiva de consolidación de envíos *Grupo de pedidos*.</span><span class="sxs-lookup"><span data-stu-id="74a3e-284">Lines from sales orders 6-5 and 6-6 for customer *US-007* were grouped into one shipment by using the *Order pool* shipment consolidation policy.</span></span>
- <span data-ttu-id="74a3e-285">Las líneas de pedido de ventas 6-7 y 6-8 para clientes *US-007* se han agrupado en un envío, utilizando la directiva de consolidación de envíos *CrossOrder*.</span><span class="sxs-lookup"><span data-stu-id="74a3e-285">Lines from sales orders 6-7 and 6-8 for customer *US-007* were grouped into one shipment by using the *CrossOrder* shipment consolidation policy.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="74a3e-286">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="74a3e-286">Additional resources</span></span>

- [<span data-ttu-id="74a3e-287">Directivas de consolidación de envíos</span><span class="sxs-lookup"><span data-stu-id="74a3e-287">Shipment consolidation policies</span></span>](about-shipment-consolidation-policies.md)
- [<span data-ttu-id="74a3e-288">Configurar directivas de consolidación de envíos</span><span class="sxs-lookup"><span data-stu-id="74a3e-288">Configure shipment consolidation policies</span></span>](configure-shipment-consolidation-policies.md)
