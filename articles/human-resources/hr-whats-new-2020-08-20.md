---
title: Novedades y cambios en Dynamics 365 Human Resources (20 de agosto de 2020)
description: Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Human Resources para el 20 de agosto de 2020.
author: andreabichsel
manager: tfehr
ms.date: 08/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-08-20
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d964f9a532582b18471550a68032d00e19a065c4
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/17/2021
ms.locfileid: "5467274"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-august-20-2020"></a><span data-ttu-id="aad3f-103">Novedades y cambios en Dynamics 365 Human Resources (20 de agosto de 2020)</span><span class="sxs-lookup"><span data-stu-id="aad3f-103">What's new or changed in Dynamics 365 Human Resources (August 20, 2020)</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="aad3f-104">Este tema describe las características que son nuevas o que se han cambiado en Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="aad3f-104">This topic describes features that are either new or changed in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="aad3f-105">Los cambios se aplican al número de compilación 8.1.3478.</span><span class="sxs-lookup"><span data-stu-id="aad3f-105">Changes apply to build number 8.1.3478.</span></span> <span data-ttu-id="aad3f-106">Los números entre paréntesis en algunos encabezados hacen referencia a los números de soporte para referencia de Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="aad3f-106">The numbers in parentheses in some headings refer to Lifecycle Services (LCS) support numbers for reference.</span></span>

## <a name="show-upcoming-and-pending-leave-of-absence-information-to-cards-in-people-workspace"></a><span data-ttu-id="aad3f-107">Mostrar información de permisos de ausencia próximos y pendientes en tarjetas en el espacio de trabajo Personas</span><span class="sxs-lookup"><span data-stu-id="aad3f-107">Show upcoming and pending leave of absence information to cards in People workspace</span></span>

<span data-ttu-id="aad3f-108">Las opciones de solicitud de bajas pendientes y próximas ya están disponibles en las tarjetas de Permisos y ausencias del espacio de trabajo **Personas**.</span><span class="sxs-lookup"><span data-stu-id="aad3f-108">Pending and upcoming leave request options are now available on the Leave and absence cards in the **People** workspace.</span></span>

## <a name="private-field-isnt-yes-by-default-for-employee-role-in-employee-self-service-477106"></a><span data-ttu-id="aad3f-109">El campo Privado no tiene el valor Sí de forma predeterminada para el rol de empleado en el autoservicio de empleados (477106)</span><span class="sxs-lookup"><span data-stu-id="aad3f-109">Private field isn't Yes by default for Employee role in Employee self service (477106)</span></span>

<span data-ttu-id="aad3f-110">El campo **Privado** ahora tiene como valor predeterminado **Sí** cuando los empleados agregan nuevos registros de dirección a través de la página **Informacion personal** del Autoservicio para empleados.</span><span class="sxs-lookup"><span data-stu-id="aad3f-110">The **Private** field now defaults to **Yes** when employees add new address records through the **Personal information** page in Employee self service.</span></span> 

## <a name="candidates-to-hire-fasttab-in-personnel-management-shows-an-incorrect-count-of-candidates-470110"></a><span data-ttu-id="aad3f-111">La ficha desplegable Candidatos a contratar de Gestión de personal muestra un recuento incorrecto de candidatos (470110)</span><span class="sxs-lookup"><span data-stu-id="aad3f-111">Candidates to hire FastTab in Personnel management shows an incorrect count of candidates (470110)</span></span>

<span data-ttu-id="aad3f-112">La página **Gestión de personal** ahora muestra con precisión el número de candidatos a contratar.</span><span class="sxs-lookup"><span data-stu-id="aad3f-112">The **Personnel management** page now accurately displays the number of candidates to hire.</span></span> 

## <a name="cant-enter-sickness-for-terminated-employee-when-accrual-is-set-to-zero-446195"></a><span data-ttu-id="aad3f-113">No se puede introducir la enfermedad para empleados despedidos cuando la acumulación se establece en cero (446195)</span><span class="sxs-lookup"><span data-stu-id="aad3f-113">Can’t enter sickness for terminated employee when accrual is set to zero (446195)</span></span>

<span data-ttu-id="aad3f-114">Las transacciones de bajas ahora están permitidas para los empleados que se despidan en el futuro y la acumulación se establece en cero.</span><span class="sxs-lookup"><span data-stu-id="aad3f-114">Leave transactions are now allowed for employees that have been terminated in the future and the accrual is set to zero.</span></span> <span data-ttu-id="aad3f-115">Las transacciones de bajas se pueden introducir hasta la fecha de terminación del empleado.</span><span class="sxs-lookup"><span data-stu-id="aad3f-115">Leave transactions can be entered up to the termination date of the employee.</span></span> 

## <a name="adding-custom-fields-to-the-new-worker-form-disables-the-fields-in-the-action-pane-for-manage-leave-473314"></a><span data-ttu-id="aad3f-116">La adición de campos personalizados al nuevo formulario Trabajador deshabilita los campos en el Panel Acciones para Administrar bajas (473314)</span><span class="sxs-lookup"><span data-stu-id="aad3f-116">Adding custom fields to the new Worker form disables the fields in the action pane for Manage leave (473314)</span></span>

<span data-ttu-id="aad3f-117">Las opciones del Panel Acciones en el nuevo formulario **Trabajador** en **Gestionar baja** ya no se deshabilitarán si se han agregado campos personalizados al nuevo formulario **Trabajador**.</span><span class="sxs-lookup"><span data-stu-id="aad3f-117">Action pane options on the new **Worker** form in **Manage leave** will no longer be disabled if custom fields have been added to the new **Worker** form.</span></span>

## <a name="making-the-leave-comment-field-mandatory-allows-a-leave-request-to-be-submitted-when-no-comment-is-entered-473543"></a><span data-ttu-id="aad3f-118">Hacer obligatorio el campo Dejar comentario permite enviar una solicitud de baja cuando no se introduce ningún comentario (473543)</span><span class="sxs-lookup"><span data-stu-id="aad3f-118">Making the Leave comment field mandatory allows a leave request to be submitted when no comment is entered (473543)</span></span>

<span data-ttu-id="aad3f-119">Los campos de comentarios ahora pueden ser obligatorios y las solicitudes de baja respetan esta configuración.</span><span class="sxs-lookup"><span data-stu-id="aad3f-119">Comment fields can now be mandatory, and leave requests honor this setting.</span></span> <span data-ttu-id="aad3f-120">Los campos obligatorios son una Característica en vista previa (GB).</span><span class="sxs-lookup"><span data-stu-id="aad3f-120">Mandatory fields is a preview feature.</span></span>

### <a name="dmf-entity-available-for-accrual-suspensions"></a><span data-ttu-id="aad3f-121">Entidad DMF disponible para suspensiones acumuladas</span><span class="sxs-lookup"><span data-stu-id="aad3f-121">DMF entity available for accrual suspensions</span></span>

<span data-ttu-id="aad3f-122">Ahora está disponible una entidad DMF para suspensiones acumuladas.</span><span class="sxs-lookup"><span data-stu-id="aad3f-122">A DMF entity is now available for accrual suspensions.</span></span>

## <a name="in-preview"></a><span data-ttu-id="aad3f-123">En vista previa</span><span class="sxs-lookup"><span data-stu-id="aad3f-123">In preview</span></span>

### <a name="mandatory-fields"></a><span data-ttu-id="aad3f-124">Campos obligatorios</span><span class="sxs-lookup"><span data-stu-id="aad3f-124">Mandatory fields</span></span>

<span data-ttu-id="aad3f-125">Ahora puede hacer que los campos sean obligatorios mediante las características de personalización de Recursos Humanos.</span><span class="sxs-lookup"><span data-stu-id="aad3f-125">You can make fields mandatory by using Human Resources personalization capabilities.</span></span> <span data-ttu-id="aad3f-126">Esta característica requiere **Vistas guardadas**.</span><span class="sxs-lookup"><span data-stu-id="aad3f-126">This feature requires **Saved views**.</span></span> <span data-ttu-id="aad3f-127">Para obtener más información sobre las vistas guardadas, consulte:</span><span class="sxs-lookup"><span data-stu-id="aad3f-127">For more information about saved views, see:</span></span>

- <span data-ttu-id="aad3f-128">[Vistas guardadas: disponibilidad general](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/finance-operations/finance-operations-crossapp-capabilities/saved-views--general-availability) en el plan del segundo lanzamiento de versiones de Dynamics 365 en 2020</span><span class="sxs-lookup"><span data-stu-id="aad3f-128">[Saved views - general availability](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/finance-operations/finance-operations-crossapp-capabilities/saved-views--general-availability) in the Dynamics 365 2020 release wave 2 plan</span></span>
- [<span data-ttu-id="aad3f-129">Crear formularios que usan completamente las vistas guardadas</span><span class="sxs-lookup"><span data-stu-id="aad3f-129">Build forms that fully utilize saved views</span></span>](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/user-interface/understanding-saved-views)

### <a name="human-resources-application-in-teams"></a><span data-ttu-id="aad3f-130">Aplicación Human Resources en Teams</span><span class="sxs-lookup"><span data-stu-id="aad3f-130">Human Resources application in Teams</span></span>

<span data-ttu-id="aad3f-131">Los empleados pueden ver y solicitar tiempo fuera del trabajo en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="aad3f-131">Employees can view and request time away from work within Microsoft Teams.</span></span> <span data-ttu-id="aad3f-132">Pueden interactuar con un bot para crear solicitudes de baja.</span><span class="sxs-lookup"><span data-stu-id="aad3f-132">They can interact with a bot to create leave requests.</span></span> <span data-ttu-id="aad3f-133">Para obtener más información, consulte:</span><span class="sxs-lookup"><span data-stu-id="aad3f-133">For more information, see:</span></span>

- <span data-ttu-id="aad3f-134">[Experiencia de bajas y ausencias de empleados en Microsoft Teams](https://docs.microsoft.com/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) en el plan del primer lanzamiento de versiones de Dynamics 365 en 2020</span><span class="sxs-lookup"><span data-stu-id="aad3f-134">[Employee leave and absence experience in Microsoft Teams](https://docs.microsoft.com/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) in the Dynamics 365 2020 release wave 1 plan</span></span>
- [<span data-ttu-id="aad3f-135">Aplicación Human Resources en Teams</span><span class="sxs-lookup"><span data-stu-id="aad3f-135">Human Resources app in Teams</span></span>](https://go.microsoft.com/fwlink/?linkid=2127841)

## <a name="coming-soon"></a><span data-ttu-id="aad3f-136">Próximamente</span><span class="sxs-lookup"><span data-stu-id="aad3f-136">Coming soon</span></span>

### <a name="human-resources-app-in-teams-preview-features"></a><span data-ttu-id="aad3f-137">Características en vista previa (GB) de la aplicación Human Resources en Teams</span><span class="sxs-lookup"><span data-stu-id="aad3f-137">Human Resources app in Teams preview features</span></span>
 
-  <span data-ttu-id="aad3f-138">**Notificaciones**: los remitentes y aprobadores de solicitudes de permisos se notificarán en la aplicación Human Resources en Teams.</span><span class="sxs-lookup"><span data-stu-id="aad3f-138">**Notifications**: Submitters and approvers of time-off requests will be notified in the Human Resources app in Teams.</span></span> <span data-ttu-id="aad3f-139">Los aprobadores podrán aprobar o rechazar las solicitudes de permisos, y los remitentes recibirán notificación de si la solicitud fue aprobada o denegada.</span><span class="sxs-lookup"><span data-stu-id="aad3f-139">Approvers will be able to approve or deny time-off requests, and submitters will be notified if the request was approved or denied.</span></span>
 
- <span data-ttu-id="aad3f-140">**Calendario de permisos del gerente**: los gerentes podrán ver los permisos aprobados y pendientes para sus subordinados directos en una vista de calendario.</span><span class="sxs-lookup"><span data-stu-id="aad3f-140">**Manager time-off calendar**: Managers will be able to see approved and pending time off for their direct reports in a calendar view.</span></span> <span data-ttu-id="aad3f-141">Esta vista proporciona un fácil reconocimiento de cuándo los miembros del equipo están fuera del trabajo.</span><span class="sxs-lookup"><span data-stu-id="aad3f-141">This view provides an easy understanding of when their team members are away from work.</span></span>

### <a name="checklist-entities-included-in-dataverse"></a><span data-ttu-id="aad3f-142">Lista de entidades incluidas en Dataverse</span><span class="sxs-lookup"><span data-stu-id="aad3f-142">Checklist entities included in Dataverse</span></span>

<span data-ttu-id="aad3f-143">Las entidades de lista de verificación para los procesos Incorporación, Retirada, Transferencias y Empresa estarán disponibles pronto en Dataverse.</span><span class="sxs-lookup"><span data-stu-id="aad3f-143">Checklist entities for Onboarding, Offboarding, Transfers, and Business processes will be available soon in Dataverse.</span></span>

## <a name="known-issues"></a><span data-ttu-id="aad3f-144">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="aad3f-144">Known issues</span></span>

<span data-ttu-id="aad3f-145">Es posible que el espacio de trabajo **Administración de características** muestre características que están deshabilitadas como características en versión preliminar cuando estén disponibles de forma generalizada.</span><span class="sxs-lookup"><span data-stu-id="aad3f-145">The **Feature management** workspace may be displaying features that are disabled as preview features when they are generally available.</span></span> <span data-ttu-id="aad3f-146">A continuación se muestra una lista de características disponibles de forma generalizada que indican un estado incorrecto.</span><span class="sxs-lookup"><span data-stu-id="aad3f-146">Below is a list of generally available features that show an incorrect status.</span></span> 

- <span data-ttu-id="aad3f-147">Administración de prestaciones</span><span class="sxs-lookup"><span data-stu-id="aad3f-147">Benefits management</span></span>
- <span data-ttu-id="aad3f-148">Gestión de casos</span><span class="sxs-lookup"><span data-stu-id="aad3f-148">Case management</span></span>
- <span data-ttu-id="aad3f-149">Registro de base de datos (auditoría)</span><span class="sxs-lookup"><span data-stu-id="aad3f-149">Database logging (Auditing)</span></span>
- <span data-ttu-id="aad3f-150">Acumulación de bajas para una sola empresa o un solo plan</span><span class="sxs-lookup"><span data-stu-id="aad3f-150">Leave accrual for a single company or a single plan</span></span>
- <span data-ttu-id="aad3f-151">Suspensión de acumulación de permisos y ausencias</span><span class="sxs-lookup"><span data-stu-id="aad3f-151">Leave and absence accrual suspension</span></span>
- <span data-ttu-id="aad3f-152">Código de motivo de ajuste de saldo y comentario</span><span class="sxs-lookup"><span data-stu-id="aad3f-152">Balance adjustment reason code and comment</span></span>
- <span data-ttu-id="aad3f-153">Comprar y vender bajas</span><span class="sxs-lookup"><span data-stu-id="aad3f-153">Buy and sell leave</span></span>
- <span data-ttu-id="aad3f-154">Calendario de bajas y ausencias</span><span class="sxs-lookup"><span data-stu-id="aad3f-154">Leave and absence calendar</span></span>
- <span data-ttu-id="aad3f-155">Reglas transferibles de baja</span><span class="sxs-lookup"><span data-stu-id="aad3f-155">Leave carry-forward rules</span></span>
- <span data-ttu-id="aad3f-156">Auditoría de acumulación de bajas</span><span class="sxs-lookup"><span data-stu-id="aad3f-156">Leave accrual auditing</span></span>
- <span data-ttu-id="aad3f-157">Eliminación de acumulaciones de bajas</span><span class="sxs-lookup"><span data-stu-id="aad3f-157">Leave accrual deletion</span></span>
- <span data-ttu-id="aad3f-158">Redondeo de acumulación de bajas</span><span class="sxs-lookup"><span data-stu-id="aad3f-158">Leave accrual rounding</span></span>
- <span data-ttu-id="aad3f-159">Configurar varios tipos de baja en un solo plan de bajas</span><span class="sxs-lookup"><span data-stu-id="aad3f-159">Configure multiple leave types on a single leave plan</span></span>
- <span data-ttu-id="aad3f-160">Actualizar mejoras de permiso</span><span class="sxs-lookup"><span data-stu-id="aad3f-160">Update time-off enhancements</span></span>
- <span data-ttu-id="aad3f-161">Usar FTE de un empleado para acumulaciones</span><span class="sxs-lookup"><span data-stu-id="aad3f-161">Use an employee's FTE for accruals</span></span>
- <span data-ttu-id="aad3f-162">Vista de compensación entre empresas</span><span class="sxs-lookup"><span data-stu-id="aad3f-162">Cross company compensation view</span></span>
- <span data-ttu-id="aad3f-163">Imprimir evaluaciones del rendimiento</span><span class="sxs-lookup"><span data-stu-id="aad3f-163">Print performance reviews</span></span>
- <span data-ttu-id="aad3f-164">Correcciones de vacaciones de acumulación de bajas</span><span class="sxs-lookup"><span data-stu-id="aad3f-164">Leave accrual holiday corrections</span></span>

### <a name="benefit-plan-employee-entity"></a><span data-ttu-id="aad3f-165">Entidad de empleados del plan de prestaciones</span><span class="sxs-lookup"><span data-stu-id="aad3f-165">Benefit plan employee entity</span></span> 

<span data-ttu-id="aad3f-166">Recientemente hemos descubierto dos problemas relacionados con la entidad **BenefitsPlanEmployee**.</span><span class="sxs-lookup"><span data-stu-id="aad3f-166">We have recently discovered two issues regarding the **BenefitsPlanEmployee** entity.</span></span> <span data-ttu-id="aad3f-167">Al importar inscripciones de trabajadores, el **Código de cobertura** y el **Código de tipo de plan** se están configurando incorrectamente.</span><span class="sxs-lookup"><span data-stu-id="aad3f-167">When importing worker enrollments, the **Coverage code** and the **Plan type code** are being set incorrectly.</span></span> <span data-ttu-id="aad3f-168">Este problema hace que los planes de beneficios para empleados se muestren incorrectamente en el formulario **Plan de beneficios para trabajadores** y en el formulario **Inscripción abierta** en el Autoservicio para empleados.</span><span class="sxs-lookup"><span data-stu-id="aad3f-168">This issue causes employee benefit plans to display incorrectly in the **Worker benefits plan** form and in the **Open enrollment** form in Employee self service.</span></span> <span data-ttu-id="aad3f-169">Este problema también puede afectar la capacidad del empleado para seleccionar planes en el Autoservicio del empleado.</span><span class="sxs-lookup"><span data-stu-id="aad3f-169">This issue can also impact the employee's ability to select plans in Employee self service.</span></span> <span data-ttu-id="aad3f-170">Actualmente no existe una solución alternativa.</span><span class="sxs-lookup"><span data-stu-id="aad3f-170">Currently there isn't a workaround.</span></span> <span data-ttu-id="aad3f-171">Estamos tratando esto como una solución de alta prioridad y la implementaremos con nuestra próxima versión.</span><span class="sxs-lookup"><span data-stu-id="aad3f-171">We're treating this as a high-priority fix and will roll out the fix with our next release.</span></span>

## <a name="see-also"></a><span data-ttu-id="aad3f-172">Consulte también</span><span class="sxs-lookup"><span data-stu-id="aad3f-172">See also</span></span>

[<span data-ttu-id="aad3f-173">Novedades y cambios en Human Resources</span><span class="sxs-lookup"><span data-stu-id="aad3f-173">What's new or changed in Human Resources</span></span>](hr-admin-whats-new.md)</br>
[<span data-ttu-id="aad3f-174">Visión general de Dynamics 365 Human Resources 2019 en el segundo lanzamiento de versiones</span><span class="sxs-lookup"><span data-stu-id="aad3f-174">Overview of Dynamics 365 Human Resources 2019 release wave 2</span></span>](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[<span data-ttu-id="aad3f-175">Actualizar proceso</span><span class="sxs-lookup"><span data-stu-id="aad3f-175">Update process</span></span>](hr-admin-setup-update-process.md)</br>
[<span data-ttu-id="aad3f-176">Administrar características</span><span class="sxs-lookup"><span data-stu-id="aad3f-176">Manage features</span></span>](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]