---
title: Aplicación Recursos humanos en Teams
description: Este tema presenta la aplicación Microsoft Dynamics 365 Human Resources en Microsoft Teams.
author: andreabichsel
manager: AnnBe
ms.date: 09/30/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: FeatureManagementWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-05-18
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 51f04e553da822c4e09d31bcd72c71b674ad1f1b
ms.sourcegitcommit: b6ab46f6e5ce60e2c3d70a348827eaf60c84cae2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2020
ms.locfileid: "3930026"
---
# <a name="human-resources-app-in-teams"></a><span data-ttu-id="fa5e6-103">Aplicación Recursos humanos en Teams</span><span class="sxs-lookup"><span data-stu-id="fa5e6-103">Human Resources app in Teams</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="fa5e6-104">La aplicación Microsoft Dynamics 365 Human Resources de Microsoft Teams permite a los empleados solicitar rápidamente tiempo libre y ver su información de saldo de tiempo libre en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="fa5e6-104">The Microsoft Dynamics 365 Human Resources app in Microsoft Teams lets employees quickly request time off and view their time-off balance information in Microsoft Teams.</span></span> <span data-ttu-id="fa5e6-105">Los empleados pueden interactuar con un bot para solicitar información.</span><span class="sxs-lookup"><span data-stu-id="fa5e6-105">Employees can interact with a bot to request information.</span></span> <span data-ttu-id="fa5e6-106">La pestaña **Tiempo libre** proporciona información más detallada.</span><span class="sxs-lookup"><span data-stu-id="fa5e6-106">The **Time off** tab provides more detailed information.</span></span> <span data-ttu-id="fa5e6-107">Además, pueden enviar información a los usuarios sobre el próximo tiempo libre a través de equipos y chats que haya fuera de la aplicación de Human Resources.</span><span class="sxs-lookup"><span data-stu-id="fa5e6-107">In addition, they can send people information about upcoming time off in teams and chats outside the Human Resources app.</span></span>

![Bot de la aplicación de bajas de Recursos Humanos en Teams](./media/hr-admin-teams-leave-app-bot.png)

![Pestaña Tiempo libre de la aplicación de bajas de Recursos Humanos en Teams](./media/hr-teams-leave-app-timeoff-tab.png)

![Tarjeta de solicitud de baja de recursos humanos](./media/hr-teams-leave-app-chat-card.png)

## <a name="install-and-setup"></a><span data-ttu-id="fa5e6-111">Instalar y configurar</span><span class="sxs-lookup"><span data-stu-id="fa5e6-111">Install and setup</span></span>

<span data-ttu-id="fa5e6-112">Puede encontrar la aplicación Recursos Humanos en la tienda Teams.</span><span class="sxs-lookup"><span data-stu-id="fa5e6-112">You can find the Human Resources app in the Teams store.</span></span> <span data-ttu-id="fa5e6-113">Para obtener información sobre cómo instalar la aplicación Teams, consulte [Administrar solicitudes de licencia en Teams](hr-teams-leave-app.md).</span><span class="sxs-lookup"><span data-stu-id="fa5e6-113">For information about installing the Teams app, see [Manage leave requests in Teams](hr-teams-leave-app.md).</span></span>

<span data-ttu-id="fa5e6-114">Para obtener información sobre la administración de permisos de aplicaciones en Teams, consulte [Administrar las directivas de permisos de aplicaciones en Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).</span><span class="sxs-lookup"><span data-stu-id="fa5e6-114">For information about managing app permissions in Teams, see [Manage app permission policies in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).</span></span>

## <a name="enable-notifications-for-the-human-resources-app-in-teams"></a><span data-ttu-id="fa5e6-115">Habilitar notificaciones para la aplicación Human Resources en Teams</span><span class="sxs-lookup"><span data-stu-id="fa5e6-115">Enable notifications for the Human Resources app in Teams</span></span>

<span data-ttu-id="fa5e6-116">Si desea que los usuarios reciban notificaciones de solicitud de permiso en la aplicación Teams, debe habilitar las notificaciones en Human Resources.</span><span class="sxs-lookup"><span data-stu-id="fa5e6-116">If you want users to receive leave request notifications in the Teams app, you must enable notifications in Human Resources.</span></span>

>[!NOTE]
><span data-ttu-id="fa5e6-117">Solo los usuarios que hayan iniciado sesión en Teams y que utilicen la aplicación Human Resources Teams recibirán notificaciones.</span><span class="sxs-lookup"><span data-stu-id="fa5e6-117">Only users who are signed into Teams and using the Human Resources Teams app will receive notifications.</span></span>

1. <span data-ttu-id="fa5e6-118">En Human Resources, seleccione **Administración del sistema**.</span><span class="sxs-lookup"><span data-stu-id="fa5e6-118">In Human Resources, select **System administration**.</span></span>

2. <span data-ttu-id="fa5e6-119">Seleccione **Vínculos**.</span><span class="sxs-lookup"><span data-stu-id="fa5e6-119">Select **Links**.</span></span>

3. <span data-ttu-id="fa5e6-120">En **Configuración**, seleccione **Parámetros del sistema**.</span><span class="sxs-lookup"><span data-stu-id="fa5e6-120">Under **Setup**, select **System parameters**.</span></span>

4. <span data-ttu-id="fa5e6-121">En la pestaña **General**, establezca **Habilitar notificaciones para la aplicación Teams** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="fa5e6-121">On the **General** tab, set **Enable notifications for Teams app** to **Yes**.</span></span>

   ![Habilitar las notificaciones de la aplicación Teams en los parámetros del sistema](./media/hr-admin-teams-leave-app-enable-notifications.png)

5. <span data-ttu-id="fa5e6-123">Para activar las notificaciones de Teams para todos los usuarios, seleccione **Sí** en el aviso.</span><span class="sxs-lookup"><span data-stu-id="fa5e6-123">To turn on Teams notifications for all users, select **Yes** at the prompt.</span></span>

   ![Habilitar notificaciones de Teams para todos los usuarios](./media/hr-admin-teams-leave-app-notifications-all-users.png)

### <a name="turn-teams-notifications-on-or-off-for-individual-users"></a><span data-ttu-id="fa5e6-125">Activar o desactivar las notificaciones de Teams para usuarios individuales</span><span class="sxs-lookup"><span data-stu-id="fa5e6-125">Turn Teams notifications on or off for individual users</span></span>

<span data-ttu-id="fa5e6-126">Una vez que haya habilitado las notificaciones para la aplicación en la aplicación Human Resources Teams, puede activar o desactivar las notificaciones para usuarios individuales.</span><span class="sxs-lookup"><span data-stu-id="fa5e6-126">After you've enabled notifications for the Human Resources Teams app, you can turn notifications on or off for individual users.</span></span>

1. <span data-ttu-id="fa5e6-127">En Human Resources, seleccione **Administración del sistema**.</span><span class="sxs-lookup"><span data-stu-id="fa5e6-127">In Human Resources, select **System administration**.</span></span>

2. <span data-ttu-id="fa5e6-128">Seleccione **Vínculos**.</span><span class="sxs-lookup"><span data-stu-id="fa5e6-128">Select **Links**.</span></span>

3. <span data-ttu-id="fa5e6-129">En **Usuarios**, seleccione **Opciones de usuario**.</span><span class="sxs-lookup"><span data-stu-id="fa5e6-129">Under **Users**, select **User options**.</span></span>

4. <span data-ttu-id="fa5e6-130">Seleccione la pestaña **Flujo de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="fa5e6-130">Select the **Workflow** tab.</span></span>

5. <span data-ttu-id="fa5e6-131">Establezca **Habilitar notificaciones para la aplicación Teams** en **Sí** para habilitar notificaciones para el usuario o **No** para deshabilitar las notificaciones para el usuario.</span><span class="sxs-lookup"><span data-stu-id="fa5e6-131">Set **Enable notifications for Teams app** to **Yes** to enable notifications for the user or **No** to disable notifications for the user.</span></span>

   ![Habilitar las notificaciones de la aplicación Teams en la pestaña Flujo de trabajo de opciones de usuario](./media/hr-admin-teams-leave-app-notifications.png)

6. <span data-ttu-id="fa5e6-133">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="fa5e6-133">Select **Save**.</span></span>

## <a name="known-issues"></a><span data-ttu-id="fa5e6-134">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="fa5e6-134">Known issues</span></span>

| <span data-ttu-id="fa5e6-135">Emitir</span><span class="sxs-lookup"><span data-stu-id="fa5e6-135">Issue</span></span> | <span data-ttu-id="fa5e6-136">Estado</span><span class="sxs-lookup"><span data-stu-id="fa5e6-136">Status</span></span> |
| --- | --- |
| <span data-ttu-id="fa5e6-137">El desplazamiento horizontal no funciona en los teléfonos Android</span><span class="sxs-lookup"><span data-stu-id="fa5e6-137">Horizontal scrolling doesn't work on Android phones</span></span> | <span data-ttu-id="fa5e6-138">El desplazamiento horizontal no es un problema en iOS ni en dispositivos de escritorio.</span><span class="sxs-lookup"><span data-stu-id="fa5e6-138">Horizontal scrolling isn't an issue on iOS or desktop devices.</span></span> <span data-ttu-id="fa5e6-139">Estamos trabajando en una solución para Android.</span><span class="sxs-lookup"><span data-stu-id="fa5e6-139">We're working on a fix for Android.</span></span> |
| <span data-ttu-id="fa5e6-140">El saldo es incorrecto si se envía tiempo libre para una fecha futura.</span><span class="sxs-lookup"><span data-stu-id="fa5e6-140">The balance is incorrect when submitting time off for a future date.</span></span> | <span data-ttu-id="fa5e6-141">La previsión no está disponible aún.</span><span class="sxs-lookup"><span data-stu-id="fa5e6-141">Forecasting isn't yet available.</span></span> <span data-ttu-id="fa5e6-142">El saldo se muestra para la fecha actual.</span><span class="sxs-lookup"><span data-stu-id="fa5e6-142">The balance displays for the current date.</span></span> |
| <span data-ttu-id="fa5e6-143">No se puede cancelar una solicitud **En revisión**.</span><span class="sxs-lookup"><span data-stu-id="fa5e6-143">Unable to cancel an **In review** request.</span></span> | <span data-ttu-id="fa5e6-144">Esta funcionalidad no es compatible actualmente y se agregará en una versión futura.</span><span class="sxs-lookup"><span data-stu-id="fa5e6-144">This functionality isn't currently supported and will be added in a future release.</span></span> |
| <span data-ttu-id="fa5e6-145">La información del saldo se calcula a partir de hoy.</span><span class="sxs-lookup"><span data-stu-id="fa5e6-145">Balance information is calculated as of today.</span></span> | <span data-ttu-id="fa5e6-146">El sistema actualmente no muestra saldos a partir del período de acumulación, incluso si está configurado en los parámetros de Baja y Ausencia.</span><span class="sxs-lookup"><span data-stu-id="fa5e6-146">The system currently doesn't display balances as of the accrual period, even if it's configured in Leave and absence parameters.</span></span> |

## <a name="troubleshooting"></a><span data-ttu-id="fa5e6-147">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="fa5e6-147">Troubleshooting</span></span>

<span data-ttu-id="fa5e6-148">Si un usuario tiene problemas para iniciar sesión o utilizar la aplicación Equipos de recursos humanos, intente seguir estas instrucciones de solución de problemas.</span><span class="sxs-lookup"><span data-stu-id="fa5e6-148">If a user is having trouble signing into or using the Human Resources Teams app, try following these troubleshooting instructions.</span></span> <span data-ttu-id="fa5e6-149">Si sigue teniendo problemas después de la resolución de problemas, comuníquese con Soporte.</span><span class="sxs-lookup"><span data-stu-id="fa5e6-149">If you're still having problems after troubleshooting, contact Support.</span></span> <span data-ttu-id="fa5e6-150">Para obtener más información, consulte [Obtener soporte](hr-admin-troubleshooting-support.md).</span><span class="sxs-lookup"><span data-stu-id="fa5e6-150">For more information, see [Get support](hr-admin-troubleshooting-support.md).</span></span>

### <a name="cant-sign-into-the-human-resources-app-in-teams"></a><span data-ttu-id="fa5e6-151">No puedo iniciar sesión en la aplicación de recursos humanos en Teams</span><span class="sxs-lookup"><span data-stu-id="fa5e6-151">Can't sign into the Human Resources app in Teams</span></span>

<span data-ttu-id="fa5e6-152">Si un usuario se comunica con usted porque no puede iniciar sesión en la aplicación, verifique que el usuario tenga un registro de empleado asociado en Human Resources.</span><span class="sxs-lookup"><span data-stu-id="fa5e6-152">If a user contacts you because they can't sign into the app, verify that the user has an associated employee record in Human Resources.</span></span>

### <a name="error-when-approving-leave-requests-in-the-human-resources-app-in-teams"></a><span data-ttu-id="fa5e6-153">Error al aprobar solicitudes de licencia en la aplicación Human Resources en Teams</span><span class="sxs-lookup"><span data-stu-id="fa5e6-153">Error when approving leave requests in the Human Resources app in Teams</span></span>

<span data-ttu-id="fa5e6-154">Si un usuario recibe un error mientras intenta aprobar solicitudes de permiso en la aplicación Teams, realice los siguientes pasos de solución de problemas:</span><span class="sxs-lookup"><span data-stu-id="fa5e6-154">If a user receives an error while trying to approve leave requests in the Teams app, perform the following troubleshooting steps:</span></span>

1. <span data-ttu-id="fa5e6-155">Verifique que su cuenta de Teams sea la misma que usan para acceder a Human Resources.</span><span class="sxs-lookup"><span data-stu-id="fa5e6-155">Verify that their Teams account is the same one they use for accessing Human Resources.</span></span>

2. <span data-ttu-id="fa5e6-156">Verifique que son un aprobador válido para la solicitud al verificar la configuración del flujo de trabajo para la aprobación de la licencia.</span><span class="sxs-lookup"><span data-stu-id="fa5e6-156">Verify that they're a valid approver for the request by checking the workflow settings for leave approval.</span></span> <span data-ttu-id="fa5e6-157">Para obtener más información sobre los flujos de trabajo de solicitud de licencia, consulte [Crear un flujo de trabajo de solicitud de licencia](hr-leave-and-absence-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="fa5e6-157">For more information about leave request workflows, see [Create a leave request workflow](hr-leave-and-absence-workflow.md).</span></span>

## <a name="privacy-notice"></a><span data-ttu-id="fa5e6-158">Aviso de privacidad</span><span class="sxs-lookup"><span data-stu-id="fa5e6-158">Privacy notice</span></span>

### <a name="microsoft-language-understanding-intelligent-service-luis"></a><span data-ttu-id="fa5e6-159">Servicio inteligente de comprensión del lenguaje de Microsoft (LUIS)</span><span class="sxs-lookup"><span data-stu-id="fa5e6-159">Microsoft Language Understanding Intelligent Service (LUIS)</span></span>

<span data-ttu-id="fa5e6-160">Con el bot de Dynamics 365 Human Resources en Microsoft Teams, las entradas de texto del usuario se analizan para comprender la consulta/intención subyacente.</span><span class="sxs-lookup"><span data-stu-id="fa5e6-160">With the Dynamics 365 Human Resources bot in Microsoft Teams, the user’s text inputs are analyzed for understanding the underlying query/intent.</span></span> <span data-ttu-id="fa5e6-161">La entrada del usuario como “Buscar cuenta de Contoso” se enruta a uno de los Servicios cognitivos de Microsoft, denominado Servicio inteligente de comprensión del lenguaje (LUIS).</span><span class="sxs-lookup"><span data-stu-id="fa5e6-161">The user’s input such as “Search account Contoso” is routed to one of Microsoft’s Cognitive Service called Language Understanding Intelligent Service (LUIS).</span></span> <span data-ttu-id="fa5e6-162">Obtenga más información sobre LUIS [aquí](https://www.luis.ai/).</span><span class="sxs-lookup"><span data-stu-id="fa5e6-162">Read more about LUIS [here](https://www.luis.ai/).</span></span> <span data-ttu-id="fa5e6-163">El servicio LUIS desambigua o comprende la intención de la entrada del usuario (en este caso, la intención es encontrar información) y la entidad objetivo (en este caso, la entidad objetivo es una cuenta llamada Contoso).</span><span class="sxs-lookup"><span data-stu-id="fa5e6-163">The LUIS service disambiguates or understands the intent of user input (in this case, the intent is to find information) and the target entity (in this case, the intended entity is an account named Contoso).</span></span> <span data-ttu-id="fa5e6-164">Esta información se pasa luego al  [marco de bot de Azure](https://azure.microsoft.com/services/bot-service/) de Microsoft, que interactúa con los datos de Dynamics 365 Human Resources y recupera la información deseada para la consulta del usuario.</span><span class="sxs-lookup"><span data-stu-id="fa5e6-164">This information is then passed on to Microsoft’s [Azure bot framework](https://azure.microsoft.com/services/bot-service/), which interacts with data from Dynamics 365 Human Resources and retrieves the desired information for the user query.</span></span> 

<span data-ttu-id="fa5e6-165">Al instalar y permitir el acceso al uso del bot, usted acepta permitir que el servicio LUIS y el marco del bot de Azure procesen la intención de detrás de la entrada, lo que da por resultado una experiencia de usuario conversacional mejorada.</span><span class="sxs-lookup"><span data-stu-id="fa5e6-165">By installing and allowing access to use of the bot, you agree to allow the LUIS service and Azure bot framework to process the intent behind the input,  which results in an enhanced conversational user experience.</span></span> <span data-ttu-id="fa5e6-166">El servicio LUIS y el marco de bot de Azure pueden tener diferentes niveles de cumplimiento en comparación con Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="fa5e6-166">The LUIS service and Azure bot framework may have varying levels of compliance compared to Dynamics 365 Human Resources.</span></span> <span data-ttu-id="fa5e6-167">Si bien el servicio LUIS solo tiene acceso a las consultas del usuario y no está diseñado para conectarse a datos o a la cuenta Dynamics 365 Human Resources del usuario, un usuario del bot Dynamics 365 Human Resources podría Introducir voluntariamente una consulta que contenga datos del cliente, datos personales u otros datos y dicho contenido de la consulta podría enviarse al servicio LUIS y al marco del bot de Azure.</span><span class="sxs-lookup"><span data-stu-id="fa5e6-167">While the LUIS service has access to only the user queries and is not designed to be connected to the user’s Dynamics 365 Human Resources data or account, a user of the Dynamics 365 Human Resources bot could voluntarily enter a query containing Customer Data, Personal Data, or other data and such query content could get sent to the LUIS service and the Azure bot framework.</span></span> 

<span data-ttu-id="fa5e6-168">El contenido de las consultas y los mensajes del usuario se conserva en el sistema LUIS durante un máximo de 30 días, se cifra en reposo y no se utiliza para la formación ni la mejora del servicio.</span><span class="sxs-lookup"><span data-stu-id="fa5e6-168">The content of user’s queries and messages is retained in LUIS system for a maximum of 30 days, is encrypted at rest, and is not used for training or service improvement.</span></span> <span data-ttu-id="fa5e6-169">Puede obtener más información sobre servicios cognitivos  [aquí](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/).</span><span class="sxs-lookup"><span data-stu-id="fa5e6-169">Read more about Cognitive Services [here](https://azure.microsoft.com/services/cognitive-services/language-understanding-intelligent-service/).</span></span> 

<span data-ttu-id="fa5e6-170">Para administrar la configuración de administración de aplicaciones en Microsoft Teams, vaya al [Centro de administración de Microsoft Teams](https://admin.teams.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="fa5e6-170">To manage admin settings for apps in Microsoft Teams, go to the [Microsoft Teams admin center](https://admin.teams.microsoft.com/).</span></span>

### <a name="microsoft-teams-azure-event-grid-and-azure-cosmos-db"></a><span data-ttu-id="fa5e6-171">Microsoft Teams, Azure Event Grid y Azure Cosmos DB</span><span class="sxs-lookup"><span data-stu-id="fa5e6-171">Microsoft Teams, Azure Event Grid, and Azure Cosmos DB</span></span>

<span data-ttu-id="fa5e6-172">Al utilizar la característica de notificaciones para la aplicación Dynamics 365 Human Resources en Microsoft Teams, algunos datos de clientes saldrán de la región geográfica donde se implementa el servicio de Recursos Humanos del inquilino.</span><span class="sxs-lookup"><span data-stu-id="fa5e6-172">When using the Dynamics 365 Human Resources app in Microsoft Teams, certain customer data may flow outside of the geographic region where your tenant’s Human Resources service is deployed.</span></span>

<span data-ttu-id="fa5e6-173">Dynamics 365 Human Resources transmite la solicitud de licencia del empleado y los detalles de la tarea del flujo de trabajo a Microsoft Azure Event Grid y Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="fa5e6-173">Dynamics 365 Human Resources transmits the employee’s leave request and workflow task details to Microsoft Azure Event Grid and Microsoft Teams.</span></span> <span data-ttu-id="fa5e6-174">Estos datos pueden almacenarse en Microsoft Azure Event Grid hasta por 24 horas y se procesarán en los Estados Unidos, están cifrados en tránsito y en reposo, y Microsoft o sus subprocesadores no los utilizan para mejoras de formación o servicios.</span><span class="sxs-lookup"><span data-stu-id="fa5e6-174">This data may be stored in Microsoft Azure Event Grid for up to 24 hours and will be processed in the United States, is encrypted in transit and at rest, and is not used by Microsoft or its subprocessors for training or service improvements.</span></span> <span data-ttu-id="fa5e6-175">Para comprender dónde se almacenan sus datos en Teams, consulte: [Ubicación de los datos en Microsoft Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams?view=o365-worldwide&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="fa5e6-175">To understand where your data is stored in Teams, please see: [Location of data in Microsoft Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams?view=o365-worldwide&preserve-view=true).</span></span>

<span data-ttu-id="fa5e6-176">Mientras conversa con el bot de chat en la aplicación de Recursos Humanos, el contenido de la conversación puede almacenarse en Azure Cosmos DB y transmitirse a Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="fa5e6-176">While conversing with the chat bot in the Human Resources app, the conversation content may be stored in Azure Cosmos DB and transmitted to Microsoft Teams.</span></span> <span data-ttu-id="fa5e6-177">Estos datos pueden almacenarse en Azure Cosmos DB durante un máximo de 24 horas y pueden procesarse fuera de la región geográfica donde se implementa el servicio de Recursos Humanos de su inquilino, están cifrados en tránsito y en reposo, y Microsoft o sus subprocesadores no los utilizan para mejoras de formación o servicio.</span><span class="sxs-lookup"><span data-stu-id="fa5e6-177">This data may be stored in Azure Cosmos DB for up to 24 hours and may be processed outside of the geographic region where your tenant's Human Resources service is deployed, is encrypted in transit and at rest, and is not used by Microsoft or its subprocessors for training or service improvements.</span></span> <span data-ttu-id="fa5e6-178">Para comprender dónde se almacenan sus datos en Teams, consulte: [Ubicación de los datos en Microsoft Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams?view=o365-worldwide&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="fa5e6-178">To understand where your data is stored in Teams, please see: [Location of data in Microsoft Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams?view=o365-worldwide&preserve-view=true).</span></span>
 
<span data-ttu-id="fa5e6-179">Para restringir el acceso a la aplicación de Recursos Humanos en Microsoft Teams para su organización o para usuarios de su organización, consulte [Administrar las directivas de permisos de aplicaciones en Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).</span><span class="sxs-lookup"><span data-stu-id="fa5e6-179">To restrict access to the Human Resources app in Microsoft Teams for your organization or users within your organization, see [Manage app permission policies in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-app-permission-policies).</span></span>

## <a name="see-also"></a><span data-ttu-id="fa5e6-180">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fa5e6-180">See also</span></span> 

[<span data-ttu-id="fa5e6-181">Descargar e instalar Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fa5e6-181">Download and install Microsoft Teams</span></span>](https://support.office.com/article/download-and-install-microsoft-teams-422bf3aa-9ae8-46f1-83a2-e65720e1a34d)</br>
[<span data-ttu-id="fa5e6-182">Centro de ayuda de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fa5e6-182">Microsoft Teams help center</span></span>](https://support.office.com/teams)</br>
[<span data-ttu-id="fa5e6-183">Administrar solicitudes de bajas en Teams</span><span class="sxs-lookup"><span data-stu-id="fa5e6-183">Manage leave requests in Teams</span></span>](hr-teams-leave-app.md)

