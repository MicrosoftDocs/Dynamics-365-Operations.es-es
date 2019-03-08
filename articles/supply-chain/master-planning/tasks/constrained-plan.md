---
title: Generar un plan con restricciones
description: Este procedimiento muestra cómo crear un plan que tenga en cuenta las restricciones de materiales y de capacidad.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, ReqCreatePlanWorkspace, ReqTransPlanCard, ReqPlanSched
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0e2265f7788fd2a4a37f6fb96d7562649dbc5b1c
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "336046"
---
# <a name="generate-a-constrained-plan"></a><span data-ttu-id="b8eea-103">Generar un plan con restricciones</span><span class="sxs-lookup"><span data-stu-id="b8eea-103">Generate a constrained plan</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="b8eea-104">Este procedimiento muestra cómo crear un plan que tenga en cuenta las restricciones de materiales y de capacidad.</span><span class="sxs-lookup"><span data-stu-id="b8eea-104">This procedure shows how to create a plan that takes into account both material and capacity constraints.</span></span> <span data-ttu-id="b8eea-105">El plan garantiza que la fabricación no comience antes de que los materiales estén disponibles y que no se reserven recursos en exceso.</span><span class="sxs-lookup"><span data-stu-id="b8eea-105">The plan ensures that manufacturing doesn't start before materials are available and resources are not overbooked.</span></span> 

<span data-ttu-id="b8eea-106">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="b8eea-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="b8eea-107">Este procedimiento se va a utilizar para el planificador de producción.</span><span class="sxs-lookup"><span data-stu-id="b8eea-107">This procedure is intended for the production planner.</span></span>


## <a name="set-up-a-constrained-plan"></a><span data-ttu-id="b8eea-108">Configurar un plan restringido</span><span class="sxs-lookup"><span data-stu-id="b8eea-108">Set up a constrained plan</span></span>
1. <span data-ttu-id="b8eea-109">Haga clic en Planificación maestra.</span><span class="sxs-lookup"><span data-stu-id="b8eea-109">Click Master planning.</span></span>
2. <span data-ttu-id="b8eea-110">Haga clic en Planes maestros.</span><span class="sxs-lookup"><span data-stu-id="b8eea-110">Click Master plans.</span></span>
3. <span data-ttu-id="b8eea-111">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="b8eea-111">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="b8eea-112">Ejemplo: StaticPlan</span><span class="sxs-lookup"><span data-stu-id="b8eea-112">Example: StaticPlan</span></span>  
4. <span data-ttu-id="b8eea-113">Seleccione Sí en el campo Capacidad limitada.</span><span class="sxs-lookup"><span data-stu-id="b8eea-113">Select Yes in the Finite capacity field.</span></span>
5. <span data-ttu-id="b8eea-114">En el campo Límite de tiempo de capacidad finita, indique "30".</span><span class="sxs-lookup"><span data-stu-id="b8eea-114">In the Finite capacity time fence field, enter '30'.</span></span>
6. <span data-ttu-id="b8eea-115">Expanda la sección Límites de tiempo en días.</span><span class="sxs-lookup"><span data-stu-id="b8eea-115">Expand the Time fences in days section.</span></span>
7. <span data-ttu-id="b8eea-116">Seleccione Sí en el campo Capacidad.</span><span class="sxs-lookup"><span data-stu-id="b8eea-116">Select Yes in the Capacity field.</span></span>
8. <span data-ttu-id="b8eea-117">En el campo Límite de tiempo de programación de capacidad (días), escriba un número.</span><span class="sxs-lookup"><span data-stu-id="b8eea-117">In the Capacity scheduling time fence (days) field, enter a number.</span></span>
    * <span data-ttu-id="b8eea-118">Ejemplo: 60</span><span class="sxs-lookup"><span data-stu-id="b8eea-118">Example: 60</span></span>  
9. <span data-ttu-id="b8eea-119">Seleccione Sí en el campo Retrasos calculados.</span><span class="sxs-lookup"><span data-stu-id="b8eea-119">Select Yes in the Calculated delays field.</span></span>
10. <span data-ttu-id="b8eea-120">En el campo Calcular límite de tiempo de retrasos (días), escriba un número.</span><span class="sxs-lookup"><span data-stu-id="b8eea-120">In the Calculate delays time fence (days) field, enter a number.</span></span>
    * <span data-ttu-id="b8eea-121">Ejemplo: 60</span><span class="sxs-lookup"><span data-stu-id="b8eea-121">Example: 60</span></span>  
11. <span data-ttu-id="b8eea-122">Expanda la sección Retrasos calculados.</span><span class="sxs-lookup"><span data-stu-id="b8eea-122">Expand the Calculated delays section.</span></span>
12. <span data-ttu-id="b8eea-123">Seleccione Sí en el campo Agregar el retraso calculado a la fecha de requisito.</span><span class="sxs-lookup"><span data-stu-id="b8eea-123">Select Yes in the Add the calculated delay to the requirement date field.</span></span>
13. <span data-ttu-id="b8eea-124">Seleccione Sí en el campo Agregar el retraso calculado a la fecha de requisito.</span><span class="sxs-lookup"><span data-stu-id="b8eea-124">Select Yes in the Add the calculated delay to the requirement date field.</span></span>
14. <span data-ttu-id="b8eea-125">Seleccione Sí en el campo Agregar el retraso calculado a la fecha de requisito.</span><span class="sxs-lookup"><span data-stu-id="b8eea-125">Select Yes in the Add the calculated delay to the requirement date field.</span></span>
15. <span data-ttu-id="b8eea-126">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="b8eea-126">Close the page.</span></span>

## <a name="create-a-constrained-plan"></a><span data-ttu-id="b8eea-127">Crear un plan restringido</span><span class="sxs-lookup"><span data-stu-id="b8eea-127">Create a constrained plan</span></span>
1. <span data-ttu-id="b8eea-128">Haga clic en Ejecutar.</span><span class="sxs-lookup"><span data-stu-id="b8eea-128">Click Run.</span></span>
2. <span data-ttu-id="b8eea-129">En el campo Plan maestro, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="b8eea-129">In the Master plan field, enter or select a value.</span></span>
    * <span data-ttu-id="b8eea-130">Seleccione el plan para el que ha configurado las restricciones.</span><span class="sxs-lookup"><span data-stu-id="b8eea-130">Select the plan for which you have set up constraints.</span></span>  
3. <span data-ttu-id="b8eea-131">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="b8eea-131">Click OK.</span></span>
    * <span data-ttu-id="b8eea-132">Esto puede tardar unos minutos.</span><span class="sxs-lookup"><span data-stu-id="b8eea-132">This may take a while.</span></span>  
4. <span data-ttu-id="b8eea-133">Haga clic en Pedidos planificados.</span><span class="sxs-lookup"><span data-stu-id="b8eea-133">Click Planned orders.</span></span>

