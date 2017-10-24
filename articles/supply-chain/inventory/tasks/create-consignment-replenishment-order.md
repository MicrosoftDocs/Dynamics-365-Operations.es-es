---
title: Crear un pedido de reabastecimiento de entrega
description: "Este procedimiento muestra cómo crear un pedido de reabastecimiento de entrega donde puede seguir la entrega prevista de un proveedor en su inventario de entrega."
author: mkirknel
manager: AnnBe
ms.date: 10/13/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: f7f8005ec9e723c94d53e6ab81f04ee388c83faa
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-consignment-replenishment-order"></a><span data-ttu-id="90399-103">Crear un pedido de reabastecimiento de entrega</span><span class="sxs-lookup"><span data-stu-id="90399-103">Create a consignment replenishment order</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="90399-104">Este procedimiento muestra cómo crear un pedido de reabastecimiento de entrega donde puede seguir la entrega prevista de un proveedor en su inventario de entrega.</span><span class="sxs-lookup"><span data-stu-id="90399-104">This procedure shows how to create a consignment replenishment order where you can track the expected delivery from a vendor into your consignment inventory.</span></span> <span data-ttu-id="90399-105">También muestra cómo registrar una recepción de productos para registrar el inventario de entrega como inventario disponible propiedad del proveedor.</span><span class="sxs-lookup"><span data-stu-id="90399-105">It also shows how to record a receipt of products so that the consignment inventory is registered as on-hand inventory owned by the vendor.</span></span> <span data-ttu-id="90399-106">Este procedimiento normalmente lo haría un profesional de compras.</span><span class="sxs-lookup"><span data-stu-id="90399-106">This procedure would typically be done by a procurement professional.</span></span> <span data-ttu-id="90399-107">Puede usar esta guía en la empresa de datos de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="90399-107">You can use this guide in demo data company USMF.</span></span> <span data-ttu-id="90399-108">Este procedimiento es para una función que se ha añadido en la versión 1611 de Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="90399-108">This procedure is for a feature that was added in Dynamics 365 for Operations, version 1611.</span></span>




## <a name="create-a-consignment-replenishment-order"></a><span data-ttu-id="90399-109">Crear un pedido de reabastecimiento de entrega</span><span class="sxs-lookup"><span data-stu-id="90399-109">Create a consignment replenishment order</span></span>
1. <span data-ttu-id="90399-110">Ir a Adquisición y abastecimiento > Envío > Pedidos de reabastecimiento de envío.</span><span class="sxs-lookup"><span data-stu-id="90399-110">Go to Procurement and sourcing > Consignment > Consignment replenishment orders.</span></span>
2. <span data-ttu-id="90399-111">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="90399-111">Click New.</span></span>
3. <span data-ttu-id="90399-112">En el campo Cuenta del proveedor, seleccione el proveedor US-104.</span><span class="sxs-lookup"><span data-stu-id="90399-112">In the Vendor account field, select vendor US-104.</span></span>
    * <span data-ttu-id="90399-113">Debe seleccionar un proveedor registrado como propietario en la página Propietarios de inventario.</span><span class="sxs-lookup"><span data-stu-id="90399-113">You must select a vendor that’s registered as an owner in the Inventory owners page.</span></span>  
4. <span data-ttu-id="90399-114">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="90399-114">Click OK.</span></span>
5. <span data-ttu-id="90399-115">Haga clic en Agregar línea.</span><span class="sxs-lookup"><span data-stu-id="90399-115">Click Add line.</span></span>
6. <span data-ttu-id="90399-116">En el campo Número de artículo, escriba "M9211CI".</span><span class="sxs-lookup"><span data-stu-id="90399-116">In the Item number field, type M9211CI.</span></span>
    * <span data-ttu-id="90399-117">Debe seleccionar un artículo que se ha configurado como inventario de entrega.</span><span class="sxs-lookup"><span data-stu-id="90399-117">You must select an item that is set up for consignment inventory.</span></span>  
7. <span data-ttu-id="90399-118">En el campo Cantidad, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="90399-118">In the Quantity field, enter a number.</span></span>
8. <span data-ttu-id="90399-119">En el campo Fecha de entrega solicitada, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="90399-119">In the Requested delivery date field, enter a date.</span></span>
    * <span data-ttu-id="90399-120">El motor MRP usa las fechas solicitada y confirmada para la llegada esperada de las mercancías.</span><span class="sxs-lookup"><span data-stu-id="90399-120">The requested and confirmed dates are used by the MRP engine for the expected arrival of the goods.</span></span>  
9. <span data-ttu-id="90399-121">En el campo Fecha de entrega confirmada, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="90399-121">In the Confirmed delivery date field, enter a date.</span></span>
10. <span data-ttu-id="90399-122">Expanda la sección Detalles de línea.</span><span class="sxs-lookup"><span data-stu-id="90399-122">Expand the Line details section.</span></span>
11. <span data-ttu-id="90399-123">Haga clic en la ficha Dimensiones de inventario.</span><span class="sxs-lookup"><span data-stu-id="90399-123">Click the Inventory dimensions tab.</span></span>
12. <span data-ttu-id="90399-124">Para mostrar el propietario en el campo Propietario de las dimensiones de inventario, actualice la página.</span><span class="sxs-lookup"><span data-stu-id="90399-124">To show the owner in the Inventory dimensions owner field, refresh the page.</span></span>
    * <span data-ttu-id="90399-125">Ahora el proveedor US-104 aparece como propietario.</span><span class="sxs-lookup"><span data-stu-id="90399-125">Vendor US-104 is now listed as the owner.</span></span>  

## <a name="check-the-inventory-transaction-status"></a><span data-ttu-id="90399-126">Compruebe el estado de la transacción de inventario</span><span class="sxs-lookup"><span data-stu-id="90399-126">Check the inventory transaction status</span></span>
1. <span data-ttu-id="90399-127">Haga clic en Inventario.</span><span class="sxs-lookup"><span data-stu-id="90399-127">Click Inventory.</span></span>
2. <span data-ttu-id="90399-128">Haga clic en Transacciones.</span><span class="sxs-lookup"><span data-stu-id="90399-128">Click Transactions.</span></span>
3. <span data-ttu-id="90399-129">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="90399-129">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="90399-130">Tenga en cuenta que el campo Recepción está establecido en Pedido.</span><span class="sxs-lookup"><span data-stu-id="90399-130">Notice that the Receipt field is set to Ordered.</span></span>  
4. <span data-ttu-id="90399-131">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="90399-131">Close the page.</span></span>

## <a name="receive-items"></a><span data-ttu-id="90399-132">Recibir artículos</span><span class="sxs-lookup"><span data-stu-id="90399-132">Receive items</span></span>
1. <span data-ttu-id="90399-133">Haga clic en Recepción de producto.</span><span class="sxs-lookup"><span data-stu-id="90399-133">Click Product receipt.</span></span>
2. <span data-ttu-id="90399-134">En el campo Recepción de producto externa, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="90399-134">In the External product receipt field, type a value.</span></span>
3. <span data-ttu-id="90399-135">En el campo Cantidad, escriba un número que sea inferior al número que se muestra aquí.</span><span class="sxs-lookup"><span data-stu-id="90399-135">In the Quantity field, enter a number that’s lower than the number that’s shown there.</span></span>
4. <span data-ttu-id="90399-136">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="90399-136">Click OK.</span></span>

## <a name="check-the-on-hand-inventory"></a><span data-ttu-id="90399-137">Compruebe el inventario disponible</span><span class="sxs-lookup"><span data-stu-id="90399-137">Check the on-hand inventory</span></span>
1. <span data-ttu-id="90399-138">Haga clic en Inventario.</span><span class="sxs-lookup"><span data-stu-id="90399-138">Click Inventory.</span></span>
2. <span data-ttu-id="90399-139">Haga clic en Disponible.</span><span class="sxs-lookup"><span data-stu-id="90399-139">Click On-hand.</span></span>
3. <span data-ttu-id="90399-140">Haga clic en Visión general.</span><span class="sxs-lookup"><span data-stu-id="90399-140">Click Overview.</span></span>
    * <span data-ttu-id="90399-141">Los artículos que se han recibido como inventario de entrega propiedad del proveedor están disponibles.</span><span class="sxs-lookup"><span data-stu-id="90399-141">The items that have been received as consignment inventory owned by the vendor are available on-hand.</span></span> <span data-ttu-id="90399-142">La cantidad restante en el pedido de reabastecimiento de entrega se muestra en el campo Pedido en total.</span><span class="sxs-lookup"><span data-stu-id="90399-142">The remaining quantity on the consignment replenishment order is shown in the Ordered in total field.</span></span>  
4. <span data-ttu-id="90399-143">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="90399-143">Close the page.</span></span>
5. <span data-ttu-id="90399-144">Haga clic en Cerrar.</span><span class="sxs-lookup"><span data-stu-id="90399-144">Click Close.</span></span>

