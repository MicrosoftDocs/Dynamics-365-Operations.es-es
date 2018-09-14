--- 
title: "Crear relación de actividad - Sucesor"
description: "El flujo de actividades en un flujo de producción lean se documenta a través de relaciones de actividad."
author: cvocph
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LeanProductionFlow, PlanActivity, PlanActivityRelationNew, PlanActivityLookup, DefaultDashboard
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: e5e5844939e1eb40e31530c434c096c5b3be7abe
ms.contentlocale: es-es
ms.lasthandoff: 09/14/2018

---
# <a name="create-activity-relation-successor"></a><span data-ttu-id="be956-103">Crear relación de actividad: sucesor</span><span class="sxs-lookup"><span data-stu-id="be956-103">Create activity relation: Successor</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="be956-104">El flujo de actividades en un flujo de producción lean se documenta a través de relaciones de actividad.</span><span class="sxs-lookup"><span data-stu-id="be956-104">The flow of activities in a lean production flow is documented through activity relations.</span></span> <span data-ttu-id="be956-105">Esta grabación muestra cómo crear una relación de actividad.</span><span class="sxs-lookup"><span data-stu-id="be956-105">This recording shows how to create an activity relation.</span></span>

<span data-ttu-id="be956-106">Requisitos previos:</span><span class="sxs-lookup"><span data-stu-id="be956-106">Prerequisites:</span></span>

- <span data-ttu-id="be956-107">Un flujo de producción y una versión en modo de borrador.</span><span class="sxs-lookup"><span data-stu-id="be956-107">A production flow and version in draft mode.</span></span> 

- <span data-ttu-id="be956-108">Se crean dos actividades que van una detrás de otra en el flujo de producción pero no se relacionan.</span><span class="sxs-lookup"><span data-stu-id="be956-108">Two activities that follow each other in the production flow are created but not related.</span></span>


## <a name="find-the-production-flow-version"></a><span data-ttu-id="be956-109">Buscar la versión del flujo de producción</span><span class="sxs-lookup"><span data-stu-id="be956-109">Find the production flow version</span></span> 
1. <span data-ttu-id="be956-110">Vaya a Control de producción > Configuración > Flujo de producción lean > Flujos de producción.</span><span class="sxs-lookup"><span data-stu-id="be956-110">Go to Production control > Setup > Lean production flow > Production flows.</span></span>
2. <span data-ttu-id="be956-111">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="be956-111">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="be956-112">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="be956-112">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="be956-113">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="be956-113">In the list, mark the selected row.</span></span>
5. <span data-ttu-id="be956-114">En la lista, seleccione una versión de borrador.</span><span class="sxs-lookup"><span data-stu-id="be956-114">In the list, select a draft version.</span></span>
    * <span data-ttu-id="be956-115">Las relaciones de actividad se pueden agregar tanto al borrador como a las versiones activas de un flujo de producción.</span><span class="sxs-lookup"><span data-stu-id="be956-115">Activity relations can be added to both draft or active versions of a production flow.</span></span>  

## <a name="open-the-activity-overview"></a><span data-ttu-id="be956-116">Abrir la visión general de la actividad</span><span class="sxs-lookup"><span data-stu-id="be956-116">Open the activity overview</span></span>
1. <span data-ttu-id="be956-117">Haga clic en Actividades.</span><span class="sxs-lookup"><span data-stu-id="be956-117">Click Activities.</span></span>
    * <span data-ttu-id="be956-118">Tenga en cuenta que el formulario muestra todas las actividades del flujo de producción que se asignan a la versión de los flujo de producción en los que está trabajando.</span><span class="sxs-lookup"><span data-stu-id="be956-118">Note that the form shows all activities of the production flow that are allocated to the Version of the production flows that you are working in.</span></span>  

## <a name="add-a-successor"></a><span data-ttu-id="be956-119">Agregar un sucesor</span><span class="sxs-lookup"><span data-stu-id="be956-119">Add a Successor</span></span>
1. <span data-ttu-id="be956-120">Haga clic en Añadir sucesor.</span><span class="sxs-lookup"><span data-stu-id="be956-120">Click Add successor.</span></span>
2. <span data-ttu-id="be956-121">En el campo Actividad, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="be956-121">In the Activity field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="be956-122">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="be956-122">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="be956-123">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="be956-123">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="be956-124">Active la casilla Restricción.</span><span class="sxs-lookup"><span data-stu-id="be956-124">Select the Constraint check box.</span></span>
6. <span data-ttu-id="be956-125">En el campo Valor de restricción, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="be956-125">In the Constraint value field, enter a number.</span></span>
    * <span data-ttu-id="be956-126">La hora de restricción es la hora que se programará entre el final programado del predecesor (hora y fecha de vencimiento) y el inicio programado del sucesor.</span><span class="sxs-lookup"><span data-stu-id="be956-126">The constraint time is the time to be scheduled between the scheduled end of the predecessor (due date and time) and the scheduled start of the successor.</span></span>  
7. <span data-ttu-id="be956-127">En el campo Unidades, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="be956-127">In the Units field, type a value.</span></span>
8. <span data-ttu-id="be956-128">En campo Coeficiente de tiempo de ciclo, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="be956-128">In the Cycle time ratio field, enter a number.</span></span>
    * <span data-ttu-id="be956-129">Si ambas actividades se ejecutan en el mismo takt, el tiempo de ciclo debe ser 1.</span><span class="sxs-lookup"><span data-stu-id="be956-129">If both activities run at the same takt, the cycle time ratio should be 1.</span></span> <span data-ttu-id="be956-130">Si la predecesora se ejecuta al doble de velocidad que la sucesora, la proporción debe ser 2.</span><span class="sxs-lookup"><span data-stu-id="be956-130">If the predecessor runs at the double speed of the successor, the ratio should be 2.</span></span>   <span data-ttu-id="be956-131">Los coeficientes de tiempo de ciclo se usan para calcular los tiempos de ciclo individuales de las actividades del flujo de producción.</span><span class="sxs-lookup"><span data-stu-id="be956-131">The cycle time ratios are used to calculate the individual cycle times of the production flow activities.</span></span>  
9. <span data-ttu-id="be956-132">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="be956-132">Click OK.</span></span>
10. <span data-ttu-id="be956-133">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="be956-133">Close the page.</span></span>
11. <span data-ttu-id="be956-134">Haga clic en la pestaña del panel de cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="be956-134">Click the GridPanel tab.</span></span>
12. <span data-ttu-id="be956-135">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="be956-135">Close the page.</span></span>
13. <span data-ttu-id="be956-136">Actualice la página.</span><span class="sxs-lookup"><span data-stu-id="be956-136">Refresh the page.</span></span>


