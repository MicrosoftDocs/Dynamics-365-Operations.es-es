--- 
title: "Registrar la recepción de mercancías en el pedido de compra"
description: "Este procedimiento le muestra cómo registrar la recepción de mercancías directamente en un pedido de compra."
author: FrankDahl
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PurchTable, PurchCreateOrder, InventItemIdLookupPurchase, PurchEditLines
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: fdahl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 32d71167fdad65cb1dec37671999a497759ca484
ms.openlocfilehash: 991d9923bc8ef9f411ef6120e63b8e31ccddf566
ms.contentlocale: es-es
ms.lasthandoff: 09/11/2018

---
# <a name="record-the-receipt-of-goods-on-the-purchase-order"></a><span data-ttu-id="0589a-103">Registrar la recepción de mercancías en el pedido de compra</span><span class="sxs-lookup"><span data-stu-id="0589a-103">Record the receipt of goods on the purchase order</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="0589a-104">Este procedimiento le muestra cómo registrar la recepción de mercancías directamente en un pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="0589a-104">This procedure shows you how to record receipt of goods directly on a purchase order.</span></span> <span data-ttu-id="0589a-105">También es posible registrar la recepción de productos en el almacén y, a continuación, registrarla después en el pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="0589a-105">It’s also possible to register product receipt in the warehouse, and then later record it on the purchase order.</span></span> <span data-ttu-id="0589a-106">Esta tarea se realiza normalmente por un agente de compras o un coordinador de Proveedores.</span><span class="sxs-lookup"><span data-stu-id="0589a-106">This task is typically done by a purchasing agent or an accounts payable coordinator.</span></span> <span data-ttu-id="0589a-107">El ejemplo mostrado en esta guía se puede utilizar en la empresa de datos de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="0589a-107">The example shown in this guide can be used in the USMF demo data company.</span></span> <span data-ttu-id="0589a-108">El ejemplo incluye pasos para crear un pedido de compra sencillo para que pueda reproducir el procedimiento como guía de tareas.</span><span class="sxs-lookup"><span data-stu-id="0589a-108">The example includes steps to create a simple purchase order so that you can play the procedure as a task guide.</span></span> <span data-ttu-id="0589a-109">Si estuviera utilizando el procedimiento en sus propios datos, empezaría en la subtarea Registrar recepción de mercancías.</span><span class="sxs-lookup"><span data-stu-id="0589a-109">If you were using the procedure on your own data, you would start at the Record receipt of goods subtask.</span></span>


## <a name="prepare-a-new-purchase-order-for-receipt-of-goods"></a><span data-ttu-id="0589a-110">Preparar un nuevo pedido de compra para la recepción de mercancías</span><span class="sxs-lookup"><span data-stu-id="0589a-110">Prepare a new purchase order for receipt of goods</span></span>
1. <span data-ttu-id="0589a-111">Vaya a Adquisición y abastecimiento > Pedidos de compra > Todos los pedidos de compra.</span><span class="sxs-lookup"><span data-stu-id="0589a-111">Go to Procurement and sourcing > Purchase orders > All purchase orders.</span></span>
2. <span data-ttu-id="0589a-112">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="0589a-112">Click New.</span></span>
3. <span data-ttu-id="0589a-113">En el campo Cuenta de proveedor, escriba "US-101".</span><span class="sxs-lookup"><span data-stu-id="0589a-113">In the Vendor account field, enter US-101.</span></span>
4. <span data-ttu-id="0589a-114">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="0589a-114">Click OK.</span></span>
5. <span data-ttu-id="0589a-115">En el campo Número de artículo, especifique M0001.</span><span class="sxs-lookup"><span data-stu-id="0589a-115">In the Item number field, enter M0001.</span></span>
6. <span data-ttu-id="0589a-116">En el campo Cantidad, especifique 5.</span><span class="sxs-lookup"><span data-stu-id="0589a-116">In the Quantity field, enter 5.</span></span>
7. <span data-ttu-id="0589a-117">En el panel de acciones, haga clic en Compra.</span><span class="sxs-lookup"><span data-stu-id="0589a-117">On the Action Pane, click Purchase.</span></span>
8. <span data-ttu-id="0589a-118">Haga clic en Confirmar.</span><span class="sxs-lookup"><span data-stu-id="0589a-118">Click Confirm.</span></span>

## <a name="record-receipt-of-goods"></a><span data-ttu-id="0589a-119">Registrar recepción de mercancías</span><span class="sxs-lookup"><span data-stu-id="0589a-119">Record receipt of goods</span></span>
1. <span data-ttu-id="0589a-120">En el panel de acciones, haga clic en Recibir.</span><span class="sxs-lookup"><span data-stu-id="0589a-120">On the Action Pane, click Receive.</span></span>
2. <span data-ttu-id="0589a-121">Haga clic en Recepción de producto.</span><span class="sxs-lookup"><span data-stu-id="0589a-121">Click Product receipt.</span></span>
    * <span data-ttu-id="0589a-122">El campo Cantidad le permite seleccionar diferentes opciones para la cantidad que desea recibir.</span><span class="sxs-lookup"><span data-stu-id="0589a-122">The Quantity field allows you to select different options for the quantity that you want to receive.</span></span> <span data-ttu-id="0589a-123">Por ejemplo, si se ha registrado una cantidad anteriormente en el almacén, puede seleccionar Cantidad registrada.</span><span class="sxs-lookup"><span data-stu-id="0589a-123">For example, if a quantity has previously been registered in the warehouse, you can select Registered quantity.</span></span>  <span data-ttu-id="0589a-124">Para este ejemplo, utilice el valor Cantidad pedida.</span><span class="sxs-lookup"><span data-stu-id="0589a-124">For this example, use the value Ordered quantity.</span></span>   
3. <span data-ttu-id="0589a-125">En el campo Recepción de producto, escriba cualquier valor.</span><span class="sxs-lookup"><span data-stu-id="0589a-125">In the Product receipt field, type any value.</span></span>
    * <span data-ttu-id="0589a-126">Este campo se utiliza para especificar una referencia que se usará como asiento para el diario de recepción de productos.</span><span class="sxs-lookup"><span data-stu-id="0589a-126">This field is used to enter a reference that will be used as voucher for the product receipt journal.</span></span>  
4. <span data-ttu-id="0589a-127">Expanda la sección Líneas.</span><span class="sxs-lookup"><span data-stu-id="0589a-127">Expand the Lines section.</span></span>
5. <span data-ttu-id="0589a-128">Establezca el valor de cantidad en '4'.</span><span class="sxs-lookup"><span data-stu-id="0589a-128">Set Quantity to '4'.</span></span>
    * <span data-ttu-id="0589a-129">Aquí puede especificar manualmente la cantidad que se está recibiendo para cada línea del pedido.</span><span class="sxs-lookup"><span data-stu-id="0589a-129">Here you are able to manually specify the quantity that is being received for each line on the order.</span></span>  
6. <span data-ttu-id="0589a-130">Contraiga la sección Líneas.</span><span class="sxs-lookup"><span data-stu-id="0589a-130">Collapse the Lines section.</span></span>
7. <span data-ttu-id="0589a-131">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="0589a-131">Click OK.</span></span>
    * <span data-ttu-id="0589a-132">Las mercancías se han registrado ahora como recibidas en el pedido de compra y se ha creado un diario de recepción de producto como documento para reflejar esto.</span><span class="sxs-lookup"><span data-stu-id="0589a-132">The goods have now been recorded as received on the purchase order, and a product receipt journal has been created as document to reflect this.</span></span> <span data-ttu-id="0589a-133">Puede utilizar la acción Recepción de producto para revisar los diarios creados con el pedido de compra y ver qué se ha recibido y cuándo.</span><span class="sxs-lookup"><span data-stu-id="0589a-133">You can use the Product receipt action to review the journals created with the purchase order, and see what was received, and when.</span></span>  


