---
title: Crear una programación para un sitio
description: Este procedimiento muestra cómo programar los pedidos de producción que no se han iniciado aún para un sitio.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdTableListPage, ProdSchedule, ProdRouteJob
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 54bb2532534d5567239dad4fab7fd74fa50d2826
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1549403"
---
# <a name="create-a-schedule-for-a-site"></a><span data-ttu-id="54b64-103">Crear una programación para un sitio</span><span class="sxs-lookup"><span data-stu-id="54b64-103">Create a schedule for a site</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="54b64-104">Este procedimiento muestra cómo programar los pedidos de producción que no se han iniciado aún para un sitio.</span><span class="sxs-lookup"><span data-stu-id="54b64-104">This procedure shows how to schedule production orders that are not yet started for a site.</span></span>  <span data-ttu-id="54b64-105">Se usa la empresa de datos de demostración USMF para completar este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="54b64-105">The demo data company USMF is used to complete this procedure.</span></span>


## <a name="identify-production-orders-that-are-not-started"></a><span data-ttu-id="54b64-106">Identificar pedidos de producción que no se han iniciado</span><span class="sxs-lookup"><span data-stu-id="54b64-106">Identify production orders that are not started</span></span>
1. <span data-ttu-id="54b64-107">Vaya a Control de producción > Pedidos de producción > Todos los pedidos de producción.</span><span class="sxs-lookup"><span data-stu-id="54b64-107">Go to Production control > Production orders > All production orders.</span></span>
2. <span data-ttu-id="54b64-108">Use el filtro rápido para buscar registros.</span><span class="sxs-lookup"><span data-stu-id="54b64-108">Use the Quick Filter to find records.</span></span> <span data-ttu-id="54b64-109">Por ejemplo, aplique un filtro en el campo Sitio con un valor de "1".</span><span class="sxs-lookup"><span data-stu-id="54b64-109">For example, filter on the Site field with a value of '1'.</span></span>
    * <span data-ttu-id="54b64-110">1 representa un sitio en USMF.</span><span class="sxs-lookup"><span data-stu-id="54b64-110">1 represents a site in USMF.</span></span> <span data-ttu-id="54b64-111">Si no utiliza USMF, seleccione un sitio de su propia empresa.</span><span class="sxs-lookup"><span data-stu-id="54b64-111">If you are not using USMF, select a site from your own company.</span></span>  
3. <span data-ttu-id="54b64-112">Abra el filtro de columna Estado.</span><span class="sxs-lookup"><span data-stu-id="54b64-112">Open the Status column filter.</span></span>
4. <span data-ttu-id="54b64-113">Aplique un filtro al campo "Estado", con el valor de "Programado", mediante el operador de filtro "es exactamente".</span><span class="sxs-lookup"><span data-stu-id="54b64-113">Apply a filter on the "Status" field, with a value of "Scheduled", using the "is exactly" filter operator.</span></span>

## <a name="create-a-schedule"></a><span data-ttu-id="54b64-114">Crear una programación</span><span class="sxs-lookup"><span data-stu-id="54b64-114">Create a schedule</span></span>
1. <span data-ttu-id="54b64-115">En la lista, active o desactive todas las filas.</span><span class="sxs-lookup"><span data-stu-id="54b64-115">In the list, mark or unmark all rows.</span></span>
2. <span data-ttu-id="54b64-116">En el panel de acciones, haga clic en Programar.</span><span class="sxs-lookup"><span data-stu-id="54b64-116">On the Action Pane, click Schedule.</span></span>
3. <span data-ttu-id="54b64-117">Haga clic en Programar trabajos.</span><span class="sxs-lookup"><span data-stu-id="54b64-117">Click Schedule jobs.</span></span>
4. <span data-ttu-id="54b64-118">En el campo Dirección de programación, seleccione “Programar hacia atrás a partir de la fecha de entrega”.</span><span class="sxs-lookup"><span data-stu-id="54b64-118">In the Scheduling direction field, select 'Backward from delivery date'.</span></span>
5. <span data-ttu-id="54b64-119">Seleccione No en el campo Capacidad limitada.</span><span class="sxs-lookup"><span data-stu-id="54b64-119">Select No in the Finite capacity field.</span></span>
6. <span data-ttu-id="54b64-120">Seleccione No en el campo Material limitado.</span><span class="sxs-lookup"><span data-stu-id="54b64-120">Select No in the Finite material field.</span></span>
7. <span data-ttu-id="54b64-121">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="54b64-121">Click OK.</span></span>
    * <span data-ttu-id="54b64-122">Esto puede tardar unos minutos.</span><span class="sxs-lookup"><span data-stu-id="54b64-122">This may take a while.</span></span>  

## <a name="view-the-result-of-scheduled-production-orders"></a><span data-ttu-id="54b64-123">Ver el resultado de los pedidos de producción programados</span><span class="sxs-lookup"><span data-stu-id="54b64-123">View the result of scheduled production orders</span></span>
1. <span data-ttu-id="54b64-124">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="54b64-124">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="54b64-125">Puede marcar cualquier fila.</span><span class="sxs-lookup"><span data-stu-id="54b64-125">You can mark any row.</span></span>  
2. <span data-ttu-id="54b64-126">En el panel de acciones, haga clic en Pedido de producción.</span><span class="sxs-lookup"><span data-stu-id="54b64-126">On the Action Pane, click Production order.</span></span>
3. <span data-ttu-id="54b64-127">Haga clic en Todos los trabajos.</span><span class="sxs-lookup"><span data-stu-id="54b64-127">Click All jobs.</span></span>
    * <span data-ttu-id="54b64-128">En esta página, puede ver la lista de trabajos.</span><span class="sxs-lookup"><span data-stu-id="54b64-128">On this page, you can see the list of jobs.</span></span> <span data-ttu-id="54b64-129">En la ficha Programación, puede ver la Fecha inicial y la Fecha final de un trabajo.</span><span class="sxs-lookup"><span data-stu-id="54b64-129">On the Scheduling tab, you can see the Start date and End date for a job.</span></span>  
4. <span data-ttu-id="54b64-130">Haga clic en Materiales.</span><span class="sxs-lookup"><span data-stu-id="54b64-130">Click Materials.</span></span>
    * <span data-ttu-id="54b64-131">En esta página, puede ver el consumo de materiales estimado para las operaciones en el pedido de producción y el inventario disponible actual.</span><span class="sxs-lookup"><span data-stu-id="54b64-131">On this page, you can see the estimated material consumption for the operations on the production order and the current available inventory.</span></span>  

