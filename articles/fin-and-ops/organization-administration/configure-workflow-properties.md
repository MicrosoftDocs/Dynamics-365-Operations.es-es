---
title: Configurar propiedades del flujo de trabajo
description: "Este tema explica cómo configurar las diversas propiedades de un flujo de trabajo."
author: sericks007
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 196083
ms.assetid: 192b7a98-7d04-4c7a-a986-29d797a8a837
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 0b8f17285fb845101e9fbec23de7dd7866811bbd
ms.contentlocale: es-es
ms.lasthandoff: 04/13/2018

---

# <a name="configure-workflow-properties"></a><span data-ttu-id="effd2-103">Configurar propiedades del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="effd2-103">Configure workflow properties</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="effd2-104">Este tema explica cómo configurar las diversas propiedades de un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="effd2-104">This topic explains how to configure the various properties of a workflow.</span></span>

<span data-ttu-id="effd2-105">Para configurar las propiedades de un flujo de trabajo, abra el flujo de trabajo en el editor de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="effd2-105">To configure the properties of a workflow, open the workflow in the workflow editor.</span></span> <span data-ttu-id="effd2-106">Haga clic en el lienzo del editor de flujos de trabajo y luego haga clic en **Propiedades** para abrir la página **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="effd2-106">Click the canvas of the workflow editor, and then click **Properties** to open the **Properties** page.</span></span> <span data-ttu-id="effd2-107">A continuación, puede usar los siguientes procedimientos para configurar las diversas propiedades del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="effd2-107">You can then use the following procedures to configure the various properties of the workflow.</span></span>

## <a name="name-the-workflow"></a><span data-ttu-id="effd2-108">Asignación de un nombre al flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="effd2-108">Name the workflow</span></span>
<span data-ttu-id="effd2-109">Siga estos pasos para asignar un nombre al flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="effd2-109">Follow these steps to enter a name for the workflow.</span></span>

1.  <span data-ttu-id="effd2-110">En el panel izquierdo, haga clic en **Configuración básica**.</span><span class="sxs-lookup"><span data-stu-id="effd2-110">In the left pane, click **Basic Settings**.</span></span>
2.  <span data-ttu-id="effd2-111">En el campo **Nombre**, especifique un nombre exclusivo para el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="effd2-111">In the **Name** field, enter a unique name for the workflow.</span></span> <span data-ttu-id="effd2-112">Por ejemplo, si crea un flujo de trabajo de solicitud de compra para cada país o región en los que opera, puede llamar al flujo de trabajo de solicitud de compra **Solicitudes de compra Dinamarca** o **Solicitudes de compra España**.</span><span class="sxs-lookup"><span data-stu-id="effd2-112">For example, if you create a purchase requisition workflow for each country/region that you operate in, you can name the purchase requisition workflow **Purchase Requisitions Denmark** or **Purchase Requisitions Spain**.</span></span>

## <a name="specify-the-workflow-owner"></a><span data-ttu-id="effd2-113">Especificación del propietario del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="effd2-113">Specify the workflow owner</span></span>
<span data-ttu-id="effd2-114">El propietario del flujo de trabajo es la persona que administra y mantiene el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="effd2-114">The workflow owner is the person who manages and maintains the workflow.</span></span> <span data-ttu-id="effd2-115">Siga estos pasos para especificar el propietario del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="effd2-115">Follow these steps to specify the workflow owner.</span></span>

1.  <span data-ttu-id="effd2-116">En el panel izquierdo, haga clic en **Configuración básica**.</span><span class="sxs-lookup"><span data-stu-id="effd2-116">In the left pane, click **Basic Settings**.</span></span>
2.  <span data-ttu-id="effd2-117">En la lista **Propietario**, seleccione el nombre de la persona que administrará el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="effd2-117">In the **Owner** list, select the name of the person who will manage the workflow.</span></span>

## <a name="select-an-email-template"></a><span data-ttu-id="effd2-118">Selección de una plantilla de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="effd2-118">Select an email template</span></span>
<span data-ttu-id="effd2-119">Siga estos pasos para seleccionar la plantilla de correo electrónico que se usa para generar los mensajes de notificación sobre el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="effd2-119">Follow these steps to select the email template that is used to generate notification messages about the workflow.</span></span>

1.  <span data-ttu-id="effd2-120">En el panel izquierdo, haga clic en **Configuración básica**.</span><span class="sxs-lookup"><span data-stu-id="effd2-120">In the left pane, click **Basic Settings**.</span></span>
2.  <span data-ttu-id="effd2-121">En la lista **Plantilla de correo electrónico para notificaciones de flujo de trabajo**, seleccione la plantilla.</span><span class="sxs-lookup"><span data-stu-id="effd2-121">In the **Email template for workflow notifications** list, select the template.</span></span>

## <a name="enter-instructions-for-users"></a><span data-ttu-id="effd2-122">Especificación de las instrucciones para los usuarios</span><span class="sxs-lookup"><span data-stu-id="effd2-122">Enter instructions for users</span></span>
<span data-ttu-id="effd2-123">Puede proporcionar instrucciones a los usuarios que envían los documentos que se deben procesar y aprobar.</span><span class="sxs-lookup"><span data-stu-id="effd2-123">You can provide instructions to users who submit documents for processing and approval.</span></span> <span data-ttu-id="effd2-124">A estos usuarios también se les conoce como *originadores*.</span><span class="sxs-lookup"><span data-stu-id="effd2-124">These users are also referred to as *originators*.</span></span> <span data-ttu-id="effd2-125">Por ejemplo, está creando un flujo de trabajo de solicitudes de compra y especifica instrucciones.</span><span class="sxs-lookup"><span data-stu-id="effd2-125">For example, you're creating a purchase requisition workflow, and you enter instructions.</span></span> <span data-ttu-id="effd2-126">Esas instrucciones se pueden ver entonces por los usuarios que especifican solicitudes de compra en la página **Solicitudes de compra**.</span><span class="sxs-lookup"><span data-stu-id="effd2-126">Those instructions can then be viewed by users who enter purchase requisitions on the **Purchase requisitions** page.</span></span> <span data-ttu-id="effd2-127">Para consultar las instrucciones, el originador hace clic en el icono de la barra de mensajes del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="effd2-127">To view instructions, the originator clicks the icon in the workflow message bar.</span></span> <span data-ttu-id="effd2-128">Siga estos pasos para escribir las instrucciones para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="effd2-128">Follow these steps to enter instructions for users.</span></span>

1.  <span data-ttu-id="effd2-129">En el panel izquierdo, haga clic en **Configuración básica**.</span><span class="sxs-lookup"><span data-stu-id="effd2-129">In the left pane, click **Basic Settings**.</span></span>
2.  <span data-ttu-id="effd2-130">En el campo **Instrucciones de envío**, escriba las instrucciones.</span><span class="sxs-lookup"><span data-stu-id="effd2-130">In the **Submission instructions** field, enter the instructions.</span></span>
3.  <span data-ttu-id="effd2-131">Para personalizar las instrucciones, puede insertar marcadores de posición.</span><span class="sxs-lookup"><span data-stu-id="effd2-131">To personalize the instructions, you can insert placeholders.</span></span> <span data-ttu-id="effd2-132">Estos se reemplazan con los datos adecuados cuando las instrucciones se muestran a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="effd2-132">Placeholders are replaced with the appropriate data when the instructions are shown to users.</span></span> <span data-ttu-id="effd2-133">Para insertar un marcador de posición, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="effd2-133">To insert a placeholder, follow these steps:</span></span>
    1.  <span data-ttu-id="effd2-134">Haga clic en el campo **Instrucciones de envío** para especificar dónde debe aparecer el marcador de posición.</span><span class="sxs-lookup"><span data-stu-id="effd2-134">Click in the **Submission instructions** field to specify where the placeholder should appear.</span></span>
    2.  <span data-ttu-id="effd2-135">Haga clic en **Insertar marcador de posición**.</span><span class="sxs-lookup"><span data-stu-id="effd2-135">Click **Insert placeholder**.</span></span>
    3.  <span data-ttu-id="effd2-136">En la lista que aparece, seleccione el marcador de posición que desea insertar.</span><span class="sxs-lookup"><span data-stu-id="effd2-136">In the list that appears, select the placeholder to insert.</span></span>
    4.  <span data-ttu-id="effd2-137">Haga clic en **Insertar**.</span><span class="sxs-lookup"><span data-stu-id="effd2-137">Click **Insert**.</span></span>

4.  <span data-ttu-id="effd2-138">Para agregar traducciones de las instrucciones, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="effd2-138">To add translations of the instructions, follow these steps:</span></span>
    1.  <span data-ttu-id="effd2-139">Haga clic en **Traducciones**.</span><span class="sxs-lookup"><span data-stu-id="effd2-139">Click **Translations**.</span></span>
    2.  <span data-ttu-id="effd2-140">En la página que aparece, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="effd2-140">On the page that appears, click **Add**.</span></span>
    3.  <span data-ttu-id="effd2-141">En la lista que aparece, seleccione el idioma en el que escribirá el texto.</span><span class="sxs-lookup"><span data-stu-id="effd2-141">In the list that appears, select the language that you will enter the text in.</span></span>
    4.  <span data-ttu-id="effd2-142">En el campo **Texto traducido**, escriba el texto.</span><span class="sxs-lookup"><span data-stu-id="effd2-142">In the **Translated text** field, enter the text.</span></span>
    5.  <span data-ttu-id="effd2-143">Para personalizar el texto, puede insertar marcadores de posición.</span><span class="sxs-lookup"><span data-stu-id="effd2-143">To personalize the text, you can insert placeholders.</span></span> <span data-ttu-id="effd2-144">Para obtener instrucciones acerca de cómo agregar un marcador de posición, consulte el paso 3.</span><span class="sxs-lookup"><span data-stu-id="effd2-144">For instructions about how to enter a placeholder, see step 3.</span></span>
    6.  <span data-ttu-id="effd2-145">Haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="effd2-145">Click **Close**.</span></span>

## <a name="specify-when-this-workflow-is-used"></a><span data-ttu-id="effd2-146">Especificación de las condiciones en que se usa el flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="effd2-146">Specify when this workflow is used</span></span>
<span data-ttu-id="effd2-147">Puede crear varios flujos de trabajo que estén basados en el mismo tipo.</span><span class="sxs-lookup"><span data-stu-id="effd2-147">You can create multiple workflows that are based on the same type.</span></span> <span data-ttu-id="effd2-148">Por ejemplo, puede crear un flujo de trabajo de solicitudes de compra para cada país o región en los que opera como, por ejemplo, Solicitudes de compra Dinamarca y Solicitudes de compra España.</span><span class="sxs-lookup"><span data-stu-id="effd2-148">For example, you can create a purchase requisition workflow for each country/region that you operate in, such as Purchase Requisitions Denmark and Purchase Requisitions Spain.</span></span> <span data-ttu-id="effd2-149">Cuando existen varios flujos de trabajo basados en el mismo tipo, debe especificar cuándo se usa cada uno.</span><span class="sxs-lookup"><span data-stu-id="effd2-149">When you have multiple workflows that are based on the same type, you must specify when each workflow is used.</span></span> <span data-ttu-id="effd2-150">Para el ejemplo anterior, especifique las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="effd2-150">For the preceding example, you specify the following conditions:</span></span>

-   <span data-ttu-id="effd2-151">Se usa Solicitudes de compra Dinamarca cuando: país/región = DK</span><span class="sxs-lookup"><span data-stu-id="effd2-151">Purchase Requisitions Denmark is used when: country/region = DK</span></span>
-   <span data-ttu-id="effd2-152">Se usa Solicitudes de compra España cuando: país/región = ES</span><span class="sxs-lookup"><span data-stu-id="effd2-152">Purchase Requisitions Spain is used when: country/region = ES</span></span>

<span data-ttu-id="effd2-153">Siga estos pasos para especificar cuándo se usa el flujo de trabajo que está configurando.</span><span class="sxs-lookup"><span data-stu-id="effd2-153">Follow these steps to specify when the workflow that you're configuring is used.</span></span>

1.  <span data-ttu-id="effd2-154">En el panel izquierdo, haga clic en **Activación**.</span><span class="sxs-lookup"><span data-stu-id="effd2-154">In the left pane, click **Activation**.</span></span>
2.  <span data-ttu-id="effd2-155">Active la casilla **Establecer condiciones para ejecutar este flujo de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="effd2-155">Select the **Set the conditions for running this workflow** check box.</span></span>
3.  <span data-ttu-id="effd2-156">Haga clic en **Agregar condición**.</span><span class="sxs-lookup"><span data-stu-id="effd2-156">Click **Add condition**.</span></span>
4.  <span data-ttu-id="effd2-157">Escriba una condición.</span><span class="sxs-lookup"><span data-stu-id="effd2-157">Enter a condition.</span></span>
5.  <span data-ttu-id="effd2-158">Escriba condiciones adicionales que sean necesarias.</span><span class="sxs-lookup"><span data-stu-id="effd2-158">Enter any additional conditions that are required.</span></span>
6.  <span data-ttu-id="effd2-159">Para comprobar que las condiciones definidas se hayan establecido correctamente, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="effd2-159">To verify that the conditions that you entered are set correctly, follow these steps:</span></span>
    1.  <span data-ttu-id="effd2-160">Haga clic en **Probar**.</span><span class="sxs-lookup"><span data-stu-id="effd2-160">Click **Test**.</span></span>
    2.  <span data-ttu-id="effd2-161">En la página **Probar condición de flujo de trabajo**, en el área **Comprobar condición**, seleccione un registro.</span><span class="sxs-lookup"><span data-stu-id="effd2-161">On the **Test workflow condition** page, in the **Validate condition** area, select a record.</span></span>
    3.  <span data-ttu-id="effd2-162">Haga clic en **Probar**.</span><span class="sxs-lookup"><span data-stu-id="effd2-162">Click **Test**.</span></span> <span data-ttu-id="effd2-163">El sistema evalúa el registro seleccionado para determinar si reúne las condiciones que se especificaron.</span><span class="sxs-lookup"><span data-stu-id="effd2-163">The system evaluates the record to determine whether it meets the conditions that you specified.</span></span> <span data-ttu-id="effd2-164">Por ejemplo, si crea un flujo de trabajo de solicitudes de compra para España, el área **Comprobar condición** de la página muestra una lista de solicitudes de compra.</span><span class="sxs-lookup"><span data-stu-id="effd2-164">For example, if you're creating a purchase requisition workflow for Spain, the **Validate condition** area of the page shows a list of purchase requisitions.</span></span> <span data-ttu-id="effd2-165">Al hacer clic en **Probar**, el sistema evalúa la solicitud de compra seleccionada para determinar si el país o región es ES.</span><span class="sxs-lookup"><span data-stu-id="effd2-165">When you click **Test**, the system evaluates the selected purchase requisition to determine whether the country/region is ES.</span></span>
    4.  <span data-ttu-id="effd2-166">Haga clic en **Aceptar** o en **Cancelar** para regresar a la página **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="effd2-166">Click **OK** or **Cancel** to return to the **Properties** page.</span></span>

## <a name="specify-when-notifications-are-sent"></a><span data-ttu-id="effd2-167">Especificación del momento en que se envían notificaciones</span><span class="sxs-lookup"><span data-stu-id="effd2-167">Specify when notifications are sent</span></span>
<span data-ttu-id="effd2-168">Cuando se envía un documento para que se lo procese, se crea una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="effd2-168">When a document is submitted for processing, a workflow instance is created.</span></span> <span data-ttu-id="effd2-169">Puede enviar notificaciones a los usuarios para indicar el inicio, la finalización, la terminación o la detención debido a un error de las instancias de flujo de trabajo basadas en el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="effd2-169">You can send notifications to users when workflow instances that are based on the workflow are started, completed, terminated, or stopped because of an error.</span></span> <span data-ttu-id="effd2-170">Siga estos pasos para especificar cuándo se envían notificaciones.</span><span class="sxs-lookup"><span data-stu-id="effd2-170">Follow these steps to specify when notifications are sent.</span></span>

1.  <span data-ttu-id="effd2-171">En el panel izquierdo, haga clic en **Notificaciones**.</span><span class="sxs-lookup"><span data-stu-id="effd2-171">In the left pane, click **Notifications**.</span></span>
2.  <span data-ttu-id="effd2-172">Active las casillas de verificación correspondientes a los eventos que deben desencadenar las notificaciones:</span><span class="sxs-lookup"><span data-stu-id="effd2-172">Select the check box for each event that should trigger notifications:</span></span>
    -   <span data-ttu-id="effd2-173">**Iniciado**: enviar notificaciones cuando se inicia una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="effd2-173">**Started** – Send notifications when a workflow instance is started.</span></span>
    -   <span data-ttu-id="effd2-174">**Detenido**: enviar notificaciones cuando una instancia de flujo de trabajo se detiene debido a un error.</span><span class="sxs-lookup"><span data-stu-id="effd2-174">**Stopped** – Send notifications when a workflow instance is stopped because of an error.</span></span>
    -   <span data-ttu-id="effd2-175">**Completado**: enviar notificaciones cuando se completa una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="effd2-175">**Completed** – Send notifications when a workflow instance is completed.</span></span>
    -   <span data-ttu-id="effd2-176">**Irrecuperable**: enviar notificaciones cuando una instancia de flujo de trabajo se detiene debido a un error irrecuperable.</span><span class="sxs-lookup"><span data-stu-id="effd2-176">**Unrecoverable** – Send notifications when a workflow instance is stopped because of an unrecoverable error.</span></span>
    -   <span data-ttu-id="effd2-177">**Terminado**: enviar notificaciones cuando finaliza una instancia de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="effd2-177">**Terminated** – Send notifications when a workflow instance is terminated.</span></span>

3.  <span data-ttu-id="effd2-178">Seleccione la fila correspondiente a uno de los eventos que seleccionó en el paso 2.</span><span class="sxs-lookup"><span data-stu-id="effd2-178">Select the row for an event that you selected in step 2.</span></span>
4.  <span data-ttu-id="effd2-179">En la pestaña **Texto de notificación**, escriba el texto de la notificación.</span><span class="sxs-lookup"><span data-stu-id="effd2-179">On the **Notification text** tab, enter the text of the notification.</span></span>
5.  <span data-ttu-id="effd2-180">Para personalizar el texto, puede insertar marcadores de posición.</span><span class="sxs-lookup"><span data-stu-id="effd2-180">To personalize the text, you can insert placeholders.</span></span> <span data-ttu-id="effd2-181">Estos se reemplazan con los datos adecuados cuando se muestra el texto a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="effd2-181">Placeholders are replaced with the appropriate data when the text is shown to users.</span></span> <span data-ttu-id="effd2-182">Para insertar un marcador de posición, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="effd2-182">To insert a placeholder, follow these steps:</span></span>
    1.  <span data-ttu-id="effd2-183">Haga clic en el campo para especificar dónde debe aparecer el marcador de posición.</span><span class="sxs-lookup"><span data-stu-id="effd2-183">Click in the field to specify where the placeholder should appear.</span></span>
    2.  <span data-ttu-id="effd2-184">Haga clic en **Insertar marcador de posición**.</span><span class="sxs-lookup"><span data-stu-id="effd2-184">Click **Insert placeholder**.</span></span>
    3.  <span data-ttu-id="effd2-185">En la lista que aparece, seleccione el marcador de posición que desea insertar.</span><span class="sxs-lookup"><span data-stu-id="effd2-185">In the list that appears, select the placeholder to insert.</span></span>
    4.  <span data-ttu-id="effd2-186">Haga clic en **Insertar**.</span><span class="sxs-lookup"><span data-stu-id="effd2-186">Click **Insert**.</span></span>

6.  <span data-ttu-id="effd2-187">Para agregar traducciones del texto, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="effd2-187">To add translations of the text, follow these steps:</span></span>
    1.  <span data-ttu-id="effd2-188">Haga clic en **Traducciones**.</span><span class="sxs-lookup"><span data-stu-id="effd2-188">Click **Translations**.</span></span>
    2.  <span data-ttu-id="effd2-189">En la página que aparece, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="effd2-189">On the page that appears, Click **Add**.</span></span>
    3.  <span data-ttu-id="effd2-190">En la lista que aparece, seleccione el idioma en el que escribirá el texto.</span><span class="sxs-lookup"><span data-stu-id="effd2-190">In the list that appears, select the language that you will enter the text in.</span></span>
    4.  <span data-ttu-id="effd2-191">En el campo **Texto traducido**, escriba el texto.</span><span class="sxs-lookup"><span data-stu-id="effd2-191">In the **Translated text** field, enter the text.</span></span>
    5.  <span data-ttu-id="effd2-192">Para personalizar el texto, puede insertar marcadores de posición.</span><span class="sxs-lookup"><span data-stu-id="effd2-192">To personalize the text, you can insert placeholders.</span></span> <span data-ttu-id="effd2-193">Para obtener instrucciones acerca de cómo agregar un marcador de posición, consulte el paso 5.</span><span class="sxs-lookup"><span data-stu-id="effd2-193">For instructions about how to enter a placeholder, see step 5.</span></span>
    6.  <span data-ttu-id="effd2-194">Haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="effd2-194">Click **Close**.</span></span>

7.  <span data-ttu-id="effd2-195">En la pestaña **Destinatario**, utilice las siguientes opciones para especificar quién debe recibir las notificaciones.</span><span class="sxs-lookup"><span data-stu-id="effd2-195">On the **Recipient** tab, use the following options to specify who should receive the notifications.</span></span>
    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="effd2-196">Opción</span><span class="sxs-lookup"><span data-stu-id="effd2-196">Option</span></span></th>
    <th><span data-ttu-id="effd2-197">Las notificaciones se envían a estos usuarios</span><span class="sxs-lookup"><span data-stu-id="effd2-197">Notifications are sent to these users</span></span></th>
    <th><span data-ttu-id="effd2-198">Para enviar notificaciones, siga estos pasos</span><span class="sxs-lookup"><span data-stu-id="effd2-198">To send notifications, follow these steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><span data-ttu-id="effd2-199">Participante</span><span class="sxs-lookup"><span data-stu-id="effd2-199">Participant</span></span></td>
    <td><span data-ttu-id="effd2-200">Usuarios asignados a un grupo o rol específicos</span><span class="sxs-lookup"><span data-stu-id="effd2-200">Users who are assigned to a specific group or role</span></span></td>
    <td><ol>
    <li><span data-ttu-id="effd2-201">En la pestaña <strong>Destinatario</strong>, haga clic en <strong>Participante</strong>.</span><span class="sxs-lookup"><span data-stu-id="effd2-201">On the <strong>Recipient</strong> tab, click <strong>Participant</strong>.</span></span></li>
    <li><span data-ttu-id="effd2-202">En la pestaña <strong>Basado en funciones</strong>, en la lista <strong>Tipo de participante</strong>, seleccione el tipo de grupo o rol al que desea enviar las notificaciones.</span><span class="sxs-lookup"><span data-stu-id="effd2-202">On the <strong>Role based</strong> tab, in the <strong>Type of participant</strong> list, select the type of group or role to send notifications to.</span></span></li>
    <li><span data-ttu-id="effd2-203">En la lista <strong>Participante</strong>, seleccione el grupo o rol al que se deben enviar las notificaciones.</span><span class="sxs-lookup"><span data-stu-id="effd2-203">In the <strong>Participant</strong> list, select the group or role to send notifications to.</span></span></li>
    </ol></td>
    </tr>
    <tr class="even">
    <td><span data-ttu-id="effd2-204">Usuario del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="effd2-204">Workflow user</span></span></td>
    <td><span data-ttu-id="effd2-205">Usuarios que participan en el flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="effd2-205">Users who are participants in this workflow</span></span></td>
    <td><ol>
    <li><span data-ttu-id="effd2-206">En la ficha <strong>Destinatario</strong>, haga clic en <strong>Usuario del flujo de trabajo</strong>.</span><span class="sxs-lookup"><span data-stu-id="effd2-206">On the <strong>Recipient</strong> tab, click <strong>Workflow user</strong>.</span></span></li>
    <li><span data-ttu-id="effd2-207">En la pestaña <strong>Usuario del flujo de trabajo</strong>, en la lista <strong>Usuario del flujo de trabajo</strong>, seleccione un participante de este flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="effd2-207">On the <strong>Workflow user</strong> tab, in the <strong>Workflow user</strong> list, select a participant in this workflow.</span></span></li>
    </ol></td>
    </tr>
    <tr class="odd">
    <td><span data-ttu-id="effd2-208">Usuario</span><span class="sxs-lookup"><span data-stu-id="effd2-208">User</span></span></td>
    <td><span data-ttu-id="effd2-209">Usuarios específicos de Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="effd2-209">Specific Finance and Operations users</span></span></td>
    <td><ol>
    <li><span data-ttu-id="effd2-210">En la ficha <strong>Destinatario</strong>, haga clic en <strong>Usuario</strong>.</span><span class="sxs-lookup"><span data-stu-id="effd2-210">On the <strong>Recipient</strong> tab, click <strong>User</strong>.</span></span></li>
    <li><span data-ttu-id="effd2-211">En la pestaña <strong>Usuario</strong>, la lista <strong>Usuarios disponibles</strong> incluye todos los usuarios de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="effd2-211">On the <strong>User</strong> tab, the <strong>Available users</strong> list includes all Finance and Operations users.</span></span> <span data-ttu-id="effd2-212">Seleccione aquellos a los que desea enviar notificaciones y muévalos a la lista <strong>Usuarios seleccionados</strong>.</span><span class="sxs-lookup"><span data-stu-id="effd2-212">Select the users to send notifications to, and move those users into the <strong>Selected users</strong> list.</span></span></li>
    </ol></td>
    </tr>
    </tbody>
    </table>

8.  <span data-ttu-id="effd2-213">Repita los pasos 3 a 7 por cada uno de los eventos que haya seleccionado en el paso 2.</span><span class="sxs-lookup"><span data-stu-id="effd2-213">Repeat steps 3 through 7 for each event that you selected in step 2.</span></span>

## <a name="enter-comments-about-the-changes-that-you-made-to-the-workflow"></a><span data-ttu-id="effd2-214">Escriba comentarios acerca de los cambios que realizó en el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="effd2-214">Enter comments about the changes that you made to the workflow</span></span>
<span data-ttu-id="effd2-215">Para escribir comentarios acerca de los cambios que realizó en el flujo de trabajo, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="effd2-215">To enter comments about the changes that you made to the workflow, follow these steps.</span></span>

1.  <span data-ttu-id="effd2-216">En el panel izquierdo, haga clic en **Notas**.</span><span class="sxs-lookup"><span data-stu-id="effd2-216">In the left pane, click **Notes**.</span></span>
2.  <span data-ttu-id="effd2-217">En el campo **Especificar comentarios sobre el flujo de trabajo**, escriba sus comentarios.</span><span class="sxs-lookup"><span data-stu-id="effd2-217">In the **Enter comments about the workflow** field, enter your comments.</span></span>
3.  <span data-ttu-id="effd2-218">Revise los comentarios:</span><span class="sxs-lookup"><span data-stu-id="effd2-218">Review your comments.</span></span> <span data-ttu-id="effd2-219">una vez agregados, no podrá modificarlos.</span><span class="sxs-lookup"><span data-stu-id="effd2-219">After you add comments, you can't modify them.</span></span>
4.  <span data-ttu-id="effd2-220">Haga **Agregar** clic en para agregar sus comentarios al área **Historial de comentarios**.</span><span class="sxs-lookup"><span data-stu-id="effd2-220">Click **Add** to add your comments to the **Comment history** area.</span></span>





