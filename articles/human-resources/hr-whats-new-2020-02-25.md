---
title: Novedades y cambios en Dynamics 365 Human Resources (25 de febrero de 2020)
description: Este artículo describe las características que son nuevas o que se han cambiado en Microsoft Dynamics 365 Human Resources para el 25 de febrero de 2020.
author: Darinkramer
manager: AnnBe
ms.date: 02/25/2020
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
ms.search.validFrom: 2020-02-25
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 1302686aeba52de484ad520efe292fafefc39ebf
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2020
ms.locfileid: "4526819"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-february-25-2020"></a><span data-ttu-id="14c76-103">Novedades y cambios en Dynamics 365 Human Resources (25 de febrero de 2020)</span><span class="sxs-lookup"><span data-stu-id="14c76-103">What's new or changed in Dynamics 365 Human Resources (February 25, 2020)</span></span>

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="14c76-104">Este artículo describe las características que son nuevas o que se han cambiado en Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="14c76-104">This article describes features that are either new or changed in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="14c76-105">Los cambios se aplican al número de compilación 8.1.2927.</span><span class="sxs-lookup"><span data-stu-id="14c76-105">Changes apply to build number 8.1.2927.</span></span> <span data-ttu-id="14c76-106">Los números entre paréntesis en algunos encabezados hacen referencia a los números de soporte en (LCS) para su referencia.</span><span class="sxs-lookup"><span data-stu-id="14c76-106">The numbers in parentheses in some headings refer to LCS support numbers for reference.</span></span>

## <a name="enable-case-management-navigation-and-data-management-framework-dmf-entity-414754"></a><span data-ttu-id="14c76-107">Habilitar la navegación de Administración de caso y el marco de administración de datos (DMF) de la entidad (414754)</span><span class="sxs-lookup"><span data-stu-id="14c76-107">Enable Case Management navigation and data management framework (DMF) entity (414754)</span></span>

<span data-ttu-id="14c76-108">Esta característica de vista previa permite una navegación adicional a casos de administración de casos.</span><span class="sxs-lookup"><span data-stu-id="14c76-108">This preview feature enables additional navigation to case management cases.</span></span> <span data-ttu-id="14c76-109">Puede habilitar esta característica de vista previa en el espacio de trabajo **Gestión de funciones**.</span><span class="sxs-lookup"><span data-stu-id="14c76-109">You can enable this preview feature in the **Feature Management** workspace.</span></span> <span data-ttu-id="14c76-110">Estos elementos de menú aparecen en el espacio de trabajo **Conformidad** de Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="14c76-110">These menu items appear in the **Compliance** workspace of Dynamics 365 Human Resources.</span></span> <span data-ttu-id="14c76-111">Con este cambio, Human Resources puede acceder a:</span><span class="sxs-lookup"><span data-stu-id="14c76-111">With this change, Human Resources can access:</span></span>

- <span data-ttu-id="14c76-112">Todos los casos</span><span class="sxs-lookup"><span data-stu-id="14c76-112">All cases</span></span>
- <span data-ttu-id="14c76-113">Mis casos</span><span class="sxs-lookup"><span data-stu-id="14c76-113">My cases</span></span>
- <span data-ttu-id="14c76-114">Mis casos abiertos</span><span class="sxs-lookup"><span data-stu-id="14c76-114">My open cases</span></span>
- <span data-ttu-id="14c76-115">Mis casos vencidos</span><span class="sxs-lookup"><span data-stu-id="14c76-115">My overdue cases</span></span>
- <span data-ttu-id="14c76-116">Casos asignados a mí mediante el flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="14c76-116">Cases assigned to me through workflow</span></span>

<span data-ttu-id="14c76-117">Junto con estas nuevas vistas de casos, también está disponible la entidad DMF **Detalle del caso**.</span><span class="sxs-lookup"><span data-stu-id="14c76-117">Along with these new views into cases, the **Case detail** DMF entity is also available.</span></span>

## <a name="enable-relationship-definitions-in-global-address-bbook-414762"></a><span data-ttu-id="14c76-118">Habilitar definiciones de relación en la libreta de direcciones global (414762)</span><span class="sxs-lookup"><span data-stu-id="14c76-118">Enable Relationship definitions in global address bBook (414762)</span></span>

<span data-ttu-id="14c76-119">Las relaciones ahora están habilitadas en la libreta de direcciones global.</span><span class="sxs-lookup"><span data-stu-id="14c76-119">Relationships are now enabled in the global address book.</span></span> <span data-ttu-id="14c76-120">Antes del lanzamiento de esta semana, el cuadro de información **Relación** de hechos mostraba las relaciones definidas por el sistema.</span><span class="sxs-lookup"><span data-stu-id="14c76-120">Prior to this week's release, the **Relationship** fact box displayed any system-defined relationships.</span></span> <span data-ttu-id="14c76-121">Ahora puede definir esas relaciones dentro de la página de la libreta de direcciones global.</span><span class="sxs-lookup"><span data-stu-id="14c76-121">Now you can define those relationships within the global address book page.</span></span>

## <a name="a-position-can-be-removed-when-active-compensation-records-exist-for-the-position-414568"></a><span data-ttu-id="14c76-122">Se puede eliminar una posición cuando existen registros de compensación activos para la posición (414568)</span><span class="sxs-lookup"><span data-stu-id="14c76-122">A position can be removed when active compensation records exist for the position (414568)</span></span>

<span data-ttu-id="14c76-123">Con este cambio, aparece una advertencia cuando intenta eliminar un puesto y un trabajador tiene un registro de compensación activo para ese mismo puesto.</span><span class="sxs-lookup"><span data-stu-id="14c76-123">With this change, a warning appears when you attempt to delete a position and a worker has an active compensation record for that same position.</span></span> <span data-ttu-id="14c76-124">Cuando esto sucede, debe actualizar el registro de compensación fija del empleado antes de eliminar el puesto.</span><span class="sxs-lookup"><span data-stu-id="14c76-124">When this happens, you must update the employee fixed compensation record before removing the position.</span></span>

## <a name="performance-review-workflow-occasionally-adds-sign-offs-from-people-who-are-not-part-of-the-process-414171"></a><span data-ttu-id="14c76-125">El flujo de trabajo de revisión de rendimiento ocasionalmente agrega aprobaciones de personas que no forman parte del proceso (414171)</span><span class="sxs-lookup"><span data-stu-id="14c76-125">Performance review workflow occasionally adds sign-offs from people who are not part of the process (414171)</span></span>

<span data-ttu-id="14c76-126">Este cambio corrige un problema en el que se agregan participantes adicionales a la revisión del desempeño.</span><span class="sxs-lookup"><span data-stu-id="14c76-126">This change corrects an issue where additional sign-off participants are added to the performance review.</span></span>

## <a name="worker-position-assignment-not-created-in-common-data-service-when-selected-on-the-new-worker-dialog-413479"></a><span data-ttu-id="14c76-127">Asignación de puesto de trabajo no creada en Common Data Service cuando se selecciona en el cuadro de diálogo Nuevo trabajador (413479)</span><span class="sxs-lookup"><span data-stu-id="14c76-127">Worker position assignment not created in Common Data Service when selected on the New Worker dialog (413479)</span></span>

<span data-ttu-id="14c76-128">Este cambio corrige un problema cuando se contrata a un nuevo trabajador y se asigna al nuevo empleado a un puesto a través del diálogo **Nuevo trabajador**.</span><span class="sxs-lookup"><span data-stu-id="14c76-128">This change corrects an issue when hiring a new worker and assigning the new hire to a position through the **New worker** dialog.</span></span> <span data-ttu-id="14c76-129">Ahora la asignación de posición se refleja en Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="14c76-129">Now the position assignment is reflected in Common Data Service.</span></span>

## <a name="coming-soon"></a><span data-ttu-id="14c76-130">Próximamente</span><span class="sxs-lookup"><span data-stu-id="14c76-130">Coming soon</span></span>

### <a name="updated-common-data-service-solution"></a><span data-ttu-id="14c76-131">Solución Common Data Service actualizada</span><span class="sxs-lookup"><span data-stu-id="14c76-131">Updated Common Data Service solution</span></span>

<span data-ttu-id="14c76-132">Una nueva solución Common Data Service estará disponible pronto con los siguientes cambios:</span><span class="sxs-lookup"><span data-stu-id="14c76-132">A new Common Data Service solution will be available soon with the following changes:</span></span>

| <span data-ttu-id="14c76-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="14c76-133">Description</span></span> | <span data-ttu-id="14c76-134">Cambio</span><span class="sxs-lookup"><span data-stu-id="14c76-134">Change</span></span> |
| ----------------------------------------- | --- |
| <span data-ttu-id="14c76-135">La entidad **Puesto de trabajo** cambia</span><span class="sxs-lookup"><span data-stu-id="14c76-135">**Job/Position** entity changes</span></span> | <span data-ttu-id="14c76-136">Se ha agregado **Región de compensación**</span><span class="sxs-lookup"><span data-stu-id="14c76-136">**Compensation region** added</span></span></br><span data-ttu-id="14c76-137">Se ha agregado **Dimensiones financieras**</span><span class="sxs-lookup"><span data-stu-id="14c76-137">**Financial dimensions** added</span></span> |
| <span data-ttu-id="14c76-138">La entidad **Trabajador** cambia</span><span class="sxs-lookup"><span data-stu-id="14c76-138">**Worker** entity changes</span></span> | <span data-ttu-id="14c76-139">Se ha agregado **Orden del nombre**</span><span class="sxs-lookup"><span data-stu-id="14c76-139">**Name sequence** added</span></span></br><span data-ttu-id="14c76-140">Se ha agregado **Trabaja desde casa**</span><span class="sxs-lookup"><span data-stu-id="14c76-140">**Works from home** added</span></span></br><span data-ttu-id="14c76-141">Se ha agregado **Idioma**</span><span class="sxs-lookup"><span data-stu-id="14c76-141">**Language** added</span></span></br><span data-ttu-id="14c76-142">Se ha agregado **Antigüedad**</span><span class="sxs-lookup"><span data-stu-id="14c76-142">**Seniority date** added</span></span></br><span data-ttu-id="14c76-143">Se ha agregado **Fecha de aniversario**</span><span class="sxs-lookup"><span data-stu-id="14c76-143">**Anniversary date** added</span></span></br><span data-ttu-id="14c76-144">Se ha agregado **Fecha de contratación original**</span><span class="sxs-lookup"><span data-stu-id="14c76-144">**Original hire date** added</span></span> |
| <span data-ttu-id="14c76-145">La entidad **Empleo** cambia</span><span class="sxs-lookup"><span data-stu-id="14c76-145">**Employment** entity changes</span></span> | <span data-ttu-id="14c76-146">Se ha agregado **Dimensiones financieras**</span><span class="sxs-lookup"><span data-stu-id="14c76-146">**Financial dimensions** added</span></span></br><span data-ttu-id="14c76-147">Se ha agregado **Razón de la finalización**</span><span class="sxs-lookup"><span data-stu-id="14c76-147">**Termination reason** added</span></span></br><span data-ttu-id="14c76-148">**Fecha de finalización** ha cambiado de nombre a **Fecha de transición**</span><span class="sxs-lookup"><span data-stu-id="14c76-148">**Termination date** renamed from **Transition date**</span></span></br><span data-ttu-id="14c76-149">Se ha agregado **Fechas del período de pruebas**</span><span class="sxs-lookup"><span data-stu-id="14c76-149">**Probation date** added</span></span> |
| <span data-ttu-id="14c76-150">La entidad **Dirección del trabajador** cambia</span><span class="sxs-lookup"><span data-stu-id="14c76-150">**Worker address** entity changes</span></span> | <span data-ttu-id="14c76-151">Se ha agregado **Dirección postal**</span><span class="sxs-lookup"><span data-stu-id="14c76-151">**Street address** added</span></span></br><span data-ttu-id="14c76-152">**Línea de dirección 1**, **Línea de dirección 2** y **Línea de dirección 3** marcadas para eliminación</span><span class="sxs-lookup"><span data-stu-id="14c76-152">**Address line 1**, **Address line 2**, and **Address line 3** marked for deprecation</span></span> |
| <span data-ttu-id="14c76-153">Nuevas entidades de configuración de compensación variable</span><span class="sxs-lookup"><span data-stu-id="14c76-153">New variable compensation setup entities</span></span> | <span data-ttu-id="14c76-154">**Tipo de plan de compensación variable**</span><span class="sxs-lookup"><span data-stu-id="14c76-154">**Compensation variable plan type**</span></span></br><span data-ttu-id="14c76-155">**Plan de compensación variable**</span><span class="sxs-lookup"><span data-stu-id="14c76-155">**Compensation variable plan**</span></span></br><span data-ttu-id="14c76-156">**Reglas de atribución**</span><span class="sxs-lookup"><span data-stu-id="14c76-156">**Vesting rules**</span></span></br><span data-ttu-id="14c76-157">**Nivel de plan de compensación variable**</span><span class="sxs-lookup"><span data-stu-id="14c76-157">**Compensation variable plan level**</span></span> |
| <span data-ttu-id="14c76-158">Nueva entidad **Empleo de calendario de trabajador**</span><span class="sxs-lookup"><span data-stu-id="14c76-158">New **Worker calendar employment** entity</span></span> | <span data-ttu-id="14c76-159">Se ha agregado la entidad **Calendario de trabajo**</span><span class="sxs-lookup"><span data-stu-id="14c76-159">**Work calendar entity** added</span></span> |
| <span data-ttu-id="14c76-160">Nueva entidad **Detalle de puesto de nómina**</span><span class="sxs-lookup"><span data-stu-id="14c76-160">New **Payroll position detail** entity</span></span> | <span data-ttu-id="14c76-161">**Detalle de puesto de nómina** agregado</span><span class="sxs-lookup"><span data-stu-id="14c76-161">**Payroll position detail** added</span></span> |
| <span data-ttu-id="14c76-162">Nueva entidad **Cargo**</span><span class="sxs-lookup"><span data-stu-id="14c76-162">New **Title** entity</span></span> | <span data-ttu-id="14c76-163">**Cargo** agregado.</span><span class="sxs-lookup"><span data-stu-id="14c76-163">**Title** added.</span></span> <span data-ttu-id="14c76-164">La nueva entidad **Título** se incluirá en el proceso de sincronización entre Recursos Humanos y Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="14c76-164">The new **Title** entity will be included in the sync process between Human Resources and Common Data Service.</span></span> <span data-ttu-id="14c76-165">No será referenciado inicialmente desde las entidades **Puesto de trabajo** o **Trabajo**.</span><span class="sxs-lookup"><span data-stu-id="14c76-165">It won't be initially referenced from **Job Position** or **Job** entities.</span></span> |

<span data-ttu-id="14c76-166">Durante las próximas semanas, estos cambios de entidad estarán disponibles en todos los entornos.</span><span class="sxs-lookup"><span data-stu-id="14c76-166">Over the next few weeks, these entity changes will be available in all environments.</span></span> <span data-ttu-id="14c76-167">Para instalar manualmente la última solución de Common Data Service para Human Resources:</span><span class="sxs-lookup"><span data-stu-id="14c76-167">To manually install the latest Common Data Service solution for Human Resources:</span></span>

1.  <span data-ttu-id="14c76-168">Vaya al [Centro de administración de Power Platform](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="14c76-168">Go to the [Power Platform Admin Center](https://admin.powerplatform.microsoft.com).</span></span>

2.  <span data-ttu-id="14c76-169">Seleccione **entornos**.</span><span class="sxs-lookup"><span data-stu-id="14c76-169">Select **Environments**.</span></span>

3.  <span data-ttu-id="14c76-170">Encuentre el entorno que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="14c76-170">Find the environment you want to upgrade.</span></span> <span data-ttu-id="14c76-171">Esto debería corresponder a **Nombre del entorno** en la sección **Información de Common Data Service** en el formulario **Acerca de** en Human Resources.</span><span class="sxs-lookup"><span data-stu-id="14c76-171">This should correspond to **Environment name** in the **Common Data Service information** section in the **About** form in Human Resources.</span></span>

4.  <span data-ttu-id="14c76-172">Seleccione el entorno para ver los detalles del entorno.</span><span class="sxs-lookup"><span data-stu-id="14c76-172">Select the environment to view the environment details.</span></span>

5.  <span data-ttu-id="14c76-173">En la barra de acciones de la parte superior, seleccione **Administrar soluciones**.</span><span class="sxs-lookup"><span data-stu-id="14c76-173">In the action bar at the top, select **Manage Solutions**.</span></span> <span data-ttu-id="14c76-174">Se abrirá una nueva ventana del navegador y navegará al **Centro de administración de Dynamics 365** en el contexto de su entorno.</span><span class="sxs-lookup"><span data-stu-id="14c76-174">A new browser window will open and navigate to **Dynamics 365 Administration Center** in the context of your environment.</span></span>

6.  <span data-ttu-id="14c76-175">En la lista **Solución**, seleccione **Delimitar Dynamics 365 Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="14c76-175">In the **Solution** list, select **Dynamics 365 Human Resources Anchor**.</span></span>

7.  <span data-ttu-id="14c76-176">Seleccione **Actualizar** para aplicar la última solución.</span><span class="sxs-lookup"><span data-stu-id="14c76-176">Select **Upgrade** to apply the latest solution.</span></span>

## <a name="in-preview"></a><span data-ttu-id="14c76-177">En vista previa</span><span class="sxs-lookup"><span data-stu-id="14c76-177">In preview</span></span>

<span data-ttu-id="14c76-178">Las siguientes características de vista previa están disponibles desde el 3 de febrero de 2020:</span><span class="sxs-lookup"><span data-stu-id="14c76-178">The following preview features became available on February 3, 2020:</span></span>

- <span data-ttu-id="14c76-179">**Características de vista previa de permisos y ausencias**: para obtener más información, consulte [Características de vista previa para permisos y ausencias](hr-leave-and-absence-overview.md?leave-and-absence-preview-features).</span><span class="sxs-lookup"><span data-stu-id="14c76-179">**Leave and absence preview features** - For more information, see [Leave and absence preview features](hr-leave-and-absence-overview.md?leave-and-absence-preview-features).</span></span>

- <span data-ttu-id="14c76-180">**Característica de vista previa de administración de prestaciones**: para obtener más información, incluidos los problemas conocidos, consulte [Visión general de la administración de prestaciones](hr-benefits-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="14c76-180">**Benefits management preview feature** - For more information, including known issues, see [Benefits management overview](hr-benefits-management-overview.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="14c76-181">Consulte también</span><span class="sxs-lookup"><span data-stu-id="14c76-181">See also</span></span>

[<span data-ttu-id="14c76-182">Novedades y cambios en Human Resources</span><span class="sxs-lookup"><span data-stu-id="14c76-182">What's new or changed in Human Resources</span></span>](hr-admin-whats-new.md)</br>
[<span data-ttu-id="14c76-183">Visión general de Dynamics 365 Human Resources 2019 en el segundo lanzamiento de versiones</span><span class="sxs-lookup"><span data-stu-id="14c76-183">Overview of Dynamics 365 Human Resources 2019 release wave 2</span></span>](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[<span data-ttu-id="14c76-184">Actualizar proceso</span><span class="sxs-lookup"><span data-stu-id="14c76-184">Update process</span></span>](hr-admin-setup-update-process.md)</br>
[<span data-ttu-id="14c76-185">Administrar características</span><span class="sxs-lookup"><span data-stu-id="14c76-185">Manage features</span></span>](hr-admin-manage-features.md)