---
title: Utilizar flujos de trabajo para administrar la información sobre los empleados
description: Este artículo explica cómo puede utilizar la capacidad del flujo de trabajo para que Recursos Humanos administre la información sobre los empleados. Por ejemplo, puede asociar un flujo de trabajo a un puesto y configurar un flujo de trabajo de aprobación que se inicia cuando los empleados cambian su registro.
author: andreabichsel
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 269074
ms.assetid: 426c6127-42ee-4163-8dd0-b2867f95581d
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: c5bb0a363a3094626d81af3d5ffea38d9a1b12a8
ms.sourcegitcommit: f8bac7ca2803913fd236adbc3806259a17a110f4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "5129812"
---
# <a name="use-workflows-to-manage-employee-information"></a><span data-ttu-id="0bb1d-104">Utilizar flujos de trabajo para administrar la información sobre los empleados</span><span class="sxs-lookup"><span data-stu-id="0bb1d-104">Use workflows to manage employee information</span></span>

<span data-ttu-id="0bb1d-105">Este artículo explica cómo puede utilizar la capacidad del flujo de trabajo para que Recursos Humanos administre la información sobre los empleados.</span><span class="sxs-lookup"><span data-stu-id="0bb1d-105">This article explains how you can use the workflow capability for Human resources to manage employee information.</span></span> <span data-ttu-id="0bb1d-106">Por ejemplo, puede asociar un flujo de trabajo a un puesto y configurar un flujo de trabajo de aprobación que se inicia cuando los empleados cambian su registro.</span><span class="sxs-lookup"><span data-stu-id="0bb1d-106">For example, you can associate a workflow with a position and configure an approval workflow that is started when employees change their record.</span></span>

<span data-ttu-id="0bb1d-107">La capacidad del flujo de trabajo para Recursos Humanos proporciona numeroso flujos de trabajo para gestionar actividades de Recursos Humanos.</span><span class="sxs-lookup"><span data-stu-id="0bb1d-107">The workflow capability for Human resources provides numerous workflows for managing human resources activities.</span></span> <span data-ttu-id="0bb1d-108">Asimismo, hay numerosas opciones disponibles para que pueda modificar flujos de trabajo específicos y asociarlos a una jerarquía de informes.</span><span class="sxs-lookup"><span data-stu-id="0bb1d-108">Additionally, numerous options are available so that you can modify specific workflows and associate them with a reporting hierarchy.</span></span> <span data-ttu-id="0bb1d-109">Los flujos de trabajo están disponibles para ayudar a gestionar cambios a varios tipos estándar de información sobre los empleados.</span><span class="sxs-lookup"><span data-stu-id="0bb1d-109">Workflows are available to help manage changes to several standard types of employee information.</span></span> <span data-ttu-id="0bb1d-110">Puede asociar un flujo de trabajo a un puesto.</span><span class="sxs-lookup"><span data-stu-id="0bb1d-110">You can associate a workflow with a position.</span></span> <span data-ttu-id="0bb1d-111">A continuación, si los empleados cambian su registro de empleado, se inicia un flujo de trabajo que requiere aprobación antes de que se guarde la nueva información.</span><span class="sxs-lookup"><span data-stu-id="0bb1d-111">Then, if employees change their employee record, a workflow is started that requires approval before the new information is saved.</span></span> <span data-ttu-id="0bb1d-112">Los flujos de trabajo están predefinidos para los siguientes tipos de información para ayudarle a gestionar de manera eficiente los cambios y mantener preciosos los datos de sus empleados:</span><span class="sxs-lookup"><span data-stu-id="0bb1d-112">Workflows are predefined for the following types of information to help you efficiently manage changes and keep your employees’ data accurate:</span></span>

-   <span data-ttu-id="0bb1d-113">Números de identificación</span><span class="sxs-lookup"><span data-stu-id="0bb1d-113">Identification numbers</span></span>
-   <span data-ttu-id="0bb1d-114">Cursos</span><span class="sxs-lookup"><span data-stu-id="0bb1d-114">Courses</span></span>
-   <span data-ttu-id="0bb1d-115">Formación</span><span class="sxs-lookup"><span data-stu-id="0bb1d-115">Education</span></span>
-   <span data-ttu-id="0bb1d-116">Imagen</span><span class="sxs-lookup"><span data-stu-id="0bb1d-116">Image</span></span>
-   <span data-ttu-id="0bb1d-117">Artículos prestados</span><span class="sxs-lookup"><span data-stu-id="0bb1d-117">Loaned items</span></span>
-   <span data-ttu-id="0bb1d-118">Experiencia profesional</span><span class="sxs-lookup"><span data-stu-id="0bb1d-118">Professional experience</span></span>
-   <span data-ttu-id="0bb1d-119">Experiencia en proyectos</span><span class="sxs-lookup"><span data-stu-id="0bb1d-119">Project experience</span></span>
-   <span data-ttu-id="0bb1d-120">Aptitudes</span><span class="sxs-lookup"><span data-stu-id="0bb1d-120">Skills</span></span>
-   <span data-ttu-id="0bb1d-121">Puestos de confianza</span><span class="sxs-lookup"><span data-stu-id="0bb1d-121">Positions of trust</span></span>
-   <span data-ttu-id="0bb1d-122">Acciones de recursos humanos</span><span class="sxs-lookup"><span data-stu-id="0bb1d-122">Human resources actions</span></span>
-   <span data-ttu-id="0bb1d-123">Registro del curso</span><span class="sxs-lookup"><span data-stu-id="0bb1d-123">Course registration</span></span>

<span data-ttu-id="0bb1d-124">Cuando se contrata, transfiere o despide a empleados, el flujo de trabajo puede incluir un proceso de revisión.</span><span class="sxs-lookup"><span data-stu-id="0bb1d-124">When employees are hired, transferred, or terminated, the workflow can include a review process.</span></span> <span data-ttu-id="0bb1d-125">De esta manera, se puede revisar un documento o se puede definir una acción como parte del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="0bb1d-125">In this way, a document can be revised or the terms of an action can be defined as part of the workflow.</span></span> <span data-ttu-id="0bb1d-126">Cuando se completa el proceso de revisión, se completa el documento o la acción, y el flujo de trabajo se mueve a un paso de aprobación final.</span><span class="sxs-lookup"><span data-stu-id="0bb1d-126">When the review process is completed, the document or action is completed, and the workflow moves to a final approval step.</span></span>

## <a name="associate-a-workflow-with-a-position-hierarchy"></a><span data-ttu-id="0bb1d-127">Asociar un flujo de trabajo a una jerarquía de puestos</span><span class="sxs-lookup"><span data-stu-id="0bb1d-127">Associate a workflow with a position hierarchy</span></span>
<span data-ttu-id="0bb1d-128">Puede asociar un flujo de trabajo con cualquier jerarquía que configure.</span><span class="sxs-lookup"><span data-stu-id="0bb1d-128">You can associate a workflow with any hierarchy that you configure.</span></span> <span data-ttu-id="0bb1d-129">Por ejemplo, si un puesto está asociado a una jerarquía de informes de matriz, puede configurar un flujo de trabajo que distribuye los gastos para un proyecto específico al cliente potencial del proyecto en lugar de al director del empleado asociado a ese puesto.</span><span class="sxs-lookup"><span data-stu-id="0bb1d-129">For example, if a position is associated with a matrix reporting hierarchy, you might configure a workflow that routes expenses for a specific project to the project lead instead of the manager of the employee who is associated with that position.</span></span> <span data-ttu-id="0bb1d-130">Para crear un nuevo flujo de trabajo o modificar un flujo de trabajo existente, en la página **Flujo de trabajo de recursos humanos**, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="0bb1d-130">To create a new workflow or modify an existing workflow, on the **Human resources workflow** page, click **New**.</span></span> <span data-ttu-id="0bb1d-131">Seleccione un flujo de trabajo en la lista para iniciar al diseñador de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="0bb1d-131">Select a workflow in the list to start the Workflow designer.</span></span> <span data-ttu-id="0bb1d-132">Puede usar al diseñador para crear un nuevo flujo de trabajo o para cambiar los pasos de un flujo de trabajo existente.</span><span class="sxs-lookup"><span data-stu-id="0bb1d-132">You can use the designer to create a new workflow or change the steps in an existing workflow.</span></span> <span data-ttu-id="0bb1d-133">Al cambiar un flujo de trabajo existente, los cambios se guardan como una nueva versión.</span><span class="sxs-lookup"><span data-stu-id="0bb1d-133">When you change an existing workflow, your changes are saved as a new version.</span></span> <span data-ttu-id="0bb1d-134">Por lo tanto, siempre puede volver a una versión anterior si es necesario.</span><span class="sxs-lookup"><span data-stu-id="0bb1d-134">Therefore, you can always go back to a previous version if you have to.</span></span>

## <a name="configure-a-human-resources-workflow"></a><span data-ttu-id="0bb1d-135">Configurar un flujo de trabajo de las acciones de recursos humanos</span><span class="sxs-lookup"><span data-stu-id="0bb1d-135">Configure a Human resources workflow</span></span>
<span data-ttu-id="0bb1d-136">Siga estos pasos para configurar un flujo de trabajo básico que se inicia cuando la solicitud de los empleados cambia a su identificación personal.</span><span class="sxs-lookup"><span data-stu-id="0bb1d-136">To configure a basic workflow that is started when employees request changes to their personal identification, follow these steps.</span></span>

1.  <span data-ttu-id="0bb1d-137">En la página **Flujos de trabajo de recursos humanos**, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="0bb1d-137">On the **Human resources workflows** page, click **New**.</span></span>
2.  <span data-ttu-id="0bb1d-138">En la lista de flujos de trabajo disponibles, seleccione **Números de identificación**.</span><span class="sxs-lookup"><span data-stu-id="0bb1d-138">In the list of available workflows, select **Identification numbers**.</span></span>
3.  <span data-ttu-id="0bb1d-139">Haga clic en **Ejecutar** para iniciar al diseñador de flujo de trabajo y, a continuación, introduzca su nombre de usuario y contraseña cuando se le solicite.</span><span class="sxs-lookup"><span data-stu-id="0bb1d-139">Click **Run** to start the Workflow designer, and then enter your user name and password when you're prompted.</span></span>
4.  <span data-ttu-id="0bb1d-140">Arrastre el elemento **Aprobar número de identificación** de la lista de elementos de flujo de trabajo al lienzo de diseñador.</span><span class="sxs-lookup"><span data-stu-id="0bb1d-140">Drag the **Approve identification number** element from the list of workflow elements to the designer canvas.</span></span>
5.  <span data-ttu-id="0bb1d-141">Conecte el elemento de aprobación para **Empezar** y **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="0bb1d-141">Connect the approval element to **Start** and **Finish**.</span></span>
6.  <span data-ttu-id="0bb1d-142">Haga doble clic en **Aprobar elemento** y, a continuación, haga clic con el botón secundario y seleccione **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="0bb1d-142">Double-click **Approve element**, and then right-click, and select **Properties**.</span></span>
7.  <span data-ttu-id="0bb1d-143">Siga estos pasos para agregar las instrucciones del elemento de trabajo:</span><span class="sxs-lookup"><span data-stu-id="0bb1d-143">Follow these steps to add work item instructions:</span></span>
    1.  <span data-ttu-id="0bb1d-144">Seleccione **Asignación** y, a continuación, seleccione **Jerarquía** en el tipo de asignación.</span><span class="sxs-lookup"><span data-stu-id="0bb1d-144">Select **Assignment**, and then select **Hierarchy** under the assignment type.</span></span>
    2.  <span data-ttu-id="0bb1d-145">En la selección **Jerarquía**, seleccione **Jerarquía configurable**.</span><span class="sxs-lookup"><span data-stu-id="0bb1d-145">Under the **Hierarchy** selection, select **Configurable hierarchy**.</span></span>
    3.  <span data-ttu-id="0bb1d-146">Agregue una condición de detención y cierre la página.</span><span class="sxs-lookup"><span data-stu-id="0bb1d-146">Add a stop condition, and close the page.</span></span>

8.  <span data-ttu-id="0bb1d-147">Complete cualquier instrucción adicional (no debe haber advertencias adicionales).</span><span class="sxs-lookup"><span data-stu-id="0bb1d-147">Complete any additional instructions (no additional warnings should exist).</span></span>
9.  <span data-ttu-id="0bb1d-148">Haga clic en **Guardar y cerrar**.</span><span class="sxs-lookup"><span data-stu-id="0bb1d-148">Click **Save and close**.</span></span> <span data-ttu-id="0bb1d-149">Active el nuevo flujo de trabajo cuando se abra el cuadro de diálogo, y seleccione **Activar**.</span><span class="sxs-lookup"><span data-stu-id="0bb1d-149">Activate the new workflow when the dialog box opens, and select **Make active**.</span></span>
10. <span data-ttu-id="0bb1d-150">Vaya a **Recursos Humanos** &gt; **Puestos** &gt; **Tipos de jerarquías de puestos**</span><span class="sxs-lookup"><span data-stu-id="0bb1d-150">Go to **Human Resources** &gt; **Positions** &gt; **Position hierarchy types**.</span></span>
11. <span data-ttu-id="0bb1d-151">Seleccione **Matriz**.</span><span class="sxs-lookup"><span data-stu-id="0bb1d-151">Select **Matrix**.</span></span>
12. <span data-ttu-id="0bb1d-152">Agregue el flujo de trabajo **Número de identificación de trabajador** a la lista.</span><span class="sxs-lookup"><span data-stu-id="0bb1d-152">Add the **Worker identification number** workflow to the list.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0bb1d-153">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="0bb1d-153">Additional resources</span></span>

[<span data-ttu-id="0bb1d-154">Ver y administrar cambios de dirección</span><span class="sxs-lookup"><span data-stu-id="0bb1d-154">View and manage address changes</span></span>](hr-personnel-view-address-changes.md) 



