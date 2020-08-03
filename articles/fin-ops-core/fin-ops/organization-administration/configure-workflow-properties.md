---
title: Configurar propiedades del flujo de trabajo
description: Este tema explica cómo configurar las diversas propiedades de un flujo de trabajo.
author: sericks007
manager: AnnBe
ms.date: 07/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 196083
ms.assetid: 192b7a98-7d04-4c7a-a986-29d797a8a837
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 268448049955170b8eb9e64cbd50416565a041b1
ms.sourcegitcommit: 561d06c2a74602dfaa40334d8afac5053aebc055
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/07/2020
ms.locfileid: "3541118"
---
# <a name="configure-workflow-properties"></a><span data-ttu-id="2c3c6-103">Configurar propiedades del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="2c3c6-103">Configure workflow properties</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2c3c6-104">Este tema explica cómo configurar las diversas propiedades de un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-104">This topic explains how to configure the various properties of a workflow.</span></span>

<span data-ttu-id="2c3c6-105">Para configurar las propiedades de un flujo de trabajo, abra el flujo de trabajo en el editor de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-105">To configure the properties of a workflow, open the workflow in the workflow editor.</span></span> <span data-ttu-id="2c3c6-106">Haga clic en el lienzo del editor de flujos de trabajo y luego haga clic en **Propiedades** para abrir la página **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-106">Click the canvas of the workflow editor, and then click **Properties** to open the **Properties** page.</span></span> <span data-ttu-id="2c3c6-107">A continuación, puede usar los siguientes procedimientos para configurar las diversas propiedades del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-107">You can then use the following procedures to configure the various properties of the workflow.</span></span>

## <a name="name-the-workflow"></a><span data-ttu-id="2c3c6-108">Asignación de un nombre al flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="2c3c6-108">Name the workflow</span></span>

<span data-ttu-id="2c3c6-109">Siga estos pasos para asignar un nombre al flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-109">Follow these steps to enter a name for the workflow.</span></span>

1. <span data-ttu-id="2c3c6-110">En el panel izquierdo, haga clic en **Configuración básica**.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-110">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="2c3c6-111">En el campo **Nombre**, especifique un nombre exclusivo para el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-111">In the **Name** field, enter a unique name for the workflow.</span></span> <span data-ttu-id="2c3c6-112">Por ejemplo, si crea un flujo de trabajo de solicitud de compra para cada país o región en los que opera, puede llamar al flujo de trabajo de solicitud de compra **Solicitudes de compra Dinamarca** o **Solicitudes de compra España**.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-112">For example, if you create a purchase requisition workflow for each country/region that you operate in, you can name the purchase requisition workflow **Purchase Requisitions Denmark** or **Purchase Requisitions Spain**.</span></span>

## <a name="specify-the-workflow-owner"></a><span data-ttu-id="2c3c6-113">Especificación del propietario del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="2c3c6-113">Specify the workflow owner</span></span>

<span data-ttu-id="2c3c6-114">El propietario del flujo de trabajo es la persona que administra y mantiene el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-114">The workflow owner is the person who manages and maintains the workflow.</span></span> <span data-ttu-id="2c3c6-115">Siga estos pasos para especificar el propietario del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-115">Follow these steps to specify the workflow owner.</span></span>

1. <span data-ttu-id="2c3c6-116">En el panel izquierdo, haga clic en **Configuración básica**.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-116">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="2c3c6-117">En la lista **Propietario**, seleccione el nombre de la persona que administrará el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-117">In the **Owner** list, select the name of the person who will manage the workflow.</span></span>

## <a name="select-an-email-template"></a><span data-ttu-id="2c3c6-118">Selección de una plantilla de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="2c3c6-118">Select an email template</span></span>

<span data-ttu-id="2c3c6-119">Siga estos pasos para seleccionar la plantilla de correo electrónico que se usa para generar los mensajes de notificación sobre el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-119">Follow these steps to select the email template that is used to generate notification messages about the workflow.</span></span>

1. <span data-ttu-id="2c3c6-120">En el panel izquierdo, haga clic en **Configuración básica**.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-120">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="2c3c6-121">En la lista **Plantilla de correo electrónico para notificaciones de flujo de trabajo**, seleccione la plantilla.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-121">In the **Email template for workflow notifications** list, select the template.</span></span>

## <a name="enter-instructions-for-users"></a><span data-ttu-id="2c3c6-122">Especificación de las instrucciones para los usuarios</span><span class="sxs-lookup"><span data-stu-id="2c3c6-122">Enter instructions for users</span></span>

<span data-ttu-id="2c3c6-123">Puede proporcionar instrucciones a los usuarios que envían los documentos que se deben procesar y aprobar.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-123">You can provide instructions to users who submit documents for processing and approval.</span></span> <span data-ttu-id="2c3c6-124">A estos usuarios también se les conoce como *originadores*.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-124">These users are also referred to as *originators*.</span></span> <span data-ttu-id="2c3c6-125">Por ejemplo, está creando un flujo de trabajo de solicitudes de compra y especifica instrucciones.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-125">For example, you're creating a purchase requisition workflow, and you enter instructions.</span></span> <span data-ttu-id="2c3c6-126">Esas instrucciones se pueden ver entonces por los usuarios que especifican solicitudes de compra en la página **Solicitudes de compra**.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-126">Those instructions can then be viewed by users who enter purchase requisitions on the **Purchase requisitions** page.</span></span> <span data-ttu-id="2c3c6-127">Para consultar las instrucciones, el originador hace clic en el icono de la barra de mensajes del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-127">To view instructions, the originator clicks the icon in the workflow message bar.</span></span> <span data-ttu-id="2c3c6-128">Siga estos pasos para escribir las instrucciones para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-128">Follow these steps to enter instructions for users.</span></span>

1. <span data-ttu-id="2c3c6-129">En el panel izquierdo, haga clic en **Configuración básica**.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-129">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="2c3c6-130">En el campo **Instrucciones de envío**, escriba las instrucciones.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-130">In the **Submission instructions** field, enter the instructions.</span></span>
3. <span data-ttu-id="2c3c6-131">Para personalizar las instrucciones, puede insertar marcadores de posición.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-131">To personalize the instructions, you can insert placeholders.</span></span> <span data-ttu-id="2c3c6-132">Estos se reemplazan con los datos adecuados cuando las instrucciones se muestran a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-132">Placeholders are replaced with the appropriate data when the instructions are shown to users.</span></span> <span data-ttu-id="2c3c6-133">Para insertar un marcador de posición, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="2c3c6-133">To insert a placeholder, follow these steps:</span></span>

    1. <span data-ttu-id="2c3c6-134">Haga clic en el campo **Instrucciones de envío** para especificar dónde debe aparecer el marcador de posición.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-134">Click in the **Submission instructions** field to specify where the placeholder should appear.</span></span>
    2. <span data-ttu-id="2c3c6-135">Haga clic en **Insertar marcador de posición**.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-135">Click **Insert placeholder**.</span></span>
    3. <span data-ttu-id="2c3c6-136">En la lista que aparece, seleccione el marcador de posición que desea insertar.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-136">In the list that appears, select the placeholder to insert.</span></span>
    4. <span data-ttu-id="2c3c6-137">Haga clic en **Insertar**.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-137">Click **Insert**.</span></span>

4. <span data-ttu-id="2c3c6-138">Para agregar traducciones de las instrucciones, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="2c3c6-138">To add translations of the instructions, follow these steps:</span></span>

    1. <span data-ttu-id="2c3c6-139">Haga clic en **Traducciones**.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-139">Click **Translations**.</span></span>
    2. <span data-ttu-id="2c3c6-140">En la página que aparece, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-140">On the page that appears, click **Add**.</span></span>
    3. <span data-ttu-id="2c3c6-141">En la lista que aparece, seleccione el idioma en el que escribirá el texto.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-141">In the list that appears, select the language that you will enter the text in.</span></span>
    4. <span data-ttu-id="2c3c6-142">En el campo **Texto traducido**, escriba el texto.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-142">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="2c3c6-143">Para personalizar el texto, puede insertar marcadores de posición.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-143">To personalize the text, you can insert placeholders.</span></span> <span data-ttu-id="2c3c6-144">Para obtener instrucciones acerca de cómo agregar un marcador de posición, consulte el paso 3.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-144">For instructions about how to enter a placeholder, see step 3.</span></span>
    6. <span data-ttu-id="2c3c6-145">Haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-145">Click **Close**.</span></span>

## <a name="specify-when-this-workflow-is-used-through-activation-conditions"></a><span data-ttu-id="2c3c6-146">Especifique cuándo se usa este flujo de trabajo mediante condiciones de activación</span><span class="sxs-lookup"><span data-stu-id="2c3c6-146">Specify when this workflow is used through activation conditions</span></span>

<span data-ttu-id="2c3c6-147">Puede crear varios flujos de trabajo que estén basados en el mismo tipo de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-147">You can create multiple workflows that are based on the same workflow type.</span></span> <span data-ttu-id="2c3c6-148">Cuando existen varios flujos de trabajo basados en el mismo tipo, debe especificar cuándo se usa cada uno usando condiciones de activación.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-148">When you have multiple workflows that are based on the same type, you must specify when each workflow is used using activation conditions.</span></span> <span data-ttu-id="2c3c6-149">Si no se cumplen las condiciones de activación, se utiliza el flujo de trabajo predeterminado.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-149">If activation conditions are not met, then the default workflow is used.</span></span> <span data-ttu-id="2c3c6-150">De manera similar, si solo hay una configuración de flujo de trabajo definida para un tipo de flujo de trabajo, entonces esa configuración de flujo de trabajo se usará independientemente de las condiciones de activación.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-150">Similarly, if there is only one workflow configuration defined for a workflow type, then that workflow configuration will be used regardless of the activation conditions.</span></span>

<span data-ttu-id="2c3c6-151">Por ejemplo, puede crear un flujo de trabajo de solicitudes de compra para cada país o región en los que opera como, por ejemplo, Solicitudes de compra Dinamarca y Solicitudes de compra España, con las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="2c3c6-151">For example, you can create a purchase requisition workflow for each country/region that you operate in, such as Purchase Requisitions Denmark and Purchase Requisitions Spain, with the following conditions:</span></span>

- <span data-ttu-id="2c3c6-152">Se usa Solicitudes de compra Dinamarca cuando: país/región = DK</span><span class="sxs-lookup"><span data-stu-id="2c3c6-152">Purchase Requisitions Denmark is used when: country/region = DK</span></span>
- <span data-ttu-id="2c3c6-153">Se usa Solicitudes de compra España cuando: país/región = ES</span><span class="sxs-lookup"><span data-stu-id="2c3c6-153">Purchase Requisitions Spain is used when: country/region = ES</span></span>

<span data-ttu-id="2c3c6-154">Siga estos pasos para especificar cuándo se usa el flujo de trabajo que está configurando.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-154">Follow these steps to specify when the workflow that you're configuring is used.</span></span>

1. <span data-ttu-id="2c3c6-155">En el panel izquierdo, haga clic en **Activación**.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-155">In the left pane, click **Activation**.</span></span>
2. <span data-ttu-id="2c3c6-156">Active la casilla **Establecer condiciones para ejecutar este flujo de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-156">Select the **Set the conditions for running this workflow** check box.</span></span>
3. <span data-ttu-id="2c3c6-157">Haga clic en **Agregar condición**.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-157">Click **Add condition**.</span></span>
4. <span data-ttu-id="2c3c6-158">Escriba una condición.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-158">Enter a condition.</span></span>
5. <span data-ttu-id="2c3c6-159">Escriba condiciones adicionales que sean necesarias.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-159">Enter any additional conditions that are required.</span></span>
6. <span data-ttu-id="2c3c6-160">Revise el flujo de trabajo con algunos registros de destino para comprobar que la condición incluya y excluya correctamente los registros.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-160">Run through the workflow with some target records to verify that the condition correctly includes and excludes records.</span></span>

## <a name="specify-when-notifications-are-sent"></a><span data-ttu-id="2c3c6-161">Especificación del momento en que se envían notificaciones</span><span class="sxs-lookup"><span data-stu-id="2c3c6-161">Specify when notifications are sent</span></span>

<span data-ttu-id="2c3c6-162">Cuando se envía un documento para que se lo procese, se crea una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-162">When a document is submitted for processing, a workflow instance is created.</span></span> <span data-ttu-id="2c3c6-163">Puede enviar notificaciones a los usuarios para indicar el inicio, la finalización, la terminación o la detención debido a un error de las instancias de flujo de trabajo basadas en el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-163">You can send notifications to users when workflow instances that are based on the workflow are started, completed, terminated, or stopped because of an error.</span></span> <span data-ttu-id="2c3c6-164">Siga estos pasos para especificar cuándo se envían notificaciones.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-164">Follow these steps to specify when notifications are sent.</span></span>

1. <span data-ttu-id="2c3c6-165">En el panel izquierdo, haga clic en **Notificaciones**.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-165">In the left pane, click **Notifications**.</span></span>
2. <span data-ttu-id="2c3c6-166">Active las casillas de verificación correspondientes a los eventos que deben desencadenar las notificaciones:</span><span class="sxs-lookup"><span data-stu-id="2c3c6-166">Select the check box for each event that should trigger notifications:</span></span>

    - <span data-ttu-id="2c3c6-167">**Iniciado**: enviar notificaciones cuando se inicia una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-167">**Started** – Send notifications when a workflow instance is started.</span></span>
    - <span data-ttu-id="2c3c6-168">**Detenido**: enviar notificaciones cuando una instancia de flujo de trabajo se detiene debido a un error.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-168">**Stopped** – Send notifications when a workflow instance is stopped because of an error.</span></span>
    - <span data-ttu-id="2c3c6-169">**Completado**: enviar notificaciones cuando se completa una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-169">**Completed** – Send notifications when a workflow instance is completed.</span></span>
    - <span data-ttu-id="2c3c6-170">**Irrecuperable**: enviar notificaciones cuando una instancia de flujo de trabajo se detiene debido a un error irrecuperable.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-170">**Unrecoverable** – Send notifications when a workflow instance is stopped because of an unrecoverable error.</span></span>
    - <span data-ttu-id="2c3c6-171">**Terminado**: enviar notificaciones cuando finaliza una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-171">**Terminated** – Send notifications when a workflow instance is terminated.</span></span>

3. <span data-ttu-id="2c3c6-172">Seleccione la fila correspondiente a uno de los eventos que seleccionó en el paso 2.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-172">Select the row for an event that you selected in step 2.</span></span>
4. <span data-ttu-id="2c3c6-173">En la pestaña **Texto de notificación**, escriba el texto de la notificación.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-173">On the **Notification text** tab, enter the text of the notification.</span></span>
5. <span data-ttu-id="2c3c6-174">Para personalizar el texto, puede insertar marcadores de posición.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-174">To personalize the text, you can insert placeholders.</span></span> <span data-ttu-id="2c3c6-175">Estos se reemplazan con los datos adecuados cuando se muestra el texto a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-175">Placeholders are replaced with the appropriate data when the text is shown to users.</span></span> <span data-ttu-id="2c3c6-176">Para insertar un marcador de posición, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="2c3c6-176">To insert a placeholder, follow these steps:</span></span>

    1. <span data-ttu-id="2c3c6-177">Haga clic en el campo para especificar dónde debe aparecer el marcador de posición.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-177">Click in the field to specify where the placeholder should appear.</span></span>
    2. <span data-ttu-id="2c3c6-178">Haga clic en **Insertar marcador de posición**.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-178">Click **Insert placeholder**.</span></span>
    3. <span data-ttu-id="2c3c6-179">En la lista que aparece, seleccione el marcador de posición que desea insertar.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-179">In the list that appears, select the placeholder to insert.</span></span>
    4. <span data-ttu-id="2c3c6-180">Haga clic en **Insertar**.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-180">Click **Insert**.</span></span>
    5. <span data-ttu-id="2c3c6-181">Un marcador de posición **Texto de notificación** común para incluir es "Últimas notas: %Workflow.Last note%", que muestra cualquier comentario del paso anterior.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-181">A common **Notification text** placeholder to include is "Last Notes: %Workflow.Last note%", which displays any comments from the previous step.</span></span>

6. <span data-ttu-id="2c3c6-182">Para agregar traducciones del texto, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="2c3c6-182">To add translations of the text, follow these steps:</span></span>

    1. <span data-ttu-id="2c3c6-183">Haga clic en **Traducciones**.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-183">Click **Translations**.</span></span>
    2. <span data-ttu-id="2c3c6-184">En la página que aparece, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-184">On the page that appears, Click **Add**.</span></span>
    3. <span data-ttu-id="2c3c6-185">En la lista que aparece, seleccione el idioma en el que escribirá el texto.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-185">In the list that appears, select the language that you will enter the text in.</span></span>
    4. <span data-ttu-id="2c3c6-186">En el campo **Texto traducido**, escriba el texto.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-186">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="2c3c6-187">Para personalizar el texto, puede insertar marcadores de posición.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-187">To personalize the text, you can insert placeholders.</span></span> <span data-ttu-id="2c3c6-188">Para obtener instrucciones acerca de cómo agregar un marcador de posición, consulte el paso 5.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-188">For instructions about how to enter a placeholder, see step 5.</span></span>
    6. <span data-ttu-id="2c3c6-189">Haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-189">Click **Close**.</span></span>

7. <span data-ttu-id="2c3c6-190">En la pestaña **Destinatario**, utilice las siguientes opciones para especificar quién debe recibir las notificaciones.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-190">On the **Recipient** tab, use the following options to specify who should receive the notifications.</span></span>

    <table>
    <thead>
    <tr>
    <th><span data-ttu-id="2c3c6-191">Opción</span><span class="sxs-lookup"><span data-stu-id="2c3c6-191">Option</span></span></th>
    <th><span data-ttu-id="2c3c6-192">Las notificaciones se envían a estos usuarios</span><span class="sxs-lookup"><span data-stu-id="2c3c6-192">Notifications are sent to these users</span></span></th>
    <th><span data-ttu-id="2c3c6-193">Para enviar notificaciones, siga estos pasos</span><span class="sxs-lookup"><span data-stu-id="2c3c6-193">To send notifications, follow these steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td><span data-ttu-id="2c3c6-194">Participante</span><span class="sxs-lookup"><span data-stu-id="2c3c6-194">Participant</span></span></td>
    <td><span data-ttu-id="2c3c6-195">Usuarios asignados a un grupo o rol específicos</span><span class="sxs-lookup"><span data-stu-id="2c3c6-195">Users who are assigned to a specific group or role</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="2c3c6-196">En la pestaña <strong>Destinatario</strong>, haga clic en <strong>Participante</strong>.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-196">On the <strong>Recipient</strong> tab, click <strong>Participant</strong>.</span></span></li>
    <li><span data-ttu-id="2c3c6-197">En la pestaña <strong>Basado en funciones</strong>, en la lista <strong>Tipo de participante</strong>, seleccione el tipo de grupo o rol al que desea enviar las notificaciones.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-197">On the <strong>Role based</strong> tab, in the <strong>Type of participant</strong> list, select the type of group or role to send notifications to.</span></span></li>
    <li><span data-ttu-id="2c3c6-198">En la lista <strong>Participante</strong>, seleccione el grupo o rol al que se deben enviar las notificaciones.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-198">In the <strong>Participant</strong> list, select the group or role to send notifications to.</span></span></li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="2c3c6-199">Usuario del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="2c3c6-199">Workflow user</span></span></td>
    <td><span data-ttu-id="2c3c6-200">Usuarios que participan en el flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="2c3c6-200">Users who are participants in this workflow</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="2c3c6-201">En la ficha <strong>Destinatario</strong>, haga clic en <strong>Usuario del flujo de trabajo</strong>.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-201">On the <strong>Recipient</strong> tab, click <strong>Workflow user</strong>.</span></span></li>
    <li><span data-ttu-id="2c3c6-202">En la pestaña <strong>Usuario del flujo de trabajo</strong>, en la lista <strong>Usuario del flujo de trabajo</strong>, seleccione un participante de este flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-202">On the <strong>Workflow user</strong> tab, in the <strong>Workflow user</strong> list, select a participant in this workflow.</span></span></li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="2c3c6-203">Usuario</span><span class="sxs-lookup"><span data-stu-id="2c3c6-203">User</span></span></td>
    <td><span data-ttu-id="2c3c6-204">Usuarios concretos</span><span class="sxs-lookup"><span data-stu-id="2c3c6-204">Specific users</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="2c3c6-205">En la ficha <strong>Destinatario</strong>, haga clic en <strong>Usuario</strong>.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-205">On the <strong>Recipient</strong> tab, click <strong>User</strong>.</span></span></li>
    <li><span data-ttu-id="2c3c6-206">En la pestaña <strong>Usuario</strong>, la lista <strong>Usuarios disponibles</strong> incluye todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-206">On the <strong>User</strong> tab, the <strong>Available users</strong> list includes all users.</span></span> <span data-ttu-id="2c3c6-207">Seleccione aquellos a los que desea enviar notificaciones y muévalos a la lista <strong>Usuarios seleccionados</strong>.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-207">Select the users to send notifications to, and move those users into the <strong>Selected users</strong> list.</span></span></li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

8. <span data-ttu-id="2c3c6-208">Repita los pasos 3 a 7 por cada uno de los eventos que haya seleccionado en el paso 2.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-208">Repeat steps 3 through 7 for each event that you selected in step 2.</span></span>

## <a name="enter-comments-about-the-changes-that-you-made-to-the-workflow"></a><span data-ttu-id="2c3c6-209">Escriba comentarios acerca de los cambios que realizó en el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-209">Enter comments about the changes that you made to the workflow</span></span>

<span data-ttu-id="2c3c6-210">Para escribir comentarios acerca de los cambios que realizó en el flujo de trabajo, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-210">To enter comments about the changes that you made to the workflow, follow these steps.</span></span>

1. <span data-ttu-id="2c3c6-211">En el panel izquierdo, haga clic en **Notas**.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-211">In the left pane, click **Notes**.</span></span>
2. <span data-ttu-id="2c3c6-212">En el campo **Especificar comentarios sobre el flujo de trabajo**, escriba sus comentarios.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-212">In the **Enter comments about the workflow** field, enter your comments.</span></span>
3. <span data-ttu-id="2c3c6-213">Revise los comentarios:</span><span class="sxs-lookup"><span data-stu-id="2c3c6-213">Review your comments.</span></span> <span data-ttu-id="2c3c6-214">una vez agregados, no podrá modificarlos.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-214">After you add comments, you can't modify them.</span></span>
4. <span data-ttu-id="2c3c6-215">Haga **Agregar** clic en para agregar sus comentarios al área **Historial de comentarios**.</span><span class="sxs-lookup"><span data-stu-id="2c3c6-215">Click **Add** to add your comments to the **Comment history** area.</span></span>
