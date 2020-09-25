---
title: Crear un proyecto nuevo
description: En este tema se proporciona información sobre cómo crear un proyecto nuevo.
author: Yowelle
manager: AnnBe
ms.date: 09/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjProjectsListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 82022
ms.assetid: bd2fb375-84c6-428a-8e54-f0f719045898
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c8c52b8c1c86ea2f6e03cf439ba5930f1006ab4f
ms.sourcegitcommit: 241ada0945c72d769eaa70ae35aedbb6a3233fdf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "3760653"
---
# <a name="create-a-new-project"></a><span data-ttu-id="2adfa-103">Crear un proyecto nuevo</span><span class="sxs-lookup"><span data-stu-id="2adfa-103">Create a new project</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2adfa-104">Complete los siguientes pasos para crear un proyecto nuevo.</span><span class="sxs-lookup"><span data-stu-id="2adfa-104">Complete the following steps to create a new project.</span></span>

1. <span data-ttu-id="2adfa-105">En la página **Administración de proyectos**, seleccione **Nuevo proyecto** y especifique los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="2adfa-105">On the **Project management** page, select **New project**, and enter the following values:</span></span>

    - <span data-ttu-id="2adfa-106">**Tipo de proyecto:** Tiempo y material</span><span class="sxs-lookup"><span data-stu-id="2adfa-106">**Project type:** Time and material</span></span>
    - <span data-ttu-id="2adfa-107">**Nombre del proyecto:** Fase 2 de la actualización XYZ</span><span class="sxs-lookup"><span data-stu-id="2adfa-107">**Project name:** XYZ Upgrade Phase 2</span></span>
    - <span data-ttu-id="2adfa-108">**Grupo de proyectos:** TM\_WIP</span><span class="sxs-lookup"><span data-stu-id="2adfa-108">**Project group:** TM\_WIP</span></span>
    - <span data-ttu-id="2adfa-109">**Id. de contrato de proyecto:** 00000002</span><span class="sxs-lookup"><span data-stu-id="2adfa-109">**Project contract ID:** 00000002</span></span>

2. <span data-ttu-id="2adfa-110">Seleccione **Crear proyecto**.</span><span class="sxs-lookup"><span data-stu-id="2adfa-110">Select **Create project**.</span></span>

## <a name="assign-a-resource-to-a-project"></a><span data-ttu-id="2adfa-111">Asignar un recurso a un proyecto</span><span class="sxs-lookup"><span data-stu-id="2adfa-111">Assign a resource to a project</span></span>

1. <span data-ttu-id="2adfa-112">En la página **Trabajadores**, en la lista **Trabajadores**, seleccione el registro del trabajador para el que ha configurado anteriormente las competencias y abra el registro de trabajador.</span><span class="sxs-lookup"><span data-stu-id="2adfa-112">On the **Workers** page, in the **Workers** list, select the record for the worker that you previously set up competencies for, and open the worker record.</span></span>
2. <span data-ttu-id="2adfa-113">En el panel de acciones, en la pestaña **Proyecto**, en el grupo **Configuración**, seleccione **Asignar proyectos**.</span><span class="sxs-lookup"><span data-stu-id="2adfa-113">On the Action Pane, on the **Project** tab, in the **Setup** group, select **Assign projects**.</span></span>
3. <span data-ttu-id="2adfa-114">En la página **Asignaciones de proyecto de validación de recursos**, en la pestaña **Proyectos** del campo **Agregar el proyecto a los proyectos seleccionados**, filtre el proyecto **Fase 2 de la actualización XYZ**.</span><span class="sxs-lookup"><span data-stu-id="2adfa-114">On the **Resource validation project assignments** page, on the **Projects** tab, in the **Add the project to selected projects** field, filter on the **XYZ Upgrade Phase 2** project.</span></span>
4. <span data-ttu-id="2adfa-115">En el panel **Proyectos restantes**, seleccione un proyecto y, a continuación, haga clic en el botón de la flecha para agregarlo al panel **Proyectos seleccionados**.</span><span class="sxs-lookup"><span data-stu-id="2adfa-115">In the **Remaining projects** pane, select a project, and then select the arrow button to add it to the **Selected projects** pane.</span></span>

<span data-ttu-id="2adfa-116">Si es necesario, también puede asignar categorías para un recurso.</span><span class="sxs-lookup"><span data-stu-id="2adfa-116">You can also assign categories for a resource as you require.</span></span> <span data-ttu-id="2adfa-117">El tipo de categoría es **Coste** o **Ingresos**.</span><span class="sxs-lookup"><span data-stu-id="2adfa-117">The category type is either **Cost** or **Revenue**.</span></span> <span data-ttu-id="2adfa-118">La organización es la que se encarga de determinar el tipo de categoría.</span><span class="sxs-lookup"><span data-stu-id="2adfa-118">The category type is determined by your organization.</span></span> <span data-ttu-id="2adfa-119">Si no hay categorías asignadas para el recurso, Finance buscará la categoría predeterminada en los precios de hora para costes e ingresos.</span><span class="sxs-lookup"><span data-stu-id="2adfa-119">If no categories are assigned for a resource, Finance looks up the default category on hour prices for cost and revenue.</span></span>

## <a name="set-up-project-resource-and-role-characteristics"></a><span data-ttu-id="2adfa-120">Configurar características de rol y recursos de proyectos</span><span class="sxs-lookup"><span data-stu-id="2adfa-120">Set up project resource and role characteristics</span></span>

<span data-ttu-id="2adfa-121">Un director de proyecto puede usar la funcionalidad de recursos de proyecto para crear los roles que se requieren para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="2adfa-121">A project manager can use the project resourcing functionality to create the roles that are required for the project.</span></span> <span data-ttu-id="2adfa-122">Los roles se pueden usar cuando los recursos confirmados son aún desconocidos cuando estos se reservan.</span><span class="sxs-lookup"><span data-stu-id="2adfa-122">Roles can be used if confirmed resources are still unknown when resources are being reserved.</span></span> <span data-ttu-id="2adfa-123">Los roles se pueden reservar temporalmente como recursos planeados, de manera que pueda continuar las etapas de planificación de proyectos.</span><span class="sxs-lookup"><span data-stu-id="2adfa-123">Roles can be temporarily reserved as planned resources, so that you can continue the project planning stages.</span></span>

<span data-ttu-id="2adfa-124">[![Ejemplo de rol](./media/projectresourcing05.jpg)](./media/projectresourcing05.jpg)</span><span class="sxs-lookup"><span data-stu-id="2adfa-124">[![Example of a role](./media/projectresourcing05.jpg)](./media/projectresourcing05.jpg)</span></span> 

<span data-ttu-id="2adfa-125">**Escenario:** Se contrató a Contoso para completar un proyecto de tiempo y material que tiene una acta de constitución de proyecto aprobada.</span><span class="sxs-lookup"><span data-stu-id="2adfa-125">**Scenario:** Contoso was hired to complete a Time and material project that has an approved project charter.</span></span> <span data-ttu-id="2adfa-126">El director de proyecto junior aún está completando el ámbito del proyecto.</span><span class="sxs-lookup"><span data-stu-id="2adfa-126">The junior project manager is still completing the scope of the project.</span></span> <span data-ttu-id="2adfa-127">El responsable de recursos está identificando actualmente recursos específicos que se reservarán para trabajar en el nuevo proyecto.</span><span class="sxs-lookup"><span data-stu-id="2adfa-127">The resource manager is currently identifying specific resources that will be reserved to work on the new project.</span></span> <span data-ttu-id="2adfa-128">Debido a la naturaleza fundamental de proyecto, uno de los roles que el patrocinador de proyecto solicitó, es el de director de proyecto principal.</span><span class="sxs-lookup"><span data-stu-id="2adfa-128">Because of the critical nature of the project, the project sponsor requested Senior project manager as one of the roles.</span></span> <span data-ttu-id="2adfa-129">El director de recursos debe adquirir el nuevo recurso y definir el rol en el sistema, en el caso de que el director de proyecto junior requiera la información del recurso durante la planificación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="2adfa-129">The resource manager must acquire the new resource and define the role in the system in case the junior project manager requires the resource information during project planning.</span></span>

<span data-ttu-id="2adfa-130">Los siguientes pasos muestran cómo el director de recursos puede configurar el rol de director de proyecto principal y asociarle características de recursos.</span><span class="sxs-lookup"><span data-stu-id="2adfa-130">The following steps show how the resource manager can set up the Senior project manager role and associate resource characteristics with it.</span></span> <span data-ttu-id="2adfa-131">Más adelante, el rol se puede usar para buscar los recursos disponibles que coinciden con las competencias de recursos necesarias.</span><span class="sxs-lookup"><span data-stu-id="2adfa-131">Later, the role can be used to search for available resources that match the required resource competencies.</span></span>

1. <span data-ttu-id="2adfa-132">En la página **Configurar roles**, seleccione **Nuevo** y especifique los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="2adfa-132">On the **Setup roles** page, select **New**, and enter the following values:</span></span>

    - <span data-ttu-id="2adfa-133">**Id. de rol:** Director de proyecto principal</span><span class="sxs-lookup"><span data-stu-id="2adfa-133">**Role ID:** Senior Project Manager</span></span>
    - <span data-ttu-id="2adfa-134">**Descripción:** Director de proyecto principal</span><span class="sxs-lookup"><span data-stu-id="2adfa-134">**Description:** Senior Project Manager</span></span>

2. <span data-ttu-id="2adfa-135">Seleccione **Crear**.</span><span class="sxs-lookup"><span data-stu-id="2adfa-135">Select **Create**.</span></span>
3. <span data-ttu-id="2adfa-136">Seleccione el rol **Director de proyecto principal** y, a continuación, haga clic en **Configurar características**.</span><span class="sxs-lookup"><span data-stu-id="2adfa-136">Select the **Senior Project Manager** role, and then select **Configure characteristics**.</span></span>
4. <span data-ttu-id="2adfa-137">En el campo **Tipo de características**, seleccione **Aptitud**.</span><span class="sxs-lookup"><span data-stu-id="2adfa-137">In the **Characteristics type** field, select **Skill**.</span></span>
5. <span data-ttu-id="2adfa-138">En el campo **Características disponibles**, especifique el tipo de aptitud que desea buscar.</span><span class="sxs-lookup"><span data-stu-id="2adfa-138">In the **Available characteristics** field, enter the skill to search for.</span></span>
6. <span data-ttu-id="2adfa-139">En el campo **Tipo de característica**, seleccione **Certificado**.</span><span class="sxs-lookup"><span data-stu-id="2adfa-139">In the **Characteristic type** field, select **Certificate**.</span></span>
7. <span data-ttu-id="2adfa-140">En el campo **Características disponibles**, especifique el tipo de certificado que desea buscar.</span><span class="sxs-lookup"><span data-stu-id="2adfa-140">In the **Available characteristics** field, enter the certificate type to search for.</span></span>

## <a name="assign-a-project-resource-to-a-project"></a><span data-ttu-id="2adfa-141">Asignar un recurso de proyecto a un proyecto</span><span class="sxs-lookup"><span data-stu-id="2adfa-141">Assign a project resource to a project</span></span>

1. <span data-ttu-id="2adfa-142">En la página **Todos los proyectos**, seleccione el proyecto **Fase 2 de la actualización XYZ**.</span><span class="sxs-lookup"><span data-stu-id="2adfa-142">On the **All projects** page, select the **XYZ Upgrade Phase 2** project.</span></span>
2. <span data-ttu-id="2adfa-143">En la pestaña **Equipo del proyecto y programación**, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="2adfa-143">On the **Project team and scheduling** tab, select **Add**.</span></span>
3. <span data-ttu-id="2adfa-144">En el campo **Rol** seleccione **Miembro del equipo**.</span><span class="sxs-lookup"><span data-stu-id="2adfa-144">In the **Role** field, select **Team member**.</span></span>
4. <span data-ttu-id="2adfa-145">Seleccione **Reservar desde calendario**.</span><span class="sxs-lookup"><span data-stu-id="2adfa-145">Select **Book from calendar**.</span></span>
5. <span data-ttu-id="2adfa-146">En la página **Disponibilidad de recursos**, haga clic en **Ver configuración**.</span><span class="sxs-lookup"><span data-stu-id="2adfa-146">On the **Resource availability** page, select **View settings**.</span></span>
6. <span data-ttu-id="2adfa-147">En la página **Ajustar parámetros de visualización**, especifique los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="2adfa-147">On the **Adjust view settings** page, enter the following values:</span></span>

    - <span data-ttu-id="2adfa-148">**Formato de la vista de intervalo de fechas:** Día</span><span class="sxs-lookup"><span data-stu-id="2adfa-148">**Format for date range view:** Day</span></span>
    - <span data-ttu-id="2adfa-149">**Mostrar descripciones de disponibilidad:** Sí</span><span class="sxs-lookup"><span data-stu-id="2adfa-149">**Display availability descriptions:** Yes</span></span>
    - <span data-ttu-id="2adfa-150">**Mostrar capacidad restante:** Sí</span><span class="sxs-lookup"><span data-stu-id="2adfa-150">**Display remaining capacity:** Yes</span></span>

7. <span data-ttu-id="2adfa-151">En la lista de recursos, seleccione un recurso.</span><span class="sxs-lookup"><span data-stu-id="2adfa-151">In the list of resources, select a resource.</span></span>
8. <span data-ttu-id="2adfa-152">Seleccione **Reserva en firme** y **Capacidad total**.</span><span class="sxs-lookup"><span data-stu-id="2adfa-152">Select **Hard book** and **Full capacity**.</span></span>

## <a name="assign-a-resource-to-a-default-role"></a><span data-ttu-id="2adfa-153">Asignar un recurso a un rol predeterminado</span><span class="sxs-lookup"><span data-stu-id="2adfa-153">Assign a resource to a default role</span></span>

<span data-ttu-id="2adfa-154">Para ayudar a los directores de proyecto o de recursos, puede explorar en profundidad en los recursos que se pueden reservar para un proyecto.</span><span class="sxs-lookup"><span data-stu-id="2adfa-154">To help project or resource managers can drill down further on the resources that can be reserved for a project.</span></span> <span data-ttu-id="2adfa-155">Puede asociar un rol predeterminado a un recurso existente o un recurso recién adquirido.</span><span class="sxs-lookup"><span data-stu-id="2adfa-155">You can associate a default role with an existing resource or a newly acquired resource.</span></span> <span data-ttu-id="2adfa-156">Por ejemplo, cuando se contrató a Daniel, este tenía la experiencia y aptitudes para ejercer la función de la analista de negocios.</span><span class="sxs-lookup"><span data-stu-id="2adfa-156">For example, when Daniel was hired, he had the experience and skills to fill the Business analyst role.</span></span> <span data-ttu-id="2adfa-157">El administrador de recursos asignó este rol como rol predeterminado de Daniel.</span><span class="sxs-lookup"><span data-stu-id="2adfa-157">The resource manager assigned this role as Daniel's default role.</span></span> <span data-ttu-id="2adfa-158">Por lo tanto, la directora de recursos agregó a Daniel a un conjunto de analistas de negocios disponibles para trabajar en proyectos.</span><span class="sxs-lookup"><span data-stu-id="2adfa-158">Therefore, the resource manager added Daniel to a pool of business analysts who are available to work on projects.</span></span>

<span data-ttu-id="2adfa-159">Durante la reserva de recursos, los directores de proyecto pueden filtrar los recursos de rol que están disponibles para trabajar en proyectos.</span><span class="sxs-lookup"><span data-stu-id="2adfa-159">During resource reservation, project managers can filter the role resources that are available to work on projects.</span></span> <span data-ttu-id="2adfa-160">Pueden usar esta información como criterio cuando realicen análisis de decisiones de varios criterios durante el cumplimiento de recursos.</span><span class="sxs-lookup"><span data-stu-id="2adfa-160">They can use this information as one criterion when they perform multi-criteria decision analysis during resource fulfillment.</span></span> <span data-ttu-id="2adfa-161">También pueden agregar otras características de recursos al filtro para buscar recursos que tienen aptitudes, formación y experiencia específicas para un proyecto determinado.</span><span class="sxs-lookup"><span data-stu-id="2adfa-161">They can also add other resource characteristics to the filter to search for resources that have specific skills, education, and experience for a given project.</span></span>

<span data-ttu-id="2adfa-162">**Escenario:** Se ha iniciado un proyecto aprobado y el rol de director de proyecto principal se reservó como recurso planeado durante la fase de planificación de proyectos.</span><span class="sxs-lookup"><span data-stu-id="2adfa-162">**Scenario:** An approved project has started, and the Senior project manager role was reserved as a planned resource during the project planning stage.</span></span> <span data-ttu-id="2adfa-163">El responsable de recursos ha adquirido ahora a un recurso para cumplir el rol de director de proyecto principal.</span><span class="sxs-lookup"><span data-stu-id="2adfa-163">The resource manager has now acquired a resource to fulfill the Senior project manager role.</span></span>

1. <span data-ttu-id="2adfa-164">En la página **Lista de recursos**, seleccione **Daniel Goldschmidt**.</span><span class="sxs-lookup"><span data-stu-id="2adfa-164">On the **Resources list** page, select **Daniel Goldschmidt**.</span></span>
2. <span data-ttu-id="2adfa-165">En la página **Rol del recurso**, seleccione **Nuevo** y especifique los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="2adfa-165">On the **Resource role** page, select **New**, and enter the following values:</span></span>

    - <span data-ttu-id="2adfa-166">**Vigente:** escriba la fecha actual.</span><span class="sxs-lookup"><span data-stu-id="2adfa-166">**Effective:** Enter the current date.</span></span>
    - <span data-ttu-id="2adfa-167">**Vencimiento:** seleccione **Nunca**.</span><span class="sxs-lookup"><span data-stu-id="2adfa-167">**Expiration:** Enter **Never**.</span></span>
    - <span data-ttu-id="2adfa-168">**Rol:** escriba **Director de proyecto principal**.</span><span class="sxs-lookup"><span data-stu-id="2adfa-168">**Role:** Enter **Senior Project Manager**.</span></span>

3. <span data-ttu-id="2adfa-169">Haga clic en **Guardar** y, a continuación, cierre la página.</span><span class="sxs-lookup"><span data-stu-id="2adfa-169">Select **Save**, and then close the page.</span></span>
4. <span data-ttu-id="2adfa-170">En la pestaña **Competencias**, agregue la aptitud **ProjectMgmt** y el certificado **PMP**.</span><span class="sxs-lookup"><span data-stu-id="2adfa-170">On the **Competencies** tab, add the **ProjectMgmt** skill and the **PMP** certificate.</span></span>
