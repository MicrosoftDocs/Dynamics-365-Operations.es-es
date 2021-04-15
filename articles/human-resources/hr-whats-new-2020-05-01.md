---
title: Novedades y cambios en Dynamics 365 Human Resources (1 de mayo de 2020)
description: Este artículo describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Human Resources para el 1 de mayo de 2020.
author: andreabichsel
ms.date: 05/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 52eb748fe8b3c62d6a5ebf46fd01afc291ec5572
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5803426"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-may-1-2020"></a><span data-ttu-id="87aea-103">Novedades y cambios en Dynamics 365 Human Resources (1 de mayo de 2020)</span><span class="sxs-lookup"><span data-stu-id="87aea-103">What's new or changed in Dynamics 365 Human Resources (May 1, 2020)</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="87aea-104">Este artículo describe las características que son nuevas o que se han cambiado en Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="87aea-104">This article describes features that are either new or changed in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="87aea-105">Los cambios se aplican al número de compilación 8.1.3196.</span><span class="sxs-lookup"><span data-stu-id="87aea-105">Changes apply to build number 8.1.3196.</span></span> <span data-ttu-id="87aea-106">Los números entre paréntesis en algunos encabezados hacen referencia a los números de soporte en (LCS) para su referencia.</span><span class="sxs-lookup"><span data-stu-id="87aea-106">The numbers in parentheses in some headings refer to LCS support numbers for reference.</span></span>

## <a name="new-performance-management-entities-available-in-data-management-framework-dmf"></a><span data-ttu-id="87aea-107">Nuevas entidades de administración de rendimiento disponibles en el marco de gestión de datos (DMF)</span><span class="sxs-lookup"><span data-stu-id="87aea-107">New Performance Management entities available in Data Management Framework (DMF)</span></span>

<span data-ttu-id="87aea-108">Ahora están disponibles las siguientes entidades.</span><span class="sxs-lookup"><span data-stu-id="87aea-108">The following entities are now available.</span></span> <span data-ttu-id="87aea-109">Si no ve estas entidades en la lista de entidades, use la opción **Actualizar entidades** en **Parámetros del marco> Configuración de la entidad> Actualizar lista de entidades**.</span><span class="sxs-lookup"><span data-stu-id="87aea-109">If you don't see these entities listed in the entities list, use the **Refresh entities** option in **Framework Parameters > Entity settings > Refresh entity list**.</span></span>

- <span data-ttu-id="87aea-110">**Competencia de tratamiento**</span><span class="sxs-lookup"><span data-stu-id="87aea-110">**Discussion Competency**</span></span>
- <span data-ttu-id="87aea-111">**Metas de tratamiento**</span><span class="sxs-lookup"><span data-stu-id="87aea-111">**Discussion Goals**</span></span>
- <span data-ttu-id="87aea-112">**Medida de tratamiento**</span><span class="sxs-lookup"><span data-stu-id="87aea-112">**Discussion Measurement**</span></span>
- <span data-ttu-id="87aea-113">**Tema de tratamiento**</span><span class="sxs-lookup"><span data-stu-id="87aea-113">**Discussion Topic**</span></span>
- <span data-ttu-id="87aea-114">**Diario de rendimiento**</span><span class="sxs-lookup"><span data-stu-id="87aea-114">**Performance Journal**</span></span>
- <span data-ttu-id="87aea-115">**Medida**</span><span class="sxs-lookup"><span data-stu-id="87aea-115">**Measurement**</span></span>
- <span data-ttu-id="87aea-116">**Medida de metas**</span><span class="sxs-lookup"><span data-stu-id="87aea-116">**Goal Measurement**</span></span>

<span data-ttu-id="87aea-117">Adicionalmente, se añadieron **Puntuación total** y **Puntuación media** a la entidad **Discusión**.</span><span class="sxs-lookup"><span data-stu-id="87aea-117">In addition, **Total score** and **Average score** were added to the **Discussion** entity.</span></span>

## <a name="increase-length-of-leave-request-comments-275641"></a><span data-ttu-id="87aea-118">Aumentar la duración de los comentarios de solicitud de baja (275641)</span><span class="sxs-lookup"><span data-stu-id="87aea-118">Increase length of leave request comments (275641)</span></span>

<span data-ttu-id="87aea-119">Los comentarios sobre las solicitudes de baja ahora permiten más de 100 caracteres.</span><span class="sxs-lookup"><span data-stu-id="87aea-119">Comments on leave requests now allow more than 100 characters.</span></span>

## <a name="final-comments-on-reviews-dont-appear-when-the-manager-or-employee-is-signed-into-a-different-company-431688"></a><span data-ttu-id="87aea-120">Los comentarios finales sobre las revisiones no aparecen cuando el gerente o el empleado inician sesión en una empresa diferente (431688)</span><span class="sxs-lookup"><span data-stu-id="87aea-120">Final comments on reviews don't appear when the manager or employee is signed into a different company (431688)</span></span>

<span data-ttu-id="87aea-121">Todos los comentarios aparecerán ahora al ver las reseñas.</span><span class="sxs-lookup"><span data-stu-id="87aea-121">All comments will now appear when viewing reviews.</span></span>

## <a name="user-defined-links-arent-supported-on-new-worker-form-390374"></a><span data-ttu-id="87aea-122">Los enlaces definidos por el usuario no son compatibles con el nuevo formulario Trabajador (390374)</span><span class="sxs-lookup"><span data-stu-id="87aea-122">User-defined links aren't supported on new Worker form (390374)</span></span>

<span data-ttu-id="87aea-123">Los enlaces definidos por el usuario ahora están habilitados en el formulario optimizado **Trabajador**.</span><span class="sxs-lookup"><span data-stu-id="87aea-123">User-defined links are now enabled on the streamlined **Worker** form.</span></span>

## <a name="hcmratinglevelentity-causes-odata-api-crash-439476"></a><span data-ttu-id="87aea-124">HcmRatingLevelEntity provoca el bloqueo de la API de OData (439476)</span><span class="sxs-lookup"><span data-stu-id="87aea-124">HcmRatingLevelEntity causes OData API crash (439476)</span></span>

<span data-ttu-id="87aea-125">Este cambio corrige el bloqueo de la API.</span><span class="sxs-lookup"><span data-stu-id="87aea-125">This change corrects the API crash.</span></span> <span data-ttu-id="87aea-126">Un nombre duplicado llevaba en sí este error.</span><span class="sxs-lookup"><span data-stu-id="87aea-126">A duplicate name cased this error.</span></span>

## <a name="in-preview"></a><span data-ttu-id="87aea-127">En vista previa</span><span class="sxs-lookup"><span data-stu-id="87aea-127">In preview</span></span>

## <a name="leave-suspension"></a><span data-ttu-id="87aea-128">Dejar suspensión</span><span class="sxs-lookup"><span data-stu-id="87aea-128">Leave suspension</span></span>

<span data-ttu-id="87aea-129">Puede suspender la baja y la ausencia en Human Resources para un empleado.</span><span class="sxs-lookup"><span data-stu-id="87aea-129">You can suspend leave and absence in Human Resources for an employee.</span></span> <span data-ttu-id="87aea-130">La suspensión de la baja detiene las acumulaciones de baja para los tipos de baja seleccionados.</span><span class="sxs-lookup"><span data-stu-id="87aea-130">Suspending leave stops the leave accruals for selected leave types.</span></span> <span data-ttu-id="87aea-131">Si la suspensión ocurre después de que se ha procesado una acumulación, la suspensión de la licencia crea un ajuste prorrateado al saldo de licencia del empleado.</span><span class="sxs-lookup"><span data-stu-id="87aea-131">If the suspension occurs after an accrual has been processed, suspending leave creates a prorated adjustment to the employee's leave balance.</span></span> <span data-ttu-id="87aea-132">Para obtener más información, consulte [Suspender baja](hr-leave-and-absence-suspend-leave.md).</span><span class="sxs-lookup"><span data-stu-id="87aea-132">For more information, see [Suspend leave](hr-leave-and-absence-suspend-leave.md).</span></span>

## <a name="update-user-experience-to-indicate-that-accrual-is-suspended-429550"></a><span data-ttu-id="87aea-133">Actualizar la experiencia del usuario para indicar que la acumulación está suspendida (429550)</span><span class="sxs-lookup"><span data-stu-id="87aea-133">Update user experience to indicate that accrual is suspended (429550)</span></span>

<span data-ttu-id="87aea-134">La experiencia del usuario ahora indica que la acumulación se ha suspendido para un plan.</span><span class="sxs-lookup"><span data-stu-id="87aea-134">The user experience now indicates that the accrual has been suspended for a plan.</span></span>

## <a name="suspend-leave-accrual-for-specified-leave-types-272447"></a><span data-ttu-id="87aea-135">Suspender la acumulación de bajas para los tipos de baja especificados (272447)</span><span class="sxs-lookup"><span data-stu-id="87aea-135">Suspend leave accrual for specified leave types (272447)</span></span>

<span data-ttu-id="87aea-136">En este comunicado, RR. HH. puede crear una regla para suspender la acumulación de bajas para empleados con solicitudes de bajas introducidas para bajas no pagadas.</span><span class="sxs-lookup"><span data-stu-id="87aea-136">In this release, HR can create a rule to suspend leave accruals for employees with leave requests entered for unpaid leave.</span></span> <span data-ttu-id="87aea-137">La baja no remunerada puede ser un tipo, pero no tiene por qué serlo.</span><span class="sxs-lookup"><span data-stu-id="87aea-137">Unpaid leave can be a type, but doesn't have to be.</span></span> <span data-ttu-id="87aea-138">Puede suspender cualquier baja basada en otro tipo de baja.</span><span class="sxs-lookup"><span data-stu-id="87aea-138">You can suspend any leave based on another leave type.</span></span>

## <a name="dmf-entity-available-for-accrual-suspensions-429549"></a><span data-ttu-id="87aea-139">Entidad DMF disponible para suspensiones acumuladas (429549)</span><span class="sxs-lookup"><span data-stu-id="87aea-139">DMF entity available for accrual suspensions (429549)</span></span>

<span data-ttu-id="87aea-140">Ahora está disponible una entidad DMF para suspensiones acumuladas.</span><span class="sxs-lookup"><span data-stu-id="87aea-140">A DMF entity is now available for accrual suspensions.</span></span>

## <a name="add-reason-code-to-accrual-suspensions-429547"></a><span data-ttu-id="87aea-141">Agregar código de razón a las suspensiones acumuladas (429547)</span><span class="sxs-lookup"><span data-stu-id="87aea-141">Add reason code to accrual suspensions (429547)</span></span>

<span data-ttu-id="87aea-142">Se han agregado códigos de motivo a la suspensión acumulada.</span><span class="sxs-lookup"><span data-stu-id="87aea-142">Reason codes have been added to the accrual suspension.</span></span>

## <a name="begin-transitioning-from-human-resources-parameters-to-leave-and-absence-parameters"></a><span data-ttu-id="87aea-143">Comenzar la transición desde los parámetros de Recursos Humanos a los parámetros de baja y ausencia</span><span class="sxs-lookup"><span data-stu-id="87aea-143">Begin transitioning from Human Resources parameters to leave and absence parameters</span></span>

<span data-ttu-id="87aea-144">Esta versión comienza a combinar los parámetros de Recursos Humanos con los parámetros de Baja y ausencia.</span><span class="sxs-lookup"><span data-stu-id="87aea-144">This release starts to combine Human Resources parameters with Leave and absence parameters.</span></span>

## <a name="carry-forward-rules"></a><span data-ttu-id="87aea-145">Transferir reglas</span><span class="sxs-lookup"><span data-stu-id="87aea-145">Carry forward rules</span></span>

<span data-ttu-id="87aea-146">Puede especificar un tipo de transferencia de baja para transferir saldos en los que los ajustes de transferencia se traspasan.</span><span class="sxs-lookup"><span data-stu-id="87aea-146">You can specify a carry forward leave type for carry forward balances where carry forward adjustments are transferred.</span></span> <span data-ttu-id="87aea-147">Por ejemplo, si un empleado adelanta 10 días, puede elegir un tipo de baja diferente para esos 10 días.</span><span class="sxs-lookup"><span data-stu-id="87aea-147">For example, if an employee carries forward 10 days, you can pick a different leave type for those 10 days.</span></span> <span data-ttu-id="87aea-148">Para más información, ver [Configurar tipos de baja y ausencia](hr-leave-and-absence-types.md).</span><span class="sxs-lookup"><span data-stu-id="87aea-148">For more information, see [Configure leave and absence types](hr-leave-and-absence-types.md).</span></span>

## <a name="known-issues"></a><span data-ttu-id="87aea-149">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="87aea-149">Known issues</span></span>

## <a name="sharepoint-preview-doesnt-work-in-some-environments"></a><span data-ttu-id="87aea-150">La vista previa SharePoint no funciona en algunos entornos</span><span class="sxs-lookup"><span data-stu-id="87aea-150">SharePoint preview doesn't work in some environments</span></span>

<span data-ttu-id="87aea-151">Si la vista previa del documento para documentos almacenados en SharePoint no funciona, intente el siguiente procedimiento:</span><span class="sxs-lookup"><span data-stu-id="87aea-151">If document preview for documents stored in SharePoint doesn't work, try the following procedure:</span></span>

1. <span data-ttu-id="87aea-152">Verifique que la cuenta de usuario administrador tenga un correo electrónico asociado con el registro de usuario.</span><span class="sxs-lookup"><span data-stu-id="87aea-152">Verify the Admin user account has an email associated with the user record.</span></span> <span data-ttu-id="87aea-153">Puede ver esta información en la página **Usuario**.</span><span class="sxs-lookup"><span data-stu-id="87aea-153">You can view this information in the **User** page.</span></span> <span data-ttu-id="87aea-154">Si el correo electrónico no está configurado, debe agregar el correo electrónico y el proveedor con el complemento OData Excel.</span><span class="sxs-lookup"><span data-stu-id="87aea-154">If email isn't set up, you need to add the email and provider with the OData Excel add-in.</span></span> <span data-ttu-id="87aea-155">Por defecto, la dirección de correo electrónico no está presente en el diseño de Excel.</span><span class="sxs-lookup"><span data-stu-id="87aea-155">By default, the email address isn't present in the Excel design.</span></span> <span data-ttu-id="87aea-156">Deberá editar el diseño de Excel, agregar todos los campos, aplicar y actualizar.</span><span class="sxs-lookup"><span data-stu-id="87aea-156">You'll need to edit the Excel design, add all fields, apply, and refresh.</span></span> <span data-ttu-id="87aea-157">Una vez que haya completado esos pasos, puede actualizar la cuenta de administrador.</span><span class="sxs-lookup"><span data-stu-id="87aea-157">Once you've completed those steps, you can update the admin account.</span></span>

2. <span data-ttu-id="87aea-158">Una vez que la cuenta de administrador tenga una cuenta de correo electrónico asociada, inicie sesión en Human Resources con credenciales de administrador.</span><span class="sxs-lookup"><span data-stu-id="87aea-158">After the Admin account has an associated email account, sign in to Human Resources with Admin credentials.</span></span>

3. <span data-ttu-id="87aea-159">Acceda a un archivo adjunto en SharePoint para comenzar la vista previa del documento.</span><span class="sxs-lookup"><span data-stu-id="87aea-159">Access an attachment in SharePoint to start the document preview.</span></span>

4. <span data-ttu-id="87aea-160">Inicie sesión con otra cuenta de usuario que tenga acceso a los archivos adjuntos y verifique que la vista previa funcione como se esperaba.</span><span class="sxs-lookup"><span data-stu-id="87aea-160">Sign in with another user account that has access to attachments and verify that the preview works as expected.</span></span>

## <a name="see-also"></a><span data-ttu-id="87aea-161">Consulte también</span><span class="sxs-lookup"><span data-stu-id="87aea-161">See also</span></span>

[<span data-ttu-id="87aea-162">Novedades y cambios en Human Resources</span><span class="sxs-lookup"><span data-stu-id="87aea-162">What's new or changed in Human Resources</span></span>](hr-admin-whats-new.md)</br>
[<span data-ttu-id="87aea-163">Visión general de Dynamics 365 Human Resources 2019 en el segundo lanzamiento de versiones</span><span class="sxs-lookup"><span data-stu-id="87aea-163">Overview of Dynamics 365 Human Resources 2019 release wave 2</span></span>](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[<span data-ttu-id="87aea-164">Actualizar proceso</span><span class="sxs-lookup"><span data-stu-id="87aea-164">Update process</span></span>](hr-admin-setup-update-process.md)</br>
[<span data-ttu-id="87aea-165">Administrar características</span><span class="sxs-lookup"><span data-stu-id="87aea-165">Manage features</span></span>](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]