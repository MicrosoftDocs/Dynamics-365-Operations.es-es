---
title: Novedades y cambios en Dynamics 365 for Talent Core HR (14 de diciembre de 2018)
description: "Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 for Talent Core HR."
author: Darinkramer
manager: AnnBe
ms.date: 12/14/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-12-14
ms.dyn365.ops.version: Talent
ms.translationtype: HT
ms.sourcegitcommit: 844c23fc908c962203e644f1154cc480425d830b
ms.openlocfilehash: 7d2866923efd7f115ad5290f35ed4fcac5e47573
ms.contentlocale: es-es
ms.lasthandoff: 12/18/2018

---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-core-hr-december-14-2018"></a><span data-ttu-id="d483d-103">Novedades y cambios en Dynamics 365 for Talent Core HR (14 de diciembre de 2018)</span><span class="sxs-lookup"><span data-stu-id="d483d-103">What's new or changed in Dynamics 365 for Talent Core HR (December 14, 2018)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="d483d-104">**Compilación 8.1.2085**</span><span class="sxs-lookup"><span data-stu-id="d483d-104">**Build 8.1.2085**</span></span>

<span data-ttu-id="d483d-105">Este tema describe las características que son nuevas o que se han cambiado en Core HR.</span><span class="sxs-lookup"><span data-stu-id="d483d-105">This topic describes features that are either new or changed in Core HR.</span></span>

## <a name="changes"></a><span data-ttu-id="d483d-106">Cambios</span><span class="sxs-lookup"><span data-stu-id="d483d-106">Changes</span></span>

### <a name="us---aca-affordable-care-act-support-for-tax-year-2018-1095-b-and-1095-c-forms"></a><span data-ttu-id="d483d-107">EE. UU - Soporte de ACA (Ley de cuidados asequible) para los formularios 1095-B y 1095-C del ejercicio fiscal 2018</span><span class="sxs-lookup"><span data-stu-id="d483d-107">US - ACA (Affordable Care Act) support for tax year 2018 1095-B and 1095-C forms</span></span>

<span data-ttu-id="d483d-108">Cada año, los grandes empleadores aplicables (ALE) deben proporcionar a cada empleado a tiempo completo un 1095-C.</span><span class="sxs-lookup"><span data-stu-id="d483d-108">Each year, Applicable Large Employers (ALEs) must provide each full-time employees with a 1095-C.</span></span> <span data-ttu-id="d483d-109">Además, si el patrón proporciona cobertura de seguro debe proporcionar el 1095-C (si es ALE) y un 1095-B (si es un pequeño empresario) a todos los empleados, a jornada completa o a tiempo parcial, cubiertos en uno de sus planes de salud.</span><span class="sxs-lookup"><span data-stu-id="d483d-109">In addition, if the employer provides self-insured coverage they must provide the 1095-C (if they are an ALE) and a 1095-B (if they are a small employer) to any employee, full-time or part-time, covered under one of their offered health plans.</span></span> <span data-ttu-id="d483d-110">Esta característica facilita formularios imprimibles para el 1095-C y 1095-B.</span><span class="sxs-lookup"><span data-stu-id="d483d-110">This feature provides printable forms for both the 1095-C and 1095-B.</span></span>

### <a name="during-import-submittedbypersonid-field-on-hcmperfjournalentity-is-ignored"></a><span data-ttu-id="d483d-111">Durante la importación el campo SubmittedByPersonId de HcmPerfJournalEntity se omite</span><span class="sxs-lookup"><span data-stu-id="d483d-111">During import SubmittedByPersonId field on HcmPerfJournalEntity is ignored</span></span>

<span data-ttu-id="d483d-112">Al importar o exportar entradas del diario de rendimiento, el campo **Enviado por** se omite.</span><span class="sxs-lookup"><span data-stu-id="d483d-112">When importing/exporting performance journal entries, the **Submitted by** field is ignored.</span></span> <span data-ttu-id="d483d-113">Con este cambio, el valor **importado/exportado** reflejará el valor de la tabla durante la exportación, al importar el sistema se actualizará con el valor que se incluye en el archivo de importación.</span><span class="sxs-lookup"><span data-stu-id="d483d-113">With this change, the value **imported/exported** will reflect the value in the table during the export, when importing the system will be updated with the value supplied in the import file.</span></span>

### <a name="analytics-tab-on-leave-and-absence-workspace-displays-openconnectionerror-error-for-non-system-admin-roles"></a><span data-ttu-id="d483d-114">La ficha Análisis del área de trabajo de “licencia y ausencia" muestra el error de “OpenConnectionError” para las funciones de la gestión de fuera del sistema</span><span class="sxs-lookup"><span data-stu-id="d483d-114">Analytics tab on 'Leave and absence' workspace displays "OpenConnectionError" error for non-system Admin roles</span></span>

<span data-ttu-id="d483d-115">Con esta actualización, no se emitirán errores al abrir la pestaña **Análisis** del espacio de trabajo **licencia y ausencia**.</span><span class="sxs-lookup"><span data-stu-id="d483d-115">With this update, no errors will be issued when opening the **Analytics** tab on the **Leave and Absence** workspace.</span></span>

### <a name="employee-self-service-position-hierarchy-drill-down-from-tile-fails-to-get-parent-node"></a><span data-ttu-id="d483d-116">Autogestión del empleado, la exploración de jerarquía de posiciones desde el icono no puede obtener el nodo principal</span><span class="sxs-lookup"><span data-stu-id="d483d-116">Employee self-service, Position Hierarchy drill-down from tile fails to get parent node</span></span>

<span data-ttu-id="d483d-117">Un cambio se ha realizado para corregir el error “Error al obtener el nodo principal" cuando la jerarquía de puestos se ha personalizado para que aparezca en un área de trabajo existente y un puesto se selecciona en la jerarquía.</span><span class="sxs-lookup"><span data-stu-id="d483d-117">A change has been made to correct the error "Getting the parent node failed" when the position hierarchy has been personalized to appear on an existing workspace and a position is selected in the hierarchy.</span></span>  

### <a name="must-be-system-admin-to-see-the-payroll-tab-in-the-position-page"></a><span data-ttu-id="d483d-118">Debe ser Administrador del sistema para ver la ficha de la nómina en la página de puesto</span><span class="sxs-lookup"><span data-stu-id="d483d-118">Must be System Admin to see the Payroll tab in the Position page</span></span>

<span data-ttu-id="d483d-119">Un cambio se ha efectuado para incluir los elementos de seguridad adecuados en el privilegio existente: “Mantener detalles de trabajador y puesto de nómina”.</span><span class="sxs-lookup"><span data-stu-id="d483d-119">A change has been made to include the correct security elements in the existing privilege: "Maintain payroll worker and position detail".</span></span> <span data-ttu-id="d483d-120">Con este cambio, de forma predeterminada, el administrador de nóminas tendrá acceso a los campos de nómina en la página de puesto.</span><span class="sxs-lookup"><span data-stu-id="d483d-120">With this change, by default, the Payroll Administrator will have access to the Payroll fields on the Position page.</span></span>

### <a name="error-when-submitting-performance-review-to-manager-and-the-reviewsperfperiod-placeholder-is-used-in-the-submission-instructions"></a><span data-ttu-id="d483d-121">Error al enviar la evaluación del rendimiento al administrador y el marcador de posición %Reviews.PerfPeriod% se usa en las instrucciones de envío</span><span class="sxs-lookup"><span data-stu-id="d483d-121">Error when submitting performance review to manager and the %Reviews.PerfPeriod% placeholder is used in the Submission instructions</span></span>

<span data-ttu-id="d483d-122">Se ha realizado un cambio que corrige el error “referencia nula” al utilizar el marcador de posición %Reviews.PerfPeriod% en las instrucciones del envío.</span><span class="sxs-lookup"><span data-stu-id="d483d-122">A change has been made that corrects the "Null Reference" error when using the %Reviews.PerfPeriod% placeholder in the Submission instructions.</span></span>

### <a name="workforce-power-bi-report-shows-error-when-worker-seniority-date-is-a-leap-day"></a><span data-ttu-id="d483d-123">El informe de Workforce Power BI muestra un error cuando la fecha antigüedad del trabajador cae en 29 de febrero</span><span class="sxs-lookup"><span data-stu-id="d483d-123">Workforce Power BI report shows error when worker seniority date is a leap day</span></span>

<span data-ttu-id="d483d-124">Con este cambio, ahora Power BI admite el 29 de febrero.</span><span class="sxs-lookup"><span data-stu-id="d483d-124">With this change, leap days are now supported in Power BI.</span></span>

### <a name="integration-between-core-hr-and-attract"></a><span data-ttu-id="d483d-125">La integración entre Core HR y Attract</span><span class="sxs-lookup"><span data-stu-id="d483d-125">Integration between Core HR and Attract</span></span>

<span data-ttu-id="d483d-126">Un cambio se ha efectuado para actualizar la integración entre Core HR y Attract en relación con los candidatos a contratar.</span><span class="sxs-lookup"><span data-stu-id="d483d-126">A change has been made to update the integration between Core HR and Attract related to candidates to hire.</span></span> <span data-ttu-id="d483d-127">Para que los candidatos a contratar estén visibles en el área de trabajo **Dirección de personal**, se usan las entidades CDS para aplicaciones (CDS 2.0) siguientes:</span><span class="sxs-lookup"><span data-stu-id="d483d-127">For candidates to hire to be visible in the **Personnel Management** workspace, the following CDS for Apps (CDS 2.0) entities are used:</span></span>

<span data-ttu-id="d483d-128">Solicitud de trabajo</span><span class="sxs-lookup"><span data-stu-id="d483d-128">Job Application</span></span>
- <span data-ttu-id="d483d-129">El motivo del estado tiene que establecerse en propuesta aceptada</span><span class="sxs-lookup"><span data-stu-id="d483d-129">Status Reason needs to be set to Offer Accepted</span></span>
-   <span data-ttu-id="d483d-130">Proporciona el candidato y la vacante</span><span class="sxs-lookup"><span data-stu-id="d483d-130">Provides Candidate and Job Opening</span></span>

<span data-ttu-id="d483d-131">Candidato</span><span class="sxs-lookup"><span data-stu-id="d483d-131">Candidate</span></span>
-   <span data-ttu-id="d483d-132">Proporciona información del candidato</span><span class="sxs-lookup"><span data-stu-id="d483d-132">Provides Candidate information</span></span>

<span data-ttu-id="d483d-133">Vacante</span><span class="sxs-lookup"><span data-stu-id="d483d-133">Job Opening</span></span>
-   <span data-ttu-id="d483d-134">Proporciona el ID de vacante y los participantes en la vacante</span><span class="sxs-lookup"><span data-stu-id="d483d-134">Provides Job Opening ID and Job Opening Participants</span></span>

<span data-ttu-id="d483d-135">Participantes en la vacante</span><span class="sxs-lookup"><span data-stu-id="d483d-135">Job Opening Participants</span></span>
-   <span data-ttu-id="d483d-136">Proporciona un director de contratación</span><span class="sxs-lookup"><span data-stu-id="d483d-136">Provides Hiring Manager</span></span>

<span data-ttu-id="d483d-137">Al agregar un candidato a la dirección del personal, ahora el candidato también puede ser despedido mediante una nueva opción disponible en la tarjeta del candidato.</span><span class="sxs-lookup"><span data-stu-id="d483d-137">When a candidate is added to Personnel Management, the candidate can now also be dismissed using a new option available on the candidate card.</span></span>

## <a name="coming-soon"></a><span data-ttu-id="d483d-138">Próximamente</span><span class="sxs-lookup"><span data-stu-id="d483d-138">Coming soon</span></span>

### <a name="leave-and-absence-future-leave-and-forecasting-leave-balances"></a><span data-ttu-id="d483d-139">Baja y ausencia: Saldos futuros de licencia y de previsión de la licencia</span><span class="sxs-lookup"><span data-stu-id="d483d-139">Leave and absence: Future leave and forecasting leave balances</span></span>

<span data-ttu-id="d483d-140">Con los cambios creados para permitir que los empleados pronostiquen el tiempo libre y pidan futuras solicitudes de tiempo libre sin afectar a sus saldos actuales de tiempo libre, el modo en que el tiempo libre de los saldos se muestra también está cambiando.</span><span class="sxs-lookup"><span data-stu-id="d483d-140">With the changes being made to allow for employees to forecast time off and request future time off requests without impacting their current time off balances, the way the time off balances are displayed is also changing.</span></span> 

<span data-ttu-id="d483d-141">El saldo disponible presentado actualmente es la cantidad de tiempo libre disponible para solicitudes que incluyen acumulaciones hasta hoy y todas las solicitudes aprobadas de licencia hasta la finalización de tiempo.</span><span class="sxs-lookup"><span data-stu-id="d483d-141">The available balance currently displayed is the amount of time off available for requests including accruals through today and all approved leave requests to the end of time.</span></span> 

<span data-ttu-id="d483d-142">Cuando se lanza la capacidad de previsión, el saldo mostrado cambia para ser el saldo actual del tiempo libre incluidas las acumulaciones hasta hoy y las solicitudes hasta hoy.</span><span class="sxs-lookup"><span data-stu-id="d483d-142">When the ability to forecast is released, the balance displayed changes to  be the current balance of time off including accruals through today and requests through today.</span></span> <span data-ttu-id="d483d-143">Los empleados y los administradores verán estos saldos actualizados en el autoservicio de empleado y director en la tarjeta **Licencias** y en la ventana **Saldos de licencias**.</span><span class="sxs-lookup"><span data-stu-id="d483d-143">Employees and managers will see these updated balances in employee and manager self-service on the **Time off** card and in the **Time off balances** window.</span></span> <span data-ttu-id="d483d-144">Los administradores de RR.HH. verán estos saldos actualizados en el espacio de trabajo **Personas** y en la ventana **Planes de licencia asignados** del empleado.</span><span class="sxs-lookup"><span data-stu-id="d483d-144">HR managers will see these updated balances in the **People** workspace and in the employee’s **Assigned leave plans** window.</span></span>

## <a name="known-issue"></a><span data-ttu-id="d483d-145">Problema conocido</span><span class="sxs-lookup"><span data-stu-id="d483d-145">Known issue</span></span>

### <a name="mapping-errors-in-the-integration-with-finance-and-operations"></a><span data-ttu-id="d483d-146">Errores de asignación en la integración con Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="d483d-146">Mapping errors in the integration with Finance and Operations</span></span>

<span data-ttu-id="d483d-147">Los siguiente problemas se han identificado en la plantilla actual para la integración de Talent con Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="d483d-147">The following issues have been identified in the current template for integrating Talent with Dynamics 365 for Finance and Operations.</span></span> <span data-ttu-id="d483d-148">Una nueva plantilla se publicará pronto y se aplicará a todos los proyectos nuevos de integración que se creen.</span><span class="sxs-lookup"><span data-stu-id="d483d-148">A new template will be published soon and will be applied to all new integration projects that are created.</span></span> <span data-ttu-id="d483d-149">Para los proyectos existentes de integración, las equivalencias de tareas se pueden volver a calcular.</span><span class="sxs-lookup"><span data-stu-id="d483d-149">For existing integration projects, the task mappings can be updated.</span></span> <span data-ttu-id="d483d-150">Consulte la tabla siguiente para obtener las asignaciones actualizadas.</span><span class="sxs-lookup"><span data-stu-id="d483d-150">Refer to the following table for updated mappings.</span></span> 

>[!NOTE]
> <span data-ttu-id="d483d-151">La tarea de asignación de puestos de trabajo a la tarea principal de los puestos no integra los datos.</span><span class="sxs-lookup"><span data-stu-id="d483d-151">The Job Positions to Positions Parent Job Assignment task does not integrate data.</span></span> <span data-ttu-id="d483d-152">Este es un problema que se está investigando actualmente.</span><span class="sxs-lookup"><span data-stu-id="d483d-152">This is an issue that is currently being researched.</span></span> <span data-ttu-id="d483d-153">No hay solución en la asignación actual.</span><span class="sxs-lookup"><span data-stu-id="d483d-153">There is no workaround in the current mapping.</span></span> 

<span data-ttu-id="d483d-154">La tarea Departamentos a la unidad operativa necesita actualizar las asignaciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="d483d-154">The Departments to Operating unit task needs the following mappings updated.</span></span>

| <span data-ttu-id="d483d-155">Campo de origen existente</span><span class="sxs-lookup"><span data-stu-id="d483d-155">Existing source field</span></span>          | <span data-ttu-id="d483d-156">Nuevo campo de origen</span><span class="sxs-lookup"><span data-stu-id="d483d-156">New source field</span></span> |
| -------------------------------|------------------|
| <span data-ttu-id="d483d-157">cdm_description (descripción)</span><span class="sxs-lookup"><span data-stu-id="d483d-157">cdm_description (Description)</span></span>  | <span data-ttu-id="d483d-158">cdm_name (nombre)</span><span class="sxs-lookup"><span data-stu-id="d483d-158">cdm_name (Name)</span></span>  |

<span data-ttu-id="d483d-159">También es necesario agregar una asignación adicional.</span><span class="sxs-lookup"><span data-stu-id="d483d-159">An additional mapping also needs to be added.</span></span> <span data-ttu-id="d483d-160">Seleccione el último campo **Ninguno** para agregar la siguiente asignación.</span><span class="sxs-lookup"><span data-stu-id="d483d-160">Select the last **None** field to add the following mapping.</span></span>

| <span data-ttu-id="d483d-161">Campo de origen</span><span class="sxs-lookup"><span data-stu-id="d483d-161">Source field</span></span>                   | <span data-ttu-id="d483d-162">Campo de destino</span><span class="sxs-lookup"><span data-stu-id="d483d-162">Destination field</span></span>    |
| -------------------------------|----------------------|
| <span data-ttu-id="d483d-163">cdm_description (descripción)</span><span class="sxs-lookup"><span data-stu-id="d483d-163">cdm_description (Description)</span></span>  | <span data-ttu-id="d483d-164">NAMEALIAS (NAMEALIAS)</span><span class="sxs-lookup"><span data-stu-id="d483d-164">NAMEALIAS (NAMEALIAS)</span></span>|

<span data-ttu-id="d483d-165">Las asignaciones actualizadas deben tener la misma apariencia que la imagen siguiente.</span><span class="sxs-lookup"><span data-stu-id="d483d-165">The updated mappings should look like the following image.</span></span>

![Tarea Departamentos a unidades operativas](./media/DepartmentMapping.png)


<span data-ttu-id="d483d-167">La tarea Trabajo a Detalle de trabajo necesita actualizar las asignaciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="d483d-167">The Jobs to Job Detail task needs the following mappings updated.</span></span>

| <span data-ttu-id="d483d-168">Campo de origen existente</span><span class="sxs-lookup"><span data-stu-id="d483d-168">Existing source field</span></span>          | <span data-ttu-id="d483d-169">Nuevo campo de origen</span><span class="sxs-lookup"><span data-stu-id="d483d-169">New source field</span></span>                   |
| -------------------------------|------------------------------------|
| <span data-ttu-id="d483d-170">cdm_name (nombre)</span><span class="sxs-lookup"><span data-stu-id="d483d-170">cdm_name (Name)</span></span>                | <span data-ttu-id="d483d-171">cdm_description (descripción)</span><span class="sxs-lookup"><span data-stu-id="d483d-171">cdm_description (Description)</span></span>      |
| <span data-ttu-id="d483d-172">cdm_name (descripción)</span><span class="sxs-lookup"><span data-stu-id="d483d-172">cdm_name (Description)</span></span>         | <span data-ttu-id="d483d-173">cdm_jobdescription (descripción del trabajo)</span><span class="sxs-lookup"><span data-stu-id="d483d-173">cdm_jobdescription(Job Description)</span></span>|


<span data-ttu-id="d483d-174">Las asignaciones actualizadas deben tener la misma apariencia que la imagen siguiente.</span><span class="sxs-lookup"><span data-stu-id="d483d-174">The updated mappings should look like the image below.</span></span>

![Tarea Trabajos a detalles del trabajo](./media/JobMapping.png)

<span data-ttu-id="d483d-176">La tarea Trabajadores a trabajo necesita actualizar las asignaciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="d483d-176">The Workers to Work task needs the following mappings updated.</span></span>

| <span data-ttu-id="d483d-177">Campo de origen existente</span><span class="sxs-lookup"><span data-stu-id="d483d-177">Existing source field</span></span>                 | <span data-ttu-id="d483d-178">Nuevo campo de origen</span><span class="sxs-lookup"><span data-stu-id="d483d-178">New source field</span></span>                               |
| --------------------------------------|------------------------------------------------|
| <span data-ttu-id="d483d-179">cdm_emailaddress1 (dirección de correo electrónico 1)</span><span class="sxs-lookup"><span data-stu-id="d483d-179">cdm_emailaddress1 (Email Address 1)</span></span>   | <span data-ttu-id="d483d-180">cdm_primaryemailaddress (dirección de correo electrónico principal)</span><span class="sxs-lookup"><span data-stu-id="d483d-180">cdm_primaryemailaddress (Primary Email Address</span></span> |
| <span data-ttu-id="d483d-181">cdm_telephone1 (teléfono 1)</span><span class="sxs-lookup"><span data-stu-id="d483d-181">cdm_telephone1 (Telephone 1)</span></span>          | <span data-ttu-id="d483d-182">cdm_primarytelephone (teléfono principal)</span><span class="sxs-lookup"><span data-stu-id="d483d-182">cdm_primarytelephone (Primary Telephone)</span></span>       |

<span data-ttu-id="d483d-183">La transformación del campo Género también debe actualizarse.</span><span class="sxs-lookup"><span data-stu-id="d483d-183">The Gender field transform also needs to be updated.</span></span> <span data-ttu-id="d483d-184">Seleccione el tipo de mapa **fn** (función) para el género y actualice las asignaciones de valores siguientes.</span><span class="sxs-lookup"><span data-stu-id="d483d-184">Select the **fn** (function) map type for Gender and update the following value mappings.</span></span>

| <span data-ttu-id="d483d-185">Valor CDS</span><span class="sxs-lookup"><span data-stu-id="d483d-185">CDS value</span></span>                   | <span data-ttu-id="d483d-186">Valor de Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="d483d-186">Finance and Operations value</span></span>                     |
| ----------------------------|--------------------------------------------------|
| <span data-ttu-id="d483d-187">75440000</span><span class="sxs-lookup"><span data-stu-id="d483d-187">75440000</span></span>                    | <span data-ttu-id="d483d-188">Masculino</span><span class="sxs-lookup"><span data-stu-id="d483d-188">Male</span></span>                                             |
| <span data-ttu-id="d483d-189">75440001</span><span class="sxs-lookup"><span data-stu-id="d483d-189">75440001</span></span>                    | <span data-ttu-id="d483d-190">Femenino</span><span class="sxs-lookup"><span data-stu-id="d483d-190">Female</span></span>                                           |
| <span data-ttu-id="d483d-191">75440002</span><span class="sxs-lookup"><span data-stu-id="d483d-191">75440002</span></span>                    | <span data-ttu-id="d483d-192">Nuevo</span><span class="sxs-lookup"><span data-stu-id="d483d-192">None</span></span>                                             | 
| <span data-ttu-id="d483d-193">75440003</span><span class="sxs-lookup"><span data-stu-id="d483d-193">75440003</span></span>                    | <span data-ttu-id="d483d-194">NonSpecific</span><span class="sxs-lookup"><span data-stu-id="d483d-194">NonSpecific</span></span>                                      |

<span data-ttu-id="d483d-195">Las asignaciones actualizadas deben tener la misma apariencia que las imágenes siguientes.</span><span class="sxs-lookup"><span data-stu-id="d483d-195">The updated mappings should look like the following images.</span></span>

![Tarea Trabajadores a Trabajador](./media/WorkerMapping.png)

![Transformación de campo de género](./media/WorkerTransform.png)
