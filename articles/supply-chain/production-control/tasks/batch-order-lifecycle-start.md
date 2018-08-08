--- 
title: "Ciclo de vida de pedidos de lote desde la creación hasta el inicio"
description: Este procedimiento le lleva por la primera parte del ciclo de vida de un pedido de lote.
author: ShylaThompson
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 13750a69776953094ac3ba72f179e57a0b8a7159
ms.contentlocale: es-es
ms.lasthandoff: 08/07/2018

---
# <a name="batch-order-lifecycle-from-create-to-start"></a><span data-ttu-id="8404b-103">Ciclo de vida de pedidos de lote desde la creación hasta el inicio</span><span class="sxs-lookup"><span data-stu-id="8404b-103">Batch order lifecycle from create to start</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="8404b-104">Este procedimiento le lleva por la primera parte del ciclo de vida de un pedido de lote.</span><span class="sxs-lookup"><span data-stu-id="8404b-104">This procedure takes you through the first part of the life cycle of a batch order.</span></span>

<span data-ttu-id="8404b-105">Desde la creación, la estimación de costes y la programación de trabajos de sobreproducción hasta el inicio real de un pedido de lote.</span><span class="sxs-lookup"><span data-stu-id="8404b-105">From creation, cost estimation, and over production job scheduling to the actual start of a batch order.</span></span>



<span data-ttu-id="8404b-106">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="8404b-106">The demo data company used to create this procedure is USMF.</span></span> 



<span data-ttu-id="8404b-107">Los requisitos previos para ejecutar el procedimiento con otro conjunto de datos son un producto liberado con una versión de ruta y fórmula activa.</span><span class="sxs-lookup"><span data-stu-id="8404b-107">The prerequisites for running the procedure with another dataset are a released product with an active formula and route version.</span></span>


## <a name="create-a-batch-order"></a><span data-ttu-id="8404b-108">Crear un pedido de lote</span><span class="sxs-lookup"><span data-stu-id="8404b-108">Create a batch order</span></span>
1. <span data-ttu-id="8404b-109">Vaya a Todos los pedidos de producción.</span><span class="sxs-lookup"><span data-stu-id="8404b-109">Go to All production orders.</span></span>
2. <span data-ttu-id="8404b-110">Haga clic en Nuevo pedido de lote.</span><span class="sxs-lookup"><span data-stu-id="8404b-110">Click New batch order.</span></span>
3. <span data-ttu-id="8404b-111">En el campo Número de artículo, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="8404b-111">In the Item number field, enter or select a value.</span></span>
4. <span data-ttu-id="8404b-112">Haga clic en Crear.</span><span class="sxs-lookup"><span data-stu-id="8404b-112">Click Create.</span></span>
5. <span data-ttu-id="8404b-113">Use un filtro rápido para filtrar el campo Producción con un valor "b".</span><span class="sxs-lookup"><span data-stu-id="8404b-113">Use the Quick Filter to filter on the Production field with a value of 'b'.</span></span>

## <a name="view-production-formula-and-expected-co-products"></a><span data-ttu-id="8404b-114">Ver fórmula de la producción y coproductos previstos</span><span class="sxs-lookup"><span data-stu-id="8404b-114">View production formula and expected co-products</span></span>
1. <span data-ttu-id="8404b-115">En el panel de acciones, haga clic en Pedido de producción.</span><span class="sxs-lookup"><span data-stu-id="8404b-115">On the Action Pane, click Production order.</span></span>
2. <span data-ttu-id="8404b-116">Haga clic en Fórmula.</span><span class="sxs-lookup"><span data-stu-id="8404b-116">Click Formula.</span></span>
3. <span data-ttu-id="8404b-117">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="8404b-117">Close the page.</span></span>
4. <span data-ttu-id="8404b-118">Haga clic en Productos conjuntos.</span><span class="sxs-lookup"><span data-stu-id="8404b-118">Click Co-products.</span></span>
5. <span data-ttu-id="8404b-119">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="8404b-119">Close the page.</span></span>

## <a name="estimate-the-batch-order"></a><span data-ttu-id="8404b-120">Estimar el pedido de lote</span><span class="sxs-lookup"><span data-stu-id="8404b-120">Estimate the batch order</span></span>
1. <span data-ttu-id="8404b-121">Haga clic en Estimación.</span><span class="sxs-lookup"><span data-stu-id="8404b-121">Click Estimate.</span></span>
2. <span data-ttu-id="8404b-122">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="8404b-122">Click OK.</span></span>
3. <span data-ttu-id="8404b-123">En el panel de acciones, haga clic en Gestionar costes.</span><span class="sxs-lookup"><span data-stu-id="8404b-123">On the Action Pane, click Manage costs.</span></span>
4. <span data-ttu-id="8404b-124">Haga clic en Ver detalles de cálculo.</span><span class="sxs-lookup"><span data-stu-id="8404b-124">Click View calculation details.</span></span>
5. <span data-ttu-id="8404b-125">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="8404b-125">Close the page.</span></span>

## <a name="release-the-batch-order"></a><span data-ttu-id="8404b-126">Liberar el pedido de lote</span><span class="sxs-lookup"><span data-stu-id="8404b-126">Release the batch order</span></span>
1. <span data-ttu-id="8404b-127">En el panel de acciones, haga clic en Pedido de producción.</span><span class="sxs-lookup"><span data-stu-id="8404b-127">On the Action Pane, click Production order.</span></span>
2. <span data-ttu-id="8404b-128">Haga clic en Liberar.</span><span class="sxs-lookup"><span data-stu-id="8404b-128">Click Release.</span></span>
3. <span data-ttu-id="8404b-129">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="8404b-129">Click OK.</span></span>

## <a name="schedule-production-jobs"></a><span data-ttu-id="8404b-130">Programar trabajos de producción</span><span class="sxs-lookup"><span data-stu-id="8404b-130">Schedule production jobs</span></span>
1. <span data-ttu-id="8404b-131">En el panel de acciones, haga clic en Programar.</span><span class="sxs-lookup"><span data-stu-id="8404b-131">On the Action Pane, click Schedule.</span></span>
2. <span data-ttu-id="8404b-132">Haga clic en Programar trabajos.</span><span class="sxs-lookup"><span data-stu-id="8404b-132">Click Schedule jobs.</span></span>
3. <span data-ttu-id="8404b-133">Seleccione No en el campo Capacidad limitada.</span><span class="sxs-lookup"><span data-stu-id="8404b-133">Select No in the Finite capacity field.</span></span>
4. <span data-ttu-id="8404b-134">Seleccione No en el campo Material limitado.</span><span class="sxs-lookup"><span data-stu-id="8404b-134">Select No in the Finite material field.</span></span>
5. <span data-ttu-id="8404b-135">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="8404b-135">Click OK.</span></span>
6. <span data-ttu-id="8404b-136">En el panel de acciones, haga clic en Pedido de producción.</span><span class="sxs-lookup"><span data-stu-id="8404b-136">On the Action Pane, click Production order.</span></span>
7. <span data-ttu-id="8404b-137">Haga clic en Todos los trabajos.</span><span class="sxs-lookup"><span data-stu-id="8404b-137">Click All jobs.</span></span>
8. <span data-ttu-id="8404b-138">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="8404b-138">Close the page.</span></span>

## <a name="start-the-batch-order"></a><span data-ttu-id="8404b-139">Iniciar el pedido de lote</span><span class="sxs-lookup"><span data-stu-id="8404b-139">Start the batch order</span></span>
1. <span data-ttu-id="8404b-140">Haga clic en Inicio.</span><span class="sxs-lookup"><span data-stu-id="8404b-140">Click Start.</span></span>
2. <span data-ttu-id="8404b-141">Haga clic en la pestaña General.</span><span class="sxs-lookup"><span data-stu-id="8404b-141">Click the General tab.</span></span>
3. <span data-ttu-id="8404b-142">Seleccione No en el campo Registrar ahora la lista de selección.</span><span class="sxs-lookup"><span data-stu-id="8404b-142">Select No in the Post picking list now field.</span></span>
4. <span data-ttu-id="8404b-143">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="8404b-143">Click OK.</span></span>
5. <span data-ttu-id="8404b-144">En el panel de acciones, haga clic en Ver.</span><span class="sxs-lookup"><span data-stu-id="8404b-144">On the Action Pane, click View.</span></span>
6. <span data-ttu-id="8404b-145">Haga clic en Lista de selección.</span><span class="sxs-lookup"><span data-stu-id="8404b-145">Click Picking list.</span></span>
7. <span data-ttu-id="8404b-146">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="8404b-146">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="8404b-147">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="8404b-147">Close the page.</span></span>
9. <span data-ttu-id="8404b-148">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="8404b-148">Close the page.</span></span>
10. <span data-ttu-id="8404b-149">Haga clic en tarjeta de ruta.</span><span class="sxs-lookup"><span data-stu-id="8404b-149">Click Route card.</span></span>
11. <span data-ttu-id="8404b-150">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="8404b-150">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="8404b-151">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="8404b-151">Close the page.</span></span>
13. <span data-ttu-id="8404b-152">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="8404b-152">Close the page.</span></span>


