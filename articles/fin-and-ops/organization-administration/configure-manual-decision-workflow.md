---
title: "Configuración de una decisión manual en un flujo de trabajo"
description: "Este tema explica cómo configurar las propiedades de una decisión manual."
author: sericks007
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 192101
ms.assetid: 0bccad77-1a44-4f08-967b-12c62c02afc7
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 078d7d5e822a5ffa74131838b249563201b54c7f
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---

# <a name="configure-a-manual-decision-in-a-workflow"></a><span data-ttu-id="ec601-103">Configuración de una decisión manual en un flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="ec601-103">Configure a manual decision in a workflow</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="ec601-104">Este tema explica cómo configurar las propiedades de una decisión manual.</span><span class="sxs-lookup"><span data-stu-id="ec601-104">This topic explains how to configure the properties of a manual decision.</span></span>

<span data-ttu-id="ec601-105">Para configurar una decisión manual, en el editor de flujo de trabajo, haga clic con el botón secundario en la decisión manual y, a continuación, haga clic en **Propiedades** para abrir la página **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="ec601-105">To configure a manual decision in the workflow editor, right-click the manual decision, and then click **Properties** to open the **Properties** page.</span></span> <span data-ttu-id="ec601-106">A continuación, use los siguientes procedimientos para configurar las propiedades de la decisión manual.</span><span class="sxs-lookup"><span data-stu-id="ec601-106">Then use the following procedures to configure the properties of the manual decision.</span></span>

## <a name="name-the-decision"></a><span data-ttu-id="ec601-107">Asignación de un nombre a la decisión</span><span class="sxs-lookup"><span data-stu-id="ec601-107">Name the decision</span></span>
<span data-ttu-id="ec601-108">Siga estos pasos para asignar un nombre a la decisión manual.</span><span class="sxs-lookup"><span data-stu-id="ec601-108">Follow these steps to enter a name for the manual decision.</span></span>

1.  <span data-ttu-id="ec601-109">En el panel izquierdo, haga clic en **Configuración básica**.</span><span class="sxs-lookup"><span data-stu-id="ec601-109">In the left pane, click **Basic Settings**.</span></span>
2.  <span data-ttu-id="ec601-110">En el campo **Nombre**, escriba un nombre único para la decisión manual.</span><span class="sxs-lookup"><span data-stu-id="ec601-110">In the **Name** field, enter a unique name for the manual decision.</span></span>

## <a name="enter-a-subject-line-and-instructions"></a><span data-ttu-id="ec601-111">Especificación de una línea de asunto e instrucciones</span><span class="sxs-lookup"><span data-stu-id="ec601-111">Enter a subject line and instructions</span></span>
<span data-ttu-id="ec601-112">Debe proporcionar una línea de asunto e instrucciones a los usuarios que están asignados a la decisión manual.</span><span class="sxs-lookup"><span data-stu-id="ec601-112">You must provide a subject line and instructions to users who are assigned to the manual decision.</span></span> <span data-ttu-id="ec601-113">Por ejemplo, si está configurando una decisión para solicitudes de compra, el usuario asignado a la decisión ve la línea de asunto y las instrucciones en la página **Solicitudes de compra**.</span><span class="sxs-lookup"><span data-stu-id="ec601-113">For example, if you're configuring a decision for purchase requisitions, the user who is assigned to the decision sees the subject line and instructions on the **Purchase requisitions** page.</span></span> <span data-ttu-id="ec601-114">La línea de asunto se muestra en una barra de mensajes de la página.</span><span class="sxs-lookup"><span data-stu-id="ec601-114">The subject line appears in a message bar on the page.</span></span> <span data-ttu-id="ec601-115">A continuación, el usuario puede hacer clic en el icono de dicha barra para ver las instrucciones.</span><span class="sxs-lookup"><span data-stu-id="ec601-115">The user can then click the icon in the message bar to view the instructions.</span></span> <span data-ttu-id="ec601-116">Siga estos pasos para escribir una línea de asunto e instrucciones.</span><span class="sxs-lookup"><span data-stu-id="ec601-116">Follow these steps to enter a subject line and instructions.</span></span>

1.  <span data-ttu-id="ec601-117">En el panel izquierdo, haga clic en **Configuración básica**.</span><span class="sxs-lookup"><span data-stu-id="ec601-117">In the left pane, click **Basic Settings**.</span></span>
2.  <span data-ttu-id="ec601-118">En la pestaña **Instrucciones** , en el campo **Asunto del elemento de trabajo**, escriba la línea de asunto.</span><span class="sxs-lookup"><span data-stu-id="ec601-118">On the **Instructions** tab, in the **Work item subject** field, enter the subject line.</span></span>
3.  <span data-ttu-id="ec601-119">Para personalizar la línea de asunto, puede insertar marcadores de posición.</span><span class="sxs-lookup"><span data-stu-id="ec601-119">To personalize the subject line, you can insert placeholders.</span></span> <span data-ttu-id="ec601-120">Estos se reemplazan con los datos adecuados cuando se muestra la línea de asunto a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="ec601-120">Placeholders are replaced with appropriate data when the subject line is shown to users.</span></span> <span data-ttu-id="ec601-121">Para insertar un marcador de posición, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="ec601-121">Follow these steps to insert a placeholder:</span></span>
    1.  <span data-ttu-id="ec601-122">En el cuadro de texto, gaga clic para especificar dónde debe aparecer el marcador de posición.</span><span class="sxs-lookup"><span data-stu-id="ec601-122">In the text box, click where the placeholder should appear.</span></span>
    2.  <span data-ttu-id="ec601-123">Haga clic en **Insertar marcador de posición**.</span><span class="sxs-lookup"><span data-stu-id="ec601-123">Click **Insert placeholder**.</span></span>
    3.  <span data-ttu-id="ec601-124">En la lista que aparece, seleccione el marcador de posición que desea insertar.</span><span class="sxs-lookup"><span data-stu-id="ec601-124">In the list that appears, select the placeholder to insert.</span></span>
    4.  <span data-ttu-id="ec601-125">Haga clic en **Insertar**.</span><span class="sxs-lookup"><span data-stu-id="ec601-125">Click **Insert**.</span></span>

4.  <span data-ttu-id="ec601-126">Para agregar traducciones de la línea de asunto, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="ec601-126">To add translations of the subject line, follow these steps:</span></span>
    1.  <span data-ttu-id="ec601-127">Haga clic en **Traducciones**.</span><span class="sxs-lookup"><span data-stu-id="ec601-127">Click **Translations**.</span></span>
    2.  <span data-ttu-id="ec601-128">En la página que aparece, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="ec601-128">On the page that appears, click **Add**.</span></span>
    3.  <span data-ttu-id="ec601-129">En la lista que aparece, seleccione el idioma en el que escribe el texto.</span><span class="sxs-lookup"><span data-stu-id="ec601-129">In the list that appears, select the language that you're entering the text in.</span></span>
    4.  <span data-ttu-id="ec601-130">En el campo **Texto traducido**, escriba el texto.</span><span class="sxs-lookup"><span data-stu-id="ec601-130">In the **Translated text** field, enter the text.</span></span>
    5.  <span data-ttu-id="ec601-131">Para personalizar el texto, puede insertar marcadores de posición como se describe en el paso 3.</span><span class="sxs-lookup"><span data-stu-id="ec601-131">To personalize the text, you can insert placeholders as described in step 3.</span></span>
    6.  <span data-ttu-id="ec601-132">Haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="ec601-132">Click **Close**.</span></span>

5.  <span data-ttu-id="ec601-133">En el campo **Instrucciones del elemento de trabajo**, escriba las instrucciones.</span><span class="sxs-lookup"><span data-stu-id="ec601-133">In the **Work item instructions** field, enter the instructions.</span></span>
6.  <span data-ttu-id="ec601-134">Para personalizar las instrucciones, puede insertar marcadores de posición.</span><span class="sxs-lookup"><span data-stu-id="ec601-134">To personalize the instructions, you can insert placeholders.</span></span> <span data-ttu-id="ec601-135">Estos se reemplazan con los datos adecuados cuando las instrucciones se muestran a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="ec601-135">Placeholders are replaced with appropriate data when the instructions are shown to users.</span></span> <span data-ttu-id="ec601-136">Para insertar un marcador de posición, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="ec601-136">Follow these steps to insert a placeholder:</span></span>
    1.  <span data-ttu-id="ec601-137">En el cuadro de texto, gaga clic para especificar dónde debe aparecer el marcador de posición.</span><span class="sxs-lookup"><span data-stu-id="ec601-137">In the text box, click where the placeholder should appear.</span></span>
    2.  <span data-ttu-id="ec601-138">Haga clic en **Insertar marcador de posición**.</span><span class="sxs-lookup"><span data-stu-id="ec601-138">Click **Insert placeholder**.</span></span>
    3.  <span data-ttu-id="ec601-139">En la lista que aparece, seleccione el marcador de posición que desea insertar.</span><span class="sxs-lookup"><span data-stu-id="ec601-139">In the list that appears, select the placeholder to insert.</span></span>
    4.  <span data-ttu-id="ec601-140">Haga clic en **Insertar**.</span><span class="sxs-lookup"><span data-stu-id="ec601-140">Click **Insert**.</span></span>

7.  <span data-ttu-id="ec601-141">Para agregar traducciones de las instrucciones, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="ec601-141">To add translations of the instructions, follow these steps:</span></span>
    1.  <span data-ttu-id="ec601-142">Haga clic en **Traducciones**.</span><span class="sxs-lookup"><span data-stu-id="ec601-142">Click **Translations**.</span></span>
    2.  <span data-ttu-id="ec601-143">En la página que aparece, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="ec601-143">On the page that appears, click **Add**.</span></span>
    3.  <span data-ttu-id="ec601-144">En la lista que aparece, seleccione el idioma en el que escribe el texto.</span><span class="sxs-lookup"><span data-stu-id="ec601-144">In the list that appears, select the language that you're entering the text in.</span></span>
    4.  <span data-ttu-id="ec601-145">En el campo **Texto traducido**, escriba el texto.</span><span class="sxs-lookup"><span data-stu-id="ec601-145">In the **Translated text** field, enter the text.</span></span>
    5.  <span data-ttu-id="ec601-146">Para personalizar el texto, puede insertar marcadores de posición como se describe en el paso 6.</span><span class="sxs-lookup"><span data-stu-id="ec601-146">To personalize the text, you can insert placeholders as described in step 6.</span></span>
    6.  <span data-ttu-id="ec601-147">Haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="ec601-147">Click **Close**.</span></span>

## <a name="specify-the-possible-outcomes-of-a-decision"></a><span data-ttu-id="ec601-148">Especificación de los posibles resultados de una decisión</span><span class="sxs-lookup"><span data-stu-id="ec601-148">Specify the possible outcomes of a decision</span></span>
<span data-ttu-id="ec601-149">Normalmente, cuando a una persona responsable de tomar decisiones se le asigna un documento, se le formula una pregunta.</span><span class="sxs-lookup"><span data-stu-id="ec601-149">Typically, when a document is assigned to a decision maker, the decision maker is asked a question.</span></span> <span data-ttu-id="ec601-150">La respuesta a esta pregunta es generalmente **Sí** o **No**, o bien **Verdadero** o **Falso**.</span><span class="sxs-lookup"><span data-stu-id="ec601-150">The answer to this question is usually **Yes** or **No**, or **True** or **False**.</span></span> <span data-ttu-id="ec601-151">Siga estos pasos para especificar los resultados que podría tener la decisión manual.</span><span class="sxs-lookup"><span data-stu-id="ec601-151">Follow these steps to specify the possible outcomes of the manual decision.</span></span>

1.  <span data-ttu-id="ec601-152">En el panel izquierdo, haga clic en **Configuración básica**.</span><span class="sxs-lookup"><span data-stu-id="ec601-152">In the left pane, click **Basic Settings**.</span></span>
2.  <span data-ttu-id="ec601-153">En la pestaña **Resultados**, en el campo **Resultado 1**, escriba el nombre del resultado o especifique la opción.</span><span class="sxs-lookup"><span data-stu-id="ec601-153">On the **Outcomes** tab, in the **Outcome 1** field, enter the name of the outcome, or the option.</span></span>
3.  <span data-ttu-id="ec601-154">Para agregar traducciones del resultado, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="ec601-154">To add translations of the outcome, follow these steps:</span></span>
    1.  <span data-ttu-id="ec601-155">Haga clic en **Traducciones**.</span><span class="sxs-lookup"><span data-stu-id="ec601-155">Click **Translations**.</span></span>
    2.  <span data-ttu-id="ec601-156">En la página que aparece, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="ec601-156">On the page that appears, click **Add**.</span></span>
    3.  <span data-ttu-id="ec601-157">En la lista que aparece, seleccione el idioma en el que escribe el texto.</span><span class="sxs-lookup"><span data-stu-id="ec601-157">In the list that appears, select the language that you're entering the text in.</span></span>
    4.  <span data-ttu-id="ec601-158">En el campo **Texto traducido**, escriba el texto.</span><span class="sxs-lookup"><span data-stu-id="ec601-158">In the **Translated text** field, enter the text.</span></span>
    5.  <span data-ttu-id="ec601-159">Haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="ec601-159">Click **Close**.</span></span>

4.  <span data-ttu-id="ec601-160">En el campo **Resultado 2**, escriba el nombre del resultado o especifique la opción.</span><span class="sxs-lookup"><span data-stu-id="ec601-160">In the **Outcome 2** field, enter the name of the outcome, or the option.</span></span>
5.  <span data-ttu-id="ec601-161">Para agregar traducciones del resultado, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="ec601-161">To add translations of the outcome, follow these steps:</span></span>
    1.  <span data-ttu-id="ec601-162">Haga clic en **Traducciones**.</span><span class="sxs-lookup"><span data-stu-id="ec601-162">Click **Translations**.</span></span>
    2.  <span data-ttu-id="ec601-163">En la página que aparece, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="ec601-163">On the page that appears, click **Add**.</span></span>
    3.  <span data-ttu-id="ec601-164">En la lista que aparece, seleccione el idioma en el que escribe el texto.</span><span class="sxs-lookup"><span data-stu-id="ec601-164">In the list that appears, select the language that you're entering the text in.</span></span>
    4.  <span data-ttu-id="ec601-165">En el campo **Texto traducido**, escriba el texto.</span><span class="sxs-lookup"><span data-stu-id="ec601-165">In the **Translated text** field, enter the text.</span></span>
    5.  <span data-ttu-id="ec601-166">Haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="ec601-166">Click **Close**.</span></span>

## <a name="specify-when-notifications-are-sent"></a><span data-ttu-id="ec601-167">Especificación del momento en que se envían notificaciones</span><span class="sxs-lookup"><span data-stu-id="ec601-167">Specify when notifications are sent</span></span>
<span data-ttu-id="ec601-168">Puede enviar notificaciones cuando se haya tomado o delegado una decisión o cuando se la haya remitido a una instancia superior.</span><span class="sxs-lookup"><span data-stu-id="ec601-168">You can send notifications to people when a decision has been made, delegated, or escalated.</span></span> <span data-ttu-id="ec601-169">Siga estos pasos para especificar cuándo se deben enviar notificaciones y a quiénes se deben enviar.</span><span class="sxs-lookup"><span data-stu-id="ec601-169">Follow these steps to specify when notifications are sent, and who the notifications are sent to.</span></span>

1.  <span data-ttu-id="ec601-170">En el panel izquierdo, haga clic en **Notificaciones**.</span><span class="sxs-lookup"><span data-stu-id="ec601-170">In the left pane, click **Notifications**.</span></span>
2.  <span data-ttu-id="ec601-171">Active las casillas de verificación junto a los eventos que deben notificarse:</span><span class="sxs-lookup"><span data-stu-id="ec601-171">Select the check box next to the events that notifications should be sent for:</span></span>
    -   <span data-ttu-id="ec601-172">**\[Elección 1\]**: el usuario asignado ha optado por la **\[Elección 1\]**.</span><span class="sxs-lookup"><span data-stu-id="ec601-172">**\[Choice 1\]** – The assigned user has selected **\[Choice 1\]**.</span></span>
    -   <span data-ttu-id="ec601-173">**\[Elección 2\]**: el usuario asignado ha optado por la **\[Elección 2\]**.</span><span class="sxs-lookup"><span data-stu-id="ec601-173">**\[Choice 2\]** – The assigned user has selected **\[Choice 2\]**.</span></span>
    -   <span data-ttu-id="ec601-174">**Delegar**: el usuario asignado ha asignado la decisión a otro usuario.</span><span class="sxs-lookup"><span data-stu-id="ec601-174">**Delegate** – The assigned user has assigned the decision to another user.</span></span>
    -   <span data-ttu-id="ec601-175">**Remitir a una instancia superior**: el usuario asignado no ha tomado la decisión en el tiempo previsto.</span><span class="sxs-lookup"><span data-stu-id="ec601-175">**Escalate** – The assigned user hasn't made the decision in the allotted time.</span></span>

3.  <span data-ttu-id="ec601-176">Seleccione la fila correspondiente a uno de los eventos que seleccionó en el paso 2.</span><span class="sxs-lookup"><span data-stu-id="ec601-176">Select the row for an event that you selected in step 2.</span></span>
4.  <span data-ttu-id="ec601-177">En la pestaña **Texto de notificación**, en el cuadro de texto, escriba el texto de la notificación.</span><span class="sxs-lookup"><span data-stu-id="ec601-177">On the **Notification text** tab, in the text box, enter the text of the notification.</span></span>
5.  <span data-ttu-id="ec601-178">Para personalizar la notificación, puede insertar marcadores de posición.</span><span class="sxs-lookup"><span data-stu-id="ec601-178">To personalize the notification, you can insert placeholders.</span></span> <span data-ttu-id="ec601-179">Estos se reemplazan con los datos adecuados cuando se muestra la notificación a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="ec601-179">Placeholders are replaced with appropriate data when the notification is show to users.</span></span> <span data-ttu-id="ec601-180">Para insertar un marcador de posición, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="ec601-180">Follow these steps to insert a placeholder:</span></span>
    1.  <span data-ttu-id="ec601-181">En el cuadro de texto, gaga clic para especificar dónde debe aparecer el marcador de posición.</span><span class="sxs-lookup"><span data-stu-id="ec601-181">In the text box, click where the placeholder should appear.</span></span>
    2.  <span data-ttu-id="ec601-182">Haga clic en **Insertar marcador de posición**.</span><span class="sxs-lookup"><span data-stu-id="ec601-182">Click **Insert placeholder**.</span></span>
    3.  <span data-ttu-id="ec601-183">En la lista que aparece, seleccione el marcador de posición que desea insertar.</span><span class="sxs-lookup"><span data-stu-id="ec601-183">In the list that appears, select the placeholder to insert.</span></span>
    4.  <span data-ttu-id="ec601-184">Haga clic en **Insertar**.</span><span class="sxs-lookup"><span data-stu-id="ec601-184">Click **Insert**.</span></span>

6.  <span data-ttu-id="ec601-185">Para agregar traducciones de la notificación, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="ec601-185">To add translations of the notification, follow these steps:</span></span>
    1.  <span data-ttu-id="ec601-186">Haga clic en **Traducciones**.</span><span class="sxs-lookup"><span data-stu-id="ec601-186">Click **Translations**.</span></span>
    2.  <span data-ttu-id="ec601-187">En la página que aparece, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="ec601-187">On the page that appears, click **Add**.</span></span>
    3.  <span data-ttu-id="ec601-188">En la lista que aparece, seleccione el idioma en el que escribe el texto.</span><span class="sxs-lookup"><span data-stu-id="ec601-188">In the list that appears, select the language that you're entering the text in.</span></span>
    4.  <span data-ttu-id="ec601-189">En el campo **Texto traducido**, escriba el texto.</span><span class="sxs-lookup"><span data-stu-id="ec601-189">In the **Translated text** field, enter the text.</span></span>
    5.  <span data-ttu-id="ec601-190">Para personalizar el texto, puede insertar marcadores de posición como se describe en el paso 5.</span><span class="sxs-lookup"><span data-stu-id="ec601-190">To personalize the text, you can insert placeholders as described in step 5.</span></span>
    6.  <span data-ttu-id="ec601-191">Haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="ec601-191">Click **Close**.</span></span>

7.  <span data-ttu-id="ec601-192">En la pestaña **Destinatario**, especifique a quién se envían las notificaciones.</span><span class="sxs-lookup"><span data-stu-id="ec601-192">On the **Recipient** tab, specify who the notifications are sent to.</span></span> <span data-ttu-id="ec601-193">Seleccione una de las opciones de la siguiente tabla y, a continuación, siga los pasos adicionales correspondientes a esa opción antes de realizar el paso 8.</span><span class="sxs-lookup"><span data-stu-id="ec601-193">Select one of the options in the following table, and then follow the additional steps for that option before you go to step 8.</span></span>
    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="ec601-194">Opción</span><span class="sxs-lookup"><span data-stu-id="ec601-194">Option</span></span></th>
    <th><span data-ttu-id="ec601-195">Destinatarios de las notificaciones</span><span class="sxs-lookup"><span data-stu-id="ec601-195">Notification recipients</span></span></th>
    <th><span data-ttu-id="ec601-196">Pasos adicionales</span><span class="sxs-lookup"><span data-stu-id="ec601-196">Additional steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><span data-ttu-id="ec601-197">Participante</span><span class="sxs-lookup"><span data-stu-id="ec601-197">Participant</span></span></td>
    <td><span data-ttu-id="ec601-198">Usuarios asignados a un grupo o rol específicos</span><span class="sxs-lookup"><span data-stu-id="ec601-198">Users who are assigned to a specific group or role</span></span></td>
    <td><ol>
    <li><span data-ttu-id="ec601-199">Tras seleccionar <strong>Participante</strong>, en la pestaña <strong>Basado en funciones</strong>, en la lista <strong>Tipo de participante</strong>, seleccione el tipo de grupo o rol al que desea enviar las notificaciones.</span><span class="sxs-lookup"><span data-stu-id="ec601-199">After you select <strong>Participant</strong>, on the <strong>Role based</strong> tab, in the <strong>Type of participant</strong> list, select the type of group or role to send notifications to.</span></span></li>
    <li><span data-ttu-id="ec601-200">En la lista <strong>Participante</strong>, seleccione el grupo al que se deben enviar las notificaciones.</span><span class="sxs-lookup"><span data-stu-id="ec601-200">In the <strong>Participant</strong> list, select the group or to send notifications to.</span></span></li>
    </ol></td>
    </tr>
    <tr class="even">
    <td><span data-ttu-id="ec601-201">Usuario del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="ec601-201">Workflow user</span></span></td>
    <td><span data-ttu-id="ec601-202">Usuarios del flujo de trabajo actual</span><span class="sxs-lookup"><span data-stu-id="ec601-202">Users in the current workflow</span></span></td>
    <td><ul>
    <li><span data-ttu-id="ec601-203">Tras seleccionar <strong>Usuario del flujo de trabajo</strong>, en la pestaña <strong>Usuario del flujo de trabajo</strong>, en la pestaña <strong>Usuario del flujo de trabajo</strong>, seleccione un usuario que participe en el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="ec601-203">After you select <strong>Workflow user</strong>, on the <strong>Workflow user</strong> tab, in the <strong>Workflow user</strong> list, select a user who participates in the workflow.</span></span></li>
    </ul></td>
    </tr>
    <tr class="odd">
    <td><span data-ttu-id="ec601-204">Usuario</span><span class="sxs-lookup"><span data-stu-id="ec601-204">User</span></span></td>
    <td><span data-ttu-id="ec601-205">Usuarios específicos de Microsoft Dynamics 365 for Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="ec601-205">Specific Microsoft Dynamics 365 for Finance and Operations users</span></span></td>
    <td><ol>
    <li><span data-ttu-id="ec601-206">Tras seleccionar <strong>Usuario</strong>, haga clic en la pestaña <strong>Usuario</strong>.</span><span class="sxs-lookup"><span data-stu-id="ec601-206">After you select <strong>User</strong>, click the <strong>User</strong> tab.</span></span></li>
    <li><span data-ttu-id="ec601-207">La lista de <strong>Usuarios disponibles</strong> incluye a todos los usuarios de Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="ec601-207">The <strong>Available users</strong> list includes all Finance and Operations users.</span></span> <span data-ttu-id="ec601-208">Seleccione aquellos a los que desea enviar notificaciones y, a continuación, muévalos a la lista <strong>Usuarios seleccionados</strong>.</span><span class="sxs-lookup"><span data-stu-id="ec601-208">Select the users to send notifications to, and then move those users to the <strong>Selected users</strong> list.</span></span></li>
    </ol></td>
    </tr>
    </tbody>
    </table>

8.  <span data-ttu-id="ec601-209">Repita los pasos 3 a 7 por cada uno de los eventos que haya seleccionado en el paso 2.</span><span class="sxs-lookup"><span data-stu-id="ec601-209">Repeat steps 3 through 7 for each event that you selected in step 2.</span></span>

## <a name="assign-a-decision"></a><span data-ttu-id="ec601-210">Asignación de una decisión</span><span class="sxs-lookup"><span data-stu-id="ec601-210">Assign a decision</span></span>
<span data-ttu-id="ec601-211">Siga estos pasos para especificar a quién se debe asignar una decisión manual.</span><span class="sxs-lookup"><span data-stu-id="ec601-211">Follow these steps to specify who a manual decision should be assigned to.</span></span>

1.  <span data-ttu-id="ec601-212">En el panel izquierdo, haga clic en **Asignación**.</span><span class="sxs-lookup"><span data-stu-id="ec601-212">In the left pane, click **Assignment**.</span></span>
2.  <span data-ttu-id="ec601-213">En la pestaña **Tipo de asignación**, seleccione una de las opciones de la siguiente tabla. A continuación, siga los pasos adicionales correspondientes a la opción elegida antes de realizar el paso 3.</span><span class="sxs-lookup"><span data-stu-id="ec601-213">On the **Assignment type** tab, select one of the options in the following table, and then follow the additional steps for that option before you go to step 3.</span></span>
    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="ec601-214">Opción</span><span class="sxs-lookup"><span data-stu-id="ec601-214">Option</span></span></th>
    <th><span data-ttu-id="ec601-215">Usuarios a los que se asigna la decisión</span><span class="sxs-lookup"><span data-stu-id="ec601-215">Users that the decision is assigned to</span></span></th>
    <th><span data-ttu-id="ec601-216">Pasos adicionales</span><span class="sxs-lookup"><span data-stu-id="ec601-216">Additional steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><span data-ttu-id="ec601-217">Participante</span><span class="sxs-lookup"><span data-stu-id="ec601-217">Participant</span></span></td>
    <td><span data-ttu-id="ec601-218">Usuarios asignados a un grupo o rol específicos</span><span class="sxs-lookup"><span data-stu-id="ec601-218">Users who are assigned to a specific group or role</span></span></td>
    <td><ol>
    <li><span data-ttu-id="ec601-219">Tras seleccionar <strong>Participante</strong>, en la pestaña <strong>Basado en funciones</strong>, en la lista <strong>Tipo de participante</strong>, seleccione el tipo de grupo o rol al que desea asignar la decisión.</span><span class="sxs-lookup"><span data-stu-id="ec601-219">After you select <strong>Participant</strong>, on the <strong>Role based</strong> tab, in the <strong>Type of participant</strong> list, select the type of group or role to assign the decision to.</span></span></li>
    <li><span data-ttu-id="ec601-220">En la lista <strong>Participante</strong>, seleccione el grupo o rol al que se debe asignar la decisión.</span><span class="sxs-lookup"><span data-stu-id="ec601-220">In the <strong>Participant</strong> list, select the group or role to assign the decision to.</span></span></li>
    </ol></td>
    </tr>
    <tr class="even">
    <td><span data-ttu-id="ec601-221">Jerarquía</span><span class="sxs-lookup"><span data-stu-id="ec601-221">Hierarchy</span></span></td>
    <td><span data-ttu-id="ec601-222">Usuarios de una jerarquía organizativa específica</span><span class="sxs-lookup"><span data-stu-id="ec601-222">Users in a specific organizational hierarchy</span></span></td>
    <td><ol>
    <li><span data-ttu-id="ec601-223">Tras seleccionar <strong>Jerarquía</strong>, en la pestaña <strong>Selección de jerarquía</strong>, en la lista <strong>Tipo de jerarquía</strong>, seleccione el tipo de jerarquía al que desea asignar la decisión.</span><span class="sxs-lookup"><span data-stu-id="ec601-223">After you select <strong>Hierarchy</strong>, on the <strong>Hierarchy selection</strong> tab, in the <strong>Hierarchy type</strong> list, select the type of hierarchy to assign the decision to.</span></span></li>
    <li><span data-ttu-id="ec601-224">El sistema debe recuperar un intervalo de nombres de usuario de la jerarquía.</span><span class="sxs-lookup"><span data-stu-id="ec601-224">The system must retrieve a range of user names from the hierarchy.</span></span> <span data-ttu-id="ec601-225">Dichos nombres representan a los usuarios a los que se puede asignar la decisión.</span><span class="sxs-lookup"><span data-stu-id="ec601-225">These names represent users that the decision can be assigned to.</span></span> <span data-ttu-id="ec601-226">Siga estos pasos para especificar el punto de inicio y de finalización del intervalo de nombres de usuario que el sistema recupera:</span><span class="sxs-lookup"><span data-stu-id="ec601-226">Follow these steps to specify the starting point and ending point of the range of user names that the system retrieves:</span></span> <ol>
    <li><span data-ttu-id="ec601-227">Para especificar el punto de inicio, seleccione una persona en la lista <strong>Comenzar desde</strong>.</span><span class="sxs-lookup"><span data-stu-id="ec601-227">To specify the starting point, select a person in the <strong>Start from</strong> list.</span></span></li>
    <li><span data-ttu-id="ec601-228">Para especificar el punto de finalización, haga clic en <strong>Agregar condición</strong>.</span><span class="sxs-lookup"><span data-stu-id="ec601-228">To specify the ending point, click <strong>Add condition</strong>.</span></span> <span data-ttu-id="ec601-229">A continuación, especifique una condición que determine en qué parte de la jerarquía el sistema dejará de recuperar nombres.</span><span class="sxs-lookup"><span data-stu-id="ec601-229">Then enter a condition that determines where in the hierarchy the system stops retrieving names.</span></span></li>
    </ol></li>
    <li><span data-ttu-id="ec601-230">En la pestaña <strong>Opciones de jerarquía</strong>, especifique a qué usuarios del intervalo se debe asignar la decisión:</span><span class="sxs-lookup"><span data-stu-id="ec601-230">On the <strong>Hierarchy options</strong> tab, specify which users in the range the decision should be assigned to:</span></span> <ul>
    <li><span data-ttu-id="ec601-231"><strong>Asignar a todos los usuarios recuperados</strong>: la decisión se asigna a todos los usuarios del intervalo.</span><span class="sxs-lookup"><span data-stu-id="ec601-231"><strong>Assign to all users retrieved</strong> – The decision is assigned to all users in the range.</span></span></li>
    <li><span data-ttu-id="ec601-232"><strong>Asignar sólo al último usuario recuperado</strong>: la decisión se asigna únicamente al último usuario del intervalo.</span><span class="sxs-lookup"><span data-stu-id="ec601-232"><strong>Assign only to last user retrieved</strong> – The decision is assigned to only the last user in the range.</span></span></li>
    <li><span data-ttu-id="ec601-233"><strong>Excluir usuarios con la siguiente condición</strong>: la decisión no se asigna a ninguno de los usuarios del intervalo que cumplen con una condición determinada.</span><span class="sxs-lookup"><span data-stu-id="ec601-233"><strong>Exclude users with the following condition</strong> – The decision isn't assigned to any users in the range who meet a specific condition.</span></span> <span data-ttu-id="ec601-234">Haga clic en <strong>Agregar condición</strong> para especificar la condición.</span><span class="sxs-lookup"><span data-stu-id="ec601-234">Click <strong>Add condition</strong> to specify the condition.</span></span></li>
    </ul></li>
    </ol></td>
    </tr>
    <tr class="odd">
    <td><span data-ttu-id="ec601-235">Usuario del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="ec601-235">Workflow user</span></span></td>
    <td><span data-ttu-id="ec601-236">Usuarios del flujo de trabajo actual</span><span class="sxs-lookup"><span data-stu-id="ec601-236">Users in the current workflow</span></span></td>
    <td><ul>
    <li><span data-ttu-id="ec601-237">Tras seleccionar <strong>Usuario del flujo de trabajo</strong>, en la pestaña <strong>Usuario del flujo de trabajo</strong>, en la pestaña <strong>Usuario del flujo de trabajo</strong>, seleccione un usuario que participe en el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="ec601-237">After you select <strong>Workflow user</strong>, on the <strong>Workflow user</strong> tab, in the <strong>Workflow user</strong> list, select a user who participates in the workflow.</span></span></li>
    </ul></td>
    </tr>
    <tr class="even">
    <td><span data-ttu-id="ec601-238">Usuario</span><span class="sxs-lookup"><span data-stu-id="ec601-238">User</span></span></td>
    <td><span data-ttu-id="ec601-239">Usuarios específicos de Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="ec601-239">Specific Finance and Operations users</span></span></td>
    <td><ol>
    <li><span data-ttu-id="ec601-240">Tras seleccionar <strong>Usuario</strong>, haga clic en la pestaña <strong>Usuario</strong>.</span><span class="sxs-lookup"><span data-stu-id="ec601-240">After you select <strong>User</strong>, click the <strong>User</strong> tab.</span></span></li>
    <li><span data-ttu-id="ec601-241">La lista de <strong>Usuarios disponibles</strong> incluye a todos los usuarios de Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="ec601-241">The <strong>Available users</strong> list includes all Finance and Operations users.</span></span> <span data-ttu-id="ec601-242">Seleccione aquellos a los que desea asignar la decisión y, a continuación, muévalos a la lista <strong>Usuarios seleccionados</strong>.</span><span class="sxs-lookup"><span data-stu-id="ec601-242">Select the users to assign the decision to, and then move those users to the <strong>Selected users</strong> list.</span></span></li>
    </ol></td>
    </tr>
    <tr class="odd">
    <td><span data-ttu-id="ec601-243">Cola</span><span class="sxs-lookup"><span data-stu-id="ec601-243">Queue</span></span></td>
    <td><span data-ttu-id="ec601-244">Una cola de elementos de trabajo</span><span class="sxs-lookup"><span data-stu-id="ec601-244">A work item queue</span></span></td>
    <td><ol>
    <li><span data-ttu-id="ec601-245">Tras seleccionar <strong>Cola</strong>, haga clic en la pestaña <strong>Basado en cola</strong>.</span><span class="sxs-lookup"><span data-stu-id="ec601-245">After you select <strong>Queue</strong>, click the <strong>Queue based</strong> tab.</span></span></li>
    <li><span data-ttu-id="ec601-246">Para asignar la decisión a una cola específica, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="ec601-246">To assign the decision to a specific queue, follow these steps:</span></span> <ol>
    <li><span data-ttu-id="ec601-247">En la lista <strong>Tipo de cola</strong>, seleccione <strong>Colas de elementos de trabajo</strong>.</span><span class="sxs-lookup"><span data-stu-id="ec601-247">In the <strong>Queue type</strong> list, select <strong>Work item queues</strong>.</span></span></li>
    <li><span data-ttu-id="ec601-248">En la lista <strong>Nombre de cola</strong>, seleccione la cola.</span><span class="sxs-lookup"><span data-stu-id="ec601-248">In the <strong>Queue name</strong> list, select the queue.</span></span></li>
    </ol></li>
    <li><span data-ttu-id="ec601-249">Si la cola a la que se debe asignar la decisión debe estar determinada por una condición específica, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="ec601-249">If a specific condition should determine which queue the decision is assigned to, follow these steps:</span></span> <ol>
    <li><span data-ttu-id="ec601-250">En la lista <strong>Tipo de cola</strong>, seleccione <strong>Colas de elementos de trabajo condicional</strong>.</span><span class="sxs-lookup"><span data-stu-id="ec601-250">In the <strong>Queue type</strong> list, select <strong>Conditional work item queues</strong>.</span></span></li>
    <li><span data-ttu-id="ec601-251">En la lista <strong>Nombre de cola</strong>, seleccione <strong>Cola condicional</strong>.</span><span class="sxs-lookup"><span data-stu-id="ec601-251">In the <strong>Queue name</strong> list, select <strong>Conditional queue</strong>.</span></span></li>
    </ol></li>
    </ol><span data-ttu-id="ec601-252">
    <strong>Nota:</strong> Esta opción solo se usa para algunos flujos de trabajo, como Gestión de casos.</span><span class="sxs-lookup"><span data-stu-id="ec601-252">
    <strong>Note:</strong> This option is used for only a few workflows, such as Case management.</span></span></td>
    </tr>
    </tbody>
    </table>

3.  <span data-ttu-id="ec601-253">En la pestaña **Límite de tiempo**, en el campo **Duración**, especifique el tiempo del que dispone el usuario para tomar la decisión.</span><span class="sxs-lookup"><span data-stu-id="ec601-253">On the **Time limit** tab, in the **Duration** field, specify how much time the user has to make the decision.</span></span> <span data-ttu-id="ec601-254">Seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="ec601-254">Select one of the following options:</span></span>
    -   <span data-ttu-id="ec601-255">**Horas**: escriba la cantidad de horas de las que dispone el usuario para tomar la decisión.</span><span class="sxs-lookup"><span data-stu-id="ec601-255">**Hours** – Enter the number of hours that the user has to make the decision.</span></span> <span data-ttu-id="ec601-256">A continuación, seleccione el calendario que usa la organización y escriba la información pertinente acerca de la semana laboral de la organización.</span><span class="sxs-lookup"><span data-stu-id="ec601-256">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    -   <span data-ttu-id="ec601-257">**Días**: escriba la cantidad de días de los que dispone el usuario para tomar la decisión.</span><span class="sxs-lookup"><span data-stu-id="ec601-257">**Days** – Enter the number of days that the user has to make the decision.</span></span> <span data-ttu-id="ec601-258">A continuación, seleccione el calendario que usa la organización y escriba la información pertinente acerca de la semana laboral de la organización.</span><span class="sxs-lookup"><span data-stu-id="ec601-258">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    -   <span data-ttu-id="ec601-259">**Semanas**: escriba la cantidad de semanas de las que dispone el usuario para tomar la decisión.</span><span class="sxs-lookup"><span data-stu-id="ec601-259">**Weeks** – Enter the number of weeks that the user has to make the decision.</span></span>
    -   <span data-ttu-id="ec601-260">**Meses**: seleccione el día y la semana antes de los cuales el usuario debe tomar la decisión.</span><span class="sxs-lookup"><span data-stu-id="ec601-260">**Months** – Select the day and week that the user must make the decision by.</span></span> <span data-ttu-id="ec601-261">Por ejemplo, tal vez desee que el usuario haya tomado la decisión antes del viernes de la tercera semana del mes.</span><span class="sxs-lookup"><span data-stu-id="ec601-261">For example, you might want the user to make the decision by Friday of the third week of the month.</span></span>
    -   <span data-ttu-id="ec601-262">**Años**: seleccione el día, la semana y el mes en los que vence el plazo para tomar la decisión.</span><span class="sxs-lookup"><span data-stu-id="ec601-262">**Years** – Select the day, week, and month that the user must make the decision by.</span></span> <span data-ttu-id="ec601-263">Por ejemplo, tal vez desee que el usuario haya tomado la decisión antes del viernes de la tercera semana de diciembre.</span><span class="sxs-lookup"><span data-stu-id="ec601-263">For example, you might want the user to make the decision by Friday of the third week of December.</span></span>

    <span data-ttu-id="ec601-264">Si el usuario no toma la decisión en el tiempo asignado, la decisión se considera vencida.</span><span class="sxs-lookup"><span data-stu-id="ec601-264">If the user doesn't make the decision in the allotted time, the decision is overdue.</span></span> <span data-ttu-id="ec601-265">Las decisiones vencidas se remiten a una instancia superior en función de las opciones que se seleccionen en el área **Remisión a una instancia superior** de la página.</span><span class="sxs-lookup"><span data-stu-id="ec601-265">A decision that is overdue is escalated, based on the options that you select in the **Escalation** area of the page.</span></span>

## <a name="specify-what-happens-when-a-decision-is-overdue"></a><span data-ttu-id="ec601-266">Especificación de la acción que se realiza cuando vence una decisión</span><span class="sxs-lookup"><span data-stu-id="ec601-266">Specify what happens when a decision is overdue</span></span>
<span data-ttu-id="ec601-267">Si un usuario no toma la decisión en el tiempo asignado, la decisión se considera vencida.</span><span class="sxs-lookup"><span data-stu-id="ec601-267">If a user doesn't make the decision in the allotted time, the decision is overdue.</span></span> <span data-ttu-id="ec601-268">Las decisiones vencidas se pueden remitir a una instancia superior, o asignar a otro usuario de forma automática.</span><span class="sxs-lookup"><span data-stu-id="ec601-268">A decision that is overdue can be escalated, or automatically assigned to another user.</span></span> <span data-ttu-id="ec601-269">Si la decisión ha vencido, siga estos pasos para remitirla a una instancia superior.</span><span class="sxs-lookup"><span data-stu-id="ec601-269">Follow these steps to escalate the decision if it's overdue.</span></span>

1.  <span data-ttu-id="ec601-270">En el panel izquierdo, haga clic en **Remisión a una instancia superior**.</span><span class="sxs-lookup"><span data-stu-id="ec601-270">In the left pane, click **Escalation**.</span></span>
2.  <span data-ttu-id="ec601-271">Active la casilla de verificación **Usar ruta de remisión a una instancia superior** para crear una ruta de remisión a una instancia superior.</span><span class="sxs-lookup"><span data-stu-id="ec601-271">Select the **Use escalation path** check box to create an escalation path.</span></span> <span data-ttu-id="ec601-272">De manera automática, el sistema asigna la decisión a los usuarios que forman parte de la ruta de remisión a una instancia superior.</span><span class="sxs-lookup"><span data-stu-id="ec601-272">The system automatically assigns the decision to the users who are listed in the escalation path.</span></span> <span data-ttu-id="ec601-273">La siguiente tabla, por ejemplo, representa una ruta de remisión a una instancia superior.</span><span class="sxs-lookup"><span data-stu-id="ec601-273">For example, the following table represents an escalation path.</span></span>
    | <span data-ttu-id="ec601-274">Secuencia</span><span class="sxs-lookup"><span data-stu-id="ec601-274">Sequence</span></span> | <span data-ttu-id="ec601-275">Ruta de remisión a una instancia superior</span><span class="sxs-lookup"><span data-stu-id="ec601-275">Escalation path</span></span>            |
    |----------|----------------------------|
    | <span data-ttu-id="ec601-276">1</span><span class="sxs-lookup"><span data-stu-id="ec601-276">1</span></span>        | <span data-ttu-id="ec601-277">Asignar a rol: Donna</span><span class="sxs-lookup"><span data-stu-id="ec601-277">Assign to: Donna</span></span>           |
    | <span data-ttu-id="ec601-278">2</span><span class="sxs-lookup"><span data-stu-id="ec601-278">2</span></span>        | <span data-ttu-id="ec601-279">Asignar a rol: Erin</span><span class="sxs-lookup"><span data-stu-id="ec601-279">Assign to: Erin</span></span>            |
    | <span data-ttu-id="ec601-280">3</span><span class="sxs-lookup"><span data-stu-id="ec601-280">3</span></span>        | <span data-ttu-id="ec601-281">Acción final: \[Elección 1\]</span><span class="sxs-lookup"><span data-stu-id="ec601-281">Final action: \[Choice 1\]</span></span> |

    <span data-ttu-id="ec601-282">En este ejemplo, el sistema asigna la decisión vencida a Donna.</span><span class="sxs-lookup"><span data-stu-id="ec601-282">In this example, the system assigns the overdue decision to Donna.</span></span> <span data-ttu-id="ec601-283">Si Donna no toma la decisión en el tiempo asignado, el sistema la asigna a Erin.</span><span class="sxs-lookup"><span data-stu-id="ec601-283">If Donna doesn't make the decision in the allotted time, the system assigns the decision to Erin.</span></span> <span data-ttu-id="ec601-284">Si Erin no toma la decisión en el tiempo asignado, el sistema selecciona la **\[Elección 1\]** como decisión.</span><span class="sxs-lookup"><span data-stu-id="ec601-284">If Erin doesn't make the decision in the allotted time, the system selects **\[Choice 1\]** as the decision.</span></span>
3.  <span data-ttu-id="ec601-285">Para agregar un usuario a la ruta de remisión a una instancia superior, haga clic en **Agregar remisión a una instancia superior**.</span><span class="sxs-lookup"><span data-stu-id="ec601-285">To add a user to the escalation path, click **Add escalation**.</span></span> <span data-ttu-id="ec601-286">Seleccione una de las opciones de la siguiente tabla y, a continuación, siga los pasos adicionales correspondientes a esa opción antes de realizar el paso 4.</span><span class="sxs-lookup"><span data-stu-id="ec601-286">Select one of the options in the following table, and then follow the additional steps for that option before you go to step 4.</span></span>
    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="ec601-287">Opción</span><span class="sxs-lookup"><span data-stu-id="ec601-287">Option</span></span></th>
    <th><span data-ttu-id="ec601-288">Usuarios a los que se remite la decisión</span><span class="sxs-lookup"><span data-stu-id="ec601-288">Users that the decision is escalated to</span></span></th>
    <th><span data-ttu-id="ec601-289">Pasos adicionales</span><span class="sxs-lookup"><span data-stu-id="ec601-289">Additional steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><span data-ttu-id="ec601-290">Jerarquía</span><span class="sxs-lookup"><span data-stu-id="ec601-290">Hierarchy</span></span></td>
    <td><span data-ttu-id="ec601-291">Usuarios de una jerarquía organizativa específica</span><span class="sxs-lookup"><span data-stu-id="ec601-291">Users in a specific organizational hierarchy</span></span></td>
    <td><ol>
    <li><span data-ttu-id="ec601-292">Tras seleccionar <strong>Jerarquía</strong>, en la pestaña <strong>Selección de jerarquía</strong>, en la lista <strong>Tipo de jerarquía</strong>, seleccione el tipo de jerarquía al que desea remitir a una instancia superior la decisión.</span><span class="sxs-lookup"><span data-stu-id="ec601-292">After you select <strong>Hierarchy</strong>, on the <strong>Hierarchy selection</strong> tab, in the <strong>Hierarchy type</strong> list, select the type of hierarchy to escalate the decision to.</span></span></li>
    <li><span data-ttu-id="ec601-293">El sistema debe recuperar un intervalo de nombres de usuario de la jerarquía.</span><span class="sxs-lookup"><span data-stu-id="ec601-293">The system must retrieve a range of user names from the hierarchy.</span></span> <span data-ttu-id="ec601-294">Dichos nombres representan a los usuarios a los que se puede remitir la decisión para una instancia superior.</span><span class="sxs-lookup"><span data-stu-id="ec601-294">These names represent users that the decision can be escalated to.</span></span> <span data-ttu-id="ec601-295">Siga estos pasos para especificar el punto de inicio y de finalización del intervalo de nombres de usuario que el sistema recupera:</span><span class="sxs-lookup"><span data-stu-id="ec601-295">Follow these steps to specify the starting point and ending point of the range of user names that the system retrieves:</span></span> <ol>
    <li><span data-ttu-id="ec601-296">Para especificar el punto de inicio, seleccione una persona en la lista <strong>Comenzar desde</strong>.</span><span class="sxs-lookup"><span data-stu-id="ec601-296">To specify the starting point, select a person in the <strong>Start from</strong> list.</span></span></li>
    <li><span data-ttu-id="ec601-297">Para especificar el punto de finalización, haga clic en <strong>Agregar condición</strong>.</span><span class="sxs-lookup"><span data-stu-id="ec601-297">To specify the ending point, click <strong>Add condition</strong>.</span></span> <span data-ttu-id="ec601-298">A continuación, especifique una condición que determine en qué parte de la jerarquía el sistema dejará de recuperar nombres.</span><span class="sxs-lookup"><span data-stu-id="ec601-298">Then enter a condition that determines where in the hierarchy the system stops retrieving names.</span></span></li>
    </ol></li>
    <li><span data-ttu-id="ec601-299">En la pestaña <strong>Opciones de jerarquía</strong>, especifique a qué usuarios del intervalo se debe remitir la decisión para una instancia superior:</span><span class="sxs-lookup"><span data-stu-id="ec601-299">On the <strong>Hierarchy options</strong> tab, specify which users in the range the decision should be escalated to:</span></span> <ul>
    <li><span data-ttu-id="ec601-300"><strong>Asignar a todos los usuarios recuperados</strong>: la decisión se remite para una instancia superior a todos los usuarios del intervalo.</span><span class="sxs-lookup"><span data-stu-id="ec601-300"><strong>Assign to all users retrieved</strong> – The decision is escalated to all users in the range.</span></span></li>
    <li><span data-ttu-id="ec601-301"><strong>Asignar sólo al último usuario recuperado</strong>: la decisión se remite para una instancia superior únicamente al último usuario del intervalo.</span><span class="sxs-lookup"><span data-stu-id="ec601-301"><strong>Assign only to last user retrieved</strong> – The decision is escalated to only the last user in the range.</span></span></li>
    <li><span data-ttu-id="ec601-302"><strong>Excluir usuarios con la siguiente condición</strong>: la decisión no se remite para una instancia superior a ninguno de los usuarios del intervalo que cumplen con una condición determinada.</span><span class="sxs-lookup"><span data-stu-id="ec601-302"><strong>Exclude users with the following condition:</strong> – The decision isn't escalated to any users in the range who meet a specific condition.</span></span> <span data-ttu-id="ec601-303">Haga clic en <strong>Agregar condición</strong> para especificar la condición.</span><span class="sxs-lookup"><span data-stu-id="ec601-303">Click <strong>Add condition</strong> to specify the condition.</span></span></li>
    </ul></li>
    </ol></td>
    </tr>
    <tr class="even">
    <td><span data-ttu-id="ec601-304">Usuario del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="ec601-304">Workflow user</span></span></td>
    <td><span data-ttu-id="ec601-305">Usuarios del flujo de trabajo actual</span><span class="sxs-lookup"><span data-stu-id="ec601-305">Users in the current workflow</span></span></td>
    <td><ul>
    <li><span data-ttu-id="ec601-306">Tras seleccionar <strong>Usuario del flujo de trabajo</strong>, en la pestaña <strong>Usuario del flujo de trabajo</strong>, en la pestaña <strong>Usuario del flujo de trabajo</strong>, seleccione un usuario que participe en el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="ec601-306">After you select <strong>Workflow user</strong>, on the <strong>Workflow user</strong> tab, in the <strong>Workflow user</strong> list, select a user who participates in the workflow.</span></span></li>
    </ul></td>
    </tr>
    <tr class="odd">
    <td><span data-ttu-id="ec601-307">Usuario</span><span class="sxs-lookup"><span data-stu-id="ec601-307">User</span></span></td>
    <td><span data-ttu-id="ec601-308">Usuarios específicos de Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="ec601-308">Specific Finance and Operations users</span></span></td>
    <td><ol>
    <li><span data-ttu-id="ec601-309">Tras seleccionar <strong>Usuario</strong>, haga clic en la pestaña <strong>Usuario</strong>.</span><span class="sxs-lookup"><span data-stu-id="ec601-309">After you select <strong>User</strong>, click the <strong>User</strong> tab.</span></span></li>
    <li><span data-ttu-id="ec601-310">La lista de <strong>Usuarios disponibles</strong> incluye a todos los usuarios de Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="ec601-310">The <strong>Available users</strong> list includes all Finance and Operations users.</span></span> <span data-ttu-id="ec601-311">Seleccione aquellos a los que desea remitir la decisión para una instancia superior y, a continuación, muévalos a la lista <strong>Usuarios seleccionados</strong>.</span><span class="sxs-lookup"><span data-stu-id="ec601-311">Select the users to escalate the decision to, and then move those users to the <strong>Selected users</strong> list.</span></span></li>
    </ol></td>
    </tr>
    </tbody>
    </table>

4.  <span data-ttu-id="ec601-312">En la pestaña **Límite de tiempo**, en el campo **Duración**, especifique el tiempo del que dispone el usuario para tomar la decisión.</span><span class="sxs-lookup"><span data-stu-id="ec601-312">On the **Time limit** tab, in the **Duration** field, specify how much time the user has to make the decision.</span></span> <span data-ttu-id="ec601-313">Seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="ec601-313">Select one of the following options:</span></span>
    -   <span data-ttu-id="ec601-314">**Horas**: escriba la cantidad de horas de las que dispone el usuario para tomar la decisión.</span><span class="sxs-lookup"><span data-stu-id="ec601-314">**Hours** – Enter the number of hours that the user has to make the decision.</span></span> <span data-ttu-id="ec601-315">A continuación, seleccione el calendario que usa la organización y escriba la información pertinente acerca de la semana laboral de la organización.</span><span class="sxs-lookup"><span data-stu-id="ec601-315">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    -   <span data-ttu-id="ec601-316">**Días**: escriba la cantidad de días de los que dispone el usuario para tomar la decisión.</span><span class="sxs-lookup"><span data-stu-id="ec601-316">**Days** – Enter the number of days that the user has to make the decision.</span></span> <span data-ttu-id="ec601-317">A continuación, seleccione el calendario que usa la organización y escriba la información pertinente acerca de la semana laboral de la organización.</span><span class="sxs-lookup"><span data-stu-id="ec601-317">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    -   <span data-ttu-id="ec601-318">**Semanas**: escriba la cantidad de semanas de las que dispone el usuario para tomar la decisión.</span><span class="sxs-lookup"><span data-stu-id="ec601-318">**Weeks** – Enter the number of weeks that the user has to make the decision.</span></span>
    -   <span data-ttu-id="ec601-319">**Meses**: seleccione el día y la semana antes de los cuales el usuario debe tomar la decisión.</span><span class="sxs-lookup"><span data-stu-id="ec601-319">**Months** – Select the day and week that the user must make the decision by.</span></span> <span data-ttu-id="ec601-320">Por ejemplo, tal vez desee que el usuario haya tomado la decisión antes del viernes de la tercera semana del mes.</span><span class="sxs-lookup"><span data-stu-id="ec601-320">For example, you might want the user to make the decision by Friday of the third week of the month.</span></span>
    -   <span data-ttu-id="ec601-321">**Años**: seleccione el día, la semana y el mes en los que vence el plazo para tomar la decisión.</span><span class="sxs-lookup"><span data-stu-id="ec601-321">**Years** – Select the day, week, and month that the user must make the decision by.</span></span> <span data-ttu-id="ec601-322">Por ejemplo, tal vez desee que el usuario haya tomado la decisión antes del viernes de la tercera semana de diciembre.</span><span class="sxs-lookup"><span data-stu-id="ec601-322">For example, you might want the user to make the decision by Friday of the third week of December.</span></span>

5.  <span data-ttu-id="ec601-323">Repita los pasos 3 a 4 por cada usuario que se debe agregar a la ruta de remisión a una instancia superior.</span><span class="sxs-lookup"><span data-stu-id="ec601-323">Repeat steps 3 through 4 for each user that should be added to the escalation path.</span></span> <span data-ttu-id="ec601-324">El orden de los usuarios se puede modificar.</span><span class="sxs-lookup"><span data-stu-id="ec601-324">You can change the order of the users.</span></span>
6.  <span data-ttu-id="ec601-325">Si los usuarios de la ruta de remisión a una instancia superior no toman la decisión en el tiempo asignado, lo hace el sistema.</span><span class="sxs-lookup"><span data-stu-id="ec601-325">If the users in the escalation path don't make the decision in the allotted time, the system makes the decision.</span></span> <span data-ttu-id="ec601-326">Para especificar la opción que el sistema selecciona, seleccione la fila **Acción** y, a continuación, en la pestaña **Finalizar acción**, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="ec601-326">To specify the option that the system selects, select the **Action** row, and then, on the **End action** tab, select an option.</span></span>

## <a name="set-a-time-limit"></a><span data-ttu-id="ec601-327">Definición de un límite de tiempo</span><span class="sxs-lookup"><span data-stu-id="ec601-327">Set a time limit</span></span>
<span data-ttu-id="ec601-328">Siga estos pasos si la decisión se debe tomar en un plazo específico.</span><span class="sxs-lookup"><span data-stu-id="ec601-328">Follow these steps if the decision must be made in a specific time.</span></span> <span data-ttu-id="ec601-329">**Nota:** Las opciones que seleccione en este procedimiento anulan las opciones elegidas en las áreas **Asignación** y **Remisión a una instancia superior** de la página.</span><span class="sxs-lookup"><span data-stu-id="ec601-329">**Note:** The options that you select in this procedure override the options that you selected in the **Assignment** and **Escalation** areas of the page.</span></span>

1.  <span data-ttu-id="ec601-330">En el panel izquiero, haga clic en **Configuración avanzada**.</span><span class="sxs-lookup"><span data-stu-id="ec601-330">In the left pane, click **Advanced settings**.</span></span>
2.  <span data-ttu-id="ec601-331">Active la casilla **Configurar un límite de tiempo para el elemento de flujo de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="ec601-331">Select the **Set a time limit for the workflow element** check box.</span></span>
3.  <span data-ttu-id="ec601-332">En el campo **Duración**, especifique cuándo se debe tomar la decisión.</span><span class="sxs-lookup"><span data-stu-id="ec601-332">In the **Duration** field, specify when the decision must be made.</span></span> <span data-ttu-id="ec601-333">Seleccione una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="ec601-333">Select one of the following options:</span></span>
    -   <span data-ttu-id="ec601-334">**Hora**: escriba la cantidad de horas.</span><span class="sxs-lookup"><span data-stu-id="ec601-334">**Hours** – Enter the number of hours.</span></span> <span data-ttu-id="ec601-335">A continuación, seleccione el calendario que usa la organización y escriba la información pertinente acerca de la semana laboral de la organización.</span><span class="sxs-lookup"><span data-stu-id="ec601-335">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    -   <span data-ttu-id="ec601-336">**Días**: escriba la cantidad de días.</span><span class="sxs-lookup"><span data-stu-id="ec601-336">**Days** – Enter the number of days.</span></span> <span data-ttu-id="ec601-337">A continuación, seleccione el calendario que usa la organización y escriba la información pertinente acerca de la semana laboral de la organización.</span><span class="sxs-lookup"><span data-stu-id="ec601-337">Then select the calendar that your organization uses, and enter information about your organization's work week.</span></span>
    -   <span data-ttu-id="ec601-338">**Semanas**: escriba la cantidad de semanas.</span><span class="sxs-lookup"><span data-stu-id="ec601-338">**Weeks** – Enter the number of weeks.</span></span>
    -   <span data-ttu-id="ec601-339">**Meses**: seleccione el día y la semana en los que vence el plazo para tomar la decisión.</span><span class="sxs-lookup"><span data-stu-id="ec601-339">**Months** – Select the day and week that the decision must be made by.</span></span> <span data-ttu-id="ec601-340">Por ejemplo, tal vez desee que la decisión se haya tomado antes del viernes de la tercera semana del mes.</span><span class="sxs-lookup"><span data-stu-id="ec601-340">For example, you might want the decision to be made by Friday of the third week of the month.</span></span>
    -   <span data-ttu-id="ec601-341">**Años**: seleccione el día, la semana y el mes en los que vence el plazo para tomar la decisión.</span><span class="sxs-lookup"><span data-stu-id="ec601-341">**Years** – Select the day, week, and month that the decision must be made by.</span></span> <span data-ttu-id="ec601-342">Por ejemplo, tal vez desee que la decisión se haya tomado antes del viernes de la tercera semana de diciembre.</span><span class="sxs-lookup"><span data-stu-id="ec601-342">For example, you might want the decision to be made by Friday of the third week of December.</span></span>

4.  <span data-ttu-id="ec601-343">Si se supera el límite de tiempo, el sistema toma la decisión.</span><span class="sxs-lookup"><span data-stu-id="ec601-343">If the time limit is exceeded, the system makes the decision.</span></span> <span data-ttu-id="ec601-344">En la lista **Acción**, seleccione la opción que debe seleccionar el sistema.</span><span class="sxs-lookup"><span data-stu-id="ec601-344">In the **Action** list, select the option that the system should select.</span></span>





