---
title: Crear una regla kanban para varias actividades
description: Este procedimiento muestra cómo crear una regla kanban que incluya varias actividades de un flujo de producción.
author: ChristianRytt
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanRules, LeanProductionFlowActivityLookup, KanbanFlowSelection, InventItemIdLookupSimple, KanbanCreateScheduled, Kanban
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: bcf507611d7f85800b2012e8372d5f91bbc8d724
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5255190"
---
# <a name="create-a-kanban-rule-for-multiple-activities"></a><span data-ttu-id="54c1f-103">Crear una regla kanban para varias actividades</span><span class="sxs-lookup"><span data-stu-id="54c1f-103">Create a kanban rule for multiple activities</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="54c1f-104">Este procedimiento muestra cómo crear una regla kanban que incluya varias actividades de un flujo de producción.</span><span class="sxs-lookup"><span data-stu-id="54c1f-104">This procedure shows how to create a kanban rule that includes multiple activities from a production flow.</span></span> <span data-ttu-id="54c1f-105">La empresa de datos de prueba utilizada para crear esta tarea es USMF.</span><span class="sxs-lookup"><span data-stu-id="54c1f-105">The demo data company used to create this task is USMF.</span></span> <span data-ttu-id="54c1f-106">Esta tarea está pensada para el ingeniero de procesos o el administrador de flujo de valor, conforme preparan la producción de un producto nuevo o modificado en un entorno de producción ajustada.</span><span class="sxs-lookup"><span data-stu-id="54c1f-106">This task is intended for the process engineer or the value stream manager, as they prepare production of a new or modified product in a lean environment.</span></span>


## <a name="create-a-new-kanban-rule"></a><span data-ttu-id="54c1f-107">Crear una nueva regla kanban</span><span class="sxs-lookup"><span data-stu-id="54c1f-107">Create a new kanban rule</span></span>
1. <span data-ttu-id="54c1f-108">Vaya a Gestión de información de productos > Producción ajustada > Reglas kanban.</span><span class="sxs-lookup"><span data-stu-id="54c1f-108">Go to Product information management > Lean manufacturing > Kanban rules.</span></span>
2. <span data-ttu-id="54c1f-109">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="54c1f-109">Click New.</span></span>
3. <span data-ttu-id="54c1f-110">En el campo Estrategia de reabastecimiento, seleccione "Programado".</span><span class="sxs-lookup"><span data-stu-id="54c1f-110">In the Replenishment strategy field, select 'Scheduled'.</span></span>
4. <span data-ttu-id="54c1f-111">En el campo Actividad del primer plan, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="54c1f-111">In the First plan activity field, enter or select a value.</span></span>
    * <span data-ttu-id="54c1f-112">Seleccione SpeakerAssemblyAndPolish.</span><span class="sxs-lookup"><span data-stu-id="54c1f-112">Select SpeakerAssemblyAndPolish.</span></span>  
5. <span data-ttu-id="54c1f-113">Seleccione la casilla Varias actividades.</span><span class="sxs-lookup"><span data-stu-id="54c1f-113">Select the Multiple activities check box.</span></span>
    * <span data-ttu-id="54c1f-114">El propósito es incluir más de una actividad en la regla kanban.</span><span class="sxs-lookup"><span data-stu-id="54c1f-114">The purpose is to include more than one activity in the kanban rule.</span></span> <span data-ttu-id="54c1f-115">Elige una ruta en el flujo de producción al seleccionar la última actividad del plan.</span><span class="sxs-lookup"><span data-stu-id="54c1f-115">You choose a path in the production flow when you select the last plan activity.</span></span>  
6. <span data-ttu-id="54c1f-116">En el campo Última actividad del plan, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="54c1f-116">In the Last plan activity field, enter or select a value.</span></span>
    * <span data-ttu-id="54c1f-117">Seleccione SpeakerTestAndPackaging.</span><span class="sxs-lookup"><span data-stu-id="54c1f-117">Select SpeakerTestAndPackaging.</span></span> <span data-ttu-id="54c1f-118">Tras seleccionar el valor, se abre automáticamente una página.</span><span class="sxs-lookup"><span data-stu-id="54c1f-118">After you select the value, a page automatically opens.</span></span> <span data-ttu-id="54c1f-119">Seleccione el flujo kanban MontajeYPulidoAltavoces > PruebayEmpaquetdoAltavoces.</span><span class="sxs-lookup"><span data-stu-id="54c1f-119">Select the kanban flow SpeakerAssemblyAndPolish > SpeakerTestAndPackaging.</span></span> <span data-ttu-id="54c1f-120">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="54c1f-120">Click OK.</span></span>  
7. <span data-ttu-id="54c1f-121">Expanda la sección Detalles.</span><span class="sxs-lookup"><span data-stu-id="54c1f-121">Expand the Details section.</span></span>
8. <span data-ttu-id="54c1f-122">En el campo Producto, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="54c1f-122">In the Product field, enter or select a value.</span></span>
    * <span data-ttu-id="54c1f-123">Seleccione el artículo L0006.</span><span class="sxs-lookup"><span data-stu-id="54c1f-123">Select Item L0006.</span></span>  

## <a name="create-kanban-and-view-jobs"></a><span data-ttu-id="54c1f-124">Crear kanban y ver trabajos</span><span class="sxs-lookup"><span data-stu-id="54c1f-124">Create kanban and view jobs</span></span>
1. <span data-ttu-id="54c1f-125">Expanda la sección Kanbans.</span><span class="sxs-lookup"><span data-stu-id="54c1f-125">Expand the Kanbans section.</span></span>
2. <span data-ttu-id="54c1f-126">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="54c1f-126">Click Add.</span></span>
3. <span data-ttu-id="54c1f-127">En el campo Número de kanbans nuevos, escriba "1".</span><span class="sxs-lookup"><span data-stu-id="54c1f-127">In the Number of new kanbans field, enter '1'.</span></span>
    * <span data-ttu-id="54c1f-128">Esto creará un kanban.</span><span class="sxs-lookup"><span data-stu-id="54c1f-128">This will create one kanban.</span></span>  
4. <span data-ttu-id="54c1f-129">Defina la cantidad del producto en "3".</span><span class="sxs-lookup"><span data-stu-id="54c1f-129">Set Product quantity to '3'.</span></span>
    * <span data-ttu-id="54c1f-130">El kanban procesará 3 productos.</span><span class="sxs-lookup"><span data-stu-id="54c1f-130">Kanban will process 3 products.</span></span>  
5. <span data-ttu-id="54c1f-131">En el campo Tiempo transcurrido, especifique una fecha y una hora.</span><span class="sxs-lookup"><span data-stu-id="54c1f-131">In the Due date/time field, enter a date and time.</span></span>
    * <span data-ttu-id="54c1f-132">Se puede especificar Hoy.</span><span class="sxs-lookup"><span data-stu-id="54c1f-132">You can enter Today.</span></span>  
6. <span data-ttu-id="54c1f-133">Haga clic en Crear.</span><span class="sxs-lookup"><span data-stu-id="54c1f-133">Click Create.</span></span>
7. <span data-ttu-id="54c1f-134">Haga clic en Detalles.</span><span class="sxs-lookup"><span data-stu-id="54c1f-134">Click Details.</span></span>
    * <span data-ttu-id="54c1f-135">Observe que el kanban tiene dos trabajos de proceso del flujo de producción.</span><span class="sxs-lookup"><span data-stu-id="54c1f-135">Notice that the kanban has two process jobs from the production flow.</span></span> <span data-ttu-id="54c1f-136">El primero es SpeakerAssemblyAndPolish y el segundo es SpeakerTestAndPackaging.</span><span class="sxs-lookup"><span data-stu-id="54c1f-136">The first one is SpeakerAssemblyAndPolish, and the second one is SpeakerTestAndPackaging.</span></span>  
    * <span data-ttu-id="54c1f-137">Este es el último paso.</span><span class="sxs-lookup"><span data-stu-id="54c1f-137">This is the last step!</span></span>  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]