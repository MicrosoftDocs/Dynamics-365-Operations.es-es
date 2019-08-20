---
title: Crear una regla kanban para varias actividades
description: Este procedimiento muestra cómo crear una regla kanban que incluya varias actividades de un flujo de producción.
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanRules, LeanProductionFlowActivityLookup, KanbanFlowSelection, InventItemIdLookupSimple, KanbanCreateScheduled, Kanban
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c7be4e9da6f3dbaf2683c0dba78e0e780628f4b2
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2019
ms.locfileid: "1838664"
---
# <a name="create-a-kanban-rule-for-multiple-activities"></a><span data-ttu-id="76347-103">Crear una regla kanban para varias actividades</span><span class="sxs-lookup"><span data-stu-id="76347-103">Create a kanban rule for multiple activities</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="76347-104">Este procedimiento muestra cómo crear una regla kanban que incluya varias actividades de un flujo de producción.</span><span class="sxs-lookup"><span data-stu-id="76347-104">This procedure shows how to create a kanban rule that includes multiple activities from a production flow.</span></span> <span data-ttu-id="76347-105">La empresa de datos de prueba utilizada para crear esta tarea es USMF.</span><span class="sxs-lookup"><span data-stu-id="76347-105">The demo data company used to create this task is USMF.</span></span> <span data-ttu-id="76347-106">Esta tarea está pensada para el ingeniero de procesos o el administrador de flujo de valor, conforme preparan la producción de un producto nuevo o modificado en un entorno de producción ajustada.</span><span class="sxs-lookup"><span data-stu-id="76347-106">This task is intended for the process engineer or the value stream manager, as they prepare production of a new or modified product in a lean environment.</span></span>


## <a name="create-a-new-kanban-rule"></a><span data-ttu-id="76347-107">Crear una nueva regla kanban</span><span class="sxs-lookup"><span data-stu-id="76347-107">Create a new kanban rule</span></span>
1. <span data-ttu-id="76347-108">Vaya a Gestión de información de productos > Producción ajustada > Reglas kanban.</span><span class="sxs-lookup"><span data-stu-id="76347-108">Go to Product information management > Lean manufacturing > Kanban rules.</span></span>
2. <span data-ttu-id="76347-109">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="76347-109">Click New.</span></span>
3. <span data-ttu-id="76347-110">En el campo Estrategia de reabastecimiento, seleccione "Programado".</span><span class="sxs-lookup"><span data-stu-id="76347-110">In the Replenishment strategy field, select 'Scheduled'.</span></span>
4. <span data-ttu-id="76347-111">En el campo Actividad del primer plan, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="76347-111">In the First plan activity field, enter or select a value.</span></span>
    * <span data-ttu-id="76347-112">Seleccione SpeakerAssemblyAndPolish.</span><span class="sxs-lookup"><span data-stu-id="76347-112">Select SpeakerAssemblyAndPolish.</span></span>  
5. <span data-ttu-id="76347-113">Seleccione la casilla Varias actividades.</span><span class="sxs-lookup"><span data-stu-id="76347-113">Select the Multiple activities check box.</span></span>
    * <span data-ttu-id="76347-114">El propósito es incluir más de una actividad en la regla kanban.</span><span class="sxs-lookup"><span data-stu-id="76347-114">The purpose is to include more than one activity in the kanban rule.</span></span> <span data-ttu-id="76347-115">Elige una ruta en el flujo de producción al seleccionar la última actividad del plan.</span><span class="sxs-lookup"><span data-stu-id="76347-115">You choose a path in the production flow when you select the last plan activity.</span></span>  
6. <span data-ttu-id="76347-116">En el campo Última actividad del plan, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="76347-116">In the Last plan activity field, enter or select a value.</span></span>
    * <span data-ttu-id="76347-117">Seleccione SpeakerTestAndPackaging.</span><span class="sxs-lookup"><span data-stu-id="76347-117">Select SpeakerTestAndPackaging.</span></span> <span data-ttu-id="76347-118">Tras seleccionar el valor, se abre automáticamente una página.</span><span class="sxs-lookup"><span data-stu-id="76347-118">After you select the value, a page automatically opens.</span></span> <span data-ttu-id="76347-119">Seleccione el flujo kanban MontajeYPulidoAltavoces > PruebayEmpaquetdoAltavoces.</span><span class="sxs-lookup"><span data-stu-id="76347-119">Select the kanban flow SpeakerAssemblyAndPolish > SpeakerTestAndPackaging.</span></span> <span data-ttu-id="76347-120">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="76347-120">Click OK.</span></span>  
7. <span data-ttu-id="76347-121">Expanda la sección Detalles.</span><span class="sxs-lookup"><span data-stu-id="76347-121">Expand the Details section.</span></span>
8. <span data-ttu-id="76347-122">En el campo Producto, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="76347-122">In the Product field, enter or select a value.</span></span>
    * <span data-ttu-id="76347-123">Seleccione el artículo L0006.</span><span class="sxs-lookup"><span data-stu-id="76347-123">Select Item L0006.</span></span>  

## <a name="create-kanban-and-view-jobs"></a><span data-ttu-id="76347-124">Crear kanban y ver trabajos</span><span class="sxs-lookup"><span data-stu-id="76347-124">Create kanban and view jobs</span></span>
1. <span data-ttu-id="76347-125">Expanda la sección Kanbans.</span><span class="sxs-lookup"><span data-stu-id="76347-125">Expand the Kanbans section.</span></span>
2. <span data-ttu-id="76347-126">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="76347-126">Click Add.</span></span>
3. <span data-ttu-id="76347-127">En el campo Número de kanbans nuevos, escriba "1".</span><span class="sxs-lookup"><span data-stu-id="76347-127">In the Number of new kanbans field, enter '1'.</span></span>
    * <span data-ttu-id="76347-128">Esto creará un kanban.</span><span class="sxs-lookup"><span data-stu-id="76347-128">This will create one kanban.</span></span>  
4. <span data-ttu-id="76347-129">Defina la cantidad del producto en "3".</span><span class="sxs-lookup"><span data-stu-id="76347-129">Set Product quantity to '3'.</span></span>
    * <span data-ttu-id="76347-130">El kanban procesará 3 productos.</span><span class="sxs-lookup"><span data-stu-id="76347-130">Kanban will process 3 products.</span></span>  
5. <span data-ttu-id="76347-131">En el campo Tiempo transcurrido, especifique una fecha y una hora.</span><span class="sxs-lookup"><span data-stu-id="76347-131">In the Due date/time field, enter a date and time.</span></span>
    * <span data-ttu-id="76347-132">Se puede especificar Hoy.</span><span class="sxs-lookup"><span data-stu-id="76347-132">You can enter Today.</span></span>  
6. <span data-ttu-id="76347-133">Haga clic en Crear.</span><span class="sxs-lookup"><span data-stu-id="76347-133">Click Create.</span></span>
7. <span data-ttu-id="76347-134">Haga clic en Detalles.</span><span class="sxs-lookup"><span data-stu-id="76347-134">Click Details.</span></span>
    * <span data-ttu-id="76347-135">Observe que el kanban tiene dos trabajos de proceso del flujo de producción.</span><span class="sxs-lookup"><span data-stu-id="76347-135">Notice that the kanban has two process jobs from the production flow.</span></span> <span data-ttu-id="76347-136">El primero es SpeakerAssemblyAndPolish y el segundo es SpeakerTestAndPackaging.</span><span class="sxs-lookup"><span data-stu-id="76347-136">The first one is SpeakerAssemblyAndPolish, and the second one is SpeakerTestAndPackaging.</span></span>  
    * <span data-ttu-id="76347-137">Este es el último paso.</span><span class="sxs-lookup"><span data-stu-id="76347-137">This is the last step!</span></span>  

