---
title: Integración con el cliente de Microsoft Project
description: Planificar y mantener la programación de un proyecto puede ser complejo, por lo que los gestores de proyectos deben utilizar herramientas que los ayuden a gestionar esta tarea. La integración con el cliente de Microsoft Project proporciona soporte para abrir y gestionar una estructura de descomposición del trabajo del proyecto.
author: KimANelson
manager: AnnBe
ms.date: 12/11/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjWbsTemplate
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2017-12-04
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: 610990612d5fb38025bf39cc648d0c9572da37b6
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "2175017"
---
# <a name="microsoft-project-client-integration"></a><span data-ttu-id="c1f99-104">Integración con el cliente de Microsoft Project</span><span class="sxs-lookup"><span data-stu-id="c1f99-104">Microsoft Project client integration</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c1f99-105">Planificar y mantener la programación de un proyecto puede ser complejo, por lo que los gestores de proyectos deben utilizar herramientas que los ayuden a gestionar esta tarea.</span><span class="sxs-lookup"><span data-stu-id="c1f99-105">Planning and maintaining a project schedule can be complex, so project managers need to use tools that help them manage this task.</span></span> <span data-ttu-id="c1f99-106">La integración con el cliente de Microsoft Project proporciona soporte para abrir y gestionar una estructura de descomposición del trabajo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="c1f99-106">Integration with Microsoft Project Client provides support to open and manage a project work breakdown structure.</span></span> <span data-ttu-id="c1f99-107">El gestor de proyectos puede volver publicar cualquier cambio en la estructura de descomposición del trabajo del proyecto de Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="c1f99-107">The project manager can publish any changes back to the Dynamics 365 Finance project work breakdown structure.</span></span>

> [!NOTE]
> <span data-ttu-id="c1f99-108">Si utiliza la actualización de julio (versión 10.0.4), debe instalar KB 4054797 y 4055884.</span><span class="sxs-lookup"><span data-stu-id="c1f99-108">If you are using the July update (version 10.0.4), you must install KB 4054797 and 4055884.</span></span>

## <a name="configure-the-microsoft-project-client-add-in"></a><span data-ttu-id="c1f99-109">Configurar el complemento del cliente de Microsoft Project</span><span class="sxs-lookup"><span data-stu-id="c1f99-109">Configure the Microsoft Project Client add-in</span></span>
<span data-ttu-id="c1f99-110">Para habilitar la integración con el cliente de Microsoft Project, se requiere la instalación de un complemento de Microsoft Dynamics 365 en la aplicación del cliente de Microsoft Project del usuario.</span><span class="sxs-lookup"><span data-stu-id="c1f99-110">To enable the integration with Microsoft Project Client, a Microsoft Dynamics 365 add-in is required to be installed in the user’s client Microsoft Project application.</span></span> <span data-ttu-id="c1f99-111">Para ello, abra el **Espacio de trabajo de gestión de proyectos**.</span><span class="sxs-lookup"><span data-stu-id="c1f99-111">This is done by opening the **Project management workspace**.</span></span>

<span data-ttu-id="c1f99-112">•   Haga click en **Configurar el complemento de cliente del proyecto** de la sección **Vínculos** > **Configuración** del espacio de trabajo.</span><span class="sxs-lookup"><span data-stu-id="c1f99-112">•   Click **Configure project client add-in** from the **Links** > **Setup** section of the workspace.</span></span>

<span data-ttu-id="c1f99-113">•   Haga clic en **Abrir** y, a continuación, haga clic en **Ejecutar** cuando se le solicite.</span><span class="sxs-lookup"><span data-stu-id="c1f99-113">•   Click **Open**, then click **Run** when prompted.</span></span>

## <a name="open-and-edit-an-existing-draft-work-breakdown-structure-in-microsoft-project-client"></a><span data-ttu-id="c1f99-114">Abra y edite una estructura de descomposición del trabajo existente de borrador en el cliente de Microsoft Project</span><span class="sxs-lookup"><span data-stu-id="c1f99-114">Open and edit an existing draft work breakdown structure in Microsoft Project Client</span></span>
<span data-ttu-id="c1f99-115">Si un proyecto en Dynamics 365 Finance ya tiene creada una estructura de descomposición del trabajo, la estructura de descomposición del trabajo se puede abrir en la aplicación de Microsoft Project Client si la estructura de descomposición del trabajo está en estado de borrador.</span><span class="sxs-lookup"><span data-stu-id="c1f99-115">If a project in Dynamics 365 Finance already has a work breakdown structure created, the work breakdown structure can be opened in the Microsoft Project Client application if the work breakdown structure is in a draft status.</span></span> <span data-ttu-id="c1f99-116">Para abrirla desde la página **Proyecto**, haga clic en el vínculo **Abrir en Microsoft Project** de la pestaña **Plan**. Esta página también se puede abrir desde dentro de la aplicación del cliente de Microsoft Project haciendo clic en **Abrir** en la pestaña **Microsoft Dynamics 365**. Seleccione **Entidad jurídica** y **Proyecto** de la lista.</span><span class="sxs-lookup"><span data-stu-id="c1f99-116">To open from the **Project** page, click **Open in Microsoft Project** link from the **Plan** tab. This page can also be opened from within the Microsoft Project Client application by clicking **Open** in the **Microsoft Dynamics 365** tab. Select the **Legal entity** and **Project** from the list.</span></span>

> [!NOTE]
> <span data-ttu-id="c1f99-117">Si utiliza Internet Explorer como su explorador, deberá hacer clic en **Guardar** para abrir manualmente la ubicación en la que se ha descargado ese archivo.</span><span class="sxs-lookup"><span data-stu-id="c1f99-117">If you're using Internet Explorer as your browser, you will need to click **Save** to manually open from the location that the file is downloaded to.</span></span> <span data-ttu-id="c1f99-118">O bien, haga clic en **Guardar y abrir** para abrir el archivo en el cliente de Microsoft Project.</span><span class="sxs-lookup"><span data-stu-id="c1f99-118">Or, click **Save and open** to open the file in Microsoft Project Client.</span></span> <span data-ttu-id="c1f99-119">No cambiar el nombre de archivo al guardar.</span><span class="sxs-lookup"><span data-stu-id="c1f99-119">Do not rename the file name when saving.</span></span>

<span data-ttu-id="c1f99-120">Antes de realizar cualquier edición en el archivo mediante Microsoft Project Client, necesita comprobarlo. Haga clic en **Desproteger** en la pestaña **Microsoft Dynamics 365**. Esto impedirá que otros usuarios editen la estructura de descomposición del trabajo dentro de Finance al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="c1f99-120">Before making any edits to the file using Microsoft Project Client, you need to check it out. Click **Check out** in the **Microsoft Dynamics 365** tab. This will prevent other users from editing the work breakdown structure from within Finance at the same time.</span></span> <span data-ttu-id="c1f99-121">Para publicar la estructura de descomposición del trabajo después de completar las ediciones, haga clic en **Desproteger** en la pestaña **Microsoft Dynamics 365**.</span><span class="sxs-lookup"><span data-stu-id="c1f99-121">To publish the work breakdown structure after completing any edits, click **Check in** on the **Microsoft Dynamics 365** tab.</span></span>

<span data-ttu-id="c1f99-122">Si ya ha agregado un equipo de proyecto al proyecto en Finance, la lista de recursos se rellenará con los miembros del equipo.</span><span class="sxs-lookup"><span data-stu-id="c1f99-122">If a project team has already been added to the project in Finance, the resource list will be populated with the team members.</span></span> <span data-ttu-id="c1f99-123">Si todavía no ha agregado un equipo de proyecto al proyecto, puede seleccionar recursos y crear al equipo desde el cliente de Microsoft Project haciendo clic en el botón **Recursos** en la pestaña **Microsoft Dynamics 365**.</span><span class="sxs-lookup"><span data-stu-id="c1f99-123">If a project team has not yet been added to the project, you can select resources and build the team within Microsoft Project Client by clicking the **Resources** button on the **Microsoft Dynamics 365** tab.</span></span> 

<span data-ttu-id="c1f99-124">Los siguientes datos se volverán a sincronizar en Finance como parte del proceso de registro de entrada:</span><span class="sxs-lookup"><span data-stu-id="c1f99-124">The following data will be synced back to Finance as part of the check-in process:</span></span>

<span data-ttu-id="c1f99-125">•   Nombre de la tarea</span><span class="sxs-lookup"><span data-stu-id="c1f99-125">•   Task name</span></span>

<span data-ttu-id="c1f99-126">•   Fecha de inicio</span><span class="sxs-lookup"><span data-stu-id="c1f99-126">•   Start date</span></span>

<span data-ttu-id="c1f99-127">•   Fecha final</span><span class="sxs-lookup"><span data-stu-id="c1f99-127">•   Finish date</span></span>

<span data-ttu-id="c1f99-128">•   Predecesores</span><span class="sxs-lookup"><span data-stu-id="c1f99-128">•   Predecessors</span></span>

<span data-ttu-id="c1f99-129">•   Nombres de recurso</span><span class="sxs-lookup"><span data-stu-id="c1f99-129">•   Resource names</span></span>

<span data-ttu-id="c1f99-130">•   Categoría</span><span class="sxs-lookup"><span data-stu-id="c1f99-130">•   Category</span></span>

<span data-ttu-id="c1f99-131">•   Categoría de recurso</span><span class="sxs-lookup"><span data-stu-id="c1f99-131">•   Resource category</span></span>

<span data-ttu-id="c1f99-132">•   Horas laborables</span><span class="sxs-lookup"><span data-stu-id="c1f99-132">•   Work hours</span></span>

<span data-ttu-id="c1f99-133">•   Notas</span><span class="sxs-lookup"><span data-stu-id="c1f99-133">•   Notes</span></span>

<span data-ttu-id="c1f99-134">•   Prioridad</span><span class="sxs-lookup"><span data-stu-id="c1f99-134">•   Priority</span></span>

> [!NOTE]
> <span data-ttu-id="c1f99-135">Si agrega cualquier otra columna a su archivo del cliente de Microsoft Project, no se guardará en el archivo y no se mostrará cuando se vuelva a abrir el archivo.</span><span class="sxs-lookup"><span data-stu-id="c1f99-135">If you add any other columns to your Microsoft Project Client file, they will not be saved to the file and will not be displayed when the file is opened again.</span></span>

## <a name="create-the-work-breakdown-structure-for-an-existing-project-using-microsoft-project-client"></a><span data-ttu-id="c1f99-136">Crear la estructura de descomposición del trabajo para un proyecto existente mediante el cliente de Microsoft Project</span><span class="sxs-lookup"><span data-stu-id="c1f99-136">Create the work breakdown structure for an existing project using Microsoft Project Client</span></span>
<span data-ttu-id="c1f99-137">Para crear una nueva estructura de descomposición del trabajo mediante el cliente de Microsoft Project, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="c1f99-137">To create a new work breakdown structure using Microsoft Project Client, follow these steps:</span></span>


1.  <span data-ttu-id="c1f99-138">Abra el cliente de Microsoft Project.</span><span class="sxs-lookup"><span data-stu-id="c1f99-138">Open Microsoft Project Client.</span></span>

2.  <span data-ttu-id="c1f99-139">En la ficha **Microsoft Dynamics 365**, haga clic en **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="c1f99-139">On the **Microsoft Dynamics 365** tab, click **Open**.</span></span>

3.  <span data-ttu-id="c1f99-140">Seleccionar la **Entidad jurídica** para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="c1f99-140">Select the **Legal entity** for the project.</span></span>

4.  <span data-ttu-id="c1f99-141">Seleccione el **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="c1f99-141">Select the **Project**.</span></span>

5.  <span data-ttu-id="c1f99-142">Haga clic en **Desproteger** en la pestaña **Microsoft Dynamics 365**.</span><span class="sxs-lookup"><span data-stu-id="c1f99-142">Click **Check out** on the **Microsoft Dynamics 365** tab.</span></span>

6.  <span data-ttu-id="c1f99-143">Cuando esté listo para publicar en Finance, haga clic en **Registrar** en la pestaña **Microsoft Dynamics 365**.</span><span class="sxs-lookup"><span data-stu-id="c1f99-143">When ready to publish to Finance, click **Check in** on the **Microsoft Dynamics 365** tab.</span></span>

## <a name="replace-the-existing-work-breakdown-structure-for-an-existing-project-using-microsoft-project-client"></a><span data-ttu-id="c1f99-144">Sustituir la estructura de descomposición del trabajo existente para un proyecto existente mediante el cliente de Microsoft Project</span><span class="sxs-lookup"><span data-stu-id="c1f99-144">Replace the existing work breakdown structure for an existing project using Microsoft Project Client</span></span>
<span data-ttu-id="c1f99-145">Para crear una estructura de descomposición del trabajo mediante el cliente de Microsoft Project y reemplazar una estructura de descomposición del trabajo existente por un proyecto existente, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="c1f99-145">To create a new work breakdown structure using Microsoft Project Client and replace an existing work breakdown structure for an existing project, follow these steps:</span></span>

1.  <span data-ttu-id="c1f99-146">Abra el cliente de Microsoft Project.</span><span class="sxs-lookup"><span data-stu-id="c1f99-146">Open the Microsoft Project Client.</span></span>

2.  <span data-ttu-id="c1f99-147">Cree la programación en el cliente de Microsoft Project.</span><span class="sxs-lookup"><span data-stu-id="c1f99-147">Create the schedule in Microsoft Project Client.</span></span>

3.  <span data-ttu-id="c1f99-148">En la pestaña **Microsoft Dynamics 365**, haga clic en **Guardar cambios** > **Reemplazar proyecto existente**.</span><span class="sxs-lookup"><span data-stu-id="c1f99-148">On the **Microsoft Dynamics 365** tab, click **Save changes** > **Replace existing project**.</span></span>

4.  <span data-ttu-id="c1f99-149">Seleccionar la **Entidad jurídica** para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="c1f99-149">Select the **Legal entity** for the project.</span></span>

5.  <span data-ttu-id="c1f99-150">Seleccione el **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="c1f99-150">Select the **Project**.</span></span>

6.  <span data-ttu-id="c1f99-151">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c1f99-151">Click **OK**.</span></span>

## <a name="create-a-new-project-from-within-microsoft-project-client"></a><span data-ttu-id="c1f99-152">Cree un nuevo proyecto desde dentro del cliente de Microsoft Project</span><span class="sxs-lookup"><span data-stu-id="c1f99-152">Create a new project from within Microsoft Project Client</span></span>


1.  <span data-ttu-id="c1f99-153">Abra el cliente de Microsoft Project.</span><span class="sxs-lookup"><span data-stu-id="c1f99-153">Open the Microsoft Project Client.</span></span>

2.  <span data-ttu-id="c1f99-154">Cree la programación en el cliente de Microsoft Project.</span><span class="sxs-lookup"><span data-stu-id="c1f99-154">Create the schedule in Microsoft Project Client.</span></span>

3.  <span data-ttu-id="c1f99-155">En la pestaña **Microsoft Dynamics 365**, haga clic en **Guardar cambios** > **Guardar en nuevo proyecto**.</span><span class="sxs-lookup"><span data-stu-id="c1f99-155">On the **Microsoft Dynamics 365** tab, click **Save changes** > **Save to new Project**.</span></span>

4.  <span data-ttu-id="c1f99-156">Seleccionar la **Entidad jurídica** para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="c1f99-156">Select the **Legal entity** for the project.</span></span>

5.  <span data-ttu-id="c1f99-157">Especifique el **Id. de proyecto** si es necesario.</span><span class="sxs-lookup"><span data-stu-id="c1f99-157">Enter the **Project ID**, if necessary.</span></span>

6.  <span data-ttu-id="c1f99-158">Especifique el **Nombre del proyecto**.</span><span class="sxs-lookup"><span data-stu-id="c1f99-158">Enter the **Project name**.</span></span>

7.  <span data-ttu-id="c1f99-159">Seleccione el **Tipo de proyecto**, el **Grupo de proyectos** y el **Id. de contrato de proyecto**.</span><span class="sxs-lookup"><span data-stu-id="c1f99-159">Select the **Project type**, **Project group** and the **Project contract ID**.</span></span> <span data-ttu-id="c1f99-160">De forma alternativa, puede crear un nuevo contrato de proyecto haciendo clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="c1f99-160">Alternatively, you can create a new project contract by clicking **New**.</span></span>

8.  <span data-ttu-id="c1f99-161">Seleccione el **Calendario** que se utilizará para los recursos.</span><span class="sxs-lookup"><span data-stu-id="c1f99-161">Select the **Calendar** to be used for resourcing.</span></span>

11. <span data-ttu-id="c1f99-162">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c1f99-162">Click **OK**.</span></span>