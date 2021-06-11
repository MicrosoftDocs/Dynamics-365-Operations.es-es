---
title: Consolide los envíos cuando se anula la directiva de consolidación de envíos
description: Este tema presenta un escenario en el que una o más líneas de ventas deben despacharse manualmente al almacén desde la página Despachar a almacén, y la directiva de consolidación de envío definida por el sistema debe anularse antes del despacho.
author: GarmMSFT
ms.date: 05/12/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSShipConsolidationPolicy, WHSShipConsolidationWorkbench, WHSFilterGroupTable, WHSShipConsolidationSetShipment, WHSShipmentConsolidation, WHSFilterGenerallyAvail, WHSReleaseToWarehouse
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: 6928375c88a199bd9c6b48f05b38343463762920
ms.sourcegitcommit: 53b797ff1b524f581046b48cdde42f50b37495bc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/28/2021
ms.locfileid: "6117018"
---
# <a name="consolidate-shipments-when-the-shipment-consolidation-policy-is-overridden"></a><span data-ttu-id="5d0b4-103">Consolide los envíos cuando se anula la directiva de consolidación de envíos</span><span class="sxs-lookup"><span data-stu-id="5d0b4-103">Consolidate shipments when the shipment consolidation policy is overridden</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5d0b4-104">Este tema presenta un escenario en el que una o más líneas de ventas deben despacharse manualmente al almacén desde la página **Despachar a almacén**, y la directiva de consolidación de envíos definida por el sistema debe anularse antes del despacho.</span><span class="sxs-lookup"><span data-stu-id="5d0b4-104">This topic presents a scenario where one or more sales lines must be manually released to the warehouse from the **Release to warehouse** page, and the system-defined shipment consolidation policy must be overridden before the release.</span></span> <span data-ttu-id="5d0b4-105">Es posible que se deba anular la directiva de consolidación de envíos si, por ejemplo, un pedido que generalmente no se consolida con envíos abiertos debe consolidarse con envíos abiertos.</span><span class="sxs-lookup"><span data-stu-id="5d0b4-105">An override of the shipment consolidation policy might be required if, for example, an order that isn't usually consolidated with open shipments must be consolidated with open shipments.</span></span>

<span data-ttu-id="5d0b4-106">Durante el escenario, creará un conjunto de pedidos de ventas y luego anulará la directiva de consolidación de envíos predeterminada antes de despachar los pedidos al almacén.</span><span class="sxs-lookup"><span data-stu-id="5d0b4-106">During the scenario, you will create a set of sales orders and then override the default shipment consolidation policy before you release the orders to the warehouse.</span></span>

## <a name="make-demo-data-available"></a><span data-ttu-id="5d0b4-107">Hacer que los datos de demostración estén disponibles</span><span class="sxs-lookup"><span data-stu-id="5d0b4-107">Make demo data available</span></span>

<span data-ttu-id="5d0b4-108">El escenario de este tema hace referencia a valores y registros que se incluyen en los datos de demostración estándar que se proporcionan para Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="5d0b4-108">The scenario in this topic references values and records that are included in the standard demo data that is provided for Microsoft Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="5d0b4-109">Si desea utilizar los valores que se proporcionan aquí mientras realiza los ejercicios, asegúrese de trabajar en un entorno donde estén instalados los datos de demostración y configure la entidad jurídica en **USMF** antes de empezar.</span><span class="sxs-lookup"><span data-stu-id="5d0b4-109">If you want to use the values that are provided here as you do the exercises, be sure to work in an environment where the demo data is installed, and set the legal entity to **USMF** before you begin.</span></span>

## <a name="set-up-shipment-consolidation-policies-and-product-filters"></a><span data-ttu-id="5d0b4-110">Configurar directivas de consolidación de envíos y filtros de productos</span><span class="sxs-lookup"><span data-stu-id="5d0b4-110">Set up shipment consolidation policies and product filters</span></span>

<span data-ttu-id="5d0b4-111">El escenario que se describe aquí supone que ya ha activado la función, realizado los ejercicios de [Configurar directivas de consolidación de envíos](configure-shipment-consolidation-policies.md) y creado las directivas y otros registros que se describen allí.</span><span class="sxs-lookup"><span data-stu-id="5d0b4-111">The scenario that is described here assumes that you've already turned on the feature, done the exercises in [Configure shipment consolidation policies](configure-shipment-consolidation-policies.md), and created the policies and other records that are described there.</span></span> <span data-ttu-id="5d0b4-112">Asegúrese de hacer esos ejercicios antes de continuar con este escenario.</span><span class="sxs-lookup"><span data-stu-id="5d0b4-112">Be sure to do those exercises before you continue with this scenario.</span></span>

## <a name="create-the-sales-orders-for-this-scenario"></a><span data-ttu-id="5d0b4-113">Crear los pedidos de ventas para este escenario</span><span class="sxs-lookup"><span data-stu-id="5d0b4-113">Create the sales orders for this scenario</span></span>

1. <span data-ttu-id="5d0b4-114">Vaya a **Clientes \> Pedidos \> Todos los pedidos de ventas** y cree tres pedidos de venta idénticos que tengan la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="5d0b4-114">Go to **Accounts receivable \> Orders \> All sales orders**, and create three identical sales orders that have the following settings:</span></span>

    - <span data-ttu-id="5d0b4-115">**Cuenta de cliente:** *US-002*</span><span class="sxs-lookup"><span data-stu-id="5d0b4-115">**Customer account:** *US-002*</span></span>

1. <span data-ttu-id="5d0b4-116">Agregue una línea de pedido que tenga la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="5d0b4-116">Add an order line that has the following settings:</span></span>

    - <span data-ttu-id="5d0b4-117">**Número de artículo:** *A0001* (un artículo al que no se ha asignado el filtro **Código 4**)</span><span class="sxs-lookup"><span data-stu-id="5d0b4-117">**Item number:** *A0001* (an item that no **Code 4** filter is assigned to)</span></span>
    - <span data-ttu-id="5d0b4-118">**Cantidad:** *1.00*</span><span class="sxs-lookup"><span data-stu-id="5d0b4-118">**Quantity:** *1.00*</span></span>

1. <span data-ttu-id="5d0b4-119">Seleccione **Inventario \> Reserva** y luego, en el Panel de acciones, seleccione **Reservar lote interno** para reservar la línea de pedido.</span><span class="sxs-lookup"><span data-stu-id="5d0b4-119">Select **Inventory \> Reservation**, and then, on the Action Pane, select **Reserve lot** to reserve the order line.</span></span>

## <a name="release-the-sales-orders-from-the-release-to-warehouse-page"></a><span data-ttu-id="5d0b4-120">Despachar los pedidos de ventas desde la página Despachar al almacén</span><span class="sxs-lookup"><span data-stu-id="5d0b4-120">Release the sales orders from the Release to warehouse page</span></span>

<span data-ttu-id="5d0b4-121">Siga estos pasos para anular la directiva de consolidación de envíos durante el deespacho al almacén.</span><span class="sxs-lookup"><span data-stu-id="5d0b4-121">Follow these steps to override the shipment consolidation policy during the release to the warehouse.</span></span>

1. <span data-ttu-id="5d0b4-122">Vaya a **Gestión de almacén \> Despachar al almacén \> Despachar al almacén**.</span><span class="sxs-lookup"><span data-stu-id="5d0b4-122">Go to **Warehouse management \> Release to warehouse \> Release to warehouse**.</span></span>
1. <span data-ttu-id="5d0b4-123">En el panel superior, seleccione el primer pedido de ventas que creó para este escenario.</span><span class="sxs-lookup"><span data-stu-id="5d0b4-123">In the upper pane, select the first sales order that you created for this scenario.</span></span>
1. <span data-ttu-id="5d0b4-124">Seleccione **Añadir** para agregar la línea al despacho al almacén.</span><span class="sxs-lookup"><span data-stu-id="5d0b4-124">Select **Add** to add the line to the release to the warehouse.</span></span> <span data-ttu-id="5d0b4-125">Tenga en cuenta que la directiva de consolidación de envíos *Predeterminada* se aplica en el panel inferior.</span><span class="sxs-lookup"><span data-stu-id="5d0b4-125">Notice that the *Default* shipment consolidation policy is applied in the bottom pane.</span></span>
1. <span data-ttu-id="5d0b4-126">En el panel inferior, elija **Seleccionar nueva directiva de consolidación de envíos**.</span><span class="sxs-lookup"><span data-stu-id="5d0b4-126">In the bottom pane, select **Select new shipment consolidation policy**.</span></span>
1. <span data-ttu-id="5d0b4-127">Seleccione una directiva que permita la consolidación con otros envíos abiertos de la misma directiva.</span><span class="sxs-lookup"><span data-stu-id="5d0b4-127">Select a policy that allows for consolidation with other open shipments of the same policy.</span></span> <span data-ttu-id="5d0b4-128">Por ejemplo, seleccione la directiva *CustomerOrderNo*.</span><span class="sxs-lookup"><span data-stu-id="5d0b4-128">For example, select the *CustomerOrderNo* policy.</span></span>
1. <span data-ttu-id="5d0b4-129">Seleccione **Despachar al almacén**.</span><span class="sxs-lookup"><span data-stu-id="5d0b4-129">Select **Release to warehouse**.</span></span>
1. <span data-ttu-id="5d0b4-130">Seleccione los pedidos de ventas segundo y tercero que creó para este escenario.</span><span class="sxs-lookup"><span data-stu-id="5d0b4-130">Select the second and third sales orders that you created for this scenario.</span></span>
1. <span data-ttu-id="5d0b4-131">Seleccione **Añadir** para agregar las líneas al despacho al almacén.</span><span class="sxs-lookup"><span data-stu-id="5d0b4-131">Select **Add** to add the lines to the release to the warehouse.</span></span> <span data-ttu-id="5d0b4-132">Tenga en cuenta que la directiva *Predeterminada* se aplica en el panel inferior.</span><span class="sxs-lookup"><span data-stu-id="5d0b4-132">Notice that the *Default* policy is applied in the bottom pane.</span></span>
1. <span data-ttu-id="5d0b4-133">Seleccione la segunda línea y luego, en el campo **Seleccionar nueva directiva de consolidación de envíos**, seleccione la directiva *CustomerOrderNo*.</span><span class="sxs-lookup"><span data-stu-id="5d0b4-133">Select the second line, and then, in the **Select new shipment consolidation policy** field, select the *CustomerOrderNo* policy.</span></span>
1. <span data-ttu-id="5d0b4-134">Seleccione **Despachar al almacén** para ambas líneas.</span><span class="sxs-lookup"><span data-stu-id="5d0b4-134">Select **Release to warehouse** for both lines.</span></span>

## <a name="verify-the-shipments"></a><span data-ttu-id="5d0b4-135">Verificar los envíos</span><span class="sxs-lookup"><span data-stu-id="5d0b4-135">Verify the shipments</span></span>

<span data-ttu-id="5d0b4-136">Deben haberse creado dos envíos:</span><span class="sxs-lookup"><span data-stu-id="5d0b4-136">Two shipments should have been created:</span></span>

- <span data-ttu-id="5d0b4-137">El primer envío contiene dos líneas y se creó utilizando la directiva de consolidación de envíos *CustomerOrderNo*.</span><span class="sxs-lookup"><span data-stu-id="5d0b4-137">The first shipment contains two lines and was created by using the *CustomerOrderNo* shipment consolidation policy.</span></span>
- <span data-ttu-id="5d0b4-138">El segundo envío contiene una línea y se creó utilizando la directiva de consolidación de envíos *Predeterminada*.</span><span class="sxs-lookup"><span data-stu-id="5d0b4-138">The second shipment contains one line and was created by using the *Default* shipment consolidation policy.</span></span>

<span data-ttu-id="5d0b4-139">Siga estos pasos para revisar los envíos que se crearon.</span><span class="sxs-lookup"><span data-stu-id="5d0b4-139">Follow these steps to review the shipments that were created.</span></span>

1. <span data-ttu-id="5d0b4-140">Vaya a **Gestión de almacenes \> Envíos \> Todos los envíos**.</span><span class="sxs-lookup"><span data-stu-id="5d0b4-140">Go to **Warehouse management \> Shipments \> All shipments**.</span></span>
1. <span data-ttu-id="5d0b4-141">Encuentre y seleccione el envío requerido.</span><span class="sxs-lookup"><span data-stu-id="5d0b4-141">Find and select the required shipment.</span></span>
1. <span data-ttu-id="5d0b4-142">En el campo **Directiva de consolidación de envíos**, revise la directiva de consolidación usada cuando se creó el envío.</span><span class="sxs-lookup"><span data-stu-id="5d0b4-142">In the **Shipment consolidation policy** field, review the consolidation policy that was used when the shipment was created.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5d0b4-143">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="5d0b4-143">Additional resources</span></span>

- [<span data-ttu-id="5d0b4-144">Directivas de consolidación de envíos</span><span class="sxs-lookup"><span data-stu-id="5d0b4-144">Shipment consolidation policies</span></span>](about-shipment-consolidation-policies.md)
- [<span data-ttu-id="5d0b4-145">Configurar directivas de consolidación de envíos</span><span class="sxs-lookup"><span data-stu-id="5d0b4-145">Configure shipment consolidation policies</span></span>](configure-shipment-consolidation-policies.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]