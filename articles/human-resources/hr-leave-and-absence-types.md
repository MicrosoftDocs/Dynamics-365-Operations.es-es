---
title: Configurar tipos de permisos y ausencias
description: Configure los tipos de baja que los empleados pueden tomar en Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 06/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 6e6ca7d04b86232ba48474fcbe288a18995661ae
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4420389"
---
# <a name="configure-leave-and-absence-types"></a><span data-ttu-id="d59ee-103">Configurar tipos de permisos y ausencias</span><span class="sxs-lookup"><span data-stu-id="d59ee-103">Configure leave and absence types</span></span>

<span data-ttu-id="d59ee-104">Los tipos de permisos en Dynamics 365 Human Resources definen los distintos tipos de ausencias que los empleados puedan notificar.</span><span class="sxs-lookup"><span data-stu-id="d59ee-104">Leave types in Dynamics 365 Human Resources define the types of absences that employees can report.</span></span> <span data-ttu-id="d59ee-105">Puede adaptar los tipos de baja en función de las necesidades de su organización.</span><span class="sxs-lookup"><span data-stu-id="d59ee-105">You can tailor leave types according to the needs of your organization.</span></span> <span data-ttu-id="d59ee-106">Entre los tipos de baja se incluyen:</span><span class="sxs-lookup"><span data-stu-id="d59ee-106">Examples of leave types include:</span></span>

- <span data-ttu-id="d59ee-107">Tiempo libre remunerado (PTO)</span><span class="sxs-lookup"><span data-stu-id="d59ee-107">Paid time off (PTO)</span></span>
- <span data-ttu-id="d59ee-108">Ausencia no retribuida</span><span class="sxs-lookup"><span data-stu-id="d59ee-108">Unpaid leave</span></span>
- <span data-ttu-id="d59ee-109">Vacaciones pagadas</span><span class="sxs-lookup"><span data-stu-id="d59ee-109">Paid vacation</span></span>
- <span data-ttu-id="d59ee-110">Baja por enfermedad</span><span class="sxs-lookup"><span data-stu-id="d59ee-110">Sick leave</span></span>
- <span data-ttu-id="d59ee-111">Baja médica</span><span class="sxs-lookup"><span data-stu-id="d59ee-111">Medical leave</span></span>
- <span data-ttu-id="d59ee-112">Licencia familiar</span><span class="sxs-lookup"><span data-stu-id="d59ee-112">Family leave</span></span>
- <span data-ttu-id="d59ee-113">Incapacidad de corta duración</span><span class="sxs-lookup"><span data-stu-id="d59ee-113">Short-term disability</span></span>
- <span data-ttu-id="d59ee-114">Licencia por duelo</span><span class="sxs-lookup"><span data-stu-id="d59ee-114">Bereavement leave</span></span>

## <a name="add-a-leave-type"></a><span data-ttu-id="d59ee-115">Agregar un tipo de licencia</span><span class="sxs-lookup"><span data-stu-id="d59ee-115">Add a leave type</span></span>

1. <span data-ttu-id="d59ee-116">En la página **Bajas y ausencias**, seleccione la pestaña **Vínculos**.</span><span class="sxs-lookup"><span data-stu-id="d59ee-116">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="d59ee-117">En **Configuración**, seleccione **Tipos de permisos y ausencias**.</span><span class="sxs-lookup"><span data-stu-id="d59ee-117">Under **Setup**, select **Leave and absence types**.</span></span>

3. <span data-ttu-id="d59ee-118">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="d59ee-118">Select **New**.</span></span>

4. <span data-ttu-id="d59ee-119">Escriba un nombre para el tipo de baja debajo de **Tipo**, seleccione un flujo de trabajo en **Id. de flujo de trabajo** e introduzca una descripción debajo de **Descripción**.</span><span class="sxs-lookup"><span data-stu-id="d59ee-119">Enter a name for the leave type under **Type**, select a workflow from **Workflow ID**, and enter a description under **Description**.</span></span>

5. <span data-ttu-id="d59ee-120">En **General**, seleccione **Ninguno**, **Programado** o **No programado** en el menú desplegable **Categoría**.</span><span class="sxs-lookup"><span data-stu-id="d59ee-120">In **General**, select **None**, **Scheduled**, or **Unscheduled** from the **Category** dropdown.</span></span>

6. <span data-ttu-id="d59ee-121">Seleccione un código de ganancia en el menú desplegable **Código de ganancias**.</span><span class="sxs-lookup"><span data-stu-id="d59ee-121">Select an earning code from the **Earning code** dropdown.</span></span>

7. <span data-ttu-id="d59ee-122">Debajo de **Código de motivo requerido**, elija si desea requerir un código de motivo.</span><span class="sxs-lookup"><span data-stu-id="d59ee-122">Under **Reason code required**, choose whether you want to require a reason code.</span></span> <span data-ttu-id="d59ee-123">Si desea requerir códigos de motivo, es posible que deba agregarlos.</span><span class="sxs-lookup"><span data-stu-id="d59ee-123">If you want to require reason codes, you might need to add them.</span></span> <span data-ttu-id="d59ee-124">Debajo de **Códigos de motivo**, seleccione **Agregar**, seleccione un código de motivo y luego seleccione la casilla **Habilitado** que se encuentra al lado.</span><span class="sxs-lookup"><span data-stu-id="d59ee-124">Under **Reason codes**, select **Add**, select a reason code, and then select the **Enabled** checkbox next to it.</span></span>

8. <span data-ttu-id="d59ee-125">Debajo de **Restringir el acceso a los roles seleccionados**, elija si desea restringir el acceso.</span><span class="sxs-lookup"><span data-stu-id="d59ee-125">Under **Restrict access to selected roles**, choose whether you want to restrict access.</span></span> <span data-ttu-id="d59ee-126">Luego seleccione los roles de seguridad en **Roles de seguridad para este tipo de permiso**.</span><span class="sxs-lookup"><span data-stu-id="d59ee-126">Then select the security roles under **Security roles for this leave type**.</span></span> <span data-ttu-id="d59ee-127">Los roles de seguridad se definen en el flujo de trabajo que ha seleccionado en **Id. de flujo de trabajo** anteriormente en este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="d59ee-127">The security roles are defined in the workflow you selected under **Workflow ID** earlier in this procedure.</span></span>

9. <span data-ttu-id="d59ee-128">Debajo de **Color del calendario**, elija qué color mostrar en los calendarios de permisos y ausencias para este tipo de permisos.</span><span class="sxs-lookup"><span data-stu-id="d59ee-128">Under **Calendar color**, choose what color to display on leave and absence calendars for this leave type.</span></span> 

10. <span data-ttu-id="d59ee-129">En **Relaciones de suspensión**, elija si desea que este tipo de licencia suspenda otro tipo de licencia o sea suspendido por otro tipo de licencia.</span><span class="sxs-lookup"><span data-stu-id="d59ee-129">Under **Suspension relations**, choose if you want to have this leave type either suspend another leave type or be suspended by another leave type.</span></span> <span data-ttu-id="d59ee-130">Cuando se envía una solicitud de baja para el tipo de licencia que suspende, se creará automáticamente una suspensión de licencia para el tipo de licencia suspendida.</span><span class="sxs-lookup"><span data-stu-id="d59ee-130">When a leave of absence request is submitted for the suspending leave type, a leave suspension will automatically be created for the suspended leave type.</span></span> 

10. <span data-ttu-id="d59ee-131">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="d59ee-131">Select **Save**.</span></span>

## <a name="configure-leave-type-rules"></a><span data-ttu-id="d59ee-132">Configurar reglas de tipo de permiso</span><span class="sxs-lookup"><span data-stu-id="d59ee-132">Configure leave type rules</span></span>

1. <span data-ttu-id="d59ee-133">Establezca opciones de redondeo para el tipo de baja.</span><span class="sxs-lookup"><span data-stu-id="d59ee-133">Set rounding options for the leave type.</span></span> <span data-ttu-id="d59ee-134">Las opciones incluyen **Ninguno**, **Arriba**, **Abajo** y **Aproximación**.</span><span class="sxs-lookup"><span data-stu-id="d59ee-134">Options include **None**, **Up**, **Down**, and **Nearest**.</span></span> <span data-ttu-id="d59ee-135">También puede establecer la precisión de redondeo para el tipo de baja.</span><span class="sxs-lookup"><span data-stu-id="d59ee-135">You can also set rounding precision for the leave type.</span></span>

2. <span data-ttu-id="d59ee-136">Establezca **Corrección de día festivo** para el tipo de baja.</span><span class="sxs-lookup"><span data-stu-id="d59ee-136">Set **Holiday correction** for the leave type.</span></span> <span data-ttu-id="d59ee-137">Cuando selecciona esta opción, Human Resources usa el número de días festivos que caen en un día laboral para determinar cómo acumular tiempo libre para el tipo de baja.</span><span class="sxs-lookup"><span data-stu-id="d59ee-137">When you select this option, Human Resources uses the number of holidays that fall on a work day to determine how to accrue time off for the leave type.</span></span> <span data-ttu-id="d59ee-138">Por ejemplo, si el día de Navidad cae en lunes, Human Resources restará un día del tipo de baja al procesar las acumulaciones.</span><span class="sxs-lookup"><span data-stu-id="d59ee-138">For example, if Christmas Day falls on a Monday, Human Resources will subtract one day from the leave type when processing accruals.</span></span>

   <span data-ttu-id="d59ee-139">Puede establecer días festivos en el calendario de tiempo laborable.</span><span class="sxs-lookup"><span data-stu-id="d59ee-139">You set holidays in the working time calendar.</span></span> <span data-ttu-id="d59ee-140">Para obtener más información, consulte [Crear un calendario de horas de trabajo](hr-leave-and-absence-working-time-calendar.md).</span><span class="sxs-lookup"><span data-stu-id="d59ee-140">For more information, see [Create a working time calendar](hr-leave-and-absence-working-time-calendar.md)</span></span>
   
 3. <span data-ttu-id="d59ee-141">Establezca **Tipo de baja de transferencia** para el tipo de baja.</span><span class="sxs-lookup"><span data-stu-id="d59ee-141">Set **Carry-forward leave type** for the leave type.</span></span> <span data-ttu-id="d59ee-142">Cuando selecciona esta opción, los saldos de arrastre se transferirán al tipo de baja especificado.</span><span class="sxs-lookup"><span data-stu-id="d59ee-142">When you select this option, any carry-forward balances will be transferred to the specified leave type.</span></span> <span data-ttu-id="d59ee-143">El tipo de baja de transferencia también debe incluirse en el plan de baja y ausencia.</span><span class="sxs-lookup"><span data-stu-id="d59ee-143">The carry-forward leave type also needs to be included in the leave and absence plan.</span></span> 
 
 4. <span data-ttu-id="d59ee-144">Defina las **Reglas de vencimiento** para el tipo de licencia.</span><span class="sxs-lookup"><span data-stu-id="d59ee-144">Define **Expiration rules** for the leave type.</span></span> <span data-ttu-id="d59ee-145">Cuando configura esta opción, puede elegir la unidad de días o meses y establecer la duración hasta el vencimiento.</span><span class="sxs-lookup"><span data-stu-id="d59ee-145">When you configure this option, you can choose the unit of days or months and set the duration for the expiry.</span></span> <span data-ttu-id="d59ee-146">También puede establecer la fecha de vigencia de la regla de vencimiento.</span><span class="sxs-lookup"><span data-stu-id="d59ee-146">You can also set the effective date of the expiration rule.</span></span> <span data-ttu-id="d59ee-147">Cualquier saldo de baja que exista al momento del vencimiento se restará del tipo de baja y se reflejará en el saldo de bajas.</span><span class="sxs-lookup"><span data-stu-id="d59ee-147">Any leave balances that exist at the time of expiry will be subtracted from the leave type and will be reflected in the leave balance.</span></span> 
 
 
## <a name="see-also"></a><span data-ttu-id="d59ee-148">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d59ee-148">See also</span></span>

- [<span data-ttu-id="d59ee-149">Visión general de bajas y ausencias</span><span class="sxs-lookup"><span data-stu-id="d59ee-149">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)
- [<span data-ttu-id="d59ee-150">Crear un plan de permisos y ausencias</span><span class="sxs-lookup"><span data-stu-id="d59ee-150">Create a leave and absence plan</span></span>](hr-leave-and-absence-plans.md)
- [<span data-ttu-id="d59ee-151">Crear un calendario de horas de trabajo</span><span class="sxs-lookup"><span data-stu-id="d59ee-151">Create a working time calendar</span></span>](hr-leave-and-absence-working-time-calendar.md)
- [<span data-ttu-id="d59ee-152">Suspender baja</span><span class="sxs-lookup"><span data-stu-id="d59ee-152">Suspend leave</span></span>](hr-leave-and-absence-suspend-leave.md)

