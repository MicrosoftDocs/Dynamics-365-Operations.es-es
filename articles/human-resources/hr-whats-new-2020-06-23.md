---
title: Novedades o cambios en Dynamics 365 Human Resources (25 de junio de 2020)
description: Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Human Resources.
author: Darinkramer
manager: AnnBe
ms.date: 6/25/2020
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
ms.author: dkrame
ms.search.validFrom: 2020-06-25
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 8d83268292ac65d62cbe8fa9a4c146bf4af36b50
ms.sourcegitcommit: bd9ff0d28718d535356ffbe1cffaaf60310dd430
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/13/2020
ms.locfileid: "3555036"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-june-23-2020"></a><span data-ttu-id="a801b-103">Novedades o cambios en Dynamics 365 Human Resources (23 de junio de 2020)</span><span class="sxs-lookup"><span data-stu-id="a801b-103">What's new or changed in Dynamics 365 Human Resources (June 23, 2020)</span></span>

<span data-ttu-id="a801b-104">Este tema describe las funciones que son nuevas o que se han cambiado en Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="a801b-104">This topic describes features that are either new or changed in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="a801b-105">Los cambios se aplican al número de compilación 8.1.3347.</span><span class="sxs-lookup"><span data-stu-id="a801b-105">Changes apply to build number 8.1.3347.</span></span> <span data-ttu-id="a801b-106">Los números entre paréntesis en algunos encabezados hacen referencia a los números de soporte en (LCS) para su referencia.</span><span class="sxs-lookup"><span data-stu-id="a801b-106">The numbers in parentheses in some headings refer to LCS support numbers for reference.</span></span>

## <a name="when-an-enrollment-is-expired-for-a-terminated-employee-the-leave-type-balance-and-amount-are-all-cleared-in-the-leave-enrollment-form-444867"></a><span data-ttu-id="a801b-107">Cuando una inscripción expira para un empleado despedido, el tipo de baja, el saldo y la cantidad se borran en el formulario de inscripción de licencia (444867)</span><span class="sxs-lookup"><span data-stu-id="a801b-107">When an enrollment is expired for a terminated employee, the leave type, balance, and amount are all cleared in the Leave enrollment form (444867)</span></span>

<span data-ttu-id="a801b-108">Los valores en **Tipo de baja**, **Saldo** y **Cantidad** ahora se mantienen en lugar de borrarse al hacer esta selección.</span><span class="sxs-lookup"><span data-stu-id="a801b-108">Values in the **Leave type**, **Balance**, and **Amount** are now maintained instead of cleared upon making this selection.</span></span>

## <a name="incorrect-forecasted-balance-when-new-feature-leave-accrual-for-a-single-company-or-a-single-plan-is-enabled-456553"></a><span data-ttu-id="a801b-109">Saldo pronosticado incorrecto cuando se habilita la nueva función (Dejar acumulación para una sola compañía o un solo plan) (456553)</span><span class="sxs-lookup"><span data-stu-id="a801b-109">Incorrect forecasted balance when new feature (Leave accrual for a single company or a single plan) is enabled (456553)</span></span>

<span data-ttu-id="a801b-110">El saldo pronosticado correcto ahora aparece cuando la acumulación de baja para una sola compañía o un solo plan se han habilitado.</span><span class="sxs-lookup"><span data-stu-id="a801b-110">The correct forecasted balance now displays when the leave accrual for a single company or single plan has been enabled.</span></span>

## <a name="entities-with-relations-that-result-in-duplicate-navigation-properties-456486"></a><span data-ttu-id="a801b-111">Entidades con relaciones que dan como resultado propiedades de navegación duplicadas (456486)</span><span class="sxs-lookup"><span data-stu-id="a801b-111">Entities with relations that result in duplicate navigation properties (456486)</span></span>

<span data-ttu-id="a801b-112">Esta versión corrige un problema con las propiedades de navegación (relación) de varias entidades.</span><span class="sxs-lookup"><span data-stu-id="a801b-112">This release corrects an issue with the navigation properties (relation) of multiple entities.</span></span> <span data-ttu-id="a801b-113">Se detectan relaciones duplicadas.</span><span class="sxs-lookup"><span data-stu-id="a801b-113">Duplicate relations are detected.</span></span> <span data-ttu-id="a801b-114">Todos estos escenarios han sido corregidos.</span><span class="sxs-lookup"><span data-stu-id="a801b-114">These scenarios have all been corrected.</span></span>
 
## <a name="cross-company-comments-on-performance-review-455536"></a><span data-ttu-id="a801b-115">Comentarios entre empresas sobre la evaluación del rendimiento (455536)</span><span class="sxs-lookup"><span data-stu-id="a801b-115">Cross-company comments on Performance review (455536)</span></span>

<span data-ttu-id="a801b-116">Los comentarios entre empresas ahora son visibles en las revisiones de rendimiento con esta solución.</span><span class="sxs-lookup"><span data-stu-id="a801b-116">Cross-company comments are now visible on performance reviews with this fix.</span></span> <span data-ttu-id="a801b-117">Este cambio corrige la vista de los comentarios de los revisores que se ingresaron en diferentes compañías para la misma revisión de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="a801b-117">This change corrects the view of reviewer comments that were entered in different companies for the same performance review.</span></span>
 
## <a name="inconsistency-in-showing-compensation-management-data-432562"></a><span data-ttu-id="a801b-118">Inconsistencia en mostrar datos de gestión de compensación (432562)</span><span class="sxs-lookup"><span data-stu-id="a801b-118">Inconsistency in showing compensation management data (432562)</span></span>

<span data-ttu-id="a801b-119">Ahora se mantiene una vista coherente de los datos de compensación en el autoservicio de Manager.</span><span class="sxs-lookup"><span data-stu-id="a801b-119">A consistent view of compensation data is now maintained in Manager self service.</span></span> <span data-ttu-id="a801b-120">Dependiendo de cómo navegue a los **Detalles de compensación** de un trabajador, los datos de compensación ahora se muestran constantemente a los gerentes.</span><span class="sxs-lookup"><span data-stu-id="a801b-120">Depending on how you navigate to a worker's **Compensation details**, compensation data now consistently displays to managers.</span></span>
 
## <a name="fixed-compensation-plans-effective-date-defaults-to-todays-date-411994"></a><span data-ttu-id="a801b-121">La fecha de vigencia fija del plan de compensación es la fecha de hoy (411994)</span><span class="sxs-lookup"><span data-stu-id="a801b-121">Fixed compensation plan's effective date defaults to today's date (411994)</span></span>

<span data-ttu-id="a801b-122">La fecha de inicio de la compensación ahora se basa en la fecha de inicio del puesto asignado al empleado.</span><span class="sxs-lookup"><span data-stu-id="a801b-122">The compensation start date is now based on the start date of the position being assigned to the employee.</span></span>

## <a name="leave-and-absence-form-enable-half-day-definition-is-disabled-when-form-opens-452607"></a><span data-ttu-id="a801b-123">El formulario de baja y ausencia Habilitar la definición de medio día se desactiva cuando se abre el formulario (452607)</span><span class="sxs-lookup"><span data-stu-id="a801b-123">Leave and absence form Enable half day definition is disabled when form opens (452607)</span></span>

<span data-ttu-id="a801b-124">Con este cambio, **Habilitar definición de medio día** se habilitará hasta que existan nuevas transacciones de baja.</span><span class="sxs-lookup"><span data-stu-id="a801b-124">With this change, the **Enable half day definition** will be enabled until new leave transactions exist.</span></span> 

## <a name="unable-to-publish-to-hcmdiscussionentity-via-excel-totalratingscore-field-error-453899"></a><span data-ttu-id="a801b-125">No se puede publicar en HcmDiscussionEntity a través de Excel; Error de campo TotalRatingScore (453899)</span><span class="sxs-lookup"><span data-stu-id="a801b-125">Unable to publish to HcmDiscussionEntity via Excel; TotalRatingScore field error (453899)</span></span>

<span data-ttu-id="a801b-126">Ahora puede actualizar el campo **TotalRatingScore** usando **HCMDiscussionEntity** en el diseñador de libros de Excel.</span><span class="sxs-lookup"><span data-stu-id="a801b-126">You can now update the **TotalRatingScore** field using **HCMDiscussionEntity** in the Excel workbook designer.</span></span>

## <a name="in-preview"></a><span data-ttu-id="a801b-127">En vista previa</span><span class="sxs-lookup"><span data-stu-id="a801b-127">In preview</span></span>

## <a name="database-logging"></a><span data-ttu-id="a801b-128">Registro de base de datos</span><span class="sxs-lookup"><span data-stu-id="a801b-128">Database logging</span></span>

<span data-ttu-id="a801b-129">El registro de la base de datos le permite determinar qué tablas y campos se supervisan.</span><span class="sxs-lookup"><span data-stu-id="a801b-129">Database logging allows you to determine which tables and fields to monitor.</span></span> <span data-ttu-id="a801b-130">También le permite determinar los eventos que deberían activar el seguimiento de cambios.</span><span class="sxs-lookup"><span data-stu-id="a801b-130">It also lets you determine the events that should trigger change tracking.</span></span> <span data-ttu-id="a801b-131">Utiliza las capacidades de registro de bases de datos para ver estos cambios a lo largo del tiempo.</span><span class="sxs-lookup"><span data-stu-id="a801b-131">You use database logging capabilities to see these changes over time.</span></span> <span data-ttu-id="a801b-132">Para más información, vea [Configurar y administrar el registro de bases de datos](hr-admin-database-logging.md).</span><span class="sxs-lookup"><span data-stu-id="a801b-132">For more information, see [Configure and manage database logging](hr-admin-database-logging.md).</span></span>

## <a name="mandatory-fields"></a><span data-ttu-id="a801b-133">Campos obligatorios</span><span class="sxs-lookup"><span data-stu-id="a801b-133">Mandatory fields</span></span> 

<span data-ttu-id="a801b-134">Ahora puede hacer que los campos sean obligatorios utilizando las capacidades de personalización de Human Resources.</span><span class="sxs-lookup"><span data-stu-id="a801b-134">You can now make fields mandatory by using Human Resources personalization capabilities.</span></span> <span data-ttu-id="a801b-135">Esta característica requiere **Vistas guardadas**.</span><span class="sxs-lookup"><span data-stu-id="a801b-135">This feature requires **Saved views**.</span></span>

## <a name="human-resources-application-in-teams"></a><span data-ttu-id="a801b-136">Aplicación Human Resources en Teams</span><span class="sxs-lookup"><span data-stu-id="a801b-136">Human Resources application in Teams</span></span>

<span data-ttu-id="a801b-137">Los empleados pueden ver y solicitar tiempo fuera del trabajo en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a801b-137">Employees can view and request time away from work within Microsoft Teams.</span></span> <span data-ttu-id="a801b-138">Pueden interactuar con un bot para crear solicitudes de baja.</span><span class="sxs-lookup"><span data-stu-id="a801b-138">They can interact with a bot to create leave requests.</span></span> <span data-ttu-id="a801b-139">Para más información, consulte [Aplicación de recursos humanos en Teams](https://go.microsoft.com/fwlink/?linkid=2127841).</span><span class="sxs-lookup"><span data-stu-id="a801b-139">For more information, see [Human Resources app in Teams](https://go.microsoft.com/fwlink/?linkid=2127841).</span></span> 

## <a name="data-management-framework-dmf-entities-for-benefits-management"></a><span data-ttu-id="a801b-140">Entidades del marco de gestión de datos (DMF) para la gestión de ventajas</span><span class="sxs-lookup"><span data-stu-id="a801b-140">Data management framework (DMF) entities for Benefits management</span></span>
 
<span data-ttu-id="a801b-141">Las entidades de gestión de ventajas se están lanzando.</span><span class="sxs-lookup"><span data-stu-id="a801b-141">Benefits management entities are releasing.</span></span> <span data-ttu-id="a801b-142">Las entidades DMF le permite importar y exportar datos para configurar fácilmente la gestión de ventajas.</span><span class="sxs-lookup"><span data-stu-id="a801b-142">DMF entities allow you to import and export data to easily configure benefits management.</span></span> <span data-ttu-id="a801b-143">Una plantilla de gestión de ventajas estará disponible para mover datos.</span><span class="sxs-lookup"><span data-stu-id="a801b-143">A Benefits management template will be available to move data.</span></span> <span data-ttu-id="a801b-144">La plantilla exporta e importa los datos de manera secuencial para respetar las dependencias de datos.</span><span class="sxs-lookup"><span data-stu-id="a801b-144">The template exports and imports the data sequentially to respect data dependencies.</span></span>

## <a name="buy-and-sell-leave"></a><span data-ttu-id="a801b-145">Comprar y vender bajas</span><span class="sxs-lookup"><span data-stu-id="a801b-145">Buy and sell leave</span></span> 

<span data-ttu-id="a801b-146">Algunas organizaciones ofrecen un beneficio que permite a los empleados comprar o vender su baja.</span><span class="sxs-lookup"><span data-stu-id="a801b-146">Some organizations provide a benefit that allows employees to buy or sell their leave.</span></span> <span data-ttu-id="a801b-147">Este proceso a menudo se gestiona manualmente.</span><span class="sxs-lookup"><span data-stu-id="a801b-147">This process is often managed manually.</span></span> <span data-ttu-id="a801b-148">Esta característica automatiza las políticas de gestión y las solicitudes del departamento de recursos humanos.</span><span class="sxs-lookup"><span data-stu-id="a801b-148">This feature automates managing policies and requests for the HR department.</span></span> <span data-ttu-id="a801b-149">Agiliza el proceso de gestión de licencias y ayuda a eliminar errores.</span><span class="sxs-lookup"><span data-stu-id="a801b-149">It streamlines the leave management process and helps eliminate mistakes.</span></span> <span data-ttu-id="a801b-150">Para obtener más información, consulte:</span><span class="sxs-lookup"><span data-stu-id="a801b-150">For more information, see:</span></span>

- [<span data-ttu-id="a801b-151">Gestionar directivas de compra y venta de bajas</span><span class="sxs-lookup"><span data-stu-id="a801b-151">Manage buy and sell leave policies</span></span>](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)
- [<span data-ttu-id="a801b-152">Comprar y vender bajas</span><span class="sxs-lookup"><span data-stu-id="a801b-152">Buy and sell leave</span></span>](hr-employee-self-service-buy-sell-leave.md)

## <a name="leave-accrual-for-a-single-company-or-single-plan"></a><span data-ttu-id="a801b-153">Acumulación de bajas para una sola compañía o plan único</span><span class="sxs-lookup"><span data-stu-id="a801b-153">Leave accrual for a single company or single plan</span></span>

<span data-ttu-id="a801b-154">Los clientes pueden procesar las acumulaciones para una sola compañía o un solo plan de licencia y ausencias.</span><span class="sxs-lookup"><span data-stu-id="a801b-154">Customers can process accruals for a single company or a single leave and absence plan.</span></span> <span data-ttu-id="a801b-155">Esta capacidad proporciona transparencia en el proceso de acumulación para clientes con diferentes años de baja o directivas de acumulación de bajas.</span><span class="sxs-lookup"><span data-stu-id="a801b-155">This ability provides clarity into the accrual process for customers with different leave years or leave accrual policies.</span></span> <span data-ttu-id="a801b-156">Para más información, consulte [Acumular bajas por empresa o por plan de licencia](hr-leave-and-absence-accrue.md#accrue-leave-per-company-or-per-leave-plan).</span><span class="sxs-lookup"><span data-stu-id="a801b-156">For more information, see [Accrue leave per company or per leave plan](hr-leave-and-absence-accrue.md#accrue-leave-per-company-or-per-leave-plan).</span></span>

## <a name="add-attachments-to-time-off-requests"></a><span data-ttu-id="a801b-157">Agregar archivos adjuntos a las solicitudes de tiempo libre</span><span class="sxs-lookup"><span data-stu-id="a801b-157">Add attachments to time off requests</span></span>

<span data-ttu-id="a801b-158">La capacidad de agregar archivos adjuntos a las solicitudes de baja aprobadas es crítica en el entorno actual de COVID-19.</span><span class="sxs-lookup"><span data-stu-id="a801b-158">The ability to add attachments to approved leave requests is critical in the current COVID-19 environment.</span></span> <span data-ttu-id="a801b-159">Los empleados ahora pueden agregar estos archivos adjuntos.</span><span class="sxs-lookup"><span data-stu-id="a801b-159">Employees can now add these attachments.</span></span> <span data-ttu-id="a801b-160">También tienen más información sobre cómo se realizan las actualizaciones para las solicitudes de baja.</span><span class="sxs-lookup"><span data-stu-id="a801b-160">They also have more insight into how updates are made to leave requests.</span></span> <span data-ttu-id="a801b-161">Para más información, vea [Agregar un archivo adjunto a una solicitud existente](hr-employee-self-service-request-time-off.md#add-an-attachment-to-an-existing-request).</span><span class="sxs-lookup"><span data-stu-id="a801b-161">For more information, see [Add an attachment to an existing request](hr-employee-self-service-request-time-off.md#add-an-attachment-to-an-existing-request).</span></span>

## <a name="add-reason-code-to-accrual-suspensions"></a><span data-ttu-id="a801b-162">Agregar código de razón a las suspensiones acumuladas</span><span class="sxs-lookup"><span data-stu-id="a801b-162">Add reason code to accrual suspensions</span></span> 

<span data-ttu-id="a801b-163">Se han agregado códigos de motivo a la suspensión acumulada.</span><span class="sxs-lookup"><span data-stu-id="a801b-163">Reason codes have been added to the accrual suspension.</span></span>

## <a name="carry-forward-rules"></a><span data-ttu-id="a801b-164">Transferir reglas</span><span class="sxs-lookup"><span data-stu-id="a801b-164">Carry forward rules</span></span> 

<span data-ttu-id="a801b-165">Puede especificar un tipo de transferencia de baja para transferir saldos en los que los ajustes de transferencia se traspasan.</span><span class="sxs-lookup"><span data-stu-id="a801b-165">You can specify a carry forward leave type for carry forward balances where carry forward adjustments are transferred.</span></span> <span data-ttu-id="a801b-166">Por ejemplo, si un empleado adelanta 10 días, puede elegir un tipo de baja diferente para esos 10 días.</span><span class="sxs-lookup"><span data-stu-id="a801b-166">For example, if an employee carries forward 10 days, you can pick a different leave type for those 10 days.</span></span> <span data-ttu-id="a801b-167">Para más información, ver [Configurar tipos de baja y ausencia](hr-leave-and-absence-types.md).</span><span class="sxs-lookup"><span data-stu-id="a801b-167">For more information, see [Configure leave and absence types](hr-leave-and-absence-types.md).</span></span>

## <a name="suspend-leave-accrual-for-specified-leave-types"></a><span data-ttu-id="a801b-168">Suspender la acumulación de bajas para los tipos de baja especificados</span><span class="sxs-lookup"><span data-stu-id="a801b-168">Suspend leave accrual for specified leave types</span></span>

<span data-ttu-id="a801b-169">Puede crear una regla para suspender la acumulación de bajas para empleados con solicitudes de bajas introducidas para bajas no pagadas.</span><span class="sxs-lookup"><span data-stu-id="a801b-169">You can create a rule to suspend leave accruals for employees with leave requests entered for unpaid leave.</span></span> <span data-ttu-id="a801b-170">La baja no remunerada puede ser un tipo, pero no tiene por qué serlo.</span><span class="sxs-lookup"><span data-stu-id="a801b-170">Unpaid leave can be a type, but doesn't have to be.</span></span> <span data-ttu-id="a801b-171">Puede suspender cualquier baja basada en otro tipo de baja.</span><span class="sxs-lookup"><span data-stu-id="a801b-171">You can suspend any leave based on another leave type.</span></span>

## <a name="dmf-entity-available-for-accrual-suspensions"></a><span data-ttu-id="a801b-172">Entidad DMF disponible para suspensiones acumuladas</span><span class="sxs-lookup"><span data-stu-id="a801b-172">DMF entity available for accrual suspensions</span></span> 

<span data-ttu-id="a801b-173">Ahora está disponible una entidad DMF para suspensiones acumuladas.</span><span class="sxs-lookup"><span data-stu-id="a801b-173">A DMF entity is now available for accrual suspensions.</span></span>

## <a name="coming-soon"></a><span data-ttu-id="a801b-174">Próximamente</span><span class="sxs-lookup"><span data-stu-id="a801b-174">Coming soon</span></span>

## <a name="configure-the-name-of-employee-self-service"></a><span data-ttu-id="a801b-175">Configurar el nombre de Autoservicio para empleados</span><span class="sxs-lookup"><span data-stu-id="a801b-175">Configure the name of Employee self-service</span></span>

<span data-ttu-id="a801b-176">Una nueva opción estará disponible en los **parámetros de Human Resources** para actualizar el nombre del espacio de trabajo de autoservicio del empleado a Autoservicio.</span><span class="sxs-lookup"><span data-stu-id="a801b-176">A new option will be available in **Human Resources parameters** to update the name of the Employee self service workspace to Self service.</span></span>

## <a name="checklist-entities-included-in-common-data-service"></a><span data-ttu-id="a801b-177">Lista de entidades incluidas en Common Data Service</span><span class="sxs-lookup"><span data-stu-id="a801b-177">Checklist entities included in Common Data Service</span></span>

<span data-ttu-id="a801b-178">Las entidades de lista de verificación para los procesos de incorporación, retirada, transferencias y negocios estarán disponibles pronto dentro de Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="a801b-178">Checklist entities for Onboarding, Offboarding, Transfers, and Business processes will be available soon within Common Data Service.</span></span>

## <a name="see-also"></a><span data-ttu-id="a801b-179">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a801b-179">See also</span></span>

[<span data-ttu-id="a801b-180">Novedades y cambios en Human Resources</span><span class="sxs-lookup"><span data-stu-id="a801b-180">What's new or changed in Human Resources</span></span>](hr-admin-whats-new.md)</br>
[<span data-ttu-id="a801b-181">Visión general de Dynamics 365 Human Resources 2019 en el segundo lanzamiento de versiones</span><span class="sxs-lookup"><span data-stu-id="a801b-181">Overview of Dynamics 365 Human Resources 2019 release wave 2</span></span>](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[<span data-ttu-id="a801b-182">Actualizar proceso</span><span class="sxs-lookup"><span data-stu-id="a801b-182">Update process</span></span>](hr-admin-setup-update-process.md)</br>
[<span data-ttu-id="a801b-183">Administrar características</span><span class="sxs-lookup"><span data-stu-id="a801b-183">Manage features</span></span>](hr-admin-manage-features.md)