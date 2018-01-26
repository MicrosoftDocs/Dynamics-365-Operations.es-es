---
title: Registro de ausencia en Tiempo y asistencia
description: "Este tema explica cómo administrar los registros de ausencia en Tiempo y asistencia."
author: johanhoffmann
manager: AnnBe
ms.date: 05/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: JMGParameters
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2017-09-20
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 3c43a42822f291607fbc9708dd07ebf99b9d7ec4
ms.openlocfilehash: c515351a24bc86387cd504e55cfc34bb2272553c
ms.contentlocale: es-es
ms.lasthandoff: 01/26/2018

---

# <a name="absence-registration-in-time-and-attendance"></a><span data-ttu-id="ece32-103">Registro de ausencia en Tiempo y asistencia</span><span class="sxs-lookup"><span data-stu-id="ece32-103">Absence registration in Time and attendance</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="ece32-104">Este tema describe los conceptos para ausencia y explica cómo gestionar ausencia en Tiempo y asistencia.</span><span class="sxs-lookup"><span data-stu-id="ece32-104">This topic describes the concepts for absence and explains how to handle absence in Time and attendance.</span></span>

## <a name="absence-that-is-based-on-regular-work-hours"></a><span data-ttu-id="ece32-105">Ausencia que se basa las horas de trabajo normales</span><span class="sxs-lookup"><span data-stu-id="ece32-105">Absence that is based on regular work hours</span></span>

<span data-ttu-id="ece32-106">Los trabajadores se consideran ausentes por las horas que no trabajen durante las horas de trabajo normales.</span><span class="sxs-lookup"><span data-stu-id="ece32-106">Workers are considered absent for any hours that they don't work during their regular work hours.</span></span> <span data-ttu-id="ece32-107">Las horas de trabajo normales se definen en el perfil de tiempo estándar de un trabajador.</span><span class="sxs-lookup"><span data-stu-id="ece32-107">Regular work hours are defined in a worker's standard time profile.</span></span>

<span data-ttu-id="ece32-108">Por ejemplo, un trabajador trabaja en un perfil de día que tiene hora de entrada a las 7:00 y salida a las 15:00.</span><span class="sxs-lookup"><span data-stu-id="ece32-108">For example, a worker is working on a day profile that has clock-in at 7:00 AM and clock-out at 3:00 PM.</span></span> <span data-ttu-id="ece32-109">Si el trabajador entra a trabajar a las 9:00, se considera ausentes de 7:00 a 9:00 ese día.</span><span class="sxs-lookup"><span data-stu-id="ece32-109">If the worker clocks in at 9:00 AM, he is considered absent from 7:00 AM to 9:00 AM on that day.</span></span>

<span data-ttu-id="ece32-110">En este caso, se pide a los trabajadores que especifiquen un motivo de la ausencia.</span><span class="sxs-lookup"><span data-stu-id="ece32-110">In this case, workers are prompted to enter a reason for their absence.</span></span> <span data-ttu-id="ece32-111">Pueden especificar un motivo seleccionando un código de ausencia.</span><span class="sxs-lookup"><span data-stu-id="ece32-111">They can specify a reason by selecting an absence code.</span></span>

## <a name="absence-codes"></a><span data-ttu-id="ece32-112">Códigos de ausencias</span><span class="sxs-lookup"><span data-stu-id="ece32-112">Absence codes</span></span>

<span data-ttu-id="ece32-113">Los códigos de ausencia definen los diferentes tipos de ausencia.</span><span class="sxs-lookup"><span data-stu-id="ece32-113">Absence codes define the various types of absence.</span></span> <span data-ttu-id="ece32-114">Los códigos de ausencia están definidos por la empresa.</span><span class="sxs-lookup"><span data-stu-id="ece32-114">Absence codes are defined by the company.</span></span>

<span data-ttu-id="ece32-115">Se pueden aplicar distintas reglas a códigos de ausencia.</span><span class="sxs-lookup"><span data-stu-id="ece32-115">Various rules can be applied to absence codes.</span></span> <span data-ttu-id="ece32-116">Por ejemplo, se puede configurar un código de ausencia para deducir o conceder un pago.</span><span class="sxs-lookup"><span data-stu-id="ece32-116">For example, an absence code can be configured to deduct or grant pay.</span></span>

<span data-ttu-id="ece32-117">Por ejemplo, una empresa define un código de ausencia **Tarde** que los trabajadores usan si llegan tarde y no tienen un buen motivo.</span><span class="sxs-lookup"><span data-stu-id="ece32-117">For example, a company defines a **Late** absence code that workers use if they come in late and don't have a good reason.</span></span> <span data-ttu-id="ece32-118">La empresa también define un código de ausencia **Curso interno** que los trabajadores usan para el tiempo que dedican a asistir a cursos internos.</span><span class="sxs-lookup"><span data-stu-id="ece32-118">The company also defines an **Internal course** absence code that workers use for time that they spend attending internal courses.</span></span> <span data-ttu-id="ece32-119">Estos códigos de ausencia pueden configurarse para que **Tarde** se deduzca del sueldo del trabajador pero **Curso interno** pero no se deduzca del sueldo del trabajador.</span><span class="sxs-lookup"><span data-stu-id="ece32-119">These absence codes can be set up so that **Late** deducts from a worker's pay but **Internal course** doesn't deduct from a worker's pay.</span></span>

<span data-ttu-id="ece32-120">Puede configurar códigos de ausencia automáticos.</span><span class="sxs-lookup"><span data-stu-id="ece32-120">You can set up automatic absence codes.</span></span> <span data-ttu-id="ece32-121">Estos códigos de ausencia se pueden utilizar para calcular el tiempo de un trabajador cuando no se registra ninguna ausencia.</span><span class="sxs-lookup"><span data-stu-id="ece32-121">These absence codes can be used to calculate a worker's time when no absence is registered.</span></span> <span data-ttu-id="ece32-122">El perfil de tiempo de un trabajador determina si se usa el código de ausencia para tiempo estándar o tiempo flexible.</span><span class="sxs-lookup"><span data-stu-id="ece32-122">The worker's time profile determines whether the absence code for standard time or flex time is used.</span></span>

### <a name="set-up-standard-time-and-flex-time"></a><span data-ttu-id="ece32-123">Configurar tiempo estándar y tiempo flexible</span><span class="sxs-lookup"><span data-stu-id="ece32-123">Set up standard time and flex time</span></span>

- <span data-ttu-id="ece32-124">Configure los parámetros para tiempo estándar y tiempo flexible utilizando las opciones **Insertar autom. ausencia** e **Insertar autom. horario flexible-** en la página **Parámetros de Tiempo y asistencia**.</span><span class="sxs-lookup"><span data-stu-id="ece32-124">Configure the parameters for standard time and flex time by using the **Auto insert absence** and **Auto insert Flex-** options on the **Time and attendance parameters** page.</span></span>

## <a name="absence-groups"></a><span data-ttu-id="ece32-125">Grupos de ausencias</span><span class="sxs-lookup"><span data-stu-id="ece32-125">Absence groups</span></span>

<span data-ttu-id="ece32-126">Los códigos de ausencia se agrupan en grupos de ausencia.</span><span class="sxs-lookup"><span data-stu-id="ece32-126">Absence codes are grouped into absence groups.</span></span> <span data-ttu-id="ece32-127">Puede utilizar grupos de ausencia para agrupar los códigos de ausencia con características comunes.</span><span class="sxs-lookup"><span data-stu-id="ece32-127">You use absence groups to group absence codes that have common characteristics.</span></span> <span data-ttu-id="ece32-128">Algunos ejemplos son: códigos de ausencia por una ausencia legal, o ausencia por una cita con médico, obligación de jurado o enfermedad de un hijo.</span><span class="sxs-lookup"><span data-stu-id="ece32-128">Examples include absence codes for a legal absence, or absence because of a doctor's appointment, jury duty, or a sick child.</span></span>

## <a name="planned-absence"></a><span data-ttu-id="ece32-129">Ausencia planificada</span><span class="sxs-lookup"><span data-stu-id="ece32-129">Planned absence</span></span>

<span data-ttu-id="ece32-130">Si sabe que un trabajador estará ausente durante un período, como vacaciones próximas, puede usar ausencia planificada.</span><span class="sxs-lookup"><span data-stu-id="ece32-130">If you know that a worker will be absent for a period, such as an upcoming vacation, you can use planned absence.</span></span> <span data-ttu-id="ece32-131">Establezca la ausencia planificada configurando el código de ausencia de modo que considere la ausencia planificada.</span><span class="sxs-lookup"><span data-stu-id="ece32-131">You set up planned absence by configuring the absence code so that it considers the planned absence.</span></span> <span data-ttu-id="ece32-132">Al configurar una ausencia planificada, no se solicitará un código de ausencia durante el período de ausencia cuando se calculen los registros de horas del usuario.</span><span class="sxs-lookup"><span data-stu-id="ece32-132">When you set up a planned absence, you aren't prompted for an absence code during the absence period when user time registrations are calculated.</span></span> <span data-ttu-id="ece32-133">La ausencia planificada se puede definir para un solo trabajador, o puede definir un trabajo por lotes para que actualice de forma masiva la ausencia planificada para los trabajadores.</span><span class="sxs-lookup"><span data-stu-id="ece32-133">Planned absence can be defined for a single worker, or you can define a batch job to bulk update the planned absence for workers.</span></span>

### <a name="set-up-planned-absence"></a><span data-ttu-id="ece32-134">Configurar ausencia planificada</span><span class="sxs-lookup"><span data-stu-id="ece32-134">Set up planned absence</span></span>

1. <span data-ttu-id="ece32-135">Seleccione &gt; **Recursos humanos** **Trabajadores** &gt; **Empleados** y seleccione un empleado.</span><span class="sxs-lookup"><span data-stu-id="ece32-135">Select **Human resources** &gt; **Workers** &gt; **Employees**, and select an employee.</span></span>
2. <span data-ttu-id="ece32-136">Seleccione **Tiempo** &gt; **Asignaciones de tiempo** &gt; **Registro de ausencia de tiempo**, y configure la ausencia planificada.</span><span class="sxs-lookup"><span data-stu-id="ece32-136">Select **Time** &gt; **Time assignments** &gt; **Time Absence registration**, and set up the planned absence.</span></span>

## <a name="interrupted-planned-absence"></a><span data-ttu-id="ece32-137">Ausencia planificada interrumpida</span><span class="sxs-lookup"><span data-stu-id="ece32-137">Interrupted planned absence</span></span>

<span data-ttu-id="ece32-138">Si aplica la opción **Interrumpir** cuando configura una ausencia planificada, la ausencia planificada se interrumpirá si el trabajador inicia sesión durante el período de ausencia planificada.</span><span class="sxs-lookup"><span data-stu-id="ece32-138">If you apply the **Interrupt** option when you set up a planned absence, the planned absence will be interrupted if the worker signs in during the planned absence period.</span></span> <span data-ttu-id="ece32-139">La ausencia planificada se marcará como **Interrumpida** y no tendrá efecto en los cálculos futuros.</span><span class="sxs-lookup"><span data-stu-id="ece32-139">The planned absence will be marked as **Interrupted** and won't have any effect on future calculations.</span></span>

### <a name="set-up-a-planned-absence-for-interruption"></a><span data-ttu-id="ece32-140">Configurar una ausencia planificada para interrupción</span><span class="sxs-lookup"><span data-stu-id="ece32-140">Set up a planned absence for interruption</span></span>

1. <span data-ttu-id="ece32-141">Abra la página **Registro de ausencia de tiempo** tal como se describe en el procedimiento para configurar ausencia planificada.</span><span class="sxs-lookup"><span data-stu-id="ece32-141">Open the **Time Absence registration** page as described in the procedure for setting up planned absence.</span></span>
2. <span data-ttu-id="ece32-142">Seleccione **Interrumpir**.</span><span class="sxs-lookup"><span data-stu-id="ece32-142">Select **Interrupt**.</span></span>

<span data-ttu-id="ece32-143">La opción **Interrumpir** se aplica cuando el tiempo se registra mediante el terminal de planta o el dispositivo de planta.</span><span class="sxs-lookup"><span data-stu-id="ece32-143">The **Interrupt** option applies when time is registered through the shop floor terminal or the shop floor device.</span></span> <span data-ttu-id="ece32-144">La opción no se aplica si los registros se especifican en las páginas de cálculo y aprobación, o en la página **Tarjeta de hora electrónica**.</span><span class="sxs-lookup"><span data-stu-id="ece32-144">The option doesn't apply if the registrations are entered on the calculation and approval pages, or on the **Electronic timecard** page.</span></span>

## <a name="examples-of-the-use-of-absence-in-a-flex-profile"></a><span data-ttu-id="ece32-145">Ejemplos de uso de ausencia en un perfil flexible</span><span class="sxs-lookup"><span data-stu-id="ece32-145">Examples of the use of absence in a flex profile</span></span>

<span data-ttu-id="ece32-146">Los tres ejemplos siguientes muestran cómo se calcula la ausencia en un perfil que tiene períodos de horario flexible.</span><span class="sxs-lookup"><span data-stu-id="ece32-146">The following three examples show how absence is calculated in a profile that has flex periods.</span></span>

<span data-ttu-id="ece32-147">Los ejemplos usan el perfil siguiente.</span><span class="sxs-lookup"><span data-stu-id="ece32-147">The examples use the following profile.</span></span>

| <span data-ttu-id="ece32-148">Registrar la hora de entrada</span><span class="sxs-lookup"><span data-stu-id="ece32-148">Clock-in</span></span> | <span data-ttu-id="ece32-149">Hora estándar</span><span class="sxs-lookup"><span data-stu-id="ece32-149">Standard time</span></span>    | <span data-ttu-id="ece32-150">Descanso</span><span class="sxs-lookup"><span data-stu-id="ece32-150">Break</span></span>             | <span data-ttu-id="ece32-151">Hora estándar</span><span class="sxs-lookup"><span data-stu-id="ece32-151">Standard time</span></span> | <span data-ttu-id="ece32-152">Horario flexible-</span><span class="sxs-lookup"><span data-stu-id="ece32-152">Flex-</span></span>        | <span data-ttu-id="ece32-153">Registrar la hora de salida</span><span class="sxs-lookup"><span data-stu-id="ece32-153">Clock-out</span></span> | <span data-ttu-id="ece32-154">Horario flexible+</span><span class="sxs-lookup"><span data-stu-id="ece32-154">Flex+</span></span>        |
|----------|------------------|-------------------|---------------|--------------|-----------|--------------|
| <span data-ttu-id="ece32-155">8 AM</span><span class="sxs-lookup"><span data-stu-id="ece32-155">8 AM</span></span>     | <span data-ttu-id="ece32-156">9 AM a 11:30 AM</span><span class="sxs-lookup"><span data-stu-id="ece32-156">9 AM to 11:30 AM</span></span> | <span data-ttu-id="ece32-157">11:30 AM a 12 PM</span><span class="sxs-lookup"><span data-stu-id="ece32-157">11:30 AM to 12 PM</span></span> | <span data-ttu-id="ece32-158">12 PM a 3 PM</span><span class="sxs-lookup"><span data-stu-id="ece32-158">12 PM to 3 PM</span></span> | <span data-ttu-id="ece32-159">3 PM a 4 PM</span><span class="sxs-lookup"><span data-stu-id="ece32-159">3 PM to 4 PM</span></span> | <span data-ttu-id="ece32-160">4 PM</span><span class="sxs-lookup"><span data-stu-id="ece32-160">4 PM</span></span>      | <span data-ttu-id="ece32-161">4 PM a 6 PM</span><span class="sxs-lookup"><span data-stu-id="ece32-161">4 PM to 6 PM</span></span> |

### <a name="example-1-signing-out-during-a-flex--period"></a><span data-ttu-id="ece32-162">Ejemplo 1: Cerrar sesión durante un período de horario flexible-</span><span class="sxs-lookup"><span data-stu-id="ece32-162">Example 1: Signing out during a Flex- period</span></span>

<span data-ttu-id="ece32-163">El trabajador entra a las 8:00 y sale a las 15:30.</span><span class="sxs-lookup"><span data-stu-id="ece32-163">The worker clocks in at 8:00 AM and clocks out at 3:30 PM.</span></span> <span data-ttu-id="ece32-164">En este caso, dado que el trabajador sale durante un período de horario flexible-, no se calcula ninguna ausencia, y se deduce media hora del saldo de horario flexible del trabajador.</span><span class="sxs-lookup"><span data-stu-id="ece32-164">In this case, because the worker clocks out during a Flex- period, no absence is calculated, and half an hour is deducted from the worker's flex balance.</span></span>

### <a name="example-2-signing-out-in-during-standard-time-period"></a><span data-ttu-id="ece32-165">Ejemplo 2: Cerrar sesión durante período de tiempo estándar</span><span class="sxs-lookup"><span data-stu-id="ece32-165">Example 2: Signing out in during Standard time period</span></span>

<span data-ttu-id="ece32-166">El trabajador entra a las 8:00 y sale a las 14:30.</span><span class="sxs-lookup"><span data-stu-id="ece32-166">The worker clocks in at 8:00 AM and clocks out at 2:30 PM.</span></span> <span data-ttu-id="ece32-167">En este caso, dado que el trabajador sale durante el periodo de hora estándar, la ausencia se calcula de las 14:30 a las 16, y se registra un período de ausencia de 1,5 horas.</span><span class="sxs-lookup"><span data-stu-id="ece32-167">In this case, because the worker clocks out during the Standard time period, absence is calculated from 2:30 PM to 4 PM, and an absence period of 1.5 hours is registered.</span></span> <span data-ttu-id="ece32-168">Se requiere un código de ausencia para ese período.</span><span class="sxs-lookup"><span data-stu-id="ece32-168">An absence code for that period is required.</span></span>

### <a name="example-3-signing-out-during-a-flex-period"></a><span data-ttu-id="ece32-169">Ejemplo 3: Cerrar sesión durante un período de horario flexible+</span><span class="sxs-lookup"><span data-stu-id="ece32-169">Example 3: Signing out during a Flex+ period</span></span>

<span data-ttu-id="ece32-170">El trabajador entra a las 8:00 y sale a las 16:30.</span><span class="sxs-lookup"><span data-stu-id="ece32-170">The worker clocks in at 8:00 AM and clocks out at 4:30 PM.</span></span> <span data-ttu-id="ece32-171">En este caso, dado que el trabajador sale durante un período de horario flexible+, no se calcula ninguna ausencia, y se agrega media hora al saldo de horario flexible del trabajador.</span><span class="sxs-lookup"><span data-stu-id="ece32-171">In this case, because the worker clocks out during a Flex+ period, no absence is calculated, and half an hour is added to the worker's flex balance.</span></span>

## <a name="absence-in-the-calculation-and-approval-process"></a><span data-ttu-id="ece32-172">Ausencia en el proceso de cálculo y aprobación</span><span class="sxs-lookup"><span data-stu-id="ece32-172">Absence in the calculation and approval process</span></span>

<span data-ttu-id="ece32-173">Los registros de tiempo del trabajador se deben calcular y aprobar antes de que puedan transferirse a un sistema de nóminas como elementos del sueldo.</span><span class="sxs-lookup"><span data-stu-id="ece32-173">Worker time registrations must be calculated and approved before they can be transferred to a payroll system as pay items.</span></span>

<span data-ttu-id="ece32-174">Un aprobador puede modificar los registros de tiempo de un trabajador.</span><span class="sxs-lookup"><span data-stu-id="ece32-174">An approver can change a worker's time registrations.</span></span> <span data-ttu-id="ece32-175">El aprobador puede incluso cambiar cualquier ausencia que el trabajador haya registrado.</span><span class="sxs-lookup"><span data-stu-id="ece32-175">The approver can even change any absence that the worker has registered.</span></span> <span data-ttu-id="ece32-176">Si el aprobador especifica manualmente un período de tiempo que tenga un código de ausencia, el código de ausencia para dicho período no es anulado por el código de ausencia predeterminado de los parámetros de Tiempo y asistencia.</span><span class="sxs-lookup"><span data-stu-id="ece32-176">If the approver manually enters a time period that has an absence code, the absence code for that period isn't overridden by the default absence code from the Time and attendance parameters.</span></span>

<span data-ttu-id="ece32-177">Por ejemplo, una trabajador entra a las 10 y selecciona un código de ausencia que indica que llega tarde.</span><span class="sxs-lookup"><span data-stu-id="ece32-177">For example, a worker clocks in at 10 AM and selects an absence code that indicates that she is late.</span></span> <span data-ttu-id="ece32-178">Más adelante, la trabajadora notifica a su supervisor que tenía una cita médica de 8 a 10.</span><span class="sxs-lookup"><span data-stu-id="ece32-178">Later, the worker informs her supervisor that she had a doctor's appointment from 8 AM to 10 AM.</span></span> <span data-ttu-id="ece32-179">Una cita médica no debe producir una reducción del sueldo del trabajador.</span><span class="sxs-lookup"><span data-stu-id="ece32-179">A doctor's appointment should not cause a deduction in the worker's pay.</span></span> <span data-ttu-id="ece32-180">Por tanto, en este caso, el supervisor puede ajustar las dos horas de ausencia de 8 a 10 manualmente especificando un código de ausencia que indica enfermedad por esas dos horas.</span><span class="sxs-lookup"><span data-stu-id="ece32-180">Therefore, in this case, the supervisor can adjust the two hours of absence from 8 AM to 10 AM by manually entering an absence code that indicates illness for those two hours.</span></span>

### <a name="calculate-and-approve-absence"></a><span data-ttu-id="ece32-181">Calcular y aprobar ausencia</span><span class="sxs-lookup"><span data-stu-id="ece32-181">Calculate and approve absence</span></span>

- <span data-ttu-id="ece32-182">Seleccione **Asistencia de tiempo** &gt; **Revisar y aprobar** &gt; **Aprobar o calcular**.</span><span class="sxs-lookup"><span data-stu-id="ece32-182">Select **Time attendance** &gt; **Review and approve** &gt; **Approve or Calculate**.</span></span>

