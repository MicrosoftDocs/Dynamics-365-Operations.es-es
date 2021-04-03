---
title: Novedades o cambios en Dynamics 365 Human Resources (08 de julio de 2020)
description: Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Human Resources para el 8 de julio de 2020.
author: andreabichsel
manager: tfehr
ms.date: 07/08/2020
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
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 9715f332088b7b5340f4252af5f789d226d90ff2
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/17/2021
ms.locfileid: "5463607"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-july-8-2020"></a><span data-ttu-id="d80be-103">Novedades o cambios en Dynamics 365 Human Resources (8 de julio de 2020)</span><span class="sxs-lookup"><span data-stu-id="d80be-103">What's new or changed in Dynamics 365 Human Resources (July 8, 2020)</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="d80be-104">Este tema describe las características que son nuevas o que se han cambiado en Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="d80be-104">This topic describes features that are either new or changed in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="d80be-105">Los cambios se aplican al número de compilación 8.1.3382.</span><span class="sxs-lookup"><span data-stu-id="d80be-105">Changes apply to build number 8.1.3382.</span></span> <span data-ttu-id="d80be-106">Los números entre paréntesis en algunos encabezados hacen referencia a los números de soporte en (LCS) para su referencia.</span><span class="sxs-lookup"><span data-stu-id="d80be-106">The numbers in parentheses in some headings refer to LCS support numbers for reference.</span></span>

## <a name="database-logging"></a><span data-ttu-id="d80be-107">Registro de base de datos</span><span class="sxs-lookup"><span data-stu-id="d80be-107">Database logging</span></span>

<span data-ttu-id="d80be-108">El registro de la base de datos le permite determinar qué tablas y campos se supervisan.</span><span class="sxs-lookup"><span data-stu-id="d80be-108">Database logging allows you to determine which tables and fields to monitor.</span></span> <span data-ttu-id="d80be-109">También le permite determinar los eventos que deberían activar el seguimiento de cambios.</span><span class="sxs-lookup"><span data-stu-id="d80be-109">It also lets you determine the events that should trigger change tracking.</span></span> <span data-ttu-id="d80be-110">Utiliza las capacidades de registro de bases de datos para ver estos cambios a lo largo del tiempo.</span><span class="sxs-lookup"><span data-stu-id="d80be-110">You use database logging capabilities to see these changes over time.</span></span> <span data-ttu-id="d80be-111">Para más información, vea [Configurar y administrar el registro de bases de datos](hr-admin-database-logging.md).</span><span class="sxs-lookup"><span data-stu-id="d80be-111">For more information, see [Configure and manage database logging](hr-admin-database-logging.md).</span></span>

## <a name="configure-the-name-of-employee-self-service"></a><span data-ttu-id="d80be-112">Configurar el nombre del Autoservicio para empleados</span><span class="sxs-lookup"><span data-stu-id="d80be-112">Configure the name of Employee self service</span></span>

<span data-ttu-id="d80be-113">En **Parámetros de Human Resources**, ahora puede cambiar el nombre del espacio de trabajo **Autoservicio para empleados** a **Autoservicio**.</span><span class="sxs-lookup"><span data-stu-id="d80be-113">In **Human Resources parameters**, you can now change the name of the **Employee self service** workspace to **Self service**.</span></span> <span data-ttu-id="d80be-114">Para más información, consulte [Cambiar el nombre del espacio de trabajo Autoservicio para empleados](hr-employee-self-service-workspace-name.md)</span><span class="sxs-lookup"><span data-stu-id="d80be-114">For more information, see [Change Employee self service workspace name](hr-employee-self-service-workspace-name.md)</span></span>

## <a name="benefits-management-open-enrollment-access-outside-of-period"></a><span data-ttu-id="d80be-115">Acceso a inscripción abierta de administración de prestaciones fuera del período</span><span class="sxs-lookup"><span data-stu-id="d80be-115">Benefits management open enrollment access outside of period</span></span>

<span data-ttu-id="d80be-116">Esta versión corrige un error por el cual los empleados podían acceder a la inscripción directa de prestaciones fuera del período de inscripción o sin un evento de vida.</span><span class="sxs-lookup"><span data-stu-id="d80be-116">This release fixes a bug where employees could access benefits open enrollment outside of the enrollment period or without a life event.</span></span> <span data-ttu-id="d80be-117">Como resultado, si necesita hacer una inscripción abierta de demostración en el autoservicio del empleado, debe ajustar las fechas de inscripción abiertas a hoy (o antes) para que sea accesible.</span><span class="sxs-lookup"><span data-stu-id="d80be-117">As a result, if you need to demo open enrollment in Employee self service, you must adjust the open enrollment dates to today (or earlier) to make it accessible.</span></span> <span data-ttu-id="d80be-118">Puede cambiar esta configuración en **Gestión de prestaciones > Reglas y períodos de opciones**.</span><span class="sxs-lookup"><span data-stu-id="d80be-118">You can change this setting under **Benefits management > Rules and options periods**.</span></span>

## <a name="email-employee-enrollment-confirmation"></a><span data-ttu-id="d80be-119">Confirmación de inscripción del empleado por correo electrónico</span><span class="sxs-lookup"><span data-stu-id="d80be-119">Email employee enrollment confirmation</span></span>

<span data-ttu-id="d80be-120">Ahora puede enviar correos electrónicos a los empleados después de que completen su selección de prestaciones.</span><span class="sxs-lookup"><span data-stu-id="d80be-120">You can now send emails to employees after they complete their benefits selection.</span></span> <span data-ttu-id="d80be-121">Puede enviar un mensaje predeterminado o utilizar una plantilla de correo electrónico de la organización.</span><span class="sxs-lookup"><span data-stu-id="d80be-121">You can either send a default message or use an organization email template.</span></span> <span data-ttu-id="d80be-122">Estas configuraciones están en **Parámetros de recursos humanos> Gestión de prestaciones**.</span><span class="sxs-lookup"><span data-stu-id="d80be-122">These settings are under **Human resource parameters > Benefits management**.</span></span>

## <a name="canceled-leave-still-appears-in-upcoming-time-off-on-people-workspace-441358"></a><span data-ttu-id="d80be-123">La baja cancelada aún aparece en el próximo tiempo libre del espacio de trabajo de Personas (441358)</span><span class="sxs-lookup"><span data-stu-id="d80be-123">Canceled leave still appears in upcoming time off on People workspace (441358)</span></span>

<span data-ttu-id="d80be-124">La baja cancelada ya no se muestra como próximo tiempo libre en las tarjetas de bajas del espacio de trabajo **Personas**.</span><span class="sxs-lookup"><span data-stu-id="d80be-124">Canceled leave no longer displays as upcoming time off on the leave cards in the **People** workspace.</span></span>

## <a name="unable-to-use-the-department-entity-property-in-the-positionv2-entity-456486"></a><span data-ttu-id="d80be-125">No se puede usar la propiedad de entidad de departamento en la entidad PositionV2 (456486)</span><span class="sxs-lookup"><span data-stu-id="d80be-125">Unable to use the department entity property in the PositionV2 entity (456486)</span></span>

<span data-ttu-id="d80be-126">Ahora puede agregar un departamento sin crear una relación duplicada.</span><span class="sxs-lookup"><span data-stu-id="d80be-126">You can now add a department without creating a duplicate relation.</span></span>

## <a name="payrollworkerenrolledbenefitdetailentity-should-only-use-calculated-field-for-retirement-plans-459779"></a><span data-ttu-id="d80be-127">PayrollWorkerEnrolledBenefitDetailEntity solo debe usar el campo calculado para los planes de jubilación (459779)</span><span class="sxs-lookup"><span data-stu-id="d80be-127">PayrollWorkerEnrolledBenefitDetailEntity should only use calculated field for retirement plans (459779)</span></span>

<span data-ttu-id="d80be-128">Al exportar la entidad **PayrollWorkerEnrolledBenefitDetailEntity**, la exportación determina si debe usar un campo calculado basado en una tabla de tasas o usar el campo **ContribuciónAmountCur** en la tabla de apoyo.</span><span class="sxs-lookup"><span data-stu-id="d80be-128">When exporting the **PayrollWorkerEnrolledBenefitDetailEntity** entity, the export determines whether it should use a calculated field based on a rate table or use the **ContributionAmountCur** field on the backing table.</span></span> <span data-ttu-id="d80be-129">La lógica utilizada por la entidad de datos utiliza la tabla de tasas en situaciones donde la aplicación normalmente no lo hace.</span><span class="sxs-lookup"><span data-stu-id="d80be-129">The logic used by the data entity uses the rate table in situations where the application normally doesn't.</span></span> <span data-ttu-id="d80be-130">Esta lógica hace que las exportaciones de la entidad devuelvan un valor cero para esta columna, porque no hay una tabla de tasas de cálculo y el producto no permite que el cliente especifique una.</span><span class="sxs-lookup"><span data-stu-id="d80be-130">This logic causes the entity exports to return a zero value for this column, because there's no calculation rate table and the product doesn't allow the customer to specify one.</span></span>
 
## <a name="confusing-translations-in-czech-language-in-personnel-management-and-employee-self-service-400276"></a><span data-ttu-id="d80be-131">Traducciones confusas al checo en Gestión de personal y Autoservicio de empleados (400276)</span><span class="sxs-lookup"><span data-stu-id="d80be-131">Confusing translations in Czech language in Personnel management and Employee self service (400276)</span></span>

<span data-ttu-id="d80be-132">Esta versión corrige las traducciones para **Directorio de empresa**, **Próximo curso registrado**, **Trabajo** y **Posición**.</span><span class="sxs-lookup"><span data-stu-id="d80be-132">This release corrects the translations for **Company directory**, **Next registered course**, **Job**, and **Position**.</span></span>
 
## <a name="the-workcalendaremployment-table-doesnt-have-the-created-and-modified-system-fields-enabled-460171"></a><span data-ttu-id="d80be-133">La tabla WorkCalendarEmployment no tiene habilitados los campos del sistema creados y modificados (460171)</span><span class="sxs-lookup"><span data-stu-id="d80be-133">The WorkCalendarEmployment table doesn't have the created and modified system fields enabled (460171)</span></span>

<span data-ttu-id="d80be-134">Los campos del sistema creados y modificados están habilitados ahora en la table **WorkCalendarEmployment** de Human Resources.</span><span class="sxs-lookup"><span data-stu-id="d80be-134">Created and modified system fields are now enabled on the **WorkCalendarEmployment** table in Human Resources.</span></span>
 
## <a name="null-reference-exception-for-hire-and-add-details-for-future-employee-455475"></a><span data-ttu-id="d80be-135">Excepción de referencia nula para Contratar y agregar detalles para el futuro empleado (455475)</span><span class="sxs-lookup"><span data-stu-id="d80be-135">Null reference exception for Hire and add details for future employee (455475)</span></span>

<span data-ttu-id="d80be-136">Esta versión corrige un error (referencia nula) en la entrada simplificada de empleados cuando contrata a un empleado usando la opción **Contratar y agregar detalles**.</span><span class="sxs-lookup"><span data-stu-id="d80be-136">This release corrects an error (null reference) in streamlined employee entry when you hire an employee using the option to **Hire and add details**.</span></span>

## <a name="changes-made-in-the-dataverse-worker-entity-dont-reflect-in-human-resources-455652"></a><span data-ttu-id="d80be-137">Los cambios realizados en la entidad de trabajadores de Dataverse no se reflejan en Human Resources (455652)</span><span class="sxs-lookup"><span data-stu-id="d80be-137">Changes made in the Dataverse Worker entity don't reflect in Human Resources (455652)</span></span>

<span data-ttu-id="d80be-138">Los cambios realizados en los siguientes campos de la entidad **Trabajador** en Dataverse ahora aparecerán en Human Resources:</span><span class="sxs-lookup"><span data-stu-id="d80be-138">Changes made to the following fields in the **Worker** entity in Dataverse will now show up in Human Resources:</span></span>

- <span data-ttu-id="d80be-139">**Trabaja en casa**</span><span class="sxs-lookup"><span data-stu-id="d80be-139">**Works from home**</span></span>
- <span data-ttu-id="d80be-140">**Antigüedad**</span><span class="sxs-lookup"><span data-stu-id="d80be-140">**Seniority date**</span></span>
- <span data-ttu-id="d80be-141">**Fecha de aniversario**</span><span class="sxs-lookup"><span data-stu-id="d80be-141">**Anniversary date**</span></span>
- <span data-ttu-id="d80be-142">**Fecha de contratación original**</span><span class="sxs-lookup"><span data-stu-id="d80be-142">**Original hire date**</span></span>

## <a name="correct-compensation-level-doesnt-default-based-on-the-job-assigned-to-the-position-394136"></a><span data-ttu-id="d80be-143">El nivel de compensación correcto no se basa por defecto en el trabajo asignado al puesto (394136)</span><span class="sxs-lookup"><span data-stu-id="d80be-143">Correct compensation level doesn't default based on the job assigned to the position (394136)</span></span>

<span data-ttu-id="d80be-144">Con este cambio, el nivel de compensación correcto predeterminado se basa en los registros de **Fecha de vigencia** de los **Detalles de posición** y la **Fecha de inicio** de la **Asignación del plan de compensación**.</span><span class="sxs-lookup"><span data-stu-id="d80be-144">With this change, the correct compensation level defaults based on the **Date effective** records for the **Position details** and the **Start date** of the **Compensation plan assignment**.</span></span>

## <a name="in-preview"></a><span data-ttu-id="d80be-145">En vista previa</span><span class="sxs-lookup"><span data-stu-id="d80be-145">In preview</span></span>

## <a name="mandatory-fields"></a><span data-ttu-id="d80be-146">Campos obligatorios</span><span class="sxs-lookup"><span data-stu-id="d80be-146">Mandatory fields</span></span> 

<span data-ttu-id="d80be-147">Ahora puede hacer que los campos sean obligatorios utilizando las capacidades de personalización de Human Resources.</span><span class="sxs-lookup"><span data-stu-id="d80be-147">You can now make fields mandatory by using Human Resources personalization capabilities.</span></span> <span data-ttu-id="d80be-148">Esta característica requiere **Vistas guardadas**.</span><span class="sxs-lookup"><span data-stu-id="d80be-148">This feature requires **Saved views**.</span></span>

## <a name="human-resources-application-in-teams"></a><span data-ttu-id="d80be-149">Aplicación Human Resources en Teams</span><span class="sxs-lookup"><span data-stu-id="d80be-149">Human Resources application in Teams</span></span>

<span data-ttu-id="d80be-150">Los empleados pueden ver y solicitar tiempo fuera del trabajo en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d80be-150">Employees can view and request time away from work within Microsoft Teams.</span></span> <span data-ttu-id="d80be-151">Pueden interactuar con un bot para crear solicitudes de baja.</span><span class="sxs-lookup"><span data-stu-id="d80be-151">They can interact with a bot to create leave requests.</span></span> <span data-ttu-id="d80be-152">Para más información, consulte [Aplicación de recursos humanos en Teams](https://go.microsoft.com/fwlink/?linkid=2127841).</span><span class="sxs-lookup"><span data-stu-id="d80be-152">For more information, see [Human Resources app in Teams](https://go.microsoft.com/fwlink/?linkid=2127841).</span></span> 

## <a name="data-management-framework-dmf-entities-for-benefits-management"></a><span data-ttu-id="d80be-153">Entidades del marco de gestión de datos (DMF) para la gestión de ventajas</span><span class="sxs-lookup"><span data-stu-id="d80be-153">Data management framework (DMF) entities for Benefits management</span></span>
 
<span data-ttu-id="d80be-154">Las entidades de gestión de ventajas se están lanzando.</span><span class="sxs-lookup"><span data-stu-id="d80be-154">Benefits management entities are releasing.</span></span> <span data-ttu-id="d80be-155">Las entidades DMF le permite importar y exportar datos para configurar fácilmente la gestión de ventajas.</span><span class="sxs-lookup"><span data-stu-id="d80be-155">DMF entities allow you to import and export data to easily configure benefits management.</span></span> <span data-ttu-id="d80be-156">Una plantilla de gestión de ventajas estará disponible para mover datos.</span><span class="sxs-lookup"><span data-stu-id="d80be-156">A Benefits management template will be available to move data.</span></span> <span data-ttu-id="d80be-157">La plantilla exporta e importa los datos de manera secuencial para respetar las dependencias de datos.</span><span class="sxs-lookup"><span data-stu-id="d80be-157">The template exports and imports the data sequentially to respect data dependencies.</span></span>

## <a name="buy-and-sell-leave"></a><span data-ttu-id="d80be-158">Comprar y vender bajas</span><span class="sxs-lookup"><span data-stu-id="d80be-158">Buy and sell leave</span></span> 

<span data-ttu-id="d80be-159">Algunas organizaciones ofrecen un beneficio que permite a los empleados comprar o vender su baja.</span><span class="sxs-lookup"><span data-stu-id="d80be-159">Some organizations provide a benefit that allows employees to buy or sell their leave.</span></span> <span data-ttu-id="d80be-160">Este proceso a menudo se gestiona manualmente.</span><span class="sxs-lookup"><span data-stu-id="d80be-160">This process is often managed manually.</span></span> <span data-ttu-id="d80be-161">Esta característica automatiza las políticas de gestión y las solicitudes del departamento de recursos humanos.</span><span class="sxs-lookup"><span data-stu-id="d80be-161">This feature automates managing policies and requests for the HR department.</span></span> <span data-ttu-id="d80be-162">Agiliza el proceso de gestión de bajas y ayuda a eliminar errores.</span><span class="sxs-lookup"><span data-stu-id="d80be-162">It streamlines the leave management process and helps eliminate mistakes.</span></span> <span data-ttu-id="d80be-163">Para obtener más información, consulte:</span><span class="sxs-lookup"><span data-stu-id="d80be-163">For more information, see:</span></span>

- [<span data-ttu-id="d80be-164">Gestionar directivas de compra y venta de bajas</span><span class="sxs-lookup"><span data-stu-id="d80be-164">Manage buy and sell leave policies</span></span>](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)
- [<span data-ttu-id="d80be-165">Comprar y vender bajas</span><span class="sxs-lookup"><span data-stu-id="d80be-165">Buy and sell leave</span></span>](hr-employee-self-service-buy-sell-leave.md)

## <a name="leave-accrual-for-a-single-company-or-single-plan"></a><span data-ttu-id="d80be-166">Acumulación de bajas para una sola compañía o plan único</span><span class="sxs-lookup"><span data-stu-id="d80be-166">Leave accrual for a single company or single plan</span></span>

<span data-ttu-id="d80be-167">Los clientes pueden procesar las acumulaciones para una sola compañía o un solo plan de bajas y ausencias.</span><span class="sxs-lookup"><span data-stu-id="d80be-167">Customers can process accruals for a single company or a single leave and absence plan.</span></span> <span data-ttu-id="d80be-168">Esta capacidad proporciona transparencia para el proceso de acumulación para clientes con diferentes años de baja o directivas de acumulación de bajas.</span><span class="sxs-lookup"><span data-stu-id="d80be-168">This ability provides clarity for the accrual process for customers with different leave years or leave accrual policies.</span></span> <span data-ttu-id="d80be-169">Para más información, consulte [Acumular bajas por empresa o por plan de licencia](hr-leave-and-absence-accrue.md).</span><span class="sxs-lookup"><span data-stu-id="d80be-169">For more information, see [Accrue leave per company or per leave plan](hr-leave-and-absence-accrue.md).</span></span>

## <a name="add-attachments-to-time-off-requests"></a><span data-ttu-id="d80be-170">Agregar archivos adjuntos a las solicitudes de permisos</span><span class="sxs-lookup"><span data-stu-id="d80be-170">Add attachments to time-off requests</span></span>

<span data-ttu-id="d80be-171">La capacidad de agregar archivos adjuntos a las solicitudes de baja aprobadas es crítica en el entorno actual de COVID-19.</span><span class="sxs-lookup"><span data-stu-id="d80be-171">The ability to add attachments to approved leave requests is critical in the current COVID-19 environment.</span></span> <span data-ttu-id="d80be-172">Los empleados ahora pueden agregar estos archivos adjuntos.</span><span class="sxs-lookup"><span data-stu-id="d80be-172">Employees can now add these attachments.</span></span> <span data-ttu-id="d80be-173">También tienen más información sobre cómo se realizan las actualizaciones para las solicitudes de baja.</span><span class="sxs-lookup"><span data-stu-id="d80be-173">They also have more insight into how updates are made to leave requests.</span></span> <span data-ttu-id="d80be-174">Para más información, vea [Agregar un archivo adjunto a una solicitud existente](hr-employee-self-service-request-time-off.md#add-an-attachment-to-an-existing-request).</span><span class="sxs-lookup"><span data-stu-id="d80be-174">For more information, see [Add an attachment to an existing request](hr-employee-self-service-request-time-off.md#add-an-attachment-to-an-existing-request).</span></span>

## <a name="add-reason-code-to-accrual-suspensions"></a><span data-ttu-id="d80be-175">Agregar código de razón a las suspensiones acumuladas</span><span class="sxs-lookup"><span data-stu-id="d80be-175">Add reason code to accrual suspensions</span></span> 

<span data-ttu-id="d80be-176">Se han agregado códigos de motivo a la suspensión acumulada.</span><span class="sxs-lookup"><span data-stu-id="d80be-176">Reason codes have been added to the accrual suspension.</span></span>

## <a name="carry-forward-rules"></a><span data-ttu-id="d80be-177">Transferir reglas</span><span class="sxs-lookup"><span data-stu-id="d80be-177">Carry forward rules</span></span> 

<span data-ttu-id="d80be-178">Puede especificar un tipo de transferencia de baja para transferir saldos en los que los ajustes de transferencia se traspasan.</span><span class="sxs-lookup"><span data-stu-id="d80be-178">You can specify a carry forward leave type for carry forward balances where carry forward adjustments are transferred.</span></span> <span data-ttu-id="d80be-179">Por ejemplo, si un empleado adelanta 10 días, puede elegir un tipo de baja diferente para esos 10 días.</span><span class="sxs-lookup"><span data-stu-id="d80be-179">For example, if an employee carries forward 10 days, you can pick a different leave type for those 10 days.</span></span> <span data-ttu-id="d80be-180">Para más información, ver [Configurar tipos de baja y ausencia](hr-leave-and-absence-types.md).</span><span class="sxs-lookup"><span data-stu-id="d80be-180">For more information, see [Configure leave and absence types](hr-leave-and-absence-types.md).</span></span>

## <a name="suspend-leave-accrual-for-specified-leave-types"></a><span data-ttu-id="d80be-181">Suspender la acumulación de bajas para los tipos de baja especificados</span><span class="sxs-lookup"><span data-stu-id="d80be-181">Suspend leave accrual for specified leave types</span></span>

<span data-ttu-id="d80be-182">Puede crear una regla para suspender la acumulación de bajas para empleados con solicitudes de bajas introducidas para bajas no pagadas.</span><span class="sxs-lookup"><span data-stu-id="d80be-182">You can create a rule to suspend leave accruals for employees with leave requests entered for unpaid leave.</span></span> <span data-ttu-id="d80be-183">La baja no remunerada puede ser un tipo, pero no tiene por qué serlo.</span><span class="sxs-lookup"><span data-stu-id="d80be-183">Unpaid leave can be a type, but doesn't have to be.</span></span> <span data-ttu-id="d80be-184">Puede suspender cualquier baja basada en otro tipo de baja.</span><span class="sxs-lookup"><span data-stu-id="d80be-184">You can suspend any leave based on another leave type.</span></span>

## <a name="dmf-entity-available-for-accrual-suspensions"></a><span data-ttu-id="d80be-185">Entidad DMF disponible para suspensiones acumuladas</span><span class="sxs-lookup"><span data-stu-id="d80be-185">DMF entity available for accrual suspensions</span></span> 

<span data-ttu-id="d80be-186">Ahora está disponible una entidad DMF para suspensiones acumuladas.</span><span class="sxs-lookup"><span data-stu-id="d80be-186">A DMF entity is now available for accrual suspensions.</span></span>

## <a name="coming-soon"></a><span data-ttu-id="d80be-187">Próximamente</span><span class="sxs-lookup"><span data-stu-id="d80be-187">Coming soon</span></span>

## <a name="checklist-entities-included-in-dataverse"></a><span data-ttu-id="d80be-188">Lista de entidades incluidas en Dataverse</span><span class="sxs-lookup"><span data-stu-id="d80be-188">Checklist entities included in Dataverse</span></span>

<span data-ttu-id="d80be-189">Las entidades de lista de verificación para los procesos Incorporación, Retirada, Transferencias y Empresa estarán disponibles pronto en Dataverse.</span><span class="sxs-lookup"><span data-stu-id="d80be-189">Checklist entities for Onboarding, Offboarding, Transfers, and Business processes will be available soon in Dataverse.</span></span>

## <a name="see-also"></a><span data-ttu-id="d80be-190">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d80be-190">See also</span></span>

[<span data-ttu-id="d80be-191">Novedades y cambios en Human Resources</span><span class="sxs-lookup"><span data-stu-id="d80be-191">What's new or changed in Human Resources</span></span>](hr-admin-whats-new.md)</br>
[<span data-ttu-id="d80be-192">Visión general de Dynamics 365 Human Resources 2019 en el segundo lanzamiento de versiones</span><span class="sxs-lookup"><span data-stu-id="d80be-192">Overview of Dynamics 365 Human Resources 2019 release wave 2</span></span>](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[<span data-ttu-id="d80be-193">Actualizar proceso</span><span class="sxs-lookup"><span data-stu-id="d80be-193">Update process</span></span>](hr-admin-setup-update-process.md)</br>
[<span data-ttu-id="d80be-194">Administrar características</span><span class="sxs-lookup"><span data-stu-id="d80be-194">Manage features</span></span>](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]