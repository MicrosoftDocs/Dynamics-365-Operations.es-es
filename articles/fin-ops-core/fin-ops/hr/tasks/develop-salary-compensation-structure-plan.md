---
title: Desarrollar plan y estructura de salarios o compensaciones
description: Esta guía de la tarea le lleva por el proceso de crear un plan de compensación fija y permitir que los empleados se inscriban en el plan a través de las reglas de idoneidad.
author: andreabichsel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, HcmCompensationWorkspace, HcmCompFixedPlansPart, HRMCompFixedPlanTable, HRMCompCreateGridDialog, HRCCompGridView, HRMCompEligibility,  HRCCompGrid
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3f0732736736fdc87f3367f24b1d20b9fa6efc59
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "2179885"
---
# <a name="develop-salarycompensation-structure-and-plan"></a><span data-ttu-id="3fe2a-103">Desarrollar plan y estructura de salarios o compensaciones</span><span class="sxs-lookup"><span data-stu-id="3fe2a-103">Develop salary/compensation structure and plan</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="3fe2a-104">Esta guía de la tarea le lleva por el proceso de crear un plan de compensación fija y permitir que los empleados se inscriban en el plan a través de las reglas de idoneidad.</span><span class="sxs-lookup"><span data-stu-id="3fe2a-104">This task guide walks though the process of creating a Fixed compensation plan and enabling employees to be enrolled in the plan through eligibility rules.</span></span> <span data-ttu-id="3fe2a-105">La empresa de datos de prueba utilizada para crear esta tarea es USMF y la tarea está pensada para los directores de compensaciones y prestaciones.</span><span class="sxs-lookup"><span data-stu-id="3fe2a-105">The demo data company used to create this task is USMF and the task is intended for Compensation and Benefits Managers.</span></span>


## <a name="create-fixed-compensation-plan"></a><span data-ttu-id="3fe2a-106">Crear un plan de compensación fija</span><span class="sxs-lookup"><span data-stu-id="3fe2a-106">Create fixed compensation plan</span></span>
1. <span data-ttu-id="3fe2a-107">Haga clic en Administración de compensaciones.</span><span class="sxs-lookup"><span data-stu-id="3fe2a-107">Click Compensation management.</span></span>
2. <span data-ttu-id="3fe2a-108">Haga clic en Planes de compensación fija.</span><span class="sxs-lookup"><span data-stu-id="3fe2a-108">Click Fixed compensation plans.</span></span>
3. <span data-ttu-id="3fe2a-109">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="3fe2a-109">Click New.</span></span>
4. <span data-ttu-id="3fe2a-110">En el campo Plan, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="3fe2a-110">In the Plan field, type a value.</span></span>
5. <span data-ttu-id="3fe2a-111">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="3fe2a-111">In the Description field, type a value.</span></span>
6. <span data-ttu-id="3fe2a-112">En el campo Fecha de vigencia, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="3fe2a-112">In the Effective date field, enter a date.</span></span>
7. <span data-ttu-id="3fe2a-113">En el campo Tipo, seleccione si el plan de compensación fija es un grupo, una categoría o un paso.</span><span class="sxs-lookup"><span data-stu-id="3fe2a-113">In the Type field, select whether the Fixed compensation plan is a Band, Grade, or Step plan.</span></span>
8. <span data-ttu-id="3fe2a-114">La casilla Recomendación permitida actúa como valor predeterminado para las acciones agregadas a este plan de un evento de procesos.</span><span class="sxs-lookup"><span data-stu-id="3fe2a-114">The Recommendation allowed checkbox acts as a default value for any actions added to this plan in a Process event.</span></span>  <span data-ttu-id="3fe2a-115">Habilitar las recomendaciones le permite anular el importe calculado del criterio al procesar la compensación.</span><span class="sxs-lookup"><span data-stu-id="3fe2a-115">Allowing recommendations enables you to override the calculated guideline amount when processing compensation.</span></span>
9. <span data-ttu-id="3fe2a-116">La tolerancia de Fuera de intervalo le permite especificar cómo desea gestionar los importes de contrapartida que se encuentran fuera del intervalo de la estructura de compensación para el nivel dado.</span><span class="sxs-lookup"><span data-stu-id="3fe2a-116">The Out of range tolerance allows you to specify how you want to handle compensation amounts that fall outside of the specified compensation structure range for the given level.</span></span>  <span data-ttu-id="3fe2a-117">Una tolerancia de Fuera de intervalo establecida en Ninguna permitirá que se use cualquier importe de compensación.</span><span class="sxs-lookup"><span data-stu-id="3fe2a-117">An Out of range tolerance of None will allow any compensation amount to be used.</span></span>  <span data-ttu-id="3fe2a-118">Una tolerancia débil advertirá el usuario si el importe de compensación es inferior al importe mínimo de puntos de referencia para dicho nivel o mayor que el importe máximo para dicho nivel.</span><span class="sxs-lookup"><span data-stu-id="3fe2a-118">A Soft tolerance will warn the user if the compensation amount is less than the minimum reference point amount for that level, or greater than the maximum amount for that level.</span></span> <span data-ttu-id="3fe2a-119">El usuario puede ignorar la advertencia y continuar.</span><span class="sxs-lookup"><span data-stu-id="3fe2a-119">The user can ignore the warning and continue.</span></span>  <span data-ttu-id="3fe2a-120">Una tolerancia estricta generará un error si la compensación del empleado está fuera de los puntos de referencia mínimo y máximo para el nivel y ajustará automáticamente la compensación del empleado para que esté dentro del intervalo.</span><span class="sxs-lookup"><span data-stu-id="3fe2a-120">A Hard tolerance will generate an error if an employee's compensation is set outside of the minimum and maximum reference points for the level and will automatically adjust the employee's compensation to fall within the range.</span></span>
10. <span data-ttu-id="3fe2a-121">El campo Regla de contratación se usa cuando un evento de proceso de compensación se ejecuta para calcular la compensación del empleado.</span><span class="sxs-lookup"><span data-stu-id="3fe2a-121">The Hire rule field is used when a compensation Process event is run to calculate an employee's compensation.</span></span>  <span data-ttu-id="3fe2a-122">Una Regla de contratación de Porcentaje calculará un aumento que esté prorrateado para la duración de tiempo que el trabajador ha estado contratado en el ciclo.</span><span class="sxs-lookup"><span data-stu-id="3fe2a-122">A Hire rule of Percent will calculate an increase that's prorated for the length of the time the worker has been employed in the cycle.</span></span>
11. <span data-ttu-id="3fe2a-123">En el campo Divisa, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="3fe2a-123">In the Currency field, type a value.</span></span>
12. <span data-ttu-id="3fe2a-124">En el campo Conversión de índice salarial, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="3fe2a-124">In the Pay rate conversion field, enter or select a value.</span></span>
13. <span data-ttu-id="3fe2a-125">Expanda la sección Matriz del intervalo de aprovechamiento.</span><span class="sxs-lookup"><span data-stu-id="3fe2a-125">Expand the Range utilization matrix section.</span></span>
    * <span data-ttu-id="3fe2a-126">Opcionalmente, agregue los registros del intervalo de aprovechamiento para hacer más rápidos a los empleados que están en el punto medio y ralentizarlos para que no lleguen al máximo de su intervalo.</span><span class="sxs-lookup"><span data-stu-id="3fe2a-126">Optionally, add range utilization records to get employees to their midpoint faster and slow them from reaching the maximum of their range.</span></span>  
14. <span data-ttu-id="3fe2a-127">En este momento, debe guardar el plan de compensación fija para habilitar el botón Configurar compensación y continuar definiendo su estructura de compensación para el plan.</span><span class="sxs-lookup"><span data-stu-id="3fe2a-127">At this point, you must save the Fixed compensation plan to enable the Set up compensation button and continue defining your compensation structure for the plan.</span></span>  <span data-ttu-id="3fe2a-128">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="3fe2a-128">Click Save.</span></span>
15. <span data-ttu-id="3fe2a-129">Haga clic en Configurar compensación.</span><span class="sxs-lookup"><span data-stu-id="3fe2a-129">Click Set up compensation.</span></span>
    * <span data-ttu-id="3fe2a-130">Hay tres maneras de crear una estructura de compensación.</span><span class="sxs-lookup"><span data-stu-id="3fe2a-130">There are three ways to create a compensation structure.</span></span> <span data-ttu-id="3fe2a-131">1: Para crear una estructura totalmente nueva, seleccione un conjunto de puntos de referencia y agregue niveles para crear su propia estructura.</span><span class="sxs-lookup"><span data-stu-id="3fe2a-131">1: Create a completely new structure by selecting a set of reference points and adding the levels to create your own structure.</span></span> <span data-ttu-id="3fe2a-132">2: Copiar una estructura de compensación de un plan existente como punto de partida y modificarla para el nuevo plan.</span><span class="sxs-lookup"><span data-stu-id="3fe2a-132">2: Copy a compensation structure from an existing plan as a starting point and modify it for the new plan.</span></span> <span data-ttu-id="3fe2a-133">3: Seleccionar una cuadrícula de compensación existente.</span><span class="sxs-lookup"><span data-stu-id="3fe2a-133">3: Select an existing compensation grid.</span></span> <span data-ttu-id="3fe2a-134">Si la cuadrícula de compensación se está usando ya en otro plan, cualquier cambio efectuado en la cuadrícula también se reflejará en el otro plan.</span><span class="sxs-lookup"><span data-stu-id="3fe2a-134">If the compensation grid is already being used by another plan, any changes made to the grid will also be reflected in the other plan.</span></span>  
16. <span data-ttu-id="3fe2a-135">Seleccione la opción Crear una nueva matriz a partir de la matriz de compensación existente.</span><span class="sxs-lookup"><span data-stu-id="3fe2a-135">Select the Create new from existing compensation matrix option.</span></span>
17. <span data-ttu-id="3fe2a-136">En el campo Copiar de cuadrícula, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="3fe2a-136">In the Copy from grid field, enter or select a value.</span></span>
    * <span data-ttu-id="3fe2a-137">Puede cambiar opcionalmente el nombre de la nueva cuadrícula de compensación que se creará como una copia de la cuadrícula seleccionada.</span><span class="sxs-lookup"><span data-stu-id="3fe2a-137">Optionally you can change the name of the new compensation grid that will be created as a copy of the selected grid.</span></span>  
18. <span data-ttu-id="3fe2a-138">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="3fe2a-138">Click OK.</span></span>
19. <span data-ttu-id="3fe2a-139">Haga clic en Cambio masivo.</span><span class="sxs-lookup"><span data-stu-id="3fe2a-139">Click Mass change.</span></span>
    * <span data-ttu-id="3fe2a-140">El cambio masivo le permite mantener las cantidades de la matriz de compensación aplicando un aumento de porcentaje o fijo a uno o varios niveles y/o puntos de referencia.</span><span class="sxs-lookup"><span data-stu-id="3fe2a-140">Mass change allows you to maintain the compensation matrix amounts by applying a percent or flat amount increase to one or more levels and/or reference points.</span></span>  
20. <span data-ttu-id="3fe2a-141">En el campo Importe del ajuste, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="3fe2a-141">In the Adjustment amount field, enter a number.</span></span>
21. <span data-ttu-id="3fe2a-142">En la lista, active o desactive todas las filas.</span><span class="sxs-lookup"><span data-stu-id="3fe2a-142">In the list, mark or unmark all rows.</span></span>
22. <span data-ttu-id="3fe2a-143">Haga clic en Aplicar a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="3fe2a-143">Click Apply to grid.</span></span>
23. <span data-ttu-id="3fe2a-144">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="3fe2a-144">Close the page.</span></span>
    * <span data-ttu-id="3fe2a-145">Una vez que se ha creado o se ha seleccionado una estructura de compensación, puede seleccionar qué puntos de referencia deben utilizarse como punto de control para el plan de compensación fija.</span><span class="sxs-lookup"><span data-stu-id="3fe2a-145">Once a compensation structure has been created or selected, you can select which of the reference points should be used as the Control point for the Fixed compensation plan.</span></span>  <span data-ttu-id="3fe2a-146">El punto de control se usa para calcular el ratio de comparación de un empleado.</span><span class="sxs-lookup"><span data-stu-id="3fe2a-146">The Control point is used to calculate an employee's Compa Ratio.</span></span>  
24. <span data-ttu-id="3fe2a-147">En el campo Punto de control, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="3fe2a-147">In the Control point field, enter or select a value.</span></span>
25. <span data-ttu-id="3fe2a-148">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="3fe2a-148">Close the page.</span></span>

## <a name="create-an-eligibility-rule-for-the-new-fixed-compensation-plan"></a><span data-ttu-id="3fe2a-149">Crear una regla de elegibilidad para el nuevo plan de compensación fija</span><span class="sxs-lookup"><span data-stu-id="3fe2a-149">Create an eligibility rule for the new Fixed compensation plan</span></span>
    * <span data-ttu-id="3fe2a-150">El nuevo plan de compensación fija no se puede asignar a un empleado hasta que se hayan definido las reglas de idoneidad para el plan.</span><span class="sxs-lookup"><span data-stu-id="3fe2a-150">The new Fixed compensation plan cannot be assigned to an employee until Eligibility rules have been defined for the plan.</span></span>  
1. <span data-ttu-id="3fe2a-151">Haga clic en Reglas de idoneidad.</span><span class="sxs-lookup"><span data-stu-id="3fe2a-151">Click Eligibility rules.</span></span>
2. <span data-ttu-id="3fe2a-152">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="3fe2a-152">Click New.</span></span>
3. <span data-ttu-id="3fe2a-153">En el campo Idoneidad, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="3fe2a-153">In the Eligibility field, type a value.</span></span>
4. <span data-ttu-id="3fe2a-154">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="3fe2a-154">In the Description field, type a value.</span></span>
5. <span data-ttu-id="3fe2a-155">En el campo Fecha de vigencia, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="3fe2a-155">In the Effective date field, enter a date.</span></span>
    * <span data-ttu-id="3fe2a-156">Las reglas de idoneidad se utilizan para los planes de compensación fijos y variables.</span><span class="sxs-lookup"><span data-stu-id="3fe2a-156">Eligibility rules are used for both Fixed and Variable compensation plans.</span></span>  <span data-ttu-id="3fe2a-157">En el campo Tipo, seleccione para qué tipo de plan es este conjunto de reglas de idoneidad.</span><span class="sxs-lookup"><span data-stu-id="3fe2a-157">In the Type field, select which type of plan this set of eligibility rules is for.</span></span>  
6. <span data-ttu-id="3fe2a-158">En el campo Plan, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="3fe2a-158">In the Plan field, enter or select a value.</span></span>
    * <span data-ttu-id="3fe2a-159">Seleccione los criterios que un empleado debe cumplir para ser idóneo para el plan de compensación.</span><span class="sxs-lookup"><span data-stu-id="3fe2a-159">Select the criteria an employee must meet in order to be eligible for the compensation plan.</span></span> <span data-ttu-id="3fe2a-160">Los criterios pueden incluir un departamento, un sindicato, una ubicación (región de compensación), un trabajo, una función, un tipo de trabajo o un nivel de compensación.</span><span class="sxs-lookup"><span data-stu-id="3fe2a-160">Criteria can include a Department, Labor union, Location (Compensation region), Job, Function, Job type, or Compensation level.</span></span> <span data-ttu-id="3fe2a-161">El empleado debe cumplir todos los criterios especificados para ser idóneo para el plan de compensación.</span><span class="sxs-lookup"><span data-stu-id="3fe2a-161">The employee must meet all specified criteria to be eligible for the compensation plan.</span></span> <span data-ttu-id="3fe2a-162">Si no se especifica ningún criterio, todos los empleados son idóneos para el plan de compensación.</span><span class="sxs-lookup"><span data-stu-id="3fe2a-162">If no criteria are specified, all employees are eligible for the compensation plan.</span></span> <span data-ttu-id="3fe2a-163">Si un empleado no cumple los criterios especificados en la regla de idoneidad o una regla de idoneidad no se ha especificado para un plan de compensación, el plan de compensación no aparecerá en las búsquedas al crear un registro de compensación fija para un empleado.</span><span class="sxs-lookup"><span data-stu-id="3fe2a-163">If an employee does not meet the criteria specified in the eligibility rule, or an eligibility rule has not been specified for a compensation plan, the compensation plan will not appear in the lookup when creating a Fixed compensation record for an employee.</span></span>  
7. <span data-ttu-id="3fe2a-164">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="3fe2a-164">Close the page.</span></span>
8. <span data-ttu-id="3fe2a-165">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="3fe2a-165">Close the page.</span></span>
