---
title: Órdenes de cuarentena
description: Este tema describe cómo se usan los pedidos de cuarentena para bloquear inventario.
author: perlynne
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventLocation, InventModelGroup, InventQuarantineOrder, InventQuarantineParmEnd, InventQuarantineParmReportFinished, InventQuarantineParmStartUp, InventTrans
audience: Application User
ms.reviewer: kamaybac
ms.custom: 30021
ms.assetid: d5047727-653c-49da-b489-6fd3fe50445e
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5e1eed14b7d38cf569af7192dec9580e771f06df
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956191"
---
# <a name="quarantine-orders"></a><span data-ttu-id="def8b-103">Órdenes de cuarentena</span><span class="sxs-lookup"><span data-stu-id="def8b-103">Quarantine orders</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="def8b-104">Este tema describe cómo se usan los pedidos de cuarentena para bloquear inventario.</span><span class="sxs-lookup"><span data-stu-id="def8b-104">This topic describes how to use quarantine orders to block inventory.</span></span>

<span data-ttu-id="def8b-105">Los pedidos de cuarentena le permiten bloquear inventario.</span><span class="sxs-lookup"><span data-stu-id="def8b-105">Quarantine orders let you block inventory.</span></span> <span data-ttu-id="def8b-106">Por ejemplo, puede que desee poner en cuarentena los artículos por motivos de control de calidad.</span><span class="sxs-lookup"><span data-stu-id="def8b-106">For example, you might want to quarantine items for quality control reasons.</span></span> <span data-ttu-id="def8b-107">El inventario que se ha puesto en cuarentena se transfiere a un almacén de cuarentena.</span><span class="sxs-lookup"><span data-stu-id="def8b-107">Inventory that has been quarantined is transferred to a quarantine warehouse.</span></span>

> [!NOTE]
> <span data-ttu-id="def8b-108">Si utiliza procesos avanzados de administración de almacenes (en Administración de almacenes), el procesamiento de pedidos en cuarentena solo se usa para los pedidos de ventas de devolución.</span><span class="sxs-lookup"><span data-stu-id="def8b-108">If you're using advanced warehouse management processes (in Warehouse management), quarantine order processing is used only for return sales orders.</span></span>

## <a name="quarantine-on-hand-inventory-items"></a><span data-ttu-id="def8b-109">Poner en cuarentena artículos de inventario disponibles</span><span class="sxs-lookup"><span data-stu-id="def8b-109">Quarantine on-hand inventory items</span></span>

<span data-ttu-id="def8b-110">Cuando ponga los artículos en cuarentena, puede crear órdenes de cuarentena manualmente o configurar el sistema para crearlas automáticamente durante el proceso de entrada.</span><span class="sxs-lookup"><span data-stu-id="def8b-110">When you quarantine items, you can either manually create the quarantine orders or set up the system to automatically create them during inbound processing.</span></span>

<span data-ttu-id="def8b-111">Para configurar el sistema para que genere automáticamente pedidos de cuarentena, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="def8b-111">To set up the system to automatically generate quarantine orders, follow these steps.</span></span>

1. <span data-ttu-id="def8b-112">Vaya a **Gestión del inventario \> Configurar \> Inventario \> Grupos de modelos de inventario**.</span><span class="sxs-lookup"><span data-stu-id="def8b-112">Go to **Inventory management \> Setup \> Inventory \> Item model groups**.</span></span>
1. <span data-ttu-id="def8b-113">Seleccione un grupo de modelos relevantes en el pane de lista o cree un nuevo grupo de modelos.</span><span class="sxs-lookup"><span data-stu-id="def8b-113">Select a relevant model group in the list pane, or create a new model group.</span></span>
1. <span data-ttu-id="def8b-114">En la ficha desplegable **Directivas de inventario**, seleccione la casilla **Gestión de cuarentenas**.</span><span class="sxs-lookup"><span data-stu-id="def8b-114">On the **Inventory policies** FastTab, select the **Quarantine management** check box.</span></span>
1. <span data-ttu-id="def8b-115">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="def8b-115">Close the page.</span></span>
1. <span data-ttu-id="def8b-116">En el campo **Almacén de cuarentena** de los almacenes de recepción, especifique un almacén de cuarentena predeterminado.</span><span class="sxs-lookup"><span data-stu-id="def8b-116">In the **Quarantine warehouse** field for the receiving warehouses, specify a default quarantine warehouse.</span></span>

<span data-ttu-id="def8b-117">Cuando un artículo registrado como recibido en el almacén pertenece a un grupo de modelos donde está seleccionada la casilla **Gestión de cuarentena**, el sistema genera una orden de cuarentena para él.</span><span class="sxs-lookup"><span data-stu-id="def8b-117">When an item that is registered as received at the warehouse belongs to a model group where the **Quarantine management** check box is selected, the system generates a quarantine order for it.</span></span> <span data-ttu-id="def8b-118">El pedido de cuarentena indica a los trabajadores que muevan el artículo al almacén de cuarentena.</span><span class="sxs-lookup"><span data-stu-id="def8b-118">The quarantine order instructs workers to move the item to the quarantine warehouse.</span></span>

<span data-ttu-id="def8b-119">Al crear pedidos de cuarentena manualmente en la página **Pedidos de cuarentena**, el artículo no se tiene que configurar para gestión de cuarentena en el grupo de modelos del artículo asociado.</span><span class="sxs-lookup"><span data-stu-id="def8b-119">When you manually create quarantine orders on the **Quarantine orders** page, the item doesn't have to be set up for quarantine management in the associated item model group.</span></span> <span data-ttu-id="def8b-120">Para este proceso, debe especificar el inventario disponible que se debe poner en cuarentena y el almacén de cuarentena que se debe utilizar.</span><span class="sxs-lookup"><span data-stu-id="def8b-120">For this process, you must specify the on-hand inventory that should be quarantined and the quarantine warehouse that should be used.</span></span> <span data-ttu-id="def8b-121">Puede usar los estados de orden de cuarentena para ayudar a planear el proceso.</span><span class="sxs-lookup"><span data-stu-id="def8b-121">You can use the quarantine order statuses to help plan the process.</span></span>

## <a name="quarantine-order-statuses"></a><span data-ttu-id="def8b-122">Estados de la orden de cuarentena</span><span class="sxs-lookup"><span data-stu-id="def8b-122">Quarantine order statuses</span></span>

<span data-ttu-id="def8b-123">Las órdenes de cuarentena pueden tener los siguientes estados:</span><span class="sxs-lookup"><span data-stu-id="def8b-123">Quarantine orders can have the following statuses:</span></span>

- <span data-ttu-id="def8b-124">Creado</span><span class="sxs-lookup"><span data-stu-id="def8b-124">Created</span></span>
- <span data-ttu-id="def8b-125">Iniciado</span><span class="sxs-lookup"><span data-stu-id="def8b-125">Started</span></span>
- <span data-ttu-id="def8b-126">Notificado como terminado</span><span class="sxs-lookup"><span data-stu-id="def8b-126">Reported as finished</span></span>
- <span data-ttu-id="def8b-127">Finalizado</span><span class="sxs-lookup"><span data-stu-id="def8b-127">Ended</span></span>

### <a name="created"></a><span data-ttu-id="def8b-128">Creado</span><span class="sxs-lookup"><span data-stu-id="def8b-128">Created</span></span>

<span data-ttu-id="def8b-129">Cuando la orden de cuarentena se ha creado manualmente, pero el artículo aún no se ha colocado en un almacén de cuarentena, la orden de cuarentena recibe el estado de **Creado**.</span><span class="sxs-lookup"><span data-stu-id="def8b-129">When a quarantine order has been created manually, but the item isn't yet in the quarantine warehouse, the quarantine order has a status of **Created**.</span></span> <span data-ttu-id="def8b-130">Se crean dos transacciones de inventario.</span><span class="sxs-lookup"><span data-stu-id="def8b-130">Two inventory transactions are generated.</span></span> <span data-ttu-id="def8b-131">Una transacción es una transacción de emisión que puede tener un estado de **En pedido**, **Reservado físicamente** o **Seleccionado**.</span><span class="sxs-lookup"><span data-stu-id="def8b-131">One transaction is an issue transaction that can have a status of **On order**, **Reserved physical**, or **Picked**.</span></span> <span data-ttu-id="def8b-132">La otra transacción es una transacción de recepción que puede tener un estado de **Pedido** o **Registrado** en el almacén de cuarentena.</span><span class="sxs-lookup"><span data-stu-id="def8b-132">The other transaction is a receipt transaction that can have a status of **Ordered** or **Registered** at the quarantine warehouse.</span></span> <span data-ttu-id="def8b-133">Puede reservar, seleccionar y registrar actualizaciones en el inventario mediante los procesos habituales.</span><span class="sxs-lookup"><span data-stu-id="def8b-133">You can reserve, pick, and register updates to the inventory by using the usual processes.</span></span>

### <a name="started"></a><span data-ttu-id="def8b-134">Iniciado</span><span class="sxs-lookup"><span data-stu-id="def8b-134">Started</span></span>

<span data-ttu-id="def8b-135">Una vez que el pedido de cuarentena tenga un estado **Iniciado**, el inventario se transfiere del almacén habitual al almacén de cuarentena y se generan dos transacciones de inventario.</span><span class="sxs-lookup"><span data-stu-id="def8b-135">When a quarantine order has a status of **Started**, the inventory is transferred from the regular warehouse to the quarantine warehouse, and two inventory transactions are generated.</span></span> <span data-ttu-id="def8b-136">Una transacción tiene el estado de **Descontada** y otra tiene un estado de **Recibida**.</span><span class="sxs-lookup"><span data-stu-id="def8b-136">One transaction has a status of **Deducted**, and the other transaction has a status of **Received**.</span></span> <span data-ttu-id="def8b-137">Al mismo tiempo, se crean dos transacciones de inventario para gestionar la transferencia de devolución.</span><span class="sxs-lookup"><span data-stu-id="def8b-137">At the same time, two inventory transactions are created to handle the return transfer.</span></span> <span data-ttu-id="def8b-138">Estas transacciones no se fechan.</span><span class="sxs-lookup"><span data-stu-id="def8b-138">These transactions aren't dated.</span></span> <span data-ttu-id="def8b-139">Una transacción tiene el estado de **Reservado físicamente** y otra tiene un estado de **Pedida**.</span><span class="sxs-lookup"><span data-stu-id="def8b-139">One transaction has a status of **Reserved physical**, and the other transaction has a status of **Ordered**.</span></span>

### <a name="reported-as-finished"></a><span data-ttu-id="def8b-140">Notificado como terminado</span><span class="sxs-lookup"><span data-stu-id="def8b-140">Reported as finished</span></span>

<span data-ttu-id="def8b-141">Para informar de un pedido de cuarentena iniciado como finalizado, abra el pedido y seleccione **Informar como terminado** en el panel de acciones.</span><span class="sxs-lookup"><span data-stu-id="def8b-141">To report a started quarantine order as finished, open the order, and select **Report as finished** on the Action Pane.</span></span> <span data-ttu-id="def8b-142">El artículo se libera desde la cuarentena, aunque aún no se ha devuelto al almacén habitual.</span><span class="sxs-lookup"><span data-stu-id="def8b-142">The item is released from quarantine, but it isn't yet moved back to the regular warehouse.</span></span> <span data-ttu-id="def8b-143">El movimiento de vuelta al almacén habitual se puede procesar mediante un diario de recepción de artículos que se pueda inicializar durante el informe como proceso terminado.</span><span class="sxs-lookup"><span data-stu-id="def8b-143">The movement back to the regular warehouse can be processed via an item arrival journal that can be initialized during the report as finished process.</span></span>

### <a name="ended"></a><span data-ttu-id="def8b-144">Finalizado</span><span class="sxs-lookup"><span data-stu-id="def8b-144">Ended</span></span>

<span data-ttu-id="def8b-145">Cuando se finaliza una orden de cuarentena, el artículo se traslada desde el almacén de cuarentena de nuevo al almacén habitual.</span><span class="sxs-lookup"><span data-stu-id="def8b-145">When a quarantine order is ended, the item is moved from the quarantine warehouse back to the regular warehouse.</span></span> <span data-ttu-id="def8b-146">El estado de la transacción de artículos se establece en *Vendido* en el almacén de cuarentena y en *Comprado* en el almacén de cuarentena.</span><span class="sxs-lookup"><span data-stu-id="def8b-146">The status of the item transaction is set to *Sold* at the quarantine warehouse and *Purchased* at the regular warehouse.</span></span>

## <a name="quarantine-order-scrap"></a><span data-ttu-id="def8b-147">Eliminación de órdenes de cuarentena</span><span class="sxs-lookup"><span data-stu-id="def8b-147">Quarantine order scrap</span></span>

<span data-ttu-id="def8b-148">Como parte del proceso de la orden de cuarentena, puede eliminar inventario.</span><span class="sxs-lookup"><span data-stu-id="def8b-148">As part of the quarantine order process, you can scrap inventory.</span></span> <span data-ttu-id="def8b-149">Al procesar la eliminación, el estado del inventario se establecerá en *Vendido* mediante una transacción de emisión del almacén de cuarentena.</span><span class="sxs-lookup"><span data-stu-id="def8b-149">When you process scrap, the status of the inventory is set to *Sold* by an issue transaction from the quarantine warehouse.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="def8b-150">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="def8b-150">Additional resources</span></span>

- [<span data-ttu-id="def8b-151">Bloqueo del inventario</span><span class="sxs-lookup"><span data-stu-id="def8b-151">Inventory blocking</span></span>](inventory-blocking.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
