---
title: Desarrollar una estructura de compensaciones
description: Este artículo le guía por el proceso de crear un plan de compensación fijo e inscribir empleados en el plan siguiendo reglas de idoneidad.
author: andreabichsel
manager: AnnBe
ms.date: 02/10/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: DefaultDashboard, HcmCompensationWorkspace, HcmCompFixedPlansPart, HRMCompFixedPlanTable, HRMCompCreateGridDialog, HRCCompGridView, HRMCompEligibility,  HRCCompGrid
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 124d0f7f83feebabf622f00732c25bfa0f6eccdd
ms.sourcegitcommit: de715b7fda2f1548f2f443b9e0f6d09f5b881d61
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/10/2020
ms.locfileid: "3034272"
---
# <a name="develop-a-compensation-structure"></a><span data-ttu-id="0757a-103">Desarrollar una estructura de compensaciones</span><span class="sxs-lookup"><span data-stu-id="0757a-103">Develop a compensation structure</span></span>

<span data-ttu-id="0757a-104">Este artículo le guía por el proceso de crear un plan de compensación fijo e inscribir empleados en el plan siguiendo reglas de idoneidad.</span><span class="sxs-lookup"><span data-stu-id="0757a-104">This article walks you through creating a fixed compensation plan and enrolling employees in the plan through eligibility rules.</span></span> <span data-ttu-id="0757a-105">Este artículo utiliza los datos de demostración de USMF y se aplica a los Gerentes de Compensación y Beneficios.</span><span class="sxs-lookup"><span data-stu-id="0757a-105">This article uses the USMF demo data and applies to Compensation and Benefits Managers.</span></span>

## <a name="create-a-fixed-compensation-plan"></a><span data-ttu-id="0757a-106">Crear un plan de compensación fija</span><span class="sxs-lookup"><span data-stu-id="0757a-106">Create a fixed compensation plan</span></span>

1. <span data-ttu-id="0757a-107">Seleccione **Administración de compensaciones**.</span><span class="sxs-lookup"><span data-stu-id="0757a-107">Select **Compensation management**.</span></span>

2. <span data-ttu-id="0757a-108">Seleccione **Crear planes de compensación fija**.</span><span class="sxs-lookup"><span data-stu-id="0757a-108">Select **Fixed compensation plans**.</span></span>

3. <span data-ttu-id="0757a-109">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="0757a-109">Select **New**.</span></span>

4. <span data-ttu-id="0757a-110">En el campo **Plan**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="0757a-110">In the **Plan** field, enter a value.</span></span>

5. <span data-ttu-id="0757a-111">En el campo **Descripción**, especifique un valor.</span><span class="sxs-lookup"><span data-stu-id="0757a-111">In the **Description** field, enter a value.</span></span>

6. <span data-ttu-id="0757a-112">En el campo **Fecha de vigencia**, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="0757a-112">In the **Effective date** field, enter a date.</span></span>

7. <span data-ttu-id="0757a-113">En el campo **Tipo,** seleccione si el plan de compensación fija es un plan de **Banda**, **Categoría** o **Paso**.</span><span class="sxs-lookup"><span data-stu-id="0757a-113">In the **Type** field, select whether the fixed compensation plan is a **Band**, **Grade**, or **Step** plan.</span></span>

8. <span data-ttu-id="0757a-114">La casilla **Recomendación permitida** actúa como valor predeterminado para las acciones agregadas a este plan de un evento de procesos.</span><span class="sxs-lookup"><span data-stu-id="0757a-114">The **Recommendation allowed** checkbox acts as a default value for any actions added to this plan in a Process event.</span></span> <span data-ttu-id="0757a-115">Habilitar las recomendaciones le permite anular el importe calculado del criterio al procesar la compensación.</span><span class="sxs-lookup"><span data-stu-id="0757a-115">Allowing recommendations enables you to override the calculated guideline amount when processing compensation.</span></span>

9. <span data-ttu-id="0757a-116">El campo **Fuera de intervalo de tolerancia** le permite especificar cómo desea gestionar los importes de contrapartida que se encuentran fuera del intervalo de la estructura de compensación para el nivel dado.</span><span class="sxs-lookup"><span data-stu-id="0757a-116">The **Out of range tolerance** field allows you to specify how you want to handle compensation amounts that fall outside of the specified compensation structure range for the given level.</span></span> <span data-ttu-id="0757a-117">Establecer el campo **Fuera del rango de tolerancia** a **Ninguno** le permite usar cualquier importe de compensación.</span><span class="sxs-lookup"><span data-stu-id="0757a-117">Setting the **Out of range tolerance** field to **None** allows you to use any compensation amount.</span></span> <span data-ttu-id="0757a-118">Una **Tolerancia débil** advertirá a los usuarios si el importe de compensación es inferior o superior al importe de punto de referencia máximo para ese nivel.</span><span class="sxs-lookup"><span data-stu-id="0757a-118">**Soft tolerance** warns users if the compensation amount is less than the minimum or greater than the maximum reference point amounts for that level.</span></span> <span data-ttu-id="0757a-119">El usuario puede ignorar la advertencia y continuar.</span><span class="sxs-lookup"><span data-stu-id="0757a-119">Users can ignore the warning and continue.</span></span> <span data-ttu-id="0757a-120">Una **Tolerancia estricta** generará un error si la compensación del empleado está fuera de los puntos de referencia mínimo y máximo para el nivel y ajustará automáticamente la compensación del empleado para que esté dentro del intervalo.</span><span class="sxs-lookup"><span data-stu-id="0757a-120">**Hard tolerance** generates an error if an employee's compensation is outside the minimum and maximum reference points for the level and will automatically adjust the employee's compensation to fall within the range.</span></span>

10. <span data-ttu-id="0757a-121">El campo **Regla de contratación** calcula la compensación de un empleado durante un evento de proceso.</span><span class="sxs-lookup"><span data-stu-id="0757a-121">The **Hire rule** field calculates an employee's compensation during a process event.</span></span> <span data-ttu-id="0757a-122">Una **Regla de contratación** de **Porcentaje** calculará un aumento que esté prorrateado para la duración de tiempo que el trabajador ha estado contratado en el ciclo.</span><span class="sxs-lookup"><span data-stu-id="0757a-122">A **Hire rule** of **Percent** calculates an increase that's prorated for the length of the time the worker has been employed in the cycle.</span></span>

11. <span data-ttu-id="0757a-123">En el campo **Divisa**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="0757a-123">In the **Currency** field, type a value.</span></span>

12. <span data-ttu-id="0757a-124">En el campo **Conversión de índice salarial**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="0757a-124">In the **Pay rate conversion** field, enter or select a value.</span></span>

13. <span data-ttu-id="0757a-125">Expanda la sección **Matriz del intervalo de aprovechamiento**.</span><span class="sxs-lookup"><span data-stu-id="0757a-125">Expand the **Range utilization matrix** section.</span></span> <span data-ttu-id="0757a-126">Opcionalmente, agregue los registros del intervalo de aprovechamiento para hacer más rápidos a los empleados que están en el punto medio y ralentizarlos para que no lleguen al máximo de su intervalo.</span><span class="sxs-lookup"><span data-stu-id="0757a-126">Optionally, add range utilization records to get employees to their midpoint faster and slow them from reaching the maximum of their range.</span></span>

14. <span data-ttu-id="0757a-127">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="0757a-127">Select **Save**.</span></span> <span data-ttu-id="0757a-128">Esto activa el botón **Configurar compensación** y continúa definiendo su estructura de compensación para el plan.</span><span class="sxs-lookup"><span data-stu-id="0757a-128">This enables the **Set up compensation** button and continue defining your compensation structure for the plan.</span></span>

15. <span data-ttu-id="0757a-129">Seleccione **Configurar compensación**.</span><span class="sxs-lookup"><span data-stu-id="0757a-129">Select **Set up compensation**.</span></span> <span data-ttu-id="0757a-130">Puede crear una estructura de compensación usando uno de estos tres métodos:</span><span class="sxs-lookup"><span data-stu-id="0757a-130">You can create a compensation structure by using one of these three methods:</span></span>

    - <span data-ttu-id="0757a-131">Para crear una estructura totalmente nueva, seleccione un conjunto de puntos de referencia y agregue niveles para crear su propia estructura.</span><span class="sxs-lookup"><span data-stu-id="0757a-131">Create a completely new structure by selecting a set of reference points and adding the levels to create your own structure.</span></span>
    - <span data-ttu-id="0757a-132">Copiar una estructura de compensación de un plan existente como punto de partida y modificarla para el nuevo plan.</span><span class="sxs-lookup"><span data-stu-id="0757a-132">Copy a compensation structure from an existing plan as a starting point and modify it for the new plan.</span></span>
    - <span data-ttu-id="0757a-133">Seleccionar una cuadrícula de compensación existente.</span><span class="sxs-lookup"><span data-stu-id="0757a-133">Select an existing compensation grid.</span></span> <span data-ttu-id="0757a-134">Si otro plan ya usa la cuadrícula de compensación, el otro plan también releja cualquier cambio que haga a la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="0757a-134">If another plan already uses the compensation grid, the other plan also reflects any changes you make to the grid.</span></span>

16. <span data-ttu-id="0757a-135">Seleccione **Crear nueva a partir de la matriz de compensación existente**.</span><span class="sxs-lookup"><span data-stu-id="0757a-135">Select **Create new from existing compensation matrix**.</span></span>

17. <span data-ttu-id="0757a-136">En el campo **Copiar cuadrícula**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="0757a-136">In the **Copy from grid** field, enter or select a value.</span></span> <span data-ttu-id="0757a-137">Puede cambiar opcionalmente el nombre de la nueva cuadrícula de compensación que creará como una copia de la cuadrícula seleccionada.</span><span class="sxs-lookup"><span data-stu-id="0757a-137">Optionally, you can change the name of the new compensation grid that you create by copying the selected grid.</span></span>

18. <span data-ttu-id="0757a-138">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0757a-138">Select **OK**.</span></span>

19. <span data-ttu-id="0757a-139">Seleccione **Cambio masivo**.</span><span class="sxs-lookup"><span data-stu-id="0757a-139">Select **Mass change**.</span></span> <span data-ttu-id="0757a-140">**Cambio masivo** le permite mantener las cantidades de la matriz de compensación aplicando un aumento de porcentaje o fijo a uno o varios niveles o puntos de referencia.</span><span class="sxs-lookup"><span data-stu-id="0757a-140">**Mass change** allows you to maintain the compensation matrix amounts by applying a percent or flat amount increase to one or more levels or reference points.</span></span>

20. <span data-ttu-id="0757a-141">En el campo **Importe del ajuste**, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="0757a-141">In the **Adjustment amount** field, enter a number.</span></span>

21. <span data-ttu-id="0757a-142">En la lista, active o desactive todas las filas.</span><span class="sxs-lookup"><span data-stu-id="0757a-142">In the list, mark or unmark all rows.</span></span>

22. <span data-ttu-id="0757a-143">Haga clic en **Aplicar a la cuadrícula**.</span><span class="sxs-lookup"><span data-stu-id="0757a-143">Click **Apply to grid**.</span></span>

23. <span data-ttu-id="0757a-144">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="0757a-144">Close the page.</span></span> <span data-ttu-id="0757a-145">Una vez que ha creado una estructura de compensación, puede seleccionar qué puntos de referencia deben utilizarse como punto de control para el plan de compensación fija.</span><span class="sxs-lookup"><span data-stu-id="0757a-145">After you create the compensation structure, you can select which of the reference points to use as the control point for the fixed compensation plan.</span></span> <span data-ttu-id="0757a-146">El punto de control se usa para calcular el ratio de comparación de un empleado.</span><span class="sxs-lookup"><span data-stu-id="0757a-146">The control point is used to calculate an employee's Compa Ratio.</span></span>

24. <span data-ttu-id="0757a-147">En el campo **Punto de control**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="0757a-147">In the **Control point** field, enter or select a value.</span></span>

25. <span data-ttu-id="0757a-148">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="0757a-148">Close the page.</span></span>

## <a name="create-an-eligibility-rule-for-the-fixed-compensation-plan"></a><span data-ttu-id="0757a-149">Crear una regla de elegibilidad para el plan de compensación fija</span><span class="sxs-lookup"><span data-stu-id="0757a-149">Create an eligibility rule for the fixed compensation plan</span></span>

<span data-ttu-id="0757a-150">El nuevo plan de compensación fija no se puede asignar a un empleado hasta que se hayan definido las reglas de idoneidad para el plan.</span><span class="sxs-lookup"><span data-stu-id="0757a-150">You can't assign a fixed compensation plan to an employee until you define eligibility rules for the plan.</span></span>  

1. <span data-ttu-id="0757a-151">Seleccione **Reglas de idoneidad**.</span><span class="sxs-lookup"><span data-stu-id="0757a-151">Select **Eligibility rules**.</span></span>

2. <span data-ttu-id="0757a-152">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="0757a-152">Select **New**.</span></span>

3. <span data-ttu-id="0757a-153">En el campo **Elegibilidad**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="0757a-153">In the **Eligibility** field, enter a value.</span></span>

4. <span data-ttu-id="0757a-154">En el campo **Descripción**, especifique un valor.</span><span class="sxs-lookup"><span data-stu-id="0757a-154">In the **Description** field, enter a value.</span></span>

5. <span data-ttu-id="0757a-155">En el campo **Fecha de vigencia**, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="0757a-155">In the **Effective date** field, enter a date.</span></span> <span data-ttu-id="0757a-156">Las reglas de idoneidad se utilizan para los planes de compensación fijos y variables.</span><span class="sxs-lookup"><span data-stu-id="0757a-156">Both fixed and variable compensation plans use eligibility rules.</span></span> <span data-ttu-id="0757a-157">En el campo **Tipo**, seleccione el tipo de plan.</span><span class="sxs-lookup"><span data-stu-id="0757a-157">In the **Type** field, select the type of plan.</span></span>

6. <span data-ttu-id="0757a-158">En el campo **Plan**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="0757a-158">In the **Plan** field, enter or select a value.</span></span> <span data-ttu-id="0757a-159">Seleccione los criterios que un empleado debe cumplir para ser idóneo para el plan de compensación.</span><span class="sxs-lookup"><span data-stu-id="0757a-159">Select the criteria an employee must meet in order to be eligible for the compensation plan.</span></span> <span data-ttu-id="0757a-160">Los criterios pueden incluir:</span><span class="sxs-lookup"><span data-stu-id="0757a-160">Criteria can include:</span></span>

    - <span data-ttu-id="0757a-161">**Departamento**</span><span class="sxs-lookup"><span data-stu-id="0757a-161">**Department**</span></span>
    - <span data-ttu-id="0757a-162">**Sindicato**</span><span class="sxs-lookup"><span data-stu-id="0757a-162">**Labor union**</span></span>
    - <span data-ttu-id="0757a-163">**Ubicación** (**Región de compensación**)</span><span class="sxs-lookup"><span data-stu-id="0757a-163">**Location** (**Compensation region**)</span></span>
    - <span data-ttu-id="0757a-164">**Trabajo**</span><span class="sxs-lookup"><span data-stu-id="0757a-164">**Job**</span></span>
    - <span data-ttu-id="0757a-165">**Función**</span><span class="sxs-lookup"><span data-stu-id="0757a-165">**Function**</span></span>
    - <span data-ttu-id="0757a-166">**Tipo de trabajo**</span><span class="sxs-lookup"><span data-stu-id="0757a-166">**Job type**</span></span>
    - <span data-ttu-id="0757a-167">**Nivel de compensación**</span><span class="sxs-lookup"><span data-stu-id="0757a-167">**Compensation level**</span></span>
    
    <span data-ttu-id="0757a-168">El empleado debe cumplir todos los criterios especificados para ser idóneo para el plan de compensación.</span><span class="sxs-lookup"><span data-stu-id="0757a-168">The employee must meet all specified criteria to be eligible for the compensation plan.</span></span> <span data-ttu-id="0757a-169">Si no especifica ningún criterio, todos los empleados son idóneos para el plan de compensación.</span><span class="sxs-lookup"><span data-stu-id="0757a-169">If you don't specify any criteria, all employees are eligible for the compensation plan.</span></span> <span data-ttu-id="0757a-170">Si un empleado no cumple los criterios especificados en la regla de idoneidad o una regla de idoneidad no se ha especificado para un plan de compensación, el plan de compensación no aparecerá en las búsquedas cuando cree un registro de compensación fija para un empleado.</span><span class="sxs-lookup"><span data-stu-id="0757a-170">If an employee doesn't meet the criteria specified in the eligibility rule, or an eligibility rule has not been specified for a compensation plan, the compensation plan won't appear in the lookup when you create a fixed compensation record for an employee.</span></span>

7. <span data-ttu-id="0757a-171">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="0757a-171">Close the page.</span></span>

8. <span data-ttu-id="0757a-172">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="0757a-172">Close the page.</span></span>

