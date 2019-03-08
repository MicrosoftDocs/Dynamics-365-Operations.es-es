---
title: Crear un pedido de reabastecimiento de entrega
description: Este procedimiento muestra cómo crear un pedido de reabastecimiento de entrega donde puede seguir la entrega prevista de un proveedor en su inventario de entrega.
author: mkirknel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ConsignmentReplenishmentOrder, ConsignmentReplenishmentOrderCreate, InventTrans, ConsignmentDraftReplenishmentOrderJournal, InventOnhandMovement, InventOnhandItem, InventItemIdLookupSimple
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9d3e33008d04ea8bb7d145c7b63cec23a4a45dd2
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "315507"
---
# <a name="create-a-consignment-replenishment-order"></a><span data-ttu-id="f63b0-103">Crear un pedido de reabastecimiento de entrega</span><span class="sxs-lookup"><span data-stu-id="f63b0-103">Create a consignment replenishment order</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f63b0-104">Este procedimiento muestra cómo crear un pedido de reabastecimiento de entrega donde puede seguir la entrega prevista de un proveedor en su inventario de entrega.</span><span class="sxs-lookup"><span data-stu-id="f63b0-104">This procedure shows how to create a consignment replenishment order where you can track the expected delivery from a vendor into your consignment inventory.</span></span> <span data-ttu-id="f63b0-105">También muestra cómo registrar una recepción de productos para registrar el inventario de entrega como inventario disponible propiedad del proveedor.</span><span class="sxs-lookup"><span data-stu-id="f63b0-105">It also shows how to record a receipt of products so that the consignment inventory is registered as on-hand inventory owned by the vendor.</span></span> <span data-ttu-id="f63b0-106">Este procedimiento normalmente lo haría un profesional de compras.</span><span class="sxs-lookup"><span data-stu-id="f63b0-106">This procedure would typically be done by a procurement professional.</span></span> <span data-ttu-id="f63b0-107">Puede usar esta guía en la empresa de datos de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="f63b0-107">You can use this guide in demo data company USMF.</span></span> <span data-ttu-id="f63b0-108">Este procedimiento es para una función que se ha agregado en la versión 1611 de Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="f63b0-108">This procedure is for a feature that was added in Dynamics 365 for Operations, version 1611.</span></span>




## <a name="create-a-consignment-replenishment-order"></a><span data-ttu-id="f63b0-109">Crear un pedido de reabastecimiento de entrega</span><span class="sxs-lookup"><span data-stu-id="f63b0-109">Create a consignment replenishment order</span></span>
1. <span data-ttu-id="f63b0-110">Ir a Adquisición y abastecimiento > Envío > Pedidos de reabastecimiento de envío.</span><span class="sxs-lookup"><span data-stu-id="f63b0-110">Go to Procurement and sourcing > Consignment > Consignment replenishment orders.</span></span>
2. <span data-ttu-id="f63b0-111">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="f63b0-111">Click New.</span></span>
3. <span data-ttu-id="f63b0-112">En el campo Cuenta del proveedor, seleccione el proveedor US-104.</span><span class="sxs-lookup"><span data-stu-id="f63b0-112">In the Vendor account field, select vendor US-104.</span></span>
    * <span data-ttu-id="f63b0-113">Debe seleccionar un proveedor registrado como propietario en la página Propietarios de inventario.</span><span class="sxs-lookup"><span data-stu-id="f63b0-113">You must select a vendor that’s registered as an owner in the Inventory owners page.</span></span>  
4. <span data-ttu-id="f63b0-114">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="f63b0-114">Click OK.</span></span>
5. <span data-ttu-id="f63b0-115">Haga clic en Agregar línea.</span><span class="sxs-lookup"><span data-stu-id="f63b0-115">Click Add line.</span></span>
6. <span data-ttu-id="f63b0-116">En el campo Número de artículo, escriba "M9211CI".</span><span class="sxs-lookup"><span data-stu-id="f63b0-116">In the Item number field, type M9211CI.</span></span>
    * <span data-ttu-id="f63b0-117">Debe seleccionar un artículo que se ha configurado como inventario de entrega.</span><span class="sxs-lookup"><span data-stu-id="f63b0-117">You must select an item that is set up for consignment inventory.</span></span>  
7. <span data-ttu-id="f63b0-118">En el campo Cantidad, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="f63b0-118">In the Quantity field, enter a number.</span></span>
8. <span data-ttu-id="f63b0-119">En el campo Fecha de entrega solicitada, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="f63b0-119">In the Requested delivery date field, enter a date.</span></span>
    * <span data-ttu-id="f63b0-120">El motor MRP usa las fechas solicitada y confirmada para la llegada esperada de las mercancías.</span><span class="sxs-lookup"><span data-stu-id="f63b0-120">The requested and confirmed dates are used by the MRP engine for the expected arrival of the goods.</span></span>  
9. <span data-ttu-id="f63b0-121">En el campo Fecha de entrega confirmada, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="f63b0-121">In the Confirmed delivery date field, enter a date.</span></span>
10. <span data-ttu-id="f63b0-122">Expanda la sección Detalles de línea.</span><span class="sxs-lookup"><span data-stu-id="f63b0-122">Expand the Line details section.</span></span>
11. <span data-ttu-id="f63b0-123">Haga clic en la ficha Dimensiones de inventario.</span><span class="sxs-lookup"><span data-stu-id="f63b0-123">Click the Inventory dimensions tab.</span></span>
12. <span data-ttu-id="f63b0-124">Para mostrar el propietario en el campo Propietario de las dimensiones de inventario, actualice la página.</span><span class="sxs-lookup"><span data-stu-id="f63b0-124">To show the owner in the Inventory dimensions owner field, refresh the page.</span></span>
    * <span data-ttu-id="f63b0-125">Ahora el proveedor US-104 aparece como propietario.</span><span class="sxs-lookup"><span data-stu-id="f63b0-125">Vendor US-104 is now listed as the owner.</span></span>  

## <a name="check-the-inventory-transaction-status"></a><span data-ttu-id="f63b0-126">Compruebe el estado de la transacción de inventario</span><span class="sxs-lookup"><span data-stu-id="f63b0-126">Check the inventory transaction status</span></span>
1. <span data-ttu-id="f63b0-127">Haga clic en Inventario.</span><span class="sxs-lookup"><span data-stu-id="f63b0-127">Click Inventory.</span></span>
2. <span data-ttu-id="f63b0-128">Haga clic en Transacciones.</span><span class="sxs-lookup"><span data-stu-id="f63b0-128">Click Transactions.</span></span>
3. <span data-ttu-id="f63b0-129">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="f63b0-129">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="f63b0-130">Tenga en cuenta que el campo Recepción está establecido en Pedido.</span><span class="sxs-lookup"><span data-stu-id="f63b0-130">Notice that the Receipt field is set to Ordered.</span></span>  
4. <span data-ttu-id="f63b0-131">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="f63b0-131">Close the page.</span></span>

## <a name="receive-items"></a><span data-ttu-id="f63b0-132">Recibir artículos</span><span class="sxs-lookup"><span data-stu-id="f63b0-132">Receive items</span></span>
1. <span data-ttu-id="f63b0-133">Haga clic en Recepción de producto.</span><span class="sxs-lookup"><span data-stu-id="f63b0-133">Click Product receipt.</span></span>
2. <span data-ttu-id="f63b0-134">En el campo Recepción de producto externa, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="f63b0-134">In the External product receipt field, type a value.</span></span>
3. <span data-ttu-id="f63b0-135">En el campo Cantidad, escriba un número que sea inferior al número que se muestra aquí.</span><span class="sxs-lookup"><span data-stu-id="f63b0-135">In the Quantity field, enter a number that’s lower than the number that’s shown there.</span></span> 
4. <span data-ttu-id="f63b0-136">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="f63b0-136">Click OK.</span></span>

## <a name="check-the-on-hand-inventory"></a><span data-ttu-id="f63b0-137">Compruebe el inventario disponible</span><span class="sxs-lookup"><span data-stu-id="f63b0-137">Check the on-hand inventory</span></span>
1. <span data-ttu-id="f63b0-138">Haga clic en Inventario.</span><span class="sxs-lookup"><span data-stu-id="f63b0-138">Click Inventory.</span></span>
2. <span data-ttu-id="f63b0-139">Haga clic en Disponible.</span><span class="sxs-lookup"><span data-stu-id="f63b0-139">Click On-hand.</span></span>
3. <span data-ttu-id="f63b0-140">Haga clic en Visión general.</span><span class="sxs-lookup"><span data-stu-id="f63b0-140">Click Overview.</span></span>
    * <span data-ttu-id="f63b0-141">Los artículos que se han recibido como inventario de entrega propiedad del proveedor están disponibles.</span><span class="sxs-lookup"><span data-stu-id="f63b0-141">The items that have been received as consignment inventory owned by the vendor are available on-hand.</span></span> <span data-ttu-id="f63b0-142">La cantidad restante en el pedido de reabastecimiento de entrega se muestra en el campo Pedido en total.</span><span class="sxs-lookup"><span data-stu-id="f63b0-142">The remaining quantity on the consignment replenishment order is shown in the Ordered in total field.</span></span>  
4. <span data-ttu-id="f63b0-143">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="f63b0-143">Close the page.</span></span>
5. <span data-ttu-id="f63b0-144">Haga clic en Cerrar.</span><span class="sxs-lookup"><span data-stu-id="f63b0-144">Click Close.</span></span>

