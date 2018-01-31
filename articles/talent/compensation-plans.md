---
title: "Planes de compensación"
description: "Los directores de compensación y de prestaciones pueden usar la Administración de compensaciones para mantener y procesar los planes de compensación variable y fija para los empleados de la organización."
author: kherr75
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: HcmCompensationLevel, HRCCompGrid, HRMCompFixedAction, HRMCompFixedBudget, HRMCompFixedPlanTable
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations, Talent
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: ceea24519d641c676521771cee274feb64ca7783
ms.openlocfilehash: 4a25daf94499d12d720a494f3895726f5e7ebcdb
ms.contentlocale: es-es
ms.lasthandoff: 01/31/2018

---

# <a name="compensation-plans"></a><span data-ttu-id="fcaaa-103">Planes de compensación</span><span class="sxs-lookup"><span data-stu-id="fcaaa-103">Compensation plans</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="fcaaa-104">Los directores de compensación y de prestaciones pueden usar la Administración de compensaciones para mantener y procesar los planes de compensación variable y fija para los empleados de la organización.</span><span class="sxs-lookup"><span data-stu-id="fcaaa-104">Compensation and Benefits Managers can use Compensation management to maintain and process fixed and variable compensation plans for the organization's employees.</span></span>

### <a name="introduction"></a><span data-ttu-id="fcaaa-105">Introducción</span><span class="sxs-lookup"><span data-stu-id="fcaaa-105">Introduction</span></span>

<span data-ttu-id="fcaaa-106">La gestión de compensaciones se usa para controlar la entrega de salarios base y primas.</span><span class="sxs-lookup"><span data-stu-id="fcaaa-106">Compensation management is used to control the delivery of base pay and awards.</span></span> <span data-ttu-id="fcaaa-107">El sueldo base fijo de un empleado y los aumentos por méritos se controlan mediante planes de compensación fijos.</span><span class="sxs-lookup"><span data-stu-id="fcaaa-107">An employee's fixed base pay and merit increases are controlled through fixed compensation plans.</span></span> <span data-ttu-id="fcaaa-108">El pago de incentivos, como los pagos de bonificación, las primas por rendimiento, las acciones y las concesiones, así como también las primas ocasionales, se controlan a través de planes de compensación variable.</span><span class="sxs-lookup"><span data-stu-id="fcaaa-108">The payment of incentive pay, such as bonus payments, performance awards, stock options, and grants, and also one-time awards, are controlled through variable compensation plans.</span></span> 

<span data-ttu-id="fcaaa-109">Los empleados pueden estar inscritos a uno o más planes de ambos tipos.</span><span class="sxs-lookup"><span data-stu-id="fcaaa-109">Employees can be enrolled in one or more plans of both types.</span></span> <span data-ttu-id="fcaaa-110">Un empleado debe cumplir los requisitos siguientes para que se pueda aplicar para la inscripción a un plan de compensación:</span><span class="sxs-lookup"><span data-stu-id="fcaaa-110">An employee must meet the following requirements in order to be eligible for enrollment in a compensation plan:</span></span>
-   <span data-ttu-id="fcaaa-111">El empleado debe tener una asignación de puesto activa.</span><span class="sxs-lookup"><span data-stu-id="fcaaa-111">The employee must have an active position assignment.</span></span>
-   <span data-ttu-id="fcaaa-112">El empleado debe cumplir los criterios definidos por las reglas de elegibilidad para un plan de compensación.</span><span class="sxs-lookup"><span data-stu-id="fcaaa-112">The employee must meet the criteria that are defined by eligibility rules for a compensation plan.</span></span>

## <a name="compensation-setup"></a><span data-ttu-id="fcaaa-113">Configuración de la compensación</span><span class="sxs-lookup"><span data-stu-id="fcaaa-113">Compensation setup</span></span>
<span data-ttu-id="fcaaa-114">En la tabla siguiente se muestran los componentes del proceso de compensación que pueden integrar la configuración de los planes de compensación de la empresa.</span><span class="sxs-lookup"><span data-stu-id="fcaaa-114">The following table lists components of the compensation process that can be integral in setting up your company's compensation plans.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="fcaaa-115">Componente</span><span class="sxs-lookup"><span data-stu-id="fcaaa-115">Component</span></span></th>
<th><span data-ttu-id="fcaaa-116">Más información...</span><span class="sxs-lookup"><span data-stu-id="fcaaa-116">More information…</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="fcaaa-117">Acciones de compensación fija</span><span class="sxs-lookup"><span data-stu-id="fcaaa-117">Fixed compensation actions</span></span></td>
<td><span data-ttu-id="fcaaa-118">Las acciones de compensación fija cumplen dos propósitos:</span><span class="sxs-lookup"><span data-stu-id="fcaaa-118">Fixed compensation actions accomplish two purposes:</span></span>
<ul>
<li><span data-ttu-id="fcaaa-119">Las acciones pueden especificar el tipo de información que se debe registrar cuando la compensación del empleado cambia.</span><span class="sxs-lookup"><span data-stu-id="fcaaa-119">Actions can specify the kind of information that must be recorded when an employee’s compensation changes.</span></span> <span data-ttu-id="fcaaa-120">Por ejemplo, se puede requerir que el motivo de un cambio, como una promoción o un descenso, se registre.</span><span class="sxs-lookup"><span data-stu-id="fcaaa-120">For example, you can require that the reason a change, such as a promotion or a demotion be recorded.</span></span></li>
<li><span data-ttu-id="fcaaa-121">Las acciones garantizan que un cálculo se aplique a un proceso de evento cuando se calculan los planes de compensación fija.</span><span class="sxs-lookup"><span data-stu-id="fcaaa-121">Actions can ensure that a calculation is applied when fixed compensation plans are processed.</span></span>  <span data-ttu-id="fcaaa-122">Por ejemplo, las acciones del tipo Recursos propios compararán el sueldo de los empleados con el punto de referencia mínimo para el nivel en el empleado y garantiza que el empleado reciba al menos el sueldo mínimo.</span><span class="sxs-lookup"><span data-stu-id="fcaaa-122">For example, actions of type Equity will compare the employees pay to the minimum reference point for the level on the employee's and ensure the employee is getting paid at least the minimum.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="fcaaa-123">Niveles</span><span class="sxs-lookup"><span data-stu-id="fcaaa-123">Levels</span></span></td>
<td><span data-ttu-id="fcaaa-124">Los niveles están asociados con trabajos y con los puestos relacionados con esos trabajos.</span><span class="sxs-lookup"><span data-stu-id="fcaaa-124">Levels are associated with jobs and any positions that are related to a job reference.</span></span> <span data-ttu-id="fcaaa-125">Puede crear niveles diferenciados para los tres tipos de planes de compensación: Categoría, Grupo y Paso.</span><span class="sxs-lookup"><span data-stu-id="fcaaa-125">You can create discrete levels for the three types of compensation plans: Grade, Band, and Step.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="fcaaa-126">Matriz del intervalo de aprovechamiento</span><span class="sxs-lookup"><span data-stu-id="fcaaa-126">Range utilization matrix</span></span></td>
<td><span data-ttu-id="fcaaa-127">Una matriz de uso de intervalos le ayudará en la transición de los empleados al punto de control de sus trabajos.</span><span class="sxs-lookup"><span data-stu-id="fcaaa-127">A range utilization matrix helps you transition employees to the control point for their jobs.</span></span> <span data-ttu-id="fcaaa-128">También se puede aplicar el uso de intervalos al control de la equidad del índice salarial en la empresa, sin tener en cuenta el rendimiento individual de un empleado o el rendimiento general de la empresa.</span><span class="sxs-lookup"><span data-stu-id="fcaaa-128">You can also use range utilization to control pay rate equity in the company without regard to an individual employee's performance or the overall performance of the company.</span></span> <span data-ttu-id="fcaaa-129">Por ejemplo, los empleados con menores pagas en un intervalo obtienen porcentajes de aumento más altos que los empleados que perciben mejores pagas en el intervalo.</span><span class="sxs-lookup"><span data-stu-id="fcaaa-129">For example, employees who are paid lower in their range get higher percentage increases than employees who are paid higher in the range.</span></span> <span data-ttu-id="fcaaa-130">De esta manera, quedan sistemáticamente anuladas las diferencias entre recursos propios.</span><span class="sxs-lookup"><span data-stu-id="fcaaa-130">In this manner, you can systematically offset equity differences.</span></span> <span data-ttu-id="fcaaa-131">El uso de intervalos se calcula como sigue: (Índice salarial fijo - mínimo del intervalo) (÷ máximo del intervalo - mínimo del intervalo).</span><span class="sxs-lookup"><span data-stu-id="fcaaa-131">The range utilization is calculated as follows: (Fixed Pay Rate - Range Minimum) ÷ (Range Maximum - Range Minimum).</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="fcaaa-132">Parámetros de configuración de puntos de referencia</span><span class="sxs-lookup"><span data-stu-id="fcaaa-132">Reference point setups</span></span></td>
<td><span data-ttu-id="fcaaa-133">Una configuración de un punto de referencia incluye un conjunto de puntos de referencia que representan los intervalos de una matriz.</span><span class="sxs-lookup"><span data-stu-id="fcaaa-133">A reference point setup includes a set of reference points that represent ranges in a matrix.</span></span> <span data-ttu-id="fcaaa-134">Cada intervalo puede estar asociado con un índice salarial.</span><span class="sxs-lookup"><span data-stu-id="fcaaa-134">Each range can be associated with a pay rate.</span></span> <span data-ttu-id="fcaaa-135">Por ejemplo, los planes de clasificación tendrán a menudo puntos de referencia Mínimo, Punto medio y Máximo.</span><span class="sxs-lookup"><span data-stu-id="fcaaa-135">For example, grade plans will often have reference points of Minimum, Midpoint, and Maximum.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="fcaaa-136">Matriz de compensación</span><span class="sxs-lookup"><span data-stu-id="fcaaa-136">Compensation matrix</span></span></td>
<td><span data-ttu-id="fcaaa-137">Una matriz de compensación es el conjunto de puntos de referencia y por los niveles que se usan para crear una estructura de compensaciones.</span><span class="sxs-lookup"><span data-stu-id="fcaaa-137">A compensation matrix is the set of reference points and levels that you use to create a compensation structure.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="fcaaa-138">Estructura de compensación</span><span class="sxs-lookup"><span data-stu-id="fcaaa-138">Compensation structure</span></span></td>
<td><span data-ttu-id="fcaaa-139">Una estructura de compensaciones es una matriz de compensaciones que incluye índices salariales asociados con puntos de referencia en cada nivel.</span><span class="sxs-lookup"><span data-stu-id="fcaaa-139">A compensation structure is a compensation matrix that has pay rates associated with the reference points for each level.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="fcaaa-140">Regla de idoneidad</span><span class="sxs-lookup"><span data-stu-id="fcaaa-140">Eligibility rules</span></span></td>
<td><span data-ttu-id="fcaaa-141">Se usan las reglas de elegibilidad para identificar a los empleados en trabajos específicos, funciones de trabajo, tipos de trabajo, departamentos, sindicatos o regiones de compensación que quedan cubiertos por planes de compensación específicos.</span><span class="sxs-lookup"><span data-stu-id="fcaaa-141">Eligibility rules are used to identify employees in specific jobs, job functions, job types, departments, labor unions, or compensation regions that are covered by specific compensation plans.</span></span> <span data-ttu-id="fcaaa-142">Debe crear reglas de idoneidad para los planes de compensación fija y variables para inscribir a empleados en el plan.</span><span class="sxs-lookup"><span data-stu-id="fcaaa-142">You must create eligibility rules for both variable and fixed compensation plans in order to enroll employees in the plan.</span></span> <span data-ttu-id="fcaaa-143">Después de especificar las reglas de idoneidad para un plan de compensación, puede definir los niveles que se deben aplicar a los trabajos que éste va a cubrir.</span><span class="sxs-lookup"><span data-stu-id="fcaaa-143">After eligibility rules are specified for a compensation plan, you can define the levels that should apply to the jobs that are covered by the plan.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="fcaaa-144">Frecuencias de pago</span><span class="sxs-lookup"><span data-stu-id="fcaaa-144">Pay frequencies</span></span></td>
<td><span data-ttu-id="fcaaa-145">Las frecuencias de pago se usan para definir el período de tiempo para el cual se especifica la compensación.</span><span class="sxs-lookup"><span data-stu-id="fcaaa-145">Pay frequencies are used to define the time period for which the compensation is specified.</span></span>  <span data-ttu-id="fcaaa-146">Por ejemplo, la frecuencia de pago ayuda a entender si el importe de compensación se especifica como sueldo anual frente a tasa de pago por hora.</span><span class="sxs-lookup"><span data-stu-id="fcaaa-146">For example, the pay frequency helps you understand if the compensation amount is specified as an annual salary versus an hourly pay rate.</span></span> <span data-ttu-id="fcaaa-147">Las frecuencias de pago se usan también para configurar factores de conversión para convertir importes de compensación de frecuencia mensual, semanal, quincenal y por hora a una frecuencia de pago anual.</span><span class="sxs-lookup"><span data-stu-id="fcaaa-147">Pay frequencies are also used to set up conversion factors to convert compensation amounts from monthly, weekly, biweekly and hourly pay frequencies to an annual pay frequency.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="fcaaa-148">Regiones de compensación</span><span class="sxs-lookup"><span data-stu-id="fcaaa-148">Compensation regions</span></span></td>
<td><span data-ttu-id="fcaaa-149">Las regiones de compensación sirven para especificar la compensación del empleado en función de la ubicación de su área de trabajo.</span><span class="sxs-lookup"><span data-stu-id="fcaaa-149">Compensation regions are used to specify employee compensation based on the location of the workplace.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="fcaaa-150">Punto de control</span><span class="sxs-lookup"><span data-stu-id="fcaaa-150">Control point</span></span></td>
<td><span data-ttu-id="fcaaa-151">El punto de control define qué considerar el índice salarial ideal para todos los empleados de un nivel de compensación.</span><span class="sxs-lookup"><span data-stu-id="fcaaa-151">The control point defines what you consider to be the ideal pay rate for all employees at a compensation level.</span></span> <span data-ttu-id="fcaaa-152">Para estructuras de plan medio, los puntos de control suelen ser el punto medio de los intervalos.</span><span class="sxs-lookup"><span data-stu-id="fcaaa-152">For grade plan structures, control points are typically the midpoint of the ranges.</span></span> <span data-ttu-id="fcaaa-153">Las estructuras de la ficha desplegable raramente usan puntos de control.</span><span class="sxs-lookup"><span data-stu-id="fcaaa-153">Band structures rarely use control points.</span></span> <span data-ttu-id="fcaaa-154">Puede especificar el punto de control de un plan de compensación fija en el formulario Planes de compensación fija.</span><span class="sxs-lookup"><span data-stu-id="fcaaa-154">You can specify the control point for a fixed compensation plan in the Fixed compensation plans form.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="fcaaa-155">Funciones de trabajo</span><span class="sxs-lookup"><span data-stu-id="fcaaa-155">Job functions</span></span></td>
<td><span data-ttu-id="fcaaa-156">Las funciones de trabajo se usan para clasificar y filtrar planes de compensación para trabajos específicos.</span><span class="sxs-lookup"><span data-stu-id="fcaaa-156">Job functions are used to classify and filter compensation plans to specific jobs.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="fcaaa-157">Tipos de trabajo</span><span class="sxs-lookup"><span data-stu-id="fcaaa-157">Job types</span></span></td>
<td><span data-ttu-id="fcaaa-158">Los tipos de trabajo se usan para clasificar y filtrar planes de compensación para trabajos específicos.</span><span class="sxs-lookup"><span data-stu-id="fcaaa-158">Job types are used to classify and filter compensation plans to specific jobs.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="fcaaa-159">Tipos de compensación variable</span><span class="sxs-lookup"><span data-stu-id="fcaaa-159">Variable compensation types</span></span></td>
<td><span data-ttu-id="fcaaa-160">Los tipos de compensación variable, como una bonificación en acciones o en efectivo, se configuran en los planes de compensación variable.</span><span class="sxs-lookup"><span data-stu-id="fcaaa-160">Variable compensation types, such as stock awards or cash award bonuses, are set up in variable compensation plans.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="fcaaa-161">Cuadrículas de compensación</span><span class="sxs-lookup"><span data-stu-id="fcaaa-161">Compensation grids</span></span></td>
<td><span data-ttu-id="fcaaa-162">Las cuadrículas de compensación contienen la estructura de compensación.</span><span class="sxs-lookup"><span data-stu-id="fcaaa-162">Compensation grids contain the compensation structure.</span></span>  <span data-ttu-id="fcaaa-163">Las cuadrículas de compensación las pueden usar uno o varios planes de compensación.</span><span class="sxs-lookup"><span data-stu-id="fcaaa-163">Compensation grids can be used by one or more compensation plans.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="fcaaa-164">Planes de rendimiento</span><span class="sxs-lookup"><span data-stu-id="fcaaa-164">Performance plans</span></span></td>
<td><span data-ttu-id="fcaaa-165">Los planes de rendimiento sirven para asociar el rendimiento a una matriz de asignación, de modo que pueda usarse el plan en una estrategia de pago de salario variable por rendimiento.</span><span class="sxs-lookup"><span data-stu-id="fcaaa-165">Performance plans are used to associate performance with an allocation matrix, so that you can use the plan in a pay-for-performance strategy.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="fcaaa-166">Evaluación del rendimiento</span><span class="sxs-lookup"><span data-stu-id="fcaaa-166">Performance ratings</span></span></td>
<td><span data-ttu-id="fcaaa-167">Las evaluaciones del rendimiento se usan en los planes de rendimiento para determinar el importe de una prima por méritos o de una prima por rendimiento.</span><span class="sxs-lookup"><span data-stu-id="fcaaa-167">Performance ratings are used in performance plans to determine the amount of a merit award or performance award.</span></span></td>
</tr>
</tbody>
</table>

## <a name="process-events"></a><span data-ttu-id="fcaaa-168">Procesar eventos</span><span class="sxs-lookup"><span data-stu-id="fcaaa-168">Process events</span></span>
<span data-ttu-id="fcaaa-169">Los eventos de proceso se utilizan para calcular información de compensación para un período específico para todos los empleados inscritos en uno o varios planes de compensación fija o variable.</span><span class="sxs-lookup"><span data-stu-id="fcaaa-169">A process event calculates compensation information for a specific period for all employees who are enrolled in one or more fixed or variable compensation plans.</span></span> <span data-ttu-id="fcaaa-170">Puede ejecutar un evento de proceso repetidamente, por ejemplo, para probar o actualizar los resultados de compensación calculados.</span><span class="sxs-lookup"><span data-stu-id="fcaaa-170">You can run a process event repeatedly to test or update calculated compensation results.</span></span>

<a name="compensation-events"></a><span data-ttu-id="fcaaa-171">Eventos de compensación</span><span class="sxs-lookup"><span data-stu-id="fcaaa-171">Compensation events</span></span>
-------------------

<span data-ttu-id="fcaaa-172">Cada vez que se ejecuta un evento de proceso, se crea un evento de compensación.</span><span class="sxs-lookup"><span data-stu-id="fcaaa-172">Each time a process event is run, a compensation event is created.</span></span>  <span data-ttu-id="fcaaa-173">Los eventos de compensación contienen los resultados del proceso de compensación para cada empleado incluido en ese evento de proceso.</span><span class="sxs-lookup"><span data-stu-id="fcaaa-173">Compensation events contain the results of the compensation process for each employee included in that process event.</span></span>  <span data-ttu-id="fcaaa-174">Cuando los cálculos son correctos, puede cargar el evento de compensación para actualizar los registros de compensación para los empleados afectados por el evento de procesos.</span><span class="sxs-lookup"><span data-stu-id="fcaaa-174">When the calculations are correct, you can load the compensation event to update the compensation records for the employees who are affected by the process event.</span></span>

## <a name="recommendations"></a><span data-ttu-id="fcaaa-175">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="fcaaa-175">Recommendations</span></span>
<span data-ttu-id="fcaaa-176">Después de ejecutar un evento de proceso, puede recomendar ajustes en la prima o en el aumento por méritos de un empleado, en función de las directrices calculadas a partir del evento de proceso.</span><span class="sxs-lookup"><span data-stu-id="fcaaa-176">After you run a process event, you can recommend adjustments to an employee’s merit increase or award amount, based on the calculated guidelines of the process event.</span></span> <span data-ttu-id="fcaaa-177">Para aplicar las recomendaciones para los empleados, debe habilitar las recomendaciones al configurar los planes de compensación o cuando configura el evento de proceso.</span><span class="sxs-lookup"><span data-stu-id="fcaaa-177">To make recommendations for employees, you must enable recommendations when you set up compensation plans or when you set up the process event.</span></span>




