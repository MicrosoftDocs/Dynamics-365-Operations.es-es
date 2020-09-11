---
title: Novedades y cambios en Dynamics 365 Human Resources (13 de abril de 2020)
description: Este artículo describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Human Resources para el 13 de abril de 2020.
author: Darinkramer
manager: AnnBe
ms.date: 4/13/2020
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
ms.search.validFrom: 2020-04-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 729490e7516d8c7aef7232c9f5c227d3207dcd68
ms.sourcegitcommit: 2bcacef1e010c312f019dbf9740ce87d627848a7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/20/2020
ms.locfileid: "3712433"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-april-13-2020"></a><span data-ttu-id="64368-103">Novedades y cambios en Dynamics 365 Human Resources (13 de abril de 2020)</span><span class="sxs-lookup"><span data-stu-id="64368-103">What's new or changed in Dynamics 365 Human Resources (April 13, 2020)</span></span>

<span data-ttu-id="64368-104">Este artículo describe las características que son nuevas o que se han cambiado en Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="64368-104">This article describes features that are either new or changed in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="64368-105">Los cambios se aplican al número de compilación 8.1.3136.</span><span class="sxs-lookup"><span data-stu-id="64368-105">Changes apply to build number 8.1.3136.</span></span> <span data-ttu-id="64368-106">Los números entre paréntesis en algunos encabezados hacen referencia a los números de soporte en (LCS) para su referencia.</span><span class="sxs-lookup"><span data-stu-id="64368-106">The numbers in parentheses in some headings refer to LCS support numbers for reference.</span></span>

## <a name="new-production-release-cadence"></a><span data-ttu-id="64368-107">Nueva cadencia de lanzamiento de producción</span><span class="sxs-lookup"><span data-stu-id="64368-107">New production release cadence</span></span>

<span data-ttu-id="64368-108">Con la versión de esta semana, la cadencia de lanzamiento de Human Resources cambia de una actualización semanal a una actualización quincenal.</span><span class="sxs-lookup"><span data-stu-id="64368-108">With this week's release, the release cadence for Human Resources shifts from a weekly update to a biweekly update.</span></span> <span data-ttu-id="64368-109">Para garantizar la alineación con prácticas de implementación seguras y mantener altos estándares de estabilidad y fiabilidad en el servicio, el proceso de implementación de actualizaciones del servicio en todas las regiones es ahora una implementación de dos semanas.</span><span class="sxs-lookup"><span data-stu-id="64368-109">To ensure alignment with safe deployment practices, and maintain high standards of stability and reliability in the service, the process of deploying service updates to all regions is now a two-week rollout.</span></span> <span data-ttu-id="64368-110">Pruebas y supervisiones adicionales verifican la implementación exitosa en cada etapa del proceso.</span><span class="sxs-lookup"><span data-stu-id="64368-110">Additional testing and monitors are in place to verify successful deployment at each stage of the process.</span></span> <span data-ttu-id="64368-111">Para obtener más información sobre la cadencia de lanzamiento, vea [Proceso de actualización](hr-admin-setup-update-process.md).</span><span class="sxs-lookup"><span data-stu-id="64368-111">For more information on the release cadence, see [Update process](hr-admin-setup-update-process.md).</span></span>

## <a name="rounding-precision-field-isnt-editable-after-specifying-a-rounding-type-435616"></a><span data-ttu-id="64368-112">El campo de precisión de redondeo no se puede editar después de especificar un tipo de redondeo (435616)</span><span class="sxs-lookup"><span data-stu-id="64368-112">Rounding precision field isn't editable after specifying a Rounding type (435616)</span></span>

<span data-ttu-id="64368-113">Con este cambio, el campo **Precisión de redondeo** ahora está disponible después de actualizar el campo **Tipo de redondeo**.</span><span class="sxs-lookup"><span data-stu-id="64368-113">With this change, the **Rounding precision** field is now available after you update the **Rounding type** field.</span></span>

## <a name="cant-edit-leave-enrollment-end-date-when-the-leave-plan-doesnt-have-accrual-periods-413628"></a><span data-ttu-id="64368-114">No se puede editar la fecha de finalización de la inscripción de licencia cuando el plan de licencia no tiene períodos de acumulación (413628)</span><span class="sxs-lookup"><span data-stu-id="64368-114">Can't edit leave enrollment end date when the leave plan doesn't have accrual periods (413628)</span></span>

<span data-ttu-id="64368-115">Ahora puede editar la fecha de finalización de la inscripción sin obtener el error "Se debe completar la base de la fecha de acumulación de campo".</span><span class="sxs-lookup"><span data-stu-id="64368-115">You can now edit the enrollment end date without getting the error "Field Accrual date basis must be filled in."</span></span>

## <a name="employment-entity-doesnt-sync-to-common-data-service-430834"></a><span data-ttu-id="64368-116">La entidad de empleo no se sincroniza con Common Data Service (430834)</span><span class="sxs-lookup"><span data-stu-id="64368-116">Employment entity doesn't sync to Common Data Service (430834)</span></span>

<span data-ttu-id="64368-117">Este cambio corrige un problema en el que los datos de empleo no se sincronizaban con Common Data Service después de agregar dimensiones financieras.</span><span class="sxs-lookup"><span data-stu-id="64368-117">This change corrects an issue where the employment data wasn't syncing to Common Data Service after adding financial dimensions.</span></span> 

## <a name="remove-multi-parenting-for-work-calendar-time-interval-entity-431775"></a><span data-ttu-id="64368-118">Eliminar la crianza múltiple para la entidad de intervalo de tiempo del calendario laboral (431775)</span><span class="sxs-lookup"><span data-stu-id="64368-118">Remove multi-parenting for Work Calendar Time Interval entity (431775)</span></span>

<span data-ttu-id="64368-119">Este cambio elimina la crianza múltiple para la entidad de **Intervalo de tiempo del calendario laboral**.</span><span class="sxs-lookup"><span data-stu-id="64368-119">This change removes multi-parenting for the **Work Calendar Time Interval** entity.</span></span>

## <a name="filter-with-cast-function-doesnt-work-on-odata-call-position-worker-assignment-entity-431699"></a><span data-ttu-id="64368-120">El filtro con función CAST no funciona en la llamada de OData a la entidad Asignar puesto de trabajador (431699)</span><span class="sxs-lookup"><span data-stu-id="64368-120">Filter with CAST function doesn't work on OData call Position Worker Assignment entity (431699)</span></span>

<span data-ttu-id="64368-121">Esta actualización incluye un cambio para permitir el filtro con la función CAST dentro de OData para la entidad **Asignar puesto de trabajador**.</span><span class="sxs-lookup"><span data-stu-id="64368-121">This update includes a change to allow  filter with CAST function within OData for the **Position Worker Assignment** entity.</span></span>

## <a name="in-preview"></a><span data-ttu-id="64368-122">En vista previa</span><span class="sxs-lookup"><span data-stu-id="64368-122">In Preview</span></span>

## <a name="leave-suspension"></a><span data-ttu-id="64368-123">Dejar suspensión</span><span class="sxs-lookup"><span data-stu-id="64368-123">Leave suspension</span></span>

<span data-ttu-id="64368-124">Puede suspender la baja y la ausencia en Human Resources para un empleado.</span><span class="sxs-lookup"><span data-stu-id="64368-124">You can suspend leave and absence in Human Resources for an employee.</span></span> <span data-ttu-id="64368-125">La suspensión de la baja detiene las acumulaciones de baja para los tipos de baja seleccionados.</span><span class="sxs-lookup"><span data-stu-id="64368-125">Suspending leave stops the leave accruals for selected leave types.</span></span> <span data-ttu-id="64368-126">Si la suspensión ocurre después de que se ha procesado una acumulación, la suspensión de la licencia crea un ajuste prorrateado al saldo de licencia del empleado.</span><span class="sxs-lookup"><span data-stu-id="64368-126">If the suspension occurs after an accrual has been processed, suspending leave creates a prorated adjustment to the employee's leave balance.</span></span> <span data-ttu-id="64368-127">Para obtener más información, consulte [Suspender baja](hr-leave-and-absence-suspend-leave.md).</span><span class="sxs-lookup"><span data-stu-id="64368-127">For more information, see [Suspend leave](hr-leave-and-absence-suspend-leave.md).</span></span>

## <a name="carry-forward-rules"></a><span data-ttu-id="64368-128">Transferir reglas</span><span class="sxs-lookup"><span data-stu-id="64368-128">Carry forward rules</span></span>

<span data-ttu-id="64368-129">Puede especificar un tipo de transferencia de baja para transferir saldos en los que los ajustes de transferencia se traspasan.</span><span class="sxs-lookup"><span data-stu-id="64368-129">You can specify a carry forward leave type for carry forward balances where carry forward adjustments are transferred.</span></span> <span data-ttu-id="64368-130">Por ejemplo, si un empleado adelanta 10 días, puede elegir un tipo de baja diferente para esos 10 días.</span><span class="sxs-lookup"><span data-stu-id="64368-130">For example, if an employee carries forward 10 days, you can pick a different leave type for those 10 days.</span></span> <span data-ttu-id="64368-131">Para más información, ver [Configurar tipos de baja y ausencia](hr-leave-and-absence-types.md).</span><span class="sxs-lookup"><span data-stu-id="64368-131">For more information, see [Configure leave and absence types](hr-leave-and-absence-types.md).</span></span>

## <a name="known-issues"></a><span data-ttu-id="64368-132">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="64368-132">Known issues</span></span>

## <a name="employment-details-entity"></a><span data-ttu-id="64368-133">Entidad Detalles de empleo</span><span class="sxs-lookup"><span data-stu-id="64368-133">Employment Details entity</span></span>

<span data-ttu-id="64368-134">La entidad **Detalles de empleo** ha sido actualizada con los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="64368-134">The **Employment Detail** entity has been updated with the following fields:</span></span>

- <span data-ttu-id="64368-135">**Frecuencia de pago**</span><span class="sxs-lookup"><span data-stu-id="64368-135">**PayFrequency**</span></span>
- <span data-ttu-id="64368-136">**Id. de categoría laboral**</span><span class="sxs-lookup"><span data-stu-id="64368-136">**Employment Category ID**</span></span>
- <span data-ttu-id="64368-137">**Tipo de empleo**</span><span class="sxs-lookup"><span data-stu-id="64368-137">**Employment Type**</span></span>
- <span data-ttu-id="64368-138">**Id. de tipo de empleo**</span><span class="sxs-lookup"><span data-stu-id="64368-138">**EmploymentType ID**</span></span>
- <span data-ttu-id="64368-139">**Estado de la prestación de empleo**</span><span class="sxs-lookup"><span data-stu-id="64368-139">**Benefit Employment Status**</span></span>

<span data-ttu-id="64368-140">Los datos de configuración para estos campos dependen de que la gestión de prestaciones esté habilitada en el espacio de trabajo **Gestión de funciones**.</span><span class="sxs-lookup"><span data-stu-id="64368-140">The setup data for these fields rely on benefits management being enabled in the **Feature management** workspace.</span></span> <span data-ttu-id="64368-141">No complete ni actualice estos campos en la entidad **Detalle de empleo**, porque provocará errores durante la importación.</span><span class="sxs-lookup"><span data-stu-id="64368-141">Don't populate or update these fields in the **Employment Detail** entity, because it will result in errors during import.</span></span>

## <a name="sharepoint-preview-doesnt-work-in-some-environments"></a><span data-ttu-id="64368-142">La vista previa SharePoint no funciona en algunos entornos</span><span class="sxs-lookup"><span data-stu-id="64368-142">SharePoint preview doesn't work in some environments</span></span>

<span data-ttu-id="64368-143">Si la vista previa del documento para documentos almacenados en SharePoint no funciona, intente el siguiente procedimiento:</span><span class="sxs-lookup"><span data-stu-id="64368-143">If document preview for documents stored in SharePoint doesn't work, try the following procedure:</span></span>

1. <span data-ttu-id="64368-144">Verifique que la cuenta de usuario administrador tenga un correo electrónico asociado con el registro de usuario.</span><span class="sxs-lookup"><span data-stu-id="64368-144">Verify the Admin user account has an email associated with the user record.</span></span> <span data-ttu-id="64368-145">Puede ver esta información en la página **Usuario**.</span><span class="sxs-lookup"><span data-stu-id="64368-145">You can view this information in the **User** page.</span></span> <span data-ttu-id="64368-146">Si el correo electrónico no está configurado, debe agregar el correo electrónico y el proveedor con el complemento OData Excel.</span><span class="sxs-lookup"><span data-stu-id="64368-146">If email isn't set up, you need to add the email and provider with the OData Excel add-in.</span></span> <span data-ttu-id="64368-147">Por defecto, la dirección de correo electrónico no está presente en el diseño de Excel.</span><span class="sxs-lookup"><span data-stu-id="64368-147">By default, the email address isn't present in the Excel design.</span></span> <span data-ttu-id="64368-148">Deberá editar el diseño de Excel, agregar todos los campos, aplicar y actualizar.</span><span class="sxs-lookup"><span data-stu-id="64368-148">You'll need to edit the Excel design, add all fields, apply, and refresh.</span></span> <span data-ttu-id="64368-149">Una vez que haya completado esos pasos, puede actualizar la cuenta de administrador.</span><span class="sxs-lookup"><span data-stu-id="64368-149">Once you've completed those steps, you can update the admin account.</span></span>

2. <span data-ttu-id="64368-150">Una vez que la cuenta de administrador tenga una cuenta de correo electrónico asociada, inicie sesión en Human Resources con credenciales de administrador.</span><span class="sxs-lookup"><span data-stu-id="64368-150">After the Admin account has an associated email account, sign in to Human Resources with Admin credentials.</span></span>

3. <span data-ttu-id="64368-151">Acceda a un archivo adjunto en SharePoint para comenzar la vista previa del documento.</span><span class="sxs-lookup"><span data-stu-id="64368-151">Access an attachment in SharePoint to start the document preview.</span></span>

4. <span data-ttu-id="64368-152">Inicie sesión con otra cuenta de usuario que tenga acceso a los archivos adjuntos y verifique que la vista previa funcione como se esperaba.</span><span class="sxs-lookup"><span data-stu-id="64368-152">Sign in with another user account that has access to attachments and verify that the preview works as expected.</span></span>

## <a name="see-also"></a><span data-ttu-id="64368-153">Consulte también</span><span class="sxs-lookup"><span data-stu-id="64368-153">See also</span></span>

[<span data-ttu-id="64368-154">Novedades y cambios en Human Resources</span><span class="sxs-lookup"><span data-stu-id="64368-154">What's new or changed in Human Resources</span></span>](hr-admin-whats-new.md)</br>
[<span data-ttu-id="64368-155">Visión general de Dynamics 365 Human Resources 2019 en el segundo lanzamiento de versiones</span><span class="sxs-lookup"><span data-stu-id="64368-155">Overview of Dynamics 365 Human Resources 2019 release wave 2</span></span>](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[<span data-ttu-id="64368-156">Actualizar proceso</span><span class="sxs-lookup"><span data-stu-id="64368-156">Update process</span></span>](hr-admin-setup-update-process.md)</br>
[<span data-ttu-id="64368-157">Administrar características</span><span class="sxs-lookup"><span data-stu-id="64368-157">Manage features</span></span>](hr-admin-manage-features.md)