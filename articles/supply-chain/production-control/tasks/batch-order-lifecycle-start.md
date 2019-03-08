---
title: Ciclo de vida de pedidos de lote desde la creación hasta el inicio
description: Este procedimiento le lleva por la primera parte del ciclo de vida de un pedido de lote.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdTableListPage, ProdTableCreate, ProdBOM, PmfProdCoBy, ProdParmCostEstimation, ProdCalcTrans, ProdParmRelease, ProdSchedule, ProdRouteJob, ProdParmStartUp, ProdJournalTransBOM, ProdJournalTransRoute
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6484c1954ff4cc600938adb07b5384f1edce8bf7
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "343130"
---
# <a name="batch-order-lifecycle-from-create-to-start"></a><span data-ttu-id="cf066-103">Ciclo de vida de pedidos de lote desde la creación hasta el inicio</span><span class="sxs-lookup"><span data-stu-id="cf066-103">Batch order lifecycle from create to start</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="cf066-104">Este procedimiento le lleva por la primera parte del ciclo de vida de un pedido de lote.</span><span class="sxs-lookup"><span data-stu-id="cf066-104">This procedure takes you through the first part of the life cycle of a batch order.</span></span>

<span data-ttu-id="cf066-105">Desde la creación, la estimación de costes y la programación de trabajos de sobreproducción hasta el inicio real de un pedido de lote.</span><span class="sxs-lookup"><span data-stu-id="cf066-105">From creation, cost estimation, and over production job scheduling to the actual start of a batch order.</span></span>



<span data-ttu-id="cf066-106">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="cf066-106">The demo data company used to create this procedure is USMF.</span></span> 



<span data-ttu-id="cf066-107">Los requisitos previos para ejecutar el procedimiento con otro conjunto de datos son un producto liberado con una versión de ruta y fórmula activa.</span><span class="sxs-lookup"><span data-stu-id="cf066-107">The prerequisites for running the procedure with another dataset are a released product with an active formula and route version.</span></span>


## <a name="create-a-batch-order"></a><span data-ttu-id="cf066-108">Crear un pedido de lote</span><span class="sxs-lookup"><span data-stu-id="cf066-108">Create a batch order</span></span>
1. <span data-ttu-id="cf066-109">Vaya a Todos los pedidos de producción.</span><span class="sxs-lookup"><span data-stu-id="cf066-109">Go to All production orders.</span></span>
2. <span data-ttu-id="cf066-110">Haga clic en Nuevo pedido de lote.</span><span class="sxs-lookup"><span data-stu-id="cf066-110">Click New batch order.</span></span>
3. <span data-ttu-id="cf066-111">En el campo Número de artículo, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="cf066-111">In the Item number field, enter or select a value.</span></span>
4. <span data-ttu-id="cf066-112">Haga clic en Crear.</span><span class="sxs-lookup"><span data-stu-id="cf066-112">Click Create.</span></span>
5. <span data-ttu-id="cf066-113">Use un filtro rápido para filtrar el campo Producción con un valor "b".</span><span class="sxs-lookup"><span data-stu-id="cf066-113">Use the Quick Filter to filter on the Production field with a value of 'b'.</span></span>

## <a name="view-production-formula-and-expected-co-products"></a><span data-ttu-id="cf066-114">Ver fórmula de la producción y coproductos previstos</span><span class="sxs-lookup"><span data-stu-id="cf066-114">View production formula and expected co-products</span></span>
1. <span data-ttu-id="cf066-115">En el panel de acciones, haga clic en Pedido de producción.</span><span class="sxs-lookup"><span data-stu-id="cf066-115">On the Action Pane, click Production order.</span></span>
2. <span data-ttu-id="cf066-116">Haga clic en Fórmula.</span><span class="sxs-lookup"><span data-stu-id="cf066-116">Click Formula.</span></span>
3. <span data-ttu-id="cf066-117">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="cf066-117">Close the page.</span></span>
4. <span data-ttu-id="cf066-118">Haga clic en Productos conjuntos.</span><span class="sxs-lookup"><span data-stu-id="cf066-118">Click Co-products.</span></span>
5. <span data-ttu-id="cf066-119">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="cf066-119">Close the page.</span></span>

## <a name="estimate-the-batch-order"></a><span data-ttu-id="cf066-120">Estimar el pedido de lote</span><span class="sxs-lookup"><span data-stu-id="cf066-120">Estimate the batch order</span></span>
1. <span data-ttu-id="cf066-121">Haga clic en Estimación.</span><span class="sxs-lookup"><span data-stu-id="cf066-121">Click Estimate.</span></span>
2. <span data-ttu-id="cf066-122">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="cf066-122">Click OK.</span></span>
3. <span data-ttu-id="cf066-123">En el panel de acciones, haga clic en Gestionar costes.</span><span class="sxs-lookup"><span data-stu-id="cf066-123">On the Action Pane, click Manage costs.</span></span>
4. <span data-ttu-id="cf066-124">Haga clic en Ver detalles de cálculo.</span><span class="sxs-lookup"><span data-stu-id="cf066-124">Click View calculation details.</span></span>
5. <span data-ttu-id="cf066-125">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="cf066-125">Close the page.</span></span>

## <a name="release-the-batch-order"></a><span data-ttu-id="cf066-126">Liberar el pedido de lote</span><span class="sxs-lookup"><span data-stu-id="cf066-126">Release the batch order</span></span>
1. <span data-ttu-id="cf066-127">En el panel de acciones, haga clic en Pedido de producción.</span><span class="sxs-lookup"><span data-stu-id="cf066-127">On the Action Pane, click Production order.</span></span>
2. <span data-ttu-id="cf066-128">Haga clic en Liberar.</span><span class="sxs-lookup"><span data-stu-id="cf066-128">Click Release.</span></span>
3. <span data-ttu-id="cf066-129">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="cf066-129">Click OK.</span></span>

## <a name="schedule-production-jobs"></a><span data-ttu-id="cf066-130">Programar trabajos de producción</span><span class="sxs-lookup"><span data-stu-id="cf066-130">Schedule production jobs</span></span>
1. <span data-ttu-id="cf066-131">En el panel de acciones, haga clic en Programar.</span><span class="sxs-lookup"><span data-stu-id="cf066-131">On the Action Pane, click Schedule.</span></span>
2. <span data-ttu-id="cf066-132">Haga clic en Programar trabajos.</span><span class="sxs-lookup"><span data-stu-id="cf066-132">Click Schedule jobs.</span></span>
3. <span data-ttu-id="cf066-133">Seleccione No en el campo Capacidad limitada.</span><span class="sxs-lookup"><span data-stu-id="cf066-133">Select No in the Finite capacity field.</span></span>
4. <span data-ttu-id="cf066-134">Seleccione No en el campo Material limitado.</span><span class="sxs-lookup"><span data-stu-id="cf066-134">Select No in the Finite material field.</span></span>
5. <span data-ttu-id="cf066-135">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="cf066-135">Click OK.</span></span>
6. <span data-ttu-id="cf066-136">En el panel de acciones, haga clic en Pedido de producción.</span><span class="sxs-lookup"><span data-stu-id="cf066-136">On the Action Pane, click Production order.</span></span>
7. <span data-ttu-id="cf066-137">Haga clic en Todos los trabajos.</span><span class="sxs-lookup"><span data-stu-id="cf066-137">Click All jobs.</span></span>
8. <span data-ttu-id="cf066-138">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="cf066-138">Close the page.</span></span>

## <a name="start-the-batch-order"></a><span data-ttu-id="cf066-139">Iniciar el pedido de lote</span><span class="sxs-lookup"><span data-stu-id="cf066-139">Start the batch order</span></span>
1. <span data-ttu-id="cf066-140">Haga clic en Inicio.</span><span class="sxs-lookup"><span data-stu-id="cf066-140">Click Start.</span></span>
2. <span data-ttu-id="cf066-141">Haga clic en la pestaña General.</span><span class="sxs-lookup"><span data-stu-id="cf066-141">Click the General tab.</span></span>
3. <span data-ttu-id="cf066-142">Seleccione No en el campo Registrar ahora la lista de selección.</span><span class="sxs-lookup"><span data-stu-id="cf066-142">Select No in the Post picking list now field.</span></span>
4. <span data-ttu-id="cf066-143">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="cf066-143">Click OK.</span></span>
5. <span data-ttu-id="cf066-144">En el panel de acciones, haga clic en Ver.</span><span class="sxs-lookup"><span data-stu-id="cf066-144">On the Action Pane, click View.</span></span>
6. <span data-ttu-id="cf066-145">Haga clic en Lista de selección.</span><span class="sxs-lookup"><span data-stu-id="cf066-145">Click Picking list.</span></span>
7. <span data-ttu-id="cf066-146">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="cf066-146">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="cf066-147">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="cf066-147">Close the page.</span></span>
9. <span data-ttu-id="cf066-148">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="cf066-148">Close the page.</span></span>
10. <span data-ttu-id="cf066-149">Haga clic en tarjeta de ruta.</span><span class="sxs-lookup"><span data-stu-id="cf066-149">Click Route card.</span></span>
11. <span data-ttu-id="cf066-150">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="cf066-150">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="cf066-151">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="cf066-151">Close the page.</span></span>
13. <span data-ttu-id="cf066-152">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="cf066-152">Close the page.</span></span>

