---
title: Programar un pedido de producción
description: Este procedimiento muestra cómo programar un pedido de producción.
author: johanhoffmann
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdTableListPage, ProdSchedule, ProdRouteJob, WrkCtrCapResSum, ProdRouteJobSched, ProductionOrderScheduleDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8b3fe8f6890c7d8ac8835503091642faa773f7f6
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4436813"
---
# <a name="schedule-a-production-order"></a><span data-ttu-id="f3d3e-103">Programar un pedido de producción</span><span class="sxs-lookup"><span data-stu-id="f3d3e-103">Schedule a production order</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="f3d3e-104">Este procedimiento muestra cómo programar un pedido de producción.</span><span class="sxs-lookup"><span data-stu-id="f3d3e-104">This procedure shows how to schedule a production order.</span></span> <span data-ttu-id="f3d3e-105">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="f3d3e-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="f3d3e-106">Este es el tercer procedimiento de siete que explica el ciclo de vida del pedido de producción.</span><span class="sxs-lookup"><span data-stu-id="f3d3e-106">This is the third procedure out of seven which explains the production order lifecycle.</span></span>


## <a name="schedule-a-production-order"></a><span data-ttu-id="f3d3e-107">Programar un pedido de producción</span><span class="sxs-lookup"><span data-stu-id="f3d3e-107">Schedule a production order</span></span>
1. <span data-ttu-id="f3d3e-108">Vaya a Control de producción > Pedidos de producción > Todos los pedidos de producción.</span><span class="sxs-lookup"><span data-stu-id="f3d3e-108">Go to Production control > Production orders > All production orders.</span></span>
    * <span data-ttu-id="f3d3e-109">Seleccione un pedido de producción con el Estimado.</span><span class="sxs-lookup"><span data-stu-id="f3d3e-109">Select a production order that has the Estimated status.</span></span>  
2. <span data-ttu-id="f3d3e-110">En el panel de acciones, haga clic en Programar.</span><span class="sxs-lookup"><span data-stu-id="f3d3e-110">On the Action Pane, click Schedule.</span></span>
3. <span data-ttu-id="f3d3e-111">Haga clic en Programar trabajos.</span><span class="sxs-lookup"><span data-stu-id="f3d3e-111">Click Schedule jobs.</span></span>
    * <span data-ttu-id="f3d3e-112">Los parámetros para programar se configuran en esta página.</span><span class="sxs-lookup"><span data-stu-id="f3d3e-112">The parameters for scheduling are set up on this page.</span></span> <span data-ttu-id="f3d3e-113">Puede configurar los parámetros para usuarios específicos o todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="f3d3e-113">You can set up the parameters for specific users or all users.</span></span>  
4. <span data-ttu-id="f3d3e-114">En el campo Dirección de programación, seleccione “Remitir a partir de hoy”.</span><span class="sxs-lookup"><span data-stu-id="f3d3e-114">In the Scheduling direction field, select 'Forward from today'.</span></span>
5. <span data-ttu-id="f3d3e-115">En el campo Fecha de programación, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="f3d3e-115">In the Scheduling date field, enter a date.</span></span>
6. <span data-ttu-id="f3d3e-116">Active o desactive la casilla Capacidad limitada.</span><span class="sxs-lookup"><span data-stu-id="f3d3e-116">Select or clear the Finite capacity check box.</span></span>
7. <span data-ttu-id="f3d3e-117">Active o desactive la casilla Material limitado.</span><span class="sxs-lookup"><span data-stu-id="f3d3e-117">Select or clear the Finite material check box.</span></span>
8. <span data-ttu-id="f3d3e-118">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="f3d3e-118">Click OK.</span></span>

## <a name="view-the-scheduling-results"></a><span data-ttu-id="f3d3e-119">Ver los resultados de la programación</span><span class="sxs-lookup"><span data-stu-id="f3d3e-119">View the scheduling results</span></span>
1. <span data-ttu-id="f3d3e-120">En el panel de acciones, haga clic en Pedido de producción.</span><span class="sxs-lookup"><span data-stu-id="f3d3e-120">On the Action Pane, click Production order.</span></span>
2. <span data-ttu-id="f3d3e-121">Haga clic en Todos los trabajos.</span><span class="sxs-lookup"><span data-stu-id="f3d3e-121">Click All jobs.</span></span>
    * <span data-ttu-id="f3d3e-122">Esta página muestra los trabajos programados que acaba de generar.</span><span class="sxs-lookup"><span data-stu-id="f3d3e-122">This page displays the scheduled jobs that you have just generated.</span></span>  
3. <span data-ttu-id="f3d3e-123">Expanda o contraiga la sección Programación.</span><span class="sxs-lookup"><span data-stu-id="f3d3e-123">Expand or collapse the Scheduling section.</span></span>
    * <span data-ttu-id="f3d3e-124">En la ficha desplegable Programación, puede ver la fecha y la hora programadas.</span><span class="sxs-lookup"><span data-stu-id="f3d3e-124">On the Scheduling FastTab, you can view the scheduled date and time.</span></span>  
4. <span data-ttu-id="f3d3e-125">Haga clic en Consultas.</span><span class="sxs-lookup"><span data-stu-id="f3d3e-125">Click Inquiries.</span></span>
5. <span data-ttu-id="f3d3e-126">Haga clic en Carga de capacidad.</span><span class="sxs-lookup"><span data-stu-id="f3d3e-126">Click Capacity load.</span></span>
    * <span data-ttu-id="f3d3e-127">La página Carga de capacidad muestra la capacidad reservada mediante la programación de trabajos, el número total de horas actualmente reservadas en el recurso y el número de horas que siguen disponibles para la programación de trabajos en el recurso.</span><span class="sxs-lookup"><span data-stu-id="f3d3e-127">The Capacity load page displays the capacity that is reserved through job scheduling, the total number of hours that are currently reserved on the resource, and the number of hours that remain available for job scheduling on the resource.</span></span>  
6. <span data-ttu-id="f3d3e-128">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="f3d3e-128">Close the page.</span></span>
7. <span data-ttu-id="f3d3e-129">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="f3d3e-129">Close the page.</span></span>

