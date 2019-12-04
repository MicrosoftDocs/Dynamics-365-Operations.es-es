---
title: Visión general de la creación de flujos de trabajo
description: Este tema explica cómo crear un flujo de trabajo.
author: sericks007
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WorkflowSelectTemplateRnr, WorkflowTableListPageRnr
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 195583
ms.assetid: 836ddd01-cc34-45c3-a4b0-20647357dbc6
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 2
ms.openlocfilehash: a643be553f3fcdfbe53f2024982a596e498830a8
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2019
ms.locfileid: "2811316"
---
# <a name="create-workflows-overview"></a><span data-ttu-id="434bc-103">Visión general de la creación de flujos de trabajo</span><span class="sxs-lookup"><span data-stu-id="434bc-103">Create workflows overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="434bc-104">Este tema explica cómo crear un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="434bc-104">This topic explains how to create a workflow.</span></span>

## <a name="open-the-workflow-editor"></a><span data-ttu-id="434bc-105">Apertura del editor de flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="434bc-105">Open the workflow editor</span></span>

<span data-ttu-id="434bc-106">Los tipos de flujos de trabajo que puede crear varían según el módulo que está usando.</span><span class="sxs-lookup"><span data-stu-id="434bc-106">The module that you're working in determines the types of workflow that you can create.</span></span> <span data-ttu-id="434bc-107">Siga estos pasos para seleccionar el tipo de flujo de trabajo que va a crear y abrir el editor de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="434bc-107">Follow these steps to select the type of workflow to create and open the workflow editor.</span></span>

1. <span data-ttu-id="434bc-108">Abra el módulo para el que desea crear un nuevo flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="434bc-108">Open the module that you want to create a new workflow for.</span></span> <span data-ttu-id="434bc-109">Por ejemplo, para crear un flujo de trabajo para las solicitudes de compra, haga clic en **Adquisición y suministro de componentes**.</span><span class="sxs-lookup"><span data-stu-id="434bc-109">For example, to create a workflow for purchase requisitions, click **Procurement and sourcing**.</span></span>
2. <span data-ttu-id="434bc-110">Haga clic en **Configuración** &gt; **Flujos de trabajo de \[nombre del módulo\]**.</span><span class="sxs-lookup"><span data-stu-id="434bc-110">Click **Setup** &gt; **\[Module name\] workflows**.</span></span>
3. <span data-ttu-id="434bc-111">En la página de lista que aparece, en el Panel de acciones, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="434bc-111">On the list page that appears, on the Action Pane, click **New**.</span></span>
4. <span data-ttu-id="434bc-112">En la página **Crear flujo de trabajo**, seleccione el tipo de flujo de trabajo para crear y haga clic en **Crear flujo de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="434bc-112">On the **Create workflow** page, select the type of workflow to create, and then click **Create workflow**.</span></span> <span data-ttu-id="434bc-113">Aparecerá el editor de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="434bc-113">The workflow editor appears.</span></span> <span data-ttu-id="434bc-114">Ahora puede usar los siguientes procedimientos para diseñar el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="434bc-114">You can now use the following procedures to design the workflow.</span></span>

## <a name="drag-workflow-elements-onto-the-canvas"></a><span data-ttu-id="434bc-115">Arrastre de elementos de flujo de trabajo al lienzo</span><span class="sxs-lookup"><span data-stu-id="434bc-115">Drag workflow elements onto the canvas</span></span>

<span data-ttu-id="434bc-116">El área de **Elementos de flujo de trabajo** del editor de flujo de trabajo contiene los elementos que se pueden agregar al flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="434bc-116">The **Workflow elements** area of the workflow editor contains the elements that you can add to your workflow.</span></span> <span data-ttu-id="434bc-117">Para agregar elementos al flujo de trabajo, arrástrelos al lienzo.</span><span class="sxs-lookup"><span data-stu-id="434bc-117">To add elements to the workflow, drag them onto the canvas.</span></span>

## <a name="connect-the-elements"></a><span data-ttu-id="434bc-118">Conexión de los elementos</span><span class="sxs-lookup"><span data-stu-id="434bc-118">Connect the elements</span></span>

<span data-ttu-id="434bc-119">Para conectar un elemento de flujo de trabajo con otro, mantenga el puntero sobre uno de los elementos hasta que aparezcan puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="434bc-119">To connect one workflow element to another, hold the pointer over an element until connection points appear.</span></span> <span data-ttu-id="434bc-120">Haga clic en uno de los puntos de conexión y arrástrelo a otro elemento.</span><span class="sxs-lookup"><span data-stu-id="434bc-120">Click a connection point, and drag it to another element.</span></span> <span data-ttu-id="434bc-121">Asegúrese de conectar todos los elementos.</span><span class="sxs-lookup"><span data-stu-id="434bc-121">Be sure to connect all the elements.</span></span>

## <a name="configure-the-properties-of-the-workflow"></a><span data-ttu-id="434bc-122">Configuración de las propiedades del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="434bc-122">Configure the properties of the workflow</span></span>

<span data-ttu-id="434bc-123">Siga estos pasos para configurar las propiedades del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="434bc-123">Follow these steps to configure the properties of the workflow.</span></span>

1. <span data-ttu-id="434bc-124">Haga clic en el lienzo para asegurarse de que no haya ningún elemento de flujo de trabajo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="434bc-124">Click the canvas to make sure that no workflow element is selected.</span></span>
2. <span data-ttu-id="434bc-125">Haga clic en **Propiedades** para abrir la página de **Propiedades** correspondiente al flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="434bc-125">Click **Properties** to open the **Properties** page for the workflow.</span></span>
3. <span data-ttu-id="434bc-126">Siga los procedimientos del tema [Configurar propiedades del flujo de trabajo](configure-workflow-properties.md).</span><span class="sxs-lookup"><span data-stu-id="434bc-126">Follow the procedures in the [Configure workflow properties](configure-workflow-properties.md) topic.</span></span>

## <a name="configure-the-elements-of-the-workflow"></a><span data-ttu-id="434bc-127">Configuración de los elementos del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="434bc-127">Configure the elements of the workflow</span></span>

<span data-ttu-id="434bc-128">Configure los elementos que arrastró al lienzo.</span><span class="sxs-lookup"><span data-stu-id="434bc-128">Configure each element that you dragged onto the canvas.</span></span> <span data-ttu-id="434bc-129">Para obtener más información acerca de cómo configurar cada elemento de flujo de trabajo, vea los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="434bc-129">For information about how to configure each workflow element, see the following topics:</span></span>

- [<span data-ttu-id="434bc-130">Configurar tareas manuales en un flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="434bc-130">Configure manual tasks in a workflow</span></span>](configure-manual-task-workflow.md)
- [<span data-ttu-id="434bc-131">Configurar tareas automatizadas en un flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="434bc-131">Configure automated tasks in a workflow</span></span>](configure-automated-task-workflow.md)
- [<span data-ttu-id="434bc-132">Configurar los procesos de aprobación en un flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="434bc-132">Configure approval processes in a workflow</span></span>](configure-approval-process-workflow.md)
- [<span data-ttu-id="434bc-133">Configurar los pasos de aprobación en un flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="434bc-133">Configure approval steps in a workflow</span></span>](configure-approval-step-workflow.md)
- [<span data-ttu-id="434bc-134">Configurar decisiones manuales en un flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="434bc-134">Configure manual decisions in a workflow</span></span>](configure-manual-decision-workflow.md)
- [<span data-ttu-id="434bc-135">Configurar decisiones condicionales en un flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="434bc-135">Configure conditional decisions in a workflow</span></span>](configure-conditional-decision-workflow.md)
- [<span data-ttu-id="434bc-136">Configurar ramas paralelas en un flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="434bc-136">Configure parallel branches in a workflow</span></span>](configure-parallel-activity-workflow.md)
- [<span data-ttu-id="434bc-137">Configurar una rama paralela</span><span class="sxs-lookup"><span data-stu-id="434bc-137">Configure a parallel branch</span></span>](configure-parallel-branch-workflow.md)
- [<span data-ttu-id="434bc-138">Configurar flujos de trabajo de elementos</span><span class="sxs-lookup"><span data-stu-id="434bc-138">Configure line-item workflows</span></span>](configure-line-item-workflow.md)

## <a name="resolve-any-errors-or-warnings"></a><span data-ttu-id="434bc-139">Resolución de los errores o advertencias</span><span class="sxs-lookup"><span data-stu-id="434bc-139">Resolve any errors or warnings</span></span>

<span data-ttu-id="434bc-140">En el panel **Errores y advertencias** ubicado en la parte inferior del editor de flujo de trabajo se muestran los mensajes generados para el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="434bc-140">The **Errors and warnings** pane at the bottom of the workflow editor shows messages that have been generated for the workflow.</span></span> <span data-ttu-id="434bc-141">Para encontrar el elemento en el que se produjo un error o advertencia, haga doble clic en el mensaje de error o advertencia.</span><span class="sxs-lookup"><span data-stu-id="434bc-141">To find the element where an error or warning occurred, double-click the error or warning message.</span></span> <span data-ttu-id="434bc-142">Antes de poder activar el flujo de trabajo, debe resolver todos los errores y advertencias.</span><span class="sxs-lookup"><span data-stu-id="434bc-142">You must resolve all errors and warnings before you can make the workflow active.</span></span>

## <a name="save-and-activate-the-workflow"></a><span data-ttu-id="434bc-143">Guardado y activación del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="434bc-143">Save and activate the workflow</span></span>

<span data-ttu-id="434bc-144">Cuando esté listo para guardar y activar el flujo de trabajo, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="434bc-144">When you're ready to save and activate the workflow, follow these steps.</span></span>

1. <span data-ttu-id="434bc-145">Haga clic en **Guardar y cerrar** para cerrar el editor de flujo de trabajo y abrir la página **Guardar flujo de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="434bc-145">Click **Save and close** to close the workflow editor and open the **Save workflow** page.</span></span>
2. <span data-ttu-id="434bc-146">Escriba comentarios acerca de los cambios que realizó en el flujo de trabajo y a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="434bc-146">Enter comments about the changes that you've made to the workflow, and then click **OK**.</span></span>
3. <span data-ttu-id="434bc-147">Si se han resuelto todos los errores y advertencias, se mostrará la página **Activar flujo de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="434bc-147">If all errors and warnings have been resolved, the **Activate workflow** page appears.</span></span> <span data-ttu-id="434bc-148">Seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="434bc-148">Select one of the following options:</span></span>

    - <span data-ttu-id="434bc-149">Para activar esta versión del flujo de trabajo, haga clic en **Activar la nueva versión**.</span><span class="sxs-lookup"><span data-stu-id="434bc-149">To activate this version of the workflow, click **Activate the new version**.</span></span> <span data-ttu-id="434bc-150">Cuando un flujo de trabajo está activo, los usuarios pueden enviar documentos a él para que se los procese.</span><span class="sxs-lookup"><span data-stu-id="434bc-150">When a workflow is active, users can submit documents to it for processing.</span></span>
    - <span data-ttu-id="434bc-151">Si no desea activar esta versión, haga clic en **No activar la versión nueva**.</span><span class="sxs-lookup"><span data-stu-id="434bc-151">If you don't want to activate this version, click **Do not activate the new version**.</span></span> <span data-ttu-id="434bc-152">Podrá activar el flujo de trabajo en otro momento.</span><span class="sxs-lookup"><span data-stu-id="434bc-152">You can activate the workflow later.</span></span>
