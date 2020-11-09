---
title: Registrar la recepción de mercancías en el pedido de compra
description: Este tema explica cómo registrar la recepción de mercancías directamente en un pedido de compra.
author: mkirknel
manager: tfehr
ms.date: 07/09/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart, PurchCreateOrder, InventItemIdLookupPurchase, PurchEditLines
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: bd8ca2cbd24f326c4eaf9cd39e32de0eca81149d
ms.sourcegitcommit: e3f4dd2257a3255c2982f4fc7b72a1121275b88a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "4018615"
---
# <a name="record-the-receipt-of-goods-on-the-purchase-order"></a><span data-ttu-id="80dcf-103">Registrar la recepción de mercancías en el pedido de compra</span><span class="sxs-lookup"><span data-stu-id="80dcf-103">Record the receipt of goods on the purchase order</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="80dcf-104">Este tema explica cómo registrar la recepción de mercancías directamente en un pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="80dcf-104">This topic explains how to record receipt of goods directly on a purchase order.</span></span> <span data-ttu-id="80dcf-105">También es posible registrar la recepción de productos en el almacén y, a continuación, registrarla después en el pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="80dcf-105">It's also possible to register product receipt in the warehouse, and then later record it on the purchase order.</span></span> <span data-ttu-id="80dcf-106">Esta tarea se realiza normalmente por un agente de compras o un coordinador de Proveedores.</span><span class="sxs-lookup"><span data-stu-id="80dcf-106">This task is typically done by a purchasing agent or an accounts payable coordinator.</span></span> <span data-ttu-id="80dcf-107">El ejemplo mostrado en esta guía se puede utilizar en la empresa de datos de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="80dcf-107">The example shown in this guide can be used in the USMF demo data company.</span></span> <span data-ttu-id="80dcf-108">El ejemplo incluye pasos para crear un pedido de compra sencillo para que pueda reproducir el procedimiento como guía de tareas.</span><span class="sxs-lookup"><span data-stu-id="80dcf-108">The example includes steps to create a simple purchase order so that you can play the procedure as a task guide.</span></span> <span data-ttu-id="80dcf-109">Si estuviera utilizando el procedimiento en sus propios datos, empezaría en la subtarea **Registrar recepción de mercancías**.</span><span class="sxs-lookup"><span data-stu-id="80dcf-109">If you were using the procedure on your own data, you would start at the **Record receipt of goods** subtask.</span></span>


## <a name="prepare-a-new-purchase-order-for-receipt-of-goods"></a><span data-ttu-id="80dcf-110">Preparar un nuevo pedido de compra para la recepción de mercancías</span><span class="sxs-lookup"><span data-stu-id="80dcf-110">Prepare a new purchase order for receipt of goods</span></span>
1. <span data-ttu-id="80dcf-111">Vaya a **Panel de exploración, Módulos > Adquisición y abastecimiento > Pedidos de compra > Todos los pedidos de compra**.</span><span class="sxs-lookup"><span data-stu-id="80dcf-111">Go to **Navigation pane > Modules > Procurement and sourcing > Purchase orders > All purchase orders**.</span></span>
2. <span data-ttu-id="80dcf-112">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="80dcf-112">Select **New**.</span></span>
3. <span data-ttu-id="80dcf-113">En el campo **Cuenta de proveedor** , escriba `US-101`.</span><span class="sxs-lookup"><span data-stu-id="80dcf-113">In the **Vendor account** field, enter `US-101`.</span></span>
4. <span data-ttu-id="80dcf-114">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="80dcf-114">Select **OK**.</span></span>
5. <span data-ttu-id="80dcf-115">En el campo **Número de artículo** , especifique `M0001`.</span><span class="sxs-lookup"><span data-stu-id="80dcf-115">In the **Item number** field, enter `M0001`.</span></span>
6. <span data-ttu-id="80dcf-116">En el campo **Cantidad** , especifique `5`.</span><span class="sxs-lookup"><span data-stu-id="80dcf-116">In the **Quantity** field, enter `5`.</span></span>
7. <span data-ttu-id="80dcf-117">En el panel de acciones, selecione **Compra.**</span><span class="sxs-lookup"><span data-stu-id="80dcf-117">On the Action Pane, select **Purchase**.</span></span>
8. <span data-ttu-id="80dcf-118">Seleccione **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="80dcf-118">Select **Confirm**.</span></span>

## <a name="record-receipt-of-goods"></a><span data-ttu-id="80dcf-119">Registrar recepción de mercancías</span><span class="sxs-lookup"><span data-stu-id="80dcf-119">Record receipt of goods</span></span>
1. <span data-ttu-id="80dcf-120">En el panel de acciones, seleccione **Recibir**.</span><span class="sxs-lookup"><span data-stu-id="80dcf-120">On the Action Pane, select **Receive**.</span></span>
2. <span data-ttu-id="80dcf-121">Seleccione **Recepción de producto**.</span><span class="sxs-lookup"><span data-stu-id="80dcf-121">Select **Product receipt**.</span></span> <span data-ttu-id="80dcf-122">El campo **Cantidad** le permite seleccionar diferentes opciones para la cantidad que desea recibir.</span><span class="sxs-lookup"><span data-stu-id="80dcf-122">The **Quantity** field allows you to select different options for the quantity that you want to receive.</span></span> <span data-ttu-id="80dcf-123">Por ejemplo, si se ha registrado una cantidad anteriormente en el almacén, puede seleccionar **Cantidad registrada**.</span><span class="sxs-lookup"><span data-stu-id="80dcf-123">For example, if a quantity has previously been registered in the warehouse, you can select **Registered quantity**.</span></span> <span data-ttu-id="80dcf-124">Para este ejemplo, utilice el valor **Cantidad pedida**.</span><span class="sxs-lookup"><span data-stu-id="80dcf-124">For this example, use the value **Ordered quantity**.</span></span>
3. <span data-ttu-id="80dcf-125">Expanda la sección **Información general**.</span><span class="sxs-lookup"><span data-stu-id="80dcf-125">Expand the **Overview** section.</span></span>
4. <span data-ttu-id="80dcf-126">En el campo **Recepción de producto** , escriba cualquier valor.</span><span class="sxs-lookup"><span data-stu-id="80dcf-126">In the **Product receipt** field, type any value.</span></span> <span data-ttu-id="80dcf-127">Este campo se utiliza para especificar una referencia que se usará como asiento para el diario de recepción de productos.</span><span class="sxs-lookup"><span data-stu-id="80dcf-127">This field is used to enter a reference that will be used as voucher for the product receipt journal.</span></span>  
5. <span data-ttu-id="80dcf-128">Expanda la sección **Líneas**.</span><span class="sxs-lookup"><span data-stu-id="80dcf-128">Expand the **Lines** section.</span></span>
6. <span data-ttu-id="80dcf-129">Establezca el valor de **Cantidad** en '4'.</span><span class="sxs-lookup"><span data-stu-id="80dcf-129">Set **Quantity** to '4'.</span></span> <span data-ttu-id="80dcf-130">Aquí puede especificar manualmente la cantidad que se está recibiendo para cada línea del pedido.</span><span class="sxs-lookup"><span data-stu-id="80dcf-130">Here you are able to manually specify the quantity that is being received for each line on the order.</span></span>  
7. <span data-ttu-id="80dcf-131">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="80dcf-131">Select **OK**.</span></span> <span data-ttu-id="80dcf-132">Las mercancías se han registrado ahora como recibidas en el pedido de compra y se ha creado un diario de recepción de producto como documento para reflejar esto.</span><span class="sxs-lookup"><span data-stu-id="80dcf-132">The goods have now been recorded as received on the purchase order, and a product receipt journal has been created as document to reflect this.</span></span> <span data-ttu-id="80dcf-133">Puede utilizar la acción Recepción de producto para revisar los diarios creados con el pedido de compra y ver qué se ha recibido y cuándo.</span><span class="sxs-lookup"><span data-stu-id="80dcf-133">You can use the Product receipt action to review the journals created with the purchase order, and see what was received, and when.</span></span>  

