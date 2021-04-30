---
title: Crear un plan de empresas vinculadas
description: Este procedimiento muestra cómo crear un plan de empresas vinculadas.
author: ChristianRytt
ms.date: 08/13/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ReqIntercompanyPlanningGroupSetup,  ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f8cf4ed879b6b2202d0b0f1f45052f5e21452967
ms.sourcegitcommit: 9b07d536b4bd8addfbdba42d2429c9fedb664635
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/07/2021
ms.locfileid: "5867359"
---
# <a name="create-an-intercompany-plan"></a><span data-ttu-id="79cc1-103">Crear un plan de empresas vinculadas</span><span class="sxs-lookup"><span data-stu-id="79cc1-103">Create an intercompany plan</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="79cc1-104">Este procedimiento muestra cómo crear un plan de empresas vinculadas.</span><span class="sxs-lookup"><span data-stu-id="79cc1-104">This procedure shows how to create an intercompany plan.</span></span> <span data-ttu-id="79cc1-105">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="79cc1-105">The demo data company used to create this procedure is USMF.</span></span>

## <a name="set-up-an-intercompany-planning-group"></a><span data-ttu-id="79cc1-106">Configurar un grupo de planificación de empresas vinculadas</span><span class="sxs-lookup"><span data-stu-id="79cc1-106">Set up an intercompany planning group</span></span>

1. <span data-ttu-id="79cc1-107">En el **Panel de exploración**, vaya a **Módulos > Planificación maestra > Configuración > Grupos de planificación empresas vinculadas**.</span><span class="sxs-lookup"><span data-stu-id="79cc1-107">In the **Navigation pane**, go to **Modules > Master planning > Setup > Intercompany planning groups**.</span></span>
2. <span data-ttu-id="79cc1-108">Use el filtro rápido para buscar registros.</span><span class="sxs-lookup"><span data-stu-id="79cc1-108">Use the Quick Filter to find records.</span></span> <span data-ttu-id="79cc1-109">Por ejemplo, aplique un filtro en el campo Nombre con un valor de “10”.</span><span class="sxs-lookup"><span data-stu-id="79cc1-109">For example, filter on the Name field with a value of '10'.</span></span>
3. <span data-ttu-id="79cc1-110">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="79cc1-110">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="79cc1-111">Seleccione **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="79cc1-111">Select **Delete**.</span></span> <span data-ttu-id="79cc1-112">Este paso es necesario para reducir la ejecución empresas vinculadas de planificación.</span><span class="sxs-lookup"><span data-stu-id="79cc1-112">This step is necessary in order to shorten the intercompany planning run.</span></span>   <span data-ttu-id="79cc1-113">La planificación de empresas vinculadas ejecutará una planificación maestra en un grupo de planificación, a partir de la secuencia de programación más baja.</span><span class="sxs-lookup"><span data-stu-id="79cc1-113">Intercompany planning will run master planning in all the companies in a planning group, starting from the lowest scheduling sequence.</span></span>  
5. <span data-ttu-id="79cc1-114">Seleccione **Sí**.</span><span class="sxs-lookup"><span data-stu-id="79cc1-114">Select **Yes**.</span></span>
6. <span data-ttu-id="79cc1-115">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="79cc1-115">Close the page.</span></span>

## <a name="create-an-intercompany-master-plan"></a><span data-ttu-id="79cc1-116">Crear un plan maestro de empresas vinculadas</span><span class="sxs-lookup"><span data-stu-id="79cc1-116">Create an intercompany master plan</span></span>

1. <span data-ttu-id="79cc1-117">En el **Panel de exploración**, vaya a **Módulos > Planificación maestra > Espacios de trabajo > Planificación maestra**.</span><span class="sxs-lookup"><span data-stu-id="79cc1-117">In the **Navigation pane**, go to **Modules > Master planning > Workspaces > Master planning**.</span></span>
2. <span data-ttu-id="79cc1-118">Seleccione **Planificación maestra de empresas vinculadas**.</span><span class="sxs-lookup"><span data-stu-id="79cc1-118">Select **Intercompany master planning**.</span></span>  
3. <span data-ttu-id="79cc1-119">En el campo **Grupo de planificación de empresas vinculadas**, seleccione el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="79cc1-119">In the **Intercompany planning group** field, select the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="79cc1-120">En la lista, seleccione el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="79cc1-120">In the list, select the link in the selected row.</span></span> <span data-ttu-id="79cc1-121">Seleccione el grupo 10 de planificación de empresas vinculadas.</span><span class="sxs-lookup"><span data-stu-id="79cc1-121">Select intercompany planning group 10.</span></span>  
5. <span data-ttu-id="79cc1-122">En el **Número de iteraciones de planificación para empresas vinculadas**, especifique "2".</span><span class="sxs-lookup"><span data-stu-id="79cc1-122">In the **Number of intercompany planning iterations** field, enter '2'.</span></span> <span data-ttu-id="79cc1-123">El grupo 10 de planificación de empresas vinculadas tiene dos miembros.</span><span class="sxs-lookup"><span data-stu-id="79cc1-123">Intercompany planning group 10 has two members.</span></span> <span data-ttu-id="79cc1-124">Para extender los retrasos de la empresa de origen (USMF) a la empresa cliente (DEMF), deberá ejecutar las empresas vinculadas en ambas empresas dos veces.</span><span class="sxs-lookup"><span data-stu-id="79cc1-124">In order to propagate the delays from the source company (USMF) to the customer company (DEMF), you will need to run intercompany in both companies two times.</span></span> <span data-ttu-id="79cc1-125">La primera iteración extenderá la demanda e identificará los retrasos en la empresa de origen (USMF).</span><span class="sxs-lookup"><span data-stu-id="79cc1-125">The first iteration will propagate the demand and identify the delays in the source company (USMF).</span></span> <span data-ttu-id="79cc1-126">La segunda iteración extenderá los retrasos de USMF a DEMF.</span><span class="sxs-lookup"><span data-stu-id="79cc1-126">The second iteration will propagate the delays from USMF to DEMF.</span></span>  
6. <span data-ttu-id="79cc1-127">En el campo **Primera iteración**, seleccione "Regeneración".</span><span class="sxs-lookup"><span data-stu-id="79cc1-127">In the **First iteration** field, select 'Regeneration'.</span></span>
7. <span data-ttu-id="79cc1-128">En el campo **Iteraciones subsiguientes**, seleccione "Regeneración".</span><span class="sxs-lookup"><span data-stu-id="79cc1-128">In the **Subsequent iterations** field, select 'Regeneration'.</span></span>
8. <span data-ttu-id="79cc1-129">En el campo **Número de subprocesos**, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="79cc1-129">In the **Number of threads** field, enter a number.</span></span> <span data-ttu-id="79cc1-130">Esto representa el número de subprocesos paralelos utilizados para la planificación.</span><span class="sxs-lookup"><span data-stu-id="79cc1-130">This represents the number of parallel threads used for planning.</span></span>  
9. <span data-ttu-id="79cc1-131">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="79cc1-131">Select **OK**.</span></span>

## <a name="view-the-result-of-the-plan"></a><span data-ttu-id="79cc1-132">Ver el resultado del plan</span><span class="sxs-lookup"><span data-stu-id="79cc1-132">View the result of the plan</span></span>

1. <span data-ttu-id="79cc1-133">En el campo **Plan**, seleccione el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="79cc1-133">In the **Plan** field, select the drop-down button to open the lookup.</span></span>
2. <span data-ttu-id="79cc1-134">En la lista, seleccione el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="79cc1-134">In the list, select the link in the selected row.</span></span> <span data-ttu-id="79cc1-135">Seleccione el vínculo para StaticPlan.</span><span class="sxs-lookup"><span data-stu-id="79cc1-135">Select the link for StaticPlan.</span></span> <span data-ttu-id="79cc1-136">Debe estar en la empresa USMF.</span><span class="sxs-lookup"><span data-stu-id="79cc1-136">You need to be in company USMF.</span></span>  
3. <span data-ttu-id="79cc1-137">Seleccione **Pedidos planificados**.</span><span class="sxs-lookup"><span data-stu-id="79cc1-137">Select **Planned orders**.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]