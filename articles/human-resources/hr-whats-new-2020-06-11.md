---
title: Novedades o cambios en Dynamics 365 Human Resources (11 de junio de 2020)
description: Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Human Resources.
author: Darinkramer
manager: AnnBe
ms.date: 06/16/2020
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
ms.search.validFrom: 2020-06-11
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 8ec15c33cdb1abc32c28fd78822b06188dd0feac
ms.sourcegitcommit: 81296c49be9953aa01e15527c34d0ef13b4622a9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/22/2020
ms.locfileid: "3614295"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-june-11-2020"></a><span data-ttu-id="bdfb3-103">Novedades o cambios en Dynamics 365 Human Resources (11 de junio de 2020)</span><span class="sxs-lookup"><span data-stu-id="bdfb3-103">What's new or changed in Dynamics 365 Human Resources (June 11, 2020)</span></span>

<span data-ttu-id="bdfb3-104">Este artículo describe las características que son nuevas o que se han cambiado en Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="bdfb3-104">This article describes features that are either new or changed in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="bdfb3-105">Los cambios se aplican al número de compilación 8.1.3316.</span><span class="sxs-lookup"><span data-stu-id="bdfb3-105">Changes apply to build number 8.1.3316.</span></span> <span data-ttu-id="bdfb3-106">Los números entre paréntesis en algunos encabezados hacen referencia a los números de soporte en (LCS) para su referencia.</span><span class="sxs-lookup"><span data-stu-id="bdfb3-106">The numbers in parentheses in some headings refer to LCS support numbers for reference.</span></span>

## <a name="streamlined-employee-form-sometimes-causes-child-form-close-x-buttons-to-stop-working-442369"></a><span data-ttu-id="bdfb3-107">El formulario de empleados optimizado a veces hace que los botones de cierre de formulario secundario (X) dejen de funcionar (442369)</span><span class="sxs-lookup"><span data-stu-id="bdfb3-107">Streamlined employee form sometimes causes child form close (X) buttons to stop working (442369)</span></span>

<span data-ttu-id="bdfb3-108">Cuando el nuevo formulario **Trabajador** fue habilitado, el botón de cierre (**X**) en ocasiones no funcionaba en formularios secundarios.</span><span class="sxs-lookup"><span data-stu-id="bdfb3-108">When the new **Worker** form was enabled, the close (**X**) button occasionally didn't work on child forms.</span></span> <span data-ttu-id="bdfb3-109">Este problema era intermitente.</span><span class="sxs-lookup"><span data-stu-id="bdfb3-109">This problem was intermittent.</span></span> <span data-ttu-id="bdfb3-110">Puede cerrar el formulario después de salir y volver a él.</span><span class="sxs-lookup"><span data-stu-id="bdfb3-110">You could close the form after leaving and coming back to it.</span></span> <span data-ttu-id="bdfb3-111">Por ejemplo, puede seleccionar un elemento del menú a la izquierda y volver al formulario **Trabajador** y luego ciérrelo.</span><span class="sxs-lookup"><span data-stu-id="bdfb3-111">For example, you could select a menu item on the left, and navigate back to the **Worker** form, and then close it.</span></span> <span data-ttu-id="bdfb3-112">El lanzamiento de esta semana corrige este problema.</span><span class="sxs-lookup"><span data-stu-id="bdfb3-112">This week's release fixes this problem.</span></span> 

## <a name="the-worker-personal-contact-person-entity-doesnt-export-personal-contacts-with-a-parent-relationship-type"></a><span data-ttu-id="bdfb3-113">La entidad de Persona de contacto personal del trabajador no exporta contactos personales con un tipo de relación principal</span><span class="sxs-lookup"><span data-stu-id="bdfb3-113">The Worker personal contact person entity doesn't export personal contacts with a parent relationship type</span></span>

<span data-ttu-id="bdfb3-114">Con este lanzamiento, la entidad **Persona de contacto personal del trabajador** exporta todos los tipos de relación.</span><span class="sxs-lookup"><span data-stu-id="bdfb3-114">With this release, the **Worker personal contact person** entity exports all relationship types.</span></span>

## <a name="the-hcmpositionworkerassignmentv2entity-should-be-part-of-the-ceridian-payroll-integration-package-by-default-448506"></a><span data-ttu-id="bdfb3-115">HcmPositionWorkerAssignmentV2Entity debería formar parte del paquete de integración de nómina de Ceridian de forma predeterminada (448506)</span><span class="sxs-lookup"><span data-stu-id="bdfb3-115">The HcmPositionWorkerAssignmentV2Entity should be part of the Ceridian payroll integration package by default (448506)</span></span>

<span data-ttu-id="bdfb3-116">Con este cambio, **HcmPositionWorkerAssignmentV2Entity** está incluido en el paquete de integración de nómina de Ceridian.</span><span class="sxs-lookup"><span data-stu-id="bdfb3-116">With this change, the **HcmPositionWorkerAssignmentV2Entity** is included in the Ceridian payroll integration package.</span></span>

## <a name="in-preview"></a><span data-ttu-id="bdfb3-117">En vista previa</span><span class="sxs-lookup"><span data-stu-id="bdfb3-117">In preview</span></span>

## <a name="database-logging"></a><span data-ttu-id="bdfb3-118">Registro de base de datos</span><span class="sxs-lookup"><span data-stu-id="bdfb3-118">Database logging</span></span>

<span data-ttu-id="bdfb3-119">La característica de registro de la base de datos le permite determinar qué tablas y campos se supervisan.</span><span class="sxs-lookup"><span data-stu-id="bdfb3-119">The database logging feature allows you to determine which tables and fields to monitor.</span></span> <span data-ttu-id="bdfb3-120">También le permite determinar los eventos que deberían activar el seguimiento de cambios.</span><span class="sxs-lookup"><span data-stu-id="bdfb3-120">It also lets you determine the events that should trigger change tracking.</span></span> <span data-ttu-id="bdfb3-121">Utiliza las capacidades de registro de bases de datos para ver estos cambios a lo largo del tiempo.</span><span class="sxs-lookup"><span data-stu-id="bdfb3-121">You use database logging capabilities to see these changes over time.</span></span> <span data-ttu-id="bdfb3-122">Para más información, vea [Configurar y administrar el registro de bases de datos](hr-admin-database-logging.md).</span><span class="sxs-lookup"><span data-stu-id="bdfb3-122">For more information, see [Configure and manage database logging](hr-admin-database-logging.md).</span></span>

## <a name="human-resources-application-in-teams"></a><span data-ttu-id="bdfb3-123">Aplicación Human Resources en Teams</span><span class="sxs-lookup"><span data-stu-id="bdfb3-123">Human Resources application in Teams</span></span>

<span data-ttu-id="bdfb3-124">Los empleados pueden ver y solicitar tiempo fuera del trabajo en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="bdfb3-124">Employees can view and request time away from work within Microsoft Teams.</span></span> <span data-ttu-id="bdfb3-125">Pueden interactuar con un bot para crear solicitudes de baja.</span><span class="sxs-lookup"><span data-stu-id="bdfb3-125">They can interact with a bot to create leave requests.</span></span> <span data-ttu-id="bdfb3-126">Para más información, consulte [Aplicación de recursos humanos en Teams](https://go.microsoft.com/fwlink/?linkid=2127841).</span><span class="sxs-lookup"><span data-stu-id="bdfb3-126">For more information, see [Human Resources app in Teams](https://go.microsoft.com/fwlink/?linkid=2127841).</span></span> 

## <a name="data-management-framework-dmf-entities-for-benefits-management"></a><span data-ttu-id="bdfb3-127">Entidades del marco de gestión de datos (DMF) para la gestión de ventajas</span><span class="sxs-lookup"><span data-stu-id="bdfb3-127">Data management framework (DMF) entities for Benefits management</span></span>
 
<span data-ttu-id="bdfb3-128">Las entidades de gestión de ventajas se están lanzando.</span><span class="sxs-lookup"><span data-stu-id="bdfb3-128">Benefits management entities are releasing.</span></span> <span data-ttu-id="bdfb3-129">Las entidades DMF le permite importar y exportar datos para configurar fácilmente la gestión de ventajas.</span><span class="sxs-lookup"><span data-stu-id="bdfb3-129">DMF entities allow you to import and export data to easily configure benefits management.</span></span> <span data-ttu-id="bdfb3-130">Una plantilla de gestión de ventajas estará disponible para mover datos.</span><span class="sxs-lookup"><span data-stu-id="bdfb3-130">A Benefits management template will be available to move data.</span></span> <span data-ttu-id="bdfb3-131">La plantilla exporta e importa los datos de manera secuencial para respetar las dependencias de datos.</span><span class="sxs-lookup"><span data-stu-id="bdfb3-131">The template exports and imports the data sequentially to respect data dependencies.</span></span>

## <a name="buy-and-sell-leave"></a><span data-ttu-id="bdfb3-132">Comprar y vender bajas</span><span class="sxs-lookup"><span data-stu-id="bdfb3-132">Buy and sell leave</span></span> 

<span data-ttu-id="bdfb3-133">Algunas organizaciones ofrecen un beneficio que permite a los empleados comprar o vender su baja.</span><span class="sxs-lookup"><span data-stu-id="bdfb3-133">Some organizations provide a benefit that allows employees to buy or sell their leave.</span></span> <span data-ttu-id="bdfb3-134">Este proceso a menudo se gestiona manualmente.</span><span class="sxs-lookup"><span data-stu-id="bdfb3-134">This process is often managed manually.</span></span> <span data-ttu-id="bdfb3-135">Esta característica automatiza las políticas de gestión y las solicitudes del departamento de recursos humanos.</span><span class="sxs-lookup"><span data-stu-id="bdfb3-135">This feature automates managing policies and requests for the HR department.</span></span> <span data-ttu-id="bdfb3-136">Agiliza el proceso de gestión de bajas y ayuda a eliminar errores.</span><span class="sxs-lookup"><span data-stu-id="bdfb3-136">It streamlines the leave management process and helps eliminate mistakes.</span></span> <span data-ttu-id="bdfb3-137">Para obtener más información, consulte:</span><span class="sxs-lookup"><span data-stu-id="bdfb3-137">For more information, see:</span></span>

- [<span data-ttu-id="bdfb3-138">Gestionar directivas de compra y venta de bajas</span><span class="sxs-lookup"><span data-stu-id="bdfb3-138">Manage buy and sell leave policies</span></span>](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)
- [<span data-ttu-id="bdfb3-139">Comprar y vender bajas</span><span class="sxs-lookup"><span data-stu-id="bdfb3-139">Buy and sell leave</span></span>](hr-employee-self-service-buy-sell-leave.md)

## <a name="leave-accrual-for-a-single-company-or-single-plan"></a><span data-ttu-id="bdfb3-140">Acumulación de bajas para una sola compañía o plan único</span><span class="sxs-lookup"><span data-stu-id="bdfb3-140">Leave accrual for a single company or single plan</span></span>

<span data-ttu-id="bdfb3-141">Los clientes pueden procesar las acumulaciones para una sola compañía o un solo plan de licencia y ausencias.</span><span class="sxs-lookup"><span data-stu-id="bdfb3-141">Customers can process accruals for a single company or a single leave and absence plan.</span></span> <span data-ttu-id="bdfb3-142">Esta capacidad proporciona transparencia en el proceso de acumulación para clientes con diferentes años de baja o directivas de acumulación de bajas.</span><span class="sxs-lookup"><span data-stu-id="bdfb3-142">This ability provides clarity into the accrual process for customers with different leave years or leave accrual policies.</span></span> <span data-ttu-id="bdfb3-143">Para más información, consulte [Acumular bajas por empresa o por plan de licencia](hr-leave-and-absence-accrue.md#accrue-leave-per-company-or-per-leave-plan).</span><span class="sxs-lookup"><span data-stu-id="bdfb3-143">For more information, see [Accrue leave per company or per leave plan](hr-leave-and-absence-accrue.md#accrue-leave-per-company-or-per-leave-plan).</span></span>

## <a name="add-attachments-to-time-off-requests"></a><span data-ttu-id="bdfb3-144">Agregar archivos adjuntos a las solicitudes de tiempo libre</span><span class="sxs-lookup"><span data-stu-id="bdfb3-144">Add attachments to time off requests</span></span>

<span data-ttu-id="bdfb3-145">La capacidad de agregar archivos adjuntos a las solicitudes de baja aprobadas es crítica en el entorno actual de COVID-19.</span><span class="sxs-lookup"><span data-stu-id="bdfb3-145">The ability to add attachments to approved leave requests is critical in the current COVID-19 environment.</span></span> <span data-ttu-id="bdfb3-146">Los empleados ahora pueden agregar estos archivos adjuntos.</span><span class="sxs-lookup"><span data-stu-id="bdfb3-146">Employees can now add these attachments.</span></span> <span data-ttu-id="bdfb3-147">También tienen más información sobre cómo se realizan las actualizaciones para las solicitudes de baja.</span><span class="sxs-lookup"><span data-stu-id="bdfb3-147">They also have more insight into how updates are made to leave requests.</span></span> <span data-ttu-id="bdfb3-148">Para más información, vea [Agregar un archivo adjunto a una solicitud existente](hr-employee-self-service-request-time-off.md#add-an-attachment-to-an-existing-request).</span><span class="sxs-lookup"><span data-stu-id="bdfb3-148">For more information, see [Add an attachment to an existing request](hr-employee-self-service-request-time-off.md#add-an-attachment-to-an-existing-request).</span></span>

## <a name="add-reason-code-to-accrual-suspensions"></a><span data-ttu-id="bdfb3-149">Agregar código de razón a las suspensiones acumuladas</span><span class="sxs-lookup"><span data-stu-id="bdfb3-149">Add reason code to accrual suspensions</span></span> 

<span data-ttu-id="bdfb3-150">Se han agregado códigos de motivo a la suspensión acumulada.</span><span class="sxs-lookup"><span data-stu-id="bdfb3-150">Reason codes have been added to the accrual suspension.</span></span>

## <a name="carry-forward-rules"></a><span data-ttu-id="bdfb3-151">Transferir reglas</span><span class="sxs-lookup"><span data-stu-id="bdfb3-151">Carry forward rules</span></span> 

<span data-ttu-id="bdfb3-152">Puede especificar un tipo de transferencia de baja para transferir saldos en los que los ajustes de transferencia se traspasan.</span><span class="sxs-lookup"><span data-stu-id="bdfb3-152">You can specify a carry forward leave type for carry forward balances where carry forward adjustments are transferred.</span></span> <span data-ttu-id="bdfb3-153">Por ejemplo, si un empleado adelanta 10 días, puede elegir un tipo de baja diferente para esos 10 días.</span><span class="sxs-lookup"><span data-stu-id="bdfb3-153">For example, if an employee carries forward 10 days, you can pick a different leave type for those 10 days.</span></span> <span data-ttu-id="bdfb3-154">Para más información, ver [Configurar tipos de baja y ausencia](hr-leave-and-absence-types.md).</span><span class="sxs-lookup"><span data-stu-id="bdfb3-154">For more information, see [Configure leave and absence types](hr-leave-and-absence-types.md).</span></span>

## <a name="suspend-leave-accrual-for-specified-leave-types"></a><span data-ttu-id="bdfb3-155">Suspender la acumulación de bajas para los tipos de baja especificados</span><span class="sxs-lookup"><span data-stu-id="bdfb3-155">Suspend leave accrual for specified leave types</span></span>

<span data-ttu-id="bdfb3-156">Puede crear una regla para suspender la acumulación de bajas para empleados con solicitudes de bajas introducidas para bajas no pagadas.</span><span class="sxs-lookup"><span data-stu-id="bdfb3-156">You can create a rule to suspend leave accruals for employees with leave requests entered for unpaid leave.</span></span> <span data-ttu-id="bdfb3-157">La baja no remunerada puede ser un tipo, pero no tiene por qué serlo.</span><span class="sxs-lookup"><span data-stu-id="bdfb3-157">Unpaid leave can be a type, but doesn't have to be.</span></span> <span data-ttu-id="bdfb3-158">Puede suspender cualquier baja basada en otro tipo de baja.</span><span class="sxs-lookup"><span data-stu-id="bdfb3-158">You can suspend any leave based on another leave type.</span></span>

## <a name="dmf-entity-available-for-accrual-suspensions"></a><span data-ttu-id="bdfb3-159">Entidad DMF disponible para suspensiones acumuladas</span><span class="sxs-lookup"><span data-stu-id="bdfb3-159">DMF entity available for accrual suspensions</span></span> 

<span data-ttu-id="bdfb3-160">Ahora está disponible una entidad DMF para suspensiones acumuladas.</span><span class="sxs-lookup"><span data-stu-id="bdfb3-160">A DMF entity is now available for accrual suspensions.</span></span>

## <a name="coming-soon"></a><span data-ttu-id="bdfb3-161">Próximamente</span><span class="sxs-lookup"><span data-stu-id="bdfb3-161">Coming soon</span></span>

## <a name="new-platform-capabilities"></a><span data-ttu-id="bdfb3-162">Nuevas capacidades de plataforma</span><span class="sxs-lookup"><span data-stu-id="bdfb3-162">New platform capabilities</span></span> 

<span data-ttu-id="bdfb3-163">Podrá hacer que los campos sean obligatorios mediante la personalización.</span><span class="sxs-lookup"><span data-stu-id="bdfb3-163">You'll be able to make fields mandatory by using personalization.</span></span> <span data-ttu-id="bdfb3-164">Esta función requerirá que habilite **Vistas guardadas**.</span><span class="sxs-lookup"><span data-stu-id="bdfb3-164">This feature will require you to enable **Saved views**.</span></span>

## <a name="configure-the-name-of-employee-self-service"></a><span data-ttu-id="bdfb3-165">Configurar el nombre de Autoservicio para empleados</span><span class="sxs-lookup"><span data-stu-id="bdfb3-165">Configure the name of Employee self-service</span></span>

<span data-ttu-id="bdfb3-166">Una nueva opción estará disponible en los parámetros de Recursos humanos para actualizar el nombre del espacio de trabajo de autoservicio del empleado a Autoservicio.</span><span class="sxs-lookup"><span data-stu-id="bdfb3-166">A new option will be available in Human Resources parameters to update the name of the Employee self service workspace to Self service.</span></span> 

## <a name="see-also"></a><span data-ttu-id="bdfb3-167">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bdfb3-167">See also</span></span>

[<span data-ttu-id="bdfb3-168">Novedades y cambios en Human Resources</span><span class="sxs-lookup"><span data-stu-id="bdfb3-168">What's new or changed in Human Resources</span></span>](hr-admin-whats-new.md)</br>
[<span data-ttu-id="bdfb3-169">Visión general de Dynamics 365 Human Resources 2019 en el segundo lanzamiento de versiones</span><span class="sxs-lookup"><span data-stu-id="bdfb3-169">Overview of Dynamics 365 Human Resources 2019 release wave 2</span></span>](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[<span data-ttu-id="bdfb3-170">Actualizar proceso</span><span class="sxs-lookup"><span data-stu-id="bdfb3-170">Update process</span></span>](hr-admin-setup-update-process.md)</br>
[<span data-ttu-id="bdfb3-171">Administrar características</span><span class="sxs-lookup"><span data-stu-id="bdfb3-171">Manage features</span></span>](hr-admin-manage-features.md)