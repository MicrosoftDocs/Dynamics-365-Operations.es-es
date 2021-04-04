---
title: Novedades o cambios en Dynamics 365 Human Resources (23 de julio de 2020)
description: Este tema describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Human Resources para el 23 de julio de 2020.
author: andreabichsel
manager: tfehr
ms.date: 07/23/2020
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
ms.search.validFrom: 2020-07-23
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 6da636cfe4a36cca57d30bde5ab830b78b351bc5
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/17/2021
ms.locfileid: "5463583"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-july-23-2020"></a><span data-ttu-id="bb40f-103">Novedades o cambios en Dynamics 365 Human Resources (23 de julio de 2020)</span><span class="sxs-lookup"><span data-stu-id="bb40f-103">What's new or changed in Dynamics 365 Human Resources (July 23, 2020)</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="bb40f-104">Este tema describe las características que son nuevas o que se han cambiado en Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="bb40f-104">This topic describes features that are either new or changed in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="bb40f-105">Los cambios se aplican al número de compilación 8.1.3416.</span><span class="sxs-lookup"><span data-stu-id="bb40f-105">Changes apply to build number 8.1.3416.</span></span> <span data-ttu-id="bb40f-106">Los números entre paréntesis en algunos encabezados hacen referencia a los números de soporte en (LCS) para su referencia.</span><span class="sxs-lookup"><span data-stu-id="bb40f-106">The numbers in parentheses in some headings refer to LCS support numbers for reference.</span></span>

## <a name="deleting-financial-dimensions-on-a-position-doesnt-work-as-expected-445476"></a><span data-ttu-id="bb40f-107">Eliminar dimensiones financieras en una posición no funciona como se esperaba (445476)</span><span class="sxs-lookup"><span data-stu-id="bb40f-107">Deleting Financial Dimensions on a Position doesn't work as expected (445476)</span></span>

<span data-ttu-id="bb40f-108">Eliminar dimensiones de una posición ahora elimina esas mismas posiciones de Dataverse.</span><span class="sxs-lookup"><span data-stu-id="bb40f-108">Removing dimensions from a position now removes those same positions from Dataverse.</span></span>

## <a name="positions-not-in-hierarchy-show-inactive-positions-397257"></a><span data-ttu-id="bb40f-109">Las posiciones que no están en la jerarquía muestran posiciones inactivas (397257)</span><span class="sxs-lookup"><span data-stu-id="bb40f-109">Positions not in hierarchy show inactive positions (397257)</span></span>

<span data-ttu-id="bb40f-110">Las posiciones que están inactivas (tienen una duración expirada), ya no se muestran en la jerarquía de posición como **Posiciones no en jerarquía**.</span><span class="sxs-lookup"><span data-stu-id="bb40f-110">Positions that are inactive (have an expired duration), no longer display in the position hierarchy as **Positions not in hierarchy**.</span></span> 

## <a name="validation-occurring-between-leaveenrollmententity-and-hcmworkerentity-on-data-management-framework-dmf-import-causes-slow-data-loads-442324"></a><span data-ttu-id="bb40f-111">La validación que ocurre entre LeaveEnrollmentEntity y HcmWorkerEntity en la importación del marco de administración de datos (DMF) causa cargas de datos lentas (442324)</span><span class="sxs-lookup"><span data-stu-id="bb40f-111">Validation occurring between LeaveEnrollmentEntity and HcmWorkerEntity on Data Management Framework (DMF) import causes slow data loads (442324)</span></span>

<span data-ttu-id="bb40f-112">Los cambios en esta versión aumentan el rendimiento de **LeaveEnrollmentEntity**.</span><span class="sxs-lookup"><span data-stu-id="bb40f-112">Changes in this release increase the performance of **LeaveEnrollmentEntity**.</span></span>

## <a name="unable-to-personalize-in-organization-administration-447490"></a><span data-ttu-id="bb40f-113">No se puede personalizar en la administración de la Organización (447490)</span><span class="sxs-lookup"><span data-stu-id="bb40f-113">Unable to personalize in Organization administration (447490)</span></span>

<span data-ttu-id="bb40f-114">Con este cambio, ahora puede personalizar los enlaces en **Administración de la organización**.</span><span class="sxs-lookup"><span data-stu-id="bb40f-114">With this change, you can now personalize the links in **Organization administration**.</span></span>

## <a name="in-preview"></a><span data-ttu-id="bb40f-115">En vista previa</span><span class="sxs-lookup"><span data-stu-id="bb40f-115">In preview</span></span>

## <a name="mandatory-fields"></a><span data-ttu-id="bb40f-116">Campos obligatorios</span><span class="sxs-lookup"><span data-stu-id="bb40f-116">Mandatory fields</span></span> 

<span data-ttu-id="bb40f-117">Ahora puede hacer que los campos sean obligatorios utilizando las capacidades de personalización de Human Resources.</span><span class="sxs-lookup"><span data-stu-id="bb40f-117">You can now make fields mandatory by using Human Resources personalization capabilities.</span></span> <span data-ttu-id="bb40f-118">Esta característica requiere **Vistas guardadas**.</span><span class="sxs-lookup"><span data-stu-id="bb40f-118">This feature requires **Saved views**.</span></span>

## <a name="human-resources-application-in-teams"></a><span data-ttu-id="bb40f-119">Aplicación Human Resources en Teams</span><span class="sxs-lookup"><span data-stu-id="bb40f-119">Human Resources application in Teams</span></span>

<span data-ttu-id="bb40f-120">Los empleados pueden ver y solicitar tiempo fuera del trabajo en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="bb40f-120">Employees can view and request time away from work within Microsoft Teams.</span></span> <span data-ttu-id="bb40f-121">Pueden interactuar con un bot para crear solicitudes de baja.</span><span class="sxs-lookup"><span data-stu-id="bb40f-121">They can interact with a bot to create leave requests.</span></span> <span data-ttu-id="bb40f-122">Para más información, consulte [Aplicación de recursos humanos en Teams](https://go.microsoft.com/fwlink/?linkid=2127841).</span><span class="sxs-lookup"><span data-stu-id="bb40f-122">For more information, see [Human Resources app in Teams](https://go.microsoft.com/fwlink/?linkid=2127841).</span></span> 

## <a name="data-management-framework-dmf-entities-for-benefits-management"></a><span data-ttu-id="bb40f-123">Entidades del marco de gestión de datos (DMF) para la gestión de ventajas</span><span class="sxs-lookup"><span data-stu-id="bb40f-123">Data management framework (DMF) entities for Benefits management</span></span>
 
<span data-ttu-id="bb40f-124">Las entidades de gestión de ventajas se están lanzando.</span><span class="sxs-lookup"><span data-stu-id="bb40f-124">Benefits management entities are releasing.</span></span> <span data-ttu-id="bb40f-125">Las entidades DMF le permite importar y exportar datos para configurar fácilmente la gestión de ventajas.</span><span class="sxs-lookup"><span data-stu-id="bb40f-125">DMF entities allow you to import and export data to easily configure benefits management.</span></span> <span data-ttu-id="bb40f-126">Una plantilla de gestión de ventajas estará disponible para mover datos.</span><span class="sxs-lookup"><span data-stu-id="bb40f-126">A Benefits management template will be available to move data.</span></span> <span data-ttu-id="bb40f-127">La plantilla exporta e importa los datos de manera secuencial para respetar las dependencias de datos.</span><span class="sxs-lookup"><span data-stu-id="bb40f-127">The template exports and imports the data sequentially to respect data dependencies.</span></span>

## <a name="buy-and-sell-leave"></a><span data-ttu-id="bb40f-128">Comprar y vender bajas</span><span class="sxs-lookup"><span data-stu-id="bb40f-128">Buy and sell leave</span></span> 

<span data-ttu-id="bb40f-129">Algunas organizaciones ofrecen un beneficio que permite a los empleados comprar o vender su baja.</span><span class="sxs-lookup"><span data-stu-id="bb40f-129">Some organizations provide a benefit that allows employees to buy or sell their leave.</span></span> <span data-ttu-id="bb40f-130">Este proceso a menudo se gestiona manualmente.</span><span class="sxs-lookup"><span data-stu-id="bb40f-130">This process is often managed manually.</span></span> <span data-ttu-id="bb40f-131">Esta característica automatiza las políticas de gestión y las solicitudes del departamento de recursos humanos.</span><span class="sxs-lookup"><span data-stu-id="bb40f-131">This feature automates managing policies and requests for the HR department.</span></span> <span data-ttu-id="bb40f-132">Agiliza el proceso de gestión de bajas y ayuda a eliminar errores.</span><span class="sxs-lookup"><span data-stu-id="bb40f-132">It streamlines the leave management process and helps eliminate mistakes.</span></span> <span data-ttu-id="bb40f-133">Para obtener más información, consulte:</span><span class="sxs-lookup"><span data-stu-id="bb40f-133">For more information, see:</span></span>

- [<span data-ttu-id="bb40f-134">Gestionar directivas de compra y venta de bajas</span><span class="sxs-lookup"><span data-stu-id="bb40f-134">Manage buy and sell leave policies</span></span>](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)
- [<span data-ttu-id="bb40f-135">Comprar y vender bajas</span><span class="sxs-lookup"><span data-stu-id="bb40f-135">Buy and sell leave</span></span>](hr-employee-self-service-buy-sell-leave.md)

## <a name="leave-accrual-for-a-single-company-or-single-plan"></a><span data-ttu-id="bb40f-136">Acumulación de bajas para una sola compañía o plan único</span><span class="sxs-lookup"><span data-stu-id="bb40f-136">Leave accrual for a single company or single plan</span></span>

<span data-ttu-id="bb40f-137">Los clientes pueden procesar las acumulaciones para una sola compañía o un solo plan de bajas y ausencias.</span><span class="sxs-lookup"><span data-stu-id="bb40f-137">Customers can process accruals for a single company or a single leave and absence plan.</span></span> <span data-ttu-id="bb40f-138">Esta capacidad proporciona transparencia para el proceso de acumulación para clientes con diferentes años de baja o directivas de acumulación de bajas.</span><span class="sxs-lookup"><span data-stu-id="bb40f-138">This ability provides clarity for the accrual process for customers with different leave years or leaves accrual policies.</span></span> <span data-ttu-id="bb40f-139">Para más información, consulte [Acumular bajas por empresa o por plan de licencia](hr-leave-and-absence-accrue.md).</span><span class="sxs-lookup"><span data-stu-id="bb40f-139">For more information, see [Accrue leave per company or per leave plan](hr-leave-and-absence-accrue.md).</span></span>

## <a name="add-attachments-to-time-off-requests"></a><span data-ttu-id="bb40f-140">Agregar archivos adjuntos a las solicitudes de permisos</span><span class="sxs-lookup"><span data-stu-id="bb40f-140">Add attachments to time-off requests</span></span>

<span data-ttu-id="bb40f-141">La capacidad de agregar archivos adjuntos a las solicitudes de baja aprobadas es crítica en el entorno actual de COVID-19.</span><span class="sxs-lookup"><span data-stu-id="bb40f-141">The ability to add attachments to approved leave requests is critical in the current COVID-19 environment.</span></span> <span data-ttu-id="bb40f-142">Los empleados ahora pueden agregar estos archivos adjuntos.</span><span class="sxs-lookup"><span data-stu-id="bb40f-142">Employees can now add these attachments.</span></span> <span data-ttu-id="bb40f-143">También tienen más información sobre cómo se realizan las actualizaciones para las solicitudes de baja.</span><span class="sxs-lookup"><span data-stu-id="bb40f-143">They also have more insight into how updates are made to leave requests.</span></span> <span data-ttu-id="bb40f-144">Para más información, vea [Agregar un archivo adjunto a una solicitud existente](hr-employee-self-service-request-time-off.md#add-an-attachment-to-an-existing-request).</span><span class="sxs-lookup"><span data-stu-id="bb40f-144">For more information, see [Add an attachment to an existing request](hr-employee-self-service-request-time-off.md#add-an-attachment-to-an-existing-request).</span></span>

## <a name="add-reason-code-to-accrual-suspensions"></a><span data-ttu-id="bb40f-145">Agregar código de razón a las suspensiones acumuladas</span><span class="sxs-lookup"><span data-stu-id="bb40f-145">Add reason code to accrual suspensions</span></span> 

<span data-ttu-id="bb40f-146">Se han agregado códigos de motivo a la suspensión acumulada.</span><span class="sxs-lookup"><span data-stu-id="bb40f-146">Reason codes have been added to the accrual suspension.</span></span>

## <a name="carry-forward-rules"></a><span data-ttu-id="bb40f-147">Transferir reglas</span><span class="sxs-lookup"><span data-stu-id="bb40f-147">Carry forward rules</span></span> 

<span data-ttu-id="bb40f-148">Puede especificar un tipo de transferencia de baja para transferir saldos en los que los ajustes de transferencia se traspasan.</span><span class="sxs-lookup"><span data-stu-id="bb40f-148">You can specify a carry forward leave type for carry forward balances where carry forward adjustments are transferred.</span></span> <span data-ttu-id="bb40f-149">Por ejemplo, si un empleado adelanta 10 días, puede elegir un tipo de baja diferente para esos 10 días.</span><span class="sxs-lookup"><span data-stu-id="bb40f-149">For example, if an employee carries forward 10 days, you can pick a different leave type for those 10 days.</span></span> <span data-ttu-id="bb40f-150">Para más información, ver [Configurar tipos de baja y ausencia](hr-leave-and-absence-types.md).</span><span class="sxs-lookup"><span data-stu-id="bb40f-150">For more information, see [Configure leave and absence types](hr-leave-and-absence-types.md).</span></span>

## <a name="suspend-leave-accrual-for-specified-leave-types"></a><span data-ttu-id="bb40f-151">Suspender la acumulación de bajas para los tipos de baja especificados</span><span class="sxs-lookup"><span data-stu-id="bb40f-151">Suspend leave accrual for specified leave types</span></span>

<span data-ttu-id="bb40f-152">Puede crear una regla para suspender la acumulación de bajas para empleados con solicitudes de bajas introducidas para bajas no pagadas.</span><span class="sxs-lookup"><span data-stu-id="bb40f-152">You can create a rule to suspend leave accruals for employees with leave requests entered for unpaid leave.</span></span> <span data-ttu-id="bb40f-153">La baja no remunerada puede ser un tipo, pero no tiene por qué serlo.</span><span class="sxs-lookup"><span data-stu-id="bb40f-153">Unpaid leave can be a type, but doesn't have to be.</span></span> <span data-ttu-id="bb40f-154">Puede suspender cualquier baja basada en otro tipo de baja.</span><span class="sxs-lookup"><span data-stu-id="bb40f-154">You can suspend any leave based on another leave type.</span></span>

## <a name="dmf-entity-available-for-accrual-suspensions"></a><span data-ttu-id="bb40f-155">Entidad DMF disponible para suspensiones acumuladas</span><span class="sxs-lookup"><span data-stu-id="bb40f-155">DMF entity available for accrual suspensions</span></span> 

<span data-ttu-id="bb40f-156">Ahora está disponible una entidad DMF para suspensiones acumuladas.</span><span class="sxs-lookup"><span data-stu-id="bb40f-156">A DMF entity is now available for accrual suspensions.</span></span>

## <a name="coming-soon"></a><span data-ttu-id="bb40f-157">Próximamente</span><span class="sxs-lookup"><span data-stu-id="bb40f-157">Coming soon</span></span>

## <a name="checklist-entities-included-in-dataverse"></a><span data-ttu-id="bb40f-158">Lista de entidades incluidas en Dataverse</span><span class="sxs-lookup"><span data-stu-id="bb40f-158">Checklist entities included in Dataverse</span></span>

<span data-ttu-id="bb40f-159">Las entidades de lista de verificación para los procesos Incorporación, Retirada, Transferencias y Empresa estarán disponibles pronto en Dataverse.</span><span class="sxs-lookup"><span data-stu-id="bb40f-159">Checklist entities for Onboarding, Offboarding, Transfers, and Business processes will be available soon in Dataverse.</span></span>

## <a name="platform-changes"></a><span data-ttu-id="bb40f-160">Cambios de plataforma</span><span class="sxs-lookup"><span data-stu-id="bb40f-160">Platform changes</span></span>

<span data-ttu-id="bb40f-161">Actualización de la plataforma 10.0.12 (36)</span><span class="sxs-lookup"><span data-stu-id="bb40f-161">Platform update 10.0.12 (36)</span></span>

## <a name="see-also"></a><span data-ttu-id="bb40f-162">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bb40f-162">See also</span></span>

[<span data-ttu-id="bb40f-163">Novedades y cambios en Human Resources</span><span class="sxs-lookup"><span data-stu-id="bb40f-163">What's new or changed in Human Resources</span></span>](hr-admin-whats-new.md)</br>
[<span data-ttu-id="bb40f-164">Visión general de Dynamics 365 Human Resources 2019 en el segundo lanzamiento de versiones</span><span class="sxs-lookup"><span data-stu-id="bb40f-164">Overview of Dynamics 365 Human Resources 2019 release wave 2</span></span>](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[<span data-ttu-id="bb40f-165">Actualizar proceso</span><span class="sxs-lookup"><span data-stu-id="bb40f-165">Update process</span></span>](hr-admin-setup-update-process.md)</br>
[<span data-ttu-id="bb40f-166">Administrar características</span><span class="sxs-lookup"><span data-stu-id="bb40f-166">Manage features</span></span>](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]