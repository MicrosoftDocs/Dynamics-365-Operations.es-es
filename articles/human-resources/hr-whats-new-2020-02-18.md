---
title: Novedades y cambios en Dynamics 365 Human Resources (18 de febrero de 2020)
description: Este artículo describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Human Resources para el 18 de febrero de 2020.
author: andreabichsel
ms.date: 02/18/2020
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
ms.search.validFrom: 2020-02-18
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 6c28d0dc76195cc0aedc132f348a229af0421c43
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5790437"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-february-18-2020"></a><span data-ttu-id="ba851-103">Novedades y cambios en Dynamics 365 Human Resources (18 de febrero de 2020)</span><span class="sxs-lookup"><span data-stu-id="ba851-103">What's new or changed in Dynamics 365 Human Resources (February 18, 2020)</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="ba851-104">Este artículo describe las características que son nuevas o que se han cambiado en Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="ba851-104">This article describes features that are either new or changed in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="ba851-105">Los cambios se aplican al número de compilación 8.1.2903.</span><span class="sxs-lookup"><span data-stu-id="ba851-105">Changes apply to build number 8.1.2903.</span></span> <span data-ttu-id="ba851-106">Los números entre paréntesis en algunos encabezados hacen referencia a los números de soporte en (LCS) para su referencia.</span><span class="sxs-lookup"><span data-stu-id="ba851-106">The numbers in parentheses in some headings refer to LCS support numbers for reference.</span></span>

## <a name="platform-update-32"></a><span data-ttu-id="ba851-107">Actualización 32 de la plataforma</span><span class="sxs-lookup"><span data-stu-id="ba851-107">Platform update 32</span></span> 

<span data-ttu-id="ba851-108">La Platform update 32 ya está disponible.</span><span class="sxs-lookup"><span data-stu-id="ba851-108">Platform update 32 is now available.</span></span> <span data-ttu-id="ba851-109">Para obtener más información, consulte [Novedades o cambios en Platform update 32 para Finance and Operations (febrero de 2020)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-update-32).</span><span class="sxs-lookup"><span data-stu-id="ba851-109">For more information, see [What's new or changed in Platform update 32 for Finance and Operations (February 2020)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-update-32).</span></span>

## <a name="search-values-are-remembered-when-changing-view-options-in-streamlined-employee-form-383833"></a><span data-ttu-id="ba851-110">Los valores de búsqueda se recuerdan al cambiar las opciones de vista en forma de empleado optimizada (383833)</span><span class="sxs-lookup"><span data-stu-id="ba851-110">Search values are remembered when changing view options in streamlined employee form (383833)</span></span>

<span data-ttu-id="ba851-111">El nuevo formulario **Trabajador** ahora recuerda los valores de búsqueda cuando cambia las opciones de vista y aplica los cambios.</span><span class="sxs-lookup"><span data-stu-id="ba851-111">The new **Worker** form now remembers  search values when you change the view options and apply changes.</span></span>

## <a name="compensation-management-summary-tiles-in-preview-feature-redirect-to-wrong-form-401861"></a><span data-ttu-id="ba851-112">Los mosaicos de resumen de administración de compensación en la característica de vista previa redirigen a un formulario incorrecto (401861)</span><span class="sxs-lookup"><span data-stu-id="ba851-112">Compensation management summary tiles in preview feature redirect to wrong form (401861)</span></span>

<span data-ttu-id="ba851-113">Los mosaicos de administración de compensación fija y variable ahora muestran los registros correctos en el nuevo formulario **Trabajador**.</span><span class="sxs-lookup"><span data-stu-id="ba851-113">Fixed and variable compensation management tiles now display the correct records in the new **Worker** form.</span></span> <span data-ttu-id="ba851-114">Se aplica solo a la función optimizada de vista previa del formulario de empleado.</span><span class="sxs-lookup"><span data-stu-id="ba851-114">Applies only to the streamlined employee form preview feature.</span></span> <span data-ttu-id="ba851-115">Puede habilitar esta característica de vista previa en **Gestión de funciones**.</span><span class="sxs-lookup"><span data-stu-id="ba851-115">You can enable this preview feature in **Feature management**.</span></span> <span data-ttu-id="ba851-116">Para obtener más información, vea [Administrar funciones](hr-admin-manage-features.md).</span><span class="sxs-lookup"><span data-stu-id="ba851-116">For more information, see [Manage features](hr-admin-manage-features.md).</span></span>

## <a name="empty-status-field-for-some-leave-request-records-in-dataverse-414915"></a><span data-ttu-id="ba851-117">Campo de estado vacío para algunos registros de solicitud de licencia en Dataverse (414915)</span><span class="sxs-lookup"><span data-stu-id="ba851-117">Empty Status field for some leave request records in Dataverse (414915)</span></span>

<span data-ttu-id="ba851-118">Este cambio corrige un problema en Dataverse cuando el campo **Estado** en una solicitud de baja se establece en **Revisión**.</span><span class="sxs-lookup"><span data-stu-id="ba851-118">This change corrects an issue in Dataverse when the **Status** field in a leave request is set to **Review**.</span></span> <span data-ttu-id="ba851-119">Dataverse ahora refleja el estado.</span><span class="sxs-lookup"><span data-stu-id="ba851-119">Dataverse now reflects the status.</span></span>

## <a name="skill-gap-analysis-only-possible-for-assigned-job-411390"></a><span data-ttu-id="ba851-120">El análisis de lagunas de habilidades solo es posible para el trabajo asignado (411390)</span><span class="sxs-lookup"><span data-stu-id="ba851-120">Skill gap analysis only possible for assigned job (411390)</span></span>

<span data-ttu-id="ba851-121">Ahora puede hacer un análisis de lagunas de habilidades en cualquier trabajo definido en Recursos Humanos.</span><span class="sxs-lookup"><span data-stu-id="ba851-121">You can now do a skill gap analysis on any job defined in Human Resources.</span></span>

## <a name="system-currency-doesnt-sync-from-dataverse-to-human-resources-in-new-environments-418011"></a><span data-ttu-id="ba851-122">La divisa del sistema no se sincroniza desde Dataverse a Recursos humanos en nuevos entornos (418011)</span><span class="sxs-lookup"><span data-stu-id="ba851-122">System currency doesn't sync from Dataverse to Human Resources in new environments (418011)</span></span>

<span data-ttu-id="ba851-123">La divisa del sistema en Dataverse ahora se puede sincronizar con Recursos humanos.</span><span class="sxs-lookup"><span data-stu-id="ba851-123">The system currency in Dataverse can now sync to Human Resources.</span></span>

## <a name="in-preview"></a><span data-ttu-id="ba851-124">En vista previa</span><span class="sxs-lookup"><span data-stu-id="ba851-124">In preview</span></span>

- [<span data-ttu-id="ba851-125">Características de vista previa para permisos y ausencias</span><span class="sxs-lookup"><span data-stu-id="ba851-125">Leave and absence preview features</span></span>](hr-leave-and-absence-overview.md?leave-and-absence-preview-features)

- [<span data-ttu-id="ba851-126">Característica de vista previa: administración de prestaciones</span><span class="sxs-lookup"><span data-stu-id="ba851-126">Benefits management preview features</span></span>](hr-benefits-management-overview.md)

## <a name="coming-soon"></a><span data-ttu-id="ba851-127">Próximamente</span><span class="sxs-lookup"><span data-stu-id="ba851-127">Coming soon</span></span>

### <a name="updated-dataverse-solution"></a><span data-ttu-id="ba851-128">Solución Dataverse actualizada</span><span class="sxs-lookup"><span data-stu-id="ba851-128">Updated Dataverse solution</span></span>

<span data-ttu-id="ba851-129">Una nueva solución Dataverse estará disponible pronto con los siguientes cambios:</span><span class="sxs-lookup"><span data-stu-id="ba851-129">A new Dataverse solution will be available soon with the following changes:</span></span>

| <span data-ttu-id="ba851-130">Descripción</span><span class="sxs-lookup"><span data-stu-id="ba851-130">Description</span></span> | <span data-ttu-id="ba851-131">Cambio</span><span class="sxs-lookup"><span data-stu-id="ba851-131">Change</span></span> |
| ----------------------------------------- | --- |
| <span data-ttu-id="ba851-132">La entidad **Puesto de trabajo** cambia</span><span class="sxs-lookup"><span data-stu-id="ba851-132">**Job/Position** entity changes</span></span> | <span data-ttu-id="ba851-133">Se ha agregado **Región de compensación**</span><span class="sxs-lookup"><span data-stu-id="ba851-133">**Compensation region** added</span></span></br><span data-ttu-id="ba851-134">Se ha agregado **Dimensiones financieras**</span><span class="sxs-lookup"><span data-stu-id="ba851-134">**Financial dimensions** added</span></span> |
| <span data-ttu-id="ba851-135">La entidad **Trabajador** cambia</span><span class="sxs-lookup"><span data-stu-id="ba851-135">**Worker** entity changes</span></span> | <span data-ttu-id="ba851-136">Se ha agregado **Orden del nombre**</span><span class="sxs-lookup"><span data-stu-id="ba851-136">**Name sequence** added</span></span></br><span data-ttu-id="ba851-137">Se ha agregado **Trabaja desde casa**</span><span class="sxs-lookup"><span data-stu-id="ba851-137">**Works from home** added</span></span></br><span data-ttu-id="ba851-138">Se ha agregado **Idioma**</span><span class="sxs-lookup"><span data-stu-id="ba851-138">**Language** added</span></span></br><span data-ttu-id="ba851-139">Se ha agregado **Antigüedad**</span><span class="sxs-lookup"><span data-stu-id="ba851-139">**Seniority date** added</span></span></br><span data-ttu-id="ba851-140">Se ha agregado **Fecha de aniversario**</span><span class="sxs-lookup"><span data-stu-id="ba851-140">**Anniversary date** added</span></span></br><span data-ttu-id="ba851-141">Se ha agregado **Fecha de contratación original**</span><span class="sxs-lookup"><span data-stu-id="ba851-141">**Original hire date** added</span></span> |
| <span data-ttu-id="ba851-142">La entidad **Empleo** cambia</span><span class="sxs-lookup"><span data-stu-id="ba851-142">**Employment** entity changes</span></span> | <span data-ttu-id="ba851-143">Se ha agregado **Dimensiones financieras**</span><span class="sxs-lookup"><span data-stu-id="ba851-143">**Financial dimensions** added</span></span></br><span data-ttu-id="ba851-144">Se ha agregado **Razón de la finalización**</span><span class="sxs-lookup"><span data-stu-id="ba851-144">**Termination reason** added</span></span></br><span data-ttu-id="ba851-145">**Fecha de finalización** ha cambiado de nombre a **Fecha de transición**</span><span class="sxs-lookup"><span data-stu-id="ba851-145">**Termination date** renamed from **Transition date**</span></span></br><span data-ttu-id="ba851-146">Se ha agregado **Fechas del período de pruebas**</span><span class="sxs-lookup"><span data-stu-id="ba851-146">**Probation date** added</span></span> |
| <span data-ttu-id="ba851-147">La entidad **Dirección del trabajador** cambia</span><span class="sxs-lookup"><span data-stu-id="ba851-147">**Worker address** entity changes</span></span> | <span data-ttu-id="ba851-148">Se ha agregado **Dirección postal**</span><span class="sxs-lookup"><span data-stu-id="ba851-148">**Street address** added</span></span></br><span data-ttu-id="ba851-149">**Línea de dirección 1**, **Línea de dirección 2** y **Línea de dirección 3** marcadas para eliminación</span><span class="sxs-lookup"><span data-stu-id="ba851-149">**Address line 1**, **Address line 2**, and **Address line 3** marked for deprecation</span></span> |
| <span data-ttu-id="ba851-150">Nuevas entidades de configuración de compensación variable</span><span class="sxs-lookup"><span data-stu-id="ba851-150">New variable compensation setup entities</span></span> | <span data-ttu-id="ba851-151">**Tipo de plan de compensación variable**</span><span class="sxs-lookup"><span data-stu-id="ba851-151">**Compensation variable plan type**</span></span></br><span data-ttu-id="ba851-152">**Plan de compensación variable**</span><span class="sxs-lookup"><span data-stu-id="ba851-152">**Compensation variable plan**</span></span></br><span data-ttu-id="ba851-153">**Reglas de atribución**</span><span class="sxs-lookup"><span data-stu-id="ba851-153">**Vesting rules**</span></span></br><span data-ttu-id="ba851-154">**Nivel de plan de compensación variable**</span><span class="sxs-lookup"><span data-stu-id="ba851-154">**Compensation variable plan level**</span></span> |
| <span data-ttu-id="ba851-155">Nueva entidad **Empleo de calendario de trabajador**</span><span class="sxs-lookup"><span data-stu-id="ba851-155">New **Worker calendar employment** entity</span></span> | <span data-ttu-id="ba851-156">Se ha agregado la entidad **Calendario de trabajo**</span><span class="sxs-lookup"><span data-stu-id="ba851-156">**Work calendar entity** added</span></span> |
| <span data-ttu-id="ba851-157">Nueva entidad **Detalle de puesto de nómina**</span><span class="sxs-lookup"><span data-stu-id="ba851-157">New **Payroll position detail** entity</span></span> | <span data-ttu-id="ba851-158">**Detalle de puesto de nómina** agregado</span><span class="sxs-lookup"><span data-stu-id="ba851-158">**Payroll position detail** added</span></span> |
| <span data-ttu-id="ba851-159">Nueva entidad **Cargo**</span><span class="sxs-lookup"><span data-stu-id="ba851-159">New **Title** entity</span></span> | <span data-ttu-id="ba851-160">**Cargo** agregado.</span><span class="sxs-lookup"><span data-stu-id="ba851-160">**Title** added.</span></span> <span data-ttu-id="ba851-161">La nueva entidad **Título** se incluirá en el proceso de sincronización entre Recursos Humanos y Dataverse.</span><span class="sxs-lookup"><span data-stu-id="ba851-161">The new **Title** entity will be included in the sync process between Human Resources and Dataverse.</span></span> <span data-ttu-id="ba851-162">No será referenciado inicialmente desde las entidades **Puesto de trabajo** o **Trabajo**.</span><span class="sxs-lookup"><span data-stu-id="ba851-162">It won't be initially referenced from **Job Position** or **Job** entities.</span></span> |

## <a name="see-also"></a><span data-ttu-id="ba851-163">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ba851-163">See also</span></span>

[<span data-ttu-id="ba851-164">Novedades y cambios en Human Resources</span><span class="sxs-lookup"><span data-stu-id="ba851-164">What's new or changed in Human Resources</span></span>](hr-admin-whats-new.md)</br>
[<span data-ttu-id="ba851-165">Visión general de Dynamics 365 Human Resources 2019 en el segundo lanzamiento de versiones</span><span class="sxs-lookup"><span data-stu-id="ba851-165">Overview of Dynamics 365 Human Resources 2019 release wave 2</span></span>](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[<span data-ttu-id="ba851-166">Actualizar proceso</span><span class="sxs-lookup"><span data-stu-id="ba851-166">Update process</span></span>](hr-admin-setup-update-process.md)</br>
[<span data-ttu-id="ba851-167">Administrar características</span><span class="sxs-lookup"><span data-stu-id="ba851-167">Manage features</span></span>](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]