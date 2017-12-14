---
title: Proceso de salida
description: "En este tema se proporciona información general del proceso de salida en la gestión del inventario."
author: perlynne
manager: AnnBe
ms.date: 10/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WMSOrder, WMSShipment, MCRPickingWorkbench, WMSPickingRegistration, CustomFilterGroup
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Core, Operations
ms.custom: 274363
ms.assetid: 375807b2-a426-4f1b-bc1f-2fe00fd48413
ms.search.region: global
ms.search.industry: Distribution
ms.author: perlynne
ms.dyn365.ops.intro: AX 7.0.0
ms.search.validFrom: 2016-02-28
ms.translationtype: HT
ms.sourcegitcommit: 0ca19ab9ed7a52328c5dd5252c418bb9343bdc2b
ms.openlocfilehash: f2cae64263769b5168d2bb9614d6388b42e23b49
ms.contentlocale: es-es
ms.lasthandoff: 12/14/2017

---

# <a name="outbound-process"></a><span data-ttu-id="aaea8-103">Proceso de salida</span><span class="sxs-lookup"><span data-stu-id="aaea8-103">Outbound process</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="aaea8-104">En este tema se proporciona información general del proceso de salida en la gestión del inventario.</span><span class="sxs-lookup"><span data-stu-id="aaea8-104">This topic provides an overview of the outbound process in Inventory management.</span></span>

## <a name="output-orders"></a><span data-ttu-id="aaea8-105">Pedidos de salida</span><span class="sxs-lookup"><span data-stu-id="aaea8-105">Output orders</span></span>

<span data-ttu-id="aaea8-106">Los pedidos de salida se usan para vincular las líneas de pedido de ventas y transferirlas mediante los procesos de selección de salida que usan listas de selección.</span><span class="sxs-lookup"><span data-stu-id="aaea8-106">Output orders are used to link sales order lines and transfer order lines with the outbound picking processes that use picking lists.</span></span>

<span data-ttu-id="aaea8-107">Cuando se crean las listas de selección a partir de los pedidos de ventas o de transferencia, se crean automáticamente los pedidos de salida o de envío.</span><span class="sxs-lookup"><span data-stu-id="aaea8-107">When picking lists are generated from either sales orders or transfer orders, output orders and shipments are automatically created.</span></span> <span data-ttu-id="aaea8-108">Una lista de selección tiene una relación unívoca con un envío.</span><span class="sxs-lookup"><span data-stu-id="aaea8-108">A picking list has a one-to-one relationship with a shipment.</span></span> <span data-ttu-id="aaea8-109">El envío de pedidos de transferencia o el albarán del pedido de ventas se puede procesar desde el mismo envío.</span><span class="sxs-lookup"><span data-stu-id="aaea8-109">The transfer order shipment or the sales order packing slip can be processed from the shipment.</span></span> 

<span data-ttu-id="aaea8-110">El siguiente diagrama muestra una vista general del proceso de pedidos de salida.</span><span class="sxs-lookup"><span data-stu-id="aaea8-110">The following diagram shows an overview of the process for outbound orders.</span></span> 

<span data-ttu-id="aaea8-111">[![Vista general del proceso de pedidos de salida](./media/outbound-order.png)](./media/outbound-order.png)</span><span class="sxs-lookup"><span data-stu-id="aaea8-111">[![Overview of the outbound order process](./media/outbound-order.png)](./media/outbound-order.png)</span></span>

<span data-ttu-id="aaea8-112">Puede configurar las reglas de salida para determinar cómo desea que el programa gestione el proceso de salida.</span><span class="sxs-lookup"><span data-stu-id="aaea8-112">You can set up outbound rules to define how the program should handle the outbound process.</span></span> <span data-ttu-id="aaea8-113">Puede usar estas reglas para controlar el proceso de envío.</span><span class="sxs-lookup"><span data-stu-id="aaea8-113">You can use these rules to control the shipment process.</span></span> <span data-ttu-id="aaea8-114">En particular, puede usar las reglas para controlar en qué fase del proceso se puede realizar un envío.</span><span class="sxs-lookup"><span data-stu-id="aaea8-114">In particular, you can use the rules to control which stage in the process a shipment can be sent during.</span></span> <span data-ttu-id="aaea8-115">La siguiente configuración indica cómo se gestionan los procesos de salida.</span><span class="sxs-lookup"><span data-stu-id="aaea8-115">The following settings define how the outbound processes are handled.</span></span>

## <a name="picking-route-status-for-sales-and-transfer-orders"></a><span data-ttu-id="aaea8-116">Estado de la ruta de selección para ventas y pedidos de transferencia</span><span class="sxs-lookup"><span data-stu-id="aaea8-116">Picking route status for sales and transfer orders</span></span> 

<span data-ttu-id="aaea8-117">Vaya a **Clientes** \> **Configuración** \> **Parámetros de clientes** y, a continuación, en la pestaña **Actualizaciones**, seleccione un valor en el campo **Estado de la ruta de selección**.</span><span class="sxs-lookup"><span data-stu-id="aaea8-117">Go to **Account receivable** \> **Setup** \> **Account receivable parameters**, and then, on the **Updates** tab, select a value in the **Picking route status** field.</span></span>

<span data-ttu-id="aaea8-118">[![Campo del estado de la ruta de selección para pedidos de ventas](./media/picking-route-status-sales-order.png)](./media/picking-route-status-sales-order.png)</span><span class="sxs-lookup"><span data-stu-id="aaea8-118">[![Picking route status field for sales orders](./media/picking-route-status-sales-order.png)](./media/picking-route-status-sales-order.png)</span></span>

<span data-ttu-id="aaea8-119">Si el campo **Estado de la ruta de selección** se establece en **Completado**, el proceso de selección aparece automáticamente como parte del proceso para crear listas de selección.</span><span class="sxs-lookup"><span data-stu-id="aaea8-119">If the **Picking route status** field is set to **Completed**, the picking process occurs automatically as part of the process of generating picking lists.</span></span> <span data-ttu-id="aaea8-120">Si el campo está establecido en **Activado**, las líneas de la lista de selección se deben actualizar manualmente.</span><span class="sxs-lookup"><span data-stu-id="aaea8-120">If the field is set to **Activated**, the picking list lines must be manually updated.</span></span>

<span data-ttu-id="aaea8-121">La misma configuración se aplica a pedidos de transferencia.</span><span class="sxs-lookup"><span data-stu-id="aaea8-121">The same setup applies to transfer orders.</span></span> <span data-ttu-id="aaea8-122">Vaya a **Gestión del inventario** \> **Configuración** \> **Parámetros de gestión de inventarios y almacenes** y, a continuación, en la pestaña **Transporte**, seleccione un valor en el campo **Estado de la ruta de selección**.</span><span class="sxs-lookup"><span data-stu-id="aaea8-122">Go to **Inventory management** \> **Setup** \> **Inventory and warehouse management parameters**, and then, on the **Transport** tab, select a value in the **Picking route status** field.</span></span>

<span data-ttu-id="aaea8-123">[![Campo del estado de la ruta de selección para pedidos de transferencia](./media/picking-route-status-transfer-order.png)](./media/picking-route-status-transfer-order.png)</span><span class="sxs-lookup"><span data-stu-id="aaea8-123">[![Picking route status field for transfer orders](./media/picking-route-status-transfer-order.png)](./media/picking-route-status-transfer-order.png)</span></span>

## <a name="end-output-inventory-orders"></a><span data-ttu-id="aaea8-124">Completar los pedidos de inventario de salida</span><span class="sxs-lookup"><span data-stu-id="aaea8-124">End output inventory orders</span></span>

<span data-ttu-id="aaea8-125">Vaya a **Gestión del inventario** \> **Configuración** \> **Parámetros de gestión de inventarios y almacenes** y, a continuación, en la pestaña **General** , establezca la opción **Completar pedido de inventario de salida**.</span><span class="sxs-lookup"><span data-stu-id="aaea8-125">Go to **Inventory management** \> **Setup** \> **Inventory and warehouse management parameters**, and then, on the **General** tab, set the **End output inventory order** option.</span></span>

<span data-ttu-id="aaea8-126">[![Opción para completar el pedido de inventario de salida](./media//end-output-inventory-order.png)](./media//end-output-inventory-order.png)</span><span class="sxs-lookup"><span data-stu-id="aaea8-126">[![End output inventory order option](./media//end-output-inventory-order.png)](./media//end-output-inventory-order.png)</span></span>

<span data-ttu-id="aaea8-127">Cuando el trabajador de almacén reduce las cantidades de la lista de selección, las cantidades correspondientes del pedido de inventario se quitarán del envío.</span><span class="sxs-lookup"><span data-stu-id="aaea8-127">When the warehouse worker reduces the picking list quantities, then the corresponding inventory order quantities will be removed from the shipment.</span></span> <span data-ttu-id="aaea8-128">Cuando la lista de selección se actualiza en un momento dado, las cantidades restantes vuelven al pedido si la opción **Completar pedido de inventario de salida** se establece en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="aaea8-128">When the picking list is updated at a point in time, the remaining quantities get reported back to the order if the **End output inventory order** option is set to **Yes**.</span></span> <span data-ttu-id="aaea8-129">Si la opción **Completar pedido de inventario de salida** se establece en **No**, las cantidades restantes se conservan como cantidad de pedido de salida abierta y se deben agregar a una nueva lista de selección como parte de la funcionalidad **Abrir pedidos de salida**.</span><span class="sxs-lookup"><span data-stu-id="aaea8-129">If the **End output inventory order** option is set to **No**, the remaining quantities are kept as an open output order quantity and must be added to a new picking list as part of the **Open output orders** functionality.</span></span> 

<span data-ttu-id="aaea8-130">[![Comando para abrir los pedidos de salida en el menú Funciones](./media/open-output-order.png)](./media/open-output-order.png)</span><span class="sxs-lookup"><span data-stu-id="aaea8-130">[![Open output orders command on the Functions menu](./media/open-output-order.png)](./media/open-output-order.png)</span></span>

<span data-ttu-id="aaea8-131">[![Menú Funciones en la página para abrir los pedidos de salida](./media/open-output-order-function.png)](./media/open-output-order-function.png)</span><span class="sxs-lookup"><span data-stu-id="aaea8-131">[![Functions menu on the Open output orders page](./media/open-output-order-function.png)](./media/open-output-order-function.png)</span></span>

## <a name="reduce-quantity"></a><span data-ttu-id="aaea8-132">Reducir cantidad</span><span class="sxs-lookup"><span data-stu-id="aaea8-132">Reduce quantity</span></span>

<span data-ttu-id="aaea8-133">El tercer parámetro que puede usar como parte del proceso de creación de listas de selección, es el parámetro **Reducir cantidad**.</span><span class="sxs-lookup"><span data-stu-id="aaea8-133">The third parameter that you can use as part of the process of generating picking lists is the **Reduce quantity** parameter.</span></span> <span data-ttu-id="aaea8-134">La configuración de este parámetro funciona igual que la configuración **Reserva** que activa un proceso de reserva como parte del proceso de liberación al almacén.</span><span class="sxs-lookup"><span data-stu-id="aaea8-134">The setting of this parameter works together with the **Reservation** setting that triggers a reservation process as part of the release to the warehouse.</span></span>

<span data-ttu-id="aaea8-135">[![Parámetro Reducir cantidad](./media/reduce-quantity.png)](./media/reduce-quantity.png)</span><span class="sxs-lookup"><span data-stu-id="aaea8-135">[![Reduce quantity parameter](./media/reduce-quantity.png)](./media/reduce-quantity.png)</span></span>

## <a name="example-of-an-outbound-process-for-a-sales-order"></a><span data-ttu-id="aaea8-136">Ejemplo de un proceso de salida de un pedido de ventas</span><span class="sxs-lookup"><span data-stu-id="aaea8-136">Example of an outbound process for a sales order</span></span>

<span data-ttu-id="aaea8-137">En este ejemplo, hay un pedido de ventas para dos artículos.</span><span class="sxs-lookup"><span data-stu-id="aaea8-137">For this example, there is a sales order for two items.</span></span> <span data-ttu-id="aaea8-138">Durante la creación de la lista de selección, debe seleccionar el parámetro **Reducir cantidad**.</span><span class="sxs-lookup"><span data-stu-id="aaea8-138">During picking list generation, you select the **Reduce quantity** parameter.</span></span> <span data-ttu-id="aaea8-139">Por lo tanto, liberará y creará líneas de selección solo para aquel inventario disponible.</span><span class="sxs-lookup"><span data-stu-id="aaea8-139">Therefore, you release and create picking lines only for available on-hand inventory.</span></span> <span data-ttu-id="aaea8-140">Se debe informar de la selección mediante un proceso de registro de listas de selección**Estado de la ruta de selección** = (**Activado**).</span><span class="sxs-lookup"><span data-stu-id="aaea8-140">The picking must be reported via a registration process for picking lists (**Picking route status** = **Activated**).</span></span>

<span data-ttu-id="aaea8-141">El inventario que no se haya reservado se reservará durante la creación de la lista de selección.</span><span class="sxs-lookup"><span data-stu-id="aaea8-141">The inventory that hasn't already been reserved is reserved during picking list generation.</span></span> <span data-ttu-id="aaea8-142">El inventario que no está disponible se puede quitar del pedido de ventas o se puede liberar al almacén para realizar más adelante un proceso de salida, cuando el inventario esté disponible para realizar una selección.</span><span class="sxs-lookup"><span data-stu-id="aaea8-142">The unavailable inventory can be either removed from the sales order or released to the warehouse for outbound processing later, when inventory is available for picking.</span></span>

<span data-ttu-id="aaea8-143">[![Actualizar la lista de selección](./media/update-picking-list.png)](./media/update-picking-list.png)</span><span class="sxs-lookup"><span data-stu-id="aaea8-143">[![Update the picking list](./media/update-picking-list.png)](./media/update-picking-list.png)</span></span>

<span data-ttu-id="aaea8-144">Tan pronto como todas las líneas de selección hayan sido utilizadas en la página **Registro de la lista de selección**, se completa el envío asociado.</span><span class="sxs-lookup"><span data-stu-id="aaea8-144">As soon as all the picking lines have been picked on the **Picking list registration** page, the associated shipment is completed.</span></span> <span data-ttu-id="aaea8-145">El proceso de los albaranes del pedido de ventas se podrá inicializar en función del inventario seleccionado.</span><span class="sxs-lookup"><span data-stu-id="aaea8-145">The process for sales order packing slips can then be initialized based on the picked inventory.</span></span>

<span data-ttu-id="aaea8-146">[![Actualizar envíos salientes](./media/outbound-shipments.png)](./media/outbound-shipments.png)</span><span class="sxs-lookup"><span data-stu-id="aaea8-146">[![Update outbound shipments](./media/outbound-shipments.png)](./media/outbound-shipments.png)</span></span>

