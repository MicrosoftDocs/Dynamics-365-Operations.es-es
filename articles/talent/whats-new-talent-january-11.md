---
title: Novedades y cambios en Dynamics 365 Talent - Core HR (11 de enero de 2019)
description: Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Talent - Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 01/11/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-01-11
ms.dyn365.ops.version: Talent
ms.openlocfilehash: d49a4aca368e3de10ae37b56c6d286d78f7f369a
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/06/2019
ms.locfileid: "2899183"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent---core-hr-january-11-2019"></a><span data-ttu-id="aeeeb-103">Novedades y cambios en Dynamics 365 Talent - Core HR (11 de enero de 2019)</span><span class="sxs-lookup"><span data-stu-id="aeeeb-103">What's new or changed in Dynamics 365 Talent - Core HR (January 11, 2019)</span></span>

<span data-ttu-id="aeeeb-104">**Compilación 8.1.2100**</span><span class="sxs-lookup"><span data-stu-id="aeeeb-104">**Build 8.1.2100**</span></span>

<span data-ttu-id="aeeeb-105">Este tema describe las características que son nuevas o que se han cambiado en Core HR.</span><span class="sxs-lookup"><span data-stu-id="aeeeb-105">This topic describes features that are either new or changed in Core HR.</span></span>

## <a name="changes"></a><span data-ttu-id="aeeeb-106">Cambios</span><span class="sxs-lookup"><span data-stu-id="aeeeb-106">Changes</span></span>

### <a name="validate-leave-requests-by-forecasting-available-balance"></a><span data-ttu-id="aeeeb-107">Valide solicitudes de licencia pronosticando el saldo disponible</span><span class="sxs-lookup"><span data-stu-id="aeeeb-107">Validate leave requests by forecasting available balance</span></span>
<span data-ttu-id="aeeeb-108">Los cambios realizados en esta versión permiten a los empleados pedir un tiempo futuro de licencia sin restarlo de los saldos actuales.</span><span class="sxs-lookup"><span data-stu-id="aeeeb-108">Changes made in this release allow employees to request future leave time without subtracting from their current balance.</span></span> <span data-ttu-id="aeeeb-109">Los flujos de trabajo estándar se usarán para cualquier solicitud futura realizada.</span><span class="sxs-lookup"><span data-stu-id="aeeeb-109">Standard workflows will be used for any future requests made.</span></span> <span data-ttu-id="aeeeb-110">Para obtener más información, consulte [Acumulación de licencias basada en las horas trabajadas](leave-accrue-hours-worked.md).</span><span class="sxs-lookup"><span data-stu-id="aeeeb-110">For more information, read [Accrue time off based on hours worked](leave-accrue-hours-worked.md).</span></span>

### <a name="view-forecasted-leave-balance-in-ess-and-people"></a><span data-ttu-id="aeeeb-111">Ver saldo de licencia previsto en ESS y personas</span><span class="sxs-lookup"><span data-stu-id="aeeeb-111">View forecasted leave balance in ESS and People</span></span>
<span data-ttu-id="aeeeb-112">Esta función permite visualizar saldos para períodos futuros de licencia, por Recursos Humanos, administradores, y empleados.</span><span class="sxs-lookup"><span data-stu-id="aeeeb-112">This feature enables viewing of balances for future leave periods by HR, managers, and employees.</span></span> <span data-ttu-id="aeeeb-113">Los empleados pueden ver los saldos futuros en el área de trabajo **Autoservicio para empleados** y Recursos Humanos tiene acceso a la misma información mediante el espacio de trabajo **Personas**.</span><span class="sxs-lookup"><span data-stu-id="aeeeb-113">Employees can view future balances in the **Employee Self-Service** workspace and HR has access to the same information using the **People** workspace.</span></span>

### <a name="notifications-for-changing-leave-balances"></a><span data-ttu-id="aeeeb-114">Notificaciones para modificar los saldos de licencia</span><span class="sxs-lookup"><span data-stu-id="aeeeb-114">Notifications for changing leave balances</span></span>
<span data-ttu-id="aeeeb-115">Los saldos de licencia mostrarán el saldo actual de los empleados.</span><span class="sxs-lookup"><span data-stu-id="aeeeb-115">Leave balances will display the employees current balance.</span></span> <span data-ttu-id="aeeeb-116">Los saldos futuros están disponibles en las áreas de trabajo **Autoservicio para empleados** y **Personas** especificando “a partir de la fecha” para calcular el saldo previsto.</span><span class="sxs-lookup"><span data-stu-id="aeeeb-116">Future balances are available on the **Employee Self-Service** and **People** workspaces by entering an “as of date” to calculate the forecasted balance.</span></span>

<span data-ttu-id="aeeeb-117">La exploración se ha agregado para ver los saldos previstos en las siguientes áreas:</span><span class="sxs-lookup"><span data-stu-id="aeeeb-117">Navigation has been added to view forecasted balances in the following areas:</span></span>
  - <span data-ttu-id="aeeeb-118">Tarjeta de**Licencias** en el área de trabajo **Autoservicio para empleados**.</span><span class="sxs-lookup"><span data-stu-id="aeeeb-118">**Time off** card on the **Employee Self-Service** workspace.</span></span>
  - <span data-ttu-id="aeeeb-119">Tarjeta de**Baja y ausencia** en el área de trabajo **Autoservicio para directores**.</span><span class="sxs-lookup"><span data-stu-id="aeeeb-119">**Leave and absence** card on the **Manager Self-Service** workspace.</span></span>
  - <span data-ttu-id="aeeeb-120">Página**Baja y ausencia** en el espacio de trabajo **Personas**.</span><span class="sxs-lookup"><span data-stu-id="aeeeb-120">**Leave and absence** page on the **People** workspace.</span></span>

### <a name="allow-decimals-for-variable-compensation-plans-cash-plans"></a><span data-ttu-id="aeeeb-121">Permite decimales para planes de compensación variable (planes de efectivo)</span><span class="sxs-lookup"><span data-stu-id="aeeeb-121">Allow decimals for Variable compensation plans (Cash plans)</span></span>
<span data-ttu-id="aeeeb-122">Las primas en efectivo y los planes variables tienen ahora la flexibilidad adicional para los importes y las anulaciones para valores con importes decimales.</span><span class="sxs-lookup"><span data-stu-id="aeeeb-122">Variable cash awards and plans now have the additional flexibility for amounts and overrides for values with decimal amounts.</span></span>

### <a name="unable-to-change-the-dates-on-variable-comp-enrollments-after-the-plan-is-saved"></a><span data-ttu-id="aeeeb-123">No se pueden cambiar las fechas en inscripciones comp de variables después de que se guarde el plan</span><span class="sxs-lookup"><span data-stu-id="aeeeb-123">Unable to change the dates on Variable comp enrollments after the plan is saved</span></span>
<span data-ttu-id="aeeeb-124">Este cambio permite que la fecha final del plan sea actualizada (extendida o caducada) después de que se haya guardado el plan.</span><span class="sxs-lookup"><span data-stu-id="aeeeb-124">This change allows for the plan end date to be updated (extended or expired) after the plan has been saved.</span></span> <span data-ttu-id="aeeeb-125">Puede activar o desactivar planes sean cuales sean las fechas de inicio o finales.</span><span class="sxs-lookup"><span data-stu-id="aeeeb-125">You can still activate or de-activate plans independent of start and end dates.</span></span>

### <a name="payroll-information-available-when-assigned-the-payroll-admin-security-role"></a><span data-ttu-id="aeeeb-126">Información de nómina disponible cuando se tiene asignado el rol de seguridad Administración de nóminas</span><span class="sxs-lookup"><span data-stu-id="aeeeb-126">Payroll information available when assigned the Payroll admin security role</span></span>
<span data-ttu-id="aeeeb-127">El rol de administrador de nóminas se ha actualizado para tener acceso a la información de nómina durante el proceso de solicitud.</span><span class="sxs-lookup"><span data-stu-id="aeeeb-127">The Payroll Administrator role has been updated to have access to the payroll information during the request process.</span></span>

### <a name="employee-self-service--position-hierarchy-drill-down-from-tile-fails-to-get-parent-node"></a><span data-ttu-id="aeeeb-128">Autogestión del empleado | La exploración de jerarquía de posiciones desde el icono no puede obtener el nodo principal</span><span class="sxs-lookup"><span data-stu-id="aeeeb-128">Employee self-service | Position hierarchy drill-down from tile fails to get parent node</span></span>
<span data-ttu-id="aeeeb-129">Los cambios se han realizado para eliminar un error que aparecía al agregar la jerarquía de puestos a las nuevas áreas de trabajo y desplazarse dentro de la estructura organizativa.</span><span class="sxs-lookup"><span data-stu-id="aeeeb-129">Changes have been made to eliminate an error that occurred when adding the position hierarchy to new workspaces and navigating within the organizational structure.</span></span>

### <a name="new-validation-message-when-personnel-number-sequence-is-in-use"></a><span data-ttu-id="aeeeb-130">Nuevo mensaje de validación cuando la secuencia del número de personal está en uso</span><span class="sxs-lookup"><span data-stu-id="aeeeb-130">New validation message when personnel number sequence is in use</span></span>
<span data-ttu-id="aeeeb-131">Un cambio se ha efectuado para aclarar cuál es el problema cuando contrata a un empleado y el número de personal siguiente está en uso.</span><span class="sxs-lookup"><span data-stu-id="aeeeb-131">A change has been made to clarify what the issue is when you hire an employee and the next personnel number is in use.</span></span>

### <a name="employee-self-service-workspace-selected-as-the-initial-startup-page"></a><span data-ttu-id="aeeeb-132">Área de trabajo de autoservicio del empleado seleccionada como página de inicio</span><span class="sxs-lookup"><span data-stu-id="aeeeb-132">Employee self-service workspace selected as the initial startup page</span></span>
<span data-ttu-id="aeeeb-133">Cuando se selecciona el área de trabajo **Autoservicio de empleado** como la página de inicio para un usuario y dicho usuario no tiene asignado el rol de empleado, el sistema redirigirá al panel predeterminado.</span><span class="sxs-lookup"><span data-stu-id="aeeeb-133">When the **Employee self-service** workspace is selected as the initial startup page for a user and that user is not assigned the employee role, the system will redirect to the default dashboard.</span></span>

### <a name="termination-reason-code-updates-position-assignment-record"></a><span data-ttu-id="aeeeb-134">El código de motivo de finalización actualiza el registro de asignación de puesto</span><span class="sxs-lookup"><span data-stu-id="aeeeb-134">Termination reason code updates position assignment record</span></span>
<span data-ttu-id="aeeeb-135">El código de motivo de baja ahora actualizará la asignación de puesto al cesar a un empleado y dar por terminado el puesto.</span><span class="sxs-lookup"><span data-stu-id="aeeeb-135">The termination reason code will now update the position assignment when terminating an employee and ending the position.</span></span> 
