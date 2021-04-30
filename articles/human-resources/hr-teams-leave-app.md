---
title: Administrar solicitudes de baja en Teams
description: Este tema muestra cómo solicitar tiempo libre en la aplicación Dynamics 365 Human Resources en Microsoft Teams.
author: andreabichsel
ms.date: 02/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeaveAbsenceWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-05-18
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 48bf6f7997d6159077419bcd05d27fd711c8fb4b
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "5891039"
---
# <a name="manage-leave-requests-in-teams"></a><span data-ttu-id="f3e15-103">Administrar solicitudes de bajas en Teams</span><span class="sxs-lookup"><span data-stu-id="f3e15-103">Manage leave requests in Teams</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="f3e15-104">La aplicación Dynamics 365 Human Resources en Microsoft Teams le permite solicitar rápidamente tiempo libre y ver su información de saldo de tiempo libre directamente en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f3e15-104">The Dynamics 365 Human Resources app in Microsoft Teams lets you quickly request time off and view your time-off balance information right in Microsoft Teams.</span></span> <span data-ttu-id="f3e15-105">Puede interactuar con un bot para solicitar información e iniciar una solicitud de baja.</span><span class="sxs-lookup"><span data-stu-id="f3e15-105">You can interact with a bot to request information and start a leave request.</span></span> <span data-ttu-id="f3e15-106">La pestaña **Tiempo libre** proporciona información más detallada.</span><span class="sxs-lookup"><span data-stu-id="f3e15-106">The **Time off** tab provides more detailed information.</span></span> <span data-ttu-id="f3e15-107">También puede enviar información a los usuarios sobre el próximo tiempo libre en Teams y chats que haya fuera de la aplicación de Human Resources.</span><span class="sxs-lookup"><span data-stu-id="f3e15-107">You can also send people information about your upcoming time off in Teams and chats outside the Human Resources app.</span></span>

## <a name="install-the-app"></a><span data-ttu-id="f3e15-108">Instalar la aplicación</span><span class="sxs-lookup"><span data-stu-id="f3e15-108">Install the app</span></span>

<span data-ttu-id="f3e15-109">Puede encontrar la aplicación Dynamics 365 Human Resources en la tienda de Teams.</span><span class="sxs-lookup"><span data-stu-id="f3e15-109">You can find the Dynamics 365 Human Resources app in the Teams store.</span></span>

1. <span data-ttu-id="f3e15-110">En Microsoft Teams, seleccione los puntos suspensivos.</span><span class="sxs-lookup"><span data-stu-id="f3e15-110">In Microsoft Teams, select the ellipses.</span></span>

   ![Puntos suspensivos de la aplicación de bajas de Recursos Humanos en Teams](./media/hr-teams-leave-app-ellipses.png)
 
2. <span data-ttu-id="f3e15-112">Busque Dynamics 365 Human Resources y luego seleccione el icono **Recursos humanos**.</span><span class="sxs-lookup"><span data-stu-id="f3e15-112">Search for Dynamics 365 Human Resources, and then select the **Human Resources** tile.</span></span>

   ![Icono RR. HH. de la aplicación de bajas de Recursos Humanos en Teams](./media/hr-teams-leave-app-human-resources-tile.png)

3. <span data-ttu-id="f3e15-114">Seleccione el botón **Agregar** para instalar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f3e15-114">Select the **Add** button to install the app.</span></span>

   ![Instalación de la aplicación de bajas de Recursos Humanos en Teams](./media/hr-teams-leave-app-in-store.png)

<span data-ttu-id="f3e15-116">Si la aplicación no inicia sesión automáticamente, seleccione la pestaña **Configuración** para iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="f3e15-116">If the app doesn't automatically sign you in, select the **Settings** tab to sign in.</span></span>

![Pestaña Configuración de la aplicación de bajas de Recursos Humanos en Teams](./media/hr-teams-leave-app-settings-tab.png)

> [!NOTE]
> <span data-ttu-id="f3e15-118">Si no ve un cuadro de diálogo de inicio de sesión, verifique la configuración de su navegador para permitir ventanas emergentes.</span><span class="sxs-lookup"><span data-stu-id="f3e15-118">If you don’t see a sign-in dialog box, check your browser settings to allow pop-ups.</span></span> 

<span data-ttu-id="f3e15-119">Si tiene acceso a más de una instancia de Recursos humanos, puede seleccionar a qué entorno desea conectarse en la pestaña **Configuración**.</span><span class="sxs-lookup"><span data-stu-id="f3e15-119">If you have access to more than one instance of Human Resources, you can select which environment you want to connect to in the **Settings** tab.</span></span>

> [!NOTE]
> <span data-ttu-id="f3e15-120">Ahora la aplicación admite el rol de seguridad Administrador del sistema.</span><span class="sxs-lookup"><span data-stu-id="f3e15-120">The app now supports the System Administrator security role.</span></span>
 
## <a name="use-the-bot"></a><span data-ttu-id="f3e15-121">Usar el bot</span><span class="sxs-lookup"><span data-stu-id="f3e15-121">Use the bot</span></span>

<span data-ttu-id="f3e15-122">Después de la instalación de la aplicación, aparece un mensaje de bienvenida, que le permite saber los tipos de acciones que el bot puede tomar en su nombre.</span><span class="sxs-lookup"><span data-stu-id="f3e15-122">After the app installs, a welcome message appears, letting you know the types of actions the bot can take on your behalf.</span></span>

![Mensaje de bienvenida del bot de la aplicación de bajas de Recursos Humanos en Teams](./media/hr-teams-leave-app-bot.png)
 
> [!NOTE]
> <span data-ttu-id="f3e15-124">Al interactuar por primera vez con el bot, es posible que deba iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="f3e15-124">When first interacting with the bot, you might need to sign in.</span></span> <span data-ttu-id="f3e15-125">Si no ve un cuadro de diálogo de inicio de sesión, verifique la configuración de su navegador para permitir ventanas emergentes.</span><span class="sxs-lookup"><span data-stu-id="f3e15-125">If you don’t see a sign-in dialog box, check your browser settings to allow pop-ups.</span></span>

<span data-ttu-id="f3e15-126">Puede pedirle al bot que:</span><span class="sxs-lookup"><span data-stu-id="f3e15-126">You can ask the bot to:</span></span>

- <span data-ttu-id="f3e15-127">Comience una solicitud de licencia por usted.</span><span class="sxs-lookup"><span data-stu-id="f3e15-127">Start a leave request for you.</span></span>

  ![Iniciar una solicitud de permiso en el chat de Teams](./media/hr-teams-leave-app-initiate.png)

- <span data-ttu-id="f3e15-129">El bot de chat completará una solicitud de permiso para usted.</span><span class="sxs-lookup"><span data-stu-id="f3e15-129">The chat bot will populate a leave request for you.</span></span> <span data-ttu-id="f3e15-130">Seleccione **Solicitar tiempo libre** y edite los detalles de su solicitud.</span><span class="sxs-lookup"><span data-stu-id="f3e15-130">Select **Request time off** and edit the details for your request.</span></span>

  ![Editar detalles de solicitud de baja](./media/hr-teams-leave-app-details.png)

- <span data-ttu-id="f3e15-132">Cuando haya terminado de editar los detalles de su solicitud de permiso, seleccione **Enviar** para enviarlo para su aprobación.</span><span class="sxs-lookup"><span data-stu-id="f3e15-132">When you're done editing your leave request details, select **Submit** to submit it for approval.</span></span>

  ![Enviar solicitud de licencia](./media/hr-teams-leave-app-submit.png)

## <a name="manage-your-leave-in-teams"></a><span data-ttu-id="f3e15-134">Administrar su baja en Teams</span><span class="sxs-lookup"><span data-stu-id="f3e15-134">Manage your leave in Teams</span></span>

<span data-ttu-id="f3e15-135">La pestaña **Tiempo libre** le permite ver:</span><span class="sxs-lookup"><span data-stu-id="f3e15-135">The **Time off** tab allows you to view:</span></span> 

- <span data-ttu-id="f3e15-136">Información del saldo de cada tipo de baja en la que esté inscrito</span><span class="sxs-lookup"><span data-stu-id="f3e15-136">Balance information for each leave type you're enrolled in</span></span>

- <span data-ttu-id="f3e15-137">Próximas solicitudes de baja</span><span class="sxs-lookup"><span data-stu-id="f3e15-137">Upcoming leave requests</span></span>

- <span data-ttu-id="f3e15-138">Solicitudes de tiempo libre</span><span class="sxs-lookup"><span data-stu-id="f3e15-138">Time-off requests</span></span>

- <span data-ttu-id="f3e15-139">Borrador de solicitudes de baja</span><span class="sxs-lookup"><span data-stu-id="f3e15-139">Draft leave requests</span></span>

![Pestaña Tiempo libre de la aplicación de bajas de Recursos Humanos en Teams](./media/hr-teams-leave-app-timeoff-tab.png)
 
### <a name="create-a-new-request"></a><span data-ttu-id="f3e15-141">Crear una nueva solicitud</span><span class="sxs-lookup"><span data-stu-id="f3e15-141">Create a new request</span></span>

1. <span data-ttu-id="f3e15-142">Para crear una nueva solicitud de baja, seleccione **Nueva solicitud**.</span><span class="sxs-lookup"><span data-stu-id="f3e15-142">To create a new leave request, select **New request**.</span></span>

   ![Nueva solicitud de la aplicación de bajas de Recursos Humanos en Teams](./media/hr-teams-leave-app-timeoff-tab-new.png)

2. <span data-ttu-id="f3e15-144">Introduzca el día o días que desea tomarse y luego seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="f3e15-144">Enter the day or days you want to take off, and then select **Add**.</span></span>

   ![Adición de tiempo libre en la aplicación de bajas de Recursos Humanos en Teams](./media/hr-teams-leave-app-timeoff-tab-add.png)

3. <span data-ttu-id="f3e15-146">Si corresponde, introduzca un código de razón.</span><span class="sxs-lookup"><span data-stu-id="f3e15-146">If applicable, enter a reason code.</span></span> <span data-ttu-id="f3e15-147">Introduzca también cualquier comentario y agregue cualquier archivo adjunto.</span><span class="sxs-lookup"><span data-stu-id="f3e15-147">Also enter any comments and add any attachments.</span></span>

4. <span data-ttu-id="f3e15-148">Cuando haya terminado de Introducir información, escriba **Enviar** para enviarlo para su aprobación.</span><span class="sxs-lookup"><span data-stu-id="f3e15-148">When you're done entering information, type **Submit** to submit it for approval.</span></span> <span data-ttu-id="f3e15-149">También puede escribir **Guardar como borrador** para volver a ello más tarde.</span><span class="sxs-lookup"><span data-stu-id="f3e15-149">You can also type **Save as draft** to come back to it later.</span></span>

### <a name="manage-draft-requests"></a><span data-ttu-id="f3e15-150">Administrar solicitudes en borrador</span><span class="sxs-lookup"><span data-stu-id="f3e15-150">Manage draft requests</span></span>

1. <span data-ttu-id="f3e15-151">Seleccione la pestaña **Borradores**.</span><span class="sxs-lookup"><span data-stu-id="f3e15-151">Select the **Drafts** tab.</span></span>

   ![Pestaña Borradores de la aplicación de bajas de Recursos Humanos en Teams](./media/hr-teams-leave-app-drafts-tab.png)

2. <span data-ttu-id="f3e15-153">Seleccione el lápiz para editar la solicitud o seleccione la papelera para eliminar la solicitud.</span><span class="sxs-lookup"><span data-stu-id="f3e15-153">Select the pencil to edit the request, or select the trash can to delete the request.</span></span>

3. <span data-ttu-id="f3e15-154">Realice los cambios necesarios.</span><span class="sxs-lookup"><span data-stu-id="f3e15-154">Make any necessary changes.</span></span> <span data-ttu-id="f3e15-155">Cuando haya terminado de Introducir información, escriba **Enviar** para enviarlo para su aprobación.</span><span class="sxs-lookup"><span data-stu-id="f3e15-155">When you're done entering information, type **Submit** to submit it for approval.</span></span> <span data-ttu-id="f3e15-156">También puede seleccionar **Guardar como borrador** para volver a ello más tarde.</span><span class="sxs-lookup"><span data-stu-id="f3e15-156">You can also select **Save as draft** to come back to it later.</span></span>

   ![Borrador de edición en la aplicación de bajas de Recursos Humanos en Teams](./media/hr-teams-leave-app-drafts-edit.png)
   
### <a name="respond-to-teams-notifications"></a><span data-ttu-id="f3e15-158">Responder a notificaciones de Teams</span><span class="sxs-lookup"><span data-stu-id="f3e15-158">Respond to Teams notifications</span></span>

<span data-ttu-id="f3e15-159">Cuando usted o un trabajador del que es aprobador envíen una solicitud de baja, recibirá una notificación en la aplicación Human Resources en Teams.</span><span class="sxs-lookup"><span data-stu-id="f3e15-159">When you or a worker you're an approver for submits a leave request, you'll receive a notification in the Human Resources app in Teams.</span></span> <span data-ttu-id="f3e15-160">Puede seleccionar la notificación para verla.</span><span class="sxs-lookup"><span data-stu-id="f3e15-160">You can select the notification to view it.</span></span> <span data-ttu-id="f3e15-161">Las notificaciones también aparecen en el área **Chat**.</span><span class="sxs-lookup"><span data-stu-id="f3e15-161">Notifications also appear in the **Chat** area.</span></span>

<span data-ttu-id="f3e15-162">Si es un aprobador, puede seleccionar **Aprobar** o **Denegar** en la notificación.</span><span class="sxs-lookup"><span data-stu-id="f3e15-162">If you're an approver, you can select **Approve** or **Deny** in the notification.</span></span> <span data-ttu-id="f3e15-163">También puede proporcionar un mensaje opcional.</span><span class="sxs-lookup"><span data-stu-id="f3e15-163">You can also provide an optional message.</span></span>

![Notificación de solicitud de baja en la aplicación Recursos Humanos en Teams](./media/hr-teams-leave-app-notification.png)

## <a name="send-upcoming-time-off-information-to-your-coworkers"></a><span data-ttu-id="f3e15-165">Enviar información sobre el próximo tiempo libre a sus compañeros de trabajo</span><span class="sxs-lookup"><span data-stu-id="f3e15-165">Send upcoming time-off information to your coworkers</span></span>

<span data-ttu-id="f3e15-166">Después de instalar la aplicación Recursos humanos para Teams, puede enviar fácilmente información sobre su próximo tiempo libre a sus compañeros de trabajo a través de Teams o chats.</span><span class="sxs-lookup"><span data-stu-id="f3e15-166">After you install the Human Resources app for Teams, you can easily send information about your upcoming time off to your coworkers in teams or chats.</span></span>

1. <span data-ttu-id="f3e15-167">En un equipo o chat de Teams, seleccione el botón Recursos humanos debajo de la ventana de chat.</span><span class="sxs-lookup"><span data-stu-id="f3e15-167">In a team or chat in Teams, select the Human Resources button below the chat window.</span></span>

   ![Botón de recursos humanos bajo la ventana de chat](./media/hr-teams-leave-app-chat-button.png)

2. <span data-ttu-id="f3e15-169">Seleccione la solicitud de baja que desea compartir.</span><span class="sxs-lookup"><span data-stu-id="f3e15-169">Select the leave request you want to share.</span></span> <span data-ttu-id="f3e15-170">Si desea compartir un borrador de solicitud de baja, primero seleccione **Borradores**.</span><span class="sxs-lookup"><span data-stu-id="f3e15-170">If you want to share a draft leave request, select **Drafts** first.</span></span>

   ![Seleccionar una solicitud de baja próxima para compartirla](./media/hr-teams-leave-app-chat-search.png)

<span data-ttu-id="f3e15-172">Su solicitud de baja se mostrará en el chat.</span><span class="sxs-lookup"><span data-stu-id="f3e15-172">Your leave request will display in the chat.</span></span>

![Tarjeta de solicitud de baja de recursos humanos](./media/hr-teams-leave-app-chat-card.png)

<span data-ttu-id="f3e15-174">Si compartió un borrador de solicitud, se mostrará como un borrador:</span><span class="sxs-lookup"><span data-stu-id="f3e15-174">If you shared a draft request, it will display as a draft:</span></span>

![Tarjeta de solicitud de baja de recursos humanos](./media/hr-teams-leave-app-chat-draft-card.png)

## <a name="view-your-teams-leave-calendar"></a><span data-ttu-id="f3e15-176">Ver el calendario de bajas de su equipo</span><span class="sxs-lookup"><span data-stu-id="f3e15-176">View your team's leave calendar</span></span>

<span data-ttu-id="f3e15-177">Si es un director con subordinados directos, puede ver el tiempo libre aprobado y pendiente de su equipo.</span><span class="sxs-lookup"><span data-stu-id="f3e15-177">If you're a manager with direct reports, you can view your team's approved and pending time off.</span></span>

1. <span data-ttu-id="f3e15-178">En la aplicación Human Resources en Teams, seleccione **Tiempo libre**.</span><span class="sxs-lookup"><span data-stu-id="f3e15-178">In the Human Resources app in Teams, select **Time off**.</span></span>

2. <span data-ttu-id="f3e15-179">Seleccione **Calendario del equipo**.</span><span class="sxs-lookup"><span data-stu-id="f3e15-179">Select **Team calendar**.</span></span> <span data-ttu-id="f3e15-180">El calendario muestra el tiempo libre aprobado y pendiente de sus subordinados directos.</span><span class="sxs-lookup"><span data-stu-id="f3e15-180">The calendar displays your direct reports' approved and pending time off.</span></span>

   ![Ver el calendario en la aplicación Human Resources Teams](./media/hr-teams-leave-app-view-calendar.png)

   > [!NOTE]
   > <span data-ttu-id="f3e15-182">Si no puede ver el calendario del equipo, pídale a su administrador que lo habilite.</span><span class="sxs-lookup"><span data-stu-id="f3e15-182">If you can't see the team calendar, ask your admin to enable it.</span></span> <span data-ttu-id="f3e15-183">Para obtener más información consulte [Instalar y configurar](hr-admin-teams-leave-app.md#install-and-setup).</span><span class="sxs-lookup"><span data-stu-id="f3e15-183">For more information, see [Install and setup](hr-admin-teams-leave-app.md#install-and-setup).</span></span>

## <a name="supported-languages"></a><span data-ttu-id="f3e15-184">Idiomas admitidos</span><span class="sxs-lookup"><span data-stu-id="f3e15-184">Supported languages</span></span>

<span data-ttu-id="f3e15-185">La aplicación Dynamics 365 Human Resources en Teams admite los siguientes idiomas:</span><span class="sxs-lookup"><span data-stu-id="f3e15-185">The Dynamics 365 Human Resources app in Teams supports the following languages:</span></span>

| <span data-ttu-id="f3e15-186">ID de configuración regional</span><span class="sxs-lookup"><span data-stu-id="f3e15-186">Locale ID</span></span> | <span data-ttu-id="f3e15-187">Idioma</span><span class="sxs-lookup"><span data-stu-id="f3e15-187">Language</span></span> |
| --- | --- |
| <span data-ttu-id="f3e15-188">de-DE</span><span class="sxs-lookup"><span data-stu-id="f3e15-188">de-DE</span></span> | <span data-ttu-id="f3e15-189">Alemán (Alemania)</span><span class="sxs-lookup"><span data-stu-id="f3e15-189">German (Germany)</span></span> |
| <span data-ttu-id="f3e15-190">es-ES</span><span class="sxs-lookup"><span data-stu-id="f3e15-190">es-ES</span></span> | <span data-ttu-id="f3e15-191">Español (España)</span><span class="sxs-lookup"><span data-stu-id="f3e15-191">Spanish (Spain)</span></span> |
| <span data-ttu-id="f3e15-192">es-MX</span><span class="sxs-lookup"><span data-stu-id="f3e15-192">es-MX</span></span> | <span data-ttu-id="f3e15-193">Español (México)</span><span class="sxs-lookup"><span data-stu-id="f3e15-193">Spanish (Mexico)</span></span> |
| <span data-ttu-id="f3e15-194">fr-CA</span><span class="sxs-lookup"><span data-stu-id="f3e15-194">fr-CA</span></span> | <span data-ttu-id="f3e15-195">Francés (Canadá)</span><span class="sxs-lookup"><span data-stu-id="f3e15-195">French (Canada)</span></span> |
| <span data-ttu-id="f3e15-196">fr-FR</span><span class="sxs-lookup"><span data-stu-id="f3e15-196">fr-FR</span></span> | <span data-ttu-id="f3e15-197">Francés (Francia)</span><span class="sxs-lookup"><span data-stu-id="f3e15-197">French (France)</span></span> |
| <span data-ttu-id="f3e15-198">it-IT</span><span class="sxs-lookup"><span data-stu-id="f3e15-198">it-IT</span></span> | <span data-ttu-id="f3e15-199">Italiano (Italia)</span><span class="sxs-lookup"><span data-stu-id="f3e15-199">Italian (Italy)</span></span> |
| <span data-ttu-id="f3e15-200">nl-NL</span><span class="sxs-lookup"><span data-stu-id="f3e15-200">nl-NL</span></span> | <span data-ttu-id="f3e15-201">Neerlandés (Países Bajos)</span><span class="sxs-lookup"><span data-stu-id="f3e15-201">Dutch (Netherlands)</span></span> |
| <span data-ttu-id="f3e15-202">pt-BR</span><span class="sxs-lookup"><span data-stu-id="f3e15-202">pt-BR</span></span> | <span data-ttu-id="f3e15-203">Portugués (Brasil)</span><span class="sxs-lookup"><span data-stu-id="f3e15-203">Portuguese (Brazil)</span></span> |
| <span data-ttu-id="f3e15-204">tr-TR</span><span class="sxs-lookup"><span data-stu-id="f3e15-204">tr-TR</span></span> | <span data-ttu-id="f3e15-205">Turco (Turquía)</span><span class="sxs-lookup"><span data-stu-id="f3e15-205">Turkish (Turkey)</span></span> |
| <span data-ttu-id="f3e15-206">zh-CN</span><span class="sxs-lookup"><span data-stu-id="f3e15-206">zh-CN</span></span> | <span data-ttu-id="f3e15-207">Chino (Simplificado)</span><span class="sxs-lookup"><span data-stu-id="f3e15-207">Chinese (Simplified)</span></span> |

## <a name="troubleshooting"></a><span data-ttu-id="f3e15-208">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="f3e15-208">Troubleshooting</span></span>

<span data-ttu-id="f3e15-209">Si tiene problemas para iniciar sesión o utilizar la aplicación Dynamics 365 Human Resources Teams, intente seguir estas instrucciones de solución de problemas.</span><span class="sxs-lookup"><span data-stu-id="f3e15-209">If you're having trouble signing into or using the Dynamics 365 Human Resources Teams app, try following these troubleshooting instructions.</span></span> <span data-ttu-id="f3e15-210">Si sigue teniendo problemas después de la resolución de problemas, comuníquese con Soporte.</span><span class="sxs-lookup"><span data-stu-id="f3e15-210">If you're still having problems after troubleshooting, contact Support.</span></span> <span data-ttu-id="f3e15-211">Para obtener más información, consulte [Obtener soporte](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md).</span><span class="sxs-lookup"><span data-stu-id="f3e15-211">For more information, see [Get support](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md).</span></span>

### <a name="cant-sign-into-the-human-resources-app-in-teams"></a><span data-ttu-id="f3e15-212">No puedo iniciar sesión en la aplicación de recursos humanos en Teams</span><span class="sxs-lookup"><span data-stu-id="f3e15-212">Can't sign into the Human Resources app in Teams</span></span>

<span data-ttu-id="f3e15-213">Si no puede iniciar sesión en la aplicación, es posible que la cuenta que está usando para iniciar sesión en Microsoft Teams no está asociado con un registro de empleado en Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="f3e15-213">If you can't sign into the app, it's possible that the account you're using to sign into Microsoft Teams isn't associated with an employee record in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="f3e15-214">Comuníquese con el administrador del sistema para asegurarse de que su registro de empleado esté asociado correctamente.</span><span class="sxs-lookup"><span data-stu-id="f3e15-214">Contact your system administrator to ensure your employee record is correctly associated.</span></span>

### <a name="translations-dont-display-correctly"></a><span data-ttu-id="f3e15-215">Las traducciones no se muestran correctamente</span><span class="sxs-lookup"><span data-stu-id="f3e15-215">Translations don't display correctly</span></span>

<span data-ttu-id="f3e15-216">Si las traducciones no se muestran como se esperaba, asegúrese de que el idioma que seleccione en Teams coincida con el idioma seleccionado en las **Opciones de usuario** de Human Resources.</span><span class="sxs-lookup"><span data-stu-id="f3e15-216">If translations don't display as expected, make sure the language you select in Teams matches the language selected in Human Resources **User options**.</span></span>

<span data-ttu-id="f3e15-217">En Teams, mire **Idioma de la aplicación** en **Ajustes**.</span><span class="sxs-lookup"><span data-stu-id="f3e15-217">In Teams, look at **App language** in **Settings**.</span></span>

![Configuración de Teams](./media/hr-teams-leave-app-settings.png)

<span data-ttu-id="f3e15-219">En Human Resources, seleccione **Ajustes** y luego seleccione **Opciones de usuario**.</span><span class="sxs-lookup"><span data-stu-id="f3e15-219">In Human Resources, select **Settings** and then select **User options**.</span></span> <span data-ttu-id="f3e15-220">Verifique que el campo **Idioma** coincide con el campo **Idioma de la aplicación** en Teams.</span><span class="sxs-lookup"><span data-stu-id="f3e15-220">Verify that the **Language** field matches the **App language** field in Teams.</span></span>

![Opciones de usuario de Human Resources](./media/hr-teams-leave-app-user-options.png)

<span data-ttu-id="f3e15-222">Si aún tiene problemas de traducción, háganoslo saber.</span><span class="sxs-lookup"><span data-stu-id="f3e15-222">If you still experience translation issues, let us know.</span></span> <span data-ttu-id="f3e15-223">Para obtener información, consulte [Obtener soporte técnico para aplicaciones de Finance and Operations o Lifecycle Services (LCS)](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md?toc=%2fdynamics365%2fhuman-resources%2ftoc.json).</span><span class="sxs-lookup"><span data-stu-id="f3e15-223">For information, see [Get support for Finance and Operations apps or Lifecycle Services (LCS)](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md?toc=%2fdynamics365%2fhuman-resources%2ftoc.json).</span></span>

### <a name="error-when-approving-leave-requests-in-the-human-resources-app-in-teams"></a><span data-ttu-id="f3e15-224">Error al aprobar solicitudes de licencia en la aplicación Human Resources en Teams</span><span class="sxs-lookup"><span data-stu-id="f3e15-224">Error when approving leave requests in the Human Resources app in Teams</span></span>

<span data-ttu-id="f3e15-225">Si recibe un error cuando intenta aprobar solicitudes de permiso en la aplicación Teams, intente los siguientes pasos de solución de problemas:</span><span class="sxs-lookup"><span data-stu-id="f3e15-225">If you receive an error when you're trying to approve leave requests in the Teams app, try the following troubleshooting steps:</span></span>

1. <span data-ttu-id="f3e15-226">Verifique que la cuenta que está usando para iniciar sesión en Microsoft Teams es la misma que usa para acceder a Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="f3e15-226">Verify that the account you're using to sign into Microsoft Teams is the same one you use for accessing Dynamics 365 Human Resources.</span></span>

2. <span data-ttu-id="f3e15-227">Verifique que es un aprobador válido para la solicitud al verificar la configuración del flujo de trabajo para la aprobación de la licencia.</span><span class="sxs-lookup"><span data-stu-id="f3e15-227">Verify that you're a valid approver for the request by checking the workflow settings for leave approval.</span></span> <span data-ttu-id="f3e15-228">Para obtener más información sobre los flujos de trabajo de solicitud de licencia, consulte [Crear un flujo de trabajo de solicitud de licencia](hr-leave-and-absence-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="f3e15-228">For more information about leave request workflows, see [Create a leave request workflow](hr-leave-and-absence-workflow.md).</span></span>

## <a name="known-accessibility-issues"></a><span data-ttu-id="f3e15-229">Problemas de accesibilidad conocidos</span><span class="sxs-lookup"><span data-stu-id="f3e15-229">Known accessibility issues</span></span>

<span data-ttu-id="f3e15-230">La aplicación Human Resources en Teams tiene los siguientes problemas de accesibilidad en los que estamos trabajando para solucionarlos en futuras versiones.</span><span class="sxs-lookup"><span data-stu-id="f3e15-230">The Human Resources app in Teams has the following accessibility issues that we're working on fixing in future releases.</span></span>

| <span data-ttu-id="f3e15-231">Emitir</span><span class="sxs-lookup"><span data-stu-id="f3e15-231">Issue</span></span> | <span data-ttu-id="f3e15-232">Solución alternativa o explicación</span><span class="sxs-lookup"><span data-stu-id="f3e15-232">Workaround or explanation</span></span> |
| --- | --- |
| <span data-ttu-id="f3e15-233">Hacer zoom al 400 % en el escritorio oculta algunos de los botones de acción de la vista.</span><span class="sxs-lookup"><span data-stu-id="f3e15-233">Zooming to 400% on desktop hides some of the action buttons from view.</span></span> | <span data-ttu-id="f3e15-234">Recomendamos usar una lupa en su lugar hasta que podamos admitir este nivel de zoom.</span><span class="sxs-lookup"><span data-stu-id="f3e15-234">We recommend using a magnifier instead until we can support this zoom level.</span></span> |
| <span data-ttu-id="f3e15-235">En la pestaña **Tiempo libre**, VoiceOver anuncia la acción de un botón mientras se lee el encabezado de la cuadrícula de tiempo libre.</span><span class="sxs-lookup"><span data-stu-id="f3e15-235">On the **Time off** tab, voiceover announces a button action while reading the header for the time-off grid.</span></span> | <span data-ttu-id="f3e15-236">El encabezado y los elementos de la cuadrícula están agrupados por año y se pueden contraer.</span><span class="sxs-lookup"><span data-stu-id="f3e15-236">The header and elements within the grid are grouped by year, and they're collapsible.</span></span> <span data-ttu-id="f3e15-237">VoiceOver interpreta esto como un elemento procesable, pero no lo es.</span><span class="sxs-lookup"><span data-stu-id="f3e15-237">Voiceover interprets this as an actionable item, but it isn't.</span></span> |
| <span data-ttu-id="f3e15-238">En la pestaña **Tiempo libre**, hay un gesto adicional de deslizar rápidamente al navegar a **Código de razón** en una nueva solicitud.</span><span class="sxs-lookup"><span data-stu-id="f3e15-238">On the **Time off** tab, there's an extra swipe gesture when navigating to **Reason code** in a new request.</span></span> | <span data-ttu-id="f3e15-239">No hay ningún control oculto al que esté intentando obtener acceso la navegación por deslizamiento.</span><span class="sxs-lookup"><span data-stu-id="f3e15-239">There is no hidden control that the swipe navigation is trying to get to.</span></span> |
| <span data-ttu-id="f3e15-240">En la pestaña **Tiempo libre**, si desliza el dedo mientras el calendario está abierto, terminará fuera del control en lugar de en la parte superior de una nueva solicitud o mientras edita una solicitud.</span><span class="sxs-lookup"><span data-stu-id="f3e15-240">On the **Time off** tab, if you swipe while the calendar is open, you end up outside the control instead of at the top in a new request or while editing a request.</span></span> | <span data-ttu-id="f3e15-241">Al llegar a **Ir a hoy**, considérelo como el final del control y deslice el dedo en la dirección inversa para volver a la parte superior.</span><span class="sxs-lookup"><span data-stu-id="f3e15-241">When you reach **Go to today**, consider that to be the end of the control and swipe in the reverse direction to get back to the top.</span></span> |
| <span data-ttu-id="f3e15-242">En la pestaña **Chat**, el foco vuelve a la parte superior cuando introduce una fecha mientras usa la herramienta de asistencia o la navegación del teclado.</span><span class="sxs-lookup"><span data-stu-id="f3e15-242">On the **Chat** tab, the focus jumps back to the top when you enter a date while using the assistive tool or keyboard navigation.</span></span> | <span data-ttu-id="f3e15-243">Desplácese con el tabulador hasta que llegue a su área de entrada de nuevo.</span><span class="sxs-lookup"><span data-stu-id="f3e15-243">Tab until you reach your input area again.</span></span> |

## <a name="privacy-notice"></a><span data-ttu-id="f3e15-244">Aviso de privacidad</span><span class="sxs-lookup"><span data-stu-id="f3e15-244">Privacy notice</span></span>

### <a name="microsoft-language-understanding-intelligent-service-luis"></a><span data-ttu-id="f3e15-245">Servicio inteligente de comprensión del lenguaje de Microsoft (LUIS)</span><span class="sxs-lookup"><span data-stu-id="f3e15-245">Microsoft Language Understanding Intelligent Service (LUIS)</span></span>

<span data-ttu-id="f3e15-246">Con el bot de Dynamics 365 Human Resources en Microsoft Teams, las entradas de texto del usuario se analizan para comprender la consulta/intención subyacente.</span><span class="sxs-lookup"><span data-stu-id="f3e15-246">With the Dynamics 365 Human Resources bot in Microsoft Teams, the user’s text inputs are analyzed for understanding the underlying query/intent.</span></span> <span data-ttu-id="f3e15-247">La entrada del usuario como “Buscar cuenta de Contoso” se enruta a uno de los Servicios cognitivos de Microsoft, denominado Servicio inteligente de comprensión del lenguaje (LUIS).</span><span class="sxs-lookup"><span data-stu-id="f3e15-247">The user’s input such as “Search account Contoso” is routed to one of Microsoft’s Cognitive Service called Language Understanding Intelligent Service (LUIS).</span></span> <span data-ttu-id="f3e15-248">Obtenga más información sobre LUIS [aquí](https://www.luis.ai/).</span><span class="sxs-lookup"><span data-stu-id="f3e15-248">Read more about LUIS [here](https://www.luis.ai/).</span></span> <span data-ttu-id="f3e15-249">El servicio LUIS desambigua o comprende la intención de la entrada del usuario (en este caso, la intención es encontrar información) y la entidad objetivo (en este caso, la entidad objetivo es una cuenta llamada Contoso).</span><span class="sxs-lookup"><span data-stu-id="f3e15-249">The LUIS service disambiguates or understands the intent of user input (in this case, the intent is to find information) and the target entity (in this case, the intended entity is an account named Contoso).</span></span> <span data-ttu-id="f3e15-250">Esta información se pasa luego al  [marco de bot de Azure](https://azure.microsoft.com/services/bot-service/) de Microsoft, que interactúa con los datos de Dynamics 365 Human Resources y recupera la información deseada para la consulta del usuario.</span><span class="sxs-lookup"><span data-stu-id="f3e15-250">This information is then passed on to Microsoft’s [Azure bot framework](https://azure.microsoft.com/services/bot-service/), which interacts with data from Dynamics 365 Human Resources and retrieves the desired information for the user query.</span></span> 

<span data-ttu-id="f3e15-251">Al instalar y permitir el acceso al uso del bot, usted acepta permitir que el servicio LUIS y el marco del bot de Azure procesen la intención de detrás de la entrada, lo que da por resultado una experiencia de usuario conversacional mejorada.</span><span class="sxs-lookup"><span data-stu-id="f3e15-251">By installing and allowing access to use of the bot, you agree to allow the LUIS service and Azure bot framework to process the intent behind the input,  which results in an enhanced conversational user experience.</span></span> <span data-ttu-id="f3e15-252">El servicio LUIS y el marco de bot de Azure pueden tener diferentes niveles de cumplimiento en comparación con Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="f3e15-252">The LUIS service and Azure bot framework may have varying levels of compliance compared to Dynamics 365 Human Resources.</span></span> <span data-ttu-id="f3e15-253">Si bien el servicio LUIS solo tiene acceso a las consultas del usuario y no está diseñado para conectarse a datos o a la cuenta Dynamics 365 Human Resources del usuario, un usuario del bot Dynamics 365 Human Resources podría Introducir voluntariamente una consulta que contenga datos del cliente, datos personales u otros datos y dicho contenido de la consulta podría enviarse al servicio LUIS y al marco del bot de Azure.</span><span class="sxs-lookup"><span data-stu-id="f3e15-253">While the LUIS service has access to only the user queries and is not designed to be connected to the user’s Dynamics 365 Human Resources data or account, a user of the Dynamics 365 Human Resources bot could voluntarily enter a query containing Customer Data, Personal Data, or other data and such query content could get sent to the LUIS service and the Azure bot framework.</span></span> 

<span data-ttu-id="f3e15-254">El contenido de las consultas y los mensajes del usuario se conserva en el sistema LUIS durante un máximo de 30 días, se cifra en reposo y no se utiliza para la formación ni la mejora del servicio.</span><span class="sxs-lookup"><span data-stu-id="f3e15-254">The content of user’s queries and messages is retained in LUIS system for a maximum of 30 days, is encrypted at rest, and is not used for training or service improvement.</span></span> <span data-ttu-id="f3e15-255">Puede obtener más información sobre servicios cognitivos  [aquí](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/).</span><span class="sxs-lookup"><span data-stu-id="f3e15-255">Read more about Cognitive Services [here](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/).</span></span> 

<span data-ttu-id="f3e15-256">Para administrar la configuración de administración de aplicaciones en Microsoft Teams, vaya al [Centro de administración de Microsoft Teams](https://admin.teams.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="f3e15-256">To manage admin settings for apps in Microsoft Teams, go to the [Microsoft Teams admin center](https://admin.teams.microsoft.com/).</span></span>

### <a name="microsoft-teams-azure-event-grid-and-azure-cosmos-db"></a><span data-ttu-id="f3e15-257">Microsoft Teams, Azure Event Grid y Azure Cosmos DB</span><span class="sxs-lookup"><span data-stu-id="f3e15-257">Microsoft Teams, Azure Event Grid, and Azure Cosmos DB</span></span>

<span data-ttu-id="f3e15-258">Al utilizar la característica de notificaciones para la aplicación Dynamics 365 Human Resources en Microsoft Teams, algunos datos de clientes saldrán de la región geográfica donde se implementa el servicio de Recursos Humanos del inquilino.</span><span class="sxs-lookup"><span data-stu-id="f3e15-258">When using the Dynamics 365 Human Resources app in Microsoft Teams, certain customer data may flow outside of the geographic region where your tenant’s Human Resources service is deployed.</span></span>

<span data-ttu-id="f3e15-259">Dynamics 365 Human Resources transmite la solicitud de licencia del empleado y los detalles de la tarea del flujo de trabajo a Microsoft Azure Event Grid y Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f3e15-259">Dynamics 365 Human Resources transmits the employee’s leave request and workflow task details to Microsoft Azure Event Grid and Microsoft Teams.</span></span> <span data-ttu-id="f3e15-260">Estos datos pueden almacenarse en Microsoft Azure Event Grid hasta por 24 horas y se procesarán en los Estados Unidos, están cifrados en tránsito y en reposo, y Microsoft o sus subprocesadores no los utilizan para mejoras de formación o servicios.</span><span class="sxs-lookup"><span data-stu-id="f3e15-260">This data may be stored in Microsoft Azure Event Grid for up to 24 hours and will be processed in the United States, is encrypted in transit and at rest, and is not used by Microsoft or its subprocessors for training or service improvements.</span></span> <span data-ttu-id="f3e15-261">Para comprender dónde se almacenan sus datos en Teams, consulte: [Ubicación de los datos en Microsoft Teams](/microsoftteams/location-of-data-in-teams?preserve-view=true&view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="f3e15-261">To understand where your data is stored in Teams, please see: [Location of data in Microsoft Teams](/microsoftteams/location-of-data-in-teams?preserve-view=true&view=o365-worldwide).</span></span>

<span data-ttu-id="f3e15-262">Mientras conversa con el bot de chat en la aplicación de Recursos Humanos, el contenido de la conversación puede almacenarse en Azure Cosmos DB y transmitirse a Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f3e15-262">While conversing with the chat bot in the Human Resources app, the conversation content may be stored in Azure Cosmos DB and transmitted to Microsoft Teams.</span></span> <span data-ttu-id="f3e15-263">Estos datos pueden almacenarse en Azure Cosmos DB durante un máximo de 24 horas y pueden procesarse fuera de la región geográfica donde se implementa el servicio de Recursos Humanos de su inquilino, están cifrados en tránsito y en reposo, y Microsoft o sus subprocesadores no los utilizan para mejoras de formación o servicio.</span><span class="sxs-lookup"><span data-stu-id="f3e15-263">This data may be stored in Azure Cosmos DB for up to 24 hours and may be processed outside of the geographic region where your tenant's Human Resources service is deployed, is encrypted in transit and at rest, and is not used by Microsoft or its subprocessors for training or service improvements.</span></span> <span data-ttu-id="f3e15-264">Para comprender dónde se almacenan sus datos en Teams, consulte: [Ubicación de los datos en Microsoft Teams](/microsoftteams/location-of-data-in-teams?preserve-view=true&view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="f3e15-264">To understand where your data is stored in Teams, please see: [Location of data in Microsoft Teams](/microsoftteams/location-of-data-in-teams?preserve-view=true&view=o365-worldwide).</span></span>
 
<span data-ttu-id="f3e15-265">Para restringir el acceso a la aplicación de Recursos Humanos en Microsoft Teams para su organización o para usuarios de su organización, consulte [Administrar las directivas de permisos de aplicaciones en Microsoft Teams](/MicrosoftTeams/teams-app-permission-policies).</span><span class="sxs-lookup"><span data-stu-id="f3e15-265">To restrict access to the Human Resources app in Microsoft Teams for your organization or users within your organization, see [Manage app permission policies in Microsoft Teams](/MicrosoftTeams/teams-app-permission-policies).</span></span>

## <a name="see-also"></a><span data-ttu-id="f3e15-266">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f3e15-266">See also</span></span>

[<span data-ttu-id="f3e15-267">Descargar e instalar Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f3e15-267">Download and install Microsoft Teams</span></span>](https://support.office.com/article/download-and-install-microsoft-teams-422bf3aa-9ae8-46f1-83a2-e65720e1a34d)</br>
[<span data-ttu-id="f3e15-268">Centro de ayuda de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f3e15-268">Microsoft Teams help center</span></span>](https://support.office.com/teams)</br>
[<span data-ttu-id="f3e15-269">Aplicación Human Resources en Teams</span><span class="sxs-lookup"><span data-stu-id="f3e15-269">Human Resources app in Teams</span></span>](hr-admin-teams-leave-app.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]