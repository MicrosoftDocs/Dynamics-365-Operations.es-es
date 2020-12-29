---
title: Configurar los procesos de aprobación en un flujo de trabajo
description: Use el siguiente procedimiento para configurar las propiedades del proceso de aprobación.
author: ChrisGarty
manager: AnnBe
ms.date: 01/24/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 195643
ms.assetid: f853f57b-83ae-4fb0-a9fa-06ea3fc34fa1
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b6f4f6a3fdf07ae267f92eedd312c6c721f18429
ms.sourcegitcommit: f5e31c34640add6d40308ac1365cc0ee60e60e24
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/08/2020
ms.locfileid: "4692901"
---
# <a name="configure-approval-processes-in-a-workflow"></a><span data-ttu-id="45e2d-103">Configurar los procesos de aprobación en un flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="45e2d-103">Configure approval processes in a workflow</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="45e2d-104">Use el siguiente procedimiento para configurar las propiedades del proceso de aprobación.</span><span class="sxs-lookup"><span data-stu-id="45e2d-104">Use the following procedure to configure the properties of the approval process.</span></span>

<span data-ttu-id="45e2d-105">Para configurar un proceso de aprobación, en el editor de flujo de trabajo, haga clic con el botón secundario en el elemento de aprobación y, a continuación, haga clic en **Propiedades** para abrir el formulario **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="45e2d-105">To configure an approval process, in the workflow editor, right-click the approval element, and then click **Properties** to open the **Properties** form.</span></span>

## <a name="name-the-approval-process"></a><span data-ttu-id="45e2d-106">Asignación de un nombre al proceso de aprobación</span><span class="sxs-lookup"><span data-stu-id="45e2d-106">Name the approval process</span></span>

<span data-ttu-id="45e2d-107">Siga estos pasos para asignar un nombre al proceso de aprobación.</span><span class="sxs-lookup"><span data-stu-id="45e2d-107">Follow these steps to enter a name for the approval process.</span></span>

1. <span data-ttu-id="45e2d-108">En el panel izquierdo, haga clic en **Configuración básica**.</span><span class="sxs-lookup"><span data-stu-id="45e2d-108">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="45e2d-109">En el campo **Nombre**, especifique un nombre único para el proceso de aprobación.</span><span class="sxs-lookup"><span data-stu-id="45e2d-109">In the **Name** field, enter a unique name for the approval process.</span></span>

## <a name="specify-when-the-system-automatically-acts-on-the-document"></a><span data-ttu-id="45e2d-110">Especificación de las condiciones en que el sistema realiza una acción automática en el documento</span><span class="sxs-lookup"><span data-stu-id="45e2d-110">Specify when the system automatically acts on the document</span></span>

<span data-ttu-id="45e2d-111">Puede configurar el sistema para que realice alguna acción en el documento de forma automática si se cumplen ciertas condiciones.</span><span class="sxs-lookup"><span data-stu-id="45e2d-111">You can configure the system to automatically act on the document if specific conditions are met.</span></span> <span data-ttu-id="45e2d-112">Por ejemplo, el sistema puede aprobar los informes de gastos con importes totales inferiores a 100 USD.</span><span class="sxs-lookup"><span data-stu-id="45e2d-112">For example, the system can approve expense reports that have total amounts that are less than USD 100.</span></span> <span data-ttu-id="45e2d-113">Siga estos pasos para especificar cuándo el sistema realiza una acción en el documento.</span><span class="sxs-lookup"><span data-stu-id="45e2d-113">Follow these steps to specify when the system acts on the document.</span></span>

1. <span data-ttu-id="45e2d-114">En el panel izquierdo, haga clic en **Acciones automáticas**.</span><span class="sxs-lookup"><span data-stu-id="45e2d-114">In the left pane, click **Automatic actions**.</span></span>
2. <span data-ttu-id="45e2d-115">Active la casilla **Habilitar acciones automáticas**.</span><span class="sxs-lookup"><span data-stu-id="45e2d-115">Select the **Enable automatic actions** check box.</span></span>
3. <span data-ttu-id="45e2d-116">Haga clic en **Agregar condición**.</span><span class="sxs-lookup"><span data-stu-id="45e2d-116">Click **Add condition**.</span></span>
4. <span data-ttu-id="45e2d-117">Escriba una condición.</span><span class="sxs-lookup"><span data-stu-id="45e2d-117">Enter a condition.</span></span>
5. <span data-ttu-id="45e2d-118">Escriba condiciones adicionales, si fuera necesario.</span><span class="sxs-lookup"><span data-stu-id="45e2d-118">Enter additional conditions, if necessary.</span></span>
6. <span data-ttu-id="45e2d-119">Para comprobar que las condiciones definidas se hayan configurado correctamente, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="45e2d-119">To verify that the conditions that you entered are configured correctly, complete the following steps:</span></span>

    1. <span data-ttu-id="45e2d-120">Haga clic en **Probar** para abrir el formulario **Probar la condición del flujo de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="45e2d-120">Click **Test** to open the **Test workflow condition** form.</span></span>
    2. <span data-ttu-id="45e2d-121">Seleccione un registro del área **Comprobar condición** del formulario.</span><span class="sxs-lookup"><span data-stu-id="45e2d-121">Select a record in the **Validate condition** area of the form.</span></span>
    3. <span data-ttu-id="45e2d-122">Haga clic en **Probar**.</span><span class="sxs-lookup"><span data-stu-id="45e2d-122">Click **Test**.</span></span> <span data-ttu-id="45e2d-123">El sistema evalúa el registro seleccionado para determinar si reúne las condiciones definidas.</span><span class="sxs-lookup"><span data-stu-id="45e2d-123">The system evaluates the record to determine whether it meets the conditions that you defined.</span></span>
    4. <span data-ttu-id="45e2d-124">Haga clic en **Aceptar** o en **Cancelar** para regresar al formulario **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="45e2d-124">Click **OK** or **Cancel** to return to the **Properties** form.</span></span>

7. <span data-ttu-id="45e2d-125">En la lista **Acción de autocompletar**, seleccione la acción que el sistema debe realizar en el documento.</span><span class="sxs-lookup"><span data-stu-id="45e2d-125">In the **Auto complete action** list, select the action that the system should take on the document.</span></span>

## <a name="specify-when-notifications-are-sent"></a><span data-ttu-id="45e2d-126">Especificación del momento en que se envían notificaciones</span><span class="sxs-lookup"><span data-stu-id="45e2d-126">Specify when notifications are sent</span></span>

<span data-ttu-id="45e2d-127">Puede enviar notificaciones cuando un documento se ha aprobado, rechazado, delegado o remitido a una instancia superior o cuando se ha solicitado un cambio.</span><span class="sxs-lookup"><span data-stu-id="45e2d-127">You can send notifications to people when a document has been approved, rejected, delegated, or escalated, or when a change has been requested.</span></span> <span data-ttu-id="45e2d-128">Siga estos pasos para especificar cuándo se deben enviar notificaciones y a quiénes se deben enviar.</span><span class="sxs-lookup"><span data-stu-id="45e2d-128">Follow these steps to specify when notifications are sent, and who the notifications are sent to.</span></span>

1. <span data-ttu-id="45e2d-129">En el panel izquierdo, haga clic en **Notificaciones**.</span><span class="sxs-lookup"><span data-stu-id="45e2d-129">In the left pane, click **Notifications**.</span></span>
2. <span data-ttu-id="45e2d-130">Active las casillas de verificación junto a los eventos que deben notificarse:</span><span class="sxs-lookup"><span data-stu-id="45e2d-130">Select the check box next to the events to send notifications for:</span></span>

    - <span data-ttu-id="45e2d-131">**Delegar**: cuando un documento se ha asignado a otro usuario para que se lo apruebe.</span><span class="sxs-lookup"><span data-stu-id="45e2d-131">**Delegate** – When a document has been assigned to another user for approval.</span></span>
    - <span data-ttu-id="45e2d-132">**Remitir a una instancia superior**: cuando el usuario asignado no ha realizado ninguna acción en un documento en el tiempo asignado.</span><span class="sxs-lookup"><span data-stu-id="45e2d-132">**Escalate** – When the assigned user has not acted on a document in the allotted time.</span></span>
    - <span data-ttu-id="45e2d-133">**Aprobar**: cuando un documento se ha aprobado.</span><span class="sxs-lookup"><span data-stu-id="45e2d-133">**Approve** – When a document has been approved.</span></span>
    - <span data-ttu-id="45e2d-134">**Rechazar**: cuando un documento se ha rechazado.</span><span class="sxs-lookup"><span data-stu-id="45e2d-134">**Reject** – When a document has been rejected.</span></span>
    - <span data-ttu-id="45e2d-135">**Solicitar cambio**: cuando el usuario asignado ha solicitado que se realice un cambio en un documento enviado.</span><span class="sxs-lookup"><span data-stu-id="45e2d-135">**Request change** – When the assigned user has requested a change to a document that was submitted.</span></span>

3. <span data-ttu-id="45e2d-136">Seleccione la fila correspondiente a uno de los eventos que seleccionó en el paso 2.</span><span class="sxs-lookup"><span data-stu-id="45e2d-136">Select the row for an event that you selected in step 2.</span></span>
4. <span data-ttu-id="45e2d-137">Haga clic en la ficha **Texto de la notificación**.</span><span class="sxs-lookup"><span data-stu-id="45e2d-137">Click the **Notification text** tab.</span></span>
5. <span data-ttu-id="45e2d-138">En el cuadro de texto, escriba el texto de la notificación.</span><span class="sxs-lookup"><span data-stu-id="45e2d-138">In the text box, enter the text for the notification.</span></span>
6. <span data-ttu-id="45e2d-139">Para personalizar el texto, puede insertar marcadores de posición, que se reemplazan con los datos adecuados cuando se muestran a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="45e2d-139">To personalize the text, you can insert placeholders, which are replaced with the appropriate data when they are displayed to users.</span></span> <span data-ttu-id="45e2d-140">Para insertar un marcador de posición, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="45e2d-140">To insert a placeholder, follow these steps:</span></span>

    1. <span data-ttu-id="45e2d-141">Haga clic en el punto del cuadro de texto en el que debe aparecer el marcador de posición.</span><span class="sxs-lookup"><span data-stu-id="45e2d-141">Click in the text box at the location where the placeholder should appear.</span></span>
    2. <span data-ttu-id="45e2d-142">Haga clic en **Insertar marcador de posición**.</span><span class="sxs-lookup"><span data-stu-id="45e2d-142">Click **Insert placeholder**.</span></span>
    3. <span data-ttu-id="45e2d-143">En la lista que se abre, seleccione el marcador de posición que desea insertar.</span><span class="sxs-lookup"><span data-stu-id="45e2d-143">In the list that is displayed, select the placeholder to insert.</span></span>
    4. <span data-ttu-id="45e2d-144">Haga clic en **Insertar**.</span><span class="sxs-lookup"><span data-stu-id="45e2d-144">Click **Insert**.</span></span>

7. <span data-ttu-id="45e2d-145">Para agregar traducciones de la notificación, haga clic en **Traducciones**.</span><span class="sxs-lookup"><span data-stu-id="45e2d-145">To add translations of the notification, click **Translations**.</span></span> <span data-ttu-id="45e2d-146">En el formulario que aparece, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="45e2d-146">In the form that is displayed, follow these steps:</span></span>

    1. <span data-ttu-id="45e2d-147">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="45e2d-147">Click **Add**.</span></span>
    2. <span data-ttu-id="45e2d-148">En la lista que aparece, seleccione el idioma que usará para escribir el texto.</span><span class="sxs-lookup"><span data-stu-id="45e2d-148">In the list that is displayed, select the language in which you will enter the text.</span></span>
    3. <span data-ttu-id="45e2d-149">En el cuadro de texto **Texto traducido**, escriba el texto.</span><span class="sxs-lookup"><span data-stu-id="45e2d-149">In the **Translated text** text box, enter the text.</span></span>
    4. <span data-ttu-id="45e2d-150">Para personalizar el texto, inserte marcadores de posición.</span><span class="sxs-lookup"><span data-stu-id="45e2d-150">To personalize the text, insert placeholders.</span></span>
    5. <span data-ttu-id="45e2d-151">Haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="45e2d-151">Click **Close**.</span></span>

8. <span data-ttu-id="45e2d-152">Haga clic en la ficha **Destinatario**.</span><span class="sxs-lookup"><span data-stu-id="45e2d-152">Click the **Recipient** tab.</span></span>
9. <span data-ttu-id="45e2d-153">Especifique los destinatarios de las notificaciones.</span><span class="sxs-lookup"><span data-stu-id="45e2d-153">Specify who the notifications are sent to.</span></span> <span data-ttu-id="45e2d-154">Seleccione una de las opciones de la siguiente tabla y, a continuación, siga los pasos adicionales correspondientes a la opción elegida antes de realizar el paso 10.</span><span class="sxs-lookup"><span data-stu-id="45e2d-154">Select one of the options in the following table, and then follow the additional steps for the option before you go to step 10.</span></span>

    <table>
    <thead>
    <tr>
    <th><span data-ttu-id="45e2d-155">Opción</span><span class="sxs-lookup"><span data-stu-id="45e2d-155">Option</span></span></th>
    <th><span data-ttu-id="45e2d-156">Destinatarios de las notificaciones</span><span class="sxs-lookup"><span data-stu-id="45e2d-156">Notification recipients</span></span></th>
    <th><span data-ttu-id="45e2d-157">Pasos adicionales</span><span class="sxs-lookup"><span data-stu-id="45e2d-157">Additional steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td><span data-ttu-id="45e2d-158"><strong>Participante</strong></span><span class="sxs-lookup"><span data-stu-id="45e2d-158"><strong>Participant</strong></span></span></td>
    <td><span data-ttu-id="45e2d-159">Usuarios asignados a un grupo o rol específicos</span><span class="sxs-lookup"><span data-stu-id="45e2d-159">Users who are assigned to a specific group or role</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="45e2d-160">Tras seleccionar <strong>Participante</strong>, haga clic en la ficha <strong>Basado en el rol</strong>.</span><span class="sxs-lookup"><span data-stu-id="45e2d-160">After you select <strong>Participant</strong>, click the <strong>Role based</strong> tab.</span></span></li>
    <li><span data-ttu-id="45e2d-161">En la lista <strong>Tipo de participante</strong>, seleccione el tipo de grupo o rol al que enviar las notificaciones.</span><span class="sxs-lookup"><span data-stu-id="45e2d-161">In the <strong>Type of participant</strong> list, select the type of group or role to send notifications to.</span></span></li>
    <li><span data-ttu-id="45e2d-162">En la lista <strong>Participante</strong>, seleccione el grupo o rol al que se deben enviar las notificaciones.</span><span class="sxs-lookup"><span data-stu-id="45e2d-162">In the <strong>Participant</strong> list, select the group or role to send notifications to.</span></span></li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="45e2d-163"><strong>Usuario del flujo de trabajo</strong></span><span class="sxs-lookup"><span data-stu-id="45e2d-163"><strong>Workflow user</strong></span></span></td>
    <td><span data-ttu-id="45e2d-164">Usuarios que participan en el flujo de trabajo actual</span><span class="sxs-lookup"><span data-stu-id="45e2d-164">Users who participate in the current workflow</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="45e2d-165">Tras seleccionar <strong>Usuario de flujo de trabajo</strong>, haga clic en la ficha <strong>Usuario de flujo de trabajo</strong>.</span><span class="sxs-lookup"><span data-stu-id="45e2d-165">After you select <strong>Workflow user</strong>, click the <strong>Workflow user</strong> tab.</span></span></li>
    <li><span data-ttu-id="45e2d-166">En la lista <strong>Usuario de flujo de trabajo</strong>, seleccione un usuario que participe en el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="45e2d-166">In the <strong>Workflow user</strong> list, select a user who participates in the workflow.</span></span></li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="45e2d-167"><strong>Usuario</strong></span><span class="sxs-lookup"><span data-stu-id="45e2d-167"><strong>User</strong></span></span></td>
    <td><span data-ttu-id="45e2d-168">Usuarios concretos</span><span class="sxs-lookup"><span data-stu-id="45e2d-168">Specific users</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="45e2d-169">Tras seleccionar <strong>Usuario</strong>, haga clic en la pestaña <strong>Usuario</strong>.</span><span class="sxs-lookup"><span data-stu-id="45e2d-169">After you select <strong>User</strong>, click the <strong>User</strong> tab.</span></span></li>
    <li><span data-ttu-id="45e2d-170">Seleccione aquellos usuarios a los que enviar notificaciones y, a continuación, muévalos a la lista de <strong>Usuarios seleccionados</strong>.</span><span class="sxs-lookup"><span data-stu-id="45e2d-170">Select the users to send notifications to, and then move these users to the <strong>Selected users</strong> list.</span></span></li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

10. <span data-ttu-id="45e2d-171">Repita los pasos 3 a 9 por cada uno de los eventos que haya seleccionado en el paso 2.</span><span class="sxs-lookup"><span data-stu-id="45e2d-171">Repeat steps 3 through 9 for each event that you selected in step 2.</span></span>

## <a name="specify-a-final-approver"></a><span data-ttu-id="45e2d-172">Especificación de un aprobador final</span><span class="sxs-lookup"><span data-stu-id="45e2d-172">Specify a final approver</span></span>

<span data-ttu-id="45e2d-173">Puede designar un aprobador final para escenarios en los que el aprobador es la persona que envió el documento para su aprobación y se está utilizando la "anulación de la aprobación del remitente".</span><span class="sxs-lookup"><span data-stu-id="45e2d-173">You can designate a final approver for scenarios where the approver is the person who submitted the document for approval and the "disallow approval by submitter" is being used.</span></span> <span data-ttu-id="45e2d-174">Para especificar un aprobador final, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="45e2d-174">Follow these steps to specify a final approver.</span></span>

1. <span data-ttu-id="45e2d-175">En el editor de flujo de trabajo, haga clic con el botón secundario en el elemento de aprobación y, a continuación, seleccione **Propiedades** para abrir el formulario **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="45e2d-175">In the workflow editor, right-click the approval element, and then select **Properties** to open the **Properties** form.</span></span>
2. <span data-ttu-id="45e2d-176">En el panel izquiero, haga clic en **Configuración avanzada**.</span><span class="sxs-lookup"><span data-stu-id="45e2d-176">In the left pane, click **Advanced settings**.</span></span>
3. <span data-ttu-id="45e2d-177">Seleccione la casilla de verificación **Usar aprobador final**.</span><span class="sxs-lookup"><span data-stu-id="45e2d-177">Select the **Use final approver** check box.</span></span>
4. <span data-ttu-id="45e2d-178">En la lista, seleccione un usuario como aprobador final.</span><span class="sxs-lookup"><span data-stu-id="45e2d-178">In the list, select a user to be the final approver.</span></span>

## <a name="set-a-time-limit"></a><span data-ttu-id="45e2d-179">Definición de un límite de tiempo</span><span class="sxs-lookup"><span data-stu-id="45e2d-179">Set a time limit</span></span>

<span data-ttu-id="45e2d-180">Siga estos pasos si el proceso de aprobación se debe completar en un plazo específico.</span><span class="sxs-lookup"><span data-stu-id="45e2d-180">Follow these steps if the approval process must be completed in a specific time.</span></span>

> [!NOTE]
> <span data-ttu-id="45e2d-181">Las opciones que seleccione al realizar estos pasos reemplazarán las opciones que haya seleccionado en las áreas de **Asignación** y **Escalada** de cada paso de aprobación.</span><span class="sxs-lookup"><span data-stu-id="45e2d-181">The options that you select in these steps override the options that you selected in the **Assignment** and **Escalation** areas of each approval step.</span></span>

1. <span data-ttu-id="45e2d-182">En el panel izquiero, haga clic en **Configuración avanzada**.</span><span class="sxs-lookup"><span data-stu-id="45e2d-182">In the left pane, click **Advanced settings**.</span></span>
2. <span data-ttu-id="45e2d-183">Active la casilla **Configurar un límite de tiempo para el elemento de** **flujo de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="45e2d-183">Select the **Set a time limit for the workflow** **element** check box.</span></span>
3. <span data-ttu-id="45e2d-184">En el campo **Duración**, especifique cuándo se debe completar el proceso de aprobación.</span><span class="sxs-lookup"><span data-stu-id="45e2d-184">In the **Duration** field, specify when the approval process must be completed.</span></span> <span data-ttu-id="45e2d-185">Seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="45e2d-185">Select one of the following options:</span></span>

    - <span data-ttu-id="45e2d-186">**Horas**: escriba la cantidad de horas disponibles para completar el proceso de aprobación.</span><span class="sxs-lookup"><span data-stu-id="45e2d-186">**Hours** – Enter the number of hours in which the approval process must be completed.</span></span> <span data-ttu-id="45e2d-187">A continuación, seleccione el calendario que usa la organización y escriba la información pertinente acerca de la semana laboral de la organización.</span><span class="sxs-lookup"><span data-stu-id="45e2d-187">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="45e2d-188">**Días**: escriba la cantidad de días disponibles para completar el proceso de aprobación.</span><span class="sxs-lookup"><span data-stu-id="45e2d-188">**Days** – Enter the number of days in which the approval process must be completed.</span></span> <span data-ttu-id="45e2d-189">A continuación, seleccione el calendario que usa la organización y escriba la información pertinente acerca de la semana laboral de la organización.</span><span class="sxs-lookup"><span data-stu-id="45e2d-189">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="45e2d-190">**Semanas**: escriba la cantidad de semanas disponibles para completar el proceso de aprobación.</span><span class="sxs-lookup"><span data-stu-id="45e2d-190">**Weeks** – Enter the number of weeks in which the approval process must be completed.</span></span>
    - <span data-ttu-id="45e2d-191">**Meses**: seleccione el día y la semana en los que vence el plazo para completar el proceso de aprobación.</span><span class="sxs-lookup"><span data-stu-id="45e2d-191">**Months** – Select the day and week by which the approval process must be completed.</span></span> <span data-ttu-id="45e2d-192">Por ejemplo, tal vez desee que el proceso de aprobación se haya completado antes del viernes de la tercera semana del mes.</span><span class="sxs-lookup"><span data-stu-id="45e2d-192">For example, you may want the approval process to be completed by Friday of the third week of the month.</span></span>
    - <span data-ttu-id="45e2d-193">**Años**: seleccione el día, la semana y el mes en los que vence el plazo para completar el proceso de aprobación.</span><span class="sxs-lookup"><span data-stu-id="45e2d-193">**Years** – Select the day, week, and month by which the approval process must be completed.</span></span> <span data-ttu-id="45e2d-194">Por ejemplo, tal vez desee que el proceso de aprobación se haya completado antes del viernes de la tercera semana de diciembre.</span><span class="sxs-lookup"><span data-stu-id="45e2d-194">For example, you may want the approval process to be completed by Friday of the third week of December.</span></span>

4. <span data-ttu-id="45e2d-195">Si se supera el límite de tiempo, el sistema realiza una acción en el documento.</span><span class="sxs-lookup"><span data-stu-id="45e2d-195">If the time limit is exceeded, the system acts on the document.</span></span> <span data-ttu-id="45e2d-196">En la lista **Acción**, seleccione la acción que debe realizar el sistema.</span><span class="sxs-lookup"><span data-stu-id="45e2d-196">In the **Action** list, select the action that the system should take.</span></span>

## <a name="specify-which-actions-are-available-to-the-user"></a><span data-ttu-id="45e2d-197">Especificación de las acciones de las que dispone el usuario</span><span class="sxs-lookup"><span data-stu-id="45e2d-197">Specify which actions are available to the user</span></span>

<span data-ttu-id="45e2d-198">Cuando se asigna un documento a un usuario para que lo apruebe, este debe realizar alguna acción.</span><span class="sxs-lookup"><span data-stu-id="45e2d-198">When a document is assigned to a user for approval, the user must act on the document.</span></span> <span data-ttu-id="45e2d-199">Siga estos pasos para especificar las acciones que el usuario puede realizar en el documento enviado.</span><span class="sxs-lookup"><span data-stu-id="45e2d-199">Follows these steps to specify which actions the user can take on the document that was submitted.</span></span>

1. <span data-ttu-id="45e2d-200">En el panel izquiero, haga clic en **Configuración avanzada**.</span><span class="sxs-lookup"><span data-stu-id="45e2d-200">In the left pane, click **Advanced settings**.</span></span>
2. <span data-ttu-id="45e2d-201">Active la casilla de verificación **Aprobar** si el usuario puede aprobar el documento.</span><span class="sxs-lookup"><span data-stu-id="45e2d-201">Select the **Approve** check box if the user can approve the document.</span></span>
3. <span data-ttu-id="45e2d-202">Active la casilla de verificación **Rechazar** si el usuario puede rechazar el documento.</span><span class="sxs-lookup"><span data-stu-id="45e2d-202">Select the **Reject** check box the user can reject the document.</span></span>
4. <span data-ttu-id="45e2d-203">Active la casilla de verificación **Solicitar cambio** si el usuario puede solicitar que se realicen cambios en el documento.</span><span class="sxs-lookup"><span data-stu-id="45e2d-203">Select the **Request change** check box the user can request changes to the document.</span></span>
5. <span data-ttu-id="45e2d-204">Active la casilla de verificación **Delegar** si el usuario puede asignar el documento a otro usuario para que lo apruebe.</span><span class="sxs-lookup"><span data-stu-id="45e2d-204">Select the **Delegate** check box if the user can assign the document to another user for approval.</span></span>

> [!NOTE]
> <span data-ttu-id="45e2d-205">La casilla de verificación **Habilitar acciones desde la lista de trabajo de Enterprise Portal** se ha quedado obsoleta.</span><span class="sxs-lookup"><span data-stu-id="45e2d-205">The **Enable actions from the work list in Enterprise Portal** check box has been deprecated.</span></span>

## <a name="configure-the-approval-steps"></a><span data-ttu-id="45e2d-206"> Configuración de los pasos de aprobación</span><span class="sxs-lookup"><span data-stu-id="45e2d-206">Configure the approval steps</span></span>

<span data-ttu-id="45e2d-207">Los procesos de aprobación se componen de pasos de aprobación.</span><span class="sxs-lookup"><span data-stu-id="45e2d-207">An approval process consists of approval steps.</span></span> <span data-ttu-id="45e2d-208">Realice el siguiente procedimiento para agregar pasos en el proceso de aprobación y configurarlos.</span><span class="sxs-lookup"><span data-stu-id="45e2d-208">Complete the following procedure to add steps the approval process and configure the steps.</span></span>

1. <span data-ttu-id="45e2d-209">En el editor de flujo de trabajo, haga doble clic en el proceso de aprobación.</span><span class="sxs-lookup"><span data-stu-id="45e2d-209">In the workflow editor, double-click the approval process.</span></span> <span data-ttu-id="45e2d-210">Los pasos del proceso se mostrarán en el editor de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="45e2d-210">The workflow editor displays the steps of the approval process.</span></span>
2. <span data-ttu-id="45e2d-211">Para agregar un paso de aprobación, arrástrelo desde el área de **Elementos del flujo de trabajo** al lienzo.</span><span class="sxs-lookup"><span data-stu-id="45e2d-211">To add an approval step, drag the step from the **Workflow elements** area to the canvas.</span></span>
3. <span data-ttu-id="45e2d-212">Para configurar un paso de aprobación, vea [Configurar los pasos de aprobación en un flujo de trabajo](configure-approval-step-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="45e2d-212">To configure an approval step, see [Configure approval steps in a workflow](configure-approval-step-workflow.md).</span></span>
