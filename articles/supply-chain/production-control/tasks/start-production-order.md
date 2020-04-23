---
title: Iniciar un pedido de producción
description: Este procedimiento muestra cómo iniciar un pedido de producción en la planta.
author: johanhoffmann
manager: tfehr
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e444f6c521c47964b9b9b864b62fb486102c2fc7
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2020
ms.locfileid: "3210396"
---
# <a name="start-a-production-order"></a><span data-ttu-id="a3518-103">Iniciar un pedido de producción</span><span class="sxs-lookup"><span data-stu-id="a3518-103">Start a production order</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="a3518-104">Este procedimiento muestra cómo iniciar un pedido de producción en la planta.</span><span class="sxs-lookup"><span data-stu-id="a3518-104">This procedure shows how to start a production order on the shop floor.</span></span> <span data-ttu-id="a3518-105">En este proceso se informa del consumo de tiempo y materiales.</span><span class="sxs-lookup"><span data-stu-id="a3518-105">Time and material consumption are reported in this process.</span></span> <span data-ttu-id="a3518-106">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="a3518-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="a3518-107">Este es el quinto procedimiento de siete que explica el ciclo de vida del pedido de producción.</span><span class="sxs-lookup"><span data-stu-id="a3518-107">This is the fifth procedure out of seven which explains the production order lifecycle.</span></span>


## <a name="start-a-production-order"></a><span data-ttu-id="a3518-108">Iniciar un pedido de producción</span><span class="sxs-lookup"><span data-stu-id="a3518-108">Start a production order</span></span>
1. <span data-ttu-id="a3518-109">Vaya a Control de producción > Pedidos de producción > Todos los pedidos de producción.</span><span class="sxs-lookup"><span data-stu-id="a3518-109">Go to Production control > Production orders > All production orders.</span></span>
    * <span data-ttu-id="a3518-110">Seleccione un pedido de producción con estado Liberado.</span><span class="sxs-lookup"><span data-stu-id="a3518-110">Select a production order that has the Released status.</span></span>  
2. <span data-ttu-id="a3518-111">En el panel de acciones, haga clic en Pedido de producción.</span><span class="sxs-lookup"><span data-stu-id="a3518-111">On the Action Pane, click Production order.</span></span>
3. <span data-ttu-id="a3518-112">Haga clic en Inicio.</span><span class="sxs-lookup"><span data-stu-id="a3518-112">Click Start.</span></span>
    * <span data-ttu-id="a3518-113">En esta página, puede confirmar el inicio del pedido de producción.</span><span class="sxs-lookup"><span data-stu-id="a3518-113">On this page, you can confirm the start of the production order.</span></span>  
4. <span data-ttu-id="a3518-114">Haga clic en la pestaña General.</span><span class="sxs-lookup"><span data-stu-id="a3518-114">Click the General tab.</span></span>
5. <span data-ttu-id="a3518-115">En el campo Desde</span><span class="sxs-lookup"><span data-stu-id="a3518-115">In the From Oper.</span></span> <span data-ttu-id="a3518-116">N. º</span><span class="sxs-lookup"><span data-stu-id="a3518-116">No.</span></span> <span data-ttu-id="a3518-117">oper., especifique "10".</span><span class="sxs-lookup"><span data-stu-id="a3518-117">field, enter '10'.</span></span>
6. <span data-ttu-id="a3518-118">En el campo Consumo de ruta automático, seleccione Siempre.</span><span class="sxs-lookup"><span data-stu-id="a3518-118">In the Automatic route consumption field, select 'Always'.</span></span>
7. <span data-ttu-id="a3518-119">Haga clic en la casilla Registrar ahora la tarjeta de ruta.</span><span class="sxs-lookup"><span data-stu-id="a3518-119">Click the Post route card now checkbox.</span></span>
8. <span data-ttu-id="a3518-120">En el campo Consumo automático de L. MAT, seleccione Siempre.</span><span class="sxs-lookup"><span data-stu-id="a3518-120">In the Automatic BOM consumption field, select 'Always'.</span></span>
9. <span data-ttu-id="a3518-121">Haga clic en la casilla Registrar ahora la lista de selección.</span><span class="sxs-lookup"><span data-stu-id="a3518-121">Click the Post picking list now checkbox.</span></span>
10. <span data-ttu-id="a3518-122">Haga clic en la casilla Imprimir lista de selección.</span><span class="sxs-lookup"><span data-stu-id="a3518-122">Click the Print picking list checkbox.</span></span>
11. <span data-ttu-id="a3518-123">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="a3518-123">Click OK.</span></span>
    * <span data-ttu-id="a3518-124">Esta es la lista de selección impresa que muestra los materiales usados para el pedido de producción.</span><span class="sxs-lookup"><span data-stu-id="a3518-124">This is the printed picking list that shows the materials used for the production order.</span></span>  
12. <span data-ttu-id="a3518-125">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="a3518-125">Close the page.</span></span>

## <a name="validate-the-picking-list"></a><span data-ttu-id="a3518-126">Validación de la lista de selección</span><span class="sxs-lookup"><span data-stu-id="a3518-126">Validate the picking list</span></span>
1. <span data-ttu-id="a3518-127">En el panel de acciones, haga clic en Ver.</span><span class="sxs-lookup"><span data-stu-id="a3518-127">On the Action Pane, click View.</span></span>
2. <span data-ttu-id="a3518-128">Haga clic en Lista de selección.</span><span class="sxs-lookup"><span data-stu-id="a3518-128">Click Picking list.</span></span>
3. <span data-ttu-id="a3518-129">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="a3518-129">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="a3518-130">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="a3518-130">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="a3518-131">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="a3518-131">Click Edit.</span></span>
6. <span data-ttu-id="a3518-132">En el campo Consumo, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="a3518-132">In the Consumption field, enter a number.</span></span>
7. <span data-ttu-id="a3518-133">Haga clic en Registrar.</span><span class="sxs-lookup"><span data-stu-id="a3518-133">Click Post.</span></span>
8. <span data-ttu-id="a3518-134">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="a3518-134">Click OK.</span></span>
    * <span data-ttu-id="a3518-135">En el diario de lista de selección se registran los materiales consumidos por el pedido de producción.</span><span class="sxs-lookup"><span data-stu-id="a3518-135">In the picking list journal, the materials consumed by the production order are posted.</span></span> <span data-ttu-id="a3518-136">Antes de registrar el diario, puede realizar ajustes si existe diferencia entre la cantidad estimada y la cantidad consumida real.</span><span class="sxs-lookup"><span data-stu-id="a3518-136">Before posting the journal, you can make adjustments if there is a difference between the estimated quantity and the actual consumed quantity.</span></span>  
9. <span data-ttu-id="a3518-137">Haga clic en la pestaña del panel de cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="a3518-137">Click the GridPanel tab.</span></span>
10. <span data-ttu-id="a3518-138">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="a3518-138">Close the page.</span></span>

## <a name="verify-the-route-card-journal"></a><span data-ttu-id="a3518-139">Verificación del diario de tarjeta de ruta</span><span class="sxs-lookup"><span data-stu-id="a3518-139">Verify the route card journal</span></span>
1. <span data-ttu-id="a3518-140">En el panel de acciones, haga clic en Ver.</span><span class="sxs-lookup"><span data-stu-id="a3518-140">On the Action Pane, click View.</span></span>
2. <span data-ttu-id="a3518-141">Haga clic en tarjeta de ruta.</span><span class="sxs-lookup"><span data-stu-id="a3518-141">Click Route card.</span></span>
3. <span data-ttu-id="a3518-142">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="a3518-142">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="a3518-143">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="a3518-143">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="a3518-144">Haga clic en Editar.</span><span class="sxs-lookup"><span data-stu-id="a3518-144">Click Edit.</span></span>
6. <span data-ttu-id="a3518-145">En el campo Horas, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="a3518-145">In the Hours field, enter a number.</span></span>
7. <span data-ttu-id="a3518-146">Haga clic en Registrar.</span><span class="sxs-lookup"><span data-stu-id="a3518-146">Click Post.</span></span>
8. <span data-ttu-id="a3518-147">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="a3518-147">Click OK.</span></span>
    * <span data-ttu-id="a3518-148">En el diario de tarjeta de ruta se registra el tiempo empleado en las operaciones individuales.</span><span class="sxs-lookup"><span data-stu-id="a3518-148">In the Route card journal, the time spent on the individual operations is recorded.</span></span> <span data-ttu-id="a3518-149">También se puede informar de la cantidad de errores y aciertos.</span><span class="sxs-lookup"><span data-stu-id="a3518-149">Good and error quantity can also be reported.</span></span>  
