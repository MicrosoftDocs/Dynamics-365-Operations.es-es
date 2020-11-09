---
title: Crear un pedido de reabastecimiento de entrega
description: Este tema explica cómo crear un pedido de reabastecimiento de entrega donde puede seguir la entrega prevista de un proveedor en su inventario de entrega.
author: mkirknel
manager: tfehr
ms.date: 08/19/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ConsignmentReplenishmentOrder, ConsignmentReplenishmentOrderCreate, InventTrans, ConsignmentDraftReplenishmentOrderJournal, InventOnhandMovement, InventOnhandItem, InventItemIdLookupSimple, ConsignmentProductReceiptJournal, ConsignmentReplenishmentOrderLineQuantity
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9e993190150e2d82088390d8db4b7c5ada2b0161
ms.sourcegitcommit: e3f4dd2257a3255c2982f4fc7b72a1121275b88a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "4018362"
---
# <a name="create-a-consignment-replenishment-order"></a><span data-ttu-id="c484d-103">Crear un pedido de reabastecimiento de entrega</span><span class="sxs-lookup"><span data-stu-id="c484d-103">Create a consignment replenishment order</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="c484d-104">Este tema explica cómo crear un pedido de reabastecimiento de entrega donde puede seguir la entrega prevista de un proveedor en su inventario de entrega.</span><span class="sxs-lookup"><span data-stu-id="c484d-104">This topic explains how to create a consignment replenishment order where you can track the expected delivery from a vendor into your consignment inventory.</span></span> <span data-ttu-id="c484d-105">También muestra cómo registrar una recepción de productos para registrar el inventario de entrega como inventario disponible propiedad del proveedor.</span><span class="sxs-lookup"><span data-stu-id="c484d-105">It also shows how to record a receipt of products so that the consignment inventory is registered as on-hand inventory owned by the vendor.</span></span> <span data-ttu-id="c484d-106">Este procedimiento normalmente lo haría un profesional de compras.</span><span class="sxs-lookup"><span data-stu-id="c484d-106">This procedure would typically be done by a procurement professional.</span></span> <span data-ttu-id="c484d-107">Puede usar esta guía en la empresa de datos de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="c484d-107">You can use this guide in demo data company USMF.</span></span> <span data-ttu-id="c484d-108">Este procedimiento es para una función que se ha agregado en la versión 1611 de Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="c484d-108">This procedure is for a feature that was added in Dynamics 365 for Operations, version 1611.</span></span>

## <a name="create-a-consignment-replenishment-order"></a><span data-ttu-id="c484d-109">Crear un pedido de reabastecimiento de entrega</span><span class="sxs-lookup"><span data-stu-id="c484d-109">Create a consignment replenishment order</span></span>
1. <span data-ttu-id="c484d-110">En el panel de exploración, vaya a **Módulos > Adquisición y abastecimiento > Entrega > Pedidos de reabastecimiento de entrega**.</span><span class="sxs-lookup"><span data-stu-id="c484d-110">In the navigation pane, go to **Modules > Procurement and sourcing > Consignment > Consignment replenishment orders**.</span></span>
2. <span data-ttu-id="c484d-111">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="c484d-111">Select **New**.</span></span>
3. <span data-ttu-id="c484d-112">En el campo **Cuenta de proveedor** , seleccione el proveedor **US-104** (es preciso seleccionar un proveedor que esté registrado como propietario en la página **propietarios de inventario** ).</span><span class="sxs-lookup"><span data-stu-id="c484d-112">In the **Vendor account** field, select vendor **US-104** (you must select a vendor that's registered as an owner in the **inventory owners** page).</span></span> 
4. <span data-ttu-id="c484d-113">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c484d-113">Select **OK**.</span></span>
5. <span data-ttu-id="c484d-114">Seleccione **Agregar línea**.</span><span class="sxs-lookup"><span data-stu-id="c484d-114">Select **Add line**.</span></span>
6. <span data-ttu-id="c484d-115">En el campo **Código de artículo** , escriba `M9211CI` (debe seleccionar un artículo que se haya configurado como inventario de envío).</span><span class="sxs-lookup"><span data-stu-id="c484d-115">In the **Item number** field, type `M9211CI` (you must select an item that is set up for consignment inventory).</span></span>
7. <span data-ttu-id="c484d-116">En el campo **Cantidad** , especifique un número.</span><span class="sxs-lookup"><span data-stu-id="c484d-116">In the **Quantity** field, enter a number.</span></span>
8. <span data-ttu-id="c484d-117">En el campo **Fecha de entrega solicitada** , especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="c484d-117">In the **Requested delivery date** field, enter a date.</span></span> <span data-ttu-id="c484d-118">El motor MRP usa las fechas solicitada y confirmada para la llegada esperada de las mercancías.</span><span class="sxs-lookup"><span data-stu-id="c484d-118">The requested and confirmed dates are used by the MRP engine for the expected arrival of the goods.</span></span>  
9. <span data-ttu-id="c484d-119">En el campo **Fecha de entrega confirmada** , especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="c484d-119">In the **Confirmed delivery date** field, enter a date.</span></span>
10. <span data-ttu-id="c484d-120">Expanda la sección **Detalles de línea.**</span><span class="sxs-lookup"><span data-stu-id="c484d-120">Expand the **Line details** section.</span></span>
11. <span data-ttu-id="c484d-121">Seleccionar la pestaña **Dimensiones del inventario**</span><span class="sxs-lookup"><span data-stu-id="c484d-121">Select the **Inventory dimensions** tab.</span></span>
12. <span data-ttu-id="c484d-122">Para mostrar el propietario en el campo **Propietario de las dimensiones de inventario** , actualice la página.</span><span class="sxs-lookup"><span data-stu-id="c484d-122">To show the owner in the **Inventory dimensions owner** field, refresh the page.</span></span> <span data-ttu-id="c484d-123">Ahora el proveedor US-104 aparece como propietario.</span><span class="sxs-lookup"><span data-stu-id="c484d-123">Vendor US-104 is now listed as the owner.</span></span>  

## <a name="check-the-inventory-transaction-status"></a><span data-ttu-id="c484d-124">Compruebe el estado de la transacción de inventario</span><span class="sxs-lookup"><span data-stu-id="c484d-124">Check the inventory transaction status</span></span>
1. <span data-ttu-id="c484d-125">Seleccione **Inventario**.</span><span class="sxs-lookup"><span data-stu-id="c484d-125">Select **Inventory**.</span></span>
2. <span data-ttu-id="c484d-126">Seleccione **Transacciones**.</span><span class="sxs-lookup"><span data-stu-id="c484d-126">Select **Transactions**.</span></span>
3. <span data-ttu-id="c484d-127">En la fila que desee, tenga en cuenta que el campo **Recepción** está establecido en **Pedido**.</span><span class="sxs-lookup"><span data-stu-id="c484d-127">In the desired row, notice that the **Receipt** field is set to **Ordered**.</span></span>  
4. <span data-ttu-id="c484d-128">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="c484d-128">Close the page.</span></span>

## <a name="receive-items"></a><span data-ttu-id="c484d-129">Recibir artículos</span><span class="sxs-lookup"><span data-stu-id="c484d-129">Receive items</span></span>
1. <span data-ttu-id="c484d-130">Seleccione **Recepción de producto**.</span><span class="sxs-lookup"><span data-stu-id="c484d-130">Select **Product receipt**.</span></span>
2. <span data-ttu-id="c484d-131">En el campo **Recepción de producto externa** , escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="c484d-131">In the **External product receipt** field, type a value.</span></span>
3. <span data-ttu-id="c484d-132">En el campo **Cantidad** , escriba un número que sea inferior al número que se muestra aquí.</span><span class="sxs-lookup"><span data-stu-id="c484d-132">In the **Quantity** field, enter a number that's lower than the number that's shown there.</span></span> 
4. <span data-ttu-id="c484d-133">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c484d-133">Select **OK**.</span></span>

## <a name="check-the-on-hand-inventory"></a><span data-ttu-id="c484d-134">Compruebe el inventario disponible</span><span class="sxs-lookup"><span data-stu-id="c484d-134">Check the on-hand inventory</span></span>
1. <span data-ttu-id="c484d-135">Seleccione **Inventario**.</span><span class="sxs-lookup"><span data-stu-id="c484d-135">Select **Inventory**.</span></span>
2. <span data-ttu-id="c484d-136">Seleccione **Disponibles**.</span><span class="sxs-lookup"><span data-stu-id="c484d-136">Select **On-hand**.</span></span>
3. <span data-ttu-id="c484d-137">Seleccione **Visión general**.</span><span class="sxs-lookup"><span data-stu-id="c484d-137">Select **Overview**.</span></span> <span data-ttu-id="c484d-138">Los artículos que se han recibido como inventario de entrega propiedad del proveedor están disponibles.</span><span class="sxs-lookup"><span data-stu-id="c484d-138">The items that have been received as consignment inventory owned by the vendor are available on-hand.</span></span> <span data-ttu-id="c484d-139">La cantidad restante en el pedido de reabastecimiento de entrega se muestra en el campo **Pedido en total**.</span><span class="sxs-lookup"><span data-stu-id="c484d-139">The remaining quantity on the consignment replenishment order is shown in the **Ordered in total** field.</span></span>  
4. <span data-ttu-id="c484d-140">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="c484d-140">Close the page.</span></span>

