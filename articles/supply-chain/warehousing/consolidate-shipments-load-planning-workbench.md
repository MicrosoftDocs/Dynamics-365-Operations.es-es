---
title: Consolidar los envíos utilizando Despachar al almacén desde área de trabajo de planificación de la carga
description: Este tema presenta un escenario en el que se despachan múltiples pedidos al almacén en la misma carga y luego se consolidan automatizadamente en envíos.
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
ms.openlocfilehash: 2f1dd5c743664e638c043b600ae7b0f6bce5ddcd
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4436617"
---
# <a name="consolidate-shipments-by-using-release-to-warehouse-from-the-load-planning-workbench"></a><span data-ttu-id="312e2-103">Consolidar los envíos utilizando Despachar al almacén desde área de trabajo de planificación de la carga</span><span class="sxs-lookup"><span data-stu-id="312e2-103">Consolidate shipments by using Release to warehouse from the load planning workbench</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="312e2-104">Este tema presenta un escenario en el que se despachan múltiples pedidos al almacén en la misma carga y luego se consolidan automatizadamente en envíos.</span><span class="sxs-lookup"><span data-stu-id="312e2-104">This topic presents a scenario where multiple orders are released to the warehouse in the same load and are then automatically consolidated into shipments.</span></span>

## <a name="make-demo-data-available"></a><span data-ttu-id="312e2-105">Hacer que los datos de demostración estén disponibles</span><span class="sxs-lookup"><span data-stu-id="312e2-105">Make demo data available</span></span>

<span data-ttu-id="312e2-106">El escenario de este tema hace referencia a valores y registros que se incluyen en los datos de demostración estándar que se proporcionan para Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="312e2-106">The scenario in this topic references values and records that are included in the standard demo data that is provided for Microsoft Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="312e2-107">Si desea utilizar los valores que se proporcionan aquí mientras realiza los ejercicios, asegúrese de trabajar en un entorno donde estén instalados los datos de demostración y configure la entidad jurídica en **USMF** antes de empezar.</span><span class="sxs-lookup"><span data-stu-id="312e2-107">If you want to use the values that are provided here as you do the exercises, be sure to work in an environment where the demo data is installed, and set the legal entity to **USMF** before you begin.</span></span>

## <a name="set-up-shipment-consolidation-policies-and-product-filters"></a><span data-ttu-id="312e2-108">Configurar directivas de consolidación de envíos y filtros de productos</span><span class="sxs-lookup"><span data-stu-id="312e2-108">Set up shipment consolidation policies and product filters</span></span>

<span data-ttu-id="312e2-109">El escenario que se describe aquí supone que ya ha activado la función, realizado los ejercicios de [Configurar directivas de consolidación de envíos](configure-shipment-consolidation-policies.md) y creado las directivas y otros registros que se describen allí.</span><span class="sxs-lookup"><span data-stu-id="312e2-109">The scenario that is described here assumes that you've already turned on the feature, done the exercises in [Configure shipment consolidation policies](configure-shipment-consolidation-policies.md), and created the policies and other records that are described there.</span></span> <span data-ttu-id="312e2-110">Asegúrese de hacer esos ejercicios antes de continuar con este escenario.</span><span class="sxs-lookup"><span data-stu-id="312e2-110">Be sure to do those exercises before you continue with this scenario.</span></span>

## <a name="create-the-sales-orders-for-this-scenario"></a><span data-ttu-id="312e2-111">Crear los pedidos de ventas para este escenario</span><span class="sxs-lookup"><span data-stu-id="312e2-111">Create the sales orders for this scenario</span></span>

<span data-ttu-id="312e2-112">Comience creando una colección de pedidos de ventas con los que pueda trabajar.</span><span class="sxs-lookup"><span data-stu-id="312e2-112">Start by creating a collection of sales orders that you can work with.</span></span> <span data-ttu-id="312e2-113">Debe trabajar con un almacén habilitado para procesos de almacén avanzado (WMS).</span><span class="sxs-lookup"><span data-stu-id="312e2-113">You must work with a warehouse that is enabled for advanced warehouse (WMS) processes.</span></span> <span data-ttu-id="312e2-114">A menos que se mencione explícitamente un almacén diferente, ese mismo almacén debe utilizarse para cada uno de los siguientes conjuntos de pedidos.</span><span class="sxs-lookup"><span data-stu-id="312e2-114">Unless a different warehouse is explicitly mentioned, that same warehouse must be used for each of the following sets of orders.</span></span>

<span data-ttu-id="312e2-115">Vaya a **Clientes \> Pedidos \> Todos los pedidos de ventas** y cree una colección de pedidos de ventas que tengan la configuración que se describe en las siguientes subsecciones.</span><span class="sxs-lookup"><span data-stu-id="312e2-115">Go to **Accounts receivable \> Orders \> All sales orders**, and create a collection of sales orders that have the settings that are described in the following subsections.</span></span>

### <a name="create-order-set-1"></a><span data-ttu-id="312e2-116">Crear conjunto de pedidos 1</span><span class="sxs-lookup"><span data-stu-id="312e2-116">Create order set 1</span></span>

#### <a name="sales-order-1-1"></a><span data-ttu-id="312e2-117">Pedido de ventas 1-1</span><span class="sxs-lookup"><span data-stu-id="312e2-117">Sales order 1-1</span></span>

1. <span data-ttu-id="312e2-118">Cree un pedido de ventas con la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="312e2-118">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="312e2-119">**Cuenta de cliente:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="312e2-119">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="312e2-120">**Modo de entrega:** *Airwa-Air*</span><span class="sxs-lookup"><span data-stu-id="312e2-120">**Mode of delivery:** *Airwa-Air*</span></span>

1. <span data-ttu-id="312e2-121">Agregue una línea de pedido que tenga la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="312e2-121">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="312e2-122">**Número de artículo:** *A0001* (un artículo al que no se ha asignado el filtro **Código 4**)</span><span class="sxs-lookup"><span data-stu-id="312e2-122">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="312e2-123">**Cantidad:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="312e2-123">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="312e2-124">Seleccione **Inventario \> Reserva** y luego, en el Panel de acciones, seleccione **Reservar lote interno** para reservar la línea de pedido.</span><span class="sxs-lookup"><span data-stu-id="312e2-124">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

#### <a name="sales-order-1-2"></a><span data-ttu-id="312e2-125">Pedido de ventas 1-2</span><span class="sxs-lookup"><span data-stu-id="312e2-125">Sales order 1-2</span></span>

1. <span data-ttu-id="312e2-126">Cree un pedido de ventas con la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="312e2-126">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="312e2-127">**Cuenta de cliente:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="312e2-127">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="312e2-128">**Modo de entrega:** *Airwa-Air*</span><span class="sxs-lookup"><span data-stu-id="312e2-128">**Mode of delivery:** *Airwa-Air*</span></span>

1. <span data-ttu-id="312e2-129">Agregue una línea de pedido que tenga la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="312e2-129">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="312e2-130">**Número de artículo:** *A0001* (un artículo al que no se ha asignado el filtro **Código 4**)</span><span class="sxs-lookup"><span data-stu-id="312e2-130">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="312e2-131">**Cantidad:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="312e2-131">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="312e2-132">Seleccione **Inventario \> Reserva** y luego, en el Panel de acciones, seleccione **Reservar lote interno** para reservar la línea de pedido.</span><span class="sxs-lookup"><span data-stu-id="312e2-132">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

#### <a name="sales-order-1-3"></a><span data-ttu-id="312e2-133">Pedido de ventas 1-3</span><span class="sxs-lookup"><span data-stu-id="312e2-133">Sales order 1-3</span></span>

1. <span data-ttu-id="312e2-134">Cree un pedido de ventas con la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="312e2-134">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="312e2-135">**Cuenta de cliente:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="312e2-135">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="312e2-136">**Modo de entrega:** *10*</span><span class="sxs-lookup"><span data-stu-id="312e2-136">**Mode of delivery:** *10*</span></span>

1. <span data-ttu-id="312e2-137">Agregue una línea de pedido que tenga la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="312e2-137">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="312e2-138">**Número de artículo:** *A0001* (un artículo al que no se ha asignado el filtro **Código 4**)</span><span class="sxs-lookup"><span data-stu-id="312e2-138">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="312e2-139">**Cantidad:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="312e2-139">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="312e2-140">Seleccione **Inventario \> Reserva** y luego, en el Panel de acciones, seleccione **Reservar lote interno** para reservar la línea de pedido.</span><span class="sxs-lookup"><span data-stu-id="312e2-140">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>
1. <span data-ttu-id="312e2-141">Agregue un segundo pedido que tenga la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="312e2-141">Add a second order line that has the following settings:</span></span>

    - <span data-ttu-id="312e2-142">**Número de artículo:** *A0002* (un artículo al que no se ha asignado el filtro **Código 4**)</span><span class="sxs-lookup"><span data-stu-id="312e2-142">**Item number:** *A0002* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="312e2-143">**Cantidad:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="312e2-143">**Quantity:** *1.00*</span></span>
    - <span data-ttu-id="312e2-144">**Modo de entrega:** *Airwa-Air*</span><span class="sxs-lookup"><span data-stu-id="312e2-144">**Mode of delivery:** *Airwa-Air*</span></span>

1. <span data-ttu-id="312e2-145">Seleccione **Inventario \> Reserva** y luego, en el Panel de acciones, seleccione **Reservar lote interno** para reservar la segunda línea de pedido.</span><span class="sxs-lookup"><span data-stu-id="312e2-145">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the second order line.</span></span>

### <a name="create-order-set-2"></a><span data-ttu-id="312e2-146">Crear conjunto de pedidos 2</span><span class="sxs-lookup"><span data-stu-id="312e2-146">Create order set 2</span></span>

#### <a name="sales-orders-2-1-and-2-2"></a><span data-ttu-id="312e2-147">Pedidos de ventas 2-1 y 2-2</span><span class="sxs-lookup"><span data-stu-id="312e2-147">Sales orders 2-1 and 2-2</span></span>

1. <span data-ttu-id="312e2-148">Cree dos pedidos de venta idénticos que tengan la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="312e2-148">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="312e2-149">**Cuenta de cliente:** *US-002*</span><span class="sxs-lookup"><span data-stu-id="312e2-149">**Customer account:** *US-002*</span></span>

1. <span data-ttu-id="312e2-150">Agregue una línea de pedido que tenga la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="312e2-150">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="312e2-151">**Número de artículo:** *M9200* (un artículo donde el filtro **Código 4** está establecido en *Inflamable*)</span><span class="sxs-lookup"><span data-stu-id="312e2-151">**Item number:** *M9200* (an item where the **Code 4** filter is set to *Flammable*)</span></span>
    - <span data-ttu-id="312e2-152">**Cantidad:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="312e2-152">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="312e2-153">Seleccione **Inventario \> Reserva** y luego, en el Panel de acciones, seleccione **Reservar lote interno** para reservar la línea de pedido.</span><span class="sxs-lookup"><span data-stu-id="312e2-153">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>
1. <span data-ttu-id="312e2-154">Agregue un segundo pedido que tenga la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="312e2-154">Add a second order line that has the following settings:</span></span>

    - <span data-ttu-id="312e2-155">**Número de artículo:** *M9201* (un artículo donde el filtro **Código 4** está establecido en *Explosivo*)</span><span class="sxs-lookup"><span data-stu-id="312e2-155">**Item number:** *M9201* (an item where the **Code 4** filter is set to *Explosive*)</span></span>
    - <span data-ttu-id="312e2-156">**Cantidad:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="312e2-156">**Quantity:** *1.00*</span></span>
    - <span data-ttu-id="312e2-157">**Modo de entrega:** *Airwa-Air*</span><span class="sxs-lookup"><span data-stu-id="312e2-157">**Mode of delivery:** *Airwa-Air*</span></span>

1. <span data-ttu-id="312e2-158">Seleccione **Inventario \> Reserva** y luego, en el Panel de acciones, seleccione **Reservar lote interno** para reservar la segunda línea de pedido.</span><span class="sxs-lookup"><span data-stu-id="312e2-158">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the second order line.</span></span>

### <a name="create-order-set-3"></a><span data-ttu-id="312e2-159">Crear conjunto de pedidos 3</span><span class="sxs-lookup"><span data-stu-id="312e2-159">Create order set 3</span></span>

#### <a name="sales-orders-3-1-and-3-2"></a><span data-ttu-id="312e2-160">Pedidos de ventas 3-1 y 3-2</span><span class="sxs-lookup"><span data-stu-id="312e2-160">Sales orders 3-1 and 3-2</span></span>

1. <span data-ttu-id="312e2-161">Cree dos pedidos de venta idénticos que tengan la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="312e2-161">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="312e2-162">**Cuenta de cliente:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="312e2-162">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="312e2-163">**Solicitud de cliente:** *1*</span><span class="sxs-lookup"><span data-stu-id="312e2-163">**Customer requisition:** *1*</span></span>

1. <span data-ttu-id="312e2-164">Agregue una línea de pedido que tenga la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="312e2-164">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="312e2-165">**Número de artículo:** *A0001* (un artículo al que no se ha asignado el filtro **Código 4**)</span><span class="sxs-lookup"><span data-stu-id="312e2-165">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="312e2-166">**Cantidad:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="312e2-166">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="312e2-167">Seleccione **Inventario \> Reserva** y luego, en el Panel de acciones, seleccione **Reservar lote interno** para reservar la línea de pedido.</span><span class="sxs-lookup"><span data-stu-id="312e2-167">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

#### <a name="sales-orders-3-3-and-3-4"></a><span data-ttu-id="312e2-168">Pedidos de ventas 3-3 y 3-4</span><span class="sxs-lookup"><span data-stu-id="312e2-168">Sales orders 3-3 and 3-4</span></span>

1. <span data-ttu-id="312e2-169">Cree dos pedidos de venta idénticos que tengan la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="312e2-169">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="312e2-170">**Cuenta de cliente:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="312e2-170">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="312e2-171">**Solicitud de cliente:** *2*</span><span class="sxs-lookup"><span data-stu-id="312e2-171">**Customer requisition:** *2*</span></span>

1. <span data-ttu-id="312e2-172">Agregue una línea de pedido que tenga la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="312e2-172">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="312e2-173">**Número de artículo:** *A0001* (un artículo al que no se ha asignado el filtro **Código 4**)</span><span class="sxs-lookup"><span data-stu-id="312e2-173">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="312e2-174">**Cantidad:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="312e2-174">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="312e2-175">Seleccione **Inventario \> Reserva** y luego, en el Panel de acciones, seleccione **Reservar lote interno** para reservar la línea de pedido.</span><span class="sxs-lookup"><span data-stu-id="312e2-175">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

### <a name="create-order-set-4"></a><span data-ttu-id="312e2-176">Crear conjunto de pedidos 4</span><span class="sxs-lookup"><span data-stu-id="312e2-176">Create order set 4</span></span>

#### <a name="sales-orders-4-1-and-4-2"></a><span data-ttu-id="312e2-177">Pedidos de ventas 4-1 y 4-2</span><span class="sxs-lookup"><span data-stu-id="312e2-177">Sales orders 4-1 and 4-2</span></span>

1. <span data-ttu-id="312e2-178">Cree dos pedidos de venta idénticos que tengan la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="312e2-178">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="312e2-179">**Cuenta de cliente:** *US-003*</span><span class="sxs-lookup"><span data-stu-id="312e2-179">**Customer account:** *US-003*</span></span>

1. <span data-ttu-id="312e2-180">Agregue una línea de pedido que tenga la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="312e2-180">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="312e2-181">**Número de artículo:** *A0001* (un artículo al que no se ha asignado el filtro **Código 4**)</span><span class="sxs-lookup"><span data-stu-id="312e2-181">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="312e2-182">**Cantidad:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="312e2-182">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="312e2-183">Seleccione **Inventario \> Reserva** y luego, en el Panel de acciones, seleccione **Reservar lote interno** para reservar la línea de pedido.</span><span class="sxs-lookup"><span data-stu-id="312e2-183">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

#### <a name="sales-orders-4-3-and-4-4"></a><span data-ttu-id="312e2-184">Pedidos de ventas 4-3 y 4-4</span><span class="sxs-lookup"><span data-stu-id="312e2-184">Sales orders 4-3 and 4-4</span></span>

1. <span data-ttu-id="312e2-185">Cree dos pedidos de venta idénticos que tengan la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="312e2-185">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="312e2-186">**Cuenta de cliente:** *US-004*</span><span class="sxs-lookup"><span data-stu-id="312e2-186">**Customer account:** *US-004*</span></span>

1. <span data-ttu-id="312e2-187">Agregue una línea de pedido que tenga la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="312e2-187">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="312e2-188">**Número de artículo:** *A0001* (un artículo al que no se ha asignado el filtro **Código 4**)</span><span class="sxs-lookup"><span data-stu-id="312e2-188">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="312e2-189">**Cantidad:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="312e2-189">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="312e2-190">Seleccione **Inventario \> Reserva** y luego, en el Panel de acciones, seleccione **Reservar lote interno** para reservar la línea de pedido.</span><span class="sxs-lookup"><span data-stu-id="312e2-190">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

#### <a name="sales-orders-4-5-and-4-6"></a><span data-ttu-id="312e2-191">Pedidos de ventas 4-5 y 4-6</span><span class="sxs-lookup"><span data-stu-id="312e2-191">Sales orders 4-5 and 4-6</span></span>

1. <span data-ttu-id="312e2-192">Cree dos pedidos de venta idénticos que tengan la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="312e2-192">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="312e2-193">**Cuenta de cliente:** *US-007*</span><span class="sxs-lookup"><span data-stu-id="312e2-193">**Customer account:** *US-007*</span></span>
    - <span data-ttu-id="312e2-194">**Sitio**: *6*</span><span class="sxs-lookup"><span data-stu-id="312e2-194">**Site:** *6*</span></span>
    - <span data-ttu-id="312e2-195">**Almacén**: *61*</span><span class="sxs-lookup"><span data-stu-id="312e2-195">**Warehouse:** *61*</span></span>
    - <span data-ttu-id="312e2-196">**Grupo:** *ShipCons*</span><span class="sxs-lookup"><span data-stu-id="312e2-196">**Pool:** *ShipCons*</span></span>

1. <span data-ttu-id="312e2-197">Agregue una línea de pedido que tenga la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="312e2-197">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="312e2-198">**Número de artículo:** *A0001* (un artículo al que no se ha asignado el filtro **Código 4**)</span><span class="sxs-lookup"><span data-stu-id="312e2-198">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="312e2-199">**Cantidad:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="312e2-199">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="312e2-200">Seleccione **Inventario \> Reserva** y luego, en el Panel de acciones, seleccione **Reservar lote interno** para reservar la línea de pedido.</span><span class="sxs-lookup"><span data-stu-id="312e2-200">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

#### <a name="sales-orders-4-7-and-4-8"></a><span data-ttu-id="312e2-201">Pedidos de ventas 4-7 y 4-8</span><span class="sxs-lookup"><span data-stu-id="312e2-201">Sales orders 4-7 and 4-8</span></span>

1. <span data-ttu-id="312e2-202">Cree dos pedidos de venta idénticos que tengan la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="312e2-202">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="312e2-203">**Cuenta de cliente:** *US-007*</span><span class="sxs-lookup"><span data-stu-id="312e2-203">**Customer account:** *US-007*</span></span>
    - <span data-ttu-id="312e2-204">**Sitio**: *6*</span><span class="sxs-lookup"><span data-stu-id="312e2-204">**Site:** *6*</span></span>
    - <span data-ttu-id="312e2-205">**Almacén**: *61*</span><span class="sxs-lookup"><span data-stu-id="312e2-205">**Warehouse:** *61*</span></span>
    - <span data-ttu-id="312e2-206">**Grupo:** Deje este campo en blanco.</span><span class="sxs-lookup"><span data-stu-id="312e2-206">**Pool:** Leave this field blank.</span></span>

1. <span data-ttu-id="312e2-207">Agregue una línea de pedido que tenga la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="312e2-207">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="312e2-208">**Número de artículo:** *A0001* (un artículo al que no se ha asignado el filtro **Código 4**)</span><span class="sxs-lookup"><span data-stu-id="312e2-208">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="312e2-209">**Cantidad:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="312e2-209">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="312e2-210">Seleccione **Inventario \> Reserva** y luego, en el Panel de acciones, seleccione **Reservar lote interno** para reservar la línea de pedido.</span><span class="sxs-lookup"><span data-stu-id="312e2-210">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

## <a name="use-the-load-planning-workbench-to-create-loads-and-release-them-to-the-warehouse"></a><span data-ttu-id="312e2-211">Use el área de trabajo de planificación de la carga para crear cargas y despacharlas al almacén</span><span class="sxs-lookup"><span data-stu-id="312e2-211">Use the load planning workbench to create loads and release them to the warehouse</span></span>

<span data-ttu-id="312e2-212">Siga estos pasos para crear una carga para cada conjunto de pedidos que creó para este escenario y luego despacharlo al almacén.</span><span class="sxs-lookup"><span data-stu-id="312e2-212">Follow these steps to create a load for each order set that you created for this scenario and then release it to the warehouse.</span></span>

1. <span data-ttu-id="312e2-213">Vaya a **Gestión de almacén \> Cargas \> Área de trabajo de planificación de la carga**.</span><span class="sxs-lookup"><span data-stu-id="312e2-213">Go to **Warehouse management \> Loads \> Load planning workbench**.</span></span>
1. <span data-ttu-id="312e2-214">En la pestaña **Líneas de venta**, busque y seleccione todas las líneas de pedido de ventas de uno de los conjuntos de pedidos que creó para este escenario.</span><span class="sxs-lookup"><span data-stu-id="312e2-214">On the **Sales lines** tab, find and select all the sales order lines from one of the order sets that you created for this scenario.</span></span>
1. <span data-ttu-id="312e2-215">En el Panel de acciones, en la pestaña **Oferta y demanda**, seleccione **Añadir \> A nueva carga** para agregar las líneas de pedidos seleccionadas a una nueva carga.</span><span class="sxs-lookup"><span data-stu-id="312e2-215">On the Action Pane, on the **Supply and demand** tab, select **Add \> To new load** to add the selected order lines to a new Load.</span></span>
1. <span data-ttu-id="312e2-216">En el cuadro de diálogo **Cargar asignación de plantilla**, en el campo **Cargar id. de plantilla**, seleccione una plantilla de carga, como *Plantilla de carga estándar*.</span><span class="sxs-lookup"><span data-stu-id="312e2-216">In the **Load template assignment** dialog box, in the **Load template ID** field, select a load template, such as *Stnd Load Template*.</span></span>
1. <span data-ttu-id="312e2-217">Haga clic en **Aceptar** para cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="312e2-217">Select **OK** to close the dialog box.</span></span> 
1. <span data-ttu-id="312e2-218">En la sección **Cargas**, busque y seleccione la carga que acaba de crear.</span><span class="sxs-lookup"><span data-stu-id="312e2-218">In the **Loads** section, find and select the load that you just created.</span></span>
1. <span data-ttu-id="312e2-219">Seleccione **Despachar \> Despachar al almacén** para liberar la carga seleccionada al almacén.</span><span class="sxs-lookup"><span data-stu-id="312e2-219">Select **Release \> Release to warehouse** to release the selected load to the warehouse.</span></span>
1. <span data-ttu-id="312e2-220">Repita este procedimiento para los otros tres conjuntos de pedidos que creó para este escenario.</span><span class="sxs-lookup"><span data-stu-id="312e2-220">Repeat this procedure for the other three order sets that you created for this scenario.</span></span>

## <a name="verify-the-shipments"></a><span data-ttu-id="312e2-221">Verificar los envíos</span><span class="sxs-lookup"><span data-stu-id="312e2-221">Verify the shipments</span></span>

<span data-ttu-id="312e2-222">El siguiente procedimiento le permite verificar los envíos que se han creado o actualizado como resultado de la consolidación de envíos.</span><span class="sxs-lookup"><span data-stu-id="312e2-222">The following procedure lets you verify the shipments that have been created or updated as a result of shipment consolidation.</span></span> <span data-ttu-id="312e2-223">Úselo para revisar cada conjunto de pedidos que creó para este escenario y luego revise las subsecciones siguientes para asegurarse de haber obtenido los resultados esperados.</span><span class="sxs-lookup"><span data-stu-id="312e2-223">Use it to review each order set that you created for this scenario, and then review the subsections that follow to make sure that you've obtained the expected results.</span></span>

1. <span data-ttu-id="312e2-224">Vaya a **Gestión de almacenes \> Envíos \> Todos los envíos**.</span><span class="sxs-lookup"><span data-stu-id="312e2-224">Go to **Warehouse management \> Shipments \> All shipments**.</span></span>
1. <span data-ttu-id="312e2-225">Encuentre y seleccione el envío requerido.</span><span class="sxs-lookup"><span data-stu-id="312e2-225">Find and select the required shipment.</span></span>
1. <span data-ttu-id="312e2-226">Si se utilizó una directiva de consolidación cuando se creó o actualizó el envío, debería verla en el campo **Directiva de consolidación de envío**.</span><span class="sxs-lookup"><span data-stu-id="312e2-226">If a consolidation policy was used when the shipment was created or updated, you should see it in the **Shipment consolidation policy** field.</span></span>

### <a name="release-order-set-1-in-one-load"></a><span data-ttu-id="312e2-227">Orden de despacho de conjunto 1 en una carga</span><span class="sxs-lookup"><span data-stu-id="312e2-227">Release order set 1 in one load</span></span>

<span data-ttu-id="312e2-228">Deben haberse creado dos envíos:</span><span class="sxs-lookup"><span data-stu-id="312e2-228">Two shipments should have been created:</span></span>

- <span data-ttu-id="312e2-229">El primer envío contiene tres líneas y se creó utilizando la directiva de consolidación de envíos *CustomerMode*.</span><span class="sxs-lookup"><span data-stu-id="312e2-229">The first shipment contains three lines and was created by using the *CustomerMode* shipment consolidation policy.</span></span>
- <span data-ttu-id="312e2-230">El segundo envío, que no utiliza el modo de transporte de entrega *Vías aéreas*, se creó usando la directiva de consolidación de envíos *CustomerOrderNo*.</span><span class="sxs-lookup"><span data-stu-id="312e2-230">The second shipment, which doesn't use the *Airways* transportation mode of delivery, was created by using the *CustomerOrderNo* shipment consolidation policy.</span></span>

### <a name="release-order-set-2-in-one-load"></a><span data-ttu-id="312e2-231">Orden de despacho de conjunto 2 en una carga</span><span class="sxs-lookup"><span data-stu-id="312e2-231">Release order set 2 in one load</span></span>

<span data-ttu-id="312e2-232">Deben haberse creado tres envíos:</span><span class="sxs-lookup"><span data-stu-id="312e2-232">Three shipments should have been created:</span></span>

- <span data-ttu-id="312e2-233">El primer envío contiene los artículos *Inflamables*.</span><span class="sxs-lookup"><span data-stu-id="312e2-233">The first shipment contains the *Flammable* items.</span></span>
- <span data-ttu-id="312e2-234">Cada uno de los otros dos envíos contiene una línea que tiene el artículo *Explosivo*.</span><span class="sxs-lookup"><span data-stu-id="312e2-234">Each of the other two shipments contains one line that has the *Explosive* item.</span></span>

### <a name="release-order-set-3-in-one-load"></a><span data-ttu-id="312e2-235">Orden de despacho de conjunto 3 en una carga</span><span class="sxs-lookup"><span data-stu-id="312e2-235">Release order set 3 in one load</span></span>

<span data-ttu-id="312e2-236">Deben haberse creado dos envíos:</span><span class="sxs-lookup"><span data-stu-id="312e2-236">Two shipments should have been created:</span></span>

- <span data-ttu-id="312e2-237">El primer envío contiene líneas de pedido del pedido de ventas donde el campo **Solicitud del cliente** está establecido en *1*.</span><span class="sxs-lookup"><span data-stu-id="312e2-237">The first shipment contains order lines from the sales order where the **Customer requisition** field is set to *1*.</span></span>
- <span data-ttu-id="312e2-238">El segundo envío contiene líneas de pedido del pedido de ventas donde el campo **Solicitud del cliente** está establecido en *2*.</span><span class="sxs-lookup"><span data-stu-id="312e2-238">The second shipment contains order lines from sales order where the **Customer requisition** field is set to *2*.</span></span>

### <a name="release-order-set-4-in-one-load"></a><span data-ttu-id="312e2-239">Orden de despacho de conjunto 4 en una carga</span><span class="sxs-lookup"><span data-stu-id="312e2-239">Release order set 4 in one load</span></span>

<span data-ttu-id="312e2-240">Deben haberse creado cuatro envíos:</span><span class="sxs-lookup"><span data-stu-id="312e2-240">Four shipments should have been created:</span></span>

- <span data-ttu-id="312e2-241">Las líneas de dos pedidos de la cuenta de cliente *US-003* se han agrupado en un envío, utilizando la directiva de consolidación de envíos *Grupo de pedidos*.</span><span class="sxs-lookup"><span data-stu-id="312e2-241">Lines from two orders for customer account *US-003* were grouped into one shipment by using the *Order pool* shipment consolidation policy.</span></span>
- <span data-ttu-id="312e2-242">Las líneas de dos pedidos de la cuenta de cliente *US-004* se han agrupado en un envío, utilizando la directiva de consolidación de envíos *Grupo de pedidos*.</span><span class="sxs-lookup"><span data-stu-id="312e2-242">Lines from two orders for customer account *US-004* were grouped into one shipment by using the *Order pool* shipment consolidation policy.</span></span>
- <span data-ttu-id="312e2-243">Las líneas de los pedidos de ventas 4-5 y 4-6 para la cuenta de cliente *US-007* se han agrupado en un envío, utilizando la directiva de consolidación de envíos *Grupo de pedidos*.</span><span class="sxs-lookup"><span data-stu-id="312e2-243">Lines from sales orders 4-5 and 4-6 for customer account *US-007* were grouped into one shipment by using the *Order pool* shipment consolidation policy.</span></span>
- <span data-ttu-id="312e2-244">Las líneas de los pedidos de ventas 4-7 y 4-8 para la cuenta de cliente *US-007* se han agrupado en un envío, utilizando la directiva de consolidación de envíos *CrossOrder*.</span><span class="sxs-lookup"><span data-stu-id="312e2-244">Lines from sales orders 4-7 and 4-8 for customer account *US-007* were grouped into one shipment by using the *CrossOrder* shipment consolidation policy.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="312e2-245">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="312e2-245">Additional resources</span></span>

- [<span data-ttu-id="312e2-246">Directivas de consolidación de envíos</span><span class="sxs-lookup"><span data-stu-id="312e2-246">Shipment consolidation policies</span></span>](about-shipment-consolidation-policies.md)
- [<span data-ttu-id="312e2-247">Configurar directivas de consolidación de envíos</span><span class="sxs-lookup"><span data-stu-id="312e2-247">Configure shipment consolidation policies</span></span>](configure-shipment-consolidation-policies.md)
