---
title: Configurar tareas manuales en un flujo de trabajo
description: Este tema explica cómo configurar las propiedades para una tarea manual.
author: sericks007
manager: AnnBe
ms.date: 08/23/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 192191
ms.assetid: 27f1afde-ff26-4b6f-8c11-27ec49130bbb
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 492c49b1a3e8334bca401770c4c2db04e8892691
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "2190175"
---
# <a name="configure-manual-tasks-in-a-workflow"></a><span data-ttu-id="b46c0-103">Configurar tareas manuales en un flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="b46c0-103">Configure manual tasks in a workflow</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b46c0-104">Este tema explica cómo configurar las propiedades para una tarea manual.</span><span class="sxs-lookup"><span data-stu-id="b46c0-104">This topic explains how to configure the properties for a manual task.</span></span>

<span data-ttu-id="b46c0-105">Para configurar una tarea manual en el editor de flujo de trabajo, haga clic con el botón secundario en la tarea y, a continuación, haga clic en **Propiedades** para abrir la página **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="b46c0-105">To configure a manual task in the workflow editor, right-click the task, and then click **Properties** to open the **Properties** page.</span></span> <span data-ttu-id="b46c0-106">A continuación, use los siguientes procedimientos para configurar las propiedades de la tarea manual.</span><span class="sxs-lookup"><span data-stu-id="b46c0-106">Then use the following procedures to configure the properties for the manual task.</span></span>

## <a name="name-the-task"></a><span data-ttu-id="b46c0-107">Asignación de un nombre a la tarea</span><span class="sxs-lookup"><span data-stu-id="b46c0-107">Name the task</span></span>

<span data-ttu-id="b46c0-108">Siga estos pasos para asignar un nombre a la tarea manual.</span><span class="sxs-lookup"><span data-stu-id="b46c0-108">Follow these steps to enter a name for the manual task.</span></span>

1. <span data-ttu-id="b46c0-109">En el panel izquierdo, haga clic en **Configuración básica**.</span><span class="sxs-lookup"><span data-stu-id="b46c0-109">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="b46c0-110">En el campo **Nombre**, especifique un nombre único para la tarea.</span><span class="sxs-lookup"><span data-stu-id="b46c0-110">In the **Name** field, enter a unique name for the task.</span></span>

## <a name="enter-a-subject-line-and-instructions"></a><span data-ttu-id="b46c0-111">Especificación de una línea de asunto e instrucciones</span><span class="sxs-lookup"><span data-stu-id="b46c0-111">Enter a subject line and instructions</span></span>

<span data-ttu-id="b46c0-112">Debe proporcionar una línea de asunto e instrucciones a los usuarios que están asignados a la tarea.</span><span class="sxs-lookup"><span data-stu-id="b46c0-112">You must provide a subject line and instructions to users who are assigned to the task.</span></span> <span data-ttu-id="b46c0-113">Por ejemplo, si está configurando una tarea para solicitudes de compra, el usuario asignado a la tarea ve la línea de asunto y las instrucciones en la página **Solicitudes de compra**.</span><span class="sxs-lookup"><span data-stu-id="b46c0-113">For example, if you're configuring a task for purchase requisitions, the user who is assigned to the task sees the subject line and instructions on the **Purchase requisitions** page.</span></span> <span data-ttu-id="b46c0-114">La línea de asunto se muestra en una barra de mensajes de la página.</span><span class="sxs-lookup"><span data-stu-id="b46c0-114">The subject line appears in a message bar on the page.</span></span> <span data-ttu-id="b46c0-115">A continuación, el usuario puede hacer clic en el icono de dicha barra para ver las instrucciones.</span><span class="sxs-lookup"><span data-stu-id="b46c0-115">The user can then click the icon in the message bar to view the instructions.</span></span> <span data-ttu-id="b46c0-116">Siga estos pasos para escribir una línea de asunto e instrucciones.</span><span class="sxs-lookup"><span data-stu-id="b46c0-116">Follow these steps to enter a subject line and instructions.</span></span>

1. <span data-ttu-id="b46c0-117">En el panel izquierdo, haga clic en **Configuración básica**.</span><span class="sxs-lookup"><span data-stu-id="b46c0-117">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="b46c0-118">En el campo **Asunto del elemento de trabajo**, escriba la línea de asunto.</span><span class="sxs-lookup"><span data-stu-id="b46c0-118">In the **Work item subject** field, enter the subject line.</span></span>
3. <span data-ttu-id="b46c0-119">Para personalizar la línea de asunto, puede insertar marcadores de posición.</span><span class="sxs-lookup"><span data-stu-id="b46c0-119">To personalize the subject line, you can insert placeholders.</span></span> <span data-ttu-id="b46c0-120">Estos se reemplazan con los datos adecuados cuando se muestra la línea de asunto a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="b46c0-120">Placeholders are replaced with appropriate data when the subject line is shown to users.</span></span> <span data-ttu-id="b46c0-121">Para insertar un marcador de posición, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="b46c0-121">Follow these steps to insert a placeholder:</span></span>

    1. <span data-ttu-id="b46c0-122">En el cuadro de texto, gaga clic para especificar dónde debe aparecer el marcador de posición.</span><span class="sxs-lookup"><span data-stu-id="b46c0-122">In the text box, click where the placeholder should appear.</span></span>
    2. <span data-ttu-id="b46c0-123">Haga clic en **Insertar marcador de posición**.</span><span class="sxs-lookup"><span data-stu-id="b46c0-123">Click **Insert placeholder**.</span></span>
    3. <span data-ttu-id="b46c0-124">En la lista que aparece, seleccione el marcador de posición que desea insertar.</span><span class="sxs-lookup"><span data-stu-id="b46c0-124">In the list that appears, select the placeholder to insert.</span></span>
    4. <span data-ttu-id="b46c0-125">Haga clic en **Insertar**.</span><span class="sxs-lookup"><span data-stu-id="b46c0-125">Click **Insert**.</span></span>

4. <span data-ttu-id="b46c0-126">Para agregar traducciones de la línea de asunto, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="b46c0-126">To add translations of the subject line, follow these steps:</span></span>

    1. <span data-ttu-id="b46c0-127">Haga clic en **Traducciones**.</span><span class="sxs-lookup"><span data-stu-id="b46c0-127">Click **Translations**.</span></span>
    2. <span data-ttu-id="b46c0-128">En la página que aparece, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="b46c0-128">On the page that appears, click **Add**.</span></span>
    3. <span data-ttu-id="b46c0-129">En la lista que aparece, seleccione el idioma en el que escribe el texto.</span><span class="sxs-lookup"><span data-stu-id="b46c0-129">In the list that appears, select the language that you're entering the text in.</span></span>
    4. <span data-ttu-id="b46c0-130">En el campo **Texto traducido**, escriba el texto.</span><span class="sxs-lookup"><span data-stu-id="b46c0-130">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="b46c0-131">Para personalizar el texto, puede insertar marcadores de posición como se describe en el paso 3.</span><span class="sxs-lookup"><span data-stu-id="b46c0-131">To personalize the text, you can insert placeholders as described in step 3.</span></span>
    6. <span data-ttu-id="b46c0-132">Haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="b46c0-132">Click **Close**.</span></span>

5. <span data-ttu-id="b46c0-133">En el campo **Instrucciones del elemento de trabajo**, escriba las instrucciones.</span><span class="sxs-lookup"><span data-stu-id="b46c0-133">In the **Work item instructions** field, enter the instructions.</span></span>
6. <span data-ttu-id="b46c0-134">Para personalizar las instrucciones, puede insertar marcadores de posición.</span><span class="sxs-lookup"><span data-stu-id="b46c0-134">To personalize the instructions, you can insert placeholders.</span></span> <span data-ttu-id="b46c0-135">Estos se reemplazan con los datos adecuados cuando las instrucciones se muestran a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="b46c0-135">Placeholders are replaced with appropriate data when the instructions are shown to users.</span></span> <span data-ttu-id="b46c0-136">Para insertar un marcador de posición, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="b46c0-136">Follow these steps to insert a placeholder:</span></span>

    1. <span data-ttu-id="b46c0-137">En el cuadro de texto, gaga clic para especificar dónde debe aparecer el marcador de posición.</span><span class="sxs-lookup"><span data-stu-id="b46c0-137">In the text box, click where the placeholder should appear.</span></span>
    2. <span data-ttu-id="b46c0-138">Haga clic en **Insertar marcador de posición**.</span><span class="sxs-lookup"><span data-stu-id="b46c0-138">Click **Insert placeholder**.</span></span>
    3. <span data-ttu-id="b46c0-139">En la lista que aparece, seleccione el marcador de posición que desea insertar.</span><span class="sxs-lookup"><span data-stu-id="b46c0-139">In the list that appears, select the placeholder to insert.</span></span>
    4. <span data-ttu-id="b46c0-140">Haga clic en **Insertar**.</span><span class="sxs-lookup"><span data-stu-id="b46c0-140">Click **Insert**.</span></span>

7. <span data-ttu-id="b46c0-141">Para agregar traducciones de las instrucciones, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="b46c0-141">To add translations of the instructions, follow these steps:</span></span>

    1. <span data-ttu-id="b46c0-142">Haga clic en **Traducciones**.</span><span class="sxs-lookup"><span data-stu-id="b46c0-142">Click **Translations**.</span></span>
    2. <span data-ttu-id="b46c0-143">En la página que aparece, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="b46c0-143">On the page that appears, click **Add**.</span></span>
    3. <span data-ttu-id="b46c0-144">En la lista que aparece, seleccione el idioma en el que escribe el texto.</span><span class="sxs-lookup"><span data-stu-id="b46c0-144">In the list that appears, select the language that you're entering the text in.</span></span>
    4. <span data-ttu-id="b46c0-145">En el campo **Texto traducido**, escriba el texto.</span><span class="sxs-lookup"><span data-stu-id="b46c0-145">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="b46c0-146">Para personalizar el texto, puede insertar marcadores de posición como se describe en el paso 6.</span><span class="sxs-lookup"><span data-stu-id="b46c0-146">To personalize the text, you can insert placeholders as described in step 6.</span></span>
    6. <span data-ttu-id="b46c0-147">Haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="b46c0-147">Click **Close**.</span></span>

## <a name="assign-the-task"></a><span data-ttu-id="b46c0-148">Asignación de la tarea</span><span class="sxs-lookup"><span data-stu-id="b46c0-148">Assign the task</span></span>

<span data-ttu-id="b46c0-149">Siga estos pasos para especificar a quién se debe asignar la tarea manual.</span><span class="sxs-lookup"><span data-stu-id="b46c0-149">Follow these steps to specify who the manual task should be assigned to.</span></span>

1. <span data-ttu-id="b46c0-150">En el panel izquierdo, haga clic en **Asignación**.</span><span class="sxs-lookup"><span data-stu-id="b46c0-150">In the left pane, click **Assignment**.</span></span>
2. <span data-ttu-id="b46c0-151">En la pestaña **Tipo de asignación**, seleccione una de las opciones de la siguiente tabla. A continuación, siga los pasos adicionales correspondientes a la opción elegida antes de realizar el paso 3.</span><span class="sxs-lookup"><span data-stu-id="b46c0-151">On the **Assignment type** tab, select one of the options in the following table, and then follow the additional steps for that option before you go to step 3.</span></span>

    <table>
    <thead>
    <tr>
    <th><span data-ttu-id="b46c0-152">Opción</span><span class="sxs-lookup"><span data-stu-id="b46c0-152">Option</span></span></th>
    <th><span data-ttu-id="b46c0-153">Usuarios a los que está asignada la tarea</span><span class="sxs-lookup"><span data-stu-id="b46c0-153">Users that the task is assigned to</span></span></th>
    <th><span data-ttu-id="b46c0-154">Pasos adicionales</span><span class="sxs-lookup"><span data-stu-id="b46c0-154">Additional steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td><span data-ttu-id="b46c0-155">Participante</span><span class="sxs-lookup"><span data-stu-id="b46c0-155">Participant</span></span></td>
    <td><span data-ttu-id="b46c0-156">Usuarios asignados a un grupo o rol específicos</span><span class="sxs-lookup"><span data-stu-id="b46c0-156">Users who are assigned to a specific group or role</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="b46c0-157">Tras seleccionar <strong>Participante</strong>, en la pestaña <strong>Basado en funciones</strong>, en la lista <strong>Tipo de participante</strong>, seleccione el tipo de grupo o rol al que desea asignar la tarea.</span><span class="sxs-lookup"><span data-stu-id="b46c0-157">After you select <strong>Participant</strong>, on the <strong>Role based</strong> tab, in the <strong>Type of participant</strong> list, select the type of group or role to assign the task to.</span></span></li>
    <li><span data-ttu-id="b46c0-158">En la lista <strong>Participante</strong>, seleccione el grupo o rol al que se debe asignar la tarea.</span><span class="sxs-lookup"><span data-stu-id="b46c0-158">In the <strong>Participant</strong> list, select the group or role to assign the task to.</span></span></li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="b46c0-159">Jerarquía</span><span class="sxs-lookup"><span data-stu-id="b46c0-159">Hierarchy</span></span></td>
    <td><span data-ttu-id="b46c0-160">Usuarios de una jerarquía organizativa específica</span><span class="sxs-lookup"><span data-stu-id="b46c0-160">Users in a specific organizational hierarchy</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="b46c0-161">Tras seleccionar <strong>Jerarquía</strong>, en la pestaña <strong>Selección de jerarquía</strong>, en la lista <strong>Tipo de jerarquía</strong>, seleccione el tipo de jerarquía al que desea asignar la tarea.</span><span class="sxs-lookup"><span data-stu-id="b46c0-161">After you select <strong>Hierarchy</strong>, on the <strong>Hierarchy selection</strong> tab, in the <strong>Hierarchy type</strong> list, select the type of hierarchy to assign the task to.</span></span></li>
    <li><span data-ttu-id="b46c0-162">El sistema debe recuperar un intervalo de nombres de usuario de la jerarquía.</span><span class="sxs-lookup"><span data-stu-id="b46c0-162">The system must retrieve a range of user names from the hierarchy.</span></span> <span data-ttu-id="b46c0-163">Dichos nombres representan a los usuarios a los que se puede asignar la tarea.</span><span class="sxs-lookup"><span data-stu-id="b46c0-163">These names represent users that the task can be assigned to.</span></span> <span data-ttu-id="b46c0-164">Siga estos pasos para especificar el punto de inicio y de finalización del intervalo de nombres de usuario que el sistema recupera:</span><span class="sxs-lookup"><span data-stu-id="b46c0-164">Follow these steps to specify the starting point and ending point of the range of user names that the system retrieves:</span></span> <ol>
    <li><span data-ttu-id="b46c0-165">Para especificar el punto de inicio, seleccione una persona en la lista <strong>Comenzar desde</strong>.</span><span class="sxs-lookup"><span data-stu-id="b46c0-165">To specify the starting point, select a person in the <strong>Start from</strong> list.</span></span></li>
    <li><span data-ttu-id="b46c0-166">Para especificar el punto de finalización, haga clic en <strong>Agregar condición</strong>.</span><span class="sxs-lookup"><span data-stu-id="b46c0-166">To specify the ending point, click <strong>Add condition</strong>.</span></span> <span data-ttu-id="b46c0-167">A continuación, especifique una condición que determine en qué parte de la jerarquía el sistema dejará de recuperar nombres.</span><span class="sxs-lookup"><span data-stu-id="b46c0-167">Then enter a condition that determines where in the hierarchy the system stops retrieving names.</span></span></li>
    </ol>
    </li>
    <li><span data-ttu-id="b46c0-168">En la pestaña <strong>Opciones de jerarquía</strong>, especifique a qué usuarios del intervalo se debe asignar la tarea:</span><span class="sxs-lookup"><span data-stu-id="b46c0-168">On the <strong>Hierarchy options</strong> tab, specify which users in the range the task should be assigned to:</span></span> <ul>
    <li><span data-ttu-id="b46c0-169"><strong>Asignar a todos los usuarios recuperados</strong>: la tarea se asigna a todos los usuarios del intervalo.</span><span class="sxs-lookup"><span data-stu-id="b46c0-169"><strong>Assign to all users retrieved</strong> – The task is assigned to all users in the range.</span></span></li>
    <li><span data-ttu-id="b46c0-170"><strong>Asignar sólo al último usuario recuperado</strong>: la tarea se asigna únicamente al último usuario del intervalo.</span><span class="sxs-lookup"><span data-stu-id="b46c0-170"><strong>Assign only to last user retrieved</strong> – The task is assigned to only the last user in the range.</span></span></li>
    <li><span data-ttu-id="b46c0-171"><strong>Excluir usuarios con la siguiente condición</strong>: la tarea no se asigna a ninguno de los usuarios del intervalo que cumplen con una condición determinada.</span><span class="sxs-lookup"><span data-stu-id="b46c0-171"><strong>Exclude users with the following condition</strong> – The task isn't assigned to users in the range who meet a specific condition.</span></span> <span data-ttu-id="b46c0-172">Haga clic en <strong>Agregar condición</strong> para especificar la condición.</span><span class="sxs-lookup"><span data-stu-id="b46c0-172">Click <strong>Add condition</strong> to specify the condition.</span></span></li>
    </ul>
    </li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="b46c0-173">Usuario del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="b46c0-173">Workflow user</span></span></td>
    <td><span data-ttu-id="b46c0-174">Usuarios del flujo de trabajo actual</span><span class="sxs-lookup"><span data-stu-id="b46c0-174">Users in the current workflow</span></span></td>
    <td>
    <ul>
    <li><span data-ttu-id="b46c0-175">Tras seleccionar <strong>Usuario del flujo de trabajo</strong>, en la pestaña <strong>Usuario del flujo de trabajo</strong>, en la pestaña <strong>Usuario del flujo de trabajo</strong>, seleccione un usuario que participe en el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="b46c0-175">After you select <strong>Workflow user</strong>, on the <strong>Workflow user</strong> tab, in the <strong>Workflow user</strong> list, select a user who participates in the workflow.</span></span></li>
    </ul>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="b46c0-176">Usuario</span><span class="sxs-lookup"><span data-stu-id="b46c0-176">User</span></span></td>
    <td><span data-ttu-id="b46c0-177">Usuarios concretos</span><span class="sxs-lookup"><span data-stu-id="b46c0-177">Specific users</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="b46c0-178">Tras seleccionar <strong>Usuario</strong>, haga clic en la pestaña <strong>Usuario</strong>.</span><span class="sxs-lookup"><span data-stu-id="b46c0-178">After you select <strong>User</strong>, click the <strong>User</strong> tab.</span></span></li>
    <li><span data-ttu-id="b46c0-179">La lista <strong>Usuarios disponibles</strong> incluye todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="b46c0-179">The <strong>Available users</strong> list includes all users.</span></span> <span data-ttu-id="b46c0-180">Seleccione aquellos a los que desea asignar la tarea y, a continuación, muévalos a la lista <strong>Usuarios seleccionados</strong>.</span><span class="sxs-lookup"><span data-stu-id="b46c0-180">Select the users to assign the task to, and then move those users to the <strong>Selected users</strong> list.</span></span></li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="b46c0-181">Cola</span><span class="sxs-lookup"><span data-stu-id="b46c0-181">Queue</span></span></td>
    <td><span data-ttu-id="b46c0-182">Una cola de elementos de trabajo</span><span class="sxs-lookup"><span data-stu-id="b46c0-182">A work item queue</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="b46c0-183">Tras seleccionar <strong>Cola</strong>, haga clic en la pestaña <strong>Basado en cola</strong>.</span><span class="sxs-lookup"><span data-stu-id="b46c0-183">After you select <strong>Queue</strong>, click the <strong>Queue based</strong> tab.</span></span></li>
    <li><span data-ttu-id="b46c0-184">Para asignar la tarea a una cola específica, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="b46c0-184">To assign the task to a specific queue, follow these steps:</span></span> <ol>
    <li><span data-ttu-id="b46c0-185">En la lista <strong>Tipo de cola</strong>, seleccione <strong>Colas de elementos de trabajo</strong>.</span><span class="sxs-lookup"><span data-stu-id="b46c0-185">In the <strong>Queue type</strong> list, select <strong>Work item queues</strong>.</span></span></li>
    <li><span data-ttu-id="b46c0-186">En la lista <strong>Nombre de cola</strong>, seleccione la cola.</span><span class="sxs-lookup"><span data-stu-id="b46c0-186">In the <strong>Queue name</strong> list, select the queue.</span></span></li>
    </ol>
    </li>
    <li><span data-ttu-id="b46c0-187">Si la cola a la que se debe asignar la tarea debe estar determinada por una condición específica, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="b46c0-187">If a specific condition should determine which queue the task is assigned to, follow these steps:</span></span> <ol>
    <li><span data-ttu-id="b46c0-188">En la lista <strong>Tipo de cola</strong>, seleccione <strong>Colas de elementos de trabajo condicional</strong>.</span><span class="sxs-lookup"><span data-stu-id="b46c0-188">In the <strong>Queue type</strong> list, select <strong>Conditional work item queues</strong>.</span></span></li>
    <li><span data-ttu-id="b46c0-189">En la lista <strong>Nombre de cola</strong>, seleccione <strong>Cola condicional</strong>.</span><span class="sxs-lookup"><span data-stu-id="b46c0-189">In the <strong>Queue name</strong> list, select <strong>Conditional queue</strong>.</span></span></li>
    </ol>
    </li>
    </ol>
    <blockquote>[!NOTE] <span data-ttu-id="b46c0-190">Esta opción solo se usa para algunos flujos de trabajo, como Gestión de casos.</span><span class="sxs-lookup"><span data-stu-id="b46c0-190">This option is used for only a few workflows, such as Case management.</span></span></blockquote>
    </td>
    </tr>
    </tbody>
    </table>

3. <span data-ttu-id="b46c0-191">En la pestaña **Límite de tiempo**, en el campo **Duración**, especifique el tiempo del que dispone el usuario para completar la tarea.</span><span class="sxs-lookup"><span data-stu-id="b46c0-191">On the **Time limit** tab, in the **Duration** field, specify how much time the user has to complete the task.</span></span> <span data-ttu-id="b46c0-192">Seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="b46c0-192">Select one of the following options:</span></span>

    - <span data-ttu-id="b46c0-193">**Horas**: escriba la cantidad de horas de las que dispone el usuario para completar la tarea.</span><span class="sxs-lookup"><span data-stu-id="b46c0-193">**Hours** – Enter the number of hours that the user has to complete the task.</span></span> <span data-ttu-id="b46c0-194">A continuación, seleccione el calendario que usa la organización y escriba la información pertinente acerca de la semana laboral de la organización.</span><span class="sxs-lookup"><span data-stu-id="b46c0-194">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="b46c0-195">**Días**: escriba la cantidad de días de los que dispone el usuario para completar la tarea.</span><span class="sxs-lookup"><span data-stu-id="b46c0-195">**Days** – Enter the number of days that the user has to complete the task.</span></span> <span data-ttu-id="b46c0-196">A continuación, seleccione el calendario que usa la organización y escriba la información pertinente acerca de la semana laboral de la organización.</span><span class="sxs-lookup"><span data-stu-id="b46c0-196">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="b46c0-197">**Semanas**: escriba la cantidad de semanas de las que dispone el usuario para completar la tarea.</span><span class="sxs-lookup"><span data-stu-id="b46c0-197">**Weeks** – Enter the number of weeks that the user has to complete the task.</span></span>
    - <span data-ttu-id="b46c0-198">**Meses**: seleccione el día y la semana en los que vence el plazo para completar la tarea.</span><span class="sxs-lookup"><span data-stu-id="b46c0-198">**Months** – Select the day and week that the user must complete the task by.</span></span> <span data-ttu-id="b46c0-199">Por ejemplo, tal vez desee que el usuario haya completado la tarea antes del viernes de la tercera semana del mes.</span><span class="sxs-lookup"><span data-stu-id="b46c0-199">For example, you might want the user to complete the task by Friday of the third week of the month.</span></span>
    - <span data-ttu-id="b46c0-200">**Años**: seleccione el día, la semana y el mes en los que vence el plazo para completar la tarea.</span><span class="sxs-lookup"><span data-stu-id="b46c0-200">**Years** – Select the day, week, and month that the user must complete the task by.</span></span> <span data-ttu-id="b46c0-201">Por ejemplo, tal vez desee que el usuario haya completado la tarea antes del viernes de la tercera semana de diciembre.</span><span class="sxs-lookup"><span data-stu-id="b46c0-201">For example, you might want the user to complete the task by Friday of the third week of December.</span></span>

    <span data-ttu-id="b46c0-202">Si el usuario no completa la tarea en el tiempo asignado, la tarea se considera vencida.</span><span class="sxs-lookup"><span data-stu-id="b46c0-202">If the user doesn't complete the task in the allotted time, the task is overdue.</span></span> <span data-ttu-id="b46c0-203">Las tareas vencidas se pueden remitir a una instancia superior en función de las opciones que se seleccionen en el área **Remisión a una instancia superior** de la página.</span><span class="sxs-lookup"><span data-stu-id="b46c0-203">A task that is overdue can be escalated, based on the options that you select in the **Escalation** area of the page.</span></span>

## <a name="specify-what-happens-when-the-task-is-overdue"></a><span data-ttu-id="b46c0-204">Especificación de la acción que se realiza cuando vence la tarea</span><span class="sxs-lookup"><span data-stu-id="b46c0-204">Specify what happens when the task is overdue</span></span>

<span data-ttu-id="b46c0-205">Si un usuario no completa la tarea manual en el tiempo asignado, la tarea se considera vencida.</span><span class="sxs-lookup"><span data-stu-id="b46c0-205">If a user doesn't complete the manual task in the allotted time, the task is overdue.</span></span> <span data-ttu-id="b46c0-206">Las tareas vencidas se pueden remitir a una instancia superior o asignar a otro usuario de forma automática.</span><span class="sxs-lookup"><span data-stu-id="b46c0-206">A task that is overdue can be escalated, or automatically assigned to another user.</span></span> <span data-ttu-id="b46c0-207">Si la tarea ha vencido, siga estos pasos para remitirla a una instancia superior.</span><span class="sxs-lookup"><span data-stu-id="b46c0-207">Follow these steps to escalate the task if it's overdue.</span></span>

1. <span data-ttu-id="b46c0-208">En el panel izquierdo, haga clic en **Remisión a una instancia superior**.</span><span class="sxs-lookup"><span data-stu-id="b46c0-208">In the left pane, click **Escalation**.</span></span>
2. <span data-ttu-id="b46c0-209">Active la casilla de verificación **Usar ruta de remisión a una instancia superior** para crear una ruta de remisión a una instancia superior.</span><span class="sxs-lookup"><span data-stu-id="b46c0-209">Select the **Use escalation path** check box to create an escalation path.</span></span> <span data-ttu-id="b46c0-210">De manera automática, el sistema asigna la tarea a los usuarios que forman parte de la ruta de remisión a una instancia superior.</span><span class="sxs-lookup"><span data-stu-id="b46c0-210">The system automatically assigns the task to the users who are listed in the escalation path.</span></span> <span data-ttu-id="b46c0-211">La siguiente tabla, por ejemplo, representa una ruta de remisión a una instancia superior.</span><span class="sxs-lookup"><span data-stu-id="b46c0-211">For example, the following table represents an escalation path.</span></span>

    | <span data-ttu-id="b46c0-212">Secuencia</span><span class="sxs-lookup"><span data-stu-id="b46c0-212">Sequence</span></span> | <span data-ttu-id="b46c0-213">Ruta de remisión a una instancia superior</span><span class="sxs-lookup"><span data-stu-id="b46c0-213">Escalation path</span></span>      |
    |----------|----------------------|
    | <span data-ttu-id="b46c0-214">1</span><span class="sxs-lookup"><span data-stu-id="b46c0-214">1</span></span>        | <span data-ttu-id="b46c0-215">Asignar a rol: Donna</span><span class="sxs-lookup"><span data-stu-id="b46c0-215">Assign to: Donna</span></span>     |
    | <span data-ttu-id="b46c0-216">2</span><span class="sxs-lookup"><span data-stu-id="b46c0-216">2</span></span>        | <span data-ttu-id="b46c0-217">Asignar a rol: Erin</span><span class="sxs-lookup"><span data-stu-id="b46c0-217">Assign to: Erin</span></span>      |
    | <span data-ttu-id="b46c0-218">3</span><span class="sxs-lookup"><span data-stu-id="b46c0-218">3</span></span>        | <span data-ttu-id="b46c0-219">Acción final: Rechazar</span><span class="sxs-lookup"><span data-stu-id="b46c0-219">Final action: Reject</span></span> |

    <span data-ttu-id="b46c0-220">En este ejemplo, el sistema asigna la tarea vencida a Donna.</span><span class="sxs-lookup"><span data-stu-id="b46c0-220">In this example, the system assigns the overdue task to Donna.</span></span> <span data-ttu-id="b46c0-221">Si Donna no completa la tarea en el tiempo asignado, el sistema la asigna a Erin.</span><span class="sxs-lookup"><span data-stu-id="b46c0-221">If Donna doesn't complete the task in the allotted time, the system assigns the task to Erin.</span></span> <span data-ttu-id="b46c0-222">Si Erin no completa la tarea en el tiempo asignado, el sistema rechaza el documento que se debía procesar.</span><span class="sxs-lookup"><span data-stu-id="b46c0-222">If Erin doesn't complete the task in the allotted time, the system rejects the document that was submitted for processing.</span></span>

3. <span data-ttu-id="b46c0-223">Para agregar un usuario a la ruta de remisión a una instancia superior, haga clic en **Agregar remisión a una instancia superior**.</span><span class="sxs-lookup"><span data-stu-id="b46c0-223">To add a user to the escalation path, click **Add escalation**.</span></span> <span data-ttu-id="b46c0-224">En la pestaña **Tipo de asignación**, seleccione una de las opciones de la siguiente tabla. A continuación, siga los pasos adicionales correspondientes a la opción elegida antes de realizar el paso 4.</span><span class="sxs-lookup"><span data-stu-id="b46c0-224">On the **Assignment type** tab, select one of the options in the following table, and then follow the additional steps for that option before you go to step 4.</span></span>

    <table>
    <thead>
    <tr>
    <th><span data-ttu-id="b46c0-225">Opción</span><span class="sxs-lookup"><span data-stu-id="b46c0-225">Option</span></span></th>
    <th><span data-ttu-id="b46c0-226">Usuarios a los que se remite la tarea</span><span class="sxs-lookup"><span data-stu-id="b46c0-226">Users that the task is escalated to</span></span></th>
    <th><span data-ttu-id="b46c0-227">Pasos adicionales</span><span class="sxs-lookup"><span data-stu-id="b46c0-227">Additional steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td><span data-ttu-id="b46c0-228">Jerarquía</span><span class="sxs-lookup"><span data-stu-id="b46c0-228">Hierarchy</span></span></td>
    <td><span data-ttu-id="b46c0-229">Usuarios de una jerarquía organizativa específica</span><span class="sxs-lookup"><span data-stu-id="b46c0-229">Users in a specific organizational hierarchy</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="b46c0-230">Tras seleccionar <strong>Jerarquía</strong>, en la pestaña <strong>Selección de jerarquía</strong>, en la lista <strong>Tipo de jerarquía</strong>, seleccione el tipo de jerarquía al que desea remitir la tarea para una instancia superior.</span><span class="sxs-lookup"><span data-stu-id="b46c0-230">After you select <strong>Hierarchy</strong>, on the <strong>Hierarchy selection</strong> tab, in the <strong>Hierarchy type</strong> list, select the type of hierarchy to escalate the task to.</span></span></li>
    <li><span data-ttu-id="b46c0-231">El sistema debe recuperar un intervalo de nombres de usuario de la jerarquía.</span><span class="sxs-lookup"><span data-stu-id="b46c0-231">The system must retrieve a range of user names from the hierarchy.</span></span> <span data-ttu-id="b46c0-232">Dichos nombres representan a los usuarios a los que se puede remitir la tarea para una instancia superior.</span><span class="sxs-lookup"><span data-stu-id="b46c0-232">These names represent users that the task can be escalated to.</span></span> <span data-ttu-id="b46c0-233">Siga estos pasos para especificar el punto de inicio y de finalización del intervalo de nombres de usuario que el sistema recupera:</span><span class="sxs-lookup"><span data-stu-id="b46c0-233">Follow these steps to specify the starting point and ending point of the range of user names that the system retrieves:</span></span> <ol>
    <li><span data-ttu-id="b46c0-234">Para especificar el punto de inicio, seleccione una persona en la lista <strong>Comenzar desde</strong>.</span><span class="sxs-lookup"><span data-stu-id="b46c0-234">To specify the starting point, select a person in the <strong>Start from</strong> list.</span></span></li>
    <li><span data-ttu-id="b46c0-235">Para especificar el punto de finalización, haga clic en <strong>Agregar condición</strong>.</span><span class="sxs-lookup"><span data-stu-id="b46c0-235">To specify the ending point, click <strong>Add condition</strong>.</span></span> <span data-ttu-id="b46c0-236">A continuación, especifique una condición que determine en qué parte de la jerarquía el sistema dejará de recuperar nombres.</span><span class="sxs-lookup"><span data-stu-id="b46c0-236">Then enter a condition that determines where in the hierarchy the system stops retrieving names.</span></span></li>
    </ol>
    </li>
    <li><span data-ttu-id="b46c0-237">En la pestaña <strong>Opciones de jerarquía</strong>, especifique a qué usuarios del intervalo se debe remitir la tarea para una instancia superior:</span><span class="sxs-lookup"><span data-stu-id="b46c0-237">On the <strong>Hierarchy options</strong> tab, specify which users in the range the task should be escalated to:</span></span> <ul>
    <li><span data-ttu-id="b46c0-238"><strong>Asignar a todos los usuarios recuperados</strong>: la tarea se remite para una instancia superior para todos los usuarios del intervalo.</span><span class="sxs-lookup"><span data-stu-id="b46c0-238"><strong>Assign to all users retrieved</strong> – The task is escalated to all users in the range.</span></span></li>
    <li><span data-ttu-id="b46c0-239"><strong>Asignar sólo al último usuario recuperado</strong>: la tarea se remite para una instancia superior únicamente al último usuario del intervalo.</span><span class="sxs-lookup"><span data-stu-id="b46c0-239"><strong>Assign only to last user retrieved</strong> – The task is escalated to only the last user in the range.</span></span></li>
    <li><span data-ttu-id="b46c0-240"><strong>Excluir usuarios con la siguiente condición</strong>: esta tarea no se remite para una instancia superior a ninguno de los usuarios del intervalo que cumplen con una condición determinada.</span><span class="sxs-lookup"><span data-stu-id="b46c0-240"><strong>Exclude users with the following condition</strong> – This task isn't escalated to users in the range who meet a specific condition.</span></span> <span data-ttu-id="b46c0-241">Haga clic en <strong>Agregar condición</strong> para especificar la condición.</span><span class="sxs-lookup"><span data-stu-id="b46c0-241">Click <strong>Add condition</strong> to specify the condition.</span></span></li>
    </ul>
    </li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="b46c0-242">Usuario del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="b46c0-242">Workflow user</span></span></td>
    <td><span data-ttu-id="b46c0-243">Usuarios del flujo de trabajo actual</span><span class="sxs-lookup"><span data-stu-id="b46c0-243">Users in the current workflow</span></span></td>
    <td>
    <ul>
    <li><span data-ttu-id="b46c0-244">Tras seleccionar <strong>Usuario del flujo de trabajo</strong>, en la pestaña <strong>Usuario del flujo de trabajo</strong>, en la pestaña <strong>Usuario del flujo de trabajo</strong>, seleccione un usuario que participe en el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="b46c0-244">After you select <strong>Workflow user</strong>, on the <strong>Workflow user</strong> tab, in the <strong>Workflow user</strong> list, select a user who participates in the workflow.</span></span></li>
    </ul>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="b46c0-245">Usuario</span><span class="sxs-lookup"><span data-stu-id="b46c0-245">User</span></span></td>
    <td><span data-ttu-id="b46c0-246">Usuarios concretos</span><span class="sxs-lookup"><span data-stu-id="b46c0-246">Specific users</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="b46c0-247">Tras seleccionar <strong>Usuario</strong>, haga clic en la pestaña <strong>Usuario</strong>.</span><span class="sxs-lookup"><span data-stu-id="b46c0-247">After you select <strong>User</strong>, click the <strong>User</strong> tab.</span></span></li>
    <li><span data-ttu-id="b46c0-248">La lista <strong>Usuarios disponibles</strong> incluye todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="b46c0-248">The <strong>Available users</strong> list includes all users.</span></span> <span data-ttu-id="b46c0-249">Seleccione aquellos a los que desea remitir la tarea para una instancia superior y, a continuación, muévalos a la lista <strong>Usuarios seleccionados</strong>.</span><span class="sxs-lookup"><span data-stu-id="b46c0-249">Select the users to escalate the task to, and then move those users to the <strong>Selected users</strong> list.</span></span></li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

4. <span data-ttu-id="b46c0-250">En la pestaña **Límite de tiempo**, en el campo **Duración**, especifique el tiempo del que dispone el usuario para completar la tarea.</span><span class="sxs-lookup"><span data-stu-id="b46c0-250">On the **Time limit** tab, in the **Duration** field, specify how much time the user has to complete the task.</span></span> <span data-ttu-id="b46c0-251">Seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="b46c0-251">Select one of the following options:</span></span>

    - <span data-ttu-id="b46c0-252">**Horas**: escriba la cantidad de horas de las que dispone el usuario para completar la tarea.</span><span class="sxs-lookup"><span data-stu-id="b46c0-252">**Hours** – Enter the number of hours that the user has to complete the task.</span></span> <span data-ttu-id="b46c0-253">A continuación, seleccione el calendario que usa la organización y escriba la información pertinente acerca de la semana laboral de la organización.</span><span class="sxs-lookup"><span data-stu-id="b46c0-253">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="b46c0-254">**Días**: escriba la cantidad de días de los que dispone el usuario para completar la tarea.</span><span class="sxs-lookup"><span data-stu-id="b46c0-254">**Days** – Enter the number of days that the user has to complete the task.</span></span> <span data-ttu-id="b46c0-255">A continuación, seleccione el calendario que usa la organización y escriba la información pertinente acerca de la semana laboral de la organización.</span><span class="sxs-lookup"><span data-stu-id="b46c0-255">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="b46c0-256">**Semanas**: escriba la cantidad de semanas de las que dispone el usuario para completar la tarea.</span><span class="sxs-lookup"><span data-stu-id="b46c0-256">**Weeks** – Enter the number of weeks that the user has to complete the task.</span></span>
    - <span data-ttu-id="b46c0-257">**Meses**: seleccione el día y la semana en los que vence el plazo para completar la tarea.</span><span class="sxs-lookup"><span data-stu-id="b46c0-257">**Months** – Select the day and week that the user must complete the task by.</span></span> <span data-ttu-id="b46c0-258">Por ejemplo, tal vez desee que el usuario haya completado la tarea antes del viernes de la tercera semana del mes.</span><span class="sxs-lookup"><span data-stu-id="b46c0-258">For example, you might want the user to complete the task by Friday of the third week of the month.</span></span>
    - <span data-ttu-id="b46c0-259">**Años**: seleccione el día, la semana y el mes en los que vence el plazo para completar la tarea.</span><span class="sxs-lookup"><span data-stu-id="b46c0-259">**Years** – Select the day, week, and month that the user must complete the task by.</span></span> <span data-ttu-id="b46c0-260">Por ejemplo, tal vez desee que el usuario haya completado la tarea antes del viernes de la tercera semana de diciembre.</span><span class="sxs-lookup"><span data-stu-id="b46c0-260">For example, you might want the user to complete the task by Friday of the third week of December.</span></span>

5. <span data-ttu-id="b46c0-261">Repita los pasos 3 a 4 por cada usuario que se debe agregar a la ruta de remisión a una instancia superior.</span><span class="sxs-lookup"><span data-stu-id="b46c0-261">Repeat steps 3 through 4 for each user that should be added to the escalation path.</span></span> <span data-ttu-id="b46c0-262">El orden de los usuarios se puede modificar.</span><span class="sxs-lookup"><span data-stu-id="b46c0-262">You can change the order of the users.</span></span>
6. <span data-ttu-id="b46c0-263">Si los usuarios de la ruta de remisión a una instancia superior no completan la tarea en el tiempo asignado, el sistema realiza una acción en la tarea.</span><span class="sxs-lookup"><span data-stu-id="b46c0-263">If the users in the escalation path don't complete the task in the allotted time, the system takes action on the task.</span></span> <span data-ttu-id="b46c0-264">Para especificar la acción que el sistema realiza, seleccione la fila **Acción** y, a continuación, en la pestaña **Finalizar acción**, seleccione una acción.</span><span class="sxs-lookup"><span data-stu-id="b46c0-264">To specify the action that the system takes, select the **Action** row, and then, on the **End action** tab, select an action.</span></span>

## <a name="specify-when-the-system-automatically-acts-on-the-task"></a><span data-ttu-id="b46c0-265">Especificación de las condiciones en que el sistema realiza una acción automática en la tarea</span><span class="sxs-lookup"><span data-stu-id="b46c0-265">Specify when the system automatically acts on the task</span></span>

<span data-ttu-id="b46c0-266">Puede configurar el sistema para que realice alguna acción en la tarea manual si se cumplen ciertas condiciones.</span><span class="sxs-lookup"><span data-stu-id="b46c0-266">You can configure the system to take action on the manual task if specific conditions are met.</span></span> <span data-ttu-id="b46c0-267">Por ejemplo, supongamos que existe una tarea que requiere que un miembro del departamento Informes de gastos revise los recibos que se adjuntan a un informe de gastos.</span><span class="sxs-lookup"><span data-stu-id="b46c0-267">For example, a task requires that a member of the Expense reports department review the receipts that are submitted together with an expense report.</span></span> <span data-ttu-id="b46c0-268">De acuerdo con las directivas de la empresa, esta tarea se debe realizar si el importe total del informe de gastos es superior a 100 USD.</span><span class="sxs-lookup"><span data-stu-id="b46c0-268">According to company policy, this task must be performed if the total amount of the expense report is more than USD 100.</span></span> <span data-ttu-id="b46c0-269">Dada esta situación, puede configurar el sistema para que el estado de la tarea cambie a **Completo** si el importe total es menor que 100.</span><span class="sxs-lookup"><span data-stu-id="b46c0-269">In this scenario, you can configure the system to automatically mark the task as **Complete** when the total amount is less than 100.</span></span> <span data-ttu-id="b46c0-270">Siga estos pasos para especificar cuándo el sistema realiza una acción en la tarea manual.</span><span class="sxs-lookup"><span data-stu-id="b46c0-270">Follow these steps to specify when the system takes action on the manual task.</span></span>

1. <span data-ttu-id="b46c0-271">En el panel izquierdo, haga clic en **Acciones automáticas**.</span><span class="sxs-lookup"><span data-stu-id="b46c0-271">In the left pane, click **Automatic actions**.</span></span>
2. <span data-ttu-id="b46c0-272">Active la casilla **Habilitar acciones automáticas**.</span><span class="sxs-lookup"><span data-stu-id="b46c0-272">Select the **Enable automatic actions** check box.</span></span>
3. <span data-ttu-id="b46c0-273">Haga clic en **Agregar condición**.</span><span class="sxs-lookup"><span data-stu-id="b46c0-273">Click **Add condition**.</span></span>
4. <span data-ttu-id="b46c0-274">Escriba una condición.</span><span class="sxs-lookup"><span data-stu-id="b46c0-274">Enter a condition.</span></span>
5. <span data-ttu-id="b46c0-275">Escriba condiciones adicionales que sean necesarias.</span><span class="sxs-lookup"><span data-stu-id="b46c0-275">Enter any additional conditions that are required.</span></span>
6. <span data-ttu-id="b46c0-276">Para comprobar que las condiciones definidas se hayan configurado correctamente, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="b46c0-276">To verify that the conditions that you entered are configured correctly, follow these steps:</span></span>

    1. <span data-ttu-id="b46c0-277">Haga clic en **Probar**.</span><span class="sxs-lookup"><span data-stu-id="b46c0-277">Click **Test**.</span></span>
    2. <span data-ttu-id="b46c0-278">En la página **Probar condición de flujo de trabajo**, en el área **Comprobar condición**, seleccione un registro.</span><span class="sxs-lookup"><span data-stu-id="b46c0-278">On the **Test workflow condition** page, in the **Validate condition** area, select a record.</span></span>
    3. <span data-ttu-id="b46c0-279">Haga clic en **Probar**.</span><span class="sxs-lookup"><span data-stu-id="b46c0-279">Click **Test**.</span></span> <span data-ttu-id="b46c0-280">El sistema evalúa el registro seleccionado para determinar si reúne las condiciones definidas.</span><span class="sxs-lookup"><span data-stu-id="b46c0-280">The system evaluates the record to determine whether it meets the conditions that you defined.</span></span>
    4. <span data-ttu-id="b46c0-281">Haga clic en **Aceptar** o en **Cancelar** para regresar a la página **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="b46c0-281">Click **OK** or **Cancel** to return to the **Properties** page.</span></span>

7. <span data-ttu-id="b46c0-282">En la lista **Acción de finalización automática**, seleccione la acción que el sistema debe realizar en la tarea.</span><span class="sxs-lookup"><span data-stu-id="b46c0-282">In the **Auto complete action** list, select the action that the system should take on the task.</span></span>

## <a name="specify-when-notifications-are-sent"></a><span data-ttu-id="b46c0-283">Especificación del momento en que se envían notificaciones</span><span class="sxs-lookup"><span data-stu-id="b46c0-283">Specify when notifications are sent</span></span>

<span data-ttu-id="b46c0-284">Puede enviar notificaciones cuando una tarea manual se ha delegado, completado, rechazado, remitido a una instancia superior o cuando se ha solicitado un cambio.</span><span class="sxs-lookup"><span data-stu-id="b46c0-284">You can send notifications to people when a manual task has been delegated, escalated, completed, or rejected, or when a change has been requested.</span></span> <span data-ttu-id="b46c0-285">Siga estos pasos para especificar cuándo se deben enviar notificaciones y a quiénes se deben enviar.</span><span class="sxs-lookup"><span data-stu-id="b46c0-285">Follow these steps to specify when notifications are sent, and who the notifications are sent to.</span></span>

1. <span data-ttu-id="b46c0-286">En el panel izquierdo, haga clic en **Notificaciones**.</span><span class="sxs-lookup"><span data-stu-id="b46c0-286">In the left pane, click **Notifications**.</span></span>
2. <span data-ttu-id="b46c0-287">Active las casillas de verificación junto a los eventos que deben notificarse:</span><span class="sxs-lookup"><span data-stu-id="b46c0-287">Select the check box next to the events that notifications should be sent for:</span></span>

    - <span data-ttu-id="b46c0-288">**Delegar**: la tarea se ha asignado a otro usuario.</span><span class="sxs-lookup"><span data-stu-id="b46c0-288">**Delegate** – The task has been assigned to another user.</span></span>
    - <span data-ttu-id="b46c0-289">**Remitir a una instancia superior**: el usuario asignado no ha completado la tarea en el tiempo previsto.</span><span class="sxs-lookup"><span data-stu-id="b46c0-289">**Escalate** – The assigned user hasn't completed the task in the allotted time.</span></span>
    - <span data-ttu-id="b46c0-290">**Completar**: el usuario asignado ha completado la tarea.</span><span class="sxs-lookup"><span data-stu-id="b46c0-290">**Complete** – The assigned user has completed the task.</span></span>
    - <span data-ttu-id="b46c0-291">**Rechazar**: el usuario asignado ha rechazado el documento enviado.</span><span class="sxs-lookup"><span data-stu-id="b46c0-291">**Reject** – The assigned user has rejected the document that was submitted.</span></span>
    - <span data-ttu-id="b46c0-292">**Solicitar cambio**: el usuario asignado ha solicitado que se realice un cambio en el documento enviado.</span><span class="sxs-lookup"><span data-stu-id="b46c0-292">**Request change** – The assigned user has requested a change to the document that was submitted.</span></span>

3. <span data-ttu-id="b46c0-293">Seleccione la fila correspondiente a uno de los eventos que seleccionó en el paso 2.</span><span class="sxs-lookup"><span data-stu-id="b46c0-293">Select the row for an event that you selected in step 2.</span></span>
4. <span data-ttu-id="b46c0-294">En la pestaña **Texto de notificación**, en el cuadro de texto, escriba el texto de la notificación.</span><span class="sxs-lookup"><span data-stu-id="b46c0-294">On the **Notification text** tab, in the text box, enter the text of the notification.</span></span>
5. <span data-ttu-id="b46c0-295">Para personalizar la notificación, puede insertar marcadores de posición.</span><span class="sxs-lookup"><span data-stu-id="b46c0-295">To personalize the notification, you can insert placeholders.</span></span> <span data-ttu-id="b46c0-296">Estos se reemplazan con la información adecuada cuando se muestra la notificación a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="b46c0-296">Placeholders are replaced with appropriate information when the notification is shown to users.</span></span> <span data-ttu-id="b46c0-297">Para insertar un marcador de posición, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="b46c0-297">Follow these steps to insert a placeholder:</span></span>

    1. <span data-ttu-id="b46c0-298">En el cuadro de texto, gaga clic para especificar dónde debe aparecer el marcador de posición.</span><span class="sxs-lookup"><span data-stu-id="b46c0-298">In the text box, click where the placeholder should appear.</span></span>
    2. <span data-ttu-id="b46c0-299">Haga clic en **Insertar marcador de posición**.</span><span class="sxs-lookup"><span data-stu-id="b46c0-299">Click **Insert placeholder**.</span></span>
    3. <span data-ttu-id="b46c0-300">En la lista que aparece, seleccione el marcador de posición que desea insertar.</span><span class="sxs-lookup"><span data-stu-id="b46c0-300">In the list that appears, select the placeholder to insert.</span></span>
    4. <span data-ttu-id="b46c0-301">Haga clic en **Insertar**.</span><span class="sxs-lookup"><span data-stu-id="b46c0-301">Click **Insert**.</span></span>

6. <span data-ttu-id="b46c0-302">Para agregar traducciones de la notificación, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="b46c0-302">To add translations of the notification, follow these steps:</span></span>

    1. <span data-ttu-id="b46c0-303">Haga clic en **Traducciones**.</span><span class="sxs-lookup"><span data-stu-id="b46c0-303">Click **Translations**.</span></span>
    2. <span data-ttu-id="b46c0-304">En la página que aparece, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="b46c0-304">On the page that appears, click **Add**.</span></span>
    3. <span data-ttu-id="b46c0-305">En la lista que aparece, seleccione el idioma en el que escribe el texto.</span><span class="sxs-lookup"><span data-stu-id="b46c0-305">In the list that appears, select the language that you're entering the text in.</span></span>
    4. <span data-ttu-id="b46c0-306">En el campo **Texto traducido**, escriba el texto.</span><span class="sxs-lookup"><span data-stu-id="b46c0-306">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="b46c0-307">Para personalizar el texto, puede insertar marcadores de posición como se describe en el paso 5.</span><span class="sxs-lookup"><span data-stu-id="b46c0-307">To personalize the text, you can insert placeholders as described in step 5.</span></span>
    6. <span data-ttu-id="b46c0-308">Haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="b46c0-308">Click **Close**.</span></span>

7. <span data-ttu-id="b46c0-309">En la pestaña **Destinatario**, especifique a quién se envían las notificaciones.</span><span class="sxs-lookup"><span data-stu-id="b46c0-309">On the **Recipient** tab, specify who the notifications are sent to.</span></span> <span data-ttu-id="b46c0-310">Seleccione una de las opciones de la siguiente tabla y, a continuación, siga los pasos adicionales correspondientes a esa opción antes de realizar el paso 8.</span><span class="sxs-lookup"><span data-stu-id="b46c0-310">Select one of the options in the following table, and then follow the additional steps for that option before you go to step 8.</span></span>

    <table>
    <thead>
    <tr>
    <th><span data-ttu-id="b46c0-311">Opción</span><span class="sxs-lookup"><span data-stu-id="b46c0-311">Option</span></span></th>
    <th><span data-ttu-id="b46c0-312">Destinatarios de las notificaciones</span><span class="sxs-lookup"><span data-stu-id="b46c0-312">Notification recipients</span></span></th>
    <th><span data-ttu-id="b46c0-313">Pasos adicionales</span><span class="sxs-lookup"><span data-stu-id="b46c0-313">Additional steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td><span data-ttu-id="b46c0-314">Participante</span><span class="sxs-lookup"><span data-stu-id="b46c0-314">Participant</span></span></td>
    <td><span data-ttu-id="b46c0-315">Usuarios asignados a un grupo o rol específicos</span><span class="sxs-lookup"><span data-stu-id="b46c0-315">Users who are assigned to a specific group or role</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="b46c0-316">Tras seleccionar <strong>Participante</strong>, en la pestaña <strong>Basado en funciones</strong>, en la lista <strong>Tipo de participante</strong>, seleccione el tipo de grupo o rol al que desea enviar las notificaciones.</span><span class="sxs-lookup"><span data-stu-id="b46c0-316">After you select <strong>Participant</strong>, on the <strong>Role based</strong> tab, in the <strong>Type of participant</strong> list, select the type of group or role to send notifications to.</span></span></li>
    <li><span data-ttu-id="b46c0-317">En la lista <strong>Participante</strong>, seleccione el grupo o rol al que se deben enviar las notificaciones.</span><span class="sxs-lookup"><span data-stu-id="b46c0-317">In the <strong>Participant</strong> list, select the group or role to send notifications to.</span></span></li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="b46c0-318">Usuario del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="b46c0-318">Workflow user</span></span></td>
    <td><span data-ttu-id="b46c0-319">Usuarios del flujo de trabajo actual</span><span class="sxs-lookup"><span data-stu-id="b46c0-319">Users in the current workflow</span></span></td>
    <td>
    <ul>
    <li><span data-ttu-id="b46c0-320">Tras seleccionar <strong>Usuario del flujo de trabajo</strong>, en la pestaña <strong>Usuario del flujo de trabajo</strong>, en la pestaña <strong>Usuario del flujo de trabajo</strong>, seleccione un usuario que participe en el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="b46c0-320">After you select <strong>Workflow user</strong>, on the <strong>Workflow user</strong> tab, in the <strong>Workflow user</strong> list, select a user who participates in the workflow.</span></span></li>
    </ul>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="b46c0-321">Usuario</span><span class="sxs-lookup"><span data-stu-id="b46c0-321">User</span></span></td>
    <td><span data-ttu-id="b46c0-322">Usuarios concretos</span><span class="sxs-lookup"><span data-stu-id="b46c0-322">Specific users</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="b46c0-323">Tras seleccionar <strong>Usuario</strong>, haga clic en la pestaña <strong>Usuario</strong>.</span><span class="sxs-lookup"><span data-stu-id="b46c0-323">After you select <strong>User</strong>, click the <strong>User</strong> tab.</span></span></li>
    <li><span data-ttu-id="b46c0-324">La lista <strong>Usuarios disponibles</strong> incluye todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="b46c0-324">The <strong>Available users</strong> list includes all users.</span></span> <span data-ttu-id="b46c0-325">Seleccione aquellos a los que desea enviar notificaciones y, a continuación, muévalos a la lista <strong>Usuarios seleccionados</strong>.</span><span class="sxs-lookup"><span data-stu-id="b46c0-325">Select the users to send notifications to, and then move those users to the <strong>Selected users</strong> list.</span></span></li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

8. <span data-ttu-id="b46c0-326">Repita los pasos 3 a 7 por cada uno de los eventos que haya seleccionado en el paso 2.</span><span class="sxs-lookup"><span data-stu-id="b46c0-326">Repeat steps 3 through 7 for each event that you selected in step 2.</span></span>

## <a name="set-a-time-limit"></a><span data-ttu-id="b46c0-327">Definición de un límite de tiempo</span><span class="sxs-lookup"><span data-stu-id="b46c0-327">Set a time limit</span></span>

<span data-ttu-id="b46c0-328">Siga estos pasos si la tarea manual se debe completar en un plazo específico.</span><span class="sxs-lookup"><span data-stu-id="b46c0-328">Follow these steps if the manual task must be completed in a specific time.</span></span>

> [!NOTE]
> <span data-ttu-id="b46c0-329">Las opciones que seleccione en este procedimiento anulan las opciones elegidas en las áreas **Asignación** y **Remisión** a una instancia superior de la página.</span><span class="sxs-lookup"><span data-stu-id="b46c0-329">The options that you select in this procedure override the options that you selected in the **Assignment** and **Escalation** areas of the page.</span></span>

1. <span data-ttu-id="b46c0-330">En el panel izquiero, haga clic en **Configuración avanzada**.</span><span class="sxs-lookup"><span data-stu-id="b46c0-330">In the left pane, click **Advanced settings**.</span></span>
2. <span data-ttu-id="b46c0-331">Active la casilla **Configurar un límite de tiempo para el elemento de flujo de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="b46c0-331">Select the **Set a time limit for the workflow element** check box.</span></span>
3. <span data-ttu-id="b46c0-332">En el campo **Duración**, especifique cuándo se debe completar la tarea.</span><span class="sxs-lookup"><span data-stu-id="b46c0-332">In the **Duration** field, specify when the task must be completed.</span></span> <span data-ttu-id="b46c0-333">Seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="b46c0-333">Select one of the following options:</span></span>

    - <span data-ttu-id="b46c0-334">**Horas**: escriba la cantidad de horas disponibles para completar la tarea.</span><span class="sxs-lookup"><span data-stu-id="b46c0-334">**Hours** – Enter the number of hours that the task must be completed in.</span></span> <span data-ttu-id="b46c0-335">A continuación, seleccione el calendario que usa la organización y escriba la información pertinente acerca de la semana laboral de la organización.</span><span class="sxs-lookup"><span data-stu-id="b46c0-335">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="b46c0-336">**Días**: escriba la cantidad de días disponibles para completar la tarea.</span><span class="sxs-lookup"><span data-stu-id="b46c0-336">**Days** – Enter the number of days that the task must be completed in.</span></span> <span data-ttu-id="b46c0-337">A continuación, seleccione el calendario que usa la organización y escriba la información pertinente acerca de la semana laboral de la organización.</span><span class="sxs-lookup"><span data-stu-id="b46c0-337">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="b46c0-338">**Semanas**: escriba la cantidad de semanas en las que se debe completar la tarea.</span><span class="sxs-lookup"><span data-stu-id="b46c0-338">**Weeks** – Enter the number of weeks that the task must be completed in.</span></span>
    - <span data-ttu-id="b46c0-339">**Meses**: seleccione el día y la semana en los que vence el plazo para completar la tarea.</span><span class="sxs-lookup"><span data-stu-id="b46c0-339">**Months** – Select the day and week that the task must be completed by.</span></span> <span data-ttu-id="b46c0-340">Por ejemplo, tal vez desee que la tarea se haya completado antes del viernes de la tercera semana del mes.</span><span class="sxs-lookup"><span data-stu-id="b46c0-340">For example, you might want the task to be completed by Friday of the third week of the month.</span></span>
    - <span data-ttu-id="b46c0-341">**Años**: seleccione el día, la semana y el mes en los que vence el plazo para completar la tarea.</span><span class="sxs-lookup"><span data-stu-id="b46c0-341">**Years** – Select the day, week, and month that the task must be completed by.</span></span> <span data-ttu-id="b46c0-342">Por ejemplo, tal vez desee que la tarea se haya completado antes del viernes de la tercera semana de diciembre.</span><span class="sxs-lookup"><span data-stu-id="b46c0-342">For example, you might want the task to be completed by Friday of the third week of December.</span></span>

4. <span data-ttu-id="b46c0-343">Si se supera el límite de tiempo, el sistema realiza una acción en la tarea.</span><span class="sxs-lookup"><span data-stu-id="b46c0-343">If the time limit is exceeded, the system takes action on the task.</span></span> <span data-ttu-id="b46c0-344">En la lista **Acción**, seleccione la acción que debe realizar el sistema.</span><span class="sxs-lookup"><span data-stu-id="b46c0-344">In the **Action** list, select the action that the system should take.</span></span>

## <a name="specify-which-actions-are-available-to-the-user"></a><span data-ttu-id="b46c0-345">Especificación de las acciones de las que dispone el usuario</span><span class="sxs-lookup"><span data-stu-id="b46c0-345">Specify which actions are available to the user</span></span>

<span data-ttu-id="b46c0-346">Cuando la tarea manual se asigna a un usuario, este debe realizar alguna acción en ella.</span><span class="sxs-lookup"><span data-stu-id="b46c0-346">When the manual task is assigned to a user, the user must take action on the task.</span></span> <span data-ttu-id="b46c0-347">Siga estos pasos para especificar las acciones que el usuario puede realizar en la tarea.</span><span class="sxs-lookup"><span data-stu-id="b46c0-347">Follow these steps to specify which actions the user can take on the task.</span></span>

> [!NOTE]
> <span data-ttu-id="b46c0-348">Las acciones disponibles variarán en función del diseño de la tarea.</span><span class="sxs-lookup"><span data-stu-id="b46c0-348">The actions that are available vary, depending on the design of the task.</span></span>

1. <span data-ttu-id="b46c0-349">En el panel izquiero, haga clic en **Configuración avanzada**.</span><span class="sxs-lookup"><span data-stu-id="b46c0-349">In the left pane, click **Advanced settings**.</span></span>
2. <span data-ttu-id="b46c0-350">Active la casilla de verificación **Completar** si el usuario debe poder cambiar el estado de la tarea a **Completo**.</span><span class="sxs-lookup"><span data-stu-id="b46c0-350">Select the **Complete** check box if the user should be able to mark the task as **Complete**.</span></span>
3. <span data-ttu-id="b46c0-351">Active la casilla de verificación **Rechazar** si el usuario debe poder rechazar el documento enviado.</span><span class="sxs-lookup"><span data-stu-id="b46c0-351">Select the **Reject** check box if the user should be able to reject the document that was submitted.</span></span>
4. <span data-ttu-id="b46c0-352">Active la casilla de verificación **Solicitar cambio** si el usuario debe poder solicitar que se realicen cambios en el documento enviado.</span><span class="sxs-lookup"><span data-stu-id="b46c0-352">Select the **Request change** check box if the user should be able to request changes to the document that was submitted.</span></span>
5. <span data-ttu-id="b46c0-353">Active la casilla de verificación **Delegar** si el usuario debe poder asignar la tarea a otro usuario.</span><span class="sxs-lookup"><span data-stu-id="b46c0-353">Select the **Delegate** check box if the user should be able to assign the task to another user.</span></span>
6. <span data-ttu-id="b46c0-354">Active la casilla de verificación **Volver a asignar** si el usuario debe poder reasignar la tarea a otro usuario de la cola de elementos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="b46c0-354">Select the **Reassign** check box if the user should be able to reassign the task to another user in the work item queue.</span></span>
7. <span data-ttu-id="b46c0-355">Active la casilla de verificación **Liberar** si el usuario debe poder reasignar la tarea a la cola de elementos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="b46c0-355">Select the **Release** check box if the user should be able to reassign the task to the work item queue.</span></span> <span data-ttu-id="b46c0-356">Otro usuario podrá encargarse de completar la tarea.</span><span class="sxs-lookup"><span data-stu-id="b46c0-356">Another user can then complete the task.</span></span>
