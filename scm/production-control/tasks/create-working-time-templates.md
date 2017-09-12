--- 
title: Crear plantillas de horarios de trabajo
description: "Las plantillas de horarios de trabajo definen las horas laborables en toda la semana y se usan para generar horarios de trabajo para un período de tiempo."
author: sorenva
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 2df37747601618fc3d45734152a05aedd39500a6
ms.contentlocale: es-es
ms.lasthandoff: 08/29/2017

---
# <a name="create-working-time-templates"></a><span data-ttu-id="91977-103">Crear plantillas de horarios de trabajo</span><span class="sxs-lookup"><span data-stu-id="91977-103">Create working time templates</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="91977-104">Las plantillas de horarios de trabajo definen las horas laborables en toda la semana y se usan para generar horarios de trabajo para un período de tiempo.</span><span class="sxs-lookup"><span data-stu-id="91977-104">Working time templates define the working hours throughout a week and are used to generate working times for a period of time.</span></span> <span data-ttu-id="91977-105">Este procedimiento le muestra cómo definir una plantilla de horario de trabajo mediante las propiedades de programación de horario de trabajo para clasificar los intervalos de horario de trabajo.</span><span class="sxs-lookup"><span data-stu-id="91977-105">This procedure shows you how to define a working time template using working time scheduling properties for categorizing working time intervals.</span></span> <span data-ttu-id="91977-106">Puede revisar este procedimiento con los datos de prueba de la empresa USMF o utilizar sus propios datos.</span><span class="sxs-lookup"><span data-stu-id="91977-106">You can walk through this procedure in demo data company USMF, or using your own data.</span></span>

1. <span data-ttu-id="91977-107">Vaya a Todos los espacios de trabajo > Administración del ciclo de vida de los recursos.</span><span class="sxs-lookup"><span data-stu-id="91977-107">Go to All workspaces > Resource lifecycle management.</span></span>
2. <span data-ttu-id="91977-108">Haga clic en Plantillas de horarios de trabajo.</span><span class="sxs-lookup"><span data-stu-id="91977-108">Click Working time templates.</span></span>

## <a name="create-working-time-template"></a><span data-ttu-id="91977-109">Crear plantilla de horario de trabajo</span><span class="sxs-lookup"><span data-stu-id="91977-109">Create working time template</span></span>
1. <span data-ttu-id="91977-110">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="91977-110">Click New.</span></span>
2. <span data-ttu-id="91977-111">En el campo Plantilla de horario de trabajo, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="91977-111">In the Working time template field, type a value.</span></span>
3. <span data-ttu-id="91977-112">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="91977-112">In the Name field, type a value.</span></span>
4. <span data-ttu-id="91977-113">Expanda la sección Lunes.</span><span class="sxs-lookup"><span data-stu-id="91977-113">Expand the Monday section.</span></span>
5. <span data-ttu-id="91977-114">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="91977-114">Click Add.</span></span>
6. <span data-ttu-id="91977-115">En el campo Desde, especifique una hora.</span><span class="sxs-lookup"><span data-stu-id="91977-115">In the From field, enter a time.</span></span>
    * <span data-ttu-id="91977-116">Especifique la hora en que el trabajo comienza por la mañana.</span><span class="sxs-lookup"><span data-stu-id="91977-116">Specify the time when work begins in the morning.</span></span>  
7. <span data-ttu-id="91977-117">En el campo Hasta, especifique una hora.</span><span class="sxs-lookup"><span data-stu-id="91977-117">In the To field, enter a time.</span></span>
    * <span data-ttu-id="91977-118">Especifique la hora del descanso para el almuerzo de los trabajadores.</span><span class="sxs-lookup"><span data-stu-id="91977-118">Specify the time when workers break for lunch.</span></span>  
8. <span data-ttu-id="91977-119">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="91977-119">Click Add.</span></span>
9. <span data-ttu-id="91977-120">En el campo Desde, especifique una hora.</span><span class="sxs-lookup"><span data-stu-id="91977-120">In the From field, enter a time.</span></span>
    * <span data-ttu-id="91977-121">Especifique la hora en que se reanuda el trabajo tras el almuerzo.</span><span class="sxs-lookup"><span data-stu-id="91977-121">Specify the time when work resumes after lunch.</span></span>  
10. <span data-ttu-id="91977-122">En el campo Hasta, especifique una hora.</span><span class="sxs-lookup"><span data-stu-id="91977-122">In the To field, enter a time.</span></span>
    * <span data-ttu-id="91977-123">Especifique el final del día laborable.</span><span class="sxs-lookup"><span data-stu-id="91977-123">Specify the end of the work day.</span></span>  

## <a name="replicate-working-times-to-all-week-days"></a><span data-ttu-id="91977-124">Replicar horarios de trabajo en todos los días de la semana</span><span class="sxs-lookup"><span data-stu-id="91977-124">Replicate working times to all week days</span></span>
1. <span data-ttu-id="91977-125">Haga clic en Copiar día.</span><span class="sxs-lookup"><span data-stu-id="91977-125">Click Copy day.</span></span>
    * <span data-ttu-id="91977-126">Copiar las definiciones de los horarios de trabajo de lunes a martes.</span><span class="sxs-lookup"><span data-stu-id="91977-126">Copy the working times definitions from Monday to Tuesday.</span></span>  
2. <span data-ttu-id="91977-127">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="91977-127">Click OK.</span></span>
3. <span data-ttu-id="91977-128">Haga clic en Copiar día.</span><span class="sxs-lookup"><span data-stu-id="91977-128">Click Copy day.</span></span>
    * <span data-ttu-id="91977-129">Copiar las definiciones de los horarios de trabajo de lunes a miércoles.</span><span class="sxs-lookup"><span data-stu-id="91977-129">Copy the working times definitions from Monday to Wednesday.</span></span>  
4. <span data-ttu-id="91977-130">En el campo Hasta día laboral, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="91977-130">In the To weekday field, select an option.</span></span>
5. <span data-ttu-id="91977-131">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="91977-131">Click OK.</span></span>
6. <span data-ttu-id="91977-132">Haga clic en Copiar día.</span><span class="sxs-lookup"><span data-stu-id="91977-132">Click Copy day.</span></span>
    * <span data-ttu-id="91977-133">Copiar las definiciones de los horarios de trabajo de lunes a jueves.</span><span class="sxs-lookup"><span data-stu-id="91977-133">Copy the working times definitions from Monday to Thursday.</span></span>  
7. <span data-ttu-id="91977-134">En el campo Hasta día laboral, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="91977-134">In the To weekday field, select an option.</span></span>
8. <span data-ttu-id="91977-135">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="91977-135">Click OK.</span></span>
9. <span data-ttu-id="91977-136">Haga clic en Copiar día.</span><span class="sxs-lookup"><span data-stu-id="91977-136">Click Copy day.</span></span>
    * <span data-ttu-id="91977-137">Copiar las definiciones de los horarios de trabajo de lunes a viernes.</span><span class="sxs-lookup"><span data-stu-id="91977-137">Copy the working times definitions from Monday to Friday.</span></span>  
10. <span data-ttu-id="91977-138">En el campo Hasta día laboral, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="91977-138">In the To weekday field, select an option.</span></span>
11. <span data-ttu-id="91977-139">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="91977-139">Click OK.</span></span>

## <a name="define-time-slots-for-special-operations"></a><span data-ttu-id="91977-140">Definir franjas temporales para operaciones especiales</span><span class="sxs-lookup"><span data-stu-id="91977-140">Define time slots for special operations</span></span>
1. <span data-ttu-id="91977-141">Expanda la sección Viernes.</span><span class="sxs-lookup"><span data-stu-id="91977-141">Expand the Friday section.</span></span>
2. <span data-ttu-id="91977-142">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="91977-142">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="91977-143">En el campo Propiedad, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="91977-143">In the Property field, enter or select a value.</span></span>
4. <span data-ttu-id="91977-144">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="91977-144">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="91977-145">En el campo Propiedad, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="91977-145">In the Property field, enter or select a value.</span></span>

## <a name="mark-weekend-days-as-closed-for-pickup"></a><span data-ttu-id="91977-146">Marcar días de fin de semana como cerrados para recogida</span><span class="sxs-lookup"><span data-stu-id="91977-146">Mark weekend days as closed for pickup</span></span>
1. <span data-ttu-id="91977-147">Expanda la sección Sábado.</span><span class="sxs-lookup"><span data-stu-id="91977-147">Expand the Saturday section.</span></span>
2. <span data-ttu-id="91977-148">Seleccione Sí en el campo Cerrado para recogida.</span><span class="sxs-lookup"><span data-stu-id="91977-148">Select Yes in the Closed for pickup field.</span></span>
3. <span data-ttu-id="91977-149">Expanda la sección Domingo.</span><span class="sxs-lookup"><span data-stu-id="91977-149">Expand the Sunday section.</span></span>
4. <span data-ttu-id="91977-150">Seleccione Sí en el campo Cerrado para recogida.</span><span class="sxs-lookup"><span data-stu-id="91977-150">Select Yes in the Closed for pickup field.</span></span>


