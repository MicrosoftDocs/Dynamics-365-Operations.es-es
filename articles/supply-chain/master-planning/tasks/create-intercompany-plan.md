---
title: Crear un plan de empresas vinculadas
description: Este procedimiento muestra cómo crear un plan de empresas vinculadas.
author: ShylaThompson
manager: AnnBe
ms.date: 08/13/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqIntercompanyPlanningGroupSetup,  ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f7fe8d155b39190f6c0ee1ee310a5edd2400623c
ms.sourcegitcommit: cbcf344b3b552acca56c3e27606eac7f2f124afe
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "1916723"
---
# <a name="create-an-intercompany-plan"></a><span data-ttu-id="ff9cb-103">Crear un plan de empresas vinculadas</span><span class="sxs-lookup"><span data-stu-id="ff9cb-103">Create an intercompany plan</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="ff9cb-104">Este procedimiento muestra cómo crear un plan de empresas vinculadas.</span><span class="sxs-lookup"><span data-stu-id="ff9cb-104">This procedure shows how to create an intercompany plan.</span></span> <span data-ttu-id="ff9cb-105">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="ff9cb-105">The demo data company used to create this procedure is USMF.</span></span>


## <a name="set-up-an-intercompany-planning-group"></a><span data-ttu-id="ff9cb-106">Configurar un grupo de planificación de empresas vinculadas</span><span class="sxs-lookup"><span data-stu-id="ff9cb-106">Set up an intercompany planning group</span></span> 
1. <span data-ttu-id="ff9cb-107">En el **Panel de exploración**, vaya a **Módulos > Planificación maestra > Configuración > Grupos de planificación empresas vinculadas**.</span><span class="sxs-lookup"><span data-stu-id="ff9cb-107">In the **Navigation pane**, go to **Modules > Master planning > Setup > Intercompany planning groups**.</span></span> 
2. <span data-ttu-id="ff9cb-108">Use el filtro rápido para buscar registros.</span><span class="sxs-lookup"><span data-stu-id="ff9cb-108">Use the Quick Filter to find records.</span></span> <span data-ttu-id="ff9cb-109">Por ejemplo, aplique un filtro en el campo Nombre con un valor de “10”.</span><span class="sxs-lookup"><span data-stu-id="ff9cb-109">For example, filter on the Name field with a value of '10'.</span></span>
3. <span data-ttu-id="ff9cb-110">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="ff9cb-110">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="ff9cb-111">Haga clic **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="ff9cb-111">Click **Delete**.</span></span> <span data-ttu-id="ff9cb-112">Este paso es necesario para reducir la ejecución empresas vinculadas de planificación.</span><span class="sxs-lookup"><span data-stu-id="ff9cb-112">This step is necessary in order to shorten the intercompany planning run.</span></span>   <span data-ttu-id="ff9cb-113">La planificación de empresas vinculadas ejecutará una planificación maestra en un grupo de planificación, a partir de la secuencia de programación más baja.</span><span class="sxs-lookup"><span data-stu-id="ff9cb-113">Intercompany planning will run master planning in all the companies in a planning group, starting from the lowest scheduling sequence.</span></span>  
5. <span data-ttu-id="ff9cb-114">Haga clic en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="ff9cb-114">Click **Yes**.</span></span>
6. <span data-ttu-id="ff9cb-115">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="ff9cb-115">Close the page.</span></span>

## <a name="create-an-intercompany-plan"></a><span data-ttu-id="ff9cb-116">Crear un plan de empresas vinculadas</span><span class="sxs-lookup"><span data-stu-id="ff9cb-116">Create an intercompany plan</span></span>
1. <span data-ttu-id="ff9cb-117">En el **Panel de exploración**, vaya a **Módulos > Planificación maestra > Espacios de trabajo > Planificación maestra**.</span><span class="sxs-lookup"><span data-stu-id="ff9cb-117">In the **Navigation pane**, go to **Modules > Master planning > Workspaces > Master planning**.</span></span>
2. <span data-ttu-id="ff9cb-118">Haga clic en **Planificación maestra de empresas vinculadas**.</span><span class="sxs-lookup"><span data-stu-id="ff9cb-118">Click **Intercompany master planning**.</span></span>  
3. <span data-ttu-id="ff9cb-119">En el campo **Grupo de planificación de empresas vinculadas**, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="ff9cb-119">In the **Intercompany planning group** field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="ff9cb-120">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="ff9cb-120">In the list, click the link in the selected row.</span></span> <span data-ttu-id="ff9cb-121">Seleccione el grupo 10 de planificación de empresas vinculadas.</span><span class="sxs-lookup"><span data-stu-id="ff9cb-121">Select intercompany planning group 10.</span></span>  
5. <span data-ttu-id="ff9cb-122">En el **Número de iteraciones de planificación para empresas vinculadas**, especifique "2".</span><span class="sxs-lookup"><span data-stu-id="ff9cb-122">In the **Number of intercompany planning iterations** field, enter '2'.</span></span> <span data-ttu-id="ff9cb-123">El grupo 10 de planificación de empresas vinculadas tiene dos miembros.</span><span class="sxs-lookup"><span data-stu-id="ff9cb-123">Intercompany planning group 10 has two members.</span></span> <span data-ttu-id="ff9cb-124">Para extender los retrasos de la empresa de origen (USMF) a la empresa cliente (DEMF), deberá ejecutar las empresas vinculadas en ambas empresas dos veces.</span><span class="sxs-lookup"><span data-stu-id="ff9cb-124">In order to propagate the delays from the source company (USMF) to the customer company (DEMF), you will need to run intercompany in both companies two times.</span></span> <span data-ttu-id="ff9cb-125">La primera iteración extenderá la demanda e identificará los retrasos en la empresa de origen (USMF).</span><span class="sxs-lookup"><span data-stu-id="ff9cb-125">The first iteration will propagate the demand and identify the delays in the source company (USMF).</span></span> <span data-ttu-id="ff9cb-126">La segunda iteración extenderá los retrasos de USMF a DEMF.</span><span class="sxs-lookup"><span data-stu-id="ff9cb-126">The second iteration will propagate the delays from USMF to DEMF.</span></span>  
6. <span data-ttu-id="ff9cb-127">En el campo **Primera iteración**, seleccione "Regeneración".</span><span class="sxs-lookup"><span data-stu-id="ff9cb-127">In the **First iteration** field, select 'Regeneration'.</span></span>
7. <span data-ttu-id="ff9cb-128">En el campo **Iteraciones subsiguientes**, seleccione "Regeneración".</span><span class="sxs-lookup"><span data-stu-id="ff9cb-128">In the **Subsequent iterations** field, select 'Regeneration'.</span></span>
8. <span data-ttu-id="ff9cb-129">En el campo **Número de subprocesos**, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="ff9cb-129">In the **Number of threads** field, enter a number.</span></span> <span data-ttu-id="ff9cb-130">Esto representa el número de subprocesos paralelos utilizados para la planificación.</span><span class="sxs-lookup"><span data-stu-id="ff9cb-130">This represents the number of parallel threads used for planning.</span></span>  
9. <span data-ttu-id="ff9cb-131">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ff9cb-131">Click **OK**.</span></span>

## <a name="view-the-result-of-the-plan"></a><span data-ttu-id="ff9cb-132">Ver el resultado del plan</span><span class="sxs-lookup"><span data-stu-id="ff9cb-132">View the result of the plan</span></span>
1. <span data-ttu-id="ff9cb-133">En el campo **Plan**, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="ff9cb-133">In the **Plan** field, click the drop-down button to open the lookup.</span></span>
2. <span data-ttu-id="ff9cb-134">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="ff9cb-134">In the list, click the link in the selected row.</span></span> <span data-ttu-id="ff9cb-135">Haga clic en el vínculo para StaticPlan.</span><span class="sxs-lookup"><span data-stu-id="ff9cb-135">Click the link for StaticPlan.</span></span> <span data-ttu-id="ff9cb-136">Debe estar en la empresa USMF.</span><span class="sxs-lookup"><span data-stu-id="ff9cb-136">You need to be in company USMF.</span></span>  
3. <span data-ttu-id="ff9cb-137">Haga clic en **Pedidos planificados**.</span><span class="sxs-lookup"><span data-stu-id="ff9cb-137">Click **Planned orders**.</span></span>

