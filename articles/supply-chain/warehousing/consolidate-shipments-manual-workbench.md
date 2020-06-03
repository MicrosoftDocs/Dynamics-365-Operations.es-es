---
title: Consolidar los envíos utilizando el área de trabajo de consolidación de envíos
description: Este tema presenta un escenario en el que se despachan múltiples pedidos al almacén en la misma carga y luego se consolidan en envíos usando el área de trabajo de consolidación de envíos.
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
ms.author: v-olbara
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: b1a2c9506b4444fc98a9e4f0389cbd69db4ce052
ms.sourcegitcommit: 8a2127c5af6cdbda30ccc1f9bef9bd4ab61e9e50
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/18/2020
ms.locfileid: "3383857"
---
# <a name="consolidate-shipments-by-using-the-shipment-consolidation-workbench"></a><span data-ttu-id="394af-103">Consolidar los envíos utilizando el área de trabajo de consolidación de envíos</span><span class="sxs-lookup"><span data-stu-id="394af-103">Consolidate shipments by using the shipment consolidation workbench</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="394af-104">Este tema presenta un escenario en el que se despachan múltiples pedidos al almacén en la misma carga y luego se consolidan en envíos usando el área de trabajo de consolidación de envíos.</span><span class="sxs-lookup"><span data-stu-id="394af-104">This topic presents a scenario where multiple orders are released to the warehouse and then consolidated into shipments later by using the shipment consolidation workbench.</span></span>

## <a name="make-demo-data-available"></a><span data-ttu-id="394af-105">Hacer que los datos de demostración estén disponibles</span><span class="sxs-lookup"><span data-stu-id="394af-105">Make demo data available</span></span>

<span data-ttu-id="394af-106">El escenario de este tema hace referencia a valores y registros que se incluyen en los datos de demostración estándar que se proporcionan para Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="394af-106">The scenario in this topic references values and records that are included in the standard demo data that is provided for Microsoft Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="394af-107">Si desea utilizar los valores que se proporcionan aquí mientras realiza los ejercicios, asegúrese de trabajar en un entorno donde estén instalados los datos de demostración y configure la entidad jurídica en **USMF** antes de empezar.</span><span class="sxs-lookup"><span data-stu-id="394af-107">If you want to use the values that are provided here as you do the exercises, be sure to work in an environment where the demo data is installed, and set the legal entity to **USMF** before you begin.</span></span>

## <a name="set-up-shipment-consolidation-policies-and-product-filters"></a><span data-ttu-id="394af-108">Configurar directivas de consolidación de envíos y filtros de productos</span><span class="sxs-lookup"><span data-stu-id="394af-108">Set up shipment consolidation policies and product filters</span></span>

<span data-ttu-id="394af-109">El escenario que se describe aquí supone que ya ha activado la función, realizado los ejercicios de [Configurar directivas de consolidación de envíos](configure-shipment-consolidation-policies.md) y creado las directivas y otros registros que se describen allí.</span><span class="sxs-lookup"><span data-stu-id="394af-109">The scenario that is described here assumes that you've already turned on the feature, done the exercises in [Configure shipment consolidation policies](configure-shipment-consolidation-policies.md), and created the policies and other records that are described there.</span></span> <span data-ttu-id="394af-110">Asegúrese de hacer esos ejercicios antes de continuar con este escenario.</span><span class="sxs-lookup"><span data-stu-id="394af-110">Be sure to do those exercises before you continue with this scenario.</span></span>

## <a name="turn-on-the-manual-shipment-consolidation-feature"></a><span data-ttu-id="394af-111">Activar la función manual de consolidación de envíos</span><span class="sxs-lookup"><span data-stu-id="394af-111">Turn on the manual shipment consolidation feature</span></span>

<span data-ttu-id="394af-112">Antes de poder usar la función *Consolidación manual de envíos*, debe activarla en su sistema.</span><span class="sxs-lookup"><span data-stu-id="394af-112">Before you can use the *Manual shipment consolidation* feature, you must turn it on in your system.</span></span> <span data-ttu-id="394af-113">Los administradores pueden usar la configuración de [gestión de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de la función y activarla.</span><span class="sxs-lookup"><span data-stu-id="394af-113">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on.</span></span> <span data-ttu-id="394af-114">En el espacio de trabajo **Administración de funciones**, la función aparece de la siguiente forma:</span><span class="sxs-lookup"><span data-stu-id="394af-114">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="394af-115">**Módulo:** *Gestión de almacén*</span><span class="sxs-lookup"><span data-stu-id="394af-115">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="394af-116">**Nombre de función:** *Consolidación manual de envíos*</span><span class="sxs-lookup"><span data-stu-id="394af-116">**Feature name:** *Manual shipment consolidation*</span></span>

<span data-ttu-id="394af-117">Como se mencionó en [Configurar directivas de consolidación de envíos](configure-shipment-consolidation-policies.md), también debe activar la función *Consolidar envío* antes de poder crear directivas.</span><span class="sxs-lookup"><span data-stu-id="394af-117">As was mentioned in [Configure shipment consolidation policies](configure-shipment-consolidation-policies.md), you must also turn on the *Consolidate shipment* feature before you can create policies.</span></span> <span data-ttu-id="394af-118">Sin embargo, ya debería haber completado ese paso.</span><span class="sxs-lookup"><span data-stu-id="394af-118">However, you should already have completed that step.</span></span>

## <a name="create-the-sales-orders-for-this-scenario"></a><span data-ttu-id="394af-119">Crear los pedidos de ventas para este escenario</span><span class="sxs-lookup"><span data-stu-id="394af-119">Create the sales orders for this scenario</span></span>

<span data-ttu-id="394af-120">Comience creando una colección de pedidos de ventas con los que pueda trabajar.</span><span class="sxs-lookup"><span data-stu-id="394af-120">Start by creating a collection of sales orders that you can work with.</span></span> <span data-ttu-id="394af-121">Debe trabajar con un almacén habilitado para procesos de almacén avanzado (WMS).</span><span class="sxs-lookup"><span data-stu-id="394af-121">You must work with a warehouse that is enabled for advanced warehouse (WMS) processes.</span></span> <span data-ttu-id="394af-122">A menos que se mencione explícitamente un almacén diferente, ese mismo almacén debe utilizarse para cada uno de los siguientes conjuntos de pedidos.</span><span class="sxs-lookup"><span data-stu-id="394af-122">Unless a different warehouse is explicitly mentioned, that same warehouse must be used for each of the following sets of orders.</span></span>

<span data-ttu-id="394af-123">Vaya a **Clientes \> Pedidos \> Todos los pedidos de ventas** y cree una colección de pedidos de ventas que tengan la configuración que se describe en las siguientes subsecciones.</span><span class="sxs-lookup"><span data-stu-id="394af-123">Go to **Accounts receivable \> Orders \> All sales orders**, and create a collection of sales orders that have the settings that are described in the following subsections.</span></span>

### <a name="create-order-set-1"></a><span data-ttu-id="394af-124">Crear conjunto de pedidos 1</span><span class="sxs-lookup"><span data-stu-id="394af-124">Create order set 1</span></span>

#### <a name="sales-orders-1-1-and-1-2"></a><span data-ttu-id="394af-125">Pedidos de ventas 1-1 y 1-2</span><span class="sxs-lookup"><span data-stu-id="394af-125">Sales orders 1-1 and 1-2</span></span>

1. <span data-ttu-id="394af-126">Cree dos pedidos de venta idénticos que tengan la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="394af-126">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="394af-127">**Cuenta de cliente:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="394af-127">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="394af-128">**Modo de entrega:** *Airwa-Air*</span><span class="sxs-lookup"><span data-stu-id="394af-128">**Mode of delivery:** *Airwa-Air*</span></span>

1. <span data-ttu-id="394af-129">Agregue una línea de pedido que tenga la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="394af-129">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="394af-130">**Número de artículo:** *A0001* (un artículo al que no se ha asignado el filtro **Código 4**)</span><span class="sxs-lookup"><span data-stu-id="394af-130">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="394af-131">**Cantidad:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="394af-131">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="394af-132">Seleccione **Inventario \> Reserva** y luego, en el Panel de acciones, seleccione **Reservar lote interno** para reservar la línea de pedido.</span><span class="sxs-lookup"><span data-stu-id="394af-132">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

#### <a name="sales-order-1-3"></a><span data-ttu-id="394af-133">Pedido de ventas 1-3</span><span class="sxs-lookup"><span data-stu-id="394af-133">Sales order 1-3</span></span>

1. <span data-ttu-id="394af-134">Cree un pedido de ventas con la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="394af-134">Create a sales order that has the following settings:</span></span>

    - <span data-ttu-id="394af-135">**Cuenta de cliente:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="394af-135">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="394af-136">**Modo de entrega:** *10*</span><span class="sxs-lookup"><span data-stu-id="394af-136">**Mode of delivery:** *10*</span></span>

1. <span data-ttu-id="394af-137">Agregue una línea de pedido que tenga la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="394af-137">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="394af-138">**Número de artículo:** *A0001* (un artículo al que no se ha asignado el filtro **Código 4**)</span><span class="sxs-lookup"><span data-stu-id="394af-138">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="394af-139">**Cantidad:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="394af-139">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="394af-140">Seleccione **Inventario \> Reserva** y luego, en el Panel de acciones, seleccione **Reservar lote interno** para reservar la línea de pedido.</span><span class="sxs-lookup"><span data-stu-id="394af-140">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>
1. <span data-ttu-id="394af-141">Agregue un segundo pedido que tenga la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="394af-141">Add a second order line that has the following settings:</span></span>

    - <span data-ttu-id="394af-142">**Número de artículo:** *A0002* (un artículo al que no se ha asignado el filtro **Código 4**)</span><span class="sxs-lookup"><span data-stu-id="394af-142">**Item number:** *A0002* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="394af-143">**Cantidad:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="394af-143">**Quantity:** *1.00*</span></span>
    - <span data-ttu-id="394af-144">**Modo de entrega:** *Airwa-Air*</span><span class="sxs-lookup"><span data-stu-id="394af-144">**Mode of delivery:** *Airwa-Air*</span></span>

1. <span data-ttu-id="394af-145">Seleccione **Inventario \> Reserva** y luego, en el Panel de acciones, seleccione **Reservar lote interno** para reservar la segunda línea de pedido.</span><span class="sxs-lookup"><span data-stu-id="394af-145">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the second order line.</span></span>

### <a name="create-order-set-2"></a><span data-ttu-id="394af-146">Crear conjunto de pedidos 2</span><span class="sxs-lookup"><span data-stu-id="394af-146">Create order set 2</span></span>

#### <a name="sales-orders-2-1-and-2-2"></a><span data-ttu-id="394af-147">Pedidos de ventas 2-1 y 2-2</span><span class="sxs-lookup"><span data-stu-id="394af-147">Sales orders 2-1 and 2-2</span></span>

1. <span data-ttu-id="394af-148">Cree dos pedidos de venta idénticos que tengan la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="394af-148">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="394af-149">**Cuenta de cliente:** *US-002*</span><span class="sxs-lookup"><span data-stu-id="394af-149">**Customer account:** *US-002*</span></span>
    - <span data-ttu-id="394af-150">**Modo de entrega:** *Airwa-Air*</span><span class="sxs-lookup"><span data-stu-id="394af-150">**Mode of delivery:** *Airwa-Air*</span></span>

1. <span data-ttu-id="394af-151">Agregue una línea de pedido que tenga la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="394af-151">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="394af-152">**Número de artículo:** *M9200* (un artículo donde el filtro **Código 4** está establecido en *Inflamable*)</span><span class="sxs-lookup"><span data-stu-id="394af-152">**Item number:** *M9200* (an item where the **Code 4** filter is set to *Flammable*)</span></span>
    - <span data-ttu-id="394af-153">**Cantidad:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="394af-153">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="394af-154">Seleccione **Inventario \> Reserva** y luego, en el Panel de acciones, seleccione **Reservar lote interno** para reservar la línea de pedido.</span><span class="sxs-lookup"><span data-stu-id="394af-154">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>
1. <span data-ttu-id="394af-155">Agregue un segundo pedido que tenga la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="394af-155">Add a second order line that has the following settings:</span></span>

    - <span data-ttu-id="394af-156">**Número de artículo:** *M9201* (un artículo donde el filtro **Código 4** está establecido en *Explosivo*)</span><span class="sxs-lookup"><span data-stu-id="394af-156">**Item number:** *M9201* (an item where the **Code 4** filter is set to *Explosive*)</span></span>
    - <span data-ttu-id="394af-157">**Cantidad:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="394af-157">**Quantity:** *1.00*</span></span>
    - <span data-ttu-id="394af-158">**Modo de entrega:** *Airwa-Air*</span><span class="sxs-lookup"><span data-stu-id="394af-158">**Mode of delivery:** *Airwa-Air*</span></span>

1. <span data-ttu-id="394af-159">Seleccione **Inventario \> Reserva** y luego, en el Panel de acciones, seleccione **Reservar lote interno** para reservar la segunda línea de pedido.</span><span class="sxs-lookup"><span data-stu-id="394af-159">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the second order line.</span></span>

### <a name="create-order-set-3"></a><span data-ttu-id="394af-160">Crear conjunto de pedidos 3</span><span class="sxs-lookup"><span data-stu-id="394af-160">Create order set 3</span></span>

#### <a name="sales-orders-3-1-and-3-2"></a><span data-ttu-id="394af-161">Pedidos de ventas 3-1 y 3-2</span><span class="sxs-lookup"><span data-stu-id="394af-161">Sales orders 3-1 and 3-2</span></span>

1. <span data-ttu-id="394af-162">Cree dos pedidos de venta idénticos que tengan la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="394af-162">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="394af-163">**Cuenta de cliente:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="394af-163">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="394af-164">**Solicitud de cliente:** *1*</span><span class="sxs-lookup"><span data-stu-id="394af-164">**Customer requisition:** *1*</span></span>

1. <span data-ttu-id="394af-165">Agregue una línea de pedido que tenga la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="394af-165">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="394af-166">**Número de artículo:** *A0001* (un artículo al que no se ha asignado el filtro **Código 4**)</span><span class="sxs-lookup"><span data-stu-id="394af-166">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="394af-167">**Cantidad:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="394af-167">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="394af-168">Seleccione **Inventario \> Reserva** y luego, en el Panel de acciones, seleccione **Reservar lote interno** para reservar la línea de pedido.</span><span class="sxs-lookup"><span data-stu-id="394af-168">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

#### <a name="sales-orders-3-3-and-3-4"></a><span data-ttu-id="394af-169">Pedidos de ventas 3-3 y 3-4</span><span class="sxs-lookup"><span data-stu-id="394af-169">Sales orders 3-3 and 3-4</span></span>

1. <span data-ttu-id="394af-170">Cree dos pedidos de venta idénticos que tengan la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="394af-170">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="394af-171">**Cuenta de cliente:** *US-001*</span><span class="sxs-lookup"><span data-stu-id="394af-171">**Customer account:** *US-001*</span></span>
    - <span data-ttu-id="394af-172">**Solicitud de cliente:** *2*</span><span class="sxs-lookup"><span data-stu-id="394af-172">**Customer requisition:** *2*</span></span>

1. <span data-ttu-id="394af-173">Agregue una línea de pedido que tenga la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="394af-173">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="394af-174">**Número de artículo:** *A0001* (un artículo al que no se ha asignado el filtro **Código 4**)</span><span class="sxs-lookup"><span data-stu-id="394af-174">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="394af-175">**Cantidad:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="394af-175">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="394af-176">Seleccione **Inventario \> Reserva** y luego, en el Panel de acciones, seleccione **Reservar lote interno** para reservar la línea de pedido.</span><span class="sxs-lookup"><span data-stu-id="394af-176">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

### <a name="create-order-set-4"></a><span data-ttu-id="394af-177">Crear conjunto de pedidos 4</span><span class="sxs-lookup"><span data-stu-id="394af-177">Create order set 4</span></span>

#### <a name="sales-orders-4-1-and-4-2"></a><span data-ttu-id="394af-178">Pedidos de ventas 4-1 y 4-2</span><span class="sxs-lookup"><span data-stu-id="394af-178">Sales orders 4-1 and 4-2</span></span>

1. <span data-ttu-id="394af-179">Cree dos pedidos de venta idénticos que tengan la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="394af-179">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="394af-180">**Cuenta de cliente:** *US-003*</span><span class="sxs-lookup"><span data-stu-id="394af-180">**Customer account:** *US-003*</span></span>

1. <span data-ttu-id="394af-181">Agregue una línea de pedido que tenga la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="394af-181">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="394af-182">**Número de artículo:** *A0001* (un artículo al que no se ha asignado el filtro **Código 4**)</span><span class="sxs-lookup"><span data-stu-id="394af-182">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="394af-183">**Cantidad:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="394af-183">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="394af-184">Seleccione **Inventario \> Reserva** y luego, en el Panel de acciones, seleccione **Reservar lote interno** para reservar la línea de pedido.</span><span class="sxs-lookup"><span data-stu-id="394af-184">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

#### <a name="sales-orders-4-3-and-4-4"></a><span data-ttu-id="394af-185">Pedidos de ventas 4-3 y 4-4</span><span class="sxs-lookup"><span data-stu-id="394af-185">Sales orders 4-3 and 4-4</span></span>

1. <span data-ttu-id="394af-186">Cree dos pedidos de venta idénticos que tengan la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="394af-186">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="394af-187">**Cuenta de cliente:** *US-004*</span><span class="sxs-lookup"><span data-stu-id="394af-187">**Customer account:** *US-004*</span></span>

1. <span data-ttu-id="394af-188">Agregue una línea de pedido que tenga la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="394af-188">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="394af-189">**Número de artículo:** *A0001* (un artículo al que no se ha asignado el filtro **Código 4**)</span><span class="sxs-lookup"><span data-stu-id="394af-189">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="394af-190">**Cantidad:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="394af-190">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="394af-191">Seleccione **Inventario \> Reserva** y luego, en el Panel de acciones, seleccione **Reservar lote interno** para reservar la línea de pedido.</span><span class="sxs-lookup"><span data-stu-id="394af-191">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

#### <a name="sales-orders-4-5-and-4-6"></a><span data-ttu-id="394af-192">Pedidos de ventas 4-5 y 4-6</span><span class="sxs-lookup"><span data-stu-id="394af-192">Sales orders 4-5 and 4-6</span></span>

1. <span data-ttu-id="394af-193">Cree dos pedidos de venta idénticos que tengan la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="394af-193">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="394af-194">**Cuenta de cliente:** *US-007*</span><span class="sxs-lookup"><span data-stu-id="394af-194">**Customer account:** *US-007*</span></span>
    - <span data-ttu-id="394af-195">**Sitio**: *6*</span><span class="sxs-lookup"><span data-stu-id="394af-195">**Site:** *6*</span></span>
    - <span data-ttu-id="394af-196">**Almacén**: *61*</span><span class="sxs-lookup"><span data-stu-id="394af-196">**Warehouse:** *61*</span></span>
    - <span data-ttu-id="394af-197">**Grupo:** *ShipCons*</span><span class="sxs-lookup"><span data-stu-id="394af-197">**Pool:** *ShipCons*</span></span>

1. <span data-ttu-id="394af-198">Agregue una línea de pedido que tenga la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="394af-198">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="394af-199">**Número de artículo:** *A0001* (un artículo al que no se ha asignado el filtro **Código 4**)</span><span class="sxs-lookup"><span data-stu-id="394af-199">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="394af-200">**Cantidad:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="394af-200">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="394af-201">Seleccione **Inventario \> Reserva** y luego, en el Panel de acciones, seleccione **Reservar lote interno** para reservar la línea de pedido.</span><span class="sxs-lookup"><span data-stu-id="394af-201">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

#### <a name="sales-orders-4-7-and-4-8"></a><span data-ttu-id="394af-202">Pedidos de ventas 4-7 y 4-8</span><span class="sxs-lookup"><span data-stu-id="394af-202">Sales orders 4-7 and 4-8</span></span>

1. <span data-ttu-id="394af-203">Cree dos pedidos de venta idénticos que tengan la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="394af-203">Create two identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="394af-204">**Cuenta de cliente:** *US-007*</span><span class="sxs-lookup"><span data-stu-id="394af-204">**Customer account:** *US-007*</span></span>
    - <span data-ttu-id="394af-205">**Sitio**: *6*</span><span class="sxs-lookup"><span data-stu-id="394af-205">**Site:** *6*</span></span>
    - <span data-ttu-id="394af-206">**Almacén**: *61*</span><span class="sxs-lookup"><span data-stu-id="394af-206">**Warehouse:** *61*</span></span>
    - <span data-ttu-id="394af-207">**Grupo:** Deje este campo en blanco.</span><span class="sxs-lookup"><span data-stu-id="394af-207">**Pool:** Leave this field blank.</span></span>

1. <span data-ttu-id="394af-208">Agregue una línea de pedido que tenga la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="394af-208">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="394af-209">**Número de artículo:** *A0001* (un artículo al que no se ha asignado el filtro **Código 4**)</span><span class="sxs-lookup"><span data-stu-id="394af-209">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="394af-210">**Cantidad:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="394af-210">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="394af-211">Seleccione **Inventario \> Reserva** y luego, en el Panel de acciones, seleccione **Reservar lote interno** para reservar la línea de pedido.</span><span class="sxs-lookup"><span data-stu-id="394af-211">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

## <a name="release-the-orders-to-the-warehouse"></a><span data-ttu-id="394af-212">Despachar los pedidos al almacén</span><span class="sxs-lookup"><span data-stu-id="394af-212">Release the orders to the warehouse</span></span>

<span data-ttu-id="394af-213">Siga estos pasos para despachar cada pedido de ventas que creó para este escenario al almacén.</span><span class="sxs-lookup"><span data-stu-id="394af-213">Follow these steps to release each sales order that you created for this scenario to the warehouse.</span></span>

1. <span data-ttu-id="394af-214">Vaya a **Clientes \> Pedidos \> Todos los pedidos de venta**.</span><span class="sxs-lookup"><span data-stu-id="394af-214">Go to **Accounts receivable \> Orders \> All sales orders**.</span></span>
1. <span data-ttu-id="394af-215">Busque y seleccione el pedido de ventas a despachar.</span><span class="sxs-lookup"><span data-stu-id="394af-215">Find and select the sales order to release.</span></span>
1. <span data-ttu-id="394af-216">En el panel Acciones, en la pestaña **Almacén**, seleccione **Acciones \> Liberar al almacén** para despachar el pedido de ventas seleccionado.</span><span class="sxs-lookup"><span data-stu-id="394af-216">On the Action Pane, on the **Warehouse** tab, select **Actions \> Release to warehouse** to release the selected sales order.</span></span>
1. <span data-ttu-id="394af-217">Repita este procedimiento para cada pedido de ventas restante que creó para este escenario.</span><span class="sxs-lookup"><span data-stu-id="394af-217">Repeat this procedure for every other sales order that you created for this scenario.</span></span>

## <a name="consolidate-the-shipments-by-using-the-shipment-consolidation-workbench"></a><span data-ttu-id="394af-218">Consolidar los envíos utilizando el área de trabajo de consolidación de envíos</span><span class="sxs-lookup"><span data-stu-id="394af-218">Consolidate the shipments by using the shipment consolidation workbench</span></span>

1. <span data-ttu-id="394af-219">Vaya a **Gestion de almacén \> Despachar al almacén \> Área de trabajo de consolidación de envíos**.</span><span class="sxs-lookup"><span data-stu-id="394af-219">Go to **Warehouse management \> Release to warehouse \> Shipment consolidation workbench**.</span></span>
1. <span data-ttu-id="394af-220">En el panel Acciones, seleccione **Editar consulta**.</span><span class="sxs-lookup"><span data-stu-id="394af-220">On the Action Pane, select **Edit query**.</span></span>
1. <span data-ttu-id="394af-221">En el cuadro de diálogo del editor de consultas, en la pestaña **Rango**, seleccione **Añadir** para agregar una fila que tenga la siguiente configuración a la cuadrícula:</span><span class="sxs-lookup"><span data-stu-id="394af-221">In the query editor dialog box, on the **Range** tab, select **Add** to add a row that has the following settings to the grid:</span></span>

    - <span data-ttu-id="394af-222">**Tabla:** *Pedidos de ventas*</span><span class="sxs-lookup"><span data-stu-id="394af-222">**Table:** *Sales orders*</span></span>
    - <span data-ttu-id="394af-223">**Campo:** *Pedido de ventas*</span><span class="sxs-lookup"><span data-stu-id="394af-223">**Field:** *Sales order*</span></span>
    - <span data-ttu-id="394af-224">**Criterio:** Introduzca una lista separada por comas de los números de pedido de ventas para cada conjunto de pedidos que creó para este escenario.</span><span class="sxs-lookup"><span data-stu-id="394af-224">**Criteria:** Enter a comma-separated list of the sales order numbers for each order set that you created for this scenario.</span></span>

1. <span data-ttu-id="394af-225">Seleccione **Aceptar** para guardar su consulta y cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="394af-225">Select **OK** to save your query and close the dialog box.</span></span>
1. <span data-ttu-id="394af-226">En el panel Acciones, seleccione **Consolidar envíos**.</span><span class="sxs-lookup"><span data-stu-id="394af-226">On the Action Pane, select **Consolidate shipments**.</span></span>
1. <span data-ttu-id="394af-227">Seleccione todos los envíos y, a continuación, en el panel Acciones, seleccione **Consolidar**.</span><span class="sxs-lookup"><span data-stu-id="394af-227">Select all the shipments, and then, on the Action Pane, select **Consolidate**.</span></span>

## <a name="verify-the-shipments"></a><span data-ttu-id="394af-228">Verificar los envíos</span><span class="sxs-lookup"><span data-stu-id="394af-228">Verify the shipments</span></span>

<span data-ttu-id="394af-229">El siguiente procedimiento le permite verificar los envíos que se han creado o actualizado como resultado de la consolidación de envíos.</span><span class="sxs-lookup"><span data-stu-id="394af-229">The following procedure lets you verify the shipments that have been created or updated as a result of shipment consolidation.</span></span> <span data-ttu-id="394af-230">Úselo para revisar cada conjunto de pedidos que creó para este escenario y luego revise las subsecciones siguientes para asegurarse de haber obtenido los resultados esperados.</span><span class="sxs-lookup"><span data-stu-id="394af-230">Use it to review each order set that you created for this scenario, and then review the subsections that follow to make sure that you've obtained the expected results.</span></span>

1. <span data-ttu-id="394af-231">Vaya a **Gestión de almacenes \> Envíos \> Todos los envíos**.</span><span class="sxs-lookup"><span data-stu-id="394af-231">Go to **Warehouse management \> Shipments \> All shipments**.</span></span>
1. <span data-ttu-id="394af-232">Encuentre y seleccione el envío requerido.</span><span class="sxs-lookup"><span data-stu-id="394af-232">Find and select the required shipment.</span></span>
1. <span data-ttu-id="394af-233">Si se utilizó una directiva de consolidación cuando se creó o actualizó el envío, debería verla en el campo **Directiva de consolidación de envío**.</span><span class="sxs-lookup"><span data-stu-id="394af-233">If a consolidation policy was used when the shipment was created or updated, you should see it in the **Shipment consolidation policy** field.</span></span>

### <a name="related-shipments-for-order-set-1"></a><span data-ttu-id="394af-234">Envíos relacionados para el conjunto de pedidos 1</span><span class="sxs-lookup"><span data-stu-id="394af-234">Related shipments for order set 1</span></span>

<span data-ttu-id="394af-235">Deben haberse creado dos envíos:</span><span class="sxs-lookup"><span data-stu-id="394af-235">Two shipments should have been created:</span></span>

- <span data-ttu-id="394af-236">El primer envío contiene tres líneas y se creó utilizando la directiva de consolidación de envíos *CustomerMode*.</span><span class="sxs-lookup"><span data-stu-id="394af-236">The first shipment contains three lines and was created by using the *CustomerMode* shipment consolidation policy.</span></span>
- <span data-ttu-id="394af-237">El segundo envío, que no utiliza el modo de transporte de entrega *Vías aéreas*, se creó usando la directiva de consolidación de envíos *CustomerOrderNo*.</span><span class="sxs-lookup"><span data-stu-id="394af-237">The second shipment, which doesn't use the *Airways* transportation mode of delivery, was created by using the *CustomerOrderNo* shipment consolidation policy.</span></span>

### <a name="related-shipments-for-order-set-2"></a><span data-ttu-id="394af-238">Envíos relacionados para el conjunto de pedidos 2</span><span class="sxs-lookup"><span data-stu-id="394af-238">Related shipments for order set 2</span></span>

<span data-ttu-id="394af-239">Deben haberse creado tres envíos:</span><span class="sxs-lookup"><span data-stu-id="394af-239">Three shipments should have been created:</span></span>

- <span data-ttu-id="394af-240">El primer envío contiene artículos *Inflamables*.</span><span class="sxs-lookup"><span data-stu-id="394af-240">The first shipment contains *Flammable* items.</span></span>
- <span data-ttu-id="394af-241">Cada uno de los otros dos envíos contiene una línea que tiene el artículo *Explosivo*.</span><span class="sxs-lookup"><span data-stu-id="394af-241">Each of the other two shipments contains one line that has the *Explosive* item.</span></span>

### <a name="related-shipments-for-order-set-3"></a><span data-ttu-id="394af-242">Envíos relacionados para el conjunto de pedidos 3</span><span class="sxs-lookup"><span data-stu-id="394af-242">Related shipments for order set 3</span></span>

<span data-ttu-id="394af-243">Deben haberse creado dos envíos:</span><span class="sxs-lookup"><span data-stu-id="394af-243">Two shipments should have been created:</span></span>

- <span data-ttu-id="394af-244">El primer envío contiene líneas de pedido del pedido de ventas donde el campo **Solicitud del cliente** está establecido en *1*.</span><span class="sxs-lookup"><span data-stu-id="394af-244">The first shipment contains order lines from the sales order where the **Customer requisition** field is set to *1*.</span></span>
- <span data-ttu-id="394af-245">El segundo envío contiene líneas de pedido del pedido de ventas donde el campo **Solicitud del cliente** está establecido en *2*.</span><span class="sxs-lookup"><span data-stu-id="394af-245">The second shipment contains order lines from sales order where the **Customer requisition** field is set to *2*.</span></span>

### <a name="related-shipments-for-order-set-4"></a><span data-ttu-id="394af-246">Envíos relacionados para el conjunto de pedidos 4</span><span class="sxs-lookup"><span data-stu-id="394af-246">Related shipments for order set 4</span></span>

<span data-ttu-id="394af-247">Deben haberse creado cuatro envíos:</span><span class="sxs-lookup"><span data-stu-id="394af-247">Four shipments should have been created:</span></span>

- <span data-ttu-id="394af-248">Las líneas de dos pedidos del cliente *US-003* se han agrupado en un envío, utilizando la directiva de consolidación de envíos *Grupo de pedidos*.</span><span class="sxs-lookup"><span data-stu-id="394af-248">Lines from two orders for customer *US-003* were grouped into one shipment by using the *Order pool* shipment consolidation policy.</span></span>
- <span data-ttu-id="394af-249">Las líneas de dos pedidos del cliente *US-004* se han agrupado en un envío, utilizando la directiva de consolidación de envíos *Grupo de pedidos*.</span><span class="sxs-lookup"><span data-stu-id="394af-249">Lines from two orders for customer *US-004* were grouped into one shipment by using the *Order pool* shipment consolidation policy.</span></span>
- <span data-ttu-id="394af-250">Las líneas de pedido de ventas 4-5 y 4-6 para clientes *US-007* se han agrupado en un envío, utilizando la directiva de consolidación de envíos *Grupo de pedidos*.</span><span class="sxs-lookup"><span data-stu-id="394af-250">Lines from sales orders 4-5 and 4-6 for customer *US-007* were grouped into one shipment by using the *Order pool* shipment consolidation policy.</span></span>
- <span data-ttu-id="394af-251">Las líneas de pedido de ventas 4-7 y 4-8 para clientes *US-007* se han agrupado en un envío, utilizando la directiva de consolidación de envíos *CrossOrder*.</span><span class="sxs-lookup"><span data-stu-id="394af-251">Lines from sales orders 4-7 and 4-8 for customer *US-007* were grouped into one shipment by using the *CrossOrder* shipment consolidation policy.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="394af-252">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="394af-252">Additional resources</span></span>

- [<span data-ttu-id="394af-253">Directivas de consolidación de envíos</span><span class="sxs-lookup"><span data-stu-id="394af-253">Shipment consolidation policies</span></span>](about-shipment-consolidation-policies.md)
- [<span data-ttu-id="394af-254">Configurar directivas de consolidación de envíos</span><span class="sxs-lookup"><span data-stu-id="394af-254">Configure shipment consolidation policies</span></span>](configure-shipment-consolidation-policies.md)
