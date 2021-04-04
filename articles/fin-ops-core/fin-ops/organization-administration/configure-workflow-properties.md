---
title: Configurar propiedades del flujo de trabajo
description: Este tema explica cómo configurar las diversas propiedades de un flujo de trabajo.
author: ChrisGarty
manager: AnnBe
ms.date: 07/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 196083
ms.assetid: 192b7a98-7d04-4c7a-a986-29d797a8a837
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 40118f329a676ffb30870eb882d127e3eb258599
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "5566976"
---
# <a name="configure-workflow-properties"></a><span data-ttu-id="57a8e-103">Configurar propiedades del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="57a8e-103">Configure workflow properties</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="57a8e-104">Este tema explica cómo configurar las diversas propiedades de un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="57a8e-104">This topic explains how to configure the various properties of a workflow.</span></span>

<span data-ttu-id="57a8e-105">Para configurar las propiedades de un flujo de trabajo, abra el flujo de trabajo en el editor de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="57a8e-105">To configure the properties of a workflow, open the workflow in the workflow editor.</span></span> <span data-ttu-id="57a8e-106">Haga clic en el lienzo del editor de flujos de trabajo y luego haga clic en **Propiedades** para abrir la página **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="57a8e-106">Click the canvas of the workflow editor, and then click **Properties** to open the **Properties** page.</span></span> <span data-ttu-id="57a8e-107">A continuación, puede usar los siguientes procedimientos para configurar las diversas propiedades del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="57a8e-107">You can then use the following procedures to configure the various properties of the workflow.</span></span>

## <a name="name-the-workflow"></a><span data-ttu-id="57a8e-108">Asignación de un nombre al flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="57a8e-108">Name the workflow</span></span>

<span data-ttu-id="57a8e-109">Siga estos pasos para asignar un nombre al flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="57a8e-109">Follow these steps to enter a name for the workflow.</span></span>

1. <span data-ttu-id="57a8e-110">En el panel izquierdo, haga clic en **Configuración básica**.</span><span class="sxs-lookup"><span data-stu-id="57a8e-110">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="57a8e-111">En el campo **Nombre**, especifique un nombre exclusivo para el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="57a8e-111">In the **Name** field, enter a unique name for the workflow.</span></span> <span data-ttu-id="57a8e-112">Por ejemplo, si crea un flujo de trabajo de solicitud de compra para cada país o región en los que opera, puede llamar al flujo de trabajo de solicitud de compra **Solicitudes de compra Dinamarca** o **Solicitudes de compra España**.</span><span class="sxs-lookup"><span data-stu-id="57a8e-112">For example, if you create a purchase requisition workflow for each country/region that you operate in, you can name the purchase requisition workflow **Purchase Requisitions Denmark** or **Purchase Requisitions Spain**.</span></span>

## <a name="specify-the-workflow-owner"></a><span data-ttu-id="57a8e-113">Especificación del propietario del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="57a8e-113">Specify the workflow owner</span></span>

<span data-ttu-id="57a8e-114">El propietario del flujo de trabajo es la persona que administra y mantiene el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="57a8e-114">The workflow owner is the person who manages and maintains the workflow.</span></span> <span data-ttu-id="57a8e-115">Siga estos pasos para especificar el propietario del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="57a8e-115">Follow these steps to specify the workflow owner.</span></span>

1. <span data-ttu-id="57a8e-116">En el panel izquierdo, haga clic en **Configuración básica**.</span><span class="sxs-lookup"><span data-stu-id="57a8e-116">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="57a8e-117">En la lista **Propietario**, seleccione el nombre de la persona que administrará el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="57a8e-117">In the **Owner** list, select the name of the person who will manage the workflow.</span></span>

## <a name="select-an-email-template"></a><span data-ttu-id="57a8e-118">Selección de una plantilla de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="57a8e-118">Select an email template</span></span>

<span data-ttu-id="57a8e-119">Siga estos pasos para seleccionar la plantilla de correo electrónico que se usa para generar los mensajes de notificación sobre el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="57a8e-119">Follow these steps to select the email template that is used to generate notification messages about the workflow.</span></span>

1. <span data-ttu-id="57a8e-120">En el panel izquierdo, haga clic en **Configuración básica**.</span><span class="sxs-lookup"><span data-stu-id="57a8e-120">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="57a8e-121">En la lista **Plantilla de correo electrónico para notificaciones de flujo de trabajo**, seleccione la plantilla.</span><span class="sxs-lookup"><span data-stu-id="57a8e-121">In the **Email template for workflow notifications** list, select the template.</span></span>

## <a name="enter-instructions-for-users"></a><span data-ttu-id="57a8e-122">Especificación de las instrucciones para los usuarios</span><span class="sxs-lookup"><span data-stu-id="57a8e-122">Enter instructions for users</span></span>

<span data-ttu-id="57a8e-123">Puede proporcionar instrucciones a los usuarios que envían los documentos que se deben procesar y aprobar.</span><span class="sxs-lookup"><span data-stu-id="57a8e-123">You can provide instructions to users who submit documents for processing and approval.</span></span> <span data-ttu-id="57a8e-124">A estos usuarios también se les conoce como *originadores*.</span><span class="sxs-lookup"><span data-stu-id="57a8e-124">These users are also referred to as *originators*.</span></span> <span data-ttu-id="57a8e-125">Por ejemplo, está creando un flujo de trabajo de solicitudes de compra y especifica instrucciones.</span><span class="sxs-lookup"><span data-stu-id="57a8e-125">For example, you're creating a purchase requisition workflow, and you enter instructions.</span></span> <span data-ttu-id="57a8e-126">Esas instrucciones se pueden ver entonces por los usuarios que especifican solicitudes de compra en la página **Solicitudes de compra**.</span><span class="sxs-lookup"><span data-stu-id="57a8e-126">Those instructions can then be viewed by users who enter purchase requisitions on the **Purchase requisitions** page.</span></span> <span data-ttu-id="57a8e-127">Para consultar las instrucciones, el originador hace clic en el icono de la barra de mensajes del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="57a8e-127">To view instructions, the originator clicks the icon in the workflow message bar.</span></span> <span data-ttu-id="57a8e-128">Siga estos pasos para escribir las instrucciones para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="57a8e-128">Follow these steps to enter instructions for users.</span></span>

1. <span data-ttu-id="57a8e-129">En el panel izquierdo, haga clic en **Configuración básica**.</span><span class="sxs-lookup"><span data-stu-id="57a8e-129">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="57a8e-130">En el campo **Instrucciones de envío**, escriba las instrucciones.</span><span class="sxs-lookup"><span data-stu-id="57a8e-130">In the **Submission instructions** field, enter the instructions.</span></span>
3. <span data-ttu-id="57a8e-131">Para personalizar las instrucciones, puede insertar marcadores de posición.</span><span class="sxs-lookup"><span data-stu-id="57a8e-131">To personalize the instructions, you can insert placeholders.</span></span> <span data-ttu-id="57a8e-132">Estos se reemplazan con los datos adecuados cuando las instrucciones se muestran a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="57a8e-132">Placeholders are replaced with the appropriate data when the instructions are shown to users.</span></span> <span data-ttu-id="57a8e-133">Para insertar un marcador de posición, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="57a8e-133">To insert a placeholder, follow these steps:</span></span>

    1. <span data-ttu-id="57a8e-134">Haga clic en el campo **Instrucciones de envío** para especificar dónde debe aparecer el marcador de posición.</span><span class="sxs-lookup"><span data-stu-id="57a8e-134">Click in the **Submission instructions** field to specify where the placeholder should appear.</span></span>
    2. <span data-ttu-id="57a8e-135">Haga clic en **Insertar marcador de posición**.</span><span class="sxs-lookup"><span data-stu-id="57a8e-135">Click **Insert placeholder**.</span></span>
    3. <span data-ttu-id="57a8e-136">En la lista que aparece, seleccione el marcador de posición que desea insertar.</span><span class="sxs-lookup"><span data-stu-id="57a8e-136">In the list that appears, select the placeholder to insert.</span></span>
    4. <span data-ttu-id="57a8e-137">Haga clic en **Insertar**.</span><span class="sxs-lookup"><span data-stu-id="57a8e-137">Click **Insert**.</span></span>

4. <span data-ttu-id="57a8e-138">Para agregar traducciones de las instrucciones, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="57a8e-138">To add translations of the instructions, follow these steps:</span></span>

    1. <span data-ttu-id="57a8e-139">Haga clic en **Traducciones**.</span><span class="sxs-lookup"><span data-stu-id="57a8e-139">Click **Translations**.</span></span>
    2. <span data-ttu-id="57a8e-140">En la página que aparece, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="57a8e-140">On the page that appears, click **Add**.</span></span>
    3. <span data-ttu-id="57a8e-141">En la lista que aparece, seleccione el idioma en el que escribirá el texto.</span><span class="sxs-lookup"><span data-stu-id="57a8e-141">In the list that appears, select the language that you will enter the text in.</span></span>
    4. <span data-ttu-id="57a8e-142">En el campo **Texto traducido**, escriba el texto.</span><span class="sxs-lookup"><span data-stu-id="57a8e-142">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="57a8e-143">Para personalizar el texto, puede insertar marcadores de posición.</span><span class="sxs-lookup"><span data-stu-id="57a8e-143">To personalize the text, you can insert placeholders.</span></span> <span data-ttu-id="57a8e-144">Para obtener instrucciones acerca de cómo agregar un marcador de posición, consulte el paso 3.</span><span class="sxs-lookup"><span data-stu-id="57a8e-144">For instructions about how to enter a placeholder, see step 3.</span></span>
    6. <span data-ttu-id="57a8e-145">Haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="57a8e-145">Click **Close**.</span></span>

> [!NOTE]
> <span data-ttu-id="57a8e-146">Los marcadores de posición no se pueden agregar usando copiar y pegar porque la información de destino no se pega correctamente.</span><span class="sxs-lookup"><span data-stu-id="57a8e-146">Placeholders cannot be added using copy and paste because the target information is not pasted in correctly.</span></span> <span data-ttu-id="57a8e-147">Utilice la interfaz para agregar marcadores de posición.</span><span class="sxs-lookup"><span data-stu-id="57a8e-147">Use the interface to add placeholders.</span></span>

## <a name="specify-when-this-workflow-is-used-through-activation-conditions"></a><span data-ttu-id="57a8e-148">Especifique cuándo se usa este flujo de trabajo mediante condiciones de activación</span><span class="sxs-lookup"><span data-stu-id="57a8e-148">Specify when this workflow is used through activation conditions</span></span>

<span data-ttu-id="57a8e-149">Puede crear varios flujos de trabajo que estén basados en el mismo tipo de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="57a8e-149">You can create multiple workflows that are based on the same workflow type.</span></span> <span data-ttu-id="57a8e-150">Cuando existen varios flujos de trabajo basados en el mismo tipo, debe especificar cuándo se usa cada uno usando condiciones de activación.</span><span class="sxs-lookup"><span data-stu-id="57a8e-150">When you have multiple workflows that are based on the same type, you must specify when each workflow is used using activation conditions.</span></span> <span data-ttu-id="57a8e-151">Si no se cumplen las condiciones de activación, se utiliza el flujo de trabajo predeterminado.</span><span class="sxs-lookup"><span data-stu-id="57a8e-151">If activation conditions are not met, then the default workflow is used.</span></span> <span data-ttu-id="57a8e-152">De manera similar, si solo hay una configuración de flujo de trabajo definida para un tipo de flujo de trabajo, entonces esa configuración de flujo de trabajo se usará independientemente de las condiciones de activación.</span><span class="sxs-lookup"><span data-stu-id="57a8e-152">Similarly, if there is only one workflow configuration defined for a workflow type, then that workflow configuration will be used regardless of the activation conditions.</span></span>

<span data-ttu-id="57a8e-153">Por ejemplo, puede crear un flujo de trabajo de solicitudes de compra para cada país o región en los que opera como, por ejemplo, Solicitudes de compra Dinamarca y Solicitudes de compra España, con las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="57a8e-153">For example, you can create a purchase requisition workflow for each country/region that you operate in, such as Purchase Requisitions Denmark and Purchase Requisitions Spain, with the following conditions:</span></span>

- <span data-ttu-id="57a8e-154">Se usa Solicitudes de compra Dinamarca cuando: país/región = DK</span><span class="sxs-lookup"><span data-stu-id="57a8e-154">Purchase Requisitions Denmark is used when: country/region = DK</span></span>
- <span data-ttu-id="57a8e-155">Se usa Solicitudes de compra España cuando: país/región = ES</span><span class="sxs-lookup"><span data-stu-id="57a8e-155">Purchase Requisitions Spain is used when: country/region = ES</span></span>

<span data-ttu-id="57a8e-156">Siga estos pasos para especificar cuándo se usa el flujo de trabajo que está configurando.</span><span class="sxs-lookup"><span data-stu-id="57a8e-156">Follow these steps to specify when the workflow that you're configuring is used.</span></span>

1. <span data-ttu-id="57a8e-157">En el panel izquierdo, haga clic en **Activación**.</span><span class="sxs-lookup"><span data-stu-id="57a8e-157">In the left pane, click **Activation**.</span></span>
2. <span data-ttu-id="57a8e-158">Active la casilla **Establecer condiciones para ejecutar este flujo de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="57a8e-158">Select the **Set the conditions for running this workflow** check box.</span></span>
3. <span data-ttu-id="57a8e-159">Haga clic en **Agregar condición**.</span><span class="sxs-lookup"><span data-stu-id="57a8e-159">Click **Add condition**.</span></span>
4. <span data-ttu-id="57a8e-160">Escriba una condición.</span><span class="sxs-lookup"><span data-stu-id="57a8e-160">Enter a condition.</span></span>
5. <span data-ttu-id="57a8e-161">Escriba condiciones adicionales que sean necesarias.</span><span class="sxs-lookup"><span data-stu-id="57a8e-161">Enter any additional conditions that are required.</span></span>
6. <span data-ttu-id="57a8e-162">Revise el flujo de trabajo con algunos registros de destino para comprobar que la condición incluya y excluya correctamente los registros.</span><span class="sxs-lookup"><span data-stu-id="57a8e-162">Run through the workflow with some target records to verify that the condition correctly includes and excludes records.</span></span>

## <a name="specify-when-notifications-are-sent"></a><span data-ttu-id="57a8e-163">Especificación del momento en que se envían notificaciones</span><span class="sxs-lookup"><span data-stu-id="57a8e-163">Specify when notifications are sent</span></span>

<span data-ttu-id="57a8e-164">Cuando se envía un documento para que se lo procese, se crea una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="57a8e-164">When a document is submitted for processing, a workflow instance is created.</span></span> <span data-ttu-id="57a8e-165">Puede enviar notificaciones a los usuarios para indicar el inicio, la finalización, la terminación o la detención debido a un error de las instancias de flujo de trabajo basadas en el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="57a8e-165">You can send notifications to users when workflow instances that are based on the workflow are started, completed, terminated, or stopped because of an error.</span></span> <span data-ttu-id="57a8e-166">Siga estos pasos para especificar cuándo se envían notificaciones.</span><span class="sxs-lookup"><span data-stu-id="57a8e-166">Follow these steps to specify when notifications are sent.</span></span>

1. <span data-ttu-id="57a8e-167">En el panel izquierdo, haga clic en **Notificaciones**.</span><span class="sxs-lookup"><span data-stu-id="57a8e-167">In the left pane, click **Notifications**.</span></span>
2. <span data-ttu-id="57a8e-168">Active las casillas de verificación correspondientes a los eventos que deben desencadenar las notificaciones:</span><span class="sxs-lookup"><span data-stu-id="57a8e-168">Select the check box for each event that should trigger notifications:</span></span>

    - <span data-ttu-id="57a8e-169">**Iniciado**: enviar notificaciones cuando se inicia una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="57a8e-169">**Started** – Send notifications when a workflow instance is started.</span></span>
    - <span data-ttu-id="57a8e-170">**Detenido**: enviar notificaciones cuando una instancia de flujo de trabajo se detiene debido a un error.</span><span class="sxs-lookup"><span data-stu-id="57a8e-170">**Stopped** – Send notifications when a workflow instance is stopped because of an error.</span></span>
    - <span data-ttu-id="57a8e-171">**Completado**: enviar notificaciones cuando se completa una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="57a8e-171">**Completed** – Send notifications when a workflow instance is completed.</span></span>
    - <span data-ttu-id="57a8e-172">**Irrecuperable**: enviar notificaciones cuando una instancia de flujo de trabajo se detiene debido a un error irrecuperable.</span><span class="sxs-lookup"><span data-stu-id="57a8e-172">**Unrecoverable** – Send notifications when a workflow instance is stopped because of an unrecoverable error.</span></span>
    - <span data-ttu-id="57a8e-173">**Terminado**: enviar notificaciones cuando finaliza una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="57a8e-173">**Terminated** – Send notifications when a workflow instance is terminated.</span></span>

3. <span data-ttu-id="57a8e-174">Seleccione la fila correspondiente a uno de los eventos que seleccionó en el paso 2.</span><span class="sxs-lookup"><span data-stu-id="57a8e-174">Select the row for an event that you selected in step 2.</span></span>
4. <span data-ttu-id="57a8e-175">En la pestaña **Texto de notificación**, escriba el texto de la notificación.</span><span class="sxs-lookup"><span data-stu-id="57a8e-175">On the **Notification text** tab, enter the text of the notification.</span></span>
5. <span data-ttu-id="57a8e-176">Para personalizar el texto, puede insertar marcadores de posición.</span><span class="sxs-lookup"><span data-stu-id="57a8e-176">To personalize the text, you can insert placeholders.</span></span> <span data-ttu-id="57a8e-177">Estos se reemplazan con los datos adecuados cuando se muestra el texto a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="57a8e-177">Placeholders are replaced with the appropriate data when the text is shown to users.</span></span> <span data-ttu-id="57a8e-178">Para insertar un marcador de posición, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="57a8e-178">To insert a placeholder, follow these steps:</span></span>

    1. <span data-ttu-id="57a8e-179">Haga clic en el campo para especificar dónde debe aparecer el marcador de posición.</span><span class="sxs-lookup"><span data-stu-id="57a8e-179">Click in the field to specify where the placeholder should appear.</span></span>
    2. <span data-ttu-id="57a8e-180">Haga clic en **Insertar marcador de posición**.</span><span class="sxs-lookup"><span data-stu-id="57a8e-180">Click **Insert placeholder**.</span></span>
    3. <span data-ttu-id="57a8e-181">En la lista que aparece, seleccione el marcador de posición que desea insertar.</span><span class="sxs-lookup"><span data-stu-id="57a8e-181">In the list that appears, select the placeholder to insert.</span></span>
    4. <span data-ttu-id="57a8e-182">Haga clic en **Insertar**.</span><span class="sxs-lookup"><span data-stu-id="57a8e-182">Click **Insert**.</span></span>
    5. <span data-ttu-id="57a8e-183">Un marcador de posición **Texto de notificación** común para incluir es "Últimas notas: %Workflow.Last note%", que muestra cualquier comentario del paso anterior.</span><span class="sxs-lookup"><span data-stu-id="57a8e-183">A common **Notification text** placeholder to include is "Last Notes: %Workflow.Last note%", which displays any comments from the previous step.</span></span>

6. <span data-ttu-id="57a8e-184">Para agregar traducciones del texto, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="57a8e-184">To add translations of the text, follow these steps:</span></span>

    1. <span data-ttu-id="57a8e-185">Haga clic en **Traducciones**.</span><span class="sxs-lookup"><span data-stu-id="57a8e-185">Click **Translations**.</span></span>
    2. <span data-ttu-id="57a8e-186">En la página que aparece, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="57a8e-186">On the page that appears, Click **Add**.</span></span>
    3. <span data-ttu-id="57a8e-187">En la lista que aparece, seleccione el idioma en el que escribirá el texto.</span><span class="sxs-lookup"><span data-stu-id="57a8e-187">In the list that appears, select the language that you will enter the text in.</span></span>
    4. <span data-ttu-id="57a8e-188">En el campo **Texto traducido**, escriba el texto.</span><span class="sxs-lookup"><span data-stu-id="57a8e-188">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="57a8e-189">Para personalizar el texto, puede insertar marcadores de posición.</span><span class="sxs-lookup"><span data-stu-id="57a8e-189">To personalize the text, you can insert placeholders.</span></span> <span data-ttu-id="57a8e-190">Para obtener instrucciones acerca de cómo agregar un marcador de posición, consulte el paso 5.</span><span class="sxs-lookup"><span data-stu-id="57a8e-190">For instructions about how to enter a placeholder, see step 5.</span></span>
    6. <span data-ttu-id="57a8e-191">Haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="57a8e-191">Click **Close**.</span></span>

7. <span data-ttu-id="57a8e-192">En la pestaña **Destinatario**, utilice las siguientes opciones para especificar quién debe recibir las notificaciones.</span><span class="sxs-lookup"><span data-stu-id="57a8e-192">On the **Recipient** tab, use the following options to specify who should receive the notifications.</span></span>

    <table>
    <thead>
    <tr>
    <th><span data-ttu-id="57a8e-193">Opción</span><span class="sxs-lookup"><span data-stu-id="57a8e-193">Option</span></span></th>
    <th><span data-ttu-id="57a8e-194">Las notificaciones se envían a estos usuarios</span><span class="sxs-lookup"><span data-stu-id="57a8e-194">Notifications are sent to these users</span></span></th>
    <th><span data-ttu-id="57a8e-195">Para enviar notificaciones, siga estos pasos</span><span class="sxs-lookup"><span data-stu-id="57a8e-195">To send notifications, follow these steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td><span data-ttu-id="57a8e-196">Participante</span><span class="sxs-lookup"><span data-stu-id="57a8e-196">Participant</span></span></td>
    <td><span data-ttu-id="57a8e-197">Usuarios asignados a un grupo o rol específicos</span><span class="sxs-lookup"><span data-stu-id="57a8e-197">Users who are assigned to a specific group or role</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="57a8e-198">En la pestaña <strong>Destinatario</strong>, haga clic en <strong>Participante</strong>.</span><span class="sxs-lookup"><span data-stu-id="57a8e-198">On the <strong>Recipient</strong> tab, click <strong>Participant</strong>.</span></span></li>
    <li><span data-ttu-id="57a8e-199">En la pestaña <strong>Basado en funciones</strong>, en la lista <strong>Tipo de participante</strong>, seleccione el tipo de grupo o rol al que desea enviar las notificaciones.</span><span class="sxs-lookup"><span data-stu-id="57a8e-199">On the <strong>Role based</strong> tab, in the <strong>Type of participant</strong> list, select the type of group or role to send notifications to.</span></span></li>
    <li><span data-ttu-id="57a8e-200">En la lista <strong>Participante</strong>, seleccione el grupo o rol al que se deben enviar las notificaciones.</span><span class="sxs-lookup"><span data-stu-id="57a8e-200">In the <strong>Participant</strong> list, select the group or role to send notifications to.</span></span></li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="57a8e-201">Usuario del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="57a8e-201">Workflow user</span></span></td>
    <td><span data-ttu-id="57a8e-202">Usuarios que participan en el flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="57a8e-202">Users who are participants in this workflow</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="57a8e-203">En la ficha <strong>Destinatario</strong>, haga clic en <strong>Usuario del flujo de trabajo</strong>.</span><span class="sxs-lookup"><span data-stu-id="57a8e-203">On the <strong>Recipient</strong> tab, click <strong>Workflow user</strong>.</span></span></li>
    <li><span data-ttu-id="57a8e-204">En la pestaña <strong>Usuario del flujo de trabajo</strong>, en la lista <strong>Usuario del flujo de trabajo</strong>, seleccione un participante de este flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="57a8e-204">On the <strong>Workflow user</strong> tab, in the <strong>Workflow user</strong> list, select a participant in this workflow.</span></span></li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="57a8e-205">Usuario</span><span class="sxs-lookup"><span data-stu-id="57a8e-205">User</span></span></td>
    <td><span data-ttu-id="57a8e-206">Usuarios concretos</span><span class="sxs-lookup"><span data-stu-id="57a8e-206">Specific users</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="57a8e-207">En la ficha <strong>Destinatario</strong>, haga clic en <strong>Usuario</strong>.</span><span class="sxs-lookup"><span data-stu-id="57a8e-207">On the <strong>Recipient</strong> tab, click <strong>User</strong>.</span></span></li>
    <li><span data-ttu-id="57a8e-208">En la pestaña <strong>Usuario</strong>, la lista <strong>Usuarios disponibles</strong> incluye todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="57a8e-208">On the <strong>User</strong> tab, the <strong>Available users</strong> list includes all users.</span></span> <span data-ttu-id="57a8e-209">Seleccione aquellos a los que desea enviar notificaciones y muévalos a la lista <strong>Usuarios seleccionados</strong>.</span><span class="sxs-lookup"><span data-stu-id="57a8e-209">Select the users to send notifications to, and move those users into the <strong>Selected users</strong> list.</span></span></li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

8. <span data-ttu-id="57a8e-210">Repita los pasos 3 a 7 por cada uno de los eventos que haya seleccionado en el paso 2.</span><span class="sxs-lookup"><span data-stu-id="57a8e-210">Repeat steps 3 through 7 for each event that you selected in step 2.</span></span>

## <a name="enter-comments-about-the-changes-that-you-made-to-the-workflow"></a><span data-ttu-id="57a8e-211">Escriba comentarios acerca de los cambios que realizó en el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="57a8e-211">Enter comments about the changes that you made to the workflow</span></span>

<span data-ttu-id="57a8e-212">Para escribir comentarios acerca de los cambios que realizó en el flujo de trabajo, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="57a8e-212">To enter comments about the changes that you made to the workflow, follow these steps.</span></span>

1. <span data-ttu-id="57a8e-213">En el panel izquierdo, haga clic en **Notas**.</span><span class="sxs-lookup"><span data-stu-id="57a8e-213">In the left pane, click **Notes**.</span></span>
2. <span data-ttu-id="57a8e-214">En el campo **Especificar comentarios sobre el flujo de trabajo**, escriba sus comentarios.</span><span class="sxs-lookup"><span data-stu-id="57a8e-214">In the **Enter comments about the workflow** field, enter your comments.</span></span>
3. <span data-ttu-id="57a8e-215">Revise los comentarios:</span><span class="sxs-lookup"><span data-stu-id="57a8e-215">Review your comments.</span></span> <span data-ttu-id="57a8e-216">una vez agregados, no podrá modificarlos.</span><span class="sxs-lookup"><span data-stu-id="57a8e-216">After you add comments, you can't modify them.</span></span>
4. <span data-ttu-id="57a8e-217">Haga **Agregar** clic en para agregar sus comentarios al área **Historial de comentarios**.</span><span class="sxs-lookup"><span data-stu-id="57a8e-217">Click **Add** to add your comments to the **Comment history** area.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]