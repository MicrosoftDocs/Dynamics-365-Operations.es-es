---
title: Configurar los pasos de aprobación en un flujo de trabajo
description: Este tema explica cómo configurar las propiedades de un paso de aprobación.
author: ChrisGarty
manager: AnnBe
ms.date: 08/23/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 192161
ms.assetid: 8b478e3d-d6b4-403b-aae0-f639a71ca36c
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 71d51f137cc0e0fcc18b39f8b92ab5c44b359609
ms.sourcegitcommit: f5e31c34640add6d40308ac1365cc0ee60e60e24
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/08/2020
ms.locfileid: "4694085"
---
# <a name="configure-approval-steps-in-a-workflow"></a><span data-ttu-id="f23d0-103">Configurar los pasos de aprobación en un flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="f23d0-103">Configure approval steps in a workflow</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f23d0-104">Este tema explica cómo configurar las propiedades de un paso de aprobación.</span><span class="sxs-lookup"><span data-stu-id="f23d0-104">This topic explains how to configure the properties of an approval step.</span></span>

<span data-ttu-id="f23d0-105">Para configurar un paso de aprobación en el editor de flujo de trabajo, haga clic con el botón secundario en el paso de aprobación y, a continuación, haga clic en **Propiedades** para abrir la página **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="f23d0-105">To configure an approval step in the workflow editor, right-click the approval step, and then click **Properties** to open the **Properties** page.</span></span> <span data-ttu-id="f23d0-106">A continuación, use los siguientes procedimientos para configurar las propiedades del paso de aprobación.</span><span class="sxs-lookup"><span data-stu-id="f23d0-106">Then use the following procedures to configure the properties of the approval step.</span></span>

## <a name="name-the-step"></a><span data-ttu-id="f23d0-107">Asignación de un nombre al paso</span><span class="sxs-lookup"><span data-stu-id="f23d0-107">Name the step</span></span>
<span data-ttu-id="f23d0-108">Siga estos pasos para asignar un nombre al paso de aprobación.</span><span class="sxs-lookup"><span data-stu-id="f23d0-108">Follow these steps to enter a name for the approval step.</span></span>

1. <span data-ttu-id="f23d0-109">En el panel izquierdo, haga clic en **Configuración básica**.</span><span class="sxs-lookup"><span data-stu-id="f23d0-109">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="f23d0-110">En el campo **Nombre**, especifique un nombre único para la etapa de aprobación.</span><span class="sxs-lookup"><span data-stu-id="f23d0-110">In the **Name** field, enter a unique name for the approval step.</span></span>

## <a name="enter-a-subject-line-and-instructions"></a><span data-ttu-id="f23d0-111">Especificación de una línea de asunto e instrucciones</span><span class="sxs-lookup"><span data-stu-id="f23d0-111">Enter a subject line and instructions</span></span>

<span data-ttu-id="f23d0-112">Debe proporcionar una línea de asunto e instrucciones a los usuarios que están asignados al paso de aprobación.</span><span class="sxs-lookup"><span data-stu-id="f23d0-112">You must provide a subject line and instructions to users who are assigned to the approval step.</span></span> <span data-ttu-id="f23d0-113">Por ejemplo, si configura un paso de aprobación para solicitudes de compra, el usuario asignado a él ve la línea de asunto y las instrucciones en la página **Solicitudes de compra**.</span><span class="sxs-lookup"><span data-stu-id="f23d0-113">For example, if you're configuring an approval step for purchase requisitions, the user who is assigned to the step sees the subject line and instructions on the **Purchase requisitions** page.</span></span> <span data-ttu-id="f23d0-114">La línea de asunto se muestra en una barra de mensajes de la página.</span><span class="sxs-lookup"><span data-stu-id="f23d0-114">The subject line appears in a message bar on the page.</span></span> <span data-ttu-id="f23d0-115">A continuación, el usuario puede hacer clic en el icono de dicha barra para ver las instrucciones.</span><span class="sxs-lookup"><span data-stu-id="f23d0-115">The user can then click the icon in the message bar to see the instructions.</span></span> <span data-ttu-id="f23d0-116">Siga estos pasos para escribir una línea de asunto e instrucciones.</span><span class="sxs-lookup"><span data-stu-id="f23d0-116">Follow these steps to enter a subject line and instructions.</span></span>

1. <span data-ttu-id="f23d0-117">En el panel izquierdo, haga clic en **Configuración básica**.</span><span class="sxs-lookup"><span data-stu-id="f23d0-117">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="f23d0-118">En el campo **Asunto del elemento de trabajo**, escriba la línea de asunto.</span><span class="sxs-lookup"><span data-stu-id="f23d0-118">In the **Work item subject** field, enter the subject line.</span></span>
3. <span data-ttu-id="f23d0-119">Para personalizar la línea de asunto, puede insertar marcadores de posición.</span><span class="sxs-lookup"><span data-stu-id="f23d0-119">To personalize the subject line, you can insert placeholders.</span></span> <span data-ttu-id="f23d0-120">Estos se reemplazan con los datos adecuados cuando se muestra la línea de asunto a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="f23d0-120">Placeholders are replaced with appropriate data when the subject line is shown to users.</span></span> <span data-ttu-id="f23d0-121">Para insertar un marcador de posición, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="f23d0-121">Follow these steps to insert a placeholder:</span></span>

    1. <span data-ttu-id="f23d0-122">En el cuadro de texto, gaga clic para especificar dónde debe aparecer el marcador de posición.</span><span class="sxs-lookup"><span data-stu-id="f23d0-122">In the text box, click where the placeholder should appear.</span></span>
    2. <span data-ttu-id="f23d0-123">Haga clic en **Insertar marcador de posición**.</span><span class="sxs-lookup"><span data-stu-id="f23d0-123">Click **Insert placeholder**.</span></span>
    3. <span data-ttu-id="f23d0-124">En la lista que aparece, seleccione el marcador de posición que desea insertar.</span><span class="sxs-lookup"><span data-stu-id="f23d0-124">In the list that appears, select the placeholder to insert.</span></span>
    4. <span data-ttu-id="f23d0-125">Haga clic en **Insertar**.</span><span class="sxs-lookup"><span data-stu-id="f23d0-125">Click **Insert**.</span></span>

4. <span data-ttu-id="f23d0-126">Para agregar traducciones de la línea de asunto, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="f23d0-126">To add translations of the subject line, follow these steps:</span></span>

    1. <span data-ttu-id="f23d0-127">Haga clic en **Traducciones**.</span><span class="sxs-lookup"><span data-stu-id="f23d0-127">Click **Translations**.</span></span>
    2. <span data-ttu-id="f23d0-128">En la página que aparece, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="f23d0-128">On the page that appears, click **Add**.</span></span>
    3. <span data-ttu-id="f23d0-129">En la lista que aparece, seleccione el idioma en el que escribe el texto.</span><span class="sxs-lookup"><span data-stu-id="f23d0-129">In the list that appears, select the language that you're entering the text in.</span></span>
    4. <span data-ttu-id="f23d0-130">En el campo **Texto traducido**, escriba el texto.</span><span class="sxs-lookup"><span data-stu-id="f23d0-130">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="f23d0-131">Para personalizar el texto, puede insertar marcadores de posición como se describe en el paso 3.</span><span class="sxs-lookup"><span data-stu-id="f23d0-131">To personalize the text, you can insert placeholders as described in step 3.</span></span>
    6. <span data-ttu-id="f23d0-132">Haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="f23d0-132">Click **Close**.</span></span>

5. <span data-ttu-id="f23d0-133">En el campo **Instrucciones del elemento de trabajo**, escriba las instrucciones.</span><span class="sxs-lookup"><span data-stu-id="f23d0-133">In the **Work item instructions** field, enter the instructions.</span></span>
6. <span data-ttu-id="f23d0-134">Para personalizar las instrucciones, puede insertar marcadores de posición.</span><span class="sxs-lookup"><span data-stu-id="f23d0-134">To personalize the instructions, you can insert placeholders.</span></span> <span data-ttu-id="f23d0-135">Estos se reemplazan con los datos adecuados cuando las instrucciones se muestran a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="f23d0-135">Placeholders are replaced with appropriate data when the instructions are shown to users.</span></span> <span data-ttu-id="f23d0-136">Para insertar un marcador de posición, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="f23d0-136">Follow these steps to insert a placeholder:</span></span>

    1. <span data-ttu-id="f23d0-137">En el cuadro de texto, gaga clic para especificar dónde debe aparecer el marcador de posición.</span><span class="sxs-lookup"><span data-stu-id="f23d0-137">In the text box, click where the placeholder should appear.</span></span>
    2. <span data-ttu-id="f23d0-138">Haga clic en **Insertar marcador de posición**.</span><span class="sxs-lookup"><span data-stu-id="f23d0-138">Click **Insert placeholder**.</span></span>
    3. <span data-ttu-id="f23d0-139">En la lista que aparece, seleccione el marcador de posición que desea insertar.</span><span class="sxs-lookup"><span data-stu-id="f23d0-139">In the list that appears, select the placeholder to insert.</span></span>
    4. <span data-ttu-id="f23d0-140">Haga clic en **Insertar**.</span><span class="sxs-lookup"><span data-stu-id="f23d0-140">Click **Insert**.</span></span>

7. <span data-ttu-id="f23d0-141">Para agregar traducciones de las instrucciones, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="f23d0-141">To add translations of the instructions, follow these steps:</span></span>

    1. <span data-ttu-id="f23d0-142">Haga clic en **Traducciones**.</span><span class="sxs-lookup"><span data-stu-id="f23d0-142">Click **Translations**.</span></span>
    2. <span data-ttu-id="f23d0-143">En la página que aparece, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="f23d0-143">On the page that appears, click **Add**.</span></span>
    3. <span data-ttu-id="f23d0-144">En la lista que aparece, seleccione el idioma en el que escribe el texto.</span><span class="sxs-lookup"><span data-stu-id="f23d0-144">In the list that appears, select the language that you're entering the text in.</span></span>
    4. <span data-ttu-id="f23d0-145">En el campo **Texto traducido**, escriba el texto.</span><span class="sxs-lookup"><span data-stu-id="f23d0-145">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="f23d0-146">Para personalizar el texto, puede insertar marcadores de posición como se describe en el paso 6.</span><span class="sxs-lookup"><span data-stu-id="f23d0-146">To personalize the text, you can insert placeholders as described in step 6.</span></span>
    6. <span data-ttu-id="f23d0-147">Haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="f23d0-147">Click **Close**.</span></span>

## <a name="assign-the-approval-step"></a><span data-ttu-id="f23d0-148">Asignación del paso de aprobación</span><span class="sxs-lookup"><span data-stu-id="f23d0-148">Assign the approval step</span></span>

<span data-ttu-id="f23d0-149">Siga estos pasos para especificar a quién se debe asignar el paso de aprobación.</span><span class="sxs-lookup"><span data-stu-id="f23d0-149">Follow these steps to specify who the approval step should be assigned to.</span></span>

1. <span data-ttu-id="f23d0-150">En el panel izquierdo, haga clic en **Asignación**.</span><span class="sxs-lookup"><span data-stu-id="f23d0-150">In the left pane, click **Assignment**.</span></span>
2. <span data-ttu-id="f23d0-151">En la pestaña **Tipo de asignación**, seleccione una de las opciones de la siguiente tabla. A continuación, siga los pasos adicionales correspondientes a la opción elegida antes de realizar el paso 3.</span><span class="sxs-lookup"><span data-stu-id="f23d0-151">On the **Assignment type** tab, select one of the options in the following table, and then follow the additional steps for that option before you go to step 3.</span></span>

    <table>
    <thead>
    <tr>
    <th><span data-ttu-id="f23d0-152">Opción</span><span class="sxs-lookup"><span data-stu-id="f23d0-152">Option</span></span></th>
    <th><span data-ttu-id="f23d0-153">Los usuarios a los que está asignado el paso de aprobación</span><span class="sxs-lookup"><span data-stu-id="f23d0-153">Users that the approval step is assigned to</span></span></th>
    <th><span data-ttu-id="f23d0-154">Pasos adicionales</span><span class="sxs-lookup"><span data-stu-id="f23d0-154">Additional steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td><span data-ttu-id="f23d0-155">Participante</span><span class="sxs-lookup"><span data-stu-id="f23d0-155">Participant</span></span></td>
    <td><span data-ttu-id="f23d0-156">Usuarios asignados a un grupo o rol específicos</span><span class="sxs-lookup"><span data-stu-id="f23d0-156">Users who are assigned to a specific group or role</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="f23d0-157">Tras seleccionar <strong>Participante</strong>, en la pestaña <strong>Basado en funciones</strong>, en la lista <strong>Tipo de participante</strong>, seleccione el tipo de grupo o rol al que desea asignar el paso.</span><span class="sxs-lookup"><span data-stu-id="f23d0-157">After you select <strong>Participant</strong>, on the <strong>Role based</strong> tab, in the <strong>Type of participant</strong> list, select the type of group or role to assign the step to.</span></span></li>
    <li><span data-ttu-id="f23d0-158">En la lista <strong>Participante</strong>, seleccione el grupo o rol al que se debe asignar el paso.</span><span class="sxs-lookup"><span data-stu-id="f23d0-158">In the <strong>Participant</strong> list, select the group or role to assign the step to.</span></span></li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="f23d0-159">Jerarquía</span><span class="sxs-lookup"><span data-stu-id="f23d0-159">Hierarchy</span></span></td>
    <td><span data-ttu-id="f23d0-160">Usuarios de una jerarquía organizativa específica</span><span class="sxs-lookup"><span data-stu-id="f23d0-160">Users in a specific organizational hierarchy</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="f23d0-161">Tras seleccionar <strong>Jerarquía</strong>, en la pestaña <strong>Selección de jerarquía</strong>, en la lista <strong>Tipo de jerarquía</strong>, seleccione el tipo de jerarquía al que desea asignar el paso.</span><span class="sxs-lookup"><span data-stu-id="f23d0-161">After you select <strong>Hierarchy</strong>, on the <strong>Hierarchy selection</strong> tab, in the <strong>Hierarchy type</strong> list, select the type of hierarchy to assign the step to.</span></span></li>
    <li><span data-ttu-id="f23d0-162">El sistema debe recuperar un intervalo de nombres de usuario de la jerarquía.</span><span class="sxs-lookup"><span data-stu-id="f23d0-162">The system must retrieve a range of user names from the hierarchy.</span></span> <span data-ttu-id="f23d0-163">Dichos nombres representan a los usuarios a los que se puede asignar el paso.</span><span class="sxs-lookup"><span data-stu-id="f23d0-163">These names represent users that the step can be assigned to.</span></span> <span data-ttu-id="f23d0-164">Siga estos pasos para especificar el punto de inicio y de finalización del intervalo de nombres de usuario que el sistema recupera:</span><span class="sxs-lookup"><span data-stu-id="f23d0-164">Follow these steps to specify the starting point and ending point of the range of user names that the system retrieves:</span></span> <ol>
    <li><span data-ttu-id="f23d0-165">Para especificar el punto de inicio, seleccione una persona en la lista <strong>Comenzar desde</strong>.</span><span class="sxs-lookup"><span data-stu-id="f23d0-165">To specify the starting point, select a person in the <strong>Start from</strong> list.</span></span></li>
    <li><span data-ttu-id="f23d0-166">Para especificar el punto de finalización, haga clic en <strong>Agregar condición</strong>.</span><span class="sxs-lookup"><span data-stu-id="f23d0-166">To specify the ending point, click <strong>Add condition</strong>.</span></span> <span data-ttu-id="f23d0-167">A continuación, especifique una condición que determine en qué parte de la jerarquía el sistema dejará de recuperar nombres.</span><span class="sxs-lookup"><span data-stu-id="f23d0-167">Then enter a condition that determines where in the hierarchy the system stops retrieving names.</span></span></li>
    </ol>
    </li>
    <li><span data-ttu-id="f23d0-168">En la pestaña <strong>Opciones de jerarquía</strong>, especifique a qué usuarios del intervalo se debe asignar el paso:</span><span class="sxs-lookup"><span data-stu-id="f23d0-168">On the <strong>Hierarchy options</strong> tab, specify which users in the range the step should be assigned to:</span></span> <ul>
    <li><span data-ttu-id="f23d0-169"><strong>Asignar a todos los usuarios recuperados</strong>: el paso se asigna a todos los usuarios del intervalo.</span><span class="sxs-lookup"><span data-stu-id="f23d0-169"><strong>Assign to all users retrieved</strong> – The step is assigned to all users in the range.</span></span></li>
    <li><span data-ttu-id="f23d0-170"><strong>Asignar sólo al último usuario recuperado</strong>: el paso se asigna únicamente al último usuario del intervalo.</span><span class="sxs-lookup"><span data-stu-id="f23d0-170"><strong>Assign only to last user retrieved</strong> – The step is assigned to only the last user in the range.</span></span></li>
    <li><span data-ttu-id="f23d0-171"><strong>Excluir usuarios con la siguiente condición</strong>: el paso no se asigna a ninguno de los usuarios del intervalo que cumplen con una condición determinada.</span><span class="sxs-lookup"><span data-stu-id="f23d0-171"><strong>Exclude users with the following condition</strong> – The step isn't assigned to any users in the range who meet a specific condition.</span></span> <span data-ttu-id="f23d0-172">Haga clic en <strong>Agregar condición</strong> para especificar la condición.</span><span class="sxs-lookup"><span data-stu-id="f23d0-172">Click <strong>Add condition</strong> to specify the condition.</span></span></li>
    </ul>
    </li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="f23d0-173">Usuario del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="f23d0-173">Workflow user</span></span></td>
    <td><span data-ttu-id="f23d0-174">Usuarios del flujo de trabajo actual</span><span class="sxs-lookup"><span data-stu-id="f23d0-174">Users in the current workflow</span></span></td>
    <td>
    <ul>
    <li><span data-ttu-id="f23d0-175">Tras seleccionar <strong>Usuario del flujo de trabajo</strong>, en la pestaña <strong>Usuario del flujo de trabajo</strong>, en la pestaña <strong>Usuario del flujo de trabajo</strong>, seleccione un usuario que participe en el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="f23d0-175">After you select <strong>Workflow user</strong>, on the <strong>Workflow user</strong> tab, in the <strong>Workflow user</strong> list, select a user who participates in the workflow.</span></span></li>
    </ul>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="f23d0-176">Usuario</span><span class="sxs-lookup"><span data-stu-id="f23d0-176">User</span></span></td>
    <td><span data-ttu-id="f23d0-177">Usuarios concretos</span><span class="sxs-lookup"><span data-stu-id="f23d0-177">Specific users</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="f23d0-178">Tras seleccionar <strong>Usuario</strong>, haga clic en la pestaña <strong>Usuario</strong>.</span><span class="sxs-lookup"><span data-stu-id="f23d0-178">After you select <strong>User</strong>, click the <strong>User</strong> tab.</span></span></li>
    <li><span data-ttu-id="f23d0-179">La lista <strong>Usuarios disponibles</strong> incluye todos los usuarios del sistema.</span><span class="sxs-lookup"><span data-stu-id="f23d0-179">The <strong>Available users</strong> list includes all system users.</span></span> <span data-ttu-id="f23d0-180">Seleccione aquellos a los que desea asignar el paso y, a continuación, muévalos a la lista <strong>Usuarios seleccionados</strong>.</span><span class="sxs-lookup"><span data-stu-id="f23d0-180">Select the users to assign the step to, and then move those users to the <strong>Selected users</strong> list.</span></span></li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

3. <span data-ttu-id="f23d0-181">En la pestaña **Límite de tiempo**, en el campo **Duración**, especifique el tiempo del que dispone el usuario para realizar alguna acción en los documentos que llegan al paso de aprobación o, dicho de otro modo, para responder a ellos.</span><span class="sxs-lookup"><span data-stu-id="f23d0-181">On the **Time limit** tab, in the **Duration** field, specify how much time the user has to take action on, or respond to, documents that reach the approval step.</span></span> <span data-ttu-id="f23d0-182">Seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="f23d0-182">Select one of the following options:</span></span>

    - <span data-ttu-id="f23d0-183">**Horas**: escriba la cantidad de horas de las que dispone el usuario para responder.</span><span class="sxs-lookup"><span data-stu-id="f23d0-183">**Hours** – Enter the number of hours that the user has to respond.</span></span> <span data-ttu-id="f23d0-184">A continuación, seleccione el calendario que usa la organización y escriba la información pertinente acerca de la semana laboral de la organización.</span><span class="sxs-lookup"><span data-stu-id="f23d0-184">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="f23d0-185">**Días**: escriba la cantidad de días de los que dispone el usuario para responder.</span><span class="sxs-lookup"><span data-stu-id="f23d0-185">**Days** – Enter the number of days that the user has to respond.</span></span> <span data-ttu-id="f23d0-186">A continuación, seleccione el calendario que usa la organización y escriba la información pertinente acerca de la semana laboral de la organización.</span><span class="sxs-lookup"><span data-stu-id="f23d0-186">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="f23d0-187">**Semanas**: escriba la cantidad de semanas de las que dispone el usuario para responder.</span><span class="sxs-lookup"><span data-stu-id="f23d0-187">**Weeks** – Enter the number of weeks that the user has to respond.</span></span>
    - <span data-ttu-id="f23d0-188">**Meses**: seleccione el día y la semana en los que vence el plazo para responder.</span><span class="sxs-lookup"><span data-stu-id="f23d0-188">**Months** – Select the day and week that the user must respond by.</span></span> <span data-ttu-id="f23d0-189">Por ejemplo, tal vez desee que el usuario haya respondido antes del viernes de la tercera semana del mes.</span><span class="sxs-lookup"><span data-stu-id="f23d0-189">For example, you might want the user to respond by Friday of the third week of the month.</span></span>
    - <span data-ttu-id="f23d0-190">**Años**: seleccione el día, la semana y el mes en los que vence el plazo para responder.</span><span class="sxs-lookup"><span data-stu-id="f23d0-190">**Years** – Select the day, week, and month that the user must respond by.</span></span> <span data-ttu-id="f23d0-191">Por ejemplo, tal vez desee que el usuario haya respondido antes del viernes de la tercera semana de diciembre.</span><span class="sxs-lookup"><span data-stu-id="f23d0-191">For example, you might want the user to respond by Friday of the third week of December.</span></span>

    <span data-ttu-id="f23d0-192">Si el usuario no realiza ninguna acción en el documento en el tiempo asignado, el documento se considera vencido.</span><span class="sxs-lookup"><span data-stu-id="f23d0-192">If the user doesn't take action on the document in the allotted time, the document is overdue.</span></span> <span data-ttu-id="f23d0-193">Los documentos vencidos se remiten a una instancia superior en función de las opciones que se seleccionen en el área **Remisión a una instancia superior** de la página.</span><span class="sxs-lookup"><span data-stu-id="f23d0-193">A document that is overdue is escalated, based on the options that you select in the **Escalation** area of the page.</span></span>

4. <span data-ttu-id="f23d0-194">Si asignó el paso de aprobación a varios usuarios o a un grupo de usuarios, en la pestaña **Directiva de finalización**, seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="f23d0-194">If you assigned the approval step to multiple users or a group of users, on the **Completion policy** tab, select one of the following options:</span></span>

    - <span data-ttu-id="f23d0-195">**Un único aprobador**: la acción que se aplica al documento la determina la primera persona que responde.</span><span class="sxs-lookup"><span data-stu-id="f23d0-195">**Single approver** – The action that is applied to the document is determined by the first person who responds.</span></span> <span data-ttu-id="f23d0-196">Por ejemplo, supongamos que Sam ha enviado un informe de gastos por un total de 15.000 USD.</span><span class="sxs-lookup"><span data-stu-id="f23d0-196">For example, Sam has submitted an expense report for USD 15,000.</span></span> <span data-ttu-id="f23d0-197">En este momento, el informe de gastos está asignado a Sue, Jo y Bill.</span><span class="sxs-lookup"><span data-stu-id="f23d0-197">The expense report is currently assigned to Sue, Jo, and Bill.</span></span> <span data-ttu-id="f23d0-198">Si Sue es la primera persona que responde al documento, la acción que ella lleva a cabo se aplica al documento.</span><span class="sxs-lookup"><span data-stu-id="f23d0-198">If Sue is the first person who responds to the document, the action that she takes is applied to the document.</span></span> <span data-ttu-id="f23d0-199">Si Sue rechaza el documento, se lo rechaza y se lo vuelve a enviar a Sam.</span><span class="sxs-lookup"><span data-stu-id="f23d0-199">If Sue rejects the document, it's rejected and sent back to Sam.</span></span> <span data-ttu-id="f23d0-200">Si Sue aprueba el documento, se lo envía a Ann para que lo apruebe.</span><span class="sxs-lookup"><span data-stu-id="f23d0-200">If Sue approves the document, it's sent to Ann for approval.</span></span>

        ![Flujo de trabajo que tiene un proceso de aprobación](./media/workflow_multipleusersinstep.gif)

    - <span data-ttu-id="f23d0-202">**Mayoría de aprobadores**: la acción que se aplica al documento se determina cuando responde la mayoría de los aprobadores.</span><span class="sxs-lookup"><span data-stu-id="f23d0-202">**Majority of approvers** – The action that is applied to the document is determined when most of the approvers respond.</span></span> <span data-ttu-id="f23d0-203">Por ejemplo, supongamos que Sam ha enviado un informe de gastos por un total de 15.000 USD.</span><span class="sxs-lookup"><span data-stu-id="f23d0-203">For example, Sam has submitted an expense report for USD 15,000.</span></span> <span data-ttu-id="f23d0-204">En este momento, el informe de gastos está asignado a Sue, Jo y Bill.</span><span class="sxs-lookup"><span data-stu-id="f23d0-204">The expense report is currently assigned to Sue, Jo, and Bill.</span></span> <span data-ttu-id="f23d0-205">Si Sue y Jo son las dos primeras aprobadoras en responder, la acción que ellas llevan a cabo se aplica al documento.</span><span class="sxs-lookup"><span data-stu-id="f23d0-205">If Sue and Jo are the first two approvers who respond, the action that they take is applied to the document.</span></span>

        - <span data-ttu-id="f23d0-206">Si Sue aprueba el documento pero Jo lo rechaza, el documento se rechaza y se vuelve a enviar a Sam.</span><span class="sxs-lookup"><span data-stu-id="f23d0-206">If Sue approves the document, but Jo rejects it, the document is rejected and sent back to Sam.</span></span>
        - <span data-ttu-id="f23d0-207">Si tanto Sue como Jo aprueban el documento, se lo envía a Ann para que lo apruebe.</span><span class="sxs-lookup"><span data-stu-id="f23d0-207">If both Sue and Jo approve the document, it's sent to Ann for approval.</span></span>

    - <span data-ttu-id="f23d0-208">**Porcentaje de aprobadores**: la acción que se aplica al documento se determina cuando responde un porcentaje específico de aprobadores.</span><span class="sxs-lookup"><span data-stu-id="f23d0-208">**Percentage of approvers** – The action that is applied to the document is determined when a specific percentage of the approvers respond.</span></span> <span data-ttu-id="f23d0-209">Por ejemplo, supongamos que Sam ha enviado un informe de gastos por un total de 15.000 USD.</span><span class="sxs-lookup"><span data-stu-id="f23d0-209">For example, Sam has submitted an expense report for USD 15,000.</span></span> <span data-ttu-id="f23d0-210">En este momento, el informe de gastos está asignado a Sue, Jo y Bill, y usted ha establecido el porcentaje en **50**.</span><span class="sxs-lookup"><span data-stu-id="f23d0-210">The expense report is currently assigned to Sue, Jo, and Bill, and you entered **50** as the percentage.</span></span> <span data-ttu-id="f23d0-211">Si Sue y Jo son las dos primeras aprobadoras en responder, la acción que ellas llevan a cabo se aplica al documento porque, entre ambas, alcanzan el 50% de aprobadores que se requiere.</span><span class="sxs-lookup"><span data-stu-id="f23d0-211">If Sue and Jo are the first two approvers who respond, the action that they take is applied to the document, because they meet the requirement for 50 percent of approvers.</span></span>

        - <span data-ttu-id="f23d0-212">Si Sue aprueba el documento pero Jo lo rechaza, el documento se rechaza y se vuelve a enviar a Sam.</span><span class="sxs-lookup"><span data-stu-id="f23d0-212">If Sue approves the document, but Jo rejects it, the document is rejected and sent back to Sam.</span></span>
        - <span data-ttu-id="f23d0-213">Si tanto Sue como Jo aprueban el documento, se lo envía a Ann para que lo apruebe.</span><span class="sxs-lookup"><span data-stu-id="f23d0-213">If both Sue and Jo approve the document, it's sent to Ann for approval.</span></span>

    - <span data-ttu-id="f23d0-214">**Todos los aprobadores**: todos los aprobadores deben aprobar el documento;</span><span class="sxs-lookup"><span data-stu-id="f23d0-214">**All approvers** – All the approvers must approve the document.</span></span> <span data-ttu-id="f23d0-215">de lo contrario, el flujo de trabajo no podrá continuar.</span><span class="sxs-lookup"><span data-stu-id="f23d0-215">Otherwise, the workflow can't continue.</span></span> <span data-ttu-id="f23d0-216">Por ejemplo, supongamos que Sam ha enviado un informe de gastos por un total de 15.000 USD.</span><span class="sxs-lookup"><span data-stu-id="f23d0-216">For example, Sam has submitted an expense report for USD 15,000.</span></span> <span data-ttu-id="f23d0-217">En este momento, el informe de gastos está asignado a Sue, Jo y Bill.</span><span class="sxs-lookup"><span data-stu-id="f23d0-217">The expense report is currently assigned to Sue, Jo, and Bill.</span></span> <span data-ttu-id="f23d0-218">Si Sue y Jo aprueban el documento pero Bill lo rechaza, el documento se rechaza y se vuelve a enviar a Sam.</span><span class="sxs-lookup"><span data-stu-id="f23d0-218">If Sue and Joe approve the document, but Bill rejects it, the document is rejected and sent back to Sam.</span></span> <span data-ttu-id="f23d0-219">Si Sue, Jo y Bill aprueban el documento, se lo envía a Ann para que lo apruebe.</span><span class="sxs-lookup"><span data-stu-id="f23d0-219">If Sue, Jo, and Bill all approve the document, it's sent to Ann for approval.</span></span>

## <a name="specify-when-the-approval-step-is-required"></a><span data-ttu-id="f23d0-220">Especificación de las condiciones en que se requiere el paso de aprobación</span><span class="sxs-lookup"><span data-stu-id="f23d0-220">Specify when the approval step is required</span></span>

<span data-ttu-id="f23d0-221">Puede especificar cuándo se requiere el paso de aprobación.</span><span class="sxs-lookup"><span data-stu-id="f23d0-221">You can specify when the approval step is required.</span></span> <span data-ttu-id="f23d0-222">El paso de aprobación se puede requerir siempre o solo si se cumplen determinadas condiciones.</span><span class="sxs-lookup"><span data-stu-id="f23d0-222">The approval step can always be required, or it can be required only if specific conditions are met.</span></span>

### <a name="the-approval-step-is-always-required"></a><span data-ttu-id="f23d0-223">El paso de aprobación se requiere siempre</span><span class="sxs-lookup"><span data-stu-id="f23d0-223">The approval step is always required</span></span>

<span data-ttu-id="f23d0-224">Siga estos pasos si el paso de aprobación se requiere siempre.</span><span class="sxs-lookup"><span data-stu-id="f23d0-224">Follow these steps if the approval step is always required.</span></span>

1. <span data-ttu-id="f23d0-225">En el panel izquierdo, haga clic en **Condición**.</span><span class="sxs-lookup"><span data-stu-id="f23d0-225">In the left pane, click **Condition**.</span></span>
2. <span data-ttu-id="f23d0-226">Seleccione la opción **Ejecutar siempre este paso**.</span><span class="sxs-lookup"><span data-stu-id="f23d0-226">Select the **Always run this step** option.</span></span>

### <a name="the-approval-step-is-required-in-specific-conditions"></a><span data-ttu-id="f23d0-227">El paso de aprobación se requiere en condiciones específicas</span><span class="sxs-lookup"><span data-stu-id="f23d0-227">The approval step is required in specific conditions</span></span>

<span data-ttu-id="f23d0-228">Es posible que el paso de aprobación que está configurando se requiera solo si se cumplen determinadas condiciones.</span><span class="sxs-lookup"><span data-stu-id="f23d0-228">The approval step that you're configuring might be required only if specific conditions are met.</span></span> <span data-ttu-id="f23d0-229">Por ejemplo, si está configurando un paso de aprobación para un flujo de trabajo de solicitudes de compra, es posible que desee que el paso de aprobación se lleve a cabo solamente cuando el importe de una solicitud de compra sea superior a 10.000 USD.</span><span class="sxs-lookup"><span data-stu-id="f23d0-229">For example, if you're configuring an approval step for a purchase requisition workflow, you might want the approval step to occur only if the amount of the purchase requisition is more than USD 10,000.</span></span> <span data-ttu-id="f23d0-230">Siga estos pasos para especificar cuándo se requiere el paso de aprobación.</span><span class="sxs-lookup"><span data-stu-id="f23d0-230">Follow these steps to specify when the approval step is required.</span></span>

1. <span data-ttu-id="f23d0-231">En el panel izquierdo, haga clic en **Condición**.</span><span class="sxs-lookup"><span data-stu-id="f23d0-231">In the left pane, click **Condition**.</span></span>
2. <span data-ttu-id="f23d0-232">Seleccione la opción **Ejecutar este paso únicamente si se cumplen las condiciones siguientes**.</span><span class="sxs-lookup"><span data-stu-id="f23d0-232">Select the **Run this step only when the following condition is met** option.</span></span>
3. <span data-ttu-id="f23d0-233">Escriba una condición.</span><span class="sxs-lookup"><span data-stu-id="f23d0-233">Enter a condition.</span></span>
4. <span data-ttu-id="f23d0-234">Escriba condiciones adicionales que sean necesarias.</span><span class="sxs-lookup"><span data-stu-id="f23d0-234">Enter any additional conditions that are required.</span></span>
5. <span data-ttu-id="f23d0-235">Para comprobar que las condiciones definidas se hayan configurado correctamente, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="f23d0-235">To verify that the conditions that you entered are configured correctly, follow these steps:</span></span>

    1. <span data-ttu-id="f23d0-236">Haga clic en **Probar**.</span><span class="sxs-lookup"><span data-stu-id="f23d0-236">Click **Test**.</span></span>
    2. <span data-ttu-id="f23d0-237">En la página **Probar condición de flujo de trabajo**, en el área **Comprobar condición**, seleccione un registro.</span><span class="sxs-lookup"><span data-stu-id="f23d0-237">On the **Test workflow condition** page, in the **Validate condition** area, select a record.</span></span>
    3. <span data-ttu-id="f23d0-238">Haga clic en **Probar**.</span><span class="sxs-lookup"><span data-stu-id="f23d0-238">Click **Test**.</span></span> <span data-ttu-id="f23d0-239">El sistema evalúa el registro seleccionado para determinar si reúne las condiciones definidas.</span><span class="sxs-lookup"><span data-stu-id="f23d0-239">The system evaluates the record to determine whether it meets the conditions that you defined.</span></span>
    4. <span data-ttu-id="f23d0-240">Haga clic en **Aceptar** o en **Cancelar** para regresar a la página **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="f23d0-240">Click **OK** or **Cancel** to return to the **Properties** page.</span></span>

## <a name="specify-what-happens-when-the-document-is-overdue"></a><span data-ttu-id="f23d0-241">Especificación de la acción que se realiza cuando vence el documento</span><span class="sxs-lookup"><span data-stu-id="f23d0-241">Specify what happens when the document is overdue</span></span>

<span data-ttu-id="f23d0-242">Si un usuario no realiza ninguna acción en un documento en el tiempo asignado, el documento se considera vencido.</span><span class="sxs-lookup"><span data-stu-id="f23d0-242">If a user doesn't take action on a document in the allotted time, the document is overdue.</span></span> <span data-ttu-id="f23d0-243">Los documentos vencidos se pueden remitir a una instancia superior o asignar a otro usuario de forma automática para que los apruebe.</span><span class="sxs-lookup"><span data-stu-id="f23d0-243">A document that is overdue can be escalated, or automatically assigned to another user for approval.</span></span> <span data-ttu-id="f23d0-244">Si el documento ha vencido, siga estos pasos para remitirlo a una instancia superior.</span><span class="sxs-lookup"><span data-stu-id="f23d0-244">Follow these steps to escalate the document if it's overdue.</span></span>

1. <span data-ttu-id="f23d0-245">En el panel izquierdo, haga clic en **Remisión a una instancia superior**.</span><span class="sxs-lookup"><span data-stu-id="f23d0-245">In the left pane, click **Escalation**.</span></span>
2. <span data-ttu-id="f23d0-246">Active la casilla de verificación **Usar ruta de remisión a una instancia superior** para crear una ruta de remisión a una instancia superior.</span><span class="sxs-lookup"><span data-stu-id="f23d0-246">Select the **Use escalation path** check box to create an escalation path.</span></span> <span data-ttu-id="f23d0-247">De manera automática, el sistema asigna el documento a los usuarios que forman parte de la ruta de remisión a una instancia superior.</span><span class="sxs-lookup"><span data-stu-id="f23d0-247">The system automatically assigns the document to the users who are listed in the escalation path.</span></span> <span data-ttu-id="f23d0-248">La siguiente tabla, por ejemplo, representa una ruta de remisión a una instancia superior.</span><span class="sxs-lookup"><span data-stu-id="f23d0-248">For example, the following table represents an escalation path.</span></span>

    | <span data-ttu-id="f23d0-249">Secuencia</span><span class="sxs-lookup"><span data-stu-id="f23d0-249">Sequence</span></span> | <span data-ttu-id="f23d0-250">Ruta de remisión a una instancia superior</span><span class="sxs-lookup"><span data-stu-id="f23d0-250">Escalation path</span></span>      |
    |----------|----------------------|
    | <span data-ttu-id="f23d0-251">1</span><span class="sxs-lookup"><span data-stu-id="f23d0-251">1</span></span>        | <span data-ttu-id="f23d0-252">Asignar a rol: Donna</span><span class="sxs-lookup"><span data-stu-id="f23d0-252">Assign to: Donna</span></span>     |
    | <span data-ttu-id="f23d0-253">2</span><span class="sxs-lookup"><span data-stu-id="f23d0-253">2</span></span>        | <span data-ttu-id="f23d0-254">Asignar a rol: Erin</span><span class="sxs-lookup"><span data-stu-id="f23d0-254">Assign to: Erin</span></span>      |
    | <span data-ttu-id="f23d0-255">3</span><span class="sxs-lookup"><span data-stu-id="f23d0-255">3</span></span>        | <span data-ttu-id="f23d0-256">Acción final: Rechazar</span><span class="sxs-lookup"><span data-stu-id="f23d0-256">Final action: Reject</span></span> |

    <span data-ttu-id="f23d0-257">En este ejemplo, el sistema asigna el documento vencido a Donna.</span><span class="sxs-lookup"><span data-stu-id="f23d0-257">In this example, the system assigns the overdue document to Donna.</span></span> <span data-ttu-id="f23d0-258">Si Donna no responde en el tiempo asignado, el sistema asigna el documento a Erin.</span><span class="sxs-lookup"><span data-stu-id="f23d0-258">If Donna doesn't respond in the allotted time, the system assigns the document to Erin.</span></span> <span data-ttu-id="f23d0-259">Si Erin no responde en el tiempo asignado, el sistema rechaza el documento.</span><span class="sxs-lookup"><span data-stu-id="f23d0-259">If Erin doesn't respond in the allotted time, the system rejects the document.</span></span>

3. <span data-ttu-id="f23d0-260">Para agregar un usuario a la ruta de remisión a una instancia superior, haga clic en **Agregar remisión a una instancia superior**.</span><span class="sxs-lookup"><span data-stu-id="f23d0-260">To add a user to the escalation path, click **Add escalation**.</span></span> <span data-ttu-id="f23d0-261">En la pestaña **Tipo de asignación**, seleccione una de las opciones de la siguiente tabla. A continuación, siga los pasos adicionales correspondientes a la opción elegida antes de realizar el paso 4.</span><span class="sxs-lookup"><span data-stu-id="f23d0-261">On the **Assignment type** tab, select one of the options in the following table, and then follow the additional steps for that option before you go to step 4.</span></span>

    <table>
    <thead>
    <tr>
    <th><span data-ttu-id="f23d0-262">Opción</span><span class="sxs-lookup"><span data-stu-id="f23d0-262">Option</span></span></th>
    <th><span data-ttu-id="f23d0-263">Usuarios a los que se remite el documento</span><span class="sxs-lookup"><span data-stu-id="f23d0-263">Users that the document is escalated to</span></span></th>
    <th><span data-ttu-id="f23d0-264">Pasos adicionales</span><span class="sxs-lookup"><span data-stu-id="f23d0-264">Additional steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td><span data-ttu-id="f23d0-265">Jerarquía</span><span class="sxs-lookup"><span data-stu-id="f23d0-265">Hierarchy</span></span></td>
    <td><span data-ttu-id="f23d0-266">Usuarios de una jerarquía organizativa específica</span><span class="sxs-lookup"><span data-stu-id="f23d0-266">Users in a specific organizational hierarchy</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="f23d0-267">Tras seleccionar <strong>Jerarquía</strong>, en la pestaña <strong>Selección de jerarquía</strong>, en la lista <strong>Tipo de jerarquía</strong>, seleccione el tipo de jerarquía al que desea remitir a una instancia superior el documento.</span><span class="sxs-lookup"><span data-stu-id="f23d0-267">After you select <strong>Hierarchy</strong>, on the <strong>Hierarchy selection</strong> tab, in the <strong>Hierarchy type</strong> list, select the type of hierarchy to escalate the document to.</span></span></li>
    <li><span data-ttu-id="f23d0-268">El sistema debe recuperar un intervalo de nombres de usuario de la jerarquía.</span><span class="sxs-lookup"><span data-stu-id="f23d0-268">The system must retrieve a range of user names from the hierarchy.</span></span> <span data-ttu-id="f23d0-269">Dichos nombres representan a los usuarios a los que se puede remitir el documento.</span><span class="sxs-lookup"><span data-stu-id="f23d0-269">These names represent users that the document can be escalated to.</span></span> <span data-ttu-id="f23d0-270">Siga estos pasos para especificar el punto de inicio y de finalización del intervalo de nombres de usuario que el sistema recupera:</span><span class="sxs-lookup"><span data-stu-id="f23d0-270">Follow these steps to specify the starting point and ending point of the range of user names that the system retrieves:</span></span> <ol>
    <li><span data-ttu-id="f23d0-271">Para especificar el punto de inicio, seleccione una persona en la lista <strong>Comenzar desde</strong>.</span><span class="sxs-lookup"><span data-stu-id="f23d0-271">To specify the starting point, select a person in the <strong>Start from</strong> list.</span></span></li>
    <li><span data-ttu-id="f23d0-272">Para especificar el punto de finalización, haga clic en <strong>Agregar condición</strong>.</span><span class="sxs-lookup"><span data-stu-id="f23d0-272">To specify the ending point, click <strong>Add condition</strong>.</span></span> <span data-ttu-id="f23d0-273">A continuación, especifique una condición que determine en qué parte de la jerarquía el sistema dejará de recuperar nombres.</span><span class="sxs-lookup"><span data-stu-id="f23d0-273">Then enter a condition that determines where in the hierarchy the system stops retrieving names.</span></span></li>
    </ol>
    </li>
    <li><span data-ttu-id="f23d0-274">En la pestaña <strong>Opciones de jerarquía</strong>, especifique a qué usuarios del intervalo se debe remitir el documento para una instancia superior:</span><span class="sxs-lookup"><span data-stu-id="f23d0-274">On the <strong>Hierarchy options</strong> tab, specify which users in the range the document should be escalated to:</span></span> <ul>
    <li><span data-ttu-id="f23d0-275"><strong>Asignar a todos los usuarios recuperados</strong>: el documento se remite para una instancia superior para todos los usuarios del intervalo.</span><span class="sxs-lookup"><span data-stu-id="f23d0-275"><strong>Assign to all users retrieved</strong> – The document is escalated to all users in the range.</span></span></li>
    <li><span data-ttu-id="f23d0-276"><strong>Asignar sólo al último usuario recuperado</strong>: el documento se remite para una instancia superior únicamente al último usuario del intervalo.</span><span class="sxs-lookup"><span data-stu-id="f23d0-276"><strong>Assign only to last user retrieved</strong> – The document is escalated to only the last user in the range.</span></span></li>
    <li><span data-ttu-id="f23d0-277"><strong>Excluir usuarios con la siguiente condición</strong>: el documento no se remite para una instancia superior a ninguno de los usuarios del intervalo que cumplen con una condición determinada.</span><span class="sxs-lookup"><span data-stu-id="f23d0-277"><strong>Exclude users with the following condition</strong> – The document isn't escalated to any users in the range who meet a specific condition.</span></span> <span data-ttu-id="f23d0-278">Haga clic en <strong>Agregar condición</strong> para especificar la condición.</span><span class="sxs-lookup"><span data-stu-id="f23d0-278">Click <strong>Add condition</strong> to specify the condition.</span></span></li>
    </ul>
    </li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="f23d0-279">Usuario del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="f23d0-279">Workflow user</span></span></td>
    <td><span data-ttu-id="f23d0-280">Usuarios del flujo de trabajo actual</span><span class="sxs-lookup"><span data-stu-id="f23d0-280">Users in the current workflow</span></span></td>
    <td>
    <ul>
    <li><span data-ttu-id="f23d0-281">Tras seleccionar <strong>Usuario del flujo de trabajo</strong>, en la pestaña <strong>Usuario del flujo de trabajo</strong>, en la pestaña <strong>Usuario del flujo de trabajo</strong>, seleccione un usuario que participe en el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="f23d0-281">After you select <strong>Workflow user</strong>, on the <strong>Workflow user</strong> tab, in the <strong>Workflow user</strong> list, select a user who participates in the workflow.</span></span></li>
    </ul>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="f23d0-282">Usuario</span><span class="sxs-lookup"><span data-stu-id="f23d0-282">User</span></span></td>
    <td><span data-ttu-id="f23d0-283">Usuarios concretos</span><span class="sxs-lookup"><span data-stu-id="f23d0-283">Specific users</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="f23d0-284">Tras seleccionar <strong>Usuario</strong>, haga clic en la pestaña <strong>Usuario</strong>.</span><span class="sxs-lookup"><span data-stu-id="f23d0-284">After you select <strong>User</strong>, click the <strong>User</strong> tab.</span></span></li>
    <li><span data-ttu-id="f23d0-285">La lista <strong>Usuarios disponibles</strong> incluye todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="f23d0-285">The <strong>Available users</strong> list includes all users.</span></span> <span data-ttu-id="f23d0-286">Seleccione aquellos a los que desea remitir el documento para una instancia superior y, a continuación, muévalos a la lista <strong>Usuarios seleccionados</strong>.</span><span class="sxs-lookup"><span data-stu-id="f23d0-286">Select the users to escalate the document to, and then move those users to the <strong>Selected users</strong> list.</span></span></li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

4. <span data-ttu-id="f23d0-287">En la pestaña **Límite de tiempo**, en el campo **Duración**, especifique el tiempo del que dispone el usuario para realizar alguna acción en los documentos, dicho de otro modo, para responder a ellos.</span><span class="sxs-lookup"><span data-stu-id="f23d0-287">On the **Time limit** tab, in the **Duration** field, specify how much time the user has to take action on, or respond to, documents.</span></span> <span data-ttu-id="f23d0-288">Seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="f23d0-288">Select one of the following options:</span></span>

    - <span data-ttu-id="f23d0-289">**Horas**: escriba la cantidad de horas de las que dispone el usuario para responder.</span><span class="sxs-lookup"><span data-stu-id="f23d0-289">**Hours** – Enter the number of hours that the user has to respond.</span></span> <span data-ttu-id="f23d0-290">A continuación, seleccione el calendario que usa la organización y escriba la información pertinente acerca de la semana laboral de la organización.</span><span class="sxs-lookup"><span data-stu-id="f23d0-290">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="f23d0-291">**Días**: escriba la cantidad de días de los que dispone el usuario para responder.</span><span class="sxs-lookup"><span data-stu-id="f23d0-291">**Days** – Enter the number of days that the user has to respond.</span></span> <span data-ttu-id="f23d0-292">A continuación, seleccione el calendario que usa la organización y escriba la información pertinente acerca de la semana laboral de la organización.</span><span class="sxs-lookup"><span data-stu-id="f23d0-292">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="f23d0-293">**Semanas**: escriba la cantidad de semanas de las que dispone el usuario para responder.</span><span class="sxs-lookup"><span data-stu-id="f23d0-293">**Weeks** – Enter the number of weeks that the user has to respond.</span></span>
    - <span data-ttu-id="f23d0-294">**Meses**: seleccione el día y la semana en los que vence el plazo para responder.</span><span class="sxs-lookup"><span data-stu-id="f23d0-294">**Months** – Select the day and week that the user must respond by.</span></span> <span data-ttu-id="f23d0-295">Por ejemplo, tal vez desee que el usuario haya respondido antes del viernes de la tercera semana del mes.</span><span class="sxs-lookup"><span data-stu-id="f23d0-295">For example, you might want the user to respond by Friday of the third week of the month.</span></span>
    - <span data-ttu-id="f23d0-296">**Años**: seleccione el día, la semana y el mes en los que vence el plazo para responder.</span><span class="sxs-lookup"><span data-stu-id="f23d0-296">**Years** – Select the day, week, and month that the user must respond by.</span></span> <span data-ttu-id="f23d0-297">Por ejemplo, tal vez desee que el usuario haya respondido antes del viernes de la tercera semana de diciembre.</span><span class="sxs-lookup"><span data-stu-id="f23d0-297">For example, you might want the user to respond by Friday of the third week of December.</span></span>

5. <span data-ttu-id="f23d0-298">Repita los pasos 3 a 4 por cada usuario que se debe agregar a la ruta de remisión a una instancia superior.</span><span class="sxs-lookup"><span data-stu-id="f23d0-298">Repeat steps 3 through 4 for each user that should be added to the escalation path.</span></span> <span data-ttu-id="f23d0-299">El orden de los usuarios se puede modificar.</span><span class="sxs-lookup"><span data-stu-id="f23d0-299">You can change the order of the users.</span></span>
6. <span data-ttu-id="f23d0-300">Si los usuarios de la ruta de remisión a una instancia superior no responden en el tiempo asignado, el sistema realiza una acción en el documento de manera automática.</span><span class="sxs-lookup"><span data-stu-id="f23d0-300">If the users in the escalation path don't respond in the allotted time, the system automatically take action on the document.</span></span> <span data-ttu-id="f23d0-301">Para especificar la acción que el sistema realiza, seleccione la fila **Acción** y, a continuación, en la pestaña **Finalizar acción**, seleccione una acción.</span><span class="sxs-lookup"><span data-stu-id="f23d0-301">To specify the action that the system takes, select the **Action** row, and then, on the **End action** tab, select an action.</span></span>
