---
title: Novedades y cambios en Dynamics 365 Human Resources (3 de marzo de 2020)
description: Este artículo describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Human Resources para el 3 de marzo de 2020.
author: andreabichsel
ms.date: 03/03/2020
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
ms.search.validFrom: 2020-03-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 793f47526ef828a281750c34da9d763c94971943
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5790461"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-march-3-2020"></a><span data-ttu-id="787bb-103">Novedades y cambios en Dynamics 365 Human Resources (3 de marzo de 2020)</span><span class="sxs-lookup"><span data-stu-id="787bb-103">What's new or changed in Dynamics 365 Human Resources (March 3, 2020)</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="787bb-104">Este artículo describe las características que son nuevas o que se han cambiado en Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="787bb-104">This article describes features that are either new or changed in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="787bb-105">Los cambios se aplican al número de compilación 8.1.2955.</span><span class="sxs-lookup"><span data-stu-id="787bb-105">Changes apply to build number 8.1.2955.</span></span> <span data-ttu-id="787bb-106">Los números entre paréntesis en algunos encabezados hacen referencia a los números de soporte en (LCS) para su referencia.</span><span class="sxs-lookup"><span data-stu-id="787bb-106">The numbers in parentheses in some headings refer to LCS support numbers for reference.</span></span>

## <a name="dataverse-solution-is-now-available-with-the-following-changes"></a><span data-ttu-id="787bb-107">La solución Dataverse ahora está disponible con los siguientes cambios:</span><span class="sxs-lookup"><span data-stu-id="787bb-107">Dataverse solution is now available with the following changes:</span></span>

<span data-ttu-id="787bb-108">Una nueva solución Dataverse estará disponible pronto con los siguientes cambios:</span><span class="sxs-lookup"><span data-stu-id="787bb-108">A new Dataverse solution will be available soon with the following changes:</span></span>

| <span data-ttu-id="787bb-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="787bb-109">Description</span></span> | <span data-ttu-id="787bb-110">Cambio</span><span class="sxs-lookup"><span data-stu-id="787bb-110">Change</span></span> |
| ----------------------------------------- | --- |
| <span data-ttu-id="787bb-111">La entidad **Puesto de trabajo** cambia</span><span class="sxs-lookup"><span data-stu-id="787bb-111">**Job/Position** entity changes</span></span> | <span data-ttu-id="787bb-112">Se ha agregado **Región de compensación**</span><span class="sxs-lookup"><span data-stu-id="787bb-112">**Compensation region** added</span></span></br><span data-ttu-id="787bb-113">Se ha agregado **Dimensiones financieras**</span><span class="sxs-lookup"><span data-stu-id="787bb-113">**Financial dimensions** added</span></span> |
| <span data-ttu-id="787bb-114">La entidad **Trabajador** cambia</span><span class="sxs-lookup"><span data-stu-id="787bb-114">**Worker** entity changes</span></span> | <span data-ttu-id="787bb-115">Se ha agregado **Orden del nombre**</span><span class="sxs-lookup"><span data-stu-id="787bb-115">**Name sequence** added</span></span></br><span data-ttu-id="787bb-116">Se ha agregado **Trabaja desde casa**</span><span class="sxs-lookup"><span data-stu-id="787bb-116">**Works from home** added</span></span></br><span data-ttu-id="787bb-117">Se ha agregado **Idioma**</span><span class="sxs-lookup"><span data-stu-id="787bb-117">**Language** added</span></span></br><span data-ttu-id="787bb-118">Se ha agregado **Antigüedad**</span><span class="sxs-lookup"><span data-stu-id="787bb-118">**Seniority date** added</span></span></br><span data-ttu-id="787bb-119">Se ha agregado **Fecha de aniversario**</span><span class="sxs-lookup"><span data-stu-id="787bb-119">**Anniversary date** added</span></span></br><span data-ttu-id="787bb-120">Se ha agregado **Fecha de contratación original**</span><span class="sxs-lookup"><span data-stu-id="787bb-120">**Original hire date** added</span></span> |
| <span data-ttu-id="787bb-121">La entidad **Empleo** cambia</span><span class="sxs-lookup"><span data-stu-id="787bb-121">**Employment** entity changes</span></span> | <span data-ttu-id="787bb-122">Se ha agregado **Dimensiones financieras**</span><span class="sxs-lookup"><span data-stu-id="787bb-122">**Financial dimensions** added</span></span></br><span data-ttu-id="787bb-123">Se ha agregado **Razón de la finalización**</span><span class="sxs-lookup"><span data-stu-id="787bb-123">**Termination reason** added</span></span></br><span data-ttu-id="787bb-124">**Fecha de finalización** ha cambiado de nombre a **Fecha de transición**</span><span class="sxs-lookup"><span data-stu-id="787bb-124">**Termination date** renamed from **Transition date**</span></span></br><span data-ttu-id="787bb-125">Se ha agregado **Fechas del período de pruebas**</span><span class="sxs-lookup"><span data-stu-id="787bb-125">**Probation date** added</span></span> |
| <span data-ttu-id="787bb-126">La entidad **Dirección del trabajador** cambia</span><span class="sxs-lookup"><span data-stu-id="787bb-126">**Worker address** entity changes</span></span> | <span data-ttu-id="787bb-127">Se ha agregado **Dirección postal**</span><span class="sxs-lookup"><span data-stu-id="787bb-127">**Street address** added</span></span></br><span data-ttu-id="787bb-128">**Línea de dirección 1**, **Línea de dirección 2** y **Línea de dirección 3** marcadas para eliminación</span><span class="sxs-lookup"><span data-stu-id="787bb-128">**Address line 1**, **Address line 2**, and **Address line 3** marked for deprecation</span></span> |
| <span data-ttu-id="787bb-129">Nuevas entidades de configuración de compensación variable</span><span class="sxs-lookup"><span data-stu-id="787bb-129">New variable compensation setup entities</span></span> | <span data-ttu-id="787bb-130">**Tipo de plan de compensación variable**</span><span class="sxs-lookup"><span data-stu-id="787bb-130">**Compensation variable plan type**</span></span></br><span data-ttu-id="787bb-131">**Plan de compensación variable**</span><span class="sxs-lookup"><span data-stu-id="787bb-131">**Compensation variable plan**</span></span></br><span data-ttu-id="787bb-132">**Reglas de atribución**</span><span class="sxs-lookup"><span data-stu-id="787bb-132">**Vesting rules**</span></span></br><span data-ttu-id="787bb-133">**Nivel de plan de compensación variable**</span><span class="sxs-lookup"><span data-stu-id="787bb-133">**Compensation variable plan level**</span></span> |
| <span data-ttu-id="787bb-134">Nueva entidad **Empleo de calendario de trabajador**</span><span class="sxs-lookup"><span data-stu-id="787bb-134">New **Worker calendar employment** entity</span></span> | <span data-ttu-id="787bb-135">Se ha agregado la entidad **Calendario de trabajo**</span><span class="sxs-lookup"><span data-stu-id="787bb-135">**Work calendar entity** added</span></span> |
| <span data-ttu-id="787bb-136">Nueva entidad **Detalle de puesto de nómina**</span><span class="sxs-lookup"><span data-stu-id="787bb-136">New **Payroll position detail** entity</span></span> | <span data-ttu-id="787bb-137">**Detalle de puesto de nómina** agregado</span><span class="sxs-lookup"><span data-stu-id="787bb-137">**Payroll position detail** added</span></span> |
| <span data-ttu-id="787bb-138">Nueva entidad **Cargo**</span><span class="sxs-lookup"><span data-stu-id="787bb-138">New **Title** entity</span></span> | <span data-ttu-id="787bb-139">**Cargo** agregado.</span><span class="sxs-lookup"><span data-stu-id="787bb-139">**Title** added.</span></span> <span data-ttu-id="787bb-140">La nueva entidad **Título** se incluirá en el proceso de sincronización entre Recursos Humanos y Dataverse.</span><span class="sxs-lookup"><span data-stu-id="787bb-140">The new **Title** entity will be included in the sync process between Human Resources and Dataverse.</span></span> <span data-ttu-id="787bb-141">No será referenciado inicialmente desde las entidades **Puesto de trabajo** o **Trabajo**.</span><span class="sxs-lookup"><span data-stu-id="787bb-141">It won't be initially referenced from **Job Position** or **Job** entities.</span></span> |

<span data-ttu-id="787bb-142">Durante las próximas semanas, estos cambios de entidad estarán disponibles en todos los entornos.</span><span class="sxs-lookup"><span data-stu-id="787bb-142">Over the next few weeks, these entity changes will be available in all environments.</span></span> <span data-ttu-id="787bb-143">Para instalar manualmente la última solución de Dataverse para Human Resources:</span><span class="sxs-lookup"><span data-stu-id="787bb-143">To manually install the latest Dataverse solution for Human Resources:</span></span>

1.  <span data-ttu-id="787bb-144">Vaya al [Centro de administración de Power Platform](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="787bb-144">Go to the [Power Platform Admin Center](https://admin.powerplatform.microsoft.com).</span></span>

2.  <span data-ttu-id="787bb-145">Seleccione **entornos**.</span><span class="sxs-lookup"><span data-stu-id="787bb-145">Select **Environments**.</span></span>

3.  <span data-ttu-id="787bb-146">Encuentre el entorno que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="787bb-146">Find the environment you want to upgrade.</span></span> <span data-ttu-id="787bb-147">El entorno debería corresponder a **Nombre del entorno** en la sección **Información de Common Data Service** en el formulario **Acerca de** en Human Resources.</span><span class="sxs-lookup"><span data-stu-id="787bb-147">The environment should correspond to **Environment name** in the **Common Data Service information** section in the **About** form in Human Resources.</span></span>

4.  <span data-ttu-id="787bb-148">Seleccione el entorno para ver los detalles del entorno.</span><span class="sxs-lookup"><span data-stu-id="787bb-148">Select the environment to view the environment details.</span></span>

5.  <span data-ttu-id="787bb-149">En la barra de acciones de la parte superior, seleccione **Administrar soluciones**.</span><span class="sxs-lookup"><span data-stu-id="787bb-149">In the action bar at the top, select **Manage Solutions**.</span></span> <span data-ttu-id="787bb-150">Se abrirá una nueva ventana del navegador y navegará al **Centro de administración de Dynamics 365** en el contexto de su entorno.</span><span class="sxs-lookup"><span data-stu-id="787bb-150">A new browser window will open and navigate to **Dynamics 365 Administration Center** in the context of your environment.</span></span>

6.  <span data-ttu-id="787bb-151">En la lista **Solución**, seleccione **Delimitar Dynamics 365 Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="787bb-151">In the **Solution** list, select **Dynamics 365 Human Resources Anchor**.</span></span>

7.  <span data-ttu-id="787bb-152">Seleccione **Actualizar** para aplicar la última solución.</span><span class="sxs-lookup"><span data-stu-id="787bb-152">Select **Upgrade** to apply the latest solution.</span></span>

## <a name="import-issues-with-the-leave-enrollment-data-entity-406082"></a><span data-ttu-id="787bb-153">Problemas de importación con la entidad de datos de inscripción de licencia (406082)</span><span class="sxs-lookup"><span data-stu-id="787bb-153">Import issues with the Leave enrollment data entity (406082)</span></span>

<span data-ttu-id="787bb-154">Ahora puede inscribir a un empleado en un nuevo plan de vacaciones del mismo tipo, siempre que la nueva fecha de inscripción sea posterior a la fecha de inscripción vencida del plan anterior.</span><span class="sxs-lookup"><span data-stu-id="787bb-154">You can now enroll an employee in a new leave plan of the same type, as long as the new enrollment date is later than the expired enrollment date of the previous plan.</span></span>

## <a name="issue-with-exporting-contribution-rates-in-the-401k-payrollworkerenrolledbenefitdetail-entity-in-dmf-420700"></a><span data-ttu-id="787bb-155">Problema con las tasas de contribución a la exportación en la entidad 401k payrollWorkerEnrolledBenefitDetail en DMF (420700)</span><span class="sxs-lookup"><span data-stu-id="787bb-155">Issue with exporting contribution rates in the 401k payrollWorkerEnrolledBenefitDetail entity in DMF (420700)</span></span>

<span data-ttu-id="787bb-156">Este cambio corrige la funcionalidad de exportación para la entidad **payrollWorkerEnrolledBenefitDetail** para reflejar los valores actuales de la contribución del empleador.</span><span class="sxs-lookup"><span data-stu-id="787bb-156">This change corrects the export functionality for the **payrollWorkerEnrolledBenefitDetail** entity to reflect the current values for employer contribution.</span></span>

## <a name="searching-in-the-streamlined-worker-form-causes-message-saying-person-field-must-be-filled-in-402525"></a><span data-ttu-id="787bb-157">La búsqueda en el formulario de trabajador optimizado provoca un mensaje que dice que se debe completar el campo Persona (402525)</span><span class="sxs-lookup"><span data-stu-id="787bb-157">Searching in the streamlined Worker form causes message saying Person field must be filled in (402525)</span></span>

<span data-ttu-id="787bb-158">Cuando busque un empleado, ya no recibirá un mensaje que indique que debe completar el campo **Persona**.</span><span class="sxs-lookup"><span data-stu-id="787bb-158">When you search for an employee, you'll no longer receive a message saying you must fill in the **Person** field.</span></span>

## <a name="note-field-value-doesnt-render-on-the-add-more-skills-form-380134"></a><span data-ttu-id="787bb-159">El valor del campo de nota no se muestra en el formulario Agregar más habilidades (380134)</span><span class="sxs-lookup"><span data-stu-id="787bb-159">Note field value doesn't render on the Add more skills form (380134)</span></span>

<span data-ttu-id="787bb-160">Este cambio corrige un problema cuando personaliza el formulario **Agregar más habilidades** en Autoservicio para empleados.</span><span class="sxs-lookup"><span data-stu-id="787bb-160">This change corrects an issue when you personalize the **Add more skills** form in Employee self service.</span></span>

## <a name="multiple-fixed-compensation-plans-dont-expire-when-transferring-employees-389466"></a><span data-ttu-id="787bb-161">Los planes de compensación fija múltiple no caducan cuando se transfieren empleados (389466)</span><span class="sxs-lookup"><span data-stu-id="787bb-161">Multiple fixed compensation plans don't expire when transferring employees (389466)</span></span>

<span data-ttu-id="787bb-162">Con este cambio, todos los registros activos de compensación fija para la posición anterior caducarán en la fecha de transición.</span><span class="sxs-lookup"><span data-stu-id="787bb-162">With this change, all active fixed compensation records for the old position will expire on the transition date.</span></span>

## <a name="in-preview"></a><span data-ttu-id="787bb-163">En vista previa</span><span class="sxs-lookup"><span data-stu-id="787bb-163">In preview</span></span>

<span data-ttu-id="787bb-164">Las siguientes características de vista previa están disponibles desde el 3 de febrero de 2020:</span><span class="sxs-lookup"><span data-stu-id="787bb-164">The following preview features became available on February 3, 2020:</span></span>

- <span data-ttu-id="787bb-165">**Características de vista previa de permisos y ausencias**: para obtener más información, consulte [Características de vista previa para permisos y ausencias](hr-leave-and-absence-overview.md?leave-and-absence-preview-features).</span><span class="sxs-lookup"><span data-stu-id="787bb-165">**Leave and absence preview features** - For more information, see [Leave and absence preview features](hr-leave-and-absence-overview.md?leave-and-absence-preview-features).</span></span>

- <span data-ttu-id="787bb-166">**Característica de vista previa de administración de prestaciones**: para obtener más información, incluidos los problemas conocidos, consulte [Visión general de la administración de prestaciones](hr-benefits-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="787bb-166">**Benefits management preview feature** - For more information, including known issues, see [Benefits management overview](hr-benefits-management-overview.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="787bb-167">Consulte también</span><span class="sxs-lookup"><span data-stu-id="787bb-167">See also</span></span>

[<span data-ttu-id="787bb-168">Novedades y cambios en Human Resources</span><span class="sxs-lookup"><span data-stu-id="787bb-168">What's new or changed in Human Resources</span></span>](hr-admin-whats-new.md)</br>
[<span data-ttu-id="787bb-169">Visión general de Dynamics 365 Human Resources 2019 en el segundo lanzamiento de versiones</span><span class="sxs-lookup"><span data-stu-id="787bb-169">Overview of Dynamics 365 Human Resources 2019 release wave 2</span></span>](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[<span data-ttu-id="787bb-170">Actualizar proceso</span><span class="sxs-lookup"><span data-stu-id="787bb-170">Update process</span></span>](hr-admin-setup-update-process.md)</br>
[<span data-ttu-id="787bb-171">Administrar características</span><span class="sxs-lookup"><span data-stu-id="787bb-171">Manage features</span></span>](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]