---
title: Novedades y cambios en Dynamics 365 Human Resources (28 de mayo de 2020)
description: Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Human Resources para el 28 de mayo de 2020.
author: andreabichsel
ms.date: 05/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-05-28
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d5396e24f036e670ce276911cd3582442a98da7f
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/18/2021
ms.locfileid: "6054341"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-may-28-2020"></a><span data-ttu-id="97a68-103">Novedades y cambios en Dynamics 365 Human Resources (28 de mayo de 2020)</span><span class="sxs-lookup"><span data-stu-id="97a68-103">What's new or changed in Dynamics 365 Human Resources (May 28, 2020)</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="97a68-104">Este tema describe las características que son nuevas o que se han cambiado en Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="97a68-104">This topic describes features that are either new or changed in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="97a68-105">Los cambios se aplican al número de compilación 8.1.3287.</span><span class="sxs-lookup"><span data-stu-id="97a68-105">Changes apply to build number 8.1.3287.</span></span> <span data-ttu-id="97a68-106">Los números entre paréntesis en algunos encabezados hacen referencia a los números de soporte en (LCS) para su referencia.</span><span class="sxs-lookup"><span data-stu-id="97a68-106">The numbers in parentheses in some headings refer to LCS support numbers for reference.</span></span>

## <a name="leaverequest-entity-doesnt-work-when-you-enable-multiple-types-per-leave-plan-447498"></a><span data-ttu-id="97a68-107">La entidad LeaveRequest no funciona cuando se habilitan varios tipos por plan de baja (447498)</span><span class="sxs-lookup"><span data-stu-id="97a68-107">LeaveRequest entity doesn't work when you enable multiple types per leave plan (447498)</span></span>

<span data-ttu-id="97a68-108">Con este cambio, **LeaveEnrollmentV2Entity** ya está disponible para corregir el error que ocurre cuando habilita varios tipos de licencia.</span><span class="sxs-lookup"><span data-stu-id="97a68-108">With this change, the **LeaveEnrollmentV2Entity** is now available to correct the error that occurs when you enable multiple leave types.</span></span>

## <a name="batch-contention-reduction-feature-preview-446619"></a><span data-ttu-id="97a68-109">Función de reducción de contención por lotes (vista previa) (446619)</span><span class="sxs-lookup"><span data-stu-id="97a68-109">Batch contention reduction feature (preview) (446619)</span></span>

<span data-ttu-id="97a68-110">Cuando habilita esta característica, puede esperar una reducción en el bloqueo de las tablas del marco de trabajo por lotes al seleccionar tareas y finalizar trabajos.</span><span class="sxs-lookup"><span data-stu-id="97a68-110">When you enable this feature, you can expect a reduction in blocking on batch framework tables while selecting tasks and finishing jobs.</span></span>

## <a name="updateconflict-while-saving-worker-prevents-editing-a-record-in-people-427915"></a><span data-ttu-id="97a68-111">UpdateConflict al guardar el trabajador impide editar un registro en Personas (427915)</span><span class="sxs-lookup"><span data-stu-id="97a68-111">UpdateConflict while saving worker prevents editing a record in People (427915)</span></span>

<span data-ttu-id="97a68-112">Este cambio corrige un error al agregar un nuevo trabajador, actualizar la información de la dirección y cambiar las preferencias de idioma.</span><span class="sxs-lookup"><span data-stu-id="97a68-112">This change corrects an error when adding a new worker, updating address information, and changing language preference.</span></span> <span data-ttu-id="97a68-113">En este escenario único, apareció un error que indica que el registro no se pudo actualizar.</span><span class="sxs-lookup"><span data-stu-id="97a68-113">In this unique scenario, an error displayed indicating the record couldn't be updated.</span></span> 

## <a name="unable-to-add-an-attachment-to-an-approved-leave-request-to-resubmit-425407"></a><span data-ttu-id="97a68-114">No se puede agregar un archivo adjunto a una solicitud de baja aprobada para volver a enviarla (425407)</span><span class="sxs-lookup"><span data-stu-id="97a68-114">Unable to add an attachment to an approved leave request to resubmit (425407)</span></span>

<span data-ttu-id="97a68-115">Este cambio ahora permite adjuntos con las solicitudes de baja aprobadas.</span><span class="sxs-lookup"><span data-stu-id="97a68-115">This change now allows attachments to approved leave requests.</span></span>

## <a name="user-can-enter-compensation-for-an-employee-in-a-different-legal-entity-form-409529"></a><span data-ttu-id="97a68-116">El usuario puede introducir una compensación para un empleado en un formulario de entidad legal diferente (409529)</span><span class="sxs-lookup"><span data-stu-id="97a68-116">User can enter compensation for an employee in a different legal entity form (409529)</span></span>

<span data-ttu-id="97a68-117">Este cambio desactiva las opciones de compensación para evitar la entrada accidental de registros de compensación para la entidad jurídica incorrecta.</span><span class="sxs-lookup"><span data-stu-id="97a68-117">This change disables compensation options to prevent inadvertent entry of compensation records for the wrong legal entity.</span></span>

## <a name="error-when-you-transfer-an-employee-and-the-worker-position-assignment-date-is-before-the-position-duration-429402"></a><span data-ttu-id="97a68-118">Error cuando se transfiere a un empleado y la fecha de asignación del puesto de trabajador es anterior a la duración del puesto (429402)</span><span class="sxs-lookup"><span data-stu-id="97a68-118">Error when you transfer an employee and the Worker position assignment date is before the position duration (429402)</span></span>

<span data-ttu-id="97a68-119">Los mensajes de error al transferir a un empleado en este escenario se han actualizado para describir mejor los cambios necesarios para corregir el problema.</span><span class="sxs-lookup"><span data-stu-id="97a68-119">Error messages when transferring an employee in this scenario have been updated to better describe the changes needed to correct the problem.</span></span>

## <a name="attachments-capabilities-in-employee-self-service-benefits-enrollment"></a><span data-ttu-id="97a68-120">Capacidades de archivos adjuntos en la inscripción de beneficios de autoservicio para empleados</span><span class="sxs-lookup"><span data-stu-id="97a68-120">Attachments capabilities in Employee self service benefits enrollment</span></span>
 
<span data-ttu-id="97a68-121">Ahora puede agregar archivos adjuntos durante el proceso de inscripción de beneficios para cada plan en el que se inscribe el empleado.</span><span class="sxs-lookup"><span data-stu-id="97a68-121">Now you can add attachments during the benefits enrollment process for each plan that the employee's enrolling in.</span></span> <span data-ttu-id="97a68-122">Entonces puede ver los archivos adjuntos dentro del formulario **Ventaja de trabajador inscrito**.</span><span class="sxs-lookup"><span data-stu-id="97a68-122">You can then view the attachments within the **Worker enrolled benefit** form.</span></span>

## <a name="in-preview"></a><span data-ttu-id="97a68-123">En vista previa</span><span class="sxs-lookup"><span data-stu-id="97a68-123">In preview</span></span>

## <a name="human-resources-application-in-teams"></a><span data-ttu-id="97a68-124">Aplicación Human Resources en Teams</span><span class="sxs-lookup"><span data-stu-id="97a68-124">Human Resources application in Teams</span></span>

<span data-ttu-id="97a68-125">Los empleados pueden ver y solicitar tiempo fuera del trabajo en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="97a68-125">Employees can view and request time away from work within Microsoft Teams.</span></span> <span data-ttu-id="97a68-126">Pueden interactuar con un bot para crear solicitudes de baja.</span><span class="sxs-lookup"><span data-stu-id="97a68-126">They can interact with a bot to create leave requests.</span></span> <span data-ttu-id="97a68-127">Para más información, consulte [Aplicación de recursos humanos en Teams](./hr-admin-teams-leave-app.md).</span><span class="sxs-lookup"><span data-stu-id="97a68-127">For more information, see [Human Resources app in Teams](./hr-admin-teams-leave-app.md).</span></span> 

## <a name="leave-suspension"></a><span data-ttu-id="97a68-128">Dejar suspensión</span><span class="sxs-lookup"><span data-stu-id="97a68-128">Leave suspension</span></span>

<span data-ttu-id="97a68-129">Puede suspender la baja y la ausencia en Human Resources para un empleado.</span><span class="sxs-lookup"><span data-stu-id="97a68-129">You can suspend leave and absence in Human Resources for an employee.</span></span> <span data-ttu-id="97a68-130">La suspensión de la baja detiene las acumulaciones de baja para los tipos de baja seleccionados.</span><span class="sxs-lookup"><span data-stu-id="97a68-130">Suspending leave stops the leave accruals for selected leave types.</span></span> <span data-ttu-id="97a68-131">Si la suspensión ocurre después de que se ha procesado una acumulación, la suspensión de la licencia crea un ajuste prorrateado al saldo de licencia del empleado.</span><span class="sxs-lookup"><span data-stu-id="97a68-131">If the suspension occurs after an accrual has been processed, suspending leave creates a prorated adjustment to the employee's leave balance.</span></span> <span data-ttu-id="97a68-132">Para obtener más información, consulte [Suspender baja](hr-leave-and-absence-suspend-leave.md).</span><span class="sxs-lookup"><span data-stu-id="97a68-132">For more information, see [Suspend leave](hr-leave-and-absence-suspend-leave.md).</span></span>

## <a name="update-user-experience-to-indicate-that-accrual-is-suspended-429550"></a><span data-ttu-id="97a68-133">Actualizar la experiencia del usuario para indicar que la acumulación está suspendida (429550)</span><span class="sxs-lookup"><span data-stu-id="97a68-133">Update user experience to indicate that accrual is suspended (429550)</span></span>

<span data-ttu-id="97a68-134">La experiencia del usuario ahora indica que la acumulación se ha suspendido para un plan.</span><span class="sxs-lookup"><span data-stu-id="97a68-134">The user experience now indicates that the accrual has been suspended for a plan.</span></span>

## <a name="coming-soon"></a><span data-ttu-id="97a68-135">Próximamente</span><span class="sxs-lookup"><span data-stu-id="97a68-135">Coming soon</span></span>

## <a name="database-logging-in-preview-in-june"></a><span data-ttu-id="97a68-136">Registro de base de datos (en vista previa en junio)</span><span class="sxs-lookup"><span data-stu-id="97a68-136">Database logging (in preview in June)</span></span>

<span data-ttu-id="97a68-137">La característica de registro de la base de datos le permite determinar qué tabla y campos se deben monitorizar.</span><span class="sxs-lookup"><span data-stu-id="97a68-137">The database logging feature allows you to determine which table and fields should be monitored.</span></span> <span data-ttu-id="97a68-138">También le permite determinar los eventos que deberían activar el seguimiento de cambios.</span><span class="sxs-lookup"><span data-stu-id="97a68-138">It also lets you determine the events that should trigger change tracking.</span></span> <span data-ttu-id="97a68-139">Las capacidades de consulta están disponibles para ver estos cambios a lo largo del tiempo.</span><span class="sxs-lookup"><span data-stu-id="97a68-139">Inquiry capabilities are available to see these changes over time.</span></span>

## <a name="buy-and-sell-leave-in-preview-june-1"></a><span data-ttu-id="97a68-140">Comprar y vender baja (en vista previa el 1 de junio)</span><span class="sxs-lookup"><span data-stu-id="97a68-140">Buy and sell leave (in preview June 1)</span></span>

<span data-ttu-id="97a68-141">Algunas organizaciones ofrecen un beneficio que permite a los empleados comprar o vender su baja.</span><span class="sxs-lookup"><span data-stu-id="97a68-141">Some organizations provide a benefit that allows employees to buy or sell their leave.</span></span> <span data-ttu-id="97a68-142">Este proceso a menudo se gestiona manualmente.</span><span class="sxs-lookup"><span data-stu-id="97a68-142">This process is often managed manually.</span></span> <span data-ttu-id="97a68-143">Esta característica proporciona una forma más automatizada de gestionar políticas y solicitudes para el departamento de recursos humanos, y ayuda a eliminar errores al tiempo que simplifica el proceso de gestión de bajas.</span><span class="sxs-lookup"><span data-stu-id="97a68-143">This feature provides a more automated way to manage policies and requests for the HR department, and it helps eliminate mistakes while streamlining the leave management process.</span></span> <span data-ttu-id="97a68-144">Para obtener más información, consulte:</span><span class="sxs-lookup"><span data-stu-id="97a68-144">For more information, see:</span></span>

- [<span data-ttu-id="97a68-145">Gestionar directivas de compra y venta de bajas</span><span class="sxs-lookup"><span data-stu-id="97a68-145">Manage buy and sell leave policies</span></span>](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)
- [<span data-ttu-id="97a68-146">Comprar y vender bajas</span><span class="sxs-lookup"><span data-stu-id="97a68-146">Buy and sell leave</span></span>](hr-employee-self-service-buy-sell-leave.md)

## <a name="data-management-framework-dmf-entities-for-benefits-management"></a><span data-ttu-id="97a68-147">Entidades del marco de gestión de datos (DMF) para la gestión de ventajas</span><span class="sxs-lookup"><span data-stu-id="97a68-147">Data management framework (DMF) entities for Benefits management</span></span>
 
<span data-ttu-id="97a68-148">Las entidades de gestión de ventajas se están lanzando.</span><span class="sxs-lookup"><span data-stu-id="97a68-148">Benefits management entities are releasing.</span></span> <span data-ttu-id="97a68-149">Las entidades DMF permiten importar y exportar datos para configurar fácilmente la gestión de ventajas.</span><span class="sxs-lookup"><span data-stu-id="97a68-149">DMF entities allow importing and exporting data to easily configure benefits management.</span></span> <span data-ttu-id="97a68-150">Una plantilla de gestión de ventajas también estará disponible para mover datos.</span><span class="sxs-lookup"><span data-stu-id="97a68-150">A Benefits management template will also be available to move data.</span></span> <span data-ttu-id="97a68-151">La plantilla exporta e importa los datos de manera secuencial para respetar las dependencias de datos.</span><span class="sxs-lookup"><span data-stu-id="97a68-151">The template exports and imports the data in a sequential manner to respect data dependencies.</span></span>

## <a name="add-reason-code-to-accrual-suspensions-june-1"></a><span data-ttu-id="97a68-152">Agregar código de razón a las suspensiones acumuladas (1 de junio)</span><span class="sxs-lookup"><span data-stu-id="97a68-152">Add reason code to accrual suspensions (June 1)</span></span>

<span data-ttu-id="97a68-153">Se han agregado códigos de motivo a la suspensión acumulada.</span><span class="sxs-lookup"><span data-stu-id="97a68-153">Reason codes have been added to the accrual suspension.</span></span>

## <a name="carry-forward-rules-june-1"></a><span data-ttu-id="97a68-154">Reglas de transferencia (1 de junio)</span><span class="sxs-lookup"><span data-stu-id="97a68-154">Carry forward rules (June 1)</span></span>

<span data-ttu-id="97a68-155">Puede especificar un tipo de transferencia de baja para transferir saldos en los que los ajustes de transferencia se traspasan.</span><span class="sxs-lookup"><span data-stu-id="97a68-155">You can specify a carry forward leave type for carry forward balances where carry forward adjustments are transferred.</span></span> <span data-ttu-id="97a68-156">Por ejemplo, si un empleado adelanta 10 días, puede elegir un tipo de baja diferente para esos 10 días.</span><span class="sxs-lookup"><span data-stu-id="97a68-156">For example, if an employee carries forward 10 days, you can pick a different leave type for those 10 days.</span></span> <span data-ttu-id="97a68-157">Para más información, ver [Configurar tipos de baja y ausencia](hr-leave-and-absence-types.md).</span><span class="sxs-lookup"><span data-stu-id="97a68-157">For more information, see [Configure leave and absence types](hr-leave-and-absence-types.md).</span></span>

## <a name="suspend-leave-accrual-for-specified-leave-types-june-1"></a><span data-ttu-id="97a68-158">Suspender la acumulación de bajas para los tipos de baja especificados (1 de junio)</span><span class="sxs-lookup"><span data-stu-id="97a68-158">Suspend leave accrual for specified leave types (June 1)</span></span>

<span data-ttu-id="97a68-159">En este comunicado, RR. HH. puede crear una regla para suspender la acumulación de bajas para empleados con solicitudes de bajas introducidas para bajas no pagadas.</span><span class="sxs-lookup"><span data-stu-id="97a68-159">In this release, HR can create a rule to suspend leave accruals for employees with leave requests entered for unpaid leave.</span></span> <span data-ttu-id="97a68-160">La baja no remunerada puede ser un tipo, pero no tiene por qué serlo.</span><span class="sxs-lookup"><span data-stu-id="97a68-160">Unpaid leave can be a type, but doesn't have to be.</span></span> <span data-ttu-id="97a68-161">Puede suspender cualquier baja basada en otro tipo de baja.</span><span class="sxs-lookup"><span data-stu-id="97a68-161">You can suspend any leave based on another leave type.</span></span>

## <a name="dmf-entity-available-for-accrual-suspensions-june-1"></a><span data-ttu-id="97a68-162">Entidad DMF disponible para suspensiones acumuladas (1 de junio)</span><span class="sxs-lookup"><span data-stu-id="97a68-162">DMF entity available for accrual suspensions (June 1)</span></span>

<span data-ttu-id="97a68-163">Ahora está disponible una entidad DMF para suspensiones acumuladas.</span><span class="sxs-lookup"><span data-stu-id="97a68-163">A DMF entity is now available for accrual suspensions.</span></span>

## <a name="see-also"></a><span data-ttu-id="97a68-164">Consulte también</span><span class="sxs-lookup"><span data-stu-id="97a68-164">See also</span></span>

[<span data-ttu-id="97a68-165">Novedades y cambios en Human Resources</span><span class="sxs-lookup"><span data-stu-id="97a68-165">What's new or changed in Human Resources</span></span>](hr-admin-whats-new.md)</br>
[<span data-ttu-id="97a68-166">Visión general de Dynamics 365 Human Resources 2019 en el segundo lanzamiento de versiones</span><span class="sxs-lookup"><span data-stu-id="97a68-166">Overview of Dynamics 365 Human Resources 2019 release wave 2</span></span>](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[<span data-ttu-id="97a68-167">Actualizar proceso</span><span class="sxs-lookup"><span data-stu-id="97a68-167">Update process</span></span>](hr-admin-setup-update-process.md)</br>
[<span data-ttu-id="97a68-168">Administrar características</span><span class="sxs-lookup"><span data-stu-id="97a68-168">Manage features</span></span>](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]