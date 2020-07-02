---
title: Configurar decisiones manuales en un flujo de trabajo
description: Este tema explica cómo configurar las propiedades de una decisión manual.
author: sericks007
manager: AnnBe
ms.date: 06/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 192101
ms.assetid: 0bccad77-1a44-4f08-967b-12c62c02afc7
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 130cb50369c13bc3478340023c94f169ee5250cf
ms.sourcegitcommit: a5009c8958037afbaa1dd4f1469255b187ced93a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/15/2020
ms.locfileid: "3455042"
---
# <a name="configure-manual-decisions-in-a-workflow"></a><span data-ttu-id="2307e-103">Configurar decisiones manuales en un flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="2307e-103">Configure manual decisions in a workflow</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2307e-104">Este tema explica cómo configurar las propiedades de una decisión manual.</span><span class="sxs-lookup"><span data-stu-id="2307e-104">This topic explains how to configure the properties of a manual decision.</span></span>

<span data-ttu-id="2307e-105">Para configurar una decisión manual, en el editor de flujo de trabajo, haga clic con el botón secundario en la decisión manual y, a continuación, haga clic en **Propiedades** para abrir la página **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="2307e-105">To configure a manual decision in the workflow editor, right-click the manual decision, and then click **Properties** to open the **Properties** page.</span></span> <span data-ttu-id="2307e-106">A continuación, use los siguientes procedimientos para configurar las propiedades de la decisión manual.</span><span class="sxs-lookup"><span data-stu-id="2307e-106">Then use the following procedures to configure the properties of the manual decision.</span></span>

## <a name="name-the-decision"></a><span data-ttu-id="2307e-107">Asignación de un nombre a la decisión</span><span class="sxs-lookup"><span data-stu-id="2307e-107">Name the decision</span></span>

<span data-ttu-id="2307e-108">Siga estos pasos para asignar un nombre a la decisión manual.</span><span class="sxs-lookup"><span data-stu-id="2307e-108">Follow these steps to enter a name for the manual decision.</span></span>

1. <span data-ttu-id="2307e-109">En el panel izquierdo, haga clic en **Configuración básica**.</span><span class="sxs-lookup"><span data-stu-id="2307e-109">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="2307e-110">En el campo **Nombre**, escriba un nombre único para la decisión manual.</span><span class="sxs-lookup"><span data-stu-id="2307e-110">In the **Name** field, enter a unique name for the manual decision.</span></span>

## <a name="enter-a-subject-line-and-instructions"></a><span data-ttu-id="2307e-111">Especificación de una línea de asunto e instrucciones</span><span class="sxs-lookup"><span data-stu-id="2307e-111">Enter a subject line and instructions</span></span>

<span data-ttu-id="2307e-112">Debe proporcionar una línea de asunto e instrucciones a los usuarios que están asignados a la decisión manual.</span><span class="sxs-lookup"><span data-stu-id="2307e-112">You must provide a subject line and instructions to users who are assigned to the manual decision.</span></span> <span data-ttu-id="2307e-113">Por ejemplo, si está configurando una decisión para solicitudes de compra, el usuario asignado a la decisión ve la línea de asunto y las instrucciones en la página **Solicitudes de compra**.</span><span class="sxs-lookup"><span data-stu-id="2307e-113">For example, if you're configuring a decision for purchase requisitions, the user who is assigned to the decision sees the subject line and instructions on the **Purchase requisitions** page.</span></span> <span data-ttu-id="2307e-114">La línea de asunto se muestra en una barra de mensajes de la página.</span><span class="sxs-lookup"><span data-stu-id="2307e-114">The subject line appears in a message bar on the page.</span></span> <span data-ttu-id="2307e-115">A continuación, el usuario puede hacer clic en el icono de dicha barra para ver las instrucciones.</span><span class="sxs-lookup"><span data-stu-id="2307e-115">The user can then click the icon in the message bar to view the instructions.</span></span> <span data-ttu-id="2307e-116">Siga estos pasos para escribir una línea de asunto e instrucciones.</span><span class="sxs-lookup"><span data-stu-id="2307e-116">Follow these steps to enter a subject line and instructions.</span></span>

1. <span data-ttu-id="2307e-117">En el panel izquierdo, haga clic en **Configuración básica**.</span><span class="sxs-lookup"><span data-stu-id="2307e-117">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="2307e-118">En la pestaña **Instrucciones** , en el campo **Asunto del elemento de trabajo**, escriba la línea de asunto.</span><span class="sxs-lookup"><span data-stu-id="2307e-118">On the **Instructions** tab, in the **Work item subject** field, enter the subject line.</span></span>
3. <span data-ttu-id="2307e-119">Para personalizar la línea de asunto, puede insertar marcadores de posición.</span><span class="sxs-lookup"><span data-stu-id="2307e-119">To personalize the subject line, you can insert placeholders.</span></span> <span data-ttu-id="2307e-120">Estos se reemplazan con los datos adecuados cuando se muestra la línea de asunto a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="2307e-120">Placeholders are replaced with appropriate data when the subject line is shown to users.</span></span> <span data-ttu-id="2307e-121">Para insertar un marcador de posición, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="2307e-121">Follow these steps to insert a placeholder:</span></span>

    1. <span data-ttu-id="2307e-122">En el cuadro de texto, gaga clic para especificar dónde debe aparecer el marcador de posición.</span><span class="sxs-lookup"><span data-stu-id="2307e-122">In the text box, click where the placeholder should appear.</span></span>
    2. <span data-ttu-id="2307e-123">Haga clic en **Insertar marcador de posición**.</span><span class="sxs-lookup"><span data-stu-id="2307e-123">Click **Insert placeholder**.</span></span>
    3. <span data-ttu-id="2307e-124">En la lista que aparece, seleccione el marcador de posición que desea insertar.</span><span class="sxs-lookup"><span data-stu-id="2307e-124">In the list that appears, select the placeholder to insert.</span></span>
    4. <span data-ttu-id="2307e-125">Haga clic en **Insertar**.</span><span class="sxs-lookup"><span data-stu-id="2307e-125">Click **Insert**.</span></span>

4. <span data-ttu-id="2307e-126">Para agregar traducciones de la línea de asunto, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="2307e-126">To add translations of the subject line, follow these steps:</span></span>

    1. <span data-ttu-id="2307e-127">Haga clic en **Traducciones**.</span><span class="sxs-lookup"><span data-stu-id="2307e-127">Click **Translations**.</span></span>
    2. <span data-ttu-id="2307e-128">En la página que aparece, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="2307e-128">On the page that appears, click **Add**.</span></span>
    3. <span data-ttu-id="2307e-129">En la lista que aparece, seleccione el idioma en el que escribe el texto.</span><span class="sxs-lookup"><span data-stu-id="2307e-129">In the list that appears, select the language that you're entering the text in.</span></span>
    4. <span data-ttu-id="2307e-130">En el campo **Texto traducido**, escriba el texto.</span><span class="sxs-lookup"><span data-stu-id="2307e-130">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="2307e-131">Para personalizar el texto, puede insertar marcadores de posición como se describe en el paso 3.</span><span class="sxs-lookup"><span data-stu-id="2307e-131">To personalize the text, you can insert placeholders as described in step 3.</span></span>
    6. <span data-ttu-id="2307e-132">Haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="2307e-132">Click **Close**.</span></span>

5. <span data-ttu-id="2307e-133">En el campo **Instrucciones del elemento de trabajo**, escriba las instrucciones.</span><span class="sxs-lookup"><span data-stu-id="2307e-133">In the **Work item instructions** field, enter the instructions.</span></span>
6. <span data-ttu-id="2307e-134">Para personalizar las instrucciones, puede insertar marcadores de posición.</span><span class="sxs-lookup"><span data-stu-id="2307e-134">To personalize the instructions, you can insert placeholders.</span></span> <span data-ttu-id="2307e-135">Estos se reemplazan con los datos adecuados cuando las instrucciones se muestran a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="2307e-135">Placeholders are replaced with appropriate data when the instructions are shown to users.</span></span> <span data-ttu-id="2307e-136">Para insertar un marcador de posición, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="2307e-136">Follow these steps to insert a placeholder:</span></span>

    1. <span data-ttu-id="2307e-137">En el cuadro de texto, gaga clic para especificar dónde debe aparecer el marcador de posición.</span><span class="sxs-lookup"><span data-stu-id="2307e-137">In the text box, click where the placeholder should appear.</span></span>
    2. <span data-ttu-id="2307e-138">Haga clic en **Insertar marcador de posición**.</span><span class="sxs-lookup"><span data-stu-id="2307e-138">Click **Insert placeholder**.</span></span>
    3. <span data-ttu-id="2307e-139">En la lista que aparece, seleccione el marcador de posición que desea insertar.</span><span class="sxs-lookup"><span data-stu-id="2307e-139">In the list that appears, select the placeholder to insert.</span></span>
    4. <span data-ttu-id="2307e-140">Haga clic en **Insertar**.</span><span class="sxs-lookup"><span data-stu-id="2307e-140">Click **Insert**.</span></span>

7. <span data-ttu-id="2307e-141">Para agregar traducciones de las instrucciones, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="2307e-141">To add translations of the instructions, follow these steps:</span></span>

    1. <span data-ttu-id="2307e-142">Haga clic en **Traducciones**.</span><span class="sxs-lookup"><span data-stu-id="2307e-142">Click **Translations**.</span></span>
    2. <span data-ttu-id="2307e-143">En la página que aparece, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="2307e-143">On the page that appears, click **Add**.</span></span>
    3. <span data-ttu-id="2307e-144">En la lista que aparece, seleccione el idioma en el que escribe el texto.</span><span class="sxs-lookup"><span data-stu-id="2307e-144">In the list that appears, select the language that you're entering the text in.</span></span>
    4. <span data-ttu-id="2307e-145">En el campo **Texto traducido**, escriba el texto.</span><span class="sxs-lookup"><span data-stu-id="2307e-145">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="2307e-146">Para personalizar el texto, puede insertar marcadores de posición como se describe en el paso 6.</span><span class="sxs-lookup"><span data-stu-id="2307e-146">To personalize the text, you can insert placeholders as described in step 6.</span></span>
    6. <span data-ttu-id="2307e-147">Haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="2307e-147">Click **Close**.</span></span>

## <a name="specify-the-possible-outcomes-of-a-decision"></a><span data-ttu-id="2307e-148">Especificación de los posibles resultados de una decisión</span><span class="sxs-lookup"><span data-stu-id="2307e-148">Specify the possible outcomes of a decision</span></span>

<span data-ttu-id="2307e-149">Normalmente, cuando a una persona responsable de tomar decisiones se le asigna un documento, se le formula una pregunta.</span><span class="sxs-lookup"><span data-stu-id="2307e-149">Typically, when a document is assigned to a decision maker, the decision maker is asked a question.</span></span> <span data-ttu-id="2307e-150">La respuesta a esta pregunta es generalmente **Sí** o **No**, o bien **Verdadero** o **Falso**.</span><span class="sxs-lookup"><span data-stu-id="2307e-150">The answer to this question is usually **Yes** or **No**, or **True** or **False**.</span></span> <span data-ttu-id="2307e-151">Siga estos pasos para especificar los resultados que podría tener la decisión manual.</span><span class="sxs-lookup"><span data-stu-id="2307e-151">Follow these steps to specify the possible outcomes of the manual decision.</span></span>

1. <span data-ttu-id="2307e-152">En el panel izquierdo, haga clic en **Configuración básica**.</span><span class="sxs-lookup"><span data-stu-id="2307e-152">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="2307e-153">En la pestaña **Resultados**, en el campo **Resultado 1**, escriba el nombre del resultado o especifique la opción.</span><span class="sxs-lookup"><span data-stu-id="2307e-153">On the **Outcomes** tab, in the **Outcome 1** field, enter the name of the outcome, or the option.</span></span>
3. <span data-ttu-id="2307e-154">Para agregar traducciones del resultado, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="2307e-154">To add translations of the outcome, follow these steps:</span></span>

    1. <span data-ttu-id="2307e-155">Haga clic en **Traducciones**.</span><span class="sxs-lookup"><span data-stu-id="2307e-155">Click **Translations**.</span></span>
    2. <span data-ttu-id="2307e-156">En la página que aparece, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="2307e-156">On the page that appears, click **Add**.</span></span>
    3. <span data-ttu-id="2307e-157">En la lista que aparece, seleccione el idioma en el que escribe el texto.</span><span class="sxs-lookup"><span data-stu-id="2307e-157">In the list that appears, select the language that you're entering the text in.</span></span>
    4. <span data-ttu-id="2307e-158">En el campo **Texto traducido**, escriba el texto.</span><span class="sxs-lookup"><span data-stu-id="2307e-158">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="2307e-159">Haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="2307e-159">Click **Close**.</span></span>

4. <span data-ttu-id="2307e-160">En el campo **Resultado 2**, escriba el nombre del resultado o especifique la opción.</span><span class="sxs-lookup"><span data-stu-id="2307e-160">In the **Outcome 2** field, enter the name of the outcome, or the option.</span></span>
5. <span data-ttu-id="2307e-161">Para agregar traducciones del resultado, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="2307e-161">To add translations of the outcome, follow these steps:</span></span>

    1. <span data-ttu-id="2307e-162">Haga clic en **Traducciones**.</span><span class="sxs-lookup"><span data-stu-id="2307e-162">Click **Translations**.</span></span>
    2. <span data-ttu-id="2307e-163">En la página que aparece, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="2307e-163">On the page that appears, click **Add**.</span></span>
    3. <span data-ttu-id="2307e-164">En la lista que aparece, seleccione el idioma en el que escribe el texto.</span><span class="sxs-lookup"><span data-stu-id="2307e-164">In the list that appears, select the language that you're entering the text in.</span></span>
    4. <span data-ttu-id="2307e-165">En el campo **Texto traducido**, escriba el texto.</span><span class="sxs-lookup"><span data-stu-id="2307e-165">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="2307e-166">Haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="2307e-166">Click **Close**.</span></span>

## <a name="specify-when-notifications-are-sent"></a><span data-ttu-id="2307e-167">Especificación del momento en que se envían notificaciones</span><span class="sxs-lookup"><span data-stu-id="2307e-167">Specify when notifications are sent</span></span>

<span data-ttu-id="2307e-168">Puede enviar notificaciones cuando se haya tomado o delegado una decisión o cuando se la haya remitido a una instancia superior.</span><span class="sxs-lookup"><span data-stu-id="2307e-168">You can send notifications to people when a decision has been made, delegated, or escalated.</span></span> <span data-ttu-id="2307e-169">Siga estos pasos para especificar cuándo se deben enviar notificaciones y a quiénes se deben enviar.</span><span class="sxs-lookup"><span data-stu-id="2307e-169">Follow these steps to specify when notifications are sent, and who the notifications are sent to.</span></span>

1. <span data-ttu-id="2307e-170">En el panel izquierdo, haga clic en **Notificaciones**.</span><span class="sxs-lookup"><span data-stu-id="2307e-170">In the left pane, click **Notifications**.</span></span>
2. <span data-ttu-id="2307e-171">Active las casillas de verificación junto a los eventos que deben notificarse:</span><span class="sxs-lookup"><span data-stu-id="2307e-171">Select the check box next to the events that notifications should be sent for:</span></span>

    - <span data-ttu-id="2307e-172">**\[Elección 1\]**: el usuario asignado ha optado por la **\[Elección 1\]**.</span><span class="sxs-lookup"><span data-stu-id="2307e-172">**\[Choice 1\]** – The assigned user has selected **\[Choice 1\]**.</span></span>
    - <span data-ttu-id="2307e-173">**\[Elección 2\]**: el usuario asignado ha optado por la **\[Elección 2\]**.</span><span class="sxs-lookup"><span data-stu-id="2307e-173">**\[Choice 2\]** – The assigned user has selected **\[Choice 2\]**.</span></span>
    - <span data-ttu-id="2307e-174">**Delegar**: el usuario asignado ha asignado la decisión a otro usuario.</span><span class="sxs-lookup"><span data-stu-id="2307e-174">**Delegate** – The assigned user has assigned the decision to another user.</span></span>
    - <span data-ttu-id="2307e-175">**Remitir a una instancia superior**: el usuario asignado no ha tomado la decisión en el tiempo previsto.</span><span class="sxs-lookup"><span data-stu-id="2307e-175">**Escalate** – The assigned user hasn't made the decision in the allotted time.</span></span>

3. <span data-ttu-id="2307e-176">Seleccione la fila correspondiente a uno de los eventos que seleccionó en el paso 2.</span><span class="sxs-lookup"><span data-stu-id="2307e-176">Select the row for an event that you selected in step 2.</span></span>
4. <span data-ttu-id="2307e-177">En la pestaña **Texto de notificación**, en el cuadro de texto, escriba el texto de la notificación.</span><span class="sxs-lookup"><span data-stu-id="2307e-177">On the **Notification text** tab, in the text box, enter the text of the notification.</span></span>
5. <span data-ttu-id="2307e-178">Para personalizar la notificación, puede insertar marcadores de posición.</span><span class="sxs-lookup"><span data-stu-id="2307e-178">To personalize the notification, you can insert placeholders.</span></span> <span data-ttu-id="2307e-179">Estos se reemplazan con los datos adecuados cuando se muestra la notificación a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="2307e-179">Placeholders are replaced with appropriate data when the notification is show to users.</span></span> <span data-ttu-id="2307e-180">Para insertar un marcador de posición, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="2307e-180">Follow these steps to insert a placeholder:</span></span>

    1. <span data-ttu-id="2307e-181">En el cuadro de texto, gaga clic para especificar dónde debe aparecer el marcador de posición.</span><span class="sxs-lookup"><span data-stu-id="2307e-181">In the text box, click where the placeholder should appear.</span></span>
    2. <span data-ttu-id="2307e-182">Haga clic en **Insertar marcador de posición**.</span><span class="sxs-lookup"><span data-stu-id="2307e-182">Click **Insert placeholder**.</span></span>
    3. <span data-ttu-id="2307e-183">En la lista que aparece, seleccione el marcador de posición que desea insertar.</span><span class="sxs-lookup"><span data-stu-id="2307e-183">In the list that appears, select the placeholder to insert.</span></span>
    4. <span data-ttu-id="2307e-184">Haga clic en **Insertar**.</span><span class="sxs-lookup"><span data-stu-id="2307e-184">Click **Insert**.</span></span>

6. <span data-ttu-id="2307e-185">Para agregar traducciones de la notificación, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="2307e-185">To add translations of the notification, follow these steps:</span></span>

    1. <span data-ttu-id="2307e-186">Haga clic en **Traducciones**.</span><span class="sxs-lookup"><span data-stu-id="2307e-186">Click **Translations**.</span></span>
    2. <span data-ttu-id="2307e-187">En la página que aparece, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="2307e-187">On the page that appears, click **Add**.</span></span>
    3. <span data-ttu-id="2307e-188">En la lista que aparece, seleccione el idioma en el que escribe el texto.</span><span class="sxs-lookup"><span data-stu-id="2307e-188">In the list that appears, select the language that you're entering the text in.</span></span>
    4. <span data-ttu-id="2307e-189">En el campo **Texto traducido**, escriba el texto.</span><span class="sxs-lookup"><span data-stu-id="2307e-189">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="2307e-190">Para personalizar el texto, puede insertar marcadores de posición como se describe en el paso 5.</span><span class="sxs-lookup"><span data-stu-id="2307e-190">To personalize the text, you can insert placeholders as described in step 5.</span></span>
    6. <span data-ttu-id="2307e-191">Haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="2307e-191">Click **Close**.</span></span>

7. <span data-ttu-id="2307e-192">En la pestaña **Destinatario**, especifique a quién se envían las notificaciones.</span><span class="sxs-lookup"><span data-stu-id="2307e-192">On the **Recipient** tab, specify who the notifications are sent to.</span></span> <span data-ttu-id="2307e-193">Seleccione una de las opciones de la siguiente tabla y, a continuación, siga los pasos adicionales correspondientes a esa opción antes de realizar el paso 8.</span><span class="sxs-lookup"><span data-stu-id="2307e-193">Select one of the options in the following table, and then follow the additional steps for that option before you go to step 8.</span></span>

    <table>
    <thead>
    <tr>
    <th><span data-ttu-id="2307e-194">Opción</span><span class="sxs-lookup"><span data-stu-id="2307e-194">Option</span></span></th>
    <th><span data-ttu-id="2307e-195">Destinatarios de las notificaciones</span><span class="sxs-lookup"><span data-stu-id="2307e-195">Notification recipients</span></span></th>
    <th><span data-ttu-id="2307e-196">Pasos adicionales</span><span class="sxs-lookup"><span data-stu-id="2307e-196">Additional steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td><span data-ttu-id="2307e-197">Participante</span><span class="sxs-lookup"><span data-stu-id="2307e-197">Participant</span></span></td>
    <td><span data-ttu-id="2307e-198">Usuarios asignados a un grupo o rol específicos</span><span class="sxs-lookup"><span data-stu-id="2307e-198">Users who are assigned to a specific group or role</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="2307e-199">Tras seleccionar <strong>Participante</strong>, en la pestaña <strong>Basado en funciones</strong>, en la lista <strong>Tipo de participante</strong>, seleccione el tipo de grupo o rol al que desea enviar las notificaciones.</span><span class="sxs-lookup"><span data-stu-id="2307e-199">After you select <strong>Participant</strong>, on the <strong>Role based</strong> tab, in the <strong>Type of participant</strong> list, select the type of group or role to send notifications to.</span></span></li>
    <li><span data-ttu-id="2307e-200">En la lista <strong>Participante</strong>, seleccione el grupo al que se deben enviar las notificaciones.</span><span class="sxs-lookup"><span data-stu-id="2307e-200">In the <strong>Participant</strong> list, select the group or to send notifications to.</span></span></li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="2307e-201">Usuario del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="2307e-201">Workflow user</span></span></td>
    <td><span data-ttu-id="2307e-202">Usuarios del flujo de trabajo actual</span><span class="sxs-lookup"><span data-stu-id="2307e-202">Users in the current workflow</span></span></td>
    <td>
    <ul>
    <li><span data-ttu-id="2307e-203">Tras seleccionar <strong>Usuario del flujo de trabajo</strong>, en la pestaña <strong>Usuario del flujo de trabajo</strong>, en la pestaña <strong>Usuario del flujo de trabajo</strong>, seleccione un usuario que participe en el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="2307e-203">After you select <strong>Workflow user</strong>, on the <strong>Workflow user</strong> tab, in the <strong>Workflow user</strong> list, select a user who participates in the workflow.</span></span></li>
    </ul>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="2307e-204">Usuario</span><span class="sxs-lookup"><span data-stu-id="2307e-204">User</span></span></td>
    <td><span data-ttu-id="2307e-205">Usuarios concretos</span><span class="sxs-lookup"><span data-stu-id="2307e-205">Specific users</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="2307e-206">Tras seleccionar <strong>Usuario</strong>, haga clic en la pestaña <strong>Usuario</strong>.</span><span class="sxs-lookup"><span data-stu-id="2307e-206">After you select <strong>User</strong>, click the <strong>User</strong> tab.</span></span></li>
    <li><span data-ttu-id="2307e-207">La lista <strong>Usuarios disponibles</strong> incluye todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="2307e-207">The <strong>Available users</strong> list includes all users.</span></span> <span data-ttu-id="2307e-208">Seleccione aquellos a los que desea enviar notificaciones y, a continuación, muévalos a la lista <strong>Usuarios seleccionados</strong>.</span><span class="sxs-lookup"><span data-stu-id="2307e-208">Select the users to send notifications to, and then move those users to the <strong>Selected users</strong> list.</span></span></li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

8. <span data-ttu-id="2307e-209">Repita los pasos 3 a 7 por cada uno de los eventos que haya seleccionado en el paso 2.</span><span class="sxs-lookup"><span data-stu-id="2307e-209">Repeat steps 3 through 7 for each event that you selected in step 2.</span></span>

## <a name="assign-a-decision"></a><span data-ttu-id="2307e-210">Asignación de una decisión</span><span class="sxs-lookup"><span data-stu-id="2307e-210">Assign a decision</span></span>

<span data-ttu-id="2307e-211">Siga estos pasos para especificar a quién se debe asignar una decisión manual.</span><span class="sxs-lookup"><span data-stu-id="2307e-211">Follow these steps to specify who a manual decision should be assigned to.</span></span>

1. <span data-ttu-id="2307e-212">En el panel izquierdo, haga clic en **Asignación**.</span><span class="sxs-lookup"><span data-stu-id="2307e-212">In the left pane, click **Assignment**.</span></span>
2. <span data-ttu-id="2307e-213">En la pestaña **Tipo de asignación**, seleccione una de las opciones de la siguiente tabla. A continuación, siga los pasos adicionales correspondientes a la opción elegida antes de realizar el paso 3.</span><span class="sxs-lookup"><span data-stu-id="2307e-213">On the **Assignment type** tab, select one of the options in the following table, and then follow the additional steps for that option before you go to step 3.</span></span>

    <table>
    <thead>
    <tr>
    <th><span data-ttu-id="2307e-214">Opción</span><span class="sxs-lookup"><span data-stu-id="2307e-214">Option</span></span></th>
    <th><span data-ttu-id="2307e-215">Usuarios a los que se asigna la decisión</span><span class="sxs-lookup"><span data-stu-id="2307e-215">Users that the decision is assigned to</span></span></th>
    <th><span data-ttu-id="2307e-216">Pasos adicionales</span><span class="sxs-lookup"><span data-stu-id="2307e-216">Additional steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td><span data-ttu-id="2307e-217">Participante</span><span class="sxs-lookup"><span data-stu-id="2307e-217">Participant</span></span></td>
    <td><span data-ttu-id="2307e-218">Usuarios asignados a un grupo o rol específicos</span><span class="sxs-lookup"><span data-stu-id="2307e-218">Users who are assigned to a specific group or role</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="2307e-219">Tras seleccionar <strong>Participante</strong>, en la pestaña <strong>Basado en funciones</strong>, en la lista <strong>Tipo de participante</strong>, seleccione el tipo de grupo o rol al que desea asignar la decisión.</span><span class="sxs-lookup"><span data-stu-id="2307e-219">After you select <strong>Participant</strong>, on the <strong>Role based</strong> tab, in the <strong>Type of participant</strong> list, select the type of group or role to assign the decision to.</span></span></li>
    <li><span data-ttu-id="2307e-220">En la lista <strong>Participante</strong>, seleccione el grupo o rol al que se debe asignar la decisión.</span><span class="sxs-lookup"><span data-stu-id="2307e-220">In the <strong>Participant</strong> list, select the group or role to assign the decision to.</span></span></li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="2307e-221">Jerarquía</span><span class="sxs-lookup"><span data-stu-id="2307e-221">Hierarchy</span></span></td>
    <td><span data-ttu-id="2307e-222">Usuarios de una jerarquía organizativa específica</span><span class="sxs-lookup"><span data-stu-id="2307e-222">Users in a specific organizational hierarchy</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="2307e-223">Tras seleccionar <strong>Jerarquía</strong>, en la pestaña <strong>Selección de jerarquía</strong>, en la lista <strong>Tipo de jerarquía</strong>, seleccione el tipo de jerarquía al que desea asignar la decisión.</span><span class="sxs-lookup"><span data-stu-id="2307e-223">After you select <strong>Hierarchy</strong>, on the <strong>Hierarchy selection</strong> tab, in the <strong>Hierarchy type</strong> list, select the type of hierarchy to assign the decision to.</span></span></li>
    <li><span data-ttu-id="2307e-224">El sistema debe recuperar un intervalo de nombres de usuario de la jerarquía.</span><span class="sxs-lookup"><span data-stu-id="2307e-224">The system must retrieve a range of user names from the hierarchy.</span></span> <span data-ttu-id="2307e-225">Dichos nombres representan a los usuarios a los que se puede asignar la decisión.</span><span class="sxs-lookup"><span data-stu-id="2307e-225">These names represent users that the decision can be assigned to.</span></span> <span data-ttu-id="2307e-226">Siga estos pasos para especificar el punto de inicio y de finalización del intervalo de nombres de usuario que el sistema recupera:</span><span class="sxs-lookup"><span data-stu-id="2307e-226">Follow these steps to specify the starting point and ending point of the range of user names that the system retrieves:</span></span> <ol>
    <li><span data-ttu-id="2307e-227">Para especificar el punto de inicio, seleccione una persona en la lista <strong>Comenzar desde</strong>.</span><span class="sxs-lookup"><span data-stu-id="2307e-227">To specify the starting point, select a person in the <strong>Start from</strong> list.</span></span></li>
    <li><span data-ttu-id="2307e-228">Para especificar el punto de finalización, haga clic en <strong>Agregar condición</strong>.</span><span class="sxs-lookup"><span data-stu-id="2307e-228">To specify the ending point, click <strong>Add condition</strong>.</span></span> <span data-ttu-id="2307e-229">A continuación, especifique una condición que determine en qué parte de la jerarquía el sistema dejará de recuperar nombres.</span><span class="sxs-lookup"><span data-stu-id="2307e-229">Then enter a condition that determines where in the hierarchy the system stops retrieving names.</span></span></li>
    </ol>
    </li>
    <li><span data-ttu-id="2307e-230">En la pestaña <strong>Opciones de jerarquía</strong>, especifique a qué usuarios del intervalo se debe asignar la decisión:</span><span class="sxs-lookup"><span data-stu-id="2307e-230">On the <strong>Hierarchy options</strong> tab, specify which users in the range the decision should be assigned to:</span></span> <ul>
    <li><span data-ttu-id="2307e-231"><strong>Asignar a todos los usuarios recuperados</strong>: la decisión se asigna a todos los usuarios del intervalo.</span><span class="sxs-lookup"><span data-stu-id="2307e-231"><strong>Assign to all users retrieved</strong> – The decision is assigned to all users in the range.</span></span></li>
    <li><span data-ttu-id="2307e-232"><strong>Asignar sólo al último usuario recuperado</strong>: la decisión se asigna únicamente al último usuario del intervalo.</span><span class="sxs-lookup"><span data-stu-id="2307e-232"><strong>Assign only to last user retrieved</strong> – The decision is assigned to only the last user in the range.</span></span></li>
    <li><span data-ttu-id="2307e-233"><strong>Excluir usuarios con la siguiente condición</strong>: la decisión no se asigna a ninguno de los usuarios del intervalo que cumplen con una condición determinada.</span><span class="sxs-lookup"><span data-stu-id="2307e-233"><strong>Exclude users with the following condition</strong> – The decision isn't assigned to any users in the range who meet a specific condition.</span></span> <span data-ttu-id="2307e-234">Haga clic en <strong>Agregar condición</strong> para especificar la condición.</span><span class="sxs-lookup"><span data-stu-id="2307e-234">Click <strong>Add condition</strong> to specify the condition.</span></span></li>
    </ul>
    </li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="2307e-235">Usuario del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="2307e-235">Workflow user</span></span></td>
    <td><span data-ttu-id="2307e-236">Usuarios del flujo de trabajo actual</span><span class="sxs-lookup"><span data-stu-id="2307e-236">Users in the current workflow</span></span></td>
    <td>
    <ul>
    <li><span data-ttu-id="2307e-237">Tras seleccionar <strong>Usuario del flujo de trabajo</strong>, en la pestaña <strong>Usuario del flujo de trabajo</strong>, en la pestaña <strong>Usuario del flujo de trabajo</strong>, seleccione un usuario que participe en el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="2307e-237">After you select <strong>Workflow user</strong>, on the <strong>Workflow user</strong> tab, in the <strong>Workflow user</strong> list, select a user who participates in the workflow.</span></span></li>
    </ul>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="2307e-238">Usuario</span><span class="sxs-lookup"><span data-stu-id="2307e-238">User</span></span></td>
    <td><span data-ttu-id="2307e-239">Usuarios concretos</span><span class="sxs-lookup"><span data-stu-id="2307e-239">Specific users</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="2307e-240">Tras seleccionar <strong>Usuario</strong>, haga clic en la pestaña <strong>Usuario</strong>.</span><span class="sxs-lookup"><span data-stu-id="2307e-240">After you select <strong>User</strong>, click the <strong>User</strong> tab.</span></span></li>
    <li><span data-ttu-id="2307e-241">La lista <strong>Usuarios disponibles</strong> incluye todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="2307e-241">The <strong>Available users</strong> list includes all users.</span></span> <span data-ttu-id="2307e-242">Seleccione aquellos a los que desea asignar la decisión y, a continuación, muévalos a la lista <strong>Usuarios seleccionados</strong>.</span><span class="sxs-lookup"><span data-stu-id="2307e-242">Select the users to assign the decision to, and then move those users to the <strong>Selected users</strong> list.</span></span></li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

3. <span data-ttu-id="2307e-243">En la pestaña **Límite de tiempo**, en el campo **Duración**, especifique el tiempo del que dispone el usuario para tomar la decisión.</span><span class="sxs-lookup"><span data-stu-id="2307e-243">On the **Time limit** tab, in the **Duration** field, specify how much time the user has to make the decision.</span></span> <span data-ttu-id="2307e-244">Seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="2307e-244">Select one of the following options:</span></span>

    - <span data-ttu-id="2307e-245">**Horas**: escriba la cantidad de horas de las que dispone el usuario para tomar la decisión.</span><span class="sxs-lookup"><span data-stu-id="2307e-245">**Hours** – Enter the number of hours that the user has to make the decision.</span></span> <span data-ttu-id="2307e-246">A continuación, seleccione el calendario que usa la organización y escriba la información pertinente acerca de la semana laboral de la organización.</span><span class="sxs-lookup"><span data-stu-id="2307e-246">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="2307e-247">**Días**: escriba la cantidad de días de los que dispone el usuario para tomar la decisión.</span><span class="sxs-lookup"><span data-stu-id="2307e-247">**Days** – Enter the number of days that the user has to make the decision.</span></span> <span data-ttu-id="2307e-248">A continuación, seleccione el calendario que usa la organización y escriba la información pertinente acerca de la semana laboral de la organización.</span><span class="sxs-lookup"><span data-stu-id="2307e-248">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="2307e-249">**Semanas**: escriba la cantidad de semanas de las que dispone el usuario para tomar la decisión.</span><span class="sxs-lookup"><span data-stu-id="2307e-249">**Weeks** – Enter the number of weeks that the user has to make the decision.</span></span>
    - <span data-ttu-id="2307e-250">**Meses**: seleccione el día y la semana antes de los cuales el usuario debe tomar la decisión.</span><span class="sxs-lookup"><span data-stu-id="2307e-250">**Months** – Select the day and week that the user must make the decision by.</span></span> <span data-ttu-id="2307e-251">Por ejemplo, tal vez desee que el usuario haya tomado la decisión antes del viernes de la tercera semana del mes.</span><span class="sxs-lookup"><span data-stu-id="2307e-251">For example, you might want the user to make the decision by Friday of the third week of the month.</span></span>
    - <span data-ttu-id="2307e-252">**Años**: seleccione el día, la semana y el mes en los que vence el plazo para tomar la decisión.</span><span class="sxs-lookup"><span data-stu-id="2307e-252">**Years** – Select the day, week, and month that the user must make the decision by.</span></span> <span data-ttu-id="2307e-253">Por ejemplo, tal vez desee que el usuario haya tomado la decisión antes del viernes de la tercera semana de diciembre.</span><span class="sxs-lookup"><span data-stu-id="2307e-253">For example, you might want the user to make the decision by Friday of the third week of December.</span></span>

    <span data-ttu-id="2307e-254">Si el usuario no toma la decisión en el tiempo asignado, la decisión se considera vencida.</span><span class="sxs-lookup"><span data-stu-id="2307e-254">If the user doesn't make the decision in the allotted time, the decision is overdue.</span></span> <span data-ttu-id="2307e-255">Las decisiones vencidas se remiten a una instancia superior en función de las opciones que se seleccionen en el área **Remisión a una instancia superior** de la página.</span><span class="sxs-lookup"><span data-stu-id="2307e-255">A decision that is overdue is escalated, based on the options that you select in the **Escalation** area of the page.</span></span>

## <a name="specify-what-happens-when-a-decision-is-overdue"></a><span data-ttu-id="2307e-256">Especificación de la acción que se realiza cuando vence una decisión</span><span class="sxs-lookup"><span data-stu-id="2307e-256">Specify what happens when a decision is overdue</span></span>

<span data-ttu-id="2307e-257">Si un usuario no toma la decisión en el tiempo asignado, la decisión se considera vencida.</span><span class="sxs-lookup"><span data-stu-id="2307e-257">If a user doesn't make the decision in the allotted time, the decision is overdue.</span></span> <span data-ttu-id="2307e-258">Las decisiones vencidas se pueden remitir a una instancia superior, o asignar a otro usuario de forma automática.</span><span class="sxs-lookup"><span data-stu-id="2307e-258">A decision that is overdue can be escalated, or automatically assigned to another user.</span></span> <span data-ttu-id="2307e-259">Si la decisión ha vencido, siga estos pasos para remitirla a una instancia superior.</span><span class="sxs-lookup"><span data-stu-id="2307e-259">Follow these steps to escalate the decision if it's overdue.</span></span>

1. <span data-ttu-id="2307e-260">En el panel izquierdo, haga clic en **Remisión a una instancia superior**.</span><span class="sxs-lookup"><span data-stu-id="2307e-260">In the left pane, click **Escalation**.</span></span>
2. <span data-ttu-id="2307e-261">Active la casilla de verificación **Usar ruta de remisión a una instancia superior** para crear una ruta de remisión a una instancia superior.</span><span class="sxs-lookup"><span data-stu-id="2307e-261">Select the **Use escalation path** check box to create an escalation path.</span></span> <span data-ttu-id="2307e-262">De manera automática, el sistema asigna la decisión a los usuarios que forman parte de la ruta de remisión a una instancia superior.</span><span class="sxs-lookup"><span data-stu-id="2307e-262">The system automatically assigns the decision to the users who are listed in the escalation path.</span></span> <span data-ttu-id="2307e-263">La siguiente tabla, por ejemplo, representa una ruta de remisión a una instancia superior.</span><span class="sxs-lookup"><span data-stu-id="2307e-263">For example, the following table represents an escalation path.</span></span>

    | <span data-ttu-id="2307e-264">Secuencia</span><span class="sxs-lookup"><span data-stu-id="2307e-264">Sequence</span></span> | <span data-ttu-id="2307e-265">Ruta de remisión a una instancia superior</span><span class="sxs-lookup"><span data-stu-id="2307e-265">Escalation path</span></span>            |
    |----------|----------------------------|
    | <span data-ttu-id="2307e-266">1</span><span class="sxs-lookup"><span data-stu-id="2307e-266">1</span></span>        | <span data-ttu-id="2307e-267">Asignar a rol: Donna</span><span class="sxs-lookup"><span data-stu-id="2307e-267">Assign to: Donna</span></span>           |
    | <span data-ttu-id="2307e-268">2</span><span class="sxs-lookup"><span data-stu-id="2307e-268">2</span></span>        | <span data-ttu-id="2307e-269">Asignar a rol: Erin</span><span class="sxs-lookup"><span data-stu-id="2307e-269">Assign to: Erin</span></span>            |
    | <span data-ttu-id="2307e-270">3</span><span class="sxs-lookup"><span data-stu-id="2307e-270">3</span></span>        | <span data-ttu-id="2307e-271">Acción final: \[Elección 1\]</span><span class="sxs-lookup"><span data-stu-id="2307e-271">Final action: \[Choice 1\]</span></span> |

    <span data-ttu-id="2307e-272">En este ejemplo, el sistema asigna la decisión vencida a Donna.</span><span class="sxs-lookup"><span data-stu-id="2307e-272">In this example, the system assigns the overdue decision to Donna.</span></span> <span data-ttu-id="2307e-273">Si Donna no toma la decisión en el tiempo asignado, el sistema la asigna a Erin.</span><span class="sxs-lookup"><span data-stu-id="2307e-273">If Donna doesn't make the decision in the allotted time, the system assigns the decision to Erin.</span></span> <span data-ttu-id="2307e-274">Si Erin no toma la decisión en el tiempo asignado, el sistema selecciona la **\[Elección 1\]** como decisión.</span><span class="sxs-lookup"><span data-stu-id="2307e-274">If Erin doesn't make the decision in the allotted time, the system selects **\[Choice 1\]** as the decision.</span></span>

3. <span data-ttu-id="2307e-275">Para agregar un usuario a la ruta de remisión a una instancia superior, haga clic en **Agregar remisión a una instancia superior**.</span><span class="sxs-lookup"><span data-stu-id="2307e-275">To add a user to the escalation path, click **Add escalation**.</span></span> <span data-ttu-id="2307e-276">Seleccione una de las opciones de la siguiente tabla y, a continuación, siga los pasos adicionales correspondientes a esa opción antes de realizar el paso 4.</span><span class="sxs-lookup"><span data-stu-id="2307e-276">Select one of the options in the following table, and then follow the additional steps for that option before you go to step 4.</span></span>

    <table>
    <thead>
    <tr>
    <th><span data-ttu-id="2307e-277">Opción</span><span class="sxs-lookup"><span data-stu-id="2307e-277">Option</span></span></th>
    <th><span data-ttu-id="2307e-278">Usuarios a los que se remite la decisión</span><span class="sxs-lookup"><span data-stu-id="2307e-278">Users that the decision is escalated to</span></span></th>
    <th><span data-ttu-id="2307e-279">Pasos adicionales</span><span class="sxs-lookup"><span data-stu-id="2307e-279">Additional steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td><span data-ttu-id="2307e-280">Jerarquía</span><span class="sxs-lookup"><span data-stu-id="2307e-280">Hierarchy</span></span></td>
    <td><span data-ttu-id="2307e-281">Usuarios de una jerarquía organizativa específica</span><span class="sxs-lookup"><span data-stu-id="2307e-281">Users in a specific organizational hierarchy</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="2307e-282">Tras seleccionar <strong>Jerarquía</strong>, en la pestaña <strong>Selección de jerarquía</strong>, en la lista <strong>Tipo de jerarquía</strong>, seleccione el tipo de jerarquía al que desea remitir a una instancia superior la decisión.</span><span class="sxs-lookup"><span data-stu-id="2307e-282">After you select <strong>Hierarchy</strong>, on the <strong>Hierarchy selection</strong> tab, in the <strong>Hierarchy type</strong> list, select the type of hierarchy to escalate the decision to.</span></span></li>
    <li><span data-ttu-id="2307e-283">El sistema debe recuperar un intervalo de nombres de usuario de la jerarquía.</span><span class="sxs-lookup"><span data-stu-id="2307e-283">The system must retrieve a range of user names from the hierarchy.</span></span> <span data-ttu-id="2307e-284">Dichos nombres representan a los usuarios a los que se puede remitir la decisión para una instancia superior.</span><span class="sxs-lookup"><span data-stu-id="2307e-284">These names represent users that the decision can be escalated to.</span></span> <span data-ttu-id="2307e-285">Siga estos pasos para especificar el punto de inicio y de finalización del intervalo de nombres de usuario que el sistema recupera:</span><span class="sxs-lookup"><span data-stu-id="2307e-285">Follow these steps to specify the starting point and ending point of the range of user names that the system retrieves:</span></span> <ol>
    <li><span data-ttu-id="2307e-286">Para especificar el punto de inicio, seleccione una persona en la lista <strong>Comenzar desde</strong>.</span><span class="sxs-lookup"><span data-stu-id="2307e-286">To specify the starting point, select a person in the <strong>Start from</strong> list.</span></span></li>
    <li><span data-ttu-id="2307e-287">Para especificar el punto de finalización, haga clic en <strong>Agregar condición</strong>.</span><span class="sxs-lookup"><span data-stu-id="2307e-287">To specify the ending point, click <strong>Add condition</strong>.</span></span> <span data-ttu-id="2307e-288">A continuación, especifique una condición que determine en qué parte de la jerarquía el sistema dejará de recuperar nombres.</span><span class="sxs-lookup"><span data-stu-id="2307e-288">Then enter a condition that determines where in the hierarchy the system stops retrieving names.</span></span></li>
    </ol>
    </li>
    <li><span data-ttu-id="2307e-289">En la pestaña <strong>Opciones de jerarquía</strong>, especifique a qué usuarios del intervalo se debe remitir la decisión para una instancia superior:</span><span class="sxs-lookup"><span data-stu-id="2307e-289">On the <strong>Hierarchy options</strong> tab, specify which users in the range the decision should be escalated to:</span></span> <ul>
    <li><span data-ttu-id="2307e-290"><strong>Asignar a todos los usuarios recuperados</strong>: la decisión se remite para una instancia superior a todos los usuarios del intervalo.</span><span class="sxs-lookup"><span data-stu-id="2307e-290"><strong>Assign to all users retrieved</strong> – The decision is escalated to all users in the range.</span></span></li>
    <li><span data-ttu-id="2307e-291"><strong>Asignar sólo al último usuario recuperado</strong>: la decisión se remite para una instancia superior únicamente al último usuario del intervalo.</span><span class="sxs-lookup"><span data-stu-id="2307e-291"><strong>Assign only to last user retrieved</strong> – The decision is escalated to only the last user in the range.</span></span></li>
    <li><span data-ttu-id="2307e-292"><strong>Excluir usuarios con la siguiente condición</strong>: la decisión no se remite para una instancia superior a ninguno de los usuarios del intervalo que cumplen con una condición determinada.</span><span class="sxs-lookup"><span data-stu-id="2307e-292"><strong>Exclude users with the following condition:</strong> – The decision isn't escalated to any users in the range who meet a specific condition.</span></span> <span data-ttu-id="2307e-293">Haga clic en <strong>Agregar condición</strong> para especificar la condición.</span><span class="sxs-lookup"><span data-stu-id="2307e-293">Click <strong>Add condition</strong> to specify the condition.</span></span></li>
    </ul>
    </li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="2307e-294">Usuario del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="2307e-294">Workflow user</span></span></td>
    <td><span data-ttu-id="2307e-295">Usuarios del flujo de trabajo actual</span><span class="sxs-lookup"><span data-stu-id="2307e-295">Users in the current workflow</span></span></td>
    <td>
    <ul>
    <li><span data-ttu-id="2307e-296">Tras seleccionar <strong>Usuario del flujo de trabajo</strong>, en la pestaña <strong>Usuario del flujo de trabajo</strong>, en la pestaña <strong>Usuario del flujo de trabajo</strong>, seleccione un usuario que participe en el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="2307e-296">After you select <strong>Workflow user</strong>, on the <strong>Workflow user</strong> tab, in the <strong>Workflow user</strong> list, select a user who participates in the workflow.</span></span></li>
    </ul>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="2307e-297">Usuario</span><span class="sxs-lookup"><span data-stu-id="2307e-297">User</span></span></td>
    <td><span data-ttu-id="2307e-298">Usuarios concretos</span><span class="sxs-lookup"><span data-stu-id="2307e-298">Specific users</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="2307e-299">Tras seleccionar <strong>Usuario</strong>, haga clic en la pestaña <strong>Usuario</strong>.</span><span class="sxs-lookup"><span data-stu-id="2307e-299">After you select <strong>User</strong>, click the <strong>User</strong> tab.</span></span></li>
    <li><span data-ttu-id="2307e-300">La lista <strong>Usuarios disponibles</strong> incluye todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="2307e-300">The <strong>Available users</strong> list includes all users.</span></span> <span data-ttu-id="2307e-301">Seleccione aquellos a los que desea remitir la decisión para una instancia superior y, a continuación, muévalos a la lista <strong>Usuarios seleccionados</strong>.</span><span class="sxs-lookup"><span data-stu-id="2307e-301">Select the users to escalate the decision to, and then move those users to the <strong>Selected users</strong> list.</span></span></li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

4. <span data-ttu-id="2307e-302">En la pestaña **Límite de tiempo**, en el campo **Duración**, especifique el tiempo del que dispone el usuario para tomar la decisión.</span><span class="sxs-lookup"><span data-stu-id="2307e-302">On the **Time limit** tab, in the **Duration** field, specify how much time the user has to make the decision.</span></span> <span data-ttu-id="2307e-303">Seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="2307e-303">Select one of the following options:</span></span>

    - <span data-ttu-id="2307e-304">**Horas**: escriba la cantidad de horas de las que dispone el usuario para tomar la decisión.</span><span class="sxs-lookup"><span data-stu-id="2307e-304">**Hours** – Enter the number of hours that the user has to make the decision.</span></span> <span data-ttu-id="2307e-305">A continuación, seleccione el calendario que usa la organización y escriba la información pertinente acerca de la semana laboral de la organización.</span><span class="sxs-lookup"><span data-stu-id="2307e-305">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="2307e-306">**Días**: escriba la cantidad de días de los que dispone el usuario para tomar la decisión.</span><span class="sxs-lookup"><span data-stu-id="2307e-306">**Days** – Enter the number of days that the user has to make the decision.</span></span> <span data-ttu-id="2307e-307">A continuación, seleccione el calendario que usa la organización y escriba la información pertinente acerca de la semana laboral de la organización.</span><span class="sxs-lookup"><span data-stu-id="2307e-307">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="2307e-308">**Semanas**: escriba la cantidad de semanas de las que dispone el usuario para tomar la decisión.</span><span class="sxs-lookup"><span data-stu-id="2307e-308">**Weeks** – Enter the number of weeks that the user has to make the decision.</span></span>
    - <span data-ttu-id="2307e-309">**Meses**: seleccione el día y la semana antes de los cuales el usuario debe tomar la decisión.</span><span class="sxs-lookup"><span data-stu-id="2307e-309">**Months** – Select the day and week that the user must make the decision by.</span></span> <span data-ttu-id="2307e-310">Por ejemplo, tal vez desee que el usuario haya tomado la decisión antes del viernes de la tercera semana del mes.</span><span class="sxs-lookup"><span data-stu-id="2307e-310">For example, you might want the user to make the decision by Friday of the third week of the month.</span></span>
    - <span data-ttu-id="2307e-311">**Años**: seleccione el día, la semana y el mes en los que vence el plazo para tomar la decisión.</span><span class="sxs-lookup"><span data-stu-id="2307e-311">**Years** – Select the day, week, and month that the user must make the decision by.</span></span> <span data-ttu-id="2307e-312">Por ejemplo, tal vez desee que el usuario haya tomado la decisión antes del viernes de la tercera semana de diciembre.</span><span class="sxs-lookup"><span data-stu-id="2307e-312">For example, you might want the user to make the decision by Friday of the third week of December.</span></span>

5. <span data-ttu-id="2307e-313">Repita los pasos 3 a 4 por cada usuario que se debe agregar a la ruta de remisión a una instancia superior.</span><span class="sxs-lookup"><span data-stu-id="2307e-313">Repeat steps 3 through 4 for each user that should be added to the escalation path.</span></span> <span data-ttu-id="2307e-314">El orden de los usuarios se puede modificar.</span><span class="sxs-lookup"><span data-stu-id="2307e-314">You can change the order of the users.</span></span>
6. <span data-ttu-id="2307e-315">Si los usuarios de la ruta de remisión a una instancia superior no toman la decisión en el tiempo asignado, lo hace el sistema.</span><span class="sxs-lookup"><span data-stu-id="2307e-315">If the users in the escalation path don't make the decision in the allotted time, the system makes the decision.</span></span> <span data-ttu-id="2307e-316">Para especificar la opción que el sistema selecciona, seleccione la fila **Acción** y, a continuación, en la pestaña **Finalizar acción**, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="2307e-316">To specify the option that the system selects, select the **Action** row, and then, on the **End action** tab, select an option.</span></span>

## <a name="set-a-time-limit"></a><span data-ttu-id="2307e-317">Definición de un límite de tiempo</span><span class="sxs-lookup"><span data-stu-id="2307e-317">Set a time limit</span></span>

<span data-ttu-id="2307e-318">Siga estos pasos si la decisión se debe tomar en un plazo específico.</span><span class="sxs-lookup"><span data-stu-id="2307e-318">Follow these steps if the decision must be made in a specific time.</span></span>

> [!NOTE]
> <span data-ttu-id="2307e-319">Las opciones que seleccione en este procedimiento anulan las opciones elegidas en las áreas **Asignación** y **Remisión** a una instancia superior de la página.</span><span class="sxs-lookup"><span data-stu-id="2307e-319">The options that you select in this procedure override the options that you selected in the **Assignment** and **Escalation** areas of the page.</span></span>

1. <span data-ttu-id="2307e-320">En el panel izquiero, haga clic en **Configuración avanzada**.</span><span class="sxs-lookup"><span data-stu-id="2307e-320">In the left pane, click **Advanced settings**.</span></span>
2. <span data-ttu-id="2307e-321">Active la casilla **Configurar un límite de tiempo para el elemento de flujo de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="2307e-321">Select the **Set a time limit for the workflow element** check box.</span></span>
3. <span data-ttu-id="2307e-322">En el campo **Duración**, especifique cuándo se debe tomar la decisión.</span><span class="sxs-lookup"><span data-stu-id="2307e-322">In the **Duration** field, specify when the decision must be made.</span></span> <span data-ttu-id="2307e-323">Seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="2307e-323">Select one of the following options:</span></span>

    - <span data-ttu-id="2307e-324">**Hora**: escriba la cantidad de horas.</span><span class="sxs-lookup"><span data-stu-id="2307e-324">**Hours** – Enter the number of hours.</span></span> <span data-ttu-id="2307e-325">A continuación, seleccione el calendario que usa la organización y escriba la información pertinente acerca de la semana laboral de la organización.</span><span class="sxs-lookup"><span data-stu-id="2307e-325">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="2307e-326">**Días**: escriba la cantidad de días.</span><span class="sxs-lookup"><span data-stu-id="2307e-326">**Days** – Enter the number of days.</span></span> <span data-ttu-id="2307e-327">A continuación, seleccione el calendario que usa la organización y escriba la información pertinente acerca de la semana laboral de la organización.</span><span class="sxs-lookup"><span data-stu-id="2307e-327">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    - <span data-ttu-id="2307e-328">**Semanas**: escriba la cantidad de semanas.</span><span class="sxs-lookup"><span data-stu-id="2307e-328">**Weeks** – Enter the number of weeks.</span></span>
    - <span data-ttu-id="2307e-329">**Meses**: seleccione el día y la semana en los que vence el plazo para tomar la decisión.</span><span class="sxs-lookup"><span data-stu-id="2307e-329">**Months** – Select the day and week that the decision must be made by.</span></span> <span data-ttu-id="2307e-330">Por ejemplo, tal vez desee que la decisión se haya tomado antes del viernes de la tercera semana del mes.</span><span class="sxs-lookup"><span data-stu-id="2307e-330">For example, you might want the decision to be made by Friday of the third week of the month.</span></span>
    - <span data-ttu-id="2307e-331">**Años**: seleccione el día, la semana y el mes en los que vence el plazo para tomar la decisión.</span><span class="sxs-lookup"><span data-stu-id="2307e-331">**Years** – Select the day, week, and month that the decision must be made by.</span></span> <span data-ttu-id="2307e-332">Por ejemplo, tal vez desee que la decisión se haya tomado antes del viernes de la tercera semana de diciembre.</span><span class="sxs-lookup"><span data-stu-id="2307e-332">For example, you might want the decision to be made by Friday of the third week of December.</span></span>

4. <span data-ttu-id="2307e-333">Si se supera el límite de tiempo, el sistema toma la decisión.</span><span class="sxs-lookup"><span data-stu-id="2307e-333">If the time limit is exceeded, the system makes the decision.</span></span> <span data-ttu-id="2307e-334">En la lista **Acción**, seleccione la opción que debe seleccionar el sistema.</span><span class="sxs-lookup"><span data-stu-id="2307e-334">In the **Action** list, select the option that the system should select.</span></span>
