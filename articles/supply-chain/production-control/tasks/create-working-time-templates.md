---
title: Crear plantillas de horarios de trabajo
description: Las plantillas de horarios de trabajo definen las horas laborables en toda la semana y se usan para generar horarios de trabajo para un período de tiempo.
author: sorenva
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: OpResLifeCycleManagementWorkspace, WorkTimeTable, WorkTimeCopyDayDialog, WorkPeriodTemplate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ed1981b7c1427c902f237f0aa95f63e89bc345ab
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2021
ms.locfileid: "5920938"
---
# <a name="create-working-time-templates"></a><span data-ttu-id="ef58b-103">Crear plantillas de horarios de trabajo</span><span class="sxs-lookup"><span data-stu-id="ef58b-103">Create working time templates</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ef58b-104">Las plantillas de horarios de trabajo definen las horas laborables en toda la semana y se usan para generar horarios de trabajo para un período de tiempo.</span><span class="sxs-lookup"><span data-stu-id="ef58b-104">Working time templates define the working hours throughout a week and are used to generate working times for a period of time.</span></span> <span data-ttu-id="ef58b-105">Este procedimiento le muestra cómo definir una plantilla de horario de trabajo mediante las propiedades de programación de horario de trabajo para clasificar los intervalos de horario de trabajo.</span><span class="sxs-lookup"><span data-stu-id="ef58b-105">This procedure shows you how to define a working time template using working time scheduling properties for categorizing working time intervals.</span></span> <span data-ttu-id="ef58b-106">Puede revisar este procedimiento con los datos de prueba de la empresa USMF o utilizar sus propios datos.</span><span class="sxs-lookup"><span data-stu-id="ef58b-106">You can walk through this procedure in demo data company USMF, or using your own data.</span></span>

1. <span data-ttu-id="ef58b-107">Vaya a **Espacios de trabajo > Administración del ciclo de vida de los recursos**.</span><span class="sxs-lookup"><span data-stu-id="ef58b-107">Go to **Workspaces > Resource lifecycle management**.</span></span>
1. <span data-ttu-id="ef58b-108">Seleccione **Plantillas de horarios de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="ef58b-108">Select **Working time templates**.</span></span>

## <a name="create-working-time-template"></a><span data-ttu-id="ef58b-109">Crear plantilla de horario de trabajo</span><span class="sxs-lookup"><span data-stu-id="ef58b-109">Create working time template</span></span>

1. <span data-ttu-id="ef58b-110">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="ef58b-110">Select **New**.</span></span>
1. <span data-ttu-id="ef58b-111">En el campo **Plantilla de horario de trabajo**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="ef58b-111">In the **Working time template** field, type a value.</span></span>
1. <span data-ttu-id="ef58b-112">En el campo **Nombre**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="ef58b-112">In the **Name** field, type a value.</span></span>
1. <span data-ttu-id="ef58b-113">Expanda la sección **Lunes**.</span><span class="sxs-lookup"><span data-stu-id="ef58b-113">Expand the **Monday** section.</span></span>
1. <span data-ttu-id="ef58b-114">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="ef58b-114">Select **Add**.</span></span>
1. <span data-ttu-id="ef58b-115">En el campo **Desde**, especifique una hora.</span><span class="sxs-lookup"><span data-stu-id="ef58b-115">In the **From** field, enter a time.</span></span>
    * <span data-ttu-id="ef58b-116">Especifique la hora en que el trabajo comienza por la mañana.</span><span class="sxs-lookup"><span data-stu-id="ef58b-116">Specify the time when work begins in the morning.</span></span>  
1. <span data-ttu-id="ef58b-117">En el campo **Hasta**, especifique una hora.</span><span class="sxs-lookup"><span data-stu-id="ef58b-117">In the **To** field, enter a time.</span></span>
    * <span data-ttu-id="ef58b-118">Especifique la hora del descanso para el almuerzo de los trabajadores.</span><span class="sxs-lookup"><span data-stu-id="ef58b-118">Specify the time when workers break for lunch.</span></span>  
1. <span data-ttu-id="ef58b-119">Seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="ef58b-119">Select **Add**.</span></span>
1. <span data-ttu-id="ef58b-120">En el campo **Desde**, especifique una hora.</span><span class="sxs-lookup"><span data-stu-id="ef58b-120">In the **From** field, enter a time.</span></span>
    * <span data-ttu-id="ef58b-121">Especifique la hora en que se reanuda el trabajo tras el almuerzo.</span><span class="sxs-lookup"><span data-stu-id="ef58b-121">Specify the time when work resumes after lunch.</span></span>  
1. <span data-ttu-id="ef58b-122">En el campo **Hasta**, especifique una hora.</span><span class="sxs-lookup"><span data-stu-id="ef58b-122">In the **To** field, enter a time.</span></span>
    * <span data-ttu-id="ef58b-123">Especifique el final del día laborable.</span><span class="sxs-lookup"><span data-stu-id="ef58b-123">Specify the end of the work day.</span></span>  

## <a name="replicate-working-times-to-all-week-days"></a><span data-ttu-id="ef58b-124">Replicar horarios de trabajo en todos los días de la semana</span><span class="sxs-lookup"><span data-stu-id="ef58b-124">Replicate working times to all week days</span></span>

1. <span data-ttu-id="ef58b-125">Seleccione **Copiar día**.</span><span class="sxs-lookup"><span data-stu-id="ef58b-125">Select **Copy day**.</span></span>
    * <span data-ttu-id="ef58b-126">Copiar las definiciones de los horarios de trabajo de lunes a martes.</span><span class="sxs-lookup"><span data-stu-id="ef58b-126">Copy the working times definitions from Monday to Tuesday.</span></span>  
1. <span data-ttu-id="ef58b-127">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ef58b-127">Select **OK**.</span></span>
1. <span data-ttu-id="ef58b-128">Seleccione **Copiar día**.</span><span class="sxs-lookup"><span data-stu-id="ef58b-128">Select **Copy day**.</span></span>
    * <span data-ttu-id="ef58b-129">Copiar las definiciones de los horarios de trabajo de lunes a miércoles.</span><span class="sxs-lookup"><span data-stu-id="ef58b-129">Copy the working times definitions from Monday to Wednesday.</span></span>  
1. <span data-ttu-id="ef58b-130">En el campo **Hasta día laboral**, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="ef58b-130">In the **To weekday** field, select an option.</span></span>
1. <span data-ttu-id="ef58b-131">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ef58b-131">Select **OK**.</span></span>
1. <span data-ttu-id="ef58b-132">Seleccione **Copiar día**.</span><span class="sxs-lookup"><span data-stu-id="ef58b-132">Select **Copy day**.</span></span>
    * <span data-ttu-id="ef58b-133">Copiar las definiciones de los horarios de trabajo de lunes a jueves.</span><span class="sxs-lookup"><span data-stu-id="ef58b-133">Copy the working times definitions from Monday to Thursday.</span></span>  
1. <span data-ttu-id="ef58b-134">En el campo **Hasta día laboral**, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="ef58b-134">In the **To weekday** field, select an option.</span></span>
1. <span data-ttu-id="ef58b-135">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ef58b-135">Select **OK**.</span></span>
1. <span data-ttu-id="ef58b-136">Seleccione **Copiar día**.</span><span class="sxs-lookup"><span data-stu-id="ef58b-136">Select **Copy day**.</span></span>
    * <span data-ttu-id="ef58b-137">Copiar las definiciones de los horarios de trabajo de lunes a viernes.</span><span class="sxs-lookup"><span data-stu-id="ef58b-137">Copy the working times definitions from Monday to Friday.</span></span>  
1. <span data-ttu-id="ef58b-138">En el campo **Hasta día laboral**, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="ef58b-138">In the **To weekday** field, select an option.</span></span>
1. <span data-ttu-id="ef58b-139">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ef58b-139">Select **OK**.</span></span>

## <a name="define-time-slots-for-special-operations"></a><span data-ttu-id="ef58b-140">Definir franjas temporales para operaciones especiales</span><span class="sxs-lookup"><span data-stu-id="ef58b-140">Define time slots for special operations</span></span>

1. <span data-ttu-id="ef58b-141">Expanda la sección **Viernes**.</span><span class="sxs-lookup"><span data-stu-id="ef58b-141">Expand the **Friday** section.</span></span>
1. <span data-ttu-id="ef58b-142">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="ef58b-142">In the list, find and select the desired record.</span></span>
1. <span data-ttu-id="ef58b-143">En el campo **Propiedad**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="ef58b-143">In the **Property** field, enter or select a value.</span></span>
1. <span data-ttu-id="ef58b-144">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="ef58b-144">In the list, find and select the desired record.</span></span>
1. <span data-ttu-id="ef58b-145">En el campo **Propiedad**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="ef58b-145">In the **Property** field, enter or select a value.</span></span>

## <a name="mark-weekend-days-as-closed-for-pickup"></a><span data-ttu-id="ef58b-146">Marcar días de fin de semana como cerrados para recogida</span><span class="sxs-lookup"><span data-stu-id="ef58b-146">Mark weekend days as closed for pickup</span></span>

1. <span data-ttu-id="ef58b-147">Expanda la sección **Sábado**.</span><span class="sxs-lookup"><span data-stu-id="ef58b-147">Expand the **Saturday** section.</span></span>
1. <span data-ttu-id="ef58b-148">Seleccione *Sí* en el campo **Cerrado para recogida**.</span><span class="sxs-lookup"><span data-stu-id="ef58b-148">Select *Yes* in the **Closed for pickup** field.</span></span>
1. <span data-ttu-id="ef58b-149">Expanda la sección **Domingo**.</span><span class="sxs-lookup"><span data-stu-id="ef58b-149">Expand the **Sunday** section.</span></span>
1. <span data-ttu-id="ef58b-150">Seleccione *Sí* en el campo **Cerrado para recogida**.</span><span class="sxs-lookup"><span data-stu-id="ef58b-150">Select *Yes* in the **Closed for pickup** field.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]