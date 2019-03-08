---
title: Crear un plan de empresas vinculadas
description: Este procedimiento muestra cómo crear un plan de empresas vinculadas.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqIntercompanyPlanningGroupSetup,  ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d378a89bbb4de6d67db0019dc72a27945d50c4e9
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "333746"
---
# <a name="create-an-intercompany-plan"></a><span data-ttu-id="ddf75-103">Crear un plan de empresas vinculadas</span><span class="sxs-lookup"><span data-stu-id="ddf75-103">Create an intercompany plan</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="ddf75-104">Este procedimiento muestra cómo crear un plan de empresas vinculadas.</span><span class="sxs-lookup"><span data-stu-id="ddf75-104">This procedure shows how to create an intercompany plan.</span></span> <span data-ttu-id="ddf75-105">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="ddf75-105">The demo data company used to create this procedure is USMF.</span></span>


## <a name="set-up-an-intercompany-planning-group"></a><span data-ttu-id="ddf75-106">Configurar un grupo de planificación de empresas vinculadas</span><span class="sxs-lookup"><span data-stu-id="ddf75-106">Set up an intercompany planning group</span></span> 
1. <span data-ttu-id="ddf75-107">Vaya a los grupos de planificación de empresas vinculadas.</span><span class="sxs-lookup"><span data-stu-id="ddf75-107">Go to Intercompany planning groups.</span></span>
    * <span data-ttu-id="ddf75-108">Planificación maestra > Configuración > Grupos de planificación de empresas vinculadas</span><span class="sxs-lookup"><span data-stu-id="ddf75-108">Master planning > Setup > Intercompany planning groups</span></span>  
2. <span data-ttu-id="ddf75-109">Use el filtro rápido para buscar registros.</span><span class="sxs-lookup"><span data-stu-id="ddf75-109">Use the Quick Filter to find records.</span></span> <span data-ttu-id="ddf75-110">Por ejemplo, aplique un filtro en el campo Nombre con un valor de “10”.</span><span class="sxs-lookup"><span data-stu-id="ddf75-110">For example, filter on the Name field with a value of '10'.</span></span>
3. <span data-ttu-id="ddf75-111">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="ddf75-111">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="ddf75-112">Haga clic Eliminar.</span><span class="sxs-lookup"><span data-stu-id="ddf75-112">Click Delete.</span></span>
    * <span data-ttu-id="ddf75-113">Este paso es necesario para reducir la ejecución empresas vinculadas de planificación.</span><span class="sxs-lookup"><span data-stu-id="ddf75-113">This step is necessary in order to shorten the intercompany planning run.</span></span>   <span data-ttu-id="ddf75-114">La planificación de empresas vinculadas ejecutará una planificación maestra en un grupo de planificación, a partir de la secuencia de programación más baja.</span><span class="sxs-lookup"><span data-stu-id="ddf75-114">Intercompany planning will run master planning in all the companies in a planning group, starting from the lowest scheduling sequence.</span></span>  
5. <span data-ttu-id="ddf75-115">Haga clic en Sí.</span><span class="sxs-lookup"><span data-stu-id="ddf75-115">Click Yes.</span></span>
6. <span data-ttu-id="ddf75-116">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="ddf75-116">Close the page.</span></span>

## <a name="create-an-intercompany-plan"></a><span data-ttu-id="ddf75-117">Crear un plan de empresas vinculadas</span><span class="sxs-lookup"><span data-stu-id="ddf75-117">Create an intercompany plan</span></span>
1. <span data-ttu-id="ddf75-118">Haga clic en Planificación maestra de empresas vinculadas.</span><span class="sxs-lookup"><span data-stu-id="ddf75-118">Click Intercompany master planning.</span></span>
    * <span data-ttu-id="ddf75-119">Esto se encuentra en el espacio de trabajo de la planificación maestra.</span><span class="sxs-lookup"><span data-stu-id="ddf75-119">This is on the Master planning workspace.</span></span>  
2. <span data-ttu-id="ddf75-120">En el campo de grupo de planificación de empresas vinculadas, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="ddf75-120">In the Intercompany planning group field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="ddf75-121">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="ddf75-121">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="ddf75-122">Seleccione el grupo 10 de planificación de empresas vinculadas.</span><span class="sxs-lookup"><span data-stu-id="ddf75-122">Select intercompany planning group 10.</span></span>  
4. <span data-ttu-id="ddf75-123">En el Número de iteraciones de planificación para empresas vinculadas, especifique "2".</span><span class="sxs-lookup"><span data-stu-id="ddf75-123">In the Number of intercompany planning iterations field, enter '2'.</span></span>
    * <span data-ttu-id="ddf75-124">El grupo 10 de planificación de empresas vinculadas tiene dos miembros.</span><span class="sxs-lookup"><span data-stu-id="ddf75-124">Intercompany planning group 10 has two members.</span></span> <span data-ttu-id="ddf75-125">Para extender los retrasos de la empresa de origen (USMF) a la empresa cliente (DEMF), deberá ejecutar las empresas vinculadas en ambas empresas dos veces.</span><span class="sxs-lookup"><span data-stu-id="ddf75-125">In order to propagate the delays from the source company (USMF) to the customer company (DEMF), you will need to run intercompany in both companies two times.</span></span> <span data-ttu-id="ddf75-126">La primera iteración extenderá la demanda e identificará los retrasos en la empresa de origen (USMF).</span><span class="sxs-lookup"><span data-stu-id="ddf75-126">The first iteration will propagate the demand and identify the delays in the source company (USMF).</span></span> <span data-ttu-id="ddf75-127">La segunda iteración extenderá los retrasos de USMF a DEMF.</span><span class="sxs-lookup"><span data-stu-id="ddf75-127">The second iteration will propagate the delays from USMF to DEMF.</span></span>  
5. <span data-ttu-id="ddf75-128">En el campo Primera iteración, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="ddf75-128">In the First iteration field, select an option.</span></span>
6. <span data-ttu-id="ddf75-129">En el campo Primera iteración, seleccione "Regeneración".</span><span class="sxs-lookup"><span data-stu-id="ddf75-129">In the First iteration field, select 'Regeneration'.</span></span>
7. <span data-ttu-id="ddf75-130">En el campo Iteraciones subsiguientes, seleccione "Regeneración".</span><span class="sxs-lookup"><span data-stu-id="ddf75-130">In the Subsequent iterations field, select 'Regeneration'.</span></span>
8. <span data-ttu-id="ddf75-131">En el campo Número de subprocesos, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="ddf75-131">In the Number of threads field, enter a number.</span></span>
    * <span data-ttu-id="ddf75-132">Esto representa el número de subprocesos paralelos utilizados para la planificación.</span><span class="sxs-lookup"><span data-stu-id="ddf75-132">This represents the number of parallel threads used for planning.</span></span>  
9. <span data-ttu-id="ddf75-133">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="ddf75-133">Click OK.</span></span>

## <a name="view-the-result-of-the-plan"></a><span data-ttu-id="ddf75-134">Ver el resultado del plan</span><span class="sxs-lookup"><span data-stu-id="ddf75-134">View the result of the plan</span></span>
1. <span data-ttu-id="ddf75-135">En el campo Plan, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="ddf75-135">In the Plan field, click the drop-down button to open the lookup.</span></span>
2. <span data-ttu-id="ddf75-136">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="ddf75-136">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="ddf75-137">Haga clic en el vínculo para StaticPlan.</span><span class="sxs-lookup"><span data-stu-id="ddf75-137">Click the link for StaticPlan.</span></span> <span data-ttu-id="ddf75-138">Debe estar en la empresa USMF.</span><span class="sxs-lookup"><span data-stu-id="ddf75-138">You need to be in company USMF.</span></span>  
3. <span data-ttu-id="ddf75-139">Haga clic en Pedidos planificados.</span><span class="sxs-lookup"><span data-stu-id="ddf75-139">Click Planned orders.</span></span>

