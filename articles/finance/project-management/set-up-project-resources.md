---
title: Configurar recursos del proyecto
description: Este tema proporciona información sobre cómo configurar o solicitar recursos del proyecto.
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
ms.openlocfilehash: c882e23794e3937f85b3e73774b36deaf28ac3ed
ms.sourcegitcommit: 241ada0945c72d769eaa70ae35aedbb6a3233fdf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "3760658"
---
# <a name="set-up-project-resources"></a><span data-ttu-id="808f0-103">Configurar recursos del proyecto</span><span class="sxs-lookup"><span data-stu-id="808f0-103">Set up project resources</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="808f0-104">Debe configurar un calendario y asociarlo a un empleado o un trabajador.</span><span class="sxs-lookup"><span data-stu-id="808f0-104">You must set up a calendar and associate it with an employee or a worker.</span></span> <span data-ttu-id="808f0-105">El calendario se usa para programar el proyecto y el horario de trabajo de los recursos reservados para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="808f0-105">The calendar is used to schedule the project and the working time of the resources that are reserved for the project.</span></span> <span data-ttu-id="808f0-106">Durante la configuración del calendario, los directores de proyecto pueden realizar la nivelación de recursos como parte de la optimización de recursos.</span><span class="sxs-lookup"><span data-stu-id="808f0-106">During calendar setup, project managers can do resource leveling as part of resource optimization.</span></span> <span data-ttu-id="808f0-107">En función de la programación del calendario, se pueden aplicar restricciones en los recursos.</span><span class="sxs-lookup"><span data-stu-id="808f0-107">Based on the calendar schedule, restrictions can be put on resources.</span></span> <span data-ttu-id="808f0-108">Puede configurar un calendario en la página **Calendarios**.</span><span class="sxs-lookup"><span data-stu-id="808f0-108">You can set up a calendar on the **Calendars** page.</span></span>

<span data-ttu-id="808f0-109">Al configurar un trabajador como recurso de proyecto, puede seleccionar aquellos trabajadores que estén trabajando en la compañía para la que esté configurando recursos.</span><span class="sxs-lookup"><span data-stu-id="808f0-109">When you set up a worker as a project resource, you can select from workers who work in the company that you're setting up resources for.</span></span> <span data-ttu-id="808f0-110">Asimismo, puede seleccionar los trabajadores de otras empresas que formen parte de su organización.</span><span class="sxs-lookup"><span data-stu-id="808f0-110">Alternatively, you can select workers from other companies in your organization.</span></span> <span data-ttu-id="808f0-111">Estos trabajadores se conocen como recursos de empresas vinculadas.</span><span class="sxs-lookup"><span data-stu-id="808f0-111">These workers are known as intercompany resources.</span></span>

<span data-ttu-id="808f0-112">Los procedimientos siguientes explican cómo configurar un trabajador como recurso del proyecto en la empresa y cómo configurar un recurso de proyecto de empresas vinculadas.</span><span class="sxs-lookup"><span data-stu-id="808f0-112">The following procedures explain how to set up a worker as a project resource in your company and how to set up an intercompany project resource.</span></span>

## <a name="set-up-a-worker-as-a-project-resource"></a><span data-ttu-id="808f0-113">Configurar un trabajador como recurso de proyecto</span><span class="sxs-lookup"><span data-stu-id="808f0-113">Set up a worker as a project resource</span></span>

1. <span data-ttu-id="808f0-114">En la página **Trabajadores**, en la lista **Trabajadores**, seleccione el trabajador que va a agregar como recurso del proyecto y abra el registro de trabajador.</span><span class="sxs-lookup"><span data-stu-id="808f0-114">On the **Workers** page, in the **Workers** list, select the worker that you're adding as a project resource, and open the worker record.</span></span>
2. <span data-ttu-id="808f0-115">En el Panel de acciones, seleccione **Proyecto** &gt; **Configuración** &gt; **Configuración del proyecto**.</span><span class="sxs-lookup"><span data-stu-id="808f0-115">On the Action Pane, select **Project** &gt; **Setup** &gt; **Project setup**.</span></span>
3. <span data-ttu-id="808f0-116">Seleccione un calendario y luego cierre la página.</span><span class="sxs-lookup"><span data-stu-id="808f0-116">Select a calendar, and then close the page.</span></span>

<span data-ttu-id="808f0-117">También puede especificar los proyectos predeterminados para un recurso como un tipo de asignación previa.</span><span class="sxs-lookup"><span data-stu-id="808f0-117">You can also specify default projects for a resource as a type of pre-assignment.</span></span> <span data-ttu-id="808f0-118">Las asignaciones previas se pueden utilizar cuando el director de recursos o el director de proyecto sabe en qué proyectos trabajará el recurso por adelantado.</span><span class="sxs-lookup"><span data-stu-id="808f0-118">Pre-assignments can be used when the resource manager or project manager knows which projects the resource will be working on in advance.</span></span> <span data-ttu-id="808f0-119">Las asignaciones previas también se pueden basar en la solicitud de un cliente o patrocinador de proyecto.</span><span class="sxs-lookup"><span data-stu-id="808f0-119">Pre-assignments can also be based on the request of a project sponsor or customer.</span></span> <span data-ttu-id="808f0-120">Para asignar previamente un proyecto, en la página **Asignar proyectos**, en la ficha **Proyectos**, en la lista **Proyectos restantes**, seleccione el proyecto adecuado.</span><span class="sxs-lookup"><span data-stu-id="808f0-120">To pre-assign a project, on the **Assign projects** page, on the **Projects** tab, in the **Remaining projects** list, select the appropriate project.</span></span>

## <a name="set-up-an-intercompany-resource"></a><span data-ttu-id="808f0-121">Configurar un recurso de empresas vinculadas</span><span class="sxs-lookup"><span data-stu-id="808f0-121">Set up an intercompany resource</span></span>

<span data-ttu-id="808f0-122">Al configurar un trabajador como recurso de empresas vinculadas, debe completar la configuración de la empresa de préstamo y la empresa que recibe el préstamo.</span><span class="sxs-lookup"><span data-stu-id="808f0-122">When you set up a worker as an intercompany resource, you must complete the setup in both the lending company and the borrowing company.</span></span>

### <a name="in-the-lending-company"></a><span data-ttu-id="808f0-123">En la empresa de préstamo</span><span class="sxs-lookup"><span data-stu-id="808f0-123">In the lending company</span></span>

1. <span data-ttu-id="808f0-124">En Finance, compruebe que la empresa de préstamo esté seleccionada y, a continuación realice el procedimiento que se detalló en la sección anterior, “Configurar un trabajador como recurso de proyecto”.</span><span class="sxs-lookup"><span data-stu-id="808f0-124">In Finance, verify that the lending company is selected, and then complete the procedure in the previous section, "Set up a worker as a project resource."</span></span>
2. <span data-ttu-id="808f0-125">En la página **Contabilidad de empresas vinculadas**, seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="808f0-125">On the **Intercompany accounting** page, select **New**.</span></span>
3. <span data-ttu-id="808f0-126">En el campo **Id. de entidad jurídica**, seleccione la empresa de préstamo.</span><span class="sxs-lookup"><span data-stu-id="808f0-126">In the **Legal entity ID** field, select the lending company.</span></span> <span data-ttu-id="808f0-127">Rellene los campos restantes según sea necesario y, a continuación seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="808f0-127">Fill in the remaining fields as appropriate, and then select **Save**.</span></span>
4. <span data-ttu-id="808f0-128">En la página **Precio de transferencia**, seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="808f0-128">On the **Transfer price** page, select **New**.</span></span>
5. <span data-ttu-id="808f0-129">En el campo **Entidad jurídica a la que se presta el trabajador**, seleccione la empresa adecuada.</span><span class="sxs-lookup"><span data-stu-id="808f0-129">In the **Borrowing legal entity** field, select the appropriate company.</span></span>
6. <span data-ttu-id="808f0-130">Si solo desea prestar a la empresa de solicitud del préstamo el recurso que ha creado al principio de esta sección, en el campo **Recurso**, seleccione el nombre de recurso que haya creado.</span><span class="sxs-lookup"><span data-stu-id="808f0-130">To lend the borrowing company only the resource that you created at the beginning of this section, in the **Resource** field, select the name of the resource that you created.</span></span> <span data-ttu-id="808f0-131">Si desea que todos los recursos de la empresa estén a disposición de la empresa que solicita el préstamo, deje el campo **Recurso** en blanco.</span><span class="sxs-lookup"><span data-stu-id="808f0-131">To make all resources in the lending company available to the borrowing company, leave the **Resource** field blank.</span></span>
7. <span data-ttu-id="808f0-132">Vaya a la página **Parámetros de administración de proyectos y contabilidad** en la pestaña **Empresas vinculadas** y establezca la opción **Activar la programación de recursos y las hojas de horas de empresas vinculadas** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="808f0-132">On the **Project management and accounting parameters** page, on the **Intercompany** tab, set the **Enable intercompany resource scheduling and timesheets** option to **Yes**.</span></span>

### <a name="in-the-borrowing-company"></a><span data-ttu-id="808f0-133">En la empresa que solicita el préstamo</span><span class="sxs-lookup"><span data-stu-id="808f0-133">In the borrowing company</span></span>

- <span data-ttu-id="808f0-134">En la página **Lista de recursos**, en el filtro de la búsqueda, escriba el nombre de recurso que creó para la empresa de préstamo y compruebe que el nombre está incluido en la lista de recursos de la empresa que solicita el préstamo.</span><span class="sxs-lookup"><span data-stu-id="808f0-134">On the **Resources list** page, in the search filter, enter the name of the resource that you created for the lending company, to verify that the name is included in the resource list for the borrowing company.</span></span>

## <a name="request-project-resources"></a><span data-ttu-id="808f0-135">Solicitar recursos de proyecto</span><span class="sxs-lookup"><span data-stu-id="808f0-135">Request project resources</span></span>
<span data-ttu-id="808f0-136">La funcionalidad de programación de recursos del proyecto solo admite a administradores de recursos para distribuir recursos de personal en compromisos o proyectos.</span><span class="sxs-lookup"><span data-stu-id="808f0-136">The functionality for project resource scheduling only lets resource managers distribute staffed resources on engagements or projects.</span></span> <span data-ttu-id="808f0-137">Para habilitar esta funcionalidad, realice las tareas siguientes o compruebe que se hayan realizado:</span><span class="sxs-lookup"><span data-stu-id="808f0-137">To enable this functionality, complete the following tasks, or verify that they have been completed:</span></span>

- <span data-ttu-id="808f0-138">Configurar secuencias numéricas.</span><span class="sxs-lookup"><span data-stu-id="808f0-138">Set up number sequences.</span></span>
- <span data-ttu-id="808f0-139">Configuración de flujos de trabajo de Gestión de proyectos y contabilidad.</span><span class="sxs-lookup"><span data-stu-id="808f0-139">Set up project management and accounting workflows.</span></span>
- <span data-ttu-id="808f0-140">Habilitar los flujos de trabajo de las solicitudes de recursos</span><span class="sxs-lookup"><span data-stu-id="808f0-140">Enable resource request workflows.</span></span>

<span data-ttu-id="808f0-141">Una vez que haya completado las tareas anteriores, puede completar las tareas siguientes según sea necesario:</span><span class="sxs-lookup"><span data-stu-id="808f0-141">After the preceding tasks have been completed, you can complete the following tasks as you require:</span></span>

- <span data-ttu-id="808f0-142">Cree una solicitud de recurso de un recurso con personal de reserva provisional.</span><span class="sxs-lookup"><span data-stu-id="808f0-142">Create a resource request from a soft-booked staffed resource.</span></span>
- <span data-ttu-id="808f0-143">Supervise las solicitudes de recursos.</span><span class="sxs-lookup"><span data-stu-id="808f0-143">Monitor resource requests.</span></span>
- <span data-ttu-id="808f0-144">Rellene las solicitudes de recursos.</span><span class="sxs-lookup"><span data-stu-id="808f0-144">Fulfill resource requests.</span></span>
- <span data-ttu-id="808f0-145">Solicite un recurso de personal de WBS.</span><span class="sxs-lookup"><span data-stu-id="808f0-145">Request a staffed resource from a WBS.</span></span>
- <span data-ttu-id="808f0-146">Reserve recursos para un proyecto sin tener un pedido de recurso de personal.</span><span class="sxs-lookup"><span data-stu-id="808f0-146">Book resources to a project without having a request for a staffed resource.</span></span>
