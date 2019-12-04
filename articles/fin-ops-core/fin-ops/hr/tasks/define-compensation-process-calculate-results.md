---
title: Definición del proceso de compensación y el cálculo de resultados
description: Los procesos de compensación se usan para determinar nuevas concesiones e importes de compensación para los empleados inscritos en planes de compensación variable y fija.
author: andreabichsel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HRMCompProcess, HRMCompProcessLine, HRMCompEvent, HRMCompEventEmpl
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0825c80e43baf0803552f7051dca5ee79dbe521e
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "2179887"
---
# <a name="define-compensation-process-and-calculate-results"></a><span data-ttu-id="e0881-103">Definición del proceso de compensación y el cálculo de resultados</span><span class="sxs-lookup"><span data-stu-id="e0881-103">Define compensation process and calculate results</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="e0881-104">Los procesos de compensación se usan para determinar nuevas concesiones e importes de compensación para los empleados inscritos en planes de compensación variable y fija.</span><span class="sxs-lookup"><span data-stu-id="e0881-104">Compensation processes are used to determine new compensation amounts and awards for employees enrolled in fixed and variable compensation plans.</span></span> <span data-ttu-id="e0881-105">Los procesos de compensación se pueden ejecutar varias veces para realizar análisis hipotéticos, para comprobar que todos los cambios y la configuración son correctos.</span><span class="sxs-lookup"><span data-stu-id="e0881-105">Compensation processes can be run multiple times to perform "what-if" analysis, to verify all changes and settings are correct.</span></span> <span data-ttu-id="e0881-106">Este procedimiento creará un proceso de compensación, ejecutará el proceso y verá los resultados.</span><span class="sxs-lookup"><span data-stu-id="e0881-106">This procedure will create a compensation process, run the process, and view the results.</span></span> <span data-ttu-id="e0881-107">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="e0881-107">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-a-compensation-process"></a><span data-ttu-id="e0881-108">Crear un proceso de compensación</span><span class="sxs-lookup"><span data-stu-id="e0881-108">Create a compensation process</span></span>
1. <span data-ttu-id="e0881-109">Vaya a Recursos humanos > Compensación > Proceso > Procesos de compensación.</span><span class="sxs-lookup"><span data-stu-id="e0881-109">Go to Human resources > Compensation > Process > Compensation processes.</span></span>
2. <span data-ttu-id="e0881-110">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="e0881-110">Click New.</span></span>
3. <span data-ttu-id="e0881-111">En el campo Proceso, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="e0881-111">In the Process field, type a value.</span></span>
4. <span data-ttu-id="e0881-112">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="e0881-112">In the Description field, type a value.</span></span>
5. <span data-ttu-id="e0881-113">En el campo Tipo de proceso, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="e0881-113">In the Process type field, select an option.</span></span>
    * <span data-ttu-id="e0881-114">Un ciclo especifica el período de tiempo evaluado para determinar la compensación.</span><span class="sxs-lookup"><span data-stu-id="e0881-114">A cycle specifies the time period evaluated to determine compensation.</span></span> <span data-ttu-id="e0881-115">La evaluación considera qué puestos ocuparon los empleados, qué índices de rendimiento se incluirán, el cálculo del porcentaje de tiempo que el empleado estuvo contratado durante el ciclo, etc.</span><span class="sxs-lookup"><span data-stu-id="e0881-115">The evaluation considers which positions were held by employees, which performance ratings to include, calculation of the percentage of time the employee was employed during the cycle, and more.</span></span> <span data-ttu-id="e0881-116">Un ejemplo de una fecha de inicio del ciclo podría ser el primer día del último ejercicio.</span><span class="sxs-lookup"><span data-stu-id="e0881-116">An example of a cycle start date might be the first day of the past fiscal year.</span></span>  
6. <span data-ttu-id="e0881-117">En el campo Inicio del ciclo, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="e0881-117">In the Cycle start field, enter a date.</span></span>
    * <span data-ttu-id="e0881-118">La fecha final del ciclo es importante porque es la fecha que se usa para determinar qué empleados estuvieron activos e inscritos en uno o varios planes de compensación.</span><span class="sxs-lookup"><span data-stu-id="e0881-118">The cycle end date is  important because it is the date used to determine which employees were actively employed and enrolled in one or more compensation plans.</span></span>  
7. <span data-ttu-id="e0881-119">En el campo Fin del ciclo, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="e0881-119">In the Cycle end field, enter a date.</span></span>
    * <span data-ttu-id="e0881-120">La fecha activa de la transacción es la fecha en que las nuevas cuotas de compensación deben surtir efecto.</span><span class="sxs-lookup"><span data-stu-id="e0881-120">The transaction active date is the date the new compensation rates should take effect.</span></span> <span data-ttu-id="e0881-121">Muchas empresas incluyen algunos meses entre su final de un ciclo y el tiempo en que las nuevas cuotas de compensación entran en vigor.</span><span class="sxs-lookup"><span data-stu-id="e0881-121">Many companies include a few months between their end of a cycle and the time the new compensation rates go into effect.</span></span> <span data-ttu-id="e0881-122">El tiempo adicional se usa para procesar y revisar la nueva compensación.</span><span class="sxs-lookup"><span data-stu-id="e0881-122">The additional time is used for processing and reviewing the new compensation.</span></span>  
8. <span data-ttu-id="e0881-123">En el campo Fecha de activación de transacción, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="e0881-123">In the Transaction active date field, enter a date.</span></span>
    * <span data-ttu-id="e0881-124">La fecha de referencia se usa para los planes de compensación variable que determinan el importe de la prima de un empleado basado en su índice de compensación en este momento.</span><span class="sxs-lookup"><span data-stu-id="e0881-124">The point-in-time date is used for variable compensation plans that determine an employee's award amount based on their compensation rate at this point in time.</span></span>  
    * <span data-ttu-id="e0881-125">La fecha de contratación prorrateada fija se usa con los planes de compensación fija con una regla de contratación de porcentaje.</span><span class="sxs-lookup"><span data-stu-id="e0881-125">The fixed pay pro rated hire date is used with fixed compensation plans with a hire rule of Percent.</span></span>  <span data-ttu-id="e0881-126">Los empleados contratados entre el inicio del ciclo y la fecha de contratación prorrateada fija recibirán el 100 % de su incremento de compensación calculado, en lugar del porcentaje prorrateado.</span><span class="sxs-lookup"><span data-stu-id="e0881-126">Employees who are hired between the cycle start and the fixed pay pro rated hire date will receive 100% of their calculated compensation increase, instead of pro-rated percentage.</span></span>  
9. <span data-ttu-id="e0881-127">En el campo Fecha de contratación prorrateada fija, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="e0881-127">In the Fixed pay pro rated hire date field, enter a date.</span></span>
    * <span data-ttu-id="e0881-128">El plazo de revisión es la fecha límite en la que todos los resultados de procesos deben revisarse para que se puedan cargar en el registro de compensación de un empleado antes de la fecha activa de la transacción.</span><span class="sxs-lookup"><span data-stu-id="e0881-128">The review deadline is the date by which all process results should be reviewed so that they can be loaded into an employee's compensation record before the transaction active date.</span></span> <span data-ttu-id="e0881-129">Este campo es únicamente informativo.</span><span class="sxs-lookup"><span data-stu-id="e0881-129">This field is informational only.</span></span>  
10. <span data-ttu-id="e0881-130">En el campo Revisar fecha límite, escriba una fecha.</span><span class="sxs-lookup"><span data-stu-id="e0881-130">In the Review deadline field, enter a date.</span></span>
11. <span data-ttu-id="e0881-131">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="e0881-131">Click Save.</span></span>

## <a name="setup-the-compensation-plans-and-actions-for-a-compensation-process"></a><span data-ttu-id="e0881-132">Configurar las acciones y los planes de compensación para un proceso de compensación</span><span class="sxs-lookup"><span data-stu-id="e0881-132">Setup the compensation plans and actions for a compensation process</span></span>
1. <span data-ttu-id="e0881-133">Haga clic en Configurar.</span><span class="sxs-lookup"><span data-stu-id="e0881-133">Click Setup.</span></span>
    * <span data-ttu-id="e0881-134">La página Configuración se usa para seleccionar qué planes procesar como parte de este proceso de compensación, además de las acciones que se deben realizar con cada plan.</span><span class="sxs-lookup"><span data-stu-id="e0881-134">The Setup page is used to select which plans to process as part of this compensation process, as well as which actions should be taken against each plan.</span></span>  
2. <span data-ttu-id="e0881-135">En el campo Plan, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="e0881-135">In the Plan field, enter or select a value.</span></span>
3. <span data-ttu-id="e0881-136">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="e0881-136">Click Save.</span></span>
4. <span data-ttu-id="e0881-137">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="e0881-137">Click Add.</span></span>
5. <span data-ttu-id="e0881-138">En el campo Acción, seleccione un tipo de acción Recursos propios.</span><span class="sxs-lookup"><span data-stu-id="e0881-138">In the Action field, select an Equity type of action.</span></span>
6. <span data-ttu-id="e0881-139">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="e0881-139">Click Add.</span></span>
7. <span data-ttu-id="e0881-140">En el campo Acción, seleccione un tipo de acción Méritos.</span><span class="sxs-lookup"><span data-stu-id="e0881-140">In the Action field, select a Merit type of action.</span></span>
    * <span data-ttu-id="e0881-141">Las acciones de compensación se pueden “encadenar” de manera conjunta con el campo Utilizar resultado anterior para indicar si la acción seleccionada debe usar el pago base de los empleados o el resultado de la acción anterior como punto de partida para el cálculo de esta acción.</span><span class="sxs-lookup"><span data-stu-id="e0881-141">Compensation actions can be "chained" together using the Use previous result field to indicate whether the selected action should use the employees base pay or the result of the previous action as the starting point for this action's calculation.</span></span>  
8. <span data-ttu-id="e0881-142">Seleccione Sí en el campo Utilizar resultado anterior.</span><span class="sxs-lookup"><span data-stu-id="e0881-142">Select Yes in the Use previous result field.</span></span>
9. <span data-ttu-id="e0881-143">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="e0881-143">Click Add.</span></span>
10. <span data-ttu-id="e0881-144">En el campo Acción, seleccione un tipo de acción General.</span><span class="sxs-lookup"><span data-stu-id="e0881-144">In the Action field, select a General type of Action.</span></span>
    * <span data-ttu-id="e0881-145">Distintos tipos de acción de compensación habilitan diferentes campos.</span><span class="sxs-lookup"><span data-stu-id="e0881-145">Different compensation action types enable different fields.</span></span> <span data-ttu-id="e0881-146">Para un tipo de acción de compensación general, se puede especificar un importe o un porcentaje de incremento.</span><span class="sxs-lookup"><span data-stu-id="e0881-146">For a General compensation action type, an increase percent or increase amount can be specified.</span></span>  
11. <span data-ttu-id="e0881-147">Seleccione la opción Seleccionar importe de incremento.</span><span class="sxs-lookup"><span data-stu-id="e0881-147">Select the Select increase amount option.</span></span>
12. <span data-ttu-id="e0881-148">En el campo Importe de incremento, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="e0881-148">In the Increase amount field, enter a number.</span></span>
13. <span data-ttu-id="e0881-149">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="e0881-149">Click Add.</span></span>
14. <span data-ttu-id="e0881-150">En el campo Acción, seleccione un tipo de acción Promoción.</span><span class="sxs-lookup"><span data-stu-id="e0881-150">In the Action field, select a Promotion type of Action.</span></span>
    * <span data-ttu-id="e0881-151">Los tipos de acción Promoción y Otro cambio de nivel permiten a los usuarios realizar ajustes manuales a la compensación del empleado.</span><span class="sxs-lookup"><span data-stu-id="e0881-151">Promotion and Other level change action types enable users to make manual adjustments to employee compensation.</span></span> <span data-ttu-id="e0881-152">Se pueden habilitar recomendaciones para estos tipos de acción, además de otros tipos de acción para que pueda especificar un nuevo valor de compensación recomendado para un empleado.</span><span class="sxs-lookup"><span data-stu-id="e0881-152">Recommendations can be enabled for these action types, as well as other action types to enable you to enter a new recommended compensation value for an employee.</span></span>  
15. <span data-ttu-id="e0881-153">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="e0881-153">Click Add.</span></span>
16. <span data-ttu-id="e0881-154">En el campo Tipo, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="e0881-154">In the Type field, select an option.</span></span>
    * <span data-ttu-id="e0881-155">Los planes de compensación fijos y variables se pueden ejecutar en el mismo proceso de compensación.</span><span class="sxs-lookup"><span data-stu-id="e0881-155">Fixed and variable compensation plans can be run in the same compensation process.</span></span>  
17. <span data-ttu-id="e0881-156">En el campo Plan, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="e0881-156">In the Plan field, enter or select a value.</span></span>
    * <span data-ttu-id="e0881-157">Use la casilla Habilitar salario variable por rendimiento para determinar si los importes fijos y de compensación variable se deben ajustar en función de la evaluación del rendimiento del empleado.</span><span class="sxs-lookup"><span data-stu-id="e0881-157">Use the Enable pay for performance check box to determined whether fixed and variable compensation amounts should be adjusted based on the employee's performance rating.</span></span>  
    * <span data-ttu-id="e0881-158">El endeudamiento se puede anular en los planes de compensación variable.</span><span class="sxs-lookup"><span data-stu-id="e0881-158">Leverage can be overridden on variable compensation plans.</span></span>  
18. <span data-ttu-id="e0881-159">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="e0881-159">Click Save.</span></span>
19. <span data-ttu-id="e0881-160">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="e0881-160">Click Add.</span></span>
20. <span data-ttu-id="e0881-161">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="e0881-161">Close the page.</span></span>

## <a name="run-the-compensation-process"></a><span data-ttu-id="e0881-162">Ejecutar el proceso de compensación</span><span class="sxs-lookup"><span data-stu-id="e0881-162">Run the compensation process</span></span>
1. <span data-ttu-id="e0881-163">Haga clic en Ejecutar proceso.</span><span class="sxs-lookup"><span data-stu-id="e0881-163">Click Run process.</span></span>
    * <span data-ttu-id="e0881-164">El control Mostrar resultados de procesamiento le permite ver los mensajes de procesamiento para el proceso de compensación completo cuando ha terminado el procesamiento.</span><span class="sxs-lookup"><span data-stu-id="e0881-164">The Show processing results control lets you view processing messages for the complete compensation process when processing has finished.</span></span>  
2. <span data-ttu-id="e0881-165">Seleccione Sí en el campo Mostrar resultados de procesamiento.</span><span class="sxs-lookup"><span data-stu-id="e0881-165">Select Yes in the Show processing results field.</span></span>
3. <span data-ttu-id="e0881-166">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="e0881-166">Click OK.</span></span>

## <a name="view-the-results"></a><span data-ttu-id="e0881-167">Ver los resultados</span><span class="sxs-lookup"><span data-stu-id="e0881-167">View the results</span></span>
1. <span data-ttu-id="e0881-168">Haga clic en Procesar resultados.</span><span class="sxs-lookup"><span data-stu-id="e0881-168">Click Process results.</span></span>
2. <span data-ttu-id="e0881-169">Haga clic en Resultados de empleados.</span><span class="sxs-lookup"><span data-stu-id="e0881-169">Click Employee results.</span></span>
3. <span data-ttu-id="e0881-170">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="e0881-170">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="e0881-171">Expanda la sección Compensación fija.</span><span class="sxs-lookup"><span data-stu-id="e0881-171">Expand the Fixed compensation section.</span></span>
    * <span data-ttu-id="e0881-172">Expanda las fichas desplegables para ver los resultados del proceso.</span><span class="sxs-lookup"><span data-stu-id="e0881-172">Expand the FastTabs to view the results of the process.</span></span> <span data-ttu-id="e0881-173">Si Habilitar recomendaciones se marcó para una acción de compensación, los campos Recomendación se habilitarán para esa acción.</span><span class="sxs-lookup"><span data-stu-id="e0881-173">If Enable recommendations was marked for a compensation action, the Recommendation fields will be enabled for that action.</span></span>  
5. <span data-ttu-id="e0881-174">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="e0881-174">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="e0881-175">Los resultados para un empleado único se pueden ver haciendo clic en el botón Ver resultados.</span><span class="sxs-lookup"><span data-stu-id="e0881-175">The results for a single employee can be viewed by clicking the View results button.</span></span>  
    * <span data-ttu-id="e0881-176">Puede sobrescribir el importe calculado de compensación calculado ajustando el porcentaje o el importe de incremento en los campos Recomendación.</span><span class="sxs-lookup"><span data-stu-id="e0881-176">You can overwrite the calculated compensation amount by adjusting the percent or the increase amount in the Recommendation fields.</span></span>  
6. <span data-ttu-id="e0881-177">En el campo recomendado de porcentaje, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="e0881-177">In the percent recommended field, enter a number.</span></span>
7. <span data-ttu-id="e0881-178">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="e0881-178">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="e0881-179">En el campo recomendado de porcentaje, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="e0881-179">In the percent recommended field, enter a number.</span></span>
    * <span data-ttu-id="e0881-180">Volver a calcular se puede usar para ignorar los cambios realizados al registro existente y generar un nuevo resultado de compensación para el empleado seleccionado.</span><span class="sxs-lookup"><span data-stu-id="e0881-180">Recalculate can be used to ignore any changes made to the existing record and generate a new compensation result for the selected employee.</span></span>  
    * <span data-ttu-id="e0881-181">Cuando se completen todos los cambios para un empleado, cambie el estado a Aprobado.</span><span class="sxs-lookup"><span data-stu-id="e0881-181">When all changes are complete for an employee, change the status to Approved.</span></span>  
9. <span data-ttu-id="e0881-182">Haga clic en Cambiar estado.</span><span class="sxs-lookup"><span data-stu-id="e0881-182">Click Change status.</span></span>
10. <span data-ttu-id="e0881-183">Haga clic en Aprobado.</span><span class="sxs-lookup"><span data-stu-id="e0881-183">Click Approved.</span></span>
    * <span data-ttu-id="e0881-184">Después de que se haya aprobado el registro, se puede ser cargar al registro de compensación oficial del empleado.</span><span class="sxs-lookup"><span data-stu-id="e0881-184">After the record has been approved it can be loaded to the employee's official compensation record.</span></span> <span data-ttu-id="e0881-185">La nueva compensación estará vigente a partir de la fecha de transacción establecida en el proceso de compensación.</span><span class="sxs-lookup"><span data-stu-id="e0881-185">The new compensation will be effective as of the transaction date set on the compensation process.</span></span>  
