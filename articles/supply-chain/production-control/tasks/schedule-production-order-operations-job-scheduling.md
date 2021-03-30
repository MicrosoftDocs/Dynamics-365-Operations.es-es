---
title: Programar un pedido de producción con programación de operaciones y trabajo
description: En tema se centra en la programación de un pedido de producción con programación de operaciones y programación de trabajos.
author: ChristianRytt
manager: tfehr
ms.date: 08/19/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdTableListPage, ProdTableCreate, InventItemIdLookupPurchase, ProdSchedule, ProdTable, ProdRouteJob
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 32ace204f1ec79cc8f9ce10ebfdc3606879e40d4
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5215850"
---
# <a name="schedule-a-production-order-with-operations-and-job-scheduling"></a><span data-ttu-id="8dec7-103">Programar un pedido de producción con programación de operaciones y trabajo</span><span class="sxs-lookup"><span data-stu-id="8dec7-103">Schedule a production order with operations and job scheduling</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="8dec7-104">En tema se centra en la programación de un pedido de producción con programación de operaciones y programación de trabajos.</span><span class="sxs-lookup"><span data-stu-id="8dec7-104">This topic focuses on scheduling a production order with operations scheduling and job scheduling.</span></span> <span data-ttu-id="8dec7-105">No se crea ningún trabajo con la programación de tareas mientras que los trabajos se crean con programación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="8dec7-105">No jobs are created with operations scheduling whereas jobs are created with job scheduling.</span></span> <span data-ttu-id="8dec7-106">La empresa de datos de prueba utilizada para crear esta tarea es USMF.</span><span class="sxs-lookup"><span data-stu-id="8dec7-106">The demo data company used to create this task is USMF.</span></span> <span data-ttu-id="8dec7-107">Este procedimiento está pensado para el director de producción, el planificador de producción o el supervisor de planta que trabaja en un entorno de fabricación discreto.</span><span class="sxs-lookup"><span data-stu-id="8dec7-107">This procedure is intended for the production manager, production planner, or shop floor supervisor working in a discrete manufacturing environment.</span></span>


## <a name="create-a-production-order"></a><span data-ttu-id="8dec7-108">Crear un pedido de producción</span><span class="sxs-lookup"><span data-stu-id="8dec7-108">Create a production order</span></span>
1. <span data-ttu-id="8dec7-109">En el panel de navegación, vaya a **Módulos > Control de producción > Pedidos de producción > Todos los pedidos de producción**.</span><span class="sxs-lookup"><span data-stu-id="8dec7-109">In the navigation pane, go to **Modules > Production control > Production orders > All production orders**.</span></span>
2. <span data-ttu-id="8dec7-110">Seleccione **Nuevo pedido de producción**.</span><span class="sxs-lookup"><span data-stu-id="8dec7-110">Select **New production order**.</span></span>
3. <span data-ttu-id="8dec7-111">En el campo **Número de artículo**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="8dec7-111">In the **Item number** field, enter or select a value.</span></span> <span data-ttu-id="8dec7-112">Seleccione el número de artículo **D0001**.</span><span class="sxs-lookup"><span data-stu-id="8dec7-112">Select Item number **D0001**.</span></span>  
4. <span data-ttu-id="8dec7-113">Seleccione **Crear**.</span><span class="sxs-lookup"><span data-stu-id="8dec7-113">Select **Create**.</span></span>

## <a name="schedule-operations-for-the-production-order"></a><span data-ttu-id="8dec7-114">Programe operaciones para el pedido de producción</span><span class="sxs-lookup"><span data-stu-id="8dec7-114">Schedule operations for the production order</span></span>
1. <span data-ttu-id="8dec7-115">Marque la fila recién creada.</span><span class="sxs-lookup"><span data-stu-id="8dec7-115">Mark the newly created row.</span></span>      
2. <span data-ttu-id="8dec7-116">En el panel de acciones, seleccione **Programación**.</span><span class="sxs-lookup"><span data-stu-id="8dec7-116">On the Action Pane, select **Schedule**.</span></span>
3. <span data-ttu-id="8dec7-117">Seleccione **Programar operaciones**.</span><span class="sxs-lookup"><span data-stu-id="8dec7-117">Select **Schedule operations**.</span></span>
4. <span data-ttu-id="8dec7-118">En el campo **Dirección de programación**, seleccione **A partir de la fecha de programación**.</span><span class="sxs-lookup"><span data-stu-id="8dec7-118">In the **Scheduling direction** field, select **Forward from scheduling date**.</span></span>
5. <span data-ttu-id="8dec7-119">En el campo **Fecha de programación**, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="8dec7-119">In the **Scheduling date** field, enter a date.</span></span> <span data-ttu-id="8dec7-120">Seleccione una fecha futura, por ejemplo, hoy más una semana.</span><span class="sxs-lookup"><span data-stu-id="8dec7-120">Select a future date, for example, today plus one week.</span></span> <span data-ttu-id="8dec7-121">Con la dirección de programación seleccionada, el pedido de producción se programará hacia delante a partir de esta fecha.</span><span class="sxs-lookup"><span data-stu-id="8dec7-121">With the selected Scheduling direction, the production order will be scheduled forward from this date.</span></span>  
6. <span data-ttu-id="8dec7-122">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8dec7-122">Select **OK**.</span></span>
7. <span data-ttu-id="8dec7-123">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="8dec7-123">In the list, mark the selected row.</span></span> <span data-ttu-id="8dec7-124">Tenga en cuenta que el estado cambia a **Programado**.</span><span class="sxs-lookup"><span data-stu-id="8dec7-124">Note that the status is changed to **Scheduled**.</span></span> 
8. <span data-ttu-id="8dec7-125">Seleccione **Todos los trabajos**.</span><span class="sxs-lookup"><span data-stu-id="8dec7-125">Select **All jobs**.</span></span> <span data-ttu-id="8dec7-126">Tenga en cuenta que ningún trabajo se crea con la programación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="8dec7-126">Note that no jobs are created with operations scheduling.</span></span>  
9. <span data-ttu-id="8dec7-127">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="8dec7-127">Close the page.</span></span>

## <a name="schedule-jobs-for-the-production-order"></a><span data-ttu-id="8dec7-128">Programe tareas para el pedido de producción</span><span class="sxs-lookup"><span data-stu-id="8dec7-128">Schedule jobs for the production order</span></span>
1. <span data-ttu-id="8dec7-129">En el panel de acciones, seleccione **Programación**.</span><span class="sxs-lookup"><span data-stu-id="8dec7-129">On the Action Pane, select **Schedule**.</span></span>
2. <span data-ttu-id="8dec7-130">Seleccione **Programar trabajos**.</span><span class="sxs-lookup"><span data-stu-id="8dec7-130">Select **Schedule jobs**.</span></span>
3. <span data-ttu-id="8dec7-131">En el campo **Dirección de programación**, seleccione **A partir de la fecha de programación**.</span><span class="sxs-lookup"><span data-stu-id="8dec7-131">In the **Scheduling direction** field, select **Forward from scheduling date**.</span></span>
4. <span data-ttu-id="8dec7-132">En el campo **Fecha de programación**, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="8dec7-132">In the **Scheduling date** field, enter a date.</span></span> <span data-ttu-id="8dec7-133">Seleccione una fecha en el futuro, por ejemplo, hoy más una semana.</span><span class="sxs-lookup"><span data-stu-id="8dec7-133">Select a date in the future, for example, today plus one week.</span></span> <span data-ttu-id="8dec7-134">Con la dirección de programación seleccionada, el pedido de producción se programará hacia delante a partir de esta fecha.</span><span class="sxs-lookup"><span data-stu-id="8dec7-134">With the selected Scheduling direction, the production order will be scheduled forward from this date.</span></span>  
5. <span data-ttu-id="8dec7-135">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8dec7-135">Select **OK**.</span></span>
6. <span data-ttu-id="8dec7-136">En el panel de acciones, seleccione **Pedido de producción**.</span><span class="sxs-lookup"><span data-stu-id="8dec7-136">On the Action Pane, select **Production order**.</span></span>
7. <span data-ttu-id="8dec7-137">Seleccione **Todos los trabajos**.</span><span class="sxs-lookup"><span data-stu-id="8dec7-137">Select **All jobs**.</span></span> <span data-ttu-id="8dec7-138">Tenga en cuenta que basándose en la ruta activa, se crean 5 trabajos con la programación de trabajos.</span><span class="sxs-lookup"><span data-stu-id="8dec7-138">Note that based on the active route, 5 jobs are created with job scheduling.</span></span>  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]