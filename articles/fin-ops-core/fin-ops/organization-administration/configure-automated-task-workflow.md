---
title: Configurar tareas automatizadas en un flujo de trabajo
description: Este tema explica cómo configurar las propiedades de una tarea automatizada.
author: ChrisGarty
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 192061
ms.assetid: c0aceb57-b5e6-4ef3-91e7-89a21c9f048a
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 664a70ed7c93c88e1a9cd020029bac285dbaa1f8
ms.sourcegitcommit: f5e31c34640add6d40308ac1365cc0ee60e60e24
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/08/2020
ms.locfileid: "4694035"
---
# <a name="configure-automated-tasks-in-a-workflow"></a><span data-ttu-id="e1769-103">Configurar tareas automatizadas en un flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="e1769-103">Configure automated tasks in a workflow</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e1769-104">Este tema explica cómo configurar las propiedades de una tarea automatizada.</span><span class="sxs-lookup"><span data-stu-id="e1769-104">This topic explains how to configure the properties for an automated task.</span></span>

<span data-ttu-id="e1769-105">Para configurar una tarea automatizada en el editor de flujo de trabajo, haga clic con el botón secundario en la tarea y, a continuación, haga clic en **Propiedades** para abrir la página **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="e1769-105">To configure an automated task in the workflow editor, right-click the task, and then click **Properties** to open the **Properties** page.</span></span> <span data-ttu-id="e1769-106">A continuación, use los siguientes procedimientos para configurar las propiedades de la tarea automatizada.</span><span class="sxs-lookup"><span data-stu-id="e1769-106">Then use the following procedures to configure the properties for the automated task.</span></span>

## <a name="name-the-task"></a><span data-ttu-id="e1769-107">Asignación de un nombre a la tarea</span><span class="sxs-lookup"><span data-stu-id="e1769-107">Name the task</span></span>

<span data-ttu-id="e1769-108">Siga estos pasos para asignar un nombre a la tarea automatizada.</span><span class="sxs-lookup"><span data-stu-id="e1769-108">Follow these steps to enter a name for the automated task.</span></span>

1. <span data-ttu-id="e1769-109">En el panel izquierdo, haga clic en **Configuración básica**.</span><span class="sxs-lookup"><span data-stu-id="e1769-109">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="e1769-110">En el campo **Nombre**, especifique un nombre único para la tarea.</span><span class="sxs-lookup"><span data-stu-id="e1769-110">In the **Name** field, enter a unique name for the task.</span></span>

## <a name="specify-when-notifications-are-sent"></a><span data-ttu-id="e1769-111">Especificación del momento en que se envían notificaciones</span><span class="sxs-lookup"><span data-stu-id="e1769-111">Specify when notifications are sent</span></span>

<span data-ttu-id="e1769-112">Puede enviar notificaciones cuando se ha ejecutado o cancelado una tarea automatizada.</span><span class="sxs-lookup"><span data-stu-id="e1769-112">You can send notifications to people when an automated task has been run or canceled.</span></span> <span data-ttu-id="e1769-113">Siga estos pasos para especificar cuándo se deben enviar notificaciones y a quiénes se deben enviar.</span><span class="sxs-lookup"><span data-stu-id="e1769-113">Follow these steps to specify when notifications are sent, and who they are sent to.</span></span>

1. <span data-ttu-id="e1769-114">En el panel izquierdo, haga clic en **Notificaciones**.</span><span class="sxs-lookup"><span data-stu-id="e1769-114">In the left pane, click **Notifications**.</span></span>
2. <span data-ttu-id="e1769-115">Active las casillas de verificación junto a los eventos que deben notificarse:</span><span class="sxs-lookup"><span data-stu-id="e1769-115">Select the check box next to the events to send notifications for:</span></span>

    - <span data-ttu-id="e1769-116">**Ejecución**: se envían notificaciones cuando la tarea se ha ejecutado.</span><span class="sxs-lookup"><span data-stu-id="e1769-116">**Execution** – Notifications are sent when the task has been run.</span></span>
    - <span data-ttu-id="e1769-117">**Cancelado**: se envían notificaciones cuando la tarea se ha cancelado.</span><span class="sxs-lookup"><span data-stu-id="e1769-117">**Canceled** – Notifications are sent when the task has been canceled.</span></span>

3. <span data-ttu-id="e1769-118">Seleccione la fila correspondiente a uno de los eventos que seleccionó en el paso 2.</span><span class="sxs-lookup"><span data-stu-id="e1769-118">Select the row for an event that you selected in step 2.</span></span>
4. <span data-ttu-id="e1769-119">En la pestaña **Texto de notificación**, en el cuadro de texto, escriba el texto de la notificación.</span><span class="sxs-lookup"><span data-stu-id="e1769-119">On the **Notification text** tab, in the text box, enter the text of the notification.</span></span>
5. <span data-ttu-id="e1769-120">Para personalizar la notificación, puede insertar marcadores de posición.</span><span class="sxs-lookup"><span data-stu-id="e1769-120">To personalize the notification, you can insert placeholders.</span></span> <span data-ttu-id="e1769-121">Estos se reemplazan con los datos adecuados cuando se muestra la notificación a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="e1769-121">Placeholders are replaced with appropriate data when the notification is shown to users.</span></span> <span data-ttu-id="e1769-122">Para insertar un marcador de posición, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="e1769-122">Follow these steps to insert a placeholder:</span></span>

    1. <span data-ttu-id="e1769-123">En el cuadro de texto, gaga clic para especificar dónde debe aparecer el marcador de posición.</span><span class="sxs-lookup"><span data-stu-id="e1769-123">In the text box, click where the placeholder should appear.</span></span>
    2. <span data-ttu-id="e1769-124">Haga clic en **Insertar marcador de posición**.</span><span class="sxs-lookup"><span data-stu-id="e1769-124">Click **Insert placeholder**.</span></span>
    3. <span data-ttu-id="e1769-125">En la lista que aparece, seleccione el marcador de posición que desea insertar.</span><span class="sxs-lookup"><span data-stu-id="e1769-125">In the list that appears, select the placeholder to insert.</span></span>
    4. <span data-ttu-id="e1769-126">Haga clic en **Insertar**.</span><span class="sxs-lookup"><span data-stu-id="e1769-126">Click **Insert**.</span></span>

6. <span data-ttu-id="e1769-127">Para agregar traducciones de la notificación, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="e1769-127">To add translations of the notification, follow these steps:</span></span>

    1. <span data-ttu-id="e1769-128">Haga clic en **Traducciones**.</span><span class="sxs-lookup"><span data-stu-id="e1769-128">Click **Translations**.</span></span>
    2. <span data-ttu-id="e1769-129">En la página que aparece, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="e1769-129">On the page that appears, click **Add**.</span></span>
    3. <span data-ttu-id="e1769-130">En la lista que aparece, seleccione el idioma en el que escribe el texto.</span><span class="sxs-lookup"><span data-stu-id="e1769-130">In the list that appears, select the language that you're entering the text in.</span></span>
    4. <span data-ttu-id="e1769-131">En el campo **Texto traducido**, escriba el texto.</span><span class="sxs-lookup"><span data-stu-id="e1769-131">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="e1769-132">Para personalizar el texto, puede insertar marcadores de posición como se describe en el paso 5.</span><span class="sxs-lookup"><span data-stu-id="e1769-132">To personalize the text, you can insert placeholders as described in step 5.</span></span>
    6. <span data-ttu-id="e1769-133">Haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="e1769-133">Click **Close**.</span></span>

7. <span data-ttu-id="e1769-134">En la pestaña **Destinatario**, especifique a quién se envían las notificaciones.</span><span class="sxs-lookup"><span data-stu-id="e1769-134">On the **Recipient** tab, specify who the notifications are sent to.</span></span> <span data-ttu-id="e1769-135">Seleccione una de las opciones de la siguiente tabla y, a continuación, siga los pasos adicionales correspondientes a esa opción antes de realizar el paso 8.</span><span class="sxs-lookup"><span data-stu-id="e1769-135">Select one of the options in the following table, and then follow the additional steps for that option before you go to step 8.</span></span>

    <table>
    <thead>
    <tr>
    <th><span data-ttu-id="e1769-136">Opción</span><span class="sxs-lookup"><span data-stu-id="e1769-136">Option</span></span></th>
    <th><span data-ttu-id="e1769-137">Destinatarios de las notificaciones</span><span class="sxs-lookup"><span data-stu-id="e1769-137">Notification recipients</span></span></th>
    <th><span data-ttu-id="e1769-138">Pasos adicionales</span><span class="sxs-lookup"><span data-stu-id="e1769-138">Additional steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td><span data-ttu-id="e1769-139">Participante</span><span class="sxs-lookup"><span data-stu-id="e1769-139">Participant</span></span></td>
    <td><span data-ttu-id="e1769-140">Usuarios asignados a un grupo o rol específicos</span><span class="sxs-lookup"><span data-stu-id="e1769-140">Users who are assigned to a specific group or role</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="e1769-141">Tras seleccionar <strong>Participante</strong>, en la pestaña <strong>Basado en funciones</strong>, en la lista <strong>Tipo de participante</strong>, seleccione el tipo de grupo o rol al que desea enviar las notificaciones.</span><span class="sxs-lookup"><span data-stu-id="e1769-141">After you select <strong>Participant</strong>, on the <strong>Role based</strong> tab, in the <strong>Type of participant</strong> list, select the type of group or role to send notifications to.</span></span></li>
    <li><span data-ttu-id="e1769-142">En la lista <strong>Participante</strong>, seleccione el grupo o rol al que se deben enviar las notificaciones.</span><span class="sxs-lookup"><span data-stu-id="e1769-142">In the <strong>Participant</strong> list, select the group or role to send notifications to.</span></span></li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="e1769-143">Usuario del flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="e1769-143">Workflow user</span></span></td>
    <td><span data-ttu-id="e1769-144">Usuarios que participan en el flujo de trabajo actual</span><span class="sxs-lookup"><span data-stu-id="e1769-144">Users who participate in the current workflow</span></span></td>
    <td>
    <ul>
    <li><span data-ttu-id="e1769-145">Tras seleccionar <strong>Usuario del flujo de trabajo</strong>, en la pestaña <strong>Usuario del flujo de trabajo</strong>, en la pestaña <strong>Usuario del flujo de trabajo</strong>, seleccione un usuario que participe en el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="e1769-145">After you select <strong>Workflow user</strong>, on the <strong>Workflow user</strong> tab, in the <strong>Workflow user</strong> list, select a user who participates in the workflow.</span></span></li>
    </ul>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="e1769-146">Usuario</span><span class="sxs-lookup"><span data-stu-id="e1769-146">User</span></span></td>
    <td><span data-ttu-id="e1769-147">Usuarios concretos</span><span class="sxs-lookup"><span data-stu-id="e1769-147">Specific users</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="e1769-148">Tras seleccionar <strong>Usuario</strong>, haga clic en la pestaña <strong>Usuario</strong>.</span><span class="sxs-lookup"><span data-stu-id="e1769-148">After you select <strong>User</strong>, click the <strong>User</strong> tab.</span></span></li>
    <li><span data-ttu-id="e1769-149">La lista <strong>Usuarios disponibles</strong> incluye todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="e1769-149">The <strong>Available users</strong> list includes all users.</span></span> <span data-ttu-id="e1769-150">Seleccione aquellos a los que desea enviar notificaciones y, a continuación, muévalos a la lista <strong>Usuarios seleccionados</strong>.</span><span class="sxs-lookup"><span data-stu-id="e1769-150">Select the users to send notifications to, and then move those users to the <strong>Selected users</strong> list.</span></span></li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

8. <span data-ttu-id="e1769-151">Repita los pasos 3 a 7 por cada uno de los eventos que haya seleccionado en el paso 2.</span><span class="sxs-lookup"><span data-stu-id="e1769-151">Repeat steps 3 through 7 for each event that you selected in step 2.</span></span>
