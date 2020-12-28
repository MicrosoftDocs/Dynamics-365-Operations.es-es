---
title: Crear un pedido de producción
description: Este procedimiento muestra cómo crear un pedido de producción.
author: johanhoffmann
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdTableListPage, ProdTableCreate, ProdTable, ProdBOM, ProdRoute, ProdJournalCreate
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ce08532b8281d730cd5fae4ebd634a08c5baeedd
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4436568"
---
# <a name="create-a-production-order"></a><span data-ttu-id="4906d-103">Crear un pedido de producción</span><span class="sxs-lookup"><span data-stu-id="4906d-103">Create a production order</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="4906d-104">Este procedimiento muestra cómo crear un pedido de producción.</span><span class="sxs-lookup"><span data-stu-id="4906d-104">This procedure shows how to create a production order.</span></span> <span data-ttu-id="4906d-105">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="4906d-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="4906d-106">Este es el primer procedimiento de siete que explica el ciclo de vida del pedido de producción.</span><span class="sxs-lookup"><span data-stu-id="4906d-106">This is the first procedure out of seven which explains the production order lifecycle.</span></span>


## <a name="create-a-production-order"></a><span data-ttu-id="4906d-107">Crear un pedido de producción</span><span class="sxs-lookup"><span data-stu-id="4906d-107">Create a production order</span></span>
1. <span data-ttu-id="4906d-108">Vaya a Control de producción > Pedidos de producción > Todos los pedidos de producción.</span><span class="sxs-lookup"><span data-stu-id="4906d-108">Go to Production control > Production orders > All production orders.</span></span>
2. <span data-ttu-id="4906d-109">Haga clic en Nuevo pedido de producción.</span><span class="sxs-lookup"><span data-stu-id="4906d-109">Click New production order.</span></span>
3. <span data-ttu-id="4906d-110">En el campo Código de artículo, escriba 'D0001'.</span><span class="sxs-lookup"><span data-stu-id="4906d-110">In the Item number field, type 'D0001'.</span></span>
4. <span data-ttu-id="4906d-111">En el campo Entrega, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="4906d-111">In the Delivery field, enter a date.</span></span>
    * <span data-ttu-id="4906d-112">La fecha de entrega indica si el pedido de producción debe completarse para entregarlo a tiempo.</span><span class="sxs-lookup"><span data-stu-id="4906d-112">The delivery date indicates when the production order should end in order to deliver on time.</span></span> <span data-ttu-id="4906d-113">Esta fecha se puede usar en el proceso de programación.</span><span class="sxs-lookup"><span data-stu-id="4906d-113">This date can be used in the scheduling process.</span></span> <span data-ttu-id="4906d-114">Por ejemplo, puede programar el pedido hacia atrás a partir de la fecha de entrega.</span><span class="sxs-lookup"><span data-stu-id="4906d-114">For example, you can schedule the order backward from the delivery date.</span></span>  
5. <span data-ttu-id="4906d-115">Establezca el valor de cantidad en '20'.</span><span class="sxs-lookup"><span data-stu-id="4906d-115">Set Quantity to '20'.</span></span>
    * <span data-ttu-id="4906d-116">Nota: el campo de número de L. MAT. muestra automáticamente el número de las L. MAT. activa para el artículo actual, pero puede cambiar la L. MAT. para el pedido de producción seleccionando una L. MAT. activa de la lista de versiones de L. MAT. aprobadas.</span><span class="sxs-lookup"><span data-stu-id="4906d-116">Note: The BOM number field automatically displays the number of any active BOM for the current item, but you can change the BOM for the production order by selecting an active BOM from the list of approved BOM versions.</span></span>    <span data-ttu-id="4906d-117">El campo Número de ruta muestra automáticamente el número de la ruta activa para el artículo actual, pero puede cambiar la ruta del pedido de producción seleccionando una ruta activa de la lista de versiones de ruta aprobadas.</span><span class="sxs-lookup"><span data-stu-id="4906d-117">The Route number field automatically displays the number of any active Route for the current item, but you can change the Route for the production order by selecting an active Route from the list of approved Route versions.</span></span>  
6. <span data-ttu-id="4906d-118">Haga clic en Crear.</span><span class="sxs-lookup"><span data-stu-id="4906d-118">Click Create.</span></span>

## <a name="validate-the-production-order"></a><span data-ttu-id="4906d-119">Validar el pedido de producción</span><span class="sxs-lookup"><span data-stu-id="4906d-119">Validate the production order</span></span>
1. <span data-ttu-id="4906d-120">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="4906d-120">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="4906d-121">Haga clic en el vínculo para el número de pedido de producción que acaba de crear.</span><span class="sxs-lookup"><span data-stu-id="4906d-121">Click the link for the production order number that you have just created.</span></span> <span data-ttu-id="4906d-122">Esto permite abrir la página de detalles del pedido.</span><span class="sxs-lookup"><span data-stu-id="4906d-122">This will open the details page for the order.</span></span>  
2. <span data-ttu-id="4906d-123">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="4906d-123">Click Edit.</span></span>
3. <span data-ttu-id="4906d-124">En el campo Entrega, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="4906d-124">In the Delivery field, enter a date.</span></span>
    * <span data-ttu-id="4906d-125">Por ejemplo, puede cambiar la fecha de entrega para el pedido de producción.</span><span class="sxs-lookup"><span data-stu-id="4906d-125">For example, you can change the delivery date for the production order.</span></span>  
4. <span data-ttu-id="4906d-126">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="4906d-126">Click Save.</span></span>
5. <span data-ttu-id="4906d-127">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="4906d-127">Close the page.</span></span>

## <a name="update-the-bom"></a><span data-ttu-id="4906d-128">Actualizar la L. MAT.</span><span class="sxs-lookup"><span data-stu-id="4906d-128">Update the BOM</span></span>
1. <span data-ttu-id="4906d-129">En el panel de acciones, haga clic en Pedido de producción.</span><span class="sxs-lookup"><span data-stu-id="4906d-129">On the Action Pane, click Production order.</span></span>
2. <span data-ttu-id="4906d-130">Haga clic en L. MAT.</span><span class="sxs-lookup"><span data-stu-id="4906d-130">Click BOM.</span></span>
    * <span data-ttu-id="4906d-131">Abrir la página L. MAT. para validar los datos de la L. MAT. que se copiaron de los datos predeterminados al crear el pedido de producción.</span><span class="sxs-lookup"><span data-stu-id="4906d-131">Open the BOM page to validate the BOM data that was copied from the default data when the production order was created.</span></span> <span data-ttu-id="4906d-132">En este procedimiento, es necesario actualizar la cantidad de una L. MAT.</span><span class="sxs-lookup"><span data-stu-id="4906d-132">In this procedure, you need to update the quantity for a BOM.</span></span>  
3. <span data-ttu-id="4906d-133">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="4906d-133">Click Edit.</span></span>
4. <span data-ttu-id="4906d-134">En el campo Cantidad, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="4906d-134">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="4906d-135">Cambiar la cantidad de la línea de L. MAT. afecta a la estimación de coste de consumo de material para el pedido de producción.</span><span class="sxs-lookup"><span data-stu-id="4906d-135">Changing the quantity on the BOM line affects the cost estimate of material consumption for the production order.</span></span>  
5. <span data-ttu-id="4906d-136">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="4906d-136">Click Save.</span></span>
6. <span data-ttu-id="4906d-137">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="4906d-137">Close the page.</span></span>

## <a name="update-the-production-route"></a><span data-ttu-id="4906d-138">Actualizar la ruta de producción</span><span class="sxs-lookup"><span data-stu-id="4906d-138">Update the production route</span></span>
1. <span data-ttu-id="4906d-139">En el panel de acciones, haga clic en Pedido de producción.</span><span class="sxs-lookup"><span data-stu-id="4906d-139">On the Action Pane, click Production order.</span></span>
2. <span data-ttu-id="4906d-140">Haga clic en Ruta.</span><span class="sxs-lookup"><span data-stu-id="4906d-140">Click Route.</span></span>
    * <span data-ttu-id="4906d-141">Abra la página Ruta para validar los datos de la ruta de producción que se copiaron de los datos predeterminados al crear el pedido.</span><span class="sxs-lookup"><span data-stu-id="4906d-141">Open the Route page to validate the data of the production route that was copied from the default data when the order was created.</span></span> <span data-ttu-id="4906d-142">En este procedimiento, es necesario actualizar la cantidad de una de las operaciones de la ruta de producción.</span><span class="sxs-lookup"><span data-stu-id="4906d-142">In this procedure, you need to update the quantity for one of the operations in the production route.</span></span>  
3. <span data-ttu-id="4906d-143">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="4906d-143">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="4906d-144">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="4906d-144">Click Edit.</span></span>
5. <span data-ttu-id="4906d-145">En el campo Cantidad de proceso, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="4906d-145">In the Process qty. field, enter a number.</span></span>
    * <span data-ttu-id="4906d-146">El cambio del tiempo de proceso afecta al consumo de ruta estimado y al coste del pedido de producción.</span><span class="sxs-lookup"><span data-stu-id="4906d-146">Changing the process time affects the estimated route consumption and the cost of the production order.</span></span>  
6. <span data-ttu-id="4906d-147">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="4906d-147">Click Save.</span></span>
7. <span data-ttu-id="4906d-148">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="4906d-148">Close the page.</span></span>

