---
title: Órdenes de cuarentena
description: Este tema describe cómo se usan los pedidos de cuarentena para bloquear el inventario.
author: perlynne
manager: tfehr
ms.date: 11/02/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventLocation, InventModelGroup, InventQuarantineOrder, InventQuarantineParmEnd, InventQuarantineParmReportFinished, InventQuarantineParmStartUp, InventTrans
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 30021
ms.assetid: d5047727-653c-49da-b489-6fd3fe50445e
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 25ba4aa92d968f4dfb0dc23b1ac459cda2d52b61
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437127"
---
# <a name="quarantine-orders"></a><span data-ttu-id="f5d03-103">Órdenes de cuarentena</span><span class="sxs-lookup"><span data-stu-id="f5d03-103">Quarantine orders</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f5d03-104">Este tema describe cómo se usan los pedidos de cuarentena para bloquear el inventario.</span><span class="sxs-lookup"><span data-stu-id="f5d03-104">This topic describes how quarantine orders are used to block inventory.</span></span>

<span data-ttu-id="f5d03-105">Los pedidos de cuarentena se pueden usar para bloquear el inventario.</span><span class="sxs-lookup"><span data-stu-id="f5d03-105">Quarantine orders can be used to block inventory.</span></span> <span data-ttu-id="f5d03-106">Por ejemplo, puede que desee poner en cuarentena los artículos por motivos de control de calidad.</span><span class="sxs-lookup"><span data-stu-id="f5d03-106">For example, you might want to quarantine items for quality control reasons.</span></span> <span data-ttu-id="f5d03-107">El inventario que se ha puesto en cuarentena se transfiere a un almacén de cuarentena.</span><span class="sxs-lookup"><span data-stu-id="f5d03-107">Inventory that has been quarantined is transferred to a quarantine warehouse.</span></span> <span data-ttu-id="f5d03-108">**Nota:** Si utiliza procesos avanzados de administración de almacenes (en Administración de almacenes), el procesamiento de pedidos en cuarentena solo se usa para los pedidos de ventas de devolución.</span><span class="sxs-lookup"><span data-stu-id="f5d03-108">**Note:** If you're using advanced warehouse management processes (in Warehouse management), quarantine order processing is used only for return sales orders.</span></span>

## <a name="quarantine-on-hand-inventory-items"></a><span data-ttu-id="f5d03-109">Poner en cuarentena artículos de inventario disponibles</span><span class="sxs-lookup"><span data-stu-id="f5d03-109">Quarantine on-hand inventory items</span></span>
<span data-ttu-id="f5d03-110">Cuando ponga los artículos en cuarentena, puede crear órdenes de cuarentena manualmente o configurar el sistema para crear las órdenes de cuarentena automáticamente durante el proceso de entrada.</span><span class="sxs-lookup"><span data-stu-id="f5d03-110">When you quarantine items, you can either create the quarantine orders manually or set up the system to create the quarantine orders automatically during inbound processing.</span></span> <span data-ttu-id="f5d03-111">Para crear órdenes de cuarentena automáticamente, seleccione la opción **Gestión de cuarentena** de la ficha **Directivas de inventario** de la página **Grupos de modelos de artículo**.</span><span class="sxs-lookup"><span data-stu-id="f5d03-111">To create quarantine orders automatically, select the **Quarantine management** option on the **Inventory policies** tab on the **Item model groups** page.</span></span> <span data-ttu-id="f5d03-112">También debe especificar el almacén de cuarentena predeterminado en el campo **Almacén de cuarentena** para los almacenes de recepción.</span><span class="sxs-lookup"><span data-stu-id="f5d03-112">You must also specify a default quarantine warehouse in the **Quarantine warehouse** field for the receiving warehouses.</span></span> <span data-ttu-id="f5d03-113">Cuando el inventario disponible físicamente se registra en un pedido de compra o pedido de producción, los artículos en cuarentena se mueven automáticamente a un almacén de cuarentena en Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="f5d03-113">When the physically on-hand inventory is recorded in a purchase order or production order, quarantined items are automatically moved to a quarantine warehouse in Supply Chain Management.</span></span> <span data-ttu-id="f5d03-114">Este movimiento se produce porque el estado del pedido de cuarentena se cambia a **Iniciado**.</span><span class="sxs-lookup"><span data-stu-id="f5d03-114">This movement occurs because the status of the quarantine order is changed to **Started**.</span></span> <span data-ttu-id="f5d03-115">Al crear órdenes de cuarentena manualmente, el artículo no se tiene que configurar para gestión de cuarentena en el grupo de modelos del artículo asociado.</span><span class="sxs-lookup"><span data-stu-id="f5d03-115">When you create quarantine orders manually, the item doesn't have to be set up for quarantine management in the associated item model group.</span></span> <span data-ttu-id="f5d03-116">Para este proceso, debe especificar el inventario disponible que se debe poner en cuarentena y el almacén de cuarentena que se debe utilizar.</span><span class="sxs-lookup"><span data-stu-id="f5d03-116">For this process, you must specify the on-hand inventory that should be quarantined and the quarantine warehouse that should be used.</span></span> <span data-ttu-id="f5d03-117">Puede usar los estados de orden de cuarentena para ayudar a planear el proceso.</span><span class="sxs-lookup"><span data-stu-id="f5d03-117">You can use the quarantine order statuses to help plan the process.</span></span>

## <a name="quarantine-order-statuses"></a><span data-ttu-id="f5d03-118">Estados de la orden de cuarentena</span><span class="sxs-lookup"><span data-stu-id="f5d03-118">Quarantine order statuses</span></span>
<span data-ttu-id="f5d03-119">Las órdenes de cuarentena pueden tener los siguientes estados:</span><span class="sxs-lookup"><span data-stu-id="f5d03-119">Quarantine orders can have the following statuses:</span></span>

-   <span data-ttu-id="f5d03-120">Creado</span><span class="sxs-lookup"><span data-stu-id="f5d03-120">Created</span></span>
-   <span data-ttu-id="f5d03-121">Iniciado</span><span class="sxs-lookup"><span data-stu-id="f5d03-121">Started</span></span>
-   <span data-ttu-id="f5d03-122">Notificado como terminado</span><span class="sxs-lookup"><span data-stu-id="f5d03-122">Reported as finished</span></span>
-   <span data-ttu-id="f5d03-123">Finalizado</span><span class="sxs-lookup"><span data-stu-id="f5d03-123">Ended</span></span>

### <a name="created"></a><span data-ttu-id="f5d03-124">Creado</span><span class="sxs-lookup"><span data-stu-id="f5d03-124">Created</span></span>

<span data-ttu-id="f5d03-125">Cuando la orden de cuarentena se ha creado manualmente, pero el artículo aún no se ha colocado en un almacén de cuarentena, la orden de cuarentena recibe el estado de **Creado**.</span><span class="sxs-lookup"><span data-stu-id="f5d03-125">When a quarantine order has been created manually, but the item isn't yet in the quarantine warehouse, the quarantine order has a status of **Created**.</span></span> <span data-ttu-id="f5d03-126">Se crean dos transacciones de inventario.</span><span class="sxs-lookup"><span data-stu-id="f5d03-126">Two inventory transactions are generated.</span></span> <span data-ttu-id="f5d03-127">Una transacción es una transacción de emisión que puede tener un estado de **En pedido**, **Reservado físicamente** o **Seleccionado**.</span><span class="sxs-lookup"><span data-stu-id="f5d03-127">One transaction is an issue transaction that can have a status of **On order**, **Reserved physical**, or **Picked**.</span></span> <span data-ttu-id="f5d03-128">La otra transacción es una transacción de recepción que puede tener un estado de **Pedido** o **Registrado** en el almacén de cuarentena.</span><span class="sxs-lookup"><span data-stu-id="f5d03-128">The other transaction is a receipt transaction that can have a status of **Ordered** or **Registered** at the quarantine warehouse.</span></span> <span data-ttu-id="f5d03-129">Puede reservar, seleccionar y registrar actualizaciones en el inventario mediante los procesos habituales.</span><span class="sxs-lookup"><span data-stu-id="f5d03-129">You can reserve, pick, and register updates to the inventory by using the usual processes.</span></span>

### <a name="started"></a><span data-ttu-id="f5d03-130">Iniciado</span><span class="sxs-lookup"><span data-stu-id="f5d03-130">Started</span></span>

<span data-ttu-id="f5d03-131">Una vez que el pedido de cuarentena tenga un estado **Iniciado**, el inventario se transfiere del almacén habitual al almacén de cuarentena y se generan dos transacciones de inventario.</span><span class="sxs-lookup"><span data-stu-id="f5d03-131">When a quarantine order has a status of **Started**, the inventory is transferred from the regular warehouse to the quarantine warehouse, and two inventory transactions are generated.</span></span> <span data-ttu-id="f5d03-132">Una transacción tiene el estado de **Descontada** y otra tiene un estado de **Recibida**.</span><span class="sxs-lookup"><span data-stu-id="f5d03-132">One transaction has a status of **Deducted**, and the other transaction has a status of **Received**.</span></span> <span data-ttu-id="f5d03-133">Al mismo tiempo, se crean dos transacciones de inventario para gestionar la transferencia de devolución.</span><span class="sxs-lookup"><span data-stu-id="f5d03-133">At the same time, two inventory transactions are created to handle the return transfer.</span></span> <span data-ttu-id="f5d03-134">Estas transacciones no se fechan.</span><span class="sxs-lookup"><span data-stu-id="f5d03-134">These transactions aren't dated.</span></span> <span data-ttu-id="f5d03-135">Una transacción tiene el estado de **Reservado físicamente** y otra tiene un estado de **Pedida**.</span><span class="sxs-lookup"><span data-stu-id="f5d03-135">One transaction has a status of **Reserved physical**, and the other transaction has a status of **Ordered**.</span></span>

### <a name="reported-as-finished"></a><span data-ttu-id="f5d03-136">Notificado como terminado</span><span class="sxs-lookup"><span data-stu-id="f5d03-136">Reported as finished</span></span>

<span data-ttu-id="f5d03-137">Al hacer clic en **Informe como finalizado**, puede notificar una orden de cuarentena iniciada como terminada.</span><span class="sxs-lookup"><span data-stu-id="f5d03-137">By clicking **Report as finished**, you can report a started quarantine order as finished.</span></span> <span data-ttu-id="f5d03-138">El artículo se libera desde la cuarentena aunque aún no se ha vuelto a trasladar al almacén habitual.</span><span class="sxs-lookup"><span data-stu-id="f5d03-138">The item is released from quarantine but isn't yet moved back to the regular warehouse.</span></span> <span data-ttu-id="f5d03-139">El movimiento de vuelta al almacén habitual se puede procesar mediante un diario de recepción de artículos que se pueda inicializar durante el Informe como proceso terminado.</span><span class="sxs-lookup"><span data-stu-id="f5d03-139">The movement back to the regular warehouse can be processed via an Item arrival journal that can be initialized during the Report as finished process.</span></span>

### <a name="ended"></a><span data-ttu-id="f5d03-140">Finalizado</span><span class="sxs-lookup"><span data-stu-id="f5d03-140">Ended</span></span>

<span data-ttu-id="f5d03-141">Cuando se finaliza una orden de cuarentena, el artículo se traslada desde el almacén de cuarentena de nuevo al almacén habitual.</span><span class="sxs-lookup"><span data-stu-id="f5d03-141">When a quarantine order is ended, the item is moved from the quarantine warehouse back to the regular warehouse.</span></span> <span data-ttu-id="f5d03-142">El estado de la transacción de artículos se establece en **Vendido** en el almacén de cuarentena y en **Comprado** en el almacén de cuarentena.</span><span class="sxs-lookup"><span data-stu-id="f5d03-142">The status of the item transaction is set to **Sold** at the quarantine warehouse and **Purchased** at the regular warehouse.</span></span>

## <a name="quarantine-order-scrap"></a><span data-ttu-id="f5d03-143">Eliminación de órdenes de cuarentena</span><span class="sxs-lookup"><span data-stu-id="f5d03-143">Quarantine order scrap</span></span>
<span data-ttu-id="f5d03-144">Como parte del proceso de la orden de cuarentena, puede eliminar inventario.</span><span class="sxs-lookup"><span data-stu-id="f5d03-144">As part of the quarantine order process, you can scrap inventory.</span></span> <span data-ttu-id="f5d03-145">Al procesar el residuo, el estado del inventario se establecerá en **Vendido** por una transacción de emisión del almacén de cuarentena.</span><span class="sxs-lookup"><span data-stu-id="f5d03-145">When you process scrap, the status of the inventory will be set to **Sold** by an issue transaction from the quarantine warehouse.</span></span>

<a name="additional-resources"></a><span data-ttu-id="f5d03-146">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="f5d03-146">Additional resources</span></span>
--------

[<span data-ttu-id="f5d03-147">Bloqueo del inventario</span><span class="sxs-lookup"><span data-stu-id="f5d03-147">Inventory blocking</span></span>](inventory-blocking.md)
